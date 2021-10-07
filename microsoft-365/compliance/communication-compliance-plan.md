---
title: 커뮤니케이션 규정 준수 계획
description: 조직에서 통신 규정 준수를 사용하는 계획을 세우는 방법을 배워야 합니다.
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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: b26d983bf73a968a06566f18c20d4df24b7763a8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179322"
---
# <a name="plan-for-communication-compliance"></a>커뮤니케이션 규정 준수 계획

조직에서 커뮤니케이션 규정 [](communication-compliance.md) 준수를 시작하기 전에 정보 기술 및 규정 준수 관리 팀에서 검토해야 하는 중요한 계획 활동 및 고려 사항이 있습니다. 다음 영역에서 배포를 철저하게 이해하고 계획하면 통신 준수 기능의 구현 및 사용이 원활하게 진행될 수 있으며 솔루션의 모범 사례에 맞게 조정됩니다.

## <a name="work-with-stakeholders-in-your-organization"></a>조직의 관련자와 작업

커뮤니케이션 규정 준수 경고에 대한 조치를 취하기 위해 공동 작업을 수행하기 위해 조직의 적절한 이해 관계자를 식별합니다. 초기 계획 및 종단 간 통신 준수 워크플로에 [](communication-compliance.md#workflow) 포함하도록 고려할 몇 가지 권장되는 관련자는 조직의 다음 영역에 있는 사용자입니다.

- 정보 기술
- 규정 준수
- 개인 정보
- 보안
- 인적 리소스
- 법률 정보

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>조사 및 수정 워크플로 계획

의 정기적인 케이던스에 대한 경고 및 사례를 모니터링하고 검토하려면 전용 이해 [관계자를 Microsoft 365 규정 준수 센터.](https://compliance.microsoft.com/) 조직의 여러 커뮤니케이션 규정 준수 역할 그룹에 사용자 및 관련자를 할당하는 방법을 이해해야 합니다.

통신 정책 및 경고를 관리하는 방법에 따라 관리자, 검토자 및 조사자를 위한 하나 이상의 역할 그룹에 사용자를 할당해야 합니다. 특정 역할 그룹에 사용자를 할당하여 다양한 통신 준수 기능 집합을 관리할 수 있습니다. 또는 모든 통신 준수 사용자를 통신 준수 역할 그룹에 할당하도록 결정할 수 있습니다. 단일 역할 그룹 또는 여러 그룹을 사용하여 규정 준수 관리 요구 사항에 가장 잘 맞도록 합니다.

통신 준수를 구성할 때 다음 역할 그룹 옵션에서 선택하도록 계획합니다.

|**역할**|**역할 권한**|
|:-----|:-----|
| **통신 규정 준수** | 이 역할 그룹을 사용하여 단일 그룹에서 조직에 대한 통신 규정 준수를 관리합니다. 지정된 관리자, 분석가, 조사자 및 뷰어에 대한 모든 사용자 계정을 추가하여 단일 그룹에서 통신 준수 권한을 구성할 수 있습니다. 이 역할 그룹에는 모든 통신 준수 권한 역할이 포함되어 있습니다. 이 구성은 통신 규정 준수를 빠르게 시작하는 가장 쉬운 방법으로, 별도의 사용자 그룹에 대해 정의된 별도의 사용 권한이 필요하지 않은 조직에 적합한 구성입니다. |
| **커뮤니케이션 규정 준수 관리자** | 이 역할 그룹을 사용하여 처음에 통신 준수를 구성하고 나중에 통신 준수 관리자를 정의된 그룹으로 나란히 구성합니다. 이 역할 그룹에 할당된 사용자는 통신 준수 정책, 전역 설정 및 역할 그룹 할당을 만들고, 읽고, 업데이트하고, 삭제할 수 있습니다. 이 역할 그룹에 할당된 사용자는 메시지 알림을 볼 수 없습니다. |
| **커뮤니케이션 준수 분석가** | 이 그룹을 사용하여 커뮤니케이션 규정 준수 분석가 역할을 할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 검토자로 할당된 정책을 보거나, 메시지 메타데이터(메시지 콘텐츠 아미타)를 보거나, 추가 검토자로 에스컬레이터하거나, 사용자에게 알림을 보낼 수 있습니다. 분석가가 보류 중인 경고를 해결할 수 없습니다. |
| **커뮤니케이션 규정 준수 조사자** | 이 그룹을 사용하여 커뮤니케이션 준수 조사자 역할을 할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 메시지 메타데이터 및 콘텐츠를 보고, 추가 검토자로 에스컬레이터하고, Advanced eDiscovery 사례로 에스컬레이터하고, 사용자에게 알림을 보내고, 경고를 해결할 수 있습니다. |
| **커뮤니케이션 규정 준수 뷰어** | 이 그룹을 사용하여 통신 보고서를 관리할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 통신 준수 홈 페이지의 모든 보고 위젯에 액세스할 수 있으며 모든 통신 준수 보고서를 볼 수 있습니다. |

## <a name="plan-for-policies"></a>정책 계획

비방성 언어, 중요한 정보 [](communication-compliance-feature-reference.md#policy-templates) 및 규정 준수를 위한 미리 정의된 템플릿을 사용하여 커뮤니케이션 규정 준수 정책을 빠르고 쉽게 만들 수 있습니다. 사용자 지정 커뮤니케이션 규정 준수 정책을 사용하면 조직 및 요구 사항과 관련한 문제를 유연하게 검색하고 조사할 수 있습니다.

통신 준수 정책을 계획할 때 다음 영역을 고려하십시오.

- 조직의 모든 사용자를 통신 준수 정책의 범위 내로 추가하는 것을 고려합니다. 특정 사용자를 개별 정책의 범위 내로 식별하는 것이 유용한 경우도 있습니다. 그러나 대부분의 조직에서는 괴롭히거나 차별 감지에 최적화된 통신 준수 정책에 모든 사용자를 포함해야 합니다.
- 설정을 간소화하려면 커뮤니케이션을 검토해야 하는 사용자에 대한 그룹을 만드는 것이 좋습니다. 그룹을 사용하는 경우 몇 가지가 필요할 수 있습니다. 예를 들어, 두 개의 고유한 사용자 그룹 간의 커뮤니케이션을 검사하는 경우나 관리되지 않는 그룹을 지정하고자 할 경우가 있습니다.
- 정책이 조직에 대한 통신에서 우려하는 모든 문제를 포점하도록 검토할 통신 비율을 100%로 구성합니다.
- 타사 원본의 통신에서 조직의 사서함으로 가져온 데이터를 검색할 Microsoft 365 있습니다. [](communication-compliance-feature-reference.md#supported-communication-types) 이러한 플랫폼에서 통신 검토를 포함하려면 메시지 모임 정책 조건이 통신 정책에 의해 모니터링되기 전에 이러한 서비스에 대한 커넥터를 구성해야 합니다.
- 정책은 사용자 지정 통신 준수 정책에서 영어가 없는 모니터링 언어를 지원할 수 있습니다. 선택한 [언어로](communication-compliance-feature-reference.md#custom-keyword-dictionaries) 공격적인 단어의 사용자 지정 키워드 사전을 작성하거나, 교육 가능한 [](classifier-get-started-with.md) 분류자들을 사용하여 자체 기계 학습 모델을 Microsoft 365.
- 모든 조직에는 서로 다른 통신 표준 및 정책 요구가 있습니다. 통신 준수 정책 조건을 [](communication-compliance-feature-reference.md#conditional-settings) 사용하여 특정 키워드를 모니터링하거나 사용자 지정 중요한 정보 유형이 있는 특정 유형의 정보를 [모니터링합니다.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>시작할 준비가 되셨나요?

Microsoft 365 조직에 대한 통신 규정 준수를 [](communication-compliance-configure.md) 구성하는 Microsoft 365 구성을 참조하거나 [Contoso에](communication-compliance-case-study.md) 대한 사례 연구 및 Contoso가 Microsoft Teams, Exchange Online 및 Yammer 통신에서 공격 언어를 모니터링하도록 통신 준수 정책을 구성한 방법을 참조합니다.
