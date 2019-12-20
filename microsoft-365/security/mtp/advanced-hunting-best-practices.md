---
title: Microsoft Threat Protection의 고급 헌팅 모범 사례
description: 고급 헌팅을 사용할 때 빠르고 효과적 이며 오류가 없는 위협 헌팅 쿼리를 작성하는 방법을 알아보세요.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, 사용자 지정 검색, 스키마, kusto, 타임아웃 방지, 명령 줄, 프로세스 id
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
ms.openlocfilehash: 871f659074c4f8386746e341db4d3500c5e80a31
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807007"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="e9e06-104">고급 헌팅 쿼리 모범 사례</span><span class="sxs-lookup"><span data-stu-id="e9e06-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="e9e06-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e9e06-105">**Applies to:**</span></span>
- <span data-ttu-id="e9e06-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e9e06-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="optimize-query-performance"></a><span data-ttu-id="e9e06-107">쿼리 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="e9e06-107">Optimize query performance</span></span>
<span data-ttu-id="e9e06-108">복잡한 쿼리를 실행하는 동안 이들 권장 사항을 수행하여 결과를 신속하게 확인하고 타임아웃을 방지하세요.</span><span class="sxs-lookup"><span data-stu-id="e9e06-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="e9e06-109">새 쿼리를 시도하는 경우에는 항상 `limit`를 사용 하여 매우 큰 결과 집합을 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="e9e06-110">또한 `count`를 사용하여 결과 집합의 크기를 초기에 평가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="e9e06-111">먼저 시간 필터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-111">Use time filters first.</span></span> <span data-ttu-id="e9e06-112">이상적으로는 쿼리를 짝수 일로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="e9e06-113">쿼리의 처음부터 시간 필터 바로 다음에 대부분의 데이터를 제거할 것으로 예상되는 필터를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="e9e06-114">전체 토큰을 찾는 경우 `contains`에서 `has` 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="e9e06-115">모든 열에서 전체 텍스트 검색을 실행하는 대신 특정 열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="e9e06-116">테이블을 합치는 경우 먼저 행 수를 줄인 다음 표를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="e9e06-117">합친 테이블의 필수 열만 `project`합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="e9e06-118">쿼리 성능을 개선하는 방법에 대한 자세한 내용은 [Kusto 쿼리 모범 사례](https://docs.microsoft.com/azure/kusto/query/best-practices)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9e06-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="e9e06-119">쿼리 팁 및 주의 사항</span><span class="sxs-lookup"><span data-stu-id="e9e06-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="e9e06-120">프로세스 ID가 포함된 쿼리</span><span class="sxs-lookup"><span data-stu-id="e9e06-120">Queries with process IDs</span></span>
<span data-ttu-id="e9e06-121">PID(프로세스 ID)는 Windows에서 재활용할 수 있으며 새 프로세스를 위해 다시 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="e9e06-122">즉, 특정 프로세스에 대한 고유 식별자로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="e9e06-123">특정 컴퓨터에서 프로세스에 대한 고유 식별자를 얻으려면 프로세스 생성 시간과 함께 프로세스 ID를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="e9e06-124">프로세스 주변의 데이터를 합치거나 요약할 때는 컴퓨터 식별자에 대한 열 (`DeviceId` 또는 `DeviceName`), 프로세스 ID (`ProcessId` 또는 `InitiatingProcessId`), 프로세스 만들기 시간 (`ProcessCreationTime` 또는 `InitiatingProcessCreationTime`)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="e9e06-125">다음의 예제 쿼리는 포트 445(SMB)를 통해 10 개가 넘는 IP 주소에 액세스하는 프로세스를(잠정적으로 파일 공유를 검색하며) 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="e9e06-126">쿼리 예제:</span><span class="sxs-lookup"><span data-stu-id="e9e06-126">Example query:</span></span>
```
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="e9e06-127">쿼리는 여러 프로세스를 동일한 프로세스 ID와 함께 사용하지 않고 단일 프로세스를 보여주는 `InitiatingProcessId`과 `InitiatingProcessCreationTime` 모두에 대해 요약을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="e9e06-128">명령줄을 사용하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="e9e06-128">Queries with command lines</span></span>

<span data-ttu-id="e9e06-129">명령줄은 다양할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-129">Command lines can vary.</span></span> <span data-ttu-id="e9e06-130">해당하는 경우 파일 이름을 필터링하고 유사 일치를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="e9e06-131">여러 가지 방법으로 작업을 수행할 수 있는 명령줄을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="e9e06-132">예를 들어 공격자는 환경 변수를 사용하거나 따옴표를 사용하여 파일 확장명이 없는 경로가 있거나 없는 이미지 파일을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="e9e06-133">또한 공격자는 매개 변수의 순서를 변경하거나 여러 개의 따옴표와 공백을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="e9e06-134">명령줄을 사용하여 보다 영구적인 쿼리를 만들려면 다음의 방법을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="e9e06-135">명령줄 필드에서 필터링하는 대신 파일 이름 필드에서 검색하여 알려진 프로세스(*net.exe* 또는 *psexec.exe* 등)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="e9e06-136">명령줄 인수에 대해 쿼리할 때 관련이 없는 여러 인수에서 특정 순서로 정확하게 일치하는 항목을 찾지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e9e06-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="e9e06-137">대신 정규 표현식을 사용하거나 별도의 여러 포함 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="e9e06-138">대/소문자를 구분하지 않는 일치 항목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-138">Use case insensitive matches.</span></span> <span data-ttu-id="e9e06-139">예를 들어 `==`, `in`와 `contains_cs` 대신 `=~`, `in~` 그리고 `contains`을 사용합니다. </span><span class="sxs-lookup"><span data-stu-id="e9e06-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="e9e06-140">DOS 명령줄 난독 처리 기법을 완화하려면 따옴표를 제거, 쉼표를 공백으로 대체, 여러 개의 연속되는 공백을 하나의 공백으로 대체할 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="e9e06-141">다른 접근 방법을 필요로 하는 더욱 복잡한 DOS 난독 기법이 있긴 하지만, 이들은 가장 일반적인 문제를 해결하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="e9e06-142">다음의 예제에서는 *net.exe* 파일을 검색 하여 Windows Defender 방화벽 서비스를 중지하는 다양한 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9e06-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="e9e06-143">관련 주제</span><span class="sxs-lookup"><span data-stu-id="e9e06-143">Related topics</span></span>
- [<span data-ttu-id="e9e06-144">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="e9e06-144">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e9e06-145">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="e9e06-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e9e06-146">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="e9e06-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e9e06-147">여러 장치 및 전자 메일에서 위협을 사냥</span><span class="sxs-lookup"><span data-stu-id="e9e06-147">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e9e06-148">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="e9e06-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
