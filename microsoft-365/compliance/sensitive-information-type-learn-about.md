---
title: 중요한 정보 유형에 대해 자세히 알아보기
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: e125a6dfb35b7018b5f85100184c842da9231327
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407328"
---
# <a name="learn-about-sensitive-information-types"></a>중요한 정보 유형에 대해 자세히 알아보기

조직에서 제어하는 중요한 항목을 식별하고 분류하는 것은 정보 보호 분야 의 [첫 번째 단계입니다.](protect-information.md)  Microsoft 365는 항목을 분류할 수 있도록 다음 세 가지 방법으로 항목을 식별합니다.

- 사용자가 수동으로
- 중요한 정보 유형과 같은 자동화된 패턴 인식
- [기계 학습](classifier-learn-about.md)

중요한 정보 유형은 패턴 기반 분류자입니다. 또한 주민등의 보안, 신용 카드 또는 은행 계좌 번호와 같은 중요한 정보를 검색하여 중요한 항목을 식별합니다. 중요한 정보 유형 엔터티 정의를 [참조하세요.](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>중요한 정보 유형이 사용

- [데이터 손실 방지 정책](data-loss-prevention-policies.md) 
- [민감도 레이블](sensitivity-labels.md)
- [보존 레이블](retention.md)
- [커뮤니케이션 규정 준수](communication-compliance.md)
- [자동 레이블 지정 정책](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>중요한 정보 유형의 기본 부분

모든 중요한 정보 유형 엔터티는 다음 필드에 의해 정의됩니다.

- 이름: 중요한 정보 유형을 참조하는 방법
- description: 중요한 정보 유형이 찾는 내용 설명
- 패턴: 패턴은 중요한 정보 유형이 감지하는 것을 정의합니다. 다음 구성 요소로 구성됩니다.
    - Primary 요소 - 중요한 정보 유형이 찾는 주 요소입니다. 체크 um 유효성 **검사,** 키워드 목록, 키워드 사전 또는 함수가 있는 정규식일 수 **있습니다.**
    - 지원 요소 – 일치의 신뢰를 높이는 데 도움이 되는 증거 역할을 하는 요소입니다. 예를 들어 SSN 번호와 근접한 키워드 "SSN"입니다. 체크 um 유효성 검사, 키워드 목록, 키워드 사전을 포함하거나 포함하지 않은 정규식일 수 있습니다.
    - 신뢰 수준 - 신뢰 수준(높음, 중간, 낮음)은 기본 요소와 함께 감지된 지원 증거의 수준을 반영합니다. 항목에 포함된 증거가 수록 일치하는 항목에 찾고 있는 중요한 정보가 포함되어 있다는 신뢰도가 높아지기 때문에
    - 근접 - 기본 요소와 지원 요소 사이의 문자 수

![증빙 및 근접 범위 다이어그램](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

이 비디오의 신뢰 수준에 대해 자세히 알아보시다


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>중요한 정보 유형 예


## <a name="argentina-national-identity-dni-number"></a>아르헨티나 국가 ID(DNI) 번호

### <a name="format"></a>형식

마침표로 구분된 8자리 숫자

### <a name="pattern"></a>패턴

8자리 숫자:
- 2자리 숫자
- 기간
- 3자리 숫자
- 기간
- 3자리 숫자

### <a name="checksum"></a>체크 um

아니요

### <a name="definition"></a>정의

DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.
- 정규식 Regex_argentina_national_id 일치하는 콘텐츠를 검색합니다.
- 검색된 Keyword_argentina_national_id 발견됩니다.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>키워드

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- ID 
- Identification National Identity Card 
- DNI 
- NIC National Registry of Persons 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>신뢰 수준에 대한 추가

중요한 정보 유형 엔터티 정의에서 **신뢰** 수준은 기본 요소 외에 검색되는 증거의 수를 반영합니다. 항목에 포함된 증거가 수록 일치하는 항목에 찾고 있는 중요한 정보가 포함되어 있다는 신뢰도가 높아지기 때문에 예를 들어 신뢰 수준이 높은 일치는 기본 요소와 근접한 더 많은 증거를 포함하나 신뢰 수준이 낮은 일치는 근접한 증거를 거의 또는 거의 포함하지 않습니다. 

신뢰도 수준이 높을수록 가음성은 가장 적지만 가음성은 더 많이 반환될 수 있습니다. 신뢰 수준이 낮거나 보통이면 가음성은 더 많이 반환하지만 가음성 수준은 0에서 0까지입니다.

- **낮은 신뢰도:** 값 65, 일치 항목은 가음성은 가장 적지만 오음성은 가장 적습니다. 낮은 신뢰도는 낮은 신뢰도, 보통 및 높은 신뢰도 일치를 모두 반환합니다.
- **중간 신뢰도**: 값 75, 일치 항목은 평균 가짓 긍정 양과 거짓 부정을 포함하게 됩니다. 보통 신뢰도는 모든 중간 신뢰도 및 높은 신뢰도 일치를 반환합니다.  
- **높은 신뢰도:** 값이 85이면 일치하는 항목은 가음성은 가장 적지만 거짓 부정은 가장 적습니다. 높은 신뢰도는 높은 일치만 반환합니다.  

신뢰도 패턴은 낮은 수로, 5~10개, 신뢰도가 높은 패턴은 20개 이상을 사용하세요.

## <a name="creating-custom-sensitive-information-types"></a>사용자 지정 중요한 정보 유형 만들기

보안 및 준수 센터에서 사용자 지정 중요한 정보 유형을 만들려면 몇 가지 옵션 중에서 선택할 수 있습니다.

- **UI 사용** 보안 및 준수 센터 UI를 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니나. 이 방법을 사용하면 정규식, 키워드 및 키워드 사전을 사용할 수 있습니다. 자세한 내용은 [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)을 참조하십시오.

- **EDM 사용** EDM(정확한 데이터 일치) 기반 분류를 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니다. 이 방법을 사용하면 주기적으로 새로 고칠 수 있는 보안 데이터베이스를 사용하여 동적인 중요한 정보 유형을 만들 수 있습니다. [분류에 기반한 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)를 참조하십시오.

- **PowerShell을 사용** PowerShell을 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니다. 이 방법은 UI를 사용하는 것보다 복잡하지만 더 다양한 구성 옵션이 있습니다. [보안 및 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type-in-scc-powershell.md)를 참조하십시오.



> [!NOTE]
> Microsoft 365 서비스에 대한 데이터 손실 방지, Microsoft 365 서비스에 대한 Microsoft Information Protection, 통신 규정 준수, 정보 거버넌스 및 레코드 관리 내에서 향상된 신뢰 수준을 즉시 사용할 수 있습니다.

> Microsoft 365 Information Protection은 이제 다음에 대해 미리보기 더블 바이트 문자 집합 언어를 지원합니다.
> - 중국어(간체)
> - 중국어(번체)
> - 한국어
> - 일본어

>이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다. 자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.

## <a name="for-further-information"></a>자세한 내용은
- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)
- [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)
- [PowerShell에서 사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
