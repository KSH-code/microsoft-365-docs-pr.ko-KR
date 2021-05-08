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
description: 프레젠테이션 또는 외부 검토에 대한 Advanced eDiscovery 콘텐츠 선택 및 내보내기 방법에 대해 자세히 알아보겠습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 76865ae92d3b3090ae2bba01c9b3e9e0f1f86366
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244364"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="3841c-103">문서의 검토 집합에서 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3841c-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="3841c-104">내보내기에서는 사용자가 다운로드 패키지의 검토 집합에서 문서를 내보낼 때 다운로드 패키지에 포함된 콘텐츠를 사용자 지정할 수 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3841c-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="3841c-105">검토 집합에서 문서를 내보내는 경우:</span><span class="sxs-lookup"><span data-stu-id="3841c-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="3841c-106">준수 Microsoft 365 센터에서 Advanced eDiscovery 사례를 열고 검토 집합  탭을 선택한 다음 내보낼 검토 집합을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="3841c-107">검토 집합에서 작업 **내보내기 를**  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3841c-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="3841c-108">내보내기 도구에는 내보내기 구성 설정이 있는 플라이아웃 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="3841c-109">일부 옵션은 기본적으로 선택되지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="3841c-110">구성할 수 있는 내보내기 옵션에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3841c-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![검토 집합에서 항목을 내보내기 위한 구성 옵션](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="3841c-112">내보내기 구성 후 **내보내기** 를 클릭하여 내보내기 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="3841c-113">출력 옵션 섹션에서 선택한  옵션에 따라 직접 다운로드 또는 조직의 Azure Storage 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="3841c-114">내보내기 작업은 사례의 수명 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="3841c-115">그러나 내보내기 작업이 완료된 후 30일 이내에 내보내기 작업에서 콘텐츠를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="3841c-116">내보내기 옵션</span><span class="sxs-lookup"><span data-stu-id="3841c-116">Export options</span></span>

<span data-ttu-id="3841c-117">다음 옵션을 사용하여 내보내기 구성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-117">Use the following options to configure the export.</span></span> <span data-ttu-id="3841c-118">일부 출력 옵션에 대해 일부 옵션이 허용되지는 않습니다. 특히 PST 형식으로 내보낼 때 텍스트 파일 및 편집된 PDF의 내보내기가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-118">Not all options are allowed for some output options, most notably, export of text files and redacted PDFs are not allowed when exporting to the PST format.</span></span>

- <span data-ttu-id="3841c-119">**내보내기 이름:** 내보내기 작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-119">**Export name**: Name of the export job.</span></span> <span data-ttu-id="3841c-120">이 이름은 다운로드할 ZIP 파일의 이름을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-120">This will be used to name the ZIP files that will be downloaded.</span></span>

- <span data-ttu-id="3841c-121">**설명:** 설명을 추가할 수 있는 자유 텍스트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-121">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="3841c-122">**다음 문서 내보내기**</span><span class="sxs-lookup"><span data-stu-id="3841c-122">**Export these documents**</span></span>

  - <span data-ttu-id="3841c-123">선택한 문서만: 이 옵션은 현재 선택된 문서만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-123">Selected documents only: This option exports only the documents that are currently selected.</span></span> <span data-ttu-id="3841c-124">이 옵션은 검토 집합에서 항목을 선택할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-124">This option is only available when items are selected in a review set.</span></span>
  - <span data-ttu-id="3841c-125">필터링된 모든 문서: 이 옵션은 활성 필터에서 문서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-125">All filtered documents: This option exports the documents in an active filter.</span></span> <span data-ttu-id="3841c-126">이 옵션은 필터가 검토 집합에 적용될 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-126">This option is only available when a filter is applied to the review set.</span></span>
  - <span data-ttu-id="3841c-127">검토 집합의 모든 문서: 이 옵션은 검토 집합의 모든 문서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-127">All documents in the review set: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="3841c-128">**출력 옵션:** 내보낼 콘텐츠는 웹 브라우저를 통해 직접 다운로드할 수 있습니다. 또는 내보낼 콘텐츠가 Azure Storage 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-128">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="3841c-129">처음 두 옵션을 사용하면 직접 다운로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-129">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="3841c-130">보고서만: 요약 및 로드 파일만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-130">Reports only: Only the summary and load file are created.</span></span>
  - <span data-ttu-id="3841c-131">느슨한 파일 및 PSTS(가능한 경우 전자 메일이 PSTS에 추가됨): 파일은 기본 응용 프로그램에서 사용자가 볼 수 있는 원래 디렉터리 구조와 같은 형식으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-131">Loose files and PSTs (email is added to PSTs when possible): Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="3841c-132">자세한 내용은 느슨한 파일 및 [PST 내보내기](#loose-files-and-pst-export-structure) 구조 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3841c-132">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  - <span data-ttu-id="3841c-133">압축된 디렉터리 구조: 파일을 내보내고 다운로드에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-133">Condensed directory structure: Files are exported and included in the download.</span></span>
  - <span data-ttu-id="3841c-134">조직 계정으로 내보낼 압축된 디렉터리 Azure Storage: 파일은 조직의 Azure Storage 계정으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-134">Condensed directory structure exported to your Azure Storage account: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="3841c-135">이 옵션의 경우 파일을 내보낼 Azure Storage 컨테이너의 URL을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-135">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="3841c-136">또한 사용자 계정의 SAS(공유 액세스 서명) 토큰을 Azure Storage 합니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-136">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="3841c-137">자세한 내용은 검토 집합의 문서 내보내기 계정을 Azure Storage [참조하세요.](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="3841c-137">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

- <span data-ttu-id="3841c-138">**포함**</span><span class="sxs-lookup"><span data-stu-id="3841c-138">**Include**</span></span>
  - <span data-ttu-id="3841c-139">태그: 이 옵션을 선택하면 태그 지정 정보가 로드 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-139">Tags: When selected, tagging information is included in the load file.</span></span>
  - <span data-ttu-id="3841c-140">텍스트 파일: 이 옵션에는 내보내기에서 추출된 네이티브 파일의 텍스트 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-140">Text files: This option includes the extracted text versions of native files in the export.</span></span>
  - <span data-ttu-id="3841c-141">편집된 네이티브를 변환된 PDF로 바꾸기: 검토 중에 편집된 PDF 파일이 생성되는 경우 이러한 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-141">Replace redacted natives with converted PDFs: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="3841c-142">이 옵션을 선택하지 않은 경우, 편집된 기본 파일만 내보내거나 실제 변경이 포함된 PDF 파일을 내보내기 위해 이 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-142">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

## <a name="the-following-sections-describe-the-folder-structure-for-loose-files-and-condensed-directory-structure-options"></a><span data-ttu-id="3841c-143">다음 섹션에서는 느슨한 파일 및 압축된 디렉터리 구조 옵션에 대한 폴더 구조에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-143">The following sections describe the folder structure for loose files and condensed directory structure options</span></span>

<span data-ttu-id="3841c-144">내보낼은 압축되지 않은 콘텐츠의 최대 크기가 75GB인 ZIP 파일로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-144">Exports are partitioned into ZIP files with a maximum size of uncompressed content of 75 GB.</span></span> <span data-ttu-id="3841c-145">내보내기 크기가 75GB 미만이면 내보내기가 요약 파일과 단일 ZIP 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-145">If the export size is less than 75 GB, the export will consist of a summary file and a single ZIP file.</span></span> <span data-ttu-id="3841c-146">압축되지 않은 데이터의 75GB를 초과하는 내보내기에서는 여러 ZIP 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-146">For exports exceeding 75 GB of uncompressed data, multiple ZIP files will be created.</span></span> <span data-ttu-id="3841c-147">다운로드한 후 ZIP 파일을 단일 위치로 압축을 풀어 전체 내보내기 파일을 다시 만드면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-147">Once downloaded, the ZIP files can be uncompressed into a single location to recreate the full export.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="3841c-148">느슨한 파일 및 PST 내보내기 구조</span><span class="sxs-lookup"><span data-stu-id="3841c-148">Loose files and PST export structure</span></span>

<span data-ttu-id="3841c-149">이 내보내기 옵션을 선택하면 내보낼 콘텐츠가 다음 구조로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-149">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="3841c-150">Summary.csv: 검토 집합에서 내보낼 콘텐츠의 요약 포함</span><span class="sxs-lookup"><span data-stu-id="3841c-150">Summary.csv: Includes a summary of the content exported from the review set</span></span>
- <span data-ttu-id="3841c-151">루트 폴더: 이름이 [Export Name] x of z.zip 이 폴더는 각 ZIP 파일 파티션에 대해 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-151">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  - <span data-ttu-id="3841c-152">Export_load_file_x z.csv: 메타데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-152">Export_load_file_x of z.csv: The metadata file.</span></span>
  - <span data-ttu-id="3841c-153">경고 및 오류 x z.csv: 이 파일에는 검토 집합에서 내보내려고 할 때 발생하는 오류에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-153">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>
  - <span data-ttu-id="3841c-154">Exchange: 이 폴더에는 PST 파일에 Exchange 콘텐츠가 모두 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-154">Exchange: This folder contains all content from Exchange stored in PST files.</span></span> <span data-ttu-id="3841c-155">이 옵션에는 편집된 PDF 파일을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-155">Redacted PDF files cannot be included with this option.</span></span> <span data-ttu-id="3841c-156">검토 집합에서 첨부 파일이 선택된 경우 상위 전자 메일은 첨부 파일이 첨부된 후 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-156">If an attachment is selected in the review set, the parent email will be exported with the attachment attached.</span></span>
  - <span data-ttu-id="3841c-157">SharePoint: 이 폴더에는 기본 SharePoint 형식의 모든 네이티브 콘텐츠가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-157">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="3841c-158">이 옵션에는 편집된 PDF 파일을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-158">Redacted PDF files cannot be included with this option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="3841c-159">압축된 디렉터리 구조</span><span class="sxs-lookup"><span data-stu-id="3841c-159">Condensed directory structure</span></span>

- <span data-ttu-id="3841c-160">Summary.csv: 검토 집합에서 내보낼 콘텐츠의 요약 포함</span><span class="sxs-lookup"><span data-stu-id="3841c-160">Summary.csv: Includes a summary of the content exported from the review set</span></span>
- <span data-ttu-id="3841c-161">루트 폴더: 이름이 [Export Name] x of z.zip 이 폴더는 각 ZIP 파일 파티션에 대해 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-161">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  - <span data-ttu-id="3841c-162">Export_load_file_x z.csv: 메타데이터 파일과 ZIP 파일에 저장된 각 파일의 위치도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-162">Export_load_file_x of z.csv: The metadata file and also includes the location of each file that is stored in the ZIP file.</span></span>
  - <span data-ttu-id="3841c-163">경고 및 오류 x z.csv: 이 파일에는 검토 집합에서 내보내려고 할 때 발생하는 오류에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-163">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>
  - <span data-ttu-id="3841c-164">NativeFiles: 이 폴더에는 내보낼 수 있는 모든 기본 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-164">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="3841c-165">변환된 네이티브를 변환된 *PDF로* 바꾸기 옵션을 선택한 경우 네이티브 파일은 재조정된 PDF로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-165">Natives files are replaced with redacted PDFs if you selected the *Replace redacted natives with converted PDFs* option.</span></span>
  - <span data-ttu-id="3841c-166">Error_files: 이 폴더에는 추출 또는 기타 처리 오류가 있는 파일이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-166">Error_files: This folder contains files that had either extraction or other processing error.</span></span> <span data-ttu-id="3841c-167">파일은 ExtractionError 또는 ProcessingError와 같은 별도의 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-167">The files will be placed into separate folders, either ExtractionError or ProcessingError.</span></span> <span data-ttu-id="3841c-168">이러한 파일은 로드 파일에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-168">These files are listed in the load file.</span></span>
  - <span data-ttu-id="3841c-169">Extracted_text_files: 이 폴더에는 처리 시 생성된 추출된 텍스트 파일이 모두 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a><span data-ttu-id="3841c-170">사용자 계정으로 내보낼 압축된 디렉터리 Azure Storage</span><span class="sxs-lookup"><span data-stu-id="3841c-170">Condensed directory structure exported to your Azure Storage Account</span></span>

<span data-ttu-id="3841c-171">이 옵션은 *압축된* 디렉터리 구조와 동일한 일반 구조를 사용 하지만 콘텐츠는 압축되지 않습니다. 데이터는 사용자 계정으로 Azure Storage 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-171">This option uses the same general structure as the *Condensed directory structure*, however the contents is not zipped and the data is saved to your Azure Storage account.</span></span> <span data-ttu-id="3841c-172">이 옵션은 일반적으로 타사 eDiscovery 공급자를 사용할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841c-172">This option is generally used when working with a third-party eDiscovery provider.</span></span> <span data-ttu-id="3841c-173">이 옵션을 사용하는 방법에 대한 자세한 내용은 검토 집합에서 문서 내보내기 계정을 Azure Storage [참조하세요.](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="3841c-173">For details about how to use this option, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>
