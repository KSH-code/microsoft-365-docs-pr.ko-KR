---
title: 콘텐츠 검색을 사용 하는 사용자 목록을 보려면 mailbox & 비즈니스용 OneDrive 사이트를 검색 합니다.
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 이 문서의 콘텐츠 검색 및 스크립트를 사용 하 여 사용자 그룹에 대 한 사서함 및 비즈니스용 OneDrive 사이트를 검색할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e3a10913cc4d8618e3d25bdf34e30c9d55a43324
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357800"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>콘텐츠 검색을 사용하여 사용자 목록에 대 한 사서함 및 비즈니스용 OneDrive 검색

보안 & 준수 센터는 시간이 오래 걸리는 eDiscovery 관련 작업을 자동화 하는 데 사용할 수 있는 다양 한 Windows PowerShell cmdlet을 제공 합니다. 현재, 보안 & 준수 센터에서 콘텐츠 검색을 만들어 많은 수의 custodian 콘텐츠 위치를 검색 하려면 시간과 준비를 수행 해야 합니다. 검색을 만들기 전에 각 비즈니스용 OneDrive 사이트에 대 한 URL을 수집한 다음 각 사서함과 비즈니스용 OneDrive 사이트를 검색에 추가 해야 합니다. 향후 릴리스에서는 보안 & 준수 센터에서이 작업을 수행 하기가 더 쉽습니다. 그때까지이 문서의 스크립트를 사용 하 여이 프로세스를 자동화할 수 있습니다. 이 스크립트는 조직의 내 사이트 도메인 (예: URL의 **contoso** `https://contoso-my.sharepoint.com` ), 사용자 전자 메일 주소 목록, 새 콘텐츠 검색의 이름, 사용할 검색 쿼리 등을 묻는 메시지를 표시 합니다. 이 스크립트는 목록에 있는 각 사용자의 비즈니스용 OneDrive URL을 가져온 다음, 사용자가 제공한 검색 쿼리를 사용 하 여 목록에 있는 각 사용자별로 사서함 및 비즈니스용 OneDrive 사이트를 검색 하는 콘텐츠 검색을 만들고 시작 합니다.
  
## <a name="permissions-and-script-information"></a>사용 권한 및 스크립트 정보

- 3 단계에서 스크립트를 실행 하려면 Security & 준수 센터 및 SharePoint Online 전역 관리자에서 eDiscovery Manager 역할 그룹의 구성원 이어야 합니다.

- 2 단계에서 만든 사용자 목록과 3 단계의 스크립트를 같은 폴더에 저장 해야 합니다. 이를 통해 스크립트를 보다 쉽게 실행할 수 있습니다.

- 스크립트에 최소 오류 처리가 포함 되어 있습니다. 이 기본 목적은 각 사용자의 사서함 및 비즈니스용 OneDrive 사이트를 빠르고 쉽게 검색 하는 것입니다.

- 이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>1단계: SharePoint Online 관리 셸 설치

첫 번째 단계는 SharePoint Online 관리 셸을 설치 하는 것입니다. 이 절차에서 셸을 사용할 필요는 없지만 3 단계에서 실행 하는 스크립트에 필요한 필수 구성 요소를 포함 하기 때문에 설치 해야 합니다. 이러한 필수 구성 요소를 통해 스크립트가 SharePoint Online과 통신 하 여 비즈니스용 OneDrive 사이트용 Url을 가져올 수 있습니다.
  
[Sharepoint Online 관리 셸 Windows PowerShell 환경 설정](https://go.microsoft.com/fwlink/p/?LinkID=286318) 으로 이동 하 여 1 단계와 2 단계를 수행 하 여 Sharepoint Online 관리 셸을 설치 합니다.
  
## <a name="step-2-generate-a-list-of-users"></a>2 단계: 사용자 목록 생성

3 단계의 스크립트는 콘텐츠 검색을 만들어 사서함 및 OneDrive 계정에서 사용자 목록을 검색 합니다. 텍스트 파일에 전자 메일 주소를 입력 하거나, Windows PowerShell에서 명령을 실행 하 여 전자 메일 주소 목록을 가져오고이를 파일 (3 단계에서 스크립트를 저장할 동일한 폴더에 있음)에 저장할 수 있습니다.
  
다음은 조직의 모든 사용자에 대 한 전자 메일 주소 목록을 가져와이를 이름이 이라는 텍스트 파일에 저장 하는 데 사용할 수 있는 [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) 명령입니다 `Users.txt` . 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

이 명령을 실행 한 후에는 파일을 열고 속성 이름이 포함 된 헤더를 제거 해야  `PrimarySmtpAddress` 합니다. 텍스트 파일에는 전자 메일 주소 목록 뿐 아니라 다른 것도 포함 해야 합니다. 전자 메일 주소 목록 앞 이나 뒤에 빈 행이 없는지 확인 합니다.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>3 단계: 스크립트를 실행 하 여 검색 만들기 및 시작

이 단계에서 스크립트를 실행 하면 다음 정보를 입력 하 라는 메시지가 표시 됩니다. 스크립트를 실행 하기 전에이 정보를 준비 해야 합니다.
  
- **사용자 자격 증명** -스크립트는 자격 증명을 사용 하 여 SharePoint Online에 액세스 하 여 비즈니스용 OneDrive url을 가져오고 원격 PowerShell을 사용 하 여 보안 & 준수 센터에 연결 합니다. 
    
- **내 사이트 도메인 이름** -내 사이트 도메인은 조직 내 모든 비즈니스용 OneDrive 사이트가 포함 된 도메인입니다. 예를 들어 내 사이트 도메인의 URL이 인 경우 **https://contoso-my.sharepoint.com**  `contoso` 스크립트에서 내 사이트 도메인 이름을 묻는 메시지를 표시 하는 경우를 입력 합니다. 
    
- 2 단계에서 만든 텍스트 파일의 경로 _ 이름 **에서 텍스트 파일의** 이름입니다. 텍스트 파일과 스크립트가 같은 폴더에 있는 경우 텍스트 파일의 이름을 입력 합니다. 그렇지 않으면 텍스트 파일의 전체 경로 이름을 입력 합니다. 
    
- **콘텐츠 검색의 이름** -스크립트에 의해 생성 되는 콘텐츠 검색의 이름입니다. 
    
- **검색 쿼리** -콘텐츠 검색에 사용할 검색 쿼리가 만들어지고 실행 됩니다. 검색 쿼리에 대 한 자세한 내용은 [키워드 쿼리 및 검색 조건을](keyword-queries-and-search-conditions.md)참조 하십시오.


**스크립트를 실행하려면**
    
1. 파일 이름 접미사. p s 1을 사용 하 여 Windows PowerShell 스크립트 파일에 다음 텍스트를 저장 합니다. 예를 들면 `SearchEXOOD4B.ps1` 입니다. 2 단계에서 사용자 목록을 저장 한 동일한 폴더에 파일을 저장 합니다.
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. Windows PowerShell을 열고 스크립트를 저장 한 폴더로 이동 하 고 2 단계에서 사용자 목록을 검색 합니다.
    
3. 스크립트를 시작 합니다. 예를 들어:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. 자격 증명을 묻는 메시지가 표시 되 면 전자 메일 주소와 암호를 입력 하 고 **확인**을 클릭 합니다. 
    
5. 스크립트에서 메시지가 표시 되 면 다음 정보를 입력 합니다. 각 **정보를 입력**한 다음 enter 키를 누릅니다.
    
    - 내 사이트 도메인의 이름입니다. 
    
    - 사용자 목록이 포함 된 텍스트 파일의 경로 이름입니다.
    
    - 콘텐츠 검색의 이름입니다.
    
    - 검색 쿼리 (이 값을 비워 두면 콘텐츠 위치의 모든 항목이 반환 됩니다.)
    
    이 스크립트는 각 비즈니스용 OneDrive 사이트에 대 한 Url을 가져온 다음 검색을 만들고 시작 합니다. 보안 & 준수 센터 PowerShell에서 **ComplianceSearch** cmdlet을 실행 하 여 검색 통계 및 결과를 표시 하거나, 보안 & 준수 센터의 **콘텐츠 검색** 페이지로 이동 하 여 검색에 대 한 정보를 볼 수 있습니다. 
