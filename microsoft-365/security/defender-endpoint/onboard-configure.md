---
title: Microsoft Defender ATP 서비스에 장치 온보딩
description: Windows 10 장치, 서버, 비 Windows 장치를 온보드하고 검색 테스트를 실행하는 방법을 배워야 합니다.
keywords: 온보딩, 끝점 온보딩을 위한 Microsoft Defender, windows atp 온보딩, sccm, 그룹 정책, mdm, 로컬 스크립트, 검색 테스트
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1deb8a0e00785705937d4cf6de71a030d3d9c971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061141"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="4c82c-104">Microsoft Defender for Endpoint 서비스에 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="4c82c-104">Onboard devices to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4c82c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4c82c-105">**Applies to:**</span></span>
- [<span data-ttu-id="4c82c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4c82c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4c82c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c82c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="4c82c-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4c82c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4c82c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="4c82c-110">지원되는 디바이스를 온보딩하려면 Endpoint 포털의 온보딩 섹션으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-110">You'll need to go the onboarding section of the Defender for Endpoint portal to onboard any of the supported devices.</span></span> <span data-ttu-id="4c82c-111">장치에 따라 적절한 단계를 안내하고 장치에 적합한 관리 및 배포 도구 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-111">Depending on the device, you'll be guided with appropriate steps and provided management and deployment tool options suitable for the device.</span></span> 

<span data-ttu-id="4c82c-112">일반적으로 디바이스를 서비스에 온보드합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-112">In general, to onboard devices to the service:</span></span>

- <span data-ttu-id="4c82c-113">장치가 최소 요구 사항을 [충족하는지 확인](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="4c82c-113">Verify that the device fulfills the [minimum requirements](minimum-requirements.md)</span></span>
- <span data-ttu-id="4c82c-114">장치에 따라 끝점 포털용 Defender의 온보딩 섹션에 제공된 구성 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-114">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal</span></span>
- <span data-ttu-id="4c82c-115">장치에 적합한 관리 도구 및 배포 방법 사용</span><span class="sxs-lookup"><span data-stu-id="4c82c-115">Use the appropriate management tool and deployment method for your devices</span></span>
- <span data-ttu-id="4c82c-116">검색 테스트를 실행하여 장치가 제대로 온보드 및 서비스에 보고되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-116">Run a detection test to verify that the devices are properly onboarded and reporting to the service</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a><span data-ttu-id="4c82c-117">온보더링 도구 옵션</span><span class="sxs-lookup"><span data-stu-id="4c82c-117">Onboarding tool options</span></span>
<span data-ttu-id="4c82c-118">다음 표에는 온보드해야 하는 끝점에 따라 사용 가능한 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-118">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="4c82c-119">끝점</span><span class="sxs-lookup"><span data-stu-id="4c82c-119">Endpoint</span></span>     | <span data-ttu-id="4c82c-120">도구 옵션</span><span class="sxs-lookup"><span data-stu-id="4c82c-120">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="4c82c-121">**Windows**</span><span class="sxs-lookup"><span data-stu-id="4c82c-121">**Windows**</span></span>  |  [<span data-ttu-id="4c82c-122">로컬 스크립트(최대 10대의 장치)</span><span class="sxs-lookup"><span data-stu-id="4c82c-122">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="4c82c-123">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="4c82c-123">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="4c82c-124">Microsoft Endpoint Manager/ 모바일 장치 관리자</span><span class="sxs-lookup"><span data-stu-id="4c82c-124">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="4c82c-125">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4c82c-125">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="4c82c-126">VDI 스크립트</span><span class="sxs-lookup"><span data-stu-id="4c82c-126">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="4c82c-127">**macOS**</span><span class="sxs-lookup"><span data-stu-id="4c82c-127">**macOS**</span></span>    | [<span data-ttu-id="4c82c-128">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="4c82c-128">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="4c82c-129">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4c82c-129">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="4c82c-130">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="4c82c-130">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="4c82c-131">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="4c82c-131">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="4c82c-132">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="4c82c-132">**Linux Server**</span></span> | [<span data-ttu-id="4c82c-133">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="4c82c-133">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="4c82c-134">Puppet</span><span class="sxs-lookup"><span data-stu-id="4c82c-134">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="4c82c-135">Ansible</span><span class="sxs-lookup"><span data-stu-id="4c82c-135">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="4c82c-136">**iOS**</span><span class="sxs-lookup"><span data-stu-id="4c82c-136">**iOS**</span></span>      | [<span data-ttu-id="4c82c-137">앱 기반</span><span class="sxs-lookup"><span data-stu-id="4c82c-137">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="4c82c-138">**Android**</span><span class="sxs-lookup"><span data-stu-id="4c82c-138">**Android**</span></span>  | [<span data-ttu-id="4c82c-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4c82c-139">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




## <a name="in-this-section"></a><span data-ttu-id="4c82c-140">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="4c82c-140">In this section</span></span>
<span data-ttu-id="4c82c-141">항목</span><span class="sxs-lookup"><span data-stu-id="4c82c-141">Topic</span></span> | <span data-ttu-id="4c82c-142">설명</span><span class="sxs-lookup"><span data-stu-id="4c82c-142">Description</span></span>
:---|:---
[<span data-ttu-id="4c82c-143">이전 버전의 Windows 온보드</span><span class="sxs-lookup"><span data-stu-id="4c82c-143">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)| <span data-ttu-id="4c82c-144">끝점용 Defender에 Windows 7 및 Windows 8.1 장치를 온보딩합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-144">Onboard Windows 7 and Windows 8.1 devices to Defender for Endpoint.</span></span> 
[<span data-ttu-id="4c82c-145">Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="4c82c-145">Onboard Windows 10 devices</span></span>](configure-endpoints.md) | <span data-ttu-id="4c82c-146">디바이스를 끝점용 Defender 서비스에 보고하려면 장치를 온보딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-146">You'll need to onboard devices for it to report to the Defender for Endpoint service.</span></span> <span data-ttu-id="4c82c-147">엔터프라이즈에서 장치를 구성하는 데 사용할 수 있는 도구 및 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-147">Learn about the tools and methods you can use to configure devices in your enterprise.</span></span>
[<span data-ttu-id="4c82c-148">서버 온보드</span><span class="sxs-lookup"><span data-stu-id="4c82c-148">Onboard servers</span></span>](configure-server-endpoints.md) |  <span data-ttu-id="4c82c-149">Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server(SAC) 버전 1803 이상, Windows Server 2019 이상 및 Windows Server 2019 Core Edition을 Endpoint용 Defender에 온보딩합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span></span>
[<span data-ttu-id="4c82c-150">비 Windows 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="4c82c-150">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md) | <span data-ttu-id="4c82c-151">Endpoint용 Defender는 Windows가 아닌 플랫폼뿐만 아니라 Windows에 대한 중앙 집중식 보안 운영 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-151">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="4c82c-152">Microsoft Defender 보안 센터에서 지원되는 다양한 OS(운영 체제)에서 경고를 보고 조직의 네트워크를 보다 잘 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-152">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> <span data-ttu-id="4c82c-153">이 환경은 타사 보안 제품의 센서 데이터를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-153">This experience leverages on a third-party security products' sensor data.</span></span> 
[<span data-ttu-id="4c82c-154">새로 온보드된 장치에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="4c82c-154">Run a detection test on a newly onboarded device</span></span>](run-detection-test.md) | <span data-ttu-id="4c82c-155">새로 온보딩된 장치에서 스크립트를 실행하여 끝점용 Defender 서비스에 제대로 보고하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-155">Run a script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>
[<span data-ttu-id="4c82c-156">프록시 및 인터넷 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4c82c-156">Configure proxy and Internet settings</span></span>](configure-proxy-internet.md)| <span data-ttu-id="4c82c-157">프록시 및 인터넷 연결 설정을 구성하여 Endpoint 클라우드 서비스용 Defender와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-157">Enable communication with the Defender for Endpoint cloud service by configuring the proxy and Internet connectivity settings.</span></span>
[<span data-ttu-id="4c82c-158">온보더링 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4c82c-158">Troubleshoot onboarding issues</span></span>](troubleshoot-onboarding.md) | <span data-ttu-id="4c82c-159">온보더링 중에 발생할 수 있는 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-159">Learn about resolving issues that might arise during onboarding.</span></span>

><span data-ttu-id="4c82c-160">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4c82c-160">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4c82c-161">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4c82c-161">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
