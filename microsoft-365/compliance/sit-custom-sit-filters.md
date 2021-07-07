---
title: 사용자 지정 중요한 정보 유형 필터 참조
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 사용자 지정 중요한 정보 유형으로 인코딩할 수 있는 필터 목록을 제공합니다.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322970"
---
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="11037-103">사용자 지정 중요한 정보 유형 필터 참조</span><span class="sxs-lookup"><span data-stu-id="11037-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="11037-104">Microsoft에서는 사용자 지정 SIT(중요한 정보 유형)를 만드는 동안 필터 또는 추가 검사를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="11037-105">지원되는 필터 및 사용 사례 목록</span><span class="sxs-lookup"><span data-stu-id="11037-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="11037-106">AllDigitsSame 제외</span><span class="sxs-lookup"><span data-stu-id="11037-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="11037-107">설명: 111111111 또는 111-111-111과 같이 모든 숫자가 중복된 숫자로 있는 일치 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="11037-108">필터 정의</span><span class="sxs-lookup"><span data-stu-id="11037-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="11037-109">엔터티 수준에서 규칙 패키지에서 사용</span><span class="sxs-lookup"><span data-stu-id="11037-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="11037-110">패턴 수준에서 규칙 패키지에 사용</span><span class="sxs-lookup"><span data-stu-id="11037-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="11037-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="11037-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="11037-112">설명: 엔터티의 시작 문자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="11037-113">포함 및 제외의 두 가지 변형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="11037-114">예를 들어 다음과 같이 목록에서 0500, 91, 091, 010으로 시작하는 숫자를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="11037-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="11037-115">0500-4500-027</span></span>
- <span data-ttu-id="11037-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="11037-116">91564721450</span></span>
- <span data-ttu-id="11037-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="11037-117">91-8523697410</span></span>
- <span data-ttu-id="11037-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="11037-118">700-8956-7844</span></span>
- <span data-ttu-id="11037-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="11037-119">1000-3265-9874</span></span>
- <span data-ttu-id="11037-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="11037-120">0100-7892-3012</span></span>

<span data-ttu-id="11037-121">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-121">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
<span data-ttu-id="11037-122">예를 들어 다음과 같이 목록에 0500, 91, 091, 0100으로 시작하는 숫자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="11037-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="11037-123">0500-4500-027</span></span>
- <span data-ttu-id="11037-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="11037-124">91564721450</span></span>
- <span data-ttu-id="11037-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="11037-125">91-8523697410</span></span>
- <span data-ttu-id="11037-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="11037-126">700-8956-7844</span></span>
- <span data-ttu-id="11037-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="11037-127">1000-3265-9874</span></span>
- <span data-ttu-id="11037-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="11037-128">0100-7892-3012</span></span>

<span data-ttu-id="11037-129">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="11037-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="11037-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="11037-131">설명: 엔터티의 끝 문자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="11037-132">예를 들어 다음과 같이 목록에서 0500,91,091, 0100으로 끝나는 숫자를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="11037-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="11037-133">1234567891</span></span>
- <span data-ttu-id="11037-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="11037-134">1234-5678-0091</span></span>
- <span data-ttu-id="11037-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="11037-135">1234.4567.7091</span></span>
- <span data-ttu-id="11037-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="11037-136">1234-8091-4564</span></span>

<span data-ttu-id="11037-137">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-137">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="11037-138">예를 들어 다음과 같은 목록에 0500, 91, 091, 0100으로 끝나는 숫자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="11037-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="11037-139">1234567891</span></span>
- <span data-ttu-id="11037-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="11037-140">1234-5678-0091</span></span>
- <span data-ttu-id="11037-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="11037-141">1234.4567.7091</span></span>
- <span data-ttu-id="11037-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="11037-142">1234-8091-4564</span></span>

<span data-ttu-id="11037-143">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="11037-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="11037-144">TextMatchFilter Full</span></span>

<span data-ttu-id="11037-145">설명: 특정 일치를 금지하여 규칙이 트리거되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="11037-146">예를 들어 유효한 신용 카드 일치 목록에서 411111111111111111111111을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="11037-147">예를 들어 다음과 같은 목록에서 411111111111111111111111과 같은 신용 카드 번호를 제외하는 경우:</span><span class="sxs-lookup"><span data-stu-id="11037-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="11037-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="11037-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="11037-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="11037-149">4111111111111111</span></span>
- <span data-ttu-id="11037-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="11037-150">3241891031113111</span></span>

<span data-ttu-id="11037-151">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-151">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="11037-152">예를 들어 다음과 같은 목록에 411111111111111111111111111과 같은 신용 카드 번호를 포함하기 위해 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="11037-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="11037-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="11037-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="11037-154">4111111111111111</span></span>
- <span data-ttu-id="11037-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="11037-155">3241891031113111</span></span>

<span data-ttu-id="11037-156">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="11037-157">TextMatchFilter Prefix</span><span class="sxs-lookup"><span data-stu-id="11037-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="11037-158">설명: 항상 포함하거나 제외해야 하는 이전 문자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="11037-159">예를 들어 신용 카드 번호 앞에 'Order ID:'가 있는 경우 유효한 일치에서 일치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="11037-160">예를 들어 다음과 같은 목록에서 전화  번호가 있는  전화 번호의 발생을 제외하고 전화 번호 앞에 문자열로 전화를 거는 경우를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="11037-161">전화 번호 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="11037-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="11037-162">전화 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="11037-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="11037-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="11037-163">45-124576532-123</span></span>

<span data-ttu-id="11037-164">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-164">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="11037-165">예를 들어 신용 카드 번호  앞에 신용 카드 및 카드 **#** 문자열이 있는 항목은 다음과 같은 목록에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11037-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="11037-166">신용 카드 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="11037-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="11037-167">45-124576532-123(전화 번호일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="11037-168">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-168">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="11037-169">TextMatchFilter 접미사</span><span class="sxs-lookup"><span data-stu-id="11037-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="11037-170">설명: 항상 포함하거나 제외해야 하는 다음 문자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="11037-171">예를 들어 신용 카드 번호 다음에 '/xuid'가 오면 유효한 일치에서 일치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="11037-172">예를 들어 다음과 같이 목록에 접미사로 4자리 숫자 인스턴스가 5개 더 있는 경우 상위 제외 발생 수를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="11037-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="11037-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="11037-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="11037-174">1234-5678-9321</span></span>

<span data-ttu-id="11037-175">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="11037-176">예를 들어 이 목록의 항목과 같이 **/xuidsuffix가** 뒤따를 경우 발생을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="11037-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="11037-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="11037-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="11037-178">1234-5678-9321</span></span>

<span data-ttu-id="11037-179">이 xml을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-179">you can use this xml</span></span>

<span data-ttu-id="11037-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="11037-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="11037-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="11037-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="11037-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="11037-182">/xuid</span></span></Term>
    <span data-ttu-id="11037-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="11037-183"></Group> </Keyword></span></span>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="11037-184">규칙 패키지에 필터 사용</span><span class="sxs-lookup"><span data-stu-id="11037-184">Using filters in rule packages</span></span>

<span data-ttu-id="11037-185">필터는 전체 SIT 또는 패턴에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11037-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="11037-186">다음은 몇 가지 코드니켓 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="11037-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="11037-187">중요한 정보 유형 수준에서</span><span class="sxs-lookup"><span data-stu-id="11037-187">At sensitive information type level</span></span>

<span data-ttu-id="11037-188">Entity의 필터 - 모든 자식 패턴을 다루게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11037-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="11037-189">필터는 해당 엔터티/중요한 유형의 패턴으로 분류된 모든 인스턴스에 적용됩니다. </span><span class="sxs-lookup"><span data-stu-id="11037-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="11037-190">중요한 정보 유형 수준의 개별 패턴</span><span class="sxs-lookup"><span data-stu-id="11037-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="11037-191">패턴 수준에서만 필터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="11037-192">필터는 패턴과 일치하는 인스턴스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="11037-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="11037-193">중요한 정보 유형 수준에서 해당 엔터티의 일부 패턴에 대한 추가 필터</span><span class="sxs-lookup"><span data-stu-id="11037-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="11037-194">엔터티 + 패턴의 필터</span><span class="sxs-lookup"><span data-stu-id="11037-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="11037-195">필터는 해당 엔터티/중요한 유형의 패턴으로 분류된 모든 인스턴스에 적용됩니다. </span><span class="sxs-lookup"><span data-stu-id="11037-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="11037-196">패턴 수준 필터는 해당 패턴과 일치하는 인스턴스를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="11037-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="11037-197">추가 정보</span><span class="sxs-lookup"><span data-stu-id="11037-197">More information</span></span>

- [<span data-ttu-id="11037-198">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="11037-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="11037-199">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="11037-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="11037-200">DLP 함수가 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="11037-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
