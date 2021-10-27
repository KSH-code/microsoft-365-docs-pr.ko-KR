---
title: 2013에서 인시던트 Microsoft 365 Defender
description: 장치, 사용자 및 사서함과 관련된 인시던트 조사
keywords: 인시던트, 인시던트, 분석, 응답, 컴퓨터, 장치, 사용자, ID, 메일, 전자 메일, 사서함, 조사, 그래프, 증거
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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 9037b8f721a33f6709f3beefdac6d294c7125333
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588304"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>2013에서 인시던트 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

Microsoft 365 Defender, 사용자 및 사서함에 있는 모든 관련 경고, 자산, 조사 및 증거를 인시던트에 집계하여 공격의 전체 너비를 포괄적으로 살펴 봐야 합니다.

인시던트 내에서 네트워크에 영향을 주는 경고를 분석하고, 경고의 의미를 이해하고, 효과적인 수정 계획을 고안할 수 있도록 증거를 수집합니다.

## <a name="initial-investigation"></a>초기 조사

세부 정보를 살펴보기 전에 인시던트의 속성과 요약을 살펴보아야 합니다.

확인 표시 열에서 인시던트부터 선택할 수 있습니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="확인 표시 열에서 인시던트 선택 예제입니다.":::

이렇게 하는 경우 인시던트에 대한 주요 정보(예: 심각도, 할당된 사용자) 및 [MITRE ATT가 &trade; ](https://attack.mitre.org/) 인시던트에 대한 CK 범주를&창이 열립니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="인시던트에 대한 요약 창의 예입니다.":::

여기에서 문제 페이지 **열기 를 선택할 수 있습니다.** 그러면 경고, 장치, 사용자, 조사 및 증거에 대한 추가 요약 정보와 탭을 찾을 수 있는 인시던트의 기본 페이지가 열립니다.

인시던트 큐에서 인시던트 이름을 선택하여 인시던트의 기본 페이지를 열 수 있습니다.

## <a name="summary"></a>요약

요약 **페이지에서는** 인시던트에 대해 가장 많이 알 수 있는 스냅숏을 한눈에 알 수 있습니다.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="사이트 포털의 인시던트에 대한 요약 Microsoft 365 Defender 예":::

정보는 다음 섹션에서 구성됩니다.

| 섹션 | 설명 |
|:-------|:-----|
| 경고 및 범주 | 킬체인에 대한 공격의 진행률을 시각적 및 숫자 보기로 볼 수 있습니다. 다른 Microsoft 보안 제품과 Microsoft 365 Defender [MITRE ATT &trade; ](https://attack.mitre.org/) 및 CK&정렬됩니다. 경고 타임라인에는 경고가 발생한 시간 순서와 각 경고의 상태 및 이름이 표시됩니다. |
| 범위 |  영향을 받는 장치, 사용자 및 사서함의 수를 표시하고 위험 수준 및 조사 우선 순위에 따라 엔터티를 나열합니다. |
| 증거 | 인시던트의 영향을 받는 엔터티 수를 표시됩니다. |
| 인시던트 정보 | 태그, 상태 및 심각도와 같은 인시던트의 속성을 표시됩니다. |
|||

요약 **페이지를 사용하여 인시던트의** 상대적 중요성을 평가하고 관련 경고 및 영향을 미치는 엔터티에 빠르게 액세스합니다.

## <a name="alerts"></a>경고

경고 **탭에서** 인시던트와 관련된 경고 및 경고에 대한 기타 정보(예: )에 대한 경고 큐를 볼 수 있습니다.

- 심각도.
- 경고에 관련된 엔터티입니다.
- 경고의 원본(ID용 Microsoft Defender, 끝점용 Microsoft Defender, Microsoft Defender for Office 365).
- 함께 연결된 이유입니다.

다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="인시던트에 대한 경고 페이지의 예입니다.":::

기본적으로 경고는 시간적으로 순서가 지정되어 시간이 지날 때 공격이 어떻게 재생되는지 알 수 있습니다. 인시던트 내에서 경고를 선택하면 Microsoft 365 Defender 상황과 관련한 경고 정보가 표시됩니다. 

경고의 이벤트를 볼 수 있습니다. 이 이벤트는 다른 트리거된 경고로 인해 현재 경고가 발생하고 장치, 파일, 사용자 및 사서함을 포함하여 공격에 관련된 모든 엔터티 및 활동을 볼 수 있습니다.

다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="인시던트 내의 경고 세부 정보 페이지의 예입니다.":::

인시던트 경고 페이지에는 다음 섹션이 있습니다.

- 경고 스토리에는 다음이 포함됩니다.

   - 무슨 일이 있었나요

   - 수행한 작업

   - 관련 이벤트

- 오른쪽 창의 경고 속성(상태, 세부 정보, 설명 등)

모든 경고에 경고 스토리 섹션에 나열된 하위 섹션이 **모두 있는 것은** 아니며,

경고 조사에서 경고 큐 및 경고 페이지를 사용하는 [방법을 학습합니다.](investigate-alerts.md)

## <a name="devices"></a>디바이스

장치 **탭에는** 인시던트와 관련된 모든 장치가 나열됩니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="인시던트에 대한 장치 페이지의 예입니다.":::

장치의 확인 표시를 선택하여 장치, 디렉터리 데이터, 활성 경고 및 로그온한 사용자의 세부 정보를 볼 수 있습니다. Microsoft Defender for Endpoints 장치 인벤토리에서 장치 세부 정보를 확인하려면 장치의 이름을 선택합니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="끝점용 Microsoft Defender에 대한 장치 페이지의 예":::

디바이스 페이지에서 모든 경고, 타임라인 및 보안 권장 사항과 같은 장치에 대한 추가 정보를 수집할 수 있습니다. 예를 들어 시간  표시 막대 탭에서 컴퓨터 타임라인을 스크롤하여 컴퓨터에서 관찰된 모든 이벤트와 동작을 시간 순서대로 볼 수 있으며, 경고가 발생했습니다.

> [!TIP]
> 디바이스 페이지에서는 필요한 경우 검색을 할 수 있습니다. in the Microsoft 365 Defender portal, choose **Endpoints > Device inventory**. 경고가 있는 장치를 선택한 다음 바이러스 백신 검색을 실행합니다. 바이러스 백신 검사와 같은 작업은 추적되어 장치 인벤토리 **페이지에** 표시됩니다. 자세한 내용은 장치에서 Microsoft Defender 바이러스 백신 [실행을 참조합니다.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)

## <a name="users"></a>사용자

사용자 **탭에는** 인시던트의 일부로 식별되거나 인시던트와 관련된 것으로 식별된 모든 사용자가 나열됩니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="인시던트에 대한 사용자 페이지의 예입니다.":::

사용자의 확인 표시를 선택하여 사용자 계정 위협, 노출 및 연락처 정보에 대한 세부 정보를 볼 수 있습니다. 사용자 이름을 선택하여 추가 사용자 계정 세부 정보를 볼 수 있습니다.

사용자 조사에서 추가 사용자 정보를 보고 인시던트의 사용자를 관리하는 [방법을 학습합니다.](investigate-users.md)


## <a name="mailboxes"></a>사서함

사서함 **탭에는** 인시던트의 일부로 식별되거나 인시던트와 관련이 있는 것으로 확인된 모든 사서함이 나열됩니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="인시던트에 대한 사서함 페이지의 예입니다.":::

사서함의 확인 표시를 선택하여 활성 경고 목록을 볼 수 있습니다. 사서함 이름을 선택하여 Microsoft Defender for Office 365.

## <a name="investigations"></a>조사

조사 **탭에는** 이 인시던트의 경고에 의해 트리거된 모든 자동화된 조사가 나열됩니다. [](m365d-autoir.md) 자동화된 조사는 Microsoft Defender for Endpoint 및 Defender for Office 365.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="인시던트에 대한 조사 페이지의 예":::

조사를 선택하여 조사 및 수정 상태에 대한 전체 정보를 확인하려면 세부 정보 페이지로 이동합니다. 조사의 일부로 승인 보류 중인 작업이 있는 경우 보류 중인 작업 기록 **탭에** 표시됩니다. 인시던트 수정의 일부로 조치를 취합니다.

조사 그래프 **탭에는** 또한 표시 하는:

- 조직의 영향을 미치는 자산에 대한 경고 연결
- 경고와 관련된 엔터티 및 해당 경고가 공격에 대한 스토리의 일부인 방식
- 인시던트에 대한 경고입니다.

조사 그래프를 통해 공격의 일부인 여러 의심스러운 엔터티를 사용자, 장치 및 사서함과 같은 관련 자산에 연결하여 공격의 전체 범위를 빠르게 이해할 수 있습니다. 

자세한 내용은 에서 자동화된 조사 [및 응답을 Microsoft 365 Defender.](m365d-autoir.md)

## <a name="evidence-and-response"></a>증거 및 응답

증거 **및 응답 탭에는** 인시던트의 경고에서 지원되는 모든 이벤트와 의심스러운 엔터티가 표시됩니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="인시던트에 대한 증거 및 응답 페이지의 예":::

Microsoft 365 Defender 모든 인시던트 지원 이벤트 및 의심스러운 엔터티를 경고에서 자동으로 조사하여 중요한 전자 메일, 파일, 프로세스, 서비스, IP 주소에 대한 정보를 제공합니다. 이렇게 하면 인시던트의 잠재적인 위협을 빠르게 감지하고 차단할 수 있습니다.

분석된 각 엔터티는 판정(악성, 의심스러운, 정리)과 수정 상태로 표시됩니다. 이렇게 하면 전체 인시던트의 수정 상태와 다음 단계를 이해하는 데 도움이 됩니다.

## <a name="graph-preview"></a>Graph(미리 보기)

Graph  탭에는 공격의 전체 범위, 공격이 시간의에 따라 네트워크를 통해 확산되는 방식, 공격이 시작된 위치 및 공격자가 얼마나 갔는가가 표시됩니다. 공격의 일부인 여러 의심스러운 엔터티를 사용자, 장치 및 사서함과 같은 관련 자산과 연결합니다. 

Graph **탭에서** 다음을 할 수 있습니다.

1. 경고 및 노드가 시간이 지날 때 발생한 경고 및 노드를 재생하여 공격의 연대론을 이해합니다.


   :::image type="content" source="../../media/investigate-incidents/incident-graph-play.gif" alt-text="Graph 페이지의 경고 및 노드 재생 예":::
 

2. 엔터티 창을 열고 엔터티 세부 정보를 검토하고 파일 삭제 또는 장치 독립과 같은 수정 작업을 수행할 수 있습니다.
 
   :::image type="content" source="../../media/investigate-incidents/incident-graph-entity-pane.png" alt-text="웹 페이지의 엔터티 창 Graph 예":::

3. 관련된 엔터티에 따라 경고를 강조합니다.
 
   :::image type="content" source="../../media/investigate-incidents/incident-graph-alert.png" alt-text="알림 페이지의 경고 강조 Graph 예":::

## <a name="next-steps"></a>다음 단계

필요한 경우:

- [인시던트 경고 조사](investigate-alerts.md)
- [인시던트 사용자 조사](investigate-users.md)

## <a name="see-also"></a>참고 항목

- [인시던트 개요](incidents-overview.md)
- [인시던트 우선 순위 지정](incident-queue.md)
- [인시던트 관리](manage-incidents.md)

