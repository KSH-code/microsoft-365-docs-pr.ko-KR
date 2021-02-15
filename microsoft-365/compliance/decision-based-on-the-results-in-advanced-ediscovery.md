---
title: Advanced eDiscovery의 결과에 따라 결정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Advanced eDiscovery의 결정 탭에서 사례 파일 검토 집합의 올바른 크기를 결정하는 데 도움이 되는 데이터를 제공하는 방법을 확인합니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769153"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="3bab9-103">Advanced eDiscovery의 결과와의관성에 따라 결정</span><span class="sxs-lookup"><span data-stu-id="3bab9-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="3bab9-104">Advanced eDiscovery의 관련성 모듈에서 결정 탭은 사례 파일 검토 집합의 크기를 결정하는 데 결정 지원 통계를 보고 사용할 수 있는 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="3bab9-105">결정 탭 사용</span><span class="sxs-lookup"><span data-stu-id="3bab9-105">Using the Decide tab</span></span>

![관련성을 결정](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="3bab9-107">이 탭에는 다음과 같은 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="3bab9-108">**문제**: 여기에서 목록에서 관심 문제를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="3bab9-109">**검토 회수율:** 관련성 점수에 따라 Advanced eDiscovery 검토를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="3bab9-110">차트의 컷오프 지점은 검토할 파일의 백분율을 나타내며, 해당 점수에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="3bab9-111">이 단계는 관련성 테스트 단계에서 컬링에 대한 내보내기 임계값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="3bab9-112">검토할 파일 수에 대한 기본 컷오프 지점은 회수 및 정밀도 사이의 균형이 최적 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="3bab9-113">실제 컷오프 지점은 목표와 비용 절차(%review) 및 위험(%회수율)에 따라 사용자가 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="3bab9-114">슬라이더를 사용하여 컷오프 지점을 조정하고, 검색할 관련 파일의 백분율을 조정할 때, 결정의 유효성을 검사하기 전에 그래프 및 매개 변수에 대한 영향을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="3bab9-115">**매개** 변수: 검토, 회수, 다음 관련 비용 및 총 비용 매개 변수는 전체 사례에 대한 컬렉션과 관련된 검토 집합과 관련된 누적 계산 통계입니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="3bab9-116">이러한 매개 변수에 대한 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="3bab9-117">**검토:** 이 컷오프에 따라 검토할 파일의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="3bab9-118">**회수:** 검토 집합에 있는 관련 파일의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="3bab9-119">**다음 관련성:** 현재 검토 집합에 없는 다른 관련 파일을 검토하고 식별하는 데 드는 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="3bab9-120">**총 비용:** 사례 파일의 이 백분율을 검토하는 데 드는 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="3bab9-121">비용 매개 변수 설정은 사례 관리자가 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="3bab9-122">**타당성** 점수로 분포: 왼쪽에 진한 회색 표시의 파일이 잘리기 점수 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="3bab9-123">도구 팁에는 전체 파일과 관련된 리뷰 파일 집합의 관련성 점수 및 관련 백분율이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="3bab9-124">확장된 **세부 정보 창에** 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="3bab9-125">컬렉션 그림의 파일에는 비어 있거나 까다로워진 파일이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="3bab9-126">패밀리 파일 그림은 해당 패밀리의 일부로 계산되는, 아직까지는 해당 파일에 대한 무관성으로 로드되지 않은 파일을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bab9-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
