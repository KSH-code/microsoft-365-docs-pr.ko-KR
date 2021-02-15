---
title: Microsoft Managed Desktop 기술
description: 이 문서에서는 Microsoft Managed Desktop에서 사용되는 기술 및 앱을 나열합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094870"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop 기술

이 문서에서는 Microsoft Managed Desktop에서 사용되는 기술 및 앱을 나열합니다.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

모든 Microsoft Managed Desktop 사용자에게는 Microsoft 365 Enterprise 라이선스가 필요합니다. 서비스의 라이선스 요구 사항에 대한 자세한 내용은 [Microsoft Managed Desktop의 사전 요구 사항을 참조하세요.](../get-ready/prerequisites.md)

이 문서에서는 필수 Enterprise 라이선스에 포함된 구성 요소에 대해 간략히 설명하고 서비스가 Microsoft Managed Desktop 장치에서 각 구성 요소를 사용하는 방법에 대한 설명을 제공합니다. 각 영역에 대한 특정 역할 및 책임은 Microsoft Managed Desktop 설명서에서 자세히 설명됩니다. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 또는 E5
 |
 --- | ---
엔터프라이즈용 Microsoft 365 앱(64비트) | 이러한 Office 응용 프로그램은 Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote와 함께 발송됩니다.<br><br>64비트 정식 버전의 Microsoft Project 및 Microsoft Visio는 포함되지 않습니다. 그러나 이러한 응용 프로그램의 설치는 엔터프라이즈용 Microsoft 365 앱 설치에 따라 달라지기 때문에 Microsoft Managed Desktop은 기본 Microsoft Intune 배포 및 보안 그룹을 만들어 라이선스가 있는 사용자에게 이러한 응용 프로그램을 배포하는 데 사용할 수 있습니다. 자세한 내용은 Microsoft Managed Desktop 장치에 Microsoft Project 또는 [Microsoft Visio 설치를 참조하세요.](../get-started/project-visio.md)
OneDrive |Azure Active Directory Single Sign-On은 사용자가 OneDrive에 처음 로그인할 때 사용하도록 설정됩니다.<br><br>"데스크톱", "문서" 및 "그림" 폴더에 대한 알려진 폴더 리디렉션이 포함됩니다. Microsoft Managed Desktop에서 사용하도록 설정하고 구성합니다.
스토어 앱 |    Microsoft Sway 및 Power BI는 디바이스와 함께 배송되지 않습니다. 이러한 앱은 Microsoft Store에서 다운로드할 수 있습니다.
Win32 응용 프로그램 |    Teams는 디바이스와 함께 제공되지 않지만 Microsoft에서 Microsoft Managed Desktop 장치용 패키지 및 제공합니다. Azure Information Protection Client는 디바이스와 함께 제공되지 않지만 배포를 위해 패키지로 만들 수 있습니다.
웹 응용 프로그램 |  Yammer, 브라우저의 Office, Delve, Flow, StaffHub, PowerApps 및 Planner는 디바이스와 함께 배송되지 않습니다. 사용자는 브라우저를 사용하여 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.



## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender가 있는 Windows 10 Enterprise E5 또는 E3
권장
 |
 --- | ---
[비즈니스용 Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) | 고객은 암호를 Microsoft Managed Desktop 장치에서 사용되는 강력한 2단계 인증으로 바꾸기 위해 비즈니스용 Windows Hello를 구현하는 것이 좋습니다.
[Application Virtualization](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | 고객은 Intune Win32 앱 관리 클라이언트를 사용하여 App-V(Application Virtualization) 패키지를 배포할 수 있습니다.
[Microsoft 365 데이터 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | 고객은 Microsoft 365 DLP(데이터 손실 방지)를 구현하여 중요한 것으로 확인된 항목에 대해 수행되는 작업을 모니터링하고 해당 항목의 의도하지 않은 공유를 방지하는 것이 좋습니다.   

서비스에 포함 및 관리
 |
 --- | ---
[BitLocker 드라이브 암호화](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | BitLocker 드라이브 암호화는 모든 시스템 드라이브를 암호화하는 데 사용됩니다. 
[Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | 시작할 때 시스템의 무결성을 보호하고 시스템 무결성이 참으로 유지 관리되고 있는지 검증합니다.
[Windows Defender Credential Guard]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | Windows Defender Credential Guard는 권한 있는 시스템 소프트웨어만 액세스할 수 있도록 가상화 기반 보안을 사용하여 비밀을 격리합니다.
[끝점용 Microsoft Defender | Endpoint Detection and Response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     Microsoft Managed Desktop Security Operations는 경고에 응답하고 엔드포인트 검색 및 응답을 사용하여 위협을 수정하기 위한 조치를 취합니다.
[끝점용 Microsoft Defender | 위협 전문가](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | Microsoft Managed Desktop은 대상 공격 알림을 통해 위협 전문가의 인사이트 및 데이터와 통합됩니다. 고객은 이 서비스를 사용하도록 설정하기 전에 추가 동의를 제공해야 합니다.  
[끝점용 Microsoft Defender | 위협 및 취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | Microsoft Managed Desktop 서비스 계획에서 향후 사용하려면 필요합니다.
[끝점용 Microsoft Defender | 공격 표면 축소](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | 공격 노출 표면 감소는 공격자에 의해 자주 남용되는 위험한 소프트웨어 동작을 대상으로 합니다.
[끝점용 Microsoft Defender | Exploit Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | 악용을 사용하여 장치를 감염하고 악용 완화 기술을 운영 체제 프로세스와 앱 모두에 자동으로 적용하여 확산되는 맬웨어로부터 보호합니다.
[끝점용 Microsoft Defender | Network Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | 네트워크 보호는 Microsoft Defender SmartScreen의 범위를 확장하여 신뢰도 낮은 원본에 연결을 시도하는 모든 아웃바운드 HTTP 트래픽을 차단합니다.
[Microsoft Defender 변조 방지](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | Windows 변조 방지는 바이러스 백신 보호와 같은 보안 설정이 변경되지 않도록 하는 데 사용됩니다.
[Microsoft Defender 바이러스 백신 동작 기반, 방어적 및 실시간 바이러스 백신 보호]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | 항상 맬웨어로 검색되지 않을 수 있는 파일 및 프로세스 위협을 검사합니다.
[Microsoft Defender 바이러스 백신 클라우드 제공 보호](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | 새로운 위협에 대해 거의 즉각적이고 자동화된 동적 보호 기능을 제공합니다.
[Microsoft Defender 차단을 최초로 차단](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | Windows에서 의심스러운 파일 또는 알 수 없는 파일을 감지할 때 새 맬웨어를 검색하고 차단합니다.
[Microsoft Defender AV 잠재적으로 원치 않는 응용 프로그램](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | PUA(사용자들이 원치 않는 응용 프로그램)를 사용하여 컴퓨터 실행 속도가 느려지거나 예기치 않은 광고를 표시하거나, 최악의 경우 예기치 않게 또는 원치 않는 다른 소프트웨어를 설치할 수 있는 앱을 차단합니다.
[Windows Defender 보안이 있는 방화벽](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | 디바이스에 대한 호스트 기반의 양측 네트워크 트래픽 필터링을 Windows Defender 방화벽은 로컬 장치로 유입되거나 유출되는 권한이 없는 네트워크 트래픽을 차단합니다.
[사용자 계정 컨트롤](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | 작업 또는 작업에 관리자 계정 유형 액세스 권한이 필요한 경우 사용자 계정 컨트롤이 보안 데스크톱으로 전환됩니다. Microsoft Managed Desktop 사용자에게는 등록 시 Standard 사용자 액세스 권한이 할당됩니다. 


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Enterprise Mobility + Security E3 및 Azure Active Directory Premium P2의 모든 기능을 사용하여 MDM 장치를 관리할 수 있습니다.
Microsoft Cloud App Security |  Microsoft Managed Desktop에서 이 선택적 기능을 사용할 수 있습니다.
Azure Information Protection P2  | Microsoft Managed Desktop에서 이 선택적 기능을 사용할 수 있습니다.
