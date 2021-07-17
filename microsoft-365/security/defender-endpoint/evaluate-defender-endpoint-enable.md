---
title: Endpoint 평가용 파일럿 Defender
description: 평가판 Microsoft 365 Defender 또는 파일럿 환경을 사용하도록 설정
keywords: Microsoft 365 Defender 평가, Microsoft 365 Defender 평가, Microsoft 365 Defender Microsoft 365 Defender 평가 랩, Microsoft 365 Defender 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458186"
---
# <a name="pilot-mde-evaluation"></a><span data-ttu-id="93092-104">파일럿 MDE 평가</span><span class="sxs-lookup"><span data-stu-id="93092-104">Pilot MDE Evaluation</span></span>

>[!NOTE]
><span data-ttu-id="93092-105">일반적인 배포를 안내하기 위해 이 시나리오는 일반적인 배포를 안내하는 용도로만 Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="93092-105">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="93092-106">Endpoint용 Defender는 다른 온보딩 도구를 사용할 수 있지만 배포 가이드에서 이러한 시나리오를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93092-106">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="93092-107">자세한 내용은 [끝점용 Microsoft Defender에 장치 온보딩을 참조하세요.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="93092-107">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="step-1-check-license-state"></a><span data-ttu-id="93092-108">1단계.</span><span class="sxs-lookup"><span data-stu-id="93092-108">Step 1.</span></span> <span data-ttu-id="93092-109">라이선스 상태 확인</span><span class="sxs-lookup"><span data-stu-id="93092-109">Check license state</span></span>

<span data-ttu-id="93092-110">라이선스 상태를 확인하고 적절히 프로비전되었는지 여부는 관리 센터 또는 라이선스 **포털을 통해** Microsoft Azure 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93092-110">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="93092-111">라이선스를 확인하기 위해 Microsoft Azure **포털로** 이동하여 Microsoft Azure 포털 라이선스 섹션으로 [이동합니다.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="93092-111">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 라이선스 페이지의 이미지](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="93092-113">또는 관리 센터에서 청구 **구독으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="93092-113">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="93092-114">화면에 프로비전된 모든 라이선스 및 해당 현재 상태가 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="93092-114">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![청구 라이선스 이미지](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="93092-116">2단계.</span><span class="sxs-lookup"><span data-stu-id="93092-116">Step 2.</span></span> <span data-ttu-id="93092-117">지원되는 관리 도구를 사용하여 끝점 온보드</span><span class="sxs-lookup"><span data-stu-id="93092-117">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="93092-118">배포 [계획 항목에서는](deployment-strategy.md) 끝점용 Defender를 배포하는 데 필요한 일반적인 단계를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93092-118">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="93092-119">이 비디오를 시청하여 온보더링 프로세스에 대한 간략한 개요를 알아보고 사용 가능한 도구 및 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="93092-119">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

<span data-ttu-id="93092-120">아키텍처를 식별한 후 사용할 배포 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93092-120">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="93092-121">선택한 배포 도구는 끝점을 서비스에 온보드하는 방법에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93092-121">The deployment tool you choose influences how you onboard endpoints to the service.</span></span>

### <a name="onboarding-tool-options"></a><span data-ttu-id="93092-122">온보더링 도구 옵션</span><span class="sxs-lookup"><span data-stu-id="93092-122">Onboarding tool options</span></span>

<span data-ttu-id="93092-123">다음 표에는 온보드해야 하는 끝점에 따라 사용 가능한 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="93092-123">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="93092-124">끝점</span><span class="sxs-lookup"><span data-stu-id="93092-124">Endpoint</span></span>     | <span data-ttu-id="93092-125">도구 옵션</span><span class="sxs-lookup"><span data-stu-id="93092-125">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="93092-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="93092-126">**Windows**</span></span>  |  [<span data-ttu-id="93092-127">로컬 스크립트(최대 10대의 장치)</span><span class="sxs-lookup"><span data-stu-id="93092-127">Local script (up to 10 devices)</span></span>](../defender-endpoint/configure-endpoints-script.md) <br> [<span data-ttu-id="93092-128">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="93092-128">Group Policy</span></span>](../defender-endpoint/configure-endpoints-gp.md) <br> [<span data-ttu-id="93092-129">Microsoft Endpoint Manager/ 모바일 장치 관리자</span><span class="sxs-lookup"><span data-stu-id="93092-129">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](../defender-endpoint/configure-endpoints-mdm.md) <br> [<span data-ttu-id="93092-130">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="93092-130">Microsoft Endpoint Configuration Manager</span></span>](../defender-endpoint/configure-endpoints-sccm.md) <br> [<span data-ttu-id="93092-131">VDI 스크립트</span><span class="sxs-lookup"><span data-stu-id="93092-131">VDI scripts</span></span>](../defender-endpoint/configure-endpoints-vdi.md) <br> [<span data-ttu-id="93092-132">Azure Defender와 통합</span><span class="sxs-lookup"><span data-stu-id="93092-132">Integration with Azure Defender</span></span>](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="93092-133">**macOS**</span><span class="sxs-lookup"><span data-stu-id="93092-133">**macOS**</span></span>    | [<span data-ttu-id="93092-134">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="93092-134">Local scripts</span></span>](../defender-endpoint/mac-install-manually.md) <br> [<span data-ttu-id="93092-135">Microsoft Endpoint Manager </span><span class="sxs-lookup"><span data-stu-id="93092-135">Microsoft Endpoint Manager</span></span>](../defender-endpoint/mac-install-with-intune.md) <br> [<span data-ttu-id="93092-136">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="93092-136">JAMF Pro</span></span>](../defender-endpoint/mac-install-with-jamf.md) <br> [<span data-ttu-id="93092-137">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="93092-137">Mobile Device Management</span></span>](../defender-endpoint/mac-install-with-other-mdm.md) |
| <span data-ttu-id="93092-138">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="93092-138">**Linux Server**</span></span> | [<span data-ttu-id="93092-139">로컬 스크립트</span><span class="sxs-lookup"><span data-stu-id="93092-139">Local script</span></span>](../defender-endpoint/linux-install-manually.md) <br> [<span data-ttu-id="93092-140">Puppet</span><span class="sxs-lookup"><span data-stu-id="93092-140">Puppet</span></span>](../defender-endpoint/linux-install-with-puppet.md) <br> [<span data-ttu-id="93092-141">Ansible</span><span class="sxs-lookup"><span data-stu-id="93092-141">Ansible</span></span>](../defender-endpoint/linux-install-with-ansible.md)|
| <span data-ttu-id="93092-142">**iOS**</span><span class="sxs-lookup"><span data-stu-id="93092-142">**iOS**</span></span>      | [<span data-ttu-id="93092-143">앱 기반</span><span class="sxs-lookup"><span data-stu-id="93092-143">App-based</span></span>](../defender-endpoint/ios-install.md)                                |
| <span data-ttu-id="93092-144">**Android**</span><span class="sxs-lookup"><span data-stu-id="93092-144">**Android**</span></span>  | [<span data-ttu-id="93092-145">Microsoft Endpoint Manager </span><span class="sxs-lookup"><span data-stu-id="93092-145">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)               |
