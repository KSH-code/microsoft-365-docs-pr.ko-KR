---
title: Microsoft 365 Defender의 고급 헌팅 쿼리 언어 학습
description: 첫 번째 위협 헌팅 쿼리를 만들고 고급 헌팅 쿼리 언어의 일반적인 연산자와 기타 요소에 대한 정보를 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 언어, 학습, 첫 번째 쿼리, 원격 분석, 이벤트, 원격 분석, 사용자 지정 검색, schema, kusto, 운영자, 데이터 형식, powershell 다운로드, 쿼리 예제
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
ms.openlocfilehash: 14287fb6dea9dda8accb580246b383f0427c3b3f
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952623"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="9f0bb-104">고급 헌팅 쿼리 언어 알아보기</span><span class="sxs-lookup"><span data-stu-id="9f0bb-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9f0bb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9f0bb-105">**Applies to:**</span></span>
- <span data-ttu-id="9f0bb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9f0bb-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="9f0bb-107">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9f0bb-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="9f0bb-108">고급 헌팅은 [Kusto 쿼리 언어](/azure/kusto/query/)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-108">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="9f0bb-109">Kusto 연산자 및 문을 사용하여 특수한 Schema에서 정보를 찾는 [쿼리를 구성할 수 있습니다.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="9f0bb-109">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="9f0bb-110">이러한 개념을 보다 잘 이해하려면 첫 번째 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-110">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="9f0bb-111">첫 번째 쿼리 시도하기</span><span class="sxs-lookup"><span data-stu-id="9f0bb-111">Try your first query</span></span>

<span data-ttu-id="9f0bb-112">Microsoft 365 보안 센터에서 헌팅으로 **이동하여** 첫 번째 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-112">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="9f0bb-113">다음 예제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-113">Use the following example:</span></span>

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

<span data-ttu-id="9f0bb-114">**[고급 헌팅에서 이 쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="9f0bb-114">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="9f0bb-115">쿼리를 설명하고 검색할 테이블 지정</span><span class="sxs-lookup"><span data-stu-id="9f0bb-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="9f0bb-116">쿼리의 시작부에 해당 설명을 설명하는 짧은 설명이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="9f0bb-117">이 설명은 나중에 쿼리를 저장하고 조직의 다른 사용자와 공유하기로 결정한 경우 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-117">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="9f0bb-118">쿼리 자체는 일반적으로 테이블 이름으로 시작하고 그 다음에 파이프()로 시작하는 여러 요소가 차례로 `|` 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-118">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="9f0bb-119">이 예제에서는 먼저 두 테이블의 조합을 만들고 , 및 파이프된 요소를 필요한 경우  `DeviceProcessEvents` `DeviceNetworkEvents` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="9f0bb-120">시간 범위 설정</span><span class="sxs-lookup"><span data-stu-id="9f0bb-120">Set the time range</span></span>
<span data-ttu-id="9f0bb-121">첫 번째 파이프된 요소는 이전 7일로 범위가 지정되는 시간 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="9f0bb-122">시간 범위를 제한하면 쿼리가 잘 수행되도록 하고 관리 가능한 결과를 반환하며 시간이 초과되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-122">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="9f0bb-123">특정 프로세스 확인</span><span class="sxs-lookup"><span data-stu-id="9f0bb-123">Check specific processes</span></span>
<span data-ttu-id="9f0bb-124">시간 범위 다음에 PowerShell 응용 프로그램을 나타내는 프로세스 파일 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="9f0bb-125">특정 명령 문자열 검색</span><span class="sxs-lookup"><span data-stu-id="9f0bb-125">Search for specific command strings</span></span>
<span data-ttu-id="9f0bb-126">그런 다음 쿼리는 일반적으로 PowerShell을 사용하여 파일을 다운로드하는 데 사용되는 명령줄에서 문자열을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="9f0bb-127">결과 열 및 길이 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9f0bb-127">Customize result columns and length</span></span> 
<span data-ttu-id="9f0bb-128">이제 쿼리에서 찾을 데이터를 명확하게 식별하기 위해 결과의 모양을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-128">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="9f0bb-129">`project` 특정 열을 반환하고 결과 `top` 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="9f0bb-130">이러한 연산자는 결과가 잘 형식화되어 있으며 상당히 크고 처리하기 쉬운지 보장하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="9f0bb-131">결과를 **표시하려면** 쿼리 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-131">Select **Run query** to see the results.</span></span> <span data-ttu-id="9f0bb-132">쿼리 편집기 오른쪽 위에 있는 확장 아이콘을 사용하여 헌팅 쿼리 및 결과에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-132">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![고급 헌팅 쿼리 편집기에서 확장 컨트롤의 이미지](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="9f0bb-134">쿼리 결과를 차트로 보고 필터를 빠르게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="9f0bb-135">자세한 [지침은 쿼리 결과 사용에 대해 읽어 보시고](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="9f0bb-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="9f0bb-136">일반적인 쿼리 연산자 학습</span><span class="sxs-lookup"><span data-stu-id="9f0bb-136">Learn common query operators</span></span>

<span data-ttu-id="9f0bb-137">첫 번째 쿼리를 실행하고 해당 구성 요소에 대한 일반적인 아이디어를 품고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-137">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="9f0bb-138">이제 약간 뒤로 돌아가 몇 가지 기본을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-138">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="9f0bb-139">고급 헌팅에서 사용하는 Kusto 쿼리 언어는 다음을 포함하여 다양한 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-139">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="9f0bb-140">연산자</span><span class="sxs-lookup"><span data-stu-id="9f0bb-140">Operator</span></span> | <span data-ttu-id="9f0bb-141">설명 및 사용법</span><span class="sxs-lookup"><span data-stu-id="9f0bb-141">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="9f0bb-142">조건자를 충족하는 행의 하위 집합으로 표를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-142">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="9f0bb-143">입력 표의 내용을 집계하는 표를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-143">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="9f0bb-144">각 표에서 지정된 열의 값을 일치시켜 새 표를 구성하는 두 테이블의 행을 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-144">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="9f0bb-145">입력 레코드 집합의 레코드 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-145">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="9f0bb-146">지정된 열을 기준으로 정렬된 처음 N개의 레코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-146">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="9f0bb-147">지정된 수의 행까지 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-147">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="9f0bb-148">포함할 열을 선택하고 이름을 바꾸거나 삭제하고 새 계산된 열을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-148">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="9f0bb-149">계산된 열을 만들고 결과 집합에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-149">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="9f0bb-150">Expr이 그룹에서 사용하는 고유한 값 집합의 동적(JSON) 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-150">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="9f0bb-151">표 집합에서 조건자와 일치하는 행을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-151">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="9f0bb-152">이러한 연산자의 실제 예제를 보려면 고급 헌팅의 **시작** 섹션에서 해당 연산자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-152">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="9f0bb-153">데이터 형식 이해</span><span class="sxs-lookup"><span data-stu-id="9f0bb-153">Understand data types</span></span>

<span data-ttu-id="9f0bb-154">고급 헌팅은 다음과 같은 일반적인 형식을 포함하여 Kusto 데이터 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-154">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="9f0bb-155">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9f0bb-155">Data type</span></span> | <span data-ttu-id="9f0bb-156">설명 및 쿼리 의미</span><span class="sxs-lookup"><span data-stu-id="9f0bb-156">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="9f0bb-157">일반적으로 이벤트 타임스탬프를 나타내는 데이터 및 시간 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-157">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="9f0bb-158">지원되는 datetime 형식 참조</span><span class="sxs-lookup"><span data-stu-id="9f0bb-158">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="9f0bb-159">UTF-8의 문자열은 단일 따옴표( ) 또는 `'` 따옴표()로 `"` 묶입니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-159">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="9f0bb-160">문자열에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="9f0bb-160">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="9f0bb-161">이 데이터 형식은 지원 `true` 또는 `false` 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-161">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="9f0bb-162">지원되는 리터럴 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="9f0bb-162">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="9f0bb-163">32비트 정수</span><span class="sxs-lookup"><span data-stu-id="9f0bb-163">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="9f0bb-164">64비트 정수</span><span class="sxs-lookup"><span data-stu-id="9f0bb-164">64-bit integer</span></span> |

<span data-ttu-id="9f0bb-165">이러한 데이터 형식에 대한 자세한 내용은 Kusto 스칼라 데이터 형식 [을 읽어 보아야 합니다.](/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="9f0bb-165">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="9f0bb-166">쿼리 작성시 도움말 보기</span><span class="sxs-lookup"><span data-stu-id="9f0bb-166">Get help as you write queries</span></span>
<span data-ttu-id="9f0bb-167">다음 기능을 활용하여 쿼리를 더 빠르게 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-167">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="9f0bb-168">**자동 제안**- 쿼리를 작성할 때 고급 헌팅은 쿼리의 제안을 IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-168">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="9f0bb-169">**Schema tree**— 테이블 목록과 해당 열을 포함하는 Schema 표현이 작업 영역 옆에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-169">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="9f0bb-170">자세한 내용을 보려면 항목 위로 마우스를 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-170">For more information, hover over an item.</span></span> <span data-ttu-id="9f0bb-171">항목을 두 번 클릭하여 쿼리 편집기에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-171">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="9f0bb-172">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—테이블 및 열 설명과 함께 포털 내 참조와 지원되는 이벤트 유형(값) `ActionType` 및 샘플 쿼리</span><span class="sxs-lookup"><span data-stu-id="9f0bb-172">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="9f0bb-173">편집기에서 여러 쿼리 작업</span><span class="sxs-lookup"><span data-stu-id="9f0bb-173">Work with multiple queries in the editor</span></span>
<span data-ttu-id="9f0bb-174">쿼리 편집기를 사용하여 여러 쿼리를 실험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-174">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="9f0bb-175">여러 쿼리를 사용:</span><span class="sxs-lookup"><span data-stu-id="9f0bb-175">To use multiple queries:</span></span>

- <span data-ttu-id="9f0bb-176">각 쿼리를 빈 줄로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-176">Separate each query with an empty line.</span></span>
- <span data-ttu-id="9f0bb-177">쿼리의 모든 부분에 커서를 배치하여 쿼리를 실행하기 전에 해당 쿼리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-177">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="9f0bb-178">그러면 선택한 쿼리만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-178">This will run only the selected query.</span></span> <span data-ttu-id="9f0bb-179">다른 쿼리를 실행하려면 그에 따라 커서를 이동하고 쿼리 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f0bb-179">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![쿼리가 여러 개 있는 쿼리 편집기 이미지](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="9f0bb-181">샘플 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="9f0bb-181">Use sample queries</span></span>

<span data-ttu-id="9f0bb-182">**시작** 섹션에서는 자주 사용하는 연산자를 사용하는 몇 가지 간단한 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-182">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="9f0bb-183">이러한 쿼리를 실행하고 약간 수정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-183">Try running these queries and making small modifications to them.</span></span>

![고급 헌팅 창 이미지](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="9f0bb-185">기본 쿼리 샘플과는 별도로 특정 위협 헌팅 시나리오에 대한 [공유 쿼리](advanced-hunting-shared-queries.md)에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-185">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="9f0bb-186">페이지 왼쪽 또는 GitHub 쿼리 리포지토리의 공유 [쿼리를 탐색합니다.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="9f0bb-186">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="9f0bb-187">쿼리 언어 설명서에 액세스</span><span class="sxs-lookup"><span data-stu-id="9f0bb-187">Access query language documentation</span></span>

<span data-ttu-id="9f0bb-188">Kusto 쿼리 언어와 지원되는 연산자에 대한 자세한 내용은 [Kusto 쿼리 언어 설명서](/azure/kusto/query/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-188">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

>[!NOTE]
><span data-ttu-id="9f0bb-189">이 문서의 일부 테이블은 끝점용 Microsoft Defender에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9f0bb-190">[Microsoft 365 Defender를 켜서](m365d-enable.md) 더 많은 데이터 원본을 사용하여 위협을 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="9f0bb-191">Endpoint용 Microsoft Defender에서 Microsoft Defender의 고급 헌팅 쿼리 마이그레이션의 단계에 따라 끝점용 [Microsoft Defender에서 Microsoft](advanced-hunting-migrate-from-mde.md)365 Defender로 고급 헌팅 워크플로를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f0bb-192">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9f0bb-192">Related topics</span></span>
- [<span data-ttu-id="9f0bb-193">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="9f0bb-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9f0bb-194">쿼리 결과로 작업</span><span class="sxs-lookup"><span data-stu-id="9f0bb-194">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="9f0bb-195">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="9f0bb-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9f0bb-196">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9f0bb-197">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="9f0bb-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9f0bb-198">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="9f0bb-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)