---
title: 고급 eDiscovery에 대 한 CJK/더블 바이트 지원
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365의 고급 eDiscovery에서 더블 바이트 문자 집합을 사용 하는 중국어, 일본어 및 한국어 (CJK) 언어를 지 원하는 방법에 대해 알아봅니다.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626942"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="740c4-103">고급 eDiscovery에 대 한 CJK 언어 지원</span><span class="sxs-lookup"><span data-stu-id="740c4-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="740c4-104">고급 eDiscovery에서는 검토 집합의 다음 고급 시나리오에 대해 더블 바이트 문자 집합 언어 (예: *CJK* 언어로 통칭 되는 중국어 간체, 중국어 번체, 일본어 및 한국어 포함)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="740c4-105">[검토 집합에서 데이터를 쿼리할](review-set-search.md)때</span><span class="sxs-lookup"><span data-stu-id="740c4-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="740c4-106">[검토 집합의 문서에 태그](tagging-documents.md)를 추가할 때</span><span class="sxs-lookup"><span data-stu-id="740c4-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="740c4-107">근접 중복 검색, 전자 메일 스레딩 및 테마 분석을 사용 하 여 [검토 집합의 사례 데이터를 분석 하는](analyzing-data-in-review-set.md) 경우</span><span class="sxs-lookup"><span data-stu-id="740c4-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="740c4-108">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="740c4-108">Frequently asked questions</span></span>

<span data-ttu-id="740c4-109">**CJK 문자가 포함 된 항목을 수집 하기 위해 검색을 만드는 방법은 무엇 인가요?**</span><span class="sxs-lookup"><span data-stu-id="740c4-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="740c4-110">고급 eDiscovery에서 콘텐츠를 검색할 때 [키워드 검색](building-search-queries.md#keyword-searches), [키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md) 에 CJK 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="740c4-111">중요 eDiscovery 및 콘텐츠 검색에서 콘텐츠를 검색할 때 CJK 문자 검색도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="740c4-112">Microsoft **는 부울 연산자,** **OR**, **NOT**및 **NEAR**을 비롯 하 여 모든 [검색 운영자](keyword-queries-and-search-conditions.md#search-operators) 및 [검색 조건](keyword-queries-and-search-conditions.md#search-conditions)에 대해 CJK 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="740c4-113">콘텐츠 위치 또는 항목에 CJK 문자가 포함 되어 있지만 검색 결과에 결과가 반환 되지 않으면 쿼리 언어-국가/지역 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![콘텐츠 검색의 쿼리 언어-국가/지역 아이콘](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="740c4-115">해당 검색에 해당 하는 언어-국가 문화권 코드 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="740c4-116">기본 언어/지역은 중립입니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-116">The default language/region is neutral.</span></span>

<span data-ttu-id="740c4-117">**한 번에 여러 언어를 검색할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="740c4-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="740c4-118">검색 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="740c4-119">고급 eDiscovery의 [검토 집합에서 데이터를 쿼리할](review-set-search.md) 때 여러 언어를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="740c4-120">[검색을 만들어 데이터를 수집](create-search-to-collect-data.md)하는 경우에는 대상으로 지정 하는 각 언어에 대해 별도의 검색을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="740c4-121">예를 들어, 중국어와 한국어가 모두 포함 된 문서를 검색 하는 경우 첫 번째 쿼리에 대해 중국어를 선택 하 고 두 번째 쿼리에 대해 한국어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="740c4-122">**검토 집합에서 쿼리에 사용할 언어를 선택 하는 쿼리 언어-국가/지역 아이콘이 표시 되지 않습니다. 검토 집합 검색에서 쿼리 언어를 지정 하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="740c4-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="740c4-123">검토 집합 쿼리의 경우 문서 언어를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="740c4-124">검토 집합에 콘텐츠를 추가 하는 경우 고급 eDiscovery에서는 문서 언어를 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="740c4-125">이렇게 하면 검토 집합에서 쿼리 결과를 최적화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="740c4-126">**[파일 메타 데이터](view-documents-in-review-set.md#file-metadata)에서 검색 된 언어를 확인할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="740c4-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="740c4-127">아니요, 파일 메타 데이터에 검색 된 언어가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="740c4-128">**검토 집합에서 문서 언어를 기준으로 필터링 할 수**있습니까?</span><span class="sxs-lookup"><span data-stu-id="740c4-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="740c4-129">아니요, 검토 집합에서 문서 언어를 필터링, 정렬 또는 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="740c4-130">**검토 설정 시나리오에 대해이 CJK 릴리스가 기존 검색 및 검토 집합에 영향을 줍니까?**</span><span class="sxs-lookup"><span data-stu-id="740c4-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="740c4-131">아니요, 기존 검색 및 검토 집합이 모두 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="740c4-132">기존 데이터를 다시 인덱싱할 필요는 없으며 영어 텍스트에 대 한 검색 결과는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="740c4-133">**표시 언어를 중국어, 일본어 또는 한국어로 변경 하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="740c4-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="740c4-134">표시 언어 및 표준 시간대를 변경 하는 방법에 대 한 자세한 내용은 [how to set language and region settings For Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="740c4-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="740c4-135">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="740c4-135">Known issues</span></span>

- <span data-ttu-id="740c4-136">OCR은 이미지 파일에서 CJK 문자를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="740c4-137">[주석 보기](view-documents-in-review-set.md#annotate-view) 의 전자 메일 파일 (예: \* .eml 및 \* .msg)은 CJK 언어에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="740c4-138">[텍스트 보기](view-documents-in-review-set.md#text-view) 의 검색 방문 횟수 강조 표시는 CJK 언어에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="740c4-139">데이터를 분석 하는 데 사용 되는 [관련성 모듈](using-relevance.md) 은 CJK 언어를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="740c4-140">[쿼리 기반 보류](managing-holds.md#manage-non-custodial-holds) 는 CJK 언어에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="740c4-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
