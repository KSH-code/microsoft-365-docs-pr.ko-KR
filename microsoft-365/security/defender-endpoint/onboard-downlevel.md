---
title: Microsoft Defender for Endpoint에서 Windows 버전의 온보딩
description: 센서 데이터를 끝점용 Microsoft Defender 센서로 보낼 수 있도록 Windows 지원되는 이전 버전의 장치 온보딩
keywords: 온보드, windows, 7, 81, oms, sp1, enterprise, pro, down level
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5c4936906ba830a660c38b76c7aaf5598ba7724c
ms.sourcegitcommit: 7791c519bd8b68fc23433e13e1ecbdbeaddbebfa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60725581"
---
# <a name="onboard-previous-versions-of-windows"></a>이전 버전의 Windows 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**플랫폼**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise
- Windows Server 2008 R2 SP1

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)

Endpoint용 Defender는 지원되는 운영 체제 버전에 고급 공격 감지 및 조사 기능을 제공함으로써 지원되는 운영 체제를 포함하기 Windows 확장합니다.



클라이언트 끝점의 Windows 끝점을 Defender에 온보딩하려면 다음을 해야 합니다.


- [클라이언트 구성 및 System Center Endpoint Protection 업데이트](#configure-and-update-system-center-endpoint-protection-clients)
- [센서 데이터를 보고하도록 MMA(Microsoft Monitoring Agent)를 설치 및 구성합니다.](#install-and-configure-microsoft-monitoring-agent-mma)


Windows Server 2008 R2 SP1의 경우 [Azure Defender를 통해 온보딩할 수 있습니다.](#onboard-windows-servers-through-azure-defender)


> [!NOTE]
> 끝점 독립 실행형 서버용 Defender는 클라이언트를 통해 Windows 서버를 온보딩하려면 노드당 Microsoft Monitoring Agent 필요합니다(옵션 1). 또는 Azure Defender를 통해 Windows 서버를 등록하려면 노드당 Azure Defender for Servers 라이선스가 필요합니다(옵션 2). [Azure Defender에서](/azure/security-center/security-center-services)사용할 수 있는 지원되는 기능을 참조하세요.



> [!TIP]
> 장치를 온보드한 후 검색 테스트를 실행하여 서비스에 올바르게 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 Endpoint 끝점에 대한 검색 테스트 [실행을 참조하세요.](run-detection-test.md)

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>클라이언트 구성 및 System Center Endpoint Protection 업데이트

> [!IMPORTANT]
> 이 단계는 조직에서 SCEP(ScEP)를 사용하는 System Center Endpoint Protection 필요합니다.

Endpoint용 Defender는 System Center Endpoint Protection 맬웨어 감지에 대한 가시성을 제공하고 잠재적으로 악성 파일이나 의심되는 맬웨어를 금지하여 조직의 공격 전파를 중지하기 위해 통합되었습니다.

이 통합을 사용하려면 다음 단계가 필요합니다.

- 클라이언트용 맬웨어 방지 플랫폼 [2017년 1월 Endpoint Protection 업데이트 설치](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)
- 고급 설정으로 SCEP 클라이언트 클라우드 보호 서비스 멤버 자격 **구성**
- 클라우드에 대한 연결을 허용하도록 Microsoft Defender 바이러스 백신 구성합니다. 자세한 내용은 [Configure and validate Microsoft Defender 바이러스 백신 network connections을 참조하십시오.](/microsoft-365/security/defender-endpoint/configure-network-connections-microsoft-defender-antivirus)

## <a name="install-and-configure-microsoft-monitoring-agent-mma"></a>MMA(Microsoft Monitoring Agent 설치 및 구성) 

### <a name="before-you-begin"></a>시작하기 전에

다음 세부 정보를 검토하여 최소 시스템 요구 사항을 확인합니다.

- [2018년 2월 월별 업데이트 롤업 설치](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

  > [!NOTE]
  > Windows Server 2008 R2, Windows 7 SP1 Enterprise 및 Windows 7 SP1 Pro.

- 고객 환경 및 진단 원격 [분석에](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) 대한 업데이트 설치

- [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) 이상 또는 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) 설치

    > [!NOTE]
    > Windows Server 2008 R2, Windows 7 SP1 Enterprise 및 Windows 7 SP1 Pro.
    >
    > 4.0.x는 위의 .NET Framework 아니기 때문에 설치하지 않습니다.
    >
    > .NET 4.5를 설치하려면 설치 후 컴퓨터를 다시 시작해야 할 수 있습니다.

- Azure Log Analytics 에이전트 최소 시스템 요구 사항을 충족합니다. 자세한 내용은 Log Analytics를 사용하여 환경의 컴퓨터에서 [데이터 수집을 참조하세요.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)


### <a name="installation-steps"></a>설치 단계

1. [64비트](https://go.microsoft.com/fwlink/?LinkId=828603) 에이전트 또는 Windows [32비트](https://go.microsoft.com/fwlink/?LinkId=828604)Windows 설치 파일을 다운로드합니다.

2. 작업 영역 ID를 구합니다.
   - 끝점용 Defender 탐색 창에서 **온보딩을 설정 > 장치 관리 > 선택합니다.**
   - 운영 체제 선택
   - 작업 영역 ID 및 작업 영역 키 복사

3. 작업 영역 ID 및 작업 영역 키를 사용하여 다음 설치 방법 중 원하는 경우 에이전트를 설치합니다.
    - [설치 프로그램을 사용하여 에이전트를 수동으로 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)

      에이전트 설정 **옵션 페이지에서** 에이전트를 **커넥트 OMS(Azure Log Analytics)를 선택합니다.**

    - [명령줄을 사용하여 에이전트를 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)
    - [스크립트를 사용하여 에이전트를 구성합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

   > [!NOTE]
   > 미국 정부 [](gov.md)고객인 경우 "Azure Cloud"에서 설치 마법사를 사용하는 경우 또는 명령줄 또는 스크립트를 사용하는 경우 "azure US Government"를 선택해야 합니다. "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 매개 변수를 1로 설정해야 합니다.

4. 프록시를 사용하여 인터넷에 연결하는 경우 프록시 및 인터넷 연결 설정 구성 섹션을 참조하세요.

완료되면 1시간 이내에 포털에 온보드 엔드포인트가 표시될 것입니다.

## <a name="configure-proxy-and-internet-connectivity-settings"></a>프록시 및 인터넷 연결 설정 구성
서버에서 프록시를 사용하여 끝점용 Defender와 통신해야 하는 경우 다음 방법 중 하나를 사용하여 프록시 서버를 사용하도록 MMA를 구성합니다.

- [프록시 서버를 사용하도록 MMA 구성](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [모든 Windows 프록시 서버를 사용하도록 구성](configure-proxy-internet.md)

프록시 또는 방화벽이 사용 중이면 서버가 SSL 차단 없이 모든 끝점용 Microsoft Defender 서비스 URL에 직접 액세스할 수 있도록 합니다. 자세한 내용은 [Enable access to Defender for Endpoint service URLs을 참조하세요.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) SSL 차단을 사용하는 경우 시스템이 Endpoint용 Defender 서비스와 통신하지 못하게 됩니다.

완료되면 1시간 이내에 포털에 Windows 서버의 온보드 서버가 표시될 것입니다.


## <a name="onboard-windows-servers-through-azure-defender"></a>Azure Defender를 Windows 서버 온보딩

1. 장치 Microsoft Defender 보안 센터 창에서 장치 관리 **설정**  >    >  **를 선택합니다.**

2. 운영 **Windows Server 2008 R2 SP1을** 선택합니다.

3. **Azure 보안 센터에서 서버 온보더를 클릭합니다.**

4. [Azure Defender를 사용하여 끝점용 Microsoft Defender의](/azure/security-center/security-center-wdatp) 온보딩 지침을 따르고 Azure ARC를 사용하는 경우 끝점 통합을 위해 [Microsoft Defender](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)통합 사용의 온보딩 지침을 따릅니다.

온보더링 단계를 완료한 후 클라이언트를 구성하고 System Center Endpoint Protection [합니다.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
>
> - 서버용 Azure Defender를 통한 온보딩이 예상대로 작동하려면 서버에 MMA(서버 관리) 설정 내에 적절한 작업 Microsoft Monitoring Agent 구성해야 합니다.
> - 구성되면 적절한 클라우드 관리 팩이 컴퓨터로 배포되어 센서 프로세스(MsSenseS.exe)가 배포 및 시작됩니다.
> - 이 설정은 서버가 OMS 게이트웨이 서버를 프록시로 사용하도록 구성된 경우도 필요합니다.



## <a name="verify-onboarding"></a>온보더링 확인

Microsoft Defender AV 및 끝점용 Microsoft Defender가 실행 중인지 확인 

> [!NOTE]
> Microsoft Defender AV를 실행해야 하는 것은 아니며 권장됩니다. 다른 바이러스 백신 공급업체 제품이 기본 끝점 보호 솔루션인 경우 수동 모드에서 Defender 바이러스 백신을 실행할 수 있습니다. Microsoft Defender for Endpoint 센서(SENSE)가 실행되고 있는지 확인한 후에만 수동 모드가 설정되고 있는지 확인할 수 있습니다. 

1. 다음 명령을 실행하여 Microsoft Defender AV가 설치되어 있는지 확인합니다.

   ```sc.exe query Windefend```

    결과가 '지정된 서비스가 설치된 서비스로 존재하지 않는 경우 Microsoft Defender AV를 설치해야 합니다. 자세한 내용은 Microsoft Defender 바이러스 백신 [를 Windows 10.](microsoft-defender-antivirus-windows.md)

    그룹 정책을 사용하여 Microsoft Defender 바이러스 백신 서버에서 그룹 정책을 Windows 방법에 대한 자세한 내용은 [그룹](use-group-policy-microsoft-defender-antivirus.md)정책 설정을 사용하여 그룹 정책 구성 및 Microsoft Defender 바이러스 백신.


2. 다음 명령을 실행하여 끝점용 Microsoft Defender가 실행 중인지 확인

    ```sc.exe query sense```
    
    결과에 실행 중이 표시해야 합니다. 온보더링에 문제가 발생하는 경우 온보더링 [문제 해결을 참조합니다.](troubleshoot-onboarding.md)

## <a name="run-a-detection-test"></a>검색 테스트 실행
새로 온보딩된 장치에서 검색 테스트 실행의 단계에 따라 서버가 끝점 서비스에 대해 Defender에 보고하는지 확인합니다. [](run-detection-test.md)





## <a name="onboarding-endpoints-with-no-management-solution"></a>관리 솔루션이 없는 끝점 온보드 

### <a name="using-group-policy"></a>그룹 정책 사용

**1단계: 끝점에 해당하는 udpate를 다운로드합니다.**

1. c:\windows\sysvol\domain\scripts로 이동합니다(도메인 컨트롤러 중 하나에서 변경 제어가 필요할 수 있습니다.)
1. MMA라는 폴더를 만들 수 있습니다.
1. 다음을 다운로드하여 MMA 폴더에 배치합니다.
   
    - 고객 환경 및 진단 원격 분석에 대한 업데이트:
      - [Windows Server 2008 R2 x64의 경우](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)
     
    Windows Server 2008 R2 SP1의 경우 다음 업데이트도 필요합니다.

    2018년 2월 월별 롤업 - KB4074598(Windows Server 2008 R2)

    [Microsoft 업데이트 카탈로그](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4074598)<br>
    Windows Server 2008 R2 x64용 업데이트 다운로드
    
    .NET Framework 3.5.1(KB315418)<br>
    [Windows Server 2008 R2 x64의 경우](https://download.microsoft.com/download/6/8/0/680ee424-358c-4fdf-a0de-b45dee07b711/windows6.1-kb3154518-x64.msu)
    
    >[!NOTE]
    > 이 문서에서는 x64 기반 서버(MMA Agent .exe x64 New SHA-2 호환 버전을 사용 중이라 가정합니다.


**2단계: 파일 이름 DeployMMA.cmd 만들기(메모장 사용)** cmd 파일에 다음 줄을 추가합니다. WORKSPACE ID 및 KEY가 필요합니다.

다음 명령은 예시입니다. 다음 값을 바 사용합니다.
- KB - 온보더링할 끝점과 관련된 해당 KB 사용
- 작업 영역 ID 및 키 - ID 및 키 사용


```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (

wusa.exe C:\Windows\MMA\Windows6.1-KB3080149-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows6.1-KB4074598-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows6.1-KB3154518-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows8.1-KB3080149-x64.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /c /t: "C:\Windows\MMA"c:\windows\MMA\ setup.exe /qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID="<your workspace ID>"
OPINSIGHTS_WORKSPACE_KEY="<your workspace key>" AcceptEndUserLicenseAgreement=1
)

)
```





### <a name="group-policy-configuration"></a>그룹 정책 구성

"끝점용 Microsoft Defender 온보딩"처럼 특별히 온보딩 장치에 대한 새 그룹 정책을 만들 수 있습니다.

- "c:\windows\MMA"라는 그룹 정책 폴더 만들기

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="폴더":::

    **이렇게 하면 MMA라는 GPO를 적용하는 모든 서버에 새 폴더가 추가되고 c:\windows에 저장됩니다. 여기에는 MMA, 선행 구성 및 설치 스크립트에 대한 설치 파일이 포함되어 있습니다.**

- Net 로그온에 저장된 각 파일에 대해 그룹 정책 파일 기본 설정을 만들 수 있습니다.

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="그룹 정책 이미지1":::

도메인\NETLOGON\MMA\filename의 파일을 C:\windows\MMA\filename에 복사하여 설치 파일이 서버에 **로컬로 저장됩니다.**

:::image type="content" source="images/deploymma.png" alt-text="mma cmd 배포":::

프로세스를 반복하지만 COMMON 탭에서 항목 수준 대상 지정을 만들면 파일이 범위의 적절한 플랫폼/운영 체제 버전으로만 복사됩니다.

:::image type="content" source="images/targeteditor.png" alt-text="대상 편집기":::

Windows Server 2008 R2의 경우 다음이 필요하며 복사만 됩니다.
- Windows6.1-KB3080149-x64.msu
- Windows6.1-KB3154518-x64.msu
- Windows6.1-KB4075598-x64.msu


이 작업을 수행한 후 시작 스크립트 정책을 만들어야 합니다.

:::image type="content" source="images/startupprops.png" alt-text="속성 시작":::

여기서 실행할 파일의 이름은 c:\windows\MMA\DeployMMA.cmd입니다.
시작 프로세스의 일부로 서버를 다시 시작하면 고객 환경 및 진단 원격 분석 KB에 대한 업데이트가 설치된 다음 MMA 에이전트를 설치하고 작업 영역 ID 및 키를 설정하면 서버가 온보드됩니다.

모든 서버를 다시  시작하지 않을 경우 즉시 작업을 사용하여 deployMMA.cmd를 실행할 수도 있습니다.

이 단계는 두 단계로 수행될 수 있습니다. **먼저** GPO에 파일 및 폴더 만들기 - GPO가 적용되고 모든 서버에 설치 파일이 있도록 시스템 시간을 제공합니다. 그런 다음 직접 작업을 추가합니다. 이렇게 하면 다시 재부팅하지 않고도 동일한 결과를 얻을 수 있습니다.

Script에는 종료 메서드가 있으며 MMA가 설치된 경우 다시 실행되지 않습니다. 또한 매일 예약된 작업을 사용하여 동일한 결과를 얻을 수도 있습니다. Configuration Manager 준수 정책과 마찬가지로 MMA가 있는지 매일 검사합니다.

:::image type="content" source="images/schtask.png" alt-text="일정 작업":::

:::image type="content" source="images/newtaskprops.png" alt-text="새 작업 속성":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="mma 다운로드 제안 배포":::

:::image type="content" source="images/tasksch.png" alt-text="작업 스케줄러":::

Server 2008 R2 관련 서버의 온보더링 설명서에 언급된 경우 아래를 참조하세요. Windows Server 2008 R2 SP1의 경우 다음 요구 사항을 충족해야 합니다.

- [2018년 2월 월별 업데이트 롤업 설치](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
- [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) 이상 또는 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) 설치

Server 2008 R2를 온보드하기 전에 KB가 Windows 확인하시기 바랍니다. 이 프로세스를 통해 서버를 관리하는 Configuration Manager가 없는 경우 모든 서버를 온보드할 수 있습니다.


## <a name="offboard-endpoints"></a>끝점 오프보드

서비스에서 끝점을 Windows 두 가지 옵션을 사용할 수 있습니다.

- MMA 에이전트 제거
- 끝점용 Defender 작업 영역 구성 제거

> [!NOTE]
> 오프보드를 Windows 끝점에서 포털로 센서 데이터 전송을 중지하지만 끝점에서 전송한 경고에 대한 참조를 포함하여 끝점의 데이터는 최대 6개월 동안 보존됩니다.

### <a name="uninstall-the-mma-agent"></a>MMA 에이전트 제거

끝점을 Windows MMA 에이전트를 제거하거나 끝점용 Defender 작업 영역으로 보고에서 이 에이전트를 제거하면 됩니다. 에이전트를 오프보딩한 후 끝점은 더 이상 끝점용 Defender에 센서 데이터를 전송하지 않습니다.
자세한 내용은 에이전트를 [사용하지 않도록 설정 을 참조하세요.](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>끝점용 Defender 작업 영역 구성 제거

다음 방법 중 하나를 사용할 수 있습니다.

- MMA 에이전트에서 끝점용 Defender 작업 영역 구성 제거
- PowerShell 명령을 실행하여 구성 제거

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>MMA 에이전트에서 끝점용 Defender 작업 영역 구성 제거

1. 사용자 **Microsoft Monitoring Agent 에서** Azure **OMS(로그 분석) 탭을** 선택합니다.

2. 끝점 작업 영역용 Defender를 선택하고 제거를 **클릭합니다.**

    ![속성 Microsoft Monitoring Agent 이미지](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>PowerShell 명령을 실행하여 구성 제거

1. 작업 영역 ID를 얻게 합니다.

   1. 탐색 창에서 **온보 설정**  >  **선택합니다.**

   1. 관련 운영 체제를 선택하고 작업 영역 ID를 얻습니다.

    
2. 승강된 PowerShell을 열고 다음 명령을 실행합니다. 얻은 작업 영역 ID를 사용하여 을 `WorkspaceID` 대체합니다.

    ```   
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```
