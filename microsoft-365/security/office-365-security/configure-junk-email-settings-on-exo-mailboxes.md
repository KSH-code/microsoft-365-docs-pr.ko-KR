---
title: Exchange Online 사서함에 대한 정크 메일 설정 구성
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online 사서함에서 정크 메일 설정을 구성 하는 방법을 알 수 있습니다. 이러한 설정 중 상당수는 Outlook 또는 웹용 Outlook에서 사용자에 게 제공 됩니다.
ms.openlocfilehash: 72b2680cb16e9d8d0f33ee3ec8a080206c68bf97
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352513"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online 사서함에 대한 정크 메일 설정 구성

Exchange Online의 사서함이 있는 Microsoft 365 조직에서 조직 스팸 방지 설정은 EOP (Exchange Online Protection)에 의해 제어 됩니다. 자세한 내용은 [EOP의 스팸 방지 보호](anti-spam-protection.md)를 참조 하세요.

그러나 관리자가 Exchange Online의 개별 사서함에 대해 구성할 수 있는 특정 스팸 방지 설정도 있습니다.

- **정크 메일 규칙을 사용 하거나 사용 하지 않도록**설정: 정크 메일 규칙은 모든 사서함에서 기본적으로 사용 하도록 설정 된 정크 메일 규칙 이라는 숨겨진 받은 편지함 규칙입니다. 정크 메일 규칙은 다음과 같은 기능을 제어 합니다.

  - **스팸 방지 정책을 기반으로 정크 메일 폴더로 메시지 이동**: 스팸 방지 정책에 대 한 **메시지 이동** 작업을 정크 메일 필터링 결과으로 구성한 경우 정크 메일 필터 규칙은 메시지가 사서함으로 배달 된 후 해당 메시지를 정크 메일 폴더로 이동 합니다. 스팸 방지 정책에서의 스팸 필터링 verdicts에 대 한 자세한 내용은 Configure 안티스팸 information For [EOP](configure-your-spam-filter-policies.md)을 참조 하십시오. 마찬가지로, ZAP (자동 삭제)이 배달 된 메시지가 스팸으로 또는 피싱 경우 정크 메일 필터 규칙은 메시지를 **정크 메일 폴더** 스팸 필터링 결과 작업으로 이동 하기 위해 정크 메일 폴더로 이동 합니다. ZAP에 대 한 자세한 내용은 [Exchange Online에서 제로 시간 자동 삭제 (ZAP)](zero-hour-auto-purge.md)를 참조 하세요.
  
  - **사용자가 Outlook 또는 웹용 outlook에서 자신을 위해 구성 하는 정크 메일 설정**: _수신 허용 목록 컬렉션_ 은 수신 허용-보낸 사람 목록, 수신 허용-받는 사람 목록 및 각 사서함의 보낸 사람 차단 목록입니다. 이러한 목록의 항목에 따라 정크 메일 규칙에서 메시지를 받은 편지함 또는 정크 메일 폴더로 이동할 것인지 여부가 결정 됩니다. 사용자는 Outlook 또는 웹용 Outlook (이전의 Outlook Web App)에서 자신의 사서함에 대 한 수신 허용 목록 컬렉션을 구성할 수 있습니다. 관리자는 모든 사용자 사서함에서 수신 허용 목록 컬렉션을 구성할 수 있습니다.

사서함에서 정크 메일 규칙을 사용 하도록 설정 하면 EOP에서 사서함에 대 한 스팸 필터링 결과 작업 **이동 메시지를 정크** 메일 폴더 또는 수신 거부 목록에 기반 하 여 정크 메일 폴더로 이동 하 고 메시지를 정크 메일 폴더 (사서함의 수신 허용-보낸 사람 목록에 기반)로 배달 하지 않도록 할 수 있습니다.

 사서함에서 정크 메일 규칙을 사용 하지 않도록 설정 된 경우 EOP에서 스팸 필터링 결과 동작 **메시지를 정크 메일** 폴더로 이동 하거나 사서함에서 수신 허용 목록 모음으로 메시지를 이동할 수 없습니다.

관리자는 Exchange Online PowerShell을 사용 하 여 사서함에 대 한 정크 메일 규칙의 상태를 사용 하지 않도록 설정 하 고 사용 하도록 설정할 수 있습니다. 또한 관리자는 Exchange Online PowerShell을 사용 하 여 사서함의 수신 허용 목록 컬렉션, 즉 수신 허용-보낸 사람 목록 및 수신 거부 목록에 있는 항목을 구성할 수 있습니다.

> [!NOTE]
> 사용자가 자체 수신 허용-보낸 사람 목록에 추가한 보낸 사람의 메시지는 EOP 필터링 (SCL은-1)을 건너뜁니다. 사용자가 Outlook에서 수신 허용-보낸 사람 목록에 항목을 추가 하지 못하도록 하려면이 항목 뒷부분의 [outlook의 정크 메일 설정](#about-junk-email-settings-in-outlook) 섹션에 설명 된 대로 그룹 정책을 사용 합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 다음 절차를 수행 하는 경우에만 Exchange Online PowerShell을 사용할 수 있습니다. Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.

- 이러한 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다. 특히 **조직 관리**, **받는 사람 관리**및 **사용자 지정 메일 받는 사람** 역할 그룹에 기본적으로 할당 되는 **메일 받는 사람** 역할 (기본적으로 **조직 관리** 및 **Help Desk** 역할 그룹에 할당 되는 **사용자 옵션** 역할)이 필요 합니다. Exchange Online에서 역할 그룹에 사용자를 추가 하려면 [Exchange online에서 역할 그룹 수정을](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)참조 하십시오. 기본 사용 권한이 있는 사용자는 [Exchange Online PowerShell에](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)대 한 액세스 권한이 있는 경우 자체 사서함에서 동일한 절차를 수행할 수 있습니다.

- EOP로 온-프레미스 Exchange 사서함을 보호하는 독립 실행형 EOP 환경에서는 EOP 스팸 필터링 결과를 변환하여 정크 메일 규칙에 따라 메시지를 정크 메일 폴더로 이동하기 위해 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.

- 공유 사서함에 대 한 안전한 보낸 사람은 Azure AD 및 EOP에 대 한 동기화가 되지 않습니다.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Exchange Online PowerShell을 사용 하 여 사서함에서 정크 메일 규칙을 사용 하거나 사용 하지 않도록 설정

> [!NOTE]
> **Set-mailboxjunkemailconfiguration** cmdlet을 사용 하 여 Outlook (캐시 된 Exchange 모드) 또는 웹용 outlook에서 열린 사서함에 대해 정크 메일 규칙을 사용 하지 않도록 설정할 수 있습니다. 사서함이 열려 있지 않으면 다음 오류가 표시 됩니다. `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` 대량 작업에 대해이 오류를 표시 하지 않으려면 `-ErrorAction SlientlyContinue` **set-mailboxjunkemailconfiguration** 명령에 추가할 수 있습니다.

사서함에 대해 정크 메일 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

이 예에서는 Ori Epstein의 사서함에 대 한 정크 메일 규칙을 사용 하지 않도록 설정 합니다.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

이 예에서는 조직의 모든 사용자 사서함에 대해 정크 메일 규칙을 사용 하지 않도록 설정 합니다.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

구문 및 매개 변수에 대 한 자세한 내용은 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)를 참조 하십시오.

> [!NOTE]
> 
> - 사용자가 자신의 사서함을 연 적이 없는 경우 이전 명령을 실행 하면 오류가 발생할 수 있습니다. 대량 작업에서이 오류가 발생 하지 않도록 `-ErrorAction SlientlyContinue` **설정 하려면 set-mailboxjunkemailconfiguration** 명령에 추가 합니다.
> 
> - 정크 메일 규칙을 사용 하지 않도록 설정 하는 경우에도 Outlook 정크 메일 필터 (구성 된 방법에 따라)는 메시지의 스팸 여부를 확인할 수 있으며 사서함의 자체 스팸 결과 및 수신 허용 목록 컬렉션을 기반으로 받은 편지함 또는 정크 메일 폴더로 메시지를 이동할 수 있습니다. 자세한 내용은이 항목의 [Outlook의 정크 메일 설정](#about-junk-email-settings-in-outlook) 섹션을 참조 하십시오.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

사서함에서 정크 메일 규칙을 사용 하거나 사용 하지 않도록 성공적으로 설정 했는지 확인 하려면 다음 절차 중 하나를 사용 하십시오.

- _ \< MailboxIdentity \> _ 를 사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 하 여 **Enabled** 속성 값을 확인 합니다.

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell을 사용 하 여 사서함에 대 한 수신 허용 목록 컬렉션 구성

사서함의 수신 허용 목록 컬렉션에는 수신 허용-보낸 사람 목록, 수신 허용-받는 사람 목록 및 수신 거부 목록이 포함 됩니다. 기본적으로 사용자는 Outlook 또는 웹용 Outlook에서 자체 사서함에 수신 허용 목록 모음을 구성할 수 있습니다. 관리자는 **set-mailboxjunkemailconfiguration** cmdlet에 해당 하는 매개 변수를 사용 하 여 사용자의 사서함에서 수신 허용 목록 컬렉션을 구성할 수 있습니다. 이러한 매개 변수에 대 한 설명은 다음 표에 나와 있습니다.

|||
|---|---|
|**Set-mailboxjunkemailconfiguration의 매개 변수**|**웹용 Outlook 설정**|
|_BlockedSendersAndDomains_|**다음 보낸 사람이 나 도메인에서 정크 메일 폴더로 전자 메일 이동**|
|_ContactsTrusted_|**내 연락처에서 전자 메일 신뢰**|
|_TrustedListsOnly_|**수신 허용-보낸 사람 및 도메인 목록 및 수신 허용-메일 그룹의 주소에서 보낸 전자 메일만 신뢰**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**이 보낸 사람 으로부터 정크 메일 폴더로 전자 메일 이동 안 함**|
|

<sup>\*</sup>**참고**사항:

- Exchange Online에서 수신 허용-보낸 사람 목록 또는 _TrustedSendersAndDomains_ 매개 변수의 **도메인 항목** 은 인식 되지 않으므로 전자 메일 주소만 사용 해야 합니다. 독립 실행형 EOP에서 디렉터리 동기화를 사용 하는 경우 도메인 항목은 기본적으로 동기화 되지 않지만 도메인에 대 한 동기화를 사용 하도록 설정할 수 있습니다. 자세한 내용은 [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange)를 참조 하십시오.

- Set-mailboxjunkemailconfiguration cmdlet ( _TrustedRecipientsAndDomains_ 매개 변수는 작동 하지 않음)을 사용 하 여 수신 허용 **-** 받는 사람 목록을 직접 수정할 수는 없습니다. 수신 허용-보낸 사람 목록을 수정 하면 해당 변경 내용이 수신 허용-받는 사람 목록에 동기화 됩니다.

사서함에 대해 수신 허용 목록 컬렉션을 구성 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

여러 값을 입력 하 고 _BlockedSendersAndDomains_ 및 _TrustedSendersAndDomains_ 매개 변수에 대 한 기존 항목을 덮어쓰려면 다음 구문을 사용 합니다 `"<Value1>","<Value2>"...` . 기존의 다른 항목에 영향을 주지 않고 하나 이상의 값을 추가 하거나 제거 하려면 다음 구문을 사용 합니다.`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

이 예에서는 Ori Epstein의 사서함에서 수신 허용 목록 컬렉션에 대 한 다음 설정을 구성 합니다.

- Shopping@fabrikam.com 값을 수신 거부 목록에 추가 합니다.

- 수신 허용-보낸 사람 목록 및 안전한 받는 사람 목록에서 chris@fourthcoffee.com 값을 제거 합니다.

- 연락처 폴더의 연락처를 신뢰할 수 있는 보낸 사람으로 처리 하도록 구성 합니다.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

이 예에서는 조직의 모든 사용자 사서함에 있는 수신 거부 목록에서 contoso.com 도메인을 제거 합니다.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

구문 및 매개 변수에 대 한 자세한 내용은 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)를 참조 하십시오.

> [!NOTE]
> 
> - 사용자가 자신의 사서함을 연 적이 없는 경우에는 이전 명령을 실행할 때 오류가 표시 될 수 있습니다. 대량 작업에서이 오류가 발생 하지 않도록 `-ErrorAction SlientlyContinue` **설정 하려면 set-mailboxjunkemailconfiguration** 명령에 추가 합니다.
> 
> - 사서함에서 정크 메일 규칙이 사용 하지 않도록 설정 된 경우에도 수신 허용 목록 컬렉션을 구성할 수 있으며 Outlook 정크 메일 필터는 메시지를 받은 편지함 또는 정크 메일 폴더로 이동할 수 있습니다. 자세한 내용은이 항목의 [Outlook의 정크 메일 설정](#about-junk-email-settings-in-outlook) 섹션을 참조 하십시오.
> 
> - Outlook 정크 메일 필터에는 추가 수신 허용 목록 모음 설정 (예: **수신 허용-보낸 사람 목록에 전자 메일을 자동으로 추가**)이 있습니다. 자세한 내용은 [정크 메일 필터를 사용 하 여 표시 되는 메시지 제어](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077)를 참조 하세요.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

사서함에 수신 허용 목록 컬렉션을 성공적으로 구성 했는지 확인 하려면 다음 절차 중 하나를 사용 하십시오.

- _ \< MailboxIdentity \> _ 를 사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 하 여 속성 값을 확인 합니다.

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  값 목록이 너무 길면 다음 구문을 사용 합니다.

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Outlook의 정크 메일 설정 정보

Outlook에서 사용할 수 있는 클라이언트 쪽 정크 메일 필터 설정을 사용 하거나 사용 하지 않도록 설정 하 고 구성 하려면 그룹 정책을 사용 합니다. 자세한 내용은 [관리 템플릿 파일 (ADMX/ADML) 및 Office 사용자 지정 365 도구 (엔터프라이즈, office 2019 및 office 2016 용)](https://www.microsoft.com/download/details.aspx?id=49030) 및 [정크 메일 설정 (예: 그룹 정책을 사용 하 여 수신 허용-보낸 사람 목록)을 배포 하는 방법을](https://support.microsoft.com/help/2252421/how-to-deploy-junk-email-settings-such-as-the-safe-senders-list-by-usi)참조 하세요.

Outlook 정크 메일 필터를 기본값으로 설정 하 고 **홈** 정크 메일 옵션 옵션에서 **자동 필터링** 을 사용 하지 않으면 \> **Junk** \> **Junk E-Mail Options** \> **Options**outlook이 massages로 분류를 시도 하지 않지만 수신 허용-보낸 사람 목록, 수신 허용-받는 사람 목록 및 수신 거부 목록에 있는 수신 허용 목록 컬렉션을 통해 메시지를 배달 후 정크 메일 폴더로 이동 합니다. 이러한 설정에 대 한 자세한 내용은 [정크 메일 필터 개요](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)를 참조 하세요.

Outlook 정크 메일 필터를 **낮음** 또는 **높음으로**설정 하면 outlook 정크 메일 필터는 자체 SmartScreen 필터 기술을 사용 하 여 스팸 메일을 식별 하 고 정크 메일로 이동 합니다. 이 스팸 분류는 EOP에 의해 결정 되는 SCL (스팸 지 수)과는 다릅니다. 실제로 Outlook은 EOP에서 SCL을 무시 합니다 (EOP가 스팸 필터링을 건너뛰도록 메시지를 표시 하지 않는 경우). 물론 EOP의 스팸 결과와 Outlook이 같을 수도 있습니다. 이러한 설정에 대 한 자세한 내용은 [정크 메일 필터에서 보호 수준 변경을](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)참조 하십시오.

> [!NOTE]
> 11 월 2016 일에 Microsoft는 Exchange 및 Outlook의 SmartScreen 필터에 대 한 스팸 정의 업데이트 생성을 중지 했습니다. 기존 SmartScreen 스팸 정의는 그대로 남아 있지만 해당 효율성은 시간이 지남에 따라 저하 될 수 있습니다. 자세한 내용은 [Outlook 및 Exchange에서 SmartScreen 지원 삭제](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)를 참조하세요.

따라서 Outlook 정크 메일 필터는 사서함에서 정크 메일 규칙을 사용할 수 없는 경우에도 사서함의 수신 허용 목록 모음과 자체 스팸 분류를 사용 하 여 메시지를 정크 메일 폴더로 이동할 수 있습니다.

Outlook 및 웹용 Outlook은 모두 수신 허용 목록 컬렉션을 지원 합니다. 수신 허용 목록 컬렉션은 Exchange Online 사서함에 저장 되므로 Outlook에서 수신 허용 목록 컬렉션에 대 한 변경 내용은 웹용 Outlook에 표시 되며 그 반대의 경우도 마찬가지입니다.

## <a name="limits-for-junk-email-settings"></a>정크 메일 설정에 대 한 제한

사용자의 사서함에 저장 된 수신 허용 목록 컬렉션 (수신 허용-보낸 사람 목록, 수신 허용-받는 사람 목록 및 수신 거부 목록)도 EOP로 동기화 됩니다. 디렉터리 동기화를 사용 하는 경우 수신 허용 목록 컬렉션은 Azure AD로 동기화 됩니다.

- 사용자 사서함의 수신 허용 목록 컬렉션에는 모든 목록 및 추가 정크 메일 필터 설정을 포함 하는 510의 제한이 있습니다. 이 제한을 초과 하는 사용자는 다음과 같은 Outlook 오류를 받게 됩니다.

  > 서버 정크 메일 목록에 추가할 수 없습니다. 서버에서 허용 되는 크기를 초과 했습니다. 정크 메일 목록이 서버에서 허용 되는 크기로 줄어들 때까지 서버의 정크 메일 필터는 사용 하지 않도록 설정 됩니다.

  이 제한에 대 한 자세한 내용과이를 변경 하는 방법에 대 한 자세한 내용은 [KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit)를 참조 하십시오.

- EOP에서 동기화 된 수신 허용 목록 컬렉션의 동기화 제한은 다음과 같습니다.

  - 수신 허용-보낸 사람 목록의 모든 항목, 수신 허용-받는 사람 목록 및 외부 연락처 ( **내 연락처에서 신뢰 전자 메일** 을 사용 하도록 설정한 경우) 1024
  - 500 차단할 보낸 사람 목록 및 차단 된 도메인 목록의 총 항목

  1024 항목 제한에 도달 하면 다음과 같은 결과가 발생 합니다.
  
  - 목록에서 PowerShell 및 웹용 Outlook의 항목을 허용 하지 않지만 오류는 표시 되지 않습니다.

    Outlook 사용자는 510 Outlook에서 1024 개 보다 많은 항목을 계속 추가할 수 있습니다. Outlook에서 사서함 (메일 흐름 규칙, 스푸핑 방지 등)에 배달 되기 전에 EOP 필터에서 메시지를 차단 하지 않는 한 이러한 추가 항목을 사용할 수 있습니다.

- 디렉터리 동기화를 사용 하는 경우 항목은 다음 순서 대로 Azure AD에 동기화 됩니다.

  1. **내 연락처의 신뢰 전자 메일** 을 사용 하도록 설정한 경우 메일 연락처입니다.
  2. 수신 허용-보낸 사람 목록 및 수신 허용-받는 사람 목록은 처음 1024 항목을 변경할 때마다 사전순으로 결합 되 고, 복제 되지 않으며, 정렬 됩니다.

  첫 번째 1024 항목이 사용 되 고 관련 정보가 메시지 헤더에 스탬프 처리 됩니다.
  
  Azure AD와 동기화 되지 않은 1024의 항목은 Outlook (웹용 Outlook 아님)에 의해 처리 되며 메시지 헤더에는 어떠한 정보도 기록 되지 않습니다.

여기에서 볼 수 있듯이 **내 연락처에서 전자 메일 신뢰** 설정을 사용 하도록 설정 하면 동기화 할 수 있는 수신 허용-보낸 사람 및 수신 허용-받는 사람 수가 줄어듭니다. 이 문제가 중요 한 경우 그룹 정책을 사용 하 여이 기능을 해제 하는 것이 좋습니다.

- 파일 이름: outlk16 ax
- 정책 설정: **연락처에서 전자 메일 신뢰**
