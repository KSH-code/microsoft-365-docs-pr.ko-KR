---
title: Advance eDiscovery의 검색 통계
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Advanced eDiscovery에서 컬렉션 검색을 실행한 후 생성되는 통계를 확인하여 검색 결과의 유효성을 검사합니다.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750779"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="320b9-103">Advanced eDiscovery의 검색 통계</span><span class="sxs-lookup"><span data-stu-id="320b9-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="320b9-104">검색 결과의 유효성을 검사할 수 있는 한 가지 방법은 결과와 관련한 통계를 확인하여 예상 결과에 맞게 조정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="320b9-105">검색이 완료되면 검색 세부 정보 플라이아웃에 높은 수준의 통계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="320b9-106">검색에 의해 검색된 항목의 수 및 볼륨</span><span class="sxs-lookup"><span data-stu-id="320b9-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="320b9-107">검색 위치에서 발견된 부분적으로 인덱싱되거나 인덱싱되지 않은 항목의 수 및 볼륨</span><span class="sxs-lookup"><span data-stu-id="320b9-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="320b9-108">검색된 사서함 및 위치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="320b9-109">자세한 통계를 보려면 검색 세부 정보 플라이아웃에서 "통계"를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="320b9-110">요약 보기</span><span class="sxs-lookup"><span data-stu-id="320b9-110">Summary view</span></span>

<span data-ttu-id="320b9-111">요약 보기에서 위치 유형(예: Exchange)별로 검색 결과를 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="320b9-112">각 위치 유형에 대해 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-112">For each location type, you can see:</span></span>

- <span data-ttu-id="320b9-113">검색 조건과 일치하는 항목이 있는 위치 수</span><span class="sxs-lookup"><span data-stu-id="320b9-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="320b9-114">검색 조건과 일치하는 위치의 항목 수</span><span class="sxs-lookup"><span data-stu-id="320b9-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="320b9-115">검색 조건과 일치하는 총 항목 볼륨입니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="320b9-116">위쪽 위치 보기</span><span class="sxs-lookup"><span data-stu-id="320b9-116">Top locations view</span></span>

<span data-ttu-id="320b9-117">위쪽 위치 보기에서는 일치하는 위치가 가장 많은 개별 위치를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="320b9-118">각 위치에 대해 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-118">For each location, you will see:</span></span>

- <span data-ttu-id="320b9-119">위치 이름(예: SharePoint URL)</span><span class="sxs-lookup"><span data-stu-id="320b9-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="320b9-120">위치 종류</span><span class="sxs-lookup"><span data-stu-id="320b9-120">Location type</span></span>

- <span data-ttu-id="320b9-121">검색 조건과 일치하는 항목 수</span><span class="sxs-lookup"><span data-stu-id="320b9-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="320b9-122">검색 조건과 일치하는 총 항목 볼륨입니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="320b9-123">쿼리 보기</span><span class="sxs-lookup"><span data-stu-id="320b9-123">Queries view</span></span>

<span data-ttu-id="320b9-124">쿼리에서 (c:s) 키워드 또는 키워드 행을 사용한 경우 위치 유형별 쿼리 보기에서 쿼리 분석 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="320b9-125">각 위치 유형에 대해 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-125">For each location type, you will see:</span></span>

- <span data-ttu-id="320b9-126">파트: 이 열에는 "Primary" 또는 "Keyword"라는 단어가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="320b9-127">"기본"은 행이 전체 쿼리에 통계를 제시하는 반면 " Keyword"는 쿼리 구성 요소 중 하나를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="320b9-128">쿼리: 행이 참조하는 실제 쿼리 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="320b9-129">Part이 "Primary"이면 전체 쿼리가 됩니다. 파트가 "키워드"이면 여기에 쿼리 구성 요소 중 하나를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="320b9-130">키워드를 지정하지 않으면서 모든 콘텐츠 콘텐츠 사서함을 검색할 때 모든 항목이 반환될 수 있도록 실제 쿼리(크기 >= 0)가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="320b9-131">SharePoint Online 및 비즈니스용 OneDrive 사이트를 검색하면 다음 두 구성 요소가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="320b9-132">NOT IsExternalContent:1 - On-premises SharePoint 조직에서 콘텐츠를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="320b9-133">NOT isOneNotePage: 1 - 검색 쿼리와 일치하는 모든 문서의 복제본이기 때문에 모든 OneNote 파일을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="320b9-134">검색 조건과 일치하는 항목이 있는 위치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="320b9-135">검색 조건과 일치하는 이러한 위치의 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="320b9-136">검색 조건과 일치하는 총 항목 볼륨입니다.</span><span class="sxs-lookup"><span data-stu-id="320b9-136">Total volume of items that matched the search conditions.</span></span>
