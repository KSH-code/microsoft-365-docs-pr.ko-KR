---
title: 방법 재교육 통신 준수에서 분류자를 확인 하는 방법 (미리 보기)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 통신 준수에서 trainable 분류자에 게 의견을 제공 하는 방법을 알아봅니다.
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132356"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a><span data-ttu-id="5832c-103">방법 재교육 통신 준수에서 분류자를 확인 하는 방법 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="5832c-103">How to retrain a classifier in communications compliance (preview)</span></span>

<span data-ttu-id="5832c-104">Microsoft 365 trainable 분류자는 다양 한 유형의 콘텐츠를 확인할 수 있도록 교육을 제공 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="5832c-105">훈련을 받은 후에는이를 통해 Office 민감도 레이블, 통신 준수 정책 및 보존 레이블 정책의 응용 프로그램에 대 한 항목을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="5832c-106">이 문서에서는 사용자 지정 trainable 분류자 및 일부 미리 훈련 된 분류자의 성능을 개선 하는 방법에 대해 설명 합니다 추가 의견을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="5832c-107">서로 다른 종류의 분류자에 대 한 자세한 내용은 [trainable 분류자 (preview)에 대 한](classifier-learn-about.md)자세한 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5832c-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="5832c-108">권한</span><span class="sxs-lookup"><span data-stu-id="5832c-108">Permissions</span></span>

<span data-ttu-id="5832c-109">Microsoft 365 준수 센터의 분류자에 액세스 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="5832c-110">분류자를 교육 하려면 준수 관리자 역할 또는 준수 데이터 관리자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="5832c-111">이러한 시나리오에서 분류자를 사용 하려면 다음과 같은 권한이 있는 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="5832c-112">통신 준수 정책 시나리오: 참가자 위험 관리 관리자, 관리 검토 관리자</span><span class="sxs-lookup"><span data-stu-id="5832c-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="5832c-113">전체 워크플로</span><span class="sxs-lookup"><span data-stu-id="5832c-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5832c-114">분류자를 조건으로 사용 하는 규정 준수 솔루션에 의견을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="5832c-115">**분류자를 조건으로 사용 하는 통신 준수 정책이 없는 경우 여기에서 중지 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5832c-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="5832c-116">사용자의 분류자를 사용할 때는 자신이 수행 하는 분류의 정밀도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="5832c-117">이 작업을 수행 하려면 일치 항목이 아닌 것으로 식별 된 항목에 대해 적용 된 분류의 품질을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="5832c-118">분류자에 대해 30 개의 평가를 수행한 후에는 해당 사용자의 의견이 자동으로 retrains.</span><span class="sxs-lookup"><span data-stu-id="5832c-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="5832c-119">분류자에 대 한 재교육의 전반적인 워크플로에 대 한 자세한 내용은 [프로세스 흐름에 대해 재교육을](classifier-learn-about.md#retraining-classifiers)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5832c-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="5832c-120">분류자는 retrained 하기 전에 이미 게시 되었으며 사용 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a><span data-ttu-id="5832c-121">방법 재교육 통신 준수 정책에서 분류자를 확인 하는 방법 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="5832c-121">How to retrain a classifier in communication compliance policies (preview)</span></span>

1. <span data-ttu-id="5832c-122">분류자를 조건으로 사용 하는 통신 준수 정책을 열고 **보류** 목록에서 식별 된 항목 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="5832c-123">줄임표 (...)를 선택 하 고 **분류를 개선**합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="5832c-124">**자세한 피드백** 창에서 항목이 true 인 경우를 선택 하 고 **일치 시킵니다**.</span><span class="sxs-lookup"><span data-stu-id="5832c-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="5832c-125">항목이 가양성 인 경우 범주에 잘못 포함 된 것이 **아니면 일치 하지 않는**항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="5832c-126">항목에 더 적합 한 다른 분류자가 있는 경우에는 **다른 trainable 분류자 추천** 목록에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="5832c-127">이렇게 하면 다른 분류자가 트리거되어 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="5832c-128">여러 항목을 선택 하 고 명령 모음에서 **자세한 피드백 제공** 을 선택 하 여 동시에 한 사용자에 게 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="5832c-129">**사용자 의견 보내기를** 선택 하 여 평가를 전송 `match` 하 `not a match` 고 다른 trainable 분류자를 추천 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="5832c-130">분류자에 의견의 30 개를 제공 하면 자동으로 재교육 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="5832c-131">재교육은 1-4 시간까지 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="5832c-132">분류자는 하루에 한 번만 retrained 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5832c-133">이 정보는 테 넌 트의 분류자로 이동 되며 **Microsoft로 돌아가지**않습니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="5832c-134">**Microsoft 365 준수 센터**에서 **데이터 분류** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="5832c-135">**Trainable 분류자 (미리 보기)** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-135">Open **Trainable classifiers (preview)**.</span></span>
8. <span data-ttu-id="5832c-136">통신 준수 정책에 사용 된 분류자는 **트레이닝 재** 된 제목 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![재교육 상태의 분류자](../media/classifier-retraining.png)

9. <span data-ttu-id="5832c-138">재교육이 완료 되 면 해당 분류자를 선택 하 여 재교육 개요를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![분류자 재교육 결과 개요](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="5832c-140">Retrained 및 현재 게시 된 버전의 분류자에 대 한 권장 작업 및 예측 비교를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="5832c-141">재교육의 결과가 만족 스 러 우면 **다시 게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="5832c-142">재교육 결과에 만족 하지 않는 경우에는 통신 준수 인터페이스의 분류자에 추가 피드백을 제공 하 고, 다른 재교육 주기를 시작 하거나, 현재 게시 된 버전의 분류자를 계속 사용 하는 경우에는 아무 작업도 수행 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="5832c-143">재게시 권장 사항에 대 한 세부 정보</span><span class="sxs-lookup"><span data-stu-id="5832c-143">Details on republishing recommendations</span></span>

<span data-ttu-id="5832c-144">다음은 retrained 분류자를 다시 게시 하거나 추가 재교육을 제안 하는 방법에 대 한 간단한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="5832c-145">이를 위해서는 trainable 분류자의 작동 방식에 대해 자세히 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="5832c-146">재교육 후에는 피드백을 사용 하 여 각 항목의 분류자 성과, 원래 분류자를 훈련 시키는 데 사용 되는 모든 항목을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="5832c-147">기본 제공 모델의 경우 분류자를 성향 습득 하는 데 사용 되는 항목은 Microsoft에서 모델을 구축 하는 데 사용 하는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="5832c-148">사용자 지정 모델의 경우 분류자의 원래 교육에서 사용 되는 항목은 테스트 및 검토를 위해 추가한 사이트에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="5832c-149">Retrained 및 게시 된 분류자에 대 한 두 항목 집합의 성능 수치를 비교 하 여 다시 게시할 수 있는지 여부에 대 한 권장 사항을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5832c-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="5832c-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5832c-150">See also</span></span>

- [<span data-ttu-id="5832c-151">Trainable 분류자에 대 한 자세한 정보 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="5832c-151">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="5832c-152">SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="5832c-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
