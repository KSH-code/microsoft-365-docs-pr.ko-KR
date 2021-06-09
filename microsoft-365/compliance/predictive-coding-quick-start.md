---
title: Advanced eDiscovery 예측 코딩 - 빠른 시작
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
description: 이 모듈에서 예측 코딩 모듈을 사용하는 방법을 Advanced eDiscovery. 이 문서에서는 예측 코딩을 사용하여 조사와 가장 관련이 있는 검토 집합의 콘텐츠를 식별하는 종단-종단 프로세스에 대해 설명합니다.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822626"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="058b0-104">빠른 시작: Advanced eDiscovery 예측 코딩(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="058b0-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="058b0-105">이 문서에서는 이 문서에서 예측 코딩 사용을 위한 빠른 시작을 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="058b0-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="058b0-106">Advanced eDiscovery 코딩 모듈은 Advanced eDiscovery 지능형 기계 학습 기능을 사용하여 검토할 콘텐츠의 양을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="058b0-107">예측 코딩을 사용하면 대량의 사례 콘텐츠를 검토에 우선 순위를 지정할 수 있는 관련 항목 집합으로 줄이고 선형화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="058b0-108">이 작업을 수행하기 위해 검토 집합에서 가장 관련성이 높은 항목의 검토 우선 순위를 지정하는 데 도움이 되는 자체 예측 코딩 모델을 만들고 교육할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="058b0-109">다음은 예측 코딩 프로세스에 대한 간략한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-109">Here's an a quick overview of the predictive coding process:</span></span>

![예측 코딩을 위한 빠른 시작 프로세스](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="058b0-111">시작하기 위해 관련성 또는 관련성이 없는 항목 50개만 레이블을 지정하는 모델을 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="058b0-112">그러면 시스템은 이 교육을 사용하여 검토 집합의 모든 항목에 예측 점수를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="058b0-113">이렇게 하면 예측 점수에 따라 항목을 필터링할 수 있습니다. 이를 통해 가장 관련성 있는(또는 관련이 없는) 항목을 먼저 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="058b0-114">더 높은 정보 및 회수율을 사용하여 모델을 교육하려는 경우 모델이 안정화될 때까지 후속 교육 라운드에서 항목에 레이블을 지정하는 것을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="058b0-115">모델이 안정화되면 최종 예측 필터를 적용하여 검토할 항목의 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="058b0-116">예측 코딩에 대한 자세한 개요는 에서 예측 코딩에 대해 자세히 [Advanced eDiscovery.](predictive-coding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="058b0-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="058b0-117">1단계: 새로운 예측 코딩 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="058b0-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="058b0-118">첫 번째 단계는 검토 집합에서 새로운 예측 코딩 모델을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="058b0-119">규정 Microsoft 365 센터에서 Advanced eDiscovery 사례를 열고 검토 집합 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="058b0-120">검토 집합을 열고 **분석** 예측 코딩 관리(미리  >  **보기)를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![검토 집합에서 분석 드롭다운 메뉴를 클릭하여 예측 코딩 페이지로 이동합니다.](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="058b0-122">예측 코딩 **모델(미리 보기) 페이지에서** 새 모델을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="058b0-123">플라이아웃 페이지에서 모델의 이름과 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="058b0-124">**저장을** 클릭하여 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="058b0-125">시스템에서 모델을 준비하는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="058b0-126">준비가 된 후 첫 번째 교육을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="058b0-127">자세한 지침은 예측 코딩 모델 [만들기를 참조하세요.](predictive-coding-create-model.md)</span><span class="sxs-lookup"><span data-stu-id="058b0-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="058b0-128">2단계: 첫 번째 교육 라운드 수행</span><span class="sxs-lookup"><span data-stu-id="058b0-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="058b0-129">모델을 만든 후의 다음 단계는 관련성 또는 관련성이 없는 항목에 레이블을 지정하여 첫 번째 교육 라운드를 완료하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="058b0-130">검토 집합을 열고 **분석** 예측 코딩 관리(미리  >  **보기)를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="058b0-131">예측 코딩 **모델(미리 보기)** 페이지에서 학습할 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="058b0-132">개요 **탭의** **1라운드에서** 다음 교육 **라운드 시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="058b0-133">교육 **탭이** 표시되고 레이블을 지정하는 데 사용할 50개 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="058b0-134">각 문서를 검토한  다음  읽기 창 아래쪽의 관련성 또는 관련이 없는 단추를 선택하여 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![각 문서에 관련성 또는 관련이 없는 것으로 레이블 지정](..\media\TrainModel1.png)

5. <span data-ttu-id="058b0-136">50개 항목에 모두 레이블을 지정한 후 마친 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="058b0-137">시스템이 레이블 지정에서 "학습"하고 모델을 업데이트하는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="058b0-138">이 프로세스가 완료되면 모델에  대한 준비 상태가 예측 코딩 모델(미리 **보기) 페이지에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="058b0-139">자세한 지침은 예측 코딩 모델 [교육을 참조하세요.](predictive-coding-train-model.md)</span><span class="sxs-lookup"><span data-stu-id="058b0-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="058b0-140">3단계: 검토 집합의 항목에 예측 점수 필터 적용</span><span class="sxs-lookup"><span data-stu-id="058b0-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="058b0-141">한 번의 교육 라운드 임대를 수행한 후 검토 집합의 항목에 예측 점수 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="058b0-142">이렇게 하면 모델이 관련성이 있는 것으로 예측한 항목을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="058b0-143">검토 집합을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-143">Open the review set.</span></span>

   ![필터를 클릭하여 필터 플라이아웃 페이지 표시](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="058b0-145">미리 로드된 기본 필터는 검토 집합 페이지 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="058b0-146">이러한 집합을 Any로 설정할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="058b0-147">필터를 클릭하여 **필터 플라이아웃** 페이지를 표시합니다. </span><span class="sxs-lookup"><span data-stu-id="058b0-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="058b0-148">분석 & **코딩 섹션을** 확장하여 필터 집합을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![분석 및 예측 & 섹션의 예측 점수 필터](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="058b0-150">예측 점수 필터의 명명 규칙은 **예측 점수(모델 이름)입니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="058b0-151">예를 들어 Model **A라는** 모델의 예측 점수 필터 이름은 예측 **점수(모델 A)입니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="058b0-152">사용할 예측 점수 필터를 선택하고 완료 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="058b0-153">검토 집합 페이지에서 예측 점수 필터에 대한 드롭다운을 클릭하고 예측 점수 범위에 대한 최소값 및 최대값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="058b0-154">예를 들어 다음 스크린샷에는 **.5에서 1.0** 사이의 예측 점수 **범위가 나와 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="058b0-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![예측 점수 필터의 최소값 및 최대값](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="058b0-156">필터 외부를 클릭하여 검토 집합에 필터를 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="058b0-157">지정한 범위 내에서 예측 점수가 있는 문서 목록이 검토 집합 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="058b0-158">자세한 지침은 검토 집합에 예측 [필터 적용을 참조하세요.](predictive-coding-apply-prediction-filter.md)</span><span class="sxs-lookup"><span data-stu-id="058b0-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="058b0-159">4단계: 추가 교육 라운드 수행</span><span class="sxs-lookup"><span data-stu-id="058b0-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="058b0-160">더 많은 교육 라운드를 수행하여 검토 집합의 관련성 및 비관련 항목을 더 잘 예측하도록 모듈을 교육해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="058b0-161">일반적으로 모델이 요구 사항을 충족하기에 충분히 안정화될 때까지 충분한 시간을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="058b0-162">자세한 내용은 추가 교육 [라운드 수행을 참조하세요.](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="058b0-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="058b0-163">5단계: 최종 예측 점수 필터를 적용하여 검토 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="058b0-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="058b0-164">3단계의 지침을 반복하여 최종 예측 점수를 검토 집합에 적용하여 모든 교육 라운드를 완료하고 모델을 안정화한 후 관련 및 관련이 없는 항목의 검토 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="058b0-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
