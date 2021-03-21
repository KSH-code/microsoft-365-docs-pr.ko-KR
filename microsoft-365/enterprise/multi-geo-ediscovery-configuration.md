---
title: Microsoft 365 Multi-Geo eDiscovery 구성
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Region 매개 변수를 사용하여 Microsoft 365 Multi-Geo의 위성 위치에서 사용하도록 eDiscovery를 구성하는 방법을 학습합니다.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923723"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="5a079-103">Microsoft 365 Multi-Geo eDiscovery 구성</span><span class="sxs-lookup"><span data-stu-id="5a079-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="5a079-104">[고급 eDiscovery](../compliance/overview-ediscovery-20.md) 기능을 사용하면 다중 지역 eDiscovery 관리자가 "지역" 보안 필터를 사용할 필요 없이 모든 지역을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-104">[Advanced eDiscovery capabilities](../compliance/overview-ediscovery-20.md) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="5a079-105">데이터는 다중 위치 테넌트의 중앙 위치의 Azure 인스턴스로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="5a079-106">고급 eDiscovery 기능이 없는 경우 다중 위치 테넌트의 eDiscovery 관리자 또는 관리자는 해당 테넌트의 중앙 위치에서만 eDiscovery를 수행 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="5a079-107">위성 위치에 대한 eDiscovery 수행 기능을 지원하기 위해 PowerShell을 통해 "Region"이라는 새로운 준수 보안 필터 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="5a079-108">이 매개 변수는 중앙 위치가 북미, 유럽 또는 아시아 태평양에 있는 테넌트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="5a079-109">Advanced eDiscovery는 중앙 위치가 북미, 유럽 또는 아시아 태평양에 있지 않은 테넌트와 위성 지리적 위치에서 eDiscovery를 수행해야 하는 테넌트에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="5a079-110">Microsoft 365 전역 관리자는 다른 사용자들이 eDiscovery를 수행할 수 있도록 하기 위해 eDiscovery 관리자 권한을 할당해야 하며, 해당 준수 보안 필터에서 “Region” 매개 변수를 할당하여 eDiscovery 수행 지역을 위성 위치로 지정해야 합니다. 그렇지 않으면 해당 위성 위치에 대해 eDiscovery가 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="5a079-p103">특정 위성 위치에 대해 eDiscovery 관리자(manager) 또는 관리자(administrator) 역할이 설정되면 해당 eDiscovery 관리자(manager) 또는 관리자(administrator)만 해당 위성 위치에 있는 SharePoint 사이트 및 OneDrive 사이트에 대해 eDiscovery 검색 작업을 수행할 수 있습니다. eDiscovery 관리자(manager) 또는 관리자(administrator)가 지정된 위성 위치 외부의 SharePoint 또는 OneDrive 사이트를 검색하려고 하면 결과가 반환되지 않습니다. 또한 지역에 대한 eDiscovery 관리자(manager) 또는 관리자(administrator)가 내보내기를 트리거할 경우 데이터가 해당 지역의 Azure 인스턴스로 내보내집니다. 이를 통해 제어 경계 너머로 콘텐츠가 내보내지지 않게 되므로 조직은 준수 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-p103">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location. If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned. Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region. This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="5a079-115">eDiscovery 관리자가 여러 SharePoint 위성 위치에 걸쳐 검색해야 할 경우 OneDrive 또는 SharePoint 사이트가 있는 대체 위성 위치를 지정하는 eDiscovery 관리자에 대해 다른 사용자 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="5a079-116">지역에 대한 준수 보안 필터를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="5a079-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="5a079-117">Microsoft 365 보안 및 준수 센터 PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="5a079-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="5a079-118">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a079-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="5a079-119">예시는 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="5a079-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="5a079-120">추가 매개 변수 및 구문에 대해서는 [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a079-120">See the [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>