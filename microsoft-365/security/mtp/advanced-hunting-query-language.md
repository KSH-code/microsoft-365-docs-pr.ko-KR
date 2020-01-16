---
title: Microsoft Threat Protection에서 고급 헌팅 쿼리 언어 알아보기
description: 첫 번째 위협 헌팅 쿼리를 만들고 고급 헌팅 쿼리 언어의 일반적인 연산자와 기타 요소에 대한 정보를 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 언어, 학습, 첫 번째 쿼리, 원격 분석, 이벤트, 원격, 사용자 지정 감지, 스키마, kusto, and, data types
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 36f2efb733e8403b30e0ecc406bb1ea2d6a6248e
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210343"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="60a5a-104">고급 헌팅 쿼리 언어 알아보기</span><span class="sxs-lookup"><span data-stu-id="60a5a-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="60a5a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="60a5a-105">**Applies to:**</span></span>
- <span data-ttu-id="60a5a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="60a5a-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="60a5a-107">고급 헌팅은 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="60a5a-108">Kusto 구문 및 연산자를 사용하여 고급 헌팅을 위해 특별히 구성된 [스키마](advanced-hunting-schema-tables.md)에서 정보를 찾는 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="60a5a-109">이러한 개념을 보다 잘 이해하려면 첫 번째 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="60a5a-110">첫 번째 쿼리 시도하기</span><span class="sxs-lookup"><span data-stu-id="60a5a-110">Try your first query</span></span>

<span data-ttu-id="60a5a-111">Microsoft 365 보안 센터에서 **헌팅**으로 이동하여 첫 번째 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-111">in the Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="60a5a-112">다음 예제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents 
| where Timestamp > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

<span data-ttu-id="60a5a-113">이는 고급 헌팅에서 표시되는 모습입니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft Defender ATP 고급 헌팅 쿼리 이미지](../images/advanced-hunting-query-example.png)

<span data-ttu-id="60a5a-115">쿼리는 내용을 설명하는 짧은 메모로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-115">The query starts with a short comment describing what it is for.</span></span> <span data-ttu-id="60a5a-116">이렇게 하면 나중에 쿼리를 저장하여 조직의 다른 사용자와 공유하도록 결정한 경우에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-116">This helps if you later decide to save your query and share it with others in your organization.</span></span>

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

<span data-ttu-id="60a5a-117">일반적으로 쿼리 자체는 표 이름으로 시작하고 다음으로 파이프(`|`)로 시작되는 일련의 요소가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="60a5a-118">이 예제에서는 표 이름 `DeviceProcessEvents`로 추가하고, 필요에 따라 파이프된 요소를 추가하는 것으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-118">In this example, we start by adding  with the table name `DeviceProcessEvents` and add piped elements as needed.</span></span>

<span data-ttu-id="60a5a-119">첫 번째 파이프된 요소는 이전 7일 이내에 범위가 지정된 시간 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-119">The first piped element is a time filter scoped within the previous seven days.</span></span> <span data-ttu-id="60a5a-120">시간 범위를 가능한 한 좁게 유지하면 쿼리가 제대로 수행되고 관리 가능한 결과를 반환하며 시간 초과되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="60a5a-121">시간 범위 바로 다음으로 PowerShell 응용 프로그램을 나타내는 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-121">The time range is immediately followed by a search for files representing the PowerShell application.</span></span>

```kusto
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

<span data-ttu-id="60a5a-122">그런 다음 쿼리는 PowerShell과 함께 일반적으로 파일을 다운로드하는 데 사용되는 명령줄을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-122">Afterwards, the query looks for command lines that are typically used with PowerShell to download files.</span></span>

```kusto
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

<span data-ttu-id="60a5a-123">쿼리에서 찾으려고 하는 데이터를 명확하게 식별하므로 결과 모양을 정의하는 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="60a5a-124">`project`은(는) 특정 열을 반환하고 `top`은(는) 결과 수를 제한하여 결과를 잘 서식화하고 상당히 크고 쉽게 처리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-124">`project` returns specific columns and `top` limits the number of results, making the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

<span data-ttu-id="60a5a-125">**쿼리 실행**을 클릭하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="60a5a-126">헌팅 쿼리와 결과에 집중할 수 있도록 화면 보기를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-126">You can expand the screen view so you can focus on your hunting query and the results.</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="60a5a-127">고급 헌팅에 대한 일반적인 쿼리 연산자 살펴보기</span><span class="sxs-lookup"><span data-stu-id="60a5a-127">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="60a5a-128">첫 번째 쿼리를 실행하고 해당 구성 요소에 대한 일반적인 아이디어를 얻었으므로 약간 되돌아가서 몇 가지 기본 사항을 배울 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-128">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="60a5a-129">고급 헌팅에서 사용하는 Kusto 쿼리 언어는 다음을 포함하여 다양한 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-129">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="60a5a-130">연산자</span><span class="sxs-lookup"><span data-stu-id="60a5a-130">Operator</span></span> | <span data-ttu-id="60a5a-131">설명 및 사용법</span><span class="sxs-lookup"><span data-stu-id="60a5a-131">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="60a5a-132">조건자를 충족하는 행의 하위 집합으로 표를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-132">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="60a5a-133">입력 표의 내용을 집계하는 표를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-133">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="60a5a-134">각 표에서 지정된 열의 값을 일치시켜 새 표를 구성하는 두 테이블의 행을 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-134">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="60a5a-135">입력 레코드 집합의 레코드 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-135">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="60a5a-136">지정된 열을 기준으로 정렬된 처음 N개의 레코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-136">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="60a5a-137">지정된 수의 행까지 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-137">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="60a5a-138">포함할 열을 선택하고 이름을 바꾸거나 삭제하고 새 계산된 열을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-138">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="60a5a-139">계산된 열을 만들고 결과 집합에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-139">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="60a5a-140">Expr이 그룹에서 사용하는 고유한 값 집합의 동적(JSON) 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-140">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="60a5a-141">표 집합에서 조건자와 일치하는 행을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-141">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="60a5a-142">이러한 연산자의 실제 예제를 보려면 고급 헌팅의 **시작** 섹션에서 해당 연산자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-142">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="60a5a-143">데이터 형식 및 해당 쿼리 구문의 영향 이해</span><span class="sxs-lookup"><span data-stu-id="60a5a-143">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="60a5a-144">고급 헌팅 표에서 데이터는 일반적으로 다음과 같은 데이터 형식으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-144">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="60a5a-145">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="60a5a-145">Data type</span></span> | <span data-ttu-id="60a5a-146">설명 및 쿼리 의미</span><span class="sxs-lookup"><span data-stu-id="60a5a-146">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="60a5a-147">일반적으로 이벤트 타임 스탬프를 나타내는 데이터 및 시간 정보</span><span class="sxs-lookup"><span data-stu-id="60a5a-147">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="60a5a-148">문자열</span><span class="sxs-lookup"><span data-stu-id="60a5a-148">Character string</span></span> |
| `bool` | <span data-ttu-id="60a5a-149">True 또는 False</span><span class="sxs-lookup"><span data-stu-id="60a5a-149">True or false</span></span> |
| `int` | <span data-ttu-id="60a5a-150">32비트 숫자 값</span><span class="sxs-lookup"><span data-stu-id="60a5a-150">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="60a5a-151">64비트 숫자 값</span><span class="sxs-lookup"><span data-stu-id="60a5a-151">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="60a5a-152">샘플 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="60a5a-152">Use sample queries</span></span>

<span data-ttu-id="60a5a-153">**시작** 섹션에서는 자주 사용하는 연산자를 사용하는 몇 가지 간단한 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-153">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="60a5a-154">이러한 쿼리를 실행하고 약간 수정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="60a5a-154">Try running these queries and making small modifications to them.</span></span>

![고급 헌팅 창 이미지](../images/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="60a5a-156">기본 쿼리 샘플과는 별도로 특정 위협 헌팅 시나리오에 대한 [공유 쿼리](advanced-hunting-shared-queries.md)에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-156">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="60a5a-157">페이지의 왼쪽에 있는 공유 쿼리 또는 GitHub 쿼리 리포지토리를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="60a5a-157">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="60a5a-158">쿼리 언어 설명서에 액세스</span><span class="sxs-lookup"><span data-stu-id="60a5a-158">Access query language documentation</span></span>

<span data-ttu-id="60a5a-159">Kusto 쿼리 언어와 지원되는 연산자에 대한 자세한 내용은 [Kusto 쿼리 언어 설명서](https://docs.microsoft.com/azure/kusto/query/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60a5a-159">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="60a5a-160">관련 항목</span><span class="sxs-lookup"><span data-stu-id="60a5a-160">Related topics</span></span>
- [<span data-ttu-id="60a5a-161">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="60a5a-161">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="60a5a-162">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="60a5a-162">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="60a5a-163">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="60a5a-163">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="60a5a-164">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="60a5a-164">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="60a5a-165">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="60a5a-165">Apply query best practices</span></span>](advanced-hunting-best-practices.md)