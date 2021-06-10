---
title: 링에서 끝점용 Microsoft Defender 배포
description: 링에서 끝점용 Microsoft Defender를 배포하는 방법 학습
keywords: 배포, 링, 평가, 파일럿, 내부자 빠른, 내부자 저속, 설치, 온보드, 단계, 배포, 배포, 채택, 구성
search.product: eADQiWindows 10XVcnh
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5aeaa51e5ab8974c8ca26453534396dac14b5853
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297215"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="9a5df-104">링에서 끝점용 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="9a5df-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9a5df-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9a5df-105">**Applies to:**</span></span>
- [<span data-ttu-id="9a5df-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9a5df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9a5df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a5df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9a5df-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9a5df-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9a5df-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="9a5df-110">링 기반 배포 방법을 사용하여 끝점에 대한 Microsoft Defender 배포를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="9a5df-111">배포 링은 다음과 같은 시나리오에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="9a5df-112">새 배포</span><span class="sxs-lookup"><span data-stu-id="9a5df-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="9a5df-113">기존 배포</span><span class="sxs-lookup"><span data-stu-id="9a5df-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="9a5df-114">새 배포</span><span class="sxs-lookup"><span data-stu-id="9a5df-114">New deployments</span></span>

![배포 링의 이미지](images/deployment-rings.png)


<span data-ttu-id="9a5df-116">링 기반 접근 방식은 온보드할 끝점 집합을 식별하고 서비스를 더 큰 장치 집합에 배포하기 전에 특정 조건이 충족되는지 확인하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="9a5df-117">각 링에 대한 종료 조건을 정의하고 다음 링으로 이동하기 전에 해당 링이 충족되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="9a5df-118">링 기반 배포를 채택하면 서비스를 배포하는 동안 발생할 수 있는 잠재적인 문제를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="9a5df-119">특정 수의 장치를 먼저 파일럿하여 잠재적인 문제를 식별하고 발생할 수 있는 잠재적인 위험을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="9a5df-120">표 1에서는 사용할 수 있는 배포 링의 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="9a5df-121">**표 1**</span><span class="sxs-lookup"><span data-stu-id="9a5df-121">**Table 1**</span></span>

|<span data-ttu-id="9a5df-122">**배포 링**</span><span class="sxs-lookup"><span data-stu-id="9a5df-122">**Deployment ring**</span></span>|<span data-ttu-id="9a5df-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="9a5df-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="9a5df-124">평가</span><span class="sxs-lookup"><span data-stu-id="9a5df-124">Evaluate</span></span> | <span data-ttu-id="9a5df-125">링 1: 파일럿 테스트용 시스템 50개 식별</span><span class="sxs-lookup"><span data-stu-id="9a5df-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="9a5df-126">파일럿</span><span class="sxs-lookup"><span data-stu-id="9a5df-126">Pilot</span></span> | <span data-ttu-id="9a5df-127">링 2: 프로덕션 환경에서 다음 50-100개 끝점 식별</span><span class="sxs-lookup"><span data-stu-id="9a5df-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="9a5df-128">전체 배포</span><span class="sxs-lookup"><span data-stu-id="9a5df-128">Full deployment</span></span> | <span data-ttu-id="9a5df-129">링 3: 더 큰 증분으로 나머지 환경에 서비스 롤아웃</span><span class="sxs-lookup"><span data-stu-id="9a5df-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="9a5df-130">종료 조건</span><span class="sxs-lookup"><span data-stu-id="9a5df-130">Exit criteria</span></span>
<span data-ttu-id="9a5df-131">이러한 링에 대한 종료 조건의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="9a5df-132">장치 인벤토리 목록에 장치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="9a5df-133">알림이 대시보드에 표시</span><span class="sxs-lookup"><span data-stu-id="9a5df-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="9a5df-134">검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="9a5df-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="9a5df-135">디바이스에 대한 시뮬레이션된 공격 실행</span><span class="sxs-lookup"><span data-stu-id="9a5df-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="9a5df-136">평가</span><span class="sxs-lookup"><span data-stu-id="9a5df-136">Evaluate</span></span>
<span data-ttu-id="9a5df-137">환경에 있는 소수의 테스트 컴퓨터를 식별하여 서비스에 온보드합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="9a5df-138">이상적으로 이러한 컴퓨터는 끝점 50개 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="9a5df-139">파일럿</span><span class="sxs-lookup"><span data-stu-id="9a5df-139">Pilot</span></span>
<span data-ttu-id="9a5df-140">끝점용 Microsoft Defender는 서비스에 온보딩할 수 있는 다양한 끝점을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-140">Microsoft Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="9a5df-141">이 링에서 온보드할 여러 장치를 식별하고 정의한 종료 기준에 따라 다음 배포 링으로 진행하기로 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="9a5df-142">다음 표에는 지원되는 끝점과 장치를 서비스에 온보드하는 데 사용할 수 있는 해당 도구가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="9a5df-143">끝점</span><span class="sxs-lookup"><span data-stu-id="9a5df-143">Endpoint</span></span>     | <span data-ttu-id="9a5df-144">배포 도구</span><span class="sxs-lookup"><span data-stu-id="9a5df-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="9a5df-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9a5df-145">**Windows**</span></span>  |  [<span data-ttu-id="9a5df-146">로컬 스크립트(최대 10대의 장치)</span><span class="sxs-lookup"><span data-stu-id="9a5df-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="9a5df-147">참고: 프로덕션 환경에 10개 이상의 장치를 배포하려는 경우 그룹 정책 방법이나 아래에 나열된 다른 지원되는 도구를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="9a5df-148">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="9a5df-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="9a5df-149">Microsoft Endpoint Manager/ 모바일 장치 관리자</span><span class="sxs-lookup"><span data-stu-id="9a5df-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="9a5df-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9a5df-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="9a5df-151">VDI 스크립트</span><span class="sxs-lookup"><span data-stu-id="9a5df-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="9a5df-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="9a5df-152">**macOS**</span></span>    | [<span data-ttu-id="9a5df-153">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="9a5df-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="9a5df-154">Microsoft Endpoint Manager </span><span class="sxs-lookup"><span data-stu-id="9a5df-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="9a5df-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="9a5df-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="9a5df-156">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="9a5df-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="9a5df-157">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="9a5df-157">**Linux Server**</span></span> | [<span data-ttu-id="9a5df-158">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="9a5df-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="9a5df-159">Puppet</span><span class="sxs-lookup"><span data-stu-id="9a5df-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="9a5df-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="9a5df-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="9a5df-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="9a5df-161">**iOS**</span></span>      | [<span data-ttu-id="9a5df-162">앱 기반</span><span class="sxs-lookup"><span data-stu-id="9a5df-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="9a5df-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="9a5df-163">**Android**</span></span>  | [<span data-ttu-id="9a5df-164">Microsoft Endpoint Manager </span><span class="sxs-lookup"><span data-stu-id="9a5df-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="9a5df-165">전체 배포</span><span class="sxs-lookup"><span data-stu-id="9a5df-165">Full deployment</span></span>
<span data-ttu-id="9a5df-166">이 단계에서 배포 계획 자료를 [사용하여](deployment-strategy.md) 배포를 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="9a5df-167">다음 자료를 사용하여 조직에 가장 적합한 끝점 아키텍처용 Microsoft Defender를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-167">Use the following material to select the appropriate Microsoft Defender for Endpoint architecture that best suites your organization.</span></span>

|<span data-ttu-id="9a5df-168">**항목**</span><span class="sxs-lookup"><span data-stu-id="9a5df-168">**Item**</span></span>|<span data-ttu-id="9a5df-169">**설명**</span><span class="sxs-lookup"><span data-stu-id="9a5df-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a5df-170">[![Endpoint 배포 전략용 Microsoft Defender의 축소판 이미지](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="9a5df-170">[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="9a5df-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="9a5df-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="9a5df-172">건축 자료는 다음 아키텍처의 배포를 계획하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="9a5df-173">클라우드 네이티브</span><span class="sxs-lookup"><span data-stu-id="9a5df-173">Cloud-native</span></span> </li><li> <span data-ttu-id="9a5df-174">공동 관리</span><span class="sxs-lookup"><span data-stu-id="9a5df-174">Co-management</span></span> </li><li> <span data-ttu-id="9a5df-175">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="9a5df-175">On-premise</span></span></li><li><span data-ttu-id="9a5df-176">평가 및 로컬 온보딩</span><span class="sxs-lookup"><span data-stu-id="9a5df-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="9a5df-177">기존 배포</span><span class="sxs-lookup"><span data-stu-id="9a5df-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="9a5df-178">Windows 끝점</span><span class="sxs-lookup"><span data-stu-id="9a5df-178">Windows endpoints</span></span>
<span data-ttu-id="9a5df-179">Windows 및/Windows 서버의 경우 **SUVP(보안** 업데이트 유효성 검사 프로그램)를 사용하여 미리 테스트할 여러 컴퓨터를 선택합니다(화요일 패치 전).</span><span class="sxs-lookup"><span data-stu-id="9a5df-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="9a5df-180">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a5df-180">For more information, see:</span></span>
- [<span data-ttu-id="9a5df-181">보안 업데이트 유효성 검사 프로그램</span><span class="sxs-lookup"><span data-stu-id="9a5df-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="9a5df-182">소프트웨어 업데이트 유효성 검사 프로그램 및 Microsoft 맬웨어 보호 센터 설치 - TwC 대화형 타임라인 4부</span><span class="sxs-lookup"><span data-stu-id="9a5df-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="9a5df-183">비 Windows 끝점</span><span class="sxs-lookup"><span data-stu-id="9a5df-183">Non-Windows endpoints</span></span>
<span data-ttu-id="9a5df-184">macOS 및 Linux에서는 몇 가지 시스템을 사용하며 베타 채널에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-184">With macOS and Linux, you could take a couple of systems and run in the Beta channel.</span></span>

>[!NOTE]
><span data-ttu-id="9a5df-185">빌드를 현재 채널로 만들기 전에 호환성, 성능 및 안정성 문제를 찾을 수 있도록 하나 이상의 보안 관리자와 개발자 한 명 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the Current channel.</span></span>

<span data-ttu-id="9a5df-186">채널 선택에 따라 장치에 제공되는 업데이트의 유형과 빈도가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="9a5df-187">Beta의 장치는 업데이트 및 새 기능을 수신하는 첫 번째 장치로, 나중에 미리 보기 및 마지막으로 현재가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-187">Devices in Beta are the first ones to receive updates and new features, followed later by Preview and lastly by Current.</span></span>

![내부자 링의 이미지](images/insider-rings.png)

<span data-ttu-id="9a5df-189">새 기능을 미리 보고 초기 피드백을 제공하기 위해서는 엔터프라이즈에서 베타 또는 미리 보기를 사용하도록 일부 장치를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either Beta or Preview.</span></span>

>[!WARNING]
><span data-ttu-id="9a5df-190">초기 설치 후 채널을 전환하려면 제품을 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="9a5df-191">제품 채널을 전환하려면 기존 패키지를 제거하고 새 채널을 사용하도록 장치를 다시 구성하고 이 문서의 단계에 따라 새 위치에서 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5df-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
