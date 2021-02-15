---
title: Microsoft 365에 대한 네트워킹 로드맵
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
description: Microsoft 365 네트워킹 구현 로드맵입니다.
ms.openlocfilehash: 2962adf7bdca35d06672696471e0932fd1a7b09c
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787754"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="d0636-103">Microsoft 365에 대한 네트워킹 로드맵</span><span class="sxs-lookup"><span data-stu-id="d0636-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="d0636-104">엔터프라이즈용 Microsoft 365에는 공동 작업 및 생산성 클라우드 서비스, Microsoft Intune 및 Microsoft Azure의 많은 ID 및 보안 서비스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="d0636-105">이러한 모든 클라우드 기반 서비스는 인터넷이나 전용 회선을 통해 클라이언트 장치의 연결 보안, 성능 및 안정성에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="d0636-106">Microsoft는 이러한 서비스를 호스팅하고 전 세계 고객이 사용할 수 있도록하기 위해 성능 및 통합을 중점을 둔 네트워킹 인프라를 설계했습니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="d0636-107">Microsoft 365 온보더링의 중요한 부분은 네트워크 및 인터넷 연결이 최적화된 액세스를 위해 설정되도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="d0636-108">전역으로 분산된 SaaS(Software-as-a-Service) 클라우드에 액세스하도록 On-premises 네트워크를 구성하는 것은,프레미스 데이터 센터 및 중앙 인터넷 연결에 대한 트래픽에 최적화된 기존 네트워크와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="d0636-109">이 문서를 사용하여 주요 차이점을 이해하고 에지 장치, 클라이언트 컴퓨터, 온-프레미스 네트워크를 수정하여 온-프레미스 사용자를 위한 최적의 성능을 구현하세요.</span><span class="sxs-lookup"><span data-stu-id="d0636-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="d0636-110">계획</span><span class="sxs-lookup"><span data-stu-id="d0636-110">Plan</span></span>

<span data-ttu-id="d0636-111">네트워킹 구현 계획 단계에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="d0636-112">Microsoft 365 네트워킹의 작동 방식 이해</span><span class="sxs-lookup"><span data-stu-id="d0636-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="d0636-113">현재 네트워크 연결 평가</span><span class="sxs-lookup"><span data-stu-id="d0636-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="d0636-114">ExpressRoute가 조직에 적합한지 확인</span><span class="sxs-lookup"><span data-stu-id="d0636-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="d0636-115">네트워크 장치 계획</span><span class="sxs-lookup"><span data-stu-id="d0636-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="d0636-116">마이그레이션을 위한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="d0636-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="d0636-117">배포</span><span class="sxs-lookup"><span data-stu-id="d0636-117">Deploy</span></span>

<span data-ttu-id="d0636-118">네트워킹 구현의 배포 단계에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="d0636-119">엔터프라이즈 네트워크가 Microsoft 365 연결에 최적화되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d0636-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="d0636-120">조직의 DNS 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="d0636-120">Add the DNS domains for your organization</span></span>](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [<span data-ttu-id="d0636-121">Microsoft 365 끝점에 대한 연결 최적화</span><span class="sxs-lookup"><span data-stu-id="d0636-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="d0636-122">원격 작업자를 위한 연결 최적화</span><span class="sxs-lookup"><span data-stu-id="d0636-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="d0636-123">필요한 경우 [ExpressRoute 구성](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="d0636-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="d0636-124">관리</span><span class="sxs-lookup"><span data-stu-id="d0636-124">Manage</span></span>

<span data-ttu-id="d0636-125">네트워킹 구현의 관리 단계에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="d0636-126">네트워크 장치가 최신 Office 365 끝점을 사용하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d0636-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="d0636-127">네트워킹 성능 모니터링 및 조정</span><span class="sxs-lookup"><span data-stu-id="d0636-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="d0636-128">ExpressRoute 연결 모니터링</span><span class="sxs-lookup"><span data-stu-id="d0636-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="d0636-129">네트워크 장비 공급업체</span><span class="sxs-lookup"><span data-stu-id="d0636-129">Network equipment vendors</span></span>

<span data-ttu-id="d0636-130">네트워크 장비 공급업체인 경우 [Microsoft 365](microsoft-365-networking-partner-program.md)네트워킹 파트너 프로그램에 가입하세요.</span><span class="sxs-lookup"><span data-stu-id="d0636-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="d0636-131">프로그램에 등록하여 제품 및 솔루션에 Microsoft 365 네트워크 연결 원칙을 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="d0636-132">Contoso에서 Microsoft 365에 대한 네트워킹을 한 방법</span><span class="sxs-lookup"><span data-stu-id="d0636-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="d0636-133">가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스에 맞게 [네트워크 장치 및 인터넷 연결을 최적화](contoso-networking.md)한 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d0636-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="d0636-135">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d0636-135">Next step</span></span>

<span data-ttu-id="d0636-136">[Microsoft 365](microsoft-365-networking-overview.md)네트워킹 연결 개요를 통해 네트워킹 계획을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="d0636-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>
