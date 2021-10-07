---
title: 여러 콘텐츠 검색 만들기, 보고하기 및 삭제
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
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 보안 및 준수 센터 PowerShell을 사용하여 검색 만들기 및 보고서 실행과 같은 콘텐츠 검색 & 방법을 설명합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 602997114c46a68be13182a504d0b123e98d2be2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172482"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>여러 콘텐츠 검색 만들기, 보고하기 및 삭제

 원본 데이터 및 검색의 풍부함과 품질에 대해 알아보려고 할 때 eDiscovery 및 조사에서 검색 검색을 빠르게 만들고 보고하는 것이 중요한 단계인 경우가 종종 있습니다. 이를 지원하기 위해 Security & Compliance Center PowerShell에서는 시간이 많이 걸리는 콘텐츠 검색 작업을 자동화하는 cmdlet 집합을 제공합니다. 이러한 스크립트를 사용하면 빠르고 쉽게 여러 검색을 만든 다음 예상 검색 결과 보고서를 실행하여 해당 데이터의 양을 결정하는 데 도움이 됩니다. 스크립트를 사용하여 서로 다른 버전의 검색을 만들어 각 검색에서 생성한 결과를 비교할 수도 있습니다. 이러한 스크립트는 데이터를 빠르고 효율적으로 식별하고 선불화하는 데 도움이 될 수 있습니다.

## <a name="before-you-create-a-content-search"></a>콘텐츠 검색을 만들기 전에

- 이 항목에 설명된 스크립트를 실행하기 위해 Microsoft 365 규정 준수 센터 관리자 역할 그룹의 구성원이 되어야 합니다.

- 1단계의 CSV 파일에 추가할 수 있는 조직의 비즈니스용 OneDrive 사이트의 URL 목록을 수집하는 경우 조직의 모든 OneDrive 위치 목록 만들기를 [참조하세요.](/onedrive/list-onedrive-urls)

- 이 항목에서 만든 모든 파일을 동일한 폴더에 저장해야 합니다. 이를 통해 스크립트를 더 쉽게 실행할 수 있습니다.

- 스크립트에는 최소한의 오류 처리가 포함됩니다. 주요 목적은 여러 콘텐츠 검색을 빠르게 만들고 보고하고 삭제하는 것입니다.

- 이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>1단계: 실행할 검색에 대한 정보가 포함된 CSV 파일 만들기

이 단계에서 만드는 CSV(콤보 구분 값) 파일에는 검색할 각 사용자에 대한 행이 포함되어 있습니다. 사용자의 Exchange Online 사서함(사용 가능한 경우 보관 사서함 포함) 및 해당 사용자의 비즈니스용 OneDrive 검색할 수 있습니다. 또는 사서함 또는 사이트만 검색할 비즈니스용 OneDrive 있습니다. 또한 온라인 조직의 모든 사이트를 SharePoint 있습니다. 3단계에서 실행한 스크립트는 CSV 파일의 각 행에 대해 별도의 검색을 생성합니다.

1. 메모장에서 다음 텍스트를 복사하여 .txt 붙여넣습니다. 이 파일을 로컬 컴퓨터의 폴더에 저장합니다. 다른 스크립트도 이 폴더에 저장합니다.

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   파일의 첫 번째 행 또는 헤더 행에는 **New-ComplianceSearch** cmdlet(3단계의 스크립트에서)에서 새 콘텐츠 검색을 만드는 데 사용할 매개 변수가 나열됩니다. 각 매개 변수 이름은 쉼표로 구분됩니다. 머리줄 행에 공백이 없는지 확인 머리줄 행 아래에 있는 각 행은 각 검색에 대한 매개 변수 값을 나타냅니다. CSV 파일의 자리 holder 데이터를 실제 데이터로 바꾸어야 합니다.

2. .txt 파일을 Excel 다음 표의 정보를 사용하여 각 검색에 대한 정보가 들어 있는 파일을 편집합니다.

   ****

   |매개 변수|설명|
   |---|---|
   |`ExchangeLocation`|사용자 사서함의 SMTP 주소입니다.|
   |`SharePointLocation`|조직의 모든 사이트의 비즈니스용 OneDrive 사이트의 URL 또는 사용자의 사이트 URL입니다. 사이트 URL의 비즈니스용 OneDrive 형식을 ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` 사용합니다. . 예:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.|
   |`ContentMatchQuery`|검색에 대한 검색 쿼리입니다. 검색 쿼리를 만드는 데 대한 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건을 참조하세요.](keyword-queries-and-search-conditions.md)|
   |`StartDate`|전자 메일의 경우 받는 사람이 메시지를 받거나 보낸 날짜입니다. 사이트 또는 SharePoint 비즈니스용 OneDrive 문서의 경우 문서를 마지막으로 수정한 날짜 또는 이후의 날짜입니다.|
   |`EndDate`|전자 메일의 경우 사용자가 보낸 메시지를 보낸 날짜 또는 이전 날짜입니다. 사이트 또는 SharePoint 비즈니스용 OneDrive 문서의 경우 문서를 마지막으로 수정한 날짜 또는 이전 날짜입니다.|
   |

3. 로컬 Excel 폴더에 CSV 파일로 저장합니다. 3단계에서 만든 스크립트는 이 CSV 파일의 정보를 사용하여 검색을 생성합니다.

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>2단계: 보안 및 준수 센터 PowerShell에 연결

다음 단계에서는 조직의 보안 및 준수 센터 PowerShell에 연결합니다. 단계별 지침은 [보안 및 준수 센터 PowerShell에 연결하기](/powershell/exchange/connect-to-scc-powershell)를 참조하세요.

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>3단계: 스크립트를 실행하여 검색 만들기 및 시작

이 단계의 스크립트는 1단계에서 만든 CSV 파일의 각 행에 대해 별도의 콘텐츠 검색을 생성합니다. 이 스크립트를 실행하면 다음 두 값을 입력하라는 메시지가 표시될 것입니다.

- **검색 그룹 ID** - 이 이름은 CSV 파일에서 만든 검색을 쉽게 구성할 수 있는 방법을 제공합니다. 만들어진 각 검색의 이름은 검색 그룹 ID를 사용하여 이름이 지정된 다음 검색 이름에 숫자가 추가됩니다. 예를 들어 검색 그룹 ID에 **ContosoCase를** 입력하면 검색 이름이 ContosoCase_1 **,** ContosoCase_2 **,** ContosoCase_3 이름이 지정됩니다.  입력하는 이름은 대소문자 구분됩니다. 4단계 및 5단계에서 검색 그룹 ID를 사용하는 경우 검색 그룹 ID를 만들 때와 동일한 사례를 사용해야 합니다.

- **CSV 파일** - 1단계에서 만든 CSV 파일의 이름입니다. 전체 파일 이름을 사용 하 고 파일 확장명을 포함 .csv 합니다. 예를 들면  `ContosoCase.csv` 입니다.

스크립트를 실행하려면

1. 파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `CreateSearches.ps1` 입니다. 다른 파일을 저장한 폴더에 파일을 저장합니다.

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

2. 이 Windows PowerShell 이전 단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:

   ```Powershell
   .\CreateSearches.ps1
   ```

3. 검색 **그룹 ID** 프롬프트에서 검색 그룹 이름을 입력한 다음 **Enter를 누르고 ;** 예를 들면  `ContosoCase` 입니다. 이 이름은 대소문자 구분이기 때문에 후속 단계에서 동일한 방식으로 입력해야 합니다.

4. 원본 **CSV** 파일 프롬프트에 파일 확장명을 포함하여 CSV 파일의 .csv 입력합니다. 예를 들면  `ContosoCase.csv` 입니다.

5. Enter를 **눌러** 스크립트를 계속 실행합니다.

   스크립트는 검색을 만들고 실행하는 진행률을 표시됩니다. 스크립트가 완료되면 프롬프트로 돌아온 것입니다.

   ![스크립트를 실행하여 여러 준수 검색을 만들 때의 샘플 출력입니다.](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>4단계: 스크립트를 실행하여 검색 예상 결과 보고

검색을 만든 후 다음 단계는 3단계에서 만든 각 검색의 검색 적중 수에 대한 간단한 보고서를 표시하는 스크립트를 실행하는 것입니다. 또한 보고서에는 각 검색에 대한 결과 크기와 총 적중 수 및 모든 검색의 총 크기가 포함됩니다. 보고 스크립트를 실행하면 보고서를 CSV 파일에 저장하려는 경우 검색 그룹 ID와 CSV 파일 이름을 입력하라는 메시지가 표시됩니다.

1. 파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `SearchReport.ps1` 입니다. 다른 파일을 저장한 폴더에 파일을 저장합니다.

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

2. 이 Windows PowerShell 이전 단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:

   ```Powershell
   .\SearchReport.ps1
   ```

3. 검색 **그룹 ID** 프롬프트에서 검색 그룹 이름을 입력한 다음 **Enter를 누르고 ;** 예를 들면  `ContosoCase` 입니다. 이 이름은 대소문자 구분이기 때문에 3단계에서 스크립트를 실행한 때와 동일한 방식으로 입력해야 합니다.

4. 보고서를 **CSV** 파일에 저장하기 위한 파일 경로(보고서를 표시하기만 하려는 경우 비워 두기) 프롬프트에서 보고서를 CSV 파일에 저장하려는 경우 전체 파일 이름 경로(.csv 파일 확장명 포함)를 입력합니다. 파일 확장명을 포함하여 CSV .csv 이름입니다. 예를 들어 현재 디렉터리에 저장하거나 입력하여 다른 폴더에 저장할  `ContosoCaseReport.csv`  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` 수 있습니다. 프롬프트를 비워 두면 보고서를 표시하지만 파일에 저장할 수 없습니다.

5. **Enter** 키를 누릅니다.

   스크립트는 검색을 만들고 실행하는 진행률을 표시됩니다. 스크립트가 완료되면 보고서가 표시됩니다.

   ![검색 보고서를 실행하여 검색 그룹에 대한 예상 정보를 표시합니다.](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> 동일한 사서함 또는 사이트가 검색 그룹에서 둘 이상의 검색에서 콘텐츠 위치로 지정된 경우 보고서의 예상 결과(항목 수와 총 크기 모두)에 동일한 항목에 대한 결과가 포함됩니다. 동일한 전자 메일 메시지 또는 문서가 검색 그룹의 여러 검색에 대한 쿼리와 일치하는 경우 두 번 이상 계산이 되거나 문서가 계산되지 않습니다.

## <a name="step-5-run-the-script-to-delete-the-searches"></a>5단계: 스크립트를 실행하여 검색 삭제

많은 검색을 만들 수 있기 때문에 이 마지막 스크립트를 사용하면 3단계에서 만든 검색을 빠르게 삭제할 수 있습니다. 다른 스크립트와 마찬가지로 이 스크립트는 검색 그룹 ID를 묻는 메시지도 제공합니다. 이 스크립트를 실행하면 검색 이름에 검색 그룹 ID가 있는 모든 검색이 삭제됩니다.

1. 파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `DeleteSearches.ps1` 입니다. 다른 파일을 저장한 폴더에 파일을 저장합니다.

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

2. 이 Windows PowerShell 이전 단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. 검색 **그룹 ID** 프롬프트에서 삭제할 검색에 대한 검색 그룹 이름을 입력한 다음 **Enter를 누르고 ;** 예를 들면  `ContosoCase` 입니다. 이 이름은 대소문자 구분이기 때문에 3단계에서 스크립트를 실행한 때와 동일한 방식으로 입력해야 합니다.

   스크립트는 삭제된 각 검색의 이름을 표시합니다.

   ![스크립트를 실행하여 검색 그룹에서 검색을 삭제합니다.](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
