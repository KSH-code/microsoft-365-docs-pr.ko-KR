---
title: 사용자 추가 및 라이선스 할당
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
description: 사용자를 추가하고 동시에 Microsoft 365에 라이선스를 할당하는 방법을 알아보세요.
ms.date: 07/01/2020
ms.openlocfilehash: 3efa32d21a21ed12041f5731296c1b033374712f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274391"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="d883d-103">사용자 추가 및 동시에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="d883d-103">Add users and assign licenses at the same time</span></span>

<span data-ttu-id="d883d-p101">팀의 각 구성원은 먼저 사용자 계정이 있어야 [Microsoft 365 비즈니스](https://www.microsoft.com/microsoft-365/business) 에디션에 로그인하고 액세스할 수 있습니다. 사용자 계정을 추가하는 가장 쉬운 방법은 Microsoft 365 관리 센터에서 한 번에 한 명씩 사용자를 추가하는 것입니다. 이 단계를 수행하면 팀 구성원은 Microsoft 365 라이선스, 로그인 자격 증명 및 Microsoft 365 사서함을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-p101">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business). The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center. After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d883d-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="d883d-107">Before you begin</span></span>

<span data-ttu-id="d883d-108">사용자를 추가하고 라이선스를 할당하려면 전역, 라이선스 또는 사용자 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-108">You must be a global, license, or a user admin to add users and assign licenses.</span></span> <span data-ttu-id="d883d-109">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d883d-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-user-in-the-admin-simplified-view"></a><span data-ttu-id="d883d-110">관리자 간소화된 보기에 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="d883d-110">Add a user in the admin simplified view</span></span>

<span data-ttu-id="d883d-111">관리 센터에 이 페이지가 표시되는 경우, **관리자 간소화된 보기** 에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-111">If you're seeing this page in the admin center, you're on the **admin simplified view**.</span></span> <span data-ttu-id="d883d-112">아래 단계에 따라 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-112">Follow the steps below to add a user.</span></span>

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="스크린샷: 간소화된 관리 센터 보기":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d883d-114"><https://admin.microsoft.com>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-114">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d883d-115"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-115">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d883d-116"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-116">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="d883d-117">**다른 사용자를 위한 계정 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-117">Select **Create an account for another person**.</span></span>
3. <span data-ttu-id="d883d-118">**사용자 계정 추가** 페이지에서 로그인하는 데 사용할 성과 이름, 표시 이름, 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-118">On the **Add a user account** page, fill in the first and last name, display name, and username they'll use to sign in.</span></span>
4. <span data-ttu-id="d883d-119">**최대 5개 전자 메일 주소** 텍스트 상자에 사용자의 전자 메일 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-119">Add the email address of the user in the **Up to 5 email addresses...** text box.</span></span> <span data-ttu-id="d883d-120">이렇게 하면 새 사용자가 Microsoft 365 서비스에 로그인하는 데 필요한 정보를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-120">This will make sure the new user gets the information they need to sign into Microsoft 365 services.</span></span>
5. <span data-ttu-id="d883d-121">이 정보를 저장하려면 **사용자 추가** 및 **로그인 정보 다운로드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-121">Select **Add user** and **Download sign-in info** if you want to save this info.</span></span>

## <a name="watch-add-users-in-the-dashboard-view"></a><span data-ttu-id="d883d-122">보기: 대시보드 보기에서 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="d883d-122">Watch: Add users in the dashboard view</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="d883d-123">비디오에 사용된 단계는 사용자를 추가하기 위한 다른 시작점을 보여주지만, 나머지 단계는 다음 절차와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-123">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a><span data-ttu-id="d883d-124">대시보드 보기에서 한 번씩 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="d883d-124">Add users one at a time in the dashboard view</span></span>

:::image type="content" source="../../media/classic-admin-center.png" alt-text="스크린샷: 관리 센터 대시보드 보기":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d883d-126"><https://admin.microsoft.com>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-126">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d883d-127"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d883d-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="d883d-129">**사용자**  >  **활성 사용자** 로 이동한 후, **사용자 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-129">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="d883d-130">**기본 설정** 창에서 사용자 정보를 입력하고 **다음** 을 택합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-130">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="d883d-131">**이름** 이름과 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-131">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="d883d-p105">**도메인** 사용자 계정의 도메인을 선택합니다. 예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com인 경우 jakob@contoso.com을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-p105">**Domain** Choose the domain for the user's account. For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="d883d-134">**암호 설정** 자동으로 생성되는 암호를 사용하거나 사용자에 대해 강력한 암호를 만들지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-134">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="d883d-135">사용자는 90일 후에 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-135">The user must change their password after 90 days.</span></span> <span data-ttu-id="d883d-136">또는 **사용자가 처음 로그인할 때 암호를 변경하도록 요구** 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-136">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="d883d-137">사용자가 추가될 때 암호를 전자 메일로 보낼지 여부를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="d883d-137">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="d883d-138">**제품 라이선스 할당** 창에서 사용자의 위치와 적절한 라이선스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-138">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="d883d-139">사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-139">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="d883d-140">**앱** 을 확장하고 앱을 선택하거나 선택을 선택 해제 사용자에게 라이선스가 있는 앱을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-140">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="d883d-141">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-141">Select **Next**.</span></span>
5. <span data-ttu-id="d883d-142">**선택적 설정** 창에서 **역할** 을 확장하여 이 사용자를 관리자로 만듭니다. **프로필 정보** 를 확장하여 사용자에 대한 추가 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-142">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="d883d-143">**다음** 을 선택하고 새 사용자의 설정을 검토하고 원하는 대로 변경한 다음 **추가 완료**, **닫기** 를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-143">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="d883d-144">동시에 여러 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="d883d-144">Add multiple users at the same time</span></span>

<span data-ttu-id="d883d-145">다음 방법 중 원하는 방법을 사용하여 동시에 여러 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-145">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="d883d-146">**스프레드시트를 사용하여 사용자를 일괄 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="d883d-146">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="d883d-147">[동시에 여러 사용자 추가](../../enterprise/add-several-users-at-the-same-time.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d883d-147">See [Add several users at the same time](../../enterprise/add-several-users-at-the-same-time.md).</span></span>
- <span data-ttu-id="d883d-148">**계정을 추가하고 라이선스를 할당하는 작업을 자동화합니다.**</span><span class="sxs-lookup"><span data-stu-id="d883d-148">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="d883d-149">[Microsoft 365 PowerShell을 사용하여 사용자 계정 만들기](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d883d-149">See [Create user accounts with Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="d883d-150">Windows PowerShell cmdlet 사용에 익숙한 경우 이 방법을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="d883d-150">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="d883d-151">**ActiveDirectory를 사용하나요?**</span><span class="sxs-lookup"><span data-stu-id="d883d-151">**Using ActiveDirectory?**</span></span> <span data-ttu-id="d883d-152">[Microsoft 365의 디렉터리 동기화 설정](../../enterprise/set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="d883d-152">[Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md).</span></span> <span data-ttu-id="d883d-153">Microsoft 365에서 Azure AD Connect 도구를 사용하여 Active Directory 사용자 계정 및 기타 Active Directory 개체를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-153">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="d883d-154">동기화를 수행하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-154">The sync only adds the user accounts.</span></span> <span data-ttu-id="d883d-155">동기화된 사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-155">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="d883d-156">**Exchange에서 마이그레이션하나요?**</span><span class="sxs-lookup"><span data-stu-id="d883d-156">**Migrating from Exchange?**</span></span> <span data-ttu-id="d883d-157">[Office 365로 여러 전자 메일 계정을 마이그레이션하는 방법](/Exchange/mailbox-migration/mailbox-migration)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d883d-157">See [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="d883d-158">단독형, 미리 구성된 또는 하이브리드 Exchange 방법을 사용하여 여러 사서함을 Microsoft 365로 마이그레이션하는 경우 마이그레이션의 일환으로 사용자가 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-158">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="d883d-159">마이그레이션하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-159">The migration only adds the user accounts.</span></span> <span data-ttu-id="d883d-160">사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-160">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="d883d-161">사용자에게 라이선스를 할당하지 않은 경우 30일의 유예 기간 후에 해당 사서함이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-161">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="d883d-162">Microsoft 365 관리 센터에서 [사용자에게 라이선스를 할당](../manage/assign-licenses-to-users.md)하는 방법을 배워보세요.</span><span class="sxs-lookup"><span data-stu-id="d883d-162">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d883d-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d883d-163">Next steps</span></span>

<span data-ttu-id="d883d-164">사용자를 추가한 후 Microsoft에서 전자 메일 알림을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-164">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="d883d-165">전자 메일에는 사용자가 Microsoft 365에 로그인할 수 있도록 해당 사용자의 사용자 ID와 암호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-165">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="d883d-166">새 암호를 알려 주기 위한 일반 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d883d-166">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="d883d-167">[직원 빠른 시작 가이드](../../business-video/employee-quick-setup.md)를 새 사용자와 공유하여 [PC 또는 Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)에서 Office 앱을 다운로드하고 설치하는 방법, [모바일 장치에서 Office 앱 및 전자 메일을 설정](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)하는 방법 등을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="d883d-167">Share the [Employee quickstart guide](../../business-video/employee-quick-setup.md) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="d883d-168">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d883d-168">Related content</span></span>

<span data-ttu-id="d883d-169">[Microsoft 365에 새 직원 추가](add-new-employee.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="d883d-169">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="d883d-170">[Microsoft 365 앱에 동시에 여러 사용자 추가](../../enterprise/add-several-users-at-the-same-time.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="d883d-170">[Add several users at the same time to Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (article)</span></span>\
<span data-ttu-id="d883d-171">[Microsoft 365의 사용자 복원](restore-user.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="d883d-171">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="d883d-172">[사용자에게 라이선스 할당](../manage/assign-licenses-to-users.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="d883d-172">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="d883d-173">[조직에서 사용자 삭제](delete-a-user.md)(문서)\</span><span class="sxs-lookup"><span data-stu-id="d883d-173">[Delete a user from your organization](delete-a-user.md) (article)</span></span>
