---
title: Microsoft Defender ATP 서비스에 온보딩
description: 끝점을 Microsoft Defender ATP 서비스에 온보딩하는 방법 학습
keywords: ''
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
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56645553c43289995012d53d7caf879874e65c8a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186932"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="6aede-103">끝점용 Microsoft Defender 서비스에 온보딩</span><span class="sxs-lookup"><span data-stu-id="6aede-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6aede-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6aede-104">**Applies to:**</span></span>
- [<span data-ttu-id="6aede-105">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6aede-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6aede-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6aede-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6aede-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6aede-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6aede-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6aede-109">끝점용 Microsoft Defender 배포의 다양한 단계와 솔루션 내에서 기능을 구성하는 방법에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="6aede-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="6aede-110">끝점용 Defender 배포는 3단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="6aede-111">[![배포 단계 - 준비](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="6aede-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="6aede-112">1단계: 준비</span><span class="sxs-lookup"><span data-stu-id="6aede-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="6aede-113">[![배포 단계 - 설정](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="6aede-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="6aede-114">2단계: 설치</span><span class="sxs-lookup"><span data-stu-id="6aede-114">Phase 2: Setup</span></span>](production-deployment.md) | ![배포 단계 - 온보드](images/phase-diagrams/onboard.png)<br><span data-ttu-id="6aede-116">3단계: 온보더</span><span class="sxs-lookup"><span data-stu-id="6aede-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="6aede-117">*여기 있습니다!*</span><span class="sxs-lookup"><span data-stu-id="6aede-117">*You are here!*</span></span>|

<span data-ttu-id="6aede-118">현재 온보더링 단계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="6aede-119">끝점용 Defender를 배포하는 데 필요한 단계는 다음 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="6aede-120">1단계: 서비스에 끝점 온보드</span><span class="sxs-lookup"><span data-stu-id="6aede-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="6aede-121">2단계: 기능 구성</span><span class="sxs-lookup"><span data-stu-id="6aede-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="6aede-122">1단계: 지원되는 관리 도구를 사용하여 끝점 온보드</span><span class="sxs-lookup"><span data-stu-id="6aede-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="6aede-123">배포 [계획 항목에서는](deployment-strategy.md) 끝점용 Defender를 배포하는 데 필요한 일반적인 단계를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="6aede-124">이 비디오를 시청하여 온보더링 프로세스에 대한 간략한 개요를 알아보고 사용 가능한 도구 및 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="6aede-125">아키텍처를 식별한 후 사용할 배포 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="6aede-126">선택한 배포 도구는 끝점을 서비스에 온보드하는 방법에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="6aede-127">온보더링 도구 옵션</span><span class="sxs-lookup"><span data-stu-id="6aede-127">Onboarding tool options</span></span>

<span data-ttu-id="6aede-128">다음 표에는 온보드해야 하는 끝점에 따라 사용 가능한 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="6aede-129">끝점</span><span class="sxs-lookup"><span data-stu-id="6aede-129">Endpoint</span></span>     | <span data-ttu-id="6aede-130">도구 옵션</span><span class="sxs-lookup"><span data-stu-id="6aede-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="6aede-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="6aede-131">**Windows**</span></span>  |  [<span data-ttu-id="6aede-132">로컬 스크립트(최대 10대의 장치)</span><span class="sxs-lookup"><span data-stu-id="6aede-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="6aede-133">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="6aede-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="6aede-134">Microsoft Endpoint Manager/ 모바일 장치 관리자</span><span class="sxs-lookup"><span data-stu-id="6aede-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="6aede-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6aede-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="6aede-136">VDI 스크립트</span><span class="sxs-lookup"><span data-stu-id="6aede-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="6aede-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="6aede-137">**macOS**</span></span>    | [<span data-ttu-id="6aede-138">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="6aede-138">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="6aede-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="6aede-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="6aede-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="6aede-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="6aede-141">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="6aede-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="6aede-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="6aede-142">**Linux Server**</span></span> | [<span data-ttu-id="6aede-143">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="6aede-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="6aede-144">Puppet</span><span class="sxs-lookup"><span data-stu-id="6aede-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="6aede-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="6aede-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="6aede-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="6aede-146">**iOS**</span></span>      | [<span data-ttu-id="6aede-147">앱 기반</span><span class="sxs-lookup"><span data-stu-id="6aede-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="6aede-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="6aede-148">**Android**</span></span>  | [<span data-ttu-id="6aede-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="6aede-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="6aede-150">2단계: 기능 구성</span><span class="sxs-lookup"><span data-stu-id="6aede-150">Step 2: Configure capabilities</span></span>
<span data-ttu-id="6aede-151">끝점을 온보드한 후 끝점 감지 및 응답, 차세대 보호, 공격 표면 감소와 같은 다양한 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-151">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="6aede-152">배포 예</span><span class="sxs-lookup"><span data-stu-id="6aede-152">Example deployments</span></span>
<span data-ttu-id="6aede-153">이 배포 가이드에서는 두 배포 도구를 사용하여 끝점을 온보드하고 기능을 구성하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-153">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="6aede-154">예제 배포의 도구는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-154">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="6aede-155">Microsoft Endpoint Configuration Manager를 사용한 온보더링</span><span class="sxs-lookup"><span data-stu-id="6aede-155">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="6aede-156">Microsoft Endpoint Manager를 사용한 온보드</span><span class="sxs-lookup"><span data-stu-id="6aede-156">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="6aede-157">위에서 언급한 배포 도구를 사용하여 끝점에 대해 다음 Defender 기능을 구성하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="6aede-157">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="6aede-158">끝점 검색 및 응답 구성</span><span class="sxs-lookup"><span data-stu-id="6aede-158">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="6aede-159">차세대 보호 구성</span><span class="sxs-lookup"><span data-stu-id="6aede-159">Next-generation protection configuration</span></span>
- <span data-ttu-id="6aede-160">공격 표면 감소 구성</span><span class="sxs-lookup"><span data-stu-id="6aede-160">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="6aede-161">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6aede-161">Related topics</span></span>
- [<span data-ttu-id="6aede-162">Microsoft Endpoint Configuration Manager를 사용한 온보더링</span><span class="sxs-lookup"><span data-stu-id="6aede-162">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="6aede-163">Microsoft Endpoint Manager를 사용한 온보드</span><span class="sxs-lookup"><span data-stu-id="6aede-163">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
