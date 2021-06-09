---
title: 검색 쿼리를 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: 키워드 및 조건을 사용하여 검색 범위 내에서 데이터를 검색할 Advanced eDiscovery 범위를 Microsoft 365.
ms.openlocfilehash: e0df319257776d3995a4b8e37781d7b5dad54d82
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838488"
---
# <a name="build-search-queries-for-collections-in-advanced-ediscovery"></a><span data-ttu-id="96f45-103">2013에서 컬렉션에 대한 검색 쿼리를 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="96f45-103">Build search queries for collections in Advanced eDiscovery</span></span>

<span data-ttu-id="96f45-104">Advanced eDiscovery 사례에서 컬렉션을 만들 [](collections-overview.md) 때 검색 쿼리를 구성할 때 키워드를 사용하여 특정 콘텐츠 및 조건을 검색하여 법적 조사와 가장 관련이 있는 항목을 반환하도록 검색 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-104">When configuring the search query when creating a [collection](collections-overview.md) in an Advanced eDiscovery case, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your legal investigation.</span></span>

![키워드 및 조건을 사용하여 검색 결과 좁히기](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="96f45-106">키워드 검색</span><span class="sxs-lookup"><span data-stu-id="96f45-106">Keyword searches</span></span>

<span data-ttu-id="96f45-107">검색 쿼리의 키워드  상자에 키워드 쿼리를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="96f45-108">키워드, 전자 메일 메시지 속성(예: 보낸 날짜 및 받은 날짜) 또는 문서 속성(예: 파일 이름 또는 문서가 마지막으로 변경된 날짜)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="96f45-109">**AND**, **OR**, **NOT**, **NEAR** 와 같은 부울 연산자를 사용하는 좀 더 복잡한 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="96f45-110">또한 전자 메일 메시지에 없는 SharePoint 및 OneDrive 문서에서 중요한 정보(예: 주민 등록 번호)를 검색하거나 외부에서 공유된 문서를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="96f45-111">**키워드** 상자를 비워 두면 콘텐츠 위치에 있는 모든 콘텐츠가 검색 결과에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-111">If you leave the **Keywords** box empty, all content located in the specified content locations is in the search results.</span></span>

## <a name="keyword-list"></a><span data-ttu-id="96f45-112">키워드 목록</span><span class="sxs-lookup"><span data-stu-id="96f45-112">Keyword list</span></span>

<span data-ttu-id="96f45-113">또는 키워드 목록 표시  확인란을 선택하고 각 행에 키워드 또는 키워드 구를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-113">Alternatively, you can select the **Show keyword list** check box and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="96f45-114">각 행의 키워드는 작성된 검색 쿼리의 **OR** 연산자와 기능상 유사한 논리 연산자(검색 쿼리 구문에서 *c:s로* 표시)에 의해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-114">The keywords in each row are connected by a logical operator (which is represented as *c:s* in the search query syntax) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="96f45-115">즉, 행에 키워드가 포함된 항목이 검색 결과에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-115">This means items that contain any keyword in any row are in the search results.</span></span> <span data-ttu-id="96f45-116">검색 쿼리의 키워드 목록에 최대 180개 행을 추가할 Advanced eDiscovery 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-116">You can add up to 180 rows in the keyword list in Advanced eDiscovery search queries.</span></span>

![키워드 목록을 사용하여 쿼리의 각 키워드에 대한 통계를 얻습니다.](../media/KeywordListSearch.png)

<span data-ttu-id="96f45-118">키워드 목록을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="96f45-118">Why use the keyword list?</span></span> <span data-ttu-id="96f45-119">키워드 목록의 각 키워드와 일치하는 항목 수를 표시하는 통계를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-119">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="96f45-120">이를 통해 가장 효과적이고 가장 효과적인 키워드를 빠르게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-120">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="96f45-121">키워드 목록의 행에 키워드 구(괄호로 둘러싸인)를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-121">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="96f45-122">검색 통계에 대한 자세한 내용은 [검색 통계를 참조하세요.](search-statistics-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="96f45-122">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="96f45-123">조건</span><span class="sxs-lookup"><span data-stu-id="96f45-123">Conditions</span></span>

<span data-ttu-id="96f45-124">검색 조건을 추가하여 검색 범위를 좁히고 보다 구체화된 결과 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-124">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="96f45-125">각 조건은 검색을 시작할 때 생성 및 실행되는 검색 쿼리에 절을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-125">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="96f45-126">조건은 **AND** 연산자와 기능상 유사한 논리 연산자(검색 쿼리 구문에서 *c:c로* 표시)에 의해 키워드 상자에 지정된 키워드 쿼리에 논리적으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-126">A condition is logically connected to the keyword query specified in the keyword box by a logical operator (which is represented as *c:c* in the search query syntax) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="96f45-127">즉, 항목은 키워드 쿼리와 검색 결과에 포함되는 하나 이상의 조건을 모두 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-127">That means items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="96f45-128">이 방법을 통해 결과를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f45-128">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="96f45-129">검색 쿼리에 사용할 수 있는 조건 목록 및 설명은 키워드 쿼리 및 검색 조건의 "검색 조건" [섹션을 참조하세요.](keyword-queries-and-search-conditions.md#search-conditions)</span><span class="sxs-lookup"><span data-stu-id="96f45-129">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
