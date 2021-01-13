---
title: 엔터프라이즈용 Microsoft 365 앱
description: Microsoft 365 앱을 배포하는 방법, 앱 업데이트 방법 및 설정 관리 방법
keywords: 변경 내용
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840352"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="7d209-104">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="7d209-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="7d209-105">초기 배포</span><span class="sxs-lookup"><span data-stu-id="7d209-105">Initial deployment</span></span>

<span data-ttu-id="7d209-106">Microsoft Managed Desktop을 사용하면 엔터프라이즈용 Microsoft 365 앱(64비트)이 모든 프로그램 디바이스에 이미지의 일부로 [설치됩니다.](../service-description/device-list.md)</span><span class="sxs-lookup"><span data-stu-id="7d209-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="7d209-107">다음 응용 프로그램이 모두 전달될 때 디바이스에 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="7d209-108">Word</span><span class="sxs-lookup"><span data-stu-id="7d209-108">Word</span></span>
- <span data-ttu-id="7d209-109">Excel</span><span class="sxs-lookup"><span data-stu-id="7d209-109">Excel</span></span>
- <span data-ttu-id="7d209-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7d209-110">PowerPoint</span></span>
- <span data-ttu-id="7d209-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="7d209-111">Outlook</span></span>
- <span data-ttu-id="7d209-112">게시자</span><span class="sxs-lookup"><span data-stu-id="7d209-112">Publisher</span></span>
- <span data-ttu-id="7d209-113">Access</span><span class="sxs-lookup"><span data-stu-id="7d209-113">Access</span></span>
- <span data-ttu-id="7d209-114">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="7d209-114">Skype for Business</span></span>
- <span data-ttu-id="7d209-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="7d209-115">OneNote</span></span>

<span data-ttu-id="7d209-116">이 방법은 네트워크에 미치는 영향을 최소화하고 사용자가 장치를 받는 즉시 생산성을 확보할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="7d209-117">그런 다음 사용할 응용 프로그램을 설정하기 위해 관리되는 장치에 더 많은 정책을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="7d209-118">Microsoft Teams는 엔터프라이즈용 Microsoft 365 앱과 별도로 배포됩니다. 기본 이미지에는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="7d209-119">사용자가 사용할 수 있는 배포</span><span class="sxs-lookup"><span data-stu-id="7d209-119">Available deployment to users</span></span>

<span data-ttu-id="7d209-120">사용자에게 어떤 이유로든 장치에 Microsoft 365 앱이 없는 경우 패키지를 사용하여 디바이스를 예상 상태로 되 돌아올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="7d209-121">최신 **Workplace-Office-Office365_Install** 그룹에 사용자를 추가하면 회사 포털에서 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="7d209-122">엔터프라이즈용 Microsoft 365 앱(32비트)</span><span class="sxs-lookup"><span data-stu-id="7d209-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="7d209-123">Microsoft Managed Desktop은 엔터프라이즈용 M365 앱의 32비트 버전 배포를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="7d209-124">Microsoft 365 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="7d209-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="7d209-125">Microsoft 365 앱은 월별 엔터프라이즈 채널에서 [업데이트로 설정됩니다.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)</span><span class="sxs-lookup"><span data-stu-id="7d209-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="7d209-126">이 방법은 매월 사용자에게 새로운 Office 기능을 제공하지만 예측 가능한 릴리스 일정에 따라 매월 하나의 업데이트만 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="7d209-127">업데이트는 두 번째 화요일에 릴리스됩니다. 이러한 업데이트에는 기능, 보안 및 품질 업데이트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="7d209-128">이러한 업데이트는 자동으로 발생하며 해당 특정 채널에 대한 Office CDN에서 직접 끌어오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="7d209-129">Microsoft Managed Desktop은 각 릴리스에 시차를 두어 환경의 잠재적인 문제를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="7d209-130">Microsoft 365 앱 제품 그룹에서 릴리스된 후 28일 후에 출시를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="7d209-131">Microsoft Managed Desktop은 다음과 같이 유효성 검사 및 테스트 시간을 허용하기 위해 서로 다른 그룹으로 업데이트 릴리스를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="7d209-132">테스트: 제로 일</span><span class="sxs-lookup"><span data-stu-id="7d209-132">Test: zero days</span></span>
- <span data-ttu-id="7d209-133">첫 번째: 제로 일</span><span class="sxs-lookup"><span data-stu-id="7d209-133">First: zero days</span></span>
- <span data-ttu-id="7d209-134">빠르기: 7일</span><span class="sxs-lookup"><span data-stu-id="7d209-134">Fast: 7 days</span></span>
- <span data-ttu-id="7d209-135">광범위: 21일</span><span class="sxs-lookup"><span data-stu-id="7d209-135">Broad: 21 days</span></span>

<span data-ttu-id="7d209-136">Microsoft Managed Desktop은 장치에 [](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 대한 업데이트 마감일을 7일로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="7d209-137">업데이트를 사용할 수 있는 경우 7일 이내에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="7d209-138">마감일 [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 12시간 전에 응용 프로그램, 시스템 트레이의 여러 위치에서 업데이트가 필요하다는 알림을 받게 되고 마감일 이전에 15분 동안 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="7d209-139">업데이트를 완료하려면 모든 Microsoft 365 앱을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="7d209-140">업데이트의 페이스킹 또는 롤백</span><span class="sxs-lookup"><span data-stu-id="7d209-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="7d209-141">어떤 이유로든 Microsoft 365 앱 업데이트를 일시 중지하거나 [](../working-with-managed-desktop/admin-support.md) 롤백해야 하는 경우 Microsoft Managed Desktop 포털을 통해 관리자 지원 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="7d209-142">릴리스 중에 Microsoft Managed Desktop은 모든 Microsoft 365 앱의 오류 비율을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="7d209-143">새 릴리스와 새 릴리스의 선행 버전 간 품질이 크게 다른 경우 Microsoft Managed Desktop Admin 포털을 통해 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="7d209-144">심각도에 따라 릴리스를 일시 중지할지 묻거나 문제를 완화하기 위한 조치를 취했다고 알려드릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="7d209-145">배달 최적화</span><span class="sxs-lookup"><span data-stu-id="7d209-145">Delivery optimization</span></span>

<span data-ttu-id="7d209-146">배달 최적화는 Windows 10에서 사용할 수 있는 피어 투 피어 배포 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="7d209-147">장치가 인터넷을 통해 Microsoft에서 다운로드한 업데이트와 같은 콘텐츠를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="7d209-148">장치를 사용하면 Microsoft에서 업데이트를 완전히 다운로드하지 않고도 로컬 네트워크의 다른 장치에서 업데이트의 일부를 얻을 수 있기 때문에 네트워크 대역폭을 줄이는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="7d209-149">[배달 최적화는](https://docs.microsoft.com/deployoffice/delivery-optimization) Windows 10 Enterprise 또는 Windows 10 Education 에디션을 실행하는 디바이스에서 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="7d209-150">Microsoft Managed Desktop에서 관리되는 설정</span><span class="sxs-lookup"><span data-stu-id="7d209-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="7d209-151">Microsoft는 서비스의 일부로 일부 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="7d209-152">Microsoft Managed Desktop은 Office 보안 기준을 관리하지 않지만 관리 섹션의 지침에 따라 직접 설정할 [수](#settings-you-manage) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="7d209-153">설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="7d209-153">Update settings</span></span>

<span data-ttu-id="7d209-154">Microsoft Managed Desktop은 [관리되는](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 장치에 대한 모든 업데이트 설정을 유지 관리하며 이러한 설정을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="7d209-155">자동으로 실행하도록 업데이트 설정</span><span class="sxs-lookup"><span data-stu-id="7d209-155">Set updates to occur automatically</span></span>

<span data-ttu-id="7d209-156">**기본값:** 사용</span><span class="sxs-lookup"><span data-stu-id="7d209-156">**Default value**: Enabled</span></span>

<span data-ttu-id="7d209-157">이 정책은 모든 Office 장치를 클라우드에서 최신으로 유지하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="7d209-158">업데이트를 적용해야 하는 마감일 설정</span><span class="sxs-lookup"><span data-stu-id="7d209-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="7d209-159">**기본값:** 7일</span><span class="sxs-lookup"><span data-stu-id="7d209-159">**Default value**: 7 days</span></span>

<span data-ttu-id="7d209-160">**UpdateDeadline** 정책은 장치에 업데이트가 적용되기 전에 사용자가 가지는 유예 기간을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="7d209-161">또한 이 마감일 [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 정책은 사용자에게 알림을 트리거하여 장치에 필요한 변경 내용을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="7d209-162">장치에서 기간 동안 업데이트 연기</span><span class="sxs-lookup"><span data-stu-id="7d209-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="7d209-163">이 정책은 각 업데이트 관리 장치 그룹에 대해 다르게 구성되고 Microsoft Managed Desktop이 업데이트 대상을 충족하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="7d209-164">테스트: 제로 일</span><span class="sxs-lookup"><span data-stu-id="7d209-164">Test: zero days</span></span>
- <span data-ttu-id="7d209-165">첫 번째: 제로 일</span><span class="sxs-lookup"><span data-stu-id="7d209-165">First: zero days</span></span>
- <span data-ttu-id="7d209-166">빠른 7일</span><span class="sxs-lookup"><span data-stu-id="7d209-166">Fast 7 days</span></span>
- <span data-ttu-id="7d209-167">광범위: 21일</span><span class="sxs-lookup"><span data-stu-id="7d209-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="7d209-168">알림 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="7d209-168">Update notifications settings</span></span>

<span data-ttu-id="7d209-169">**기본값:** False</span><span class="sxs-lookup"><span data-stu-id="7d209-169">**Default value**: False</span></span>

<span data-ttu-id="7d209-170">"업데이트 알림 숨기기" 설정은 Microsoft Managed Desktop 장치에서 **False로** 설정되어 [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 업데이트가 필요한 경우 사용자에게 알림하여 사용자에게 최상의 업데이트 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="7d209-171">업데이트를 찾을 위치 지정</span><span class="sxs-lookup"><span data-stu-id="7d209-171">Specify a location to look for updates</span></span>

<span data-ttu-id="7d209-172">**기본값:** 월별 엔터프라이즈 채널</span><span class="sxs-lookup"><span data-stu-id="7d209-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="7d209-173">**UpdatePath** 및 **UpdateChannel** 정책의 조합은 업데이트 일정을 달성하는 데 필요한 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="7d209-174">이러한 정책은 모든 Office 장치가 월별 엔터프라이즈 채널에 대한 CDN에서 직접 업데이트를 받게 하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="7d209-175">Microsoft 365 앱의 대상 버전 지정</span><span class="sxs-lookup"><span data-stu-id="7d209-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="7d209-176">대상 버전 정책은 특정 버전의 Office를 롤백하거나 고정하기 위해 Microsoft Managed Desktop에서 때때로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="7d209-177">Office 자동 업데이트를 사용 또는 사용하지 않도록 설정하는 옵션 숨기기</span><span class="sxs-lookup"><span data-stu-id="7d209-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="7d209-178">**기본값:** 사용</span><span class="sxs-lookup"><span data-stu-id="7d209-178">**Default value**: Enabled</span></span>

<span data-ttu-id="7d209-179">이 설정은 Microsoft Managed Desktop이 Microsoft 365 응용 프로그램에 대한 업데이트 대상을 충족하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="7d209-180">첫 실행 설정</span><span class="sxs-lookup"><span data-stu-id="7d209-180">First run settings</span></span> 

<span data-ttu-id="7d209-181">Office를 처음 실행할 때 동작에 영향을 주는 몇 가지 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="7d209-182">최종 사용자를 대신하여 사용 조건에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="7d209-183">**기본값:** 사용 안</span><span class="sxs-lookup"><span data-stu-id="7d209-183">**Default value**: Disabled</span></span>

<span data-ttu-id="7d209-184">사용자가 Microsoft 365 앱을 처음 열면 사용 조건에 동의하라는 메시지가 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="7d209-185">사용자를 대신하여 사용 조건에 동의하려는 경우 Microsoft Managed Desktop Operations 팀에 이 설정을 사용하도록 요청하는 서비스 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="7d209-186">Outlook 모바일 표시 안 함 확인란</span><span class="sxs-lookup"><span data-stu-id="7d209-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="7d209-187">**기본값:** 사용 안</span><span class="sxs-lookup"><span data-stu-id="7d209-187">**Default value**: Disabled</span></span>

<span data-ttu-id="7d209-188">사용자가 Outlook을 처음 열면 Outlook Mobile을 설치하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="7d209-189">사용자에게 해당 확인란을 표시하지 못하게 하려는 경우 Microsoft Managed Desktop Operations 팀에 장치에 대해 이 설정을 사용하도록 설정해달고 요청하는 서비스 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="7d209-190">기타 설정</span><span class="sxs-lookup"><span data-stu-id="7d209-190">Other settings</span></span>

<span data-ttu-id="7d209-191">Microsoft Managed Desktop이 선택적으로 사용자 대신 구성할 수 있는 다른 Microsoft 365 앱 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="7d209-192">개인 OneDrive를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="7d209-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="7d209-193">**기본값:** 사용 안</span><span class="sxs-lookup"><span data-stu-id="7d209-193">**Default value**: Disabled</span></span>

<span data-ttu-id="7d209-194">일부 조직에서는 사용자가 장치에서 회사 파일과 개인 파일에 모두 액세스할 수 있는 사용자가 우려합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="7d209-195">이 설정을 사용하도록 설정해달는 Microsoft Managed Desktop Operations 팀에 서비스 요청을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="7d209-196">관리하는 설정</span><span class="sxs-lookup"><span data-stu-id="7d209-196">Settings you manage</span></span>

<span data-ttu-id="7d209-197">Microsoft Managed Desktop이 아직 서비스의 일부로 설정하지 않은 다른 많은 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="7d209-198">Office 클라우드 정책 서비스를 사용하는 Microsoft Intune을 사용하여 이러한 정책을 [구성할 수](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="7d209-199">이러한 정책을 설정하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="7d209-200">Microsoft Endpoint Manager 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="7d209-201">만들기 **> Office 앱에** 대한 앱 > 선택</span><span class="sxs-lookup"><span data-stu-id="7d209-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="7d209-202">정책 구성 **만들기 페이지에서** 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="7d209-203">이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-203">Enter a name.</span></span>
    - <span data-ttu-id="7d209-204">설명을 입력합니다(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="7d209-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="7d209-205">**할당에서** 엔터프라이즈용 Microsoft 365 앱의 모든 사용자에게 해당 정책을 적용하는지 또는 웹용 Office를 사용하여 문서에 익명으로 액세스하는 사용자에게만 해당 정책을 적용하는지 여부를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d209-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="7d209-206">정책 구성에 할당된 AAD 기반 보안 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="7d209-207">각 정책 구성은 하나의 그룹에만 할당할 수 있으며 각 그룹에는 하나의 정책 구성만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="7d209-208">정책 구성에 포함될 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="7d209-209">정책 설정 이름을 검색하여 구성할 정책 설정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="7d209-210">또한 응용 프로그램, 정책이 권장되는 보안 기준인지 여부 및 정책이 구성되어 있는지 여부를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="7d209-211">플랫폼 열은 Windows 장치용 Microsoft 365 앱, 웹용 Office 또는 모든 엔터프라이즈용 Microsoft 365 앱에 정책이 적용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d209-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="7d209-212">선택한 후 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d209-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="7d209-213">Office 구성 정책은 사용자 기반 배포만 지원</span><span class="sxs-lookup"><span data-stu-id="7d209-213">Office Configuration Policies only support user-based deployment</span></span>
