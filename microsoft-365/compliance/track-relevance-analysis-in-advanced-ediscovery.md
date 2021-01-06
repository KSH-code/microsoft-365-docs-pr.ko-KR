---
title: Advanced eDiscovery에서 검색 결과 추적
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Advanced eDiscovery에서 사례 문제에 대한 관련성 교육 상태 및 결과를 보고 해석하는 방법을 학습합니다.
ms.openlocfilehash: 889153b2d6587daee4212ab8f2b5ccb941e848a4
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760346"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery-classic"></a><span data-ttu-id="7c461-103">Advanced eDiscovery(클래식)에서관행성 분석 추적</span><span class="sxs-lookup"><span data-stu-id="7c461-103">Track Relevance analysis in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="7c461-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7c461-106">Advanced eDiscovery에서, Relevance Track 탭은 태그 탭에 수행된 해당 학습의 계산된 유효성을 표시하고, 해당 과정에 대한 추가 교육 프로세스에서 수행할 다음 단계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="7c461-107">학습 상태 추적</span><span class="sxs-lookup"><span data-stu-id="7c461-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="7c461-108">아래 문제 이름 대화 상자의 다음 예와 같이 사례 문제에 대한 관련성 트랙에서 다음 세부 **정보를** 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="7c461-109">**평가:** 이 진행률 표시기는 이 시점에 수행된 관련성 교육이 오차의 여백으로 평가 목표를 달성한 정도를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="7c461-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="7c461-110">또한 해당 교육 결과의 풍부한 풍부한 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="7c461-111">**교육:** 이 색으로 코딩된 진행률 표시기 및 도구 설명 표시는 관련성 학습 결과 안정성과 각 문제별로 태그가 지정되는 관련성 교육 샘플의 수를 나타내는 숫자 배율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="7c461-112">전문가는 이 과정의 진행률을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="7c461-113">**일괄 계산:** 이 진행률 표시기는 일괄 계산 완료에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="7c461-114">**다음 단계:** 수행할 다음 단계에 대한 권장 사항 표시</span><span class="sxs-lookup"><span data-stu-id="7c461-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="7c461-115">이 예제에는 완료된 색 진행률 표시기 및 확인 표시로 표시된 성공적으로 완료된 문제 평가가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="7c461-116">태그 지정이 진행 중이지만 이 사례는 여전히 불안정한 것으로 간주됩니다(안정성 상태는 도구 설명에도 표시).</span><span class="sxs-lookup"><span data-stu-id="7c461-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="7c461-117">다음 단계 권장은 "교육"입니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-117">The next step recommendation is "Training".</span></span> 
    
    ![관련 트랙 훈련 1 단계](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="7c461-119">확장된 보기에는 추가 정보 및 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="7c461-120">표시된 현재 오류 여백은 이미 태그가 지정되어 있는 기존 평가 파일이 있는 경우 현재 평가 상태의 회수 오차입니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="7c461-121">평가 단계는 문제당 평가 확인란의  선택을 취소한 다음 "모든 문제"에 대해 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="7c461-122">그러나 이 문제의 통계는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="7c461-123">> 확인란 선택을 취소하는 것은 평가가 수행되기 전에만 수행할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="7c461-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="7c461-124">여러 문제가 있는 경우 각 문제에 대해 확인란이 선택 취소된 경우 평가가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="7c461-125">첫 번째 샘플 파일 집합으로 평가가 완료되지 않은 경우 평가는 더 많은 파일에 태그를 지정하기 위한 다음 단계가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="7c461-126">관련성 **추적에서** 교육 진행률 표시기 및 도구 팁은 안정성에 도달하는 데 필요한 예상 추가 샘플 수를 \> 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="7c461-127">이 예상치에는 필요한 추가 교육에 대한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![관련 트랙 훈련](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="7c461-129">태그 지정을 완료하고 교육을 계속해야 하는 경우 **교육을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c461-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="7c461-130">추가 교육을 위해 로드된 파일 집합에서 다른 샘플 파일 집합이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="7c461-131">그런 다음 태그 탭으로 돌아와서 더 많은 파일에 태그를 지정하고 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="7c461-132">안정적인 교육 수준에 도달</span><span class="sxs-lookup"><span data-stu-id="7c461-132">Reaching stable training levels</span></span>

<span data-ttu-id="7c461-133">평가 파일이 안정적인 수준의 교육을 수행한 후 Advanced eDiscovery는 일괄 계산을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c461-134">일반적으로 안정된 교육 샘플이 세 번 제공된 후 다음 단계는 "일괄 계산"입니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="7c461-135">예를 들어 이전 샘플의 파일 태그가 변경되거나 시드 파일이 추가된 경우와 같은 예외가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="7c461-136">일괄 계산 수행</span><span class="sxs-lookup"><span data-stu-id="7c461-136">Performing Batch calculation</span></span>

<span data-ttu-id="7c461-137">일괄 계산은 교육이 성공적으로 완료된 후 다음 단계로 실행됩니다(안정된 교육 상태가 진행률 표시줄에 표시되면 도구 팁에서 확인 표시 및 안정 상태). 일괄 계산은 전체 파일 수집에 대한관련성 교육 중에 획득한 지식을 적용하여 파일의 타당성 평가 및관련성 점수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="7c461-138">문제가 두 개 이상이면 문제당 일괄 계산이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="7c461-139">일괄 계산 중에 모든 파일을 처리하는 동안 진행률이 모니터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="7c461-140">여기서 권장되는 다음 단계는 "없음"으로, 이 시점에서 추가적인 관련성 교육이 필요하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="7c461-141">다음 단계는 '타당성 **결정' \> 탭입니다.**</span><span class="sxs-lookup"><span data-stu-id="7c461-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="7c461-142">일괄 처리 계산 후 새 파일을 가져오는 경우 관리자는 가져온 파일을 새 로드에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c461-143">일괄 계산 중에 **취소를** 클릭하면 이미 실행된 것이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="7c461-144">Batch 계산을 다시 실행하면 마지막 실행 지점에서 프로세스가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="7c461-145">태그 지정 일관성 평가</span><span class="sxs-lookup"><span data-stu-id="7c461-145">Assessing tagging consistency</span></span>

<span data-ttu-id="7c461-146">파일 태그 지정에 불일치가 있는 경우 분석에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="7c461-147">결과가 최적이 아니거나 일관성이 의심스러우면 Advanced eDiscovery 태그 지정 일관성 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="7c461-148">불일치하게 태그가 지정될 수 있는 파일 목록이 반환됩니다. 필요한 경우 해당 파일을 검토하고 다시 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c461-149">평가 후 7회 이상의 교육이 진행된 후 관련성 추적 문제 세부 결과 교육 진행률에서 태그 일관성을 볼  \>  \>  \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7c461-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="7c461-150">이 검토는 한 번의 문제로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="7c461-151">**Relevance \> Track에서** 문제의 행을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="7c461-152">다음 단계 **오른쪽에서** 수정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c461-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="7c461-153">다음 **단계** 옵션으로 태그 불일치 선택, 7개의 교육 샘플 후 확인을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="7c461-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="7c461-154">태그 **불일치** 선택.</span><span class="sxs-lookup"><span data-stu-id="7c461-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="7c461-155">태그 **탭에** 필요한 경우 다시 태그를 지정하는 불일치 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="7c461-156">**계산을** 클릭하여 변경 내용을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="7c461-157">태그 불일치에 태그를 지정한 후의 다음 단계는 "교육"입니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="7c461-158">결과 보기 및 사용</span><span class="sxs-lookup"><span data-stu-id="7c461-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="7c461-159">관련성 **\>** 추적 탭에서 문제의 행을 확장하고 자세한 결과 옆에 **있는** 보기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c461-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="7c461-160">아래와 같이 자세한 결과 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![자세한 결과 교육 하는 관련성](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="7c461-162">태그 지정 요약</span><span class="sxs-lookup"><span data-stu-id="7c461-162">Tagging summary</span></span>

 <span data-ttu-id="7c461-163">아래 표시된 예제에서  태그 지정 요약에는 각 평가, 교육 및 추가 파일 태그 지정 프로세스의 합계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![관련성 추적 태그 요약](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="7c461-165">키워드</span><span class="sxs-lookup"><span data-stu-id="7c461-165">Keywords</span></span>

<span data-ttu-id="7c461-166">키워드는 파일의 관련성을 나타내는 중요한 지표로 Advanced eDiscovery로 식별된 파일의 고유한 문자열, 단어, 구 또는 일련의 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="7c461-167">"포함" 열은 관련성으로 태그가 지정된 파일의 키워드 및 가중치를 나열하고 "제외" 열에는 관련이 없는 것으로 태그가 지정된 파일의 키워드 및 가중치가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="7c461-168">Advanced eDiscovery는 음수 또는 양수 키워드 가중치 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="7c461-169">가중치가 높을수록 키워드가 나타나는 파일에 일괄 계산 중에 관련성 점수가 더 높게 할당될 가능성이 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="7c461-170">고급 eDiscovery 키워드 목록을 사용하여 전문가가 작성한 목록을 보완하거나 파일 검토 프로세스의 어느 시점에서든 간접적인 평가로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="7c461-171">교육 진행률</span><span class="sxs-lookup"><span data-stu-id="7c461-171">Training progress</span></span>

<span data-ttu-id="7c461-172">교육 **진행률** 창에는 아래 예제와 같이 교육 진행률 그래프와 품질 표시기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![관련 교육 진행 상황 관리](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="7c461-174">**교육 품질 표시기:** 다음과 같이 태그 지정 일관성의 등급을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="7c461-175">**양호:** 파일에 일관되게 태그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="7c461-176">(녹색 표시등 표시)</span><span class="sxs-lookup"><span data-stu-id="7c461-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="7c461-177">**보통**: 일부 파일의 태그가 불일치하게 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="7c461-178">(노란색 조명 표시)</span><span class="sxs-lookup"><span data-stu-id="7c461-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="7c461-179">**경고:** 많은 파일이 불일치하게 태그가 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="7c461-180">(빨간색 표시등 표시)</span><span class="sxs-lookup"><span data-stu-id="7c461-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="7c461-181">**교육 진행률 그래프:** F-측정 값과 비교하여 여러 가지 해당 교육 주기 후의 해당 학습 안정성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="7c461-182">그래프에서 왼쪽에서 오른쪽으로 이동하면 신뢰 구간이 좁아지고 F 측정값과 함께 Advanced eDiscovery와 함께 사용되어 해당 학습 결과가 최적화될 때 안정성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c461-183">회수가 정밀도의 2배 가중치를 받는 F 측정 메트릭인 F2를 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="7c461-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="7c461-184">풍부한(25% 이상)가 있는 경우의 경우 F1(1:1 비율)을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="7c461-185">F-측정 비율은 고급 설정과의 연결성 설정에서  \> **구성할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7c461-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="7c461-186">일괄 계산 결과</span><span class="sxs-lookup"><span data-stu-id="7c461-186">Batch calculation results</span></span>

<span data-ttu-id="7c461-187">일괄 **계산 결과** 창에는 다음과 같이 해당 내용에 대해 점수가 매기던 파일 수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="7c461-188">**성공**</span><span class="sxs-lookup"><span data-stu-id="7c461-188">**Success**</span></span>
    
- <span data-ttu-id="7c461-189">**빈**: 공백/탭과 같은 텍스트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="7c461-190">**실패**: 과도한 크기로 인해 또는 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="7c461-191">**무시:** 과도한 크기로 인해</span><span class="sxs-lookup"><span data-stu-id="7c461-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="7c461-192">**Nebulous**: 의미 없는 텍스트가 포함되거나 문제와 관련된 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="7c461-193">비어 있거나 실패하거나, 무시하거나, 거동이면 -1의관위 점수를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="7c461-194">교육 통계</span><span class="sxs-lookup"><span data-stu-id="7c461-194">Training statistics</span></span>

<span data-ttu-id="7c461-195">교육 **통계 창에는** Advanced eDiscovery 관련성 교육의 결과를 기반으로 통계 및 그래프가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![관련 트랙 교육 통계](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="7c461-197">이 보기에는 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-197">This view shows the following:</span></span>
  
- <span data-ttu-id="7c461-198">**리뷰 회수율**: 가설적인 선형 검토에서 관련성 점수에 따라 결과를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="7c461-199">검토 집합 크기 집합이 설정된 경우 회수는 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="7c461-200">**매개** 변수: 전체 사례에 대한 파일 수집과 관련한 검토 집합에 대한 누적 계산 통계입니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="7c461-201">**검토:** 이 컷오프에 따라 검토할 파일의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="7c461-202">**회수:** 검토 집합에 있는 관련 파일의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="7c461-203">**타당성** 점수로 분포: 왼쪽에 진한 회색 표시의 파일이 잘리기 점수 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="7c461-204">도구 팁에는 전체 파일과 관련된 리뷰 파일 집합의 관련성 점수 및 관련 백분율이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c461-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
