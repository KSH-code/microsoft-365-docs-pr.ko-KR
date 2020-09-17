---
title: 문서 이해 및 양식 처리 모델의 차이점 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 문서 이해 및 양식 처리 모델 간의 주요 차이점에 대해 설명 합니다.
ms.openlocfilehash: ceea3a6e7898d8971ea458222d6164b496fcb8b7
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950063"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="7d43b-103">문서 이해 및 양식 처리 모델의 차이점 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="7d43b-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="7d43b-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="7d43b-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="7d43b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="7d43b-106">Project Cortex의 콘텐츠 이해를 통해 SharePoint 문서 라이브러리에 업로드 되는 문서를 식별 하 고 분류할 수 있을 뿐만 아니라 각 파일에서 관련 정보를 추출 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="7d43b-107">예를 들어 파일이 SharePoint 문서 라이브러리에 업로드 되 면 *구매 주문* 으로 식별 되는 모든 파일이 해당 파일을 표시 되는 사용자 지정 문서 라이브러리 보기에 표시 되는 것 처럼 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="7d43b-108">또한 각 파일 (예: *PO 번호* 및 *합계*)에서 특정 정보를 가져오고 문서 라이브러리 보기의 열에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="7d43b-109">콘텐츠 이해를 통해 *모델* 을 만들어 필요한 정보를 식별 하 고 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="7d43b-110">사용할 수 있는 모델에는 다음과 같은 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="7d43b-111">문서 이해 모델</span><span class="sxs-lookup"><span data-stu-id="7d43b-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="7d43b-112">양식 처리 모델</span><span class="sxs-lookup"><span data-stu-id="7d43b-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="7d43b-113">일반적으로 동일한 용도로 두 모델을 모두 사용 하지만, 사용할 수 있는 중요 한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-113">While both models are used for generally the same purpose, there are key differences that will affect which one you might choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="7d43b-114">구조적이 고 구조화 및 반구조적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="7d43b-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="7d43b-115">문서 이해 모델을 사용 하 여 추출할 텍스트 엔터티가 문서의 문장이 나 특정 영역에 위치할 수 있는 문자 또는 계약과 같은 구조화 되지 않은 문서에서 데이터를 식별 하 고 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="7d43b-116">예를 들어, 구조화 되지 않은 문서는 다양 한 방식으로 작성할 수 있는 계약 갱신 문자임이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="7d43b-117">그러나 각 계약 갱신 문서의 본문에 일관 되 게 제공 되는 정보 (예: 텍스트 문자열 "서비스 시작 날짜"와 실제 날짜)가 여기에 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="7d43b-118">양식 처리 모델을 사용 하 여 파일을 식별 하 고, 일반 키-값 쌍 (예 *: 10/1/2020*) \* 또는 테이블 데이터를 사용할 수 있는 양식 또는 송장 등의 구조적 또는 반구조적 문서에서 데이터를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="7d43b-119">예를 들어 양식 처리를 위한 좋은 방법은 클라이언트에서 문서 레이아웃의 같은 영역에 있는 특정 필드에 대 한 정보 (예: *이름*, *전화 번호*, *전체 비용*등)를 제공 해야 하는 회사의 주문 요청 양식입니다.  세금 양식은 구조화 된 문서를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="7d43b-120">생성 위치</span><span class="sxs-lookup"><span data-stu-id="7d43b-120">Where they are created</span></span>

<span data-ttu-id="7d43b-121">문서 이해 모델은 SharePoint 콘텐츠 센터 사이트에서 만들어지고 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="7d43b-122">콘텐츠 센터 사이트에 액세스 하 여 모델을 이해 하는 문서를 만들거나 SharePoint 문서 라이브러리에이를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="7d43b-123">모델을 이해 하는 문서를 만드는 경우 SharePoint 콘텐츠 형식 갤러리에 저장 되는 [sharepoint 콘텐츠 형식을](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="7d43b-124">필요한 경우 기존 콘텐츠 형식을 사용 하 여 모델을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="7d43b-125">양식 처리 모델은 PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)에서 만들어지지만 SharePoint 문서 라이브러리에서 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint document library.</span></span> <span data-ttu-id="7d43b-126">사용자가 양식 처리 모델을 만들기 위해 문서 라이브러리에서 양식 처리 모델 만들기를 사용 하도록 설정 해야 하 고 관리자가 관리자 설정 이해 콘텐츠를 통해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="7d43b-127">양식 처리 모델에서는 파일을 문서 라이브러리에 업로드 한 경우이를 처리 하기 위해 PowerAutomate 흐름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="7d43b-128">또한 양식 처리 모델은 SharePoint 콘텐츠 형식 갤러리에도 저장 되는 새 [SharePoint 콘텐츠 형식을](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="7d43b-129">적용할 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="7d43b-129">Where they can be applied</span></span>

<span data-ttu-id="7d43b-130">문서를 이해 하는 데 사용할 수 있는 다양 한 SharePoint 문서 라이브러리에이 모델을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="7d43b-131">콘텐츠 센터를 사용 하 여 문서 이해 모델을 만들 수 있을 뿐만 아니라 다른 문서 라이브러리에도 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="7d43b-132">콘텐츠 센터를 통해 문서를 이해 하는 방법을 보다 중앙에서 제어할 수 있으며,이 정보는 콘텐츠 센터에 롤업 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="7d43b-133">양식 처리 모델은 현재 만들어진 SharePoint 문서 라이브러리에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="7d43b-134">이렇게 하면 사이트에 대 한 액세스 권한이 있는 라이선스가 부여 된 모든 사용자가 양식 처리 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43b-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="7d43b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d43b-135">See Also</span></span>
[<span data-ttu-id="7d43b-136">교육: AI Builder를 사용 하 여 비즈니스 성과 개선</span><span class="sxs-lookup"><span data-stu-id="7d43b-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="7d43b-137">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="7d43b-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="7d43b-138">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="7d43b-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="7d43b-139">문서 이해 모델 적용</span><span class="sxs-lookup"><span data-stu-id="7d43b-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="7d43b-140">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="7d43b-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



