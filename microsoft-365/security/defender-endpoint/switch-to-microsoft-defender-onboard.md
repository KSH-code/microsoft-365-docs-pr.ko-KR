---
title: 끝점용 Microsoft Defender로 전환 - 온보딩
description: 이 단계는 Microsoft가 아닌 솔루션에서 끝점용 Microsoft Defender로 마이그레이션하기 위한 온보딩 3단계입니다.
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
ms.custom: migrationguides
ms.topic: article
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 6b3b9fda0060108bd6a3c48188ff6e89261be096
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327249"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Endpoint용 Microsoft Defender로 전환 - 3단계: 온보딩

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![1단계: 준비3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[1 단계: 준비](switch-to-microsoft-defender-prepare.md) | [![2 단계: 설정](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[2 단계: 설정](switch-to-microsoft-defender-setup.md) | ![3 단계: 온보딩](images/phase-diagrams/onboard.png)<br/>3 단계: 온보딩 |
|--|--|--|
|| |*여기 있습니다!* |


**끝점용 Microsoft [Defender로](switch-to-microsoft-defender-migration.md#the-migration-process)전환하는 3단계입니다.** 이 마이그레이션 단계에는 다음 단계가 포함됩니다.

1. [끝점용 Microsoft Defender에 장치를 온보딩합니다.](#onboard-devices-to-microsoft-defender-for-endpoint)
2. [검색 테스트를 실행합니다.](#run-a-detection-test)
3. [Microsoft가 아닌 솔루션을 제거합니다.](#uninstall-your-non-microsoft-solution)
4. [끝점용 Microsoft Defender가](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)활성 모드에 있는지 확인

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender에 장치 온보딩

1. Microsoft Defender 보안 센터()로 이동하여 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 로그인합니다.
2. 설정 **장치**  >  **관리**  >  **온보더링을 선택합니다.** 
3. **온보더링 프로세스를** 시작할 운영 체제 선택 목록에서 운영 체제를 선택합니다. 
4. 배포 **방법에서** 옵션을 선택합니다. 링크 및 프롬프트에 따라 조직의 장치를 온보드합니다. 도움이 필요하신가요? [온보더링 방법(이](#onboarding-methods) 문서의)을 참조하세요.

### <a name="onboarding-methods"></a>온보더링 방법
 
배포 방법은 선택한 운영 체제에 따라 다릅니다. 온보드에 대한 도움말을 확인하면 아래 표에 나열된 리소스를 참조하세요.

|운영 체제  |메서드  |
|---------|---------|
|Windows 10     |- [그룹 정책](configure-endpoints-gp.md)<br/>- [Configuration Manager](configure-endpoints-sccm.md)<br/>- [모바일 장치 관리(Intune)](configure-endpoints-mdm.md)<br/>- [로컬 스크립트](configure-endpoints-script.md) <p>**참고:** 로컬 스크립트는 개념 증명에 적합하지만 프로덕션 배포에는 사용되지 않습니다. 프로덕션 배포의 경우 그룹 정책, Microsoft Endpoint Configuration Manager 또는 Intune을 사용하는 것이 좋습니다.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft 모니터링 에이전트](onboard-downlevel.md)<p>**참고:** Microsoft 모니터링 에이전트는 이제 Azure Log Analytics 에이전트입니다. 자세한 내용은 Log Analytics 에이전트 [개요를 참조하세요.](/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 이상 <br/>- Windows Server 2019 Core Edition <br/>- Windows Server 버전 1803 이상 |- [로컬 스크립트](configure-endpoints-script.md) <br/>- [그룹 정책](configure-endpoints-gp.md) <br/>- [Configuration Manager](configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md) <br/>- [비영구 장치에 대한 VDI 온보딩 스크립트](configure-endpoints-vdi.md) <p>**참고:** 로컬 스크립트는 개념 증명에 적합하지만 프로덕션 배포에는 사용되지 않습니다. 프로덕션 배포의 경우 그룹 정책, Microsoft Endpoint Configuration Manager 또는 Intune을 사용하는 것이 좋습니다.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender 보안 센터](configure-server-endpoints.md)<br/>- [Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS<br/>- 11.3.1(Big Sur) <br/>- 10.15(카탈로나)<br/>- 10.14(Mojave)<p>iOS<p>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 이상<br/>- SLES 12+<br/>- 데비안 9+<br/>- Oracle Linux 7.2 |[Windows가 아닌 장치 온보딩](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>검색 테스트 실행

온보딩된 장치가 Endpoint용 Microsoft Defender에 제대로 연결되어 있는지 확인하려면 검색 테스트를 실행할 수 있습니다.

|운영 체제  |지침  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, 버전 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |검색 [테스트 실행을 참조합니다.](run-detection-test.md) <p>끝점용 Microsoft Defender 데모 시나리오 사이트( )를 방문하고 하나 이상의 [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 시나리오를 시도해 봤습니다. 예를 들어 클라우드 제공 보호 **데모 시나리오를 시도해** 보겠습니다.         |
|macOS<br/>- 11.3.1(Big Sur) <br/>- 10.15(카탈로나)<br/>- 10.14(Mojave)    |에서 DIY 앱을 다운로드하여 [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 사용하세요. <p>자세한 내용은 [macOS의 끝점용 Microsoft Defender를 참조하세요.](microsoft-defender-endpoint-mac.md)        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 이상<br/>- SLES 12+<br/>- 데비안 9+<br/>- Oracle Linux 7.2 |1. 다음 명령을 실행하고 **1의 결과를 찾아야 합니다.** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. 터미널 창을 열고 다음 명령을 실행합니다. <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. 다음 명령을 실행하여 감지된 위협을 나열합니다. <br/>`mdatp threat list`. <p>자세한 내용은 [Linux의 끝점용 Microsoft Defender를 참조하세요.](microsoft-defender-endpoint-linux.md) |

## <a name="uninstall-your-non-microsoft-solution"></a>Microsoft가 아닌 솔루션 제거

끝점용 Microsoft Defender에 조직의 장치를 온보딩한 후 다음 단계는 비 Microsoft 끝점 보호 솔루션을 제거하는 것입니다.

이 단계에 대한 도움이 필요한 경우 솔루션 공급자의 기술 지원 팀에 문의하세요.

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>끝점용 Microsoft Defender가 활성 모드에 있는지 확인

Microsoft가 아닌 끝점 보호 솔루션을 제거한 후 다음 단계는 끝점용 Microsoft Defender와 Microsoft Defender 바이러스 백신 활성화 및 활성 모드로 설정하는 것입니다.

이를 위해 끝점용 Microsoft Defender 데모 시나리오 사이트( )를 [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 방문하세요. 다음을 포함하여 해당 페이지에서 하나 이상의 데모 시나리오를 시도해 봤습니다.
- 클라우드 제공 보호
- PUA(잠재적으로 원치 않는 응용 프로그램)
- NP(네트워크 보호)

> [!IMPORTANT]
> 사용 중이면 Windows Server 2016 수동으로 시작해야 Microsoft Defender 바이러스 백신 있습니다. 디바이스에서 PowerShell cmdlet을 사용하여 이 `mpcmdrun.exe -wdenable` 작업을 할 수 있습니다.

## <a name="next-steps"></a>다음 단계

**축하합니다!** 끝점용 [Microsoft Defender로의 마이그레이션을 완료했습니다!](switch-to-microsoft-defender-migration.md#the-migration-process) 

- [에서 보안 작업](security-operations-dashboard.md) 대시보드를 방문하세요Microsoft Defender 보안 센터. [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 
- [마이그레이션 후 끝점에 대한 Microsoft Defender를 관리합니다.](manage-atp-post-migration.md)
