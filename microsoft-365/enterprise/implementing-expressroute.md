---
title: Office 365용 ExpressRoute 구현
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: Office 365용 ExpressRoute를 구현하는 방법을 알아보고, Office 365 서비스에 대한 대체 라우팅 경로를 제공합니다.
ms.openlocfilehash: 767a99f3a27f30b7193fd0d0b8376ff4923daffb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692799"
---
# <a name="implementing-expressroute-for-office-365"></a>Office 365용 ExpressRoute 구현

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Office 365용 ExpressRoute는 여러 인터넷 연결 Office 365 서비스에 대한 대체 라우팅 경로를 제공합니다. Office 365용 ExpressRoute의 아키텍처는 인터넷을 통해 이미 인터넷을 통해 액세스할 수 있는 Office 365 서비스의 광고 공용 IP 접두사에 기반하여 이러한 IP 접두사의 후속 재배포를 위한 프로비전된 ExpressRoute 회로를 기반으로 합니다. ExpressRoute를 사용하면 인터넷 및 ExpressRoute를 통해 많은 Office 365 서비스에 대해 여러 다른 라우팅 경로를 효과적으로 사용하도록 설정할 수 있습니다. 네트워크의 이 라우팅 상태는 내부 네트워크 토폴로지가 디자인되는 방식에 대한 중요한 변경을 나타내는 것일 수 있습니다.
  
 **상태:** 전체 가이드 v2
  
핵심 네트워크와 인터넷에 삽입된 경로가 있는 전용 회로를 통해 라우팅을 사용할 수 있는 네트워크 복잡도에 부호를 수용할 수 있도록 Office 365용 ExpressRoute 구현을 신중하게 계획해야 합니다. 사용자와 팀이 이 가이드의 자세한 계획 및 테스트를 수행하지 않는 경우 ExpressRoute 회로를 사용하는 경우 Office 365 서비스에 대한 연결이 간헐적으로 끊어지거나 총 연결이 끊어질 위험이 있습니다.
  
구현을 성공적으로 수행하려면 인프라 요구 사항을 분석하고, 자세한 네트워크 평가 및 디자인을 거치고, 단계적으로 제어되는 방식으로 롤아웃을 신중하게 계획하고, 자세한 유효성 검사 및 테스트 계획을 세워야 합니다. 대규모 분산 환경의 경우 구현이 몇 개월에 걸쳐 표시될 수 있습니다. 이 가이드는 미리 계획하는 데 도움이 하도록 디자인된 것입니다.
  
대규모의 성공적인 배포는 계획하는 데 6개월이 걸릴 수 있으며 네트워킹, 방화벽 및 프록시 서버 관리자, Office 365 관리자, 보안, 최종 사용자 지원, 프로젝트 관리 및 임원 후원자를 포함하여 조직의 여러 영역에서 팀 구성원을 포함하기도 합니다. 계획 프로세스에 대한 투자로 인해 배포 오류가 발생하여 문제가 발생하거나 복잡하고 비용이 많이 드는 문제 해결이 줄어듭니다.
  
이 구현 가이드가 시작되기 전에 다음과 같은 선행 요구가 완료될 것으로 예상됩니다.
  
1. 네트워크 평가를 완료하여 ExpressRoute가 권장 및 승인된지 확인합니다.

2. ExpressRoute 네트워크 서비스 공급자를 선택했습니다. [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)파트너 및 피어링 위치에 대한 세부 정보를 찾을 수 있습니다.

3. [ExpressRoute](https://azure.microsoft.com/documentation/services/expressroute/) 설명서를 이미 읽고 이해하며 내부 네트워크는 ExpressRoute 선행 요구 사항을 끝까지 충족할 수 있습니다.

4. 팀에서는 [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365) 채널 [https://aka.ms/ert](https://aka.ms/ert) 9의 [Office 365](https://channel9.msdn.com/series/aer) 교육 시리즈에 대한 모든 공개 지침 및 설명서를 읽고 다음을 비롯한 중요한 기술 세부 정보를 이해하기 위해 Azure ExpressRoute를 시청했습니다.

      - SaaS 서비스의 인터넷 종속성

      - 비대칭 경로를 방지하고 복잡한 라우팅을 처리하는 방법

      - 경계 보안, 가용성 및 응용 프로그램 수준 컨트롤을 통합하는 방법

## <a name="begin-by-gathering-requirements"></a>먼저 요구 사항 수집
<a name="requirements"> </a>

조직 내에서 채택할 기능 및 서비스를 결정하는 것부터 시작하십시오. 사용할 다른 Office 365 서비스의 기능과 네트워크에서 해당 기능을 사용하는 사용자들을 호스트할 위치를 결정해야 합니다. 시나리오 카탈로그를 사용하면 각 시나리오에 필요한 네트워크 특성을 추가해야 합니다. 예: 인바운드 및 아웃바운드 네트워크 트래픽 흐름 및 Office 365 끝점을 ExpressRoute를 통해 사용할 수 있는지의 경우
  
조직의 요구 사항을 수집하기 위해
  
- 조직에서 사용 하는 Office 365 서비스의 인바운드 및 아웃바운드 네트워크 트래픽을 카탈로그화합니다. 다른 Office 365 시나리오에 필요한 흐름에 대한 설명은 Office 365 URL 및 IP 주소 범위 페이지를 참조하세요.

- 내부 WAN 백본 및 토폴로지, 위성 사이트 연결, 마지막 마일 사용자 연결, 네트워크 경계 발신 지점으로 라우팅 및 프록시 서비스에 대한 세부 정보를 표시하는 기존 네트워크 토폴로지의 설명서를 수집합니다.

  - 인터넷 및 제안된 ExpressRoute 연결 경로를 모두 표시하여 Office 365 및 기타 Microsoft 서비스가 연결할 네트워크 다이어그램의 인바운드 서비스 끝점을 식별합니다.

  - 현재 인터넷으로의 발신 위치와 함께 위치 간의 모든 지리적 사용자 위치 및 WAN 연결을 식별하고 ExpressRoute 피어링 위치로의 발신을 제안할 위치를 식별합니다.

  - 모든 에지 장치(예: proxies, firewalls 등)를 식별하고 인터넷 및 ExpressRoute를 통해 진행되는 흐름에 대한 관계를 카탈로그화합니다.

  - 최종 사용자가 인터넷 및 ExpressRoute 흐름에 대해 직접 라우팅 또는 간접 응용 프로그램 프록시를 통해 Office 365 서비스에 액세스할지 여부를 문서화합니다.

- 네트워크 다이어그램에 테넌트 및 meet-me 위치의 위치를 추가합니다.

- 주요 사용자 위치에서 Office 365로의 예상 및 관찰된 네트워크 성능 및 대기 시간 특성을 예측합니다. Office 365는 전역 및 분산된 서비스 집합으로, 사용자는 테넌트의 위치와 다를 수 있는 위치에 연결됩니다. 이러한 이유로 ExpressRoute 및 인터넷 연결을 통해 Microsoft 전역 네트워크의 가장 가까운 가장자리와 사용자 간의 대기 시간을 측정하고 최적화하는 것이 좋습니다. 네트워크 평가의 결과를 사용하여 이 작업을 지원할 수 있습니다.

- 새로운 ExpressRoute 연결을 통해 충족해야 하는 회사 네트워크 보안 및 고가용성 요구 사항을 나열합니다. 예를 들어 인터넷 시작 또는 ExpressRoute 회로 오류가 발생하면 사용자가 Office 365에 계속 액세스하는 방법을 예로 들 수 있습니다.

- 인바운드 및 아웃바운드 Office 365 네트워크 흐름이 인터넷 경로를 사용하며 ExpressRoute를 사용할 문서입니다. 사용자의 지리적 위치의 세부 사항과, 각기 다른 사용자 위치와는 다른 계획을 세워야 할 수 있습니다.

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>아웃바운드 및 인바운드 네트워크 트래픽 카탈로그화
<a name="trafficCatalog"> </a>

라우팅 및 기타 네트워크 복잡도 최소화를 위해 규정 요구 사항 또는 네트워크 평가의 결과로 전용 연결을 거치는 데 필요한 네트워크 트래픽 흐름에 Office 365용 ExpressRoute만 사용하는 것이 좋습니다. 또한 ExpressRoute 라우팅의 범위를 단계화하고 구현 프로젝트의 서로 다른 단계와는 다른 고유한 단계로 아웃바운드 및 인바운드 네트워크 트래픽 흐름에 접근하는 것이 좋습니다. 사용자가 시작한 아웃바운드 네트워크 트래픽 흐름을 위해 Office 365용 ExpressRoute를 배포하고 인터넷을 통해 인바운드 네트워크 트래픽 흐름을 남겨 두면 추가적인 비대칭 라우팅 가능성이 도입될 경우의 토니엄 복잡성 및 위험 증가를 제어할 수 있습니다.
  
네트워크 트래픽 카탈로그에는 모든 인바운드 및 아웃바운드 네트워크 연결 목록이 포함되어야 합니다.
  
- 아웃바운드 네트워크 트래픽 흐름은 Microsoft 서비스의 대상을 사용하여 내부 클라이언트 또는 서버에서와 같이, 내부 클라이언트 또는 서버에서 연결이 시작되는 모든 시나리오입니다. 이러한 연결은 Office 365 경로의 프록시 서버, 방화벽 또는 기타 네트워킹 장치를 통과하는 경우와 같이 Office 365 또는 간접 연결일 수 있습니다.

- 인바운드 네트워크 트래픽 흐름은 Microsoft 클라우드에서 On-프레미스 호스트로의 연결이 시작되는 모든 시나리오입니다. 이러한 연결은 일반적으로 외부에서 시작된 흐름에 대해 고객 보안 정책에 필요한 방화벽 및 기타 보안 인프라를 통과해야 합니다.

Office  [365용 ExpressRoute를](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) 사용하여 라우팅 문서의 경로 확인 섹션을 읽어 인바운드 트래픽을 보낼 서비스를 결정하고 Office 365 끝점 참조 문서에서 Office [365용](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) **ExpressRoute로** 표시된 열을 찾아 나머지 연결 정보를 확인할 수 있습니다.
  
아웃바운드 연결이 필요한 각 서비스에 대해 네트워크 라우팅, 프록시 구성, 패킷 검사 및 대역폭 요구 사항을 포함하여 서비스에 대해 계획된 연결을 설명할 수 있습니다.
  
인바운드 연결이 필요한 각 서비스에 대해 몇 가지 추가 정보가 필요합니다. Microsoft 클라우드의 서버는 해당 네트워크에 대한 연결을 설정할 것입니다. 연결이 올바르게 설정되도록 다음을 포함하여 이 연결의 모든 측면을 설명할 수 있습니다. 이러한 인바운드 연결을 수락할 서비스의 공용 DNS 항목, CIDR 형식의 IPv4 IP 주소, ISP 장비가 관련된 ISP 및 이러한 연결에 대해 인바운드 NAT 또는 원본 NAT가 처리되는 방식
  
인바운드 연결은 인터넷 또는 ExpressRoute를 통해 연결되고 있는지에 관계없이 검토하여 비대칭 라우팅이 도입되지 않은지 확인합니다. 경우에 따라 Office 365 서비스에서 인바운드 연결을 시작하는 On-premises 끝점도 다른 Microsoft 및 비 Microsoft 서비스에서 액세스해야 할 수 있습니다. Office 365를 위해 이러한 서비스에 ExpressRoute 라우팅을 사용하도록 설정하는 것이 다른 시나리오를 중단하지 않는 것이 가장 중요합니다. 대부분의 경우 고객은 ExpressRoute를 사용하도록 설정한 후 Microsoft의 인바운드 흐름이 대칭을 유지하도록 내부 네트워크(예: 원본 기반 NAT)를 구현해야 할 수 있습니다.
  
다음은 필요한 세부 정보 수준 샘플입니다. 이 경우 Exchange Hybrid는 ExpressRoute를 통해프레미스 시스템으로 라우팅됩니다.

|**Connection 속성**|**값**|
|:-----|:-----|
|**네트워크 트래픽 방향** <br/> |인바운드  <br/> |
|**서비스** <br/> |Exchange 하이브리드  <br/> |
|**공용 Office 365 끝점(원본)** <br/> |Exchange Online(IP 주소)  <br/> |
|**공용 On-Premises 끝점(대상)** <br/> |5.5.5.5  <br/> |
|**공용(인터넷) DNS 항목** <br/> |Autodiscover.contoso.com  <br/> |
|**이 끝점을 다른(Office 365가 아닌) Microsoft 서비스에서 사용할 수 있습니다.** <br/> |아니요  <br/> |
|**이 끝점을 인터넷의 사용자/시스템에서 사용할 수 있도록 합니다.** <br/> |예  <br/> |
|**공용 끝점을 통해 게시된 내부 시스템** <br/> |Exchange Server 클라이언트 액세스 역할(-프레미스) 192.168.101, 192.168.102, 192.168.103  <br/> |
|**공용 끝점의 IP 광고** <br/> |**인터넷으로**: 5.5.0.0/16  <br/> **ExpressRoute**: 5.5.5.0/24  <br/> |
|**보안/경계 컨트롤** <br/> |**인터넷 경로**: DeviceID_002  <br/> **Express 경로**: DeviceID_003  <br/> |
|**고가용성** <br/> |2개 지리적 중복에서 활성/활성  <br/> ExpressRoute 회로 - 시카고 및 달라  <br/> |
|**경로 대칭 컨트롤** <br/> |**메서드**: 원본 NAT  <br/> **인터넷 경로:** 192.168.5.5에 대한 원본 NAT 인바운드 연결  <br/> |**Express 경로:** 192.168.1.0(시카고) 및 192.168.2.0(다라)에 대한 원본 NAT 연결  <br/> |

다음은 아웃바운드 전용 서비스 샘플입니다.

|**Connection 속성**|**값**|
|:-----|:-----|
|**네트워크 트래픽 방향** <br/> |아웃바운드  <br/> |
|**서비스** <br/> |SharePoint Online  <br/> |
|**On-premises endpoint (source)** <br/> |사용자 workstation  <br/> |
|**공용 Office 365 끝점(대상)** <br/> |SharePoint Online(IP 주소)  <br/> |
|**공용(인터넷) DNS 항목** <br/> |\*.sharepoint.com(및 추가 FQDNS)  <br/> |
|**CDN 추천** <br/> |cdn.sharepointonline.com(및 추가 FQDN) - CDN 공급자가 유지 관리하는 IP 주소  <br/> |
|**사용 중 IP 광고 및 NAT** <br/> |**인터넷 경로/원본 NAT**: 1.1.1.0/24  <br/> **Express 경로/원본 NAT**: 1.1.2.0/24(시카고) 및 1.1.3.0/24(다라)  <br/> |
|**연결 방법** <br/> |**인터넷**: 계층 7 프록시(.pac 파일)를 통해  <br/> **ExpressRoute**: 직접 라우팅(프록시 없음)  <br/> |
|**보안/경계 컨트롤** <br/> |**인터넷 경로**: DeviceID_002  <br/> **Express 경로**: DeviceID_003  <br/> |
|**고가용성** <br/> |**인터넷 경로:** 중복된 인터넷으로의 연결  <br/> **ExpressRoute 경로:** 2개 지리적 중복 ExpressRoute 회로를 가로지르는 활성/활성 '핫 스패킷' 라우팅 - 시카고 및 다라  <br/> |
|**경로 대칭 컨트롤** <br/> |**메서드:** 모든 연결에 대한 원본 NAT  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>지역별 연결을 통해 네트워크 토폴로지 디자인
<a name="topology"> </a>

서비스 및 관련 네트워크 트래픽 흐름을 이해한 후 이러한 새로운 연결 요구 사항을 통합하고 Office 365용 ExpressRoute를 사용하기 위해 변경한 내용을 보여 주는 네트워크 다이어그램을 만들 수 있습니다. 다이어그램에는 다음이 포함되어야 합니다.
  
1. Office 365 및 기타 서비스에 액세스할 모든 사용자 위치

2. 모든 인터넷 및 ExpressRoute egress points.

3. 라우터, 방화벽, 응용 프로그램 프록시 서버 및 침입 감지/방지를 포함하여 네트워크 내/외의 연결을 관리하는 모든 아웃바운드 및 인바운드 장치

4. ADFS 웹 응용 프로그램 프록시 서버로부터의 연결을 수락하는 내부 ADFS 서버와 같은 모든 인바운드 트래픽에 대한 내부 대상입니다.

5. 보급할 모든 IP 서브넷 카탈로그

6. 사람들이 Office 365에 액세스할 각 위치를 식별하고 ExpressRoute에 사용할 meet-me 위치를 나열합니다.

7. 내부 네트워크 토폴로지의 위치 및 부분에서 ExpressRoute에서 학습된 Microsoft IP prefix가 수락, 필터링 및 전파됩니다.

8. 네트워크 토폴로지에서는 각 네트워크 세그먼트의 지리적 위치와 ExpressRoute 및/또는 인터넷을 통해 Microsoft 네트워크에 연결하는 방법을 보여야 합니다.

아래 다이어그램에는 인바운드 및 아웃바운드 라우팅 광고와 함께 Office 365를 사용할 각 위치가 표시됩니다.
  
![ExpressRoute 지역 지역 meet-me](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
아웃바운드 트래픽의 경우 다음 세 가지 방법 중 하나를 통해 Office 365에 액세스합니다.
  
1. 캘리포니아 주민을 위한 북미의 meet-me 위치를 통해

2. 홍콩 주민들을 위해 홍콩에서 meet-me 위치를 통해

3. 방글라데시의 인터넷을 통해 더 적은 수의 사람이고 ExpressRoute 회로가 프로비전된 것이 없습니다.

![지역별 다이어그램에 대한 아웃바운드 연결](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
마찬가지로 Office 365의 인바운드 네트워크 트래픽은 다음 세 가지 방법 중 하나를 통해 반환됩니다.
  
1. 캘리포니아 주민을 위한 북미의 meet-me 위치를 통해

2. 홍콩 주민들을 위해 홍콩에서 meet-me 위치를 통해

3. 방글라데시의 인터넷을 통해 더 적은 수의 사람이고 ExpressRoute 회로가 프로비전된 것이 없습니다.

![지역별 다이어그램에 대한 인바운드 연결](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>적절한 내게 위치 결정

ExpressRoute 회로가 네트워크를 Microsoft 네트워크에 연결하는 실제 위치인 meet-me 위치 선택은 사람들이 Office 365에 액세스할 위치의 영향을 습니다. SaaS 제품으로 Office 365는 Azure에서와 동일한 방식으로 IaaS 또는 PaaS 지역 모델에서 작동하지 않습니다. 대신 Office 365는 분산된 공동 작업 서비스 집합으로, 사용자가 여러 데이터 센터 및 지역에 걸쳐 끝점에 연결해야 할 수 있으며, 이는 사용자의 테넌트가 호스팅되는 동일한 위치나 지역에 있지 않을 수도 있습니다.
  
즉, Office 365용 ExpressRoute에 대해 meet-me 위치를 선택할 때 가장 중요한 고려 사항은 조직의 사용자가 연결할 위치입니다. 최적의 Office 365 연결에 대한 일반적인 권장은 라우팅을 구현하는 것입니다. 따라서 Office 365 서비스에 대한 사용자 요청이 가장 짧은 네트워크 경로를 통해 Microsoft 네트워크로 연결될 수 있도록 이 라우팅을 '핫 에지' 라우팅이라고도 합니다. 예를 들어 대부분의 Office 365 사용자가 한 또는 두 위치에 있는 경우 해당 사용자의 위치에 가장 가까운 meet-me 위치를 선택하면 최적의 디자인을 만들 수 있습니다. 회사에 여러 지역에 많은 사용자 수가 있는 경우 여러 ExpressRoute 회로와 meet-me 위치가 있는 것을 고려할 수 있습니다. 일부 사용자 위치의 경우 Microsoft 네트워크 및 Office 365에 대한 가장 짧고 최적의 경로는 내부 WAN 및 ExpressRoute meet-me 지점이 아닌 인터넷을 통해 진행될 수 있습니다.
  
종종 사용자에게 상대적인 근접성을 가지는 지역 내에서 선택할 수 있는 여러 개의 meet-me 위치가 있습니다. 다음 표를 작성하여 결정을 내릴 수 있습니다.

|**캘리포니아 및 뉴욕의 계획된 ExpressRoute meet-me 위치**||
|:-----|:-----|
|위치  <br/> |사람 수  <br/> |인터넷을 통해 Microsoft 네트워크로의 예상 대기 시간  <br/> |ExpressRoute를 통해 Microsoft 네트워크에 대한 예상 대기 시간  <br/> |
|Los Angeles  <br/> |10,000  <br/> |~15ms  <br/> |~10ms(실리콘 실리콘을 통해)  <br/> |
|워싱턴 DC  <br/> |15,000  <br/> |~20ms  <br/> |~10ms(뉴욕을 통해)  <br/> |
|달라  <br/> |5,000  <br/> |~15ms  <br/> |~40ms(뉴욕을 통해)  <br/> |

Office 365 지역, ExpressRoute 네트워크 서비스 공급자 meet-me 위치 및 위치별로 사용자 수량을 표시하는 전역 네트워크 아키텍처를 개발한 후 최적화를 수행할 수 있는지 식별하는 데 사용할 수 있습니다. 또한 Meet-me 위치를 얻기 위해 트래픽이 먼 위치로 경로가 이동하는 전역 헤어빈 네트워크 연결을 보여 줍니다. 전역 네트워크의 헤어피가 발견된 경우 계속하기 전에 수정해야 합니다. 다른 meet-me 위치를 찾거나 선택적 인터넷 중단 연결 지점을 사용하여 헤어빈을 방지합니다.
  
첫 번째 다이어그램은 북미에 실제 위치가 두 개 있는 고객의 예를 보여줍니다. Office 위치, Office 365 테넌트 위치 및 ExpressRoute meet-me 위치에 대한 몇 가지 선택 사항을 볼 수 있습니다. 이 예에서 고객은 다음 두 가지 원칙에 따라 다음 순서로 충족 장소를 선택했습니다.
  
1. 조직 내 사용자와 가장 가까운 거리입니다.

2. Office 365가 호스팅되는 Microsoft 데이터 센터와 가장 가까운 위치입니다.

![ExpressRoute US geographic meet-me](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
이 개념을 약간 더 확장하면 두 번째 다이어그램은 유사한 정보 및 의사 결정으로 직면한 다국적 고객의 예를 보여 주게 됩니다. 이 고객은 방글라데시에 소규모 사무실을 가며, 10명으로 소규모 팀에서만 이 지역의 규모를 늘려가고 있습니다. Chennai에는 meet-me 위치가 있으며, Chennai에 호스트된 Office 365가 있는 Microsoft 데이터 센터가 있으므로 만남 위치가 좋습니다. 그러나 10명에게 추가 회로의 비용은 부담이 될 수 있습니다. 네트워크를 살펴보면 네트워크를 통해 네트워크 트래픽을 보내는 데 관련된 대기 시간이 다른 ExpressRoute 회로를 취득하는 데 자본을 소비하는 것보다 더 효과적인지 여부를 결정해야 합니다.
  
또는 방글라데시의 10명은 소개 다이어그램에 표시되어 있으며 아래 재현된 내부 네트워크에서 라우팅하는 것보다 인터넷을 통해 Microsoft 네트워크로 전송된 네트워크 트래픽으로 더 나은 성능을 경험할 수 있습니다.
  
![지역별 다이어그램에 대한 아웃바운드 연결](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>Office 365 구현 계획에 대한 ExpressRoute 만들기
<a name="implementation"> </a>

구현 계획에는 ExpressRoute 구성의 기술 세부 정보와 네트워크의 다른 모든 인프라 구성 세부 정보(예: 다음)가 모두 들어야 합니다.
  
- ExpressRoute와 인터넷 간에 분할된 서비스를 계획합니다.

- 대역폭, 보안, 고가용성 및 장애 조치 계획

- 서로 다른 위치에 대한 적절한 라우팅 경로 최적화를 포함하여 인바운드 및 아웃바운드 라우팅 디자인

- ExpressRoute 경로를 네트워크에 보급할 거리와 클라이언트가 인터넷 또는 ExpressRoute 경로를 선택하기 위한 메커니즘을 결정하십시오. 예를 들어 직접 라우팅 또는 응용 프로그램 프록시를 사용할 수 있습니다.

- 보낸 사람 정책 프레임워크 항목을 포함하여 DNS [레코드 변경을 계획합니다.](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)

- 아웃바운드 및 인바운드 원본 NAT를 포함한 NAT 전략을 계획합니다.

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>인터넷 및 ExpressRoute 네트워크 경로를 모두 통해 라우팅 계획
<a name="paths"> </a>

- 초기 배포의 경우 인바운드 전자 메일 또는 하이브리드 연결과 같은 모든 인바운드 서비스가 인터넷을 사용하는 것이 좋습니다.

- [PAC/WPAD](https://aka.ms/manageo365endpoints)파일, 기본 경로, 프록시 서버 및 BGP 경로 광고 구성과 같은 최종 사용자 클라이언트 LAN 라우팅을 계획합니다.

- 프록시 서버, 방화벽 및 클라우드 프록시를 비롯한 경계 라우팅을 계획합니다.

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>대역폭, 보안, 고가용성 및 장애 조치 계획
<a name="availability"> </a>

각 주요 Office 365 워크로드에 필요한 대역폭 계획을 작성합니다. Exchange Online, SharePoint Online 및 비즈니스용 Skype Online 대역폭 요구 사항을 별도로 예측합니다. Exchange Online 및 비즈니스용 Skype에 대해 제공한 추정 계산기를 시작 장소로 사용할 수 있습니다. 그러나 조직의 대역폭 요구 사항을 완전히 이해하려면 사용자 프로필 및 위치의 대표적인 샘플이 있는 파일럿 테스트가 필요합니다.
  
각 인터넷 및 ExpressRoute 발신 위치에서 보안이 계획에 처리되는 방법을 추가하고, Office 365에 대한 모든 ExpressRoute 연결은 공용 피어링을 사용하며, 외부 네트워크에 연결하는 회사 보안 정책에 따라 계속 보호되어야 합니다.
  
계획에 정전 유형 및 해당 사람들이 가장 간단한 방법으로 전체 용량으로 작업을 수행할 수 있는 방법에 대한 세부 정보를 추가합니다.
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>지터, 대기 시간, 정체 및 Headroom에 대한 비즈니스용 Skype 요구 사항을 포함한 대역폭 요구 사항 계획
  
비즈니스용 Skype Online에는 비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능 문서에 자세히 설명된 특정 추가 네트워크 요구 [사항도 있습니다.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Office 365용 ExpressRoute를](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)사용하여 네트워크 계획에서 **Azure ExpressRoute에** 대한 대역폭 계획 섹션을 읽어 읽습니다.
  
파일럿 사용자와 대역폭 평가를 수행할 때 이 가이드를 사용할 수 있습니다. 기준 및 성능 기록을 사용하여 [Office 365 성능 조정](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
  
#### <a name="plan-for-high-availability-requirements"></a>고가용성 요구 사항 계획
  
요구 사항을 충족하기 위한 고가용성 계획을 만들고 이를 업데이트된 네트워크 토폴로지 다이어그램에 통합합니다. [Office 365용 ExpressRoute를](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)사용하여 네트워크 계획에서 **Azure ExpressRoute를** 사용하여 고가용성 및 장애 조치 섹션을 읽어 읽습니다.
  
#### <a name="plan-for-network-security-requirements"></a>네트워크 보안 요구 사항 계획
  
네트워크 보안 요구 사항을 충족하는 계획을 세우고 이를 업데이트된 네트워크 토폴로지 다이어그램에 통합합니다. [Office 365용 ExpressRoute를](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)사용하여 네트워크 계획에서 **Office 365용 Azure ExpressRoute** 시나리오에 보안 컨트롤 적용 섹션을 읽어 읽습니다.
  
### <a name="design-outbound-service-connectivity"></a>아웃바운드 서비스 연결 디자인
<a name="outbound"> </a>

Office 365용 ExpressRoute에는 익숙하지 않을 수 있는 아웃바운드 네트워크 요구 사항이 있습니다.  특히 Office 365에 대한 사용자 및 네트워크를 나타내고 Microsoft에 대한 아웃바운드 네트워크 연결의 원본 끝점 역할을 하는 IP 주소는 아래에 설명된 특정 요구 사항을 따라야 합니다.
  
1. 끝점은 회사 또는 사용자에게 ExpressRoute 연결을 제공하는 통신 회사에 등록된 공용 IP 주소입니다.

2. 끝점은 Microsoft에 보급하고 ExpressRoute에서 유효성을 검사/수락해야 합니다.

3. 끝점은 동일하거나 더 선호되는 라우팅 메트릭을 사용하여 인터넷에 보급하지 말아야 합니다.

4. ExpressRoute를 통해 구성되지 않은 Microsoft 서비스에 연결하기 위해 끝점을 사용하면 안 됩니다.

네트워크 디자인이 이러한 요구 사항을 충족하지 않는 경우 검은색 홀링 또는 비대칭 라우팅 경로 지정으로 인해 사용자가 Office 365 및 기타 Microsoft 서비스에 대한 연결 실패를 경험할 위험이 있습니다. Microsoft 서비스에 대한 요청이 ExpressRoute를 통해 라우팅되지만 응답이 인터넷을 통해 다시 라우팅되거나 그 반대로 라우팅되거나 방화벽과 같은 상태 관리 네트워크 장치에 의해 응답이 삭제될 때 발생합니다.
  
위의 요구 사항을 충족하는 데 사용할 수 있는 가장 일반적인 방법은 네트워크의 일부로 구현되거나 ExpressRoute 통신 사업자에서 제공하는 원본 NAT를 사용하는 것입니다. 원본 NAT를 사용하면 ExpressRoute에서 인터넷 네트워크의 세부 정보 및 개인 IP 주소를 추상화할 수 있습니다. 적절한 IP 경로 광고와 결합하여 경로 대칭을 보장하는 쉬운 메커니즘을 제공합니다. ExpressRoute 피어링 위치와 관련이 있는 상태 관리 네트워크 장치를 사용하는 경우 경로 대칭을 보장하기 위해 각 ExpressRoute 피어링에 대해 별도의 NAT 풀을 구현해야 합니다.
  
[ExpressRoute NAT 요구 사항에 대해 자세히 읽어 읽습니다.](https://azure.microsoft.com/documentation/articles/expressroute-nat/)
  
네트워크 토폴로지 다이어그램에 대한 아웃바운드 연결에 대한 변경 내용을 추가합니다.
  
### <a name="design-inbound-service-connectivity"></a>인바운드 서비스 연결 디자인
<a name="inbound"> </a>

대부분의 엔터프라이즈 Office 365 배포에서는 Exchange, SharePoint 및 비즈니스용 Skype 하이브리드 시나리오, 사서함 마이그레이션 및 ADFS 인프라를 사용하는 인증과 같은 Office 365에서 Office 365로의 일종의 인바운드 연결에 대해 가정합니다. ExpressRoute를 사용하여 아웃바운드 연결을 위해 Microsoft와의 추가 라우팅 경로를 사용하도록 설정하면 해당 흐름이 인터넷을 계속 사용하도록 하려는 경우에도 이러한 인바운드 연결은 비대칭 라우팅의 영향을 부과할 수 있습니다. 아래에 설명된 몇 가지 예방조치가 Office 365에서 Office 365 시스템으로의 인바운드 흐름을 기반으로 하는 인터넷에 영향을 끼치지 않도록 하는 것이 좋습니다.
  
인바운드 네트워크 트래픽 흐름에 대한 비대칭 라우팅 위험을 최소화하기 위해 모든 인바운드 연결은 ExpressRoute에 대한 라우팅 가시성이 있는 네트워크 세그먼트로 라우팅되기 전에 원본 NAT를 사용해야 합니다. 원본 NAT 없이 ExpressRoute에 대한 라우팅 가시성이 있는 네트워크 세그먼트로 들어오는 연결이 허용되는 경우 Office 365에서 시작된 요청은 인터넷에서 입력되지만 Office 365로 돌아가는 응답은 ExpressRoute 네트워크 경로를 다시 Microsoft 네트워크로 다시 선호하여 비대칭 라우팅을 유발합니다.
  
이 요구 사항을 충족하기 위해 다음 구현 패턴 중 하나를 고려할 수 있습니다.
  
1. 인터넷에서 프레미스 시스템으로의 경로에 있는 방화벽 또는 부하 조정 장치와 같은 네트워킹 장비를 사용하여 요청이 내부 네트워크로 라우팅되기 전에 원본 NAT를 수행하십시오.

2. ExpressRoute 경로가 인터넷 연결을 처리하는 프런트 엔드 서버 또는 역방향 프록시 시스템과 같은 인바운드 서비스가 있는 네트워크 세그먼트로 전파되지 않도록 합니다.

네트워크에서 이러한 시나리오를 명시적으로 고려하고 인터넷을 통해 모든 인바운드 네트워크 트래픽 흐름을 유지하면 비대칭 라우팅의 배포 및 운영 위험을 최소화할 수 있습니다.
  
ExpressRoute 연결을 통해 일부 인바운드 흐름을 지시할 수 있는 경우도 있습니다. 이러한 시나리오에서는 다음과 같은 추가 고려 사항을 고려해야 합니다.
  
1. Office 365는 공용 IPS를 사용하는 끝점만 대상으로 할 수 있습니다. 즉, 익스프레미스 인바운드 끝점이 ExpressRoute를 통해 Office 365에만 노출되는 경우에도 공용 IP를 연결해야 합니다.

2. Office 365 서비스에서 수행한 모든 DNS 이름 확인은 공용 DNS를 사용하여 수행됩니다. 즉, 인터넷에서 인바운드 서비스 끝점의 FQDN과 IP 매핑을 등록해야 합니다.

3. ExpressRoute를 통해 인바운드 네트워크 연결을 수신하려면 이러한 끝점에 대한 공용 IP 서브넷을 ExpressRoute를 통해 Microsoft에 보급해야 합니다.

4. 이러한 인바운드 네트워크 트래픽 흐름을 신중하게 평가하여 회사 보안 및 네트워크 정책에 따라 적절한 보안 및 네트워크 제어가 적용되는지 확인합니다.

5. 익스프레미스 인바운드 끝점이 ExpressRoute를 통해 Microsoft에 보급된 후 ExpressRoute는 Office 365를 포함하여 모든 Microsoft 서비스의 해당 끝점에 대한 기본 라우팅 경로가 됩니다. 즉, 해당 끝점 서브넷은 Office 365 서비스와의 통신에만 사용되어야 하며 Microsoft 네트워크의 다른 서비스는 사용되지 않습니다. 그렇지 않으면 다른 Microsoft 서비스의 인바운드 연결이 ExpressRoute를 통해 인바운드를 라우팅하는 것을 선호하는 비대칭 라우팅이 발생하고 반환 경로는 인터넷을 사용하게 됩니다.

6. ExpressRoute 회로 또는 meet-me 위치가 다운된 경우, 별도의 네트워크 경로를 통해 요청을 수락할 수 있도록 여전히 프레미스 인바운드 끝점을 사용할 수 있도록 해야 합니다. 이는 여러 ExpressRoute 회로를 통해 해당 끝점에 대한 광고 서브넷을 의미할 수 있습니다.

7. 특히 이러한 흐름이 방화벽과 같은 상태 관리 네트워크 장치 간을 통과하는 경우 ExpressRoute를 통해 네트워크에 유입되는 모든 인바운드 네트워크 트래픽 흐름에 원본 NAT를 적용하는 것이 좋습니다.

8. ADFS 프록시 또는 Exchange 자동 검색과 같은 일부 On-premises 서비스는 Office 365 서비스와 인터넷 모두에서 인바운드 요청을 받을 수 있습니다. 이러한 요청의 경우 Office 365는 인터넷을 통해 사용자 요청과 동일한 FQDN을 대상으로 합니다. 인터넷에서 해당 끝점으로의 인바운드 사용자 연결을 허용하는 동시에 Office 365 연결이 ExpressRoute를 사용하게 하도록 설정하면 라우팅 복잡성이 크게 증가합니다. 대부분의 고객이 ExpressRoute를 통해 이러한 복잡한 시나리오를 구현하는 것은 운영 고려 사항으로 인해 권장되지 않습니다. 이 추가 오버헤드에는 비대칭 라우팅의 위험을 관리하며 여러 차원에서 라우팅 광고 및 정책을 신중하게 관리해야 합니다.

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>네트워크 토폴로지 계획을 업데이트하여 비대칭 경로를 방지하는 방법 표시
<a name="asymmetric"> </a>

조직의 사용자가 인터넷의 다른 중요한 서비스뿐만 아니라 Office 365를 원활하게 사용할 수 있도록 비대칭 라우팅을 방지하려는 경우 고객에게는 비대칭 라우팅을 유발하는 두 가지 일반적인 구성이 있습니다. 이제 사용할 네트워크 구성을 검토하고 이러한 비대칭 라우팅 시나리오 중 하나일 수 있는지 확인할 수 있습니다.
  
먼저 다음 네트워크 다이어그램과 관련된 몇 가지 다른 상황을 살펴보아야 합니다. 이 다이어그램에서는 ADFS 또는 하이브리드 서버와 같은 인바운드 요청을 받는 모든 서버가 새 저지 데이터 센터에 있으며 인터넷에 보급됩니다.
  
1. 경계 네트워크는 안전하기는 하지만 들어오는 요청에 사용할 수 있는 원본 NAT는 없습니다.

2. New Jersey 데이터 센터의 서버는 인터넷 및 ExpressRoute 경로를 모두 볼 수 있습니다.

![ExpressRoute 연결 개요](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
또한 이러한 문제를 해결하는 방법에 대한 제안도 있습니다.
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>문제 1: 인터넷을 통해 클라우드에서 프레미스로의 연결
  
다음 다이어그램은 네트워크 구성에서 인터넷을 통해 Microsoft 클라우드의 인바운드 요청에 NAT를 제공하지 않는 경우 취하는 비대칭 네트워크 경로를 보여 주는 다이어그램입니다.
  
1. Office 365의 인바운드 요청은 공용 DNS에서온-프레미스 끝점의 IP 주소를 검색하고 경계 네트워크로 요청을 전송합니다.

2. 이 잘못된 구성에서는 트래픽이 전송되어 실제 원본 IP 주소가 반환 대상으로 사용되는 경계 네트워크에서 원본 NAT를 구성하거나 사용할 수 없습니다.

  - 네트워크의 서버는 사용 가능한 ExpressRoute 네트워크 연결을 통해 반환 트래픽을 Office 365로 라우팅합니다.

  - 그 결과 Office 365로의 해당 흐름에 대한 비대칭 경로가 생성되어 연결이 끊어집니다.

![ExpressRoute 비대칭 라우팅 문제 1](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>해결 방법 1a: 원본 NAT
  
원본 NAT를 인바운드 요청에 추가하기만 하면 잘못 구성된 네트워크가 해결됩니다. 다음은 이 다이어그램에 대한 설명입니다.
  
1. 들어오는 요청은 계속해서 New Jersey 데이터 센터의 경계 네트워크를 통해 입력됩니다. 이번에는 원본 NAT를 사용할 수 있습니다.

2. 서버의 응답은 원래 IP 주소 대신 원본 NAT와 연결된 IP로 다시 라우팅되어 응답이 동일한 네트워크 경로를 따라 반환됩니다.

![ExpressRoute 비대칭 라우팅 솔루션 1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>솔루션 1b: 라우트 스코핑
  
또는 ExpressRoute BGP 사전 보급을 허용하지 않고 해당 컴퓨터의 대체 네트워크 경로를 제거하도록 선택할 수 있습니다. 다음은 이 다이어그램에 대한 설명입니다.
  
1. 들어오는 요청은 계속해서 New Jersey 데이터 센터의 경계 네트워크를 통해 입력됩니다. 이번에는 New Jersey 데이터 센터에서 ExpressRoute 회로를 통해 Microsoft에서 보급한 사전을 사용할 수 없습니다.

2. 서버의 응답은 사용 가능한 유일한 경로를 통해 원래 IP 주소와 연결된 IP로 다시 라우팅되어 응답이 동일한 네트워크 경로를 따라 반환됩니다.

![ExpressRoute 비대칭 라우팅 솔루션 2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>문제 2: ExpressRoute를 통해 클라우드에서 프레미스로의 연결
  
다음 다이어그램은 네트워크 구성에서 ExpressRoute를 통해 Microsoft 클라우드의 인바운드 요청에 대해 NAT를 제공하지 않는 경우 취하는 비대칭 네트워크 경로를 보여 주는 다이어그램입니다.
  
1. Office 365의 인바운드 요청은 DNS에서 IP 주소를 검색하고 경계 네트워크로 요청을 전송합니다.

2. 이 잘못된 구성에서는 트래픽이 전송되어 실제 원본 IP 주소가 반환 대상으로 사용되는 경계 네트워크에서 원본 NAT를 구성하거나 사용할 수 없습니다.

  - 네트워크의 컴퓨터가 사용 가능한 ExpressRoute 네트워크 연결을 통해 반환 트래픽을 Office 365로 라우팅합니다.

  - 그 결과 Office 365에 대한 비대칭 연결이 됩니다.

![ExpressRoute 비대칭 라우팅 문제 2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>해결 방법 2: 원본 NAT
  
원본 NAT를 인바운드 요청에 추가하기만 하면 잘못 구성된 네트워크가 해결됩니다. 다음은 이 다이어그램에 대한 설명입니다.
  
1. 들어오는 요청은 뉴욕 데이터 센터의 경계 네트워크를 통해 계속 입력됩니다. 이번에는 원본 NAT를 사용할 수 있습니다.

2. 서버의 응답은 원래 IP 주소 대신 원본 NAT와 연결된 IP로 다시 라우팅되어 응답이 동일한 네트워크 경로를 따라 반환됩니다.

![ExpressRoute 비대칭 라우팅 솔루션 3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>네트워크 디자인에 경로 대칭이 있는지 확인

이제 구현 계획이 Office 365를 사용할 여러 시나리오에 대해 경로 대칭을 제공하는지 문서에서 확인해야 합니다. 사용자가 서비스의 다른 기능을 사용할 때 취해야 하는 특정 네트워크 경로를 식별합니다. On-premises network and WAN routing, to the perimeter devices, to the connectivity path; ExpressRoute 또는 인터넷 및 온라인 끝점에 대한 연결
  
이전에 조직에서 채택할 서비스로 식별된 모든 Office 365 네트워크 서비스에 대해 이 작업을 해야 합니다.
  
이 문서에서는 두 번째 사용자와 함께 경로를 따라 이동하는 데 도움이 됩니다. 각 네트워크 홉이 다음 경로를 얻을 것으로 예상되는 위치를 설명하고 라우팅 경로를 잘 알고 있도록 합니다. ExpressRoute는 항상 인터넷 기본 경로보다 경로 비용을 낮추는 Microsoft 서버 IP 주소에 대한 보다 범위가 지정되는 경로를 제공합니다.
  
### <a name="design-client-connectivity-configuration"></a>클라이언트 연결 구성 디자인
<a name="asymmetric"> </a>

![ExpressRoute에서 PAC 파일 사용](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
인터넷 바인딩 트래픽에 프록시 서버를 사용하는 경우 네트워크의 클라이언트 컴퓨터가 프록시 서버를 전송하지 않고 원하는 ExpressRoute 트래픽을 Office 365로 보내도록 올바르게 구성되도록 PAC 또는 클라이언트 구성 파일을 조정해야 합니다. 일부 Office 365 트래픽을 비롯한 나머지 트래픽은 관련 프록시로 전송됩니다. PAC 파일과 같은 [Office 365](https://aka.ms/manageo365endpoints) 끝점 관리에 대한 가이드를 읽어보세요.
  
> [!NOTE]
> 끝점은 매주 자주 변경됩니다. 조직에서 채택한 서비스 및 기능에 따라 변경해야만 최신을 유지해야 하는 변경 횟수를 줄일 수 있습니다. 변경 내용이 발표되고 기록이 과거의 모든 변경 내용으로 유지되는 RSS 피드의 유효 날짜에 주의를 기울이면 유효 날짜에 도달할 때까지 알림이 적용되거나 광고에서 제거될 수 있습니다. 
  
## <a name="build-your-deployment-and-testing-procedures"></a>배포 및 테스트 절차 구축
<a name="testing"> </a>

구현 계획에는 테스트 및 롤백 계획이 모두 포함되어야 합니다. 구현이 예상대로 작동하지 않는 경우 문제가 발견되기 전에 최소한의 사용자 수에 영향을 미치기 위한 계획을 세우는 것이 가장 거입니다. 다음은 계획에서 고려해야 하는 몇 가지 높은 수준의 원칙입니다.
  
1. 중단을 최소화하기 위해 네트워크 세그먼트 및 사용자 서비스 온보더링을 단계별로 구성합니다.

2. 별도의 인터넷에 연결된 호스트에서 추적 경로 및 TCP 연결을 사용하여 경로를 테스트하기 위한 계획을 세우는 것입니다.

3. 인바운드 및 아웃바운드 서비스의 테스트는 테스트 Office 365 테넌트가 있는 격리된 테스트 네트워크에서 수행해야 합니다.

      - 또는 고객이 아직 Office 365를 사용하지 않았거나 파일럿을 사용 중이면 프로덕션 네트워크에서 테스트를 수행할 수 있습니다.

      - 또는 테스트 및 모니터링을 위해 별개로 설정된 프로덕션 정전 중에 테스트를 수행할 수 있습니다.

      - 또는 각 계층 3 라우터 노드에서 각 서비스에 대한 경로를 확인하여 테스트를 완료할 수 있습니다. 실제 테스트의 부족으로 위험이 도입된 것이기 때문에 다른 테스트가 불가능한 경우 이 가을을 다시 사용해야 합니다.

### <a name="build-your-deployment-procedures"></a>배포 절차 구축

대규모 사용자 그룹에 배포하기 전에 테스트할 수 있도록 배포 절차는 소규모 사용자 그룹에 단계적 배포해야 합니다. 다음은 ExpressRoute 배포를 단계적으로 구성하는 몇 가지 방법입니다.
  
1. Microsoft 피어링을 통해 ExpressRoute를 설정하고 단계적 테스트 목적으로만 경로 광고를 단일 호스트로 전달합니다.

2. 처음에 ExpressRoute 네트워크에 대한 경로를 단일 네트워크 세그먼트로 보급하고 네트워크 세그먼트 또는 지역별로 경로 광고를 확장합니다.

3. Office 365를 처음 배포하는 경우 소수의 사용자에 대해 ExpressRoute 네트워크 배포를 파일럿으로 사용하십시오.

4. 프록시 서버를 사용하는 경우 테스트 PAC 파일을 구성하여 소수의 사용자가 추가하기 전에 테스트 및 피드백을 사용하여 ExpressRoute로 보내도록 할 수 있습니다.

구현 계획에는 수행해야 하는 각 배포 절차 또는 네트워킹 구성을 배포하는 데 사용되어야 하는 명령이 나열되어야 합니다. 네트워크의 정전 시간이 도착하면 변경하는 모든 변경 내용은 미리 작성된 서면 배포 계획에서 작성한 것이고 피어는 검토해야 합니다. ExpressRoute의 기술 구성에 대한 지침을 참조하세요.
  
- 전자 메일을 계속 보낼 모든 프레미스 서버의 IP 주소를 변경한 경우 SPF TXT 레코드를 업데이트합니다.

- 새 NAT 구성을 수용할 수 있도록 IP 주소를 변경한 경우, 모든 DNS 항목을 업데이트합니다.

- 라우팅 또는 프록시 구성을 유지 관리하기 위해 Office 365 끝점 알림에 대한 RSS 피드를 구독해야 합니다.

ExpressRoute 배포가 완료되면 테스트 계획의 절차를 실행해야 합니다. 각 절차에 대한 결과를 기록해야 합니다. 테스트 계획 결과에 구현이 성공하지 않은 경우 원래 프로덕션 환경으로 롤백하기 위한 절차를 포함해야 합니다.
  
### <a name="build-your-test-procedures"></a>테스트 절차 작성

테스트 절차에는 ExpressRoute를 사용할 각 아웃바운드 및 인바운드 네트워크 서비스에 대한 테스트와 사용하지 않을 Office 365에 대한 테스트가 포함되어야 합니다. 이 절차에는 회사 LAN의 각 프레미스가 아닌 사용자를 포함하여 각 고유 네트워크 위치에서의 테스트가 포함되어야 합니다.
  
테스트 작업의 몇 가지 예는 다음과 같습니다.
  
1. Ping from your on-premises router to your network operator router.

2. 500+ Office 365 및 CRM Online IP 주소 광고가온-프레미스 라우터에서 수신되어 유효한지 확인합니다.

3. 인바운드 및 아웃바운드 NAT가 ExpressRoute와 내부 네트워크 간에 작동하고 있는지 확인합니다.

4. NAT 경로가 라우터에서 보급되고 있는지 확인합니다.

5. ExpressRoute가 보급된 도우미를 수락한지 유효성을 검사합니다.

      - 다음 cmdlet을 사용하여 피어링 광고를 확인할 수 있습니다.

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. 공용 NAT IP 범위가 다른 ExpressRoute 또는 공용 인터넷 네트워크 회로를 통해 Microsoft에 보급되지 않는지 확인합니다.(이전 예제와 같은 더 큰 범위의 특정 하위 집합이 아닌 경우).

7. ExpressRoute 회로는 쌍으로 연결되고 두 BGP 세션이 모두 실행 중인지 유효성을 검사합니다.

8. NAT 내부에 단일 호스트를 설정하고 ping, tracert 및 tcpping을 사용하여 새 회로에서 호스트 365에 대한 연결을 outlook.office365.com. 또는 미러링된 포트의 Wireshark 또는 Microsoft Network Monitor 3.4와 같은 도구를 사용하여 MSEE에 연결된 IP 주소에 연결할 수 outlook.office365.com.

9. Exchange Online에 대한 응용 프로그램 수준 기능을 테스트합니다.

  - 테스트 Outlook은 Exchange Online에 연결하여 전자 메일을 보내고 받을 수 있습니다.

  - 테스트 Outlook은 온라인 모드를 사용할 수 있습니다.

  - 스마트폰 연결 및 보내기/받기 기능을 테스트합니다.

10. SharePoint Online의 응용 프로그램 수준 기능 테스트

  - 비즈니스용 OneDrive 동기화 클라이언트를 테스트합니다.

  - SharePoint Online 웹 액세스를 테스트합니다.

11. 비즈니스용 Skype 통화 시나리오에 대한 응용 프로그램 수준 기능을 테스트합니다.

  - 인증된 사용자로 전화 회의에 참가[최종 사용자가 시작한 초대]입니다.

  - 전화 회의에 사용자를 초대 [MCU에서 보낸 초대].

  - 비즈니스용 Skype 웹 응용 프로그램을 사용하여 회의에 익명 사용자로 참가합니다.

  - 유선 PC 연결, IP 전화 및 모바일 장치에서 통화에 참가합니다.

  - 페더전 사용자 o PSTN 유효성 검사에 대한 통화: 통화가 완료되었습니다. 통화 품질이 허용됩니다. 연결 시간이 허용됩니다.

  - 연락처의 현재 상태가 테넌트 및 페더러티 사용자의 두 구성원 모두에 대해 업데이트되어 있는지를 확인할 수 있습니다.

### <a name="common-problems"></a>일반적인 문제

비대칭 라우팅은 가장 일반적인 구현 문제입니다. 다음은 찾아야 하는 몇 가지 일반적인 소스입니다.
  
- 원본 NAT가 없는 열린 네트워크 라우팅 토폴로지 또는 플랫 네트워크 라우팅 토폴로지 사용

- 인터넷 및 ExpressRoute 연결을 통해 인바운드 서비스로 라우팅하는 데 SNAT를 사용하지 않습니다.

- 광범위하게 배포하기 전에 테스트 네트워크에서 ExpressRoute에서 인바운드 서비스를 테스트하지 않습니다.

## <a name="deploying-expressroute-connectivity-through-your-network"></a>네트워크를 통해 ExpressRoute 연결 배포
<a name="testing"> </a>

각 새 네트워크 세그먼트에 대해 롤백할 계획을 사용하여 네트워크의 여러 부분에 대한 연결을 점진적으로 배포하여 한 네트워크의 한 세그먼트에 배포를 준비합니다. 배포가 Office 365 배포에 맞춰진 경우 먼저 Office 365 파일럿 사용자에게 배포하고 해당 사용자부터 확장합니다.
  
먼저 테스트한 다음 프로덕션을 위해 다음을 실행합니다.
  
- 배포 단계를 실행하여 ExpressRoute를 사용하도록 설정할 수 있습니다.

- 네트워크 경로가 예상대로 표시될지 테스트합니다.

- 각 인바운드 및 아웃바운드 서비스에 대해 테스트를 수행하십시오.

- 문제가 발견된 경우 롤백합니다.

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>테스트 네트워크 세그먼트를 사용하여 ExpressRoute에 대한 테스트 연결 설정

이제 문서에 대한 계획을 완료한 후 소규모로 테스트해야 합니다. 이 테스트에서는 Microsoft 피어링과 단일 ExpressRoute 연결을 설정하여,프레미스 네트워크의 테스트 서브넷에 연결합니다. 테스트 서브넷과 연결하여 [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=403802) 테넌트 평가판을 구성하고 프로덕션에서 사용할 모든 아웃바운드 및 인바운드 서비스를 테스트 서브넷에 포함할 수 있습니다. 테스트 네트워크 세그먼트에 대한 DNS를 설정하고 모든 인바운드 및 아웃바운드 서비스를 설정합니다. 테스트 계획을 실행하고 각 서비스의 라우팅과 경로 전파에 익숙한지 확인
  
### <a name="execute-the-deployment-and-test-plans"></a>배포 및 테스트 계획 실행

위에서 설명한 항목을 완료할 때 완료한 영역을 확인하고 배포 및 테스트 계획을 실행하기 전에 사용자와 팀이 검토한 항목을 검토합니다.
  
- 네트워크 변경과 관련된 아웃바운드 및 인바운드 서비스 목록입니다.

- 인터넷 출구 및 ExpressRoute meet-me 위치를 모두 보여 주며 글로벌 네트워크 아키텍처 다이어그램입니다.

- 배포된 각 서비스에 사용되는 다양한 네트워크 경로를 표시하는 네트워크 라우팅 다이어그램입니다.

- 필요한 경우 변경 및 롤백을 구현하는 단계가 있는 배포 계획입니다.

- 각 Office 365 및 네트워크 서비스를 테스트하기 위한 테스트 계획입니다.

- 인바운드 및 아웃바운드 서비스의 프로덕션 경로에 대한 문서 유효성 검사를 완료했습니다.

- 가용성 테스트를 포함하여 테스트 네트워크 세그먼트 전체에서 완료된 테스트입니다.

전체 배포 계획 및 테스트 계획을 실행할 수 있을 만큼 긴 정전 기간을 선택하고 문제 해결에 어느 정도 시간이 있으며 필요한 경우 롤백에 필요한 시간을 선택합니다.
  
> [!CAUTION]
> 인터넷과 ExpressRoute를 모두 통해 라우팅하는 복잡한 특성으로 인해 복잡한 라우팅 문제를 처리하기 위해 이 창에 버퍼 시간을 더 추가하는 것이 좋습니다.
  
### <a name="configure-qos-for-skype-for-business-online"></a>비즈니스용 Skype Online에 대한 QoS 구성

QoS는 비즈니스용 Skype Online에 대한 음성 및 모임 혜택을 얻는 데 필요합니다. ExpressRoute 네트워크 연결이 다른 Office 365 서비스 액세스를 차단하지 않는지 확인한 후 QoS를 구성할 수 있습니다. QoS 구성은 비즈니스용 [Skype Online의 ExpressRoute 및 QoS 문서에 설명되어 있습니다.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
## <a name="troubleshooting-your-implementation"></a>구현 문제 해결
<a name="troubleshooting"> </a>

구현 계획에서 누락된 경우 이 구현 가이드의 단계를 가장 먼저 살펴봐야 합니다. 가능한 경우 돌아가서 소규모 네트워크 테스트를 추가로 실행하여 오류를 복제하고 디버그합니다.
  
테스트 중에 실패한 인바운드 또는 아웃바운드 서비스를 식별합니다. 실패한 각 서비스에 대한 IP 주소 및 서브넷을 구체적으로 얻습니다. 문서에서 네트워크 토폴로지 다이어그램을 진행하고 라우팅의 유효성을 검사합니다. ExpressRoute 라우팅이 보급되는 위치의 유효성을 검사합니다. 가능한 경우 추적을 사용하여 정전 중에 라우팅을 테스트합니다.
  
각 고객 끝점에 대한 네트워크 추적을 사용하여 PSPing을 실행하고 원본 및 대상 IP 주소를 평가하여 예상대로 유효한지 확인합니다. 포트 25에 노출된 메일 호스트에 대해 텔넷을 실행하고 SNAT가 예상되는 경우 원래 원본 IP 주소를 숨기고 있는지 확인해야 합니다.
  
ExpressRoute 연결을 사용하여 Office 365를 배포하는 동안 ExpressRoute에 대한 네트워크 구성이 최적화되어 있으며 클라이언트 컴퓨터와 같은 네트워크의 다른 구성 요소도 최적화해야 합니다. 이 계획 가이드를 사용하여 누락된 단계를 해결하는 것 외에도 Office [365에](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) 대한 성능 문제 해결 계획을 작성했습니다.
  
다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/implementexpressroute365](https://aka.ms/implementexpressroute365)
  
## <a name="related-topics"></a>관련 항목

[Office 365 네트워크 연결 평가](assessing-network-connectivity.md) 
  
[Office 365용 Azure ExpressRoute](azure-expressroute.md)
  
[Office 365 연결에 대한 ExpressRoute 관리](managing-expressroute-for-connectivity.md)
  
[Office 365용 ExpressRoute를 사용한 라우팅](routing-with-expressroute.md)
  
[Office 365용 ExpressRoute를 사용한 네트워크 계획](network-planning-with-expressroute.md)
  
[Office 365 시나리오용 ExpressRoute에서 BGP 커뮤니티 사용](bgp-communities-in-expressroute.md)
  
[비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[비즈니스용 Skype Online의 네트워크 최적화](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[비즈니스용 Skype Online의 ExpressRoute 및 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[ExpressRoute를 사용하는 호출 흐름](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정](performance-tuning-using-baselines-and-history.md)
  
[Office 365 성능 문제 해결 계획](performance-troubleshooting-plan.md)
  
[Office 365 URL 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 네트워크 및 성능 조정](network-planning-and-performance.md)
