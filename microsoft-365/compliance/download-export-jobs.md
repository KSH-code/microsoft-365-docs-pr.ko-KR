---
title: 고급 eDiscovery 사례에 대 한 내보내기 작업 다운로드
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
description: Advanced eDiscovery의 검토 집합에서 내보낸 문서를 Azure 저장소 탐색기를 설치 하 고 사용 하 여 다운로드 합니다.
ms.openlocfilehash: 4b09521b4a72fc8fda68f5892c899fe76a066809
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399165"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="93adb-103">고급 eDiscovery 사례에서 내보내기 작업 다운로드</span><span class="sxs-lookup"><span data-stu-id="93adb-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="93adb-104">고급 eDiscovery 사례의 검토 집합에서 문서를 내보낼 때 문서는 Microsoft에서 제공한 Azure 저장소 위치 또는 조직에서 관리 하는 Azure 저장소 위치에 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="93adb-105">사용 되는 Azure Storage location 유형은 문서를 내보낼 때 선택한 옵션에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="93adb-106">이 문서에서는 Microsoft Azure Storage Explorer를 사용 하 여 Azure 저장소 위치에 연결 하 여 내보낸 문서를 찾아보고 다운로드 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="93adb-107">Azure Storage Explorer에 대 한 자세한 내용은 [빠른 시작: Azure Storage Explorer 사용](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93adb-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="93adb-108">1 단계: Azure Storage Explorer 설치</span><span class="sxs-lookup"><span data-stu-id="93adb-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="93adb-109">첫 번째 단계는 Azure Storage Explorer를 다운로드 하 여 설치 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="93adb-110">자세한 내용은 [Azure Storage Explorer 도구](https://go.microsoft.com/fwlink/p/?LinkId=544842)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93adb-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="93adb-111">이 도구를 사용 하 여 3 단계에서 내보낸 문서에 연결 하 고 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="93adb-112">2 단계: 내보내기 작업에서 SAS URL 가져오기</span><span class="sxs-lookup"><span data-stu-id="93adb-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="93adb-113">다음 단계에서는 [검토 집합에서 문서를 내보내기](export-documents-from-review-set.md)위해 내보내기 작업을 만들 때 생성 되는 SAS (공유 액세스 서명) URL을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="93adb-114">Microsoft에서 제공한 Azure 저장소 위치 또는 조직에서 관리 하는 Azure 저장소 위치에 업로드 된 문서에 대 한 SAS URL을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="93adb-115">두 경우 모두 SAS URL을 사용 하 여 3 단계에서 Azure 저장소 위치에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="93adb-116">**고급 eDiscovery** 페이지에서 사례로 이동한 후 **내보내기** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="93adb-117">**내보내기 탭에서** 다운로드 하려는 내보내기 작업을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="93adb-118">플라이 아웃 페이지의 **위치**아래에 표시 된 SAS URL을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="93adb-119">필요한 경우 3 단계에서 액세스할 수 있도록 파일을 파일로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![위치 아래에 표시 된 SAS URL 복사](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="93adb-121">3 단계: Azure 저장소 위치에 연결</span><span class="sxs-lookup"><span data-stu-id="93adb-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="93adb-122">마지막 단계에서는 Azure Storage Explorer와 SAS URL을 사용 하 여 Azure 저장소 위치에 연결 하 고 내보낸 문서를 로컬 컴퓨터로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="93adb-123">1 단계에서 설치한 Azure Storage Explorer를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="93adb-124">**계정 추가** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-124">Click the **Add account** icon.</span></span> <span data-ttu-id="93adb-125">또는 **저장소 계정을**마우스 오른쪽 단추로 클릭 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![계정 추가 아이콘을 클릭 합니다.](../media/AzureStorageConnect.png)

3. <span data-ttu-id="93adb-127">**Azure Storage에 연결** 페이지에서 **SAS (공유 액세스 서명) URI 사용** 을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![SAS (공유 액세스 서명) URI 사용을 클릭 한 후 다음을 클릭 합니다.](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="93adb-129">**SAS URI로 연결** 페이지에서 URI 상자를 클릭 한 다음 2 단계에서 얻은 SAS URL을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![URI 상자에 SAS URL을 붙여 넣습니다.](../media/AzureStorageConnect3.png)

    <span data-ttu-id="93adb-131">**표시 이름** 상자에 SAS URL의 일부가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="93adb-132">이 이름은 저장소 위치에 연결한 후 **저장소 계정** 에 만들어지는 컨테이너의 표시 이름으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="93adb-133">이 이름은 Advanced eDiscovery 사례의 ID와 고유 식별자로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="93adb-134">기본 표시 이름을 그대로 유지 하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="93adb-135">이름을 변경 하는 경우에는 표시 이름이 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="93adb-136">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-136">Click **Next**.</span></span>

    <span data-ttu-id="93adb-137">**연결 요약** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-137">The **Connection summary** page is displayed.</span></span>

    ![연결 요약 페이지에서 연결을 클릭 하 여 Azure 저장소 위치에 연결 합니다.](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="93adb-139">**연결 요약** 페이지에서 연결 정보를 검토 한 다음 **연결**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="93adb-140">**Blob 컨테이너** 노드 ( **저장소 계정**  >  **(연결 된 컨테이너))** \> 가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Blob 컨테이너 노드의 작업 내보내기](../media/AzureStorageConnect5.png)

    <span data-ttu-id="93adb-142">여기에는 4 단계의 표시 이름으로 이름이 지정 된 컨테이너가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="93adb-143">이 컨테이너에는 사용자가 만든 각 내보내기 작업에 대 한 폴더가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="93adb-144">이러한 폴더는 내보내기 작업의 ID에 해당 하는 ID로 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="93adb-145">**작업** 탭에 나열 된 각 **내보내기 데이터 준비** 작업에 대 한 플라이 아웃 페이지의 **지원 정보** 아래에서 이러한 내보내기 id와 내보내기 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="93adb-146">내보내기 작업 폴더를 두 번 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="93adb-147">폴더 및 내보내기 보고서 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-147">A list of folders and export reports is displayed.</span></span>
   
    ![내보내기 폴더에는 내보낸 파일 및 내보내기 보고서가 포함 되어 있습니다.](../media/AzureStorageConnect6.png)

   <span data-ttu-id="93adb-149">내보내기 작업 폴더에는 다음과 같은 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-149">The export job folder contains the following items.</span></span> <span data-ttu-id="93adb-150">내보내기 폴더의 실제 항목은 내보내기 작업을 만들 때 구성 된 내보내기 옵션에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="93adb-151">자세한 내용은 [문서를 검토 집합에서 내보내기를](export-documents-from-review-set.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93adb-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="93adb-152">Export_load_file.csv:이 CSV 파일은 내보낸 각 문서에 대 한 정보를 포함 하는 세부 내보내기 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="93adb-153">이 파일은 문서에 대 한 각 metadata 속성의 열로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="93adb-154">이 보고서에 포함 된 메타 데이터의 목록 및 설명에 대 한 자세한 내용은 [Advanced eDiscovery의 문서 메타 데이터 필드](document-metadata-fields.md)에 있는 표에서 **내보낸 필드 이름** 열을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93adb-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields.md).</span></span>
    
    - <span data-ttu-id="93adb-155">Summary.txt: 내보내기 통계를 포함 하는 내보내기 요약이 포함 된 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="93adb-156">Extracted_text_files:이 폴더에는 내보낸 각 문서의 텍스트 파일 버전이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="93adb-157">NativeFiles:이 폴더에는 내보낸 각 문서의 네이티브 파일 버전이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="93adb-158">Error_files:이 폴더에는 내보내기 작업에 오류 파일이 포함 된 경우 다음 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="93adb-159">ExtractionError.csv:이 CSV 파일에는 부모 항목에서 올바르게 추출 되지 않은 파일에 대 한 사용 가능한 메타 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="93adb-160">ProcessingError:이 폴더에는 처리 오류가 있는 문서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="93adb-161">이 콘텐츠는 항목 수준으로, 첨부 파일에 처리 오류가 있는 경우 첨부 파일이 들어 있는 문서도이 폴더에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="93adb-162">내보내기에서 모든 콘텐츠를 내보내려면 내보내기 폴더를 선택 하 고 **다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="93adb-163">내보낸 파일을 다운로드 하려는 위치를 지정 하 고 폴더 선택을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="93adb-164">Azure Storage Explorer가 내보내기 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="93adb-165">내보낸 항목을 다운로드 하는 상태가 **활동** 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="93adb-166">다운로드가 완료 되 면 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-166">A message is displayed when the download is finished.</span></span>

    ![다운로드가 완료 되 면 메시지가 표시 됨](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="93adb-168">전체 내보내기 작업을 다운로드 하는 대신 특정 항목을 선택 하 여 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="93adb-169">항목을 다운로드 하는 대신 항목을 두 번 클릭 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93adb-169">And instead of downloading items, you can double-click an item to view it.</span></span>
