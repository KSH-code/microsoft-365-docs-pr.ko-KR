---
title: 중국 사용자를 위한 Microsoft 365 전역 테넌트 성능 최적화
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
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
description: 이 문서에서는 글로벌 Microsoft 365 테넌트의 중국 사용자를 위한 네트워크 성능을 최적화하기 위한 지침을 제공합니다.
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923197"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>중국 사용자를 위한 Microsoft 365 전역 테넌트 성능 최적화

>[!IMPORTANT]
>이 지침은 중국에 있는 엔터프라이즈 Microsoft 365 사용자가 전역 **Microsoft 365** 테넌트에 연결하는 사용 **시나리오와 관련이 있습니다.** 이 **지침은** 21Vianet에서 운영하는 Office 365의 테넌트에는 적용되지 않습니다.

글로벌 Microsoft 365 테넌트가 있는 기업의 경우 중국 기반 사용자에 대한 Microsoft 365 클라이언트 성능은 중국 텔코의 인터넷 아키텍처에 고유한 요인으로 복잡할 수 있습니다.

중국 ISP는 경계 네트워크 정체가 높은 경계 장치를 통과하는 전역 공용 인터넷에 대한 오프사이어 연결을 규제했습니다. 이 정체로 인해 중국으로 들어와서 들어와는 모든 인터넷 트래픽에 대한 패킷 손실 및 대기 시간이 생성됩니다.

![Microsoft 365 트래픽 - 미개인](../media/O365-networking/China-O365-unoptimized.png)

패킷 손실 및 대기 시간은 네트워크 서비스의 성능에 유해해지며, 특히 대용량 파일 전송과 같은 대규모 데이터 교환이 필요하거나 거의 실시간 성능(오디오 및 비디오 응용 프로그램)이 필요한 서비스입니다.

이 항목의 목표는 중국의 국경 간 네트워크 정체가 Microsoft 365 서비스에 미치는 영향을 완화하기 위한 모범 사례를 제공하는 것입니다. 이 항목에서는 중국 통신 사업자 내에서의 복잡한 라우팅으로 인한 높은 패킷 대기 시간 문제와 같은 기타 일반적인 마지막 마일 성능 문제를 해결하지 않습니다.

## <a name="corporate-network-best-practices"></a>회사 네트워크 모범 사례

글로벌 Microsoft 365 테넌트 및 중국의 사용자가 있는 많은 기업은 중국 사무실 위치와 전 세계 해상 위치 간의 회사 네트워크 트래픽을 전달하는 개인 네트워크를 구현했습니다. 이러한 기업은 이 네트워크 인프라를 활용하여 국경 간 네트워크 정체를 방지하고 중국에서 Microsoft 365 서비스 성능을 최적화할 수 있습니다.

>[!IMPORTANT]
>모든 전용 WAN 구현과 함께 항상 해당 국가 및/또는 지역에 대한 규정 요구 사항을 문의하여 네트워크 구성이 준수되도록 해야 합니다.

첫 번째 단계에서는 [Microsoft 365에](./network-planning-and-performance.md)대한 네트워크 계획 및 성능 조정의 벤치마크 네트워크 지침을 따라야 합니다. 기본 목표는 가능한 경우 중국의 인터넷에서 전역 Microsoft 365 서비스에 액세스하지 않도록 하는 것입니다.

- 기존 개인 네트워크를 활용하여 중국 사무실 네트워크와 중국 외부의 공용 인터넷을 통해 나가는 오프소어 위치 간의 Microsoft 365 네트워크 트래픽을 전달합니다. 중국 외부의 거의 모든 위치는 명확한 이점을 제공합니다. 네트워크 관리자는 대기 시간이 짧은 Microsoft 전역 네트워크와의 상호 연결 시간이 짧은 영역을 전송하여 최적화를 추가로 [최적화할 수 있습니다.](/azure/networking/microsoft-global-network) 홍콩, 일본 및 대한민국은 예시입니다.
- Microsoft 365 트래픽이 회사 네트워크의 개인 오프소어 링크를 전송할 수 있도록 VPN 연결을 통해 회사 네트워크에 액세스하도록 사용자 장치를 구성합니다. VPN 클라이언트가 분할 터널링을 사용하도록 구성되지 않은지 또는 사용자 장치가 Microsoft 365 트래픽에 대한 분할 터널링을 무시하도록 구성되어 있는지 확인
- 개인 오프사이트 링크를 통해 모든 Microsoft 365 트래픽을 라우팅하도록 네트워크를 구성합니다. 개인 링크에서 트래픽 양을 최소화해야 하는 경우 최적화 범주의 끝점만 라우팅하고 허용 및  기본  끝점에 대한 요청이 인터넷을 전송하도록 허용하도록 선택할 수 있습니다.  이렇게 하면 높은 대기 시간 및 패킷 손실에 가장 민감한 중요한 서비스로 최적화된 트래픽을 제한하여 성능을 개선하고 대역폭 소비를 최소화할 수 있습니다.
- 가능한 경우 Teams와 같은 라이브 미디어 스트리밍 트래픽에 TCP 대신 UDP를 사용합니다. UDP는 TCP보다 더 나은 라이브 미디어 스트리밍 성능을 제공합니다.

Microsoft 365 트래픽을 선택적으로 라우팅하는 방법에 대한 자세한 내용은 [Office 365](managing-office-365-endpoints.md)끝점 관리를 참조하세요. 전 세계 모든 Office 365 URL 및 IP 주소 목록은 [Office 365 URL](urls-and-ip-address-ranges.md)및 IP 주소 범위를 참조하세요.

![Microsoft 365 트래픽 - 최적화](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>사용자 모범 사례

가정, 커피숍, 커피숍 및 지사와 같은 원격 위치에서 전역 Microsoft 365 테넌트에 연결하는 중국의 사용자는 장치와 Microsoft 365 간의 트래픽이 중국의 정체된 국경 간 네트워크 회로를 전송해야 하기 때문에 네트워크 성능이 좋지 않은 성능을 경험할 수 있습니다.

경계 간 개인 네트워크 및/또는 회사 네트워크에 대한 VPN 액세스가 옵션이 아닌 경우 중국 기반 사용자에게 이러한 모범 사례를 따르는 교육을 통해 사용자당 성능 문제를 완화할 수 있습니다.

- 캐싱을 지원하는 다양한 Office 클라이언트(예: Outlook, Teams, OneDrive 등)를 활용하고 웹 기반 클라이언트를 방지합니다. Office 클라이언트 캐싱 및 오프라인 액세스 기능은 네트워크 정체 및 대기 시간의 영향을 크게 줄일 수 있습니다.
- Microsoft 365 테넌트가 오디오 회의  기능을 사용하여 구성된 경우 Teams 사용자는 PSTN(Public Switched Telephone Network)을 통해 모임에 참가할 수 있습니다. 자세한 내용은 [Office 365의 오디오 회의를 참조하세요.](/microsoftteams/audio-conferencing-in-office-365)
- 사용자가 네트워크 성능 문제가 발생하면 IT 부서에 문제 해결을 보고하고 Microsoft 365 서비스에 문제가 있는 것으로 의심되는 경우 Microsoft 지원으로 에스컬레이터해야 합니다. 경계 간 네트워크 성능으로 인해 모든 문제가 발생된 것은 아니며,

Microsoft는 최대한 광범위한 네트워크 아키텍처 및 특성을 통해 Microsoft 365 사용자 환경 및 클라이언트 성능을 개선하기 위해 지속적으로 작업하고 있습니다. Office [365 기술](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) 커뮤니티를 방문하여 대화를 시작하거나 참가하고, 리소스를 찾고, 기능 요청 및 제안을 제출합니다.

## <a name="related-topics"></a>관련 주제

[Microsoft 365의 네트워크 계획 및 성능 조정](./network-planning-and-performance.md)

[Microsoft 365 네트워크 연결 원칙](microsoft-365-network-connectivity-principles.md)

[Office 365 엔드포인트 관리](managing-office-365-endpoints.md)

[Office 365 URL 및 IP 주소 범위](urls-and-ip-address-ranges.md)

[Microsoft 전역 네트워크](/azure/networking/microsoft-global-network)