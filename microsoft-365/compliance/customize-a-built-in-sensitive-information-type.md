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
# <a name="customize-a-built-in-sensitive-information-type"></a>기본 제공 중요한 정보 유형 사용자 지정

When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information. 
  
You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md). 
  
## <a name="export-the-xml-file-of-the-current-rules"></a>현재 규칙의 XML 파일 내보내기

XML을 내보내려면 [원격 PowerShell을 통해 보안 및 준수 센터에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)해야 합니다.
  
1. In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."

```powershell
Get-DlpSensitiveInformationTypeRulePackage
```    
2. Store your organization's rules in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.

```powershell    
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
```
    
3. Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.) 
    
```powershell
Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
```

> [!IMPORTANT]
> Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder. 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>XML에서 수정하려는 규칙 찾기

The cmdlets above exported the entire *rule collection*, which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify. 
  
1. 텍스트 편집기를 사용하여 이전 섹션에서 내보낸 XML 파일을 엽니다.
    
2. Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.
    
3. Look for *Func_credit_card* to find the Credit Card Number rule definition. In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated "SSN." The Credit Card Number rule XML should look like the following code sample.
    
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

Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>XML 수정 및 중요한 정보 유형 새로 만들기

First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.
  
All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.
  
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

Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**. 
  
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

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>중요한 정보 유형에서 증빙 요구 사항 제거

이제 보안 &amp; 준수 센터에 업로드할 수 있는 중요한 정보 유형이 새로 추가 되었으므로 다음 단계는 더 구체적으로 규칙을 만드는 것입니다. 체크섬을 전달하는 16자리 숫자만 검색하지만 키워드와 같은 추가(증빙) 증명 정보를 요구하지 않도록 규칙을 수정합니다. 이 작업을 수행하려면 증빙 정보를 검색하는 XML 부분을 제거해야 합니다. 증빙 정보는 가양성을 줄이는 데 매우 유용합니다. 이 경우에는 일반적으로 신용 카드 번호 근처에 몇 가지 특정 키워드나 만료 날짜가 있습니다. 해당 증빙 정보를 제거하는 경우 예제에서 85인 `confidenceLevel`을 낮추어 신용 카드 번호를 찾았는지 확신하는 정도를 조정해야 합니다.
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>조직에 관련된 키워드 찾기

You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.
  
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

## <a name="upload-your-rule"></a>규칙 업로드

규칙을 업로드하려면 다음을 수행해야 합니다.
  
1. Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.
    
2. [원격 PowerShell을 통해 보안 및 준수 센터에 연결합니다.](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. PowerShell에서 다음을 입력합니다.

```powershell    
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte).
```
> [!IMPORTANT]
> Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder. 
  
4. 확인하려면 Y를 입력하고 **Enter** 키를 누릅니다.
5. 새 규칙이 업로드 되었으며 다음을 입력하여 표시 이름을 확인합니다.

```powershell
Get-DlpSensitiveInformationType
```

To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).
  
## <a name="term-glossary"></a>용어 설명

다음은 이 절차 동안 표시되는 용어에 대한 정의입니다.
  
|**용어**|**정의**|
|:-----|:-----|
|엔터티|Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.|
|함수|The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.|
|IdMatch|이는 패턴과 일치하는 ID(예: 신용 카드 번호)입니다.|
|키워드 목록|The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.|
|패턴|패턴에는 중요한 유형에서 무엇을 조회하는지가 목록으로 포함됩니다. 여기에는 체크섬 확인과 같은 작업을 수행하는 키워드, regex 및 내부 함수를 포함합니다. 중요한 정보 유형에는 고유한 신뢰도를 갖는 여러 개의 패턴이 있을 수 있습니다. 이 기능은 증빙 정보가 발견되면 높은 신뢰도를 반환하고 증빙 정보가 거의 혹은 전혀 발견되지 않으면 낮은 신뢰도를 반환하는 중요한 정보 유형을 만들 때 유용합니다.|
|패턴 confidenceLevel|This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).|
|patternsProximity|신용 카드 번호 패턴처럼 보이는 항목이 있는 경우 `patternsProximity`는 증빙을 찾게 되는 해당 번호 주변의 근접 범위를 나타냅니다.|
|recommendedConfidence|This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked. The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action. If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.|
   
## <a name="for-more-information"></a>자세한 내용

- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)
    
- [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)
    
- [데이터 손실 방지 정책 개요](data-loss-prevention-policies.md)
