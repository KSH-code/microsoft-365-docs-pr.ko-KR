---
title: Microsoft 365 Defender의 인시던트
description: Microsoft 365 보안 센터에서 장치, 사용자 및 사서함에 걸쳐 볼 수 있는 인시던트 조사
keywords: 인시던트, 경고, 조사, 분석, 대응, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365
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
ms.openlocfilehash: 890e64367c49c24c8c70e2cbda9869a5d0797219
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939591"
---
# <a name="incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender의 인시던트

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험해 보고 싶으신가요? [랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.
>

Microsoft 365 Defender의 인시던트는 공격의 스토리를 만드는 상관 관계 있는 경고 및 관련 데이터의 모음입니다. 

Microsoft 365 서비스 및 앱은 의심스러운 또는 악의적인 이벤트 또는 활동을 감지할 때 경고를 생성합니다. 개별 경고는 완료되거나 지속적인 공격에 대한 중요한 단서를 제공합니다. 그러나 공격은 일반적으로 장치, 사용자 및 사서함과 같은 다양한 유형의 엔터티에 대해 다양한 기술을 사용합니다. 그 결과 테넌트의 여러 엔터티에 대한 여러 경고가 생성됩니다. 

개별 경고를 함께 하여 공격에 대한 통찰력을 확보하는 것은 어렵고 시간이 많이 소요될 수 있기 때문에 Microsoft 365 Defender는 경고 및 관련 정보를 인시던트에 자동으로 집계합니다.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender가 엔터티의 이벤트를 인시던트와 상관 관계 지정하는 방법":::

Microsoft 365 Defender의 인시던트에 대한 간략한 개요(4분)를 시청하세요.

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

관련 경고를 인시던트로 그룹화하면 공격을 포괄적으로 볼 수 있습니다. 예를 들어 다음을 볼 수 있습니다.

- 공격이 시작된 위치입니다.
- 사용된 전술
- 공격이 테넌트에 얼마나 들어갔는가.
- 공격 범위(예: 영향을 받는 장치, 사용자 및 사서함 수)입니다. 
- 공격과 관련된 모든 데이터입니다.

[활성화된](m365d-enable.md)경우 Microsoft 365 Defender는 자동화 및 인공 지능을 통해 경고를 자동으로 조사하고 해결할 수 있습니다. 추가 수정 단계를 수행하여 공격을 해결할 수도 있습니다. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Microsoft 365 보안 센터의 인시던트 및 경고

Microsoft 365 보안 센터(&)의 > 인시던트 및 인시던트 경고에서 인시던트 security.microsoft.com[관리합니다.](https://security.microsoft.com)  다음은 예입니다.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 보안 센터의 인시던트 페이지":::

인시던트 이름을 선택하면 인시던트 요약이 표시될 수 있으며 추가 정보가 있는 탭에 액세스할 수 있습니다.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 보안 센터의 인시던트에 대한 요약 페이지 예":::

인시던트에 대한 추가 탭은:

- 경고 

  인시던트 및 해당 정보와 관련된 모든 경고입니다.

- 디바이스

  인시던트의 일부로 식별되거나 인시던트와 관련된 모든 장치입니다.

- 사용자

  인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사용자입니다.

- 사서함

  인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사서함입니다.

- 조사

  인시던트의 경고에 의해 트리거된 모든 자동화된 조사.

- 증거 및 응답

  인시던트의 경고에서 지원되는 모든 이벤트 및 의심스러운 엔터티

다음은 인시던트와 인시던트 데이터 및 Microsoft 365 보안 센터의 인시던트 탭 간의 관계입니다.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Microsoft 365 보안 센터에서 인시던트와 인시던트의 데이터와 인시던트의 관계":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Microsoft 365 Defender의 인시던트 대응 워크플로 예

다음은 Microsoft 365 보안 센터를 사용하여 Microsoft 365의 인시던트에 응답하기 위한 예제 워크플로입니다.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Microsoft 365에 대한 인시던트 대응 워크플로의 예":::

지속적인 기준에 따라 인시던트 큐에서 분석 및 해결을 위해 우선 순위가 가장 높은 인시던트를 식별하고 대응을 준비합니다. 이 조합은

- [인시던트](incident-queue.md) 큐 필터링 및 정렬을 통해 우선 순위가 가장 높은 인시던트 결정
- [직위를](manage-incidents.md) 수정하고, 분석가에게 할당하고, 태그와 설명을 추가하여 인시던트 관리

1. 각 인시던트에 대해 공격 [및 경고 분석을 시작합니다.](investigate-incidents.md)

   a. 인시던트의 요약을 보고 인시던트의 범위 및 심각도와 영향을  받는 엔터티(요약 탭)를 이해합니다.

   b. 경고의 출처, 범위 및 심각도(경고 탭)를  이해하기 위해 경고 분석을 시작하십시오.

   c. 필요한 경우 영향을 받는 장치, 사용자 및 사서함(장치, 사용자 및 사서함 탭)에 대한 **정보를** 수집합니다. 

   d. Microsoft 365 Defender가 일부 경고(조사 탭)를 자동으로 해결한 **방법을** 참조합니다.
   
   e. 필요한 경우 인시던트에 대한 데이터 집합의 정보를 사용하여 자세한 정보(증거 및 응답 **탭)를 사용합니다.**

2. 분석 후 또는 분석 중에 보안 위협의 공격 및 제거에 대한 추가 영향을 줄이기 위한 포함 문제를 해결합니다.

3. 테넌트 리소스를 인시던트 이전 상태로 복원하여 공격으로부터 복구합니다.

4. [인시던트](manage-incidents.md#resolve-incident) 문제를 해결하고 인시던트 사후 학습을 통해 다음을 할 수 있습니다.

   - 공격의 유형과 그 영향에 대해 이해합니다.
   - [위협](threat-analytics.md) 분석 및 보안 커뮤니티에서 공격을 조사하여 보안 공격 추세를 조사합니다.
   - 인시던트 해결에 사용한 워크플로를 회수하고 필요한 경우 표준 워크플로, 프로세스, 정책 및 플레이북을 업데이트합니다.
   - 보안 구성의 변경이 필요한지 여부를 결정하고 구현합니다.

## <a name="example-security-operations-for-microsoft-365-defender"></a>Microsoft 365 Defender에 대한 보안 작업 예

다음은 Microsoft 365 Defender에 대한 보안 작업의 예입니다.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Micosoft 365 Defender의 보안 작업 예":::

일별 작업에는 다음이 포함됩니다.

- [인시던트](manage-incidents.md) 관리
- 자동화된 조사 및 [대응(AIR)](m365d-action-center.md) 작업 검토
- 최신 위협 [분석 검토](threat-analytics.md)
- [인시던트에](investigate-incidents.md) 응답

월별 작업에는 다음이 포함됩니다.

- AIR [설정 검토](m365d-configure-auto-investigation-response.md)
- 보안 [점수 및](microsoft-secure-score-improvement-actions.md) 위협 요소 [& 관리 검토](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- IT 보안 관리 체인에 보고

분기별 작업에는 CISO(최고 정보 보안 책임자)에게 보안 결과를 보고하고 브리핑할 수 있습니다.

연간 작업에는 직원, 시스템 및 프로세스를 테스트하기 위한 주요 인시던트 또는 위반 연습 수행이 포함됩니다. 

매일, 월별, 분기별 및 연간 작업을 사용하여 프로세스, 정책 및 보안 구성을 업데이트하거나 구체화할 수 있습니다.

## <a name="next-steps"></a>다음 단계

인시던트  페이지의 인시던트 큐에 최근 인시던트가 나열됩니다. 여기에서 다음을 할 수 있습니다.

- 심각도 및 기타 [](incident-queue.md) 요인에 따라 우선 순위를 지정해야 하는 사고를 참조합니다. 
- [인시던트](manage-incidents.md)관리 워크플로의 이름 변경, 할당, 분류 및 태그 및 설명 추가를 포함하는 인시던트 관리
- [인시던트 분석을](investigate-incidents.md) 수행 합니다.
