---
title: 네트워킹 업 (클라우드)-설계자의 관점 1 개
description: 설명이.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: c8b8416b276ce0e5335b0c0193c6cd79a81d7959
ms.sourcegitcommit: a418195dc11e6251ae37e788c102bbaa7087e44e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44581593"
---
# <a name="networking-up-to-the-cloud--one-architects-viewpoint"></a>네트워킹 업 (클라우드)-설계자의 관점 1 개

이 문서에서 Microsoft의 [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & 준수 설계자는 가장 일반적인 문제를 방지 하 여 클라우드 연결용으로 네트워크를 최적화 하는 방법에 대해 설명 합니다. 

## <a name="about-the-author"></a>만든 이 정보

![Ed Fisher photo](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

현재는 보안 & 준수에 초점을 맞추어 동남 지역의 주 기술 전문가입니다. 지난 10 년 동안 Office 365로 전환 하는 고객에 게 작업 했습니다. 필자는 수백만 명의 사용자, 전세계 다양 한 지역의 여러 위치, 높은 수준의 보안, 그리고 수많은 준수 요구 사항을 사용 하 여 전 세계의 수많은 사용자가 포함 된 정부 기관 및 기업을 대상으로 하는 소규모 상점을 잘 사용 하 고 있습니다. 수백 대의 기업에서 수백만 명의 사용자가 클라우드로 안전 하 고 안전 하 게 이동 하는 데 도움이 되었습니다.

지난 25 년 동안 보안, 인프라 및 네트워크 엔지니어링이 포함 되 고 이전 employers 중 두 가지를 Office 365으로 이동 하 여 Microsoft에 참여 한 적이 있으면 테이블의 측면에는 많은 시간이 있었으며, 어떤 일이 든 지 기억이 들지 않습니다. 두 명의 고객이 동일 하 게 존재 하는 것은 같지만, 요구 사항이 가장 많고, 모든 SaaS 또는 PaaS 플랫폼과 같은 표준화 된 서비스를 사용 하는 경우에는 가장 좋은 방법은 동일 합니다.



## <a name="its-not-the-network--its-how-youre-misusing-it"></a>네트워크를 사용 하는 것이 아닙니다.

발생 횟수에 관계 없이,이를 통해 *독창적인* 보안 팀 및 네트워킹 팀이 Microsoft 클라우드 서비스에 연결 하는 것으로 생각 하는 방법을 amaze 수 있습니다. 사용자가 수행 하려는 작업에 대 한 정보를 대화에 참여 하거나, 보다 빠르고 간편 하 게 작업을 수행 하 고 비용 효율적 이며, 보다 나은 성능을 높일 수 있는 *방법을* 제공 하지 않고 사용을 위해 보안 정책, 준수 표준 또는 보다 나은 방법을 제공 합니다. 

이러한 종류의 내용이 사용자에 게 전달 되 면 일반적으로 문제를 해결 하 고 whys를 사용 하 여 필요한 위치로 가져올 수 있습니다. 그러나 완벽 하 게 frank 경우에는 이러한 작업을 수행 하는 것이 좋을 수도 있는데, 마지막으로 concede 경우에는이를 알리는 말 이라고 말할 것입니다. 때로는이 작업을 수행 하는 것이 좋습니다 *.* 제가이 게시물에 포함 하려는 모든 작업을 설명 하려고 합니다. 역할에 관계 없이 조직에서 Microsoft 클라우드 서비스를 사용 하려는 경우에는 다음과 같은 몇 가지 wisdom 도움이 될 것입니다.


## <a name="guiding-principles"></a>안내 원칙
여기에서 수행 하는 작업에 대 한 몇 가지 기본 규칙부터 알아보겠습니다. 실제 보안을 유지 하면서 최소 복잡성과 최대 성능을 보장 하기 위해 클라우드 서비스에 안전 하 게 연결 하는 방법에 대해 설명 합니다. 다음에 해당 하는 작업 중 어떤 것도 해당 되지 않으며, 사용자 또는 고객 에게도 모든 항목에 대해 즐겨 사용 하는 프록시 서버를 사용할 수 있는 것은 아닙니다.

- **가능 하면 안 되는 것이 고,** 그렇지 않은 경우에는 Paraphrase Ian Malcolm에서 Jurassic 공원 동영상을 시작 해야 합니다. . . 예, 그래, 하지만 보안 팀은 사용자가 수행 해야 하는 일을 방해 하지 않을 가능성이 있는지 여부와 관계 없이 계속 사용 되었습니다. "    
- **보안은 복잡성을 의미 하지** 는 않지만 더 많은 비용을 투자 하거나 더 많은 장치를 통과 하거나 기타 단추를 클릭 하는 것 보다 더 안전 하지는 않습니다.
- **Office 365은 인터넷을 통해 액세스** 되지만 office 365은 인터넷과는 다릅니다. 이 서비스는 Microsoft에서 관리 하 고 사용자를 담당 하는 SaaS 서비스로, 인터넷에서 방문 하는 웹 사이트와는 달리, 실제로는 curtain를 확인 하 고, 목표를 충족 하는 동안 사용자의 작업을 수행 해야 하는 경우에만 정책 및 규정 준수 표준을 충족 하는 데 필요한 컨트롤을 적용할 수 있습니다.
- **Chokepoints은 중요 한 정보를** 제공 하기 때문에 모든 사용자에 대 한 모든 인터넷 트래픽을 일부 중앙 지점으로 설정 하는 것이 좋지만,이 경우에도 대부분의 사이트를 모니터링 하 고 정책을 적용 하는 것 보다 저렴 하지만 모든 위치에서 인터넷 액세스를 프로 비전 하는 것 보다 비용이 적게 들 수 있습니다. 하지만 이러한 chokepoints는 정확히 ... 트래픽이 좁게 있는 지점입니다. 사용자가 설치 되어 있는 Agram 이나 스트리밍 비디오를 스트리밍하는 것을 방지 하지만 업무상 중요 한 비즈니스 응용 프로그램 트래픽을 동일한 방식으로 처리 하지 않도록 하는 데는 문제가 없습니다.
- **Dns가 만족 스 럽 지 않은 경우,** 다른 세계 지역에 있는 서버에 대 한 recursing 요청 또는 ISP의 dns 서버 또는 dns 확인 정보를 캐시 하는 다른 공용 DNS 서버를 사용 하는 경우에 상관 없이 가장 잘 디자인 된 네트워크는 dns 불량에 의해 hamstrung 될 수 있습니다. 
- 이 **작업을 수행 하는 데 사용 되는 방법으로는 간단 하지만,이를 수행** 하는 방법은 물론, 기술 변경 사항 및 Office 365가 예외는 아닙니다. 온-프레미스 서비스에 대해 개발 및 배포 했거나 웹 서핑을 제어 하는 보안 조치를 적용 하는 것은 동일한 수준의 보안 보증을 제공 하지 않으며 성능에 부정적인 영향을 줄 수 있습니다.
- **Office 365는 기본적으로 인터넷을 통해 액세스 하도록 작성 되었습니다** (간단히 설명 됨). 사용자와 edge 간에 수행 하려는 작업에 관계 없이 트래픽이 네트워크를 떠나는 후에도 인터넷을 통해 전송 됩니다. Azure Express를 사용 하 여 네트워크에서 몇 가지 대기 시간 중요 트래픽을 우리에 게 직접 라우팅하는 경우에도 인터넷 연결이 절대적으로 필요 합니다. 수락 합니다. 이를 지나치게 생각해 서는 안 됩니다.

## <a name="where-bad-choices-are-often-made"></a>일반적으로 잘못 된 선택이 수행 되는 위치

보안 이름이 잘못 결정 되는 장소가 많지만, 이러한 위치는 고객에 게 가장 자주 발생 하는 것입니다. 대부분의 고객 대화에는 모든 내용이 한 번에 포함 됩니다.

### <a name="insufficient-resources-at-the-edge"></a>에 지의 리소스 부족
Greenfield 환경을 배포 하는 고객은 매우 적고, 사용자가 작업 하는 방법과 인터넷 송신 환경에 대 한 경험을가지고 왔습니다. 사용자가 프록시 서버를 보유 하 고 있는지 또는 직접 액세스를 허용 하 고 i m i m i m i m a i n i m i m i m a i m a i m a m a m a m a m/m a m a m a m a m a m a m a m a t

대역폭은 항상 중요 하지만 NAT 장치에는 증가 하는 부하를 처리 하기에 충분 한 마가 없을 수 있으며 리소스를 확보 하기 위해 연결을 조기에 닫을 수 있습니다. Office 365에 연결 되는 대부분의 클라이언트 소프트웨어에는 영구 연결이 필요 하며, Office 365를 완전히 활용 하는 사용자는 32 개 이상의 동시 연결을 사용할 수 있습니다. NAT 장치를 제거 하는 경우 해당 앱이 더 이상 없는 연결을 사용 하려고 하면 응답이 없게 될 수 있습니다. 새 연결을 제공 하 고 설정 하려고 하면 네트워크 기어에 부하가 더 많이 추가 됩니다.

### <a name="localized-breakout"></a>지역화 된 브레이크 아웃
이 목록에 있는 다른 모든 항목은 네트워크에서 가능한 한 빨리 이동 하는 한 가지 작업을 수행 합니다. 사용자의 트래픽을 중앙 송신 지점으로 백홀이, 특히 해당 egress 지점이 사용자가 있는 경우와 다른 지역에 있는 경우에는 불필요 한 대기 시간을 도입 하 고 클라이언트 환경 및 다운로드 속도에 모두 영향을 줍니다. Microsoft는 거의 모든 주요 ISP와 함께 구축 된 모든 서비스 및 피어 링에 대 한 프런트 엔드가 있는 전 세계의 현재 상태를 유지 하 고 있으며, 사용자의 트래픽을 *로컬로* 라우팅 하면 최소 대기 시간을 사용 하 여 네트워크에 빠르게 연결할 수 있습니다. 

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS 확인 트래픽은 인터넷 송신 경로를 따라야 합니다.
물론 클라이언트에서 끝점을 찾으려면 DNS를 사용 해야 합니다. Microsoft의 DNS 서버는 요청 원본에 가장 가까운 인터넷 용어로 응답을 반환 하도록 DNS 요청의 원본을 평가 합니다. 이름 확인 요청이 사용자의 트래픽과 같은 경로를 lest 다른 지역의 끝점에 제공 되도록 DNS가 구성 되어 있는지 확인 합니다. 즉, 원격 데이터 센터에서 DNS 서버로 전달 하는 대신 로컬 DNS 서버를 "루트로 이동" 하는 것이 좋습니다. 그리고 세계의 한 부분에서 결과를 캐시 하 고 세계의 다른 부분 으로부터의 요청에 제공 하는 공용 및 개인 DNS 서비스를 시청 하세요.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>프록시에 대 한 프록시에 대 한 질문입니다.
가장 먼저 고려해 야 할 사항은 사용자가 Office 365에 대 한 연결을 프록시 하는지 여부입니다. 이 방법은 간단 합니다. 프록시 하지 않습니다. 인터넷을 통해 Office 365에 액세스 하지만 인터넷은 아닙니다. 핵심 서비스를 확장 한 것으로 취급 해야 합니다. DLP, 맬웨어 방지 또는 콘텐츠 검사와 같이 프록시에서 수행할 수 있는 모든 작업을 서비스에서 이미 사용할 수 있으며, 확장성 및 TLS 암호화 연결을 해독할 필요 없이 사용할 수 있습니다. 그러나 제어할 수 없는 트래픽을 실제로 프록시 하려는 경우에는의 지침 및 트래픽 범주에 주의를 기울여야 [https://aka.ms/pnc](https://aka.ms/pnc) [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) 합니다. Microsoft는 Office 365에 대 한 세 가지 트래픽 범주를 보유 하 고 있습니다. 최적화와 허용은 프록시를 직접 실행 하 고 우회 해야 합니다. 기본값은 프록시 일 수 있습니다. 세부 정보는 해당 문서에 있습니다. . . 읽습니다.

프록시를 사용 하는 대부분의 고객은 실제로 수행 하는 작업을 클라이언트에서 프록시에 대해 HTTP 연결 요청을 수행할 때 더 비싼 추가 라우터인 것으로 인식 하 고 있습니다. MAPI 및 RTC와 같은 사용 중인 프로토콜은 웹 프록시가 이해 하는 프로토콜 일 뿐 이므로 TLS 크랙를 사용 하더라도 실제로는 추가 보안을 얻을 수 없습니다. 추가 *are* 대기 시간이 발생 합니다. [https://aka.ms/pnc](https://aka.ms/pnc)Microsoft 365 트래픽에 대 한 최적화, 허용 및 기본 범주를 포함 하 여 자세한 내용은 여기를 참조 하세요.

마지막으로 프록시에 대 한 전반적인 영향과 해당 영향을 처리 하는 데 대 한 대응을 고려해 야 합니다. 더 많은 연결이 프록시를 통해 이루어지기 때문에 많은 트래픽을 버퍼링 하지 않아도 되도록 TCP 확장 요인이 줄어들 수 있습니다. 필자는 해당 프록시를 사용 하 여이 범위가 0에 해당 하는 오버 로드 된 고객을 보았습니다. 배율 계수는 지 수 값 이기 때문에 8을 사용 하는 것 이므로, 배율 인수 값의 감소는 처리량에 매우 부정적으로 영향을 줍니다.

TLS 검사는 보안을 의미 합니다. 하지만 실제로는 그렇지 않습니다. 프록시를 사용 하는 대부분의 고객은 모든 트래픽을 검사 하 고 TLS "중단 및 검사"를 의미 합니다. HTTPS (개인 정보 취급 방침 notwithstanding)를 통해 액세스 하는 웹 사이트에 대해이 작업을 수행 하는 경우 프록시가 수백 밀리초 동안 10 ~ 20 개의 동시 스트림에 대해이 작업을 수행 해야 할 수 있습니다. 많은 수의 다운로드가 있거나 비디오를 포함 하 고 있는 경우에는 이러한 연결 중 하나 이상이 더 오래 지속 될 수도 있지만 전체적으로는 대부분의 연결이 설정, 전송 및 닫기가 매우 빠릅니다. 중단 및 검사는 프록시가 작업을 두 번 수행 해야 함을 의미 합니다. 클라이언트에서 프록시로의 각 연결에 대해 프록시도 끝점에 대 한 별도의 연결을 설정 해야 합니다. 따라서 1, 2, 4, 32, 64가 됩니다. . . 진행 중인 위치를 확인 하세요. 일반적인 웹 서핑을 위해 프록시 솔루션의 크기를 적절 하 게 조정 했지만 Office 365에 대 한 클라이언트 연결에 대해 동일한 작업을 수행 하려고 하면 오랫동안 지속 되는 장기 연결의 수가 사용자가 설정한 크기 보다 큰 순서로 표시 될 수 있습니다.

### <a name="streaming-isnt-important-except-that-it-is"></a>스트리밍은 중요 하지 않으며, *이* 를 제외 하면
UDP를 사용 하는 Office 365의 서비스는 비즈니스용 Skype (곧 폐기 예정)와 Microsoft 팀입니다. 팀에서는 오디오, 비디오 및 프레젠테이션 공유를 포함 하는 스트리밍 트래픽을 위해 UDP를 사용 합니다. 음성 및 비디오를 제공 하 고 데크를 제공 하거나 데모를 수행 하는 경우와 같은 스트리밍 트래픽이 라이브 됩니다. 이러한 경우에는 패킷이 손실 되거나 순서가 부족 한 경우에 UDP를 사용 하기 때문에 사용자가 실제로 unnoticeable 스트림은 계속 진행 될 수 있습니다. 

클라이언트의 아웃 바운드 UDP 트래픽을 서비스에 허용 하지 않으면 TCP를 사용 하 여 다시 사용할 수 있습니다. 그러나 TCP 패킷이 손실 되 면 재전송 시간 제한 (RTO)이 만료 되어 손실 된 패킷을 다시 전송할 수 있을 때까지 *모든 항목이 중지* 됩니다. 패킷이 순서에 관계 없이 도착 하면 모든 항목은 다른 패킷이 도착할 때까지 중지 되 고 순서 대로 다시 어셈블됩니다. 두 경우 모두 오디오의 perceptible 결함이 발생 합니다 (최대 여유 공간?) 및 비디오 (someth를 클릭 했는지 확인 합니다. . . 이러한 작업을 수행 하면 성능이 저하 되 고 사용자 환경이 잘못 될 수 있습니다. 그리고 프록시에 대해 자세히 설명 하는 내용을 떠올려 보십시오. 팀 클라이언트에서 프록시를 강제로 사용 하도록 설정 하는 경우 TCP를 사용 하도록 강제 설정 합니다. 이제 성능에 부정적인 영향을 두 번 해 서 사용할 수 있습니다.

### <a name="split-tunneling-may-seem-scary"></a>분할 터널링은 무서운 것 처럼 보일 수 있음
하지만 그렇지 않습니다. Office 365에 대 한 모든 연결은 TLS를 통해 수행 됩니다. 지금까지 상당히 많은 경우 TLS 1.2를 제공 하며, 레거시 클라이언트가 여전히이를 사용 하므로 이전 버전을 곧 사용할 수 없게 됩니다.

TLS 연결을 강제 하거나 이러한 연결이 32 되기 전에 VPN을 계속 실행 하는 경우에는 서비스에서 보안을 추가 하지 않습니다. 대기 시간이 추가 되 고 전반적인 처리량이 감소 합니다. 일부 VPN 솔루션에서는 UDP가 TCP를 통해 터널링 되도록 강제 하 여 스트리밍 트래픽에 아주 부정적인 영향을 줄 수도 있습니다. 또한 TLS 검사를 수행 하는 경우가 아니면, 모든 단점은 발생 하지 않습니다. 고객 들이 아주 일반적인 주제 이며, 이제 대부분의 직원이 원격 이기 때문에, 모든 사용자가 [Office 365 끝점을 최적화](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)하기 위해 분할 터널링을 구성 하는 것이 아니라, 현재는 직원 들이 VPN을 사용 하 여 연결을 설정 하는 것 보다 상당한 대역폭과 성능 상의 영향을 볼 수 있다는 것입니다.

분할 터널링을 수행 하는 쉬운 문제를 해결 하는 데 도움이 됩니다. 자세한 내용은 [VPN 분할 터널링을 사용 하 여 원격 사용자에 대 한 Office 365 연결 최적화](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)를 참조 하십시오.


## <a name="the-sins-of-the-past"></a>이전의 죄
많은 경우에는 (1) 서비스가 작동 하는 방식을 알지 못하는 경우 (2) 클라우드를 도입 하기 전에 작성 한 회사 정책을 준수 하 려 하 고, (3) 보안 팀이 목표를 달성할 수 있는 방법이 두 개 이상 있다는 것을 인식 하지 못할 수 있습니다. 앞에서 설명한 것 처럼, 아래 링크에서는 첫 번째 방법을 사용 하는 것이 도움이 됩니다. 두 번째를 통과 하려면 경영 후원이 필요할 수 있습니다. 보안 정책의 목적을 사용 하는 것이 아니라 제 3 자에 게 제공 됩니다. 조건부 액세스에서 콘텐츠 중재, 정보 보호에 대 한 DLP, 끝점 유효성 검사, 0 일 위협에 대 한 해결 방법, 모든 최종 목표는 Office 365에서 사용할 수 있는 것으로, 그리고 온-프레미스 네트워크 기어, 강제 VPN 터널 및 TLS 중단 및 검사에 대 한 종속성을 제외 하 고는 적절 한 보안 정책을 구현할 수 있습니다. 

그렇지 않으면 조직이 클라우드로 이동 하기 전에 조정 되 고 구매한 하드웨어는 새 트래픽 패턴을 처리 하기 위해 수직 확장 될 수 없습니다. 모든 트래픽을 단일 egress 지점을 통해 라우트 해야 하는 경우/또는 프록시를 만들려면 네트워크 장비 및 대역폭을 적절히 업그레이드할 준비를 해야 합니다. 두 사용자가 동시에 사용 되는 경우에는 둘 다에 대 한 사용률을 면밀 하 게 모니터링 합니다. 모든 것은 tipping 지점에 도달할 때까지 아무 문제가 없습니다. 

## <a name="exceptions-to-the-rules"></a>규칙에 대 한 예외

조직에서 [테 넌 트 제한이](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)필요한 경우 TLS 중단 및 검사를 수행 하는 프록시를 사용 하 여 프록시를 통해 일부 트래픽을 강제 적용 해야 하지만이를 통해 모든 트래픽을 강제 실행할 필요는 없습니다.  모두 없거나 아무 것도 수행 하지 않으므로 프록시를 통해 수정 해야 하는 사항에 유의 하세요. 

분할 터널링을 허용 하지만 일반 웹 트래픽에 대해 프록시를 사용 하는 경우에는 PAC 파일에서 직접 진행 해야 하는 항목 및 VPN 터널을 통해 수행 되는 작업에 대 한 흥미로운 트래픽을 정의 하는 방법을 정의 해야 합니다. [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs)이를 보다 쉽게 관리할 수 있도록 샘플 PAC 파일을 제공 합니다.

## <a name="conclusion"></a>결론

거의 모든 Fortune 500을 포함 하 여 수십 대의 조직에서는 업무상 중요 한 기능에 Office 365을 사용 합니다. 이렇게 하면 인터넷을 통해 안전 하 게 작업을 수행할 수 있습니다.

 실행 중인 보안 목표에 관계 없이 VPN 연결, 프록시 서버, TLS 중단 및 검사 또는 중앙 집중식 인터넷 송신이 필요 하지 않은 사용자의 트래픽을 수행 하는 방법 (네트워크가 회사 본부 인지 여부에 관계 없이 네트워크에서 최대한 빠른 성능을 제공 함). 또는 해당 사용자가 집에서 작업 합니다. 이 가이드는 Office 365 서비스를 구축 하 고 보안 및 성능이 뛰어난 사용자 환경을 유지 하는 방법을 기반으로 합니다.

## <a name="further-reading"></a>추가 정보

[Office 365 네트워크 연결 원칙](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)

[Office 365 URL 및 IP 주소 범위](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges?redirectSourcePath=%252fen-us%252farticle%252fOffice-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Office 365 끝점 관리](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)

[Office 365 IP 주소 및 URL 웹 서비스](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)

[Office 365 네트워크 연결 평가](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity) 

[Office 365 네트워크 및 성능 조정](https://docs.microsoft.com/office365/enterprise/network-planning-and-performance)

[Office 365 네트워크 연결 평가](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity) 

[초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정](https://docs.microsoft.com/office365/enterprise/performance-tuning-using-baselines-and-history)

[Office 365 성능 문제 해결 계획](https://docs.microsoft.com/office365/enterprise/performance-troubleshooting-plan)

[콘텐츠 배달 네트워크](https://docs.microsoft.com/office365/enterprise/content-delivery-networks)

[Microsoft 365 연결성 테스트](https://connectivity.office.com/)

[Microsoft가 빠르고 안정적인 글로벌 네트워크를 구축 하는 방법](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 네트워킹 블로그](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[VPN 분할 터널링을 사용 하는 원격 사용자에 대 한 Office 365 연결](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)


