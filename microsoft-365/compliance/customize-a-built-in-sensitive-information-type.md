---
title: 기본 제공 중요한 정보 유형 사용자 지정
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 조직의 요구 사항에 맞는 규칙을 사용할 수 있도록 해주는 사용자 지정 중요한 정보 유형을 만드는 방법을 알아봅니다.
ms.openlocfilehash: 7c9be91de796ed06ca2bdd71e9e4de0462a92358
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817937"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="d58dc-103">기본 제공 중요한 정보 유형 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d58dc-103">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="d58dc-104">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  .</span><span class="sxs-lookup"><span data-stu-id="d58dc-104">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  .</span></span> <span data-ttu-id="d58dc-105">Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away.</span><span class="sxs-lookup"><span data-stu-id="d58dc-105">Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away.</span></span> <span data-ttu-id="d58dc-106">To use these rules, you have to include them in a policy.</span><span class="sxs-lookup"><span data-stu-id="d58dc-106">To use these rules, you have to include them in a policy.</span></span> <span data-ttu-id="d58dc-107">You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type.</span><span class="sxs-lookup"><span data-stu-id="d58dc-107">You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type.</span></span> <span data-ttu-id="d58dc-108">This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span><span class="sxs-lookup"><span data-stu-id="d58dc-108">This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="d58dc-109">You can take this example and apply it to other built-in sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="d58dc-109">You can take this example and apply it to other built-in sensitive information types.</span></span> <span data-ttu-id="d58dc-110">For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="d58dc-110">For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="d58dc-111">현재 규칙의 XML 파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="d58dc-111">Export the XML file of the current rules</span></span>

<span data-ttu-id="d58dc-112">XML을 내보내려면 [원격 PowerShell을 통해 보안 및 준수 센터에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-112">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="d58dc-113">In the PowerShell, type the following to display your organization's rules on screen.</span><span class="sxs-lookup"><span data-stu-id="d58dc-113">In the PowerShell, type the following to display your organization's rules on screen.</span></span> <span data-ttu-id="d58dc-114">If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span><span class="sxs-lookup"><span data-stu-id="d58dc-114">If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>

```powershell
Get-DlpSensitiveInformationTypeRulePackage
```    
2. <span data-ttu-id="d58dc-115">Store your organization's rules in a variable by typing the following.</span><span class="sxs-lookup"><span data-stu-id="d58dc-115">Store your organization's rules in a variable by typing the following.</span></span> <span data-ttu-id="d58dc-116">Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span><span class="sxs-lookup"><span data-stu-id="d58dc-116">Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>

```powershell    
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
```
    
3. <span data-ttu-id="d58dc-117">Make a formatted XML file with all that data by typing the following.</span><span class="sxs-lookup"><span data-stu-id="d58dc-117">Make a formatted XML file with all that data by typing the following.</span></span> <span data-ttu-id="d58dc-118">( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span><span class="sxs-lookup"><span data-stu-id="d58dc-118">( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 
    
```powershell
Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
```

> [!IMPORTANT]
> <span data-ttu-id="d58dc-119">Make sure that you use the file location where your rule pack is actually stored.</span><span class="sxs-lookup"><span data-stu-id="d58dc-119">Make sure that you use the file location where your rule pack is actually stored.</span></span>  <span data-ttu-id="d58dc-120">`C:\custompath\` is a placeholder.</span><span class="sxs-lookup"><span data-stu-id="d58dc-120">`C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="d58dc-121">XML에서 수정하려는 규칙 찾기</span><span class="sxs-lookup"><span data-stu-id="d58dc-121">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="d58dc-122">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide.</span><span class="sxs-lookup"><span data-stu-id="d58dc-122">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide.</span></span> <span data-ttu-id="d58dc-123">Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span><span class="sxs-lookup"><span data-stu-id="d58dc-123">Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="d58dc-124">텍스트 편집기를 사용하여 이전 섹션에서 내보낸 XML 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-124">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="d58dc-125">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules.</span><span class="sxs-lookup"><span data-stu-id="d58dc-125">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules.</span></span> <span data-ttu-id="d58dc-126">Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span><span class="sxs-lookup"><span data-stu-id="d58dc-126">Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span></span>
    
3. <span data-ttu-id="d58dc-127">Look for *Func_credit_card* to find the Credit Card Number rule definition.</span><span class="sxs-lookup"><span data-stu-id="d58dc-127">Look for *Func_credit_card* to find the Credit Card Number rule definition.</span></span> <span data-ttu-id="d58dc-128">In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated.</span><span class="sxs-lookup"><span data-stu-id="d58dc-128">In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated.</span></span> <span data-ttu-id="d58dc-129">An example of this is the U.S. Social Security number rule, which is abbreviated "SSN."</span><span class="sxs-lookup"><span data-stu-id="d58dc-129">An example of this is the U.S. Social Security number rule, which is abbreviated "SSN."</span></span> <span data-ttu-id="d58dc-130">The Credit Card Number rule XML should look like the following code sample.</span><span class="sxs-lookup"><span data-stu-id="d58dc-130">The Credit Card Number rule XML should look like the following code sample.</span></span>
    
  ```xml
  <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
         patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
         <IdMatch idRef="Func_credit_card" />
          <Any minMatches="1">
            <Match idRef="Keyword_cc_verification" />
            <Match idRef="Keyword_cc_name" />
            <Match idRef="Func_expiration_date" />
          </Any>
        </Pattern>
      </Entity>
  ```

<span data-ttu-id="d58dc-131">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs.</span><span class="sxs-lookup"><span data-stu-id="d58dc-131">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs.</span></span> <span data-ttu-id="d58dc-132">For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span><span class="sxs-lookup"><span data-stu-id="d58dc-132">For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span></span>
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="d58dc-133">XML 수정 및 중요한 정보 유형 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="d58dc-133">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="d58dc-134">First, you need to create a new sensitive information type because you can't directly modify the default rules.</span><span class="sxs-lookup"><span data-stu-id="d58dc-134">First, you need to create a new sensitive information type because you can't directly modify the default rules.</span></span> <span data-ttu-id="d58dc-135">You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d58dc-135">You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="d58dc-136">For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span><span class="sxs-lookup"><span data-stu-id="d58dc-136">For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="d58dc-137">All XML rule definitions are built on the following general template.</span><span class="sxs-lookup"><span data-stu-id="d58dc-137">All XML rule definitions are built on the following general template.</span></span> <span data-ttu-id="d58dc-138">You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ".</span><span class="sxs-lookup"><span data-stu-id="d58dc-138">You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ".</span></span> <span data-ttu-id="d58dc-139">.</span><span class="sxs-lookup"><span data-stu-id="d58dc-139">.</span></span> <span data-ttu-id="d58dc-140">."</span><span class="sxs-lookup"><span data-stu-id="d58dc-140">."</span></span> <span data-ttu-id="d58dc-141">placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span><span class="sxs-lookup"><span data-stu-id="d58dc-141">placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

<span data-ttu-id="d58dc-142">Now, you have something that looks similar to the following XML.</span><span class="sxs-lookup"><span data-stu-id="d58dc-142">Now, you have something that looks similar to the following XML.</span></span> <span data-ttu-id="d58dc-143">Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule.</span><span class="sxs-lookup"><span data-stu-id="d58dc-143">Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule.</span></span> <span data-ttu-id="d58dc-144">The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.</span><span class="sxs-lookup"><span data-stu-id="d58dc-144">The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.</span></span> <span data-ttu-id="d58dc-145">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span><span class="sxs-lookup"><span data-stu-id="d58dc-145">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="d58dc-146">중요한 정보 유형에서 증빙 요구 사항 제거</span><span class="sxs-lookup"><span data-stu-id="d58dc-146">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="d58dc-147">이제 보안 &amp; 준수 센터에 업로드할 수 있는 중요한 정보 유형이 새로 추가 되었으므로 다음 단계는 더 구체적으로 규칙을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-147">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific.</span></span> <span data-ttu-id="d58dc-148">체크섬을 전달하는 16자리 숫자만 검색하지만 키워드와 같은 추가(증빙) 증명 정보를 요구하지 않도록 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-148">Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence, like keywords.</span></span> <span data-ttu-id="d58dc-149">이 작업을 수행하려면 증빙 정보를 검색하는 XML 부분을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-149">To do this, you need to remove the part of the XML that looks for corroborative evidence.</span></span> <span data-ttu-id="d58dc-150">증빙 정보는 가양성을 줄이는 데 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-150">Corroborative evidence is very helpful in reducing false positives.</span></span> <span data-ttu-id="d58dc-151">이 경우에는 일반적으로 신용 카드 번호 근처에 몇 가지 특정 키워드나 만료 날짜가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-151">In this case there are usually certain keywords or an expiration date near the credit card number.</span></span> <span data-ttu-id="d58dc-152">해당 증빙 정보를 제거하는 경우 예제에서 85인 `confidenceLevel`을 낮추어 신용 카드 번호를 찾았는지 확신하는 정도를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-152">If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="d58dc-153">조직에 관련된 키워드 찾기</span><span class="sxs-lookup"><span data-stu-id="d58dc-153">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="d58dc-154">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence.</span><span class="sxs-lookup"><span data-stu-id="d58dc-154">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence.</span></span> <span data-ttu-id="d58dc-155">You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number.</span><span class="sxs-lookup"><span data-stu-id="d58dc-155">You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number.</span></span> <span data-ttu-id="d58dc-156">To add your own keywords, you need to define a keyword list and reference it within your rule.</span><span class="sxs-lookup"><span data-stu-id="d58dc-156">To add your own keywords, you need to define a keyword list and reference it within your rule.</span></span> <span data-ttu-id="d58dc-157">The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span><span class="sxs-lookup"><span data-stu-id="d58dc-157">The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span>
  
```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a><span data-ttu-id="d58dc-158">규칙 업로드</span><span class="sxs-lookup"><span data-stu-id="d58dc-158">Upload your rule</span></span>

<span data-ttu-id="d58dc-159">규칙을 업로드하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-159">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="d58dc-160">Save it as an .xml file with Unicode encoding.</span><span class="sxs-lookup"><span data-stu-id="d58dc-160">Save it as an .xml file with Unicode encoding.</span></span> <span data-ttu-id="d58dc-161">This is important because the rule won't work if the file is saved with a different encoding.</span><span class="sxs-lookup"><span data-stu-id="d58dc-161">This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. [<span data-ttu-id="d58dc-162">원격 PowerShell을 통해 보안 및 준수 센터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-162">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. <span data-ttu-id="d58dc-163">PowerShell에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-163">In the PowerShell, type the following.</span></span>

```powershell    
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte).
```
> [!IMPORTANT]
> <span data-ttu-id="d58dc-164">Make sure that you use the file location where your rule pack is actually stored.</span><span class="sxs-lookup"><span data-stu-id="d58dc-164">Make sure that you use the file location where your rule pack is actually stored.</span></span>  <span data-ttu-id="d58dc-165">`C:\custompath\` is a placeholder.</span><span class="sxs-lookup"><span data-stu-id="d58dc-165">`C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="d58dc-166">확인하려면 Y를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-166">To confirm, type Y, and then press **Enter**.</span></span>
5. <span data-ttu-id="d58dc-167">새 규칙이 업로드 되었으며 다음을 입력하여 표시 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-167">Verify that your new rule was uploaded and it's display name by typing:</span></span>

```powershell
Get-DlpSensitiveInformationType
```

<span data-ttu-id="d58dc-168">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy.</span><span class="sxs-lookup"><span data-stu-id="d58dc-168">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy.</span></span> <span data-ttu-id="d58dc-169">To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="d58dc-169">To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="d58dc-170">용어 설명</span><span class="sxs-lookup"><span data-stu-id="d58dc-170">Term glossary</span></span>

<span data-ttu-id="d58dc-171">다음은 이 절차 동안 표시되는 용어에 대한 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-171">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="d58dc-172">**용어**</span><span class="sxs-lookup"><span data-stu-id="d58dc-172">**Term**</span></span>|<span data-ttu-id="d58dc-173">**정의**</span><span class="sxs-lookup"><span data-stu-id="d58dc-173">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d58dc-174">엔터티</span><span class="sxs-lookup"><span data-stu-id="d58dc-174">Entity</span></span>|<span data-ttu-id="d58dc-175">Entities are what we call sensitive information types, such as credit card numbers.</span><span class="sxs-lookup"><span data-stu-id="d58dc-175">Entities are what we call sensitive information types, such as credit card numbers.</span></span> <span data-ttu-id="d58dc-176">Each entity has a unique GUID as its ID.</span><span class="sxs-lookup"><span data-stu-id="d58dc-176">Each entity has a unique GUID as its ID.</span></span> <span data-ttu-id="d58dc-177">If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule.</span><span class="sxs-lookup"><span data-stu-id="d58dc-177">If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule.</span></span> <span data-ttu-id="d58dc-178">You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span><span class="sxs-lookup"><span data-stu-id="d58dc-178">You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="d58dc-179">함수</span><span class="sxs-lookup"><span data-stu-id="d58dc-179">Functions</span></span>|<span data-ttu-id="d58dc-180">The XML file references  `Func_credit_card`, which is a function in compiled code.</span><span class="sxs-lookup"><span data-stu-id="d58dc-180">The XML file references  `Func_credit_card`, which is a function in compiled code.</span></span> <span data-ttu-id="d58dc-181">Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span><span class="sxs-lookup"><span data-stu-id="d58dc-181">Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="d58dc-182">IdMatch</span><span class="sxs-lookup"><span data-stu-id="d58dc-182">IdMatch</span></span>|<span data-ttu-id="d58dc-183">이는 패턴과 일치하는 ID(예: 신용 카드 번호)입니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-183">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="d58dc-184">키워드 목록</span><span class="sxs-lookup"><span data-stu-id="d58dc-184">Keyword lists</span></span>|<span data-ttu-id="d58dc-185">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity.</span><span class="sxs-lookup"><span data-stu-id="d58dc-185">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity.</span></span> <span data-ttu-id="d58dc-186">These aren't currently displayed in the XML.</span><span class="sxs-lookup"><span data-stu-id="d58dc-186">These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="d58dc-187">패턴</span><span class="sxs-lookup"><span data-stu-id="d58dc-187">Pattern</span></span>|<span data-ttu-id="d58dc-188">패턴에는 중요한 유형에서 무엇을 조회하는지가 목록으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-188">The pattern contains the list of what the sensitive type is looking for.</span></span> <span data-ttu-id="d58dc-189">여기에는 체크섬 확인과 같은 작업을 수행하는 키워드, regex 및 내부 함수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-189">This includes keywords, regexes, and internal functions, which perform tasks like verifying checksums.</span></span> <span data-ttu-id="d58dc-190">중요한 정보 유형에는 고유한 신뢰도를 갖는 여러 개의 패턴이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-190">Sensitive information types can have multiple patterns with unique confidences.</span></span> <span data-ttu-id="d58dc-191">이 기능은 증빙 정보가 발견되면 높은 신뢰도를 반환하고 증빙 정보가 거의 혹은 전혀 발견되지 않으면 낮은 신뢰도를 반환하는 중요한 정보 유형을 만들 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-191">This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="d58dc-192">패턴 confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="d58dc-192">Pattern confidenceLevel</span></span>|<span data-ttu-id="d58dc-193">This is the level of confidence that the DLP engine found a match.</span><span class="sxs-lookup"><span data-stu-id="d58dc-193">This is the level of confidence that the DLP engine found a match.</span></span> <span data-ttu-id="d58dc-194">This level of confidence is associated with a match for the pattern if the pattern's requirements are met.</span><span class="sxs-lookup"><span data-stu-id="d58dc-194">This level of confidence is associated with a match for the pattern if the pattern's requirements are met.</span></span> <span data-ttu-id="d58dc-195">This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span><span class="sxs-lookup"><span data-stu-id="d58dc-195">This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="d58dc-196">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="d58dc-196">patternsProximity</span></span>|<span data-ttu-id="d58dc-197">신용 카드 번호 패턴처럼 보이는 항목이 있는 경우 `patternsProximity`는 증빙을 찾게 되는 해당 번호 주변의 근접 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d58dc-197">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="d58dc-198">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="d58dc-198">recommendedConfidence</span></span>|<span data-ttu-id="d58dc-199">This is the confidence level we recommend for this rule.</span><span class="sxs-lookup"><span data-stu-id="d58dc-199">This is the confidence level we recommend for this rule.</span></span> <span data-ttu-id="d58dc-200">The recommended confidence applies to entities and affinities.</span><span class="sxs-lookup"><span data-stu-id="d58dc-200">The recommended confidence applies to entities and affinities.</span></span> <span data-ttu-id="d58dc-201">For entities, this number is never evaluated against the  `confidenceLevel` for the pattern.</span><span class="sxs-lookup"><span data-stu-id="d58dc-201">For entities, this number is never evaluated against the  `confidenceLevel` for the pattern.</span></span> <span data-ttu-id="d58dc-202">It's merely a suggestion to help you choose a confidence level if you want to apply one.</span><span class="sxs-lookup"><span data-stu-id="d58dc-202">It's merely a suggestion to help you choose a confidence level if you want to apply one.</span></span> <span data-ttu-id="d58dc-203">For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked.</span><span class="sxs-lookup"><span data-stu-id="d58dc-203">For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked.</span></span> <span data-ttu-id="d58dc-204">The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action.</span><span class="sxs-lookup"><span data-stu-id="d58dc-204">The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action.</span></span> <span data-ttu-id="d58dc-205">If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span><span class="sxs-lookup"><span data-stu-id="d58dc-205">If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="d58dc-206">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="d58dc-206">For more information</span></span>

- [<span data-ttu-id="d58dc-207">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="d58dc-207">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="d58dc-208">사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="d58dc-208">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="d58dc-209">데이터 손실 방지 정책 개요</span><span class="sxs-lookup"><span data-stu-id="d58dc-209">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
