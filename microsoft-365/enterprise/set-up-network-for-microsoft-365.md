---
title: 사용자에 대한 네트워크 Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 네트워크 연결 개요 및 끝점 목록을 포함하여 Microsoft 365 대한 네트워크를 설정하는 데 도움이 되는 정보가 있는 문서의 링크를 찾아야 합니다.
ms.openlocfilehash: 52de26081b4e61346ab584e1600893349b47fd17
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2021
ms.locfileid: "58355883"
---
# <a name="set-up-your-network-for-microsoft-365"></a>사용자에 대한 네트워크 Microsoft 365

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

사용자 온보 Microsoft 365 중요한 부분은 네트워크 및 인터넷 연결이 최적화된 액세스를 위해 설정되어 있도록 하는 것입니다. 전역 분산 SaaS(Software-as-a-Service) 클라우드에 액세스하도록 사내 네트워크를 구성하는 것은 사내 데이터 센터 및 중앙 인터넷 연결에 대한 트래픽에 최적화된 기존 네트워크와 다릅니다. 

이 문서를 사용하여 주요 차이점을 이해하고 에지 장치, 클라이언트 컴퓨터, 온-프레미스 네트워크를 수정하여 온-프레미스 사용자를 위한 최적의 성능을 구현하세요.

## <a name="how-microsoft-365-networking-works"></a>네트워크 Microsoft 365 작동 방식

다음 문서를 참조하여 연결에 대한 개요를 Microsoft 365.

- [Microsoft 365 네트워킹 연결 개요](microsoft-365-networking-overview.md)
- [Microsoft 365 네트워크 연결 원칙](microsoft-365-network-connectivity-principles.md)
- [Microsoft 365 네트워크 연결 평가](assessing-network-connectivity.md)

성능 향상에 대한 조언은 에 대한 네트워크 계획 및 성능 [조정을 Microsoft 365.](network-planning-and-performance.md)

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a>네트워크 Microsoft 365 공급업체로 네트워킹 지원

네트워크 장비 공급업체의 경우 [Office 365 네트워킹 파트너 프로그램](microsoft-365-networking-partner-program.md)에 참가하세요. 프로그램에 등록하여 제품 및 솔루션에 Office 365 네트워크 연결 원칙을 구축하세요. 

## <a name="office-365-endpoints"></a>Office 365 엔드포인트

엔드포인트는 인터넷에서 Office 365 트래픽을 위한 대상 IP 주소, DNS 도메인 이름, URL의 집합입니다. 

Office 365 클라우드 기반 서비스에 대한 성능을 최적화하려면 클라이언트 브라우저와 에지 네트워크의 장치가 일부 엔드포인트를 특별하게 처리해야 합니다. 이러한 장치로는 방화벽, SSL Break and Inspect 및 패킷 검사 장치, 데이터 손실 방지 시스템 등이 있습니다.

자세한 내용은 [Office 365 엔드포인트 관리](managing-office-365-endpoints.md)를 참조하세요.

현재 5개의 서로 다른 Office 365 클라우드가 있습니다. 이 표는 각 클라우드의 엔드포인트 목록으로 안내합니다.

| 끝점 | 설명 |
|:-------|:-----|
| [전 세계 엔드포인트](urls-and-ip-address-ranges.md) | 미국 GCC(정부 커뮤니티 클라우드)를 포함하는 전 세계 Office 365 구독의 엔드포인트입니다. |
| [미국 정부 DoD 엔드포인트](microsoft-365-u-s-government-dod-endpoints.md) | 미국 DoD(국방부) 구독의 엔드포인트입니다. |
| [미국 정부 GCC High 엔드포인트](microsoft-365-u-s-government-gcc-high-endpoints.md) | 미국 GCC(정부 커뮤니티 클라우드) High 구독의 엔드포인트입니다. |
| [21Vianet에서 운영하는 Office 365 엔드포인트](urls-and-ip-address-ranges-21vianet.md) | 21Vianet에서 운영하는 Office 365용 엔드포인트입니다. 중국에서 Office 365의 요구 사항을 충족하도록 설계되었습니다. |
| [Office 365 Germany 끝점](microsoft-365-germany-endpoints.md) | 독일, EU(유럽 연합), EFTA(유럽 자유 무역 연합)의 가장 규제를 많이 받는 고객을 위해 유럽에 있는 별도 클라우드의 엔드포인트입니다. |
|||

Office 365 클라우드의 최신 엔드포인트 목록을 자동으로 가져오게 만들려면 [Office 365 IP 주소 및 URL 웹 서비스](microsoft-365-ip-web-service.md)를 참조하세요.

엔드포인트에 대한 추가 내용은 다음 문서를 참조하세요.

- [웹 서비스에 포함되지 않는 추가 엔드포인트](additional-office365-ip-addresses-and-urls.md)
- [Mac용 Office 2016의 네트워크 요청](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a>Microsoft 365 네트워킹에 대한 추가 항목

네트워킹의 특수한 항목은 다음 Microsoft 365 참조하세요.

- [콘텐츠 배달 네트워크](content-delivery-networks.md)
- [Office 365 서비스의 IPv6 지원](ipv6-support.md)
- [NAT 지원(Office 365)](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a>Microsoft 365용 ExpressRoute

Office 365 트래픽의 ExpressRoute 사용에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Office 365용 Azure ExpressRoute](azure-expressroute.md)
- [Office 365용 ExpressRoute 구현](implementing-expressroute.md)
- [Office 365용 ExpressRoute를 사용한 네트워크 계획](network-planning-with-expressroute.md)
- [Office 365용 ExpressRoute를 사용한 라우팅](routing-with-expressroute.md)
