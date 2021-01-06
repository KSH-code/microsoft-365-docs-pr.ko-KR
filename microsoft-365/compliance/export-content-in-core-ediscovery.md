---
title: Core eDiscovery 사례에서 콘텐츠 내보내기 및 다운로드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 Core eDiscovery 사례에서 콘텐츠를 내보내고 다운로드하는 방법을 설명합니다.
ms.openlocfilehash: 30fc30943bd570cf4d79ce88b5bef5836b3dfe14
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760302"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="9fd61-103">Core eDiscovery 사례에서 콘텐츠 내보내기</span><span class="sxs-lookup"><span data-stu-id="9fd61-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="9fd61-104">검색이 성공적으로 실행된 후 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-104">After a search is successfully run, you can export the search results.</span></span> <span data-ttu-id="9fd61-105">검색 결과를 내보내면 사서함 항목이 PST 파일 또는 개별 메시지로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="9fd61-106">SharePoint 및 비즈니스용 OneDrive 사이트에서 콘텐츠를 내보내면 기본 Office 문서 및 기타 문서의 복사본이 내보내됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="9fd61-107">내보낼 Results.csv 대한 정보가 포함된 파일과 모든 검색 결과에 대한 정보가 포함된 매니페스트 파일(XML 형식)도 내보내기됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="9fd61-108">사례와 연결된 단일 [](#export-the-results-of-a-single-search) 검색의 결과를 내보내거나 사례와 연결된 여러 검색의 결과를 내보낼 [수 있습니다.](#export-the-results-of-multiple-searches)</span><span class="sxs-lookup"><span data-stu-id="9fd61-108">You can export the results of a [single search associated with a case](#export-the-results-of-a-single-search) or you can export the results of [multiple searches associated with a case](#export-the-results-of-multiple-searches).</span></span>
  
## <a name="export-the-results-of-a-single-search"></a><span data-ttu-id="9fd61-109">단일 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="9fd61-109">Export the results of a single search</span></span>

1. <span data-ttu-id="9fd61-110">적절한 eDiscovery 권한이 할당된 사용자 계정의 자격 증명을 사용하여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-110">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="9fd61-111">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-111">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="9fd61-112">Core **eDiscovery** 페이지에서 검색 결과를 내보낼 사례를 선택하고 사례 **열기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fd61-112">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="9fd61-113">사례의 **홈** 페이지에서 검색 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-113">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="9fd61-114">사례에 대한 검색 목록에서 검색 결과를 내보낼 검색을 클릭한 다음  플라이아웃에서 결과 내보내기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-114">In the list of searches for the case, click the search that you want to export search results from, and then click **Export results** on the flyout.</span></span>

    <span data-ttu-id="9fd61-115">결과 **내보내기** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-115">The **Export results** page is displayed.</span></span> 

    ![결과 내보내기 페이지](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="9fd61-117">Core eDiscovery 사례와 연결된 검색 결과를 내보내는 워크플로는 콘텐츠 검색 페이지에서 검색 결과를 내보내는 워크플로와 **동일합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fd61-117">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="9fd61-118">단계별 지침은 콘텐츠 검색 결과 [내보내기를 참조하세요.](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="9fd61-118">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9fd61-119">검색 결과를 내보낼 때 동일한 메시지의 여러 인스턴스가 검색된 사서함에 있을 수 있는 경우에도 전자 메일 메시지 복사본을 하나만 내보낼 수 있도록 중복 제거를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-119">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="9fd61-120">중복 제거 및 중복 항목을 식별하는 방법에 대한 자세한 내용은 [eDiscovery](de-duplication-in-ediscovery-search-results.md)검색 결과에서 중복 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd61-120">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

    <span data-ttu-id="9fd61-121">내보내기 시작하면 검색 결과가 다운로드 준비됩니다. 즉, Microsoft 클라우드의 Microsoft 제공 Azure Storage 위치에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-121">After you start the export, the search results are prepared for downloading, which means they are uploaded to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="9fd61-122">내보내기 **탭을** 클릭하여 사례에 대한 내보내기 작업 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-122">Click the **Export** tab to display the list of export jobs for the case.</span></span>
  
    <span data-ttu-id="9fd61-123">새로 고침을 **클릭하여** 만든 내보내기 작업을 표시하기 위해 내보내기 작업 목록을 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-123">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="9fd61-124">내보내기 작업의 이름은 검색 이름에  추가된 _Export 검색과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-124">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="9fd61-125">만든 내보내기 작업을 클릭하여 플라이아웃 페이지에 상태 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-125">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="9fd61-126">이 정보에는 Azure Storage 위치로 전송된 항목의 백분율이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-126">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="9fd61-127">모든 항목이 전송된 후  결과 다운로드를 클릭하여 검색 결과를 로컬 컴퓨터에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-127">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="9fd61-128">검색 결과를 다운로드하는 자세한 내용은 콘텐츠 검색 결과 내보내기 [2단계를 참조하세요.](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="9fd61-128">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

## <a name="export-the-results-of-multiple-searches"></a><span data-ttu-id="9fd61-129">여러 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="9fd61-129">Export the results of multiple searches</span></span>

<span data-ttu-id="9fd61-130">사례와 연결된 단일 검색의 결과를 내보내는 대신 단일 내보내기 작업에서 동일한 사례에서 여러 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-130">As an alternative to exporting the results of a single search associated with a case, you can export the results of multiple searches from the same case in a single export job.</span></span> <span data-ttu-id="9fd61-131">여러 검색의 결과를 한 번씩 내보내는 것보다 결과를 한 번 더 빠르고 쉽게 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-131">Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fd61-132">이러한 검색 중 하나를 보류된 위치로 구성한 경우 여러 검색 결과를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-132">You can't export the results of multiple searches if one of those searches was configured to search locations on hold.</span></span>

1. <span data-ttu-id="9fd61-133">적절한 eDiscovery 권한이 할당된 사용자 계정의 자격 증명을 사용하여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="9fd61-134">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-134">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="9fd61-135">Core **eDiscovery** 페이지에서 검색 결과를 내보낼 사례를 선택하고 사례 **열기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fd61-135">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="9fd61-136">사례의 **홈** 페이지에서 검색 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-136">On the **Home** page for the case, click the **Searches** tab.</span></span>
    
5. <span data-ttu-id="9fd61-137">사례에 대한 검색 목록에서 검색 결과를 내보낼 둘 이상의 검색 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-137">In the list of searches for the case, select the checkbox next to two or more searches you want to export search results from.</span></span> 

   <span data-ttu-id="9fd61-138">대량 **작업 플라이아웃** 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-138">The **Bulk actions** flyout page appears.</span></span> 

    ![대량 작업 페이지에서 결과 내보내기 클릭](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. <span data-ttu-id="9fd61-140">결과 **내보내기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fd61-140">Click **Export results**.</span></span>

   <span data-ttu-id="9fd61-141">결과 **내보내기** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-141">The **Export results** page is displayed.</span></span> 

    ![결과 내보내기 페이지](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="9fd61-143">이때 Core eDiscovery 사례와 연결된 여러 검색의 결과를 내보내는 워크플로는 단일 검색에 대한 검색 결과를 내보내는 워크플로와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-143">At this point, the workflow to export the results of multiple searches associated with a Core eDiscovery case is that same as exporting the search results for a single search.</span></span> <span data-ttu-id="9fd61-144">이전 섹션의 5단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd61-144">See step 5 in the previous section.</span></span>

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="9fd61-145">여러 검색 결과 내보내기에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="9fd61-145">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="9fd61-146">여러 검색의 결과를 내보내면 **OR** 연산자를 사용하여 모든 검색의 검색 쿼리가 결합된 다음 결합된 검색이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-146">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started.</span></span> <span data-ttu-id="9fd61-147">결합된 검색의 예상 결과는 선택한 내보내기 작업의 플라이아웃 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-147">The estimated results of the combined search are displayed in the flyout page of the selected export job.</span></span> <span data-ttu-id="9fd61-148">그런 다음 검색 결과가 Microsoft 클라우드의 Azure Storage 위치에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-148">The search results are then copied to the Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="9fd61-149">복사 작업의 상태도 플라이아웃 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-149">The status of the copy job is also displayed on the flyout page.</span></span> <span data-ttu-id="9fd61-150">앞서 설명한 것 처럼 모든 검색 결과가 복사된 후 로컬 컴퓨터에 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-150">As previously stated, after all the search results have been copied, you can download them to a local computer.</span></span>

- <span data-ttu-id="9fd61-151">내보낼 모든 검색에 대한 쿼리의 최대 키워드 수는 500개입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-151">The maximum number of keywords from queries for all searches that you want to export is 500.</span></span> <span data-ttu-id="9fd61-152">단일 검색에 대한 제한과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-152">This is the same limit for a single search.</span></span> <span data-ttu-id="9fd61-153">이는 내보내기 작업이 **OR** 연산자를 사용하여 모든 검색 쿼리를 결합하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-153">That's because the export job combines all the search queries by using the **OR** operator.</span></span> <span data-ttu-id="9fd61-154">이 제한을 초과하면 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-154">If you exceed this limit, an error will be returned.</span></span> <span data-ttu-id="9fd61-155">이 경우 더 적은 수의 검색에서 결과를 내보내거나 내보낼 원본 검색의 검색 쿼리를 단순화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-155">In this case, you have to export the results from fewer searches or simplify the search queries of the original searches that you want to export.</span></span>

- <span data-ttu-id="9fd61-156">내보낼 검색 결과는 항목을 찾은 콘텐츠 위치에 따라 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-156">The search results that are exported are organized by the content location the item was found in.</span></span> <span data-ttu-id="9fd61-157">즉, 내보내기 결과의 콘텐츠 위치에 다른 검색에서 반환된 항목이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-157">That means a content location in the export results may have items returned by different searches.</span></span> <span data-ttu-id="9fd61-158">예를 들어 각 사서함에 대해 하나의 PST 파일로 전자 메일 메시지를 내보내는 경우 PST 파일에 여러 검색 결과가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-158">For example, if you choose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>

- <span data-ttu-id="9fd61-159">동일한 콘텐츠 위치의 동일한 전자 메일 항목 또는 문서가 내보내는 검색 중 두 개 이상에 의해 반환되는 경우 항목의 복사본이 하나만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-159">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>

- <span data-ttu-id="9fd61-160">여러 검색을 만든 후 내보내기 기능을 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-160">You can't edit an export for multiple searches after you create it.</span></span> <span data-ttu-id="9fd61-161">예를 들어 내보내기 작업에서 검색을 추가하거나 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-161">For example, you can't add or remove searches from the export job.</span></span> <span data-ttu-id="9fd61-162">내보내는 검색 결과를 변경하기 위해 내보내기 작업을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-162">You have to create an export job to change which search results are exported.</span></span> <span data-ttu-id="9fd61-163">내보내기 작업을 만든 후 결과를 컴퓨터에 다운로드하거나 내보내기 작업을 다시 시작하거나 내보내기 작업을 삭제할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-163">After an export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>

- <span data-ttu-id="9fd61-164">내보내기 작업을 다시 시작하면 내보내기 작업을 만드는 검색의 쿼리에 대한 변경 내용이 검색된 검색 결과에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-164">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="9fd61-165">내보내기 작업을 다시 시작하면 내보내기 작업을 만들 때 실행된 동일한 결합된 검색 쿼리 작업이 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-165">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="9fd61-166">또한 내보내기 기능을 다시 시작하면 Azure Storage 위치로 복사된 검색 결과가 이전 결과를 덮어입습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-166">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="9fd61-167">복사된 이전 결과는 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd61-167">The previous results that were copied won't be available to be downloaded.</span></span>
