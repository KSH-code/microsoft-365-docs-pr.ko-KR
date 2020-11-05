---
title: EDiscovery에서 부분적으로 인덱싱된 항목 조사
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
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
description: 조직 내의 Exchange, SharePoint 및 비즈니스용 OneDrive에서 부분적으로 인덱싱된 (또는 인덱싱되지 않은) 항목을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: bbf234e2051cd103d1b99ab75b8e5c15365762a9
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920000"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="a7e64-103">EDiscovery에서 부분적으로 인덱싱된 항목 조사</span><span class="sxs-lookup"><span data-stu-id="a7e64-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="a7e64-104">Microsoft 365 준수 센터에서 실행 하는 eDiscovery 검색은 검색을 실행할 때 예상 되는 검색 결과에 부분적으로 인덱싱된 항목을 자동으로 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="a7e64-105">부분적으로 인덱싱된 항목은 Exchange 사서함 항목 및 SharePoint의 문서와 몇 가지 이유로 검색을 위해 완전히 인덱싱되지 않은 비즈니스용 OneDrive 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="a7e64-106">대부분의 전자 메일 메시지와 사이트 문서는 [전자 메일 메시지에 대 한 인덱싱 제한](limits-for-content-search.md#indexing-limits-for-email-messages)범위 내에 있으므로 성공적으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="a7e64-107">그러나 일부 항목은 이러한 인덱싱 제한을 초과할 수 있으며 부분적으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="a7e64-108">다음은 eDiscovery 검색을 실행할 때 항목을 검색용으로 인덱싱하지 않아 부분적으로 인덱싱된 항목으로 반환 하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="a7e64-109">전자 메일 메시지에는 이미지 파일과 같은 유효한 처리기가 없는 첨부 파일이 있습니다. 부분적으로 인덱싱된 전자 메일 항목의 가장 일반적인 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>

- <span data-ttu-id="a7e64-110">전자 메일 메시지에 첨부 된 파일이 너무 많음</span><span class="sxs-lookup"><span data-stu-id="a7e64-110">Too many files attached to an email message</span></span>

- <span data-ttu-id="a7e64-111">전자 메일 메시지에 첨부 된 파일이 너무 큽니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-111">A file attached to an email message is too large</span></span>

- <span data-ttu-id="a7e64-112">파일 형식이 인덱싱에 대해 지원 되지만 특정 파일에 대해 인덱싱 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-112">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>

<span data-ttu-id="a7e64-113">이는 다를 수 있지만 대부분의 조직 고객은 볼륨 별로 콘텐츠가 1% 미만이 고 부분적으로 인덱싱되는 크기의 콘텐츠 중 12% 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="a7e64-114">볼륨과 크기 간의 차이점은 큰 파일의 경우 완전히 인덱싱할 수 없는 콘텐츠가 포함 될 가능성이 높기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="a7e64-115">검색에서 부분적으로 인덱싱된 항목 수가 변경 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="a7e64-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="a7e64-116">EDiscovery 검색을 실행 하 고 나면 검색 된 위치에 있는 부분적으로 인덱싱된 항목의 총 수와 크기는 search에 대 한 자세한 통계에 표시 되는 검색 결과 통계에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="a7e64-117">참고 이러한 항목은 검색 통계에서  *인덱싱되지 않은 항목이*  라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="a7e64-118">검색 결과에서 반환 되는 부분적으로 인덱싱된 항목의 수에 영향을 주는 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="a7e64-119">항목이 부분적으로 인덱싱되 고 검색 쿼리와 일치 하는 경우 검색 결과 항목 및 부분적으로 인덱싱된 항목의 개수와 크기 모두에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="a7e64-120">그러나 같은 검색의 결과를 내보내면 항목은 검색 결과 집합에만 포함 됩니다. 부분적으로 인덱싱된 항목은 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="a7e64-121">키워드 쿼리 또는 조건을 사용 하 여 검색 쿼리의 날짜 범위를 지정 하는 경우 날짜 범위와 일치 하지 않는 부분적으로 인덱싱된 항목이 부분적으로 인덱싱된 항목의 수에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-121">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="a7e64-122">날짜 범위 내에 속하는 부분적으로 인덱싱된 항목만 부분 인덱싱된 항목의 수에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-122">Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>

> [!NOTE]
> <span data-ttu-id="a7e64-123">SharePoint 및 OneDrive 사이트에 있는 부분적으로 인덱싱된 항목은 검색에 대 한 자세한 통계에 표시 되는 부분적으로 인덱싱된 항목의 예상 기간에 포함 *되지 않습니다* .</span><span class="sxs-lookup"><span data-stu-id="a7e64-123">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="a7e64-124">그러나 eDiscovery 검색의 결과를 내보낼 때 부분적으로 인덱싱된 항목을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-124">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="a7e64-125">예를 들어, 사이트만 검색 하는 경우에는 부분 인덱싱된 항목의 예상 수는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-125">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="a7e64-126">조직에서 부분적으로 인덱싱된 항목의 비율 계산</span><span class="sxs-lookup"><span data-stu-id="a7e64-126">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="a7e64-127">부분적으로 인덱싱된 항목에 대 한 조직의 노출을 이해 하려면 빈 키워드 쿼리를 사용 하 여 모든 사서함의 모든 콘텐츠에 대해 검색을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-127">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="a7e64-128">아래 아래의 예제에는 56208 (4830 MB) 완전히 인덱싱된 항목 및 470 316 (5MB) 부분 인덱싱된 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-128">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![부분적으로 인덱싱된 항목을 보여 주는 검색 통계 예제](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="a7e64-130">다음 계산을 사용 하 여 부분적으로 인덱싱된 항목의 백분율을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-130">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="a7e64-131">**조직에서 부분적으로 인덱싱된 항목의 비율을 계산 하려면 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a7e64-131">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

<span data-ttu-id="a7e64-132">이전 예제의 검색 결과를 사용 하 여. 모든 사서함의 84% 항목이 부분적으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-132">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="a7e64-133">**조직에서 부분적으로 인덱싱된 항목의 크기 비율을 계산 하려면 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a7e64-133">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="a7e64-134">따라서 위 예에서 전체 사서함 항목 크기의 6.54%는 부분적으로 인덱싱된 항목에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-134">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="a7e64-135">앞에서 설명한 것 처럼 대부분의 조직 고객은 볼륨 별로 콘텐츠가 1% 미만이 고 부분적으로 인덱싱되는 크기의 콘텐츠 중 12% 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-135">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="a7e64-136">부분적으로 인덱싱된 항목 사용</span><span class="sxs-lookup"><span data-stu-id="a7e64-136">Working with partially indexed items</span></span>

<span data-ttu-id="a7e64-137">일부 항목을 검사 하 여 관련 정보가 포함 되어 있지 않은지 확인 해야 하는 경우에는 부분적으로 인덱싱된 항목에 대 한 정보가 포함 된 [콘텐츠 검색 보고서를 내보낼](export-a-content-search-report.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-137">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="a7e64-138">콘텐츠 검색 보고서를 내보낼 때는 부분적으로 인덱싱된 항목이 포함 된 내보내기 옵션 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-138">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![두 번째 또는 세 번째 옵션을 선택 하 여 부분적으로 인덱싱된 항목 내보내기](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="a7e64-140">이러한 옵션 중 하나를 사용 하 여 eDiscovery 검색 결과 또는 검색 보고서를 내보낼 때 내보내기에는 인덱싱되지 Items.csv 라는 보고서가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-140">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="a7e64-141">이 보고서에는 ResultsLog.csv 파일과 같은 대부분의 정보가 포함 되어 있습니다. 그러나 인덱싱되지 않은 Items.csv 파일에는 부분 인덱싱된 항목과 관련 된 두 개의 필드인 **오류 태그** 및 **오류 속성이** 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-141">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="a7e64-142">이러한 필드에는 부분적으로 인덱싱된 각 항목의 인덱싱 오류에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-142">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="a7e64-143">이러한 두 필드의 정보를 사용 하 여 특정 사항에 대 한 인덱싱 오류가 조사에 영향을 미치는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-143">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="a7e64-144">이 경우에는 대상 검색을 수행 하 고 특정 전자 메일 메시지와 SharePoint 또는 OneDrive 문서를 검색 하 고 내보내서 조사와 관련이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-144">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="a7e64-145">단계별 지침은 [Office 365에서 대상 지정 검색용 CSV 파일 준비](csv-file-for-an-id-list-content-search.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7e64-145">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a7e64-146">또한 인덱싱되지 않은 Items.csv 파일에는 **오류 유형** 및 **오류 메시지** 라는 필드도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-146">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="a7e64-147">이러한 필드는 **오류 태그** 및 **오류 속성** 필드의 정보와 유사 하지만 자세한 정보를 포함 하는 레거시 필드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-147">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="a7e64-148">이러한 레거시 필드는 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-148">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="a7e64-149">부분적으로 인덱싱된 항목과 관련 된 오류</span><span class="sxs-lookup"><span data-stu-id="a7e64-149">Errors related to partially indexed items</span></span>

<span data-ttu-id="a7e64-150">Error 태그는 두 가지 정보, 오류 및 파일 형식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-150">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="a7e64-151">예를 들어 다음 오류/filetype 쌍에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-151">For example, in this error/filetype pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="a7e64-152">`parseroutputsize` 은 오류이 고 `xls` 오류가 발생 한 파일의 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-152">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="a7e64-153">파일 형식이 인식 되지 않았거나 파일 형식이 오류에 적용 되지 않는 경우에는 파일 형식 대신 값이 표시 됩니다 `noformat` .</span><span class="sxs-lookup"><span data-stu-id="a7e64-153">In cases were the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="a7e64-154">다음은 인덱싱 오류 목록과 오류의 가능한 원인에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-154">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="a7e64-155">**Error 태그**</span><span class="sxs-lookup"><span data-stu-id="a7e64-155">**Error tag**</span></span>|<span data-ttu-id="a7e64-156">**설명**</span><span class="sxs-lookup"><span data-stu-id="a7e64-156">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="a7e64-157">전자 메일 메시지의 첨부 파일이 너무 많고 이러한 첨부 파일 중 일부가 처리 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-157">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="a7e64-158">콘텐츠 검색기 및 문서 파서가 다른 첨부 파일 내에 중첩 된 첨부 파일의 수준을 너무 많이 검색 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-158">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="a7e64-159">이러한 첨부 파일 중 일부가 처리 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-159">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="a7e64-160">첨부 파일이 RMS 보호 되었기 때문에 디코딩에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-160">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="a7e64-161">전자 메일 메시지에 첨부 된 파일이 너무 커서 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-161">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="a7e64-162">처리 된 전자 메일 메시지를 인덱스에 쓸 때 인덱싱 가능한 속성 중 하나가 너무 커서 잘렸습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-162">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="a7e64-163">잘린 속성은 오류 속성 필드에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-163">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="a7e64-164">유효한 유니코드로 처리할 수 없는 텍스트가 포함 된 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="a7e64-164">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="a7e64-165">이 항목에 대 한 인덱싱이 불완전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-165">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="a7e64-166">첨부 파일 또는 전자 메일 메시지의 내용이 암호화 되 고 Microsoft 365에서 콘텐츠를 디코딩할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-166">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="a7e64-167">구문 분석 중 알 수 없는 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-167">An unknown error occurred during parsing.</span></span> <span data-ttu-id="a7e64-168">이는 일반적으로 소프트웨어 버그나 서비스 중단으로 인해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-168">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="a7e64-169">파서가 처리할 수 없는 첨부 파일이 너무 커서 해당 첨부 파일의 구문 분석이 발생 하지 않았거나 완료 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-169">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="a7e64-170">첨부 파일이 잘못 되었거나 파서에서 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-170">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="a7e64-171">이 결과는 이전 파일 형식, 호환 되지 않는 소프트웨어에서 만든 파일 또는 요청 되지 않은 것으로 가장 된 바이러스로 인해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-171">This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="a7e64-172">첨부 파일의 구문 분석 출력이 너무 커서 잘렸습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-172">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="a7e64-173">첨부 파일이 Microsoft 365에서 검색할 수 없는 파일 형식을 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-173">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="a7e64-174">첨부 파일 형식이 Office 365에서 검색할 수 있지만 해당 파일 형식이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-174">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="a7e64-175">Exchange 스토어의 전자 메일 속성 값이 너무 커서 검색할 수 없으며 메시지를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-175">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="a7e64-176">일반적으로 전자 메일 메시지의 body 속성에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-176">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="a7e64-177">콘텐츠 검색기에서 RMS 보호 메시지를 디코딩하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-177">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="a7e64-178">색인 중에 너무 많은 단어가 문서에 식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-178">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="a7e64-179">제한에 도달 하면 속성 처리가 중지 되 고 속성이 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-179">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="a7e64-180">오류 필드에는 오류 태그 필드에 나열 된 처리 오류의 영향을 받는 필드에 대 한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-180">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="a7e64-181">또는와 같은 속성을 검색 하는  `subject` 경우  `participants` 메시지 본문의 오류는 검색 결과에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-181">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="a7e64-182">이는 추가로 조사 해야 하는 부분적으로 인덱싱된 항목을 정확히 결정할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-182">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="a7e64-183">PowerShell 스크립트를 사용 하 여 부분적으로 인덱싱된 전자 메일 항목에 대 한 조직의 노출을 확인</span><span class="sxs-lookup"><span data-stu-id="a7e64-183">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="a7e64-184">다음 단계에서는 모든 Exchange 사서함의 모든 항목을 검색 하는 PowerShell 스크립트를 실행 한 다음 조직에서 부분적으로 인덱싱된 전자 메일 항목 (개수 및 크기)에 대 한 보고서를 생성 하 고 발생 하는 각 인덱싱 오류에 대 한 항목 수 (파일 형식)를 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-184">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="a7e64-185">이전 섹션의 오류 태그 설명을 사용 하 여 인덱싱 오류를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-185">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="a7e64-186">파일 이름 접미사. p s 1을 사용 하 여 Windows PowerShell 스크립트 파일에 다음 텍스트를 저장 합니다. 예를 들면 `PartiallyIndexedItems.ps1` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-186">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="a7e64-187">[보안 및 준수 센터 PowerShell에 연결](https://go.microsoft.com/fwlink/p/?linkid=627084)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-187">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>

3. <span data-ttu-id="a7e64-188">보안 & 준수 센터 PowerShell에서 1 단계에서 스크립트를 저장 한 폴더로 이동한 후 스크립트를 실행 합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="a7e64-188">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

<span data-ttu-id="a7e64-189">스크립트에서 반환 하는 출력의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-189">Here's an example fo the output returned by the script.</span></span>
  
![조직에서 부분적으로 인덱싱된 전자 메일 항목에 대 한 보고서를 생성 하는 스크립트의 출력 예](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="a7e64-191">다음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="a7e64-191">Note the following:</span></span>
  
1. <span data-ttu-id="a7e64-192">전자 메일 항목의 총 수와 크기 및 조직의 부분적으로 인덱싱된 전자 메일 항목의 비율 (개수 및 크기)</span><span class="sxs-lookup"><span data-stu-id="a7e64-192">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>

2. <span data-ttu-id="a7e64-193">오류 태그와 오류가 발생 한 해당 파일 형식을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e64-193">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7e64-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7e64-194">See also</span></span>

[<span data-ttu-id="a7e64-195">EDiscovery에서 부분적으로 인덱싱된 항목</span><span class="sxs-lookup"><span data-stu-id="a7e64-195">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)
