---
title: Microsoft 규정 준수 점수 (미리 보기) 계산
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 규정 준수 점수가 위험을 해결 하 고 준수 상태를 개선 하기 위해 수행한 조치에 따라 개인 설정 점수를 계산 하는 방법을 이해 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024678"
---
# <a name="compliance-score-preview-calculation"></a>규정 준수 점수 (미리 보기) 계산

> [!IMPORTANT]
> 준수 점수 및 준수 관리자의 권장 사항을 준수 보장으로 해석하면 안 됩니다. 규정 환경에 따라 고객 컨트롤의 효율성을 평가 하 고 유효성을 검사 하는 작업은 사용자의 결정입니다. 이러한 서비스는 현재 미리 보기로 사용 되며 [온라인 서비스 약관](https://go.microsoft.com/fwlink/?linkid=2108910)의 사용 약관에 따라 달라 집니다. [보안 및 규정 준수에 대 한 자세한 내용은 Microsoft 365 라이선싱 지침을](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)참조 하세요.

## <a name="how-compliance-score-works"></a>준수 점수 작동 방식

규정 준수 점수 대시보드에는 컨트롤 내에서 향상 작업을 완료 하는 과정의 진행 상황을 측정 하는 점수가 표시 됩니다. 각 작업은 발생할 수 있는 잠재적 위험에 따라 점수에 서로 다른 영향을 줍니다. 점수는 전반적인 준수 상태를 개선 하기 위해 집중할 작업을 우선적으로 적용 하는 데 도움이 될 수 있습니다.

컨트롤에 대해 표시 되는 규정 준수 점수 값은 합격/불합격 기준에 따라 전체 점수 *에 적용 됩니다* . 컨트롤이 구현 되 고 후속 평가 테스트를 통과 하거나 그렇지 않은 경우 

컨트롤의 규정 준수 점수에는 다음과 같은 점수가 추가 됩니다.

- **구현 상태** 는 **구현** 됨 또는 **대체 구현**으로 동일 합니다.
- **테스트 결과가** **통과**됩니다.

컨트롤 점수는 향상 작업을 수행 하 여 획득 한 점수를 더한 값입니다. 계산 점수는 컨트롤 점수의 합계입니다. **평가 점수의 합은 전반적인 준수 점수입니다.**

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Microsoft 365 데이터 보호 기준을 기반으로 한 초기 점수
  
준수 점수가 Microsoft 365 데이터 보호 기준을 기반으로 초기 점수를 제공 합니다. 이 기준은 데이터 보호 및 일반 데이터 관리를 위한 주요 규정 및 표준을 포함 하는 컨트롤 집합입니다. 이 기준은 기본적으로 NIST CSF (표준 및 기술 Cybersecurity 프레임 워크) 및 ISO (국제 표준화 기구)를 비롯 하 여 FedRAMP (연방 위험 및 권한 부여 관리 프로그램) 및 GDPR (유럽 연합의 일반 데이터 보호 규정)의 요소를 그립니다.

다른 평가를 구성 하기 전에 모든 조직에서 기본적으로 제공 하는 데이터 보호 기준 평가는 초기 점수를 계산 하는 데 사용 됩니다. 처음 방문할 때 준수 점수는 이미 Microsoft 365 솔루션의 신호를 수집 하 고 있습니다. 주요 데이터 보호 표준 및 규정을 기준으로 조직이 수행 하는 방법을 한눈에 확인 하 고 고려해 야 할 개선 작업을 확인할 수 있습니다.

모든 조직에는 특정 요구 사항이 있기 때문에 규정 준수 점수를 통해 위험을 최대한 포괄적으로 최소화 하 고 관리 하는 데 도움이 되는 고유한 평가를 설정 및 관리할 수 있습니다.

## <a name="how-compliance-score-continuously-assesses-controls"></a>규정 준수 점수가 지속적으로 제어를 평가 하는 방법

규정 준수 점수가 Microsoft 365 환경을 자동으로 검색 하 고 시스템 설정을 계속 검색 하며, 기술 제어 상태를 자동으로 업데이트 합니다. 보안 점수는 모니터링을 수행 하는 기본 엔진입니다.

제어 상태는 24 시간 마다 준수 점수 대시보드에 업데이트 됩니다. 사용자가 컨트롤을 구현 하는 권장 사항을 따르면 다음 날에 제어 상태를 업데이트 한 것을 볼 수 있습니다.

예를 들어 Azure AD 포털에서 MFA (multi-factor authentication)를 설정 하는 경우 준수 점수가 설정을 감지 하 고 제어 액세스 솔루션 세부 정보에 해당 사실을 반영 합니다. 반대로, MFA를 설정 하지 않은 경우에는 권장 되는 조치로 인 한 준수 점수 플래그를 사용 합니다.

공개 미리 보기 중에는 일부 컨트롤에 대해서도 연속 평가를 사용할 수 있습니다.

#### <a name="learn-more"></a>자세히 알아보기
[보안 점수 및 작동 방식에 대해 읽어](../security/mtp/microsoft-secure-score-new.md)보세요.
  
## <a name="action-types-and-points"></a>작업 유형 및 점

준수 점수에는 관리 하는 작업 및 Microsoft가 관리 하는 작업 이라는 두 가지 유형의 작업이 추적 됩니다. 두 가지 작업 유형에 모두 완료 시 전체 점수를 계산 하는 점이 있습니다.

1. **점수가** 조직에서 관리 하는 컨트롤을 기반으로 준수 점수를 제공 합니다.
2. **Microsoft 관리 지점은** 클라우드 서비스 공급자로 microsoft가 관리 하는 작업을 기반으로 준수 점수에 기여 합니다.

작업에는 필수 또는 임의 인지에 따라 점수 값이 할당 되 고, 사용자에 게 예방, 예방용 인지 또는 정정 인지 여부가 결정 됩니다.

### <a name="mandatory-and-discretionary-actions"></a>필수 및 임의 작업

 - **필수 작업** 은 고의적으로 또는 실수로 건너뛸 수 없습니다. 예를 들어 암호 길이, 복잡성 및 만료에 대 한 요구 사항을 설정 하는 중앙 집중식으로 관리 되는 암호 정책이 있습니다. 사용자는 이러한 요구 사항을 준수 하 여 시스템에 액세스 해야 합니다.
  
 - **임의 작업** 은 사용자에 게 정책을 이해 하 고 그에 따라 조치를 취할 수 있도록 합니다. 예를 들어 사용자가 자신의 컴퓨터에서 작업을 수행 하는 데 사용 하는 정책입니다.
  
### <a name="preventative-detective-and-corrective-actions"></a>예방적, 예방용 인지 및 정정 작업
  
 - **예방적 작업** 은 특정 위험을 해결 합니다. 예를 들어 암호화를 사용 하 여 rest에서 정보를 보호 하는 것은 공격 및 침해에 대 한 예방 조치입니다. 의무의 분리는 관심 충돌을 관리 하 고 사기를 방지 하기 위한 예방 조치입니다.
  
 - **예방용 인지 작업** 은 시스템을 적극적으로 모니터링 하 여 위험을 나타내거나 침입 또는 침해를 감지 하는 데 사용할 수 있는 불규칙 한 조건이 나 행동을 식별 합니다. 예를 들면 시스템 액세스 감사 및 권한 있는 관리 작업을 예로 들 있습니다. 규정 준수 감사는 프로세스 문제를 찾는 데 사용 되는 예방용 인지 작업 유형입니다.
  
- **정정 작업** 에서는 보안 인시던트가 부정적으로 영향을 최소화 하 고, 정정 작업을 수행 하 여 즉각적인 영향을 줄이고, 가능한 경우 피해를 반대로 유지 합니다. 개인 정보 보호 인시던트 응답은 손상을 제한 하 고 위반 후 시스템을 작동 상태로 복원 하기 위한 정정 작업입니다.
  
각 작업은 표시 되는 위험에 따라 규정 준수 점수에 할당 된 값을 가집니다.

|**유형**|**할당 된 점수**|
|:-----|:-----|
| 예방적 필수 | kb(56kbps |
| 예방적 임의 | 9  |
| 예방용 인지 필수 | 3  |
| 예방용 인지 임의 | 1  |
| 정정 필수 | 3  |
| 정정 임의 | 1  |
  
![규정 준수 점수 컨트롤 포인트 값](../media/compliance-score-controls-scoring.png "규정 준수 점수 컨트롤 포인트 값")