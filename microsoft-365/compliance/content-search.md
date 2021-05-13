---
title: Microsoft 365 규정 준수 센터에서 콘텐츠 검색 만들기 및 실행
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 규정 준수 센터의 콘텐츠 검색 eDiscovery 도구를 사용하여 다양한 Microsoft 365 서비스의 콘텐츠를 검색합니다.
ms.openlocfilehash: 5f48418882d5d4c7589b3ef394a0a306c0675f34
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332849"
---
# <a name="create-a-content-search"></a><span data-ttu-id="b8255-103">콘텐츠 검색 만들기</span><span class="sxs-lookup"><span data-stu-id="b8255-103">Create a content search</span></span>

<span data-ttu-id="b8255-104">Microsoft 365 규정 준수 센터의 콘텐츠 검색 eDiscovery 도구를 사용하여 조직에서 전자 메일, 문서, 인스턴트 메시징 대화와 같은 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-104">You can use the Content search eDiscovery tool in the Microsoft 365 compliance center to search for in-place content such as email, documents, and instant messaging conversations in your organization.</span></span> <span data-ttu-id="b8255-105">다음 Microsoft 365 데이터 원본에서 콘텐츠를 검색하려면 이 도구를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-105">Use this tool to search for content in these Microsoft 365 data sources:</span></span>
  
- <span data-ttu-id="b8255-106">Exchange Online 사서함</span><span class="sxs-lookup"><span data-stu-id="b8255-106">Exchange Online mailboxes</span></span>

- <span data-ttu-id="b8255-107">SharePoint Online 사이트 및 비즈니스용 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="b8255-107">SharePoint Online sites and OneDrive for Business accounts</span></span>

- <span data-ttu-id="b8255-108">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8255-108">Microsoft Teams</span></span>

- <span data-ttu-id="b8255-109">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="b8255-109">Microsoft 365 Groups</span></span>

- <span data-ttu-id="b8255-110">Yammer 그룹</span><span class="sxs-lookup"><span data-stu-id="b8255-110">Yammer Groups</span></span>

<span data-ttu-id="b8255-111">검색을 실행하면 콘텐츠 위치 수와 예상 검색 결과 수가 검색 플라이아웃 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-111">After you run a search, the number of content locations and an estimated number of search results are displayed on the search flyout page.</span></span> <span data-ttu-id="b8255-112">검색 쿼리와 일치하는 항목이 가장 많은 콘텐츠 위치와 같은 통계를 빠르게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-112">You can quickly view statistics, such as the content locations that have the most items that match the search query.</span></span> <span data-ttu-id="b8255-113">검색을 실행한 후에는 결과를 미리 보거나 로컬 컴퓨터로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-113">After you run a search, you can preview the results or export them to a local computer.</span></span>

## <a name="create-and-run-a-search"></a><span data-ttu-id="b8255-114">검색 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="b8255-114">Create and run a search</span></span>

<span data-ttu-id="b8255-115">Microsoft 365 규정 준수의 **콘텐츠 검색** 페이지에 액세스(하여 검색을 실행하고 검색 결과를 미리 보기 및 내보내기를 수행)하려면 관리자, 준수 관리자 또는 eDiscovery 구성원이 보안 및 준수 센터의 eDiscovery 매니저 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-115">To access to the **Content search** page in the Microsoft 365 compliance center (to run searches and preview results and export results), an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in Security & Compliance Center.</span></span> <span data-ttu-id="b8255-116">자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-116">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="b8255-117">해당 <https://compliance.microsoft.com> 할당된 계정의 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-117">Go to <https://compliance.microsoft.com> and sign in using the credentials of an account that's been assigned the appropriate permissions.</span></span>

2. <span data-ttu-id="b8255-118">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 **모두 표시** 를 클릭한 다음 **콘텐츠 검색** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-118">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="b8255-119">**콘텐츠 검색** 페이지에서 **새 검색** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-119">On the **Content search** page, click **New search**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b8255-120">**ID 목록으로 검색**: 이 옵션은 Exchange ID 목록을 사용하여 특정 전자 메일 메시지 및 기타 사서함 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-120">The **Search by ID list** option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="b8255-121">ID 목록 검색을 만들려면 검색할 특정 사서함 항목을 식별하는 CSV(쉼표로 구분된 값) 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-121">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="b8255-122">자세한 내용은 [ID 목록 검색을 위해 CSV 파일 준비](csv-file-for-an-id-list-content-search.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-122">For instructions, see [Prepare a CSV file for an ID list search](csv-file-for-an-id-list-content-search.md).</span></span>

4. <span data-ttu-id="b8255-123">검색 이름과 검색 식별에 도움이 되는 설명(선택 사항)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-123">Type a name for the search, an optional description that helps identify the search.</span></span> <span data-ttu-id="b8255-124">검색 이름은 조직에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-124">The name of the search must be unique in your organization.</span></span>

5. <span data-ttu-id="b8255-125">**위치** 페이지에서 검색할 콘텐츠 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-125">On the **Locations** page, choose the content locations that you want to search.</span></span> <span data-ttu-id="b8255-126">사서함, 사이트 및 공용 폴더를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-126">You can search mailboxes, sites, and public folders.</span></span>

    ![보류 시킬 콘텐츠 위치 선택](../media/ContentSearchLocations.png)
  
   1. <span data-ttu-id="b8255-128">**Exchange 사서함**: 토글을 **켜기** 로 설정한 다음 **사용자, 그룹 또는 팀 선택** 을 클릭하여 보류할 사서함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-128">**Exchange mailboxes**: Set the toggle to **On** and then click **Choose users, groups, or teams** to specify the mailboxes to place on hold.</span></span> <span data-ttu-id="b8255-129">검색 상자를 사용하여 보류 상태로 지정할 사용자 사서함 및 메일 그룹(그룹 구성원의 사서함을 보류)을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-129">Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold.</span></span> <span data-ttu-id="b8255-130">Microsoft Teams(채널 메시지), Office 365 그룹 및 Yammer 그룹과 연결된 사서함을 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-130">You can also search the mailbox associated with a Microsoft Team (for channel messages), Office 365 Group, and Yammer Group.</span></span> <span data-ttu-id="b8255-131">사서함에 저장된 애플리케이션 데이터에 대한 자세한 내용은 [eDiscovery용 사서함에 저장된 콘텐츠](what-is-stored-in-exo-mailbox.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-131">For more information about the application data stored in mailboxes, see [Content stored in mailboxes for eDiscovery](what-is-stored-in-exo-mailbox.md).</span></span>

   2. <span data-ttu-id="b8255-132">**SharePoint 사이트**: 토글을 **켜기** 로 설정한 다음 **사이트 선택** 을 클릭하여 SharePoint 사이트 및 OneDrive 계정을 보류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-132">**SharePoint sites**: Set the toggle to **On** and then click **Choose sites** to specify SharePoint sites and OneDrive accounts to place on hold.</span></span> <span data-ttu-id="b8255-133">보류할 각 사이트의 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-133">Type the URL for each site that you want to place on hold.</span></span> <span data-ttu-id="b8255-134">Microsoft Teams, Office 365 그룹 또는 Yammer 그룹의 SharePoint 사이트 URL을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-134">You can also add the URL for the SharePoint site for a Microsoft Team, Office 365 Group, or Yammer Group.</span></span>
  
   3. <span data-ttu-id="b8255-135">**Exchange 공용 폴더**: 토글을 **켜기** 로 설정하여 Exchange Online 조직의 모든 공용 폴더를 보류합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-135">**Exchange public folders**: Set the toggle to **On** to put all public folders in your Exchange Online organization on hold.</span></span> <span data-ttu-id="b8255-136">보류할 특정 공용 폴더는 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-136">You can't choose specific public folders to put on hold.</span></span> <span data-ttu-id="b8255-137">공용 폴더를 보류하고 싶지 않은 경우 토글 스위치를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-137">Leave the toggle switch off if you don't want to put a hold on public folders.</span></span>
  
   4. <span data-ttu-id="b8255-138">이 확인란을 선택된 것으로 유지하여 온-프레미스 사용자에 대한 Teams 콘텐츠를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-138">Keep this checkbox selected to search for Teams content for on-premises users.</span></span> <span data-ttu-id="b8255-139">예를 들어 조직에서 모든 Exchange 사서함을 검색하고 이 확인란도 선택하는 경우, 온-프레미스 사용자의 Teams 채팅 데이터를 저장하는 데 사용되는 클라우드 기반 저장소가 검색 범위에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-139">For example, if you search all Exchange mailboxes in the organization and this checkbox is selected, the cloud-based storage used to store Teams chat data for on-premises users will be included in the scope of the search.</span></span> <span data-ttu-id="b8255-140">자세한 내용은 [온-프레미스 사용자의 Teams 채팅 데이터 검색](search-cloud-based-mailboxes-for-on-premises-users.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-140">For more information, see [Search for Teams chat data for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>

6. <span data-ttu-id="b8255-141">**검색 조건 정의** 페이지에서 키워드 쿼리를 입력하고, 필요한 경우 검색 쿼리에 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-141">On the **Define your search conditions** page, type a keyword query and add conditions to the search query if necessary.</span></span>

   ![검색 쿼리 구성](../media/ContentSearchQuery.png)

   1. <span data-ttu-id="b8255-143">키워드, 메시지 속성(보낸 날짜 및 받은 날짜) 또는 문서 속성(예: 파일 이름 또는 문서를 마지막으로 변경한 날짜)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-143">Specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="b8255-144">**AND**, **OR**, **NOT**, **NEAR** 와 같은 부울 연산자를 사용하는 좀 더 복잡한 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-144">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="b8255-145">키워드 상자를 비워 두면 지정된 콘텐츠 위치에 있는 모든 콘텐츠가 검색 결과에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-145">If you leave the keyword box empty, all content located in the specified content locations is included in the search results.</span></span> <span data-ttu-id="b8255-146">자세한 내용은 [eDiscovery에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-146">For more information, see [Keyword queries and search conditions for eDiscovery](keyword-queries-and-search-conditions.md).</span></span>

   2. <span data-ttu-id="b8255-147">또는 **키워드 목록 표시** 확인란을 클릭하고 각 행에 키워드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-147">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="b8255-148">이렇게하면 각 행의 키워드는 만든 검색 쿼리의 **OR** 연산자와 기능상 유사한 논리 연산자(**c:s**)로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-148">If you do this, the keywords on each row are connected by a logical operator (**c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span>

      <span data-ttu-id="b8255-149">키워드 목록을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="b8255-149">Why use the keyword list?</span></span> <span data-ttu-id="b8255-150">각 키워드와 일치하는 항목 수를 보여주는 통계를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-150">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="b8255-151">이를 통해 가장 (및 가장 덜) 유효한 키워드를 신속하게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-151">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="b8255-152">키워드 문구(괄호로 묶음)를 연속으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-152">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="b8255-153">키워드 목록 및 검색 통계에 대한 자세한 내용은 [검색에 대한 키워드 통계 얻기](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-153">For more information about the keyword list and search statistics, see [Get keyword statistics for searches](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span>

      > [!NOTE]
      > <span data-ttu-id="b8255-154">큰 키워드 목록으로 인한 문제를 줄일 수 있도록 키워드 목록에서 최대 20개의 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-154">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

   3. <span data-ttu-id="b8255-155">검색 조건을 추가하여 검색 범위를 좁히고 보다 구체적인 결과 집합을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-155">You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="b8255-156">각 조건은 검색을 시작할 때 생성 및 실행되는 검색 쿼리에 절을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-156">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="b8255-157">조건은 **AND** 연산자와 기능상 유사한 논리 연산자(**c:c**)로 키워드 쿼리 (키워드 상자에서 지정)에 논리적으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-157">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="b8255-158">즉, 결과에 포함되려면 항목이 키워드 쿼리와 하나 이상의 조건을 모두 만족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-158">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="b8255-159">이 방법을 통해 결과를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-159">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="b8255-160">검색 쿼리에서 사용할 수 있는 조건의 목록 및 설명은 [검색 조건](keyword-queries-and-search-conditions.md#search-conditions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-160">For a list and description of conditions that you can use in a search query, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>

7. <span data-ttu-id="b8255-161">검색 설정을 검토하고 필요한 경우 편집한 다음 검색을 제출하여 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-161">Review the search settings (and edit if necessary), and then submit the search to start it.</span></span>
  
<span data-ttu-id="b8255-162">이 콘텐츠 검색에 다시 액세스하거나 **콘텐츠 검색** 페이지에 나열된 다른 콘텐츠 검색에 액세스하려면 검색을 선택한 다음 **열기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-162">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b8255-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b8255-163">Next steps</span></span>

<span data-ttu-id="b8255-164">다음은 콘텐츠 검색을 만들고 실행한 후 수행할 다음 단계 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b8255-164">Here's a list of next steps to perform after you create and run a Content search.</span></span>

- [<span data-ttu-id="b8255-165">검색 결과 미리 보기</span><span class="sxs-lookup"><span data-stu-id="b8255-165">Preview search results</span></span>](preview-ediscovery-search-results.md)

- [<span data-ttu-id="b8255-166">검색 결과에 대한 통계 보기</span><span class="sxs-lookup"><span data-stu-id="b8255-166">View statistics for search results</span></span>](view-keyword-statistics-for-content-search.md)

- [<span data-ttu-id="b8255-167">검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="b8255-167">Export search results</span></span>](export-search-results.md)

- [<span data-ttu-id="b8255-168">검색 보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="b8255-168">Export a search report</span></span>](export-a-content-search-report.md)

## <a name="more-information"></a><span data-ttu-id="b8255-169">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="b8255-169">More information</span></span>

<span data-ttu-id="b8255-170">다른 Microsoft 365 서비스의 콘텐츠 검색과 같은 콘텐츠 검색에 대한 자세한 내용은 [콘텐츠 검색 기능 참조](content-search-reference.md)를 보세요.</span><span class="sxs-lookup"><span data-stu-id="b8255-170">For more information about Content search, such as searching for content in different Microsoft 365 services, see [Feature reference for Content search](content-search-reference.md).</span></span>
