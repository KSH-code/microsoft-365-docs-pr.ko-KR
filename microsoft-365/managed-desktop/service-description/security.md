---
title: Microsoft Managed Desktop의 보안 기술
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1e50b07208df46b199aada9c2ccbe04cc1c1ae72
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289486"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 보안 기술

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop은 다양 한 Microsoft 기술을 사용 하 여 관리 되는 장치 및 데이터를 안전 하 게 보호 합니다. 또한 Microsoft Managed Desktop Security Operations Center는 이러한 기술과 함께 다양 한 [프로세스](security-operations.md) 를 사용 합니다.

특히 다음 사항에 유의합니다. 

- [장치 보안](#device-security) -Microsoft Managed Desktop 장치에 대 한 보안 및 보호
- [Id 및 액세스 관리](#identity-and-access-management) -Azure Active Directory Identity services를 통한 장치 보안 사용 관리
- [네트워크 보안](#network-security) -VPN 정보 및 Microsoft Managed Desktop 권장 솔루션 및 설정
- [정보 보안](#information-security) -중요 한 정보를 보다 안전 하 게 보호 하는 데 사용할 수 있는 선택적 서비스 

Microsoft Managed Desktop에서 사용 되는 데이터 저장, 사용 및 보안 방법에 대 한 자세한 내용은 당사의 백서를 참조 하세요 [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>장치 보안

Microsoft Managed Desktop은 모든 관리 장치를 보호 하 고 보호할 수 있도록 하며 다음 서비스를 사용 하 여 가능한 한 빨리 위협을 감지 합니다.

서비스 | 설명
--- | ---
바이러스 검사 | Microsoft Defender AV를 설치 하 고 구성 합니다.<br>Microsoft Defender AV 정의가 최신 상태입니다.
전체 볼륨 암호화 |    Windows BitLocker는 Microsoft Managed Desktop 장치에 대 한 볼륨 암호화 솔루션입니다.<br><br>조직이 서비스에 등록 장치가 절전 모드일 때 로컬 데이터에 대 한 무단 액세스를 방지 하기 위해 TPM (기본 제공 트러스트 플랫폼 모듈)이 포함 된 Windows BitLocker를 사용 하 여 디바이스가 암호화 됩니다. 
모니터링 |    Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)은 모든 Microsoft 관리 되는 데스크톱 장치에서 보안 위협 모니터링에 사용 됩니다. 기업 고객은 Microsoft Defender ATP를 사용 하 여 회사 네트워크에서 advanced threat를 감지, 조사 및 응답할 수 있습니다. 자세한 내용은 [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 를 참조 하세요. 
운영 체제 업데이트 |  Microsoft Managed Desktop 장치는 항상 최신 보안 업데이트를 사용 하 여 보호 됩니다.
보안 장치 구성 |   Microsoft Managed Desktop은 Microsoft 보안 기준을 구현 합니다. 자세한 내용은 [Windows 보안 기준을](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) 참조 하십시오.



## <a name="identity-and-access-management"></a>ID 및 액세스 관리

Id 및 액세스 관리 회사 자산 및 업무상 중요 한 데이터를 보호 합니다. Microsoft Managed Desktop azure Active Directory (Azure AD) 관리 id와의 보안 된 사용을 보장 하도록 장치를 구성 합니다. Azure AD 테 넌 트에서 정확한 정보를 유지 관리 하는 것은 고객의 책임입니다. 

서비스 | 설명
--- | ---
생체 인식 인증 |  Windows Hello에서는 사용자가 얼굴 또는 PIN을 사용 하 여 로그인 하 여 암호를 잊거나 도용 하기 어렵게 만듭니다. 고객은 하이브리드 구성에서이 서비스를 사용할 수 있도록 온-프레미스 Active Directory에 필요한 필수 구성 요소를 구현 해야 합니다. 자세한 내용은 [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 를 참조 하세요. 
표준 사용자 권한 |  시스템을 보호 하 고 보다 안전 하 게 보호 하기 위해 사용자에 게 표준 사용자 권한이 할당 됩니다. 이 작업은 Windows Autopilot 경험의 일부로 할당 됩니다.



## <a name="network-security"></a>네트워크 보안

고객은 네트워크 보안을 담당 합니다. 

서비스 | 설명
--- | ---
VPN | 고객은 VPN 인프라를 소유 하 여 제한 된 회사 리소스가 인트라넷 외부에 노출 될 수 있도록 합니다.<br><br>최소 요구 사항: Microsoft Managed Desktop에는 Windows 10 호환 및 지원 되는 VPN 솔루션이 필요 합니다. 조직에서 VPN 솔루션을 필요로 하는 경우에는 Windows 10을 지원 하 고 Intune을 통해 패키지 및 배포 가능 해야 합니다. 자세한 내용은 소프트웨어 게시자에 게 문의 하세요.<br><br>사항이<br>-Microsoft는 VPN 프로필을 푸시 하기 위해 Intune을 통해 쉽게 배포할 수 있는 최신 VPN 솔루션을 권장 합니다. 이를 통해 회사 네트워크에 간편 하 고 안정적 이며 안전 하 게 액세스할 수 있습니다. 자세한 내용은 [[VPN 설정 (Intune)]](https://docs.microsoft.com/intune/vpn-settings-configure)을 참조 하십시오.<br>-굵은 VPN 클라이언트 또는 레거시 VPN 클라이언트는 사용자 환경에 영향을 줄 수 있으므로 Microsoft Managed Desktop을 사용 하는 동안 Microsoft에서 권장 하지 않습니다.<br>-Microsoft에서는 성능 문제가 발생 하지 않도록 하기 위해 VPN을 사용 하지 않고 나가는 웹 트래픽이 인터넷으로 직접 이동 하는 것이 좋습니다.<br>가장 이상적으로 말하면 VPN 대신 Azure Active Directory 앱 프록시를 사용 하는 것이 좋습니다.


## <a name="information-security"></a>정보 보안

이러한 선택적 서비스를 구성 하 여 회사 높은 가치 자산을 보호할 수 있습니다. 

서비스 | 설명
--- | ---
데이터 복구  | 장치의 주요 폴더에 저장 된 정보는 비즈니스용 OneDrive에 백업 됩니다. Microsoft Managed Desktop은 비즈니스용 OneDrive와 동기화 되지 않은 데이터에 대해 책임을 지지 않습니다. 
Windows Information Protection |    높은 수준의 정보 보안이 필요한 회사의 경우 [Windows Information protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) 및 [Azure information protection](https://www.microsoft.com/cloud-platform/azure-information-protection)을 권장 합니다. 

