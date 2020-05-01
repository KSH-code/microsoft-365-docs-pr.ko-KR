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
ms.openlocfilehash: 48e6b000110014637afbf032f81b23703a763f4d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943247"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="45c59-103">민감도 레이블을 콘텐츠에 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="45c59-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="45c59-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="45c59-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="45c59-105">민감도 레이블을 만들 때 사용자가 지정한 조건과 일치하는 경우 해당 레이블을 콘텐츠에 자동으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-105">When you create a sensitivity label, you can automatically assign that label to content when it matches conditions that you specify.</span></span>

<span data-ttu-id="45c59-106">콘텐츠에 자동으로 민감도 레이블을 적용하는 기능도 다음과 같은 이유로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-106">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="45c59-107">사용자에게 각 분류를 언제 사용할지 교육할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-107">You don't need to train your users when to use each of your classifications.</span></span>

- <span data-ttu-id="45c59-108">모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-108">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="45c59-109">사용자가 더 이상 정책을 알아야 할 필요가 없으며, 그 대신 업무에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-109">Users no longer need to know about your policies—they can instead focus on their work.</span></span>

<span data-ttu-id="45c59-110">민감도 레이블을 자동으로 적용하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-110">There are two different methods for automatically applying a sensitivity label:</span></span>

- <span data-ttu-id="45c59-111">**사용자가 문서를 편집하거나 전자 메일 작성(답장 또는 전달) 시 클라이언트 쪽 레이블 지정**: Office 앱(Word, Excel, PowerPoint 및 Outlook)에 자동 레이블 지정을 위해 구성된 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-111">**Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for Office apps (Word, Excel, PowerPoint, and Outlook).</span></span> 
    
    <span data-ttu-id="45c59-112">이 방법은 자동 레이블 적용뿐만 아니라 사용자에게 레이블을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-112">This method supports recommending a label to users, as well as automatically applying a label.</span></span> <span data-ttu-id="45c59-113">그러나 두 경우 모두 사용자가 레이블을 수락할지 또는 거부할지 결정하여 내용에 올바른 레이블을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-113">But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content.</span></span> <span data-ttu-id="45c59-114">이 클라이언트 쪽 레이블에는 문서가 저장되기 전에 레이블을 지정할 수 있으므로 문서에 대한 지연 시간이 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-114">This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved.</span></span> <span data-ttu-id="45c59-115">그러나 일부 클라이언트 앱에서는 자동 레이블 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-115">However, not all client apps support auto-labeling.</span></span> <span data-ttu-id="45c59-116">이 기능은 Azure Information Protection 통합 레이블 지정 클라이언트 및 [일부 버전의 Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-116">This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span> 
    
    <span data-ttu-id="45c59-117">구성 방법에 대한 자세한 내용은 이 페이지에서 [Office 앱에 대한 자동 레이블 지정 구성 방법](#how-to-configure-auto-labeling-for-office-apps)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-117">For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.</span></span>

- <span data-ttu-id="45c59-118">**콘텐츠가 이미 저장(SharePoint Online 또는 비즈니스용 OneDrive) 또는 전자 메일 전송(Exchange Online에서 처리됨)된 경우 서비스쪽 레이블 지정**: 자동 레이블 지정 정책 사용(현재 미리보기)</span><span class="sxs-lookup"><span data-stu-id="45c59-118">**Service-side labeling when content is already saved (in SharePoint Online or OneDrive for Business) or emailed (processed by Exchange Online)**: Use an auto-labeling policy—currently in preview.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="45c59-119">[Microsoft 365 서비스에서 민감도 레이블이 있는 자동 분류의 공개 미리보기 발표](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961) 미리보기 발표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-119">See the preview announcement, [Announcing public preview of auto classification with sensitivity labels in Microsoft 365 services](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961).</span></span>
    
    <span data-ttu-id="45c59-120">이 방법을 민감도 레이블이 있는 자동 분류라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-120">This method is referred to as auto classification with sensitivity labels.</span></span> <span data-ttu-id="45c59-121">또한 유휴 데이터(SharePoint 및 OneDrive의 문서) 및 전송 중인 데이터(Exchange에서 보내거나 받은 전자 메일)에 대한 자동 레이블 지정이라고 부르는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-121">You might also hear it referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange).</span></span> <span data-ttu-id="45c59-122">Exchange의 경우 유휴 전자 메일(사서함)은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-122">For Exchange, it doesn't include emails at rest (mailboxes).</span></span> 
    
    <span data-ttu-id="45c59-123">이 레이블 지정은 응용 프로그램이 아닌 서비스에서 적용되므로 사용자에게 어떤 버전의 앱이 있는지 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-123">Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version.</span></span> <span data-ttu-id="45c59-124">따라서 이 기능은 조직 전체에서 즉시 사용할 수 있으며 대규모로 레이블을 지정하는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-124">As a result, this capability is immediately available throughout your organization and suitable for labeling at scale.</span></span> <span data-ttu-id="45c59-125">자동 레이블 지정 정책은 사용자가 레이블 지정 프로세스와 상호 작용하지 않기 때문에 권장되는 레이블 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-125">Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process.</span></span> <span data-ttu-id="45c59-126">대신 관리자가 시뮬레이션 모드에서 정책을 실행하여 실제로 레이블을 적용하기 전에 콘텐츠의 올바른 레이블을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-126">Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.</span></span>
    
    <span data-ttu-id="45c59-127">구성 지침은 이 페이지에서 [SharePoint, OneDrive 및 Exchange에 대한 자동 레이블 지정 정책을 구성하는 방법](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-127">For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.</span></span>
    
    <span data-ttu-id="45c59-128">SharePoint 및 OneDrive에 대한 자동 레이블 지정에만 해당:</span><span class="sxs-lookup"><span data-stu-id="45c59-128">Specific to auto-labeling for SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="45c59-129">테넌트에서 하루 최대 25,000개의 자동 레이블 지정 파일 수(Word, PowerPoint 또는 Excel)</span><span class="sxs-lookup"><span data-stu-id="45c59-129">Maximum of 25,000 automatically labeled files (Word, PowerPoint, or Excel) in your tenant per day</span></span>
    - <span data-ttu-id="45c59-130">모든 정책에서 최대 10개의 사이트 모음 수</span><span class="sxs-lookup"><span data-stu-id="45c59-130">Maximum of 10 sites collections across all policies</span></span>
    - <span data-ttu-id="45c59-131">모든 테넌트에서 최대 10개의 정책 수</span><span class="sxs-lookup"><span data-stu-id="45c59-131">Maximum of 10 policies across your tenant</span></span>

    <span data-ttu-id="45c59-132">Exchange 자동 레이블 지정에만 해당:</span><span class="sxs-lookup"><span data-stu-id="45c59-132">Specific to auto-labeling for Exchange:</span></span>
    - <span data-ttu-id="45c59-133">Office 앱의 수동 레이블 지정 또는 자동 레이블 지정과 달리, 자동 레이블 지정 정책에서 사용자가 지정한 조건에 대해 Office 첨부 파일도 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-133">Unlike manual labeling or auto-labeling with Office apps, Office attachments are also scanned for the conditions you specify in your auto-labeling policy.</span></span> <span data-ttu-id="45c59-134">일치하는 항목이 있는 경우 전자 메일에 레이블이 표시되지만 첨부 파일에는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-134">When there is a match, the email is labeled but not the attachment.</span></span>
    - <span data-ttu-id="45c59-135">IRM 암호화를 적용하는 Exchange 메일 흐름 규칙 또는 DLP(데이터 손실 방지) 정책이 있는 경우: 이러한 규칙 또는 정책과 자동 레이블 지정 정책으로 콘텐츠를 식별하면 레이블이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-135">If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied.</span></span> <span data-ttu-id="45c59-136">해당 레이블이 암호화를 적용하면 Exchange 메일 흐름 규칙 또는 DLP 정책의 IRM 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-136">If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored.</span></span> <span data-ttu-id="45c59-137">그러나 해당 레이블에 암호화가 적용되지 않으면 레이블과 더불어 메일 흐름 규칙 또는 DLP 정책의 IRM 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-137">However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.</span></span>
    - <span data-ttu-id="45c59-138">레이블이 없는 IRM 암호화를 포함하는 전자 메일은 자동 레이블 지정을 사용하여 일치하는 항목이 있는 경우 모든 암호화 설정이 있는 레이블로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-138">Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.</span></span>
    - <span data-ttu-id="45c59-139">자동 레이블 지정 조건과 일치하는 경우 받는 전자 메일에 레이블이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-139">Incoming email is labeled when there is a match with your auto-labeling conditions.</span></span> <span data-ttu-id="45c59-140">그러나 레이블이 암호화로 구성되면 암호화가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-140">However, if the label is configured for encryption, that encryption isn't applied.</span></span>
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a><span data-ttu-id="45c59-141">자동 레이블 지정 정책과 Office 앱에 대한 자동 레이블 지정 비교</span><span class="sxs-lookup"><span data-stu-id="45c59-141">Compare auto-labeling for Office apps with auto-labeling policies</span></span>

<span data-ttu-id="45c59-142">다음 표를 사용하면 두 가지 보완적인 자동 레이블 지정 방법의 동작이 어떻게 차이나는지 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-142">Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:</span></span>

|<span data-ttu-id="45c59-143">기능 또는 동작</span><span class="sxs-lookup"><span data-stu-id="45c59-143">Feature or behavior</span></span>|<span data-ttu-id="45c59-144">레이블 지정 설정: Office 앱에 대한 자동 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="45c59-144">Label setting: Auto-labeling for Office apps</span></span> |<span data-ttu-id="45c59-145">정책: 자동 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="45c59-145">Policy: Auto-labeling</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45c59-146">앱 종속성</span><span class="sxs-lookup"><span data-stu-id="45c59-146">App dependency</span></span>|[<span data-ttu-id="45c59-147">예</span><span class="sxs-lookup"><span data-stu-id="45c59-147">Yes</span></span>](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |<span data-ttu-id="45c59-148">아니요</span><span class="sxs-lookup"><span data-stu-id="45c59-148">No</span></span> |
|<span data-ttu-id="45c59-149">위치별 제한</span><span class="sxs-lookup"><span data-stu-id="45c59-149">Restrict by location</span></span>|<span data-ttu-id="45c59-150">아니오</span><span class="sxs-lookup"><span data-stu-id="45c59-150">No</span></span> |<span data-ttu-id="45c59-151">예</span><span class="sxs-lookup"><span data-stu-id="45c59-151">Yes</span></span> |
|<span data-ttu-id="45c59-152">조건: 훈련 가능한 분류자</span><span class="sxs-lookup"><span data-stu-id="45c59-152">Conditions: Trainable classifiers</span></span>|<span data-ttu-id="45c59-153">예(제한된 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="45c59-153">Yes (limited preview)</span></span> |<span data-ttu-id="45c59-154">아니요</span><span class="sxs-lookup"><span data-stu-id="45c59-154">No</span></span> |
|<span data-ttu-id="45c59-155">조건: 전자 메일 공유 옵션 및 추가 옵션</span><span class="sxs-lookup"><span data-stu-id="45c59-155">Conditions: Sharing options and additional options for email</span></span>|<span data-ttu-id="45c59-156">아니요</span><span class="sxs-lookup"><span data-stu-id="45c59-156">No</span></span> |<span data-ttu-id="45c59-157">예</span><span class="sxs-lookup"><span data-stu-id="45c59-157">Yes</span></span> |
|<span data-ttu-id="45c59-158">권장 사항, 정책 도구 설명 및 사용자 재정의</span><span class="sxs-lookup"><span data-stu-id="45c59-158">Recommendations, policy tooltip, and user overrides</span></span>|<span data-ttu-id="45c59-159">예</span><span class="sxs-lookup"><span data-stu-id="45c59-159">Yes</span></span> |<span data-ttu-id="45c59-160">아니요</span><span class="sxs-lookup"><span data-stu-id="45c59-160">No</span></span> |
|<span data-ttu-id="45c59-161">시뮬레이션 모드</span><span class="sxs-lookup"><span data-stu-id="45c59-161">Simulation mode</span></span>|<span data-ttu-id="45c59-162">아니요</span><span class="sxs-lookup"><span data-stu-id="45c59-162">No</span></span> |<span data-ttu-id="45c59-163">예</span><span class="sxs-lookup"><span data-stu-id="45c59-163">Yes</span></span> |
|<span data-ttu-id="45c59-164">조건이 확인된 Exchange 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="45c59-164">Exchange attachments checked for conditions</span></span>|<span data-ttu-id="45c59-165">아니요</span><span class="sxs-lookup"><span data-stu-id="45c59-165">No</span></span> | <span data-ttu-id="45c59-166">예</span><span class="sxs-lookup"><span data-stu-id="45c59-166">Yes</span></span>|
|<span data-ttu-id="45c59-167">시각적 표시 적용</span><span class="sxs-lookup"><span data-stu-id="45c59-167">Apply visual markings</span></span> |<span data-ttu-id="45c59-168">예</span><span class="sxs-lookup"><span data-stu-id="45c59-168">Yes</span></span> |<span data-ttu-id="45c59-169">예(전자 메일만 해당)</span><span class="sxs-lookup"><span data-stu-id="45c59-169">Yes (email only)</span></span> |
|<span data-ttu-id="45c59-170">레이블 없이 적용된 IRM 암호화 재정의</span><span class="sxs-lookup"><span data-stu-id="45c59-170">Override IRM encryption applied without a label</span></span>|<span data-ttu-id="45c59-171">예(사용자에게 내보내기의 최소 사용 권한이 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="45c59-171">Yes if the user has the minimum usage right of Export</span></span> |<span data-ttu-id="45c59-172">예(전자 메일만 해당)</span><span class="sxs-lookup"><span data-stu-id="45c59-172">Yes (email only)</span></span> |
|<span data-ttu-id="45c59-173">받는 전자 메일에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="45c59-173">Label incoming email</span></span>|<span data-ttu-id="45c59-174">아니요</span><span class="sxs-lookup"><span data-stu-id="45c59-174">No</span></span> |<span data-ttu-id="45c59-175">예(암호화가 적용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="45c59-175">Yes (encryption not applied)</span></span> |

> [!NOTE]
> <span data-ttu-id="45c59-176">콘텐츠에 수동으로 레이블을 지정한 경우 해당 레이블은 자동 레이블로 대체되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-176">When content has been manually labeled, that label will never be replaced by automatic labeling.</span></span> <span data-ttu-id="45c59-177">그러나 자동 레이블 지정 정책은 Office 앱에 대한 자동 레이블 지정을 사용하여 적용된 [우선 순위가 낮은 레이블](sensitivity-labels.md#label-priority-order-matters)을 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-177">However, auto-labeling policies can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was applied by using auto-labeling for Office apps.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="45c59-178">두 개 이상 레이블에 적용했을 때 여러 조건의 평가 방식</span><span class="sxs-lookup"><span data-stu-id="45c59-178">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="45c59-p108">레이블은 정책에서 지정한 위치에 따라 평가되도록 정렬됩니다. 먼저 배치된 레이블은 가장 낮은 위치에 있고(가장 민감하지 않음) 마지막에 위치한 레이블은 가장 높은 위치에 배치됩니다(가장 민감합니다). 우선 순위에 대한 자세한 내용은 [레이블 우선 순위 (순서 관련 문제)](sensitivity-labels.md#label-priority-order-matters)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="45c59-p108">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="45c59-181">상위 레이블이 자동으로 적용되거나 권장되도록 구성하지 않음</span><span class="sxs-lookup"><span data-stu-id="45c59-181">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="45c59-182">상위 레이블(하위 레이블이 있는 레이블)은 콘텐츠에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-182">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="45c59-183">Office 앱에서 상위 레이블을 자동으로 적용하거나 권장하도록 구성하지 않았는지 확인하고 자동 레이블 정책에 대한 상위 레이블을 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-183">Make sure that you don't configure a parent label to be auto-applied or recommended in Office apps, and don't select a parent label for an auto-labeling policy.</span></span> <span data-ttu-id="45c59-184">이렇게 하면 상위 레이블이 콘텐츠에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-184">If you do, the parent label won't be applied to content.</span></span>

<span data-ttu-id="45c59-185">하위 레이블과 함께 자동 레이블을 사용하려면 상위 레이블과 하위 레이블을 모두 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-185">To use automatic labeling with sublabels, make sure you publish both the parent label and the sublabel.</span></span>

<span data-ttu-id="45c59-186">상위 레이블 및 하위 레이블에 대한 자세한 내용은 [하위 레이블(레이블 그룹화)](sensitivity-labels.md#sublabels-grouping-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-186">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="45c59-187">Office 앱에 대한 자동 레이블 지정을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="45c59-187">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="45c59-188">Windows용 Office 앱의 자동 레이블 지정은 Azure Information Protection 통합 레이블 클라이언트에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-188">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="45c59-189">Office 앱에서 기본 제공되는 레이블 지정 기능은 [일부 앱에서 미리 볼 수 있습니다.](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)</span><span class="sxs-lookup"><span data-stu-id="45c59-189">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="45c59-190">[민감도 레이블을 만들거나 편집](create-sensitivity-labels.md)할 경우 Office 앱에 대한 자동 레이블 지정 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-190">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![민감도 레이블에 대한 자동 레이블 지정 옵션](../media/sensitivity-labels-auto-labeling-options.png)

<span data-ttu-id="45c59-192">해당 콘텐츠가 특정 유형의 중요한 정보를 포함하는 경우 자동으로 민감도 레이블을 콘텐츠에 적용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-192">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="45c59-193">중요한 정보 유형 또는 분류자 목록에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-193">Choose from a list of sensitive info types or classifiers:</span></span>

![Office 앱에서 자동 레이블 지정에 대한 레이블 조건](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="45c59-195">현재 **분류자**의 옵션은 제한된 미리 보기 상태이며, 테넌트에 대해 이 기능을 사용하려면 Microsoft에 양식을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-195">Currently, the option for **Classifiers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="45c59-196">자세한 내용은 블로그 포스트 [기본 제공되는 분류자를 사용하여 Office 앱에서 자동 레이블 지정 발표 - 제한된 미리보기](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-196">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="45c59-197">이 민감도 레이블이 자동으로 적용되면 사용자는 Office 앱에서 알림을 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-197">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="45c59-198">예시:</span><span class="sxs-lookup"><span data-stu-id="45c59-198">For example:</span></span>

![문서에 레이블이 자동 적용되었다는 알림](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="45c59-200">레이블에 대한 중요한 정보 유형 구성</span><span class="sxs-lookup"><span data-stu-id="45c59-200">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="45c59-201">**중요한 정보 유형** 옵션을 선택하면 DLP(데이터 손실 방지) 정책을 만들 때 같은 중요한 정보 유형 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-201">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="45c59-202">예를 들어 신용 카드 번호 또는 주민등록번호와 같은 고객의 PII(개인 식별 정보)를 포함하는 모든 콘텐츠에 자동으로 기밀 유지 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-202">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Office 앱에서 자동 레이블 지정을 위한 중요한 정보 유형](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="45c59-204">중요한 정보 유형을 선택하면 인스턴스 수 또는 일치 정확도를 변경하여 조건을 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-204">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="45c59-205">자세한 내용은 [규칙을 조정하여 더욱 쉽게 또는 더욱 일치하기 어렵게 하기](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-205">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="45c59-206">또한 조건이 모든 민감 정보 유형을 감지해야 하는지 또는 한 가지 유형만 감지하면 되는지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-206">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="45c59-207">조건을 더 유연하게 만들거나 복잡하게 만들려면 그룹을 추가하고 그룹 간에 논리 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-207">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="45c59-208">자세한 내용은 [그룹화 및 논리 연산자](data-loss-prevention-policies.md#grouping-and-logical-operators)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-208">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![인스턴스 개수 및 일치 정확도 옵션](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifiers-for-a-label"></a><span data-ttu-id="45c59-210">레이블의 분류자 구성하기</span><span class="sxs-lookup"><span data-stu-id="45c59-210">Configuring classifiers for a label</span></span>

<span data-ttu-id="45c59-211">**분류자** 옵션을 선택하는 경우 기본 제공 분류자를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-211">When you select the **Classifiers** option, select one or more of the built-in classifiers:</span></span>

![분류자 및 민감도 레이블 옵션](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="45c59-213">이러한 분류자에 대한 자세한 내용은 [교육 가능한 분류자 시작하기(미리 보기)](classifier-getting-started-with.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-213">For more information about these classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="45c59-214">미리 보기 기간 동안 다음 앱이 민감도 레이블에 분류자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-214">During the preview period, the following apps support classifiers for sensitivity labels:</span></span>

- <span data-ttu-id="45c59-215">[Office 참가자](https://office.com/insider)로부터의 Windows용 엔터프라이즈용 Microsoft 365 앱 데스크톱 앱:</span><span class="sxs-lookup"><span data-stu-id="45c59-215">Microsoft365 Apps for enterprise desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="45c59-216">Word</span><span class="sxs-lookup"><span data-stu-id="45c59-216">Word</span></span>
    - <span data-ttu-id="45c59-217">Excel</span><span class="sxs-lookup"><span data-stu-id="45c59-217">Excel</span></span>
    - <span data-ttu-id="45c59-218">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="45c59-218">PowerPoint</span></span>

- <span data-ttu-id="45c59-219">[SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블을 사용(공개 미리보기)](sensitivity-labels-sharepoint-onedrive-files.md)하는 경우 웹 앱용 Office:</span><span class="sxs-lookup"><span data-stu-id="45c59-219">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="45c59-220">Word</span><span class="sxs-lookup"><span data-stu-id="45c59-220">Word</span></span>
    - <span data-ttu-id="45c59-221">Excel</span><span class="sxs-lookup"><span data-stu-id="45c59-221">Excel</span></span>
    - <span data-ttu-id="45c59-222">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="45c59-222">PowerPoint</span></span>
    - <span data-ttu-id="45c59-223">Outlook</span><span class="sxs-lookup"><span data-stu-id="45c59-223">Outlook</span></span>

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a><span data-ttu-id="45c59-224">사용자가 민감도 레이블을 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-224">Recommend that the user applies a sensitivity label</span></span>

<span data-ttu-id="45c59-225">원하는 경우 사용자에게 레이블을 적용할 것을 권장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-225">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="45c59-226">이 옵션을 사용하면 사용자가 분류 및 관련 보호를 수락하거나, 레이블이 콘텐츠에 적합하지 않은 경우에는 권장 사항을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-226">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![사용자에게 민감도 레이블 권장 옵션](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="45c59-228">다음은 사용자 지정 정책 팁을 사용하여 레이블을 권장 작업으로 적용하도록 조건을 구성할 때 Azure Information Protection 통합 레이블 지정 클라이언트에서 표시되는 프롬프트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-228">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip.</span></span> <span data-ttu-id="45c59-229">정책 팁에 표시될 텍스트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-229">You can choose what text is displayed in the policy tip.</span></span>

![권장된 레이블을 적용하라는 메시지 표시](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="45c59-231">자동 또는 권장 레이블이 적용되는 경우</span><span class="sxs-lookup"><span data-stu-id="45c59-231">When automatic or recommended labels are applied</span></span>

<span data-ttu-id="45c59-232">Office 앱에서 구현되는 자동 및 권장되는 레이블 지정은 Office에 기본 제공되는 레이블을 사용할지 또는 Azure Information Protection 통합 레이블 지정 클라이언트를 사용하는지에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-232">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="45c59-233">그러나 두 경우 모두에 다음이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-233">In both cases, however:</span></span>

- <span data-ttu-id="45c59-234">이전에 수동으로 레이블을 지정했거나, 이전에 더 높은 민감도로 레이블이 자동으로 지정된 문서 및 전자 메일에는 자동 레이블 지정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-234">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="45c59-235">문서 또는 전자 메일에는 단일 보존 레이블 외에 단일 민감도 레이블만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-235">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="45c59-236">이전에 더 높은 민감도로 레이블이 지정된 문서 또는 전자 메일에는 권장 레이블 지정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-236">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="45c59-237">콘텐츠에 더 높은 민감도로 레이블이 지정되면 사용자에게 권장 사항 및 정책 팁이 포함된 프롬프트가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-237">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="45c59-238">기본 제공 레이블 지정과 관련된 내용:</span><span class="sxs-lookup"><span data-stu-id="45c59-238">Specific to built-in labeling:</span></span>

- <span data-ttu-id="45c59-239">모든 Office 앱이 자동(및 권장) 레이블 지정을 지원하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-239">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="45c59-240">자세한 내용은 [앱에서의 민감도 레이블 기능에 대한 지원](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-240">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="45c59-241">데스크톱 버전의 Word에서 권장되는 레이블의 경우 사용자가 권장되는 민감도 레이블을 적용하는 대신, 중요한 콘텐츠를 검토하고 제거할 수 있도록 권장 사항을 트리거한 중요한 콘텐츠에 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-241">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="45c59-242">Office 앱에서 이러한 레이블을 적용하는 방법에 대한 자세한 내용과 예제 스크린샷 및 중요한 정보를 검색하는 방법에 대한 자세한 내용은 [Office에서 파일 및 전자 메일에 자동으로 민감도 레이블 적용 또는 추천](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-242">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="45c59-243">Azure Information Protection 통합 레이블 지정 클라이언트와 관련된 내용:</span><span class="sxs-lookup"><span data-stu-id="45c59-243">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="45c59-244">자동 및 권장되는 레이블은 문서를 저장할 때는 Word, Excel 및 PowerPoint에 적용되고, 전자 메일을 보낼 때는 Outlook에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-244">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="45c59-245">Outlook에서 권장되는 레이블 지정을 지원하려면 먼저 [고급 정책 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-245">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="45c59-246">문서 및 전자 메일의 본문 텍스트와 머리글 및 바닥글에서는 중요한 정보를 검색할 수 있지만, 전자 메일의 제목 줄이나 첨부 파일에서는 중요한 정보를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-246">Sensitive information can be detected in the body text in documents and emails, and to headers and footers—but not in the subject line or attachments of email.</span></span>

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a><span data-ttu-id="45c59-247">SharePoint, OneDrive 및 Exchange에 대한 자동 레이블 지정 정책을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="45c59-247">How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange</span></span>
> [!NOTE]
> <span data-ttu-id="45c59-248">자동 레이블 지정 정책은 공개 미리 보기에서 테넌트에 점진적으로 배포되며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-248">Auto-labeling policies are gradually rolling out to tenants in public preview and subject to change.</span></span>

### <a name="prerequisites-for-auto-labeling-policies"></a><span data-ttu-id="45c59-249">자동 레이블 지정 정책에 대한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="45c59-249">Prerequisites for auto-labeling policies</span></span>

- <span data-ttu-id="45c59-250">시뮬레이션 모드로 Microsoft 365에 대한 감사가 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-250">Auditing for Microsoft 365 must be turned on for simulation mode.</span></span> <span data-ttu-id="45c59-251">감사를 설정해야 하거나 감사가 이미 설정되어 있는지 확실하지 않은 경우에는 [감사 로그 검색 켜기 또는 끄기](turn-audit-log-search-on-or-off.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-251">If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="45c59-252">SharePoint 및 OneDrive에서 파일에 자동 레이블을 지정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-252">To auto-label files in SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="45c59-253">[SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용(공개 미리 보기)](sensitivity-labels-sharepoint-onedrive-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-253">You have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>
    - <span data-ttu-id="45c59-254">자동 레이블 지정 정책이 실행될 때 다른 프로세스나 사용자가 파일을 열면 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-254">At the time the auto-labeling policy runs, the file mustn't be open by another process or user.</span></span>

- <span data-ttu-id="45c59-255">기본 제공 민감도 유형이 아닌 [사용자 지정 민감도 정보 유형](custom-sensitive-info-types.md)을 사용하려는 경우:</span><span class="sxs-lookup"><span data-stu-id="45c59-255">If you plan to use [custom sensitive information types](custom-sensitive-info-types.md) rather than the built-in sensitivity types:</span></span> 
    - <span data-ttu-id="45c59-256">사용자 지정 민감도 정보 유형은 사용자 지정 민감도 정보 유형을 저장한 후 생성되는 콘텐츠에 대해 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-256">Custom sensitivity information types are evaluated for content that is created after the custom sensitivity information types are saved.</span></span> 
    - <span data-ttu-id="45c59-257">새로운 사용자 지정 민감도 정보 유형을 테스트하려면 자동 레이블 지정 정책을 만들기 전에 해당 유형을 만든 다음 테스트용 샘플 데이터가 포함된 새 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-257">To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.</span></span>

- <span data-ttu-id="45c59-258">자동 레이블 지정 정책에 대해 선택할 수 있는 하나 이상의 민감도 레이블이 [생성 및 게시](create-sensitivity-labels.md)(적어도 한 명의 사용자에게) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-258">One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policies.</span></span> <span data-ttu-id="45c59-259">이러한 레이블의 경우:</span><span class="sxs-lookup"><span data-stu-id="45c59-259">For these labels:</span></span>
    - <span data-ttu-id="45c59-260">소개에 설명된 대로 레이블 설정은 자동 레이블 지정 정책을 보완하기 때문에 Office 앱 레이블 설정의 자동 레이블 지정 설정이 켜져 있는지 여부는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-260">It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction.</span></span> 
    - <span data-ttu-id="45c59-261">자동 레이블에 사용하려는 레이블이 시각적 표시(머리글, 바닥글, 워터 마크)를 사용하도록 구성된 경우 문서에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-261">If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.</span></span>
    - <span data-ttu-id="45c59-262">레이블이 암호화를 적용하는 경우 **지금 권한 할당** 설정에 대해 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-262">If the labels apply encryption, they must be configured for the **Assign permissions now** setting.</span></span>

### <a name="learn-about-simulation-mode"></a><span data-ttu-id="45c59-263">시뮬레이션 모드에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="45c59-263">Learn about simulation mode</span></span>

<span data-ttu-id="45c59-264">시뮬레이션 모드는 자동 레이블 지정 정책에 고유하며 워크플로에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-264">Simulation mode is unique to auto-labeling policies and woven into the workflow.</span></span> <span data-ttu-id="45c59-265">정책에서 적어도 한 번의 시뮬레이션이 실행될 때까지 문서 및 전자 메일에 자동으로 레이블을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-265">You can't automatically label documents and emails until your policy has run at least one simulation.</span></span>

<span data-ttu-id="45c59-266">자동 레이블 지정 정책의 워크플로:</span><span class="sxs-lookup"><span data-stu-id="45c59-266">Workflow for an auto-labeling policy:</span></span>

1. <span data-ttu-id="45c59-267">자동 레이블 지정 정책 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="45c59-267">Create and configure an auto-labeling policy</span></span>

2. <span data-ttu-id="45c59-268">시뮬레이션 모드로 정책을 실행하고 최소 24시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-268">Run the policy in simulation mode and wait at least 24 hours</span></span>

3. <span data-ttu-id="45c59-269">결과를 검토하고 필요한 경우 정책을 조정한 후 시뮬레이션 모드를 다시 실행하고 최소 24시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-269">Review the results, and if necessary, refine your policy, rerun simulation mode and wait at least 24 hours</span></span>

4. <span data-ttu-id="45c59-270">필요한 경우 3단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-270">Repeat step 3 as needed</span></span>

5. <span data-ttu-id="45c59-271">프로덕션에서 배포</span><span class="sxs-lookup"><span data-stu-id="45c59-271">Deploy in production</span></span>

<span data-ttu-id="45c59-272">시뮬레이션된 배포는 PowerShell의 WhatIf 매개 변수처럼 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-272">The simulated deployment runs like the WhatIf parameter for PowerShell.</span></span> <span data-ttu-id="45c59-273">사용자가 정의한 규칙을 사용하여 자동 레이블 지정 정책이 선택한 레이블을 적용한 것처럼 보고된 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-273">You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined.</span></span> <span data-ttu-id="45c59-274">그런 다음 필요한 경우 규칙을 조정하고 시뮬레이션을 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-274">You can then refine your rules for accuracy if needed, and rerun the simulation.</span></span> <span data-ttu-id="45c59-275">그러나 Exchange용 자동 레이블 지정은 사서함에 저장된 전자 메일이 아닌 보내고 받는 전자 메일에 적용되기 때문에, 정확히 같은 전자 메일 메시지를 보내고 받을 수 없는 한 시뮬레이션의 전자 메일에 대한 결과가 일관되길 기대하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-275">However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.</span></span>

<span data-ttu-id="45c59-276">또한 시뮬레이션 모드를 사용하면 배포 전에 자동 레이블 지정 정책의 범위를 단계적으로 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-276">Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment.</span></span> <span data-ttu-id="45c59-277">예를 들어 단일 문서 라이브러리를 사용하여 SharePoint 사이트와 같은 단일 위치에서 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-277">For example, you might start with a single location, such as a SharePoint site, with a single document library.</span></span> <span data-ttu-id="45c59-278">그런 다음 반복적인 변경으로 범위를 여러 사이트로 늘리고 OneDrive와 같은 다른 위치로 범위를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-278">Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.</span></span>

<span data-ttu-id="45c59-279">마지막으로 시뮬레이션 모드를 사용하여 자동 레이블 지정 정책을 실행하는 데 필요한 시간을 대략적으로 제공하여 시뮬레이션 모드없이 실행할 시기를 계획하고 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-279">Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.</span></span>

### <a name="creating-an-auto-labeling-policy"></a><span data-ttu-id="45c59-280">자동 레이블 지정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="45c59-280">Creating an auto-labeling policy</span></span>

1. <span data-ttu-id="45c59-281">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-281">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="45c59-282">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="45c59-282">**Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="45c59-283">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-283">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="45c59-284">**자동 레이블 지정(미리 보기)** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-284">Select the **Auto-labeling (preview)** tab:</span></span>
    
    ![자동 레이블 지정(미리 보기)](../media/auto-labeling-tab.png)
    
    <span data-ttu-id="45c59-286">이 새 탭은 여전히 테넌트에 배포 중입니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-286">This new tab is still rolling out to tenants.</span></span> <span data-ttu-id="45c59-287">보이지 않는 경우 며칠 후 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-287">If you don't see it, try again in a few days.</span></span>

3. <span data-ttu-id="45c59-288">**+ 정책 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-288">Select **+ Create policy**.</span></span>

4. <span data-ttu-id="45c59-289">**이 레이블을 적용할 정보 선택** 페이지에서 **재무** 또는 **개인 정보 보호**와 같은 템플릿 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-289">For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**.</span></span> <span data-ttu-id="45c59-290">**표시 옵션** 드롭 다운을 사용하여 검색을 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-290">You can refine your search by using the **Show options for** dropdown.</span></span> <span data-ttu-id="45c59-291">또는 템플릿이 요구 사항을 충족하지 않으면 **사용자 지정 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-291">Or, select **Custom policy** if the templates don't meet your requirements.</span></span> <span data-ttu-id="45c59-292">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-292">Select **Next**.</span></span>

5. <span data-ttu-id="45c59-293">**자동 레이블 지정 정책 이름 지정** 페이지에서 고유한 이름을 입력하고, 필요에 따라 레이블을 지정할 콘텐츠를 식별하는 자동으로 적용되는 레이블, 위치 및 조건을 식별하는 데 도움이 되는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-293">For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.</span></span>

6. <span data-ttu-id="45c59-294">**레이블을 적용할 위치 선택** 페이지에서 Exchange, SharePoint 사이트 및 OneDrive의 위치를 선택하고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-294">For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive.</span></span> <span data-ttu-id="45c59-295">그런 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-295">Then select **Next**.</span></span>

7. <span data-ttu-id="45c59-296">**정책 설정 정의** 페이지에서 선택한 모든 위치에서 레이블을 지정할 컨텐츠를 식별하는 규칙을 정의하기 위해 **포함된 콘텐츠 찾기**의 기본값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-296">For the **Define policy settings** page: Keep the default of **Find content that contains** to define rules that identify content to label across all your selected locations.</span></span> <span data-ttu-id="45c59-297">위치마다 다른 규칙이 필요한 경우 **고급 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-297">If you need different rules per location, select **Advanced settings**.</span></span> <span data-ttu-id="45c59-298">그런 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-298">Then select **Next**.</span></span>
    
    <span data-ttu-id="45c59-299">이 규칙은 민감한 정보 유형 및 공유 옵션이 포함된 조건을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-299">The rules use conditions that include sensitive information types and sharing options:</span></span>
    - <span data-ttu-id="45c59-300">민감한 정보 유형의 경우 기본 제공 정보 유형과 사용자 지정 민감한 정보 유형을 모두 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-300">For sensitive information types, you can select both built-in and custom sensitive information types.</span></span>
    - <span data-ttu-id="45c59-301">공유 옵션의 경우 **조직 내부의 사용자만** 또는 **조직 외부의 사용자**를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-301">For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.</span></span>
    
    <span data-ttu-id="45c59-302">유일한 위치가 **Exchange**이거나 **고급 설정**을 선택한 경우 다음과 같은 추가 조건을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-302">If your only location is **Exchange**, or if you select **Advanced settings**, there are additional conditions that you can select:</span></span>
    - <span data-ttu-id="45c59-303">보낸 사람 IP 주소는</span><span class="sxs-lookup"><span data-stu-id="45c59-303">Sender IP address is</span></span>
    - <span data-ttu-id="45c59-304">받는 사람 도메인은</span><span class="sxs-lookup"><span data-stu-id="45c59-304">Recipient domain is</span></span>
    - <span data-ttu-id="45c59-305">받는 사람은</span><span class="sxs-lookup"><span data-stu-id="45c59-305">Recipient is</span></span>
    - <span data-ttu-id="45c59-306">첨부 파일 확장명은</span><span class="sxs-lookup"><span data-stu-id="45c59-306">Attachment's file extension is</span></span>
    - <span data-ttu-id="45c59-307">첨부 파일이 암호로 보호됨</span><span class="sxs-lookup"><span data-stu-id="45c59-307">Attachment is password protected</span></span>
    - <span data-ttu-id="45c59-308">전자 메일 첨부 파일의 콘텐츠를 검사할 수 없음</span><span class="sxs-lookup"><span data-stu-id="45c59-308">Any email attachment's content could not be scanned</span></span>
    - <span data-ttu-id="45c59-309">전자 메일 첨부 파일 내용의 검사가 완료되지 않음</span><span class="sxs-lookup"><span data-stu-id="45c59-309">Any email attachment's content didn't complete scanning</span></span>

8. <span data-ttu-id="45c59-310">**레이블이 지정된 콘텐츠를 정의하는 규칙 설정** 페이지에서 **+ 규칙 만들기**를 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-310">For the **Set up rules to define what content is labeled** page: Select **+ Create rule** and then select **Next**.</span></span>

9. <span data-ttu-id="45c59-311">**규칙 만들기** 페이지에서 규칙 이름을 지정하고 민감한 정보 유형 또는 공유 옵션을 사용하여 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-311">On the **Create rule** page, name and define your rule, using sensitive information types or the sharing option, and then select **Save**.</span></span>
    
    <span data-ttu-id="45c59-312">민감한 정보 유형의 구성 옵션은 Office 앱에 대한 자동 레이블 지정에 대해 선택한 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-312">The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps.</span></span> <span data-ttu-id="45c59-313">자세한 정보가 필요한 경우 [레이블에 민감한 정보 유형 구성](#configuring-sensitive-info-types-for-a-label)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c59-313">If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).</span></span>

10. <span data-ttu-id="45c59-314">**레이블이 지정된 콘텐츠를 정의하는 규칙 설정** 페이지로 돌아가서, 레이블을 지정할 콘텐츠를 식별하기 위해 다른 규칙이 필요한 경우 **+ 규칙 만들기**를 다시 선택하고 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-314">Back on the **Set up rules to define what content is labeled** page: Select **+ Create rule** again if you need another rule to identify the content to label, and repeat the previous step.</span></span> <span data-ttu-id="45c59-315">필요한 모든 규칙을 정의하고 해당 상태가 켜져 있음을 확인한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-315">When you have defined all the rules you need, and confirmed their status is on, select **Next**.</span></span>

11. <span data-ttu-id="45c59-316">**자동 적용할 레이블 선택** 페이지에서 **+ 레이블 선택**을 선택하고, **민감도 레이블 선택** 창에서 레이블을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-316">For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.</span></span>

12. <span data-ttu-id="45c59-317">**정책 시뮬레이션을 지금 또는 나중에 실행할지 결정** 페이지에서 지금 자동 레이블 지정 정책을 실행할 준비가 되었으면, 시뮬레이션 모드에서 **시뮬레이션 모드에서 정책 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-317">For the **Decide if you want to run policy simulation now or later** page: Select **Run policy in simulation mode** if you're ready to run the auto-labeling policy now, in simulation mode.</span></span> <span data-ttu-id="45c59-318">그렇지 않으면 **정책을 해제로 두기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-318">Otherwise, select **Leave policy turned off**.</span></span> <span data-ttu-id="45c59-319">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-319">Select **Next**.</span></span> 

13. <span data-ttu-id="45c59-320">**요약** 페이지에서 자동 레이블 지정 정책의 구성을 검토하고 필요한 사항을 변경한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-320">For the **Summary** page: Review the configuration of your auto-labeling policy and make any changes that needed, and complete the wizard.</span></span>
    
    <span data-ttu-id="45c59-321">Office 앱에 대한 자동 레이블 지정 기능과 달리 별도의 게시 옵션은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-321">Unlike auto-labeling for Office apps, there's no separate publish option.</span></span> <span data-ttu-id="45c59-322">그러나 게시 레이블과 마찬가지로 자동 레이블 지정 정책이 조직 전체에 복제될 때까지 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-322">However, as with publishing labels, allow up to 24 hours for the auto-labeling policy to replicate throughout your organization.</span></span>

<span data-ttu-id="45c59-323">이제 **정보 보호** 페이지의 **자동 레이블 지정(미리 보기)** 탭, **시뮬레이션** 혹은 **끄기** 구역에 시뮬레이션 모드에서 실행할지의 선택 여부에 따라 자동 레이블 정책이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-323">Now on the **Information protection** page, **Auto-labeling (preview)** tab, you see your auto-labeling policy in the **Simulation** or **Off** section, depending on whether you chose to run it in simulation mode or not.</span></span> <span data-ttu-id="45c59-324">구성 및 상태에 대한 세부 사항을 보려면 정책을 선택합니다(예: **정책 시뮬레이션을 아직 실행 중**).</span><span class="sxs-lookup"><span data-stu-id="45c59-324">Select your policy to see the details of the configuration and status (for example, **Policy simulation is still running**).</span></span> <span data-ttu-id="45c59-325">시뮬레이션 모드에서의 정책의 경우 **일치 항목** 탭을 선택하여 지정한 규칙과 일치하는 전자 메일 또는 문서를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-325">For policies in simulation mode, select the **Matched items** tab to see which emails or documents matched the rules that you specified.</span></span>

<span data-ttu-id="45c59-326">다음의 인터페이스에서 직접 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-326">You can modify your policy directly from this interface:</span></span>

- <span data-ttu-id="45c59-327">**끄기** 구역에 있는 정책의 경우 **정책 편집** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-327">For a policy in the **Off** section, select the **Edit policy** button.</span></span>

- <span data-ttu-id="45c59-328">**시뮬레이션** 구역의 정책의 경우, 페이지 맨 위의 다음의 탭에서 **편집** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-328">For policy in the **Simulation** section, select the **Edit** option at the top of the page, from either tab:</span></span>
    
    ![자동 레이블 지정 정책 옵션 편집](../media/auto-labeling-edit.png)
    
    <span data-ttu-id="45c59-330">시뮬레이션없이 정책을 실행할 준비가 되면 **정책 켜기** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-330">When you're ready to run the policy without simulation, select the **Turn on policy** option.</span></span>

<span data-ttu-id="45c59-331">적절한 [권한](data-classification-content-explorer.md#permissions)이 있는 경우 [콘텐츠 탐색기](data-classification-content-explorer.md)를 사용하여 자동 레이블 지정 정책의 결과를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-331">You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):</span></span>
- <span data-ttu-id="45c59-332">**콘텐츠 탐색기 목록 뷰어**를 사용하면 파일의 콘텐츠가 아닌 파일의 레이블을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-332">**Content Explorer List viewer** lets you see a file's label but not the file's contents.</span></span>
- <span data-ttu-id="45c59-333">**콘텐츠 탐색기 콘텐츠 뷰어**를 사용하면 파일의 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-333">**Content Explorer Content viewer** lets you see the file's contents.</span></span>

> [!TIP]
> <span data-ttu-id="45c59-334">콘텐츠 탐색기를 사용하여 민감한 정보가 포함된 레이블이 지정되지 않은 문서가 있는 위치를 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-334">You can also use content explorer to identify locations that have unlabeled documents that contain sensitive information.</span></span> <span data-ttu-id="45c59-335">이 정보를 사용하여 이러한 위치를 자동 레이블 지정 정책에 추가하고 식별된 민감한 정보 유형을 규칙으로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="45c59-335">Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.</span></span>

