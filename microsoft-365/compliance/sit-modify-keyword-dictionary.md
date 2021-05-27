---
title: 키워드 사전 수정
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
description: Microsoft 365 준수 센터에서 키워드 사전을 수정하는 방법을 자세히 알아보습니다.
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685213"
---
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="578c9-103">키워드 사전 수정</span><span class="sxs-lookup"><span data-stu-id="578c9-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="578c9-104">키워드 사전 중 하나에 있는 키워드를 수정하거나 기본 제공 사전 중 하나에서 키워드를 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="578c9-105">PowerShell 또는 준수 센터를 통해 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="578c9-106">준수 센터에서 키워드 사전 수정</span><span class="sxs-lookup"><span data-stu-id="578c9-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="578c9-107">키워드 사전은 SIT(중요한 정보 유형) 패턴으로 또는 중요한 `Primary elements` `Supporting elements` 정보 유형으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="578c9-108">SIT를 만드는 동안 또는 기존 SIT에서 키워드 사전을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="578c9-109">예를 들어 기존 키워드 사전을 편집하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="578c9-110">업데이트할 키워드 사전이 있는 패턴을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="578c9-111">업데이트할 키워드 사전을 찾아 편집을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="578c9-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="578c9-112">한 줄에 하나의 키워드를 사용하여 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-112">Make your edits, using one keyword per line.</span></span>

![스크린샷 키워드 편집](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="578c9-114">를 `Done` 선택.</span><span class="sxs-lookup"><span data-stu-id="578c9-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="578c9-115">PowerShell을 사용하여 키워드 사전 수정</span><span class="sxs-lookup"><span data-stu-id="578c9-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="578c9-116">예를 들어 PowerShell에서 일부 용어를 수정하고, 용어를 수정할 수 있는 위치에 로컬로 저장한 다음 이전 용어를 제자리에 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="578c9-117">먼저 사전 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="578c9-118">`$dict`을(를) 인쇄하면 다양한 변수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="578c9-119">키워드 자체는 백엔드의 개체에 저장되지만 `$dict.KeywordDictionary`에는 키워드에 대한 문자열 표현이 포함되어 있어 사전을 수정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="578c9-120">사전을 수정하기 전에 `.split(',')` 방법을 사용하여 용어 문자열을 어레이로 다시 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="578c9-121">그런 다음 `.trim()` 메서드를 사용하여 키워드 사이의 원치 않는 공백을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="578c9-p105">이제 사전에서 몇 가지 용어를 제거해봅니다. 예제 사전에는 키워드가 몇 개만 포함되어 있으므로 사전을 내보내고 메모장에서 편집하는 과정으로 쉽게 건너뛸 수 있습니다. 그렇지만 사전에는 많은 용어가 들어 있는 것이 일반적이므로 먼저 이 방법을 배워 PowerShell에서 쉽게 편집할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-p105">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="578c9-p106">마지막 단계에서는 키워드를 배열로 저장했습니다. [배열에서 항목을 제거](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))하는 방법에는 여러 가지가 있지만 사전에서 제거하려는 용어의 배열을 만든 후 용어 목록에 없는 사전 용어만 복사하여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-p106">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="578c9-p107">명령 `$terms`를 실행하여 현재 용어 목록을 표시합니다. 명령 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-p107">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="578c9-128">다음 명령을 실행하여 제거하려는 용어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="578c9-129">목록에서 용어를 실제로 제거하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="578c9-p108">명령 `$updatedTerms`를 실행하여 업데이트된 용어 목록을 표시합니다. 명령 출력은 다음과 같습니다(지정된 용어가 제거됨).</span><span class="sxs-lookup"><span data-stu-id="578c9-p108">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="578c9-p109">이제 파일을 열고 영어를 더 추가한 후 유니코드 인코딩(UTF-16)으로 저장하면 됩니다. 업데이트된 용어를 업로드하고 사전을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-p109">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="578c9-134">사전이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="578c9-135">`Identity` 필드가 사전의 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="578c9-136">`set-`cmdlet을 사용하여 사전 이름도 변경하려면 위 명령에서 새 사전 이름과 함께 `-Name` 매개 변수만 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="578c9-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="578c9-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="578c9-137">See Also</span></span>
- [<span data-ttu-id="578c9-138">키워드 사전 만들기</span><span class="sxs-lookup"><span data-stu-id="578c9-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="578c9-139">사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="578c9-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
