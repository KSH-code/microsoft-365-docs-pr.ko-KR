---
title: PowerShell 스크립트를 사용하여 감사 로그 검색
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Exchange Online에서 Search-UnifiedAuditLog cmdlet을 실행하여 감사 로그를 검색하는 PowerShell 스크립트를 사용하세요. 이 스크립트는 실행할 때마다 대량 감사 레코드 집합을 반환하도록 최적화되어 있습니다. 이 스크립트는 이러한 레코드를 Excel의 Power Query를 사용하여 보거나 변환할 수 있는 CSV 파일로 내보냅니다.
ms.openlocfilehash: d104ac5bb056d898dd03aaf3765a35950a7ea094
ms.sourcegitcommit: df1ad7118c4a95a310a4f17124322a6ae6ace26f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2021
ms.locfileid: "60268569"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>PowerShell 스크립트를 사용하여 감사 로그 검색

오늘날의 IT 관리자는 보안, 규정 준수 및 감사를 최우선 과제로 꼽았습니다. Microsoft 365에는 조직이 보안, 규정 준수 및 감사를 관리하는 데 도움이 되는 몇 가지 기능이 내장되어 있습니다. 특히 통합 감사 로깅을 사용하면 보안 인시던트 및 규정 준수 문제를 조사할 수 있습니다. 다음 방법을 사용하여 감사 로그를 검색할 수 있습니다.

- [Office 365 관리 작업 API](/office/office-365-management-api/office-365-management-activity-api-reference)

- Microsoft 365 규정 준수 센터의 [ 감사 로그 검색 도구 ](search-the-audit-log-in-security-and-compliance.md)

- Exchange Online PowerShell의 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet

감사 로그를 정기적으로 검색해야 하는 경우 대규모 조직에 지속적으로 수백만 개의 감사 레코드를 검색할 수 있는 확장성과 성능을 제공할 수 있으므로 Office 365 관리 작업 API를 사용하는 솔루션을 고려해야 합니다. Microsoft 365 규정 준수 센터에서 감사 로그 검색 도구를 사용하면 더 짧은 시간 범위에서 발생하는 특정 작업에 대한 감사 레코드를 빠르게 찾을 수 있습니다. 감사 로그 검색 도구(특히 대규모 조직의 경우)에서 더 긴 시간 범위를 사용하면 레코드를 너무 많이 반환하여 쉽게 관리하거나 내보낼 수 없습니다.

특정 조사나 인시던트에 대한 감사 데이터를 수동으로 검색해야 하는 경우, 특히 대규모 조직의 날짜 범위에 대해 감사 데이터를 수동으로 검색해야 하는 경우 **Search-UnifiedAuditLog** cmdlet을 사용하는 것이 가장 좋습니다. 이 게시물에는 (cmdlet을 실행할 때마다) 50,000개의 감사 레코드를 검색한 다음 검토에 도움이 되도록 Excel의 파워 쿼리를 사용하여 형식을 지정할 수 있는 CSV 파일로 내보낼 수 있는 cmdlet을 사용하는 PowerShell 스크립트가 포함되어 있습니다. 또한 이 문서의 스크립트를 사용하면 대규모 감사 로그 검색이 서비스에서 시간 초과될 가능성을 최소화할 수 있습니다.

## <a name="before-you-run-the-script"></a>스크립트를 실행하기 전에

- 감사 기록을 사용하도록 설정해야 조직에서 스크립트를 사용하여 감사 레코드를 반환할 수 있습니다. Microsoft 365 및 Office 365 엔터프라이즈 조직에서는 기본적으로 감사 로그 검색이 켜져 있습니다. 조직에 감사 로그 검색이 켜져 있는지 확인하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  **UnifiedAuditLogIngestionEnabled** 에 대한 `True` 값은 로그 검색이 켜져 있는 것을 나타냅니다.

- 스크립트를 성공적으로 실행하려면 Exchange Online에서 보기 전용 감사 로그 또는 감사 로그 역할이 할당되어야 합니다. 기본적으로 이러한 역할은 Exchange 관리 센터의 사용 권한 페이지에서 규정 준수 관리 및 조직 관리 역할 그룹에 할당됩니다. 자세한 내용은 [규정 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log)의 "감사 로그 검색 요구 사항" 섹션을 참조하십시오.

- 스크립트가 완료되는 데 시간이 오래 걸릴 수 있습니다. 실행하는 데 걸리는 시간은 감사 레코드를 검색할 스크립트를 구성하는 간격의 크기 및 날짜 범위에 따라 달라집니다. 날짜 범위가 크고 간격이 작을수록 실행 시간이 길어집니다. 날짜 범위 및 간격에 대한 자세한 내용은 2단계의 표를 참조하십시오.

- 이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.

## <a name="step-1-connect-to-exchange-online-powershell"></a>1단계: Exchange Online PowerShell에 연결

첫 번째 단계는 Exchange Online PowerShell에 연결하는 것입니다. 최신 인증 또는 MFA(다단계 인증)를 사용하여 연결할 수 있습니다. 단계별 지침은 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>2단계: 감사 레코드를 검색하도록 스크립트를 수정 및 실행

Exchange Online PowerShell에 연결한 후 다음 단계는 스크립트를 생성, 수정 및 실행하여 감사 데이터를 검색하는 것입니다. 감사 로그 검색 스크립트의 처음 7줄에는 검색을 구성하기 위해 수정할 수 있는 다음 변수가 포함됩니다. 이러한 변수에 대한 설명은 2단계의 표를 참조하십시오.

1. 파일 이름 접미사 .ps1을 사용하여 다음 텍스트를 Windows PowerShell 스크립트에 저장합니다. 예를 들어 SearchAuditLog.ps1로 저장합니다.

   ```powershell
   #Modify the values for the following variables to configure the audit log search.
   $logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
   $outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
   [DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
   [DateTime]$end = [DateTime]::UtcNow
   $record = "AzureActiveDirectory"
   $resultSize = 5000
   $intervalMinutes = 60
   
   #Start script
   [DateTime]$currentStart = $start
   [DateTime]$currentEnd = $start
   
   Function Write-LogFile ([String]$Message)
   {
       $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
       $final | Out-File $logFile -Append
   }
   
   Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
   Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"
   
   $totalCount = 0
   while ($true)
   {
       $currentEnd = $currentStart.AddMinutes($intervalMinutes)
       if ($currentEnd -gt $end)
       {
           $currentEnd = $end
       }
   
       if ($currentStart -eq $currentEnd)
       {
           break
       }
   
       $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
       Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       $currentCount = 0
   
       $sw = [Diagnostics.StopWatch]::StartNew()
       do
       {
           $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize
   
           if (($results | Measure-Object).Count -ne 0)
           {
               $results | export-csv -Path $outputFile -Append -NoTypeInformation
   
               $currentTotal = $results[0].ResultCount
               $totalCount += $results.Count
               $currentCount += $results.Count
               Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"
   
               if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
               {
                   $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                   Write-LogFile $message
                   Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                   ""
                   break
               }
           }
       }
       while (($results | Measure-Object).Count -ne 0)
   
       $currentStart = $currentEnd
   }
   
   Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
   Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green
   ```

2. 다음 표에 나열된 변수를 수정하여 검색 기준을 구성합니다. 스크립트에는 이러한 변수에 대한 표본 값이 포함되어 있지만 특정 요구 사항을 충족하도록 이러한 값을 변경해야 합니다.

   <br>

   ****

   |변수|샘플 값|설명|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|스크립트에서 수행한 감사 로그 검색 진행률에 대한 정보를 포함하는 로그 파일의 이름과 위치를 지정합니다. 스크립트는 UTC 타임스탬프를 로그 파일에 기록합니다.|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|스크립트에서 반환한 감사 레코드가 들어 있는 CSV 파일의 이름과 위치를 지정합니다.|
   |`[DateTime]$start` 및 `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|감사 로그 검색의 날짜 범위를 지정합니다. 스크립트는 지정된 날짜 범위 내에서 발생한 감사 활동에 대한 레코드를 반환합니다. 예를 들어 2021년 1월에 수행된 작업을 반환하려면 시작 날짜 `"2021-01-01"`과(와) 종료 날짜 `"2021-01-31"`을(를) 사용할 수 있습니다(이중 따옴표로 묶어야 함). 스크립트의 샘플 값은 이전 24시간 동안 수행된 작업에 대한 레코드를 반환합니다. 값에 타임스탬프를 포함하지 않을 경우 기본 타임스탬프는 지정된 날짜에 오전 12:00(자정)입니다.|
   |`$record`|"AzureActiveDirectory"|검색할 감사 작업의 레코드 유형(*작업* 이라고도 함)을 지정합니다. 이 속성은 활동이 트리거된 서비스 또는 기능을 나타냅니다. 이 변수에 사용할 수 있는 레코드 유형 목록은 [감사 로그 레코드 유형](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)을 참조하십시오. 레코드 유형 이름 또는 ENUM 값을 사용할 수 있습니다. <br/><br/>**팁** 모든 레코드 유형에 대한 감사 레코드를 반환하려면 `$null` 값을 사용하세요(더블 따옴표 없음).|
   |`$resultSize`|5000|**-UnifiedAuditLog** cmdlet을 스크립트(*결과 집합* 이라고 함)에서 호출할 때마다 반환되는 결과 수를 지정합니다. 5,000이라는 값은 cmdlet에서 지원하는 최대값입니다. 이 값은 그대로 두십시오.|
   |`$intervalMinutes`|60|반환되는 5000개 레코드의 한계를 극복하기 위해 이 변수는 지정한 데이터 범위를 가져와 더 작은 시간 간격으로 분할합니다. 이제 전체 날짜 범위가 아닌 각 간격은 명령의 5000 레코드 출력 제한에 따릅니다. 날짜 범위 내의 60분 간격당 5000개 레코드의 기본값은 대부분의 조직에 충분해야 합니다. 그러나 스크립트가 `maximum results limitation reached`이라는 오류를 반환하는 경우 시간 간격(예: 30분 또는 15분)을 줄이고 스크립트를 다시 실행합니다.|
   ||||

   위 표에 나열된 대부분의 변수는 **-UnifiedAuditLog** cmdlet에 대한 매개 변수에 해당합니다. 이러한 매개 변수에 대한 자세한 내용은 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)를 참조하십시오.

3. 로컬 컴퓨터에서 Windows PowerShell을 열고 수정된 스크립트를 저장한 폴더로 이동합니다.

4. Exchange Online PowerShell에서 스크립트를 실행합니다(예:

   ```powershell
   .\SearchAuditLog.ps1
   ```

스크립트가 실행되는 동안 진행 메시지를 표시합니다. 스크립트 실행이 완료되면 감사 레코드가 포함된 로그 파일과 CSV 파일을 생성하여 `$logFile` 및 `$outputFile` 변수로 정의된 폴더에 저장합니다.

> [!IMPORTANT]
> 스크립트에서 cmdlet을 실행할 때마다 반환되는 최대 감사 레코드 수는 50,000개로 제한됩니다. 이 스크립트를 실행하고 50,000개의 결과를 반환하는 경우 날짜 범위 내에 발생한 작업에 대한 감사 레코드가 포함되지 않았을 수 있습니다. 이 경우 날짜 범위를 더 작은 기간으로 나눈 다음 각 날짜 범위에 대해 스크립트를 다시 실행하는 것이 좋습니다. 예를 들어, 90일 간의 날짜 범위가 50,000개의 결과를 반환하는 경우 스크립트를 두 번, 날짜 범위에서 처음 45일 동안 한 번, 이후 45일 동안 다시 실행할 수 있습니다.

## <a name="step-3-format-and-view-the-audit-records"></a>3단계: 감사 기록 포맷 및 보기

스크립트를 실행하고 감사 레코드를 CSV 파일로 내보낸 후에는 감사 레코드를 보다 쉽게 검토하고 분석할 수 있도록 CSV 형식을 지정할 수 있습니다. 이렇게 하는 한 가지 방법은 Excel의 Power Query JSON 변환 기능을 사용하여 **AuditData** 열의 JSON 개체에 있는 각 속성을 고유한 열로 분할하는 것입니다. 단계별 지침을 보려면 [감사 로그 레코드 내보내기, 구성 및 보기](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)의 “2단계: 파워 쿼리 편집기를 사용하여 내보낸 감사 로그의 서식 지정”을 참조하세요.
