---
title: SharePoint Online의 탐색 옵션
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: 이 문서에서는 SharePoint Online에서 SharePoint 게시를 사용하도록 설정한 탐색 옵션 사이트에 대해 설명합니다.
ms.openlocfilehash: b5989bf26ebf7bb1452f983af89a6e6739821d53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923627"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="4ccf3-103">SharePoint Online의 탐색 옵션</span><span class="sxs-lookup"><span data-stu-id="4ccf3-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="4ccf3-104">이 문서에서는 SharePoint Online에서 SharePoint 게시를 사용하도록 설정한 탐색 옵션 사이트에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="4ccf3-105">탐색 선택 및 구성은 SharePoint Online의 사이트 성능 및 확장성에 큰 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="4ccf3-106">SharePoint 게시 사이트 서식 파일은 중앙 집중식 포털에 필요한 경우만 사용해야 합니다. 게시 기능은 특정 사이트에서만 사용하도록 설정해야 합니다. 잘못 사용될 경우 성능에 영향을 줄 수 있는 특정 사이트에서만 게시 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="4ccf3-107">메가 메뉴, 계단식 탐색 또는 허브 탐색과 같은 최신 SharePoint 탐색 옵션을 사용하는 경우 이 문서는 사이트에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="4ccf3-108">최신 SharePoint 사이트 아키텍처는 보다 평면적인 사이트 계층 구조와 허브 및 스포크 모델을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="4ccf3-109">따라서 SharePoint 게시 기능을 사용할 필요가 없는 많은 시나리오를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="4ccf3-110">탐색 옵션 개요</span><span class="sxs-lookup"><span data-stu-id="4ccf3-110">Overview of navigation options</span></span>

<span data-ttu-id="4ccf3-111">탐색 공급자 구성은 전체 사이트의 성능에 큰 영향을 줄 수 있으며, SharePoint 사이트의 요구 사항에 따라 효과적으로 확장되는 탐색 공급자 및 구성을 선택하려면 신중하게 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="4ccf3-112">사용자 지정 탐색 구현뿐만 아니라 두 가지 바로 사용 가능한 탐색 공급자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="4ccf3-113">사이트에 대한 [](#using-structural-navigation-in-sharepoint-online)구조적 탐색 캐싱을 설정하는 경우 첫 번째 옵션인 구조 탐색 은 클래식 SharePoint 사이트에 대해 SharePoint Online의 권장 탐색 **옵션입니다.**</span><span class="sxs-lookup"><span data-stu-id="4ccf3-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="4ccf3-114">이 탐색 공급자는 현재 사이트 아래에 탐색 항목을 표시하고 선택적으로 현재 사이트와 해당 형제 항목을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="4ccf3-115">보안 자르기 및 사이트 구조 열0과 같은 추가 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="4ccf3-116">캐싱을 사용하지 않도록 설정하면 성능 및 확장성에 부정적인 영향을 미치며, 조정이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="4ccf3-117">두 번째 옵션인 [**관리(메타데이터) 탐색은**](#using-managed-navigation-and-metadata-in-sharepoint-online)관리되는 메타데이터 용어 집합을 사용하는 탐색 항목을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="4ccf3-118">필요한 경우를 위해 보안 트리밍을 사용하지 않도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="4ccf3-119">보안 트리밍은 이 탐색 공급자에 대한 보안 기본 설정으로 사용됩니다. 그러나 대부분의 사이트에서는 탐색 요소가 사이트의 모든 사용자에게 일관성이 유지되는 경우가 많기 때문에 보안 자르기 오버헤드가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="4ccf3-120">보안 조정을 사용하지 않도록 설정하는 권장 구성을 통해 이 탐색 공급자는 사이트 구조를 열000개할 필요가 없습니다. 성능에 대한 영향이 적정 수준으로 확장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="4ccf3-121">첫 실행 탐색 공급자 외에도 많은 고객이 대체 사용자 지정 탐색 구현을 성공적으로 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="4ccf3-122">이 문서의 검색 [기반 클라이언트 쪽 스크립팅을](#using-search-driven-client-side-scripting) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="4ccf3-123">SharePoint Online의 장단점 탐색 옵션</span><span class="sxs-lookup"><span data-stu-id="4ccf3-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="4ccf3-124">다음 표에서는 각 옵션의 장단을 요약하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="4ccf3-125">구조 탐색</span><span class="sxs-lookup"><span data-stu-id="4ccf3-125">Structural navigation</span></span>  |<span data-ttu-id="4ccf3-126">관리 탐색</span><span class="sxs-lookup"><span data-stu-id="4ccf3-126">Managed navigation</span></span>  |<span data-ttu-id="4ccf3-127">검색 기반 탐색</span><span class="sxs-lookup"><span data-stu-id="4ccf3-127">Search-driven navigation</span></span>  |<span data-ttu-id="4ccf3-128">사용자 지정 탐색 공급자</span><span class="sxs-lookup"><span data-stu-id="4ccf3-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="4ccf3-129">Pros:</span><span class="sxs-lookup"><span data-stu-id="4ccf3-129">Pros:</span></span><br/><br/><span data-ttu-id="4ccf3-130">유지 관리가 간편합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-130">Easy to maintain</span></span><br/><span data-ttu-id="4ccf3-131">보안이 잘림</span><span class="sxs-lookup"><span data-stu-id="4ccf3-131">Security trimmed</span></span><br/><span data-ttu-id="4ccf3-132">콘텐츠가 변경될 때 24시간 이내에 자동으로 업데이트</span><span class="sxs-lookup"><span data-stu-id="4ccf3-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="4ccf3-133">Pros:</span><span class="sxs-lookup"><span data-stu-id="4ccf3-133">Pros:</span></span><br/><br/><span data-ttu-id="4ccf3-134">유지 관리가 간편합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-134">Easy to maintain</span></span><br/>|<span data-ttu-id="4ccf3-135">Pros:</span><span class="sxs-lookup"><span data-stu-id="4ccf3-135">Pros:</span></span><br/><br/><span data-ttu-id="4ccf3-136">보안이 잘림</span><span class="sxs-lookup"><span data-stu-id="4ccf3-136">Security trimmed</span></span><br/><span data-ttu-id="4ccf3-137">사이트가 추가될 때 자동으로 업데이트</span><span class="sxs-lookup"><span data-stu-id="4ccf3-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="4ccf3-138">빠른 로드 시간 및 로컬 캐시된 탐색 구조</span><span class="sxs-lookup"><span data-stu-id="4ccf3-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="4ccf3-139">Pros:</span><span class="sxs-lookup"><span data-stu-id="4ccf3-139">Pros:</span></span><br/><br/><span data-ttu-id="4ccf3-140">사용 가능한 다양한 옵션</span><span class="sxs-lookup"><span data-stu-id="4ccf3-140">Wider choice of options available</span></span><br/><span data-ttu-id="4ccf3-141">캐싱이 올바르게 사용되는 경우 빠른 로드</span><span class="sxs-lookup"><span data-stu-id="4ccf3-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="4ccf3-142">많은 옵션이 반응형 페이지 디자인에 잘 작동</span><span class="sxs-lookup"><span data-stu-id="4ccf3-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="4ccf3-143">Cons:</span><span class="sxs-lookup"><span data-stu-id="4ccf3-143">Cons:</span></span><br/><br/><span data-ttu-id="4ccf3-144">**캐싱을 사용하지 않도록 설정한 경우 성능에 영향을 미치기**</span><span class="sxs-lookup"><span data-stu-id="4ccf3-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="4ccf3-145">스로틀 적용</span><span class="sxs-lookup"><span data-stu-id="4ccf3-145">Subject to throttling</span></span><br/>|<span data-ttu-id="4ccf3-146">Cons:</span><span class="sxs-lookup"><span data-stu-id="4ccf3-146">Cons:</span></span><br/><br/><span data-ttu-id="4ccf3-147">사이트 구조를 반영하기 위해 자동으로 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="4ccf3-148">**보안 트리밍을** 사용하도록 설정하거나 탐색 구조가 복잡할 경우 성능에 영향을 미치기</span><span class="sxs-lookup"><span data-stu-id="4ccf3-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="4ccf3-149">Cons:</span><span class="sxs-lookup"><span data-stu-id="4ccf3-149">Cons:</span></span><br/><br/><span data-ttu-id="4ccf3-150">사이트를 쉽게 주문할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="4ccf3-150">No ability to easily order sites</span></span><br/><span data-ttu-id="4ccf3-151">마스터 페이지를 사용자 지정해야 합니다(기술 기술 필요).</span><span class="sxs-lookup"><span data-stu-id="4ccf3-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="4ccf3-152">Cons:</span><span class="sxs-lookup"><span data-stu-id="4ccf3-152">Cons:</span></span><br/><br/><span data-ttu-id="4ccf3-153">사용자 지정 개발이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-153">Custom development is required</span></span><br/><span data-ttu-id="4ccf3-154">외부 데이터 원본/저장된 캐시가 필요합니다(예: Azure).</span><span class="sxs-lookup"><span data-stu-id="4ccf3-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="4ccf3-155">사이트에 가장 적합한 옵션은 사이트 요구 사항 및 기술 기능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="4ccf3-156">콘텐츠가 변경될 때 자동으로 업데이트되는 구성하기 쉬운 탐색 공급자를 [](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) 원하는 경우 캐싱을 사용하는 구조 탐색이 좋은 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="4ccf3-157">전체 사이트 구조를 계층 구조가 단순화하여 최신 SharePoint 사이트와 동일한 원칙을 적용하면 성능이 향상되고 최신 SharePoint 사이트로의 이동이 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="4ccf3-158">즉, 수백 개의 사이트(하위 웹)가 있는 단일 사이트 모음을 사용할 수 있는 대신 하위 사이트(하위 웹)가 거의 없는 사이트 모음이 많이 있는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="4ccf3-159">SharePoint Online에서 탐색 성능 분석</span><span class="sxs-lookup"><span data-stu-id="4ccf3-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="4ccf3-160">[SharePoint용](./page-diagnostics-for-spo.md) 페이지 진단 도구는 SharePoint Online 최신 포털 및 클래식 게시 사이트 페이지를 모두 분석하는 Microsoft Edge 및 Chrome 브라우저의 브라우저 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-160">The [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="4ccf3-161">이 도구는 SharePoint Online에서만 작동하며 SharePoint 시스템 페이지에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="4ccf3-162">이 도구는 미리 정의된 규칙 집합에 대해 페이지가 수행되는 방법을 보여 주며, 테스트 결과가 기준 값에 맞지 않은 경우 자세한 정보를 표시하는 분석된 각 페이지에 대한 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="4ccf3-163">SharePoint Online 관리자 및 디자이너는 이 도구를 사용하여 성능 문제를 해결하여 게시 전에 새 페이지를 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="4ccf3-164">**특히 SPRequestDuration은** SharePoint에서 페이지를 처리하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="4ccf3-165">탐색에 페이지 포함, 복잡한 사이트 계층 및 기타 구성 및 토폴로지 옵션이 모두 긴 기간에 기여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="4ccf3-166">SharePoint Online에서 구조 탐색 사용</span><span class="sxs-lookup"><span data-stu-id="4ccf3-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="4ccf3-167">이 탐색은 기본적으로 사용되는 기본 제공 탐색으로, 가장 간단한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="4ccf3-168">또한 사용자 지정이 필요하지 않은 사용자도 항목을 쉽게 추가하고, 항목을 숨기고, 설정 페이지에서 탐색을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="4ccf3-169">[캐싱을 사용하도록](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)설정하는 것이 좋습니다. 그렇지 않은 경우 성능에 많은 비용이 드는 상거래가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="4ccf3-170">구조 탐색 캐싱을 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="4ccf3-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="4ccf3-171">사이트 **설정 디자인** 탐색에서 전역 탐색 또는 현재 탐색에 대해 구조적 탐색이 선택되어 있는지  >    >  확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="4ccf3-172">페이지 **표시를 선택하면** 성능에 부정적인 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![하위 페이지 표시가 선택된 구조 탐색](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="4ccf3-174">캐싱은 사이트 모음 수준과 사이트 수준에서 사용하도록 설정하거나 사용하지 않도록 설정할 수 있으며 기본적으로 둘 다에 대해 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="4ccf3-175">사이트 모음 수준에서 사용하도록 설정하려면 사이트 설정 사이트 모음 관리 사이트 모음  >    >  **탐색에서** 캐싱 사용 **확인란을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ccf3-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![사이트 수준에서 캐싱 사용](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="4ccf3-177">사이트 수준에서 사용하도록 설정하려면 사이트 설정  >  **탐색에서** 캐싱 사용 **확인란을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ccf3-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![사이트 수준에서 캐싱 사용](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="4ccf3-179">SharePoint Online에서 관리 탐색 및 메타데이터 사용</span><span class="sxs-lookup"><span data-stu-id="4ccf3-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="4ccf3-180">관리 탐색은 구조 탐색과 동일한 기능을 대부분 다시하는 데 사용할 수 있는 또 다른 첫 번째 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="4ccf3-181">관리되는 메타데이터는 보안 트리밍을 사용하도록 구성하거나 사용하지 않도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="4ccf3-182">보안 트리밍을 사용하지 않도록 구성하면 관리 탐색이 일정한 수의 서버 호출로 모든 탐색 링크를 로드할 때 매우 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="4ccf3-183">그러나 보안 트리밍을 사용하도록 설정하면 관리 탐색의 성능 이점 중 일부를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="4ccf3-184">보안 트리밍을 사용하도록 설정해야 하는 경우 다음을 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="4ccf3-185">모든 친숙한 URL 링크를 단순 링크로 업데이트</span><span class="sxs-lookup"><span data-stu-id="4ccf3-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="4ccf3-186">필요한 보안 트리밍 노드를 친숙한 URL로 추가</span><span class="sxs-lookup"><span data-stu-id="4ccf3-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="4ccf3-187">탐색 항목 수를 100개 이상, 수준 3개까지 제한</span><span class="sxs-lookup"><span data-stu-id="4ccf3-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="4ccf3-188">대부분의 사이트에서는 탐색 구조가 사이트의 모든 사용자에 대해 일관성이 유지되는 경우가 많기 때문에 보안 트리밍이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="4ccf3-189">보안 트리밍을 사용하지 않도록 설정하고 일부 사용자가 액세스할 수 없는 링크가 탐색에 추가된 경우 링크는 계속 표시되지만 액세스 거부 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="4ccf3-190">콘텐츠에 부적당하게 액세스할 위험이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="4ccf3-191">관리 탐색 및 결과를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="4ccf3-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="4ccf3-192">관리 탐색의 세부 docs.microsoft.com 문서가 몇 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="4ccf3-193">예를 들어 [SharePoint Server의 관리 탐색 개요를 참조하세요.](/sharepoint/administration/overview-of-managed-navigation)</span><span class="sxs-lookup"><span data-stu-id="4ccf3-193">For example, see [Overview of managed navigation in SharePoint Server](/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="4ccf3-194">관리 탐색을 구현하기 위해 사이트의 탐색 구조에 해당하는 URL을 사용하여 용어를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="4ccf3-195">대부분의 경우 구조 탐색을 대체하기 위해 관리 탐색을 수동으로 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="4ccf3-196">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-196">For example:</span></span>

![SharePoint Online 사이트 구조](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="4ccf3-198">)</span><span class="sxs-lookup"><span data-stu-id="4ccf3-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="4ccf3-199">검색 기반 클라이언트 쪽 스크립팅 사용</span><span class="sxs-lookup"><span data-stu-id="4ccf3-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="4ccf3-200">사용자 지정 탐색 구현의 공통 클래스 중 하나는 탐색 노드의 로컬 캐시를 저장하는 클라이언트 렌더링 디자인 패턴을 수용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="4ccf3-201">이러한 탐색 공급자에는 몇 가지 주요 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="4ccf3-202">일반적으로 반응형 페이지 디자인에서 잘 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="4ccf3-203">리소스 비용으로 렌더링할 수 있으며 시간 제한 후 백그라운드에서 새로 고칠 수 있기 때문에 확장성이 매우 능동적입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="4ccf3-204">이러한 탐색 공급자는 간단한 정적 구성에서 다양한 동적 데이터 공급자에 이르기까지 다양한 전략을 사용하여 탐색 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="4ccf3-205">데이터 공급자의 예로는 검색 기반 탐색을 사용하여 탐색 노드를 열고 보안 트리밍을 효율적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="4ccf3-206">사용자 지정 탐색 공급자를 빌드하는 다른 **인기 있는 옵션이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4ccf3-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="4ccf3-207">사용자 지정 탐색 공급자를 구축하는 방법에 대한 자세한 지침은 [SharePoint Online](/sharepoint/dev/solution-guidance/portal-navigation) 포털의 탐색 솔루션을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-207">Please review [Navigation solutions for SharePoint Online portals](/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="4ccf3-208">검색을 사용하면 연속 크롤링을 사용하여 백그라운드에서 구축된 인덱스를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="4ccf3-209">검색 결과는 검색 인덱스에서 끌어오고 결과는 보안이 잘림됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="4ccf3-210">이는 일반적으로 보안 트리밍이 필요한 경우 첫 탐색 공급자보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="4ccf3-211">구조 탐색 검색을 사용하면 특히 사이트 구조가 복잡한 경우 페이지 로드 시간이 상당히 빠를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="4ccf3-212">관리 탐색을 통해 이 기능의 주요 이점은 보안 트리밍을 활용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="4ccf3-213">이 방법을 사용하려면 사용자 지정 마스터 페이지를 만들고 바로 실행 탐색 코드를 사용자 지정 HTML로 바꾸는 과정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="4ccf3-214">다음 예제에 설명된 다음 절차에 따라 파일의 탐색 코드를 `seattle.html` 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="4ccf3-215">이 예제에서는 파일을 열고 전체 요소를 사용자 지정 `seattle.html` `id="DeltaTopNavigation"` HTML 코드로 바립니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="4ccf3-216">예제: 마스터 페이지에서 첫 실행 탐색 코드 바꾸기</span><span class="sxs-lookup"><span data-stu-id="4ccf3-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="4ccf3-217">사이트 설정 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="4ccf3-218">마스터 페이지 를 클릭하여 마스터 페이지 **갤러리를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4ccf3-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="4ccf3-219">여기에서 라이브러리를 탐색하고 파일을 다운로드할 수 `seattle.master` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="4ccf3-220">텍스트 편집기를 사용하여 코드를 편집하고 다음 스크린샷에서 코드 블록을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![표시된 코드 블록 삭제](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="4ccf3-222">및 태그 사이에 있는 코드를 제거하고 다음 코드 코드로 `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. <span data-ttu-id="4ccf3-223">시작에 있는 로드 이미지 앵커 태그의 URL을 사이트 모음의 로드 이미지에 대한 링크로 바니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="4ccf3-224">변경한 후 파일 이름을 바 변경한 다음 마스터 페이지 갤러리에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="4ccf3-225">그러면 새 .master 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="4ccf3-226">이 HTML은 JavaScript 코드에서 반환된 검색 결과로 채워지는 기본 마크업입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="4ccf3-227">다음 코드 코드에서 설명한 var 루트 = "사이트 모음 URL"의 값을 변경하려면 코드를 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="4ccf3-228">결과는 self.nodes 배열에 할당되어 배열 self.hierarchy에 출력을 할당하는 linq.js 계층 구조가 개체에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="4ccf3-229">이 배열은 HTML에 바인딩된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="4ccf3-230">이는 toggleView() 함수에서 자체 개체를 ko.applyBinding() 함수에 전달하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="4ccf3-231">그러면 계층 구조 배열이 다음 HTML에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="4ccf3-232">및 에 대한 이벤트 처리기 는 함수에서 수행되는 하위사이트 드롭다운 메뉴를 처리하기 위해 최상위 탐색에 `mouseenter` `mouseexit` `addEventsToElements()` 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="4ccf3-233">복잡한 탐색 예제에서 로컬 캐싱이 없는 새 페이지 로드는 관리 탐색 방법과 비슷한 결과를 얻기 위해 서버에 소요된 시간이 벤치마크 구조 탐색에서 끊어졌다는 표시를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="4ccf3-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="4ccf3-234">JavaScript 파일...</span><span class="sxs-lookup"><span data-stu-id="4ccf3-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="4ccf3-235">사용자 지정 JavaScript를 사용하는 경우 공용 CDN이 사용하도록 설정되어 있으며 파일이 CDN 위치에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="4ccf3-236">전체 JavaScript 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-236">The entire JavaScript file is as follows:</span></span>

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

<span data-ttu-id="4ccf3-237">함수에 위에 표시된 코드를 요약하기 위해 만들어진 다음 해당 개체에 대한 함수가 `jQuery $(document).ready` `viewModel object` `loadNavigationNodes()` 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="4ccf3-238">이 함수는 클라이언트 브라우저의 HTML5 로컬 저장소에 저장된 이전에 구축된 탐색 계층 구조를 로드하거나 함수를 `queryRemoteInterface()` 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="4ccf3-239">`QueryRemoteInterface()` 스크립트의 앞부분에서 정의한 query 매개 변수와 함께 함수를 사용하여 요청을 작성한 다음 서버에서 데이터를 `getRequest()` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="4ccf3-240">이 데이터는 기본적으로 다양한 속성을 사용하여 데이터 전송 개체로 표현되는 사이트 모음의 모든 사이트의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="4ccf3-241">이 데이터는 이전에 정의한 HTML에 값을 바인딩하여 사용할 관찰 가능한 속성을 만드는 데 사용하는 이전에 정의된 개체로 `SPO.Models.NavigationNode` `Knockout.js` 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="4ccf3-242">그런 다음 개체가 결과 배열에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-242">The objects are then put into a results array.</span></span> <span data-ttu-id="4ccf3-243">이 배열은 Knockout을 사용하여 JSON으로 구문 분석되고 향후 페이지 로드 시 성능을 향상하기 위해 로컬 브라우저 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="4ccf3-244">이 방법의 이점</span><span class="sxs-lookup"><span data-stu-id="4ccf3-244">Benefits of this approach</span></span>

<span data-ttu-id="4ccf3-245">이 방법의 [](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) 주요 이점 중 하나는 HTML5 로컬 저장소를 사용하여 다음에 페이지를 로드할 때 사용자의 탐색이 로컬에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="4ccf3-246">구조 탐색에 검색 API를 사용할 경우 성능이 주요 향상됩니다. 그러나 이 기능을 실행하고 사용자 지정하는 데는 몇 가지 기술적인 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="4ccf3-247">예제 [구현에서](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)사이트는 첫 실행 구조 탐색과 같은 방식으로 순서가 정해진 것입니다. 사전순</span><span class="sxs-lookup"><span data-stu-id="4ccf3-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="4ccf3-248">이 순서에서 을(를) 를(를) 하여 개발하고 유지 관리하는 것이 더 복잡할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="4ccf3-249">또한 이 방법을 사용하려면 지원되는 마스터 페이지에서 이 방법을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="4ccf3-250">사용자 지정 마스터 페이지가 유지 관리되지 않는 경우 사이트가 Microsoft에서 마스터 페이지에 적용하는 업데이트 및 개선된 기능에서 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="4ccf3-251">위의 [코드에는](#about-the-javascript-file) 다음과 같은 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="4ccf3-252">jQuery - https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="4ccf3-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="4ccf3-253">KnockoutJS - https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="4ccf3-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="4ccf3-254">Linq.js - https://linqjs.codeplex.com/ 또는 github.com/neuecc/linq.js</span><span class="sxs-lookup"><span data-stu-id="4ccf3-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="4ccf3-255">현재 버전의 LinqJS에는 위의 코드에 사용된 ByHierarchy 메서드가 포함되어 있지 않은 경우 탐색 코드가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="4ccf3-256">이 문제를 해결하기 위해 줄 앞에 다음 Linq.js 메서드를 `Flatten: function ()` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ccf3-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a><span data-ttu-id="4ccf3-257">관련 주제</span><span class="sxs-lookup"><span data-stu-id="4ccf3-257">Related topics</span></span>

[<span data-ttu-id="4ccf3-258">SharePoint Server의 관리 탐색 개요</span><span class="sxs-lookup"><span data-stu-id="4ccf3-258">Overview of managed navigation in SharePoint Server</span></span>](/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="4ccf3-259">구조적 탐색 캐싱 및 성능</span><span class="sxs-lookup"><span data-stu-id="4ccf3-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)