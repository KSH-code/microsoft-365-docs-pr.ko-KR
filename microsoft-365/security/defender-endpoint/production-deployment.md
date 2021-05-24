---
title: 끝점 배포를 위한 Microsoft Defender 설정
description: 끝점용 Microsoft Defender 배포를 설정하는 방법을 설명합니다.
keywords: 배포, 설정, 라이선스 유효성 검사, 테넌트 구성, 네트워크 구성
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b49565c45c1f38d0d2ce71b097af079782ba4de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636197"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="a521f-104">끝점 배포를 위한 Microsoft Defender 설정</span><span class="sxs-lookup"><span data-stu-id="a521f-104">Set up Microsoft Defender for Endpoint deployment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a521f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a521f-105">**Applies to:**</span></span>
- [<span data-ttu-id="a521f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a521f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a521f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a521f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a521f-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a521f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a521f-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a521f-110">끝점용 Defender 배포는 3단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="a521f-111">[![배포 단계 - 준비](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="a521f-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="a521f-112">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="a521f-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | ![배포 단계 - 설정](images/phase-diagrams/setup.png)<br><span data-ttu-id="a521f-114">2 단계: 설정</span><span class="sxs-lookup"><span data-stu-id="a521f-114">Phase 2: Setup</span></span> | <span data-ttu-id="a521f-115">[![배포 단계 - 온보드](images/phase-diagrams/onboard.png)](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="a521f-115">[![deployment phase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span></span><br>[<span data-ttu-id="a521f-116">3 단계: 온보딩</span><span class="sxs-lookup"><span data-stu-id="a521f-116">Phase 3: Onboard</span></span>](onboarding.md) |
| ----- | ----- | ----- |
| | <span data-ttu-id="a521f-117">*여기 있습니다!*</span><span class="sxs-lookup"><span data-stu-id="a521f-117">*You are here!*</span></span>||

<span data-ttu-id="a521f-118">현재 설정 단계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-118">You are currently in the set-up phase.</span></span>

<span data-ttu-id="a521f-119">이 배포 시나리오에서는 다음 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-119">In this deployment scenario, you'll be guided through the steps on:</span></span>
- <span data-ttu-id="a521f-120">라이선스 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a521f-120">Licensing validation</span></span>
- <span data-ttu-id="a521f-121">테넌트 구성</span><span class="sxs-lookup"><span data-stu-id="a521f-121">Tenant configuration</span></span>
- <span data-ttu-id="a521f-122">네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="a521f-122">Network configuration</span></span>


>[!NOTE]
><span data-ttu-id="a521f-123">일반적인 배포를 안내하기 위해 이 시나리오는 일반적인 배포를 안내하는 용도로만 Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a521f-123">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="a521f-124">Endpoint용 Defender는 다른 온보딩 도구를 사용할 수 있지만 배포 가이드에서 이러한 시나리오를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-124">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="a521f-125">자세한 내용은 [끝점용 Microsoft Defender에 장치 온보딩을 참조하세요.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a521f-125">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="check-license-state"></a><span data-ttu-id="a521f-126">라이선스 상태 확인</span><span class="sxs-lookup"><span data-stu-id="a521f-126">Check license state</span></span>

<span data-ttu-id="a521f-127">라이선스 상태를 확인하고 적절히 프로비전되었는지 여부는 관리 센터 또는 라이선스 **포털을 통해** Microsoft Azure 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-127">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="a521f-128">라이선스를 확인하기 위해 Microsoft Azure **포털로** 이동하여 Microsoft Azure 포털 라이선스 섹션으로 [이동합니다.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="a521f-128">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 라이선스 페이지의 이미지](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="a521f-130">또는 관리 센터에서 청구 **구독으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a521f-130">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="a521f-131">화면에 프로비전된 모든 라이선스 및 해당 현재 상태가 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a521f-131">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![청구 라이선스 이미지](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a><span data-ttu-id="a521f-133">클라우드 서비스 공급자 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a521f-133">Cloud Service Provider validation</span></span>

<span data-ttu-id="a521f-134">회사에 프로비전된 라이선스에 액세스하고 라이선스 상태를 확인하려면 관리 센터로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="a521f-134">To gain access into which licenses are provisioned to your company, and to check the state of the licenses, go to the admin center.</span></span>

1. <span data-ttu-id="a521f-135">파트너 **포털에서** 서비스 관리 **를 > Office 365.**</span><span class="sxs-lookup"><span data-stu-id="a521f-135">From the **Partner portal**, select **Administer services > Office 365**.</span></span>

2. <span data-ttu-id="a521f-136">파트너 포털 **링크를** 클릭하면 관리자  대신 관리 옵션이 열리며 고객 관리 센터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-136">Clicking on the **Partner portal** link will open the **Admin on behalf** option and will give you access to the customer admin center.</span></span>

   ![O365 관리 포털의 이미지](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a><span data-ttu-id="a521f-138">테넌트 구성</span><span class="sxs-lookup"><span data-stu-id="a521f-138">Tenant Configuration</span></span>
<span data-ttu-id="a521f-139">끝점용 Microsoft Defender에 쉽게 온보딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-139">Onboarding to Microsoft Defender for Endpoint is easy.</span></span> <span data-ttu-id="a521f-140">탐색 메뉴에서 끝점 섹션 아래에 있는 항목을 선택하거나 인시던트, 헌팅Microsoft 365 센터 또는 위협 분석과 같은 Microsoft 365 Defender 기능을 선택하여 온보딩 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-140">From the navigation menu, select any item under the Endpoints section, or any Microsoft 365 Defender feature such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span>

<span data-ttu-id="a521f-141">웹 브라우저에서 보안 센터 [Microsoft 365 이동합니다.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a521f-141">From a web browser, navigate to the [Microsoft 365 Security Center](https://security.microsoft.com).</span></span>

## <a name="network-configuration"></a><span data-ttu-id="a521f-142">네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="a521f-142">Network configuration</span></span>
<span data-ttu-id="a521f-143">조직에서 끝점이 인터넷에 액세스하기 위해 프록시를 사용할 필요가 없는 경우 이 섹션을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-143">If the organization doesn't require the endpoints to use a Proxy to access the Internet, skip this section.</span></span>

<span data-ttu-id="a521f-144">엔드포인트용 Microsoft Defender 센서를 사용하려면 센서 데이터를 보고하고 엔드포인트용 Microsoft Defender 서비스와 통신하기 위해 WinHTTP(Microsoft Windows HTTP)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="a521f-145">포함된 Microsoft Defender for Endpoint 센서는 LocalSystem 계정을 사용하여 시스템 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-145">The embedded Microsoft Defender for Endpoint sensor runs in the system context using the LocalSystem account.</span></span> <span data-ttu-id="a521f-146">센서는 WinHTTP(Microsoft Defender HTTP Services)를 사용하여 엔드포인트용 Microsoft Defender 클라우드 서비스와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-146">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Microsoft Defender for Endpoint cloud service.</span></span> <span data-ttu-id="a521f-147">WinHTTP 구성 설정은 WinINet(Windows Internet) 인터넷 검색 프록시 설정과는 독립적이며 다음 검색 방법을 사용하여 프록시 서버를 검색할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-147">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

<span data-ttu-id="a521f-148">**Autodiscovery 메서드:**</span><span class="sxs-lookup"><span data-stu-id="a521f-148">**Autodiscovery methods:**</span></span>

-   <span data-ttu-id="a521f-149">투명한 프록시</span><span class="sxs-lookup"><span data-stu-id="a521f-149">Transparent proxy</span></span>

-   <span data-ttu-id="a521f-150">WPAD(웹 프록시 자동 검색 프로토콜)</span><span class="sxs-lookup"><span data-stu-id="a521f-150">Web Proxy Autodiscovery Protocol (WPAD)</span></span>

<span data-ttu-id="a521f-151">네트워크 토폴로지에서 투명 프록시 또는 WPAD를 구현한 경우 특수 구성 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-151">If a Transparent proxy or WPAD has been implemented in the network topology, there is no need for special configuration settings.</span></span> <span data-ttu-id="a521f-152">프록시의 끝점 URL 제외에 대한 Microsoft Defender에 대한 자세한 [](production-deployment.md#proxy-service-urls) 내용은 URL 허용 목록 또는 장치 프록시 및 인터넷 연결 설정 구성에서 이 문서의 프록시 서비스 URL 섹션을 [참조하세요.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="a521f-152">For more information on Microsoft Defender for Endpoint URL exclusions in the proxy, see the [Proxy Service URLs](production-deployment.md#proxy-service-urls) section in this document for the URLs allow list or on [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="a521f-153">**수동 정적 프록시 구성:**</span><span class="sxs-lookup"><span data-stu-id="a521f-153">**Manual static proxy configuration:**</span></span>

-   <span data-ttu-id="a521f-154">레지스트리 기반 구성</span><span class="sxs-lookup"><span data-stu-id="a521f-154">Registry-based configuration</span></span>

-   <span data-ttu-id="a521f-155">netsh 명령을 사용하여 구성된 WinHTTP</span><span class="sxs-lookup"><span data-stu-id="a521f-155">WinHTTP configured using netsh command</span></span> <br> <span data-ttu-id="a521f-156">안정적인 토폴로지의 데스크톱에만 적합(예: 같은 프록시 뒤에 있는 회사 네트워크의 데스크톱)</span><span class="sxs-lookup"><span data-stu-id="a521f-156">Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="a521f-157">레지스트리 기반 정적 프록시를 사용하여 프록시 서버를 수동으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-157">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="a521f-158">컴퓨터가 인터넷에 연결할 수 없는 경우 Endpoint용 Microsoft Defender 센서만 진단 데이터를 보고하고 끝점 서비스용 Microsoft Defender와 통신할 수 있도록 레지스트리 기반 정적 프록시를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-158">Configure a registry-based static proxy to allow only Microsoft Defender for Endpoint sensor to report diagnostic data and communicate with Microsoft Defender for Endpoint services if a computer isn't permitted to connect to the Internet.</span></span> <span data-ttu-id="a521f-159">정적 프록시는 GP(그룹 정책)를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-159">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="a521f-160">그룹 정책은 다음에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-160">The group policy can be found under:</span></span>

 - <span data-ttu-id="a521f-161">관리 템플릿 Windows 구성 요소 데이터 수집 및 Preview 빌드 연결된 사용자 환경 및 원격 분석 서비스에 대해 인증된 프록시 사용 \> \> \> 구성</span><span class="sxs-lookup"><span data-stu-id="a521f-161">Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
     - <span data-ttu-id="a521f-162">이 설정을 **사용으로 설정하고** 인증된 프록시 사용 안 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a521f-162">Set it to **Enabled** and select **Disable Authenticated Proxy usage**</span></span>

1. <span data-ttu-id="a521f-163">그룹 정책 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-163">Open the Group Policy Management Console.</span></span>
2. <span data-ttu-id="a521f-164">조직 관행에 따라 정책을 만들거나 기존 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-164">Create a policy or edit an existing policy based off the organizational practices.</span></span>
3. <span data-ttu-id="a521f-165">그룹 정책을 편집하고 관리 템플릿 Windows 데이터 수집 및 Preview 빌드 연결된 사용자 환경 및 원격 분석 서비스에 대해 인증된 프록시 사용 구성 으로 **\> \> \> 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a521f-165">Edit the Group Policy and navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span></span> 
    <span data-ttu-id="a521f-166">![그룹 정책 구성 이미지](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="a521f-166">![Image of Group Policy configuration](images/atp-gpo-proxy1.png)</span></span>

4. <span data-ttu-id="a521f-167">**사용하도록 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-167">Select **Enabled**.</span></span>
5. <span data-ttu-id="a521f-168">인증된 **프록시 사용 안 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a521f-168">Select **Disable Authenticated Proxy usage**.</span></span>
   
6. <span data-ttu-id="a521f-169">관리 템플릿 구성 요소 Windows 및 Preview 빌드 연결된 사용자 환경 및 원격 분석 구성으로 **\> \> \> 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a521f-169">Navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure connected user experiences and telemetry**.</span></span>
    <span data-ttu-id="a521f-170">![그룹 정책 구성 설정의 이미지](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="a521f-170">![Image of Group Policy configuration setting](images/atp-gpo-proxy2.png)</span></span>
7. <span data-ttu-id="a521f-171">**사용하도록 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-171">Select **Enabled**.</span></span>
8. <span data-ttu-id="a521f-172">프록시 서버 **이름을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="a521f-172">Enter the **Proxy Server Name**.</span></span>

<span data-ttu-id="a521f-173">정책은 레지스트리 키 `HKLM\Software\Policies\Microsoft\Windows\DataCollection`에서 레지스트리 값 `TelemetryProxyServer`을(를) REG_SZ로, `DisableEnterpriseAuthProxy`을(를) REG_DWORD로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-173">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="a521f-174">레지스트리 값은 `TelemetryProxyServer` 다음 문자열 형식을 가합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-174">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

```text
<server name or ip>:<port>
```

<span data-ttu-id="a521f-175">예: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="a521f-175">For example: 10.0.0.6:8080</span></span>

<span data-ttu-id="a521f-176">레지스트리 값 `DisableEnterpriseAuthProxy`을(를) 1로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-176">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="a521f-177">netsh 명령을 사용하여 수동으로 프록시 서버 구성</span><span class="sxs-lookup"><span data-stu-id="a521f-177">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="a521f-178">netsh를 사용하여 시스템 전체의 정적 프록시를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-178">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="a521f-179">이는 Windows 서비스를 포함하여 기본 프록시로 WinHTTP를 사용하는 모든 응용 프로그램에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-179">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="a521f-180">토폴로지(예: 사무실에서 집으로)를 변경하는 랩톱이 netsh로 오작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-180">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="a521f-181">레지스트리 기반 정적 프록시 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-181">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="a521f-182">승격된 명령줄을 열기:</span><span class="sxs-lookup"><span data-stu-id="a521f-182">Open an elevated command line:</span></span>

    1. <span data-ttu-id="a521f-183">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="a521f-183">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="a521f-184">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="a521f-185">다음 명령을 입력하고 **Enter** 를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-185">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="a521f-186">예: netsh winhttp 설정 프록시 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="a521f-186">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>


###  <a name="proxy-configuration-for-down-level-devices"></a><span data-ttu-id="a521f-187">다운 수준 장치에 대한 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="a521f-187">Proxy Configuration for down-level devices</span></span>

<span data-ttu-id="a521f-188">Down-Level 장치에는 Windows 7 SP1 및 Windows 8.1 Workstation과 Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 및 Windows Server 2016 Windows Server CB 1803 이전의 Windows Server 2016 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-188">Down-Level devices include Windows 7 SP1 and Windows 8.1 workstations as well as Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and versions of Windows Server 2016 prior to Windows Server CB 1803.</span></span> <span data-ttu-id="a521f-189">이러한 운영 체제는 끝점에서 Azure로의 통신을 처리하도록 Microsoft 관리 에이전트의 일부로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-189">These operating systems will have the proxy configured as part of the Microsoft Management Agent to handle communication from the endpoint to Azure.</span></span> <span data-ttu-id="a521f-190">이러한 장치에서 프록시를 구성하는 방법에 대한 자세한 내용은 Microsoft Management Agent Fast Deployment Guide를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a521f-190">Refer to the Microsoft Management Agent Fast Deployment Guide for information on how a proxy is configured on these devices.</span></span>

### <a name="proxy-service-urls"></a><span data-ttu-id="a521f-191">프록시 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="a521f-191">Proxy Service URLs</span></span>
<span data-ttu-id="a521f-192">v20이 포함된 URL은 버전 1803 이상을 Windows 10 있는 경우 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-192">URLs that include v20 in them are only needed if you have Windows 10, version 1803 or later devices.</span></span> <span data-ttu-id="a521f-193">예를 들어 디바이스가 버전 1803 이상에 있는 Windows 10만 ```us-v20.events.data.microsoft.com``` 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-193">For example, ```us-v20.events.data.microsoft.com``` is only needed if the device is on Windows 10, version 1803 or later.</span></span>
 

<span data-ttu-id="a521f-194">프록시 또는 방화벽이 익명 트래픽을 차단하는 경우, Endpoint용 Microsoft Defender 센서가 시스템 컨텍스트에서 연결하고 있는 경우 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="a521f-194">If a proxy or firewall is blocking anonymous traffic, as Microsoft Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the listed URLs.</span></span>

<span data-ttu-id="a521f-195">다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-195">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="a521f-196">이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인하거나  해당 URL에 대한 허용 규칙을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-196">Ensure there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="a521f-197">**도메인 목록의 스프레드시트**</span><span class="sxs-lookup"><span data-stu-id="a521f-197">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="a521f-198">**설명**</span><span class="sxs-lookup"><span data-stu-id="a521f-198">**Description**</span></span>|
|:-----|:-----|
|![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지](images/mdatp-urls.png)<br/>  | <span data-ttu-id="a521f-200">서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-200">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="a521f-201">여기에서 스프레드시트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-201">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a><span data-ttu-id="a521f-202">Microsoft Defender for Endpoint Service 백 엔드 IP 범위</span><span class="sxs-lookup"><span data-stu-id="a521f-202">Microsoft Defender for Endpoint service backend IP ranges</span></span>

<span data-ttu-id="a521f-203">네트워크 장치가 DNS 기반 규칙을 지원하지 않는 경우 대신 IP 범위를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-203">If your network devices don't support DNS-based rules, use IP ranges instead.</span></span>

<span data-ttu-id="a521f-204">Endpoint용 Defender는 Azure 클라우드에서 구축되어 다음 지역에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-204">Defender for Endpoint is built in Azure cloud, deployed in the following regions:</span></span>

- <span data-ttu-id="a521f-205">AzureCloud.eastus</span><span class="sxs-lookup"><span data-stu-id="a521f-205">AzureCloud.eastus</span></span>
- <span data-ttu-id="a521f-206">AzureCloud.eastus2</span><span class="sxs-lookup"><span data-stu-id="a521f-206">AzureCloud.eastus2</span></span>
- <span data-ttu-id="a521f-207">AzureCloud.westcentralus</span><span class="sxs-lookup"><span data-stu-id="a521f-207">AzureCloud.westcentralus</span></span>
- <span data-ttu-id="a521f-208">AzureCloud.northeurope</span><span class="sxs-lookup"><span data-stu-id="a521f-208">AzureCloud.northeurope</span></span>
- <span data-ttu-id="a521f-209">AzureCloud.westeurope</span><span class="sxs-lookup"><span data-stu-id="a521f-209">AzureCloud.westeurope</span></span>
- <span data-ttu-id="a521f-210">AzureCloud.uksouth</span><span class="sxs-lookup"><span data-stu-id="a521f-210">AzureCloud.uksouth</span></span>
- <span data-ttu-id="a521f-211">AzureCloud.ukwest</span><span class="sxs-lookup"><span data-stu-id="a521f-211">AzureCloud.ukwest</span></span>

<span data-ttu-id="a521f-212">Azure IP 범위 및 서비스 태그 – 공용 클라우드에서 [Azure IP 범위를 찾을 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=56519)</span><span class="sxs-lookup"><span data-stu-id="a521f-212">You can find the Azure IP ranges in [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).</span></span>

> [!NOTE]
> <span data-ttu-id="a521f-213">클라우드 기반 솔루션으로 IP 주소 범위는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-213">As a cloud-based solution, the IP address ranges can change.</span></span> <span data-ttu-id="a521f-214">DNS 기반 규칙으로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-214">It's recommended you move to DNS-based rules.</span></span>

> [!NOTE]
> <span data-ttu-id="a521f-215">미국 정부 고객인 경우 미국 정부용 끝점용 Defender 페이지에서 해당 [섹션을 참조하세요.](gov.md#service-backend-ip-ranges)</span><span class="sxs-lookup"><span data-stu-id="a521f-215">If you are a US Government customer, please see the corresponding section in the [Defender for Endpoint for US Government](gov.md#service-backend-ip-ranges) page.</span></span>

## <a name="next-step"></a><span data-ttu-id="a521f-216">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a521f-216">Next step</span></span>

<span data-ttu-id="a521f-217">![**3단계: 온보더**](images/onboard.png)</span><span class="sxs-lookup"><span data-stu-id="a521f-217">![**Phase 3: Onboard**](images/onboard.png)</span></span> <br><span data-ttu-id="a521f-218">[3단계: 끝점용](onboarding.md)Microsoft Defender 서비스가 센서 데이터를 얻을 수 있도록 장치에 서비스를 온보딩합니다.</span><span class="sxs-lookup"><span data-stu-id="a521f-218">[Phase 3: Onboard](onboarding.md): Onboard devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span></span> 
