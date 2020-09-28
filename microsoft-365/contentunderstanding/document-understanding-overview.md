---
title: 문서 이해 개요
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint Syntex에서 이해 하는 문서에 대 한 개요를 볼 수 있습니다.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294763"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="ead49-103">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="ead49-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="ead49-104">문서 이해는 인공 지능 (인공 지능) 모델을 사용 하 여 파일 분류를 자동화 하 고 정보를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="ead49-105">편지 또는 계약과 같은 구조화 되지 않은 문서에서 사용 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="ead49-106">이러한 문서에는 구문 또는 패턴에 따라 식별 가능한 텍스트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="ead49-107">식별 된 텍스트는 파일 형식 (분류)과 추출할 대상 (추출기)을 모두 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="ead49-108">문서 이해 모델은 *콘텐츠 센터*라는 유형의 SharePoint 사이트에서 만들어지고 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="ead49-109">SharePoint 문서 라이브러리에 적용 된 모델에는 추출할 정보를 저장 하기 위한 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="ead49-110">만드는 콘텐츠 형식은 SharePoint 콘텐츠 형식 갤러리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="ead49-111">기존 콘텐츠 형식을 사용 하 여 해당 스키마를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="ead49-112">문서에 *분류자* 및 *추출기* 를 추가 하 여 다음 작업을 수행할 수 있는 모델을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="ead49-113">분류자는 문서 라이브러리로 업로드 되는 문서를 식별 하 고 분류 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="ead49-114">예를 들어 분류자는 라이브러리에 업로드 되는 모든 *계약 갱신* 문서를 식별 하기 위해 "교육" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="ead49-115">계약 갱신 콘텐츠 형식은 사용자가 분류자를 만들 때 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="ead49-116">추출기이 문서에서 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="ead49-117">예를 들어 문서 라이브러리에서 식별 된 모든 계약 갱신 문서에 대해 각 계약 갱신 문서에 대 한 *서비스 시작 날짜* 및  *클라이언트* 도 표시 되는 열이 보기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="ead49-118">샘플 파일을 사용 하 여 모델에서 분류자 및 추출기을 학습 하 고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="ead49-119">샘플 파일에서는 파일에서 데이터를 식별 하 고 추출 하려고 할 때 확인할 수 있는 사항에 대 한 모델 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="ead49-120">예를 들어 회사에서 사용 하는 계약 갱신 문서의 샘플을 사용 하 여 계약 갱신 분류자 및 추출기을 교육 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="ead49-121">샘플 파일을 사용 하 여 모델의 효율성을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="ead49-122">모델을 게시 한 후 콘텐츠 센터를 사용 하 여 액세스 권한이 있는 SharePoint 문서 라이브러리에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead49-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="ead49-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ead49-123">See Also</span></span>
[<span data-ttu-id="ead49-124">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="ead49-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="ead49-125">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="ead49-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="ead49-126">[콘텐츠 센터 만들기](create-a-content-center.md) 
 [양식 처리 모델 만들기](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="ead49-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="ead49-127">[모델 적용](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="ead49-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="ead49-128">문서 이해와 양식 처리 모델의 차이점</span><span class="sxs-lookup"><span data-stu-id="ead49-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="ead49-129">양식 처리 개요</span><span class="sxs-lookup"><span data-stu-id="ead49-129">Form processing overview</span></span>](form-processing-overview.md)
