---
title: Microsoft Threat Protection의 고급 구하기 쿼리 결과 작업
description: Microsoft Threat Protection에서 상세하게 검색에 의해 반환 되는 쿼리 결과의 대부분 만들기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, 스키마, kusto, microsoft 365, microsoft Threat Protection, 시각화, 차트, 필터 드릴 다운
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929245"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="420f3-104">고급 구하기 쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="420f3-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="420f3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="420f3-105">**Applies to:**</span></span>
- <span data-ttu-id="420f3-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="420f3-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="420f3-107">[고급 구하기](advanced-hunting-overview.md) 쿼리를 작성 하 여 매우 정확한 정보를 반환할 수 있지만 쿼리 결과를 사용 하 여 구체적인 작업과 지표를 보다 명확 하 게 파악 하 고 조사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="420f3-108">쿼리 결과에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="420f3-109">결과를 테이블 또는 차트로 보기</span><span class="sxs-lookup"><span data-stu-id="420f3-109">View results as a table or chart</span></span>
- <span data-ttu-id="420f3-110">표 및 차트 내보내기</span><span class="sxs-lookup"><span data-stu-id="420f3-110">Export tables and charts</span></span>
- <span data-ttu-id="420f3-111">자세한 엔터티 정보 드릴 다운</span><span class="sxs-lookup"><span data-stu-id="420f3-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="420f3-112">쿼리를 결과에서 직접 조정 하거나 필터를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="420f3-113">쿼리 결과를 테이블 또는 차트로 보기</span><span class="sxs-lookup"><span data-stu-id="420f3-113">View query results as a table or chart</span></span>
<span data-ttu-id="420f3-114">기본적으로 고급 구하기에서는 쿼리 결과를 테이블 형식 데이터로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="420f3-115">차트와 같은 데이터를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="420f3-116">고급 구하기에서는 다음 보기를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="420f3-117">보기 유형</span><span class="sxs-lookup"><span data-stu-id="420f3-117">View type</span></span> | <span data-ttu-id="420f3-118">설명</span><span class="sxs-lookup"><span data-stu-id="420f3-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="420f3-119">**목차가**</span><span class="sxs-lookup"><span data-stu-id="420f3-119">**Table**</span></span> | <span data-ttu-id="420f3-120">쿼리 결과를 테이블 형식으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="420f3-121">**세로 막대형 차트**</span><span class="sxs-lookup"><span data-stu-id="420f3-121">**Column chart**</span></span> | <span data-ttu-id="420f3-122">X 축에서 일련의 고유 항목을 해당 높이가 다른 필드의 숫자 값을 나타내는 세로 막대로 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="420f3-123">**누적 세로 막대형 차트**</span><span class="sxs-lookup"><span data-stu-id="420f3-123">**Stacked column chart**</span></span> | <span data-ttu-id="420f3-124">X 축에 있는 일련의 고유한 항목을 해당 높이가 하나 이상의 다른 필드에 있는 숫자 값을 나타내는 누적 세로 막대로 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="420f3-125">**원형 차트**</span><span class="sxs-lookup"><span data-stu-id="420f3-125">**Pie chart**</span></span> | <span data-ttu-id="420f3-126">고유 항목을 나타내는 단면 원형을 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="420f3-127">각 원형의 크기는 다른 필드의 숫자 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="420f3-128">**도넛형 차트**</span><span class="sxs-lookup"><span data-stu-id="420f3-128">**Donut chart**</span></span> | <span data-ttu-id="420f3-129">고유 항목을 나타내는 단면 원호를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="420f3-130">각 호의 길이는 다른 필드의 숫자 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="420f3-131">**꺾은선형 차트**</span><span class="sxs-lookup"><span data-stu-id="420f3-131">**Line chart**</span></span> | <span data-ttu-id="420f3-132">일련의 고유한 항목에 숫자 값을 그리고 플롯 된 값을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="420f3-133">**분산형 차트**</span><span class="sxs-lookup"><span data-stu-id="420f3-133">**Scatter chart**</span></span> | <span data-ttu-id="420f3-134">일련의 고유한 항목에 숫자 값 그리기</span><span class="sxs-lookup"><span data-stu-id="420f3-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="420f3-135">**영역형 차트**</span><span class="sxs-lookup"><span data-stu-id="420f3-135">**Area chart**</span></span> | <span data-ttu-id="420f3-136">일련의 고유한 항목에 숫자 값을 그리고 플롯 된 값 아래에 섹션을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="420f3-137">효율적인 차트 작성 쿼리</span><span class="sxs-lookup"><span data-stu-id="420f3-137">Construct queries for effective charts</span></span>
<span data-ttu-id="420f3-138">차트를 렌더링 하는 경우 고급 구하기에서는 관심 있는 열과 집계할 숫자 값을 자동으로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="420f3-139">의미 있는 차트를 가져오려면 시각화 하려는 특정 값을 반환 하는 쿼리를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="420f3-140">아래에는 몇 가지 예제 쿼리와 결과 차트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="420f3-141">심각도 별 경고</span><span class="sxs-lookup"><span data-stu-id="420f3-141">Alerts by severity</span></span>
<span data-ttu-id="420f3-142">`summarize` 연산자를 사용 하 여 차트로 표시할 값의 숫자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="420f3-143">아래 쿼리는 `summarize` 연산자를 사용 하 여 심각도 별 경고 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="420f3-144">결과를 렌더링 하는 경우 세로 막대형 차트에서 각 심각도 값은 개별 열로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="420f3-145">![열 차트로 표시 되는](../../media/advanced-hunting-column-chart.jpg)
*심각도에 따라 열 차트 쿼리 결과로* 표시 되는 고급 구하기 쿼리 결과 이미지</span><span class="sxs-lookup"><span data-stu-id="420f3-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="420f3-146">운영 체제별 경고 심각도</span><span class="sxs-lookup"><span data-stu-id="420f3-146">Alert severity by operating system</span></span>
<span data-ttu-id="420f3-147">또한 `summarize` 연산자를 사용 하 여 여러 필드의 차트 값에 대 한 결과를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="420f3-148">예를 들어 여러 운영 체제 (OS)에서 경고 심각도가 분산 되는 방식을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="420f3-149">아래 쿼리는 `join` 연산자를 사용 하 여 `DeviceInfo` 테이블에서 OS 정보를 가져온 후 `summarize` `OSPlatform` 와 `Severity` 열에서 모두 값을 계산 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="420f3-150">이러한 결과는 누적 세로 막대형 차트를 사용 하 여 시각화 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="420f3-151">![OS에의 한 경고에 대 한 누적 된 차트](../../media/advanced-hunting-stacked-chart.jpg)
쿼리 결과로 표시 되는 고급 구하기 쿼리 결과 이미지*및 누적 차트로 표시 되는 심각도*</span><span class="sxs-lookup"><span data-stu-id="420f3-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="420f3-152">상위 10 개의 보낸 사람 도메인에 걸친 피싱 전자 메일</span><span class="sxs-lookup"><span data-stu-id="420f3-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="420f3-153">유한 하지 않은 값의 목록을 처리 하는 경우 `Top` 연산자를 사용 하 여 대부분의 인스턴스가 있는 값만 차트로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="420f3-154">예를 들어 가장 많이 피싱 전자 메일을 사용 하 여 상위 10 개의 보낸 사람 도메인을 가져오려면 아래 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="420f3-155">원형 차트 보기를 사용 하 여 상위 도메인 전체에 분포를 효과적으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="420f3-156">![](../../media/advanced-hunting-pie-chart.jpg)
*상위 보낸 사람 도메인에 걸친 피싱 전자 메일의 분포를 보여 주는 원형 차트 원형 차트로* 표시 되는 고급 구하기 쿼리 결과 이미지</span><span class="sxs-lookup"><span data-stu-id="420f3-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="420f3-157">시간에 따른 파일 활동</span><span class="sxs-lookup"><span data-stu-id="420f3-157">File activities over time</span></span>
<span data-ttu-id="420f3-158">`bin()` 함수에 `summarize` 연산자를 사용 하 여 시간에 따른 특정 지표와 관련 된 이벤트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="420f3-159">아래 쿼리는 파일 `invoice.doc` 을 30 분 간격으로 포함 하는 이벤트 수를 계산 하 여 해당 파일과 관련 된 작업의 스파이크를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="420f3-160">아래의 꺽은선형 차트는 `invoice.doc`다음과 같은 작업을 포함 하는 시간 기간을 명확 하 게 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="420f3-161">![](../../media/advanced-hunting-line-chart.jpg)
*시간에 따른 파일 관련 이벤트 수를 보여주는* 꺾은선형 차트 차트로 표시 되는 고급 구하기 쿼리 결과 이미지</span><span class="sxs-lookup"><span data-stu-id="420f3-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="420f3-162">표 및 차트 내보내기</span><span class="sxs-lookup"><span data-stu-id="420f3-162">Export tables and charts</span></span>
<span data-ttu-id="420f3-163">쿼리를 실행 한 후에는 **내보내기를** 선택 하 여 결과를 로컬 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="420f3-164">선택한 보기에 따라 결과를 내보낼 방법이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="420f3-165">**표 보기** — 쿼리 결과를 Microsoft Excel 통합 문서로 테이블 형식으로 내보내기</span><span class="sxs-lookup"><span data-stu-id="420f3-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="420f3-166">**모든 차트** -쿼리 결과가 렌더링 된 차트의 JPEG 이미지로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="420f3-167">쿼리 결과에서 드릴 다운</span><span class="sxs-lookup"><span data-stu-id="420f3-167">Drill down from query results</span></span>
<span data-ttu-id="420f3-168">쿼리 결과에서 컴퓨터, 파일, 사용자, IP 주소 및 URL과 같은 엔터티에 대한 자세한 정보를 보려면 엔터티 식별자를 클릭하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-168">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="420f3-169">그러면 Microsoft Defender 보안 센터에서 선택한 엔터티에 대한 자세한 프로필 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-169">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="420f3-170">결과에서 쿼리 조정</span><span class="sxs-lookup"><span data-stu-id="420f3-170">Tweak your queries from the results</span></span>
<span data-ttu-id="420f3-171">결과 집합의 값을 마우스 오른쪽 단추로 클릭하면 쿼리가 빠르게 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-171">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="420f3-172">옵션을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-172">You can use the options to:</span></span>

- <span data-ttu-id="420f3-173">선택한 값을 명시적으로 찾습니다 (`==`)</span><span class="sxs-lookup"><span data-stu-id="420f3-173">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="420f3-174">쿼리에서 선택한 값을 제외합니다 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="420f3-174">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="420f3-175">쿼리에 값을 추가하는 고급 연산자를 사용합니다 (예: `contains`, `starts with` 및 `ends with`)</span><span class="sxs-lookup"><span data-stu-id="420f3-175">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![고급 구하기 결과 집합 이미지](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="420f3-177">쿼리 결과 필터링</span><span class="sxs-lookup"><span data-stu-id="420f3-177">Filter the query results</span></span>
<span data-ttu-id="420f3-178">오른쪽에 표시되는 필터는 결과 집합에 대한 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-178">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="420f3-179">각 열에는 해당 열에 대해 발견된 고유 값과 인스턴스 수를 나열하는 자체적인 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-179">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="420f3-180">포함 하거나 제외할 값의 또는 `+` `-` 단추를 선택 하 고 **쿼리 실행**을 선택 하 여 쿼리를 구체화 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-180">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![고급 헌팅 필터 이미지](../../media/advanced-hunting-filter.png)

<span data-ttu-id="420f3-182">필터를 적용하여 쿼리를 수정한 다음 쿼리를 실행하면 그에 따라 결과가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="420f3-182">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="420f3-183">관련 항목</span><span class="sxs-lookup"><span data-stu-id="420f3-183">Related topics</span></span>
- [<span data-ttu-id="420f3-184">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="420f3-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="420f3-185">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="420f3-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="420f3-186">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="420f3-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="420f3-187">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="420f3-187">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="420f3-188">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="420f3-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="420f3-189">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="420f3-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="420f3-190">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="420f3-190">Custom detections overview</span></span>](custom-detections-overview.md)
