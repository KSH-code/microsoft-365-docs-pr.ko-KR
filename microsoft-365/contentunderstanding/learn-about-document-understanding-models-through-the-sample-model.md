---
title: 샘플 모델을 통해 문서 이해 모델 알아보기
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 샘플 모델을 통해 문서 이해 모델 알아보기
ms.openlocfilehash: 75e17c8075fa381c68b6f85e0dfbe96e5d2ad557
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321268"
---
# <a name="learn-about-document-understanding-models-through-a-sample-model"></a><span data-ttu-id="403a7-103">샘플 모델을 통해 문서 이해 모델 알아보기</span><span class="sxs-lookup"><span data-stu-id="403a7-103">Learn about document understanding models through a sample model</span></span>

<span data-ttu-id="403a7-104">Microsoft SharePoint Syntex에서 제공하는 샘플 모델을 사용하여 사용자가 모델을 직접 작성하는 방법에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-104">Microsoft SharePoint Syntex provides you a with a sample model you can use to examine, giving you a better understanding of how to create your own models.</span></span> <span data-ttu-id="403a7-105">샘플 모델을 사용하여 분류자, 추출자 및 설명자와 같은 모델 구성 요소를 검토할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-105">The sample model also allows you to examine model components, such as its classifier, extractors, and explanations.</span></span> <span data-ttu-id="403a7-106">샘플 파일을 사용하여 모델을 훈련 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-106">You can also use the sample files to train the model.</span></span>

## <a name="import-the-sample-model"></a><span data-ttu-id="403a7-107">샘플 모델 가져오기</span><span class="sxs-lookup"><span data-stu-id="403a7-107">Import the sample model</span></span>

<span data-ttu-id="403a7-108">샘플 모델에 액세스 하려면 먼저 모델을 콘텐츠 센터로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-108">To access the sample model, you need to first import the model to your content center.</span></span>

1. <span data-ttu-id="403a7-109">콘텐츠 센터에서 모델 목록을 보려면 **모델**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-109">From the content center, select **Models** to see your models list.</span></span></br>
2. <span data-ttu-id="403a7-110">**모델** 페이지에서 **샘플 모델 가져오기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-110">On the **Models** page, select **Import sample model**.</span></span></br>

    ![샘플 모델 가져오기](../media/content-understanding/import-sample-model.png) </br>

3. <span data-ttu-id="403a7-112">가져오기가 완료되면 **BenefitsChangeNotice** 모델 홈 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-112">When the import completes, the **BenefitsChangeNotice** model home page will open.</span></span> <span data-ttu-id="403a7-113">나중에 샘플 모델을 열어야 하는 경우 콘텐츠 센터의 모델 목록에서 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-113">If you need to open the sample model in the future, you can do this from the models list in the content center.</span></span> </br>

     ![샘플 홈 페이지](../media/content-understanding/sample-home-page.png)</br>

<span data-ttu-id="403a7-115">샘플 모델 분석을 통해 모델을 구성하는 방법에 대한 이해를 할 수 있을 뿐만 아니라 작업 모델이 더 진행 되어 다음과 같은 작업을 수행하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-115">You can not only look through analyze the sample model to get a better understanding of how the model is constructed, but as a working model can go further and do things such as:</span></span>

- <span data-ttu-id="403a7-116">다른 추출기 추가</span><span class="sxs-lookup"><span data-stu-id="403a7-116">Add a another extractor.</span></span> <span data-ttu-id="403a7-117">예를 들어 *할인율*을 추출 하는 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-117">For example, add one that extracts the *discount fee*.</span></span>
- <span data-ttu-id="403a7-118">문서 라이브러리에 모델을 적용하고 교육 파일을 업로드 하여 모델이 파일을 분류하고 데이터를 추출하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="403a7-118">Apply the model to a document library, and upload some of the training files to it to see how the model classifies files and extracts data from them.</span></span>


## <a name="see-also"></a><span data-ttu-id="403a7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="403a7-119">See Also</span></span>
[<span data-ttu-id="403a7-120">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="403a7-120">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="403a7-121">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="403a7-121">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="403a7-122">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="403a7-122">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="403a7-123">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="403a7-123">Create a form processing model</span></span>](create-a-form-processing-model.md)  
