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
ms.openlocfilehash: d71091b4c3545880b103b8d4a4111b3c63d35506
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218965"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>일반적인 eDiscovery 문제 조사, 문제 해결

이 항목에서는 eDiscovery 검색 중이나 eDiscovery 프로세스의 다른 곳에서 발생할 수 있는 문제를 식별하고 해결하기 위해 취할 수 있는 기본 문제 해결 단계를 다단계로 제공합니다. 이러한 시나리오 중 일부를 해소하려면 Microsoft 지원에 도움이 필요합니다. Microsoft 지원에 문의하는 경우의 정보는 해결 단계에 포함되어 있습니다.

## <a name="errorissue-ambiguous-location"></a>오류/문제: 모호한 위치

검색할 사용자의 사서함 위치를 추가하려고 하여 EOP(Exchange Online Protection) 디렉터리에 동일한 userID를 사용하여 중복되거나 충돌하는 개체가 있는 경우 다음 오류가 발생합니다. `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>해결 방법

사용자 ID가 같은 중복 사용자 또는 메일 목록을 검사합니다.

1. 커넥트 보안 및 [& 센터 PowerShell에 대한 정보를 제공합니다.](/powershell/exchange/connect-to-scc-powershell)

2. 다음 명령을 실행하여 사용자 이름의 모든 인스턴스를 검색합니다.

    ```powershell
    Get-Recipient <username>
    ```

   'useralias@contoso.com'의 출력은 다음과 유사합니다.

   > 
   > |이름|RecipientType|
   > |---|---|
   > |별칭, 사용자|MailUser|
   > |별칭, 사용자|사용자|

3. 여러 사용자가 반환되는 경우 충돌하는 개체를 찾아 수정합니다.

## <a name="errorissue-search-fails-on-specific-locations"></a>오류/문제: 특정 위치에서 검색 실패

eDiscovery 또는 콘텐츠 검색을 통해 다음 오류가 발생할 수 있습니다. `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![검색 관련 위치 실패 오류 스크린샷.](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>해결 방법

이 오류가 발생하는 경우 검색에 실패한 위치를 확인한 다음 실패한 위치에서만 검색을 다시 하는 것이 좋습니다.

1. 커넥트 보안 & [PowerShell에](/powershell/exchange/connect-to-scc-powershell) 대한 정보를 보고 다음 명령을 실행합니다.

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. PowerShell 출력에서 오류 필드의 실패한 위치를 보거나 검색 출력에서 오류의 상태 세부 정보를 본다.

3. 실패한 위치에서만 eDiscovery 검색을 다시 시도합니다.

4. 이러한 오류가 계속 발생하는 경우 자세한 문제 해결 단계는 [실패한](/Office365/SecurityCompliance/retry-failed-content-search) 위치 다시 시도를 참조하세요.

## <a name="errorissue-file-not-found"></a>오류/문제: 파일을 찾을 수 없습니다.

SharePoint Online 및 비즈니스용 OneDrive 포함된 eDiscovery 검색을 실행하는 경우 파일이 사이트에 있는 경우 오류가 발생할 `File Not Found` 수 있습니다. 이 오류는 내보내기 경고에 추가되거나 errors.csv 건너뜁 items.csv. 사이트에서 파일을 찾을 수 없는 경우나 인덱스가 최신이 아니면 이러한 문제가 발생할 수 있습니다. 다음은 실제 오류 텍스트입니다(강조 표시 추가).

> 28.06.2019 10:02:19_FailedToExportItem_Failed 다운로드할 수 있습니다. 추가 진단 정보: Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Document 형식의 콘텐츠 6ea52149-91cd-4965-b5bb-82ca6a3ec9be에서 다운로드하지 못했습니다. 상관 관계 ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***파일을 찾을 수 없습니다.*** Microsoft. SharePoint. Microsoft의 Client.ClientRequest.ProcessResponseStream(Stream responseStream) SharePoint. Client.ClientRequest.ProcessResponse() --- 내부 예외 스택 추적 종료 ---

### <a name="resolution"></a>해결 방법

1. 검색에서 식별된 위치를 확인하여 파일의 위치가 올바른지 확인하고 검색 위치에 추가하는지 확인합니다.

2. 사이트, 라이브러리 [](/sharepoint/crawl-site-content) 또는 목록의 크롤링 및 다시 인덱싱을 수동으로 요청하는 절차에 따라 사이트를 다시 인덱싱합니다.

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a>오류/문제: 더 이상 존재하지 않는 이 파일을 내보낼 수 없습니다. 파일은 인덱스에 계속 나열되어 있기 때문에 예상 검색 결과 수에 포함되어 있습니다. 결국 파일은 인덱스에서 제거되고 나중에 오류가 발생하지 않습니다.

온라인 및 검색 위치가 포함된 eDiscovery 검색을 실행하면 SharePoint 수 비즈니스용 OneDrive 있습니다. eDiscovery는 SPO 인덱스를 사용하여 파일 위치를 식별합니다. 파일을 삭제했지만 SPO 인덱스가 아직 업데이트되지 않은 경우 이 오류가 발생할 수 있습니다.

### <a name="resolution"></a>해결 방법 

SPO 위치를 열고 이 파일이 실제로 해당 위치에 없는지 확인해야 합니다.
권장되는 해결 방법은 사이트를 수동으로 다시 인덱스하거나 사이트가 자동 백그라운드 프로세스에 의해 다시 인덱스될 때까지 기다리는 것입니다.

## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artifact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a>오류/문제: 폴더 또는 자체적으로 다운로드할 수 없는 다른 아티팩트이기 때문에 이 검색 결과가 다운로드되지 않은 경우 폴더 또는 라이브러리의 항목이 다운로드됩니다.

온라인 및 검색 위치가 포함된 eDiscovery 검색을 실행하면 SharePoint 수 비즈니스용 OneDrive 있습니다. 즉, 인덱스에 보고된 항목을 시도하고 내보내려고 했지만 내보낼 수 없는 폴더로 표시되었습니다. 오류에서 설명한 것 처럼 폴더 항목을 내보낼 수 없지만 해당 콘텐츠를 내보낼 수 있습니다.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>오류/문제: 받는 사람을 찾을 수 없는 경우 검색이 실패합니다.

eDiscovery 검색은 오류와 함께 `recipient not found` 실패합니다. 이 오류는 개체가 동기화되지 않은 EOP(Exchange Online Protection)에서 사용자 개체를 찾을 수 없는 경우 발생할 수 있습니다.

### <a name="resolution"></a>해결 방법

1. 커넥트 [PowerShell을 Exchange Online 합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

2. 다음 명령을 실행하여 사용자가 동기화된 Exchange Online Protection.

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. 사용자 질문에 대한 메일 사용자 개체가 있습니다. 반환되는 개체가 없는 경우 사용자 개체를 조사합니다. 개체를 동기화할 수 없는 경우 Microsoft 지원에 문의합니다.

## <a name="issueerror-search-fails-with-error-cs007"></a>문제/오류: 오류 CS007로 검색 실패

콘텐츠 검색 또는 Core eDiscovery 사례와 연결된 검색을 수행할 때 일시적인 오류가 발생하고 CS007 오류로 검색이 실패합니다.

### <a name="resolution"></a>해결 방법

1. 검색을 업데이트하고 검색 쿼리의 복잡성을 줄입니다.  예를 들어 와일드카드 검색에서는 시스템이 너무 많은 결과를 반환하여 CS007 오류가 발생할 수 있습니다.

2. 업데이트된 검색을 다시런합니다.

## <a name="errorissue-exporting-search-results-is-slow"></a>오류/문제: 검색 결과 내보내기 속도가 느립니다.

핵심 eDiscovery 또는 콘텐츠 검색에서 검색 결과를 내보낼 Microsoft 365 규정 준수 센터 다운로드 시간이 예상보다 오래 걸러야 합니다.  다운로드할 데이터의 양을 확인하고 내보내기 속도를 늘일 수 있습니다.

### <a name="resolution"></a>해결 방법

1. 커넥트 보안 & [PowerShell에](/powershell/exchange/connect-to-scc-powershell) 대한 정보를 보고 다음 명령을 실행합니다.

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. SearchResults 및 SearchStatistics 매개 변수에서 다운로드할 데이터의 양을 검색합니다.

3. 다음 명령을 실행합니다.

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. 결과 필드에서 내보낼 데이터를 찾고 발생하는 오류를 찾습니다.

5. 콘텐츠를 내보낼 디렉터리에 있는 trace.log 파일을 확인하여 오류를 확인합니다.

6. 그래도 문제가 있는 경우 많은 결과 집합을 작은 검색으로 반환하는 검색을 나중을 고려합니다. 예를 들어 검색 쿼리에서 날짜 범위를 사용하여 더 빠르게 다운로드할 수 있는 더 작은 결과 집합을 반환할 수 있습니다.

## <a name="errorissue-export-process-not-progressing-or-is-stuck"></a>오류/문제: 내보내기 프로세스가 진행 중이 아니거나 문제가 발생했습니다.

핵심 eDiscovery 또는 콘텐츠 검색에서 검색 결과를 내보낼 Microsoft 365 규정 준수 센터 내보내기 프로세스가 진행 중이 아니거나 빨라진 것으로 나타납니다.

### <a name="resolution"></a>해결 방법

1. 필요한 경우 검색을 다시합니다. 검색이 7일을 넘게 지난 경우 검색을 다시 시작해야 합니다.

2. 내보내기 작업을 다시 시작합니다.

## <a name="errorissue-internal-server-error-500-occurred"></a>오류/문제: "내부 서버 오류(500)가 발생했습니다."

eDiscovery 검색을 실행하는 경우 "내부 서버 오류(500)가 발생했습니다."와 유사한 오류로 검색이 계속 실패하면 특정 사서함 위치에서만 검색을 다시 실행해야 할 수 있습니다.

![내부 서버 오류 500 스크린샷.](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>해결 방법

1. 더 작은 검색으로 검색을 중단하고 검색을 다시 실행합니다.  더 작은 날짜 범위를 사용해 보거나 검색되는 위치 수를 제한합니다.

2. 커넥트 보안 & [PowerShell에](/powershell/exchange/connect-to-scc-powershell) 대한 정보를 보고 다음 명령을 실행합니다.

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. 출력에서 결과 및 오류를 검사합니다.

4. trace.log 파일을 검사합니다. 이 위치는 검색 결과를 내보낼 때와 동일한 폴더에 있습니다.

5. Microsoft 지원 팀에 문의합니다.

## <a name="errorissue-holds-dont-sync"></a>오류/문제: 보류가 동기화되지 않습니다.

eDiscovery 사례 보류 정책 동기화 배포 오류입니다. 오류는 다음을 읽습니다.

> "리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다. 최종 배포 상태를 업데이트하는 데 추가 2시간이 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다."

### <a name="resolution"></a>해결 방법

1. 커넥트 보안 & [센터 PowerShell을](/powershell/exchange/connect-to-scc-powershell) 사용하여 eDiscovery 사례 보류에 대해 다음 명령을 실행합니다.

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    보존 정책의 경우 다음 명령을 실행합니다.

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. DistributionDetail 매개 변수의 값에서 다음과 같은 오류를 검사합니다.

   > 오류: 리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다. 최종 배포 상태를 업데이트하는 데 추가 2시간이 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다."

3. 문제의 정책에서 RetryDistribution 매개 변수를 실행합니다.

   eDiscovery 사례 보류의 경우:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   보존 정책의 경우:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Microsoft 지원 팀에 문의합니다.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>오류: "HTTP 조건부 헤더를 사용하여 지정한 조건이 충족되지 않았습니다."

eDiscovery 내보내기 도구를 사용하여 검색 결과를 다운로드할 때 다음과 같은 오류가 발생할 수 있습니다. 이 오류는 일반적으로 Azure Storage `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 오류입니다.

### <a name="resolution"></a>해결 방법

이 문제를 해결하려면 eDiscovery 내보내기 도구를 다시 시작하는 검색 결과 다운로드를 다시 시도합니다. [](export-search-results.md#step-2-download-the-search-results)

## <a name="errorissue-downloaded-export-shows-no-results"></a>오류/문제: 다운로드한 내보내기에서 결과가 표시되지 않습니다.

내보내기 성공 후 내보내기 도구를 통해 완료된 다운로드는 결과에 파일 0을 보여줍니다.

### <a name="resolution"></a>해결 방법

이는 클라이언트 쪽 문제입니다. 이를 수정하기 위해 다음 단계를 따르세요.

1. 다른 클라이언트/컴퓨터로 다운로드해 하세요.

2. [Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) cmdlet을 사용하여 더 이상 필요 없는 이전 검색을 제거합니다.

3. 로컬 드라이브에 다운로드해야 합니다.

4. 바이러스 스캐너가 실행되고 있지 않은지 확인

5. 다른 내보내기에서 동일한 폴더나 상위 폴더로 다운로드하지 않는지 확인합니다.

6. 이전 단계가 작동하지 않는 경우 압축 및 중복 제거를 사용하지 않도록 설정하십시오.

7. 이 문제가 작동하는 경우 로컬 바이러스 스캐너 또는 디스크 문제 때문인 것입니다.

## <a name="error-your-request-cant-be-started-because-the-maximum-number-of-jobs-for-your-organization-are-currently-running"></a>오류: "조직의 최대 작업 수가 현재 실행 중이기 때문에 요청을 시작할 수 없습니다."

조직이 최대 동시 내보내기 작업 수 제한에 도달했습니다. 모든 새 내보내기 작업이 스로틀됩니다.

### <a name="resolution"></a>해결 방법

다음 스크립트를 실행하여 지난 7일 동안 시작된 내보내기 작업이 아직 실행되고 있는 수를 검색합니다.

1. 커넥트 보안 및 [& 센터 PowerShell에 대한 정보를 제공합니다.](/powershell/exchange/connect-to-scc-powershell)

2. 다음 스크립트를 실행하여 현재 내보내기 작업에서 스로틀을 트리거하는 정보를 수집합니다.

   ```powershell
   $date = Get-Date;
   $exports = Get-ComplianceSearchAction -Export -ResultSize Unlimited;
   $inprogressExports = $exports | ?{$_.Results -eq $null -or (!$_.Results.Contains("Export status: Completed") -and !$_.Results.Contains("Export status: none"))};
   $exportJobsRunning = $inprogressExports | ?{$_.JobStartTime -ge $date.AddDays(-7)} | Sort-Object JobStartTime -Descending;
   ```

3. 다음 명령을 실행하여 현재 실행 중인 내보내기 작업 목록을 표시합니다.

   ```powershell
   $exportJobsRunning | Format-Table Name, JobStartTime, JobEndTime, Status | More;
   ```

   이전 명령이 10개 이상의 내보내기 작업을 반환하면 조직에서 동시 내보내기 작업 수 제한에 도달한 것입니다. 자세한 내용은 [eDiscovery](limits-for-content-search.md)검색 제한을 참조하세요.

4. [Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) cmdlet을 사용하여 더 이상 필요 없는 기존 내보내기 작업이 완료될 때까지 기다리거나 제거할 수 있습니다.
