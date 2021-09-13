---
title: Office 365용 ExpressRoute를 사용한 라우팅
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e1da26c6-2d39-4379-af6f-4da213218408
description: 이 문서에서는 Azure ExpressRoute 라우팅 요구 사항, 회로 및 라우팅 도메인에 대해 Office 365.
ms.openlocfilehash: d157515f60a68a46b033571a0fd39e6a5711b884
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215695"
---
# <a name="routing-with-expressroute-for-office-365"></a>Office 365용 ExpressRoute를 사용한 라우팅

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Azure ExpressRoute를 사용하여 Office 365 라우팅 트래픽을 제대로 이해하려면 핵심 [ExpressRoute](/azure/expressroute/expressroute-routing) 라우팅 요구 사항과 [ExpressRoute](/azure/expressroute/expressroute-circuit-peerings)회로 및 라우팅 도메인을 확고하게 파악해야 합니다. 이러한 기본은 고객이 사용하는 ExpressRoute를 Office 365 기본을 제공합니다.
  
위의 문서에서 이해해야 할 몇 가지 주요 항목은 다음과 같습니다.
  
- ExpressRoute 회로는 특정 물리적 인프라에 매핑되지 않지만 Microsoft 및 사용자 대신 피어링 공급자가 단일 피어링 위치에서 만든 논리적 연결입니다.

- ExpressRoute 회로와 고객 s-key 간에는 1:1 매핑이 있습니다.

- 각 회로는 두 개의 독립적인 피어링 관계(Azure Private 피어링 및 Microsoft 피어링)를 지원할 수 있습니다. Office 365 Microsoft 피어링이 필요합니다.

- 각 회로에는 모든 피어링 관계에서 공유되는 고정 대역폭이 있습니다.

- ExpressRoute 회로에 사용할 공용 IPv4 주소 및 공용 AS 번호는 소유가 사용자로 확인되거나 주소 범위의 소유자가 단독으로 사용자에게 할당해야 합니다.

- 가상 ExpressRoute 회로는 전 세계적으로 중복되고 표준 BGP 라우팅 관행을 따르게 될 것입니다. 따라서 활성/활성 구성에서 공급자에 대해 에스가당 두 개의 물리적 회로를 권장하는 것입니다.

지원되는 서비스, 비용 및 구성 세부 정보에 대한 자세한 내용은 [FAQ](/azure/expressroute/expressroute-faqs) 페이지를 참조하세요. Microsoft 피어링 지원을 제공하는 연결 공급자 목록에 대한 자세한 내용은 [ExpressRoute 위치](/azure/expressroute/expressroute-locations) 문서를 참조하세요. 또한 개념을 보다 철저하게 설명할 수 있도록 채널 9에 Office 365 [교육용 10부분의 Azure ExpressRoute를](https://channel9.msdn.com/series/aer) 기록했습니다.
  
## <a name="ensuring-route-symmetry"></a>경로 대칭 보장

Office 365 프런트 엔드 서버는 인터넷 및 ExpressRoute에서 모두 액세스할 수 있습니다. 이러한 서버는 둘 다 사용 가능한 경우 ExpressRoute 회로를 통해 다시 사내로 라우팅하는 것을 선호합니다. 이 때문에 네트워크의 트래픽이 인터넷 회로를 통해 라우팅하는 것을 선호하는 경우 경로 비대칭성 경로가 있습니다. 비대칭 경로는 상태 패킷 검사를 수행하는 장치가 아웃바운드 패킷이 팔로우하는 아웃바운드 패킷과 다른 경로를 따르는 반환 트래픽을 차단할 수 있기 때문에 문제가 됩니다.
  
인터넷 또는 ExpressRoute를 Office 365 연결에 대한 연결을 시작하는지 여부에 관계없이 원본은 공개적으로 라우팅 가능한 주소가 되어야 합니다. 많은 고객이 Microsoft와 직접 피어링하는 경우 고객 간에 중복이 가능한 개인 주소를 가지는 것은 불가능합니다.
  
다음은 Office 365 네트워크로의 통신이 시작되는 시나리오입니다. 네트워크 디자인을 단순화하려면 인터넷 경로를 통해 라우팅하는 것이 좋습니다.
  
- Exchange Online 테넌트에서 Exchange Online 또는 SharePoint Online에서 SharePoint 호스트로 보낸 온라인 메일과 같은 SMTP 서비스입니다. SMTP 프로토콜은 ExpressRoute 회로를 통해 공유되는 경로 prefix와 ExpressRoute를 통해 광고하는 사내 SMTP 서버를 통해 공유되는 것보다 Microsoft 네트워크 내에서 더 광범위하게 사용됩니다.

- 로그인에 대한 암호 유효성 검사 중 ADFS.

- [Exchange Server 하이브리드 배포](/exchange/exchange-hybrid).

- [SharePoint 하이브리드 검색을 검색합니다.](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)

- [SharePoint 하이브리드 BCS.](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)

- [비즈니스용 Skype 및/또는](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) [비즈니스용 Skype.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)

- [비즈니스용 Skype 클라우드 커넥터](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Microsoft가 이러한 양방향 트래픽 흐름을 위해 네트워크로 다시 라우팅하려면 BGP 경로를 Microsoft와 공유해야 합니다. ExpressRoute를 통해 Microsoft에 경로 prefix를 보급할 때 다음과 같은 모범 사례를 따라야 합니다.

1) 공용 인터넷 및 ExpressRoute를 통해 동일한 공용 IP 주소 경로 선두를 보급하지 않습니다. ExpressRoute를 통해 Microsoft에 대한 IP BGP 경로 Prefix 광고는 인터넷에 보급되지 않은 범위에서만 광고를 표시하는 것이 좋습니다. 사용 가능한 IP 주소 공간으로 인해 이를 달성할 수 없는 경우 ExpressRoute를 통해 인터넷 회로보다 더 구체적인 범위를 보급해야 합니다.

2) ExpressRoute 회로당 별도의 NAT IP 풀을 사용하며 인터넷 회로와 구분합니다.

3) Microsoft에 보급되는 경로는 ExpressRoute를 통해 경로가 네트워크에 보급되는 경로뿐만 아니라 Microsoft 네트워크의 모든 서버에서 네트워크 트래픽을 유인합니다. 팀에서 라우팅 시나리오를 정의하고 잘 이해할 수 있는 서버에만 경로를 보급합니다. 네트워크에서 여러 ExpressRoute 회로 각각에 별도의 IP 주소 경로 prefix를 보급합니다.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>ExpressRoute를 통해 라우팅되는 응용 프로그램 및 기능 결정

Microsoft 피어 라우팅 도메인을 사용하여 피어링 관계를 구성하고 적절한 액세스가 승인되면 ExpressRoute를 통해 사용할 수 있는 모든 PaaS 및 SaaS 서비스를 볼 수 있습니다. ExpressRoute용으로 Office 365 서비스는 [BGP](./bgp-communities-in-expressroute.md) 커뮤니티 또는 경로 필터로 [관리할 수 있습니다.](/azure/expressroute/how-to-routefilter-portal)
  
Microsoft 피어링을 사용하여 사용할 수 있는 각 Office 365 [](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 기능은 응용 프로그램 유형 및 FQDN에 따라 Office 365 끝점 문서에 나열됩니다. 테이블에서 FQDN을 사용하는 이유는 고객이 PAC 파일 또는 기타 프록시 구성을 사용하여 트래픽을 [](./managing-office-365-endpoints.md) 관리할 수 있도록 허용하기 위해 PAC 파일과 같은 Office 365 끝점 관리 가이드를 참조하세요.
  
경우에 따라 하나 이상의 하위 FQDNS가 상위 수준 와일드카드 도메인과 다르게 보급되는 와일드카드 도메인을 사용했습니다. 일반적으로 와일드카드가 ExpressRoute 및 인터넷에 모두 보급되는 긴 서버 목록을 나타내고 대상의 작은 하위 집합이 인터넷에만 보급되거나 반대로 표시될 때 발생합니다. 차이점이 있는 위치를 이해하기 위해 아래 표를 참조하세요.
  
이 표에는 인터넷에만 보급되는 하위 FQDNS와 함께 인터넷 및 Azure ExpressRoute 둘 다에 보급되는 와일드카드 FQDNS가 표시됩니다.

|**ExpressRoute 및 인터넷 회로에 보급된 와일드카드 도메인**|**인터넷 회로에만 보급되는 하위 FQDN**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

일반적으로 PAC 파일은 보급된 끝점을 ExpressRoute로 직접 전송하고 다른 모든 네트워크 요청을 프록시로 보내기 위한 것입니다. 이와 같이 PAC 파일을 구성하는 경우 PAC 파일을 다음 순서로 작성합니다.
  
1. 위의 표의 열 2에 있는 하위 FQDNS를 PAC 파일 맨 위에 포함하여 프록시로 트래픽을 전송합니다. Office 365 끝점 관리에 대한 문서에서 사용할 수 있는 샘플 PAC 파일을 Office 365 [있습니다.](./managing-office-365-endpoints.md)

2. 첫 번째 섹션 아래의 이 문서에서 ExpressRoute로 보급된 모든 FQDNs를 포함하여 트래픽을 ExpressRoute 회로로 직접 전송합니다. [](./urls-and-ip-address-ranges.md)

3. 이러한 두 항목 아래에 다른 네트워크 끝점 또는 규칙을 포함하여 프록시로 트래픽을 전송합니다.

이 표에는 Azure ExpressRoute 및 인터넷 회로에 보급되는 하위 FQDNS와 함께 인터넷 회로에만 보급되는 와일드카드 도메인이 표시됩니다. 위의 PAC 파일의 경우 아래 표의 열 2에 있는 FQDNS가 참조되는 링크에서 ExpressRoute로 보급되는 것으로 표시되어 파일의 두 번째 항목 그룹에 포함됩니다.

|**인터넷 회로에만 보급된 와일드카드 도메인**|**ExpressRoute 및 인터넷 회로에 보급되는 하위 FQDN**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover- \<tenant\> .outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>인터넷 Office 365 ExpressRoute를 통해 트래픽 라우팅

선택한 Office 365 응용 프로그램으로 라우팅하려면 여러 가지 주요 요소를 결정해야 합니다.
  
1. 응용 프로그램에 필요한 대역폭의 정도입니다. 기존 사용 샘플링은 조직에서 이를 결정하는 유일한 신뢰할 수 있는 방법입니다.

2. 네트워크 트래픽이 네트워크를 떠날 위치 성능에 영향을 미치기 때문에 연결에 대한 네트워크 Office 365 최소화해야 합니다. 이 비즈니스용 Skype 음성 및 비디오를 사용하게 되어 네트워크 대기 시간이 짧아질 수 있습니다.

3. 네트워크 위치의 일부 또는 전체에서 ExpressRoute를 사용하려는 경우

4. 선택한 네트워크 공급자가 ExpressRoute를 제공하는 위치

이러한 질문에 대한 답변을 확인한 후 대역폭 및 위치 요구 사항을 충족하는 ExpressRoute 회로를 프로비전할 수 있습니다. 네트워크 계획 지원에 대한 [](./network-planning-and-performance.md) 자세한 내용은 Office 365 네트워크 조정 가이드 및 사례 연구에서 Microsoft가 네트워크 성능 계획을 처리하는 [방법을 참조하세요.](https://aka.ms/tunemsit)
  
### <a name="example-1-single-geographic-location"></a>예 1: 단일 지리적 위치
  
이 예는 지리적 위치가 하나인 Trey Research라는 소설 회사에 대한 시나리오입니다.
  
Trey Research의 직원은 보안 부서에서 회사 네트워크와 ISP 사이에 있는 아웃바운드 proxies 쌍에서 명시적으로 허용하는 인터넷의 서비스 및 웹 사이트에만 연결할 수 있습니다.
  
Trey Research는 Azure ExpressRoute를 Office 365 계획하고 콘텐츠 배달 네트워크로 전송되는 트래픽과 같은 일부 트래픽은 Office 365 위해 ExpressRoute를 통해 라우팅할 수 없습니다. 모든 트래픽은 기본적으로 프록시 장치로 이미 라우팅되기 때문에 이러한 요청은 이전과 계속 작동합니다. Trey Research는 Azure ExpressRoute 라우팅 요구 사항을 충족할 수 있는지 확인한 후 회로를 만들고, 라우팅을 구성하고, 새 ExpressRoute 회로를 가상 네트워크에 연결합니다. 기본 Azure ExpressRoute 구성이 적용된 후 Trey Research는 게시하는 #2 [PAC](./managing-office-365-endpoints.md) 파일을 사용하여 사용자별 연결을 위한 직접 ExpressRoute를 통해 Office 365 라우팅합니다.
  
다음 다이어그램과 같이 Trey Research는 라우팅 및 아웃바운드 프록시 구성 변경의 조합을 사용하여 인터넷을 통해 Office 365 트래픽 및 ExpressRoute를 통해 트래픽의 하위 집합을 라우팅하기 위한 요구 사항을 충족할 수 있습니다.
  
1. 게시하는 [#2 PAC](./managing-office-365-endpoints.md) 파일을 사용하여 Azure ExpressRoute에 대한 별도의 인터넷 발신 지점을 통해 트래픽을 Office 365.

2. 클라이언트는 Trey Research의 Proxies에 대한 기본 경로로 구성됩니다.

이 예제 시나리오에서 Trey Research는 아웃바운드 프록시 장치를 사용합니다. 마찬가지로, azure ExpressRoute를 사용하지 않는 Office 365 잘 알려진 높은 볼륨 끝점으로 이동하는 트래픽을 검사하는 비용을 기반으로 이 기술을 사용하여 트래픽을 라우팅할 수 있습니다.
  
Exchange Online, SharePoint Online 및 비즈니스용 Skype Online에 대한 가장 높은 볼륨 FQDNS는 다음과 같습니다.
  
![ExpressRoute 고객 에지 네트워크.](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com outlook.office.com

- \<tenant-name\>.sharepoint.com, \<tenant-name\> -my.sharepoint.com, \<tenant-name\> - \<app\> .sharepoint.com

- \*. Lync.com 비 TCP 트래픽에 대한 IP 범위와 함께 사용할 수 있습니다.

- \*broadcast.officeapps.live.com, \* excel.officeapps.live.com, \* \* onenote.officeapps.live.com, powerpoint.officeapps.live.com, \* \* view.officeapps.live.com, visio.officeapps.live.com, \* word-edit.officeapps.live.com, \* word-view.officeapps.live.com, office.live.com

자세한 내용은 [에서](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy) 프록시 설정을 배포 및 관리하고 Windows 8 프록시에 의해 Office 365 설정이 스로틀되지 [않는지 확인합니다.](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)
  
단일 ExpressRoute 회로를 사용할 경우 Trey Research에 대한 고가용성은 없습니다. ExpressRoute 연결을 서비스하는 Trey의 중복된 에지 디바이스 쌍에서 장애 조치(failover)할 추가 ExpressRoute 회로가 없습니다. 따라서 Trey Research는 인터넷으로 장애 조치(fail over)를 할 때 수동 재구성 및 경우에 따라 새 IP 주소를 필요로 하게 됩니다. Trey가 고가용성을 추가하려는 경우 가장 간단한 해결 방법은 각 위치에 대해 ExpressRoute 회로를 추가하고 활성/활성 방식으로 회로를 구성하는 것입니다.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>여러 위치로 Office 365 ExpressRoute 라우팅

마지막 시나리오에서는 ExpressRoute를 Office 365 트래픽을 라우팅하는 것이 훨씬 더 복잡한 라우팅 아키텍처의 토대입니다. 위치 수에 관계없이 해당 위치가 있는 대륙 수, ExpressRoute 회로 수 등 일부 트래픽을 인터넷으로 라우팅할 수 있으며 ExpressRoute를 통해 일부 트래픽이 필요합니다.
  
여러 지역에서 여러 위치를 사용하는 고객을 위해 답변해야 하는 추가 질문은 다음과 같습니다.
  
1. 모든 위치에 ExpressRoute 회로가 필요한가요? 비즈니스용 Skype Online을 사용 중이거나 SharePoint Online 또는 Exchange Online에 대한 대기 시간 민감도가 우려되는 경우 각 위치에서 중복된 쌍의 Active/Active ExpressRoute 회로를 사용하는 것이 좋습니다. 자세한 비즈니스용 Skype 미디어 품질 및 네트워크 연결 가이드를 참조하세요.

2. ExpressRoute 회로를 특정 지역에서 사용할 수 없는 경우 어떤 Office 365 라우팅해야 하나요?

3. 작은 위치가 많은 네트워크의 경우 트래픽을 통합하는 기본 방법은 무엇입니까?

이러한 각 문제는 고유한 과제를 제공하며, 사용자 고유의 네트워크와 Microsoft에서 사용할 수 있는 옵션을 평가해야 합니다.

|**고려 사항**|**평가할 네트워크 구성 요소**|
|:-----|:-----|
|두 개 이상의 위치에 있는 회로  <br/> |활성/활성 방식으로 구성된 회로는 최소 두 개 이상 권장됩니다.  <br/> 비용, 대기 시간 및 대역폭 요구 사항을 비교해야 합니다.  <br/> BGP 경로 비용, PAC 파일 및 NAT를 사용하여 여러 회로로 라우팅을 관리합니다.  <br/> |
|ExpressRoute 회로가 없는 위치에서 라우팅  <br/> |요청 요청을 시작한 사람에 가깝게 발신 및 DNS 확인을 Office 365.  <br/> DNS 전달을 사용하여 원격 사무실에서 적절한 끝점을 검색할 수 있습니다.  <br/> 원격 사무실의 클라이언트에는 ExpressRoute 회로에 대한 액세스를 제공하는 경로를 사용할 수 있어야 합니다.  <br/> |
|소규모 사무실 통합  <br/> |사용 가능한 대역폭 및 데이터 사용량을 신중하게 비교해야 합니다.  <br/> |

> [!NOTE]
> 실제 위치에 관계없이 경로를 사용할 수 있는 경우 Microsoft는 인터넷을 통해 ExpressRoute를 선호합니다.
  
각 고유 네트워크에 대해 이러한 각 고려 사항을 고려해야 합니다. 다음은 예제입니다.
  
### <a name="example-2-multi-geographic-locations"></a>예제 2: 여러 지리적 위치
  
이 예는 여러 지리적 위치가 있는 Humongous Insurance라는 허위 회사에 대한 시나리오입니다.
  
Humongous Insurance는 전 세계 사무실과 지리적으로 분산되어 있습니다. 직접 네트워크 연결에서 대부분의 Office 365 트래픽을 유지하기 위해 Azure ExpressRoute를 Office 365 합니다. Humongous Insurance에는 두 대륙에 사무실이 있습니다. ExpressRoute가 실현되지 않는 원격 사무실의 직원은 ExpressRoute 연결을 사용하려면 기본 시설 중 하나 또는 둘 다로 다시 라우팅해야 합니다.
  
이 원칙은 Microsoft 데이터 센터로 전송되는 Office 365 가능한 한 빠르게 전송하는 것입니다. 이 예에서 Humongous Insurance은 원격 사무실이 가능한 한 빨리 모든 연결을 통해 Microsoft 데이터 센터로 이동하기 위해 인터넷을 통해 라우팅해야 하는지 또는 원격 사무실이 ExpressRoute 연결을 통해 Microsoft 데이터 센터로 가급적 빨리 연결하기 위해 내부 네트워크를 통해 라우팅해야 하는지 여부를 결정해야 합니다.
  
Microsoft의 데이터 센터, 네트워크 및 응용 프로그램 아키텍처는 전 세계에 분산된 통신을 사용하며 가능한 가장 효율적인 방식으로 서비스를 제공하도록 디자인되었습니다. 이는 세계에서 가장 큰 네트워크 중 하나입니다. 고객 네트워크에 Office 365 위해 예정된 요청은 이 아키텍처를 활용할 수 없습니다.
  
Humongous Insurance의 상황에서는 ExpressRoute를 통해 사용하려는 응용 프로그램에 따라 계속 진행해야 합니다. 예를 들어 비즈니스용 Skype Online 고객인 경우 또는 외부 비즈니스용 Skype Online 모임에 연결할 때 ExpressRoute 연결을 사용하겠지만 비즈니스용 Skype Online 미디어 품질 및 네트워크 연결 가이드에서 권장하는 디자인은 세 번째 위치에 대한 추가 ExpressRoute 회로를 프로비전하는 것입니다. 네트워킹 관점에서 보면 비용이 더 많이 들 수 있습니다. 그러나 Microsoft 데이터 센터로 전달하기 전에 대륙 간 요청을 라우팅하면 온라인 모임 및 통신 중에 비즈니스용 Skype 또는 사용할 수 없는 환경이 발생할 수 있습니다.
  
Humongous Insurance에서 비즈니스용 Skype Online을 사용하지 않는 경우 Office 365 예정된 네트워크 트래픽을 ExpressRoute 연결을 통해 다시 대륙으로 라우팅하는 것이 타당할 수 있습니다. 그러나 불필요하게 대기 시간이 발생하거나 TCP 정체가 발생할 수 있습니다. 두 경우 Office 365 모두 인터넷으로 전송되는 트래픽을 로컬 사이트에서 라우팅하는 것이 좋습니다.
  
![ExpressRoute 다중 지리입니다.](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Humongous Insurance에서 다중 지리 전략을 계획할 때 회로 크기, 회로 수, 장애 조치(failover) 등 여러 가지를 고려해야 합니다.
  
여러 지역이 회로를 사용하려고 하는 단일 위치에서 ExpressRoute를 사용하는 Humongous Insurance는 원격 사무실에서 Office 365 연결은 가장 가까운 Office 365 데이터 센터로 전송되어 본사 위치가 수신하도록 하려고 합니다. 이를 위해 Humongous Insurance은 DNS 전달을 구현하여 본사 인터넷 시작점에 가장 가까운 Office 365 환경과 적절한 연결을 설정하는 데 필요한 왕복 및 DNS 검색 횟수를 줄입니다. 이렇게 하면 클라이언트가 로컬 프런트 엔드 서버를 확인하지 못하게 하여 사용자가 연결되는 Front-End 서버가 Humongous Insurance가 Microsoft와 함께 피어링하는 본사 근처에 위치할 수 있습니다. 도메인 이름에 [조건부 전달자](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10))할당을 학습할 수도 있습니다.
  
이 시나리오에서 원격 사무실의 트래픽은 북미의 Office 365 프런트 엔드 인프라를 해결하고 Office 365 응용 프로그램의 아키텍처에 따라 백 엔드 서버에 연결하기 위해 Office 365 합니다. 예를 들어 Exchange Online 북미에서 연결을 종료하면 해당 프런트 엔드 서버는 테넌트가 있는 모든 곳에서 백 엔드 사서함 서버에 연결합니다. 모든 서비스에는 유니캐스트 및 모든캐스트 목적지로 구성된 널리 분산된 프런트 도어 서비스가 있습니다.
  
Humongous에 여러 대륙에 주요 사무실이 있는 경우 비즈니스용 Skype Online과 같은 중요한 응용 프로그램의 대기 시간을 줄이기 위해 지역당 최소 두 개의 활성/활성 회로를 사용하는 것이 좋습니다. 모든 사무실이 단일 대륙에 있는 경우 또는 실시간 공동 작업을 사용하지 않는 경우 통합 또는 분산된 시작 지점을 가지는 것은 고객별 결정입니다. 여러 회로를 사용할 수 있는 경우 단일 회로를 사용할 수 없게 될 경우 BGP 라우팅은 장애 조치(failover)를 보장합니다.
  
샘플 라우팅 구성 및 에 [대해 자세히](/azure/expressroute/expressroute-config-samples-routing) 알아보시고 을(를) 자세히 알아보아야 [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat) 합니다.
  
## <a name="selective-routing-with-expressroute"></a>ExpressRoute를 통해 선택적 라우팅

ExpressRoute를 통해 선택적 라우팅은 테스트, 일부 사용자에게 ExpressRoute 롤아웃 등의 다양한 이유로 필요할 수 있습니다. 고객이 ExpressRoute를 통해 네트워크 트래픽을 선택적으로 라우팅하는 Office 365 다양한 도구가 있습니다.
  
1. **경로 필터링/egregation** - BGP 경로가 ExpressRoute를 Office 365 서브넷 또는 라우터의 하위 집합으로 라우팅할 수 있도록 허용 이 경로는 고객 네트워크 세그먼트 또는 실제 사무실 위치별로 선택적으로 라우팅됩니다. 이는 일반적으로 사용자에 대한 ExpressRoute의 시차를 Office 365 BGP 디바이스에 구성됩니다.

2. **PAC 파일/URL** - 특정 Office 365 경로에 대해 전송되는 네트워크 트래픽을 지정합니다. 이렇게 하여 PAC 파일 배포로 식별된 클라이언트 컴퓨터로 [선택적으로 라우팅합니다.](./managing-office-365-endpoints.md)

3. **경로 필터링**  -  [경로 필터는](/azure/expressroute/how-to-routefilter-portal) Microsoft 피어링을 통해 지원되는 서비스의 하위 집합을 사용할 수 있는 한 가지 방법입니다.

4. **BGP** 커뮤니티 - [BGP](./bgp-communities-in-expressroute.md) 커뮤니티 태그 기반 필터링을 통해 고객은 ExpressRoute를 Office 365 및 인터넷을 트래버스할 응용 프로그램을 결정할 수 있습니다.

다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/erorouting]()
  
## <a name="related-topics"></a>관련 항목

[Office 365 네트워크 연결 평가](assessing-network-connectivity.md) 
  
[Office 365용 Azure ExpressRoute](azure-expressroute.md)
  
[Office 365 연결에 대한 ExpressRoute 관리](managing-expressroute-for-connectivity.md)
  
[Office 365용 ExpressRoute를 사용한 네트워크 계획](network-planning-with-expressroute.md)
  
[Office 365용 ExpressRoute 구현](implementing-expressroute.md)
  
[비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[비즈니스용 Skype Online의 네트워크 최적화](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[비즈니스용 Skype Online의 ExpressRoute 및 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[ExpressRoute를 사용하는 호출 흐름](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[다른 시나리오에 ExpressRoute에서 BGP Office 365 사용](bgp-communities-in-expressroute.md)
  
[초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정](performance-tuning-using-baselines-and-history.md)
  
[Office 365 성능 문제 해결 계획](performance-troubleshooting-plan.md)
  
[Office 365 URL 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 네트워크 및 성능 조정](network-planning-and-performance.md)
