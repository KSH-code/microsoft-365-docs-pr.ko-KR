---
title: '4단계: 트래픽 바이패스 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 신뢰할 수 있는 Office 365 위치로의 트래픽 바이패스를 위해 웹 브라우저 및 에 장치를 이해하고 구성합니다.
ms.openlocfilehash: f52921fdc0a5329e3fffae687855a653f7026df6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870116"
---
# <a name="step-4-configure-traffic-bypass"></a>4단계: 트래픽 바이패스 구성

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

일반 인터넷 트래픽이 위험할 수 있으므로 일반적인 조직 네트워크는 프록시 서버, SSL 중단 및 조사, 패킷 검사 장치와 같은 에지 장치와 데이터 손실 방지 시스템을 통해 보안을 적용합니다. “Office 365 트래픽에 대해 타사 네트워크 장치 또는 솔루션 사용”에서 네트워크 차단 장치의 일부 문제점을 읽어보세요.

그러나 Microsoft 365 클라우드 기반 서비스에서 사용하는 DNS 도메인 이름 및  IP 주소는 잘 알려져 있습니다. 또한 트래픽 및 서비스 자체는 많은 보안 기능으로 보호됩니다. 이러한 보안 및 보호는 이미 설정되어 있으므로 에지 장치에서 복제할 필요가 없습니다. Microsoft 365 트래픽에 대한 중간 대상 및 중복 보안 처리로 인해 성능이 크게 저하될 수 있습니다.

중간 대상 및 중복 보안 처리를 제거하는 첫 번째 단계는 Microsoft 365 트래픽을 식별하는 것입니다. Microsoft는 끝점이라고 하는 다음과 같은 유형의 DNS 도메인 이름 및 IP 주소 범위를 정의했습니다.

- 최적화 - 모든 Office 365 서비스에 연결하는 데 필요하며 75%가 넘는 Microsoft 365 대역폭, 연결 및 데이터 볼륨을 나타냅니다. 이러한 끝점은 네트워크 성능, 대기 시간 및 가용성에 가장 민감한 Microsoft 365 시나리오를 나타냅니다.
- 허용 - 특정 Microsoft 365 서비스 및 기능에 연결하는 데 필요하지만 최적화 범주의 경우만큼 네트워크 성능 및 대기 시간에 민감하지 않습니다.
 - 기본 - 최적화를 요구하지 않는 Microsoft 365 서비스 및 종속성을 나타냅니다. 기본 범주 끝점을 일반적인 인터넷 트래픽으로 처리할 수 있습니다.

[https://aka.ms/o365endpoints](https://aka.ms/o365endpoints)에서 DNS 도메인 이름 및 IP 주소 범위를 찾을 수 있습니다.

다음이 권장됩니다.

- 온-프레미스 컴퓨터의 인터넷 브라우저에서 PAC(프록시 자동 구성) 스크립트를 사용하여 Microsoft 365 클라우드 기반 서비스의 DNS 도메인 이름에 대한 프록시 서버를 무시합니다. 최신 Microsoft 365 PAC 스크립트의 경우 Get-Pacfile PowerShell 스크립트를 참조하세요.
- 에지 장치를 분석하여 중복 처리를 확인한 후, 처리하지 않고 최적화 및 허용 끝점으로 트래픽을 전달하도록 구성합니다. 이것을 트래픽 바이패스라고 합니다. 
- 
에지 장치에는 방화벽, SSL 중단 및 조사, 패킷 검사 장치, 데이터 손실 방지 시스템이 포함되어 있습니다. 에지 장치를 구성하고 구성을 업데이트하려면 스크립트 또는 REST 호출을 사용하여 Office 365 끝점 웹 서비스의 구조화된 끝점 목록을 사용할 수 있습니다. 자세한 내용은 [Office 365 IP 주소 및 URL 웹 서비스](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)를 참조하세요.

Microsoft 365 최적화 및 허용 범주 끝점에 대한 트래픽의 일반 프록시 및 네트워크 보안 처리만 우회하게 됩니다. 다른 모든 일반 인터넷 트래픽은 프록시 처리되며, 기존 네트워크 보안 처리를 따릅니다.


중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step4)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[클라이언트 및 Office 365 서비스 성능 최적화](networking-optimize-tcp-performance.md) |



