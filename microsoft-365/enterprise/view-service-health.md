---
title: Microsoft 365 서비스 상태 확인 방법
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: 활성 서비스 중단이 Microsoft 365 지원 서비스에 문의하기 전에 서비스 상태를 봐야 합니다.
ms.openlocfilehash: 95ab260b4950d261eed1288b8fdf1f59883ff15f
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300408"
---
# <a name="how-to-check-microsoft-365-service-health"></a><span data-ttu-id="fca5c-103">Microsoft 365 서비스 상태 확인 방법</span><span class="sxs-lookup"><span data-stu-id="fca5c-103">How to check Microsoft 365 service health</span></span>

<span data-ttu-id="fca5c-104">[![관리 센터가 변경되고 있음을 알리는 레이블이며 aka.ms/aboutM365preview에서 자세한 내용을 확인할 수 있습니다.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="fca5c-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span></span>

<span data-ttu-id="fca5c-105">Microsoft 서비스 서비스 상태 페이지의 서비스 상태 페이지에서 웹용 Office, Yammer, Microsoft Dynamics CRM 및 모바일 장치 관리 클라우드 서비스를 비롯한  [Microsoft 365 관리 센터.](https://go.microsoft.com/fwlink/p/?linkid=2024339)</span><span class="sxs-lookup"><span data-stu-id="fca5c-105">You can view the health of your Microsoft services, including Office on the web, Yammer, Microsoft Dynamics CRM, and mobile device management cloud services, on the **Service health** page in the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).</span></span> <span data-ttu-id="fca5c-106">클라우드 서비스와 관련된 문제가 발생한 경우 지원 서비스에 문의하거나 문제 해결에 시간을 소비하기 전에 먼저 서비스 상태를 확인하여 이 문제가 현재 해결이 진행 중인 상태인 알려진 문제인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-106">If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.</span></span>

<span data-ttu-id="fca5c-107">관리 센터에 로그인할 수 없는 경우 서비스 상태 [](https://status.office365.com) 페이지를 사용하여 테넌트에 로그인하지 못하게 하는 알려진 문제를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-107">If you are unable to sign in to the admin center, you can use the [service status page](https://status.office365.com) to check for known issues preventing you from logging into your tenant.</span></span>  <span data-ttu-id="fca5c-108">또한 Twitter의 @MSFT365status [](https://twitter.com/MSFT365Status) 팔로우하여 특정 이벤트에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-108">Also sign up to follow us at [@MSFT365status](https://twitter.com/MSFT365Status) on Twitter to see information on certain events.</span></span>

## <a name="how-to-check-service-health"></a><span data-ttu-id="fca5c-109">서비스 상태 확인 방법</span><span class="sxs-lookup"><span data-stu-id="fca5c-109">How to check service health</span></span>

1. <span data-ttu-id="fca5c-110">의 Microsoft 365 관리 센터 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) 으로 이동하고 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-110">Go to the Microsoft 365 admin center at [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339), and sign in with an admin account.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fca5c-111">전역 관리자 또는 서비스 지원 관리자 역할이 할당된 사용자는 서비스 상태 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-111">People who are assigned the global admin or service support admin role can view service health.</span></span> <span data-ttu-id="fca5c-112">Exchange, SharePoint 및 비즈니스용 Skype 관리자가 서비스 상태를 볼 수 있도록 하려면 이러한 관리자에게도 서비스 관리자 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-112">To allow Exchange, SharePoint, and Skype for Business admins to view service health, they must also be assigned the Service admin role.</span></span> <span data-ttu-id="fca5c-113">서비스 상태 볼 수 있는 역할에 대한 자세한 내용은 관리자 역할 [정보를 참조하세요.](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)</span><span class="sxs-lookup"><span data-stu-id="fca5c-113">For more information about roles that can view service health, see [About admin roles](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles).</span></span>

2. <span data-ttu-id="fca5c-114">서비스 상태 보기를 위해 관리 센터에서 상태 서비스 상태로 이동하거나 홈 대시보드에서 서비스 상태   >   **카드를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="fca5c-114">To view service health, in the admin center, go to **Health** > **Service health**, or select the **Service health** card on the **Home dashboard**.</span></span> <span data-ttu-id="fca5c-115">대시보드 카드는 활성 서비스 문제가 있는지 여부와 자세한 서비스 상태 페이지에 대한 **링크를** 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-115">The dashboard card indicates whether there is an active service issue and links to the detailed **Service health** page.</span></span>

3. <span data-ttu-id="fca5c-116">서비스 **상태 페이지에서** 각 클라우드 서비스의 상태는 표 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-116">On the **Service health** page, the health state of each cloud service is shown in a table format.</span></span>

   ![View of current issues in service health](../media/service-health-all-services.png)

<span data-ttu-id="fca5c-118">모든 **서비스 탭(기본** 보기)에는 모든 서비스, 해당 현재 상태 및 활성 인시던트 또는 권고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-118">The **All services** tab (the default view) shows all services, their current health state, and any active incidents or advisories.</span></span> <span data-ttu-id="fca5c-119">상태 열의 아이콘 및 **상태는** 각 서비스의 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-119">An icon and status in the **Health** column indicate the state of each service.</span></span>

<span data-ttu-id="fca5c-120">서비스에 대한 활성 인시던트 또는 권고가 있는 경우 중첩된 테이블의 서비스 이름 바로 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-120">If there is an active incident or advisory for a service they will be listed directly under the service name in a nested table.</span></span> <span data-ttu-id="fca5c-121">중첩된 테이블을 축소하여 서비스 이름 왼쪽에 있는 chevron 아이콘을 클릭하여 이 보기에서 인시던트 또는 권고를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-121">You can collapse the nested table to hide the incidents or advisories in this view by clicking on the chevron icon to the left of the service name.</span></span>   

<span data-ttu-id="fca5c-122">보기를 필터링하여 모든 활성 인시던트만  표시하려면 페이지 위쪽의 인시던트 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-122">To filter your view to only show all the active incidents, select the **Incidents** tab at the top of the page.</span></span> <span data-ttu-id="fca5c-123">권고 **탭을 선택하면** 게시된 모든 활성 권고만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-123">Selecting the **Advisories** tab will only show all the active advisories posted.</span></span>

<span data-ttu-id="fca5c-124">기록 **탭에는** 지난 7일 또는 30일 이내에 해결된 모든 인시던트 및 권고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-124">The **History** tab shows all incidents and advisories that have been resolved within the last seven or 30 days.</span></span>

<span data-ttu-id="fca5c-125">Microsoft 365 서비스에서 문제가 발생하고 서비스 상태 페이지에 나열되지 않는 경우 문제  보고를 선택하고 짧은 양식을 완료하여 해당 서비스에 대해 알려 주세요.</span><span class="sxs-lookup"><span data-stu-id="fca5c-125">If you're experiencing an issue with a Microsoft 365 service and you don’t see it listed on the **Service health** page, tell us about it by selecting **Report an issue**, and completing the short form.</span></span> <span data-ttu-id="fca5c-126">다른 조직의 관련 데이터 및 보고서를 살펴보고 문제가 얼마나 광범위하고, 서비스가 시작된 경우를 살펴 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-126">We’ll look at related data and reports from other organizations to see how widespread the issue is, and if it originated with our service.</span></span> <span data-ttu-id="fca5c-127">이 경우 해결을 추적할 수 있는 서비스 상태 페이지에서  새 인시던트 또는 권고로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-127">If it did, we’ll add it as a new incident or advisory on the **Service health** page, where you can track its resolution.</span></span> <span data-ttu-id="fca5c-128">보고된 **문제** 페이지에는 테넌트가 이 양식에서 보고한 모든 문제와 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-128">The **Reported Issues** page will show all issues your tenant has reported from this form and the status.</span></span>

<span data-ttu-id="fca5c-129">대시보드에 표시되는 서비스의 보기를 사용자 지정하려면 기본 설정 사용자 지정 보기를 선택하고 서비스 상태 대시보드 보기에서 필터링할 서비스의 확인란 선택을   >  취소합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-129">To customize your view of which services show up on the dashboard, select **Preferences** > **Custom view**,  and clear the checkboxes for the services you want to filter out of your Service health dashboard view.</span></span> <span data-ttu-id="fca5c-130">모니터링할 각 서비스에 대해 확인란이 선택되어 있는지 확인란을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-130">Make sure that the checkbox is selected for each service that you want to monitor.</span></span>

<span data-ttu-id="fca5c-131">테넌트에 영향을 주는 새 인시던트 및 활성 인시던트에 대한 상태 변경에 대한 전자 메일 알림을 등록하려면 기본 설정 전자 메일을 선택하고 전자 메일로 서비스 열 알림 보내기 를 클릭한 후 다음을  >  지정합니다. </span><span class="sxs-lookup"><span data-stu-id="fca5c-131">To sign up for email notifications of new incidents that affect your tenant and status changes for an active incident, select **Preferences** > **Email**, click **Send me service heath notifications in email**, and then specify:</span></span>

- <span data-ttu-id="fca5c-132">최대 2개의 전자 메일 주소.</span><span class="sxs-lookup"><span data-stu-id="fca5c-132">Up to two email addresses.</span></span>
- <span data-ttu-id="fca5c-133">인시던트 또는 권고에 대한 알림을 원하는지 여부</span><span class="sxs-lookup"><span data-stu-id="fca5c-133">Whether you want notifications for incidents or advisories</span></span>
- <span data-ttu-id="fca5c-134">알림을 원하는 서비스</span><span class="sxs-lookup"><span data-stu-id="fca5c-134">The services for which you want notification</span></span>

<span data-ttu-id="fca5c-135">서비스의 모든 이벤트 대신 개별 이벤트에 대한 전자 메일 알림을 구독할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-135">You can also subscribe to email notifications for individual events instead of every event for a service.</span></span> <span data-ttu-id="fca5c-136">이렇게하려면 전자 메일 알림 업데이트를 받을 활성 문제를 선택하고 이 문제의 알림 관리를 선택한 후 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-136">To do so, select the active issue you want to receive email notification updates for, select **Manage notifications for this issue**, and then specify:</span></span> 
- <span data-ttu-id="fca5c-137">최대 2개의 전자 메일 주소.</span><span class="sxs-lookup"><span data-stu-id="fca5c-137">Up to two email addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="fca5c-138">각 관리자는 기본 설정을 사용할 수 있으며 위의 두 전자 메일 주소 제한은 관리자 계정당입니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-138">Each admin can have their Preferences set and the above limit of two email address is per admin account.</span></span>

> [!TIP]
> <span data-ttu-id="fca5c-139">모바일 장치에서 Microsoft 365 관리 [](https://go.microsoft.com/fwlink/p/?linkid=627216) 앱을 사용하여 서비스 상태(푸시 알림으로 최신 상태 유지)를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-139">You can also use the [Microsoft 365 Admin app](https://go.microsoft.com/fwlink/p/?linkid=627216) on your mobile device to view Service health, which is a great way to stay current with push notifications.</span></span>

### <a name="view-details-of-posted-service-health"></a><span data-ttu-id="fca5c-140">게시된 서비스 상태의 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="fca5c-140">View details of posted service health</span></span>

<span data-ttu-id="fca5c-141">모든 서비스 **보기에서** 문제 제목을 선택하여 해결 방법에서 작업하는 동안 게시된 모든 메시지의 피드를 포함하여 문제에 대한 자세한 정보를 표시하는 문제 세부 정보 페이지를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-141">On the **All services** view, select the issue title to see the issue detail page, which shows more information about the issue, including a feed of all the messages posted while we work on a solution.</span></span> 

<span data-ttu-id="fca5c-142">[![서비스 권고를 보여주는 스크린샷 ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="fca5c-142">[ ![A screenshot showing the service advisory](../media/service-health-advisory.png) ](../media/service-health-advisory.png#lightbox)</span></span>

<span data-ttu-id="fca5c-143">권고 또는 인시던트 요약은 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-143">The advisory or incident summary provides the following information:</span></span>

- <span data-ttu-id="fca5c-144">**title** - 문제의 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-144">**Title** - A summary of the problem.</span></span>
- <span data-ttu-id="fca5c-145">**ID** - 문제의 숫자 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-145">**ID** - A numeric identifier for the problem.</span></span>
- <span data-ttu-id="fca5c-146">**Service** - 영향을 받는 서비스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-146">**Service** - The name of the affected service.</span></span>
- <span data-ttu-id="fca5c-147">**Last updated** - 서비스 상태 메시지가 마지막으로 업데이트된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-147">**Last updated** - The last time that the service health message was updated.</span></span>
- <span data-ttu-id="fca5c-148">**예상 시작 시간** - 문제가 시작된 예상 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-148">**Estimated Start time** - The estimated time when the issue started.</span></span>
- <span data-ttu-id="fca5c-149">**Status** - 이 문제가 서비스에 미치는 영향.</span><span class="sxs-lookup"><span data-stu-id="fca5c-149">**Status** - How this problem affects the service.</span></span>
- <span data-ttu-id="fca5c-150">**사용자 영향** - 이 문제가 최종 사용자에게 미치는 영향에 대한 간략한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-150">**User Impact** - A brief description of the impact this issue has on the end user.</span></span>
- <span data-ttu-id="fca5c-151">**모든 업데이트** - 솔루션을 적용하는 진행 상황을 알려드렸다는 메시지를 자주 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-151">**All Updates** - We post frequent messages to let you know the progress that we're making in applying a solution.</span></span>

![문제 세부 정보를 보여주는 스크린샷](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a><span data-ttu-id="fca5c-153">서비스 상태 세부 정보 번역</span><span class="sxs-lookup"><span data-stu-id="fca5c-153">Translate service health details</span></span>

<span data-ttu-id="fca5c-154">기계 번역을 사용하여 원하는 언어로 메시지를 자동으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-154">We use machine translation to automatically display messages in your preferred language.</span></span> <span data-ttu-id="fca5c-155">언어를 [설정하는 방법에](/microsoft-365/admin/manage/language-translation-for-message-center-posts) 대한 자세한 내용은 메시지 센터 게시물의 언어 번역을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-155">Read [Language translation for Message center posts](/microsoft-365/admin/manage/language-translation-for-message-center-posts) for more information on how to set your language.</span></span>

### <a name="definitions"></a><span data-ttu-id="fca5c-156">정의</span><span class="sxs-lookup"><span data-stu-id="fca5c-156">Definitions</span></span>

<span data-ttu-id="fca5c-157">대부분의 경우 서비스는 추가 정보도 없는 정상으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-157">Most of the time, services will appear as healthy with no further information.</span></span> <span data-ttu-id="fca5c-158">서비스에 문제가 있으면 문제가 권고 또는 인시던트로 식별되고 현재 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-158">When a service is having a problem, the issue is identified as either an advisory or an incident and shows a current status.</span></span>

> [!TIP]
> <span data-ttu-id="fca5c-159">계획된 유지 관리 이벤트는 서비스 상태에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-159">Planned maintenance events aren't shown in service health.</span></span> <span data-ttu-id="fca5c-160">**메시지 센터** 를 통해 최신 상태를 유지함으로써 계획된 유지 관리 이벤트를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-160">You can track planned maintenance events by staying up to date with the **Message center**.</span></span> <span data-ttu-id="fca5c-161">변경 계획으로 분류된 메시지로 필터링하여 변경이 발생하는 시기, 해당 효과 및 이러한 변경에 대해 준비하는 방법을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fca5c-161">Filter to messages categorized as Plan for change to find out when the change is going to happen, its effect, and how to prepare for it.</span></span> <span data-ttu-id="fca5c-162">자세한 [내용은 Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) 메시지 센터를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-162">See [Message center in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) for more details.</span></span>

### <a name="incidents-and-advisories"></a><span data-ttu-id="fca5c-163">인시던트 및 권고</span><span class="sxs-lookup"><span data-stu-id="fca5c-163">Incidents and advisories</span></span>

| <span data-ttu-id="fca5c-164">아이콘</span><span class="sxs-lookup"><span data-stu-id="fca5c-164">Icon</span></span> | <span data-ttu-id="fca5c-165">설명</span><span class="sxs-lookup"><span data-stu-id="fca5c-165">Description</span></span> |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|<span data-ttu-id="fca5c-p114">서비스에 권고가 표시되면 Microsoft에서 일부 사용자에게 영향을 미치는 문제를 알고 있지만, 서비스를 계속 사용할 수는 있습니다. 권고에는 일반적으로 문제에 대한 해결 방법이 있으며, 문제가 일시적으로 발생하는 것일 수 있거나 범위 및 사용자 영향에서 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-p114">If a service has an advisory shown, we are aware of a problem that is affecting some users, but the service is still available. In an advisory, there is often a workaround to the problem and the problem may be intermittent or is limited in scope and user impact.</span></span>  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|<span data-ttu-id="fca5c-p115">서비스에 활성 인시던트가 표시되면 이 인시던트가 중요 문제이며 서비스 또는 서비스의 주요 기능을 사용할 수 없습니다. 예를 들어 사용자가 전자 메일을 보내고 받을 수 없거나 로그인할 수 없습니다. 인시던트는 사용자에게 눈에 띄는 영향을 줍니다. 진행 중인 인시던트가 있는 경우 서비스 상태 대시보드에서 조사, 완화 노력 및 해결 확인과 관련된 업데이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-p115">If a service has an active incident shown, it's a critical issue and the service or a major function of the service is unavailable. For example, users may be unable to send and receive email or unable to sign-in. Incidents will have noticeable impact to users. When there is an incident in progress, we will provide updates regarding the investigation, mitigation efforts, and confirmation of resolution in the Service health dashboard.</span></span>  <br/> |

### <a name="status-definitions"></a><span data-ttu-id="fca5c-174">상태 정의</span><span class="sxs-lookup"><span data-stu-id="fca5c-174">Status definitions</span></span>

| <span data-ttu-id="fca5c-175">상태</span><span class="sxs-lookup"><span data-stu-id="fca5c-175">Status</span></span> | <span data-ttu-id="fca5c-176">정의</span><span class="sxs-lookup"><span data-stu-id="fca5c-176">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="fca5c-177">**조사 중**</span><span class="sxs-lookup"><span data-stu-id="fca5c-177">**Investigating**</span></span> | <span data-ttu-id="fca5c-178">Microsoft에서 잠재적인 문제를 알고 있으며 문제의 상황과 영향의 범위에 대한 추가 정보를 수집하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-178">We're aware of a potential issue and are gathering more information about what's going on and the scope of impact.</span></span> |
|<span data-ttu-id="fca5c-179">**서비스 저하**</span><span class="sxs-lookup"><span data-stu-id="fca5c-179">**Service degradation**</span></span> | <span data-ttu-id="fca5c-p116">Microsoft에서 서비스 또는 기능 사용에 영향을 줄 수 있는 문제가 있음을 확인했습니다. 서비스가 평소보다 느리게 작동하거나, 일시적인 중단이 발생하거나, 기능이 작동하지 않는 등의 경우에 이 상태가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-p116">We've confirmed that there is an issue that may affect use of a service or feature. You might see this status if a service is performing more slowly than usual, there are intermittent interruptions, or if a feature isn't working, for example.</span></span> |
|<span data-ttu-id="fca5c-182">**서비스 중단**</span><span class="sxs-lookup"><span data-stu-id="fca5c-182">**Service interruption**</span></span> | <span data-ttu-id="fca5c-p117">문제가 사용자의 서비스 액세스 기능에 영향을 준다고 판단한 이 상태가 표시됩니다. 이 경우 문제가 중대하며 일관되게 재현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-p117">You'll see this status if we determine that an issue affects the ability for users to access the service. In this case, the issue is significant and can be reproduced consistently.</span></span> |
|<span data-ttu-id="fca5c-185">**서비스를 복원하는 중**</span><span class="sxs-lookup"><span data-stu-id="fca5c-185">**Restoring service**</span></span> | <span data-ttu-id="fca5c-186">문제의 원인이 식별되었으며, Microsoft에서 수행할 정정 작업을 알고 있고 서비스를 다시 정상 상태로 복원하는 프로세스를 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-186">The cause of the issue has been identified, we know what corrective action to take, and are in the process of bringing the service back to a healthy state.</span></span> |
|<span data-ttu-id="fca5c-187">**확장된 복구**</span><span class="sxs-lookup"><span data-stu-id="fca5c-187">**Extended recovery**</span></span> | <span data-ttu-id="fca5c-p118">이 상태는 대부분의 사용자에 대해 서비스를 복원하기 위한 정정 작업이 진행 중이지만, 영향을 받는 모든 시스템에 이를 적용하는 데 시간이 다소 소요될 것임을 나타냅니다. 영구적인 수정 사항을 적용하기 위해 대기하는 동안 영향을 줄이기 위해 임시 수정 사항을 적용한 경우에도 이 상태가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-p118">This status indicates that corrective action is in progress to restore service to most users but will take some time to reach all the affected systems. You might also see this status if we've made a temporary fix to reduce impact while we wait to apply a permanent fix.</span></span> |
|<span data-ttu-id="fca5c-190">**조사 일시 중단됨**</span><span class="sxs-lookup"><span data-stu-id="fca5c-190">**Investigation suspended**</span></span> | <span data-ttu-id="fca5c-p119">잠재적 문제에 대한 자세한 조사 결과, 추가 조사를 하기 위한 고객의 추가 정보가 필요한 경우 이 상태가 표시됩니다. 고객의 행동이 요구되는 경우 필요한 데이터나 로그를 알려드립니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-p119">If our detailed investigation of a potential issue results in a request for additional information from customers to allow us to investigate further, you'll see this status. If we need you to act, we'll let you know what data or logs we need.</span></span> |
|<span data-ttu-id="fca5c-193">**서비스 복원됨**</span><span class="sxs-lookup"><span data-stu-id="fca5c-193">**Service restored**</span></span> | <span data-ttu-id="fca5c-p120">Microsoft에서 정정 작업이 기본 문제를 해결했으며 서비스가 정상 상태로 복원되었음을 확인했습니다. 문제를 확인하려면 문제 세부 정보를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fca5c-p120">We've confirmed that corrective action has resolved the underlying problem and the service has been restored to a healthy state. To find out what went wrong, view the issue details.</span></span> |
|<span data-ttu-id="fca5c-196">**가긍성**</span><span class="sxs-lookup"><span data-stu-id="fca5c-196">**False positive**</span></span> | <span data-ttu-id="fca5c-197">자세한 조사가 끝날 때 서비스가 정상 상태인지와 설계에 따라 작동하고 있는 것으로 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-197">After a detailed investigation, we’ve confirmed the service is healthy and operating as designed.</span></span> <span data-ttu-id="fca5c-198">서비스에 대한 영향이 관찰되지 않았습니다. 또는 인시던트의 원인이 서비스 외부에서 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-198">No impact to the service was observed or the cause of the incident originated outside of the service.</span></span> |
|<span data-ttu-id="fca5c-199">**게시된 인시던트 사후 보고서**</span><span class="sxs-lookup"><span data-stu-id="fca5c-199">**Post-incident report published**</span></span> | <span data-ttu-id="fca5c-200">근본 원인 정보가 포함된 특정 문제와 유사한 문제가 다시 발생하지 않도록 하는 다음 단계가 포함된 인시던트 사후 보고서를 게시했습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-200">We’ve published a Post Incident Report for a specific issue that includes root cause information and next steps to ensure a similar issue doesn’t reoccur.</span></span> |

### <a name="message-post-types"></a><span data-ttu-id="fca5c-201">메시지 게시 유형</span><span class="sxs-lookup"><span data-stu-id="fca5c-201">Message Post Types</span></span>

| <span data-ttu-id="fca5c-202">유형</span><span class="sxs-lookup"><span data-stu-id="fca5c-202">Type</span></span> | <span data-ttu-id="fca5c-203">정의</span><span class="sxs-lookup"><span data-stu-id="fca5c-203">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="fca5c-204">**빠른 업데이트**</span><span class="sxs-lookup"><span data-stu-id="fca5c-204">**Quick Update**</span></span> | <span data-ttu-id="fca5c-205">모든 고객이 사용할 수 있는 광범위하게 영향을 미치는 인시던트에 대한 짧고 빈번한 증분 업데이트.</span><span class="sxs-lookup"><span data-stu-id="fca5c-205">Short and frequent incremental updates for broadly impacting incidents, available to all customers.</span></span> |
|<span data-ttu-id="fca5c-206">**추가 세부 정보**</span><span class="sxs-lookup"><span data-stu-id="fca5c-206">**Additional Details**</span></span> | <span data-ttu-id="fca5c-207">이러한 추가 게시물은 더욱 풍부한 기술 및 해결 세부 정보를 제공하여 인시던트 처리에 대한 더 깊은 가시성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-207">These additional posts will provide richer technical and resolution details to offer deeper visibility into the handling of incidents.</span></span> <span data-ttu-id="fca5c-208">모니터링 에 대해 설명한 동일한 요구 사항을 충족하는 [테넌트에 Exchange Online 있습니다.](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements)</span><span class="sxs-lookup"><span data-stu-id="fca5c-208">This is available for tenants that meet the same requirements outlined for [Exchange Online monitoring](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements),</span></span> |

### <a name="history"></a><span data-ttu-id="fca5c-209">기록</span><span class="sxs-lookup"><span data-stu-id="fca5c-209">History</span></span>

<span data-ttu-id="fca5c-210">서비스 상태를 통해 현재 상태를 보고 지난 30일 동안 테넌트에 영향을 미쳤던 모든 서비스 권고 및 인시던트의 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-210">Service health lets you look at your current health status and view the history of any service advisories and incidents that have affected your tenant in the past 30 days.</span></span> <span data-ttu-id="fca5c-211">모든 서비스의 지난 상태는 기록 **보기를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fca5c-211">To view the past health of all services, select **History** view.</span></span>

<span data-ttu-id="fca5c-212">가동 시간 약속에 대한 자세한 내용은 에서 투명한 작업을 [Microsoft 365.](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)</span><span class="sxs-lookup"><span data-stu-id="fca5c-212">For more information about our commitment to uptime, see [Transparent operations from Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fca5c-213">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fca5c-213">Related topics</span></span>

[<span data-ttu-id="fca5c-214">보고서의 활동 Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="fca5c-214">Activity Reports in the Microsoft 365 admin center</span></span>](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[<span data-ttu-id="fca5c-215">메시지 센터 기본 설정</span><span class="sxs-lookup"><span data-stu-id="fca5c-215">Message center Preferences</span></span>](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[<span data-ttu-id="fca5c-216">관리 센터에서 Windows 릴리스 상태 확인 방법</span><span class="sxs-lookup"><span data-stu-id="fca5c-216">How to check Windows release health on admin center</span></span>](/windows/deployment/update/check-release-health)
