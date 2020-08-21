---
title: 여러 콘텐츠 검색 만들기, 보고하기 및 삭제
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
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Office 365의 보안 및 준수 센터에서 PowerShell 스크립트를 통해 검색 만들기, 보고서 실행 등의 콘텐츠 & 검색 작업을 자동화하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d748e12942fa2d634f27c04de37ccf5b3ec19297
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845900"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>여러 콘텐츠 검색 만들기, 보고하기 및 삭제

 기본 데이터에 대해 알아보려는 경우 검색을 빠르게 만들고 보고하는 작업은 종종 eDiscovery 및 조사와 검색의 풍부성과 품질에 대한 중요한 단계입니다. 이작업을 지원하기 위해 보안 & 준수 센터 PowerShell은 시간이 오는 콘텐츠 검색 작업을 자동화하는 일집합의 cmdlet을 제공합니다. 이 스크립트를 사용하면 다수의 검색을 빠르고 간략하게 만들고 예상 검색 결과 보고서를 실행하여 해당 데이터의 수량을 확인하는 데 도움이 될 수 있는 예상 검색 결과 보고서를 실행합니다. 또한 스크립트를 사용하여 생성되는 각 검색 결과를 비교하기 위해 여러 버전의 검색을 만들 수 있습니다. 이러한 스크립트를 통해 데이터를 효율적으로 식별하고 색을 효율적으로 식별하고 조사할 수 있습니다.

## <a name="before-you-create-a-content-search"></a>콘텐츠 검색을 만들기 전에

- 이 항목에서 설명하는 스크립트를 실행하려면 보안 & 준수 센터에서 eDiscovery 관리자(Manager) 역할 그룹의 구성원이어야 합니다.

- 1단계에서 CSV 파일에 추가할 수 있는 조직의 비즈니스용 OneDrive 사이트에 대한 URL 목록을 수집하려면 조직에서 [모든 OneDrive 위치 목록 만들기를 참조하세요.](https://docs.microsoft.com/onedrive/list-onedrive-urls)

- 이 항목에서 만드는 모든 파일을 동일한 폴더에 저장해야 합니다. 이렇게 하면 스크립트를 더 쉽게 실행할 수 있습니다.

- 스크립트에는 최소한의 오류 처리가 포함됩니다. 주요 목적은 여러 콘텐츠 검색을 빠르게 만들고 보고하고 삭제하는 것입니다.

- 이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>1단계: 실행하려는 검색에 대한 정보가 포함된 CSV 파일 만들기

이 단계에서 만드는 CSV(쉼표로 구분된 값) 파일에는 검색할 각 사용자에 대한 행이 포함되어 있습니다. 사용자의 Exchange Online 사서함(사용하도록 설정된 경우 보관 사서함 포함) 및 비즈니스용 OneDrive 사이트를 검색할 수 있습니다. 또는 사서함 또는 비즈니스용 OneDrive 사이트만 검색할 수 있습니다. SharePoint Online 조직의 모든 사이트도 검색할 수 있습니다. 3단계에서 실행되는 스크립트는 CSV 파일의 각 행에 대해 개별적으로 검색을 만듭니다.

1. 메모장을 사용하여 다음 텍스트를 복사하여 .txt 파일에 붙여넣습니다. 이 파일을 로컬 컴퓨터의 폴더에 저장합니다. 다른 스크립트도 이 폴더에저장합니다.

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   파일의 첫 번째 행(머리글 행)에는 3단계의 스크립트에서 **New-ComplianceSearch** cmdlet에 의해 새 콘텐츠 검색을 만드는 데 사용되는 매개 변수가 표시되어 있습니다. 각 매개 변수 이름은 쉼표로 구분됩니다. 머리글 행에 공백이 있다는 보이는지 확인합니다. 머리글 행 아래의 각 행은 각 검색의 매개 변수 값을 나타냅니다. CSV 파일의 자리 표시자 데이터를 실제 데이터로 바꾸어야 합니다.

2. Excel에서 .txt 파일을 연 다음 다음 표의 정보를 사용하여 각 검색에 대한 정보가 포함된 파일을 편집합니다.

   ****

   |매개 변수|설명|
   |---|---|
   |`ExchangeLocation`|사용자 사서함의 SMTP 주소입니다.|
   |`SharePointLocation`|사용자의 비즈니스용 OneDrive 사이트 URL 또는 조직 내 모든 사이트의 URL입니다. 비즈니스용 OneDrive 사이트 URL에 사용할 URL은 다음 형식을 ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` 사용합니다. 예:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.|
   |`ContentMatchQuery`|검색에 대한 검색 쿼리입니다. 검색 쿼리를 만드는 방법에 대한 자세한 내용은 콘텐츠 [검색에 대한 키워드 쿼리 및 검색 조건을 참조하세요.](keyword-queries-and-search-conditions.md)|
   |`StartDate`|전자 메일 메시지의 경우 받는 사람이 메시지를 받거나 보낸 사람이 메시지를 보낸 날짜입니다. SharePoint 또는 비즈니스용 OneDrive 사이트에 있는 문서의 경우 문서가 마지막으로 수정된 이후의 날짜입니다.|
   |`EndDate`|전자 메일 메시지의 경우 사용자가 보냅니다. 메시지를 전송한 날짜입니다. SharePoint 또는 비즈니스용 OneDrive 사이트에 있는 문서의 경우 문서가 마지막으로 수정되기 전이나 완료된 날짜입니다.|
   |

3. Excel 파일을 CSV 파일로 로컬 컴퓨터의 폴더에 저장합니다. 3단계에서 만드는 스크립트는 이 CSV 파일의 정보를 사용하여 검색을 만듭니다.

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>2단계: 보안 및 준수 센터 PowerShell에 연결

다음 단계에서는 조직의 보안 및 준수 센터 PowerShell에 연결합니다. 단계별 지침은 [보안 및 준수 센터 PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)를 참조하세요.

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>3단계: 스크립트를 실행하여 검색 만들기 및 시작

이 단계의 스크립트에서는 1단계에서 만든 CSV 파일의 각 행에 대해 별도의 콘텐츠 검색을 만듭니다. 이 스크립트를 실행하면 다음의 두 값을 입력하라는 메시지가 표시됩니다.

- **검색 그룹 ID** - 이 이름은 CSV 파일에서 만든 검색을 구성하는 데 필요한 간략한 방법을 제공합니다. 각 검색의 이름은 검색 그룹 ID를 사용하여 이름이 지정되고 검색 이름에 숫자가 추가됩니다. 예를 들어 검색 그룹 **ID에 ContosoCase를** 입력하면 검색 이름이 **ContosoCase_1**, **ContosoCase_2,** **ContosoCase_3 등으로**이름이 지정됩니다. 입력하는 이름은 대/소문자를 구분합니다. 4단계와 5단계에서 검색 그룹 ID를 사용할 때 만들 때와 동일한 사례를 해야 합니다.

- **CSV 파일** - 1단계에서 만든 CSV 파일의 이름입니다. 전체 파일 이름(.csv 파일 확장명 포함)을 포함시둡니다. 예를 들면  `ContosoCase.csv` 다음과 같습니다.

스크립트를 실행하려면

1. 파일 이름 확장자 .Windows PowerShell 사용하여 스크립트 파일에 다음 텍스트를 저장합니다. 예를 들면 `CreateSearches.ps1` 다음과 같습니다. 다른 파일을 저장한 폴더에 파일을 저장합니다.

   ```Powershell
   # Get the Search Group ID and the location of the CSV input file
   $searchGroup = Read-Host 'Search Group ID'
   $csvFile = Read-Host 'Source CSV file'

   # Do a quick check to make sure our group name will not collide with other searches
   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

     $searchName = $searchGroup +'_' + $searchCounter
     $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
     if ($search)
     {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
     }
     $searchCounter++
   }

   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

     # Create the query
     $query = $_.ContentMatchQuery
     if(($_.StartDate -or $_.EndDate))
     {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
     }

     # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
     $exchangeLocation = $null
     if ( $_.ExchangeLocation)
     {
           $exchangeLocation = $_.ExchangeLocation
     }

     # Create and run the search
     $searchName = $searchGroup +'_' + $searchCounter
     Write-Host "Creating and running search: " $searchName -NoNewline
     $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query

     # Start and wait for each search to complete
     Start-ComplianceSearch $search.Name
     while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
     {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
     }
     Write-Host ""

     $searchCounter++
   }
   ```

2. 복사하고 Windows PowerShell 단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:

   ```Powershell
   .\CreateSearches.ps1
   ```

3. 검색 그룹 **ID 프롬프트에** 검색 그룹 이름을 입력한 다음 Enter 키를 누릅니다; **Enter** 예를 들면 `ContosoCase` 다음과 같습니다. 이 이름은 대/소문자를 구분하므로 후속 단계에서 동일한 방식으로 입력해야 합니다.

4. 원본 **CSV 파일 의스터에서** .csv 파일 확장명을 포함하여 CSV 파일의 이름을 입력합니다. 예를 들면  `ContosoCase.csv` 다음과 같습니다.

5. **Enter 키를 눌러** 스크립트를 계속 실행합니다.

   이 스크립트는 검색 만들기 및 실행의 진행률을 표시합니다. 스크립트가 완료되면 이 프롬프트로 다시 반환됩니다.

   ![여러 규정 준수 검색을 만드는 스크립트를 실행한 경우의 샘플 출력](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>4단계: 스크립트를 실행하여 검색 예상 결과 보고

검색을 만든 후에는 3단계에서 만든 각 검색의 검색 적중 횟수에 대한 간단한 보고서가 표시된 스크립트를 실행합니다. 이 보고서에는 각 검색의 결과 크기, 모든 검색의 총 적중 수 및 총 크기도 포함됩니다. 보고 스크립트를 실행하면 검색 그룹 ID를 입력하라는 메시지가 표시되며, CSV 파일로 보고서를 저장하려는 경우 CSV 파일 이름을 입력하라는 메시지가 표시됩니다.

1. 파일 이름 확장자 .Windows PowerShell 사용하여 스크립트 파일에 다음 텍스트를 저장합니다. 예를 들면 `SearchReport.ps1` 다음과 같습니다. 다른 파일을 저장한 폴더에 파일을 저장합니다.

   ```Powershell
   $searchGroup = Read-Host 'Search Group ID'
   $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
   $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
   $allSearchStats = @()
   foreach ($partialObj in $searches)
   {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
   }
   # Calculate the totals
   $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
   # Convert the total size to MB and round to the nearst 100th
   $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
   $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
   # Get the total successful searches and total of all searches
   $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
   $allCount = $allSearchStats.Count
   $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
   # Totals Row
   $totalSearchStats = New-Object PSObject
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
   $allSearchStats += $totalSearchStats
   # Just get the columns we're interested in showing
   $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
   # Print the results to the screen
   $allSearchStatsPrime |ft -AutoSize -Wrap
   # Save the results to a CSV file
   if ($outputFile)
   {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
   }
   ```

2. 복사하고 Windows PowerShell 단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:

   ```Powershell
   .\SearchReport.ps1
   ```

3. 검색 그룹 **ID 프롬프트에** 검색 그룹 이름을 입력한 다음 Enter 키를 누릅니다; **Enter** 예를 들수수합니다. `ContosoCase` 이 이름은 대/소문자를 구분하므로 3단계에서 스크립트를 실행한 것과 같은 방식으로 입력해야 합니다.

4. CSV 파일에 **보고서를 저장할 파일 경로(보고서를** 표시할 때 는 비워 둡니다) 메시지를 CSV 파일에 저장할 경우 전체 파일 이름 경로(.csv 파일 확장명 포함)의 파일 이름을 입력합니다. .csv 파일 확장명을 포함한 CSV 파일의 이름입니다. 예를 들어 현재  `ContosoCaseReport.csv` 디렉터리에 저장하려면 입력하거나 다른 폴더에  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` 저장하도록 입력할 수 있습니다. 또한 메시지를 비워 두면 보고서가 표시되지만 파일에 저장할 수는 없습니다.

5. **Enter** 키를 누릅니다.

   이 스크립트는 검색 만들기 및 실행의 진행률을 표시합니다. 스크립트가 완료되면 보고서가 표시됩니다.

   ![검색 보고서를 실행하여 검색 그룹에 대한 예상 결과 표시](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> 동일한 사서함이나 사이트가 검색 그룹둘 이상의 검색에서 콘텐츠 위치로 지정된 경우 보고서에 예상된 결과,적정 치수(항목 수 및 전체 크기에 대해)에는 동일한 항목에 대한 결과가 포함될 수 있습니다. 같은 전자 메일 메시지 또는 문서가 검색 그룹의 다양한 검색에 대한 쿼리와 일치할 경우 두 번 이상 계산하기 때문입니다.

## <a name="step-5-run-the-script-to-delete-the-searches"></a>5단계: 스크립트를 실행하여 검색 삭제

많은 검색을 만들 수 있기 때문에 마지막 스크립트를 사용하면 3단계에서 만든 검색을 빠르게 삭제하기만 하면 됩니다. 다른 스크립트와 마찬가지로 이 스크립트에서도 검색 그룹 ID를 지정하라는 메시지가 표시됩니다. 이 스크립트를 실행하면 검색 이름의 검색 그룹 ID를 가지한 모든 검색이 삭제됩니다.

1. 파일 이름 확장자 .Windows PowerShell 사용하여 스크립트 파일에 다음 텍스트를 저장합니다. 예를 들면 `DeleteSearches.ps1` 다음과 같습니다. 다른 파일을 저장한 폴더에 파일을 저장합니다.

   ```Powershell
   # Delete all searches in a search group
   $searchGroup = Read-Host 'Search Group ID'
   Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
   }
   ```

2. 복사하고 Windows PowerShell 단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. 검색 **그룹 ID 프롬프트에** 삭제할 검색의 검색 그룹 이름을 입력한 다음 Enter 키를 누릅니다; **Enter** 예를 들면 `ContosoCase` 다음과 같습니다. 이 이름은 대/소문자를 구분하므로 3단계에서 스크립트를 실행한 것과 같은 방식으로 입력해야 합니다.

   스크립트에는 삭제된 각 검색의 이름이 표시됩니다.

   ![검색 그룹에서 검색을 삭제하기 위한 스크립트 실행](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
