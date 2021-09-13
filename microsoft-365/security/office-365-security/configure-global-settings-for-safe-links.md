---
title: Defender for 금고 링크 설정에 대한 전역 Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft Defender for 금고 링크에 대한 전역 설정("다음 URL 차단" 목록 및 Office 365 앱 보호)을 보고 구성하는 방법을 Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 099ff894cc350ecedbd7743ab348aede540874ab
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219822"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender에서 금고 링크에 대한 전역 설정 Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 이 문서는 [Office 365용 Microsoft Defender](defender-for-office-365.md)가 있는 비즈니스 고객을 대상으로 합니다. 사용자 계정의 Safelinks에 대한 정보를 찾는 가정용 사용자인 Outlook [고급 Outlook.com 보안 을 참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

금고 링크는 메일 흐름에서 [인바운드](defender-for-office-365.md) 전자 Office 365 URL 검색을 제공하는 Microsoft Defender for Office 365 기능으로, 전자 메일 메시지 및 기타 위치에서 URL 및 링크 확인을 클릭하는 시간을 제공합니다. 자세한 내용은 microsoft [Defender에서](safe-links.md)금고 링크를 참조하세요Office 365.

링크 정책에서 대부분의 금고 링크 금고 구성합니다. 자세한 내용은 [Set up 금고 Links policies in Microsoft Defender for Office 365.](set-up-safe-links-policies.md)

그러나 금고 링크는 링크 정책 자체 외부에서 구성하는 금고 전역 설정도 사용합니다.

- 다음 **URL 차단 목록** 이 설정은 모든 활성 링크 정책에 포함된 모든 금고 적용됩니다. 자세한 내용은 링크에 대한 "다음 URL [차단" 금고 참조하세요.](safe-links.md#block-the-following-urls-list-for-safe-links)
- 금고 앱에 대한 Office 365 보호합니다. 이러한 설정은 사용자가 활성 링크 정책에 포함되어 있는지 여부에 관계없이 Office 365 대한 Defender 사용이 허가된 조직의 금고 적용됩니다. 자세한 내용은 금고 앱에 대한 [링크 Office 365 참조하세요.](safe-links.md#safe-links-settings-for-office-365-apps)

Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online PowerShell)에서 전역 Exchange Online 링크 설정을 구성할 수 있습니다. Exchange Online 사서함이 있는 적격 Microsoft 365 조직의 경우, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell은 Office 365 추가 기능 구독용 Microsoft Defender를 사용하여 구성할 수 있습니다. 금고

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 기본 제공 또는 기본 금고 링크 정책이 있으므로 다음 URL 차단 목록이 금고 링크 정책을 하나  이상 만들어야 합니다. 자세한 내용은 [Set up 금고 Links policies in Microsoft Defender for Office 365.](set-up-safe-links-policies.md)

- <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다. 링크 페이지로 직접 금고 **를** <https://security.microsoft.com/safelinksv2> 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.
  - 금고 링크에 대한 전역 설정을 구성하려면 조직 관리 또는  보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.
  - 금고 링크에 대한 전역 설정에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 그룹 또는 보안 읽기 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹도 기능에 대한 읽기 전용 권한을 부여합니다.

- 링크의 전역 설정에 대한 권장 금고 링크 금고 [참조하세요.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

- 새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.

- [새로운 기능은 계속해서](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Microsoft Defender for Office 365. 새 기능이 추가될 때 기존 링크 정책에 대한 조정을 금고 있습니다.

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a>웹 사이트 포털에서 "다음 URL 차단" Microsoft 365 Defender 구성

다음 **URL 차단 목록은** 지원되는 앱에서 링크 검색을 금고 차단해야 하는 링크를 식별합니다. 자세한 내용은 링크에 대한 "다음 URL [차단" 금고 참조하세요.](safe-links.md#block-the-following-urls-list-for-safe-links)

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 \>  \> **금고** \> **링크로** 이동하세요. 

2. 링크 **금고 페이지에서** 전역 설정을 **클릭합니다.** 조직의 **금고** 링크 정책 플라이아웃이 나타나면 다음 URL 차단 상자로 **이동하세요.**

3. "다음 URL 차단" 목록에 대한 항목 구문에 설명된 하나 이상의 항목을 [구성합니다.](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   작업을 마친 후 **저장** 을 클릭합니다.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>PowerShell에서 "다음 URL 차단" 목록 구성

항목 구문에 대한 자세한 내용은 ["다음 URL 차단" 목록의 항목 구문을 참조하세요.](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

**Get-AtpPolicyForO365** cmdlet을 사용하여 _BlockURLs_ 속성의 기존 항목을 볼 수 있습니다.

- 기존 항목을 대체할 값을 추가하기 위해 PowerShell 또는 PowerShell에서 Exchange Online 구문을 Exchange Online Protection 합니다.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  다음은 목록에 다음 항목을 추가하는 예제입니다.

  - 도메인, 하위 도메인 및 도메인에 대한 경로를 fabrikam.com.
  - 하위 도메인 조사를 차단하지만 하위 도메인의 상위 도메인 또는 기타 하위 도메인은 tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- 다른 기존 항목에 영향을 주지 않고 값을 추가하거나 제거하려면 다음 구문을 사용합니다.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  이 예제에서는 새 adatum.com 추가하고 새 항목의 fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a>금고 포털에서 Office 365 앱에 대한 Microsoft 365 Defender 링크 보호 구성

금고 앱에 대한 Office 365 보호는 지원되는 데스크톱, 모바일 및 Office 문서에 적용됩니다. 자세한 내용은 금고 앱에 대한 [링크 Office 365 참조하세요.](safe-links.md#safe-links-settings-for-office-365-apps)

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 \>  \> **금고** \> **링크로** 이동하세요. 

2. 링크 **금고 페이지에서** 전역 설정을 **클릭합니다.** 조직의 **금고** 링크 정책 플라이아웃이 나타나면 지원되는 설정 앱 섹션의 콘텐츠에 적용되는 다음 설정을 Office 365 **구성합니다.**

   - **금고 앱에서** Office 365 링크 사용: 지원되는 금고 Office 365 앱에 대해 금고 링크를 사용하도록 설정하려면 토글이 오른쪽에 있는지 확인: 토글합니다. ![ ](../../media/scc-toggle-on.png) .

   - **사용자가 Office 365** 앱에서 보호된 링크를 클릭하는 경우 추적하지 않습니다. 토글을 왼쪽으로 이동하여 지원되는 Office 365 앱의 차단된 URL과 관련된 사용자 클릭을 추적합니다. 토글 ![ 끄기. ](../../media/scc-toggle-off.png)

   - 사용자가 Office 365 앱에서 원래 URL을 클릭할 수 있도록 합니다. 사용자가 지원되는 Office 365 앱에서 원래 차단된 **URL을** 클릭하지 못하게 차단하려면 토글이 오른쪽에 있는지 ![ 확인합니다. ](../../media/scc-toggle-on.png)

   작업을 마친 후 **저장** 을 클릭합니다.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>PowerShell에서 금고 앱에 대한 Office 365 링크 보호 구성

PowerShell을 사용하여 금고 앱에 대한 Office 365 링크 보호를 구성하는 경우 powerShell 또는 Exchange Online PowerShell에서 Exchange Online Protection 구문을 사용하세요.

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

이 예제에서는 앱의 금고 링크 보호에 대해 Office 365 구성합니다.

- 금고 앱에 Office 365 링크가 켜져 _있습니다(EnableSafeLinksForO365Clients_ 매개 변수를 사용하지 않습니다. 기본값은 $true).
- 지원되는 앱의 차단된 URL과 관련된 사용자 Office 365 추적됩니다.
- 사용자가 지원되는 Office 365 앱에서 원래 차단된 URL을 클릭할 수 _없습니다(AllowClickThrough_ 매개 변수를 사용하지 않습니다. 기본값은 $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](/powershell/module/exchange/set-atppolicyforo365)

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

금고 링크에 대한 전역 설정(다음 URL 차단 목록 및  Office 365 앱 보호 설정)을 성공적으로 구성한지 확인하려면 다음 단계를 수행합니다.

- Microsoft 365 Defender 포털의 정책 섹션에서 전자 **메일 &** 공동 작업 정책 & 규칙 위협 정책 금고 링크로 이동하여 전역 설정을 클릭하고 플라이아웃에 나타나는 설정을 \>  \>  \>   \> 확인합니다. 

- PowerShell Exchange Online PowerShell을 Exchange Online Protection 다음 명령을 실행하고 설정을 확인합니다.

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  구문과 매개 변수에 대한 자세한 내용은 [Get-AtpPolicyForO365를 참조하십시오.](/powershell/module/exchange/get-atppolicyforo365)
