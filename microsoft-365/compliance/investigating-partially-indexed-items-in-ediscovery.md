---
title: eDiscovery에서 부분적으로 인덱싱된 항목 조사
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
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: 조직 내에서 인덱싱된 항목(인덱싱되지 않은 항목이라고도 Exchange, SharePoint 및 비즈니스용 OneDrive 관리하는 방법을 학습합니다.
ms.openlocfilehash: 539fd2687735a5ee14be543750becca8c6c3154c
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311457"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="d4426-103">eDiscovery에서 부분적으로 인덱싱된 항목 조사</span><span class="sxs-lookup"><span data-stu-id="d4426-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="d4426-104">검색을 실행할 때 Microsoft 365 준수 센터에서 실행되는 eDiscovery 검색에는 예상 검색 결과에 부분적으로 인덱싱된 항목이 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="d4426-105">부분적으로 인덱싱된 항목은 Exchange 검색을 위해 완전히 인덱싱되지 않은 SharePoint 비즈니스용 OneDrive 사이트의 사서함 항목 및 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="d4426-106">대부분의 전자 메일 메시지와 사이트 문서는 전자 메일 메시지의 인덱싱 제한에 해당하기 때문에 성공적으로 [인덱싱됩니다.](limits-for-content-search.md#indexing-limits-for-email-messages)</span><span class="sxs-lookup"><span data-stu-id="d4426-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="d4426-107">그러나 일부 항목은 이러한 인덱싱 제한을 초과할 수 있으며 부분적으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="d4426-108">다음은 검색을 위해 항목을 인덱싱할 수 없는 다른 이유와 eDiscovery 검색을 실행할 때 부분적으로 인덱싱된 항목으로 반환되는 다른 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="d4426-109">전자 메일 메시지에 이미지 파일과 같은 유효한 처리기 없이 첨부된 파일이 있습니다. 부분적으로 인덱싱된 전자 메일 항목의 가장 일반적인 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="d4426-110">전자 메일 메시지에 첨부된 파일이 너무 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="d4426-111">전자 메일 메시지에 첨부된 파일이 너무 대용량입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="d4426-112">파일 형식 인덱싱은 지원되지만 특정 파일에 대해 인덱싱 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="d4426-113">대부분의 조직 고객은 볼륨별로 콘텐츠의 1% 미만을 차지하고 부분적으로 인덱싱되는 크기에 따라 콘텐츠의 12% 미만을 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="d4426-114">볼륨과 크기 간에 차이가 있는 이유는 파일이 크면 완전히 인덱싱할 수 없는 콘텐츠가 들어 있을 가능성이 더 높기 때문에 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="d4426-115">검색에 대해 부분적으로 인덱싱된 항목 수가 변경된 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d4426-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="d4426-116">eDiscovery 검색을 실행한 후 검색된 위치에서 부분적으로 인덱싱된 항목의 총 수와 크기가 검색에 대한 자세한 통계에 표시되는 검색 결과 통계에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="d4426-117">이러한 항목을 검색 통계에서  *인덱서되지*  않은 항목이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="d4426-118">다음은 검색 결과에 반환되는 부분적으로 인덱싱된 항목 수에 영향을 주는 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="d4426-119">항목이 부분적으로 인덱싱된 경우 검색 쿼리와 일치하는 항목은 검색 결과 항목의 개수 및 크기와 부분적으로 인덱싱된 항목에 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="d4426-120">그러나 동일한 검색 결과를 내보낼 때 항목은 검색 결과 집합에만 포함됩니다. 부분적으로 인덱싱된 항목으로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="d4426-121">SharePoint 및 OneDrive 사이트에 있는 부분적으로 인덱싱된  항목은 검색에 대한 세부 통계에 표시되는 부분적으로 인덱싱된 항목의 예상 항목에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-121">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="d4426-122">그러나 eDiscovery 검색 결과를 내보낼 때 부분적으로 인덱싱된 항목을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-122">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="d4426-123">예를 들어 사이트만 검색하는 경우 부분적으로 인덱싱된 예상 항목 수는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-123">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="d4426-124">조직에서 부분적으로 인덱싱된 항목의 비율 계산</span><span class="sxs-lookup"><span data-stu-id="d4426-124">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="d4426-125">부분적으로 인덱싱된 항목에 대한 조직의 노출을 이해하기 위해 빈 키워드 쿼리를 사용하여 모든 사서함의 모든 콘텐츠에 대한 검색을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-125">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="d4426-126">다음 예제에서는 1,629,904(146.46GB) 완전히 인덱싱된 항목과 부분적으로 인덱싱된 항목 10,025개(10.27GB)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-126">In the following example, there are 1,629,904 (146.46 GB) fully indexed items and 10,025 (10.27 GB) partially indexed items.</span></span>
  
![부분적으로 인덱싱된 항목을 표시하는 검색 통계의 예](../media/PartiallyIndexedItemsTest.png)
  
<span data-ttu-id="d4426-128">다음 계산을 사용하여 부분적으로 인덱싱된 항목의 백분율을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-128">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="d4426-129">**조직에서 부분적으로 인덱싱된 항목의 비율을 계산합니다.**</span><span class="sxs-lookup"><span data-stu-id="d4426-129">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(10025/1629904) x 100 = 0.62%`

<span data-ttu-id="d4426-130">이전 예의 검색 결과를 사용하여 모든 사서함 항목의 0.62%가 부분적으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-130">By using the search results from the previous example, 0.62% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="d4426-131">**조직에서 부분적으로 인덱싱된 항목의 크기 백분율을 계산합니다.**</span><span class="sxs-lookup"><span data-stu-id="d4426-131">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(10.27 GB/146.46 MB) x 100 = 7.0%`

<span data-ttu-id="d4426-132">따라서 이전 예에서는 사서함 항목의 전체 크기의 7%가 부분적으로 인덱싱된 항목에서 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-132">So in the previous example, 7% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="d4426-133">앞서 설명한 것 처럼 대부분의 조직 고객은 볼륨당 콘텐츠의 1% 미만을 차지하고 부분적으로 인덱싱된 크기에 따라 콘텐츠의 12% 미만을 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-133">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="d4426-134">부분적으로 인덱싱된 항목 작업</span><span class="sxs-lookup"><span data-stu-id="d4426-134">Working with partially indexed items</span></span>

<span data-ttu-id="d4426-135">부분적으로 항목을 검사하여 관련 정보가 없는지 검사해야 하는 경우 부분적으로 인덱싱된 항목에 대한 정보가 포함된 콘텐츠 검색 보고서를 내보낼 수 있습니다. [](export-a-content-search-report.md)</span><span class="sxs-lookup"><span data-stu-id="d4426-135">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="d4426-136">콘텐츠 검색 보고서를 내보낼 때 부분적으로 인덱싱된 항목을 포함하는 내보내기 옵션 중 하나를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-136">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![부분적으로 인덱싱된 항목을 내보내는 두 번째 또는 세 번째 옵션 선택](../media/PartiallyIndexedItemsExportOptions.png)
  
<span data-ttu-id="d4426-138">이러한 옵션 중 하나를 사용하여 eDiscovery 검색 결과 또는 검색 보고서를 내보낼 때 내보내기에는 Unindexed라는 보고서가 Items.csv.</span><span class="sxs-lookup"><span data-stu-id="d4426-138">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="d4426-139">이 보고서에는 파일과 대부분의 동일한 정보가 ResultsLog.csv 포함됩니다. 그러나 인덱싱되지 않은 Items.csv 파일에는 부분적으로 인덱싱된 항목과 관련된 두 개의 필드인 **오류 태그** 및 오류 **속성도 포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d4426-139">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="d4426-140">이러한 필드에는 부분적으로 인덱싱된 각 항목에 대한 인덱싱 오류에 대한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-140">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="d4426-141">이러한 두 필드의 정보를 사용하면 특정 인덱싱 오류가 조사에 영향을 미치는지 여부를 결정하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-141">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="d4426-142">이 경우 대상 검색을 수행하고 특정 전자 메일 메시지와 SharePoint 또는 OneDrive 문서를 검색하여 내보낼 수 있으므로 조사와 관련이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-142">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="d4426-143">단계별 지침은 에서 대상 검색을 위한 [CSV 파일 준비를 Office 365.](csv-file-for-an-id-list-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="d4426-143">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d4426-144">Unindexed Items.csv 파일에는 오류 유형 및 오류 메시지 **필드도** **포함되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d4426-144">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="d4426-145">이러한 필드는 오류 태그 및 오류 속성 필드의 정보와  비슷하지만 보다 자세한 정보를 포함하는 레거시 필드입니다. </span><span class="sxs-lookup"><span data-stu-id="d4426-145">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="d4426-146">이러한 레거시 필드는 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-146">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="d4426-147">부분적으로 인덱싱된 항목과 관련된 오류</span><span class="sxs-lookup"><span data-stu-id="d4426-147">Errors related to partially indexed items</span></span>

<span data-ttu-id="d4426-148">오류 태그는 오류와 파일 형식의 두 가지 정보로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-148">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="d4426-149">예를 들어 이 오류/파일 형식 쌍의 경우:</span><span class="sxs-lookup"><span data-stu-id="d4426-149">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="d4426-150">`parseroutputsize` 는 오류가 발생한 파일의 파일 `xls` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-150">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="d4426-151">파일 형식이 인식되지 않았거나 파일 형식이 오류에 적용되지 않은 경우 파일 형식 대신 값이 `noformat` 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-151">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="d4426-152">다음은 인덱싱 오류 목록과 오류의 가능한 원인에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-152">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="d4426-153">오류 태그</span><span class="sxs-lookup"><span data-stu-id="d4426-153">Error tag</span></span> | <span data-ttu-id="d4426-154">설명</span><span class="sxs-lookup"><span data-stu-id="d4426-154">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="d4426-155">전자 메일 메시지에 첨부 파일이 너무 많고 이러한 첨부 파일 중 일부는 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-155">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="d4426-156">콘텐츠 검색기 및 문서 파서에서 다른 첨부 파일 내에 중첩된 너무 많은 수준의 첨부 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-156">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="d4426-157">이러한 첨부 파일 중 일부는 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-157">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="d4426-158">첨부 파일이 RMS로 보호되어 디코딩에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-158">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="d4426-159">전자 메일 메시지에 첨부된 파일이 너무 크며 처리될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-159">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="d4426-160">처리된 전자 메일 메시지를 인덱스에 쓸 때 인덱싱 가능한 속성 중 하나에 너무 크며 잘리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-160">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="d4426-161">이 속성은 오류 속성 필드에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-161">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="d4426-162">전자 메일 메시지에 유효한 유니코드로 처리될 수 없는 텍스트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-162">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="d4426-163">이 항목에 대한 인덱싱이 불완전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-163">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="d4426-164">첨부 파일 또는 전자 메일 메시지의 콘텐츠가 암호화되며 Microsoft 365 디코딩할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-164">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="d4426-165">구문 분석하는 동안 알 수 없는 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-165">An unknown error occurred during parsing.</span></span> <span data-ttu-id="d4426-166">이는 일반적으로 소프트웨어 버그 또는 서비스 충돌의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-166">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="d4426-167">첨부 파일이 너무 까다로우면 파서에서 처리할 수 없습니다. 이 첨부 파일을 구문 분석하지 않았거나 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-167">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="d4426-168">첨부 파일이 오작동하여 파서에서 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-168">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="d4426-169">이 결과는 이전 파일 형식, 비호호화 소프트웨어로 만든 파일 또는 클레임된 것 외의 바이러스로 인해 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-169">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="d4426-170">첨부 파일 구문 분석의 출력이 너무 크며 잘라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-170">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="d4426-171">첨부 파일에 검색할 수 Microsoft 365 파일 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-171">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="d4426-172">첨부 파일에 검색할 수 있는 Office 365 형식이 있지만 해당 파일 형식의 구문 분석은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-172">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="d4426-173">Exchange Store의 전자 메일 속성 값이 너무 크면 검색할 수 없는 경우 메시지를 처리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-173">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="d4426-174">이 작업은 일반적으로 전자 메일 메시지의 본문 속성에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-174">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="d4426-175">콘텐츠 검색기에서 RMS로 보호된 메시지를 디코딩하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-175">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="d4426-176">문서에서 인덱싱하는 동안 단어가 너무 많이 식별되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-176">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="d4426-177">제한에 도달하면 속성 처리가 중지된 후 속성이 끊어지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-177">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="d4426-178">오류 필드는 오류 태그 필드에 나열된 처리 오류의 영향을 받는 필드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-178">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="d4426-179">또는 같은 속성을 검색하는 경우 메시지 본문의 오류는 검색 결과에 영향을  `subject`  `participants` 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-179">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="d4426-180">이 기능은 추가로 조사해야 할 부분적으로 인덱싱된 항목을 정확하게 결정할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-180">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="d4426-181">PowerShell 스크립트를 사용하여 부분적으로 인덱싱된 전자 메일 항목에 대한 조직의 노출 확인</span><span class="sxs-lookup"><span data-stu-id="d4426-181">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="d4426-182">다음 단계에서는 모든 Exchange 사서함의 모든 항목을 검색한 다음 조직에서 부분적으로 인덱싱된 전자 메일 항목의 비율(개수 및 크기별로)에 대한 보고서를 생성하고 발생하는 각 인덱싱 오류에 대한 항목 수 및 해당 파일 형식을 표시하는 PowerShell 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-182">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="d4426-183">이전 섹션의 오류 태그 설명을 사용하여 인덱싱 오류를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-183">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="d4426-184">파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `PartiallyIndexedItems.ps1` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-184">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

   ```powershell
     write-host "**************************************************"
     write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "**************************************************"
     " " 
     # Create a search with Error Tags Refinders enabled
     Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
     New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
     Start-ComplianceSearch "RefinerTest"
     # Loop while search is in progress
     do{
         Write-host "Waiting for search to complete..."
         Start-Sleep -s 5
         $complianceSearch = Get-ComplianceSearch "RefinerTest"
     }while ($complianceSearch.Status -ne 'Completed')
     $refiners = $complianceSearch.Refiners | ConvertFrom-Json
     $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
     $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
     $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
     " "
     "===== Partially indexed items ====="
     "         Total          Ratio"
     "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
     "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
     " "
     Write-Host ===== Reasons for partially indexed items =====
     foreach($errorTagProperty in $errorTagProperties)
     {
         $name = $refiners.Entries.($errorTagProperty.Name).Name
         $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
         $frag = $name.Split("{_}")
         $errorTag = $frag[0]
         $fileType = $frag[1]
         if ($errorTag -ne $lastErrorTag)
         {
             $errorTag
         }
         "    " + $fileType + " => " + $count
         $lastErrorTag = $errorTag
     }
   ```

2. <span data-ttu-id="d4426-185">[보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/exchange-online-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-185">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

3. <span data-ttu-id="d4426-186">보안 & 준수 센터 PowerShell에서 1단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d4426-186">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="d4426-187">다음은 스크립트에서 반환된 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-187">Here's an example fo the output returned by the script.</span></span>
  
![부분적으로 인덱싱된 전자 메일 항목에 대한 조직의 노출에 대한 보고서를 생성하는 스크립트의 출력 예](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="d4426-189">다음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="d4426-189">Note the following:</span></span>
>  
> - <span data-ttu-id="d4426-190">전자 메일 항목의 총 수와 크기, 부분적으로 인덱싱된 전자 메일 항목의 조직 비율(개수 및 크기)입니다.</span><span class="sxs-lookup"><span data-stu-id="d4426-190">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="d4426-191">목록 오류 태그 및 오류가 발생한 해당 파일 형식</span><span class="sxs-lookup"><span data-stu-id="d4426-191">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4426-192">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4426-192">See also</span></span>

[<span data-ttu-id="d4426-193">eDiscovery에서 부분적으로 인덱싱된 항목</span><span class="sxs-lookup"><span data-stu-id="d4426-193">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)