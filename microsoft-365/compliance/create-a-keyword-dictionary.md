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
ms.openlocfilehash: 661ca9e227e8583bb6b601792e178c1c366132cb
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256714"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="111f5-103">키워드 사전 만들기</span><span class="sxs-lookup"><span data-stu-id="111f5-103">Create a keyword dictionary</span></span>

<span data-ttu-id="111f5-104">DLP(데이터 손실 방지)는 중요한 항목을 식별, 모니터링 및 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="111f5-105">중요한 항목을 식별하려면 키워드를 찾아야 하는 경우가 있으며, 특히 의료 관련 통신과 같은 일반 컨텐츠 또는 부적절하거나 명시적인 언어를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="111f5-106">중요한 정보 유형에서 키워드 목록을 만들 수 있지만 키워드 목록은 크기가 제한되어 있으며, 키워드 목록을 만들거나 편집하려면 XML을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="111f5-107">키워드 사전은 키워드 관리를 보다 간단하고 훨씬 더 큰 규모로 제공하여 사전에서 최대 1 MB의 용어(사후 압축)를 지원하고 모든 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="111f5-108">테넌트 제한도 압축 후에 1 MB가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="111f5-109">1 MB의 사후 압축 제한은 테넌트 전체에서 결합된 모든 사전에 1백만 문자에 가까운 문자가 있을 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="111f5-110">키워드 사전 제한</span><span class="sxs-lookup"><span data-stu-id="111f5-110">Keyword dictionary limits</span></span>

<span data-ttu-id="111f5-111">테넌트당 만들 수 있는 중요한 정보 유형을 기반으로 하는 키워드 사전은 50개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="111f5-112">테넌트에 있는 키워드 사전의 수를 확인하려면 [보안 및 준수 센터 PowerShell 연결](/powershell/exchange/connect-to-scc-powershell)의 절차를 따라 테넌트에 연결하고 이 PowerShell 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="111f5-113">키워드 사전을 만드는 기본 단계</span><span class="sxs-lookup"><span data-stu-id="111f5-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="111f5-p103">사전의 키워드는 다양한 원본, 서비스 또는 PowerShell cmdlet에서 가져온 파일(예:.csv 또는 .txt 목록)(대부분의 경우), PowerShell cmdlet에 사용자가 직접 입력한 목록 또는 기존 사전에서 가져올 수 있습니다. 키워드 사전을 만들 때 다음과 같은 동일한 핵심 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="111f5-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="111f5-116">**보안 및 규정 준수 센터**([https://protection.office.com](https://protection.office.com))를 사용하거나 **보안 &amp;준수 센터 PowerShell** 에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="111f5-117">**원하는 원본** 에서 키워드를 정의 하거나 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="111f5-118">마법사와 cmdlet 모두 쉼표로 구분된 키워드 목록을 사용하여 사용자 정의 키워드 사전을 만들 수 있으므로 이 단계는 키워드의 출처에 따라 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="111f5-119">로드되면 가져오기 전에 인코딩 및 바이트 배열로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="111f5-120">**사전을 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="111f5-120">**Create your dictionary**.</span></span> <span data-ttu-id="111f5-121">이름과 설명을 선택하고 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="111f5-122">보안 및 준수 센터를 사용하여 키워드 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="111f5-123">다음 단계를 따라 사용자 지정 사전에 대한 키워드를 만들고 가져오세요.</span><span class="sxs-lookup"><span data-stu-id="111f5-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="111f5-124">보안 및 규정 준수 센터([https://protection.office.com](https://protection.office.com))에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="111f5-125">**분류 > 중요한 정보 유형** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="111f5-126">**만들기** 를 선택하고 중요한 정보 유형에 대한 **이름** 및 **설명** 을 입력하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="111f5-127">**요소 추가** 를 선택한 다음 **다음이 포함된 내용 감지** 드롭다운에서 **사전(광범위한 키워드)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="111f5-128">**사전 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="111f5-129">검색 컨트롤에서 **여기에서 새 키워드 사전을 만들 수 있음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="111f5-130">사용자 지정 사전에 대한 **이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="111f5-131">**가져오기** 를 선택하고 키워드 파일 종류에 따라 **텍스트 파일에서** 또는 **csv 파일에서** 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="111f5-132">파일 대화 상자에서 로컬 PC 또는 네트워크 파일 공유에 있는 키워드 파일을 선택한 다음 **열기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="111f5-133">**저장** 을 선택한 다음 **키워드 사전** 목록에서 사용자 지정 사전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="111f5-134">**추가** 를 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="111f5-135">중요한 정보 유형 선택 사항을 검토 및 완료한 다음 **완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="111f5-136">PowerShell을 사용하여 파일에서 키워드 사전 만들기</span><span class="sxs-lookup"><span data-stu-id="111f5-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="111f5-137">대형 사전을 작성해야 하는 경우 파일 또는 다른 원본에서 내보낸 목록의 키워드를 사용하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="111f5-138">이 경우 외부 전자 메일에서 표시하기에 부적절한 언어 목록이 포함된 키워드 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="111f5-139">먼저 [보안 &amp; 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="111f5-140">키워드를 텍스트 파일에 복사합니다. 이때 각 키워드를 별도 줄에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="111f5-p107">텍스트 파일을 유니코드 인코딩으로 저장합니다. 메모장에서 \> **다른 이름으로 저장** \> **인코딩으로** \> **유니코드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="111f5-143">다음 cmdlet을 실행하여 파일을 변수로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="111f5-144">다음 cmdlet을 실행하여 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="111f5-145">사용자 지정 중요한 정보 유형과 DLP 정책에서 키워드 사전 사용</span><span class="sxs-lookup"><span data-stu-id="111f5-145">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="111f5-146">키워드 사전은 사용자 정의 중요한 정보 유형에 대한 일치 요구 사항의 일부로 사용하거나 중요한 정보 유형 자체로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-146">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="111f5-147">둘 다 [사용자 지정 중요한 정보 유형](create-a-custom-sensitive-information-type-in-scc-powershell.md)을(를) 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-147">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="111f5-148">링크된 문서의 지침에 따라 중요한 정보 유형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-148">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="111f5-149">XML을 사용하게 되면 사전에 사용할 GUID 식별자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-149">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="111f5-150">사전의 ID를 확인하려면 다음 명령을 실행하고 **Identity** 속성 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-150">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="111f5-151">이 명령의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-151">The output of the command looks like this:</span></span>
  
<span data-ttu-id="111f5-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="111f5-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="111f5-p109">사용자 지정 중요한 정보 유형의 XML에 ID를 붙여넣은 후 업로드합니다. 이제 사전이 중요한 정보 유형 목록에 표시되므로 일치시킬 키워드 수를 지정하여 정책에서 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-p109">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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

> [!NOTE]
> <span data-ttu-id="111f5-155">Microsoft 365 Information Protection은 다음의 더블 바이트 문자 집합 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-155">Microsoft 365 Information Protection supports double byte character set languages for:</span></span>
> - <span data-ttu-id="111f5-156">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="111f5-156">Chinese (simplified)</span></span>
> - <span data-ttu-id="111f5-157">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="111f5-157">Chinese (traditional)</span></span>
> - <span data-ttu-id="111f5-158">한국어</span><span class="sxs-lookup"><span data-stu-id="111f5-158">Korean</span></span>
> - <span data-ttu-id="111f5-159">일본어</span><span class="sxs-lookup"><span data-stu-id="111f5-159">Japanese</span></span>
>
><span data-ttu-id="111f5-160">이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-160">This support is available for sensitive information types.</span></span> <span data-ttu-id="111f5-161">자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="111f5-161">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="111f5-162">중국어/일본어 문자와 단일 바이트 문자가 포함된 패턴을 검색하거나 중국어/일본어 및 영어가 포함된 패턴을 검색하려면 키워드 또는 regex의 두 가지 변형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-162">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span> <span data-ttu-id="111f5-163">예를 들어 "机密的document"와 같은 키워드를 검색하려면 해당 키워드의 두 변형을 사용합니다. 일본어와 영어 텍스트 사이에 공백이 있고 일본어 텍스트와 영어 텍스트 사이에 공백이 없는 다른 텍스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-163">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="111f5-164">따라서 SIT에 추가할 키워드는 "机密的 document" 및 "机密的document"여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-164">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="111f5-165">마찬가지로 "東京オリンピック2020"라는 구를 검색하려면 두 가지 변형("東京オリンピック 2020" 및 "東京オリンピック2020")을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-165">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> <span data-ttu-id="111f5-166">더블 바이트 하이픈 또는 더블 바이트 마침표로 regex를 만드는 동안 regex에서 하이픈이나 마침표가 이스케이프되는 것처럼 두 문자를 모두 이스케이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-166">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex.</span></span> <span data-ttu-id="111f5-167">참조를 위한 샘플 regex는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-167">Here is a sample regex for reference:</span></span>
    - <span data-ttu-id="111f5-168">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="111f5-168">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
> <span data-ttu-id="111f5-169">키워드 목록에서 단어 일치 대신 문자열 일치를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="111f5-169">We recommend using a string match instead of a word match in a keyword list.</span></span>
