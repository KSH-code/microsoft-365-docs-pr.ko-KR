---
title: 고급 사냥을 사용 하는 장치, 전자 메일, 앱 및 id 간의 위협에 대 한 헌트
description: 장치, 전자 메일, 앱 및 id를 다루는 일반적인 구하기 시나리오 및 샘플 쿼리를 연구 합니다.
keywords: 고급 구하기, Office365 데이터, Windows 장치, Office365 전자 메일 표준화, 전자 메일, 앱, id, 위협 검색, 사이버 위협 검색, 검색, 쿼리, 원격 분석, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9f5468ccb853bbbe126198a14f7b824d953a2738
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412637"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>장치, 전자 메일, 앱 및 id 간의 위협 구하기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft Threat Protection

Microsoft Threat Protection의 [고급 구하기](advanced-hunting-overview.md) 에서는 다음을 통해 위협을 사전에 사냥 할 수 있습니다.
- Microsoft Defender ATP에서 관리 하는 장치
- Microsoft 365에서 처리 하는 전자 메일
- Microsoft Cloud App Security 및 Azure ATP에서 추적 하는 클라우드 앱 작업, 인증 이벤트 및 도메인 컨트롤러 작업

이 표시 수준을 사용 하면 전자 메일 또는 웹에 도착 하는 정교한 침입, 로컬 권한 승격, 권한이 부여 된 도메인 자격 증명 획득 및 장치 간에 laterally 이동을 비롯 하 여 네트워크의 섹션을 통과 하는 위협 요소를 신속 하 게 파악할 수 있습니다. 

다음과 같은 복잡 한 위협을 검색할 때 쿼리를 구성 하는 방법을 살펴보는 데 도움이 되는 다양 한 구하기 시나리오를 기반으로 하는 일반적인 기술 및 예제 쿼리가 나와 있습니다.

## <a name="get-entity-info"></a>엔터티 정보 가져오기
이러한 쿼리를 사용 하 여 사용자 계정, 장치 및 파일에 대 한 정보를 빠르게 가져올 수 있는 방법을 알아봅니다. 

### <a name="obtain-user-accounts-from-email-addresses"></a>전자 메일 주소에서 사용자 계정 가져오기
[장치와 전자 메일을 포함하는 테이블](advanced-hunting-schema-tables.md)에서 쿼리를 생성할 때 보낸 사람 또는 받는 사람 전자 메일 주소에서 사용자 계정 이름을 확인해야 할 수 있습니다. 일반적으로 전자 메일 주소에서 *로컬 호스트* 를 사용 하 여 받는 사람 또는 보낸 사람 주소에 대해이 작업을 수행할 수 있습니다.

아래 코드 조각에서는 [tostring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) kusto 함수를 사용 하 여 `@` 열에서 from 받는 사람 전자 메일 주소 바로 앞에 로컬 호스트를 추출 합니다 `RecipientEmailAddress` .

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
아래 쿼리는이 코드 조각을 사용할 수 있는 방법을 보여 줍니다.

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>IdentityInfo 테이블 병합

[IdentityInfo 테이블](advanced-hunting-identityinfo-table.md)을 병합 하거나 조인 하 여 계정 이름 및 기타 계정 정보를 볼 수 있습니다. 아래 쿼리는 [Emailevents 테이블](advanced-hunting-emailevents-table.md) 에서 피싱 및 맬웨어 검색 목록을 얻은 다음 해당 정보를 `IdentityInfo` 표에 조인 하 여 각 받는 사람에 대 한 자세한 정보를 확인 합니다. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>장치 정보 가져오기
[고급 구하기 스키마](advanced-hunting-schema-tables.md) 는 다양 한 테이블에 광범위 한 장치 정보를 제공 합니다. 예를 들어 [DeviceInfo 테이블](advanced-hunting-deviceinfo-table.md) 은 정기적으로 집계 되는 이벤트 데이터를 기반으로 하는 포괄적인 장치 정보를 제공 합니다. 이 쿼리는 테이블을 사용 하 여 `DeviceInfo` 손상 가능성이 있는 사용자 ( `<account-name>` )가 모든 장치에 로그온 되어 있는지 확인 한 다음 해당 장치에서 트리거된 경고를 나열 합니다.

>[!Tip]
> 이 쿼리는 `kind=inner` 왼쪽에 있는 값의 중복 제거를 차단 하는 [내부 조인을](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)지정 하는 데 사용 `DeviceId` 됩니다.

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a>헌팅 시나리오

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Zapped 되지 않은 전자 메일을 받은 사용자의 로그온 작업을 나열 합니다.
[0 시간 자동 삭제 (ZAP)](../office-365-security/zero-hour-auto-purge.md) 는 받은 후 악성 전자 메일을 처리 합니다. ZAP이 실패 하면 악성 코드가 장치에서 실행 되어 계정을 손상 시킬 수 있습니다. 이 쿼리는 ZAP에서 해결 되지 않은 전자 메일을 받는 사람이 수행한 로그온 활동을 확인 합니다.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>자격 증명 도용의 대상이 되는 도메인 계정에의 한 로그온 시도 받기
이 쿼리는 먼저 테이블의 모든 자격 증명 액세스 알림을 식별 `AlertInfo` 합니다. 그런 다음 대상으로 지정 된 `AlertEvidence` 계정 및 필터의 이름을 구문 분석 하는 테이블을 병합 하거나 조인 합니다. 마지막으로 테이블을 검사 `IdentityLogonEvents` 하 여 도메인에 가입 된 대상 계정으로 모든 로그온 작업을 가져옵니다.

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>알려진 악의적인 보낸 사람의 파일이 장치에 있는지 확인
악성 파일을 보내는 전자 메일 주소 ()를 알고 있다고 가정 하면 `MaliciousSender@example.com` 이 쿼리를 실행 하 여이 보낸 사람의 파일이 장치에 있는지 확인할 수 있습니다. 예를 들어이 쿼리를 사용 하 여 맬웨어 배포 캠페인의 영향을 받는 장치를 확인할 수 있습니다.

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>악의적인 전자 메일을 받은 후에 로그온 시도를 검토합니다.
이 쿼리는 알려진 악의적인 전자 메일을 받은 후 30분 이내에 전자 메일 받는 사람이 수행한 10개의 최신 로그온을 찾습니다. 이 쿼리를 사용하여 전자 메일 받는 사람의 계정이 노출되었는지 확인할 수 있습니다.

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where MalwareFilterVerdict == "Malware"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>알려진 악의적인 보낸 사람의 전자 메일을 수신 후 PowerShell 활동 검토
악의적인 전자 메일에는 종종 추가 페이로드를 전달하기 위해 PowerShell 명령을 실행하는 문서 및 특수하게 조작된 기타 첨부 파일이 포함 됩니다. 알려진 악성 보낸 사람 ()이 보내는 전자 메일을 알고 있는 경우 `MaliciousSender@example.com` 이 쿼리를 사용 하 여 보낸 사람 으로부터 받은 전자 메일이 30 분 이내에 발생 한 PowerShell 활동을 나열 하 고 검토할 수 있습니다.  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
