---
title: 사서함 사이트 & 비즈니스용 OneDrive 콘텐츠 검색을 사용하여 사용자 목록 검색
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
description: 이 문서의 콘텐츠 검색 및 스크립트를 사용하여 사용자 그룹의 사서함 및 비즈니스용 OneDrive 사이트를 검색합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922470"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="65975-103">콘텐츠 검색을 사용하여 사용자 목록에 대 한 사서함 및 비즈니스용 OneDrive 검색</span><span class="sxs-lookup"><span data-stu-id="65975-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="65975-104">보안 & 준수 센터에서는 시간이 많이 걸리는 eDiscovery 관련 Windows PowerShell 자동화할 수 있는 다양한 cmdlet을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="65975-105">현재 보안 및 준수 & 콘텐츠 검색을 만들어 많은 수의 관리인 콘텐츠 위치를 검색하는 데는 많은 시간 및 준비가 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="65975-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="65975-106">검색을 만들기 전에 각 비즈니스용 OneDrive URL을 수집한 다음 각 사서함 및 비즈니스용 OneDrive 사이트를 검색에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="65975-107">향후 릴리스에서는 보안 및 준수 센터에서 더 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65975-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="65975-108">지금까지 이 문서의 스크립트를 사용하여 이 프로세스를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65975-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="65975-109">이 스크립트는 조직의 MySite 도메인 이름(예: URL의 **contoso),** 사용자 전자 메일 주소 목록, 새 콘텐츠 검색의 이름 및 사용할 검색 쿼리를 묻는 메시지를 `https://contoso-my.sharepoint.com` 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL `https://contoso-my.sharepoint.com`), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="65975-110">이 스크립트는 목록의 각 사용자에 대한 비즈니스용 OneDrive URL을 다운로드한 다음 제공한 검색 쿼리를 사용하여 목록의 각 사용자에 대해 사서함 및 비즈니스용 OneDrive 사이트를 검색하는 콘텐츠 검색을 만들고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span>
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="65975-111">사용 권한 및 스크립트 정보</span><span class="sxs-lookup"><span data-stu-id="65975-111">Permissions and script information</span></span>

- <span data-ttu-id="65975-112">3단계에서 스크립트를 실행하기 위해 Security & Compliance Center에서 eDiscovery 관리자 역할 그룹의 구성원이자 SharePoint Online 전역 관리자 역할 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>

- <span data-ttu-id="65975-113">2단계에서 만든 사용자 목록과 3단계의 스크립트를 동일한 폴더에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="65975-114">이를 통해 스크립트를 더 쉽게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65975-114">That will make it easier to run the script.</span></span>

- <span data-ttu-id="65975-115">스크립트에는 최소한의 오류 처리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="65975-115">The script includes minimal error handling.</span></span> <span data-ttu-id="65975-116">기본 목적은 각 사용자의 사서함 및 사이트 비즈니스용 OneDrive 쉽고 빠르게 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-116">Its primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>

- <span data-ttu-id="65975-p104">이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="65975-122">1단계: SharePoint Online 관리 셸 설치</span><span class="sxs-lookup"><span data-stu-id="65975-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="65975-123">첫 번째 단계는 온라인 관리 SharePoint 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="65975-124">이 절차에서는 셸을 사용할 필요는 없지만 3단계에서 실행한 스크립트에 필요한 필수 요구가 포함되어 있기 때문에 셸을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="65975-125">이러한 선행 작업을 통해 스크립트가 SharePoint Online과 통신하여 비즈니스용 OneDrive 사이트의 URL을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65975-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="65975-126">SharePoint [Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 관리 셸 Windows PowerShell 환경 설정으로 이동한 다음 1단계 및 2단계를 수행하여 SharePoint 온라인 관리 셸을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="65975-127">2단계: 사용자 목록 생성</span><span class="sxs-lookup"><span data-stu-id="65975-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="65975-128">3단계의 스크립트는 사용자 목록의 사서함 및 OneDrive 검색하는 콘텐츠 검색을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="65975-129">텍스트 파일에 전자 메일 주소를 입력하기만 하면 됩니다. 또는 Windows PowerShell 명령을 실행하여 전자 메일 주소 목록을 다운로드하여 파일에 저장할 수 있습니다(3단계에서 스크립트를 저장할 폴더와 동일한 폴더에 위치).</span><span class="sxs-lookup"><span data-stu-id="65975-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="65975-130">다음은 조직의 모든 Exchange Online 전자 메일 주소 목록을 다운로드하여 라는 텍스트 파일에 저장하기 위해 실행할 수 있는 [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 명령입니다. `Users.txt`</span><span class="sxs-lookup"><span data-stu-id="65975-130">Here's an [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="65975-131">이 명령을 실행한 후 파일을 열고 속성 이름 을 포함하는 헤더를 제거해야  `PrimarySmtpAddress` 합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="65975-132">텍스트 파일에는 전자 메일 주소 목록만 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="65975-133">전자 메일 주소 목록 앞이나 뒤의 빈 행이 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="65975-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="65975-134">3단계: 스크립트를 실행하여 검색 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="65975-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="65975-135">이 단계에서 스크립트를 실행 하면 다음 정보를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65975-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="65975-136">스크립트를 실행하기 전에 이 정보를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="65975-137">**사용자 자격** 증명 - 스크립트는 자격 증명을 사용하여 SharePoint Online에 액세스하여 비즈니스용 OneDrive URL을 얻고 원격 PowerShell을 사용하여 보안 & 준수 센터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="65975-138">**MySite** 도메인의 이름 - MySite 도메인은 조직의 모든 비즈니스용 OneDrive 사이트가 포함된 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="65975-139">예를 들어 MySite 도메인의 URL이 인 경우 스크립트에서 MySite 도메인의 이름을 묻는 메시지가 표시될 **https://contoso-my.sharepoint.com**  `contoso` 때 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="65975-140">**2단계** - 2단계에서 만든 텍스트 파일의 경로 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="65975-141">텍스트 파일과 스크립트가 같은 폴더에 있는 경우 텍스트 파일의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="65975-142">그렇지 않은 경우 텍스트 파일의 전체 경로 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="65975-143">**콘텐츠 검색의 이름** - 스크립트에서 만들 콘텐츠 검색의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="65975-144">**검색 쿼리** - 콘텐츠 검색에 사용할 검색 쿼리가 만들어지며 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="65975-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="65975-145">검색 쿼리에 대한 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건을 참조하세요.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="65975-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="65975-146">**스크립트를 실행하려면**</span><span class="sxs-lookup"><span data-stu-id="65975-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="65975-147">파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `SearchEXOOD4B.ps1` 입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="65975-148">2단계에서 사용자 목록을 저장한 폴더에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
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

2. <span data-ttu-id="65975-149">2단계에서 Windows PowerShell 열고 스크립트 및 사용자 목록을 저장한 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="65975-150">스크립트를 시작 합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="65975-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="65975-151">자격 증명을 입력하라는 메시지가 표시될 때 전자 메일 주소와 암호를 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="65975-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="65975-152">스크립트에서 메시지가 표시될 때 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="65975-153">각 정보를 입력한 다음 Enter를 **누르고 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="65975-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="65975-154">MySite 도메인의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="65975-155">사용자 목록이 포함된 텍스트 파일의 경로 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="65975-156">콘텐츠 검색의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65975-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="65975-157">검색 쿼리(콘텐츠 위치의 모든 항목을 반환하기 위해 이 비워 두기).</span><span class="sxs-lookup"><span data-stu-id="65975-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="65975-158">스크립트는 각 사이트의 URL을 비즈니스용 OneDrive 검색을 만들고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="65975-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="65975-159">Security & Compliance Center PowerShell에서 **Get-ComplianceSearch** cmdlet을 실행하여 검색 통계 및 결과를 표시하거나 &,  보안 및 준수 센터의 콘텐츠 검색 페이지로 이동하여 검색에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65975-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span>