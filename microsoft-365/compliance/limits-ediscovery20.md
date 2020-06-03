---
title: Advanced eDiscovery 제한
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365의 고급 eDiscovery 솔루션에 적용 되는 제한 사항에 대해 알아봅니다. 검색 도구를 사용 하 여 사례 데이터를 수집 하는 경우 대/소문자 제한, 인덱싱 제한 및 검색 제한 사항이 포함 됩니다.
ms.openlocfilehash: babc05cc5c74f435f0be6fbc8eafd80f09a77b75
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520150"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="dafed-104">Advanced eDiscovery 제한 사항</span><span class="sxs-lookup"><span data-stu-id="dafed-104">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="dafed-105">이 문서에서는 Microsoft 365의 고급 eDiscovery 솔루션에 대 한 제한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-105">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="dafed-106">사례 및 검토 제한 설정</span><span class="sxs-lookup"><span data-stu-id="dafed-106">Case and review set limits</span></span>

<span data-ttu-id="dafed-107">다음 표에는 Advanced eDiscovery의 사례 및 검토 집합에 대 한 제한이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-107">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="dafed-108">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="dafed-108">**Description of limit**</span></span>|<span data-ttu-id="dafed-109">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="dafed-109">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dafed-110">사례에 추가할 수 있는 총 문서 수 (사례에서 모든 검토 집합의 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-110">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="dafed-111">1,000,000</span><span class="sxs-lookup"><span data-stu-id="dafed-111">1 million</span></span>  <br/> |
|<span data-ttu-id="dafed-112">부하 집합 당 총 파일 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-112">Total file size per load set.</span></span> <span data-ttu-id="dafed-113">여기에는 비 Office 365을 검토 집합으로 로드 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-113">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="dafed-114">100GB</span><span class="sxs-lookup"><span data-stu-id="dafed-114">100 GB</span></span>  <br/> |
|<span data-ttu-id="dafed-115">조직에서 일별 모든 검토 집합에 로드 된 총 데이터 양</span><span class="sxs-lookup"><span data-stu-id="dafed-115">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="dafed-116">2TB</span><span class="sxs-lookup"><span data-stu-id="dafed-116">2 TB</span></span> <br/> |
|<span data-ttu-id="dafed-117">사례 당 최대 부하 집합 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-117">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="dafed-118">15 </span><span class="sxs-lookup"><span data-stu-id="dafed-118">15</span></span> <br/> |
|<span data-ttu-id="dafed-119">사례 당 최대 검토 집합 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-119">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="dafed-120">20cm(8</span><span class="sxs-lookup"><span data-stu-id="dafed-120">20</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="dafed-121">인덱싱 제한</span><span class="sxs-lookup"><span data-stu-id="dafed-121">Indexing limits</span></span>

<span data-ttu-id="dafed-122">다음 표에는 고급 eDiscovery의 인덱싱 제한이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-122">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="dafed-123">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="dafed-123">**Description of limit**</span></span>|<span data-ttu-id="dafed-124">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="dafed-124">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="dafed-125">단일 파일에서 추출한 최대 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-125">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="dafed-126">1000만<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dafed-126">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="dafed-127">단일 파일의 최대 크기</span><span class="sxs-lookup"><span data-stu-id="dafed-127">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="dafed-128">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dafed-128">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="dafed-129">문서에 포함 된 항목의 최대 깊이</span><span class="sxs-lookup"><span data-stu-id="dafed-129">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="dafed-130">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dafed-130">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="dafed-131">OCR (광학 인식)에서 처리 되는 최대 파일 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-131">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="dafed-132">24mb<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dafed-132">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="dafed-133">검색 제한</span><span class="sxs-lookup"><span data-stu-id="dafed-133">Search limits</span></span>

<span data-ttu-id="dafed-134">이 섹션에서 설명 하는 제한은 **검색** 탭의 검색 도구를 사용 하 여 사례에 대 한 데이터를 수집 하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-134">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="dafed-135">자세한 내용은 [Advanced eDiscovery에서 사례 데이터 수집](collecting-data-for-ediscovery.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dafed-135">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="dafed-136">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="dafed-136">**Description of limit**</span></span>|<span data-ttu-id="dafed-137">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="dafed-137">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dafed-138">단일 검색에서 검색할 수 있는 최대 사서함 또는 사이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-138">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="dafed-139">제한 없음</span><span class="sxs-lookup"><span data-stu-id="dafed-139">No limit</span></span>  <br/> |
|<span data-ttu-id="dafed-140">동시에 실행할 수 있는 최대 검색 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-140">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="dafed-141">제한 없음</span><span class="sxs-lookup"><span data-stu-id="dafed-141">No limit</span></span>  <br/> | 
|<span data-ttu-id="dafed-142">단일 사용자가 동시에 시작할 수 있는 최대 검색 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-142">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="dafed-143">10  </span><span class="sxs-lookup"><span data-stu-id="dafed-143">10</span></span>  <br/> | 
|<span data-ttu-id="dafed-144">검색 쿼리의 최대 문자 수 (연산자 및 조건 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-144">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="dafed-145">**사서함**: 1만</span><span class="sxs-lookup"><span data-stu-id="dafed-145">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="dafed-146">**사이트**: 4000-최대 20 <sup>개의 사이트를</sup> 검색할 때 모든 사이트 또는 2000를 검색 하는 경우</span><span class="sxs-lookup"><span data-stu-id="dafed-146">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="dafed-147">접두사 와일드 카드에 대 한 최소 영숫자 문자 수입니다. 예를 **들면 \* 1** 또는 \*\*set \* \*\*입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-147">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="dafed-148">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="dafed-148">3</span></span>  <br/> |  
|<span data-ttu-id="dafed-149">접두사 와일드 카드를 사용 하 여 정확한 구문을 검색 하거나 접두사 와일드 카드와 **근사** 부울 연산자를 사용 하는 경우 반환 되는 최대 variant입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-149">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="dafed-150">1만 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="dafed-150">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="dafed-151">검색에 대 한 미리 보기 페이지에 표시 되는 사용자 사서함 당 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-151">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="dafed-152">최신 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-152">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="dafed-153">100</span><span class="sxs-lookup"><span data-stu-id="dafed-153">100</span></span>  <br/> |
|<span data-ttu-id="dafed-154">검색에 대 한 미리 보기 페이지에 표시 되는 모든 사서함의 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-154">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="dafed-155">1,000</span><span class="sxs-lookup"><span data-stu-id="dafed-155">1,000</span></span>  <br/> |
|<span data-ttu-id="dafed-156">검색 결과에 대해 미리 볼 수 있는 최대 사서함 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-156">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="dafed-157">검색 쿼리와 일치 하는 항목이 포함 된 사서함이 1000 개 보다 많으면 가장 많은 결과가 포함 된 최상위 1000 사서함만 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-157">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="dafed-158">1,000</span><span class="sxs-lookup"><span data-stu-id="dafed-158">1,000</span></span>  <br/> |
|<span data-ttu-id="dafed-159">검색에 대 한 미리 보기 페이지에 표시 되는 SharePoint 및 비즈니스용 OneDrive 사이트의 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-159">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="dafed-160">최신 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-160">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="dafed-161">200</span><span class="sxs-lookup"><span data-stu-id="dafed-161">200</span></span>  <br/> |
|<span data-ttu-id="dafed-162">검색 결과에 대해 미리 볼 수 있는 최대 SharePoint 및 비즈니스용 OneDrive 사이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-162">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="dafed-163">검색 쿼리와 일치 하는 항목이 포함 된 사이트가 200 개 보다 많으면 가장 많은 결과가 포함 된 최상위 200 사이트만 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-163">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="dafed-164">200</span><span class="sxs-lookup"><span data-stu-id="dafed-164">200</span></span>  <br/> |
|<span data-ttu-id="dafed-165">검색에 대 한 미리 보기 페이지에 표시 되는 공용 폴더 사서함당 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-165">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="dafed-166">100</span><span class="sxs-lookup"><span data-stu-id="dafed-166">100</span></span>  <br/> |
|<span data-ttu-id="dafed-167">검색에 대 한 미리 보기 페이지에 표시 되는 모든 공용 폴더 사서함 항목에 있는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-167">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="dafed-168">200</span><span class="sxs-lookup"><span data-stu-id="dafed-168">200</span></span>  <br/> |
|<span data-ttu-id="dafed-169">검색 결과에 대해 미리 볼 수 있는 최대 공용 폴더 사서함 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-169">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="dafed-170">검색 쿼리와 일치 하는 항목을 포함 하는 공용 폴더 사서함이 500 개 보다 많으면 가장 많은 결과가 포함 된 최상위 500 사서함만 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-170">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="dafed-171">500</span><span class="sxs-lookup"><span data-stu-id="dafed-171">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="dafed-172">뷰어 제한</span><span class="sxs-lookup"><span data-stu-id="dafed-172">Viewer limits</span></span>

|<span data-ttu-id="dafed-173">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="dafed-173">**Description of limit**</span></span>|<span data-ttu-id="dafed-174">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="dafed-174">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="dafed-175">네이티브 뷰어에 표시할 수 있는 Excel 파일의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-175">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="dafed-176">4mb</span><span class="sxs-lookup"><span data-stu-id="dafed-176">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="dafed-177">다운로드 제한 설정 검토</span><span class="sxs-lookup"><span data-stu-id="dafed-177">Review set download limits</span></span>

|<span data-ttu-id="dafed-178">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="dafed-178">**Description of limit**</span></span>|<span data-ttu-id="dafed-179">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="dafed-179">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dafed-180">전체 파일 크기 또는 검토 집합에서 다운로드 한 최대 문서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-180">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="dafed-181">3mb 또는 50 문서 <sup>4 개</sup></span><span class="sxs-lookup"><span data-stu-id="dafed-181">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="dafed-182"><sup>1</sup> 파일 한도를 초과 하는 항목은 처리 오류로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-182"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="dafed-183"><sup>2</sup> SharePoint 및 비즈니스용 OneDrive 위치를 검색 하는 경우 검색 되는 사이트의 url에 있는 문자가이 제한에 대해 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-183"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="dafed-184"><sup>3</sup> 비 구 쿼리 (큰따옴표를 사용 하지 않는 키워드 값)의 경우에는 특수 접두사 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-184"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="dafed-185">이렇게 하면 문서에서 단어가 나타나지만 문서에서 나타나는 위치를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-185">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="dafed-186">구문 쿼리 (큰따옴표를 사용한 키워드 값)를 수행 하려면 문서 내에서 구의 단어를 비교 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-186">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="dafed-187">즉, 구 쿼리에 접두사 인덱스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-187">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="dafed-188">이 경우에는 접두사를 확장 하는 모든 가능한 단어를 내부적으로 확장 합니다. 예를 들어 \*\*시간이 \* \*\* **"시간/타이머/시간 또는 timex 또는 timeboxed" (...)** 로 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-188">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="dafed-189">1만 제한은 쿼리와 일치 하는 문서 수가 아닌 단어를 확장할 수 있는 최대 variant 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-189">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="dafed-190">구문이 아닌 용어의 상한 값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-190">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="dafed-191"><sup>4</sup> 이 제한은 검토 집합에서 선택한 문서를 다운로드 하는 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-191"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="dafed-192">검토 집합에서 문서를 내보내는 경우에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dafed-192">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="dafed-193">문서 다운로드 및 내보내기에 대 한 자세한 내용은 [Advanced eDiscovery에서 케이스 데이터 내보내기를](exporting-data-ediscover20.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dafed-193">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

