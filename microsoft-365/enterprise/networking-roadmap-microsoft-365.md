---
title: Microsoft 365에 대 한 네트워킹 로드맵
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 네트워킹을 구현 하기 위한 로드맵입니다.
ms.openlocfilehash: 93d0f253e098815139b431a826f7e5e7a0410b37
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692582"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Microsoft 365에 대 한 네트워킹 로드맵

기업에 대 한 microsoft 365에는 공동 작업 및 생산성 클라우드 서비스, Microsoft Intune 및 다양 한 Microsoft Azure의 id 및 보안 서비스가 포함 되어 있습니다. 이러한 모든 클라우드 기반 서비스는 인터넷이나 전용 회선을 통해 클라이언트 장치의 연결 보안, 성능 및 안정성에 의존합니다. Microsoft는 이러한 서비스를 호스팅하고 전 세계 고객이 사용할 수 있도록하기 위해 성능 및 통합을 중점을 둔 네트워킹 인프라를 설계했습니다. 

Microsoft 365 온 보 딩의 중요 한 부분은 네트워크 및 인터넷 연결이 최적화 된 액세스를 사용 하도록 설정 되어 있는지 확인 하는 것입니다. 온-프레미스 네트워크가 온-프레미스 네트워크를 구성 하 여 SaaS (globally distributed Software) 클라우드에 액세스 하는 것은 들어오는 일반 네트워크와는 다른 내부 데이터 센터 및 중앙 인터넷 연결에 대 한 트래픽에 최적화 됩니다. 

이 문서를 사용하여 주요 차이점을 이해하고 에지 장치, 클라이언트 컴퓨터, 온-프레미스 네트워크를 수정하여 온-프레미스 사용자를 위한 최적의 성능을 구현하세요.

## <a name="plan"></a>계획

네트워킹 구현 계획 단계에서 다음을 수행 합니다.

- [Microsoft 365 네트워킹 작동 방식 이해](microsoft-365-networking-overview.md)
- [현재 네트워크 연결 평가](assessing-network-connectivity.md)
- [조직에 대 한 것이 적합 한지 확인](network-planning-with-expressroute.md)
- [네트워크 장치 계획](plan-for-network-devices.md)
- [마이그레이션을 위해 네트워크 설정 하기](network-and-migration-planning.md)

## <a name="deploy"></a>배포

네트워킹 구현 배포 단계에서 다음을 수행 합니다.

- [엔터프라이즈 네트워크가 Microsoft 365 연결에 맞게 최적화 되어 있는지 확인](set-up-network-for-microsoft-365.md)
- [조직의 DNS 도메인 추가](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [Microsoft 365 끝점에 대 한 연결 최적화](microsoft-365-ip-web-service.md)
- [원격 작업자에 대 한 연결 최적화](microsoft-365-vpn-split-tunnel.md)
- 필요한 경우 [express를 구성](azure-expressroute.md) 합니다.

## <a name="manage"></a>관리

네트워킹 구현 관리 단계에서 다음을 수행 합니다.

- [네트워크 장치에서 최신 Office 365 끝점을 사용 하는지 확인](microsoft-365-endpoints.md)
- [네트워킹 성능 모니터링 및 조정](network-planning-and-performance.md)
- [Express 경로 연결 모니터링](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>네트워크 장비 공급 업체

네트워크 장비 공급 업체가 면 [Microsoft 365 네트워킹 파트너 프로그램](microsoft-365-networking-partner-program.md)에 가입 합니다. 제품 및 솔루션에 Microsoft 365 네트워크 연결 원리를 빌드하기 위해 프로그램에 등록 합니다. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Contoso에서 Microsoft 365에 대 한 네트워킹을 수행 하는 방법

가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스에 맞게 [네트워크 장치 및 인터넷 연결을 최적화](contoso-networking.md)한 방법을 알아봅니다.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>다음 단계

[Microsoft 365 네트워킹 연결 개요](microsoft-365-networking-overview.md)를 사용 하 여 네트워킹 계획을 시작 합니다.
