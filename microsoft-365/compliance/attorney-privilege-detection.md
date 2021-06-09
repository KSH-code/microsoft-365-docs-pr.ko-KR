---
title: 2013에서 변호사-클라이언트 권한 검색 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 변호사-클라이언트 권한 검색 모델을 사용하여 특정 사례의 콘텐츠를 검토할 때 권한이 부여된 콘텐츠에 대한 기계 학습 기반 검색을 Advanced eDiscovery 있습니다.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358044"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="13ffe-103">2013에서 변호사-클라이언트 권한 검색 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="13ffe-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="13ffe-104">eDiscovery 프로세스의 검토 단계에서 중요한 비용과 관련이 있는 측면은 권한이 부여된 콘텐츠에 대한 문서를 검토하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="13ffe-105">Advanced eDiscovery 권한 있는 콘텐츠에 대한 기계 학습 기반 검색을 제공하면 이 프로세스의 효율성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="13ffe-106">이 기능을 *변호사-클라이언트 권한 검색이라고 합니다.*</span><span class="sxs-lookup"><span data-stu-id="13ffe-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="13ffe-107">작동 방식</span><span class="sxs-lookup"><span data-stu-id="13ffe-107">How does it work?</span></span>

<span data-ttu-id="13ffe-108">변호사-클라이언트 권한 검색을 사용하도록 설정하면 검토 집합의 데이터를 분석할 때 검토 집합의 [](analyzing-data-in-review-set.md) 모든 문서가 변호사-클라이언트 권한 검색 모델에 의해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="13ffe-109">이 모델에서는 다음 두 가지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-109">The model looks for two things:</span></span>

- <span data-ttu-id="13ffe-110">권한 있는 콘텐츠 - 이 모델에서는 기계 학습을 사용하여 문서에 본질적으로 적합한 콘텐츠가 포함되어 있는지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="13ffe-111">참가자 – 변호사-클라이언트 권한 검색 설정의 일부로 조직의 변호사 목록을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="13ffe-112">그런 다음 모델은 문서의 참가자를 변호사 목록과 비교하여 문서에 변호사 참가자가 적어도 한 명 이상 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="13ffe-113">이 모델에서는 모든 문서에 대해 다음과 같은 세 가지 속성을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="13ffe-114">**AttorneyClientPrivilegeScore:** 문서가 실제로 합법적일 가능성 점수의 값은 **0에서 1** **사이입니다.**</span><span class="sxs-lookup"><span data-stu-id="13ffe-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="13ffe-115">**HasAttorney:** 이 속성은 문서 참가자 중 한 자가 변호사 목록에 나열된 경우 **true로** 설정됩니다. 그렇지 않으면 값이 **false입니다.**</span><span class="sxs-lookup"><span data-stu-id="13ffe-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="13ffe-116">또한 조직에서 변호사 목록을 업로드하지 않은 경우 이 값은 **false** 로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="13ffe-117">**IsPrivilege:** 이 속성은  **AttorneyClientPrivilegeScore** 값이 임계값을 초과하거나  문서에 변호사 참가자가 있는 경우 true로 설정됩니다. 그렇지 않으면 값이 **false로 설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="13ffe-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="13ffe-118">이러한 속성 및 해당 값은 다음 스크린샷과 같이 검토 집합에 있는 문서의 파일 메타데이터에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![파일 메타데이터에 표시된 변호사-클라이언트 권한 속성](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="13ffe-120">이러한 세 속성은 검토 집합 내에서도 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="13ffe-121">자세한 내용은 [검토 집합의 데이터 쿼리를 참조하세요.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="13ffe-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="13ffe-122">변호사-클라이언트 권한 검색 모델 설정</span><span class="sxs-lookup"><span data-stu-id="13ffe-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="13ffe-123">변호사-클라이언트 권한 검색 모델을 사용하도록 설정하려면 조직에서 이를 켜고 변호사 목록을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="13ffe-124">1단계: 변호사-클라이언트 권한 검색 켜기</span><span class="sxs-lookup"><span data-stu-id="13ffe-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="13ffe-125">조직의 eDiscovery 관리자인 사용자(eDiscovery 관리자 역할 그룹의 eDiscovery 관리자 하위 그룹의 구성원)는 해당 사례에서 모델을 사용할 수 있도록 Advanced eDiscovery 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="13ffe-126">보안 및 & 센터에서 **eDiscovery**> Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="13ffe-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="13ffe-127">Advanced eDiscovery **홈** 페이지의 설정 타일에서 전역 분석 **설정 구성을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="13ffe-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   !["실험적 기능 구성"을 선택합니다.](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="13ffe-129">분석 **설정 탭에서** **변호사-클라이언트** 권한 관리 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="13ffe-130">**비공개 유지 권한** 플라이아웃 페이지에서 토글을 사용하여 기능을 켠 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="13ffe-131">2단계: 업로드 목록 보기(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="13ffe-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="13ffe-132">변호사-클라이언트 권한 검색 모델을 전체적으로 활용하고 이전에 설명한 Has **Attorney** or **Potentially Privileged** detection의 결과를 사용하려면 조직에서 일하는 변호사 및 법률 담당자의 전자 메일 주소 목록을 업로드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="13ffe-133">변호사-클라이언트 권한 검색 모델에서 사용할 변호사 목록을 업로드하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="13ffe-p106">헤더 행이 없는 .csv 파일을 생성하고 각 해당 사용자의 전자 메일 주소를 별도의 줄에 추가합니다. 이 파일을 로컬 컴퓨터에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-p106">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line. Save this file to your local computer.</span></span>

2. <span data-ttu-id="13ffe-136">Advanced eDiscovery **홈** 페이지의 설정 타일에서  실험적 기능 구성을 선택한 다음 변호사-클라이언트 권한 설정 **관리를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="13ffe-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="13ffe-137">**변호사-클라이언트 권한** 페이지가 표시되고, **변호사-클라이언트** 권한 검색 토글이 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![변호사-클라이언트 권한 플라이아웃 페이지](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="13ffe-139">**찾아보기를** 선택한 다음 1단계에서 .csv 파일을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="13ffe-140">**저장을** 선택하여 변호사 목록을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="13ffe-141">변호사-클라이언트 권한 검색 모델 사용</span><span class="sxs-lookup"><span data-stu-id="13ffe-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="13ffe-142">이 섹션의 단계에 따라 검토 집합의 문서에 대해 변호사-클라이언트 권한 검색을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="13ffe-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="13ffe-143">1단계: 변호사-클라이언트 권한 검색 모델을 사용하여 스마트 태그 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="13ffe-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="13ffe-144">검토 프로세스에서 비공개 유지 권한 탐지 결과를 확인하는 주요 방법 중 하나는 스마트 태그 그룹을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="13ffe-145">스마트 태그 그룹은 비공개 유지 권한 탐지 결과를 나타내고 스마트 태그 그룹의 태그 옆에 결과를 인라인으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="13ffe-146">이렇게 하면 문서 검토 중에 권한이 부여될 수 있는 문서를 빠르게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="13ffe-147">또한 스마트 태그 그룹의 태그를 사용하여 문서를 권한 있는 문서 또는 권한 없는 문서로 태그할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="13ffe-148">스마트 태그에 대한 자세한 내용은 에서 스마트 태그 [Advanced eDiscovery.](smart-tags.md)</span><span class="sxs-lookup"><span data-stu-id="13ffe-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="13ffe-149">1단계에서 분석한 문서가 포함된 검토 집합에서 검토  집합 관리를 선택한 다음 태그 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="13ffe-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="13ffe-150">태그 **아래에서** 그룹 추가 옆의 풀다운을 선택한 **다음** 스마트 태그 그룹 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="13ffe-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   !["스마트 태그 그룹 추가"를 선택합니다.](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="13ffe-152">스마트 **태그 모델** 선택 페이지에서 변호사-클라이언트 권한 옆의  **선택을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="13ffe-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="13ffe-153">변호사-클라이언트 **권한이라는** 태그 그룹이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="13ffe-154">이 태그에는 **모델에서** 생성한 가능한 결과에 해당하는 Positive 및 **Negative이라는** 두 개의 자식 태그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![변호사-클라이언트 권한 스마트 태그 그룹](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="13ffe-156">검토에 따라 태그 그룹 및 태그 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="13ffe-157">예를 들어 양수 이름을  **Privileged로,** **음수는** 권한 없습니다.로 **이름을 다시 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="13ffe-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="13ffe-158">2단계: 검토 집합 분석</span><span class="sxs-lookup"><span data-stu-id="13ffe-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="13ffe-159">검토 집합의 문서를 분석하면 변호사-클라이언트 권한 검색 모델도 실행되어 해당 속성(작동 방식에 설명)이 검토 집합의 모든 문서에 추가됩니다. [](#how-does-it-work)</span><span class="sxs-lookup"><span data-stu-id="13ffe-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="13ffe-160">검토 집합의 데이터를 분석하는 데 대한 자세한 내용은 에서 검토 집합의 데이터 [분석을 Advanced eDiscovery.](analyzing-data-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="13ffe-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="13ffe-161">3단계: 권한 있는 콘텐츠 검토를 위해 스마트 태그 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="13ffe-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="13ffe-162">검토 집합을 분석하고 스마트 태그를 설정한 후 다음 단계는 문서를 검토하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="13ffe-163">모델에서 문서가 잠재적으로 권한이 부여된 것으로 판단되면  태그 지정 패널의 해당 스마트 태그는 변호사-클라이언트 권한 검색에서 생성되는 다음과 같은 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="13ffe-164">문서에 본질적으로 합법적일 수 있는 콘텐츠가 있는 경우 **Legal** 콘텐츠 레이블이 해당 스마트 태그(이 경우 기본 **양수** 태그) 옆에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="13ffe-165">문서에 조직의 변호사 목록에 있는 참가자가 있는 경우 해당 스마트 태그 옆에 **'변호사'** 레이블이 표시됩니다(이 경우 기본 양수 **태그도** 해당).</span><span class="sxs-lookup"><span data-stu-id="13ffe-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="13ffe-166">문서에 본질적으로 법적이 될 수 있는 콘텐츠가 있으며 참가자가  변호사  목록에 있는 경우 법률 관련 콘텐츠와 변호사 레이블이 모두 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="13ffe-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="13ffe-167">모델에서 문서에 본질적으로 합법적인 콘텐츠가 포함되어 있지 않다고 판단하거나 변호사 목록의 참가자를 포함하지 않는 경우 태그 지정 패널에 두 레이블이 모두 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="13ffe-168">예를 들어 다음 스크린샷에는 두 개의 문서가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="13ffe-169">첫 번째 콘텐츠에는 본질적으로 합법적인 콘텐츠가 포함되어 있으며 참가자가 변호사 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="13ffe-170">두 번째에는 둘 다 포함되어 있으므로 레이블을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-170">The second contains neither and therefore doesn't display any labels.</span></span>

![변호사 및 법률 콘텐츠 레이블이 있는 문서화](../media/AeDTaggingPanelLegalContentAttorney.png)

![레이블이 없는 문서](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="13ffe-173">문서를 검토하여 문서에 권한이 부여된 콘텐츠가 포함되어 있는지 확인한 후 해당 태그를 지정하여 문서에 태그를 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ffe-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
