---
title: 끝점 DLP에 대한 장치 프록시 및 인터넷 연결 설정을 구성합니다.
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Endpoint DLP에 대한 장치 프록시 및 인터넷 연결 설정을 구성하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 801f3cf4f2215002fb80f7c4d68c2f5b83f5d04d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226710"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="866e3-103">끝점 DLP에 대한 장치 프록시 및 인터넷 연결 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="866e3-104">Microsoft Endpoint DLP는 Microsoft Windows HTTP(WinHTTP)를 사용하여 데이터를 보고하고 Microsoft 끝점 클라우드 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="866e3-105">포함된 Endpoint DLP는 LocalSystem(로컬 시스템) 계정을 사용하여 시스템 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="866e3-106">전달 프록시를 인터넷 게이트웨이로 사용하는 조직의 경우 네트워크 보호를 사용하여 프록시 뒤에서 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="866e3-107">자세한 내용은 [전달 프록시 뒤에서 발생하는 연결 이벤트 조사](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="866e3-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="866e3-108">WinHTTP 구성 설정은 Windows Internet(WinINet) 인터넷 검색 프록시 설정과 독립적이며 다음 자동 검색 방법을 사용해야만 프록시 서버를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="866e3-109">투명한 프록시</span><span class="sxs-lookup"><span data-stu-id="866e3-109">Transparent proxy</span></span>
- <span data-ttu-id="866e3-110">WPAD(웹 프록시 자동 검색) 프로토콜</span><span class="sxs-lookup"><span data-stu-id="866e3-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="866e3-111">네트워크 토폴로지에서 투명 프록시 또는 WPAD를 사용하는 경우에는 특별한 구성 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="866e3-112">프록시의 엔드포인트 URL 제외에 대한 Defender에 대한 자세한 내용은 [프록시 서버 ](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)에서 엔드포인트 DLP 클라우드 서비스 URL 액세스 사용을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="866e3-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="866e3-113">수동 정적 프록시 구성:</span><span class="sxs-lookup"><span data-stu-id="866e3-113">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="866e3-114">레지스트리 기반 구성</span><span class="sxs-lookup"><span data-stu-id="866e3-114">Registry-based configuration</span></span>
  - <span data-ttu-id="866e3-115">netsh 명령을 사용하여 구성된 WinHTTP – 안정적인 토폴로지의 데스크톱에만 적합합니다(예: 동일한 프록시 뒤에 있는 회사 네트워크의 데스크톱).</span><span class="sxs-lookup"><span data-stu-id="866e3-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="866e3-116">레지스트리 기반 정적 프록시를 사용하여 프록시 서버를 수동으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="866e3-117">인터넷에 연결할 수 없는 끝점 디바이스의 경우 레지스트리 기반 정적 프록시를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="866e3-118">Microsoft 끝점 DLP만 진단 데이터를 보고하고 Microsoft 끝점 클라우드 서비스와 통신할 수 있도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="866e3-119">정적 프록시는 GP(그룹 정책)를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="866e3-120">그룹 정책은 다음에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="866e3-121">**관리 템플릿 > Windows 구성 요소 > 데이터 수집 및 미리 보기 빌드 > 연결된 사용자 환경 및 원격 측정 서비스에 대한 인증된 프록시 사용 구성** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="866e3-122">**사용**(으)로 설정하고 **인증 프록시 사용 안 함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span>

   ![그룹 정책 설정 1의 이미지](../media/atp-gpo-proxy1.png)

3. <span data-ttu-id="866e3-124">**관리 템플릿 > Windows 구성 요소 > 데이터 수집 및 미리 보기 빌드 > 연결된 사용자 환경 및 원격 메트릭** 을(를) 여십시오.</span><span class="sxs-lookup"><span data-stu-id="866e3-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

   <span data-ttu-id="866e3-125">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="866e3-125">Configure the proxy</span></span>

   ![그룹 정책 설정 2의 이미지](../media/atp-gpo-proxy2.png)

   <span data-ttu-id="866e3-127">정책은 레지스트리 키 `HKLM\Software\Policies\Microsoft\Windows\DataCollection`에서 레지스트리 값 `TelemetryProxyServer`을(를) REG_SZ로, `DisableEnterpriseAuthProxy`을(를) REG_DWORD로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

   <span data-ttu-id="866e3-128">레지스트리 값 TelemetryProxyServer는 이 형식 \<server name or ip\>:\<port\>입니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="866e3-129">예: **10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="866e3-129">For example: **10.0.0.6:8080**</span></span>

   <span data-ttu-id="866e3-130">레지스트리 값 `DisableEnterpriseAuthProxy`을(를) 1로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="866e3-131">netsh 명령을 사용하여 프록시 서버를 수동으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="866e3-132">netsh를 사용하여 시스템 전체의 정적 프록시를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="866e3-133">이는 Windows 서비스를 포함하여 기본 프록시로 WinHTTP를 사용하는 모든 응용 프로그램에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="866e3-134">- 토폴로지를 변경하는 노트북(예: 사무실에서 가정으로)은 netsh에서 오작동합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="866e3-135">레지스트리 기반 정적 프록시 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="866e3-136">승격된 명령줄을 열기:</span><span class="sxs-lookup"><span data-stu-id="866e3-136">Open an elevated command line:</span></span>
    1. <span data-ttu-id="866e3-137">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="866e3-137">Go to **Start** and type **cmd**</span></span>
    2. <span data-ttu-id="866e3-138">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="866e3-139">다음 명령을 입력하고 **Enter** 를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-139">Enter the following command and press **Enter**:</span></span>

   `netsh winhttp set proxy <proxy>:<port>`

   <span data-ttu-id="866e3-140">예: **netsh winhttp 설정 프록시 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="866e3-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="866e3-141">winhttp 프록시를 재설정하려면 다음 명령을 입력하고 **Enter** 를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

   `netsh winhttp reset proxy`

<span data-ttu-id="866e3-142">자세한 내용은 [Netsh 명령 구문, 컨텍스트 및 포맷](/windows-server/networking/technologies/netsh/netsh-contexts)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="866e3-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="866e3-143">프록시 서버에서 끝점 DLP 클라우드 서비스 URL에 대한 액세스를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="866e3-144">프록시 또는 방화벽이 기본적으로 모든 트래픽을 차단하고 특정 도메인만 통과하도록 허용하는 경우 다운로드 가능한 시트에 나열된 도메인을 허용된 도메인 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="866e3-145">이 [다운로드 가능한 스프레드시트](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)에는 네트워크가 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-145">This [downloadable spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="866e3-146">이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인하거나 해당 URL에 대한 허용 규칙을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="866e3-147">프록시 또는 방화벽에 HTTPS 검색(SSL 검사)이 활성화된 경우 위의 표에 나열된 도메인을 HTTPS 검색에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="866e3-148">끝점 DLP가 시스템 컨텍스트에서 연결되므로 프록시 또는 방화벽이 익명 트래픽을 차단하는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="866e3-149">Microsoft 클라우드 서비스 URL에 대한 클라이언트 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="866e3-150">프록시 구성이 성공적으로 완료되었는지 확인합니다. WinHTTP는 사용자 환경의 프록시 서버를 통해 검색할 수 있으며 프록시 서버가 엔드포인트용 Defender 서비스 URL에 대한 트래픽을 허용하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="866e3-151">끝점 DLP가 실행 중인 PC에 [MDATP 클라이언트 분석기 도구](https://aka.ms/mdatpanalyzer)을(를) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="866e3-152">장치에서 MDATPC Client Analyzer.zip의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="866e3-153">승격된 명령줄을 열기:</span><span class="sxs-lookup"><span data-stu-id="866e3-153">Open an elevated command line:</span></span>
    1. <span data-ttu-id="866e3-154">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="866e3-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="866e3-155">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4. <span data-ttu-id="866e3-156">다음 명령을 입력하고 **Enter** 를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-156">Enter the following command and press **Enter**:</span></span>

   `HardDrivePath\MDATPClientAnalyzer.cmd`

   <span data-ttu-id="866e3-157">예를 들어 *HardDrivePath* 를 MDATPC 클라이언트 Analyzer 도구가 다운로드된 경로로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

   <span data-ttu-id="866e3-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="866e3-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>

5. <span data-ttu-id="866e3-159">_HardDrivePath\*에 사용된 폴더의 도구에서 생성한 **MDPCclient AnalyzerResult.zip** _ 파일의 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6. <span data-ttu-id="866e3-160">**MDATPClient AnalyzerResult.txt** 를 열고 프록시 구성 단계를 수행하여 서버 검색 및 서비스 URL 액세스를 설정했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="866e3-161">도구는 엔드포인트용 Defender 클라이언트와 상호 작용하도록 구성된 엔드포인트용 Defender 서비스 URL의 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="866e3-162">그런 다음 엔드포인트용 Defender 서비스와 통신하는 데 잠재적으로 사용될 수있는 각 URL에 대한 결과를 **MDATPClientAnalyzerResult.txt** 파일에 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="866e3-163">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-163">For example:</span></span>

   ```DOS
   Testing URL: https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command-line proxy: Doesn't exist
   ```

<span data-ttu-id="866e3-164">연결 옵션 중 하나 이상이 (200) 상태를 반환하는 경우 엔드포인트용 Defender 클라이언트는 이 연결 방법을 사용하여 테스트된 URL과 제대로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-164">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span>

<span data-ttu-id="866e3-165">그러나 연결 검사 결과가 오류를 나타내는 경우 HTTP 오류가 표시됩니다(HTTP 상태 코드 참조).</span><span class="sxs-lookup"><span data-stu-id="866e3-165">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="866e3-166">그런 다음 [프록시 서버에서 끝점 DLP 클라우드 서비스 URL에 대한 액세스 활성화](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)에 표시된 표의 URL을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-166">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="866e3-167">사용할 URL은 온보드 절차 중에 선택한 영역에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-167">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
>
> <span data-ttu-id="866e3-168">연결 분석기 도구가 ASR 규칙 [PSExec 및 WMI 명령에서 생성된 블록 프로세스 생성](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-168">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="866e3-169">연결 도구를 실행하려면 이 규칙을 일시적으로 비활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="866e3-169">You will need to temporarily disable this rule to run the connectivity tool.</span></span>
>
> <span data-ttu-id="866e3-p113">원격 측정 프록시 서버를 설정할 때 레지스트리 또는 그룹 정책을 통해 엔드포인트용 Defender가 정의된 프록시에 액세스할 수 없는 경우 직접으로 되돌아갑니다. 관련 항목:</span><span class="sxs-lookup"><span data-stu-id="866e3-p113">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy. Related topics:</span></span>
>
> - <span data-ttu-id="866e3-172">Windows 10 디바이스 온보딩</span><span class="sxs-lookup"><span data-stu-id="866e3-172">Onboard Windows 10 devices</span></span>
> - <span data-ttu-id="866e3-173">Microsoft 엔드포인트 DLP 온보딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="866e3-173">Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>

## <a name="see-also"></a><span data-ttu-id="866e3-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="866e3-174">See also</span></span>

- [<span data-ttu-id="866e3-175">끝점 데이터 손실 방지에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="866e3-175">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="866e3-176">엔드포인트 데이터 손실 방지 사용</span><span class="sxs-lookup"><span data-stu-id="866e3-176">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="866e3-177">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="866e3-177">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="866e3-178">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="866e3-178">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="866e3-179">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="866e3-179">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="866e3-180">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="866e3-180">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="866e3-181">Windows 10 컴퓨터용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="866e3-181">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="866e3-182">Microsoft 365 구독</span><span class="sxs-lookup"><span data-stu-id="866e3-182">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="866e3-183">Azure AD 가입 장치</span><span class="sxs-lookup"><span data-stu-id="866e3-183">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="866e3-184">Chromium 기반 새 Microsoft Edge 다운로드하기</span><span class="sxs-lookup"><span data-stu-id="866e3-184">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
