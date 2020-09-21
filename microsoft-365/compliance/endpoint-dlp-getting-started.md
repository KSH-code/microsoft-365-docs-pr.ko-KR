---
title: Microsoft 365 Endpoint 데이터 손실 방지(미리 보기) 시작하기
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Microsoft 365 Endpoint 데이터 손실 방지를 설정하여 파일 활동을 모니터링하고 해당 파일에 대한 보호 작업을 엔드포인트에 구현합니다.
ms.openlocfilehash: 43ab2a30570f153f16819ede2eeed1f0e091da74
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949848"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="ce8c5-103">Endpoint 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-103">Get started with Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="ce8c5-104">Microsoft Endpoint 데이터 손실 방지(Endpoint DLP)는 Microsoft 365 서비스에서 중요 한 항목을 검색하고 보호하는 데 사용할 수 있는 Microsoft 365의 DLP(데이터 손실 방지) 제품군의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="ce8c5-105">모든 Microsoft의 DLP 제공에 대한 자세한 내용은 [데이터 손실 방지 개요](data-loss-prevention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="ce8c5-106">Endpoint DLP에 대한 자세한 내용은 [Endpoint 데이터 손실 방지(미리 보기)에 대한 자세한 정보](endpoint-dlp-learn-about.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention (preview)](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="ce8c5-107">Microsoft Endpoint DLP를 사용하면 Windows 10 장치를 모니터링하고 중요한 항목이 사용되고 공유되는 때를 탐지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="ce8c5-108">이를 통해 중요한 항목이 올바르게 사용되며 보호하고 위험을 초래할 수 있는 위험한 행동을 방지하는 데 필요한 가시성과 제어 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ce8c5-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="ce8c5-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="ce8c5-110">SKU/구독 라이선싱</span><span class="sxs-lookup"><span data-stu-id="ce8c5-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="ce8c5-111">Endpoint DLP를 시작하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)과 추가 기능을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="ce8c5-112">Endpoint DLP 기능에 액세스하고 사용하려면 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="ce8c5-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ce8c5-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="ce8c5-114">Microsoft 365 A5(EDU)</span><span class="sxs-lookup"><span data-stu-id="ce8c5-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="ce8c5-115">Microsoft 365 E5 compliance</span><span class="sxs-lookup"><span data-stu-id="ce8c5-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="ce8c5-116">Microsoft 365 A5 compliance</span><span class="sxs-lookup"><span data-stu-id="ce8c5-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="ce8c5-117">Microsoft 365 E5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="ce8c5-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="ce8c5-118">Microsoft 365 A5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="ce8c5-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="ce8c5-119">권한</span><span class="sxs-lookup"><span data-stu-id="ce8c5-119">Permissions</span></span>

<span data-ttu-id="ce8c5-120">장치 관리를 사용하도록 설정하려면 사용하는 계정이 다음 역할 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="ce8c5-121">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-121">Global admin</span></span>
- <span data-ttu-id="ce8c5-122">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-122">Security admin</span></span>
- <span data-ttu-id="ce8c5-123">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-123">Compliance admin</span></span>

<span data-ttu-id="ce8c5-124">사용자 지정 계정을 사용하여 장치 관리 설정을 보려면 계정이 다음 역할 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="ce8c5-125">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-125">Global admin</span></span>
- <span data-ttu-id="ce8c5-126">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-126">Compliance admin</span></span>
- <span data-ttu-id="ce8c5-127">준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-127">Compliance data admin</span></span>
- <span data-ttu-id="ce8c5-128">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-128">Global reader</span></span>

<span data-ttu-id="ce8c5-129">사용자 지정 계정을 사용하여 온보딩/오프보딩 페이지에 액세스하려면 계정이 다음 역할 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="ce8c5-130">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-130">Global admin</span></span>
- <span data-ttu-id="ce8c5-131">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-131">Compliance admin</span></span>

<span data-ttu-id="ce8c5-132">사용자 지정 계정을 사용하여 장치 모니터링을 설정/해제하려면 계정이 다음 역할 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="ce8c5-133">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-133">Global admin</span></span>
- <span data-ttu-id="ce8c5-134">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-134">Compliance admin</span></span>

<span data-ttu-id="ce8c5-135">Endpoint DLP의 데이터는 [활동 탐색기](data-classification-activity-explorer.md)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="ce8c5-136">활동 탐색기에 대한 사용 권한을 부여하는 네 개의 역할이 있습니다. 데이터에 액세스하는 데 사용하는 계정은 해당 역할 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="ce8c5-137">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-137">Global admin</span></span>
- <span data-ttu-id="ce8c5-138">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-138">Compliance admin</span></span>
- <span data-ttu-id="ce8c5-139">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-139">Security admin</span></span>
- <span data-ttu-id="ce8c5-140">준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="ce8c5-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="ce8c5-141">엔드포인트 준비하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-141">Prepare your endpoints</span></span>

<span data-ttu-id="ce8c5-142">Endpoint DLP를 배포하는 데 사용할 Windows 10 장치가 다음 요구 사항을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="ce8c5-143">Windows 10 빌드 1809 이상을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-143">Must be running Windows 10 build 1809 or up.</span></span>
2. <span data-ttu-id="ce8c5-144">모든 장치가 [AAD(Azure Active Directory)에 가입](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)되어 있거나 Hybrid Azure AD에 가입되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-144">All devices must be [Azure Active Directory (AAD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>
3. <span data-ttu-id="ce8c5-145">엔드 포인트 장치에 Microsoft Chromium Edge 브라우저를 설치하여 클라우드로 업로드 활동에 대한 정책 작업을 적용하세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-145">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="ce8c5-146">[Chromium 기반 새 Microsoft Edge 다운로드하기](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-146">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="ce8c5-147">장치 관리에 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="ce8c5-147">Onboarding devices into device management</span></span>

 <span data-ttu-id="ce8c5-148">장치에서 중요한 항목을 모니터링하고 보호하려면 장치 모니터링을 사용하도록 설정하고 엔드포인트를 온보딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-148">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="ce8c5-149">이러한 작업은 모두 Microsoft 365 규정 준수 포털에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-149">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="ce8c5-150">아직 온보딩되지 않은 장치를 온보딩하려는 경우 적절한 스크립트를 다운로드하여 해당 장치에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-150">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="ce8c5-151">[장치 온보딩 절차](endpoint-dlp-getting-started.md#onboarding-devices)를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-151">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="ce8c5-152">이미 [MDATP(Microsoft Defender Advanced Threat Protection)](https://docs.microsoft.com/windows/security/threat-protection/)에 온보딩된 장치가 있으면 해당 장치가 관리되는 장치 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-152">If you already have devices onboarded into [Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="ce8c5-153">[MDATP에 온보딩된 장치의 경우 절차](endpoint-dlp-getting-started.md#with-devices-onboarded-into-mdatp)를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-153">Follow the [With devices onboarded into MDATP procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-mdatp).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="ce8c5-154">장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="ce8c5-154">Onboarding devices</span></span>

<span data-ttu-id="ce8c5-155">이 배포 시나리오에서는 아직 온보딩되지 않은 장치를 온보드하고, Windows 10 장치의 의도하지 않은 공유에서 중요한 항목을 모니터링하고 보호하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-155">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="ce8c5-156">[Microsoft 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-156">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="ce8c5-157">규정 준수 센터 설정 페이지를 열고 **장치 온보딩**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-157">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   ![장치 관리 사용하도록 설정하기](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > <span data-ttu-id="ce8c5-159">일반적으로 장치 온보딩이 활성화되는 데 60초 정도 소요되지만, Microsoft 지원에 연락하기 전에 30분까지 기다려보세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-159">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="ce8c5-160">**장치 관리**를 선택하여 **장치** 목록을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-160">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="ce8c5-161">목록은 장치가 온보딩될 때까지 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-161">The list will be empty until you onboard devices.</span></span>
4. <span data-ttu-id="ce8c5-162">**온보딩**을 선택하여 온보딩 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-162">Choose **Onboarding** to begin the onboarding process.</span></span>
5. <span data-ttu-id="ce8c5-163">**배포 방법** 목록에서 이러한 추가 장치에 배포할 방법을 선택한 다음 **패키지를 다운로드합니다**.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-163">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   ![배포 방법](../media/endpoint-dlp-getting-started-3-deployment-method.png)
6. <span data-ttu-id="ce8c5-165">[Windows 10 컴퓨터용 온보딩 도구와 방법](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)의 해당 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-165">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="ce8c5-166">이 링크를 누르면 5단계에서 선택한 배포 패키지와 일치하는 MDATP 절차에 액세스할 수 있는 랜딩 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-166">This link take you to a landing page where you can access MDATP procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="ce8c5-167">그룹 정책을 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-167">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="ce8c5-168">Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-168">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="ce8c5-169">모바일 장치 관리 도구를 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-169">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="ce8c5-170">로컬 스크립트를 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-170">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="ce8c5-171">비영구적 VDI(가상 데스크톱 인프라) 머신 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-171">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="ce8c5-172">작업이 완료되고 엔드포인트가 온보딩되면 장치 목록에 표시되고 감사 활동 로그를 활동 탐색기에 보고하기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-172">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="ce8c5-173">이 환경은 라이선스 적용하에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-173">This experience is under license enforcement.</span></span> <span data-ttu-id="ce8c5-174">필수 라이선스가 없으면 데이터가 표시되지 않거나 테이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-174">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-mdatp"></a><span data-ttu-id="ce8c5-175">MDATP에 온보딩된 장치의 경우</span><span class="sxs-lookup"><span data-stu-id="ce8c5-175">With devices onboarded into MDATP</span></span>

<span data-ttu-id="ce8c5-176">이 시나리오에서 MDATP는 이미 배포되었으며 엔드포인트 보고가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-176">In this scenario, MDATP is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="ce8c5-177">이러한 모든 엔드포인트는 관리되는 장치 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-177">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="ce8c5-178">[장치 온보딩 절차](endpoint-dlp-getting-started.md#onboarding-devices)를 사용하여 새 장치를 Endpoint DLP로 계속해서 온보딩하여 범위를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-178">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="ce8c5-179">[Microsoft 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-179">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="ce8c5-180">규정 준수 센터 설정 페이지를 열고 **장치 모니터링 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-180">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>
3. <span data-ttu-id="ce8c5-181">**장치 관리**를 선택하여 **장치** 목록을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-181">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="ce8c5-182">이미 MDATP에 보고하고 있는 장치 목록이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-182">You should see the list of devices that are already reporting in to MDATP.</span></span> <span data-ttu-id="ce8c5-183">![장치 관리](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="ce8c5-183">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
4. <span data-ttu-id="ce8c5-184">추가 디바이스를 온보딩해야 하는 경우에는 **온보딩**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-184">Choose **Onboarding** if you need to onboard additional devices.</span></span>
5. <span data-ttu-id="ce8c5-185">**배포 방법** 목록에서 이러한 추가 장치에 배포할 방법을 선택한 다음 **패키지를 다운로드합니다**.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>
6. <span data-ttu-id="ce8c5-186">[Windows 10 컴퓨터용 온보딩 도구와 방법](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)의 해당 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-186">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="ce8c5-187">이 링크를 누르면 5단계에서 선택한 배포 패키지와 일치하는 MDATP 절차에 액세스할 수 있는 랜딩 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-187">This link take you to a landing page where you can access MDATP procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="ce8c5-188">그룹 정책을 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-188">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="ce8c5-189">Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-189">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="ce8c5-190">모바일 장치 관리 도구를 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-190">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="ce8c5-191">로컬 스크립트를 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-191">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="ce8c5-192">비영구적 VDI(가상 데스크톱 인프라) 머신 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-192">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="ce8c5-193">작업이 완료되고 엔드포인트가 온보딩되면 **장치** 표에 표시되고 감사 로그를 **활동 탐색기**에 보고하기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-193">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="ce8c5-194">이 환경은 라이선스 적용하에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-194">This experience is under license enforcement.</span></span> <span data-ttu-id="ce8c5-195">필수 라이선스가 없으면 데이터가 표시되지 않거나 테이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-195">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="ce8c5-196">활동 탐색기에서 Endpoint DLP 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-196">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="ce8c5-197">Microsoft 365 규정 준수 센터에서 도메인에 대한 [데이터 분류 페이지](https://compliance.microsoft.com/dataclassification?viewid=overview)를 열고 활동 탐색기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-197">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>
2. <span data-ttu-id="ce8c5-198">[활동 탐색기 시작하기](data-classification-activity-explorer.md)의 절차를 참조하여 엔드포인트 장치에 대한 모든 데이터에 액세스하고 테이터를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-198">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

![엔드포인트 장치에 대한 활동 탐색기 필터](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a><span data-ttu-id="ce8c5-200">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ce8c5-200">Next steps</span></span>
<span data-ttu-id="ce8c5-201">이제 온보딩된 장치가 있고 활동 탐색기에서 활동 데이터를 볼 수 있으므로 중요한 항목을 보호하는 DLP 정책을 만드는 다음 단계를 진행할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce8c5-201">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="ce8c5-202">Endpoint 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-202">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="ce8c5-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce8c5-203">See also</span></span>

- [<span data-ttu-id="ce8c5-204">Endpoint 데이터 손실 방지(미리 보기)에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="ce8c5-204">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="ce8c5-205">Endpoint 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-205">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="ce8c5-206">데이터 손실 방지 개요</span><span class="sxs-lookup"><span data-stu-id="ce8c5-206">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="ce8c5-207">DLP 정책 생성, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="ce8c5-207">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="ce8c5-208">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-208">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="ce8c5-209">Microsoft Defender Advanced Threat Protection(Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="ce8c5-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="ce8c5-210">Windows 10 컴퓨터용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="ce8c5-210">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="ce8c5-211">Microsoft 365 구독</span><span class="sxs-lookup"><span data-stu-id="ce8c5-211">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="ce8c5-212">Azure Active Directory(AAD) 가입</span><span class="sxs-lookup"><span data-stu-id="ce8c5-212">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="ce8c5-213">Chromium 기반 새 Microsoft Edge 다운로드하기</span><span class="sxs-lookup"><span data-stu-id="ce8c5-213">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
