---
title: Advanced eDiscovery에서 데이터 분석에 연결 모듈 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery의 해당 워크플로 및 교육 단계에 대한 설명이 있는 증거의 데이터를 분석하는 방법을 알아보십시오.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286064"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="77009-103">Advanced eDiscovery에서 데이터 분석에 연결 모듈 사용</span><span class="sxs-lookup"><span data-stu-id="77009-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="77009-104">Advanced eDiscovery에서 관련성 모듈에는 사례와 관련된 파일의 관련성 교육 및 검토가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="77009-105">해당 워크플로를 사용하려면 검토 집합 내에서 검토 집합 관리로 이동한 후 해당성 표시를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="77009-106">워크플로를 시작하기 전에 완료해야 하는 몇 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="77009-107">프로세스: 검토 집합에 추가된 각 부하 집합은 여기에 "컨테이너"로 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="77009-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="77009-108">관련성 모듈에 추가하려면 먼저 이러한 문서를 처리해야 합니다. 이 경우 특정 문제를 위해 이러한 태그를 시드로 표시하거나 미리 태그가 지정될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="77009-109">관련성 추가: 관련성 로드에서 관련성에 대해 처리된 문서를 추가하여 교육에 사용할 수 있도록 할 \> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="77009-110">다음과 같이 워크플로가 표시 및 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-110">The Relevance workflow is shown and described as follows:</span></span>
  
![관련성 워크플로](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="77009-112">**평가 및 추적 주기:**</span><span class="sxs-lookup"><span data-stu-id="77009-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="77009-113">**평가:** 임의 파일 샘플을 기반으로 초기 평가를 사용할 수 있으며, 이 평가를 사용하여 결정을 적용하여 예측 코딩 프로세스의 성능을 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="77009-114">**트랙:** 프로세스의 통계 유효성을 모니터링하는 동안 평가의 중간 결과를 계산하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="77009-115">**교육 및 추적 주기**</span><span class="sxs-lookup"><span data-stu-id="77009-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="77009-116">**태그**: Advanced eDiscovery는 개별 파일의 전문가의 되번기 검토 및 태그 지정에 따라 각 문제와 관련성 기준을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="77009-117">**추적:** 프로세스의 통계 유효성을 모니터링하는 동안 관련성 교육의 중간 결과를 계산하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="77009-118">**일괄** 계산: 누적 및 학습된 해당 기준이 전체 파일 모음에 적용되고 각 파일에 대해 해당 점수가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="77009-119">**결정**: 전체 사례에 적용된 분석 결과는 일괄 계산 후 표시되고 문서 검토 결정을 내리는 데 사용되는 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="77009-120">**테스트:** 결과를 테스트하여 Advanced eDiscovery 처리의 유효성과 유효성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="77009-121">**검색**: 관련성 워크플로가 완료되면 검토 집합 내에서 쿼리를 실행할 때 문제의 문서의 읽기 백분위수와 같은 출력을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="77009-122">관련성 교육 및 검토에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="77009-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="77009-123">다음은 관련성 교육 및 검토에 대한 지침의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="77009-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="77009-124">**오류 및** 불일치: 교육 중에 태그 지정 오류가 발생하면 이전 파일 샘플로 돌아가 오류를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="77009-125">오류가 너무 많거나 사례나 문제의 새로운 관점이 있는 경우 관리자는 해당 기준을 다시 정의하고 해당 교육을 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="77009-126">**태그 지정 및 교육**:</span><span class="sxs-lookup"><span data-stu-id="77009-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="77009-127">파일에는 콘텐츠에만 태그를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="77009-128">양도자, 날짜 또는 파일 경로와 같은 메타데이터는 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="77009-129">파일에 태그를 지정하는 경우 텍스트에 날짜 범위 표시를 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="77009-130">파일에 태그를 지정하는 경우 포함된 그래픽 이미지를 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="77009-131">관련성에 적용된 텍스트는 관련성의 텍스트 보기에 표시되는 파일 콘텐츠에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="77009-132">무시 텍스트의 값이 이미 해당 학습을 시작한 후에 정의된 경우 무시된 새 텍스트는 정의한 지점에서 만든 예제 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="77009-133">텍스트 무시 기능을 사용할 경우 파일 분석 성능이 낮아지기에 신중하게 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="77009-134">필요한 경우 태그 **지정 건너뛰기** 옵션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="77009-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="77009-135">Advanced eDiscovery는 건너뛴 파일을 기반으로 교육하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="77009-136">평가에서 파일이 관련성이 있는지 여부를 밝히기 어려운 경우 가능하면 건너뛰기보다는 관련성(R) 또는 NR(관련이 없는)으로 태그를 지정하는 것이 **좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="77009-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="77009-137">Advanced eDiscovery에서 교육을 평가하면 이러한 유형의 파일이 얼마나 잘 처리된지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="77009-138">추출된 텍스트가 매우 적은 파일라도 가능한 경우 "건너뛰기"가 아니라 R/NR 교육에서 태그를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="77009-139">파일을 읽을 수 있으며 R/NR로 태그가 지정될 수 있는 한 태그 지정은 분류자에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="77009-140">태그 탭에 표시된 예제 파일 목록에  있는 파일 시퀀스 번호를 사용하면 파일의 원래 표시된 순서로 돌아올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="77009-141">샘플로 돌아가 평가 및 교육 집합 파일의 태그를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="77009-142">다음 샘플을 만들 때 변경 내용이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="77009-143">PDF 형식의 검색된 Excel 파일은 파일에 태그를 지정하는 경우 네이티브 Excel 파일과 동일하게 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="77009-144">파일의 관련성 태그 지정과 관련하여 의심스러우면 전문가에게 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="77009-145">또한 과정의 후반부에 시간이 손실될 수 있으며 전체 결과의 품질에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="77009-146">키워드 목록에 정의된 키워드는 사용자가 태그를 지정하는 동안 관련 파일을 식별할 수 있도록 색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="77009-147">**일괄** 계산: 전문가가 R/NR로 태그가 지정한 파일은 0 또는 100점의 점수를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="77009-148">이는 일괄 계산 전에 수행된 태그 지정에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="77009-149">전문가가 일괄 계산 후 이 문제를 유휴로 전환하고 이 문제를 계속 태그를 지정하면 새로 태그가 지정된 점수는 100/0이 아니라 원래 점수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="77009-150">**문제 및** 샘플링 모드: 문제는 일반적으로 해당 작업 완료(관련성 교육이 안정화되고 일괄 계산이 수행된 경우), 문제가 취소되거나 다른 사용자가 문제를 작업할 때 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="77009-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="77009-151">관련성 교육의 단계</span><span class="sxs-lookup"><span data-stu-id="77009-151">Steps in Relevance training</span></span>

<span data-ttu-id="77009-152">관련성 **\>** 추적 탭에서 Advanced eDiscovery는 다음 단계와 함께 처리를 진행하는 방법에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="77009-153">다음과 같은 각 단계가 의미 교육 프로세스에서 권장되는 경우의 의미에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="77009-154">태그 지정 / 계속 태그 지정: 샘플 내의 각 파일 및 문제와 전문가가 수행한 파일 검토 및 관계성 태그 지정</span><span class="sxs-lookup"><span data-stu-id="77009-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="77009-155">의미: 기존 샘플에 태그를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="77009-156">평가/ 평가 계속: 사례 문제의 유효성을 조기 검사하고 현재 사례에 대해 가져온 파일 인구의 예비 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="77009-157">의미: 추가 평가가 필요하거나 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="77009-158">교육/계속 교육: Advanced eDiscovery가 파일 샘플에 태그를 지정하는 전문가로부터 학습하고 각 사례의 컨텍스트 내에서 각 문제와 관련성 기준을 식별하는 기능을 획득하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="77009-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="77009-159">의미: 이 문제의 경우 추가 교육이 필요합니다. 다음 샘플을 만들어 태그를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="77009-160">일괄 계산: Advanced eDiscovery가 교육 단계에서 획득한 지식을 사용하여 전체 파일 수집에 적용하는 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="77009-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="77009-161">해당 파일 그룹의 모든 파일은 해당성에 대해 평가되어 해당 점수가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="77009-162">의미: 문제가 안정화되고 일괄 계산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="77009-163">Catch-up: 전문가가 롤링 로드 시나리오 중에 추가 파일 부하에서 선택한 파일 샘플을 검토하고 태그를 지정하는 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77009-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="77009-164">의미: 새 부하가 추가되고 작업을 계속하려면 추가가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="77009-165">태그 불일치: 프로세스는 Advanced eDiscovery 알고리즘을 통해 분석에 부정적인 영향을 줄 수 있는 파일 태그 지정 프로세스의 불일치가 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="77009-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="77009-166">의미: 다음 샘플에는 이전 샘플에서 태그가 지정된 파일이 포함되고 해당 태그를 다시 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="77009-167">업데이트 분류자: 사용자가 태그 지정 또는 시드 변경 내용을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="77009-168">의미: 태그 지정 및 시드 변경 내용을 다른 의미 샘플을 수동으로 실행할 필요 없이 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="77009-169">보류 중: The Relevance training process is completed.</span><span class="sxs-lookup"><span data-stu-id="77009-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="77009-170">의미: 현재 관련성 교육이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="77009-171">Advanced eDiscovery는 여러 단계에서 권장되는 다음 단계를 통해 프로세스를 안내하기는 하지만 탭과 페이지 간을 탐색하고 개별 사례, 문제 또는 문서 검토 프로세스와 관련이 있을 수 있는 상황을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="77009-172">Advanced eDiscovery 다음 단계 처리 선택을 수락하거나 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="77009-173">권장되는 다음 단계가 다른 단계를 수행하려면 대화  상자의 확장된 문제 표시에 나열된  다음 단계를 클릭하고 다음 단계 옆에 있는 수정 단추를 클릭한 다음 다른 다음 단계 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77009-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="77009-174">일부 옵션은 잠금 해제 후 프로세스의 그 시점에서 사용할 수 없는 상태로 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77009-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="77009-175">추가 정보</span><span class="sxs-lookup"><span data-stu-id="77009-175">More information</span></span>

[<span data-ttu-id="77009-176">이해와 무관성 평가</span><span class="sxs-lookup"><span data-stu-id="77009-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77009-177">태그 지정 및 평가</span><span class="sxs-lookup"><span data-stu-id="77009-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77009-178">태그 지정 및관련성 교육</span><span class="sxs-lookup"><span data-stu-id="77009-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77009-179">추적과정성 분석</span><span class="sxs-lookup"><span data-stu-id="77009-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77009-180">결과에 따라 결정</span><span class="sxs-lookup"><span data-stu-id="77009-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="77009-181">테스트와의관성 분석</span><span class="sxs-lookup"><span data-stu-id="77009-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="77009-182">검토 집합에서 데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="77009-182">Query the data in a review set</span></span>](review-set-search.md)
