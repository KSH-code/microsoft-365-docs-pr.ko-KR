---
title: 검토 집합에서 데이터 쿼리
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 검토 집합에서 쿼리를 만들고 실행하여 검토 사례에서 보다 효율적인 검토를 위해 데이터를 구성하는 Advanced eDiscovery 대해 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345803"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="55f2d-103">검토 집합에서 데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="55f2d-103">Query the data in a review set</span></span>

<span data-ttu-id="55f2d-104">대부분의 경우 검토 집합의 데이터를 더 깊이 파고들고 보다 효율적인 검토를 위해 데이터를 구성할 수 있는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="55f2d-105">검토 집합에서 쿼리를 사용하면 검토 조건을 충족하는 문서의 하위 집합에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="55f2d-106">검토 집합에서 쿼리 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="55f2d-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="55f2d-107">검토 집합의 문서에 대한 쿼리를 만들고 실행하려면 검토 집합에서 새 쿼리를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="55f2d-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="55f2d-108">쿼리 이름을 지정하고 조건을 정의한  후 저장을 선택하여 쿼리를 저장하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="55f2d-109">이전에 저장한 쿼리를 실행하려면 저장된 쿼리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-109">To run a query that has been previously saved, select a saved query.</span></span>

![쿼리 집합 검토](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="55f2d-111">검토 집합 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="55f2d-111">Building a review set query</span></span>

<span data-ttu-id="55f2d-112">키워드 조건에서 키워드, 속성 및 조건의 조합을 사용하여 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="55f2d-113">더 복잡한 쿼리를 작성하기 위해 조건을 블록(조건 그룹)으로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="55f2d-114">검색할 수 있는 메타데이터 속성의 목록 및 설명은 [Advanced eDiscovery의 문서 메타데이터 필드](document-metadata-fields-in-Advanced-eDiscovery.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55f2d-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="55f2d-115">조건</span><span class="sxs-lookup"><span data-stu-id="55f2d-115">Conditions</span></span>

<span data-ttu-id="55f2d-116">검토 집합의 모든 검색 가능한 필드에는 쿼리를 작성하는 데 사용할 수 있는 해당 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="55f2d-117">조건에는 여러 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="55f2d-118">Freetext: 자유 텍스트 조건은 제목과 같은 텍스트 필드에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="55f2d-119">여러 검색 용어를 콤보로 구분하여 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="55f2d-120">날짜: 마지막으로 수정한 날짜와 같은 날짜 필드에 날짜 조건이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="55f2d-121">검색 옵션: 검색 옵션 조건은 검토 집합의 특정 필드에 대해 가능한 값 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="55f2d-122">검토 집합에 가능한 값이 유한한 수의 보낸 사람 등의 필드에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="55f2d-123">키워드: 키워드 조건은 용어를 검색하거나 KQL과 같은 쿼리 언어를 사용하는 데 사용할 수 있는 자유형 조건의 특정 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="55f2d-124">자세한 내용은 아래를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55f2d-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="55f2d-125">쿼리 언어</span><span class="sxs-lookup"><span data-stu-id="55f2d-125">Query language</span></span>

<span data-ttu-id="55f2d-126">조건 외에도 키워드 조건에서 KQL과 같은 쿼리 언어를 사용하여 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="55f2d-127">검토 집합 쿼리의 쿼리 언어는 **AND**, **OR,** **NOT** 및 NEAR 등의 표준 부울 연산자를 **지원합니다.**</span><span class="sxs-lookup"><span data-stu-id="55f2d-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="55f2d-128">또한 단일 문자 와일드카드(?) 및 다중 문자 와일드카드(\*)도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="55f2d-129">필터</span><span class="sxs-lookup"><span data-stu-id="55f2d-129">Filters</span></span>

<span data-ttu-id="55f2d-130">저장할 수 있는 쿼리 외에도 검토 집합 필터를 사용하여 검토 집합 쿼리에 추가 조건을 신속하게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="55f2d-131">필터를 사용하면 검토 집합 쿼리에 의해 표시되는 결과를 보다 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![필터 집합 검토](../media/AeDReviewSetFilters.png)

<span data-ttu-id="55f2d-133">필터는 두 가지 중요한 방식으로 쿼리와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="55f2d-134">필터는 일시적입니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-134">Filters are transient.</span></span> <span data-ttu-id="55f2d-135">기존 세션을 넘어도 지속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="55f2d-136">즉, 필터를 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="55f2d-137">쿼리는 검토 집합에 저장되고 검토 집합을 열 때마다 해당 쿼리에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-137">Queries are saved to the review set, and access them whenever you open the review set.</span></span>

- <span data-ttu-id="55f2d-138">필터는 항상 가산됩니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-138">Filters are always additive.</span></span> <span data-ttu-id="55f2d-139">필터는 현재 검토 집합 쿼리와 함께 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="55f2d-140">다른 쿼리를 적용하면 현재 쿼리에서 반환된 결과가 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="55f2d-140">Applying a different query will replace the results returned by the current query.</span></span>
