---
title: CJK/Double Byte for Advanced eDiscovery
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
description: 더블 Advanced eDiscovery 집합을 Microsoft 365, 중국어, 일본어 및 한국어(CJK) 언어를 지원하는 방법을 배워야 합니다.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926604"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="a5999-103">CJK 언어 지원 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a5999-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="a5999-104">Advanced eDiscovery 검토 집합에서 다음과 같은 고급 시나리오에 대해 더블바트 문자 집합 언어(중국어 간체, 중국어 번체, 일본어 및 *한국어(총체적으로 CJK* 언어라고도 합니다))를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="a5999-105">검토 [집합의 데이터를 쿼리할 때](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="a5999-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="a5999-106">검토 [집합에서 문서에 태그를 지정하는 경우.](tagging-documents.md)</span><span class="sxs-lookup"><span data-stu-id="a5999-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="a5999-107">중복에 [가까운 검색,](analyzing-data-in-review-set.md) 전자 메일 스레딩 및 테마 분석을 사용하여 검토 집합의 사례 데이터를 분석할 때</span><span class="sxs-lookup"><span data-stu-id="a5999-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a5999-108">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="a5999-108">Frequently asked questions</span></span>

<span data-ttu-id="a5999-109">**검색을 만들어 CJK 문자가 포함된 항목을 수집하는 방법**</span><span class="sxs-lookup"><span data-stu-id="a5999-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="a5999-110">콘텐츠 검색 시 키워드 [검색,](building-search-queries.md#keyword-searches)키워드 [](keyword-queries-and-search-conditions.md) 쿼리 및 검색 조건에 CJK 문자를 사용할 수 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a5999-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="a5999-111">Core eDiscovery 및 콘텐츠 검색에서 콘텐츠를 검색할 때 CJK 문자 검색도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="a5999-112">부울 연산자 **AND, OR,** [](keyword-queries-and-search-conditions.md#search-operators) **NOT** 및 NEAR를 비롯한 모든 검색 연산자 및 검색 조건에 대해 CJK 지원을 **제공합니다.** [](keyword-queries-and-search-conditions.md#search-conditions)</span><span class="sxs-lookup"><span data-stu-id="a5999-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="a5999-113">콘텐츠 위치 또는 항목에 CJK 문자가 포함되어 있지만 검색에서 결과를 반환하지 않는 경우 쿼리 언어-국가/지역 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![콘텐츠 검색의 쿼리 언어-국가/지역 아이콘](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="a5999-115">를 선택하고 검색에 해당하는 언어-국가 문화권 코드 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="a5999-116">기본 언어/지역은 중립입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-116">The default language/region is neutral.</span></span>

<span data-ttu-id="a5999-117">**한에 여러 언어를 검색할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="a5999-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="a5999-118">검색 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="a5999-119">[2013의 검토 집합에서](review-set-search.md) 데이터를 쿼리할 Advanced eDiscovery 여러 언어를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="a5999-120">데이터를 [수집하는 검색을](create-search-to-collect-data.md)만들 때 대상으로 하는 각 언어에 대해 별도의 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="a5999-121">예를 들어 중국어와 한국어가 모두 포함된 문서를 검색하는 경우 첫 번째 쿼리에 대해 중국어를 선택하고 두 번째 쿼리에 대해 한국어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="a5999-122">**리뷰 집합에서 쿼리에 대한 언어를 선택하는 쿼리 언어-국가/지역 아이콘이 없습니다. 검토 집합 검색에서 쿼리 언어를 지정하는 방법**</span><span class="sxs-lookup"><span data-stu-id="a5999-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="a5999-123">검토 집합 쿼리의 경우 문서 언어를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="a5999-124">Advanced eDiscovery 집합에 콘텐츠를 추가할 때 문서 언어를 자동으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="a5999-125">이렇게 하면 검토 집합에서 쿼리 결과를 최적화하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="a5999-126">**파일 메타데이터에서 검색된 언어를 볼 [수 있나요?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="a5999-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="a5999-127">아니요. 파일 메타데이터에서 검색된 언어를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="a5999-128">**검토 집합의 문서 언어를 사용하여 필터링할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="a5999-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="a5999-129">아니요. 검토 집합의 문서 언어별로 필터링, 정렬 또는 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="a5999-130">**검토 집합 시나리오에 대한 이 CJK 릴리스가 기존 검색 및 검토 집합에 영향을 미치나요?**</span><span class="sxs-lookup"><span data-stu-id="a5999-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="a5999-131">아니요. 기존 검색 및 검토 집합은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="a5999-132">기존 데이터를 다시 인덱서할 필요가 없습니다. 영어 텍스트의 검색 결과는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="a5999-133">**표시 언어를 중국어, 일본어 또는 한국어로 변경하는 방법**</span><span class="sxs-lookup"><span data-stu-id="a5999-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="a5999-134">표시 언어 및 표준 시간대를 변경하는 방법에 대한 자세한 내용은 에 대한 언어 및 지역 설정을 설정하는 [Office 365.](/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="a5999-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="a5999-135">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="a5999-135">Known issues</span></span>

- <span data-ttu-id="a5999-136">OCR은 이미지 파일의 CJK 문자를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="a5999-137">[Annotate](view-documents-in-review-set.md#annotate-view) 보기의 전자 메일 파일(예: \*.eml 및 \*.msg)은 CJK 언어에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="a5999-138">텍스트 보기의 검색 적중 강조 [표시는](view-documents-in-review-set.md#text-view) CJK 언어에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="a5999-139">데이터를 [분석하는 데](using-relevance.md) 사용되는 중요성 모듈은 CJK 언어를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="a5999-140">[CJK](managing-holds.md#manage-non-custodial-holds) 언어에서는 쿼리 기반 보류가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>