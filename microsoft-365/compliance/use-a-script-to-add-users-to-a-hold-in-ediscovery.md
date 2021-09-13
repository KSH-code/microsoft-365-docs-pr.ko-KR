---
title: 스크립트를 사용하여 Core eDiscovery 사례에서 보류에 사용자 추가
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: 스크립트를 실행하여 사이트 & 비즈니스용 OneDrive eDiscovery 사례와 연결된 새 보류에 사서함을 추가하는 Microsoft 365 규정 준수 센터.
ms.openlocfilehash: a521e96cd81649acf032f7c6a79473a7507e3ba2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216265"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>스크립트를 사용하여 Core eDiscovery 사례에서 보류에 사용자 추가

보안 & 준수 센터 PowerShell에서는 eDiscovery 사례 만들기 및 관리와 관련된 시간이 많이 걸리는 작업을 자동화할 수 있는 cmdlet을 제공합니다. 현재 핵심 eDiscovery 사례를 사용하여 Microsoft 365 규정 준수 센터 콘텐츠를 보류할 수 있는 위치에 두는 데는 많은 시간 및 준비가 소요됩니다. 예를 들어 보류를 만들기 전에 보류할 각 비즈니스용 OneDrive URL을 수집해야 합니다. 그런 다음 보류하려는 각 사용자에 대해 사서함 및 해당 사서함 비즈니스용 OneDrive 보류에 추가해야 합니다. 이 문서의 스크립트를 사용하여 이 프로세스를 자동화할 수 있습니다.
  
이 스크립트를 실행하면 조직의 내 사이트 도메인 이름(예: URL, 기존 `contoso` eDiscovery 사례의 이름, 사례와 연결된 새 보류의 이름, 보류할 사용자의 전자 메일 주소 목록 및 쿼리 기반 보류를 만들 때 사용할 검색 쿼리)을 묻는 메시지가 https://contoso-my.sharepoint.com) 표시됩니다. 그런 다음 스크립트는 목록의 각 사용자에 대한 비즈니스용 OneDrive 사이트의 URL을 다운로드하고 새 보류를 만든 다음 목록의 각 사용자에 대한 사서함 및 비즈니스용 OneDrive 사이트를 보류에 추가합니다. 또한 스크립트는 새 보류에 대한 정보가 포함된 로그 파일을 생성합니다.
  
이를 수행하기 위한 단계는 다음과 같습니다.
  
[1단계: SharePoint Online 관리 셸 설치](#step-1-install-the-sharepoint-online-management-shell)
  
[2단계: 사용자 목록 생성](#step-2-generate-a-list-of-users)
  
[3단계: 스크립트를 실행하여 보류 만들기 및 사용자 추가](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>보류에 사용자를 추가하기 전에

- 3단계에서 스크립트를 실행하기 위해 Microsoft 365 규정 준수 센터 및 SharePoint Online 관리자의 eDiscovery 관리자 역할 그룹의 구성원이 되어야 합니다. 자세한 내용은 Office 365 보안 및 준수 센터에서 [eDiscovery 권한 할당을 & 참조하세요.](assign-ediscovery-permissions.md)

- 사서함의 eDiscovery 사례와 연결된 보류에 최대 1,000개 사서함과 100개 사이트를 추가할 수 Microsoft 365 규정 준수 센터. 보류하려는 모든 사용자에게 비즈니스용 OneDrive 사이트가 있는 경우 이 문서의 스크립트를 사용하여 보류에 최대 100명 사용자를 추가할 수 있습니다.

- 2단계에서 만든 사용자 목록과 3단계의 스크립트를 동일한 폴더에 저장해야 합니다. 이를 통해 스크립트를 더 쉽게 실행할 수 있습니다.

- 이 스크립트는 기존 사례와 연결된 새 보류에 사용자 목록을 추가합니다. 스크립트를 실행하기 전에 보류와 연결하려는 사례가 만들어지야 합니다.

- 이 문서의 스크립트는 보안 및 준수 센터 PowerShell 및 & 온라인 관리 셸에 연결할 때 최신 SharePoint 지원됩니다. 조직 또는 조직에 있는 경우 스크립트를 있는 Microsoft 365 사용할 Microsoft 365 GCC 있습니다. 독일 Office 365, Microsoft 365 GCC High 조직 또는 Microsoft 365 DoD 조직인 경우 스크립트를 편집하여 스크립트를 성공적으로 실행해야 합니다. 특히 줄을 편집하고 `Connect-IPPSSession` *ConnectionUri* 및 *AzureADAuthorizationEndpointUri* 매개 변수(및 조직 유형에 적합한 값)를 사용하여 보안 & 준수 센터 PowerShell에 연결해야 합니다. 자세한 내용은 보안 및 준수 센터 [PowerShell에](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)대한 커넥트 예제를 & 참조하세요.

- 이 스크립트는 보안 및 준수 & PowerShell과 온라인 SharePoint 연결이 자동으로 끊어집니다.

- 스크립트에는 최소한의 오류 처리가 포함됩니다. 기본 목적은 각 사용자의 사서함 및 비즈니스용 OneDrive 쉽게 보류하는 것입니다.

- 이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>1단계: SharePoint Online 관리 셸 설치

첫 번째 단계는 로컬 컴퓨터에 SharePoint 온라인 관리 셸을 설치하는 것입니다. 이 절차에서는 셸을 사용할 필요는 없지만 3단계에서 실행한 스크립트에 필요한 필수 요구가 포함되어 있기 때문에 셸을 설치해야 합니다. 이러한 선행 작업을 통해 스크립트가 SharePoint Online과 통신하여 비즈니스용 OneDrive 사이트의 URL을 얻을 수 있습니다.
  
SharePoint [Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 관리 셸 Windows PowerShell 환경 설정으로 이동한 다음 1단계 및 2단계를 수행하여 로컬 컴퓨터에 SharePoint 온라인 관리 셸을 설치합니다.

## <a name="step-2-generate-a-list-of-users"></a>2단계: 사용자 목록 생성

3단계의 스크립트는 eDiscovery 사례와 연결된 보류를 만들고 사용자 목록의 사서함 및 비즈니스용 OneDrive 사이트를 보류에 추가합니다. 텍스트 파일에 전자 메일 주소를 입력하기만 하면 됩니다. 또는 Windows PowerShell 명령을 실행하여 전자 메일 주소 목록을 다운로드하여 파일에 저장할 수 있습니다(3단계에서 스크립트를 저장할 폴더와 동일한 폴더에 위치).
  
다음은 조직의 모든 사용자에 대한 전자 메일 주소 목록을 다운로드하고 HoldUsers.txt.라는 텍스트 파일에 저장하기 위한 PowerShell 명령(Exchange Online 조직에 연결된 원격 PowerShell을 사용하여 실행)HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

이 명령을 실행한 후 텍스트 파일을 열고 속성 이름이 포함된 헤더를  `PrimarySmtpAddress` 제거합니다. 그런 다음 3단계에서 만들 보류에 추가할 사용자를 제외한 모든 전자 메일 주소를 제거합니다. 전자 메일 주소 목록 앞이나 뒤의 빈 행이 없는지 확인
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>3단계: 스크립트를 실행하여 보류 만들기 및 사용자 추가

이 단계에서 스크립트를 실행 하면 다음 정보를 묻는 메시지가 표시 됩니다. 스크립트를 실행하기 전에 이 정보를 준비해야 합니다.
  
- **사용자 자격 증명:** 스크립트는 자격 증명을 사용하여 PowerShell을 사용하여 보안 및 & 센터에 연결합니다. 또한 이러한 자격 증명을 사용하여 SharePoint Online에 액세스하여 사용자 목록에 대한 비즈니스용 OneDrive URL을 얻습니다.

- **도메인의 SharePoint 이름:** 스크립트는 이 이름을 입력하라는 메시지가 표시되어 SharePoint 센터에 연결할 수 있습니다. 또한 조직의 도메인 URL에 OneDrive 이름을 사용 합니다. 예를 들어 관리 센터의 URL이고 OneDrive URL이 인 경우 스크립트에서 도메인 이름을 입력하라는 메시지가 표시될 때 `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` 를 입력합니다.

- **사례의 이름:** 기존 사례의 이름입니다. 스크립트는 이 사례와 연결된 새 보류를 생성합니다.

- **보류의 이름:** 스크립트가 만들고 지정된 사례와 연결되는 보류의 이름입니다.

- **쿼리 기반 보류에 대한 검색 쿼리:** 지정한 검색 조건을 충족하는 콘텐츠만 보류할 수 있도록 쿼리 기반 보류를 만들 수 있습니다. 모든 콘텐츠를 보류하기 위해 검색 쿼리를 묻는 메시지가 표시될 때 **Enter를** 누르기만 합니다.

- **보류 켜기 또는 해제:** 스크립트를 만든 후 보류를 켜거나 스크립트가 보류를 사용하도록 설정하지 않고 보류를 만들 수 있도록 할 수 있습니다. 스크립트가 보류를 설정하지 않은 경우 나중에 또는 다음 PowerShell 명령을 실행하여 Microsoft 365 규정 준수 센터 수 있습니다.

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **사용자 목록이** 있는 텍스트 파일의 이름 - 보류에 추가할 사용자 목록이 포함된 2단계의 텍스트 파일 이름입니다. 이 파일이 스크립트와 동일한 폴더에 있는 경우 파일 이름(예: 스크립트)을 HoldUsers.txt. 텍스트 파일이 다른 폴더에 있는 경우 파일의 전체 경로 이름을 입력합니다.

스크립트에서 요청하는 정보를 수집한 후 마지막 단계는 스크립트를 실행하여 새 보류를 만들고 사용자를 추가하는 것입니다.
  
1. 파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 `.ps1` 저장합니다. 예를 들면 `AddUsersToHold.ps1`와 같습니다.

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $finallist)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. 로컬 컴퓨터에서 Windows PowerShell 열고 스크립트를 저장한 폴더로 이동합니다.

3. 스크립트를 실행합니다. 예를 들어:

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. 스크립트에서 요청하는 정보를 입력합니다.

   이 스크립트는 보안 & 준수 센터 PowerShell에 연결한 다음 eDiscovery 사례에 새 보류를 만들고 비즈니스용 OneDrive 사용자에 대한 사서함 및 사서함을 추가합니다. 새 보류를 보기 위해 페이지의 **eDiscovery** 페이지에서 사례로 Microsoft 365 규정 준수 센터 수 있습니다.

스크립트 실행이 완료되면 다음 로그 파일을 만들고 스크립트가 있는 폴더에 저장합니다.
  
- **LocationsOnHold.txt:** 스크립트가 보류된 비즈니스용 OneDrive 사이트 및 사서함 목록이 들어 있습니다.

- **LocationsNotOnHold.txt:** 스크립트가 보류되지 비즈니스용 OneDrive 사이트 및 사서함 목록이 들어 있습니다. 사용자에게 사서함이 있지만 비즈니스용 OneDrive 없는 경우 사용자가 보류되지 않은 비즈니스용 OneDrive 사이트 목록에 포함됩니다.

- **GetCaseHoldPolicy.txt:** 새 보류를 만들고 나서 스크립트가 실행된 새 보류에 대한 **Get-CaseHoldPolicy** cmdlet의 출력을 포함 이 cmdlet이 반환하는 정보에는 사서함 및 비즈니스용 OneDrive 사이트가 보류된 사용자 목록과 보류를 사용할 수 있는지 여부가 포함됩니다. 

- **GetCaseHoldRule.txt:** 새 보류를 만들고 나서 스크립트가 실행된 새 보류에 대한 **Get-CaseHoldRule** cmdlet의 출력이 들어 있습니다. 이 cmdlet이 반환하는 정보에는 스크립트를 사용하여 쿼리 기반 보류를 만든 경우 검색 쿼리가 포함됩니다.
