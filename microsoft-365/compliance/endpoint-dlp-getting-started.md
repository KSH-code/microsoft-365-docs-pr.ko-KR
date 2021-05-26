---
title: Microsoft 365 엔드포인트 데이터 손실 방지 시작하기
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 Endpoint 데이터 손실 방지를 설정하여 파일 활동을 모니터링하고 해당 파일에 대한 보호 작업을 엔드포인트에 구현합니다.
ms.openlocfilehash: a6c0ec6f1248fdeecd8616b7eda000b7608d452d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651011"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="2ef4f-103">엔드포인트 데이터 손실 방지 시작하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="2ef4f-104">Microsoft Endpoint 데이터 손실 방지(Endpoint DLP)는 Microsoft 365 서비스에서 중요 한 항목을 검색하고 보호하는 데 사용할 수 있는 Microsoft 365의 DLP(데이터 손실 방지) 제품군의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="2ef4f-105">모든 Microsoft DLP 제공에 대한 자세한 내용은 [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-105">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span> <span data-ttu-id="2ef4f-106">끝점 DLP에 대해 자세히 알아보려면 [끝점 데이터 손실 방지](endpoint-dlp-learn-about.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="2ef4f-107">Microsoft Endpoint DLP를 사용하면 Windows 10 장치를 모니터링하고 중요한 항목이 사용되고 공유되는 때를 탐지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="2ef4f-108">이를 통해 중요한 항목이 올바르게 사용되며 보호하고 위험을 초래할 수 있는 위험한 행동을 방지하는 데 필요한 가시성과 제어 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2ef4f-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="2ef4f-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="2ef4f-110">SKU/구독 라이선싱</span><span class="sxs-lookup"><span data-stu-id="2ef4f-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="2ef4f-111">Endpoint DLP를 시작하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)과 추가 기능을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="2ef4f-112">Endpoint DLP 기능에 액세스하고 사용하려면 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="2ef4f-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2ef4f-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="2ef4f-114">Microsoft 365 A5(EDU)</span><span class="sxs-lookup"><span data-stu-id="2ef4f-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="2ef4f-115">Microsoft 365 E5 compliance</span><span class="sxs-lookup"><span data-stu-id="2ef4f-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="2ef4f-116">Microsoft 365 A5 compliance</span><span class="sxs-lookup"><span data-stu-id="2ef4f-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="2ef4f-117">Microsoft 365 E5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="2ef4f-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="2ef4f-118">Microsoft 365 A5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="2ef4f-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="2ef4f-119">권한</span><span class="sxs-lookup"><span data-stu-id="2ef4f-119">Permissions</span></span>

<span data-ttu-id="2ef4f-120">장치 관리를 사용하도록 설정하려면 사용하는 계정이 다음 역할 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="2ef4f-121">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-121">Global admin</span></span>
- <span data-ttu-id="2ef4f-122">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-122">Security admin</span></span>
- <span data-ttu-id="2ef4f-123">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-123">Compliance admin</span></span>

<span data-ttu-id="2ef4f-124">사용자 지정 계정을 사용하여 장치 관리 설정을 보려면 계정이 다음 역할 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="2ef4f-125">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-125">Global admin</span></span>
- <span data-ttu-id="2ef4f-126">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-126">Compliance admin</span></span>
- <span data-ttu-id="2ef4f-127">준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-127">Compliance data admin</span></span>
- <span data-ttu-id="2ef4f-128">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-128">Global reader</span></span>

<span data-ttu-id="2ef4f-129">사용자 지정 계정을 사용하여 온보딩/오프보딩 페이지에 액세스하려면 계정이 다음 역할 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="2ef4f-130">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-130">Global admin</span></span>
- <span data-ttu-id="2ef4f-131">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-131">Compliance admin</span></span>

<span data-ttu-id="2ef4f-132">사용자 지정 계정을 사용하여 장치 모니터링을 설정/해제하려면 계정이 다음 역할 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="2ef4f-133">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-133">Global admin</span></span>
- <span data-ttu-id="2ef4f-134">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-134">Compliance admin</span></span>

<span data-ttu-id="2ef4f-135">Endpoint DLP의 데이터는 [활동 탐색기](data-classification-activity-explorer.md)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="2ef4f-136">활동 탐색기에 대한 사용 권한을 부여하는 네 개의 역할이 있습니다. 데이터에 액세스하는 데 사용하는 계정은 해당 역할 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="2ef4f-137">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-137">Global admin</span></span>
- <span data-ttu-id="2ef4f-138">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-138">Compliance admin</span></span>
- <span data-ttu-id="2ef4f-139">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-139">Security admin</span></span>
- <span data-ttu-id="2ef4f-140">준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-140">Compliance data admin</span></span>
- <span data-ttu-id="2ef4f-141">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-141">Global reader</span></span>
- <span data-ttu-id="2ef4f-142">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-142">Security reader</span></span>
- <span data-ttu-id="2ef4f-143">보고서 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="2ef4f-143">Reports reader</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="2ef4f-144">엔드포인트 준비하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-144">Prepare your endpoints</span></span>

<span data-ttu-id="2ef4f-145">Endpoint DLP를 배포하는 데 사용할 Windows 10 장치가 다음 요구 사항을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-145">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="2ef4f-146">Windows 10 x64 빌드 1809 이상을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-146">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="2ef4f-147">맬웨어 방지 클라이언트 버전이 4.18.2009.7 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-147">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="2ef4f-148">Windows 보안 앱을 열고, 설정 아이콘을 선택한 다음 정보를 선택하여 현재 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-148">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="2ef4f-149">버전 번호는 맬웨어 방지 클라이언트 버전 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-149">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="2ef4f-150">Windows 업데이트 KB4052623을 설치하여 최신 맬웨어 방지 클라이언트 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-150">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="2ef4f-151">Windows 보안 구성 요소가 활성화되지 않아도 Windows 보안 상태와 독립적으로 끝점 DLP를 실행할 수 있습니다. 그러나 [실시간 보호 및 동작 모니터](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)는 활성화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-151">None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.</span></span>
 
3. <span data-ttu-id="2ef4f-152">다음 Windows 업데이트가 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-152">The following Windows Updates are installed.</span></span> 
 
   > [!NOTE]
   > <span data-ttu-id="2ef4f-153">참고: 이 업데이트는 장치를 끝점 DLP로 온보딩하기 위한 필수 요건은 아니지만, 중요한 문제에 대한 수정을 포함하므로 제품을 사용하기 전에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-153">These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="2ef4f-154">Windows 10 1809의 경우 - KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="2ef4f-154">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="2ef4f-155">Windows 10 1903 혹은 1909의 경우 - KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="2ef4f-155">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="2ef4f-156">Windows 10 2004의 경우 - KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="2ef4f-156">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="2ef4f-157">Office 2016(다른 Office 버전이 아님)을 실행하는 장치의 경우 - KB4577063</span><span class="sxs-lookup"><span data-stu-id="2ef4f-157">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="2ef4f-158">모든 장치는 다음 중 하나에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-158">All devices must be one of these:</span></span>
- [<span data-ttu-id="2ef4f-159">Azure AD(Azure Active Directory) 조인됨</span><span class="sxs-lookup"><span data-stu-id="2ef4f-159">Azure Active Directory (Azure AD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- <span data-ttu-id="2ef4f-160">AD 조인됨</span><span class="sxs-lookup"><span data-stu-id="2ef4f-160">AD joined</span></span>
- [<span data-ttu-id="2ef4f-161">하이브리드 Azure AD 조인됨</span><span class="sxs-lookup"><span data-stu-id="2ef4f-161">Hybrid Azure AD joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
- [<span data-ttu-id="2ef4f-162">AAD 등록됨</span><span class="sxs-lookup"><span data-stu-id="2ef4f-162">AAD registered</span></span>](/azure/active-directory/user-help/user-help-register-device-on-network)

5. <span data-ttu-id="2ef4f-163">엔드 포인트 장치에 Microsoft Chromium Edge 브라우저를 설치하여 클라우드로 업로드 활동에 대한 정책 작업을 적용하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-163">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="2ef4f-164">[Chromium 기반 새 Microsoft Edge 다운로드하기](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-164">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="2ef4f-165">Microsoft 365 앱 버전 2004~2008의 월 단위 엔터프라이즈 채널을 사용하고 있는 경우 Office 콘텐츠를 분류하는 엔드포인트 DLP와 관련된 알려진 문제가 있으며 버전 2009 이상으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-165">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="2ef4f-166">현재 버전에 대한 자세한 내용은 [Microsoft 365 앱의 업데이트 기록(날짜순)](/officeupdates/update-history-microsoft365-apps-by-date)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-166">See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="2ef4f-167">해당 문제에 대한 자세한 내용을 보려면 [2020년 현재 채널 릴리스에 대한 릴리스 노트](/officeupdates/current-channel#version-2010-october-27)의 Office 제품군 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-167">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="2ef4f-168">장치 프록시를 사용하여 인터넷에 연결하는 끝점이 있는 경우 [끝점 DLP에 대한 장치 프록시 및 인터넷 연결 설정 구성](endpoint-dlp-configure-proxy.md)의 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-168">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="2ef4f-169">장치 관리에 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="2ef4f-169">Onboarding devices into device management</span></span>

<span data-ttu-id="2ef4f-170">장치에서 중요한 항목을 모니터링하고 보호하려면 장치 모니터링을 사용하도록 설정하고 엔드포인트를 온보딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-170">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="2ef4f-171">이러한 작업은 모두 Microsoft 365 규정 준수 포털에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-171">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="2ef4f-172">아직 온보딩되지 않은 장치를 온보딩하려는 경우 적절한 스크립트를 다운로드하여 해당 장치에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-172">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="2ef4f-173">[장치 온보딩 절차](endpoint-dlp-getting-started.md#onboarding-devices)를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-173">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="2ef4f-174">이미 [엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)에 온보딩된 장치가 있으면 해당 장치가 관리되는 장치 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-174">If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="2ef4f-175">[엔드포인트용 Microsoft Defender에 온보딩된 장치 절차](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint)를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-175">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="2ef4f-176">온보딩 장치</span><span class="sxs-lookup"><span data-stu-id="2ef4f-176">Onboarding devices</span></span>

<span data-ttu-id="2ef4f-177">이 배포 시나리오에서는 아직 온보딩되지 않은 장치를 온보드하고, Windows 10 장치의 의도하지 않은 공유에서 중요한 항목을 모니터링하고 보호하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-177">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="2ef4f-178">[Microsoft 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-178">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="2ef4f-179">규정 준수 센터 설정 페이지를 열고 **장치 온보딩** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-179">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2ef4f-180">![장치 관리를 사용하도록 설정](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="2ef4f-180">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="2ef4f-181">일반적으로 장치 온보딩이 활성화되는 데 60초 정도 소요되지만, Microsoft 지원에 연락하기 전에 30분까지 기다려보세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-181">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="2ef4f-182">**장치 관리** 를 선택하여 **장치** 목록을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-182">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="2ef4f-183">목록은 장치가 온보딩될 때까지 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-183">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="2ef4f-184">**온보딩** 을 선택하여 온보딩 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-184">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="2ef4f-185">**배포 방법** 목록에서 이러한 추가 장치에 배포할 방법을 선택한 다음 **패키지를 다운로드합니다**.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2ef4f-186">![배포 방법](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="2ef4f-186">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="2ef4f-187">[Windows 10 컴퓨터용 온보딩 도구와 방법](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)의 해당 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-187">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="2ef4f-188">이 링크를 누르면 5단계에서 선택한 배포 패키지와 일치하는 엔드포인트용 Microsoft Defender에 액세스할 수 있는 랜딩 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-188">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="2ef4f-189">그룹 정책을 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-189">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="2ef4f-190">Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-190">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="2ef4f-191">모바일 장치 관리 도구를 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-191">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="2ef4f-192">로컬 스크립트를 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-192">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="2ef4f-193">단일 세션 시나리오에서 비영구적 VDI(가상 데스크톱 인프라) 머신 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-193">Onboard non-persistent virtual desktop infrastructure (VDI) machines in single-session scenarios</span></span>

<span data-ttu-id="2ef4f-194">작업이 완료되고 엔드포인트가 온보딩되면 장치 목록에 표시되고 감사 활동 로그를 활동 탐색기에 보고하기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-194">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="2ef4f-195">이 환경은 라이선스 적용하에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-195">This experience is under license enforcement.</span></span> <span data-ttu-id="2ef4f-196">필수 라이선스가 없으면 데이터가 표시되지 않거나 테이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-196">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="2ef4f-197">엔드포인트용 Microsoft Defender에 온보딩된 장치 사용</span><span class="sxs-lookup"><span data-stu-id="2ef4f-197">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="2ef4f-198">이 시나리오에서 엔드포인트용 Microsoft Defender는 이미 배포되었으며 엔드포인트 보고가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-198">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="2ef4f-199">이러한 모든 엔드포인트는 관리되는 장치 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-199">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="2ef4f-200">[장치 온보딩 절차](endpoint-dlp-getting-started.md#onboarding-devices)를 사용하여 새 장치를 Endpoint DLP로 계속해서 온보딩하여 범위를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-200">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="2ef4f-201">[Microsoft 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-201">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="2ef4f-202">규정 준수 센터 설정 페이지를 열고 **장치 모니터링 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-202">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="2ef4f-203">**장치 관리** 를 선택하여 **장치** 목록을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-203">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="2ef4f-204">이미 엔드포인트용 Microsoft Defender에 보고하고 있는 장치 목록이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-204">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2ef4f-205">![장치 관리](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="2ef4f-205">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="2ef4f-206">추가 디바이스를 온보딩해야 하는 경우에는 **온보딩** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-206">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="2ef4f-207">**배포 방법** 목록에서 이러한 추가 장치에 배포할 방법을 선택한 다음 **패키지를 다운로드합니다**.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-207">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="2ef4f-208">[Windows 10 컴퓨터용 온보딩 도구와 방법](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)의 해당 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-208">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="2ef4f-209">이 링크를 누르면 5단계에서 선택한 배포 패키지와 일치하는 엔드포인트용 Microsoft Defender에 액세스할 수 있는 랜딩 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-209">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="2ef4f-210">그룹 정책을 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-210">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="2ef4f-211">Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-211">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="2ef4f-212">모바일 장치 관리 도구를 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-212">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="2ef4f-213">로컬 스크립트를 사용하여 Windows 10 컴퓨터 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-213">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="2ef4f-214">비영구적 VDI(가상 데스크톱 인프라) 머신 온보딩하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-214">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="2ef4f-215">작업이 완료되고 엔드포인트가 온보딩되면 **장치** 표에 표시되고 감사 로그를 **활동 탐색기** 에 보고하기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-215">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="2ef4f-216">이 환경은 라이선스 적용하에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-216">This experience is under license enforcement.</span></span> <span data-ttu-id="2ef4f-217">필수 라이선스가 없으면 데이터가 표시되지 않거나 테이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-217">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="2ef4f-218">DLP 경고 관리 대시보드에서 끝점 DLP 경고 보기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-218">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="2ef4f-219">Microsoft 365 규정 준수 센터에서 데이터 손실 방지 페이지를 열고 경고를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-219">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="2ef4f-220">끝점 DLP 정책에 대한 경고를 보려면 [DLP 정책에 대한 경고를 구성하고 보는 방법](dlp-configure-view-alerts-policies.md)에서 절차를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-220">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="2ef4f-221">활동 탐색기에서 Endpoint DLP 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-221">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="2ef4f-222">Microsoft 365 규정 준수 센터에서 도메인에 대한 [데이터 분류 페이지](https://compliance.microsoft.com/dataclassification?viewid=overview)를 열고 활동 탐색기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-222">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="2ef4f-223">[활동 탐색기 시작하기](data-classification-activity-explorer.md)의 절차를 참조하여 엔드포인트 장치에 대한 모든 데이터에 액세스하고 테이터를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-223">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2ef4f-224">![엔드포인트 장치에 대한 활동 탐색기 필터](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="2ef4f-224">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="2ef4f-225">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2ef4f-225">Next steps</span></span>
<span data-ttu-id="2ef4f-226">이제 온보딩된 장치가 있고 활동 탐색기에서 활동 데이터를 볼 수 있으므로 중요한 항목을 보호하는 DLP 정책을 만드는 다음 단계를 진행할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4f-226">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="2ef4f-227">엔드포인트 데이터 손실 방지 사용</span><span class="sxs-lookup"><span data-stu-id="2ef4f-227">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="2ef4f-228">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ef4f-228">See also</span></span>

- [<span data-ttu-id="2ef4f-229">끝점 데이터 손실 방지에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="2ef4f-229">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="2ef4f-230">끝점 데이터 손실 방지 사용</span><span class="sxs-lookup"><span data-stu-id="2ef4f-230">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="2ef4f-231">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-231">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="2ef4f-232">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="2ef4f-232">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="2ef4f-233">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-233">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="2ef4f-234">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2ef4f-234">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="2ef4f-235">Windows 10 컴퓨터용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="2ef4f-235">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="2ef4f-236">Microsoft 365 구독</span><span class="sxs-lookup"><span data-stu-id="2ef4f-236">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="2ef4f-237">Azure AD 가입 장치</span><span class="sxs-lookup"><span data-stu-id="2ef4f-237">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="2ef4f-238">Chromium 기반 새 Microsoft Edge 다운로드하기</span><span class="sxs-lookup"><span data-stu-id="2ef4f-238">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
