---
title: PowerShell, WMI 및 2016을 사용하여 끝점에 대한 Microsoft Defender MPCmdRun.exe
description: PowerShell, WMI 및 PowerShell을 사용하여 끝점용 Microsoft Defender를 관리하는 방법을 MPCmdRun.exe
keywords: 마이그레이션 후, 관리, 운영, 유지 관리, 사용률, PowerShell, WMI, MPCmdRun.exe, windows defender Advanced Threat Protection, atp, edr
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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 3d76beed9cb63fdbd56f9a97f925a99cbc01e1b8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070239"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>PowerShell, WMI 및 PowerShell을 사용하여 끝점에 대한 Microsoft Defender를 MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Microsoft [Endpoint Manager를](https://docs.microsoft.com/mem) 사용하여 장치에 대한 조직의 위협 방지 기능을 관리하는 것이 좋습니다(끝점이라고도 합니다). Endpoint Manager에는 [Microsoft Intune 및](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) [Microsoft Endpoint Configuration Manager가 포함됩니다.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) 
> - [Endpoint Manager에 대해 자세히 알아보시고](https://docs.microsoft.com/mem/endpoint-manager-overview)
> - [Configuration Manager 및 Intune을 사용하여 Windows 10 장치에서 끝점용 Microsoft Defender 공동 관리](manage-atp-post-migration-intune.md)
> - [Intune을 사용하여 끝점용 Microsoft Defender 관리](manage-atp-post-migration-intune.md) 

[PowerShell,](#configure-microsoft-defender-for-endpoint-with-powershell)WMI(Windows [Management Instrumentation)](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) 및 [Microsoft 맬웨어](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) 보호 명령줄 유틸리티(WMI)를 사용하여 장치에서 일부 Microsoft Defender 바이러스 백신 설정을 관리할 MPCmdRun.exe. 예를 들어 일부 Microsoft Defender 바이러스 백신 설정을 관리할 수 있습니다. 또한 경우에 따라 공격 표면 감소 규칙을 사용자 지정하고 보호 설정을 악용할 수 있습니다. 

> [!IMPORTANT]
> PowerShell, WMI 또는 WMI를 사용하여 구성하는 위협 방지 MCPmdRun.exe Intune 또는 Configuration Manager와 함께 배포된 구성 설정으로 덮어 사용할 수 있습니다.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>PowerShell을 통해 끝점에 대한 Microsoft Defender 구성

PowerShell을 사용하여 Microsoft Defender 바이러스 백신, 악용 방지 및 공격 표면 축소 규칙을 관리할 수 있습니다.

|작업   |자세한 정보를 알아볼 수 있는 리소스  |
|---------|---------|
|**Microsoft Defender 바이러스 백신 관리** <br/><br/>*맬웨어 방지 보호 상태를 보고, 바이러스 백신 검사에 대한 기본 & 업데이트를 구성하고, 바이러스 백신 보호를 다른 변경합니다.*    |[PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[PowerShell cmdlet을 사용하여 클라우드 제공 보호 사용](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**조직의 장치에** 대한 위협을 완화하도록 exploit Protection 구성<br/><br/> *처음에는 감사 모드에서 Exploit Protection을 [사용하는](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) 것이 좋습니다. 이렇게 하면 악용 방지가 조직에서 사용하는 앱에 어떤 영향을 주는지 알 수 있습니다.*     | [Exploit Protection 사용자 지정](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[악용 방지를 위한 PowerShell cmdlet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|**PowerShell을 사용하여 공격** 표면 감소 규칙 구성 <br/><br/>*PowerShell을 사용하여 공격 표면 감소 규칙에서 파일 및 폴더를 제외할 수 있습니다.* |[공격 표면 감소 규칙 사용자 지정: PowerShell을 사용하여 폴더에서 파일 & 제외](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>또한 PowerShell을 사용하여 공격 표면 감소 규칙을 설정하는 데 사용할 수 있는 [António Vasconcelo의](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)그래픽 사용자 인터페이스 도구를 참조하세요. |
|**PowerShell을 사용하여** 네트워크 보호 사용 <br/><br/>*PowerShell을 사용하여 네트워크 보호를 사용하도록 설정할 수 있습니다.* |[PowerShell을 통해 네트워크 보호 켜기](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**랜섬웨어로부터 보호하도록** 제어된 폴더 액세스 구성 <br/><br/>*[제어된 폴더 액세스를](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) 랜섬웨어 방지 보호라고도 합니다.* |[PowerShell을 사용하여 제어된 폴더 액세스 사용](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**Microsoft Defender 방화벽을** 구성하여 조직의 장치로 들어와서 유입되는 권한이 없는 네트워크 트래픽을 차단합니다. |[Microsoft Defender Firewall with Advanced Security Administration using Windows PowerShell](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|Windows를 실행하는 조직의 장치에 대한 정보를 보호하도록 암호화 및 **BitLocker** 구성 |[BitLocker PowerShell 참조 가이드](https://docs.microsoft.com/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>WMI(Windows Management Instrumentation)를 통해 끝점에 대한 Microsoft Defender 구성

WMI는 설정을 검색, 수정 및 업데이트할 수 있는 스크립팅 인터페이스입니다. 자세한 내용은 [WMI 사용을 참조합니다.](https://docs.microsoft.com/windows/win32/wmisdk/using-wmi) 

|작업   |자세한 정보를 알아볼 수 있는 리소스  |
|---------|---------|
|**장치에서 클라우드 제공** 보호 사용    |[WMI(Windows Management Instruction)를 사용하여 클라우드 제공 보호 사용](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|Microsoft Defender **바이러스 백신에** 대한 설정 검색, 수정 및 업데이트     | [WMI를 사용하여 Microsoft Defender 바이러스 백신 구성 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[사용 가능한 WMI 클래스 및 예제 스크립트 목록 검토](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>또한 보관된 [WMIv2 Windows Defender 참조 정보를 참조하세요.](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Microsoft 맬웨어 보호 유틸리티(Command-Line 유틸리티)를 사용하여 끝점에 대한 Microsoft Defender MPCmdRun.exe)

개별 장치에서 검색을 실행하고, 진단 추적을 시작하고, 보안 인텔리전스 업데이트를 확인하고, 명령줄 도구를 사용하여 mpcmdrun.exe 있습니다. 유틸리티는 에서 찾을 수 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 있습니다. 명령 프롬프트에서 실행합니다.

|작업   |자세한 정보를 알아볼 수 있는 리소스  |
|---------|---------|
|**Microsoft Defender 바이러스 백신 관리**  |[Microsoft Defender 바이러스 백신을 구성하고 mpcmdrun.exe](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Microsoft Defender 보안 센터 구성

아직 수행하지 않은 경우 경고를 보고, 위협 방지 기능을 구성하고, 조직의 전반적인 보안태세에 대한 자세한 정보를 볼 수 있도록 **Microsoft Defender** 보안 센터( [https://securitycenter.windows.com](https://securitycenter.windows.com) )를 구성합니다. 

Microsoft Defender 보안 센터에서 최종 사용자가 볼 수 있는 기능의 여부와 기능을 구성할 수 있습니다.

- [Microsoft Defender 보안 센터 개요](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [끝점 보호: Microsoft Defender 보안 센터](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>다음 단계

- [위협 및 취약성 관리 개요 보기](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Microsoft Defender 보안 센터 보안 작업 대시보드 방문](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Intune을 사용하여 끝점용 Microsoft Defender 관리](manage-atp-post-migration-intune.md)
