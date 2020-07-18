---
title: PowerShell을 사용하여 보존 레이블 만들기 및 게시
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: PowerShell을 사용하여 Microsoft 365 준수 센터와 별개로 명령줄에서 보존 레이블을 만들고 게시하는 방법을 알아봅니다.
ms.openlocfilehash: 416746bb849020d76bcf950d397768239d17baf1
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126369"
---
# <a name="create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="63702-103">PowerShell을 사용하여 보존 레이블 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="63702-103">Create and publish retention labels by using PowerShell</span></span>

><span data-ttu-id="63702-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="63702-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="63702-105">Microsoft 365에서 문서 및 전자 메일을 유지하거나 삭제하게 해주는 [보존 레이블](retention.md)을 사용하기로 결정한 후에 최대 수백 개에 이르는 여러 개의 보존 레이블을 만들고 게시할 수 있음을 깨달았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-105">After you've decided to use [retention labels](retention.md) to help you keep or delete documents and emails in Microsoft 365, you might have realized that you have many and possibly hundreds of retention labels to create and publish.</span></span> <span data-ttu-id="63702-106">대량으로 보존 레이블을 만드는 권장 방법은 Microsoft 365 준수 센터에서 [파일 계획](file-plan-manager.md)을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="63702-106">The recommended method to create retention labels at scale is by using [file plan](file-plan-manager.md) from the Microsoft 365 compliance center.</span></span> <span data-ttu-id="63702-107">그렇지만 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels)을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-107">However, you can also use [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels).</span></span>
  
<span data-ttu-id="63702-108">보존 레이블을 일괄적으로 만들어 보존 레이블 정책의 형태로 게시할 수 있도록 이 문서의 정보, 서식 파일과 예제, 스크립트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-108">Use the information, template files and examples, and script in this article to help you bulk-create retention labels and publish them in retention label policies.</span></span> <span data-ttu-id="63702-109">그런 다음 [관리자 및 사용자가 보존 레이블을 적용](create-apply-retention-labels.md#how-to-apply-published-retention-labels)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-109">Then, the retention labels can be [applied by administrators and users](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span></span>

<span data-ttu-id="63702-110">제공된 지침은 자동 적용된 보존 레이블과는 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-110">The supplied instructions don't support retention labels that are auto-applied.</span></span>

<span data-ttu-id="63702-111">개요:</span><span class="sxs-lookup"><span data-stu-id="63702-111">Overview:</span></span> 

1. <span data-ttu-id="63702-112">Excel에서 보존 레이블의 목록과 보존 레이블 정책의 목록을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-112">In Excel, create a list of your retention labels and a list of their retention label policies.</span></span>

2. <span data-ttu-id="63702-113">PowerShell을 사용하여 해당 목록에 있는 보존 레이블과 보존 레이블 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63702-113">Use PowerShell to create the retention labels and retention label policies in those lists.</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="63702-114">고지 사항</span><span class="sxs-lookup"><span data-stu-id="63702-114">Disclaimer</span></span>

<span data-ttu-id="63702-115">이 문서에 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-115">The sample scripts provided in this article aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="63702-116">샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="63702-116">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="63702-117">또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-117">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="63702-118">샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="63702-118">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="63702-119">어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="63702-119">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-the-retention-labels"></a><span data-ttu-id="63702-120">1단계: 보존 레이블에 대한 .csv 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="63702-120">Step 1: Create a .csv file for the retention labels</span></span>

1. <span data-ttu-id="63702-121">서식 파일에 대한 아래의 샘플 .csv 파일 및 서로 다른 네 개의 보존 레이블에 대한 예제 항목을 복사하여 Excel에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-121">Copy the following sample .csv file for a template and example entries for four different retention labels, and paste them into Excel.</span></span> 

2. <span data-ttu-id="63702-122">텍스트를 열로 변환: **데이터** 탭 \> **텍스트를 열로 구분** \> **구분** \> **쉼표** \> **일반**</span><span class="sxs-lookup"><span data-stu-id="63702-122">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="63702-123">예제를 사용자가 직접 작성한 보존 레이블 및 설정 항목으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-123">Replace the examples with entries for your own retention labels and settings.</span></span> <span data-ttu-id="63702-124">매개 변수 값에 대한 자세한 내용은 [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63702-124">For more information about the parameter values, see [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span></span>

3. <span data-ttu-id="63702-125">워크시트를 이후의 단계에서 쉽게 찾을 수 있는 위치에 .csv 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-125">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="63702-126">예: C:\>Scripts\Labels.csv</span><span class="sxs-lookup"><span data-stu-id="63702-126">For example: C:\>Scripts\Labels.csv</span></span>

  
<span data-ttu-id="63702-127">참고:</span><span class="sxs-lookup"><span data-stu-id="63702-127">Notes:</span></span>

- <span data-ttu-id="63702-p106">이미 존재하는 보존 레이블과 동일한 이름을 가진 보존 레이블이 .csv 파일에 있을 경우 스크립트에서 해당 보존 레이블 생성을 건너뜁니다. 중복 보존 레이블은 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-p106">If the .csv file contains a retention label with the same name as one that already exists, the script skips creating that retention label. No duplicate retention labels are created.</span></span>
    
- <span data-ttu-id="63702-130">제공된 샘플 .csv 파일에서 열 머리글을 변경하거나 이름을 바꾸지 마세요. 바꿀 경우 스크립트에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-130">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-labels"></a><span data-ttu-id="63702-131">보존 레이블에 대한 샘플 .csv 파일</span><span class="sxs-lookup"><span data-stu-id="63702-131">Sample .csv file for retention labels</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-the-retention-label-policies"></a><span data-ttu-id="63702-132">2단계: 보존 레이블 정책에 대한 .csv 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="63702-132">Step 2: Create a .csv file for the retention label policies</span></span>

1. <span data-ttu-id="63702-133">서식 파일에 대한 아래의 샘플 .csv 파일 및 서로 다른 세 개의 보존 레이블 정책에 대한 예제 항목을 복사하여 Excel에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-133">Copy the following sample .csv file for a template and example entries for three different retention label policies, and paste them into Excel.</span></span> 

2. <span data-ttu-id="63702-134">텍스트를 열로 변환: **데이터** 탭 \> **텍스트를 열로 구분** \> **구분** \> **쉼표** \> **일반**</span><span class="sxs-lookup"><span data-stu-id="63702-134">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="63702-135">예제를 사용자가 직접 작성한 보존 레이블 정책 및 그 설정에 대한 입력으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-135">Replace the examples with entries for your own retention label policies and their settings.</span></span> <span data-ttu-id="63702-136">이 cmdlet의 매개 변수 값에 대한 자세한 내용은 [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63702-136">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy).</span></span>

3. <span data-ttu-id="63702-137">워크시트를 이후의 단계에서 쉽게 찾을 수 있는 위치에 .csv 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-137">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="63702-138">예: `<path>Policies.csv`</span><span class="sxs-lookup"><span data-stu-id="63702-138">For example: `<path>Policies.csv`</span></span>


<span data-ttu-id="63702-139">참고:</span><span class="sxs-lookup"><span data-stu-id="63702-139">Notes:</span></span>
  
- <span data-ttu-id="63702-p109">이미 존재하는 보존 레이블 정책과 동일한 이름을 가진 보존 레이블 정책이 .csv 파일에 있을 경우 스크립트에서 해당 보존 레이블 정책 생성을 건너뜁니다. 중복 보존 레이블 정책은 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-p109">If the .csv file contains a retention label policy with the same name as one that already exists, the script skips creating that retention label policy. No duplicate retention label policies are created.</span></span>
    
- <span data-ttu-id="63702-142">제공된 샘플 .csv 파일에서 열 머리글을 변경하거나 이름을 바꾸지 마세요. 바꿀 경우 스크립트에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-142">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-policies"></a><span data-ttu-id="63702-143">보존 정책에 대한 샘플 .csv 파일</span><span class="sxs-lookup"><span data-stu-id="63702-143">Sample .csv file for retention policies</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="63702-144">3단계: PowerShell 스크립트 만들기</span><span class="sxs-lookup"><span data-stu-id="63702-144">Step 3: Create the PowerShell script</span></span>

1. <span data-ttu-id="63702-145">다음 PowerShell 스크립트를 복사하여 메모장에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="63702-145">Copy and paste the following PowerShell script into Notepad.</span></span>

2. <span data-ttu-id="63702-146">쉽게 찾을 수 있는 위치에 **.ps1**이라는 파일 이름 확장명을 사용하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-146">Save the file by using a file name extension of **.ps1** in a location that's easy to find.</span></span> <span data-ttu-id="63702-147">예: `<path>CreateRetentionSchedule.ps1`</span><span class="sxs-lookup"><span data-stu-id="63702-147">For example: `<path>CreateRetentionSchedule.ps1`</span></span>

<span data-ttu-id="63702-148">참고:</span><span class="sxs-lookup"><span data-stu-id="63702-148">Notes:</span></span>

- <span data-ttu-id="63702-149">스크립트에 이전의 두 단계에서 만든 두 개의 원본 파일을 제공하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63702-149">The script prompts you to provide the two source files that you created in the previous two steps:</span></span>
    - <span data-ttu-id="63702-150">보존 레이블을 만들 원본 파일을 지정하지 않으면 스크립트가 보존 레이블 정책 만들기로 넘어갑니다.</span><span class="sxs-lookup"><span data-stu-id="63702-150">If you don't specify the source file to create the retention labels, the script moves on to create the retention label policies.</span></span> 
    - <span data-ttu-id="63702-151">보존 레이블 정책을 만들 원본 파일을 지정하지 않으면 스크립트에서 보존 레이블만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="63702-151">If you don't specify the source file to create the retention label policies, the script creates the retention labels only.</span></span>

- <span data-ttu-id="63702-152">스크립트를 실행하면 수행한 각 작업과 작업 성공 또는 실패 여부를 기록하는 로그 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="63702-152">The script generates a log file that records each action it took and whether the action succeeded or failed.</span></span> <span data-ttu-id="63702-153">이 로그 파일을 찾는 방법에 대한 지침은 최종 단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63702-153">See the final step for instructions how to locate this log file.</span></span>

### <a name="powershell-script"></a><span data-ttu-id="63702-154">PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="63702-154">PowerShell script</span></span>

```Powershell
<#
. Steps: Import and publish retention labels
    ○ Load retention labels csv file 
    ○ Validate csv file input
    ○ Create retention labels
    ○ Create retention policies
    ○ Publish retention labels for the policies
    ○ Generate the log for retention labels and policies creation
    ○ Generate the csv result for the labels and policies created
. Syntax
    .\Publish-ComplianceTag.ps1 [-LabelListCSV <string>] [-PolicyListCSV <string>] 
. Detailed Description
    1) [-LabelListCSV <string>]
    -LabelListCSV ".\SampleInputFile_LabelList.csv"
    Load compliance tag for creation.
    2) [-PolicyListCSV <string>]
    -PolicyListCSV ".\SampleInputFile_PolicyList.csv"
    Load compliance tag for creation.
#>
param (
    [Parameter(Mandatory = $true)]
    [string]$LabelListCSV = "",
    [Parameter(Mandatory = $true)]
    [string]$PolicyListCSV = "",
    [Switch]$ResultCSV
)
# -------------------
# File operation
# -------------------
Function FileExist
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath,
        [Switch]$Warning
    )
    $inputFileExist = Test-Path $FilePath
    if (!$inputFileExist)
    {
        if ($Warning -eq $false) 
        { 
            WriteToLog -Type "Failed" -Message "[File: $FilePath] The file doesn't exist"
            throw 
        }
        else 
        { 
            WriteToLog -Type "Warning" -Message "[File: $FilePath] The file doesn't exist"
        }
    }
    else
    {
        WriteToLog -Type "Succeed" -Message "[File: $FilePath] The file is found"
    }
}
# -------------------
# Log operation
# -------------------
Function WriteToLog
{
    Param(
        # Message want to write to log file
        [Parameter(Mandatory = $true)]
        [String]$Message,
        # "Succeed" or "Faild"
        [String]$Type = "Message"
    )
    $date = Get-Date -Format 'HH:mm:ss'
    $logInfo = $date + " - [$Type] " + $Message
    $logInfo | Out-File -FilePath $logfilePath -Append
    if ($Type -eq "Succeed") { Write-Host $logInfo -ForegroundColor Green }
    elseif ($Type -eq "Failed") { Write-Host $logInfo -ForegroundColor Red }
    elseif ($Type -eq "Warning") { Write-Host $logInfo -ForegroundColor Yellow }
    elseif ($Type -eq "Start") { Write-Host $logInfo -ForegroundColor Cyan }
    else { Write-Verbose $logInfo }
}
Function Create-Log
{
    Param(
        # Log folder Root
        [Parameter(Mandatory = $true)]
        [String]$LogFolderRoot,
        # The function Log file for
        [Parameter(Mandatory = $true)]
        [String]$LogFunction
    )
    $logFolderPath = "$LogFolderRoot\logfiles"
    $folderExist = Test-Path "$logFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$logFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $logfilePath = "$logFolderPath\Log_{0}_{1}.txt" -f $LogFunction, $date
    Write-Verbose "Log file is written to: $logfilePath"
    $logfile = New-Item $logfilePath  -type file
    return $logfilePath
}
Function Create-ResultCSV
{
    Param(
        # Result folder Root
        [Parameter(Mandatory = $true)]
        [String]$ResultFolderRoot,
        # The function Result file for
        [Parameter(Mandatory = $true)]
        [String]$ResultFunction
    )
    $retFolderPath = "$ResultFolderRoot\logfiles"
    $folderExist = Test-Path "$retFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$retFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $retfilePath = "$retFolderPath\Result_{0}_{1}.csv" -f $ResultFunction, $date
    Write-Verbose "Result file is written to: $retfilePath"
    $retfile = New-Item $retfilePath  -type file
    return $retfilePath
}
# -------------------
# Prepare Log File
# -------------------
$scriptPath = '.\'
$logfilePath = Create-Log -LogFolderRoot $scriptPath -LogFunction "Publish_Compliance_Tag"
if ($ResultCSV)
{
    $tagRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Creation"
    $tagPubRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Publish"
}
# -------------------
# Invoke Powershell cmdlet
# -------------------
Function InvokePowerShellCmdlet
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$CmdLet
    )
    try
    {
        WriteToLog -Type "Start" -Message "Execute Cmdlet : '$CmdLet'" 
        return Invoke-Expression $CmdLet -ErrorAction SilentlyContinue
    }
    catch
    {
        WriteToLog -Type "Failed" "Failed to execute cmdlet!"
        WriteToLog -Type "Failed" $error[0]
        return $null
    }
}
# -------------------
# Create Compliance Tag
# -------------------
Function CreateComplianceTag
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to create Compliance Tag"
    FileExist $FilePath
    
    # TODO Validate CSV file for the Header
    try
    {
        # Import csv
        $labels = Import-Csv $FilePath
        # Retrieve existing compliance tags
        $tags = InvokePowerShellCmdlet "Get-ComplianceTag"
        foreach($lab in $labels)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $cmdlet = 'New-ComplianceTag'
            if ([String]::IsNullOrEmpty($lab.'Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $name = $lab.'Name (Required)'
                $cmdlet += " -Name '" + $name + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'Comment (Optional)'))
            {
                $para = $lab.'Comment (Optional)'
                $cmdlet += " -Comment '" + $para + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'IsRecordLabel (Required)'))
            {
                $para = $lab.'IsRecordLabel (Required)'
                $cmdlet += " -IsRecordLabel " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionAction (Optional)'))
            {
                $para = $lab.'RetentionAction (Optional)'
                $cmdlet += " -RetentionAction " + $para 
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionDuration (Optional)'))
            {
                $para = $lab.'RetentionDuration (Optional)'
                $cmdlet += " -RetentionDuration " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionType (Optional)'))
            {
                $para = $lab.'RetentionType (Optional)'
                $cmdlet += " -RetentionType " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'ReviewerEmail (Optional)'))
            {
                $emails = $lab.'ReviewerEmail (Optional)'.Split(",") | ForEach-Object { $_.Trim() }
                if (($emails -ne $null) -and ($emails.Count -ne 0))
                {
                    $eml = '@('
                    foreach($email in $emails)
                    {
                        $eml += "'{0}'," -f $email
                    }
                    $eml = $eml.Substring(0, $eml.Length - 1) + ')'
                    
                    $cmdlet += " -ReviewerEmail " + $eml
                }
            }
            # If the tag already exists, skip for creation
            if (($tags -eq $null) -or ($tags | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create compliance tag
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
                
                $ret = InvokePowerShellCmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The tag '$name' already exists! Skip for creation!"
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Create Retention Compliance Policy
# -------------------
Function CreateRetentionCompliancePolicy
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to Create Retention Policy"
    FileExist $FilePath
    try
    {
        # Import csv
        $list = Import-Csv -Path $FilePath
        # Retrieve existing retention compliance policy
        $policies = InvokePowerShellCmdlet "Get-RetentionCompliancePolicy"
        foreach($rp in $list)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $rpid = [String]::Empty;
            $cmdlet = 'New-RetentionCompliancePolicy'
            if ([String]::IsNullOrEmpty($rp.'Policy Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
               $name = $rp.'Policy Name (Required)'
               $cmdlet += " -Name '" + $name + "'"
            }
            if ([String]::IsNullOrEmpty($rp.'Enabled (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $enabled = $rp.'Enabled (Required)'
                $cmdlet += " -Enabled " + $enabled
            }
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocation (Optional)'))
            {
                $para = $rp.'ExchangeLocation (Optional)'
                $cmdlet += " -ExchangeLocation " + $para
            }
         
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocationException (Optional)'))
            {
                $para = $rp.'ExchangeLocationException (Optional)'
                $cmdlet += " -ExchangeLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocation (Optional)'))
            {
                $para = $rp.'ModernGroupLocation (Optional)'
                $cmdlet += " -ModernGroupLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocationException (Optional)'))
            {
                $para = $rp.'ModernGroupLocationException (Optional)'
                $cmdlet += " -ModernGroupLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocation (Optional)'))
            {
                $para = $rp.'OneDriveLocation (Optional)'
                $cmdlet += " -OneDriveLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocationException (Optional)'))
            {
                $para = $rp.'OneDriveLocationException (Optional)'
                $cmdlet += " -OneDriveLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocation (Optional)'))
            {
                $para = $rp.'SharePointLocation (Optional)'
                $cmdlet += " -SharePointLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocationException (Optional)'))
            {
                $para = $rp.'SharePointLocationException (Optional)'
                $cmdlet += " -SharePointLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'PublicFolderLocation (Optional)'))
            {
                $para = $rp.'PublicFolderLocation (Optional)'
                $cmdlet += " -PublicFolderLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocation (Optional)'))
            {
                $para = $rp.'SkypeLocation (Optional)'
                $cmdlet += " -SkypeLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocationException (Optional)'))
            {
                $para = $rp.'SkypeLocationException (Optional)'
                $cmdlet += " -SkypeLocationException " + $para
            }
            # If the policy already exists, skip for creation
            if (($policies -eq $null) -or ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create retention compliance policy
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
            
                $ret = invokepowershellcmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
                $rpid = $ret.Guid
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The policy '$name' already exists! Skip for creation!"
                $rpid = ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }).Guid
            }
                        
            # Retrieve tag name for publishing
            $ts = $rp.'PublishComplianceTag (Required)'
            $tagList = $ts.Split(",") | ForEach-Object { $_.Trim() }
            
            WriteToLog -Type "Message" -Message "Publish Tags : '$ts'" 
            
            PublishComplianceTag -PolicyGuid $rpid -TagName $tagList
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Publish Compliance Tag
# -------------------
Function PublishComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$PolicyGuid,
        [Parameter(Mandatory = $true)]
        [String[]]$TagNames
    )
    
    WriteToLog -Type "Start" "Start to Publish Compliance Tag"
    try
    {
        # Retrieve existing rule related to the given compliance policy
        $rule = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $PolicyGuid)
        $tagGuids = New-Object System.Collections.ArrayList
        
        foreach ($tn in $TagNames)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag {0}" -f $tn)
            $tagGuids.Add($t.Guid) | Out-Null
        }
        if ($rule -ne $null)
        {
            foreach ($r in $rule)
            {
                if ([String]::IsNullOrEmpty($r.PublishComplianceTag))
                {
                    continue;
                }
                else
                {
                    $tl = $r.PublishComplianceTag.Split(",")
                    if ($tagGuids.Contains([GUID]$tl[0]))
                    {
                        $tagGuids.Remove([GUID]$tl[0]);
                    }
                }
            }
        }
        
        foreach($t in $tagGuids)
        {
            # Publish compliance tag
            $cmdlet = "New-RetentionComplianceRule -Policy {0} -PublishComplianceTag {1}" -f $PolicyGuid, $t
            $ret = InvokePowerShellCmdlet $cmdlet
            
            if ($ret -eq $null)
            {
                WriteToLog -Type "Failed" $error[0]
                break;
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Export All Labels Created in The Process
# -------------------
Function ExportCreatedComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$LabelFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Compliance Tag Created"
    try
    {
        # Import input csv
        $labels = Import-Csv $LabelFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn Name,([string])
        $col2 = New-Object system.Data.DataColumn Comment,([string])
        $col3 = New-Object system.Data.DataColumn IsRecordLabel,([string])
        $col4 = New-Object system.Data.DataColumn RetentionAction,([string])
        $col5 = New-Object system.Data.DataColumn RetentionDuration,([string])
        $col6 = New-Object system.Data.DataColumn RetentionType,([string])
        $col7 = New-Object system.Data.DataColumn ReviewerEmail,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        foreach($lab in $labels)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag '{0}' " -f $lab.'Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Name'] = $t.Name
            $row['Comment'] = $t.Comment
            $row['IsRecordLabel'] = $t.IsRecordLabel
            $row['RetentionAction'] = $t.RetentionAction
            $row['RetentionDuration'] = $t.RetentionDuration
            $row['RetentionType'] = $t.RetentionType
            $row['ReviewerEmail'] = $t.ReviewerEmail
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# -------------------
# Export All Published Labels and Policies in The Process
# -------------------
Function ExportPublishedComplianceTagAndPolicy
{
    Param(
        [Parameter(Mandatory = $true)]
        [String[]]$PolicyFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Published Compliance Tag and Policy"
    try
    {
        # Import input csv
        $policies = Import-Csv $PolicyFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn 'Policy Name',([string])
        $col2 = New-Object system.Data.DataColumn PublishComplianceTag,([string])
        $col3 = New-Object system.Data.DataColumn Comment,([string])
        $col4 = New-Object system.Data.DataColumn Enabled,([string])
        $col5 = New-Object system.Data.DataColumn ExchangeLocation,([string])
        $col6 = New-Object system.Data.DataColumn ExchangeLocationException,([string])
        $col7 = New-Object system.Data.DataColumn ModernGroupLocation,([string])
        $col8 = New-Object system.Data.DataColumn ModernGroupLocationException,([string])
        $col9 = New-Object system.Data.DataColumn OneDriveLocation,([string])
        $col10 = New-Object system.Data.DataColumn OneDriveLocationException,([string])
        $col11 = New-Object system.Data.DataColumn PublicFolderLocation,([string])
        $col12 = New-Object system.Data.DataColumn SharePointLocation,([string])
        $col13 = New-Object system.Data.DataColumn SharePointLocationException,([string])
        $col14 = New-Object system.Data.DataColumn SkypeLocation,([string])
        $col15 = New-Object system.Data.DataColumn SkypeLocationException,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        $table.columns.add($col8)
        $table.columns.add($col9)
        $table.columns.add($col10)
        $table.columns.add($col11)
        $table.columns.add($col12)
        $table.columns.add($col13)
        $table.columns.add($col14)
        $table.columns.add($col15)
        foreach($policy in $policies)
        {
            $t = InvokePowerShellCmdlet ("Get-RetentionCompliancePolicy '{0}' -DistributionDetail" -f $policy.'Policy Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Policy Name'] = $t.Name
            
            $rules = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $t.Guid)
            $tagList = [String]::Empty
            foreach($rule in $rules)
            {
                if ([String]::IsNullOrEmpty($rule.PublishComplianceTag) -eq $False)
                {
                    $tName = $rule.PublishComplianceTag.Split(',')[1]
                    $tagList = [String]::Concat($tagList, $tName, ",")
                }
            }
            if (![String]::IsNullOrEmpty($tagList))
            {
                $tagList = $tagList.Substring(0, $tagList.LastIndexOf(','))
            }
            $row['PublishComplianceTag'] = $tagList
            $row['Comment'] = $t.Comment
            $row['Enabled'] = $t.Enabled
            $row['ExchangeLocation'] = $t.ExchangeLocation
            $row['ExchangeLocationException'] = $t.ExchangeLocationException
            $row['ModernGroupLocation'] = $t.ModernGroupLocation
            $row['ModernGroupLocationException'] = $t.ModernGroupLocationException
            $row['OneDriveLocation'] = $t.OneDriveLocation
            $row['OneDriveLocationException'] = $t.OneDriveLocationException
            $row['PublicFolderLocation'] = $t.PublicFolderLocation
            $row['SharePointLocation'] = $t.SharePointLocation
            $row['SharePointLocationException'] = $t.SharePointLocationException
            $row['SkypeLocation'] = $t.SkypeLocation
            $row['SkypeLocationException'] = $t.SkypeLocationException
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagPubRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# Create compliance tag
CreateComplianceTag -FilePath $LabelListCSV
# Create retention policy and publish compliance tag with the policy
CreateRetentionCompliancePolicy -FilePath $PolicyListCSV
# Export to result csv
if ($ResultCSV)
{
    ExportCreatedComplianceTag -LabelFilePath $LabelListCSV
    ExportPublishedComplianceTagAndPolicy -PolicyFilePath $PolicyListCSV 
}

```

## <a name="step-4-run-the-powershell-script"></a><span data-ttu-id="63702-155">4단계: PowerShell 스크립트 실행하기</span><span class="sxs-lookup"><span data-stu-id="63702-155">Step 4: Run the PowerShell script</span></span>

<span data-ttu-id="63702-156">먼저 [보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-156">First, [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="63702-157">그런 다음 보존 레이블을 만들고 게시하는 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-157">Then, run the script that creates and publishes the retention labels:</span></span>
  
1. <span data-ttu-id="63702-158">보안 및 준수 센터 PowerShell 세션에서 경로, 이어서 `.\` 문자와 스크립트의 파일 이름을 입력한 다음 Enter 키를 눌러 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-158">In your Security & Compliance Center PowerShell session, enter the path, followed by the characters `.\` and the file name of the script, and then press ENTER to run the script.</span></span> <span data-ttu-id="63702-159">예제:</span><span class="sxs-lookup"><span data-stu-id="63702-159">For example:</span></span>
    
    ```powershell
    <path>.\CreateRetentionSchedule.ps1
    ```

2. <span data-ttu-id="63702-160">스크립트에 이전 단계에서 만든 .csv 파일의 위치를 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63702-160">The script prompts you for the locations of the .csv files that you created in the previous steps.</span></span> <span data-ttu-id="63702-161">경로, 이어서 `.\` 문자와 .csv 파일의 파일 이름을 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="63702-161">Enter the path, followed by the characters `.\` and file name of the .csv file, and then press ENTER.</span></span> <span data-ttu-id="63702-162">예를 들어 첫 번째 프롬프트의 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-162">For example, for the first prompt:</span></span>
    
    ```powershell
    <path>.\Labels.csv
    ```

## <a name="step-5-view-the-log-file-with-the-results"></a><span data-ttu-id="63702-163">5단계: 결과가 포함된 로그 파일 보기</span><span class="sxs-lookup"><span data-stu-id="63702-163">Step 5: View the log file with the results</span></span>

<span data-ttu-id="63702-164">스크립트로 생성된 로그 파일을 사용하여 결과를 확인하고 해결해야 하는 오류를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="63702-164">Use the log file that the script created to check the results and identify any failures that need resolving.</span></span>

<span data-ttu-id="63702-165">다음 위치에서 로그 파일을 찾을 수 있습니다. 단, 파일 이름 예제의 숫자는 각기 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="63702-165">You can find the log file at the following location, although the digits in the example file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```


