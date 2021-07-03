---
title: PowerShell을 사용한 사용자 지정 중요한 정보 유형 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 규정 준수 센터에서 정책에 대한 사용자 지정 중요한 정보 유형을 만들고 가져오는 방법을 알아보세요.
ms.openlocfilehash: ef63adc5fb4f032b6224e054950f8c40f5e78f5a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287614"
---
# <a name="create-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="d637a-103">PowerShell을 사용한 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="d637a-103">Create a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="d637a-104">이 항목에서는 PowerShell을 사용하여 사용자 지정 [중요한 정보 유형](sensitive-information-type-entity-definitions.md)을 정의하는 XML *규칙 패키지* 파일을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-104">This topic shows you how to use PowerShell to create an XML *rule package* file that defines your own custom [sensitive information types](sensitive-information-type-entity-definitions.md).</span></span> <span data-ttu-id="d637a-105">먼저 정규식을 만드는 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-105">You need to know how to create a regular expression.</span></span> <span data-ttu-id="d637a-106">이 항목에서는 하나의 예로서 직원 ID를 식별하는 중요한 정보 유형을 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-106">As an example, this topic creates a custom sensitive information type that identifies an employee ID.</span></span> <span data-ttu-id="d637a-107">자체 XML 파일을 만들기 위한 시작점으로 본 XML 예제를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-107">You can use this example XML as a starting point for your own XML file.</span></span> <span data-ttu-id="d637a-108">중요한 정보 유형에 대한 자세한 내용은 [중요한 정보 유형에 대해 자세히 알아보기](sensitive-information-type-learn-about.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-108">If you are new to sensitive information types, see [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span>

<span data-ttu-id="d637a-p102">잘 구성된 XML 파일을 만들었으면 Microsoft 365 PowerShell을 사용하여 Microsoft 365에 업로드할 수 있습니다. 그러면 정책에서 해당 사용자 지정 중요한 정보 유형을 사용하고 중요한 정보가 의도대로 감지되는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p102">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell. Then you're ready to use your custom sensitive information type in your policies and test that it's detecting the sensitive information as you intended.</span></span>

> [!NOTE]
> <span data-ttu-id="d637a-111">PowerShell에서 제공하는 세밀한 제어가 필요하지 않은 경우 규정 준수 센터에서 사용자 지정 중요한 정보 유형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-111">If you don't need the fine grained control that PowerShell provides, you can create custom sensitive information types in the Compliance center.</span></span> <span data-ttu-id="d637a-112">자세한 내용은 [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-112">For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="important-disclaimer"></a><span data-ttu-id="d637a-113">중요 고지 사항</span><span class="sxs-lookup"><span data-stu-id="d637a-113">Important disclaimer</span></span>

<span data-ttu-id="d637a-p104"> 고객 환경 및 콘텐츠 일치 요구의 차이 때문에 Microsoft 지원 서비스는 고객 콘텐츠 일치 정의(예: 사용자 지정 분류 또는 정규식 패턴(RegEx라고 함) 정의)를 제공하도록 지원할 수 없습니다. 고객 콘텐츠 일치 개발, 테스트 및 디버그를 위해 Office 365 고객은 내부 IT 리소스에 의존하거나 MCS(Microsoft 컨설팅 서비스)와 같은 외부 컨설팅 리소스에 의존해야 합니다. 지원 엔지니어는 이 기능에 대해 제한된 지원을 제공할 수 있지만 사용자 지정 콘텐츠 일치 개발이 고객의 요구나 의무를 이행할 것이라는 보장을 제공할 수 없습니다. 제공될 수 있는 지원 유형의 예로, 테스트 목적으로 샘플 정규식 패턴이 제공될 수 있습니다. 또는 지원 서비스는 단일 특정 콘텐츠 예제에서 예상대로 트리거되지 않는 기존 RegEx 패턴 문제를 해결하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p104">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns. For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS). Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.  As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes. Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span></span>

<span data-ttu-id="d637a-119">이 토픽에서 [인식해야 할 잠재적인 유효성 검사 문제](#potential-validation-issues-to-be-aware-of)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-119">See [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of) in this topic.</span></span>

<span data-ttu-id="d637a-120">텍스트 처리에 사용되는 Boost.RegEx(이전에는 RegEx++라고 함) 엔진에 대한 자세한 내용은 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-120">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

> [!NOTE]
> <span data-ttu-id="d637a-121">사용자 지정 중요한 정보 유형에서 키워드의 일부로 앰퍼and 문자(&)를 사용하는 경우 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-121">If you use an ampersand character (&) as part of a keyword in your custom sensitive information type, please note that there is a known issue.</span></span> <span data-ttu-id="d637a-122">문자가 올바르게 식별되었는지 확인하려면 문자 주위에 공백이 있는 추가 용어를 추가해야 합니다(예: L & P _&_ P).</span><span class="sxs-lookup"><span data-stu-id="d637a-122">You should add an additional term with spaces around the character to make sure that the character is properly identified, for example, L & P _not_ L&P.</span></span>

## <a name="sample-xml-of-a-rule-package"></a><span data-ttu-id="d637a-123">규칙 패키지의 샘플 XML</span><span class="sxs-lookup"><span data-stu-id="d637a-123">Sample XML of a rule package</span></span>

<span data-ttu-id="d637a-p106">다음은 이 항목에서 만들 규칙 패키지의 샘플 XML입니다. 요소와 특성은 다음 섹션에 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p106">Here's the sample XML of the rule package that we'll create in this topic. Elements and attributes are explained in the sections below.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
  <Version build="0" major="1" minor="0" revision="0"/>
  <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
  <Details defaultLangCode="en-us">
    <LocalizedDetails langcode="en-us">
      <PublisherName>Contoso</PublisherName>
      <Name>Employee ID Custom Rule Pack</Name>
      <Description>
      This rule package contains the custom Employee ID entity.
      </Description>
    </LocalizedDetails>
  </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
  <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="65">
      <IdMatch idRef="Regex_employee_id"/>
    </Pattern>
    <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
    </Pattern>
    <Pattern confidenceLevel="85">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
      <Any minMatches="1">
        <Match idRef="Keyword_badge" minCount="2"/>
        <Match idRef="Keyword_employee"/>
      </Any>
      <Any minMatches="0" maxMatches="0">
        <Match idRef="Keyword_false_positives_local"/>
        <Match idRef="Keyword_false_positives_intl"/>
      </Any>
    </Pattern>
  </Entity>
  <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
  <Keyword id="Keyword_employee">
    <Group matchStyle="word">
      <Term>Identification</Term>
      <Term>Contoso Employee</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_badge">
    <Group matchStyle="string">
      <Term>card</Term>
      <Term>badge</Term>
      <Term caseSensitive="true">ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_local">
    <Group matchStyle="word">
      <Term>credit card</Term>
      <Term>national ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_intl">
    <Group matchStyle="word">
      <Term>identity card</Term>
      <Term>national ID</Term>
      <Term>EU debit card</Term>
    </Group>
  </Keyword>
  <LocalizedStrings>
    <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
      <Name default="true" langcode="en-us">Employee ID</Name>
      <Description default="true" langcode="en-us">
      A custom classification for detecting Employee IDs.
      </Description>
      <Description default="false" langcode="de-de">
      Description for German locale.
      </Description>
    </Resource>
  </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a><span data-ttu-id="d637a-p107">주요 요구 사항은 무엇인가요? [Rule, Entity, Pattern 요소]</span><span class="sxs-lookup"><span data-stu-id="d637a-p107">What are your key requirements? [Rule, Entity, Pattern elements]</span></span>

<span data-ttu-id="d637a-128">시작하기 전에 규칙에 대한 XML 스키마의 기본 구조와 이 구조를 사용하여 올바른 콘텐츠를 식별하도록 사용자 지정 중요한 정보 유형을 정의하는 방법을 이해하면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-128">Before you get started, it's helpful to understand the basic structure of the XML schema for a rule, and how you can use this structure to define your custom sensitive information type so that it will identify the right content.</span></span>
  
<span data-ttu-id="d637a-p108">규칙은 하나 이상의 엔터티(중요한 정보 유형)를 정의하고, 각 엔터티는 하나 이상의 패턴을 정의합니다. 패턴은 전자 메일이나 문서와 같은 콘텐츠를 평가할 때 정책이 검색하는 항목을 나타냅니다. </span><span class="sxs-lookup"><span data-stu-id="d637a-p108">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns. A pattern is what a policy looks for when it evaluates content such as email and documents.</span></span>

<span data-ttu-id="d637a-p109">이 항목에서 XML 마크업에서는 규칙을 사용하여 중요한 정보 유형이라고도 하는 엔터티를 정의하는 패턴을 의미합니다. 따라서 이 항목에서는 규칙을 볼 때 조건과 작업이 아닌 엔터티 또는 중요한 정보 유형을 생각합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p109">In this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type. So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.</span></span>
  
### <a name="simplest-scenario-entity-with-one-pattern"></a><span data-ttu-id="d637a-133">가장 간단한 시나리오: 하나의 패턴을 갖는 엔터티</span><span class="sxs-lookup"><span data-stu-id="d637a-133">Simplest scenario: entity with one pattern</span></span>

<span data-ttu-id="d637a-p110">다음은 가장 간단한 시나리오입니다. 정책이 9자리 숫자로 구성된 조직의 직원 ID를 포함하는 콘텐츠를 식별하게 하려고 합니다. 따라서 패턴은 9자리 숫자를 식별하는 규칙에 포함된 정규식을 나타냅니다. 9자리 숫자를 포함하는 모든 콘텐츠는 해당 패턴을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p110">Here's the simplest scenario. You want your policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number. So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers. Any content containing a nine-digit number satisfies the pattern.</span></span>
  
![하나의 패턴을 갖는 엔터티 다이어그램](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
<span data-ttu-id="d637a-139">이 패턴은 간단하지만 9자리 숫자를 포함하는 콘텐츠를 일치시켜 직원 ID가 아닐 수 있는 많은 가양성을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-139">However, while simple, this pattern may identify many false positives by matching content that contains any nine-digit number that is not necessarily an employee ID.</span></span>
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a><span data-ttu-id="d637a-140">좀 더 일반적인 시나리오: 여러 패턴을 갖는 엔터티</span><span class="sxs-lookup"><span data-stu-id="d637a-140">More common scenario: entity with multiple patterns</span></span>

<span data-ttu-id="d637a-141">이러한 이유로, 해당 엔터티(예: 9자리 숫자) 외에 뒷받침하는 증거(예: 키워드 또는 날짜)를 식별하는 패턴을 추가적으로 사용하여 엔터티를 정의하는 것이 좀 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-141">For this reason, it's more common to define an entity by using more than one pattern, where the patterns identify supporting evidence (such as a keyword or date) in addition to the entity (such as a nine-digit number).</span></span>
  
<span data-ttu-id="d637a-142">예를 들어, 직원 ID를 포함하는 콘텐츠를 식별할 확률을 높이기 위해, 채용 날짜도 식별하는 다른 패턴을 정의하고, 9자리 숫자 외에 채용 날짜와 키워드(예: “직원 ID”)를 둘 다 식별하는 또 다른 패턴을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-142">For example, to increase the likelihood of identifying content that contains an employee ID, you can define another pattern that also identifies a hire date, and define yet another pattern that identifies both a hire date and a keyword (such as "employee ID"), in addition to the nine-digit number.</span></span>
  
![여러 패턴을 갖는 엔터티 다이어그램](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
<span data-ttu-id="d637a-144">이 구조는 다음과 같은 몇 가지 중요한 측면을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-144">Note a couple of important aspects of this structure:</span></span>
  
- <span data-ttu-id="d637a-p111">더 많은 증거가 필요한 패턴은 더 높은 신뢰도 수준을 갖습니다. 이것은 나중에 정책에서 이 중요한 정보를 사용할 때 높은 신뢰도 일치만 사용하여 더 제한적인 작업(콘텐츠 차단 등)을 사용할 수 있고 낮은 신뢰도 일치를 사용하여 덜 제한적인 작업(예: 알림 보내기)을 사용할 수 있으므로 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p111">Patterns that require more evidence have a higher confidence level. This is useful because when you later use this sensitive information type in a policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span></span>

- <span data-ttu-id="d637a-p112">IdMatch 및 Match와 같은 지원 요소는 Pattern이 아닌 Rule 요소의 하위 요소인 regex와 키워드를 참조합니다. 이러한 지원 요소는 Pattern에 의해 참조되나 Rule에 포함됩니다. 즉, 여러 개의 엔터티와 패턴에서 정규식이나 키워드 목록 등 지원 요소에 대한 정의를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p112">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern. These supporting elements are referenced by the Pattern but included in the Rule. This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span></span>

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a><span data-ttu-id="d637a-p113">식별해야 하는 엔터티는 무엇인가? [Entity 요소, id 속성]</span><span class="sxs-lookup"><span data-stu-id="d637a-p113">What entity do you need to identify? [Entity element, id attribute]</span></span>

<span data-ttu-id="d637a-p114">엔터티는 정상적인 패턴을 갖는 중요한 정보 유형(예: 신용 카드 번호)입니다. 각 엔터티는 ID로서 고유한 GUID를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p114">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern. Each entity has a unique GUID as its ID.</span></span>
  
### <a name="name-the-entity-and-generate-its-guid"></a><span data-ttu-id="d637a-154">엔터티에 이름 지정 및 해당 GUID 생성</span><span class="sxs-lookup"><span data-stu-id="d637a-154">Name the entity and generate its GUID</span></span>

1. <span data-ttu-id="d637a-155">선택한 XML 편집기에서 Rules 및 Entity 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-155">In your XML editor of choice, add the Rules and Entity elements.</span></span>
2. <span data-ttu-id="d637a-p115">사용자 지정 엔터티의 이름(이 예제에서는 직원 ID)을 포함하는 주석을 추가합니다. 나중에 이 엔터티 이름을 지역화된 문자열 섹션에 추가합니다. 그러면 해당 이름이 정책을 만들 때 UI에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p115">Add a comment that contains the name of your custom entity — in this example, Employee ID. Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a policy.</span></span>
3. <span data-ttu-id="d637a-158">엔터티의 GUID를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-158">Generate a GUID for your entity.</span></span> <span data-ttu-id="d637a-159">GUID를 생성하는 방법에는 여러 가지가 있지만, PowerShell에서 **[guid]::NewGuid()** 를 입력하면 간단하게 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-159">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> <span data-ttu-id="d637a-160">뒤에서 현지화된 문자열 섹션에도 엔터티 GUID를 추가하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-160">Later, you'll also add the entity GUID to the localized strings section.</span></span>
  
![Rules 및 Entity 보여 주는 XML 태그 요소](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a><span data-ttu-id="d637a-p117">일치하려는 패턴은 어느 것인가요? [Pattern 요소, IdMatch 요소, Regex 요소]</span><span class="sxs-lookup"><span data-stu-id="d637a-p117">What pattern do you want to match? [Pattern element, IdMatch element, Regex element]</span></span>

<span data-ttu-id="d637a-p118">패턴에는 중요한 정보 유형이 검색하는 항목 목록이 포함됩니다. 여기에는 regex, 키워드 및 기본 제공 함수(regex를 실행하여 날짜나 주소를 찾는 것과 같은 작업 수행)가 포함될 수 있습니다. 중요한 정보 유형은 고유한 신뢰도를 갖는 여러 패턴을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p118">The pattern contains the list of what the sensitive information type is looking for. This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses). Sensitive information types can have multiple patterns with unique confidences.</span></span>
  
<span data-ttu-id="d637a-p119">아래의 모든 패턴이 갖는 공통점은 모두가 공백 (\s) … (\s)으로 둘러싸인 9자리 숫자(\d{9})를 찾는 동일한 정규식을 참조한다는 것입니다. 이 정규식은 IdMatch 요소에서 참조되고 직원 ID 엔터티를 찾는 모든 패턴의 공통된 요구 사항입니다. IdMatch는 패턴이 직원 ID, 신용 카드 번호, 주민 등록 번호 등을 일치시킬 식별자입니다. Pattern 요소에는 IdMatch 요소가 1개만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p119">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) … (\s). This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity. IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number. A Pattern element must have exactly one IdMatch element.</span></span>
  
![단일 Regex 요소를 참조하는 여러 Pattern 요소를 보여 주는 XML 태그](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
<span data-ttu-id="d637a-p120">결과가 충족되면 패턴은 해당 개수 및 신뢰도를 반환합니다. 이 결과를 정책의 조건에서 사용할 수 있습니다. 중요한 정보 유형을 감지하는 조건을 정책에 추가하면 여기에 표시된 것처럼 개수 및 신뢰도를 편집할 수 있습니다. 신뢰도(일치 정확도라고도 함)는 이 항목의 뒷부분에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p120">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your policy. When you add a condition for detecting a sensitive information type to a policy, you can edit the count and confidence level as shown here. Confidence level (also called match accuracy) is explained later in this topic.</span></span>
  
![인스턴스 개수 및 일치 정확도 옵션](../media/sit-confidence-level.png)
  
<span data-ttu-id="d637a-p121">정규식을 만들 때 인식해야 하는 잠재적인 문제가 있을 수 있다는 사실을 고려해야 합니다. 예를 들어, 너무 많은 콘텐츠를 식별하는 regex를 작성하여 업로드하는 경우 성능에 영향을 줄 수 있습니다. 이러한 잠재적인 문제에 대한 자세한 내용은 뒷부분에 나오는 [인식해야 하는 잠재적인 유효성 검사 문제](#potential-validation-issues-to-be-aware-of)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-p121">When you create your regular expression, keep in mind that there are potential issues to be aware of. For example, if you write and upload a regex that identifies too much content, this can impact performance. To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span></span>
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a><span data-ttu-id="d637a-p122">추가 서비스를 요구해야 하는가? [Match 요소, minCount 속성]</span><span class="sxs-lookup"><span data-stu-id="d637a-p122">Do you want to require additional evidence? [Match element, minCount attribute]</span></span>

<span data-ttu-id="d637a-182">패턴은 IdMatch에 더해 Match 요소를 사용하여 키워드, regex, 날짜, 주소 등 추가적인 증빙을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-182">In addition to the IdMatch, a pattern can use the Match element to require additional supporting evidence, such as a keyword, regex, date, or address.</span></span>
  
<span data-ttu-id="d637a-p123">Pattern은 여러 개의 Match 요소를 포함할 수 있으며, 여러 개의 Match 요소는 Pattern 요소에 직접 포함하거나 Any 요소를 사용하여 조합할 수 있습니다. Match 요소는 암시적 AND 연산자로 연결합니다. 패턴이 일치하기 위해서는 모든 Match 요소가 충족되어야 합니다. Any 요소를 사용하여 AND 또는 OR 연산자를 사용할 수 있습니다(다른 섹션에서 상술).</span><span class="sxs-lookup"><span data-stu-id="d637a-p123">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element. Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched. You can use the Any element to introduce AND or OR operators (more on that in a later section).</span></span>
  
<span data-ttu-id="d637a-p124">선택적인 minCount 특성을 사용하여 각 Match 요소에 대해 검색되어야 하는 일치 인스턴스 수를 지정할 수 있습니다. 예를 들어, 키워드 목록에서 두 개 이상의 키워드가 검색된 경우에만 패턴이 충족되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p124">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements. For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span></span>
  
![minOccurs 특성을 갖는 Match 요소를 보여 주는 XML 태그](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a><span data-ttu-id="d637a-189">키워드 [Keyword, Group 및 Term 요소, matchStyle 및 caseSensitive 특성]</span><span class="sxs-lookup"><span data-stu-id="d637a-189">Keywords [Keyword, Group, and Term elements, matchStyle and caseSensitive attributes]</span></span>

<span data-ttu-id="d637a-p125">직원 ID와 같은 중요한 정보를 식별할 경우 흔히 중요한 증거로 키워드를 사용할 수 있습니다. 예를 들어, 9자리 숫자를 일치시키는 것 외에도, "카드", "배지", "ID"와 같은 단어를 찾을 수 있습니다. 이렇게 하려면 Keyword 요소를 사용합니다. Keyword 요소에는 여러 패턴 또는 엔터티의 여러 Match 요소에서 참조할 수 있는 ID 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p125">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence. For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID". To do this, you use the Keyword element. The Keyword element has an ID attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span></span>
  
<span data-ttu-id="d637a-p126">키워드는 Group 요소에 Term 요소 목록으로 포함됩니다. Group 요소에는 다음과 같은 두 값 중 하나를 갖는 matchStyle 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p126">Keywords are included as a list of Term elements in a Group element. The Group element has a matchStyle attribute with two possible values:</span></span>
  
- <span data-ttu-id="d637a-p127">**matchStyle="word"** word 일치는 공백 또는 다른 구분 기호로 둘러싸인 전체 단어를 식별합니다. 단어의 일부를 일치시키거나 아시아 언어의 단어를 일치시켜야 하는 경우가 아니면 항상 word를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p127">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters. You should always use word unless you need to match parts of words or match words in Asian languages.</span></span> 
    
- <span data-ttu-id="d637a-p128">**matchStyle="string"** string 일치는 무엇으로 둘러싸여 있는지에 관계없이 문자열을 식별합니다. 예를 들어, "id"는 "bid" 및 "idea"를 일치시킵니다. 아시아 단어를 일치시키거나 키워드를 다른 문자열의 일부로 포함할 수 있는 경우에만 string을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p128">**matchStyle="string"** String match identifies strings no matter what they're surrounded by. For example, "id" will match "bid" and "idea". Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span></span> 
    
<span data-ttu-id="d637a-201">마지막으로, 콘텐츠가 대소문자를 포함하는 키워드와 정확히 일치하도록 지정하려면 하도록 Term 요소의 caseSensitive 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-201">Finally, you can use the caseSensitive attribute of the Term element to specify that the content must match the keyword exactly, including lower- and upper-case letters.</span></span>
  
![키워드를 참조하는 Match 요소를 보여 주는 XML 태그](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a><span data-ttu-id="d637a-203">정규식 [Regex 요소]</span><span class="sxs-lookup"><span data-stu-id="d637a-203">Regular expressions [Regex element]</span></span>

<span data-ttu-id="d637a-p129">이 예제에서 직원 ID 엔터티는 이미 IdMatch 요소를 사용하여 패턴, 즉 공백으로 둘러싸인 9자리 숫자에 대한 정규식을 참조합니다. 또한 패턴은 Match 요소를 사용하여 미국 우편 번호 형식의 5자리 또는 9자리 숫자와 같은 증빙을 식별하기 위해 추가 Regex 요소를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p129">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern — a nine-digit number surrounded by whitespace. In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span></span>
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a><span data-ttu-id="d637a-206">날짜 또는 주소와 같은 추가 패턴 [기본 제공 함수]</span><span class="sxs-lookup"><span data-stu-id="d637a-206">Additional patterns such as dates or addresses [built-in functions]</span></span>

<span data-ttu-id="d637a-p130">내장된 민감한 정보 유형 외에도 민감한 정보 유형은 미국 날짜, EU 날짜, 만료 날짜 또는 미국 주소와 같은 확증적인 증거를 식별할 수 있는 내장 기능을 사용할 수도 있습니다. Microsoft 365는 사용자 지정 함수 업로드를 지원하지 않지만 사용자 지정 중요한 정보 유형을 만들 때 엔터티는 기본 제공 기능을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p130">In addition to the built-in sensitive information types, sensitive information types can also use built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address. Microsoft 365 does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span></span>
  
<span data-ttu-id="d637a-209">예를 들어, 직원 ID 배지에 채용 날짜가 있는 경우 이 사용자 지정 엔터티는 기본 제공 함수 `Func_us_date`를 날짜가 미국에서 일반적으로 사용되는 형식을 갖는 날짜를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-209">For example, an employee ID badge has a hire date on it, so this custom entity can use the built-in function  `Func_us_date` to identify a date in the format commonly used in the US.</span></span> 
  
<span data-ttu-id="d637a-210">자세한 내용은 [DLP 함수가 찾는 항목](what-the-dlp-functions-look-for.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-210">For more information, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
  
![기본 제공 함수를 참조하는 Match 요소를 보여 주는 XML 태그](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a><span data-ttu-id="d637a-212">다양한 증거 조합 [Any 요소, minMatches 및 maxMatches 특성]</span><span class="sxs-lookup"><span data-stu-id="d637a-212">Different combinations of evidence [Any element, minMatches and maxMatches attributes]</span></span>

<span data-ttu-id="d637a-p131">Pattern 요소에서 모든 IdMatch 및 Match 요소는 암시적 AND 연산자로 조인됩니다. 즉, 패턴이 충족되기 위해서는 모든 일치 항목이 충족되어야 합니다. 그렇지만 Any 요소를 통해 Match 요소를 그룹화하여 좀 더 유연한 일치 논리를 만들 수 있습니다. 예를 들어, Any 요소를 사용하여 자식 Match 요소를 모두 일치시키거나 모두 일치시키지 않거나 정확한 하위 집합만 일치시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p131">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator — all of the matches must be satisfied before the pattern can be satisfied. However, you can create more flexible matching logic by using the Any element to group Match elements. For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span></span>
  
<span data-ttu-id="d637a-p132">Any 요소에는 패턴이 일치되기 위해 충족되어야 하는 자식 Match 요소 수를 정의하는 데 사용할 수 있는 선택적 minMatches 및 maxMatches 특성이 있습니다. 이러한 특성은 일치를 위해 확인되는 증거 인스턴스 수가 아니라 충족되어야 하는 Match 요소의 수를 정의합니다. 특정 일치의 최소 인스턴스 수(예: 목록의 2개 키워드)를 정의하려면 Match 요소에 대해 minCount 특성을 사용합니다(위 내용 참조).</span><span class="sxs-lookup"><span data-stu-id="d637a-p132">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched. Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches. To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span></span>
  
### <a name="match-at-least-one-child-match-element"></a><span data-ttu-id="d637a-219">하나 이상의 하위 Match 요소 매치</span><span class="sxs-lookup"><span data-stu-id="d637a-219">Match at least one child Match element</span></span>

<span data-ttu-id="d637a-p133">최소 개수의 Match 요소만 충족되도록 요구하려는 경우 minMatches 특성을 사용할 수 있습니다. 실제로 Match 요소는 암시적 OR 연산자로 조인됩니다. 목록에서 미국 형식 날짜 또는 키워드가 발견되면 이 Any 요소가 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p133">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute. In effect, these Match elements are joined by an implicit OR operator. This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span></span>

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a><span data-ttu-id="d637a-223">자식 Match 요소의 정확한 하위 집합 일치</span><span class="sxs-lookup"><span data-stu-id="d637a-223">Match an exact subset of any children Match elements</span></span>

<span data-ttu-id="d637a-p134">정확한 개수의 Match 요소가 충족되어야 하는 경우 minMatches 및 maxMatches를 같은 값으로 설정할 수 있습니다. 이 Any 요소는 정확히 하나의 날짜 또는 키워드가 검색되어야만 충족되며, 일치 항목 수가 더 있으면 패턴이 일치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p134">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value. This Any element is satisfied only if exactly one date or keyword is found — any more than that, and the pattern won't be matched.</span></span>

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a><span data-ttu-id="d637a-226">어떤 자식 Match 요소와도 일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="d637a-226">Match none of children Match elements</span></span>

<span data-ttu-id="d637a-p135">패턴이 충족되기 위해 특정 증거가 없어야 하는 경우 minMatches와 maxMatches를 0으로 설정할 수 있습니다. 이 방식은 키워드 목록 또는 가양성을 나타낼 수 있는 기타 증거가 있는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p135">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0. This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span></span>
  
<span data-ttu-id="d637a-p136">예를 들어, 직원 ID 엔터티는 키워드 "card"를 찾습니다. 이것인 "ID card"를 나타낼 수 있기 때문입니다. 카드가 "credit card" 구에만 나타나면 해당 콘텐츠의 “card”는 “ID card”를 의미하지 않을 수 있습니다. 따라서 패턴을 충족하기 위해 제외하려는 용어 목록에 "credit card"를 키워드로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p136">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card". However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card". So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span></span>
  
```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a><span data-ttu-id="d637a-232">몇 가지 고유 용어 일치</span><span class="sxs-lookup"><span data-stu-id="d637a-232">Match a number of unique terms</span></span>

<span data-ttu-id="d637a-233">몇 가지 고유 용어를 일치시키려면 다음 예에 표시된 것처럼 *uniqueResults* 매개 변수를 사용하고 *true* 로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-233">If you want to match a number of unique terms, use the *uniqueResults* parameter, set to *true*, as shown in the following example:</span></span>

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

<span data-ttu-id="d637a-234">이 예에는 3개 이상의 고유 일치 항목을 사용하여 급여 수정 사항에 대해 패턴이 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-234">In this example, a pattern is defined for salary revision using at least three unique matches.</span></span> 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a><span data-ttu-id="d637a-p137">엔터티가 다른 증거와 얼마나 가까워야 하나요? [patternsProximity 특성]</span><span class="sxs-lookup"><span data-stu-id="d637a-p137">How close to the entity must the other evidence be? [patternsProximity attribute]</span></span>

<span data-ttu-id="d637a-p138">중요한 정보 유형은 직원 ID를 나타나는 패턴을 찾으며, 해당 패턴의 일부로 “ID”와 같은 키워드 등을 중요 증거로 찾습니다. 이 증거에 더 가까울수록 패턴이 실제 직원 ID일 확률이 높습니다. Entity 요소의 필수 patternsProximity 특성을 사용하여 패턴의 다른 증거가 엔터티에 얼마나 가까워야 하는지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p138">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID". It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID. You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span></span>
  
![patternsProximity 특성을 보여 주는 XML 태그](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
<span data-ttu-id="d637a-p139">엔터티의 각 패턴에 대해, patternsProximity 특성 값은 해당 패턴에 대해 지정된 다른 모든 Match의 IdMatch 위치로부터 거리(유니코드 문자)를 정의합니다. 근접 범위는 IdMatch 위치에 의해 고정되며, 범위는 IdMatch의 좌우로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p139">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern. The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span></span>
  
![근접 범위 다이어그램](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
<span data-ttu-id="d637a-p140">아래 예제에서는 근접 범위가 사용자 지정 엔터티에 대한 IdMatch 요소가 하나 이상의 키워드 또는 날짜 증빙 일치를 요구하는 패턴 일치에 어떤 영향을 미치는지를 보여 줍니다. ID2 및 ID3의 경우 근접 범위 내에서 증빙을 찾을 수 없거나 부분적인 증빙만 발견되므로 ID1만 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p140">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date. Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span></span>
  
![증빙 및 근접 범위 다이어그램](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
<span data-ttu-id="d637a-p141">전자 메일의 경우 메시지 본문과 각 첨부 파일이 별도 항목으로 취급됩니다. 즉, 근접 범위는 이러한 각 항목이 범위 너머까지 확장되지 않습니다. 각 항목(첨부 파일 또는 본문) 내에 idMatch 및 증빙이 둘 다 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p141">Note that for email, the message body and each attachment are treated as separate items. This means that the proximity window does not extend beyond the end of each of these items. For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span></span>
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a><span data-ttu-id="d637a-p142">각 패턴의 적정 신뢰 수준은 무엇인가? [confidenceLevel 속성, recommendedConfidence 속성]</span><span class="sxs-lookup"><span data-stu-id="d637a-p142">What are the right confidence levels for different patterns? [confidenceLevel attribute, recommendedConfidence attribute]</span></span>

<span data-ttu-id="d637a-p143">패턴이 더 많은 증거를 요구할수록 패턴이 일치될 때 실제 엔터티(예: 직원 ID)가 식별될 신뢰도는 더 높아집니다. 예를 들어, 매우 근접한 9자리 ID 숫자, 채용 날짜, 키워드를 요구하는 패턴의 경우 9자리 ID 숫자만 요구하는 패턴의 경우보다 신뢰도가 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p143">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched. For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span></span>
  
<span data-ttu-id="d637a-p144">Pattern 요소에는 필수 confidencelevel 특성이 있습니다. confidenceLevel 값(1에서 100 사이의 정수)을 엔터티의 각 패턴에 대한 고유 ID로 생각할 수 있습니다. 즉, 엔터티의 패턴에는 다른 신뢰도가 할당되어야 합니다. 정수 정밀도 값은 중요하지 않습니다. 준수 팀에서 허용하는 숫자만 선택하면 됩니다. 사용자 지정 중요한 정보 유형을 업로드한 후 DLP 정책을 만든 후에 생성한 규칙의 조건에서 이러한 신뢰도를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p144">The Pattern element has a required confidenceLevel attribute. You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity — the patterns in an entity must have different confidence levels that you assign. The precise value of the integer doesn't matter — simply pick numbers that make sense to your compliance team. After you upload your custom sensitive information type and then create a policy, you can reference these confidence levels in the conditions of the rules that you create.</span></span>
  
![다른 confidenceLevel 특성 값을 갖는 Pattern 요소를 보여 주는 XML 태그](../media/sit-xml-markedup-2.png)
  
<span data-ttu-id="d637a-259">Entity는 각 Pattern에 대핸 confidenceLevel 외에도 recommendedConfidence 속성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-259">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute.</span></span> <span data-ttu-id="d637a-260">권장 신뢰도 속성은 규칙의 신뢰도 수준 기본값이라고 생각하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-260">The recommended confidence attribute can be thought of as the default confidence level for the rule.</span></span> <span data-ttu-id="d637a-261">정책에서 규칙을 만들 때 규칙에서 사용할 신뢰도 수준을 지정하지 않은 경우에는 규칙이 해당 엔터티의 권장 신뢰도 수준을 사용하여 매치를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-261">When you create a rule in a policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span></span> <span data-ttu-id="d637a-262">RecommendedConfidence 속성은 규칙 패키지의 각 Entity ID에 대한 필수 항목입니다. 이 값이 없는 경우 중요한 정보 유형을 사용 하는 정책을 저장하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-262">Please note that the recommendedConfidence attribute is mandatory for each Entity ID in the Rule Package, if missing you won't be able to save policies that use the Sensitive Information Type.</span></span> 
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-compliance-center-localizedstrings-element"></a><span data-ttu-id="d637a-p146">준수 센터의 UI에서 다른 언어를 지원하려고 하나요? [LocalizedStrings 요소]</span><span class="sxs-lookup"><span data-stu-id="d637a-p146">Do you want to support other languages in the UI of the Compliance center? [LocalizedStrings element]</span></span>

<span data-ttu-id="d637a-p147">준수 팀에서 Microsoft 365 준수 센터를 사용하여 다른 로캘 및 다른 언어로 정책을 만드는 경우 사용자 지정 중요한 정보 유형의 지역화된 이름 및 설명 버전을 제공할 수 있습니다. 준수 팀에서 지원되는 언어로 Office 365를 사용하는 경우 UI에 지역화된 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p147">If your compliance team uses the Microsoft 365 Compliance center to create polices policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type. When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span></span>
  
![인스턴스 개수 및 일치 정확도 옵션](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="d637a-p148">Rules 요소는 사용자 지정 엔터티의 GUID를 참조하는 Resource 요소가 포함된 LocalizedStrings 요소를 포함해야 합니다. 마찬가지로, 각 Resource 요소는 각각이 langcode 특성을 사용하여 특정 언어에 대해 지역화된 문자열을 제공하는 하나 이상의 Name 및 Description 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p148">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity. In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span></span>
  
![LocalizedStrings 요소의 내용을 보여 주는 XML 태그](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
<span data-ttu-id="d637a-p149">규정 준수 센터의 UI에 사용자 지정 중요한 정보 유형이 표시될 때만 지역화된 문자열을 사용합니다. 키워드 목록 또는 정규식의 다른 지역화된 버전을 제공할 때는 지역화된 문자열을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p149">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Compliance center. You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span></span>
  
## <a name="other-rule-package-markup-rulepack-guid"></a><span data-ttu-id="d637a-273">다른 규칙 패키지 태그 [RulePack GUID]</span><span class="sxs-lookup"><span data-stu-id="d637a-273">Other rule package markup [RulePack GUID]</span></span>

<span data-ttu-id="d637a-p150">마지막으로, 각 RulePackage의 시작 부분에는 채워야 하는 일반적인 정보가 포함되어 있습니다. 다음 태그를 템플릿으로 사용하고 ". . ." 자리 표시자를 사용자 고유의 정보로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p150">Finally, the beginning of each RulePackage contains some general information that you need to fill in. You can use the following markup as a template and replace the ". . ." placeholders with your own info.</span></span>
  
<span data-ttu-id="d637a-p151">가장 중요한 점은 RulePack의 GUID를 생성해야 한다는 것입니다. 그뿐 아니라 엔터티의 GUID를 생성했을 것입니다. 이 GUID는 RulePack의 두 번째 GUID입니다. GUID를 생성하는 방법에는 몇 가지가 있지만 PowerShell에서 [guid]::NewGuid()를 입력하여 쉽게 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p151">Most importantly, you'll need to generate a GUID for the RulePack. Above, you generated a GUID for the entity; this is a second GUID for the RulePack. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span>
  
<span data-ttu-id="d637a-p152">Version 요소도 중요합니다. 처음으로 규칙 패키지를 업로드하면, Microsoft 365에서 버전 번호를 표시합니다. 나중에 규칙 패키지를 업데이트하고 새 버전을 업로드하는 경우 해당 버전 번호를 업데이트해야 합니다. 그렇지 않으면 Office 365에서 규칙 패키지를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p152">The Version element is also important. When you upload your rule package for the first time, Microsoft 365 notes the version number. Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
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
  . . .
 </Rules>
</RulePackage>

```

<span data-ttu-id="d637a-285">완료되면 RulePack 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-285">When complete, your RulePack element should look like this.</span></span>
  
![RulePack 요소를 보여 주는 XML 태그](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)
  
## <a name="changes-for-exchange-online"></a><span data-ttu-id="d637a-287">Exchange Online의 변경</span><span class="sxs-lookup"><span data-stu-id="d637a-287">Changes for Exchange Online</span></span>

<span data-ttu-id="d637a-p153">이전에는 Exchange Online PowerShell을 사용하여 DLP에 대한 사용자 지정 중요한 정보 유형을 가져왔습니다. 이제 사용자 지정 중요한 정보 유형은 Exchange 관리 센터와 규정 준수 센터 둘 다에서 사용할 수 있습니다. 이러한 기능 개선의 일부로, 규정 및 준수 센터 PowerShell을 사용하여 사용자 지정 중요한 정보 유형을 가져와야 하며, 더 이상 Exchange Powershell에서 가져올 수 없습니다. 사용자 지정 중요한 정보 유형은 이전과 마찬가지로 계속 작동하지만 규정 준수 센터의 사용자 지정 중요한 정보 유형에 대한 변경 내용이 Exchange 관리 센터에 반영되는 데 최대 1시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p153">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP. Now your custom sensitive information types can be used in both the Exchange admin center and the Compliance center. As part of this improvement, you should use Compliance center PowerShell to import your custom sensitive information types — you can't import them from the Exchange PowerShell anymore. Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Compliance center to appear in the Exchange admin center.</span></span>
  
<span data-ttu-id="d637a-292">규정 준수 센터에서 **[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** cmdlet을 사용하여 규칙 패키지를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-292">Note that in the Compliance center, you use the **[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** cmdlet to upload a rule package.</span></span> <span data-ttu-id="d637a-293">(이전에 Exchange 관리 센터에서는 **ClassificationRuleCollection**\` cmdlet을 사용했습니다.)</span><span class="sxs-lookup"><span data-stu-id="d637a-293">(Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span></span> 
  
## <a name="upload-your-rule-package"></a><span data-ttu-id="d637a-294">규칙 패키지 업로드</span><span class="sxs-lookup"><span data-stu-id="d637a-294">Upload your rule package</span></span>



<span data-ttu-id="d637a-295">규칙 패키지를 업로드하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-295">To upload your rule package, do the following steps:</span></span>
  
1. <span data-ttu-id="d637a-296">유니코드 인코딩을 사용하여 .xml 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-296">Save it as an .xml file with Unicode encoding.</span></span>
    
2. [<span data-ttu-id="d637a-297">규정 준수 센터 PowerShell에 연결하기</span><span class="sxs-lookup"><span data-stu-id="d637a-297">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
    
3. <span data-ttu-id="d637a-298">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-298">Use the following syntax:</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="d637a-299">이 예제에서는 C:\My Documents에서 MyNewRulePack.xml이라는 유니코드 XML 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-299">This example uploads the Unicode XML file named MyNewRulePack.xml from C:\My Documents.</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="d637a-300">구문과 매개 변수에 대한 자세한 내용은 [새로 만들기-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-300">For detailed syntax and parameter information, see [New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).</span></span>

   > [!NOTE]
   > <span data-ttu-id="d637a-301">지원되는 규칙 패키지의 최대 개수는 10개이지만 각 패키지에는 여러 중요한 정보 유형에 대한 정의가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-301">The maximum number of rule packages supported is 10, but each package can contain the definition of multiple sensitive information types.</span></span>

4. <span data-ttu-id="d637a-302">새로운 중요한 정보 유형을 성공적으로 만들었는지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-302">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="d637a-303">[DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet을 실행하여 새 규칙 패키지가 나열되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-303">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to verify the new rule package is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ``` 

   - <span data-ttu-id="d637a-304">[DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 중요한 정보 유형이 나열되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-304">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ``` 

     <span data-ttu-id="d637a-305">사용자 지정 중요한 정보 유형의 경우 게시자 속성 값은 Microsoft Corporation이 아닌 다른 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-305">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="d637a-306">\<Name\>(을)를 중요한 정보 유형의 이름 값(예: 직원 ID)으로 바꾸고 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-306">Replace \<Name\> with the Name value of the sensitive information type (example: Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a><span data-ttu-id="d637a-307">인식해야 할 잠재적인 유효성 검사 문제</span><span class="sxs-lookup"><span data-stu-id="d637a-307">Potential validation issues to be aware of</span></span>

<span data-ttu-id="d637a-p155">규칙 패키지 XML 파일을 업로드할 때 시스템은 XML의 유효성을 검사하고 알려진 잘못된 패턴 및 명확한 성능 문제를 확인합니다. 다음은 유효성 검사가 정규식에서 확인하는 몇 가지 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p155">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues. Here are some known issues that the validation checks for — a regular expression:</span></span>
  
- <span data-ttu-id="d637a-310">모든 항목을 일치시키는 "|" 표시는 비어 있는 일치로 간주되므로 정규식을 이 표시로 시작하거나 끝낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-310">Cannot begin or end with alternator "|", which matches everything because it's considered an empty match.</span></span>
    
  <span data-ttu-id="d637a-311">예를 들어, "|a" 또는 "b|"는 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-311">For example, "|a" or "b|" will not pass validation.</span></span>
    
- <span data-ttu-id="d637a-312">".{0,m}" 패턴은 기능이 없고 성능을 저하시키기만 하므로 정규식을 이 패턴으로 시작하거나 끝낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-312">Cannot begin or end with a ".{0,m}" pattern, which has no functional purpose and only impairs performance.</span></span>
    
  <span data-ttu-id="d637a-313">예를 들어, ".{0,50}ASDF" 또는 "ASDF.{0,50}"는 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-313">For example, ".{0,50}ASDF" or "ASDF.{0,50}" will not pass validation.</span></span>
    
- <span data-ttu-id="d637a-314">".{0,m}" 또는 ".{1,m}"을 그룹으로 사용할 수 없고, ".\*" 또는 ".+"를 그룹으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-314">Cannot have ".{0,m}" or ".{1,m}" in groups, and cannot have ".\*" or ".+" in groups.</span></span>
    
  <span data-ttu-id="d637a-315">예를 들어, "(.{0,50000})"은 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-315">For example, "(.{0,50000})" will not pass validation.</span></span>
    
- <span data-ttu-id="d637a-316">"{0,m}" 또는 "{1,m}" 리피터가 그룹으로 포함된 문자는 정규식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-316">Cannot have any character with "{0,m}" or "{1,m}" repeaters in groups.</span></span>
    
  <span data-ttu-id="d637a-317">예를 들어, "(a\*)"는 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-317">For example, "(a\*)" will not pass validation.</span></span>
    
- <span data-ttu-id="d637a-318">정규식을 ".{1,m}"으로 시작하거나 끝낼 수 없으며 "."만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-318">Cannot begin or end with ".{1,m}"; instead, use just "."</span></span>
    
  <span data-ttu-id="d637a-319">예를 들어, ".{1,m}asdf"는 유효성 검사를 통과하지 못하므로 ".asdf"만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-319">For example, ".{1,m}asdf" will not pass validation; instead, use just ".asdf".</span></span>
    
- <span data-ttu-id="d637a-320">바인딩되지 않은 리피터(예: "\*" 또는 "+")는 그룹으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-320">Cannot have an unbounded repeater (such as "\*" or "+") on a group.</span></span>
    
  <span data-ttu-id="d637a-321">예를 들어, "(xx)\*" 및 "(xx)+"는 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-321">For example, "(xx)\*" and "(xx)+" will not pass validation.</span></span>
  
- <span data-ttu-id="d637a-322">키워드의 길이는 최대 50자입니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-322">Keywords have a maximum of 50 characters in Length.</span></span>  <span data-ttu-id="d637a-323">이 값을 초과하는 그룹에 키워드가 있는 경우 제안된 솔루션은 용어 그룹을 [키워드 사전](./create-a-keyword-dictionary.md)으로 만들고 파일의 일치 또는 ID 일치 엔티티의 일부로 XML 구조 내에서 키워드 사전의 GUID를 참조하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-323">If you have a keyword within a Group exceeding this, a suggested solution is to create the Group of terms as a [Keyword Dictionary](./create-a-keyword-dictionary.md) and reference the GUID of the Keyword Dictionary within the XML structure as part of the Entity for Match or idMatch in the file.</span></span>

- <span data-ttu-id="d637a-324">각 사용자 지정 중요 정보 유형은 최대 2048개의 키워드를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-324">Each Custom Sensitive Information Type can have a maximum of 2048 keywords total.</span></span>

- <span data-ttu-id="d637a-325">단일 테넌트에서 키워드 사전의 최대 크기는 1MB로 압축됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-325">The maximum size of Keyword Dictionaries in a single tenant is 1 MB compressed.</span></span> <span data-ttu-id="d637a-326">사용자 지정 중요한 정보 유형을 생성할 때 필요한 횟수만큼 동일한 사전을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-326">Reference the same dictionary as many times as necessary when creating custom sensitive information types.</span></span> <span data-ttu-id="d637a-327">우선 중요한 정보 유형에 사용자 정의 키워드 목록을 만드는 것부터 시작하고 키워드 목록에 2048개 이상의 키워드가 있거나 키워드의 길이가 50자 이상인 경우 키워드 사전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-327">Start with creating custom keyword lists in the sensitive information type and use keyword dictionaries if you have more than 2048 keywords in a keyword list or a keyword is larger than 50 characters in length.</span></span>

- <span data-ttu-id="d637a-328">테넌트에는 최대 50개의 키워드 사전 기반 중요한 정보 유형이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-328">A maximum of 50 keyword dictionary based sensitive information types are allowed in a tenant.</span></span>

- <span data-ttu-id="d637a-329">각 엔티티 요소에 권장되는 신뢰 속성이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-329">Ensure each Entity element contains a recommendedConfidence attribute.</span></span>

- <span data-ttu-id="d637a-330">PowerShell cmdlet을 사용할 경우 약 1MB의 역직렬화된 데이터의 최대 반환 크기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-330">When using the PowerShell Cmdlet there is a maximum return size of the Deserialized Data of approximately 1 megabyte.</span></span>   <span data-ttu-id="d637a-331">규칙 팩 XML 파일 크기에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-331">This will affect the size of your rule pack XML file.</span></span> <span data-ttu-id="d637a-332">업로드된 파일을 최대 770킬로바이트로 제한하여 오류 없이 일관된 결과를 얻으려면 제안된 제한을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-332">Keep the uploaded file limited to a 770 kilobyte maximum as a suggested limit for consistent results without error when processing.</span></span>

- <span data-ttu-id="d637a-333">XML 구조에는 공백, 탭 또는 캐리지 리턴/라인피드 항목과 같은 문자를 포맷할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-333">The XML structure does not require formatting characters such as spaces, tabs, or carriage return/linefeed entries.</span></span>  <span data-ttu-id="d637a-334">업로드 시 공간을 최적화할 때 이 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-334">Take note of this when optimizing for space on uploads.</span></span> <span data-ttu-id="d637a-335">Microsoft Visual Code와 같은 도구는 XML 파일을 압축하기 위한 조인 라인 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-335">Tools such as Microsoft Visual Code provide join line features to compact the XML file.</span></span>
    
<span data-ttu-id="d637a-336">사용자 지정 중요한 정보 유형에 성능에 영향을 줄 수 있는 문제가 포함된 경우 업로드되지 않으며 다음 오류 메시지 중 하나가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-336">If a custom sensitive information type contains an issue that may affect performance, it won't be uploaded and you may see one of these error messages:</span></span>
  
- <span data-ttu-id="d637a-337">**예상보다 더 많은 콘텐츠와 일치하는 일반 수량자(예: '+', '\*')**</span><span class="sxs-lookup"><span data-stu-id="d637a-337">**Generic quantifiers which match more content than expected (e.g., '+', '\*')**</span></span>
    
- <span data-ttu-id="d637a-338">**어설션 둘러보기**</span><span class="sxs-lookup"><span data-stu-id="d637a-338">**Lookaround assertions**</span></span>
    
- <span data-ttu-id="d637a-339">**일반 수량자와의 복잡한 그룹화**</span><span class="sxs-lookup"><span data-stu-id="d637a-339">**Complex grouping in conjunction with general quantifiers**</span></span>
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a><span data-ttu-id="d637a-340">콘텐츠를 다시 크롤링하여 중요한 정보 식별</span><span class="sxs-lookup"><span data-stu-id="d637a-340">Recrawl your content to identify the sensitive information</span></span>

<span data-ttu-id="d637a-p160">Microsoft 365는 검색 크롤러를 사용하여 사이트 콘텐츠에서 중요한 정보를 식별하고 분류합니다. SharePoint Online 및 비즈니스용 OneDrive 사이트의 콘텐츠는 업데이트될 때마다 자동으로 다시 크롤링됩니다. 하지만 기존의 모든 콘텐츠에 있는 새로운 사용자 지정 중요한 정보 유형을 식별하려면 해당 콘텐츠를 다시 크롤링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p160">Microsoft 365 uses the search crawler to identify and classify sensitive information in site content. Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated. But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span></span>
  
<span data-ttu-id="d637a-344">Microsoft 365에서 전체 테넌트의 다시 크롤링을 수동으로 요청할 수 없으나 사이트 모음, 목록 또는 라이브러리에 대해서는 다시 크롤링을 요청할 수 있습니다. [사이트, 라이브러리 또는 목록의 크롤링 및 다시 인덱싱을 수동으로 요청](/sharepoint/crawl-site-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-344">In Microsoft 365, you can't manually request a recrawl of an entire tenant, but you can do this for a site collection, list, or library — see [Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content).</span></span>
  
## <a name="remove-a-custom-sensitive-information-type"></a><span data-ttu-id="d637a-345">사용자 지정 중요한 정보 유형 제거</span><span class="sxs-lookup"><span data-stu-id="d637a-345">Remove a custom sensitive information type</span></span>

> [!NOTE]
> <span data-ttu-id="d637a-346">사용자 지정 중요한 정보 유형을 제거하기 전에 DLP 정책이나 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)이 중요한 정보 유형을 계속 참조하지 않는 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-346">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

<span data-ttu-id="d637a-347">규정 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형을 제거하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-347">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="d637a-p161">**개별 사용자 지정 중요한 정보 유형 제거**: [사용자 지정 중요한 정보 유형 수정](#modify-a-custom-sensitive-information-type)에서 설명하는 방법을 사용합니다. 사용자 지정 중요한 정보 유형을 포함하는 사용자 지정 규칙 패키지를 내보내고 XML 파일에서 중요한 정보 유형을 제거하고 기존 사용자 지정 규칙 패키지에 업데이트된 XML 파일을 다시 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p161">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type](#modify-a-custom-sensitive-information-type). You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="d637a-350">**사용자 지정 규칙 패키지 및 여기에 포함된 모든 사용자 지정 중요한 정보 유형 제거**: 이 방법은 이 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-350">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

1. [<span data-ttu-id="d637a-351">규정 준수 센터 PowerShell에 연결하기</span><span class="sxs-lookup"><span data-stu-id="d637a-351">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="d637a-352">사용자 지정 규칙 패키지를 제거하려면 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-352">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="d637a-353">Name 값(모든 언어) 또는 `RulePack id` (GUID) 값을 사용하여 규칙 패키지를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-353">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="d637a-354">이 예제에서는 "Employee ID Custom Rule Pack"이라는 규칙 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-354">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="d637a-355">구문과 매개 변수에 대한 자세한 내용은 [제거-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-355">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="d637a-356">사용자 지정 중요한 정보 유형을 성공적으로 제거했는지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-356">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="d637a-357">[DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet을 실행하고 이 규칙 패키지가 더 이상 나열되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-357">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="d637a-358">[DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 제거된 규칙 패키지에서 더 이상 중요한 정보 유형이 나열되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-358">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="d637a-359">사용자 지정 중요한 정보 유형의 경우 게시자 속성 값은 Microsoft Corporation이 아닌 다른 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-359">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="d637a-360">\<Name\>(을)를 중요한 정보 유형의 이름 값(예: 직원 ID)으로 바꾸고 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 중요한 정보 유형이 더 이상 나열되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-360">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="modify-a-custom-sensitive-information-type"></a><span data-ttu-id="d637a-361">사용자 지정 중요한 정보 유형 수정</span><span class="sxs-lookup"><span data-stu-id="d637a-361">Modify a custom sensitive information type</span></span>

<span data-ttu-id="d637a-362">규정 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형을 수정하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-362">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="d637a-363">XML 파일에 사용자 지정 중요한 정보 유형을 포함하는 기존 규칙 패키지를 내보냅니다. (또는 기존 XML 파일이 있는 경우이를 내보냅니다)</span><span class="sxs-lookup"><span data-stu-id="d637a-363">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="d637a-364">내보낸 XML 파일의 사용자 지정 중요한 정보 유형을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-364">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="d637a-365">기존 규칙 패키지에 업데이트된 XML 파일을 다시 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-365">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="d637a-366">규정 준수 센터 PowerShell에 연결하려면 [규정 준수 센터 PowerShell에 연결하기](/powershell/exchange/exchange-online-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-366">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="d637a-367">1단계: XML 파일로 기존 규칙 패키지 내보내기</span><span class="sxs-lookup"><span data-stu-id="d637a-367">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="d637a-368">XML 파일의 복사본이 있는 경우(예: XML 파일을 만들고 가져온 경우) 다음 단계로 건너 뛰고 XML 파일을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-368">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="d637a-369">아직 모르는 경우 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 사용자 지정 규칙 패키지의 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-369">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="d637a-p162">기본 제공 민감한 정보 유형이 들어있는 기본 제공 규칙 패키지의 이름은 Microsoft Rule Package입니다. 규정 준수 센터 UI에서 만든 사용자 지정 중요한 정보 유형이 포함된 규칙 패키지의 이름은 Microsoft.SCCManaged.CustomRulePack입니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-p162">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="d637a-372">[DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet을 사용하여 사용자 지정 규칙 패키지를 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-372">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="d637a-373">예를 들어, 규칙 패키지의 이름이 "Employee ID Custom Rule Pack"인 경우 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-373">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="d637a-374">[Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet을 실행하여 사용자 지정 규칙 패키지를 XML 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-374">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="d637a-375">이 예제에서는 규칙 패키지를 C:\My Documents 폴더의 ExportedRulePackage.xml 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-375">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="d637a-376">2단계: 내보낸 XML 파일의 중요한 정보 유형 수정</span><span class="sxs-lookup"><span data-stu-id="d637a-376">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="d637a-377">XML 파일의 중요한 정보 유형 및 파일의 기타 요소는 이 항목의 앞부분에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-377">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="d637a-378">3단계: 기존 규칙 패키지에 업데이트된 XML 파일 다시 가져오기</span><span class="sxs-lookup"><span data-stu-id="d637a-378">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="d637a-379">업데이트된 XML을 기존 규칙 패키지로 가져오려면 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-379">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="d637a-380">구문과 매개 변수에 대한 자세한 내용은 [설정-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d637a-380">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>

## <a name="reference-rule-package-xml-schema-definition"></a><span data-ttu-id="d637a-381">참조: 규칙 패키지 XML 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="d637a-381">Reference: Rule package XML schema definition</span></span>

<span data-ttu-id="d637a-382">아래 태그를 복사하여 XSD 파일로 저장하면 규칙 패키지 XML 파일의 유효성 검사를 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d637a-382">You can copy this markup, save it as an XSD file, and use it to validate your rule package XML file.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce"
           xmlns:xs="https://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>
```

## <a name="more-information"></a><span data-ttu-id="d637a-383">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d637a-383">More information</span></span>

- [<span data-ttu-id="d637a-384">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="d637a-384">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="d637a-385">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="d637a-385">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="d637a-386">DLP 함수가 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="d637a-386">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
