---
title: 끝점용 Microsoft Defender에 인터넷 액세스 없이 장치 온보딩
ms.reviewer: ''
description: 끝점용 Microsoft Defender 센서로 센서 데이터를 보낼 수 있도록 인터넷에 연결하지 않고 장치 온보딩
keywords: 온보드, 서버, vm, 온-프레미스, oms 게이트웨이, 로그 분석, Azure 로그 분석, mma
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
ms.openlocfilehash: fb5a9a4d35af2d400cdff1e417727e662738514e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861350"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="a5d25-104">끝점용 Microsoft Defender에 인터넷 액세스 없이 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="a5d25-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a5d25-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a5d25-105">**Applies to:**</span></span>
- [<span data-ttu-id="a5d25-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a5d25-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a5d25-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5d25-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a5d25-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a5d25-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a5d25-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d25-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="a5d25-110">인터넷에 연결하지 않고 장치를 온보드하려면 다음과 같은 일반적인 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d25-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="a5d25-111">아래 단계는 Windows Server 2016 이하 또는 Windows 8.1 이하와 같은 이전 버전의 Windows를 실행하는 디바이스에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d25-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="a5d25-112">'TelemetryProxyServer' 레지스트리 또는 GPO를 통해 구성된 경우 연결이 끊어진 Windows 10 또는 Windows Server 2019 장치의 프록시로 OMS 게이트웨이 서버를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d25-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="a5d25-113">Windows 10 또는 Windows Server 2019의 경우 - TelemetryProxyServer를 사용할 수 있는 동안 표준 프록시 장치 또는 어플라이언스를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d25-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="a5d25-114">또한 연결이 끊어진 환경의 Windows 10 또는 Windows Server 2019는 내부 파일 또는 웹 서버를 통해 오프라인으로 인증서 신뢰 목록을 업데이트할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d25-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="a5d25-115">오프라인으로 CTL을 업데이트하는 데 대한 자세한 내용은 CTL 파일을 다운로드하도록 파일 또는 웹 서버 [구성을 참조하세요.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)</span><span class="sxs-lookup"><span data-stu-id="a5d25-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="a5d25-116">온보더링 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5d25-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="a5d25-117">이전 버전의 Windows 온보딩</span><span class="sxs-lookup"><span data-stu-id="a5d25-117">Onboard previous versions of Windows</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="a5d25-118">끝점용 Microsoft Defender 서비스에 서버 온보딩</span><span class="sxs-lookup"><span data-stu-id="a5d25-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="a5d25-119">장치 프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="a5d25-119">Configure device proxy and Internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="a5d25-120">사내 장치</span><span class="sxs-lookup"><span data-stu-id="a5d25-120">On-premise devices</span></span>

- <span data-ttu-id="a5d25-121">프록시 또는 허브 역할을 하게 Azure Log Analytics(이전의 OMS 게이트웨이)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d25-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="a5d25-122">Azure Log Analytics 에이전트</span><span class="sxs-lookup"><span data-stu-id="a5d25-122">Azure Log Analytics Agent</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="a5d25-123">[끝점 작업 영역용 Defender를 위한 MMA(Microsoft](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) 모니터링 에이전트) 지점 설치 및 & ID</span><span class="sxs-lookup"><span data-stu-id="a5d25-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="a5d25-124">Azure Log Analytics의 동일한 네트워크에서 오프라인 장치</span><span class="sxs-lookup"><span data-stu-id="a5d25-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="a5d25-125">MMA를 구성하여:</span><span class="sxs-lookup"><span data-stu-id="a5d25-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="a5d25-126">프록시로 Azure Log Analytics IP</span><span class="sxs-lookup"><span data-stu-id="a5d25-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="a5d25-127">Endpoint 작업 영역용 Defender & ID</span><span class="sxs-lookup"><span data-stu-id="a5d25-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="a5d25-128">Azure 가상 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="a5d25-128">Azure virtual machines</span></span>
- <span data-ttu-id="a5d25-129">[Azure Log Analytics 작업](https://docs.microsoft.com/azure/azure-monitor/platform/gateway) 영역 구성 및 사용</span><span class="sxs-lookup"><span data-stu-id="a5d25-129">Configure and enable [Azure Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="a5d25-130">프록시 또는 허브 역할을 하게 Azure Log Analytics Gateway(이전의 OMS 게이트웨이)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d25-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="a5d25-131">Azure Log Analytics 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="a5d25-131">Azure Log Analytics Gateway</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="a5d25-132">[끝점 작업 영역용 Defender를 위한 MMA(Microsoft](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) 모니터링 에이전트) 지점 설치 및 & ID</span><span class="sxs-lookup"><span data-stu-id="a5d25-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="a5d25-133">동일한 OMS 게이트웨이 네트워크의 오프라인 Azure VM</span><span class="sxs-lookup"><span data-stu-id="a5d25-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="a5d25-134">Azure Log Analytics IP를 프록시로 구성</span><span class="sxs-lookup"><span data-stu-id="a5d25-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="a5d25-135">Azure Log Analytics 작업 영역 키 & ID</span><span class="sxs-lookup"><span data-stu-id="a5d25-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="a5d25-136">AZURE 보안 센터(ASC)</span><span class="sxs-lookup"><span data-stu-id="a5d25-136">Azure Security Center (ASC)</span></span>
      - [<span data-ttu-id="a5d25-137">보안 정책 \> 로그 분석 작업 영역</span><span class="sxs-lookup"><span data-stu-id="a5d25-137">Security Policy \> Log Analytics Workspace</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="a5d25-138">위협 감지 끝점에서 내 데이터에 액세스할 수 있도록 \> 허용</span><span class="sxs-lookup"><span data-stu-id="a5d25-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="a5d25-139">자세한 내용은 보안 정책 [작업을 참조하세요.](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)</span><span class="sxs-lookup"><span data-stu-id="a5d25-139">For more information, see [Working with security policies](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span></span>
