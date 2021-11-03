---
title: 인시던트에 대한 Microsoft 365 Defender
description: 사이트 포털에서 장치, 사용자 및 사서함에 걸쳐 볼 수 있는 인시던트 Microsoft 365 Defender 조사합니다.
keywords: 인시던트, 경고, 조사, 분석, 대응, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365, 인시던트 대응, 사이버 공격
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
ms.openlocfilehash: a1ef2dde05bd2244ea982cfa2dabd5927484f46b
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724383"
---
# <a name="incident-response-with-microsoft-365-defender"></a>인시던트에 대한 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험하고 싶으신가요? [실험실 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.
>

이 Microsoft 365 Defender 인시던트는 공격의 스토리를 만드는 상호 관련된 경고 및 관련 데이터의 모음입니다. 

Microsoft 365 및 앱은 의심스러우거나 악의적인 이벤트나 활동을 감지할 때 경고를 생성합니다. 개별 경고는 완료되거나 지속적인 공격에 대한 중요한 단서를 제공합니다. 그러나 공격은 일반적으로 장치, 사용자 및 사서함과 같은 다양한 유형의 엔터티에 대해 다양한 기술을 사용합니다. 그 결과 테넌트의 여러 엔터티에 대한 여러 경고가 생성됩니다. 

개별 경고를 함께 하여 공격에 대한 통찰력을 확보하는 것은 까다롭고 시간이 많이 소요될 수 Microsoft 365 Defender 경고 및 관련 정보를 인시던트에 자동으로 집계합니다.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="엔터티 Microsoft 365 Defender 이벤트와 인시던트의 상관 관계가 지정되는 방법":::

4분 동안의 인시던트에 대한 Microsoft 365 Defender 간략한 개요를 시청하세요.

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

관련 경고를 인시던트로 그룹화하면 공격을 포괄적으로 볼 수 있습니다. 예를 들어 다음을 볼 수 있습니다.

- 공격이 시작된 위치입니다.
- 사용된 전술
- 공격이 테넌트에 얼마나 들어갔는가.
- 공격 범위(예: 영향을 받는 장치, 사용자 및 사서함 수)입니다. 
- 공격과 관련된 모든 데이터입니다.

이 [옵션을](m365d-enable.md)Microsoft 365 Defender 자동화 [](m365d-autoir.md) 및 인공 지능을 통해 경고를 자동으로 조사하고 해결할 수 있습니다. 추가 수정 단계를 수행하여 공격을 해결할 수도 있습니다. 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>사이트 포털의 인시던트 Microsoft 365 Defender 알림

인시던트  및 인시던트 & 포털(>)의 빠른 실행에서 인시던트 Microsoft 365 Defender 관리합니다 security.microsoft.com.[](https://security.microsoft.com) 다음은 예입니다.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="사이트 포털의 인시던트 Microsoft 365 Defender.":::

인시던트 이름을 선택하면 인시던트 요약이 표시될 수 있으며 추가 정보가 있는 탭에 액세스할 수 있습니다.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="사이트 포털의 인시던트에 대한 요약 Microsoft 365 Defender 예":::

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

  [인시던트의](m365d-autoir.md) 경고에 의해 트리거된 모든 자동화된 조사.

- 증거 및 응답

  인시던트의 경고에서 지원되는 모든 이벤트 및 의심스러운 엔터티

- Graph(미리 보기)

  공격의 일부인 여러 의심스러운 엔터티를 사용자, 장치 및 사서함과 같은 관련 자산과 연결하는 공격의 시각적 표현입니다.

다음은 인시던트와 인시던트 데이터 및 인시던트 포털에서 인시던트의 탭 Microsoft 365 Defender 관계입니다.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="인시던트 및 데이터와 인시던트 포털의 인시던트 탭 간의 Microsoft 365 Defender.":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>예제 인시던트 대응 워크플로를 Microsoft 365 Defender

다음은 Microsoft 365 포털을 사용하여 인시던트에 응답하기 위한 Microsoft 365 Defender 예제입니다.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="관리에 대한 인시던트 대응 워크플로의 Microsoft 365.":::

지속적인 기준에 따라 인시던트 큐에서 분석 및 해결을 위해 우선순위가 가장 높은 인시던트를 식별하고 대응을 준비합니다. 이러한 조치는 다음으로 구성됩니다.

- [인시던트](incident-queue.md) 큐 필터링 및 정렬을 통해 우선 순위가 가장 높은 인시던트 결정
- [직위를](manage-incidents.md) 수정하고, 분석가에게 할당하고, 태그와 설명을 추가하여 인시던트 관리

1. 각 인시던트에 대해 [공격을 시작하고 조사 및 분석을 경고합니다.](investigate-incidents.md)
 
   1. 인시던트의 요약을 확인하여 인시던트의 범위 및 심각도와  요약 및  보기(미리 보기) 탭으로 영향을 받는 엔터티를 Graph 파악합니다.

   1. 경고 탭을 사용하여 경고의 출처, 범위 및 심각도에 대해 이해하기 위해 경고 분석을 **시작하십시오.**

   1. 필요한 경우 장치, 사용자 및 사서함 탭을 사용하여 영향을 받는 장치, 사용자 및 사서함에 대한 **정보를** 수집합니다.

   1. 조사 탭에서 Microsoft 365 Defender [](m365d-autoir.md) 경고를 자동으로 해결한 방법을 **참조합니다.**
   
   1. 필요한 경우 증거 및 응답 탭에서 자세한 정보를 위해 인시던트에 대한 데이터 **집합의 정보를** 사용합니다.

2. 분석 후 또는 분석 중에 억제를 수행하여 보안 위협의 공격 및 제거에 대한 추가 영향을 줄입니다.

3. 가능하면 테넌트 리소스를 인시던트 이전 상태로 복원하여 공격으로부터 복구합니다.

4. [인시던트](manage-incidents.md#resolve-an-incident) 문제를 해결하고 인시던트 사후 학습을 통해 다음을 할 수 있습니다.

   - 공격의 유형과 그 영향에 대해 이해합니다.
   - [위협](threat-analytics.md) 분석 및 보안 커뮤니티에서 공격을 조사하여 보안 공격 추세를 조사합니다.
   - 인시던트 해결에 사용한 워크플로를 회수하고 필요한 경우 표준 워크플로, 프로세스, 정책 및 플레이북을 업데이트합니다.
   - 보안 구성의 변경이 필요한지 여부를 결정하고 구현합니다.

보안 분석이 처음인 경우 [](incidents-overview.md) 추가 정보는 첫 번째 인시던트에 응답하는 소개를 참조하고 인시던트 예제를 안내합니다.

Microsoft 제품 전반의 인시던트 대응에 대한 자세한 내용은 이 [문서를 참조하세요.](/security/compass/incident-response-overview)

## <a name="example-security-operations-for-microsoft-365-defender"></a>보안 작업의 Microsoft 365 Defender

다음은 보안 작업(SecOps)의 예입니다Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="보안 작업의 예로는 Microsoft 365 Defender.":::

일별 작업에는 다음이 포함됩니다.

- [인시던트](manage-incidents.md) 관리
- 관리 [센터에서 자동화된 조사 및 대응(AIR)](m365d-action-center.md) 작업 검토
- 최신 위협 [분석 검토](threat-analytics.md)
- [인시던트에](investigate-incidents.md) 응답

월별 작업에는 다음이 포함됩니다.

- AIR [설정 검토](m365d-configure-auto-investigation-response.md)
- 보안 [점수 및](microsoft-secure-score-improvement-actions.md) 위협 요소 [& 관리 검토](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- IT 보안 관리 체인에 보고

분기별 작업에는 CISO(최고 정보 보안 책임자)에게 보안 결과를 보고하고 브리핑할 수 있습니다.

연간 작업에는 직원, 시스템 및 프로세스를 테스트하기 위한 주요 인시던트 또는 위반 연습 수행이 포함됩니다. 

매일, 월별, 분기별 및 연간 작업을 사용하여 프로세스, 정책 및 보안 구성을 업데이트하거나 구체화할 수 있습니다.

자세한 [내용은 보안 Microsoft 365 Defender](integrate-microsoft-365-defender-secops.md) 통합을 참조합니다.

### <a name="secops-resources-across-microsoft-products"></a>Microsoft 제품 전반의 SecOps 리소스

Microsoft 제품 전반의 SecOps에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [기능](/security/compass/security-operations-capabilities)
- [모범 사례](/security/compass/security-operations)
- [비디오 및 슬라이드](/security/compass/security-operations-videos-and-decks)


## <a name="get-incident-notifications-by-email"></a>전자 메일로 인시던트 알림 확인

새 인시던트 Microsoft 365 Defender 기존 인시던트에 대한 업데이트에 대한 전자 메일로 직원에게 알리도록 사용자 계정을 설정할 수 있습니다. 다음에 따라 알림을 하게 선택할 수 있습니다.

- 인시던트 심각도.
- 장치 그룹.
- 인시던트당 첫 번째 업데이트에만 해당합니다.

전자 메일 알림에는 인시던트 이름, 심각도, 범주 등 인시던트에 대한 중요한 세부 정보가 포함되어 있습니다. 인시던트로 바로 이동하여 분석을 바로 시작할 수도 있습니다. 자세한 내용은 인시던트 [조사를 참조하세요.](investigate-incidents.md)

전자 메일 알림에서 받는 사람을 추가하거나 제거할 수 있습니다. 새 받는 사람은 인시던트가 추가된 후 인시던트에 대한 알림을 받을 수 있습니다. 

>[!NOTE]
>전자 메일 알림 설정을 구성하려면 '보안 설정 관리' 권한이 필요합니다. 기본 사용 권한 관리를 사용하도록 선택한 경우 보안 관리자 또는 전역 관리자 역할이 있는 사용자는 자동으로 전자 메일 알림을 구성할 수 있습니다. <br> <br>
마찬가지로 조직에서 RBAC(역할 기반 액세스 제어)를 사용하는 경우 관리할 수 있는 장치 그룹에 따라 알림을 만들고, 편집하고, 삭제하고, 받을 수만 있습니다.

### <a name="create-a-rule-for-email-notifications"></a>전자 메일 알림에 대한 규칙 만들기

다음 단계에 따라 새 규칙을 만들고 전자 메일 알림 설정을 사용자 지정하세요.

1. 탐색 창에서 **인시던트 설정 > Microsoft 365 Defender > 알림을 선택합니다.**
2. 항목 **추가를 선택합니다.**
3. 기본 **페이지에서** 규칙 이름과 설명을 입력하고 다음 을 **선택합니다.**
4. 알림 **설정 페이지에서** 다음을 구성합니다.
    - **경고 심각도** - 인시던트 알림을 트리거할 경고 심각도를 선택합니다. 예를 들어 심각도 높은 인시던트에 대한 정보만 원할 경우 높음 을 **선택합니다.**
    - **장치 그룹 범위** - 모든 장치 그룹을 지정하거나 테넌트의 장치 그룹 목록에서 선택할 수 있습니다.
    - **인시던트당 첫 발생에만 알림** - 기타 선택 영역과 일치하는 첫 경고에 대해서만 알림을 받길 원하는 경우 선택합니다. 인시던트와 관련된 추후 업데이트 또는 경고에 대해서는 추가 알림이 발송되지 않습니다.
    - **전자 메일에 조직 이름 포함** - 전자 메일 알림에 조직 이름을 표시하려면 선택합니다.
    - **테넌트별 포털 링크 포함** - 전자 메일 알림에 특정 Microsoft 365 테넌트에 액세스하기 위한 테넌트 ID가 포함된 링크를 추가하려면 선택합니다.

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="인시던트 전자 메일 알림에 대한 알림 설정입니다.":::

5. **다음** 을 선택합니다. 받는 **사람 페이지에서** 인시던트 알림을 받을 전자 메일 주소를 추가합니다. 각 **새 전자** 메일 주소를 입력한 후 추가를 선택합니다. 알림을 테스트하고 받는 사람이 받은 편지함으로 받는지 확인하려면 테스트 전자 메일 **보내기 를 선택합니다.** 
6. **다음** 을 선택합니다. 규칙 **검토 페이지에서** 규칙 설정을 검토한 다음 규칙 만들기 **를 선택합니다.** 받는 사람은 설정에 따라 전자 메일을 통해 인시던트 알림을 수신하기 시작할 것입니다.

기존 규칙을 편집하려면 규칙 목록에서 해당 규칙을 선택합니다. 규칙 이름이 있는 창에서 규칙  편집을 선택하고 **기본,** 알림 설정 및 받는 사람 페이지에서 **변경합니다.**

규칙을 삭제하려면 규칙 목록에서 규칙을 선택합니다. 규칙 이름이 있는 창에서 삭제를 **선택합니다.**


## <a name="training-for-security-analysts"></a>보안 분석가를 위한 교육

Microsoft Learn의 이 학습 모듈을 사용하여 인시던트 및 경고를 관리하는 Microsoft 365 Defender 방법을 이해합니다.

|교육:|Microsoft 365 Defender로 하는 인시던트 조사|
|---|---|
|![교육 아이콘을 Microsoft 365 Defender 조사합니다.](../../media/incidents-overview/m365-defender-address-security-investigation.svg)| Microsoft 365 Defender 서비스의 위협 데이터를 통합하고 AI를 사용하여 인시던트 및 경고에 결합합니다. 인시던트와 후속 조치와 해결을 위한 관리 사이의 시간을 최소화하는 방법을 배워보세요. <p> 27분 - 6단위 |

> [!div class="nextstepaction"]
> [시작 >](/learn/modules/defender-investigate-incidents/)

## <a name="next-steps"></a>다음 단계

보안 팀의 경험 수준 또는 역할에 따라 나열된 단계를 사용하세요.

### <a name="experience-level"></a>환경 수준

보안 분석 및 인시던트 대응에 대한 환경 수준은 다음 표를 따르하세요.

| 수준 | 단계 |
|:-------|:-----|
| **신규** | <ol><li> 예제 [](first-incident-overview.md) 공격을 통해 Microsoft 365 Defender 포털에서 일반적인 분석, 수정 및 사후 인시던트 검토 프로세스를 안내하는 안내를 받을 수 있는 첫 번째 인시던트에 응답 안내를 참조하세요. </li><li> 심각도 및 기타 [](incident-queue.md) 요인에 따라 우선 순위를 지정해야 하는 사고를 참조합니다. </li><li> [인시던트](manage-incidents.md)관리 워크플로에 따라 태그 및 설명을 변경, 할당, 분류 및 추가하는 인시던트 관리 를 관리합니다.</li></ol> |
| **경험** | <ol><li> 사이트 포털의 인시던트  페이지에서 인시던트 큐를 Microsoft 365 Defender. 여기에서 다음을 수행할 수 있습니다. </li> <ul><li> 심각도 및 기타 [](incident-queue.md) 요인에 따라 우선 순위를 지정해야 하는 사고를 참조합니다. </li><li> [인시던트](manage-incidents.md)관리 워크플로에 따라 태그 및 설명을 변경, 할당, 분류 및 추가하는 인시던트 관리 를 관리합니다. </li><li> [인시던트 조사를](investigate-incidents.md) 수행합니다. </li></ul> </li><li> 위협 분석을 사용하여 새로운 위협을 [추적하고 대응합니다.](threat-analytics.md) </li><li>  고급 위협 헌팅으로 위협을 사전 [예방적으로 헌팅합니다.](advanced-hunting-overview.md) </li><li> [피싱,](/security/compass/incident-response-playbooks) 암호 분사 및 앱 동의 부여 공격에 대한 자세한 지침은 다음 인시던트 대응 플레이북을 참조하세요. </li></ol> |


### <a name="security-team-role"></a>보안 팀 역할

보안 팀 역할에 따라 이 표를 따르기

| 역할 | 단계 |
|:-------|:-----|
| 인시던트 응답자(계층 1) | 사이트 포털의 인시던트  페이지에서 인시던트 큐를 Microsoft 365 Defender. 여기에서 다음을 수행할 수 있습니다. <ul><li> 심각도 및 기타 [](incident-queue.md) 요인에 따라 우선 순위를 지정해야 하는 사고를 참조합니다. </li><li> [인시던트](manage-incidents.md)관리 워크플로에 따라 태그 및 설명을 변경, 할당, 분류 및 추가하는 인시던트 관리 를 관리합니다. </li></ul> |
| 보안 조사자 또는 분석가(계층 2) | <ol><li> 사이트 [포털의](investigate-incidents.md) 인시던트 페이지에서 인시던트 Microsoft 365 Defender 수행하십시오.  </li><li> [피싱,](/security/compass/incident-response-playbooks) 암호 분사 및 앱 동의 부여 공격에 대한 자세한 지침은 다음 인시던트 대응 플레이북을 참조하세요. </li></ol> |
| 고급 보안 분석가 또는 위협 헌터(계층 3) | <ol><li>사이트 [포털의](investigate-incidents.md) 인시던트 페이지에서 인시던트 Microsoft 365 Defender 수행하십시오.  </li><li> 위협 분석을 사용하여 새로운 위협을 [추적하고 대응합니다.](threat-analytics.md) </li><li> 고급 위협 헌팅으로 위협을 사전 [예방적으로 헌팅합니다.](advanced-hunting-overview.md) </li><li> [피싱,](/security/compass/incident-response-playbooks) 암호 분사 및 앱 동의 부여 공격에 대한 자세한 지침은 다음 인시던트 대응 플레이북을 참조하세요. |
| SOC 관리자 | SOC(보안 Microsoft 365 Defender 센터)에 통합하는 방법을 [참조합니다.](integrate-microsoft-365-defender-secops.md) |

