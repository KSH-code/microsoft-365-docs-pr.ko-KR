---
title: eDiscovery 검색 결과에 대한 통계 보기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 검색 통계 기능을 사용하여 검색 준수 센터에서 Core eDiscovery 사례와 연결된 콘텐츠 검색 및 검색에 대한 통계를 표시하는 Microsoft 365 대해 알아보겠습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311116"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="a3533-103">eDiscovery 검색 결과에 대한 통계 보기</span><span class="sxs-lookup"><span data-stu-id="a3533-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="a3533-104">콘텐츠 검색 또는 Core eDiscovery 사례와 연결된 검색을 만들고 실행한 후 예상 검색 결과에 대한 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="a3533-105">여기에는 검색 결과 요약(검색 플라이아웃 페이지에 표시되는 예상 검색 결과 요약), 검색 쿼리와 일치하는 항목이 포함된 콘텐츠 위치 수와 같은 쿼리 통계, 가장 일치하는 항목이 있는 콘텐츠 위치의 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="a3533-106">또한 키워드 목록을 사용하여 검색 쿼리의 각 키워드에 대한 통계를 반환하도록 검색을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="a3533-107">이렇게 하면 쿼리의 각 키워드에서 반환되는 결과 수를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="a3533-108">검색 통계를 CSV 파일에 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="a3533-109">이를 통해 Excel의 필터링 및 정렬 기능을 사용하여 결과를 비교하고 검색 결과에 대한 보고서를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="a3533-110">검색에 대한 통계를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-110">Get statistics for searches</span></span>

<span data-ttu-id="a3533-111">Core eDiscovery 사례와 연결된 콘텐츠 검색 또는 검색에 대한 통계를 표시하기 위해:</span><span class="sxs-lookup"><span data-stu-id="a3533-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="a3533-112">Microsoft 365 준수 센터에서 모두 표시를 클릭하고 다음 중 하나를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="a3533-113">콘텐츠 **검색을** 클릭한 다음 검색을 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="a3533-114">또는</span><span class="sxs-lookup"><span data-stu-id="a3533-114">OR</span></span>

   - <span data-ttu-id="a3533-115">**eDiscovery**  >  **Core를 클릭하고** 사례를 선택한 다음  검색 탭에서 검색을 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="a3533-116">선택한 검색의 플라이아웃 페이지에서 검색 통계 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![검색 통계 탭](../media/SearchStatistics1.png)

<span data-ttu-id="a3533-118">검색 **통계 탭에는** 검색에 대한 다양한 유형의 통계가 포함된 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="a3533-119">콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="a3533-119">Search content</span></span>

<span data-ttu-id="a3533-120">이 섹션에는 검색에서 반환된 예상 항목에 대한 그래픽 요약이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="a3533-121">검색 조건과 일치하는 항목 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="a3533-122">이 정보는 검색에서 반환되는 예상 항목 수에 대한 아이디어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![검색 예상 검색](../media/SearchContentReport.png)

- <span data-ttu-id="a3533-124">**위치 기준 예상 항목:** 검색에서 반환된 예상 항목의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="a3533-125">사서함에 있으며 사이트에 있는 특정 항목 수도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="a3533-126">**적중 횟수가 있는** 예상 위치: 검색에서 반환된 항목이 포함된 총 콘텐츠 위치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="a3533-127">사서함 및 사이트 위치의 특정 수도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="a3533-128">**위치당 데이터 볼륨(MB)**: 검색에서 반환된 모든 예상 항목의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="a3533-129">사서함 항목 및 사이트 항목의 특정 크기도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="a3533-130">조건 보고서</span><span class="sxs-lookup"><span data-stu-id="a3533-130">Condition report</span></span>

<span data-ttu-id="a3533-131">이 섹션에는 검색 쿼리에 대한 통계와 검색 쿼리의 여러 부분과 일치하는 예상 항목 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="a3533-132">이러한 통계를 사용하여 검색 쿼리의 각 구성 요소와 일치하는 항목 수를 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="a3533-133">이렇게하면 검색 조건을 구체화하고 필요한 경우 범위 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="a3533-134">이 보고서의 복사본을 CSV 형식으로 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-134">You can also download a copy of this report in CSV format.</span></span>

![조건 보고서](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="a3533-136">**위치 유형:** 쿼리 통계를 적용할 수 있는 콘텐츠 위치의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="a3533-137">Exchange **값은** 사서함 위치를 나타냅니다. 값이 **SharePoint** 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="a3533-138">**파트:** 검색 쿼리에서 통계를 적용할 수 있는 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="a3533-139">**Primary는** 전체 검색 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="a3533-140">**Keyword는** 행의 통계가 특정 키워드에 대한 통계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="a3533-141">검색 쿼리에 키워드 목록을 사용하는 경우 쿼리의 각 구성 요소에 대한 통계가 이 표에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="a3533-142">자세한 내용은 [검색에 대한 키워드 통계 보기를 참조하세요.](#get-keyword-statistics-for-searches)</span><span class="sxs-lookup"><span data-stu-id="a3533-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="a3533-143">**조건:** 해당 행에 표시된 통계를 반환한 검색 쿼리의 실제 구성 요소(키워드 또는 조건)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="a3533-144">**적중 횟수가** 있는 위치: 조건 열에  나열된 기본 쿼리 또는 키워드 쿼리와 일치하는 항목이 포함된 콘텐츠 위치(위치 유형 열로 지정)의 **수입니다.**</span><span class="sxs-lookup"><span data-stu-id="a3533-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="a3533-145">**항목:** 조건 열에 나열된 쿼리와 일치하는 항목 수(지정된 콘텐츠 위치의 항목 수)입니다. </span><span class="sxs-lookup"><span data-stu-id="a3533-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="a3533-146">앞서 설명한 것 처럼 항목에 검색되는 키워드의 인스턴스가 여러 개 포함된 경우 이 열에는 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="a3533-147">**크기(MB)**: 조건 열의 검색 쿼리와 일치하는 지정된 콘텐츠 위치에 있는 모든 항목의 총 **크기입니다.**</span><span class="sxs-lookup"><span data-stu-id="a3533-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="a3533-148">상위 위치</span><span class="sxs-lookup"><span data-stu-id="a3533-148">Top locations</span></span>

<span data-ttu-id="a3533-149">이 섹션에는 검색에서 반환된 항목이 가장 많은 특정 콘텐츠 위치에 대한 통계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="a3533-150">주요 위치 1,000개가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="a3533-151">이 보고서의 복사본을 CSV 형식으로 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="a3533-152">위치 이름(사서함의 전자 메일 주소 및 사이트의 URL)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="a3533-153">위치 유형(사서함 또는 사이트)</span><span class="sxs-lookup"><span data-stu-id="a3533-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="a3533-154">검색에서 반환된 콘텐츠 위치에 있는 예상 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="a3533-155">각 콘텐츠 위치에 있는 예상 항목의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="a3533-156">검색에 대한 키워드 통계를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="a3533-157">앞서 설명한 것  처럼 조건 보고서 섹션에는 검색 쿼리와 쿼리와 일치하는 항목의 수 및 크기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="a3533-158">검색 쿼리를 만들거나 편집할 때 키워드 목록을 사용하는 경우 각 키워드 또는 키워드 구와 일치하는 항목 수를 표시하는 향상된 통계를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="a3533-159">이렇게하면 가장 효과적이고 가장 효과적인 쿼리 부분을 빠르게 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="a3533-160">예를 들어 키워드가 많은 수의 항목을 반환하는 경우 키워드 쿼리를 구체화하여 검색 결과 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="a3533-161">키워드 목록을 만들고 검색에 대한 키워드 통계를 표시하는 경우:</span><span class="sxs-lookup"><span data-stu-id="a3533-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="a3533-162">규정 Microsoft 365 센터에서 Core eDiscovery 사례와 연결된 새 콘텐츠 검색 또는 검색을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="a3533-163">검색 **마법사의** 조건 페이지에서</span><span class="sxs-lookup"><span data-stu-id="a3533-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="a3533-164">키워드 목록 **표시 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-164">select the **Show keyword list** checkbox.</span></span>

   ![키워드 목록 표시 확인란](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="a3533-166">키워드 테이블의 행에 키워드 또는 키워드 단계를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="a3533-167">예를 들어 첫 번째 행에 **budget을** 입력하고 두 번째 행에 **보안을** 입력한 다음 세 번째 행에 **FY2021을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![목록에 최대 20개 키워드 또는 키워드 구를 입력합니다.](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="a3533-169">큰 키워드 목록으로 인한 문제를 줄이기 위해 검색 쿼리의 키워드 목록에서 최대 20개 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="a3533-170">검색하고 통계를 얻을 키워드를 목록에 추가한 후 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="a3533-171">검색이 완료되면 해당 검색을 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="a3533-172">검색 **통계 탭에서** 조건  보고서를 클릭하여 검색에 대한 키워드 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![각 키워드에 대한 통계가 표시됩니다.](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="a3533-174">이전 스크린샷과 같이 각 키워드에 대한 통계가 표시됩니다. 여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="a3533-175">검색에 포함된 각 콘텐츠 위치 유형에 대한 키워드 통계입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="a3533-176">인덱서되지 않은 사서함 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="a3533-177">검색 쿼리의 조건이 포함된 각 키워드(파트  열에서 **키워드로** 식별)에 대한 실제 검색 쿼리 및 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="a3533-178">전체 검색 쿼리(파트  열에서  기본으로 식별) 및 각 위치 유형에 대한 전체 쿼리에 대한 통계입니다.</span><span class="sxs-lookup"><span data-stu-id="a3533-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="a3533-179">요약 탭에 표시되는 통계와 **동일한 통계입니다.**</span><span class="sxs-lookup"><span data-stu-id="a3533-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
