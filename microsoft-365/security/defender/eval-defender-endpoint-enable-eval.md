---
title: 끝점 평가를 위해 Microsoft Defender 사용, MDE 평가 활성화
description: 라이선스 Microsoft 365 Defender 및 온보딩 엔드포인트를 포함하여 테스트 테스트 또는 파일럿 환경을 사용하도록 설정
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458100"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a><span data-ttu-id="575d1-103">끝점 평가 환경에 Microsoft Defender 사용</span><span class="sxs-lookup"><span data-stu-id="575d1-103">Enable Microsoft Defender for Endpoint evaluation environment</span></span>


<span data-ttu-id="575d1-104">이 문서에서는 프로덕션 장치를 사용하여 끝점용 Microsoft Defender의 평가 환경을 설정하는 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-104">This article will guide you through the steps on setting up the evaluation environment for Microsoft Defender for Endpoint using production devices.</span></span> 


>[!TIP]
><span data-ttu-id="575d1-105">끝점용 Microsoft Defender에는 미리 구성된 장치를 추가하고 시뮬레이션을 실행하여 플랫폼의 기능을 평가할 수 있는 제품 내 평가 랩도 함께 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-105">Microsoft Defender for Endpoint also comes with an in-product evaluation lab where you can add pre-configured devices and run simulations to evaluate the capabilities of the platform.</span></span> <span data-ttu-id="575d1-106">이 랩에는 고급 헌팅 및 위협 분석과 같은 많은 기능에 대한 지침을 포함하여 Enpdoint용 Microsoft Defender의 가치를 빠르게 보여 줄 수 있는 간소화된 설정 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-106">The lab comes with a simplified set-up experience that can help quickly demonstrate the value of Microsoft Defender for Enpdoint including guidance for many features like advanced hunting and threat analytics.</span></span> <span data-ttu-id="575d1-107">자세한 내용은 [기능 평가를 참조하세요.](/defender-endpoint/evaluation-lab.md)</span><span class="sxs-lookup"><span data-stu-id="575d1-107">For more information, see [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span></span> <br> <span data-ttu-id="575d1-108">이 문서에서 제공하는 지침과 평가 랩의 주요 차이점은 평가 환경은 프로덕션 장치를 사용하는 반면, 평가 랩은 프로덕션이 아닌 장치를 사용하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-108">The main difference between the guidance provided in this article and the evaluation lab is the evaluation environment uses production devices whereas the evaluation lab uses non-production devices.</span></span> 

<span data-ttu-id="575d1-109">다음 단계를 사용하여 끝점용 Microsoft Defender에 대한 평가를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-109">Use the following steps to enable the evaluation for Microsoft Defender for Endpoint.</span></span>

![Microsoft Defender 평가 환경에서 끝점에 대해 Microsoft Defender를 사용하도록 설정하는 단계](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [<span data-ttu-id="575d1-111">1단계. 라이선스 상태 확인</span><span class="sxs-lookup"><span data-stu-id="575d1-111">Step 1. Check license state</span></span>](#step-1-check-license-state)
- [<span data-ttu-id="575d1-112">2단계. 끝점 온보드</span><span class="sxs-lookup"><span data-stu-id="575d1-112">Step 2. Onboard endpoints</span></span>](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a><span data-ttu-id="575d1-113">1단계.</span><span class="sxs-lookup"><span data-stu-id="575d1-113">Step 1.</span></span> <span data-ttu-id="575d1-114">라이선스 상태 확인</span><span class="sxs-lookup"><span data-stu-id="575d1-114">Check license state</span></span>

<span data-ttu-id="575d1-115">먼저 라이선스 상태를 확인하여 라이선스가 제대로 프로비전되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-115">You'll first need to check the license state to verify that it was properly provisioned.</span></span> <span data-ttu-id="575d1-116">이 작업을 관리 센터 또는 관리 포털을 통해 Microsoft Azure **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="575d1-116">You can do this through the admin center or through the **Microsoft Azure portal**.</span></span>


1. <span data-ttu-id="575d1-117">라이선스를 확인하기 위해 Microsoft Azure **포털로** 이동하여 Microsoft Azure 포털 라이선스 섹션으로 [이동합니다.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="575d1-117">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 라이선스 페이지의 이미지](../../media/defender/atp-licensing-azure-portal.png)

1. <span data-ttu-id="575d1-119">또는 관리 센터에서 청구 **구독으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="575d1-119">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="575d1-120">화면에 프로비전된 모든 라이선스 및 해당 현재 상태가 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="575d1-120">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![청구 라이선스 이미지](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="575d1-122">2단계.</span><span class="sxs-lookup"><span data-stu-id="575d1-122">Step 2.</span></span> <span data-ttu-id="575d1-123">지원되는 관리 도구를 사용하여 끝점 온보드</span><span class="sxs-lookup"><span data-stu-id="575d1-123">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="575d1-124">라이선스 상태가 올바르게 프로비전되었는지 확인한 후 장치에 서비스 등록을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-124">After verifying that the license state has been provisioned properly, you can start onboarding devices to the service.</span></span> 

<span data-ttu-id="575d1-125">끝점용 Microsoft Defender를 평가하기 위해 평가를 수행하기 위해 몇 Windows 10 장치를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-125">For the purpose of evaluating Microsoft Defender for Endpoint, we recommend choosing a couple of Windows 10 devices to conduct the evaluation on.</span></span> 

<span data-ttu-id="575d1-126">배포 [계획 항목에서는](../defender-endpoint/deployment-strategy.md) 끝점용 Defender를 배포하는 데 필요한 일반적인 단계를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-126">The [Plan deployment](../defender-endpoint/deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="575d1-127">이 비디오를 시청하여 온보더링 프로세스에 대한 간략한 개요를 알아보고 사용 가능한 도구 및 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-127">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a><span data-ttu-id="575d1-128">온보더링 도구 옵션</span><span class="sxs-lookup"><span data-stu-id="575d1-128">Onboarding tool options</span></span>

<span data-ttu-id="575d1-129">다음 표에는 온보드해야 하는 끝점에 따라 사용 가능한 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="575d1-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

<span data-ttu-id="575d1-130">끝점</span><span class="sxs-lookup"><span data-stu-id="575d1-130">Endpoint</span></span> | <span data-ttu-id="575d1-131">도구 옵션</span><span class="sxs-lookup"><span data-stu-id="575d1-131">Tool options</span></span>
:---|:---
<span data-ttu-id="575d1-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="575d1-132">**Windows**</span></span> | <span data-ttu-id="575d1-133">[로컬 스크립트(최대 10대의 장치),](../defender-endpoint/configure-endpoints-script.md)그룹 [정책, Microsoft Endpoint Manager/ 모바일](../defender-endpoint/configure-endpoints-mdm.md)장치 관리자, Microsoft Endpoint Configuration Manager, [VDI](../defender-endpoint/configure-endpoints-vdi.md)스크립트, [Azure Defender와의](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) 통합 [](../defender-endpoint/configure-endpoints-gp.md) [](../defender-endpoint/configure-endpoints-sccm.md)</span><span class="sxs-lookup"><span data-stu-id="575d1-133">[Local script (up to 10 devices)](../defender-endpoint/configure-endpoints-script.md),  [Group Policy](../defender-endpoint/configure-endpoints-gp.md),  [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md),  [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md),  [VDI scripts](../defender-endpoint/configure-endpoints-vdi.md),  [Integration with Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span></span>
<span data-ttu-id="575d1-134">**macOS**</span><span class="sxs-lookup"><span data-stu-id="575d1-134">**macOS**</span></span> | <span data-ttu-id="575d1-135">[로컬 스크립트](../defender-endpoint/mac-install-manually.md) [,](../defender-endpoint/mac-install-with-intune.md)Microsoft Endpoint Manager , [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md), 모바일 장치 [관리](../defender-endpoint/mac-install-with-other-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="575d1-135">[Local scripts](../defender-endpoint/mac-install-manually.md),  [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md),  [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md),  [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span></span>
<span data-ttu-id="575d1-136">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="575d1-136">**Linux Server**</span></span> | <span data-ttu-id="575d1-137">[로컬 스크립트,](../defender-endpoint/linux-install-manually.md)  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span><span class="sxs-lookup"><span data-stu-id="575d1-137">[Local script](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span></span>
<span data-ttu-id="575d1-138">**iOS**</span><span class="sxs-lookup"><span data-stu-id="575d1-138">**iOS**</span></span> | [<span data-ttu-id="575d1-139">앱 기반</span><span class="sxs-lookup"><span data-stu-id="575d1-139">App-based</span></span>](../defender-endpoint/ios-install.md)
<span data-ttu-id="575d1-140">**Android**</span><span class="sxs-lookup"><span data-stu-id="575d1-140">**Android**</span></span> | [<span data-ttu-id="575d1-141">Microsoft Endpoint Manager </span><span class="sxs-lookup"><span data-stu-id="575d1-141">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)



## <a name="next-step"></a><span data-ttu-id="575d1-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="575d1-142">Next step</span></span>
[<span data-ttu-id="575d1-143">끝점용 Microsoft Defender에 대한 파일럿 설정</span><span class="sxs-lookup"><span data-stu-id="575d1-143">Setup the pilot for Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-pilot.md)
 
<span data-ttu-id="575d1-144">[끝점용 Microsoft Defender 평가 개요로 돌아가기](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="575d1-144">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="575d1-145">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="575d1-145">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>