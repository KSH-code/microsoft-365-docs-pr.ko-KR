---
title: ID 목록 콘텐츠 검색을 위한 CSV 파일 준비
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: 기존 콘텐츠 검색의 CSV 파일을 사용하여 특정 전자 메일 항목을 반환하는 ID 목록 검색을 만들 수 있습니다.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311541"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="8f5fa-103">ID 목록 콘텐츠 검색을 위한 CSV 파일 준비</span><span class="sxs-lookup"><span data-stu-id="8f5fa-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="8f5fa-104">특정 사서함 전자 메일 메시지 및 기타 사서함 항목은 특정 사서함 EXCHANGE 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="8f5fa-105">ID 목록 검색을 만들려면 검색할 특정 사서함 항목을 식별하는 CSV(쉼표로 구분된 값) 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="8f5fa-106">이 CSV 파일의 경우  콘텐츠 검색 결과를 내보내거나 기존 콘텐츠 검색에서 콘텐츠 검색 보고서를 **내보낼 때** 포함된Results.csv파일 또는 인덱서되지 않은 Items.csv파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="8f5fa-107">그런 다음 이러한 파일 중 하나를 편집하여 검색할 특정 항목을 나타내고, 새 ID 목록 검색을 만들고, CSV 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="8f5fa-108">**ID 목록 검색을 만드는 이유**</span><span class="sxs-lookup"><span data-stu-id="8f5fa-108">**Why create an ID list search?**</span></span> <span data-ttu-id="8f5fa-109">Results.csv또는 인덱서되지 않은 Items.csv파일의 메타데이터를 기반으로 항목이 eDiscovery 요청에 응답하는지 여부를 확인할 수 없는 경우 ID 목록 검색을 사용하여 해당 항목을 찾고 **미리** 보고 내보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="8f5fa-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="8f5fa-110">ID 목록 검색은 일반적으로 인덱서되지 않은 특정 항목 집합을 검색하고 반환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="8f5fa-111">ID 목록 검색을 만드는 프로세스를 간략하게 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="8f5fa-112">규정 준수 센터에서 새 검색을 Microsoft 365 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="8f5fa-113">콘텐츠 검색 결과 또는 콘텐츠 검색 보고서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="8f5fa-114">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-114">For more information, see:</span></span>

    - [<span data-ttu-id="8f5fa-115">콘텐츠 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="8f5fa-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="8f5fa-116">콘텐츠 검색 보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="8f5fa-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="8f5fa-117">Results.csv 파일 또는 Items.csv **파일을** 편집하고 ID 목록 검색에 포함할 특정 사서함 항목을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="8f5fa-118">ID 목록 [검색을](#prepare-the-csv-file-for-an-id-list-search) 위해 CSV 파일을 준비하기 위한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="8f5fa-119">새 ID 목록 검색을 만들고(지침 [참조)](#create-an-id-list-search)준비한 CSV 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="8f5fa-120">생성된 검색 쿼리는 CSV 파일에서 선택한 항목만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="8f5fa-121">ID 목록 검색은 사서함 항목에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="8f5fa-122">ID 목록 검색에서 SharePoint OneDrive 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="8f5fa-123">ID 목록 검색을 위한 CSV 파일 준비</span><span class="sxs-lookup"><span data-stu-id="8f5fa-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="8f5fa-124">검색에 대한 검색 결과 또는 보고서를 내보본 후 다음 단계를 수행하여 ID 목록 검색을 위해 CSV 파일을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="8f5fa-125">이 CSV 파일은 ID 목록 검색의 모든 항목을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="8f5fa-126">사이트 및 SharePoint 계정이 포함된 검색에서 CSV OneDrive 수 있지만 ID 목록 검색을 위해 사서함 항목만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="8f5fa-127">SharePoint 또는 OneDrive 경우 ID 목록 검색을 만들 때 CSV 파일의 유효성 검사가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="8f5fa-128">파일 **Results.csv** 또는 인덱서되지 **않은** Items.csv파일을 Excel.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="8f5fa-129">선택한 **열에서** 검색할 항목에 해당하는 셀에 예를 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="8f5fa-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="8f5fa-130">검색하려는 모든 항목에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8f5fa-131">CSV 파일을 열면 Excel **ID** 열의 데이터 형식이 일반으로 변경될 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8f5fa-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="8f5fa-132">그러면 항목에 대한 문서 ID가 과학적 표시로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="8f5fa-133">예를 들어 "481037338205"의 문서 ID는 "4.81037E+11"으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="8f5fa-134">이 경우 다음 단계를 수행하여 문서 **ID** 열의 데이터 형식을 **번호로** 변경하여 문서 ID에 대한 올바른 형식을 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="8f5fa-135">이렇게 하지 않는 경우 CSV 파일을 사용하는 ID 목록 검색이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="8f5fa-136">전체 문서 **ID 열을 마우스 오른쪽 단추로** 클릭하고 **셀 서식을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f5fa-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="8f5fa-137">범주 **상자에서** 번호를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f5fa-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="8f5fa-138">소수 자식 수를 **0으로** 변경한  다음 확인을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="8f5fa-139">문서 ID 열의 값은 숫자로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="8f5fa-140">다음은 ID 목록 콘텐츠 검색을 위해 제출할 준비가 된 CSV 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![대상 콘텐츠 검색을 위한 CSV 파일의 예](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="8f5fa-142">CSV 파일을 저장하거나  다른 이름으로 저장을 사용하여 다른 파일 이름으로 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="8f5fa-143">두 경우 모두 CSV 형식으로 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="8f5fa-144">ID 목록 검색 만들기</span><span class="sxs-lookup"><span data-stu-id="8f5fa-144">Create an ID list search</span></span>

<span data-ttu-id="8f5fa-145">다음 단계는 새 ID 목록 검색을 만들고 이전 단계에서 준비한 CSV 파일을 제출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f5fa-146">검색 결과 또는 보고서를 내보낼 때 ID 목록 검색을 2일 이상 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="8f5fa-147">2일 전에 내보낼 검색 결과 또는 보고서의 경우 검색 결과 또는 보고서를 다시 내보내서 업데이트된 CSV 파일을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="8f5fa-148">그런 다음 업데이트된 CSV 파일 중 하나를 준비하고 이를 사용하여 ID 목록 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="8f5fa-149"><https://compliance.microsoft.com>으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="8f5fa-150">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 **모두 표시** 를 클릭한 다음 **콘텐츠 검색** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="8f5fa-151">콘텐츠 검색 **페이지에서** **ID 목록으로 검색을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f5fa-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="8f5fa-152">ID로  검색 목록 플라이아웃에서 검색 이름을 지정하고 원하는 경우  설명을 지정한 다음 찾아보기를 클릭하고 이전 단계에서 준비한 CSV 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="8f5fa-153">Microsoft 365 CSV 파일의 유효성을 검사하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="8f5fa-154">유효성 검사에 실패하면 유효성 검사 오류를 해결하는 데 도움이 될 수 있는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="8f5fa-155">ID 목록 검색을 만들 수 있는 CSV 파일의 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="8f5fa-156">CSV 파일의 유효성을 검사한 후  검색을 클릭하여 ID 목록 검색을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="8f5fa-157">다음은 생성된 쿼리와 예상 검색 결과 수를 표시하는 ID 목록 검색의 플라이아웃 페이지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![ID 목록 검색에 대한 검색 쿼리](../media/SearchIDListFlyout.png)

    <span data-ttu-id="8f5fa-159">ID 검색 통계에 표시되는 예상 항목 수는 CSV 파일에서 선택한 항목 수와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="8f5fa-160">ID 목록 검색에서 반환된 항목을 미리 보거나 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="8f5fa-161">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8f5fa-161">More information</span></span>

<span data-ttu-id="8f5fa-162">ID 목록 검색을 만들고 나서 사서함을 이동하면 검색 쿼리에서 지정된 항목이 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="8f5fa-163">사서함을 이동할 때 사서함 항목의 **DocumentId** 속성이 변경되어 있기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="8f5fa-164">ID 목록 검색을 만든 후 사서함을 이동하는 경우는 드물지만 새 콘텐츠 검색을 만들거나 기존 검색에 대한 검색 결과를 업데이트한 다음 검색 결과 또는 보고서를 내보내 새 ID 목록 검색을 만드는 데 사용할 수 있는 업데이트된 CSV 파일을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5fa-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
