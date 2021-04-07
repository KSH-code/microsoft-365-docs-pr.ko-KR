---
title: 네트워크 장치 검색 및 취약성 관리
description: 이제 스위치, 라우터, WLAN 컨트롤러 및 방화벽 운영 체제에서 보안 권장 사항 및 취약점 감지를 사용할 수 있습니다.
keywords: 네트워크 장치, 네트워크 장치 취약점 감지, 스위치 운영 체제, 라우터, WLAN 컨트롤러 및 방화벽
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06b52e937dd0260a50883c45c36389a6a955ad0e
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604535"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="85a2c-104">네트워크 장치 검색 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="85a2c-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="85a2c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="85a2c-105">**Applies to:**</span></span>

- <span data-ttu-id="85a2c-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="85a2c-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>
- [<span data-ttu-id="85a2c-107">위협 및 취약점 관리</span><span class="sxs-lookup"><span data-stu-id="85a2c-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="85a2c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85a2c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="85a2c-109">**네트워크 장치 검사 및 관리는 현재 공개 미리 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="85a2c-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="85a2c-110">이 미리 보기 버전은 서비스 수준 계약 없이 제공하며 프로덕션 워크로드에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="85a2c-111">일부 기능은 지원되지 않을 수도, 기능이 제한될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="85a2c-112">자세한 내용은 끝점 미리 보기 [기능용 Microsoft Defender를 참조하세요.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="85a2c-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="85a2c-113">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="85a2c-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="85a2c-114">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="85a2c-115">네트워크 검색 기능은 Microsoft  365 보안 센터 및 Microsoft Defender 보안 센터 콘솔의 장치 인벤토리 섹션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-115">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="85a2c-116">지정된 끝점 디바이스용 Microsoft Defender가 각 네트워크 세그먼트에서 미리 구성한 네트워크 장치에 대해 정기적으로 인증된 스캔을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-116">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="85a2c-117">검색된 끝점의 위협 및 취약성 관리 기능에 대한 Defender는 검색된 스위치, 라우터, WLAN 컨트롤러, 방화벽 및 VPN 게이트웨이를 보호하는 통합 워크플로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-117">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="85a2c-118">네트워크 장치가 검색 및 분류되면 보안 관리자는 최신 보안 권장 사항을 받고 조직 전체에 배포된 네트워크 장치에 대해 최근에 발견된 취약점을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-118">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities foron network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="85a2c-119">방법</span><span class="sxs-lookup"><span data-stu-id="85a2c-119">Approach</span></span>

<span data-ttu-id="85a2c-120">끝점용 Defender에는 네트워크 장치 자체에 내장된 센서가 아니기 때문에 네트워크 장치는 표준 끝점으로 관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-120">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="85a2c-121">이러한 유형의 디바이스에는 원격 검사가 장치에서 필요한 정보를 얻는 에이전트 없는 접근 방식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-121">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="85a2c-122">네트워크 토폴로지 및 특성에 따라 단일 장치 또는 끝점용 Microsoft Defender에 온보딩된 몇 대의 장치가 SNMP를 사용하여 인증된 네트워크 장치 검색을 수행하며 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-122">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="85a2c-123">유의해야 할 두 가지 유형의 장치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-123">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="85a2c-124">**평가 장치:** 네트워크 장치를 검색하는 데 사용할 이미 온보드된 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-124">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="85a2c-125">**네트워크 장치:** 스캔하고 온보드할 네트워크 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-125">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="85a2c-126">네트워크 장치에 대한 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="85a2c-126">Vulnerability management for network devices</span></span> 

<span data-ttu-id="85a2c-127">네트워크 장치가 검색 및 분류되면 보안 관리자는 최신 보안 권장 사항을 받고 조직 전체에 배포된 네트워크 장치에서 최근에 발견된 취약점을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-127">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="85a2c-128">지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="85a2c-128">Operating systems that are supported</span></span>

<span data-ttu-id="85a2c-129">다음 운영 체제가 현재 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-129">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="85a2c-130">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="85a2c-130">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="85a2c-131">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="85a2c-131">Juniper JUNOS</span></span>
- <span data-ttu-id="85a2c-132">HPE ArubaOS, Procurve 스위치 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="85a2c-132">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="85a2c-133">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="85a2c-133">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="85a2c-134">고객 사용에서 수집한 데이터를 기반으로 시간이 지날수록 더 많은 네트워킹 공급업체 및 OS가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-134">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="85a2c-135">따라서 이 목록에 지정되지 않은 경우에도 모든 네트워크 장치를 구성하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-135">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="85a2c-136">시작하는 방법</span><span class="sxs-lookup"><span data-stu-id="85a2c-136">How to get started</span></span>

<span data-ttu-id="85a2c-137">첫 번째 단계는 인증된 네트워크 검색을 수행할 장치를 선택하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-137">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="85a2c-138">검사할 네트워크 장치의 관리 포트에 대한 네트워크 연결이 있는 끝점 온보딩 장치(클라이언트 또는 서버)에 대한 Defender를 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="85a2c-138">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="85a2c-139">Endpoint용 Defender 평가 장치와 대상 네트워크 장치 간의 SNMP 트래픽(예: 방화벽)을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-139">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="85a2c-140">취약점에 대해 평가할 네트워크 장치(예: Cisco 스위치 또는 Palo Alto Networks 방화벽)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-140">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="85a2c-141">끝점 평가 장치가 구성된 네트워크 장치를 쿼리할 수 있도록 구성된 모든 네트워크 장치에서 SNMP 읽기 전용이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-141">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="85a2c-142">'SNMP 쓰기'는 이 기능의 적절한 기능에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-142">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="85a2c-143">검색할 네트워크 장치의 IP 주소(또는 이러한 장치가 배포된 서브넷)를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-143">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="85a2c-144">네트워크 장치의 SNMP 자격 증명(예: 커뮤니티 문자열, noAuthNoPriv, authNoPriv, authPriv)을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-144">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="85a2c-145">새 평가 작업을 구성할 때 자격 증명을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-145">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="85a2c-146">프록시 클라이언트 구성: Endpoint 장치 프록시 요구 사항에 대한 Defender 외의 추가 구성은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-146">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="85a2c-147">네트워크 스캐너를 인증하고 제대로 작동하도록 허용하려면 다음 도메인/URL을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-147">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="85a2c-148">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="85a2c-148">login.windows.net</span></span>  
    - <span data-ttu-id="85a2c-149">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="85a2c-149">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="85a2c-150">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="85a2c-150">login.microsoftonline.com</span></span>
    - <span data-ttu-id="85a2c-151">*.blob.core.windows.net/networkscannerstable/*</span><span class="sxs-lookup"><span data-stu-id="85a2c-151">*.blob.core.windows.net/networkscannerstable/*</span></span>

    <span data-ttu-id="85a2c-152">참고: 이러한 URL은 허용되는 데이터 수집의 끝점에 대해 문서화된 Defender 목록에 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-152">Note: These URLs are not specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="85a2c-153">사용 권한</span><span class="sxs-lookup"><span data-stu-id="85a2c-153">Permissions</span></span>

<span data-ttu-id="85a2c-154">평가 작업을 구성하려면 보안 센터에서 보안 설정 관리와 같은 사용자 **권한 옵션이 필요합니다.**</span><span class="sxs-lookup"><span data-stu-id="85a2c-154">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="85a2c-155">설정 역할로 이동하여 권한을  >  **찾을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="85a2c-155">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="85a2c-156">자세한 내용은 역할 기반 액세스 제어에 대한 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="85a2c-156">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="85a2c-157">네트워크 스캐너 설치</span><span class="sxs-lookup"><span data-stu-id="85a2c-157">Install the network scanner</span></span>

1. <span data-ttu-id="85a2c-158">Microsoft **365 보안** 설정  >    >  **끝점**  >  **평가 작업('네트워크** 평가' 아래)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-158">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under 'Network assessments').</span></span>
    1. <span data-ttu-id="85a2c-159">Microsoft Defender 보안 센터에서 설정 > 작업 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-159">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="85a2c-160">네트워크 스캐너를 다운로드하여 지정된 Endpoint 평가 장치에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-160">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

![스캐너 단추 다운로드](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="85a2c-162">네트워크 스캐너 설치 & 등록</span><span class="sxs-lookup"><span data-stu-id="85a2c-162">Network scanner installation & registration</span></span>

<span data-ttu-id="85a2c-163">로그인 프로세스는 지정된 평가 장치 자체 또는 다른 장치(예: 개인 클라이언트 장치)에서 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-163">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="85a2c-164">네트워크 스캐너 등록 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-164">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="85a2c-165">명령줄에 나타나는 URL을 복사하고 따르고 제공된 설치 코드를 사용하여 등록 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-165">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>
    - <span data-ttu-id="85a2c-166">참고: URL을 복사할 수 있게 명령 프롬프트 설정을 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-166">Note: You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="85a2c-167">코드를 입력하고 "보안 센터에서 보안 설정 관리"라는 끝점용 Defender 권한이 있는 Microsoft 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-167">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="85a2c-168">완료되면 로그인을 확인한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-168">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="85a2c-169">새 평가 작업 구성</span><span class="sxs-lookup"><span data-stu-id="85a2c-169">Configure a new assessment job</span></span>  

<span data-ttu-id="85a2c-170">설정의 평가 작업 페이지에서 **네트워크** 평가 작업 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="85a2c-170">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="85a2c-171">설정 프로세스에 따라 정기적으로 검사하고 장치 인벤토리에 추가할 네트워크 장치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="85a2c-171">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="85a2c-172">네트워크 장치 인벤토리에서 장치 중복을 방지하려면 각 IP 주소가 여러 평가 장치에서 한 번만 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-172">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

![네트워크 평가 작업 단추 추가](images/assessment-jobs-add.png)

<span data-ttu-id="85a2c-174">네트워크 평가 작업 단계 추가:</span><span class="sxs-lookup"><span data-stu-id="85a2c-174">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="85a2c-175">네트워크 스캐너가 설치된 '평가 작업' 이름 및 '평가 장치'를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="85a2c-175">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="85a2c-176">이 장치는 주기적인 인증된 스캔을 수행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-176">This device will perform the periodic authenticated scans.</span></span> 
2. <span data-ttu-id="85a2c-177">검사할 대상 네트워크 장치의 IP 주소(또는 이러한 장치가 배포된 서브넷)를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-177">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 
3. <span data-ttu-id="85a2c-178">대상 네트워크 장치의 필수 SNMP 자격 증명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-178">Add required SNMP credentials of the target network devices.</span></span> 
4. <span data-ttu-id="85a2c-179">새로 구성된 네트워크 평가 작업을 저장하여 주기적인 네트워크 검색을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-179">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="85a2c-180">네트워크 장치 검색 및 추가</span><span class="sxs-lookup"><span data-stu-id="85a2c-180">Scan and add network devices</span></span>

<span data-ttu-id="85a2c-181">설정 프로세스 중에 한 번의 테스트 검색을 수행하여 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-181">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="85a2c-182">Endpoint용 Defender 평가 장치와 구성된 대상 네트워크 장치 간에 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-182">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="85a2c-183">구성된 SNMP 자격 증명이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-183">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="85a2c-184">각 평가 장치는 최대 1,500회의 성공적인 IP 주소 검색을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-184">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="85a2c-185">예를 들어 IP 주소가 100개만 성공한 결과를 반환하는 10개 다른 서브넷을 검색하는 경우 동일한 평가 장치에 있는 다른 서브넷에서 1,400개 IP 추가 주소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-185">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="85a2c-186">검색할 IP 주소 범위/서브넷이 여러 개 있는 경우 테스트 검사 결과를 표시하는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-186">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="85a2c-187">테스트 검사는 최대 1,024개 주소에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-187">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="85a2c-188">결과가 표시될 때 주기적 검사에 포함될 장치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-188">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="85a2c-189">검사 결과 보기를 건너뛰면 구성된 모든 IP 주소가 장치의 응답에 관계없이 네트워크 평가 작업으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-189">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="85a2c-190">검색 결과를 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-190">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="85a2c-191">장치 인벤토리</span><span class="sxs-lookup"><span data-stu-id="85a2c-191">Device inventory</span></span>

<span data-ttu-id="85a2c-192">새로 검색된 장치는 장치 인벤토리 페이지의 새 **네트워크** 장치 **탭에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-192">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="85a2c-193">장치가 업데이트될 때까지 평가 작업을 추가한 후 최대 2시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-193">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

![장치 인벤토리의 네트워크 장치 섹션](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a><span data-ttu-id="85a2c-195">문제 해결</span><span class="sxs-lookup"><span data-stu-id="85a2c-195">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="85a2c-196">네트워크 스캐너 설치 실패</span><span class="sxs-lookup"><span data-stu-id="85a2c-196">Network scanner installation has failed</span></span>

<span data-ttu-id="85a2c-197">필요한 URL이 방화벽 설정의 허용 도메인에 추가되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-197">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="85a2c-198">또한 장치 프록시 및 인터넷 연결 설정 구성에 설명된 바와 같이 프록시 [설정이 구성되어 있는지 확인합니다.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="85a2c-198">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="85a2c-199">Microsoft.com/devicelogin 웹 페이지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-199">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="85a2c-200">필요한 URL이 방화벽의 허용 도메인에 추가되는지 확인</span><span class="sxs-lookup"><span data-stu-id="85a2c-200">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="85a2c-201">또한 프록시 설정이 장치 프록시 및 인터넷 연결 설정 구성에 설명된 [바와 같이 구성되어 있는지 확인합니다.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="85a2c-201">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="85a2c-202">네트워크 장치가 몇 시간 후에 장치 인벤토리에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-202">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="85a2c-203">검사 결과는 평가 작업 구성을 완료한 후 수행된 초기 검사 후 몇 시간 후에 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-203">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="85a2c-204">장치가 아직 표시되어 있지 않은 경우 네트워크 스캐너를 설치한 평가 장치에서 'MdatpNetworkScanService' 서비스가 실행되고 있는지 확인하고 관련 평가 작업 구성에서 "검사 실행"을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="85a2c-204">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="85a2c-205">5분 후에도 여전히 결과를 얻지 못하면 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-205">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="85a2c-206">마지막으로 본 디바이스가 24시간보다 길습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-206">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="85a2c-207">스캐너가 제대로 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-207">Validate that the scanner is running properly.</span></span> <span data-ttu-id="85a2c-208">그런 다음 검사 정의로 이동하여 "테스트 실행"을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-208">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="85a2c-209">관련 IP 주소에서 반환되는 오류 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-209">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="85a2c-210">필수 위협 및 취약성 관리 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="85a2c-210">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="85a2c-211">등록이 완료되고 "새 에이전트를 추가할 수 있는 권한이 없는 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-211">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="85a2c-212">필요한 사용 권한은 '보안 센터에서 보안 설정 관리'입니다."</span><span class="sxs-lookup"><span data-stu-id="85a2c-212">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="85a2c-213">아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-213">Press any key to exit.</span></span>

<span data-ttu-id="85a2c-214">시스템 관리자에게 필요한 사용 권한을 할당해달고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-214">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="85a2c-215">또는 다른 관련 구성원에게 로그인 코드 및 링크를 제공하여 로그인 프로세스에 도움을 줄 수 있도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-215">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="85a2c-216">등록 프로세스에서 명령줄에 제공된 링크를 사용하여 등록 프로세스가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-216">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="85a2c-217">다른 브라우저를 사용해 보거나 로그인 링크 및 코드를 다른 장치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-217">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="85a2c-218">텍스트가 너무 작거나 명령줄에서 텍스트를 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-218">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="85a2c-219">복사 및 텍스트 크기를 변경할 수 있도록 장치의 명령줄 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85a2c-219">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="85a2c-220">관련 문서</span><span class="sxs-lookup"><span data-stu-id="85a2c-220">Related articles</span></span>

- [<span data-ttu-id="85a2c-221">장치 인벤토리</span><span class="sxs-lookup"><span data-stu-id="85a2c-221">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="85a2c-222">고급 기능 구성</span><span class="sxs-lookup"><span data-stu-id="85a2c-222">Configure advanced features</span></span>](advanced-features.md)
