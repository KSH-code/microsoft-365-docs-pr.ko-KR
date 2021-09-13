---
title: Office 365 연결을 위한 ExpressRoute 관리
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: Prefix 필터링, 보안 및 규정 Office 365 구성할 공통 영역을 포함하여 사용자에 대해 ExpressRoute를 관리하는 방법을 알아보습니다.
ms.openlocfilehash: e8de0763df7d592bc41802b1ead48df06891e6dc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213852"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Office 365 연결을 위한 ExpressRoute 관리

Office 365 ExpressRoute는 인터넷으로의 모든 트래픽을 들이지 않고도 여러 Office 365 서비스에 도달할 수 있는 대체 라우팅 경로를 제공합니다. Office 365 인터넷 연결이 Office 365 Microsoft가 BGP를 통해 네트워크로 보급하는 특정 경로는 네트워크에 다른 구성이 없는 한 직접 ExpressRoute 회로를 선호합니다. 이 라우팅을 관리하도록 구성할 수 있는 세 가지 공통 영역으로는 사전 필터링, 보안 및 규정 준수가 있습니다.
  
> [!NOTE]
> Microsoft는 Azure ExpressRoute에 대해 Microsoft 피어 라우팅 도메인을 검토하는 방법을 변경했습니다. 2017년 7월 31일부터 모든 Azure ExpressRoute 고객은 Azure 관리 콘솔 또는 PowerShell을 통해 직접 Microsoft 피어링을 사용하도록 설정할 수 있습니다. Microsoft 피어링을 사용하도록 설정한 후 모든 고객은 Dynamics 365 Customer Engagement 응용 프로그램(이전의 CRM Online)에 대한 BGP 경로 광고를 수신하는 경로 필터를 만들 수 있습니다. Azure ExpressRoute가 필요한 Office 365 Microsoft에서 검토를 얻어야만 해당 사용자에 대한 경로 필터를 만들 수 Office 365. Microsoft 계정 팀에 문의하여 ExpressRoute를 사용하도록 설정하기 위한 검토를 요청하는 Office 365 있습니다. 사용자에 대한 경로 필터를 만들려고 Office 365 구독에 오류 [메시지가 표시됩니다.](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Prefix Filtering

고객이 Microsoft에서 보급한 모든 BGP 경로를 수락하는 것이 좋습니다. 제공된 경로는 엄격한 검토 및 유효성 검사 프로세스를 통해 추가된 검사에 대한 혜택을 제거합니다. ExpressRoute는 기본적으로 고객 쪽에서 인바운드 경로 필터링이 없는 IP prefix 소유권, 무결성 및 규모와 같은 권장 컨트롤을 제공합니다.
  
ExpressRoute 공용 피어링에서 경로 소유권에 대한 추가 유효성 검사가 필요한 경우 보급된 경로를 [Microsoft의](https://www.microsoft.com/download/details.aspx?id=53602)공용 IP 범위를 나타내는 모든 IPv4 및 IPv6 IP prefix의 목록에 대해 확인할 수 있습니다. 이러한 범위는 전체 Microsoft 주소 공간을 포용하고 불필요하게 변경되어 필터링할 수 있는 안정적인 범위 집합을 제공함으로써 Microsoft 소유가 아닌 다른 경로가 해당 환경으로 누출되는 것이 우려되는 고객에게도 추가적인 보호를 제공합니다. 변경이 있을 경우 해당 월의 1일에 변경이 발생하고 페이지의 세부  정보 섹션에 있는 버전 번호는 파일이 업데이트될 때마다 변경됩니다.
  
여러 가지 이유로, Office 365 필터 목록을 생성하기 위해 URL 및 [IP](./urls-and-ip-address-ranges.md) 주소 범위를 사용하지 않도록 할 수 있습니다. 다음을 포함
  
- ip Office 365 IP는 자주 변경됩니다.

- URL Office 365 IP 주소 범위는 라우팅이 아닌 방화벽 허용 목록 및 프록시 인프라를 관리하도록 디자인되어 있습니다.

- Office 365 URL 및 IP 주소 범위는 ExpressRoute Microsoft 서비스 범위에 있을 수 있는 다른 URL을 포함하지 않습니다.

|**옵션**|**복잡성**|**변경 컨트롤**|
|:-----|:-----|:-----|
|모든 Microsoft 경로 수락  <br/> |**낮음:** 고객은 Microsoft 컨트롤을 사용하여 모든 경로가 제대로 소유되었는지 확인합니다.  <br/> |없음  <br/> |
|Microsoft 소유의 슈퍼넷 필터링  <br/> |**보통:** 고객은 Microsoft 소유 경로만 허용하도록 요약된 사전 필터 목록을 구현합니다.  <br/> |고객은 불필요하게 업데이트가 경로 필터에 반영되도록 해야 합니다.  <br/> |
|IP Office 365 필터링  <br/> [!CAUTION] Not-Recommended |**높음:** 고객 필터는 정의된 IP Office 365 따라 경로를 필터합니다.  <br/> |고객은 월별 업데이트를 위한 강력한 변경 관리 프로세스를 구현해야 합니다.  <br/> [!CAUTION] 이 솔루션을 사용하려면 상당한 변경이 필요합니다. 변경 내용이 제시간에 구현되지 않은 경우 서비스가 정전될 수 있습니다.   |

Azure ExpressRoute를 Office 365 연결은 Office 365 끝점이 배포된 네트워크를 나타내는 특정 IP 서브넷의 BGP 광고를 기반으로 합니다. Office 365 구성하는 서비스 수가 Office 365 때문에 고객은 네트워크에서 수락하는 광고를 관리해야 하는 경우가 종종 있습니다. 사용자 환경에 보급되는 미리 알림의 수가 우려되는 경우 [BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) 커뮤니티 기능을 사용하여 특정 Office 365 서비스 집합으로 광고를 필터링할 수 있습니다. 이 기능은 이제 미리 보기로 제공됩니다.
  
Microsoft에서 제공하는 BGP 경로 광고를 관리하는 방법에 관계없이 인터넷 회로에서만 Office 365 연결하는 경우와 비교할 때 Office 365 서비스에 특별한 노출을 얻지 못합니다. Microsoft는 고객이 연결하기 위해 사용하는 회로 유형에 관계없이 동일한 보안, 규정 준수 및 성능 수준을 Office 365.
  
### <a name="security"></a>보안

Microsoft는 ExpressRoute 공용 및 Microsoft 피어링으로 연결하기 위한 자체 네트워크 및 보안 경계 컨트롤을 유지 관리하는 Office 365 좋습니다. 네트워크에서 Microsoft 네트워크로 아웃바운드 이동하는 네트워크 요청과 Microsoft 네트워크에서 네트워크로의 인바운드에 대한 보안 제어가 설정해야 합니다.
  
#### <a name="outbound-from-customer-to-microsoft"></a>고객에서 Microsoft로 아웃바운드
  
컴퓨터가 Office 365 연결될 때 인터넷 또는 ExpressRoute 회로를 통해 연결이 설정되어 있는지에 관계없이 동일한 끝점 집합에 연결합니다. 사용되는 회로에 관계없이 Microsoft는 Office 365 서비스를 일반 인터넷 대상보다 신뢰할 수 있는 것으로 취급하는 것이 좋습니다. 아웃바운드 보안 컨트롤은 노출을 줄이고 지속적인 유지 관리 작업을 최소화하기 위해 포트 및 프로토콜에 집중해야 합니다. 필수 포트 정보는 끝점 [참조](./urls-and-ip-address-ranges.md) Office 365 사용할 수 있습니다.
  
추가된 컨트롤의 경우 프록시 인프라 내에서 FQDN 수준 필터링을 사용하여 인터넷 또는 서비스로 연결되는 일부 또는 모든 네트워크 요청을 제한하거나 검사할 수 Office 365. 기능이 릴리스될 때 FQDNS 목록을 유지 관리하고 Office 365 제품을 발전함에 따라 게시된 웹 엔드포인트에 대한 변경 내용을 보다 강력하게 관리하고 추적해야 [Office 365 있습니다.](./urls-and-ip-address-ranges.md)
  
> [!CAUTION]
> 아웃바운드 보안을 관리하기 위해 IP prefix만 사용하지 않는 것이 Office 365.

|**옵션**|**복잡성**|**변경 컨트롤**|
|:-----|:-----|:-----|
|제한 없음  <br/> |**낮음:** 고객은 Microsoft에 무제한 아웃바운드 액세스를 허용합니다.  <br/> |없음  <br/> |
|포트 제한  <br/> |**낮음:** 고객은 예상 포트를 통해 Microsoft에 대한 아웃바운드 액세스를 제한합니다.  <br/> |Infrequent.  <br/> |
|FQDN 제한  <br/> |**높음:** 고객은 게시된 FQDNS를 Office 365 아웃바운드 액세스를 제한합니다.  <br/> |월별 변경 내용  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Microsoft에서 고객으로 인바운드
  
Microsoft에서 네트워크에 대한 연결을 시작해야 하는 몇 가지 선택적 시나리오가 있습니다.
  
- 로그인에 대한 암호 유효성 검사 중 ADFS.

- [Exchange Server 하이브리드 배포](/exchange/exchange-hybrid).

- 테넌트에서 Exchange Online 호스트로의 메일입니다.

- SharePoint Online Online에서 SharePoint 호스트로 보내는 온라인 메일입니다.

- [SharePoint 하이브리드 검색을 검색합니다.](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)

- [SharePoint 하이브리드 BCS.](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)

- [비즈니스용 Skype 및/또는](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) [비즈니스용 Skype.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)

- [비즈니스용 Skype 클라우드 커넥터](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

복잡성을 줄이기 위해 ExpressRoute 회로 대신 인터넷 회로를 통해 이러한 연결을 수락하는 것이 좋습니다. 규정 준수 또는 성능 요구에 따라 ExpressRoute 회로를 통해 이러한 인바운드 연결을 수락해야 하는 경우 방화벽 또는 역방향 프록시를 사용하여 허용된 연결의 범위를 지정하는 것이 좋습니다. 끝점을 사용하여 [](./urls-and-ip-address-ranges.md) Office 365 FQDNs 및 IP prefix를 알아 내는 데 사용할 수 있습니다.
  
### <a name="compliance"></a>규정 준수

규정 준수 컨트롤에 사용하는 라우팅 경로를 사용하지 않습니다. ExpressRoute 또는 인터넷 회로를 통해 Office 365 서비스에 연결하는지 여부에 관계없이 규정 준수 컨트롤은 변경되지 않습니다. 조직의 요구 사항을 충족하기 위한 최상의 Office 365 준수 및 보안 인증 수준을 검토해야 합니다.
  
다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>관련 항목

[콘텐츠 배달 네트워크](content-delivery-networks.md)
  
[Office 365 URL 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 끝점 관리](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Azure ExpressRoute for Office 365 교육](https://channel9.msdn.com/series/aer)