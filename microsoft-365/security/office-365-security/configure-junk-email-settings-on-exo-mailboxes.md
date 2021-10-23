---
title: Exchange Online 사서함에 대한 정크 메일 설정 구성
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 사서함에서 정크 메일 설정을 구성하는 Exchange Online 있습니다. 이러한 설정 중 상당수는 사용자 또는 Outlook 사용할 웹용 Outlook.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d3a55b1f49430d3c2a61b0db44e3ce8f8a060093
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555491"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online 사서함에 대한 정크 메일 설정 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

조직의 Microsoft 365 사서함이 있는 Exchange Online 조직에서는 EOP(스팸 방지 Exchange Online Protection 제어합니다. 자세한 내용은 [EOP의 스팸 방지 보호를 참조하세요.](anti-spam-protection.md)

그러나 관리자가 다음의 개별 사서함에 대해 구성할 수 있는 특정 스팸 방지 설정도 Exchange Online.

> [!NOTE]
> 이제 EOP는 자체 메일 흐름 배달 에이전트를 사용하여 메시지를 정크 메일 규칙을 사용하는 대신 정크 메일 폴더로 라우팅합니다. **Set-MailboxJunkEmailConfiguration** cmdlet의 _Enabled_ 매개 변수는 메일 흐름에 더 이상 영향을 주지 않습니다. EOP는 스팸 방지 정책에 설정된 작업에 따라 메시지를 라우팅합니다. 사용자의 금고 보낸 사람 목록 및 수신 차단된 보낸 사람 목록은 평소처럼 계속 작동됩니다.

- **스팸** 방지 정책에 따라 정크 메일 폴더로 메시지 이동: 스팸 필터링 판정에 대해 정크 메일 폴더로 메시지 이동 작업을 사용하여 스팸 방지 정책을 구성하면 메시지가 사서함으로 배달된 후 메시지가 정크 메일 폴더로 이동됩니다.  스팸 방지 정책의 스팸 필터링 판정에 대한 자세한 내용은 EOP에서 스팸 방지 정책 [구성을 참조하세요.](configure-your-spam-filter-policies.md) 마찬가지로 ZAP(제로 아워 자동 제거)에서 배달된 메시지가 스팸 또는 피싱으로 확인되는 경우  메시지는 정크 메일 폴더로 메시지 이동을 위해 정크 메일 폴더 스팸 필터링 판정 작업의 정크 메일 폴더로 이동됩니다. ZAP에 대한 자세한 내용은 에서 [제로 아워 ZAP(자동 제거)를 Exchange Online.](zero-hour-auto-purge.md)

- **사용자가** Outlook 또는 웹용 Outlook에서 자신을 구성하는 정크 메일 설정:  수신 수신 목록 컬렉션은 각 사서함의 금고 보낸 사람 목록, 금고 받는 사람 목록 및 수신 차단된 보낸 사람 목록입니다. 이러한 목록의 항목에 따라 메시지가 받은 편지함 또는 정크 메일 폴더로 이동될지 여부가 결정됩니다. 사용자는 Outlook 또는 웹용 Outlook 사서함에 대해 safelist 컬렉션을 구성할 수 Outlook Web App. 관리자는 모든 사용자의 사서함에 대해 Safelist 컬렉션을 구성할 수 있습니다.

EOP는 스팸 필터링 판정 동작에 따라 메시지를 정크 메일  폴더로 이동하거나 사서함의 수신 차단된 보낸 사람 목록으로 메시지를 이동하고 사서함의 금고 보낸 사람 목록에 따라 메시지가 정크 메일 폴더로 배달되지 않도록 할 수 있습니다.

관리자는 Exchange Online PowerShell을 사용하여 사서함(수신 금고 목록, 금고 받는 사람 목록 및 수신 차단된 보낸 사람 목록)의 항목을 구성할 수 있습니다.

> [!NOTE]
> 사용자가 자신의 보낸 사람 목록에 추가한 금고 EOP의 일부로 콘텐츠 필터링을 건너뜁습니다(SCL은 -1). 사용자가 금고 보낸 사람 목록에 항목을 추가하지 못하게 Outlook 이 문서 의 2부에서 정크 메일 정보 설정에 설명된 Outlook 그룹 정책을 사용합니다. [](#about-junk-email-settings-in-outlook) 정책 필터링, 콘텐츠 필터링 및 Office 365 검사에 대한 Defender는 메시지에 계속 적용됩니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- PowerShell을 사용하여 Exchange Online 절차를 수행하면 됩니다. Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 Exchange Online 사용 권한을 할당해야 합니다. 특히 조직 관리, 받는 사람 관리 및 사용자 지정 메일 받는 사람 역할 그룹에 기본적으로 할당되는  Mail  **Recipients** 역할 또는 조직 관리 및 **지원** 센터 역할 그룹에 기본적으로 할당되는 사용자 옵션 역할이 필요합니다.  에서 역할 그룹에 사용자를 추가하려면 Exchange Online 에서 역할 [그룹 수정을 Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups) 기본 권한이 있는 사용자는 [PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)에 액세스할 수 있는 한 자신의 사서함에서 동일한 절차를 Exchange Online 있습니다.

- EOP가 전자 메일 사서함을 보호하는 하이브리드 환경에서는 Exchange 사서함에서 메일 흐름 규칙(전송 규칙)을 구성해야 Exchange. 이러한 메일 흐름 규칙은 사서함의 정크 메일 규칙이 메시지를 정크 메일 폴더로 이동할 수 있도록 EOP 스팸 필터링 판정을 변환합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 EOP 구성하기](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)를 참조하세요.

- 금고 사서함의 보낸 사람이 Azure AD 및 EOP에 기본적으로 동기화되지 않습니다.

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>PowerShell Exchange Online 사용하여 사서함에 대해 Safelist 컬렉션 구성

사서함의 수신 금지 목록 컬렉션에는 금고 목록, 금고 받는 사람 목록 및 수신 차단된 보낸 사람 목록이 포함됩니다. 기본적으로 사용자는 사서함의 사서함에 대해 safelist 컬렉션을 구성할 수 Outlook 웹용 Outlook. 관리자는 **Set-MailboxJunkEmailConfiguration** cmdlet에서 해당 매개 변수를 사용하여 사용자 사서함에 대해 safelist 컬렉션을 구성할 수 있습니다. 이러한 매개 변수에 대한 설명은 다음 표에 설명되어 있습니다.

<br>

****

|매개 변수의 Set-MailboxJunkEmailConfiguration|웹용 Outlook 설정|
|---|---|
|_BlockedSendersAndDomains_|**이러한 보낸 사람 또는 도메인에서 정크 메일 폴더로 전자 메일 이동**|
|_ContactsTrusted_|**연락처의 전자 메일 신뢰**|
|_TrustedListsOnly_|**보낸 사람 및 도메인 목록 및 금고 메일 금고 전자 메일만 신뢰**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**이러한 보낸 사람이 내 정크 메일 폴더로 전자 메일을 이동하지 않습니다.**|
|

<sup>\*</sup>**참고**:

- 이 Exchange Online 보낸  사람 금고 _TrustedSendersAndDomains_ 매개 변수의 도메인 항목은 인식되지 않습니다. 따라서 전자 메일 주소만 사용합니다. 디렉터리 동기화가 있는 독립 실행형 EOP에서는 도메인 항목이 기본적으로 동기화되지 않지만 도메인에 대해 동기화를 사용하도록 설정할 수 있습니다. 자세한 내용은 [KB3019657을 참조하세요.](https://support.microsoft.com/help/3019657)
- **Set-MailboxJunkEmailConfiguration** cmdlet을 사용하여 금고 받는 사람 목록을 직접 수정할 수 _없습니다(TrustedRecipientsAndDomains_ 매개 변수가 작동하지 않습니다). 보낸 사람 금고 수정하면 해당 변경 내용이 받는 사람 금고 동기화됩니다.

사서함에 대해 safelist 컬렉션을 구성하기 위해 다음 구문을 사용 합니다.

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

여러 값을 입력하고 _BlockedSendersAndDomains_ 및 _TrustedSendersAndDomains_ 매개 변수에 대한 기존 항목을 덮어치기 위해 다음 구문을 `"<Value1>","<Value2>"...` 사용합니다. . 다른 기존 항목에 영향을 주지 않고 하나 이상의 값을 추가하거나 제거하려면 다음 구문을 사용합니다. `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

이 예에서는 Ori Epstein의 사서함에 있는 safelist 컬렉션에 대해 다음 설정을 구성합니다.

- 수신 shopping@fabrikam.com 목록에 값을 추가합니다.
- 보낸 사람 chris@fourthcoffee.com 금고 받는 사람 목록에서 금고 제거합니다.
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
> - 정크 Outlook 필터에 추가 수신 목록 모음 설정이 **있습니다(예:** 전자 메일을 보낸 사람 목록에 자동으로 금고). 자세한 내용은 정크 메일 필터를 사용하여 보게되는 메시지 [제어를 참조하세요.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)

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

사용자 계정에서 사용할 수 있는 클라이언트 쪽 정크 메일 필터 설정을 사용하도록 설정, 비활성화 및 구성하려면 Outlook 정책을 사용합니다. 자세한 내용은 관리 템플릿 파일(ADMX/ADML) 및 Office [Customization Tool for 엔터프라이즈용 Microsoft 365 앱, Office 2019 및 Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) [](https://support.microsoft.com/help/2252421)및 그룹 정책을 사용하여 금고 보낸 사람 목록과 같은 정크 메일 설정을 배포하는 방법을 참조하세요.

Outlook 정크 메일 필터가 기본값으로 설정된  경우 홈 정크 메일 옵션에서 자동 필터링 안  \>  \>  \> 하세요. Outlook는 메시지를 스팸으로 분류하지 않지만 수신자 목록, 금고 받는 사람 목록 및 수신 수신 차단 목록)을 사용하여 메시지를 정크 메일 접기로 이동합니다 금고. r 배달 후 이러한 설정에 대한 자세한 내용은 정크 메일 필터 [개요를 참조하세요.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

정크 Outlook 필터를 낮음 또는  높음으로 설정하면 Outlook 정크 메일 필터는 자체 SmartScreen 필터 기술을 사용하여 스팸을 식별하고 정크 메일 폴더로 이동합니다.  이 스팸 분류는 EOP에 의해 결정된 SCL(스팸 지수)과는 별개입니다. 실제로 Outlook EOP에서 SCL을 무시하고(EOP가 스팸 필터링을 건너뛰기 위해 메시지를 표시하지 않은 경우) 자체 조건을 사용하여 메시지가 스팸인지 여부를 판단합니다. 물론 EOP와 EOP의 스팸 판정이 같을 Outlook 있습니다. 이러한 설정에 대한 자세한 내용은 정크 메일 필터에서 보호 수준 [변경을 참조하세요.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

> [!NOTE]
> 2016년 11월, Microsoft는 2016년 11월에 Microsoft와 팜에서 SmartScreen 필터에 대한 스팸 정의 Exchange Outlook. 기존 SmartScreen 스팸 정의는 적용된 것이지만 시간이 지날 때 효율성이 저하될 수 있습니다. 자세한 내용은 [Outlook 및 Exchange에서 SmartScreen 지원 삭제](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)를 참조하세요.

따라서 Outlook 정크 메일 필터는 사서함의 수신 금지 목록 모음 및 자체 스팸 분류를 사용하여 메시지를 정크 메일 폴더로 이동할 수 있습니다.

Outlook 웹용 Outlook 모두 safelist 컬렉션을 지원하지 않습니다. safelist 컬렉션은 Exchange Online 저장되어 있으므로 Outlook 컬렉션의 변경 내용은 웹용 Outlook 표시되고 그 반대의 경우도 마찬가지입니다.

## <a name="limits-for-junk-email-settings"></a>정크 메일 설정에 대한 제한

사용자 사서함에 저장된 수신 금고 목록, 금고 받는 사람 목록 및 수신 금지된 보낸 사람 목록)도 EOP에 동기화됩니다. 디렉터리 동기화를 통해 Safelist 컬렉션이 Azure AD에 동기화됩니다.

- 사용자 사서함의 수신할 수 있는 목록 모음의 제한은 510 KB(모든 목록과 추가 정크 메일 필터 설정 포함)입니다. 사용자가 이 제한을 초과하면 다음과 같은 Outlook 오류가 발생합니다.

  > 서버에 정크 메일 목록을 추가할 수 없습니다. 서버에서 허용되는 크기를 넘습니다. 정크 메일 목록이 서버에서 허용되는 크기로 줄어들 때까지 서버의 정크 메일 필터를 사용할 수 없습니다.

  이 제한 및 변경 방법에 대한 자세한 내용은 [KB2669081을 참조하세요.](https://support.microsoft.com/help/2669081)

- EOP의 동기화된 Safelist 컬렉션에는 다음과 같은 동기화 제한이 있습니다.
  - 연락처의 전자 메일 신뢰가 사용하도록 설정된 경우 금고 보낸 사람 목록, 금고 받는 사람  목록 및 외부 연락처의 총 항목 1024개
  - 수신 차단된 보낸 사람 목록 및 차단된 도메인 목록의 총 항목 500개

  1024 항목 제한에 도달하면 다음과 같은 상황이 발생하게됩니다.

  - PowerShell 및 웹용 Outlook 수락이 중지되지만 오류가 표시되지 않습니다.

    Outlook 510 KB의 제한에 도달할 때까지 1024개가 넘는 항목을 Outlook 수 있습니다. Outlook 사서함으로 배달하기 전에 EOP 필터가 메시지를 차단하지 않는 한 이러한 추가 항목을 사용할 수 있습니다(메일 흐름 규칙, 스푸핑 방지 등).

- 디렉터리 동기화를 통해 항목은 다음 순서대로 Azure AD에 동기화됩니다.
  1. 내 연락처의 전자 메일을 신뢰하는 경우 메일 **연락처를** 사용할 수 있습니다.
  2. 금고 목록과 금고 받는 사람 목록은 처음 1024개 항목에 대해 변경될 때마다 사전순으로 결합, 중복 제거 및 정렬됩니다.

  처음 1024개 항목이 사용하며 관련 정보는 메시지 헤더에 스탬프 처리됩니다.

  Azure AD에 동기화되지 않은 1024개가 넘는 항목은 Outlook(웹용 Outlook 아바타)에서 처리하며 메시지 헤더에 정보가 스탬프 처리되지 않습니다.

보시다시마 내  연락처에서 전자 메일 신뢰 설정을 사용하도록 설정하면 동기화할 수 있는 금고 받는 사람 및 금고 수가 줄어듭됩니다. 이 문제가 우려되는 경우 그룹 정책을 사용하여 이 기능을 해제하는 것이 좋습니다.

- 파일 이름: outlk16.opax
- 정책 설정: **연락처의 전자 메일 신뢰**
