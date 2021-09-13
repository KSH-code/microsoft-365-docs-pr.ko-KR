---
title: Microsoft Managed Desktop 기술
description: 이 문서에서는 이 문서에서 사용되는 기술 및 앱을 Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: dd8293f05a5b88bbd17a3b6760c9a535737fd439
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215405"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop 기술

이 문서에서는 이 문서에서 사용되는 기술 및 앱을 Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise 사용자에 대해 라이선스가 Microsoft Managed Desktop 필요합니다. 서비스의 라이선스 요구 사항에 대한 자세한 내용은 에 대한 사전 요구 [사항을 Microsoft Managed Desktop.](../get-ready/prerequisites.md)

이 문서에서는 필요한 Enterprise 라이선스에 포함된 구성 요소를 요약하고 서비스에서 각 구성 요소를 장치와 함께 사용하는 Microsoft Managed Desktop 설명을 제공합니다. 각 영역에 대한 특정 역할 및 책임은 각 영역 설명서에서 Microsoft Managed Desktop 자세히 설명되어 있습니다. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 또는 E5

| 제품 |정보 |
--- |--- 
엔터프라이즈용 Microsoft 365 앱(64비트) | 이러한 Office 응용 프로그램은 Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote.<br><br>64비트 버전의 Microsoft Project Microsoft Visio 버전은 포함되지 않습니다. 그러나 이러한 응용 프로그램의 설치는 엔터프라이즈용 Microsoft 365 앱 설치에 따라 달라지기 때문에 Microsoft Managed Desktop 기본 Microsoft Intune 배포 및 보안 그룹을 만들었다가 사용이 허가된 사용자에게 이러한 응용 프로그램을 배포하는 데 사용할 수 있습니다. 자세한 내용은 장치에서 Microsoft Project 또는 Microsoft Visio [설치를 Microsoft Managed Desktop 참조하세요.](../get-started/project-visio.md)
OneDrive |Azure Active Directory Single Sign-On은 사용자가 처음 로그인할 때 사용할 수 OneDrive.<br><br>"데스크톱", "문서" 및 "그림" 폴더에 대한 알려진 폴더 리디렉션이 포함됩니다. 를 사용하도록 설정하고 Microsoft Managed Desktop.
스토어 앱 | Microsoft Sway 및 Power BI 함께 배송되지 않습니다. 이러한 앱은 앱에서 다운로드할 수 Microsoft Store.
Win32 응용 프로그램 | Teams 함께 제공되지 않지만 Microsoft에서 패키지로 Microsoft Managed Desktop 장치용입니다. Azure Information Protection 클라이언트는 디바이스와 함께 제공되지 않지만 배포를 위해 패키지로 만들 수 있습니다.
웹 응용 프로그램 | Yammer, Office, Delve, Flow, StaffHub, Power Apps 및 Planner에서 사용할 수 없습니다. 사용자는 브라우저를 사용하여 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.

## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise 끝점용 Microsoft Defender를 통해 E5 또는 E3

IT 관리자는 다음 설정을 구성하는 것이 좋습니다. 이러한 설정은 기본 설정의 일부로 포함되거나 Microsoft Managed Desktop.

제품  |정보
--- | ---
비즈니스용 Windows Hello | 암호를 Windows Hello 장치를 위한 강력한 2단계 인증으로 바꾸기 위해 비즈니스용 Microsoft Managed Desktop 합니다. 자세한 내용은 비즈니스용 Windows Hello [을 참조하세요.](/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Application Virtualization | Intune Win32 앱 관리 클라이언트를 사용하여 App-V(Application Virtualization) 패키지를 배포할 수 있습니다. 자세한 내용은 [Application Virtualization 을 참조하세요.](/windows/application-management/app-v/appv-technical-reference)
Microsoft 365 손실 방지 | 중요한 Microsoft 365 항목에 대해 수행되는 작업을 모니터링하고 해당 항목의 의도하지 않은 공유를 방지하는 데 도움이 되는 데이터 손실 방지 기능을 구현해야 합니다. 자세한 내용은 데이터 [손실 Microsoft 365 참조하세요.](../../compliance/endpoint-dlp-learn-about.md)

다음의 일부로 포함되고 관리되는 Microsoft Managed Desktop.

제품 |정보
--- |---
BitLocker 드라이브 암호화 | BitLocker 드라이브 암호화는 모든 시스템 드라이브를 암호화하는 데 사용됩니다. 자세한 내용은 [BitLocker 드라이브 암호화를 참조하세요.](/windows/security/information-protection/bitlocker/bitlocker-overview)
Windows Defender System Guard | 시작할 때 시스템의 무결성을 보호하고 시스템 무결성이 참으로 유지 관리되고 있는지 유효성을 검사합니다. 자세한 내용은 System [Guard Windows Defender 참조하세요.](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Windows Defender Credential Guard | Windows Defender Credential Guard는 권한 있는 시스템 소프트웨어만 액세스할 수 있도록 가상화 기반 보안을 사용하여 비밀을 격리합니다. 자세한 내용은 System [Guard Windows Defender 참조하세요.](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
끝점용 Microsoft Defender - 끝점 감지 및 응답 | Microsoft Managed Desktop 보안 운영은 경고에 응답하고 끝점 감지 및 응답을 사용하여 위협을 수정하기 위한 조치를 취합니다. 자세한 내용은 [끝점용 Microsoft Defender - 끝점 검색 및 응답을 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
끝점용 Microsoft Defender - 위협 전문가 | Microsoft Managed Desktop 공격 알림을 통해 위협 전문가의 인사이트 및 데이터와 통합됩니다. 이 서비스를 사용하도록 설정하기 전에 추가 동의를 제공해야 합니다. 자세한 내용은 [Endpoint용 Microsoft Defender - 위협 전문가를 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
끝점용 Microsoft Defender - 위협 및 취약성 관리 | 서비스 계획의 향후 사용에 Microsoft Managed Desktop 필요합니다. 자세한 내용은 [끝점용 Microsoft Defender - 위협 및 취약성 관리를 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
끝점용 Microsoft Defender - 공격 표면 감소 | 공격 표면 감소는 공격자에 의해 자주 남용되는 위험한 소프트웨어 동작을 대상으로 합니다. 자세한 내용은 [끝점용 Microsoft Defender - 공격 표면 감소를 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
끝점용 Microsoft Defender - Exploit Protection | 악용을 사용하여 장치를 감염하고 악용 완화 기술을 운영 체제 프로세스와 앱에 자동으로 적용하여 확산되는 맬웨어로부터 보호합니다. 자세한 내용은 [끝점용 Microsoft Defender - Exploit Protection을 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
끝점용 Microsoft Defender - 네트워크 보호 | 네트워크 보호는 신뢰도 Microsoft Defender SmartScreen 연결을 시도하는 모든 아웃바운드 HTTP 및 HTTPS 트래픽을 차단하기 위해 네트워크 보호 범위를 확장합니다. 자세한 내용은 [끝점용 Microsoft Defender - 네트워크 보호를 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Microsoft Defender 변조 보호 | Windows 변조 보호는 바이러스 백신 보호와 같은 보안 설정이 변경되지 않도록 하는 데 사용됩니다. 자세한 내용은 [Microsoft Defender 변조 보호를 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)
Microsoft Defender 바이러스 백신 동작 기반,추론적 및 실시간 바이러스 백신 보호 | 맬웨어로 검색되지 않을 수 있는 파일 및 프로세스 위협을 항상 검사합니다. 자세한 내용은 동작 기반, Microsoft Defender 바이러스 백신 및 실시간 바이러스 백신 보호를 [참조하세요.](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md)
Microsoft Defender 바이러스 백신 클라우드 제공 보호 | 새로운 위협과 새로운 위협에 대해 거의 즉각적이고 자동화된 동적 보호 기능을 제공합니다. 자세한 내용은 클라우드 [제공 Microsoft Defender 바이러스 백신 보호를 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "한시적 차단" | 사용자가 의심스러우거나 알 수 없는 파일을 Windows 새 맬웨어를 검색하고 차단합니다. 자세한 내용은 [Microsoft Defender 차단을 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Microsoft Defender 바이러스 백신 잠재적으로 원치 않는 응용 프로그램 | 잠재적으로 원치 않는 응용 프로그램은 컴퓨터의 실행 속도가 느려지거나, 예기치 않은 광고를 표시하거나, 최악의 경우 예기치 않게 또는 원치 않는 다른 소프트웨어를 설치할 수 있는 앱을 차단하는 데 사용됩니다. 자세한 내용은 [잠재적으로 Microsoft Defender 바이러스 백신 응용 프로그램을 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender 고급 보안이 있는 방화벽 | 장치에 대한 호스트 기반의 양측 네트워크 트래픽 필터링은 Windows Defender 들어오거나 로컬 장치로 유입되는 권한이 없는 네트워크 트래픽을 차단합니다. 자세한 내용은 고급 [보안이 Windows Defender 방화벽을 참조하세요.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
사용자 계정 컨트롤 | 작업 또는 작업에 관리자 계정 유형 액세스 권한이 필요한 경우 사용자 계정 컨트롤이 보안 데스크톱으로 전환됩니다. Microsoft Managed Desktop 사용자에게 등록 시 표준 사용자 액세스 권한이 할당됩니다. 자세한 내용은 사용자 계정 [컨트롤 을 참조하세요.](/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

제품 |정보
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 | MDM 디바이스를 관리하기 위해 Enterprise Mobility + Security E3 기능을 사용할 수 있습니다. 선택적 기능으로 Azure Active Directory Premium P2 사용할 수 Microsoft Managed Desktop.
Microsoft Cloud App Security | 이 선택적 기능을 사용자와 함께 사용할 Microsoft Managed Desktop.
Azure Information Protection P2  | 이 선택적 기능을 사용자와 함께 사용할 Microsoft Managed Desktop.
