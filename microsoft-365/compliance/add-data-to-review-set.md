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
description: 고급 eDiscovery 사례와 연결 된 검색 결과를 추가 합니다. 항목이 원래 위치에서 복사 되 고 Microsoft에서 제공한 Azure 저장소 위치로 복사 됩니다. 또한 항목은 다시 인덱싱되 고 고급 eDiscovery는 이미지 파일에서 OCR (광학 인식)을 수행 하 고 검토 및 분석을 위해 이미지 텍스트를 업로드 합니다.
ms.openlocfilehash: 5e4eaa5e83bbca3a80abe0026f3880ce8d3c85c4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080160"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="13f4f-105">검색 결과를 검토 집합에 추가</span><span class="sxs-lookup"><span data-stu-id="13f4f-105">Add search results to a review set</span></span>

<span data-ttu-id="13f4f-106">검색 결과가 만족 스 러 우면 해당 검색 결과를 검토 하 고 분석할 준비가 되 면 대/소문자에서 검토 집합에 해당 결과를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-106">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="13f4f-107">원본 데이터를 검토 집합에 복사 하면 테마 검색, 거의 중복 검색 및 전자 메일 스레드 식별과 같은 고급 분석 도구를 제공 하 여 검토 및 분석 프로세스를 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-107">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="13f4f-108">Office 365에서 수집한 데이터 외에도 해당 데이터를 검토할 수 있도록 부재 외 365 데이터 원본의 데이터를 검토 집합에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-108">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span> 

<span data-ttu-id="13f4f-109">검색 결과를 검토 집합에 추가 하면 (사례에 대 한 검토 집합이 **검토 집합** 탭에 나열 됨) 다음과 같은 상황이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-109">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="13f4f-110">검색이 다시 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-110">The search is run again.</span></span> <span data-ttu-id="13f4f-111">즉, 검토 집합에 복사 되는 실제 검색 결과는 검색을 마지막으로 실행 했을 때 반환 된 예상 결과와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-111">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="13f4f-112">검색 결과의 모든 항목은 live Office 365 서비스의 원본 데이터 원본에서 복사 되 고 Microsoft 클라우드의 안전한 Azure 저장소 위치로 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-112">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="13f4f-113">모든 항목 (콘텐츠 및 메타 데이터 포함)은 사례 데이터를 검토 하는 동안 검토 집합의 모든 데이터를 완벽 하 게 검색할 수 있도록 다시 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-113">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="13f4f-114">사례 조사 중에 검토 집합에서 데이터를 검색할 때 데이터를 정밀 검색 및 fast search로 다시 인덱싱</span><span class="sxs-lookup"><span data-stu-id="13f4f-114">Re-indexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="13f4f-115">검토 집합에 데이터를 추가 하려면 검색 탭에서 검색을 클릭 하 고 플라이 아웃 페이지에서 **집합을 검토 하려면 결과 추가를** **클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="13f4f-115">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![검토 집합에 데이터 추가](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="13f4f-117">기존 검토 집합에 추가 하거나 새 검토 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-117">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="13f4f-118">새 검토 집합에 추가 하는 경우 이름을 지정 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-118">If adding to a new review set, specify the name and then click **Add**.</span></span>

![검토 집합 선택](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="13f4f-120">검토 집합에 데이터를 추가 하는 것은 장시간 실행 되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-120">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="13f4f-121">이 프로세스에는 Office 365 (예: 사서함 및 사이트)의 원본 데이터 원본에서 항목을 수집 하 여 Azure 저장소 위치로 복사한 다음 (이 복사 프로세스는 수집이 *라고도 함)* 항목을 다시 인덱싱하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-121">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="13f4f-122">**작업** 탭 또는 **검색** 탭의 진행 상태를 추적 하 여 **추가 된 데이터를 검토 집합** 열에서 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-122">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="13f4f-123">검토 집합 처리가 완료 되 면 사례에서 **검토 집합** 탭을 클릭 하 고 검토 집합을 클릭 하 여 검토 집합에서 데이터를 필터링, 검토, 태그 지정 및 내보내는 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-123">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="13f4f-124">검토 집합에 샘플 추가</span><span class="sxs-lookup"><span data-stu-id="13f4f-124">Add a sample to a review set</span></span>

<span data-ttu-id="13f4f-125">검색 결과의 유효성을 검토 집합에 추가 하기 전에 보다 철저히 확인 하려는 경우 모든 항목을 추가 하는 대신 검토 집합에 검색 결과의 예제를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-125">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="13f4f-126">검토 집합에 샘플을 추가 하려면 검색 탭에서 검색을 클릭 하 고 플라이 아웃 페이지에서 **샘플** 을 **클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="13f4f-126">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="13f4f-127">**매개 변수 샘플링** 페이지에서 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-127">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="13f4f-128">**신뢰 수준%** 및 **신뢰도 간격%** -검토 집합에 추가 된 항목은 설정한 통계 매개 변수에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-128">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="13f4f-129">일반적으로 결과를 샘플링할 때 신뢰 수준과 간격을 사용 하는 경우에는 드롭다운 상자에서이를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-129">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="13f4f-130">그렇지 않으면 기본 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-130">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="13f4f-131">**무작위 샘플%** -검토 집합에 추가 되는 항목은 검색에서 반환 되는 총 항목 수에 대 한 지정 된 백분율을 임의로 선택 하 여 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-131">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="13f4f-132">이전 옵션 중 하나를 선택 하 고 구성한 후에는 예제를 추가할 검토 집합을 선택한 다음 **보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-132">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="13f4f-133">다시 말하지만 **작업** 탭 이나 **검색** 탭에서 **검토 집합에 추가 된 데이터** 열에서 상태를 모니터링 하 여 진행 상황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-133">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="13f4f-134">광학 인식</span><span class="sxs-lookup"><span data-stu-id="13f4f-134">Optical character recognition</span></span>

<span data-ttu-id="13f4f-135">검토 집합에 검색 결과를 추가 하면 고급 eDiscovery의 OCR (광학 인식) 기능은 이미지에서 텍스트를 자동으로 추출 하며, 검토 집합에 추가 되는 데이터와 함께 이미지 텍스트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-135">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="13f4f-136">검토 집합에서 선택한 이미지 파일의 텍스트 뷰어에서 추출한 텍스트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-136">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="13f4f-137">이렇게 하면 이미지의 텍스트에 대 한 추가 검토 및 분석을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-137">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="13f4f-138">OCR은 느슨한 파일, 전자 메일 첨부 파일 및 포함 된 이미지에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-138">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="13f4f-139">OCR에 대해 지원 되는 이미지 파일 형식 목록은 [Advanced eDiscovery에서 지원 되는 파일 형식을](supported-filetypes-ediscovery20.md#image)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13f4f-139">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="13f4f-140">고급 eDiscovery에서 만드는 각 사례에 대해 OCR 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f4f-140">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="13f4f-141">자세한 내용은 [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="13f4f-141">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
