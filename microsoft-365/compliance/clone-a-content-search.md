---
title: 콘텐츠 검색 복제
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: 이 문서의 PowerShell 스크립트를 사용하여 규정 준수 센터의 기존 콘텐츠 검색을 Office 365 Microsoft 365.
ms.openlocfilehash: 763bd6ac49841e5b55bbbc187631ef74426d9d0a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153213"
---
# <a name="clone-a-content-search"></a>콘텐츠 검색 복제

많은 사서함 또는 Office 365 및 Microsoft 365 검색하는 Office 365 또는 SharePoint 비즈니스용 OneDrive 센터에서 콘텐츠 검색을 만드는 데 시간이 걸릴 수 있습니다. URL을 잘못 입력한 경우 검색할 사이트를 지정하면 오류가 발생할 수 있습니다. 이러한 문제를 방지하기 위해 이 문서의 Windows PowerShell 스크립트를 사용하여 기존 콘텐츠 검색을 빠르게 복제할 수 있습니다. 검색을 복제하면 원래 검색과 동일한 속성(예: 콘텐츠 위치 및 검색 쿼리)이 포함된 새 검색이 만들어집니다. 그런 다음 키워드 쿼리 또는 날짜 범위를 변경하여 새 검색을 편집하고 실행할 수 있습니다.
  
콘텐츠 검색을 복제하는 이유
  
- 서로 다른 키워드 검색 쿼리의 결과를 비교하기 위해 동일한 콘텐츠 위치에서 실행됩니다.
    
- 새 검색을 만들 때 많은 수의 콘텐츠 위치를 다시 입력하지 않고도 시간을 절약할 수 있습니다.
    
- 검색 결과의 크기를 줄입니다. 예를 들어 내보낼 결과가 너무 많은 검색이 있는 경우 검색을 복제한 다음 날짜 범위에 따라 검색 조건을 추가하여 검색 결과 수를 줄일 수 있습니다.
  
## <a name="script-information"></a>스크립트 정보

- 이 항목에 설명된 스크립트를 실행하기 위해 Microsoft 365 규정 준수 센터 관리자 역할 그룹의 구성원이 되어야 합니다.
    
- 스크립트에는 최소한의 오류 처리가 포함됩니다. 스크립트의 기본 목적은 콘텐츠 검색을 빠르게 복제하는 것입니다.
    
- 스크립트는 새 콘텐츠 검색을 생성하지만 시작하지는 않습니다.
    
- 이 스크립트는 복제하는 콘텐츠 검색이 eDiscovery 사례와 연결되어 있는지 여부를 고려합니다. 검색이 사례와 연결된 경우 새 검색도 동일한 사례와 연결됩니다. 기존 검색이 사례와 연결되지 않은 경우 새 검색이 준수  센터의 콘텐츠 검색 페이지에 나열됩니다. 
    
- 이 항목에서 제공하는 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다. 샘플 스크립트는 어떤 종류의 보증도 없이 그대로 제공됩니다. 또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>1단계: 스크립트를 실행하여 검색 복제

이 단계의 스크립트는 기존 콘텐츠 검색을 복제하여 새 콘텐츠 검색을 생성합니다. 이 스크립트를 실행하면 다음 정보를 입력하라는 메시지가 표시될 것입니다.
  
- **사용자 자격 증명** - 스크립트는 자격 증명을 사용하여 보안 및 준수 & PowerShell에 연결합니다. 앞서 설명한 것 처럼 스크립트를 실행하기 위해 Security & Compliance Center에서 eDiscovery 관리자 역할 그룹의 구성원이 되어야 합니다. 
    
- **기존 검색의 이름** - 복제하려는 콘텐츠 검색입니다. 
    
- **만들 새** 검색의 이름 - 이 값을 비워 두면 스크립트는 복제할 검색의 이름을 기반으로 하는 새 검색의 이름을 생성합니다. 
    
검색을 복제하는 경우:
  
1. 파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `CloneSearch.ps1` 입니다.
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. Windows PowerShell 열고 스크립트를 저장한 폴더로 이동합니다.
    
3. 스크립트를 실행합니다. 예를 들어:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. 자격 증명을 입력하라는 메시지가 표시될 때 전자 메일 주소와 암호를 입력한 다음 확인을 **클릭합니다.**
    
5. 스크립트에서 메시지가 표시될 때 다음 정보를 입력합니다. 각 정보를 입력한 다음 Enter를 **누르고 를 입력합니다.**
    
    - 기존 검색의 이름입니다.
    
    - 새 검색의 이름입니다.
    
    스크립트는 새 콘텐츠 검색을 생성하지만 시작하지는 않습니다. 이렇게 하면 다음 단계에서 검색을 편집하고 실행할 수 있습니다. 새 검색이 사례와 연결되는지 여부에 따라 **Get-ComplianceSearch** cmdlet을 실행하거나 준수 센터의 콘텐츠 검색 또는 **eDiscovery** 페이지로 이동하여 새 검색의 속성을 볼 수 있습니다.  
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>2단계: 준수 센터에서 복제된 검색 편집 및 실행

스크립트를 실행하여 기존 콘텐츠 검색을 복제한 후 다음 단계는 준수 센터로 이동하여 새 검색을 편집하고 실행하는 것입니다. 앞서 언급했듯이 키워드 검색 쿼리를 변경하고 검색 조건을 추가하거나 제거하여 검색을 편집할 수 있습니다. 자세한 내용은 다음을 참조하세요.
  
- [Office 365의 콘텐츠 검색](content-search.md)
    
- [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)
    
- [eDiscovery 사례](./get-started-core-ediscovery.md)