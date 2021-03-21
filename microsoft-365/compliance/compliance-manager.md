---
title: Microsoft 준수 관리자
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 관리자는 조직에서 위험 평가를 간소화하고 자동화하는 데 도움을 주며 위험을 해결하기 위한 권장 조치를 제안합니다.
ms.openlocfilehash: 80d955f3d321ef8f82fe3654e4d7d08572ec72cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922732"
---
# <a name="microsoft-compliance-manager"></a>Microsoft 준수 관리자

**이 문서의 예는** 준수 관리자가 무엇일지, 규정 준수를 간소화하고 위험을 줄이는 방법 및 주요 구성 요소에 대해 자세히 알아보습니다.

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>새로운 사항: 준수 관리자의 GA 릴리스

규정 준수 관리자는 이제 [Microsoft 365](microsoft-365-compliance-center.md)규정 준수 센터 내에서 종합적인 준수 관리 솔루션으로 GA(규정 준수 관리자)를 사용할 수 있습니다. 이 릴리스를 통해 준수 관리자는 Microsoft Service Trust Portal에서 이전 위치의 전환을 완료합니다. 준수 관리자는 이제 미국 GCC(정부 커뮤니티) 보통 및 GCC High 고객에게도 제공됩니다.

준수 점수의 공개 미리 보기로 시작된 기능은 향상된 준수 관리 기능과 더 쉽게 사용할 수 있는 중앙 집중식 도구로 발전했습니다.  GA 릴리스는 규정 준수 활동을 확장하는 데 도움이 하도록 미리 구축된 평가의 더 큰 컬렉션을 제공합니다.

**GA 릴리스에 대해 자세히 알아보시다.**
- 자주 [묻는 질문은](compliance-manager-faq.md) 진화된 내용을 자세히 설명하는 것입니다.
- 이 블로그 게시물의 GA 기능 [향상에 대해 읽어 읽습니다.](https://aka.ms/compliancemanager/GAblog)

아래 비디오를 시청하여 준수 관리자가 조직에서 규정 준수를 관리하는 방법을 간소화하는 방법을 알아보세요.
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>준수 관리자

[Microsoft 준수 관리자는](https://compliance.microsoft.com/compliancemanager) Microsoft [365](microsoft-365-compliance-center.md) 규정 준수 센터의 기능으로, 보다 간편하고 편리한 조직 규정 준수 요구 사항을 관리할 수 있습니다. 규정 준수 관리자는 데이터 보호 위험 인벤토리를 수집하는 것부터 제어 구현의 복잡도 관리, 규정 및 인증을 최신으로 유지, 감사자에 보고하는 것까지 규정 준수 여정 전체를 도울 수 있습니다.

준수 관리자는 규정 준수를 간소화하고, 제공함으로써 위험을 줄일 수 있도록 합니다.

- 일반 산업 및 지역 표준 및 규정 또는 고유한 준수 요구를 충족하기 위한 사용자 지정 평가에 대한 미리 구축된 평가(사용 가능한 평가는 사용권 계약에 따라 다를 수 있습니다. [자세한 내용은 을(를) 자세히 알아보아](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

- 단일 도구를 통해 위험 평가를 효율적으로 완료하는 데 도움이 되는 워크플로 기능입니다.

- 조직에 가장 관련성이 높은 표준 및 규정을 준수하는 데 도움이 되는 제안된 개선 작업에 대한 세부 단계별 지침입니다. Microsoft에서 관리하는 작업의 경우 구현 세부 정보 및 감사 결과를 볼 수 있습니다.

- 개선 작업을 완료하는 진행 상황을 측정하여 규정 준수 상황을 이해하는 데 도움이 되는 위험 기반 준수 점수입니다.

준수 관리자 대시보드는 현재 준수 점수를 표시하고, 주의가 필요한 사항을 볼 수 있도록 도움을 주며 주요 개선 조치를 안내합니다. 다음은 준수 관리자 대시보드의 모양에 대한 예입니다.

![준수 관리자 - 대시보드](../media/compliance-manager-dashboard.png "준수 관리자 대시보드")

## <a name="understanding-your-compliance-score"></a>준수 점수 이해

규정 준수 관리자는 규정, 표준 또는 정책을 준수하기 위해 취한 개선 조치를 완료하기 위한 포인트를 수여하고 이러한 점수를 전체 준수 점수로 결합합니다. 각 작업은 관련된 잠재적인 위험에 따라 점수에 다른 영향을 미치게 됩니다. 준수 점수는 전반적인 준수 자세를 개선하기 위해 집중할 작업의 우선 순위를 지정하는 데 도움이 될 수 있습니다.

준수 관리자는 Microsoft 365 데이터 보호 기준에 따라 초기 점수를 제공합니다. 이 기준은 데이터 보호 및 일반 데이터 거버넌스에 대한 주요 규정 및 표준을 포함하는 제어 집합입니다.

##### <a name="learn-more"></a>자세한 정보

[준수 점수의 계산 방법을 이해합니다.](compliance-score-calculation.md)

[개선 작업 방법을 자세히 알아보고 개선 작업 을 수행 합니다.](compliance-manager-improvement-actions.md)

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>주요 요소: 컨트롤, 평가, 템플릿, 개선 작업

준수 관리자는 여러 데이터 요소를 사용하여 규정 준수 활동을 관리하는 데 도움이 됩니다. 준수 관리자를 사용하여 규정 준수 활동을 할당, 테스트 및 모니터링할 때 주요 요소(컨트롤, 평가, 템플릿 및 개선 작업)를 기본적으로 이해하면 도움이 됩니다.

### <a name="controls"></a>컨트롤

컨트롤은 규정, 표준 또는 정책의 요구 사항입니다. 시스템 구성, 조직 프로세스 및 규정, 표준 또는 정책의 특정 요구 사항을 충족하는 책임이 있는 사용자에 대해 평가하고 관리하는 방법을 정의합니다.

준수 관리자는 다음과 같은 유형의 컨트롤을 추적합니다.

1. **Microsoft 관리 컨트롤**: Microsoft가 구현을 담당하는 Microsoft 클라우드 서비스에 대한 컨트롤
2. **컨트롤**: 고객 관리 컨트롤이라고도 하는 이러한 컨트롤은 조직에서 구현 및 관리되는 컨트롤입니다.
3. **공유 컨트롤**: 조직과 Microsoft가 구현에 대한 책임을 공유하는 컨트롤입니다.

##### <a name="learn-more"></a>자세한 정보

[컨트롤의 진행률을 모니터링합니다.](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)

준수 관리자가 지속적으로 컨트롤을 [평가하는 방법을 알아보습니다.](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)

### <a name="assessments"></a>평가

평가는 특정 규정, 표준 또는 정책의 컨트롤 그룹화입니다. 평가 내에서 작업을 완료하면 표준, 규정 또는 법률의 요구 사항을 충족하는 데 도움이 됩니다. 예를 들어, 해당 내의 모든 작업을 완료하면 MICROSOFT 365 설정을 ISO 27001 요구 사항에 따라 가져오는 데 도움이 된다고 평가할 수 있습니다.

평가에는 여러 구성 요소가 있습니다.

- **범위 내 서비스**: 평가에 적용할 수 있는 특정 Microsoft 서비스 집합
- **Microsoft 관리 컨트롤**: Microsoft가 사용자 대신 구현하는 Microsoft 클라우드 서비스에 대한 컨트롤
- **컨트롤**: 고객 관리 컨트롤이라고도 하는 이러한 컨트롤은 조직에서 구현 및 관리되는 컨트롤입니다.
- **공유 컨트롤**: 조직과 Microsoft가 구현에 대한 책임을 공유하는 컨트롤입니다.
- **평가 점수:** 조직 및 Microsoft에서 관리하는 평가 내의 작업에서 가능한 총 점수 달성 진행률을 보여 주며

평가를 만들 때 평가를 그룹에 할당합니다. 조직에 가장 논리적인 방식으로 그룹을 구성할 수 있습니다. 예를 들어 감사 연도, 지역, 솔루션, 조직 내의 팀 또는 다른 방법으로 평가를 그룹화할 수 있습니다. 그룹을 만든 후 준수 [](compliance-manager-setup.md#filtering-your-dashboard-view) 관리자 대시보드를 필터링하여 하나 이상의 그룹으로 점수를 볼 수 있습니다.

##### <a name="learn-more"></a>자세한 정보

[준수 관리자에서 평가를 빌드하고 관리합니다.](compliance-manager-assessments.md)

### <a name="templates"></a>템플릿

준수 관리자는 평가를 빠르게 만드는 데 도움이 되는 템플릿을 제공합니다. 이러한 템플릿을 수정하여 요구에 최적화된 평가를 만들 수 있습니다. 자체 컨트롤 및 작업을 사용하여 템플릿을 만들어 사용자 지정 평가를 빌드할 수도 있습니다. 예를 들어 템플릿이 내부 비즈니스 프로세스 제어를 지원하거나 150개 이상의 미리 작성된 평가 템플릿 중 하나에 적용되지 않는 지역별 데이터 보호 표준을 사용할 수 있습니다.

##### <a name="learn-more"></a>자세한 정보

[준수 관리자에서 제공하는 평가 템플릿 목록을 를 시청하세요.](compliance-manager-templates-list.md)

[평가용 템플릿을](compliance-manager-templates.md)만들고 수정하는 방법에 대한 자세한 지침을 얻습니다.

### <a name="improvement-actions"></a>개선 작업

개선 작업은 규정 준수 활동을 중앙 집중화하는 데 도움이 됩니다. 각 개선 작업은 데이터 보호 규정 및 표준을 준수하는 데 도움이 되는 권장 지침을 제공합니다. 개선 작업을 조직의 사용자에게 할당하여 구현 및 테스트 작업을 수행할 수 있습니다. 개선 작업 내에 문서, 메모 및 상태 업데이트를 기록할 수 있습니다.

##### <a name="learn-more"></a>자세한 정보

[개선 작업을 사용하여 준수 워크플로를 관리합니다.](compliance-manager-improvement-actions.md)

[작업이 준수 점수에 미치는 영향에 대해 자세히 알아보습니다.](compliance-score-calculation.md#action-types-and-points)

## <a name="supported-languages"></a>지원되는 언어

준수 관리자는 다음 언어로 제공됩니다.

- 영어
- 바하사 인도네시아어
- 바하사 말레이어
- 중국어(간체)
- 중국어(번체)
- 체코어
- 덴마크어
- 네덜란드어
- 핀란드어
- 프랑스어
- 독일어
- 히브리어
- 헝가리어
- 이탈리아어
- 일본어
- 한국어
- 노르웨이어
- 폴란드어
- 포르투갈어(브라질)
- 러시아어
- 스페인어
- 스웨덴어
- 태국어
- 터키어

## <a name="next-steps-set-up-and-customize"></a>다음 단계: 설정 및 사용자 지정

준수 관리자 시작 에서 로그인, 사용 권한 및 역할 할당, 설정 구성 및 대시보드 보기 개인 설정 방법에 [대해 자세히 알아보습니다.](compliance-manager-setup.md)

그런 다음 평가를 설정하여 조직에 가장 중요한 산업 표준을 준수하는 데 도움이 하도록 준수 관리자를 [사용자 지정합니다.](compliance-manager-assessments.md)