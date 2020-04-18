---
title: 핵심 eDiscovery 사례에서 콘텐츠 내보내기 및 다운로드
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
description: 이 문서에서는 핵심 eDiscovery 사례에서 콘텐츠를 내보내고 다운로드 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: e0d4315c48a0d0878b8052265ff8663cd1987169
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551419"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="39649-103">핵심 eDiscovery 사례에서 콘텐츠 내보내기</span><span class="sxs-lookup"><span data-stu-id="39649-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="39649-104">검색을 성공적으로 실행 한 후에는 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-104">After a search is successfully run, you can export the search results.</span></span> <span data-ttu-id="39649-105">검색 결과를 내보낼 때 사서함 항목은 PST 파일이 나 개별 메시지로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="39649-106">SharePoint 및 비즈니스용 OneDrive 사이트에서 콘텐츠를 내보낼 때 기본 Office 문서 및 기타 문서의 복사본이 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="39649-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="39649-107">내보낸 모든 항목에 대 한 정보 및 모든 검색 결과에 대 한 정보가 포함 된 매니페스트 파일 (XML 형식)이 포함 된 결과 .csv 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="39649-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="39649-108">[사례와 연결 된 단일 검색](#export-the-results-of-a-single-search) 의 결과를 내보내거나 [사례와 연결 된 여러 검색](#export-the-results-of-multiple-searches)의 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-108">You can export the results of a [single search associated with a case](#export-the-results-of-a-single-search) or you can export the results of [multiple searches associated with a case](#export-the-results-of-multiple-searches).</span></span>
  
## <a name="export-the-results-of-a-single-search"></a><span data-ttu-id="39649-109">단일 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="39649-109">Export the results of a single search</span></span>

1. <span data-ttu-id="39649-110">[https://compliance.microsoft.com](https://compliance.microsoft.com) 적절 한 eDiscovery 권한이 할당 된 사용자 계정에 대 한 자격 증명을 사용 하 여으로 이동 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-110">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="39649-111">Microsoft 365 준수 센터의 왼쪽 탐색 창에서 **모두 표시**를 클릭 한 다음 **eDiscovery > 코어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-111">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="39649-112">**핵심 eDiscovery** 페이지에서 검색 결과를 내보내려는 사례를 선택 하 고 **열기 사례**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-112">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="39649-113">사례에 대 한 **홈** 페이지에서 **검색** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-113">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="39649-114">사례에 대 한 검색 목록에서 검색 결과를 내보내려는 검색을 클릭 한 다음 플라이 아웃에서 **결과 내보내기를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-114">In the list of searches for the case, click the search that you want to export search results from, and then click **Export results** on the flyout.</span></span>

    <span data-ttu-id="39649-115">**결과 내보내기** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-115">The **Export results** page is displayed.</span></span> 

    ![내보내기 결과 페이지](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="39649-117">핵심 eDiscovery 사례와 연결 된 검색 결과를 내보내기 위한 워크플로는 **콘텐츠 검색** 페이지에서 검색에 대 한 검색 결과를 내보내는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-117">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="39649-118">단계별 지침은 [Export content search results](export-search-results.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39649-118">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="39649-119">검색 결과를 내보낼 때는 검색 된 사서함에서 같은 메시지의 인스턴스가 여러 개 발견 된 경우에도 전자 메일 메시지의 복사본 하나만 내보내도록 하는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-119">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="39649-120">복제 제거 및 중복 항목이 식별 되는 방식에 대 한 자세한 내용은 [eDiscovery 검색 결과의 중복](de-duplication-in-ediscovery-search-results.md)제거를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39649-120">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

    <span data-ttu-id="39649-121">내보내기를 시작한 후에는 검색 결과가 다운로드 가능 하므로 Microsoft 클라우드에서 Microsoft가 제공한 Azure 저장소 위치로 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-121">After you start the export, the search results are prepared for downloading, which means they are uploaded to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="39649-122">**내보내기** 탭을 클릭 하 여 사례에 대 한 내보내기 작업 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-122">Click the **Export** tab to display the list of export jobs for the case.</span></span>
  
    <span data-ttu-id="39649-123">**새로 고침** 을 클릭 하 여 만든 내보내기 작업이 표시 되도록 내보내기 작업 목록을 업데이트 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-123">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="39649-124">내보내기 작업의 이름은 검색 이름에 **_Export** 추가 된 해당 검색과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-124">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="39649-125">만든 내보내기 작업을 클릭 하 여 플라이 아웃 페이지에 상태 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-125">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="39649-126">이 정보에는 Azure 저장소 위치로 전송 된 항목의 백분율이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-126">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="39649-127">모든 항목을 전송 하 고 나면 **결과 다운로드** 를 클릭 하 여 로컬 컴퓨터에 검색 결과를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-127">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="39649-128">검색 결과를 다운로드 하는 방법에 대 한 자세한 내용은 [Export content search results](export-search-results.md#step-2-download-the-search-results) in의 2 단계를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39649-128">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

## <a name="export-the-results-of-multiple-searches"></a><span data-ttu-id="39649-129">여러 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="39649-129">Export the results of multiple searches</span></span>

<span data-ttu-id="39649-130">사례와 연결 된 단일 검색의 결과를 내보내는 대신 단일 내보내기 작업에서 여러 검색의 결과를 동일한 case에서 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-130">As an alternative to exporting the results of a single search associated with a case, you can export the results of multiple searches from the same case in a single export job.</span></span> <span data-ttu-id="39649-131">결과를 한 번에 하나씩 내보내는 것 보다 여러 검색의 결과를 내보낼 때 보다 빠르고 쉽게 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-131">Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39649-132">이러한 검색 중 하나가 보류 중인 위치를 검색 하도록 구성 된 경우에는 여러 검색의 결과를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-132">You can't export the results of multiple searches if one of those searches was configured to search locations on hold.</span></span>

1. <span data-ttu-id="39649-133">[https://compliance.microsoft.com](https://compliance.microsoft.com) 적절 한 eDiscovery 권한이 할당 된 사용자 계정에 대 한 자격 증명을 사용 하 여으로 이동 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="39649-134">Microsoft 365 준수 센터의 왼쪽 탐색 창에서 **모두 표시**를 클릭 한 다음 **eDiscovery > 코어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-134">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="39649-135">**핵심 eDiscovery** 페이지에서 검색 결과를 내보내려는 사례를 선택 하 고 **열기 사례**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-135">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="39649-136">사례에 대 한 **홈** 페이지에서 **검색** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-136">On the **Home** page for the case, click the **Searches** tab.</span></span>
    
5. <span data-ttu-id="39649-137">사례에 대 한 검색 목록에서 검색 결과를 내보내려는 두 개 이상의 검색 옆에 있는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-137">In the list of searches for the case, select the checkbox next to two or more searches you want to export search results from.</span></span> 

   <span data-ttu-id="39649-138">**대량 작업** 플라이 아웃 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="39649-138">The **Bulk actions** flyout page appears.</span></span> 

    ![대량 작업 페이지에서 결과 내보내기 클릭](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. <span data-ttu-id="39649-140">**결과 내보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-140">Click **Export results**.</span></span>

   <span data-ttu-id="39649-141">**결과 내보내기** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-141">The **Export results** page is displayed.</span></span> 

    ![내보내기 결과 페이지](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="39649-143">이 시점에서 코어 eDiscovery 사례와 연결 된 여러 검색의 결과를 내보내기 위한 워크플로는 단일 검색에 대 한 검색 결과를 내보내는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-143">At this point, the workflow to export the results of multiple searches associated with a Core eDiscovery case is that same as exporting the search results for a single search.</span></span> <span data-ttu-id="39649-144">이전 섹션의 5 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39649-144">See step 5 in the previous section.</span></span>

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="39649-145">여러 검색 결과 내보내기에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="39649-145">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="39649-146">여러 검색의 결과를 내보낼 때 모든 검색의 검색 쿼리를 사용 하 여 **OR** 연산자를 결합 한 다음 결합 된 검색을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-146">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started.</span></span> <span data-ttu-id="39649-147">결합 된 검색의 예상 결과는 선택한 내보내기 작업의 플라이 아웃 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-147">The estimated results of the combined search are displayed in the flyout page of the selected export job.</span></span> <span data-ttu-id="39649-148">검색 결과가 Microsoft 클라우드의 Azure Storage 위치에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-148">The search results are then copied to the Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="39649-149">복사 작업의 상태는 플라이 아웃 페이지에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-149">The status of the copy job is also displayed on the flyout page.</span></span> <span data-ttu-id="39649-150">앞에서 설명한 것 처럼 모든 검색 결과를 복사한 후 로컬 컴퓨터에 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-150">As previously stated, after all the search results have been copied, you can download them to a local computer.</span></span>

- <span data-ttu-id="39649-151">내보내려는 모든 검색에 대 한 쿼리의 최대 키워드 수는 500입니다.</span><span class="sxs-lookup"><span data-stu-id="39649-151">The maximum number of keywords from queries for all searches that you want to export is 500.</span></span> <span data-ttu-id="39649-152">이 제한은 단일 검색에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-152">This is the same limit for a single search.</span></span> <span data-ttu-id="39649-153">내보내기 작업은 **OR** 연산자를 사용 하 여 모든 검색 쿼리를 결합 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="39649-153">That's because the export job combines all the search queries by using the **OR** operator.</span></span> <span data-ttu-id="39649-154">이 제한을 초과 하면 오류가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-154">If you exceed this limit, an error will be returned.</span></span> <span data-ttu-id="39649-155">이 경우 검색 결과를 줄여서 내보낼 원본 검색의 검색 쿼리를 단순화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-155">In this case, you have to export the results from fewer searches or simplify the search queries of the original searches that you want to export.</span></span>

- <span data-ttu-id="39649-156">내보낸 검색 결과는 항목을 찾은 콘텐츠 위치로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-156">The search results that are exported are organized by the content location the item was found in.</span></span> <span data-ttu-id="39649-157">즉, 내보내기 결과의 콘텐츠 위치에 여러 검색에서 반환 되는 항목이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-157">That means a content location in the export results may have items returned by different searches.</span></span> <span data-ttu-id="39649-158">예를 들어 각 사서함에 대해 한 PST 파일에 전자 메일 메시지를 내보내도록 선택한 경우 PST 파일에 여러 검색 결과가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-158">For example, if you choose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>

- <span data-ttu-id="39649-159">내보낸 검색 중 둘 이상에서 동일한 콘텐츠 위치에 있는 동일한 전자 메일 항목 또는 문서를 반환 하는 경우에는 항목의 복사본을 하나만 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="39649-159">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>

- <span data-ttu-id="39649-160">여러 검색을 만든 후에는 해당 내보내기를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-160">You can't edit an export for multiple searches after you create it.</span></span> <span data-ttu-id="39649-161">예를 들어 내보내기 작업에서 검색을 추가 하거나 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-161">For example, you can't add or remove searches from the export job.</span></span> <span data-ttu-id="39649-162">내보낼 검색 결과를 변경 하려면 내보내기 작업을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39649-162">You have to create an export job to change which search results are exported.</span></span> <span data-ttu-id="39649-163">내보내기 작업을 만든 후에는 결과를 컴퓨터로 다운로드 하거나, 내보내기를 다시 시작 하거나, 내보내기 작업을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-163">After an export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>

- <span data-ttu-id="39649-164">내보내기를 다시 시작 하면 내보내기 작업을 구성 하는 검색 쿼리에 대 한 모든 변경 내용이 검색 된 검색 결과에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-164">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="39649-165">내보내기를 다시 시작 하면 내보내기 작업을 만들 때 실행 된 것과 동일한 결합 된 검색 쿼리 작업이 다시 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39649-165">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="39649-166">또한 내보내기를 다시 시작 하면 Azure 저장소 위치로 복사 되는 검색 결과가 이전 결과를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="39649-166">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="39649-167">이전에 복사한 결과를 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-167">The previous results that were copied won't be available to be downloaded.</span></span>

- <span data-ttu-id="39649-168">고급 eDiscovery (클래식)에서 여러 검색의 결과를 준비 하는 것은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-168">Preparing the results of multiple searches for analysis in Advanced eDiscovery (classic) isn't available.</span></span> <span data-ttu-id="39649-169">고급 eDiscovery (클래식)에서 분석에 대 한 단일 검색 결과만 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39649-169">You can only prepare the results of a single search for analysis in Advanced eDiscovery (classic).</span></span>
