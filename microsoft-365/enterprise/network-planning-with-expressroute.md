---
title: Office 365용 ExpressRoute를 통한 네트워크 계획
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: 이 문서에서는 Azure ExpressRoute for Office 365 네트워크 계획에 활용하는 방법에 대해 설명합니다.
ms.openlocfilehash: e087afee52893b0be48e4024c619e3599f54338d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177066"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Office 365용 ExpressRoute를 통한 네트워크 계획

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

ExpressRoute for Office 365 네트워크와 Microsoft의 데이터 센터 간에 계층 3 연결을 제공합니다. 회로는 프런트 엔드 서버의 BGP(Border Gateway Protocol) 경로 Office 365 사용합니다. 프레미스 장치의 관점에서 볼 때 Azure ExpressRoute는 인터넷의 대안으로 볼 수 Office 365 TCP/IP 경로를 선택해야 합니다.
  
Azure ExpressRoute는 Microsoft의 데이터 센터 내에서 Office 365 지원되는 특정 기능 및 서비스 집합에 대한 직접 경로를 추가합니다. Azure ExpressRoute는 Microsoft 데이터 센터 또는 도메인 이름 확인과 같은 기본 인터넷 서비스에 대한 인터넷 연결을 대체하지 않습니다. Azure ExpressRoute 및 인터넷 회로를 보호하고 중복해야 합니다.
  
다음 표에서는 인터넷과 Azure ExpressRoute 연결 간의 몇 가지 차이점을 Office 365.

|**네트워크 계획의 차이점**|**인터넷 네트워크 연결**|**ExpressRoute 네트워크 연결**|
|:-----|:-----|:-----|
| 다음을 비롯한 필수 인터넷 서비스에 대한 액세스  <br/>  DNS 이름 확인  <br/>  인증서 해지 확인  <br/>  콘텐츠 배달 네트워크(CDN)  <br/> |예  <br/> |Microsoft 소유 DNS 및/또는 CDN 인프라에 대한 요청은 ExpressRoute 네트워크를 사용할 수 있습니다.  <br/> |
| 다음을 Office 365 서비스에 대한 액세스  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  비즈니스용 Skype Online  <br/>  Office 브라우저에서 실행  <br/>  Office 365 포털 및 인증  <br/> |예, 모든 응용 프로그램 및 기능  <br/> |예, [특정 응용 프로그램 및 기능](./urls-and-ip-address-ranges.md) <br/> |
|경계의 사내 보안  <br/> |예  <br/> |예  <br/> |
|고가용성 계획  <br/> |대체 인터넷 네트워크 연결로의 장애 조치(failover)  <br/> |대체 ExpressRoute 연결로의 장애 조치(failover)  <br/> |
|예측 가능한 네트워크 프로필과 직접 연결  <br/> |아니요  <br/> |예  <br/> |
|IPv6 연결.  <br/> |예  <br/> |예  <br/> |

네트워크 계획 지침에 대한 자세한 내용은 아래 제목을 확장합니다. 또한 심층 교육을 위한 10부분의 [Azure ExpressRoute](https://channel9.msdn.com/series/aer) Office 365 기록했습니다.

## <a name="existing-azure-expressroute-customers"></a>기존 Azure ExpressRoute 고객

기존 Azure ExpressRoute 회로를 사용 중일 때 이 회로에 Office 365 연결을 추가하는 경우 회로의 수, 위치 및 회로 크기를 확인하여 회로가 Office 365 요구 사항을 충족하는지 확인해야 합니다. 대부분의 고객은 추가 대역폭이 필요하며 많은 고객에게는 추가 회로가 필요합니다.
  
기존 Azure ExpressRoute 회로를 Office 365 액세스하려면 경로 [](/azure/expressroute/how-to-routefilter-portal) 필터를 구성하여 Office 365 서비스에 액세스할 수 있도록 합니다.
  
Azure ExpressRoute 구독은 고객 중심입니다. 즉, 구독은 고객과 통합됩니다. 고객은 여러 Azure ExpressRoute 회로를 사용할 수 있으며 이러한 회로를 통해 많은 Microsoft 클라우드 리소스에 액세스할 수 있습니다. 예를 들어 중복 Azure ExpressRoute 회로 쌍을 통해 Azure 호스트된 가상 컴퓨터, Office 365 테넌트 및 Office 365 프로덕션 테넌트에 액세스하게 선택할 수 있습니다.
  
이 표에서는 회로를 통해 구현할 수 있는 두 가지 유형의 피어링 관계에 대해 간략하게 설명합니다.

|**피어링 관계**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**서비스** <br/> |IaaS: Azure 가상 컴퓨터  <br/> |PaaS: Azure 공용 서비스  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|연결 시작**** <br/> |고객-Microsoft  <br/> Microsoft-to-Customer  <br/> |고객-Microsoft  <br/> Microsoft-to-Customer  <br/> |
|**QoS 지원** <br/> |QoS 없음  <br/> |QoS<sup>1</sup> <br/> |

<sup>1</sup> QoS는 현재 비즈니스용 Skype 지원됩니다.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Azure ExpressRoute에 대한 대역폭 계획

모든 Office 365 고객은 각 위치의 사용자 수, 각 Office 365 응용 프로그램의 활성 상태 및 기타 요소(예: 사내 또는 하이브리드 장비 및 네트워크 보안 구성 사용)에 따라 고유한 대역폭 요구가 있습니다.
  
대역폭이 너무 적을 경우 정체, 데이터 다시 전송 및 예측할 수 없는 지연이 됩니다. 대역폭이 너무 많을 경우 불필요한 비용이 야기됩니다. 기존 네트워크에서 대역폭은 회로에서 사용 가능한 헤드룸의 양을 백분율로 지칭하기도 합니다. 헤드룸이 10%이면 정체가 야기될 수 있으며 일반적으로 80%의 헤드룸이 있는 것은 불필요한 비용을 의미하는 것입니다. 일반적인 헤드룸 대상 할당은 20%에서 50%까지입니다.
  
올바른 수준의 대역폭을 찾으면 기존 네트워크 소비를 테스트하는 것이 가장 좋습니다. 이는 모든 네트워크 구성 및 응용 프로그램이 고유한 방식으로 사용 현황을 측정할 수 있는 유일한 방법일 뿐입니다. 측정할 때 네트워크 요구 사항을 이해하기 위해 총 대역폭 소비, 대기 시간 및 TCP 정체에 주의해야 합니다.
  
모든 네트워크 응용 프로그램을 포함하는 예상 기준이 있는 경우 Office 365 조직의 사용자 프로필로 구성된 소규모 그룹과 함께 파일럿을 수행하여 실제 사용 현황을 결정하고 두 측정값을 사용하여 각 사무실 위치에 필요한 대역폭의 양을 예측합니다. 테스트에서 발견된 대기 시간 또는 TCP 정체 문제가 있는 경우 SSL 암호 해독/검사와 같은 집중적인 네트워크 Office 365 제거하거나 사용자와 더 가깝게 발신을 이동해야 할 수 있습니다.
  
권장되는 네트워크 처리 유형에 대한 모든 권장 사항은 ExpressRoute 및 인터넷 회로에 모두 적용됩니다. 성능 조정 사이트에 대한 나머지 지침도 [마찬가지입니다.](./network-planning-and-performance.md)
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Azure ExpressRoute에 보안 컨트롤 적용 Office 365 시나리오

Azure ExpressRoute 연결 보안은 인터넷 연결 보안과 동일한 원칙으로 시작됩니다. 많은 고객이 자신의 사내 네트워크와 기타 Microsoft 클라우드에 연결하는 ExpressRoute 경로를 따라 네트워크 및 경계 Office 365 배포하기로 선택했습니다. 이러한 컨트롤에는 방화벽, 응용 프로그램 proxies, 데이터 누출 방지, 침입 감지, 침입 방지 시스템 등이 포함됩니다. 대부분의 경우 고객은 Microsoft로 이동하는 사내에서 시작된 트래픽과 Microsoft에서 고객 사내 네트워크로 시작된 트래픽과 일반 인터넷 대상으로 이동하는 트래픽에 서로 다른 수준의 제어를 적용합니다.
  
다음은 배포하기로 선택한 [ExpressRoute](/azure/expressroute/expressroute-connectivity-models) 연결 모델과 보안을 통합하는 몇 가지 예입니다.

|**ExpressRoute 통합 옵션**|**네트워크 보안 경계 모델**|
|:-----|:-----|
|클라우드 교환에 공동 위치  <br/> |ExpressRoute 연결이 설정되는 공동 위치 시설에 새 보안/경계 인프라를 설치하거나 기존 보안/경계 인프라를 활용합니다.  <br/> 공동 위치 기능을 사용하여 공동 위치 시설에서 사내 보안/경계 인프라로의 라우팅/상호 연결 및 후방 우회 연결을 전적으로 활용합니다.  <br/> |
|지점 대 점 이더넷  <br/> |기존온-프레미스 보안/경계 인프라 위치에서 지점 대 지점 ExpressRoute 연결을 종료합니다.  <br/> ExpressRoute 경로와 관련한 새 보안/경계 인프라를 설치하고 지점 대 지점 연결을 종료합니다.  <br/> |
|모든 IPVPN  <br/> |사용자 연결을 위해 ExpressRoute에 사용되는 IPVPN으로 유입되는 모든 위치에서 기존 Office 365 활용합니다.  <br/> 보안/경계 역할을 하도록 지정된 특정 Office 365 위치에 대한 ExpressRoute에 사용되는 IPVPN 헤어피입니다.  <br/> |

일부 서비스 공급자는 Azure ExpressRoute와의 통합 솔루션의 일부로 관리되는 보안/경계 기능을 제공합니다.
  
Office 365 연결에 대해 ExpressRoute에 사용되는 네트워크/보안 경계 옵션의 토폴로지 배치를 고려할 때 다음 사항을 추가로 고려해야 합니다.
  
- 깊이 및 유형 네트워크/보안 컨트롤은 사용자 환경의 성능 및 확장성에 Office 365 있습니다.

- 아웃바운드(On-premises- \> Microsoft) 및 인바운드(Microsoft-on-premises)[활성화된 경우] 흐름의 요구 사항이 \> 다를 수 있습니다. 이는 일반 인터넷 대상에 대한 아웃바운드와 다를 수 있습니다.

- Office 365/프로토콜 및 필요한 IP 서브넷에 대한 요구 사항은 트래픽이 ExpressRoute를 통해 라우팅되는지 또는 인터넷을 Office 365 동일합니다.

- 고객 네트워크/보안 제어의 토공학적 배치는 사용자와 Office 365 서비스 간의 궁극적인 종단 간 네트워크를 결정하며 네트워크 대기 시간 및 정체에 큰 영향을 줄 수 있습니다.

- 고객은 중복, 고가용성 및 재해 복구에 대한 모범 사례에 따라 Office 365 ExpressRoute와 함께 사용할 수 있도록 보안/경계 토폴로지 설계를 권장합니다.

다음은 다양한 Azure ExpressRoute 연결 옵션과 위에서 설명한 경계 보안 모델을 비교하는 Woodgrove Bank의 예입니다.
  
### <a name="example-1-securing-azure-expressroute"></a>예제 1: Azure ExpressRoute 보안
  
Woodgrove Bank는 Azure ExpressRoute를 구현하는 것을 고려 중입니다. Office 365 [ExpressRoute를](routing-with-expressroute.md) 사용한 라우팅에 대한 최적의 아키텍처를 계획한 후 위의 지침을 사용하여 대역폭 요구 사항을 파악한 후 경계 보안에 가장 적합한 방법을 결정하고 있습니다.
  
여러 대륙에 위치가 있는 다국적 조직인 Woodgrove의 경우 보안은 모든 경계에 걸쳐 있어야 합니다. Woodgrove에 대한 최적의 연결 옵션은 각 대륙에 있는 직원들의 요구를 충족하기 위해 전 세계 여러 피어링 위치와의 다중 지점 연결입니다. 각 대륙은 대륙 내의 중복 Azure ExpressRoute 회로를 포함하며 보안은 이러한 모든 회로에 걸쳐야 합니다.
  
Woodgrove의 기존 인프라는 안정적이며 추가 작업을 처리할 수 있습니다. 따라서 Woodgrove Bank는 Azure ExpressRoute 및 인터넷 경계 보안을 위한 인프라를 사용할 수 있습니다. 그렇지 않은 경우 Woodgrove는 기존 장비를 보완하거나 다른 유형의 연결을 처리하기 위해 추가 장비를 구매할 수 있습니다.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Azure ExpressRoute를 사용하여 고가용성 및 장애 조치
<a name="BKMK_high-availability"> </a>

ExpressRoute를 사용하여 각 시작에서 ExpressRoute 공급자로 두 개 이상의 활성 회로를 프로비전하는 것이 좋습니다. 고객에게 오류가 발생하면 한 쌍의 활성/활성 ExpressRoute 회로를 프로비저닝하여 쉽게 방지할 수 있는 가장 일반적인 장소입니다. 또한 인터넷을 통해만 사용할 수 있는 여러 Office 365 인터넷 회로가 2개 이상 권장됩니다.
  
네트워크의 시작 지점 내에서는 사람들이 가용성을 인식하는 방법에 중요한 역할을 하는 여러 다른 장치 및 회로가 있습니다. 연결 시나리오의 이러한 부분은 ExpressRoute 또는 Office 365 SLA에서 다루지 않지만 조직의 사람들이 인식하는 종단에서 서비스 가용성까지 중요한 역할을 합니다.
  
특정 구성 요소 중 하나에 Office 365 오류가 서비스를 사용하는 사용자 경험에 영향을 줄 경우 영향을 받는 전체 사용자 비율을 제한하는 방법을 찾아야 합니다. 장애 조치(failover) 모드가 작동상 복잡한 경우 복구에 오랜 시간이 들이는 사용자 환경을 고려하고 작동이 단순하고 자동화된 장애 조치(failover) 모드를 찾아야 합니다.
  
네트워크 외부에서 Office 365, ExpressRoute 및 ExpressRoute 공급자 모두 가용성 수준이 다릅니다.
  
### <a name="service-availability"></a>서비스 가용성
  
- Office 365 서비스에는 개별 서비스에 대한 [](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)사용 시간 및 가용성 메트릭이 포함된 잘 정의된 서비스 수준 계약이 포함됩니다. 이러한 Office 365 가용성 수준을 유지할 수 있는 한 가지 이유는 전역 Microsoft 네트워크를 사용하여 여러 Microsoft 데이터 센터 간에 개별 구성 요소가 원활하게 장애 조치(failover)할 수 있는 기능입니다. 이 장애 조치(failover)는 데이터 센터 및 네트워크에서 여러 인터넷 시작 지점으로 확장하며, 서비스를 사용하는 사용자 관점에서 장애 조치(failover)를 원활하게 할 수 있습니다.

- ExpressRoute는 Microsoft 네트워크 에지와 ExpressRoute 공급자 또는 파트너 인프라 간의 개별 전용 회로에서 [99.9%의](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) 가용성 SLA를 제공합니다. 이러한 서비스 수준은 각 피어링 위치에 있는 [](/azure/expressroute/expressroute-introduction) 중복 Microsoft 장비와 네트워크 공급자 장비 간의 두 개의 독립적인 상호 연결로 구성된 ExpressRoute 회로 수준에서 적용됩니다.

### <a name="provider-availability"></a>공급자 가용성
  
- Microsoft의 서비스 수준 정렬은 ExpressRoute 공급자 또는 파트너에서 중지됩니다. 또한 가용성 수준에 영향을 줄 수 있는 선택을 할 수 있는 첫 번째 장소입니다. ExpressRoute 공급자가 각 Microsoft 피어링 위치에서 네트워크 경계와 공급자 연결 간에 제공하는 아키텍처, 가용성 및 탄력성 특성을 면밀하게 평가해야 합니다. 중복성, 피어링 장비, 통신 사업자 제공 WAN 회로 및 NAT 서비스 또는 관리되는 방화벽과 같은 추가 가치 추가 서비스의 논리적 및 물리적 측면 모두에 주의해야 합니다.

### <a name="designing-your-availability-plan"></a>가용성 계획 디자인
  
고가용성 및 탄력성을 계획하고 디자인하여 최종 연결 시나리오에 대한 계획을 세우고 Office 365. 디자인에는 다음이 포함되어야 합니다.
  
- 인터넷 및 ExpressRoute 회로를 모두 포함하여 단일 오류 지점이 없습니다.

- 대부분의 예상 오류 모드에 영향을 주는 사용자 수 및 영향을 받는 기간 최소화

- 대부분의 예상 오류 모드에서 단순하고 반복 가능하고 자동 복구 프로세스를 최적화합니다.

- 과도하게 저하 없이 중복 경로를 통해 네트워크 트래픽 및 기능에 대한 전체 요구를 충족할 수 있습니다.

연결 시나리오에는 여러 독립 및 활성 네트워크 경로에 최적화된 네트워크 토폴로지가 포함되어야 Office 365. 이렇게 하면 개별 장치 또는 장비 수준에서의 중복에만 최적화된 토폴로지보다 종단-종단식 가용성이 향상됩니다.
  
> [!TIP]
> 사용자가 여러 대륙 또는 지리적 지역에 분산되어 있으며 이러한 각 위치가 중복된 WAN 회로를 통해 단일 ExpressRoute 회로가 있는 단일 사내 위치에 연결하는 경우 사용자는 서로 다른 지역을 가장 가까운 피어링 위치에 연결하는 독립 ExpressRoute 회로를 포함하는 네트워크 토폴로지 디자인보다 종단 투 엔드 서비스 가용성이 감소합니다.
  
각 회로가 다른 지리적 피어링 위치와 연결하여 ExpressRoute 회로를 두 개 이상 프로비전하는 것이 좋습니다. 다른 사람들이 다른 서비스에 ExpressRoute 연결을 사용할 모든 지역에 대해 이 활성 활성 회로 쌍을 프로비전해야 Office 365 합니다. 이렇게 하면 데이터 센터 또는 피어링 위치와 같은 주요 위치에 영향을 주는 재해가 발생 하는 동안 각 지역이 연결된 상태로 유지될 수 있습니다. 이러한 트래픽을 활성/활성으로 구성하면 최종 사용자 트래픽을 여러 네트워크 경로에 분산할 수 있습니다. 이렇게 하면 장치 또는 네트워크 장비가 정전되는 동안 영향을 받는 사용자 범위가 줄어듭니다.
  
인터넷과 함께 단일 ExpressRoute 회로를 백업으로 사용하지 않는 것이 좋습니다.
  
### <a name="example-2-failover-and-high-availability"></a>예제 2: 장애 조치(Failover) 및 고가용성
  
Woodgrove Bank의 다중 지역 디자인은 라우팅, 대역폭, 보안에 대한 검토를 거치며 이제 고가용성 검토를 거치야 합니다. Woodgrove는 고가용성에 대해 세 가지 범주를 다루고 있습니다. 탄력성, 안정성 및 중복성.
  
복구를 통해 Woodgrove는 오류로부터 빠르게 복구할 수 있습니다. 안정성을 통해 Woodgrove는 시스템 내에서 일관된 결과를 제공할 수 있습니다. 중복을 통해 Woodgrove는 하나 이상의 미러된 인프라 인스턴스 간에 이동할 수 있습니다.
  
각 에지 구성 내에서 Woodgrove에는 중복 방화벽, Proxies 및 IDS가 있습니다. 북아메리카의 경우 Woodgrove는 다른 에지 구성이 다른 에지 데이터 센터에 있으며, 버진아 데이터 센터의 다른 에지 구성이 있습니다. 각 위치에 중복된 장비는 해당 위치로의 탄력을 제공합니다.
  
Woodgrove Bank의 네트워크 구성은 몇 가지 주요 원칙을 기반으로 합니다.
  
- 각 지리적 지역 내에 여러 Azure ExpressRoute 회로가 있습니다.

- 지역 내의 각 회로는 지역 내의 모든 네트워크 트래픽을 지원할 수 있습니다.

- 라우팅은 가용성, 위치 등에 따라 경로 중 하나 또는 다른 경로를 명확하게 선호합니다.

- Azure ExpressRoute 회로 간의 장애 조치(failover)는 Woodgrove에 필요한 추가 구성이나 작업 없이 자동으로 수행됩니다.

- Woodgrove에서 요구하는 추가 구성이나 작업을 수행하지 않으면 인터넷 회로 간의 장애 조치(failover)가 자동으로 수행됩니다.

이 구성에서는 물리적 및 가상 수준의 중복을 통해 Woodgrove Bank는 안정적인 방식으로 로컬 탄력성, 지역별 탄력성 및 글로벌 탄력성을 제공할 수 있습니다. Woodgrove는 지역당 단일 Azure ExpressRoute 회로를 평가하고 인터넷으로 장애 조치(fail over)할 가능성을 평가한 후에 이 구성을 선택했습니다.
  
Woodgrove가 지역별로 여러 Azure ExpressRoute 회로를 사용할 수 없는 경우 북미에서 시작된 트래픽을 아시아 태평양의 Azure ExpressRoute 회로로 라우팅하면 받아들일 수 없는 대기 시간이 추가되어 필요한 DNS 전달자 구성이 복잡해집니다.
  
인터넷을 백업 구성으로 활용하는 것은 권장되지 않습니다. 이로 인해 Woodgrove의 안정성 원칙이 끊어지며 연결을 사용하는 환경이 불일치하게 됩니다. 또한 구성된 BGP 광고, NAT 구성, DNS 구성 및 프록시 구성을 고려하여 장애 조치(failover)를 위해 수동 구성이 필요합니다. 이로 인해 장애 조치(failover) 복잡성이 추가되어 복구 시간이 증가하고 관련된 단계를 진단하고 문제를 해결할 수 있는 능력이 감소합니다.
  
여전히 트래픽 관리 또는 Azure ExpressRoute를 계획하고 구현하는 방법에 대한 질문이 있나요? 나머지 네트워크 및 [성능](./network-planning-and-performance.md) 지침 또는 [Azure ExpressRoute FAQ를 읽어 읽습니다.](/azure/expressroute/expressroute-faqs)
  
## <a name="working-with-azure-expressroute-providers"></a>Azure ExpressRoute 공급자 사용
<a name="BKMK_high-availability"> </a>

대역폭, 대기 시간, 보안 및 고가용성 계획에 따라 회로 위치를 선택하세요. 회로를 두는 최적의 위치를 알고 나면 지역별로 현재 공급자 목록을 [검토합니다.](/azure/expressroute/expressroute-locations)
  
공급자 또는 공급자와 함께 최상의 연결 옵션, 지점 대 지점, 다중 지점 또는 호스트를 선택합니다. 대역폭 및 기타 중복 구성 요소가 라우팅 및 고가용성 디자인을 지원하는 한 연결 옵션을 혼합하고 일치할 수 있습니다.
  
다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>관련 항목
<a name="BKMK_high-availability"> </a>

[Office 365 네트워크 연결 평가](assessing-network-connectivity.md) 
  
[Office 365용 Azure ExpressRoute](azure-expressroute.md)
  
[Office 365 연결에 대한 ExpressRoute 관리](managing-expressroute-for-connectivity.md)
  
[Office 365용 ExpressRoute를 사용한 라우팅](routing-with-expressroute.md)
  
[Office 365용 ExpressRoute 구현](implementing-expressroute.md)
  
[다른 시나리오에 ExpressRoute에서 BGP Office 365 사용](bgp-communities-in-expressroute.md)
  
[비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[비즈니스용 Skype Online의 네트워크 최적화](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[비즈니스용 Skype Online의 ExpressRoute 및 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[ExpressRoute를 사용하는 호출 흐름](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정](performance-tuning-using-baselines-and-history.md)
  
[Office 365 성능 문제 해결 계획](performance-troubleshooting-plan.md)
  
[Office 365 URL 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 네트워크 및 성능 조정](network-planning-and-performance.md)
  
[Office 365 끝점 FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)