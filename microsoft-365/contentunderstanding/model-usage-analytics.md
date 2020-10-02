---
title: 문서 이해 모델 사용 분석
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 문서 이해 모델에 보존 레이블을 적용하는 방법 알아보기
ms.openlocfilehash: 26e8aea3ef52e9d850dea2f2268858d8367f7408
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321280"
---
# <a name="document-understanding-model-usage-analytics"></a><span data-ttu-id="53fb9-103">문서 이해 모델 사용 분석</span><span class="sxs-lookup"><span data-stu-id="53fb9-103">Document understanding model usage analytics</span></span>

<span data-ttu-id="53fb9-104">Microsoft SharePoint Syntex 콘텐츠 센터는 콘텐츠 센터에서 게시 된 모델이 어떻게 사용 되는지에 대한 더 많은 정보를 제공 하기 위해 모델 사용 분석을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="53fb9-104">Your Microsoft SharePoint Syntex content center provides you model usage analytics to provide more information about how your models that have been published from the content center are being used.</span></span> <span data-ttu-id="53fb9-105">여기에는 다음의 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="53fb9-105">This includes a roll-up of the following information:</span></span>

- <span data-ttu-id="53fb9-106">모델이 적용 되는 곳</span><span class="sxs-lookup"><span data-stu-id="53fb9-106">Where your models are being applied</span></span>
- <span data-ttu-id="53fb9-107">시간이 지남에 따라 몇 개의 파일이 프로세스 되는지</span><span class="sxs-lookup"><span data-stu-id="53fb9-107">How many files are being processes over time</span></span>

 ![모델 분석](../media/content-understanding/model-analytics.png) </br>

## <a name="total-model-percentage"></a><span data-ttu-id="53fb9-109">총 모델 백분율</span><span class="sxs-lookup"><span data-stu-id="53fb9-109">Total model percentage</span></span>

   ![총 모델 백분율](../media/content-understanding/total-model-percentage.png) </br>

<span data-ttu-id="53fb9-111">**총 모델 백분율** 파이 차트는 게시된 각 모델을 콘텐츠 센터에서 게시된 모델에 의해 총 프로세스된 파일에 대한 백분율을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="53fb9-111">The **Total model percentage** pie chart displays each published model as a percentage of the total files processed by all published models on the content center.</span></span>

<span data-ttu-id="53fb9-112">각 모델은 모델에 의해 성공적으로 분석된 업로드 된 파일의 백분율인 **완성율**을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="53fb9-112">Each model also shows the **Completeness Rate**, the percentage of uploaded files that were successfully analyzed by the model.</span></span> <span data-ttu-id="53fb9-113">낮은 완성율은 모델 혹은 분석된 파일에 문제가 있음을 의미 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53fb9-113">A low completeness rate may mean that there are issues with either the model or the files that are being analyzed.</span></span>

## <a name="files-processed-over-time"></a><span data-ttu-id="53fb9-114">시간에 따라 처리 된 파일</span><span class="sxs-lookup"><span data-stu-id="53fb9-114">Files processed over time</span></span>

   ![처리 된 파일](../media/content-understanding/files-processed-over-time.png) </br>

<span data-ttu-id="53fb9-116">**시간에 따라 처리된 파일** 바 차트는 각 모델에서 시간에 따라 처리된 파일만을 보여주는 것이 아니라 어떤 모델이 적용 되었는지에 대한 문서 라이브러리도 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="53fb9-116">The **Files processed over time** bar chart shows you not only the number of files processed over time for each model, but also shows you the document libraries to which the model was applied.</span></span>

   ![바 차트](../media/content-understanding/bar-chart-models.png) </br>

## <a name="see-also"></a><span data-ttu-id="53fb9-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53fb9-118">See Also</span></span>
[<span data-ttu-id="53fb9-119">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="53fb9-119">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="53fb9-120">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="53fb9-120">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="53fb9-121">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="53fb9-121">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="53fb9-122">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="53fb9-122">Create a form processing model</span></span>](create-a-form-processing-model.md)  
