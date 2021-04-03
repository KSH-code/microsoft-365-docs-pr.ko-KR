---
title: 검토 집합에서 문서 내보내기
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
ms.assetid: ''
description: 프레젠테이션 또는 외부 검토를 위해 고급 eDiscovery 검토 집합에서 콘텐츠를 선택하고 내보내는 방법을 학습합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581026"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="907f7-103">Advanced eDiscovery의 검토 집합에서 문서 내보내기</span><span class="sxs-lookup"><span data-stu-id="907f7-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="907f7-104">내보내기 기능을 사용하면 Advanced eDiscovery의 검토 집합에서 문서를 내보낼 때 다운로드 패키지에 포함된 콘텐츠를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="907f7-105">검토 집합에서 문서를 내보내는 경우:</span><span class="sxs-lookup"><span data-stu-id="907f7-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="907f7-106">Microsoft 365 규정 준수 센터에서 고급 eDiscovery  사례를 열고 검토 집합 탭을 선택한 다음 내보낼 검토 집합을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="907f7-107">검토 집합에서 작업 **내보내기 를**  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="907f7-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="907f7-108">내보내기 도구에는 내보내기 구성 설정이 있는 플라이아웃 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="907f7-109">일부 옵션은 기본적으로 선택되지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="907f7-110">구성할 수 있는 내보내기 옵션에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="907f7-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![검토 집합에서 항목을 내보내기 위한 구성 옵션](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="907f7-112">내보내기 구성 후 **내보내기** 를 클릭하여 내보내기 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="907f7-113">출력 옵션 섹션에서 선택한  옵션에 따라 직접 다운로드 또는 조직의 Azure Storage 계정으로 내보내기 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="907f7-114">내보내기 작업은 사례의 수명 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="907f7-115">그러나 내보내기 작업이 완료된 후 30일 이내에 내보내기 작업에서 콘텐츠를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="907f7-116">내보내기 옵션</span><span class="sxs-lookup"><span data-stu-id="907f7-116">Export options</span></span>

<span data-ttu-id="907f7-117">다음 옵션을 사용하여 내보내기 구성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="907f7-118">**내보내기 이름:** 내보내기 작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="907f7-119">**설명:** 설명을 추가할 수 있는 자유 텍스트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="907f7-120">**다음 문서 내보내기**</span><span class="sxs-lookup"><span data-stu-id="907f7-120">**Export these documents**</span></span>

  - <span data-ttu-id="907f7-121">**선택한 문서만:** 이 옵션은 현재 선택된 문서만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="907f7-122">**검토 집합의** 모든 문서: 이 옵션은 검토 집합의 모든 문서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="907f7-123">**메타 데이터**</span><span class="sxs-lookup"><span data-stu-id="907f7-123">**Metadata**</span></span>
  
  - <span data-ttu-id="907f7-124">**파일 로드:** 이 파일에는 각 파일에 대한 메타데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="907f7-125">이 파일은 일반적으로 타사 eDiscovery 도구에서 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="907f7-126">포함된 필드에 대한 자세한 내용은 [Advanced eDiscovery의 문서 메타데이터 필드를 참조하세요.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="907f7-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="907f7-127">**태그:** 태그 지정 정보를 선택하면 로드 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="907f7-128">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="907f7-128">**Content**</span></span>
  
  - <span data-ttu-id="907f7-129">**기본 파일:** 검토 집합에 문서의 기본 파일을 포함하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="907f7-130">기본 파일을 내보내는 경우 채팅 대화 내보내기 방법에 대한 다음 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="907f7-131">**대화 옵션**</span><span class="sxs-lookup"><span data-stu-id="907f7-131">**Conversation options**</span></span>

    - <span data-ttu-id="907f7-132">**대화 파일:** 이 옵션은 재구성된 채팅 대화를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="907f7-133">이 형식은 기본 응용 프로그램에서 사용자에게 표시하는 모양과 같은 형식으로 대화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="907f7-134">**개별 채팅 메시지:** 이 옵션은 Microsoft 365에 저장된 원래 대화 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="907f7-135">**옵션**</span><span class="sxs-lookup"><span data-stu-id="907f7-135">**Options**</span></span>

  - <span data-ttu-id="907f7-136">**텍스트 파일:**- 이 옵션에는 내보내기에서 추출된 네이티브 파일의 텍스트 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="907f7-137">**편집된** 네이티브를 변환된 PDF로 바꾸기: 검토 중에 편집된 PDF 파일이 생성되는 경우 이러한 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="907f7-138">이 옵션을 선택하지 않은 경우, 편집된 기본 파일만 내보내거나 실제 변경이 포함된 PDF 파일을 내보내기 위해 이 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="907f7-139">**출력 옵션:** 내보낼 콘텐츠는 웹 브라우저를 통해 직접 다운로드할 수 있습니다. 또는 Azure Storage 계정으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="907f7-140">처음 두 옵션을 사용하면 직접 다운로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="907f7-141">느슨한 파일 및 PSTS(가능한 경우 전자 메일이 **PSTS에 추가)**: 파일은 기본 응용 프로그램에서 사용자가 볼 수 있는 원래 디렉터리 구조와 같은 형식으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="907f7-142">자세한 내용은 느슨한 파일 및 [PST 내보내기](#loose-files-and-pst-export-structure) 구조 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="907f7-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="907f7-143">**압축된 디렉터리 구조:** 파일을 내보내고 다운로드에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="907f7-144">**Azure Storage** 계정으로 내보낼 압축된 디렉터리 구조: 파일이 조직의 Azure Storage 계정으로 내보내기됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="907f7-145">이 옵션의 경우 파일을 내보낼 Azure Storage 계정의 컨테이너 URL을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="907f7-146">Azure Storage 계정에 대한 SAS(공유 액세스 서명) 토큰도 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="907f7-147">자세한 내용은 검토 집합의 문서를 [Azure Storage 계정으로 내보내기를 참조하세요.](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="907f7-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="907f7-148">다음 섹션에서는 느슨한 파일 및 압축된 디렉터리 구조 옵션에 대한 폴더 구조에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="907f7-149">느슨한 파일 및 PST 내보내기 구조</span><span class="sxs-lookup"><span data-stu-id="907f7-149">Loose files and PST export structure</span></span>

<span data-ttu-id="907f7-150">이 내보내기 옵션을 선택하면 내보낼 콘텐츠가 다음 구조로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="907f7-151">루트 폴더: 이름이 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="907f7-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="907f7-152">Export_load_file.csv: 메타데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="907f7-153">Summary.csv: 내보내기 통계도 포함하는 요약 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="907f7-154">Exchange: 이 폴더에는 Exchange의 모든 콘텐츠가 기본 파일 형식으로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="907f7-155">변환된 네이티브를 변환된 **PDF로** 바꾸기 옵션을 선택한 경우 네이티브 파일은 재조정된 PDF로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="907f7-156">SharePoint: 이 폴더에는 SharePoint의 모든 기본 콘텐츠가 기본 파일 형식으로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="907f7-157">변환된 네이티브를 변환된 **PDF로** 바꾸기 옵션을 선택한 경우 네이티브 파일은 재조정된 PDF로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="907f7-158">압축된 디렉터리 구조</span><span class="sxs-lookup"><span data-stu-id="907f7-158">Condensed directory structure</span></span>

- <span data-ttu-id="907f7-159">루트 폴더: 이 폴더의 이름은 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="907f7-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="907f7-160">Export_load_file.csv: 메타데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="907f7-161">Summary.txt: 내보내기 통계도 포함하는 요약 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="907f7-162">NativeFiles: 이 폴더에는 내보낼 수 있는 모든 기본 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="907f7-163">편집된 PDF 파일을 내보낼 경우 PST 파일에 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="907f7-164">대신 별도의 폴더에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="907f7-165">Error_files: 내보내기에 포함된 경우 이 폴더에 다음 오류 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="907f7-166">ExtractionError: 상위 파일에서 제대로 추출되지 않은 파일의 사용 가능한 메타데이터가 포함된 CSV 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="907f7-167">ProcessingError: 이 파일에는 처리 오류가 있는 문서 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="907f7-168">이 콘텐츠는 항목 수준으로, 첨부 파일에서 처리 오류가 발생하는 경우 첨부 파일이 포함된 전자 메일 메시지가 이 폴더에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="907f7-169">Extracted_text_files: 이 폴더에는 처리 시 생성된 추출된 텍스트 파일이 모두 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907f7-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
