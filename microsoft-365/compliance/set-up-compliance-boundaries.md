---
title: eDiscovery 조사를 위한 준수 경계 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 준수 경계를 사용하여 eDiscovery 관리자가 검색할 수 있는 사용자 콘텐츠 위치를 제어하는 논리적 경계를 Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29596375263d52eb6156ddfa32330f08957ccd15
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2021
ms.locfileid: "60216877"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>eDiscovery 조사를 위한 준수 경계 설정

이 문서의 지침은 핵심 eDiscovery 또는 조사를 관리하는 데 사용할 Advanced eDiscovery 수 있습니다.

규정 준수 경계는 eDiscovery 관리자가 검색할 수 있는 사용자 콘텐츠 위치(예: 사서함, OneDrive 계정 및 SharePoint 사이트)를 제어하는 논리적 경계를 조직 내에 생성합니다. 또한 규정 준수 경계는 조직 내에서 법률, 인사 또는 기타 조사를 관리하는 데 사용되는 eDiscovery 사례에 액세스할 수 있는 사용자도 제어합니다. 지리적 보드 및 규정을 준수해야 하는 다국적 기업과 여러 기관으로 구분되는 정부에 규정 준수 경계가 필요한 경우가 종종 있습니다. 또한 Microsoft 365 준수 경계를 통해 콘텐츠 검색을 수행하고 eDiscovery 사례를 사용하여 조사를 관리할 때 이러한 요구 사항을 충족할 수 있습니다.
  
다음 그림의 예제를 사용하여 규정 준수 경계의 작동 방식에 대해 설명합니다.
  
![준수 경계는 eDiscovery 사례에 대한 액세스를 제어하는 기관 및 관리자 역할 그룹에 대한 액세스를 제어하는 검색 권한 필터로 구성됩니다.](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
이 예에서 Contoso LTD는 Fourth Coffee와 Coho Winery의 두 지사로 구성된 조직입니다. 비즈니스를 위해서는 eDiscovery 관리자와 조사자는 해당 Exchange 사서함, OneDrive 계정 및 해당 SharePoint 사이트만 검색할 수 있도록 요구합니다. 또한 eDiscovery 관리자 및 조사자는 해당 기관에서 eDiscovery 사례만 볼 수 있으며 구성원인 사례에만 액세스할 수 있습니다. 또한 이 시나리오에서 조사자는 콘텐츠 위치를 보류하거나 사례에서 콘텐츠를 내보낼 수 없습니다. 규정 준수 경계가 이러한 요구 사항을 충족하는 방식은 다음과 있습니다.
  
- eDiscovery의 검색 권한 필터링 기능은 eDiscovery 관리자 및 조사자에서 검색할 수 있는 콘텐츠 위치를 제어합니다. 즉, Fourth Coffee 에이전시의 eDiscovery 관리자와 조사관은 Fourth Coffee 자회사의 콘텐츠 위치만 검색할 수 있습니다. Coho Winery 자회사에도 동일한 제한이 적용됩니다.

- [역할 그룹은](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) 준수 경계에 대해 다음과 같은 기능을 제공합니다.

  - 전자 메일에서 eDiscovery 사례를 볼 수 있는 Microsoft 365 규정 준수 센터. 즉, eDiscovery 관리자와 조사관은 해당 에이전시의 eDiscovery 케이스만 볼 수 있습니다.

  - eDiscovery 사례에 구성원을 할당할 수 있는 사용자 제어 즉, eDiscovery 관리자와 조사관은 본인이 소속된 케이스에만 구성원을 할당할 수 있습니다.

  - 특정 권한을 할당하는 역할을 추가하거나 제거하여 구성원이 수행할 수 있는 eDiscovery 관련 작업을 제어합니다.

- 역할 그룹에 검색 권한 필터를 적용하면 작업을 수행할 수 있는 권한이 역할 그룹에 할당된 경우 역할 그룹의 구성원은 다음 검색 관련 작업을 수행할 수 있습니다.

  - 콘텐츠 검색

  - 검색 결과 미리 보기

  - 검색 결과 내보내기

  - 검색에서 반환된 항목 제거

규정 준수 경계를 설정하는 프로세스는 다음과 같습니다.
  
[1단계: 기관을 정의하기 위한 사용자 특성 식별](#step-1-identify-a-user-attribute-to-define-your-agencies)

[2단계: 각 기관에 대한 역할 그룹 만들기](#step-2-create-a-role-group-for-each-agency)

[3단계: 준수 경계를 적용하는 검색 권한 필터 만들기](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[4단계: 기관 내 조사를 위한 eDiscovery 사례 만들기](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>준수 경계를 설정하기 전에

- 사용자에게 라이선스를 할당해야 Exchange Online 합니다. 이 확인을 위해 PowerShell에서 [Get-User](/powershell/module/exchange/get-user) cmdlet을 Exchange Online 합니다.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>1단계: 기관을 정의하기 위한 사용자 특성 식별

첫 번째 단계는 기관을 정의하는 데 사용할 특성을 선택하는 것입니다. 이 특성은 eDiscovery 관리자에게 이 특성에 대한 특정 값이 할당된 사용자의 콘텐츠 위치만 검색하도록 제한하는 검색 권한 필터를 만드는 데 사용됩니다. 예를 들어 Contoso가 Department 특성을 사용하기로 결정한 **경우를 예로 들어 보겠습니다.** Fourth Coffee 자회사의 사용자에 대한 이 특성의 값은 입니다. Coho Winery 자회사의 사용자 값은  `FourthCoffee` `CohoWinery` 입니다. 3단계에서는 이 쌍(예:  `attribute:value` *Department:FourthCoffee)을* 사용하여 eDiscovery 관리자가 검색할 수 있는 사용자 콘텐츠 위치를 제한합니다. 
  
다음은 준수 경계에 사용할 수 있는 사용자 특성의 몇 가지 예입니다.
  
- Company

- CustomAttribute1 - CustomAttribute15

- 부서

- 사무실

- CountryOrRegion(두 글자 국가 코드)

전체 목록은 지원되는 사서함 필터의 전체 [목록을 참조하세요.](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)

## <a name="step-2-create-a-role-group-for-each-agency"></a>2단계: 각 기관에 대한 역할 그룹 만들기

다음 단계는 기관에 맞게 Microsoft 365 규정 준수 센터 역할 그룹을 만드는 것입니다. 기본 제공 eDiscovery 관리자 그룹을 복사하고 적절한 구성원을 추가하고 요구 사항에 적합하지 않은 역할을 제거하여 역할 그룹을 만드는 것이 좋습니다. eDiscovery 관련 역할에 대한 자세한 내용은 [eDiscovery](assign-ediscovery-permissions.md)사용 권한 할당을 참조하세요.
  
역할 그룹을 만들하려면 의  권한 페이지로 이동하여 Microsoft 365 규정 준수 센터 준수 경계 및 eDiscovery 사례를 사용하여 조사를 관리할 각 기관의 각 팀에 대한 역할 그룹을 만드십시오.
  
Contoso 규정 준수 경계 시나리오를 사용하는 경우 4개의 역할 그룹을 만들어야 합니다. 각 그룹에 적절한 구성원을 추가해야 합니다.
  
- Fourth Coffee eDiscovery 관리자

- Fourth Coffee 조사관

- Coho Winery eDiscovery 관리자

- Coho Winery 조사관
  
Contoso 규정 준수 경계 시나리오의 요구 사항을 충족하기  위해  조사자 역할 그룹에서 보류 및 내보내기 역할을 제거하여 조사자는 콘텐츠 위치에 보류를 배치하고 사례에서 콘텐츠를 내보내지 못하도록 합니다.

> [!IMPORTANT]
> 사례의 구성원으로 추가한 역할 그룹에서 역할을 추가하거나 제거하면 역할 그룹이 사례의 구성원(또는 역할 그룹이 구성원인 경우)으로 자동으로 제거됩니다. 이러한 이유는 사례의 구성원에게 추가 사용 권한을 부수적으로 제공하는 것을 방지하기 위한 것입니다. 마찬가지로 역할 그룹이 삭제되면 역할 그룹이 구성원이던 모든 경우에서 제거됩니다.

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>3단계: 준수 경계를 적용하는 검색 권한 필터 만들기

각 기관에 대해 역할 그룹을 만든 후 다음 단계는 각 역할 그룹을 특정 기관에 연결하고 규정 준수 경계 자체를 정의하는 검색 권한 필터를 만드는 것입니다. 각 기관에 대해 하나의 검색 권한 필터를 만들어야 합니다. 보안 권한 필터를 만드는 데 대한 자세한 내용은 [Configure permissions filtering for Content Search을 참조하십시오.](permissions-filtering-for-content-search.md)
  
다음은 이 문서의 시나리오에 대한 준수 경계에 사용되는 검색 권한 필터를 만드는 데 사용되는 구문입니다.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "SiteContent_Path -like '<SharePointURL>' -or SiteContent_Path -like '<OneDriveURL>'"
```

명령의 각 매개 변수에 대한 설명은 다음과 같습니다.
  
- `FilterName`: 필터의 이름을 지정합니다. 필터가 사용되는 기관을 설명하거나 식별하는 이름을 사용 합니다.

- `Users`: 이 필터를 적용한 사용자 또는 그룹을 수행한 검색 작업에 지정합니다. 준수 경계의 경우 이 매개 변수는 필터를 만들 기관에서 역할 그룹(3단계에서 만든 역할 그룹)을 지정합니다. 이 매개 변수는 다중 값 매개 변수이기 때문에 하나 이상의 역할 그룹을 각자 각자 구분하여 포함할 수 있습니다.

- `Filters`: 필터의 검색 조건을 지정합니다. 준수 경계의 경우 다음 필터를 정의합니다. 각 위치는 서로 다른 콘텐츠 위치에 적용됩니다.

  - `Mailbox`: 매개 변수에 정의된 역할 OneDrive 검색할 수 있는 사서함 또는 사용자 계정을 `Users` 지정합니다. 이 필터를 사용하면 역할 그룹의 구성원이 특정 기관의 사서함 또는 OneDrive 계정만 검색할 수 있습니다. 예를 들면 `"Mailbox_Department -eq 'FourthCoffee'"` 입니다.

  - `SiteContent`: 이 필터에는 두 개의 개별 필터가 포함됩니다. 첫 번째 SharePoint 매개 변수에 정의된 역할 그룹이 검색할 수 있는 기관의 사이트 정보를 `SiteContent_Path` `Users` 지정합니다. 예를 들면 `SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee'`와 같습니다. 두 번째 필터(운영자에 의해 첫 번째 필터에 연결)는 기관의 OneDrive `SiteContent_Path` `SiteContent_Path` `or` *도메인(MySite* 도메인이라고도 합니다.)을 지정합니다. 예를 들면 `SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'`와 같습니다. 필터 대신 필터를 `Site_Path` 사용할 수 `SiteContent` 있습니다. 및 필터는 교환이 가능하며 이 문서에 설명된 검색 권한 `Site` `SiteContent` 필터에는 영향을 주지 않습니다.

    > [!IMPORTANT]
    > 이전 검색 권한 OneDrive 필터가 포함된 `SiteContent` 이유는 무엇입니까? 필터는 사서함 및 OneDrive 계정에 모두 적용될 수 있으며 SharePoint 필터를 포함하면 OneDrive 필터도 포함하지 않은 경우 OneDrive `Mailbox`  `Site` 제외됩니다. 검색 권한 필터에 SharePoint 필터가 없는 경우 사서함 필터에 준수 경계 범위에 OneDrive 계정이 포함되는 별도의 OneDrive 필터를 포함할 필요는 없습니다. 즉, 필터만 있는 검색 권한 필터에는 사서함과 사서함 계정이 `Mailbox` 모두 OneDrive 있습니다.

다음은 Contoso 규정 준수 경계 시나리오를 지원하기 위해 생성된 두 검색 권한 필터의 예입니다. 이 두 예는 모두 쉼표로 구분된 필터 목록을 포함합니다. 목록에서 사서함과 사이트 필터는 동일한 검색 사용 권한 필터에 포함되며 쉼표로 구분됩니다.
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

> [!NOTE]
> 이전 예제의 매개 변수 구문에는 `Filters` 필터 *목록이 포함되어 있습니다.* 필터 목록은 사서함 필터와 사이트 경로 필터를 콤보로 구분하여 포함하는 필터입니다. 이전 예제에서 는 을(를) 구분하고 `Mailbox` 필터를 `SiteContent` `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "SiteContent_Path -like '<SharePointURL>' -or SiteContent_Path -like '<OneDriveURL>'"` 사용합니다. eDiscovery 검색을 실행하는 동안 이 필터를 처리하면 필터 목록에서 사서함 필터와 SharePoint/OneDrive 필터 하나씩 두 개의 검색 권한 필터가 만들어집니다. 필터 목록을 사용하는 대신 각 기관에 대해 두 개의 별도 검색 권한 필터를 만들 수 있습니다. 사서함 특성에 대한 검색 권한 필터와 사서함 특성 및 SharePoint 사이트 특성에 대한 SharePoint OneDrive 있습니다. 두 경우 모두 결과가 동일합니다. 필터 목록을 사용하거나 별도의 검색 권한 필터를 만드는 것은 기본 설정의 문제입니다.

### <a name="how-do-the-search-permissions-filters-work-in-this-scenario"></a>이 시나리오에서는 검색 권한 필터가 어떻게 작동하나요?

이 시나리오의 각 기관에 대해 검색 권한 필터가 적용되는 방식은 다음과 같습니다.

1. 이 필터는 먼저 eDiscovery 관리자가 검색할 수 있는 콘텐츠 위치를 `Mailbox` 정의하기 위해 적용됩니다. 이 경우 Coho Winery eDiscovery 관리자는 Department 사서함 속성의 값이 **FourthCoffee인** 사용자의 OneDrive 계정만 검색할 수 있습니다.  Coho Winery eDiscovery 관리자는 부서 사서함 속성 값이 **CohoWinery인** 사용자의 OneDrive 계정만 검색할 수 있습니다.  이 `Mailbox` 필터는 eDiscovery 관리자가 검색할 수 있는 콘텐츠 위치를 지정하기 때문에 콘텐츠 위치 필터입니다. 두 필터에서 eDiscovery 관리자는 특정 사서함 속성 값을 사용하여 콘텐츠 위치만 검색할 수 있습니다.

2. 검색할 수 있는 콘텐츠 위치를 정의한 후 필터의 다음 부분에서 eDiscovery 관리자가 검색할 수 있는 콘텐츠를 정의합니다. 첫 번째 `SiteContent` 필터를 사용하면 Fourth Coffee eDiscovery 관리자는 사이트 경로 속성이 포함되거나 시작되는 문서만 검색할 수 `https://contoso.sharepoint.com/sites/FourthCoffee` 있습니다. Coho Winery eDiscovery 관리자는 를 포함하거나 시작하는 사이트 경로 속성이 있는 문서만 검색할 수 `https://contoso.sharepoint.com/sites/CohoWinery` 있습니다. 따라서 두 필터는 검색할 수 있는 콘텐츠를 정의하므로 콘텐츠 `SiteContent` 필터입니다.  두 필터에서 eDiscovery 관리자는 특정 문서 속성 값이 있는 문서만 검색할 수 있습니다. 검색 가능한 SharePoint 속성이 모든 문서에 스탬프가 지정되어 있기 때문에 모든 SharePoint 관련 필터는 콘텐츠 필터입니다. 자세한 내용은 [eDiscovery에](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)대한 사용 권한 필터링 구성을 참조하세요.

   > [!NOTE]
   > 이 문서의 시나리오에서는 이 시나리오를 사용하지 않는 경우 사서함 콘텐츠 필터를 사용하여 eDiscovery 관리자가 검색할 수 있는 콘텐츠를 지정할 수도 있습니다. 사서함 콘텐츠 필터의 구문은 `MailboxContent_<Property:value>` 입니다. 예를 들어 날짜 범위, 받는 사람 또는 도메인을 기준으로 콘텐츠 필터를 만들 수 있습니다. 사서함 콘텐츠 필터에 대한 자세한 내용은 [Configure search permissions filtering을 참조하십시오.](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)

3. 검색 권한 필터는 **AND** 부울 연산자에 의해 검색 쿼리에 가입됩니다. 즉, 기관 중 하나의 eDiscovery 관리자가 eDiscovery 검색을 실행하면 검색에서 반환되는 항목은 검색 쿼리 및 검색 권한 필터에 정의된 조건과 일치해야 합니다.

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a>4단계: 기관 내 조사를 위한 eDiscovery 사례 만들기

마지막 단계는 2단계에서 Core eDiscovery 사례 또는 Advanced eDiscovery 사례를 Microsoft 365 규정 준수 센터 2단계에서 만든 역할 그룹을 사례의 구성원으로 추가하는 것입니다. 따라서 규정 준수 경계를 사용하는 두 가지 중요한 특성이 있습니다.
  
- 사례에 추가된 역할 그룹의 구성원만 사례를 보고 액세스할 수 Microsoft 365 규정 준수 센터. 예를 들어 Fourth Coffee Investigators 역할 그룹이 사례의 유일한 구성원인 경우 Fourth Coffee eDiscovery Managers 역할 그룹의 구성원(또는 다른 역할 그룹의 구성원)은 사례를 보거나 액세스할 수 없습니다.

- 사례에 할당된 역할 그룹의 구성원이 사례와 연결된 검색을 실행하면 해당 기관 내의 콘텐츠 위치(3단계에서 만든 검색 권한 필터로 정의)만 검색할 수 있습니다.

사례를 만들고 구성원을 할당합니다.

1. 웹 페이지의 **Core eDiscovery** 또는 Advanced eDiscovery 페이지로 Microsoft 365 규정 준수 센터 사례를 만드십시오. 

2. 사례 목록에서 만든 사례의 이름을 클릭합니다.

3. 역할 그룹을 사례에 구성원으로 추가합니다. 자세한 내용은 다음 문서 중 하나를 참조하십시오.

   - [Core eDiscovery 사례에 구성원 추가](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [사례에 구성원 Advanced eDiscovery 추가](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> 역할 그룹을 사례에 추가할 때 사용자가 구성원으로 있는 역할 그룹만 추가할 수 있습니다.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Multi-Geo 환경에서 콘텐츠 검색 및 내보내기

검색 권한 필터를 사용하면 내보낼 콘텐츠가 라우팅되는 위치와 특정 환경의 콘텐츠 위치를 검색할 때 검색할 수 있는 데이터 센터를 [SharePoint Multi-Geo 있습니다.](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)
  
- **검색 결과 내보내기:** 특정 데이터 센터에서 Exchange, 사이트 및 SharePoint 계정에서 OneDrive 내보낼 수 있습니다. 즉, 검색 결과를 내보낼 데이터 센터 위치를 지정할 수 있습니다.

    **New-ComplianceSecurityFilter** 또는 **Set-ComplianceSecurityFilter** cmdlet에 *대해 Region* 매개 변수를 사용하여 내보내기 경로 지정 데이터 센터를 만들거나 변경합니다.
  
    |**매개 변수 값**|**데이터센터 위치**|
    |:-----|:-----|
    |NAM  <br/> |북아메리칸어(미국에 데이터 센터)  <br/> |
    |EUR  <br/> |유럽  <br/> |
    |APC  <br/> |아시아 태평양  <br/> |
    |CAN <br/> |캐나다|
    |||

- **콘텐츠 검색 라우팅:** 사이트 및 사이트 계정의 콘텐츠 SharePoint 라우팅할 OneDrive 데이터 센터로 라우팅할 수 있습니다. 즉, 검색을 실행할 데이터 센터 위치를 지정할 수 있습니다.

    *Region* 매개 변수에 대해 다음 값 중 하나를 사용하여 사이트 및 계정의 검색 시 검색이 SharePoint 데이터 센터 위치를 OneDrive 있습니다.
  
    |**매개 변수 값**|**데이터 센터의 데이터 센터 라우팅 SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |US  <br/> |
    |EUR  <br/> |유럽  <br/> |
    |APC  <br/> |아시아 태평양  <br/> |
    |CAN  <br/> |US  <br/> |
    |AUS  <br/> |아시아 태평양  <br/> |
    |KOR  <br/> |조직의 기본 데이터 센터  <br/> |
    |GBR  <br/> |유럽  <br/> |
    |JPN  <br/> |아시아 태평양  <br/> |
    |IND  <br/> |아시아 태평양  <br/> |
    |LAM  <br/> |US  <br/> |
    |NOR  <br/> |유럽 |
    |BRA  <br/> |북미 데이터 센터 |
    |||

   검색 권한 필터에 *대해 Region* 매개 변수를 지정하지 않으면 조직의 기본 SharePoint 지역이 검색됩니다. 검색 결과를 가장 가까운 데이터 센터로 내보낼 수 있습니다.

   개념을 단순화하기 위해 *Region* 매개 변수는 데이터 센터 및 데이터 센터에서 콘텐츠를 검색하는 SharePoint OneDrive. 콘텐츠 검색은 데이터 센터의 지리적 위치에 Exchange Exchange 콘텐츠 검색에는 적용되지 않습니다. 또한 동일한 *Region* 매개 변수 값에 따라 내보내기 경로가 라우팅되는 데이터 센터가 지정될 수도 있습니다. 이는 종종 지리적 보드에서 데이터 이동을 제어하는 데 필요합니다.

> [!NOTE]
> 이 매개 변수를 Advanced eDiscovery *Region* 매개 변수는 데이터를 내보낼 지역을 제어하지 않습니다. 데이터는 조직의 중앙 위치에서 내보낼 수 있습니다. 또한 SharePoint 및 OneDrive 검색은 데이터 센터의 지리적 위치에 의해 바인딩되지 않습니다. 모든 데이터 센터가 검색됩니다. 자세한 내용은 Advanced eDiscovery 의 Advanced eDiscovery [솔루션 개요를 Microsoft 365.](overview-ediscovery-20.md)

다음은 준수 경계에 대한 검색 권한 필터를 만들 때 *Region* 매개 변수를 사용하는 예입니다. 이 경우 Fourth Coffee 자회사가 북미에 있으며 Coho Winery가 유럽에 있는 것으로 가정합니다.
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'" -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'" -Region EUR
```

다중 위치 환경에서 콘텐츠를 검색하고 내보낼 때 다음에 유의하세요.
  
- *지역* 매개 변수가 Exchange 사서함의 검색을 제어하지 않습니다. 사서함을 검색하면 모든 데이터 센터가 검색됩니다. 사서함이 검색되는 Exchange 제한하려면 검색 권한 필터를 만들거나 변경할 때 *Filters* 매개 변수를 사용합니다.

- eDiscovery 관리자가 여러 SharePoint 지역을 검색해야 하는 경우 해당 eDiscovery 관리자에 대해 다른 사용자 계정을 만들어 검색 권한 필터에서 사용하여 SharePoint 사이트 또는 OneDrive 계정이 있는 지역을 지정해야 합니다. 이 설정을 설정하는 자세한 내용은 콘텐츠 검색의 "SharePoint Multi-Geo 환경에서 콘텐츠 검색" [섹션을 참조하세요.](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)

- SharePoint 및 OneDrive 검색할 때 *Region* 매개 변수는 eDiscovery 관리자가 eDiscovery 조사를 수행하게 될 기본 또는 위성 위치로 검색을 지시합니다. eDiscovery 관리자가 검색 권한 SharePoint OneDrive 영역 외부의 사이트 및 사이트 검색을 검색하면 검색 결과가 반환되지 않습니다.

- Core eDiscovery에서 검색 결과를 내보낼 때 콘텐츠 검색 도구를 사용하여 검색할 수 있는 모든 콘텐츠 위치(Exchange, 비즈니스용 Skype, SharePoint, OneDrive 및 기타 서비스)의 콘텐츠가 데이터 센터의 Azure Storage 위치에 업로드됩니다. *Region* 매개 변수입니다. 이렇게 하면 조직이 제어된 테두리에서 콘텐츠를 내보내지 못하도록 하여 규정 준수를 유지하도록 할 수 있습니다. 검색 권한 필터에 지역이 지정되지 않은 경우 콘텐츠가 조직의 기본 데이터 센터에 업로드됩니다.

  사용자 계정에서 Advanced eDiscovery Region 매개 변수를 사용하여 콘텐츠가 업로드되는 위치를 제어할 *수* 없습니다. 콘텐츠가 조직의 Azure Storage 데이터 센터의 위치로 업로드됩니다. 중앙 위치에 기반한 지리적 위치 목록은 [Multi-Geo eDiscovery Microsoft 365 참조하세요.](../enterprise/multi-geo-ediscovery-configuration.md)

- 다음 명령을 실행하여 기존 검색 권한 필터를 편집하여 지역을 추가하거나 변경할 수 있습니다.

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>허브 사이트에 SharePoint 준수 경계 사용

SharePoint 허브 [사이트는](/sharepoint/dev/features/hub-site/hub-site-overview) eDiscovery 규정 준수 경계가 따르는 동일한 지리적 또는 기관 경계에 맞춰 정렬되는 경우가 종종 있습니다. 즉, 허브 사이트의 사이트 ID 속성을 사용하여 준수 경계를 만들 수 있습니다. 이렇게하려면 SharePoint Online PowerShell의 [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) cmdlet을 사용하여 허브 사이트의 SiteId를 얻은 다음 부서 ID 속성에 이 값을 사용하여 검색 권한 필터를 만드면 됩니다.

다음 구문을 사용하여 SharePoint 허브 사이트에 대한 검색 권한 필터를 만들 수 있습니다.

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'"
```

다음은 Coho Winery 기관의 허브 사이트에 대한 검색 권한 필터를 만드는 예입니다.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'"
```

## <a name="compliance-boundary-limitations"></a>규정 준수 경계 제한

준수 경계를 사용하는 eDiscovery 사례 및 조사를 관리할 때 다음 제한 사항을 염두에 두어야 합니다.
  
- 검색을 만들고 실행할 때 에이전시 외부에 있는 콘텐츠 위치를 선택할 수 있습니다. 하지만 검색 권한 필터로 인하여 해당 위치의 콘텐츠는 검색 결과에 포함되지 않습니다.

- eDiscovery 사례의 보류에는 규정 준수 경계가 적용되지 않습니다. 즉, 한 에이전시의 eDiscovery 관리자가 보류 중인 다른 에이전시의 사용자가 될 수 있습니다. 하지만 eDiscovery 관리자가 보류된 사용자의 콘텐츠 위치를 검색할 경우 준수 경계가 적용됩니다. 즉, eDiscovery 관리자는 사용자를 보류 상태로 지정할 수는 있지만 사용자의 콘텐츠 위치를 검색할 수는 없습니다.

    또한 보류 통계는 에이전시의 콘텐츠 위치에만 적용됩니다.

- 검색 권한 필터(사서함 또는 사이트 필터)가 할당되어 있으며 조직의 모든 SharePoint 사이트를 포함하는 검색에 대해 인덱서되지 않은 항목을 내보내려고 시도하면 다음 오류 메시지가 표시됩니다. `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` . 검색 권한 필터가 할당되어 있으며 인덱서되지 않은 항목을 SharePoint 검색을 다시 시작하고 검색할 특정 SharePoint 포함해야 합니다. 그렇지 않으면 모든 사이트가 포함된 검색에서 인덱싱된 항목만 내보낼 SharePoint 있습니다. 검색 결과를 내보낼 때의 옵션에 대한 자세한 내용은 콘텐츠 검색 결과 [내보내기 를 참조하세요.](export-search-results.md#step-1-prepare-search-results-for-export)

- Exchange 공용 폴더에는 검색 권한 필터가 적용되지 않습니다.

## <a name="more-information"></a>추가 정보

- 사서함이 사용이 허가되지 않는 경우 사용자는 더 이상 준수 경계 내에서 고려되지 않습니다. 사서함이 삭제될 때 사서함에 보류가 적용된 경우 사서함에 보존된 콘텐츠에는 여전히 준수 경계 또는 검색 권한 필터가 적용됩니다.

- 사용자에 대해 준수 경계 및 검색 권한 필터를 구현하는 경우 사용자의 사서함을 삭제하지 말고 해당 사용자 사서함을 삭제하지 OneDrive 좋습니다. 즉, 사용자의 사서함을 삭제하는 경우 사용자 사서함에 대해 검색 권한 필터를 적용하는 데 OneDrive 계정도 mailbox_RecipientFilter 계정도 제거해야 OneDrive.

- 규정 준수 경계 및 검색 권한 필터는 이 스탬프된 콘텐츠의 Exchange, OneDrive 및 SharePoint 인덱싱에 따라 스탬프가 설정됩니다.

- 콘텐츠 기반 준수 경계에 제외 필터(예: 검색 권한 필터에서 사용)를 사용하지 `-not()` 않는 것이 좋습니다. 최근에 업데이트된 특성이 있는 콘텐츠가 인덱싱되지 않은 경우 제외 필터를 사용하면 예기치 않은 결과가 발생할 수 있습니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**Who 및 cmdlet을 사용하여 검색 권한 필터를 New-ComplianceSecurityFilter Set-ComplianceSecurityFilter 수 있습니까?**
  
검색 권한 필터를 만들고 보고 수정하려면 검색 권한 필터에서 Organization Management 역할 그룹의 구성원 Microsoft 365 규정 준수 센터.
  
**eDiscovery 관리자가 여러 기관에 걸쳐 있는 둘 이상의 역할 그룹에 할당된 경우 한 기관 또는 다른 기관에서 콘텐츠를 검색하는 방법**
  
eDiscovery 관리자는 검색 쿼리에 특정 기관으로 검색을 제한하는 매개 변수를 추가할 수 있습니다. 예를 들어 조직에서 기관을 차별화하기 위해 **CustomAttribute10** 속성을 지정한 경우 검색 쿼리에 다음을 추가하여 특정 기관의 사서함 및 OneDrive 계정을 검색할 수 있습니다. `CustomAttribute10:<value>` .
  
**검색 권한 필터에서 준수 특성으로 사용되는 특성 값이 변경되는 경우 어떻게 하나요?**
  
필터에 사용되는 특성 값이 변경되는 경우 검색 권한 필터에서 준수 경계를 적용하는 데 최대 3일이 소요됩니다. 예를 들어 Contoso 시나리오에서 Fourth Coffee 에이전시의 사용자가 Coho Winery 에이전시로 전송되는 경우를 예로 들어 보겠습니다. 따라서 사용자 개체의 **Department** 특성 값이 *FourthCoffee에서* *CohoWinery로 변경됩니다.* 이 경우 Fourth Coffee eDiscovery 및 투자자는 특성이 변경된 후 최대 3일 동안 해당 사용자에 대한 검색 결과를 얻게 됩니다. 마찬가지로 Coho Winery eDiscovery 관리자 및 조사자는 사용자의 검색 결과를 얻기까지 최대 3일이 소요됩니다.
  
**eDiscovery 관리자가 두 개의 별도 규정 준수 경계의 콘텐츠를 볼 수 있나요?**
  
예, 두 기관을 모두 볼 수 있는 역할 그룹에 eDiscovery 관리자를 Exchange 사서함을 검색할 때 이 기능을 사용할 수 있습니다. 그러나 SharePoint 및 OneDrive 계정을 검색할 때 eDiscovery 관리자는 기관이 같은 지역 또는 지리적 위치에 있는 경우만 서로 다른 준수 경계에서 콘텐츠를 검색할 수 있습니다. **참고:** 사이트와 사이트 Advanced eDiscovery 검색할 때 지리적 위치가 SharePoint OneDrive 제한이 적용되지 않습니다.
  
**검색 권한 필터는 eDiscovery 사례 보류, Microsoft 365 또는 DLP에 대해 작동합니까?**
  
아니요, 현재는 불가능합니다.
  
**콘텐츠를 내보낼 위치를 제어하는 지역을 지정하지만 해당 지역에 SharePoint 조직이 없는 경우 해당 지역을 검색할 SharePoint?**
  
검색 권한 필터에 지정된 영역이 조직에 없는 경우 기본 지역이 검색됩니다.
  
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
