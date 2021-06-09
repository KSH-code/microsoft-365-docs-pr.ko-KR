---
title: 조직의 Azure Storage 계정으로 문서 내보내기
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
ms.custom: seo-marvel-mar2020
description: 검토 집합에서 문서를 Azure Storage 계정으로 내보은 다음 Azure Storage Explorer 사용하여 로컬 컴퓨터에 다운로드합니다.
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574730"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a><span data-ttu-id="960fe-103">검토 집합의 문서를 Azure Storage 계정으로 내보내기</span><span class="sxs-lookup"><span data-stu-id="960fe-103">Export documents in a review set to an Azure Storage account</span></span>

<span data-ttu-id="960fe-104">Advanced eDiscovery 검토 집합에서 문서를 내보낼 때 조직에서 관리하는 Azure Storage 계정으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-104">When you export documents from a review set in an Advanced eDiscovery case, you have the option to export them to an Azure Storage account managed by your organization.</span></span> <span data-ttu-id="960fe-105">이 옵션을 사용하면 문서가 사용자 위치로 Azure Storage 됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-105">If you used this option, the documents are uploaded to your Azure Storage location.</span></span> <span data-ttu-id="960fe-106">내보낼 수 있는 문서는 다음을 사용하여 문서에 액세스하여 로컬 컴퓨터 또는 다른 위치에 다운로드할 수 Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="960fe-106">After they are exported, you can access the documents (and download them to a local computer or other location) by using the Azure Storage Explorer.</span></span> <span data-ttu-id="960fe-107">이 문서에서는 Azure Storage 계정으로 문서를 내보내고 Azure Storage Explorer 사용하여 내보낼 문서를 다운로드할 Azure Storage 위치에 연결하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-107">This article provides instructions for how to export documents to your Azure Storage account and the use the Azure Storage Explorer to connect to an Azure Storage location to download the exported documents.</span></span> <span data-ttu-id="960fe-108">자세한 내용은 Azure Storage Explorer [를 Azure Storage Explorer.](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="960fe-108">For more information about Azure Storage Explorer, see [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="before-you-export-documents-from-a-review-set"></a><span data-ttu-id="960fe-109">검토 집합에서 문서를 내보내기 전에</span><span class="sxs-lookup"><span data-stu-id="960fe-109">Before you export documents from a review set</span></span>

- <span data-ttu-id="960fe-110">검토 집합에서 문서를 내보내기 위해 Azure Storage 계정의 특정 컨테이너에 대한 URL과 SAS(공유 액세스 서명) 토큰을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-110">You need to provide a shared access signature (SAS) token for your Azure Storage account and the URL for a specific container in the storage account to export documents from a review set.</span></span> <span data-ttu-id="960fe-111">2단계를 수행할 때 이러한 작업을 준비해야 합니다(예: 텍스트 파일에 복사).</span><span class="sxs-lookup"><span data-stu-id="960fe-111">Be sure to have these at hand (for example, copied to a text file) when you perform Step 2</span></span>

  - <span data-ttu-id="960fe-112">**SAS 토큰: SAS** 토큰은 컨테이너가 아니라 Azure Storage 계정용입니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-112">**SAS token**: Be sure to get the SAS token is for your Azure Storage account (and not for the container).</span></span> <span data-ttu-id="960fe-113">계정의 SAS 토큰을 생성할 수 Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="960fe-113">You can generate an SAS token for your account in Azure Storage.</span></span> <span data-ttu-id="960fe-114">이렇게하려면 Azure Storage 계정으로 이동한 다음 저장소  계정 블레이드의 설정 설정에서 액세스 **서명** 공유를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-114">To do this, go to the Azure Storage account, and select **Share access signature** under the **Settings** settings in the storage account blade.</span></span> <span data-ttu-id="960fe-115">기본 설정을 사용하여 SAS 토큰을 생성할 때 모든 리소스 유형을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-115">Use the default settings and allow all resource types when you generate the SAS token.</span></span>

  - <span data-ttu-id="960fe-116">**컨테이너 URL:** 검토 집합 문서를 업로드한 다음 컨테이너의 URL 복사본을 다운로드할 컨테이너를 만들어야 합니다. 예를 들면 `https://ediscoverydata.blob.core.windows.net/exportdata` 입니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-116">**Container URL**: You need to create a container to upload the review set documents to, and then get a copy of the URL for the container; for example, `https://ediscoverydata.blob.core.windows.net/exportdata`.</span></span> <span data-ttu-id="960fe-117">URL을 얻습니다. Azure Storage 컨테이너 블레이드의 설정  **섹션에서** 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-117">To get the URL, go to the container in Azure Storage, and select **Properties** under the **Settings** section in the container blade.</span></span>

- <span data-ttu-id="960fe-118">설치 프로그램을 다운로드하여 Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="960fe-118">Download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="960fe-119">자세한 내용은 Azure Storage Explorer [참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=544842)</span><span class="sxs-lookup"><span data-stu-id="960fe-119">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="960fe-120">이 도구를 사용하여 Azure Storage 계정의 컨테이너에 연결하고 1단계에서 내보낼 문서를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-120">You use this tool to connect to the container in your Azure Storage account and download the documents that you exported in Step 1.</span></span>

## <a name="step-1-export-the-documents-from-a-review-set"></a><span data-ttu-id="960fe-121">1단계: 검토 집합에서 문서 내보내기</span><span class="sxs-lookup"><span data-stu-id="960fe-121">Step 1: Export the documents from a review set</span></span>

<span data-ttu-id="960fe-122">첫 번째 단계는 검토 집합에서 문서를 내보내는 내보내기 작업을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-122">The first step is to create an export job to export documents out of a review set.</span></span> <span data-ttu-id="960fe-123">모든 내보내기 옵션에 대한 자세한 지침은 검토 집합에서 문서 [내보내기 를 참조하세요.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="960fe-123">For more detailed instructions about all the export options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="960fe-124">다음 절차에서는 문서를 조직의 계정으로 내보내기 위한 설정을 Azure Storage 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-124">The following procedure highlights the settings to export documents to your organization's Azure Storage account.</span></span>

1. <span data-ttu-id="960fe-125">준수 Microsoft 365 센터에서 Advanced eDiscovery 사례를 열고 검토 집합  탭을 선택한 다음 내보낼 검토 집합을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-125">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="960fe-126">검토 집합에서 작업 **내보내기 를**  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="960fe-126">In the review set, click **Action** > **Export**.</span></span>

3. <span data-ttu-id="960fe-127">내보내기 **옵션** 플라이아웃 페이지에서 내보내기 이름(필수) 및 설명(선택 사항)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-127">On the **Export options** flyout page, type a name (required) and description (optional) for the export.</span></span>

4. <span data-ttu-id="960fe-128">문서, 메타데이터, 콘텐츠 및 옵션 섹션의 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-128">Configure the settings in the documents, metadata, content, and options sections.</span></span> <span data-ttu-id="960fe-129">이러한 설정에 대한 자세한 내용은 [검토 집합에서 문서 내보내기 를 참조하세요.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="960fe-129">For more information about these settings, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

5. <span data-ttu-id="960fe-130">출력 **옵션 섹션에서** 계정으로 내보낼 압축된 디렉터리 Azure Storage **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="960fe-130">In the **Output options** section, select the **Condensed directory structure exported to your Azure Storage account** option.</span></span>

6. <span data-ttu-id="960fe-131">저장소 계정의 컨테이너 URL과 SAS 토큰을 해당 필드에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-131">Paste the container URL and the SAS token for your storage account in the corresponding fields.</span></span>

   ![해당 필드에 연결 URL 및 SAS 토큰 붙여넣기](../media/AzureStorageOutputOptions.png)

7. <span data-ttu-id="960fe-133">내보내기 **를** 클릭하여 내보내기 작업을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-133">Click **Export** to create the export job.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="960fe-134">2단계: 내보내기 작업에서 SAS URL 얻기</span><span class="sxs-lookup"><span data-stu-id="960fe-134">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="960fe-135">다음 단계는 1단계에서 내보내기 작업을 만든 후 생성되는 SAS URL을 얻는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-135">The next step is to obtain the SAS URL that's generated after you create the export job in Step 1.</span></span> <span data-ttu-id="960fe-136">SAS URL을 사용하여 검토 집합 문서를 내보낼 Azure Storage 계정의 컨테이너에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-136">You use the SAS URL to connect to the container in your Azure Storage account that you exported the review set documents to.</span></span>

1. <span data-ttu-id="960fe-137">페이지 **Advanced eDiscovery** 사례로 이동한 다음 내보내기 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-137">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="960fe-138">**내보내기** 탭에서 다운로드하려는 내보내기 작업을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-138">On the **Exports** tab, click the export job that you want to download.</span></span> <span data-ttu-id="960fe-139">1단계에서 만든 내보내기 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-139">This is the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="960fe-140">플라이아웃 페이지의 **위치** 아래에서 표시되는 SAS URL을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-140">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="960fe-141">필요한 경우 3단계에서 액세스할 수 있도록 텍스트 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-141">If necessary, you can save it to a text file so you can access it in Step 3.</span></span>

   ![위치에 표시되는 SAS URL 복사](../media/eDiscoExportJob.png)

   > [!TIP]
   > <span data-ttu-id="960fe-143">내보내기 작업에서 표시되는 SAS URL은 컨테이너 URL과 사용자 계정의 SAS 토큰을 Azure Storage 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-143">The SAS URL that's displayed in the export job is a concatenation of the container URL and the SAS token for your Azure Storage account.</span></span> <span data-ttu-id="960fe-144">내보내기 작업에서 복사하거나 URL과 SAS 토큰을 결합하여 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-144">You can copy it from the export job or create it yourself by combining the URL and the SAS token.</span></span>

## <a name="step-3-connect-to-the-azure-storage-container"></a><span data-ttu-id="960fe-145">3단계: 커넥트 컨테이너에 Azure Storage 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-145">Step 3: Connect to the Azure Storage container</span></span>

<span data-ttu-id="960fe-146">마지막 단계는 Azure Storage Explorer 및 SAS URL을 사용하여 Azure Storage 계정의 컨테이너에 연결하고 내보낼 문서를 로컬 컴퓨터에 다운로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-146">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the container in your Azure Storage account and download the exported documents to a local computer.</span></span>

1. <span data-ttu-id="960fe-147">다운로드하여 Azure Storage Explorer 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-147">Start the Azure Storage Explorer that you downloaded and installed.</span></span>

2. <span data-ttu-id="960fe-148">열기 **대화 커넥트 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="960fe-148">Click the **Open Connect Dialog** icon.</span></span>

   ![계정 추가 아이콘을 클릭합니다.](../media/AzureStorageConnect.png)

3. <span data-ttu-id="960fe-150">시작 **커넥트 Azure Storage** Blob 컨테이너 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="960fe-150">On the **Connect to Azure Storage** page, click **Blob container**.</span></span>

4. <span data-ttu-id="960fe-151">인증 **방법 선택 페이지에서** **SAS(공유 액세스 서명)** 옵션을 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="960fe-151">On the **Select Authentication Method** page, select the **Shared access signature (SAS)** option and then click **Next**.</span></span>

5. <span data-ttu-id="960fe-152">연결 **정보 입력 페이지의** Blob 컨테이너 SAS URL 상자에 2단계의 내보내기 작업에서 획득한 **SAS URL을 붙여 넣습니다.**</span><span class="sxs-lookup"><span data-stu-id="960fe-152">On the **Enter Connection Info** page, paste the SAS URL (that you obtained in the export job in Step 2) in the **Blob Container SAS URL** box.</span></span>

    ![URI 상자에 SAS URL 붙여넣기](../media/AzureStorageConnect3.png)

    <span data-ttu-id="960fe-154">표시 이름 상자에 컨테이너 **이름이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-154">Notice that the container name is displayed in the **Display name** box.</span></span> <span data-ttu-id="960fe-155">이 이름을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-155">You can edit this name.</span></span>

6. <span data-ttu-id="960fe-156">다음을 클릭하여 요약 페이지를 **표시한** 다음 를 **커넥트.** </span><span class="sxs-lookup"><span data-stu-id="960fe-156">Click **Next** to display the **summary** page and then click **Connect**.</span></span>

    <span data-ttu-id="960fe-157">Blob **컨테이너** 노드(Storage **계정(연결된**  >  **컨테이너)가 열립니다.** \></span><span class="sxs-lookup"><span data-stu-id="960fe-157">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Blobs 컨테이너 노드에서 작업 내보내기](../media/AzureStorageConnect5.png)

    <span data-ttu-id="960fe-159">5단계의 표시 이름으로 이름이 인 컨테이너가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-159">It contains a container named with the display name from step 5.</span></span> <span data-ttu-id="960fe-160">이 컨테이너에는 사용자 계정의 컨테이너로 다운로드한 각 내보내기 작업의 폴더가 Azure Storage 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-160">This container contains a folder for each export job that you've downloaded to the container in your Azure Storage account.</span></span> <span data-ttu-id="960fe-161">이러한 폴더의 이름은 내보내기 작업의 ID에 해당하는 ID로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-161">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="960fe-162">이러한 내보내기 ID(및 내보내기 이름)는  작업 사례의 작업 탭에 나열된 각 내보내기  작업 준비 작업의 플라이아웃 페이지의 지원 정보에서 Advanced eDiscovery 있습니다. </span><span class="sxs-lookup"><span data-stu-id="960fe-162">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab in the Advanced eDiscovery case.</span></span>

7. <span data-ttu-id="960fe-163">내보내기 작업 폴더를 두 번 클릭하여 열립니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-163">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="960fe-164">폴더 및 내보내기 보고서 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-164">A list of folders and export reports is displayed.</span></span>

    ![내보내기 폴더에 내보낼 파일 및 내보내기 보고서가 포함되어 있습니다.](../media/AzureStorageConnect6.png)

8. <span data-ttu-id="960fe-166">내보내기 작업에서 모든 콘텐츠를 내보내려면  위쪽 화살표를 클릭하여 내보내기 작업 폴더로 돌아가 다운로드를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="960fe-166">To export all contents from the export job, click the **Up** arrow to go back to the export job folder, and then click **Download**.</span></span>

9. <span data-ttu-id="960fe-167">내보낸 파일을 다운로드할 위치를 지정한 다음 폴더 선택을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-167">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="960fe-168">이 Azure Storage Explorer 다운로드 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-168">The Azure Storage Explorer starts the download process.</span></span> <span data-ttu-id="960fe-169">내보낼 항목 다운로드의 상태가 활동 **창에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-169">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="960fe-170">다운로드가 완료되면 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-170">A message is displayed when the download is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="960fe-171">전체 내보내기 작업을 Azure Storage Explorer 다운로드하고 볼 특정 항목을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-171">Instead of downloading the entire export job in Azure Storage Explorer, you can select specific items to download and view.</span></span>

## <a name="more-information"></a><span data-ttu-id="960fe-172">추가 정보</span><span class="sxs-lookup"><span data-stu-id="960fe-172">More information</span></span>

- <span data-ttu-id="960fe-173">내보내기 작업 폴더에는 다음 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-173">The export job folder contains the following items.</span></span> <span data-ttu-id="960fe-174">내보내기 폴더의 실제 항목은 내보내기 작업을 만들 때 구성된 내보내기 옵션에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-174">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="960fe-175">이러한 옵션에 대한 자세한 내용은 [검토 집합에서 문서 내보내기 를 참조하세요.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="960fe-175">For more information about these options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

  - <span data-ttu-id="960fe-176">Export_load_file.csv: 이 CSV 파일은 내보낼 각 문서에 대한 정보를 포함하는 세부 정보 내보내기 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-176">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="960fe-177">파일은 문서의 각 메타데이터 속성에 대한 열로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-177">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="960fe-178">이 보고서에 포함된 메타데이터의 목록 및 설명은 의  문서 메타데이터 필드에 있는 표의 내보낼 필드 이름 [열을 Advanced eDiscovery.](document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="960fe-178">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>

  - <span data-ttu-id="960fe-179">Summary.txt: 내보내기 통계를 포함하여 내보내기 요약이 포함된 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-179">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>

  - <span data-ttu-id="960fe-180">Extracted_text_files: 이 폴더에는 내보낼 각 문서의 텍스트 파일 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-180">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>

  - <span data-ttu-id="960fe-181">NativeFiles: 이 폴더에는 내보낼 각 문서의 기본 파일 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-181">NativeFiles: This folder contains a native file version of each exported document.</span></span>

  - <span data-ttu-id="960fe-182">Error_files: 내보내기 작업에서 오류 파일이 포함된 경우 이 폴더에는 다음 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-182">Error_files: This folder includes the following items when the export job contains any error files:</span></span>

    - <span data-ttu-id="960fe-183">ExtractionError.csv: 이 CSV 파일에는 상위 항목에서 제대로 추출되지 않은 파일에 대한 사용 가능한 메타데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-183">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>

    - <span data-ttu-id="960fe-184">ProcessingError: 이 폴더에는 처리 오류가 있는 문서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-184">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="960fe-185">이 콘텐츠는 항목 수준에 있습니다. 즉, 첨부 파일에 처리 오류가 있는 경우 첨부 파일이 포함된 문서도 이 폴더에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="960fe-185">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
