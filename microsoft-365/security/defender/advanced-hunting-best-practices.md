---
title: Microsoft 365 Defender의 고급 헌팅 쿼리 모범 사례
description: 고급 헌팅을 사용하여 빠르고 효율적이며 오류가 없는 위협 헌팅 쿼리를 생성하는 방법을 학습합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema, kusto, 시간 제한 방지, 명령줄, 프로세스 ID, 최적화, 모범 사례, 구문 분석, 가입, 요약
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
ms.openlocfilehash: e0744a01fc599b66f371b01194579f4845ed19fb
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498725"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="d8443-104">고급 헌팅 쿼리 모범 사례</span><span class="sxs-lookup"><span data-stu-id="d8443-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d8443-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d8443-105">**Applies to:**</span></span>
- <span data-ttu-id="d8443-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8443-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d8443-107">이러한 권장 사항을 적용하여 결과를 더 빠르게 얻고 복잡한 쿼리를 실행하는 동안 시간 제한을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="d8443-108">쿼리 성능을 개선하는 방법에 대한 자세한 내용은 [Kusto 쿼리 모범 사례](/azure/kusto/query/best-practices)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8443-108">For more guidance on improving query performance, read [Kusto query best practices](/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="d8443-109">CPU 리소스 할당량 이해</span><span class="sxs-lookup"><span data-stu-id="d8443-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="d8443-110">크기에 따라 각 테넌트는 고급 헌팅 쿼리를 실행하기 위해 할당된 CPU 리소스 집합에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="d8443-111">다양한 서비스 제한에 대한 자세한 내용은 고급 헌팅 할당량 및 사용 매개 변수 를 [참조하세요.](advanced-hunting-limits.md)</span><span class="sxs-lookup"><span data-stu-id="d8443-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="d8443-112">여러 쿼리를 정기적으로 실행하는 고객은 사용을 추적하고 이 문서의 최적화 지침을 적용하여 할당량 또는 사용 매개 변수 초과로 인한 중단을 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="d8443-113">일반 최적화 팁</span><span class="sxs-lookup"><span data-stu-id="d8443-113">General optimization tips</span></span>

- <span data-ttu-id="d8443-114">**새 쿼리** 크기 -쿼리가 큰 결과 집합을 반환하는 것으로 의심되는 경우 먼저 개수 연산자를 사용하여 [평가합니다.](/azure/data-explorer/kusto/query/countoperator)</span><span class="sxs-lookup"><span data-stu-id="d8443-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="d8443-115">제한 [또는](/azure/data-explorer/kusto/query/limitoperator) 동의어를 사용하여 큰 결과 집합을 `take` 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-115">Use [limit](/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="d8443-116">**필터를** 초기에 적용 - 특히 [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)또는 [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction)등의 변환 및 구문 분석 함수를 사용하기 전에 데이터 집합을 줄이기 위해 시간 필터 및 기타 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="d8443-117">아래 예제에서는 필터링 연산자가 레코드 수를 줄인 후 구문 분석 함수 [extractjson()이](/azure/data-explorer/kusto/query/extractjsonfunction) 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-117">In the example below, the parsing function [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="d8443-118">**비트에 포함**- 단어 내에서 하위 스트링을 불필요하게 검색하지 않도록 에는 대신 `has` 연산자를 `contains` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="d8443-119">문자열 연산자에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="d8443-119">Learn about string operators</span></span>](/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="d8443-120">**특정 열을 찾아**-모든 열에서 전체 텍스트 검색을 실행하는 대신 특정 열을 살펴 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="d8443-121">모든 열을 `*` 검사하는 데는 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="d8443-122">**속도에 대한 대소문자** 구분 - 대소문자 구분 검색은 보다 구체적이며 일반적으로 더 많은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="d8443-123">대소문자 구분 [문자열](/azure/data-explorer/kusto/query/datatypes-string-operators)연산자(예: `has_cs` 및)의 `contains_cs` 이름은 일반적으로 로 `_cs` 끝됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-123">Names of case-sensitive [string operators](/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="d8443-124">대신 대소문자 구분 등호 연산자를 사용할 `==` 수 `=~` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="d8443-125">**구문 분석,** 추출 안 하세요 . [](/azure/data-explorer/kusto/query/parseoperator) 가능한 경우 구문 분석 연산자 또는 [parse_json() 같은 구문 분석 함수를 사용하세요.](/azure/data-explorer/kusto/query/parsejsonfunction)</span><span class="sxs-lookup"><span data-stu-id="d8443-125">**Parse, don't extract**—Whenever possible, use the [parse operator](/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="d8443-126">정규식을 사용하는 문자열 `matches regex` [연산자나 extract()](/azure/data-explorer/kusto/query/extractfunction)함수는 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-126">Avoid the `matches regex` string operator or the [extract() function](/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="d8443-127">좀 더 복잡한 시나리오에서는 정규식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="d8443-128">구문 분석 함수에 대한 자세한 내용을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="d8443-129">**식이 아닌** 필터 테이블 - 테이블 열을 필터링할 수 있는 경우 계산된 열에는 필터링하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="d8443-130">**3자 용어** 없음 - 3자 이하의 용어를 사용하여 비교하거나 필터링하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="d8443-131">이러한 용어는 인덱싱되지 않습니다. 이러한 용어와 일치하면 더 많은 리소스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="d8443-132">**선택적으로 프로젝트**- 필요한 열만 투영하여 결과를 보다 쉽게 이해할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="d8443-133">조인 또는 유사한 작업을 [](/azure/data-explorer/kusto/query/joinoperator) 실행하기 전에 특정 열을 투영하면 성능을 개선하는 데도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-133">Projecting specific columns prior to running [join](/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="d8443-134">연산자 `join` 최적화</span><span class="sxs-lookup"><span data-stu-id="d8443-134">Optimize the `join` operator</span></span>
<span data-ttu-id="d8443-135">조인 [연산자는](/azure/data-explorer/kusto/query/joinoperator) 지정된 열의 값과 일치하여 두 테이블의 행을 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-135">The [join operator](/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="d8443-136">다음 팁을 적용하여 이 연산자를 사용하는 쿼리를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="d8443-137">**왼쪽에 작은** 테이블 - 연산자는 조인 문 왼쪽에 있는 테이블의 레코드를 오른쪽의 레코드와 `join` 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="d8443-138">테이블을 왼쪽에 두면 더 적은 수의 레코드를 일치해야 하여 쿼리 속도를 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="d8443-139">아래 표에서는 계정 SID로 연결하기 전에 세 개의 특정 장치만 다루기 위해 왼쪽 테이블을 `DeviceLogonEvents` `IdentityLogonEvents` 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- <span data-ttu-id="d8443-140">**안쪽 조인** 특징 사용 [](/azure/data-explorer/kusto/query/joinoperator#join-flavors) - 오른쪽 표에 일치하는 각 행을 반환하기 전에 왼쪽 표의 기본 조인 특징 또는 내부 [유니크](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) 조인 중복 제거 행을 조인 키로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-140">**Use the inner-join flavor**—The default [join flavor](/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="d8443-141">왼쪽 표에 키 값이 같은 행이 여러 개 있는 경우 해당 행은 중복 제거하여 각 고유 값에 대해 단일 임의의 행을 `join` 남기게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="d8443-142">이 기본 동작은 유용한 정보를 제공할 수 있는 중요한 정보를 왼쪽 표에 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="d8443-143">예를 들어 아래 쿼리는 동일한 첨부 파일이 여러 전자 메일 메시지를 사용하여 전송된 경우에도 특정 첨부 파일이 포함된 전자 메일 하나만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="d8443-144">이 제한을 해결하기 위해 [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) 왼쪽 테이블의 모든 행이 오른쪽에 일치하는 값을 표시하는 것으로 지정하여 내부 조인 형식을 `kind=inner` 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-144">To address this limitation, we apply the [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="d8443-145">**시간 창에서** 레코드에 참가 - 보안 이벤트를 조사할 때 분석가가 같은 기간에 발생하는 관련 이벤트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="d8443-146">또한 사용할 때 동일한 방법을 적용하면 확인할 레코드 수를 줄여 성능이 `join` 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="d8443-147">아래 쿼리는 악성 파일을 수신한 후 30분 이내에 로그온 이벤트를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="d8443-148">**양쪽에** 시간 필터 적용 - 특정 시간 창을 조사하지 않는 경우에도 왼쪽 테이블과 오른쪽 테이블 모두에 시간 필터를 적용하면 레코드 수를 줄이고 성능을 향상시킬 수 `join` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="d8443-149">아래 쿼리는 지난 한 시간의 레코드만 조인할 수 있도록 두 테이블에 `Timestamp > ago(1h)` 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="d8443-150">**성능에 대한 힌트** 사용 - 연산자와 힌트를 사용하여 리소스를 많이 사용하는 작업을 실행하는 경우 백end에 부하를 분산할 `join` 수 있도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="d8443-151">조인 힌트에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="d8443-151">Learn more about join hints</span></span>](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="d8443-152">예를 들어 **[](/azure/data-explorer/kusto/query/shufflequery)** 셔플 힌트는 기수 값이 많은 키(예: 아래 쿼리의 키)를 사용하여 테이블을 조인할 때 쿼리 성능을 `AccountObjectId` 향상시키는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-152">For example, the **[shuffle hint](/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="d8443-153">**[브로드캐스트](/azure/data-explorer/kusto/query/broadcastjoin)** 힌트는 왼쪽 테이블이 작고(최대 100,000개 레코드) 오른쪽 테이블이 매우 큰 경우 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-153">The **[broadcast hint](/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="d8443-154">예를 들어 아래 쿼리는 표의 링크가 포함된 모든 메시지에  특정 제목이 있는 몇 가지 전자 메일에 참가하려고 `EmailUrlInfo` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="d8443-155">연산자 `summarize` 최적화</span><span class="sxs-lookup"><span data-stu-id="d8443-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="d8443-156">요약 [연산자는](/azure/data-explorer/kusto/query/summarizeoperator) 테이블의 내용을 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-156">The [summarize operator](/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="d8443-157">다음 팁을 적용하여 이 연산자를 사용하는 쿼리를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="d8443-158">**고유한 값 찾기**- 일반적으로 반복할 수 있는 고유한 값을 찾는 `summarize` 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="d8443-159">이 값을 사용하여 반복 값이 없는 열을 집계할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="d8443-160">단일 전자 메일이 여러 이벤트의 일부가  될 수 있는 반면, 개별 전자 메일의 네트워크 메시지 ID에는 항상 고유한 보낸 사람 주소가 있기 때문에 아래 예제에서는 효율적이지 `summarize` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="d8443-161">연산자를 으로 쉽게 대체할 수 있습니다. 그러면 더 적은 리소스를 사용하면서 잠재적으로 동일한 결과를 `summarize` `project` 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="d8443-162">다음 예에서는 동일한 받는 사람 주소로 전자 메일을 보내는 보낸 사람 주소의 고유한 인스턴스가 여러 개 있을 수 있기 때문에 보다 효율적으로 `summarize` 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="d8443-163">이러한 조합은 고유하지 않습니다. 중복 항목일 가능성이 뚜렷합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="d8443-164">**쿼리 셔플**-을(를) 반복적인 값을 사용하는 열에 사용하는 것이 가장 좋은 반면 동일한 열에는 기수도 높거나 고유 값이 많이 사용될 `summarize` 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="d8443-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="d8443-165">연산자와 마찬가지로 처리 부하를 분산하고 카디널리티가 높은 열에서 작업할 때 성능을 잠재적으로 개선하기 위해 셔플 힌트를 적용할 `join` 수도 [](/azure/data-explorer/kusto/query/shufflequery) `summarize` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-165">Like the `join` operator, you can also apply the [shuffle hint](/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="d8443-166">아래 쿼리는 수만 개의 대규모 조직에서 실행할 수 있는 고유한 받는 사람 전자 메일 주소의 개수를 `summarize` 계산하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="d8443-167">성능을 향상하기 위해 다음을 `hint.shufflekey` 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="d8443-168">쿼리 시나리오</span><span class="sxs-lookup"><span data-stu-id="d8443-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="d8443-169">프로세스 ID를 사용하여 고유한 프로세스 식별</span><span class="sxs-lookup"><span data-stu-id="d8443-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="d8443-170">PID(프로세스 ID)는 Windows에서 재활용할 수 있으며 새 프로세스를 위해 다시 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="d8443-171">즉, 특정 프로세스에 대한 고유 식별자로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="d8443-172">특정 컴퓨터에서 프로세스에 대한 고유 식별자를 얻으려면 프로세스 생성 시간과 함께 프로세스 ID를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="d8443-173">프로세스 주변의 데이터를 합치거나 요약할 때는 컴퓨터 식별자에 대한 열 (`DeviceId` 또는 `DeviceName`), 프로세스 ID (`ProcessId` 또는 `InitiatingProcessId`), 프로세스 만들기 시간 (`ProcessCreationTime` 또는 `InitiatingProcessCreationTime`)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="d8443-174">다음의 예제 쿼리는 포트 445(SMB)를 통해 10 개가 넘는 IP 주소에 액세스하는 프로세스를(잠정적으로 파일 공유를 검색하며) 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="d8443-175">쿼리 예제:</span><span class="sxs-lookup"><span data-stu-id="d8443-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="d8443-176">쿼리는 여러 프로세스를 동일한 프로세스 ID와 함께 사용하지 않고 단일 프로세스를 보여주는 `InitiatingProcessId`과 `InitiatingProcessCreationTime` 모두에 대해 요약을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="d8443-177">쿼리 명령줄</span><span class="sxs-lookup"><span data-stu-id="d8443-177">Query command lines</span></span>
<span data-ttu-id="d8443-178">여러 가지 방법으로 작업을 수행할 수 있는 명령줄을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="d8443-179">예를 들어 공격자는 파일 확장명 없이 환경 변수를 사용하거나 따옴표를 사용하여 경로 없이 이미지 파일을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="d8443-180">또한 공격자는 매개 변수 순서를 변경하거나 여러 따옴표와 공백을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="d8443-181">명령줄에 대해 지속적 쿼리를 더 많이 만들 수 있는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="d8443-182">명령줄 자체를 필터링하는 대신 \*\* 파일 이름 *필드에* 일치하여 알려진 프로세스(예:net.exe또는psexec.exe)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="d8443-183">parse_command_line 함수를 사용하여 [명령줄 섹션 구문](/azure/data-explorer/kusto/query/parse-command-line) 분석</span><span class="sxs-lookup"><span data-stu-id="d8443-183">Parse command-line sections using the [parse_command_line() function](/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="d8443-184">명령줄 인수에 대해 쿼리할 때 관련이 없는 여러 인수에서 특정 순서로 정확하게 일치하는 항목을 찾지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d8443-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="d8443-185">대신 정규 표현식을 사용하거나 별도의 여러 포함 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="d8443-186">대/소문자를 구분하지 않는 일치 항목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-186">Use case insensitive matches.</span></span> <span data-ttu-id="d8443-187">예를 들어 , 및 대신 `=~` `in~` , `contains` `==` `in` 를 `contains_cs` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="d8443-188">명령줄 난침 기술을 완화하기 위해 따옴표를 제거하고, 콤보를 공백으로 바꾸고, 여러 개의 연속된 공백을 단일 공백으로 바꾸는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="d8443-189">다른 접근 방식이 필요한 더 복잡한 난 난급법이 있지만 이러한 조정을 통해 일반적인 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="d8443-190">다음 예에서는 방화벽 서비스 "MpsSvc"를net.exe파일을 검색하는 쿼리를 생성하는 다양한 방법을 보여집니다. </span><span class="sxs-lookup"><span data-stu-id="d8443-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="d8443-191">외부 원본에서 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="d8443-191">Ingest data from external sources</span></span>
<span data-ttu-id="d8443-192">긴 목록이나 큰 테이블을 쿼리에 통합하기 위해 [externaldata](/azure/data-explorer/kusto/query/externaldata-operator) 연산자를 사용하여 지정된 URI에서 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-192">To incorporate long lists or large tables into your query, use the [externaldata operator](/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="d8443-193">TXT, CSV, JSON 또는 기타 형식의 파일에서 데이터를 얻을 [수 있습니다.](/azure/data-explorer/ingestion-supported-formats)</span><span class="sxs-lookup"><span data-stu-id="d8443-193">You can get data from files in TXT, CSV, JSON, or [other formats](/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="d8443-194">아래 예제에서는 MalwareBazaar(abuse.ch)에서 제공하는 맬웨어 SHA-256 해시의 광범위한 목록을 사용하여 전자 메일의 첨부 파일을 검사하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a><span data-ttu-id="d8443-195">문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="d8443-195">Parse strings</span></span>
<span data-ttu-id="d8443-196">구문 분석 또는 변환이 필요한 문자열을 효율적으로 처리하는 데 사용할 수 있는 다양한 함수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="d8443-197">문자열</span><span class="sxs-lookup"><span data-stu-id="d8443-197">String</span></span> | <span data-ttu-id="d8443-198">함수</span><span class="sxs-lookup"><span data-stu-id="d8443-198">Function</span></span> | <span data-ttu-id="d8443-199">사용 예제</span><span class="sxs-lookup"><span data-stu-id="d8443-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="d8443-200">명령줄</span><span class="sxs-lookup"><span data-stu-id="d8443-200">Command-lines</span></span> | [<span data-ttu-id="d8443-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="d8443-201">parse_command_line()</span></span>](/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="d8443-202">명령과 모든 인수를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="d8443-203">경로</span><span class="sxs-lookup"><span data-stu-id="d8443-203">Paths</span></span> | [<span data-ttu-id="d8443-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="d8443-204">parse_path()</span></span>](/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="d8443-205">파일 또는 폴더 경로의 섹션을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="d8443-206">버전 번호</span><span class="sxs-lookup"><span data-stu-id="d8443-206">Version numbers</span></span> | [<span data-ttu-id="d8443-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="d8443-207">parse_version()</span></span>](/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="d8443-208">섹션당 최대 4개의 섹션과 섹션당 최대 8자까지 버전 번호를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="d8443-209">구문 분석된 데이터를 사용하여 버전 나이를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="d8443-210">IPv4 주소</span><span class="sxs-lookup"><span data-stu-id="d8443-210">IPv4 addresses</span></span> | [<span data-ttu-id="d8443-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="d8443-211">parse_ipv4()</span></span>](/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="d8443-212">IPv4 주소를 긴 정수로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="d8443-213">IPv4 주소를 변환하지 않고 비교하기 위해 [ipv4_compare() 를 사용합니다.](/azure/data-explorer/kusto/query/ipv4-comparefunction)</span><span class="sxs-lookup"><span data-stu-id="d8443-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="d8443-214">IPv6 주소</span><span class="sxs-lookup"><span data-stu-id="d8443-214">IPv6 addresses</span></span> | [<span data-ttu-id="d8443-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="d8443-215">parse_ipv6()</span></span>](/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="d8443-216">IPv4 또는 IPv6 주소를 정형 IPv6로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8443-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="d8443-217">IPv6 주소를 비교하기 위해 [ipv6_compare() 를 사용합니다.](/azure/data-explorer/kusto/query/ipv6-comparefunction)</span><span class="sxs-lookup"><span data-stu-id="d8443-217">To compare IPv6 addresses, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="d8443-218">지원되는 모든 구문 분석 함수에 대한 자세한 내용은 [Kusto 문자열 함수 를 읽어 보아야 합니다.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions)</span><span class="sxs-lookup"><span data-stu-id="d8443-218">To learn about all supported parsing functions, [read about Kusto string functions](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d8443-219">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d8443-219">Related topics</span></span>
- [<span data-ttu-id="d8443-220">Kusto 쿼리 언어 설명서</span><span class="sxs-lookup"><span data-stu-id="d8443-220">Kusto query language documentation</span></span>](/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="d8443-221">할당량 및 사용량 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8443-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="d8443-222">고급 헌팅 오류 처리</span><span class="sxs-lookup"><span data-stu-id="d8443-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="d8443-223">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="d8443-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d8443-224">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="d8443-224">Learn the query language</span></span>](advanced-hunting-query-language.md)