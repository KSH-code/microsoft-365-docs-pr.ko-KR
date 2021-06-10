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
description: eDiscovery에서 일반적인 문제를 해결하기 위해 취할 수 있는 기본 문제 Office 365 대해 자세히 알아보십시오.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28c092cefbdd8add46d3f36aa118e230d16a918a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822241"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="f38e1-103">일반적인 eDiscovery 문제 조사, 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f38e1-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="f38e1-104">이 항목에서는 eDiscovery 검색 중이나 eDiscovery 프로세스의 다른 곳에서 발생할 수 있는 문제를 식별하고 해결하기 위해 취할 수 있는 기본 문제 해결 단계를 다단계로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="f38e1-105">이러한 시나리오 중 일부를 해소하려면 Microsoft 지원에 도움이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="f38e1-106">Microsoft 지원에 문의하는 경우의 정보는 해결 단계에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="f38e1-107">오류/문제: 모호한 위치</span><span class="sxs-lookup"><span data-stu-id="f38e1-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="f38e1-108">검색할 사용자의 사서함 위치를 추가하려고 하여 EOP(Exchange Online Protection) 디렉터리에 동일한 userID를 사용하여 중복되거나 충돌하는 개체가 있는 경우 다음 오류가 발생합니다. `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="f38e1-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="f38e1-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-109">Resolution</span></span>

<span data-ttu-id="f38e1-110">사용자 ID가 같은 중복 사용자 또는 메일 목록을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="f38e1-111">커넥트 보안 및 [& 센터 PowerShell에 대한 정보를 제공합니다.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="f38e1-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="f38e1-112">다음 명령을 실행하여 사용자 이름의 모든 인스턴스를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="f38e1-113">'useralias@contoso.com'의 출력은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="f38e1-114">이름</span><span class="sxs-lookup"><span data-stu-id="f38e1-114">Name</span></span>|<span data-ttu-id="f38e1-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="f38e1-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="f38e1-116">별칭, 사용자</span><span class="sxs-lookup"><span data-stu-id="f38e1-116">Alias, User</span></span>|<span data-ttu-id="f38e1-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="f38e1-117">MailUser</span></span>|
   > |<span data-ttu-id="f38e1-118">별칭, 사용자</span><span class="sxs-lookup"><span data-stu-id="f38e1-118">Alias, User</span></span>|<span data-ttu-id="f38e1-119">사용자</span><span class="sxs-lookup"><span data-stu-id="f38e1-119">User</span></span>|

3. <span data-ttu-id="f38e1-120">여러 사용자가 반환되는 경우 충돌하는 개체를 찾아 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="f38e1-121">오류/문제: 특정 위치에서 검색 실패</span><span class="sxs-lookup"><span data-stu-id="f38e1-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="f38e1-122">eDiscovery 또는 콘텐츠 검색을 통해 다음 오류가 발생할 수 있습니다. `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="f38e1-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![검색 관련 위치 실패 오류 스크린샷](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="f38e1-124">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-124">Resolution</span></span>

<span data-ttu-id="f38e1-125">이 오류가 발생하는 경우 검색에 실패한 위치를 확인한 다음 실패한 위치에서만 검색을 다시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="f38e1-126">커넥트 보안 & [PowerShell에](/powershell/exchange/connect-to-scc-powershell) 대한 정보를 보고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="f38e1-127">PowerShell 출력에서 오류 필드의 실패한 위치를 보거나 검색 출력에서 오류의 상태 세부 정보를 본다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="f38e1-128">실패한 위치에서만 eDiscovery 검색을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="f38e1-129">이러한 오류가 계속 발생하는 경우 자세한 문제 해결 단계는 [실패한](/Office365/SecurityCompliance/retry-failed-content-search) 위치 다시 시도를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f38e1-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="f38e1-130">오류/문제: 파일을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-130">Error/issue: File not found</span></span>

<span data-ttu-id="f38e1-131">SharePoint Online 및 비즈니스용 OneDiscovery 위치를 포함하는 eDiscovery 검색을 실행하는 경우 파일이 사이트에 있는 경우 오류가 발생할 `File Not Found` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="f38e1-132">이 오류는 내보내기 경고에 추가되거나 errors.csv 건너뜁 items.csv.</span><span class="sxs-lookup"><span data-stu-id="f38e1-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="f38e1-133">사이트에서 파일을 찾을 수 없는 경우나 인덱스가 최신이 아니면 이러한 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="f38e1-134">다음은 실제 오류 텍스트입니다(강조 표시 추가).</span><span class="sxs-lookup"><span data-stu-id="f38e1-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="f38e1-135">28.06.2019 10:02:19_FailedToExportItem_Failed 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="f38e1-136">추가 진단 정보: Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Document 형식의 콘텐츠 6ea52149-91cd-4965-b5bb-82ca6a3ec9be에서 다운로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="f38e1-137">상관 관계 ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="f38e1-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="f38e1-138">ServerErrorCode: Microsoft에서 -2147024894 --->. SharePoint. Client.ServerException: ***파일을 찾을 수 없습니다.***</span><span class="sxs-lookup"><span data-stu-id="f38e1-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="f38e1-139">Microsoft. SharePoint. Microsoft의 Client.ClientRequest.ProcessResponseStream(Stream responseStream) SharePoint. Client.ClientRequest.ProcessResponse() --- 내부 예외 스택 추적 종료 ---</span><span class="sxs-lookup"><span data-stu-id="f38e1-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="f38e1-140">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-140">Resolution</span></span>

1. <span data-ttu-id="f38e1-141">검색에서 식별된 위치를 확인하여 파일의 위치가 올바른지 확인하고 검색 위치에 추가하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-141">Check location identified in the search to ensure that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="f38e1-142">사이트, 라이브러리 [](/sharepoint/crawl-site-content) 또는 목록의 크롤링 및 다시 인덱싱을 수동으로 요청하는 절차에 따라 사이트를 다시 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a><span data-ttu-id="f38e1-143">오류/문제: 더 이상 존재하지 않는 이 파일을 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-143">Error/issue: This file wasn't exported because it doesn't exist anymore.</span></span> <span data-ttu-id="f38e1-144">파일은 인덱스에 계속 나열되어 있기 때문에 예상 검색 결과 수에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-144">The file was included in the count of estimated search results because it's still listed in the index.</span></span> <span data-ttu-id="f38e1-145">결국 파일은 인덱스에서 제거되고 나중에 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-145">The file will eventually be removed from the index, and won't cause an error in the future.</span></span>

<span data-ttu-id="f38e1-146">온라인 및 비즈니스용 OneDiscovery 위치를 포함하는 eDiscovery 검색을 SharePoint 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-146">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="f38e1-147">eDiscovery는 SPO 인덱스를 사용하여 파일 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-147">eDiscovery relies on teh SPO index to identify the file locations.</span></span> <span data-ttu-id="f38e1-148">파일을 삭제했지만 SPO 인덱스가 아직 업데이트되지 않은 경우 이 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-148">If the file was deleted but the SPO index was not yet updated this error may occur.</span></span>

### <a name="resolution"></a><span data-ttu-id="f38e1-149">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-149">Resolution</span></span> 
<span data-ttu-id="f38e1-150">SPO 위치를 열고 이 파일이 실제로 해당 위치에 없는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-150">Open the SPO location and verify that this file indeed is not there.</span></span>
<span data-ttu-id="f38e1-151">권장되는 해결 방법은 사이트를 수동으로 다시 인덱스하거나 사이트가 자동 백그라운드 프로세스에 의해 다시 인덱스될 때까지 기다리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-151">Suggested solution is to manually reindex the site, or wait till the site reindexes by the automatic background process.</span></span>


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artefact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a><span data-ttu-id="f38e1-152">오류/문제: 폴더 또는 자체적으로 다운로드할 수 없는 다른 아트 페이지이기 때문에 이 검색 결과가 다운로드되지 않은 경우 폴더 또는 라이브러리의 항목이 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-152">Error/issue: This search result was not downloaded as it is a folder or other artefact that can't be downloaded by itself, any items inside the folder or library will be downloaded.</span></span>

<span data-ttu-id="f38e1-153">온라인 및 비즈니스용 OneDiscovery 위치를 포함하는 eDiscovery 검색을 SharePoint 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-153">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="f38e1-154">즉, 인덱스에 보고된 항목을 시도하고 내보내려고 했지만 내보낼 수 없는 폴더로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-154">It means that we were going to try and export the item reported in the index, but it turned out to be a folder so we did not export it.</span></span> <span data-ttu-id="f38e1-155">오류에서 설명한 것 처럼 폴더 항목을 내보낼 수 없지만 해당 콘텐츠를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-155">As mentioned in the error, we don't export folder items but we do export their contents.</span></span>


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="f38e1-156">오류/문제: 받는 사람을 찾을 수 없는 경우 검색이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-156">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="f38e1-157">eDiscovery 검색은 오류와 함께 `recipient not found` 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-157">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="f38e1-158">이 오류는 개체가 동기화되지 않은 EOP(Exchange Online Protection)에서 사용자 개체를 찾을 수 없는 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-158">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="f38e1-159">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-159">Resolution</span></span>

1. <span data-ttu-id="f38e1-160">커넥트 [PowerShell을 Exchange Online 합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f38e1-160">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f38e1-161">다음 명령을 실행하여 사용자가 동기화된 Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="f38e1-161">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="f38e1-162">사용자 질문에 대한 메일 사용자 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-162">There should be a mail user object for the user question.</span></span> <span data-ttu-id="f38e1-163">반환되는 개체가 없는 경우 사용자 개체를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-163">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="f38e1-164">개체를 동기화할 수 없는 경우 Microsoft 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-164">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="f38e1-165">오류/문제: 검색 결과 내보내기 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-165">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="f38e1-166">보안 및 준수 센터에서 eDiscovery 또는 콘텐츠 검색에서 검색 결과를 내보낼 때 다운로드 시간이 예상보다 오래 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-166">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="f38e1-167">다운로드할 데이터의 양을 확인하고 내보내기 속도를 늘일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-167">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="f38e1-168">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-168">Resolution</span></span>

1. <span data-ttu-id="f38e1-169">커넥트 보안 & [PowerShell에](/powershell/exchange/connect-to-scc-powershell) 대한 정보를 보고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="f38e1-170">SearchResults 및 SearchStatistics 매개 변수에서 다운로드할 데이터의 양을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-170">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="f38e1-171">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-171">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="f38e1-172">결과 필드에서 내보낼 데이터를 찾고 발생하는 오류를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-172">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="f38e1-173">콘텐츠를 내보낼 디렉터리에 있는 trace.log 파일을 확인하여 오류를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-173">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="f38e1-174">그래도 문제가 있는 경우 많은 결과 집합을 작은 검색으로 반환하는 검색을 나중을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-174">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="f38e1-175">예를 들어 검색 쿼리에서 날짜 범위를 사용하여 더 빠르게 다운로드할 수 있는 더 작은 결과 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-175">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="f38e1-176">오류/문제: "내부 서버 오류(500)가 발생했습니다."</span><span class="sxs-lookup"><span data-stu-id="f38e1-176">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="f38e1-177">eDiscovery 검색을 실행하는 경우 "내부 서버 오류(500)가 발생했습니다."와 유사한 오류로 검색이 계속 실패하면 특정 사서함 위치에서만 검색을 다시 실행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-177">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![내부 서버 오류 500 스크린샷](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="f38e1-179">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-179">Resolution</span></span>

1. <span data-ttu-id="f38e1-180">더 작은 검색으로 검색을 중단하고 검색을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-180">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="f38e1-181">더 작은 날짜 범위를 사용해 보거나 검색되는 위치 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-181">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="f38e1-182">커넥트 보안 & [PowerShell에](/powershell/exchange/connect-to-scc-powershell) 대한 정보를 보고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-182">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="f38e1-183">출력에서 결과 및 오류를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-183">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="f38e1-184">trace.log 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-184">Examine the trace.log file.</span></span> <span data-ttu-id="f38e1-185">이 위치는 검색 결과를 내보낼 때와 동일한 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-185">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="f38e1-186">Microsoft 지원 팀에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-186">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="f38e1-187">오류/문제: 보류가 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-187">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="f38e1-188">eDiscovery 사례 보류 정책 동기화 배포 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-188">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="f38e1-189">오류는 다음을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-189">The error reads:</span></span>

> <span data-ttu-id="f38e1-190">"리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-190">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="f38e1-191">최종 배포 상태를 업데이트하는 데 추가 2시간이 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다."</span><span class="sxs-lookup"><span data-stu-id="f38e1-191">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="f38e1-192">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-192">Resolution</span></span>

1. <span data-ttu-id="f38e1-193">커넥트 보안 & [센터 PowerShell을](/powershell/exchange/connect-to-scc-powershell) 사용하여 eDiscovery 사례 보류에 대해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-193">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="f38e1-194">보존 정책의 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-194">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="f38e1-195">DistributionDetail 매개 변수의 값에서 다음과 같은 오류를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-195">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="f38e1-196">오류: 리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-196">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="f38e1-197">최종 배포 상태를 업데이트하는 데 추가 2시간이 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다."</span><span class="sxs-lookup"><span data-stu-id="f38e1-197">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="f38e1-198">문제의 정책에서 RetryDistribution 매개 변수를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-198">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="f38e1-199">eDiscovery 사례 보류의 경우:</span><span class="sxs-lookup"><span data-stu-id="f38e1-199">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="f38e1-200">보존 정책의 경우:</span><span class="sxs-lookup"><span data-stu-id="f38e1-200">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="f38e1-201">Microsoft 지원 팀에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-201">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="f38e1-202">오류: "HTTP 조건부 헤더를 사용하여 지정한 조건이 충족되지 않았습니다."</span><span class="sxs-lookup"><span data-stu-id="f38e1-202">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="f38e1-203">eDiscovery 내보내기 도구를 사용하여 검색 결과를 다운로드할 때 다음과 같은 오류가 발생할 수 있습니다. 이 오류는 일반적으로 Azure Storage `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-203">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="f38e1-204">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-204">Resolution</span></span>

<span data-ttu-id="f38e1-205">이 문제를 해결하려면 eDiscovery 내보내기 도구를 다시 시작하는 검색 결과 다운로드를 다시 시도합니다. [](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="f38e1-205">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="f38e1-206">오류/문제: 다운로드한 내보내기에서 결과가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-206">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="f38e1-207">내보내기 성공 후 내보내기 도구를 통해 완료된 다운로드는 결과에 파일 0을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-207">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="f38e1-208">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f38e1-208">Resolution</span></span>

<span data-ttu-id="f38e1-209">이는 클라이언트 쪽 문제로, 이를 수정하기 위해 다음 단계를 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="f38e1-209">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="f38e1-210">다른 클라이언트/컴퓨터로 다운로드해 하세요.</span><span class="sxs-lookup"><span data-stu-id="f38e1-210">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="f38e1-211">[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) cmdlet을 사용하여 더 이상 필요 없는 이전 검색을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-211">Remove old searches that are no longer needed using [Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) cmdlet.</span></span>

3. <span data-ttu-id="f38e1-212">로컬 드라이브에 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-212">Make sure to download to a local drive.</span></span>

4. <span data-ttu-id="f38e1-213">바이러스 스캐너가 실행되고 있지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="f38e1-213">Make sure the virus scanner is not running.</span></span>

5. <span data-ttu-id="f38e1-214">다른 내보내기에서 동일한 폴더나 상위 폴더로 다운로드하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-214">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

6. <span data-ttu-id="f38e1-215">이전 단계가 작동하지 않는 경우 압축 및 중복 제거를 사용하지 않도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="f38e1-215">If the previous steps did not work, disable zipping and de-duplication.</span></span>

7. <span data-ttu-id="f38e1-216">이 문제가 작동하는 경우 로컬 바이러스 스캐너 또는 디스크 문제 때문인 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f38e1-216">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
