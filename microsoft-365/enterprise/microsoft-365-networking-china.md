---
title: Microsoft 365 사용자를 위한 전역 테넌트 성능 최적화
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 전역 테넌트의 중국 사용자를 위한 네트워크 성능을 최적화하기 위한 Microsoft 365 제공합니다.
ms.openlocfilehash: 9660270dbe73e9cbdff0b1e3796224b36319956b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220816"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 사용자를 위한 전역 테넌트 성능 최적화

> [!IMPORTANT]
> 이 지침은 중국에 있는  엔터프라이즈 Microsoft 365 사용자가 전역 테넌트에 연결하는 Microsoft 365 **관련됩니다.** 이 **지침은** 21Vianet에서 운영하는 Office 365 테넌트에는 적용되지 않습니다.

글로벌 Microsoft 365 테넌트가 있는 기업의 경우Microsoft 365 중국 기반 사용자의 클라이언트 성능은 중국 텔코의 인터넷 아키텍처에 고유한 요소로 복잡할 수 있습니다.

중국 ISP는 높은 수준의 경계 네트워크 정체에 가까우는 경계 장치를 통과하는 전역 공용 인터넷에 대한 오프사이어 연결을 규제했습니다. 이 정체로 인해 중국으로 들어와서 들어와는 모든 인터넷 트래픽에 대한 패킷 손실 및 대기 시간이 생성됩니다.

![Microsoft 365 - 비개인적 트래픽.](../media/O365-networking/China-O365-unoptimized.png)

패킷 손실 및 대기 시간은 네트워크 서비스의 성능에 유해해지며, 특히 큰 데이터 교환(예: 대용량 파일 전송)이 필요하거나 거의 실시간 성능(오디오 및 비디오 응용 프로그램)이 필요한 서비스입니다.

이 항목의 목표는 중국의 국경 간 네트워크 정체가 다른 서비스에 미치는 영향을 완화하기 위한 모범 Microsoft 365 것입니다. 이 항목에서는 중국 통신 사업자 내에서의 복잡한 라우팅으로 인한 높은 패킷 대기 시간 문제와 같은 기타 일반적인 마지막 마일 성능 문제를 해결하지 않습니다.

## <a name="corporate-network-best-practices"></a>회사 네트워크 모범 사례

글로벌 Microsoft 365 테넌트와 중국의 사용자가 있는 많은 기업은 중국 사무실 위치와 전 세계 해상 위치 간의 회사 네트워크 트래픽을 전달하는 개인 네트워크를 구현했습니다. 이러한 기업은 이 네트워크 인프라를 활용하여 국경 간 네트워크 정체를 방지하고 중국의 Microsoft 365 성능을 최적화할 수 있습니다.

> [!IMPORTANT]
> 모든 전용 WAN 구현과 함께 항상 해당 국가 및/또는 지역에 대한 규정 요구 사항을 문의하여 네트워크 구성이 준수되도록 해야 합니다.

첫 번째 단계에서는 네트워크 계획 및 성능 조정에서 벤치마크 네트워크 지침을 따라야 [Microsoft 365.](./network-planning-and-performance.md) 주요 목표는 가능한 경우 중국에서 인터넷에서 Microsoft 365 전역 서비스에 액세스하지 않도록 하는 것입니다.

- 기존 사설망을 활용하여 중국의 Microsoft 365 네트워크와 중국 외부의 공용 인터넷으로 나가는 해상 위치 간의 네트워크 트래픽을 전달합니다. 중국 외부의 거의 모든 위치는 명확한 이점을 제공합니다. 네트워크 관리자는 대기 시간이 짧은 Microsoft 전역 네트워크와의 상호 연결 시간이 짧은 영역을 전송하여 최적화를 추가로 [최적화할 수 있습니다.](/azure/networking/microsoft-global-network) 홍콩, 싱가포르, 일본 및 대한민국이 예시입니다.
- VPN 연결을 통해 회사 네트워크에 액세스하도록 사용자 Microsoft 365 네트워크의 개인 오프사이트 링크를 전송할 수 있도록 사용자 장치를 구성합니다. VPN 클라이언트가 분할 터널링을 사용하도록 구성되지 않은지 또는 사용자 장치가 사용자 트래픽에 대한 분할 터널링을 Microsoft 365 합니다. 미디어 트래픽 및 실시간 미디어 Teams VPN 연결을 최적화하는 데 대한 자세한 내용은 이 섹션을 [참조하세요.](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)
- 개인 오프사이트 링크를 Microsoft 365 모든 트래픽을 라우팅하도록 네트워크를 구성합니다. 개인 링크에서 트래픽 양을 최소화해야 하는 경우 최적화 범주의 끝점만 라우팅하고 허용 및  기본  끝점에 대한 요청이 인터넷을 전송하도록 허용하도록 선택할 수 있습니다.  이렇게 하면 높은 대기 시간 및 패킷 손실에 가장 민감한 중요한 서비스로 최적화된 트래픽을 제한하여 성능을 개선하고 대역폭 소비를 최소화할 수 있습니다.
- 가능한 경우 TCP 대신 UDP를 사용하여 라이브 미디어 스트리밍 트래픽(예: 미디어 스트리밍 트래픽)을 Teams. UDP는 TCP보다 더 나은 라이브 미디어 스트리밍 성능을 제공합니다.

트래픽을 선택적으로 라우팅하는 방법에 대한 자세한 Microsoft 365 끝점 Office 365 [참조하세요.](managing-office-365-endpoints.md) 전 세계 모든 OFFICE 365 URL 및 IP 주소 목록은 Office 365 URL 및 IP 주소 범위를 [참조하세요.](urls-and-ip-address-ranges.md)

![Microsoft 365 트래픽 - 최적화됩니다.](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>사용자 모범 사례

기업 네트워크에 연결되지 않은 집, 커피숍, 커피숍 및 지점과 같은 원격 위치에서 전역 Microsoft 365 테넌트에 연결하는 중국의 사용자는 장치와 Microsoft 365 번화한 중국의 경계 네트워크 회로를 전송해야 하기 때문에 네트워크 성능이 좋지 않습니다.

경계 간 개인 네트워크 및/또는 회사 네트워크에 대한 VPN 액세스가 옵션이 아닌 경우 중국 기반 사용자에게 이러한 모범 사례를 따르는 교육을 통해 사용자당 성능 문제를 완화할 수 있습니다.

- 캐싱을 지원하는 다양한 Office 클라이언트(예: Outlook, Teams, OneDrive 등)를 활용하고 웹 기반 클라이언트를 방지합니다. Office 및 오프라인 액세스 기능을 통해 네트워크 정체 및 대기 시간의 영향을 크게 줄일 수 있습니다.
- Microsoft 365 테넌트가 오디오 회의 기능을 사용하여  구성된 경우 Teams PSTN(전화망)을 통해 모임에 참가할 수 있습니다. 자세한 내용은 에서 [오디오 회의를 Office 365.](/microsoftteams/audio-conferencing-in-office-365)
- 사용자가 네트워크 성능 문제가 발생하면 IT 부서에 문제 해결을 보고하고 서비스 문제로 의심되는 경우 Microsoft Microsoft 365 에스컬레이터해야 합니다. 경계 간 네트워크 성능으로 인해 모든 문제가 발생된 것은 아니며,

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>중국의 Microsoft Teams 모임 네트워크 성능 최적화

글로벌 Microsoft 365 테넌트가 있는 조직의 경우 Microsoft 365 사용자에 대한 클라이언트 성능은 중국 인터넷 아키텍처의 고유한 요소로 복잡할 수 있습니다. 많은 회사 및 학교에서 이 지침에 따라 좋은 결과를 보고했습니다. 그러나 범위는 IT 네트워킹 설정을 제어하는 사용자 네트워크 위치(예: VPN 연결이 있는 사무실 위치 또는 홈/모바일 끝점)로 제한됩니다. Microsoft Teams 모임은 집 사무실, 모바일 위치, 출장 중, 커피숍 등의 외부 위치에서 자주 사용됩니다. 통화 및 모임은 실시간 미디어 트래픽을 사용하기 때문에 이러한 Teams 정체에 특히 민감합니다.

따라서 Microsoft는 통신 공급자와 협력하여 Teams 및 비즈니스용 Skype Online 실시간 미디어 트래픽을 전달하기 위해 중국의 국내 및 공용 인터넷 연결과 Teams 및 Skype 글로벌 클라우드의 Teams 및 Skype 서비스를 사용하여 Microsoft 365 온라인 실시간 미디어 트래픽을 전달했습니다. 이 기능을 통해 패킷 손실 및 사용자 환경에 영향을 미치는 기타 주요 메트릭이 10배 이상 향상됩니다.

>[!IMPORTANT]
>현재 이러한 개선된 기능으로는 대규모 브로드캐스트 또는 Microsoft Stream을 사용하는 대규모 브로드캐스트 또는 "타운홀" 스타일 모임과 같은 Microsoft Live 이벤트 모임에 Teams 않습니다. 라이브 이벤트 모임을 보기 위해 중국의 사용자는 개인 네트워크 또는 SDWAN/VPN 솔루션을 사용해야 합니다. 그러나 네트워크 개선은 라이브 이벤트 모임을 발표하거나 생성하는 사용자에게 도움이 됩니다. 이 환경은 제작자 또는 발표자에 대한 정기적인 Teams 기능하기 때문에 도움이 됩니다.

### <a name="organization-network-best-practices-for-teams-meetings"></a>조직 네트워크 모임에 대한 Teams 모범 사례

경계 네트워크 정체가 없는 것을 방지하기 위해 개인 네트워크 확장을 고려하기 위한 이전 지침에 따라 이러한 네트워크 개선을 활용하는 방법을 고려해야 합니다. 조직 사무실 네트워크에는 다음과 같은 두 가지 일반적인 옵션이 있습니다.

1. 새로 추가하지 않습니다. 크로스 테두리 정체가 방지하기 위해 개인 네트워크 우회에 대한 이전 지침을 계속 따르하세요. Teams 실시간 미디어 트래픽은 이전과 같은 설정을 활용합니다.
2. 분할/하이브리드 패턴을 구현합니다.
   - 모임 및 실시간 미디어 트래픽 호출을 제외한 최적화를 위해 플래그가 Teams 모든 트래픽에 대해 이전 지침을 사용하세요.
   - 공용 Teams 실시간 미디어 트래픽을 호출하여 모임을 라우팅합니다. 실시간 미디어 네트워크 트래픽 식별에 대한 자세한 내용은 다음 정보를 참조하세요.

공용 Teams 인터넷을 통해 실시간 미디어 오디오 및 비디오 트래픽을 전송하면 높은 품질의 연결을 사용하며 개인 네트워크를 통해 해당 트래픽을 전송하는 데 무료로 비용을 지불하는 대신 비용이 절감될 수 있습니다. 사용자가 SDWAN 또는 VPN 클라이언트를 사용하는 경우 유사한 추가 이점이 있을 수 있습니다. 일부 조직에서는 일반적인 사례로 더 많은 데이터를 트래버스하는 공용 인터넷 연결을 선호할 수 있습니다.

SDWAN 또는 VPN 구성에 동일한 옵션을 적용할 수 있습니다. 예를 들어 사용자는 SDWAN 또는 VPN을 사용하여 Microsoft 365 트래픽을 회사 네트워크로 라우팅한 다음 해당 네트워크의 개인 확장을 활용하여 테두리 간 정체가 방지됩니다. 이제 사용자의 SDWAN 또는 VPN을 구성하여 VPN 라우팅에서 Teams 및 실시간 트래픽 호출을 제외할 수 있습니다. 이 VPN 구성을 분할 터널링이라고 합니다. 자세한 [내용은 OFFICE 365 VPN 분할 터널링을](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) 참조하세요.

또한 실시간 트래픽을 포함하여 모든 Microsoft 365 트래픽에 대해 SDWAN 또는 VPN을 Microsoft Teams 수 있습니다. Microsoft는 SDWAN 또는 VPN 솔루션 사용에 대한 권장 사항이 없습니다.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>모임에 대한 홈, 모바일 Teams 모범 사례

중국의 사용자는 일반 또는 모바일 연결을 통해 중국의 공용 인터넷 서비스에 연결하여 이러한 개선된 기능을 활용할 수 있습니다. Teams 및 품질 향상을 통해 공용 인터넷의 실시간 미디어 오디오 및 비디오 트래픽을 직접적으로 이점으로 사용할 수 있습니다.

그러나 다른 Microsoft 365 서비스의 데이터와 채팅 또는 파일과 같은 Teams 기타 트래픽은 이러한 개선을 통해 직접적인 혜택을 받을 수 없습니다. 조직 네트워크 외부의 사용자는 이 트래픽에 대한 네트워크 성능이 여전히 나쁨을 경험할 수 있습니다. 이 문서에서 설명한 것 처럼 VPN 또는 SDWAN을 사용하여 이러한 효과를 완화할 수 있습니다. 또한 사용자가 웹 클라이언트를 통해 다양한 데스크톱 클라이언트를 사용하게 할 수 있습니다. 이 클라이언트는 네트워크 문제를 완화하기 위해 앱에서 바로 캐싱을 지원할 수 있습니다.

### <a name="identifying-teams-real-time-media-network-traffic"></a>실시간 Teams 네트워크 트래픽 식별

네트워크 장치 또는 VPN/SDWAN 설치를 구성하려면 실시간 미디어 오디오 Teams 트래픽만 제외해야 합니다. 트래픽 세부 정보는 URL 및 IP 주소 범위의 공식 목록에서 ID [11에 Office 365 있습니다.](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams) 다른 모든 네트워크 구성은 그대로 유지해야 합니다.

Microsoft는 최대한 광범위한 네트워크 아키텍처 및 특성에 Microsoft 365 사용자 환경 및 클라이언트 성능을 개선하기 위해 지속적으로 작업하고 있습니다. Office 365 [네트워킹](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) 기술 Community 방문하여 대화를 시작하거나 참가하고, 리소스를 찾고, 기능 요청 및 제안을 제출합니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365의 네트워크 계획 및 성능 조정](./network-planning-and-performance.md)

[Microsoft 365 네트워크 연결 원칙](microsoft-365-network-connectivity-principles.md)

[Office 365 엔드포인트 관리](managing-office-365-endpoints.md)

[Office 365 URL 및 IP 주소 범위](urls-and-ip-address-ranges.md)

[Microsoft 전역 네트워크](/azure/networking/microsoft-global-network)
