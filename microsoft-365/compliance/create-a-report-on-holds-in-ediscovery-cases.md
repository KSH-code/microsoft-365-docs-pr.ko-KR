---
title: EDiscovery 사례의 보존 보고서 만들기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: eDiscovery 사례와 연결된 모든 보류에 대한 정보가 포함된 보고서를 생성하는 방법을 학습합니다.
ms.openlocfilehash: 04282f6f2481d892fa16d685936efeec55feae77
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908412"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="24363-103">EDiscovery 사례의 보존 보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="24363-103">Create a report on holds in eDiscovery cases</span></span>

<span data-ttu-id="24363-104">이 문서의 스크립트를 통해 eDiscovery 관리자 및 eDiscovery 관리자는 Office 365 또는 조직의 준수 센터에서 eDiscovery 사례와 연결된 모든 보류에 대한 정보가 포함된 보고서를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24363-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="24363-105">보고서에는 보류가 연결된 사례의 이름, 보류된 콘텐츠 위치, 보류가 쿼리 기반인지 여부 등의 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24363-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="24363-106">보류가 없는 사례가 있는 경우 스크립트는 보류가 없는 사례 목록을 사용하여 추가 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="24363-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="24363-107">보고서에 [포함된 정보에](#more-information) 대한 자세한 내용은 추가 정보 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24363-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>

## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="24363-108">관리자 요구 사항 및 스크립트 정보</span><span class="sxs-lookup"><span data-stu-id="24363-108">Admin requirements and script information</span></span>

- <span data-ttu-id="24363-109">조직의 모든 eDiscovery 사례에 대한 보고서를 생성하기 위해 조직의 eDiscovery 관리자(Administrator)를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24363-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="24363-110">eDiscovery 관리자인 경우 보고서에는 액세스할 수 있는 사례에 대한 정보만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="24363-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="24363-111">eDiscovery 사용 권한에 대한 자세한 내용은 [eDiscovery](assign-ediscovery-permissions.md)사용 권한 할당을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24363-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="24363-112">이 문서의 스크립트에는 최소한의 오류 처리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24363-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="24363-113">기본 목적은 조직의 eDiscovery 사례와 연결된 보류에 대한 보고서를 빠르게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>

- <span data-ttu-id="24363-p104">이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="24363-119">1단계: 커넥트 준수 센터 PowerShell에 & 관리</span><span class="sxs-lookup"><span data-stu-id="24363-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="24363-120">첫 번째 단계에서는 조직의 보안 및 준수 센터 PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="24363-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="24363-121">단계별 지침은 [보안 및 준수 센터 PowerShell에 연결하기](/powershell/exchange/connect-to-scc-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24363-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="24363-122">2단계: 스크립트를 실행하여 eDiscovery 사례와 관련된 보류 보고</span><span class="sxs-lookup"><span data-stu-id="24363-122">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="24363-123">Security & Compliance Center PowerShell에 연결한 후 다음 단계는 조직의 eDiscovery 사례에 대한 정보를 수집하는 스크립트를 만들고 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-123">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span>

1. <span data-ttu-id="24363-124">파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들어 CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="24363-124">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span>

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "***********************************************"
   " "
   #prompt users to specify a path to store the output files
   $time=get-date
   $Path = Read-Host 'Enter a file path to save the report to a .csv file'
   $outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   $noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   #add case details to the csv file
   function add-tocasereport{
   Param([string]$casename,
   [String]$casestatus,
   [datetime]$casecreatedtime,
   [string]$casemembers,
   [datetime]$caseClosedDateTime,
   [string]$caseclosedby,
   [string]$holdname,
   [String]$Holdenabled,
   [string]$holdcreatedby,
   [string]$holdlastmodifiedby,
   [string]$ExchangeLocation,
   [string]$sharePointlocation,
   [string]$ContentMatchQuery,
   [datetime]$holdcreatedtime,
   [datetime]$holdchangedtime
   )
   $addRow = New-Object PSObject
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
   $allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
   $allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of cases and holds..."
   " "
   $edc =Get-ComplianceCase -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }

   " "
   Write-host "Script complete! Report files saved to this folder: '$Path'"
   " "
   #script end
   ```

2. <span data-ttu-id="24363-125">1단계에서 Windows PowerShell 세션에서 스크립트를 저장한 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="24363-125">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="24363-126">스크립트를 실행합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="24363-126">Run the script; for example:</span></span>

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   <span data-ttu-id="24363-127">스크립트에서 보고서를 저장할 대상 폴더를 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="24363-127">The script will prompt for a target folder to save the report to.</span></span>

4. <span data-ttu-id="24363-128">보고서를 저장할 폴더의 전체 경로 이름을 입력한 다음 **Enter를 누를 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="24363-128">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>

   > [!TIP]
   > <span data-ttu-id="24363-129">스크립트가 있는 폴더와 동일한 폴더에 보고서를 저장하기 위해 대상 폴더에 대한 메시지가 표시될 때 마침표(".")를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="24363-129">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="24363-130">스크립트가 있는 폴더의 하위 폴더에 보고서를 저장하기 위해 하위 폴더의 이름을 입력하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24363-130">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span>

   <span data-ttu-id="24363-131">스크립트는 조직의 모든 eDiscovery 사례에 대한 정보를 수집하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="24363-131">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="24363-132">스크립트가 실행되는 동안에는 보고서 파일에 액세스하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24363-132">Don't access the report file while the script is running.</span></span> <span data-ttu-id="24363-133">스크립트가 완료되면 스크립트 세션에 확인 Windows PowerShell 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="24363-133">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="24363-134">이 메시지가 표시되면 4단계에서 지정한 폴더의 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24363-134">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="24363-135">보고서의 파일 이름은 `CaseHoldsReport<DateTimeStamp>.csv` 입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-135">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="24363-136">또한 스크립트는 보류가 없는 사례 목록이 있는 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="24363-136">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="24363-137">이 보고서의 파일 이름은 `CaseswithNoHolds<DateTimeStamp>.csv` 입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-137">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="24363-138">다음은 CaseHoldsReport.ps1 실행의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-138">Here's an example of running the CaseHoldsReport.ps1 script.</span></span>

   ![스크립트를 실행한 CaseHoldsReport.ps1 출력](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a><span data-ttu-id="24363-140">추가 정보</span><span class="sxs-lookup"><span data-stu-id="24363-140">More information</span></span>

<span data-ttu-id="24363-141">이 문서의 스크립트를 실행할 때 만들어진 사례 보류 보고서에는 각 보류에 대한 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24363-141">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="24363-142">앞서 설명한처럼 조직의 모든 보류에 대한 정보를 반환하기 위해 eDiscovery 관리자(Administrator)를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24363-142">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="24363-143">케이스 보류에 대한 자세한 내용은 [eDiscovery 사례를 참조하세요.](./get-started-core-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="24363-143">For more information about case holds, see [eDiscovery cases](./get-started-core-ediscovery.md).</span></span>

- <span data-ttu-id="24363-144">보류의 이름과 보류가 연결된 eDiscovery 사례의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-144">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>

- <span data-ttu-id="24363-145">eDiscovery 사례가 활성 상태인지 닫혀 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-145">Whether or not the eDiscovery case is active or closed.</span></span>

- <span data-ttu-id="24363-146">보류를 사용할지 또는 사용하지 않도록 설정할지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-146">Whether or not the hold is enabled or disabled.</span></span>

- <span data-ttu-id="24363-147">보류가 연결된 eDiscovery 사례의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-147">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="24363-148">사례 구성원은 할당된 eDiscovery 사용 권한에 따라 사례를 보거나 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24363-148">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>

- <span data-ttu-id="24363-149">사례를 만든 시간 및 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-149">The time and date the case was created.</span></span>

- <span data-ttu-id="24363-150">사례가 닫히면 사례를 닫은 사람 및 종료한 시간 및 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-150">If a case is closed, the person who closed it and the time and date it was closed.</span></span>

- <span data-ttu-id="24363-151">사서함 Exchange 보류 SharePoint 사이트 위치를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="24363-151">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>

- <span data-ttu-id="24363-152">보류가 쿼리 기반이면 쿼리 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-152">If the hold is query-based, the query syntax.</span></span>

- <span data-ttu-id="24363-153">보류를 만든 시간 및 날짜 및 보류를 만든 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-153">The time and date the hold was created and the person who created it.</span></span>

- <span data-ttu-id="24363-154">보류가 마지막으로 변경된 시간 및 날짜 및 변경한 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="24363-154">The time and date the hold was last changed and the person who changed it.</span></span>