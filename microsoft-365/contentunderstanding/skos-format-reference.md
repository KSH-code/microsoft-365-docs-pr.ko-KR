---
title: SharePoint 분류에 대 한 오디오 os 형식 참조
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SharePoint 분류에 대 한 오디오 os 형식 참조
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296082"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SharePoint 분류에 대 한 오디오 os 형식 참조

이 [문서에는](https://www.w3.org/TR/skos-primer/) [SharePoint 분류법](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 을 나타내는 데 사용 되는 RDF 어휘가 나와 있습니다. 이 RDF 구문을 직렬화 하려면 RDF [거북](https://www.w3.org/TR/turtle/)을 사용 합니다.

다음 표에는 [SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 어휘의과 동등한 [os](https://www.w3.org/TR/skos-primer/) 가 나와 있습니다. SharePoint에서는 SharePoint 분류가 일치 하지 않는 기능 [운영 체제](https://www.w3.org/TR/skos-primer/) 값을 지원 하지 않습니다.

|SharePoint 분류|에 해당 하는 운영 체제|
|:-----------------|:--------------|
|sharepoint-분류법: Term|오디오 os: 개념|
|sharepoint-분류법: TermSet|(고) os: ConceptScheme|
|sharepoint-분류법: inTermSet|(고) os: inScheme|
|sharepoint-분류법: hasTopLevelTerm|(고) os: hasTopConcept|
|sharepoint-분류법: topLevelTermOf|(고) os: topConceptOf|
|sharepoint-분류법: defaultLabel|(고) os: prefLabel|
|sharepoint-분류법: termSetName|(고) os: prefLabel|
|sharepoint-분류법: propertyName|(고) os: prefLabel|
|sharepoint-분류법: otherLabel|(고) os: altLabel|
|sharepoint-분류: 설명|(고) os: 정의|
|sharepoint-분류법: 상위|오디오 os: 더 넓게|
|sharepoint-분류법: child|(고) os: 좁게|

다음 표에는 [OWL](https://www.w3.org/TR/owl2-primer/)에서 파생 된 SharePoint 분류법 어휘의 엔터티가 표시 됩니다.

|SharePoint 분류 용어 모음|OWL에서 파생|
|:-----------------------------|:----------------------|
|sharepoint-분류법: Is사용 가능 For태깅|owl:datatypeproperty|
|sharepoint-분류법: SharedCustomPropertyForTerm|owl: ObjectProperty|
|sharepoint-분류법: LocalCustomPropertyForTerm|owl: ObjectProperty|
|sharepoint-분류법: CustomPropertyForTermSet|owl: ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint 분류 용어 모음

분류는 공식적인 분류 시스템입니다. 분류는 항목을 설명 하는 단어, 레이블 및 용어를 그룹화 한 다음 그룹을 계층 구조로 정렬 합니다.

**sharepoint-분류법: Term**

관리 되는 메타 데이터 계층 구조의 용어나 키워드를 나타냅니다.

[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 SharePoint [시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)의 원자성 단위입니다. 각 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)에 속하는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 에 속합니다. 

[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Compulsorily [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)내에 있습니다. DefaultLabel은 시각적 표현에 표시 되는 [용어의](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 이름입니다. [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 정의 하는 데 필요한 필드는 다음과 같습니다.

- sharepoint-분류법: defaultLabel
- sharepoint-분류법: inTermSet

다음과 같은 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 사용할 수 있습니다.

- 두 [용어가](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 모두 같은 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 제공 되는 다른 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 와 계층적으로 관련 되어 있어야 합니다.
- 하위 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)는 여러 개 있지만 상위 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)는 하나만 포함 해야 합니다.
- 상위 [용어가](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 정의 되어 있지 않은 경우 TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)입니다.
- [시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어 당 하나의 defaultlabel을 사용 합니다.
- 상위 [용어가](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)포함 되지 않고 TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)도 없는 경우에는 존재 하지 않습니다. 
- 같은 계층 구조 수준에 고유한 defaultLabel 포함 합니다.

**sharepoint-분류법: TermSet**

"TermSet"로 알려진 용어 개체의 계층적 또는 단순 집합을 나타냅니다.

이름에서 알 수 있듯이 TermSet은 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)집합입니다. [시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 의 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 속해야 합니다. [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 독립적으로 존재할 수 없습니다. 

[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 를 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 는 [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)에서 논리적으로 함께 그룹화 됩니다. [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 을 정의 하는 데 필요한 필드는 다음과 같습니다.

- sharepoint-분류법: termSetName

제공 된 termSetName가 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)내에서 고유 하지 않은 경우 sharepoint는 이름 끝에 번호를 추가 하 여 termSetName의 고유성을 유지 합니다.

**sharepoint-분류법: hasTopLevelTerm**

SharePoint는이 속성을 사용 하 여 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에서 가장 위쪽에 있는 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ( [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 계층 구조를 가리키는 진입점)를 매핑합니다. 이는 sharepoint 분류법: topLevelTermOf에 대 한 역 관계입니다. 

이를 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> 상위 [용어의](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)최상위 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 정의할 수 없습니다.

**sharepoint-분류법: topLevelTermOf**

Sharepoint-분류법: topLevelTermOf는 sharepoint 분류법: hasTopLevelTerm의 역함수입니다.

이를 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-분류법: inTermSet**

이를 사용 하 여 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 매핑합니다. [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 단일 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에만 존재할 수 있습니다. [용어를 정의 하는](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)경우 SharePoint에서이 속성을 사용 해야 합니다.

## <a name="required-labels"></a>필수 레이블

관리 되는 메타 데이터 사용을 시작 하기 전에 조직에서 신중한 계획을 수립할 수 있습니다. 수행 해야 하는 계획의 양은 분류의 공식적인 정도에 따라 달라 집니다. 또한 메타 데이터에 대해 적용 하려는 제어 정도에 따라 달라 집니다. 계층 구조의 각 수준에서 용어 또는 TermSet에 대해 필수 lables를 구성 해야 합니다.

용어에는 기본 언어로 레이블이 하나 이상 있을 수 있으며 기본이 아닌 언어로는 0 개 이상의 레이블이 있습니다. 용어에 언어 레이블이 있는 경우 레이블 중 하나가 기본 레이블 이어야 합니다.

**sharepoint-분류법: defaultLabel**

[용어의](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)필수 매개 변수인 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 에는이 기본 어휘 레이블을 사용 합니다. [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)를 시각적으로 표시 하는 데 사용 됩니다.

DefaultLabel을 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel에는 문자열 및 언어 태그와 같은 두 부분으로 구성 됩니다. 언어는 [시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어 중 하나 여야 합니다. DefaultLabel은 동일한 계층 구조 수준에서 같은 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 모든 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 에 대해 고유 해야 합니다.

**sharepoint-분류법: termSetName**

현재 TermSet 개체의 이름을 가져오고 설정 합니다.

[시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어로 된 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 어휘 레이블입니다. [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대 한 필수 매개 변수입니다. [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 시각적으로 나타내는 데 사용 합니다.

TermSetName를 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-분류법: propertyName**

현재 TermSet 개체의 속성 이름을 가져오고 설정 합니다.

Sharepoint 분류법: SharedCustomPropertyForTerm, sharepoint-분류법: LocalCustomPropertyForTerm 및 sharepoint-분류법: CustomPropertyForTermSet ( [시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어)에 대 한 어휘 레이블입니다.

Sharepoint-분류: propertyName은 CustomProperty의 키로 간주 됩니다.

PropetyName를 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>선택적 레이블

또한 분류에 선택적 레이블을 추가할 수 있습니다.

**sharepoint-분류법: otherLabel**

[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대 한 대체 어휘 레이블입니다. 

OtherLabel을 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>의미 관계

분류에는 계층적이 고 간단한 "관련 용어" 연관 관계가 있지만 일부는 "의미 관계" 또는 사용자 지정 관계가 있습니다. 

**sharepoint-분류법: 상위**

[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 계층적으로 다른 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)와 연결 합니다. [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 최상위 [용어만](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 될 수 있지만 상위 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)를 포함 하지 않아야 하는 경우가 있습니다. 

부모를 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

즉, TermA1에 부모 TermA가 있습니다. 이와 반비례 또한 TermA1은 TermA의 자식입니다. 부모-자식 관계가 inversible 관계입니다.

**sharepoint-분류법: child**

이 개체는 자식 TermSet 인스턴스를 하나 이상 포함 하며 TermSets 속성을 통해 액세스할 수 있습니다. 또한이 클래스는 새 자식 TermSet 개체를 만들기 위한 메서드를 제공 합니다. 하위 용어 및 TermSet 인스턴스 편집에 대 한 권한이 그룹에 지정 되어 있습니다. 

[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 계층적으로 다른 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)와 연결 합니다.

자식을 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

즉, TermA에 자식 TermA1가 있습니다. 이와 반비례 또한 TermA는 TermA1 부모-자식 관계 중 inversible 관계에 해당 합니다.

## <a name="documentation-notes"></a>문서 참고 사항

이 섹션에서는 Microsoft. 분류법 네임 스페이스에 자세히 설명 되어 있는 분류에 대해 알아봅니다.

**sharepoint-분류: 설명**

[SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 어휘 엔터티에 대 한 자세한 설명입니다. 

설명을 추가 하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>사용자 지정 속성

현재 용어 개체에 대 한 사용자 지정 속성 개체의 컬렉션을 읽기 전용 사전에서 가져옵니다.

사용자 지정 속성 [은 용어나](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대해 정의할 수 있는 키-값 쌍으로, [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대 한 설명을 추가로 설명 합니다. SharePoint는 propertyName에 대 한 도움말을 사용 하 여 사용자 지정 속성의 키를 지정 합니다.

**sharepoint-분류법: CustomPropertyForTermSet**

이를 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-분류법: SharedCustomPropertyForTerm**

용어에 대 한 사용자 지정 속성을 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)와 함께 [전달 해야 하](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 경우에는 다른 곳에서 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 다시 사용할 때 sharedcustompropertyforterm에서 정의 해야 합니다.

이를 정의 하는 구문은 다음과 같습니다.

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-분류법: LocalCustomPropertyForTerm**

용어에 대 한 사용자 지정 속성을 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)와 함께 사용할 필요가 없는 경우 다른 곳에서 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 다시 사용 하는 경우 [에는](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) localcustompropertyforterm에서 정의 해야 합니다.

이를 정의 하는 구문은 다음과 같습니다.

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>데이터 속성

계층 구조의 각 수준에서 용어 또는 TermSet에 대 한 특정 데이터 속성을 구성할 수 있습니다.

**sharepoint-분류법: Is사용 가능 For태깅**

이 방법을 사용 하 여 SharePoint 목록 및 라이브러리에서 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 를 사용할 수 있는지 여부를 지정 합니다.  

이에 대 한 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>도메인 및 범위

아래 표에는 SharePoint 분류 어휘의 도메인 및 범위에 대 한 설명이 나와 있습니다.

|조건자/동사|의미|도메인|Range|
|:--------------|:------|:-----|:----|
inTermSet|용어 집합|용어|용어 집합|
inTermGroup|용어 그룹|TermSet|TermGroup|
topLevelTermOf|가 최상위 수준인 경우|용어|TermSet|
hasTopLevelTerm|최상위 용어 포함|용어 집합|용어|
termSetName|용어 집합 이름|용어|일반 리터럴|
defaultLabel|용어에 기본 레이블이 있음|용어|일반 리터럴|
otherLabel|용어에 다른 레이블이 있습니다.|용어|일반 리터럴|
propertyName|속성 레이블 있음|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean, String, Integer, Decimal, Double|
|설명|설명 있음|전체|일반 리터럴|
|상위|부모 있음|용어|용어|
|하위|하위 있음|용어|용어|
|Isto For태깅|태그 지정 가능|용어, 용어 집합|부울|
|SharedCustomPropertyForTerm|공유 사용자 지정 속성 있음|용어|Boolean, string, Integer, Decimal, Double|
|LocalCustomPropertyForTerm|로컬 사용자 지정 속성 있음|용어|Boolean, String, Integer, Decimal, Double|
|CustomPropertyForTermSet|사용자 지정 속성 포함|TermSet|Boolean, String, Integer, Decimal, Double|

| [SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 에서 허용 하지 않는 [os](https://www.w3.org/TR/skos-primer/) 의 유효한 시나리오:

- 계층 구조 중복성-나머지 여러 개념에 동시에 연결할 수 있지만 sharepoint 분류법: 용어 [에는 하나의](https://www.w3.org/TR/skos-primer/) sharepoint 분류법만 있을 수 있으며, 따라서 순환 종속성도 허용 되지 않습니다.
- 고아 용어는 SharePoint 분류에서 허용 되지 않습니다. 모든 sharepoint-분류: 용어에는 sharepoint 분류법: parent가 있거나 sharepoint-분류법: topLevelTermOf a TermSet 이어야 합니다.
- SharePoint 분류법은 결합형 관계를 지원 하지 않습니다.
- SharePoint 분류법은 두 가지 유형의 계층 구조, 즉 sharepoint-분류법: parent 및 sharepoint-분류법: 하위만 사용할 수 있습니다. 
- 과 [(와) 달리,](https://www.w3.org/TR/skos-primer/) SharePoint 분류 어휘의 계층적 관계는 동일한 TermSet 내 에서만 용어를 사용 하 여 설정할 수 있습니다.

## <a name="see-also"></a>참고 항목

[운영 체제 기반 형식으로 된 용어 집합 가져오기](import-term-set-skos.md)

