---
title: Exchange Online 사서함에 대한 정크 메일 설정 구성
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 사서함에서 정크 메일 설정을 구성하는 Exchange Online 있습니다. 이러한 설정 중 상당수는 웹에서 Outlook Outlook 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a401321645530d3d66ebcccd6b8aea27ce21d6e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624804"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online 사서함에 대한 정크 메일 설정 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

조직의 Microsoft 365 사서함이 있는 Exchange Online 조직에서는 EOP(스팸 방지 Exchange Online Protection 제어합니다. 자세한 내용은 [EOP의 스팸 방지 보호를 참조하세요.](anti-spam-protection.md)

그러나 관리자가 다음의 개별 사서함에 대해 구성할 수 있는 특정 스팸 방지 설정도 Exchange Online.

- 정크 메일 규칙 사용 또는 사용 **안함:** 정크 메일 규칙은 모든 사서함에서 기본적으로 사용하도록 설정된 정크 메일 규칙이라는 숨겨진 받은 편지함 규칙입니다. 정크 메일 규칙은 다음 기능을 제어합니다.

  - **스팸** 방지 정책에 따라 정크 메일 폴더로 메시지 이동: 스팸 필터링 판정에 대해 정크 메일 폴더로 메시지 이동 작업을 사용하여 스팸 방지 정책을 구성하면 정크 메일 필터 규칙은 메시지가 사서함으로 배달된 후 메시지를 정크 메일 폴더로 이동합니다.  스팸 방지 정책의 스팸 필터링 판정에 대한 자세한 내용은 EOP에서 스팸 방지 정책 [구성을 참조하세요.](configure-your-spam-filter-policies.md) 마찬가지로 ZAP(제로 아워 자동 제거)에서 배달된 메시지가 스팸 또는 피싱으로 확인되는 경우 정크 메일 필터  규칙은 메시지를 정크 메일 폴더 스팸 필터링 판정 작업으로 이동하기 위해 메시지를 정크 메일 폴더로 이동합니다. ZAP에 대한 자세한 내용은 에서 [제로 아워 ZAP(자동 제거)를 Exchange Online.](zero-hour-auto-purge.md)

  - **사용자가** 웹용 Outlook 또는 Outlook 사용자에 대해 구성하는 정크 메일  설정: 수신 수신 목록 컬렉션은 각 사서함의 수신이 가능한 보낸 사람 목록, 수신 수신이 가능한 받는 사람 목록 및 수신이 차단된 보낸 사람 목록입니다. 이러한 목록의 항목은 정크 메일 규칙이 메시지를 받은 편지함 또는 정크 메일 폴더로 이동할지 여부를 지정합니다. 사용자는 웹용 사서함(이전의 웹 Outlook 또는 Outlook 사서함에 대해 safelist 컬렉션을 구성할 Outlook Web App. 관리자는 모든 사용자의 사서함에 대해 Safelist 컬렉션을 구성할 수 있습니다.

사서함에서 정크 메일 규칙을 사용하도록 설정하면 EOP는 스팸 필터링 판정 동작에 따라 메시지를 정크  메일 폴더로 이동하거나 사서함의 수신 차단된 보낸 사람 목록으로 메시지를 이동하고, 메시지가 사서함의 수신 가능 보낸 사람 목록에 따라 정크 메일 폴더로 배달되지 않도록 할 수 있습니다.

 사서함에서 정크 메일 규칙을 사용하지 않도록 설정하면 EOP에서 스팸 필터링 판정 동작에 따라 메시지를 정크 메일 폴더로 이동하거나 사서함의 수신할 수 있는 목록 모음으로 메시지를 이동할 수 없습니다. 

관리자는 PowerShell을 사용하여 Exchange Online 정크 메일 규칙의 상태를 사용하지 않도록 설정하고, 사용하도록 설정하고, 볼 수 있습니다. 관리자는 PowerShell을 사용하여 사서함의 수신 Exchange Online 컬렉션(수신- 보낸 사람 목록, 수신 금지된 받는 사람 목록 및 수신 금지된 보낸 사람 목록)을 구성할 수도 있습니다.

> [!NOTE]
> 사용자가 자신의 수신 - 보낸 사람 목록에 추가한 보낸 사람이 보낸 메시지는 EOP의 일부로 연결 필터링을 건너뜁습니다(SCL은 -1). 사용자가 보낸 사람 목록에 항목을 추가하지 못하게 Outlook 이 문서 의 2부에서 정크 메일 정보 설정에 설명된 Outlook 그룹 정책을 사용합니다. [](#about-junk-email-settings-in-outlook) 정책 필터링, 콘텐츠 필터링 및 Office 365 검사에 대한 Defender는 메시지에 계속 적용됩니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- PowerShell을 사용하여 Exchange Online 절차를 수행하면 됩니다. Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 Exchange Online 사용 권한을 할당해야 합니다. 특히 조직 관리, 받는 사람 관리 및 사용자 지정 메일 받는 사람 역할 그룹에 기본적으로 할당되는  Mail  **Recipients** 역할 또는 조직 관리 및 **지원** 센터 역할 그룹에 기본적으로 할당되는 사용자 옵션 역할이 필요합니다.  에서 역할 그룹에 사용자를 추가하려면 Exchange Online 에서 역할 [그룹 수정을 Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups) 기본 권한이 있는 사용자는 [PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)에 액세스할 수 있는 한 자신의 사서함에서 동일한 절차를 Exchange Online 있습니다.

- EOP로 온-프레미스 Exchange 사서함을 보호하는 하이브리드 환경에서는 EOP 스팸 필터링 평가 결과를 변환하여 정크 메일 규칙에 따라 메시지를 정크 메일 폴더로 이동하기 위해 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 EOP 구성하기](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)를 참조하세요.

- 공유 사서함의 수신 안전한 보낸 사람이 Azure AD 및 EOP에 기본적으로 동기화되지 않습니다.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>PowerShell Exchange Online 사용하여 사서함에서 정크 메일 규칙을 사용 또는 사용하지 않도록 설정

> [!NOTE]
> **Set-MailboxJunkEmailConfiguration** cmdlet을 사용하여 웹에서 Outlook(캐시된 Exchange 모드로) 또는 Outlook 사서함에서 정크 메일 규칙을 사용하지 않도록 설정할 수 있습니다. 사서함을 열지 않은 경우 다음 오류가 발생합니다. 대량 작업에 대해 이 오류를 표시하지 않는 경우 `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 명령에 추가할 수 있습니다.

사서함에서 정크 메일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

이 예에서는 Ori Epstein의 사서함에서 정크 메일 규칙을 사용하지 않도록 설정합니다.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

이 예에서는 조직의 모든 사용자 사서함에 대해 정크 메일 규칙을 사용하지 않도록 설정합니다.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

구문과 매개 변수에 대한 자세한 내용은 [Set-MailboxJunkEmailConfiguration을 참조하십시오.](/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - 사용자가 사서함을 연 적이 없는 경우 이전 명령을 실행할 때 오류가 발생할 수 있습니다. 대량 작업에 대해 이 오류를 표시하지 않습니다. `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 명령에 추가합니다.
>
> - 정크 메일 규칙을 사용하지 않도록 설정한 경우에도 Outlook 정크 메일 필터(구성 방법에 따라)는 메시지가 스팸인지 여부를 확인할 수 있으며, 자체 스팸 판정 및 사서함의 수신 금지 목록 모음에 따라 받은 편지함 또는 정크 메일 폴더로 메시지를 이동할 수 있습니다. 자세한 내용은 이 문서의 정크 메일 Outlook [섹션을](#about-junk-email-settings-in-outlook) 참조하세요.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

사서함에서 정크 메일 규칙을 성공적으로 사용하도록 설정하거나 사용하지 않도록 설정한 경우 다음 절차를 수행하십시오.

- 사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행하여 _\<MailboxIdentity\>_ **Enabled** 속성 값을 확인합니다.

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>PowerShell Exchange Online 사용하여 사서함에 대해 Safelist 컬렉션 구성

사서함의 수신 금지 목록 컬렉션에는 수신 금지된 보낸 사람 목록, 수신 금지된 받는 사람 목록 및 수신이 차단된 보낸 사람 목록이 포함됩니다. 기본적으로 사용자는 웹용 사서함 또는 웹의 사서함에 Outlook Outlook 수 있습니다. 관리자는 **Set-MailboxJunkEmailConfiguration** cmdlet에서 해당 매개 변수를 사용하여 사용자 사서함에 대해 safelist 컬렉션을 구성할 수 있습니다. 이러한 매개 변수에 대한 설명은 다음 표에 설명되어 있습니다.

****

|매개 변수의 Set-MailboxJunkEmailConfiguration|Outlook 설정|
|---|---|
|_BlockedSendersAndDomains_|**이러한 보낸 사람 또는 도메인에서 정크 메일 폴더로 전자 메일 이동**|
|_ContactsTrusted_|**연락처의 전자 메일 신뢰**|
|_TrustedListsOnly_|**수신 허용 - 보낸 사람 및 도메인 목록의 주소와 안전한 메일링 목록의 전자 메일만 신뢰**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**이러한 보낸 사람이 내 정크 메일 폴더로 전자 메일을 이동하지 않습니다.**|
|

<sup>\*</sup>**참고**:

- 이 Exchange Online 수신  허용 - 보낸 사람 목록 또는 _TrustedSendersAndDomains_ 매개 변수의 도메인 항목은 인식되지 않습니다. 따라서 전자 메일 주소만 사용합니다. 디렉터리 동기화가 있는 독립 실행형 EOP에서는 도메인 항목이 기본적으로 동기화되지 않지만 도메인에 대해 동기화를 사용하도록 설정할 수 있습니다. 자세한 내용은 [KB3019657을 참조하세요.](https://support.microsoft.com/help/3019657)

- **Set-MailboxJunkEmailConfiguration** cmdlet을 사용하여 수신 가능한 받는 사람 목록을 직접 수정할 수 _없습니다(TrustedRecipientsAndDomains_ 매개 변수가 작동하지 않습니다). 수신-보낸 사람 목록을 수정하면 해당 변경 내용이 수신 가능한 받는 사람 목록에 동기화됩니다.

사서함에 대해 safelist 컬렉션을 구성하기 위해 다음 구문을 사용 합니다.

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

여러 값을 입력하고 _BlockedSendersAndDomains_ 및 _TrustedSendersAndDomains_ 매개 변수에 대한 기존 항목을 덮어치기 위해 다음 구문을 `"<Value1>","<Value2>"...` 사용합니다. . 다른 기존 항목에 영향을 주지 않고 하나 이상의 값을 추가하거나 제거하려면 다음 구문을 사용합니다. `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

이 예에서는 Ori Epstein의 사서함에 있는 safelist 컬렉션에 대해 다음 설정을 구성합니다.

- 수신 shopping@fabrikam.com 목록에 값을 추가합니다.

- 수신- chris@fourthcoffee.com 목록 및 수신이 가능한 받는 사람 목록에서 값을 제거합니다.

- 연락처 폴더의 연락처를 신뢰할 수 있는 보낸 사람으로 처리하도록 구성합니다.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

이 예에서는 조직의 contoso.com 사서함의 수신 차단된 보낸 사람 목록에서 도메인 도메인을 제거합니다.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

구문과 매개 변수에 대한 자세한 내용은 [Set-MailboxJunkEmailConfiguration을 참조하십시오.](/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - 사용자가 사서함을 연 적이 없는 경우 이전 명령을 실행할 때 오류가 발생할 수 있습니다. 대량 작업에 대해 이 오류를 표시하지 않습니다. `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 명령에 추가합니다.
>
> - 사서함에서 정크 메일 규칙을 사용하지 않도록 설정한 경우에도 수신 수신 목록 컬렉션을 구성할 수 있으며 Outlook 정크 메일 필터는 메시지를 받은 편지함 또는 정크 메일 폴더로 이동할 수 있습니다. 자세한 내용은 이 문서의 정크 메일 Outlook [섹션을](#about-junk-email-settings-in-outlook) 참조하세요.
>
> - 정크 Outlook 필터에 추가 수신 목록 모음 설정이 있습니다(예: 수신- 보낸 사람 목록에 전자 메일 **자동** 추가). 자세한 내용은 정크 메일 필터를 사용하여 보게되는 메시지 [제어를 참조하세요.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

사서함에 대해 safelist 컬렉션을 성공적으로 구성한 경우 다음 절차를 수행하십시오.

- 사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행하여 속성 _\<MailboxIdentity\>_ 값을 검증합니다.

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  값 목록이 너무 길면 다음 구문을 사용합니다.

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>2016의 정크 메일 설정 Outlook

사용자 계정에서 사용할 수 있는 클라이언트 쪽 정크 메일 필터 설정을 사용하도록 설정, 비활성화 및 구성하려면 Outlook 정책을 사용합니다. 자세한 내용은 그룹 정책을 사용하여 [엔터프라이즈용 Microsoft 365 앱, Office 2019 및 Office 2016에 대한 관리 템플릿 파일(ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) 및 Office [](https://support.microsoft.com/help/2252421)사용자 지정 도구 및 수신-보낸 사람 목록과 같은 정크 메일 설정을 배포하는 방법을 참조하세요.

Outlook 정크 메일 필터가 기본값으로 설정되어  있는 경우 홈  정크 정크 메일 옵션에서 자동 필터링 안 하세요. Outlook 스팸으로 분류하지는 않지만 수신 금지 목록 컬렉션(수신이 가능한 보낸 사람 목록, 수신자 목록 및 수신 차단된 보낸 사람 목록)을 사용하여 메시지를 배달 후 정크 메일 폴더로 \>  \>  \> 이동합니다. 이러한 설정에 대한 자세한 내용은 정크 메일 필터 [개요를 참조하세요.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

정크 Outlook 필터를 낮음 또는  높음으로 설정하면 Outlook 정크 메일 필터는 자체 SmartScreen 필터 기술을 사용하여 스팸을 식별하고 정크 메일 폴더로 이동합니다.  이 스팸 분류는 EOP에 의해 결정된 SCL(스팸 지수)과는 별개입니다. 실제로 Outlook EOP에서 SCL을 무시하고(EOP가 스팸 필터링을 건너뛰기 위해 메시지를 표시하지 않은 경우) 자체 조건을 사용하여 메시지가 스팸인지 여부를 판단합니다. 물론 EOP와 EOP의 스팸 판정이 같을 Outlook 있습니다. 이러한 설정에 대한 자세한 내용은 정크 메일 필터에서 보호 수준 [변경을 참조하세요.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

> [!NOTE]
> 2016년 11월, Microsoft는 2016년 11월에 Microsoft와 팜에서 SmartScreen 필터에 대한 스팸 정의 Exchange Outlook. 기존 SmartScreen 스팸 정의는 적용된 것이지만 시간이 지날 때 효율성이 저하될 수 있습니다. 자세한 내용은 [Outlook 및 Exchange에서 SmartScreen 지원 삭제](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)를 참조하세요.

따라서 Outlook 정크 메일 필터는 사서함에서 정크 메일 규칙을 사용하지 않도록 설정한 경우에도 사서함의 수신 수신 목록 모음 및 자체 스팸 분류를 사용하여 메시지를 정크 메일 폴더로 이동할 수 있습니다.

Outlook Outlook 목록 모음을 지원하지 않습니다. safelist 컬렉션은 Exchange Online 사서함에 저장됩니다. 따라서 Outlook 목록 모음의 변경 내용은 Outlook 웹에 표시되고 그 반대의 경우도 마찬가지입니다.

## <a name="limits-for-junk-email-settings"></a>정크 메일 설정에 대한 제한

또한 사용자의 사서함에 저장된 수신 가능 목록 모음(수신 가능 보낸 사람 목록, 수신 가능 받는 사람 목록 및 수신이 차단된 보낸 사람 목록)도 EOP에 동기화됩니다. 디렉터리 동기화를 통해 Safelist 컬렉션이 Azure AD에 동기화됩니다.

- 사용자 사서함의 수신할 수 있는 목록 모음의 제한은 510 KB(모든 목록과 추가 정크 메일 필터 설정 포함)입니다. 사용자가 이 제한을 초과하면 다음과 같은 Outlook 오류가 발생합니다.

  > 서버에 정크 메일 목록을 추가할 수 없습니다. 서버에서 허용되는 크기를 넘습니다. 정크 메일 목록이 서버에서 허용되는 크기로 줄어들 때까지 서버의 정크 메일 필터를 사용할 수 없습니다.

  이 제한 및 변경 방법에 대한 자세한 내용은 [KB2669081을 참조하세요.](https://support.microsoft.com/help/2669081)

- EOP의 동기화된 Safelist 컬렉션에는 다음과 같은 동기화 제한이 있습니다.

  - 내 연락처의 전자 메일을 신뢰하는 경우 수신 가능 보낸 사람 목록,  수신 가능 받는 사람 목록 및 외부 연락처의 총 항목 1024개
  - 수신 차단된 보낸 사람 목록 및 차단된 도메인 목록의 총 항목 500개

  1024 항목 제한에 도달하면 다음과 같은 상황이 발생하게됩니다.

  - PowerShell 및 웹에서 Outlook 수락이 중지되지만 오류는 표시되지 않습니다.

    Outlook 510 KB의 제한에 도달할 때까지 1024개가 넘는 항목을 Outlook 수 있습니다. Outlook 사서함으로 배달하기 전에 EOP 필터가 메시지를 차단하지 않는 한 이러한 추가 항목을 사용할 수 있습니다(메일 흐름 규칙, 스푸핑 방지 등).

- 디렉터리 동기화를 통해 항목은 다음 순서대로 Azure AD에 동기화됩니다.

  1. 내 연락처의 전자 메일을 신뢰하는 경우 메일 **연락처를** 사용할 수 있습니다.
  2. 처음 1024개 항목에 대해 변경이 이행될 때마다 수신이 가능한 보낸 사람 목록과 수신 수신자 목록이 사전순으로 결합, 중복 제거 및 정렬됩니다.

  처음 1024개 항목이 사용하며 관련 정보는 메시지 헤더에 스탬프 처리됩니다.

  Azure AD에 동기화되지 않은 1024개가 넘는 항목은 웹에서 Outlook(웹에서 Outlook 아미라)에서 처리하며 메시지 헤더에 정보가 스탬프 처리되지 않습니다.

아래에서 볼 수 있겠지만, 내 연락처에서 전자 메일 신뢰 설정을 사용하도록 설정하면 동기화할 수 있는 수신-보낸 사람 및 안전한 받는 사람 수가 줄어듭됩니다.  이 문제가 우려되는 경우 그룹 정책을 사용하여 이 기능을 해제하는 것이 좋습니다.

- 파일 이름: outlk16.opax
- 정책 설정: **연락처의 전자 메일 신뢰**