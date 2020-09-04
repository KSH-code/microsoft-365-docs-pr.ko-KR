---
title: Advanced eDiscovery 제한
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
description: Microsoft 365의 고급 eDiscovery 솔루션에 적용 되는 사례 제한, 인덱싱 제한 및 검색 제한에 대해 알아봅니다.
ms.openlocfilehash: c139480f18e0e6d94aae5a38d5fd636fbc62b2dc
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358476"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="46ed6-103">Advanced eDiscovery 제한 사항</span><span class="sxs-lookup"><span data-stu-id="46ed6-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="46ed6-104">이 문서에서는 Microsoft 365의 고급 eDiscovery 솔루션에 대 한 제한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="46ed6-105">사례 및 검토 제한 설정</span><span class="sxs-lookup"><span data-stu-id="46ed6-105">Case and review set limits</span></span>

<span data-ttu-id="46ed6-106">다음 표에는 Advanced eDiscovery의 사례 및 검토 집합에 대 한 제한이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="46ed6-107">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="46ed6-107">**Description of limit**</span></span>|<span data-ttu-id="46ed6-108">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="46ed6-108">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="46ed6-109">사례에 추가할 수 있는 총 문서 수 (사례에서 모든 검토 집합의 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="46ed6-110">3백만 개</span><span class="sxs-lookup"><span data-stu-id="46ed6-110">3 million</span></span> <br/> |
|<span data-ttu-id="46ed6-111">부하 집합 당 총 파일 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-111">Total file size per load set.</span></span> <span data-ttu-id="46ed6-112">여기에는 비 Office 365을 검토 집합으로 로드 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="46ed6-113">300GB</span><span class="sxs-lookup"><span data-stu-id="46ed6-113">300 GB</span></span> <br/> |
|<span data-ttu-id="46ed6-114">조직에서 일별 모든 검토 집합에 로드 된 총 데이터 양</span><span class="sxs-lookup"><span data-stu-id="46ed6-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="46ed6-115">2TB</span><span class="sxs-lookup"><span data-stu-id="46ed6-115">2 TB</span></span> <br/> |
|<span data-ttu-id="46ed6-116">사례 당 최대 부하 집합 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="46ed6-117">200</span><span class="sxs-lookup"><span data-stu-id="46ed6-117">200</span></span> <br/> |
|<span data-ttu-id="46ed6-118">사례 당 최대 검토 집합 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="46ed6-119">20cm(8</span><span class="sxs-lookup"><span data-stu-id="46ed6-119">20</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="46ed6-120">인덱싱 제한</span><span class="sxs-lookup"><span data-stu-id="46ed6-120">Indexing limits</span></span>

<span data-ttu-id="46ed6-121">다음 표에는 고급 eDiscovery의 인덱싱 제한이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-121">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="46ed6-122">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="46ed6-122">**Description of limit**</span></span>|<span data-ttu-id="46ed6-123">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="46ed6-123">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="46ed6-124">단일 파일에서 추출한 최대 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-124">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="46ed6-125">1000만<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="46ed6-125">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="46ed6-126">단일 파일의 최대 크기</span><span class="sxs-lookup"><span data-stu-id="46ed6-126">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="46ed6-127">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="46ed6-127">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="46ed6-128">문서에 포함 된 항목의 최대 깊이</span><span class="sxs-lookup"><span data-stu-id="46ed6-128">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="46ed6-129">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="46ed6-129">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="46ed6-130">OCR (광학 인식)에서 처리 되는 최대 파일 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-130">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="46ed6-131">24mb<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="46ed6-131">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="46ed6-132">검색 제한</span><span class="sxs-lookup"><span data-stu-id="46ed6-132">Search limits</span></span>

<span data-ttu-id="46ed6-133">이 섹션에서 설명 하는 제한은 **검색** 탭의 검색 도구를 사용 하 여 사례에 대 한 데이터를 수집 하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-133">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="46ed6-134">자세한 내용은 [Advanced eDiscovery에서 사례 데이터 수집](collecting-data-for-ediscovery.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="46ed6-134">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="46ed6-135">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="46ed6-135">**Description of limit**</span></span>|<span data-ttu-id="46ed6-136">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="46ed6-136">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="46ed6-137">단일 검색에서 검색할 수 있는 최대 사서함 또는 사이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-137">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="46ed6-138">제한 없음</span><span class="sxs-lookup"><span data-stu-id="46ed6-138">No limit</span></span>  <br/> |
|<span data-ttu-id="46ed6-139">동시에 실행할 수 있는 최대 검색 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-139">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="46ed6-140">제한 없음</span><span class="sxs-lookup"><span data-stu-id="46ed6-140">No limit</span></span>  <br/> | 
|<span data-ttu-id="46ed6-141">단일 사용자가 동시에 시작할 수 있는 최대 검색 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-141">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="46ed6-142">10  </span><span class="sxs-lookup"><span data-stu-id="46ed6-142">10</span></span>  <br/> | 
|<span data-ttu-id="46ed6-143">검색 쿼리의 최대 문자 수 (연산자 및 조건 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-143">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="46ed6-144">**사서함**: 1만</span><span class="sxs-lookup"><span data-stu-id="46ed6-144">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="46ed6-145">**사이트**: 4000-최대 20 <sup>개의 사이트를</sup> 검색할 때 모든 사이트 또는 2000를 검색 하는 경우</span><span class="sxs-lookup"><span data-stu-id="46ed6-145">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="46ed6-146">접두사 와일드 카드에 대 한 최소 영숫자 문자 수입니다. 예를 **들면 \* 1** 또는 \*\*set \* \*\*입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-146">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="46ed6-147">3 </span><span class="sxs-lookup"><span data-stu-id="46ed6-147">3</span></span>  <br/> |  
|<span data-ttu-id="46ed6-148">접두사 와일드 카드를 사용 하 여 정확한 구문을 검색 하거나 접두사 와일드 카드와 **근사** 부울 연산자를 사용 하는 경우 반환 되는 최대 variant입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-148">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="46ed6-149">1만 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="46ed6-149">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="46ed6-150">검색에 대 한 미리 보기 페이지에 표시 되는 사용자 사서함 당 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-150">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="46ed6-151">최신 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-151">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="46ed6-152">100</span><span class="sxs-lookup"><span data-stu-id="46ed6-152">100</span></span>  <br/> |
|<span data-ttu-id="46ed6-153">검색에 대 한 미리 보기 페이지에 표시 되는 모든 사서함의 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-153">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="46ed6-154">1,000</span><span class="sxs-lookup"><span data-stu-id="46ed6-154">1,000</span></span>  <br/> |
|<span data-ttu-id="46ed6-155">검색 결과에 대해 미리 볼 수 있는 최대 사서함 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-155">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="46ed6-156">검색 쿼리와 일치 하는 항목이 포함 된 사서함이 1000 개 보다 많으면 가장 많은 결과가 포함 된 최상위 1000 사서함만 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-156">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="46ed6-157">1,000</span><span class="sxs-lookup"><span data-stu-id="46ed6-157">1,000</span></span>  <br/> |
|<span data-ttu-id="46ed6-158">검색에 대 한 미리 보기 페이지에 표시 되는 SharePoint 및 비즈니스용 OneDrive 사이트의 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-158">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="46ed6-159">최신 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-159">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="46ed6-160">200</span><span class="sxs-lookup"><span data-stu-id="46ed6-160">200</span></span>  <br/> |
|<span data-ttu-id="46ed6-161">검색 결과에 대해 미리 볼 수 있는 최대 SharePoint 및 비즈니스용 OneDrive 사이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-161">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="46ed6-162">검색 쿼리와 일치 하는 항목이 포함 된 사이트가 200 개 보다 많으면 가장 많은 결과가 포함 된 최상위 200 사이트만 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-162">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="46ed6-163">200</span><span class="sxs-lookup"><span data-stu-id="46ed6-163">200</span></span>  <br/> |
|<span data-ttu-id="46ed6-164">검색에 대 한 미리 보기 페이지에 표시 되는 공용 폴더 사서함당 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-164">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="46ed6-165">100</span><span class="sxs-lookup"><span data-stu-id="46ed6-165">100</span></span>  <br/> |
|<span data-ttu-id="46ed6-166">검색에 대 한 미리 보기 페이지에 표시 되는 모든 공용 폴더 사서함 항목에 있는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-166">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="46ed6-167">200</span><span class="sxs-lookup"><span data-stu-id="46ed6-167">200</span></span>  <br/> |
|<span data-ttu-id="46ed6-168">검색 결과에 대해 미리 볼 수 있는 최대 공용 폴더 사서함 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-168">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="46ed6-169">검색 쿼리와 일치 하는 항목을 포함 하는 공용 폴더 사서함이 500 개 보다 많으면 가장 많은 결과가 포함 된 최상위 500 사서함만 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-169">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="46ed6-170">500</span><span class="sxs-lookup"><span data-stu-id="46ed6-170">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="46ed6-171">뷰어 제한</span><span class="sxs-lookup"><span data-stu-id="46ed6-171">Viewer limits</span></span>

|<span data-ttu-id="46ed6-172">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="46ed6-172">**Description of limit**</span></span>|<span data-ttu-id="46ed6-173">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="46ed6-173">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="46ed6-174">네이티브 뷰어에 표시할 수 있는 Excel 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-174">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="46ed6-175">4mb</span><span class="sxs-lookup"><span data-stu-id="46ed6-175">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="46ed6-176">다운로드 제한 설정 검토</span><span class="sxs-lookup"><span data-stu-id="46ed6-176">Review set download limits</span></span>

|<span data-ttu-id="46ed6-177">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="46ed6-177">**Description of limit**</span></span>|<span data-ttu-id="46ed6-178">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="46ed6-178">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="46ed6-179">전체 파일 크기 또는 검토 집합에서 다운로드 한 최대 문서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-179">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="46ed6-180">3mb 또는 50 문서 <sup>4 개</sup></span><span class="sxs-lookup"><span data-stu-id="46ed6-180">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="46ed6-181"><sup>1</sup> 파일 한도를 초과 하는 항목은 처리 오류로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-181"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="46ed6-182"><sup>2</sup> SharePoint 및 비즈니스용 OneDrive 위치를 검색 하는 경우 검색 되는 사이트의 url에 있는 문자가이 제한에 대해 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-182"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="46ed6-183"><sup>3</sup> 비 구 쿼리 (큰따옴표를 사용 하지 않는 키워드 값)의 경우에는 특수 접두사 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-183"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="46ed6-184">이렇게 하면 문서에서 단어가 나타나지만 문서에서 나타나는 위치를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-184">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="46ed6-185">구문 쿼리 (큰따옴표를 사용한 키워드 값)를 수행 하려면 문서 내에서 구의 단어를 비교 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-185">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="46ed6-186">즉, 구 쿼리에 접두사 인덱스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-186">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="46ed6-187">이 경우에는 접두사를 확장 하는 모든 가능한 단어를 내부적으로 확장 합니다. 예를 들어 \*\*시간이 \* \*\* **"시간/타이머/시간 또는 timex 또는 timeboxed" (...)** 로 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-187">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="46ed6-188">1만 제한은 쿼리와 일치 하는 문서 수가 아닌 단어를 확장할 수 있는 최대 variant 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-188">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="46ed6-189">구문이 아닌 용어의 상한 값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-189">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="46ed6-190"><sup>4</sup> 이 제한은 검토 집합에서 선택한 문서를 다운로드 하는 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-190"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="46ed6-191">검토 집합에서 문서를 내보내는 경우에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46ed6-191">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="46ed6-192">문서 다운로드 및 내보내기에 대 한 자세한 내용은 [Advanced eDiscovery에서 케이스 데이터 내보내기를](exporting-data-ediscover20.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="46ed6-192">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

