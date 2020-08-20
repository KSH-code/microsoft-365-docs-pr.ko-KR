---
title: 검색 결과를 검토 집합에 추가
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
ms.custom:
- seo-marvel-apr2020
description: 검색 결과 또는 해당 검색 결과의 예제를 고급 eDiscovery 사례 검토 집합에 추가하는 방법을 설명합니다.
ms.openlocfilehash: 687cc33c0e7e6a09fb352e9c13058a6fcac30053
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814530"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="72d5d-103">검색 결과를 검토 집합에 추가</span><span class="sxs-lookup"><span data-stu-id="72d5d-103">Add search results to a review set</span></span>

<span data-ttu-id="72d5d-104">검색 결과에 만족하고 해당 검색 결과를 검토하고 분석할 준비가 된 경우 사례의 검토 집합에 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-104">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="72d5d-105">또한 원본 데이터를 검토 집합에 복사하면 테마 검색, 중복 검색 및 이메일 스레드 식별과 같은 고급 분석 도구를 제공하여 검토 및 분석 프로세스가 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-105">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="72d5d-106">또한 Microsoft 365에서 수집한 데이터 외에도 해당 데이터를 검토 집합에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-106">You can also add data from non-Microsoft 365 data sources to a review set so that you can review that data in addition to the data you collect from Microsoft 365.</span></span> 

<span data-ttu-id="72d5d-107">검토 집합에 검색 결과가 추가되면(사례의 리뷰 집합이 검토 집합 탭에 **표시됨)** 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-107">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="72d5d-108">검색이 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-108">The search is run again.</span></span> <span data-ttu-id="72d5d-109">즉, 리뷰 집합으로 복사된 실제 검색 결과는 검색을 마지막으로 실행할 때 반환된 예상 결과와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-109">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="72d5d-110">검색 결과의 모든 항목은 라이브 서비스의 원본 데이터 원본에서 복사되고 Microsoft 클라우드의 보안 Azure Storage 위치로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-110">All items in the search results are copied from the original data source in the live services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="72d5d-111">콘텐츠 및 메타데이터를 포함한 모든 항목은 다시 인덱싱되므로 사례 데이터를 검토하는 동안 리뷰 집합의 모든 데이터를 완전히 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-111">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="72d5d-112">사례 조사 중에 검토 집합의 데이터를 검색하면 데이터를 아주 빠르고 빠른 검색으로 수행한 결과를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-112">Re-indexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="72d5d-113">검토 집합에 데이터를 추가하려면 검색 탭에서 **검색을** 클릭한 다음 **결과 추가를** 클릭하여 플라이 아웃 페이지의 집합을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-113">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![검토 집합에 데이터 추가](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="72d5d-115">기존 검토 집합에 추가하거나 새 검토 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-115">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="72d5d-116">새 검토 집합에 추가하려면 이름을 지정하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="72d5d-116">If adding to a new review set, specify the name and then click **Add**.</span></span>

![검토 집합 선택](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

## <a name="define-options-to-scope-your-collection-for-review"></a><span data-ttu-id="72d5d-118">컬렉션의 범위를 검토할 수 있도록 정의하는 옵션 정의</span><span class="sxs-lookup"><span data-stu-id="72d5d-118">Define options to scope your collection for review</span></span>

<span data-ttu-id="72d5d-119">검색의 콘텐츠를 기존 검토 집합에 추가하거나 검토할 콘텐츠를 수집하는 방법에 대한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-119">As you add the content of a search to an existing review set or create a new one you have options for how to collect the content for review:</span></span>

- <span data-ttu-id="72d5d-120">**대화 내용 검토 집합** - 대화와 대화에 대한 컨텍스트를 검토할 수 있게 스레드된 대화에 대해 보호하도록 선택된 대화에 대해 사용할 수 있습니다. 이 문서 [대화 검토 집합]에서 더 많은 내용을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="72d5d-120">**Conversational review set** - the items added to the review set will be enabled for threaded conversations to help review content in context of the back and forth conversation, see more in this article [conversation review sets]</span></span>

- <span data-ttu-id="72d5d-121">**최신 첨부 파일에 대한 검색 사용** - 추가 검토를 위해 모음에 최신 첨부 파일 또는 연결된 파일을 포함하려면 이 제어를 사용합니다. 이 콘텐츠를 그룹화하는 데 사용할 수 있는 새로운 검색 가능한 필드 이름에 대한 자세한 내용은 [Advanced ediscovery의 문서 메타데이터 필드] 참조</span><span class="sxs-lookup"><span data-stu-id="72d5d-121">**Enable retrieval for modern attachment** - use this control to include modern attachments or linked files in the collection for further review; read more about the new searchable field names that are available to group this content, see [document metadata fields in advanced ediscovery]</span></span>

- <span data-ttu-id="72d5d-122">**SharePoint의 버전 포함(beta)** - 이 제어는 버전 제한 및 컬렉션의 검색 매개 변수별로 모든 버전의 SharePoint 파일 모음을 사용합니다. 참고: 이 컨트롤을 사용하면 컬렉션의 크기가 크게 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-122">**Include versions from SharePoint (beta)** - this control enables collection of all version of a SharePoint file per the version limits and search parameters of the collection; note: this control will increase the size of the collection significantly</span></span>

<span data-ttu-id="72d5d-123">검토 집합에 데이터를 추가하는 것은 긴 실행 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-123">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="72d5d-124">이 프로세스는 Microsoft 365의 원본 데이터 원본에서 항목을 수집하고(예: 사서함 및 사이트에서 의사를 가리키고 복사)에 복사(이 복사 프로세스를 *수집라고도*함)하고 다시 인덱싱하는 작업을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-124">This process includes gathering items from the original data sources in Microsoft 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="72d5d-125">작업 탭이나 추가된 데이터에서 **상태를** 모니터링하여 검토 집합 열의 **Searches** **상태를 모니터링하여 작업 탭의 진행 상황을 추적할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-125">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="72d5d-126">검토 집합 처리가 완료된 후 해당 사례의 **검토 집합** 탭을 클릭한 다음 검토 집합을 클릭하여 검토 집합의 데이터 필터링, 검토, 태그 지정 및 내보내기 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-126">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="72d5d-127">검토 집합에 샘플 추가</span><span class="sxs-lookup"><span data-stu-id="72d5d-127">Add a sample to a review set</span></span>

<span data-ttu-id="72d5d-128">모든 결과를 검토 집합에 추가하기 전에 검색 결과의 유효성을 보다 세부적으로 확인하려면 모든 항목을 추가하는 대신 검색 결과의 샘플을 검토 집합에 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-128">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="72d5d-129">검토 집합에 샘플을 추가하려면 검색 탭에서 검색을 클릭한 **다음** 플라이 **아웃 페이지에서 샘플을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-129">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="72d5d-130">샘플링 **매개 변수는 페이지에서 다음** 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-130">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="72d5d-131">**신뢰 수준 %** 및 신뢰 수준 **%-** 검토 집합에 추가된 항목은 사용자가 설정한 통계 매개 변수에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-131">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="72d5d-132">일반적으로 결과를 샘플링할 때 신뢰 수준 및 간격을 사용하는 경우 드롭다운 상자에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-132">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="72d5d-133">그렇지 않은 경우 기본 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-133">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="72d5d-134">**임의 샘플 %** - 리뷰 집합에 추가된 항목은 검색에서 반환되는 총 항목 수의 지정된 비율의 임의 선택을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-134">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="72d5d-135">이전 옵션 중 하나를 선택하고 구성한 후 샘플을 추가할 검토 집합을 선택하고 보내기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="72d5d-135">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="72d5d-136">마찬가지로, 추가된 데이터에서 상태를 **모니터링하여** 검토 집합 열을 모니터링하여 작업 탭 또는 **검색 탭의 진행 상황을 추적할 수** 있습니다. **Searches**</span><span class="sxs-lookup"><span data-stu-id="72d5d-136">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="72d5d-137">광학 인식</span><span class="sxs-lookup"><span data-stu-id="72d5d-137">Optical character recognition</span></span>

<span data-ttu-id="72d5d-138">검토 집합에 검색 결과를 추가하면 고급 eDiscovery의 OCR(광학 문자 인식) 기능이 이미지에서 텍스트를 자동으로 추출하고 검토 집합에 추가된 데이터가 포함된 이미지 텍스트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-138">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="72d5d-139">검토 집합에서 선택한 이미지 파일의 텍스트 뷰어에서 추출된 텍스트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-139">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="72d5d-140">이렇게 하면 이미지의 텍스트를 추가로 검토하고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-140">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="72d5d-141">OCR은 느슨한 파일, 전자 메일 첨부 파일 및 포함된 이미지에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-141">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="72d5d-142">OCR에 지원되는 이미지 파일 형식 목록은 Advanced [eDiscovery에서 지원되는 파일 형식을 참조하세요.](supported-filetypes-ediscovery20.md#image)</span><span class="sxs-lookup"><span data-stu-id="72d5d-142">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="72d5d-143">Advanced eDiscovery에서 만드는 각 케이스에 대해 OCR 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d5d-143">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="72d5d-144">자세한 내용은 검색 및 [분석 설정 구성을 참조하세요.](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)</span><span class="sxs-lookup"><span data-stu-id="72d5d-144">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
