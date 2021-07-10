---
title: Microsoft 365 Multi-Geo 검색 구성
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Multi-Geo 환경에서 검색을 구성하는 방법을 학습합니다. 다중 위치 환경의 OneDrive 클라이언트만 결과를 반환할 수 있습니다.
ms.openlocfilehash: dfc9e3dd986132810f363ba47ba18eae45666fc7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362273"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a><span data-ttu-id="2f01f-104">Microsoft 365 Multi-Geo 검색 구성</span><span class="sxs-lookup"><span data-stu-id="2f01f-104">Configure Search for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="2f01f-105">다중 지역 환경에서 각 지리적 위치에는 자체 검색 인덱스와 검색 센터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-105">In a multi-geo environment, each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="2f01f-106">사용자가 검색을 하면 쿼리가 모드 인덱스로 팬아웃되고 반환된 결과는 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-106">When a user searches, the query is fanned out to all the indexes, and the returned results are merged.</span></span>

<span data-ttu-id="2f01f-107">예를 들어, 한 지리적 위치에 있는 사용자가 다른 지리적 위치에 저장된 콘텐츠를 검색하거나, 다른 지리적 위치로 제한된 SharePoint 사이트에서 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-107">For example, a user in one geo location can search for content stored in another geo location, or for content on a SharePoint site that's restricted to a different geo location.</span></span> <span data-ttu-id="2f01f-108">사용자가 이 콘텐츠에 액세스할 수 있으면 검색 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-108">If the user has access to this content, search will show the result.</span></span>

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a><span data-ttu-id="2f01f-109">Multi-Geo 환경에서는 어떤 검색 클라이언트가 사용되나요?</span><span class="sxs-lookup"><span data-stu-id="2f01f-109">Which search clients work in a multi-geo environment?</span></span>

<span data-ttu-id="2f01f-110">이러한 클라이언트는 모든 지리적 위치의 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-110">These clients can return results from all geo locations:</span></span>

- <span data-ttu-id="2f01f-111">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2f01f-111">OneDrive</span></span>
- <span data-ttu-id="2f01f-112">Delve</span><span class="sxs-lookup"><span data-stu-id="2f01f-112">Delve</span></span>
- <span data-ttu-id="2f01f-113">SharePoint 홈페이지</span><span class="sxs-lookup"><span data-stu-id="2f01f-113">The SharePoint home page</span></span>
- <span data-ttu-id="2f01f-114">검색 센터</span><span class="sxs-lookup"><span data-stu-id="2f01f-114">The Search Center</span></span>
- <span data-ttu-id="2f01f-115">SharePoint 검색 API를 사용하는 사용자 지정 검색 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2f01f-115">Custom search applications that use the SharePoint Search API</span></span>

### <a name="onedrive"></a><span data-ttu-id="2f01f-116">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2f01f-116">OneDrive</span></span>

<span data-ttu-id="2f01f-117">Multi-Geo 환경이 설정되는 즉시, OneDrive에서 검색하는 사용자는 모든 지리적 위치에서 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-117">As soon as the multi-geo environment has been set up, users that search in OneDrive get results from all geo locations.</span></span>

### <a name="delve"></a><span data-ttu-id="2f01f-118">Delve</span><span class="sxs-lookup"><span data-stu-id="2f01f-118">Delve</span></span>

<span data-ttu-id="2f01f-119">Multi-Geo 환경이 설정되는 즉시, Delve에서 검색하는 사용자는 모든 지리적 위치에서 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-119">As soon as the multi-geo environment has been set up, users that search in Delve get results from all geo locations.</span></span>

<span data-ttu-id="2f01f-p104">Delve 피드 및 프로필 카드는 중앙 위치에 저장된 파일의 미리 보기만 표시합니다. 위성 위치에 저장된 파일의 경우 대신 해당 파일 형식에 대한 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-p104">The Delve feed and the profile card only show previews of files that are stored in the central location. For files that are stored in satellite locations, the icon for the file type is shown instead.</span></span>

### <a name="the-sharepoint-home-page"></a><span data-ttu-id="2f01f-122">SharePoint 홈페이지</span><span class="sxs-lookup"><span data-stu-id="2f01f-122">The SharePoint home page</span></span>

<span data-ttu-id="2f01f-p105">Multi-Geo 환경이 설정되는 즉시, 사용자는 SharePoint 홈페이지에서 다중 지리적 위치의 뉴스, 최근 사이트 및 팔로우된 사이트를 볼 수 있습니다. SharePoint 홈페이지의 검색 상자를 사용하는 경우 다중 지리적 위치에서 병합된 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-p105">As soon as the multi-geo environment has been set up, users will see news, recent and followed sites from multiple geo locations on their SharePoint home page. If they use the search box on the SharePoint home page, they'll get merged results from multiple geo locations.</span></span>

### <a name="the-search-center"></a><span data-ttu-id="2f01f-125">검색 센터</span><span class="sxs-lookup"><span data-stu-id="2f01f-125">The Search Center</span></span>

<span data-ttu-id="2f01f-p106">Multi-Geo 환경이 설정된 후에 각 검색 센터는 자체 지리적 위치의 결과만 계속 표시합니다. 관리자는 모든 지리적 위치에서 결과를 가져오려면 [각 검색 센터의 설정을 변경](#_Set_up_a_1)해야 합니다. 그런 후에 검색 센터에서 검색을 하는 사용자는 모든 지리적 위치에서 결과를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-p106">After the multi-geo environment has been set up, each Search Center continues to only show results from their own geo location. Admins must [change the settings of each Search Center](#_Set_up_a_1) to get results from all geo locations. Afterwards, users that search in the Search Center get results from all geo locations.</span></span>

### <a name="custom-search-applications"></a><span data-ttu-id="2f01f-129">사용자 지정 검색 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2f01f-129">Custom search applications</span></span>

<span data-ttu-id="2f01f-p107">일반적인 경우처럼, 사용자 지정 검색 응용 프로그램은 기존 SharePoint 검색 REST API를 사용하여 검색 인덱스와 상호 작용합니다. 모든 또는 일부 지리적 위치에서 결과를 얻으려면 응용 프로그램은 [API를 호출하고 요청에 새 Multi-Geo 쿼리 매개 변수를 포함](#_Get_custom_search)해야 합니다. 이렇게 하면 모든 지리적 위치로의 쿼리 팬아웃이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-p107">As usual, custom search applications interact with the search indexes by using the existing SharePoint Search REST APIs. To get results from all, or some geo locations, the application must [call the API and include the new Multi-Geo query parameters](#_Get_custom_search) in the request. This triggers a fan out of the query to all geo locations.</span></span>

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a><span data-ttu-id="2f01f-133">Multi-Geo 환경에서 검색의 차이점은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2f01f-133">What's different about search in a multi-geo environment?</span></span>

<span data-ttu-id="2f01f-134">이미 익숙할 수 있는 일부 검색 기능이 Multi-Geo 환경에서는 다르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-134">Some search features you might be familiar with, work differently in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f01f-135">기능</span><span class="sxs-lookup"><span data-stu-id="2f01f-135">Feature</span></span></th>
<th align="left"><span data-ttu-id="2f01f-136">작동 방법</span><span class="sxs-lookup"><span data-stu-id="2f01f-136">How it works</span></span></th>
<th align="left"><span data-ttu-id="2f01f-137">해결 방법</span><span class="sxs-lookup"><span data-stu-id="2f01f-137">Workaround</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2f01f-138">승격된 결과</span><span class="sxs-lookup"><span data-stu-id="2f01f-138">Promoted results</span></span></td>
<td align="left"><span data-ttu-id="2f01f-139">전체 수준의 테넌트, 사이트 모음 또는 사이트에 대해 승격된 결과가 포함 된 쿼리 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-139">You can create query rules with promoted results at different levels: for the whole tenant, for a site collection, or for a site.</span></span> <span data-ttu-id="2f01f-140">Multi-Geo 환경에서 테넌트 수준의 승격된 결과를 정의하여 모든 지역의 검색 센터로 결과를 승격하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f01f-140">In a multi-geo environment, define promoted results at the tenant level to promote the results to the Search Centers in all geo locations.</span></span> <span data-ttu-id="2f01f-141">사이트 모음 또는 사이트의 위치에 있는 검색 센터에서만 결과를 승격하려면 사이트 모음 또는 사이트 수준에서 승격된 결과를 정의하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f01f-141">If you only want to promote results in the Search Center that's in the geo location of the site collection or site, define the promoted results at the site collection or site level.</span></span> <span data-ttu-id="2f01f-142">이 결과는 다른 지리적 위치에서 승격되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-142">These results are not promoted in other geo locations.</span></span></td>
<td align="left"><span data-ttu-id="2f01f-143">지리적 위치별로 승격된 다른 결과가 필요하지 않을 경우(예: 여행에 대해 다른 규칙 지정) 테넌트 수준에서 승격된 결과를 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-143">If you don't need different promoted results per geo location, for example different rules for traveling, we recommend defining promoted results at the tenant level.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2f01f-144">검색 구체화</span><span class="sxs-lookup"><span data-stu-id="2f01f-144">Search refiners</span></span></td>
<td align="left"><span data-ttu-id="2f01f-p109">검색은 테넌트의 모든 지리적 위치에서 구체화 결과를 반환한 후 집계합니다. 이러한 집계에는 가능한 최선의 노력이 수반되며, 구체화 개수가 100% 정확하지 않을 수도 있습니다. 대부분의 검색 기반 시나리오에서는 이 정도의 정확도로 충분합니다. </span><span class="sxs-lookup"><span data-stu-id="2f01f-p109">Search returns refiners from all the geo locations of a tenant and then aggregates them. The aggregation is a best effort, meaning that the refiner counts might not be 100% accurate. For most search-driven scenarios, this accuracy is sufficient. </span></span></td>
<td align="left"><span data-ttu-id="2f01f-148">구체화 완성도에 의존하는 검색 기반 응용 프로그램의 경우 개별적으로 각 지리적 위치를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-148">For search-driven applications that depend on refiner completeness, query each geo location independently.</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="2f01f-149">Multi-Geo 검색은 수치 구체화에 대한 동적 버킷팅을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-149">Multi-geo search doesn't support dynamic bucketing for numerical refiners.</span></span></td>
<td align="left"><span data-ttu-id="2f01f-150">숫자 <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">구체화에 "Discretize"</a> 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-150">Use the <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">"Discretize" parameter</a> for numerical refiners.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2f01f-151">문서 ID</span><span class="sxs-lookup"><span data-stu-id="2f01f-151">Document IDs</span></span></td>
<td align="left"><span data-ttu-id="2f01f-152">문서 ID에 의존하는 검색 기반 응용 프로그램을 개발하는 경우 Multi-Geo 환경의 문서 ID가 지리적 위치 간에 고유하지 않으며 지리적 위치별로 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-152">If you're developing a search-driven application that depends on document IDs, note that document IDs in a multi-geo environment aren't unique across geo locations, they are unique per geo location.</span></span></td>
<td align="left"><span data-ttu-id="2f01f-153">위치 정보를 식별 할 수 있는 열을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-153">We've added a column that identifies the geo location.</span></span> <span data-ttu-id="2f01f-154">고유성을 얻으려면 이 열을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f01f-154">Use this column to achieve uniqueness.</span></span> <span data-ttu-id="2f01f-155">이 열의 이름은 "GeoLocationSource"입니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-155">This column is named "GeoLocationSource".</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2f01f-156">결과의 수</span><span class="sxs-lookup"><span data-stu-id="2f01f-156">Number of results</span></span></td>
<td align="left"><span data-ttu-id="2f01f-157">검색 결과 페이지에는 지리적 위치의 결합된 결과가 표시되지만 500개가 넘는 결과는 여러 페이지로 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-157">The search results page shows combined results from the geo locations, but it's not possible to page beyond 500 results.</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2f01f-158">Hybrid search</span><span class="sxs-lookup"><span data-stu-id="2f01f-158">Hybrid search</span></span></td>
<td align="left"><span data-ttu-id="2f01f-159"><a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">클라우드 하이브리드 검색</a>이 있는 하이브리드 SharePoint 환경에서는 온-프레미스 콘텐츠가 중앙 위치의 Microsoft 365 인덱스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-159">In a hybrid SharePoint environment with <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud hybrid search</a>,  on-premises content is added to the Microsoft 365 index of the central location.</span></span></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a><span data-ttu-id="2f01f-160">Multi-Geo 환경에서 지원되지 않는 검색은 어떤 것인가요?</span><span class="sxs-lookup"><span data-stu-id="2f01f-160">What's not supported for search in a multi-geo environment?</span></span>

<span data-ttu-id="2f01f-161">기존에 친숙하던 일부 검색 기능이 Multi-Geo 환경에서 지원되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-161">Some of the search features you might be familiar with, aren't supported in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f01f-162">검색 기능</span><span class="sxs-lookup"><span data-stu-id="2f01f-162">Search feature</span></span></th>
<th align="left"><span data-ttu-id="2f01f-163">참고</span><span class="sxs-lookup"><span data-stu-id="2f01f-163">Note</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2f01f-164">앱 전용 인증</span><span class="sxs-lookup"><span data-stu-id="2f01f-164">App-only authentication</span></span></td>
<td align="left"><span data-ttu-id="2f01f-165">앱 전용 인증(서비스의 권한 있는 액세스)은 Multi-Geo 검색에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-165">App-only authentication (privileged access from services) isn't supported in multi-geo search.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2f01f-166">게스트</span><span class="sxs-lookup"><span data-stu-id="2f01f-166">Guests</span></span></td>
<td align="left"><span data-ttu-id="2f01f-167">게스트는 검색하는 지리적 위치에서만 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-167">Guests only get results from the geo location that they're searching from.</span></span></td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a><span data-ttu-id="2f01f-168">Multi-Geo 환경에서 검색은 어떤 방식으로 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="2f01f-168">How does search work in a multi-geo environment?</span></span>

<span data-ttu-id="2f01f-169">모든 검색 클라이언트는 기존 SharePoint 검색 REST API를 사용하여 검색 인덱스와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-169">All the search clients use the existing SharePoint Search REST APIs to interact with the search indexes.</span></span>

![검색 REST SharePoint 인덱스와 상호 작용하는 방법을 보여 주는 다이어그램](../media/configure-search-for-multi-geo-image1-1.png)

1. <span data-ttu-id="2f01f-171">검색 클라이언트는 쿼리 속성 EnableMultiGeoSearch가 true인 검색 REST 끝점을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-171">A search client calls the Search REST endpoint with the query property EnableMultiGeoSearch= true.</span></span>
2. <span data-ttu-id="2f01f-172">쿼리는 테넌트의 모든 지리적 위치로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-172">The query is sent to all geo locations in the tenant.</span></span>
3. <span data-ttu-id="2f01f-173">각 지리적 위치의 검색 결과가 병합되고 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-173">Search results from each geo location are merged and ranked.</span></span>
4. <span data-ttu-id="2f01f-174">클라이언트는 통합된 검색 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-174">The client gets unified search results.</span></span>

<span data-ttu-id="2f01f-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Microsoft는 모든 지리적 위치에서 결과를 얻을 때까지 검색 결과를 병합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Notice that we don't merge the search results until we've received results from all the geo locations.</span></span> <span data-ttu-id="2f01f-176">즉, Multi-Geo 정보 검색은 지리적 위치가 하나뿐인 환경에서의 검색보다 대기 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-176">This means that multi-geo searches have additional latency compared to searches in an environment with only one geo location.</span></span>

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a><span data-ttu-id="2f01f-177">검색 센터에서 모든 지리적 위치의 결과를 표시하도록 지정</span><span class="sxs-lookup"><span data-stu-id="2f01f-177">Get a Search Center to show results from all geo locations</span></span>

<span data-ttu-id="2f01f-178">각 검색 센터에는 여러 범주가 있으며 각 범주를 개별적으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-178">Each Search Center has several verticals and you have to set up each vertical individually.</span></span>

1. <span data-ttu-id="2f01f-179">검색 결과 페이지 및 검색 결과 웹 파트를 편집할 수 있는 권한이 있는 계정으로 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-179">Ensure that you perform these steps with an account that has permission to edit the search results page and the Search Result Web Part.</span></span>

2. <span data-ttu-id="2f01f-180">검색 결과 페이지로 이동합니다(검색 결과 페이지의 [목록](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) 참조).</span><span class="sxs-lookup"><span data-stu-id="2f01f-180">Navigate to the search results page (see the [list](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) of search results pages)</span></span>

3. <span data-ttu-id="2f01f-p112">설정할 범주를 선택하고 오른쪽 위 모서리에 있는 **설정** 톱니바퀴 아이콘을 클릭한 후 **페이지 편집** 을 클릭합니다. 검색 결과 페이지가 편집 모드에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-p112">Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**. The search results page opens in Edit mode.</span></span>

   ![목록에서 페이지 선택 설정](../media/configure-search-for-multi-geo-image2.png)

4. <span data-ttu-id="2f01f-184">검색 결과 웹 파트에서 웹 파트 오른쪽 위 모서리로 포인터를 이동하고 화살표를 클릭한 후 메뉴에서 **웹 파트 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-184">In the Search Results Web Part, move the pointer to the upper, right corner of the web part, click the arrow, and then click **Edit Web Part** on the menu.</span></span> <span data-ttu-id="2f01f-185">검색 결과 웹 파트 도구 창은 페이지 오른쪽 위에 있는 리본 아래에 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-185">The Search Results Web Part tool pane opens under the ribbon in the top right of the page.</span></span>

   ![웹 파트 선택 편집](../media/configure-search-for-multi-geo-image3.png)

5. <span data-ttu-id="2f01f-187">웹 파트 도구 창의 **설정** 섹션에 있는 **결과 제어 설정** 에서 **Multi-Geo 결과 표시** 를 선택하여 검색 결과 웹 파트에 모든 지리적 위치의 결과를 표시하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-187">In the Web Part tool pane, in the **Settings** section, under **Results control settings**, select **Show Multi-Geo results** to get the Search Results Web Part to show results from all geo locations.</span></span>

6. <span data-ttu-id="2f01f-188">**확인** 을 클릭하여 변경 내용을 저장하고 웹 파트 도구 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-188">Click **OK** to save your change and close the Web Part tool pane.</span></span>

7. <span data-ttu-id="2f01f-189">주 메뉴의 페이지 탭에서 **체크 인** 을 클릭하여 검색 결과 웹 파트에 대한 변경 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-189">Check your changes to the Search Results Web Part by clicking **Check-In** on the Page tab of the main menu.</span></span>

8. <span data-ttu-id="2f01f-190">페이지 위쪽의 메모에 제공된 링크를 사용하여 변경 내용을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-190">Publish the changes by using the link provided in the note at the top of the page.</span></span>

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a><span data-ttu-id="2f01f-191">사용자 지정 검색 응용 프로그램에서 전체 또는 일부 지리적 위치의 결과를 표시하도록 지정</span><span class="sxs-lookup"><span data-stu-id="2f01f-191">Get custom search applications to show results from all or some geo locations</span></span>

<span data-ttu-id="2f01f-p114">사용자 지정 검색 응용 프로그램은 SharePoint 검색 REST API에 대한 요청을 통해 쿼리 매개 변수를 지정하여 전체 또는 일부 지리적 위치에서 결과를 가져옵니다. 쿼리 매개 변수에 따라, 쿼리는 모든 지리적 위치 또는 일부 지리적 위치로 팬아웃됩니다. 예를 들어, 관련 정보를 찾기 위해 지리적 위치의 하위 집합만 쿼리하면 될 경우 팬아웃을 이러한 위치로만 제어할 수 있습니다. 요청이 성공하면 SharePoint 검색 REST API가 응답 데이터를 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-p114">Custom search applications get results from all, or some, geo locations by specifying query parameters with the request to the SharePoint Search REST API. Depending on the query parameters, the query is fanned out to all geo locations, or to some geo locations. For example, if you only need to query a subset of geo locations to find relevant information, you can control the fan out to only these. If the request succeeds, the SharePoint Search REST API returns response data.</span></span>

### <a name="requirement"></a><span data-ttu-id="2f01f-196">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f01f-196">Requirement</span></span>

<span data-ttu-id="2f01f-p115">각 지역 위치의 경우 조직의 모든 사용자가 루트 웹 사이트(예: contoso **APAC**.sharepoint.com/ 및 contoso **EU**.sharepoint.com/) **읽기** 권한 수준을 받아야 합니다. [권한에 대해 자세히 알아보세요](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span><span class="sxs-lookup"><span data-stu-id="2f01f-p115">For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso **APAC**.sharepoint.com/ and contoso **EU**.sharepoint.com/). [Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span></span>

### <a name="query-parameters"></a><span data-ttu-id="2f01f-199">쿼리 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f01f-199">Query parameters</span></span>

<span data-ttu-id="2f01f-200">EnableMultiGeoSearch - 이 쿼리는 Multi-Geo 테넌트의 다른 지리적 위치의 인덱스로 쿼리를 팬아웃할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-200">EnableMultiGeoSearch - This is a Boolean value that specifies whether the query shall be fanned out to the indexes of other geo locations of the multi-geo tenant.</span></span> <span data-ttu-id="2f01f-201">**true** 로 설정하면 쿼리가 적용됩니다. **false** 로 설정하면 쿼리가 팬 아웃되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-201">Set it to **true** to fan out the query; **false** to not fan out the query.</span></span> <span data-ttu-id="2f01f-202">이 매개 변수를 포함하지 않는 경우 엔터프라이즈 검색 센터 서식 파일을 사용하는 사이트에 대한 REST API 호출을 수행할 때(이 경우 기본값은 **true**)를 제외하고 기본값은 **false** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-202">If you don't include this parameter, the default value is **false**, except when making a REST API call against a site which uses the Enterprise Search Center template, in this case the default value is **true**.</span></span> <span data-ttu-id="2f01f-203">Multi-Geo가 아닌 환경에서 매개 변수를 사용하면 매개 변수가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-203">If you use the parameter in an environment that isn't multi-geo, the parameter is ignored.</span></span>

<span data-ttu-id="2f01f-204">ClientType - 이것은 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-204">ClientType - This is a string.</span></span> <span data-ttu-id="2f01f-205">각 검색 응용 프로그램에 대해 고유한 클라이언트 이름을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f01f-205">Enter a unique client name for each search application.</span></span> <span data-ttu-id="2f01f-206">이 매개 변수를 포함하지 않으면 쿼리가 다른 지리적 위치로 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-206">If you don't include this parameter, the query is not fanned out to other geo locations.</span></span>

<span data-ttu-id="2f01f-207">MultiGeoSearchConfiguration -**EnableMultiGeoSearch** 가 **true** 일 때 쿼리를 내보내는 Multi-Geo 테넌트의 지리적 위치에 대한 선택적 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-207">MultiGeoSearchConfiguration - This is an optional list of which geo locations in the multi-geo tenant to fan the query out to when **EnableMultiGeoSearch** is **true**.</span></span> <span data-ttu-id="2f01f-208">이 매개 변수를 포함하지 않거나 공백으로 두면 모든 지리적 위치로 쿼리가 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-208">If you don't include this parameter, or leave it blank, the query is fanned out to all geo locations.</span></span> <span data-ttu-id="2f01f-209">각 지리적 위치에 대해 JSON 형식으로 다음 항목을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f01f-209">For each geo location, enter the following items, in JSON format:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f01f-210">항목</span><span class="sxs-lookup"><span data-stu-id="2f01f-210">Item</span></span></th>
<th align="left"><span data-ttu-id="2f01f-211">설명</span><span class="sxs-lookup"><span data-stu-id="2f01f-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2f01f-212">DataLocation</span><span class="sxs-lookup"><span data-stu-id="2f01f-212">DataLocation</span></span></td>
<td align="left"><span data-ttu-id="2f01f-213">지리적 위치(예: NAM)</span><span class="sxs-lookup"><span data-stu-id="2f01f-213">The geo location, for example NAM.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2f01f-214">EndPoint</span><span class="sxs-lookup"><span data-stu-id="2f01f-214">EndPoint</span></span></td>
<td align="left"><span data-ttu-id="2f01f-215">연결할 끝점(예: https://contoso.sharepoint.com)</span><span class="sxs-lookup"><span data-stu-id="2f01f-215">The endpoint to connect to, for example https://contoso.sharepoint.com</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2f01f-216">SourceId</span><span class="sxs-lookup"><span data-stu-id="2f01f-216">SourceId</span></span></td>
<td align="left"><span data-ttu-id="2f01f-217">결과 원본의 GUID(예: B81EAB55-3140-4312-B0F4-9459D1B4FFEE)</span><span class="sxs-lookup"><span data-stu-id="2f01f-217">The GUID of the result source, for example B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2f01f-p119">DataLocation 또는 EndPoint를 생략하거나 DataLocation이 중복되면 요청이 실패합니다. [Microsoft Graph를 사용하여 테넌트의 지리적 위치 끝점에 대한 정보를 얻을 수 있습니다](/sharepoint/dev/solution-guidance/multigeo-discovery).</span><span class="sxs-lookup"><span data-stu-id="2f01f-p119">If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails. [You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](/sharepoint/dev/solution-guidance/multigeo-discovery).</span></span>

### <a name="response-data"></a><span data-ttu-id="2f01f-220">응답 데이터</span><span class="sxs-lookup"><span data-stu-id="2f01f-220">Response data</span></span>

<span data-ttu-id="2f01f-p120">MultiGeoSearchStatus – SharePoint 검색 API가 요청에 대한 응답으로 반환하는 속성입니다. 속성의 값은 문자열이며 SharePoint 검색 API가 반환하는 결과에 대해 다음과 같은 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-p120">MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request. The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f01f-223">값</span><span class="sxs-lookup"><span data-stu-id="2f01f-223">Value</span></span></th>
<th align="left"><span data-ttu-id="2f01f-224">설명</span><span class="sxs-lookup"><span data-stu-id="2f01f-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2f01f-225">Full</span><span class="sxs-lookup"><span data-stu-id="2f01f-225">Full</span></span></td>
<td align="left"><span data-ttu-id="2f01f-226"><strong>모든</strong> 지리적 위치의 전체 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-226">Full results from <strong>all</strong> the geo locations.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2f01f-227">Partial</span><span class="sxs-lookup"><span data-stu-id="2f01f-227">Partial</span></span></td>
<td align="left"><span data-ttu-id="2f01f-p121">하나 이상의 지리적 위치에서 가져온 부분적인 결과입니다. 일시적인 오류로 인해 결과가 불완전합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-p121">Partial results from one or more geo locations. The results are incomplete due to a transient error.</span></span></td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a><span data-ttu-id="2f01f-230">REST 서비스를 사용하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="2f01f-230">Query using the REST service</span></span>

<span data-ttu-id="2f01f-p122">GET 요청을 사용하여 URL에 쿼리 매개 변수를 지정합니다. POST 요청을 사용하여 본문에 JSON(JavaScript 개체 표기법) 형식으로 쿼리 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-p122">With a GET request, you specify the query parameters in the URL. With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.</span></span>

#### <a name="request-headers"></a><span data-ttu-id="2f01f-233">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="2f01f-233">Request headers</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f01f-234">이름</span><span class="sxs-lookup"><span data-stu-id="2f01f-234">Name</span></span></th>
<th align="left"><span data-ttu-id="2f01f-235">값</span><span class="sxs-lookup"><span data-stu-id="2f01f-235">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2f01f-236">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2f01f-236">Content-Type</span></span></td>
<td align="left"><span data-ttu-id="2f01f-237">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="2f01f-237">application/json;odata=verbose</span></span></td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="2f01f-238">**모든** 지리적 위치로 팬아웃되는 샘플 GET 요청</span><span class="sxs-lookup"><span data-stu-id="2f01f-238">Sample GET request that's fanned out to **all** geo locations</span></span>

```http
https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'
```

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a><span data-ttu-id="2f01f-239">**일부** 지리적 위치로 팬아웃할 샘플 GET 요청</span><span class="sxs-lookup"><span data-stu-id="2f01f-239">Sample GET request to fan out to **some** geo locations</span></span>

```http
https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'
```

> [!NOTE]
> <span data-ttu-id="2f01f-240">MultiGeoSearchConfiguration 속성의 지리적 위치 목록에 있는 쉼표와 콜론 앞에는 **백슬래시** 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-240">Commas and colons in the list of geo locations for the MultiGeoSearchConfiguration property are preceded by the **backslash** character.</span></span> <span data-ttu-id="2f01f-241">이는 GET 요청이 콜론을 사용하여 속성과 쉼표를 구분하여 속성 인수를 구분하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-241">This is because GET requests use colons to separate properties and commas to separate arguments of properties.</span></span> <span data-ttu-id="2f01f-242">이스케이프 문자로 백슬래시가 없으면 MultiGeoSearchConfiguration 속성이 잘못 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-242">Without the backslash as an escape character, the MultiGeoSearchConfiguration property is interpreted wrongly.</span></span>

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="2f01f-243">**모든** 지리적 위치로 팬아웃되는 샘플 POST 요청</span><span class="sxs-lookup"><span data-stu-id="2f01f-243">Sample POST request that's fanned out to **all** geo locations</span></span>

```http
    {
    "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }
```

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a><span data-ttu-id="2f01f-244">**일부** 지리적 위치로 팬아웃되는 샘플 POST 요청</span><span class="sxs-lookup"><span data-stu-id="2f01f-244">Sample POST request that's fanned out to **some** geo locations</span></span>

```http
    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }
```

### <a name="query-using-csom"></a><span data-ttu-id="2f01f-245">CSOM을 사용하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="2f01f-245">Query using CSOM</span></span>

<span data-ttu-id="2f01f-246">다음은 **모든** 지리적 위치로 팬아웃되는 샘플 CSOM 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="2f01f-246">Here's a sample CSOM query that's fanned out to **all** geo locations:</span></span>

```CSOM
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery.Properties["EnableMultiGeoSearch"] = true;
```
