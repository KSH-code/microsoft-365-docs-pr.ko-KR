---
title: 일반적인 eDiscovery 문제 해결
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Office 365 eDiscovery에서 일반적인 문제를 해결 하기 위해 수행할 수 있는 기본적인 문제 해결 단계에 대해 알아봅니다.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c9d917306c1a4ffd0dd1e11e1dd87c135e94f05
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545956"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="20377-103">일반적인 eDiscovery 문제 조사, 문제 해결 및 해결</span><span class="sxs-lookup"><span data-stu-id="20377-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="20377-104">이 항목에서는 eDiscovery 검색 중에 발생할 수 있는 문제를 파악 하 고 해결 하기 위해 수행할 수 있는 기본적인 문제 해결 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="20377-105">이러한 시나리오 중 일부를 해결 하려면 Microsoft 기술 지원 서비스에서 도움을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="20377-106">Microsoft 지원 센터에 문의 하는 방법에 대 한 정보는 해결 방법에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="20377-107">오류/문제: 모호한 위치</span><span class="sxs-lookup"><span data-stu-id="20377-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="20377-108">사용자의 사서함 위치를 검색에 추가 하려고 했지만 EOP (Exchange Online Protection) 디렉터리에 동일한 userID가 있는 개체가 중복 되거나 충돌 하는 경우에는 다음 오류가 발생 `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="20377-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="20377-109">Resolution</span></span>

<span data-ttu-id="20377-110">동일한 사용자 ID의 중복 된 사용자 또는 메일 그룹을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="20377-111">[보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="20377-112">다음 명령을 실행 하 여 username의 모든 인스턴스를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="20377-113">' Useralias@contoso.com '의 출력은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="20377-114">이름</span><span class="sxs-lookup"><span data-stu-id="20377-114">Name</span></span>|<span data-ttu-id="20377-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="20377-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="20377-116">별칭, 사용자</span><span class="sxs-lookup"><span data-stu-id="20377-116">Alias, User</span></span>|<span data-ttu-id="20377-117">Enable-mailuser</span><span class="sxs-lookup"><span data-stu-id="20377-117">MailUser</span></span>|
   > |<span data-ttu-id="20377-118">별칭, 사용자</span><span class="sxs-lookup"><span data-stu-id="20377-118">Alias, User</span></span>|<span data-ttu-id="20377-119">사용자</span><span class="sxs-lookup"><span data-stu-id="20377-119">User</span></span>|

3. <span data-ttu-id="20377-120">여러 사용자가 반환 되 면 충돌 하는 개체를 찾아서 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="20377-121">오류/문제: 특정 위치에서 검색 실패</span><span class="sxs-lookup"><span data-stu-id="20377-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="20377-122">EDiscovery 또는 콘텐츠 검색 시 다음 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="20377-123">이 검색은 (#) 오류와 함께 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="20377-124">실패 한 위치에서 검색을 다시 시도 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="20377-124">Would you like to retry the search on the failed locations?</span></span>

![검색 별 위치 실패 오류 스크린샷](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="20377-126">해결 방법</span><span class="sxs-lookup"><span data-stu-id="20377-126">Resolution</span></span>

<span data-ttu-id="20377-127">이 오류가 표시 되는 경우 검색에 실패 한 위치를 확인 한 다음 실패 한 위치 에서만 검색을 다시 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-127">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="20377-128">[보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 에 연결한 후 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-128">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="20377-129">PowerShell 출력의 오류 필드에서 실패 한 위치를 확인 하거나, 오류에 있는 상태 세부 정보를 검색 결과에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-129">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="20377-130">실패 한 위치 에서만 eDiscovery 검색을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-130">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="20377-131">계속 해 서 이러한 오류가 표시 되 면 다른 문제 해결 단계에 대 한 [다시 시도 실패 위치](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="20377-131">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="20377-132">오류/문제: 파일을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="20377-132">Error/issue: File not found</span></span>

<span data-ttu-id="20377-133">SharePoint Online 및 업무용 위치를 포함 하는 eDiscovery 검색을 실행할 때 해당 `File Not Found` 파일이 사이트에 있더라도 오류가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-133">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="20377-134">이 오류는 내보내기 경고에 표시 되 고 errors.csv 하거나 items.csv 건너 뜁니다.</span><span class="sxs-lookup"><span data-stu-id="20377-134">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="20377-135">이 오류는 사이트에서 파일을 찾을 수 없거나 인덱스가 오래 된 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-135">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="20377-136">다음은 실제 오류 (강조 추가 됨)의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="20377-136">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="20377-137">28.06.2019 10:02:19_FailedToExportItem_Failed 콘텐츠를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="20377-138">추가 진단 정보: ContentDownloadTemporaryFailure: 콘텐츠 6ea52149-91cd-4965-b5bb-82ca6a3ec9be 문서를 다운로드 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="20377-139">상관 관계 Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="20377-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="20377-140">ServerErrorCode:-2147024894---> Microsoft web.config. Servererrorcode: ***파일을 찾을 수 없습니다***.</span><span class="sxs-lookup"><span data-stu-id="20377-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="20377-141">ProcessResponseStream (Stream responseStream)의 Microsoft sharepoint. Clientrequest ()---내부 예외 스택 추적의 끝을---합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="20377-142">해결 방법</span><span class="sxs-lookup"><span data-stu-id="20377-142">Resolution</span></span>

1. <span data-ttu-id="20377-143">검색에서 확인 된 위치를 확인 하 여 파일 위치가 올바르며 검색 위치에 추가 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="20377-144">[수동으로 크롤링을 요청 하 고 사이트, 라이브러리 또는 목록을 다시 인덱싱하여 사이트의](https://docs.microsoft.com/sharepoint/crawl-site-content) 인덱스를 해제 하는 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="20377-145">오류/문제: 받는 사람이 발견 되지 않아 검색이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-145">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="20377-146">EDiscovery 검색이 실패 하 고 오류가 발생 `recipient not found` 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-146">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="20377-147">이 오류는 EOP (Exchange Online Protection)에서 개체가 동기화 되지 않아 사용자 개체를 찾을 수 없는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="20377-148">해결 방법</span><span class="sxs-lookup"><span data-stu-id="20377-148">Resolution</span></span>

1. <span data-ttu-id="20377-149">[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-149">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="20377-150">사용자가 Exchange Online Protection과 동기화 되었는지 확인 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-150">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="20377-151">사용자 질문에 대 한 메일 사용자 개체가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-151">There should be a mail user object for the user question.</span></span> <span data-ttu-id="20377-152">아무 것도 반환 하지 않으면 사용자 개체를 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="20377-153">개체를 동기화 할 수 없으면 Microsoft 지원에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="20377-153">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="20377-154">오류/문제: 검색 결과를 내보내는 속도가 느림</span><span class="sxs-lookup"><span data-stu-id="20377-154">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="20377-155">보안 및 준수 센터에서 eDiscovery 또는 콘텐츠 검색의 검색 결과를 내보낼 때 다운로드가 예상 보다 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="20377-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="20377-156">다운로드 해야 하는 데이터의 양을 확인 하 고 내보내기 속도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="20377-157">해결 방법</span><span class="sxs-lookup"><span data-stu-id="20377-157">Resolution</span></span>

1. <span data-ttu-id="20377-158">[다운로드 속도 증가](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)문서에서 식별 된 단계를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="20377-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>

2. <span data-ttu-id="20377-159">문제가 계속 되 면 [보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 에 연결 하 고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-159">If you still have issues, connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="20377-160">SearchResults 및 Searchresults 매개 변수로 다운로드할 데이터 양을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

4. <span data-ttu-id="20377-161">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-161">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

5. <span data-ttu-id="20377-162">결과 필드에서 내보낸 데이터를 찾아 발생 한 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-162">In the results field, find the data that has been exported and view any errors encountered.</span></span>

6. <span data-ttu-id="20377-163">오류에 대해 콘텐츠를 내보낸 디렉터리에 있는 trace 파일을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="20377-164">오류/문제: "내부 서버 오류 (500)가 발생 했습니다."</span><span class="sxs-lookup"><span data-stu-id="20377-164">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="20377-165">EDiscovery 검색을 실행할 때 "내부 서버 오류 (500)이 발생 했습니다."와 유사한 오류와 함께 검색이 계속 실패 하면 특정 사서함 위치에 대해서만 검색을 다시 실행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![내부 서버 오류 500 스크린샷](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="20377-167">해결 방법</span><span class="sxs-lookup"><span data-stu-id="20377-167">Resolution</span></span>

1. <span data-ttu-id="20377-168">검색을 더 작은 검색으로 나누고 검색을 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="20377-169">더 작은 날짜 범위를 사용 하거나 검색 중인 위치 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-169">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="20377-170">[보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 에 연결한 후 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-170">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="20377-171">결과 및 오류에 대 한 출력을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-171">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="20377-172">추적 .log 파일을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-172">Examine the trace.log file.</span></span> <span data-ttu-id="20377-173">검색 결과를 내보낸 것과 같은 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-173">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="20377-174">Microsoft 지원 팀에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-174">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="20377-175">오류/문제: 보류가 동기화 되지 않음</span><span class="sxs-lookup"><span data-stu-id="20377-175">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="20377-176">eDiscovery 사례 보류 정책 동기화 배포 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="20377-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="20377-177">오류는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-177">The error reads:</span></span>

> <span data-ttu-id="20377-178">"리소스: 정책을 배포 하는 데 예상 보다 오래 걸리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20377-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="20377-179">최종 배포 상태를 업데이트 하는 데 2 시간이 더 소요 될 수도 있으므로 몇 시간 후에 다시 확인 하세요. "</span><span class="sxs-lookup"><span data-stu-id="20377-179">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="20377-180">해결 방법</span><span class="sxs-lookup"><span data-stu-id="20377-180">Resolution</span></span>

1. <span data-ttu-id="20377-181">[보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 에 연결한 후 eDiscovery 사례 보류에 대해 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-181">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="20377-182">보존 정책에 대해 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-182">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="20377-183">DistributionDetail 매개 변수의 값을 검사 하 여 다음과 같은 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-183">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="20377-184">오류: 리소스: 정책을 배포 하는 데 예상 보다 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="20377-184">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="20377-185">최종 배포 상태를 업데이트 하는 데 2 시간이 더 소요 될 수도 있으므로 몇 시간 후에 다시 확인 하세요. "</span><span class="sxs-lookup"><span data-stu-id="20377-185">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="20377-186">문제가 있는 정책에서 RetryDistribution 매개 변수를 실행 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="20377-186">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="20377-187">EDiscovery 사례 보류의 경우:</span><span class="sxs-lookup"><span data-stu-id="20377-187">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="20377-188">보존 정책:</span><span class="sxs-lookup"><span data-stu-id="20377-188">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="20377-189">Microsoft 지원 팀에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="20377-189">Contact Microsoft Support.</span></span>

## <a name="see-also"></a><span data-ttu-id="20377-190">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20377-190">See Also</span></span>

- [<span data-ttu-id="20377-191">콘텐츠 위치 오류를 방지 하기 위한 팁</span><span class="sxs-lookup"><span data-stu-id="20377-191">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
