---
title: 검토 집합의 항목에 예측 점수 필터 적용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 예측 점수 필터를 사용하여 예측 코딩 모델이 관련성이 있는 것으로 예측된 항목을 표시합니다.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822594"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="7ff3c-103">검토 집합에 예측 점수 필터 적용(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="7ff3c-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="7ff3c-104">Advanced eDiscovery 예측 코딩 모델을 만들고 안정된 지점으로 교육한 후 예측 점수 필터를 적용하여 모델이 관련성이 없다고 결정한 검토 집합 항목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="7ff3c-105">모델을 만들 때 해당 예측 점수 필터도 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="7ff3c-106">이 필터를 사용하여 지정된 범위 내에서 예측 점수가 할당된 항목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="7ff3c-107">일반적으로 **0에서** **.5** 사이의 예측 점수는 모델이 예측한 항목과 관련이 없는 항목에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="7ff3c-108">**.5에서 1.0** 사이의 예측 점수가 할당된 항목은 모델이 예측한 관련 항목입니다. </span><span class="sxs-lookup"><span data-stu-id="7ff3c-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="7ff3c-109">예측 점수 필터를 사용할 수 있는 두 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="7ff3c-110">모델이 예측한 검토 집합의 항목 검토 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="7ff3c-111">모델이 예측한 리뷰 집합의 항목을 선회하는 것은 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="7ff3c-112">또는 예측 점수 필터를 사용하여 관련이 없는 항목의 검토의 우선 순위를 다시 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="7ff3c-113">예측 점수 필터를 적용하기 전에</span><span class="sxs-lookup"><span data-stu-id="7ff3c-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="7ff3c-114">해당 예측 점수 필터를 만들 수 있도록 예측 코딩 모델을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="7ff3c-115">교육 라운드 후에 예측 점수 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="7ff3c-116">그러나 여러 라운드를 수행한 후 또는 모델이 안정될 때까지 기다렸다가 예측 점수 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="7ff3c-117">예측 점수 필터 적용</span><span class="sxs-lookup"><span data-stu-id="7ff3c-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="7ff3c-118">규정 Microsoft 365 센터에서 Advanced eDiscovery 사례를 열고 검토 집합  탭을 선택한 다음 검토 집합을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![필터를 클릭하여 필터 플라이아웃 페이지 표시](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="7ff3c-120">미리 로드된 기본 필터는 검토 집합 페이지 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="7ff3c-121">이러한 집합을 Any로 설정할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7ff3c-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="7ff3c-122">필터를 클릭하여 **필터 플라이아웃** 페이지를 표시합니다. </span><span class="sxs-lookup"><span data-stu-id="7ff3c-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="7ff3c-123">분석 & **코딩 섹션을** 확장하여 필터 집합을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![분석 및 예측 & 섹션의 예측 점수 필터](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="7ff3c-125">예측 점수 필터의 명명 규칙은 **예측 점수(모델 이름)입니다.**</span><span class="sxs-lookup"><span data-stu-id="7ff3c-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="7ff3c-126">예를 들어 Model **A라는** 모델의 예측 점수 필터 이름은 예측 **점수(모델 A)입니다.**</span><span class="sxs-lookup"><span data-stu-id="7ff3c-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="7ff3c-127">사용할 예측 점수 필터를 선택하고 완료 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7ff3c-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="7ff3c-128">검토 집합 페이지에서 예측 점수 필터에 대한 드롭다운을 클릭하고 예측 점수 범위에 대한 최소값 및 최대값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="7ff3c-129">예를 들어 다음 스크린샷에는 **.5에서 1.0** 사이의 예측 점수 **범위가 나와 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7ff3c-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![예측 점수 필터의 최소값 및 최대값](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="7ff3c-131">필터 외부를 클릭하여 검토 집합에 필터를 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="7ff3c-132">지정한 범위 내에서 예측 점수가 있는 문서 목록이 검토 집합 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="7ff3c-133">문서에 할당된 실제 예측 점수를 보려면 읽기  창에서 메타데이터 탭을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="7ff3c-134">검토 집합의 모든 모델에 대한 예측 점수는 **RelevanceScores** 메타데이터 속성에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="7ff3c-135">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7ff3c-135">More information</span></span>

- <span data-ttu-id="7ff3c-136">필터 사용에 대한 자세한 내용은 검토 집합에서 콘텐츠 쿼리 및 [필터링을 참조하세요.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="7ff3c-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
