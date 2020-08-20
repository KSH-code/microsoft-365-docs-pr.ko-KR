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
# <a name="use-content-search-for-targeted-collections"></a>대상 지정 컬렉션을 위해 콘텐츠 검색 사용

보안 준수 센터의 콘텐츠 검색 기능은 Exchange 사서함이나 SharePoint 및 비즈니스용 OneDrive 사이트의 특정 &amp; 폴더를 검색하는 UI를 직접 방법하지는 않습니다. 그러나 실제 검색 쿼리 구문의 사이트에 대한 폴더 *targeted collection*ID 속성 또는 전자 메일의 경로 속성(DocumentLink) 속성을 지정하여 특정 폴더(대상 컬렉션이라고 함)를 검색할 수 있습니다. 콘텐츠 검색을 사용하여 대상 컬렉션을 수행하는 것은 사례 또는 권한 있는 항목에 해당하는 항목이 특정 사서함 또는 사이트 폴더에 있는 경우에 유용합니다. 이 문서에 나오는 스크립트를 사용하여 SharePoint 및 비즈니스용 OneDrive 사이트의 폴더 경로(DocumentLink)를 사서함 폴더의 폴더 ID 또는 사서함 폴더의 폴더 ID(DocumentLink)를 가져올 수 있습니다. 그런 다음 검색 쿼리에서 폴더 ID 또는 경로를 사용하여 폴더에 있는 항목을 반환할 수 있습니다.

> [!NOTE]
> SharePoint 또는 비즈니스용 OneDrive 사이트의 폴더에 있는 콘텐츠를 반환하기 위해 이 항목의 스크립트에서는 Path 속성 대신 DocumentLink 관리 속성을 사용합니다. DocumentLink 속성은 폴더의 모든 콘텐츠를 반환하기 때문에 Path 속성보다 더 강력한 반면 Path 속성은 일부 미디어 파일을 반환하지 않습니다.

## <a name="before-you-use-content-search"></a>콘텐츠 검색을 사용하기 전에

- 1단계의 스크립트를 실행하려면 보안 준수 센터에서 eDiscovery &amp; 관리자(Manager) 역할 그룹의 구성원이어야 합니다. 자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.
    
    또한 Exchange Online 조직의 메일 받는 사람 역할을 할당해야 합니다. 1단계에 있는 **스크립트에 포함되어 있는 Get-MailboxFolderStatistics** cmdlet을 실행하려면 이 작업을 수행해야 합니다. 기본적으로 메일 받는 사람 역할은 Exchange Online의 조직 관리 및 받는 사람 관리 역할 그룹에 할당됩니다. Exchange Online에서 사용 권한을 할당하는 방법에 대한 자세한 내용은 역할 그룹 구성원 [관리를 참조하십시오.](https://go.microsoft.com/fwlink/p/?linkid=692102) 사용자 지정 역할 그룹을 만들고 Mail Recipients 역할을 할당한 다음 1단계에서 스크립트를 실행해야 하는 구성원을 추가할 수도 있습니다. 자세한 내용은 [역할 그룹 관리](https://go.microsoft.com/fwlink/p/?linkid=730688) 항목을 참조하십시오.
    
- 1단계에서 스크립트를 실행할 때마다 새 원격 PowerShell 세션이 만들어집니다. 따라서 사용 가능한 모든 원격 PowerShell 세션을 자를 수 있습니다. 이문제가 발생하지 않도록 하려면 다음 명령을 실행하여 활성 원격 PowerShell 세션 연결을 끊을 수 있습니다.
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    자세한 내용은 [원격 PowerShell을 사용하여 Exchange Online에 연결](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조하세요.
    
- 스크립트에는 최소한의 오류 처리가 포함되어 있습니다. 이 스크립트의 주요 목적은 대상 컬렉션을 수행하기 위해 콘텐츠 검색의 검색 쿼리 구문에 사용할 수 있는 사서함 폴더 ID 또는 사이트 경로 목록을 빠르게 표시하는 데 있습니다.
    
- 이 항목에서 제공하는 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다. 예제 스크립트는 어떤 종류의 보상 없이 있는 상태가 된 것과 같습니다. 또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 예제 스크립트 및 설명서의 사용 또는 성능으로 인한 전체 위험은 사용자에게 있습니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>1단계: 스크립트를 실행하여 사서함 또는 사이트에 대한 폴더 목록 가져오기

이 첫 번째 단계에서 실행한 스크립트는 사서함 폴더 또는 SharePoint 및 비즈니스용 OneDrive 폴더 목록과 각 폴더에 대 한 해당 폴더 ID 또는 경로 목록을 반환합니다. 이 스크립트를 실행하면 다음 정보를 입력하라는 메시지가 표시됩니다.
  
- **전자 메일 주소 또는 사이트 URL** Exchange 사서함 폴더 및 폴더 ID 목록을 반환하려면 보유자의 전자 메일 주소를 입력합니다. 또는 지정된 사이트의 경로 목록을 반환할 SharePoint 사이트 또는 비즈니스용 OneDrive 사이트의 URL을 입력합니다. 그 예는 다음과 같습니다. 
    
  - **Exchange** - stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **비즈니스용 OneDrive** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **사용자 자격 증명** - 스크립트는 자격 증명을 사용하여 Exchange Online 및 원격 PowerShell을 사용하여 & 준수 센터에 연결합니다. 앞서 설명한 것과 같이 이 스크립트를 실행하려면 적절한 사용 권한을 할당해야 합니다.
    
사서함 폴더 또는 사이트 문서 링크(경로) 이름의 목록 표시:
  
1. 파일 이름 확장자 .Windows PowerShell 사용하여 스크립트 파일에 다음 텍스트를 저장합니다. 예를 들면 `GetFolderSearchParameters.ps1` 다음과 같습니다.
    
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

2. 로컬 컴퓨터에서 폴더를 Windows PowerShell 스크립트를 저장한 폴더로 이동합니다.
    
3. 스크립트를 실행합니다. 예를 들어:
    
   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. 스크립트가 사용자에게 묻는 정보를 입력합니다.
    
    스크립트는 지정된 사용자에 대한 사서함 폴더 또는 사이트 폴더 목록을 표시합니다. 폴더 ID 또는 documentlink 이름을 복사한 후 2단계의 검색 쿼리에 붙여넣을 수 있도록 이 창을 열어 둡니다.
    
    > [!TIP]
    > 컴퓨터 화면에 폴더 목록을 표시하는 대신 스크립트 출력을 텍스트 파일로 다시 보낼 수 있습니다. 이 파일은 스크립트가 있는 폴더에 저장됩니다. 예를 들어 스크립트 출력을 텍스트 파일로 리디렉션하려면 3단계에서 다음 명령을 실행합니다. 그런 다음 검색  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 쿼리에서 사용할 폴더 ID 또는 documentlink를 파일에서 복사할 수 있습니다.
  
### <a name="script-output-for-mailbox-folders"></a>사서함 폴더에 대한 스크립트 출력

사서함 폴더 ID를 가져오는 경우, 스크립트는 원격 PowerShell을 사용하여 Exchange Online에 연결하고 **Get-MailboxFolderStatisics** cmdlet을 실행한 다음 지정된 사서함에서 폴더 목록을 표시합니다. 사서함에 있는 모든 폴더에 대해 이 스크립트는 **FolderPath** 열에는 폴더 이름을 표시하고 폴더 ID는 **FolderQuery** 열에 표시합니다. 또한 이 스크립트는 **folderId의** 접두사(사서함 속성의 이름)를 폴더 ID에 추가합니다. **folderid 속성은** 검색 가능 속성이므로 `folderid:<folderid>` 2단계의 검색 쿼리에서 해당 폴더를 검색하는 데 사용합니다. 이 스크립트는 최대 100개의 사서함 폴더를 표시합니다.

> [!IMPORTANT]
> 이 문서의 스크립트에는 **Get-MailboxFolderStatistics에서** 반환된 64자의 폴더 ID 값을 검색용으로 인덱싱된 48자 형식과 동일한 48자 형식으로 변환하는 인코딩 논리가 포함되어 있습니다. 이 문서의 스크립트를 실행하는 대신 PowerShell에서 **Get-MailboxFolderStatistics** cmdlet을 실행하여 폴더 ID를 가져오면 해당 폴더 ID 값을 사용하는 검색 쿼리가 실패합니다. 콘텐츠 검색에 사용할 수 있는 형식이 올바르게 지정된 폴더 ID를 가져오도록 스크립트를 실행해야 합니다.
  
다음은 사서함 폴더에 대한 스크립트에서 반환되는 출력의 예입니다.
  
![스크립트에서 반환되는 사서함 폴더 및 폴더 ID목록 예](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
2단계의 예제에서는 사용자의 복구 가능한 항목 폴더에서 제거 하위 폴더를 검색하는 데 사용되는 쿼리를 보여입니다.
  
### <a name="script-output-for-site-folders"></a>사이트 폴더에 대한 스크립트 출력

SharePoint 또는 비즈니스용 OneDrive 사이트에서 **documentlink** 속성의 경로를 가져오는 경우, 스크립트는 원격 PowerShell을 사용하여 보안 & 준수 센터에 연결하고 사이트에서 폴더를 검색하는 새 콘텐츠 검색을 만든 다음 지정된 사이트에 있는 폴더의 목록을 표시합니다. 스크립트는 각 폴더의 이름을 표시하고 폴더 URL에 **documentlink의 접두사를** 추가합니다. documentlink 속성이 **검색** 가능 속성이므로 2단계의 검색 `documentlink:<path>` 쿼리에서 속성:값 쌍을 사용하여 폴더를 검색합니다. 이 스크립트는 최대 200개의 사이트 폴더를 표시합니다. 사이트 폴더가 200개를 초과하는 경우 가장 큰 폴더가 표시됩니다.
  
다음은 사이트 폴더에 대한 스크립트에서 반환되는 출력 예제입니다.
  
![스크립트에서 반환되는 사이트 폴더의 documentlink 이름 목록 예](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>2단계: 폴더 ID 또는 문서 링크를 사용하여 대상 컬렉션 수행

특정 사용자에 대한 폴더 ID 또는 문서 링크 목록을 수집하는 스크립트를 실행한 후 다음 단계를 수행하여 보안 & 준수 센터로 이동한 후 특정 폴더를 검색하는 새 콘텐츠 검색을 만듭니다. 콘텐츠 검색 키워드 상자에서 `folderid:<folderid>` `documentlink:<path>` 구성한 검색 쿼리(또는 New-ComplianceSearch cmdlet을 사용하는 경우 *ContentMatchQuery 매개* 변수의 값)에 또는 속성:값 **쌍을 사용합니다.** 또는 속성을 다른 검색  `folderid` 매개 변수  `documentlink` 또는 검색 조건과 함께 사용할 수 있습니다. 쿼리에 속성만  `folderid`  `documentlink` 포함하면 지정한 폴더에 있는 모든 항목이 검색됩니다. 
  
1. [https://protection.office.com](https://protection.office.com)으로 이동합니다.
    
2. 1단계에서 스크립트를 실행하는 데 사용한 계정 및 자격 증명을 사용하여 로그인합니다.
    
3. 보안 센터의 왼쪽 창에서 & 검색 콘텐츠 **검색을 클릭한** \> **다음 새 추가** **아이콘을** ![ ](../media/O365-MDM-CreatePolicy-AddIcon.gif) 클릭합니다.
    
4. **새 검색** 페이지에서 콘텐츠 검색의 이름을 입력합니다. 이 이름은 조직 내에서 고유해야 합니다. 
    
5. **어디에서 사서함 폴더를**검색하시는지에 따라 다음 중 하나를 수행합니다.
    
    - **Choose specific mailbox to search** then add the same mailbox you 실행한 후 1단계에서 스크립트를 실행했을 때 지정한 사서함과 동일한 사서함을 추가합니다. 
    
      또는
    
    - 검색할 **특정 사이트 선택을 클릭하여** 검색한 다음 1단계에서 스크립트를 실행했을 때 지정한 것과 동일한 사이트 URL을 추가합니다. 
    
6. **다음**을 클릭합니다.
    
7. 페이지를 찾을 **항목의 키워드 상자에** 1단계의 스크립트에서  `folderid:<folderid>`  `documentlink:<path>` 반환된 값이나 값을 붙여넣습니다. 
    
    예를 들어 다음 스크린샷의 쿼리에서는 사용자의 복구 가능한 항목 폴더에서 제거 하위 폴더의 항목이 검색됩니다(제거 하위 폴더의 속성 값은 `folderid` 1단계의 스크린샷에 표시됨).
    
    ![검색 쿼리의 키워드 상자에 folderid 또는 documentlink 붙여넣기](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. **검색을** 클릭하여 대상 지정 컬렉션 검색을 시작합니다. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>대상 지정 컬렉션의 검색 쿼리 예

다음은 검색 쿼리에서 대상  `folderid` 컬렉션을  `documentlink` 수행하기 위해 사용하는 몇 가지 예입니다. 자리 표시자는 공간을  `folderid:<folderid>` 저장하는  `documentlink:<path>` 데 사용됩니다. 
  
- 이 예제에서는 세 가지 사서함 폴더를 검색합니다. 비슷한 쿼리 구문을 사용하여 사용자의 복구 가능한 항목 폴더에서 숨겨진 폴더를 검색할 수 있습니다.
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 이 예에서는 사서함 폴더에서 정확한 구가 포함된 항목을 검색합니다.
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- 이 예제에서는 제목에 문자 "NDA"가 포함된 문서가 들어 있는 사이트 폴더와 모든 하위 폴더를 검색합니다.
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- 다음은 사이트 폴더와 모든 하위 폴더에서 날짜 범위 내에 변경된 문서를 검색하는 예제입니다.
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>추가 정보

이 문서의 스크립트를 사용하여 대상 컬렉션을 수행할 때 다음 사항에 유의하세요.
  
- 스크립트는 결과에서 폴더를 제거하지 않습니다. 따라서 결과에 나열된 일부 폴더는 시스템에서 생성된 콘텐츠를 포함하므로 검색할 수 없거나 항목을 0으로 반환할 수 있습니다.
    
- 이 스크립트는 사용자의 기본 사서함에 대한 폴더 정보만 반환합니다. 사용자의 보관 사서함 폴더에 대한 정보는 반환하지 않습니다.
    
- 사서함 폴더를 검색할 때는 지정한 폴더(속성로  `folderid` 식별된)만 검색되며 하위 폴더는 검색되지 않습니다. 하위 폴더를 검색하려면 검색할 하위 폴더의 폴더 ID를 사용할 필요가 있습니다. 
    
- 사이트 폴더를 검색할 때 폴더(속성에 의해  `documentlink` 식별됨)와 모든 하위 폴더가 검색됩니다. 
    
- 검색 쿼리에서 속성만 지정한 검색 결과를 내보내는 경우에는 첫 번째 내보내기 옵션인 "알 수 없는 형식이 있는 항목을 제외하거나, 암호화되거나, 다른 이유로 인덱싱되지 않은 항목을 제외한 모든 `folderid` 항목"을 선택할 수 있습니다. 폴더 ID가 항상 인덱싱되므로 폴더의 모든 항목은 인덱싱 상태에 관계없이 항상 내보내집니다.
