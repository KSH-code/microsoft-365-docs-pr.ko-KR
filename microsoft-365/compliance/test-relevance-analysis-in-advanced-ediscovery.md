---
title: Advanced eDiscovery의 테스트관행성 분석
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Advanced eDiscovery에서 일괄 계산 후 테스트 탭을 사용하여 전체 처리 품질을 테스트, 비교 및 유효성을 검사하는 방법을 학습합니다.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769173"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="34e1c-103">Advanced eDiscovery의 테스트관행성 분석</span><span class="sxs-lookup"><span data-stu-id="34e1c-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="34e1c-104">Advanced eDiscovery의 테스트 탭을 사용하면 전체 처리 품질을 테스트, 비교 및 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="34e1c-105">이러한 테스트는 일괄 계산 후 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="34e1c-106">전문가는 컬렉션의 파일에 태그를 지정하여 태그가 지정한 각 파일이 사례와 관련이 있는지 여부를 최종적으로 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="34e1c-107">단일 및 다중 문제 시나리오에서는 일반적으로 문제당 테스트가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="34e1c-108">각 테스트 후에 결과를 볼 수 있으며 지정된 샘플 테스트 파일을 사용하여 테스트 결과를 다시 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="34e1c-109">나머지 테스트</span><span class="sxs-lookup"><span data-stu-id="34e1c-109">Testing the rest</span></span>

<span data-ttu-id="34e1c-110">"나머지 테스트" 테스트는 선별 결정의 유효성을 검사하는 데 사용됩니다. 예를 들어 최종 Advanced eDiscovery 결과에 따라 특정 관련성 컷오프 점수 이상의 파일만 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="34e1c-111">전문가는 선택한 컷오프 점수의 파일 샘플을 검토하여 해당 집합 내의 관련 파일 수를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="34e1c-112">이 테스트에서는 검토 집합과 Rest 테스트 인구 간의 통계 및 비교를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="34e1c-113">검토 집합의 결과는 교육 중의 해당성으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="34e1c-114">결과에는 다음과 같은 설정 및 입력 매개 변수에 기반한 계산이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="34e1c-115">샘플의 파일 수와 식별된 관련 파일의 샘플 통계를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="34e1c-116">검토 집합 및 Rest의 Population 매개 변수(예: 파일 수, 예상 관련 파일 수, 예상 풍부한 정보 및 다른 관련 파일을 찾는 평균 비용)의 테이블 형식 비교</span><span class="sxs-lookup"><span data-stu-id="34e1c-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="34e1c-117">비용 매개 변수 설정은 관리자가 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="34e1c-118">"나머지 테스트" 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="34e1c-119">**타당성 테스트 탭을 \> 열** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="34e1c-120">테스트 **탭에서** 새 **테스트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="34e1c-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="34e1c-121">다음 **예제와** 같이 테스트 만들기 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![나머지 결과 테스트 하는 관련성](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="34e1c-123">테스트 **이름 및** **설명에** 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="34e1c-124">테스트 **유형 목록에서** **나머지** 테스트 선택</span><span class="sxs-lookup"><span data-stu-id="34e1c-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="34e1c-125">**문제/범주 목록에서** 문제 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="34e1c-126">로드 **목록에서** 로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="34e1c-127">읽기 **%에서** 기본값을 수락하거나 잘라 내는관성 점수의 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="34e1c-128">Set **크기로** 설정하거나 기본값을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="34e1c-129">복원 아이콘은 기본값을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="34e1c-130">태그 **지정 시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="34e1c-130">Click **Start tagging**.</span></span> <span data-ttu-id="34e1c-131">테스트 샘플이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-131">A test sample is generated.</span></span>

10. <span data-ttu-id="34e1c-132">**Relevance \> Tag** 탭에서 각 파일을 검토하고 태그를 지정하고 완료하면 계산을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="34e1c-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="34e1c-133">테스트 탭에서 결과 보기를 클릭하여 테스트 결과를 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="34e1c-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="34e1c-134">다음 스크린샷에는 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-134">An example is shown in the following screenshot.</span></span>

    ![나머지 결과 테스트 합니다.](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="34e1c-136">이전 스크린샷에서 표의 **샘플** 매개 변수 섹션에는 전문가가 태그를 지정한 샘플의 파일 수와 해당 샘플에서 찾은 관련 파일 수에 대한 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="34e1c-137">표의 **Population 매개** 변수 섹션에는 선택한 컷오프보다 점수가 높은 파일의 검토 집합 인구와 선택한 컷오프 이상의 점수가 있는 "나머지" 파일 인구를 포함하는 테스트 결과가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="34e1c-138">각 인구에 대해 다음과 같은 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="34e1c-139">읽기 % - 상태 컷오프가 포함된 파일 포함</span><span class="sxs-lookup"><span data-stu-id="34e1c-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="34e1c-140">총 파일 수</span><span class="sxs-lookup"><span data-stu-id="34e1c-140">The total number of files</span></span>

- <span data-ttu-id="34e1c-141">예상 관련 파일 수</span><span class="sxs-lookup"><span data-stu-id="34e1c-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="34e1c-142">예상 풍부한</span><span class="sxs-lookup"><span data-stu-id="34e1c-142">The estimated richness</span></span>

- <span data-ttu-id="34e1c-143">다른 관련 파일을 찾는 데 드는 평균 검토 비용</span><span class="sxs-lookup"><span data-stu-id="34e1c-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="34e1c-144">조각 테스트</span><span class="sxs-lookup"><span data-stu-id="34e1c-144">Testing the slice</span></span>

<span data-ttu-id="34e1c-145">"슬라이스 테스트" 테스트는 "나머지 테스트" 테스트와 유사하게 테스트를 수행하지만, 파일 집합의 세그먼트는 읽기 전용으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="34e1c-146">"조각 테스트" 테스트를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="34e1c-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="34e1c-147">**타당성 테스트 탭을 \> 열** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="34e1c-148">테스트 **탭에서** 새 **테스트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="34e1c-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="34e1c-149">테스트 **만들기 대화** 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="34e1c-150">테스트 **이름 및** **설명에** 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="34e1c-151">테스트 **유형 목록에서** 조각 **테스트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="34e1c-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="34e1c-152">문제 **목록에서** 문제 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="34e1c-153">로드 **목록에서** 로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="34e1c-154">읽기 **사이의 읽기 %에서** 기본 낮음 및 높은 범위 값을 수락하거나 컷오프된 관계 점수에 대한 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="34e1c-155">설정 **크기에서** 값을 선택하거나 기본값을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="34e1c-156">복원 아이콘은 기본값을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="34e1c-157">태그 **지정 시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="34e1c-157">Click **Start tagging**.</span></span> <span data-ttu-id="34e1c-158">테스트 샘플이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="34e1c-158">A test sample is generated.</span></span>

10. <span data-ttu-id="34e1c-159">**Relevance \> Tag** 탭에서 각 파일을 검토하고 태그를 지정하고 완료하면 계산을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="34e1c-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="34e1c-160">테스트 탭에서 결과 보기를 클릭하여 테스트 결과를 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="34e1c-160">In the Test tab, you can click **View results** to see the test results.</span></span>
