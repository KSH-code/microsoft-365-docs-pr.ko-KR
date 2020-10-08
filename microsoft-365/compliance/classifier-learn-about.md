---
title: 학습 가능한 분류자에 대한 자세한 정 (미리 보기)
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
description: Microsoft 365 trainable 분류자는 긍정적이 고 부정적 샘플을 확인 하 여 다양 한 유형의 콘텐츠를 인식할 수 있도록 교육을 제공 하는 도구입니다. 일단 분류자가 학습 되 면 결과가 정확 함을 확인할 수 있습니다. 그런 다음이를 사용 하 여 조직의 콘텐츠를 검색 하 고이를 분류 하 여 보존 또는 민감도 레이블을 적용 하거나 DLP (데이터 손실 방지) 또는 보존 정책에 포함 합니다.
ms.openlocfilehash: 7abfbe101508d24e58464ff38b14ab87447001f0
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379304"
---
# <a name="learn-about-classifiers-preview"></a>분류자에 대 한 자세한 정보 (미리 보기)

콘텐츠를 보호 하 고 적절 하 게 레이블을 지정 하 여 정보 보호 규칙의 시작 위치를 확인할 수 있습니다. Microsoft 365에는 세 가지 방법으로 콘텐츠를 분류할 수 있습니다.

## <a name="manually"></a>수동으로

이 방법을 사용 하려면 사용자의 판단 및 조치가 필요 합니다. 관리자는 기존 레이블과 중요 한 정보 유형을 사용 하거나 직접 만들어 게시할 수 있습니다. 사용자와 관리자는 콘텐츠를 발견 하는 콘텐츠에 적용 합니다. 그런 다음 콘텐츠를 보호 하 고 해당 처리를 관리할 수 있습니다.

## <a name="automated-pattern-matching"></a>자동화 된 패턴 일치

이 분류 메커니즘 범주에는 다음을 통한 콘텐츠 찾기가 포함 됩니다.

- 키워드 또는 메타 데이터 값 (키워드 쿼리 언어)
- 공유 보안, 신용 카드 또는 은행 계좌 번호와 같은 중요 한 정보 [(중요 한 정보 유형 엔터티 정의)](sensitive-information-type-entity-definitions.md)를 이전에 식별 한 패턴으로 사용 합니다.
- 서식 파일의 변형 [(문서 손가락 인쇄)](document-fingerprinting.md)으로 인해 항목을 인식 합니다.
- 정확한 문자열 [(정확한 데이터 일치)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)을 사용 합니다.

그런 다음 민감도 및 보존 레이블을 자동으로 적용 하 여 [DLP (데이터 손실 방지)](data-loss-prevention-policies.md) 에서 콘텐츠를 사용할 수 있도록 하 고 [보존 레이블에 대 한 자동 적용 정책을](apply-retention-labels-automatically.md)적용할 수 있습니다.

## <a name="classifiers"></a>분류자

이 분류 방법은 수동 또는 자동 패턴 일치 방법으로 쉽게 식별할 수 없는 콘텐츠에 특히 적합 합니다. 이 분류 방법은 항목에 있는 요소 (패턴 일치)가 아니라 항목을 기준으로 항목을 식별 하는 분류자를 교육 하는 방법에 대해 자세히 설명 합니다. 분류자는 분류에 관심이 있는 콘텐츠의 수백 가지 예를 검토 하 여 콘텐츠 형식을 식별 하는 방법을 학습 합니다. 먼저 범주에서 명확 하 게 보여 주는 예제를 공급 합니다. 이를 처리 하 고 나면 일치 및 일치 하지 않는 예제를 모두 함께 제공 하 여 테스트 합니다. 그런 다음 분류자는 지정 된 항목이 작성 중인 범주에 속하는지 여부에 따라 예측을 수행 합니다. 그런 다음 결과를 확인 하 여 해당 예측의 정확도를 높일 수 있도록 true, true 음수, 가양성 및 거짓 네거티브를 정렬 합니다. 

분류자를 게시 하면 SharePoint Online, Exchange 및 OneDrive와 같은 위치에 있는 항목을 기준으로 정렬 되며 콘텐츠를 분류 합니다. 분류자를 게시 한 후에는 초기 교육 프로세스와 유사한 피드백 프로세스를 사용 하 여이를 계속 학습 시킬 수 있습니다.

### <a name="where-you-can-use-trainable-classifiers"></a>Trainable 분류자를 사용할 수 있는 위치
기본 제공 분류자와 trainable 분류자는 각각 조건과 [통신 준수](communication-compliance.md)를 기반으로 하는 [보존 레이블 정책, 자동 적용](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) [레이블을 사용 하 여 Office autolabeling](apply-sensitivity-label-automatically.md)에 대 한 조건으로 사용할 수 있습니다. 

민감도 레이블은 분류자를 조건으로 사용할 수 있습니다. [민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)을 참조 하십시오.

> [!IMPORTANT]
> 분류자는 암호화 되지 않고 영어로 있는 항목에 대해서만 작동 합니다.

## <a name="types-of-classifiers"></a>분류자 유형

- **미리 교육 된 분류자** -Microsoft에서는 교육을 받지 않고 사용을 시작할 수 있는 여러 분류자를 만들고 미리 교육 했습니다. 이러한 분류자는 상태와 함께 표시 됩니다 `Ready to use` .
- **사용자 지정 분류자** -미리 숙련 된 분류자가 포함 된 것 보다 많은 분류 요구가 필요한 경우 고유한 분류자를 만들어 교육할 수 있습니다.

### <a name="pre-trained-classifiers"></a>미리 훈련 된 분류자

Microsoft 365에는 미리 훈련 된 5 개의 분류자가 제공 됩니다.

> [!CAUTION]
> 더 많은 가양성을 **생성 하 여 미리 교육** 을 받은 이전 분류자를 방식 합니다. 이 도구를 사용 하지 않고 현재 사용 중인 경우 비즈니스 프로세스를 외부에서 이동 해야 합니다. 대신 **위협**, **불경**및 **Harassment** 미리 교육 된 분류자를 사용 하는 것이 좋습니다.

- **다시 시작**: 지원자 개인, 교육, 전문가 자격, 작업 환경 및 기타 개인 식별 정보에 대 한 텍스트 계정인 항목을 검색 합니다.
- **소스 코드**: GitHub에서 상위 25 용으로 사용 되는 컴퓨터 프로그래밍 언어에 작성 된 지침 및 문 집합이 포함 되어 있는 항목을 검색 합니다.
    - ActionScript
    - C
    - & #
    - C + +
    - Clojure
    - CoffeeScript
    - 갈
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - 목표-C
    - Perl
    - PHP
    - Python
    - 이력서
    - Ruby
    - Scala
    - 셸
    - Swift
    - Tex
    - Vim 스크립트

> [!NOTE]
> 소스 코드는 대량의 텍스트가 소스 코드 인지 검색할 수 있도록 교육을 받습니다. 일반 텍스트와 섞여 있는 소스 코드 텍스트는 검색 되지 않습니다.

- **Harassment**: 레이스, ethnicity, religion, 국립 근원, 성별, 성적 방향, 연령, 장애 등의 특성을 기반으로 하 여 한 명 이상의 개인이 대상으로 하는 공격적인 언어 텍스트 항목의 특정 범주를 감지 합니다.
- **불경**: 대부분의 사용자에 게 embarrass 하는 식이 포함 된 비속어 (공격적인 언어) 텍스트 항목의 특정 범주를 감지 합니다.
- **위협**: 사용자 또는 속성에 대 한 폭력을 커밋하거나 물리적으로 피해를 주거나 위험에 관련 된 비속어 텍스트 항목의 특정 범주를 감지 합니다.

이러한 정보는의 상태를 포함 하는 **Microsoft 365 준수 센터**  >  **데이터 분류 (preview)**  >  **Trainable 분류자** 보기에 표시 `Ready to use` 됩니다.

![분류자-미리 훈련 된 분류자](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 비속어, harassment, 비속어 및 threat 분류자는 검색 가능한 텍스트만 사용할 수 있습니다.  추가적으로, 언어 및 문화 표준이 지속적으로 변경 되 고 이러한 현실에 따라 Microsoft는 이러한 분류자를 업데이트할 수 있는 권리를 보유 합니다. 이 분류자는 사용 중인 공격적인 및 기타 언어를 모니터링 하는 데 도움이 될 수 있지만, 이러한 언어의 결과를 해결 하는 것이 아니므로 조직의 해당 언어 사용에 대 한 다양 한 모니터링 또는 대응 수단을 제공 하기 위한 것이 아닙니다. Microsoft 또는 해당 자회사가 아닌 조직은 미리 훈련 된 분류자로 식별 되는 콘텐츠의 모니터링, 적용, 차단, 제거 및 보존과 관련 된 모든 결정을 계속 담당 합니다.

### <a name="custom-classifiers"></a>사용자 지정 분류자

미리 교육 된 분류자가 사용자의 요구를 충족 하지 않는 경우 고유한 분류자를 만들고 교육 해 볼 수 있습니다. 자체를 만드는 작업과 관련 된 작업은 훨씬 더 많이 수행 되지만 조직 요구 사항에 맞게 조정 하는 것이 훨씬 더 낫습니다.

> [!IMPORTANT]
> 기본적으로 사용자 지정 분류자를 만드는 사용자만이 해당 분류자에서 수행한 예측을 학습 하 고 검토할 수 있습니다. 다른 사용자가 분류자 예측을 학습 하 고 검토할 수 있도록 하려면 [다른 사용자에 게 교육 및 권한 검토](classifier-get-started-with.md#give-others-train-and-review-rights)를 참조 하세요.

#### <a name="process-flow-for-creating-custom-classifiers"></a>사용자 지정 분류자를 만들기 위한 프로세스 흐름

승인 솔루션에서 사용 하기 위한 분류자를 만들고 게시 하는 경우 (예: 보존 정책 및 통신 감독)이 흐름을 따릅니다. 사용자 지정 trainable 분류자를 만드는 방법에 대 한 자세한 내용은 [사용자 지정 분류자 만들기](classifier-get-started-with.md)를 참조 하십시오.

![프로세스 흐름 사용자 지정 분류자](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>재교육 분류자

모든 사용자 지정 분류자 및 미리 교육을 받은 모든 분류자의 정확성을 향상 시킬 수 있으며,이를 통해 수행 되는 분류의 정확성에 대 한 피드백을 제공 합니다. 이를 재교육 이라고 하며이 워크플로를 따릅니다.

![분류자 재교육 워크플로](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>참고 항목

- [보존 레이블](retention.md)
- [DLP(데이터 손실 방지)](data-loss-prevention-policies.md)
- [민감도 레이블](sensitivity-labels.md)
- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)
- [문서 손가락 인쇄](document-fingerprinting.md)
- [정확한 데이터 일치](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
