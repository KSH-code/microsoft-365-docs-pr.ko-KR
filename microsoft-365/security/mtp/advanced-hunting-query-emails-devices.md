---
title: 고급 헌팅을 사용하여 다양한 장치와 전자 메일에서 위협을 찾기
description: 장치와 전자 메일을 포괄하는 일반적인 헌팅 시나리오와 예제 쿼리를 연구하세요.
keywords: 고급 헌팅, Office365 데이터, Windows 장치, Office365 전자 메일 표준화, 전자 메일, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b374aac84b309d18a88ee7248021b50a893e120c
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911416"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>여러 장치 및 전자 메일에서 위협을 탐지

**적용 대상:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

Microsoft Threat Protection의 [고급 헌팅](advanced-hunting-overview.md)을 통해 Windows 장치 및 Office 365 전자 메일 전반에 걸쳐 위협을 사전에 헌팅할 수 있습니다. 다음은 장치와 전자 메일을 모두 포괄하는 쿼리를 구성하는 방법을 탐색하는 데 도움이 되는 몇 가지 헌팅 시나리오와 예제 쿼리입니다.

## <a name="obtain-user-accounts-from-email-addresses"></a>전자 메일 주소에서 사용자 계정 가져오기
[장치와 전자 메일을 포함하는 테이블](advanced-hunting-schema-tables.md)에서 쿼리를 생성할 때 보낸 사람 또는 받는 사람 전자 메일 주소에서 사용자 계정 이름을 확인해야 할 수 있습니다. 이렇게 하려면 전자 메일 주소에서 *로컬 호스트*를 사용합니다.

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

이 정규화 기법은 이후의 시나리오에서 사용됩니다.

## <a name="hunting-scenarios"></a>헌팅 시나리오

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>알려진 악의적인 보낸 사람의 파일이 장치에 있는지 확인
악의적인 파일을 보내는 전자 메일 주소를 알고 있다고 가정하고 이 쿼리를 실행하여 이 보낸 사람의 파일이 장치에 존재하는지 여부를 확인할 수 있습니다. 예를 들어 이 쿼리를 사용하여 맬웨어 배포 캠페인의 영향을 받는 장치 수를 판단할 수 있습니다.

```
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
FileCreationEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>악의적인 전자 메일을 받은 후에 로그온 시도를 검토합니다.
이 쿼리는 알려진 악의적인 전자 메일을 받은 후 30분 이내에 전자 메일 받는 사람이 수행한 10개의 최신 로그온을 찾습니다. 이 쿼리를 사용하여 전자 메일 받는 사람의 계정이 노출되었는지 확인할 수 있습니다.

```
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
LogonEvents
| project LogonTime = EventTime, AccountName, ComputerName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>알려진 악의적인 보낸 사람의 전자 메일을 수신 후 PowerShell 활동 검토
악의적인 전자 메일에는 종종 추가 페이로드를 전달하기 위해 PowerShell 명령을 실행하는 문서 및 특수하게 조작된 기타 첨부 파일이 포함 됩니다. 악의적인 발신자가 보낸 전자 메일을 알고 있는 경우 이 쿼리를 사용하여 보낸 사람으로부터 전자 메일을 받은 후 30분 이내에 발생한 PowerShell 활동을 나열하고 검토할 수 있습니다.  

```
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
ProcessCreationEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = EventTime, AccountName, ComputerName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>관련 항목
- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)