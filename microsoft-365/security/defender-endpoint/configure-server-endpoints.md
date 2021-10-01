---
title: 끝점 Windows Microsoft Defender에 서버 온보딩
description: 센서 Windows 끝점용 Microsoft Defender 센서로 보낼 수 있도록 서버를 온보딩합니다.
keywords: 온보딩 서버, 서버, 2012r2, 2016, 2019, 서버 온보딩, 장치 관리, 끝점 서버용 Microsoft Defender 구성, 끝점 서버용 Microsoft Defender 온보딩, 끝점 서버용 Microsoft Defender 온보딩
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 49c307bc2a68ae750e7ac9c54fd52b3b2b5f45ad
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60043206"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>끝점 Windows Microsoft Defender에 서버 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- Windows Server 2008 R2 SP1
- Windows Server 2012 R2
- Windows Server 2016
- Windows SAC(서버) 버전 1803 이상
- Windows Server 2019 이상
- Windows Server 2019 Core Edition

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configserver-abovefoldlink)

Endpoint용 Defender는 Windows 서버 운영 체제를 포함하기 위해 지원을 확장합니다. 이 지원은 보안 콘솔을 통해 고급 공격 감지 및 조사 기능을 Microsoft 365 Defender 제공합니다.

라이선스 및 인프라에 필요한 사항을 실제로 설명하는 내용은 [Endpoint용 Defender로 Windows 서버 보호를 참조하세요.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)

Windows 보안 서버의 기본 Windows 다운로드하고 사용하는 방법에 대한 지침은 Windows 보안 [참조하세요.](/windows/device-security/windows-security-baselines)

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2008 R2 SP1, Windows Server 2012 R2 및 Windows Server 2016

다음 옵션 중 Windows Server 2008 R2 SP1, Windows Server 2012 R2 및 Windows Server 2016 Defender for Endpoint에 온보딩할 수 있습니다.

- **옵션 1:** MMA(Microsoft Monitoring Agent 설치 및 구성하여 [온보더링)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)
- **옵션 2:** [Azure 보안 센터를 통해 온보더](#option-2-onboard-windows-servers-through-azure-security-center)
- **옵션 3:** [Microsoft Endpoint Manager 버전 2002 이상을](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later) 통해 온보드

제공된 옵션 중 원하는 옵션을 사용하여 온보더링 단계를 완료한 후 클라이언트를 구성하고 System Center Endpoint Protection [합니다.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
> Windows(옵션 1) 또는 Microsoft Endpoint Manager(옵션 3)를 통해 Windows Microsoft Monitoring Agent 서버를 온보딩하려면 노드당 Defender가 필요합니다. 또는 Azure 보안 센터(옵션 2)를 통해 Windows 서버를 등록하려면 노드당 Azure Defender for Servers 라이선스가 필요합니다. 자세한 내용은 [Azure Defender에서 사용할 수 있는 지원되는 기능을 참조하세요.](/azure/security-center/security-center-services) 사용자 라이선스와 달리 이러한 라이선스는 사용자 또는 개체에 할당되지 않습니다. 규정 준수를 위해 테넌트에 의해야 합니다.

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a>옵션 1: MMA(Microsoft Monitoring Agent 설치 및 구성하여 온보더링)

끝점용 Defender에 센서 데이터를 보고하도록 Windows MMA를 설치하고 구성해야 합니다. 자세한 내용은 Azure Log Analytics 에이전트를 사용하여 로그 데이터 [수집을 참조하세요.](/azure/azure-monitor/platform/log-analytics-agent)

SCOM(System Center Operations Manager) 또는 Azure 모니터(이전의 OM Microsoft Monitoring Agent S(Operations Management Suite))를 이미 사용 중이면 MMA(Operations Management Suite)를 연결하여 다중 호밍 지원을 통해 끝점 작업 영역용 Defender에 보고합니다.

일반적으로 다음 단계를 수행해야 합니다.

  1. 시작하기 전에 섹션에 설명된 **온보더링 요구 사항을 이행합니다.**
  2. 서버에서 서버 모니터링을 Microsoft 365 Defender.
  3. 서버가 끝점용 Defender에 센서 데이터를 보고하도록 MMA를 설치하고 구성합니다.
  4. 클라이언트를 구성하고 System Center Endpoint Protection 업데이트합니다.


#### <a name="before-you-begin"></a>시작하기 전에

다음 단계를 수행하여 온보더링 요구 사항을 충족합니다.

Windows Server 2008 R2 SP1 또는 Windows Server 2012 R2의 경우 다음 핫픽스를 설치해야 합니다.

- [고객 환경 및 진단 원격 분석에 대한 업데이트](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

Windows Server 2008 R2 SP1의 경우 다음 요구 사항을 충족해야 합니다.

- [2월](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598) 월간 업데이트 롤업 설치
- [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) 이상 또는 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) 설치

    > [!NOTE]
    > SCCM을 통해 Windows Server 2008 R2 SP1을 관리하는 경우 SCCM 클라이언트 에이전트는 .Net Framework 4.5.2를 설치합니다. 따라서 .NET Framework 4.5 이상을 설치할 필요가 없습니다.

Windows Server 2008 R2 SP1 및 Windows Server 2012 R2의 경우: 클라이언트 System Center Endpoint Protection [구성 및 업데이트합니다.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
> 이 단계는 조직에서 SCEP(System Center Endpoint Protection)를 사용하며 Windows Server 2008 R2 SP1 및 R2를 Windows Server 2012 하는 Windows Server 2012 필요합니다.

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>MMA(Microsoft Monitoring Agent)를 설치 및 구성하여 끝점용 Microsoft Defender에 센서 데이터 보고

1. 64비트 Windows 설치 파일을 [다운로드합니다.](https://go.microsoft.com/fwlink/?LinkId=828603)

2. 이전 절차에서 얻은 작업 영역 ID 및 작업 영역 키를 사용하여 다음 설치 방법을 선택하고 에이전트를 Windows 설치합니다.
    - [설치 프로그램을 사용하여 에이전트를 수동으로 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)
    에이전트 설정 **옵션 페이지에서** **에이전트를 커넥트 OMS(Azure Log Analytics) 로 이동합니다.**
    - [명령줄을 사용하여 에이전트를 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)
    - [스크립트를 사용하여 에이전트를 구성합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

> [!NOTE]
> 미국 정부 [](gov.md)고객인 경우 "Azure Cloud"에서 설치 마법사를 사용하는 경우 또는 명령줄 또는 스크립트를 사용하는 경우 "azure US Government"를 선택해야 합니다. "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 매개 변수를 1로 설정해야 합니다.

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a>필요한 Windows 서버 프록시 및 인터넷 연결 설정 구성

서버에서 프록시를 사용하여 끝점용 Defender와 통신해야 하는 경우 다음 방법 중 하나를 사용하여 프록시 서버를 사용하도록 MMA를 구성합니다.

- [프록시 서버를 사용하도록 MMA 구성](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)
- [모든 Windows 프록시 서버를 사용하도록 구성](configure-proxy-internet.md)

프록시 또는 방화벽이 사용 중이면 서버가 SSL 차단 없이 모든 끝점용 Microsoft Defender 서비스 URL에 직접 액세스할 수 있도록 합니다. 자세한 내용은 [Enable access to Defender for Endpoint service URLs을 참조하세요.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) SSL 차단을 사용하는 경우 시스템이 Endpoint용 Defender 서비스와 통신하지 못하게 됩니다.

완료되면 1시간 이내에 포털에 Windows 서버의 온보드 서버가 표시될 것입니다.

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a>옵션 2: Azure Windows 서버 온보드

Microsoft 365 Defender 창에서 **끝점 설정** 관리 온보더링을 \>  \>  \> **선택합니다.**

1. 운영 **Windows Server 2008 R2 SP1, 2012 R2 및 2016을** 선택합니다.

2. **Azure 보안 센터에서 서버 온보더를 클릭합니다.**

3. [Azure Defender를 사용하여 끝점용 Microsoft Defender의](/azure/security-center/security-center-wdatp) 온보딩 지침을 따르고 Azure ARC를 사용하는 경우 끝점 통합을 위해 [Microsoft Defender](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)통합 사용의 온보딩 지침을 따릅니다.

온보더링 단계를 완료한 후 클라이언트를 구성하고 System Center Endpoint Protection [합니다.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
>
> - 서버용 Azure Defender를 통한 온보딩이 예상대로 작동하려면 서버에 MMA(서버 관리) 설정 내에 적절한 작업 Microsoft Monitoring Agent 구성해야 합니다.
> - 구성되면 적절한 클라우드 관리 팩이 컴퓨터로 배포되어 센서 프로세스(MsSenseS.exe)가 배포 및 시작됩니다.
> - 이 설정은 서버가 OMS 게이트웨이 서버를 프록시로 사용하도록 구성된 경우도 필요합니다.

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a>옵션 3: Microsoft Endpoint Manager 2002 이상을 통해 Windows 서버 온보드

2002 버전 Windows Server 2012 사용하여 R2 및 Windows Server 2016 Microsoft Endpoint Manager 온보드할 수 있습니다. 자세한 내용은 현재 분기의 [끝점용 Microsoft Defender를 Microsoft Endpoint Manager 참조하세요.](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)

온보더링 단계를 완료한 후 클라이언트를 구성하고 System Center Endpoint Protection [합니다.](#configure-and-update-system-center-endpoint-protection-clients)

## <a name="windows-server-sac-version-1803-windows-server-2019-windows-server-2022-and-windows-server-2019-core-edition"></a>Windows SAC(Server) 버전 1803, Windows Server 2019, Windows Server 2022 및 Windows Server 2019 Core edition

다음 배포 방법을 사용하여 Windows Server(Windows Server) 버전 1803 또는 Windows Server 2019 또는 Windows Server 2022 또는 Windows Server 2019 Core edition을 온보드할 수 있습니다.

- [로컬 스크립트](configure-endpoints-script.md)
- [그룹 정책](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [System Center Configuration Manager 2012/2012 R2 1511/ 1602](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [비영구 장치에 대한 VDI 온보딩 스크립트](configure-endpoints-vdi.md)

> [!NOTE]
>
> - Windows Server 2019 및 Windows Server 2022용 온보딩 패키지는 Microsoft Endpoint Manager 현재 스크립트를 제공합니다. Configuration Manager에서 스크립트를 배포하는 방법에 대한 자세한 내용은 Configuration Manager의 패키지 [및 프로그램을 참조하세요.](/configmgr/apps/deploy-use/packages-and-programs)
> - 로컬 스크립트는 개념 증명에 적합하지만 프로덕션 배포에는 사용되지 않습니다. 프로덕션 배포의 경우 그룹 정책을 사용하는 것이 Microsoft Endpoint Configuration Manager.

Windows Server에 대한 지원은 서버 활동, 커널 및 메모리 공격 감지 범위에 대한 심층적인 정보를 제공하며 대응 작업을 가능하게 합니다.

1. 장치와 동일한 도구 및 방법을 사용하여 Windows 서버에서 끝점 온보딩 설정에 대한 Defender를 Windows 10 구성합니다. 자세한 내용은 장치 [온보드 Windows 10 참조하세요.](configure-endpoints.md)

2. 타사 맬웨어 방지 솔루션을 실행하는 경우 다음 Microsoft Defender AV 수동 모드 설정을 적용해야 합니다. 올바르게 구성되어 있는지 확인합니다.

    1. 다음 레지스트리 항목을 설정하십시오.
       - 경로: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
       - 이름: ForceDefenderPassiveMode
       - 유형: REG_DWORD
       - Value: 1

    1. 수동 모드가 구성되어 있는지 확인하도록 다음 PowerShell 명령을 실행합니다.

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. 수동 모드 이벤트가 포함된 최근 이벤트가 발견된지 확인:

       ![수동 모드 확인 결과의 이미지입니다.](images/atp-verify-passive-mode.png)

3. 다음 명령을 실행하여 Microsoft Defender AV가 설치되어 있는지 확인합니다.

   ```dos
   sc.exe query Windefend
   ```

    결과가 '지정된 서비스가 설치된 서비스로 존재하지 않는 경우 Microsoft Defender AV를 설치해야 합니다. 자세한 내용은 Microsoft Defender 바이러스 백신 [를 Windows 10.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

    그룹 정책을 사용하여 Microsoft Defender 바이러스 백신 서버에서 그룹 정책을 Windows 방법에 대한 자세한 내용은 [그룹](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)정책 설정을 사용하여 그룹 정책 구성 및 Microsoft Defender 바이러스 백신.

## <a name="integration-with-azure-defender"></a>Azure Defender와 통합

Endpoint용 Defender는 Azure Defender와 통합하여 포괄적인 서버 Windows 솔루션을 제공할 수 있습니다. 이 통합을 통해 Azure Defender는 끝점용 Defender의 기능을 사용하여 서버의 위협 감지 기능을 Windows 있습니다.

이 통합에는 다음과 같은 기능이 포함됩니다.

- 자동 온보딩 - Azure Defender에 온보딩된 Windows Endpoint용 Defender 센서가 자동으로 사용하도록 설정됩니다. Azure Defender 온보딩에 대한 자세한 내용은 [통합된 끝점용 Microsoft Defender 라이선스 사용을 참조하세요.](/azure/security-center/security-center-wdatp)

    > [!NOTE]
    > 서버용 Azure Defender와 끝점용 Microsoft Defender 간의 통합은 Windows Server 2022, Windows [Server 2019 및 WVD(Windows Virtual Desktop)를](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)지원하기 위해 확장되어 있습니다.

- Windows Azure Defender가 모니터링하는 서버는 Endpoint용 Defender에서도 사용할 수 있습니다. Azure Defender는 끝점 테넌트용 Defender에 원활하게 연결하여 클라이언트와 서버 전체에서 단일 보기를 제공합니다. 또한 Azure Defender 콘솔에서 끝점용 Defender 경고를 사용할 수 있습니다.

- 서버 조사 - Azure Defender 고객은 액세스하여 Microsoft 365 Defender 조사를 수행하여 잠재적인 위반 범위를 밝히는 데 사용할 수 있습니다.

> [!IMPORTANT]
>
> - Azure Defender를 사용하여 서버를 모니터링하면 끝점 테넌트에 대한 Defender가 자동으로 만들어집니다(미국 사용자의 경우 유럽 및 영국 사용자용 EU).
Endpoint용 Defender에서 수집한 데이터는 프로비전 중에 식별된 테넌트의 지리적 위치에 저장됩니다.
> - Azure Defender를 사용하기 전에 Endpoint용 Defender를 사용하는 경우 나중에 Azure Defender와 통합하는 경우에도 테넌트를 만들 때 지정한 위치에 데이터가 저장됩니다.
> - 일단 구성되면 데이터가 저장되는 위치를 변경할 수 없습니다. 데이터를 다른 위치로 이동해야 하는 경우 Microsoft 지원에 문의하여 테넌트를 다시 설정해야 합니다.
>
이러한 통합을 활용하는 서버 끝점 모니터링은 Office 365 GCC 사용하지 않도록 설정되어 있습니다.

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>클라이언트 구성 및 System Center Endpoint Protection 업데이트

Endpoint용 Defender는 통합된 System Center Endpoint Protection. 통합을 통해 맬웨어 감지에 대한 가시성을 확보하고 잠재적인 악성 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격 전파를 중지할 수 있습니다.

이 통합을 사용하려면 다음 단계가 필요합니다.

- Endpoint Protection [맬웨어](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)방지 플랫폼 업데이트를 설치합니다.

- [고급 설정으로 SCEP](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 클라이언트 클라우드 보호 서비스 멤버 **자격을 구성합니다.**

## <a name="run-a-detection-test-to-verify-onboarding"></a>검색 테스트를 실행하여 온보더링 확인

장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)

## <a name="offboard-windows-servers"></a>서버 Windows 오프보드

Windows 클라이언트 장치에 사용할 수 있는 동일한 방법으로 SAC(Windows Server), Windows Server 2019, Windows Server 2022 및 Windows Server 2019 Core 에디션을 오프보드할 Windows 10 있습니다.

- [그룹 정책을 사용하여 오프보더](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Configuration Manager를 사용하여 디바이스 오프보드](configure-endpoints-sccm.md#offboard-devices-using-configuration-manager)
- [모바일 장치 관리 도구를 사용하여 장치 오프보드 및 모니터링](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)
- [로컬 스크립트를 사용하여 디바이스 오프보딩](configure-endpoints-script.md#offboard-devices-using-a-local-script)

다른 Windows 서버 버전의 경우 서비스에서 서버 Windows 오프보드할 수 있는 두 가지 옵션이 있습니다.

- MMA 에이전트 제거
- 끝점용 Defender 작업 영역 구성 제거

> [!NOTE]
> 오프보드를 통해 Windows 서버는 포털에 센서 데이터 전송을 중지하지만 Windows 서버에 있는 모든 경고에 대한 참조를 포함하여 데이터까지 최대 6개월 동안 보존됩니다.

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a>MMA Windows 제거하여 서버 제거

Windows 서버를 오프보딩하기 위해 MMA 에이전트를 Windows 끝점 작업 영역의 Defender에 보고에서 이 에이전트를 제거하면 됩니다. 에이전트를 오프보딩한 후 Windows 서버는 더 이상 끝점용 Defender로 센서 데이터를 보내지 않습니다.
자세한 내용은 에이전트를 [사용하지 않도록 설정 을 참조하세요.](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>끝점용 Defender 작업 영역 구성 제거

서버의 Windows 다음 방법 중 하나를 사용할 수 있습니다.

- MMA 에이전트에서 끝점용 Defender 작업 영역 구성 제거
- PowerShell 명령을 실행하여 구성 제거

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>MMA 에이전트에서 끝점용 Defender 작업 영역 구성 제거

1. 사용자 **Microsoft Monitoring Agent 에서** Azure **OMS(로그 분석) 탭을** 선택합니다.

2. 끝점 작업 영역용 Defender를 선택하고 제거를 **클릭합니다.**

    ![속성 Microsoft Monitoring Agent 이미지입니다.](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>PowerShell 명령을 실행하여 구성 제거

1. 작업 영역 ID를 얻게 합니다.

   1. Microsoft 365 Defender 창에서 **끝점 설정** 관리 온보더링을 \>  \>  \> **선택합니다.**

   1. 운영 **Windows Server 2008 R2 SP1, 2012 R2 및 2016을** 선택하고 작업 영역 ID를 얻습니다.

      ![서버 Windows 이미지입니다.](images/atp-server-offboarding-workspaceid.png)

2. 승강된 PowerShell을 열고 다음 명령을 실행합니다. 얻은 작업 영역 ID를 사용하여 을 `WorkspaceID` 대체합니다.

    ```powershell
    $ErrorActionPreference = "SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()
    ```

## <a name="onboarding-servers-with-no-management-solution"></a>관리 솔루션이 없는 온보드 서버

### <a name="using-group-policy"></a>그룹 정책 사용

**1단계: 서버에 복사하는 데 필요한 파일을 생성합니다.**

1. c:\windows\sysvol\domain\scripts로 이동합니다(도메인 컨트롤러 중 하나에서 변경 제어가 필요할 수 있습니다.)
1. MMA라는 폴더를 만들 수 있습니다.
1. 다음을 다운로드하고 MMA 폴더에 배치합니다.

    **사용자 환경 및 진단 원격 분석에 대한 업데이트(Windows Server 2008 R2 및 Windows Server 2012 R2)**

    [2008 R2 Windows 2008의 경우](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [2012 Windows x64의 경우](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > 이 문서에서는 x64 기반 서버(MMA Agent .exe x64 [New SHA-2 호환 버전)를 사용 중이라 가정합니다.](https://go.microsoft.com/fwlink/?LinkId=828603)

**2단계: 파일 이름 DeployMMA.cmd 만들기(메모장 사용)** cmd 파일에 다음 줄을 추가합니다. WORKSPACE ID 및 KEY가 필요합니다.

```dos
@echo off
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" (
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a>그룹 정책 구성

"끝점용 Microsoft Defender 온보딩"처럼 특별히 온보딩 장치에 대한 새 그룹 정책을 만들 수 있습니다.

- "c:\windows\MMA"라는 그룹 정책 폴더 만들기

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="폴더를 지정합니다.":::

    **이렇게 하면 MMA라는 GPO를 적용하는 모든 서버에 새 폴더가 추가되고 c:\windows에 저장됩니다. 여기에는 MMA, 선행 구성 및 설치 스크립트에 대한 설치 파일이 포함되어 있습니다.**

- Net 로그온에 저장된 각 파일에 대해 그룹 정책 파일 기본 설정을 만들 수 있습니다.

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="그룹 정책 이미지1.":::

도메인\NETLOGON\MMA\filename의 파일을 C:\windows\MMA\filename에 복사하여 설치 파일이 서버에 **로컬로 저장됩니다.**

:::image type="content" source="images/deploymma.png" alt-text="mma cmd를 배포합니다.":::

두 KB(Windows Server 2008R2/Windows 7 및 Windows Server 2012 R2용 KB)의 경우 프로세스를 반복하지만 COMMON 탭에 항목 수준 대상 지정을 만들면 파일이 범위의 해당 플랫폼/운영 체제 버전으로만 복사됩니다.

:::image type="content" source="images/targeteditor.png" alt-text="대상 편집기.":::

- Windows Server 2008 R2의 경우 Windows6.1-BJ3080149-x64.msu가 필요하며 복사만 됩니다.
- R2의 Windows Server 2012 Windows8.1-BJ3080149-x64.msu가 필요하며(복사만 해당)

이 작업을 수행한 후 시작 스크립트 정책을 만들어야 합니다.

:::image type="content" source="images/startupprops.png" alt-text="속성을 시작합니다.":::

여기서 실행할 파일의 이름은 c:\windows\MMA\DeployMMA.cmd입니다.
시작 프로세스의 일부로 서버를 다시 시작하면 고객 환경 및 진단 원격 분석 KB에 대한 업데이트가 설치된 다음 MMA 에이전트를 설치하고 작업 영역 ID 및 키를 설정하면 서버가 온보드됩니다.

모든 서버를 다시  시작하지 않을 경우 즉시 작업을 사용하여 deployMMA.cmd를 실행할 수도 있습니다.
이 단계는 두 단계로 수행될 수 있습니다. 먼저 **GPO에서 파일** 및 폴더를 생성합니다. GPO가 적용되고 모든 서버에 설치 파일이 있도록 시스템 시간을 제공합니다. 그런 다음 직접 작업을 추가합니다. 이렇게 하면 다시 재부팅하지 않고도 동일한 결과를 얻을 수 있습니다.

Script에는 종료 메서드가 있으며 MMA가 설치된 경우 다시 실행되지 않습니다. 또한 매일 예약된 작업을 사용하여 동일한 결과를 얻을 수도 있습니다. Configuration Manager 준수 정책과 마찬가지로 MMA가 있는지 매일 검사합니다.

:::image type="content" source="images/schtask.png" alt-text="작업 예약.":::

:::image type="content" source="images/newtaskprops.png" alt-text="새 작업 속성":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="mma 다운로드 props를 배포합니다.":::

:::image type="content" source="images/tasksch.png" alt-text="작업 스케줄러.":::

Server 2008 R2 관련 서버의 온보더링 설명서에 설명된 것 처럼 아래를 참조하세요.

Windows Server 2008 R2 PS1의 경우 다음 요구 사항을 충족해야 합니다.

- [2018년 2월 월별 업데이트 롤업 설치](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

- [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) 이상 또는 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) 설치

온보드 Windows Server 2008 R2에 KB가 있는지 확인하시기 바랍니다. 이 프로세스를 통해 서버를 관리하는 Configuration Manager가 없는 경우 모든 서버를 온보드할 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [그룹 정책을 통한 Windows 10 장치 온보딩](configure-endpoints.md)
- [Windows가 아닌 장치 온보딩](configure-endpoints-non-windows.md)
- [프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md)
- [새로 온보딩된 Endpoint 디바이스용 Defender에서 검색 테스트 실행](run-detection-test.md)
- [끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
