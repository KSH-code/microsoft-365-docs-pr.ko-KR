---
title: 다음을 사용하여 중요한 정보 유형 정책 Office 365 메시지 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 조직에서 중요한 정보 유형 정책을 만드는 방법을 Office 365 메시지 암호화.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216662"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>메시지 암호화를 사용하여 조직에 대한 중요한 정보 유형 정책 만들기

메일 흐름 규칙 또는 DLP(데이터 손실 방지)를 사용하여 Exchange 중요한 정보 유형 정책을 만들 수 Office 365 메시지 암호화. 메일 흐름 Exchange 만들기 위해 EAC(Exchange 관리 센터) 또는 PowerShell을 사용할 수 있습니다.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>EAC에서 메일 흐름 규칙을 사용하여 정책을 만들면

EAC(Exchange 관리 센터)에 로그인하고 메일 흐름 **규칙으로**  >  **이동하세요.** 규칙 페이지에서 규칙에 적용되는 규칙을 Office 365 메시지 암호화. 메시지 또는 첨부 파일에 특정 키워드 또는 중요한 정보 유형이 있는 경우와 같은 조건에 따라 규칙을 만들 수 있습니다.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>PowerShell에서 메일 흐름 규칙을 사용하여 정책을 만들 수 있습니다.

조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 정책 Set-IRMConfiguration New-TransportRule cmdlet을 사용하여 정책을 만들 수 있습니다.

## <a name="example-mail-flow-rule-created-with-powershell"></a>PowerShell을 통해 만든 메일 흐름 규칙 예

PowerShell에서 다음 명령을 실행하여 전자 Exchange 첨부 파일에 다음과 같은 중요한 정보 유형이 포함되어 있는 경우 암호화 전용 옵션을 사용하여 조직 외부로 전송되는 전자 메일을 자동으로 암호화하는 Exchange 메일 흐름 규칙을 만들 수 있습니다.

- ABA 라우팅 번호
- 신용 카드 번호
- DEA(마약 집행 기구) 번호
- 미국/영국 passport number
- 미국 은행 계좌 번호
- 미국 ITIN(개인 납세자 번호)
- 미국 SSN(사회 보험 번호)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

자세한 내용은 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) 및 [New-TransportRule을 참조하세요.](/powershell/module/exchange/new-transportrule)

## <a name="how-recipients-access-attachments"></a>받는 사람이 첨부 파일에 액세스하는 방법

Microsoft에서 메시지를 암호화한 후 받는 사람은 암호화된 전자 메일에 액세스하고 열 때 첨부 파일에 무제한으로 액세스할 수 있습니다.

## <a name="to-prepare-for-this-change"></a>이 변경을 준비하기 위해

해당 최종 사용자 설명서 및 교육 자료를 업데이트하여 조직의 사용자가 이 변경에 대비할 수 있습니다. 이러한 Office 365 메시지 암호화 리소스를 사용자와 적절하게 공유합니다.

- [PC용 Outlook 암호화된 메시지 보내기, 보기 및 회신](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 필수 동영상: Office 암호화](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>감사 로그에서 이러한 변경 내용 보기

Microsoft 365 감사하고 관리자가 사용할 수 있도록 합니다. 이 작업은 'New-TransportRule'이고, 보안 및 준수 센터의 감사 로그 검색에서 샘플 감사 & 코드는 아래와 같습니다.

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>중요한 정보 유형 정책을 사용하지 않도록 설정하거나 사용자 지정

Exchange 메일 흐름 규칙을 만든 후 EAC(Exchange [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) 관리 센터)의 메일 흐름 규칙으로 이동하여 규칙을 사용하지 않도록 설정하거나 편집하고 "아웃바운드 중요한 전자  >   메일 *암호화(기본* 규칙 사용 안 함) " 규칙을 사용하지 않도록 설정할 수 있습니다.