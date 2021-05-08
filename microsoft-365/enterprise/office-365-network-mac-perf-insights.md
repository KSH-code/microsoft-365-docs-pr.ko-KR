---
title: Microsoft 365 네트워크 인사이트(미리 보기)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 네트워크 인사이트(미리 보기)
ms.openlocfilehash: ca665f4e492b071e5a387ffde0efae8336bd96bc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245783"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="1d3e0-103">Microsoft 365 네트워크 인사이트(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="1d3e0-104">**네트워크 인사이트는** Microsoft 365 테넌트에서 수집된 성능 메트릭으로, 테넌트의 관리 사용자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="1d3e0-105">인사이트는 의 Microsoft 365 관리 센터에 <https://portal.microsoft.com/adminportal/home#/networkperformance> 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="1d3e0-106">인사이트는 사무실 위치의 네트워크 경계를 디자인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="1d3e0-107">각 인사이트는 사용자가 테넌트에 액세스하는 각 지리적 위치에 대한 특정 일반적인 문제의 성능 특성에 대한 실시간 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="1d3e0-108">각 사무실 위치에 대해 표시될 수 있는 6개의 특정 네트워크 인사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="1d3e0-109">백hauled 네트워크 유선</span><span class="sxs-lookup"><span data-stu-id="1d3e0-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="1d3e0-110">네트워크 중간 장치</span><span class="sxs-lookup"><span data-stu-id="1d3e0-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="1d3e0-111">가까운 고객을 위해 검색된 성능 향상</span><span class="sxs-lookup"><span data-stu-id="1d3e0-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="1d3e0-112">최적이 아닌 서비스 Exchange Online 프론트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="1d3e0-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="1d3e0-113">최적화되지 않은 온라인 SharePoint 프론트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="1d3e0-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="1d3e0-114">정문에서 낮은 SharePoint 다운로드</span><span class="sxs-lookup"><span data-stu-id="1d3e0-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="1d3e0-115">중국 사용자 최적의 네트워크 유출</span><span class="sxs-lookup"><span data-stu-id="1d3e0-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="1d3e0-116">테넌트에 대해 표시될 수 있는 두 가지 테넌트 수준 네트워크 인사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="1d3e0-117">이러한 페이지는 생산성 점수 페이지에도 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="1d3e0-118">Exchange 문제로 영향을 미치는 샘플링된 연결 수</span><span class="sxs-lookup"><span data-stu-id="1d3e0-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="1d3e0-119">SharePoint 문제로 영향을 미치는 샘플링된 연결 수</span><span class="sxs-lookup"><span data-stu-id="1d3e0-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="1d3e0-120">Microsoft 365 관리 센터의 네트워크 인사이트, 성능 권장 사항 및 평가는 현재 미리 보기 상태입니다. Microsoft 365 미리 보기 프로그램에 등록된 Microsoft 365 테넌트에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="1d3e0-121">백hauled 네트워크 유선</span><span class="sxs-lookup"><span data-stu-id="1d3e0-121">Backhauled network egress</span></span>

<span data-ttu-id="1d3e0-122">이 인사이트 서비스는 네트워크 인사이트 서비스에서 특정 사용자 위치에서 네트워크로의 거리가 500 마일(800킬로미터)보다 크다는 것을 감지한 경우, Microsoft 365 트래픽이 일반적인 인터넷 에지 장치 또는 프록시로 백하우게 되었음을 나타내는 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="1d3e0-123">이 인사이트는 일부 요약 보기에서 "Egress"로 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1d3e0-124">![백hauled 네트워크 유선](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1d3e0-125">시나리오</span><span class="sxs-lookup"><span data-stu-id="1d3e0-125">What does this mean?</span></span>

<span data-ttu-id="1d3e0-126">이는 사무실 위치와 네트워크 출구 사이의 거리가 500 마일(800킬로미터)보다 먼지(킬로미터)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="1d3e0-127">사무실 위치는 난해한 클라이언트 컴퓨터 위치로 식별됩니다. 네트워크에서 위치는 역방향 IP 주소를 사용하여 위치 데이터베이스에 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="1d3e0-128">컴퓨터의 위치 서비스를 사용하지 않도록 Windows 사무실 위치가 부정확할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="1d3e0-129">역방향 IP 주소 데이터베이스 정보가 부정확한 경우 네트워크 유입 위치가 부정확할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="1d3e0-130">이 인사이트에 대한 세부 정보에는 사무실 위치, 위치의 예상 총 테넌트 사용자 백분율, 현재 네트워크 발신 위치, 발신 위치의 관련성, 위치와 현재 발신 지점 사이의 거리, 조건이 처음 검색된 날짜 및 조건이 해결된 날짜가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1d3e0-131">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1d3e0-131">What should I do?</span></span>

<span data-ttu-id="1d3e0-132">이 정보의 경우 연결이 Microsoft의 전역 네트워크 및 가장 가까운 서비스 프런트 도어로 최적으로 라우팅될 수 있도록 사무실 위치에 더 가깝게 네트워크 Microsoft 365 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="1d3e0-133">또한 Microsoft는 향후 네트워크 지점과 서비스 프런트 도어를 모두 확장하여 사용자 사무실 위치로의 네트워크 Microsoft 365 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="1d3e0-134">이 문제를 해결하는 방법에 대한 자세한 내용은 Egress Network Connectivity [Principles에서](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) Office 365 [참조하세요.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="1d3e0-135">네트워크 중간 장치</span><span class="sxs-lookup"><span data-stu-id="1d3e0-135">Network intermediary device</span></span>

<span data-ttu-id="1d3e0-136">이 인사이트는 사용자와 Microsoft 네트워크 간에 디바이스가 사용자 환경에 영향을 미칠 수 있는 디바이스를 감지한 Office 365 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="1d3e0-137">Microsoft 데이터 센터로 전송되는 특정 Microsoft 365 네트워크 트래픽에 대해 이러한 트래픽을 무시하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="1d3e0-138">이 권장 설정은 네트워크 연결 Microsoft 365 [설명에 추가적으로 설명되어 있습니다.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="1d3e0-139">한 가지 네트워크 중계 인사이트는 네트워크 중계 장치에 의해 가로채기 및 암호 해독되는 Exchange, SharePoint Teams 네트워크 끝점에 대한 중요한 네트워크 끝점이 있는 경우 SS Office 365 L 중단 및 검사입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1d3e0-140">시나리오</span><span class="sxs-lookup"><span data-stu-id="1d3e0-140">What does this mean?</span></span>

<span data-ttu-id="1d3e0-141">프록시 서버, VPN 및 데이터 손실 방지 장치와 같은 네트워크 중간 장치는 트래픽이 중간에 있는 Microsoft 365 클라이언트의 성능과 안정성에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1d3e0-142">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1d3e0-142">What should I do?</span></span>

<span data-ttu-id="1d3e0-143">네트워크 트래픽에 대한 처리를 무시하도록 검색된 네트워크 Microsoft 365 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="1d3e0-144">가까운 고객을 위해 검색된 성능 향상</span><span class="sxs-lookup"><span data-stu-id="1d3e0-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="1d3e0-145">이 인사이트는 네트워크 인사이트 서비스에서 대도시 지역에 있는 많은 고객이 이 사무실에 있는 조직의 사용자보다 더 나은 성능을 제공한다고 감지하는 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="1d3e0-146">이 인사이트는 일부 요약 보기에서 "피어"로 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1d3e0-147">![상대 네트워크 성능](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1d3e0-148">시나리오</span><span class="sxs-lookup"><span data-stu-id="1d3e0-148">What does this mean?</span></span>

<span data-ttu-id="1d3e0-149">이 인사이트는 이 사무실 위치와 동일한 Microsoft 365 고객에 대한 집계 성과를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="1d3e0-150">이 인사이트는 사용자의 평균 대기 시간이 인접 테넌트의 평균 대기 시간보다 10% 더 큰 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1d3e0-151">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1d3e0-151">What should I do?</span></span>

<span data-ttu-id="1d3e0-152">이 조건에는 회사 네트워크 또는 ISP의 대기 시간, 병목 현상, 아키텍처 디자인 문제 등 여러 가지 이유가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="1d3e0-153">사무실 네트워크와 현재 프런트 도어 사이의 경로에 있는 각 홉 간의 Microsoft 365 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="1d3e0-154">자세한 내용은 네트워크 [연결 Microsoft 365 을 참조하세요.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="1d3e0-155">최적이 아닌 서비스 Exchange Online 프론트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="1d3e0-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="1d3e0-156">이 인사이트는 네트워크 인사이트 서비스가 특정 위치에 있는 사용자가 최적의 서비스 프런트 도어에 연결하지 않는 Exchange Online 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="1d3e0-157">이 인사이트는 일부 요약 보기에서 "라우팅"으로 약어됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1d3e0-158">![최적이 아닌 EXO 프런트 도어](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1d3e0-159">시나리오</span><span class="sxs-lookup"><span data-stu-id="1d3e0-159">What does this mean?</span></span>

<span data-ttu-id="1d3e0-160">당사는 Exchange Online 사무실 위치 도시에서 사용하기에 적합한 서비스 프런트 도어를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="1d3e0-161">현재 테스트에서 이 목록에 없는 Exchange Online 서비스 프런트 도어를 사용하는 것으로 표시되어 있는 경우 이 권장을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1d3e0-162">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1d3e0-162">What should I do?</span></span>

<span data-ttu-id="1d3e0-163">최적화되지 않은 Exchange Online 서비스 프런트 도어를 사용하는 경우 회사 네트워크가 들어오기 전에 네트워크 백힐로 인해 발생할 수 있습니다. 이 경우 로컬 및 직접 네트워크 유출이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="1d3e0-164">또한 원격 DNS 재귀 해결 서버 사용으로 인해 발생할 수 있습니다. 이 경우 DNS 재귀 확인자 서버를 네트워크 전송에 맞추는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="1d3e0-165">최적화되지 않은 온라인 SharePoint 프론트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="1d3e0-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="1d3e0-166">이 인사이트는 네트워크 인사이트 서비스가 특정 위치에 있는 사용자가 가장 가까운 온라인 서비스 프런트 도어에 연결하지 않는 SharePoint 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="1d3e0-167">이 인사이트는 일부 요약 보기에서 "Afd"로 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1d3e0-168">![최적이 아닌 SPO 프런트 도어](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1d3e0-169">시나리오</span><span class="sxs-lookup"><span data-stu-id="1d3e0-169">What does this mean?</span></span>

<span data-ttu-id="1d3e0-170">테스트 클라이언트가 SharePoint 온라인 서비스 프런트 도어를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="1d3e0-171">그런 다음 사무실 위치 도시에 대해 해당 도시에 대한 SharePoint 온라인 서비스 프런트 도어와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="1d3e0-172">일치하지 않는 경우 이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1d3e0-173">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1d3e0-173">What should I do?</span></span>

<span data-ttu-id="1d3e0-174">최적화되지 않은 SharePoint 온라인 서비스 프런트 도어를 사용하는 경우 회사 네트워크가 들어오기 전에 네트워크 백힐로 인해 발생할 수 있습니다. 이 경우 로컬 및 직접 네트워크 유출이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="1d3e0-175">또한 원격 DNS 재귀 해결 서버 사용으로 인해 발생할 수 있습니다. 이 경우 DNS 재귀 확인자 서버를 네트워크 전송에 맞추는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="1d3e0-176">정문에서 낮은 SharePoint 다운로드</span><span class="sxs-lookup"><span data-stu-id="1d3e0-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="1d3e0-177">이 인사이트는 네트워크 인사이트 서비스가 특정 사무실 위치와 SharePoint Online 간의 대역폭이 1MBps 미만인 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="1d3e0-178">이 인사이트는 일부 요약 보기에서 "Throughput"로 약어됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1d3e0-179">시나리오</span><span class="sxs-lookup"><span data-stu-id="1d3e0-179">What does this mean?</span></span>

<span data-ttu-id="1d3e0-180">사용자가 SharePoint Online 및 비즈니스용 OneDrive 도어에서 얻을 수 있는 다운로드 속도는 메가바이트(MBps) 단위로 측정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="1d3e0-181">이 값이 1MBps보다 작은 경우 이 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1d3e0-182">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1d3e0-182">What should I do?</span></span>

<span data-ttu-id="1d3e0-183">다운로드 속도를 높이기 위해 대역폭을 늘리면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="1d3e0-184">또는 사무실 위치의 사용자 컴퓨터와 SharePoint 온라인 서비스 프런트 도어 간에 네트워크 정체가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="1d3e0-185">이를 연속적인 손실이라고도 부르며 충분한 대역폭을 사용할 수 있는 경우에도 사용자가 사용할 수 있는 다운로드 속도를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="1d3e0-186">중국 사용자 최적의 네트워크 유출</span><span class="sxs-lookup"><span data-stu-id="1d3e0-186">China user optimal network egress</span></span>

<span data-ttu-id="1d3e0-187">이 인사이트는 조직에서 중국의 사용자가 다른 지리적 위치에 있는 Microsoft 365 테넌트에 연결하는 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="1d3e0-188">시나리오</span><span class="sxs-lookup"><span data-stu-id="1d3e0-188">What does this mean?</span></span>

<span data-ttu-id="1d3e0-189">조직에 개인 WAN 연결이 있는 경우 다음 위치 중 한 위치에서 인터넷으로 네트워크가 유출된 중국의 사무실 위치에서 네트워크 WAN 회로를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="1d3e0-190">홍콩</span><span class="sxs-lookup"><span data-stu-id="1d3e0-190">Hong Kong</span></span>
- <span data-ttu-id="1d3e0-191">일본</span><span class="sxs-lookup"><span data-stu-id="1d3e0-191">Japan</span></span>
- <span data-ttu-id="1d3e0-192">대만</span><span class="sxs-lookup"><span data-stu-id="1d3e0-192">Taiwan</span></span>
- <span data-ttu-id="1d3e0-193">대한민국</span><span class="sxs-lookup"><span data-stu-id="1d3e0-193">South Korea</span></span>
- <span data-ttu-id="1d3e0-194">싱가포르</span><span class="sxs-lookup"><span data-stu-id="1d3e0-194">Singapore</span></span>
- <span data-ttu-id="1d3e0-195">말레이시아</span><span class="sxs-lookup"><span data-stu-id="1d3e0-195">Malaysia</span></span>

<span data-ttu-id="1d3e0-196">이러한 위치보다 사용자로부터 더 멀리 인터넷을 유출하면 성능이 낮아지며 중국에서 전송하면 경계 정체로 인해 대기 시간이 길어지며 연결 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="1d3e0-197">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1d3e0-197">What should I do?</span></span>

<span data-ttu-id="1d3e0-198">이 인사이트와 관련된 성능 문제를 완화하는 방법에 대한 자세한 내용은 중국 사용자를 위한 Microsoft 365 전역 테넌트 성능 최적화를 [참조하세요.](microsoft-365-networking-china.md)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="1d3e0-199">Exchange 문제로 영향을 미치는 샘플링된 연결 수</span><span class="sxs-lookup"><span data-stu-id="1d3e0-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="1d3e0-200">이 인사이트는 샘플링된 연결 중 50% 이상이 영향을 미치는 경우를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="1d3e0-201">영향은 각 샘플에 Exchange 60% 미만인 평가로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1d3e0-202">시나리오</span><span class="sxs-lookup"><span data-stu-id="1d3e0-202">What does this mean?</span></span>

<span data-ttu-id="1d3e0-203">이는 대부분의 사용자가 사용자 환경과 연결되지 Outlook 경험할 가능성이 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="1d3e0-204">샘플의 백분율은 60포인트 미만으로 표시하는 사용자의 백분율을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="1d3e0-205">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1d3e0-205">What should I do?</span></span>

<span data-ttu-id="1d3e0-206">아직 표시하지 않은 경우 Office 위치 네트워크 연결 표시를 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="1d3e0-207">네트워크에 영향을 미치는 불량 네트워크 연결의 영향을 Exchange 각 사무실에서 사용자를 Microsoft 네트워크에 연결하는 네트워크 경계를 개선하는 방법을 찾으시고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="1d3e0-208">SharePoint 문제로 영향을 미치는 샘플링된 연결 수</span><span class="sxs-lookup"><span data-stu-id="1d3e0-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="1d3e0-209">이 인사이트는 샘플링된 연결 중 50% 이상이 영향을 미치는 경우를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="1d3e0-210">영향은 각 샘플에 SharePoint 40% 미만인 평가로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="1d3e0-211">시나리오</span><span class="sxs-lookup"><span data-stu-id="1d3e0-211">What does this mean?</span></span>

<span data-ttu-id="1d3e0-212">이는 대부분의 사용자가 사용자 환경 문제 및 사용자 환경과 관련한 SharePoint OneDrive.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="1d3e0-213">샘플의 백분율은 40포인트 미만으로 표시하는 사용자의 백분율을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="1d3e0-214">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1d3e0-214">What should I do?</span></span>

<span data-ttu-id="1d3e0-215">아직 표시하지 않은 경우 Office 위치 네트워크 연결 표시를 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="1d3e0-216">네트워크에 영향을 미치는 불량 네트워크 연결의 영향을 SharePoint Microsoft 네트워크에 연결하는 각 사무실에서 네트워크 경계를 개선하는 방법을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3e0-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d3e0-217">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1d3e0-217">Related topics</span></span>

[<span data-ttu-id="1d3e0-218">Microsoft 365 관리 센터의 네트워크 연결(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="1d3e0-219">Microsoft 365 네트워크 평가(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="1d3e0-220">Microsoft 365 연결 테스트 도구(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="1d3e0-221">Microsoft 365 네트워크 연결 위치 서비스(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1d3e0-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
