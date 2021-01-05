---
title: Advanced eDiscovery에서 사례에 대한 데이터 수집
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
description: Advanced eDiscovery의 검색 도구를 사용하여 조사에서 검토할 문서 집합을 식별하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751273"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="00aed-103">Advanced eDiscovery에서 사례에 대한 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="00aed-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="00aed-104">사례에 관심이 있는 보호자 및 데이터 원본을 식별한 다음에는 확인할 문서 집합을 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="00aed-105">Advanced eDiscovery의 검색 도구를 사용하여 Microsoft 365의 상주 및 비보조 위치에서 관련 문서를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="00aed-106">검색을 실행한 후 검색 쿼리와 일치하는 항목이 가장 많은 위치 등 검색된 항목에 대한 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="00aed-107">결과의 하위 집합을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="00aed-108">추가로 검사할 문서 집합을 확인한 경우 검색 결과를 검토 집합에 추가하여 수집 및 프로세스를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="00aed-109">검색 만들기</span><span class="sxs-lookup"><span data-stu-id="00aed-109">Create a search</span></span>

<span data-ttu-id="00aed-110">검색 **탭에서** 새  검색을 선택하면 검색 만들기를 안내하는 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="00aed-111">검색을 만드는 방법에 대한 자세한 내용은 검색 만들기를 참조하여 데이터를 [수집합니다.](create-search-to-collect-data.md)</span><span class="sxs-lookup"><span data-stu-id="00aed-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="00aed-112">검색을 만든 후 세부 정보가 있는 플라이아웃 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="00aed-113">**검색이** 아직  완료되지 않았기 때문에 통계 및 미리 보기 단추를 처음에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="00aed-114">검색 탭에서 검색 진행률을 **추적할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="00aed-115">검색 결과 및 통계 보기</span><span class="sxs-lookup"><span data-stu-id="00aed-115">View search results and statistics</span></span>

<span data-ttu-id="00aed-116">콘텐츠 검색에는 통계(예상치) 및 미리 보기의 두 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="00aed-117">이러한 각 구성 요소가 완료되면 검색 탭의 해당 열에 표시되는  상태가 **제출에서** 진행  중으로 **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="00aed-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="00aed-118">검색 예상이 완료되면 검색을 선택하여 검색 결과에 대한 몇 가지 높은 수준의 통계를 표시하는 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="00aed-119">이때 통계 단추가 활성화됩니다. </span><span class="sxs-lookup"><span data-stu-id="00aed-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="00aed-120">이 옵션을 선택하여 검색 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="00aed-121">요약</span><span class="sxs-lookup"><span data-stu-id="00aed-121">Summary</span></span>
- <span data-ttu-id="00aed-122">상위 위치</span><span class="sxs-lookup"><span data-stu-id="00aed-122">Top locations</span></span>
- <span data-ttu-id="00aed-123">쿼리</span><span class="sxs-lookup"><span data-stu-id="00aed-123">Queries</span></span>

<span data-ttu-id="00aed-124">검색 통계에 대한 자세한 내용은 [검색 통계를 참조하세요.](search-statistics-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="00aed-124">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

<span data-ttu-id="00aed-125">미리 보기가 완료되면 미리 **보기** 단추가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="00aed-126">결과의 샘플링된 하위 집합을 미리 확인하려면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="00aed-127">검색 결과를 검토 집합에 추가</span><span class="sxs-lookup"><span data-stu-id="00aed-127">Add search results to a review set</span></span>

<span data-ttu-id="00aed-128">검색의 전체 결과를 수집하고 처리하기 위해 준비되면 검토 집합에 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="00aed-129">자세한 내용은 검토 [집합에 데이터 추가를 참조합니다.](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="00aed-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="00aed-130">검토 집합에 비 Microsoft 365 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="00aed-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="00aed-131">사례에 대한 수집 프로세스의 일부로, 비 Office 365 데이터를 검토 집합에 추가하고 검색 도구를 사용하여 수집한 Office 365 데이터와 함께 검토 및 분석할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="00aed-132">비 Office 365를 추가하는 경우 이 경우 해당 정보를 특정 보직원과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00aed-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="00aed-133">자세한 내용은 [검토 집합에 비 Microsoft 365 데이터 로드를 참조하세요.](load-non-Office-365-data-into-a-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="00aed-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
