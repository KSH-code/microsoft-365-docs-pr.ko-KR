---
title: Microsoft Threat Protection의 고급 헌팅 개요
description: Microsoft 365의 고급 검색 쿼리와 이를 사용하여 네트워크의 위협과 약점을 사전에 찾는 방법에 대해 알아보세요.
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 검색, 스키마, kusto, microsoft 365 및 microsoft Threat Protection
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
ms.openlocfilehash: 7e96ca06a7b77a6bdc0cf4af55d519aebda833cd
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600385"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="e0cd8-104">Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응</span><span class="sxs-lookup"><span data-stu-id="e0cd8-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="e0cd8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e0cd8-105">**Applies to:**</span></span>
- <span data-ttu-id="e0cd8-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="e0cd8-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e0cd8-107">고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="e0cd8-108">네트워크의 이벤트를 사전에 검사하여 흥미로운 지표와 엔티티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="e0cd8-109">데이터에 대한 유연한 액세스는 알려진 위협과 잠재적 위협 모두에 대한 제한없는 헌팅을 용이하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="e0cd8-110">Microsoft 365 보안 센터에서 고급 구하기는 전자 메일의 데이터를 제공 하 여 Microsoft Defender ATP, 등록 장치 및 Office 365 ATP의 데이터를 조회 하는 쿼리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-110">In the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="e0cd8-111">고급 헌팅을 사용하려면 [Microsoft Threat Protection](mtp-enable.md)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="e0cd8-112">고급 헌팅 시작</span><span class="sxs-lookup"><span data-stu-id="e0cd8-112">Get started with advanced hunting</span></span>

<span data-ttu-id="e0cd8-113">고급 헌팅을 빠르게 시작하고 실행하려면 몇가지 단계를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="e0cd8-114">학습 목표</span><span class="sxs-lookup"><span data-stu-id="e0cd8-114">Learning goal</span></span> | <span data-ttu-id="e0cd8-115">설명</span><span class="sxs-lookup"><span data-stu-id="e0cd8-115">Description</span></span> | <span data-ttu-id="e0cd8-116">리소스</span><span class="sxs-lookup"><span data-stu-id="e0cd8-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="e0cd8-117">**언어에 대한 느낌을 받아보세요.**</span><span class="sxs-lookup"><span data-stu-id="e0cd8-117">**Get a feel for the language**</span></span> | <span data-ttu-id="e0cd8-118">고급 헌팅은 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)을 기반으로 하며, 동일한 구문 및 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="e0cd8-119">첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="e0cd8-120">쿼리 언어 개요</span><span class="sxs-lookup"><span data-stu-id="e0cd8-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="e0cd8-121">**스키마의 이해**</span><span class="sxs-lookup"><span data-stu-id="e0cd8-121">**Understand the schema**</span></span> | <span data-ttu-id="e0cd8-122">스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="e0cd8-123">이는 데이터를 찾을 위치와 쿼리를 구성하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="e0cd8-124">스키마 참조</span><span class="sxs-lookup"><span data-stu-id="e0cd8-124">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="e0cd8-125">**미리 정의된 쿼리 사용**</span><span class="sxs-lookup"><span data-stu-id="e0cd8-125">**Use predefined queries**</span></span> | <span data-ttu-id="e0cd8-126">다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="e0cd8-127">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="e0cd8-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="e0cd8-128">**쿼리 최적화**</span><span class="sxs-lookup"><span data-stu-id="e0cd8-128">**Optimize queries**</span></span> | <span data-ttu-id="e0cd8-129">전자 메일 및 장치에서 데이터를 결합하는 효율적인 쿼리 및 쿼리를 만드는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="e0cd8-130">[쿼리 모범 사례](advanced-hunting-shared-queries.md), [여러 장치 및 전자 메일에서 헌팅](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="e0cd8-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="e0cd8-131">쿼리 작성시 도움말 보기</span><span class="sxs-lookup"><span data-stu-id="e0cd8-131">Get help as you write queries</span></span>
<span data-ttu-id="e0cd8-132">다음 기능을 활용하여 쿼리를 더 빠르게 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="e0cd8-133">**자동 제안** — 쿼리를 작성할 때 고급 헌팅에서 제안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="e0cd8-134">**스키마 참조** — 테이블 및 해당 열 목록이 포함된 스키마 참조가 작업 영역 옆에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="e0cd8-135">자세한 내용을 보려면 항목 위로 마우스를 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-135">For more information, hover over an item.</span></span> <span data-ttu-id="e0cd8-136">항목을 두 번 클릭하여 쿼리 편집기에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="e0cd8-137">쿼리 결과에서 드릴 다운</span><span class="sxs-lookup"><span data-stu-id="e0cd8-137">Drilldown from query results</span></span>
<span data-ttu-id="e0cd8-138">쿼리 결과에서 컴퓨터, 파일, 사용자, IP 주소 및 URL과 같은 엔터티에 대한 자세한 정보를 보려면 엔터티 식별자를 클릭하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="e0cd8-139">그러면 Microsoft Defender 보안 센터에서 선택한 엔터티에 대한 자세한 프로필 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="e0cd8-140">결과에서 쿼리 조정</span><span class="sxs-lookup"><span data-stu-id="e0cd8-140">Tweak your queries from the results</span></span>
<span data-ttu-id="e0cd8-141">결과 집합의 값을 마우스 오른쪽 단추로 클릭하면 쿼리가 빠르게 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="e0cd8-142">옵션을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-142">You can use the options to:</span></span>

- <span data-ttu-id="e0cd8-143">선택한 값을 명시적으로 찾습니다 (`==`)</span><span class="sxs-lookup"><span data-stu-id="e0cd8-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="e0cd8-144">쿼리에서 선택한 값을 제외합니다 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="e0cd8-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="e0cd8-145">쿼리에 값을 추가하는 고급 연산자를 사용합니다 (예: `contains`, `starts with` 및 `ends with`)</span><span class="sxs-lookup"><span data-stu-id="e0cd8-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Microsoft Defender ATP 고급 헌팅 결과 집합 이미지](../images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="e0cd8-147">쿼리 결과 필터링</span><span class="sxs-lookup"><span data-stu-id="e0cd8-147">Filter the query results</span></span>
<span data-ttu-id="e0cd8-148">오른쪽에 표시되는 필터는 결과 집합에 대한 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="e0cd8-149">각 열에는 해당 열에 대해 발견된 고유 값과 인스턴스 수를 나열하는 자체적인 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="e0cd8-150">포함하거나 제외하려는 값에서 "+" 또는 "-" 단추를 선택한 다음 **쿼리 실행**을 선택하여 쿼리를 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![고급 헌팅 필터 이미지](../images/advanced-hunting-filter.png)

<span data-ttu-id="e0cd8-152">필터를 적용하여 쿼리를 수정한 다음 쿼리를 실행하면 그에 따라 결과가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cd8-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0cd8-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e0cd8-153">Related topics</span></span>
- [<span data-ttu-id="e0cd8-154">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="e0cd8-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e0cd8-155">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="e0cd8-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e0cd8-156">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="e0cd8-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e0cd8-157">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="e0cd8-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e0cd8-158">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="e0cd8-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)