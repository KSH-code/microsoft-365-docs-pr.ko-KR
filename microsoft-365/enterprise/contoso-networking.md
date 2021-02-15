---
title: Contoso Corporation에 대한 네트워킹
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 네트워킹 인프라와 회사에서 엔터프라이즈 클라우드 서비스용 Microsoft 365에 대한 최적의 네트워킹 성능을 위해 SD-WAN 기술을 사용하는 방법을 이해합니다.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754017"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="0386b-103">Contoso Corporation에 대한 네트워킹</span><span class="sxs-lookup"><span data-stu-id="0386b-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="0386b-p101">Contoso는 클라우드 포함 인프라를 채택하기 위해 클라우드 서비스로의 네트워크 트래픽이 이동하는 방식의 기본적인 변화를 고안했습니다. Office 계층 구조의 다음 수준에 대한 네트워크 연결 및 트래픽에 초점을 맞추는 내부 허브 및 스포크 모델 대신, 사용자 위치를 인터넷에서 가장 가까운 Microsoft 365 네트워크 위치에 대한 로컬 인터넷 발신 및 로컬 연결에 매핑했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-p101">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels. Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="0386b-106">네트워킹 인프라</span><span class="sxs-lookup"><span data-stu-id="0386b-106">Networking infrastructure</span></span>

<span data-ttu-id="0386b-107">다음은 전 세계 Contoso 사무실을 연결하는 네트워크 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="0386b-108">멀티 프로토콜 레이블 전환 (MPLS) WAN 네트워크</span><span class="sxs-lookup"><span data-stu-id="0386b-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="0386b-p102">MPLS WAN 네트워크는 스포크 및 허브 구성에서 파리 본사를 지역 사무소 및 지사에 위성 사무소에 연결합니다. 이 네트워크를 통해 사용자는 파리 본사에서 업무용 응용 프로그램을 구성하는 On-프레미스 서버에 액세스할 수 있습니다. 또한 일반 인터넷 트래픽을 파리 사무실로 라우팅하여 네트워크 보안 장치가 요청을 스크럽합니다. 각 사무실 내에서 라우터는 개인 IP 주소 공간을 사용하는 서브넷의 유선 호스트 또는 무선 액세스 지점으로 트래픽을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration. The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters. It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="0386b-113">Microsoft 365 트래픽에 대한 로컬 직접 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="0386b-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="0386b-p103">각 사무실에는 프록시 서버를 통해 자체 인터넷 연결이 있는 하나 이상의 로컬 인터넷 ISP 네트워크 회로가 있는 소프트웨어 정의 WAN(SD-WAN) 장치가 있습니다. 이 링크는 일반적으로 공용 IP 주소와 로컬 DNS 서버를 제공하는 로컬 ISP에 대한 WAN 링크로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-p103">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="0386b-116">인터넷 서비스</span><span class="sxs-lookup"><span data-stu-id="0386b-116">Internet presence</span></span>

  <span data-ttu-id="0386b-p104">Contoso는 contoso com 공용 도메인 \. 이름을 소유합니다. 제품 주문을 위한 Contoso 공용 웹 사이트는 파리 캠퍼스에 있는 인터넷에 연결된 데이터 센터에 있는 서버 집합입니다. Contoso는 인터넷에서 /24 공용 IP 주소 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-p104">Contoso owns the contoso\.com public domain name. The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="0386b-120">그림 1에서는 Contoso 네트워킹 인프라와 인터넷에 대한 연결을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Contoso 네트워크](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="0386b-122">**그림 1: Contoso 네트워크**</span><span class="sxs-lookup"><span data-stu-id="0386b-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="0386b-123">Microsoft에 대한 최적 네트워크 연결을 위해 SD-WAN 사용</span><span class="sxs-lookup"><span data-stu-id="0386b-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="0386b-124">Contoso는 다음과 같은 [Microsoft 365 네트워크 연결 원칙](microsoft-365-network-connectivity-principles.md)을 준수했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="0386b-125">Microsoft 365 네트워크 트래픽 식별 및 차별화</span><span class="sxs-lookup"><span data-stu-id="0386b-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="0386b-126">네트워크 연결을 로컬로 송신</span><span class="sxs-lookup"><span data-stu-id="0386b-126">Egress network connections locally</span></span>
- <span data-ttu-id="0386b-127">네트워크 헤어핀 방지</span><span class="sxs-lookup"><span data-stu-id="0386b-127">Avoid network hairpins</span></span>
- <span data-ttu-id="0386b-128">중복된 네트워크 보안 장치 우회</span><span class="sxs-lookup"><span data-stu-id="0386b-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="0386b-129">Microsoft 365의 네트워크 트래픽에는 *최적화,* 허용 및 기본값의 세 *가지* 범주가 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="0386b-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="0386b-130">최적화 및 허용 트래픽은 끝점에서 암호화 및 보호되고 Microsoft 365 네트워크로 전송되는 신뢰할 수 있는 네트워크 트래픽입니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="0386b-131">Contoso는 다음의 사항을 결정했습니다:</span><span class="sxs-lookup"><span data-stu-id="0386b-131">Contoso decided to:</span></span>

- <span data-ttu-id="0386b-132">최적화 및 허용 범주 트래픽에 대해 직접 인터넷 검색을 사용하여 모든 기본 범주 트래픽을 파리 기반 중앙 인터넷 연결로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="0386b-133">이러한 원칙을 따르고 Microsoft 365 클라우드 기반 서비스에 대해 최적의 네트워크 성능을 달성하기 위한 간단한 방법으로 각 사무실에 SD-WAN 장치를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="0386b-134">SD-WAN 장치에는 로컬 사무실 네트워크와 여러 대의 WAN 포트용 LAN 포트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="0386b-135">하나의 WAN 포트가 MPLS 네트워크에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="0386b-136">다른 회로는 로컬 ISP 회로에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="0386b-137">SD-WAN 장치는 ISP 링크를 통해 최적화 및 허용범주 네트워크 트래픽을 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="0386b-138">Contoso 업무(LINE-OF-BUSINESS) 앱 인프라</span><span class="sxs-lookup"><span data-stu-id="0386b-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="0386b-139">Contoso는 다음과 같은 업무용 응용 프로그램 및 서버 인트라넷 인프라를 설계했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="0386b-140">위성 사무소는 로컬 캐싱 서버를 사용하여 자주 액세스하는 문서 및 내부 웹 사이트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="0386b-p107">지역 허브는 지역 사무소와 위성 사무소에 지역 응용 프로그램 서버를 사용합니다. 이러한 서버는 파리 본사의 서버와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="0386b-143">파리 캠퍼스 데이터 센터에는 전체 조직에 서비스를 제공 하는 중앙 집중식 응용 프로그램 서버가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="0386b-144">그림 2에서는 Contoso 인트라넷을 통해 서버에 액세스할 때 사용되는 네트워크 트래픽 용량의 백분율을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![내부 응용 프로그램에 대한 Contoso 인프라](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="0386b-146">**그림 2: 내부 응용 프로그램에 대한 Contoso 인프라**</span><span class="sxs-lookup"><span data-stu-id="0386b-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="0386b-147">위성 또는 지역 허브 사무소의 경우 직원에게 필요한 리소스의 60%는 위성 및 지역 허브 사무소 서버에서 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="0386b-148">추가 리소스 요청의 40%는 WAN 링크를 통해 파리 캠퍼스로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="0386b-149">엔터프라이즈용 Microsoft 365에 대한 네트워크 분석 및 준비</span><span class="sxs-lookup"><span data-stu-id="0386b-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="0386b-150">Contoso 사용자가 엔터프라이즈용 Microsoft 365 서비스를 성공적으로 채택하는 경우 인터넷 또는 Microsoft 클라우드 서비스에 직접 연결하거나 고가용성에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="0386b-151">Contoso는 엔터프라이즈 클라우드 서비스용 Microsoft 365에 대한 최적화된 연결을 계획하고 구현하기 위해 다음 단계를 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="0386b-152">계획을 지원하기 위한 회사 WAN 네트워크 다이어그램 만들기</span><span class="sxs-lookup"><span data-stu-id="0386b-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="0386b-153">네트워크 계획을 시작하기 위해 Contoso는 자신의 사무실 위치, 기존 네트워크 연결, 기존 네트워크 경계 장치 및 네트워크에서 관리되는 서비스 클래스를 보여주는 다이어그램을 만들었다.</span><span class="sxs-lookup"><span data-stu-id="0386b-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="0386b-154">또한 네트워킹 연결 계획 및 구현의 각 후속 단계에서 이 다이어그램을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="0386b-155">엔터프라이즈용 Microsoft 365 네트워크 연결 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="0386b-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="0386b-156">Contoso는 [Microsoft 365](microsoft-365-network-connectivity-principles.md) 네트워크 연결 원칙 및 샘플 참조 네트워크 아키텍처를 사용하여 SD-WAN을 Microsoft 365 연결에 대한 기본 토폴로지로 식별했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="0386b-157">각 사무실에서 인터넷 연결 사용률 및 MPLS-WAN 대역폭을 분석하고 필요한 경우 대역폭 증가</span><span class="sxs-lookup"><span data-stu-id="0386b-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="0386b-158">각 사무실의 현재 사용량을 분석하고 예측된 Microsoft 365 클라우드 기반 트래픽이 평균 20%의 사용되지 않는 용량으로 작동할 수 있도록 회로가 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="0386b-159">Microsoft 네트워크 서비스에 대한 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="0386b-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="0386b-160">Contoso는 Office 365, Intune 및 Azure 끝점 집합을 결정하고 최적의 성능을 위해 인터넷 경로의 방화벽, 보안 장치 및 기타 시스템을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="0386b-161">Office 365 최적화 및 허용 범주 트래픽에 대한 끝점은 ISP 회로를 통해 라우팅하기 위해 SD-WAN 장치로 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="0386b-162">내부 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="0386b-162">Configure internal DNS</span></span>

   <span data-ttu-id="0386b-163">DNS가 작동해야 하고 Microsoft 365 트래픽 여부를 로컬에서 조회해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="0386b-164">네트워크 끝점 및 포트 연결 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0386b-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="0386b-165">Contoso는 Microsoft 네트워크 연결 테스트 도구를 실행하여 엔터프라이즈용 Microsoft 365 클라우드 서비스에 대한 연결의 유효성을 검사했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="0386b-166">네트워크 연결에 맞게 직원 컴퓨터 최적화</span><span class="sxs-lookup"><span data-stu-id="0386b-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="0386b-167">개별 컴퓨터에서 최신 운영 체제 업데이트가 설치되어 있으며 모든 클라이언트에서 끝점 보안 모니터링이 활성화되도록 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="0386b-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="0386b-168">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0386b-168">Next step</span></span>

<span data-ttu-id="0386b-169">Contoso가 직원을 위해 클라우드에서 해당온-프레미스 [Active Directory 도메인](contoso-identity.md) 서비스를 활용하고 고객 및 비즈니스 파트너에 대한 인증을 페더화하는 방법에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="0386b-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="0386b-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0386b-170">See also</span></span>

[<span data-ttu-id="0386b-171">Microsoft 365 네트워킹 로드맵</span><span class="sxs-lookup"><span data-stu-id="0386b-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="0386b-172">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="0386b-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="0386b-173">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="0386b-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
