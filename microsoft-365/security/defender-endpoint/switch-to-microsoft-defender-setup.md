---
title: 끝점용 Microsoft Defender로 전환 - 설치
description: 이는 끝점용 Microsoft Defender로 전환하기 위한 2단계 설치입니다.
keywords: migration, Microsoft Defender for Endpoint, edr
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
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 21a3ee2f40667e31c6eb9b1cf80a30997f167b82
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245747"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Endpoint용 Microsoft Defender로 전환 - 2단계: 설치

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![1 단계: 준비](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[1 단계: 준비](switch-to-microsoft-defender-prepare.md) |![2 단계: 설정](images/phase-diagrams/setup.png)<br/>2 단계: 설정 |[![3단계: 온보더 3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[3 단계: 온보딩](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*여기 있습니다!* | |

**끝점용 Microsoft [Defender로 전환하는 설치 단계에 오신 것을 환영합니다.](switch-to-microsoft-defender-migration.md#the-migration-process)** 이 단계에는 다음 단계가 포함됩니다.
1. 수동 Microsoft Defender 바이러스 백신 활성화하고 수동 [모드에 있는지 확인할 수 있습니다.](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)
2. [에 대한 업데이트를 Microsoft Defender 바이러스 백신.](#get-updates-for-microsoft-defender-antivirus)
3. 기존 끝점 솔루션의 제외 목록에 끝점용 [Microsoft Defender를 추가합니다.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)
4. [에 대한](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)제외 목록에 기존 솔루션을 Microsoft Defender 바이러스 백신.
5. [끝점용 Microsoft Defender의](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint)제외 목록에 기존 솔루션을 추가합니다.
6. 장치 그룹, 장치 컬렉션 및 조직 [구성 단위를 설치합니다.](#set-up-your-device-groups-device-collections-and-organizational-units)
7. [맬웨어 방지 정책 및 실시간 보호를 구성합니다.](#configure-antimalware-policies-and-real-time-protection)

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>사용 Microsoft Defender 바이러스 백신 수동 모드에 있는지 확인

Windows Server와 같은 Windows 버전에서는 McAfee Microsoft Defender 바이러스 백신 설치 시 제거되거나 사용하지 않도록 설정되어 있을 수 있습니다. 이는 mcAfee와 Microsoft Defender 바이러스 백신 바이러스 백신 제품을 설치할 때 수동 또는 비활성화 모드로 전환되지 않습니다. (자세한 내용은 호환성을 Microsoft Defender 바이러스 백신 [참조).](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

마이그레이션 프로세스의 이 단계에서는 다음과 같은 작업을 수행합니다.
- [Windows Server에서 DisableAntiSpyware를 false로 설정](#set-disableantispyware-to-false-on-windows-server)
- [Microsoft Defender 바이러스 백신 서버에서 Windows 다시 설치합니다.](#reinstall-microsoft-defender-antivirus-on-windows-server)
- [Microsoft Defender 바이러스 백신 서버에서 수동 모드로 Windows 설정](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [클라이언트 Microsoft Defender 바이러스 백신 장치에서 Windows 사용](#enable-microsoft-defender-antivirus-on-your-windows-client-devices) 및
- [수동 Microsoft Defender 바이러스 백신 모드로 설정되어 있는지 확인](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Windows Server에서 DisableAntiSpyware를 false로 설정

[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 레지스트리 키는 과거에 사용되지 않도록 설정하고 Microsoft Defender 바이러스 백신 McAfee와 같은 다른 바이러스 백신 제품을 배포하는 데 사용했습니다. 일반적으로 장치 및 끝점에서 이 레지스트리 Windows 안 됩니다. 그러나 구성한 경우 값을 `DisableAntiSpyware` false로 설정하는 방법에는 다음이 있습니다.

1. Windows 서버에서 레지스트리 편집기를 여는 방법을 확인합니다.

1. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`(으)로 이동합니다.

1. 해당 폴더에서 **DisableAntiSpyware라는** DWORD 항목을 찾아야 합니다.
   - 해당 항목이 없는 경우 모두 설정되어 있습니다.
   - **DisableAntiSpyware가** 표시되어 있는 경우 4단계로 진행합니다.

1. DisableAntiSpyware DWORD를 마우스 오른쪽 단추로 클릭한 다음 수정을 **클릭합니다.**

1. 값을 로 `0` 설정 이 경우 레지스트리 키의 값이 *false로 설정됩니다.*

> [!TIP]
> 이 레지스트리 키에 대한 자세한 내용은 [DisableAntiSpyware를 참조하세요.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender 바이러스 백신 서버에서 Windows 다시 설치

> [!NOTE]
> 다음 절차는 다음 버전의 런타임 버전을 실행하는 끝점 또는 장치에만 Windows.
> - Windows Server 2019
> - Windows 서버, 버전 1803(핵심 전용 모드)
> - Windows Server 2016

1. 끝점 또는 디바이스의 로컬 관리자로서 관리자 권한으로 Windows PowerShell.
2. 다음 PowerShell cmdlet을 실행합니다. <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/><br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
    > [!NOTE]
    > PS를 실행하는 작업 순서 내에서 DISM 명령을 사용하는 경우 다음 경로에 cmd.exe 필요합니다.
    > 예제:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/><br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. 실행 중인 Microsoft Defender 바이러스 백신 확인을 위해 다음 PowerShell cmdlet을 사용 합니다. <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>사용 중이 Windows Server 2016?

사용자 Windows Server 2016 사용하도록 설정하는 데 문제가 Microsoft Defender 바이러스 백신 다음 PowerShell cmdlet을 사용 합니다.

`mpcmdrun -wdenable`

> [!TIP]
> 아직 해결되지 않았습니까? 자세한 [Microsoft Defender 바이러스 백신 서버 Windows 참조합니다.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016)

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Microsoft Defender 바이러스 백신 서버에서 수동 모드로 Windows 설정

조직에서 여전히 기존 끝점 보호 솔루션을 사용 중이기 때문에 수동 Microsoft Defender 바이러스 백신 설정해야 합니다. 이렇게 하면 기존 솔루션과 Microsoft Defender 바이러스 백신 끝점용 Microsoft Defender에 대한 온보딩을 완료할 때까지 함께 실행할 수 있습니다.

1. 레지스트리 편집기를 열고 다음으로 이동합니다. <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. **ForceDefenderPassiveMode라는** DWORD 항목을 편집하거나 만들고 다음 설정을 지정합니다.
   - DWORD 값을 **1로 설정**
   - **기본에서** 16진수 **를 선택합니다.**

> [!NOTE]
> 다음과 같은 다른 메서드를 사용하여 레지스트리 키를 설정할 수 있습니다.
>- [그룹 정책 기본 설정](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [로컬 그룹 정책 개체 도구](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Configuration Manager의 패키지](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>클라이언트 Microsoft Defender 바이러스 백신 장치에서 Windows 사용

조직에서 Microsoft가 아닌 바이러스 백신 솔루션을 사용 중이기 때문에 조직의 Microsoft Defender 바이러스 백신 장치에서 사용하지 않도록 Windows 있습니다. 마이그레이션 프로세스의 이 단계에서는 마이그레이션을 사용하도록 Microsoft Defender 바이러스 백신. 

Intune을 Microsoft Defender 바이러스 백신 Intune을 사용하는 것이 좋습니다. 그러나 다음 표에 나열된 모든 메서드를 사용할 수 있습니다.

|메서드  |수행할 작업  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**참고:** 이제 Intune이 Microsoft Endpoint Manager. |1. Microsoft Endpoint Manager [관리 센터로 이동하여](https://go.microsoft.com/fwlink/?linkid=2109431) 로그인합니다.<br/><br/>2. **장치 구성**  >  **프로필을 선택한** 다음 구성할 프로필 유형을 선택합니다. 아직 장치 제한 프로필 유형을  만들지 않았거나 새 장치 제한 프로필 유형을 만들하려는 경우 Configure [device restriction settings in Microsoft Intune.](/intune/device-restrictions-configure)<br/><br/>3. 속성을 **선택하고** 구성 설정 **편집을 선택합니다.**<br/><br/>4. 를 **Microsoft Defender 바이러스 백신** 확장합니다. <br/><br/>5. 클라우드 제공 **보호를 사용하도록 설정**<br/><br/>6. 샘플 제출 전에 사용자에게 확인 **드롭다운에서** 자동으로 모든 샘플 **보내기 를 선택합니다.**<br/><br/>7. 잠재적으로 원치 않는 응용 **프로그램 검색 드롭다운에서** 사용 또는 **감사를** **선택합니다.**<br/><br/>8. **검토 + 저장을 선택한** 다음 저장을 **선택합니다.**<br/>**팁:** 설정을 만들고 구성하는 방법을 포함하여 Intune 장치 프로필에 대한 자세한 내용은 Microsoft Intune [프로필이란?을 참조하세요.](/intune/device-profiles)|
|제어판의 Windows     |에서 지침을 따르세요. [를 Microsoft Defender 바이러스 백신.](/mem/intune/user-help/turn-on-defender-windows) <br/>**참고:** 일부  버전의 Windows Defender 바이러스 백신 대신  Microsoft Defender 바이러스 백신 표시될 수 Windows.        |
|[고급 그룹 정책 관리](/microsoft-desktop-optimization-pack/agpm/) <br/>또는<br/>[그룹 정책 관리 콘솔](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. 로 이동 `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` <br/><br/>2. 끄기 이라는 정책을 **Microsoft Defender 바이러스 백신.**<br/><br/>3. 정책 **설정 편집 을 선택하고** 정책이 사용하지 않도록 설정되어 있는지 확인 합니다. 이렇게 하면 Microsoft Defender 바이러스 백신. <br/><br/>**참고:** 일부  버전의 Windows Defender 바이러스 백신 대신  Microsoft Defender 바이러스 백신 표시될 수 Windows. |


### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>수동 Microsoft Defender 바이러스 백신 모드에 있는지 확인

Microsoft Defender 바이러스 백신 수동 모드로 설정한 경우 기존 끝점 보호 솔루션과 함께 Microsoft Defender 바이러스 백신 수 있습니다. 다음 표에 설명된 바와 같이 명령 프롬프트 또는 PowerShell을 사용하여 이 작업을 수행할 수 있습니다.

|메서드  |수행할 작업  |
|---------|---------|
|명령 프롬프트     |1. Windows 장치에서 관리자 권한으로 명령 프롬프트를 여는 경우 <br/><br/>2. `sc query windefend` 를 입력한 다음 Enter를 누를 수 있습니다.<br/><br/>3. 결과를 검토하여 수동 Microsoft Defender 바이러스 백신 실행 중인지 검토합니다.         |
|PowerShell     |1. Windows 디바이스에서 관리자 권한으로 Windows PowerShell 를 니다.<br/><br/>2. [Get-MpComputerStatus](/powershell/module/defender/Get-MpComputerStatus) cmdlet을 실행합니다. <br/><br/>3. 결과 목록에서 **AMRunningMode:** 수동 모드 또는 **AMRunningMode: SxS** 수동 모드 를 검색합니다.          |

> [!NOTE]
> 일부 버전의 *Windows Defender 바이러스 백신* 대신 Microsoft Defender 바이러스 백신 *수* Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>배포에 대한 업데이트 Microsoft Defender 바이러스 백신

디바이스가 Microsoft Defender 바이러스 백신 모드로 실행 중인 경우에도 장치에 새로운 맬웨어 및 공격 기술로부터 보호하는 데 필요한 최신 기술 및 Microsoft Defender 바이러스 백신 유지하는 것이 [중요합니다.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

최신 업데이트와 관련된 두 가지 유형의 업데이트가 Microsoft Defender 바이러스 백신 있습니다.
- 보안 인텔리전스 업데이트
- 제품 업데이트

업데이트를 다운로드하기 위해 Manage [Microsoft Defender 바이러스 백신 and apply baselines의 지침을 따르고.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>기존 솔루션의 제외 목록에 끝점용 Microsoft Defender 추가

설치 프로세스의 이 단계에서는 기존 끝점 보호 솔루션 및 조직에서 사용하는 기타 보안 제품에 대한 제외 목록에 끝점용 Microsoft Defender를 추가합니다. 

> [!TIP]
> 제외를 구성하는 데 도움이 필요한 경우 솔루션 공급자의 설명서를 참조하십시오.

구성할 특정 제외는 끝점 또는 Windows 실행 중인 장치 버전에 따라 달라지며 다음 표에 나열되어 있습니다.

|OS |제외 |
|--|--|
|- Windows 10 [버전 1803](/windows/release-health/status-windows-10-1803) 이상(릴리스 [Windows 10 참조)](/windows/release-health/release-information)<br/>- Windows 10 버전 1703 또는 [1709(KB4493441](https://support.microsoft.com/help/4493441) 설치) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows 서버, 버전 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**참고:** 모니터링 호스트 임시 파일 6\45가 번호 매기기 하위 폴더가 다를 수 있습니다.<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>기존 솔루션을 기존 솔루션의 제외 목록에 Microsoft Defender 바이러스 백신

설치 프로세스의 이 단계에서 기존 솔루션을 제외 목록에 Microsoft Defender 바이러스 백신 합니다. 

검사에 제외를 [Microsoft Defender 바이러스 백신](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)경로 및 프로세스 제외를 추가해야 합니다. 다음 점에 유의하십시오.
- 경로 제외는 특정 파일과 해당 파일이 액세스하는 모든 파일을 제외합니다.
- 프로세스 제외는 프로세스 터치를 제외하지만 프로세스 자체는 제외하지 않습니다.
- 각 실행(.exe)을 경로 제외 및 프로세스 제외로 나열하면 프로세스와 터치하는 항목은 모두 제외됩니다.
- 이름만 사용하지 말고 전체 경로를 사용하여 프로세스 제외를 나열합니다. 이름 전용 메서드는 안전하지 않습니다.

다음 표에 나열된 여러 가지 방법에서 제외를 Microsoft Defender 바이러스 백신 수 있습니다.


|메서드 | 수행할 작업|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**참고:** 이제 Intune이 Microsoft Endpoint Manager. |1. Microsoft Endpoint Manager [관리 센터로 이동하여](https://go.microsoft.com/fwlink/?linkid=2109431) 로그인합니다.<br/><br/>2. **장치 구성** 프로필을 선택한 다음 구성할  >  프로필을 선택합니다.<br/><br/>3. **관리에서** 속성을 **선택합니다.**<br/> <br/>4. 구성 **설정: 편집 을 선택합니다.**<br/><br/>5. **를 Microsoft Defender 바이러스 백신** 확장한 다음 제외 **Microsoft Defender 바이러스 백신 확장합니다.**<br/><br/>6. 검색에서 제외할 파일 및 폴더, 확장명 및 Microsoft Defender 바이러스 백신 지정합니다. 참조는 Microsoft Defender 바이러스 백신 [제외를 참조합니다.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<br/><br/>7. **검토 + 저장 을 선택한** 다음 저장 을 **선택 합니다.**  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. [Configuration Manager 콘솔을](/mem/configmgr/core/servers/manage/admin-console) 사용하여 자산 및 준수 Endpoint Protection 맬웨어 방지 정책으로 이동한 다음 수정할 정책을  >    >  선택합니다. <br/><br/>2. 파일 및 폴더, 확장명 및 프로세스에서 제외할 파일 및 폴더에 대한 제외 Microsoft Defender 바이러스 백신 지정합니다. |
|[그룹 정책 개체](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. 그룹 정책 관리 컴퓨터에서 [](https://technet.microsoft.com/library/cc731212.aspx)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**<br/><br/>2. 그룹 정책 관리 **편집기에서** 컴퓨터 구성으로 **이동하여** 관리 템플릿 **을 클릭합니다.**<br/><br/>3. 트리를 확장하여 Windows **구성 > Microsoft Defender 바이러스 백신 > 확장합니다.**<br/>**참고:** 일부  버전의 Windows Defender 바이러스 백신 대신  Microsoft Defender 바이러스 백신 표시될 수 Windows.<br/><br/>4. 경로 제외  설정을 두 번 클릭하고 제외를 추가합니다.<br/>- 옵션을 사용으로 **설정합니다.**<br/>- 옵션 **섹션에서** **표시...를 클릭합니다.**<br/>- 값 이름 열 아래에 각 폴더를 자체 **줄에 지정합니다.**<br/>- 파일을 지정하는 경우 드라이브 문자, 폴더 경로, 파일 이름 및 확장명을 포함하여 파일의 정식 경로를 입력해야 합니다. 값 **열에 0을** **입력합니다.**<br/><br/>5. 확인을 **클릭합니다.**<br/><br/>6. 확장 제외  설정을 두 번 클릭하고 제외를 추가합니다.<br/>- 옵션을 사용으로 **설정합니다.**<br/>- 옵션 **섹션에서** **표시...를 클릭합니다.**<br/>- 값 이름 열 아래에 각 파일 확장명을 자체 **줄에 입력합니다.**  값 **열에 0을** **입력합니다.**<br/><br/>7. **확인을 클릭합니다.** |
|로컬 그룹 정책 개체 |1. 끝점 또는 디바이스에서 로컬 그룹 정책 편집기를 열 수 있습니다. <br/><br/>2. 컴퓨터 **구성** 관리 템플릿 Windows  >    >  **구성 요소 Microsoft Defender 바이러스 백신** 로  >    >  **이동하십시오.**<br/><br/>**참고:** 일부  버전의 Windows Defender 바이러스 백신 대신  Microsoft Defender 바이러스 백신 표시될 수 Windows.<br/><br/>3. 경로 및 프로세스 제외를 지정합니다. |
|레지스트리 키 |1. 다음 레지스트리 키를 내보낼 수 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` 있습니다. .<br/><br/>2. 레지스트리 키를 가져올 수 있습니다. 다음은 이와 관련된 두 가지 예입니다.<br/>- 로컬 경로: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- 네트워크 공유: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |
|||


## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender의 제외 목록에 기존 솔루션 추가

끝점용 Microsoft Defender에 제외를 추가하기 위해 [표시기를 생성합니다.](/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files)

1. Microsoft Defender 보안 센터 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ()로 이동하여 로그인합니다.<br/>

1. 탐색 창에서 규칙 **설정**  >    >  **를 선택하십시오.**<br/>

1. 파일 **해시 탭에서** **표시기 추가를 선택합니다.**<br/>

1. 표시기 **탭에서** 다음 설정을 지정합니다.
   - 파일 해시(도움이 필요하세요? 이 [문서의 CMPivot을 사용하여](#find-a-file-hash-using-cmpivot) 파일 해시 찾기를 참조하세요.)
   - **만료일(UTC)에서** 사용 안 을 **선택 합니다.**<br/>
   
1. 작업 **탭에서** 다음 설정을 지정합니다.
   - **응답 작업:** **허용**
   - 제목 및 설명<br/>
   
1. 범위 **탭의** 장치 **그룹에서** 내  범위의 모든 장치 또는 목록에서 **선택 을 선택합니다.**<br/>

1. 요약 **탭에서** 설정을 검토하고 저장을 **클릭합니다.**

### <a name="find-a-file-hash-using-cmpivot"></a>CMPivot을 사용하여 파일 해시 찾기

CMPivot은 Configuration Manager에 대한 콘솔 내 유틸리티입니다. CMPivot은 사용자 환경의 실시간 디바이스 상태 액세스 권한을 제공합니다. 이 쿼리는 대상 컬렉션의 현재 연결된 모든 디바이스에서 쿼리를 즉시 실행하고 결과를 반환합니다. 자세한 내용은 [CMPivot 개요를 참조하세요.](/mem/configmgr/core/servers/manage/cmpivot-overview)

CMPivot을 사용하여 파일 해시를 얻은 후 다음 단계를 수행합니다.

1. 선행 [준비를 검토합니다.](/mem/configmgr/core/servers/manage/cmpivot#prerequisites)
2. [CMPivot을 시작 합니다.](/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot) 
3. 커넥트()에 대한 `SCCM_ServerName.DomainName.com` 설명입니다.
4. 쿼리 **탭을** 선택합니다.
5. 장치 **컬렉션 목록에서** 모든 **시스템(기본값)을 선택합니다.**
6. 쿼리 상자에 다음 쿼리를 입력합니다.<br/>

   ```kusto
   File(c:\\windows\\notepad.exe)
   | project Hash
   ```
   
   > [!NOTE]
   > 위의 쿼리에서 이 notepad.exe타사 보안 제품 프로세스 이름으로 바 대체합니다. 

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>장치 그룹, 장치 모음 및 조직 구성 단위 설정

| 컬렉션 유형 | 수행할 작업 |
|--|--|
|[장치](/microsoft-365/security/defender-endpoint/machine-groups) 그룹(이전의 컴퓨터 그룹)을 사용하면 보안 운영 팀이 자동화된 조사 및 수정과 같은 보안 기능을 구성할 수 있습니다.<br/> 장치 그룹은 보안 운영 팀이 필요한 경우 수정 작업을 수행할 수 있도록 해당 장치에 대한 액세스를 할당하는 데도 유용합니다. <br/>디바이스 그룹은 디바이스 그룹에서 Microsoft Defender 보안 센터. |1. 을(를) [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 보안 센터.<br/><br/>2. 왼쪽의 탐색 창에서 사용 **설정**  >  **장치 그룹을**  >  **선택하십시오.**  <br/><br/>3. **+ 장치 그룹 추가를 선택 합니다.**<br/><br/>4. 디바이스 그룹의 이름과 설명을 지정합니다.<br/><br/>5. 자동화 **수준 목록에서** 옵션을 선택합니다. (전체 - **위협을 자동으로 수정하는 것이** 좋습니다.) 다양한 자동화 수준에 대한 자세한 내용은 위협 수정 방법을 [참조합니다.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/><br/>6. 일치하는 규칙에 대한 조건을 지정하여 장치 그룹에 속하는 장치를 확인합니다. 예를 들어 도메인, OS 버전을 선택하거나 장치 [태그를 사용할 수도 있습니다.](/microsoft-365/security/defender-endpoint/machine-tags)<br/><br/>7. 사용자 액세스 **탭에서** 장치 그룹에 포함된 장치에 액세스할 수 있는 역할을 지정합니다. <br/><br/>8. 완료 **를 선택 합니다.** |
|[장치 모음을](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) 사용하면 보안 운영 팀에서 응용 프로그램을 관리하거나, 규정 준수 설정을 배포하거나, 조직의 장치에 소프트웨어 업데이트를 설치할 수 있습니다.<br/>장치 컬렉션은 Configuration [Manager 를 사용하여 만들어집니다.](/mem/configmgr/) |컬렉션 만들기의 [단계를 따릅니다.](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[조직 구성 단위를](/azure/active-directory-domain-services/create-ou) 사용하면 사용자 계정, 서비스 계정 또는 컴퓨터 계정과 같은 개체를 논리적으로 그룹화할 수 있습니다. 그런 다음 관리자를 특정 조직 구성 단위에 할당하고 그룹 정책을 적용하여 대상 구성 설정을 적용할 수 있습니다.<br/> 조직 구성 단위는 도메인 서비스에 [Azure Active Directory 정의됩니다.](/azure/active-directory-domain-services) | Create an [Organizational Unit in an Azure Active Directory Domain Services managed domain의 단계를 따릅니다.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>맬웨어 방지 정책 및 실시간 보호 구성

Configuration Manager 및 장치 컬렉션을 사용하여 맬웨어 방지 정책을 구성합니다.
- Configuration Manager에서 맬웨어 방지 정책 [만들기 및 Endpoint Protection 배포를 참조하세요.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- 맬웨어 방지 정책을 만들고 구성하는 동안 실시간 [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 보호 설정을 검토하고 차단을 사용하면 [됩니다.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> 조직의 장치가 온보드되기 전에 정책을 배포할 수 있습니다.

## <a name="next-step"></a>다음 단계

**축하합니다!** 끝점용 [Microsoft Defender로](switch-to-microsoft-defender-migration.md#the-migration-process)전환하는 설치 단계를 완료했습니다!

- [3단계: 끝점용 Microsoft Defender 온보딩으로 진행](switch-to-microsoft-defender-onboard.md)
