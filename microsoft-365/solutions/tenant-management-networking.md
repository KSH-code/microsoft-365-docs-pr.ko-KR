---
title: 2단계. 엔터프라이즈 테넌트용 Microsoft 365에 대한 최적의 네트워킹
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 테넌트에 대한 네트워크 액세스를 최적화합니다.
ms.openlocfilehash: 5eac0793d2afc924a919671ffa105362ea1866d9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407195"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="087fe-104">2단계.</span><span class="sxs-lookup"><span data-stu-id="087fe-104">Step 2.</span></span> <span data-ttu-id="087fe-105">엔터프라이즈 테넌트용 Microsoft 365에 대한 최적의 네트워킹</span><span class="sxs-lookup"><span data-stu-id="087fe-105">Optimal networking for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="087fe-106">엔터프라이즈용 Microsoft 365에는 Teams 및 Exchange Online과 같은 클라우드 생산성 앱과 Microsoft Intune이 포함되어 있으며, Microsoft Azure의 ID 및 보안 서비스가 많이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-106">Microsoft 365 for enterprise includes cloud productivity apps such as Teams and Exchange Online, and Microsoft Intune, along with many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="087fe-107">이러한 모든 클라우드 기반 서비스는 인터넷의 모든 위치에 있는 클라이언트 장치의 연결 보안, 성능 및 안정성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-107">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices on your on-premises network or any location on the Internet.</span></span> 

<span data-ttu-id="087fe-108">테넌트에 대한 네트워크 액세스를 최적화하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-108">To optimize network access for your tenant, you need to:</span></span>

- <span data-ttu-id="087fe-109">Microsoft 전역 네트워크에 가장 가까운 위치와의 경로를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-109">Optimize the path between your on-premises users and the closest location to the Microsoft Global Network.</span></span>
- <span data-ttu-id="087fe-110">원격 액세스 VPN 솔루션을 사용하는 원격 사용자를 위해 Microsoft 전역 네트워크에 대한 액세스를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-110">Optimize access to the Microsoft Global Network for your remote users that are using a remote access VPN solution.</span></span>
- <span data-ttu-id="087fe-111">네트워크 인사이트를 사용하여 사무실 위치의 네트워크 경계를 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-111">Use Network Insights to design the network perimeter for your office locations.</span></span>
- <span data-ttu-id="087fe-112">Office 365 CDN을 사용하여 SharePoint 사이트에서 호스트되는 특정 자산에 대한 액세스를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-112">Optimize access to specific assets hosted on SharePoint sites with the Office 365 CDN.</span></span>
- <span data-ttu-id="087fe-113">끝점 목록이 있는 Microsoft 365 트러스트된 트래픽에 대한 처리를 무시하도록 프록시 및 네트워크 에지 장치를 구성하고 변경이 진행되면 목록 업데이트를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-113">Configure proxy and network edge devices to bypass processing for Microsoft 365 trusted traffic with the list of endpoints and automate the updating of the list as changes are made.</span></span>

## <a name="enterprise-on-premises-workers"></a><span data-ttu-id="087fe-114">엔터프라이즈 사내 작업자</span><span class="sxs-lookup"><span data-stu-id="087fe-114">Enterprise on-premises workers</span></span>

<span data-ttu-id="087fe-115">엔터프라이즈 네트워크의 경우 클라이언트와 가장 가까운 Microsoft 365 끝점 간에 최고 성능의 네트워크 액세스를 사용하도록 설정하여 최종 사용자 환경을 최적화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-115">For enterprise networks, you should optimize the end user experience by enabling the highest-performing network access between clients and the closest Microsoft 365 endpoints.</span></span> <span data-ttu-id="087fe-116">최종 사용자 환경의 품질은 사용자가 사용하는 응용 프로그램의 성능 및 응답 성능과 직접적인 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-116">The quality of end user experience is directly related to the performance and responsiveness of the application that the user is using.</span></span> <span data-ttu-id="087fe-117">예를 들어 Microsoft Teams는 짧은 대기 시간을 통해 사용자 전화 통화, 회의 및 공유 화면 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-117">For example, Microsoft Teams relies on low latency so that user phone calls, conferences and shared screen collaborations are glitch-free.</span></span>

<span data-ttu-id="087fe-118">네트워크 디자인의 기본 목표는 클라이언트 장치에서 Microsoft 전역 네트워크로의 RTT(왕복 시간)를 줄이면서 대기 시간이 짧은 모든 Microsoft의 데이터 센터를 전 세계에 분산된 낮은 대기 시간, 고가용성 클라우드 응용 프로그램 진입점과 상호 연결하는 Microsoft의 공용 네트워크 백본으로의 RTT(왕복 시간)를 최소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-118">The primary goal in the network design should be to minimize latency by reducing the round-trip time (RTT) from client devices to the Microsoft Global Network, Microsoft's public network backbone that interconnects all of Microsoft's datacenters with low latency, high availability cloud application entry points, known as front doors, spread around the world.</span></span>

<span data-ttu-id="087fe-119">다음은 기존 엔터프라이즈 네트워크의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-119">Here is an example of a traditional enterprise network.</span></span>

![인터넷에 대한 중앙 액세스가 있는 기존 엔터프라이즈 네트워크](../media/tenant-management-overview/tenant-management-networking-traditional.png)

<span data-ttu-id="087fe-121">이 그림에서 지점은 WAN(Wide Area Network) 장치 및 WAN 백본을 통해 중앙 사무실에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-121">In this illustration, branch offices connect to a central office through wide area network (WAN) devices and a WAN backbone.</span></span> <span data-ttu-id="087fe-122">인터넷 액세스는 중앙 사무실의 네트워크 에지 및 ISP(인터넷 서비스 공급자)의 보안 또는 프록시 장치를 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-122">Internet access is through a security or proxy device at the network edge of the central office and an Internet service provider (ISP).</span></span> <span data-ttu-id="087fe-123">인터넷에서 Microsoft 전역 네트워크에는 전 세계 지역에 일련의 정문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-123">On the Internet, the Microsoft Global Network has a series of front doors in regions around the world.</span></span> <span data-ttu-id="087fe-124">조직은 또한 트래픽에 대한 추가 패킷 처리 및 보안을 위해 중간 위치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-124">Organizations can also use intermediate locations for additional packet processing and security for traffic.</span></span> <span data-ttu-id="087fe-125">조직의 Microsoft 365 테넌트는 Microsoft 전역 네트워크 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-125">An organization's Microsoft 365 tenant is located within the Microsoft Global Network.</span></span>

<span data-ttu-id="087fe-126">Microsoft 365 클라우드 서비스에 대한 이 구성의 문제는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-126">The problems with this configuration for Microsoft 365 cloud services are:</span></span>

- <span data-ttu-id="087fe-127">지사 사용자의 경우 트래픽이 로컬이 아닌 정문으로 전송되고 대기 시간이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-127">For users in branch offices, traffic gets sent to non-local front doors, increasing latency.</span></span>
- <span data-ttu-id="087fe-128">중간 위치에 트래픽을 보내면 신뢰할 수 있는 트래픽에 대해 중복된 패킷 처리를 수행하여 대기 시간이 증가하는 네트워크 헤어피가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-128">Sending traffic to intermediate locations create network hairpins that perform duplicate packet processing on trusted traffic, increasing latency.</span></span>
- <span data-ttu-id="087fe-129">네트워크 에지 장치는 신뢰할 수 있는 트래픽에 대해 원치 않는 중복 패킷 처리를 수행하여 대기 시간을 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-129">Network edge devices perform unneeded and duplicate packet processing on trusted traffic, increasing latency.</span></span>

<span data-ttu-id="087fe-130">Microsoft 365 네트워크 성능을 최적화하는 것은 복잡할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-130">Optimizing Microsoft 365 network performance doesn't need to be complicated.</span></span> <span data-ttu-id="087fe-131">다음과 같은 몇 가지 주요 원칙에 따라 최상의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-131">You can get the best possible performance by following a few key principles:</span></span>

- <span data-ttu-id="087fe-132">Microsoft 클라우드 서비스로 연결되는 신뢰할 수 있는 트래픽인 Microsoft 365 네트워크 트래픽을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-132">Identify Microsoft 365 network traffic, which is trusted traffic destined to Microsoft cloud services.</span></span>
- <span data-ttu-id="087fe-133">사용자가 Microsoft 365에 연결하는 각 위치에서 인터넷으로의 Microsoft 365 네트워크 트래픽의 로컬 분기를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-133">Allow local branch egress of Microsoft 365 network traffic to the internet from each location where users connect to Microsoft 365.</span></span>
- <span data-ttu-id="087fe-134">네트워크 헤어피를 피합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-134">Avoid network hairpins.</span></span>
- <span data-ttu-id="087fe-135">Microsoft 365 트래픽이 Proxies 및 패킷 검사 장치를 무시하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-135">Allow Microsoft 365 traffic to bypass proxies and packet inspection devices.</span></span>

<span data-ttu-id="087fe-136">이러한 원칙을 구현하면 Microsoft 365에 최적화된 엔터프라이즈 네트워크를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-136">If you implement these principles, you get an enterprise network optimized for Microsoft 365.</span></span>

![Microsoft 365에 최적화된 엔터프라이즈 네트워크](../media/tenant-management-overview/tenant-management-networking-optimized.png)

<span data-ttu-id="087fe-138">이 그림에서 지사는 신뢰할 수 있는 Microsoft 365 트래픽을 지역적으로 가장 가까운 프런트 도어로 보내는 소프트웨어 정의 WAN 장치(SDWAN) 장치를 통해 자체 인터넷에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-138">In this illustration, branch offices have their own Internet connection through a software-defined WAN device (SDWAN) device, which sends trusted Microsoft 365 traffic to the regionally closest front door.</span></span> <span data-ttu-id="087fe-139">중앙 사무실에서 신뢰할 수 있는 Microsoft 365 트래픽은 보안 또는 프록시 장치를 우회하고 중간 장치는 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-139">At the central office, trusted Microsoft 365 traffic bypasses the security or proxy device and intermediate devices are no longer used.</span></span>

<span data-ttu-id="087fe-140">다음은 최적화된 구성으로 기존 엔터프라이즈 네트워크의 대기 시간 문제를 해결하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-140">Here's are how the optimized configuration solves the latency issues of a traditional enterprise network:</span></span>

- <span data-ttu-id="087fe-141">신뢰할 수 있는 Microsoft 365 트래픽은 WAN 백본을 건너뛰고 모든 사무실의 로컬 프론트 도어로 전송됩니다. 이 경우 대기 시간이 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-141">Trusted Microsoft 365 traffic skips the WAN backbone and is sent to local front doors for all offices, decreasing latency.</span></span>
- <span data-ttu-id="087fe-142">중복 패킷 처리를 수행하는 네트워크 헤어피는 Microsoft 365의 신뢰할 수 있는 트래픽에 대해 건너뜁니다. 이 경우 대기 시간이 줄어 니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-142">Network hairpins that perform duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>
- <span data-ttu-id="087fe-143">Microsoft 365 신뢰할 수 있는 트래픽에 대해 원치 않는 중복 패킷 처리를 수행하는 네트워크 에지 장치를 건너뜁니다. 이 경우 대기 시간이 줄어 니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-143">Network edge devices that perform unneeded and duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>

<span data-ttu-id="087fe-144">자세한 내용은 [Microsoft 365 네트워크 연결 개요 를 참조하세요.](../enterprise/microsoft-365-networking-overview.md)</span><span class="sxs-lookup"><span data-stu-id="087fe-144">For more information, see [Microsoft 365 network connectivity overview](../enterprise/microsoft-365-networking-overview.md).</span></span>

## <a name="remote-workers"></a><span data-ttu-id="087fe-145">원격 작업자</span><span class="sxs-lookup"><span data-stu-id="087fe-145">Remote workers</span></span>

<span data-ttu-id="087fe-146">원격 작업자가 기존 VPN 클라이언트를 사용하 여 조직 네트워크에 대한 원격 액세스 권한을 얻는 경우, VPN 클라이언트에 분할 터널링 지원이 되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-146">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span> <span data-ttu-id="087fe-147">분할 터널링을 사용하지 않는 경우에는 모든 원격 작업 트래픽이 조직의 에지 장치로 전송되어 처리된 후 인터넷으로 전송되지 않고 VPN 연결을 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-147">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span> <span data-ttu-id="087fe-148">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-148">Here is an example.</span></span>

![터널링이 없는 VPN 클라이언트의 네트워크 트래픽](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="087fe-150">이 그림에서 Microsoft 365 트래픽은 조직을 통해 간접 경로를 취해야 합니다. 이 경로는 VPN 클라이언트의 물리적 위치에서 멀리 떨어져 있는 Microsoft 전역 네트워크 정문으로 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-150">In this illustration, Microsoft 365 traffic must take an indirect route through your organization, which could be forwarded to a Microsoft Global Network front door far away from the VPN client’s physical location.</span></span> <span data-ttu-id="087fe-151">이 간접 경로는 네트워크 트래픽에 대기 시간을 더하여 전반적인 성능을 저하시킵니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-151">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="087fe-152">분할 터널링을 사용할 경우, 사용자는 특정 유형의 트래픽을 제외하여 VPN 연결을 통해 조직 네트워크에 보내지 않도록 VPN 클라이언트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-152">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="087fe-153">Microsoft 365 클라우드 리소스에 대한 액세스를 최적화하려면 VPN 연결을 통해 범주 **최적화** Microsoft 365 끝점으로의 트래픽을 제외하도록 분할 터널링 VPN 클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-153">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="087fe-154">자세한 내용은 [Office 365 끝점](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) 범주 [](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) 및 분할 터널링에 대한 범주 끝점 최적화 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="087fe-154">For more information, see [Office 365 endpoint categories](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) and [the lists](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) of Optimize category endpoints for split tunneling.</span></span>

<span data-ttu-id="087fe-155">다음은 분할 터널링에 대한 결과 트래픽 흐름으로, Microsoft 365 클라우드 앱에 대한 트래픽의 대부분이 VPN 연결을 우회하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-155">Here is the resulting traffic flow for split tunneling, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![터널링이 있는 VPN 클라이언트에서의 네트워크 트래픽](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="087fe-157">이 그림에서 VPN 클라이언트는 인터넷을 통해 직접 중요한 Microsoft 365 클라우드 서비스 트래픽을 보내고 수신하며 가장 가까운 정문을 Microsoft 글로벌 네트워크로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-157">In this illustration, the VPN client sends and receives crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest front door into the Microsoft Global Network.</span></span>

<span data-ttu-id="087fe-158">자세한 내용과 지침은 [VPN 분산 터널링을 사용한 원격 근무자의 Office 365 연결 최적화](../enterprise/microsoft-365-vpn-split-tunnel.md)를 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="087fe-158">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

## <a name="using-network-insights-preview"></a><span data-ttu-id="087fe-159">네트워크 인사이트 사용(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="087fe-159">Using Network Insights (preview)</span></span>

<span data-ttu-id="087fe-160">네트워크 인사이트는 사무실 위치의 네트워크 경계를 디자인하는 데 도움이 되는 Microsoft 365 테넌트에서 수집된 성능 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-160">Network insights are performance metrics collected from your Microsoft 365 tenant that help you design network perimeters for your office locations.</span></span> <span data-ttu-id="087fe-161">각 인사이트는 사내 사용자가 테넌트에 액세스하는 각 지리적 위치에 대해 지정된 문제의 성능 특성에 대한 실시간 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-161">Each insight provides live details about the performance characteristics for a specified issue for each geographic location where on-premises users are accessing your tenant.</span></span>

<span data-ttu-id="087fe-162">테넌트에 대해 표시될 수 있는 두 가지 테넌트 수준 네트워크 인사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-162">There are two tenant level network insights that may be shown for the tenant:</span></span>

- [<span data-ttu-id="087fe-163">연결 문제의 영향을 미치는 Exchange 샘플링된 연결</span><span class="sxs-lookup"><span data-stu-id="087fe-163">Exchange sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="087fe-164">연결 문제의 영향을 미치는 SharePoint 샘플링된 연결</span><span class="sxs-lookup"><span data-stu-id="087fe-164">SharePoint sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

<span data-ttu-id="087fe-165">다음은 각 사무실 위치에 대한 특정 네트워크 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-165">These are the specific network insights for each office location:</span></span>

- [<span data-ttu-id="087fe-166">백hauled 네트워크 유선</span><span class="sxs-lookup"><span data-stu-id="087fe-166">Backhauled network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [<span data-ttu-id="087fe-167">가까운 고객을 위해 검색된 성능 향상</span><span class="sxs-lookup"><span data-stu-id="087fe-167">Better performance detected for customers near you</span></span>](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="087fe-168">최적의 Exchange Online 서비스 프런트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="087fe-168">Use of a non-optimal Exchange Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="087fe-169">최적의 SharePoint Online 서비스 프런트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="087fe-169">Use of a non-optimal SharePoint Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="087fe-170">SharePoint 프런트 도어에서 낮은 다운로드 속도</span><span class="sxs-lookup"><span data-stu-id="087fe-170">Low download speed from SharePoint front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="087fe-171">중국 사용자 최적의 네트워크 유출</span><span class="sxs-lookup"><span data-stu-id="087fe-171">China user optimal network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
><span data-ttu-id="087fe-172">Microsoft 365 관리 센터의 네트워크 인사이트, 성능 권장 사항 및 평가는 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-172">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status.</span></span> <span data-ttu-id="087fe-173">기능 미리 보기 프로그램에 등록된 Microsoft 365 테넌트에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-173">It is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

<span data-ttu-id="087fe-174">자세한 내용은 [Microsoft 365 Network Insights를 참조하세요.](../enterprise/office-365-network-mac-perf-insights.md)</span><span class="sxs-lookup"><span data-stu-id="087fe-174">For more information, see [Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md).</span></span>

## <a name="sharepoint-performance-with-the-office-365-cdn"></a><span data-ttu-id="087fe-175">Office 365 CDN을 사용하여 SharePoint 성능</span><span class="sxs-lookup"><span data-stu-id="087fe-175">SharePoint performance with the Office 365 CDN</span></span>

<span data-ttu-id="087fe-176">클라우드 기반 CDN(콘텐츠 배달 네트워크)을 사용하면 로드 시간을 줄이고, 대역폭을 절약하고, 응답 속도를 단축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-176">A cloud-based Content Delivery Network (CDN) allows you to reduce load times, save bandwidth, and speed responsiveness.</span></span> <span data-ttu-id="087fe-177">CDN은 그래픽 또는 비디오 파일과 같은 정적 자산을 요청하는 브라우저에 더 가깝게 캐싱하여 성능을 향상하여 다운로드 속도를 높이고 대기 시간을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-177">A CDN improves performance by caching static assets such as graphic or video files closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="087fe-178">Microsoft 365 E3 및 E5의 SharePoint에 포함된 기본 제공 Office 365 CDN(콘텐츠 배달 네트워크)을 사용하여 정적 자산을 호스트하여 SharePoint 페이지에 대한 성능을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-178">You can use the built-in Office 365 Content Delivery Network (CDN), included with SharePoint in Microsoft 365 E3 and E5, to host static assets to provide better performance for your SharePoint pages.</span></span>

<span data-ttu-id="087fe-179">Office 365 CDN은 여러 위치, 즉 _출발지_ 에 정적 자산을 호스트하고 글로벌 고속 네트워크에서 제공할 수 있는 여러 CDN으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-179">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="087fe-180">Office 365 CDN에서 호스팅하려는 콘텐츠의 종류에 따라 공개  출처, 비공개  출처 또는 둘 다를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-180">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins, or both.</span></span>

<span data-ttu-id="087fe-181">배포 및 구성 시 Office 365 CDN은 공용 및 개인 출처에서 자산을 업로드하고 인터넷을 통해 사용자에게 빠르게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-181">When deployed and configured, the Office 365 CDN uploads assets from public and private origins and makes them available for fast access to users located across the Internet.</span></span>

<span data-ttu-id="087fe-182">![사용자를 위해 배포된 Office 365 CDN](../media/O365-CDN/o365-cdn-flow-transparent.svg "사용자를 위해 배포된 Office 365 CDN")</span><span class="sxs-lookup"><span data-stu-id="087fe-182">![Office 365 CDN deployed for users](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN deployed for users")</span></span>

<span data-ttu-id="087fe-183">자세한 내용은 [SharePoint Online에서 Office 365 CDN 사용을 참조하세요.](../enterprise/use-microsoft-365-cdn-with-spo.md)</span><span class="sxs-lookup"><span data-stu-id="087fe-183">For more information, see [Use the Office 365 CDN with SharePoint Online](../enterprise/use-microsoft-365-cdn-with-spo.md).</span></span>

## <a name="automated-endpoint-listing"></a><span data-ttu-id="087fe-184">자동화된 끝점 목록</span><span class="sxs-lookup"><span data-stu-id="087fe-184">Automated endpoint listing</span></span>

<span data-ttu-id="087fe-185">사내 클라이언트, 에지 장치 및 클라우드 기반 패킷 분석 서비스가 신뢰할 수 있는 Microsoft 365 트래픽 처리를 건너뛰도록 Microsoft 365 서비스에 해당하는 끝점 집합(IP 주소 범위 및 DNS 이름)으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-185">To have your on-premises clients, edge devices, and cloud-based packet analysis services skip processing of trusted Microsoft 365 traffic, you must configure them with the set of endpoints (IP address ranges and DNS names) corresponding to Microsoft 365 services.</span></span> <span data-ttu-id="087fe-186">이러한 끝점은 방화벽 및 기타 에지 보안 장치에서 수동으로 구성할 수 있으며, 클라이언트 컴퓨터의 PAC 파일로는 팩스를 무시하거나 지사에서 SD-WAN 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-186">These endpoints can be manually configured in firewalls and other edge security devices, PAC files for client computers to bypass proxies, or SD-WAN devices at branch offices.</span></span> <span data-ttu-id="087fe-187">그러나 끝점은 시간이 지날 때 변경되어 이러한 위치에서 끝점 목록을 수동으로 수동으로 유지 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-187">However, the endpoints change over time, requiring ongoing manual maintenance of the endpoint lists in these locations.</span></span>

<span data-ttu-id="087fe-188">클라이언트 PAC 파일 및 네트워크 장치에서 Microsoft 365 끝점에 대한 목록 및 변경 관리를 자동화하려면 [Office 365 IP 주소](../enterprise/microsoft-365-ip-web-service.md)및 URL REST 기반 웹 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-188">To automate the listing and change management for Microsoft 365 endpoints in your client PAC files and network devices, use the [Office 365 IP Address and URL REST-based web service](../enterprise/microsoft-365-ip-web-service.md).</span></span> <span data-ttu-id="087fe-189">이 서비스를 사용하면 Microsoft 365 네트워크 트래픽을 보다 잘 식별하고 차별화할 수 있어 최신 변경 내용을 보다 쉽게 평가, 구성 및 최신으로 유지 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-189">This service helps you better identify and differentiate Microsoft 365 network traffic, making it easier for you to evaluate, configure, and stay current with the latest changes.</span></span>

<span data-ttu-id="087fe-190">PowerShell, Python 또는 기타 언어를 사용하여 시간이 지날 때 끝점에 대한 변경 내용을 결정하고 PAC 파일 및 에지 네트워크 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-190">You can use PowerShell, Python, or other languages to determine the changes to endpoints over time and configure your PAC files and edge network devices.</span></span>

<span data-ttu-id="087fe-191">기본 프로세스는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-191">The basic process is:</span></span>

1. <span data-ttu-id="087fe-192">Office 365 IP 주소 및 URL 웹 서비스 및 선택한 구성 메커니즘을 사용하여 현재 Microsoft 365 끝점 집합으로 PAC 파일 및 네트워크 장치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-192">Use the Office 365 IP Address and URL web service and the configuration mechanism of your choice to configure your PAC files and network devices with the current set of Microsoft 365 endpoints.</span></span>
2. <span data-ttu-id="087fe-193">매일 다시 실행하여 끝점의 변경 내용을 확인하거나 알림 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-193">Run a daily recurring to check for changes in the endpoints or use a notification method.</span></span>
3. <span data-ttu-id="087fe-194">변경 내용이 검색되면 클라이언트 컴퓨터의 PAC 파일을 다시 생성하고 다시 재배포하고 네트워크 장치를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-194">When changes are detected, regenerate and redistribute the PAC file for client computers and make the changes to your network devices.</span></span>

<span data-ttu-id="087fe-195">자세한 내용은 [Office 365 IP 주소 및 URL 웹 서비스를 참조하세요.](../enterprise/microsoft-365-ip-web-service.md)</span><span class="sxs-lookup"><span data-stu-id="087fe-195">For more information, see [Office 365 IP Address and URL web service](../enterprise/microsoft-365-ip-web-service.md).</span></span>

## <a name="results-of-step-2"></a><span data-ttu-id="087fe-196">2단계의 결과</span><span class="sxs-lookup"><span data-stu-id="087fe-196">Results of Step 2</span></span>

<span data-ttu-id="087fe-197">최적의 네트워킹이 있는 Microsoft 365 테넌트의 경우 다음을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-197">For your Microsoft 365 tenant with optimal networking, you have determined:</span></span>

- <span data-ttu-id="087fe-198">모든 지점에 인터넷 연결을 추가하고 네트워크 헤어피를 제거하여 사내 사용자의 네트워크 성능을 최적화하는 방법</span><span class="sxs-lookup"><span data-stu-id="087fe-198">How to optimize network performance for on-premises users by adding Internet connections to all branch offices and eliminating network hairpins.</span></span>
- <span data-ttu-id="087fe-199">지속적인 업데이트를 포함하여 클라이언트 기반 PAC 파일 및 네트워크 장치 및 서비스에 대해 자동화된 신뢰할 수 있는 끝점 목록을 구현하는 방법(엔터프라이즈 네트워크에 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="087fe-199">How to implement automated trusted endpoint listing for your client-based PAC files and your network devices and services, including ongoing updates (most suitable for enterprise networks).</span></span>
- <span data-ttu-id="087fe-200">원격 작업자의 액세스를 지원하기 위해 사내 리소스에 대한 액세스 권한을 지원하는 방법</span><span class="sxs-lookup"><span data-stu-id="087fe-200">How to support the access of remote workers to on-premises resources.</span></span>
- <span data-ttu-id="087fe-201">네트워크 인사이트를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="087fe-201">How to use Network Insights</span></span>
- <span data-ttu-id="087fe-202">Office 365 CDN을 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="087fe-202">How to deploy the Office 365 CDN.</span></span>

<span data-ttu-id="087fe-203">다음은 최적의 네트워킹을 통해 엔터프라이즈 조직 및 해당 테넌트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-203">Here is an example of an enterprise organization and its tenant with optimal networking.</span></span>

![최적의 네트워킹이 있는 테넌트의 예](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[<span data-ttu-id="087fe-205">이 이미지의 더 큰 버전 참조</span><span class="sxs-lookup"><span data-stu-id="087fe-205">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

<span data-ttu-id="087fe-206">이 그림에서는 이 엔터프라이즈 조직의 테넌트에 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-206">In this illustration, the tenant for this enterprise organization has:</span></span>

- <span data-ttu-id="087fe-207">신뢰할 수 있는 Microsoft 365 트래픽을 로컬 프런트 도어로 전달하는 SDWAN 장치를 사용하여 각 지점에 대한 로컬 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="087fe-207">Local internet access for each branch office with an SDWAN device that forwards trusted Microsoft 365 traffic to a local front door.</span></span>
- <span data-ttu-id="087fe-208">네트워크 헤어피 없음</span><span class="sxs-lookup"><span data-stu-id="087fe-208">No network hairpins.</span></span>
- <span data-ttu-id="087fe-209">Microsoft 365 신뢰할 수 있는 트래픽을 로컬 프런트 도어로 전달하는 중앙 사무실 보안 및 프록시 에지 장치</span><span class="sxs-lookup"><span data-stu-id="087fe-209">Central office security and proxy edge devices that forward Microsoft 365 trusted traffic to a local front door.</span></span>

## <a name="ongoing-maintenance-for-optimal-networking"></a><span data-ttu-id="087fe-210">최적의 네트워킹을 위한 지속적인 유지 관리</span><span class="sxs-lookup"><span data-stu-id="087fe-210">Ongoing maintenance for optimal networking</span></span>

<span data-ttu-id="087fe-211">지속적인 기준에 따라 다음을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-211">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="087fe-212">끝점의 변경 내용을 위해 에지 장치 및 배포된 PAC 파일을 업데이트하거나 자동화된 프로세스가 제대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-212">Update your edge devices and deployed PAC files for changes in endpoints or verify that your automated process works properly.</span></span>
- <span data-ttu-id="087fe-213">Office 365 CDN에서 자산을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-213">Manage your assets in the Office 365 CDN.</span></span>
- <span data-ttu-id="087fe-214">끝점 변경에 대해 VPN 클라이언트의 분할 터널링 구성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-214">Update the split tunneling configuration in your VPN clients for changes in endpoints.</span></span>

## <a name="next-step"></a><span data-ttu-id="087fe-215">다음 단계</span><span class="sxs-lookup"><span data-stu-id="087fe-215">Next step</span></span>

<span data-ttu-id="087fe-216">[![3단계. ID 동기화 및 보안 로그인 적용](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span><span class="sxs-lookup"><span data-stu-id="087fe-216">[![Step 3. Synchronize your identities and enforce secure sign-ins](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span></span>

<span data-ttu-id="087fe-217">ID를 [계속](tenant-management-identity.md) 유지하여 사내 계정 및 그룹을 동기화하고 보안 사용자 로그인을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="087fe-217">Continue with [identity](tenant-management-identity.md) to synchronize your on-premises accounts and groups and enforce secure user sign-ins.</span></span>
