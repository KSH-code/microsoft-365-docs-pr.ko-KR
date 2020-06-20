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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Office 365 보안 & 준수 센터에서 키워드 사전을 만드는 기본 단계를 알아봅니다.
ms.openlocfilehash: 38a92aaf7e72ab79243c547ff48fa156e26b6ee6
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818057"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="29c1c-103">키워드 사전 만들기</span><span class="sxs-lookup"><span data-stu-id="29c1c-103">Create a keyword dictionary</span></span>

<span data-ttu-id="29c1c-104">DLP (데이터 손실 방지)는 중요 한 정보를 식별, 모니터링 및 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive information.</span></span> <span data-ttu-id="29c1c-105">중요 한 정보 식별 간혹 키워드를 찾으려는 경우, 특히 일반 콘텐츠 (예: 의료 관련 통신)를 식별 하거나 부적절 한 언어나 명시적 언어를 사용 해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-105">Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="29c1c-106">키워드 목록은 중요 한 정보 유형으로 만들 수 있지만 키워드 목록은 크기를 제한 하며 XML을 수정 하 여 만들거나 편집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="29c1c-107">키워드 사전은 보다 간단 하 게 키워드를 관리할 수 있도록 하 여 사전 당 최대 10만 용어를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="29c1c-108">키워드 사전을 만드는 기본 단계</span><span class="sxs-lookup"><span data-stu-id="29c1c-108">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="29c1c-109">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary.</span><span class="sxs-lookup"><span data-stu-id="29c1c-109">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary.</span></span> <span data-ttu-id="29c1c-110">When you create a keyword dictionary, you follow the same core steps:</span><span class="sxs-lookup"><span data-stu-id="29c1c-110">When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="29c1c-111">**보안 & 준수 센터** ()를 사용 [https://protection.office.com](https://protection.office.com) 하거나 보안 및 \*\* &amp; 준수 센터 PowerShell\*\*에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-111">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="29c1c-112">**원하는 원본에서 키워드를 정의 하거나 로드**합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-112">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="29c1c-113">마법사와 cmdlet은 모두 쉼표로 구분 된 키워드 목록을 사용 하 여 사용자 지정 키워드 사전을 만들기 때문에이 단계는 키워드의 출처에 따라 약간씩 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-113">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="29c1c-114">일단 로드되고 나면 가져오기 전에 인코딩되어 바이트 배열로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-114">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="29c1c-115">**사전을 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="29c1c-115">**Create your dictionary**.</span></span> <span data-ttu-id="29c1c-116">이름 및 설명을 선택 하 고 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-116">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="29c1c-117">보안 & 준수 센터를 사용 하 여 키워드 사전 만들기</span><span class="sxs-lookup"><span data-stu-id="29c1c-117">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="29c1c-118">다음 단계를 따라 사용자 지정 사전에 대한 키워드를 만들고 가져오세요.</span><span class="sxs-lookup"><span data-stu-id="29c1c-118">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="29c1c-119">보안 & 준수 센터 ()에 연결 합니다 [https://protection.office.com](https://protection.office.com) .</span><span class="sxs-lookup"><span data-stu-id="29c1c-119">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="29c1c-120">**분류 > 중요한 정보 유형**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-120">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="29c1c-121">**만들기**를 선택하고 중요한 정보 유형에 대한 **이름** 및 **설명**을 입력하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-121">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="29c1c-122">**요소 추가**를 선택한 다음 **다음이 포함된 내용 감지** 드롭다운에서 **사전(광범위한 키워드)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-122">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="29c1c-123">**사전 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-123">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="29c1c-124">검색 컨트롤에서 **여기에서 새 키워드 사전을 만들 수 있음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-124">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="29c1c-125">사용자 지정 사전에 대한 **이름**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-125">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="29c1c-126">**가져오기**를 선택하고 키워드 파일 종류에 따라 **텍스트 파일에서** 또는 **csv 파일에서** 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-126">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="29c1c-127">파일 대화 상자에서 로컬 PC 또는 네트워크 파일 공유에 있는 키워드 파일을 선택한 다음 **열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-127">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="29c1c-128">**저장**을 선택한 다음 **키워드 사전** 목록에서 사용자 지정 사전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-128">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="29c1c-129">**추가**를 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-129">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="29c1c-130">중요한 정보 유형 선택 사항을 검토 및 완료한 다음 **완료**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-130">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="29c1c-131">PowerShell을 사용하여 파일에서 키워드 사전 만들기</span><span class="sxs-lookup"><span data-stu-id="29c1c-131">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="29c1c-132">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span><span class="sxs-lookup"><span data-stu-id="29c1c-132">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="29c1c-133">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span><span class="sxs-lookup"><span data-stu-id="29c1c-133">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="29c1c-134">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="29c1c-134">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="29c1c-135">키워드를 텍스트 파일에 복사합니다. 이때 각 키워드를 별도 줄에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-135">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="29c1c-136">Save the text file with Unicode encoding.</span><span class="sxs-lookup"><span data-stu-id="29c1c-136">Save the text file with Unicode encoding.</span></span> <span data-ttu-id="29c1c-137">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="29c1c-137">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="29c1c-138">다음 cmdlet을 실행하여 파일을 변수로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-138">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="29c1c-139">다음 cmdlet을 실행하여 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-139">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="29c1c-140">기존 키워드 사전 수정</span><span class="sxs-lookup"><span data-stu-id="29c1c-140">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="29c1c-141">키워드 사전 중 하나에 있는 키워드를 수정하거나 기본 제공 사전 중 하나에서 키워드를 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-141">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="29c1c-142">현재는 PowerShell을 사용한 사용자 지정 사전 업데이트만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-142">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="29c1c-143">예를 들어 PowerShell에서 몇 가지 용어를 수정 하 고,이 용어를 로컬로 저장 한 후 편집기에서 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-143">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="29c1c-144">먼저 사전 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-144">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="29c1c-145">인쇄 `$dict` 시 다양 한 변수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-145">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="29c1c-146">키워드 자체는 백 엔드에서 개체에 저장 되지만 `$dict.KeywordDictionary` 사전을 수정 하는 데 사용할 수 있는 문자열 표현이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-146">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="29c1c-147">사전을 수정 하려면 메서드를 사용 하 여 용어 문자열을 다시 배열로 변환 해야 합니다 `.split(',')` .</span><span class="sxs-lookup"><span data-stu-id="29c1c-147">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="29c1c-148">그런 다음 메서드를 사용 하 여 키워드와 함께 사용 하는 불필요 한 공백을 정리 하 여 `.trim()` 사용할 키워드만 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-148">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="29c1c-149">Now you'll remove some terms from the dictionary.</span><span class="sxs-lookup"><span data-stu-id="29c1c-149">Now you'll remove some terms from the dictionary.</span></span> <span data-ttu-id="29c1c-150">Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29c1c-150">Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="29c1c-151">In the last step, you saved the keywords to an array.</span><span class="sxs-lookup"><span data-stu-id="29c1c-151">In the last step, you saved the keywords to an array.</span></span> <span data-ttu-id="29c1c-152">There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span><span class="sxs-lookup"><span data-stu-id="29c1c-152">There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="29c1c-153">Run the command  `$terms` to show the current list of terms.</span><span class="sxs-lookup"><span data-stu-id="29c1c-153">Run the command  `$terms` to show the current list of terms.</span></span> <span data-ttu-id="29c1c-154">The output of the command looks like this:</span><span class="sxs-lookup"><span data-stu-id="29c1c-154">The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="29c1c-155">다음 명령을 실행하여 제거하려는 용어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-155">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="29c1c-156">목록에서 용어를 실제로 제거하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-156">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="29c1c-157">Run the command  `$updatedTerms` to show the updated list of terms.</span><span class="sxs-lookup"><span data-stu-id="29c1c-157">Run the command  `$updatedTerms` to show the updated list of terms.</span></span> <span data-ttu-id="29c1c-158">The output of the command looks like this (the specified terms have been removed):</span><span class="sxs-lookup"><span data-stu-id="29c1c-158">The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="29c1c-159">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="29c1c-159">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16).</span></span> <span data-ttu-id="29c1c-160">Now you'll upload the updated terms and update the dictionary in place.</span><span class="sxs-lookup"><span data-stu-id="29c1c-160">Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="29c1c-161">Now the dictionary has been updated in place.</span><span class="sxs-lookup"><span data-stu-id="29c1c-161">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="29c1c-162">Note that the  `Identity` field takes the name of the dictionary.</span><span class="sxs-lookup"><span data-stu-id="29c1c-162">Note that the  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="29c1c-163">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span><span class="sxs-lookup"><span data-stu-id="29c1c-163">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="29c1c-164">사용자 지정 중요한 정보 유형과 DLP 정책에서 키워드 사전 사용</span><span class="sxs-lookup"><span data-stu-id="29c1c-164">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="29c1c-165">키워드 사전은 사용자 지정 중요 한 정보 유형 또는 중요 한 정보 유형 자체로 일치 요구 사항의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-165">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="29c1c-166">두 경우 모두 [사용자 지정 중요 한 정보 유형을](create-a-custom-sensitive-information-type-in-scc-powershell.md)만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-166">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="29c1c-167">중요 한 정보 유형을 만들려면 연결 된 문서에 설명 된 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-167">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="29c1c-168">XML을 사용 하는 경우에는 사전의 GUID 식별자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-168">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="29c1c-169">사전의 ID를 확인하려면 다음 명령을 실행하고 **Identity** 속성 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-169">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="29c1c-170">이 명령의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="29c1c-170">The output of the command looks like this:</span></span>
  
<span data-ttu-id="29c1c-171">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="29c1c-171">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="29c1c-172">Paste the identity into your custom sensitive information type's XML and upload it.</span><span class="sxs-lookup"><span data-stu-id="29c1c-172">Paste the identity into your custom sensitive information type's XML and upload it.</span></span> <span data-ttu-id="29c1c-173">Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span><span class="sxs-lookup"><span data-stu-id="29c1c-173">Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
