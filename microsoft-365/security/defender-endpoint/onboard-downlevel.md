---
title: Microsoft Defender for Endpoint에서 Windows 버전의 온보딩
description: 센서 데이터를 끝점용 Microsoft Defender 센서로 보낼 수 있도록 Windows 지원되는 이전 버전의 장치 온보딩
keywords: 온보드, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d0cb4a3d01c1380f4fd06999c8f81a4054e2fd00
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844433"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="eaa57-104">이전 버전의 Windows 온보딩</span><span class="sxs-lookup"><span data-stu-id="eaa57-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eaa57-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="eaa57-105">**Applies to:**</span></span>
- [<span data-ttu-id="eaa57-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eaa57-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eaa57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eaa57-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="eaa57-108">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="eaa57-108">**Platforms**</span></span>
- <span data-ttu-id="eaa57-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eaa57-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="eaa57-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="eaa57-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="eaa57-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="eaa57-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="eaa57-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eaa57-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="eaa57-113">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="eaa57-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="eaa57-114">[무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="eaa57-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="eaa57-115">Endpoint용 Defender는 지원되는 운영 체제 버전에 고급 공격 감지 및 조사 기능을 제공함으로써 지원되는 운영 체제를 포함하기 Windows 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="eaa57-116">클라이언트 끝점의 Windows 끝점을 Defender에 온보딩하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="eaa57-117">클라이언트를 구성하고 System Center Endpoint Protection 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="eaa57-118">아래에 설명된 Microsoft Monitoring Agent 끝점용 Defender에 센서 데이터를 보고하도록 MMA(관리자)를 설치하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="eaa57-119">장치를 온보드한 후 검색 테스트를 실행하여 서비스에 올바르게 온보드되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="eaa57-120">자세한 내용은 새로 온보딩된 Endpoint 끝점에 대한 검색 테스트 [실행을 참조하세요.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="eaa57-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="eaa57-121">클라이언트 구성 및 System Center Endpoint Protection 업데이트</span><span class="sxs-lookup"><span data-stu-id="eaa57-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="eaa57-122">이 단계는 조직에서 SCEP(ScEP)를 사용하는 System Center Endpoint Protection 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="eaa57-123">Endpoint용 Defender는 System Center Endpoint Protection 맬웨어 감지에 대한 가시성을 제공하고 잠재적으로 악성 파일이나 의심되는 맬웨어를 금지하여 조직의 공격 전파를 중지하기 위해 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="eaa57-124">이 통합을 사용하려면 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="eaa57-125">클라이언트용 맬웨어 방지 플랫폼 [2017년 1월 Endpoint Protection 업데이트 설치](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="eaa57-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="eaa57-126">고급 설정으로 SCEP 클라이언트 클라우드 보호 서비스 멤버 자격 **구성**</span><span class="sxs-lookup"><span data-stu-id="eaa57-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="eaa57-127">클라우드에 대한 연결을 허용하도록 Microsoft Defender 바이러스 백신 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="eaa57-128">자세한 내용은 클라우드에 대한 연결 [Microsoft Defender 바이러스 백신 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="eaa57-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="eaa57-129">MMA(Microsoft Monitoring Agent)를 설치 및 구성하여 끝점용 Microsoft Defender에 센서 데이터 보고</span><span class="sxs-lookup"><span data-stu-id="eaa57-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="eaa57-130">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="eaa57-130">Before you begin</span></span>
<span data-ttu-id="eaa57-131">다음 세부 정보를 검토하여 최소 시스템 요구 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="eaa57-132">[2018년 2월 월별 업데이트 롤업 설치](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="eaa57-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="eaa57-133">Windows 7 SP1 Enterprise 및 Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="eaa57-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="eaa57-134">고객 환경 및 진단 원격 [분석에](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) 대한 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="eaa57-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="eaa57-135">[.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) 이상 또는 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) 설치</span><span class="sxs-lookup"><span data-stu-id="eaa57-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="eaa57-136">Windows 7 SP1 Enterprise 및 Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="eaa57-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="eaa57-137">4.0.x는 위의 .NET Framework 아니기 때문에 설치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="eaa57-138">Azure Log Analytics 에이전트 최소 시스템 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="eaa57-139">자세한 내용은 Log Analytics를 사용하여 환경의 컴퓨터에서 데이터 [수집을 참조하세요.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="eaa57-139">For more information, see [Collect data from computers in your environment with Log Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites).</span></span>



1. <span data-ttu-id="eaa57-140">[64비트](https://go.microsoft.com/fwlink/?LinkId=828603) 에이전트 또는 Windows [32비트](https://go.microsoft.com/fwlink/?LinkId=828604)Windows 설치 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="eaa57-141">작업 영역 ID를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="eaa57-142">끝점용 Defender 탐색 창에서 **온보딩을 설정 > 장치 관리 > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eaa57-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="eaa57-143">운영 **Windows 7 SP1 및 8.1을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="eaa57-144">작업 영역 ID 및 작업 영역 키 복사</span><span class="sxs-lookup"><span data-stu-id="eaa57-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="eaa57-145">작업 영역 ID 및 작업 영역 키를 사용하여 다음 설치 방법 중 원하는 경우 에이전트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="eaa57-146">[설치 프로그램을 사용하여 에이전트를 수동으로 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)</span><span class="sxs-lookup"><span data-stu-id="eaa57-146">[Manually install the agent using setup](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="eaa57-147">에이전트 설정 **옵션 페이지에서** 에이전트를 **커넥트 OMS(Azure Log Analytics)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eaa57-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="eaa57-148">[명령줄을 사용하여 에이전트를 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)</span><span class="sxs-lookup"><span data-stu-id="eaa57-148">[Install the agent using the command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="eaa57-149">[스크립트를 사용하여 에이전트를 구성합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)</span><span class="sxs-lookup"><span data-stu-id="eaa57-149">[Configure the agent using a script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="eaa57-150">미국 정부 [](gov.md)고객인 경우 "Azure Cloud"에서 설치 마법사를 사용하는 경우 또는 명령줄 또는 스크립트를 사용하는 경우 "azure US Government"를 선택해야 합니다. "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 매개 변수를 1로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="eaa57-151">프록시를 사용하여 인터넷에 연결하는 경우 프록시 설정 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eaa57-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="eaa57-152">완료되면 1시간 이내에 포털에 온보드 엔드포인트가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="eaa57-153">프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="eaa57-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="eaa57-154">각 Windows 끝점은 HTTPS를 사용하여 인터넷에 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="eaa57-155">이 연결은 프록시를 사용하여 직접 연결하거나 [OMS 게이트웨이를 통해](/azure/log-analytics/log-analytics-oms-gateway)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-155">This connection can be direct, using a proxy, or through the [OMS Gateway](/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="eaa57-156">프록시 또는 방화벽이 기본적으로 모든 트래픽을 차단하고 특정 도메인만 허용하거나 SSL 검사(SSL 검사)를 통해 허용하는 경우 끝점 서비스 URL용 [Defender에](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)대한 액세스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="eaa57-157">오프보드 클라이언트 끝점</span><span class="sxs-lookup"><span data-stu-id="eaa57-157">Offboard client endpoints</span></span>
<span data-ttu-id="eaa57-158">오프보딩을 위해 끝점에서 MMA 에이전트를 제거하거나 끝점 작업 영역용 Defender에 보고에서 이 에이전트를 제거하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="eaa57-159">에이전트를 오프보딩한 후 끝점은 더 이상 끝점용 Defender에 센서 데이터를 전송하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa57-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="eaa57-160">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="eaa57-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="eaa57-161">[무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)</span><span class="sxs-lookup"><span data-stu-id="eaa57-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>
