---
title: eDiscovery에 대한 사용 권한 필터링 구성
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: 검색 권한 필터링을 사용하여 eDiscovery 관리자가 조직의 사서함 및 사이트의 하위 집합만 검색할 수 있도록 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 785fd1237cab66a898307724c5142a6baf4d6120
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200428"
---
# <a name="configure-permissions-filtering-for-ediscovery"></a>eDiscovery에 대한 사용 권한 필터링 구성

검색 권한 필터링을 사용하여 eDiscovery 관리자가 조직의 사서함 및 사이트의 하위 집합만 검색할 수 있도록 할 수 있습니다. 또한 권한 필터링을 사용하여 동일한 eDiscovery 관리자가 특정 검색 조건을 충족하는 사서함 또는 사이트 콘텐츠만 검색하도록 할 수도 있습니다. 예를 들어 검색 관리자가 특정 위치나 부서의 사용자 사서함만 검색하도록 할 수 있습니다. 이 작업을 위해 지원되는 받는 사람 필터를 사용하여 특정 사용자 또는 사용자 그룹이 검색할 수 있는 사서함을 제한하는 필터를 만들 수 있습니다. 사용자가 검색할 수 있는 사서함 콘텐츠를 지정하는 필터를 만들 수도 있습니다. 이 작업은 검색 가능한 메시지 속성을 사용하는 필터를 만들어 수행합니다. 마찬가지로 eDiscovery 관리자가 조직의 특정 사이트만 SharePoint 수 있습니다. 이 작업은 검색할 수 있는 사이트를 제한하는 필터를 만들어 수행합니다. 검색할 수 있는 사이트 콘텐츠를 지정하는 필터를 만들 수도 있습니다. 이 작업은 검색 가능한 사이트 속성을 사용하는 필터를 만들어 수행합니다.

검색 권한 필터는 콘텐츠 검색, Core eDiscovery 및 콘텐츠 검색을 사용하여 콘텐츠를 검색할 Advanced eDiscovery Microsoft 365 규정 준수 센터. 검색 권한 필터를 특정 사용자에게 적용하면 해당 사용자는 다음과 같은 검색 관련 작업을 수행할 수 있습니다.

- 콘텐츠 검색

- 검색 결과 미리 보기

- 검색 결과 내보내기

- 검색에서 반환된 항목 제거

검색 권한 필터링을 사용하여 특정 eDiscovery 관리자가 검색할 수 있는 사용자 콘텐츠 위치(예: 사서함, SharePoint 사이트 및 OneDrive 계정)를 제어하는 조직 내에서 논리적 경계(규정 준수 경계라고도함)를 만들 수도 있습니다. 자세한 내용은 [eDiscovery](set-up-compliance-boundaries.md)조사에 대한 준수 경계 설정 을 참조하세요.
  
Security & Compliance PowerShell의 다음 네 가지 cmdlet을 사용하여 검색 권한 필터를 구성하고 관리할 수 있습니다.
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>사용 권한 필터링 구성 요구 사항

- 준수 보안 필터 cmdlet을 실행하기 위해 조직의 Organization Management 역할 그룹의 구성원이 Microsoft 365 규정 준수 센터. 자세한 내용은 [보안 및 준수 센터의 사용 권한](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)을 참조하세요.

- 준수 보안 필터 cmdlet을 사용 Exchange Online 및 보안 & PowerShell에 연결해야 합니다. 이러한 cmdlet은 사서함 속성에 액세스해야 하기 때문에 PowerShell에 연결해야 Exchange Online 필요합니다. 다음 섹션의 단계를 참조하세요.

- 검색 권한 필터에 대한 자세한 내용은 [More information](#more-information) 섹션을 참조하세요.

- 검색 권한 필터링은 비활성 사서함에 적용할 수 있습니다. 즉, 사서함 및 사서함 콘텐츠 필터링을 사용하여 비활성 사서함을 검색할 수 있는 사용자만 제한할 수 있습니다. 사용 [권한](#more-information) 필터링 및 비활성 사서함에 대한 자세한 내용은 추가 정보 섹션을 참조하세요.

- 검색 권한 필터링은 검색에서 공용 폴더를 검색할 수 있는 Exchange.

- 조직에서 만들 수 있는 검색 권한 필터의 수에는 제한이 없습니다. 그러나 검색 쿼리의 조건은 최대 100개입니다. 이 경우 조건은 **부울** 연산자(예: AND, **OR** 및 NEAR)에 의해 쿼리에 연결된 것으로 **정의됩니다.** 조건 수에 대한 제한에는 검색 쿼리 자체와 검색을 실행한 사용자에게 적용되는 모든 검색 권한 필터가 포함됩니다. 따라서 검색 권한 필터가 수록(특히 동일한 사용자 또는 사용자 그룹에 이러한 필터가 적용되는 경우) 검색에 대한 최대 조건 수를 초과할 가능성이 더 낫습니다. 조직에서 조건 제한에 도달하지 못하게 방지하려면 비즈니스 요구 사항을 충족하기 위해 조직의 검색 권한 필터 수를 최대한 적게 유지하세요. 자세한 내용은 [eDiscovery](set-up-compliance-boundaries.md#frequently-asked-questions)조사에 대한 준수 경계 설정 을 참조하세요.

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>커넥트 세션에서 Exchange Online 및 보안 & 준수 센터 PowerShell을 사용할 수 있습니다.

이 섹션의 스크립트를 성공적으로 실행하려면 먼저 PowerShell V2 모듈을 다운로드하여 Exchange Online 설치해야 합니다. 자세한 내용은 [PowerShell V2 Exchange Online 정보를 참조하세요.](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

1. 파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 **.ps1.** 예를 들어 이라는 파일에 저장할 수 **ConnectEXO-SCC.ps1.**

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 로컬 컴퓨터에서 Windows PowerShell 를 열고 이전 단계에서 만든 스크립트가 있는 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

작동 여부는 어떻게 확인하나요? 스크립트를 실행하고 나면 Exchange Online 및 Security & PowerShell의 cmdlet을 로컬 Windows PowerShell 세션으로 가져오게 됩니다. 오류가 발생하지 않으면 정상적으로 연결된 것입니다. 빠른 테스트는 보안 및 보안 Exchange Online PowerShell & 실행하는 것입니다. 예를 들어, 및 **Get-Mailbox** 및 **Get-ComplianceSearch를** 실행할 수 있습니다.

PowerShell 연결 오류 문제 해결에 대한 자세한 내용은 다음을 참조합니다.

- [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [보안 및 준수 센터 PowerShell에 연결하기](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

**New-ComplianceSecurityFilter는** 검색 권한 필터를 만드는 데 사용됩니다. 이 cmdlet의 기본 구문은 다음과 같습니다.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <user or role group> -Filters <filter>
```

다음 섹션에서는 이 cmdlet의 매개 변수에 대해 설명합니다. 검색 권한 필터를 만들 때 모든 매개 변수가 필요합니다.

### <a name="filtername"></a>*FilterName*

_FilterName_ 매개 변수는 사용 권한 필터의 이름을 지정합니다. 이 이름은 **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** 및 **Remove-ComplianceSecurityFilter** cmdlet을 사용할 때 필터를 식별하는 데 사용됩니다.

### <a name="filters"></a>*필터*

_Filters 매개_ 변수는 준수 보안 필터에 대한 검색 조건을 지정합니다. 다음과 같은 세 가지 유형의 필터를 만들 수 있습니다.  

- **사서함 또는 OneDrive 필터링:** 이 유형의 필터는 할당된 사용자(Users 매개 OneDrive 지정)가  검색할 수 있는 사서함 및 계정 계정을 지정합니다. 이러한 유형의 필터는 사용자가 *검색할* 수 있는 콘텐츠 위치를 정의하기 때문에 콘텐츠 위치 필터라고 합니다. 이 유형의 필터에 대한 구문은  _mailboxPropertyName에 Mailbox_ MailboxPropertyName입니다._ 여기서 _MailboxPropertyName은_ 검색할 수 있는 사서함 및 OneDrive 계정의 범위를 지정하는 사서함 속성을 지정합니다. 예를 들어 사서함 필터를 사용하면 이 필터가 할당된 사용자가 `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` CustomAttribute10 속성에서 "OttawaUsers" OneDrive 사서함 및 사서함 계정만 검색할 수 있습니다.

  지원되는 필터링 가능한 받는 사람 속성은  _MailboxPropertyName 속성에 사용할 수_ 있습니다. 검색 가능한 속성 목록은 [-RecipientFilter](/powershell/exchange/recipientfilter-properties)매개 변수의 필터링 가능한 속성을 참조하세요.

- **사서함 콘텐츠 필터링:** 이 유형의 필터는 검색할 수 있는 콘텐츠에 적용됩니다. 이 유형의 필터는 할당된 사용자가 *검색할* 수 있는 사서함 콘텐츠를 지정하기 때문에 콘텐츠 필터라고 합니다. 이 유형의 필터에 대한 구문은 **MailboxContent_** _SearchablePropertyName: value입니다._ 여기서  _SearchablePropertyName은_ 검색에서 지정할 수 있는 KQL(Keyword Query Language) 속성을 지정합니다. 예를 들어 사서함 콘텐츠 필터를 사용하면 이 필터가 할당된 사용자가 해당 도메인의 받는 사람에게 보낸 메시지만 contoso.com  `MailboxContent_recipients:contoso.com` 있습니다. 검색 가능한 메시지 속성 목록은 [eDiscovery에 대한 키워드 쿼리](keyword-queries-and-search-conditions.md#searchable-email-properties)및 검색 조건을 참조하세요. 

  > [!IMPORTANT]
  > 단일 검색 필터에는 사서함 필터와 사서함 콘텐츠 필터를 포함할 수 없습니다. 이러한 필터를 단일 필터에 결합하기 위해 필터 목록 을 [사용해야 합니다.](#using-a-filters-list-to-combine-filter-types)  그러나 필터에는 같은 형식의 보다 복잡한 쿼리가 포함될 수 있습니다. 예를 들어 `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`

- **사이트 및 사이트 콘텐츠 필터링:** 할당된 사용자가 검색할 수 있는 SharePoint 또는 사이트 콘텐츠를 지정하는 데 사용할 수 있는 OneDrive 및 사용자 관련 필터에는 두 가지가 있습니다.

  - **Site_**_SearchableSiteProperty_
  
  - **SiteContent_**_SearchableSiteProperty_
  
   이러한 두 필터는 교환이 가능합니다. 예를 들어 `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors'"` 동일한  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors'"` 결과를 반환합니다. 검색 가능한 사이트 속성 목록은 [eDiscovery에](keyword-queries-and-search-conditions.md#searchable-site-properties) 대한 키워드 쿼리 및 검색 조건을 참조하세요. 자세한 내용은 overview [of crawled and managed properties in SharePoint.](/SharePoint/technical-reference/crawled-and-managed-properties-overview) 쿼리 가능 열에  **예로** 표시된 속성을 사용하여 사이트 또는 사이트 콘텐츠 필터를 만들 수 있습니다.  

  > [!IMPORTANT]
  > 지원되는 속성 중 하나를 사용하여 사이트 필터를 설정하는 것은 필터의 사이트 속성이 해당 사이트의 모든 문서로 전파되는 것은 아니며, 즉, 사용자는 사이트 필터가 작동하고 올바른 콘텐츠를 캡처하기 위해 해당 사이트의 문서와 연결된 특정 속성 필드를 채우는 작업을 계속 담당합니다. 예를 들어 사용자에게 보안 필터 "Site_RefineableString00 -eq 'abc'"가 적용되어 있는 경우 사용자는 키워드 쿼리 "xyz"를 사용하여 검색을 실행합니다. 보안 필터가 쿼리에 추가되고 실행 중인 실제 쿼리는 "xyz **AND RefineableString0:'abc'**"가 됩니다. 사용자는 사이트의 문서에 실제로 RefineableString00 필드의 값이 "abc"로 설정되어 있도록 합니다. 그렇지 않은 경우 검색 쿼리는 결과를 반환하지 않습니다.

검색 권한 필터에 대해 *Filters* 매개 변수를 구성할 때 다음 사항을 고려하십시오.

- 사서함과 달리 사이트 필터가 위치 필터처럼 보임에도 사이트의 콘텐츠 위치 필터는 없습니다.  경로와 SharePoint OneDrive 사이트 관련 속성은 문서에 직접 스탬프가 지정되어 있기 때문에 콘텐츠 필터(Site_ 및 SiteContent_ 필터를 교환할 수 있는 이유)입니다.    왜 그 이유는 무엇입니까? 이는 사용자들이 설계한 SharePoint 결과입니다. 이 SharePoint 사서함이 있는 경우처럼 속성이 있는 "사이트 개체"Exchange 없습니다. 따라서 *Path 속성은* 문서에 스탬프가 지정되어 있으며 문서가 있는 사이트의 URL을 포함하게 됩니다. 따라서 사이트 *필터는* 콘텐츠 위치 필터가 아닌 콘텐츠 필터로 간주됩니다.

- 사용자가 특정 서비스의 콘텐츠 위치를 검색하지 못하도록 명시적으로 차단하려면 검색 권한 필터를 만들어야 합니다(예: 사용자가 모든 Exchange 사이트 또는 모든 SharePoint 검색하지 못하도록 차단). 즉, 사용자가 조직의 모든 SharePoint 검색할 수 있도록 하는 검색 권한 필터를 만들면 해당 사용자가 사서함을 검색할 수 없습니다. 예를 들어 SharePoint 관리자가 사이트만 SharePoint 수 있도록 허용하려면 사서함을 검색할 수 없는 필터를 만들어야 합니다. 마찬가지로 Exchange 관리자만 사서함을 검색할 수 있도록 허용하려면 사이트 검색을 차단하는 필터를 만들어야 합니다.

### <a name="users"></a>*사용자*

Users  _매개_ 변수는 이 필터를 검색에 적용한 사용자를 지정합니다. 별칭 또는 기본 SMTP 주소로 사용자를 식별합니다. 여러 값을 쉼표로 구분하여 지정하거나 **All** 값을 사용하여 모든 사용자에게 필터를 할당할 수 있습니다.

Users 매개 변수를 사용하여 역할 Microsoft 365 규정 준수 센터 있습니다.  이렇게 하면 사용자 지정 역할 그룹을 만든 다음 해당 역할 그룹에 검색 권한 필터를 할당할 수 있습니다. 예를 들어 다국적 기업의 미국 자회사에 대한 eDiscovery 관리자용 사용자 지정 역할 그룹이 있는 경우를 예로 들어 보겠습니다. _Users_ 매개 변수를 사용하여 역할 그룹의 Name 속성을 사용하여 이 역할 그룹을 지정한 다음 _Filter_ 매개 변수를 사용하여 미국 내 사서함만 검색할 수 있습니다. 이 매개 변수를 사용하여 메일 그룹을 지정할 수 없습니다.|

### <a name="using-a-filters-list-to-combine-filter-types"></a>필터 목록을 사용하여 필터 유형 결합

필터 *목록은* 사서함 필터와 사이트 필터를 각 콤보로 구분하여 포함하는 필터입니다. 이 콤보는 **OR 연산자로도** 기능합니다. 다양한 유형의 필터를 결합할 수 있는 유일한 방법은 필터 목록을 사용하는 것입니다. 다음 예에서는 콤보가 사서함 및  사이트 필터를 **구분합니다.**

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors'"
```

필터 목록이 포함된 필터가 검색을 실행하는 동안 처리되면 필터 목록에서 두 개의 검색 권한 필터가 만들어지며 각 필터에 대해 각 필터에 대해 각 필터가 각 필터에 대해 하나씩 만들어집니다. 따라서 이전 예에서는 사서함 검색 권한 필터와 사이트 검색 권한 필터가 하나씩 만들어집니다. 이러한 필터는 **OR 연산자로 연결됩니다.**

필터 목록을 사용하는 대신 별도의 두 개의 검색 권한 필터를 만들 수 있습니다. 따라서 이전 예에서는 사서함 특성에 대해 필터를 하나 만들고 사이트 특성에 대해 필터를 하나씩 만들어야 합니다. 두 경우 모두 결과가 같습니다. 필터 목록을 사용하거나 별도의 검색 권한 필터를 만드는 것은 기본 설정의 문제입니다.

필터 목록 사용에 대해 다음에 유의하세요.

- 필터 목록을 사용하여 사서함 필터와 **MailboxContent** 필터가 포함된 필터를 만들어야 합니다. 

- 필터 목록의 각 구성 요소에는 복잡한 필터 구문이 포함될 수 있습니다. 예를 들어 사서함 및 사이트 필터에는 **-or** 연산자로 구분된 여러 필터가 포함될 수 있습니다.

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>검색 권한 필터 만들기의 예

다음은 **New-ComplianceSecurityFilter** cmdlet을 사용하여 검색 권한 필터를 만드는 예입니다.
  
이 예에서는 사용자가 캐나다의 사서함 및 annb@contoso.com 계정에만 검색 작업을 OneDrive 수 있습니다. 이 필터에는 ISO 3166-1의 3자리 캐나다 국가 코드가 포함되어 있습니다.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'"
```

이 예에서는 사용자가 donh 및 suzanf에서 CustomAttribute1 사서함 속성에 대해 'Marketing' OneDrive 사서함 및 사서함 계정만 검색할 수 있도록 허용합니다.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'"
```

이 예에서는 "US Discovery Managers" 역할 그룹의 구성원이 미국의 사서함 및 OneDrive 계정만 검색할 수 있습니다. 이 필터에는 ISO 3166-1의 3자리 미국 국가 코드가 포함되어 있습니다.
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'"
```

이 예에서는 "Fourth Coffee eDiscovery Managers" 역할 그룹의 구성원이 Department 사서함 속성에 대해 'FourthCoffee' OneDrive 사서함 및 사서함 계정만 검색할 수 있습니다. 또한 이 필터를 사용하면 역할 그룹 구성원이 Fourth Coffee SharePoint 검색할 수 있습니다.

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

> [!NOTE]
> 이전 예제에서는 역할 그룹 구성원이 계정에서 문서를 검색할 수 있도록 사이트 콘텐츠 `SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'` 필터()를 추가로 OneDrive 합니다. 이 필터를 포함하지 않는 경우 역할 그룹 구성원만 에 있는 문서를 검색할 수 `https://contoso.sharepoint.com/sites/FourthCoffee` 있습니다.

이 예에서는 eDiscovery Manager 역할 그룹의 구성원이 Ottawa Users 메일 그룹의 구성원의 사서함 및 OneDrive 계정만 검색할 수 있도록 허용합니다. Get-DistributionGroup PowerShell의 Exchange Online cmdlet은 Ottawa Users 그룹의 구성원을 찾는 데 사용됩니다.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"
```

이 예에서는 사용자가 Executive Team 메일 그룹의 구성원의 사서함 및 OneDrive 검색 작업을 수행할 수 없습니다. 즉, 사용자가 이러한 사서함에서 콘텐츠를 삭제할 수 있습니다. PowerShell의 Get-DistributionGroup cmdlet은 Exchange Online 팀 그룹의 구성원을 찾는 데 사용됩니다.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" 
```

이 예에서는 OneDrive eDiscovery Managers 사용자 지정 역할 그룹의 구성원이 조직의 OneDrive 콘텐츠만 검색할 수 있습니다.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```
  
이 예에서는 2015년 동안 보낸 전자 메일 메시지에 대한 검색 작업만 수행하도록 사용자를 제한합니다.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'"
```

이전 예제와 마찬가지로 이 예제에서는 2015년 1월에 마지막으로 변경된 문서에서만 검색 작업을 수행하도록 제한합니다.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" 
```

이 예에서는 "OneDrive Discovery Managers" 역할 그룹의 구성원이 조직의 사서함에 대해 검색 작업을 수행하지 못하게 합니다.

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"
```

이 예에서는 조직의 모든 사용자가 janet 또는 sarad에서 보내거나 받은 전자 메일 메시지에 대해 검색 작업을 수행하지 못하게 합니다.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'"
```

이 예에서는 필터 목록을 사용하여 사서함과 사이트 필터를 결합합니다. 이 예에서 사서함 필터는 콘텐츠 위치 필터이고 사이트 필터는 콘텐츠 필터입니다.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery'"
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter는** 검색 권한 필터 목록을 반환하는 데 사용됩니다. _FilterName 매개_ 변수를 사용하여 특정 검색 필터에 대한 정보를 반환합니다.
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter는** 기존 검색 권한 필터를 수정하는 데 사용됩니다. 다음 섹션에서는 이 cmdlet의 매개 변수에 대해 설명합니다. 유일한 필수 매개 변수는 _FilterName 입니다._
  
### <a name="filtername"></a>*FilterName*

_FilterName_ 매개 변수는 사용 권한 필터의 이름을 지정합니다.

### <a name="users"></a>*사용자*

Users  _매개_ 변수는 이 필터를 검색에 적용한 사용자를 지정합니다. 이 속성은 다중 값 속성이기 때문에 이 매개 변수를 사용하여 사용자 또는 사용자 그룹을 지정하면 기존 사용자 목록을 덮어 덮어됩니다. 선택한 사용자를 추가 및 제거하는 구문은 다음 예제를 참조합니다.

Users 매개 변수를 사용하여 역할 Microsoft 365 규정 준수 센터 있습니다.  이렇게 하면 사용자 지정 역할 그룹을 만든 다음 해당 역할 그룹에 검색 권한 필터를 할당할 수 있습니다. 예를 들어 다국적 기업의 미국 자회사에 대한 eDiscovery 관리자용 사용자 지정 역할 그룹이 있는 경우를 예로 들어 보겠습니다. _Users_ 매개 변수를 사용하여 역할 그룹의 Name 속성을 사용하여 이 역할 그룹을 지정한 다음 _Filter_ 매개 변수를 사용하여 미국 내 사서함만 검색할 수 있습니다. 이 매개 변수로 메일 그룹을 지정할 수는 없습니다.

### <a name="filters"></a>*필터*

_Filters 매개_ 변수는 준수 보안 필터에 대한 검색 조건을 지정합니다. 다음과 같은 세 가지 유형의 필터를 만들 수 있습니다.

- **사서함 및 OneDrive 필터링:** 이 유형의 필터는 할당된 사용자(Users 매개 OneDrive 지정)가  검색할 수 있는 사서함 및 계정 계정을 지정합니다. 이 유형의 필터에 대한 구문은  _Mailbox_ MailboxPropertyName입니다._ 여기서 _MailboxPropertyName은_ 검색할 수 있는 사서함의 범위를 지정하는 데 사용되는 사서함 속성을 지정합니다. 예를 들어 사서함 필터를 사용하면 이 필터가 할당된 사용자가  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` CustomAttribute10 속성에 "OttawaUsers" 값이 있는 사서함만 검색할 수 있습니다.  지원되는 필터링 가능한 받는 사람 속성은  _MailboxPropertyName 속성에 사용할 수_ 있습니다. 지원되는 속성 목록은 [-RecipientFilter](/powershell/exchange/recipientfilter-properties)매개 변수의 필터링 가능한 속성을 참조하세요.

- **사서함 콘텐츠 필터링:** 이 유형의 필터는 검색할 수 있는 콘텐츠에 적용됩니다. 할당된 사용자가 검색할 수 있는 사서함 콘텐츠를 지정합니다. 이 유형의 필터에 대한 구문은 **MailboxContent_** _SearchablePropertyName:value입니다._ 여기서  _SearchablePropertyName은_ 검색에서 지정할 수 있는 KQL(Keyword Query Language) 속성을 지정합니다. 예를 들어 사서함 콘텐츠 필터를 사용하면 이 필터가 할당된 사용자가 해당 도메인의 받는 사람에게 보낸 메시지만 contoso.com  `MailboxContent_recipients:contoso.com` 있습니다.  검색 가능한 메시지 속성 목록은 [eDiscovery에 대한 키워드 쿼리](keyword-queries-and-search-conditions.md)및 검색 조건을 참조하세요. 

- **사이트 및 사이트 콘텐츠 필터링:** 할당된 SharePoint 검색할 비즈니스용 OneDrive 사이트 또는 사이트 콘텐츠를 지정하는 데 사용할 수 있는 사이트 관련 필터와 사이트 관련 필터에는 다음 두 가지가 있습니다.

  - **Site_** *SearchableSiteProperty* 
  - **SiteContent** _ *SearchableSiteProperty*
  
  이러한 두 필터는 교환이 가능합니다. 예를 들어  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 동일한  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 결과를 반환합니다. 검색 가능한 사이트 속성 목록은 Overview [of crawled and managed properties in SharePoint.](/SharePoint/technical-reference/crawled-and-managed-properties-overview) 쿼리 가능 열에  **예로** 표시된 속성을 사용하여 사이트 또는 사이트 콘텐츠 필터를 만들 수 있습니다.

### <a name="examples-of-changing-search-permissions-filters"></a>검색 권한 필터 변경 예

다음 예제에서는 **Get-ComplianceSecurityFilter** 및 **Set-ComplianceSecurityFilter** cmdlet을 사용하여 필터가 할당된 기존 사용자 목록에 사용자를 추가하거나 제거하는 방법을 보여 주며, 필터에서 사용자를 추가 또는 제거할 때는 SMTP 주소를 사용하여 사용자를 지정합니다.
  
이 예에서는 필터에 사용자를 추가합니다.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

이 예에서는 필터에서 사용자를 제거합니다.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

**Remove-ComplianceSecurityFilter는** 검색 필터를 삭제하는 데 사용됩니다. _FilterName 매개_ 변수를 사용하여 삭제할 필터를 지정합니다.
  
## <a name="more-information"></a>추가 정보

- **검색 권한 필터링은 어떻게 작동하나요?** 사용 권한 필터는 검색이 실행되는 경우 검색 쿼리에 추가됩니다. 사용 권한 필터는 **AND** 부울 연산자에 의해 검색 쿼리에 가입됩니다. 검색 쿼리 및 사용 권한 필터에 대한 쿼리 논리는 다음과 같습니다.

  ```text
  <SearchQuery> AND <PermissionsFilter>
  ```

  예를 들어 Bob이 작업자 메일 그룹의 구성원 사서함에 대해 모든 검색 작업을 수행할 수 있는 권한 필터가 있습니다. 그런 다음 Bob은 검색 쿼리를 사용하여 조직의 모든 사서함에 대해 검색을  `sender:jerry@adatum.com` 실행합니다. 사용 권한 필터와 검색 쿼리는 **AND** 연산자로 논리적으로 결합되어 있기 때문에 검색은 작업자 메일 그룹의 구성원에게 jerry@adatum.com 메시지를 반환합니다. 

- **여러 검색 권한 필터가 있는 경우 발생하는 결과** 검색 쿼리에서는 여러 사용 권한 필터가 **OR 부울** 연산자로 결합됩니다. 따라서 필터 중 하나가 참이면 결과가 반환됩니다. 검색에서 **OR** 연산자로 결합된 모든 필터는 AND 연산자에 의해 검색 쿼리와 **결합됩니다.**

  ```text
  <SearchQuery> AND  (<PermissionsFilter1> OR <PermissionsFilter2> OR <PermissionsFilter3>)
  ```

  검색 필터를 통해 Bob이 작업자 메일 그룹의 구성원 사서함만 검색할 수 있는 이전 예제를 적용해 보겠습니다. 그런 후에 이제 Bob이 Phil의 사서함("Mailbox_Alias -ne 'Phil'")을 검색하지 못하도록 하는 다른 필터를 만듭니다. 이번에는 Phil을 작업자 그룹의 구성원으로 가정합니다. Bob이 조직의 모든 사서함에 대해 검색을 실행하면 Bob이 Phil의 사서함을 검색하지 못하게 하는 필터를 적용한 경우에도 Phil의 사서함에 대한 검색 결과가 반환됩니다. 이것은 Bob이 작업자 그룹을 검색할 수 있도록 하는 첫 번째 필터가 올바르기 때문입니다. Phil이 작업자 그룹의 구성원이더라도 Bob은 Phil의 사서함을 검색할 수 있습니다.

- **비활성 사서함에 대해 검색 권한 필터링이 작동하나요?** 예. 사서함 및 사서함 콘텐츠 필터를 사용하여 조직에서 비활성 사서함을 검색할 수 있는 사용자만 제한할 수 있습니다. 일반 사서함과 마찬가지로 비활성 사서함은 사용 권한 필터를 만드는 데 사용되는 받는 사람 속성을 사용하여 구성해야 합니다. 필요한 경우 **Get-Mailbox -InactiveMailboxOnly** 명령을 사용하여 비활성 사서함의 속성을 표시할 수 있습니다. 자세한 내용은 비활성 사서함 만들기 [및 관리를 참조하세요.](create-and-manage-inactive-mailboxes.md)
  
- **공용 폴더에 대해 검색 권한 필터링이 작동하나요?** 아니요. 앞서 설명한 것 처럼 검색 권한 필터링을 사용하여 검색 권한에서 공용 폴더를 검색할 수 있는 Exchange. 예를 들어 공용 폴더 위치의 항목은 사용 권한 필터를 통해 검색 결과에서 제외할 수 없습니다.

- **사용자가 특정 서비스의 모든 콘텐츠 위치를 검색하도록 허용하면 다른 서비스의 콘텐츠 위치를 검색할 수 없는가요?** 아니요. 앞서 설명한처럼 사용자가 특정 서비스에서 콘텐츠 위치를 검색하지 못하도록 명시적으로 차단하려면 검색 권한 필터를 만들어야 합니다(예: 사용자가 모든 Exchange 사서함 또는 모든 SharePoint 사이트를 검색하지 못하도록 차단). 즉, 사용자가 조직의 모든 SharePoint 검색할 수 있도록 하는 검색 권한 필터를 만들면 해당 사용자가 사서함을 검색할 수 없습니다. 예를 들어 SharePoint 관리자가 사이트만 SharePoint 수 있도록 허용하려면 사서함을 검색할 수 없는 필터를 만들어야 합니다. 마찬가지로 Exchange 관리자만 사서함을 검색할 수 있도록 허용하려면 사이트 검색을 차단하는 필터를 만들어야 합니다.

- **검색 권한 필터는 검색 쿼리 문자 제한에 대해 계산합니까?** 예. 검색 권한 필터는 검색 쿼리의 문자 제한에 계산됩니다. 자세한 내용은 에서 [제한을 Advanced eDiscovery.](limits-ediscovery20.md)

**조직에서 만들 수 있는 검색 권한 필터의 최대 개수는 무엇입니까?**
  
조직에서 만들 수 있는 검색 권한 필터의 수에는 제한이 없습니다. 그러나 검색 쿼리의 조건은 최대 100개입니다. 이 경우 조건은 **부울** 연산자(예: AND, **OR** 및 NEAR)에 의해 쿼리에 연결된 것으로 **정의됩니다.** 조건 수의 제한에는 검색 쿼리 자체와 검색을 실행한 사용자에게 적용되는 모든 검색 권한 필터가 포함됩니다. 따라서 검색 권한 필터가 수록(특히 동일한 사용자 또는 사용자 그룹에 이러한 필터가 적용되는 경우) 검색에 대한 최대 조건 수를 초과할 가능성이 더 낫습니다.

이 제한의 작동 방법을 이해하려면 검색이 실행되는 경우 검색 권한 필터가 검색 쿼리에 추가됩니다. 검색 권한 필터는 **AND** 부울 연산자에 의해 검색 쿼리에 가입됩니다. 검색 쿼리 및 단일 검색 권한 필터에 대한 쿼리 논리는 다음과 같습니다.

```text
<SearchQuery> AND <PermissionsFilter>
```

여러 검색 권한 필터는 **OR** 부울 연산자로 결합된 다음 해당 조건은 AND 연산자에 의해 검색 쿼리에 **연결됩니다.**

검색 쿼리 및 여러 검색 권한 필터에 대한 쿼리 논리는 다음과 같습니다.

```text
<SearchQuery> AND (<PermissionsFilter1> OR <PermissionsFilter2> OR <PermissionsFilter3>...)
```

검색 쿼리 자체는 부울 연산자로 연결된 여러 조건으로 구성될 수 있습니다. 검색 쿼리의 각 조건도 100개 조건 제한에 계산됩니다.

또한 쿼리에 추가된 검색 권한 필터의 수는 검색을 실행하는 사용자에 따라 달라 집니다. 특정 사용자가 검색을 실행하면 해당 사용자에게 적용되는 검색 권한 필터(필터의 *Users* 매개 변수로 정의)가 쿼리에 추가됩니다. 조직에는 수백 개의 검색 권한 필터가 있을 수 있지만 동일한 사용자에게 100개 이상의 필터가 적용된 경우 해당 사용자가 검색을 실행할 때 100개의 조건 제한이 초과될 가능성이 습니다.

조건 제한에 대해 유의해야 할 한 가지가 있습니다. 검색 쿼리 또는 SharePoint 사용 권한 필터에 포함된 특정 사이트 수도 이 제한에 계산됩니다. 

조직에서 조건 제한에 도달하지 못하게 방지하려면 비즈니스 요구 사항을 충족하기 위해 조직의 검색 권한 필터 수를 최대한 적게 유지하세요.