---
title: Azure에서 Microsoft 365용 고가용성 페더레이션 인증 배포
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: '요약: Microsoft Azure에서 Microsoft 365 구독에 대한 고가용성 페더타 인증을 구성합니다.'
ms.openlocfilehash: abe01445b8963dcdc5693b45a680e273f5084446
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692655"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a><span data-ttu-id="c71fb-103">Azure에서 Microsoft 365용 고가용성 페더레이션 인증 배포</span><span class="sxs-lookup"><span data-stu-id="c71fb-103">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>

<span data-ttu-id="c71fb-104">이 문서에는 이러한 가상 컴퓨터를 사용하는 Azure 인프라 서비스에서 Microsoft 365용 고가용성 페더링 인증을 배포하기 위한 단계별 지침에 대한 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-104">This article has links to the step-by-step instructions for deploying high availability federated authentication for Microsoft Microsoft 365 in Azure infrastructure services with these virtual machines:</span></span>
  
- <span data-ttu-id="c71fb-105">웹 응용 프로그램 프록시 서버 2개</span><span class="sxs-lookup"><span data-stu-id="c71fb-105">Two web application proxy servers</span></span>
    
- <span data-ttu-id="c71fb-106">AD FS(Active Directory Federation Services) 서버 2개</span><span class="sxs-lookup"><span data-stu-id="c71fb-106">Two Active Directory Federation Services (AD FS) servers</span></span>
    
- <span data-ttu-id="c71fb-107">복제본 도메인 컨트롤러 2개</span><span class="sxs-lookup"><span data-stu-id="c71fb-107">Two replica domain controllers</span></span>
    
- <span data-ttu-id="c71fb-108">Azure AD Connect를 실행하는 디렉터리 동기화 서버 1개</span><span class="sxs-lookup"><span data-stu-id="c71fb-108">One directory synchronization server running Azure AD Connect</span></span>
    
<span data-ttu-id="c71fb-109">다음은 각 서버에 대해 자리 표시자 이름이 사용된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-109">Here is the configuration, with placeholder names for each server.</span></span>
  
<span data-ttu-id="c71fb-110">**Azure의 Microsoft 365 인프라에 대한 고가용성 페더전 인증**</span><span class="sxs-lookup"><span data-stu-id="c71fb-110">**A high availability federated authentication for Microsoft 365 infrastructure in Azure**</span></span>

![Azure에서 고가용성 Microsoft 365 페더타 인증 인프라의 최종 구성](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="c71fb-112">모든 가상 컴퓨터는 단일 프레미스 간 Azure VNet(가상 네트워크)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-112">All of the virtual machines are in a single cross-premises Azure virtual network (VNet).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c71fb-p101">개별 사용자의 페더레이션 인증은 온-프레미스 리소스를 사용하지 않습니다. 그러나 프레미스 간 연결을 사용할 수 없게 되는 경우 VNet의 도메인 컨트롤러가 온-프레미스 Active Directory Domain Services(AD DS)에서 만든 사용자 계정 및 그룹에 대한 업데이트를 받을 수 없게 됩니다. 이 문제가 발생하지 않도록 하려면 프레미스 간 연결을 위한 고가용성을 구성하면 됩니다. 자세한 내용은 [항상 사용 가능한 프레미스 간 및 VNet 간 연결](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c71fb-p101">Federated authentication of individual users does not rely on any on-premises resources. However, if the cross-premises connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services (AD DS). To ensure this does not happen, you can configure high availability for your cross-premises connection. For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="c71fb-117">특정 역할에 대한 각 쌍의 가상 컴퓨터는 자체 서브넷 및 가용성 집합에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-117">Each pair of virtual machines for a specific role is in its own subnet and availability set.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c71fb-p102">이 VNet이 온-프레미스 네트워크에 연결되어 있으므로 이 구성에는 jumpbox 또는 관리 서브넷의 가상 컴퓨터 모니터링이 포함되지 않습니다. 자세한 내용은 [N 계층 아키텍처에 대해 Windows VM 실행](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c71fb-p102">Because this VNet is connected to the on-premises network, this configuration does not include jumpbox or monitoring virtual machines on a management subnet. For more information, see [Running Windows VMs for an N-tier architecture](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm).</span></span> 
  
<span data-ttu-id="c71fb-120">이 구성의 결과로 모든 Microsoft 365 사용자에 대해 페더전된 인증을 사용할 수 있습니다. 그러면 사용자가 Microsoft 365 계정이 아닌 AD DS 자격 증명을 사용하여 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-120">The result of this configuration is that you will have federated authentication for all of your Microsoft 365 users, in which they can use their AD DS credentials to sign in rather than their Microsoft 365 account.</span></span> <span data-ttu-id="c71fb-121">페더레이션 인증 인프라는 온-프레미스 경계 네트워크 대신 Azure 인프라 서비스에 더욱 쉽게 배포되는 중복 서버 집합을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-121">The federated authentication infrastructure uses a redundant set of servers that are more easily deployed in Azure infrastructure services, rather than in your on-premises edge network.</span></span>
  
## <a name="bill-of-materials"></a><span data-ttu-id="c71fb-122">제품 구성 정보(BOM)</span><span class="sxs-lookup"><span data-stu-id="c71fb-122">Bill of materials</span></span>

<span data-ttu-id="c71fb-123">이 기본 구성에는 다음과 같은 Azure 서비스 및 구성 요소 집합이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-123">This baseline configuration requires the following set of Azure services and components:</span></span>
  
- <span data-ttu-id="c71fb-124">가상 컴퓨터 7개</span><span class="sxs-lookup"><span data-stu-id="c71fb-124">Seven virtual machines</span></span>
    
- <span data-ttu-id="c71fb-125">4개의 서브넷이 있는 프레미스 간 가상 네트워크 1개</span><span class="sxs-lookup"><span data-stu-id="c71fb-125">One cross-premises virtual network with four subnets</span></span>
    
- <span data-ttu-id="c71fb-126">리소스 그룹 4개</span><span class="sxs-lookup"><span data-stu-id="c71fb-126">Four resource groups</span></span>
    
- <span data-ttu-id="c71fb-127">가용성 집합 3개</span><span class="sxs-lookup"><span data-stu-id="c71fb-127">Three availability sets</span></span>
    
- <span data-ttu-id="c71fb-128">Azure 구독 1개</span><span class="sxs-lookup"><span data-stu-id="c71fb-128">One Azure subscription</span></span>
    
<span data-ttu-id="c71fb-129">다음은 이 구성의 가상 컴퓨터 및 해당 기본 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-129">Here are the virtual machines and their default sizes for this configuration.</span></span>
  
|<span data-ttu-id="c71fb-130">**항목**</span><span class="sxs-lookup"><span data-stu-id="c71fb-130">**Item**</span></span>|<span data-ttu-id="c71fb-131">**가상 컴퓨터 설명**</span><span class="sxs-lookup"><span data-stu-id="c71fb-131">**Virtual machine description**</span></span>|<span data-ttu-id="c71fb-132">**Azure 갤러리 이미지**</span><span class="sxs-lookup"><span data-stu-id="c71fb-132">**Azure gallery image**</span></span>|<span data-ttu-id="c71fb-133">**기본 크기**</span><span class="sxs-lookup"><span data-stu-id="c71fb-133">**Default size**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c71fb-134">1.</span><span class="sxs-lookup"><span data-stu-id="c71fb-134">1.</span></span>  <br/> |<span data-ttu-id="c71fb-135">첫 번째 도메인 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="c71fb-135">First domain controller</span></span>  <br/> |<span data-ttu-id="c71fb-136">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c71fb-136">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c71fb-137">D2</span><span class="sxs-lookup"><span data-stu-id="c71fb-137">D2</span></span>  <br/> |
|<span data-ttu-id="c71fb-138">2.</span><span class="sxs-lookup"><span data-stu-id="c71fb-138">2.</span></span>  <br/> |<span data-ttu-id="c71fb-139">두 번째 도메인 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="c71fb-139">Second domain controller</span></span>  <br/> |<span data-ttu-id="c71fb-140">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c71fb-140">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c71fb-141">D2</span><span class="sxs-lookup"><span data-stu-id="c71fb-141">D2</span></span>  <br/> |
|<span data-ttu-id="c71fb-142">3.</span><span class="sxs-lookup"><span data-stu-id="c71fb-142">3.</span></span>  <br/> |<span data-ttu-id="c71fb-143">Azure AD Connect 서버</span><span class="sxs-lookup"><span data-stu-id="c71fb-143">Azure AD Connect server</span></span>  <br/> |<span data-ttu-id="c71fb-144">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c71fb-144">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c71fb-145">D2</span><span class="sxs-lookup"><span data-stu-id="c71fb-145">D2</span></span>  <br/> |
|<span data-ttu-id="c71fb-146">4.</span><span class="sxs-lookup"><span data-stu-id="c71fb-146">4.</span></span>  <br/> |<span data-ttu-id="c71fb-147">첫 번째 AD FS 서버</span><span class="sxs-lookup"><span data-stu-id="c71fb-147">First AD FS server</span></span>  <br/> |<span data-ttu-id="c71fb-148">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c71fb-148">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c71fb-149">D2</span><span class="sxs-lookup"><span data-stu-id="c71fb-149">D2</span></span>  <br/> |
|<span data-ttu-id="c71fb-150">5.</span><span class="sxs-lookup"><span data-stu-id="c71fb-150">5.</span></span>  <br/> |<span data-ttu-id="c71fb-151">두 번째 AD FS 서버</span><span class="sxs-lookup"><span data-stu-id="c71fb-151">Second AD FS server</span></span>  <br/> |<span data-ttu-id="c71fb-152">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c71fb-152">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c71fb-153">D2</span><span class="sxs-lookup"><span data-stu-id="c71fb-153">D2</span></span>  <br/> |
|<span data-ttu-id="c71fb-154">6.</span><span class="sxs-lookup"><span data-stu-id="c71fb-154">6.</span></span>  <br/> |<span data-ttu-id="c71fb-155">첫 번째 웹 응용 프로그램 프록시 서버</span><span class="sxs-lookup"><span data-stu-id="c71fb-155">First web application proxy server</span></span>  <br/> |<span data-ttu-id="c71fb-156">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c71fb-156">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c71fb-157">D2</span><span class="sxs-lookup"><span data-stu-id="c71fb-157">D2</span></span>  <br/> |
|<span data-ttu-id="c71fb-158">7.</span><span class="sxs-lookup"><span data-stu-id="c71fb-158">7.</span></span>  <br/> |<span data-ttu-id="c71fb-159">두 번째 웹 응용 프로그램 프록시 서버</span><span class="sxs-lookup"><span data-stu-id="c71fb-159">Second web application proxy server</span></span>  <br/> |<span data-ttu-id="c71fb-160">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c71fb-160">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c71fb-161">D2</span><span class="sxs-lookup"><span data-stu-id="c71fb-161">D2</span></span>  <br/> |
   
<span data-ttu-id="c71fb-162">이러한 구성에 대한 예상 비용을 계산하려면 [Azure 가격 계산기](https://azure.microsoft.com/pricing/calculator/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c71fb-162">To compute the estimated costs for this configuration, see the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/)</span></span>
  
## <a name="phases-of-deployment"></a><span data-ttu-id="c71fb-163">배포 단계</span><span class="sxs-lookup"><span data-stu-id="c71fb-163">Phases of deployment</span></span>

<span data-ttu-id="c71fb-164">이 작업은 다음과 같은 단계로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-164">You deploy this workload in the following phases:</span></span>
  
- <span data-ttu-id="c71fb-p104">[1단계: Azure 구성](high-availability-federated-authentication-phase-1-configure-azure.md). 리소스 그룹, 저장소 계정, 가용성 집합 및 프레미스 간 가상 네트워크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-p104">[Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md). Create resource groups, storage accounts, availability sets, and a cross-premises virtual network.</span></span>
    
- <span data-ttu-id="c71fb-167">[2단계: 도메인 컨트롤러 구성](high-availability-federated-authentication-phase-2-configure-domain-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="c71fb-167">[Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="c71fb-168">복제본 AD DS 도메인 컨트롤러를 디렉터리 동기화 서버를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-168">Create and configure replica AD DS domain controllers and the directory synchronization server.</span></span>
    
- <span data-ttu-id="c71fb-p106">[3단계: AD FS 서버 구성](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). 2개의 AD FS 서버를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-p106">[Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Create and configure the two AD FS servers.</span></span>
    
- <span data-ttu-id="c71fb-p107">[4단계: 웹 응용 프로그램 프록시 구성](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). 2개의 웹 응용 프로그램 프록시 서버를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-p107">[Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). Create and configure the two web application proxy servers.</span></span>
    
- <span data-ttu-id="c71fb-173">[5단계: Microsoft 365에](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)대한 페더타 인증을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-173">[Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="c71fb-174">Microsoft 365 구독에 대한 페더타 인증을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-174">Configure federated authentication for your Microsoft 365 subscription.</span></span>
    
<span data-ttu-id="c71fb-175">이러한 문서에서는 Azure 인프라 서비스에서 Microsoft 365에 대한 기능적인 고가용성 페더레이드 인증을 만들기 위한 미리 정의된 아키텍처에 대한 단계적 프레미스 가이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-175">These articles provide a prescriptive, phase-by-phase guide for a predefined architecture to create a functional, high availability federated authentication for Microsoft 365 in Azure infrastructure services.</span></span> <span data-ttu-id="c71fb-176">다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-176">Keep the following in mind:</span></span>
  
- <span data-ttu-id="c71fb-177">숙련된 AD FS 구현자인 경우 3~4단계의 지침을 적용하고 본인의 요구에 가장 적합한 서버 집합을 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-177">If you are an experienced AD FS implementer, feel free to adapt the instructions in phases 3 and 4 and build the set of servers that best suits your needs.</span></span>
    
- <span data-ttu-id="c71fb-178">기존 프레미스 간 가상 네트워크와 함께 기존 Azure 하이브리드 클라우드 배포가 이미 있는 경우에는 1-2단계의 지침을 적용하거나 건너뛰고, 적절한 서브넷에 AD FS 및 웹 응용 프로그램 프록시 서버를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-178">If you already have an existing Azure hybrid cloud deployment with an existing cross-premises virtual network, feel free to adapt or skip the instructions in phases 1 and 2 and place the AD FS and web application proxy servers on the appropriate subnets.</span></span>
    
<span data-ttu-id="c71fb-179">이 구성의 개발/테스트 환경 또는 개념 증명을 빌드하려면 [Microsoft 365 개발/테스트](federated-identity-for-your-microsoft-365-dev-test-environment.md)환경의 페더티된 ID를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-179">To build a dev/test environment or a proof-of-concept of this configuration, see [Federated identity for your Microsoft 365 dev/test environment](federated-identity-for-your-microsoft-365-dev-test-environment.md).</span></span>
  
## <a name="next-step"></a><span data-ttu-id="c71fb-180">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c71fb-180">Next step</span></span>

<span data-ttu-id="c71fb-181">[1단계: Azure 구성](high-availability-federated-authentication-phase-1-configure-azure.md)으로 이 작업의 구성을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c71fb-181">Start the configuration of this workload with [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> 
  
