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
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Exchange Online에서 Search-UnifiedAuditLog cmdlet을 실행하여 감사 로그를 검색하는 PowerShell 스크립트를 사용하세요. 이 스크립트는 대량 감사 레코드 집합(최대 50,000개)을 반환하는 데 최적화되어 있습니다. 이 스크립트는 이러한 레코드를 Excel의 Power Query를 사용하여 보거나 변환할 수 있는 CSV 파일로 내보냅니다.
ms.openlocfilehash: 3d44054d8d1111fe86e06460f5ca4d442d0d1625
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233332"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="cea2d-105">PowerShell 스크립트를 사용하여 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="cea2d-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="cea2d-106">오늘날의 IT 관리자는 보안, 규정 준수 및 감사를 최우선 과제로 꼽았습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="cea2d-107">Microsoft 365에는 조직이 보안, 규정 준수 및 감사를 관리하는 데 도움이 되는 몇 가지 기능이 내장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="cea2d-108">특히 통합 감사 로깅을 사용하면 보안 인시던트 및 규정 준수 문제를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="cea2d-109">다음 방법을 사용하여 감사 로그를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="cea2d-110">Office 365 관리 작업 API</span><span class="sxs-lookup"><span data-stu-id="cea2d-110">The Office 365 Management Activity API</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="cea2d-111">Microsoft 365 규정 준수 센터의 [ 감사 로그 검색 도구 ](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="cea2d-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="cea2d-112">Exchange Online PowerShell의 [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet</span><span class="sxs-lookup"><span data-stu-id="cea2d-112">The [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="cea2d-113">감사 로그를 정기적으로 검색해야 하는 경우 대규모 조직에 지속적으로 수백만 개의 감사 레코드를 검색할 수 있는 확장성과 성능을 제공할 수 있으므로 Office 365 관리 작업 API를 사용하는 솔루션을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="cea2d-114">Microsoft 365 규정 준수 센터에서 감사 로그 검색 도구를 사용하면 더 짧은 시간 범위에서 발생하는 특정 작업에 대한 감사 레코드를 빠르게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="cea2d-115">감사 로그 검색 도구(특히 대규모 조직의 경우)에서 더 긴 시간 범위를 사용하면 레코드를 너무 많이 반환하여 쉽게 관리하거나 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="cea2d-116">특정 조사나 인시던트에 대한 감사 데이터를 수동으로 검색해야 하는 경우, 특히 대규모 조직의 날짜 범위에 대해 감사 데이터를 수동으로 검색해야 하는 경우 **Search-UnifiedAuditLog** cmdlet을 사용하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="cea2d-117">이 자료에는 cmdlet을 사용하여 최대 50,000개의 감사 레코드를 검색한 다음 검토를 돕기 위해 Excel의 Power Query를 사용하여 포맷할 수 있는 CSV 파일로 내보내는 PowerShell 스크립트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="cea2d-118">또한 이 문서의 스크립트를 사용하면 대규모 감사 로그 검색이 서비스에서 시간 초과될 가능성을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="cea2d-119">스크립트를 실행하기 전에</span><span class="sxs-lookup"><span data-stu-id="cea2d-119">Before you run the script</span></span>

- <span data-ttu-id="cea2d-120">감사 기록을 사용하도록 설정해야 조직에서 스크립트를 사용하여 감사 레코드를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="cea2d-121">Microsoft 365 및 Office 365 엔터프라이즈 조직에서는 기본적으로 감사 로그 검색이 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="cea2d-122">조직에 감사 로그 검색이 켜져 있는지 확인하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```
  
  <span data-ttu-id="cea2d-123">**UnifiedAuditLogIngestionEnabled** 에 대한 `True` 값은 로그 검색이 켜져 있는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="cea2d-124">스크립트를 성공적으로 실행하려면 Exchange Online에서 보기 전용 감사 로그 또는 감사 로그 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="cea2d-125">기본적으로 이러한 역할은 Exchange 관리 센터의 사용 권한 페이지에서 규정 준수 관리 및 조직 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="cea2d-126">자세한 내용은 [규정 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log)의 "감사 로그 검색 요구 사항" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cea2d-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span>

- <span data-ttu-id="cea2d-127">스크립트가 완료되는 데 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="cea2d-128">실행하는 데 걸리는 시간은 감사 레코드를 검색할 스크립트를 구성하는 간격의 크기 및 날짜 범위에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="cea2d-129">날짜 범위가 크고 간격이 작을수록 실행 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="cea2d-130">날짜 범위 및 간격에 대한 자세한 내용은 2단계의 표를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cea2d-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="cea2d-131">이 문서에 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-131">The sample script provided in this article isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="cea2d-132">샘플 스크립트는 어떤 종류의 보증도 없이 그대로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-132">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="cea2d-133">또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-133">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="cea2d-134">샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-134">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="cea2d-135">어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-135">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="cea2d-136">1단계: Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="cea2d-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="cea2d-137">첫 번째 단계는 Exchange Online PowerShell에 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="cea2d-138">최신 인증 또는 MFA(다단계 인증)를 사용하여 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="cea2d-139">단계별 지침은 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cea2d-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="cea2d-140">2단계: 감사 레코드를 검색하도록 스크립트를 수정 및 실행</span><span class="sxs-lookup"><span data-stu-id="cea2d-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="cea2d-141">Exchange Online PowerShell에 연결한 후 다음 단계는 스크립트를 생성, 수정 및 실행하여 감사 데이터를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="cea2d-142">감사 로그 검색 스크립트의 처음 7줄에는 검색을 구성하기 위해 수정할 수 있는 다음 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="cea2d-143">이러한 변수에 대한 설명은 2단계의 표를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cea2d-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="cea2d-144">.ps1의 파일 이름 접미사를 사용하여 다음 텍스트를 Windows PowerShell 스크립트에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-144">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1.</span></span> <span data-ttu-id="cea2d-145">예를 들어 SearchAuditLog.ps1이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-145">For example, SearchAuditLog.ps1.</span></span>

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

2. <span data-ttu-id="cea2d-146">다음 표에 나열된 변수를 수정하여 검색 기준을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="cea2d-147">스크립트에는 이러한 변수에 대한 표본 값이 포함되어 있지만 특정 요구 사항을 충족하도록 이러한 값을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   |<span data-ttu-id="cea2d-148">변수</span><span class="sxs-lookup"><span data-stu-id="cea2d-148">Variable</span></span>|<span data-ttu-id="cea2d-149">샘플 값</span><span class="sxs-lookup"><span data-stu-id="cea2d-149">Sample value</span></span>|<span data-ttu-id="cea2d-150">설명</span><span class="sxs-lookup"><span data-stu-id="cea2d-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="cea2d-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="cea2d-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="cea2d-152">스크립트에서 수행한 감사 로그 검색 진행률에 대한 정보를 포함하는 로그 파일의 이름과 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-152">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script.</span></span> <span data-ttu-id="cea2d-153">스크립트에서 로그 파일에 UTC 타임스탬프를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-153">The script writes UTC timestamps to the log file.</span></span>|
   |`$outputFile`|<span data-ttu-id="cea2d-154">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="cea2d-154">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="cea2d-155">스크립트에서 반환한 감사 레코드가 들어 있는 CSV 파일의 이름과 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-155">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="cea2d-156">`[DateTime]$start` 및 `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="cea2d-156">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="cea2d-159">감사 로그 검색의 날짜 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-159">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="cea2d-160">스크립트는 지정된 날짜 범위 내에서 발생한 감사 활동에 대한 레코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-160">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="cea2d-161">예를 들어 2021년 1월에 수행된 작업을 반환하려면 시작 날짜 `"2021-01-01"`과(와) 종료 날짜 `"2021-01-31"`을(를) 사용할 수 있습니다(이중 따옴표로 묶어야 함). 스크립트의 샘플 값은 이전 24시간 동안 수행된 작업에 대한 레코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-161">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="cea2d-162">값에 타임스탬프를 포함하지 않을 경우 기본 타임스탬프는 지정된 날짜에 오전 12:00(자정)입니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-162">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="cea2d-163">"AzureActiveDirectory"</span><span class="sxs-lookup"><span data-stu-id="cea2d-163">"AzureActiveDirectory"</span></span>|<span data-ttu-id="cea2d-164">검색할 감사 작업의 레코드 유형(*작업* 이라고도 함)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-164">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="cea2d-165">이 속성은 활동이 트리거된 서비스 또는 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-165">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="cea2d-166">이 변수에 사용할 수 있는 레코드 유형 목록은 [감사 로그 레코드 유형](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cea2d-166">For a list of record types that you can use for this variable, see [Audit log record type](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="cea2d-167">레코드 유형 이름 또는 ENUM 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-167">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="cea2d-168">**팁** 모든 레코드 유형에 대한 감사 레코드를 반환하려면 `$null` 값을 사용하세요(더블 따옴표 없음).</span><span class="sxs-lookup"><span data-stu-id="cea2d-168">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="cea2d-169">5000</span><span class="sxs-lookup"><span data-stu-id="cea2d-169">5000</span></span>|<span data-ttu-id="cea2d-170">**-UnifiedAuditLog** cmdlet을 스크립트(*결과 집합* 이라고 함)에서 호출할 때마다 반환되는 결과 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-170">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="cea2d-171">5,000이라는 값은 cmdlet에서 지원하는 최대값입니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-171">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="cea2d-172">이 값은 그대로 두십시오.</span><span class="sxs-lookup"><span data-stu-id="cea2d-172">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="cea2d-173">60</span><span class="sxs-lookup"><span data-stu-id="cea2d-173">60</span></span>|<span data-ttu-id="cea2d-174">반환되는 5000개 레코드의 한계를 극복하기 위해 이 변수는 지정한 데이터 범위를 가져와 더 작은 시간 간격으로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-174">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="cea2d-175">이제 전체 날짜 범위가 아닌 각 간격은 명령의 5000 레코드 출력 제한에 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-175">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="cea2d-176">날짜 범위 내의 60분 간격당 5000개 레코드의 기본값은 대부분의 조직에 충분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-176">The default value of 5000 records per 60-minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="cea2d-177">그러나 스크립트가 `maximum results limitation reached`이라는 오류를 반환하는 경우 시간 간격(예: 30분 또는 15분)을 줄이고 스크립트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-177">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="cea2d-178">위 표에 나열된 대부분의 변수는 **-UnifiedAuditLog** cmdlet에 대한 매개 변수에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-178">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="cea2d-179">이러한 매개 변수에 대한 자세한 내용은 [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cea2d-179">For more information about these parameters, see [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="cea2d-180">로컬 컴퓨터에서 Windows PowerShell을 열고 수정된 스크립트를 저장한 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-180">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="cea2d-181">Exchange Online PowerShell에서 스크립트를 실행합니다(예:</span><span class="sxs-lookup"><span data-stu-id="cea2d-181">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="cea2d-182">스크립트는 실행 중 진행률 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-182">The script displays progress messages while it's running.</span></span> <span data-ttu-id="cea2d-183">스크립트 실행이 완료되면 감사 레코드가 포함된 로그 파일과 CSV 파일을 생성하여 `$logFile` 및 `$outputFile` 변수로 정의된 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-183">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cea2d-184">이 스크립트를 실행할 때마다 반환되는 최대 감사 레코드 수에는 50,000개의 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-184">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="cea2d-185">이 스크립트를 실행하고 50,000개의 결과를 반환하는 경우 날짜 범위 내에 발생한 작업에 대한 감사 레코드가 포함되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-185">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="cea2d-186">이 경우 날짜 범위를 더 작은 기간으로 나눈 다음 각 날짜 범위에 대해 스크립트를 다시 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-186">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="cea2d-187">예를 들어, 90일 간의 날짜 범위가 50,000개의 결과를 반환하는 경우 스크립트를 두 번, 날짜 범위에서 처음 45일 동안 한 번, 이후 45일 동안 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-187">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="cea2d-188">3단계: 감사 기록 포맷 및 보기</span><span class="sxs-lookup"><span data-stu-id="cea2d-188">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="cea2d-189">스크립트를 실행하고 감사 레코드를 CSV 파일로 내보낸 후에는 감사 레코드를 보다 쉽게 검토하고 분석할 수 있도록 CSV 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-189">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="cea2d-190">이렇게 하는 한 가지 방법은 Excel의 Power Query JSON 변환 기능을 사용하여 **AuditData** 열의 JSON 개체에 있는 각 속성을 고유한 열로 분할하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cea2d-190">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="cea2d-191">단계별 지침을 보려면 [감사 로그 레코드 내보내기, 구성 및 보기](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)의 “2단계: 파워 쿼리 편집기를 사용하여 내보낸 감사 로그의 서식 지정”을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cea2d-191">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>
