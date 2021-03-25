---
title: Symantec에서 끝점용 Microsoft Defender로 - 2단계, 설정
description: 이것은 Symantec에서 끝점용 Microsoft Defender로 마이그레이션하는 2단계 설치입니다.
keywords: 마이그레이션, Windows Defender Advanced Threat Protection, atp, edr
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 3fbe7ca11ca168f2af75b76252acf4d3a97b35f0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074852"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>Symantec에서 마이그레이션 - 2단계: 끝점용 Microsoft Defender 설정

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![1단계: 준비](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[1단계: 준비](symantec-to-microsoft-defender-atp-prepare.md) |![2단계: 설정](images/phase-diagrams/setup.png)<br/>2단계: 설정 |[![3단계: 온보더](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[3단계: 온보더](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*여기 있습니다!* | |


**[Symantec에서 끝점용 Microsoft Defender로 마이그레이션하는 설치 단계에 오신 것을 환영합니다.](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)** 이 단계에는 다음 단계가 포함됩니다.
1. Microsoft Defender 바이러스 백신을 사용하도록 설정하거나 다시 [설치합니다(특정 버전의 Windows용).](#enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows)
2. [Microsoft Defender 바이러스 백신을 사용하도록 설정](#enable-microsoft-defender-antivirus).
3. [Microsoft Defender 바이러스 백신에 대한 업데이트를 다운로드합니다.](#get-updates-for-microsoft-defender-antivirus)
4. [Symantec의 제외 목록에 끝점용 Microsoft Defender를 추가합니다.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec)
5. Microsoft Defender 바이러스 백신의 제외 목록에 [Symantec을 추가합니다.](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus)
6. [끝점용 Microsoft Defender의 제외 목록에 Symantec을 추가합니다.](#add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint)
7. 장치 그룹, 장치 컬렉션 및 조직 [구성 단위를 설치합니다.](#set-up-your-device-groups-device-collections-and-organizational-units)
8. [맬웨어 방지 정책 및 실시간 보호를 구성합니다.](#configure-antimalware-policies-and-real-time-protection)

## <a name="enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows"></a>Microsoft Defender 바이러스 백신 사용 또는 다시 설치(특정 버전의 Windows용)

> [!TIP]
> Windows 10을 실행하는 경우 이 작업을 수행할 필요가 없습니다. Microsoft **[Defender 바이러스 백신 사용으로 진행합니다.](#enable-microsoft-defender-antivirus)**

특정 버전의 Windows에서는 Microsoft Defender 바이러스 백신이 제거되거나 사용하지 않도록 설정되어 있을 수 있습니다. Symantec과 같은 타사 바이러스 백신 제품을 설치할 때 Microsoft Defender 바이러스 백신이 수동 또는 비활성화 모드로 전환되지 않습니다. 자세한 내용은 [Microsoft Defender 바이러스 백신 호환성을 참조합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility) 

이제 Symantec에서 끝점용 Microsoft Defender로 이동한 후 Microsoft Defender 바이러스 백신을 활성화 또는 다시 설치하고 수동 모드로 설정해야 합니다. 

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Windows Server에서 Microsoft Defender 바이러스 백신 다시 설치

> [!NOTE]
> 다음 절차는 다음 버전의 Windows를 실행하는 끝점 또는 장치에만 적용됩니다.
> - Windows Server 2019
> - Windows Server, 버전 1803(코어 전용 모드)
> - Windows Server 2016
> 
> Microsoft Defender 바이러스 백신은 Windows 10에 기본 제공되지만 사용하지 않도록 설정되어 있을 수 있습니다. 이 경우 Microsoft [Defender 바이러스 백신 사용으로 진행합니다.](#enable-microsoft-defender-antivirus)

1. 끝점 또는 디바이스의 로컬 관리자로서 관리자 권한으로 Windows PowerShell.
2. 다음 PowerShell cmdlet을 실행합니다. `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

   > [!NOTE]
   > PS를 실행하는 작업 순서 내에서 DISM 명령을 사용하는 경우 다음 경로에 cmd.exe 필요합니다.
   > 예제:<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>
3. Microsoft Defender 바이러스 백신이 실행되고 있는지 확인하기 위해 다음 PowerShell cmdlet을 사용 합니다. <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Windows Server 2016을 사용하나요?

Windows Server 2016을 사용하고 있으며 Microsoft Defender 바이러스 백신을 사용하도록 설정하는 데 문제가 있는 경우 다음 PowerShell cmdlet을 사용 합니다.

`mpcmdrun -wdenable`

> [!TIP]
> 여전히 도움이 필요하세요? [Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신을 참조합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016)

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Windows Server에서 Microsoft Defender 바이러스 백신을 수동 모드로 설정

조직에서 여전히 Symantec을 사용 중이기 때문에 Microsoft Defender 바이러스 백신을 수동 모드로 설정해야 합니다. 이렇게 하면 끝점용 Microsoft Defender에 대한 온보딩을 완료할 때까지 Symantec 및 Microsoft Defender 바이러스 백신을 나란히 실행할 수 있습니다.

1. 레지스트리 편집기를 열고 다음으로 이동합니다. <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.
2. **ForceDefenderPassiveMode라는** DWORD 항목을 편집하거나 만들고 다음 설정을 지정합니다.
   - DWORD 값을 **1로 설정**
   - **기본에서** 16진수 **를 선택합니다.**

> [!NOTE]
> 다음과 같은 다른 메서드를 사용하여 레지스트리 키를 설정할 수 있습니다.
>- [그룹 정책 기본 설정](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [로컬 그룹 정책 개체 도구](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Configuration Manager의 패키지](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="enable-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신 사용

조직에서 Symantec을 기본 바이러스 백신 솔루션으로 사용 중이기 때문에 Microsoft Defender 바이러스 백신은 조직의 Windows 장치에서 사용하지 않도록 설정되어 있을 수 있습니다. 마이그레이션 프로세스의 이 단계에서는 Microsoft Defender 바이러스 백신을 사용하도록 설정해야 합니다. 

Microsoft Defender 바이러스 백신을 사용하도록 설정하려면 Intune을 사용하는 것이 좋습니다. 그러나 다음 표에 나열된 모든 메서드를 사용할 수 있습니다.

|메서드  |수행할 작업  |
|---------|---------|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**참고:** Intune은 이제 Microsoft 끝점 관리자입니다. |1. Microsoft [Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) 관리 센터로 이동하여 로그인합니다.<br/>2. **장치 구성**  >  **프로필을 선택한** 다음 구성할 프로필 유형을 선택합니다. 아직 장치 제한 프로필 유형을  만들지 않았거나 새 장치 제한 프로필 유형을 만들 경우 [Microsoft Intune에서](https://docs.microsoft.com/intune/device-restrictions-configure)장치 제한 설정 구성을 참조하세요.<br/>3. 속성을 **선택하고** 구성 설정 **편집을 선택합니다.**<br/>4. **Microsoft Defender 바이러스 백신을 확장합니다.** <br/>5. 클라우드 제공 **보호를 사용하도록 설정**<br/>6. 샘플 제출 전에 사용자에게 확인 **드롭다운에서** 자동으로 모든 샘플 **보내기 를 선택합니다.**<br/>7. 잠재적으로 원치 않는 응용 **프로그램 검색 드롭다운에서** 사용 또는 **감사를** **선택합니다.**<br/>8. **검토 + 저장을 선택한** 다음 저장을 **선택합니다.**<br/>설정을 만들고 구성하는 방법을 포함하여 Intune 장치 프로필에 대한 자세한 내용은 [Microsoft Intune 장치 프로필이란?을 참조하세요.](https://docs.microsoft.com/intune/device-profiles)|
|Windows의 제어판     |다음 지침을 따르세요. [Microsoft Defender 바이러스 백신 켜기.](https://docs.microsoft.com/mem/intune/user-help/turn-on-defender-windows) <br/>**참고:** 일부  Windows Windows Defender *Microsoft Defender 바이러스* 백신 대신 바이러스 백신이 표시될 수 있습니다.        |
|[고급 그룹 정책 관리](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) <br/>또는<br/>[그룹 정책 관리 콘솔](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. 로 이동 `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` <br/>2. Microsoft Defender 바이러스 백신 끄기라는 **정책을 찾아 봐야 합니다.**<br/>3. 정책 **설정 편집 을 선택하고** 정책이 사용하지 않도록 설정되어 있는지 확인 합니다. 이를 통해 Microsoft Defender 바이러스 백신을 사용할 수 있습니다. <br/>**참고:** 일부  Windows Windows Defender *Microsoft Defender 바이러스* 백신 대신 바이러스 백신이 표시될 수 있습니다. |

### <a name="verify-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Microsoft Defender 바이러스 백신이 수동 모드에 있는지 확인

Microsoft Defender 바이러스 백신을 수동 모드로 설정한 경우 Symantec과 함께 Microsoft Defender 바이러스 백신을 실행할 수 있습니다. 다음 표에 설명된 바와 같이 명령 프롬프트 또는 PowerShell을 사용하여 이 작업을 수행할 수 있습니다.

|메서드  |수행할 작업  |
|---------|---------|
|명령 프롬프트     |1. Windows 장치에서 관리자 권한으로 명령 프롬프트를 니다. <br/>2. `sc query windefend` 를 입력한 다음 Enter를 누를 수 있습니다.<br/>3. 결과를 검토하여 Microsoft Defender 바이러스 백신이 수동 모드로 실행되고 있는지 검토합니다.         |
|PowerShell     |1. Windows 디바이스에서 관리자 권한으로 Windows PowerShell 를 니다.<br/>2. [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/Get-MpComputerStatus) cmdlet을 실행합니다. <br/>3. 결과 목록에서 **AMRunningMode:** 수동 모드 또는 **AMRunningMode: SxS** 수동 모드 를 검색합니다.|

> [!NOTE]
> 일부 버전의 *Windows에서는* *Microsoft Defender* Windows Defender 대신 바이러스 백신을 사용할 수 있습니다.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신에 대한 업데이트 다운로드

Microsoft Defender 바이러스 백신을 수동 모드로 실행 중인 경우에도 장치에 새로운 맬웨어 및 공격 기술로부터 보호하는 데 필요한 최신 기술 및 기능을 유지하는 것이 [중요합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Microsoft Defender 바이러스 백신을 최신 상태로 유지하는 데 관련된 두 가지 유형의 업데이트가 있습니다.
- 보안 인텔리전스 업데이트
- 제품 업데이트

업데이트를 다운로드하기 위해 Microsoft Defender 바이러스 백신 업데이트 관리의 지침을 [따르고 기준을 적용합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>Symantec의 제외 목록에 끝점용 Microsoft Defender 추가

설치 프로세스의 이 단계에서는 Symantec 및 조직에서 사용하는 기타 보안 제품에 대한 제외 목록에 끝점용 Microsoft Defender를 추가합니다. 구성할 특정 제외는 끝점 또는 장치가 실행되는 Windows 버전에 따라 달라지며 다음 표에 나열되어 있습니다.

|OS |제외 |
|--|--|
|- Windows 10 버전 [1803](https://docs.microsoft.com/windows/release-health/status-windows-10-1803) [이상(Windows 10 릴리스 정보 참조)](https://docs.microsoft.com/windows/release-health/release-information)<br/>- [KB4493441이](https://support.microsoft.com/help/4493441) 설치된 Windows 10 버전 [1703 또는 1709](https://docs.microsoft.com/windows/release-health/status-windows-10-1709) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, 버전 1803](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**참고:** 모니터링 호스트 임시 파일 6\45가 번호 매기기 하위 폴더가 다를 수 있습니다.<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신의 제외 목록에 Symantec 추가

설치 프로세스의 이 단계에서는 Microsoft Defender 바이러스 백신 제외 목록에 Symantec 및 기타 보안 솔루션을 추가합니다. 

> [!NOTE]
> 제외할 프로세스 및 서비스에 대한 자세한 내용은 [Endpoint Protection 14에서](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html)사용하는 Broadcom의 프로세스 및 서비스를 참조합니다.

[Microsoft Defender 바이러스](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)백신 검사에 제외를 추가할 때 경로 및 프로세스 제외를 추가해야 합니다. 다음 점에 유의하십시오.
- 경로 제외는 특정 파일과 해당 파일이 액세스하는 모든 파일을 제외합니다.
- 프로세스 제외는 프로세스 터치를 제외하지만 프로세스 자체는 제외하지 않습니다.
- 각 실행파일(.exe)을 경로 제외와 프로세스 제외로 나열하면 프로세스와 해당 프로세스가 터치하는 항목은 모두 제외됩니다.
- 이름만 사용하지 말고 전체 경로를 사용하여 프로세스 제외를 나열합니다. 이름 전용 메서드는 안전하지 않습니다.

다음 표에 나와 있는 여러 방법 중 선택해 Microsoft Defender 바이러스 백신에 제외를 추가할 수 있습니다.

|메서드 | 수행할 작업|
|--|--|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**참고:** Intune은 이제 Microsoft 끝점 관리자입니다. |1. Microsoft [Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) 관리 센터로 이동하여 로그인합니다.<br/>2. **장치 구성** 프로필을 선택한 다음 구성할  >  프로필을 선택합니다.<br/>3. **관리에서** 속성을 **선택합니다.** <br/>4. 구성 **설정: 편집 을 선택합니다.**<br/>5. **Microsoft Defender 바이러스** 백신을 확장한 다음 Microsoft Defender 바이러스 백신 **제외를 확장합니다.**<br/>6. Microsoft Defender 바이러스 백신 검사에서 제외할 파일 및 폴더, 확장명 및 프로세스를 지정합니다. 참조는 [Microsoft Defender 바이러스 백신 제외를 참조합니다.](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<br/>7. **검토 + 저장 을 선택한** 다음 저장 을 **선택 합니다.**  |
|[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/) |1. [Configuration Manager 콘솔을](https://docs.microsoft.com/mem/configmgr/core/servers/manage/admin-console)사용하여 **자산** 및 준수  >  **끝점 보호** 맬웨어 방지 정책으로 이동한 다음 수정할 정책을  >  선택합니다. <br/>2. Microsoft Defender 바이러스 백신 검사에서 제외할 파일 및 폴더, 확장명 및 프로세스에 대한 제외 설정을 지정합니다. |
|[그룹 정책 개체](https://docs.microsoft.com/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. 그룹 정책 관리 컴퓨터에서 [](https://technet.microsoft.com/library/cc731212.aspx)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**<br/>2. 그룹 정책 관리 **편집기에서** 컴퓨터 구성으로 **이동하여** 관리 템플릿 **을 클릭합니다.**<br/>3. Microsoft Defender 바이러스 백신 > Windows 구성 > **확장합니다.**<br/>**참고:** 일부  Windows Windows Defender *Microsoft Defender 바이러스* 백신 대신 바이러스 백신이 표시될 수 있습니다.<br/>4. 경로 제외  설정을 두 번 클릭하고 제외를 추가합니다.<br/>- 옵션을 사용으로 **설정합니다.**<br/>- 옵션 **섹션에서** **표시...를 클릭합니다.**<br/>- 값 이름 열 아래에 각 폴더를 자체 **줄에 지정합니다.**<br/>- 파일을 지정하는 경우 드라이브 문자, 폴더 경로, 파일 이름 및 확장명을 포함하여 파일의 정식 경로를 입력해야 합니다. 값 **열에 0을** **입력합니다.**<br/>5. 확인을 **클릭합니다.**<br/>6. 확장 제외  설정을 두 번 클릭하고 제외를 추가합니다.<br/>- 옵션을 사용으로 **설정합니다.**<br/>- 옵션 **섹션에서** **표시...를 클릭합니다.**<br/>- 값 이름 열 아래에 각 파일 확장명을 자체 **줄에 입력합니다.**  값 **열에 0을** **입력합니다.**<br/>7. **확인을 클릭합니다.** |
|로컬 그룹 정책 개체 |1. 끝점 또는 디바이스에서 로컬 그룹 정책 편집기를 열 수 있습니다. <br/>2. 컴퓨터 **구성** 관리  >  **템플릿**  >  **Windows 구성 요소**  >  **Microsoft Defender 바이러스** 백신  >  **제외로 이동** <br/>**참고:** 일부  Windows Windows Defender *Microsoft Defender 바이러스* 백신 대신 바이러스 백신이 표시될 수 있습니다.<br/>3. 경로 및 프로세스 제외를 지정합니다. |
|레지스트리 키 |1. 다음 레지스트리 키를 내보낼 수 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` 있습니다. .<br/>2. 레지스트리 키를 가져올 수 있습니다. 다음은 이와 관련된 두 가지 예입니다.<br/>- 로컬 경로: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- 네트워크 공유: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender의 제외 목록에 Symantec 추가

끝점용 Microsoft Defender에 제외를 추가하기 위해 [표시기를 생성합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files)

1. Microsoft Defender 보안 센터()로 이동하여 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 로그인합니다.
2. 탐색 창에서 설정 규칙  >    >  **표시기를 선택합니다.**
3.  파일 **해시 탭에서** **표시기 추가를 선택합니다.**
4. 표시기 **탭에서** 다음 설정을 지정합니다.
   - 파일 해시(도움이 필요하세요? 이 [문서의 CMPivot을 사용하여](#find-a-file-hash-using-cmpivot) 파일 해시 찾기를 참조하세요.)
   - **만료일(UTC)에서** 사용 안 을 **선택 합니다.**
5. 작업 **탭에서** 다음 설정을 지정합니다.
   - **응답 작업:** **허용**
   - 제목 및 설명
6. 범위 **탭의** 장치 **그룹에서** 내  범위의 모든 장치 또는 목록에서 **선택 을 선택합니다.**
7. 요약 **탭에서** 설정을 검토하고 저장을 **클릭합니다.**

### <a name="find-a-file-hash-using-cmpivot"></a>CMPivot을 사용하여 파일 해시 찾기

CMPivot은 Configuration Manager에 대한 콘솔 내 유틸리티입니다. CMPivot은 사용자 환경의 실시간 디바이스 상태 액세스 권한을 제공합니다. 이 쿼리는 대상 컬렉션의 현재 연결된 모든 디바이스에서 쿼리를 즉시 실행하고 결과를 반환합니다. 자세한 내용은 [CMPivot 개요를 참조하세요.](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot-overview)

CMPivot을 사용하여 파일 해시를 얻은 후 다음 단계를 수행합니다.

1. 선행 [준비를 검토합니다.](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#prerequisites)
2. [CMPivot을 시작 합니다.](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot) 
3. Configuration Manager()에 `SCCM_ServerName.DomainName.com` 연결합니다.
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
|[장치](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) 그룹(이전의 컴퓨터 그룹)을 사용하면 보안 운영 팀이 자동화된 조사 및 수정과 같은 보안 기능을 구성할 수 있습니다.<br/> 장치 그룹은 보안 운영 팀이 필요한 경우 수정 작업을 수행할 수 있도록 해당 장치에 대한 액세스를 할당하는 데도 유용합니다. <br/>장치 그룹은 Microsoft Defender 보안 센터에서 만들어집니다. |1. Microsoft Defender 보안 센터()로 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 이동하십시오.<br/>2. 왼쪽의 탐색 창에서 설정 사용 권한 장치  >    >  **그룹을 선택합니다.**  <br/>3. **+ 장치 그룹 추가를 선택 합니다.**<br/>4. 디바이스 그룹의 이름과 설명을 지정합니다.<br/>5. 자동화 **수준 목록에서** 옵션을 선택합니다. (전체 - **위협을 자동으로 수정하는 것이** 좋습니다.) 다양한 자동화 수준에 대한 자세한 내용은 위협 수정 방법을 [참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/>6. 일치하는 규칙에 대한 조건을 지정하여 장치 그룹에 속하는 장치를 확인합니다. 예를 들어 도메인, OS 버전을 선택하거나 장치 [태그를 사용할 수도 있습니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags) <br/>7. 사용자 액세스 **탭에서** 장치 그룹에 포함된 장치에 액세스할 수 있는 역할을 지정합니다. <br/>8. 완료 **를 선택 합니다.** |
|[장치 모음을](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/introduction-to-collections) 사용하면 보안 운영 팀에서 응용 프로그램을 관리하거나, 규정 준수 설정을 배포하거나, 조직의 장치에 소프트웨어 업데이트를 설치할 수 있습니다. <br/>장치 컬렉션은 Configuration [Manager 를 사용하여 만들어집니다.](https://docs.microsoft.com/mem/configmgr/) |컬렉션 만들기의 [단계를 따릅니다.](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[조직 구성 단위를](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) 사용하면 사용자 계정, 서비스 계정 또는 컴퓨터 계정과 같은 개체를 논리적으로 그룹화할 수 있습니다. 그런 다음 관리자를 특정 조직 구성 단위에 할당하고 그룹 정책을 적용하여 대상 구성 설정을 적용할 수 있습니다.<br/> 조직 구성 단위는 [Azure Active Directory 도메인 서비스에 정의됩니다.](https://docs.microsoft.com/azure/active-directory-domain-services) | Azure Active Directory 도메인 서비스 관리 도메인에서 조직 구성 단위 [만들기의 단계를 따릅니다.](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>맬웨어 방지 정책 및 실시간 보호 구성

Configuration Manager 및 장치 컬렉션을 사용하여 맬웨어 방지 정책을 구성합니다.

- [Configuration Manager에서 Endpoint Protection에](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)대한 맬웨어 방지 정책 만들기 및 배포를 참조하세요.
- 맬웨어 방지 정책을 만들고 구성하는 동안 실시간 [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 보호 설정을 검토하고 차단을 사용하면 [됩니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> 조직의 장치가 온보드되기 전에 정책을 배포할 수 있습니다.

## <a name="next-step"></a>다음 단계

**축하합니다!** [Symantec에서 끝점용 Microsoft Defender로 마이그레이션하는 설치 단계를 완료했습니다.](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)
- [3단계: 끝점용 Microsoft Defender 온보딩으로 진행](symantec-to-microsoft-defender-atp-onboard.md)
