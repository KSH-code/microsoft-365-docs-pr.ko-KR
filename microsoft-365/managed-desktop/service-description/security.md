---
title: Microsoft Managed Desktop의 보안 기술
description: 장치 보안, ID 및 액세스 관리, 네트워크 보안 및 정보 보안에 사용되는 기술
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5076ddca6053adc7cebb9599c8d82a42c7ab5a63
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840916"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 보안 기술

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop은 여러 Microsoft 기술을 사용하여 관리되는 장치 및 데이터를 보호합니다. 또한 Microsoft Managed Desktop Security Operations [](security-operations.md) Center는 이러한 기술과 함께 다양한 프로세스를 사용합니다.

특히 다음 사항에 유의합니다. 

- [장치 보안](#device-security) - Microsoft Managed Desktop 장치의 보안 및 보호
- [ID 및 액세스 관리](#identity-and-access-management) - Azure Active Directory ID 서비스를 통해 디바이스의 보안 사용 관리
- [네트워크 보안](#network-security) - VPN 정보 및 Microsoft Managed Desktop 권장 솔루션 및 설정
- [정보 보안](#information-security) - 중요한 정보를 추가로 보호하기 위한 선택적 사용 가능한 서비스 

Microsoft Managed Desktop에서 사용하는 데이터 저장소, 사용 현황 및 보안 사례에 대한 자세한 내용은 백서(.)를 [https://aka.ms/mmd-data](https://aka.ms/mmd-data) 참조하세요.


## <a name="device-security"></a>장치 보안

Microsoft Managed Desktop은 모든 관리되는 장치를 보호하고 다음 서비스를 사용하여 최대한 일찍 위협을 감지합니다.

서비스 | 설명
--- | ---
바이러스 검사 | Microsoft Defender AV가 설치 및 구성됩니다.<br>Microsoft Defender AV 정의는 최신입니다.
전체 볼륨 암호화 |    Windows BitLocker는 Microsoft Managed Desktop 장치용 볼륨 암호화 솔루션입니다.<br><br>조직이 서비스에 온보드된 후 장치가 절전 모드에 있을 때 또는 해제된 경우 로컬 데이터에 대한 무단 액세스를 방지하기 위해 TPM(신뢰 플랫폼 모듈)이 기본 제공된 Windows BitLocker를 사용하여 암호화됩니다. 
모니터링 |    끝점용 Microsoft Defender는 모든 Microsoft Managed Desktop 장치에서 보안 위협 모니터링에 사용됩니다. 끝점용 Defender를 사용하면 엔터프라이즈 고객이 회사 네트워크에서 고급 위협을 감지, 조사 및 대응할 수 있습니다. 자세한 내용은 [끝점용 Microsoft Defender를 참조하세요.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
운영 체제 업데이트 |  Microsoft Managed Desktop 장치는 항상 최신 보안 업데이트로 보호됩니다.
보안 장치 구성 |   Microsoft Managed Desktop은 Microsoft 보안 기준을 구현합니다. 자세한 내용은 [Windows 보안 기준을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>ID 및 액세스 관리

ID 및 액세스 관리는 회사 자산 및 업무상 중요한 데이터를 보호합니다. Microsoft Managed Desktop은 Azure AD(Azure Active Directory) 관리 ID에 안전하게 사용하도록 장치를 구성합니다. Azure AD 테넌트에서 정확한 정보를 유지 관리하는 것은 고객의 책임입니다. 

서비스 | 설명
--- | ---
생체 인식 인증 |  Windows Hello를 사용하면 사용자가 얼굴이나 PIN을 사용하여 로그인할 수 있어 암호를 잊어버리거나 도용하기 더 어려워질 수 있습니다. 고객은 하이브리드 구성에서 이 서비스를 사용하기 위해 해당 On-프레미스 Active Directory에 필요한 필수 구성을 구현해야 합니다. 자세한 내용은 [Windows Hello를 참조하세요.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
표준 사용자 권한 |  시스템을 보호하고 보안을 더 안전하게 유지하려면 사용자에게 표준 사용자 권한이 할당됩니다. 이 사용 권한은 Windows Autopilot 첫 실행 경험의 일부로 할당됩니다.



## <a name="network-security"></a>네트워크 보안

고객은 네트워크 보안을 담당합니다. 

서비스 | 설명
--- | ---
VPN | 고객은 제한된 회사 리소스를 인트라넷 외부에 노출할 수 있도록 VPN 인프라를 소유합니다.<br><br>최소 요구 사항: Microsoft Managed Desktop에는 Windows 10 호환 및 지원되는 VPN 솔루션이 필요합니다. 조직에 VPN 솔루션이 필요한 경우 Windows 10을 지원하고 Intune을 통해 패키지 및 배포가 가능해야 합니다. 자세한 내용은 소프트웨어 게시자에 문의하십시오.<br><br>권장 사항:<br>- Microsoft는 Intune을 통해 쉽게 배포하여 VPN 프로필을 푸시할 수 있는 최신 VPN 솔루션을 권장합니다. 이 접근 방식은 회사 네트워크에 액세스할 수 있는 항상 매끄럽고 안정적이며 안전한 방법을 제공합니다. 자세한 내용은 [[Intune의 VPN 설정]을 참조하세요.](https://docs.microsoft.com/intune/vpn-settings-configure)<br>- 사용자 환경에 영향을 줄 수 있는 Microsoft Managed Desktop을 사용하는 동안 굵은 VPN 클라이언트 또는 이전 VPN 클라이언트는 사용하지 않는 것이 좋습니다.<br>- 성능 문제를 방지하기 위해 VPN을 거치지 않고도 나타난 웹 트래픽이 인터넷으로 직접 연결될 것을 권장합니다.<br>- 이상적으로 Microsoft는 VPN 대신 Azure Active Directory 앱 프록시를 사용하는 것이 좋습니다.


## <a name="information-security"></a>정보 보안

이러한 선택적 서비스를 구성하여 회사 고가치 자산을 보호할 수 있습니다. 

서비스 | 설명
--- | ---
데이터 복구  | 장치의 키 폴더에 저장된 정보는 비즈니스용 OneDrive에 백업됩니다. Microsoft Managed Desktop은 비즈니스용 OneDrive와 동기화되지 않은 데이터를 담당하지 않습니다. 
Windows Information Protection |    높은 수준의 정보 보안을 필요로 하는 회사에서는 [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) 및 Azure Information [Protection을 권장합니다.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

