---
title: Microsoft 365 네트워크 평가(미리 보기)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 네트워크 평가(미리 보기)
ms.openlocfilehash: 3d80130dbf9ca41342bc1a01fe3ce992303efb48
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200750"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 네트워크 평가(미리 보기)

Microsoft 365 관리 센터의 네트워크 연결에서 **네트워크** 평가는 많은 네트워크 성능 메트릭의 집계를 엔터프라이즈 네트워크 경계 상태의 스냅숏으로 나타내며, 0에서 100까지의 포인트 값으로 표시됩니다. 네트워크 평가는 고객 책임 네트워크 디자인이 Office 365 사용자 환경에 얼마나 영향을 미치는지 알 수 있습니다. 네트워크 평가는 전체 테넌트와 사용자가 테넌트에 연결하는 각 지리적 위치에 대해 범위가 지정되어 Microsoft 365 관리자에게 엔터프라이즈의 네트워크 상태 정보를 즉시 파악하고 모든 전역 사무실 위치에 대한 자세한 보고서로 빠르게 드릴다운할 수 있는 간편한 방법을 제공합니다.

네트워크 평가점 값은 하루 한 번 컴파일된 TCP 대기 시간, 다운로드 속도 및 UDP 연결 품질 메트릭의 평균입니다. Microsoft 소유 네트워크의 성능 메트릭은 평가 결과가 모호하고 회사 네트워크와 관련이 있도록 이러한 측정에서 제외됩니다.

![네트워크 평가 값](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

네트워크 평가 값이 매우 낮으면 Microsoft 365 클라이언트가 테넌트에 연결하거나 반응형 사용자 환경을 유지 관리하는 데 중요한 문제가 있는 반면, 값이 높으면 몇 가지 지속적인 성능 문제가 있는 제대로 구성된 네트워크를 나타냅니다. 값 80%는 네트워크 성능으로 인해 Microsoft 365 연결 또는 응답성에 대한 정기적인 사용자 불만을 받지 않을 것으로 예상되는 정상 기준을 나타났습니다. 이처럼 네트워크 연결이 개선될수록 사용자 환경과 함께 이 값이 커지게 됩니다.

| 네트워크 평가 | 예상 사용자 환경 |
| :----------------- | :----------------------- |
| 100                | 최상의 선택                     |
| 80                 | 권장 사항 충족    |
| 60                 | 용인되는               |
| 40                 | 사용자에게 문제가 있을 수 있습니다. |
| 20                 | 사용자가 불만을 할 수 있습니다.       |
| 0                  | 네트워크 문제의 일반적인 토론 항목 |

>[!IMPORTANT]
>Microsoft 365 관리 센터의 네트워크 정보, 성능 권장 사항 및 평가는 현재 미리 보기 상태입니다. 기능 미리 보기 프로그램에 등록된 Microsoft 365 테넌트에만 사용할 수 있습니다.

## <a name="network-assessment-panel"></a>네트워크 평가 패널

테넌트 또는 특정 사무실 위치로 범위가 지정되거나 각 네트워크 평가에는 평가에 대한 세부 정보가 있는 패널이 표시됩니다. 이 패널은 측정 데이터를 받은 워크로드만 포함하여 각 구성 요소 작업의 총점 및 백분율로 평가의 막대형 차트를 보여 주며, 사무실 위치 네트워크 평가를 위해 사무실 위치와 같은 도시에 있는 데이터를 보고한 5개의 각 결과에서 Microsoft 365 고객의 백분율을 비교합니다.

![네트워크 평가 값 예제](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

패널의 평가 **분석에는** 각 구성 요소 워크로드에 대한 평가가 표시됩니다.

평가 **기록에는** 지난 30일 동안의 평가 및 벤치마크가 표시될 수 있습니다. 기록 탭을 사용하여 최대 2년 동안 모든 사무실 위치의 메트릭 기록을 보고할 수도 있습니다. 기록 탭을 사용하면 보고할 특성을 선택하고 보고서 기간을 선택하여 네트워크 업데이트 프로젝트의 영향을 강조 표시하고 네트워크 평가 개선을 볼 수 있습니다.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>테넌트 네트워크 평가 및 사무실 위치 네트워크 평가

네트워크 평가는 사무실 위치의 네트워크 경계 디자인을 Microsoft 네트워크로 측정합니다. 네트워크 경계 개선은 각 사무실 위치에서 가장 잘 수행됩니다.

전체 Microsoft 365 테넌트에 대한 네트워크 평가 값은 모든 사무실 위치에 대한 네트워크 평가의 가중 평균인 네트워크 성능 개요 페이지에 표시됩니다. 해당 위치의 요약 페이지에 검색된 각 사무실 위치에 대한 특정 네트워크 평가 값도 있습니다.

## <a name="exchange-online"></a>Exchange Online

Exchange Online의 경우 클라이언트 컴퓨터로부터 Exchange 서비스 프런트 도어로의 TCP 대기 시간이 측정됩니다. 이는 네트워크가 고객 LAN 및 WAN을 통해 이동하는 거리의 영향을 미칠 수 있습니다. 또한 연결이 지연되거나 패킷이 다시 전송되는 네트워크 중간 장치 또는 서비스의 영향을 을 수 있습니다. 가장 가까운 Exchange 서비스 프런트 도어가 얼마나 멀리 있는지 영향을 미치게 됩니다. 50번째 백분위수 또는 P50 측정값으로도 알려진 중위값은 지난 3일 동안의 모든 측정값에 대해 측정됩니다.

Exchange Online 평가는 다음 표를 사용하여 수행됩니다. 임계값 간의 모든 TCP 대기 시간 번호에는 대역 내에서 선형으로 포인트가 할당됩니다.

| TCP 대기 시간   | 포인트 |
| :------------ | :----- |
| 10ms 이하  | 100    |
| 25ms          | 80     |
| 100ms         | 60     |
| 200ms         | 40     |
| 300ms         | 20     |
| 350ms 이상 | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online의 경우 사용자가 SharePoint 또는 OneDrive에서 문서에 액세스하는 데 사용할 수 있는 다운로드 속도가 측정됩니다. 이 대역폭은 클라이언트 컴퓨터와 Microsoft 네트워크 간의 네트워크 회로에서 사용할 수 있는 대역폭의 영향을 미칠 수 있습니다. 또한 복잡한 네트워크 장치의 병목 현상이나 낮은 범위의 서비스 영역에서 병목 현상이 있는 네트워크 정체 Wi-Fi 있습니다. 다운로드 속도는 초당 메가비트 등급 회로의 약 10분의 1에 달하는 초당 메가바이트 단위로 측정됩니다. 초당 MegaByte 단위는 1초에 다운로드할 수 있는 크기 파일을 직접 볼 수 있기 때문에 유용합니다. 25번째 백분위수(P25 측정값)는 지난 3일 동안의 모든 측정에 대해 수행됩니다. 이 25번째 백분위수는 시간 경과에 따라 다양한 정체의 영향을 줄이는 데 도움이 됩니다.

SharePoint Online 평가는 다음 표를 사용하여 수행됩니다. 임계값 간의 모든 다운로드 속도 번호에는 대역 내에서 선형으로 포인트가 할당됩니다.

| 다운로드 속도 | 포인트 |
| :------------- | :----- |
| 20MBps 이상 | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Microsoft Teams의 경우 네트워크 품질은 UDP 대기 시간, UDP 지터 및 UDP 패킷 손실로 측정됩니다. UDP는 Microsoft Teams의 통화 및 회의 오디오 및 비디오 미디어 연결에 사용됩니다. UDP가 보다 일반적인 TCP 프로토콜에 별도로 구성되어 네트워크의 UDP 지원에서 연결 간격과 대기 시간 및 다운로드 속도와 동일한 요인에 의해 영향을 줄 수 있습니다. 50번째 백분위수 또는 P50 측정값으로도 알려진 중위값은 지난 3일 동안의 모든 측정값에 대해 측정됩니다. 

이러한 UDP 측정값에서 1에서 5까지의 배율에 대한 평균 점수를 계산합니다. 그런 다음 Microsoft Teams 네트워크 평가를 위해 0~100포인트 배율에 매핑합니다.  전반적으로 양호한 점은 87.5포인트를 넘고 전반적인 불량은 50포인트 미만입니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 관리 센터의 네트워크 연결(미리 보기)](office-365-network-mac-perf-overview.md)

[Microsoft 365 네트워크 성능 인사이트(미리 보기)](office-365-network-mac-perf-insights.md)

[Microsoft 365 네트워크 연결 테스트 도구(미리 보기)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services(미리 보기)](office-365-network-mac-location-services.md)
