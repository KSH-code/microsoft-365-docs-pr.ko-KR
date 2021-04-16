---
title: Microsoft 365 Defender에서 인시던트 우선 순위 지정
description: Microsoft 365 Defender의 인시던트 큐에서 인시던트 필터링 방법 학습
keywords: 사고, 큐, 개요, 장치, 식별, 사용자, 사서함, 전자 메일, 사고
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8acd8d85826d7bda399c03cc60f2806af954c6c3
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861606"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender에서 인시던트 우선 순위 지정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

Microsoft 365 Defender는 상관 관계 분석을 적용하고 관련 경고 및 다양한 제품의 자동화된 조사를 인시던트에 집계합니다. 또한 Microsoft 365 Defender는 전체 제품군에 걸쳐 Microsoft 365 Defender가 보유하고 있는 종단 간 표시가 있는 경우 악성으로만 식별될 수 있는 활동에 대해 고유한 경고를 트리거합니다. 이 보기는 보안 분석가에게 보다 광범위한 공격 스토리를 제공하여 조직 전체의 복잡한 위협을 더 잘 이해하고 대응하는 데 도움이 됩니다.

**인시던트 큐에는** 장치, 사용자 및 사서함에서 만들어진 인시던트 모음이 표시됩니다. 이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다. 

인시던트 및  인시던트 & Microsoft 365 보안 센터(>)의 빠른 실행에서 인시던트[큐로 security.microsoft.com.](https://security.microsoft.com)

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="인시던트 큐의 예":::

기본적으로 Microsoft 365 보안 센터의 인시던트 큐에는 지난 6개월 동안의 인시던트가 표시됩니다. 가장 최근 인시던트는 목록 맨 위에 있으므로 먼저 볼 수 있습니다.

인시던트 큐에는 인시던트 또는 영향을 주는 엔터티의 다양한 특성을 표시하는 사용자 지정 가능한 열이 있습니다(열 선택 선택). 이를 통해 분석을 위한 인시던트 우선 순위에 대한 정보를 통해 의사 결정을 내리는 데 도움이 됩니다.

추가 가시성을 위해 자동 인시던트 명명은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 인시던트 이름을 생성합니다. 이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.

예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*

> [!NOTE]
> 자동 인시던트 명명을 출시하기 전에 존재한 인시던트의 이름은 변경되지 않습니다.

또한 인시던트 큐는 여러 필터링 옵션을 노출합니다. 이 옵션을 적용하면 환경의 모든 기존 인시던트에 대한 광범위한 스위프를 수행하거나 특정 시나리오 또는 위협에 집중할 수 있습니다. 사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다. 

## <a name="available-filters"></a>사용 가능한 필터

기본 인시던트 큐에서  필터를 선택하여 필터링된 인시던트 집합을 볼 수 있는 필터 창을 볼 수 있습니다. 예를 들면 다음과 같습니다.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="인시던트 큐에 대한 필터 창의 예":::

다음 표에는 사용 가능한 필터 이름이 나열되어 있습니다.

| 필터 이름 | 설명 |
|:-------|:-----|
| 할당된 사용자 | 사용자에게 할당된 경고 또는 자동화에서 처리하는 경고를 표시하기로 선택할 수 있습니다. |
| 범주 | 범주를 선택해 특정 전략, 기술 또는 공격 구성 요소에 집중합니다. |
| 분류 | 관련 경고의 설정된 분류에 따라 인시던트 필터링 값에는 실제 경고, 거짓 경고 또는 설정되지 않은 알림이 포함됩니다. |
| 데이터 민감도 | 일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다.  필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.   <br><br> Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.|
| 장치 그룹 | 정의된 장치 그룹으로 필터링합니다. |
| 조사 상태 | 자동화된 조사 상태를 통해 인시던트 필터링  |
| 다중 범주 | 여러 범주에 매핑된 인시던트만 표시하여 잠재적으로 더 많은 손상을 일으킬 수 있는 인시던트만 보게 선택할 수 있습니다. |
| 다중 서비스 원인  | 다른 원본(끝점용 Microsoft Defender, Microsoft Cloud App Security, ID용 Microsoft Defender, Office 365용 Microsoft Defender)의 경고가 포함된 인시던트만 표시하기 위해 필터링합니다. |
| OS 플랫폼 | 운영 체제에 따라 인시던트 큐 보기를 제한합니다. |
| 서비스 원인 | 특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다. |
| 심각도 | 인시던트의 심각도는 자산에 미칠 수 있는 영향을 나타내는 것입니다. 심각도가 높을수록 영향이 클수록 일반적으로 가장 즉각적인 주의가 필요합니다. |
| 상태 | 상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다. |
|||

## <a name="incident-response-workflow"></a>인시던트 대응 워크플로

다음은 인시던트에 응답하기 위한 일반적인 워크플로입니다.

1. 조사 및 해결을 위해 우선 순위가 가장 높은 인시던트 식별 및 세분화
2. 우선 순위가 높은 각 인시던트에 대해 조사를 [시작합니다.](investigate-incidents.md)

   a. 인시던트의 요약을 보고 인시던트의 범위, 영향을 받는 엔터티 및  심각도(요약 탭)를 이해합니다.

   b. 경고를 보고 시작하여 경고의 출처, 범위 및 **심각도(경고** 탭)를 이해합니다.

   c. 필요한 경우 영향을 받는 장치, 사용자 및 사서함(장치, 사용자 및 사서함 탭)에 대한 **정보를** 수집합니다. 

   d. Microsoft 365 Defender가 일부 경고(조사 탭)를 자동으로 해결한 **방법을** 참조합니다.
   
   e. 필요한 경우 인시던트에 대한 데이터 집합의 정보를 사용하여 자세한 정보(증거 및 응답 **탭)를 사용합니다.**

조사할 때 다음을 염려해야 합니다.

- 포함: 테넌트에 대한 추가 영향을 줄입니다.
- 지우기: 보안 위협 제거.
- 복구: 테넌트 리소스를 공격 전에 있는 상태로 복원합니다.

인시던트 해결 후 잠시 시간을 내어 다음을 배우는 것이 가장 까다로워야 합니다.

- 공격의 유형과 그 영향에 대해 이해합니다.
- 보안 커뮤니티에서 보안 공격 추세를 조사합니다.
- 인시던트 해결에 사용한 워크플로를 회수하고 필요한 경우 표준 워크플로 및 플레이북을 업데이트합니다.

다음은 기본 프로세스에 대한 요약입니다.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="인시던트 조사를 위한 기본 프로세스":::

## <a name="next-step"></a>다음 단계

우선 순위가 가장 높은 인시던트가 필요한 사고를 확인한 후 해당 인시던트 를 선택하고 조사를 [시작합니다.](investigate-incidents.md)

## <a name="see-also"></a>참고 항목
- [사고 개요](incidents-overview.md)
- [사고 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)
