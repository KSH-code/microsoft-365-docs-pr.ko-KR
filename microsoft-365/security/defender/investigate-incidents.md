---
title: Defender에서 인시던트 Microsoft 365 조사
description: 장치, 사용자 및 사서함과 관련된 인시던트 조사
keywords: 인시던트, 인시던트, 분석, 응답, 컴퓨터, 장치, 사용자, ID, 메일, 전자 메일, 사서함, 조사, 그래프, 증거
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
ms.openlocfilehash: 865aa9dc34a91be251d6f7772da5cc686f9641a4
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651319"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Defender에서 인시던트 Microsoft 365 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

Microsoft 365 Defender는 장치, 사용자 및 사서함에서 모든 관련 경고, 자산, 조사 및 증거를 인시던트에 집계하여 공격의 전체 너비를 포괄적으로 살펴 봐야 합니다.

인시던트 내에서 네트워크에 영향을 주는 경고를 분석하고, 경고의 의미를 이해하고, 효과적인 수정 계획을 고안할 수 있도록 증거를 수집합니다.

## <a name="initial-investigation"></a>초기 조사

세부 정보를 살펴보기 전에 인시던트의 속성과 요약을 살펴보아야 합니다.

확인 표시 열에서 인시던트부터 선택할 수 있습니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="확인 표시 열에서 인시던트 선택 예제":::

이렇게 하는 경우 인시던트에 대한 주요 정보(예: 심각도, 할당된 사용자) 및 [MITRE ATT가 &trade; ](https://attack.mitre.org/) 인시던트에 대한 CK 범주를&창이 열립니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="인시던트에 대한 요약 창의 예":::

여기에서 문제 페이지 **열기 를 선택할 수 있습니다.** 그러면 경고, 장치, 사용자, 조사 및 증거에 대한 추가 요약 정보와 탭을 찾을 수 있는 인시던트의 기본 페이지가 열립니다.

인시던트 큐에서 인시던트 이름을 선택하여 인시던트의 기본 페이지를 열 수 있습니다.

## <a name="summary"></a>요약

요약 **페이지에서는** 인시던트에 대해 가장 많이 알 수 있는 스냅숏을 한눈에 알 수 있습니다.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="보안 센터의 인시던트에 대한 요약 Microsoft 365 예":::

공격 범주는 킬체인에 대해 공격이 진행된 상황을 시각적 및 숫자로 볼 수 있도록 합니다. 다른 Microsoft 보안 제품과 Microsoft 365 Defender는 [MITRE ATT &trade; ](https://attack.mitre.org/) 및 CK&정렬됩니다.

범위 섹션에서는 이 인시던트의 일부인 영향을 받는 상위 자산 목록을 제공합니다. 위험 수준, 조사 우선 순위 및 자산에 대한 태그 지정과 같은 해당 자산에 관한 특정 정보가 있는 경우 이 섹션에도 표시됩니다.

경고 타임라인은 경고가 발생한 시간 순서와 이러한 경고가 이 인시던트와 연결되는 이유에 대해 살피는 기능을 제공합니다.

마지막 - 증거 섹션에서는 인시던트에 포함된 다양한 아티팩트 수와 수정 상태에 대한 요약을 제공 하여 사용자가 조치가 필요한지 즉시 확인할 수 있습니다.

이 개요는 파악해야 하는 인시던트의 주요 특징에 대한 정보를 제공하여 인시던트의 초기 조사를 지원할 수 있습니다.

## <a name="alerts"></a>경고

경고 **탭에서** 인시던트와 관련된 경고 및 경고에 대한 기타 정보(예: )에 대한 경고 큐를 볼 수 있습니다.

- 심각도.
- 경고에 관련된 엔터티입니다.
- 경고의 원본(ID용 Microsoft Defender, 끝점용 Microsoft Defender, Microsoft Defender for Office 365).
- 함께 연결된 이유입니다.

다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="인시던트에 대한 경고 페이지 예":::

기본적으로 경고는 시간이 지날 때 인시던트가 어떻게 재생되는지 볼 수 있도록 시간 순서대로 지정됩니다. 인시던트 내에서 경고를 선택하면 Microsoft 365 상황과 관련한 경고 정보가 표시됩니다. 

경고의 이벤트, 즉 다른 트리거된 경고로 인해 현재 경고가 발생하고 파일, 사용자 및 사서함을 포함하여 공격에 관련된 모든 엔터티 및 활동을 볼 수 있습니다.

다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="인시던트 내의 경고 세부 정보 페이지 예":::

이 인시던트 경고 페이지는 다음 섹션으로 구성됩니다.

- 경고 스토리 - 발생된 일에 대한 요약을 포함합니다.
- 관련 이벤트 및 경고
- 요약 세부 정보

경고 조사에서 경고 큐 및 경고 페이지를 사용하는 [방법을 학습합니다.](investigate-alerts.md)

## <a name="devices"></a>디바이스

장치 **탭에는** 인시던트와 관련된 모든 장치가 나열됩니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="인시던트에 대한 장치 페이지의 예":::

장치의 확인 표시를 선택하여 장치, 디렉터리 데이터, 활성 경고 및 로그온한 사용자의 세부 정보를 볼 수 있습니다. Microsoft Defender for Endpoints 장치 인벤토리에서 장치 세부 정보를 확인하려면 장치의 이름을 선택합니다.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="끝점용 Microsoft Defender의 장치 페이지 예":::

디바이스 페이지에서 모든 경고, 타임라인 및 보안 권장 사항과 같은 장치에 대한 추가 정보를 수집할 수 있습니다. 예를 들어 시간  표시 막대 탭에서 컴퓨터 타임라인을 스크롤하여 컴퓨터에서 관찰된 모든 이벤트와 동작을 시간 순서대로 볼 수 있으며, 경고가 발생했습니다.

> [!TIP]
> 디바이스 페이지에서는 필요한 경우 검색을 할 수 있습니다. In the Microsoft 365 security center, choose **Endpoints > Device inventory**. 경고가 있는 장치를 선택한 다음 바이러스 백신 검색을 실행합니다. 바이러스 백신 검사와 같은 작업은 추적되어 장치 인벤토리 **페이지에** 표시됩니다. 자세한 내용은 장치에서 Microsoft Defender 바이러스 백신 [실행을 참조합니다.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)

## <a name="users"></a>사용자

사용자 **탭에는** 인시던트의 일부로 식별되거나 인시던트와 관련된 것으로 식별된 모든 사용자가 나열됩니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="인시던트에 대한 사용자 페이지의 예":::

사용자의 확인 표시를 선택하여 사용자 계정 위협, 노출 및 연락처 정보에 대한 세부 정보를 볼 수 있습니다. 사용자 이름을 선택하여 추가 사용자 계정 세부 정보를 볼 수 있습니다.

사용자 조사에서 추가 사용자 정보를 보고 인시던트의 사용자를 관리하는 [방법을 학습합니다.](investigate-users.md)


## <a name="mailboxes"></a>사서함

사서함 **탭에는** 인시던트의 일부로 식별되거나 인시던트와 관련이 있는 것으로 확인된 모든 사서함이 나열됩니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="인시던트에 대한 사서함 페이지의 예":::

사서함의 확인 표시를 선택하여 활성 경고 목록을 볼 수 있습니다. 사서함 이름을 선택하여 Microsoft Defender for Office 365.

## <a name="investigations"></a>조사

조사 **탭에는** 이 인시던트의 경고에 의해 트리거된 모든 자동화된 조사가 나열됩니다. [](m365d-autoir.md) 조사는 Microsoft Defender for Endpoint 및 Defender for Office 365에서 자동화된 조사를 실행하도록 구성한 방법에 따라 수정 작업을 수행하거나 분석가의 작업 승인을 Office 365.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="인시던트에 대한 조사 페이지의 예":::

조사를 선택하여 조사 세부 사항 페이지로 이동하고 조사 및 수정 상태에 대한 전체 정보를 확인하세요. 조사의 일부로 승인 보류 중인 작업이 있는 경우 보류 중인 작업 탭에 표시됩니다. 인시던트 수정의 일부로 조치를 취합니다.

자세한 내용은 Defender의 자동화된 조사 [및 Microsoft 365 참조하세요.](m365d-autoir.md)

## <a name="evidence-and-response"></a>증거 및 응답

증거 **및 응답 탭에는** 인시던트의 경고에서 지원되는 모든 이벤트와 의심스러운 엔터티가 표시됩니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="인시던트에 대한 증거 및 응답 페이지의 예":::

Microsoft 365 Defender는 경고에서 모든 인시던트 지원 이벤트 및 의심스러운 엔터티를 자동으로 조사하여 중요한 전자 메일, 파일, 프로세스, 서비스, IP 주소에 대한 정보를 제공합니다. 이렇게 하면 인시던트의 잠재적인 위협을 빠르게 감지하고 차단할 수 있습니다.

분석된 각 엔터티는 판정(악성, 의심스러운, 정리)과 수정 상태로 표시됩니다. 이렇게 하면 전체 인시던트의 수정 상태와 다음 단계를 이해하는 데 도움이 됩니다.

## <a name="graph-in-preview"></a>Graph(미리 보기)

새 **Graph** 탭(미리 보기)을 사용하면 다음을 볼 수 있습니다.

- 조직의 영향을 미치는 자산에 대한 경고 연결
- 경고와 관련된 엔터티 및 해당 경고가 공격에 대한 스토리의 일부인 방식
- 인시던트에 대한 경고입니다.

다음은 예입니다.

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="인시던트에 대한 Graph 페이지의 예":::

인시던트 그래프를 사용하면 공격의 일부인 여러 의심스러운 엔터티를 사용자, 장치 및 사서함과 같은 관련 자산에 연결하여 공격의 전체 범위를 빠르게 이해할 수 있습니다. 

이제 시간이 지날 때 네트워크를 통해 공격이 확산되는 방식, 공격이 시작된 위치 및 공격이 얼마나 진행된지 이해할 수 있습니다.

## <a name="next-steps"></a>다음 단계

필요한 경우:

- [인시던트 경고 조사](investigate-alerts.md)
- [인시던트 사용자 조사](investigate-users.md)

## <a name="see-also"></a>참고 항목

- [인시던트 개요](incidents-overview.md)
- [인시던트 우선 순위 지정](incident-queue.md)
- [인시던트 관리](manage-incidents.md)

