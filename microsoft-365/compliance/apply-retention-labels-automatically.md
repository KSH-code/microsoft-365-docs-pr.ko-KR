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
ms.openlocfilehash: 088a521089d34e74865c94b3cd147b02f8d812cb
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816971"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="513aa-103">보존 레이블 자동 적용하여 콘텐츠를 보존 또는 삭제하기</span><span class="sxs-lookup"><span data-stu-id="513aa-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="513aa-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="513aa-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="513aa-105">[보존 레이블](retention.md)의 가장 강력한 기능 중 하나는 지정된 조건과 일치하는 콘텐츠에 자동으로 레이블을 적용하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="513aa-106">이 경우 조직의 사용자는 레이블을 적용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="513aa-107">Microsoft 365에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="513aa-108">자동 적용 보존 레이블은 다음과 같은 이유 때문에 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="513aa-109">사용자에게 모든 분류를 교육할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="513aa-110">모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="513aa-111">사용자가 더 이상 데이터 거버넌스 정책을 알아야 할 필요가 없으며, 업무에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="513aa-112">콘텐츠에 중요한 정보, 키워드나 검색 가능한 속성 또는 [학습 가능한 분류자](classifier-getting-started-with.md) 일치 항목이 포함된 경우 보존 레이블을 콘텐츠에 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="513aa-113">다음 조건에 따라 보존 레이블을 자동으로 적용하는 프로세스:</span><span class="sxs-lookup"><span data-stu-id="513aa-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![자동 적용 레이블의 역할 및 작업 다이어그램](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="513aa-115">두 가지 관리 단계를 수행하려면 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="513aa-116">자동 정책은 자동으로 보존 레이블을 적용하기 위해 조건과 함께 서비스 측 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="513aa-117">다음을 수행할 때 보존 레이블을 레이블 정책과 함께 자동으로 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="513aa-118">해당 컨테이너의 레이블이 지정되지 않은 콘텐츠에 자동으로 레이블이 지정되도록 SharePoint 라이브러리, 폴더 또는 문서 집합에 기본 보존 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="513aa-119">규칙을 사용하여 전자 메일에 자동으로 보존 레이블 적용하기</span><span class="sxs-lookup"><span data-stu-id="513aa-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="513aa-120">이 시나리오의 경우 [앱에서 보존 레이블 만들기 및 적용하기](create-apply-retention-labels.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="513aa-121">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="513aa-121">Before you begin</span></span>

<span data-ttu-id="513aa-122">조직의 전역 관리자는 보존 레이블과 해당 정책을 만들고 편집할 수 있는 모든 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="513aa-123">전역 관리자로 로그인하지 않은 경우 [보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="513aa-124">보존 레이블을 자동으로 적용하는 방법</span><span class="sxs-lookup"><span data-stu-id="513aa-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="513aa-125">먼저 보존 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-125">First, create your retention label.</span></span> <span data-ttu-id="513aa-126">그런 다음 해당 레이블을 적용하는 자동 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="513aa-127">보존 레이블을 이미 만든 경우에는 [자동 정책 만들기](#step-2-create-an-auto-apply-policy)로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="513aa-128">탐색 지침은 [레코드 관리](records-management.md)를 사용 중인지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="513aa-129">두 시나리오 모두에 대한 지침이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="513aa-130">1단계: 보존 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="513aa-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="513aa-131">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="513aa-132">레코드 관리를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="513aa-132">If you are using records management:</span></span>
        - <span data-ttu-id="513aa-133">**솔루션** > **레코드 관리** > **파일 계획** 탭 > **+ 레이블 만들기** > **보존 레이블**</span><span class="sxs-lookup"><span data-stu-id="513aa-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="513aa-134">레코드 관리를 사용하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="513aa-134">If you are not using records management:</span></span>
       - <span data-ttu-id="513aa-135">**솔루션** > **정보 관리** > **레이블** tab > + **레이블 만들기**</span><span class="sxs-lookup"><span data-stu-id="513aa-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="513aa-136">바로 옵션이 표시되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="513aa-136">Don't immediately see your option?</span></span> <span data-ttu-id="513aa-137">먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="513aa-138">마법사의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="513aa-139">레코드 관리를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="513aa-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="513aa-140">파일 계획 설명자에 대한 자세한 내용은 [파일 계획을 사용하여 보존 레이블 관리의 개요](file-plan-manager.md)를 참조하세요</span><span class="sxs-lookup"><span data-stu-id="513aa-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="513aa-141">보존 레이블을 사용하여 [레코드](records-management.md#records)를 선언하려면 옵션 **항목에 레코드로 표시를 설정**을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-141">To use the retention label to declare a [record](records-management.md#records), enable the option **Mark items as a record**.</span></span>

3. <span data-ttu-id="513aa-142">레이블을 만든 후 레이블을 게시하고 레이블을 자동으로 적용하거나 단지 레이블을 저장하는 옵션이 표시되면 **이 레이블을 특정 콘텐츠에 자동으로 적용**을 선택한 후 **완료**를 선택하여 다음 절차에서 2 단계로 바로 이동하는 자동 레이블 만들기 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-142">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="513aa-143">기존 레이블을 편집하려면 레이블을 선택한 후 **레이블 편집** 옵션을 선택하여 레이블 설명과 [적격 설정](#updating-retention-labels-and-their-policies)을 변경하는 데 사용하는 편집 보유 마법사를 2단계에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-143">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="513aa-144">2단계: 자동 적용 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="513aa-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="513aa-145">자동 적용 정책을 만들 때 지정한 조건에 따라 콘텐츠에 자동으로 적용할 보존 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="513aa-146">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="513aa-147">레코드 관리를 사용하는 경우: **정보 거버넌스**</span><span class="sxs-lookup"><span data-stu-id="513aa-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="513aa-148">**솔루션** > **레코드 관리** > **레이블 정책** 탭 > **레이블 자동 적용**</span><span class="sxs-lookup"><span data-stu-id="513aa-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="513aa-149">레코드 관리를 사용하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="513aa-149">If you are not using records management:</span></span>
        - <span data-ttu-id="513aa-150">**솔루션** > **정보 거버넌스** > **레이블 정책** 탭 > **레이블 자동 적용**</span><span class="sxs-lookup"><span data-stu-id="513aa-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="513aa-151">바로 옵션이 표시되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="513aa-151">Don't immediately see your option?</span></span> <span data-ttu-id="513aa-152">먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="513aa-153">자동 레이블 만들기 마법사의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-153">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="513aa-154">보존 레이블을 자동으로 적용하는 조건을 구성하는 방법에 대한 자세한 내용은이 페이지에서 [보존 레이블 자동 적용에 대한 조건 구성하기](#configuring-conditions-for-auto-apply-retention-labels) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="513aa-155">보존 레이블이 지원하는 위치에 대한 자세한 내용은 [보존 레이블과 위치](retention.md#retention-label-policies-and-locations) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="513aa-156">기존 자동 적용 정책을 편집하려면 정책을 선택하고 선택한 보존 레이블과 모든 [적격 설정](#updating-retention-labels-and-their-policies)을 2단계에서 변경하도록 해주는 보존 정책 편집 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-156">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="513aa-157">보존 레이블 자동 적용에 대한 조건 구성하기</span><span class="sxs-lookup"><span data-stu-id="513aa-157">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="513aa-158">콘텐츠에 다음이 포함될 경우, 콘텐츠에 자동으로 보존 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-158">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="513aa-159">특정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="513aa-159">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="513aa-160">만든 쿼리와 일치하는 특정 키워드 또는 검색 가능한 속성</span><span class="sxs-lookup"><span data-stu-id="513aa-160">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="513aa-161">학습 가능한 분류자와 일치</span><span class="sxs-lookup"><span data-stu-id="513aa-161">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="513aa-162">특정 유형의 중요한 정보가 있는 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="513aa-162">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="513aa-163">중요한 정보에 대한 자동 적용 보존 레이블을 만들면 DLP(데이터 손실 방지) 정책을 만들 때 같은 정책 템플릿 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-163">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="513aa-164">각 템플릿은 특정 중요한 정보 유형을 찾도록 미리 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-164">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="513aa-165">예를 들어 여기에 나와 있는 서식 파일은 미국 ITIN, SSN 및 여권 번호를 **개인 정보** 범주와 **미국 PII (개인 식별 정보) 데이터 서식 파일**에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-165">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![중요한 정보 유형을 갖는 정책 템플릿](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="513aa-167">중요한 정보 유형에 대한 자세한 내용은 [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-167">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="513aa-168">정책 템플릿을 선택한 후 중요한 정보 유형을 추가하거나 제거할 수 있으며 인스턴스 수 및 일치 정확도를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-168">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="513aa-169">다음에 표시된 예제 스크린샷에서는 다음 경우에만 보존 레이블이 자동 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-169">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="513aa-170">탐지된 중요한 정보 유형은 일치 정확도(또는 신뢰 수준)가 75 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-170">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="513aa-171">많은 중요한 정보 유형은 여러 패턴으로 정의됩니다. 여기서 일치 정확도가 더 높은 패턴은 증거(예: 키워드, 날짜 또는 주소)가 더 많이 발견되어야 하지만, 일치 정확도가 더 낮은 패턴에는 증거가 덜 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-171">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="513aa-172">**최소** 일치 정확도가 더 낮을수록 콘텐츠가 조건과 일치하기가 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-172">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="513aa-173">콘텐츠는 이러한 세 가지 중요한 정보 유형 중 어느 유형의 1~9개 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="513aa-174">**모두**로 변경되도록 **최대** 값을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-174">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="513aa-175">이러한 옵션에 대한 자세한 내용은 를 쉽게 찾을 수 있도록 하기 위해 DLP 문서에서 다음 지침을 참조하세요. [일치하기 더욱 쉽게 혹은 어렵게 만드는 튜닝 규칙](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match) </span><span class="sxs-lookup"><span data-stu-id="513aa-175">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![중요한 정보 유형을 식별하기 위한 옵션](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="513aa-177">키워드 또는 검색 가능 속성이 있는 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="513aa-177">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="513aa-p113">검색 가능한 속성의 특정 단어, 구 또는 값을 포함하는 쿼리를 사용하여 콘텐츠에 레이블을 자동으로 적용할 수 있습니다. AND, OR 및 NOT과 같은 검색 연산자를 사용하여 쿼리를 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-p113">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![쿼리 편집기](../media/new-retention-query-editor.png)

<span data-ttu-id="513aa-181">KQL(키워드 쿼리 언어)에 대한 자세한 내용은 [KQL(키워드 쿼리 언어) 구문 참조](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-181">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="513aa-182">쿼리 기반 레이블은 검색 인덱스를 사용하여 콘텐츠를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-182">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="513aa-183">검색 가능한 속성에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-183">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="513aa-184">콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건</span><span class="sxs-lookup"><span data-stu-id="513aa-184">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="513aa-185">SharePoint Server에서 크롤링 및 관리 속성의 개요</span><span class="sxs-lookup"><span data-stu-id="513aa-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="513aa-186">SharePoint 관리 속성에는 별칭이 지원되지만, 보존 레이블을 구성할 때는 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-186">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="513aa-187">관리 속성의 실제 이름을 항상 지정합니다(예: "RefableString01").</span><span class="sxs-lookup"><span data-stu-id="513aa-187">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="513aa-188">예제 쿼리:</span><span class="sxs-lookup"><span data-stu-id="513aa-188">Examples queries:</span></span>

| <span data-ttu-id="513aa-189">워크로드</span><span class="sxs-lookup"><span data-stu-id="513aa-189">Workload</span></span> | <span data-ttu-id="513aa-190">예제</span><span class="sxs-lookup"><span data-stu-id="513aa-190">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="513aa-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="513aa-191">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="513aa-192">Exchange</span><span class="sxs-lookup"><span data-stu-id="513aa-192">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="513aa-193">SharePoint</span><span class="sxs-lookup"><span data-stu-id="513aa-193">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="513aa-194">SharePoint</span><span class="sxs-lookup"><span data-stu-id="513aa-194">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="513aa-195">학습 가능한 분류자를 사용하여 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="513aa-195">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="513aa-196">학습 가능한 분류자 옵션을 선택할 때 기본 분류자 중 하나 또는 사용자 지정 분류자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-196">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="513aa-197">기본 제공 분류자에는 **이력서**, **SourceCode**, **대상 희롱**, **비속어**, **위협**이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-197">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![학습 가능한 분류자 선택](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="513aa-199">당사는 **비속어** 기본 제공 분류자가 많은 수의 가양성을 생성하였기 에 그 사용을 중단하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-199">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="513aa-200">이러한 기본 제공 분류자를 사용하지 않도록 하고 현재 사용하고 있는 경우에는 비즈니스 프로세스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-200">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="513aa-201">대신에 **대상 지정 괴롭힘**,**모독** 그리고 **위협**기본 제공 분류자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-201">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="513aa-202">이 옵션을 사용하여 레이블을 자동으로 적용하려면 SharePoint 사이트 및 사서함에 10MB 이상의 데이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-202">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="513aa-203">학습 가능한 분류자에 대한 자세한 내용은 [학습 가능한 분류자 시작(미리 보기)](classifier-getting-started-with.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-203">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="513aa-204">구성 예는 [분류자를 준비하고 기본 제공 분류자를 사용하는 방법](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="513aa-204">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="513aa-205">보존 레이블이 적용되는 데 걸리는 시간</span><span class="sxs-lookup"><span data-stu-id="513aa-205">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="513aa-206">보존 레이블을 자동으로 적용하는 경우 보존 레이블이 조건과 일치하는 모든 기존 콘텐츠에 적용되는 데 최대 7일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-206">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![자동 적용 레이블이 적용되는 경우를 나타내는 다이어그램](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="513aa-208">보존 레이블과 해당 정책 업데이트하기</span><span class="sxs-lookup"><span data-stu-id="513aa-208">Updating retention labels and their policies</span></span>

<span data-ttu-id="513aa-209">보존 레이블 또는 자동 적용 정책을 편집할 때 보존 레이블이 이미 콘텐츠에 적용된 경우, 새로 식별된 콘텐츠 외에 이 콘텐츠에도 업데이트된 설정이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-209">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="513aa-210">다음 내용을 포함하는 레이블이나 정책을 만들고 저장한 후에는 일부 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-210">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="513aa-211">사용자가 만든 날짜를 기준으로 콘텐츠를 보존하거나 삭제하도록 레이블을 구성하지 않은 경우 보존 기간을 제외한 보존 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-211">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="513aa-212">항목을 레코드로 표시하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="513aa-212">The option to mark items as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="513aa-213">다음 단계</span><span class="sxs-lookup"><span data-stu-id="513aa-213">Next steps</span></span>

<span data-ttu-id="513aa-214">SharePoint에서 관리 속성에 자동 적용 정책을 사용하는 예제 시나리오와 보존 기간을 시작하는 이벤트 기반 보존에 대한 자세한 내용은  [보존 레이블을 사용하여 SharePoint에 저장된 문서의 수명 주기를 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.  </span><span class="sxs-lookup"><span data-stu-id="513aa-214">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
