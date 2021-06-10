---
title: SharePoint 2013용 Microsoft Azure 아키텍처
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 98fc1006-9399-4ff0-a216-c7c05820d822
description: SharePoint 가상 SharePoint 호스트할 수 있는 Microsoft Azure 솔루션 유형과 호스트할 Azure를 설정하는 방법을 설명합니다.
ms.openlocfilehash: eed74e2dcbe383f0f63e7f6ea2fc70fe7b51b1b3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924179"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a><span data-ttu-id="a3ba0-103">SharePoint 2013용 Microsoft Azure 아키텍처</span><span class="sxs-lookup"><span data-stu-id="a3ba0-103">Microsoft Azure Architectures for SharePoint 2013</span></span>

<span data-ttu-id="a3ba0-104">Azure는 SharePoint Server 2013 솔루션을 호스팅하기에 좋은 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-104">Azure is a good environment for hosting a SharePoint Server 2013 solution.</span></span> <span data-ttu-id="a3ba0-105">대부분의 경우 권장되는 Microsoft 365 Azure에서 호스팅되는 SharePoint 서버 팜은 특정 솔루션에 대한 좋은 옵션일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-105">In most cases, we recommend Microsoft 365, but a SharePoint Server farm hosted in Azure can be a good option for specific solutions.</span></span> <span data-ttu-id="a3ba0-106">이 문서에서는 Azure 플랫폼에 적합한 SharePoint 솔루션을 설계하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-106">This article describes how to architect SharePoint solutions so they are a good fit in the Azure platform.</span></span> <span data-ttu-id="a3ba0-107">예를 들어 다음과 같은 두 가지 특정 솔루션이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-107">The following two specific solutions are used as examples:</span></span>
  
- [<span data-ttu-id="a3ba0-108">Microsoft Azure에서 SharePoint Server 2013 재해 복구</span><span class="sxs-lookup"><span data-stu-id="a3ba0-108">SharePoint Server 2013 Disaster Recovery in Microsoft Azure</span></span>](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [<span data-ttu-id="a3ba0-109">SharePoint Server 2013을 사용하는 Microsoft Azure의 인터넷 사이트</span><span class="sxs-lookup"><span data-stu-id="a3ba0-109">Internet Sites in Microsoft Azure using SharePoint Server 2013</span></span>](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a><span data-ttu-id="a3ba0-110">Azure 인프라 SharePoint 권장 솔루션</span><span class="sxs-lookup"><span data-stu-id="a3ba0-110">Recommended SharePoint solutions for Azure Infrastructure Services</span></span>

<span data-ttu-id="a3ba0-111">Azure 인프라 서비스는 클라우드 솔루션을 호스팅하기 위한 SharePoint 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-111">Azure infrastructure services is a compelling option for hosting SharePoint solutions.</span></span> <span data-ttu-id="a3ba0-112">일부 솔루션은 다른 솔루션보다 이 플랫폼에 더 잘 맞습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-112">Some solutions are a better fit for this platform than others.</span></span> <span data-ttu-id="a3ba0-113">다음 표에서는 권장 해결법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-113">The following table shows recommended solutions.</span></span>
  
|<span data-ttu-id="a3ba0-114">**솔루션**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-114">**Solution**</span></span>|<span data-ttu-id="a3ba0-115">**Azure에 이 솔루션이 권장되는 이유**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-115">**Why this solution is recommended for Azure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3ba0-116">개발 및 테스트 환경</span><span class="sxs-lookup"><span data-stu-id="a3ba0-116">Development and test environments</span></span>  <br/> |<span data-ttu-id="a3ba0-117">이러한 환경은 쉽게 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-117">It's easy to create and manage these environments.</span></span>  <br/> |
|<span data-ttu-id="a3ba0-118">Azure로의 SharePoint 팜의 재해 복구</span><span class="sxs-lookup"><span data-stu-id="a3ba0-118">Disaster recovery of on-premises SharePoint farms to Azure</span></span>  <br/> |<span data-ttu-id="a3ba0-119">**호스팅된 보조 데이터 센터** 다른 지역의 보조 데이터 센터에 투자하는 대신 Azure를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-119">**Hosted secondary datacenter** Use Azure instead of investing in a secondary datacenter in a different region.</span></span> <br/> <span data-ttu-id="a3ba0-120">**낮은 비용의 재해 복구 환경** 프레미스 재해 복구 환경보다 적은 수의 리소스를 유지 관리하고 비용을 지불합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-120">**Lower-cost disaster-recovery environments** Maintain and pay for fewer resources than an on-premises disaster recovery environment.</span></span> <span data-ttu-id="a3ba0-121">리소스 수는 콜드 대기, 웜 대기 또는 핫 대기 중 선택하는 재해 복구 환경에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-121">The number of resources depends on the disaster recovery environment you choose: cold standby, warm standby, or hot standby.</span></span> <br/> <span data-ttu-id="a3ba0-122">**보다 탄력적인 플랫폼** 재해가 발생하면 팜에서 복구를 SharePoint 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-122">**More elastic platform** In the event of a disaster, easily scale-out your recovery SharePoint farm to meet load requirements.</span></span> <span data-ttu-id="a3ba0-123">리소스가 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-123">Scale in when you no longer need the resources.</span></span> <br/> <span data-ttu-id="a3ba0-124">에서 [SharePoint Server 2013 재해 복구를 Microsoft Azure.](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)</span><span class="sxs-lookup"><span data-stu-id="a3ba0-124">See [SharePoint Server 2013 Disaster Recovery in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).</span></span>  <br/> |
|<span data-ttu-id="a3ba0-125">기능 및 규모를 사용하는 인터넷 연결 사이트는 사이트에서 사용할 수 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3ba0-125">Internet-facing sites that use features and scale not available in Microsoft 365</span></span>  <br/> |<span data-ttu-id="a3ba0-126">**노력에 집중** 인프라를 구축하는 대신 멋진 사이트를 구축하는 데 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-126">**Focus your efforts** Concentrate on building a great site rather than building infrastructure.</span></span> <br/> <span data-ttu-id="a3ba0-127">**Azure에서 탄력성 활용** 새 서버를 추가하여 수요에 따라 팜의 크기를 설정하고 필요한 리소스만 지불합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-127">**Take advantage of elasticity in Azure** Size the farm for the demand by adding new servers, and pay only for resources you need.</span></span> <span data-ttu-id="a3ba0-128">동적 컴퓨터 할당은 지원되지 않습니다(자동 크기 조정).</span><span class="sxs-lookup"><span data-stu-id="a3ba0-128">Dynamic machine allocation is not supported (auto scale).</span></span> <br/> <span data-ttu-id="a3ba0-129">**AD Azure Active Directory 사용** 고객 계정에 대해 Azure AD를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-129">**Use Azure Active Directory (AD)** Take advantage of Azure AD for customer accounts.</span></span> <br/> <span data-ttu-id="a3ba0-130">**다른 SharePoint 사용할** 수 없는 추가 Microsoft 365 심층 보고 및 웹 분석을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-130">**Add SharePoint functionality not available in Microsoft 365** Add deep reporting and web analytics.</span></span> <br/> <span data-ttu-id="a3ba0-131">Microsoft Azure Server [2013을 SharePoint 인터넷 사이트를 참조합니다.](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)</span><span class="sxs-lookup"><span data-stu-id="a3ba0-131">See [Internet Sites in Microsoft Azure using SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md).</span></span>  <br/> |
|<span data-ttu-id="a3ba0-132">앱 또는 Microsoft 365 환경을 지원하기 위한 앱 팜</span><span class="sxs-lookup"><span data-stu-id="a3ba0-132">App farms to support Microsoft 365 or on-premises environments</span></span>  <br/> |<span data-ttu-id="a3ba0-133">**Azure에서** 앱을 빌드, 테스트 및 호스트하여 사내 환경과 클라우드 환경을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-133">**Build, test, and host apps** in Azure to support both on-premises and cloud environments.</span></span> <br/> <span data-ttu-id="a3ba0-134">**Azure에서** 이 역할을 호스트하는 대신, 사내 환경의 새 하드웨어를 구입하세요.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-134">**Host this role** in Azure instead of buying new hardware for on-premises environments.</span></span> <br/> |
   
<span data-ttu-id="a3ba0-135">인트라넷 및 공동 작업 솔루션 및 워크로드의 경우 다음 옵션을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-135">For intranet and collaboration solutions and workloads, consider the following options:</span></span>
  
- <span data-ttu-id="a3ba0-136">비즈니스 Microsoft 365 충족하는지 아니면 솔루션의 일부가 될 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-136">Determine if Microsoft 365 meets your business requirements or can be part of the solution.</span></span> <span data-ttu-id="a3ba0-137">Microsoft 365 항상 최신으로 유지되는 다양한 기능 집합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-137">Microsoft 365 provides a rich feature set that is always up to date.</span></span>
    
- <span data-ttu-id="a3ba0-138">모든 Microsoft 365 충족하지 않는 경우 MCS(Microsoft Consulting Services)에서 SharePoint 2013의 표준 구현을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-138">If Microsoft 365 does not meet all your business requirements, consider a standard implementation of SharePoint 2013 on premises from Microsoft Consulting Services (MCS).</span></span> <span data-ttu-id="a3ba0-139">표준 아키텍처는 사용자 지정된 아키텍처보다 더 빠르고 저렴한 솔루션이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-139">A standard architecture can be a quicker, cheaper, and easier solution for you to support than a customized one.</span></span> 
    
- <span data-ttu-id="a3ba0-140">표준 구현이 비즈니스 요구 사항을 충족하지 않는 경우 사용자 지정된 사내 솔루션을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-140">If a standard implementation doesn't meet your business requirements, consider a customized on-premises solution.</span></span>
    
- <span data-ttu-id="a3ba0-141">비즈니스 요구 사항에 클라우드 플랫폼을 사용하는 것이 중요한 경우 Azure 인프라 서비스에서 호스팅되는 SharePoint 2013의 표준 또는 사용자 지정 구현을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-141">If using a cloud platform is important for your business requirements, consider a standard or customized implementation of SharePoint 2013 hosted in Azure infrastructure services.</span></span> <span data-ttu-id="a3ba0-142">SharePoint 솔루션은 다른 기본이 아닌 Microsoft 공용 클라우드 플랫폼보다 Azure에서 훨씬 더 쉽게 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-142">SharePoint solutions are much easier to support in Azure than other non-native Microsoft public cloud platforms.</span></span>
    
## <a name="before-you-design-the-azure-environment"></a><span data-ttu-id="a3ba0-143">Azure 환경을 디자인하기 전에</span><span class="sxs-lookup"><span data-stu-id="a3ba0-143">Before you design the Azure environment</span></span>

<span data-ttu-id="a3ba0-144">이 문서에서는 예제 SharePoint 토폴로지의 경우 이러한 디자인 개념을 모든 팜 토폴로지에서 사용할 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-144">While this article uses example SharePoint topologies, you can use these design concepts with any SharePoint farm topology.</span></span> <span data-ttu-id="a3ba0-145">Azure 환경을 디자인하기 전에 다음 토폴로지, 아키텍처, 용량 및 성능 지침을 사용하여 SharePoint 팜을 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-145">Before you design the Azure environment, use the following topology, architecture, capacity, and performance guidance to design the SharePoint farm:</span></span>
  
- [<span data-ttu-id="a3ba0-146">2013 IT SharePoint 아키텍처 디자인</span><span class="sxs-lookup"><span data-stu-id="a3ba0-146">Architecture design for SharePoint 2013 IT pros</span></span>](/SharePoint/technical-reference/technical-diagrams)
    
- [<span data-ttu-id="a3ba0-147">SharePoint Server 2013에서 성능 및 용량 관리 계획</span><span class="sxs-lookup"><span data-stu-id="a3ba0-147">Plan for performance and capacity management in SharePoint Server 2013</span></span>](/SharePoint/administration/performance-planning-in-sharepoint-server-2013)
    
## <a name="determine-the-active-directory-domain-type"></a><span data-ttu-id="a3ba0-148">Active Directory 도메인 유형 확인</span><span class="sxs-lookup"><span data-stu-id="a3ba0-148">Determine the Active Directory domain type</span></span>

<span data-ttu-id="a3ba0-149">각 SharePoint 서버 팜은 Active Directory를 통해 팜 설정에 대한 관리 계정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-149">Each SharePoint Server farm relies on Active Directory to provide administrative accounts for farm setup.</span></span> <span data-ttu-id="a3ba0-150">현재 Azure의 여러 솔루션에 SharePoint 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-150">At this time, there are two options for SharePoint solutions in Azure.</span></span> <span data-ttu-id="a3ba0-151">이는 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-151">These are described in the following table.</span></span>
  
|<span data-ttu-id="a3ba0-152">**옵션**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-152">**Option**</span></span>|<span data-ttu-id="a3ba0-153">**설명**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3ba0-154">전용 도메인</span><span class="sxs-lookup"><span data-stu-id="a3ba0-154">Dedicated domain</span></span>  <br/> |<span data-ttu-id="a3ba0-155">Azure에 격리된 전용 Active Directory 도메인을 배포하여 사용자 팜을 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-155">You can deploy a dedicated and isolated Active Directory domain to Azure to support your SharePoint farm.</span></span> <span data-ttu-id="a3ba0-156">공용 인터넷 사이트에는 이 선택이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-156">This is a good choice for public-facing Internet sites.</span></span>  <br/> |
|<span data-ttu-id="a3ba0-157">크로스-프레미스 연결을 통해 사내 도메인 확장</span><span class="sxs-lookup"><span data-stu-id="a3ba0-157">Extend the on-premises domain through a cross-premises connection</span></span>  <br/> |<span data-ttu-id="a3ba0-158">크로스-프레미스 연결을 통해 사내 도메인을 확장하면 사용자는 인트라넷을 통해 호스트된 SharePoint 팜에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-158">When you extend the on-premises domain through a cross-premises connection, users access the SharePoint farm via your intranet as if it were hosted on-premises.</span></span> <span data-ttu-id="a3ba0-159">프레미스 Active Directory 및 DNS 구현을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-159">You can take advantage of your on-premises Active Directory and DNS implementation.</span></span>  <br/> <span data-ttu-id="a3ba0-160">Azure에서 재해 복구 환경을 구축하려면 프레미스 간 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-160">A cross-premises connection is required for building a disaster-recovery environment in Azure to fail over to from your on-premises farm.</span></span>  <br/> |
   
<span data-ttu-id="a3ba0-161">이 문서에는 크로스-프레미스 연결을 통해 사내 도메인을 확장하기 위한 디자인 개념이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-161">This article includes design concepts for extending the on-premises domain through a cross-premises connection.</span></span> <span data-ttu-id="a3ba0-162">솔루션에서 전용 도메인을 사용하는 경우 프레미스 간 연결이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-162">If your solution uses a dedicated domain, you don't need a cross-premises connection.</span></span>
  
## <a name="design-the-virtual-network"></a><span data-ttu-id="a3ba0-163">가상 네트워크 디자인</span><span class="sxs-lookup"><span data-stu-id="a3ba0-163">Design the virtual network</span></span>

<span data-ttu-id="a3ba0-164">먼저 Azure에 가상 컴퓨터를 두는 서브넷이 포함된 가상 네트워크가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-164">First you need a virtual network in Azure, which includes subnets on which you will place your virtual machines.</span></span> <span data-ttu-id="a3ba0-165">가상 네트워크에는 서브넷에 할당하는 개인 IP 주소 공간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-165">The virtual network needs a private IP address space, portions of which you assign to the subnets.</span></span>
  
<span data-ttu-id="a3ba0-166">크로스-프레미스 연결을 통해 Azure로 사내 네트워크를 확장하는 경우(재해 복구 환경에 필요) 조직 네트워크의 다른 곳에서 아직 사용되지 않는 개인 주소 공간을 선택해야 합니다. 여기에는 사내 환경 및 기타 Azure Virtual Network가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-166">If you are extending your on-premises network to Azure through a cross-premises connection (required for a disaster recovery environment), you must choose a private address space that is not already in use elsewhere in your organization network, which can include your on-premises environment and other Azure virtual networks.</span></span> 
  
<span data-ttu-id="a3ba0-167">**그림 1: Azure의 가상 네트워크가 있는 사내 환경**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-167">**Figure 1: On-premises environment with a virtual network in Azure**</span></span>

![Microsoft Azure 솔루션에 대한 가상 네트워크 SharePoint 있습니다.](../media/OPrrasconWA-AZarch.png)
  
<span data-ttu-id="a3ba0-171">다음은 이 다이어그램에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-171">In this diagram:</span></span>
  
- <span data-ttu-id="a3ba0-172">Azure의 가상 네트워크는 사내 환경과 나란히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-172">A virtual network in Azure is illustrated side-by-side to the on-premises environment.</span></span> <span data-ttu-id="a3ba0-173">두 환경은 사이트 간 VPN 연결 또는 ExpressRoute일 수 있는 프레미스 간 연결로 아직 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-173">The two environments are not yet connected by a cross-premises connection, which can be a site-to-site VPN connection or ExpressRoute.</span></span>
    
- <span data-ttu-id="a3ba0-174">이때 가상 네트워크는 서브넷만 포함하며 다른 아키텍처 요소는 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-174">At this point, the virtual network just includes the subnets and no other architectural elements.</span></span> <span data-ttu-id="a3ba0-175">하나의 서브넷은 Azure 게이트웨이를 호스트하고 다른 서브넷은 SharePoint 팜의 계층을 호스트하고 Active Directory 및 DNS에 대한 추가 서브넷을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-175">One subnet will host the Azure gateway and other subnets host the tiers of the SharePoint farm, with an additional one for Active Directory and DNS.</span></span>
    
## <a name="add-cross-premises-connectivity"></a><span data-ttu-id="a3ba0-176">크로스-프레미스 연결 추가</span><span class="sxs-lookup"><span data-stu-id="a3ba0-176">Add cross-premises connectivity</span></span>

<span data-ttu-id="a3ba0-177">다음 배포 단계는 프레미스 간 연결을 만드는 것입니다(솔루션에 적용되는 경우).</span><span class="sxs-lookup"><span data-stu-id="a3ba0-177">The next deployment step is to create the cross-premises connection (if this applies to your solution).</span></span> <span data-ttu-id="a3ba0-178">크로스-프레미스 연결의 경우 Azure 게이트웨이는 별도의 게이트웨이 서브넷에 있으며 주소 공간을 만들고 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-178">For cross-premises connections, a Azure gateway resides in a separate gateway subnet, which you must create and assign an address space.</span></span> 
  
<span data-ttu-id="a3ba0-179">크로스-프레미스 연결을 계획할 때 Azure 게이트웨이 및 연결은 정의하고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-179">When you plan for a cross-premises connection, you define and create an Azure gateway and connection to an on-premises gateway device.</span></span>
  
<span data-ttu-id="a3ba0-180">**그림 2: Azure 게이트웨이 및 사내 게이트웨이 장치를 사용하여 사내 환경과 Azure 간에 사이트 간 연결을 제공합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-180">**Figure 2: Using an Azure gateway and an on-premises gateway device to provide site-to-site connectivity between the on-premises environment and Azure**</span></span>

![사이트 간 VPN 연결 또는 ExpressRoute일 수 있는 프레미스 간 연결을 통해 Azure Virtual Network에 연결된 사내 환경](../media/AZarch-VPNgtwyconnct.png)
  
<span data-ttu-id="a3ba0-182">다음은 이 다이어그램에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-182">In this diagram:</span></span>
  
- <span data-ttu-id="a3ba0-183">이전 다이어그램에 추가하면, 사이트 간 VPN 연결 또는 ExpressRoute일 수 있는 프레미스 간 연결을 통해 Azure Virtual Network에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-183">Adding to the previous diagram, the on-premises environment is connected to the Azure virtual network by a cross-premise connection, which can be a site-to-site VPN connection or ExpressRoute.</span></span>
    
- <span data-ttu-id="a3ba0-184">Azure 게이트웨이가 게이트웨이 서브넷에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-184">An Azure gateway is on a gateway subnet.</span></span>
    
- <span data-ttu-id="a3ba0-185">사내 환경에는 라우터 또는 VPN 서버와 같은 게이트웨이 장치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-185">The on-premises environment includes a gateway device, such as a router or VPN server.</span></span>
    
<span data-ttu-id="a3ba0-186">프레미스 간 가상 네트워크를 계획하고 만드는 자세한 내용은 커넥트 가상 네트워크에 대한 Microsoft Azure [참조하세요.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)</span><span class="sxs-lookup"><span data-stu-id="a3ba0-186">For additional information to plan for and create a cross-premises virtual network, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a><span data-ttu-id="a3ba0-187">AD DS(Active Directory 도메인 서비스) 및 DNS 추가</span><span class="sxs-lookup"><span data-stu-id="a3ba0-187">Add Active Directory Domain Services (AD DS) and DNS</span></span>

<span data-ttu-id="a3ba0-188">Azure의 재해 복구를 위해 Windows Server AD와 DNS를 모두 배포하는 하이브리드 시나리오에서 Windows Server AD를 배포하고 Azure Virtual Machines에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-188">For disaster recovery in Azure, you deploy Windows Server AD and DNS in a hybrid scenario where Windows Server AD is deployed both on-premises and on Azure virtual machines.</span></span>
  
<span data-ttu-id="a3ba0-189">**그림 3: 하이브리드 Active Directory 도메인 구성**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-189">**Figure 3: Hybrid Active Directory domain configuration**</span></span>

![Azure Virtual Network에 배포된 STwo 가상 컴퓨터 및 SharePoint 팜 서브넷은 복제본 도메인 컨트롤러 및 DNS 서버입니다.](../media/AZarch-HyADdomainConfig.png)
  
<span data-ttu-id="a3ba0-191">이 다이어그램은 Windows 서버 AD 및 DNS 서브넷에 두 가상 컴퓨터를 추가하여 이전 다이어그램을 토대합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-191">This diagram builds on the previous diagrams by adding two virtual machines to a Windows Server AD and DNS subnet.</span></span> <span data-ttu-id="a3ba0-192">이러한 가상 컴퓨터는 복제본 도메인 컨트롤러 및 DNS 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-192">These virtual machines are replica domain controllers and DNS servers.</span></span> <span data-ttu-id="a3ba0-193">이는 서버 AD 환경의 Windows 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-193">They are an extension of the on-premises Windows Server AD environment.</span></span> 
  
<span data-ttu-id="a3ba0-194">다음 표에서는 Azure의 이러한 가상 머신에 대한 구성 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-194">The following table provides configuration recommendations for these virtual machines in Azure.</span></span> <span data-ttu-id="a3ba0-195">Azure 환경이 프레미스 환경과 통신하지 않는 전용 도메인의 경우에도 사용자 환경을 디자인하기 위한 시작점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-195">Use these as a starting point for designing your own environment—even for a dedicated domain where your Azure environment doesn't communicate with your on-premises environment.</span></span>
  
|<span data-ttu-id="a3ba0-196">**항목**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-196">**Item**</span></span>|<span data-ttu-id="a3ba0-197">**구성**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-197">**Configuration**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3ba0-198">Azure의 가상 컴퓨터 크기</span><span class="sxs-lookup"><span data-stu-id="a3ba0-198">Virtual machine size in Azure</span></span>  <br/> |<span data-ttu-id="a3ba0-199">표준 계층의 A1 또는 A2 크기</span><span class="sxs-lookup"><span data-stu-id="a3ba0-199">A1 or A2 size in the Standard tier</span></span>  <br/> |
|<span data-ttu-id="a3ba0-200">운영 체제</span><span class="sxs-lookup"><span data-stu-id="a3ba0-200">Operating system</span></span>  <br/> |<span data-ttu-id="a3ba0-201">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a3ba0-201">Windows Server 2012 R2</span></span>  <br/> |
|<span data-ttu-id="a3ba0-202">Active Directory 역할</span><span class="sxs-lookup"><span data-stu-id="a3ba0-202">Active Directory role</span></span>  <br/> |<span data-ttu-id="a3ba0-203">글로벌 카탈로그 서버로 지정된 AD DS 도메인 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-203">AD DS domain controller designated as a global catalog server.</span></span> <span data-ttu-id="a3ba0-204">이 구성을 통해 크로스-프레미스 연결을 통해 트래픽을 내보내게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-204">This configuration reduces egress traffic across the cross-premises connection.</span></span>  <br/> <span data-ttu-id="a3ba0-205">변경률이 높은 다중 도메인 환경에서(일반적이지 않은 경우) 복제 트래픽을 줄이기 위해 Azure의 글로벌 카탈로그 서버와 동기화되지 않는 도메인 컨트롤러를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-205">In a multidomain environment with high rates of change (this is not common), configure domain controllers on premises not to sync with the global catalog servers in Azure, to reduce replication traffic.</span></span>  <br/> |
|<span data-ttu-id="a3ba0-206">DNS 역할</span><span class="sxs-lookup"><span data-stu-id="a3ba0-206">DNS role</span></span>  <br/> |<span data-ttu-id="a3ba0-207">도메인 컨트롤러에 DNS Server 서비스를 설치하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-207">Install and configure the DNS Server service on the domain controllers.</span></span>  <br/> |
|<span data-ttu-id="a3ba0-208">데이터 디스크</span><span class="sxs-lookup"><span data-stu-id="a3ba0-208">Data disks</span></span>  <br/> |<span data-ttu-id="a3ba0-209">Active Directory 데이터베이스, 로그 및 SYSVOL을 추가 Azure 데이터 디스크에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-209">Place the Active Directory database, logs, and SYSVOL on additional Azure data disks.</span></span> <span data-ttu-id="a3ba0-210">이러한 디스크는 운영 체제 디스크 또는 Azure에서 제공하는 임시 디스크에 두지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-210">Do not place these on the operating system disk or the temporary disks provided by Azure.</span></span>  <br/> |
|<span data-ttu-id="a3ba0-211">IP 주소</span><span class="sxs-lookup"><span data-stu-id="a3ba0-211">IP addresses</span></span>  <br/> |<span data-ttu-id="a3ba0-212">고정 IP 주소를 사용하여 도메인 컨트롤러가 구성된 후 가상 네트워크의 가상 머신에 이러한 주소를 할당하도록 가상 네트워크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-212">Use static IP addresses and configure the virtual network to assign these addresses to the virtual machines in the virtual network after the domain controllers have been configured.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="a3ba0-213">Azure에서 Active Directory를 배포하기 전에 Azure 가상 컴퓨터의 Windows Server Active Directory 배포에 대한 [지침을 읽어야 합니다.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100)</span><span class="sxs-lookup"><span data-stu-id="a3ba0-213">Before you deploy Active Directory in Azure, read [Guidelines for Deploying Windows Server Active Directory on Azure Virtual Machines](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100).</span></span> <span data-ttu-id="a3ba0-214">이러한 설정은 솔루션에 다른 아키텍처 또는 다른 구성 설정이 필요한지 여부를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-214">These help you determine if a different architecture or different configuration settings are needed for your solution.</span></span> 
  
## <a name="add-the-sharepoint-farm"></a><span data-ttu-id="a3ba0-215">팜 SharePoint 추가</span><span class="sxs-lookup"><span data-stu-id="a3ba0-215">Add the SharePoint farm</span></span>

<span data-ttu-id="a3ba0-216">적절한 서브넷의 SharePoint 팜의 가상 컴퓨터를 계층에 두습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-216">Place the virtual machines of the SharePoint farm in tiers on the appropriate subnets.</span></span>
  
<span data-ttu-id="a3ba0-217">**그림 4: 가상 SharePoint 배치**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-217">**Figure 4: Placement of SharePoint virtual machines**</span></span>

![데이터베이스 서버 및 SharePoint 팜 서브넷 내의 Azure Virtual Network에 추가된 SharePoint 서버 역할](../media/AZarch-SPVMsinCloudSer.png)
  
<span data-ttu-id="a3ba0-219">이 다이어그램은 각 계층에 SharePoint 팜 서버 역할을 추가하여 이전 다이어그램을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-219">This diagram builds on the previous diagrams by adding the SharePoint farm server roles in their respective tiers.</span></span>
  
- <span data-ttu-id="a3ba0-220">실행 중인 두 데이터베이스 가상 SQL Server 계층을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-220">Two database virtual machines running SQL Server create the database tier.</span></span>
    
- <span data-ttu-id="a3ba0-221">프런트 엔드 서버SharePoint 분산 캐시 서버 및 백 엔드 서버 등 각 계층에 대해 SharePoint Server 2013을 실행하는 가상 컴퓨터 2대.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-221">Two virtual machines running SharePoint Server 2013 for each of the following tiers: front end servers, distributed cache servers, and back end servers.</span></span>
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a><span data-ttu-id="a3ba0-222">가용성 집합 및 장애 도메인에 대한 서버 역할 디자인 및 미세 조정</span><span class="sxs-lookup"><span data-stu-id="a3ba0-222">Design and fine tune server roles for availability sets and fault domains</span></span>

<span data-ttu-id="a3ba0-223">장애 도메인은 역할 인스턴스가 실행되는 하드웨어 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-223">A fault domain is a grouping of hardware in which role instances run.</span></span> <span data-ttu-id="a3ba0-224">Azure 인프라에서 동일한 장애 도메인 내의 가상 컴퓨터를 동시에 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-224">Virtual machines within the same fault domain can be updated by the Azure infrastructure at the same time.</span></span> <span data-ttu-id="a3ba0-225">또는 동일한 랙을 공유하기 때문에 동시에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-225">Or, they can fail at the same time because they share the same rack.</span></span> <span data-ttu-id="a3ba0-226">동일한 장애 도메인에 두 개의 가상 컴퓨터를 사용할 위험이 없는 경우 가상 컴퓨터를 가용성 집합으로 구성하여 각 가상 컴퓨터의 장애 도메인이 서로 다른 도메인에 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-226">To avoid the risk of having two virtual machines on the same fault domain, you can configure your virtual machines as an availability set, which ensures that each virtual machine is in a different fault domain.</span></span> <span data-ttu-id="a3ba0-227">세 개의 가상 컴퓨터를 가용성 집합으로 구성하는 경우 Azure는 두 개 이상의 가상 컴퓨터를 동일한 장애 도메인에 두 개 이상 위치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-227">If three virtual machines are configured as an availability set, Azure guarantees that no more than two of the virtual machines are located in the same fault domain.</span></span>
  
<span data-ttu-id="a3ba0-228">SharePoint 팜에 대해 Azure 아키텍처를 디자인할 때 가용성 집합의 일부로 동일한 서버 역할을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-228">When you design the Azure architecture for a SharePoint farm, configure identical server roles to be part of an availability set.</span></span> <span data-ttu-id="a3ba0-229">이렇게 하면 가상 컴퓨터를 여러 장애 도메인에 분산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-229">This ensures that your virtual machines are spread across multiple fault domains.</span></span>
  
<span data-ttu-id="a3ba0-230">**그림 5: Azure 가용성 집합을 사용하여 SharePoint 팜 계층에 대한 고가용성 제공**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-230">**Figure 5: Use Azure Availability Sets to provide high availability for the SharePoint farm tiers**</span></span>

![SharePoint 2013 솔루션에 대한 Azure 인프라의 가용성 집합 구성](../media/AZenv-WinAzureAvailSetsHA.png)
  
<span data-ttu-id="a3ba0-232">이 다이어그램에서는 Azure 인프라 내에서 가용성 집합의 구성을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-232">This diagram calls out the configuration of availability sets within the Azure infrastructure.</span></span> <span data-ttu-id="a3ba0-233">다음 각 역할은 별도의 가용성 집합을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-233">Each of the following roles share a separate availability set:</span></span>
  
- <span data-ttu-id="a3ba0-234">Active Directory 및 DNS</span><span class="sxs-lookup"><span data-stu-id="a3ba0-234">Active Directory and DNS</span></span>
    
- <span data-ttu-id="a3ba0-235">Database</span><span class="sxs-lookup"><span data-stu-id="a3ba0-235">Database</span></span>
    
- <span data-ttu-id="a3ba0-236">백 엔드</span><span class="sxs-lookup"><span data-stu-id="a3ba0-236">Back end</span></span>
    
- <span data-ttu-id="a3ba0-237">캐시 배포</span><span class="sxs-lookup"><span data-stu-id="a3ba0-237">Distribute cache</span></span>
    
- <span data-ttu-id="a3ba0-238">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="a3ba0-238">Front end</span></span>
    
<span data-ttu-id="a3ba0-239">Azure SharePoint 팜을 세부적으로 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-239">The SharePoint farm might need to be fine tuned in the Azure platform.</span></span> <span data-ttu-id="a3ba0-240">모든 구성 요소의 고가용성을 보장하기 위해 서버 역할이 모두 동일하게 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-240">To ensure high availability of all components, ensure that the server roles are all configured identically.</span></span>
  
<span data-ttu-id="a3ba0-241">다음은 특정 용량 및 성능 목표를 충족하는 표준 인터넷 사이트 아키텍처를 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-241">Here is an example that shows a standard Internet Sites architecture that meets specific capacity and performance goals.</span></span> <span data-ttu-id="a3ba0-242">이 예제는 SharePoint [Server 2013용 인터넷 사이트 검색 아키텍처](https://go.microsoft.com/fwlink/p/?LinkId=261519)아키텍처의 아키텍처 모델에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-242">This example is featured in the following architecture model: [Internet Sites Search Architectures for SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=261519).</span></span>
  
<span data-ttu-id="a3ba0-243">**그림 6: 3계층 팜의 용량 및 성능 목표 계획 예제**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-243">**Figure 6: Planning example for capacity and performance goals in a three-tier farm**</span></span>

![특정 용량 SharePoint 성능 목표를 충족하는 구성 요소 할당이 있는 Standard SharePoint 2013 인터넷 사이트 아키텍처](../media/AZarch-CapPerfexmpArch.png)
  
<span data-ttu-id="a3ba0-245">다음은 이 다이어그램에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-245">In this diagram:</span></span>
  
- <span data-ttu-id="a3ba0-246">3계층 팜은 웹 서버, 응용 프로그램 서버 및 데이터베이스 서버로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-246">A three-tier farm is represented: web servers, application servers, and database servers.</span></span>
    
- <span data-ttu-id="a3ba0-247">세 개의 웹 서버는 여러 구성 요소와 동일하게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-247">The three web servers are configured identically with multiple components.</span></span>
    
- <span data-ttu-id="a3ba0-248">두 데이터베이스 서버는 동일하게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-248">The two database servers are configured identically.</span></span>
    
- <span data-ttu-id="a3ba0-249">세 응용 프로그램 서버는 동일하게 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-249">The three application servers are not configured identically.</span></span> <span data-ttu-id="a3ba0-250">이러한 서버 역할은 Azure의 가용성 집합에 대해 미세 조정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-250">These server roles require fine tuning for availability sets in Azure.</span></span>
    
<span data-ttu-id="a3ba0-251">응용 프로그램 서버 계층에 대해 자세히 살펴보급시다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-251">Let's look closer at the application server tier.</span></span>
  
<span data-ttu-id="a3ba0-252">**그림 7: 미세 조정 전 응용 프로그램 서버 계층**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-252">**Figure 7: Application server tier before fine tuning**</span></span>

![가용성 SharePoint 조정하기 전에 Server 2013 응용 프로그램 Microsoft Azure 예제](../media/AZarch-AppServtierBefore.png)
  
<span data-ttu-id="a3ba0-254">다음은 이 다이어그램에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-254">In this diagram:</span></span>
  
- <span data-ttu-id="a3ba0-255">응용 프로그램 계층에는 세 개의 서버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-255">Three servers are included in the application tier.</span></span>
    
- <span data-ttu-id="a3ba0-256">첫 번째 서버에는 4개의 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-256">The first server includes four components.</span></span>
    
- <span data-ttu-id="a3ba0-257">두 번째 서버에는 세 가지 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-257">The second server includes three components.</span></span>
    
- <span data-ttu-id="a3ba0-258">세 번째 서버에는 두 개의 구성 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-258">The third server includes two components.</span></span>
    
<span data-ttu-id="a3ba0-259">팜의 성능 및 용량 목표에 따라 구성 요소 수를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-259">You determine the number of components by the performance and capacity targets for the farm.</span></span> <span data-ttu-id="a3ba0-260">Azure에 맞게 이 아키텍처를 조정하기 위해 4개의 구성 요소를 세 서버에 모두 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-260">To adapt this architecture for Azure, we'll replicate the four components across all three servers.</span></span> <span data-ttu-id="a3ba0-261">이렇게 하면 성능 및 용량에 필요한 구성 요소 수가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-261">This increases the number of components beyond what is necessary for performance and capacity.</span></span> <span data-ttu-id="a3ba0-262">이 디자인은 이러한 세 개의 가상 컴퓨터를 가용성 집합에 할당할 때 Azure 플랫폼의 네 가지 구성 요소를 모두 고가용성으로 보장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-262">The tradeoff is that this design ensures high availability of all four components in the Azure platform when these three virtual machines are assigned to an availability set.</span></span>
  
<span data-ttu-id="a3ba0-263">**그림 8: 미세 조정 후 응용 프로그램 서버 계층**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-263">**Figure 8: Application server tier after fine tuning**</span></span>

![SharePoint 가용성 집합에 대한 조정 후 서버 2013 응용 Microsoft Azure 예제](../media/AZarch-AppServtierAfter.png)
  
<span data-ttu-id="a3ba0-265">이 다이어그램은 동일한 4개의 구성 요소로 동일하게 구성된 3개의 응용 프로그램 서버를 모두 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-265">This diagram shows all three application servers configured identically with the same four components.</span></span>
  
<span data-ttu-id="a3ba0-266">가용성 집합을 SharePoint 팜의 계층에 추가하면 구현이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-266">When we add availability sets to the tiers of the SharePoint farm, the implementation is complete.</span></span>
  
<span data-ttu-id="a3ba0-267">**그림 9: Azure 인프라 SharePoint 완료된 팜**</span><span class="sxs-lookup"><span data-stu-id="a3ba0-267">**Figure 9: The completed SharePoint farm in Azure infrastructure services**</span></span>

![예제 SharePoint, 크로스-프레미스 연결, 서브넷, VM 및 가용성 집합이 있는 Azure 인프라 서비스의 2013 팜 예제](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
<span data-ttu-id="a3ba0-269">이 다이어그램은 Azure 인프라 서비스에서 SharePoint 팜을 보여 주며, 가용성 집합을 통해 각 계층의 서버에 장애 도메인을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ba0-269">This diagram shows the SharePoint farm implemented in Azure infrastructure services, with availability sets to provide fault domains for the servers in each tier.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3ba0-270">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3ba0-270">See Also</span></span>

[<span data-ttu-id="a3ba0-271">Microsoft 365 솔루션 및 아키텍처 센터</span><span class="sxs-lookup"><span data-stu-id="a3ba0-271">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)
  
[<span data-ttu-id="a3ba0-272">SharePoint Server 2013을 사용하는 Microsoft Azure의 인터넷 사이트</span><span class="sxs-lookup"><span data-stu-id="a3ba0-272">Internet Sites in Microsoft Azure using SharePoint Server 2013</span></span>](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[<span data-ttu-id="a3ba0-273">Microsoft Azure에서 SharePoint Server 2013 재해 복구</span><span class="sxs-lookup"><span data-stu-id="a3ba0-273">SharePoint Server 2013 Disaster Recovery in Microsoft Azure</span></span>](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)