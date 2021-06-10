---
title: 포털 시작 스케줄러를 사용하여 포털 시작
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 이 문서에서는 포털 시작 스케줄러를 사용하여 포털을 시작 하는 방법을 설명 합니다.
ms.openlocfilehash: bf01f6ae93b424543a6a509f89961a1b7a0c9ad7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841669"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="e0b51-103">포털 시작 스케줄러를 SharePoint 포털 시작</span><span class="sxs-lookup"><span data-stu-id="e0b51-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="e0b51-104">포털은 트래픽이 많은 인트라넷의 SharePoint 커뮤니케이션 사이트로, 몇 주 동안 10,000~10만 명 이상의 뷰어가 있는 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="e0b51-105">포털 시작 스케줄러를 사용하여 포털을 시작하여 사용자가 새 웹 사이트 포털에 액세스할 때 원활한 보기 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="e0b51-106">포털 시작 스케줄러는 뷰어를 단계적으로 일괄 처리하고 새 포털에 대한 URL 리디렉션을 관리하여 단계적 롤아웃 방식을 따르는 데 도움이 하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="e0b51-107">각 웨이브가 시작되는 동안 사용자 피드백을 수집하고, 포털 성능을 모니터링하고, 실행을 일시 중지하여 다음 단계로 진행하기 전에 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="e0b51-108">에서 포털 시작을 계획하는 방법에 대해 [SharePoint.](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="e0b51-108">Learn more about how to [plan a portal launch in SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span>

<span data-ttu-id="e0b51-109">**리디렉션에는 두 가지 유형이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="e0b51-110">**양방향:** 새로운 최신 SharePoint 포털을 시작하여 기존 SharePoint 또는 최신 포털을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="e0b51-111">**임시 페이지로** 리디렉션: 기존 SharePoint 포털이 없는 새 최신 SharePoint 시작</span><span class="sxs-lookup"><span data-stu-id="e0b51-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="e0b51-112">사이트 사용 권한은 시작의 일부로 물결과는 별도로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="e0b51-113">예를 들어 조직 전체 포털을 시작하려면 사용 권한을 "외부 사용자를 제외한 모든 사용자"로 권한을 설정한 다음 보안 그룹을 사용하여 사용자를 웨이브로 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="e0b51-114">보안 그룹을 웨이브에 추가하면 해당 보안 그룹이 사이트에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-114">Adding a security group to a wave does not give that security group access to the site.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="e0b51-115">이 기능은 2021년 **5월부터** 대상 릴리스 고객을 위한 SharePoint 커뮤니케이션 사이트 홈 페이지의 설정 패널에서 액세스할 수 있으며 2021년 7월까지 모든 고객이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="e0b51-116">이 도구의 PowerShell 버전을 지금 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="e0b51-117">이 기능은 최신 통신 사이트에서만 SharePoint 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="e0b51-118">포털 시작을 사용자 지정하고 예약하려면 사이트에 대한 사이트 소유자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="e0b51-119">시작은 최소 7일 전에 예약해야 합니다. 각 웨이브는 1~7일 동안 지속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="e0b51-120">필요한 물결 수는 예상되는 사용자 수에 따라 자동으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-120">The number of waves required is automatically determined by the expected number of users</span></span>
> - <span data-ttu-id="e0b51-121">포털 시작을 설정하기 전에 사이트의 [](https://aka.ms/perftool) SharePoint 페이지가 정상 상태인지 확인하기 위해 SharePoint 도구에 대한 페이지 진단을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="e0b51-122">시작이 끝나면 사이트에 대한 사용 권한이 있는 모든 사용자가 새 사이트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="e0b51-123">조직에서 [Viva Connections를](/SharePoint/viva-connections)사용하는 경우 사용자는 Microsoft Teams 앱 바에서 조직의 아이콘을 볼 수 있습니다. 그러나 아이콘을 선택하면 사용자가 웨이브가 시작될 때까지 포털에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-123">If your organization is using [Viva Connections](/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="e0b51-124">이 기능은 독일, Office 365 21Vianet에서 운영하는 Office 365(중국) 또는 미국 Microsoft 365 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

## <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="e0b51-125">포털 시작 스케줄러 옵션 간의 차이점을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="e0b51-126">이전의 포털 시작은 PowerShell을 통해서만 SharePoint 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="e0b51-127">이제 포털 시작을 예약하고 관리하는 데 도움이 되는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="e0b51-128">두 도구의 주요 차이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="e0b51-129">**SharePoint PowerShell 버전:**</span><span class="sxs-lookup"><span data-stu-id="e0b51-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="e0b51-130">PowerShell을 사용하려면 관리자 [자격 SharePoint 필요합니다.](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="e0b51-130">Admin credentials are required to use [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span></span>
- <span data-ttu-id="e0b51-131">한 웨이브의 최소 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0b51-131">Minimum requirement of one wave</span></span>
- <span data-ttu-id="e0b51-132">UTC(협정 세계시) 표준 시간대에 따라 시작 예약</span><span class="sxs-lookup"><span data-stu-id="e0b51-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="e0b51-133">**제품 내 버전:**</span><span class="sxs-lookup"><span data-stu-id="e0b51-133">**In-product version:**</span></span>

- <span data-ttu-id="e0b51-134">사이트 소유자 자격 증명 필요</span><span class="sxs-lookup"><span data-stu-id="e0b51-134">Site owner credentials are required</span></span>
- <span data-ttu-id="e0b51-135">두 가지 파도의 최소 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0b51-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="e0b51-136">지역 설정에 표시된 포털의 현지 표준 시간대를 기준으로 시작 예약</span><span class="sxs-lookup"><span data-stu-id="e0b51-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>

## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="e0b51-137">포털 시작 스케줄러 사용 시작</span><span class="sxs-lookup"><span data-stu-id="e0b51-137">Get started using the Portal launch scheduler</span></span>

1. <span data-ttu-id="e0b51-138">포털 시작 스케줄러 도구를 사용하려면 먼저 사이트 [소유자,](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) 사이트  구성원 또는 방문자로 사이트 권한을 통해 이 사이트에 액세스해야 하는 모든 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2. <span data-ttu-id="e0b51-139">그런 다음 다음 두 가지 방법 중 하나를 통해 포털 시작 스케줄러에 액세스하여 포털 시작 일정을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

   <span data-ttu-id="e0b51-140">**옵션 1:** 처음 몇 번(또는 홈페이지 버전 3.0까지) 홈 페이지에 대한 변경 내용을 편집하고 다시 게시하는 경우 포털 시작 스케줄러 도구를 사용할지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="e0b51-141">예약을 **통해** 시작 예약을 선택하여 앞으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="e0b51-142">또는 **다시 게시를 선택하여** 시작을 설정하지 않고 페이지 편집을 다시 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>

   ![홈 페이지를 다시 게시할 때 포털 시작 스케줄러를 사용하는 프롬프트 이미지](../media/portal-launch-republish-2.png)

   <span data-ttu-id="e0b51-144">**옵션 2:** 원하는 경우 SharePoint 커뮤니케이션 사이트 홈 페이지로 이동하여 설정 사이트  실행 예약을 선택하여 포털의 시작을 예약할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="e0b51-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>

   ![사이트 설정 예약이 강조 표시된 이미지](../media/portal-launch-settings-2.png)

3. <span data-ttu-id="e0b51-146">다음으로 포털의 상태 점수를 확인하고 필요한 경우 포털에서 정상 [](https://aka.ms/perftool) 점수를 받을 때까지 SharePoint 페이지 진단 도구를 사용하여 포털을 **개선합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="e0b51-147">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-147">Then, select **Next**.</span></span>

   ![포털 시작 스케줄러 도구의 이미지](../media/portal-launch-panel-2.png)

   > [!NOTE]
   > <span data-ttu-id="e0b51-149">사이트 이름 및 설명은 포털 시작 스케줄러에서 편집할 수 없습니다. 대신  홈 페이지에서 사이트  설정 정보를 선택하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>

4. <span data-ttu-id="e0b51-150">**드롭다운에서** 예상 사용자 수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="e0b51-151">이 그림은 사이트에 액세스해야 하는 사용자 수를 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="e0b51-152">포털 시작 스케줄러는 예상되는 사용자에 따라 다음을 자동으로 결정하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>

   - <span data-ttu-id="e0b51-153">사용자 수가 10k명 미만: 2회</span><span class="sxs-lookup"><span data-stu-id="e0b51-153">Less than 10k users: Two waves</span></span>
   - <span data-ttu-id="e0b51-154">10k ~ 30k 사용자: 세 가지 파도</span><span class="sxs-lookup"><span data-stu-id="e0b51-154">10k to 30k users: Three waves</span></span>
   - <span data-ttu-id="e0b51-155">30k+ ~ 100k 사용자: 5회</span><span class="sxs-lookup"><span data-stu-id="e0b51-155">30k+ to 100k users: Five waves</span></span>
   - <span data-ttu-id="e0b51-156">사용자 수가 100k명 이상인 경우 포털 시작 섹션에 나열된 단계를 통해 5개의 단계로 Microsoft에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="e0b51-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span>

5. <span data-ttu-id="e0b51-157">그런 다음 필요한 **리디렉션 유형을** 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-157">Then, determine the **Type of redirect** needed:</span></span>

   <span data-ttu-id="e0b51-158">**옵션 1: 기존** SharePoint 페이지로 사용자 보내기 ( 양방향) – 새 최신 SharePoint 포털을 시작하여 기존 SharePoint 포털을 대체할 때 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="e0b51-159">활성 웨이브의 사용자는 이전 사이트로 이동하는지 새 사이트로 이동하는지 여부에 관계없이 새 사이트로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="e0b51-160">새 사이트에 액세스하려고 하는 시작되지 않은 웨이브의 사용자는 해당 웨이브가 시작될 때까지 이전 사이트로 다시 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e0b51-161">양방향 옵션을 사용하는 경우 시작을 위한 사용자도 다른 사이트 포털에 대한 사이트 소유자 SharePoint 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>

   <span data-ttu-id="e0b51-162">**옵션 2: 사용자를** 자동게이트된 임시 페이지(임시 페이지 리디렉션)로 보내기 - 기존 사이트 포털이 없는 경우 임시 페이지 리디렉션을 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="e0b51-163">사용자는 새로운 최신 SharePoint 포털로 이동되고 사용자가 아직 시작되지 않은 상태이면 임시 페이지로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>

   <span data-ttu-id="e0b51-164">**옵션 3: 외부** 페이지로 사용자 보내기 - 사용자의 웨이브가 시작될 때까지 임시 방문 페이지 환경으로 외부 URL을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>

6. <span data-ttu-id="e0b51-165">대상을 파도로 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-165">Break up your audience into waves.</span></span> <span data-ttu-id="e0b51-166">웨이브당 최대 20개 보안 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="e0b51-167">각 웨이브가 시작될 때까지 웨이브 세부 정보를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="e0b51-168">각 웨이브는 최소 1일(24시간) 및 최대 7일 동안 지속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="e0b51-169">따라서 SharePoint 환경과 사용자들이 많은 사이트 사용자를 익고 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="e0b51-170">UI를 통해 시작을 계획할 때 표준 시간대는 사이트의 국가별 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="e0b51-171">포털 시작 스케줄러는 자동으로 최소 2회의 웨이브로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="e0b51-172">그러나 이 도구의 PowerShell 버전은 1파일을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
   > - <span data-ttu-id="e0b51-173">Microsoft 365 이 버전의 포털 시작 스케줄러에서 지원되지 않는 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="e0b51-174">사이트를 바로 보아야 하는 사용자를 결정하고 사용자가 파도에서 제외된 사용자 필드에 정보를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="e0b51-175">이러한 사용자는 웨이브에서 제외되기 때문에 시작 전, 실행 중 또는 이후에 리디렉션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e0b51-176">최대 50개의 고유한 사용자 또는 보안 그룹을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-176">Up to 50 distinct users or security groups max can be added.</span></span> <span data-ttu-id="e0b51-177">파도가 시작되기 전에 50명 이상의 사용자가 포털에 액세스해야 하는 경우 보안 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-177">Use security groups when you need more than 50 individuals to get access to the portal before the waves start launching.</span></span>

8. <span data-ttu-id="e0b51-178">포털 시작 세부 정보를 확인하고 일정 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-178">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="e0b51-179">시작이 예약된 후 SharePoint 포털 홈 페이지에 대한 모든 변경 내용은 포털 시작이 다시 시작되기 전에 정상 진단 결과를 수신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-179">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-a-portal-with-over-100k-users"></a><span data-ttu-id="e0b51-180">100k 사용자가 있는 포털 시작</span><span class="sxs-lookup"><span data-stu-id="e0b51-180">Launch a portal with over 100k users</span></span>

<span data-ttu-id="e0b51-181">사용자가 10만 명 이상인 포털을 시작해야 하는 경우 아래 나열된 단계에 따라 지원 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-181">If you are planning to launch a portal with over 100,000 users, submit a support request following the steps listed below.</span></span> <span data-ttu-id="e0b51-182">요청된 모든 정보를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-182">Make sure to include all the requested information.</span></span>

<span data-ttu-id="e0b51-183">**다음 단계를 따르세요.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-183">**Follow these steps:**</span></span>

1. <span data-ttu-id="e0b51-184"><https://admin.microsoft.com>으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-184">Go to <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="e0b51-185">새 관리 센터 미리 보기를 사용하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="e0b51-185">Ensure you are using the new admin center preview</span></span>
3. <span data-ttu-id="e0b51-186">왼쪽 탐색 창에서 지원을 선택한 다음 새 서비스 **요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-186">On the left navigational pane, select **Support**, and then select **New Service Request**</span></span>

   <span data-ttu-id="e0b51-187">그러면 화면 오른쪽에 **도움이 필요하세요?** 창이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-187">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4. <span data-ttu-id="e0b51-188">문제를 **간단히 설명하기** 위해 "100k SharePoint 포털 시작"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-188">For **Briefly describe your issue**, enter "Launch SharePoint Portal with 100k users"</span></span></br>
5. <span data-ttu-id="e0b51-189">그런 다음 고객 **지원에 문의를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-189">Then, select **Contact Support**</span></span>
6. <span data-ttu-id="e0b51-190">**설명에서**"100k SharePoint 포털 시작"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-190">Under **Description**, enter "Launch SharePoint Portal with 100k users"</span></span>
7. <span data-ttu-id="e0b51-191">나머지 정보를 입력하고 **연락을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-191">Fill out the remaining information, and then select **Contact me**</span></span>
8. <span data-ttu-id="e0b51-192">티켓이 생성되면 다음과 같은 정보를 고객 지원팀으로 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="e0b51-192">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
   - <span data-ttu-id="e0b51-193">포털 URL</span><span class="sxs-lookup"><span data-stu-id="e0b51-193">Portal URL's</span></span>
   - <span data-ttu-id="e0b51-194">필요한 사용자 수</span><span class="sxs-lookup"><span data-stu-id="e0b51-194">Number of users expected</span></span>
   - <span data-ttu-id="e0b51-195">예상 시작 일정</span><span class="sxs-lookup"><span data-stu-id="e0b51-195">Estimated launch schedule</span></span>

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="e0b51-196">예약된 포털 시작 변경</span><span class="sxs-lookup"><span data-stu-id="e0b51-196">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="e0b51-197">시작 세부 정보는 웨이브가 시작된 날짜까지 각 웨이브에 대해 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-197">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span>

1. <span data-ttu-id="e0b51-198">포털 시작 세부 정보를 편집하려면 사이트 설정 시작 **예약을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="e0b51-198">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2. <span data-ttu-id="e0b51-199">그런 다음 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-199">Then, select **Edit**.</span></span>
3. <span data-ttu-id="e0b51-200">편집을 마치면 업데이트를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-200">When you are finished making your edits, select **Update**.</span></span>

## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="e0b51-201">예약된 포털 시작 삭제</span><span class="sxs-lookup"><span data-stu-id="e0b51-201">Delete a scheduled portal launch</span></span>

<span data-ttu-id="e0b51-202">일부 웨이브가 이미 시작된 경우에도 포털 시작 스케줄러 도구를 사용하여 예약된 시작을 취소하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-202">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1. <span data-ttu-id="e0b51-203">포털의 시작을 취소하기 위해 사이트 설정 **실행** **예약으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0b51-203">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2. <span data-ttu-id="e0b51-204">그런 다음 **삭제를** 선택하고 아래 메시지가 표시되면 다시 **삭제를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-204">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

   ![포털 시작 스케줄러 도구의 이미지](../media/portal-launch-delete-2.png)

## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="e0b51-206">PowerShell 포털 시작 스케줄러 사용</span><span class="sxs-lookup"><span data-stu-id="e0b51-206">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="e0b51-207">SharePoint 포털 시작 스케줄러 도구는 원래 SharePoint [PowerShell을](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) 통해서만 사용할 수 있으며 이 방법을 선호하는 고객을 위해 PowerShell을 통해 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-207">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="e0b51-208">이 문서의 시작에 있는 동일한 메모는 두 버전의 포털 시작 스케줄러에 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-208">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span>

> [!NOTE]
> <span data-ttu-id="e0b51-209">PowerShell을 사용하려면 관리자 권한이 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-209">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="e0b51-210">PowerShell에서 만든 시작에 대한 포털 시작 세부 정보가 표시되고 이 도구의 새 포털 시작 스케줄러 도구에서 관리할 SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e0b51-210">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>

### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="e0b51-211">앱 설치 및 SharePoint 온라인에 연결</span><span class="sxs-lookup"><span data-stu-id="e0b51-211">App setup and connecting to SharePoint Online</span></span>

1. <span data-ttu-id="e0b51-212">[최신 SharePoint Online 관리 셸 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)</span><span class="sxs-lookup"><span data-stu-id="e0b51-212">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e0b51-p118">이전 버전의 SharePoint Online 관리 셸을 설치한 경우 프로그램 추가/제거로 이동하여 "SharePoint Online 관리 셸"을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-p118">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="e0b51-214">다운로드 센터 페이지에서 언어를 선택하고 다운로드 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-214">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="e0b51-215">x64 및 x86 .msi 파일 다운로드 중에서 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-215">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="e0b51-216">64 비트 버전의 Windows를 실행하는 경우 x64 파일을, 32 비트 버전을 실행하는 경우 x86 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-216">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="e0b51-217">버전을 모르는 경우에는 [어떠한 Windows 운영 체제 버전을 실행 중인가요?](https://support.microsoft.com/help/13443/windows-which-operating-system)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0b51-217">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="e0b51-218">파일을 다운로드한 후 파일을 실행하고 설정 마법사의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-218">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="e0b51-219">Microsoft 365에서 [전역 관리자 또는 SharePoint 관리자](/sharepoint/sharepoint-admin-role)로 SharePoint에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-219">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="e0b51-220">자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0b51-220">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="e0b51-221">기존 포털 시작 설정 보기</span><span class="sxs-lookup"><span data-stu-id="e0b51-221">View any existing portal launch setups</span></span>

<span data-ttu-id="e0b51-222">기존 포털 시작 구성이 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="e0b51-222">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="e0b51-223">사이트에서 포털 시작 예약</span><span class="sxs-lookup"><span data-stu-id="e0b51-223">Schedule a portal launch on the site</span></span>

<span data-ttu-id="e0b51-224">필요한 파도 수는 예상되는 시작 크기에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-224">The number of waves required depends on your expected launch size.</span></span>

- <span data-ttu-id="e0b51-225">10k 사용자 미만: 한 웨이브</span><span class="sxs-lookup"><span data-stu-id="e0b51-225">Less than 10k users: One wave</span></span>
- <span data-ttu-id="e0b51-226">10k ~ 30k 사용자: 세 가지 파도</span><span class="sxs-lookup"><span data-stu-id="e0b51-226">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="e0b51-227">30k+ ~ 100k 사용자: 5회</span><span class="sxs-lookup"><span data-stu-id="e0b51-227">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="e0b51-228">100k 사용자 이상: 5개의 물결표로 Microsoft 계정 팀에 문의</span><span class="sxs-lookup"><span data-stu-id="e0b51-228">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="e0b51-229">양방향 리디렉션 단계</span><span class="sxs-lookup"><span data-stu-id="e0b51-229">Steps for bidirectional redirection</span></span>

<span data-ttu-id="e0b51-230">양방향 리디렉션에는 기존 SharePoint 또는 최신 포털을 대체하는 새로운 최신 SharePoint 포털을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-230">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="e0b51-231">활성 웨이브의 사용자는 이전 사이트로 이동하는지 새 사이트로 이동하는지 여부에 관계없이 새 사이트로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-231">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="e0b51-232">새 사이트에 액세스하려고 하는 시작되지 않은 웨이브의 사용자는 해당 웨이브가 시작될 때까지 이전 사이트로 다시 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-232">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

<span data-ttu-id="e0b51-233">이전 사이트의 기본 홈 페이지와 새 사이트의 기본 홈 페이지 간 리디렉션만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-233">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="e0b51-234">리디렉션되지 않고 이전 및 새 사이트에 액세스해야 하는 관리자 또는 소유자가 있는 경우 매개 변수를 사용하여 나열해야 `WaveOverrideUsers` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-234">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="e0b51-235">기존 SharePoint 사이트에서 새 SharePoint 사이트로 사용자를 마이그레이션하려면 다음을 단계적으로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-235">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="e0b51-236">다음 명령을 실행하여 포털 시작 웨이브를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-236">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="e0b51-237">예제:</span><span class="sxs-lookup"><span data-stu-id="e0b51-237">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="e0b51-238">유효성 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-238">Complete validation.</span></span> <span data-ttu-id="e0b51-239">리디렉션이 서비스 전체에서 구성을 완료하는 데 5-10분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-239">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="e0b51-240">임시 페이지로 리디렉션하는 단계</span><span class="sxs-lookup"><span data-stu-id="e0b51-240">Steps for redirection to temporary page</span></span>

<span data-ttu-id="e0b51-241">기존 사이트 포털이 없는 경우 임시 페이지 리디렉션을 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-241">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="e0b51-242">사용자는 새로운 최신 SharePoint 온라인 포털로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-242">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="e0b51-243">사용자가 시작되지 않은 웨이브에 있는 경우 임시 페이지(모든 URL)로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-243">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span>

1. <span data-ttu-id="e0b51-244">다음 명령을 실행하여 포털 시작 웨이브를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-244">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="e0b51-245">예제:</span><span class="sxs-lookup"><span data-stu-id="e0b51-245">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="e0b51-246">유효성 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-246">Complete validation.</span></span> <span data-ttu-id="e0b51-247">리디렉션이 서비스 전체에서 구성을 완료하는 데 5-10분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-247">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="e0b51-248">사이트에서 포털 시작 일시 중지 또는 다시 시작</span><span class="sxs-lookup"><span data-stu-id="e0b51-248">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="e0b51-249">진행 중 포털 시작을 일시 중지하고 예정된 물결 진행이 발생하지 않도록 일시적으로 차단하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-249">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="e0b51-250">모든 사용자가 이전 사이트로 리디렉션되는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-250">Validate that all users are redirected to the old site.</span></span>

3. <span data-ttu-id="e0b51-251">일시 중지된 포털 시작을 다시 시작하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-251">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```

4. <span data-ttu-id="e0b51-252">이제 리디렉션이 복원되어 있는지 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-252">Validate that the redirection is now restored.</span></span>

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="e0b51-253">사이트에서 포털 시작 삭제</span><span class="sxs-lookup"><span data-stu-id="e0b51-253">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="e0b51-254">다음 명령을 실행하여 사이트에 대해 예약되거나 진행 중인 포털 시작을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-254">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="e0b51-255">모든 사용자에 대해 리디렉션이 진행되지 않은지 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b51-255">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="e0b51-256">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="e0b51-256">Learn more</span></span>

[<span data-ttu-id="e0b51-257">SharePoint Online에서 포털 시작 롤아웃 계획</span><span class="sxs-lookup"><span data-stu-id="e0b51-257">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="e0b51-258">커뮤니케이션 사이트 계획</span><span class="sxs-lookup"><span data-stu-id="e0b51-258">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
