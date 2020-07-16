---
title: Microsoft Threat Protection에서 고급 헌팅 쿼리 언어 알아보기
description: 첫 번째 위협 헌팅 쿼리를 만들고 고급 헌팅 쿼리 언어의 일반적인 연산자와 기타 요소에 대한 정보를 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 threat 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 언어, 학습, 첫 번째 쿼리, 원격 분석, 이벤트, 원격, 사용자 지정 감지, 스키마, kusto, operators, 데이터 형식, powershell 다운로드, 쿼리 예제
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
ms.openlocfilehash: 26b376fe3e804a3ebaa478e484807bea4c33d38b
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049701"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="c3685-104">고급 헌팅 쿼리 언어 알아보기</span><span class="sxs-lookup"><span data-stu-id="c3685-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="c3685-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c3685-105">**Applies to:**</span></span>
- <span data-ttu-id="c3685-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c3685-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c3685-107">고급 헌팅은 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="c3685-108">Kusto 구문 및 연산자를 사용하여 고급 헌팅을 위해 특별히 구성된 [스키마](advanced-hunting-schema-tables.md)에서 정보를 찾는 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="c3685-109">이러한 개념을 보다 잘 이해하려면 첫 번째 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="c3685-110">첫 번째 쿼리 시도하기</span><span class="sxs-lookup"><span data-stu-id="c3685-110">Try your first query</span></span>

<span data-ttu-id="c3685-111">Microsoft 365 보안 센터에서 **검색으로 이동 하 여** 첫 번째 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="c3685-112">다음 예제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="c3685-113">이는 고급 헌팅에서 표시되는 모습입니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft Threat Protection 고급 구하기 쿼리 이미지](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="c3685-115">쿼리 설명 및 검색할 테이블 지정</span><span class="sxs-lookup"><span data-stu-id="c3685-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="c3685-116">쿼리의 시작 부분에 요약 설명이 추가 되어 해당 내용을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="c3685-117">이렇게 하면 나중에 쿼리를 저장 하 고 조직의 다른 사용자와 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="c3685-118">일반적으로 쿼리 자체는 표 이름으로 시작하고 다음으로 파이프(`|`)로 시작되는 일련의 요소가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="c3685-119">이 예제에서는 먼저 두 개의 테이블을 통합 하 고 `DeviceProcessEvents` `DeviceNetworkEvents` 필요에 따라 파이프 된 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="c3685-120">시간 범위 설정</span><span class="sxs-lookup"><span data-stu-id="c3685-120">Set the time range</span></span>
<span data-ttu-id="c3685-121">첫 번째 파이프 요소는 이전 7 일간 범위가 지정 된 시간 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="c3685-122">시간 범위를 가능한 한 좁게 유지하면 쿼리가 제대로 수행되고 관리 가능한 결과를 반환하며 시간 초과되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="c3685-123">특정 프로세스 확인</span><span class="sxs-lookup"><span data-stu-id="c3685-123">Check specific processes</span></span>
<span data-ttu-id="c3685-124">시간 범위 바로 뒤에 PowerShell 응용 프로그램을 나타내는 프로세스 파일 이름을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="c3685-125">특정 명령 문자열 검색</span><span class="sxs-lookup"><span data-stu-id="c3685-125">Search for specific command strings</span></span>
<span data-ttu-id="c3685-126">나중에이 쿼리는 PowerShell을 사용 하 여 파일을 다운로드 하는 데 일반적으로 사용 되는 명령줄에서 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="c3685-127">결과 열 및 길이 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c3685-127">Customize result columns and length</span></span> 
<span data-ttu-id="c3685-128">쿼리에서 찾으려고 하는 데이터를 명확하게 식별하므로 결과 모양을 정의하는 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="c3685-129">`project`특정 열을 반환 하 고 `top` 결과 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="c3685-130">이러한 연산자를 사용 하면 결과의 형식이 적절 하 고 상당히 크고 프로세스를 간편 하 게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="c3685-131">**쿼리 실행**을 클릭하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="c3685-132">검색 쿼리와 결과에 중점을 두기 위해 쿼리 편집기의 오른쪽 위에 있는 확장 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![고급 구하기 쿼리 편집기의 확장 컨트롤 이미지](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="c3685-134">쿼리 결과를 차트로 보고 필터를 빠르게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="c3685-135">지침을 보려면 [쿼리 결과 작업에 대 한 내용을 읽어보십시오](advanced-hunting-query-results.md) .</span><span class="sxs-lookup"><span data-stu-id="c3685-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="c3685-136">고급 헌팅에 대한 일반적인 쿼리 연산자 살펴보기</span><span class="sxs-lookup"><span data-stu-id="c3685-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="c3685-137">첫 번째 쿼리를 실행하고 해당 구성 요소에 대한 일반적인 아이디어를 얻었으므로 약간 되돌아가서 몇 가지 기본 사항을 배울 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="c3685-138">고급 헌팅에서 사용하는 Kusto 쿼리 언어는 다음을 포함하여 다양한 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="c3685-139">연산자</span><span class="sxs-lookup"><span data-stu-id="c3685-139">Operator</span></span> | <span data-ttu-id="c3685-140">설명 및 사용법</span><span class="sxs-lookup"><span data-stu-id="c3685-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="c3685-141">조건자를 충족하는 행의 하위 집합으로 표를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="c3685-142">입력 표의 내용을 집계하는 표를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="c3685-143">각 표에서 지정된 열의 값을 일치시켜 새 표를 구성하는 두 테이블의 행을 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="c3685-144">입력 레코드 집합의 레코드 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="c3685-145">지정된 열을 기준으로 정렬된 처음 N개의 레코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="c3685-146">지정된 수의 행까지 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="c3685-147">포함할 열을 선택하고 이름을 바꾸거나 삭제하고 새 계산된 열을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="c3685-148">계산된 열을 만들고 결과 집합에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="c3685-149">Expr이 그룹에서 사용하는 고유한 값 집합의 동적(JSON) 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="c3685-150">표 집합에서 조건자와 일치하는 행을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="c3685-151">이러한 연산자의 실제 예제를 보려면 고급 헌팅의 **시작** 섹션에서 해당 연산자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="c3685-152">데이터 형식 및 해당 쿼리 구문의 영향 이해</span><span class="sxs-lookup"><span data-stu-id="c3685-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="c3685-153">고급 헌팅 표에서 데이터는 일반적으로 다음과 같은 데이터 형식으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="c3685-154">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c3685-154">Data type</span></span> | <span data-ttu-id="c3685-155">설명 및 쿼리 의미</span><span class="sxs-lookup"><span data-stu-id="c3685-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="c3685-156">일반적으로 이벤트 타임 스탬프를 나타내는 데이터 및 시간 정보</span><span class="sxs-lookup"><span data-stu-id="c3685-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="c3685-157">문자열</span><span class="sxs-lookup"><span data-stu-id="c3685-157">Character string</span></span> |
| `bool` | <span data-ttu-id="c3685-158">True 또는 False</span><span class="sxs-lookup"><span data-stu-id="c3685-158">True or false</span></span> |
| `int` | <span data-ttu-id="c3685-159">32비트 숫자 값</span><span class="sxs-lookup"><span data-stu-id="c3685-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="c3685-160">64비트 숫자 값</span><span class="sxs-lookup"><span data-stu-id="c3685-160">64-bit numeric value</span></span> |

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="c3685-161">쿼리 작성시 도움말 보기</span><span class="sxs-lookup"><span data-stu-id="c3685-161">Get help as you write queries</span></span>
<span data-ttu-id="c3685-162">다음 기능을 활용하여 쿼리를 더 빠르게 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="c3685-162">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="c3685-163">**Autosuggest** -쿼리를 작성할 때 고급 사냥은 IntelliSense의 추천 단어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-163">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="c3685-164">**스키마 트리** -테이블 및 해당 열 목록이 포함 된 스키마 표현이 작업 영역 옆에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-164">**Schema tree** — a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="c3685-165">자세한 내용을 보려면 항목 위로 마우스를 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-165">For more information, hover over an item.</span></span> <span data-ttu-id="c3685-166">항목을 두 번 클릭하여 쿼리 편집기에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-166">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="c3685-167">**[스키마 참조](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** -테이블 및 열 설명과 관련 된 포털 내 참조 및 지원 되는 이벤트 유형 ( `ActionType` 값) 및 예제 쿼리</span><span class="sxs-lookup"><span data-stu-id="c3685-167">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="c3685-168">편집기에서 여러 쿼리 작업</span><span class="sxs-lookup"><span data-stu-id="c3685-168">Work with multiple queries in the editor</span></span>
<span data-ttu-id="c3685-169">쿼리 편집기는 여러 쿼리를 실험 하기 위해 스크래치 pad로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-169">The query editor can serve as your scratch pad for experimenting with multiple queries.</span></span> <span data-ttu-id="c3685-170">여러 쿼리를 사용 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-170">To use multiple queries:</span></span>

- <span data-ttu-id="c3685-171">각 쿼리를 빈 줄로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-171">Separate each query with an empty line.</span></span>
- <span data-ttu-id="c3685-172">쿼리를 실행 하기 전에 쿼리 부분에 커서를 놓고 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-172">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="c3685-173">이렇게 하면 선택한 쿼리만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-173">This will run only the selected query.</span></span> <span data-ttu-id="c3685-174">다른 쿼리를 실행 하려면 그에 따라 커서를 이동 하 고 **쿼리 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-174">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![쿼리가 여러 개 있는 쿼리 편집기 이미지](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="c3685-176">샘플 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="c3685-176">Use sample queries</span></span>

<span data-ttu-id="c3685-177">**시작** 섹션에서는 자주 사용하는 연산자를 사용하는 몇 가지 간단한 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-177">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="c3685-178">이러한 쿼리를 실행하고 약간 수정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c3685-178">Try running these queries and making small modifications to them.</span></span>

![고급 헌팅 창 이미지](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="c3685-180">기본 쿼리 샘플과는 별도로 특정 위협 헌팅 시나리오에 대한 [공유 쿼리](advanced-hunting-shared-queries.md)에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-180">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="c3685-181">페이지의 왼쪽에 있는 공유 쿼리 또는 GitHub 쿼리 리포지토리를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="c3685-181">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="c3685-182">쿼리 언어 설명서에 액세스</span><span class="sxs-lookup"><span data-stu-id="c3685-182">Access query language documentation</span></span>

<span data-ttu-id="c3685-183">Kusto 쿼리 언어와 지원되는 연산자에 대한 자세한 내용은 [Kusto 쿼리 언어 설명서](https://docs.microsoft.com/azure/kusto/query/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3685-183">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3685-184">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c3685-184">Related topics</span></span>
- [<span data-ttu-id="c3685-185">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="c3685-185">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c3685-186">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="c3685-186">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="c3685-187">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="c3685-187">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c3685-188">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="c3685-188">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c3685-189">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="c3685-189">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c3685-190">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="c3685-190">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
