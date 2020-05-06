---
title: 검토 집합에서 데이터 쿼리
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 고급 eDiscovery 사례에서 보다 효율적인 검토를 위해 데이터를 구성 하기 위해 검토 집합에서 쿼리를 만들고 실행 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1bf4d86ea4aecb33cbb2e7ad7b617cd58a5c086d
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034602"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="f64a4-103">검토 집합에서 데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="f64a4-103">Query the data in a review set</span></span>

<span data-ttu-id="f64a4-104">대부분의 경우 검토 집합에서 데이터를 심층적으로 살펴보고 해당 데이터를 구성 하 여 보다 효율적인 검토를 용이 하 게 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="f64a4-105">검토 집합에서 쿼리를 사용 하면 검토 기준을 충족 하는 문서 하위 집합을 중심으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="f64a4-106">검토 집합에서 쿼리 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="f64a4-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="f64a4-107">검토 집합의 문서에 대 한 쿼리를 만들고 실행 하려면 검토 집합에서 **새 쿼리** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-107">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="f64a4-108">쿼리 이름을 지정 하 고 조건을 정의한 후 **저장** 을 클릭 하 여 쿼리를 저장 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-108">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="f64a4-109">이전에 저장 한 쿼리를 실행 하려면 저장 된 쿼리를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-109">To run a query that has been previously saved, click a saved query.</span></span>

![집합 쿼리 검토](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="f64a4-111">검토 집합 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="f64a4-111">Building a review set query</span></span>

<span data-ttu-id="f64a4-112">키워드 조건 카드에 조건 카드와 쿼리 언어의 조합을 사용 하 여 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-112">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="f64a4-113">또한 조건 카드를 블록 ( *조건 그룹*이라고 함)로 그룹화 하 여 좀 더 복잡 한 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-113">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="f64a4-114">검색할 수 있는 메타 데이터 속성의 목록 및 설명에 대 한 자세한 내용은 [Advanced eDiscovery의 문서 메타 데이터 필드](document-metadata-fields-in-Advanced-eDiscovery.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f64a4-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="f64a4-115">조건 카드</span><span class="sxs-lookup"><span data-stu-id="f64a4-115">Condition cards</span></span>

<span data-ttu-id="f64a4-116">검토 집합의 모든 검색 가능 필드에는 쿼리를 작성 하는 데 사용할 수 있는 해당 하는 조건 카드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-116">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="f64a4-117">여러 유형의 조건 카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-117">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="f64a4-118">Freetext: 주제와 같은 텍스트 필드에 freetext 조건 카드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-118">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="f64a4-119">여러 검색 용어를 쉼표로 구분 하 여 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="f64a4-120">날짜: 마지막으로 수정한 날짜와 같은 날짜 필드에 날짜 조건 카드가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-120">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="f64a4-121">검색 옵션: 검색 옵션 조건 카드에는 검토 집합의 특정 필드에 사용할 수 있는 값 목록이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-121">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="f64a4-122">이 속성은 검토 집합에서 가능한 값의 수가 제한 되는 필드 (예: 보낸 사람)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="f64a4-123">키워드: 키워드 조건 카드는 용어를 검색 하거나에서 KQL와 같은 쿼리 언어를 사용 하는 데 사용할 수 있는 freetext 조건 카드의 특정 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-123">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="f64a4-124">자세한 내용은 아래를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f64a4-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="f64a4-125">쿼리 언어</span><span class="sxs-lookup"><span data-stu-id="f64a4-125">Query language</span></span>

<span data-ttu-id="f64a4-126">조건 카드 외에도 키워드 카드에서 KQL 같은 쿼리 언어를 사용 하 여 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-126">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="f64a4-127">검토 집합 쿼리 언어에서는 **AND**, **OR**, **NOT**및 **NEAR**과 같은 표준 부울 연산자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="f64a4-128">또한 단일 문자 와일드 카드 (?) 및 여러 문자 와일드 카드 (\*)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="f64a4-129">필터 사용</span><span class="sxs-lookup"><span data-stu-id="f64a4-129">Using filters</span></span>

<span data-ttu-id="f64a4-130">검토할 수 있는 쿼리 외에도 검토 집합 필터를 사용 하 여 검토 집합 쿼리에 추가 조건을 빠르게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="f64a4-131">이를 통해 검토 집합 쿼리로 표시 되는 결과를 보다 구체화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-131">This helps you further refine the results displayed by a review set query.</span></span>

![집합 필터 검토](../media/AeDReviewSetFilters.png)

<span data-ttu-id="f64a4-133">필터는 다음과 같은 두 가지 중요 한 방식으로 쿼리와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="f64a4-134">필터가 일시적입니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-134">Filters are transient.</span></span> <span data-ttu-id="f64a4-135">기존 세션 보다는 지속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="f64a4-136">즉, 필터를 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="f64a4-137">쿼리가 검토 집합에 저장 되 고 검토 집합을 열 때마다이 쿼리에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="f64a4-138">필터는 항상 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-138">Filters are always additive.</span></span> <span data-ttu-id="f64a4-139">필터는 현재 검토 집합 쿼리와 함께 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="f64a4-140">다른 쿼리를 적용 하면 현재 쿼리에서 반환 된 결과가 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64a4-140">Applying a different query will replace the results returned by the current query.</span></span>
