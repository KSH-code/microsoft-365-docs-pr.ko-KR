---
title: 문서 이해 개요
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint 구문에서 문서 이해 개요 얻기
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683826"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="f4c06-103">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="f4c06-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="f4c06-104">문서 이해는 파일 분류와 정보 추출을 자동화 하기 위해 인공 지능(AI) 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="f4c06-105">편지나 계약서와 같이 구조화 되지 않은 문서에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="f4c06-106">이러한 문서에는 구문 또는 패턴을 기반으로 식별할 수 있는 텍스트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="f4c06-107">식별 된 텍스트는 파일 형식(분류자)과 추출 하려는 대상(추출자)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="f4c06-108">문서 이해 시나리오 예제에 대한 자세한 내용은 [SharePoint Syntex 채택: 시작 가이드](./adoption-getstarted.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4c06-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="f4c06-109">문서 이해 모델은 *콘텐츠 센터* 라는 SharePoint 사이트 형식에서 만들어지고 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="f4c06-110">SharePoint 문서 라이브러리에 적용 되는 경우 모델은 추출되는 정보를 저장하기 위한 열이 있는 콘텐츠 유형과 연결이 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="f4c06-111">사용자가 만든 콘텐츠 형식은 SharePoint 콘텐츠 형식 갤러리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="f4c06-112">기존 콘텐츠 유형을 사용하여 해당 스키마를 사용하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="f4c06-113">읽기 전용 또는 봉인된 내용 유형은 업데이트할 수 없으므로 모델에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="f4c06-114">문서 이해 모델에 *분류자* 및 *추출자* 를 추가하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="f4c06-115">분류자는 문서 라이브러리에 업로드 되는 문서를 식별하고 분류하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="f4c06-116">예를 들어, 분류자는 라이브러리에 업로드 되는 모든 *계약 갱신* 을 식별하도록 “성향 습득” 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="f4c06-117">계약 갱신 콘텐츠 형식은 사용자가 분류자를 만들 때 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="f4c06-118">추출자가 이 문서에서 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="f4c06-119">예를 들어 문서 라이브러리에서 식별 된 모든 계약 갱신 문서에서 각 계약 갱신 문서에 대한 *서비스 시작 날짜* 및 *클라이언트* 를 보도록 사용자 보기의 열을 디스플레이 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="f4c06-120">예제 파일을 사용하여 모델에서 분류자와 추출자를 성향 습득하고 테스트 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="f4c06-121">예제 파일에서는 파일에서 데이터를 식별하고 추출하려고 할 때 검색할 항목의 모델 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="f4c06-122">예를 들어, 사용자의 회사가 사용하는 계약 갱신 문서 예제를 사용하여 계약 갱신 분류자와 추출자를 성향 습득 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="f4c06-123">예제 파일을 사용하여 모델의 효율성을 테스트 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="f4c06-124">모델을 게시 한 후 콘텐츠 센터를 사용하여 액세스 권한이 있는 모든 SharePoint 문서 라이브러리에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="f4c06-125">파일 제한 사항</span><span class="sxs-lookup"><span data-stu-id="f4c06-125">File limitations</span></span>

<span data-ttu-id="f4c06-126">문서 이해 모델에서는 OCR(광학 인식) 기술을 사용하여 예제 파일이 있는 모델을 교육하고 문서 라이브러리의 파일에 대해 모델을 실행할 때 모두 PDF, 이미지 및 TIFF 파일을 스캔합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="f4c06-127">Microsoft Office 텍스트 기반 파일과 OCR로 스캔한 파일(PDF, 이미지 또는 TIFF)과 관련하여 다음과 같은 차이점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="f4c06-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="f4c06-128">Office 파일: 교육 중 및 문서 라이브러리의 파일에 대해 실행할 때 64,000자로 잘라냈습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="f4c06-129">OCR로 스캔한 파일: 20페이지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="f4c06-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4c06-130">Requirements</span></span>

<span data-ttu-id="f4c06-131">OCR 처리는 다음 요구 사항을 충족하는 문서에서 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="f4c06-132">JPG, PNG 또는 PDF 형식(텍스트 또는 스캔됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="f4c06-133">문자 추출 및 위치 관련 오류가 없는 텍스트 포함 PDF가 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="f4c06-134">PDF가 암호로 잠겨 있는 경우 PDF를 제출하기 전에 잠금을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="f4c06-135">컬렉션당 학습에 사용되는 문서의 합산 파일 크기는 50MB를 초과하면 안 되며 PDF 문서는 500페이지를 초과하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="f4c06-136">이미지의 경우 크기는 50 × 50에서 10,000 픽셀 × 10,000 픽셀 사이여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f4c06-137">매우 넓거나 홀수 차원이 있는 이미지(예: 평면도)는 OCR 프로세스에서 잘리고 정확도가 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="f4c06-138">PDF 파일의 경우 크기는 Legal 또는 A3 용지 크기에 해당하는 최대 17 x 17인치여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="f4c06-139">용지 문서에서 스캔하는 경우 스캔은 고품질 이미지여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="f4c06-140">라틴어 알파벳(영어 문자)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="f4c06-141">AI 작성기는 현재 다음 형식의 양식 처리 입력 데이터를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="f4c06-142">- 확인란 또는 라디오 단추</span><span class="sxs-lookup"><span data-stu-id="f4c06-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="f4c06-143">- 서명</span><span class="sxs-lookup"><span data-stu-id="f4c06-143">- Signatures</span></span><br><span data-ttu-id="f4c06-144">- 채우기 가능한 PDF</span><span class="sxs-lookup"><span data-stu-id="f4c06-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="f4c06-145">지원되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="f4c06-145">Supported file types</span></span>

<span data-ttu-id="f4c06-146">문서 이해 모델에서는 다음 파일 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c06-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="f4c06-147">doc</span><span class="sxs-lookup"><span data-stu-id="f4c06-147">doc</span></span>
- <span data-ttu-id="f4c06-148">docx</span><span class="sxs-lookup"><span data-stu-id="f4c06-148">docx</span></span>
- <span data-ttu-id="f4c06-149">eml</span><span class="sxs-lookup"><span data-stu-id="f4c06-149">eml</span></span>
- <span data-ttu-id="f4c06-150">heic</span><span class="sxs-lookup"><span data-stu-id="f4c06-150">heic</span></span>
- <span data-ttu-id="f4c06-151">heif</span><span class="sxs-lookup"><span data-stu-id="f4c06-151">heif</span></span>
- <span data-ttu-id="f4c06-152">htm</span><span class="sxs-lookup"><span data-stu-id="f4c06-152">htm</span></span>
- <span data-ttu-id="f4c06-153">html</span><span class="sxs-lookup"><span data-stu-id="f4c06-153">html</span></span>
- <span data-ttu-id="f4c06-154">jpeg</span><span class="sxs-lookup"><span data-stu-id="f4c06-154">jpeg</span></span>
- <span data-ttu-id="f4c06-155">jpg</span><span class="sxs-lookup"><span data-stu-id="f4c06-155">jpg</span></span>
- <span data-ttu-id="f4c06-156">markdown</span><span class="sxs-lookup"><span data-stu-id="f4c06-156">markdown</span></span>
- <span data-ttu-id="f4c06-157">md</span><span class="sxs-lookup"><span data-stu-id="f4c06-157">md</span></span>
- <span data-ttu-id="f4c06-158">msg</span><span class="sxs-lookup"><span data-stu-id="f4c06-158">msg</span></span>
- <span data-ttu-id="f4c06-159">pdf</span><span class="sxs-lookup"><span data-stu-id="f4c06-159">pdf</span></span>
- <span data-ttu-id="f4c06-160">png</span><span class="sxs-lookup"><span data-stu-id="f4c06-160">png</span></span>
- <span data-ttu-id="f4c06-161">ppt</span><span class="sxs-lookup"><span data-stu-id="f4c06-161">ppt</span></span>
- <span data-ttu-id="f4c06-162">pptx</span><span class="sxs-lookup"><span data-stu-id="f4c06-162">pptx</span></span>
- <span data-ttu-id="f4c06-163">rtf</span><span class="sxs-lookup"><span data-stu-id="f4c06-163">rtf</span></span>
- <span data-ttu-id="f4c06-164">tif</span><span class="sxs-lookup"><span data-stu-id="f4c06-164">tif</span></span>
- <span data-ttu-id="f4c06-165">tiff</span><span class="sxs-lookup"><span data-stu-id="f4c06-165">tiff</span></span>
- <span data-ttu-id="f4c06-166">txt</span><span class="sxs-lookup"><span data-stu-id="f4c06-166">txt</span></span>
- <span data-ttu-id="f4c06-167">xls</span><span class="sxs-lookup"><span data-stu-id="f4c06-167">xls</span></span>
- <span data-ttu-id="f4c06-168">xlsx</span><span class="sxs-lookup"><span data-stu-id="f4c06-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="f4c06-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4c06-169">See Also</span></span>
[<span data-ttu-id="f4c06-170">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="f4c06-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="f4c06-171">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="f4c06-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="f4c06-172">콘텐츠 센터 만들기</span><span class="sxs-lookup"><span data-stu-id="f4c06-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="f4c06-173">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="f4c06-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="f4c06-174">모델 적용</span><span class="sxs-lookup"><span data-stu-id="f4c06-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="f4c06-175">문서 이해와 양식 처리 모델의 차이</span><span class="sxs-lookup"><span data-stu-id="f4c06-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="f4c06-176">양식 처리 개요</span><span class="sxs-lookup"><span data-stu-id="f4c06-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="f4c06-177">SharePoint Syntex 접근성 모드</span><span class="sxs-lookup"><span data-stu-id="f4c06-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)