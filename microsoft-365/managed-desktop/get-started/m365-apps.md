---
title: 엔터프라이즈용 Microsoft 365 앱
description: 배포 Microsoft 365 앱, 업데이트 방법 및 설정 관리 방법
keywords: 변경 내용
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: c3928b5814332f2585adc613e1e84cbe5cc883a0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925614"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="eaae7-104">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="eaae7-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="eaae7-105">초기 배포</span><span class="sxs-lookup"><span data-stu-id="eaae7-105">Initial deployment</span></span>

<span data-ttu-id="eaae7-106">Microsoft Managed Desktop 엔터프라이즈용 Microsoft 365 앱64비트(64비트)가 모든 프로그램 디바이스에 이미지의 일부로 [설치되도록 합니다.](../service-description/device-list.md)</span><span class="sxs-lookup"><span data-stu-id="eaae7-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="eaae7-107">다음 응용 프로그램이 모두 전달될 때 디바이스에 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="eaae7-108">Word</span><span class="sxs-lookup"><span data-stu-id="eaae7-108">Word</span></span>
- <span data-ttu-id="eaae7-109">Excel</span><span class="sxs-lookup"><span data-stu-id="eaae7-109">Excel</span></span>
- <span data-ttu-id="eaae7-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="eaae7-110">PowerPoint</span></span>
- <span data-ttu-id="eaae7-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="eaae7-111">Outlook</span></span>
- <span data-ttu-id="eaae7-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="eaae7-112">Publisher</span></span>
- <span data-ttu-id="eaae7-113">Access</span><span class="sxs-lookup"><span data-stu-id="eaae7-113">Access</span></span>
- <span data-ttu-id="eaae7-114">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="eaae7-114">Skype for Business</span></span>
- <span data-ttu-id="eaae7-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="eaae7-115">OneNote</span></span>

<span data-ttu-id="eaae7-116">이 접근 방식은 네트워크 영향을 최소화하고 사용자가 장치를 받는 즉시 생산성을 확보할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="eaae7-117">그런 다음 관리되는 장치에 더 많은 정책을 배포하여 사용할 응용 프로그램을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="eaae7-118">Microsoft Teams 배포할 때 엔터프라이즈용 Microsoft 365 앱 이미지에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="eaae7-119">사용자에게 사용 가능한 배포</span><span class="sxs-lookup"><span data-stu-id="eaae7-119">Available deployment to users</span></span>

<span data-ttu-id="eaae7-120">어떤 이유로 Microsoft 365 앱 장치에 대한 사용자 계정이 없는 경우 패키지를 사용하여 디바이스를 예상 상태로 되 돌아올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="eaae7-121">최신 **Workplace-Office-Office365_Install** 그룹에 사용자를 추가하면 해당 그룹에서 앱을 사용할 수 회사 포털.</span><span class="sxs-lookup"><span data-stu-id="eaae7-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="eaae7-122">엔터프라이즈용 Microsoft 365 앱(32비트)</span><span class="sxs-lookup"><span data-stu-id="eaae7-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="eaae7-123">Microsoft Managed Desktop 32비트 버전의 엔터프라이즈용 M365 앱 배포를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="eaae7-124">업데이트 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="eaae7-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="eaae7-125">Microsoft 365 앱 월별 채널에서 업데이트할 Enterprise [있습니다.](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)</span><span class="sxs-lookup"><span data-stu-id="eaae7-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="eaae7-126">이 방법을 사용하면 매월 새로운 Office 기능을 제공하지만 예측 가능한 릴리스 일정에 따라 매월 하나의 업데이트만 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="eaae7-127">업데이트는 두 번째 화요일에 릴리스됩니다. 이러한 업데이트에는 기능, 보안 및 품질 업데이트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="eaae7-128">이러한 업데이트는 자동으로 발생하며 해당 특정 채널에 대한 Office CDN 직접 끌어오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="eaae7-129">Microsoft Managed Desktop 각 릴리스에 시차를 두어 작업 환경에서 발생할 수 있는 문제를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="eaae7-130">앱 제품 그룹에서 릴리스 후 28일 후에 Microsoft 365 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="eaae7-131">Microsoft Managed Desktop 그룹으로 업데이트 릴리스를 예약하여 다음과 같이 유효성 검사 및 테스트에 필요한 시간을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="eaae7-132">테스트: 제로 일</span><span class="sxs-lookup"><span data-stu-id="eaae7-132">Test: zero days</span></span>
- <span data-ttu-id="eaae7-133">첫 번째: 제로 일</span><span class="sxs-lookup"><span data-stu-id="eaae7-133">First: zero days</span></span>
- <span data-ttu-id="eaae7-134">빠르기: 3일</span><span class="sxs-lookup"><span data-stu-id="eaae7-134">Fast: 3 days</span></span>
- <span data-ttu-id="eaae7-135">광범위: 7일</span><span class="sxs-lookup"><span data-stu-id="eaae7-135">Broad: 7 days</span></span>

<span data-ttu-id="eaae7-136">Microsoft Managed Desktop 업데이트 기한을 [7일로](/deployoffice/configure-update-settings-microsoft-365-apps) 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-136">Microsoft Managed Desktop sets a seven-day [update deadline](/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="eaae7-137">업데이트를 사용할 수 있는 경우 7일 이내에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="eaae7-138">마감일 [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 12시간 전에 응용 프로그램, 시스템 트레이의 여러 위치에서 업데이트가 필요하다는 알림을 받고 마감일 이전에 15분간 경고를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-138">Users are [notified](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="eaae7-139">모든 Microsoft 365 앱 완료하려면 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="eaae7-140">업데이트의 페이스킹 또는 롤백</span><span class="sxs-lookup"><span data-stu-id="eaae7-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="eaae7-141">어떤 이유로든 앱 업데이트를 일시 중지하거나 롤백해야 Microsoft 365 [](../working-with-managed-desktop/admin-support.md) 포털을 통해 관리자 지원 요청을 Microsoft Managed Desktop 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="eaae7-142">릴리스 중에는 Microsoft Managed Desktop 오류율을 모니터링할 수 Microsoft 365 앱.</span><span class="sxs-lookup"><span data-stu-id="eaae7-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="eaae7-143">새 릴리스와 그 선행 버전 간 품질이 크게 다를 경우 Microsoft Managed Desktop 관리 포털을 통해 연락을 Microsoft Managed Desktop 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="eaae7-144">심각도에 따라 릴리스를 일시 중지할지 묻거나 문제를 완화하기 위해 조치를 취했다고 알려드릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="eaae7-145">배달 최적화</span><span class="sxs-lookup"><span data-stu-id="eaae7-145">Delivery optimization</span></span>

<span data-ttu-id="eaae7-146">배달 최적화는 다양한 기능에서 사용할 수 있는 피어 투 피어 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="eaae7-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="eaae7-147">이 기능을 사용하면 장치가 인터넷을 통해 Microsoft에서 다운로드한 업데이트와 같은 콘텐츠를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="eaae7-148">장치를 사용하면 Microsoft에서 업데이트를 완전히 다운로드하지 않고도 로컬 네트워크의 다른 장치에서 업데이트의 일부를 다운로드할 수 있기 때문에 네트워크 대역폭을 줄이는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="eaae7-149">[배달 최적화는](/deployoffice/delivery-optimization) Windows 10 Enterprise 또는 Windows 10 Education 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-149">[Delivery Optimization](/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="eaae7-150">설정 관리되는 Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="eaae7-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="eaae7-151">Microsoft는 서비스의 일부로 일부 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="eaae7-152">Microsoft Managed Desktop 보안 기준은 관리하지 않지만 Office 관리 섹션의 지침에 따라 직접 설정할 [설정](#settings-you-manage) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="eaae7-153">설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="eaae7-153">Update settings</span></span>

<span data-ttu-id="eaae7-154">Microsoft Managed Desktop [장치에](/deployoffice/configure-update-settings-microsoft-365-apps) 대한 모든 업데이트 설정을 유지 관리하며 이러한 설정을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-154">Microsoft Managed Desktop maintains all [update settings](/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="eaae7-155">자동으로 실행하도록 업데이트 설정</span><span class="sxs-lookup"><span data-stu-id="eaae7-155">Set updates to occur automatically</span></span>

<span data-ttu-id="eaae7-156">**기본값:** 사용</span><span class="sxs-lookup"><span data-stu-id="eaae7-156">**Default value**: Enabled</span></span>

<span data-ttu-id="eaae7-157">이 정책은 모든 Office 클라우드에서 최신으로 유지될 수 있도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="eaae7-158">업데이트를 적용해야 하는 마감일 설정</span><span class="sxs-lookup"><span data-stu-id="eaae7-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="eaae7-159">**기본값:** 7일</span><span class="sxs-lookup"><span data-stu-id="eaae7-159">**Default value**: 7 days</span></span>

<span data-ttu-id="eaae7-160">**UpdateDeadline** 정책은 장치에 업데이트가 적용되기 전에 사용자가 가지는 유예 기간을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="eaae7-161">또한 이 마감일 [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 정책은 사용자에게 알림을 트리거하여 장치에 필요한 변경 내용을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-161">This deadline policy also triggers [notifications](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="eaae7-162">장치에 대한 업데이트 지연 기간</span><span class="sxs-lookup"><span data-stu-id="eaae7-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="eaae7-163">이 정책은 각 업데이트 관리 장치 그룹에 대해 다르게 구성됩니다. 이 정책은 Microsoft Managed Desktop 대상을 충족하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="eaae7-164">테스트: 제로 일</span><span class="sxs-lookup"><span data-stu-id="eaae7-164">Test: zero days</span></span>
- <span data-ttu-id="eaae7-165">첫 번째: 제로 일</span><span class="sxs-lookup"><span data-stu-id="eaae7-165">First: zero days</span></span>
- <span data-ttu-id="eaae7-166">빠른 7일</span><span class="sxs-lookup"><span data-stu-id="eaae7-166">Fast 7 days</span></span>
- <span data-ttu-id="eaae7-167">광범위: 21일</span><span class="sxs-lookup"><span data-stu-id="eaae7-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="eaae7-168">알림 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="eaae7-168">Update notifications settings</span></span>

<span data-ttu-id="eaae7-169">**기본값:** False</span><span class="sxs-lookup"><span data-stu-id="eaae7-169">**Default value**: False</span></span>

<span data-ttu-id="eaae7-170">"업데이트 알림 숨기기" 설정은 Microsoft Managed Desktop 업데이트가 필요한 경우 사용자에게 알리는 [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 최상의 업데이트 환경을 제공하기 위해 모든 장치에서 **False로** 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="eaae7-171">업데이트를 찾을 위치 지정</span><span class="sxs-lookup"><span data-stu-id="eaae7-171">Specify a location to look for updates</span></span>

<span data-ttu-id="eaae7-172">**기본값: 월별** Enterprise 채널</span><span class="sxs-lookup"><span data-stu-id="eaae7-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="eaae7-173">**UpdatePath** 및 **UpdateChannel** 정책의 조합은 업데이트 일정을 달성하기 위해 필요한 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="eaae7-174">이러한 정책은 모든 Office 장치가 월별 채널의 CDN 업데이트를 Enterprise 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="eaae7-175">대상 버전의 사용자 지정 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="eaae7-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="eaae7-176">대상 버전 정책은 경우에 따라 특정 Microsoft Managed Desktop 버전을 롤백하거나 고정하기 위해 Office.</span><span class="sxs-lookup"><span data-stu-id="eaae7-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="eaae7-177">자동 업데이트를 사용하도록 설정하거나 사용하지 않도록 설정하는 Office 숨기기</span><span class="sxs-lookup"><span data-stu-id="eaae7-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="eaae7-178">**기본값:** 사용</span><span class="sxs-lookup"><span data-stu-id="eaae7-178">**Default value**: Enabled</span></span>

<span data-ttu-id="eaae7-179">이 설정은 Microsoft Managed Desktop 응용 프로그램에 대한 업데이트 대상을 충족하는 Microsoft 365 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="eaae7-180">첫 실행 설정</span><span class="sxs-lookup"><span data-stu-id="eaae7-180">First run settings</span></span> 

<span data-ttu-id="eaae7-181">처음 실행될 때 동작에 영향을 주는 몇 가지 Office 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="eaae7-182">최종 사용자를 대신하여 사용 조건에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="eaae7-183">**기본값:** 사용 안 하게</span><span class="sxs-lookup"><span data-stu-id="eaae7-183">**Default value**: Disabled</span></span>

<span data-ttu-id="eaae7-184">사용자가 Microsoft 365 앱을 처음 열면 사용 조건에 동의하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="eaae7-185">사용자를 대신하여 사용 조건에 동의하려는 경우 Microsoft Managed Desktop Operations 팀에 이 설정을 사용하도록 요청하는 서비스 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="eaae7-186">모바일 Outlook 확인란 표시 안 함</span><span class="sxs-lookup"><span data-stu-id="eaae7-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="eaae7-187">**기본값:** 사용 안 하게</span><span class="sxs-lookup"><span data-stu-id="eaae7-187">**Default value**: Disabled</span></span>

<span data-ttu-id="eaae7-188">사용자가 모바일을 처음으로 Outlook 모바일을 설치하라는 메시지가 Outlook 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="eaae7-189">사용자에게 해당 확인란을 표시하지 못하게 하려는 경우 Microsoft Managed Desktop Operations 팀에 이 설정을 사용하도록 설정해달고 요청하여 서비스 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="eaae7-190">기타 설정</span><span class="sxs-lookup"><span data-stu-id="eaae7-190">Other settings</span></span>

<span data-ttu-id="eaae7-191">사용자 대신 Microsoft 365 구성할 Microsoft Managed Desktop 수 있는 다른 앱 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="eaae7-192">개인 정보 보호 OneDrive</span><span class="sxs-lookup"><span data-stu-id="eaae7-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="eaae7-193">**기본값:** 사용 안 하게</span><span class="sxs-lookup"><span data-stu-id="eaae7-193">**Default value**: Disabled</span></span>

<span data-ttu-id="eaae7-194">일부 조직에서는 사용자가 장치에서 회사 파일과 개인 파일에 모두 액세스할 수 있는 사용자가 우려합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="eaae7-195">이 설정을 사용하도록 요청하는 Microsoft Managed Desktop 작업 팀에 서비스 요청을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="eaae7-196">설정 관리</span><span class="sxs-lookup"><span data-stu-id="eaae7-196">Settings you manage</span></span>

<span data-ttu-id="eaae7-197">다른 여러 정책이 Microsoft Managed Desktop 아직 서비스의 일부로 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="eaae7-198">클라우드 정책 서비스를 사용하는 Microsoft Intune 사용하여 이러한 정책을 Office [수](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="eaae7-199">이러한 정책을 설정하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="eaae7-200">Microsoft Endpoint Manager 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="eaae7-201">앱 **앱 > 정책 Office 만들기를 > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eaae7-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="eaae7-202">정책 **구성 만들기** 페이지에서 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="eaae7-203">이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-203">Enter a name.</span></span>
    - <span data-ttu-id="eaae7-204">설명을 제공합니다(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="eaae7-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="eaae7-205">**할당에서** 해당 정책을 모든 사용자 또는 엔터프라이즈용 Microsoft 365 앱 익명으로 액세스하는 사용자에게만 해당 정책을 적용하는지 웹용 Office.</span><span class="sxs-lookup"><span data-stu-id="eaae7-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="eaae7-206">정책 구성에 할당된 AAD 기반 보안 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="eaae7-207">각 정책 구성은 하나의 그룹에만 할당할 수 있으며 각 그룹에는 하나의 정책 구성만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="eaae7-208">정책 구성에 포함될 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="eaae7-209">정책 설정 이름을 검색하여 구성할 정책 설정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="eaae7-210">또한 응용 프로그램, 정책이 권장되는 보안 기준인지 여부 및 정책이 구성되어 있는지 여부를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="eaae7-211">플랫폼 열은 정책이 엔터프라이즈용 Microsoft 365 앱 장치, Windows 또는 모두에 웹용 Office 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eaae7-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="eaae7-212">선택한 후 만들기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eaae7-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="eaae7-213">Office 구성 정책은 사용자 기반 배포만 지원</span><span class="sxs-lookup"><span data-stu-id="eaae7-213">Office Configuration Policies only support user-based deployment</span></span>