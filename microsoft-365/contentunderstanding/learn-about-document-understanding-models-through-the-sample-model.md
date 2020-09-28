---
title: 예제 모델을 통해 모델을 이해 하는 문서에 대해 자세히 알아보기
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 예제 모델을 통해 모델을 이해 하는 문서에 대해 자세히 알아보기
ms.openlocfilehash: c27d50df69c2555b1720e3e919f786076ab1e3fb
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296118"
---
# <a name="learn-about-document-understanding-models-through-a-sample-model"></a><span data-ttu-id="c1f8d-103">예제 모델을 통한 문서 이해 모델에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="c1f8d-103">Learn about document understanding models through a sample model</span></span>

<span data-ttu-id="c1f8d-104">Microsoft SharePoint Syntex에서는 사용자가 모델을 직접 만드는 방법을 보다 잘 이해할 수 있도록 하기 위해 사용 하는 샘플 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-104">Microsoft SharePoint Syntex provides you a with a sample model you can use to examine, giving you a better understanding of how to create your own models.</span></span> <span data-ttu-id="c1f8d-105">또한이 샘플 모델을 사용 하면 분류자, 추출기 및 설명과 같은 모델 구성 요소를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-105">The sample model also allows you to examine model components, such as its classifier, extractors, and explanations.</span></span> <span data-ttu-id="c1f8d-106">샘플 파일을 사용 하 여 모델을 양성 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-106">You can also use the sample files to train the model.</span></span>

## <a name="import-the-sample-model"></a><span data-ttu-id="c1f8d-107">샘플 모델 가져오기</span><span class="sxs-lookup"><span data-stu-id="c1f8d-107">Import the sample model</span></span>

<span data-ttu-id="c1f8d-108">예제 모델에 액세스 하려면 먼저 모델을 콘텐츠 센터로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-108">To access the sample model, you need to first import the model to your content center.</span></span>

1. <span data-ttu-id="c1f8d-109">콘텐츠 센터 **에서 모델을 선택 하** 여 모델 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-109">From the content center, select **Models** to see your models list.</span></span></br>
2. <span data-ttu-id="c1f8d-110">**모델** 페이지에서 **예제 모델 가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-110">On the **Models** page, select **Import sample model**.</span></span></br>

    ![가져오기 예제 모델](../media/content-understanding/import-sample-model.png) </br>

3. <span data-ttu-id="c1f8d-112">모델 목록에 표시 되는 *BenefitsChangeNotice* 의 예제 모델을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-112">Look for the sample model titled *BenefitsChangeNotice.classifier* that appears in your models list.</span></span></br>

    ![예제 모델](../media/content-understanding/sample-model.png) </br>

4. <span data-ttu-id="c1f8d-114">*BenefitsChangeNotice*를 선택 하 여 모델의 홈 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-114">Select the *BenefitsChangeNotice.classifier*, to open the model's home page.</span></span></br>
  
     ![예제 홈 페이지](../media/content-understanding/sample-home-page.png)

5. <span data-ttu-id="c1f8d-116">모델 홈 페이지에서 모델을 보다 자세히 검토 하 여 모델이 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-116">From the model home page, examine the model more closely to see how it was created.</span></span>
 
- <span data-ttu-id="c1f8d-117">모델을 학습 하는 데 사용 되는 샘플 파일을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-117">View the sample files used to train the model.</span></span>
- <span data-ttu-id="c1f8d-118">모델의 엔터티 추출기 좀 더 자세히 검토 하 여 샘플 모델이 설명을 구성 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f8d-118">Examine the model's entity extractors more closely to see how the sample model configured the explanations.</span></span>

   ![샘플 모델 추출기](../media/content-understanding/entity-extractors.png)  

## <a name="see-also"></a><span data-ttu-id="c1f8d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1f8d-120">See Also</span></span>
[<span data-ttu-id="c1f8d-121">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="c1f8d-121">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="c1f8d-122">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="c1f8d-122">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="c1f8d-123">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="c1f8d-123">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="c1f8d-124">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="c1f8d-124">Create a form processing model</span></span>](create-a-form-processing-model.md)  
