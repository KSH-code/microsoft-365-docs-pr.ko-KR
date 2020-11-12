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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999594"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="c8760-103">포털 시작 스케줄러를 사용 하 여 포털 시작</span><span class="sxs-lookup"><span data-stu-id="c8760-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="c8760-104">새 포털에 대 한 물결을 설정 하는 테 넌 트 관리자의 기능을 먼저 확인 하 여 포털 시작 스케줄러를 사용 하 여 포털을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="c8760-105">그런 다음 관리자는 활성 물결에 사용자가 있는지 여부에 따라 요청 리디렉션을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="c8760-106">성공적인 포털을 시작 하는 방법에 대 한 자세한 내용은 [정상 포털 만들기, 시작 및 유지 관리](https://go.microsoft.com/fwlink/?linkid=2105838)에서 자세히 설명 하는 기본 원칙, 모범 사례 및 권장 사항을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c8760-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="c8760-107">앱 설치</span><span class="sxs-lookup"><span data-stu-id="c8760-107">App setup</span></span>
1. <span data-ttu-id="c8760-108">`Microsoft.Online.SharePoint.PowerShell`제어판을 통해 컴퓨터에서 기존 프로그램이 있으면 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="c8760-109">PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` 통과</span><span class="sxs-lookup"><span data-stu-id="c8760-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="c8760-110">SharePoint Online에 연결</span><span class="sxs-lookup"><span data-stu-id="c8760-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="c8760-111">Windows에서 [SharePoint Online 관리 셸을](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="c8760-112">관리자 권한으로 테 넌 트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="c8760-113">메시지가 표시 되 면 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="c8760-114">기존 설치 프로그램을 가져오기 위한 명령</span><span class="sxs-lookup"><span data-stu-id="c8760-114">Command to get an existing setup</span></span>

<span data-ttu-id="c8760-115">기존 포털 시작 구성을 보려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="c8760-116">통과 `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="c8760-117">`-DisplayFormat Raw`웨이브 컬렉션을 raw 입력 형식으로 서식이 지정 된 경우 추가 매개 변수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="c8760-118">양방향 리디렉션 명령</span><span class="sxs-lookup"><span data-stu-id="c8760-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="c8760-119">이전 사이트 사용자를 미리 구성 된 방식으로 새 사이트로 마이그레이션하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="c8760-120">포털 시작 물결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="c8760-121">이 작업은 초기 릴리스 테스트 단계 에서만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="c8760-122">변경의 영향을 즉시 테스트 하려면 첫 번째 물결이 `LaunchDateUtc` 현재 날짜로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="c8760-123">이 플래그를 지정 하지 않으면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="c8760-124">이 오류는 프로덕션에서 시작을 최소 7 일 이상으로 예약 해야 하기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="c8760-125">유효성 검사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-125">Complete validation.</span></span>
  - <span data-ttu-id="c8760-126">리디렉션이 서비스 전체에서 구성을 완료 하는 데 최대 5 분이 걸릴 수 있으므로 계속 하기 전에 잠시 기다려 주십시오.</span><span class="sxs-lookup"><span data-stu-id="c8760-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="c8760-127">로 지정 된 사용자에 게 로그인 하는 경우 `WaveOverrideUsers` 아무 것도 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="c8760-128">탐색 한 사이트를 그대로 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="c8760-129">보기 관리자에 게 속하는 사용자와 로그인 *합니다.*</span><span class="sxs-lookup"><span data-stu-id="c8760-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="c8760-130">이전 사이트로 이동 하 여 새 사이트로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="c8760-131">새 사이트로 이동 하 여 새 사이트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="c8760-132">*VIEWER SG2* 에서 사용자에 게 로그온 하 여 이전 사이트로 이동한 후 이전 사이트를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="c8760-133">새 사이트로 이동 하 여 이전 사이트로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="c8760-134">포털 시작을 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="c8760-135">시작 물결을 일시 중지 해야 하는 경우 "x" 일 수 동안 일시 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="c8760-136">플래그를 `Status` 일시 중지로 설정 하면 예정 된 모든 웨이브 progressions를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="c8760-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="c8760-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="c8760-138">모든 사용자가 이전 사이트로 리디렉션되는 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="c8760-139">포털 시작 진행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="c8760-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="c8760-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="c8760-141">리디렉션이 이제 복원 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="c8760-142">포털을 삭제 하 여 설치 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="c8760-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="c8760-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="c8760-144">모든 사용자에 대해 리디렉션이 발생 하지 않음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="c8760-145">임시 페이지로의 리디렉션 명령</span><span class="sxs-lookup"><span data-stu-id="c8760-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="c8760-146">이전 사이트가 없고, 새 포털 페이지에서 웨이브에서 연결 되지 않은 사용자를 생략 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="c8760-147">사이트에서 임시 페이지를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="c8760-148">포털 시작 웨이브를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="c8760-149">유효성 검사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-149">Complete validation.</span></span>

  - <span data-ttu-id="c8760-150">5 분 정도 기다린 후에 작업을 완료 하는 데 최대 5 분까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="c8760-151">*뷰어* \ 관리자에 게 속하는 사용자에 게 로그 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="c8760-152">새 사이트로 이동 하 여 새 사이트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="c8760-153">Temp 페이지로 이동 하 여 임시 페이지를 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="c8760-154">*뷰어 SG2* 에 속하는 사용자에 게 로그 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="c8760-155">새 사이트로 이동 하 여 temp 페이지로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="c8760-156">Temp 페이지로 이동 하 여 임시 페이지를 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="c8760-157">포털을 삭제 하 여 설치 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="c8760-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="c8760-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="c8760-159">모든 사용자에 대해 리디렉션이 발생 하지 않음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8760-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="c8760-160">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="c8760-160">Learn more</span></span>
[<span data-ttu-id="c8760-161">SharePoint Online에서 포털 시작 롤아웃 계획 계획</span><span class="sxs-lookup"><span data-stu-id="c8760-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)