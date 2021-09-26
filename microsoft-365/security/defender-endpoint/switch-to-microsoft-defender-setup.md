---
title: 끝점용 Microsoft Defender로 전환 - 설치
description: 끝점용 Defender로 전환합니다. 설치 프로세스(설치 프로세스 포함)를 Microsoft Defender 바이러스 백신.
keywords: 마이그레이션, 끝점용 Microsoft Defender, 바이러스 백신, 수동 모드, 설정 프로세스
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
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom: migrationguides
ms.date: 09/23/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: c65860eca559b1871f4f22a14a0bf179f06f3f9b
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59776863"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Endpoint용 Microsoft Defender로 전환 - 2단계: 설치

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![1단계: 준비.](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[1 단계: 준비](switch-to-microsoft-defender-prepare.md)|![2단계: 설정.](images/phase-diagrams/setup.png)<br/>2 단계: 설정|[![3단계: 온보더3.](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[3 단계: 온보딩](switch-to-microsoft-defender-onboard.md)|
|---|---|---|
||*여기 있습니다!*||

**끝점용 [Defender로 전환하는 설치 단계에 오신 것을 환영합니다.](switch-to-microsoft-defender-migration.md#the-migration-process)** 이 단계에는 다음 단계가 포함됩니다.

1. [끝점에서 Microsoft Defender 바이러스 백신 다시 설치/사용하도록 설정](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)
2. [끝점에 대한 Defender를 구성합니다.](#configure-defender-for-endpoint)
3. 기존 솔루션의 제외 목록에 [끝점용 Defender를 추가합니다.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)
4. [에 대한](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)제외 목록에 기존 솔루션을 Microsoft Defender 바이러스 백신.
5. 장치 그룹, 장치 컬렉션 및 조직 [구성 단위를 설치합니다.](#set-up-your-device-groups-device-collections-and-organizational-units)

## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>끝점에서 Microsoft Defender 바이러스 백신 다시 설치/사용

특정 버전의 Windows, Microsoft Defender 바이러스 백신 Microsoft 바이러스 백신/맬웨어 방지 솔루션이 설치될 때 제거되거나 비활성화된 것일 수 있습니다. 끝점을 Windows 끝점에 대한 Defender에 온보딩된 경우 Microsoft Defender 바이러스 백신 Microsoft가 아닌 바이러스 백신 솔루션과 함께 수동 모드에서 실행할 수 있습니다. 자세한 내용은 [Endpoint용 Defender를 통해 바이러스 백신 보호를 참조합니다.](microsoft-defender-antivirus-compatibility.md#antivirus-protection-with-defender-for-endpoint)

Endpoint용 Defender로 전환할 때 추가 기능을 다시 설치하거나 사용하도록 설정하기 위해 특정 단계를 Microsoft Defender 바이러스 백신. 다음 표에서는 클라이언트 및 서버에서 Windows 설명되어 있습니다.

<br/><br/>

|끝점 유형|수행할 작업|
|---|---|
|Windows 클라이언트(예: Windows 10)|일반적으로 클라이언트가 제거되지 않은 경우 Windows 작업을 수행하지 Microsoft Defender 바이러스 백신 않습니다. Microsoft Defender 바이러스 백신 설치해야 하지만 마이그레이션 프로세스의 이 시점에서는 사용하지 않도록 설정되어 있을 가능성이 습니다. Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션이 설치되고 클라이언트가 끝점용 Defender에 아직 온보딩되지 않은 경우 Microsoft Defender 바이러스 백신 사용하지 않도록 설정됩니다. <br/><br/> 나중에 클라이언트 끝점이 Endpoint용 Defender에 온보딩될 때 해당 끝점이 Microsoft가 아닌 바이러스 백신 솔루션을 실행하는 경우 Microsoft Defender 바이러스 백신 모드로 전환됩니다. <br/><br/> Microsoft가 아닌 바이러스 백신 솔루션을 제거하면 Microsoft Defender 바이러스 백신 모드로 전환됩니다.|
|Windows 서버|Windows 서버에서 서버를 다시 설치하고 수동으로 Microsoft Defender 바이러스 백신 수동 모드로 설정해야 합니다. 모든 Windows Microsoft가 아닌 바이러스 백신/맬웨어 방지가 설치되어 있는 경우 microsoft가 아닌 Microsoft Defender 바이러스 백신 솔루션과 함께 실행할 수 없습니다. 이러한 경우 수동으로 Microsoft Defender 바이러스 백신 제거하거나 사용하지 않도록 설정됩니다. <br/><br/> Microsoft Defender 바이러스 백신 서버에서 Windows 다시 설치하거나 사용하도록 설정하려면 다음 작업을 수행합니다. <br/>- [Windows Server에서 DisableAntiSpyware를 false로 설정(필요한](#set-disableantispyware-to-false-on-windows-server) 경우만 해당)<br/>- [Microsoft Defender 바이러스 백신 서버에서 Windows 다시 설치](#reinstall-microsoft-defender-antivirus-on-windows-server)<br/>- [Microsoft Defender 바이러스 백신 서버에서 수동 모드로 Windows 설정](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)|

> [!TIP]
> Microsoft가 아닌 바이러스 백신 Microsoft Defender 바이러스 백신 상태와 관련한 자세한 내용은 Microsoft Defender 바이러스 백신 [참조합니다.](microsoft-defender-antivirus-compatibility.md)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Windows Server에서 DisableAntiSpyware를 false로 설정

[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 레지스트리 키는 과거에 사용되어 Microsoft Defender 바이러스 백신 McAfee, Symantec 등의 다른 바이러스 백신 제품을 배포했습니다. 일반적으로 장치 및 끝점에 이 레지스트리 **Windows 안 됩니다.** 그러나 *구성한 경우* 값을 `DisableAntiSpyware` false로 설정하는 방법에는 다음이 있습니다.

1. Windows 서버에서 레지스트리 편집기를 여는 방법을 확인합니다.

2. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`(으)로 이동합니다.

3. 해당 폴더에서 **DisableAntiSpyware라는** DWORD 항목을 찾아야 합니다.
   - 해당 항목이 없는 경우 모두 설정되어 있습니다.
   - **DisableAntiSpyware가** 표시되어 있는 경우 4단계로 진행합니다.

4. DisableAntiSpyware DWORD를 마우스 오른쪽 단추로 클릭한 다음 수정을 **클릭합니다.**

5. 값을 로 `0` 설정 이 작업을 수행하면 레지스트리 키의 값이 *false로 설정됩니다.*

> [!TIP]
> 이 레지스트리 키에 대한 자세한 내용은 [DisableAntiSpyware를 참조하세요.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender 바이러스 백신 서버에서 Windows 다시 설치

> [!IMPORTANT]
> 다음 절차는 다음 버전의 런타임 버전을 실행하는 끝점 또는 장치에만 Windows.
>
> - Windows Server 2019
> - Windows 서버, 버전 1803(핵심 전용 모드)
> - Windows Server 2016 (다음 섹션, 현재 사용 [중입니까?](#are-you-using-windows-server-2016)Windows Server 2016 참조).

1. 끝점 또는 디바이스의 로컬 관리자로서 관리자 권한으로 Windows PowerShell.

2. 다음 PowerShell cmdlet을 실행합니다.

   ```powershell
   # For Windows Server 2016
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Gui
   # For Windows Server 2019
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```
   그런 다음 장치를 다시 시작합니다. 
   
   PowerShell을 실행하는 작업 순서 내에서 DISM 명령을 사용하는 경우 다음 경로에 cmd.exe 필요합니다.
   예제:

   ```powershell
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Microsoft Defender 바이러스 백신 서버에서 수동 모드로 Windows 설정

1. 레지스트리 편집기를 열고 다음으로 이동합니다.

   ```text
   Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
   ```

2. **ForceDefenderPassiveMode라는** DWORD 항목을 편집하거나 만들고 다음 설정을 지정합니다.

   - DWORD 값을 **1로 설정**
   - **기본에서** 16진수 **를 선택합니다.**

> [!NOTE]
> Endpoint용 Defender에 온보딩한 후 Microsoft Defender 바이러스 백신 서버에서 수동 모드로 Windows 있습니다. 수동 모드가 예상대로 설정되어 있는지 확인하려면 **Microsoft-Windows-Windows Defender** 작업 로그()에서 이벤트 *5007을* 검색하고 `C:\Windows\System32\winevt\Logs` **ForceDefenderPassiveMode** 또는 **PassiveMode** 레지스트리 키가 에 의해 0x1.

### <a name="are-you-using-windows-server-2016"></a>사용 중이 Windows Server 2016?

현재는 수동 모드에서 Microsoft Defender 바이러스 백신 실행할 수 Windows Server 2016. Microsoft가 아닌 다른 바이러스 백신/맬웨어 방지 솔루션을 제거하고 설치/Microsoft Defender 바이러스 백신. 사용자 설정에 문제가 있는 경우 Microsoft Defender 바이러스 백신 Windows Server 2016 다음 단계를 따르세요.

1. 장치에서 관리자 권한으로 PowerShell을 여는 것입니다.

2. 다음 PowerShell cmdlet을 `mpcmdrun -wdenable` 입력합니다. .

> [!TIP]
> 자세한 내용은 다음 문서를 참조하세요.
>
> - [Windows Server의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
> - [Microsoft Defender 바이러스 백신 제품과의 호환성](microsoft-defender-antivirus-compatibility.md)

### <a name="confirm-that-microsoft-defender-antivirus-is-enabled"></a>사용 Microsoft Defender 바이러스 백신 확인

다음 표에 설명된 여러 방법 중 하나를 사용하여 Microsoft Defender 바이러스 백신 상태를 확인할 수 있습니다.

<br/><br/>

|방법|절차|
|---|---|
|Windows 보안 앱| 1. Windows 디바이스에서 Windows 보안 를 니다.<br/><br/>2. 바이러스 **백신 & 보호를 선택합니다.**<br/><br/>3. Who **보호에서** 공급자 **관리를 선택합니다.** 보안 공급자 **페이지의** 바이러스 백신 **아래에서** 을(를) Microsoft Defender 바이러스 백신 **표시됩니다.**|
|작업 관리자|1. Windows 디바이스에서 작업 관리자 앱을 니다.<br/><br/>2. 세부 정보 **탭을** 선택합니다.<br/><br/>3. **목록에서** MsMpEng.exe찾아야 합니다.|
|Windows PowerShell <br/><br/> (실행 중인 Microsoft Defender 바이러스 백신 확인)|1. Windows 장치에서 Windows PowerShell.<br/><br/>2. 다음 PowerShell cmdlet을 `Get-Process` 실행합니다. .<br/><br/>3. 결과를 검토합니다. 활성화된 **MsMpEng.exe** 경우 Microsoft Defender 바이러스 백신 표시됩니다.|
|Windows PowerShell <br/> (바이러스 백신 보호가 실행 중이지 확인)|[Get-MpComputerStatus PowerShell cmdlet을 사용할 수 있습니다.](/powershell/module/defender/get-mpcomputerstatus) <br/><br/>1. Windows 장치에서 Windows PowerShell.<br/><br/>2. 다음 PowerShell cmdlet을 `Get-MpComputerStatus|select AMRunningMode` 실행합니다. .<br/><br/>3. 결과를 검토합니다. 끝점에서 사용할 **수** **있는** Microsoft Defender 바이러스 백신 일반 또는 수동이 표시됩니다.|

> [!TIP]
> [자세한 내용은 Microsoft Defender 바이러스 백신 을(를) 자세히 알아보아야 합니다.](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states)

## <a name="configure-defender-for-endpoint"></a>끝점에 대한 Defender 구성

마이그레이션 프로세스의 이 단계에서는 끝점에 대한 Microsoft Defender 바이러스 백신 구성합니다. Intune을 사용하는 것이 좋습니다. 그러나 다음 표에 나열된 모든 메서드를 사용할 수 있습니다.

<br/><br/>

|메서드|수행할 작업|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **참고:** Intune이 현재 Microsoft Endpoint Manager.|1. Microsoft Endpoint Manager [관리 센터로 이동하여](https://go.microsoft.com/fwlink/?linkid=2109431) 로그인합니다.<br/><br/>2. **장치 구성** \> **프로필을 선택한** 다음 구성할 프로필 유형을 선택합니다. 아직 장치 제한 프로필 유형을  만들지 않았거나 새 장치 제한 프로필 유형을 만들하려는 경우 Configure [device restriction settings in Microsoft Intune.](/intune/device-restrictions-configure)<br/><br/>3. 속성을 **선택한** 다음 구성 **설정: 편집을 선택합니다.**<br/><br/>4. 를 **Microsoft Defender 바이러스 백신** 확장합니다.<br/><br/>5. 클라우드 제공 **보호를 사용하도록 설정**<br/><br/>6. 샘플 제출 전에 사용자에게 확인 **드롭다운에서** 자동으로 모든 샘플 **보내기 를 선택합니다.**<br/><br/>7. 잠재적으로 원치 않는 응용 **프로그램 검색 드롭다운에서** 사용 또는 **감사를** **선택합니다.**<br/><br/>8. **검토 + 저장을 선택한** 다음 저장을 **선택합니다.** <br/><br/> **팁:** 설정을 만들고 구성하는 방법을 포함하여 Intune 장치 프로필에 대한 자세한 내용은 Microsoft Intune [프로필이란?을 참조하세요.](/intune/device-profiles)|
|Microsoft Endpoint Configuration Manager|Configuration Manager에서 맬웨어 방지 정책 [만들기 및 Endpoint Protection 배포를 참조하세요.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies) <br/><br/> 맬웨어 방지 정책을 만들고 구성할 때 실시간 [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 보호 설정을 검토하고 차단을 사용하면 [됩니다.](configure-block-at-first-sight-microsoft-defender-antivirus.md)
|제어판의 Windows|에서 지침을 따르세요. [를 Microsoft Defender 바이러스 백신.](/mem/intune/user-help/turn-on-defender-windows) 일부 버전의 *Windows Defender 바이러스 백신* 대신 Microsoft Defender 바이러스 백신  표시될 수 Windows.|
|[고급 그룹 정책 관리](/microsoft-desktop-optimization-pack/agpm/) <br/><br/> 또는 <br/><br/> [그룹 정책 관리 콘솔](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)|1. 컴퓨터 **구성** 관리 템플릿 및 \>  \> **Windows 구성** \> **요소로 Microsoft Defender 바이러스 백신.**<br/><br/>2. 끄기 이라는 정책을 **Microsoft Defender 바이러스 백신.**<br/><br/>3. 정책 **설정 편집 을 선택하고** 정책이 사용하지 않도록 설정되어 있는지 확인 합니다. 이 작업을 수행하면 Microsoft Defender 바이러스 백신. 일부 버전의 *Windows Defender 바이러스 백신* 대신 Microsoft Defender 바이러스 백신  표시될 수 Windows.|

> [!TIP]
> 조직의 장치가 온보드되기 전에 정책을 배포할 수 있습니다.

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>기존 솔루션의 제외 목록에 끝점용 Microsoft Defender 추가

설치 프로세스의 이 단계에서는 기존 끝점 보호 솔루션 및 조직에서 사용하는 기타 보안 제품에 대한 제외 목록에 Endpoint용 Defender를 추가합니다.

> [!TIP]
> 제외를 구성하는 데 도움이 필요한 경우 솔루션 공급자의 설명서를 참조하십시오.

구성할 특정 제외는 끝점 또는 장치가 Windows 버전에 따라 달라지며 다음 표에 나열되어 있습니다.

<br><br/>

|OS|제외|
|---|---|
|Windows 10 버전 [1803](/windows/release-health/status-windows-10-1803) 이상(릴리스 정보 Windows 10 [참조)](/windows/release-health/release-information) <br/><br/> Windows 10 버전 1703 또는 [1709(KB4493441](https://support.microsoft.com/help/4493441) 설치) <br/><br/> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019) <br/><br/> [Windows 서버, 버전 1803](/windows-server/get-started/whats-new-in-windows-server-1803)|`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe` <br/><br/> `C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe` <br/><br/> `C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe` <br/><br/> `C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`|
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/><br/> [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) <br/><br/> [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/><br/> [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/><br/> [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)|`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe` <br/><br/> **참고:** 호스트 임시 파일 6\45 모니터링은 번호가 매기기된 하위 폴더가 다를 수 있습니다. <br/><br/> `C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe` <br/><br/> `C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe` <br/><br/> `C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe` <br/><br/> `C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe` <br/><br/> `C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe` <br/><br/> `C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe`|

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>기존 솔루션을 기존 솔루션의 제외 목록에 Microsoft Defender 바이러스 백신

설치 프로세스의 이 단계에서 기존 솔루션을 제외 목록에 Microsoft Defender 바이러스 백신 합니다. 다음 표에 나열된 여러 가지 방법에서 제외를 Microsoft Defender 바이러스 백신 수 있습니다.

<br><br/>

|메서드|수행할 작업|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **참고:** Intune이 현재 Microsoft Endpoint Manager.|1. Microsoft Endpoint Manager [관리 센터로 이동하여](https://go.microsoft.com/fwlink/?linkid=2109431) 로그인합니다.<br/><br/>2. **장치 구성** 프로필을 선택한 다음 구성할 \> 프로필을 선택합니다.<br/><br/>3. **관리에서** 속성을 **선택합니다.**<br/><br/>4. 구성 **설정: 편집 을 선택합니다.**<br/><br/>5. **를 Microsoft Defender 바이러스 백신** 확장한 다음 제외 **Microsoft Defender 바이러스 백신 확장합니다.**<br/><br/>6. 검색에서 제외할 파일 및 폴더, 확장명 및 Microsoft Defender 바이러스 백신 지정합니다. 참조는 Microsoft Defender 바이러스 백신 [제외를 참조합니다.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<br/><br/>7. **검토 + 저장 을 선택한** 다음 저장 을 **선택 합니다.**|
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/)|1. [Configuration Manager 콘솔을](/mem/configmgr/core/servers/manage/admin-console)  사용하여 자산 및 준수 Endpoint Protection 맬웨어 방지 정책으로 이동한 다음 수정할 정책을 \>  \> 선택합니다.<br/><br/>2. 파일 및 폴더, 확장명 및 프로세스에서 제외할 파일 및 폴더에 대한 제외 Microsoft Defender 바이러스 백신 지정합니다.|
|[그룹 정책 개체](/previous-versions/windows/desktop/Policy/group-policy-objects)|1. 그룹 정책 관리 컴퓨터에서 [](https://technet.microsoft.com/library/cc731212.aspx)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 을 **선택합니다.**<br/><br/>2. 그룹 정책 관리 **편집기에서** 컴퓨터 구성으로 **이동하여** 관리 **템플릿을 선택합니다.**<br/><br/>3. 트리를 확장하여 Windows **구성 Microsoft Defender 바이러스 백신 \> \> 확장합니다.** 일부 버전의 *Windows Defender 바이러스 백신* 대신 Microsoft Defender 바이러스 백신  표시될 수 Windows.<br/><br/>4. 경로 제외  설정을 두 번 클릭하고 제외를 추가합니다.<br/><br/>5. 옵션을 사용으로 **설정합니다.**<br/><br/>6. **옵션 섹션에서** **표시...를 선택합니다.**<br/><br/>7. 값 이름 열 아래에 각 폴더를 자체 **줄에 지정합니다.** 파일을 지정하는 경우 드라이브 문자, 폴더 경로, 파일 이름 및 확장명을 포함하여 파일의 정식 경로를 입력해야 합니다. 값 **열에 0을** **입력합니다.**<br/><br/>8. **확인을 선택합니다.**<br/><br/>9. 확장 제외  설정을 두 번 클릭하고 제외를 추가합니다.<br/><br/>10. 옵션을 사용으로 **설정합니다.**<br/><br/>11. **옵션 섹션에서** **표시...를 선택합니다.**<br/><br/>12. 값 이름 열 아래에 각 파일 확장명을 자체 **줄에 입력합니다.** 값 **열에 0을** **입력합니다.**<br/><br/>13. 확인을 **선택합니다.**|
|로컬 그룹 정책 개체|1. 끝점 또는 디바이스에서 로컬 그룹 정책 편집기를 열 수 있습니다.<br/><br/>2. 컴퓨터 **구성** 관리 템플릿 Windows \>  \> **구성 요소 Microsoft Defender 바이러스 백신** 로 \>  \> **이동하십시오.** 일부 버전의 *Windows Defender 바이러스 백신* 대신 Microsoft Defender 바이러스 백신  표시될 수 Windows.<br/><br/>3. 경로 및 프로세스 제외를 지정합니다.|
|레지스트리 키|1. 다음 레지스트리 키를 내보낼 수 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` 있습니다. .<br/><br/>2. 레지스트리 키를 가져올 수 있습니다. 다음은 이와 관련된 두 가지 예입니다.<br/>- 로컬 경로: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg`<br/>- 네트워크 공유: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg`|

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>제외에 대해 다음 점에 유의합니다.

검사에 제외를 [Microsoft Defender 바이러스 백신](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)경로 및 프로세스 제외를 추가해야 합니다.

다음 점에 유의하십시오.

- *경로 제외는* 특정 파일과 해당 파일이 액세스하는 모든 파일을 제외합니다.
- *프로세스 제외는* 프로세스 터치를 제외하지만 프로세스 자체는 제외하지 않습니다.
- 이름만 사용하지 말고 전체 경로를 사용하여 프로세스 제외를 나열합니다. 이름 전용 메서드는 안전하지 않습니다.
- 각 실행(.exe)을 경로 제외 및 프로세스 제외로 나열하면 프로세스와 터치하는 항목은 모두 제외됩니다.

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>장치 그룹, 장치 모음 및 조직 구성 단위 설정

장치 그룹, 장치 컬렉션 및 조직 구성 단위를 사용하면 보안 팀이 보안 정책을 효율적이고 효율적으로 관리하고 할당할 수 있습니다. 다음 표에서는 이러한 각 그룹과 이러한 그룹을 구성하는 방법에 대해 설명하고 있습니다. 조직에서 세 가지 컬렉션 유형을 모두 사용하지 않을 수 있습니다.

<br/><br/>

|컬렉션 유형|수행할 작업|
|---|---|
|[장치 그룹(이전의](/microsoft-365/security/defender-endpoint/machine-groups) 컴퓨터 그룹)을 사용하면 보안 운영 팀이 자동화된 조사 및 수정과 같은 보안 기능을 구성할 수 있습니다.  <br/><br/> 장치 그룹은 보안 운영 팀이 필요한 경우 수정 작업을 수행할 수 있도록 해당 장치에 대한 액세스를 할당하는 데도 유용합니다. <br/><br/> 장치 그룹은 사이트 [포털에서 Microsoft 365 Defender 생성됩니다.](microsoft-defender-security-center.md)|1. Microsoft 365 Defender 포털()로 <https://security.microsoft.com> 이동하십시오.<br/><br/>2. 왼쪽의 탐색 창에서 **끝점 사용 설정** 장치 그룹을 \>  \>  \> **선택하세요.**<br/><br/>3. **+ 장치 그룹 추가를 선택 합니다.**<br/><br/>4. 디바이스 그룹의 이름과 설명을 지정합니다.<br/><br/>5. 자동화 **수준 목록에서** 옵션을 선택합니다. (전체 - **위협을 자동으로 수정하는 것이** 좋습니다.) 다양한 자동화 수준에 대한 자세한 내용은 위협 수정 방법을 [참조합니다.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/><br/>6. 일치하는 규칙에 대한 조건을 지정하여 장치 그룹에 속하는 장치를 확인합니다. 예를 들어 도메인, OS 버전을 선택하거나 장치 [태그를 사용할 수도 있습니다.](/microsoft-365/security/defender-endpoint/machine-tags)<br/><br/>7. 사용자 액세스 **탭에서** 장치 그룹에 포함된 장치에 액세스할 수 있는 역할을 지정합니다.<br/><br/>8. 완료 **를 선택 합니다.**|
|[장치 모음을](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) 사용하면 보안 운영 팀에서 응용 프로그램을 관리하거나, 규정 준수 설정을 배포하거나, 조직의 장치에 소프트웨어 업데이트를 설치할 수 있습니다. <br/><br/> 장치 컬렉션은 Configuration [Manager 를 사용하여 만들어집니다.](/mem/configmgr/)|컬렉션 만들기의 [단계를 따릅니다.](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)|
|[조직 구성 단위를](/azure/active-directory-domain-services/create-ou) 사용하면 사용자 계정, 서비스 계정 또는 컴퓨터 계정과 같은 개체를 논리적으로 그룹화할 수 있습니다. <br/><br/> 그런 다음 관리자를 특정 조직 구성 단위에 할당하고 그룹 정책을 적용하여 대상 구성 설정을 적용할 수 있습니다. <br/><br/> 조직 구성 단위는 도메인 서비스에 [Azure Active Directory 정의됩니다.](/azure/active-directory-domain-services)|Create an [Organizational Unit in an Azure Active Directory Domain Services managed domain의 단계를 따릅니다.](/azure/active-directory-domain-services/create-ou)|

## <a name="next-step"></a>다음 단계

**축하합니다!** [Endpoint용 Defender로](switch-to-microsoft-defender-migration.md#the-migration-process)전환하는 설치 단계를 완료했습니다!

- [3단계: 끝점용 Defender 온보딩으로 진행](switch-to-microsoft-defender-onboard.md)
