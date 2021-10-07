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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 사용자 지정 중요한 정보 유형으로 인코딩할 수 있는 필터 목록을 제공합니다.
ms.openlocfilehash: 3c91ff4a31f8e80b4798743169d5c30195dcdcde
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175002"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>사용자 지정 중요한 정보 유형 필터 참조

Microsoft에서는 사용자 지정 SIT(중요한 정보 유형)를 만드는 동안 필터 또는 추가 검사를 정의할 수 있습니다.

## <a name="list-of-supported-filters-and-use-cases"></a>지원되는 필터 및 사용 사례 목록

### <a name="alldigitssame-exclude"></a>AllDigitsSame 제외

설명: 111-111-111과 같은 모든 숫자를 중복 숫자로 111111111 일치 항목을 제외할 수 있습니다.

필터 정의
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

엔터티 수준에서 규칙 패키지에서 사용
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

패턴 수준에서 규칙 패키지에 사용
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

설명: 엔터티의 시작 문자를 정의할 수 있습니다. 포함 및 제외의 두 가지 변형이 있습니다.

예를 들어 다음과 같이 목록에서 0500, 91, 091, 010으로 시작하는 숫자를 제외합니다.

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

이 xml을 사용할 수 있습니다.

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
예를 들어 다음과 같이 목록에 0500, 91, 091, 0100으로 시작하는 숫자를 포함합니다. 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

이 xml을 사용할 수 있습니다.

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

설명: 엔터티의 끝 문자를 정의할 수 있습니다. 

예를 들어 다음과 같이 목록에서 0500,91,091, 0100으로 끝나는 숫자를 제외합니다.

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

이 xml을 사용할 수 있습니다.

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

예를 들어 다음과 같은 목록에 0500, 91, 091, 0100으로 끝나는 숫자를 포함합니다.

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

이 xml을 사용할 수 있습니다.

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

설명: 특정 일치를 금지하여 규칙이 트리거되지 않도록 할 수 있습니다. 예를 들어 유효한 4111111111111111 일치 목록에서 제외합니다.

예를 들어 다음과 같은 목록에서 4111111111111111 3241891031113111 신용 카드 번호를 제외합니다.

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

이 xml을 사용할 수 있습니다.

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

예를 들어 다음과 같은 목록에 4111111111111111 3241891031113111 신용 카드 번호를 포함하기 위해 다음을 들 수 있습니다.

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

이 xml을 사용할 수 있습니다.

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>TextMatchFilter Prefix

설명: 항상 포함하거나 제외해야 하는 이전 문자를 정의할 수 있습니다. 예를 들어 신용 카드 번호 앞에 'Order ID:'가 있는 경우 유효한 일치에서 일치를 제거합니다.

예를 들어 다음과 같은 목록에서 전화  번호가 있는  전화 번호의 발생을 제외하고 전화 번호 앞에 문자열로 전화를 거는 경우를 제외합니다.

- 전화 번호 091-8974-653278
- 전화 45-124576532-123
- 45-124576532-123

이 xml을 사용할 수 있습니다.

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

예를 들어 신용 카드 번호  앞에 신용 카드 및 카드 **#** 문자열이 있는 항목은 다음과 같은 목록에 포함됩니다.

- 신용 카드 45-124576532-123 
- 45-124576532-123(전화 번호일 수 있습니다.

이 xml을 사용할 수 있습니다.

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

### <a name="textmatchfilter-suffix"></a>TextMatchFilter 접미사

설명: 항상 포함하거나 제외해야 하는 다음 문자를 정의할 수 있습니다. 예를 들어 신용 카드 번호 다음에 '/xuid'가 오면 유효한 일치에서 일치를 제거합니다.

예를 들어 다음과 같이 목록에 접미사로 4자리 숫자 인스턴스가 5개 더 있는 경우 상위 제외 발생 수를 제외합니다.

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

이 xml을 사용할 수 있습니다.

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
예를 들어 이 목록의 항목과 같이 **/xuidsuffix가** 뒤따를 경우 발생을 제외합니다.

- 1234-5678-9321 /xuid
- 1234-5678-9321

이 xml을 사용할 수 있습니다.

''xml <Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group> </Keyword>
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

## <a name="using-filters-in-rule-packages"></a>규칙 패키지에 필터 사용

필터는 전체 SIT 또는 패턴에서 정의할 수 있습니다. 다음은 몇 가지 코드니켓 예제입니다. 

### <a name="at-sensitive-information-type-level"></a>중요한 정보 유형 수준에서

Entity의 필터 - 모든 자식 패턴을 다루게 됩니다.

필터는 해당 엔터티/중요한 유형의 패턴으로 분류된 모든 인스턴스에 적용됩니다. 

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>중요한 정보 유형 수준의 개별 패턴

패턴 수준에서만 필터를 사용합니다.

필터는 패턴과 일치하는 인스턴스에 적용됩니다.

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>중요한 정보 유형 수준에서 해당 엔터티의 일부 패턴에 대한 추가 필터

엔터티 + 패턴의 필터

필터는 해당 엔터티/중요한 유형의 패턴으로 분류된 모든 인스턴스에 적용됩니다.  패턴 수준 필터는 해당 패턴과 일치하는 인스턴스를 필터링합니다.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>추가 정보

- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)

- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)

- [DLP 함수가 찾는 항목](what-the-dlp-functions-look-for.md)
