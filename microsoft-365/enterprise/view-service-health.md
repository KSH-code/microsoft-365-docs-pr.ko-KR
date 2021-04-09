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
description: 지원 서비스에 문의하기 전에 Microsoft 365 서비스의 상태를 확인하여 활성 서비스 중단이 있는지 확인할 수 있습니다.
ms.openlocfilehash: e0ab4eaa1f7a96168839a4abef2f0f254a21d0ad
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644635"
---
# <a name="how-to-check-microsoft-365-service-health"></a><span data-ttu-id="292f2-103">Microsoft 365 서비스 상태 확인 방법</span><span class="sxs-lookup"><span data-stu-id="292f2-103">How to check Microsoft 365 service health</span></span>

<span data-ttu-id="292f2-104">[![관리 센터가 변경되고 있음을 알리는 레이블이며 aka.ms/aboutM365preview에서 자세한 내용을 확인할 수 있습니다.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="292f2-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span></span>

<span data-ttu-id="292f2-105">웹용 Office, Yammer, Microsoft Dynamics CRM 및 모바일 장치 관리 클라우드 서비스를 비롯한 Microsoft 서비스의 상태는 Microsoft  [365](https://go.microsoft.com/fwlink/p/?linkid=2024339)관리 센터의 서비스 상태 페이지에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-105">You can view the health of your Microsoft services, including Office on the web, Yammer, Microsoft Dynamics CRM, and mobile device management cloud services, on the **Service health** page in the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).</span></span> <span data-ttu-id="292f2-106">클라우드 서비스와 관련된 문제가 발생한 경우 지원 서비스에 문의하거나 문제 해결에 시간을 소비하기 전에 먼저 서비스 상태를 확인하여 이 문제가 현재 해결이 진행 중인 상태인 알려진 문제인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-106">If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.</span></span>

<span data-ttu-id="292f2-107">관리 센터에 로그인할 수 없는 경우 서비스 상태 [](https://status.office365.com) 페이지를 사용하여 테넌트에 로그인하지 못하게 하는 알려진 문제를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-107">If you are unable to sign in to the admin center, you can use the [service status page](https://status.office365.com) to check for known issues preventing you from logging into your tenant.</span></span>  <span data-ttu-id="292f2-108">또한 Twitter의 @MSFT365status [](https://twitter.com/MSFT365Status) 팔로우하여 특정 이벤트에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-108">Also sign up to follow us at [@MSFT365status](https://twitter.com/MSFT365Status) on Twitter to see information on certain events.</span></span>

  
### <a name="how-to-check-service-health"></a><span data-ttu-id="292f2-109">서비스 상태 확인 방법</span><span class="sxs-lookup"><span data-stu-id="292f2-109">How to check service health</span></span>

1. <span data-ttu-id="292f2-110">의 Microsoft 365 관리 센터로 이동하고 관리자 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-110">Go to the Microsoft 365 admin center at [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339), and sign in with an admin account.</span></span>

    > [!NOTE]
    > <span data-ttu-id="292f2-111">전역 관리자 또는 서비스 지원 관리자 역할이 할당된 사용자는 서비스 상태 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-111">People who are assigned the global admin or service support admin role can view service health.</span></span> <span data-ttu-id="292f2-112">Exchange, SharePoint 및 비즈니스용 Skype 관리자가 서비스 상태를 볼 수 있도록 하려면 이러한 관리자에게도 서비스 관리자 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-112">To allow Exchange, SharePoint, and Skype for Business admins to view service health, they must also be assigned the Service admin role.</span></span> <span data-ttu-id="292f2-113">서비스 상태 볼 수 있는 역할에 대한 자세한 내용은 관리자 역할 [정보를 참조하세요.](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)</span><span class="sxs-lookup"><span data-stu-id="292f2-113">For more information about roles that can view service health, see [About admin roles](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles).</span></span>
  
2. <span data-ttu-id="292f2-114">새 관리 센터를 사용하지 않는 경우  홈 페이지에서  오른쪽 위에 있는 새 관리 센터 시도 토글을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-114">If you are not using the new admin center, on the **Home** page, select the **Try the new admin center** toggle in the upper-right corner.</span></span>

3. <span data-ttu-id="292f2-115">서비스 상태 보기를 위해 관리 센터에서 상태 서비스 상태로 이동하거나 홈 대시보드에서 서비스 상태   >   **카드를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="292f2-115">To view service health, in the admin center, go to **Health** > **Service health**, or select the **Service health** card on the **Home dashboard**.</span></span> <span data-ttu-id="292f2-116">대시보드 카드는 활성 서비스 문제가 있는지 여부와 자세한 서비스 상태 페이지에 대한 **링크를** 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-116">The dashboard card indicates whether there is an active service issue and links to the detailed **Service health** page.</span></span>
  
4. <span data-ttu-id="292f2-117">서비스 **상태 페이지에서** 각 클라우드 서비스의 상태는 표 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-117">On the **Service health** page, the health state of each cloud service is shown in a table format.</span></span>

   ![View of current issues in service health](../media/service-health-all-services.png)

<span data-ttu-id="292f2-119">모든 **서비스 탭(기본** 보기)에는 모든 서비스와 해당 현재 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-119">The **All services** tab (the default view) shows all services and their current health state.</span></span> <span data-ttu-id="292f2-120">아이콘과 **상태** 열은 각 서비스의 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-120">An icon and the **Status** column indicate the state of each service.</span></span> 

<span data-ttu-id="292f2-121">현재 인시던트가 발생하는 서비스로 보기를  필터링하려면 페이지 위쪽의 인시던트 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-121">To filter your view to services currently experiencing an incident, select the **Incidents** tab at the top of the page.</span></span> <span data-ttu-id="292f2-122">권고 **탭을 선택하면** 현재 권고가 게시된 서비스만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-122">Selecting the **Advisories** tab will show only services that currently have an advisory posted.</span></span> 

<span data-ttu-id="292f2-123">기록 **탭에는** 해결된 인시던트 및 권고 기록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-123">The **History** tab shows the history of incidents and advisories that have been resolved.</span></span>

<span data-ttu-id="292f2-124">Microsoft 365 서비스에서 문제가 발생하고 서비스 상태 페이지에 나열되어 있는  문제가 없는 경우 문제 보고 및 짧은 양식을 완료하여 해당 문제를 알려 주세요.</span><span class="sxs-lookup"><span data-stu-id="292f2-124">If you're experiencing an issue with a Microsoft 365 service and you don’t see it listed on the **Service health** page, tell us about it by selecting **Report an issue**, and completing the short form.</span></span> <span data-ttu-id="292f2-125">다른 조직의 관련 데이터 및 보고서를 살펴보고 문제가 얼마나 광범위하고, 서비스가 시작된 경우를 살펴 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-125">We’ll look at related data and reports from other organizations to see how widespread the issue is, and if it originated with our service.</span></span> <span data-ttu-id="292f2-126">이 경우 해결을 추적할 수 있는 서비스 상태 페이지에서  새 인시던트 또는 권고로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-126">If it did, we’ll add it as a new incident or advisory on the **Service health** page, where you can track its resolution.</span></span> <span data-ttu-id="292f2-127">약 30분 내에 목록에 나타나지 않으면 지원에 문의하여 문제를 해결하는 것이 가장 까다로우면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-127">If you don’t see it appear on the list within about 30 minutes, consider contacting support to resolve the issue.</span></span>

<span data-ttu-id="292f2-128">대시보드에 표시하는 서비스의 보기를 사용자 지정하려면 기본 설정 사용자 지정 보기를 선택하고 서비스 상태 대시보드 보기에서 필터링할 서비스의 확인란 선택을   >  취소합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-128">To customize your view of which services show up on the dashboard, select **Preferences** > **Custom view**,  and clear the check boxes for the services you want to filter out of your Service health dashboard view.</span></span> <span data-ttu-id="292f2-129">모니터링할 각 서비스에 대해 확인란이 선택되어 있는지 확인란을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-129">Make sure that the check box is selected for each service that you want to monitor.</span></span>    

<span data-ttu-id="292f2-130">테넌트에 영향을 주는 새 인시던트 및 활성 인시던트에 대한 상태 변경에 대한 전자 메일 알림을 등록하려면 기본 설정 전자 메일을 선택하고 전자 메일로 서비스 열 알림 보내기 를 클릭한 후 다음을  >  지정합니다. </span><span class="sxs-lookup"><span data-stu-id="292f2-130">To sign up for email notifications of new incidents that affect your tenant and status changes for an active incident, select **Preferences** > **Email**, click **Send me service heath notifications in email**, and then specify:</span></span>

- <span data-ttu-id="292f2-131">최대 2개의 전자 메일 주소.</span><span class="sxs-lookup"><span data-stu-id="292f2-131">Up to two email addresses.</span></span>
- <span data-ttu-id="292f2-132">인시던트 또는 권고에 대한 알림을 원하는지 여부</span><span class="sxs-lookup"><span data-stu-id="292f2-132">Whether you want notifications for incidents or advisories</span></span>
- <span data-ttu-id="292f2-133">알림을 원하는 서비스</span><span class="sxs-lookup"><span data-stu-id="292f2-133">The services for which you want notification</span></span>

> [!NOTE]
> <span data-ttu-id="292f2-134">각 관리자는 기본 설정을 사용할 수 있으며 위의 두 전자 메일 주소 제한은 관리자 계정당입니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-134">Each admin can have their Preferences set and the above limit of two email address is per admin account.</span></span>

> [!TIP]
> <span data-ttu-id="292f2-135">모바일 장치에서 [Microsoft 365 관리](https://go.microsoft.com/fwlink/p/?linkid=627216) 앱을 사용하여 서비스 상태도 볼 수 있습니다. 이는 푸시 알림을 사용하여 최신 정보를 유지 하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-135">You can also use the [Microsoft 365 Admin app](https://go.microsoft.com/fwlink/p/?linkid=627216) on your mobile device to view Service health, which is a great way to stay current with push notifications.</span></span> 
  
### <a name="view-details-of-posted-service-health"></a><span data-ttu-id="292f2-136">게시된 서비스 상태의 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="292f2-136">View details of posted service health</span></span>

<span data-ttu-id="292f2-137">모든 **서비스 보기에서** 서비스 상태를 선택하면 권고 또는 인시던트의 요약 보기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-137">On the **All services** view, selecting the service status will open a summary view of advisories or incidents.</span></span>
  
<span data-ttu-id="292f2-138">[![서비스 권고를 보여주는 스크린샷 ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="292f2-138">[ ![A screenshot showing the service advisory](../media/service-health-advisory.png) ](../media/service-health-advisory.png#lightbox)</span></span>

<span data-ttu-id="292f2-139">권고 또는 인시던트 요약은 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-139">The advisory or incident summary provides the following information:</span></span>

- <span data-ttu-id="292f2-140">**title** - 문제의 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-140">**Title** - A summary of the problem.</span></span>
- <span data-ttu-id="292f2-141">**Service** - 영향을 받는 서비스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-141">**Service** - The name of the affected service.</span></span>
- <span data-ttu-id="292f2-142">**ID** - 문제의 숫자 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-142">**ID** - A numeric identifier for the problem.</span></span>
- <span data-ttu-id="292f2-143">**Status** - 이 문제가 서비스에 미치는 영향.</span><span class="sxs-lookup"><span data-stu-id="292f2-143">**Status** - How this problem affects the service.</span></span>
- <span data-ttu-id="292f2-144">**시작 시간** - 문제가 시작된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-144">**Start time** - The time when the issue started.</span></span>
- <span data-ttu-id="292f2-145">**Last updated** - 서비스 상태 메시지가 마지막으로 업데이트된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-145">**Last updated** - The last time that the service health message was updated.</span></span> <span data-ttu-id="292f2-146">솔루션 적용 진행률을 알려주기 위해 자주 메시지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-146">We post frequent messages to let you know the progress that we're making in applying a solution.</span></span>

<span data-ttu-id="292f2-147">문제 제목을 선택하여 해결 방법에서 작업하는 동안 게시된 모든 [](#history) 메시지 기록을 포함하여 문제에 대한 자세한 정보를 표시하는 문제 세부 정보 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-147">Select the issue title to see the issue detail page, which shows more information about the issue, including the [history](#history) of all messages posted while we work on a solution.</span></span>

![문제 세부 정보를 보여주는 스크린샷](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a><span data-ttu-id="292f2-149">서비스 상태 세부 정보 번역</span><span class="sxs-lookup"><span data-stu-id="292f2-149">Translate service health details</span></span>

<span data-ttu-id="292f2-p110">서비스 상태 설명은 실시간으로 게시되므로 해당 언어로 자동 번역되지 않으며 서비스 이벤트의 세부 정보는 영어로만 제공됩니다. 설명을 번역하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-p110">Because service health explanations are posted in real-time, they are not automatically translated to your language and the details of a service event are in English only. To translate the explanation, follow these steps:</span></span>
  
1. <span data-ttu-id="292f2-152">1.[번역기](https://www.bing.com/translator/)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-152">Go to [Translator](https://www.bing.com/translator/).</span></span>

2. <span data-ttu-id="292f2-p111">**서비스 상태** 페이지에서 인시던트 또는 권고를 선택합니다. **세부 정보 표시** 아래에서 문제에 대한 텍스트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-p111">On the **Service health** page, select an incident or advisory. Under **Show details**, copy the text about the issue.</span></span>

3. <span data-ttu-id="292f2-155">번역기에서 텍스트를 붙여넣고 **번역하기** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-155">In Translator, paste the text and choose **Translate**.</span></span>

### <a name="definitions"></a><span data-ttu-id="292f2-156">정의</span><span class="sxs-lookup"><span data-stu-id="292f2-156">Definitions</span></span>

<span data-ttu-id="292f2-157">대부분의 경우 서비스는 추가 정보도 없는 정상으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-157">Most of the time, services will appear as healthy with no further information.</span></span> <span data-ttu-id="292f2-158">서비스에 문제가 있으면 문제가 권고 또는 인시던트로 식별되고 현재 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-158">When a service is having a problem, the issue is identified as either an advisory or an incident and shows a current status.</span></span>
  
> [!TIP]
> <span data-ttu-id="292f2-159">계획된 유지 관리 이벤트는 서비스 상태에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-159">Planned maintenance events aren't shown in service health.</span></span> <span data-ttu-id="292f2-160">**메시지 센터** 를 통해 최신 상태를 유지함으로써 계획된 유지 관리 이벤트를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-160">You can track planned maintenance events by staying up to date with the **Message center**.</span></span> <span data-ttu-id="292f2-161">변경 계획으로 분류된 메시지로 필터링하여 변경이 발생하는 시기, 해당 효과 및 이러한 변경에 대해 준비하는 방법을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="292f2-161">Filter to messages categorized as Plan for change to find out when the change is going to happen, its effect, and how to prepare for it.</span></span> <span data-ttu-id="292f2-162">자세한 [내용은 Microsoft 365의 메시지](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) 센터를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-162">See [Message center in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) for more details.</span></span>
  
### <a name="incidents-and-advisories"></a><span data-ttu-id="292f2-163">인시던트 및 권고</span><span class="sxs-lookup"><span data-stu-id="292f2-163">Incidents and advisories</span></span>

| <span data-ttu-id="292f2-164">아이콘</span><span class="sxs-lookup"><span data-stu-id="292f2-164">Icon</span></span> | <span data-ttu-id="292f2-165">설명</span><span class="sxs-lookup"><span data-stu-id="292f2-165">Description</span></span> |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|<span data-ttu-id="292f2-p114">서비스에 권고가 표시되면 Microsoft에서 일부 사용자에게 영향을 미치는 문제를 알고 있지만, 서비스를 계속 사용할 수는 있습니다. 권고에는 일반적으로 문제에 대한 해결 방법이 있으며, 문제가 일시적으로 발생하는 것일 수 있거나 범위 및 사용자 영향에서 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-p114">If a service has an advisory shown, we are aware of a problem that is affecting some users, but the service is still available. In an advisory, there is often a workaround to the problem and the problem may be intermittent or is limited in scope and user impact.</span></span>  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|<span data-ttu-id="292f2-p115">서비스에 활성 인시던트가 표시되면 이 인시던트가 중요 문제이며 서비스 또는 서비스의 주요 기능을 사용할 수 없습니다. 예를 들어 사용자가 전자 메일을 보내고 받을 수 없거나 로그인할 수 없습니다. 인시던트는 사용자에게 눈에 띄는 영향을 줍니다. 진행 중인 인시던트가 있는 경우 서비스 상태 대시보드에서 조사, 완화 노력 및 해결 확인과 관련된 업데이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-p115">If a service has an active incident shown, it's a critical issue and the service or a major function of the service is unavailable. For example, users may be unable to send and receive email or unable to sign-in. Incidents will have noticeable impact to users. When there is an incident in progress, we will provide updates regarding the investigation, mitigation efforts, and confirmation of resolution in the Service health dashboard.</span></span>  <br/> |

### <a name="status-definitions"></a><span data-ttu-id="292f2-174">상태 정의</span><span class="sxs-lookup"><span data-stu-id="292f2-174">Status definitions</span></span>

| <span data-ttu-id="292f2-175">상태</span><span class="sxs-lookup"><span data-stu-id="292f2-175">Status</span></span> | <span data-ttu-id="292f2-176">정의</span><span class="sxs-lookup"><span data-stu-id="292f2-176">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="292f2-177">**조사 중**</span><span class="sxs-lookup"><span data-stu-id="292f2-177">**Investigating**</span></span> | <span data-ttu-id="292f2-178">Microsoft에서 잠재적인 문제를 알고 있으며 문제의 상황과 영향의 범위에 대한 추가 정보를 수집하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-178">We're aware of a potential issue and are gathering more information about what's going on and the scope of impact.</span></span> |
|<span data-ttu-id="292f2-179">**서비스 저하**</span><span class="sxs-lookup"><span data-stu-id="292f2-179">**Service degradation**</span></span> | <span data-ttu-id="292f2-p116">Microsoft에서 서비스 또는 기능 사용에 영향을 줄 수 있는 문제가 있음을 확인했습니다. 서비스가 평소보다 느리게 작동하거나, 일시적인 중단이 발생하거나, 기능이 작동하지 않는 등의 경우에 이 상태가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-p116">We've confirmed that there is an issue that may affect use of a service or feature. You might see this status if a service is performing more slowly than usual, there are intermittent interruptions, or if a feature isn't working, for example.</span></span> |
|<span data-ttu-id="292f2-182">**서비스 중단**</span><span class="sxs-lookup"><span data-stu-id="292f2-182">**Service interruption**</span></span> | <span data-ttu-id="292f2-p117">문제가 사용자의 서비스 액세스 기능에 영향을 준다고 판단한 이 상태가 표시됩니다. 이 경우 문제가 중대하며 일관되게 재현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-p117">You'll see this status if we determine that an issue affects the ability for users to access the service. In this case, the issue is significant and can be reproduced consistently.</span></span> |
|<span data-ttu-id="292f2-185">**서비스를 복원하는 중**</span><span class="sxs-lookup"><span data-stu-id="292f2-185">**Restoring service**</span></span> | <span data-ttu-id="292f2-186">문제의 원인이 식별되었으며, Microsoft에서 수행할 정정 작업을 알고 있고 서비스를 다시 정상 상태로 복원하는 프로세스를 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-186">The cause of the issue has been identified, we know what corrective action to take, and are in the process of bringing the service back to a healthy state.</span></span> |
|<span data-ttu-id="292f2-187">**확장된 복구**</span><span class="sxs-lookup"><span data-stu-id="292f2-187">**Extended recovery**</span></span> | <span data-ttu-id="292f2-p118">이 상태는 대부분의 사용자에 대해 서비스를 복원하기 위한 정정 작업이 진행 중이지만, 영향을 받는 모든 시스템에 이를 적용하는 데 시간이 다소 소요될 것임을 나타냅니다. 영구적인 수정 사항을 적용하기 위해 대기하는 동안 영향을 줄이기 위해 임시 수정 사항을 적용한 경우에도 이 상태가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-p118">This status indicates that corrective action is in progress to restore service to most users but will take some time to reach all the affected systems. You might also see this status if we've made a temporary fix to reduce impact while we wait to apply a permanent fix.</span></span> |
|<span data-ttu-id="292f2-190">**조사 일시 중단됨**</span><span class="sxs-lookup"><span data-stu-id="292f2-190">**Investigation suspended**</span></span> | <span data-ttu-id="292f2-p119">잠재적 문제에 대한 자세한 조사 결과, 추가 조사를 하기 위한 고객의 추가 정보가 필요한 경우 이 상태가 표시됩니다. 고객의 행동이 요구되는 경우 필요한 데이터나 로그를 알려드립니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-p119">If our detailed investigation of a potential issue results in a request for additional information from customers to allow us to investigate further, you'll see this status. If we need you to act, we'll let you know what data or logs we need.</span></span> |
|<span data-ttu-id="292f2-193">**서비스 복원됨**</span><span class="sxs-lookup"><span data-stu-id="292f2-193">**Service restored**</span></span> | <span data-ttu-id="292f2-p120">Microsoft에서 정정 작업이 기본 문제를 해결했으며 서비스가 정상 상태로 복원되었음을 확인했습니다. 문제를 확인하려면 문제 세부 정보를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="292f2-p120">We've confirmed that corrective action has resolved the underlying problem and the service has been restored to a healthy state. To find out what went wrong, view the issue details.</span></span> |
|<span data-ttu-id="292f2-196">**가긍성**</span><span class="sxs-lookup"><span data-stu-id="292f2-196">**False positive**</span></span> | <span data-ttu-id="292f2-197">자세한 조사가 끝날 때 서비스가 정상 상태인지와 설계에 따라 작동하고 있는 것으로 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-197">After a detailed investigation, we’ve confirmed the service is healthy and operating as designed.</span></span> <span data-ttu-id="292f2-198">서비스에 대한 영향이 관찰되지 않았습니다. 또는 인시던트의 원인이 서비스 외부에서 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-198">No impact to the service was observed or the cause of the incident originated outside of the service.</span></span> |
|<span data-ttu-id="292f2-199">**게시된 인시던트 사후 보고서**</span><span class="sxs-lookup"><span data-stu-id="292f2-199">**Post-incident report published**</span></span> | <span data-ttu-id="292f2-200">근본 원인 정보가 포함된 특정 문제와 유사한 문제가 다시 발생하지 않도록 하는 다음 단계가 포함된 인시던트 사후 보고서를 게시했습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-200">We’ve published a Post Incident Report for a specific issue that includes root cause information and next steps to ensure a similar issue doesn’t reoccur.</span></span> |

### <a name="history"></a><span data-ttu-id="292f2-201">기록</span><span class="sxs-lookup"><span data-stu-id="292f2-201">History</span></span>

<span data-ttu-id="292f2-202">서비스 상태를 통해 현재 상태를 보고 지난 30일 동안 테넌트에 영향을 미쳤던 모든 서비스 권고 및 인시던트의 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-202">Service health lets you look at current health status and view the history of any service advisories and incidents that have affected your tenant in the past 30 days.</span></span> <span data-ttu-id="292f2-203">모든 서비스의 지난 상태 확인하려면 문제 **세부** 정보 페이지에서 기록 보기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-203">To view the past health of all services, select **View history** on the issue detail page.</span></span>
  
![Show link to health history](../media/service-health-view-history.png)
  
<span data-ttu-id="292f2-205">선택한 시간 범위에서 게시된 모든 서비스 상태 메시지 목록이 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-205">A list of all service health messages posted in the selected timeframe is displayed, as shown below:</span></span>
  
![View service health history](../media/service-health-history.png)
  
<span data-ttu-id="292f2-207">모든 행을 확장하여 문제의 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292f2-207">Expand any row to view more details about the issue.</span></span>
  
<span data-ttu-id="292f2-208">작동 시간 약속에 대한 자세한 내용은 [Microsoft 365의 투명한 운영을 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)</span><span class="sxs-lookup"><span data-stu-id="292f2-208">For more information about our commitment to uptime, see [Transparent operations from Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).</span></span>

## <a name="related-topics"></a><span data-ttu-id="292f2-209">관련 항목</span><span class="sxs-lookup"><span data-stu-id="292f2-209">Related topics</span></span>

<span data-ttu-id="292f2-210">[Microsoft 365 관리 센터의 활동 보고서](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 [메시지 센터 기본 설정](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)</span><span class="sxs-lookup"><span data-stu-id="292f2-210">[Activity Reports in the Microsoft 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
[Message center Preferences](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)</span></span><br/>
[<span data-ttu-id="292f2-211">관리 센터에서 Windows 릴리스 상태 확인 방법</span><span class="sxs-lookup"><span data-stu-id="292f2-211">How to check Windows release health on admin center</span></span>](https://docs.microsoft.com/windows/deployment/update/check-release-health)
