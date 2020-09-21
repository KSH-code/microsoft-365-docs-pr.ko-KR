---
title: Advanced eDiscovery에서 사례에 대 한 데이터 수집
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
description: 고급 eDiscovery의 검색 도구를 사용 하 여 검토를 위해 검토할 문서 집합을 식별 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-2020
ms.openlocfilehash: 725c289324a8e4d5bd4d7a7b9ddd9e091b6d6241
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956201"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="6fcf8-103">Advanced eDiscovery에서 사례에 대 한 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="6fcf8-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="6fcf8-104">해당 사례에 관심이 있는 custodians 및 데이터 원본을 식별 한 후에는 delve에 사용할 문서 집합을 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="6fcf8-105">고급 eDiscovery의 검색 도구를 사용 하 여 Microsoft 365의 custodial 및 비 custodial 위치에서 관련 문서를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="6fcf8-106">검색을 실행 한 후 검색 쿼리와 일치 하는 항목이 가장 많은 위치와 같은 검색 된 항목에 대 한 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="6fcf8-107">또한 결과의 하위 집합을 미리 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="6fcf8-108">추가로 확인할 문서 집합을 식별 한 경우 수집 및 처리할 검토 집합에 검색 결과를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="6fcf8-109">검색 만들기</span><span class="sxs-lookup"><span data-stu-id="6fcf8-109">Create a search</span></span>

<span data-ttu-id="6fcf8-110">**검색 탭에서** **새 검색** 을 선택 하는 마법사를 시작 하 여 search를 만드는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="6fcf8-111">검색을 만드는 방법에 대 한 자세한 내용은 [create a search를 검색 하 여 데이터 수집](create-search-to-collect-data.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="6fcf8-112">검색을 만든 후에는 세부 정보가 포함 된 플라이 아웃 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="6fcf8-113">검색이 아직 완료 되지 않았으므로 **통계** 및 **미리 보기** 단추가 처음에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="6fcf8-114">검색의 진행 상태를 추적할 수 있습니다 ( **검색 탭)** .</span><span class="sxs-lookup"><span data-stu-id="6fcf8-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="6fcf8-115">검색 결과 및 통계 보기</span><span class="sxs-lookup"><span data-stu-id="6fcf8-115">View search results and statistics</span></span>

<span data-ttu-id="6fcf8-116">콘텐츠 검색에는 통계 (예측) 및 미리 보기의 두 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="6fcf8-117">이러한 각 구성 요소가 완료 되 면 **검색** 탭의 해당 열에 **제출** 됨에서 **진행 중** 으로 **완료**로 변경 된 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="6fcf8-118">검색 예측이 완료 되 면 검색을 선택 하 여 검색 결과에 대 한 일부 고급 통계를 표시 하는 플라이 아웃 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="6fcf8-119">이 시점에서 **통계** 단추가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="6fcf8-120">이 도구를 선택 하 여 다음과 같은 검색 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="6fcf8-121">요약</span><span class="sxs-lookup"><span data-stu-id="6fcf8-121">Summary</span></span>
- <span data-ttu-id="6fcf8-122">상위 위치</span><span class="sxs-lookup"><span data-stu-id="6fcf8-122">Top locations</span></span>
- <span data-ttu-id="6fcf8-123">쿼리하도록</span><span class="sxs-lookup"><span data-stu-id="6fcf8-123">Queries</span></span>

<span data-ttu-id="6fcf8-124">검색 통계에 대 한 자세한 내용은 [검색 통계](search-statistics.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="6fcf8-125">미리 보기가 완료 되 면 **미리 보기** 단추가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="6fcf8-126">이 도구를 선택 하 여 샘플링 된 결과의 하위 집합을 미리 봅니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="6fcf8-127">검색 결과를 검토 집합에 추가</span><span class="sxs-lookup"><span data-stu-id="6fcf8-127">Add search results to a review set</span></span>

<span data-ttu-id="6fcf8-128">검색의 전체 결과를 수집 하 고 처리할 준비가 되 면 검토 집합에 추가 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="6fcf8-129">자세한 내용은 [검토 집합에 데이터 추가](add-data-to-review-set.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="6fcf8-130">검토 집합에 타사 365 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="6fcf8-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="6fcf8-131">사례에 대 한 수집 프로세스의 일부로, Office 이외의 365 데이터를 검토 집합에 추가 하 고, 검색 도구를 사용 하 여 수집한 Office 365 데이터와 함께 검토 하 고 분석할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="6fcf8-132">Office 이외의 365을 추가 하는 경우에는 케이스의 특정 custodian 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="6fcf8-133">자세한 내용은 타사 [365 데이터를 검토 집합으로 로드](load-non-Office-365-data-into-a-review-set.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6fcf8-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
