---
title: 대상 컬렉션에 콘텐츠 검색 사용
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
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: 검색 창의 콘텐츠 Microsoft 365 규정 준수 센터 사용하여 특정 사서함 또는 사이트 폴더의 항목을 검색하는 대상 컬렉션을 수행할 수 있습니다.
ms.openlocfilehash: e5da234d78d2f26af70f3e69ff6a1917f9d99b34
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216272"
---
# <a name="use-content-search-for-targeted-collections"></a>대상 컬렉션에 콘텐츠 검색 사용

Microsoft 365 규정 준수 센터 콘텐츠 검색 도구는 UI에서 특정 폴더를 검색하는 직접적인 Exchange 사서함 또는 SharePoint 비즈니스용 OneDrive 없습니다. 그러나 실제 검색 쿼리 구문에서 사이트의 전자 메일 또는 경로(DocumentLink) 속성에 대한 폴더 ID 속성을 지정하여 특정 폴더(대상 컬렉션이라고도 합니다.)를 검색할 수 있습니다. 콘텐츠 검색을 사용하여 대상 컬렉션을 수행하면 사례 또는 권한 있는 항목에 응답하는 항목이 특정 사서함 또는 사이트 폴더에 있다는 확신이 있는 경우 유용합니다. 이 문서의 스크립트를 사용하여 사서함 폴더의 폴더 ID를 얻을 수도 있으며, 사서함 폴더 및 폴더의 경로(DocumentLink)를 SharePoint 비즈니스용 OneDrive 있습니다. 그런 다음 검색 쿼리의 폴더 ID 또는 경로를 사용하여 폴더에 있는 항목을 반환할 수 있습니다.

> [!NOTE]
> 이 항목의 스크립트는 SharePoint 비즈니스용 OneDrive 폴더에 있는 콘텐츠를 반환하기 위해 Path 속성 대신 DocumentLink 관리 속성을 사용합니다. DocumentLink 속성은 폴더의 모든 콘텐츠를 반환하기 때문에 Path 속성보다 강력하고 Path 속성은 일부 미디어 파일을 반환하지 않습니다.

## <a name="before-you-run-a-targeted-collection"></a>대상 컬렉션을 실행하기 전에

- 1단계에서 스크립트를 실행하기 위해 Microsoft 365 규정 준수 센터 관리자 역할 그룹의 구성원이 되어야 합니다. 자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.

- 조직에서 Mail Recipients 역할도 할당해야 Exchange Online. 스크립트에 포함된 **Get-MailboxFolderStatistics** cmdlet을 실행하려면 이 작업을 실행해야 합니다. 기본적으로 Mail Recipients 역할은 조직의 조직 관리 및 받는 사람 관리 역할 그룹에 Exchange Online. 권한 할당에 대한 자세한 내용은 역할 Exchange Online 구성원 [관리를 참조하십시오.](/exchange/manage-role-group-members-exchange-2013-help) 사용자 지정 역할 그룹을 만들고 Mail Recipients 역할을 할당한 다음 1단계에서 스크립트를 실행해야 하는 구성원을 추가할 수도 있습니다. 자세한 내용은 [역할 그룹 관리](/Exchange/permissions-exo/role-groups) 항목을 참조하십시오.

- 이 문서의 스크립트는 최신 인증을 지원합니다. 조직 또는 조직에 있는 경우 스크립트를 있는 Microsoft 365 사용할 Microsoft 365 GCC 있습니다. 독일 Office 365, Microsoft 365 GCC High 조직 또는 Microsoft 365 DoD 조직인 경우 스크립트를 편집하여 스크립트를 성공적으로 실행해야 합니다. 특히 줄을 편집하고 `Connect-ExchangeOnline` *ExchangeEnvironmentName* 매개 변수 및 조직 유형에 적합한 값을 사용하여 PowerShell에 Exchange Online 합니다.  또한 줄을 편집하고 `Connect-IPPSSession` *ConnectionUri* 및 *AzureADAuthorizationEndpointUri* 매개 변수 및 조직 유형에 적합한 값을 사용하여 보안 & PowerShell에 연결해야 합니다. 자세한 내용은 [PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) 커넥트 Exchange Online 보안 및 준수 센터 PowerShell에 커넥트 예제를 & [참조하세요.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- 스크립트를 실행할 때마다 새 원격 PowerShell 세션이 만들어집니다. 즉, 사용 가능한 모든 원격 PowerShell 세션을 사용할 수 있습니다. 이러한 문제가 발생하지 않도록 방지하기 위해 다음 명령을 실행하여 활성 원격 PowerShell 세션 연결을 끊습니다.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    자세한 내용은 [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 스크립트에는 최소한의 오류 처리가 포함됩니다. 이 스크립트의 기본 목적은 콘텐츠 검색의 검색 쿼리 구문에서 대상 컬렉션을 수행하기 위해 사용할 수 있는 사서함 폴더의 ID 또는 사이트 경로 목록을 빠르게 표시하는 것입니다.

- 이 항목에서 제공하는 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다. 샘플 스크립트는 어떤 종류의 보증도 없이 그대로 제공됩니다. 또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>1단계: 스크립트를 실행하여 사서함 또는 사이트의 폴더 목록을 얻습니다.

이 첫 번째 단계에서 실행되는 스크립트는 사서함 폴더 또는 사서함 폴더 또는 SharePoint 및 비즈니스용 OneDrive 폴더 목록과 각 폴더에 대한 해당 폴더 ID 또는 경로를 반환합니다. 이 스크립트를 실행하면 다음 정보를 묻는 메시지가 나타날 수 있습니다.

- **전자 메일 주소 또는** 사이트 URL: 서버의 전자 메일 주소를 입력하여 Exchange 폴더의 목록을 반환합니다. 또는 SharePoint 사이트 또는 비즈니스용 OneDrive 사이트의 URL을 입력하여 지정된 사이트의 경로 목록을 반환합니다. 다음은 몇 가지 예입니다.

  - **Exchange**:`stacig@contoso.onmicrosoft.com`

  - **SharePoint**:`https://contoso.sharepoint.com/sites/marketing`

  - **비즈니스용 OneDrive**:`https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com`

- **사용자 자격 증명:** 스크립트는 최신 인증을 사용하여 Exchange Online PowerShell 또는 보안 & PowerShell에 연결하는 데 자격 증명을 사용하게 됩니다. 앞서 설명한 것 처럼 이 스크립트를 성공적으로 실행하려면 적절한 사용 권한을 할당해야 합니다.

사서함 폴더 또는 사이트 문서 링크(경로) 이름의 목록을 표시하는 경우:

1. 파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `GetFolderSearchParameters.ps1` 입니다.

   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Microsoft 365 compliance center.            #
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
   # Authenticate with Exchange Online and the Microsoft 365 compliance center (Exchange Online Protection - EOP)
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
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
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
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

2. 로컬 컴퓨터에서 Windows PowerShell 열고 스크립트를 저장한 폴더로 이동합니다.

3. 스크립트를 실행합니다. 예를 들어:

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. 스크립트에서 요청하는 정보를 입력합니다.

    이 스크립트는 지정된 사용자의 사서함 폴더 또는 사이트 폴더 목록을 표시합니다. 폴더 ID 또는 문서링크 이름을 복사하여 2단계의 검색 쿼리에 붙여넣을 수 있도록 이 창을 열어 넣습니다.

    > [!TIP]
    > 컴퓨터 화면에 폴더 목록을 표시하는 대신 스크립트 출력을 텍스트 파일로 다시 지시할 수 있습니다. 이 파일은 스크립트가 있는 폴더에 저장됩니다. 예를 들어 스크립트 출력을 텍스트 파일로 리디렉션하기 위해 3단계: 파일에서 폴더 ID 또는 문서 링크를 복사하여 검색 쿼리에 사용할 수  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 있습니다.

### <a name="script-output-for-mailbox-folders"></a>사서함 폴더에 대한 스크립트 출력

사서함 폴더를 받는 경우 스크립트는 Exchange Online PowerShell에 연결하고 **Get-MailboxFolderStatisics** cmdlet을 실행한 다음 지정된 사서함의 폴더 목록을 표시합니다. 사서함의 모든 폴더에 대해 이 스크립트는 **FolderPath** 열에 있는 폴더의 이름과 **FolderQuery** 열의 폴더 ID를 표시됩니다. 또한 스크립트는 폴더 ID에 **folderId(사서함** 속성의 이름)의 prefix를 추가합니다. **folderid** 속성은 검색 가능한 속성이기 때문에 2단계의 검색 쿼리에서 해당 폴더를 `folderid:<folderid>` 검색합니다. 스크립트는 최대 100 개의 사서함 폴더를 표시 합니다.

> [!IMPORTANT]
> 이 문서의 스크립트에는 **Get-MailboxFolderStatistics에서** 반환된 64자 폴더 ID 값을 검색을 위해 인덱싱되는 동일한 48자 형식으로 변환하는 인코딩 논리가 포함되어 있습니다. PowerShell에서 **Get-MailboxFolderStatistics** cmdlet을 실행하여 폴더 ID를 얻는 경우(이 문서에서 스크립트를 실행하는 대신) 해당 폴더 ID 값을 사용하는 검색 쿼리가 실패합니다. 스크립트를 실행하여 콘텐츠 검색에 사용할 수 있는 올바르게 형식이 지정된 폴더 ID를 만들어야 합니다.

다음은 사서함 폴더에 대한 스크립트에서 반환된 출력의 예입니다.

![스크립트에서 반환된 사서함 폴더 및 폴더의 목록 예입니다.](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

2단계의 예제에서는 사용자의 복구 가능한 항목 폴더에서 제거 하위 폴더를 검색하는 데 사용되는 쿼리를 보여 제공합니다.

### <a name="script-output-for-site-folders"></a>사이트 폴더에 대한 스크립트 출력

SharePoint 또는 비즈니스용 OneDrive 사이트에서 **documentlink** 속성의 경로를 표시하는 경우 스크립트는 Security & Compliance PowerShell에 연결하여 사이트에서 폴더를 검색하는 새 콘텐츠 검색을 만든 다음 지정된 사이트에 있는 폴더 목록을 표시합니다. 스크립트는 각 폴더의 이름을 표시하고 폴더 URL에 **documentlink의 prefix를** 추가합니다. **documentlink** 속성은 검색 가능한 속성이기 때문에 2단계의 검색 쿼리에서 property:value 쌍을 사용하여 해당 폴더를 `documentlink:<path>` 검색합니다. 스크립트에 최대 200개 사이트 폴더가 표시됩니다. 사이트 폴더가 200개가 넘는 경우 가장 새로 추가된 폴더가 표시됩니다.

다음은 사이트 폴더에 대한 스크립트에서 반환된 출력의 예입니다.

![스크립트에서 반환된 사이트 폴더의 문서링크 이름 목록 예제입니다.](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>2단계: 폴더 ID 또는 문서 링크를 사용하여 대상 컬렉션 수행

스크립트를 실행하여 특정 사용자에 대한 폴더 ID 또는 문서 링크 목록을 수집한 후 다음 단계로 이동하여 특정 폴더를 Microsoft 365 규정 준수 센터 새 콘텐츠 검색을 만들어야 합니다. 콘텐츠 검색 키워드 상자에서 구성한 검색 쿼리에서 or property:value 쌍을 사용하거나 `folderid:<folderid>` `documentlink:<path>` **New-ComplianceSearch** cmdlet을 사용하는 경우 *ContentMatchQuery* 매개 변수의 값으로 사용합니다. 또는 속성을 다른 검색 매개 변수  `folderid`  `documentlink` 또는 검색 조건과 결합할 수 있습니다. 쿼리에 or 속성만 포함하면 지정한 폴더에 있는 모든 항목이  `folderid`  `documentlink` 검색에 반환됩니다.

1. 1단계에서 스크립트를 실행하기 위해 사용한 계정 및 자격 증명으로 <https://compliance.microsoft.com> 이동하여 로그인합니다.

2. 준수 센터의 왼쪽 창에서 모든 콘텐츠 검색 표시를 클릭한 다음  >  새 검색 **을 클릭합니다.**

3. 키워드 **상자에** 1단계의 스크립트에서 반환된 또는 값을 `folderid:<folderid>`  `documentlink:<path>/*` 붙여 넣습니다.

    예를 들어 다음 스크린샷의 쿼리는 사용자의 복구 가능한 항목 폴더에 있는 제거 하위 폴더의 항목을 검색합니다. 제거 하위 폴더의 속성 값은 1단계의 스크린샷에 표시됩니다. `folderid`

    ![folderid 또는 documentlink를 검색 쿼리의 키워드 상자에 붙여 넣습니다.](../media/FolderIDSearchQuery.png)
    > [!IMPORTANT]
    > documentlink 검색에는 후행 을 사용해야  `asterisk '/*'` 합니다.  

4. 위치 **아래에서** 특정 **위치를 선택한** 다음 수정을 **클릭합니다.**

5. 사서함 폴더 또는 사이트 폴더를 검색하는지 여부에 따라 다음 중 하나를 합니다.

    - 전자 **Exchange** 옆에 있는 **사용자,** 그룹 또는 팀 선택을 클릭한 다음 1단계에서 스크립트를 실행할 때 지정한 사서함을 추가합니다.

      또는

    - 사이트 **SharePoint** 옆에서 사이트  선택을 클릭한 다음 1단계에서 스크립트를 실행할 때 지정한 동일한 사이트 URL을 추가합니다.

6. 검색할 콘텐츠 위치를 저장한 후 저장을 & **실행을** 클릭하고 콘텐츠 검색의  이름을 입력한 다음 저장을 클릭하여 대상 컬렉션 검색을 시작하십시오.

### <a name="examples-of-search-queries-for-targeted-collections"></a>대상 컬렉션에 대한 검색 쿼리의 예

다음은 검색 쿼리에서 및 속성을 사용하여 대상 컬렉션을 수행하는 몇 가지  `folderid`  `documentlink` 예입니다. 자리를 비우고  `folderid:<folderid>`  `documentlink:<path>` 공간을 절약하는 데 사용됩니다.

- 이 예에서는 서로 다른 세 개의 사서함 폴더를 검색합니다. 유사한 쿼리 구문을 사용하여 사용자의 복구 가능한 항목 폴더에서 숨겨진 폴더를 검색할 수 있습니다.

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 이 예에서는 사서함 폴더에서 정확한 구가 포함된 항목을 검색합니다.

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- 이 예제에서는 사이트 폴더와 모든 하위 폴더에서 제목에 "NDA"라는 문자가 포함된 문서를 검색합니다.

  ```powershell
  documentlink:"<path>/*" AND filename:nda
  ```

- 이 예제에서는 사이트 폴더와 모든 하위 폴더에서 날짜 범위 내에서 변경된 문서를 검색합니다.

  ```powershell
  documentlink:"<path>/*" AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>추가 정보

이 문서의 스크립트를 사용하여 대상 컬렉션을 수행할 때 다음에 유의하세요.

- 스크립트는 결과에서 폴더를 제거하지 않습니다. 따라서 결과에 나열된 일부 폴더는 시스템 생성 콘텐츠를 포함하거나 사서함 항목이 아닌 하위 폴더만 포함하기 때문에 검색할 수 없는(또는 0개 항목 반환)될 수 있습니다.

- 이 스크립트는 사용자의 기본 사서함에 대한 폴더 정보만 반환합니다. 사용자의 보관 사서함에 있는 폴더에 대한 정보는 반환하지 않습니다. 사용자의 보관 사서함에 있는 폴더에 대한 정보를 반환하려면 스크립트를 편집할 수 있습니다. 이렇게하려면 줄을 으로 변경한 다음 편집된 스크립트를 `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` 저장하고 실행합니다. 이렇게 변경하면 사용자의 보관 사서함에 있는 폴더 및 하위 폴더의 폴더 ID가 반환됩니다. 전체 보관 사서함을 검색하기 위해 검색 쿼리에서 모든 폴더 ID 속성:값 쌍을 `OR` 연산자와 연결할 수 있습니다.

- 사서함 폴더를 검색할 때 속성으로 식별된 지정된 폴더만 검색됩니다. 하위 폴더는 `folderid` 검색되지 않습니다. 하위 폴더를 검색하려면 검색할 하위 폴더의 폴더 ID를 사용해야 합니다.

- 사이트 폴더를 검색할 때 해당 속성으로 식별된 폴더 및 모든 하위 폴더가 `documentlink` 검색됩니다.

- 검색 쿼리에서 속성만 지정한 검색 결과를 내보낼 때 첫 번째 내보내기 옵션인 "인식할 수 없는 형식의 항목을 제외한 모든 항목은 암호화되거나 다른 이유로 인덱싱되지 않았습니다."를 선택할 수 있습니다. `folderid` 폴더 ID는 항상 인덱싱됩니다.
