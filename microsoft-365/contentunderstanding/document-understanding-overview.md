---
title: 문서 이해 개요
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint 구문에서 문서 이해 개요 얻기
ms.openlocfilehash: e3b239260953837f70663bb6f7e2dba1676c49eb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911201"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="8202e-103">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="8202e-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="8202e-104">문서 이해는 파일 분류와 정보 추출을 자동화 하기 위해 인공 지능(AI) 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="8202e-105">편지나 계약서와 같이 구조화 되지 않은 문서에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="8202e-106">이러한 문서에는 구문 또는 패턴을 기반으로 식별할 수 있는 텍스트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="8202e-107">식별 된 텍스트는 파일 형식(분류자)과 추출 하려는 대상(추출자)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="8202e-108">문서 이해 시나리오 예제에 대한 자세한 내용은 [SharePoint Syntex 채택: 시작 가이드](./adoption-getstarted.md#document-understanding-scenario-example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8202e-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="8202e-109">문서 이해 모델은 *콘텐츠 센터* 라는 SharePoint 사이트 형식에서 만들어지고 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="8202e-110">SharePoint 문서 라이브러리에 적용 되는 경우 모델은 추출되는 정보를 저장하기 위한 열이 있는 콘텐츠 유형과 연결이 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="8202e-111">사용자가 만든 콘텐츠 형식은 SharePoint 콘텐츠 형식 갤러리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="8202e-112">기존 콘텐츠 유형을 사용하여 해당 스키마를 사용하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="8202e-113">읽기 전용 또는 봉인된 내용 유형은 업데이트할 수 없으므로 모델에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="8202e-114">문서 이해 모델에 *분류자* 및 *추출자* 를 추가하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="8202e-115">분류자는 문서 라이브러리에 업로드 되는 문서를 식별하고 분류하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="8202e-116">예를 들어, 분류자는 라이브러리에 업로드 되는 모든 *계약 갱신* 을 식별하도록 “성향 습득” 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="8202e-117">계약 갱신 콘텐츠 형식은 사용자가 분류자를 만들 때 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="8202e-118">추출자가 이 문서에서 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="8202e-119">예를 들어 문서 라이브러리에서 식별 된 모든 계약 갱신 문서에서 각 계약 갱신 문서에 대한 *서비스 시작 날짜* 및 *클라이언트* 를 보도록 사용자 보기의 열을 디스플레이 합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="8202e-120">예제 파일을 사용하여 모델에서 분류자와 추출자를 성향 습득하고 테스트 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="8202e-121">예제 파일에서는 파일에서 데이터를 식별하고 추출하려고 할 때 검색할 항목의 모델 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="8202e-122">예를 들어, 사용자의 회사가 사용하는 계약 갱신 문서 예제를 사용하여 계약 갱신 분류자와 추출자를 성향 습득 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="8202e-123">예제 파일을 사용하여 모델의 효율성을 테스트 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="8202e-124">모델을 게시 한 후 콘텐츠 센터를 사용하여 액세스 권한이 있는 모든 SharePoint 문서 라이브러리에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

### <a name="file-limitations"></a><span data-ttu-id="8202e-125">파일 제한 사항</span><span class="sxs-lookup"><span data-stu-id="8202e-125">File limitations</span></span>

<span data-ttu-id="8202e-126">문서 이해 모델에서는 OCR(광학 인식) 기술을 사용하여 예제 파일이 있는 모델을 교육하고 문서 라이브러리의 파일에 대해 모델을 실행할 때 모두 PDF, 이미지 및 TIFF 파일을 스캔합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="8202e-127">Microsoft Office 텍스트 기반 파일과 OCR로 스캔한 파일(PDF, 이미지 또는 TIFF)과 관련하여 다음과 같은 차이점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="8202e-127">Note the following differences in regards to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="8202e-128">Office 파일: 교육 중 및 문서 라이브러리의 파일에 대해 실행할 때 64K자로 잘라냅니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-128">Office files: We truncate at 64K characters (in training and when run against files in a document library).</span></span>
- <span data-ttu-id="8202e-129">OCR로 스캔한 파일: 20페이지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-129">OCR-scanned files: There is a 20 page limit.</span></span>  

#### <a name="supported-file-types"></a><span data-ttu-id="8202e-130">지원되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="8202e-130">Supported file types</span></span>

<span data-ttu-id="8202e-131">문서 이해 모델에서는 다음 파일 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8202e-131">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="8202e-132">doc</span><span class="sxs-lookup"><span data-stu-id="8202e-132">doc</span></span>
- <span data-ttu-id="8202e-133">docx</span><span class="sxs-lookup"><span data-stu-id="8202e-133">docx</span></span>
- <span data-ttu-id="8202e-134">eml</span><span class="sxs-lookup"><span data-stu-id="8202e-134">eml</span></span>
- <span data-ttu-id="8202e-135">heic</span><span class="sxs-lookup"><span data-stu-id="8202e-135">heic</span></span>
- <span data-ttu-id="8202e-136">heif</span><span class="sxs-lookup"><span data-stu-id="8202e-136">heif</span></span>
- <span data-ttu-id="8202e-137">htm</span><span class="sxs-lookup"><span data-stu-id="8202e-137">htm</span></span>
- <span data-ttu-id="8202e-138">html</span><span class="sxs-lookup"><span data-stu-id="8202e-138">html</span></span>
- <span data-ttu-id="8202e-139">jpeg</span><span class="sxs-lookup"><span data-stu-id="8202e-139">jpeg</span></span>
- <span data-ttu-id="8202e-140">jpg</span><span class="sxs-lookup"><span data-stu-id="8202e-140">jpg</span></span>
- <span data-ttu-id="8202e-141">markdown</span><span class="sxs-lookup"><span data-stu-id="8202e-141">markdown</span></span>
- <span data-ttu-id="8202e-142">md</span><span class="sxs-lookup"><span data-stu-id="8202e-142">md</span></span>
- <span data-ttu-id="8202e-143">msg</span><span class="sxs-lookup"><span data-stu-id="8202e-143">msg</span></span>
- <span data-ttu-id="8202e-144">pdf</span><span class="sxs-lookup"><span data-stu-id="8202e-144">pdf</span></span>
- <span data-ttu-id="8202e-145">png</span><span class="sxs-lookup"><span data-stu-id="8202e-145">png</span></span>
- <span data-ttu-id="8202e-146">ppt</span><span class="sxs-lookup"><span data-stu-id="8202e-146">ppt</span></span>
- <span data-ttu-id="8202e-147">pptx</span><span class="sxs-lookup"><span data-stu-id="8202e-147">pptx</span></span>
- <span data-ttu-id="8202e-148">rtf</span><span class="sxs-lookup"><span data-stu-id="8202e-148">rtf</span></span>
- <span data-ttu-id="8202e-149">tif</span><span class="sxs-lookup"><span data-stu-id="8202e-149">tif</span></span>
- <span data-ttu-id="8202e-150">tiff</span><span class="sxs-lookup"><span data-stu-id="8202e-150">tiff</span></span>
- <span data-ttu-id="8202e-151">txt</span><span class="sxs-lookup"><span data-stu-id="8202e-151">txt</span></span>
- <span data-ttu-id="8202e-152">xls</span><span class="sxs-lookup"><span data-stu-id="8202e-152">xls</span></span>
- <span data-ttu-id="8202e-153">xlsx</span><span class="sxs-lookup"><span data-stu-id="8202e-153">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="8202e-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8202e-154">See Also</span></span>
[<span data-ttu-id="8202e-155">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="8202e-155">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="8202e-156">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="8202e-156">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="8202e-157">콘텐츠 센터 만들기</span><span class="sxs-lookup"><span data-stu-id="8202e-157">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="8202e-158">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="8202e-158">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="8202e-159">모델 적용</span><span class="sxs-lookup"><span data-stu-id="8202e-159">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="8202e-160">문서 이해와 양식 처리 모델의 차이</span><span class="sxs-lookup"><span data-stu-id="8202e-160">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="8202e-161">양식 처리 개요</span><span class="sxs-lookup"><span data-stu-id="8202e-161">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="8202e-162">SharePoint Syntex 접근성 모드</span><span class="sxs-lookup"><span data-stu-id="8202e-162">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)