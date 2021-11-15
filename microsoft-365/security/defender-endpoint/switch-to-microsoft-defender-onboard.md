---
title: 끝점용 Microsoft Defender로 전환 - 온보딩
description: 끝점용 Microsoft Defender로 전환합니다. 장치를 온보드한 다음 Microsoft가 아닌 다른 솔루션을 제거합니다.
keywords: migration, Microsoft Defender for Endpoint, edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.custom:
- migrationguides
- admindeeplinkDEFENDER
ms.topic: article
ms.date: 10/07/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: ee864bb33b03f51f2529bca0026290fa675c1c4e
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962521"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Endpoint용 Microsoft Defender로 전환 - 3단계: 온보딩

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![1단계: 준비3.](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[1 단계: 준비](switch-to-microsoft-defender-prepare.md) | [![2 단계: 설정](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[2 단계: 설정](switch-to-microsoft-defender-setup.md) | ![3 단계: 온보딩](images/phase-diagrams/onboard.png)<br/>3 단계: 온보딩 |
|--|--|--|
|| |*여기 있습니다!* |

**끝점용 [Defender로](switch-to-microsoft-defender-migration.md#the-migration-process)전환하는 3단계입니다.** 이 마이그레이션 단계에는 다음 단계가 포함됩니다.

1. [끝점용 Defender에 장치를 온보딩합니다.](#onboard-devices-to-microsoft-defender-for-endpoint)
2. [검색 테스트를 실행합니다.](#run-a-detection-test)
3. [끝점에서 Microsoft Defender 바이러스 백신 수동 모드에 있는지 확인](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)
4. [에 대한 업데이트를 Microsoft Defender 바이러스 백신.](#get-updates-for-microsoft-defender-antivirus)
5. [Microsoft가 아닌 솔루션을 제거합니다.](#uninstall-your-non-microsoft-solution)
6. [끝점용 Defender가 제대로 작동하고 있는지 확인합니다.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender에 장치 온보딩

1. Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">포털로 이동하여</a> 로그인합니다.

2. 끝점 **설정(장치** 관리 \>  \>  아래)를 **선택하세요.**

3. **온보더링 프로세스를** 시작할 운영 체제 선택 목록에서 운영 체제를 선택합니다.

4. 배포 **방법에서** 옵션을 선택합니다. 링크 및 프롬프트에 따라 조직의 장치를 온보드합니다. 도움이 필요하신가요? [온보더링 방법(이](#onboarding-methods) 문서의)을 참조하세요.

> [!NOTE]
> 온보딩하는 동안 문제가 발생하면 끝점 온보딩 문제에 [대한 Microsoft Defender 문제 해결을 참조합니다.](troubleshoot-onboarding.md) 이 문서에서는 끝점에서 온보더링 문제 및 일반적인 오류를 해결하는 방법을 설명합니다.

### <a name="onboarding-methods"></a>온보더링 방법

배포 방법은 운영 체제 및 기본 설정 방법에 따라 다릅니다. 다음 표에는 끝점용 Defender에 온보딩하는 데 도움이 되는 리소스가 나열됩니다.

|운영 체제  |메서드  |
|---------|---------|
|Windows 10 이상<br/><br/>Windows Server 2019 이상<br/><br/>Windows Server, 버전 1803 이상<br/><br/>Windows Server 2012 R2 및 2016 <sup> [[1]](#fn1)<sup>  |   [로컬 스크립트(최대 10대의 장치)](configure-endpoints-script.md)<br><br/>   [그룹 정책](configure-endpoints-gp.md)<br/><br/>[Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)<br/><br/>[Microsoft Endpoint Manager/ 모바일 장치 관리(Intune)](configure-endpoints-mdm.md)<br>    [VDI 스크립트](configure-endpoints-vdi.md) <br><br> **참고:** 로컬 스크립트는 개념 증명에 적합하지만 프로덕션 배포에는 사용되지 않습니다. 프로덕션 배포의 경우 그룹 정책, Microsoft Endpoint Configuration Manager 또는 Intune을 사용하는 것이 좋습니다.
|Windows Server 2008 R2 SP1 | [Microsoft Monitoring Agent(MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) [또는 Azure Defender](/azure/security-center/security-center-wdatp) <br><br> **참고:** Microsoft Monitoring Agent Azure Log Analytics 에이전트가 됩니다. 자세한 내용은 Log Analytics 에이전트 [개요를 참조하세요.](/azure/azure-monitor/platform/log-analytics-agent)  
|Windows 8.1 Enterprise<br/><br/>Windows 8.1 Pro<br/><br/>Windows 7 SP1 Pro<br/><br/>Windows 7 SP1| [Microsoft Monitoring Agent(MMA)](onboard-downlevel.md) <br><br> **참고:** Microsoft Monitoring Agent Azure Log Analytics 에이전트가 됩니다. 자세한 내용은 Log Analytics 에이전트 [개요를 참조하세요.](/azure/azure-monitor/platform/log-analytics-agent)  
| macOS:<br/>11.3.1(Big Sur)<br/>10.15(카탈로나)<br/>10.14(모잡) | [로컬 스크립트](mac-install-manually.md)<br/><br/>[Microsoft Endpoint Manager ](mac-install-with-intune.md)<br/><br/>[JAMF Pro](mac-install-with-jamf.md)<br/><br/>[모바일 장치 관리](mac-install-with-other-mdm.md)   |
| Linux:<br/>RHEL 7.2+<br/>CentOS Linux 7.2+<br/>Ubuntu 16 LTS 이상<br/>SLES 12+<br/>데비안 9+<br/>Oracle Linux 7.2 |  [로컬 스크립트](linux-install-manually.md) <br><br/> [Puppet](linux-install-with-puppet.md) <br><br/> [Ansible](linux-install-with-ansible.md)|  
| iOS | [Microsoft Endpoint Manager ](ios-install.md)     |
|Android  | [Microsoft Endpoint Manager ](android-intune.md)               | 




(<a id="fn1">1</a>) Windows Server 2016 Windows Server 2012 R2는 온보드 서버의 지침을 사용하여 Windows [합니다.](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)


## <a name="run-a-detection-test"></a>검색 테스트 실행

온보딩된 장치가 Endpoint용 Defender에 올바르게 연결되어 있는지 확인하려면 검색 테스트를 실행하면 됩니다.

<br/><br/>

|운영 체제|지침|
|---|---|
|Windows 10 이상<br/><br/>Windows Server 2022<br/><br/>Windows Server 2019<br/><br/>Windows Server, 버전 1803 이상<br/><br/>Windows Server 2016<br/><br/>Windows Server 2012 R2|검색 [테스트 실행을 참조합니다.](run-detection-test.md)<br/><br/>Endpoint용 Defender 데모 시나리오 사이트( )를 방문하여 하나 이상의 <https://demo.wd.microsoft.com> 시나리오를 시도해 봤습니다. 예를 들어 클라우드 제공 보호 **데모 시나리오를 시도해** 보겠습니다.|
|macOS:<br/> 11.3.1(Big Sur)<br/>10.15(카탈로나)<br/>10.14(모잡)|에서 DIY 앱을 다운로드하여 <https://aka.ms/mdatpmacosdiy> 사용하세요. <br/><br/> 자세한 내용은 [macOS의 Endpoint용 Defender를 참조하세요.](microsoft-defender-endpoint-mac.md)|
|Linux:<br/> RHEL 7.2+<br/>CentOS Linux 7.2+<br/>Ubuntu 16 LTS 이상<br/>SLES 12+<br/>데비안 9+<br/>Oracle Linux 7.2|1. 다음 명령을 실행하고 1 : **의 결과를 찾아야** `mdatp health --field real_time_protection_enabled` 합니다.<br/><br/>2. 터미널 창을 열고 다음 명령을 `curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt` 실행합니다. .<br/><br/>3. 다음 명령을 실행하여 감지된 위협을 `mdatp threat list` 나열합니다. .<br/><br/>자세한 내용은 [Linux의 끝점용 Defender를 참조하세요.](microsoft-defender-endpoint-linux.md)|


## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>끝점에서 Microsoft Defender 바이러스 백신 수동 모드에 있는지 확인

끝점이 Endpoint용 Defender에 온보딩되어 이제 끝점이 수동 모드에서 실행되고 있는지 Microsoft Defender 바이러스 백신 단계입니다. 다음 표에 설명된 여러 방법 중 하나를 사용할 수 있습니다.

<br/><br/>

|메서드|수행할 작업|
|---|---|
|명령 프롬프트|1. Windows 디바이스에서 명령 프롬프트를 니다.<br/><br/>2. `sc query windefend` 를 입력한 다음 Enter를 누를 수 있습니다.<br/><br/>3. 결과를 검토하여 수동 Microsoft Defender 바이러스 백신 실행 중인지 검토합니다.|
|PowerShell|1. Windows 디바이스에서 관리자 권한으로 Windows PowerShell 를 니다.<br/><br/>2. 다음 PowerShell cmdlet을 `Get-MpComputerStatus|select AMRunningMode` 실행합니다. . <br/><br/>3. 결과를 검토합니다. 수동 **모드가 표시됩니다.**|
|Windows 보안 앱|1. Windows 디바이스에서 Windows 보안 를 니다.<br/><br/>2. 바이러스 **백신 & 보호를 선택합니다.**<br/><br/>3. Who **보호에서** 공급자 **관리를 선택합니다.**<br/><br/>4. 보안 공급자 **페이지의** 바이러스 백신에서 를 **Microsoft Defender 바이러스 백신 을 검색합니다.**|
|작업 관리자|1. Windows 디바이스에서 작업 관리자 앱을 니다.<br/><br/>2. 세부 정보 **탭을** 선택합니다. 목록에서 **MsMpEng.exe** 찾아야 합니다.|

> [!NOTE]
> 일부 버전의 *Windows Defender 바이러스 백신* 대신 Microsoft Defender 바이러스 백신 *수* Windows.
> 수동 모드 및 활성 모드에 대한 자세한 내용은 상태 에 대한 [Microsoft Defender 바이러스 백신 참조합니다.](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states)

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>수동 Microsoft Defender 바이러스 백신 Windows 서버에서 수동 모드로 설정

Microsoft Defender 바이러스 백신 Server, Windows 1803 이상 또는 Windows Server 2019 또는 Windows Server 2022에서 수동 모드로 설정하기 위해 다음 단계를 수행합니다.

1. 레지스트리 편집기를 열고 다음으로 이동합니다.

   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. **ForceDefenderPassiveMode라는** DWORD 항목을 편집하거나 만들고 다음 설정을 지정합니다.
   - DWORD 값을 **1로 설정**
   - **기본에서** 16진수 **를 선택합니다.**

> [!NOTE]
> 다음과 같은 다른 메서드를 사용하여 레지스트리 키를 설정할 수 있습니다.
>
> - [그룹 정책 기본 설정](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
> - [로컬 그룹 정책 개체 도구](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
> - [Configuration Manager의 패키지](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>시작 Microsoft Defender 바이러스 백신 시작 Windows Server 2016

사용 중이면 Windows Server 2016 수동으로 시작해야 Microsoft Defender 바이러스 백신 있습니다. 장치에서 PowerShell cmdlet을 사용하여 이 작업을 `mpcmdrun.exe -wdenable` 수행할 수 있습니다.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>배포에 대한 업데이트 Microsoft Defender 바이러스 백신

디바이스가 Microsoft Defender 바이러스 백신 모드로 실행 중인 경우에도 장치에 새로운 맬웨어 및 공격 기술로부터 보호하는 데 필요한 최신 기술 및 Microsoft Defender 바이러스 백신 유지하는 것이 중요합니다. (호환성 [Microsoft Defender 바이러스 백신 참조)](microsoft-defender-antivirus-compatibility.md)

최신 업데이트와 관련된 두 가지 유형의 업데이트가 Microsoft Defender 바이러스 백신 있습니다.

- 보안 인텔리전스 업데이트
- 제품 업데이트

업데이트를 다운로드하기 위해 Manage [Microsoft Defender 바이러스 백신 and apply baselines의 지침을 따르고.](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="uninstall-your-non-microsoft-solution"></a>Microsoft가 아닌 솔루션 제거

이때 다음이 있습니다.

- 끝점용 Defender에 조직의 장치를 온보딩하고
- Microsoft Defender 바이러스 백신 및 사용하도록 설정되어 있습니다.

다음 단계는 Microsoft가 아닌 바이러스 백신, 맬웨어 방지 및 끝점 보호 솔루션을 제거하는 것입니다. Microsoft가 아닌 솔루션을 제거하면 Microsoft Defender 바이러스 백신 모드로 전환됩니다. 대부분의 경우 이 문제는 자동으로 수행됩니다.

Microsoft가 아닌 솔루션의 솔루션이 없는 경우 해당 기술 지원 팀에 문의합니다.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>끝점용 Defender가 제대로 작동하고 있는지 확인

끝점용 Defender에 온보딩하고 이전의 Microsoft가 아닌 솔루션을 제거한 후 다음 단계는 끝점용 Defender가 제대로 작동하게 하는 것입니다. 이 작업을 수행하는 좋은 방법은 Endpoint용 Defender 데모 시나리오 사이트( )를 방문하는 [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 것입니다. 다음을 포함하여 해당 페이지에서 하나 이상의 데모 시나리오를 시도해 봤습니다.

- 클라우드 제공 보호
- PUA(잠재적으로 원치 않는 응용 프로그램)
- NP(네트워크 보호)

## <a name="next-steps"></a>다음 단계

**축하합니다!** 끝점용 [Defender로의 마이그레이션을 완료했습니다!](switch-to-microsoft-defender-migration.md#the-migration-process)

- [Microsoft 365 Defender](security-operations-dashboard.md) 포털에서 보안 작업 대시보드를 [https://security.microsoft.com](https://security.microsoft.com) 방문하세요.
- [마이그레이션 후 끝점에 대한 Defender를 관리합니다.](manage-atp-post-migration.md)
