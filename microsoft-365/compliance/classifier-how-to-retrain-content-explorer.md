---
title: 콘텐츠 탐색기에서 분류자를 재학습하는 방법
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
description: 콘텐츠 탐색기에서 학습 가능한 분류자에 피드백을 제공하는 방법을 학습합니다.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793067"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="ba880-103">콘텐츠 탐색기에서 분류자를 재학습하는 방법</span><span class="sxs-lookup"><span data-stu-id="ba880-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="ba880-104">학습 가능한 Microsoft 365 분류자인 도구는 살펴보기 위한 샘플을 제공하여 다양한 유형의 콘텐츠를 인식하는 데 사용할 수 있는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="ba880-105">교육이 이행된 후 이를 사용하여 민감도 레이블, 커뮤니케이션 준수 정책 및 보존 Office 적용하기 위한 항목을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="ba880-106">이 문서에서는 사용자 지정 학습 가능한 분류자 및 사전 학습된 일부 분류자에 대한 추가 피드백을 제공하여 성능을 개선하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="ba880-107">다양한 분류자 유형에 대한 자세한 내용은 학습 가능한 분류자에 대해 자세히 [알아보기를 참조합니다.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="ba880-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="ba880-108">조정 및 재실행 프로세스에 대한 간단한 요약은 이 비디오를 시청하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba880-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="ba880-109">자세한 내용을 확인하려면 이 전체 문서를 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="ba880-110">사용 권한</span><span class="sxs-lookup"><span data-stu-id="ba880-110">Permissions</span></span>

<span data-ttu-id="ba880-111">규정 준수 센터에서 분류자에 Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="ba880-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="ba880-112">분류자 교육을 위해 규정 준수 관리자 역할 또는 준수 데이터 관리자 필요</span><span class="sxs-lookup"><span data-stu-id="ba880-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="ba880-113">이러한 시나리오에서 분류기를 사용하려면 다음 권한이 있는 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="ba880-114">보존 레이블 정책 시나리오: 레코드 관리 및 보존 관리 역할</span><span class="sxs-lookup"><span data-stu-id="ba880-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="ba880-115">전체 워크플로</span><span class="sxs-lookup"><span data-stu-id="ba880-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba880-116">콘텐츠 탐색기에서 보존 레이블 정책을 자동으로 적용하기 위한 피드백을 Exchange 분류기를 조건으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="ba880-117">**보존 레이블을 항목에 자동으로 적용하고 분류기를 조건으로 Exchange 보존 정책이 없는 경우 여기에서 중지하세요.**</span><span class="sxs-lookup"><span data-stu-id="ba880-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="ba880-118">분류기를 사용할 때 분류의 정밀도를 높이는 것이 더 나을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="ba880-119">이 작업을 위해 일치하는 항목으로 식별되거나 일치하지 않은 항목의 분류 품질을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="ba880-120">분류자에 대해 30회 평가를 수행한 후 해당 피드백을 반영하고 자동으로 재조정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="ba880-121">분류자 재시도의 전체 워크플로에 대한 자세한 내용은 분류자 재조정을 위한 프로세스 흐름을 [참조하세요.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="ba880-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="ba880-122">분류자는 이미 게시되어 있으며 사용 중이면 다시 강의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="ba880-123">콘텐츠 탐색기에서 분류자를 재학습하는 방법</span><span class="sxs-lookup"><span data-stu-id="ba880-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="ba880-124">규정 준수 Microsoft 365 또는 보안 관리자 역할 액세스로 규정 준수 센터에 로그인하고 Microsoft 365 **데이터** 분류 콘텐츠 탐색기를  >    >  **를 니다.**</span><span class="sxs-lookup"><span data-stu-id="ba880-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="ba880-125">레이블, **정보** 유형 또는 범주에 대한 필터 목록에서 교육 가능한 **분류자 를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba880-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba880-126">집계된 항목이 학습 가능한 분류자 제목 아래에 표시될 경우 최대 8일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="ba880-127">보존 레이블 정책을 자동 적용하는 데 사용한 학습 가능한 분류자 선택</span><span class="sxs-lookup"><span data-stu-id="ba880-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="ba880-128">피드백을 제공하면 교육 가능한 분류자입니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="ba880-129">항목에 보존 레이블 열에  항목이 있는 경우 항목이 로 분류된 `match` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="ba880-130">항목에 보존 레이블 열에 항목이  없는 경우 항목은 으로 분류된 `close match` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="ba880-131">항목에 대한 피드백을 제공하여 분류자 정밀도를 가장 향상시킬 수 `close match` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="ba880-132">항목을 선택하고 여는 경우</span><span class="sxs-lookup"><span data-stu-id="ba880-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="ba880-133">여러 항목을 모두 선택한 다음 명령 표시줄에서 분류 개선을 선택하여 동시에 피드백을 **제공할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="ba880-134">의견 **제공 을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba880-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="ba880-135">세부 **피드백 창에서** 항목이 실제 양수이면 일치를 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="ba880-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="ba880-136">항목이 가을 긍정이면 범주에 잘못 포함되었습니다. **일치하지 않음을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba880-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="ba880-137">항목에 더 적합한 다른 분류자가 있는 경우 교육 가능한 다른 분류자 제안 목록에서 선택할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="ba880-138">이렇게 하면 다른 분류자는 항목을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="ba880-139">피드백 **보내기를** 선택하면 , 분류에 대한 평가를 보내고 교육 가능한 다른 분류자 제안을 `match` 할 수 `not a match` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="ba880-140">분류자에 30개 피드백 인스턴스를 제공하면 자동으로 재조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="ba880-141">재조정은 1시간에서 4시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="ba880-142">분류자에는 하루 두 번만 재조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba880-143">이 정보는 테넌트의 분류자로 이동하고 **Microsoft로 돌아가지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="ba880-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="ba880-144">교육 **가능한 분류자 를 열기**</span><span class="sxs-lookup"><span data-stu-id="ba880-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="ba880-145">통신 준수 정책에 사용된 분류자는 재교육 제목 **아래에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![재조정 상태의 분류자](../media/classifier-retraining.png)

11. <span data-ttu-id="ba880-147">재 교육이 완료되면 분류기를 선택해 재 교육 개요를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![분류자 재조정 결과 개요](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="ba880-149">권장 작업과 재실행 및 현재 게시된 분류자 버전의 예측 비교를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="ba880-150">재작성 결과가 만족스러우면 다시 **게시를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba880-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="ba880-151">재실행 결과에 만족하지 않는 경우 콘텐츠 탐색기 인터페이스에서 분류자에 추가 피드백을 제공하고 다른 재실행 주기를 시작하거나, 현재 게시된 분류자 버전이 계속 사용되는 경우 아무 것도 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Content Explorer interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="ba880-152">추천 다시 게시에 대한 세부 정보</span><span class="sxs-lookup"><span data-stu-id="ba880-152">Details on republishing recommendations</span></span>

<span data-ttu-id="ba880-153">다음은 재구성된 분류자 다시 게시 또는 추가 재실행을 제안하기 위한 권장을 수식화하는 방법에 대한 약간의 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="ba880-154">이를 위해서는 학습 가능한 분류자 작동 방법을 좀 더 깊이 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="ba880-155">재조정 후 피드백이 있는 항목과 원래 분류자 교육에 사용된 항목 둘 다에서 분류자 성능을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="ba880-156">기본 제공 모델의 경우 분류자 교육에 사용되는 항목은 Microsoft에서 모델을 빌드하는 데 사용하는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="ba880-157">사용자 지정 모델의 경우 원래 교육에 사용된 항목 분류자는 테스트 및 검토를 위해 추가한 사이트의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="ba880-158">재실행 및 게시된 분류자에 대한 두 항목 집합의 성능 수를 비교하여 다시 게시하기 위한 개선이 있는지 여부를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="ba880-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="ba880-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba880-159">See also</span></span>

- [<span data-ttu-id="ba880-160">학습 가능한 분류자에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="ba880-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="ba880-161">SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="ba880-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)