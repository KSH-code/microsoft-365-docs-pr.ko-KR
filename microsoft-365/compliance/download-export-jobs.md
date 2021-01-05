---
title: Advanced eDiscovery 사례에 대한 내보내기 작업 다운로드
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Azure Storage Explorer를 설치하고 사용하여 Advanced eDiscovery의 검토 집합에서 내보낼 문서를 다운로드합니다.
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751295"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="6ccee-103">Advanced eDiscovery 사례에서 내보내기 작업 다운로드</span><span class="sxs-lookup"><span data-stu-id="6ccee-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="6ccee-104">Advanced eDiscovery 사례의 검토 집합에서 문서를 내보내면 문서가 Microsoft 제공 Azure Storage 위치 또는 조직에서 관리하는 Azure Storage 위치로 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="6ccee-105">사용되는 Azure Storage 위치의 유형은 문서를 내보낼 때 선택한 옵션에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="6ccee-106">이 문서에서는 Microsoft Azure Storage Explorer를 사용하여 Azure Storage 위치에 연결하여 내보낼 문서를 찾아 다운로드하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="6ccee-107">Azure Storage Explorer에 대한 자세한 내용은 [빠른 시작: Azure 저장소 탐색기 사용을 참조하세요.](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="6ccee-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="6ccee-108">1단계: Azure 저장소 탐색기 설치</span><span class="sxs-lookup"><span data-stu-id="6ccee-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="6ccee-109">첫 번째 단계는 Azure 저장소 탐색기를 다운로드하여 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="6ccee-110">자세한 내용은 [Azure 저장소 탐색기 도구를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=544842)</span><span class="sxs-lookup"><span data-stu-id="6ccee-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="6ccee-111">이 도구를 사용하여 3단계에서 내보낼 문서에 연결하고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="6ccee-112">2단계: 내보내기 작업에서 SAS URL 얻기</span><span class="sxs-lookup"><span data-stu-id="6ccee-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="6ccee-113">다음 단계는 검토 집합에서 문서를 내보내기 위해 내보내기 작업을 만들 때 생성되는 SAS(공유 액세스 서명) [URL을 얻는 것입니다.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="6ccee-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="6ccee-114">조직에서 관리하는 Azure Storage 위치 또는 Microsoft 제공 Azure Storage 위치로 업로드되는 문서에 대한 SAS URL을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="6ccee-115">두 경우 모두 SAS URL을 사용하여 3단계의 Azure Storage 위치에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="6ccee-116">Advanced **eDiscovery** 페이지에서 사례로 이동한 다음 **내보내기 탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="6ccee-117">내보내기 **탭에서** 다운로드할 내보내기 작업을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="6ccee-118">플라이아웃 페이지의 **위치** 아래에서 표시되는 SAS URL을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="6ccee-119">필요한 경우 3단계에서 액세스할 수 있도록 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![위치 아래에 표시되는 SAS URL 복사](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="6ccee-121">3단계: Azure Storage 위치에 연결</span><span class="sxs-lookup"><span data-stu-id="6ccee-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="6ccee-122">마지막 단계는 Azure 저장소 탐색기 및 SAS URL을 사용하여 Azure Storage 위치에 연결하고 로컬 컴퓨터로 내보낼 문서를 다운로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="6ccee-123">1단계에서 설치한 Azure Storage Explorer를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="6ccee-124">계정 **추가 아이콘을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-124">Click the **Add account** icon.</span></span> <span data-ttu-id="6ccee-125">또는 저장소 계정을 마우스 오른쪽 단추로 **클릭할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6ccee-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![계정 추가 아이콘을 클릭합니다.](../media/AzureStorageConnect.png)

3. <span data-ttu-id="6ccee-127">Azure **Storage에 연결 페이지에서** **SAS(공유 액세스 서명) URI 사용 URI를** 클릭하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ccee-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![SAS(공유 액세스 서명) URI 사용 클릭하고 다음을 클릭합니다.](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="6ccee-129">**SAS URI로** 연결 페이지에서 URI 상자를 클릭한 다음 2단계에서 획득한 SAS URL을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![URI 상자에 SAS URL 붙여넣기](../media/AzureStorageConnect3.png)

    <span data-ttu-id="6ccee-131">SAS URL의 일부가 표시 이름 **상자에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6ccee-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="6ccee-132">이 이름은 저장소 위치에 연결한 후 **저장소** 계정 아래에 만들어진 컨테이너의 표시 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="6ccee-133">이 이름은 Advanced eDiscovery 사례의 ID와 고유 식별자로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="6ccee-134">기본 표시 이름을 유지하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="6ccee-135">이름을 변경하는 경우 표시 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="6ccee-136">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-136">Click **Next**.</span></span>

    <span data-ttu-id="6ccee-137">연결 **요약 페이지가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-137">The **Connection summary** page is displayed.</span></span>

    ![연결 요약 페이지에서 연결을 클릭하여 Azure Storage 위치에 연결](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="6ccee-139">연결 **요약 페이지에서** 연결 정보를 검토하고 연결 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ccee-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="6ccee-140">Blob **컨테이너** 노드(저장소   >  **계정(연결된 컨테이너) 아래)가** \> 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Blob 컨테이너 노드에서 작업 내보내기](../media/AzureStorageConnect5.png)

    <span data-ttu-id="6ccee-142">이 컨테이너에는 4단계의 표시 이름으로 이름이 지정된 컨테이너가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="6ccee-143">이 컨테이너에는 만든 각 내보내기 작업의 폴더가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="6ccee-144">이러한 폴더의 이름은 내보내기 작업의 ID에 해당하는 ID로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="6ccee-145">작업 탭에 나열된 각 내보내기 작업 준비  데이터에 대한 플라이아웃 페이지의  지원 정보에서 이러한 내보내기 ID(및 내보내기 이름)를 찾을 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="6ccee-146">내보내기 작업 폴더를 두 번 클릭하여 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="6ccee-147">폴더 및 내보내기 보고서 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-147">A list of folders and export reports is displayed.</span></span>
   
    ![내보내기 폴더에 내보낼 파일 및 내보내기 보고서가 포함되어 있습니다.](../media/AzureStorageConnect6.png)

   <span data-ttu-id="6ccee-149">내보내기 작업 폴더에는 다음 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-149">The export job folder contains the following items.</span></span> <span data-ttu-id="6ccee-150">내보내기 폴더의 실제 항목은 내보내기 작업을 만들 때 구성된 내보내기 옵션에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="6ccee-151">자세한 내용은 검토 집합에서 [문서 내보내기를 참조하세요.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="6ccee-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="6ccee-152">Export_load_file.csv: 이 CSV 파일은 내보낼 각 문서에 대한 정보가 포함된 세부 정보 내보내기 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="6ccee-153">파일은 문서의 각 메타데이터 속성에 대한 열로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="6ccee-154">이 보고서에 포함된 메타데이터의 목록 및 설명은 Advanced  [eDiscovery의](document-metadata-fields-in-advanced-ediscovery.md)문서 메타데이터 필드에 있는 표의 내보낼 필드 이름 열을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ccee-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="6ccee-155">Summary.txt: 내보내기 통계를 포함하는 내보내기 요약이 포함된 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="6ccee-156">Extracted_text_files: 이 폴더에는 내보낼 각 문서의 텍스트 파일 버전이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="6ccee-157">NativeFiles: 이 폴더에는 내보낼 각 문서의 기본 파일 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="6ccee-158">Error_files: 내보내기 작업에서 오류 파일이 포함된 경우 이 폴더에는 다음 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="6ccee-159">ExtractionError.csv: 이 CSV 파일에는 상위 항목에서 제대로 추출되지 않은 파일에 대한 사용 가능한 메타데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="6ccee-160">ProcessingError: 이 폴더에는 처리 오류가 있는 문서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="6ccee-161">이 콘텐츠는 항목 수준에 있습니다. 즉, 첨부 파일에 처리 오류가 있는 경우 첨부 파일이 포함된 문서도 이 폴더에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="6ccee-162">내보내기에서 모든 콘텐츠를 내보내려면 내보내기 폴더를 선택한 다음 다운로드를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ccee-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="6ccee-163">내보낼 파일을 다운로드할 위치를 지정하고 폴더 선택을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="6ccee-164">Azure 저장소 탐색기에서 내보내기 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="6ccee-165">내보낼 항목 다운로드 상태가 작업 **창에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="6ccee-166">다운로드가 완료되면 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-166">A message is displayed when the download is finished.</span></span>

    ![다운로드가 완료되면 메시지가 표시됩니다.](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="6ccee-168">전체 내보내기 작업을 다운로드하는 대신 다운로드할 특정 항목을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="6ccee-169">항목을 다운로드하는 대신 항목을 두 번 클릭하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccee-169">And instead of downloading items, you can double-click an item to view it.</span></span>
