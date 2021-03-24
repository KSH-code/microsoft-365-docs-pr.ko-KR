---
title: 고급 헌팅을 위한 쿼리 모범 사례
description: 고급 헌팅을 사용할 때 빠르고 효과적 이며 오류가 없는 위협 헌팅 쿼리를 작성하는 방법을 알아보세요.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, kusto, 시간 제한 방지, 명령줄, 프로세스 ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6259ac1c5804b244c825a1bb54401640fdefaf34
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072431"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="740bb-104">고급 헌팅 쿼리 모범 사례</span><span class="sxs-lookup"><span data-stu-id="740bb-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="740bb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="740bb-105">**Applies to:**</span></span>
- [<span data-ttu-id="740bb-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="740bb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="740bb-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="740bb-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="740bb-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="740bb-109">쿼리 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="740bb-109">Optimize query performance</span></span>

<span data-ttu-id="740bb-110">이러한 권장 사항을 적용하여 결과를 더 빠르게 얻고 복잡한 쿼리를 실행하는 동안 시간 제한을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="740bb-111">새 쿼리를 시도하는 경우에는 항상 `limit`를 사용 하여 매우 큰 결과 집합을 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="740bb-112">또한 `count`를 사용하여 결과 집합의 크기를 초기에 평가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="740bb-113">먼저 시간 필터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-113">Use time filters first.</span></span> <span data-ttu-id="740bb-114">이상적으로는 쿼리를 7일로 제한하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="740bb-115">쿼리의 처음부터 시간 필터 바로 다음에 대부분의 데이터를 제거할 것으로 예상되는 필터를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="740bb-116">전체 토큰을 찾는 경우 `contains`에서 `has` 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="740bb-117">모든 열에서 전체 텍스트 검색을 실행하는 대신 특정 열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="740bb-118">테이블을 합치는 경우 먼저 행 수를 줄인 다음 표를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="740bb-119">합친 테이블의 필수 열만 `project`합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="740bb-120">쿼리 성능을 개선하는 방법에 대한 자세한 내용은 [Kusto 쿼리 모범 사례](https://docs.microsoft.com/azure/kusto/query/best-practices)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="740bb-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="740bb-121">쿼리 팁 및 주의 사항</span><span class="sxs-lookup"><span data-stu-id="740bb-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="740bb-122">프로세스 ID가 포함된 쿼리</span><span class="sxs-lookup"><span data-stu-id="740bb-122">Queries with process IDs</span></span>

<span data-ttu-id="740bb-123">PID(프로세스 ID)는 Windows에서 재활용할 수 있으며 새 프로세스를 위해 다시 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="740bb-124">즉, 특정 프로세스에 대한 고유 식별자로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="740bb-125">특정 장치에서 프로세스의 고유 식별자를 얻습니다. 프로세스 생성 시간과 함께 프로세스 ID를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="740bb-126">프로세스에 대한 데이터를 조인하거나 요약할 때 장치 식별자(또는 ), 프로세스 ID( 또는 ) 및 프로세스 생성 시간(또는 )에 대한 `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` 열을 `ProcessCreationTime` 포함합니다. `InitiatingProcessCreationTime`</span><span class="sxs-lookup"><span data-stu-id="740bb-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="740bb-127">다음의 예제 쿼리는 포트 445(SMB)를 통해 10 개가 넘는 IP 주소에 액세스하는 프로세스를(잠정적으로 파일 공유를 검색하며) 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="740bb-128">쿼리는 여러 프로세스를 동일한 프로세스 ID와 함께 사용하지 않고 단일 프로세스를 보여주는 `InitiatingProcessId`과 `InitiatingProcessCreationTime` 모두에 대해 요약을 합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="740bb-129">명령줄을 사용하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="740bb-129">Queries with command lines</span></span>

<span data-ttu-id="740bb-130">명령줄은 다양할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-130">Command lines can vary.</span></span> <span data-ttu-id="740bb-131">해당하는 경우 파일 이름을 필터링하고 유사 일치를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="740bb-132">여러 가지 방법으로 작업을 수행할 수 있는 명령줄을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="740bb-133">예를 들어 공격자는 환경 변수를 사용하거나 따옴표를 사용하여 파일 확장명이 없는 경로가 있거나 없는 이미지 파일을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="740bb-134">또한 공격자는 매개 변수의 순서를 변경하거나 여러 개의 따옴표와 공백을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="740bb-135">명령줄을 사용하여 보다 영구적인 쿼리를 만들려면 다음의 방법을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="740bb-136">명령줄 필드에서 필터링하는 대신 파일 이름 필드에서 검색하여 알려진 프로세스(*net.exe* 또는 *psexec.exe* 등)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="740bb-137">명령줄 인수에 대해 쿼리할 때 관련이 없는 여러 인수에서 특정 순서로 정확하게 일치하는 항목을 찾지 마세요.</span><span class="sxs-lookup"><span data-stu-id="740bb-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="740bb-138">대신 정규 표현식을 사용하거나 별도의 여러 포함 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="740bb-139">대/소문자를 구분하지 않는 일치 항목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-139">Use case insensitive matches.</span></span> <span data-ttu-id="740bb-140">예를 들어 , 및 대신 `=~` `in~` `contains` `==` 를 `in` 사용합니다. `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="740bb-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="740bb-141">DOS 명령줄 난독 처리 기법을 완화하려면 따옴표를 제거, 쉼표를 공백으로 대체, 여러 개의 연속되는 공백을 하나의 공백으로 대체할 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="740bb-142">다른 접근 방법을 필요로 하는 더욱 복잡한 DOS 난독 기법이 있긴 하지만, 이들은 가장 일반적인 문제를 해결하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="740bb-143">다음의 예제에서는 *net.exe* 파일을 검색 하여 Windows Defender 방화벽 서비스를 중지하는 다양한 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
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

> <span data-ttu-id="740bb-144">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="740bb-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="740bb-145">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="740bb-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="740bb-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="740bb-146">Related topics</span></span>

- [<span data-ttu-id="740bb-147">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="740bb-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="740bb-148">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="740bb-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="740bb-149">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="740bb-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="740bb-150">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="740bb-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="740bb-151">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="740bb-151">Custom detections overview</span></span>](overview-custom-detections.md)
