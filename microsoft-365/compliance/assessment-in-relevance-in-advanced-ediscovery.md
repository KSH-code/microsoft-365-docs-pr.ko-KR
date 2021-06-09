---
title: 2016년 8월 1일부로의 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 평가 단계 및 해당 역할에 대한 개요를 확인하여 2016년 8월 관련성 교육 중에 문제가 Microsoft 365 Advanced eDiscovery.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769279"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="62ca3-103">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="62ca3-103">Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="62ca3-104">Advanced eDiscovery 정의된 문제 및 사례에 대해 가져온 데이터에 대해 초기 평가를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-104">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="62ca3-105">Advanced eDiscovery 채택된 접근 방식을 결정하고 이러한 결정을 문서 검토 프로젝트에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-105">Advanced eDiscovery lets the expert make decisions about an adopted approach and to apply these decisions to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="62ca3-106">평가 이해</span><span class="sxs-lookup"><span data-stu-id="62ca3-106">Understanding assessment</span></span>

<span data-ttu-id="62ca3-107">평가에서 전문가는 500개 이상의 파일을 임의로 검토하며, 이 집합을 사용하여 문제의 양을 파악하고 교육 결과를 반영하는 통계를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-107">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="62ca3-108">정확한 통계를 제공하고 교육 프로세스의 안정화 지점을 효과적으로 결정하기 위해 관련성이 Advanced eDiscovery 통계 수준에 도달할 수 있을 만큼 관련 파일이 발견되면 평가가 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-108">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="62ca3-109">평가 집합의 관련 파일 수가 높을수록 안정성 알고리즘의 통계와 효율성이 더 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-109">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="62ca3-110">평가 파일 내의 관련 파일 수는 문제의 풍부도에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-110">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="62ca3-111">풍부한성은 문제와 관련된 집합의 예상 관련 파일 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-111">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="62ca3-112">부자연스러움이 높은 문제는 더 낮은 풍부한 문제보다 관련 파일의 수가 더 빨라진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-112">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="62ca3-113">매우 낮은 풍부한 문제(예: 2% 이하)에는 매우 많은 관련 파일에 도달하기 위해 매우 큰 평가 집합이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-113">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="62ca3-114">교육 중 및 일괄 계산 후 추적 및 결정 탭에 있는 통계에는 다양한 검토 집합에 대한 회수 예상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-114">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="62ca3-115">통계에서 샘플 집합(이 경우 평가 파일)을 기반으로 하는 예측에는 오차의 여백과 해당 오류 여백의 신뢰 수준이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-115">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="62ca3-116">예를 들어 예상 회수율이 80%이면 신뢰 수준이 95%인 오차에 더하기 또는 5%를 냈을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-116">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="62ca3-117">즉, 예상 회수율은 실제로 75%-85%이고 이 예상은 95% 신뢰를 가졌다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-117">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="62ca3-118">평가 집합이 클수록 오류의 여백이 더 작아지고 통계가 더 정확해집니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-118">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="62ca3-119">전문가가 초기 평가 집합인 500개 파일을 검토한 후, 해당 관계에 따라 회수 값의 현재 오차를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-119">After the expert reviews an initial assessment set of 500 files, Relevance can determine the current margin of error of the recall values.</span></span> <span data-ttu-id="62ca3-120">또한 평가 집합을 최적화하기 위해 기본 오차 여백에 도달하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-120">Relevance will also recommend a default margin of error to reach to optimize the assessment set.</span></span> <span data-ttu-id="62ca3-121">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-121">Here are some examples:</span></span>
  
- <span data-ttu-id="62ca3-122">평가 집합에서 이미 10%를 더하기 또는 10%를 득하는 오차의 여백을 산출한 경우, 교육으로 이동하는 것이 좋습니다(추가 평가 검토가 필요하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="62ca3-122">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend moving on to training (no additional assessment review is needed).</span></span> 

- <span data-ttu-id="62ca3-123">평가 집합에서 더하기 또는 13%를 밝게 하는 오차의 여백을 산출한 경우 다른 평가 파일 집합을 검토하여 더 작은 여백에 도달하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-123">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 

- <span data-ttu-id="62ca3-124">유용성 수준이 매우 낮은 경우 오류의 여백이 너무 크면(통계를 통계를 유용하지 못하게 만들기) 관련성으로 평가를 중지하는 것이 좋습니다. 이는 유용한 오차의 여백에 도달하는 데 필요한 평가 집합이 너무 크기 때문에 관련성에 따라 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-124">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>

<span data-ttu-id="62ca3-125">각 문제마다 자체의 풍부한 오류 및 현재 오류 여백이 있으며 그 결과로 예상되는 추가 평가 파일 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-125">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="62ca3-126">다음 평가 집합은 최대 파일 수(단일 집합에서 최대 1,000개)에 따라 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-126">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="62ca3-127">관련성 권장 사항을 수락하거나 요구 사항에 따라 현재 오류 여백을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-127">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="62ca3-128">기본 현재 오류 여백은 75% 이상인 회수율로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-128">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62ca3-129">문제당 평가 확인란의 선택을 취소한 다음 "모든 문제"에 대해 평가 단계는  문제에 대한 확장된 보기의 관련성 트랙 탭에서 우회할 수 있습니다. **\>**</span><span class="sxs-lookup"><span data-stu-id="62ca3-129">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="62ca3-130">따라서 이 문제의 통계는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-130">As a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="62ca3-131">평가 **확인란의** 선택을 취소하는 것은 평가가 수행되기 전에만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-131">Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="62ca3-132">여러 문제가 있는 경우 각 문제에 대한 확인란이 선택 취소된 경우 평가는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62ca3-132">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue.</span></span>
