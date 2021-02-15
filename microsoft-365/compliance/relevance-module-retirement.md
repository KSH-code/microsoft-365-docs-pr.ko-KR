---
title: Advanced eDiscovery에서와관성 모듈 사용 중지
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Advanced eDiscovery의 연결 모듈은 2021년 3월 10일에 사용 중지됩니다. 이 문서에서는 관련성 사용이 중지되기 전에 할 일에 대해 설명합니다. 특히 모델의 메타데이터를 유지할 수 있도록 일괄 계산을 실행하여 미완료 모델을 완료합니다.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122537"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="2951d-105">Advanced eDiscovery에서 Relevance 모듈 사용 중지</span><span class="sxs-lookup"><span data-stu-id="2951d-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="2951d-106">2021년 3월 10일, Advanced eDiscovery에서 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="2951d-107">이 사용 중지는 조직이 더 이상 관련성 모듈에 액세스할 수 없음(Advanced  >   eDiscovery 사례에서 검토 집합 관련성 관리로) 또는 기존 관련성 모델에 액세스할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="2951d-108">사용 중지되는 현재의 연결 모듈은 2021년 2분기 CY 2021의 새로운 예측 코딩 솔루션으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="2951d-109">이 새로운 기능을 통해 조직은 보다 쉽고 직관적인 워크플로에서 자체 예측 코딩 모델을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="2951d-110">예정된 사용 중지를 준비하기 위해 관련성 모듈을 사용하는 조직은 모든 기존 모델에 대해 일괄 계산을 실행하여 사용 중지 날짜 전에 모델의 출력을 내보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="2951d-111">모델의 모든 관련성 점수는 해당 검토 집합에 영구적으로 저장되고 문서를 내보낼 때 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="2951d-112">또한 해당 점수는 로드 파일에 메타데이터로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="2951d-113">또한 관련성 점수에 따라 검토 집합의 콘텐츠를 필터링할 수 있으며 관련성 모델에 의해 생성되는 모든 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="2951d-114">완료되지 않은 모델 완료</span><span class="sxs-lookup"><span data-stu-id="2951d-114">Complete unfinished models</span></span>

<span data-ttu-id="2951d-115">미완료 관련성 모델의 경우 검토 집합의 문서에 모델을 적용할 수 있도록 평가, 교육 및 일괄 계산을 완료하십시오.</span><span class="sxs-lookup"><span data-stu-id="2951d-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="2951d-116">일괄 계산을 완료하면 관련성 모듈의 사용 중지 날짜 이후에 정보가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="2951d-117">미완성 모델을 완료하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="2951d-118">모델이 안정화되고 일괄 계산 준비가 될 때까지 모델을 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="2951d-119">태그 [지정 및관련성 교육을 참조합니다.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="2951d-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="2951d-120">다음 스크린샷은 일괄 계산에 사용할 수 있는 모듈을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="2951d-121">평가 및 교육이 완료된 후 다음 단계는 일괄 계산을 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![일괄 계산 준비가 완료된 모델의 스크린샷](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="2951d-123">일괄 처리 계산을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-123">Run the Batch calculation.</span></span> <span data-ttu-id="2951d-124">일괄 [처리 계산 수행을 참조합니다.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="2951d-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="2951d-125">일괄 계산이 성공적이지 확인</span><span class="sxs-lookup"><span data-stu-id="2951d-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="2951d-126">일괄 [계산 결과를 참조합니다.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)</span><span class="sxs-lookup"><span data-stu-id="2951d-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="2951d-127">미완료한 해당 모델 완료에 대한 도움말을 원할 경우 Microsoft 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="2951d-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
