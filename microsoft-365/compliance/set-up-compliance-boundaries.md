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
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 준수 경계를 사용하여 eDiscovery 관리자가 Microsoft 365에서 검색할 수 있는 사용자 콘텐츠 위치를 제어하는 논리적 경계를 만드는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80f1c6705550d21ac54a0fb4dda2b605b497adbc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919504"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>eDiscovery 조사를 위한 준수 경계 설정

이 문서의 지침은 Core eDiscovery 또는 Advanced eDiscovery를 사용하여 조사를 관리할 때 적용할 수 있습니다.

규정 준수 경계는 조직 내에서 eDiscovery 관리자가 검색할 수 있는 사용자 콘텐츠 위치(예: 사서함, OneDrive 계정 및 SharePoint 사이트)를 제어하는 논리적 경계를 만들 수 있습니다. 또한 규정 준수 경계는 조직 내에서 법률, 인사 또는 기타 조사를 관리하는 데 사용되는 eDiscovery 사례에 액세스할 수 있는 사용자도 제어합니다. 지리적 보드 및 규정을 준수해야 하는 다국적 기업과 여러 기관으로 구분되는 정부에 규정 준수 경계가 필요한 경우가 종종 있습니다. Microsoft 365에서 규정 준수 경계는 콘텐츠 검색을 수행하고 eDiscovery 사례를 사용하여 조사를 관리할 때 이러한 요구 사항을 충족하는 데 도움이 됩니다.
  
다음 그림의 예제를 사용하여 규정 준수 경계의 작동 방식에 대해 설명합니다.
  
![규정 준수 경계는 eDiscovery 사례에 대한 액세스를 제어하는 기관 및 관리자 역할 그룹에 대한 액세스를 제어하는 검색 권한 필터로 구성됩니다.](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
이 예에서 Contoso LTD는 Fourth Coffee와 Coho Winery의 두 지사로 구성된 조직입니다. 기업에서는 eDiscovery 관리 및 조사자는 해당 기관의 Exchange 사서함, OneDrive 계정 및 SharePoint 사이트만 검색할 수 있도록 요구합니다. 또한 eDiscovery 관리자 및 조사자는 해당 기관에서 eDiscovery 사례만 볼 수 있으며 구성원인 사례에만 액세스할 수 있습니다. 또한 이 시나리오에서 조사자는 콘텐츠 위치를 보류하거나 사례에서 콘텐츠를 내보낼 수 없습니다. 규정 준수 경계가 이러한 요구 사항을 충족하는 방식은 다음과 있습니다.
  
- 콘텐츠 검색의 검색 권한 필터링 기능은 eDiscovery 관리자 및 조사자에서 검색할 수 있는 콘텐츠 위치를 제어합니다. 즉, Fourth Coffee 기관의 eDiscovery 관리자 및 조사자는 Fourth Coffee 자회사의 콘텐츠 위치만 검색할 수 있습니다. Coho Winery 자회사에도 동일한 제한이 적용됩니다.

- 역할 그룹은 준수 경계에 대해 다음과 같은 기능을 제공합니다.

  - 보안 및 준수 센터에서 eDiscovery 사례를 볼 & 제어합니다. 즉, eDiscovery 관리자 및 조사자는 해당 기관에서 eDiscovery 사례만 볼 수 있습니다.

  - eDiscovery 사례에 구성원을 할당할 수 있는 사용자 제어 즉, eDiscovery 관리자와 조사자는 자신들이 구성원으로 있는 사례에만 구성원을 할당할 수 있습니다.

  - 특정 권한을 할당하는 역할을 추가하거나 제거하여 구성원이 수행할 수 있는 eDiscovery 관련 작업을 제어합니다.

규정 준수 경계를 설정하는 프로세스는 다음과 같습니다.
  
[1단계: 기관을 정의하기 위한 사용자 특성 식별](#step-1-identify-a-user-attribute-to-define-your-agencies)

[2단계: Microsoft 지원 서비스에서 사용자 특성을 OneDrive 계정과 동기화하도록 요청 제출](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[3단계: 각 기관에 대한 역할 그룹 만들기](#step-3-create-a-role-group-for-each-agency)

[4단계: 준수 경계를 적용하는 검색 권한 필터 만들기](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[5단계: 기관 내 조사를 위한 eDiscovery 사례 만들기](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>준수 경계를 설정하기 전에

ID가 있는 Azure AD(Active Directory) 특성(1단계)을 사용자의 OneDrive 계정(2단계)에 성공적으로 동기화하려면 먼저 다음 선행 요구 사항을 충족해야 합니다.

- 사용자에게 Exchange Online 라이선스 및 SharePoint Online 라이선스가 할당되어야 합니다.

- 사용자 사서함의 크기는 10MB 이상입니다. 사용자의 사서함이 10MB 미만이면 기관을 정의하는 데 사용되는 특성이 사용자의 OneDrive 계정에 동기화되지 않습니다.

- 준수 경계 및 검색 권한 필터를 만드는 데 사용되는 특성을 사용하려면 Azure AD(Azure Active Directory) 특성을 사용자 사서함과 동기화해야 합니다. 사용하려는 특성이 동기화된지 확인하려는 경우 Exchange Online PowerShell에서 [Get-User](/powershell/module/exchange/get-user) cmdlet을 실행합니다. 이 cmdlet의 출력에는 Exchange Online에 동기화된 Azure AD 특성이 표시됩니다.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>1단계: 기관을 정의하기 위한 사용자 특성 식별

첫 번째 단계는 기관을 정의하는 데 사용할 Azure AD 특성을 선택하는 것입니다. 이 특성은 eDiscovery 관리자에게 이 특성에 대한 특정 값이 할당된 사용자의 콘텐츠 위치만 검색하도록 제한하는 검색 권한 필터를 만드는 데 사용됩니다. 예를 들어 Contoso가 Department 특성을 사용하기로 결정한 **경우를 예로 들어 보겠습니다.** Fourth Coffee 자회사의 사용자에 대한 이 특성의 값은 입니다. Coho Winery 자회사의 사용자 값은  `FourthCoffee` `CohoWinery` 입니다. 4단계에서 이 쌍(예:  `attribute:value` *Department:FourthCoffee)을* 사용하여 eDiscovery 관리자가 검색할 수 있는 사용자 콘텐츠 위치를 제한합니다. 
  
규정 준수 경계에 사용할 수 있는 Azure AD 사용자 특성 목록은 다음과 같습니다.
  
- Company

- CustomAttribute1 - CustomAttribute15

- 부서

- 사무실

- C(2문자 국가 코드) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup> 이 특성은 Exchange Online PowerShell에서 **Get-User** cmdlet을 실행하여 반환되는 CountryOrRegion 속성에 매핑됩니다. 이 cmdlet은 두 글자로 된 국가 코드에서 번역되는 지역화된 국가 이름을 반환합니다. 자세한 내용은 [Set-User](/powershell/module/exchange/set-user) cmdlet 참조 문서의 CountryOrRegion 매개 변수 설명을 참조하세요.

더 많은 사용자 특성을 사용할 수 있습니다. 특히 Exchange 사서함의 경우 위에 나열된 특성만 현재 OneDrive에서 지원됩니다.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>2단계: Microsoft 지원 서비스에서 사용자 특성을 OneDrive 계정과 동기화하도록 요청 제출

다음 단계는 1단계에서 선택한 Azure AD 특성을 조직의 모든 OneDrive 계정과 동기화하기 위해 Microsoft 지원에 요청을 제출하는 것입니다. 이 동기화가 발생하면 1단계에서 선택한 특성 및 해당 값이 라는 숨겨진 관리 속성에 `ComplianceAttribute` 매핑됩니다. 이 특성을 사용하여 4단계에서 OneDrive에 대한 검색 권한 필터를 만들 수 있습니다.
  
Microsoft 지원에 요청을 제출할 때 다음 정보를 포함합니다.
  
- 조직의 기본 도메인 이름

- Azure AD 특성의 이름(1단계)

- 지원 요청의 목적에 대한 다음 제목 또는 설명: "규정 준수 보안 필터를 위해 Azure AD와 비즈니스용 OneDrive 동기화 사용". 이렇게 하면 요청을 구현하는 eDiscovery 엔지니어링 팀으로 요청을 라우팅하는 데 도움이 됩니다.

엔지니어링 변경이 이행된 후 특성이 OneDrive에 동기화된 후 Microsoft 지원에서 변경된 빌드 번호와 예상 배포 날짜를 전송합니다. 배포 프로세스는 일반적으로 지원 요청을 제출한 후 4~6주가 소요됩니다.
  
> [!IMPORTANT]
> 이 특성 변경이 배포되기 전에 3~5단계를 완료할 수 있습니다. 그러나 콘텐츠 검색을 실행하면 특성 동기화가 배포될 때까지 검색 권한 필터에 지정된 OneDrive 계정의 문서가 반환되지 않습니다.
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>3단계: 각 기관에 대한 역할 그룹 만들기

다음 단계는 보안 및 준수 센터에서 기관과 & 역할 그룹을 만드는 것입니다. 기본 제공 eDiscovery Managers 그룹을 복사하고, 적절한 구성원을 추가하고, 요구에 적합하지 않을 수 있는 역할을 제거하여 역할 그룹을 만드는 것이 좋습니다. eDiscovery 관련 역할에 대한 자세한 내용은 Office 365 보안 및 준수 센터에서 [eDiscovery 권한 할당을 & 참조하세요.](assign-ediscovery-permissions.md)
  
역할 그룹을 만들하려면 보안  & 준수 센터의 사용 권한 페이지로 이동하여 준수 경계 및 eDiscovery 사례를 사용하여 조사를 관리할 각 기관의 각 팀에 대한 역할 그룹을 만드십시오.
  
Contoso 규정 준수 경계 시나리오를 사용하는 경우 4개의 역할 그룹을 만들어야 합니다. 각 그룹에 적절한 구성원을 추가해야 합니다.
  
- Fourth Coffee eDiscovery 관리자

- Fourth Coffee Investigators

- Coho Winery eDiscovery 관리자

- Coho Winery Investigators
  
Contoso 규정 준수 경계 시나리오의 요구 사항을 충족하기  위해  조사자 역할 그룹에서 보류 및 내보내기 역할을 제거하여 조사자는 콘텐츠 위치에 보류를 배치하고 사례에서 콘텐츠를 내보내지 못하도록 합니다.

## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>4단계: 준수 경계를 적용하는 검색 권한 필터 만들기

각 기관에 대해 역할 그룹을 만든 후 다음 단계는 각 역할 그룹을 특정 기관에 연결하고 규정 준수 경계 자체를 정의하는 검색 권한 필터를 만드는 것입니다. 각 기관에 대해 하나의 검색 권한 필터를 만들어야 합니다. 보안 권한 필터를 만드는 데 대한 자세한 내용은 [Configure permissions filtering for Content Search을 참조하십시오.](permissions-filtering-for-content-search.md)
  
다음은 준수 경계에 사용되는 검색 권한 필터를 만드는 데 사용되는 구문입니다.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

명령의 각 매개 변수에 대한 설명은 다음과 같습니다.
  
- `FilterName`: 필터의 이름을 지정합니다. 필터가 사용되는 기관을 설명하거나 식별하는 이름을 사용 합니다.

- `Users`: 이 필터를 적용한 사용자 또는 그룹을 수행한 콘텐츠 검색 작업에 지정합니다. 준수 경계의 경우 이 매개 변수는 필터를 만들 기관에서 역할 그룹(3단계에서 만든 역할 그룹)을 지정합니다. 이 매개 변수는 다중 값 매개 변수이기 때문에 하나 이상의 역할 그룹을 각자 각자 구분하여 포함할 수 있습니다.

- `Filters`: 필터의 검색 조건을 지정합니다. 준수 경계에 대해 다음 필터를 정의합니다. 각 위치는 콘텐츠 위치에 적용됩니다. 

    - `Mailbox`: 매개 변수에 정의된 역할 그룹이 검색할 수 있는  `Users` 사서함을 지정합니다. 규정 준수 경계의 경우  *ComplianceAttribute는*  1단계에서 식별한 특성과  *AttributeValue가*  기관을 지정하는 특성과 동일합니다. 이 필터를 사용하면 역할 그룹의 구성원이 특정 기관의 사서함만 검색할 수 있습니다. 예를 들면 `"Mailbox_Department -eq 'FourthCoffee'"` 입니다. 

    - `Site`: 매개 변수에 정의된 역할 그룹이 검색할 수 있는 OneDrive 계정을 `Users` 지정합니다. OneDrive 필터의 경우 실제 문자열을 사용  `ComplianceAttribute` 합니다. 이 특성은 1단계에서 식별한 동일한 특성에 매핑됩니다. 이 특성은 2단계에서 제출한 지원 요청의 결과로 OneDrive 계정에 동기화됩니다. *AttributeValue는*  기관을 지정합니다. 이 필터를 사용하면 역할 그룹의 구성원이 특정 기관의 OneDrive 계정만 검색할 수 있습니다. 예를 들면  `"Site_ComplianceAttribute -eq 'FourthCoffee'"` 입니다.

    - `Site_Path`: 매개 변수에 정의된 역할 그룹이 검색할 수 있는 SharePoint 사이트를  `Users` 지정합니다. *SharePointURL은* 역할 그룹의 구성원이 검색할 수 있는 기관의 사이트를 지정합니다. 예:  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. 및 `Site` `Site_Path` 필터는 -or 연산자로 **연결됩니다.**

     > [!NOTE]
     > 매개 변수 구문에는 `Filters` 필터 *목록이 포함되어 있습니다.* 필터 목록은 사서함 필터와 사이트 필터를 각 콤보로 구분하여 포함하는 필터입니다. 이전 예제에서는 을(를)  구분하여 Mailbox_ComplianceAttribute **Site_ComplianceAttribute** `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` 있습니다. 콘텐츠 검색을 실행하는 동안 이 필터를 처리하면 필터 목록에서 사서함 필터와 사이트 필터 1개 등 두 개의 검색 권한 필터가 만들어집니다. 필터 목록을 사용하는 대신 각 기관에 대해 두 개의 별도 검색 권한 필터를 만들 수 있습니다. 사서함 특성에 대한 검색 권한 필터와 사이트 특성에 대한 필터가 각각 하나씩 있습니다. 두 경우 모두 결과가 동일합니다. 필터 목록을 사용하거나 별도의 검색 권한 필터를 만드는 것은 기본 설정의 문제입니다.

- `Action`: 필터가 적용되는 준수 검색 작업의 유형을 지정합니다. 예를 들어 매개 변수에 정의된 역할 그룹의 구성원이 콘텐츠 검색을 실행할 때만  `-Action Search` `Users` 필터를 적용합니다. 이 경우 검색 결과를 내보낼 때 필터가 적용되지 않습니다. 준수 경계의 경우 필터가 모든 검색 작업에  `-Action All` 적용 하도록 사용 합니다. 

    콘텐츠 검색 작업 목록은 [Configure permissions filtering for Content Search의](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)"New-ComplianceSecurityFilter" 섹션을 참조하십시오.

다음은 Contoso 규정 준수 경계 시나리오를 지원하기 위해 만들어지기 위한 두 가지 검색 권한 필터의 예입니다. 이러한 두 예에는 사서함과 사이트 필터가 동일한 검색 권한 필터에 포함되어 있으며 각 필터가 각기 다른 콤보 필터로 구분되는 콤보로 구분된 필터 목록이 있습니다.
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>5단계: 기관 내 조사를 위한 eDiscovery 사례 만들기

마지막 단계는 Microsoft 365 규정 준수 센터에서 Core eDiscovery 사례 또는 Advanced eDiscovery 사례를 만든 다음 3단계에서 만든 역할 그룹을 사례의 구성원으로 추가하는 것입니다. 따라서 규정 준수 경계를 사용하는 두 가지 중요한 특성이 있습니다.
  
- 사례에 추가된 역할 그룹의 구성원만 보안 및 준수 센터에서 사례를 & 수 있습니다. 예를 들어 Fourth Coffee Investigators 역할 그룹이 사례의 유일한 구성원인 경우 Fourth Coffee eDiscovery Managers 역할 그룹의 구성원(또는 다른 역할 그룹의 구성원)은 사례를 보거나 액세스할 수 없습니다.

- 사례에 할당된 역할 그룹의 구성원이 사례와 연결된 검색을 실행하면 해당 기관 내의 콘텐츠 위치(4단계에서 만든 검색 권한 필터로 정의)만 검색할 수 있습니다.

사례를 만들고 구성원을 할당합니다.

1. Microsoft 365 규정 준수 센터의 **Core eDiscovery** 또는 **Advanced eDiscovery** 페이지로 이동하여 사례를 만드십시오.

2. 사례 목록에서 만든 사례의 이름을 클릭합니다.

3. 이 경우 **관리 플라이아웃** 페이지의 역할 그룹 **관리에서** 추가 ![ 아이콘 ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **추가를 클릭합니다.**

    ![eDiscovery 사례의 구성원으로 역할 그룹 추가](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 역할 그룹 목록에서 3단계에서 만든 역할 그룹 중 하나를 선택하고 추가를 **클릭합니다.**

5. 이 **사례** 관리 **플라이아웃에서** 저장을 클릭하여 변경을 저장합니다.

> [!NOTE]
> 역할 그룹을 사례에 추가할 때 사용자가 구성원으로 있는 역할 그룹만 추가할 수 있습니다.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Multi-Geo 환경에서 콘텐츠 검색 및 내보내기

검색 권한 필터를 사용하면 내보내기용 콘텐츠가 라우팅되는 위치와 [SharePoint Multi-Geo](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)환경에서 콘텐츠 위치를 검색할 때 검색할 수 있는 데이터 센터를 제어할 수도 있습니다.
  
- **검색 결과 내보내기:** 특정 데이터 센터에서 Exchange 사서함, SharePoint 사이트 및 OneDrive 계정에서 검색 결과를 내보낼 수 있습니다. 즉, 검색 결과를 내보낼 데이터 센터 위치를 지정할 수 있습니다.

    **New-ComplianceSecurityFilter** 또는 **Set-ComplianceSecurityFilter** cmdlet에 **대해 Region** 매개 변수를 사용하여 내보내기 경로 지정 데이터 센터를 만들거나 변경합니다.
  
    |**매개 변수 값**|**데이터 센터 위치**|
    |:-----|:-----|
    |NAM  <br/> |북아메리칸어(미국에 데이터 센터)  <br/> |
    |EUR  <br/> |유럽  <br/> |
    |APC  <br/> |아시아 태평양  <br/> |
    |CAN <br/> |캐나다|
    |||

- **콘텐츠 검색 라우팅:** SharePoint 사이트 및 OneDrive 계정의 콘텐츠 검색을 위성 데이터 센터로 라우팅할 수 있습니다. 즉, 검색을 실행할 데이터 센터 위치를 지정할 수 있습니다.

    **Region** 매개 변수에 대해 다음 값 중 하나를 사용하여 SharePoint 사이트 및 OneDrive 계정을 검색할 때 검색이 실행되는 데이터 센터 위치를 제어합니다. 
  
    |**매개 변수 값**|**SharePoint의 데이터 센터 라우팅 위치**|
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

   검색 권한 필터에 **대해 Region** 매개 변수를 지정하지 않으면 조직의 기본 SharePoint 지역이 검색됩니다. 검색 결과를 가장 가까운 데이터 센터로 내보낼 수 있습니다.

   개념을 단순화하기 위해 **Region** 매개 변수는 SharePoint 및 OneDrive에서 콘텐츠를 검색하는 데 사용되는 데이터 센터를 제어합니다. Exchange 콘텐츠 검색은 데이터 센터의 지리적 위치에 의해 바인딩되지 않는 Exchange의 콘텐츠 검색에는 적용되지 않습니다. 또한 동일한 **Region** 매개 변수 값에 따라 내보내기 경로가 라우팅되는 데이터 센터가 지정될 수도 있습니다. 이는 종종 지리적 보드에서 데이터 이동을 제어하는 데 필요합니다.

> [!NOTE]
> Advanced eDiscovery를 사용하는 경우 **Region** 매개 변수는 데이터가 내보내는 지역을 제어하지 않습니다. 데이터는 조직의 기본 데이터 센터에서 내보낼 수 있습니다. 또한 SharePoint 및 OneDrive에서 콘텐츠를 검색하는 것은 데이터 센터의 지리적 위치에 의해 바인딩되지 않습니다. 모든 데이터 센터가 검색됩니다. Advanced eDiscovery에 대한 자세한 내용은 [Microsoft 365의 Advanced eDiscovery 솔루션 개요를 참조하세요.](overview-ediscovery-20.md)

다음은 준수 경계에 대한 검색 권한 필터를 만들 때 **Region** 매개 변수를 사용하는 예입니다. 이 경우 Fourth Coffee 자회사가 북미에 있으며 Coho Winery가 유럽에 있는 것으로 가정합니다. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

다중 위치 환경에서 콘텐츠를 검색하고 내보낼 때 다음에 유의하세요.
  
- **지역** 매개 변수가 Exchange 사서함의 검색을 제어하지 않습니다. 사서함을 검색하면 모든 데이터 센터가 검색됩니다. 검색되는 Exchange 사서함의 범위를 제한하려면 검색 권한 필터를 만들거나 변경할 때 **Filters** 매개 변수를 사용합니다. 

- eDiscovery 관리자가 여러 SharePoint 지역을 검색해야 하는 경우 해당 eDiscovery 관리자에 대해 다른 사용자 계정을 만들어 검색 권한 필터에서 사용하여 SharePoint 사이트 또는 OneDrive 계정이 있는 지역을 지정해야 합니다. 이 설정에 대한 자세한 내용은 콘텐츠 검색의 "SharePoint Multi-Geo 환경에서 콘텐츠 검색" [섹션을 참조하세요.](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)

- SharePoint 및 OneDrive에서 콘텐츠를 검색할 때 **Region** 매개 변수는 eDiscovery 관리자가 eDiscovery 조사를 수행하게 될 기본 또는 위성 위치로 검색을 지시합니다. eDiscovery 관리자가 검색 권한 필터에 지정된 지역 외부의 SharePoint 및 OneDrive 사이트를 검색하면 검색 결과가 반환되지 않습니다.

- 검색 결과를 내보낼 때 Exchange, 비즈니스용 Skype, SharePoint, OneDrive 및 콘텐츠 검색 도구를 사용하여 검색할 수 있는 기타 서비스 등 모든 콘텐츠 위치의 콘텐츠가 **Region** 매개 변수에 지정된 데이터 센터의 Azure Storage 위치에 업로드됩니다. 이렇게 하면 조직이 제어된 테두리에서 콘텐츠를 내보내지 못하도록 하여 규정 준수를 유지하도록 할 수 있습니다. 검색 권한 필터에 지역이 지정되지 않은 경우 콘텐츠가 조직의 기본 데이터 센터에 업로드됩니다.

- 다음 명령을 실행하여 기존 검색 권한 필터를 편집하여 지역을 추가하거나 변경할 수 있습니다.

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>SharePoint 허브 사이트에 규정 준수 경계 사용

[SharePoint 허브 사이트는](/sharepoint/dev/features/hub-site/hub-site-overview) 종종 eDiscovery 규정 준수 경계가 따르는 동일한 지리적 또는 기관 경계에 맞게 조정됩니다. 즉, 허브 사이트의 사이트 ID 속성을 사용하여 준수 경계를 만들 수 있습니다. 이렇게하려면 SharePoint Online PowerShell에서 [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) cmdlet을 사용하여 허브 사이트의 SiteId를 얻은 다음 부서 ID 속성에 이 값을 사용하여 검색 권한 필터를 만드면 됩니다.

다음 구문을 사용하여 SharePoint 허브 사이트에 대한 검색 권한 필터를 만들 수 있습니다.

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

다음은 Coho Winery 기관의 허브 사이트에 대한 검색 권한 필터를 만드는 예입니다.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>규정 준수 경계 제한

준수 경계를 사용하는 eDiscovery 사례 및 조사를 관리할 때 다음 제한 사항을 염두에 두어야 합니다.
  
- 검색을 만들고 실행하는 경우 기관 외부에 있는 콘텐츠 위치를 선택할 수 있습니다. 그러나 검색 권한 필터로 인하여 해당 위치의 콘텐츠는 검색 결과에 포함되지 않습니다.

- eDiscovery 사례의 보류에는 규정 준수 경계가 적용되지 않습니다. 즉, 한 기관의 eDiscovery 관리자가 사용자를 다른 기관에 보류할 수 있습니다. 그러나 eDiscovery 관리자가 보류된 사용자의 콘텐츠 위치를 검색하면 준수 경계가 적용됩니다. 즉, eDiscovery 관리자는 사용자를 보류할 수 있는 경우에도 사용자의 콘텐츠 위치를 검색할 수 없습니다.

    또한 보류 통계는 기관의 콘텐츠 위치에만 적용됩니다.

- 검색 권한 필터는 Exchange 공용 폴더에 적용되지 않습니다.

## <a name="more-information"></a>추가 정보

- 사서함에 대한 라이선스가 부여되지 않는 경우 Azure AD 특성이 더 이상 사서함에 동기화되지 않습니다. 사서함이 삭제될 때 보류된 경우 사서함에 보존된 콘텐츠는 사서함을 삭제하기 전에 마지막으로 Azure AD 특성을 동기화한 시간을 기준으로 준수 경계 또는 검색 권한 필터의 적용을 받는 것입니다. 

    또한 사서함이 사용이 허가되지 않는 경우 사용자의 사서함과 OneDrive 계정 간의 동기화가 중단됩니다. OneDrive 계정에 대한 준수 특성의 마지막 스탬프된 값은 그대로 유지됩니다.

- 준수 특성은 사용자의 Exchange 사서함에서 OneDrive 계정으로 7일마다 동기화됩니다. 앞서 설명한 것 처럼 이 동기화는 사용자에게 Exchange Online 및 SharePoint Online 라이선스가 모두 할당되어 있으며 사용자의 사서함이 10MB 이상인 경우만 발생합니다.

- 사용자 사서함과 OneDrive 계정에 대해 준수 경계 및 검색 권한 필터가 구현된 경우 해당 OneDrive 계정이 아니라 사용자의 사서함을 삭제하지 않는 것이 좋습니다. 즉, 사용자의 사서함을 삭제하는 경우 사용자의 OneDrive 계정도 제거해야 합니다.

- 사용자에게 둘 이상의 OneDrive 계정이 있을 수 있는 상황(예: 반환 직원)이 있습니다. 이러한 경우 Azure AD의 사용자와 연결된 기본 OneDrive 계정만 동기화됩니다.

- 규정 준수 경계 및 검색 권한 필터는 Exchange, OneDrive 및 SharePoint의 콘텐츠에 스탬프가 적용된 특성 및 이 스탬프된 콘텐츠의 후속 인덱싱에 따라 달라 습니다. 

- 콘텐츠 기반 준수 경계에 제외 필터(예: 검색 권한 필터에서 사용)를 사용하지 `-not()` 않는 것이 좋습니다. 최근에 업데이트된 특성이 있는 콘텐츠가 인덱싱되지 않은 경우 제외 필터를 사용하면 예기치 않은 결과가 발생할 수 있습니다. 

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**검색 권한 필터를 만들고 관리할 수 있는 사람(New-ComplianceSecurityFilter 및 cmdlet을 Set-ComplianceSecurityFilter 수 있나요?**
  
검색 권한 필터를 만들고 보고 수정하려면 보안 및 준수 센터에서 조직 관리 역할 그룹의 구성원 & 합니다.
  
**eDiscovery 관리자가 여러 기관에 걸쳐 있는 둘 이상의 역할 그룹에 할당된 경우 한 기관 또는 다른 기관에서 콘텐츠를 검색하는 방법**
  
eDiscovery 관리자는 검색 쿼리에 특정 기관으로 검색을 제한하는 매개 변수를 추가할 수 있습니다. 예를 들어 조직에서 기관을 차별화하기 위해 **CustomAttribute10** 속성을 지정한 경우 검색 쿼리에 다음을 추가하여 특정 기관의 사서함 및 OneDrive 계정을 검색할 수  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` 있습니다. .
  
**검색 권한 필터에서 준수 특성으로 사용되는 특성 값이 변경되는 경우 어떻게 하나요?**
  
필터에 사용되는 특성 값이 변경되는 경우 검색 권한 필터에서 준수 경계를 적용하는 데 최대 3일이 소요됩니다. 예를 들어 Contoso 시나리오에서 Fourth Coffee 에이전시의 사용자가 Coho Winery 에이전시로 전송되는 경우를 예로 들어 보겠습니다. 따라서 사용자 개체의 **Department** 특성 값이 *FourthCoffee에서* *CohoWinery로 변경됩니다.* 이 경우 Fourth Coffee eDiscovery 및 투자자는 특성이 변경된 후 최대 3일 동안 해당 사용자에 대한 검색 결과를 얻게 됩니다. 마찬가지로 Coho Winery eDiscovery 관리자 및 조사자는 사용자의 검색 결과를 얻기까지 최대 3일이 소요됩니다.
  
**eDiscovery 관리자가 두 개의 별도 규정 준수 경계의 콘텐츠를 볼 수 있나요?**
  
예. 두 기관 모두에 대한 가시성이 있는 역할 그룹에 eDiscovery 관리자를 추가하여 Exchange 사서함을 검색할 때 이 기능을 사용할 수 있습니다. 그러나 SharePoint 사이트 및 OneDrive 계정을 검색할 때 eDiscovery 관리자는 기관이 같은 지역 또는 지리적 위치에 있는 경우 다른 준수 경계에서 콘텐츠를 검색할 수 있습니다. **참고:** SharePoint 및 OneDrive에서 콘텐츠를 검색하는 것은 지리적 위치로 제한되지 않는 고급 eDiscovery에는 이러한 제한이 적용되지 않습니다.
  
**검색 권한 필터가 eDiscovery 사례 보류, Microsoft 365 보존 정책 또는 DLP에 대해 작동합니까?**
  
아니요, 현재는 아니요.
  
**콘텐츠를 내보낼 위치를 제어하는 지역을 지정하지만 해당 지역에 SharePoint 조직이 없는 경우 SharePoint를 검색할 수 있나요?**
  
검색 권한 필터에 지정된 영역이 조직에 없는 경우 기본 지역이 검색됩니다.
  
**조직에서 만들 수 있는 검색 권한 필터의 최대 개수는 무엇입니까?**
  
조직에서 만들 수 있는 검색 권한 필터의 수에는 제한이 없습니다. 그러나 검색 권한 필터가 100개가 넘는 경우 검색 성능에 영향을 미치게 됩니다. 조직의 검색 권한 필터 수를 최대한 적게 유지하려면 Exchange, SharePoint 및 OneDrive에 대한 규칙을 가능한 한 검색 권한 필터로 결합하는 필터를 만듭니다.