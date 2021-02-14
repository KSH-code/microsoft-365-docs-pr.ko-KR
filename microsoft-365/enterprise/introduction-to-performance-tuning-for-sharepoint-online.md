---
title: SharePoint Online의 성능 조정 소개
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: 이 문서에서는 SharePoint Online에서 최상의 성능을 위해 페이지를 디자인할 때 고려해야 하는 특정 측면에 대해 설명합니다.
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692789"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="ea832-103">SharePoint Online의 성능 조정 소개</span><span class="sxs-lookup"><span data-stu-id="ea832-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="ea832-104">이 문서에서는 SharePoint Online에서 최상의 성능을 위해 페이지를 디자인할 때 고려해야 하는 특정 측면에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="ea832-105">SharePoint Online 메트릭</span><span class="sxs-lookup"><span data-stu-id="ea832-105">SharePoint Online metrics</span></span>

<span data-ttu-id="ea832-106">SharePoint Online에 대한 다음과 같은 광범위한 메트릭은 성능에 대한 실제 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="ea832-107">페이지 로드 속도</span><span class="sxs-lookup"><span data-stu-id="ea832-107">How fast pages load</span></span>
    
- <span data-ttu-id="ea832-108">페이지당 필요한 왕복 수</span><span class="sxs-lookup"><span data-stu-id="ea832-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="ea832-109">서비스 문제</span><span class="sxs-lookup"><span data-stu-id="ea832-109">Issues with the service</span></span>
    
- <span data-ttu-id="ea832-110">성능 저하를 일으키는 기타 것</span><span class="sxs-lookup"><span data-stu-id="ea832-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="ea832-111">데이터로 결론을 도출했습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="ea832-112">데이터는 다음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-112">The data tells us:</span></span>
  
- <span data-ttu-id="ea832-113">대부분의 페이지는 SharePoint Online에서 잘 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="ea832-114">사용자 지정되지 않은 페이지는 매우 빠르게 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="ea832-115">비즈니스용 OneDrive, 팀 사이트 및 시스템 페이지(예: _layouts 등)는 모두 빠르게 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="ea832-116">SharePoint Online 페이지의 속도가 가장 느린 1%는 로드하는 데 5,000밀리초가 넘는 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="ea832-117">사용할 수 있는 한 가지 간단한 벤치마크 테스트는 사용자 지정된 몇 가지 기능을 사용하기에 따라 자체 포털의 로드 시간을 비즈니스용 OneDrive 홈 페이지의 로드 시간과 비교하여 성능을 측정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="ea832-118">이 단계는 종종 지원 서비스에서 네트워크 성능 문제를 해결할 때 완료를 요청하는 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="ea832-119">성능을 확인할 때 표준 사용자 계정 사용</span><span class="sxs-lookup"><span data-stu-id="ea832-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="ea832-120">사이트 모음 관리자, 사이트 소유자, 편집자 또는 참가자는 추가 보안 그룹에 속하며 추가 사용 권한을 가지기 때문에 SharePoint가 페이지에 로드하는 추가 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="ea832-121">이는 SharePoint Online 및 SharePoint Online에 적용할 수 있지만, SharePoint Online과는 다른 차이점이 쉽게 발견되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="ea832-122">사용자에 대해 페이지가 어떻게 수행될지 올바르게 평가하려면 표준 사용자 계정을 사용하여 제작 컨트롤 및 보안 그룹과 관련된 추가 트래픽이 로드되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="ea832-123">성능 조정을 위한 연결 범주</span><span class="sxs-lookup"><span data-stu-id="ea832-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="ea832-124">서버와 사용자 간의 연결을 세 가지 기본 구성 요소로 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="ea832-125">로드 시간을 파악하기 위해 SharePoint Online 페이지를 디자인할 때 이러한 정보를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="ea832-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="ea832-126">**서버** Microsoft가 데이터 센터에서 호스팅하는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="ea832-127">**네트워크** 데이터 센터와 사용자 간의 Microsoft 네트워크, 인터넷 및 프레미스 네트워크</span><span class="sxs-lookup"><span data-stu-id="ea832-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="ea832-128">**브라우저** 페이지가 로드되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="ea832-129">이러한 세 연결 내에 일반적으로 페이지 속도가 95%인 5가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="ea832-130">이 문서에서는 이러한 각 이유에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="ea832-131">탐색 문제</span><span class="sxs-lookup"><span data-stu-id="ea832-131">Navigation issues</span></span>
    
- <span data-ttu-id="ea832-132">콘텐츠 롤업</span><span class="sxs-lookup"><span data-stu-id="ea832-132">Content roll up</span></span>
    
- <span data-ttu-id="ea832-133">큰 파일</span><span class="sxs-lookup"><span data-stu-id="ea832-133">Large files</span></span>
    
- <span data-ttu-id="ea832-134">서버에 대한 많은 요청</span><span class="sxs-lookup"><span data-stu-id="ea832-134">Many requests to the server</span></span>
    
- <span data-ttu-id="ea832-135">웹 파트 처리</span><span class="sxs-lookup"><span data-stu-id="ea832-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="ea832-136">서버 연결</span><span class="sxs-lookup"><span data-stu-id="ea832-136">Server connection</span></span>

<span data-ttu-id="ea832-137">SharePoint의 성능에 영향을 주는 대부분의 문제는 SharePoint Online에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="ea832-138">예상한 것 처럼, 서버의 수행 방법을 훨씬 더 많이 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="ea832-139">SharePoint Online의 경우 상황이 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="ea832-140">서버에서 더 많은 작업을 할수록 페이지를 렌더링하는 데 더 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="ea832-141">SharePoint를 사용하는 경우 이러한 측면에서 가장 큰 장점은 여러 웹 파트가 있는 복잡한 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="ea832-142">SharePoint Server On-premises</span><span class="sxs-lookup"><span data-stu-id="ea832-142">SharePoint Server on-premises</span></span>
  
![온-프레미스 서버의 스크린샷](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="ea832-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ea832-144">SharePoint Online</span></span>
  
![온라인 서버의 스크린샷](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="ea832-146">SharePoint Online에서는 특정 페이지 요청이 실제로 여러 서버를 호출하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="ea832-147">개별 요청에 대한 서버 간의 요청 행렬이 끝날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="ea832-148">이러한 조작은 페이지 로드 관점에서 비용이 많이 들고 속도가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="ea832-149">서버 상호 작용에 대한 이러한 서버의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="ea832-150">웹에서 SQL 서버로</span><span class="sxs-lookup"><span data-stu-id="ea832-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="ea832-151">웹에서 응용 프로그램 서버로</span><span class="sxs-lookup"><span data-stu-id="ea832-151">Web to application servers</span></span>
    
<span data-ttu-id="ea832-152">서버 상호 작용이 느려질 수 있는 다른 것은 캐시 누락입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="ea832-153">On-premises SharePoint와 달리, 이전에 방문한 페이지에 대해 동일한 서버를 적중할 가능성이 매우 높습니다. 이렇게 하면 개체 캐싱이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="ea832-154">네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="ea832-154">Network connection</span></span>

<span data-ttu-id="ea832-155">WAN을 사용하지 않는온-프레미스 SharePoint에서는 데이터 센터와 최종 사용자 간의 고속 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="ea832-156">일반적으로 네트워크 관점에서 볼 때 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="ea832-157">SharePoint Online에서는 몇 가지 추가 요인을 고려해야 합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="ea832-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="ea832-158">Microsoft 네트워크</span><span class="sxs-lookup"><span data-stu-id="ea832-158">The Microsoft network</span></span>
    
- <span data-ttu-id="ea832-159">인터넷</span><span class="sxs-lookup"><span data-stu-id="ea832-159">The Internet</span></span>
    
- <span data-ttu-id="ea832-160">The ISP</span><span class="sxs-lookup"><span data-stu-id="ea832-160">The ISP</span></span>
    
<span data-ttu-id="ea832-161">사용중인 SharePoint 버전 및 네트워크와 관계없이 일반적으로 네트워크가 사용 중이 될 수 있는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="ea832-162">큰 페이로드</span><span class="sxs-lookup"><span data-stu-id="ea832-162">Large payload</span></span>
    
- <span data-ttu-id="ea832-163">많은 파일</span><span class="sxs-lookup"><span data-stu-id="ea832-163">Many files</span></span>
    
- <span data-ttu-id="ea832-164">서버와의 실제 거리가 먼 거리</span><span class="sxs-lookup"><span data-stu-id="ea832-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="ea832-165">SharePoint Online에서 활용할 수 있는 한 가지 기능은 Microsoft CDN(콘텐츠 배달 네트워크)입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="ea832-166">CDN은 기본적으로 여러 데이터 센터에 배포된 분산된 서버 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="ea832-167">CDN을 사용할 경우 클라이언트가 원래 SharePoint Server에서 멀리 떨어져 있는 경우에도 페이지의 콘텐츠를 클라이언트와 가까운 서버에서 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="ea832-168">Microsoft는 향후 이 기능을 사용하여 사용자 지정할 수 없는 로컬 페이지 인스턴스(예: SharePoint Online 관리자 홈 페이지)를 저장할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="ea832-169">CDNS에 대한 자세한 내용은 콘텐츠 배달 [네트워크를 참조하십시오.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="ea832-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="ea832-170">주의해야 하지만 ISP의 연결 속도에 대해 많은 작업을 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="ea832-171">간단한 속도 테스트 도구로 연결 속도를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="ea832-172">브라우저 연결</span><span class="sxs-lookup"><span data-stu-id="ea832-172">Browser connection</span></span>

<span data-ttu-id="ea832-173">성능 관점에서는 웹 브라우저에서 고려해야 할 몇 가지 요인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="ea832-174">복잡한 페이지를 방문하면 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="ea832-175">대부분의 브라우저에는 작은 캐시(약 90MB)만 있는 반면, 평균 웹 페이지는 일반적으로 약 1.6MB입니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="ea832-176">이렇게 하는 데는 시간이 오래 걸릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="ea832-177">대역폭도 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="ea832-178">예를 들어 사용자가 다른 세션에서 비디오를 보는 경우 SharePoint 페이지의 성능에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="ea832-179">사용자가 스트리밍 미디어를 스트리밍하지 못하게 할 수 있는 반면, 사용자가 페이지를 로드하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea832-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="ea832-180">최적의 성능을 얻을 수 있도록 다양한 SharePoint Online 페이지 사용자 지정 기술 및 기타 모범 사례에 대한 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea832-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="ea832-181">SharePoint Online의 탐색 옵션</span><span class="sxs-lookup"><span data-stu-id="ea832-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="ea832-182">SharePoint Online용 페이지 진단 도구 사용</span><span class="sxs-lookup"><span data-stu-id="ea832-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="ea832-183">SharePoint Online에 대한 이미지 최적화</span><span class="sxs-lookup"><span data-stu-id="ea832-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="ea832-184">SharePoint Online에서 이미지 및 JavaScript 로드 지연</span><span class="sxs-lookup"><span data-stu-id="ea832-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="ea832-185">SharePoint Online의 축소 및 묶음</span><span class="sxs-lookup"><span data-stu-id="ea832-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="ea832-186">sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기</span><span class="sxs-lookup"><span data-stu-id="ea832-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="ea832-187">콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용하여 SharePoint Online의 성능 향상</span><span class="sxs-lookup"><span data-stu-id="ea832-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- <span data-ttu-id="ea832-188">[Capacity planning and load testing SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)(용량 계획과 부하 테스트가 가능한 SharePoint Online)</span><span class="sxs-lookup"><span data-stu-id="ea832-188">[Capacity planning and load testing SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)</span></span>
    
- [<span data-ttu-id="ea832-189">SharePoint Online의 성능 문제 진단</span><span class="sxs-lookup"><span data-stu-id="ea832-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="ea832-190">SharePoint online에서 개체 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="ea832-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="ea832-191">방법: SharePoint Online에서 스로틀되거나 차단되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="ea832-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

