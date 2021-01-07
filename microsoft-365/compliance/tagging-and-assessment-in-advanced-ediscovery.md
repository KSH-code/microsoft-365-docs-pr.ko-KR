---
title: Advanced eDiscovery의 태그 지정 및 평가
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: 파일에 태그를 지정하고 Advanced eDiscovery에서 평가 결과를 검토하는 등 평가 교육을 수행하는 단계를 검토합니다.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769193"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="b66d9-103">Advanced eDiscovery의 연결 모듈에 태그 지정 및 평가</span><span class="sxs-lookup"><span data-stu-id="b66d9-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="b66d9-104">이 섹션에서는 Advanced eDiscovery의 관련성 모듈에서 평가 절차에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="b66d9-105">평가 교육 및 분석 수행</span><span class="sxs-lookup"><span data-stu-id="b66d9-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="b66d9-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span><span class="sxs-lookup"><span data-stu-id="b66d9-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="b66d9-107">예를 들어 이 절차에서는 샘플 평가 집합 500개 파일이  만들어지고 태그 탭이 표시됩니다. 여기에는 태그 패널, 표시된 파일 콘텐츠 및 기타 태그 옵션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![평가 대 한 관련 태그 탭](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="b66d9-109">샘플의 각 파일을 검토하고, 각 사례 문제와 관련된 파일을 확인한 다음, 관련성(R), 관련성(NR) 및 태그 지정  패널 창의 건너뛰기 단추를 사용하여 파일에 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="b66d9-110">평가에는 태그가 있는 500개 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="b66d9-111">파일이 "건너뛴" 경우 태그를 지정하는 파일이 더 많이 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="b66d9-112">샘플의 모든 파일에 태그를 지정한 후 계산을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b66d9-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="b66d9-113">평가 현재 오류 여백과 풍부한 내용은  아래와 같이 관련성 트랙 탭에 계산되고 표시되고 문제당 세부 정보가 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="b66d9-114">이 대화 상자에 대한 자세한 내용은 평가 결과 검토 [섹션에서 설명합니다.](#reviewing-assessment-results)</span><span class="sxs-lookup"><span data-stu-id="b66d9-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![관련 트랙-평가](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="b66d9-116">기본적으로 문제의 평가 진행률 표시기가 완료되면 기본 다음 단계로 진행하여 평가 샘플이 검토되고 관련 파일이 태그가 지정되었음을 나타내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="b66d9-117">> 경우 탭 결과를 보고 오류 여백과 다음 단계를 제어하려면 다음 단계  옆에 있는 수정을 클릭하고 평가 계속을 선택한 다음 확인을 **클릭합니다.**  </span><span class="sxs-lookup"><span data-stu-id="b66d9-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="b66d9-118">평가 **확인란** 오른쪽으로  수정을 클릭하여 문제당 평가 매개 변수를 보고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="b66d9-119">다음 **예제와 같이** 각 문제의 평가 수준 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![평가 수준 사례 문제](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="b66d9-121">이 문제의 다음 매개 변수는 계산되어 평가 수준 대화 **상자에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="b66d9-122">**회수 예상** 대상 오차: 이 값을 기준으로 검토해야 하는 예상 추가 파일 수가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="b66d9-123">회수에 사용되는 여백은 75%보다 높고 신뢰 수준은 95%입니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="b66d9-124">**추가 평가 파일 필요:** 현재 오류 여백의 요구 사항이 충족되지 않은 경우 필요한 파일 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="b66d9-125">현재 오차 여백을 조정하고 다른 오류 여백의 효과를 표시(문제당):</span><span class="sxs-lookup"><span data-stu-id="b66d9-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="b66d9-126">문제 **선택 목록에서** 문제를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="b66d9-127">회수 **예상 대상 오차 여백에서** 새 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="b66d9-128">업데이트 **값을 클릭하여** 조정의 영향을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="b66d9-129">평가 **수준** 대화 상자에서 고급을 **클릭하여** 다음과 같은 추가 매개 변수 및 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![평가 수준 사례 문제를 상세하게 보기](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="b66d9-131">**예상 풍부한 환경:** 현재 평가 결과에 따라 풍부한 예상</span><span class="sxs-lookup"><span data-stu-id="b66d9-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="b66d9-132">**가정된 회수율:** 기본적으로 대상 오류 여백은 75% 이상의 회수에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="b66d9-133">이 **매개** 변수를 변경하고 다른 회수 값 범위에서 오류 여백을 제어하려면 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="b66d9-134">**신뢰 수준**: 기본적으로 신뢰도에 대한 권장 오차 여백은 95%입니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="b66d9-135">이 **매개 변수를** 변경하려면 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="b66d9-136">**예상되는** 풍부한 오차 여백: 업데이트된 값을 제공하면 모든 추가 평가 파일을 검토한 후 풍부한 오차의 예상 여백입니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="b66d9-137">**추가 평가 파일이 필요합니다.** 업데이트된 값을 제공하면 대상에 도달하기 위해 검토해야 하는 추가 평가 파일의 수가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="b66d9-138">**필요한 총 평가 파일:** 업데이트된 값을 제공하면 검토에 필요한 총 평가 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="b66d9-139">**평가의** 예상 관련 파일 수: 업데이트된 값을 제공하면 모든 추가 평가 파일을 검토한 후 전체 평가에 예상되는 관련 파일 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="b66d9-140">매개 **변수가 변경된** 경우 값 다시 계산을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="b66d9-141">작업을 마치면 문제가 하나이면 **확인을** 클릭하여 변경 내용을  저장합니다(또는 검토하거나 수정한 후 마침에 여러 문제가 있는 경우 **다음).**</span><span class="sxs-lookup"><span data-stu-id="b66d9-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="b66d9-142">문제가 여러 개 있는 경우 모든 문제를 검토하거나 조정한 후 평가 **수준:** 요약 대화 상자가 다음 예제와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![평가 수준 요약](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="b66d9-144">평가가 성공적으로 완료된 경우, 다음 단계로 진행하여관련성 교육을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="b66d9-145">평가 결과 검토</span><span class="sxs-lookup"><span data-stu-id="b66d9-145">Reviewing assessment results</span></span>

<span data-ttu-id="b66d9-146">평가 샘플에 태그가 지정되면 평가 결과가 계산되고 해당 트랙 탭에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="b66d9-147">확장된 트랙 표시에 표시되는 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="b66d9-148">회수 예상에 대한 평가 현재 오차 여백</span><span class="sxs-lookup"><span data-stu-id="b66d9-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="b66d9-149">예상 풍부한성</span><span class="sxs-lookup"><span data-stu-id="b66d9-149">Estimated richness</span></span>

- <span data-ttu-id="b66d9-150">필요한 추가 평가 파일(검토용)</span><span class="sxs-lookup"><span data-stu-id="b66d9-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="b66d9-151">평가 현재 오류 여백은 Advanced eDiscovery에서 권장하는 오류 여백입니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="b66d9-152">"추가 평가 파일 필요"에 표시되는 번호는 해당 권장에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="b66d9-153">평가 진행률 표시기는 현재 오차 여백이 있는 경우 평가의 완료 수준을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="b66d9-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="b66d9-154">평가가 진행 중이면 사용자는 다른 평가 샘플에 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="b66d9-155">평가 진행률 표시기가 평가가 완료된 것으로 표시될 때 평가 샘플 검토가 완료되고 관련 파일이 태그가 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="b66d9-156">확장된 트랙 표시에는 권장되는 다음 단계, 평가 통계 및 자세한 결과에 대한 액세스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="b66d9-157">유용성이 매우 낮을 경우 유용한 통계를 생성하기 위해 최소한의 관련 파일에 도달하는 데 필요한 추가 평가 파일의 수가 매우 높습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="b66d9-158">그런 다음 고급 eDiscovery를 통해 교육을 진행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="b66d9-159">평가 진행률 표시기는 음영이 표시되고 통계를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="b66d9-160">통계 기반 손떨림 보정이 없을 경우 정확도 및 신뢰 수준이 낮은 결과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="b66d9-161">그러나 찾은 관련 파일의 백분율을 알 필요가 없는 경우 이러한 결과를 사용하여 관련 파일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="b66d9-162">마찬가지로, 이 상태를 사용하여 관련성 점수가 특정 문제와 관련된 파일에 대한 액세스를 가속화할 수 있는 낮은 풍부한 문제를 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="b66d9-163">**Relevance \> Track** 탭에서 확장된 문제 표시를 통해 다음과 같은 보기 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="b66d9-164">다음 단계와 같이 권장되는 다음 **단계:** 오른쪽으로 수정 단추를 클릭한  다음 다음 단계에서 다른 단계를 선택하여(문제별) 태그 지정을 무시할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b66d9-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="b66d9-165">평가 진행률 표시기가 완료되지 않은 경우 평가는 추가 평가 파일에 태그를 지정하고 통계 정확도를 높이기 위한 다음 권장 옵션이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="b66d9-166">수정을 클릭하고 평가 수준 대화 상자에서 회수 예상 대상 오류 여백을 변경하고 업데이트 값을 클릭하여 오류 여백을 변경하고 해당 영향을 평가할 **수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="b66d9-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="b66d9-167">또한 이 대화 상자에서 고급을 클릭하여 고급 옵션을 볼 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b66d9-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="b66d9-168">보기를 클릭하여 추가 평가 수준 통계 및 해당 영향을 볼 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b66d9-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="b66d9-169">표시된 세부 정보 결과 대화 상자에서 500개 이상의 태그가 지정된 평가 파일이 있으며 18개 이상의 파일이 문제와 관련된 것으로 태그가 지정되어 있는 경우 문제당 통계를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b66d9-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
