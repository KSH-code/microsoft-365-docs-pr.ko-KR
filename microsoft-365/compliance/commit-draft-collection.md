---
title: 검토 집합에 초안 컬렉션 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 초안 컬렉션을 만들고 이 컬렉션을 다시 작성한 후 검토 집합으로 커밋할 수 있습니다. 초안 컬렉션을 커밋하면 수집된 항목이 사례의 검토 집합에 추가됩니다. 수집된 항목이 검토 집합에 들어오면 분석, 검토 및 내보낼 수 있습니다.
ms.openlocfilehash: e28592e7aac289bfc0cc29d312963fa21d9f8fd4
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838889"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="c438a-105">초안 컬렉션을 임시 검토 집합에 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c438a-105">Commit a draft collection to a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="c438a-106">초안 컬렉션에서 수집한 항목에 만족하고 이를 분석, 태그 및 검토할 준비가 된 경우 사례의 검토 집합에 컬렉션을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-106">When you're satisfied with the items you've collected in a draft collection and are ready to analyze, tag, and review them, you can add a collection to a review set in the case.</span></span> <span data-ttu-id="c438a-107">초안 컬렉션을 검토 집합에 커밋하면 수집된 항목이 검토 집합의 원래 콘텐츠 위치에서 Microsoft 365 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-107">When you commit a draft collection to a review set, collected items are copied from their original content location in Microsoft 365 to a review set.</span></span> <span data-ttu-id="c438a-108">검토 집합은 Microsoft 클라우드에서 microsoft에서 제공하는 안전한 Azure Storage 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-108">A review set is a secure, Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>

## <a name="commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="c438a-109">검토 집합에 초안 컬렉션 사용</span><span class="sxs-lookup"><span data-stu-id="c438a-109">Commit a draft collection to a review set</span></span>

1. <span data-ttu-id="c438a-110">준수 Microsoft 365 센터에서 Advanced eDiscovery 사례를 연 다음 컬렉션 탭을  선택하여 해당 사례의 컬렉션 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-110">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, and then select the **Collections** tab to display a list of the collections in the case.</span></span>

   ![사례의 컬렉션 목록](../media/CommitDraftCollections1.png)

   > [!TIP]
   > <span data-ttu-id="c438a-112">상태 열의 값은 검토 집합에 추가할 수 있는 초안 `Estimated` 컬렉션을 식별합니다. </span><span class="sxs-lookup"><span data-stu-id="c438a-112">A value of `Estimated` in the **Status** column identifies the draft collections that can be added to a review set.</span></span> <span data-ttu-id="c438a-113">상태는 컬렉션이 검토 집합에 이미 추가된 `Committed` 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-113">A status of `Committed` indicates that a collection has already been added to a review set.</span></span>

2. <span data-ttu-id="c438a-114">컬렉션 **페이지에서** 검토 집합에 커밋할 초안 컬렉션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-114">On the **Collections** page, select the draft collection that you want to commit to a review set.</span></span>

3. <span data-ttu-id="c438a-115">플라이아웃 페이지의 아래쪽에서 **Actions**  >  **Edit 컬렉션 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c438a-115">On the bottom of the flyout page, select **Actions** > **Edit collection**.</span></span>

4. <span data-ttu-id="c438a-116">컬렉션 편집 마법사에서 **초안** 저장 또는 수집 페이지가 **표시될 때까지 다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-116">In the edit collection wizard, click **Next** until the **Save draft or collect** page is displayed.</span></span>

5. <span data-ttu-id="c438a-117">다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-117">Configure the following settings:</span></span>

   1. <span data-ttu-id="c438a-118">항목 **수집을 선택하고 검토 집합에 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c438a-118">Select **Collect items and add to review set**.</span></span>

   2. <span data-ttu-id="c438a-119">컬렉션을 제출한 후 새로 작성된 검토 집합에 컬렉션을 추가할지 아니면 기존 검토 집합에 추가할지 여부를 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="c438a-119">Decide whether to add the collection to a new review set (which is created after you submit the collection) or to an existing review set.</span></span> <span data-ttu-id="c438a-120">결정에 따라 이 섹션을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-120">Complete this section based on your decision.</span></span>

   3. <span data-ttu-id="c438a-121">추가 컬렉션 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-121">Configure the additional collection settings:</span></span>

       - <span data-ttu-id="c438a-122">**Teams** 및 Yammer 메시지: 컬렉션에 검색 쿼리에서 반환된 채팅 항목이 포함된 대화 스레드를 컬렉션에 추가하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-122">**Teams and Yammer messages**: Select this option to add conversation threads to the collection that include the chat items returned by the search query in the collection.</span></span> <span data-ttu-id="c438a-123">즉, 검색 조건과 일치하는 항목이 포함된 채팅 대화가 재구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-123">This means that the chat conversation that contains items that match the search criteria is reconstructed.</span></span> <span data-ttu-id="c438a-124">이렇게 하면 대화의 컨텍스트에서 채팅 항목을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-124">This lets you review chat items in the context of the back and forth conversation.</span></span> <span data-ttu-id="c438a-125">자세한 내용은 에서 [대화 스레딩을 Advanced eDiscovery.](conversation-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="c438a-125">For more information, see [Conversation threading in Advanced eDiscovery](conversation-review-sets.md).</span></span>

       - <span data-ttu-id="c438a-126">**클라우드 첨부 파일:** 컬렉션 결과가 검토 집합에 추가될 때 최신 첨부 파일 또는 연결된 파일을 포함하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-126">**Cloud attachments**: Select this option to include modern attachments or linked files when the collection results are added to the review set.</span></span> <span data-ttu-id="c438a-127">즉, 최신 첨부 파일 또는 연결된 파일의 대상 파일이 검토 집합에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-127">This means that the target file of a modern attachment or linked file is added to the review set.</span></span>

       - <span data-ttu-id="c438a-128">**SharePoint 버전:** 컬렉션의 버전 제한 및 검색 매개 변수에 따라 SharePoint 문서의 모든 버전 컬렉션을 사용하도록 설정하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-128">**SharePoint versions**: Select this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="c438a-129">이 옵션을 선택하면 검토 집합에 추가된 항목의 크기가 크게 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-129">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

   4. <span data-ttu-id="c438a-130">검토 집합에 추가할 컬렉션의 배율을 정의하도록 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-130">Configure the settings to define the scale of the collection to add to the review set:</span></span>

      - <span data-ttu-id="c438a-131">**모든 컬렉션 결과 추가:** 컬렉션의 검색 조건과 일치하는 모든 항목을 검토 집합에 추가하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-131">**Add all collection results**: Select this option to add all the items that match the search criteria of the collection to the review set.</span></span>

      - <span data-ttu-id="c438a-132">**컬렉션 결과 샘플** 추가: 모든 결과를 추가하는 대신 검토 집합에 컬렉션 결과 샘플을 추가하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-132">**Add a sample of the collection results**: Select this option to add a sample of the collection results to the review set instead of adding all results.</span></span> <span data-ttu-id="c438a-133">이 옵션을 선택하는 경우 샘플 **매개** 변수 편집을 클릭하고 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-133">If you select this option, click **Edit sample parameters** and choose one of the following options:</span></span>

         - <span data-ttu-id="c438a-134">**신뢰도 기반** 샘플: 컬렉션의 항목이 검토 집합에 추가되면 설정한 통계 매개 변수에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-134">**Sample based on confidence**: Items from the collection are added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="c438a-135">일반적으로 결과를 샘플링할 때 신뢰 수준과 간격을 사용하는 경우 드롭다운 상자에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-135">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="c438a-136">그렇지 않은 경우 기본 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-136">Otherwise, use the default settings.</span></span>

         - <span data-ttu-id="c438a-137">**임의** 샘플: 컬렉션의 항목은 검색에서 반환된 총 항목 수에 대해 지정된 비율의 임의 선택에 따라 검토 집합에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-137">**Randomly sample**: Items from the collection are added to the review set based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

6. <span data-ttu-id="c438a-138">컬렉션 **검토 페이지에서** 이전 페이지에서 구성한 컬렉션 설정을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-138">On the **Review your collection** page, you can review the collection settings that you configured on the previous page.</span></span> <span data-ttu-id="c438a-139">**변경하려면** 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-139">Click **Edit** if you want to change them.</span></span>

7. <span data-ttu-id="c438a-140">**제출을** 클릭하여 초안 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-140">Click **Submit** to create the draft collection.</span></span> <span data-ttu-id="c438a-141">컬렉션이 만들어졌다는 확인 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-141">A page is displayed confirming that the collection was created.</span></span>

## <a name="what-happens-after-you-commit-a-draft-collection"></a><span data-ttu-id="c438a-142">초안 컬렉션을 커밋한 후 발생하는 일</span><span class="sxs-lookup"><span data-stu-id="c438a-142">What happens after you commit a draft collection</span></span>

<span data-ttu-id="c438a-143">초안 컬렉션을 검토 집합에 커밋하면 다음과 같은 상황이 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-143">When you commit a draft collection to a review set, the following things happen:</span></span>

- <span data-ttu-id="c438a-144">컬렉션 검색 쿼리가 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-144">The collection search query is run again.</span></span> <span data-ttu-id="c438a-145">즉, 검토 집합에 복사된 실제 검색 결과는 컬렉션 검색이 마지막으로 실행될 때 반환된 예상 결과와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-145">This means the actual search results copied to the review set may be different than the estimated results that were returned when the collection search was last run.</span></span>

- <span data-ttu-id="c438a-146">검색 결과의 모든 항목은 라이브 서비스의 원본 데이터 원본에서 복사되어 Microsoft 클라우드의 보안 Azure Storage 위치에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-146">All items in the search results are copied from the original data source in the live service, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="c438a-147">문서 또는 비관리 데이터 원본에 없는 모든 항목(콘텐츠 및 메타데이터 포함)은 사례 데이터를 검토하는 동안 검토 집합의 모든 데이터를 완전히 검색할 수 있도록 깊이 인덱싱이라는 프로세스에서 다시 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-147">All items (including the content and metadata) that aren't located in custodian or non-custodian data sources are reindexed (in a process called *deep indexing*) so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="c438a-148">컬렉션의 콘텐츠를 다시 인덱스하면 사례 조사 중에 검토 집합의 콘텐츠를 검색하거나 필터링할 때 철저하고 빠른 검색이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-148">Reindexing the content in a collection results in thorough and fast searches when you search or filter the content in the review set during the case investigation.</span></span>

- <span data-ttu-id="c438a-149">암호화된 SharePoint OneDrive 문서 및 암호화된 파일 첨부 전자 메일 메시지는 컬렉션을 검토 집합에 커밋할 때 암호가 해독됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-149">Encrypted SharePoint and OneDrive documents and encrypted files attached email messages that's returned in the search results are decrypted when you commit the collection to a review set.</span></span> <span data-ttu-id="c438a-150">검토 집합에서 암호 해독된 파일을 검토하고 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-150">You can review and query the decrypted files in the review set.</span></span> <span data-ttu-id="c438a-151">자세한 내용은 [eDiscovery](ediscovery-decryption.md)도구에서 암호 Microsoft 365 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c438a-151">For more information, see [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).</span></span>

- <span data-ttu-id="c438a-152">OCR(광학 문자 인식) 기능은 이미지에서 텍스트를 추출하고 검토 집합에 추가된 콘텐츠와 함께 이미지 텍스트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-152">Optical character recognition (OCR) functionality extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="c438a-153">자세한 내용은 이 문서의 광학 문자 [인식](#optical-character-recognition) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c438a-153">For more information, see the [Optical character recognition](#optical-character-recognition) section in this article.</span></span>

- <span data-ttu-id="c438a-154">커밋이 완료되면 컬렉션 탭의 상태 열 값이 로  `Committed` 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-154">After the commit is successfully completed, the value of the status column of on the **Collections** tab is changed to `Committed`.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="c438a-155">광학 문자 인식</span><span class="sxs-lookup"><span data-stu-id="c438a-155">Optical character recognition</span></span>

<span data-ttu-id="c438a-156">검토 집합에 컬렉션을 커밋하면 검토 집합에 추가된 콘텐츠와 함께 이미지에서 Advanced eDiscovery 자동으로 추출되는 OCR(광학 문자 인식) 기능이 이미지에서 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-156">When you commit a collection to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="c438a-157">선택된 이미지 파일의 텍스트 뷰어에서 추출된 텍스트를 검토 집합에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-157">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="c438a-158">따라서 이미지의 텍스트를 추가로 검토하고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-158">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="c438a-159">느슨한 파일, 전자 메일 첨부 파일 및 포함된 이미지에 대해 OCR이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-159">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="c438a-160">OCR에 지원되는 이미지 파일 형식 목록은 [고급 eDiscovery에서 지원되는 파일 형식](supported-filetypes-ediscovery20.md#image)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c438a-160">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="c438a-161">고급 eDiscovery에서 만든 각 사례에 대해 OCR 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c438a-161">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="c438a-162">자세한 내용은 검색 및 분석 [설정 구성을 참조하세요.](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)</span><span class="sxs-lookup"><span data-stu-id="c438a-162">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
