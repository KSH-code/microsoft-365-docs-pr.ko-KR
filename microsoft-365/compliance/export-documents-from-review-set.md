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
description: 프레젠테이션 또는 외부 검토에 대한 검토 집합에서 콘텐츠를 선택하고 내보내는 방법을 학습합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2ca8e2f400d9f257549e59305d1fd56586185e2
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423649"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="1ff07-103">Advanced eDiscovery의 검토 집합에서 문서 내보내기</span><span class="sxs-lookup"><span data-stu-id="1ff07-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="1ff07-104">내보내기에서는 사용자가 다운로드 패키지에 포함된 콘텐츠를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="1ff07-105">내보내기 도구는 다음 설정을 사용하여 구성 페이지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-105">The Export tool provides a configuration page with the following settings:</span></span>

![검토 집합에서 항목을 내보내기 위한 옵션](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="1ff07-107">내보내기 옵션</span><span class="sxs-lookup"><span data-stu-id="1ff07-107">Export options</span></span>

- <span data-ttu-id="1ff07-108">내보내기 이름: 내보내기 작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="1ff07-109">설명: 설명을 추가할 수 있는 자유 텍스트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="1ff07-110">다음 문서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-110">Export these documents:</span></span>

  - <span data-ttu-id="1ff07-111">선택한 문서만 - 현재 선택된 문서만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="1ff07-112">검토 집합의 모든 문서 - 검토 집합의 모든 문서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="1ff07-113">메타데이터</span><span class="sxs-lookup"><span data-stu-id="1ff07-113">Metadata</span></span>
  
  - <span data-ttu-id="1ff07-114">파일 로드 - 이 파일에는 각 파일에 대한 메타데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="1ff07-115">포함된 필드에 대한 자세한 내용은 [Advanced eDiscovery의 문서 메타데이터 필드를 참조하세요.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="1ff07-115">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="1ff07-116">이 파일은 일반적으로 타사 eDiscovery 도구에서 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="1ff07-117">태그 - 태그를 선택하면 태그 정보가 로드 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="1ff07-118">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="1ff07-118">Content</span></span>
  
  - <span data-ttu-id="1ff07-119">기본 파일 - 기본 파일을 포함하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="1ff07-120">대화 옵션</span><span class="sxs-lookup"><span data-stu-id="1ff07-120">Conversation options</span></span>
    
    - <span data-ttu-id="1ff07-121">대화 파일 - 재구성된 채팅 메시지를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="1ff07-122">이 형식은 기본 응용 프로그램에서 사용자에게 표시하는 모양과 같은 형식으로 대화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="1ff07-123">개별 채팅 메시지 - Microsoft 365에 저장된 원래 대화 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="1ff07-124">옵션</span><span class="sxs-lookup"><span data-stu-id="1ff07-124">Options</span></span>

  - <span data-ttu-id="1ff07-125">텍스트 파일 - 추출된 네이티브 파일의 텍스트 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="1ff07-126">편집된 네이티브를 변환된 PDF로 바꾸기 - 검토 중에 편집된 PDF 파일이 생성되는 경우 이러한 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="1ff07-127">이 옵션을 선택하지 않은 경우, 편집된 기본 파일만 내보내거나 실제 변경이 포함된 PDF 파일을 내보내기 위해 이 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="1ff07-128">출력 옵션(내보낼 콘텐츠는 웹 브라우저를 통해 직접 다운로드할 수 있습니다. 또는 Azure Storage 계정으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="1ff07-129">처음 두 옵션을 사용하면 직접 다운로드를 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="1ff07-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="1ff07-130">느슨한 파일 및 PSTS(가능한 경우 전자 메일이 PSTS에 추가) - 파일은 기본 응용 프로그램에서 사용자가 볼 수 있는 원래 디렉터리 구조와 같은 형식으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="1ff07-131">자세한 내용은 느슨한 파일 및 [PST 내보내기](#loose-files-and-pst-export-structure) 구조 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff07-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="1ff07-132">압축된 디렉터리 구조 - 파일을 내보내고 다운로드에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="1ff07-133">Azure Storage 계정으로 내보낼 압축된 디렉터리 구조 - 파일이 조직의 Azure Storage 계정으로 내보내기됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage account.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="1ff07-134">느슨한 파일 및 PST 내보내기 구조</span><span class="sxs-lookup"><span data-stu-id="1ff07-134">Loose files and PST export structure</span></span>

<span data-ttu-id="1ff07-135">이 내보내기 옵션을 선택하면 내보낼 콘텐츠가 다음 구조로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="1ff07-136">루트 폴더 - 이름이 지정되어 있는 이 폴더는 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="1ff07-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="1ff07-137">Export_load_file.csv - 메타데이터 파일.</span><span class="sxs-lookup"><span data-stu-id="1ff07-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="1ff07-138">Summary.csv - 내보내기 통계도 포함하는 요약 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="1ff07-139">Exchange - 이 폴더에는 Exchange의 모든 콘텐츠가 기본 파일 형식으로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="1ff07-140">변환된 네이티브를 변환된 **PDF로** 바꾸기 옵션을 선택한 경우 네이티브 파일은 재조정된 PDF로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="1ff07-141">SharePoint = 이 폴더에는 SharePoint의 모든 기본 콘텐츠가 기본 파일 형식으로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="1ff07-142">변환된 네이티브를 변환된 **PDF로** 바꾸기 옵션을 선택한 경우 네이티브 파일은 재조정된 PDF로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="1ff07-143">압축된 디렉터리 구조</span><span class="sxs-lookup"><span data-stu-id="1ff07-143">Condensed directory structure</span></span>

- <span data-ttu-id="1ff07-144">루트 폴더 - 이 폴더의 이름은 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="1ff07-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="1ff07-145">Export_load_file.csv - 메타데이터 파일.</span><span class="sxs-lookup"><span data-stu-id="1ff07-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="1ff07-146">Summary.txt - 내보내기 통계도 포함하는 요약 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="1ff07-147">Input_or_native_files - 이 폴더에는 내보낼 수 있는 모든 기본 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="1ff07-148">편집된 PDF 파일을 내보낼 경우 PST 파일에 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="1ff07-149">대신 별도의 폴더에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="1ff07-150">Error_files - 내보내기에 포함된 경우 이 폴더에 다음 오류 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="1ff07-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="1ff07-151">ExtractionError.</span></span> <span data-ttu-id="1ff07-152">상위 파일에서 제대로 추출되지 않은 파일의 사용 가능한 메타데이터가 포함된 CSV 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="1ff07-153">ProcessingError – 이 파일에는 처리 오류가 있는 문서 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="1ff07-154">이 콘텐츠는 항목 수준으로, 첨부 파일에서 처리 오류가 발생하는 경우 첨부 파일이 포함된 전자 메일 메시지가 이 폴더에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="1ff07-155">Extracted_text_files - 이 폴더에는 처리 시 생성된 추출된 텍스트 파일이 모두 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="1ff07-156">내보내기 작업은 사례의 수명 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-156">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="1ff07-157">그러나 내보내기 작업이 완료된 후 30일 이내에 내보내기 작업에서 콘텐츠를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff07-157">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>
