---
title: 콘텐츠 검색을 다시 시도하여 콘텐츠 위치 오류 해결
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 조사 중에 다시 시도 단추를 사용하여 콘텐츠 위치 오류가 있는 콘텐츠 검색을 해결할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3aed9c1d2d1fe3c40adb64b4854ef359f931bcb
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357558"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="1f399-103">콘텐츠 검색을 다시 시도하여 콘텐츠 위치 오류 해결</span><span class="sxs-lookup"><span data-stu-id="1f399-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="1f399-104">보안 및 준수 센터에서 콘텐츠 검색을 사용하여 많은 수의 사서함을 검색하는 경우 오류와 비슷한 검색 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the  error:</span></span>

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="1f399-105">이러한 오류(CS001-002, CS003-002, CS008-009, CS012-002 및 CS012-002 형식의 오류)는 콘텐츠 검색이 특정 콘텐츠 위치를 검색하지 못했다는 것을 나타냅니다. 이 예에서는 두 개의 사서함을 검색하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="1f399-106">이러한 오류는 콘텐츠 검색의 상태 세부 정보 플라이아웃 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="1f399-107">콘텐츠 위치 오류의 원인</span><span class="sxs-lookup"><span data-stu-id="1f399-107">Cause of content location errors</span></span>

<span data-ttu-id="1f399-108">많은 수의 사서함을 검색할 때 검색은 Microsoft 데이터 센터의 수천 대 서버에 분산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="1f399-109">특정 서버는 한 번이면 다시 시작 상태가 되거나 중복 복사본으로 장애 조치(fail over)하는 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="1f399-110">이러한 경우 모두 데이터 검색에 대한 콘텐츠 검색 요청의 시간이 시간으로 설정됩니다. 이전 예에서 실패한 사서함에 대한 오류는 검색 시간 제한의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-110">In either of these cases, the Content Search's request to retrieve data will time out. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="1f399-111">콘텐츠 위치 오류 해결</span><span class="sxs-lookup"><span data-stu-id="1f399-111">Resolving content location errors</span></span>

<span data-ttu-id="1f399-112">검색을 다시 시작하면 여러 서버에서 유사한 오류가 발생하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-112">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="1f399-113">검색을 다시 시작하는 대신 검색  결과 페이지 맨 위에 표시되는 다시 시도 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-113">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![다시 시도 단추를 클릭하여 콘텐츠 위치 오류를 해결합니다.](../media/retrycontentsearch3.png)

<span data-ttu-id="1f399-115">이렇게 하면 실패한 사서함에 대한 검색만 다시 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-115">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="1f399-116">검색을 다시 시도하면 반환된 다른 결과가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-116">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="1f399-117">콘텐츠 위치 오류를 방지하는 팁</span><span class="sxs-lookup"><span data-stu-id="1f399-117">Tips to avoid content location errors</span></span>

<span data-ttu-id="1f399-118">다음은 콘텐츠 위치 오류의 몇 가지 추가 원인과 많은 수의 사서함을 검색할 때 이를 방지하는 데 도움이 되는 팁입니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-118">Here are some additional causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="1f399-119">사용자 작업으로 인해 검색되는 사서함이 사용 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-119">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="1f399-120">이 경우 사서함을 사용할 수 없게 되기 위해 검색 서비스가 자체적으로 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-120">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="1f399-121">이를 방지하기 위해 업무 시간 이 아닌 시간에 검색을 실행해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-121">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="1f399-122">검색 쿼리가 사서함에서 너무 많은 콘텐츠를 검색하고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-122">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="1f399-123">가능한 경우 키워드, 날짜 범위 및 검색 조건을 사용하여 검색 범위를 좁히십시오.</span><span class="sxs-lookup"><span data-stu-id="1f399-123">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="1f399-124">키워드 목록을 사용하여 검색 쿼리를 만들 때 키워드 또는 키워드 구가 너무 [많이 있습니다.](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)</span><span class="sxs-lookup"><span data-stu-id="1f399-124">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span></span> <span data-ttu-id="1f399-125">키워드 목록을 사용하는 검색 쿼리를 실행하면 기본적으로 이 서비스는 통계를 생성하기 위해 키워드 목록의 각 행에 대해 별도의 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-125">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="1f399-126">검색 쿼리에서 키워드 목록을 사용하는 경우 키워드 목록의 행 수를 최소화하거나 숫자 키워드를 더 작은 목록으로 나누고 각 키워드 목록에 대해 다른 검색을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-126">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1f399-127">큰 키워드 목록으로 인한 문제를 줄이기 위해 이제 검색 쿼리의 키워드 목록에서 최대 20개 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-127">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="1f399-128">같은 사서함에서 동시에 너무 많은 검색이 수행되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-128">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="1f399-129">가능한 경우 사서함 하나에 대해 한 번의 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-129">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="1f399-130">단일 검색에서 너무 많은 사서함 검색</span><span class="sxs-lookup"><span data-stu-id="1f399-130">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="1f399-131">많은 수의 사서함을 검색할 때 콘텐츠 위치 오류가 발생할 확률이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-131">The probability of content location errors increases when searching a large number of mailboxes.</span></span> <span data-ttu-id="1f399-132">가능한 경우 각 검색에 조직에 사서함의 하위 집합이 포함 있도록 여러 검색을 실행 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-132">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="1f399-133">사서함에 대한 필수 유지 관리가 수행되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f399-133">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="1f399-134">이 원인은 거의 발생하지 않을 수 있습니다. 콘텐츠 위치 오류가 발생한 후 잠시 기다렸다가 검색을 다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="1f399-134">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
