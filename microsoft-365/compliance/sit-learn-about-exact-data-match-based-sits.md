---
title: 정확한 데이터 일치 기반 중요한 정보 유형에 대해 자세히 알아보기
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
description: 정확한 데이터 일치 기반의 중요한 정보 유형에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 552d86e4c460ee0195ec83d88965592298a17d90
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914887"
---
# <a name="learn-about-exact-data-match-based-sensitive-information-types"></a>정확한 데이터 일치 기반 중요한 정보 유형에 대해 자세히 알아보기

중요한 [정보](sensitive-information-type-learn-about.md) 유형은 중요한 항목이 부적절하거나 부적절하게 공유되는 것을 방지하고, eDiscovery에서 관련 데이터를 밝히고, 특정 유형의 정보에 거버넌스 작업을 적용할 수 있도록 하는 데 사용됩니다. 다음을 기반으로 사용자 지정 SIT(중요한 정보 유형)를 정의합니다.

- 패턴
- 직원, 사회 보장 *번호* 또는 *ID와* 같은 *키워드* 증거
- 특정 패턴의 증거에 대한 문자 근접성
- 신뢰 수준

그러나 일반 패턴에 따라 일치하는 값을 찾은 것이 아니라 정확히 또는 거의 정확한 데이터 값을 사용하는 사용자 지정 SIT(중요한 정보 유형)를 원할 경우 어떻게 하나요? EDM(정확한 데이터 일치) 기반 분류를 사용하여 다음을 위해 설계된 사용자 지정 중요한 정보 유형을 만들 수 있습니다.

- 역동적이며 쉽게 새로 고침
- 확장성 향상
- 가양성 수 감소
- 구조화된 중요한 데이터 사용
- Microsoft를 비롯한 누구와도 공유하지 말고 중요한 정보를 보다 안전하게 처리
- 여러 Microsoft 클라우드 서비스와 함께 사용 가능

![EDM 기반 분류.](../media/EDMClassification.png)

EDM 기반 분류를 사용하면 중요한 정보 데이터베이스의 정확한 값을 참조하는 사용자 지정 중요한 정보 유형을 만들 수 있습니다. 데이터베이스는 매일 새로 고칠 수 있으며 최대 1억 행의 데이터를 포함할 수 있습니다. 직원, 환자 또는 고객이 계속 이동하고 기록이 변경됨에 따라 사용자 지정 중요한 정보 유형을 적절하고 최신인 상태로 유지합니다. 또한 EDM 기반 분류를 [데이터 손실 방지 정책](dlp-learn-about-dlp.md) 또는 [Microsoft Cloud App Security 파일 정책](/cloud-app-security/data-protection-policies) 등의 정책과 사용할 수 있습니다.

> [!NOTE]
> Microsoft 365 Information Protection은 다음의 더블 바이트 문자 집합 언어를 지원합니다.
>
> - 중국어(간체)
> - 중국어(번체)
> - 한국어
> - 일본어
>
> 이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다. 자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.

## <a name="whats-different-in-an-edm-sit"></a>EDM SIT의 다른점

EDM SITS를 사용하면 고유한 몇 가지 개념을 이해하는 것이 도움이 됩니다.  

### <a name="schema"></a>Schema

이 schema는 다음을 정의하는 xml 파일입니다.

- 나중에 *DataStore라고 하는 스마마의 이름입니다.* 
- 중요한 정보 원본 테이블에 포함된 필드 이름입니다. 중요한 정보 원본 테이블 열 이름에 대한 1:1 매핑이 있습니다.
- 검색 가능한 필드
- 구성 가능한 일치라고 하는 모든 검색 수정 매개 변수(검색된 값의 대소문자 및 대소문자 무단).

### <a name="sensitive-information-source-table"></a>중요한 정보 원본 테이블

EDM SIT가 찾아보는 중요한 정보 값이 포함된 중요한 원본 테이블입니다. 열과 로로 이루어졌다. 열 헤더는 필드 이름, 행은 데이터의 인스턴스입니다. 각 셀에는 해당 필드에 대한 해당 인스턴스의 값이 들어 있습니다.

다음은 중요한 정보 원본 테이블의 간단한 예입니다.

|이름  |성  |Date of Birth  |
|---------|---------|---------|
|이사야어   |Langer  | 05-05-1960 |
|Ana   |Bowman         |11-24-1971 |
|오스카   |Ward         |02-12-1998 |


### <a name="rule-package"></a>규칙 패키지

모든 SIT에는 규칙 패키지가 있습니다. EDM SIT에서 규칙 패키지를 사용하여 다음을 정의합니다.

- 일치 - 정확한 검색에 사용할 기본 요소로 사용할 필드를 지정합니다. 체크 um 유효성 검사, 키워드 목록, 키워드 사전 또는 함수를 포함하거나 포함하지 않은 정규식일 수 있습니다.
- 분류 - EDM lookup을 트리거하는 중요한 유형 일치를 지정합니다.
- 찾은 경우 일치의 신뢰를 높이는 데 도움이 되는 증거를 제공하는 요소인 지원 요소입니다. 예를 들어 SSN 번호와 근접한 키워드 "SSN"입니다. 체크 um 유효성 검사, 키워드 목록, 키워드 사전을 포함하거나 포함하지 않은 정규식일 수 있습니다.
- 신뢰도(높음, 중간, 낮음)는 기본 요소와 함께 감지된 지원 증거의 수를 반영합니다. 항목에 포함된 증거가 수록 일치하는 항목에 찾고 있는 중요한 정보가 포함되어 있다는 신뢰도가 높아지기 때문에 신뢰 [수준에 대한](sensitive-information-type-learn-about.md#fundamental-parts-of-a-sensitive-information-type) 자세한 내용은 중요한 정보 유형의 기본 부분을 참조하세요.
근접 - 기본 요소와 지원 요소 사이의 문자 수

### <a name="you-supply-your-own-schema-and-data"></a>자체의 Schema 및 데이터 제공

Microsoft 365, regex 패턴, 키워드 및 신뢰 수준이 있는 [200개가 넘는 SITS가](sensitive-information-type-entity-definitions.md) 함께 제공합니다. EDM SITS를 사용하면 중요한 항목을 식별하는 기본 및 보조 필드뿐만 아니라, 해당 스마를 정의할 책임이 있습니다. 기본 및 보조 데이터 값은 매우 중요하기 때문에 임의로 생성되거나 [](/dotnet/standard/security/ensuring-data-integrity-with-hash-codes) 자체 제공된 솔트 값을 포함하는 해시 함수를 통해 이러한 값을 [암호화하게](https://en.wikipedia.org/wiki/Salt_(cryptography)#:~:text=The%20salt%20value%20is%20generated%20at%20random%20and,the%20salt%20value%20and%20hashed%20value%20are%20stored.) 됩니다. 그런 다음 이러한 해시된 값이 서비스에 업로드됩니다. 따라서 중요한 데이터가 열리지 않습니다.

### <a name="primary-and-secondary-support-elements"></a>기본 및 보조 지원 요소

EDM SIT를 만들 때 규칙  패키지에서 기본 요소 필드를 정의합니다. 기본 필드는 모든 콘텐츠가 검색되고 식별을 위해 정의된 패턴을 따라야 하는 요소입니다. 검사된 항목에서 기본 요소가 발견되는 경우 EDM은  패턴을 따를 필요가 없는 보조 또는 지원 요소와 기본 요소와의 근접성을 검색합니다. EDM을 사용하려면 기존 SIT를 통해 기본 요소를 먼저 검색해야 합니다. 사용 가능한 [SITS의](sensitive-information-type-entity-definitions.md) 전체 목록은 중요한 정보 유형 엔터티 정의를 참조하세요. EDM SIT에서 검색할 클래스를 검색하는 클래스 중 하나를 찾아야 합니다. 예를 들어 EDM SIT Schema에 주된 요소로 미국 사회 보장 번호가 있는 경우 EDM 스마마를 만들 때 미국 [SSN(사회](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn) 보장 번호) SIT와 연결합니다.


## <a name="how-matching-works"></a>일치 작동 방식

EDM은 검색된 콘텐츠를 정의한 중요한 데이터 표와 비교하여 일치를 검색합니다. 일치 테스트는 기존 규칙과 패턴의 조합을 사용하여 일치된 데이터가 찾고 보호하려는 데이터의 실제 인스턴스가 되도록 합니다. 핵심적으로 EDM은 문서 및 전자 메일의 문자열을 제공하는 중요한 데이터 표의 값과 비교하여 단방형 암호화 해시를 비교하여 콘텐츠의 값이 표에 존재하는지 확인하도록 합니다.

> [!TIP]
> 일반적인 방법은 EDM 중요한 정보 유형과 DLP 규칙을 기반으로 하는 일반 중요한 정보 유형을 서로 다른 임계값과 결합하는 것입니다. 예를 들어, 하나 이상의 일치가 DLP 경고를 발생하게 하는 엄격한 요구 사항 및 낮은 허용 오차를 사용하여 주민등용 번호 및 기타 데이터를 조사하는 EDM 중요한 정보 유형을 사용할 수 있으며, 더 높은 수를 위해 기본 제공된 미국 사회 보장 번호와 같은 일반 중요한 정보 유형을 사용할 수 있습니다.  

## <a name="see-also"></a>참고 항목

- [정확한 데이터 일치 기반 중요한 정보 유형 시작](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
   