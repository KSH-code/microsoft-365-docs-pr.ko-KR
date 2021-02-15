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
description: 이러한 검색 결과의 검색 결과 또는 샘플을 Advanced eDiscovery 사례 검토 집합에 추가하는 방법을 학습합니다.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919980"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="b7b43-103">검색 결과를 검토 집합에 추가</span><span class="sxs-lookup"><span data-stu-id="b7b43-103">Add search results to a review set</span></span>

<span data-ttu-id="b7b43-104">검색 결과가 만족스러우면 해당 검색 결과를 검토하고 분석할 준비가 된 경우 해당 검색 결과를 검토 집합에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-104">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="b7b43-105">또한 원본 데이터를 검토 집합에 복사하면 테마 검색, 중복에 가까운 검색, 전자 메일 스레드 식별 등의 고급 분석 도구를 제공하여 검토 및 분석 프로세스를 용이하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-105">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="b7b43-106">Microsoft 365에서 수집하는 데이터 외에 해당 데이터를 검토할 수 있도록 Microsoft 365가 아닌 다른 데이터 원본의 데이터를 검토 집합에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-106">You can also add data from non-Microsoft 365 data sources to a review set so that you can review that data in addition to the data you collect from Microsoft 365.</span></span>

<span data-ttu-id="b7b43-107">검색 결과를 검토 집합에 추가하면(사례의 검토 집합이 검토 집합 **탭에** 나열) 다음과 같은 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-107">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="b7b43-108">검색이 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-108">The search is run again.</span></span> <span data-ttu-id="b7b43-109">즉, 리뷰 집합에 복사된 실제 검색 결과가 검색이 마지막으로 실행될 때 반환된 예상 결과와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-109">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="b7b43-110">검색 결과의 모든 항목은 라이브 서비스의 원본 데이터 원본에서 복사된 후 Microsoft 클라우드의 보안 Azure Storage 위치에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-110">All items in the search results are copied from the original data source in the live services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="b7b43-111">콘텐츠 및 메타데이터를 포함한 모든 항목은 다시 인덱서되어 사례 데이터를 검토하는 동안 검토 집합의 모든 데이터를 완전히 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-111">All items (including the content and metadata) are reindexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="b7b43-112">사례 조사 중에 검토 집합의 데이터를 검색할 때 데이터를 다시 인덱스하면 철저하고 빠른 검색이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-112">Reindexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

- <span data-ttu-id="b7b43-113">[Microsoft](encryption.md) 암호화 기술로 암호화되고 검색 결과에 반환되는 전자 메일 메시지에 첨부된 파일은 전자 메일 메시지와 첨부 파일이 검토 집합에 추가될 때 암호가 해독됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-113">A file encrypted with a [Microsoft encryption technology](encryption.md) and is attached to an email message that's returned in the search results is decrypted when the email message and attached file are added to the review set.</span></span> <span data-ttu-id="b7b43-114">검토 집합에서 암호 해독된 파일을 검토하고 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-114">You can review and query the decrypted file in the review set.</span></span> <span data-ttu-id="b7b43-115">암호 해독된 전자 메일 첨부 파일을 검토 집합에 추가하기 위해 RMS 암호 해독 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-115">You have to be assigned the RMS Decrypt role to add decrypted email attachments to a review set.</span></span> <span data-ttu-id="b7b43-116">자세한 내용은 [Microsoft 365 eDiscovery](ediscovery-decryption.md)도구의 암호 해독을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7b43-116">For more information, see [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).</span></span>

<span data-ttu-id="b7b43-117">검토 집합에 데이터를 추가하려면 검색 탭에서 검색을 클릭한  다음 결과 추가를 클릭하여 플라이아웃 페이지에서 설정된 검토를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="b7b43-117">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

<span data-ttu-id="b7b43-118">기존 검토 집합에 추가하거나 새 검토 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-118">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="b7b43-119">새 검토 집합에 추가하는 경우 이름을 지정한 다음 **추가를** 클릭하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-119">If adding to a new review set, specify the name and then click **Add** to display the flyout page.</span></span>

![검토 집합 선택 및 컬렉션 옵션 구성](../media/AeD_AddToReviewSet.png)

<span data-ttu-id="b7b43-121">검토 집합에 데이터를 추가하는 과정은 오래 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-121">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="b7b43-122">이 프로세스에는 Microsoft 365의 원본 데이터 원본(예: 사서함 및 사이트)에서 항목을 수집하고 Azure Storage 위치로 복사한 다음(이 복사 프로세스를 수집이라고도 합니다) 항목을 다시 인덱스하는 과정이 포함됩니다. </span><span class="sxs-lookup"><span data-stu-id="b7b43-122">This process includes gathering items from the original data sources in Microsoft 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then reindexing the items.</span></span> <span data-ttu-id="b7b43-123">추가된 데이터의 상태를  모니터링하여 작업 탭  또는 검색 탭에서 설정된 열을 검토하여 진행 상황을 **추적할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-123">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="b7b43-124">검토 집합 처리가 완료되면 해당  사례의 검토 집합 탭을 클릭한 다음 검토 집합을 클릭하여 검토 집합의 데이터 필터링, 검토, 태그 지정 및 내보내기 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-124">After the review set processing is completed, click the **Review sets** tab in the case, and then click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="define-options-to-scope-your-collection-for-review"></a><span data-ttu-id="b7b43-125">검토할 컬렉션의 범위를 지정하는 옵션 정의</span><span class="sxs-lookup"><span data-stu-id="b7b43-125">Define options to scope your collection for review</span></span>

<span data-ttu-id="b7b43-126">기존 또는 새 검토 집합에 검색 콘텐츠를 추가할 때 검토를 위해 콘텐츠를 수집하는 방법에 대한 다음 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-126">When you add the content of a search to an existing or new review set, you have the following options for how to collect the content for review:</span></span>

- <span data-ttu-id="b7b43-127">**SharePoint(베타)의** 버전 포함: 컬렉션의 버전 제한 및 검색 매개 변수에 따라 모든 버전의 SharePoint 문서 컬렉션을 사용하도록 설정하려면 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-127">**Include versions from SharePoint (beta)**: Use this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="b7b43-128">이 옵션을 선택하면 검토 집합에 추가된 항목의 크기가 크게 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-128">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

- <span data-ttu-id="b7b43-129">**대화 검색** 옵션: 검토 집합에 추가된 항목은 스레드 대화에 대해 사용하도록 설정되어 뒷부분 대화의 컨텍스트에서 콘텐츠를 검토하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-129">**Conversation retrieval options**: Items added to the review set are enabled for threaded conversations to help review content in context of the back and forth conversation.</span></span> <span data-ttu-id="b7b43-130">자세한 내용은 [Advanced eDiscovery의 대화 검토를 참조하세요.](conversation-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="b7b43-130">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

- <span data-ttu-id="b7b43-131">**최신 첨부 파일에** 대한 검색 사용: 추가 검토를 위해 컬렉션에 최신 첨부 파일 또는 연결된 파일을 포함하려면 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-131">**Enable retrieval for modern attachments**: Use this option to include modern attachments or linked files in the collection for further review.</span></span> <span data-ttu-id="b7b43-132">최신 첨부 파일과 관련된 검색 가능한 속성에 대한 자세한 내용은 [Advanced eDiscovery의](document-metadata-fields-in-Advanced-eDiscovery.md)문서 메타데이터 필드를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7b43-132">For more information about the searchable properties related to modern attachments, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="b7b43-133">리뷰 집합에 샘플 추가</span><span class="sxs-lookup"><span data-stu-id="b7b43-133">Add a sample to a review set</span></span>

<span data-ttu-id="b7b43-134">모든 검색 결과를 검토 집합에 추가하기 전에 검색 결과의 유효성을 보다 철저하게 검사하려는 경우 모든 검색 결과를 추가하는 대신 검토 집합에 검색 결과 샘플을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-134">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="b7b43-135">리뷰 집합에 샘플을 추가하려면 검색 탭에서 검색을 클릭하고 플라이아웃 페이지에서 **샘플을** 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="b7b43-135">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="b7b43-136">샘플링 **매개 변수 페이지에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-136">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="b7b43-137">**신뢰 수준 %** 및 신뢰 **구간 %** - 검토 집합에 추가된 항목은 설정한 통계 매개 변수에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-137">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="b7b43-138">일반적으로 결과를 샘플링할 때 신뢰 수준과 간격을 사용하는 경우 드롭다운 상자에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-138">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="b7b43-139">그렇지 않은 경우 기본 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-139">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="b7b43-140">**임의 샘플 %** - 리뷰 집합에 추가된 항목은 검색에서 반환된 총 항목 수에 대해 지정된 비율의 임의 선택을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-140">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="b7b43-141">이전 옵션 중 하나를 선택하고 구성한 후 검토 집합을 선택하여 샘플을 추가한 다음 보내기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7b43-141">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="b7b43-142">다시, 추가된 데이터에서  설정된 열을 검토하여 작업 탭 또는 검색 탭에서 진행 상황을 추적할 **수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="b7b43-142">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="b7b43-143">광학 문자 인식</span><span class="sxs-lookup"><span data-stu-id="b7b43-143">Optical character recognition</span></span>

<span data-ttu-id="b7b43-144">검색 결과를 검토 집합에 추가하면 Advanced eDiscovery의 OCR(광학 문자 인식) 기능이 이미지에서 텍스트를 자동으로 추출하고 리뷰 집합에 추가된 데이터가 포함된 이미지 텍스트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-144">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="b7b43-145">선택된 이미지 파일의 텍스트 뷰어에서 추출된 텍스트를 검토 집합에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-145">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="b7b43-146">이를 통해 이미지의 텍스트에 대한 추가 검토 및 분석을 수행 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-146">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="b7b43-147">느슨한 파일, 전자 메일 첨부 파일 및 포함된 이미지에 대해 OCR이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-147">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="b7b43-148">OCR에 지원되는 이미지 파일 형식 목록은 [Advanced eDiscovery에서](supported-filetypes-ediscovery20.md#image)지원되는 파일 형식을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7b43-148">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="b7b43-149">Advanced eDiscovery에서 만드는 각 사례에 대해 OCR 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-149">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="b7b43-150">자세한 내용은 검색 및 분석 [설정 구성을 참조하세요.](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)</span><span class="sxs-lookup"><span data-stu-id="b7b43-150">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
