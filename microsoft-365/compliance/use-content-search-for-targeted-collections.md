---
title: 대상 지정 컬렉션을 위해 콘텐츠 검색 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: 보안 대시보드 준수 센터의 & 콘텐츠 검색을 사용하여 대상 컬렉션을 수행합니다. 그러면 특정 사서함 또는 사이트 폴더에 항목이 위치할 수 있습니다.
ms.openlocfilehash: aa311d0f9226330d9f2d881af6dabbdc6d0a15b5
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814540"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="ca662-103">대상 지정 컬렉션을 위해 콘텐츠 검색 사용</span><span class="sxs-lookup"><span data-stu-id="ca662-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="ca662-104">보안 준수 센터의 콘텐츠 검색 기능은 Exchange 사서함이나 SharePoint 및 비즈니스용 OneDrive 사이트의 특정 &amp; 폴더를 검색하는 UI를 직접 방법하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-104">The Content Search feature in the Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="ca662-105">그러나 실제 검색 쿼리 구문의 사이트에 대한 폴더 *targeted collection*ID 속성 또는 전자 메일의 경로 속성(DocumentLink) 속성을 지정하여 특정 폴더(대상 컬렉션이라고 함)를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="ca662-106">콘텐츠 검색을 사용하여 대상 컬렉션을 수행하는 것은 사례 또는 권한 있는 항목에 해당하는 항목이 특정 사서함 또는 사이트 폴더에 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="ca662-107">이 문서에 나오는 스크립트를 사용하여 SharePoint 및 비즈니스용 OneDrive 사이트의 폴더 경로(DocumentLink)를 사서함 폴더의 폴더 ID 또는 사서함 폴더의 폴더 ID(DocumentLink)를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="ca662-108">그런 다음 검색 쿼리에서 폴더 ID 또는 경로를 사용하여 폴더에 있는 항목을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="ca662-109">SharePoint 또는 비즈니스용 OneDrive 사이트의 폴더에 있는 콘텐츠를 반환하기 위해 이 항목의 스크립트에서는 Path 속성 대신 DocumentLink 관리 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="ca662-110">DocumentLink 속성은 폴더의 모든 콘텐츠를 반환하기 때문에 Path 속성보다 더 강력한 반면 Path 속성은 일부 미디어 파일을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-use-content-search"></a><span data-ttu-id="ca662-111">콘텐츠 검색을 사용하기 전에</span><span class="sxs-lookup"><span data-stu-id="ca662-111">Before you use Content Search</span></span>

- <span data-ttu-id="ca662-112">1단계의 스크립트를 실행하려면 보안 준수 센터에서 eDiscovery &amp; 관리자(Manager) 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="ca662-113">자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca662-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="ca662-114">또한 Exchange Online 조직의 메일 받는 사람 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="ca662-115">1단계에 있는 **스크립트에 포함되어 있는 Get-MailboxFolderStatistics** cmdlet을 실행하려면 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1.</span></span> <span data-ttu-id="ca662-116">기본적으로 메일 받는 사람 역할은 Exchange Online의 조직 관리 및 받는 사람 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="ca662-117">Exchange Online에서 사용 권한을 할당하는 방법에 대한 자세한 내용은 역할 그룹 구성원 [관리를 참조하십시오.](https://go.microsoft.com/fwlink/p/?linkid=692102)</span><span class="sxs-lookup"><span data-stu-id="ca662-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="ca662-118">사용자 지정 역할 그룹을 만들고 Mail Recipients 역할을 할당한 다음 1단계에서 스크립트를 실행해야 하는 구성원을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="ca662-119">자세한 내용은 [역할 그룹 관리](https://go.microsoft.com/fwlink/p/?linkid=730688) 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca662-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="ca662-120">1단계에서 스크립트를 실행할 때마다 새 원격 PowerShell 세션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-120">Each time you run the script in Step 1, a new remote PowerShell session is created.</span></span> <span data-ttu-id="ca662-121">따라서 사용 가능한 모든 원격 PowerShell 세션을 자를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-121">So you could use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="ca662-122">이문제가 발생하지 않도록 하려면 다음 명령을 실행하여 활성 원격 PowerShell 세션 연결을 끊을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-122">To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="ca662-123">자세한 내용은 [원격 PowerShell을 사용하여 Exchange Online에 연결](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca662-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="ca662-124">스크립트에는 최소한의 오류 처리가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-124">The script includes minimal error handling.</span></span> <span data-ttu-id="ca662-125">이 스크립트의 주요 목적은 대상 컬렉션을 수행하기 위해 콘텐츠 검색의 검색 쿼리 구문에 사용할 수 있는 사서함 폴더 ID 또는 사이트 경로 목록을 빠르게 표시하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-125">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="ca662-126">이 항목에서 제공하는 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-126">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="ca662-127">예제 스크립트는 어떤 종류의 보상 없이 있는 상태가 된 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-127">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="ca662-128">또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-128">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="ca662-129">예제 스크립트 및 설명서의 사용 또는 성능으로 인한 전체 위험은 사용자에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-129">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="ca662-130">어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-130">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="ca662-131">1단계: 스크립트를 실행하여 사서함 또는 사이트에 대한 폴더 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="ca662-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="ca662-132">이 첫 번째 단계에서 실행한 스크립트는 사서함 폴더 또는 SharePoint 및 비즈니스용 OneDrive 폴더 목록과 각 폴더에 대 한 해당 폴더 ID 또는 경로 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-132">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="ca662-133">이 스크립트를 실행하면 다음 정보를 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-133">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="ca662-134">**전자 메일 주소 또는 사이트 URL** Exchange 사서함 폴더 및 폴더 ID 목록을 반환하려면 보유자의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-134">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="ca662-135">또는 지정된 사이트의 경로 목록을 반환할 SharePoint 사이트 또는 비즈니스용 OneDrive 사이트의 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-135">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="ca662-136">그 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-136">Here are some examples:</span></span> 
    
  - <span data-ttu-id="ca662-137">**Exchange** - stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ca662-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="ca662-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="ca662-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="ca662-139">**비즈니스용 OneDrive** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="ca662-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="ca662-140">**사용자 자격 증명** - 스크립트는 자격 증명을 사용하여 Exchange Online 및 원격 PowerShell을 사용하여 & 준수 센터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-140">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="ca662-141">앞서 설명한 것과 같이 이 스크립트를 실행하려면 적절한 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-141">As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="ca662-142">사서함 폴더 또는 사이트 문서 링크(경로) 이름의 목록 표시:</span><span class="sxs-lookup"><span data-stu-id="ca662-142">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="ca662-143">파일 이름 확장자 .Windows PowerShell 사용하여 스크립트 파일에 다음 텍스트를 저장합니다. 예를 들면 `GetFolderSearchParameters.ps1` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
   # The script will then:                                            #
   #    * If an email address is supplied: list the folders for the target mailbox.            #
   #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
   #    * for the site.                                                                                    #
   #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
   #      appended to the folder ID or documentlink to use in a Content Search.                #
   # Notes:                                                #
   #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
   #      the current folder and all sub-folders are searched.                        #
   #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
   #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
   #      each sub-folder that you want to search.                                #
   #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
   #########################################################################################################
   # Collect the target email address or SharePoint Url
   $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
   # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
   if (!$credentials)
   {
      $credentials = Get-Credential
   }
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
   }
   elseif ($addressOrSite.IndexOf("http") -ige 0)
   {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security & Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
   }
   else
   {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
   }
   ```

2. <span data-ttu-id="ca662-144">로컬 컴퓨터에서 폴더를 Windows PowerShell 스크립트를 저장한 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="ca662-145">스크립트를 실행합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="ca662-145">Run the script; for example:</span></span>
    
   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="ca662-146">스크립트가 사용자에게 묻는 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="ca662-147">스크립트는 지정된 사용자에 대한 사서함 폴더 또는 사이트 폴더 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-147">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="ca662-148">폴더 ID 또는 documentlink 이름을 복사한 후 2단계의 검색 쿼리에 붙여넣을 수 있도록 이 창을 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-148">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ca662-149">컴퓨터 화면에 폴더 목록을 표시하는 대신 스크립트 출력을 텍스트 파일로 다시 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-149">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="ca662-150">이 파일은 스크립트가 있는 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-150">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="ca662-151">예를 들어 스크립트 출력을 텍스트 파일로 리디렉션하려면 3단계에서 다음 명령을 실행합니다. 그런 다음 검색  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 쿼리에서 사용할 폴더 ID 또는 documentlink를 파일에서 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-151">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="ca662-152">사서함 폴더에 대한 스크립트 출력</span><span class="sxs-lookup"><span data-stu-id="ca662-152">Script output for mailbox folders</span></span>

<span data-ttu-id="ca662-153">사서함 폴더 ID를 가져오는 경우, 스크립트는 원격 PowerShell을 사용하여 Exchange Online에 연결하고 **Get-MailboxFolderStatisics** cmdlet을 실행한 다음 지정된 사서함에서 폴더 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-153">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="ca662-154">사서함에 있는 모든 폴더에 대해 이 스크립트는 **FolderPath** 열에는 폴더 이름을 표시하고 폴더 ID는 **FolderQuery** 열에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-154">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="ca662-155">또한 이 스크립트는 **folderId의** 접두사(사서함 속성의 이름)를 폴더 ID에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-155">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="ca662-156">**folderid 속성은** 검색 가능 속성이므로 `folderid:<folderid>` 2단계의 검색 쿼리에서 해당 폴더를 검색하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-156">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="ca662-157">이 스크립트는 최대 100개의 사서함 폴더를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-157">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca662-158">이 문서의 스크립트에는 **Get-MailboxFolderStatistics에서** 반환된 64자의 폴더 ID 값을 검색용으로 인덱싱된 48자 형식과 동일한 48자 형식으로 변환하는 인코딩 논리가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-158">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="ca662-159">이 문서의 스크립트를 실행하는 대신 PowerShell에서 **Get-MailboxFolderStatistics** cmdlet을 실행하여 폴더 ID를 가져오면 해당 폴더 ID 값을 사용하는 검색 쿼리가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-159">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="ca662-160">콘텐츠 검색에 사용할 수 있는 형식이 올바르게 지정된 폴더 ID를 가져오도록 스크립트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-160">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="ca662-161">다음은 사서함 폴더에 대한 스크립트에서 반환되는 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-161">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![스크립트에서 반환되는 사서함 폴더 및 폴더 ID목록 예](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="ca662-163">2단계의 예제에서는 사용자의 복구 가능한 항목 폴더에서 제거 하위 폴더를 검색하는 데 사용되는 쿼리를 보여입니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-163">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="ca662-164">사이트 폴더에 대한 스크립트 출력</span><span class="sxs-lookup"><span data-stu-id="ca662-164">Script output for site folders</span></span>

<span data-ttu-id="ca662-165">SharePoint 또는 비즈니스용 OneDrive 사이트에서 **documentlink** 속성의 경로를 가져오는 경우, 스크립트는 원격 PowerShell을 사용하여 보안 & 준수 센터에 연결하고 사이트에서 폴더를 검색하는 새 콘텐츠 검색을 만든 다음 지정된 사이트에 있는 폴더의 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-165">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to the Security & Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="ca662-166">스크립트는 각 폴더의 이름을 표시하고 폴더 URL에 **documentlink의 접두사를** 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-166">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="ca662-167">documentlink 속성이 **검색** 가능 속성이므로 2단계의 검색 `documentlink:<path>` 쿼리에서 속성:값 쌍을 사용하여 폴더를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-167">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="ca662-168">이 스크립트는 최대 200개의 사이트 폴더를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-168">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="ca662-169">사이트 폴더가 200개를 초과하는 경우 가장 큰 폴더가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-169">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="ca662-170">다음은 사이트 폴더에 대한 스크립트에서 반환되는 출력 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-170">Here's an example of the output returned by the script for site folders.</span></span>
  
![스크립트에서 반환되는 사이트 폴더의 documentlink 이름 목록 예](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="ca662-172">2단계: 폴더 ID 또는 문서 링크를 사용하여 대상 컬렉션 수행</span><span class="sxs-lookup"><span data-stu-id="ca662-172">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="ca662-173">특정 사용자에 대한 폴더 ID 또는 문서 링크 목록을 수집하는 스크립트를 실행한 후 다음 단계를 수행하여 보안 & 준수 센터로 이동한 후 특정 폴더를 검색하는 새 콘텐츠 검색을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-173">After you've run the script to collect a list of folder IDs or documentlinks for a specific user, the next step to go to the Security & Compliance Center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="ca662-174">콘텐츠 검색 키워드 상자에서 `folderid:<folderid>` `documentlink:<path>` 구성한 검색 쿼리(또는 New-ComplianceSearch cmdlet을 사용하는 경우 *ContentMatchQuery 매개* 변수의 값)에 또는 속성:값 **쌍을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca662-174">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="ca662-175">또는 속성을 다른 검색  `folderid` 매개 변수  `documentlink` 또는 검색 조건과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-175">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="ca662-176">쿼리에 속성만  `folderid`  `documentlink` 포함하면 지정한 폴더에 있는 모든 항목이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-176">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span> 
  
1. <span data-ttu-id="ca662-177">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-177">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="ca662-178">1단계에서 스크립트를 실행하는 데 사용한 계정 및 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-178">Sign in using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="ca662-179">보안 센터의 왼쪽 창에서 & 검색 콘텐츠 **검색을 클릭한** \> **다음 새 추가** **아이콘을** ![ ](../media/O365-MDM-CreatePolicy-AddIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-179">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**, and then click **New** ![Add icon](../media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="ca662-180">**새 검색** 페이지에서 콘텐츠 검색의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-180">On the **New search** page, type a name for the Content Search.</span></span> <span data-ttu-id="ca662-181">이 이름은 조직 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-181">This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="ca662-182">**어디에서 사서함 폴더를**검색하시는지에 따라 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-182">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="ca662-183">**Choose specific mailbox to search** then add the same mailbox you 실행한 후 1단계에서 스크립트를 실행했을 때 지정한 사서함과 동일한 사서함을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-183">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="ca662-184">또는</span><span class="sxs-lookup"><span data-stu-id="ca662-184">Or</span></span>
    
    - <span data-ttu-id="ca662-185">검색할 **특정 사이트 선택을 클릭하여** 검색한 다음 1단계에서 스크립트를 실행했을 때 지정한 것과 동일한 사이트 URL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-185">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="ca662-186">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-186">Click **Next**.</span></span>
    
7. <span data-ttu-id="ca662-187">페이지를 찾을 **항목의 키워드 상자에** 1단계의 스크립트에서  `folderid:<folderid>`  `documentlink:<path>` 반환된 값이나 값을 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-187">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="ca662-188">예를 들어 다음 스크린샷의 쿼리에서는 사용자의 복구 가능한 항목 폴더에서 제거 하위 폴더의 항목이 검색됩니다(제거 하위 폴더의 속성 값은 `folderid` 1단계의 스크린샷에 표시됨).</span><span class="sxs-lookup"><span data-stu-id="ca662-188">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![검색 쿼리의 키워드 상자에 folderid 또는 documentlink 붙여넣기](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="ca662-190">**검색을** 클릭하여 대상 지정 컬렉션 검색을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-190">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="ca662-191">대상 지정 컬렉션의 검색 쿼리 예</span><span class="sxs-lookup"><span data-stu-id="ca662-191">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="ca662-192">다음은 검색 쿼리에서 대상  `folderid` 컬렉션을  `documentlink` 수행하기 위해 사용하는 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-192">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="ca662-193">자리 표시자는 공간을  `folderid:<folderid>` 저장하는  `documentlink:<path>` 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-193">Note that placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="ca662-194">이 예제에서는 세 가지 사서함 폴더를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-194">This example searches three different mailbox folders.</span></span> <span data-ttu-id="ca662-195">비슷한 쿼리 구문을 사용하여 사용자의 복구 가능한 항목 폴더에서 숨겨진 폴더를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-195">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="ca662-196">이 예에서는 사서함 폴더에서 정확한 구가 포함된 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-196">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="ca662-197">이 예제에서는 제목에 문자 "NDA"가 포함된 문서가 들어 있는 사이트 폴더와 모든 하위 폴더를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-197">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="ca662-198">다음은 사이트 폴더와 모든 하위 폴더에서 날짜 범위 내에 변경된 문서를 검색하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-198">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="ca662-199">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ca662-199">More information</span></span>

<span data-ttu-id="ca662-200">이 문서의 스크립트를 사용하여 대상 컬렉션을 수행할 때 다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="ca662-200">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="ca662-201">스크립트는 결과에서 폴더를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-201">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="ca662-202">따라서 결과에 나열된 일부 폴더는 시스템에서 생성된 콘텐츠를 포함하므로 검색할 수 없거나 항목을 0으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-202">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="ca662-203">이 스크립트는 사용자의 기본 사서함에 대한 폴더 정보만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-203">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="ca662-204">사용자의 보관 사서함 폴더에 대한 정보는 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-204">It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="ca662-205">사서함 폴더를 검색할 때는 지정한 폴더(속성로  `folderid` 식별된)만 검색되며 하위 폴더는 검색되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-205">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="ca662-206">하위 폴더를 검색하려면 검색할 하위 폴더의 폴더 ID를 사용할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-206">To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="ca662-207">사이트 폴더를 검색할 때 폴더(속성에 의해  `documentlink` 식별됨)와 모든 하위 폴더가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-207">When searching site folders, the folder (identified by its  `documentlink` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="ca662-208">검색 쿼리에서 속성만 지정한 검색 결과를 내보내는 경우에는 첫 번째 내보내기 옵션인 "알 수 없는 형식이 있는 항목을 제외하거나, 암호화되거나, 다른 이유로 인덱싱되지 않은 항목을 제외한 모든 `folderid` 항목"을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-208">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="ca662-209">폴더 ID가 항상 인덱싱되므로 폴더의 모든 항목은 인덱싱 상태에 관계없이 항상 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="ca662-209">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
