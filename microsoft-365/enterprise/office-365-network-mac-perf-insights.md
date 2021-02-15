---
title: Microsoft 365 Network Insights(미리 보기)
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
description: Microsoft 365 Network Insights(미리 보기)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055476"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="31496-103">Microsoft 365 Network Insights(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="31496-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="31496-104">**네트워크 인사이트는** Microsoft 365 테넌트에서 수집된 성능 메트릭으로, 테넌트의 관리자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="31496-105">인사이트는 Microsoft 365 관리 센터의 .에 <https://portal.microsoft.com/adminportal/home#/networkperformance> 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="31496-106">인사이트는 사무실 위치의 네트워크 경계를 디자인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="31496-107">각 인사이트는 사용자가 테넌트에 액세스하는 각 지리적 위치에 대한 특정 일반적인 문제의 성능 특성에 대한 실시간 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="31496-108">각 사무실 위치에 대해 표시될 수 있는 6개의 특정 네트워크 인사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="31496-109">백hauled 네트워크 유치</span><span class="sxs-lookup"><span data-stu-id="31496-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="31496-110">네트워크 중간 장치</span><span class="sxs-lookup"><span data-stu-id="31496-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="31496-111">가까운 고객을 위해 검색된 성능 향상</span><span class="sxs-lookup"><span data-stu-id="31496-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="31496-112">최적의 Exchange Online 서비스 프런트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="31496-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="31496-113">최적화되지 않은 SharePoint Online 서비스 프런트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="31496-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="31496-114">SharePoint 프런트 도어에서 낮은 다운로드 속도</span><span class="sxs-lookup"><span data-stu-id="31496-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="31496-115">중국 사용자 최적의 네트워크 유출</span><span class="sxs-lookup"><span data-stu-id="31496-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="31496-116">테넌트에 대해 표시될 수 있는 두 가지 테넌트 수준 네트워크 인사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="31496-117">이러한 페이지는 생성자 점수 페이지에도 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="31496-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="31496-118">연결 문제의 영향을 미치는 Exchange 샘플링된 연결</span><span class="sxs-lookup"><span data-stu-id="31496-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="31496-119">연결 문제의 영향을 미치는 SharePoint 샘플링된 연결</span><span class="sxs-lookup"><span data-stu-id="31496-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="31496-120">Microsoft 365 관리 센터의 네트워크 정보, 성능 권장 사항 및 평가는 현재 미리 보기 상태입니다. 기능 미리 보기 프로그램에 등록된 Microsoft 365 테넌트에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="31496-121">백hauled 네트워크 유치</span><span class="sxs-lookup"><span data-stu-id="31496-121">Backhauled network egress</span></span>

<span data-ttu-id="31496-122">이 인사이트 서비스는 네트워크 인사이트 서비스가 특정 사용자 위치에서 네트워크 시작까지의 거리가 500 마일(800킬로미터)보다 크다는 것을 감지하는 경우 Microsoft 365 트래픽이 공통 인터넷 에지 장치 또는 프록시로 다시 정비되고 있는 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="31496-123">이 인사이트는 일부 요약 보기에서 "Egress"로 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![백hauled 네트워크 유치](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="31496-125">시나리오</span><span class="sxs-lookup"><span data-stu-id="31496-125">What does this mean?</span></span>

<span data-ttu-id="31496-126">이 설정은 사무실 위치와 네트워크 출구 사이의 거리가 500 마일(800킬로미터)보다 먼 거리를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="31496-127">사무실 위치는 난청된 클라이언트 컴퓨터 위치로 식별됩니다. 네트워크의 위치는 위치 데이터베이스에 대한 역방향 IP 주소를 사용하여 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="31496-128">컴퓨터의 Windows Location Services를 사용하지 않도록 설정한 경우 사무실 위치가 부정확할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="31496-129">역방향 IP 주소 데이터베이스 정보가 부정확한 경우 네트워크 유입 위치가 부정확할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="31496-130">이 인사이트에 대한 세부 정보로는 사무실 위치, 위치의 총 테넌트 사용자의 예상 백분율, 현재 네트워크 발신 위치, 발신 위치의 관련성, 위치와 현재 발신 지점 사이의 거리, 조건이 처음 감지된 날짜 및 조건이 해결된 날짜가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31496-131">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="31496-131">What should I do?</span></span>

<span data-ttu-id="31496-132">이 정보의 경우 연결이 Microsoft의 전역 네트워크 및 가장 가까운 Microsoft 365 서비스 프런트 도어로 최적으로 라우팅될 수 있도록 사무실 위치와 더 가깝게 네트워크 이동을 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="31496-133">또한 Microsoft는 향후 네트워크 지점과 Microsoft 365 서비스 프런트 도어를 모두 확장하여 사용자 사무실 위치에 대한 네트워크 유출을 닫을 수 있도록 하여 향후 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="31496-134">이 문제를 해결하는 방법에 대한 자세한 내용은 Office 365 네트워크 연결 원칙에서 로컬로 네트워크 연결을 [Egress(네트워크](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) [연결)를 참조하세요.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="31496-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="31496-135">네트워크 중간 장치</span><span class="sxs-lookup"><span data-stu-id="31496-135">Network intermediary device</span></span>

<span data-ttu-id="31496-136">사용자와 Microsoft 네트워크 간에 Office 365 사용자 환경에 영향을 줄 수 있는 장치를 감지한 경우 이 인사이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="31496-137">이러한 트래픽은 Microsoft 데이터 센터로 전송되는 특정 Microsoft 365 네트워크 트래픽에 대해 무시하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="31496-138">이 권장은 [Microsoft 365 네트워크 연결 원칙에 추가적으로 설명되어 있습니다.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="31496-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31496-139">시나리오</span><span class="sxs-lookup"><span data-stu-id="31496-139">What does this mean?</span></span>

<span data-ttu-id="31496-140">프록시 서버, VPN 및 데이터 손실 방지 장치와 같은 네트워크 중간 장치는 트래픽이 중간에 있는 Microsoft 365 클라이언트의 성능 및 안정성에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31496-141">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="31496-141">What should I do?</span></span>

<span data-ttu-id="31496-142">Microsoft 365 네트워크 트래픽에 대한 처리를 무시하도록 검색된 네트워크 중간 장치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="31496-143">가까운 고객을 위해 검색된 성능 향상</span><span class="sxs-lookup"><span data-stu-id="31496-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="31496-144">이 인사이트는 네트워크 인사이트 서비스에서 대도시 지역에 있는 많은 고객이 이 사무실의 사용자보다 더 나은 성능을 제공한다고 감지하는 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="31496-145">이 인사이트는 일부 요약 보기에서 "피어"로 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![상대 네트워크 성능](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="31496-147">시나리오</span><span class="sxs-lookup"><span data-stu-id="31496-147">What does this mean?</span></span>

<span data-ttu-id="31496-148">이 인사이트는 이 사무실 위치와 동일한 도시에 있는 Microsoft 365 고객의 집계 성과를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="31496-149">이 인사이트는 사용자의 평균 대기 시간이 인접한 테넌트의 평균 대기 시간보다 10% 더 큰 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31496-150">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="31496-150">What should I do?</span></span>

<span data-ttu-id="31496-151">이 조건에는 회사 네트워크 또는 ISP의 대기 시간, 병목 현상 또는 아키텍처 디자인 문제 등 여러 가지 이유가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="31496-152">사무실 네트워크와 현재 Microsoft 365 프런트 도어 사이의 경로에 있는 각 홉 간의 대기 시간을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="31496-153">자세한 내용은 [Microsoft 365 네트워크 연결 원칙을 참조하세요.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="31496-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="31496-154">최적의 Exchange Online 서비스 프런트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="31496-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="31496-155">네트워크 인사이트 서비스에서 특정 위치에 있는 사용자가 최적의 Exchange Online 서비스 프런트 도어에 연결되지 않는 경우 이 인사이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="31496-156">이 인사이트는 일부 요약 보기에서 "라우팅"으로 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![최적이 아닌 EXO 프런트 도어](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="31496-158">시나리오</span><span class="sxs-lookup"><span data-stu-id="31496-158">What does this mean?</span></span>

<span data-ttu-id="31496-159">Office 위치 도시에서 좋은 성능을 제공하는 데 적합한 Exchange Online 서비스 프런트 도어를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="31496-160">현재 테스트에서 이 목록에 없는 Exchange Online 서비스 프런트 도어 사용을 보여 주면 이 권장이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31496-161">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="31496-161">What should I do?</span></span>

<span data-ttu-id="31496-162">최적의 Exchange Online 서비스 프런트 도어 사용은 회사 네트워크가 유출되기 전에 네트워크 백힐로 인해 발생할 수 있으며, 이 경우 로컬 및 직접 네트워크 유출을 권장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="31496-163">또한 원격 DNS 재귀 확인 서버 사용으로 인해 발생할 수 있습니다. 이 경우 DNS 재귀 확인 서버와 네트워크 전송을 맞추는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="31496-164">최적화되지 않은 SharePoint Online 서비스 프런트 도어 사용</span><span class="sxs-lookup"><span data-stu-id="31496-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="31496-165">네트워크 인사이트 서비스에서 특정 위치에 있는 사용자가 가장 가까운 SharePoint Online 서비스 프런트 도어에 연결되지 않는 경우 이 인사이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="31496-166">이 인사이트는 일부 요약 보기에서 "Afd"로 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![최적이 아닌 SPO 프런트 도어](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="31496-168">시나리오</span><span class="sxs-lookup"><span data-stu-id="31496-168">What does this mean?</span></span>

<span data-ttu-id="31496-169">테스트 클라이언트가 연결하고 있는 SharePoint Online 서비스 프런트 도어를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="31496-170">그런 다음 사무실 위치 도시의 경우 해당 도시에 대해 예상되는 SharePoint Online 서비스 프런트 도어와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="31496-171">일치하지 않는 경우 이 권장을 합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31496-172">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="31496-172">What should I do?</span></span>

<span data-ttu-id="31496-173">회사 네트워크가 유출되기 전에 최적이 아닌 SharePoint Online 서비스 프런트 도어가 사용되기 때문에 로컬 및 직접 네트워크 유출을 권장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="31496-174">또한 원격 DNS 재귀 확인 서버 사용으로 인해 발생할 수 있습니다. 이 경우 DNS 재귀 확인 서버와 네트워크 전송을 맞추는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="31496-175">SharePoint 프런트 도어에서 낮은 다운로드 속도</span><span class="sxs-lookup"><span data-stu-id="31496-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="31496-176">네트워크 인사이트 서비스가 특정 사무실 위치와 SharePoint Online 간의 대역폭이 1MBps 미만인 경우 이 인사이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="31496-177">이 인사이트는 일부 요약 보기에서 "결과"로 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31496-178">시나리오</span><span class="sxs-lookup"><span data-stu-id="31496-178">What does this mean?</span></span>

<span data-ttu-id="31496-179">사용자가 SharePoint Online 및 비즈니스용 OneDrive 서비스 프런트 도어에서 얻을 수 있는 다운로드 속도는 초당 메가바이트(MBps)로 측정됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="31496-180">이 값이 1MBps 미만이면 이 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31496-181">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="31496-181">What should I do?</span></span>

<span data-ttu-id="31496-182">다운로드 속도를 높이기 위해 대역폭을 늘러야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="31496-183">또는 사무실 위치의 사용자 컴퓨터와 SharePoint Online 서비스 프런트 도어 간에 네트워크 정체가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="31496-184">이러한 손실을 연속적인 손실이라고도 하여 충분한 대역폭을 사용할 수 있는 경우에도 사용자가 사용할 수 있는 다운로드 속도를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="31496-185">중국 사용자 최적의 네트워크 유출</span><span class="sxs-lookup"><span data-stu-id="31496-185">China user optimal network egress</span></span>

<span data-ttu-id="31496-186">이 인사이트는 중국의 사용자가 다른 지리적 위치에 있는 Microsoft 365 테넌트에 연결하는 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="31496-187">시나리오</span><span class="sxs-lookup"><span data-stu-id="31496-187">What does this mean?</span></span>

<span data-ttu-id="31496-188">조직에 개인 WAN 연결이 있는 경우 다음 위치 중 인터넷으로 네트워크가 유출된 중국의 사무실 위치에서 네트워크 WAN 회로를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="31496-189">홍콩</span><span class="sxs-lookup"><span data-stu-id="31496-189">Hong Kong</span></span>
- <span data-ttu-id="31496-190">일본</span><span class="sxs-lookup"><span data-stu-id="31496-190">Japan</span></span>
- <span data-ttu-id="31496-191">대만</span><span class="sxs-lookup"><span data-stu-id="31496-191">Taiwan</span></span>
- <span data-ttu-id="31496-192">대한민국</span><span class="sxs-lookup"><span data-stu-id="31496-192">South Korea</span></span>
- <span data-ttu-id="31496-193">싱가포르</span><span class="sxs-lookup"><span data-stu-id="31496-193">Singapore</span></span>
- <span data-ttu-id="31496-194">말레이시아</span><span class="sxs-lookup"><span data-stu-id="31496-194">Malaysia</span></span>

<span data-ttu-id="31496-195">이러한 위치보다 사용자로부터 더 멀리 인터넷으로 유출되는 경우 성능이 짧아지며 중국의 전송으로 인해 국경 간 정체로 인해 대기 시간이 길어지며 연결 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31496-196">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="31496-196">What should I do?</span></span>

<span data-ttu-id="31496-197">이 인사이트와 관련된 성능 문제를 완화하는 방법에 대한 자세한 내용은 중국 사용자를 위한 [Microsoft 365](microsoft-365-networking-china.md)전역 테넌트 성능 최적화를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31496-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="31496-198">연결 문제의 영향을 미치는 Exchange 샘플링된 연결</span><span class="sxs-lookup"><span data-stu-id="31496-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="31496-199">이 인사이트는 샘플링된 연결의 50% 이상이 영향을 미치는 경우를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="31496-200">영향은 각 샘플에 대해 Exchange 평가에서 60% 미만으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31496-201">시나리오</span><span class="sxs-lookup"><span data-stu-id="31496-201">What does this mean?</span></span>

<span data-ttu-id="31496-202">이는 대부분의 사용자가 Exchange Online에 연결하는 데 Outlook 연결 시 사용자 환경 문제가 발생하고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="31496-203">샘플의 백분율은 60포인트 미만으로 표시하는 사용자의 백분율을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="31496-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="31496-204">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="31496-204">What should I do?</span></span>

<span data-ttu-id="31496-205">아직 수행하지 않은 경우 Office 위치 네트워크 연결 표시를 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="31496-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="31496-206">Exchange에 영향을 미치는 불량 네트워크 연결의 영향을 미치는 사무실을 식별하고 사용자를 Microsoft 네트워크에 연결하는 각 사무실에서 네트워크 경계를 개선하는 방법을 찾고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="31496-207">연결 문제의 영향을 미치는 SharePoint 샘플링된 연결</span><span class="sxs-lookup"><span data-stu-id="31496-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="31496-208">이 인사이트는 샘플링된 연결의 50% 이상이 영향을 미치는 경우를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="31496-209">영향은 각 샘플에 대해 SharePoint 평가에서 40% 미만으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="31496-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31496-210">시나리오</span><span class="sxs-lookup"><span data-stu-id="31496-210">What does this mean?</span></span>

<span data-ttu-id="31496-211">이는 대부분의 사용자가 SharePoint 및 OneDrive에서 사용자 환경 문제를 겪을 가능성이 높게 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31496-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="31496-212">샘플의 백분율은 40포인트 미만으로 표시하는 사용자의 백분율을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="31496-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="31496-213">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="31496-213">What should I do?</span></span>

<span data-ttu-id="31496-214">아직 수행하지 않은 경우 Office 위치 네트워크 연결 표시를 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="31496-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="31496-215">SharePoint에 영향을 미치는 불량 네트워크 연결의 영향을 미치는 사무실을 식별하고 사용자를 Microsoft 네트워크에 연결하는 각 사무실에서 네트워크 경계를 개선하는 방법을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31496-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="31496-216">관련 항목</span><span class="sxs-lookup"><span data-stu-id="31496-216">Related topics</span></span>

[<span data-ttu-id="31496-217">Microsoft 365 관리 센터의 네트워크 연결(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="31496-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="31496-218">Microsoft 365 네트워크 평가(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="31496-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="31496-219">Microsoft 365 네트워크 연결 테스트 도구(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="31496-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="31496-220">Microsoft 365 Network Connectivity Location Services(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="31496-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
