---
title: 다른 시나리오에 ExpressRoute에서 BGP Office 365 사용
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Azure ExpressRoute에서 BGP 커뮤니티를 사용하여 여러 시나리오에 필요한 IP prefix 및 필요한 대역폭을 관리하는 Office 365 대해 설명합니다.
ms.openlocfilehash: 9cb6980c1d8cc120f99cac087602856aeacf1adf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185995"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>다른 시나리오에 ExpressRoute에서 BGP Office 365 사용

Azure ExpressRoute를 Office 365 연결은 Office 365 끝점이 배포된 네트워크를 나타내는 특정 IP 서브넷의 BGP 광고를 기반으로 합니다. Office 365 구성하는 서비스 수가 Office 365 때문에 고객은 네트워크에서 수락하는 광고를 관리해야 하는 경우가 종종 있습니다. IP 서브넷 수 줄이기 이 문서의 나머지 전체에서 IP prefix를 참조하여 BGP 네트워크 관리 용어에 맞게 고객에게 다음과 같은 최종 목표를 제공합니다.
  
- 수락된 보급된 **IP prefix** 허용 번호 관리 - 제한된 수의 IP 인프라 또는 네트워크 통신 사업자만 지원하는 네트워크 통신 사업자 또는 제한된 수의 사전 승인에 대해 요금을 부과하는 네트워크 통신 사업자 고객은 네트워크에 이미 보급된 총 prefix 수를 평가하고 ExpressRoute에 가장 적합한 Office 365 응용 프로그램을 선택해야 합니다.

- **Azure ExpressRoute** 회로에 필요한 대역폭 양 관리 - 고객은 ExpressRoute 경로와 인터넷 경로를 통해 Office 365 서비스의 대역폭 봉투를 제어하려는 경우도 있습니다. 이를 통해 고객은 인터넷 경로를 통해 나머지 비즈니스용 Skype 응용 프로그램에 대해 ExpressRoute 대역폭을 예약하고 나머지 Office 365 라우팅할 수 있습니다.

이러한 목표를 고객에게 지원하기 위해 Office 365 표시된 서비스별 BGP 커뮤니티 값으로 ExpressRoute를 통해 보급되는 IP prefix에 태그가 지정됩니다.
  
> [!NOTE]
> 다른 응용 프로그램과 연결된 일부 네트워크 트래픽이 커뮤니티 값에 포함될 것으로 예상됩니다. 이는 공유 서비스 및 데이터 센터가 있는 전역 소프트웨어 as a Service 제공에 대해 예상되는 동작입니다. 위의 두 가지 목표를 통해 가능한 경우 이 문제를 최소화했습니다. 즉, 사전 수 및/또는 대역폭을 염두에 두어 관리해야 합니다.

|**서비스**|**BGP Community 값**|**참고**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |EOP Exchange 포함\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|비즈니스용 Skype\*  <br/> |12076:5030  <br/> |비즈니스용 Skype 온라인 & Microsoft Teams 서비스  <br/> |
|기타 Office 365 서비스\*  <br/> |12076:5100  <br/> |포털 Azure Active Directory(인증 및 디렉터리 동기화 시나리오) 및 Office 365 포함됩니다.  <br/> |
|\*ExpressRoute에 포함된 서비스 시나리오의 범위는 Office 365 [끝점 문서에 설명되어](./urls-and-ip-address-ranges.md) 있습니다.  <br/> \*\*추가 서비스 및 BGP 커뮤니티 값은 향후 추가될 수 있습니다. [BGP 커뮤니티의 현재 목록을 참조하세요.](/azure/expressroute/expressroute-routing)  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>BGP 커뮤니티를 사용하는 가장 일반적인 시나리오는 무엇입니까?

고객은 BGP 커뮤니티를 사용하여 Azure ExpressRoute를 통해 네트워크에서 허용되는 IP prefix 그룹을 규제하여 특정 Office 365 서비스의 예상 대역폭 봉투에 영향을 미치게 됩니다. 모든 Office 365 Azure ExpressRoute 또는 BGP 커뮤니티 사용에 관계없이 인터넷 바인딩 트래픽이 필요한다는 것을 이해해야 합니다. 다음 세 가지 시나리오는 이 기능의 가장 일반적인 사용입니다.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>시나리오 1: IP Office 365 수 최소화

Contoso Corporation은 현재 온라인 및 Office 365 Exchange Online 50,000명 SharePoint 회사입니다. ExpressRoute 요구 사항을 검토할 때 Contoso는 많은 지역별 위치에 있는 네트워크 장치가 100개 이상의 추가 경로 항목을 통해 라우팅 테이블 크기를 처리할 수 없는지 확인합니다. Contoso는 ExpressRoute가 전체 Office 365 서비스에 대해 보급하는 총 IP prefix 수를 검토하고 100을 초과하는 것으로 결론 내렸다. 100개 이상의 추가 경로 항목을 유지하기 위해 Contoso는 ExpressRoute를 Office 365 ExpressRoute를 사용하여 ExpressRoute Microsoft 피어링을 통해 수신된 SharePoint Online BGP 커뮤니티 값인 12076:5020만 사용할 수 있습니다.

|**사용된 BGP 커뮤니티 태그**|**Azure ExpressRoute를 통해 라우팅할 수 있는 기능**|**필요한 인터넷 경로**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint 온라인 &amp; 비즈니스용 OneDrive  <br/> | DNS, CRL, &amp; CDN 요청  <br/>  기타 Office 365 Azure ExpressRoute를 통해 지원되지 않는 모든 서비스  <br/>  다른 모든 Microsoft 클라우드 서비스  <br/>  Office 365 포털, Office 365, Office &amp; 검색  <br/>  Exchange Online, Exchange Online Protection 및 비즈니스용 Skype Online  <br/> |

> [!NOTE]
> 각 서비스에 대해 더 낮은 prefix 개수를 달성하기 위해 서비스 간에 최소한의 겹치는 정도가 유지됩니다. 이것은 예상된 동작입니다.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>시나리오 2: ExpressRoute 및 내부 대역폭 사용을 일부 Office 365 수 있습니다.

분산된 다른 네트워크가 있는 대규모 다국적 기업인 Fabrikam Inc는 다음을 비롯한 여러 Office 365 서비스 구독자입니다. Exchange Online, SharePoint Online 및 비즈니스용 Skype. Fabrikam의 내부 라우팅 인프라는 라우팅 테이블에서 수천 개의 IP prefix를 처리할 수 있습니다. 그러나 Fabrikam은 네트워크 성능에 가장 민감한 Office 365 응용 프로그램에 대해 ExpressRoute 및 내부 대역폭만 프로비전하고 다른 모든 Office 365 응용 프로그램에 대해 기존 인터넷 대역폭을 사용하려는 경우
  
이러한 이유로 Fabrikam은 ExpressRoute Microsoft 피어링을 통해 수신된 비즈니스용 Skype Online BGP Community 값인 12076:5030으로 Azure ExpressRoute 대역폭 범위를 지정합니다. 네트워크와 연결된 나머지 네트워크 트래픽은 Office 365 계속 인터넷 연결 지점을 사용하게 됩니다.

|**사용된 BGP 커뮤니티 태그**|**Azure ExpressRoute를 통해 라우팅할 수 있는 기능**|**필요한 인터넷 경로**|
|:-----|:-----|:-----|
|비즈니스용 Skype  <br/> (12076:5030)  <br/> |Skype SIP 신호, 다운로드, 음성, 비디오 및 데스크톱 공유  <br/> | DNS, CRL, &amp; CDN 요청  <br/>  기타 Office 365 Azure ExpressRoute를 통해 지원되지 않는 모든 서비스  <br/>  다른 모든 Microsoft 클라우드 서비스  <br/>  Office 365 포털, Office 365, Office &amp; 검색  <br/>  비즈니스용 Skype 원격 분석, Skype 빠른 팁, 공용 IM 연결  <br/>  Exchange Online, Exchange Online Protection 및 SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>시나리오 3: 서비스 전용 Azure ExpressRoute Office 365 수 있습니다.

Woodgrove Bank는 서비스를 포함한 여러 Microsoft 클라우드 서비스의 Office 365. Woodgrove Bank는 네트워크 용량 및 소비를 평가한 후 Azure ExpressRoute를 지원되는 Office 365 서비스에 대한 기본 경로로 배포하기로 결정했습니다. 라우팅 테이블은 프로비전된 Azure ExpressRoute 회로와 모든 프로비전된 Office 365 대역폭 및 대기 시간 요구 사항을 모두 지원할 수 있습니다.
  
다른 Microsoft 클라우드 서비스와 연결된 네트워크 트래픽을 Office 365. Woodgrove Bank는 특정 BGP 커뮤니티 값, 12076:Office 365 12076:5020, 12076:5030, 12076:5030, 12076:5100으로 태그가 지정된 모든 IP Office 365 ExpressRoute의 사용 범위를 지정합니다.

|**사용된 BGP 커뮤니티 태그**|**Azure ExpressRoute를 통해 라우팅할 수 있는 기능**|**필요한 인터넷 경로**|
|:-----|:-----|:-----|
|Exchange, 비즈니스용 Skype & Microsoft Teams, SharePoint, &amp; 기타 서비스  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |&amp;Exchange Online Exchange Online Protection  <br/> SharePoint 온라인 &amp; 비즈니스용 OneDrive  <br/> Skype SIP 신호, 다운로드, 음성, 비디오 및 데스크톱 공유  <br/> Office 365 포털, Office 365, Office &amp; 검색  <br/> | DNS, CRL, &amp; CDN 요청  <br/>  기타 Office 365 Azure ExpressRoute를 통해 지원되지 않는 모든 서비스  <br/>  다른 모든 Microsoft 클라우드 서비스  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>BGP 커뮤니티 사용에 대한 주요 계획 고려 사항

BGP 커뮤니티를 활용하여 ExpressRoute가 고객 네트워크를 통해 보급되고 전파되는 방식에 영향을 주는 고객은 다음 사항을 고려해야 합니다.
  
- 네트워크 디자인에서 BGP 커뮤니티를 사용하는 경우 경로 대칭이 계속 유지 관리되도록 하는 것이 중요합니다. 경우에 따라 BGP 커뮤니티를 추가하거나 제거하면 대칭 라우팅이 손상되고 라우팅 구성을 업데이트하여 대칭 라우팅을 다시 설정해야 하는 상황이 생성될 수 있습니다.

- BGP 커뮤니티 값으로 Azure ExpressRoute를 곱하는 것은 고객 작업입니다. Microsoft는 고객이 구성한 모든 스위핑에 관계없이 피어링 관계와 연결된 모든 IP prefix를 보급합니다.

- Azure ExpressRoute는 고객이 할당한 BGP 커뮤니티를 기반으로 Microsoft 네트워크에서 어떠한 작업도 지원하지 않습니다.

- 서비스에서 사용하는 IP Office 365 서비스별 BGP 커뮤니티 값으로만 표시되고 위치별 BGP 커뮤니티는 지원되지 않습니다. Office 365 서비스는 본질적으로 전역적이기 때문에 테넌트의 위치에 따라 또는 Office 365 클라우드 내의 데이터를 필터링하는 것은 지원되지 않습니다. 요청하는 Office 365 서비스의 IP 주소 위치에 관계없이 사용자의 네트워크 위치에서 Microsoft 전역 네트워크로의 최단 또는 가장 선호 네트워크 경로를 조정하도록 네트워크를 구성하는 것이 좋습니다.

- 각 BGP 커뮤니티 값에 포함된 IP prefixes는 값과 연결된 Office 365 응용 프로그램의 IP 주소가 포함된 서브넷을 나타냈습니다. 경우에 따라 두 개 이상의 Office 365 응용 프로그램에 IP 주소가 있는 경우 IP 주소가 두 개 이상의 커뮤니티 값에 기존에 있는 경우도 있습니다. 할당 조각화로 인한 동작은 적지만 이로 인해 예상되는 동작은 prefix 개수 또는 대역폭 관리 목표에 영향을 끼치지 않습니다. 고객은 효과를 최소화하기 위해 BGP 커뮤니티를 활용하는 경우 "필요하지 않은 것을 거부"하는 것이 아니라 "필요한 것을 허용" 접근법을 Office 365 것이 됩니다.

- BGP 커뮤니티를 사용해도 네트워크 연결 요구 사항 또는 구성을 변경하지는 Office 365. 인터넷에 액세스하려는 Office 365 여전히 인터넷에 액세스할 수 있는 권한이 필요합니다.

- BGP 커뮤니티로 Azure ExpressRoute를 구성하면 내부 네트워크가 Microsoft 피어링 관계를 통해 볼 수 있는 경로에만 영향을 미치게 됩니다. PAC 또는 WPAD 구성을 범위가 지정한 라우팅과 함께 사용하는 등의 추가 응용 프로그램 수준 구성을 만들어야 할 수 있습니다.

- Microsoft에서 할당한 BGP 커뮤니티를 사용하는 것 외에도 고객은 내부 라우팅에 영향을 미치기 위해 Azure ExpressRoute를 통해 Office 365 IP prefix에 자체 BGP 커뮤니티를 할당할 수 있습니다. 인기 있는 사용 사례는 각각 ExpressRoute 피어링 위치를 통해 학습된 모든 경로에 위치 기반 BGP 커뮤니티를 할당한 다음 고객 네트워크에서 해당 정보 다운스트림을 사용하여 Microsoft 네트워크로 가장 짧거나 가장 선호되는 네트워크 경로를 조정하는 것입니다. 고객 할당 BGP 커뮤니티와 ExpressRoute를 Office 365 Microsoft의 제어 또는 표시 범위를 벗어남

돌아오는 데 사용할 수 있는 짧은 링크는 [https://aka.ms/bgpexpressroute365]() 입니다. .
  
## <a name="related-topics"></a>관련 항목

[Office 365 네트워크 연결 평가](assessing-network-connectivity.md) 
  
[Office 365용 Azure ExpressRoute](azure-expressroute.md)
  
[Office 365 연결에 대한 ExpressRoute 관리](managing-expressroute-for-connectivity.md)
  
[Office 365용 ExpressRoute를 사용한 라우팅](routing-with-expressroute.md)
  
[Office 365용 ExpressRoute를 사용한 네트워크 계획](network-planning-with-expressroute.md)
  
[비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[비즈니스용 Skype Online의 ExpressRoute 및 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[ExpressRoute를 사용하는 호출 흐름](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Office 365용 ExpressRoute 구현](implementing-expressroute.md)
  
[BGP 커뮤니티 지원](/azure/expressroute/expressroute-routing)
  
[초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정](performance-tuning-using-baselines-and-history.md)
  
[Office 365 성능 문제 해결 계획](performance-troubleshooting-plan.md)
  
[Azure ExpressRoute for Office 365 교육](https://channel9.msdn.com/series/aer)