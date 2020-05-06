---
title: 일반적인 eDiscovery 문제 해결
f1.keywords:
- NOCSH
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
description: Office 365 eDiscovery에서 일반적인 문제를 해결 하기 위해 수행할 수 있는 기본적인 문제 해결 단계에 대해 알아봅니다.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8b73e886e9aa639ff5575f10822417411a0784e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035670"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>일반적인 eDiscovery 문제 조사, 문제 해결 및 해결

이 항목에서는 eDiscovery 검색 중에 발생할 수 있는 문제를 파악 하 고 해결 하기 위해 수행할 수 있는 기본적인 문제 해결 단계를 설명 합니다. 이러한 시나리오 중 일부를 해결 하려면 Microsoft 기술 지원 서비스에서 도움을 받아야 합니다. Microsoft 지원 센터에 문의 하는 방법에 대 한 정보는 해결 방법에 포함 되어 있습니다.

## <a name="errorissue-ambiguous-location"></a>오류/문제: 모호한 위치

사용자의 사서함 위치를 검색에 추가 하려고 했지만 EOP (Exchange Online Protection) 디렉터리에 동일한 userID가 있는 개체가 중복 되거나 충돌 하는 경우에는 다음 `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`오류가 발생 합니다. 

### <a name="resolution"></a>문제 해결 방법

동일한 사용자 ID의 중복 된 사용자 또는 메일 그룹을 확인 합니다.

1. [보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)에 연결 합니다.

2. 다음 명령을 실행 하 여 username의 모든 인스턴스를 검색 합니다.

    ```powershell
    Get-Recipient <username>
    ```

   ' Useralias@contoso.com '의 출력은 다음과 유사 합니다.

   > 
   > |이름  |RecipientType  |
   > |---------|---------|
   > |별칭, 사용자     |Enable-mailuser         |
   > |별칭, 사용자     |사용자         |

3. 여러 사용자가 반환 되 면 충돌 하는 개체를 찾아서 수정 합니다.

## <a name="errorissue-search-fails-on-specific-locations"></a>오류/문제: 특정 위치에서 검색 실패

EDiscovery 또는 콘텐츠 검색 시 다음 오류가 발생할 수 있습니다.
>이 검색은 (#) 오류와 함께 완료 되었습니다.  실패 한 위치에서 검색을 다시 시도 하 시겠습니까?

![검색 별 위치 실패 오류 스크린샷](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>문제 해결 방법

이 오류가 표시 되는 경우 검색에 실패 한 위치를 확인 한 다음 실패 한 위치 에서만 검색을 다시 실행 하는 것이 좋습니다.

1. [보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) 에 연결한 후 다음 명령을 실행 합니다.

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. PowerShell 출력의 오류 필드에서 실패 한 위치를 확인 하거나, 오류에 있는 상태 세부 정보를 검색 결과에 표시 합니다.

3. 실패 한 위치 에서만 eDiscovery 검색을 다시 시도 합니다.

4. 계속 해 서 이러한 오류가 표시 되 면 다른 문제 해결 단계에 대 한 [다시 시도 실패 위치](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) 를 참조 하십시오.

## <a name="errorissue-file-not-found"></a>오류/문제: 파일을 찾을 수 없음

SharePoint Online 및 업무용 위치를 포함 하는 eDiscovery 검색을 실행할 때 해당 파일이 사이트에 있더라도 오류가 `File Not Found` 표시 될 수 있습니다. 이 오류는 내보내기 경고 및 오류로 인해 발생 하며 .csv 또는 건너뛴 항목입니다. 이 오류는 사이트에서 파일을 찾을 수 없거나 인덱스가 오래 된 경우에 발생할 수 있습니다. 다음은 실제 오류 (강조 추가 됨)의 텍스트입니다.
  
> 28.06.2019 10:02:19_FailedToExportItem_Failed 콘텐츠를 다운로드 합니다. 추가 진단 정보: ContentDownloadTemporaryFailure: 콘텐츠 6ea52149-91cd-4965-b5bb-82ca6a3ec9be 문서를 다운로드 하지 못했습니다. 상관 관계 Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode:-2147024894---> Microsoft web.config. Servererrorcode: ***파일을 찾을 수 없습니다***. ProcessResponseStream (Stream responseStream)의 Microsoft sharepoint. Clientrequest ()---내부 예외 스택 추적의 끝을---합니다.

### <a name="resolution"></a>문제 해결 방법

1. 검색에서 확인 된 위치를 확인 하 여 파일 위치가 올바르며 검색 위치에 추가 되었는지 확인 합니다.

2. [수동으로 크롤링을 요청 하 고 사이트, 라이브러리 또는 목록을 다시 인덱싱하여 사이트의](https://docs.microsoft.com/sharepoint/crawl-site-content) 인덱스를 해제 하는 절차를 사용 합니다.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>오류/문제: 받는 사람이 발견 되지 않아 검색이 실패 합니다.

EDiscovery 검색이 실패 하 고 `recipient not found`오류가 발생 합니다. 이 오류는 EOP (Exchange Online Protection)에서 개체가 동기화 되지 않아 사용자 개체를 찾을 수 없는 경우에 발생할 수 있습니다.

### <a name="resolution"></a>문제 해결 방법

1. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)에 연결 합니다.

2. 사용자가 Exchange Online Protection과 동기화 되었는지 확인 하려면 다음 명령을 실행 합니다.

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. 사용자 질문에 대 한 메일 사용자 개체가 있어야 합니다. 아무 것도 반환 하지 않으면 사용자 개체를 조사 합니다. 개체를 동기화 할 수 없으면 Microsoft 지원에 문의 하세요.

## <a name="errorissue-exporting-search-results-is-slow"></a>오류/문제: 검색 결과를 내보내는 속도가 느림

보안 및 준수 센터에서 eDiscovery 또는 콘텐츠 검색의 검색 결과를 내보낼 때 다운로드가 예상 보다 오래 걸립니다.  다운로드 해야 하는 데이터의 양을 확인 하 고 내보내기 속도를 높일 수 있습니다.

### <a name="resolution"></a>문제 해결 방법

1.    [다운로드 속도 증가](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)문서에서 식별 된 단계를 사용해 봅니다.

2.    문제가 계속 되 면 [보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) 에 연결 하 고 다음 명령을 실행 합니다.

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. SearchResults 및 Searchresults 매개 변수로 다운로드할 데이터 양을 찾습니다.

5. 다음 명령을 실행합니다.

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. 결과 필드에서 내보낸 데이터를 찾아 발생 한 오류를 확인 합니다.

7. 오류에 대해 콘텐츠를 내보낸 디렉터리에 있는 trace 파일을 확인 합니다.

## <a name="errorissue-internal-server-error-500-occurred"></a>오류/문제: "내부 서버 오류 (500)가 발생 했습니다."

EDiscovery 검색을 실행할 때 "내부 서버 오류 (500)이 발생 했습니다."와 유사한 오류와 함께 검색이 계속 실패 하면 특정 사서함 위치에 대해서만 검색을 다시 실행 해야 할 수 있습니다.

![내부 서버 오류 500 스크린샷](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>문제 해결 방법

1. 검색을 더 작은 검색으로 나누고 검색을 다시 실행 합니다.  더 작은 날짜 범위를 사용 하거나 검색 중인 위치 수를 제한 합니다.

2. [보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) 에 연결한 후 다음 명령을 실행 합니다.

    ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
    Get-ComplianceSearch <searchname> | FL
    ```

3. 결과 및 오류에 대 한 출력을 검사 합니다.

4. 추적 .log 파일을 검사 합니다. 검색 결과를 내보낸 것과 같은 폴더에 있습니다.

5. Microsoft 지원 팀에 문의합니다.

## <a name="errorissue-holds-dont-sync"></a>오류/문제: 보류가 동기화 되지 않음

eDiscovery 사례 보류 정책 동기화 배포 오류입니다. 오류는 다음과 같습니다.

> "리소스: 정책을 배포 하는 데 예상 보다 오래 걸리고 있습니다. 최종 배포 상태를 업데이트 하는 데 2 시간이 더 소요 될 수도 있으므로 몇 시간 후에 다시 확인 하세요. "

### <a name="resolution"></a>문제 해결 방법

1.    [보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) 에 연결한 후 eDiscovery 사례 보류에 대해 다음 명령을 실행 합니다.

    ```powershell
    Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
    ```

    보존 정책에 대해 다음 명령을 실행 합니다.

    ```powershell
    Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
    ```

2. DistributionDetail 매개 변수의 값을 검사 하 여 다음과 같은 오류를 확인 합니다.
 
   > 오류: 리소스: 정책을 배포 하는 데 예상 보다 오래 걸립니다. 최종 배포 상태를 업데이트 하는 데 2 시간이 더 소요 될 수도 있으므로 몇 시간 후에 다시 확인 하세요. " 
   
3. 문제가 있는 정책에서 RetryDistribution 매개 변수를 실행 해 봅니다.
   
    
    EDiscovery 사례 보류의 경우:

    ```powershell
    Set-CaseHoldPolicy <policyname> -RetryDistribution
    ```

    보존 정책:

    ```powershell
    Set-RetentionCompliancePolicy <policyname> -RetryDistribution
    ``` 

4. Microsoft 지원 팀에 문의합니다.

## <a name="see-also"></a>참고 항목

- [콘텐츠 위치 오류를 방지 하기 위한 팁](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
