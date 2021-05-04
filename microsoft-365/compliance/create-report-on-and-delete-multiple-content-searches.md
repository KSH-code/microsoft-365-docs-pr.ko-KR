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
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 검색을 만들고 PowerShell 스크립트를 통해 보고서 실행과 같은 콘텐츠 검색 작업을 자동화하는 방법을 & 준수 센터에서 Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6155a0bf411cc83fd58291efe7797e7f68370708
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994965"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="1c454-103">여러 콘텐츠 검색 만들기, 보고하기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="1c454-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="1c454-104">원본 데이터 및 검색의 풍부함과 품질에 대해 알아보려고 할 때 eDiscovery 및 조사에서 검색 검색을 빠르게 만들고 보고하는 것이 중요한 단계인 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="1c454-105">이를 위해 Security & Compliance Center PowerShell에서는 시간이 많이 걸리는 콘텐츠 검색 작업을 자동화하는 cmdlet 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="1c454-106">이러한 스크립트를 사용하면 빠르고 쉽게 여러 검색을 만든 다음 예상 검색 결과 보고서를 실행하여 해당 데이터의 양을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="1c454-107">스크립트를 사용하여 서로 다른 버전의 검색을 만들어 각 검색에서 생성한 결과를 비교할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="1c454-108">이러한 스크립트는 데이터를 빠르고 효율적으로 식별하고 선불화하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="1c454-109">콘텐츠 검색을 만들기 전에</span><span class="sxs-lookup"><span data-stu-id="1c454-109">Before you create a Content Search</span></span>

- <span data-ttu-id="1c454-110">이 항목에 설명된 스크립트를 실행하기 위해 Security & Compliance Center에서 eDiscovery 관리자 역할 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="1c454-111">1단계의 CSV 파일에 추가할 수 있는 조직의 비즈니스용 OneDrive 사이트의 URL 목록을 수집하는 경우 조직의 모든 OneDrive 위치 목록 만들기를 [참조하세요.](/onedrive/list-onedrive-urls)</span><span class="sxs-lookup"><span data-stu-id="1c454-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="1c454-112">이 항목에서 만든 모든 파일을 동일한 폴더에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="1c454-113">이를 통해 스크립트를 더 쉽게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="1c454-114">스크립트에는 최소한의 오류 처리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="1c454-115">주요 목적은 여러 콘텐츠 검색을 빠르게 만들고 보고하고 삭제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="1c454-p104">이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="1c454-121">1단계: 실행할 검색에 대한 정보가 포함된 CSV 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="1c454-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="1c454-122">이 단계에서 만드는 CSV(콤보 구분 값) 파일에는 검색할 각 사용자에 대한 행이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="1c454-123">사용자의 Exchange Online 사서함(사용 가능한 경우 보관 사서함 포함) 및 해당 사용자의 비즈니스용 OneDrive 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="1c454-124">또는 사서함 또는 사이트만 검색할 비즈니스용 OneDrive 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="1c454-125">또한 온라인 조직의 모든 사이트를 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="1c454-126">3단계에서 실행한 스크립트는 CSV 파일의 각 행에 대해 별도의 검색을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="1c454-127">메모장에서 다음 텍스트를 복사하여 .txt 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="1c454-128">이 파일을 로컬 컴퓨터의 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="1c454-129">다른 스크립트도 이 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="1c454-130">파일의 첫 번째 행 또는 헤더 행에는 **New-ComplianceSearch** cmdlet(3단계의 스크립트에서)에서 새 콘텐츠 검색을 만드는 데 사용할 매개 변수가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="1c454-131">각 매개 변수 이름은 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="1c454-132">머리줄 행에 공백이 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="1c454-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="1c454-133">머리줄 행 아래에 있는 각 행은 각 검색에 대한 매개 변수 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="1c454-134">CSV 파일의 자리 holder 데이터를 실제 데이터로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="1c454-135">.txt 파일을 Excel 다음 표의 정보를 사용하여 각 검색에 대한 정보가 들어 있는 파일을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="1c454-136">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c454-136">Parameter</span></span>|<span data-ttu-id="1c454-137">설명</span><span class="sxs-lookup"><span data-stu-id="1c454-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="1c454-138">사용자 사서함의 SMTP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="1c454-139">조직의 모든 사이트의 비즈니스용 OneDrive 사이트의 URL 또는 사용자의 사이트 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="1c454-140">사이트 URL의 비즈니스용 OneDrive 형식을 ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` 사용합니다. .</span><span class="sxs-lookup"><span data-stu-id="1c454-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="1c454-141">예:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span><span class="sxs-lookup"><span data-stu-id="1c454-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="1c454-142">검색에 대한 검색 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-142">The search query for the search.</span></span> <span data-ttu-id="1c454-143">검색 쿼리를 만드는 데 대한 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건을 참조하세요.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="1c454-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="1c454-144">전자 메일의 경우 받는 사람이 메시지를 받거나 보낸 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="1c454-145">사이트 또는 SharePoint 비즈니스용 OneDrive 문서의 경우 문서를 마지막으로 수정한 날짜 또는 이후의 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="1c454-146">전자 메일의 경우 사용자가 보낸 메시지를 보낸 날짜 또는 이전 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="1c454-147">사이트 또는 SharePoint 비즈니스용 OneDrive 문서의 경우 문서를 마지막으로 수정한 날짜 또는 이전 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="1c454-148">로컬 Excel 폴더에 CSV 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="1c454-149">3단계에서 만든 스크립트는 이 CSV 파일의 정보를 사용하여 검색을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="1c454-150">2단계: 보안 및 준수 센터 PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="1c454-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="1c454-151">다음 단계에서는 조직의 보안 및 준수 센터 PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="1c454-152">단계별 지침은 [보안 및 준수 센터 PowerShell에 연결하기](/powershell/exchange/connect-to-scc-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c454-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="1c454-153">3단계: 스크립트를 실행하여 검색 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="1c454-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="1c454-154">이 단계의 스크립트는 1단계에서 만든 CSV 파일의 각 행에 대해 별도의 콘텐츠 검색을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="1c454-155">이 스크립트를 실행하면 다음 두 값을 입력하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="1c454-156">**검색 그룹 ID** - 이 이름은 CSV 파일에서 만든 검색을 쉽게 구성할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="1c454-157">만들어진 각 검색의 이름은 검색 그룹 ID를 사용하여 이름이 지정된 다음 검색 이름에 숫자가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="1c454-158">예를 들어 검색 그룹 ID에 **ContosoCase를** 입력하면 검색 이름이 ContosoCase_1 **,** ContosoCase_2 **,** ContosoCase_3 이름이 지정됩니다. </span><span class="sxs-lookup"><span data-stu-id="1c454-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="1c454-159">입력하는 이름은 대소문자 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="1c454-160">4단계 및 5단계에서 검색 그룹 ID를 사용하는 경우 검색 그룹 ID를 만들 때와 동일한 사례를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="1c454-161">**CSV 파일** - 1단계에서 만든 CSV 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="1c454-162">전체 파일 이름을 사용 하 고 파일 확장명을 포함 .csv 합니다. 예를 들면  `ContosoCase.csv` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="1c454-163">스크립트를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1c454-163">To run the script:</span></span>

1. <span data-ttu-id="1c454-164">파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `CreateSearches.ps1` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="1c454-165">다른 파일을 저장한 폴더에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-165">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="1c454-166">이 Windows PowerShell 이전 단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="1c454-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="1c454-167">검색 **그룹 ID** 프롬프트에서 검색 그룹 이름을 입력한 다음 **Enter를 누르고 ;** 예를 들면  `ContosoCase` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="1c454-168">이 이름은 대소문자 구분이기 때문에 후속 단계에서 동일한 방식으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="1c454-169">원본 **CSV** 파일 프롬프트에 파일 확장명을 포함하여 CSV 파일의 .csv 입력합니다. 예를 들면  `ContosoCase.csv` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="1c454-170">Enter를 **눌러** 스크립트를 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="1c454-171">스크립트는 검색을 만들고 실행하는 진행률을 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="1c454-172">스크립트가 완료되면 프롬프트로 돌아온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-172">When the script is complete, it returns to the prompt.</span></span>

   ![여러 규정 준수 검색을 만드는 스크립트를 실행한 경우의 샘플 출력](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="1c454-174">4단계: 스크립트를 실행하여 검색 예상 결과 보고</span><span class="sxs-lookup"><span data-stu-id="1c454-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="1c454-175">검색을 만든 후 다음 단계는 3단계에서 만든 각 검색의 검색 적중 수에 대한 간단한 보고서를 표시하는 스크립트를 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="1c454-176">또한 보고서에는 각 검색에 대한 결과 크기와 총 적중 수 및 모든 검색의 총 크기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="1c454-177">보고 스크립트를 실행하면 보고서를 CSV 파일에 저장하려는 경우 검색 그룹 ID와 CSV 파일 이름을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="1c454-178">파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `SearchReport.ps1` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="1c454-179">다른 파일을 저장한 폴더에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-179">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="1c454-180">이 Windows PowerShell 이전 단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="1c454-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="1c454-181">검색 **그룹 ID** 프롬프트에서 검색 그룹 이름을 입력한 다음 **Enter를 누르고 ;** 예를 들면  `ContosoCase` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="1c454-182">이 이름은 대소문자 구분이기 때문에 3단계에서 스크립트를 실행한 때와 동일한 방식으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="1c454-183">보고서를 **CSV** 파일에 저장하기 위한 파일 경로(보고서를 표시하기만 하려는 경우 비워 두기) 프롬프트에서 보고서를 CSV 파일에 저장하려는 경우 전체 파일 이름 경로(.csv 파일 확장명 포함)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="1c454-184">파일 확장명을 포함하여 CSV .csv 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="1c454-185">예를 들어 현재 디렉터리에 저장하거나 입력하여 다른 폴더에 저장할  `ContosoCaseReport.csv`  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="1c454-186">프롬프트를 비워 두면 보고서를 표시하지만 파일에 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="1c454-187">**Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-187">Press **Enter**.</span></span>

   <span data-ttu-id="1c454-188">스크립트는 검색을 만들고 실행하는 진행률을 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="1c454-189">스크립트가 완료되면 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-189">When the script is complete, the report is displayed.</span></span>

   ![검색 보고서를 실행하여 검색 그룹에 대한 예상 결과 표시](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="1c454-191">동일한 사서함 또는 사이트가 검색 그룹에서 둘 이상의 검색에서 콘텐츠 위치로 지정된 경우 보고서의 예상 결과(항목 수와 총 크기 모두)에 동일한 항목에 대한 결과가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="1c454-192">동일한 전자 메일 메시지 또는 문서가 검색 그룹의 여러 검색에 대한 쿼리와 일치하는 경우 두 번 이상 계산이 되거나 문서가 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="1c454-193">5단계: 스크립트를 실행하여 검색 삭제</span><span class="sxs-lookup"><span data-stu-id="1c454-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="1c454-194">많은 검색을 만들 수 있기 때문에 이 마지막 스크립트를 사용하면 3단계에서 만든 검색을 빠르게 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="1c454-195">다른 스크립트와 마찬가지로 이 스크립트는 검색 그룹 ID를 묻는 메시지도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="1c454-196">이 스크립트를 실행하면 검색 이름에 검색 그룹 ID가 있는 모든 검색이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="1c454-197">파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 .ps1. 예를 들면 `DeleteSearches.ps1` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="1c454-198">다른 파일을 저장한 폴더에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-198">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="1c454-199">이 Windows PowerShell 이전 단계에서 스크립트를 저장한 폴더로 이동한 다음 스크립트를 실행합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="1c454-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="1c454-200">검색 **그룹 ID** 프롬프트에서 삭제할 검색에 대한 검색 그룹 이름을 입력한 다음 **Enter를 누르고 ;** 예를 들면  `ContosoCase` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="1c454-201">이 이름은 대소문자 구분이기 때문에 3단계에서 스크립트를 실행한 때와 동일한 방식으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="1c454-202">스크립트는 삭제된 각 검색의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c454-202">The script displays the name of each search that's deleted.</span></span>

   ![검색 그룹에서 검색을 삭제하기 위한 스크립트 실행](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
