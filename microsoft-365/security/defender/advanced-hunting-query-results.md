---
title: Microsoft 365 Defender의 고급 헌팅 쿼리 결과 사용
description: Microsoft 365 Defender에서 고급 헌팅을 통해 반환된 쿼리 결과를 가장 많이 사용합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, schema, kusto, 시각화, 차트, 필터, 드릴다운
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eccf93b019baa240a46260a28f3f0bc109345dd4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952599"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="b1975-104">고급 헌팅 쿼리 결과 사용</span><span class="sxs-lookup"><span data-stu-id="b1975-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b1975-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b1975-105">**Applies to:**</span></span>
- <span data-ttu-id="b1975-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1975-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b1975-107">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b1975-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b1975-108">고급 헌팅 [](advanced-hunting-overview.md) 쿼리를 구성하여 매우 정확한 정보를 반환할 수 있는 반면, 쿼리 결과를 사용하여 더 많은 정보를 얻고 특정 활동 및 지표를 조사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-108">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="b1975-109">쿼리 결과에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-109">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="b1975-110">결과를 표 또는 차트로 보기</span><span class="sxs-lookup"><span data-stu-id="b1975-110">View results as a table or chart</span></span>
- <span data-ttu-id="b1975-111">표 및 차트 내보내기</span><span class="sxs-lookup"><span data-stu-id="b1975-111">Export tables and charts</span></span>
- <span data-ttu-id="b1975-112">자세한 엔터티 정보로 드릴다운</span><span class="sxs-lookup"><span data-stu-id="b1975-112">Drill down to detailed entity information</span></span>
- <span data-ttu-id="b1975-113">결과에서 직접 쿼리 조정 또는 필터 적용</span><span class="sxs-lookup"><span data-stu-id="b1975-113">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="b1975-114">테이블 또는 차트로 쿼리 결과 보기</span><span class="sxs-lookup"><span data-stu-id="b1975-114">View query results as a table or chart</span></span>
<span data-ttu-id="b1975-115">기본적으로 고급 헌팅은 쿼리 결과를 테이블형 데이터로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-115">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="b1975-116">차트와 동일한 데이터를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-116">You can also display the same data as a chart.</span></span> <span data-ttu-id="b1975-117">고급 헌팅은 다음과 같은 보기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-117">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="b1975-118">보기 유형</span><span class="sxs-lookup"><span data-stu-id="b1975-118">View type</span></span> | <span data-ttu-id="b1975-119">설명</span><span class="sxs-lookup"><span data-stu-id="b1975-119">Description</span></span> |
| -- | -- |
| <span data-ttu-id="b1975-120">**표**</span><span class="sxs-lookup"><span data-stu-id="b1975-120">**Table**</span></span> | <span data-ttu-id="b1975-121">쿼리 결과를 테이블 형식 형식으로 표시</span><span class="sxs-lookup"><span data-stu-id="b1975-121">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="b1975-122">**열 차트**</span><span class="sxs-lookup"><span data-stu-id="b1975-122">**Column chart**</span></span> | <span data-ttu-id="b1975-123">x 축에 있는 일련의 고유한 항목을 높이가 다른 필드의 숫자 값을 나타내는 세로 막대로 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-123">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="b1975-124">**누적 세로형 차트**</span><span class="sxs-lookup"><span data-stu-id="b1975-124">**Stacked column chart**</span></span> | <span data-ttu-id="b1975-125">x 축에 있는 일련의 고유한 항목을 높이가 하나 이상의 다른 필드의 숫자 값을 나타내는 누적 세로 막대로 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-125">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="b1975-126">**파이 차트**</span><span class="sxs-lookup"><span data-stu-id="b1975-126">**Pie chart**</span></span> | <span data-ttu-id="b1975-127">고유한 항목을 나타내는 섹션 파이를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-127">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="b1975-128">각 파이의 크기는 다른 필드의 숫자 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-128">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="b1975-129">**도넛형 차트**</span><span class="sxs-lookup"><span data-stu-id="b1975-129">**Donut chart**</span></span> | <span data-ttu-id="b1975-130">고유한 항목을 나타내는 섹션 호를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-130">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="b1975-131">각 호의 길이는 다른 필드의 숫자 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-131">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="b1975-132">**꺾은선형 차트**</span><span class="sxs-lookup"><span data-stu-id="b1975-132">**Line chart**</span></span> | <span data-ttu-id="b1975-133">일련의 고유한 항목에 대한 숫자 값을 그리며 그루팅된 값을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-133">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="b1975-134">**분산형 차트**</span><span class="sxs-lookup"><span data-stu-id="b1975-134">**Scatter chart**</span></span> | <span data-ttu-id="b1975-135">일련의 고유 항목에 대한 숫자 값을 그리게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-135">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="b1975-136">**영역형 차트**</span><span class="sxs-lookup"><span data-stu-id="b1975-136">**Area chart**</span></span> | <span data-ttu-id="b1975-137">일련의 고유 항목에 대한 숫자 값을 그리고 그림을 그리게 하는 값 아래에 구역을 채우는 경우</span><span class="sxs-lookup"><span data-stu-id="b1975-137">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="b1975-138">유효 차트에 대한 쿼리 생성</span><span class="sxs-lookup"><span data-stu-id="b1975-138">Construct queries for effective charts</span></span>
<span data-ttu-id="b1975-139">차트를 렌더링할 때 고급 헌팅은 자동으로 관심 열과 집계할 숫자 값을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-139">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="b1975-140">의미 있는 차트를 얻기 위해 시각화하려는 특정 값을 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-140">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="b1975-141">다음은 몇 가지 예제 쿼리와 결과 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-141">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="b1975-142">심각도에 따라 알림</span><span class="sxs-lookup"><span data-stu-id="b1975-142">Alerts by severity</span></span>
<span data-ttu-id="b1975-143">연산자를 사용하여 차트에 사용할 값의 `summarize` 수를 구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-143">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="b1975-144">아래 쿼리는 연산자를 사용하여 심각도에 따라 경고 `summarize` 수를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-144">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="b1975-145">결과를 렌더링할 때 열 차트에는 각 심각도 값이 별도의 열로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-145">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="b1975-146">![열 차트로 표시되는 고급 헌팅 쿼리 결과의 이미지 열 차트로 표시되는 심각도에 따라 경고에 대한 쿼리 ](../../media/advanced-hunting-column-chart.jpg)
 *결과*</span><span class="sxs-lookup"><span data-stu-id="b1975-146">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="b1975-147">운영 체제의 경고 심각도</span><span class="sxs-lookup"><span data-stu-id="b1975-147">Alert severity by operating system</span></span>
<span data-ttu-id="b1975-148">연산자를 사용하여 여러 필드의 차트 값에 대한 `summarize` 결과를 준비할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-148">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="b1975-149">예를 들어 운영 체제(OS)에 경고 심각도가 분산되어 있는 방법을 이해해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-149">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="b1975-150">아래 쿼리는 연산자를 사용하여 테이블에서 OS 정보를 끌어와서 및 열의 값을 계산하는 `join` `DeviceInfo` 데 `summarize` `OSPlatform` `Severity` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-150">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="b1975-151">이러한 결과는 누적 세로형 차트를 사용하여 가장 잘 시각화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-151">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="b1975-152">![누적 차트로 표시되는 고급 헌팅 쿼리 결과의 이미지 ](../../media/advanced-hunting-stacked-chart.jpg)
 *누적 차트로 표시되는 OS의* 경고 및 심각도에 대한 쿼리 결과</span><span class="sxs-lookup"><span data-stu-id="b1975-152">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="b1975-153">상위 10개 보낸 사람 도메인의 피싱 전자 메일</span><span class="sxs-lookup"><span data-stu-id="b1975-153">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="b1975-154">유한하지 않은 값 목록을 다루는 경우 연산자를 사용하여 대부분의 인스턴스가 있는 값만 차트로 `Top` 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-154">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="b1975-155">예를 들어 피싱 전자 메일이 가장 많은 상위 10개 보낸 사람 도메인을 얻은 경우 아래 쿼리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-155">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="b1975-156">파이 차트 보기를 사용하여 최상위 도메인에 대한 배포를 효과적으로 보여 주면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-156">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="b1975-157">![상위 보낸 사람 도메인의 피싱 전자 메일 배포를 보여 주며, 파이 차트로 표시되는 고급 헌팅 쿼리 ](../../media/advanced-hunting-pie-chart.jpg)
 *결과의 이미지*</span><span class="sxs-lookup"><span data-stu-id="b1975-157">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="b1975-158">시간의에 대한 파일 활동</span><span class="sxs-lookup"><span data-stu-id="b1975-158">File activities over time</span></span>
<span data-ttu-id="b1975-159">함수와 함께 연산자를 사용하면 시간이 지날 때 특정 표시기가 `summarize` 관련된 이벤트를 확인할 수 `bin()` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-159">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="b1975-160">아래 쿼리는 해당 파일과 관련된 활동의 스파이크를 표시하기 위해 30분 간격으로 파일이 관련된 이벤트를 `invoice.doc` 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-160">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="b1975-161">아래 라인 차트는 관련 활동이 더 많은 기간을 명확하게 `invoice.doc` 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-161">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="b1975-162">![라인 차트로 표시되는 고급 헌팅 쿼리 결과의 이미지 시간의 지난 파일 관련 이벤트 수를 보여주는 라인 ](../../media/advanced-hunting-line-chart.jpg)
 *차트입니다.*</span><span class="sxs-lookup"><span data-stu-id="b1975-162">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="b1975-163">표 및 차트 내보내기</span><span class="sxs-lookup"><span data-stu-id="b1975-163">Export tables and charts</span></span>
<span data-ttu-id="b1975-164">쿼리를 실행한 후 내보내기 를 **선택하여** 결과를 로컬 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-164">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="b1975-165">선택한 보기에 따라 결과가 내보내는 방식이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-165">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="b1975-166">**테이블 보기** - 쿼리 결과가 Microsoft Excel 통합 문서로 테이블 형식 형태로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-166">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="b1975-167">**모든 차트** - 쿼리 결과가 렌더링된 차트의 JPEG 이미지로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-167">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="b1975-168">쿼리 결과에서 드릴다운</span><span class="sxs-lookup"><span data-stu-id="b1975-168">Drill down from query results</span></span>
<span data-ttu-id="b1975-169">쿼리 결과에서 레코드를 빠르게 검사하려면 해당 행을 선택하여 레코드 검사 **패널을 여는 방법을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-169">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="b1975-170">패널은 선택한 레코드에 따라 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-170">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="b1975-171">**자산** - 레코드에 있는 주요 자산(사서함, 장치 및 사용자)에 대한 요약된 보기, 위험 및 노출 수준과 같은 사용 가능한 정보로 향상</span><span class="sxs-lookup"><span data-stu-id="b1975-171">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="b1975-172">**프로세스 트리** - 프로세스 정보가 있는 레코드에 대해 생성되어 사용 가능한 상황 정보를 사용하여 강화됩니다. 일반적으로 더 많은 열을 반환하는 쿼리의 경우 프로세스 트리가 더 다양할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-172">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="b1975-173">**모든 세부 정보** - 레코드의 열에 있는 모든 값</span><span class="sxs-lookup"><span data-stu-id="b1975-173">**All details** — all the values from the columns in the record</span></span>  

![레코드를 검사하기 위한 패널이 있는 선택한 레코드의 이미지](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="b1975-175">컴퓨터, 파일, 사용자, IP 주소 또는 URL과 같은 쿼리 결과의 특정 엔터티에 대한 자세한 내용을 확인하려면 엔터티 식별자를 선택하여 해당 엔터티에 대한 자세한 프로필 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-175">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="b1975-176">결과에서 쿼리 조정</span><span class="sxs-lookup"><span data-stu-id="b1975-176">Tweak your queries from the results</span></span>
<span data-ttu-id="b1975-177">결과 집합의 값을 마우스 오른쪽 단추로 클릭하면 쿼리가 빠르게 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-177">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="b1975-178">옵션을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-178">You can use the options to:</span></span>

- <span data-ttu-id="b1975-179">선택한 값을 명시적으로 찾습니다 (`==`)</span><span class="sxs-lookup"><span data-stu-id="b1975-179">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="b1975-180">쿼리에서 선택한 값을 제외합니다 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="b1975-180">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="b1975-181">쿼리에 값을 추가하는 고급 연산자를 사용합니다 (예: `contains`, `starts with` 및 `ends with`)</span><span class="sxs-lookup"><span data-stu-id="b1975-181">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![고급 헌팅 결과 집합의 이미지](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="b1975-183">쿼리 결과 필터링</span><span class="sxs-lookup"><span data-stu-id="b1975-183">Filter the query results</span></span>
<span data-ttu-id="b1975-184">오른쪽에 표시되는 필터는 결과 집합에 대한 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-184">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="b1975-185">각 열에는 해당 열에 대해 발견된 고유 값과 인스턴스 수를 나열하는 자체적인 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-185">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="b1975-186">포함하거나 제외하려는 값에서 또는 단추를 선택한 다음 쿼리 실행 을 선택하여 쿼리를 `+` `-` **구체화합니다.**</span><span class="sxs-lookup"><span data-stu-id="b1975-186">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![고급 헌팅 필터 이미지](../../media/advanced-hunting-filter.png)

<span data-ttu-id="b1975-188">필터를 적용하여 쿼리를 수정한 다음 쿼리를 실행하면 그에 따라 결과가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-188">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

>[!NOTE]
><span data-ttu-id="b1975-189">이 문서의 일부 테이블은 끝점용 Microsoft Defender에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b1975-190">[Microsoft 365 Defender를 켜서](m365d-enable.md) 더 많은 데이터 원본을 사용하여 위협을 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="b1975-191">Endpoint용 Microsoft Defender에서 Microsoft Defender의 고급 헌팅 쿼리 마이그레이션의 단계에 따라 끝점용 [Microsoft Defender에서 Microsoft](advanced-hunting-migrate-from-mde.md)365 Defender로 고급 헌팅 워크플로를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1975-192">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b1975-192">Related topics</span></span>
- [<span data-ttu-id="b1975-193">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="b1975-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b1975-194">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="b1975-194">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b1975-195">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="b1975-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b1975-196">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b1975-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b1975-197">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="b1975-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b1975-198">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="b1975-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b1975-199">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="b1975-199">Custom detections overview</span></span>](custom-detections-overview.md)
