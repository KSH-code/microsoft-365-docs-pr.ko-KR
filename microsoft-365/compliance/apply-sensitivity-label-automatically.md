---
title: 민감도 레이블을 콘텐츠에 자동으로 적용
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 민감도 레이블을 만들 때 문서 또는 전자 메일에 레이블을 자동으로 할당하거나 사용자에게 권장 레이블을 선택하라는 메시지를 표시할 수 있습니다.
ms.openlocfilehash: a1ea81bf8c65d3f54d26b19eae3b590f11283c30
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277215"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="b2f04-103">민감도 레이블을 콘텐츠에 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="b2f04-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="b2f04-104">민감도 레이블을 만들 때 민감한 정보가 포함된 콘텐츠에 해당 레이블을 자동으로 할당하거나 사용자에게 권장 레이블을 적용하라는 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-104">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="b2f04-105">콘텐츠에 자동으로 민감도 레이블을 적용하는 기능도 다음과 같은 이유로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="b2f04-106">사용자에게 모든 분류를 교육할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="b2f04-107">모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="b2f04-108">사용자가 더 이상 정책을 알아야 할 필요가 없으며, 그 대신 업무에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="b2f04-109">Windows용 Office 앱의 자동 레이블 지정은 Azure Information Protection 통합 레이블 클라이언트에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-109">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="b2f04-110">Office 앱에서 기본 제공되는 레이블 지정 기능은 [일부 앱에서 미리 볼 수 있습니다.](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)</span><span class="sxs-lookup"><span data-stu-id="b2f04-110">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="b2f04-111">[민감도 레이블을 만들거나 편집](create-sensitivity-labels.md)할 경우 Office 앱에 대한 자동 레이블 지정 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-111">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![민감도 레이블에 대한 자동 레이블 지정 옵션](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="b2f04-113">Office 앱에 대한 자동 레이블 지정을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="b2f04-113">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="b2f04-114">민감도 레이블의 가장 강력한 기능 중 하나는 특정 조건과 일치하는 콘텐츠에 자동으로 레이블을 적용하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="b2f04-115">이 경우 조직의 사용자는 민감도 레이블을 적용할 필요가 없습니다. Office 365에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-115">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="b2f04-116">해당 콘텐츠가 특정 유형의 중요한 정보를 포함하는 경우 자동으로 민감도 레이블을 콘텐츠에 적용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-116">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="b2f04-117">중요한 정보 유형 또는 분류자 목록에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-117">Choose from a list of sensitive info types or classifers:</span></span>

![Office 앱에서 자동 레이블 지정에 대한 레이블 조건](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="b2f04-119">현재 **분류자**의 옵션은 제한된 미리 보기 상태이며, 테넌트에 대해 이 기능을 사용하려면 Microsoft에 양식을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-119">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="b2f04-120">자세한 내용은 블로그 포스트 [기본 제공되는 분류자를 사용하여 Office 앱에서 자동 레이블 지정 발표 - 제한된 미리보기](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2f04-120">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="b2f04-121">이 민감도 레이블이 자동으로 적용되면 사용자는 Office 앱에서 알림을 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-121">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="b2f04-122">**OK**를 선택하여 알림을 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-122">They can choose **OK** to dismiss the notification.</span></span>

![문서에 레이블이 자동 적용되었다는 알림](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="b2f04-124">레이블에 대한 중요한 정보 유형 구성</span><span class="sxs-lookup"><span data-stu-id="b2f04-124">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="b2f04-125">**중요한 정보 유형** 옵션을 선택하면 DLP(데이터 손실 방지) 정책을 만들 때 같은 중요한 정보 유형 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-125">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="b2f04-126">예를 들어 신용 카드 번호 또는 주민등록번호와 같은 고객의 PII(개인 식별 정보)를 포함하는 모든 콘텐츠에 자동으로 기밀 유지 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-126">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Office 앱에서 자동 레이블 지정을 위한 중요한 정보 유형](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="b2f04-128">중요한 정보 유형을 선택하면 인스턴스 수 또는 일치 정확도를 변경하여 조건을 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-128">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="b2f04-129">자세한 내용은 [규칙을 조정하여 더욱 쉽게 또는 더욱 일치하기 어렵게 하기](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2f04-129">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="b2f04-130">또한 조건이 모든 민감 정보 유형을 감지해야 하는지 또는 한 가지 유형만 감지하면 되는지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-130">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="b2f04-131">조건을 더 유연하게 만들거나 복잡하게 만들려면 그룹을 추가하고 그룹 간에 논리 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-131">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="b2f04-132">자세한 내용은 [그룹화 및 논리 연산자](data-loss-prevention-policies.md#grouping-and-logical-operators)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2f04-132">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![인스턴스 개수 및 일치 정확도 옵션](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="b2f04-134">레이블의 분류자 구성</span><span class="sxs-lookup"><span data-stu-id="b2f04-134">Configuring classifers for a label</span></span>

<span data-ttu-id="b2f04-135">**분류자** 옵션을 선택하는 경우 기본 제공 분류자를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-135">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![분류자 및 민감도 레이블 옵션](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="b2f04-137">이러한 분류자에 대한 자세한 내용은 [교육 가능한 분류자 시작(미리 보기)](classifier-getting-started-with.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2f04-137">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="b2f04-138">미리 보기 기간 동안 다음 앱이 민감도 레이블에 분류자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-138">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="b2f04-139">[Office Insider](https://office.com/insider)의 Windows용 Office 365 ProPlus 데스크톱 앱:</span><span class="sxs-lookup"><span data-stu-id="b2f04-139">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="b2f04-140">Word</span><span class="sxs-lookup"><span data-stu-id="b2f04-140">Word</span></span>
    - <span data-ttu-id="b2f04-141">Excel</span><span class="sxs-lookup"><span data-stu-id="b2f04-141">Excel</span></span>
    - <span data-ttu-id="b2f04-142">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b2f04-142">PowerPoint</span></span>

- <span data-ttu-id="b2f04-143">[SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블을 사용(공개 미리보기)](sensitivity-labels-sharepoint-onedrive-files.md)하는 경우 웹 앱용 Office:</span><span class="sxs-lookup"><span data-stu-id="b2f04-143">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="b2f04-144">Word</span><span class="sxs-lookup"><span data-stu-id="b2f04-144">Word</span></span>
    - <span data-ttu-id="b2f04-145">Excel</span><span class="sxs-lookup"><span data-stu-id="b2f04-145">Excel</span></span>
    - <span data-ttu-id="b2f04-146">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b2f04-146">PowerPoint</span></span>
    - <span data-ttu-id="b2f04-147">Outlook</span><span class="sxs-lookup"><span data-stu-id="b2f04-147">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="b2f04-148">사용자가 민감도 레이블을 적용할 것을 권장합니다</span><span class="sxs-lookup"><span data-stu-id="b2f04-148">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="b2f04-149">원하는 경우 사용자에게 레이블을 적용할 것을 권장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-149">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="b2f04-150">이 옵션을 사용하면 사용자가 분류 및 관련 보호를 수락하거나, 레이블이 콘텐츠에 적합하지 않은 경우에는 권장 사항을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-150">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

<span data-ttu-id="b2f04-151">Word, PowerPoint 및 Excel에서 권장 레이블이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-151">Recommended labels are supported for Word, PowerPoint, and Excel.</span></span>

![사용자에게 민감도 레이블 권장 옵션](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="b2f04-p110">다음은 사용자 지정 정책 팁을 사용하여 레이블을 맞춤 정책 팁과 함께 권장 작업으로 적용하도록 조건을 구성 할때 프롬프트가 표시되는 예입니다. 정책 팁에 표시될 텍스트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-p110">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![권장된 레이블을 적용하라는 메시지 표시](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="b2f04-156">자동 또는 권장 레이블이 적용되는 방식</span><span class="sxs-lookup"><span data-stu-id="b2f04-156">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="b2f04-157">자동 레이블은 문서를 저장할 때는 Word, Excel 및 PowerPoint에 적용되고, 전자 메일을 보낼 때는 Outlook에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-157">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="b2f04-158">이러한 조건은 문서 및 전자 메일의 본문 텍스트와 머리글 및 바닥글에서 중요한 정보를 검색하지만, 전자 메일의 제목 줄이나 첨부 파일에서는 중요한 정보를 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-158">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="b2f04-159">이전에 수동으로 레이블을 지정했거나, 이전에 더 높은 민감도로 레이블이 자동으로 지정된 문서 및 전자 메일에는 자동 레이블 지정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-159">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="b2f04-160">문서 또는 전자 메일에는 단일 보존 레이블 외에 단일 민감도 레이블만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-160">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="b2f04-161">권장 레이블 지정은 문서를 저장할 때는 Word, Excel 및 PowerPoint에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-161">Recommended labeling applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="b2f04-162">이전에 더 높은 민감도로 레이블이 지정된 문서에는 권장 레이블 지정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-162">You can't use recommended labeling for documents that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="b2f04-163">콘텐츠에 더 높은 민감도로 레이블이 지정되면 사용자에게 권장 사항 및 정책 팁이 포함된 프롬프트가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-163">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="b2f04-164">두 개 이상 레이블에 적용했을 때 여러 조건의 평가 방식</span><span class="sxs-lookup"><span data-stu-id="b2f04-164">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="b2f04-p114">레이블은 정책에서 지정한 위치에 따라 평가되도록 정렬됩니다. 먼저 배치된 레이블은 가장 낮은 위치에 있고(가장 민감하지 않음) 마지막에 위치한 레이블은 가장 높은 위치에 배치됩니다(가장 민감합니다). 우선 순위에 대한 자세한 내용은 [레이블 우선 순위 (순서 관련 문제)](sensitivity-labels.md#label-priority-order-matters)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b2f04-p114">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="b2f04-167">상위 레이블이 자동으로 적용되거나 권장되도록 구성하지 않음</span><span class="sxs-lookup"><span data-stu-id="b2f04-167">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="b2f04-168">상위 레이블(하위 레이블이 있는 레이블)은 콘텐츠에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-168">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="b2f04-169">상위 레이블은 Azure Information Protection 통합 레이블 지정 클라이언트를 사용하는 Office 앱에서 콘텐츠에 적용되지 않으므로 상위 레이블이 자동으로 적용되거나 권장되도록 구성하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f04-169">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="b2f04-170">상위 레이블 및 하위 레이블에 대한 자세한 내용은 [하위 레이블(레이블 그룹화)](sensitivity-labels.md#sublabels-grouping-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2f04-170">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
