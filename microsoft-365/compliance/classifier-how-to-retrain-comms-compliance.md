---
title: 커뮤니케이션 준수에서 분류자를 재학습하는 방법
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
description: 커뮤니케이션 규정 준수에서 학습 가능한 분류자에 피드백을 제공하는 방법을 학습합니다.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752652"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="feb99-103">커뮤니케이션 준수에서 분류자를 재학습하는 방법</span><span class="sxs-lookup"><span data-stu-id="feb99-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="feb99-104">Microsoft 365 학습 가능한 분류자는 다양한 유형의 콘텐츠를 인식할 수 있는 도구로, 살펴보기 위한 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="feb99-105">교육이 이행된 후 이를 사용하여 Office 민감도 레이블, 커뮤니케이션 준수 정책 및 보존 레이블 정책의 적용을 위한 항목을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="feb99-106">이 문서에서는 사용자 지정 학습 가능한 분류자 및 사전 학습된 일부 분류자에 대한 성능을 개선하는 방법을 보여 주며 추가 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="feb99-107">다양한 분류자 유형에 대한 자세한 내용은 학습 가능한 분류자에 [대한 자세한 내용을 참조합니다.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="feb99-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="feb99-108">사용 권한</span><span class="sxs-lookup"><span data-stu-id="feb99-108">Permissions</span></span>

<span data-ttu-id="feb99-109">Microsoft 365 규정 준수 센터에서 분류자에 액세스하는 경우:</span><span class="sxs-lookup"><span data-stu-id="feb99-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="feb99-110">분류자 교육을 위해 규정 준수 관리자 역할 또는 준수 데이터 관리자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="feb99-111">이러한 시나리오에서 분류기를 사용하려면 다음 권한이 있는 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="feb99-112">커뮤니케이션 준수 정책 시나리오: 내부자 위험 관리 관리자, 관리 검토 관리자</span><span class="sxs-lookup"><span data-stu-id="feb99-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="feb99-113">전체 워크플로</span><span class="sxs-lookup"><span data-stu-id="feb99-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="feb99-114">분류기를 조건으로 사용하는 준수 솔루션에 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="feb99-115">**분류기를 조건으로 사용하는 통신 준수 정책이 없는 경우 여기에서 중지하세요.**</span><span class="sxs-lookup"><span data-stu-id="feb99-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="feb99-116">분류기를 사용할 때 분류하는 분류의 정밀도를 높이는 것이 더 나을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="feb99-117">이 작업을 위해 일치하는 것으로 식별된 항목에 대해 만들어진 분류의 품질을 평가하거나 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="feb99-118">분류자에 대해 30회 평가를 수행한 후 해당 피드백을 반영하고 자동으로 자체적으로 다시 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="feb99-119">분류자 재조정의 전체 워크플로에 대한 자세한 내용은 분류자 재조정에 대한 프로세스 흐름을 [참조하세요.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="feb99-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="feb99-120">분류자는 이미 게시되어 있으며 사용 중이면 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="feb99-121">통신 준수 정책에서 분류자 재조정 방법</span><span class="sxs-lookup"><span data-stu-id="feb99-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="feb99-122">분류기를 조건으로 사용하는 통신 준수 정책을 열고 보류 중인 목록에서 식별된 항목 중 **하나를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="feb99-123">타원을 선택하고 **분류를 개선합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb99-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="feb99-124">세부 **피드백 창에서** 항목이 실제 양수이면 일치 항목을 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="feb99-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="feb99-125">항목이 범주에 잘못 포함되어 있는 경우 일치하지 **않음을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb99-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="feb99-126">항목에 더 적합한 다른 분류자인 경우 교육 가능한 다른 분류자 제안 목록에서 선택할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="feb99-127">이렇게 하면 다른 분류자에서 항목을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="feb99-128">여러 항목을 모두 선택한 다음 명령 표시줄에서  자세한 피드백 제공을 선택하여 여러 항목에 대한 피드백을 동시에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="feb99-129">피드백 **보내기를** 선택하면 평가, 분류 및 기타 학습 가능한 분류자 제안이 `match` `not a match` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="feb99-130">분류자에 30개 피드백 인스턴스를 제공하면 자동으로 재조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="feb99-131">재조정에는 1~4시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="feb99-132">분류자에는 하루 두 번만 재조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="feb99-133">이 정보는 테넌트의 분류자로 이동하고 **Microsoft로 돌아가지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="feb99-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="feb99-134">**Microsoft 365** 규정 **준수** 센터에서 데이터 분류 페이지를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="feb99-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="feb99-135">학습 **가능한 분류자 열기.**</span><span class="sxs-lookup"><span data-stu-id="feb99-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="feb99-136">커뮤니케이션 준수 정책에 사용된 분류자는 재 교육 **제목에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![재조정 상태의 분류자](../media/classifier-retraining.png)

9. <span data-ttu-id="feb99-138">재 교육이 완료되면 분류기를 선택해 다시 교육 개요를 하세요.</span><span class="sxs-lookup"><span data-stu-id="feb99-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![분류자 재조정 결과 개요](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="feb99-140">권장 작업과 재조정된 분류자 및 현재 게시된 버전의 예측 비교를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="feb99-141">재작성 결과가 만족스러우면 다시 게시를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb99-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="feb99-142">재실행 결과에 만족하지 않는 경우 통신 준수 인터페이스에서 분류자에 추가 피드백을 제공하고 다른 재조정 주기를 시작하거나, 현재 게시된 분류자 버전이 계속 사용되는 경우 아무 것도 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="feb99-143">권장 사항 다시 게시에 대한 세부 정보</span><span class="sxs-lookup"><span data-stu-id="feb99-143">Details on republishing recommendations</span></span>

<span data-ttu-id="feb99-144">다음은 재조정된 분류자 다시 게시 또는 추가 재조정을 제안하기 위한 권장을 수식화하는 방법에 대한 약간의 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="feb99-145">이를 위해서는 학습 가능한 분류자 작동 방식에 대해 좀 더 깊이 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="feb99-146">재조정 후 피드백이 있는 항목과 원래 분류자 교육에 사용된 모든 항목에 대해 분류자 성능을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="feb99-147">기본 제공 모델의 경우 분류자 학습에 사용되는 항목은 모델을 빌드하는 데 Microsoft에서 사용하는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="feb99-148">사용자 지정 모델의 경우, 원래 교육에 사용된 항목 분류자는 테스트 및 검토를 위해 추가한 사이트의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="feb99-149">재게시 및 게시된 분류자에 대한 두 항목 집합의 성능 수를 비교하여 다시 게시하기 위한 개선이 있는지 여부를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="feb99-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="feb99-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="feb99-150">See also</span></span>

- [<span data-ttu-id="feb99-151">학습 가능한 분류자에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="feb99-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="feb99-152">SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="feb99-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
