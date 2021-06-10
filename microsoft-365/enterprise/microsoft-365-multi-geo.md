---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft 365 Multi-Geo를 사용하여 Microsoft 365 범위를 여러 지리적 지역으로 확장하는 방법을 알아봅니다.
ms.openlocfilehash: 2805470f1a35bb5978f3d25c30aa07523ad21afb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909553"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="dbf3f-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="dbf3f-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="dbf3f-104">Microsoft 365 Multi-Geo를 사용하면 Microsoft 365 범위를 기존 테넌트 내 여러 지리적 지역 및 / 또는 국가로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="dbf3f-105">Microsoft 계정 팀에 문의하여 Microsoft 365 Multi-Geo용 Multi-National Company에 등록하세요.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="dbf3f-106">Microsoft 365 Multi-Geo를 사용하여 데이터 상주 요구 사항을 충족하기 위해 선택한 지리적 위치의 미사용 데이터를 프로비저닝 및 저장하고, 동시에 귀하의 전 세계 작업자들이 최신 생산성 환경을 활용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

<span data-ttu-id="dbf3f-107">Microsoft 365 Multi-Geo에 대한 비디오 소개는 [SharePoint Online 및 OneDrive Multi-Geo에서 데이터 위치](https://www.youtube.com/watch?v=Do9U3JuROhk)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-107">For a video introduction to Microsoft 365 Multi-Geo, see [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).</span></span>

## <a name="multi-geo-architecture"></a><span data-ttu-id="dbf3f-108">Multi-Geo 아키텍처</span><span class="sxs-lookup"><span data-stu-id="dbf3f-108">Multi-Geo architecture</span></span>

<span data-ttu-id="dbf3f-109">Multi-Geo 환경에서 Microsoft 365 테넌트는 중앙 위치(Microsoft 365 구독이 원래 제공되었던 위치)와 하나 이상의 위성 위치로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-109">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="dbf3f-110">Multi-Geo 테넌트의 경우 지리적 위치, 그룹 및 사용자 정보에 대한 정보는 Azure Active Directory(AAD)에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-110">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="dbf3f-111">테넌트 정보가 중앙에서 관리되고 각 지리적 위치와 동기화되기 때문에 회사의 모든 사람과 관련된 공유 및 경험은 전역 세계적으로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-111">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![SharePoint 관리 센터의 Multi-Geo 지도 스크린샷](../media/multi-geo-world-map.png)

<span data-ttu-id="dbf3f-113">참고로, Microsoft 365 Multi-Geo는 성능 최적화를 위해 설계되지 않았고 데이터 상주 요구 사항을 충족하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-113">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="dbf3f-114">Microsoft 365의 성능 최적화에 대한 자세한 내용은 [Microsoft 365의 네트워크 계획 및 성능 조정](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)을 참조하거나 지원 그룹에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-114">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="dbf3f-115">용어</span><span class="sxs-lookup"><span data-stu-id="dbf3f-115">Terminology</span></span>

<span data-ttu-id="dbf3f-116">다음은 Microsoft 365 Multi-Geo를 설명하는 데 사용되는 주요 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-116">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="dbf3f-117">**중앙 위치** - 테넌트가 원래 프로비저닝된 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="dbf3f-117">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="dbf3f-118">**지역 관리자** - 하나 이상의 지정된 위성 위치를 관리할 수 있는 관리자</span><span class="sxs-lookup"><span data-stu-id="dbf3f-118">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="dbf3f-119">**지역 코드** - 주어직 지리적 위치에 대한 세 자리 코드</span><span class="sxs-lookup"><span data-stu-id="dbf3f-119">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="dbf3f-120">**지리적 위치** – Exchange 우편함 및 OneDrive 및 SharePoint 사이트를 포함하여 데이터를 호스팅하기 위해 Multi-Geo 테넌트에서 사용할 수있는 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="dbf3f-120">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="dbf3f-121">**선호 하는 데이터 위치 (PDL)** - 사용자가 Exchange 사서함과 OneDrive를 프로비저닝하는 위치를 나타내는 관리자가 설정한 사용자 속성</span><span class="sxs-lookup"><span data-stu-id="dbf3f-121">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="dbf3f-122">또한 PDL은 사용자가 만든 SharePoint 사이트가 프로비저닝되는 위치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-122">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="dbf3f-123">**위성 위치** - 지리적 인식 Microsoft 365 작업(SharePoint, OneDrive 및 Exchange)이 Multi-Geo 테넌트에서 사용하도록 설정된 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="dbf3f-123">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="dbf3f-124">**테넌트** – Microsoft 365에서 일반적으로 하나 이상의 도메인에 연결되어 있는 조직을 나타내는 표현(예: contoso.com)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-124">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="dbf3f-125">라이선싱</span><span class="sxs-lookup"><span data-stu-id="dbf3f-125">Licensing</span></span>

<span data-ttu-id="dbf3f-126">Microsoft 365 Multi-Geo는 테넌트에 최소 Microsoft 365 사용자 수가 250명 이상인 기업계약 고객을 위한 다음 Microsoft 365 구독 계획에 대한 추가 기능으로 사용할 수 있으며, 이러한 사용자 중 최소 5%는 Multi-Geo를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-126">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for Enterprise Agreement customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="dbf3f-127">사용자 구독 라이선스는 Multi-Geo Services 기업계약 동일한 라이선스에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-127">User subscription licenses must be on the same Enterprise Agreement as the Multi-Geo Services licenses.</span></span> <span data-ttu-id="dbf3f-128">자세한 내용은 Microsoft 계정 팀에 문의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-128">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="dbf3f-129">Microsoft 365 F1, F3, E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="dbf3f-129">Microsoft 365 F1, F3, E3, or E5</span></span>
- <span data-ttu-id="dbf3f-130">Office 365 F3, E1, E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="dbf3f-130">Office 365 F3, E1, E3, or E5</span></span>
- <span data-ttu-id="dbf3f-131">온라인 계획 1 또는 계획 2 교환</span><span class="sxs-lookup"><span data-stu-id="dbf3f-131">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="dbf3f-132">OneDrive for Business 계획 1 또는 계획 2</span><span class="sxs-lookup"><span data-stu-id="dbf3f-132">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="dbf3f-133">SharePoint Online 계획 1 또는 계획 2</span><span class="sxs-lookup"><span data-stu-id="dbf3f-133">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="dbf3f-134">Microsoft 365 Multi-Geo 사용 가능 여부</span><span class="sxs-lookup"><span data-stu-id="dbf3f-134">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="dbf3f-135">Microsoft 365 Multi-Geo는 현재 다음 지역 및 국가에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-135">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="dbf3f-136">시작하기</span><span class="sxs-lookup"><span data-stu-id="dbf3f-136">Getting started</span></span>

<span data-ttu-id="dbf3f-137">Multi-Geo를 시작하려면 이러한 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-137">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="dbf3f-138">계정 팀과 협의하여 _Microsoft 365의 Multi-Geo 기능_ 서비스 계획을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-138">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="dbf3f-139">계정 팀이 필요한 라이센스 수를 추가할 수 있도록 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-139">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="dbf3f-140">Multi-Geo 기능은 Microsoft 365 구독을 250개 이상 보유한 EA 고객에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-140">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="dbf3f-141">Microsoft 365 Multi-Geo를 사용하여 시작하기 전에 Microsoft에서는 Multi-Geo 지원을 위해 Exchange Online 테넌트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-141">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="dbf3f-142">이 일회성 구성 프로세스는 *Microsoft 365의 Multi-Geo 기능* 서비스 계획을 주문하고 테넌트에 라이선스가 표시된 후에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-142">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="dbf3f-143">테넌트가 각 워크로드에 대한 구성 [프로세스를](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) 완료하고 나면 Microsoft 365 메시지 센터에서 작업별 알림을 받게 되면 Microsoft 365 Multi-Geo 기능 구성 및 사용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-143">You will receive workload-specific notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your tenant has completed the configuration process for each workload, and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span> <span data-ttu-id="dbf3f-144">Multi-Geo 지원을 위해 테넌트를 구성하는 데 필요한 시간은 테넌트마다 다르지만 대부분의 테넌트는 기능 라이센스를 받은 후 한 달 내에 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-144">The time required to configure a tenant for Multi-Geo support varies from tenant to tenant, but most tenants finish within a month after receipt of the feature licenses.</span></span> <span data-ttu-id="dbf3f-145">더 크거나 더 복잡한 테넌트는 구성 프로세스를 완료하는 데 더 많은 시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-145">Larger or more complex tenants may require more time to complete the configuration process.</span></span> <span data-ttu-id="dbf3f-146">필요한 경우 특정 테넌트에 대한 자세한 내용은 계정 팀에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-146">Please contact your account team for details on your specific tenant should you require it.</span></span>

2. <span data-ttu-id="dbf3f-147">[Multi-Geo 환경 계획](plan-for-multi-geo.md)을 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-147">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="dbf3f-148">[Multi-Geo 환경 관리](administering-a-multi-geo-environment.md) 및 [사용자가 환경을 경험하는 방법](multi-geo-user-experience.md)에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-148">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="dbf3f-149">Microsoft 365 Multi-Geo를 설치할 준비가 되면 [Multi-Geo의 테넌트를 구성합니다](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="dbf3f-149">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="dbf3f-150">[검색 설정](configure-search-for-multi-geo.md)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-150">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dbf3f-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbf3f-151">See also</span></span>

[<span data-ttu-id="dbf3f-152">Exchange Online 및 OneDrive의 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="dbf3f-152">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="dbf3f-153">OneDrive 및 SharePoint Online의 Multi-Geo 기능</span><span class="sxs-lookup"><span data-stu-id="dbf3f-153">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="dbf3f-154">Exchange Online의 Multi-Geo 기능</span><span class="sxs-lookup"><span data-stu-id="dbf3f-154">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="dbf3f-155">Multi-Geo 환경의 Teams 작업 환경</span><span class="sxs-lookup"><span data-stu-id="dbf3f-155">Teams experience in a multi-geo environment</span></span>](/microsoftteams/teams-experience-o365odb-spo-multi-geo)