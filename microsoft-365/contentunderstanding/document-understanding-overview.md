---
title: 문서 이해 개요
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Microsoft SharePoint 구문에서 문서 이해 개요 얻기
ms.openlocfilehash: 1265dfa06db323e23d63a044a1a95a6b67c525cf
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333561"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="57b2a-103">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="57b2a-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="57b2a-104">문서 이해는 파일 분류와 정보 추출을 자동화 하기 위해 인공 지능(AI) 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="57b2a-105">편지나 계약서와 같이 구조화 되지 않은 문서에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="57b2a-106">이러한 문서에는 구문 또는 패턴을 기반으로 식별할 수 있는 텍스트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="57b2a-107">식별 된 텍스트는 파일 형식(분류자)과 추출 하려는 대상(추출자)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="57b2a-108">문서 이해 시나리오 예제에 대한 자세한 내용은 [SharePoint Syntex 채택: 시작 가이드](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57b2a-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="57b2a-109">문서 이해 모델은 *콘텐츠 센터*라는 SharePoint 사이트 형식에서 만들어지고 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="57b2a-110">SharePoint 문서 라이브러리에 적용 되는 경우 모델은 추출되는 정보를 저장하기 위한 열이 있는 콘텐츠 유형과 연결이 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="57b2a-111">사용자가 만든 콘텐츠 형식은 SharePoint 콘텐츠 형식 갤러리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="57b2a-112">기존 콘텐츠 유형을 사용하여 해당 스키마를 사용하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-112">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="57b2a-113">문서 이해 모델에 *분류자* 및 *추출자*를 추가하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-113">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="57b2a-114">분류자는 문서 라이브러리에 업로드 되는 문서를 식별하고 분류하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-114">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="57b2a-115">예를 들어, 분류자는 라이브러리에 업로드 되는 모든 *계약 갱신*을 식별하도록 “성향 습득” 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-115">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="57b2a-116">계약 갱신 콘텐츠 형식은 사용자가 분류자를 만들 때 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-116">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="57b2a-117">추출자가 이 문서에서 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-117">Extractors pull information from these documents.</span></span> <span data-ttu-id="57b2a-118">예를 들어 문서 라이브러리에서 식별 된 모든 계약 갱신 문서에서 각 계약 갱신 문서에 대한 *서비스 시작 날짜* 및 *클라이언트*를 보도록 사용자 보기의 열을 디스플레이 합니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-118">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="57b2a-119">예제 파일을 사용하여 모델에서 분류자와 추출자를 성향 습득하고 테스트 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-119">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="57b2a-120">예제 파일에서는 파일에서 데이터를 식별하고 추출하려고 할 때 검색할 항목의 모델 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-120">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="57b2a-121">예를 들어, 사용자의 회사가 사용하는 계약 갱신 문서 예제를 사용하여 계약 갱신 분류자와 추출자를 성향 습득 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-121">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="57b2a-122">예제 파일을 사용하여 모델의 효율성을 테스트 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-122">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="57b2a-123">모델을 게시 한 후 콘텐츠 센터를 사용하여 액세스 권한이 있는 모든 SharePoint 문서 라이브러리에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57b2a-123">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  



## <a name="see-also"></a><span data-ttu-id="57b2a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57b2a-124">See Also</span></span>
[<span data-ttu-id="57b2a-125">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="57b2a-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="57b2a-126">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="57b2a-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="57b2a-127">콘텐츠 센터 만들기</span><span class="sxs-lookup"><span data-stu-id="57b2a-127">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="57b2a-128">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="57b2a-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="57b2a-129">모델 적용</span><span class="sxs-lookup"><span data-stu-id="57b2a-129">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="57b2a-130">문서 이해와 양식 처리 모델의 차이</span><span class="sxs-lookup"><span data-stu-id="57b2a-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="57b2a-131">양식 처리 개요</span><span class="sxs-lookup"><span data-stu-id="57b2a-131">Form processing overview</span></span>](form-processing-overview.md)
