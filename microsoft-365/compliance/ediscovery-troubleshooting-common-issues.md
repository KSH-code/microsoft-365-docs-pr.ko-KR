---
title: Troublshooting 일반적인 eDiscovery 문제
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Office 365 eDiscovery에서 일반적인 문제를 조사 하 고 문제를 해결 합니다.
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207298"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="feff8-103">일반적인 eDiscovery 문제 조사, 문제 해결 및 해결</span><span class="sxs-lookup"><span data-stu-id="feff8-103">Investigate, troubleshoot and resolve common eDiscovery issues</span></span>

<span data-ttu-id="feff8-104">이 항목에서는 eDiscovery 검색 중에 발생할 수 있는 문제를 파악 하 고 해결 하기 위해 수행할 수 있는 기본적인 문제 해결 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="feff8-105">이러한 시나리오 중 일부를 해결 하려면 CSS (고객 지원 서비스)에서 도움을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-105">Resolving some of these scenarios requires help from Customer Support Services (CSS).</span></span> <span data-ttu-id="feff8-106">CSS에 연결 하는 경우에 대 한 정보는 해결 단계에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-106">Information on when to contact CSS is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="feff8-107">오류/모호한 위치 문제</span><span class="sxs-lookup"><span data-stu-id="feff8-107">Error/issue ambiguous location</span></span>

<span data-ttu-id="feff8-108">이 오류는 "검색에 사용자의 사서함 위치를 추가 하려고 했지만 `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` EOP (Exchange Online Protection)에 동일한 사용자 id가 있는 중복 되거나 충돌 하는 개체가 있는 경우 준수 검색에서 다음의 잘못 된 위치를 포함 합니다." 라는 오류가 표시 됩니다. 디렉토리로.</span><span class="sxs-lookup"><span data-stu-id="feff8-108">You'll receive this error "The compliance search contains the following invalid location `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` if you tried to add user’s mailbox location to search and there are duplicate or conflicting objects with the same user id in the Exchange Online Protection (EOP) directory.</span></span>

### <a name="resolution"></a><span data-ttu-id="feff8-109">문제 해결 방법</span><span class="sxs-lookup"><span data-stu-id="feff8-109">Resolution</span></span>

<span data-ttu-id="feff8-110">동일한 사용자 ID의 중복 된 사용자 또는 메일 그룹을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="feff8-111">[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-111">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="feff8-112">사용자 이름의 인스턴스를 모두 검색 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-112">Retrieve all instances of the username, type:</span></span>

```powershell
Get-Recipient <username>
```

<span data-ttu-id="feff8-113">' Useralias@contoso.com '의 출력</span><span class="sxs-lookup"><span data-stu-id="feff8-113">The output for 'useralias@contoso.com' might be</span></span>

> 
> |<span data-ttu-id="feff8-114">이름</span><span class="sxs-lookup"><span data-stu-id="feff8-114">Name</span></span>  |<span data-ttu-id="feff8-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="feff8-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="feff8-116">별칭, 사용자</span><span class="sxs-lookup"><span data-stu-id="feff8-116">Alias, User</span></span>     |<span data-ttu-id="feff8-117">Enable-mailuser</span><span class="sxs-lookup"><span data-stu-id="feff8-117">MailUser</span></span>         |
> |<span data-ttu-id="feff8-118">별칭, 사용자</span><span class="sxs-lookup"><span data-stu-id="feff8-118">Alias, User</span></span>     |<span data-ttu-id="feff8-119">사용자</span><span class="sxs-lookup"><span data-stu-id="feff8-119">User</span></span>         |

3. <span data-ttu-id="feff8-120">여러 사용자가 반환 되 면 충돌 하는 개체를 찾아서 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="feff8-121">특정 위치에서 오류/문제 검색 실패</span><span class="sxs-lookup"><span data-stu-id="feff8-121">Error/issue search fails on specific locations</span></span>

<span data-ttu-id="feff8-122">EDiscovery 또는 콘텐츠 검색 시 다음 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="feff8-123">이 검색은 (#) 오류와 함께 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="feff8-124">실패 한 위치에서 검색을 다시 시도 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="feff8-124">Would you like to retry the search on the failed locations?</span></span>

![검색 관련 위치 실패 오류 스크린샷]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="feff8-126">문제 해결 방법</span><span class="sxs-lookup"><span data-stu-id="feff8-126">Resolution</span></span>

<span data-ttu-id="feff8-127">이 오류가 표시 되는 경우 검색에 실패 한 위치를 확인 한 다음 실패 한 위치 에서만 검색을 다시 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-127">If you receive this error, we recommend that you verify the locations that failed in the search  then re-run the search only on the failed locations.</span></span>

1. <span data-ttu-id="feff8-128">[Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-128">Connect to [Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="feff8-129">형식일</span><span class="sxs-lookup"><span data-stu-id="feff8-129">Type:</span></span>

```powershell
Get-Compliancesearch searchname|fl 
```

3. <span data-ttu-id="feff8-130">PowerShell 출력의 오류 필드에서 실패 한 위치를 확인 하거나, 오류에 있는 상태 세부 정보를 검색 결과에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-130">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>
1. <span data-ttu-id="feff8-131">실패 한 위치 에서만 eDiscovery 검색을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-131">Retry the eDiscovery search on the failed locations only.</span></span>
1. <span data-ttu-id="feff8-132">계속 해 서 이러한 오류가 표시 되 면 추가 문제 해결 단계에 대 한 [다시 시도 실패 위치](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="feff8-132">If you continue to receive these error, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for additional troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="feff8-133">오류/문제 파일을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="feff8-133">Error/issue file not found</span></span>

<span data-ttu-id="feff8-134">SharePoint Online 및 업무용 위치를 포함 하는 eDiscovery 검색을 실행할 때 해당 파일이 사이트에 있더라도 오류가 `File Not Found` 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-134">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="feff8-135">이 오류는 내보내기 경고 및 오류로 인해 발생 합니다. csv이 파일을 사이트에서 찾을 수 없거나 인덱스가 오래 된 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-135">This error will be in the export warnings and errors.csv or skipped items.csv  This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="feff8-136">아래에는 강조 추가 된 실제 오류의 텍스트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="feff8-137">28.06.2019 10:02:19_FailedToExportItem_Failed-콘텐츠를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="feff8-138">추가 진단 정보: ContentDownloadTemporaryFailure: 콘텐츠 6ea52149-91cd-4965-b5bb-82ca6a3ec9be 문서를 다운로드 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="feff8-139">상관 관계 Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="feff8-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="feff8-140">ServerErrorCode:-2147024894---> Microsoft web.config. Servererrorcode: ***파일을 찾을 수 없습니다***.</span><span class="sxs-lookup"><span data-stu-id="feff8-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="feff8-141">ProcessResponseStream (Stream responseStream)의 Microsoft sharepoint. Clientrequest ()---내부 예외 스택 추적의 끝을---합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="feff8-142">문제 해결 방법</span><span class="sxs-lookup"><span data-stu-id="feff8-142">Resolution</span></span>

1. <span data-ttu-id="feff8-143">검색에서 확인 된 위치를 확인 하 여 파일 위치가 올바르며 검색 위치에 추가 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>
2. <span data-ttu-id="feff8-144">[수동으로 크롤링을 요청 하 고 사이트, 라이브러리 또는 목록을 다시 인덱싱하여](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) 사이트를 다시 인덱싱하는 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-recipient-not-found"></a><span data-ttu-id="feff8-145">오류/문제 검색 실패 받는 사람을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="feff8-145">Error/issue search fails recipient not found</span></span>

<span data-ttu-id="feff8-146">오류로 `recipient not found`인해 eDiscovery 검색이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-146">eDiscovery search fails with error `recipient not found`.</span></span> <span data-ttu-id="feff8-147">이 오류는 EOP (Exchange Online Protection)에서 개체가 동기화 되지 않아 사용자 개체를 찾을 수 없는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="feff8-148">문제 해결 방법</span><span class="sxs-lookup"><span data-stu-id="feff8-148">Resolution</span></span>

1. <span data-ttu-id="feff8-149">[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-149">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="feff8-150">사용자 개체가 Exchange Online Protection 유형과 동기화 되어 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="feff8-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

```powershell
Get-Recipient userId|fl
```

3. <span data-ttu-id="feff8-151">사용자 질문에 대 한 enable-mailuser 개체가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-151">There should be a mailuser object for the user question.</span></span> <span data-ttu-id="feff8-152">아무 것도 반환 하지 않으면 사용자 개체를 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="feff8-153">개체를 동기화 할 수 없는 경우 CSS에 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-153">Contact CSS if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="feff8-154">오류/내보내기 검색 결과 속도가 느림</span><span class="sxs-lookup"><span data-stu-id="feff8-154">Error/issue exporting search results is slow</span></span>

<span data-ttu-id="feff8-155">보안 및 준수 센터에서 eDiscovery 또는 콘텐츠 검색의 검색 결과를 내보낼 때 다운로드가 예상 보다 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="feff8-156">다운로드 해야 하는 데이터의 양을 확인 하 고 내보내기 속도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="feff8-157">문제 해결 방법</span><span class="sxs-lookup"><span data-stu-id="feff8-157">Resolution</span></span>

1.  <span data-ttu-id="feff8-158">[다운로드 속도 증가](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)문서에서 식별 된 단계를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>
2.  <span data-ttu-id="feff8-159">문제가 계속 되 면 [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) 에 연결 하 고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-159">If you still have issues, connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname\fl
```

4. <span data-ttu-id="feff8-160">SearchResults 및 Searchresults 매개 변수로 다운로드할 데이터 양을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>
5. <span data-ttu-id="feff8-161">형식일</span><span class="sxs-lookup"><span data-stu-id="feff8-161">Type:</span></span>

```powershell
Get-ComplianceSearchAction |fl
```

6. <span data-ttu-id="feff8-162">결과 필드에서 내보낸 데이터를 찾아서 발생 한 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-162">In the results field find the data that has been exported and view any errors encountered.</span></span>
7. <span data-ttu-id="feff8-163">오류에 대해 콘텐츠를 내보낸 디렉터리에 있는 trace 파일을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="feff8-164">오류/문제 "내부 서버 오류 (500)가 발생 했습니다."</span><span class="sxs-lookup"><span data-stu-id="feff8-164">Error/issue "Internal server error (500) occurred"</span></span>

<span data-ttu-id="feff8-165">EDiscovery 검색을 실행할 때 "내부 서버 오류 (500)이 발생 했습니다."와 유사한 오류와 함께 검색이 계속 실패 하면 특정 사서함 위치에 대해서만 검색을 다시 실행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need re-run the search only on specific mailbox locations.</span></span>

![내부 서버 오류 500 스크린샷](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="feff8-167">문제 해결 방법</span><span class="sxs-lookup"><span data-stu-id="feff8-167">Resolution</span></span>

1. <span data-ttu-id="feff8-168">검색을 더 작은 검색으로 나누고 검색을 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="feff8-169">더 작은 날짜 범위를 사용 하거나 검색 중인 위치 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-169">Try using a smaller date range or limit the number of locations being searched.</span></span>
2. <span data-ttu-id="feff8-170">[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) 에 연결 하 고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-170">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname |fl
```

3. <span data-ttu-id="feff8-171">결과 및 오류에 대 한 출력을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-171">Examine the output for results and errors.</span></span>
3. <span data-ttu-id="feff8-172">추적 .log 파일을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-172">Examine the trace.log file.</span></span> <span data-ttu-id="feff8-173">이 폴더는 내보내기 대상으로 보낸 편지함에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-173">It will be in the same folder that you sent the export to.</span></span>
4. <span data-ttu-id="feff8-174">지원 CSS에 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-174">Contact Support CSS.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="feff8-175">오류/문제점 보류가 동기화 되지 않음</span><span class="sxs-lookup"><span data-stu-id="feff8-175">Error/issue holds don't sync</span></span>

<span data-ttu-id="feff8-176">eDiscovery 사례 보류 정책 동기화 배포 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="feff8-177">오류는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-177">The error reads:</span></span>

> <span data-ttu-id="feff8-178">"리소스: 정책을 배포 하는 데 예상 보다 오래 걸리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="feff8-179">최종 배포 상태를 업데이트 하는 데 두 시간 정도 걸릴 수 있으므로 몇 시간 후에 다시 확인 하세요. "</span><span class="sxs-lookup"><span data-stu-id="feff8-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="feff8-180">문제 해결 방법</span><span class="sxs-lookup"><span data-stu-id="feff8-180">Resolution</span></span>

1.  <span data-ttu-id="feff8-181">[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) 에 연결 하 고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-181">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. <span data-ttu-id="feff8-182">Distributiondetail 매개 변수의 값을 검사 하 여 다음과 같은 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-182">Examine the value in the Distributiondetail parameter for errors like the following:</span></span>

> <span data-ttu-id="feff8-183">오류가 있는 경우에는 정책을 수동으로 다시 동기화 하도록 PG에 게 에스컬레이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="feff8-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="feff8-184">연락처 CSS</span><span class="sxs-lookup"><span data-stu-id="feff8-184">Contact CSS.</span></span>

## <a name="see-also"></a><span data-ttu-id="feff8-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="feff8-185">See Also</span></span>
- [<span data-ttu-id="feff8-186">콘텐츠 위치 오류를 방지 하기 위한 팁</span><span class="sxs-lookup"><span data-stu-id="feff8-186">Tips to avoid content location errors</span></span>](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)