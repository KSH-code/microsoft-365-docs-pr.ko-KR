---
title: 통신 준수 계획
description: 조직의 통신 준수 사용 계획에 대해 설명 합니다.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045857"
---
# <a name="plan-for-communication-compliance"></a>통신 준수 계획

조직의 [통신 준수](communication-compliance.md) 를 시작 하기 전에 정보 기술 및 준수 관리 팀에서 검토 해야 하는 중요 한 계획 작업 및 고려 사항이 있습니다. 다음 영역에서 배포를 철저히 이해 하 고 계획 하는 것은 통신 준수 기능의 구현과 사용이 원활 하 게 진행 되 고 솔루션에 대 한 모범 사례와 부합 되도록 하는 데 도움이 됩니다.

## <a name="work-with-stakeholders-in-your-organization"></a>조직의 관련자에 대 한 작업

조직에서 통신 준수 알림에 대 한 작업을 수행 하기 위해 공동 작업을 수행할 수 있는 적절 한 관련자를 파악 합니다. 초기 계획에 포함 해야 하는 몇 가지 권장 되는 이해 관계자와 종단 간 [통신 규정 준수 워크플로](communication-compliance.md#workflow) 는 다음과 같은 조직 영역의 사용자입니다.

- 정보 기술
- 규정 준수
- 개인 정보
- 보안
- 인사부
- 법무

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>조사 및 업데이트 관리 워크플로 계획

[Microsoft 365 준수 센터](https://compliance.microsoft.com/)에서 일반 흐름에 대 한 경고를 모니터링 하 고 검토 하려면 전용 검토자를 선택 합니다. **관리 검토 관리자**, **사례 관리**, **준수 관리자**및 **검토** 역할을 사용 하 여 검토자에 게 사용 권한을 사용 하도록 설정 하려면 [새 역할 그룹을 만들어야](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) 합니다.

## <a name="plan-for-policies"></a>정책 계획

원하지 않는 언어, 중요 한 정보 및 규정 준수를 위해 [미리 정의 된 서식 파일](communication-compliance-feature-reference.md#policy-templates) 을 사용 하 여 쉽고 빠르게 통신 규정 준수 정책을 만들 수 있습니다. 사용자 지정 통신 준수 정책을 사용 하면 조직 및 요구 사항과 관련 된 문제를 유연 하 게 검색 하 고 조사할 수 있습니다.

통신 준수 정책을 계획할 때는 다음을 고려 하십시오.

- 조직의 모든 사용자를 통신 준수 정책에 대 한 범위 내로 추가 하는 것이 좋습니다. 개별 정책의 범위 내에서 특정 사용자를 확인 하는 것이 유용한 경우도 있지만 대부분의 조직에는 harassment 또는 판별 검색에 최적화 된 통신 준수 정책의 모든 사용자가 포함 되어야 합니다.
- 설정을 단순화 하려면 통신을 검토 해야 하는 사용자를 위해 그룹을 만드는 것이 좋습니다. 그룹을 사용 하는 경우 여러 개 필요할 수도 있습니다. 예를 들어 서로 다른 두 그룹의 통신을 검색 하려는 경우 또는 감독 되지 않는 그룹을 지정 하려는 경우
- 검토할 통신 비율을 100%로 구성 하 여 정책에서 조직의 통신에 대 한 모든 문제를 포착 하는지 확인 합니다.
- Microsoft 365 조직의 사서함으로 가져온 데이터를 타사 [원본의](communication-compliance-feature-reference.md#supported-communication-types) 통신을 검색할 수 있습니다. 이러한 플랫폼의 통신 검토를 포함 하려면 통신 정책에 따라 메시지 회의 정책 조건을 모니터링 하기 전에 이러한 서비스에 대 한 커넥터를 구성 해야 합니다.
- 사용자 지정 통신 준수 정책에서는 정책이 영어가 아닌 다른 모니터링 언어를 지원할 수 있습니다. 선택한 언어로 공격적인 단어의 [사용자 지정 키워드 사전을](communication-compliance-feature-reference.md#custom-keyword-dictionaries) 작성 하거나 Microsoft 365에서 [trainable 분류자](classifier-getting-started-with.md) 를 사용 하 여 고유한 컴퓨터 학습 모델을 작성 합니다.
- 모든 조직에는 서로 다른 통신 표준 및 정책 요구 사항이 있습니다. 통신 준수 [정책 조건을](communication-compliance-feature-reference.md#conditional-settings) 사용 하 여 특정 키워드를 모니터링 하거나, [사용자 지정 중요 한 정보 유형을](create-a-custom-sensitive-information-type.md)사용 하 여 특정 유형의 정보를 모니터링 합니다.

## <a name="ready-to-get-started"></a>시작할 준비가 되셨습니까?

Microsoft 365 조 직에 대 한 통신 준수를 구성 하려면 microsoft [365에 대 한 통신 준수 구성](communication-compliance-configure.md) 또는 [Contoso의 사례 연구](communication-compliance-case-study.md) 를 확인 하거나 Microsoft 팀, Exchange Online 및 Yammer 통신에서 비속어를 모니터링 하기 위한 통신 준수 정책을 빠르게 구성 하는 방법을 참조 하세요.
