---
title: 2013에서 예측 코딩 모델 Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 84bb34f8ec1b935dc30072e16f57b5f5665c3546
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226218"
---
# <a name="train-a-predictive-coding-model-preview"></a><span data-ttu-id="e4531-102">예측 코딩 모델 교육(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e4531-102">Train a predictive coding model (preview)</span></span>

<span data-ttu-id="e4531-103">Advanced eDiscovery 예측 코딩 모델을 만든 후 다음 단계는 첫 번째 교육 라운드를 수행하여 검토 집합의 관련성 및 비관련 콘텐츠에 대한 모델을 교육하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-103">After you create a predictive coding model in Advanced eDiscovery, the next step is to performing the first training round to train the model on what is relevant and non-relevant content in your review set.</span></span> <span data-ttu-id="e4531-104">첫 번째 교육을 완료한 후 후속 교육 라운드를 수행하여 관련성 및 비관련 콘텐츠를 예측하는 모델의 능력을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-104">After you complete the first round of training, you can perform subsequent training rounds to improve the model's ability to predict relevant and non-relevant content.</span></span>

<span data-ttu-id="e4531-105">예측 코딩 워크플로를 검토하기 위해 2013에서 예측 코딩에 [대해 Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span><span class="sxs-lookup"><span data-stu-id="e4531-105">To review the predictive coding workflow, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span></span>

## <a name="before-you-train-a-model"></a><span data-ttu-id="e4531-106">모델을 교육하기 전에</span><span class="sxs-lookup"><span data-stu-id="e4531-106">Before you train a model</span></span>

- <span data-ttu-id="e4531-107">교육 라운드 중에 문서의  콘텐츠 관련성에 따라 관련성 또는 관련이 없는 항목으로 레이블을 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="e4531-107">During a training round, label items as **Relevant** or **Not relevant** based on the relevancy of the content in the document.</span></span> <span data-ttu-id="e4531-108">메타데이터 필드의 값에 따라 결정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-108">Don't base your decision on the values in the metadata fields.</span></span> <span data-ttu-id="e4531-109">예를 들어 전자 메일 메시지 또는 Teams 대화의 경우 메시지 참가자에 대한 레이블 지정 결정에 기반하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-109">For example, for email messages or Teams conversations, don't base your labeling decision on the message participants.</span></span>

## <a name="train-a-model-for-the-first-time"></a><span data-ttu-id="e4531-110">처음으로 모델 교육</span><span class="sxs-lookup"><span data-stu-id="e4531-110">Train a model for the first time</span></span>

1. <span data-ttu-id="e4531-111">이 Microsoft 365 규정 준수 센터 사례를 Advanced eDiscovery 검토 집합 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-111">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="e4531-112">검토 집합을 열고 **분석** 예측 코딩 관리(미리  >  **보기)를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e4531-112">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

3. <span data-ttu-id="e4531-113">예측 코딩 **모델(미리 보기)** 페이지에서 학습할 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-113">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

4. <span data-ttu-id="e4531-114">개요 **탭의** **1라운드에서** 다음 교육 **라운드 시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e4531-114">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="e4531-115">교육 **탭이** 표시되고 레이블을 지정하는 데 사용할 50개 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-115">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

5. <span data-ttu-id="e4531-116">각 문서를 검토한  다음  읽기 창 아래쪽의 관련성 또는 관련이 없는 단추를 선택하여 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-116">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![각 문서에 관련성 또는 관련이 없는 것으로 레이블 지정](..\media\TrainModel1.png)

6. <span data-ttu-id="e4531-118">50개 항목에 모두 레이블을 지정한 후 마친 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e4531-118">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="e4531-119">시스템이 레이블 지정에서 "학습"하고 모델을 업데이트하는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-119">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="e4531-120">이 프로세스가 완료되면 모델에  대한 준비 상태가 예측 코딩 모델(미리 **보기) 페이지에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-120">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

## <a name="perform-additional-training-rounds"></a><span data-ttu-id="e4531-121">추가 교육 라운드 수행</span><span class="sxs-lookup"><span data-stu-id="e4531-121">Perform additional training rounds</span></span>

<span data-ttu-id="e4531-122">첫 번째 교육을 수행한 후 이전 섹션의 단계를 수행하여 후속 교육 라운드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-122">After you perform the first round of training, you can perform subsequent training rounds by following the steps in the previous section.</span></span> <span data-ttu-id="e4531-123">유일한 차이점은 모델 개요 탭에서 업데이트되는 교육 라운드의 **수입니다.** 예를 들어 첫 번째 교육 라운드를  수행한 후 다음 교육 라운드 시작을 클릭하여 두 번째 교육을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-123">The only difference is the number of the training round will be updated on the model **Overview** tab. For example, after performing the first training round, you can click **Start next training round** to start the second round of training.</span></span> <span data-ttu-id="e4531-124">그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-124">And so on.</span></span>

<span data-ttu-id="e4531-125">각 교육 라운드(진행 중 및 완료된 교육)는 모델의 교육 탭에 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="e4531-125">Each round of training (both those in progress and those that are complete) is displayed on the **Training** tab for the model.</span></span> <span data-ttu-id="e4531-126">교육 라운드를 선택하면 라운드에 대한 정보와 메트릭이 있는 플라이아웃 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-126">When you select a training round, a flyout page with information and metrics for the round is displayed.</span></span>

## <a name="what-happens-after-you-perform-a-training-round"></a><span data-ttu-id="e4531-127">교육 라운드를 수행한 후 발생하는 작업</span><span class="sxs-lookup"><span data-stu-id="e4531-127">What happens after you perform a training round</span></span>

<span data-ttu-id="e4531-128">첫 번째 교육 라운드를 수행한 후 다음 작업을 수행하는 작업이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-128">After you perform the first training round, a job is started that does the following things:</span></span>

- <span data-ttu-id="e4531-129">교육 집합에서 40개 항목에 레이블을 지정한 방식에 따라 모델이 레이블 지정을 통해 학습하고 자체적으로 더 정확하게 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-129">Based on how you labeled the 40 items in the training set, the model learns from your labeling and updates itself to become more accurate.</span></span>

- <span data-ttu-id="e4531-130">그런 다음 모델은 전체 검토 집합의 각 항목을 처리하고 **0(관련되지 않은)에서** **1(관련성)** 사이의 예측 점수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-130">The model then processes each item in the entire review set and assigns a prediction score between **0** (not relevant) and **1** (relevant).</span></span>

- <span data-ttu-id="e4531-131">이 모델은 교육 라운드 중에 레이블을 지정한 컨트롤 집합의 10개 항목에 예측 점수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-131">The model assigns a prediction score to the 10 items in the control set that you labeled during the training round.</span></span> <span data-ttu-id="e4531-132">이 모델은 이러한 10개 항목의 예측 점수와 교육 라운드 중에 항목에 할당한 실제 레이블을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-132">The model compares the prediction score of these 10 items with the actual label that you assigned to the item during the training round.</span></span> <span data-ttu-id="e4531-133">이 비교에 따라 모델은 다음 분류(Control *set confusion* matrix)를 식별하여 모델의 예측 성능을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-133">Based on this comparison, the model identifies the following classification (called the *Control set confusion matrix*) to assess the model's prediction performance:</span></span>

  |          |<span data-ttu-id="e4531-134">Model predicts item is relevant</span><span class="sxs-lookup"><span data-stu-id="e4531-134">Model predicts item is relevant</span></span> |<span data-ttu-id="e4531-135">Model predicts item is not relevant</span><span class="sxs-lookup"><span data-stu-id="e4531-135">Model predicts item is not relevant</span></span> |
  |:---------|:---------|:---------|
  |<span data-ttu-id="e4531-136">**관련성 있는 검토자 레이블 항목**</span><span class="sxs-lookup"><span data-stu-id="e4531-136">**Reviewer labels item as relevant**</span></span>| <span data-ttu-id="e4531-137">참 긍정</span><span class="sxs-lookup"><span data-stu-id="e4531-137">True positive</span></span>| <span data-ttu-id="e4531-138">가양성</span><span class="sxs-lookup"><span data-stu-id="e4531-138">False positive</span></span> |
  |<span data-ttu-id="e4531-139">**관련이 없는 검토자 레이블 항목**</span><span class="sxs-lookup"><span data-stu-id="e4531-139">**Reviewer labels item as not relevant**</span></span>| <span data-ttu-id="e4531-140">거짓 부정</span><span class="sxs-lookup"><span data-stu-id="e4531-140">False negative</span></span> |<span data-ttu-id="e4531-141">True 음수</span><span class="sxs-lookup"><span data-stu-id="e4531-141">True negative</span></span> |
  ||||

  <span data-ttu-id="e4531-142">이러한 비교에 따라 모델에서는 F-점수, 정밀도 및 회수 메트릭의 값과 각 메트릭에 대한 오류 여백을 파생합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-142">Based on these comparisons, the model derives values for the F-score, precision, and recall metrics and the margin of error for each one.</span></span> <span data-ttu-id="e4531-143">이러한 모델 성능 메트릭에 대한 점수는 교육 라운드의 플라이아웃 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-143">Scores for these model performance metrics are displayed on a flyout page for the training round.</span></span> <span data-ttu-id="e4531-144">이러한 메트릭에 대한 설명은 [예측 코딩 참조를 참조하세요.](predictive-coding-reference.md)</span><span class="sxs-lookup"><span data-stu-id="e4531-144">For a description of these metrics, see [Predictive coding reference](predictive-coding-reference.md).</span></span>

- <span data-ttu-id="e4531-145">마지막으로 이 모델에서는 다음 교육 라운드에 사용할 다음 50개 항목을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-145">Finally, the model determines the next 50 items that will be used for the next training round.</span></span> <span data-ttu-id="e4531-146">이번에는 모델이 컨트롤 집합에서 20개 항목과 검토 집합의 새 항목 30개를 선택하여 다음 라운드에 대한 교육 집합으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-146">This time, the model might select 20 items from the control set and 30 new items from the review set and designate them as the training set for the next round.</span></span> <span data-ttu-id="e4531-147">다음 교육 라운드에 대한 샘플링은 균일하게 샘플링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-147">The sampling for the next training round is not uniformly sampled.</span></span> <span data-ttu-id="e4531-148">이 모델은 검토 집합에서 항목의 샘플링 선택을 최적화하여 예측이 모호한 항목을 선택합니다. 즉, 예측 점수가 0.5 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-148">The model will optimize the sampling selection of items from the review set to select items where the prediction is ambiguous, which means the prediction score is in the 0.5 range.</span></span> <span data-ttu-id="e4531-149">이 프로세스를 편향 선택 *으로 알려져 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="e4531-149">This process is known as *biased selection*.</span></span>

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a><span data-ttu-id="e4531-150">후속 교육 라운드를 수행한 후 발생하는 작업</span><span class="sxs-lookup"><span data-stu-id="e4531-150">What happens after you perform subsequent training rounds</span></span>

<span data-ttu-id="e4531-151">후속 교육 라운드(첫 번째 교육 라운드 이후)를 수행한 후 모델에서 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-151">After you perform subsequent training rounds (after the first training round), the model does the following things:</span></span>

- <span data-ttu-id="e4531-152">모델은 해당 교육 라운드에서 교육 집합에 적용한 레이블에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-152">The model is updated based on the labels that you applied to the training set in that round of training.</span></span>

- <span data-ttu-id="e4531-153">시스템은 컨트롤 집합의 항목에 대해 모델의 예측 점수를 평가하고 점수가 컨트롤 집합의 항목에 레이블을 지정한 방식에 부합하는지 여부를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-153">The system evaluates the model's prediction score on the items in the control set and check whether the score aligns with how you labeled items in the control set.</span></span> <span data-ttu-id="e4531-154">평가는 모든 교육 라운드에 대한 컨트롤 집합의 모든 레이블이 붙은 항목에 대해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-154">The evaluation is performed on all labeled items from control set for all training rounds.</span></span> <span data-ttu-id="e4531-155">이 평가 결과는 모델의 개요 탭에  있는 대시보드에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-155">The results of this evaluation are incorporated in the dashboard on the **Overview** tab for the model.</span></span>

- <span data-ttu-id="e4531-156">업데이트된 모델은 검토 집합의 모든 항목을 다시 처리하고 각 항목에 업데이트된 예측 점수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-156">The updated model reprocesses every item in the review set and assign each item an updated prediction score.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e4531-157">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e4531-157">Next steps</span></span>

<span data-ttu-id="e4531-158">첫 번째 교육 라운드를 수행한 후 더 많은 교육 라운드를 수행하거나 모델의 예측 점수 필터를 검토 집합에 적용하여 모델이 관련성이 있는 것으로 예측한 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4531-158">After you perform the first training round, you can perform more training rounds or apply the model's prediction score filter to the review set to view the items the model has predicted as relevant or not relevant.</span></span> <span data-ttu-id="e4531-159">자세한 내용은 검토 집합에 예측 점수 [필터 적용을 참조하세요.](predictive-coding-apply-prediction-filter.md)</span><span class="sxs-lookup"><span data-stu-id="e4531-159">For more information, see [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>
