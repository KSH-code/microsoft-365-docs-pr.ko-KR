---
title: 인시던트 우선 순위를 Microsoft 365 Defender
description: 2016년 8월의 인시던트 큐에서 인시던트 필터링 Microsoft 365 Defender
keywords: 인시던트, 큐, 개요, 장치, ID, 사용자, 사서함, 전자 메일, 인시던트, 분석, 응답, Triage
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
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
ms.openlocfilehash: d3dea119e73da7d0b0e8745ea1f96969f4818ac8
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914323"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>인시던트 우선 순위를 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

Microsoft 365 Defender 상관 관계 분석을 적용하고 다양한 제품의 관련 경고 및 자동화된 조사를 인시던트로 집계합니다. Microsoft 365 Defender 전체 제품군에 걸쳐 있는 종단 간 표시 여부가 Microsoft 365 Defender 악성으로만 식별될 수 있는 활동에 대해 고유한 경고를 트리거합니다. 이 보기는 보안 분석가에게 보다 광범위한 공격 스토리를 제공하여 조직 전체의 복잡한 위협을 더 잘 이해하고 대응하는 데 도움이 됩니다.

**인시던트 큐에는** 장치, 사용자 및 사서함에서 만들어진 인시던트 모음이 표시됩니다. 이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다. 이를 인시던트 Triage라고도 합니다.

인시던트 및  인시던트 & 포털(>)의 빠른 실행에서 인시던트 Microsoft 365 Defender 큐로[security.microsoft.com.](https://security.microsoft.com) 다음은 예입니다.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="인시던트 큐의 예입니다." lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

최근 **인시던트** 및 알림 섹션에는 지난 24시간 동안 수신된 경고 및 인시던트 수의 그래프가 표시됩니다.

기본적으로 Microsoft 365 Defender 포털의 인시던트 큐에는 지난 6개월 동안의 인시던트가 표시됩니다. 가장 최근 인시던트는 목록 맨 위에 있으므로 먼저 볼 수 있습니다.

인시던트 큐에는 인시던트 또는 영향을 주는 엔터티의 다양한 특성을 표시하는 사용자 지정 가능한 열이 있습니다(열 선택 선택). 이를 통해 분석을 위한 인시던트 우선 순위에 대한 정보를 통해 의사 결정을 내리는 데 도움이 됩니다.

추가 가시성을 위해 자동 인시던트 명명은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 인시던트 이름을 생성합니다. 이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.

예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*

> [!NOTE]
> 자동 인시던트 명명을 출시하기 전에 존재한 인시던트의 이름은 변경되지 않습니다.

또한 인시던트 큐는 여러 필터링 옵션을 노출합니다. 이 옵션을 적용하면 환경의 모든 기존 인시던트에 대한 광범위한 스위프를 수행하거나 특정 시나리오 또는 위협에 집중할 수 있습니다. 사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다. 

## <a name="available-filters"></a>사용 가능한 필터

기본 인시던트 큐에서  필터를 선택하여 필터링된 인시던트 집합을 볼 수 있는 필터 창을 볼 수 있습니다. 예를 들면 다음과 같습니다.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="문제 큐에 대한 필터 창의 예입니다." lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

다음 표에는 사용 가능한 필터 이름이 나열되어 있습니다.

| 필터 이름 | 설명 |
|:-------|:-----|
| 할당된 사용자 | 사용자에게 할당된 경고 또는 자동화에서 처리하는 경고를 표시하기로 선택할 수 있습니다. |
| Categories | 범주를 선택해 특정 전략, 기술 또는 공격 구성 요소에 집중합니다. |
| 분류 | 관련 경고의 설정된 분류에 따라 인시던트 필터링 값에는 실제 경고, 거짓 경고 또는 설정되지 않은 알림이 포함됩니다. |
| 데이터 민감도 | 일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다.  필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.   <br><br> Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.|
| 장치 그룹 | 정의된 장치 그룹으로 필터링합니다. |
| 조사 상태 | 자동화된 조사 상태를 통해 인시던트 필터링  |
| 다중 범주 | 여러 범주에 매핑된 인시던트만 표시하여 잠재적으로 더 많은 손상을 일으킬 수 있는 인시던트만 보게 선택할 수 있습니다. |
| 다중 서비스 원인  | 다른 원본(끝점용 Microsoft Defender, Microsoft Cloud App Security, ID용 Microsoft Defender, Microsoft Defender for Office 365)의 경고만 표시하기 위해 필터링합니다. |
| OS 플랫폼 | 운영 체제에 따라 인시던트 큐 보기를 제한합니다. |
| 서비스 원인 | 특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다. |
| 심각도 | 인시던트의 심각도는 자산에 미칠 수 있는 영향을 나타내는 것입니다. 심각도가 높을수록 영향이 클수록 일반적으로 가장 즉각적인 주의가 필요합니다. |
| 상태 | 상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다. |
|||

## <a name="save-defined-filters-as-urls"></a>정의된 필터를 URL로 저장

문제 큐에서 유용한 필터를 구성한 후 브라우저 탭의 URL에 책갈피를 지정하거나 웹 페이지, Word 문서 또는 원하는 장소에 링크로 저장할 수 있습니다. 이렇게 하면 한 번의 클릭으로 인시던트 큐의 주요 보기에 액세스할 수 있습니다.

- 새 인시던트
- 높은 심각도 인시던트
- 미지정 인시던트
- 높은 심각도, 미지정 인시던트
- 내게 할당된 인시던트
- 내게 할당된 인시던트 및 끝점용 Microsoft Defender
- 특정 태그 또는 태그가 있는 인시던트
- 특정 위협 범주가 있는 인시던트
- 특정 관련 위협이 있는 인시던트
- 특정 배우와의 인시던트

유용한 필터 보기 목록을 URL로 컴파일하고 저장한 후 이를 사용하여 큐의 인시던트 처리 및 우선 [](manage-incidents.md) 순위를 빠르게 지정하고 후속 할당 및 분석을 위해 이를 관리할 수 있습니다.

## <a name="next-steps"></a>다음 단계

우선 순위가 가장 높은 인시던트가 필요한 인시던트가 결정되면 선택하고 다음을 선택합니다.

- [태그,](manage-incidents.md) 할당, 가짓 긍정 인시던트에 대한 즉각적인 해결 및 설명에 대한 인시던트의 속성을 관리합니다.
- 조사를 [시작 합니다.](investigate-incidents.md)

## <a name="see-also"></a>참고 항목
- [인시던트 개요](incidents-overview.md)
- [인시던트 관리](manage-incidents.md)
- [인시던트 조사](investigate-incidents.md)
