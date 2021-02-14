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
description: Microsoft Azure 가상 머신에서 호스팅할 수 있는 SharePoint 2013 솔루션 유형과 호스트할 Azure를 설정하는 방법을 설명합니다.
ms.openlocfilehash: 37d7eb2a746e30ad560949a933783beb6b971a08
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696379"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a><span data-ttu-id="f642c-103">SharePoint 2013용 Microsoft Azure 아키텍처</span><span class="sxs-lookup"><span data-stu-id="f642c-103">Microsoft Azure Architectures for SharePoint 2013</span></span>

<span data-ttu-id="f642c-104">Azure는 SharePoint Server 2013 솔루션을 호스팅하기에 좋은 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-104">Azure is a good environment for hosting a SharePoint Server 2013 solution.</span></span> <span data-ttu-id="f642c-105">대부분의 경우 Microsoft 365를 사용하는 것이 좋지만 Azure에서 호스트되는 SharePoint Server 팜은 특정 솔루션에 좋은 옵션일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-105">In most cases, we recommend Microsoft 365, but a SharePoint Server farm hosted in Azure can be a good option for specific solutions.</span></span> <span data-ttu-id="f642c-106">이 문서에서는 Azure 플랫폼에 적합한 SharePoint 솔루션을 설계하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-106">This article describes how to architect SharePoint solutions so they are a good fit in the Azure platform.</span></span> <span data-ttu-id="f642c-107">다음과 같은 두 가지 특정 솔루션이 예제로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-107">The following two specific solutions are used as examples:</span></span>
  
- [<span data-ttu-id="f642c-108">Microsoft Azure에서 SharePoint Server 2013 재해 복구</span><span class="sxs-lookup"><span data-stu-id="f642c-108">SharePoint Server 2013 Disaster Recovery in Microsoft Azure</span></span>](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [<span data-ttu-id="f642c-109">SharePoint Server 2013을 사용하는 Microsoft Azure의 인터넷 사이트</span><span class="sxs-lookup"><span data-stu-id="f642c-109">Internet Sites in Microsoft Azure using SharePoint Server 2013</span></span>](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a><span data-ttu-id="f642c-110">Azure 인프라 서비스에 대한 권장 SharePoint 솔루션</span><span class="sxs-lookup"><span data-stu-id="f642c-110">Recommended SharePoint solutions for Azure Infrastructure Services</span></span>

<span data-ttu-id="f642c-111">Azure 인프라 서비스는 SharePoint 솔루션을 호스팅하기 위한 좋은 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-111">Azure infrastructure services is a compelling option for hosting SharePoint solutions.</span></span> <span data-ttu-id="f642c-112">일부 솔루션은 다른 솔루션보다 이 플랫폼에 더 잘 맞습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-112">Some solutions are a better fit for this platform than others.</span></span> <span data-ttu-id="f642c-113">다음 표에서는 권장 해결법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-113">The following table shows recommended solutions.</span></span>
  
|<span data-ttu-id="f642c-114">**솔루션**</span><span class="sxs-lookup"><span data-stu-id="f642c-114">**Solution**</span></span>|<span data-ttu-id="f642c-115">**Azure에 이 솔루션이 권장되는 이유**</span><span class="sxs-lookup"><span data-stu-id="f642c-115">**Why this solution is recommended for Azure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f642c-116">개발 및 테스트 환경</span><span class="sxs-lookup"><span data-stu-id="f642c-116">Development and test environments</span></span>  <br/> |<span data-ttu-id="f642c-117">이러한 환경을 쉽게 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-117">It's easy to create and manage these environments.</span></span>  <br/> |
|<span data-ttu-id="f642c-118">Azure에 대한 On-premises SharePoint 팜의 재해 복구</span><span class="sxs-lookup"><span data-stu-id="f642c-118">Disaster recovery of on-premises SharePoint farms to Azure</span></span>  <br/> |<span data-ttu-id="f642c-119">**호스팅된 보조 데이터 센터** 다른 지역의 보조 데이터 센터에 투자하는 대신 Azure를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-119">**Hosted secondary datacenter** Use Azure instead of investing in a secondary datacenter in a different region.</span></span> <br/> <span data-ttu-id="f642c-120">**낮은 비용의 재해 복구 환경** 프레미스 재해 복구 환경보다 적은 수의 리소스를 유지 관리하고 비용을 지불합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-120">**Lower-cost disaster-recovery environments** Maintain and pay for fewer resources than an on-premises disaster recovery environment.</span></span> <span data-ttu-id="f642c-121">리소스 수는 콜드 대기, 웜 대기 또는 핫 대기와 같은 재해 복구 환경에 따라 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-121">The number of resources depends on the disaster recovery environment you choose: cold standby, warm standby, or hot standby.</span></span> <br/> <span data-ttu-id="f642c-122">**보다 탄력적인 플랫폼** 재해가 발생하면 부하 요구 사항을 충족하기 위해 복구 SharePoint 팜을 쉽게 수 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-122">**More elastic platform** In the event of a disaster, easily scale-out your recovery SharePoint farm to meet load requirements.</span></span> <span data-ttu-id="f642c-123">더 이상 리소스가 필요하지 때 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-123">Scale in when you no longer need the resources.</span></span> <br/> <span data-ttu-id="f642c-124">[Microsoft Azure에서 SharePoint Server 2013 재해 복구를 참조하세요.](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)</span><span class="sxs-lookup"><span data-stu-id="f642c-124">See [SharePoint Server 2013 Disaster Recovery in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).</span></span>  <br/> |
|<span data-ttu-id="f642c-125">Microsoft 365에서 사용할 수 없는 기능 및 확장을 사용하는 인터넷 연결 사이트</span><span class="sxs-lookup"><span data-stu-id="f642c-125">Internet-facing sites that use features and scale not available in Microsoft 365</span></span>  <br/> |<span data-ttu-id="f642c-126">**노력에 집중** 인프라를 구축하는 대신 멋진 사이트를 구축하는 데 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-126">**Focus your efforts** Concentrate on building a great site rather than building infrastructure.</span></span> <br/> <span data-ttu-id="f642c-127">**Azure에서 탄력성 활용** 새 서버를 추가하여 수요에 따라 팜의 크기를 정하고 필요한 리소스만 지불하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-127">**Take advantage of elasticity in Azure** Size the farm for the demand by adding new servers, and pay only for resources you need.</span></span> <span data-ttu-id="f642c-128">동적 컴퓨터 할당은 지원되지 않습니다(자동 크기 조정).</span><span class="sxs-lookup"><span data-stu-id="f642c-128">Dynamic machine allocation is not supported (auto scale).</span></span> <br/> <span data-ttu-id="f642c-129">**Azure AD(Active Directory) 사용** 고객 계정에 대해 Azure AD를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-129">**Use Azure Active Directory (AD)** Take advantage of Azure AD for customer accounts.</span></span> <br/> <span data-ttu-id="f642c-130">**Microsoft 365에서** 사용할 수 없는 SharePoint 기능 추가 심층 보고 및 웹 분석을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-130">**Add SharePoint functionality not available in Microsoft 365** Add deep reporting and web analytics.</span></span> <br/> <span data-ttu-id="f642c-131">[SharePoint Server 2013을](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)사용하여 Microsoft Azure의 인터넷 사이트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f642c-131">See [Internet Sites in Microsoft Azure using SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md).</span></span>  <br/> |
|<span data-ttu-id="f642c-132">Microsoft 365 또는 프레미스 환경을 지원하기 위한 앱 팜</span><span class="sxs-lookup"><span data-stu-id="f642c-132">App farms to support Microsoft 365 or on-premises environments</span></span>  <br/> |<span data-ttu-id="f642c-133">**Azure에서 앱 빌드,** 테스트 및 호스트를 통해 클라우드 환경과의 환경 모두를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-133">**Build, test, and host apps** in Azure to support both on-premises and cloud environments.</span></span> <br/> <span data-ttu-id="f642c-134">**Azure에서 새** 하드웨어를 구입하는 대신 Azure에서 이 역할을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-134">**Host this role** in Azure instead of buying new hardware for on-premises environments.</span></span> <br/> |
   
<span data-ttu-id="f642c-135">인트라넷 및 공동 작업 솔루션 및 워크로드의 경우 다음 옵션을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="f642c-135">For intranet and collaboration solutions and workloads, consider the following options:</span></span>
  
- <span data-ttu-id="f642c-136">Microsoft 365가 비즈니스 요구 사항을 충족하는지 아니면 솔루션의 일부가 될 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-136">Determine if Microsoft 365 meets your business requirements or can be part of the solution.</span></span> <span data-ttu-id="f642c-137">Microsoft 365는 항상 최신의 다양한 기능 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-137">Microsoft 365 provides a rich feature set that is always up to date.</span></span>
    
- <span data-ttu-id="f642c-138">Microsoft 365가 모든 비즈니스 요구 사항을 충족하지 않는 경우 MCS(Microsoft Consulting Services)에서 제공하는 SharePoint 2013의 표준 구현을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="f642c-138">If Microsoft 365 does not meet all your business requirements, consider a standard implementation of SharePoint 2013 on premises from Microsoft Consulting Services (MCS).</span></span> <span data-ttu-id="f642c-139">표준 아키텍처는 사용자 지정된 아키텍처보다 더 빠르고 저렴한 솔루션이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-139">A standard architecture can be a quicker, cheaper, and easier solution for you to support than a customized one.</span></span> 
    
- <span data-ttu-id="f642c-140">표준 구현이 비즈니스 요구 사항을 충족하지 않는 경우 사용자 지정된 On-프레미스 솔루션을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="f642c-140">If a standard implementation doesn't meet your business requirements, consider a customized on-premises solution.</span></span>
    
- <span data-ttu-id="f642c-141">비즈니스 요구 사항에 클라우드 플랫폼을 사용하는 것이 중요한 경우 Azure 인프라 서비스에서 호스트된 SharePoint 2013의 표준 또는 사용자 지정 구현을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="f642c-141">If using a cloud platform is important for your business requirements, consider a standard or customized implementation of SharePoint 2013 hosted in Azure infrastructure services.</span></span> <span data-ttu-id="f642c-142">SharePoint 솔루션은 다른 기본이 아닌 Microsoft 공용 클라우드 플랫폼보다 Azure에서 훨씬 더 쉽게 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-142">SharePoint solutions are much easier to support in Azure than other non-native Microsoft public cloud platforms.</span></span>
    
## <a name="before-you-design-the-azure-environment"></a><span data-ttu-id="f642c-143">Azure 환경을 디자인하기 전에</span><span class="sxs-lookup"><span data-stu-id="f642c-143">Before you design the Azure environment</span></span>

<span data-ttu-id="f642c-144">이 문서에서는 예제 SharePoint 토폴로지와 함께 이러한 디자인 개념을 SharePoint 팜 토폴로지와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-144">While this article uses example SharePoint topologies, you can use these design concepts with any SharePoint farm topology.</span></span> <span data-ttu-id="f642c-145">Azure 환경을 디자인하기 전에 다음 토폴로지, 아키텍처, 용량 및 성능 지침을 사용하여 SharePoint 팜을 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-145">Before you design the Azure environment, use the following topology, architecture, capacity, and performance guidance to design the SharePoint farm:</span></span>
  
- [<span data-ttu-id="f642c-146">SharePoint 2013 IT전문가용 아키텍처 디자인</span><span class="sxs-lookup"><span data-stu-id="f642c-146">Architecture design for SharePoint 2013 IT pros</span></span>](https://technet.microsoft.com/sharepoint/fp123594.aspx)
    
- [<span data-ttu-id="f642c-147">SharePoint Server 2013에서 성능 및 용량 관리 계획</span><span class="sxs-lookup"><span data-stu-id="f642c-147">Plan for performance and capacity management in SharePoint Server 2013</span></span>](https://technet.microsoft.com/library/8dd52916-f77d-4444-b593-1f7d6f330e5f.aspx)
    
## <a name="determine-the-active-directory-domain-type"></a><span data-ttu-id="f642c-148">Active Directory 도메인 유형 확인</span><span class="sxs-lookup"><span data-stu-id="f642c-148">Determine the Active Directory domain type</span></span>

<span data-ttu-id="f642c-149">각 SharePoint Server 팜은 Active Directory를 통해 팜 설정에 대한 관리 계정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-149">Each SharePoint Server farm relies on Active Directory to provide administrative accounts for farm setup.</span></span> <span data-ttu-id="f642c-150">현재 Azure에서 SharePoint 솔루션에 대한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-150">At this time, there are two options for SharePoint solutions in Azure.</span></span> <span data-ttu-id="f642c-151">이러한 설명은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-151">These are described in the following table.</span></span>
  
|<span data-ttu-id="f642c-152">**옵션**</span><span class="sxs-lookup"><span data-stu-id="f642c-152">**Option**</span></span>|<span data-ttu-id="f642c-153">**설명**</span><span class="sxs-lookup"><span data-stu-id="f642c-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f642c-154">전용 도메인</span><span class="sxs-lookup"><span data-stu-id="f642c-154">Dedicated domain</span></span>  <br/> |<span data-ttu-id="f642c-155">Azure에 격리된 전용 Active Directory 도메인을 배포하여 SharePoint 팜을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-155">You can deploy a dedicated and isolated Active Directory domain to Azure to support your SharePoint farm.</span></span> <span data-ttu-id="f642c-156">공용 인터넷 사이트에는 이 선택이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-156">This is a good choice for public-facing Internet sites.</span></span>  <br/> |
|<span data-ttu-id="f642c-157">크로스-프레미스 연결을 통해 프레미스 도메인 확장</span><span class="sxs-lookup"><span data-stu-id="f642c-157">Extend the on-premises domain through a cross-premises connection</span></span>  <br/> |<span data-ttu-id="f642c-158">크로스-프레미스 연결을 통해 크로스-프레미스 도메인을 확장하면 사용자는 인트라넷을 통해 SharePoint 팜이 호스트된 경우처럼 SharePoint 팜에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-158">When you extend the on-premises domain through a cross-premises connection, users access the SharePoint farm via your intranet as if it were hosted on-premises.</span></span> <span data-ttu-id="f642c-159">프레미스 Active Directory 및 DNS 구현을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-159">You can take advantage of your on-premises Active Directory and DNS implementation.</span></span>  <br/> <span data-ttu-id="f642c-160">Azure에서 재해 복구 환경을 구축하려면 프레미스 간 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-160">A cross-premises connection is required for building a disaster-recovery environment in Azure to fail over to from your on-premises farm.</span></span>  <br/> |
   
<span data-ttu-id="f642c-161">이 문서에는 크로스-프레미스 연결을 통해프레미스 도메인을 확장하기 위한 디자인 개념이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-161">This article includes design concepts for extending the on-premises domain through a cross-premises connection.</span></span> <span data-ttu-id="f642c-162">솔루션에서 전용 도메인을 사용하는 경우 프레미스 간 연결이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-162">If your solution uses a dedicated domain, you don't need a cross-premises connection.</span></span>
  
## <a name="design-the-virtual-network"></a><span data-ttu-id="f642c-163">가상 네트워크 디자인</span><span class="sxs-lookup"><span data-stu-id="f642c-163">Design the virtual network</span></span>

<span data-ttu-id="f642c-164">먼저 Azure에 가상 컴퓨터를 두는 서브넷이 포함된 가상 네트워크가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-164">First you need a virtual network in Azure, which includes subnets on which you will place your virtual machines.</span></span> <span data-ttu-id="f642c-165">가상 네트워크에는 서브넷에 할당하는 일부가 개인 IP 주소 공간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-165">The virtual network needs a private IP address space, portions of which you assign to the subnets.</span></span>
  
<span data-ttu-id="f642c-166">크로스-프레미스 연결을 통해 Azure로 On-premises 네트워크를 확장하는 경우(재해 복구 환경에 필요) 조직 네트워크의 다른 곳에서 아직 사용되지 않는 개인 주소 공간을 선택해야 합니다. 이 공간에는 해당 환경 및 기타 Azure Virtual Network가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-166">If you are extending your on-premises network to Azure through a cross-premises connection (required for a disaster recovery environment), you must choose a private address space that is not already in use elsewhere in your organization network, which can include your on-premises environment and other Azure virtual networks.</span></span> 
  
<span data-ttu-id="f642c-167">**그림 1: Azure의 가상 네트워크를 사용하여 프레미스 환경**</span><span class="sxs-lookup"><span data-stu-id="f642c-167">**Figure 1: On-premises environment with a virtual network in Azure**</span></span>

![SharePoint 솔루션에 대한 Microsoft Azure Virtual Network 디자인입니다.](../media/OPrrasconWA-AZarch.png)
  
<span data-ttu-id="f642c-171">다음은 이 다이어그램에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-171">In this diagram:</span></span>
  
- <span data-ttu-id="f642c-172">Azure의 가상 네트워크는 사내 환경과 나란히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-172">A virtual network in Azure is illustrated side-by-side to the on-premises environment.</span></span> <span data-ttu-id="f642c-173">두 환경은 사이트 간 VPN 연결 또는 ExpressRoute일 수 있는 프레미스 간 연결로 아직 연결되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-173">The two environments are not yet connected by a cross-premises connection, which can be a site-to-site VPN connection or ExpressRoute.</span></span>
    
- <span data-ttu-id="f642c-174">이때 가상 네트워크는 서브넷만 포함하며 다른 아키텍처 요소는 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-174">At this point, the virtual network just includes the subnets and no other architectural elements.</span></span> <span data-ttu-id="f642c-175">하나의 서브넷은 Azure 게이트웨이를 호스트하고 다른 서브넷은 SharePoint 팜의 계층을 호스트하며 Active Directory 및 DNS에 대한 추가 계층을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-175">One subnet will host the Azure gateway and other subnets host the tiers of the SharePoint farm, with an additional one for Active Directory and DNS.</span></span>
    
## <a name="add-cross-premises-connectivity"></a><span data-ttu-id="f642c-176">크로스-프레미스 연결 추가</span><span class="sxs-lookup"><span data-stu-id="f642c-176">Add cross-premises connectivity</span></span>

<span data-ttu-id="f642c-177">다음 배포 단계는 프레미스 간 연결을 만드는 것입니다(솔루션에 적용되는 경우).</span><span class="sxs-lookup"><span data-stu-id="f642c-177">The next deployment step is to create the cross-premises connection (if this applies to your solution).</span></span> <span data-ttu-id="f642c-178">크로스-프레미스 연결의 경우 Azure 게이트웨이는 별도의 게이트웨이 서브넷에 있으며, 주소 공간을 만들고 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-178">For cross-premises connections, a Azure gateway resides in a separate gateway subnet, which you must create and assign an address space.</span></span> 
  
<span data-ttu-id="f642c-179">크로스-프레미스 연결을 계획할 때 Azure 게이트웨이 및 연결은 정의하고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-179">When you plan for a cross-premises connection, you define and create an Azure gateway and connection to an on-premises gateway device.</span></span>
  
<span data-ttu-id="f642c-180">**그림 2: Azure 게이트웨이 및 프레미스 게이트웨이 장치를 사용하여,프레미스 환경과 Azure 간에 사이트 간 연결을 제공합니다.**</span><span class="sxs-lookup"><span data-stu-id="f642c-180">**Figure 2: Using an Azure gateway and an on-premises gateway device to provide site-to-site connectivity between the on-premises environment and Azure**</span></span>

![사이트 간 VPN 연결 또는 ExpressRoute일 수 있는 프레미스 간 연결을 통해 Azure Virtual Network에 연결된 프레미스 환경](../media/AZarch-VPNgtwyconnct.png)
  
<span data-ttu-id="f642c-182">다음은 이 다이어그램에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-182">In this diagram:</span></span>
  
- <span data-ttu-id="f642c-183">이전 다이어그램에 추가하면, 사이트 간 VPN 연결 또는 ExpressRoute일 수 있는 프레미스 간 연결을 통해 Azure Virtual Network에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-183">Adding to the previous diagram, the on-premises environment is connected to the Azure virtual network by a cross-premise connection, which can be a site-to-site VPN connection or ExpressRoute.</span></span>
    
- <span data-ttu-id="f642c-184">Azure 게이트웨이가 게이트웨이 서브넷에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-184">An Azure gateway is on a gateway subnet.</span></span>
    
- <span data-ttu-id="f642c-185">On-premises environment includes a gateway device, such as a router or VPN server.</span><span class="sxs-lookup"><span data-stu-id="f642c-185">The on-premises environment includes a gateway device, such as a router or VPN server.</span></span>
    
<span data-ttu-id="f642c-186">크로스-프레미스 가상 네트워크를 계획하고 만드는 자세한 내용은 Microsoft Azure Virtual Network에 대한 프레미스 간 네트워크 [연결을 참조하세요.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)</span><span class="sxs-lookup"><span data-stu-id="f642c-186">For additional information to plan for and create a cross-premises virtual network, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a><span data-ttu-id="f642c-187">AD DS(Active Directory 도메인 서비스) 및 DNS 추가</span><span class="sxs-lookup"><span data-stu-id="f642c-187">Add Active Directory Domain Services (AD DS) and DNS</span></span>

<span data-ttu-id="f642c-188">Azure의 재해 복구를 위해 Windows Server AD를 배포하는 하이브리드 시나리오에서 Windows Server AD와 DNS를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-188">For disaster recovery in Azure, you deploy Windows Server AD and DNS in a hybrid scenario where Windows Server AD is deployed both on-premises and on Azure virtual machines.</span></span>
  
<span data-ttu-id="f642c-189">**그림 3: 하이브리드 Active Directory 도메인 구성**</span><span class="sxs-lookup"><span data-stu-id="f642c-189">**Figure 3: Hybrid Active Directory domain configuration**</span></span>

![Azure Virtual Network에 배포된 STwo 가상 컴퓨터 및 SharePoint 팜 서브넷은 복제본 도메인 컨트롤러 및 DNS 서버입니다.](../media/AZarch-HyADdomainConfig.png)
  
<span data-ttu-id="f642c-191">이 다이어그램은 Windows Server AD 및 DNS 서브넷에 가상 컴퓨터를 두 개 추가하여 이전 다이어그램을 토대화합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-191">This diagram builds on the previous diagrams by adding two virtual machines to a Windows Server AD and DNS subnet.</span></span> <span data-ttu-id="f642c-192">이러한 가상 컴퓨터는 복제본 도메인 컨트롤러 및 DNS 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-192">These virtual machines are replica domain controllers and DNS servers.</span></span> <span data-ttu-id="f642c-193">이는 해당 환경의 확장으로, Windows Server AD 환경의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-193">They are an extension of the on-premises Windows Server AD environment.</span></span> 
  
<span data-ttu-id="f642c-194">다음 표에서는 Azure의 이러한 가상 머신에 대한 구성 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-194">The following table provides configuration recommendations for these virtual machines in Azure.</span></span> <span data-ttu-id="f642c-195">Azure 환경이 사용자 환경과 통신하지 않는 전용 도메인의 경우에도 자체 환경을 디자인하기 위한 시작 지점으로 이 기능을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f642c-195">Use these as a starting point for designing your own environment—even for a dedicated domain where your Azure environment doesn't communicate with your on-premises environment.</span></span>
  
|<span data-ttu-id="f642c-196">**항목**</span><span class="sxs-lookup"><span data-stu-id="f642c-196">**Item**</span></span>|<span data-ttu-id="f642c-197">**구성**</span><span class="sxs-lookup"><span data-stu-id="f642c-197">**Configuration**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f642c-198">Azure의 가상 컴퓨터 크기</span><span class="sxs-lookup"><span data-stu-id="f642c-198">Virtual machine size in Azure</span></span>  <br/> |<span data-ttu-id="f642c-199">표준 계층의 A1 또는 A2 크기</span><span class="sxs-lookup"><span data-stu-id="f642c-199">A1 or A2 size in the Standard tier</span></span>  <br/> |
|<span data-ttu-id="f642c-200">운영 체제</span><span class="sxs-lookup"><span data-stu-id="f642c-200">Operating system</span></span>  <br/> |<span data-ttu-id="f642c-201">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f642c-201">Windows Server 2012 R2</span></span>  <br/> |
|<span data-ttu-id="f642c-202">Active Directory 역할</span><span class="sxs-lookup"><span data-stu-id="f642c-202">Active Directory role</span></span>  <br/> |<span data-ttu-id="f642c-203">글로벌 카탈로그 서버로 지정된 AD DS 도메인 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-203">AD DS domain controller designated as a global catalog server.</span></span> <span data-ttu-id="f642c-204">이 구성은 크로스-프레미스 연결을 통해 유출 트래픽을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-204">This configuration reduces egress traffic across the cross-premises connection.</span></span>  <br/> <span data-ttu-id="f642c-205">변경률이 높은 다중 도메인 환경에서는 복제 트래픽을 줄이기 위해 Azure의 글로벌 카탈로그 서버와 동기화되지 않는 도메인 컨트롤러를 프레미스에서 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-205">In a multidomain environment with high rates of change (this is not common), configure domain controllers on premises not to sync with the global catalog servers in Azure, to reduce replication traffic.</span></span>  <br/> |
|<span data-ttu-id="f642c-206">DNS 역할</span><span class="sxs-lookup"><span data-stu-id="f642c-206">DNS role</span></span>  <br/> |<span data-ttu-id="f642c-207">도메인 컨트롤러에 DNS 서버 서비스를 설치하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-207">Install and configure the DNS Server service on the domain controllers.</span></span>  <br/> |
|<span data-ttu-id="f642c-208">데이터 디스크</span><span class="sxs-lookup"><span data-stu-id="f642c-208">Data disks</span></span>  <br/> |<span data-ttu-id="f642c-209">Active Directory 데이터베이스, 로그 및 SYSVOL을 추가 Azure 데이터 디스크에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-209">Place the Active Directory database, logs, and SYSVOL on additional Azure data disks.</span></span> <span data-ttu-id="f642c-210">이러한 디스크는 운영 체제 디스크 또는 Azure에서 제공하는 임시 디스크에 두지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-210">Do not place these on the operating system disk or the temporary disks provided by Azure.</span></span>  <br/> |
|<span data-ttu-id="f642c-211">IP 주소</span><span class="sxs-lookup"><span data-stu-id="f642c-211">IP addresses</span></span>  <br/> |<span data-ttu-id="f642c-212">고정 IP 주소를 사용하여 도메인 컨트롤러가 구성된 후 가상 네트워크의 가상 머신에 이러한 주소를 할당하도록 가상 네트워크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-212">Use static IP addresses and configure the virtual network to assign these addresses to the virtual machines in the virtual network after the domain controllers have been configured.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="f642c-213">Azure에서 Active Directory를 배포하기 전에 Azure 가상 머신에 Windows Server Active Directory를 배포하기 위한 지침을 [읽어야 합니다.](https://go.microsoft.com/fwlink/p/?linkid=392681)</span><span class="sxs-lookup"><span data-stu-id="f642c-213">Before you deploy Active Directory in Azure, read [Guidelines for Deploying Windows Server Active Directory on Azure Virtual Machines](https://go.microsoft.com/fwlink/p/?linkid=392681).</span></span> <span data-ttu-id="f642c-214">이러한 설정은 솔루션에 다른 아키텍처 또는 다른 구성 설정이 필요한지 여부를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-214">These help you determine if a different architecture or different configuration settings are needed for your solution.</span></span> 
  
## <a name="add-the-sharepoint-farm"></a><span data-ttu-id="f642c-215">SharePoint 팜 추가</span><span class="sxs-lookup"><span data-stu-id="f642c-215">Add the SharePoint farm</span></span>

<span data-ttu-id="f642c-216">SharePoint 팜의 가상 컴퓨터를 적절한 서브넷의 계층에 2000개 2000개까지 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-216">Place the virtual machines of the SharePoint farm in tiers on the appropriate subnets.</span></span>
  
<span data-ttu-id="f642c-217">**그림 4: SharePoint 가상 컴퓨터 배치**</span><span class="sxs-lookup"><span data-stu-id="f642c-217">**Figure 4: Placement of SharePoint virtual machines**</span></span>

![SharePoint 팜 서브넷 내의 Azure Virtual Network에 추가된 데이터베이스 서버 및 SharePoint 서버 역할](../media/AZarch-SPVMsinCloudSer.png)
  
<span data-ttu-id="f642c-219">이 다이어그램은 각 계층에 SharePoint 팜 서버 역할을 추가하여 이전 다이어그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-219">This diagram builds on the previous diagrams by adding the SharePoint farm server roles in their respective tiers.</span></span>
  
- <span data-ttu-id="f642c-220">두 개의 데이터베이스 가상 컴퓨터를 SQL Server 계층을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-220">Two database virtual machines running SQL Server create the database tier.</span></span>
    
- <span data-ttu-id="f642c-221">프런트 엔드 서버, 분산 캐시 서버 및 백 엔드 서버의 각 계층에 대해 SharePoint Server 2013을 실행하는 두 개의 가상 컴퓨터.</span><span class="sxs-lookup"><span data-stu-id="f642c-221">Two virtual machines running SharePoint Server 2013 for each of the following tiers: front end servers, distributed cache servers, and back end servers.</span></span>
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a><span data-ttu-id="f642c-222">가용성 집합 및 장애 도메인에 대한 서버 역할 디자인 및 세부 조정</span><span class="sxs-lookup"><span data-stu-id="f642c-222">Design and fine tune server roles for availability sets and fault domains</span></span>

<span data-ttu-id="f642c-223">장애 도메인은 역할 인스턴스가 실행되는 하드웨어 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-223">A fault domain is a grouping of hardware in which role instances run.</span></span> <span data-ttu-id="f642c-224">Azure 인프라에서 동일한 장애 도메인 내의 가상 컴퓨터를 동시에 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-224">Virtual machines within the same fault domain can be updated by the Azure infrastructure at the same time.</span></span> <span data-ttu-id="f642c-225">또는 동일한 랙을 공유하기 때문에 동시에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-225">Or, they can fail at the same time because they share the same rack.</span></span> <span data-ttu-id="f642c-226">동일한 장애 도메인에 가상 컴퓨터 두 대가 있을 위험을 방지하기 위해 가상 컴퓨터를 가용성 집합으로 구성하여 각 가상 컴퓨터가 다른 장애 도메인에 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-226">To avoid the risk of having two virtual machines on the same fault domain, you can configure your virtual machines as an availability set, which ensures that each virtual machine is in a different fault domain.</span></span> <span data-ttu-id="f642c-227">세 개의 가상 컴퓨터를 가용성 집합으로 구성한 경우 Azure는 두 개 이상의 가상 컴퓨터를 동일한 장애 도메인에 두 개 이상 위치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-227">If three virtual machines are configured as an availability set, Azure guarantees that no more than two of the virtual machines are located in the same fault domain.</span></span>
  
<span data-ttu-id="f642c-228">SharePoint 팜에 대해 Azure 아키텍처를 디자인할 때 가용성 집합의 일부로 동일한 서버 역할을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-228">When you design the Azure architecture for a SharePoint farm, configure identical server roles to be part of an availability set.</span></span> <span data-ttu-id="f642c-229">이렇게 하면 가상 컴퓨터를 여러 장애 도메인에 분산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-229">This ensures that your virtual machines are spread across multiple fault domains.</span></span>
  
<span data-ttu-id="f642c-230">**그림 5: Azure 가용성 집합을 사용하여 SharePoint 팜 계층에 대한 고가용성 제공**</span><span class="sxs-lookup"><span data-stu-id="f642c-230">**Figure 5: Use Azure Availability Sets to provide high availability for the SharePoint farm tiers**</span></span>

![SharePoint 2013 솔루션에 대한 Azure 인프라의 가용성 집합 구성](../media/AZenv-WinAzureAvailSetsHA.png)
  
<span data-ttu-id="f642c-232">이 다이어그램은 Azure 인프라 내에서 가용성 집합의 구성을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-232">This diagram calls out the configuration of availability sets within the Azure infrastructure.</span></span> <span data-ttu-id="f642c-233">다음 각 역할은 별도의 가용성 집합을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-233">Each of the following roles share a separate availability set:</span></span>
  
- <span data-ttu-id="f642c-234">Active Directory 및 DNS</span><span class="sxs-lookup"><span data-stu-id="f642c-234">Active Directory and DNS</span></span>
    
- <span data-ttu-id="f642c-235">Database</span><span class="sxs-lookup"><span data-stu-id="f642c-235">Database</span></span>
    
- <span data-ttu-id="f642c-236">백 엔드</span><span class="sxs-lookup"><span data-stu-id="f642c-236">Back end</span></span>
    
- <span data-ttu-id="f642c-237">캐시 배포</span><span class="sxs-lookup"><span data-stu-id="f642c-237">Distribute cache</span></span>
    
- <span data-ttu-id="f642c-238">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="f642c-238">Front end</span></span>
    
<span data-ttu-id="f642c-239">Azure 플랫폼에서 SharePoint 팜을 미세 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-239">The SharePoint farm might need to be fine tuned in the Azure platform.</span></span> <span data-ttu-id="f642c-240">모든 구성 요소의 고가용성을 보장하기 위해 서버 역할이 모두 동일하게 구성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-240">To ensure high availability of all components, ensure that the server roles are all configured identically.</span></span>
  
<span data-ttu-id="f642c-241">다음은 특정 용량 및 성능 목표를 충족하는 표준 인터넷 사이트 아키텍처를 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-241">Here is an example that shows a standard Internet Sites architecture that meets specific capacity and performance goals.</span></span> <span data-ttu-id="f642c-242">이 예제는 [SharePoint Server 2013용 인터넷 사이트](https://go.microsoft.com/fwlink/p/?LinkId=261519)검색 아키텍처 아키텍처의 아키텍처 모델에 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-242">This example is featured in the following architecture model: [Internet Sites Search Architectures for SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=261519).</span></span>
  
<span data-ttu-id="f642c-243">**그림 6: 3계층 팜의 용량 및 성능 목표 계획 예제**</span><span class="sxs-lookup"><span data-stu-id="f642c-243">**Figure 6: Planning example for capacity and performance goals in a three-tier farm**</span></span>

![특정 용량 및 성능 목표를 충족하는 구성 요소 할당이 있는 표준 SharePoint 2013 인터넷 사이트 아키텍처](../media/AZarch-CapPerfexmpArch.png)
  
<span data-ttu-id="f642c-245">다음은 이 다이어그램에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-245">In this diagram:</span></span>
  
- <span data-ttu-id="f642c-246">3계층 팜은 웹 서버, 응용 프로그램 서버 및 데이터베이스 서버로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-246">A three-tier farm is represented: web servers, application servers, and database servers.</span></span>
    
- <span data-ttu-id="f642c-247">세 개의 웹 서버는 여러 구성 요소와 동일하게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-247">The three web servers are configured identically with multiple components.</span></span>
    
- <span data-ttu-id="f642c-248">두 데이터베이스 서버는 동일하게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-248">The two database servers are configured identically.</span></span>
    
- <span data-ttu-id="f642c-249">세 응용 프로그램 서버가 동일하게 구성되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-249">The three application servers are not configured identically.</span></span> <span data-ttu-id="f642c-250">이러한 서버 역할은 Azure의 가용성 집합에 대해 미세 조정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-250">These server roles require fine tuning for availability sets in Azure.</span></span>
    
<span data-ttu-id="f642c-251">응용 프로그램 서버 계층에 대해 자세히 살펴보고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-251">Let's look closer at the application server tier.</span></span>
  
<span data-ttu-id="f642c-252">**그림 7: 미세 조정 전 응용 프로그램 서버 계층**</span><span class="sxs-lookup"><span data-stu-id="f642c-252">**Figure 7: Application server tier before fine tuning**</span></span>

![Microsoft Azure 가용성 집합을 조정하기 전에 SharePoint Server 2013 응용 프로그램 서버 계층 예](../media/AZarch-AppServtierBefore.png)
  
<span data-ttu-id="f642c-254">다음은 이 다이어그램에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-254">In this diagram:</span></span>
  
- <span data-ttu-id="f642c-255">응용 프로그램 계층에는 세 개의 서버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-255">Three servers are included in the application tier.</span></span>
    
- <span data-ttu-id="f642c-256">첫 번째 서버에는 4개의 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-256">The first server includes four components.</span></span>
    
- <span data-ttu-id="f642c-257">두 번째 서버에는 세 가지 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-257">The second server includes three components.</span></span>
    
- <span data-ttu-id="f642c-258">세 번째 서버에는 두 개의 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-258">The third server includes two components.</span></span>
    
<span data-ttu-id="f642c-259">팜의 성능 및 용량 목표에 따라 구성 요소 수를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-259">You determine the number of components by the performance and capacity targets for the farm.</span></span> <span data-ttu-id="f642c-260">Azure에 맞게 이 아키텍처를 조정하기 위해 3개의 서버 모두에 네 가지 구성 요소를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-260">To adapt this architecture for Azure, we'll replicate the four components across all three servers.</span></span> <span data-ttu-id="f642c-261">이렇게 하면 성능 및 용량에 필요한 구성 요소 수를 초과하는 구성 요소 수가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-261">This increases the number of components beyond what is necessary for performance and capacity.</span></span> <span data-ttu-id="f642c-262">이 디자인은 이러한 세 개의 가상 컴퓨터를 가용성 집합에 할당할 때 Azure 플랫폼의 네 가지 구성 요소 모두의 고가용성을 보장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-262">The tradeoff is that this design ensures high availability of all four components in the Azure platform when these three virtual machines are assigned to an availability set.</span></span>
  
<span data-ttu-id="f642c-263">**그림 8: 미세 조정 후 응용 프로그램 서버 계층**</span><span class="sxs-lookup"><span data-stu-id="f642c-263">**Figure 8: Application server tier after fine tuning**</span></span>

![Microsoft Azure 가용성 집합에 대한 조정 후 SharePoint Server 2013 응용 프로그램 서버 계층 예](../media/AZarch-AppServtierAfter.png)
  
<span data-ttu-id="f642c-265">이 다이어그램은 동일한 4개의 구성 요소로 동일하게 구성된 세 개의 응용 프로그램 서버를 모두 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-265">This diagram shows all three application servers configured identically with the same four components.</span></span>
  
<span data-ttu-id="f642c-266">SharePoint 팜의 계층에 가용성 집합을 추가하면 구현이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-266">When we add availability sets to the tiers of the SharePoint farm, the implementation is complete.</span></span>
  
<span data-ttu-id="f642c-267">**그림 9: Azure 인프라 서비스의 완료된 SharePoint 팜**</span><span class="sxs-lookup"><span data-stu-id="f642c-267">**Figure 9: The completed SharePoint farm in Azure infrastructure services**</span></span>

![가상 네트워크, 크로스-프레미스 연결, 서브넷, VM 및 가용성 집합이 있는 Azure 인프라 서비스의 SharePoint 2013 팜 예제](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
<span data-ttu-id="f642c-269">이 다이어그램은 Azure 인프라 서비스에서 구현된 SharePoint 팜을 보여 주며, 각 계층의 서버에 장애 도메인을 제공하기 위한 가용성 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f642c-269">This diagram shows the SharePoint farm implemented in Azure infrastructure services, with availability sets to provide fault domains for the servers in each tier.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f642c-270">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f642c-270">See Also</span></span>

[<span data-ttu-id="f642c-271">Microsoft 365 솔루션 및 아키텍처 센터</span><span class="sxs-lookup"><span data-stu-id="f642c-271">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)
  
[<span data-ttu-id="f642c-272">SharePoint Server 2013을 사용하는 Microsoft Azure의 인터넷 사이트</span><span class="sxs-lookup"><span data-stu-id="f642c-272">Internet Sites in Microsoft Azure using SharePoint Server 2013</span></span>](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[<span data-ttu-id="f642c-273">Microsoft Azure에서 SharePoint Server 2013 재해 복구</span><span class="sxs-lookup"><span data-stu-id="f642c-273">SharePoint Server 2013 Disaster Recovery in Microsoft Azure</span></span>](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)


