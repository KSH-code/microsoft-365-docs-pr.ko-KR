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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0de55eefe2f7dd8c9f891fbe126a68a49699ecd3
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594100"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="be784-104">장치 프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="be784-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="be784-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="be784-105">**Applies to:**</span></span>
- [<span data-ttu-id="be784-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="be784-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="be784-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be784-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="be784-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="be784-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="be784-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="be784-110">Endpoint용 Defender 센서를 사용하려면 Microsoft WinHTTP(Windows HTTP)가 센서 데이터를 보고하고 Endpoint용 Defender 서비스와 통신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="be784-111">포함된 Endpoint용 Defender 센서는 LocalSystem 계정을 사용하여 시스템 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="be784-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="be784-112">센서는 Microsoft Windows HTTP 서비스(WinHTTP)를 사용하여 Endpoint 클라우드 서비스용 Defender와 통신할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="be784-113">전달 프록시를 인터넷 게이트웨이로 사용하는 조직의 경우 네트워크 보호를 사용하여 프록시 뒤에서 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="be784-114">자세한 내용은 [전달 프록시 뒤에서 발생하는 연결 이벤트 조사](investigate-behind-proxy.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="be784-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="be784-115">WinHTTP 구성 설정은 WinINet(Windows Internet) 인터넷 검색 프록시 설정과는 독립적이며 다음 검색 방법을 사용하여 프록시 서버를 검색할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="be784-116">자동 검색 방법:</span><span class="sxs-lookup"><span data-stu-id="be784-116">Auto-discovery methods:</span></span>

  - <span data-ttu-id="be784-117">투명한 프록시</span><span class="sxs-lookup"><span data-stu-id="be784-117">Transparent proxy</span></span>

  - <span data-ttu-id="be784-118">WPAD(웹 프록시 자동 검색) 프로토콜</span><span class="sxs-lookup"><span data-stu-id="be784-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="be784-119">네트워크 토폴로지에서 투명 프록시 또는 WPAD를 사용하는 경우 특별한 구성 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="be784-120">프록시에서 끝점 URL 제외에 대한 Defender에 대한 자세한 내용은 프록시 서버에서 끝점 서비스 URL에 대한 Defender 액세스 사용 [을 참조하세요.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="be784-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="be784-121">수동 정적 프록시 구성:</span><span class="sxs-lookup"><span data-stu-id="be784-121">Manual static proxy configuration:</span></span>

  - <span data-ttu-id="be784-122">레지스트리 기반 구성</span><span class="sxs-lookup"><span data-stu-id="be784-122">Registry based configuration</span></span>

  - <span data-ttu-id="be784-123">netsh 명령을 사용하여 구성된 WinHTTP – 안정적인 토폴로지의 데스크톱에만 적합합니다(예: 동일한 프록시 뒤에 있는 회사 네트워크의 데스크톱).</span><span class="sxs-lookup"><span data-stu-id="be784-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="be784-124">레지스트리 기반 정적 프록시를 사용하여 프록시 서버를 수동으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="be784-125">컴퓨터가 인터넷에 연결할 수 없는 경우 Endpoint 센서용 Defender만 진단 데이터를 보고하고 Endpoint 서비스용 Defender와 통신할 수 있도록 레지스트리 기반 정적 프록시를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not permitted to connect to the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="be784-126">Windows 10 또는 Windows Server 2019에서 이 옵션을 사용하는 경우 다음(이상) 빌드 및 누적 업데이트 롤업을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span>
>
> - <span data-ttu-id="be784-127">Windows 10 버전 1809 또는 Windows Server 2019 -https://support.microsoft.com/kb/5001384</span><span class="sxs-lookup"><span data-stu-id="be784-127">Windows 10, version 1809 or Windows Server 2019 - https://support.microsoft.com/kb/5001384</span></span>
> - <span data-ttu-id="be784-128">Windows 10 버전 1909 -https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="be784-128">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span>
> - <span data-ttu-id="be784-129">Windows 10 버전 2004 -https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="be784-129">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span>
> - <span data-ttu-id="be784-130">Windows 10 버전 20H2 -https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="be784-130">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span>
>
> <span data-ttu-id="be784-131">이러한 업데이트는 CnC(명령 및 제어) 채널의 연결 및 안정성을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="be784-131">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span>

<span data-ttu-id="be784-132">정적 프록시는 GP(그룹 정책)를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-132">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="be784-133">그룹 정책은 다음에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-133">The group policy can be found under:</span></span>

- <span data-ttu-id="be784-134">**관리 템플릿 > Windows 구성 요소 > 데이터 수집 및 미리 보기 빌드> 연결된 사용자 환경 및 원격 분석 서비스에 대한 인증된 프록시 사용 구성**</span><span class="sxs-lookup"><span data-stu-id="be784-134">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

  <span data-ttu-id="be784-135">사용으로 **설정하고** 인증된 프록시 사용 안 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="be784-135">Set it to **Enabled** and select **Disable Authenticated Proxy usage**.</span></span>

  ![그룹 정책 설정의 이미지1](images/atp-gpo-proxy1.png)

- <span data-ttu-id="be784-137">**관리 템플릿 > Windows** 구성 요소 > 데이터 수집 및 Preview 빌드> 연결된 사용자 환경 및 원격 분석 구성:</span><span class="sxs-lookup"><span data-stu-id="be784-137">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

  <span data-ttu-id="be784-138">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="be784-138">Configure the proxy</span></span>

  ![그룹 정책 설정의 이미지2](images/atp-gpo-proxy2.png)

  <span data-ttu-id="be784-140">이 정책은 레지스트리 키 아래에 REG_SZ REG_DWORD 두 레지스트리 값을 REG_DWORD `TelemetryProxyServer` `DisableEnterpriseAuthProxy` 값으로 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-140">The policy sets two registry values, `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD, under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

  <span data-ttu-id="be784-141">레지스트리 값은 `TelemetryProxyServer` 다음 문자열 형식을 가합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-141">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

  ```text
  <server name or ip>:<port>
  ```

  <span data-ttu-id="be784-142">예: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="be784-142">For example: 10.0.0.6:8080</span></span>

  <span data-ttu-id="be784-143">레지스트리 값 `DisableEnterpriseAuthProxy`을(를) 1로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-143">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="be784-144">netsh 명령을 사용하여 수동으로 프록시 서버 구성</span><span class="sxs-lookup"><span data-stu-id="be784-144">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="be784-145">netsh를 사용하여 시스템 전체의 정적 프록시를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-145">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="be784-146">이는 Windows 서비스를 포함하여 기본 프록시로 WinHTTP를 사용하는 모든 응용 프로그램에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="be784-146">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="be784-147">토폴로지(예: 사무실에서 집으로)를 변경하는 랩톱이 netsh로 오작동합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-147">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="be784-148">레지스트리 기반 정적 프록시 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-148">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="be784-149">승격된 명령줄을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="be784-149">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="be784-150">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="be784-150">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="be784-151">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="be784-152">다음 명령을 입력하고 **Enter** 를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="be784-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="be784-153">예: `netsh winhttp set proxy 10.0.0.6:8080`</span><span class="sxs-lookup"><span data-stu-id="be784-153">For example: `netsh winhttp set proxy 10.0.0.6:8080`</span></span>

<span data-ttu-id="be784-154">winhttp 프록시를 재설정하려면 다음 명령을 입력하고 **Enter** 를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="be784-154">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="be784-155">자세한 내용은 [Netsh 명령 구문, 컨텍스트 및 포맷](/windows-server/networking/technologies/netsh/netsh-contexts)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="be784-155">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="be784-156">프록시 서버에서 끝점용 Microsoft Defender 서비스 URL에 대한 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="be784-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="be784-157">프록시 또는 방화벽이 기본적으로 모든 트래픽을 차단하고 특정 도메인만 통과하도록 허용하는 경우 다운로드 가능한 시트에 나열된 도메인을 허용된 도메인 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="be784-158">다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="be784-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="be784-159">이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 또는 해당 URL에 대한 허용 규칙을 만들어야 할 수도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="be784-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


| <span data-ttu-id="be784-160">도메인 목록의 스프레드시트</span><span class="sxs-lookup"><span data-stu-id="be784-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="be784-161">설명</span><span class="sxs-lookup"><span data-stu-id="be784-161">Description</span></span> |
|:-----|:-----|
|![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지](images/mdatp-urls.png)<br/>  | <span data-ttu-id="be784-163">서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="be784-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="be784-164">여기에서 스프레드시트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="be784-165">프록시 또는 방화벽에 HTTPS 검색(SSL 검사)이 활성화된 경우 위의 표에 나열된 도메인을 HTTPS 검색에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="be784-166">settings-win.data.microsoft.com 1803 이전 버전을 실행 중인 Windows 10 디바이스가 있는 경우 이 업데이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="be784-167">v20이 포함된 URL은 버전 1803 이상을 실행하는 Windows 10 있는 경우 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="be784-168">예를 들어 버전 1803 이상을 Windows 10 US Data Storage 장치에 `us-v20.events.data.microsoft.com` 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-168">For example, `us-v20.events.data.microsoft.com` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="be784-169">환경에서 Microsoft Defender 바이러스 백신 사용하는 경우 Configure network [connections to the Microsoft Defender 바이러스 백신 cloud service을 참조합니다.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="be784-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="be784-170">프록시 또는 방화벽이 익명 트래픽을 차단하는 경우 Endpoint용 Defender 센서가 시스템 컨텍스트에서 연결하고 있는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="be784-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="be784-171">Microsoft Monitoring Agent(MMA) - 이전 버전의 Windows 클라이언트 또는 Windows Server에 대한 프록시 및 방화벽 요구 사항</span><span class="sxs-lookup"><span data-stu-id="be784-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="be784-172">아래 정보에는 Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 및 이전 버전의 Windows 버전에 대한 Log Analytics 에이전트(Microsoft Monitoring Agent라고도임)와 통신하는 데 필요한 프록시 및 방화벽 구성 정보가 Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="be784-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="be784-173">에이전트 리소스</span><span class="sxs-lookup"><span data-stu-id="be784-173">Agent Resource</span></span>|<span data-ttu-id="be784-174">포트</span><span class="sxs-lookup"><span data-stu-id="be784-174">Ports</span></span> |<span data-ttu-id="be784-175">Direction</span><span class="sxs-lookup"><span data-stu-id="be784-175">Direction</span></span> |<span data-ttu-id="be784-176">HTTPS 검사 무시</span><span class="sxs-lookup"><span data-stu-id="be784-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="be784-177">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="be784-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="be784-178">포트 443</span><span class="sxs-lookup"><span data-stu-id="be784-178">Port 443</span></span> |<span data-ttu-id="be784-179">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="be784-179">Outbound</span></span>|<span data-ttu-id="be784-180">예</span><span class="sxs-lookup"><span data-stu-id="be784-180">Yes</span></span> |  
|<span data-ttu-id="be784-181">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="be784-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="be784-182">포트 443</span><span class="sxs-lookup"><span data-stu-id="be784-182">Port 443</span></span> |<span data-ttu-id="be784-183">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="be784-183">Outbound</span></span>|<span data-ttu-id="be784-184">예</span><span class="sxs-lookup"><span data-stu-id="be784-184">Yes</span></span> |  
|<span data-ttu-id="be784-185">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="be784-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="be784-186">포트 443</span><span class="sxs-lookup"><span data-stu-id="be784-186">Port 443</span></span> |<span data-ttu-id="be784-187">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="be784-187">Outbound</span></span>|<span data-ttu-id="be784-188">예</span><span class="sxs-lookup"><span data-stu-id="be784-188">Yes</span></span> |
|<span data-ttu-id="be784-189">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="be784-189">\*.azure-automation.net</span></span> |<span data-ttu-id="be784-190">포트 443</span><span class="sxs-lookup"><span data-stu-id="be784-190">Port 443</span></span> |<span data-ttu-id="be784-191">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="be784-191">Outbound</span></span>|<span data-ttu-id="be784-192">예</span><span class="sxs-lookup"><span data-stu-id="be784-192">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="be784-193">클라우드 기반 솔루션으로 IP 범위는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="be784-194">DNS 확인할 수 있는 설정으로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="be784-195">MMA(Microsoft Monitoring Agent) 서비스 URL 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="be784-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="be784-196">이전 버전의 MMA(Microsoft Monitoring Agent)를 사용할 때 특정 환경에 대한 와일드카드(\*) 요구 사항을 제거하기 위해 다음 지침을 Windows.</span><span class="sxs-lookup"><span data-stu-id="be784-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="be784-197">MMA(Microsoft Monitoring Agent)를 통해 이전 운영 체제를 끝점용 Defender에 온보딩합니다(자세한 내용은 [Endpoint용 Defender](https://go.microsoft.com/fwlink/p/?linkid=2010326) 및 Windows 서버에 이전 버전의 Windows [온보딩을 참조하세요.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="be784-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="be784-198">컴퓨터의 포털에 보고하는 Microsoft Defender 보안 센터 합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-198">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="be784-199">"C:\Program Files\Microsoft Monitoring Agent\Agent"에서 TestCloudConnection.exe 도구를 실행하여 연결의 유효성을 검사하고 특정 작업 영역의 필수 URL을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="be784-200">Microsoft Defender for Endpoint URL 목록을 확인하여 해당 지역의 전체 요구 사항 목록을 확인합니다(서비스 URL 스프레드시트를 [참조하세요).](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)</span><span class="sxs-lookup"><span data-stu-id="be784-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

    ![조직의 관리자 Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="be784-202">\*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com 및 *.agentsvc.azure-automation.net URL 끝점에서 사용되는 와일드카드(*)를 특정 작업 영역 ID로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="be784-203">작업 영역 ID는 환경 및 작업 영역과 관련이 있으며, 작업 영역 포털 내에서 테넌트의 온보드 섹션에서 Microsoft Defender 보안 센터 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="be784-204">\*.blob.core.windows.net URL 끝점을 테스트 결과의 "방화벽 규칙: \*.blob.core.windows.net" 섹션에 표시된 URL로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="be784-205">Azure Defender를 통한 온보딩의 경우 여러 작업 영역이 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-205">In the case of onboarding via Azure Defender, multiple workspaces maybe used.</span></span> <span data-ttu-id="be784-206">각 작업 영역의 온보드된 TestCloudConnection.exe 위의 절차에 따라 작업 영역 간에 \*.blob.core.windows.net URL이 변경되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="be784-207">끝점 서비스 URL용 Microsoft Defender에 대한 클라이언트 연결 확인</span><span class="sxs-lookup"><span data-stu-id="be784-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="be784-208">프록시 구성이 성공적으로 완료되었는지 확인합니다. WinHTTP는 사용자 환경의 프록시 서버를 통해 검색할 수 있으며 프록시 서버가 엔드포인트용 Defender 서비스 URL에 대한 트래픽을 허용하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="be784-209">[끝점용 MDATP](https://aka.ms/mdatpanalyzer) 실행 중인 PC에 클라이언트 분석기 도구를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="be784-210">장치에서 MDATPC Client Analyzer.zip의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="be784-211">승격된 명령줄을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="be784-211">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="be784-212">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="be784-212">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="be784-213">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-213">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="be784-214">다음 명령을 입력하고 **Enter** 를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="be784-214">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="be784-215">*HardDrivePath를* MDATPClientAnalyzer 도구가 다운로드된 경로로 대체합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-215">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example:</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="be784-216">*HardDrivePath에서* *MDATPClientAnalyzerResult.zip* 도구로 만든 파일 추출</span><span class="sxs-lookup"><span data-stu-id="be784-216">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="be784-217">*MDATPClient AnalyzerResult.txt* 를 열고 프록시 구성 단계를 수행하여 서버 검색 및 서비스 URL 액세스를 설정했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-217">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>

   <span data-ttu-id="be784-218">도구는 엔드포인트용 Defender 클라이언트와 상호 작용하도록 구성된 엔드포인트용 Defender 서비스 URL의 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-218">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="be784-219">그런 다음 엔드포인트용 Defender 서비스와 통신하는 데 잠재적으로 사용될 수있는 각 URL에 대한 결과를 *MDATPClientAnalyzerResult.txt* 파일에 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-219">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="be784-220">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-220">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="be784-221">연결 옵션 중 하나 이상이 (200) 상태를 반환하는 경우 엔드포인트용 Defender 클라이언트는 이 연결 방법을 사용하여 테스트된 URL과 제대로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-221">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span>

<span data-ttu-id="be784-222">그러나 연결 검사 결과가 오류를 나타내는 경우 HTTP 오류가 표시됩니다(HTTP 상태 코드 참조).</span><span class="sxs-lookup"><span data-stu-id="be784-222">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="be784-223">그런 다음 프록시 서버 에서 [Defender for Endpoint](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)서비스 URL에 대한 액세스 사용에 표시된 표의 URL을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-223">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="be784-224">사용할 URL은 온보더링 절차 중에 선택한 지역에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-224">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="be784-225"> 연결 분석기 도구가 ASR 규칙 [ PSExec 및 WMI 명령 ](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)에서 생성된 블록 프로세스 생성과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be784-225">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="be784-226">연결 도구를 실행하려면 이 규칙을 일시적으로 비활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be784-226">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="be784-227">TelemetryProxyServer가 설정되어 있는 경우 레지스트리 또는 그룹 정책을 통해 끝점에 대한 Defender가 정의된 프록시에 액세스할 수 없는 경우 직접로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="be784-227">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="be784-228">관련 항목</span><span class="sxs-lookup"><span data-stu-id="be784-228">Related topics</span></span>

- [<span data-ttu-id="be784-229">그룹 정책을 통한 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="be784-229">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="be784-230">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="be784-230">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
