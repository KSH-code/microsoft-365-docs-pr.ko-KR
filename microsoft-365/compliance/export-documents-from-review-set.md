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
description: 프레젠테이션 또는 외부 검토를 위해 검토 집합에서 콘텐츠를 선택 하 고 내보내는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 855f1b8fef7a1df6ed86f058b71e5027851b5f0d
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399182"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="34474-103">검토 집합에서 문서 내보내기</span><span class="sxs-lookup"><span data-stu-id="34474-103">Export documents from a review set</span></span>

<span data-ttu-id="34474-104">내보내기를 사용 하면 다운로드 패키지에 포함 된 콘텐츠를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="34474-105">내보내기 도구에서는 다음과 같은 설정을 사용 하 여 구성 페이지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="34474-105">The Export tool provides a configuration page with the following settings:</span></span>

![검토 집합에서 항목을 내보내기 위한 옵션](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="34474-107">내보내기 옵션</span><span class="sxs-lookup"><span data-stu-id="34474-107">Export options</span></span>

- <span data-ttu-id="34474-108">내보내기 이름: 내보내기 작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="34474-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="34474-109">설명: 설명을 추가할 수 있는 자유 텍스트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="34474-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="34474-110">내보낼 문서:</span><span class="sxs-lookup"><span data-stu-id="34474-110">Export these documents:</span></span>

  - <span data-ttu-id="34474-111">선택한 문서만-현재 선택 된 문서만 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="34474-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="34474-112">검토 집합의 모든 문서-검토 집합의 모든 문서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="34474-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="34474-113">메타데이터</span><span class="sxs-lookup"><span data-stu-id="34474-113">Metadata</span></span>
  
  - <span data-ttu-id="34474-114">파일 로드-이 파일에는 각 파일의 메타 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="34474-115">포함 된 필드에 대 한 자세한 내용은 [Advanced eDiscovery의 문서 메타 데이터 필드](document-metadata-fields-in-Advanced-eDiscovery.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="34474-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="34474-116">이 파일은 일반적으로 타사 eDiscovery 도구로 ingested 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="34474-117">태그-이 확인란이 선택 되 면 태그 정보가 로드 파일에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="34474-118">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="34474-118">Content</span></span>
  
  - <span data-ttu-id="34474-119">네이티브 파일-네이티브 파일을 포함 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="34474-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="34474-120">대화 옵션</span><span class="sxs-lookup"><span data-stu-id="34474-120">Conversation options</span></span>
    
    - <span data-ttu-id="34474-121">대화 파일-내보낸 채팅 메시지를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="34474-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="34474-122">이 형식은 사용자가 네이티브 응용 프로그램에 표시 되는 것과 비슷한 형태의 대화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="34474-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="34474-123">개별 채팅 메시지-Microsoft 365에 저장 되어 있는 원본 대화 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="34474-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="34474-124">옵션</span><span class="sxs-lookup"><span data-stu-id="34474-124">Options</span></span>

  - <span data-ttu-id="34474-125">텍스트 파일-추출 된 텍스트 버전의 네이티브 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="34474-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="34474-126">변환 된 Pdf로 redacted natives 교체-검토 중에 redacted PDF 파일이 생성 되는 경우 이러한 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="34474-127">이 옵션을 선택 하지 않으면 서 redacted 이었던 네이티브 파일만 내보내도록 선택 하거나, 실제 redactions 포함 된 PDF 파일을 내보내도록이 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="34474-128">출력 옵션 (내보낸 콘텐츠는 웹 브라우저를 통해 직접 다운로드 하거나 Azure Storage 계정으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="34474-129">처음 두 옵션은 직접 다운로드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34474-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="34474-130">느슨한 파일 및 Pst (가능한 경우 Pst에 전자 메일이 추가 됨)-파일은 기본 응용 프로그램에서 사용자가 본 디렉터리 구조와 비슷한 형식으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="34474-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="34474-131">자세한 내용은 [파일 및 PST 내보내기 구조 완화](#loose-files-and-pst-export-structure) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="34474-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="34474-132">압축 된 디렉터리 구조-파일을 내보내고 다운로드에 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="34474-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="34474-133">Azure Storage 계정으로 내보낸 디렉터리 구조-파일을 조직의 Azure Storage accouunt로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="34474-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="34474-134">느슨한 파일 및 PST 내보내기 구조</span><span class="sxs-lookup"><span data-stu-id="34474-134">Loose files and PST export structure</span></span>

<span data-ttu-id="34474-135">이 내보내기 옵션을 선택 하면 내보낸 콘텐츠가 다음 구조로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="34474-136">루트 폴더-명명 된 ExportName.zip의이 폴더</span><span class="sxs-lookup"><span data-stu-id="34474-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="34474-137">Export_load_file.csv 메타 데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="34474-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="34474-138">Summary.csv-내보내기 통계도 포함 된 요약 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="34474-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="34474-139">Exchange-이 폴더에는 Exchange의 모든 콘텐츠가 기본 파일 형식으로 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="34474-140">**변환 된 pdf로 redacted Natives 바꾸기** 옵션을 선택한 경우 Natives 파일이 redacted pdf로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="34474-141">SharePoint =이 폴더에는 SharePoint의 모든 네이티브 콘텐츠가 네이티브 파일 형식으로 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="34474-142">**변환 된 pdf로 redacted Natives 바꾸기** 옵션을 선택한 경우 Natives 파일이 redacted pdf로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="34474-143">압축 디렉터리 구조</span><span class="sxs-lookup"><span data-stu-id="34474-143">Condensed directory structure</span></span>

- <span data-ttu-id="34474-144">루트 폴더-이 폴더의 이름은 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="34474-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="34474-145">Export_load_file.csv 메타 데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="34474-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="34474-146">Summary.txt-내보내기 통계도 포함 된 요약 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="34474-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="34474-147">Input_or_native_files-이 폴더에는 내보낸 모든 네이티브 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="34474-148">Redacted PDF 파일을 내보내면 PST 파일에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="34474-149">대신, 구분 된 폴더에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="34474-150">Error_files-이 폴더에는 내보내기에 포함 된 경우 다음 오류 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="34474-151">ExtractionError</span><span class="sxs-lookup"><span data-stu-id="34474-151">ExtractionError.</span></span> <span data-ttu-id="34474-152">부모 파일에서 올바르게 추출 되지 않은 파일의 사용 가능한 메타 데이터가 포함 된 CSV 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="34474-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="34474-153">ProcessingError-이 파일에는 처리 오류가 있는 문서 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="34474-154">이 콘텐츠는 항목 수준으로, 첨부 파일에 처리 오류가 발생 한 경우 첨부 파일이 포함 된 전자 메일 메시지가이 폴더에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="34474-155">Extracted_text_files-이 폴더에는 처리 시 생성 된 추출 된 텍스트 파일이 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34474-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="34474-156">내보내기 작업은 서비스 케이스 수명 동안 보존 되며, 케이스가 삭제 되지 않는 한 다운로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34474-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
