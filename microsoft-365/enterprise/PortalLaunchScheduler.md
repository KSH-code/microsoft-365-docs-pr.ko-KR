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
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926145"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="6b2da-103">포털 시작 스케줄러를 사용하여 포털 시작</span><span class="sxs-lookup"><span data-stu-id="6b2da-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="6b2da-104">포털은 사이트에서 콘텐츠를 사용하는 다수의 사이트 방문자를 보유하는 인트라넷 상의 SharePoint 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="6b2da-105">사용자가 새 SharePoint Online 포털에 액세스하는 원활하고 원활하게 작업할 수 있도록 하는 중요한 부분으로 포털을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="6b2da-106">SharePoint Online에서 포털 시작 롤아웃 계획에 자세히 설명된 방식으로 시작은 포털을 롤아웃하는 [핵심적인 방법입니다.](./planportallaunchroll-out.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="6b2da-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](./planportallaunchroll-out.md?view=o365-worldwide).</span></span> <span data-ttu-id="6b2da-107">포털 시작 스케줄러는 새 포털에 대한 리디렉션을 관리하여 단계적/단계적 롤아웃 방식을 따르는 데 도움이 하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="6b2da-108">각 단계가 진행되는 동안 각 배포 단계 동안 사용자 피드백을 수집하고 성능을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="6b2da-109">이 경우 포털을 느리게 도입하여 다음 단계로 진행하기 전에 문제를 일시 중지하고 해결할 수 있으며 궁극적으로 사용자에게 긍정적인 환경을 보장할 수 있는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="6b2da-110">리디렉션에는 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="6b2da-111">양방향: 새로운 최신 SharePoint Online 포털을 시작하여 기존 SharePoint 클래식 또는 최신 포털을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="6b2da-112">임시 페이지 리디렉션: 기존 SharePoint 포털이 없는 새로운 최신 SharePoint Online 포털 시작</span><span class="sxs-lookup"><span data-stu-id="6b2da-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="6b2da-113">포털 시작 스케줄러는 최신 SharePoint Online 포털(통신 사이트)을 시작해야만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="6b2da-114">시작은 최소 7일 전에 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="6b2da-115">필요한 물결 수는 예상되는 사용자 수에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="6b2da-116">포털 시작을 설정하기 전에 [SharePoint용 페이지](./page-diagnostics-for-spo.md) 진단 도구를 실행하여 포털의 홈 페이지가 정상 상태인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="6b2da-117">포털을 시작하면 사이트에 대한 사용 권한이 있는 모든 사용자가 새 사이트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="6b2da-118">성공적인 포털을 시작하는 데 대한 자세한 내용은 정상 포털 만들기, 시작 및 유지 관리에 자세히 설명된 기본 원칙, 사례 및 권장 사항을 [따르하세요.](/sharepoint/portal-health)</span><span class="sxs-lookup"><span data-stu-id="6b2da-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="6b2da-119">이 기능은 Office 365 Germany, 21Vianet에서 운영하는 Office 365(중국) 또는 Microsoft 365 Government 계획에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="6b2da-120">앱 설정 및 SharePoint Online에 연결</span><span class="sxs-lookup"><span data-stu-id="6b2da-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="6b2da-121">[최신 SharePoint Online 관리 셸 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)</span><span class="sxs-lookup"><span data-stu-id="6b2da-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b2da-p104">이전 버전의 SharePoint Online 관리 셸을 설치한 경우 프로그램 추가/제거로 이동하여 "SharePoint Online 관리 셸"을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="6b2da-123">다운로드 센터 페이지에서 언어를 선택하고 다운로드 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="6b2da-124">x64 및 x86 .msi 파일 다운로드 중에서 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="6b2da-125">64 비트 버전의 Windows를 실행하는 경우 x64 파일을, 32 비트 버전을 실행하는 경우 x86 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="6b2da-126">버전을 모르는 경우에는 [어떠한 Windows 운영 체제 버전을 실행 중인가요?](https://support.microsoft.com/help/13443/windows-which-operating-system)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b2da-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="6b2da-127">파일을 다운로드한 후 파일을 실행하고 설정 마법사의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="6b2da-128">Microsoft 365에서 [전역 관리자 또는 SharePoint 관리자](/sharepoint/sharepoint-admin-role)로 SharePoint에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="6b2da-129">자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b2da-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="6b2da-130">기존 포털 시작 설정 보기</span><span class="sxs-lookup"><span data-stu-id="6b2da-130">View any existing portal launch setups</span></span>

<span data-ttu-id="6b2da-131">기존 포털 시작 구성이 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="6b2da-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="6b2da-132">사이트에서 포털 시작 예약</span><span class="sxs-lookup"><span data-stu-id="6b2da-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="6b2da-133">필요한 파도 수는 예상되는 시작 크기에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="6b2da-134">10k 사용자 미만: 1개 웨이브</span><span class="sxs-lookup"><span data-stu-id="6b2da-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="6b2da-135">10k ~ 30k 사용자: 3회</span><span class="sxs-lookup"><span data-stu-id="6b2da-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="6b2da-136">30k+ ~ 100k 사용자: 5회</span><span class="sxs-lookup"><span data-stu-id="6b2da-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="6b2da-137">100k 사용자 5명 이상: 5회 진행하여 Microsoft 계정 팀에 문의</span><span class="sxs-lookup"><span data-stu-id="6b2da-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="6b2da-138">양방향 리디렉션 단계</span><span class="sxs-lookup"><span data-stu-id="6b2da-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="6b2da-139">양방향 리디렉션에는 기존 SharePoint 클래식 또는 최신 포털을 대체하는 새로운 최신 SharePoint Online 포털을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="6b2da-140">활성 웨이브의 사용자는 이전 사이트로 이동하는지 새 사이트로 이동하는지 여부에 관계없이 새 사이트로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="6b2da-141">새 사이트에 액세스하려고 하는 시작되지 않은 웨이브의 사용자는 해당 웨이브가 시작될 때까지 이전 사이트로 다시 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="6b2da-142">이전 사이트의 기본 홈 페이지와 새 사이트의 기본 홈 페이지 간 리디렉션만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="6b2da-143">리디렉션되지 않고 이전 및 새 사이트에 액세스해야 하는 관리자 또는 소유자가 있는 경우 매개 변수를 사용하여 나열해야 `WaveOverrideUsers` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="6b2da-144">기존 SharePoint 사이트에서 새 SharePoint 사이트로 사용자를 단계적 방식으로 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="6b2da-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="6b2da-145">다음 명령을 실행하여 포털 시작 웨이브를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="6b2da-146">예제:</span><span class="sxs-lookup"><span data-stu-id="6b2da-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="6b2da-147">유효성 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-147">Complete validation.</span></span> <span data-ttu-id="6b2da-148">리디렉션이 서비스 전체에서 구성을 완료하는 데 5-10분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="6b2da-149">임시 페이지로 리디렉션하는 단계</span><span class="sxs-lookup"><span data-stu-id="6b2da-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="6b2da-150">기존 SharePoint 포털이 없는 경우 임시 페이지 리디렉션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="6b2da-151">사용자는 단계적 방식으로 새로운 최신 SharePoint Online 포털로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="6b2da-152">사용자가 시작되지 않은 웨이브에 있는 경우 임시 페이지(모든 URL)로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="6b2da-153">다음 명령을 실행하여 포털 시작 웨이브를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="6b2da-154">예제:</span><span class="sxs-lookup"><span data-stu-id="6b2da-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="6b2da-155">유효성 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-155">Complete validation.</span></span> <span data-ttu-id="6b2da-156">리디렉션이 서비스 전체에서 구성을 완료하는 데 5-10분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="6b2da-157">사이트에서 포털 시작 일시 중지 또는 다시 시작</span><span class="sxs-lookup"><span data-stu-id="6b2da-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="6b2da-158">진행 중 포털 시작을 일시 중지하고 예정된 물결 진행이 발생하지 않도록 일시적으로 차단하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="6b2da-159">모든 사용자가 이전 사이트로 리디렉션되는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="6b2da-160">일시 중지된 포털 시작을 다시 시작하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="6b2da-161">이제 리디렉션이 복원되어 있는지 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="6b2da-162">사이트에서 포털 시작 삭제</span><span class="sxs-lookup"><span data-stu-id="6b2da-162">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="6b2da-163">다음 명령을 실행하여 사이트에 대해 예약되거나 진행 중인 포털 시작을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="6b2da-164">모든 사용자에 대해 리디렉션이 진행되지 않은지 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2da-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="6b2da-165">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="6b2da-165">Learn more</span></span>
[<span data-ttu-id="6b2da-166">SharePoint Online에서 포털 시작 롤아웃 계획</span><span class="sxs-lookup"><span data-stu-id="6b2da-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)