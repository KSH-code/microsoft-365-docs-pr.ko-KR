---
title: Microsoft 365 네트워크 평가 (미리 보기)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 네트워크 평가 (미리 보기)
ms.openlocfilehash: 15eb514980bb53bd32380e44b6bfa174670f6b85
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948319"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 네트워크 평가 (미리 보기)

Microsoft 365 관리 센터의 Microsoft 365 페이지 연결에서 **네트워크 평가** 는 많은 네트워크 성능 메트릭 집계를 0-100의 포인트 값으로 나타내는 기업 네트워크 경계 상태의 스냅숏으로 정제 합니다. 네트워크 평가는 전체 테 넌 트와 사용자가 테 넌 트에 연결 하는 각 지리적 위치에 대해 범위가 지정 되므로 Microsoft 365 관리자는 회사의 네트워크 상태를 신속 하 게 파악 하 고 전체 사무실 위치에 대 한 자세한 보고서로 드릴 다운할 수 있는 쉬운 방법을 제공 합니다.

Network 평가 점수 값은 표시 되는 시간에 실시간으로 컴파일된 TCP 대기 시간, 다운로드 속도 및 UDP 연결 품질 메트릭에 대 한 평균 측정값입니다. Microsoft 소유의 네트워크에 대 한 성능 메트릭은 평가 결과가 모호 하 고 회사 네트워크에 한정 되도록 하기 위해 이러한 측정값에서 제외 됩니다.

![네트워크 평가 값](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

아주 낮은 네트워크 평가 값은 Microsoft 365 클라이언트에 테 넌 트에 연결 하는 중요 한 문제가 있거나 응답성이 뛰어난 사용자 환경을 유지 관리 하는 반면, 값이 높으면 성능 문제가 거의 없는 네트워크를 올바르게 구성한 것을 의미 합니다. 값이 80%는 네트워크 성능으로 인 한 Microsoft 365 연결 또는 응답성에 대 한 일반 사용자 불만을 수신 하지 않을 것으로 예상 되는 정상적인 기준을 나타냅니다. 반복적으로 네트워크 연결이 개선 됨에 따라이 값은 사용자 환경에 따라 증가 합니다.

>[!IMPORTANT]
>네트워크 insights, Microsoft 365 관리 센터의 성능 권장 사항 및 평가는 현재 미리 보기 상태 이며, 기능 미리 보기 프로그램에 등록 되어 있는 Microsoft 365 테 넌 트에만 사용할 수 있습니다.

## <a name="network-assessment-panel"></a>네트워크 평가 패널

테 넌 트 또는 특정 사무실 위치로 범위가 지정 되었는지 여부에 관계 없이 각 네트워크 평가에는 평가에 대 한 세부 정보가 포함 된 패널이 표시 됩니다. 이 패널에는 평가에 대 한 가로 막대형 차트와 측정 데이터를 받은 작업을 포함 하는 각 구성 요소 작업의 총 지점에 대 한 완료율이 표시 됩니다. Office 위치 네트워크 평가의 경우 office 위치와 같은 도시의 데이터를 보고 한 모든 Microsoft 365 클라이언트의 중앙값을 나타내는 벤치 마크가 표시 됩니다.

![네트워크 평가 값 예](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

패널의 **평가 분석** 에서는 각 구성 요소 작업에 대 한 평가를 보여 줍니다.

**평가 기록** 에는 평가 및 벤치 마크의 최근 30 일이 표시 됩니다. 기록 탭을 사용 하 여 최대 2 년 동안 office 위치의 메트릭 기록을 보고할 수도 있습니다.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>테 넌 트 네트워크 평가 및 사무실 위치 네트워크 평가

네트워크 평가는 사무실의 네트워크 경계를 Microsoft 네트워크로의 디자인을 측정 합니다. 네트워크 경계에 대 한 향상은 각 사무실 위치에서 또는 네트워크 연결이 집계 되는 위치에 있어 여러 위치에 영향을 주는 향상 된 기능을 제공 하는 것이 좋습니다.

네트워크 성능 개요 페이지에는 전체 Microsoft 365 테 넌 트에 대 한 네트워크 평가 값과 해당 위치의 요약 페이지에 있는 검색 된 각 사무실 위치에 대 한 특정 값이 표시 됩니다.

## <a name="exchange-online"></a>Exchange Online

Exchange Online의 경우 클라이언트 컴퓨터에서 Exchange 프런트 엔드 서버로의 TCP 대기 시간이 측정 됩니다. 이는 네트워크가 고객 LAN 및 WAN을 통과 하는 거리에 영향을 받을 수 있습니다. 또한 연결을 지연 시키거나 패킷을 다시 전송 하도록 하는 네트워크 매개 장치 또는 서비스의 영향을 받을 수 있습니다. 이전 3 일 동안의 모든 측정값에 대해 중앙값 (50 번째 백분위 수 또는 P50 측정값이 라고도 함)을 가져옵니다.

Exchange Online 평가는 다음 표를 사용 하 여 수행 됩니다. 임계값 사이의 TCP 대기 시간 번호는 밴드 내에서 선형으로 지정 됩니다.

| TCP 대기 시간   | 포인트 |
| :------------ | :----- |
| 10ms 또는 less  | 100    |
| 25ms          | 80     |
| 적고 100 밀리초         | 60     |
| 200ms         | 40     |
| 300ms         | 20cm(8     |
| 350ms 이상 | 개      |

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online의 경우 사용자가 SharePoint Online 또는 OneDrive에서 문서에 액세스 하는 데 사용할 수 있는 다운로드 속도가 측정 됩니다. 이는 클라이언트 컴퓨터와 Microsoft 네트워크 간의 네트워크 회로에서 사용 가능한 대역폭의 영향을 받을 수 있습니다. 또한 복잡 한 네트워크 장치에서 병목 현상이 발생 한 네트워크 혼잡 이나 적절 하지 않은 서비스 범위에 있는 경우에도 영향을 받습니다. 다운로드 속도는 초당 mb 단위로 측정 되며 약 1/10 초당 메가 비트 회로입니다. 이전 3 일 동안의 모든 측정값에 대해 25 번째 백분위 수 (P25 측정값이 라고도 함)를 가져옵니다.

다음 표를 사용 하 여 SharePoint Online 평가를 수행 합니다. 임계값 사이의 다운로드 속도 번호는 밴드 내에서 선형으로 지정 됩니다.

| 다운로드 속도 | 포인트 |
| :------------- | :----- |
| 20MBps 이상 | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20cm(8     |
| 0MBps          | 개      |

## <a name="microsoft-teams"></a>Microsoft Teams

Microsoft 팀의 경우 네트워크 품질은 UDP 대기 시간, UDP 지터 및 UDP 패킷 손실으로 측정 됩니다. UDP는 Microsoft 팀의 통화 및 회의 오디오 및 비디오 미디어 연결에 사용 됩니다. 이는 UDP가 보다 일반적인 TCP 프로토콜과 별도로 구성 되므로 네트워크의 UDP 지원에서의 연결 간격 외에도 대기 시간 및 다운로드 속도와 동일한 요인의 영향을 받을 수 있습니다. 이전 3 일 동안의 모든 측정값에 대해 중앙값 (50 번째 백분위 수 또는 P50 측정값이 라고도 함)을 가져옵니다. 

다음 표를 사용 하 여 Microsoft 팀 평가를 수행 합니다. 표시 된 점수를 얻기 위해 나열 된 임계값 보다 세 가지 UDP 측정값을 모두 포함 해야 합니다. 밴드 내의 단일 위치에 대 한 평가는 없습니다.

| UDP 패킷 손실 | UDP 대기 시간 | UDP 지터 | 포인트 |
| :-------------- | :---------- | :--------- | :----- |
| 0.25%           | 60ms        | 15ms       | 100    |
| 1.00%           | 120ms       | 40ms       | 80     |
| 1.50%           | 240ms       | 65ms       | 60     |
| 3.00%           | 275ms       | 80ms       | 40     |
| 5.00%           | 350ms       | 150ms      | 20cm(8     |
| 더 높은      | 더 높은  | 더 높은 | 개      |

## <a name="related-topics"></a>관련 항목

[Microsoft 365 관리 센터의 네트워크 성능 권장 사항 (미리 보기)](office-365-network-mac-perf-overview.md)

[Microsoft 365 network performance insights (preview)](office-365-network-mac-perf-insights.md)

[M365 관리 센터의 Microsoft 365 connectivity test (preview)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 네트워크 연결 위치 서비스 (미리 보기)](office-365-network-mac-location-services.md)
