---
title: Microsoft 365 Network Insights (미리 보기)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (미리 보기)
ms.openlocfilehash: 682c888fefb9bec9725e470d62019c857fc2de07
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171341"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="6b998-103">Microsoft 365 Network Insights (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="6b998-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="6b998-104">**네트워크 Insights** Microsoft 365 테 넌 트에서 수집한 성능 메트릭 및 테 넌 트의 관리 사용자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="6b998-105">Insights는 Microsoft 365 관리 센터에 표시 됩니다 <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="6b998-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="6b998-106">Insights는 사무실 사무소에 대 한 네트워크 perimeters 디자인에 도움을 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="6b998-107">각 통찰력은 사용자가 테 넌 트에 액세스 하는 각 지리적 위치에 대 한 특정 일반적인 문제의 성능 특성에 대 한 실시간 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="6b998-108">각 사무실 위치에 대해 표시할 수 있는 6 가지 특정 네트워크 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="6b998-109">Backhauled 네트워크 송신</span><span class="sxs-lookup"><span data-stu-id="6b998-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="6b998-110">주변 고객에 게 더 나은 성능 검색</span><span class="sxs-lookup"><span data-stu-id="6b998-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="6b998-111">최적이 아닌 Exchange Online 서비스 전면 도어 사용</span><span class="sxs-lookup"><span data-stu-id="6b998-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="6b998-112">최적이 아닌 SharePoint Online 서비스 전면 도어 사용</span><span class="sxs-lookup"><span data-stu-id="6b998-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="6b998-113">SharePoint 전면 도어에서 다운로드 속도 낮음</span><span class="sxs-lookup"><span data-stu-id="6b998-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="6b998-114">중국 사용자 최적 네트워크 송신</span><span class="sxs-lookup"><span data-stu-id="6b998-114">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="6b998-115">테 넌 트에 대해 표시할 수 있는 테 넌 트 수준 네트워크 정보는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-115">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="6b998-116">이러한 항목은 producvitivy 점수 페이지에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-116">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="6b998-117">연결 문제의 영향을 받는 Exchange 샘플링 된 연결</span><span class="sxs-lookup"><span data-stu-id="6b998-117">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="6b998-118">연결 문제의 영향을 받는 SharePoint 샘플링 된 연결</span><span class="sxs-lookup"><span data-stu-id="6b998-118">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="6b998-119">네트워크 insights, Microsoft 365 관리 센터의 성능 권장 사항 및 평가는 현재 미리 보기 상태 이며, 기능 미리 보기 프로그램에 등록 되어 있는 Microsoft 365 테 넌 트에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-119">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="6b998-120">Backhauled 네트워크 송신</span><span class="sxs-lookup"><span data-stu-id="6b998-120">Backhauled network egress</span></span>

<span data-ttu-id="6b998-121">이 통찰력은 네트워크 insights 서비스가 지정 된 사용자 위치에서 네트워크 송신으로의 거리가 500 마일 (800 킬로미터) 보다 크면 Microsoft 365 트래픽이 일반 인터넷에 지 장치 또는 프록시로 backhauled는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-121">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="6b998-122">이 통찰력은 일부 요약 보기에서 "Egress"로 간략 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-122">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Backhauled 네트워크 송신](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="6b998-124">시나리오</span><span class="sxs-lookup"><span data-stu-id="6b998-124">What does this mean?</span></span>

<span data-ttu-id="6b998-125">이는 사무실 위치와 네트워크 송신 사이의 거리가 500 마일 (800 킬로미터) 보다 큼을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-125">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="6b998-126">Office 위치는 난독 처리 된 클라이언트 컴퓨터 위치로 식별 되며 네트워크 송신 위치는 역방향 IP 주소를 위치 데이터베이스에 사용 하 여 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-126">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="6b998-127">컴퓨터에서 Windows 위치 서비스를 사용 하지 않도록 설정 하면 office 위치가 정확 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-127">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="6b998-128">역방향 IP 주소 데이터베이스 정보가 부정확 한 경우 네트워크 송신 위치가 부정확 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-128">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="6b998-129">이러한 통찰력에 대 한 자세한 내용은 사무실 위치, 현재 네트워크 송신 위치, egress 위치의 관련성, 위치 및 현재 송신 지점 간의 거리, 조건이 처음 검색 된 날짜, 조건이 해결 된 날짜 등을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-129">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="6b998-130">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b998-130">What should I do?</span></span>

<span data-ttu-id="6b998-131">이에 대 한 자세한 내용은 연결을 통해 최적의 microsoft 글로벌 네트워크 및 가장 가까운 Microsoft 365 서비스 전면 도어로 경로를 지정할 수 있도록 네트워크를 office 위치에 더 가깝게 egress 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-131">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="6b998-132">또한 사용자에 게 네트워크를 닫도록 네트워크가 송신 되도록 설정 하면 향후에도 Microsoft는 네트워크의 현재 상태와 Microsoft 365 서비스 전면 도어를 모두 확장 하는 동시에 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-132">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="6b998-133">이 문제를 해결 하는 방법에 대 한 자세한 내용은 [Office 365 네트워크 연결 원리](microsoft-365-network-connectivity-principles.md)에서 [로컬로 Egress 네트워크 연결](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b998-133">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="6b998-134">주변 고객에 게 더 나은 성능 검색</span><span class="sxs-lookup"><span data-stu-id="6b998-134">Better performance detected for customers near you</span></span>

<span data-ttu-id="6b998-135">이 통찰력은 네트워크 insights 서비스에서이 사무실 위치에 있는 조직의 사용자 보다 많은 수의 metro 영역을 검색 하는 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-135">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="6b998-136">이 통찰력은 일부 요약 보기에서 "피어"로 간략 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-136">This insight is abbreviated as "Peers" in some summary views.</span></span>

![상대적 네트워크 성능](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="6b998-138">시나리오</span><span class="sxs-lookup"><span data-stu-id="6b998-138">What does this mean?</span></span>

<span data-ttu-id="6b998-139">이러한 통찰력은이 사무실 위치와 같은 도시의 Microsoft 365 고객의 집계 성과를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-139">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="6b998-140">이러한 통찰력은 사용자의 평균 대기 시간이 인접 한 테 넌 트의 평균 대기 시간 보다 10% 보다 많은 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-140">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="6b998-141">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b998-141">What should I do?</span></span>

<span data-ttu-id="6b998-142">회사 네트워크 또는 ISP의 대기 시간, 병목 현상 또는 아키텍처 디자인 문제를 포함 하 여 이러한 상황이 발생 하는 여러 가지 이유가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-142">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="6b998-143">Office 네트워크와 현재 Microsoft 365 전면 도어 간의 경로에 있는 각 홉 사이의 대기 시간을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-143">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="6b998-144">자세한 내용은 [Office 365 네트워크 연결 원리](microsoft-365-network-connectivity-principles.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6b998-144">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="6b998-145">최적이 아닌 Exchange Online 서비스 전면 도어 사용</span><span class="sxs-lookup"><span data-stu-id="6b998-145">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="6b998-146">이 통찰력은 네트워크 insights 서비스가 특정 위치의 사용자가 최적의 Exchange Online 서비스 전면 도어에 연결 되지 않는 것을 감지 하는 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-146">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="6b998-147">이에 대 한 자세한 정보는 요약 보기의 "라우팅" 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-147">This insight is abbreviated as "Routing" in some summary views.</span></span>

![최적이 아닌 EXO 전면 도어](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="6b998-149">시나리오</span><span class="sxs-lookup"><span data-stu-id="6b998-149">What does this mean?</span></span>

<span data-ttu-id="6b998-150">적절 한 성능을 제공 하는 office 위치 도시에서 사용 하기에 적합 한 Exchange Online 서비스 프런트 도어를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-150">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="6b998-151">현재 테스트에서이 목록에 없는 Exchange Online 서비스 앞 도어를 사용 하는 경우에는이 권장 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-151">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="6b998-152">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b998-152">What should I do?</span></span>

<span data-ttu-id="6b998-153">Exchange Online 서비스 프런트 도어를 사용 하는 경우에는 회사 네트워크 egress가 되기 전에 로컬 및 직접 네트워크 송신을 권장 하는 네트워크 교환이 발생 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-153">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="6b998-154">또한 원격 DNS 재귀 해결 프로그램 서버를 사용 하는 경우에도 DNS 재귀 해결 프로그램 서버를 네트워크 egress에 정렬 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-154">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="6b998-155">최적이 아닌 SharePoint Online 서비스 전면 도어 사용</span><span class="sxs-lookup"><span data-stu-id="6b998-155">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="6b998-156">이 통찰력은 네트워크 insights 서비스가 특정 위치의 사용자가 가장 가까운 SharePoint Online 서비스 앞 도어에 연결 되지 않는 것을 감지 하는 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="6b998-157">이 통찰력은 일부 요약 보기에서 "Afd"로 간략 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-157">This insight is abbreviated as "Afd" in some summary views.</span></span>

![최적이 아닌 SPO 전면 도어](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="6b998-159">시나리오</span><span class="sxs-lookup"><span data-stu-id="6b998-159">What does this mean?</span></span>

<span data-ttu-id="6b998-160">테스트 클라이언트가 연결 되는 SharePoint Online 서비스 프런트 도어를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-160">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="6b998-161">그런 다음 office 위치 도시에서 해당 도시의 예상 SharePoint Online 서비스 전면 도어를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-161">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="6b998-162">일치 하지 않는 경우이 권장 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-162">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="6b998-163">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b998-163">What should I do?</span></span>

<span data-ttu-id="6b998-164">네트워크를 사용 하기 전에 회사 네트워크 송신이 가장 좋지 않은 경우 (예를 들어 로컬 및 직접 네트워크 송신을 권장 하는 경우)에는 최적이 아닌 SharePoint Online 서비스 프런트 도어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-164">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="6b998-165">또한 원격 DNS 재귀 해결 프로그램 서버를 사용 하는 경우에도 DNS 재귀 해결 프로그램 서버를 네트워크 egress에 정렬 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-165">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="6b998-166">SharePoint 전면 도어에서 다운로드 속도 낮음</span><span class="sxs-lookup"><span data-stu-id="6b998-166">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="6b998-167">네트워크 insights 서비스가 특정 사무실 위치와 SharePoint Online 간의 대역폭이 1 MBps 미만인 경우이 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-167">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="6b998-168">이 통찰력은 일부 요약 보기에서 "처리량"으로 간략하게 정리 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-168">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="6b998-169">시나리오</span><span class="sxs-lookup"><span data-stu-id="6b998-169">What does this mean?</span></span>

<span data-ttu-id="6b998-170">사용자가 SharePoint Online에서 가져올 수 있는 다운로드 속도 및 비즈니스용 OneDrive 서비스의 프런트 도어는 초당 메가바이트 (MBps)로 측정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-170">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="6b998-171">이 값이 1 MBps 보다 작으면 이러한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-171">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="6b998-172">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b998-172">What should I do?</span></span>

<span data-ttu-id="6b998-173">다운로드 속도를 개선 하기 위해 대역폭을 늘려야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-173">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="6b998-174">또는 사무실 위치에 있는 사용자 컴퓨터와 SharePoint Online 서비스 전면 도어의 네트워크 정체가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-174">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="6b998-175">이를 congestive 손실 이라고 하는 경우도 있으며 충분 한 대역폭을 사용할 수 있는 경우에도 사용자가 사용할 수 있는 다운로드 속도를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-175">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="6b998-176">중국 사용자 최적 네트워크 송신</span><span class="sxs-lookup"><span data-stu-id="6b998-176">China user optimal network egress</span></span>

<span data-ttu-id="6b998-177">이 정보는 조직에서 다른 지리적 위치에 있는 Microsoft 365 테 넌 트에 연결 하는 사용자가 있는 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-177">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="6b998-178">시나리오</span><span class="sxs-lookup"><span data-stu-id="6b998-178">What does this mean?</span></span>

<span data-ttu-id="6b998-179">조직에 사설 WAN 연결이 있는 경우 중국의 사무실 위치에서 네트워크 WAN 회로를 구성 하는 것이 좋습니다 (다음 위치에서 인터넷으로 네트워크가 송신 됨).</span><span class="sxs-lookup"><span data-stu-id="6b998-179">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="6b998-180">홍콩</span><span class="sxs-lookup"><span data-stu-id="6b998-180">Hong Kong</span></span>
- <span data-ttu-id="6b998-181">일본</span><span class="sxs-lookup"><span data-stu-id="6b998-181">Japan</span></span>
- <span data-ttu-id="6b998-182">대만</span><span class="sxs-lookup"><span data-stu-id="6b998-182">Taiwan</span></span>
- <span data-ttu-id="6b998-183">대한민국</span><span class="sxs-lookup"><span data-stu-id="6b998-183">South Korea</span></span>
- <span data-ttu-id="6b998-184">싱가포르</span><span class="sxs-lookup"><span data-stu-id="6b998-184">Singapore</span></span>
- <span data-ttu-id="6b998-185">말레이시아</span><span class="sxs-lookup"><span data-stu-id="6b998-185">Malaysia</span></span>

<span data-ttu-id="6b998-186">인터넷 egress 사용자가 이러한 위치 보다 더 멀리 떨어진 경우에는 성능이 저하 되 고 중국에서 egress로 인해 경계 간 혼잡으로 인 한 대기 시간 및 연결 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-186">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="6b998-187">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b998-187">What should I do?</span></span>

<span data-ttu-id="6b998-188">이러한 정보와 관련 된 성능 문제를 완화 하는 방법에 대 한 자세한 내용은 [중국 사용자에 대 한 Office 365 전역 테 넌 트 성능 최적화](microsoft-365-networking-china.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6b998-188">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="6b998-189">연결 문제의 영향을 받는 Exchange 샘플링 된 연결</span><span class="sxs-lookup"><span data-stu-id="6b998-189">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="6b998-190">이러한 통찰력은 50% 이상의 샘플링 된 연결에 영향을 미칠 때이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-190">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="6b998-191">영향은 각 샘플에 대해 60% 미만으로 Exchange 평가에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-191">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="6b998-192">시나리오</span><span class="sxs-lookup"><span data-stu-id="6b998-192">What does this mean?</span></span>

<span data-ttu-id="6b998-193">대부분의 사용자에 게 Outlook에서 Exchange Online에 연결 하는 동안 사용자 환경 문제가 발생할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-193">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="6b998-194">샘플 비율은 60 포인트 미만으로 표시 되는 사용자의 비율을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-194">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="6b998-195">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b998-195">What should I do?</span></span>

<span data-ttu-id="6b998-196">Office 위치 네트워크 연결 표시 기능 사용 (아직 수행 하지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="6b998-196">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="6b998-197">Exchange에 영향을 주는 불량 네트워크 연결의 영향을 받는 사무실을 확인 하 고 사용자를 Microsoft 네트워크에 연결 하는 각 위치에서 네트워크 경계를 개선 하는 방법을 확인 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="6b998-197">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="6b998-198">연결 문제의 영향을 받는 SharePoint 샘플링 된 연결</span><span class="sxs-lookup"><span data-stu-id="6b998-198">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="6b998-199">이러한 통찰력은 50% 이상의 샘플링 된 연결에 영향을 미칠 때이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="6b998-200">영향은 각 샘플에 대 한 40% 미만으로 SharePoint 평가에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-200">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="6b998-201">시나리오</span><span class="sxs-lookup"><span data-stu-id="6b998-201">What does this mean?</span></span>

<span data-ttu-id="6b998-202">대부분의 사용자에 게 SharePoint 및 OneDrive의 사용자 환경 문제가 발생할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="6b998-203">샘플 비율은 40 포인트 미만으로 표시 되는 사용자의 비율을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b998-203">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="6b998-204">제가 뭘 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b998-204">What should I do?</span></span>

<span data-ttu-id="6b998-205">Office 위치 네트워크 연결 표시 기능 사용 (아직 수행 하지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="6b998-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="6b998-206">SharePoint에 영향을 주는 불량 네트워크 연결의 영향을 받는 사무실을 파악 하 고 사용자를 Microsoft 네트워크에 연결 하는 각각의 네트워크 경계를 개선 하는 방법을 확인 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="6b998-206">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b998-207">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6b998-207">Related topics</span></span>

[<span data-ttu-id="6b998-208">Microsoft 365 관리 센터의 네트워크 연결 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="6b998-208">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="6b998-209">Microsoft 365 네트워크 평가 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="6b998-209">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="6b998-210">Microsoft 365 네트워크 연결 테스트 도구 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="6b998-210">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="6b998-211">Microsoft 365 네트워크 연결 위치 서비스 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="6b998-211">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
