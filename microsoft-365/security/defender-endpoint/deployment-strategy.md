---
title: 끝점용 Microsoft Defender 배포 계획
description: 환경에 가장 적합한 엔드포인트 배포 전략에 대한 Microsoft Defender 선택
keywords: 배포, 계획, 배포 전략, 클라우드 네이티브, 관리, 온-프레미스, 평가, 온보드, 로컬, 그룹 정책, gp, 끝점 관리자, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163578"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="d2e2c-104">끝점용 Microsoft Defender 배포 계획</span><span class="sxs-lookup"><span data-stu-id="d2e2c-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d2e2c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d2e2c-105">**Applies to:**</span></span>
- [<span data-ttu-id="d2e2c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d2e2c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d2e2c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2e2c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d2e2c-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d2e2c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d2e2c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="d2e2c-110">제품군 내에서 보안 기능을 최대화하고 사이버 위협으로부터 엔터프라이즈를 보다 잘 보호할 수 있도록 끝점 배포에 대한 Microsoft Defender 배포를 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="d2e2c-111">이 솔루션은 환경 아키텍처를 식별하는 방법, 요구에 가장 적합한 배포 도구 유형 선택 및 기능 구성 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![배포 흐름의 이미지](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="d2e2c-113">1단계: 아키텍처 식별</span><span class="sxs-lookup"><span data-stu-id="d2e2c-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="d2e2c-114">모든 엔터프라이즈 환경이 고유하다는 것을 알고 있으므로 서비스 배포 방법을 선택할 때 유연성을 제공하는 몇 가지 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="d2e2c-115">환경에 따라 일부 도구는 특정 아키텍처에 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="d2e2c-116">다음 자료를 사용하여 조직에 가장 적합한 끝점 아키텍처에 적합한 Defender를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="d2e2c-117">항목</span><span class="sxs-lookup"><span data-stu-id="d2e2c-117">Item</span></span> | <span data-ttu-id="d2e2c-118">설명</span><span class="sxs-lookup"><span data-stu-id="d2e2c-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="d2e2c-119">[![Endpoint 배포 전략용 Defender의 축소판 이미지](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="d2e2c-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="d2e2c-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="d2e2c-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="d2e2c-121">건축 자료는 다음 아키텍처의 배포를 계획하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="d2e2c-122">클라우드 네이티브</span><span class="sxs-lookup"><span data-stu-id="d2e2c-122">Cloud-native</span></span> </li><li> <span data-ttu-id="d2e2c-123">공동 관리</span><span class="sxs-lookup"><span data-stu-id="d2e2c-123">Co-management</span></span> </li><li> <span data-ttu-id="d2e2c-124">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="d2e2c-124">On-premise</span></span></li><li><span data-ttu-id="d2e2c-125">평가 및 로컬 온보딩</span><span class="sxs-lookup"><span data-stu-id="d2e2c-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="d2e2c-126">2단계: 배포 방법 선택</span><span class="sxs-lookup"><span data-stu-id="d2e2c-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="d2e2c-127">Endpoint용 Defender는 서비스에 온보딩할 수 있는 다양한 끝점을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="d2e2c-128">다음 표에는 배포를 적절하게 계획할 수 있도록 지원되는 끝점 및 해당 배포 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="d2e2c-129">끝점</span><span class="sxs-lookup"><span data-stu-id="d2e2c-129">Endpoint</span></span>     | <span data-ttu-id="d2e2c-130">배포 도구</span><span class="sxs-lookup"><span data-stu-id="d2e2c-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="d2e2c-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d2e2c-131">**Windows**</span></span>  |  [<span data-ttu-id="d2e2c-132">로컬 스크립트(최대 10대의 장치)</span><span class="sxs-lookup"><span data-stu-id="d2e2c-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="d2e2c-133">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="d2e2c-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="d2e2c-134">Microsoft Endpoint Manager/ 모바일 장치 관리자</span><span class="sxs-lookup"><span data-stu-id="d2e2c-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="d2e2c-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d2e2c-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="d2e2c-136">VDI 스크립트</span><span class="sxs-lookup"><span data-stu-id="d2e2c-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="d2e2c-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="d2e2c-137">**macOS**</span></span>    | [<span data-ttu-id="d2e2c-138">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="d2e2c-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="d2e2c-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d2e2c-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="d2e2c-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="d2e2c-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="d2e2c-141">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="d2e2c-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="d2e2c-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="d2e2c-142">**Linux Server**</span></span> | [<span data-ttu-id="d2e2c-143">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="d2e2c-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="d2e2c-144">Puppet</span><span class="sxs-lookup"><span data-stu-id="d2e2c-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="d2e2c-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="d2e2c-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="d2e2c-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="d2e2c-146">**iOS**</span></span>      | [<span data-ttu-id="d2e2c-147">앱 기반</span><span class="sxs-lookup"><span data-stu-id="d2e2c-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="d2e2c-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="d2e2c-148">**Android**</span></span>  | [<span data-ttu-id="d2e2c-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d2e2c-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="d2e2c-150">3단계: 기능 구성</span><span class="sxs-lookup"><span data-stu-id="d2e2c-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="d2e2c-151">끝점을 온보딩한 후 제품군에서 사용할 수 있는 강력한 보안 보호를 최대화할 수 있도록 끝점용 Defender의 보안 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="d2e2c-152">기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2e2c-152">Capabilities include:</span></span>

- <span data-ttu-id="d2e2c-153">끝점 감지 및 대응</span><span class="sxs-lookup"><span data-stu-id="d2e2c-153">Endpoint detection and response</span></span>
- <span data-ttu-id="d2e2c-154">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="d2e2c-154">Next-generation protection</span></span>
- <span data-ttu-id="d2e2c-155">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="d2e2c-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="d2e2c-156">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d2e2c-156">Related topics</span></span>
- [<span data-ttu-id="d2e2c-157">배포 단계</span><span class="sxs-lookup"><span data-stu-id="d2e2c-157">Deployment phases</span></span>](deployment-phases.md)
