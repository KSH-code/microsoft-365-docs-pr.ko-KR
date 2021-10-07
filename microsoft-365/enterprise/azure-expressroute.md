---
title: Office 365용 Azure Express 경로
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Azure ExpressRoute와 함께 Azure ExpressRoute를 Office 365 배포하는 경우 네트워크 구현 프로젝트를 계획합니다.
ms.openlocfilehash: 9a4f4be76751ec03610bd766f51ec91526ca18a4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198544"
---
# <a name="azure-expressroute-for-office-365"></a>Office 365용 Azure Express 경로

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Azure ExpressRoute를 사용자와 함께 사용하는 Office 365 Azure ExpressRoute를 배포하는 경우 필요한 네트워크 구현 프로젝트를 계획하는 방법을 Office 365. Azure에서 실행되는 인프라 및 플랫폼 서비스는 네트워크 아키텍처 및 성능 고려 사항을 해결하여 종종 이점을 제공합니다. 이러한 경우 Azure용 ExpressRoute를 권장합니다. Office 365 Dynamics 365와 같은 서비스로 제공되는 소프트웨어는 인터넷을 통해 안전하고 안정적으로 액세스할 수 있도록 구축되어 있습니다. Internet performance and security 및 [Assessing Office 365](assessing-network-connectivity.md)network connectivity 문서에서 Azure ExpressRoute를 고려할 Office 365 있습니다.

> [!NOTE]
> 끝점용 Microsoft Defender는 Azure ExpressRoute와의 통합을 제공하지 않습니다. 이는 고객이 개인 네트워크에서 끝점 클라우드 서비스에 대한 Microsoft Defender로의 연결을 가능하게 하는 ExpressRoute 규칙을 정의하는 데 중지하지는 못하게 하지만, 서비스 또는 클라우드 인프라가 발전함에 따라 규칙을 유지 관리하는 것은 고객의 확정입니다.

> [!NOTE]
> 대부분의 상황에서 서비스에 가장 적합한 연결 모델을 제공하지 Microsoft 365 경우에는 ExpressRoute를 권장하지 않습니다. 따라서 이 연결 모델을 사용하여 Microsoft 인증을 Microsoft 365. 모든 고객 요청을 검토하고 필요한 Microsoft 365 시나리오에서만 ExpressRoute에 권한을 승인합니다. 자세한 내용은 Microsoft 365 [대한 ExpressRoute](https://aka.ms/erguide) 가이드를 읽고 생산성, 네트워크 및 보안 팀이 있는 문서에 대한 포괄적인 검토를 따라 Microsoft 계정 팀과 함께 필요한 경우 예외를 제출하세요. 사용자에 대한 경로 필터를 만들려고 Office 365 오류 메시지가 [표시됩니다.](https://support.microsoft.com/kb/3181709)

## <a name="planning-azure-expressroute-for-office-365"></a>Azure ExpressRoute for Office 365

인터넷 연결 외에도 Microsoft 네트워킹 구성 요소에 대해 예측 가능성 및 99.95%의 사용 시간 SLA를 제공하는 직접 연결을 통해 Office 365 네트워크 트래픽의 하위 집합을 라우팅할 수 있습니다. Azure ExpressRoute는 사용자 및 기타 Microsoft 클라우드 서비스에 Office 365 전용 네트워크 연결을 제공합니다.

기존 MPLS WAN이 있는지 여부에 관계없이 ExpressRoute를 세 가지 방법 중 하나를 사용하여 네트워크 아키텍처에 추가할 수 있습니다. 지원되는 클라우드 교환 공동 위치 공급자, 이더넷 지점 대 지점 연결 공급자 또는 MPLS 연결 공급자를 통해 지역 [에서 사용할 수 있는 공급자를 참조합니다.](/azure/expressroute/expressroute-locations) Direct ExpressRoute 연결을 사용하면 아래에 포함된 Office 365 서비스에 설명된 응용 [프로그램에 대한 연결을](azure-expressroute.md#BKMK_WhatDoIGet) 설정할 수 있습니다. 다른 모든 응용 프로그램 및 서비스에 대한 네트워크 트래픽은 계속해서 인터넷을 트래버스합니다.

Office 365, Windows Update 및 TechNet과 같은 모든 Microsoft 응용 프로그램에 액세스하기 위해 인터넷을 통해 Microsoft의 데이터 센터에 연결하는 일반적인 Office 365 높은 수준의 네트워크 다이어그램을 고려합니다. 고객은 사내 네트워크에서 연결하는지 독립적인 인터넷 연결에 관계없이 유사한 네트워크 경로를 사용하게 됩니다.

![Office 365 연결합니다.](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

이제 인터넷 및 ExpressRoute를 사용하여 인터넷에 연결하는 Office 365 고객을 설명하는 업데이트된 다이어그램을 Office 365. 공용 DNS 및 Content Delivery Network 노드와 같은 일부 연결에는 여전히 공용 인터넷 연결이 필요합니다. 또한 ExpressRoute 연결된 건물에 없는 고객의 사용자가 인터넷을 통해 연결하고 있는지 확인합니다.

![Office 365 연결](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

여전히 자세한 정보를 원하세요? Azure [ExpressRoute for azure ExpressRoute로](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) 네트워크 트래픽을 관리하는 방법을 Office 365 에 대해 [Azure ExpressRoute를](/azure/expressroute/expressroute-faqs)구성하는 Office 365. 또한 개념을 보다 철저하게 설명할 수 있도록 채널 9에 Office 365 [교육용 Azure ExpressRoute](https://channel9.msdn.com/series/aer) 10부도 기록했습니다.

## <a name="what-office-365-services-are-included"></a>포함된 Office 365 서비스는 무엇입니까?
<a name="BKMK_WhatDoIGet"> </a>

다음 표에는 ExpressRoute를 Office 365 지원되는 서비스 목록이 나열되어 있습니다. 이러한 응용 [프로그램에 Office 365](./urls-and-ip-address-ranges.md) 네트워크 요청에 대해 이해하려면 해당 끝점 문서를 참조하세요.

| 포함된 응용 프로그램 |
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|비즈니스용 Skype 온라인<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint 온라인<sup>1</sup> <br/> 비즈니스용 OneDrive<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|포털 및 공유<sup>1</sup> <br/> Azure Active Directory(Azure AD) <sup>1</sup> <br/> Azure AD 커넥트<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> 이러한 각 응용 프로그램에는 ExpressRoute를 통해 지원되지 않는 인터넷 연결 요구 사항이 있습니다. 자세한 내용은 Office 365 [끝점](./urls-and-ip-address-ranges.md) 문서를 참조하세요.

Office 365 ExpressRoute에 포함되지 않은 서비스는 중국의 Office 365 클라이언트 다운로드, 엔터프라이즈용 Microsoft 365 앱 ID 공급자 로그인 및 Office 365(21 Vianet에서 운영) 서비스입니다.

## <a name="implementing-expressroute-for-office-365"></a>Office 365용 ExpressRoute 구현

ExpressRoute를 구현하려면 네트워크 및 응용 프로그램 소유자의 개입이 필요하며, 새 네트워크 라우팅 [아키텍처,](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)대역폭 요구 사항, 보안 구현 위치, 고가용성 등 신중하게 계획해야 합니다. ExpressRoute를 구현하려면 다음을 해야 합니다.

1. 연결 계획에서 ExpressRoute가 충족해야 하는 Office 365 완전히 이해합니다. 인터넷 또는 ExpressRoute를 사용할 응용 프로그램을 이해하고 네트워크 용량, 보안 및 고가용성 요구 사항을 네트워크 트래픽에 인터넷과 ExpressRoute를 둘 다 사용하는 컨텍스트에서 Office 365 계획합니다.

2. 인터넷 및 ExpressRoute 트래픽 1 둘 다의 발신 및 피어링 위치를<sup>확인합니다.</sup>

3. 인터넷 및 ExpressRoute 연결에 필요한 용량을 확인합니다.

4. 보안 및 기타 표준 경계 컨트롤 1을 구현하기 위한 계획을<sup>수립합니다.</sup>

5. ExpressRoute를 구독할 Microsoft Azure 계정이 있어야 합니다.

6. 연결 모델 및 승인된 [공급자를 선택합니다.](/azure/expressroute/expressroute-locations) 고객은 여러 연결 모델 또는 파트너를 선택할 수 있으며 파트너가 기존 네트워크 공급자와 동일할 필요는 없습니다.

7. 트래픽을 ExpressRoute로 지시하기 전에 배포의 유효성을 검사합니다.

8. 선택적으로 [QoS를 구현하고](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 지역별 확장을 평가합니다.

<sup>1</sup> 중요한 성능 고려 사항. 여기서 결정한 결정은 대기 시간에 크게 영향을 줄 수 있습니다. 이 결정은 사용자와 같은 응용 프로그램에 비즈니스용 Skype.

추가 참조를 위해 [](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) ExpressRoute 설명서와 함께 라우팅 [가이드를 사용하세요.](/azure/expressroute/expressroute-introduction)

For expressRoute for Office 365, you'll need to work with one or more [approved providers](/azure/expressroute/expressroute-locations) to provision the desired number and size circuits with an ExpressRoute Premium subscription. 이 경우 추가 라이선스를 구매할 수 Office 365.

다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/expressrouteoffice365]()

[ExpressRoute에](https://aka.ms/ert)등록할 준비가 Office 365?

## <a name="related-topics"></a>관련 주제

[Office 365 네트워크 연결 평가](assessing-network-connectivity.md) 

[Office 365 연결에 대한 ExpressRoute 관리](managing-expressroute-for-connectivity.md)

[Office 365용 ExpressRoute를 사용한 라우팅](routing-with-expressroute.md)

[Office 365용 ExpressRoute를 사용한 네트워크 계획](network-planning-with-expressroute.md)

[Office 365용 ExpressRoute 구현](implementing-expressroute.md)

[다른 시나리오에 ExpressRoute에서 BGP Office 365 사용](bgp-communities-in-expressroute.md)

[비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정](performance-tuning-using-baselines-and-history.md)

[Office 365 성능 문제 해결 계획](performance-troubleshooting-plan.md)

[Office 365 URL 및 IP 주소 범위](urls-and-ip-address-ranges.md)

[Office 365 네트워크 및 성능 조정](network-planning-and-performance.md)

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)
