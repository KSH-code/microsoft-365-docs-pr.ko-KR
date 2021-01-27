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
description: Office 365 eDiscovery에서 일반적인 문제를 해결하기 위해 취할 수 있는 기본 문제 해결 단계에 대해 자세히 알아보십시오.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1fbda23b730956db42d8e7a92218fb9837868b8
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988142"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>일반적인 eDiscovery 문제 조사, 문제 해결 및 해결

이 항목에서는 eDiscovery 검색 중 또는 eDiscovery 프로세스의 다른 곳에서 발생할 수 있는 문제를 식별하고 해결하기 위해 취할 수 있는 기본적인 문제 해결 단계를 다단계로 다단계에서 다단계에서 다단계로 하여금 확인할 수 있습니다. 이러한 시나리오 중 일부를 해소하려면 Microsoft 지원의 도움이 필요합니다. Microsoft 지원에 문의하는 경우의 정보는 해결 단계에 포함되어 있습니다.

## <a name="errorissue-ambiguous-location"></a>오류/문제: 모호한 위치

검색할 사용자의 사서함 위치를 추가하려고 하여 EOP(Exchange Online Protection) 디렉터리에 동일한 userID를 사용하여 중복되거나 충돌하는 개체가 있는 경우 다음 오류가 `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` 발생합니다.

### <a name="resolution"></a>해결 방법

사용자 ID가 같은 중복 사용자 또는 메일 목록을 검사합니다.

1. 보안 및 [& 센터 PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

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

eDiscovery 또는 콘텐츠 검색에서는 다음 오류가 발생할 수 있습니다. `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![검색 관련 위치 실패 오류 스크린샷](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>해결 방법

이 오류가 발생하면 검색에 실패한 위치를 확인한 다음 실패한 위치에서만 검색을 다시 발생하는 것이 좋습니다.

1. 보안 & 준수 센터 [PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 연결한 다음 다음 명령을 실행합니다.

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. PowerShell 출력에서 오류 필드의 실패한 위치를 보거나 검색 출력에서 오류의 상태 세부 정보에서 볼 수 있습니다.

3. 실패한 위치에서만 eDiscovery 검색을 다시 시도합니다.

4. 이러한 오류가 계속 발생하는 경우 [](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) 추가 문제 해결 단계를 위해 실패한 위치를 다시 시도하십시오.

## <a name="errorissue-file-not-found"></a>오류/문제: 파일을 찾을 수 없습니다.

SharePoint Online 및 비즈니스용 OneDiscovery 위치를 포함하는 eDiscovery 검색을 실행하는 경우 파일이 사이트에 있는 경우 오류가 발생할 `File Not Found` 수 있습니다. 이 오류는 내보내기 경고에 추가되거나 errors.csv 건너뜁니다items.csv. 사이트에서 파일을 찾을 수 없는 경우나 인덱스가 최신이 아니면 이러한 문제가 발생할 수 있습니다. 다음은 실제 오류 텍스트입니다(강조 표시 추가).

> 28.06.2019 10:02:19_FailedToExportItem_Failed 콘텐츠를 다운로드합니다. 추가 진단 정보: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: 문서 유형의 콘텐츠 6ea52149-91cd-4965-b5bb-82ca6a3ec9be에서 다운로드하지 못했습니다. 상관 관계 ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 --->.SharePoint.Client.ServerException: ***파일을 찾을 수 없습니다.*** Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream)의 Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- 내부 예외 스택 추적 종료 ---

### <a name="resolution"></a>해결 방법

1. 검색에서 식별된 위치를 확인하여 파일의 위치가 올바른지 확인하고 검색 위치에 추가하는지 확인합니다.

2. 사이트, [라이브러리](https://docs.microsoft.com/sharepoint/crawl-site-content) 또는 목록의 크롤링 및 다시 인덱싱을 수동으로 요청하는 절차에 따라 사이트를 다시 인덱싱합니다.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>오류/문제: 받는 사람을 찾을 수 없는 경우 검색이 실패합니다.

eDiscovery 검색은 오류와 함께 `recipient not found` 실패합니다. 개체가 동기화되지 않은 경우 EOP(Exchange Online Protection)에서 사용자 개체를 찾을 수 없는 경우 이 오류가 발생할 수 있습니다.

### <a name="resolution"></a>해결 방법

1. Exchange [Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. 다음 명령을 실행하여 사용자가 Exchange Online Protection에 동기화된지 검사합니다.

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. 사용자 질문에 대한 메일 사용자 개체가 있습니다. 반환되는 개체가 없는 경우 사용자 개체를 조사합니다. 개체를 동기화할 수 없는 경우 Microsoft 지원에 문의합니다.

## <a name="errorissue-exporting-search-results-is-slow"></a>오류/문제: 검색 결과 내보내기 속도가 느립니다.

보안 및 준수 센터에서 eDiscovery 또는 콘텐츠 검색에서 검색 결과를 내보낼 때 다운로드 시간이 예상보다 오래 소요됩니다.  다운로드할 데이터의 양을 확인하고 내보내기 속도를 늘일 수 있습니다.

### <a name="resolution"></a>해결 방법

1. 보안 & 준수 센터 [PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 연결한 다음 다음 명령을 실행합니다.

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. SearchResults 및 SearchStatistics 매개 변수에서 다운로드할 데이터의 양을 검색합니다.

3. 다음 명령을 실행합니다.

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. 결과 필드에서 내보낼 데이터를 찾고 발생하는 오류를 찾습니다.

5. 콘텐츠를 내보낼 디렉터리에 있는 trace.log 파일에서 오류가 없는지 확인합니다.

6. 그래도 문제가 있는 경우 많은 결과 집합을 더 작은 검색으로 반환하는 검색을 나중을 고려합니다. 예를 들어 검색 쿼리에서 날짜 범위를 사용하여 더 빠르게 다운로드할 수 있는 더 작은 결과 집합을 반환할 수 있습니다.

## <a name="errorissue-internal-server-error-500-occurred"></a>오류/문제: "내부 서버 오류(500)가 발생했습니다."

eDiscovery 검색을 실행하는 경우 "내부 서버 오류(500)가 발생했습니다."와 유사한 오류로 검색이 계속 실패하면 특정 사서함 위치에서만 검색을 다시 실행해야 할 수 있습니다.

![내부 서버 오류 500 스크린샷](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>해결 방법

1. 더 작은 검색으로 검색을 중단하고 검색을 다시 실행합니다.  더 작은 날짜 범위를 사용해 보거나 검색할 위치 수를 제한합니다.

2. 보안 & 준수 센터 [PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 연결한 후 다음 명령을 실행합니다.

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. 출력에서 결과 및 오류를 검사합니다.

4. trace.log 파일을 검사합니다. 검색 결과를 내보낼 때와 동일한 폴더에 있습니다.

5. Microsoft 지원 팀에 문의합니다.

## <a name="errorissue-holds-dont-sync"></a>오류/문제: 보류가 동기화되지 않습니다.

eDiscovery 케이스 보류 정책 동기화 배포 오류입니다. 이 오류는 다음을 읽습니다.

> "리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다. 최종 배포 상태를 업데이트하는 데 2시간이 추가로 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다."

### <a name="resolution"></a>해결 방법

1. 보안 & 준수 센터 [PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 연결한 다음 eDiscovery 사례 보류에 대해 다음 명령을 실행합니다.

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    보존 정책의 경우 다음 명령을 실행합니다.

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. DistributionDetail 매개 변수의 값에서 다음과 같은 오류를 검사합니다.

   > 오류: 리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다. 최종 배포 상태를 업데이트하는 데 2시간이 추가로 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다."

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

eDiscovery 내보내기 도구를 사용하여 검색 결과를 다운로드할 때 다음과 같은 오류가 발생할 수 있습니다. 이는 일반적으로 Azure Storage 위치에서 발생하는 일시적인 `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 오류입니다.

### <a name="resolution"></a>해결 방법

이 문제를 해결하려면 검색 [](export-search-results.md#step-2-download-the-search-results)결과 다운로드를 다시 시도하여 eDiscovery 내보내기 도구를 다시 시작합니다.

## <a name="errorissue-downloaded-export-shows-no-results"></a>오류/문제: 다운로드한 내보내기에서 결과가 표시되지 않습니다.

내보내기에 성공하면 내보내기 도구를 통해 완료된 다운로드에 결과에 파일이 0개 표시됩니다.

### <a name="resolution"></a>해결 방법

이것은 클라이언트 쪽 문제로, 이를 수정하기 위해 다음 단계를 시도하세요.

1. 다른 클라이언트/컴퓨터로 다운로드해 하세요.

2. 로컬 드라이브에 다운로드해야 합니다.

3. 바이러스 스캐너가 실행되고 있지 않은지 확인

4. 다른 내보내기에서 동일한 폴더나 상위 폴더로 다운로드하지 않는지 확인합니다.

5. 이전 단계가 작동하지 않는 경우 압축 해제 및 중복 제거를 사용하지 않도록 설정하십시오.

6. 이 문제가 작동하는 경우 문제가 로컬 바이러스 스캐너 또는 디스크 문제 때문인 것입니다.
