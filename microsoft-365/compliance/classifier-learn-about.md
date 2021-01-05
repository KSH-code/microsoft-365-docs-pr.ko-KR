---
title: 학습 가능한 분류자에 대해 자세히
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 학습 가능한 분류자에서는 다양한 유형의 콘텐츠를 인식할 수 있는 도구로, 이를 통해 볼 수 있는 양성 및 부정 샘플을 제공합니다. 분류자 학습이 이행되면 결과가 정확한지 확인할 수 있습니다. 그런 다음 조직의 콘텐츠를 검색하여 보존 또는 민감도 레이블을 적용하거나 DLP(데이터 손실 방지) 또는 보존 정책에 포함하기 위해 이를 분류합니다.
ms.openlocfilehash: d5e7eb891e4cff2fc220d1e9264839d05ed11bd2
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752642"
---
# <a name="learn-about-classifiers"></a>분류자에 대해 자세히

콘텐츠를 적절히 보호하고 처리할 수 있도록 콘텐츠를 분류하고 레이블을 지정하는 것은 정보 보호 분야를 위한 시작점입니다. Microsoft 365에는 콘텐츠를 분류하는 세 가지 방법이 있습니다.

## <a name="manually"></a>수동으로

이 방법을 사용하려면 사람의 판단과 조치가 필요합니다. 관리자는 기존 레이블 및 중요한 정보 유형을 사용하거나 자체 레이블을 만든 다음 게시할 수 있습니다. 사용자와 관리자는 콘텐츠를 접할 때 해당 콘텐츠를 콘텐츠에 적용합니다. 그런 다음 콘텐츠를 보호하고 해당 콘텐츠를 관리할 수 있습니다.

## <a name="automated-pattern-matching"></a>자동화된 패턴 일치

이 분류 메커니즘 범주에는 다음을 통해 콘텐츠를 찾는 내용이 포함됩니다.

- 키워드 또는 메타데이터 값(키워드 쿼리 언어)
- 사회 보장, 신용 카드 또는 은행 계좌 번호(중요한 정보 유형 엔터티 정의)와 같은 이전에 식별된 중요한 정보 패턴을 [사용합니다.](sensitive-information-type-entity-definitions.md)
- 서식 파일(문서 손가락 인쇄)의 변형이기 때문에 항목을 [인식합니다.](document-fingerprinting.md)
- 정확한 문자열(정확한 데이터 [일치)이 있는 경우.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

그런 다음 민감도 및 보존 레이블을 자동으로 적용하여 [콘텐츠를 DLP(데이터](data-loss-prevention-policies.md) 손실 방지)에 사용할 수 있도록 설정하고 보존 레이블에 대한 정책을 자동으로 적용할 [수 있습니다.](apply-retention-labels-automatically.md)

## <a name="classifiers"></a>분류자

이 분류 방법은 수동 또는 자동화된 패턴 일치 방법으로 쉽게 식별되지 않는 콘텐츠에 특히 적합합니다. 이 분류 방법은 항목의 요소(패턴 일치)가 아니라 항목의 항목을 기준으로 항목을 식별하기 위해 분류자를 교육하는 것입니다. 분류기는 분류에 관심 있는 콘텐츠의 수백 가지 예를 확인하여 콘텐츠 형식을 식별하는 방법을 학습합니다. 먼저 범주에 있는 예제를 공급합니다. 이러한 예제를 처리한 후 일치하는 예제와 일치하지 않는 예제를 모두 조합하여 테스트합니다. 그런 다음 분류기는 주어진 항목이 구축하는 범주에 속하는지 여부를 예측합니다. 그런 다음 결과를 확인하여 참 긍정, 참 부정, 가긍성 및 거짓 부정을 정렬하여 예측 정확도를 높일 수 있습니다. 

분류기를 게시할 때 SharePoint Online, Exchange 및 OneDrive와 같은 위치의 항목을 정렬하고 콘텐츠를 분류합니다. 분류기를 게시한 후 초기 교육 프로세스와 유사한 피드백 프로세스를 사용하여 분류자 교육을 계속할 수 있습니다.

### <a name="where-you-can-use-trainable-classifiers"></a>학습 가능한 분류자 사용 위치
기본 제공 분류자 및 학습 가능한 분류자 모두 민감도 레이블이 있는 [Office](apply-sensitivity-label-automatically.md)자동 레이블 [지정,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) 조건 및 통신 준수에 따라 보존 레이블 정책 자동 적용에 대한 조건으로 사용할 수 [있습니다.](communication-compliance.md) 

민감도 레이블은 분류기를 조건으로 사용할 수 있습니다. 콘텐츠에 자동으로 민감도 [레이블 적용을 참조하세요.](apply-sensitivity-label-automatically.md)

> [!IMPORTANT]
> 분류기는 암호화되지 않은 영어 항목에서만 작동됩니다.

## <a name="types-of-classifiers"></a>분류자 유형

- **사전 교육된** 분류자 - Microsoft는 교육 없이 사용할 수 있는 여러 분류자들을 생성하고 사전 교육했습니다. 이러한 분류자는 의 상태와 함께 `Ready to use` 표시됩니다.
- **사용자** 지정 분류자 - 사전 학습된 분류자에서 다루는 범위를 넘어 확장되는 분류 요구가 있는 경우 자체 분류기를 만들고 교육할 수 있습니다.

### <a name="pre-trained-classifiers"></a>사전 학습된 분류자

Microsoft 365는 사전 학습된 5개의 분류자와 함께 제공합니다.

> [!CAUTION]
> 가양성의 수가  높게 생성되고 있기 때문에 공격 언어 사전 학습 분류자 사용이 더는 사용되지 않습니다. 사용하지 말고 현재 사용 중인 경우 비즈니스 프로세스를 해당 프로세스에서 벗어날 수 있습니다. 위협, 괴롭히기 및 괴롭히기 사전 학습된 분류자 대신 사용하는 것이 좋습니다.  

- **이력서**: 신청자의 개인, 교육, 전문 자격, 작업 환경 및 기타 개인 식별 정보의 텍스트 계정인 항목을 검색합니다.
- **소스 코드**: GitHub에서 사용된 상위 25개 컴퓨터 프로그래밍 언어로 작성된 지침 및 문 집합이 포함된 항목을 검색합니다.
    - ActionScript
    - C
    - C #
    - C++
    - 클로루어
    - CoffeeScript
    - Go
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - Perl
    - PHP
    - Python
    - R
    - Ruby
    - 스칼라
    - 셸
    - Swift
    - 텍스
    - Vim 스크립트

> [!NOTE]
> 소스 코드는 대량의 텍스트가 소스 코드인 경우를 감지하기 위해 교육됩니다. 일반 텍스트와 교차하는 소스 코드 텍스트를 검색하지 않습니다.

- **괴롭기:** 경인도, 인종, 종교, 국적, 성별, 성적 취향, 연령, 장애 등 한 명 또는 여러 개인을 대상으로 하는 공격적인 행동과 관련된 특정 범주의 공격적 언어 텍스트 항목을 검색합니다.
- **비방:** 대부분의 사용자에 대해 당황하는 식을 포함하는 특정 범주의 비방 언어 텍스트 항목을 검색합니다.
- **위협:** 위협을 가하거나 사람 또는 속성에 대한 물리적 손해나 손상을 가하기 위한 위협과 관련된 공격적인 언어 텍스트 항목의 특정 범주를 감지합니다.

이러한 분류는 **Microsoft 365** 규정 준수 센터의 상태와 함께 교육 가능한 분류자 보기에  >    >   `Ready to use` 표시됩니다.

![classifiers-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 공격적인 언어, 괴롭음, 괴롭음 및 위협 분류자만 검색 가능한 텍스트로만 작동할 수 있습니다.  또한 언어 및 문화 표준은 지속적으로 변경되고 이러한 현실을 토대하여 Microsoft는 재량에 따라 이러한 분류자들을 업데이트할 수 있는 권리가 있습니다. 분류자는 공격적 언어 및 사용되는 기타 언어를 모니터링하는 데 도움이 될 수 있는 반면, 분류자는 해당 언어의 결과를 해결하지는 않습니다. 이러한 언어의 사용에 대한 모니터링 또는 응답을 조직에서 전적으로 제공하는 것은 아니며, Microsoft 또는 해당 자회사가 아닌 조직은 사전 학습된 분류자에 의해 식별된 콘텐츠의 모니터링, 적용, 차단, 제거 및 보존과 관련된 모든 결정에 대한 책임을 져야 합니다.

### <a name="custom-classifiers"></a>사용자 지정 분류자

사전 학습된 분류자들이 요구 사항을 충족하지 않는 경우 자체 분류기를 만들고 교육할 수 있습니다. 자신만의 작업을 만드는 데 관련된 작업도 훨씬 더 많지만 조직 요구에 훨씬 더 잘 맞게 조정됩니다. 

예를 들어 다음에 대해 학습 가능한 분류기를 만들 수 있습니다.
 
- 법률 문서 - 변호사 클라이언트 권한, 닫는 집합, 작업 설명 등의
- 전략적 비즈니스 문서 - 보도 자료, 인수, 거래, 비즈니스 또는 마케팅 계획, 지적 재산권, 디자인 문서 등
- 가격 정보 - 송장, 가격 견적, 작업 주문, 매입 문서 등 
- 재무 정보 - 조직 투자, 분기별 또는 연간 결과 등    

#### <a name="process-flow-for-creating-custom-classifiers"></a>사용자 지정 분류자 만들기 위한 프로세스 흐름

보존 정책 및 통신 감독과 같은 규정 준수 솔루션에서 사용할 분류자 만들기 및 게시는 이 흐름을 따르게 됩니다. 학습 가능한 사용자 지정 분류자 만들기에 대한 자세한 내용은 사용자 지정 분류자 [만들기를 참조합니다.](classifier-get-started-with.md)

![프로세스 흐름 사용자 지정 분류자](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>분류자 재시도

수행한 분류의 정확성에 대한 피드백을 제공하여 모든 사용자 지정 분류자 및 사전 학습된 분류자의 정확도를 향상시킬 수 있습니다. 이를 재조정이라고 합니다. 이 워크플로를 따르는 것입니다.

![분류자 재조정 워크플로](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>참고 항목

- [보존 레이블](retention.md)
- [DLP(데이터 손실 방지)](data-loss-prevention-policies.md)
- [민감도 레이블](sensitivity-labels.md)
- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)
- [문서 손가락 인쇄](document-fingerprinting.md)
- [정확한 데이터 일치](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
