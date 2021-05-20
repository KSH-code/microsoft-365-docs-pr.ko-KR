---
title: McAfee에서 끝점용 Microsoft Defender로 - 온보드
description: McAfee에서 끝점용 Microsoft Defender로 마이그레이션하는 3단계인 온보딩입니다.
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
- m365solution-McAfeemigrate
- m365solution-scenario
ms.custom: migrationguides
ms.topic: article
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 8a9d1ea36ae0778892768e3b39f4ffbed2a8d732
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538030"
---
# <a name="migrate-from-mcafee---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>McAfee에서 마이그레이션 - 3단계: 끝점용 Microsoft Defender로 온보딩

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


|[![1 단계: 준비](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[1 단계: 준비](mcafee-to-microsoft-defender-prepare.md) |[![2 단계: 설정](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[2 단계: 설정](mcafee-to-microsoft-defender-setup.md) |![3 단계: 온보딩](images/phase-diagrams/onboard.png)<br/>3 단계: 온보딩 |
|--|--|--|
|| |*여기 있습니다!* |

**[McAfee 끝점 보안(McAfee)에서 끝점용 Microsoft Defender로](mcafee-to-microsoft-defender-migration.md#the-migration-process)마이그레이션의 3단계를 시작 합니다.** 이 마이그레이션 단계에는 다음 단계가 포함됩니다.

1. [끝점용 Microsoft Defender에 장치를 온보딩합니다.](#onboard-devices-to-microsoft-defender-for-endpoint)

2. [검색 테스트를 실행합니다.](#run-a-detection-test)

3. [수동 Microsoft Defender 바이러스 백신 모드에 있는지 확인](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)

4. [에 대한 업데이트를 Microsoft Defender 바이러스 백신.](#get-updates-for-microsoft-defender-antivirus)

5. [McAfee를 제거합니다.](#uninstall-mcafee)

6. [끝점용 Defender가 제대로 작동하고 있는지 확인합니다.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender에 장치 온보딩

1. Microsoft Defender 보안 센터 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ()로 이동하여 로그인합니다.

2. 장치 **설정**  >  **온보더링**  >  **을 선택하세요.** 

3. **온보더링 프로세스를** 시작할 운영 체제 선택 목록에서 운영 체제를 선택합니다. 

4. 배포 **방법에서** 옵션을 선택합니다. 링크 및 프롬프트에 따라 조직의 장치를 온보드합니다. 도움이 필요하신가요? [온보더링 방법(이](#onboarding-methods) 문서의)을 참조하세요.

### <a name="onboarding-methods"></a>온보더링 방법
 
배포 방법은 선택한 운영 체제에 따라 다릅니다. 온보드에 대한 도움말을 확인하면 아래 표에 나열된 리소스를 참조하세요.

| 운영 체제  |메서드  |
|---------|---------|
| Windows 10     | [그룹 정책](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[모바일 장치 관리(Intune)](configure-endpoints-mdm.md)<p>[로컬 스크립트](configure-endpoints-script.md) <br/>**참고:** 로컬 스크립트는 개념 증명에 적합하지만 프로덕션 배포에는 사용되지 않습니다. 프로덕션 배포의 경우 그룹 정책, Microsoft Endpoint Configuration Manager 또는 Intune을 사용하는 것이 좋습니다.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 SP1 Enterprise<p>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<br/>**참고:** Microsoft Monitoring Agent Azure Log Analytics 에이전트가 됩니다. 자세한 내용은 Log Analytics 에이전트 [개요를 참조하세요.](/azure/azure-monitor/platform/log-analytics-agent)        |
| Windows Server 2019 이상<p>Windows Server 2019 Core Edition<p>Windows 서버 버전 1803 이상 | [로컬 스크립트](configure-endpoints-script.md)<p>[그룹 정책](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[System Center Configuration Manager](configure-endpoints-sccm.md)<p>[비영구 장치에 대한 VDI 온보딩 스크립트](configure-endpoints-vdi.md) <br/>**참고:** 로컬 스크립트는 개념 증명에 적합하지만 프로덕션 배포에는 사용되지 않습니다. 프로덕션 배포의 경우 그룹 정책, Microsoft Endpoint Configuration Manager 또는 Intune을 사용하는 것이 좋습니다.    |
| Windows Server 2016 <p>Windows Server 2012 R2<p>Windows Server 2008 R2 SP1  | [Microsoft Defender 보안 센터](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS:<p>11.3.1(Big Sur)<p>10.15(카탈로나)<p>10.14(모잡) |[Windows가 아닌 장치 온보딩](configure-endpoints-non-windows.md)  |
|iOS |[Windows가 아닌 장치 온보딩](configure-endpoints-non-windows.md)  |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS 이상<p>SLES 12+<p>데비안 9+<p>Oracle Linux 7.2 |[Windows가 아닌 장치 온보딩](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>검색 테스트 실행

온보딩된 장치가 Endpoint용 Microsoft Defender에 제대로 연결되어 있는지 확인하려면 검색 테스트를 실행할 수 있습니다.

|운영 체제  |지침  |
|---------|---------|
| Windows 10<p>Windows Server 2019 <p>Windows 서버, 버전 1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     |검색 [테스트 실행을 참조합니다.](run-detection-test.md) <p>끝점용 Microsoft Defender 데모 시나리오 사이트( )를 방문하고 하나 이상의 [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 시나리오를 시도해 봤습니다. 예를 들어 클라우드 제공 보호 **데모 시나리오를 시도해** 보겠습니다.         |
|macOS<p>11.3.1(Big Sur)<p>10.15(카탈로나)<p>10.14(모잡)     |에서 DIY 앱을 다운로드하여 [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 사용하세요. <p>자세한 내용은 [Mac의 끝점용 Microsoft Defender를 참조하세요.](microsoft-defender-endpoint-mac.md)        |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS 이상<p>SLES 12+<p>데비안 9+<p>Oracle Linux 7.2 |1. 다음 명령을 실행하고 **1의 결과를 찾아야 합니다.** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. 터미널 창을 열고 다음 명령을 실행합니다. <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. 다음 명령을 실행하여 감지된 위협을 나열합니다. <br/>`mdatp threat list`. <p>자세한 내용은 [Linux의 끝점용 Microsoft Defender를 참조하세요.](microsoft-defender-endpoint-linux.md) |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>수동 Microsoft Defender 바이러스 백신 모드에 있는지 확인

끝점이 Endpoint용 Defender에 온보딩되어 이제 끝점이 수동 모드에서 실행되고 있는지 Microsoft Defender 바이러스 백신 단계입니다. 다음 표에 설명된 바와 같이 명령 프롬프트 또는 PowerShell을 사용하여 이 작업을 수행할 수 있습니다.

|메서드  |수행할 작업  |
|---------|---------|
|명령 프롬프트     |1. Windows 장치에서 관리자 권한으로 명령 프롬프트를 여는 경우<p> 2. `sc query windefend` 를 입력한 다음 Enter를 누를 수 있습니다.<p> 3. 결과를 검토하여 수동 Microsoft Defender 바이러스 백신 실행 중인지 검토합니다.         |
|PowerShell     |1. Windows 디바이스에서 관리자 권한으로 Windows PowerShell 를 니다.<p> 2. [Get-MpComputerStatus](/powershell/module/defender/Get-MpComputerStatus) cmdlet을 실행합니다. <p> 3. 결과 목록에서 **AMRunningMode:** 수동 모드 또는 **AMRunningMode: SxS** 수동 모드 를 검색합니다.|

> [!NOTE]
> 일부 버전의 *Windows Defender 바이러스 백신* 대신 Microsoft Defender 바이러스 백신 *수* Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>수동 Microsoft Defender 바이러스 백신 Windows 서버에서 수동 모드로 설정

Microsoft Defender 바이러스 백신 Server, Windows 1803 이상 또는 Windows Server 2019에서 수동 모드로 설정하기 위해 다음 단계를 수행합니다.

1. 레지스트리 편집기를 열고 로 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` 이동합니다.

2. **ForcePassiveMode라는** DWORD 항목을 편집하거나 만들고 다음 설정을 지정합니다.

   - DWORD 값을 로 `1` 설정
   - **기본에서** 16진수 **를 선택합니다.**
 
   > [!NOTE]
   > 다음과 같은 다른 메서드를 사용하여 레지스트리 키를 설정할 수 있습니다.
   > - 그룹 정책 기본 설정
   > - 로컬 그룹 정책 개체 도구
   > - Configuration Manager의 패키지

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>시작 Microsoft Defender 바이러스 백신 시작 Windows Server 2016

사용 중이면 Windows Server 2016 수동으로 시작해야 Microsoft Defender 바이러스 백신 있습니다. 디바이스에서 PowerShell cmdlet을 사용하여 이 `mpcmdrun.exe -wdenable` 작업을 할 수 있습니다.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>배포에 대한 업데이트 Microsoft Defender 바이러스 백신

디바이스가 Microsoft Defender 바이러스 백신 모드로 실행 중인 경우에도 장치에 새로운 맬웨어 및 공격 기술로부터 보호하는 데 필요한 최신 기술 및 Microsoft Defender 바이러스 백신 유지하는 것이 중요합니다.

최신 업데이트와 관련된 두 가지 유형의 업데이트가 Microsoft Defender 바이러스 백신 있습니다.
- 보안 인텔리전스 업데이트
- 제품 업데이트

업데이트를 다운로드하기 위해 Manage [Microsoft Defender 바이러스 백신 and apply baselines의 지침을 따르고.](manage-updates-baselines-microsoft-defender-antivirus.md)


## <a name="uninstall-mcafee"></a>McAfee 제거

이제 조직의 장치를 끝점용 Microsoft Defender에 온보딩했습니다. 다음 단계는 McAfee를 제거하는 것입니다. 이 단계에 대한 도움말을 확인한 후 McAfee ServicePortal()로 [http://mysupport.mcafee.com](http://mysupport.mcafee.com) 이동하십시오.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>끝점용 Defender가 제대로 작동하고 있는지 확인

McAfee를 제거한 후 다음 단계는 Microsoft Defender 바이러스 백신 및 끝점 검색 및 응답이 활성화되어 활성 모드로 설정되어 있는지 확인합니다.

이를 위해 끝점용 Microsoft Defender 데모 시나리오 사이트( )를 [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 방문하세요. 다음을 포함하여 해당 페이지에서 하나 이상의 데모 시나리오를 시도해 봤습니다.
- 클라우드 제공 보호
- PUA(잠재적으로 원치 않는 응용 프로그램)
- NP(네트워크 보호)

> [!IMPORTANT]
> 사용 중이면 Windows Server 2016 수동으로 시작해야 Microsoft Defender 바이러스 백신 있습니다. 디바이스에서 PowerShell cmdlet을 사용하여 이 `mpcmdrun.exe -wdenable` 작업을 할 수 있습니다.

## <a name="next-steps"></a>다음 단계

**축하합니다!** [McAfee에서 끝점용 Microsoft Defender로](mcafee-to-microsoft-defender-migration.md#the-migration-process)마이그레이션을 완료했습니다! 

- [에서 보안 작업](security-operations-dashboard.md) 대시보드를 방문하세요Microsoft Defender 보안 센터. [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 
- [마이그레이션 후 끝점에 대한 Microsoft Defender를 관리합니다.](manage-atp-post-migration.md)
