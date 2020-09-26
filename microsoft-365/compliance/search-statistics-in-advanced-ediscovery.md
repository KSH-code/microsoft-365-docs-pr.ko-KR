---
title: 사전 eDiscovery에서 검색 통계
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 고급 eDiscovery에서 컬렉션 검색을 실행 한 후 생성 되는 통계를 확인 하 여 검색 결과의 유효성을 검사 합니다.
ms.openlocfilehash: ef5653a76d94272ba5f608149648f1421198929a
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286084"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="0634f-103">Advanced eDiscovery의 검색 통계</span><span class="sxs-lookup"><span data-stu-id="0634f-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="0634f-104">검색 결과의 유효성을 검사할 수 있는 한 가지 방법은 결과를 기준으로 통계를 확인 하 여 예상과 일치 하는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="0634f-105">검색이 완료 되 면 검색 세부 정보 플라이 아웃에 높은 수준의 통계가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="0634f-106">검색을 통해 검색 되는 항목의 수 및 볼륨</span><span class="sxs-lookup"><span data-stu-id="0634f-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="0634f-107">검색 위치에서 찾은 부분 인덱스 또는 인덱싱되지 않은 항목의 수 및 볼륨</span><span class="sxs-lookup"><span data-stu-id="0634f-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="0634f-108">검색 된 사서함 및 위치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="0634f-109">자세한 통계를 보려면 검색 세부 정보 플라이 아웃에서 "통계"를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="0634f-110">요약 보기</span><span class="sxs-lookup"><span data-stu-id="0634f-110">Summary view</span></span>

<span data-ttu-id="0634f-111">요약 보기에서 위치 유형 (예: Exchange)을 기준으로 아래로 나누어진 검색 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="0634f-112">각 위치 유형에 대해 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-112">For each location type, you can see:</span></span>

- <span data-ttu-id="0634f-113">검색 조건과 일치 하는 항목이 있는 위치 수</span><span class="sxs-lookup"><span data-stu-id="0634f-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="0634f-114">이 위치에서 검색 조건과 일치 하는 항목의 수</span><span class="sxs-lookup"><span data-stu-id="0634f-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="0634f-115">검색 조건과 일치 하는 항목의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="0634f-116">상위 위치 보기</span><span class="sxs-lookup"><span data-stu-id="0634f-116">Top locations view</span></span>

<span data-ttu-id="0634f-117">최상위 위치 보기에는 가장 일치 하는 개별 위치가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="0634f-118">각 위치에 대해 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-118">For each location, you will see:</span></span>

- <span data-ttu-id="0634f-119">위치 이름 (예: SharePoint URL)</span><span class="sxs-lookup"><span data-stu-id="0634f-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="0634f-120">위치 종류</span><span class="sxs-lookup"><span data-stu-id="0634f-120">Location type</span></span>

- <span data-ttu-id="0634f-121">검색 조건과 일치 하는 항목 수</span><span class="sxs-lookup"><span data-stu-id="0634f-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="0634f-122">검색 조건과 일치 하는 항목의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="0634f-123">쿼리 보기</span><span class="sxs-lookup"><span data-stu-id="0634f-123">Queries view</span></span>

<span data-ttu-id="0634f-124">쿼리에 사용 된 (c:s) 키워드나 키워드 행이 있는 경우 쿼리 결과를 위치 유형별 쿼리 보기로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="0634f-125">각 위치 유형에 대해 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-125">For each location type, you will see:</span></span>

- <span data-ttu-id="0634f-126">파트:이 열에는 "Primary" 또는 "Keyword" 라는 단어가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="0634f-127">"기본"은 행에 전체 쿼리에 대 한 통계가 표시 되는 반면 "Keyword"는 쿼리 구성 요소 중 하나를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="0634f-128">쿼리: 행이 참조 하는 실제 쿼리 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="0634f-129">Part가 "Primary" 이면 전체 쿼리가 됩니다. Part가 "Keyword" 이면 여기에 쿼리 구성 요소 중 하나가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="0634f-130">모든 contentin 사서함을 검색 하는 경우 (키워드를 지정 하지 않음) 실제 쿼리는 (size >= 0)로, 모든 항목이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="0634f-131">SharePoint Online 및 비즈니스용 OneDrive 사이트를 검색 하면 다음과 같은 두 가지 구성 요소가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="0634f-132">NOT IsExternalContent: 1-온-프레미스 SharePoint 조직에서 모든 콘텐츠를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="0634f-133">NOT isOneNotePage: 1-모든 OneNote 파일은 검색 쿼리와 일치 하는 모든 문서와 중복 되므로 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="0634f-134">검색 조건과 일치 하는 항목이 있는 위치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="0634f-135">검색 조건과 일치 하는 이러한 위치에 있는 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="0634f-136">검색 조건과 일치 하는 항목의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0634f-136">Total volume of items that matched the search conditions.</span></span>
