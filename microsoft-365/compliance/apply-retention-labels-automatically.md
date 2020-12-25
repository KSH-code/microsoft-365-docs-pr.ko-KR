---
title: 보존 레이블 자동 적용하여 콘텐츠를 보존 또는 삭제하기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 레이블을 만들고 자동 게시하여 레이블을 자동으로 적용하여 필요한 항목을 보존하고 필요하지 않은 항목을 삭제할 수 있습니다.
ms.openlocfilehash: b4e1afbc520b7ec046b4af399e7c1c0cd094e8f9
ms.sourcegitcommit: 5756896ad87e28fac20f7981eaaeacfb0c098254
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2020
ms.locfileid: "49730159"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="c69b0-103">보존 레이블 자동 적용하여 콘텐츠를 보존 또는 삭제하기</span><span class="sxs-lookup"><span data-stu-id="c69b0-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="c69b0-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="c69b0-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="c69b0-105">이 시나리오는 [규제 기록](records-management.md#records)에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="c69b0-106">[보존 레이블](retention.md)의 가장 강력한 기능 중 하나는 지정된 조건과 일치하는 콘텐츠에 자동으로 레이블을 적용하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="c69b0-107">이 경우 조직의 사용자는 레이블을 적용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="c69b0-108">Microsoft 365에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="c69b0-109">자동 적용 보존 레이블은 다음과 같은 이유 때문에 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="c69b0-110">사용자에게 모든 분류를 교육할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="c69b0-111">모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="c69b0-112">사용자가 더 이상 데이터 거버넌스 정책을 알아야 할 필요가 없으며, 업무에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="c69b0-113">콘텐츠에 중요한 정보, 키워드나 검색 가능한 속성 또는 [학습 가능한 분류자](classifier-get-started-with.md) 일치 항목이 포함된 경우 보존 레이블을 콘텐츠에 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="c69b0-114">이제 미리 보기에서 검색 가능한 속성을 사용하여 [Teams 모임 녹음/녹화](#microsoft-teams-meeting-recordings)을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-114">Now in preview, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="c69b0-115">다음 조건에 따라 보존 레이블을 자동으로 적용하는 프로세스:</span><span class="sxs-lookup"><span data-stu-id="c69b0-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![자동 적용 레이블의 역할 및 작업 다이어그램](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="c69b0-117">두 가지 관리 단계를 수행하려면 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="c69b0-118">자동 정책은 자동으로 보존 레이블을 적용하기 위해 조건과 함께 서비스 측 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="c69b0-119">다음을 수행할 때 보존 레이블을 레이블 정책과 함께 자동으로 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="c69b0-120">SharePoint Syntex의 문서 이해 모델에 보존 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-120">Apply a retention label to a document understanding model in SharePoint Syntex</span></span>
> - <span data-ttu-id="c69b0-121">SharePoint 및 Outlook에 대한 기본 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="c69b0-121">Apply a default retention label for SharePoint and Outlook</span></span>
>- <span data-ttu-id="c69b0-122">Outlook 규칙을 사용하여 전자 메일에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="c69b0-122">Apply a retention label to email by using Outlook rules</span></span>
>
> <span data-ttu-id="c69b0-123">이 시나리오의 경우 [앱에서 보존 레이블 만들기 및 적용하기](create-apply-retention-labels.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-123">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c69b0-124">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c69b0-124">Before you begin</span></span>

<span data-ttu-id="c69b0-125">조직의 전역 관리자는 보존 레이블과 해당 정책을 만들고 편집할 수 있는 모든 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-125">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="c69b0-126">전역 관리자로 로그인하지 않은 경우 [보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-126">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="c69b0-127">보존 레이블을 자동으로 적용하는 방법</span><span class="sxs-lookup"><span data-stu-id="c69b0-127">How to auto-apply a retention label</span></span>

<span data-ttu-id="c69b0-128">먼저 보존 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-128">First, create your retention label.</span></span> <span data-ttu-id="c69b0-129">그런 다음 해당 레이블을 적용하는 자동 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-129">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="c69b0-130">보존 레이블을 이미 만든 경우에는 [자동 정책 만들기](#step-2-create-an-auto-apply-policy)로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-130">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="c69b0-131">탐색 지침은 [레코드 관리](records-management.md)를 사용 중인지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-131">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="c69b0-132">두 시나리오 모두에 대한 지침이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-132">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="c69b0-133">1단계: 보존 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="c69b0-133">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="c69b0-134">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-134">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="c69b0-135">레코드 관리를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="c69b0-135">If you are using records management:</span></span>
        - <span data-ttu-id="c69b0-136">**솔루션** > **레코드 관리** > **파일 계획** 탭 > **+ 레이블 만들기** > **보존 레이블**</span><span class="sxs-lookup"><span data-stu-id="c69b0-136">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="c69b0-137">레코드 관리를 사용하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="c69b0-137">If you are not using records management:</span></span>
       - <span data-ttu-id="c69b0-138">**솔루션** > **정보 관리** > **레이블** tab > + **레이블 만들기**</span><span class="sxs-lookup"><span data-stu-id="c69b0-138">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="c69b0-139">바로 옵션이 표시되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="c69b0-139">Don't immediately see your option?</span></span> <span data-ttu-id="c69b0-140">먼저 **모두 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-140">First select **Show all**.</span></span> 

2. <span data-ttu-id="c69b0-141">마법사의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-141">Follow the prompts in the wizard.</span></span> <span data-ttu-id="c69b0-142">레코드 관리를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="c69b0-142">If you are using records management:</span></span>
    
    - <span data-ttu-id="c69b0-143">파일 계획 설명자에 대한 자세한 내용은 [파일 계획을 사용하여 보존 레이블 관리의 개요](file-plan-manager.md)를 참조하세요</span><span class="sxs-lookup"><span data-stu-id="c69b0-143">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="c69b0-144">보존 레이블을 사용하여 레코드를 선언하려면 **항목을 레코드로 표시** 를 선택하거나 **항목을 규제 레코드로 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-144">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**.</span></span> <span data-ttu-id="c69b0-145">자세한 정보는 [레코드를 선언하도록 보존 레이블 구성하기](declare-records.md#configuring-retention-labels-to-declare-records)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-145">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="c69b0-146">레이블을 만든 후 레이블을 게시하고 레이블을 자동으로 적용하거나 단지 레이블을 저장하는 옵션이 표시되면 **이 레이블을 특정 콘텐츠에 자동으로 적용** 을 선택한 후 **완료** 를 선택하여 다음 절차에서 2 단계로 바로 이동하는 자동 레이블 만들기 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-146">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="c69b0-147">기존 레이블을 편집하려면 레이블을 선택한 후 **레이블 편집** 옵션을 선택하여 레이블 설명과 [적격 설정](#updating-retention-labels-and-their-policies)을 변경하는 데 사용하는 편집 보유 마법사를 2단계에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-147">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="c69b0-148">2단계: 자동 적용 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c69b0-148">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="c69b0-149">자동 적용 정책을 만들 때 지정한 조건에 따라 콘텐츠에 자동으로 적용할 보존 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-149">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="c69b0-150">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="c69b0-151">레코드 관리를 사용하는 경우: **정보 거버넌스**</span><span class="sxs-lookup"><span data-stu-id="c69b0-151">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="c69b0-152">**솔루션** > **레코드 관리** > **레이블 정책** 탭 > **레이블 자동 적용**</span><span class="sxs-lookup"><span data-stu-id="c69b0-152">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="c69b0-153">레코드 관리를 사용하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="c69b0-153">If you are not using records management:</span></span>
        - <span data-ttu-id="c69b0-154">**솔루션** > **정보 거버넌스** > **레이블 정책** 탭 > **레이블 자동 적용**</span><span class="sxs-lookup"><span data-stu-id="c69b0-154">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="c69b0-155">바로 옵션이 표시되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="c69b0-155">Don't immediately see your option?</span></span> <span data-ttu-id="c69b0-156">먼저 **모두 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-156">First select **Show all**.</span></span> 

2. <span data-ttu-id="c69b0-157">자동 레이블 만들기 마법사의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-157">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="c69b0-158">보존 레이블을 자동으로 적용하는 조건을 구성하는 방법에 대한 자세한 내용은이 페이지에서 [보존 레이블 자동 적용에 대한 조건 구성하기](#configuring-conditions-for-auto-apply-retention-labels) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-158">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="c69b0-159">보존 레이블이 지원하는 위치에 대한 자세한 내용은 [보존 레이블과 위치](retention.md#retention-label-policies-and-locations) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-159">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="c69b0-160">기존 자동 적용 정책을 편집하려면 정책을 선택하고 선택한 보존 레이블과 모든 [적격 설정](#updating-retention-labels-and-their-policies)을 2단계에서 변경하도록 해주는 보존 정책 편집 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-160">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

<span data-ttu-id="c69b0-161">자동 적용 레이블 정책을 사용하여 콘텐츠에 레이블을 지정한 후에는 콘텐츠 또는 정책을 변경하거나 새 자동 적용 레이블 정책을 사용하여 적용된 레이블을 자동으로 제거하거나 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-161">After content is labeled by using an auto-apply label policy, the applied label can't be automatically removed or changed by changing the content or the policy, or by a new auto-apply label policy.</span></span> <span data-ttu-id="c69b0-162">자세한 내용은 [한 번에 하나의 보존 레이블만](retention.md#only-one-retention-label-at-a-time)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-162">For more information, see [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="c69b0-163">보존 레이블 자동 적용에 대한 조건 구성하기</span><span class="sxs-lookup"><span data-stu-id="c69b0-163">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="c69b0-164">콘텐츠에 다음이 포함될 경우, 콘텐츠에 자동으로 보존 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-164">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="c69b0-165">특정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="c69b0-165">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="c69b0-166">만든 쿼리와 일치하는 특정 키워드 또는 검색 가능한 속성</span><span class="sxs-lookup"><span data-stu-id="c69b0-166">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="c69b0-167">학습 가능한 분류자와 일치</span><span class="sxs-lookup"><span data-stu-id="c69b0-167">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="c69b0-168">특정 유형의 중요한 정보가 있는 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="c69b0-168">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="c69b0-169">중요한 정보에 대한 자동 적용 보존 레이블 정책을 만들면 DLP(데이터 손실 방지) 정책을 만들 때 같은 정책 템플릿 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-169">When you create auto-apply retention label policies for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="c69b0-170">각 템플릿은 특정 중요한 정보 유형을 찾도록 미리 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-170">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="c69b0-171">예를 들어 여기에 나와 있는 서식 파일은 미국 ITIN, SSN 및 여권 번호를 **개인 정보** 범주와 **미국 PII (개인 식별 정보) 데이터 서식 파일** 에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-171">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![중요한 정보 유형을 갖는 정책 템플릿](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="c69b0-173">중요한 정보 유형에 대한 자세한 내용은 [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-173">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="c69b0-174">정책 템플릿을 선택한 후 중요한 정보 유형을 추가하거나 제거할 수 있으며 인스턴스 수 및 일치 정확도를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-174">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="c69b0-175">다음에 표시된 예제 스크린샷에서는 다음 경우에만 보존 레이블이 자동 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-175">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="c69b0-176">탐지된 중요한 정보 유형은 일치 정확도(또는 신뢰 수준)가 75 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-176">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="c69b0-177">많은 중요한 정보 유형은 여러 패턴으로 정의됩니다. 여기서 일치 정확도가 더 높은 패턴은 증거(예: 키워드, 날짜 또는 주소)가 더 많이 발견되어야 하지만, 일치 정확도가 더 낮은 패턴에는 증거가 덜 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-177">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="c69b0-178">**최소** 일치 정확도가 더 낮을수록 콘텐츠가 조건과 일치하기가 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-178">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="c69b0-179">콘텐츠는 이러한 세 가지 중요한 정보 유형 중 어느 유형의 1~9개 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-179">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="c69b0-180">**모두** 로 변경되도록 **최대** 값을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-180">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="c69b0-181">이러한 옵션에 대한 자세한 내용은 를 쉽게 찾을 수 있도록 하기 위해 DLP 문서에서 다음 지침을 참조하세요. [일치하기 더욱 쉽게 혹은 어렵게 만드는 튜닝 규칙](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match) </span><span class="sxs-lookup"><span data-stu-id="c69b0-181">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![중요한 정보 유형을 식별하기 위한 옵션](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)

<span data-ttu-id="c69b0-183">중요한 정보 유형을 사용하여 보존 레이블을 자동으로 적용할 때 고려해야 할 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-183">To consider when using sensitive information types to auto-apply retention labels:</span></span>

- <span data-ttu-id="c69b0-184">새 항목과 수정된 항목은 자동으로 레이블을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-184">New and modified items can be auto-labeled.</span></span>

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="c69b0-185">키워드 또는 검색 가능 속성이 있는 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="c69b0-185">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="c69b0-p115">검색 가능한 속성의 특정 단어, 구 또는 값을 포함하는 쿼리를 사용하여 콘텐츠에 레이블을 자동으로 적용할 수 있습니다. AND, OR 및 NOT과 같은 검색 연산자를 사용하여 쿼리를 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-p115">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![쿼리 편집기](../media/new-retention-query-editor.png)

<span data-ttu-id="c69b0-189">KQL(키워드 쿼리 언어)에 대한 자세한 내용은 [KQL(키워드 쿼리 언어) 구문 참조](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-189">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="c69b0-190">쿼리 기반 자동 적용 정책은 eDiscovery 콘텐츠 검색과 동일한 검색 색인을 사용하여 콘텐츠를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-190">Query-based auto-apply policies use the same search index as eDiscovery content search to identify content.</span></span> <span data-ttu-id="c69b0-191">사용할 수 있는 검색 가능 속성에 대한 자세한 내용은 [내용 검색](keyword-queries-and-search-conditions.md)에 대한 키워드 쿼리 및 검색 조건을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-191">For more information about the searchable properties that you can use, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="c69b0-192">키워드 또는 검색 가능 속성을 사용하여 보존 레이블을 자동으로 적용할 때 고려해야 할 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-192">Some things to consider when using keywords or searchable properties to auto-apply retention labels:</span></span>

- <span data-ttu-id="c69b0-193">SharePoint, OneDrive 및 Exchange에 대해 새 항목, 수정된 항목 및 기존 항목이 자동 레이블로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-193">New, modified, and existing items will be auto-labeled for SharePoint, OneDrive, and Exchange.</span></span>

- <span data-ttu-id="c69b0-194">SharePoint의 경우 이러한 KQL 쿼리에 대해 탐색된 속성 및 사용자 지정 속성이 지원되지 않으므로 미리 정의된 관리 속성만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-194">For SharePoint, crawled properties and custom properties aren't supported for these KQL queries and you must use only predefined managed properties.</span></span> <span data-ttu-id="c69b0-195">그러나 기본적으로 리파이너로 사용하도록 설정된 미리 정의된 관리 속성((RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09 및 RefinableDouble00-09)으로 테넌트 수준에서 매핑을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-195">However, you can use mappings at the tenant level with the predefined managed properties that are enabled as refiners by default (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09, and RefinableDouble00-09).</span></span> <span data-ttu-id="c69b0-196">자세한 내용은 [SharePoint 서버](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)에서 탐색 및 관리 속성에 대한 개요를 참조하고, 지침은 [새 관리 속성](https://docs.microsoft.com/sharepoint/manage-search-schema#create-a-new-managed-property)을(를) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-196">For more information, see [Overview of crawled and managed properties in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview), and for instructions, see [Create a new managed property](https://docs.microsoft.com/sharepoint/manage-search-schema#create-a-new-managed-property).</span></span>

- <span data-ttu-id="c69b0-197">사용자 지정 속성을 고정 속성 중 하나에 매핑하는 경우 KQL 쿼리에서 보존 레이블에 사용하기 전에 24시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-197">If you map a custom property to one of the refiner properties, wait 24 hours before you use it in your KQL query for a retention label.</span></span>

- <span data-ttu-id="c69b0-198">별칭을 사용하여 SharePoint 관리 속성의 이름을 변경할 수 있지만 레이블의 KQL 쿼리에 이 속성을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-198">Although SharePoint managed properties can be renamed by using aliases, don't use these for KQL queries in your labels.</span></span> <span data-ttu-id="c69b0-199">관리 속성의 실제 이름을 항상 지정합니다(예: "RefableString01").</span><span class="sxs-lookup"><span data-stu-id="c69b0-199">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

- <span data-ttu-id="c69b0-200">공백이나 특수 문자가 포함된 값을 검색하려면 큰 따옴표(`" "`)를 사용하여 구를 포함하세요. 예를 들어, `subject:"Financial Statements"`</span><span class="sxs-lookup"><span data-stu-id="c69b0-200">To search for values that contain spaces or special characters, use double quotation marks (`" "`) to contain the phrase; for example, `subject:"Financial Statements"`.</span></span>

- <span data-ttu-id="c69b0-201">URL을 기준으로 항목을 일치시키려면 *Path* 대신 *DocumentLink* 속성을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-201">Use the *DocumentLink* property instead of *Path* to match an item based on its URL.</span></span> 

- <span data-ttu-id="c69b0-202">접미사 와일드카드 검색(예: `*cat`) 또는 부분 문자열 와일드카드 검색(예: `*cat*`)은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-202">Suffix wildcard searches ( such as `*cat`) or substring wildcard searches (such as `*cat*`) aren't supported.</span></span> <span data-ttu-id="c69b0-203">그러나, 접두사 와일드카드 검색(예: `cat*`)이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-203">However, prefix wildcard searches (such as `cat*`) are supported.</span></span>

- <span data-ttu-id="c69b0-204">부분 인덱싱된 항목은 예상된 항목에 레이블을 지정하지 않거나 NOT 연산자를 사용할 때 레이블 지정에서 제외될 것으로 예상되는 항목에 레이블을 지정하지 않는 데 책임이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-204">Be aware that partially indexed items can be responsible for not labeling items that you're expecting, or labeling items that you're expecting to be excluded from labeling when you use the NOT operator.</span></span> <span data-ttu-id="c69b0-205">자세한 내용은 [콘텐츠 검색에서 부분적으로 인덱싱된 항목](partially-indexed-items-in-content-search.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-205">For more information, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>


<span data-ttu-id="c69b0-206">예제 쿼리:</span><span class="sxs-lookup"><span data-stu-id="c69b0-206">Examples queries:</span></span>

| <span data-ttu-id="c69b0-207">워크로드</span><span class="sxs-lookup"><span data-stu-id="c69b0-207">Workload</span></span> | <span data-ttu-id="c69b0-208">예제</span><span class="sxs-lookup"><span data-stu-id="c69b0-208">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="c69b0-209">Exchange</span><span class="sxs-lookup"><span data-stu-id="c69b0-209">Exchange</span></span>   | `subject:"Financial Statements"` |
|<span data-ttu-id="c69b0-210">Exchange</span><span class="sxs-lookup"><span data-stu-id="c69b0-210">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="c69b0-211">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c69b0-211">SharePoint</span></span> | `contenttype:document` |
|<span data-ttu-id="c69b0-212">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c69b0-212">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|<span data-ttu-id="c69b0-213">Exchange 또는 SharePoint</span><span class="sxs-lookup"><span data-stu-id="c69b0-213">Exchange or SharePoint</span></span> | `"customer information" OR "private"`|

<span data-ttu-id="c69b0-214">더 복잡한 예:</span><span class="sxs-lookup"><span data-stu-id="c69b0-214">More complex examples:</span></span>

<span data-ttu-id="c69b0-215">다음 SharePoint 쿼리는 해당 파일에 키워드 **password**, **passwords** 또는 **pw** 이 포함된 경우 Word 문서 또는 Excel 스프레드시트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-215">The following query for SharePoint identifies Word documents or Excel spreadsheets when those files contain the keywords **password**, **passwords**, or **pw**:</span></span>

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

<span data-ttu-id="c69b0-216">다음 Exchange 쿼리는 해당 문서가 이메일에 첨부될 때 **nda** 또는 **비공개 계약** 구문이 포함된 Word 문서 또는 PDF를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-216">The following query for Exchange identifies any Word document or PDF that contains the word **nda** or the phrase **non disclosure agreement** when those documents are attached to an email:</span></span>

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

<span data-ttu-id="c69b0-217">SharePoint에 대한 다음 쿼리는 신용 카드 번호가 포함된 문서를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-217">The following query for SharePoint identifies documents that contain a credit card number:</span></span> 

```
sensitivetype:"credit card number"
```

<span data-ttu-id="c69b0-218">다음 쿼리에는 법적 내용이 포함된 문서 또는 전자 메일을 식별하는 데 도움이 되는 일반적인 키워드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-218">The following query contains some typical keywords to help identify documents or emails that contain legal content:</span></span>

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

<span data-ttu-id="c69b0-219">다음 쿼리는 인력진의 문서 또는 전자 메일을 식별하는 데 도움이 되는 일반적인 키워드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-219">The following query contains typical keywords to help identify documents or emails for human resources:</span></span> 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

<span data-ttu-id="c69b0-220">이 최종 예제에서는 키워드 사이에 연산자를 항상 포함하는 최상의 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-220">Note that this final example uses the best practice of always including  operators between keywords.</span></span> <span data-ttu-id="c69b0-221">키워드(또는 두 개의 속성:값 식) 사이에 공백이 있으면 AND를 사용한 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-221">A space between keywords (or two property:value expressions) is the same as using AND.</span></span> <span data-ttu-id="c69b0-222">항상 연산자를 추가하면 이 예제 쿼리는 키워드를 포함하는 내용 대신 이러한 키워드를 모두 포함하는 내용만 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-222">By always adding operators, it's easier to see that this example query will identify only content that contains all these keywords, instead of content that contains any of the keywords.</span></span> <span data-ttu-id="c69b0-223">키워드가 포함된 내용을 식별하려는 경우 AND 대신 OR을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-223">If your intention is to identify content that contains any of the keywords, specify OR instead of AND.</span></span> <span data-ttu-id="c69b0-224">이 예에서 알 수 있듯이, 연산자를 항상 지정하면 쿼리를 올바르게 해석하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-224">As this example shows, when you always specify the operators, it's easier to correctly interpret the query.</span></span> 

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="c69b0-225">Microsoft Teams 모임 녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="c69b0-225">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="c69b0-226">Teams 모임 녹음/녹화를 유지하고 삭제하는 기능은 미리 보기로 제공되며 기록이 OneDrive 또는 SharePoint에 저장되기 전에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-226">The ability to retain and delete Teams meeting recordings is in preview and won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="c69b0-227">자세한 정보는 [모임 녹음/녹화에 비즈니스용 OneDrive 및 SharePoint 또는 Stream 사용](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-227">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="c69b0-228">사용자의 OneDrive 계정 또는 SharePoint에 저장된 Microsoft Teams 모임 녹음/녹화를 식별하려면 **키워드 쿼리 편집기** 에 대해 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-228">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor**:</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="c69b0-229">대부분의 경우 모임 녹음/녹화는 OneDrive에 저장되지만, </span><span class="sxs-lookup"><span data-stu-id="c69b0-229">Most of the time, meeting recordings are saved to OneDrive.</span></span> <span data-ttu-id="c69b0-230">채널 모임의 경우에는 SharePoint에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-230">But for channel meetings, they are saved in SharePoint.</span></span>


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="c69b0-231">학습 가능한 분류자를 사용하여 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="c69b0-231">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="c69b0-232">학습 가능한 분류자 옵션을 선택할 때 기본 분류자 중 하나 또는 사용자 지정 분류자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-232">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="c69b0-233">기본 제공 분류자에는 **이력서**, **SourceCode**, **대상 희롱**, **비속어**, **위협** 이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-233">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![학습 가능한 분류자 선택](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="c69b0-235">당사는 **비속어** 기본 제공 분류자가 많은 수의 가양성을 생성하였기 에 그 사용을 중단하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-235">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="c69b0-236">이러한 기본 제공 분류자를 사용하지 않도록 하고 현재 사용하고 있는 경우에는 비즈니스 프로세스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-236">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="c69b0-237">대신에 **대상 지정 괴롭힘**,**모독** 그리고 **위협** 기본 제공 분류자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-237">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="c69b0-238">이 옵션을 사용하여 레이블을 자동으로 적용하려면 SharePoint 사이트 및 사서함에 10MB 이상의 데이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-238">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="c69b0-239">학습 가능한 분류자에 대한 자세한 내용은 [학습 가능한 분류자에 대한 자세한 정보(미리 보기)](classifier-learn-about.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-239">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="c69b0-240">Trainable 분류자를 Exchange에 사용하는 경우 최근 릴리스된 [콘텐츠 탐색기에서 분류자를 재학습하는 방법(미리 보기)](classifier-how-to-retrain-content-explorer.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-240">If you use trainable classifiers for Exchange, see the recently released [How to retrain a classifier in content explorer (preview)](classifier-how-to-retrain-content-explorer.md).</span></span>

<span data-ttu-id="c69b0-241">교육 가능한 분류자를 사용하여 보존 레이블을 자동으로 적용할 때 고려해야 할 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-241">To consider when using trainable classifiers to auto-apply retention labels:</span></span>

- <span data-ttu-id="c69b0-242">신규 및 수정된 품목은 자동 라벨링할 수 있으며, 지난 6개월 동안의 기존 품목도 라벨링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-242">New and modified items can be auto-labeled, and existing items from the last six months.</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="c69b0-243">보존 레이블이 적용되는 데 걸리는 시간</span><span class="sxs-lookup"><span data-stu-id="c69b0-243">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="c69b0-244">보존 레이블을 자동으로 적용하는 경우 보존 레이블이 조건과 일치하는 모든 기존 콘텐츠에 적용되는 데 최대 7일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-244">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![자동 적용 레이블이 적용되는 경우를 나타내는 다이어그램](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

<span data-ttu-id="c69b0-246">7일 후에 레이블이 표시되지 않는 경우, 준수 센터의 **레이블 정책** 페이지에서 자동 적용 정책을 선택하여 그 **상태** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-246">If the expected labels don't appear after seven days, check the **Status** of the auto-apply policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="c69b0-247">**꺼짐(오류)** 의 상태가 표시되고 위치에 대한 세부 정보에 정책을 배포하거나(SharePoint의 경우) 혹은 정책 재배포를 시도하는 데(OneDrive의 경우) 예상보다 시간이 오래 걸리고 있다는 메시지가 표시되는 경우, [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell 명령을 실행하여 정책 배포를 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-247">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. <span data-ttu-id="c69b0-248">[보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-248">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c69b0-249">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-249">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="c69b0-250">보존 레이블과 해당 정책 업데이트하기</span><span class="sxs-lookup"><span data-stu-id="c69b0-250">Updating retention labels and their policies</span></span>

<span data-ttu-id="c69b0-251">보존 레이블 또는 자동 적용 정책을 편집할 때 보존 레이블이 이미 콘텐츠에 적용된 경우, 새로 식별된 콘텐츠 외에 이 콘텐츠에도 업데이트된 설정이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-251">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="c69b0-252">다음 내용을 포함하는 레이블이나 정책을 만들고 저장한 후에는 일부 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-252">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="c69b0-253">보존 레이블 및 정책 이름과 보존 기간을 제외한 보존 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-253">The retention label and policy name, and the retention settings except the retention period.</span></span> <span data-ttu-id="c69b0-254">그러나 항목에 레이블이 지정된 시기를 기준으로 보존 기간을 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-254">However, you can't change the retention period when the retention period is based on when items were labeled.</span></span>
- <span data-ttu-id="c69b0-255">항목을 레코드로 표시하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c69b0-255">The option to mark items as a record.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="c69b0-256">변경 방지를 위한 정책 잠금</span><span class="sxs-lookup"><span data-stu-id="c69b0-256">Locking the policy to prevent changes</span></span>

<span data-ttu-id="c69b0-257">아무도 정책을 끄거나, 삭제하거나, 제한 수준을 낮출 수 없도록 하려면, [보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 보존 잠금 사용](retention-preservation-lock.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-257">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c69b0-258">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c69b0-258">Next steps</span></span>

<span data-ttu-id="c69b0-259">SharePoint에서 관리 속성에 자동 적용 보존 레이블 정책을 사용하는 예제 시나리오와 보존 기간을 시작하는 이벤트 기반 보존에 대한 자세한 내용은 [보존 레이블을 사용하여 SharePoint에 저장된 문서의 수명 주기를 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69b0-259">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply retention label policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
