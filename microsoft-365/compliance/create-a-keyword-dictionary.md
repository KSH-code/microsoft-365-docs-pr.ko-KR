---
title: 키워드 사전 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Office 365 보안 및 준수 센터에서 키워드 사전을 만드는 기본 단계에 대해 알아봅니다.
ms.openlocfilehash: 488e39921f36a6557378a6214269fcb399114972
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921580"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="30650-103">키워드 사전 만들기</span><span class="sxs-lookup"><span data-stu-id="30650-103">Create a keyword dictionary</span></span>

<span data-ttu-id="30650-104">DLP(데이터 손실 방지)는 중요한 항목을 식별, 모니터링 및 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="30650-105">중요한 항목을 식별하려면 키워드를 찾아야 하는 경우가 있으며, 특히 의료 관련 통신과 같은 일반 컨텐츠 또는 부적절하거나 명시적인 언어를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="30650-106">중요한 정보 유형에서 키워드 목록을 만들 수 있지만 키워드 목록은 크기가 제한되어 있으며, 키워드 목록을 만들거나 편집하려면 XML을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="30650-107">키워드 사전은 키워드 관리를 보다 간단하고 훨씬 더 큰 규모로 제공하여 사전에서 최대 1MB의 용어(사후 압축)를 지원하고 모든 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="30650-108">테넌트 제한도 압축 후에 1MB가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30650-108">The tenant limit is also 1MB after compression.</span></span> <span data-ttu-id="30650-109">1MB의 사후 압축 제한은 테넌트 전체에서 결합된 모든 사전에 1백만 문자에 가까운 문자가 있을 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-109">1MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million character.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30650-110">Microsoft 365 Information Protection은 이제 다음에 대해 미리보기 더블 바이트 문자 집합 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-110">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="30650-111">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="30650-111">Chinese (simplified)</span></span>
> - <span data-ttu-id="30650-112">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="30650-112">Chinese (traditional)</span></span>
> - <span data-ttu-id="30650-113">한국어</span><span class="sxs-lookup"><span data-stu-id="30650-113">Korean</span></span>
> - <span data-ttu-id="30650-114">일본어</span><span class="sxs-lookup"><span data-stu-id="30650-114">Japanese</span></span>
>
><span data-ttu-id="30650-115">이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-115">This support is available for sensitive information types.</span></span> <span data-ttu-id="30650-116">자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30650-116">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="30650-117">키워드 사전을 만드는 기본 단계</span><span class="sxs-lookup"><span data-stu-id="30650-117">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="30650-p103">사전의 키워드는 다양한 원본, 서비스 또는 PowerShell cmdlet에서 가져온 파일(예:.csv 또는 .txt 목록)(대부분의 경우), PowerShell cmdlet에 사용자가 직접 입력한 목록 또는 기존 사전에서 가져올 수 있습니다. 키워드 사전을 만들 때 다음과 같은 동일한 핵심 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="30650-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="30650-120">**보안 및 규정 준수 센터**([https://protection.office.com](https://protection.office.com))를 사용하거나 **보안 &amp;준수 센터 PowerShell** 에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-120">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="30650-121">**원하는 원본** 에서 키워드를 정의 하거나 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-121">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="30650-122">마법사와 cmdlet 모두 쉼표로 구분된 키워드 목록을 사용하여 사용자 정의 키워드 사전을 만들 수 있으므로 이 단계는 키워드의 출처에 따라 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="30650-122">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="30650-123">로드되면 가져오기 전에 인코딩 및 바이트 배열로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="30650-123">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="30650-124">**사전을 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="30650-124">**Create your dictionary**.</span></span> <span data-ttu-id="30650-125">이름과 설명을 선택하고 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30650-125">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="30650-126">보안 및 준수 센터를 사용하여 키워드 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30650-126">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="30650-127">다음 단계를 따라 사용자 지정 사전에 대한 키워드를 만들고 가져오세요.</span><span class="sxs-lookup"><span data-stu-id="30650-127">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="30650-128">보안 및 규정 준수 센터([https://protection.office.com](https://protection.office.com))에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-128">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="30650-129">**분류 > 중요한 정보 유형** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-129">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="30650-130">**만들기** 를 선택하고 중요한 정보 유형에 대한 **이름** 및 **설명** 을 입력하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-130">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="30650-131">**요소 추가** 를 선택한 다음 **다음이 포함된 내용 감지** 드롭다운에서 **사전(광범위한 키워드)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-131">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="30650-132">**사전 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-132">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="30650-133">검색 컨트롤에서 **여기에서 새 키워드 사전을 만들 수 있음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-133">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="30650-134">사용자 지정 사전에 대한 **이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-134">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="30650-135">**가져오기** 를 선택하고 키워드 파일 종류에 따라 **텍스트 파일에서** 또는 **csv 파일에서** 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-135">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="30650-136">파일 대화 상자에서 로컬 PC 또는 네트워크 파일 공유에 있는 키워드 파일을 선택한 다음 **열기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-136">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="30650-137">**저장** 을 선택한 다음 **키워드 사전** 목록에서 사용자 지정 사전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-137">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="30650-138">**추가** 를 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-138">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="30650-139">중요한 정보 유형 선택 사항을 검토 및 완료한 다음 **완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-139">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="30650-140">PowerShell을 사용하여 파일에서 키워드 사전 만들기</span><span class="sxs-lookup"><span data-stu-id="30650-140">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="30650-141">대형 사전을 작성해야 하는 경우 파일 또는 다른 원본에서 내보낸 목록의 키워드를 사용하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-141">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="30650-142">이 경우 외부 전자 메일에서 표시하기에 부적절한 언어 목록이 포함된 키워드 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30650-142">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="30650-143">먼저 [보안 &amp; 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-143">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="30650-144">키워드를 텍스트 파일에 복사합니다. 이때 각 키워드를 별도 줄에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-144">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="30650-p107">텍스트 파일을 유니코드 인코딩으로 저장합니다. 메모장에서 \> **다른 이름으로 저장** \> **인코딩으로** \> **유니코드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="30650-147">다음 cmdlet을 실행하여 파일을 변수로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-147">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="30650-148">다음 cmdlet을 실행하여 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30650-148">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="30650-149">기존 키워드 사전 수정</span><span class="sxs-lookup"><span data-stu-id="30650-149">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="30650-150">키워드 사전 중 하나에 있는 키워드를 수정하거나 기본 제공 사전 중 하나에서 키워드를 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-150">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="30650-151">현재는 PowerShell을 사용한 사용자 지정 사전 업데이트만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-151">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="30650-152">예를 들어 PowerShell에서 일부 용어를 수정하고, 용어를 수정할 수 있는 위치에 로컬로 저장한 다음 이전 용어를 제자리에 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-152">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="30650-153">먼저 사전 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-153">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="30650-154">`$dict`을(를) 인쇄하면 다양한 변수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="30650-154">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="30650-155">키워드 자체는 백엔드의 개체에 저장되지만 `$dict.KeywordDictionary`에는 키워드에 대한 문자열 표현이 포함되어 있어 사전을 수정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30650-155">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="30650-156">사전을 수정하기 전에 `.split(',')` 방법을 사용하여 용어 문자열을 어레이로 다시 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-156">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="30650-157">그런 다음 `.trim()` 메서드를 사용하여 키워드 사이의 원치 않는 공백을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-157">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="30650-p111">이제 사전에서 몇 가지 용어를 제거해봅니다. 예제 사전에는 키워드가 몇 개만 포함되어 있으므로 사전을 내보내고 메모장에서 편집하는 과정으로 쉽게 건너뛸 수 있습니다. 그렇지만 사전에는 많은 용어가 들어 있는 것이 일반적이므로 먼저 이 방법을 배워 PowerShell에서 쉽게 편집할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="30650-p112">마지막 단계에서는 키워드를 배열로 저장했습니다. [배열에서 항목을 제거](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))하는 방법에는 여러 가지가 있지만 사전에서 제거하려는 용어의 배열을 만든 후 용어 목록에 없는 사전 용어만 복사하여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="30650-p113">명령 `$terms`를 실행하여 현재 용어 목록을 표시합니다. 명령 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

<span data-ttu-id="30650-164">다음 명령을 실행하여 제거하려는 용어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-164">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="30650-165">목록에서 용어를 실제로 제거하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-165">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="30650-p114">명령 `$updatedTerms`를 실행하여 업데이트된 용어 목록을 표시합니다. 명령 출력은 다음과 같습니다(지정된 용어가 제거됨).</span><span class="sxs-lookup"><span data-stu-id="30650-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="30650-p115">이제 파일을 열고 영어를 더 추가한 후 유니코드 인코딩(UTF-16)으로 저장하면 됩니다. 업데이트된 용어를 업로드하고 사전을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="30650-p116">이제 사전이 제대로 업데이트되었습니다. `Identity` 필드 에는 사전의 이름이 표시됩니다. `set-` cmdlet을 사용하여 사전 이름도 변경하려면 위 명령에서 새 사전 이름과 함께 `-Name` 매개 변수만 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30650-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="30650-173">사용자 지정 중요한 정보 유형과 DLP 정책에서 키워드 사전 사용</span><span class="sxs-lookup"><span data-stu-id="30650-173">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="30650-174">키워드 사전은 사용자 정의 중요한 정보 유형에 대한 일치 요구 사항의 일부로 사용하거나 중요한 정보 유형 자체로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-174">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="30650-175">둘 다 [사용자 지정 중요한 정보 유형](create-a-custom-sensitive-information-type-in-scc-powershell.md)을(를) 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-175">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="30650-176">링크된 문서의 지침에 따라 중요한 정보 유형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30650-176">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="30650-177">XML을 사용하게 되면 사전에 사용할 GUID 식별자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-177">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="30650-178">사전의 ID를 확인하려면 다음 명령을 실행하고 **Identity** 속성 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="30650-178">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="30650-179">이 명령의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-179">The output of the command looks like this:</span></span>
  
<span data-ttu-id="30650-180">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="30650-180">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="30650-p118">사용자 지정 중요한 정보 유형의 XML에 ID를 붙여넣은 후 업로드합니다. 이제 사전이 중요한 정보 유형 목록에 표시되므로 일치시킬 키워드 수를 지정하여 정책에서 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30650-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```
