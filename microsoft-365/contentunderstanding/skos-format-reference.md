---
title: SharePoint 분류에 대한 SKOS 형식 참조
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ms.localizationpriority: high
description: SharePoint 분류에 대한 SKOS 형식 참조
ms.openlocfilehash: 95183b64d76a70f69d08cd5a3c9dcf76f4e83bce
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747659"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SharePoint 분류에 대한 SKOS 형식 참조

본 문서는 [SharePoint 분류](/dotnet/api/microsoft.sharepoint.taxonomy)를 나타내는 데 사용되는 RDF 용어를 포함하고 있으며 [SKOS](https://www.w3.org/TR/skos-primer/)를 기반으로 합니다. 이 RDF 구문을 직렬화하려면 RDF [TURTLE](https://www.w3.org/TR/turtle/)을 사용하세요.

다음 표에서 [SharePoint 분류](/dotnet/api/microsoft.sharepoint.taxonomy) 용어에 해당하는 [SKOS](https://www.w3.org/TR/skos-primer/)를 표시합니다. SharePoint는 해당하는 SharePoint 분류가 없는 [SKOS](https://www.w3.org/TR/skos-primer/) 값을 지원하지 않습니다.

|SharePoint 분류|해당하는 SKOS|
|:-----------------|:--------------|
|sharepoint-taxonomy:Term|skos:Concept|
|sharepoint-taxonomy:TermSet|skos:ConceptScheme|
|sharepoint-taxonomy:inTermSet|skos:inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos:topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:description|skos:definition|
|sharepoint-taxonomy:parent|skos:broader|
|sharepoint-taxonomy:child|skos:narrower|

다음 표는 [OWL](https://www.w3.org/TR/owl2-primer/)에서 파생된 SharePoint 분류 용어의 엔터티입니다.

|SharePoint 분류 용어|OWL에서 파생|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint 분류 용어

분류는 공식 분류 체계입니다. 분류는 요소를 설명하는 단어, 레이블, 용어를 그룹화하고 해당 그룹을 계층 구조로 정렬합니다.

**sharepoint-taxonomy:Term**

관리된 메타데이터 계층 구조에서 Term 또는 Keyword를 나타냅니다.

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)는 SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)의 원자성 단위입니다. 각 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)는 [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group)에 속한 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 속해 있습니다.

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)을 정의하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)은 필수적으로 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 내에 존재합니다. DefaultLabel은 시각적 표현에 표시되는 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 이름입니다. [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)을 정의하는 데 필요한 필드에는 다음이 있습니다.

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)은 다음 사항을 수행할 수 있습니다.

- 동일한 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 속해 있는 두 가지 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)과 제공된 다른 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)과 계층적으로 관련될 수 있습니다.
- 여러 하위 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)이 있지만 하나의 상위 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)만 가집니다.
- topLevelTermOf [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 경우 상위 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)이 정의되지 않습니다.
- [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어 당 하나의 defaultLabel이 있습니다.
- 상위 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)이 포함되지 않거나 topLevelTermOf [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)이 아닌 경우 존재하지 않습니다.
- 동일한 계층 수준에 고유한 defaultLabel이 있어야 합니다.

**sharepoint-taxonomy:TermSet**

"TermSet" 이라는 계층적 또는 일련의 용어 개체 집합을 나타냅니다.

이름에서 알 수 있듯이 TermSet은 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)의 집합입니다. [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)의 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)은 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 속해 있어야 합니다. [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)은 독립적으로 존재할 수 없습니다.

[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 정의하는 구문은 다음과 같습니다.

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)은 [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group)에서 논리적으로 함께 그룹화됩니다. [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 정의하는 데 필요한 필드에는 다음이 있습니다.

- sharepoint-taxonomy:termSetName

제공된 termSetName이 [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) 내에서 고유하지 않은 경우 SharePoint는 이름 끝에 숫자를 추가하여 termSetName의 고유성을 유지합니다.

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint는 이 속성을 사용하여 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에서 최상위 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)을 매핑합니다. 이는 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) 계층에 대한 진입점입니다. 이 항목은 sharepoint-taxonomy:topLevelTermOf와 역 관계입니다.

이를 정의하는 구문은 다음과 같습니다.

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> 상위 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)의 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)을 정의할 수 없습니다.

**sharepoint-taxonomy:topLevelTermOf**

sharepoint-taxonomy:topLevelTermOf는 sharepoint-taxonomy:hasTopLevelTerm과 역 관계입니다.

이를 정의하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

이를 사용하여 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)을 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 매핑합니다. [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)은 단일 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에만 존재할 수 있습니다. [용어를 정의](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)하는 경우 SharePoint에서 해당 속성이 필요합니다.

## <a name="required-labels"></a>필수 레이블

조직에서 관리된 메타데이터를 사용하기 전에 신중하게 계획해야 할 수 있습니다. 수행해야 하는 계획의 양은 분류의 공식적인 정도에 따라 다릅니다. 또한 메타데이터에 적용할 제어 정도에 따라서도 다릅니다. 각 계층 수준에서 Term이나 TermSet의 필수 레이블을 구성해야 합니다.

Term에는 기본 언어로 레이블이 하나 이상 포함될 수 있으며 기본 언어가 아닌 경우 1개 이상의 레이블이 있거나 레이블이 없을 수 있습니다. 용어에 언어 레이블이 있는 경우 레이블 중 하나는 기본 레이블이어야 합니다.

**sharepoint-taxonomy:defaultLabel**

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)의 필수 매개 변수인 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)에 이 기본 어휘 레이블을 사용합니다. [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)를 시각적으로 나타내는 데 사용합니다.

DefaultLabel을 정의하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel에는 문자열 및 언어 태그의 두 부분이 포함되어 있습니다. 언어는 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어 중 하나여야 합니다. DefaultLabel은 동일한 계층 수준에서 동일한 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 모든 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대해 고유해야 합니다.

**sharepoint-taxonomy:termSetName**

현재 TermSet 개체의 이름을 가져오고 설정합니다.

[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어에 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대한 어휘 레이블입니다. [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대한 필수 매개 변수입니다. [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 시각적으로 나타내기 위해 사용합니다.

termSetName을 정의하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

현재 TermSet 개체의 속성 이름을 가져오고 설정합니다.

이는 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어에서 sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet에 대한 어휘 레이블입니다.

sharepoint-taxonomy:propertyName은 CustomProperty의 키로 간주됩니다.

propertyName을 정의하는 구문은 다음과 같습니다.

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>선택적 레이블

분류에 선택적 레이블을 추가할 수도 있습니다.

**sharepoint-taxonomy:otherLabel**

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대한 대체 어휘 레이블입니다.

otherLabel을 정의하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>의미 관계

분류는 계층적이며 때때로 단순한 "관련 용어" 연관 관계를 가지지만 일부는 "의미 관계" 또는 사용자 지정 관계를 가지기도 합니다.

**sharepoint-taxonomy:parent**

이 항목은 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)을 다른 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)과 계층적으로 연결합니다. [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)은 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 최상위 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)일 수 있지만 그렇지 않은 경우 상위 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)이 있어야 합니다.

상위 항목을 정의하는 구문은 다음과 같습니다.

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

즉 TermA가 상위 항목이 될 수 있으며 TermA가 하위 항목이 될 수 있음을 의미합니다.

**sharepoint-taxonomy:child**

개체는 하나 이상의 하위 TermSet 인스턴스를 포함하며 TermSet 속성을 통해 액세스할 수 있습니다. 이 클래스는 새 하위 TermSet 개체를 만드는 방법을 제공합니다. 하위 Term 및 TermSet 인스턴스 편집 권한은 그룹에서 지정됩니다.

이는 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)을 다른 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)과 계층적으로 관련되게 합니다.

하위 항목을 정의하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

즉 TermA가 상위 항목이 될 수 있으며 TermA가 하위 항목이 될 수 있음을 의미합니다.

## <a name="documentation-notes"></a>문서 노트

이 섹션에서는 Microsoft.SharePoint.Taxonomy Namespace에서 상세하게 나온 분류에 대해 설명합니다.

**sharepoint-taxonomy:description**

이는 [SharePoint 분류](/dotnet/api/microsoft.sharepoint.taxonomy) 용어 엔터티에 대한 자세한 설명입니다.

설명을 추가하는 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>사용자 지정 속성

읽기 전용 사전에서 현재 Term 개체에 대한 사용자 지정 속성 개체의 컬렉션을 가져옵니다.

사용자 지정 속성은 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대해 정의할 수 있는 키 값 쌍으로서 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대해 상세히 설명합니다. SharePoint는 propertyName에 대한 도움말이 있는 사용자 지정 속성의 키를 지정합니다.

**sharepoint-taxonomy:CustomPropertyForTermSet**

이를 정의하는 구문은 다음과 같습니다.

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대한 사용자 지정 속성을 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)함께 사용해야 하는 경우 해당 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)을 다른 위치에서 재사용한 다음 SharedCustomPropertyForTerm에서 정의해야 합니다.

이를 정의하는 구문은 다음과 같습니다.

```SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대한 사용자 지정 속성을 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)함께 사용하지 않아야 하는 경우 해당 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)을 다른 위치에서 재사용한 다음 LocalCustomPropertyForTerm에서 정의해야 합니다.

이를 정의하는 구문은 다음과 같습니다.

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>데이터 속성

각 계층 수준에서 Term이나 TermSet의 특정 데이터 속성을 구성해야 합니다.

**sharepoint-taxonomy:isAvailableForTagging**

이 속성을 사용하여 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 SharePoint 목록 및 라이브러리에서 사용할 수 있는지 여부를 지정할 수 있습니다.

이에 대한 구문은 다음과 같습니다.

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>도메인 및 범위

아래 표에서는 SharePoint 분류 용어의 도메인 및 범위에 대해 설명합니다.

|조건부/동사|의미|도메인|범위|
|:--------------|:------|:-----|:----|
inTermSet|용어 집합에 속함|용어|용어 집합|
inTermGroup|용어 그룹에 속함|TermSet|TermGroup|
topLevelTermOf|최상위 용어|용어|TermSet|
hasTopLevelTerm|최상위 용어 보유|용어 집합|용어|
termSetName|용어 집합에 이름이 있음|용어|일반 리터럴|
defaultLabel|용어에 기본 레이블이 있음|용어|일반 리터럴|
otherLabel|용어에 기타 레이블이 있음|용어|일반 리터럴|
propertyName|속성 레이블이 있음|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |부울, 문자열, 정수, 소수, 실수|
|description|설명 있음|모두|일반 리터럴|
|parent|상위 용어 있음|용어|용어|
|하위|하위 용어 있음|용어|용어|
|isAvailableForTagging|태그 지정 가능|용어, 용어 집합|부울|
|SharedCustomPropertyForTerm|공유 사용자 지정 속성 있음|용어|부울, 문자열, 정수, 소수, 실수|
|LocalCustomPropertyForTerm|로컬 사용자 지정 속성 있음|용어|부울, 문자열, 정수, 소수, 실수|
|CustomPropertyForTermSet|사용자 지정 속성 있음|TermSet|부울, 문자열, 정수, 소수, 실수|

[SKOS](https://www.w3.org/TR/skos-primer/)는 [SharePoint 분류](/dotnet/api/microsoft.sharepoint.taxonomy)에서 허용하지 않는 유효한 시나리오를 제공합니다.

- 계층 중복 - [SKOS](https://www.w3.org/TR/skos-primer/) 개념이 여러 광범위한 개념에 동시에 부여될 수 있지만 sharepoint-taxonomy:Term은 하나의 sharepoint-taxonomy:parent만 가지므로 Term의 주기적은 의존은 허용되지 않습니다.
- 분리된 용어는 SharePoint 분류에서 허용되지 않습니다. 모든 sharepoint-taxonomy:Term은 sharepoint-taxonomy:parent를 가지거나 sharepoint-taxonomy:topLevelTermOf a TermSet이어야 합니다.
- SharePoint 분류는 결합형 관계를 지원하지 않습니다.
- SharePoint 분류는 sharepoint-taxonomy:parent 및 sharepoint-Taxonomy:child 두 가지 유형의 계층 관계만 허용합니다.
- [SKOS](https://www.w3.org/TR/skos-primer/)와 다르게 SharePoint 분류 용어의 계층적 관계는 동일한 TermSet 내에서만 Term으로 설정될 수 있습니다.

## <a name="see-also"></a>참고 항목

[SKOS 기반 형식을 사용하여 용어 집합 가져오기](import-term-set-skos.md)