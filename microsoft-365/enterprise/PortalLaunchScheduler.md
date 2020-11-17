---
title: 포털 시작 스케줄러를 사용 하 여 포털 시작
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
description: 이 문서에서는 포털 시작 스케줄러를 사용 하 여 포털을 시작 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: a7a007fdd95638109830a8e3689232060f2b9d8b
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123586"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="4c186-103">포털 시작 스케줄러를 사용 하 여 포털 시작</span><span class="sxs-lookup"><span data-stu-id="4c186-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="4c186-104">포털은 사이트에서 콘텐츠를 사용하는 다수의 사이트 방문자를 보유하는 인트라넷 상의 SharePoint 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="4c186-105">물결에서 포털을 시작 하는 것은 사용자에 게 새 SharePoint Online 포털에 쉽게 액세스할 수 있도록 하는 데 있어 중요 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="4c186-106">물결에서 시작 하는 것은 [SharePoint Online에서 포털 시작 롤아웃 계획 계획](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)에 설명 된 것 처럼 포털을 롤아웃 하는 핵심 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="4c186-107">포털 시작 스케줄러는 새 포털의 리디렉션을 관리 하 여 웨이브/단계적 롤아웃 방식에 따라 진행 하는 데 도움을 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="4c186-108">각 물결 중에는 각 배포 전파가 진행 되는 동안 사용자 의견을 수집 하 고 성능을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="4c186-109">이렇게 하면 다음 웨이브를 계속 진행 하기 전에 문제를 일시 중지 및 해결 하 고 궁극적으로 사용자에 게 긍정적인 환경을 유지 하는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="4c186-110">리디렉션에는 다음과 같은 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="4c186-111">양방향 작업: 새로운 최신 SharePoint Online 포털을 시작 하 여 기존 SharePoint 클래식 또는 최신 포털을 교체 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="4c186-112">임시 페이지 리디렉션: 기존 SharePoint 포털을 사용 하지 않고 새로운 최신 SharePoint Online 포털 시작</span><span class="sxs-lookup"><span data-stu-id="4c186-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="4c186-113">포털 시작 스케줄러는 커뮤니케이션 사이트 및 최신 팀 사이트와 같은 최신 SharePoint Online 포털을 실행 하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-113">The portal launch scheduler is only available to launch modern SharePoint Online portals, like communication sites and modern team sites.</span></span> <span data-ttu-id="4c186-114">시작을 7 일 이상 미리 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="4c186-115">필요한 물결 수는 예상 사용자 수에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="4c186-116">포털 시작을 예약 하기 전에 포털의 홈 페이지가 정상 인지 확인 하기 위해 [SharePoint 용 페이지 진단을](https://aka.ms/perftool) 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="4c186-117">포털 시작이 끝나면 사이트에 대 한 사용 권한이 있는 모든 사용자가 새 사이트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="4c186-118">성공적인 포털을 시작 하는 방법에 대 한 자세한 내용은 [정상 포털을 만들고, 시작 하 고, 유지 관리](https://docs.microsoft.com/sharepoint/portal-health)하는 방법에 대해 설명 하는 기본 원칙, 모범 사례 및 권장 사항을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4c186-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="4c186-119">이 기능은 Office 365 독일, 21Vianet에서 운영 하는 Office 365 (중국) 또는 Microsoft 365 US 정부 요금제에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="4c186-120">앱 설치 및 SharePoint Online에 연결</span><span class="sxs-lookup"><span data-stu-id="4c186-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="4c186-121">[최신 SharePoint Online 관리 셸 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)</span><span class="sxs-lookup"><span data-stu-id="4c186-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c186-p104">이전 버전의 SharePoint Online 관리 셸을 설치한 경우 프로그램 추가/제거로 이동하여 "SharePoint Online 관리 셸"을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="4c186-123">다운로드 센터 페이지에서 언어를 선택하고 다운로드 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="4c186-124">x64 및 x86 .msi 파일 다운로드 중에서 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="4c186-125">64 비트 버전의 Windows를 실행하는 경우 x64 파일을, 32 비트 버전을 실행하는 경우 x86 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="4c186-126">버전을 모르는 경우에는 [어떠한 Windows 운영 체제 버전을 실행 중인가요?](https://support.microsoft.com/help/13443/windows-which-operating-system)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c186-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="4c186-127">파일을 다운로드한 후 파일을 실행하고 설정 마법사의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="4c186-128">Microsoft 365에서 [전역 관리자 또는 SharePoint 관리자](/sharepoint/sharepoint-admin-role)로 SharePoint에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="4c186-129">자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c186-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="4c186-130">기존 포털 시작 프로그램 보기</span><span class="sxs-lookup"><span data-stu-id="4c186-130">View any existing portal launch setups</span></span>

<span data-ttu-id="4c186-131">기존 포털 시작 구성이 있는지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="4c186-132">사이트에서 포털 시작 예약</span><span class="sxs-lookup"><span data-stu-id="4c186-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="4c186-133">필요한 물결 수는 예상 되는 시작 크기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="4c186-134">10k 미만의 사용자: 웨이브 1 개</span><span class="sxs-lookup"><span data-stu-id="4c186-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="4c186-135">10k ~ 30k 사용자: 3 개의 물결</span><span class="sxs-lookup"><span data-stu-id="4c186-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="4c186-136">30k + 10만 명의 사용자: 5 물결</span><span class="sxs-lookup"><span data-stu-id="4c186-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="4c186-137">10만 명 이상: 5 개의 물결 및 Microsoft 계정 팀에 문의</span><span class="sxs-lookup"><span data-stu-id="4c186-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bi-directional-redirection"></a><span data-ttu-id="4c186-138">양방향 리디렉션 단계</span><span class="sxs-lookup"><span data-stu-id="4c186-138">Steps for bi-directional redirection</span></span>

<span data-ttu-id="4c186-139">양방향 리디렉션에는 기존 SharePoint 클래식 또는 최신 포털을 대체 하기 위해 최신 SharePoint Online 포털을 새로 시작 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="4c186-140">활성 물결의 사용자가 이전 사이트 또는 새 사이트로 이동 하는지 여부에 관계 없이 새 사이트로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="4c186-141">시작 되지 않은 웨이브의 사용자가 새 사이트에 액세스 하려고 하면 해당 물결이 시작 될 때까지 이전 사이트로 다시 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> <span data-ttu-id="4c186-142">이전 및 새 사이트를 리디렉션하지 않고 액세스 해야 하는 관리자 또는 소유자가 있는 경우에는 매개 변수를 사용 하 여 나열 되는지 확인 합니다 `WaveOverrideUsers` .</span><span class="sxs-lookup"><span data-stu-id="4c186-142">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> 

<span data-ttu-id="4c186-143">기존 SharePoint 사이트의 사용자를 미리 구성 된 방식으로 새 SharePoint 사이트로 마이그레이션하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-143">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="4c186-144">다음 명령을 실행 하 여 포털 시작 물결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-144">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="4c186-145">예제:</span><span class="sxs-lookup"><span data-stu-id="4c186-145">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="4c186-146">유효성 검사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-146">Complete validation.</span></span> <span data-ttu-id="4c186-147">리디렉션이 서비스 전체에서 구성을 완료 하는 데 5-10 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-147">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="4c186-148">임시 페이지로 리디렉션하는 단계</span><span class="sxs-lookup"><span data-stu-id="4c186-148">Steps for redirection to temporary page</span></span>

<span data-ttu-id="4c186-149">기존 SharePoint 포털이 없는 경우 임시 페이지 리디렉션을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-149">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="4c186-150">사용자는 미리 구성 된 새로운 SharePoint Online 포털을 미리 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-150">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="4c186-151">사용자가 아직 시작 되지 않은 웨이브에 있는 경우에는 임시 페이지 (모든 URL)로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-151">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="4c186-152">다음 명령을 실행 하 여 포털 시작 물결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-152">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="4c186-153">예제:</span><span class="sxs-lookup"><span data-stu-id="4c186-153">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="4c186-154">유효성 검사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-154">Complete validation.</span></span> <span data-ttu-id="4c186-155">리디렉션이 서비스 전체에서 구성을 완료 하는 데 5-10 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-155">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="4c186-156">사이트에서 포털 시작 일시 중지 또는 다시 시작</span><span class="sxs-lookup"><span data-stu-id="4c186-156">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="4c186-157">진행 중인 포털 시작을 일시 중지 하 고 예정 된 웨이브 progressions 발생 하는 것을 일시적으로 방지 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-157">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="4c186-158">모든 사용자가 이전 사이트로 리디렉션되도록 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-158">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="4c186-159">일시 중지 된 포털 시작을 다시 시작 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-159">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="4c186-160">리디렉션이 이제 복원 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-160">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="4c186-161">사이트에서 포털 시작을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-161">Delete a portal launch on the site</span></span>
1. <span data-ttu-id="4c186-162">포털 시작 웨이브를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-162">Create a Portal launch Wave.</span></span>
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="4c186-163">다음 명령을 실행 하 여 사이트에 대해 예약 되거나 진행 중인 포털 시작을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. <span data-ttu-id="4c186-164">모든 사용자에 대해 리디렉션이 발생 하지 않음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c186-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="4c186-165">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="4c186-165">Learn more</span></span>
[<span data-ttu-id="4c186-166">SharePoint Online에서 포털 시작 롤아웃 계획 계획</span><span class="sxs-lookup"><span data-stu-id="4c186-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
