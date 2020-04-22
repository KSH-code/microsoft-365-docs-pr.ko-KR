---
title: '3단계: 네트워크 헤어핀 방지'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 더 나은 성능을 위해 네트워크 헤어핀을 이해하고 제거합니다.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583428"
---
# <a name="step-3-avoid-network-hairpins"></a>3단계: 네트워크 헤어핀 방지

*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![1 단계-네트워킹](../media/deploy-foundation-infrastructure/networking_icon-small.png)

목적지의 트래픽 바운드가 온-프레미스 보안 스택, 클라우드 액세스 브로커 또는 클라우드 기반 웹 게이트웨이와 같은 다른 중간 위치로 전달될 시 [네트워크 헤어핀](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)이 발생합니다. 예를 들면 다음과 같습니다.

![네트워크 헤어핀의 예시](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

네트워크 헤어핀은 네트워크 서비스 공급업체로 인해 인터넷에서의 잘못된 라우팅이 원인이 될 수도 있습니다. 

헤어핀은 대기 시간을 더하고 잠재적으로 지리적으로 떨어진 위치로 트래픽 방향을 전환할 수 있습니다.

Microsoft 365 클라우드 기반 서비스에 대한 트래픽의 성능을 최적화하기 위해 로컬 인터넷 연결을 제공하는 ISP가 해당 위치에서 근접한 Microsoft 전역 네트워크와 직접 피어링 관계가 있는지 여부를 확인합니다. 이러한 연결에는 헤어핀이 없습니다.

Microsoft 365 트래픽을 위해 클라우드 기반 네트워크 또는 보안 서비스를 사용하는 경우 헤어핀 효과를 평가하고 성능에 미치는 영향을 이해해야 합니다. 다음을 검사하세요.

- 지사 및 Microsoft 전역 네트워크 피어링 지점과 관련해서 트래픽이 전달되는 서비스 공급자의 번호 및 위치 
- ISP 및 Microsoft와 서비스 공급자의 네트워크 피어링 관계 품질 
- 서비스 공급자 인프라의 백홀이 성능에 미치는 영향

가능하면 인터넷 트래픽을 처리하는 타사 클라우드 또는 클라우드 기반 네트워크 보안 공급업체를 통한 프로시 또는 터널링 대신, 신뢰할 수 있는 Microsoft 365 트래픽을 직접 전송하도록 에지 라우터를 구성합니다. 

![네트워크 헤어핀의 우회 예시](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

Microsoft의 전역 네트워크에 대한 진입점과 얼마나 근접한지와 조직 네트워크가 ISP에 연결되는 지점과 얼마나 근접한지를 테스트하려면 [Office 365 Network 온보딩 도구](https://connectivity.office.com/)를 사용하세요.

중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step3)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![4단계](../media/stepnumbers/Step4.png)|[트래픽 바이패스 구성](networking-configure-proxies-firewalls.md)|
