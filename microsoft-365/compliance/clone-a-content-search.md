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
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: 이 문서의 PowerShell 스크립트를 사용하여 Office 365 또는 Microsoft 365의 준수 센터에서 기존 콘텐츠 검색을 빠르게 복제할 수 있습니다.
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918064"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="bc951-103">콘텐츠 검색 복제</span><span class="sxs-lookup"><span data-stu-id="bc951-103">Clone a Content Search</span></span>

<span data-ttu-id="bc951-104">Office 365 또는 Microsoft 365의 준수 센터에서 많은 사서함 또는 SharePoint 및 비즈니스용 OneDrive 사이트를 검색하는 콘텐츠 검색을 만드는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="bc951-105">URL을 잘못 입력한 경우 검색할 사이트를 지정하면 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="bc951-106">이러한 문제를 방지하기 위해 이 문서의 Windows PowerShell 스크립트를 사용하여 기존 콘텐츠 검색을 빠르게 복제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="bc951-107">검색을 복제하면 원래 검색과 동일한 속성(예: 콘텐츠 위치 및 검색 쿼리)이 포함된 새 검색이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="bc951-108">그런 다음 키워드 쿼리 또는 날짜 범위를 변경하여 새 검색을 편집하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="bc951-109">콘텐츠 검색을 복제하는 이유</span><span class="sxs-lookup"><span data-stu-id="bc951-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="bc951-110">서로 다른 키워드 검색 쿼리의 결과를 비교하기 위해 동일한 콘텐츠 위치에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="bc951-111">새 검색을 만들 때 많은 수의 콘텐츠 위치를 다시 입력하지 않고도 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="bc951-112">검색 결과의 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-112">To decrease the size of the search results.</span></span> <span data-ttu-id="bc951-113">예를 들어 내보낼 결과가 너무 많은 검색이 있는 경우 검색을 복제한 다음 날짜 범위에 따라 검색 조건을 추가하여 검색 결과 수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="bc951-114">스크립트 정보</span><span class="sxs-lookup"><span data-stu-id="bc951-114">Script information</span></span>

- <span data-ttu-id="bc951-115">이 항목에 설명된 스크립트를 실행하기 위해 Security & Compliance Center에서 eDiscovery 관리자 역할 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="bc951-116">스크립트에는 최소한의 오류 처리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-116">The script includes minimal error handling.</span></span> <span data-ttu-id="bc951-117">스크립트의 기본 목적은 콘텐츠 검색을 빠르게 복제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="bc951-118">스크립트는 새 콘텐츠 검색을 생성하지만 시작하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="bc951-119">이 스크립트는 복제하는 콘텐츠 검색이 eDiscovery 사례와 연결되어 있는지 여부를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="bc951-120">검색이 사례와 연결된 경우 새 검색도 동일한 사례와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="bc951-121">기존 검색이 사례와 연결되지 않은 경우 새 검색이 준수  센터의 콘텐츠 검색 페이지에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="bc951-122">이 항목에서 제공하는 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="bc951-123">샘플 스크립트는 어떤 종류의 보증도 없이 그대로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="bc951-124">또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="bc951-125">샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="bc951-126">어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="bc951-127">1단계: 스크립트를 실행하여 검색 복제</span><span class="sxs-lookup"><span data-stu-id="bc951-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="bc951-128">이 단계의 스크립트는 기존 콘텐츠 검색을 복제하여 새 콘텐츠 검색을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="bc951-129">이 스크립트를 실행하면 다음 정보를 입력하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="bc951-130">**사용자 자격 증명** - 스크립트는 자격 증명을 사용하여 조직의 보안 & 준수 센터에 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc951-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="bc951-131">앞서 설명한 것 처럼 스크립트를 실행하기 위해 Security & Compliance Center에서 eDiscovery 관리자 역할 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="bc951-132">**기존 검색의 이름** - 복제하려는 콘텐츠 검색입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="bc951-133">**만들 새** 검색의 이름 - 이 값을 비워 두면 스크립트는 복제할 검색의 이름을 기반으로 하는 새 검색의 이름을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="bc951-134">검색을 복제하는 경우:</span><span class="sxs-lookup"><span data-stu-id="bc951-134">To clone a search:</span></span>
  
1. <span data-ttu-id="bc951-135">파일 이름 접미사 .ps1을 Windows PowerShell 스크립트 파일에 다음 텍스트를 저장합니다. 예를 들면 `CloneSearch.ps1` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="bc951-136">Windows PowerShell 열고 스크립트를 저장한 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="bc951-137">스크립트를 실행합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bc951-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="bc951-138">자격 증명을 입력하라는 메시지가 표시될 때 전자 메일 주소와 암호를 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc951-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="bc951-139">스크립트에서 메시지가 표시될 때 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="bc951-140">각 정보를 입력한 다음 Enter를 **누르고 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc951-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="bc951-141">기존 검색의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="bc951-142">새 검색의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-142">The name of the new search.</span></span>
    
    <span data-ttu-id="bc951-143">스크립트는 새 콘텐츠 검색을 생성하지만 시작하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="bc951-144">이렇게 하면 다음 단계에서 검색을 편집하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="bc951-145">새 검색이 사례와 연결되는지 여부에 따라 **Get-ComplianceSearch** cmdlet을 실행하거나 준수 센터의 콘텐츠 검색 또는 **eDiscovery** 페이지로 이동하여 새 검색의 속성을 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="bc951-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="bc951-146">2단계: 준수 센터에서 복제된 검색 편집 및 실행</span><span class="sxs-lookup"><span data-stu-id="bc951-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="bc951-147">스크립트를 실행하여 기존 콘텐츠 검색을 복제한 후 다음 단계는 준수 센터로 이동하여 새 검색을 편집하고 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="bc951-148">앞서 언급했듯이 키워드 검색 쿼리를 변경하고 검색 조건을 추가하거나 제거하여 검색을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="bc951-149">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc951-149">For more information, see:</span></span>
  
- [<span data-ttu-id="bc951-150">Office 365의 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="bc951-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="bc951-151">콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건</span><span class="sxs-lookup"><span data-stu-id="bc951-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="bc951-152">eDiscovery 사례</span><span class="sxs-lookup"><span data-stu-id="bc951-152">eDiscovery cases</span></span>](./get-started-core-ediscovery.md)