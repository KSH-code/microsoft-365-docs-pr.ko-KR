---
title: ID 목록 콘텐츠 검색에 대 한 CSV 파일 준비
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
description: 기존 콘텐츠 검색의 CSV 파일을 사용하여 특정 전자 메일 메시지를 반환하는 ID 목록 검색을 만들 수 있습니다.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817977"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="a36fd-103">ID 목록 콘텐츠 검색에 대 한 CSV 파일 준비</span><span class="sxs-lookup"><span data-stu-id="a36fd-103">Prepare a CSV file for an ID list Content Search</span></span>

<span data-ttu-id="a36fd-104">Exchange ID 목록을 사용하여 특정 사서함 전자 메일 메시지 및 기타 사서함 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="a36fd-105">ID 목록 검색(대상 지정 검색이라고도 합니다)을 만들 수 있도록 검색할 특정 사서함 항목을 식별하는 CSV(콤보로 구분된 값) 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-105">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="a36fd-106">이 CSV 파일의 경우 콘텐츠 **검색** 결과를 내보내거나 콘텐츠 검색 보고서를 기존 콘텐츠 검색에서 내보낼 **때** 포함된Results.csv파일 또는 인덱서되지 않은 Items.csv파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-106">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="a36fd-107">그런 다음 이러한 파일 중 하나를 편집하여 검색할 특정 항목을 지정한 다음 새 ID 목록 검색을 만들고 CSV 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-107">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span>

<span data-ttu-id="a36fd-108">ID 목록 검색을 만드는 프로세스를 간략하게 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-108">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="a36fd-109">보안 및 준수 센터에서 새 콘텐츠 검색 또는 & 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-109">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="a36fd-110">콘텐츠 검색 결과를 내보내거나 콘텐츠 검색 보고서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-110">Export the content search results or export the content search report.</span></span> <span data-ttu-id="a36fd-111">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a36fd-111">For more information, see:</span></span>

    - [<span data-ttu-id="a36fd-112">콘텐츠 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="a36fd-112">Export Content Search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="a36fd-113">콘텐츠 검색 보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="a36fd-113">Export a Content Search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="a36fd-114">Results.csv **파일** 또는 인덱서되지 않은 Items.csvID 목록 검색에 포함할 특정 사서함 항목을 식별합니다. </span><span class="sxs-lookup"><span data-stu-id="a36fd-114">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="a36fd-115">ID [목록](#prepare-the-csv-file-for-an-id-list-search) 검색을 위해 CSV 파일을 준비하기 위한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a36fd-115">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="a36fd-116">새 ID 목록 검색을 만들고(지침 [참조)](#create-an-id-list-search)준비한 CSV 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-116">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="a36fd-117">생성된 검색 쿼리는 CSV 파일에서 선택한 항목만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-117">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="a36fd-118">ID 목록 검색은 사서함 항목에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-118">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="a36fd-119">ID 목록 검색에서는 SharePoint 및 OneDrive 문서를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-119">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

 <span data-ttu-id="a36fd-120">**ID 목록 검색을 만드는 이유**</span><span class="sxs-lookup"><span data-stu-id="a36fd-120">**Why create an ID list search?**</span></span> <span data-ttu-id="a36fd-121">**Results.csv** 또는 인덱서되지 않은 Items.csv파일의 메타데이터를 기반으로 항목이 eDiscovery 요청에 응답하는지 여부를 확인할 수 없는 경우 ID 목록 검색을 사용하여 해당 항목을 찾아 미리 보고 내보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="a36fd-121">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="a36fd-122">ID 목록 검색은 일반적으로 인덱서되지 않은 특정 항목 집합을 검색하고 반환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-122">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="a36fd-123">ID 목록 검색을 위한 CSV 파일 준비</span><span class="sxs-lookup"><span data-stu-id="a36fd-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="a36fd-124">콘텐츠 검색에 대한 검색 결과 또는 보고서를 내보낼 경우 다음 단계를 수행하여 ID 목록 검색을 위해 CSV 파일을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-124">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="a36fd-125">이 CSV 파일은 ID 목록 검색의 모든 항목을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-125">This CSV file will identify every item in the ID list search.</span></span>

<span data-ttu-id="a36fd-126">SharePoint 사이트 및 OneDrive 계정을 포함 하는 검색에서 CSV 파일을 사용할  수 있지만 ID 목록 검색에 대 한 사서함 항목만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-126">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="a36fd-127">SharePoint 또는 OneDrive에서 문서를 선택하면 ID 목록 검색을 만들 때 CSV 파일이 유효성 검사에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="a36fd-128">Excel에서 Results.csv파일을 열거나 **Items.csv** 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="a36fd-129">선택한 **열에** 검색할 항목에 해당하는 셀에 **예를** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="a36fd-130">검색하려는 모든 항목에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a36fd-131">Excel에서 CSV 파일을 열면 문서 **ID** 열의 데이터 형식이 일반으로 **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a36fd-131">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="a36fd-132">따라서 항목의 문서 ID가 과학적 표시로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="a36fd-133">예를 들어 "481037338205"의 문서 ID는 "4.81037E+11"으로 표시됩니다. 문서 **ID** 열의 데이터 형식을 **숫자로** 변경하여 문서 ID에 대한 올바른 형식을 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="a36fd-134">이렇게 하지 않는 경우 CSV 파일을 사용하는 ID 목록 검색이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-134">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="a36fd-135">전체 문서 **ID 열을 마우스 오른쪽 단추로** 클릭하고 **셀 서식을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a36fd-135">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="a36fd-136">범주 **상자에서** 번호를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a36fd-136">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="a36fd-137">소수 자치소 수를 **0으로** 변경한 다음 **확인을** 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-137">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="a36fd-138">문서 ID 열의 값은 숫자로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-138">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="a36fd-139">다음은 ID 목록 콘텐츠 검색을 위해 제출할 준비가 된 CSV 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-139">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>

    ![대상 콘텐츠 검색에 대한 CSV 파일의 예](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. <span data-ttu-id="a36fd-141">CSV 파일을 저장하거나  다른 파일 이름으로 다른 이름으로 저장에 다른 이름으로 저장을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-141">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="a36fd-142">두 경우 모두 CSV 형식으로 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-142">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="a36fd-143">ID 목록 검색 만들기</span><span class="sxs-lookup"><span data-stu-id="a36fd-143">Create an ID list search</span></span>

<span data-ttu-id="a36fd-144">다음 단계에서는 새 ID 목록 콘텐츠 검색을 만들고 이전 단계에서 준비한 CSV 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-144">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a36fd-145">콘텐츠 검색에서 결과 또는 보고서를 내보낼 때 ID 목록 검색을 2일 이상 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-145">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="a36fd-146">2일이 지난 검색 결과 또는 보고서를 내보낼 경우 검색 결과 또는 보고서를 다시 내보내 업데이트된 CSV 파일을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-146">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="a36fd-147">그런 다음 업데이트된 CSV 파일 중 하나를 준비하고 이를 사용하여 ID 목록 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-147">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="a36fd-148">보안 & 준수 센터에서 검색 콘텐츠  \> **검색으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="a36fd-148">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>

2. <span data-ttu-id="a36fd-149">검색 **페이지에서** 아이콘 새로 검색 추가 옆에 있는 화살표를 클릭한 다음 ID 목록으로 ![ ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)  **검색을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a36fd-149">On the **Search** page, click the arrow next to ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>

    ![새 검색 드롭다운 목록에서 ID로 검색 목록 클릭](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. <span data-ttu-id="a36fd-151">**ID로** 검색 목록 플라이아웃에서 검색 이름을 지정하고 원하는 경우  설명을 입력한 다음 찾아보기를 클릭하고 이전 단계에서 준비한 CSV 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-151">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="a36fd-152">Microsoft 365는 CSV 파일의 유효성을 검사하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-152">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="a36fd-153">유효성 검사에 실패하면 유효성 검사 오류를 해결하는 데 도움이 될 수 있는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-153">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="a36fd-154">ID 목록 검색을 만들 수 있는 CSV 파일의 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-154">The CSV file has to be successfully validated to create an ID list search.</span></span>

4. <span data-ttu-id="a36fd-155">CSV 파일의 유효성을 검사한 후 **검색을** 클릭하여 ID 목록 검색을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-155">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="a36fd-156">다음은 ID 목록 검색에 대해 생성된 예상 검색 결과 및 쿼리의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-156">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>

    ![세부 정보 창의 대상 콘텐츠 검색에 대한 검색 쿼리](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    <span data-ttu-id="a36fd-158">ID 검색 통계에 표시되는 예상 항목 수는 CSV 파일에서 선택한 항목 수와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-158">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

5. <span data-ttu-id="a36fd-159">ID 목록 검색에서 반환된 항목을 미리 보거나 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-159">Preview or export the items returned by the ID list search.</span></span>

> [!NOTE]
> <span data-ttu-id="a36fd-160">ID 목록 검색을 만들고 나서 사서함을 이동하면 검색에 대한 쿼리가 지정된 항목을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-160">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="a36fd-161">사서함을 이동할 때 사서함 항목에 대한 **DocumentId** 속성이 변경되어 있기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-161">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="a36fd-162">ID 목록 검색을 만든 후 사서함이 이동되는 드물지만, 새 콘텐츠 검색을 만들거나 기존 콘텐츠 검색에 대한 검색 결과를 업데이트한 다음 검색 결과 또는 보고서를 내보내 새 ID 목록 검색을 만드는 데 사용할 수 있는 업데이트된 CSV 파일을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a36fd-162">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
