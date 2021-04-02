---
title: 고급 헌팅 쿼리 언어 알아보기
description: 첫 번째 위협 헌팅 쿼리를 만들고 고급 헌팅 쿼리 언어의 일반적인 연산자와 기타 요소에 대한 정보를 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 언어, 학습, 첫 번째 쿼리, 원격 분석, 이벤트, 원격 분석, 사용자 지정 검색, schema, kusto, 연산자, 데이터 형식
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: af612a051f133e4846e04033ab35ea39769d0193
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499539"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="8c662-104">고급 헌팅 쿼리 언어 알아보기</span><span class="sxs-lookup"><span data-stu-id="8c662-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c662-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8c662-105">**Applies to:**</span></span>
- [<span data-ttu-id="8c662-106">엔드포인트용 Defender</span><span class="sxs-lookup"><span data-stu-id="8c662-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="8c662-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8c662-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8c662-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="8c662-109">고급 헌팅은 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-109">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="8c662-110">Kusto 연산자 및 문을 사용하여 특수한 Schema에서 정보를 찾는 [쿼리를 구성할 수 있습니다.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="8c662-110">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-reference.md).</span></span> <span data-ttu-id="8c662-111">이러한 개념을 보다 잘 이해하려면 첫 번째 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-111">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="8c662-112">첫 번째 쿼리 시도하기</span><span class="sxs-lookup"><span data-stu-id="8c662-112">Try your first query</span></span>

<span data-ttu-id="8c662-113">Microsoft Defender 보안 센터에서 고급 헌팅으로 **이동하여** 첫 번째 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-113">In Microsoft Defender Security Center, go to **Advanced hunting** to run your first query.</span></span> <span data-ttu-id="8c662-114">다음 예제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-114">Use the following example:</span></span>

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
<span data-ttu-id="8c662-115">**[고급 헌팅에서 이 쿼리 실행](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="8c662-115">**[Run this query in advanced hunting](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="8c662-116">쿼리를 설명하고 검색할 테이블 지정</span><span class="sxs-lookup"><span data-stu-id="8c662-116">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="8c662-117">쿼리의 시작부에 해당 설명을 설명하는 짧은 설명이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-117">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="8c662-118">이 설명은 나중에 쿼리를 저장하고 조직의 다른 사용자와 공유하기로 결정한 경우 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-118">This comment helps if you later decide to save the query and share it with others in your organization.</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
```
<span data-ttu-id="8c662-119">쿼리 자체는 일반적으로 테이블 이름으로 시작하고 그 다음에 파이프()로 시작하는 여러 요소가 차례로 `|` 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-119">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="8c662-120">이 예제에서는 먼저 두 테이블의 조합을 만들고 , 및 파이프된 요소를 필요한 경우  `DeviceProcessEvents` `DeviceNetworkEvents` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-120">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="8c662-121">시간 범위 설정</span><span class="sxs-lookup"><span data-stu-id="8c662-121">Set the time range</span></span>
<span data-ttu-id="8c662-122">첫 번째 파이프된 요소는 이전 7일로 범위가 지정되는 시간 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-122">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="8c662-123">시간 범위를 제한하면 쿼리가 잘 수행되도록 하고 관리 가능한 결과를 반환하며 시간이 초과되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-123">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="8c662-124">특정 프로세스 확인</span><span class="sxs-lookup"><span data-stu-id="8c662-124">Check specific processes</span></span>
<span data-ttu-id="8c662-125">시간 범위 다음에 PowerShell 응용 프로그램을 나타내는 프로세스 파일 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-125">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="8c662-126">특정 명령 문자열 검색</span><span class="sxs-lookup"><span data-stu-id="8c662-126">Search for specific command strings</span></span>
<span data-ttu-id="8c662-127">그런 다음 쿼리는 일반적으로 PowerShell을 사용하여 파일을 다운로드하는 데 사용되는 명령줄에서 문자열을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-127">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="8c662-128">결과 열 및 길이 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8c662-128">Customize result columns and length</span></span> 
<span data-ttu-id="8c662-129">이제 쿼리에서 찾을 데이터를 명확하게 식별하기 위해 결과의 모양을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-129">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="8c662-130">`project` 특정 열을 반환하고 결과 `top` 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-130">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="8c662-131">이러한 연산자는 결과가 잘 형식화되어 있으며 상당히 크고 처리하기 쉬운지 보장하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-131">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="8c662-132">결과를 **표시하려면** 쿼리 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-132">Select **Run query** to see the results.</span></span> <span data-ttu-id="8c662-133">쿼리 편집기 오른쪽 위에 있는 확장 아이콘을 사용하여 헌팅 쿼리 및 결과에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-133">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![고급 헌팅 쿼리 편집기에서 확장 컨트롤의 이미지](images/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="8c662-135">쿼리 결과를 차트로 보고 필터를 빠르게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-135">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="8c662-136">자세한 [지침은 쿼리 결과 사용에 대해 읽어 보시고](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="8c662-136">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="8c662-137">고급 헌팅에 대한 일반적인 쿼리 연산자 살펴보기</span><span class="sxs-lookup"><span data-stu-id="8c662-137">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="8c662-138">첫 번째 쿼리를 실행하고 해당 구성 요소에 대한 일반적인 아이디어를 품고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-138">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="8c662-139">이제 약간 뒤로 돌아가 몇 가지 기본을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-139">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="8c662-140">고급 헌팅에서 사용하는 Kusto 쿼리 언어는 다음을 포함하여 다양한 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-140">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="8c662-141">연산자</span><span class="sxs-lookup"><span data-stu-id="8c662-141">Operator</span></span> | <span data-ttu-id="8c662-142">설명 및 사용법</span><span class="sxs-lookup"><span data-stu-id="8c662-142">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="8c662-143">조건자를 충족하는 행의 하위 집합으로 표를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-143">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="8c662-144">입력 표의 내용을 집계하는 표를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-144">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="8c662-145">각 표에서 지정된 열의 값을 일치시켜 새 표를 구성하는 두 테이블의 행을 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-145">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="8c662-146">입력 레코드 집합의 레코드 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-146">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="8c662-147">지정된 열을 기준으로 정렬된 처음 N개의 레코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-147">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="8c662-148">지정된 수의 행까지 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-148">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="8c662-149">포함할 열을 선택하고 이름을 바꾸거나 삭제하고 새 계산된 열을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-149">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="8c662-150">계산된 열을 만들고 결과 집합에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-150">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="8c662-151">Expr이 그룹에서 사용하는 고유한 값 집합의 동적(JSON) 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-151">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="8c662-152">표 집합에서 조건자와 일치하는 행을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-152">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="8c662-153">이러한 연산자의 라이브 예제를 확인하기 위해  고급 헌팅 페이지의 시작 섹션에서 연산자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-153">To see a live example of these operators, run them from the **Get started** section of the advanced hunting page.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="8c662-154">데이터 형식 이해</span><span class="sxs-lookup"><span data-stu-id="8c662-154">Understand data types</span></span>

<span data-ttu-id="8c662-155">고급 헌팅은 다음과 같은 일반적인 형식을 포함하여 Kusto 데이터 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-155">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="8c662-156">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c662-156">Data type</span></span> | <span data-ttu-id="8c662-157">설명 및 쿼리 의미</span><span class="sxs-lookup"><span data-stu-id="8c662-157">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="8c662-158">일반적으로 이벤트 타임스탬프를 나타내는 데이터 및 시간 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-158">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="8c662-159">지원되는 datetime 형식 참조</span><span class="sxs-lookup"><span data-stu-id="8c662-159">See supported datetime formats</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="8c662-160">UTF-8의 문자열은 단일 따옴표( ) 또는 `'` 따옴표()로 `"` 묶입니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-160">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="8c662-161">문자열에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="8c662-161">Read more about strings</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="8c662-162">이 데이터 형식은 지원 `true` 또는 `false` 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-162">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="8c662-163">지원되는 리터럴 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="8c662-163">See supported literals and operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="8c662-164">32비트 정수</span><span class="sxs-lookup"><span data-stu-id="8c662-164">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="8c662-165">64비트 정수</span><span class="sxs-lookup"><span data-stu-id="8c662-165">64-bit integer</span></span> |

<span data-ttu-id="8c662-166">이러한 데이터 형식에 대한 자세한 내용은 Kusto 스칼라 데이터 형식 [을 읽어 보아야 합니다.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="8c662-166">To learn more about these data types, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="8c662-167">쿼리 작성시 도움말 보기</span><span class="sxs-lookup"><span data-stu-id="8c662-167">Get help as you write queries</span></span>
<span data-ttu-id="8c662-168">다음 기능을 활용하여 쿼리를 더 빠르게 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="8c662-168">Take advantage of the following functionality to write queries faster:</span></span>

- <span data-ttu-id="8c662-169">**자동 제안**- 쿼리를 작성할 때 고급 헌팅은 쿼리의 제안을 IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="8c662-169">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span>
- <span data-ttu-id="8c662-170">**Schema tree**— 테이블 목록과 해당 열을 포함하는 Schema 표현이 작업 영역 옆에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-170">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="8c662-171">자세한 내용을 보려면 항목 위로 마우스를 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-171">For more information, hover over an item.</span></span> <span data-ttu-id="8c662-172">항목을 두 번 클릭하여 쿼리 편집기에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-172">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="8c662-173">**[Schema reference](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**—테이블 및 열 설명과 함께 포털 내 참조와 지원되는 이벤트 유형(값) `ActionType` 및 샘플 쿼리</span><span class="sxs-lookup"><span data-stu-id="8c662-173">**[Schema reference](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="8c662-174">편집기에서 여러 쿼리 작업</span><span class="sxs-lookup"><span data-stu-id="8c662-174">Work with multiple queries in the editor</span></span>
<span data-ttu-id="8c662-175">쿼리 편집기를 사용하여 여러 쿼리를 실험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-175">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="8c662-176">여러 쿼리를 사용:</span><span class="sxs-lookup"><span data-stu-id="8c662-176">To use multiple queries:</span></span>

- <span data-ttu-id="8c662-177">각 쿼리를 빈 줄로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-177">Separate each query with an empty line.</span></span>
- <span data-ttu-id="8c662-178">쿼리의 모든 부분에 커서를 배치하여 쿼리를 실행하기 전에 해당 쿼리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-178">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="8c662-179">그러면 선택한 쿼리만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-179">This will run only the selected query.</span></span> <span data-ttu-id="8c662-180">다른 쿼리를 실행하려면 그에 따라 커서를 이동하고 쿼리 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c662-180">To run another query, move the cursor accordingly and select **Run query**.</span></span>

<span data-ttu-id="8c662-181">![쿼리가 여러 개 있는 고급 헌팅 쿼리 편집기 이미지 ](images/ah-multi-query.png)
 </span><span class="sxs-lookup"><span data-stu-id="8c662-181">![Image of the advanced hunting query editor with multiple queries](images/ah-multi-query.png)
_Query editor with multiple queries_</span></span>

## <a name="use-sample-queries"></a><span data-ttu-id="8c662-182">샘플 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="8c662-182">Use sample queries</span></span>

<span data-ttu-id="8c662-183">**시작** 섹션에서는 자주 사용하는 연산자를 사용하는 몇 가지 간단한 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-183">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="8c662-184">이러한 쿼리를 실행하고 약간 수정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="8c662-184">Try running these queries and making small modifications to them.</span></span>

![고급 헌팅 시작 탭의 이미지](images/atp-advanced-hunting.png)

> [!NOTE]
> <span data-ttu-id="8c662-186">기본 쿼리 샘플과는 별도로 특정 위협 헌팅 시나리오에 대한 [공유 쿼리](advanced-hunting-shared-queries.md)에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c662-186">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="8c662-187">페이지 왼쪽 또는 GitHub 쿼리 리포지토리의 공유 [쿼리를 탐색합니다.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="8c662-187">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-comprehensive-query-language-reference"></a><span data-ttu-id="8c662-188">포괄적인 쿼리 언어 참조 액세스</span><span class="sxs-lookup"><span data-stu-id="8c662-188">Access comprehensive query language reference</span></span>

<span data-ttu-id="8c662-189">쿼리 언어에 대한 자세한 내용은 [Kusto 쿼리 언어 설명서를 참조하세요.](https://docs.microsoft.com/azure/kusto/query/)</span><span class="sxs-lookup"><span data-stu-id="8c662-189">For detailed information about the query language, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c662-190">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8c662-190">Related topics</span></span>
- [<span data-ttu-id="8c662-191">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="8c662-191">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8c662-192">쿼리 결과로 작업</span><span class="sxs-lookup"><span data-stu-id="8c662-192">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="8c662-193">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="8c662-193">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8c662-194">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="8c662-194">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="8c662-195">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="8c662-195">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
