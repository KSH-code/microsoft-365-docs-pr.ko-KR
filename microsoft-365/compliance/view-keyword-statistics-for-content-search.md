---
title: 콘텐츠 검색 결과에 대한 키워드 통계 보기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: 검색 통계 기능을 사용하여 보안 및 준수 센터에서 여러 콘텐츠 검색에 대한 통계를 표시하고 & 방법을 알아보겠습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7faf956aaec5619655818036b969086e0af0c6a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49987836"
---
# <a name="view-keyword-statistics-for-content-search-results"></a><span data-ttu-id="ffa53-103">콘텐츠 검색 결과에 대한 키워드 통계 보기</span><span class="sxs-lookup"><span data-stu-id="ffa53-103">View keyword statistics for Content Search results</span></span>

<span data-ttu-id="ffa53-104">콘텐츠 검색을 만들고 실행한 후 예상 검색 결과에 대한 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-104">After you create and run a Content Search, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="ffa53-105">여기에는 검색 결과 요약(세부 정보 창에 표시되는 예상 검색 결과 요약), 검색 쿼리와 일치하는 항목이 있는 콘텐츠 위치 수 등의 쿼리 통계, 일치하는 항목이 가장 일치하는 콘텐츠 위치의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed in the details pane), the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items.</span></span> <span data-ttu-id="ffa53-106">하나 이상의 콘텐츠 검색에 대한 통계를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-106">You can display statistics for one or more content searches.</span></span> <span data-ttu-id="ffa53-107">이렇게 하면 여러 검색에 대한 결과를 빠르게 비교하고 검색 쿼리의 효율성에 대한 의사 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-107">This lets you to quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="ffa53-108">또한 검색 쿼리에서 각 키워드에 대한 통계를 반환하도록 새 검색과 기존 검색을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-108">Additionally, you can configure new and existing searches to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="ffa53-109">이렇게 하면 쿼리의 각 키워드에 대한 결과 수를 비교하고 여러 검색의 키워드 통계를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-109">This lets you compare the number of results for each keyword in a query and to compare the keyword statistics from multiple searches.</span></span>
  
<span data-ttu-id="ffa53-110">또한 검색 통계 및 키워드 통계를 CSV 파일로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-110">You can also download the search statistics and keyword statistics to a CSV file.</span></span> <span data-ttu-id="ffa53-111">이를 통해 Excel의 필터링 및 정렬 기능을 사용하여 결과를 비교하고 검색 결과에 대한 보고서를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-111">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-content-searches"></a><span data-ttu-id="ffa53-112">콘텐츠 검색에 대한 통계를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-112">Get statistics for Content Searches</span></span>

<span data-ttu-id="ffa53-113">콘텐츠 검색에 대한 통계를 표시하는 경우:</span><span class="sxs-lookup"><span data-stu-id="ffa53-113">To display statistics for Content searches:</span></span>
  
1. <span data-ttu-id="ffa53-114">Microsoft 365 규정 준수 센터에서 모든 콘텐츠 검색   >  **표시로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="ffa53-114">In the Microsoft 365 compliance center, go to **Show all** > **Content search**.</span></span>

2. <span data-ttu-id="ffa53-115">검색 목록에서 두 개 이상의 검색을 선택한 다음  대량 작업  플라이아웃 페이지에서 검색 통계를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-115">In the list of searches, select two or more searches, and then click **Search statistics** on the **Bulk actions** flyout page.</span></span>
    
    ![여러 검색을 선택한 다음 검색 통계를 클릭합니다.](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. <span data-ttu-id="ffa53-117">검색 **통계 페이지에서** 다음 링크 중 하나를 클릭하여 선택한 검색에 대한 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-117">On the **Search statistics** page, click one of the following links to display statistics about the selected searches.</span></span> 
    
    <span data-ttu-id="ffa53-118">**요약**</span><span class="sxs-lookup"><span data-stu-id="ffa53-118">**Summary**</span></span>
    
    <span data-ttu-id="ffa53-119">이 페이지에는 콘텐츠 검색 페이지의 세부 정보 창에 표시되는 통계와 유사한 **통계가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-119">This page displays statistics similar to the ones displayed in the details pane on the **Content search** page.</span></span> <span data-ttu-id="ffa53-120">선택한 모든 검색에 대한 통계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-120">Statistics for all selected searches are displayed.</span></span> <span data-ttu-id="ffa53-121">이 페이지에서 선택한 검색을 다시 실행하여 통계를 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-121">Note that you can also re-run the selected searches from this page to update the statistics.</span></span> 
    
    ![선택한 검색에 대한 통계 요약](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    <span data-ttu-id="ffa53-123">a.</span><span class="sxs-lookup"><span data-stu-id="ffa53-123">a.</span></span>  <span data-ttu-id="ffa53-124">콘텐츠 검색의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-124">The name of the Content Search.</span></span> <span data-ttu-id="ffa53-125">앞서 설명한 것 처럼 여러 검색에 대한 통계를 표시하고 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-125">As previously stated, you can display and compare statistics for multiple searches.</span></span>
    
    <span data-ttu-id="ffa53-126">b.</span><span class="sxs-lookup"><span data-stu-id="ffa53-126">b.</span></span> <span data-ttu-id="ffa53-127">검색된 콘텐츠 위치의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-127">The type of content location that was searched.</span></span> <span data-ttu-id="ffa53-128">각 행에는 지정된 검색의 사서함, 사이트 및 공용 폴더에 대한 통계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-128">Each row displays statistics for mailboxes, sites, and public folders from the specified search.</span></span>
    
    <span data-ttu-id="ffa53-129">c.</span><span class="sxs-lookup"><span data-stu-id="ffa53-129">c.</span></span> <span data-ttu-id="ffa53-130">검색 쿼리와 일치하는 항목이 포함된 콘텐츠 위치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-130">The number of content locations containing items that match the search query.</span></span> <span data-ttu-id="ffa53-131">사서함의 경우 이 통계에는 검색 쿼리와 일치하는 항목이 포함된 보관 사서함의 수도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-131">For mailboxes, this statistic also includes the number of archive mailboxes that contain items that match the search query.</span></span>
    
    <span data-ttu-id="ffa53-132">d.</span><span class="sxs-lookup"><span data-stu-id="ffa53-132">d.</span></span> <span data-ttu-id="ffa53-133">검색 쿼리와 일치하는 지정된 모든 콘텐츠 위치의 총 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-133">The total number of items of all specified content locations that match the search query.</span></span> <span data-ttu-id="ffa53-134">항목 유형의 예로는 전자 메일 메시지, 일정 항목 및 문서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-134">Examples of item types include email messages, calendar items, and documents.</span></span> <span data-ttu-id="ffa53-135">항목에 검색되는 키워드 인스턴스가 여러 개 포함된 경우 총 항목 수에서 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-135">If an item contains multiple instances of a keyword that is being searched for, it's only counted once in the total number of items.</span></span> <span data-ttu-id="ffa53-136">예를 들어 단어 "stock" 또는 "fraud"를 검색하고 전자 메일 메시지에 단어 "stock"의 세 인스턴스가 포함된 경우 항목 열에서 한 번만 **계산됩니다.**</span><span class="sxs-lookup"><span data-stu-id="ffa53-136">For example, if you're searching for words "stock" or "fraud" and an email message contains three instances of the word "stock", it's only counted once in the **Items** column.</span></span> 
    
    <span data-ttu-id="ffa53-137">e.</span><span class="sxs-lookup"><span data-stu-id="ffa53-137">e.</span></span> <span data-ttu-id="ffa53-138">검색 쿼리와 일치하는 지정된 콘텐츠 위치에 있는 모든 항목의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-138">The total size of all items that were found in the specified content location that match the search query.</span></span> 
    
    <span data-ttu-id="ffa53-139">**쿼리**</span><span class="sxs-lookup"><span data-stu-id="ffa53-139">**Queries**</span></span>
    
    <span data-ttu-id="ffa53-140">이 페이지에는 검색 쿼리에 대한 통계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-140">This page displays statistics about the search query.</span></span>
    
    ![선택한 검색에 대한 검색 쿼리 통계](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    <span data-ttu-id="ffa53-142">a.</span><span class="sxs-lookup"><span data-stu-id="ffa53-142">a.</span></span> <span data-ttu-id="ffa53-143">행에 쿼리 통계가 포함된 콘텐츠 검색의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-143">The name of the Content Search that the row contains query statistics for.</span></span>
    
    <span data-ttu-id="ffa53-144">b.</span><span class="sxs-lookup"><span data-stu-id="ffa53-144">b.</span></span> <span data-ttu-id="ffa53-145">쿼리 통계를 적용할 수 있는 콘텐츠 위치의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-145">The type of content location that the query statistics are applicable to.</span></span>
    
    <span data-ttu-id="ffa53-146">c.</span><span class="sxs-lookup"><span data-stu-id="ffa53-146">c.</span></span> <span data-ttu-id="ffa53-147">이 열은 통계를 적용할 수 있는 검색 쿼리 부분을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-147">This column indicates which part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="ffa53-148">**기본은** 전체 검색 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-148">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="ffa53-149">검색 쿼리를 만들거나 편집할 때 키워드 목록을 사용하는 경우 쿼리의 각 구성 요소에 대한 통계가 이 표에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-149">If you use a keyword list when you create or edit a search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="ffa53-150">자세한 내용은 이 [문서의](#get-keyword-statistics-for-content-searches) 콘텐츠 검색에 대한 키워드 통계 보기 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffa53-150">See the [Get keyword statistics for Content Searches](#get-keyword-statistics-for-content-searches) section in this article for more information.</span></span> 
    
    <span data-ttu-id="ffa53-151">d.</span><span class="sxs-lookup"><span data-stu-id="ffa53-151">d.</span></span> <span data-ttu-id="ffa53-152">이 열에는 콘텐츠 검색 도구에서 실행되는 실제 검색 쿼리가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-152">This column contains the actual search query that run by the Content Search tool.</span></span> <span data-ttu-id="ffa53-153">이 도구는 만드는 쿼리에 몇 가지 구성 요소를 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-153">Note that the tool automatically adds a few additional components to the query that you create.</span></span> 

    - <span data-ttu-id="ffa53-154">키워드를 지정하지 않으면서 사서함의 모든 콘텐츠를 검색할 때 모든 항목이 반환될 수 있도록 실제 키 단어  `size>=0` 쿼리가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-154">When you search for all content in mailboxes (by not specifying any keywords), the actual key word query is  `size>=0` so that all items are returned.</span></span> 
    
     - <span data-ttu-id="ffa53-155">SharePoint Online 및 비즈니스용 OneDrive 사이트를 검색하면 다음 두 구성 요소가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-155">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
          <span data-ttu-id="ffa53-156">**NOT IsExternalContent:1** - On-premises SharePoint 조직에서 콘텐츠를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-156">**NOT IsExternalContent:1** - Excludes any content from an on-premises SharePoint organization.</span></span> 
    
          <span data-ttu-id="ffa53-157">**NOT IsOneNotePage:1** - 검색 쿼리와 일치하는 모든 문서의 복제본이기 때문에 모든 OneNote 파일을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-157">**NOT IsOneNotePage:1** - Excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span> 

    
    <span data-ttu-id="ffa53-158">e.</span><span class="sxs-lookup"><span data-stu-id="ffa53-158">e.</span></span> <span data-ttu-id="ffa53-159">쿼리 열에 나열된 검색 쿼리와 일치하는 항목이 포함된 콘텐츠 위치의 번호(\*\* 위치 유형 \*\* 열로 **지정)입니다.**</span><span class="sxs-lookup"><span data-stu-id="ffa53-159">The number of the content locations (specified by the \*\* Location type \*\* column) that contain items that match the search query listed in the **Query** column.</span></span> 
    
    <span data-ttu-id="ffa53-160">f.</span><span class="sxs-lookup"><span data-stu-id="ffa53-160">f.</span></span> <span data-ttu-id="ffa53-161">쿼리 열에 나열된 검색 쿼리와 일치하는 지정된 콘텐츠 위치의 항목 **수입니다.**</span><span class="sxs-lookup"><span data-stu-id="ffa53-161">The number of items (from the specified content location) that match the search query listed in the **Query** column.</span></span> <span data-ttu-id="ffa53-162">앞서 설명한 것 처럼 항목에 검색되는 키워드의 인스턴스가 여러 개 포함된 경우 이 열에서는 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-162">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in the this column.</span></span> 
    
    <span data-ttu-id="ffa53-163">g.</span><span class="sxs-lookup"><span data-stu-id="ffa53-163">g.</span></span> <span data-ttu-id="ffa53-164">지정된 콘텐츠 위치에 있는 쿼리 열의 검색 쿼리와 일치하는 모든 항목의 총 **크기입니다.**</span><span class="sxs-lookup"><span data-stu-id="ffa53-164">The total size of all items that were found (in the specified content location) that match the search query in the **Query** column.</span></span> 
    
    <span data-ttu-id="ffa53-165">**상위 위치**</span><span class="sxs-lookup"><span data-stu-id="ffa53-165">**Top locations**</span></span>
    
    <span data-ttu-id="ffa53-166">이 페이지에는 검색된 각 콘텐츠 위치의 검색 쿼리와 일치하는 항목 수에 대한 통계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-166">This page displays statistics about the number of items that match the search query in each content location that was searched.</span></span> <span data-ttu-id="ffa53-167">주요 위치 1,000개가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-167">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="ffa53-168">여러 검색에 대한 통계를 보는 경우 각 검색에 대한 상위 1,000개 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-168">If you view statistics for multiple searches, the top 1,000 locations for each search are displayed.</span></span> <span data-ttu-id="ffa53-169">콘텐츠 위치는 검색 쿼리와 일치하는 항목이 없는 경우 이 페이지에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-169">Note that a content location isn't included on this page if it doesn't contain any items that match the search query.</span></span>
    
    ![검색된 콘텐츠 위치에 있는 항목 수에 대한 통계](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    <span data-ttu-id="ffa53-171">a.</span><span class="sxs-lookup"><span data-stu-id="ffa53-171">a.</span></span> <span data-ttu-id="ffa53-172">콘텐츠 위치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-172">The name of the content location.</span></span>
    
    <span data-ttu-id="ffa53-173">b.</span><span class="sxs-lookup"><span data-stu-id="ffa53-173">b.</span></span> <span data-ttu-id="ffa53-174">위치 통계를 적용할 수 있는 콘텐츠 위치의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-174">The type of content location that the location statistics are applicable to.</span></span>
    
    <span data-ttu-id="ffa53-175">c.</span><span class="sxs-lookup"><span data-stu-id="ffa53-175">c.</span></span> <span data-ttu-id="ffa53-176">통계를 표시하는 각 검색에 대한 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-176">There are columns for each search that you're displaying statistics for.</span></span> <span data-ttu-id="ffa53-177">이 열에는 각 콘텐츠 위치의 검색 쿼리와 일치하는 항목의 수 및 총 크기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-177">This column shows the number (and total size) of items that match the search query in each content location.</span></span> <span data-ttu-id="ffa53-178">여러 검색에 대한 통계를 표시하는 경우 이 열의 "NA"는 콘텐츠 위치가 해당 검색에 포함되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-178">Note that when you're displaying statistics for multiple searches, the "NA" in this column indicates that the content location wasn't included in that search.</span></span> 

## <a name="get-keyword-statistics-for-content-searches"></a><span data-ttu-id="ffa53-179">콘텐츠 검색에 대한 키워드 통계를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-179">Get keyword statistics for Content Searches</span></span>

<span data-ttu-id="ffa53-180">앞서 설명한 것 **처럼** 쿼리 페이지에는 검색 쿼리와 쿼리와 일치하는 항목의 수 및 크기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-180">As previous explained, the **Queries** page shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="ffa53-181">검색 쿼리를 만들거나 편집할 때 키워드 목록을 사용하는 경우 각 키워드 또는 키워드 구와 일치하는 항목 수를 표시하는 향상된 통계를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-181">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="ffa53-182">이렇게하면 쿼리의 어느 부분이 가장 효과적이고 가장 효과적인지 빠르게 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-182">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="ffa53-183">예를 들어 키워드가 많은 수의 항목을 반환하는 경우 키워드 쿼리를 구체화하여 검색 결과 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-183">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span> <span data-ttu-id="ffa53-184">콘텐츠 검색을 만들거나 편집할 때 키워드 목록을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-184">You can set up a keyword list when you create or edit a Content Search.</span></span> 

<span data-ttu-id="ffa53-185">콘텐츠 검색에 대한 키워드 목록을 만들고 키워드 통계를 표시하는 경우:</span><span class="sxs-lookup"><span data-stu-id="ffa53-185">To create a keyword list and view keyword statistics for a Content Search:</span></span>
  
1. <span data-ttu-id="ffa53-186">Microsoft 365 규정 준수 센터에서 모든 콘텐츠 검색   >  **표시로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="ffa53-186">In the Microsoft 365 compliance center, go to **Show all** > **Content search**.</span></span>
    
2. <span data-ttu-id="ffa53-187">콘텐츠 검색 목록에서 검색을 클릭한 다음 편집  ![ 아이콘을 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-187">In the list of content searches, click and a search, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="ffa53-188">**쿼리를** 클릭한 다음 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-188">Click **Query** and then do the following things:</span></span> 
    
    ![키워드 목록 표시 확인란을 클릭하고 각 행에 키워드를 입력합니다.](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    <span data-ttu-id="ffa53-190">a.</span><span class="sxs-lookup"><span data-stu-id="ffa53-190">a.</span></span> <span data-ttu-id="ffa53-191">키워드 목록 **표시 확인란을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-191">Click the **Show keyword list** check box.</span></span> 
    
    <span data-ttu-id="ffa53-192">b.</span><span class="sxs-lookup"><span data-stu-id="ffa53-192">b.</span></span> <span data-ttu-id="ffa53-193">키워드 테이블의 행에 키워드 또는 키워드 단계를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-193">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="ffa53-194">예를 들어 첫 번째 행에 **예산을** 입력한 다음 두 번째 행에 보안을 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="ffa53-194">For example, type **budget** in the first row and then type **security** in the second row.</span></span> 
    
4. <span data-ttu-id="ffa53-195">검색하고 통계를 얻을 키워드를 추가한 후 **검색을** 클릭하여 수정된 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-195">After adding the keywords that you want to search and get statistics for, click **Search** to run the revised search.</span></span> 
    
5. <span data-ttu-id="ffa53-196">검색이 완료되면 검색 목록에서 검색을 선택하고 검색 통계  검색 통계 ![ 단추를 ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-196">When the search is completed, select it in the list of searches, and then click **Search statistics** ![Search Statistics button](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png).</span></span> <span data-ttu-id="ffa53-197">여러 검색에 대한 키워드 통계를 표시하고 비교할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-197">You can also display and compare keyword statistics for multiple searches.</span></span>
    
6. <span data-ttu-id="ffa53-198">검색 **통계 페이지에서** **쿼리를** 클릭하여 선택한 검색에 대한 키워드 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-198">On the **Search statistics** page, click **Query** to display the keyword statistics for the selected searches.</span></span> 
    
    ![선택한 검색의 각 키워드에 대한 통계가 표시됩니다.](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    <span data-ttu-id="ffa53-200">이전 스크린샷과 같이 각 키워드에 대한 통계가 표시됩니다. 여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-200">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span> 
    
    - <span data-ttu-id="ffa53-201">검색에 포함된 각 콘텐츠 위치 유형에 대한 키워드 통계입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-201">The keyword statistics for each type of content location included in the search.</span></span>
    
    - <span data-ttu-id="ffa53-202">검색 쿼리의 조건을 포함하는 각 키워드에 대한 실제 검색 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-202">The actual search query for each keyword, which includes any conditions from the search query.</span></span> 
    
    - <span data-ttu-id="ffa53-203">전체 검색 쿼리(파트 열에서  **기본** 쿼리로 식별)와 전체 쿼리에 대한 통계입니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-203">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query.</span></span> <span data-ttu-id="ffa53-204">요약 페이지에 표시되는 통계와 **동일합니다.**</span><span class="sxs-lookup"><span data-stu-id="ffa53-204">Note these are the same statistics displayed on the **Summary** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="ffa53-205">큰 키워드 목록으로 인한 문제를 줄이기 위해 이제 검색 쿼리의 키워드 목록에서 최대 20개 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffa53-205">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>
