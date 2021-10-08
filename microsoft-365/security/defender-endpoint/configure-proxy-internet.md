---
title: 장치 프록시 및 인터넷 연결 설정 구성
description: 클라우드 서비스와 통신할 수 있도록 끝점 프록시 및 인터넷 설정에 대한 Microsoft Defender를 구성합니다.
keywords: 구성, 프록시, 인터넷, 인터넷 연결, 설정, 프록시 설정, netsh, winhttp, 프록시 서버
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 42f21f27e30cc4a2bc4af5a2ecefd07c7353d96a
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240227"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>디바이스 프록시 및 인터넷 연결 설정 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Endpoint용 Defender 센서를 사용하려면 Microsoft WinHTTP(Windows HTTP)가 센서 데이터를 보고하고 Endpoint용 Defender 서비스와 통신해야 합니다.

포함된 Endpoint용 Defender 센서는 LocalSystem 계정을 사용하여 시스템 컨텍스트에서 실행됩니다. 센서는 Microsoft Windows HTTP 서비스(WinHTTP)를 사용하여 Endpoint 클라우드 서비스용 Defender와 통신할 수 있도록 합니다.

> [!TIP]
> 인터넷에 대한 게이트웨이로 전방 Proxies를 사용하는 조직의 경우 네트워크 보호를 사용하여 전방 proxies 뒤에 발생하는 연결 이벤트를 [조사할 수 있습니다.](investigate-behind-proxy.md)

WinHTTP 구성 설정은 WinINet(Windows Internet) 검색 프록시 설정과는 독립적이며 다음 검색 방법을 사용하여 프록시 서버를 검색할 수만 있습니다.

- 자동 검색 방법:

  - 투명한 프록시
  
  - WPAD(웹 프록시 자동 검색) 프로토콜

    > [!NOTE]
    > 네트워크 토폴로지에서 투명 프록시 또는 WPAD를 사용하는 경우 특별한 구성 설정이 필요하지 않습니다. 프록시에서 끝점 URL 제외에 대한 Defender에 대한 자세한 내용은 프록시 서버에서 끝점 서비스 URL에 대한 Defender 액세스 사용 [을 참조하세요.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

- 수동 정적 프록시 구성:

  - 레지스트리 기반 구성
  
  - netsh 명령을 사용하여 구성된 WinHTTP: 안정적인 토폴로지의 데스크톱에만 적합합니다(예: 같은 프록시 뒤에 있는 회사 네트워크의 데스크톱).

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>레지스트리 기반 정적 프록시를 사용하여 프록시 서버를 수동으로 구성합니다.

컴퓨터가 인터넷에 연결할 수 없는 경우 진단 데이터를 보고하고 끝점 서비스용 Defender와 통신하도록 끝점 검색 및 응답(EDR) 센서에 대한 Defender에 대한 레지스트리 기반 정적 프록시를 구성합니다.

> [!NOTE]
> Windows 10 또는 Windows 11 또는 Windows Server 2019 또는 Windows Server 2022에서 이 옵션을 사용하는 경우 다음 빌드 및 누적 업데이트 롤업을 사용하는 것이 좋습니다.
>
> - Windows 11
> - Windows 10, 버전 1809 Windows Server 2019 또는 Windows Server 2022 -<https://support.microsoft.com/kb/5001384>
> - Windows 10 버전 1909 -<https://support.microsoft.com/kb/4601380>
> - Windows 10 버전 2004 -<https://support.microsoft.com/kb/4601382>
> - Windows 10 버전 20H2 -<https://support.microsoft.com/kb/4601382>
>
> 이러한 업데이트는 CnC(명령 및 제어) 채널의 연결 및 안정성을 향상시킵니다.

정적 프록시는 GP(그룹 정책)를 통해 구성할 수 있습니다. 그룹 정책은 다음에서 확인할 수 있습니다.

- **관리 템플릿 > Windows** 구성 요소 > 데이터 수집 및 미리 보기 빌드 > 사용자 환경 및 원격 분석 서비스에 대해 인증된 프록시 사용 구성.

  사용으로 **설정하고** 인증된 프록시 사용 안 **을 선택합니다.**

  ![그룹 정책 설정의 이미지1.](images/atp-gpo-proxy1.png)

- **관리 템플릿 > Windows** 구성 요소 > 데이터 수집 및 Preview 빌드> 연결된 사용자 환경 및 원격 분석 구성:

  프록시 구성

  ![그룹 정책 설정의 이미지 2.](images/atp-gpo-proxy2.png)


| 그룹 정책 | 레지스트리 키 | 레지스트리 항목 | 값 |
|:---|:---|:---|:---|
| 연결된 사용자 환경 및 원격 분석 서비스에 대해 인증된 프록시 사용 구성 | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `DisableEnterpriseAuthProxy` | 1(REG_DWORD) |
| 연결된 사용자 환경 및 원격 분석 구성 | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `TelemetryProxyServer` | ```http://servername or ip:port``` <br> <br> 예: ```http://10.0.0.6:8080``` (REG_SZ) |

## <a name="configure-a-static-proxy-for-microsoft-defender-antivirus"></a>사용자에 대한 정적 프록시 Microsoft Defender 바이러스 백신

Microsoft Defender 바이러스 백신 클라우드 [제공](cloud-protection-microsoft-defender-antivirus.md) 보호는 새로운 위협과 새로운 위협으로부터 거의 즉각적으로 자동화된 보호 기능을 제공합니다. Defender 바이러스 백신이 [](manage-indicators.md) 활성 맬웨어 방지 솔루션인 경우 사용자 지정 표시기에는 연결이 필요합니다. 또한 [EDR](edr-in-block-mode.md) Microsoft가 아닌 솔루션을 기본 맬웨어 방지 솔루션으로 사용하는 경우에도 차단 모드로 전환할 수 있습니다.

여기에서 찾은 그룹 정책을 사용하여 정적 프록시를 구성합니다.

1. 관리 템플릿 > Windows 구성 요소 > Microsoft Defender 바이러스 백신 > 네트워크에 연결할 프록시 서버 정의 **를 정의합니다.** 

2. 이 옵션을 **사용으로 설정하고** 프록시 서버를 정의합니다. URL에 1000만 http:// 있어야 https://. 지원되는 버전의 https:// 업데이트 관리를 [Microsoft Defender 바이러스 백신 참조하세요.](manage-updates-baselines-microsoft-defender-antivirus.md)

   :::image type="content" source="images/proxy-server-mdav.png" alt-text="서버의 프록시 Microsoft Defender 바이러스 백신.":::

3. 레지스트리 키 아래에서 정책은 레지스트리 값을 레지스트리 값으로  `HKLM\Software\Policies\Microsoft\Windows Defender`  `ProxyServer`   REG_SZ. 

   레지스트리 값은  `ProxyServer`   다음 문자열 형식을 가합니다.

    ```text
    <server name or ip>:<port>

    For example: http://10.0.0.6:8080
    ```

> [!NOTE]
>
> 탄력성 목적 및 클라우드 제공 보호의 실시간 특성을 위해 Microsoft Defender 바이러스 백신 마지막으로 알려진 작업 프록시를 캐시합니다. 보안 클라우드 연결이 끊어지기 때문에 프록시 솔루션에서 SSL 검사를 수행하지 않는지 확인합니다. 
>
> Microsoft Defender 바이러스 백신 업데이트 다운로드를 위해 Windows 또는 Microsoft 업데이트에 연결하는 데 정적 프록시를 사용하지 않습니다. 대신 업데이트 업데이트 또는 구성된 Windows 순서에 따라 구성된 내부 업데이트 원본을 사용하도록 구성된 경우 시스템 전체 [프록시를 사용합니다.](manage-protection-updates-microsoft-defender-antivirus.md) 
>
> 필요한 경우 관리 템플릿 > Windows 구성 요소> Microsoft Defender 바이러스 백신 > 여러 프록시가 있는 고급 구성을 설정해야 하는 경우 네트워크에 연결하기 위해 프록시 자동 구성 **정의(.pac)를** 사용할 수 **있습니다.** 관리 템플릿 > Windows 구성 요소 > Microsoft Defender 바이러스 백신 > 프록시 서버를 무시할 주소 정의를 사용하여 Microsoft Defender 바이러스 백신 해당 대상에 프록시 서버를 사용하지 못하게 할 수 있습니다. 
>
> Cmdlet과 함께 PowerShell을 사용하여 `Set-MpPreference` 다음 옵션을 구성할 수 있습니다. 
>
> - ProxyBypass 
> - ProxyPacUrl 
> - ProxyServer 

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>netsh 명령을 사용하여 수동으로 프록시 서버 구성

netsh를 사용하여 시스템 전체의 정적 프록시를 구성합니다.

> [!NOTE]
>
> - 이는 Windows 서비스를 포함하여 기본 프록시로 WinHTTP를 사용하는 모든 응용 프로그램에 영향을 미칩니다.</br>
> - 토폴로지(예: 사무실에서 집으로)를 변경하는 랩톱이 netsh로 오작동합니다. 레지스트리 기반 정적 프록시 구성을 사용합니다.

1. 승격된 명령줄을 열기:
   1. **시작**(으)로 이동하고 **cmd** 를 입력하십시오.
   1. **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

2. 다음 명령을 입력하고 **Enter** 를 누릅니다.

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   예: `netsh winhttp set proxy 10.0.0.6:8080`

winhttp 프록시를 재설정하려면 다음 명령을 입력하고 **Enter** 를 누릅니다.

```PowerShell
netsh winhttp reset proxy
```

자세한 내용은 [Netsh 명령 구문, 컨텍스트 및 포맷](/windows-server/networking/technologies/netsh/netsh-contexts)을 참조하십시오.

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>프록시 서버에서 끝점용 Microsoft Defender 서비스 URL에 대한 액세스 사용

프록시 또는 방화벽이 기본적으로 모든 트래픽을 차단하고 특정 도메인만 통과하도록 허용하는 경우 다운로드 가능한 시트에 나열된 도메인을 허용된 도메인 목록에 추가합니다.

다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다. 이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인하거나  해당 URL에 대한 허용 규칙을 만들어야 할 수 있습니다.

<br>

**** 
|도메인 목록의 스프레드시트|설명|
|---|---|
|![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지입니다.](images/mdatp-urls.png)|서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다. <p> [여기에서 스프레드시트를 다운로드합니다.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)|
|

프록시 또는 방화벽에 HTTPS 검색(SSL 검사)이 활성화된 경우 위의 표에 나열된 도메인을 HTTPS 검색에서 제외합니다.
방화벽에서 지리 열이 WW인 모든 URL을 열 수 있습니다. 지역 열이 WW가 아닌 행의 경우 특정 데이터 위치에 대한 URL을 여는 것입니다. 데이터 위치 설정을 확인하려면 데이터 저장소 위치 확인 [및 끝점용 Microsoft Defender에 대한 데이터 보존 설정 업데이트를 참조하세요.](/microsoft-365/security/defender-endpoint/data-retention-settings)

> [!NOTE]
> settings-win.data.microsoft.com 1803 이전 버전을 실행하는 Windows 디바이스가 있는 경우만 이 기능을 사용할 수 있습니다.<br>
>
> v20이 포함된 URL은 버전 1803 이상을 실행하는 Windows 있는 경우 필요합니다. 예를 들어 버전 1803 이상을 Windows 미국 데이터 센터 지역으로 온보드된 Storage `us-v20.events.data.microsoft.com` 필요합니다.
>
> 환경에서 Microsoft Defender 바이러스 백신 사용하는 경우 Configure network [connections to the Microsoft Defender 바이러스 백신 cloud service을 참조합니다.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)

프록시 또는 방화벽이 익명 트래픽을 차단하는 경우 Endpoint용 Defender 센서가 시스템 컨텍스트에서 연결하고 있는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인하십시오.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent(MMA) - 이전 버전의 Windows 클라이언트 또는 Windows Server에 대한 프록시 및 방화벽 요구 사항

아래 정보에는 Windows 7 SP1, Windows 8.1 및 Windows Server 2008 R2* 등의 이전 버전의 Windows에 대해 Log Analytics 에이전트(Microsoft Monitoring Agent라고도임)와 통신하는 데 필요한 프록시 및 방화벽 구성 정보가 나열되어 있습니다.

<br>

****

|에이전트 리소스|포트|방향|HTTP 검사 바이패스|
|---|---|---|---|
|*.ods.opinsights.azure.com|포트 443|아웃바운드|예|
|*.oms.opinsights.azure.com|포트 443|아웃바운드|예|
|*.blob.core.windows.net|포트 443|아웃바운드|예|
|*.azure-automation.net|포트 443|아웃바운드|예|

>[!NOTE]
>*이러한 연결 요구 사항은 MMA가 필요한 Windows Server 2016 및 Windows Server 2012 R2용 이전의 Microsoft Defender for Endpoint에도 적용됩니다. 새 통합 솔루션으로 이러한 운영 체제를 온보딩하는 지침은 [온보딩](configure-server-endpoints.md)Windows 서버 또는 [끝점용 Microsoft Defender의](/microsoft-365/security/defender-endpoint/server-migration)서버 마이그레이션 시나리오에서 새 연결되지 않은 솔루션으로 마이그레이션하는 것입니다.

> [!NOTE]
> 클라우드 기반 솔루션으로 IP 범위는 변경될 수 있습니다. DNS 확인할 수 있는 설정으로 이동하는 것이 좋습니다.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>MMA(Microsoft Monitoring Agent) 서비스 URL 요구 사항 확인 

 이전 버전의 MMA(Microsoft Monitoring Agent)를 사용할 때 특정 환경에 대한 와일드카드(*) 요구 사항을 Windows.

1.  MMA(Microsoft Monitoring Agent)를 통해 이전 운영 체제를 끝점용 Defender에 온보딩합니다(자세한 내용은 [Endpoint용 Defender](https://go.microsoft.com/fwlink/p/?linkid=2010326) 및 Windows 서버에 이전 버전의 Windows [온보딩을 참조하세요.](configure-server-endpoints.md)

2. 컴퓨터의 포털에 보고하는 Microsoft 365 Defender 합니다.

3. "C:\Program Files\Microsoft Monitoring Agent\Agent"에서 TestCloudConnection.exe 도구를 실행하여 연결의 유효성을 검사하고 특정 작업 영역의 필수 URL을 확인할 수 있습니다.

4. Microsoft Defender for Endpoint URL 목록을 확인하여 해당 지역의 전체 요구 사항 목록을 확인합니다(서비스 URL 스프레드시트 [참조).](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

    ![조직의 관리자 Windows PowerShell.](images/admin-powershell.png)

.ods.opinsights.azure.com, .oms.opinsights.azure.com 및 .agentsvc.azure-automation.net URL 끝점에 사용되는 와일드카드( )를 특정 작업 영역 ID로 바꿀 \* \* 수 \* \* 있습니다. 작업 영역 ID는 환경 및 작업 영역과 관련이 있으며, 작업 영역 포털 내의 테넌트 온보더링 섹션에서 Microsoft 365 Defender 있습니다.

.blob.core.windows.net URL 끝점을 테스트 결과의 \* "방화벽 규칙: .blob.core.windows.net" 섹션에 표시된 URL로 바꿀 \* 수 있습니다.

> [!NOTE]
> Azure Defender를 통한 온보딩의 경우 여러 작업 영역이 사용될 수 있습니다. 각 작업 영역의 온보드된 TestCloudConnection.exe 위의 절차에 따라 작업 영역 간에 *.blob.core.windows.net URL이 변경되어 있는지 확인해야 합니다.

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>끝점 서비스 URL용 Microsoft Defender에 대한 클라이언트 연결 확인

프록시 구성이 성공적으로 완료되었는지 확인합니다. WinHTTP는 사용자 환경의 프록시 서버를 통해 검색할 수 있으며 프록시 서버가 엔드포인트용 Defender 서비스 URL에 대한 트래픽을 허용하는지 여부를 확인할 수 있습니다.

1. [Endpoint용 Microsoft Defender 클라이언트 분석기 도구를 Endpoint용](https://aka.ms/mdeanalyzer) Defender 센서가 실행되는 PC에 다운로드합니다.

2. 디바이스에서 콘텐츠 MDEClientAnalyzer.zip 추출합니다.

3. 승격된 명령줄을 엽니다.
   1. **시작**(으)로 이동하고 **cmd** 를 입력하십시오.
   1. **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

4. 다음 명령을 입력하고 **Enter** 를 누릅니다.

    ```PowerShell
    HardDrivePath\MDEClientAnalyzer.cmd
    ```

    *HardDrivePath를* MDEClientAnalyzer 도구가 다운로드된 경로로 바 대체합니다. 예를 들면 다음과 같습니다.

    ```PowerShell
    C:\Work\tools\MDEClientAnalyzer\MDEClientAnalyzer.cmd
    ```

5. *HardDrivePath에서* *MDEClientAnalyzerResult.zip* 도구로 만든 파일 추출

6. 서비스 *MDEClientAnalyzerResult.txt* 열고 프록시 구성 단계를 수행하여 서버 검색 및 서비스 URL 액세스를 사용하도록 설정해야 합니다.

   도구는 엔드포인트용 Defender 클라이언트와 상호 작용하도록 구성된 엔드포인트용 Defender 서비스 URL의 연결을 확인합니다. 그런 다음 최종MDEClientAnalyzerResult.txt용  Defender와 통신하는 데 사용할 수 있는 각 URL에 대한 결과를 파일로 출력합니다. 예를 들어 다음과 같습니다.

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

연결 옵션 중 하나 이상이 (200) 상태를 반환하는 경우 엔드포인트용 Defender 클라이언트는 이 연결 방법을 사용하여 테스트된 URL과 제대로 통신할 수 있습니다.

그러나 연결 검사 결과가 오류를 나타내는 경우 HTTP 오류가 표시됩니다(HTTP 상태 코드 참조). 그런 다음 프록시 서버 에서 [Defender for Endpoint](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)서비스 URL에 대한 액세스 사용에 표시된 표의 URL을 사용할 수 있습니다. 사용할 URL은 온보더링 절차 중에 선택한 지역에 따라 다를 수 있습니다.

> [!NOTE]
> 연결 분석기 도구 클라우드 연결 검사는 PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단 공격 표면 감소 규칙과 [호환되지 않습니다.](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules.md#block-process-creations-originating-from-psexec-and-wmi-commands) 연결 도구를 실행하려면 이 규칙을 일시적으로 비활성화해야 합니다. 또는 분석기를 실행하면 [ASR](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction.md#exclude-files-and-folders) 제외를 일시적으로 추가할 수 있습니다.
>
> TelemetryProxyServer가 설정되어 있는 경우 레지스트리 또는 그룹 정책을 통해 끝점에 대한 Defender가 정의된 프록시에 액세스할 수 없는 경우 직접로 변경됩니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사](configure-network-connections-microsoft-defender-antivirus.md)
- [그룹 정책 설정을 사용하여 그룹 정책 Microsoft Defender 바이러스 백신](use-group-policy-microsoft-defender-antivirus.md)
- [그룹 정책을 통한 Windows 장치 온보딩](configure-endpoints.md)
- [끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
