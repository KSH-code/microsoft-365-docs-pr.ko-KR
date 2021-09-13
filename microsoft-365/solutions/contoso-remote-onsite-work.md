---
title: Contoso의 COVID-19 응답 및 하이브리드 작업 지원
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso Corporation이 COVID-19에 대응하고 하이브리드 작업을 위한 소프트웨어 설치 및 업데이트 인프라를 설계한 방법을 이해합니다.
ms.openlocfilehash: 06ce48969d35017da47be1e75ec3c374b9afb9a1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219722"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a>Contoso의 COVID-19 응답 및 하이브리드 작업 지원

Contoso는 항상 파리 본사의 중앙 VPN 서버를 통해 사내 리소스에 액세스한 원격 작업자를 지원했습니다. Contoso는 모든 원격 작업자에게 관리되는 노트북을 발급했습니다. 사내 작업자는 데스크톱 컴퓨터와 노트북을 함께 사용했습니다.

## <a name="contosos-response-to-covid-19"></a>CONtoso의 COVID-19에 대한 응답

COVID-19가 시작된 후 갑자기 필수적인 작업자는 모두 원격 작업자입니다. Contoso는 인력을 자택에서 일하고, 클라우드 서비스를 사용하여 온라인 및 사내 리소스에 대한 원격 액세스를 통해 기본 활동을 수행하게 하여 Microsoft 365 대응했습니다.

Contoso는 이미 원격 인력의 25%를 지원하기 위해 파리 본사에 원격 액세스 VPN 서버를 사용했지만, 인력의 90%를 지원하기 위해 원격 액세스 용량을 확장하기 위해 빠르게 이동했습니다. Contoso는 원격 작업자가 Contoso 인트라넷에 액세스하기 위해 지역적으로 가까운 진입점을 사용할 수 있도록 각 위성 사무실에 원격 액세스 VPN 서버를 배포했습니다.

또한 Contoso는 분할 터널링을 위해 랩톱, 태블릿 및 스마트폰에 설치된 VPN 클라이언트의 구성을 업데이트하여 최적화된 Office 365 끝점 집합에 대한 트래픽이 VPN 연결을 무시하고 인터넷을 통해 직접 전송하도록 합니다. 자세한 내용은 VPN 분할 터널링을 Office 365 원격 사용자에 대한 연결 [최적화를 참조하세요.](../enterprise/microsoft-365-vpn-split-tunnel.md)

다음은 파리 본사 및 각 위성 사무소에 VPN 장치를 설치한 결과 구성입니다. 

![Contoso의 VPN 인프라.](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

설치된 VPN 클라이언트가 있는 원격 작업원은 DNS를 사용하여 지역적으로 가장 가까운 사무실을 찾고 여기에 설치된 VPN 장치에 연결합니다. 분할 터널링을 Microsoft 365 최적화 끝점에 대한 트래픽은 지역적으로 가장 가까운 네트워크 Microsoft 365 전송됩니다. 다른 모든 트래픽은 VPN 연결을 통해 VPN 장치로 전송됩니다.

## <a name="contosos-support-for-hybrid-work"></a>Contoso의 하이브리드 작업 지원

지역 잠금 중에 원격 작업자를 지원하기 위해 초기에 변경된 후 Contoso는 하이브리드 작업을 지원하기 위해 인프라를 변경하여 작업자가 다음을 할 수 있습니다.

- 항상 원격.
- 항상 onsite.
- 사설 및 원격의 조합입니다.

Microsoft 365, 보안 및 규정 준수 기능은 Zero Trust용으로 설계되어 있으며 사용자 및 디바이스의 위치에 관계없이 작동하도록 디자인되었습니다. 자세한 내용은 [Zero Trust를 참조하세요.](https://www.microsoft.com/security/business/zero-trust)

그러나 설치할 소프트웨어가 온-프레미스 또는 인터넷 원본에서 제공될 수 있기 때문에 소프트웨어의 새 설치 및 업데이트 관리는 디바이스 위치에 따라 달라집니다. Contoso IT 설계자는 새로운 설치 및 업데이트 인프라를 작업자가 아닌 디바이스의 위치에 따라 설계했습니다.

두 가지 유형의 장치를 지정했습니다. 전용은 사내 및 로밍입니다.

### <a name="dedicated-on-premises"></a>전용 On-premises

전용 사내 장치는 Contoso 인트라넷을 떠나지 않는 데스크톱 또는 서버 컴퓨터로, VPN 클라이언트가 설치되어 있지 않습니다. 이러한 사내 장치는 Microsoft Endpoint Configuration Manager, 엔터프라이즈용 Microsoft 365 앱 및 에지 브라우저의 설치 및 업데이트에 Windows 10 배포 지점을 계속 사용합니다.

### <a name="roaming"></a>로밍

로밍 장치는 Contoso 인트라넷을 떠날 수 있으며, Contoso VPN 클라이언트가 설치된 스마트폰 및 태블릿과 같은 여러 사무실 작업자와 모든 원격 작업자와 기타 조직 소유 디바이스에 발급된 랩톱을 포함합니다. 

이러한 장치는 주어진 시간 동안 인터넷에 연결할 수 있기 때문에 Intune 또는 기타 클라우드 기반 서비스를 사용하여 Windows 10, 엔터프라이즈용 Microsoft 365 앱 업데이트합니다. 기존 사내 구성 관리자 배포 지점은 사용하지 않습니다.

즉, 로밍 장치에 대한 일부 설치 및 업데이트는 인터넷을 통해 수행되는 반면, 이러한 설치 및 업데이트는 사내에 있으며 인트라넷에 연결됩니다. 그러나 Contoso IT 설계자는 특히 대부분의 원격 작업자가 인트라넷에 연결되지 않은 경우를 위해 인터넷에 대한 인트라넷 대역폭을 최적화하는 것보다 구성의 단순성을 중요하게 결정했습니다.

결과 인프라는 다음과 있습니다.

![Contoso의 설치 및 업데이트 인프라.](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

설치 및 업데이트 동작은 장치의 컴퓨터 계정을 다음 그룹 중 하나의 구성원으로 설정하여 결정됩니다.

- OnPremDevices

  장치의 Configuration Manager 클라이언트는 설치 및 업데이트에 배포 지점을 사용합니다.

- RoamingDevices

  Intune 및 장치의 기타 설정은 설치 및 업데이트에 Microsoft 365 네트워크 사용을 지정합니다.

## <a name="new-onboarding-process"></a>새 온보더링 프로세스

새 관리자 또는 데이터 센터의 새 서버에 대해 발급된 새 전용 사내 디바이스의 경우, 사용자가 로그인하면 OnPremDevices 그룹의 디바이스 구성원 자격에 따라 Configuration Manager 클라이언트가 프레미스 구성 관리자 배포 지점에서 Windows 10, 엔터프라이즈용 Microsoft 365 앱 및 Edge에 대한 최신 업데이트를 다운로드하여 설치합니다. 완료되면 전용 사내 장치를 사용할 수 있으며 지속적인 업데이트에 이러한 배포 지점을 사용합니다.

새 관리자에게 발급된 새 원격 장치의 경우, 이 사용자가 로그인하면 RoamingDevices 그룹의 멤버 자격에 따라 장치가 Intune 클라우드 서비스 및 기타 서비스에 연결하고 Windows 10, 엔터프라이즈용 Microsoft 365 앱 및 Edge에 대한 최신 업데이트를 다운로드하여 설치합니다. 완료되면 원격 장치를 사용할 준비가 완료되고, 설치된 VPN 클라이언트를 사용하여 지속적인 업데이트를 위해 Microsoft 365 네트워크와 액세스할 수 있습니다.

## <a name="next-step"></a>다음 단계

[조직에서 하이브리드 작업을 위한](empower-people-to-work-remotely.md) 인프라를 설정합니다.
