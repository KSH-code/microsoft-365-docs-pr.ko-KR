---
title: 엔터프라이즈용 Microsoft 365 앱
description: Microsoft 365 앱을 배포 하는 방법, 업데이트 방식 및 설정 관리 방법
keywords: 변경 내용
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 767489ba9f9ac63bc1a2d8b4999b6634335b1aef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547749"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="8f749-104">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="8f749-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="8f749-105">초기 배포</span><span class="sxs-lookup"><span data-stu-id="8f749-105">Initial deployment</span></span>

<span data-ttu-id="8f749-106">Microsoft Managed Desktop은 모든 [프로그램 장치](../service-description/device-list.md)에서 Microsoft 365 Apps for enterprise (64 비트)가 이미지의 일부로 설치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="8f749-107">다음 응용 프로그램은 제공 될 때 장치에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="8f749-108">Word</span><span class="sxs-lookup"><span data-stu-id="8f749-108">Word</span></span>
- <span data-ttu-id="8f749-109">Excel</span><span class="sxs-lookup"><span data-stu-id="8f749-109">Excel</span></span>
- <span data-ttu-id="8f749-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8f749-110">PowerPoint</span></span>
- <span data-ttu-id="8f749-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="8f749-111">Outlook</span></span>
- <span data-ttu-id="8f749-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="8f749-112">Publisher</span></span>
- <span data-ttu-id="8f749-113">Access</span><span class="sxs-lookup"><span data-stu-id="8f749-113">Access</span></span>
- <span data-ttu-id="8f749-114">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="8f749-114">Skype for Business</span></span>
- <span data-ttu-id="8f749-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="8f749-115">OneNote</span></span>

<span data-ttu-id="8f749-116">이 방법을 사용 하면 네트워크 영향을 최소화 하 고 사용자가 장치를 수신 하는 즉시 생산성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="8f749-117">그런 다음 추가 정책을 관리 되는 장치에 배포 하 여 사용할 응용 프로그램을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-117">We then deploy additional policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="8f749-118">Microsoft 팀은 Microsoft 365 앱 for enterprise와 별도로 배포 되며, 기본 이미지에는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="8f749-119">사용자에 게 제공 되는 배포</span><span class="sxs-lookup"><span data-stu-id="8f749-119">Available deployment to users</span></span>

<span data-ttu-id="8f749-120">어떤 이유로 든 사용자의 장치에 Microsoft 365 앱이 없는 경우 패키지를 사용 하 여 장치를 예상 상태로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="8f749-121">사용자를 **최신 직장의 Office Office365_Install** 그룹에 추가 하면 회사 포털에서 해당 앱을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="8f749-122">Microsoft 365 Apps for enterprise (32 비트)</span><span class="sxs-lookup"><span data-stu-id="8f749-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="8f749-123">Microsoft Managed Desktop은 32 비트 버전의 M365 앱 배포를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="8f749-124">Microsoft 365 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="8f749-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="8f749-125">Microsoft 365 앱은 [월별 엔터프라이즈 채널](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)에서 업데이트 되도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="8f749-126">이 방법을 사용 하면 매달 새로운 Office 기능을 제공할 수 있지만 예측 가능한 릴리스 일정에는 월별 업데이트가 하나씩만 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="8f749-127">업데이트는 해당 월의 두 번째 화요일에 릴리스됩니다. 이러한 업데이트에는 기능, 보안 및 품질 업데이트가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="8f749-128">이러한 업데이트는 자동으로 실행 되며 해당 특정 채널에 대 한 Office CDN에서 직접 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="8f749-129">Microsoft Managed Desktop은 각 staggers 해당 환경에서 발생할 수 있는 문제를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="8f749-130">Microsoft 365 앱 제품 그룹의 릴리스 28 일 후에 출시 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="8f749-131">Microsoft Managed Desktop은 다음과 같은 유효성 검사 및 테스트에 대 한 시간을 허용 하도록 다른 그룹으로 릴리스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="8f749-132">테스트: 0 일</span><span class="sxs-lookup"><span data-stu-id="8f749-132">Test: 0 days</span></span>
- <span data-ttu-id="8f749-133">먼저: 0 일</span><span class="sxs-lookup"><span data-stu-id="8f749-133">First: 0 days</span></span>
- <span data-ttu-id="8f749-134">빠름: 7 일</span><span class="sxs-lookup"><span data-stu-id="8f749-134">Fast: 7 days</span></span>
- <span data-ttu-id="8f749-135">광범위: 21 일</span><span class="sxs-lookup"><span data-stu-id="8f749-135">Broad: 21 days</span></span>

<span data-ttu-id="8f749-136">Microsoft Managed Desktop은 장치에 대 한 7 일 동안의 [업데이트 마감 날짜](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="8f749-137">업데이트를 사용할 수 있게 되 면 7 일 이내에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="8f749-138">사용자에 [게는 여러](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 위치 (응용 프로그램)에서 최종 기한 이전의 시스템 용지함 12 시간에 대 한 업데이트가 필요 하며 기한 이전의 15 분 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="8f749-139">업데이트를 완료 하려면 모든 Microsoft 365 앱을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="8f749-140">업데이트 일시 중지 또는 롤백</span><span class="sxs-lookup"><span data-stu-id="8f749-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="8f749-141">어떤 이유로 든 Microsoft 365 앱 업데이트를 일시 중지 하거나 롤백해야 하는 경우 Microsoft Managed Desktop portal을 통해 [관리자 지원 요청](../working-with-managed-desktop/admin-support.md) 을 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="8f749-142">릴리스 중에 Microsoft Managed Desktop은 모든 Microsoft 365 앱의 오류율을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="8f749-143">새 릴리스와 이전 버전의 선행 작업과 중요 한 품질이 큰 차이를 확인 하는 경우 Microsoft Managed Desktop Administration portal을 통해 사용자에 게 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="8f749-144">심각도에 따라 릴리스를 일시 중지할 것인지, 아니면 문제를 완화 하기 위해 조치를 취하는 것을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="8f749-145">배달 최적화</span><span class="sxs-lookup"><span data-stu-id="8f749-145">Delivery optimization</span></span>

<span data-ttu-id="8f749-146">배달 최적화는 Windows 10에서 사용할 수 있는 피어 투 피어 배포 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="8f749-147">이를 통해 장치에서 인터넷을 통해 Microsoft 로부터 다운로드 한 콘텐츠 (예: 업데이트)를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="8f749-148">따라서 장치는 Microsoft에서 완전히 업데이트를 다운로드 하는 대신 로컬 네트워크의 다른 장치에서 업데이트의 일부를 가져올 수 있으므로 네트워크 대역폭을 줄이는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-148">This can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="8f749-149">Windows 10 Enterprise 또는 Windows 10 교육용 버전을 실행 하는 장치에서 [배달 최적화](https://docs.microsoft.com/deployoffice/delivery-optimization) 가 기본적으로 사용 되도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="8f749-150">Microsoft Managed Desktop에서 관리 하는 설정</span><span class="sxs-lookup"><span data-stu-id="8f749-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="8f749-151">Microsoft는 일부 설정을 서비스의 일부로 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="8f749-152">Microsoft Managed Desktop은 Office 보안 기준을 관리 하지 않지만 사용자가 [관리 하는 설정](#settings-you-manage) 섹션의 지침에 따라 직접 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="8f749-153">업데이트 설정</span><span class="sxs-lookup"><span data-stu-id="8f749-153">Update settings</span></span>

<span data-ttu-id="8f749-154">Microsoft Managed Desktop은 관리 장치에 대 한 모든 [업데이트 설정을](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 유지 관리 하며, 이러한 설정을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="8f749-155">자동으로 실행하도록 업데이트 설정</span><span class="sxs-lookup"><span data-stu-id="8f749-155">Set updates to occur automatically</span></span>

<span data-ttu-id="8f749-156">**기본값**: Enabled</span><span class="sxs-lookup"><span data-stu-id="8f749-156">**Default value**: Enabled</span></span>

<span data-ttu-id="8f749-157">이 정책은 모든 Office 장치를 클라우드에서 최신 상태로 유지할 수 있도록 하기 위해 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="8f749-158">업데이트를 적용 해야 하는 마감 날짜 설정</span><span class="sxs-lookup"><span data-stu-id="8f749-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="8f749-159">**기본값**: 7 일</span><span class="sxs-lookup"><span data-stu-id="8f749-159">**Default value**: 7 days</span></span>

<span data-ttu-id="8f749-160">**Updatedeadline** policy는 사용자가 장치에 업데이트를 적용 하기 전에 보유 하는 유예 기간을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="8f749-161">또한이 기한 정책은 사용자에 게 장치에서 필요한 변경 사항을 알리는 [알림을](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="8f749-162">일정 기간 동안 장치에 대 한 업데이트 지연</span><span class="sxs-lookup"><span data-stu-id="8f749-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="8f749-163">이 정책은 각 업데이트 관리 장치 그룹에 대해 서로 다른 방식으로 구성 되며 Microsoft Managed Desktop이 해당 업데이트 목표를 충족 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="8f749-164">테스트: 0 일</span><span class="sxs-lookup"><span data-stu-id="8f749-164">Test: 0 days</span></span>
- <span data-ttu-id="8f749-165">먼저: 0 일</span><span class="sxs-lookup"><span data-stu-id="8f749-165">First: 0 days</span></span>
- <span data-ttu-id="8f749-166">Fast 7 일</span><span class="sxs-lookup"><span data-stu-id="8f749-166">Fast 7 days</span></span>
- <span data-ttu-id="8f749-167">광범위: 21 일</span><span class="sxs-lookup"><span data-stu-id="8f749-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="8f749-168">알림 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="8f749-168">Update notifications settings</span></span>

<span data-ttu-id="8f749-169">**기본값**: False</span><span class="sxs-lookup"><span data-stu-id="8f749-169">**Default value**: False</span></span>

<span data-ttu-id="8f749-170">Microsoft Managed Desktop 장치에서 "업데이트 알림 숨기기" 설정이 **False** 로 설정 되어 있으면 업데이트가 필요한 경우 사용자 [에 게 최적의](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 업데이트 환경이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="8f749-171">업데이트를 찾을 위치 지정</span><span class="sxs-lookup"><span data-stu-id="8f749-171">Specify a location to look for updates</span></span>

<span data-ttu-id="8f749-172">**기본값**: 월별 엔터프라이즈 채널</span><span class="sxs-lookup"><span data-stu-id="8f749-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="8f749-173">업데이트 일정을 달성 하기 위해 필요한 경우 **Updatepath** 및 **UpdateChannel** 정책의 조합이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="8f749-174">이러한 정책은 모든 Office 장치에서 월별 엔터프라이즈 채널에 대 한 CDN에서 직접 업데이트를 받도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="8f749-175">Microsoft 365 앱의 대상 버전 지정</span><span class="sxs-lookup"><span data-stu-id="8f749-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="8f749-176">특정 Office 버전을 롤백하거나 고정 하기 위해 Microsoft Managed Desktop에서 대상 버전 정책을 사용 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="8f749-177">Office 자동 업데이트를 사용 하거나 사용 하지 않도록 설정 하는 옵션 숨기기</span><span class="sxs-lookup"><span data-stu-id="8f749-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="8f749-178">**기본값**: Enabled</span><span class="sxs-lookup"><span data-stu-id="8f749-178">**Default value**: Enabled</span></span>

<span data-ttu-id="8f749-179">이 설정은 microsoft Managed Desktop이 Microsoft 365 응용 프로그램에 대 한 업데이트 목표를 충족 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="8f749-180">첫 번째 실행 설정</span><span class="sxs-lookup"><span data-stu-id="8f749-180">First run settings</span></span> 

<span data-ttu-id="8f749-181">Office를 처음 실행할 때의 동작에 영향을 주는 몇 가지 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="8f749-182">최종 사용자 대신 사용 조건에 동의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="8f749-183">**기본값**: 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="8f749-183">**Default value**: Disabled</span></span>

<span data-ttu-id="8f749-184">사용자가 Microsoft 365 앱을 처음 열 때 사용권 조항에 동의 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="8f749-185">사용자 대신 사용 조건에 동의 하려면 Microsoft Managed Desktop Operations 팀을 통해 서비스 요청을 사용 하도록 설정 하 라는 메시지를 파일에 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="8f749-186">Outlook 모바일 확인란 표시 안 함</span><span class="sxs-lookup"><span data-stu-id="8f749-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="8f749-187">**기본값**: 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="8f749-187">**Default value**: Disabled</span></span>

<span data-ttu-id="8f749-188">사용자가 Outlook을 처음 열 때 Outlook Mobile을 설치 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="8f749-189">사용자가 해당 확인란을 볼 수 없도록 하려면 Microsoft Managed Desktop Operations 팀을 통해 서비스 요청이 장치에 대해 사용 하도록 설정 되어 있는지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="8f749-190">기타 설정</span><span class="sxs-lookup"><span data-stu-id="8f749-190">Other settings</span></span>

<span data-ttu-id="8f749-191">Microsoft Managed Desktop에서 사용자 대신 선택적으로 구성할 수 있는 기타 Microsoft 365 앱 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="8f749-192">개인 OneDrive 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="8f749-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="8f749-193">**기본값**: 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="8f749-193">**Default value**: Disabled</span></span>

<span data-ttu-id="8f749-194">일부 조직에서는 사용자가 자신의 장치에서 회사 및 개인 파일에 모두 액세스 하는 것을 걱정 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="8f749-195">이 설정을 사용 하도록 설정 하려면 Microsoft Managed Desktop Operations 팀과 서비스 요청을 파일에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="8f749-196">관리 하는 설정</span><span class="sxs-lookup"><span data-stu-id="8f749-196">Settings you manage</span></span>

<span data-ttu-id="8f749-197">Microsoft Managed Desktop이 서비스의 일부로 아직 설정 되지 않은 다른 여러 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="8f749-198">[Office 클라우드 정책](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 서비스를 사용 하는 Microsoft Intune을 사용 하 여 이러한 구성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-198">You can configure these by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="8f749-199">이렇게 하려면 다음과 같이 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f749-199">To do this, follow these steps:</span></span>

1.  <span data-ttu-id="8f749-200">Microsoft Endpoint Manager 관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="8f749-201">**Office 앱에 대 한 앱 > 정책 > 만들기를 선택 합니다** .</span><span class="sxs-lookup"><span data-stu-id="8f749-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="8f749-202">정책 구성 **만들기** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="8f749-203">이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-203">Enter a name.</span></span>
    - <span data-ttu-id="8f749-204">설명을 입력 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="8f749-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="8f749-205">**할당**에서이 정책이 Microsoft 365 앱 enterprise 용 모든 사용자에 게 적용 되는지, 아니면 웹을 사용 하 여 Office를 통해 문서에 익명으로 액세스 하는 사용자에 게 적용할지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="8f749-206">정책 구성에 할당 된 AAD 기반 보안 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="8f749-207">각 정책 구성은 하나의 그룹에만 할당할 수 있으며 각 그룹에는 하나의 정책 구성만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="8f749-208">정책 구성에 포함할 정책 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="8f749-209">정책 설정 이름을 검색 하 여 구성할 정책 설정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="8f749-210">또한 정책이 권장 되는 보안 기준 인지 여부 및 정책이 구성 되었는지 여부에 따라 응용 프로그램에서 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="8f749-211">Platform 열에는 정책이 Windows 장치용 엔터프라이즈 용 Microsoft 365 앱, 웹을 위한 Office 또는 모두에 적용 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="8f749-212">선택한 후 **만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="8f749-213">Office 구성 정책만 사용자 기반 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f749-213">Office Configuration Policies only support user-based deployment</span></span>
