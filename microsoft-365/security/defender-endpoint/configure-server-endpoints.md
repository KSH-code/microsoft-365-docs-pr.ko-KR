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
ms.openlocfilehash: 08fe4314c1461710d83ea7aeba1fdf9a60dd33a8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339241"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="6a0db-104">끝점 Windows Microsoft Defender에 서버 온보딩</span><span class="sxs-lookup"><span data-stu-id="6a0db-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a0db-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6a0db-105">**Applies to:**</span></span>

- <span data-ttu-id="6a0db-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="6a0db-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="6a0db-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6a0db-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="6a0db-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6a0db-108">Windows Server 2016</span></span>
- <span data-ttu-id="6a0db-109">Windows SAC(서버) 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="6a0db-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="6a0db-110">Windows Server 2019 이상</span><span class="sxs-lookup"><span data-stu-id="6a0db-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="6a0db-111">Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="6a0db-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="6a0db-112">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6a0db-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6a0db-113">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="6a0db-114">Endpoint용 Defender는 Windows 서버 운영 체제를 포함하기 위해 지원을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="6a0db-115">이 지원은 보안 콘솔을 통해 고급 공격 감지 및 조사 기능을 Microsoft 365 Defender 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft 365 Defender console.</span></span>

<span data-ttu-id="6a0db-116">라이선스 및 인프라에 필요한 사항을 실제로 설명하는 내용은 [Endpoint용 Defender로 Windows 서버 보호를 참조하세요.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)</span><span class="sxs-lookup"><span data-stu-id="6a0db-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="6a0db-117">Windows 보안 서버의 기본 Windows 다운로드하고 사용하는 방법에 대한 지침은 Windows 보안 [참조하세요.](/windows/device-security/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="6a0db-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="6a0db-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 및 Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6a0db-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="6a0db-119">다음 옵션 중 Windows Server 2008 R2 SP1, Windows Server 2012 R2 및 Windows Server 2016 Defender for Endpoint에 온보딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="6a0db-120">**옵션 1:** MMA(Microsoft Monitoring Agent 설치 및 구성하여 [온보더링)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="6a0db-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="6a0db-121">**옵션 2:** [Azure 보안 센터를 통해 온보더](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="6a0db-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="6a0db-122">**옵션 3:** [Microsoft Endpoint Manager 버전 2002 이상을](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later) 통해 온보드</span><span class="sxs-lookup"><span data-stu-id="6a0db-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="6a0db-123">제공된 옵션 중 원하는 옵션을 사용하여 온보더링 단계를 완료한 후 클라이언트를 구성하고 System Center Endpoint Protection [합니다.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="6a0db-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="6a0db-124">Windows(옵션 1) 또는 Microsoft Endpoint Manager(옵션 3)를 통해 Windows Microsoft Monitoring Agent 서버를 온보딩하려면 노드당 Defender가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="6a0db-125">또는 Azure 보안 센터를 통해 Windows 서버를 온보딩하려면 노드당 Azure Defender for Servers 라이선스가 필요합니다(옵션 2). [Azure Defender에서](/azure/security-center/security-center-services)사용할 수 있는 지원되는 기능을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a0db-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="6a0db-126">옵션 1: MMA(Microsoft Monitoring Agent 설치 및 구성하여 온보더링)</span><span class="sxs-lookup"><span data-stu-id="6a0db-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="6a0db-127">끝점용 Defender에 센서 데이터를 보고하도록 Windows MMA를 설치하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="6a0db-128">자세한 내용은 Azure Log Analytics 에이전트를 사용하여 로그 데이터 [수집을 참조하세요.](/azure/azure-monitor/platform/log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="6a0db-128">For more information, see [Collect log data with Azure Log Analytics agent](/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="6a0db-129">SCOM(System Center Operations Manager) 또는 Azure 모니터(이전의 OM Microsoft Monitoring Agent S(Operations Management Suite))를 이미 사용 중이면 MMA(Operations Management Suite)를 연결하여 다중 호밍 지원을 통해 끝점 작업 영역용 Defender에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="6a0db-130">일반적으로 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="6a0db-131">시작하기 전에 섹션에 설명된 **온보더링 요구 사항을 이행합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="6a0db-132">포털에서 서버 Microsoft 365 Defender 켜기.</span><span class="sxs-lookup"><span data-stu-id="6a0db-132">Turn on server monitoring from Microsoft 365 Defender portal.</span></span>
3. <span data-ttu-id="6a0db-133">서버가 끝점용 Defender에 센서 데이터를 보고하도록 MMA를 설치하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="6a0db-134">클라이언트를 구성하고 System Center Endpoint Protection 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="6a0db-135">장치를 온보드한 후 검색 테스트를 실행하여 서비스에 올바르게 온보드되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="6a0db-136">자세한 내용은 새로 온보딩된 Endpoint 끝점에 대한 검색 테스트 [실행을 참조하세요.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="6a0db-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="6a0db-137">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6a0db-137">Before you begin</span></span>

<span data-ttu-id="6a0db-138">다음 단계를 수행하여 온보더링 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="6a0db-139">Windows Server 2008 R2 SP1 또는 Windows Server 2012 R2의 경우 다음 핫픽스를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="6a0db-140">고객 환경 및 진단 원격 분석에 대한 업데이트</span><span class="sxs-lookup"><span data-stu-id="6a0db-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="6a0db-141">Windows Server 2008 R2 SP1의 경우 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="6a0db-142">[2월](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598) 월간 업데이트 롤업 설치</span><span class="sxs-lookup"><span data-stu-id="6a0db-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="6a0db-143">[.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) 이상 또는 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) 설치</span><span class="sxs-lookup"><span data-stu-id="6a0db-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a0db-144">SCCM을 통해 Windows Server 2008 R2 SP1을 관리하는 경우 SCCM 클라이언트 에이전트는 .Net Framework 4.5.2를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="6a0db-145">따라서 .NET Framework 4.5 이상을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="6a0db-146">Windows Server 2008 R2 SP1 및 Windows Server 2012 R2의 경우: 클라이언트 System Center Endpoint Protection [구성 및 업데이트합니다.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="6a0db-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="6a0db-147">이 단계는 조직에서 SCEP(System Center Endpoint Protection)를 사용하며 Windows Server 2008 R2 SP1 및 R2를 Windows Server 2012 하는 Windows Server 2012 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="6a0db-148">MMA(Microsoft Monitoring Agent)를 설치 및 구성하여 끝점용 Microsoft Defender에 센서 데이터 보고</span><span class="sxs-lookup"><span data-stu-id="6a0db-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="6a0db-149">64비트 Windows 설치 파일을 [다운로드합니다.](https://go.microsoft.com/fwlink/?LinkId=828603)</span><span class="sxs-lookup"><span data-stu-id="6a0db-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="6a0db-150">이전 절차에서 얻은 작업 영역 ID 및 작업 영역 키를 사용하여 다음 설치 방법을 선택하고 에이전트를 Windows 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="6a0db-151">[설치 프로그램을 사용하여 에이전트를 수동으로 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)</span><span class="sxs-lookup"><span data-stu-id="6a0db-151">[Manually install the agent using setup](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="6a0db-152">에이전트 설정 **옵션 페이지에서** **에이전트를 커넥트 OMS(Azure Log Analytics) 로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="6a0db-153">[명령줄을 사용하여 에이전트를 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)</span><span class="sxs-lookup"><span data-stu-id="6a0db-153">[Install the agent using the command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="6a0db-154">[스크립트를 사용하여 에이전트를 구성합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)</span><span class="sxs-lookup"><span data-stu-id="6a0db-154">[Configure the agent using a script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="6a0db-155">미국 정부 [](gov.md)고객인 경우 "Azure Cloud"에서 설치 마법사를 사용하는 경우 또는 명령줄 또는 스크립트를 사용하는 경우 "azure US Government"를 선택해야 합니다. "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 매개 변수를 1로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="6a0db-156">필요한 Windows 서버 프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="6a0db-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="6a0db-157">서버에서 프록시를 사용하여 끝점용 Defender와 통신해야 하는 경우 다음 방법 중 하나를 사용하여 프록시 서버를 사용하도록 MMA를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="6a0db-158">프록시 서버를 사용하도록 MMA 구성</span><span class="sxs-lookup"><span data-stu-id="6a0db-158">Configure the MMA to use a proxy server</span></span>](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="6a0db-159">모든 Windows 프록시 서버를 사용하도록 구성</span><span class="sxs-lookup"><span data-stu-id="6a0db-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="6a0db-160">프록시 또는 방화벽이 사용 중이면 서버가 SSL 차단 없이 모든 끝점용 Microsoft Defender 서비스 URL에 직접 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="6a0db-161">자세한 내용은 [Enable access to Defender for Endpoint service URLs을 참조하세요.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="6a0db-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="6a0db-162">SSL 차단을 사용하는 경우 시스템이 Endpoint용 Defender 서비스와 통신하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="6a0db-163">완료되면 1시간 이내에 포털에 Windows 서버의 온보드 서버가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="6a0db-164">옵션 2: Azure Windows 서버 온보드</span><span class="sxs-lookup"><span data-stu-id="6a0db-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="6a0db-165">Microsoft 365 Defender 창에서 **끝점 설정** 관리 온보더링을  >    >    >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-165">In the Microsoft 365 Defender navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="6a0db-166">운영 **Windows Server 2008 R2 SP1, 2012 R2 및 2016을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="6a0db-167">**Azure 보안 센터에서 서버 온보더를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="6a0db-168">[Azure Defender를 사용하여 끝점용 Microsoft Defender의](/azure/security-center/security-center-wdatp) 온보딩 지침을 따르고 Azure ARC를 사용하는 경우 끝점 통합을 위해 [Microsoft Defender](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)통합 사용의 온보딩 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="6a0db-169">온보더링 단계를 완료한 후 클라이언트를 구성하고 System Center Endpoint Protection [합니다.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="6a0db-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="6a0db-170">서버용 Azure Defender를 통한 온보딩이 예상대로 작동하려면 서버에 MMA(서버 관리) 설정 내에 적절한 작업 Microsoft Monitoring Agent 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="6a0db-171">구성되면 적절한 클라우드 관리 팩이 컴퓨터로 배포되어 센서 프로세스(MsSenseS.exe)가 배포 및 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="6a0db-172">이 설정은 서버가 OMS 게이트웨이 서버를 프록시로 사용하도록 구성된 경우도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="6a0db-173">옵션 3: Microsoft Endpoint Manager 2002 이상을 통해 Windows 서버 온보드</span><span class="sxs-lookup"><span data-stu-id="6a0db-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="6a0db-174">2002 버전 Windows Server 2012 사용하여 R2 및 Windows Server 2016 Microsoft Endpoint Manager 온보드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="6a0db-175">자세한 내용은 현재 분기의 [끝점용 Microsoft Defender를 Microsoft Endpoint Manager 참조하세요.](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="6a0db-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="6a0db-176">온보더링 단계를 완료한 후 클라이언트를 구성하고 System Center Endpoint Protection [합니다.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="6a0db-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="6a0db-177">Windows SAC(서버) 버전 1803, Windows Server 2019 및 Windows Server 2019 Core edition</span><span class="sxs-lookup"><span data-stu-id="6a0db-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="6a0db-178">다음 배포 방법을 사용하여 Windows Server(Windows Server) 버전 1803, Windows Server 2019 또는 Windows Server 2019 Core Edition을 온보드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="6a0db-179">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="6a0db-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="6a0db-180">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="6a0db-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="6a0db-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6a0db-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="6a0db-182">System Center Configuration Manager 2012/2012 R2 1511/ 1602</span><span class="sxs-lookup"><span data-stu-id="6a0db-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="6a0db-183">비영구 장치에 대한 VDI 온보딩 스크립트</span><span class="sxs-lookup"><span data-stu-id="6a0db-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="6a0db-184">현재 스크립트를 Windows Server 2019를 Microsoft Endpoint Manager 온보딩 패키지</span><span class="sxs-lookup"><span data-stu-id="6a0db-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="6a0db-185">Configuration Manager에서 스크립트를 배포하는 방법에 대한 자세한 내용은 Configuration Manager의 패키지 [및 프로그램을 참조하세요.](/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="6a0db-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="6a0db-186">로컬 스크립트는 개념 증명에 적합하지만 프로덕션 배포에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="6a0db-187">프로덕션 배포의 경우 그룹 정책을 사용하는 것이 Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6a0db-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="6a0db-188">Windows Server에 대한 지원은 서버 활동, 커널 및 메모리 공격 감지 범위에 대한 심층적인 정보를 제공하며 대응 작업을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="6a0db-189">장치와 동일한 도구 및 방법을 사용하여 Windows 서버에서 끝점 온보딩 설정에 대한 Defender를 Windows 10 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="6a0db-190">자세한 내용은 장치 [온보드 Windows 10 참조하세요.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="6a0db-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="6a0db-191">타사 맬웨어 방지 솔루션을 실행하는 경우 다음 Microsoft Defender AV 수동 모드 설정을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="6a0db-192">올바르게 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="6a0db-193">다음 레지스트리 항목을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a0db-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="6a0db-194">경로: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="6a0db-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="6a0db-195">이름: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="6a0db-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="6a0db-196">유형: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="6a0db-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="6a0db-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="6a0db-197">Value: 1</span></span>

    1. <span data-ttu-id="6a0db-198">수동 모드가 구성되어 있는지 확인하도록 다음 PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="6a0db-199">수동 모드 이벤트가 포함된 최근 이벤트가 발견된지 확인:</span><span class="sxs-lookup"><span data-stu-id="6a0db-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![수동 모드 확인 결과의 이미지](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="6a0db-201">다음 명령을 실행하여 Microsoft Defender AV가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="6a0db-202">결과가 '지정된 서비스가 설치된 서비스로 존재하지 않는 경우 Microsoft Defender AV를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="6a0db-203">자세한 내용은 Microsoft Defender 바이러스 백신 [를 Windows 10.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)</span><span class="sxs-lookup"><span data-stu-id="6a0db-203">For more information, see [Microsoft Defender Antivirus in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="6a0db-204">그룹 정책을 사용하여 Microsoft Defender 바이러스 백신 서버에서 그룹 정책을 Windows 방법에 대한 자세한 내용은 [그룹](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)정책 설정을 사용하여 그룹 정책 구성 및 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="6a0db-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="6a0db-205">Azure Defender와 통합</span><span class="sxs-lookup"><span data-stu-id="6a0db-205">Integration with Azure Defender</span></span>

<span data-ttu-id="6a0db-206">Endpoint용 Defender는 Azure Defender와 통합하여 포괄적인 서버 Windows 솔루션을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="6a0db-207">이 통합을 통해 Azure Defender는 끝점용 Defender의 기능을 사용하여 서버의 위협 감지 기능을 Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="6a0db-208">이 통합에는 다음과 같은 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="6a0db-209">자동 온보딩 - Azure Defender에 온보딩된 Windows Endpoint용 Defender 센서가 자동으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="6a0db-210">Azure Defender 온보딩에 대한 자세한 내용은 [통합된 끝점용 Microsoft Defender 라이선스 사용을 참조하세요.](/azure/security-center/security-center-wdatp)</span><span class="sxs-lookup"><span data-stu-id="6a0db-210">For more information on Azure Defender onboarding, see [Use the integrated Microsoft Defender for Endpoint license](/azure/security-center/security-center-wdatp).</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a0db-211">서버용 Azure Defender와 끝점용 Microsoft Defender 간의 통합은 Windows [Server 2019 및 WVD(가상 데스크톱)Windows](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)지원하기 위해 확장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="6a0db-212">Windows Azure Defender가 모니터링하는 서버는 Endpoint용 Defender에서도 사용할 수 있습니다. Azure Defender는 끝점 테넌트용 Defender에 원활하게 연결하여 클라이언트와 서버 전체에서 단일 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="6a0db-213">또한 Azure Defender 콘솔에서 끝점용 Defender 경고를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="6a0db-214">서버 조사 - Azure Defender 고객은 Microsoft 365 Defender 포털에 액세스하여 자세한 조사를 수행하여 잠재적인 위반 범위를 밝히는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-214">Server investigation -  Azure Defender customers can access Microsoft 365 Defender portal to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="6a0db-215">Azure Defender를 사용하여 서버를 모니터링하면 끝점 테넌트에 대한 Defender가 자동으로 만들어집니다(미국 사용자의 경우 유럽 및 영국 사용자용 EU).</span><span class="sxs-lookup"><span data-stu-id="6a0db-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="6a0db-216">Endpoint용 Defender에서 수집한 데이터는 프로비전 중에 식별된 테넌트의 지리적 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="6a0db-217">Azure Defender를 사용하기 전에 Endpoint용 Defender를 사용하는 경우 나중에 Azure Defender와 통합하는 경우에도 테넌트를 만들 때 지정한 위치에 데이터가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="6a0db-218">일단 구성되면 데이터가 저장되는 위치를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="6a0db-219">데이터를 다른 위치로 이동해야 하는 경우 Microsoft 지원에 문의하여 테넌트를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="6a0db-220">이러한 통합을 활용하는 서버 끝점 모니터링은 Office 365 GCC 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="6a0db-221">클라이언트 구성 및 System Center Endpoint Protection 업데이트</span><span class="sxs-lookup"><span data-stu-id="6a0db-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="6a0db-222">Endpoint용 Defender는 통합된 System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="6a0db-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="6a0db-223">통합을 통해 맬웨어 감지에 대한 가시성을 확보하고 잠재적인 악성 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격 전파를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="6a0db-224">이 통합을 사용하려면 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="6a0db-225">Endpoint Protection [맬웨어](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)방지 플랫폼 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="6a0db-226">[고급 설정으로 SCEP](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 클라이언트 클라우드 보호 서비스 멤버 **자격을 구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-226">[Configure the SCEP client Cloud Protection Service membership](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="6a0db-227">서버 Windows 오프보드</span><span class="sxs-lookup"><span data-stu-id="6a0db-227">Offboard Windows servers</span></span>

<span data-ttu-id="6a0db-228">SAC(Windows Server), Windows Server 2019 및 Windows Server 2019 Core Edition은 클라이언트 장치에서 사용할 수 있는 동일한 방법으로 Windows 10 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="6a0db-229">다른 Windows 서버 버전의 경우 서비스에서 서버 Windows 오프보드할 수 있는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="6a0db-230">MMA 에이전트 제거</span><span class="sxs-lookup"><span data-stu-id="6a0db-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="6a0db-231">끝점용 Defender 작업 영역 구성 제거</span><span class="sxs-lookup"><span data-stu-id="6a0db-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="6a0db-232">오프보드를 통해 Windows 서버는 포털에 센서 데이터 전송을 중지하지만 Windows 서버에 있는 모든 경고에 대한 참조를 포함하여 데이터까지 최대 6개월 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="6a0db-233">MMA Windows 제거하여 서버 제거</span><span class="sxs-lookup"><span data-stu-id="6a0db-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="6a0db-234">Windows 서버를 오프보딩하기 위해 MMA 에이전트를 Windows 끝점 작업 영역의 Defender에 보고에서 이 에이전트를 제거하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="6a0db-235">에이전트를 오프보딩한 후 Windows 서버는 더 이상 끝점용 Defender로 센서 데이터를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="6a0db-236">자세한 내용은 에이전트를 [사용하지 않도록 설정 을 참조하세요.](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)</span><span class="sxs-lookup"><span data-stu-id="6a0db-236">For more information, see [To disable an agent](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="6a0db-237">끝점용 Defender 작업 영역 구성 제거</span><span class="sxs-lookup"><span data-stu-id="6a0db-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="6a0db-238">서버의 Windows 다음 방법 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="6a0db-239">MMA 에이전트에서 끝점용 Defender 작업 영역 구성 제거</span><span class="sxs-lookup"><span data-stu-id="6a0db-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="6a0db-240">PowerShell 명령을 실행하여 구성 제거</span><span class="sxs-lookup"><span data-stu-id="6a0db-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="6a0db-241">MMA 에이전트에서 끝점용 Defender 작업 영역 구성 제거</span><span class="sxs-lookup"><span data-stu-id="6a0db-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="6a0db-242">사용자 **Microsoft Monitoring Agent 에서** Azure **OMS(로그 분석) 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="6a0db-243">끝점 작업 영역용 Defender를 선택하고 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![속성 Microsoft Monitoring Agent 이미지](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="6a0db-245">PowerShell 명령을 실행하여 구성 제거</span><span class="sxs-lookup"><span data-stu-id="6a0db-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="6a0db-246">작업 영역 ID를 얻게 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="6a0db-247">Microsoft 365 Defender 창에서 **끝점 설정** 관리 온보더링을  >    >    >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-247">In the Microsoft 365 Defender navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

   1. <span data-ttu-id="6a0db-248">운영 **Windows Server 2008 R2 SP1, 2012 R2 및 2016을** 선택하고 작업 영역 ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![서버 Windows 이미지](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="6a0db-250&quot;>승강된 PowerShell을 열고 다음 명령을 실행합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6a0db-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;6a0db-251&quot;>얻은 작업 영역 ID를 사용하여 을 `WorkspaceID` 대체합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6a0db-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="6a0db-252">관리 솔루션이 없는 온보드 서버</span><span class="sxs-lookup"><span data-stu-id="6a0db-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="6a0db-253">그룹 정책 사용</span><span class="sxs-lookup"><span data-stu-id="6a0db-253">Using Group Policy</span></span>

<span data-ttu-id="6a0db-254">**1단계: 서버에 복사하는 데 필요한 파일을 생성합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="6a0db-255">c:\windows\sysvol\domain\scripts로 이동합니다(도메인 컨트롤러 중 하나에서 변경 제어가 필요할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="6a0db-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="6a0db-256">MMA라는 폴더를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="6a0db-257">다음을 다운로드하고 MMA 폴더에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="6a0db-258">**사용자 환경 및 진단 원격 분석에 대한 업데이트(Windows Server 2008 R2 및 Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="6a0db-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="6a0db-259">2008 R2 Windows 2008의 경우</span><span class="sxs-lookup"><span data-stu-id="6a0db-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="6a0db-260">2012 Windows x64의 경우</span><span class="sxs-lookup"><span data-stu-id="6a0db-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="6a0db-261">이 문서에서는 x64 기반 서버(MMA Agent .exe x64 [New SHA-2 호환 버전)를 사용 중이라 가정합니다.](https://go.microsoft.com/fwlink/?LinkId=828603)</span><span class="sxs-lookup"><span data-stu-id="6a0db-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="6a0db-262">**2단계: 파일 이름 DeployMMA.cmd 만들기(메모장 사용)** cmd 파일에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="6a0db-263">WORKSPACE ID 및 KEY가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-263">Note that you'll need your WORKSPACE ID and KEY.</span></span>

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

## <a name="group-policy-configuration"></a><span data-ttu-id="6a0db-264">그룹 정책 구성</span><span class="sxs-lookup"><span data-stu-id="6a0db-264">Group Policy Configuration</span></span>

<span data-ttu-id="6a0db-265">"끝점용 Microsoft Defender 온보딩"처럼 특별히 온보딩 장치에 대한 새 그룹 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="6a0db-266">"c:\windows\MMA"라는 그룹 정책 폴더 만들기</span><span class="sxs-lookup"><span data-stu-id="6a0db-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="폴더":::

    <span data-ttu-id="6a0db-268">**이렇게 하면 MMA라는 GPO를 적용하는 모든 서버에 새 폴더가 추가되고 c:\windows에 저장됩니다. 여기에는 MMA, 선행 구성 및 설치 스크립트에 대한 설치 파일이 포함되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="6a0db-269">Net 로그온에 저장된 각 파일에 대해 그룹 정책 파일 기본 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="그룹 정책 이미지1":::

<span data-ttu-id="6a0db-271">도메인\NETLOGON\MMA\filename의 파일을 C:\windows\MMA\filename에 복사하여 설치 파일이 서버에 **로컬로 저장됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6a0db-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="mma cmd 배포":::

<span data-ttu-id="6a0db-273">두 KB(Windows Server 2008R2/Windows 7 및 Windows Server 2012 R2용 KB)의 경우 프로세스를 반복하지만 COMMON 탭에 항목 수준 대상 지정을 만들면 파일이 범위의 해당 플랫폼/운영 체제 버전으로만 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="대상 편집기":::

- <span data-ttu-id="6a0db-275">Windows Server 2008 R2의 경우 Windows6.1-BJ3080149-x64.msu가 필요하며 복사만 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="6a0db-276">R2의 Windows Server 2012 Windows8.1-BJ3080149-x64.msu가 필요하며(복사만 해당)</span><span class="sxs-lookup"><span data-stu-id="6a0db-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="6a0db-277">이 작업을 수행한 후 시작 스크립트 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="속성 시작":::

<span data-ttu-id="6a0db-279">여기서 실행할 파일의 이름은 c:\windows\MMA\DeployMMA.cmd입니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd.</span></span>
<span data-ttu-id="6a0db-280">시작 프로세스의 일부로 서버를 다시 시작하면 고객 환경 및 진단 원격 분석 KB에 대한 업데이트가 설치된 다음 MMA 에이전트를 설치하고 작업 영역 ID 및 키를 설정하면 서버가 온보드됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-280">Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMA Agent, while setting the Workspace ID and Key, and the server will be onboarded.</span></span>

<span data-ttu-id="6a0db-281">모든 서버를 다시  시작하지 않을 경우 즉시 작업을 사용하여 deployMMA.cmd를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-281">You could also use an **immediate task** to run the deployMMA.cmd if you don't want to reboot all the servers.</span></span>
<span data-ttu-id="6a0db-282">이 단계는 두 단계로 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-282">This could be done in two phases.</span></span> <span data-ttu-id="6a0db-283">**먼저** GPO에서 파일 및 폴더 만들기 - GPO가 적용되고 모든 서버에 설치 파일이 있도록 시스템 시간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-283">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="6a0db-284">그런 다음 직접 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-284">Then, add the immediate task.</span></span> <span data-ttu-id="6a0db-285">이렇게 하면 다시 재부팅하지 않고도 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-285">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="6a0db-286">Script에는 종료 메서드가 있으며 MMA가 설치된 경우 다시 실행되지 않습니다. 또한 매일 예약된 작업을 사용하여 동일한 결과를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-286">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="6a0db-287">Configuration Manager 준수 정책과 마찬가지로 MMA가 있는지 매일 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-287">Similar to a Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="일정 작업":::

:::image type="content" source="images/newtaskprops.png" alt-text="새 작업 속성":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="mma 다운로드 제안 배포":::

:::image type="content" source="images/tasksch.png" alt-text="작업 스케줄러":::

<span data-ttu-id="6a0db-292">Server 2008 R2 관련 서버의 온보더링 설명서에 설명된 것 처럼 아래를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a0db-292">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="6a0db-293">Windows Server 2008 R2 PS1의 경우 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-293">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="6a0db-294">[2018년 2월 월별 업데이트 롤업 설치](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="6a0db-294">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="6a0db-295">[.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) 이상 또는 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) 설치</span><span class="sxs-lookup"><span data-stu-id="6a0db-295">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="6a0db-296">온보드 Windows Server 2008 R2에 KB가 있는지 확인하시기 바랍니다. 이 프로세스를 통해 서버를 관리하는 Configuration Manager가 없는 경우 모든 서버를 온보드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0db-296">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a0db-297">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6a0db-297">Related topics</span></span>

- [<span data-ttu-id="6a0db-298">그룹 정책을 통한 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="6a0db-298">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="6a0db-299">Windows가 아닌 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="6a0db-299">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="6a0db-300">프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="6a0db-300">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="6a0db-301">새로 온보딩된 Endpoint 디바이스용 Defender에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="6a0db-301">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="6a0db-302">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6a0db-302">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
