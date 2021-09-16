---
title: Intune을 사용하여 끝점용 Microsoft Defender 관리
description: Intune을 사용하여 끝점용 Microsoft Defender를 관리하는 방법 학습
keywords: 마이그레이션 후, 관리, 운영, 유지 관리, 사용률, intune, Endpoint용 Microsoft Defender, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 07/29/2021
ms.reviewer: chventou
ms.openlocfilehash: 90cc05e801198ad2df8516fb2d9aa1f425f943c9
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59402193"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Intune을 사용하여 끝점용 Microsoft Defender 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

디바이스에 [Microsoft Endpoint Manager](/mem)대한 조직의 위협 방지 기능을 관리하기 위해 Microsoft Intune(Intune)를 포함하는 Microsoft Endpoint Manager 를 사용하는 것이 좋습니다. [자세한 내용은 Endpoint Manager.](/mem/endpoint-manager-overview)

이 문서에서는 Intune에서 끝점용 Microsoft Defender 설정을 찾는 방법을 설명하고 수행할 수 있는 다양한 작업을 나열합니다.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Intune에서 끝점에 대한 Microsoft Defender 설정 찾기

> [!IMPORTANT]
> 이 문서에 설명된 설정을 구성하려면 Intune에 전역 관리자 또는 서비스 관리자 역할이 할당되어 있어야 합니다. 자세한 내용은 **[관리자 유형(Intune)을 참조합니다.](/mem/intune/fundamentals/users-add#types-of-administrators)**

1. Azure Portal()로 [https://portal.azure.com](https://portal.azure.com) 이동하여 로그인합니다.

2. **Azure 서비스에서** **Intune 을 선택하세요.**

3. 왼쪽의 탐색 창에서 장치 구성 을 선택한 다음 관리 아래에서 프로필 **을 선택 합니다.**

4. 기존 프로필을 선택하거나 새 프로필을 만들 수 있습니다.

> [!TIP]
> 도움이 필요하신가요? **[Intune에서 끝점에 Microsoft Defender 사용을 참조합니다.](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Intune을 통해 끝점용 Microsoft Defender 구성

다음 표에는 Intune을 사용하여 끝점용 Microsoft Defender를 구성하기 위해 수행할 수 있는 다양한 작업이 나열됩니다. 모든 것을 한 번만 구성할 수 있습니다. 작업을 선택하고 해당 리소스를 읽은 다음 계속 진행합니다.

<br/><br/>

|작업|자세한 정보를 알아볼 수 있는 리소스|
|---|---|
|**Intune을** 사용하여 조직의 장치를 관리하여 장치에 저장된 장치 및 데이터를 보호합니다.|[Microsoft Intune을 통해 장치 보호](/mem/intune/protect/device-protect)|
|**Endpoint용 Microsoft Defender와 Intune을** Mobile Threat Defense 솔루션으로 통합 <br/>*(Android 장치 및 장치 및 Windows 10 이상용)*|[Intune에서 조건부 액세스를 통해 끝점에 대한 Microsoft Defender 준수 적용](/mem/intune/protect/advanced-threat-protection)|
|**조건부 액세스를 사용하여** 전자 메일 및 회사 리소스에 연결할 수 있는 장치 및 앱 제어|[끝점용 Microsoft Defender에서 조건부 액세스 구성](/microsoft-365/security/defender-endpoint/configure-conditional-access)|
|**정책 Microsoft Defender 바이러스 백신 공급자를** 사용하여 정책 설정 [구성(정책 CSP)](/windows/client-management/mdm/policy-configuration-service-provider)|[장치 제한: Microsoft Defender 바이러스 백신](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) <p> [정책 CSP - 끝점용 Microsoft Defender](/windows/client-management/mdm/policy-csp-defender)|
|**필요한 경우 제외를 지정합니다Microsoft Defender 바이러스 백신** <p> *일반적으로 제외를 적용할 필요는 없습니다. Microsoft Defender 바이러스 백신 운영 체제 동작 및 일반적인 관리 파일(예: 엔터프라이즈 관리, 데이터베이스 관리 및 기타 엔터프라이즈 시나리오에 사용되는 파일)을 기반으로 하는 여러 자동 제외가 포함됩니다.*|[현재 지원되는 Enterprise 실행 중인 컴퓨터의 바이러스 검사 권장 Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers) <p> [장치 제한: Microsoft Defender 바이러스 백신 디바이스에 대한 Windows 10 제외](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <p> [Microsoft Defender 바이러스 백신 또는 2019에 대한 Windows Server 2016 제외 구성](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**공격자가 자주 남용되는** 소프트웨어 동작을 대상으로 공격 표면 감소 규칙을 구성합니다. <p> *처음에 감사 모드에서 [](/microsoft-365/security/defender-endpoint/audit-windows-defender) 공격 표면 감소 규칙을 구성합니다(최소 1주 및 최대 2개월). 템플릿을 사용하여 상태를 Power BI(템플릿을 얻음)를 사용하여 상태를 모니터링한 다음 준비가 되면 해당 규칙을 활성 모드로 설정할 수 있습니다.[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)*|[끝점용 Microsoft Defender의 감사 모드](/microsoft-365/security/defender-endpoint/audit-windows-defender) <p> [끝점 보호: 공격 표면 감소](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction) <p> [공격 표면 감소 규칙에 대해 자세히 알아보십시오.](/microsoft-365/security/defender-endpoint/attack-surface-reduction) <p> [Tech Community 블로그 게시물: 공격 표면 감소 규칙 디미스ifying - 1부](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)|
|**신뢰도가 낮은** 모든 앱에서 IP 주소 또는 도메인으로의 아웃바운드 연결을 차단하도록 네트워크 필터링 구성  <p> *네트워크 필터링을 네트워크 [보호라고도 합니다.](/microsoft-365/security/defender-endpoint/network-protection)* <p> *장치에 최신 Windows 10 맬웨어 방지 플랫폼 업데이트가 설치되어 [있는지](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) 확인합니다.*|[끝점 보호: 네트워크 필터링](/mem/intune/protect/endpoint-protection-windows-10#network-filtering) <p> [이벤트 뷰어에서 Windows 이벤트 검토](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer)|
|**랜섬웨어로부터 보호하도록** 제어된 폴더 액세스 구성 <p> *[제어된 폴더 액세스를](/microsoft-365/security/defender-endpoint/controlled-folders) 랜섬웨어 방지 보호라고도 합니다.*|[끝점 보호: 제어된 폴더 액세스](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <p> [Intune에서 제어된 폴더 액세스 사용](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)|
|**악용을** 사용하여 다른 장치를 확산하고 감염시킬 수 있는 맬웨어로부터 조직의 장치를 보호하도록 Exploit Protection 구성 <p> *[Exploit Protection을](/microsoft-365/security/defender-endpoint/exploit-protection) Exploit Guard라고도 합니다.*|[끝점 보호: Microsoft Defender Exploit Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <p> [Intune에서 Exploit Protection 사용](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune)|
|**인터넷의 Microsoft Defender SmartScreen** 파일로부터 보호하기 위해 구성합니다. <p> *Microsoft Edge 장치에 설치해야 합니다. Google Chrome 및 FireFox 브라우저에서 보호를 위해 Exploit Protection을 구성합니다.*|[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <p> [장치 제한: Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen) <p> [Intune에서 SmartScreen을 관리하기 위한 정책 설정](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)|
|**Microsoft Defender 방화벽을** 구성하여 조직의 장치로 들어와서 유입되는 권한이 없는 네트워크 트래픽을 차단합니다.|[끝점 보호: Microsoft Defender 방화벽](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <p> [고급 보안이 있는 Microsoft Defender 방화벽](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)|
|**암호화 및 BitLocker를** 구성하여 암호화를 실행하는 조직의 장치에 대한 정보를 Windows|[끝점 보호: Windows 암호화](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption) <p> [Windows 10용 BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview)|
|자격 증명 도난 공격으로부터 보호하도록 **Microsoft Defender Credential Guard** 구성|Windows 10, Windows Server 2016 및 Windows Server 2019에 대한 자세한 내용은 [Endpoint protection: Microsoft Defender Credential Guard를 참조합니다.](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <p> Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 및 Windows Server 2012 R2의 경우 [PtH(Pass-the-Hash)](https://www.microsoft.com/download/details.aspx?id=36036) 공격 및 기타 자격 증명 도난 완화, 버전 1 및 2를 참조합니다.|
|조직의 장치에서 앱을 감사할지 또는 신뢰할지 여부를 선택하도록 **Microsoft Defender** 응용 프로그램 제어 구성 <p> *Microsoft Defender 응용 프로그램 제어를 [AppLocker라고도 합니다.](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)*|[Microsoft Defender 응용 프로그램 제어 정책을 사용하여 Microsoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune) <p> [끝점 보호: Microsoft Defender 응용 프로그램 제어](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control) <p> [AppLocker CSP](/windows/client-management/mdm/applocker-csp)|
|**허가되지 않은** 주변 장치의 위협이 장치를 해치지 않도록 장치 제어 및 USB 주변 장치 액세스를 구성합니다.|[Endpoint 및 Intune용 Microsoft Defender를 사용하여 USB 장치 및 기타 이동식 미디어 제어](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)|

## <a name="configure-your-microsoft-365-defender-portal"></a>사용자 Microsoft 365 Defender 구성

아직 수행하지 않은 경우 경고를 보고Microsoft 365 Defender 위협 방지 기능을 구성하고 조직의 전반적인 보안 상태와 관련한 자세한 정보를 볼 수 있도록 Microsoft 365 Defender 포털을 구성합니다. 자세한 [내용은 Microsoft 365 Defender.](microsoft-defender-security-center.md) 또한 최종 사용자가 사이트 포털에서 볼 수 있는 기능과 Microsoft 365 Defender 있습니다.

- [개요 Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [끝점 보호: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>다음 단계

- [위협 및 취약성 관리에 대한 개요 보기](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Microsoft 365 Defender 포털 보안 작업 대시보드 방문](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
