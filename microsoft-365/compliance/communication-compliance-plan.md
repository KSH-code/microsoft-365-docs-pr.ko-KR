---
title: 커뮤니케이션 규정 준수 계획
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
ms.openlocfilehash: d64edc9d80722080db18c45127bfc82110d1ea9e
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131540"
---
# <a name="plan-for-communication-compliance"></a>커뮤니케이션 규정 준수 계획

조직의 [통신 준수](communication-compliance.md) 를 시작 하기 전에 정보 기술 및 준수 관리 팀에서 검토 해야 하는 중요 한 계획 작업 및 고려 사항이 있습니다. 다음 영역에서 배포를 철저히 이해 하 고 계획 하는 것은 통신 준수 기능의 구현과 사용이 원활 하 게 진행 되 고 솔루션에 대 한 모범 사례와 부합 되도록 하는 데 도움이 됩니다.

## <a name="work-with-stakeholders-in-your-organization"></a>조직의 관련자에 대 한 작업

조직에서 통신 준수 알림에 대 한 작업을 수행 하기 위해 공동 작업을 수행할 수 있는 적절 한 관련자를 파악 합니다. 초기 계획에 포함 해야 하는 몇 가지 권장 되는 이해 관계자와 종단 간 [통신 규정 준수 워크플로](communication-compliance.md#workflow) 는 다음과 같은 조직 영역의 사용자입니다.

- 정보 기술
- 규정 준수
- 개인 정보
- 보안
- 인사부
- 법률 정보

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>조사 및 업데이트 관리 워크플로 계획

[Microsoft 365 준수 센터](https://compliance.microsoft.com/)에서 일반 흐름에 대 한 경고 및 사례를 모니터링 하 고 검토 하려면 전용 관련자를 선택 합니다. 사용자 및 관련자를 조직의 서로 다른 통신 규정 준수 역할 그룹에 할당 하는 방법을 이해 하 고 있어야 합니다.

통신 정책 및 알림을 관리 하는 방법에 따라 관리자, 검토자 및 investigators에 대 한 하나 이상의 역할 그룹에 사용자를 할당 해야 합니다. 사용자를 특정 역할 그룹에 할당 하 여 서로 다른 통신 준수 기능 집합을 관리할 수 있습니다. 또는 통신 준수 역할 그룹에 모든 통신 준수 사용자를 할당할지 결정할 수 있습니다. 준수 관리 요구 사항에 가장 적합 한 역할 그룹 또는 여러 그룹을 사용 합니다.

통신 준수를 구성할 때 이러한 역할 그룹 옵션 중에서 선택할 계획입니다.

|**역할**|**역할 권한**|
|:-----|:-----|
| **통신 준수** | 이 역할 그룹을 사용 하 여 단일 그룹의 조직에 대 한 통신 준수를 관리 합니다. 지정 된 관리자, 분석가, investigators 및 뷰어에 대 한 모든 사용자 계정을 추가 하 여 단일 그룹에서 통신 준수 권한을 구성할 수 있습니다. 이 역할 그룹에는 모든 통신 준수 권한 역할이 포함 되어 있습니다. 이 구성은 서로 다른 사용자 그룹에 대해 정의 된 별도의 사용 권한이 필요 하지 않은 조직에 적합 하며 통신 준수를 빠르게 시작할 수 있는 가장 쉬운 방법입니다. |
| **통신 준수 관리자** | 이 역할 그룹을 사용 하 여 초기에 통신 준수 관리자를 정의 된 그룹으로 세분 하 고 의사 소통 준수를 구성 합니다. 이 역할 그룹에 할당 된 사용자는 통신 준수 정책, 전역 설정 및 역할 그룹 할당을 만들고, 읽고, 업데이트 하 고, 삭제할 수 있습니다. 이 역할 그룹에 할당 된 사용자는 메시지 알림을 볼 수 없습니다. |
| **통신 준수 분석가** | 이 그룹을 사용 하 여 통신 준수 분석가 역할을 하는 사용자에 게 사용 권한을 할당 합니다. 이 역할 그룹에 할당 된 사용자는 검토자로 할당 되는 정책, 메시지 메타 데이터를 보거나, 추가 검토자에 게 승격 하거나, 사용자에 게 알림을 보낼 수 있습니다. 분석가가 보류 중인 알림을 확인할 수 없습니다. |
| **통신 준수 Investigator** | 이 그룹을 사용 하 여 통신 준수 investigators 역할을 할 사용자에 게 사용 권한을 할당 합니다. 이 역할 그룹에 할당 된 사용자는 메시지 메타 데이터와 콘텐츠를 보고, 추가 검토자에 게 에스컬레이션 하며, 고급 eDiscovery 사례로 에스컬레이션 하 고, 사용자에 게 알림을 보내며, 경고를 해결할 수 있습니다. |
| **통신 준수 뷰어** | 이 그룹을 사용 하 여 통신 보고서를 관리할 사용자에 게 사용 권한을 할당 합니다. 이 역할 그룹에 할당 된 사용자는 통신 준수 홈 페이지의 모든 보고 widget에 액세스 하 고 모든 통신 준수 보고서를 볼 수 있습니다. |

## <a name="plan-for-policies"></a>정책 계획

원하지 않는 언어, 중요 한 정보 및 규정 준수를 위해 [미리 정의 된 서식 파일](communication-compliance-feature-reference.md#policy-templates) 을 사용 하 여 쉽고 빠르게 통신 규정 준수 정책을 만들 수 있습니다. 사용자 지정 통신 준수 정책을 사용 하면 조직 및 요구 사항과 관련 된 문제를 유연 하 게 검색 하 고 조사할 수 있습니다.

통신 준수 정책을 계획할 때는 다음 영역을 고려 하십시오.

- 조직의 모든 사용자를 통신 준수 정책에 대 한 범위 내로 추가 하는 것이 좋습니다. 개별 정책의 범위 내에서 특정 사용자를 확인 하는 것이 유용한 경우도 있지만 대부분의 조직에는 harassment 또는 판별 검색에 최적화 된 통신 준수 정책의 모든 사용자가 포함 되어야 합니다.
- 설정을 단순화 하려면 통신을 검토 해야 하는 사용자를 위해 그룹을 만드는 것이 좋습니다. 그룹을 사용 하는 경우 여러 개 필요할 수도 있습니다. 예를 들어 서로 다른 두 그룹의 통신을 검색 하려는 경우 또는 감독 되지 않는 그룹을 지정 하려는 경우
- 검토할 통신 비율을 100%로 구성 하 여 정책에서 조직의 통신에 대 한 모든 문제를 포착 하는지 확인 합니다.
- Microsoft 365 조직의 사서함으로 가져온 데이터를 타사 [원본의](communication-compliance-feature-reference.md#supported-communication-types) 통신을 검색할 수 있습니다. 이러한 플랫폼의 통신 검토를 포함 하려면 통신 정책에 따라 메시지 회의 정책 조건을 모니터링 하기 전에 이러한 서비스에 대 한 커넥터를 구성 해야 합니다.
- 사용자 지정 통신 준수 정책에서는 정책이 영어가 아닌 다른 모니터링 언어를 지원할 수 있습니다. 선택한 언어로 공격적인 단어의 [사용자 지정 키워드 사전을](communication-compliance-feature-reference.md#custom-keyword-dictionaries) 작성 하거나 Microsoft 365에서 [trainable 분류자](classifier-get-started-with.md) 를 사용 하 여 고유한 컴퓨터 학습 모델을 작성 합니다.
- 모든 조직에는 서로 다른 통신 표준 및 정책 요구 사항이 있습니다. 통신 준수 [정책 조건을](communication-compliance-feature-reference.md#conditional-settings) 사용 하 여 특정 키워드를 모니터링 하거나, [사용자 지정 중요 한 정보 유형을](create-a-custom-sensitive-information-type.md)사용 하 여 특정 유형의 정보를 모니터링 합니다.

## <a name="ready-to-get-started"></a>시작할 준비가 되셨습니까?

Microsoft 365 조 직에 대 한 통신 준수를 구성 하려면 microsoft [365에 대 한 통신 준수 구성](communication-compliance-configure.md) 또는 [Contoso의 사례 연구](communication-compliance-case-study.md) 를 확인 하거나 Microsoft 팀, Exchange Online 및 Yammer 통신에서 비속어를 모니터링 하기 위한 통신 준수 정책을 빠르게 구성 하는 방법을 참조 하세요.
