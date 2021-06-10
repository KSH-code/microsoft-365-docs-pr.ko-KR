---
title: 네트워크용 네트워킹 로드맵 Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 네트워크 구성을 구현하기 위한 Microsoft 365 로드맵입니다.
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923555"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="811bd-103">네트워크용 네트워킹 로드맵 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="811bd-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="811bd-104">Microsoft 365 엔터프라이즈용 클라우드 서비스에는 공동 작업 및 생산성 클라우드 서비스, Microsoft Intune 및 여러 ID 및 보안 서비스가 Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="811bd-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="811bd-105">이러한 모든 클라우드 기반 서비스는 인터넷이나 전용 회선을 통해 클라이언트 장치의 연결 보안, 성능 및 안정성에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="811bd-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="811bd-106">Microsoft는 이러한 서비스를 호스팅하고 전 세계 고객이 사용할 수 있도록하기 위해 성능 및 통합을 중점을 둔 네트워킹 인프라를 설계했습니다.</span><span class="sxs-lookup"><span data-stu-id="811bd-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="811bd-107">사용자 온보 Microsoft 365 중요한 부분은 네트워크 및 인터넷 연결이 최적화된 액세스를 위해 설정되어 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="811bd-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="811bd-108">전역 분산 SaaS(Software-as-a-Service) 클라우드에 액세스하도록 사내 네트워크를 구성하는 것은 사내 데이터 센터 및 중앙 인터넷 연결에 대한 트래픽에 최적화된 기존 네트워크와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="811bd-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="811bd-109">이 문서를 사용하여 주요 차이점을 이해하고 에지 장치, 클라이언트 컴퓨터, 온-프레미스 네트워크를 수정하여 온-프레미스 사용자를 위한 최적의 성능을 구현하세요.</span><span class="sxs-lookup"><span data-stu-id="811bd-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="811bd-110">계획</span><span class="sxs-lookup"><span data-stu-id="811bd-110">Plan</span></span>

<span data-ttu-id="811bd-111">네트워킹 구현의 계획 단계에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="811bd-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="811bd-112">네트워크 Microsoft 365 방법 이해</span><span class="sxs-lookup"><span data-stu-id="811bd-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="811bd-113">현재 네트워크 연결 평가</span><span class="sxs-lookup"><span data-stu-id="811bd-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="811bd-114">ExpressRoute가 조직에 적합한지 확인</span><span class="sxs-lookup"><span data-stu-id="811bd-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="811bd-115">네트워크 장치 계획</span><span class="sxs-lookup"><span data-stu-id="811bd-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="811bd-116">마이그레이션을 위한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="811bd-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="811bd-117">배포</span><span class="sxs-lookup"><span data-stu-id="811bd-117">Deploy</span></span>

<span data-ttu-id="811bd-118">네트워킹 구현의 배포 단계에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="811bd-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="811bd-119">엔터프라이즈 네트워크가 연결에 최적화되어 Microsoft 365 확인</span><span class="sxs-lookup"><span data-stu-id="811bd-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="811bd-120">조직의 DNS 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="811bd-120">Add the DNS domains for your organization</span></span>](../admin/setup/add-domain.md)
- [<span data-ttu-id="811bd-121">끝점에 대한 Microsoft 365 최적화</span><span class="sxs-lookup"><span data-stu-id="811bd-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="811bd-122">원격 작업자에 대한 연결 최적화</span><span class="sxs-lookup"><span data-stu-id="811bd-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="811bd-123">필요한 경우 [ExpressRoute 구성](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="811bd-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="811bd-124">관리</span><span class="sxs-lookup"><span data-stu-id="811bd-124">Manage</span></span>

<span data-ttu-id="811bd-125">네트워킹 구현의 관리 단계에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="811bd-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="811bd-126">네트워크 장치가 최신 끝점을 사용하고 Office 365 확인</span><span class="sxs-lookup"><span data-stu-id="811bd-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="811bd-127">네트워킹 성능 모니터링 및 조정</span><span class="sxs-lookup"><span data-stu-id="811bd-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="811bd-128">ExpressRoute 연결 모니터링</span><span class="sxs-lookup"><span data-stu-id="811bd-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="811bd-129">네트워크 장비 공급업체</span><span class="sxs-lookup"><span data-stu-id="811bd-129">Network equipment vendors</span></span>

<span data-ttu-id="811bd-130">네트워크 장비 공급업체인 경우 에 [Microsoft 365 네트워킹 파트너 프로그램.](microsoft-365-networking-partner-program.md)</span><span class="sxs-lookup"><span data-stu-id="811bd-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="811bd-131">프로그램에 등록하여 Microsoft 365 솔루션에 대한 네트워크 연결 원칙을 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="811bd-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="811bd-132">Contoso가 2013에 대한 네트워킹을 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="811bd-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="811bd-133">가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스에 맞게 [네트워크 장치 및 인터넷 연결을 최적화](contoso-networking.md)한 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="811bd-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="811bd-135">다음 단계</span><span class="sxs-lookup"><span data-stu-id="811bd-135">Next step</span></span>

<span data-ttu-id="811bd-136">네트워킹 연결 개요를 Microsoft 365 [네트워킹 계획을 시작하세요.](microsoft-365-networking-overview.md)</span><span class="sxs-lookup"><span data-stu-id="811bd-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>