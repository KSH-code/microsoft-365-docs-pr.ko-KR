---
title: 사용자 추가 및 라이선스 할당
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 사용자를 추가하고 동시에 Microsoft 365에 라이선스를 할당하는 방법을 배워야 합니다.
ms.date: 07/01/2020
ms.openlocfilehash: 412774c9786abc01e94c5a350871f9d34586cce4
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114156"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="cf5ef-103">사용자 추가 및 동시에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="cf5ef-103">Add users and assign licenses at the same time</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cf5ef-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-104">The admin center is changing.</span></span> <span data-ttu-id="cf5ef-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="cf5ef-106">팀의 각 사용자는 비즈니스용 [Microsoft 365에](https://www.microsoft.com/microsoft-365/business)로그인하고 액세스할 수 있는 사용자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-106">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="cf5ef-107">사용자 계정을 추가하는 가장 쉬운 방법은 Microsoft 365 관리 센터에서 한 번씩 계정을 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-107">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cf5ef-108">이 단계를 진행하면 사용자에게 Microsoft 365 라이선스, 로그인 자격 증명 및 Microsoft 365 사서함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-108">After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cf5ef-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="cf5ef-109">Before you begin</span></span>

<span data-ttu-id="cf5ef-110">사용자를 추가하고 라이선스를 할당하려면 전역, 라이선스 또는 사용자 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-110">You must be a global, license, or a user admin to add users and assign licenses.</span></span> <span data-ttu-id="cf5ef-111">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-111">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="watch-add-users-in-the-admin-center"></a><span data-ttu-id="cf5ef-112">감시: 관리 센터에서 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="cf5ef-112">Watch: Add users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="cf5ef-113">비디오에 사용된 단계는 사용자를 추가하기 위한 다른 시작 지점을 보여 주지만 나머지 단계는 다음 절차와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-113">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time"></a><span data-ttu-id="cf5ef-114">한 번씩 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="cf5ef-114">Add users one at a time</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cf5ef-115"><https://admin.microsoft.com> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-115">Go to the admin center at <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="cf5ef-116">사용자  활성 > **사용자로 이동한** 다음 사용자 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-116">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="cf5ef-117">기본 **설정** 창에서 기본 사용자 정보를 입력하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-117">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="cf5ef-118">**이름** 이름과 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-118">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="cf5ef-119">**도메인** 사용자 계정의 도메인을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-119">**Domain** Choose the domain for the user's account.</span></span> <span data-ttu-id="cf5ef-120">예를 들어 사용자의 사용자 이름이 Jakob인 경우 도메인이 contoso.com 로그인할 수 jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-120">For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="cf5ef-121">**암호 설정** 자동 생성 암호를 사용하거나 사용자에 대해 강력한 암호를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-121">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="cf5ef-122">사용자는 90일 후에 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-122">The user must change their password after 90 days.</span></span> <span data-ttu-id="cf5ef-123">또는 이 사용자가 처음 로그인할 때 암호를 **변경하도록 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-123">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="cf5ef-124">사용자가 추가될 때 전자 메일로 암호를 보낼지 여부를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-124">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="cf5ef-125">제품 라이선스 **할당** 창에서 사용자의 위치 및 적절한 라이선스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-125">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="cf5ef-126">사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-126">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="cf5ef-127">앱을 **확장하고** 앱을 선택하거나 선택을 선택하여 사용자에게 라이선스가 있는 앱을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-127">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="cf5ef-128">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-128">Select **Next**.</span></span>
5. <span data-ttu-id="cf5ef-129">선택적 **설정 창에서** **역할을** 확장하여 이 사용자를 관리자로 설정합니다. 프로필 **정보를 확장하여** 사용자에 대한 추가 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-129">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="cf5ef-130">Select **Next,** review your new user's settings, make any changes you like, then select **Finish adding,** then **Close**.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-130">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cf5ef-131"><https://portal.office.de/adminportal> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-131">Go to the admin center at <https://portal.office.de/adminportal>.</span></span>
2. <span data-ttu-id="cf5ef-132">사용자  활성 > **사용자로 이동한** 다음 사용자 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-132">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="cf5ef-133">새 사용자 **창에서** 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-133">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="cf5ef-134">완료되면 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-134">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="cf5ef-135">**이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-135">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="cf5ef-136">**도메인** 예를 들어 사용자의 사용자 이름이 Jakob인 경우 도메인이 contoso.com 로그인하려면 다음을 입력하여 jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-136">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="cf5ef-137">**연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-137">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="cf5ef-138">**암호** 자동 생성 암호를 사용하거나 확장하여 사용자의 강력한 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-138">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="cf5ef-139">90일 후에 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-139">They must change their password after 90 days.</span></span> <span data-ttu-id="cf5ef-140">또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정** 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-140">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="cf5ef-141">**역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-141">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="cf5ef-p109">**제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cf5ef-144"><https://portal.partner.microsoftonline.cn> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-144">Go to the admin center at <https://portal.partner.microsoftonline.cn>.</span></span>
2. <span data-ttu-id="cf5ef-145">사용자  활성 > **사용자로 이동한** 다음 사용자 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-145">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="cf5ef-146">새 사용자 **창에서** 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-146">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="cf5ef-147">완료되면 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-147">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="cf5ef-148">**이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-148">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="cf5ef-149">**도메인** 예를 들어 사용자의 사용자 이름이 Jakob인 경우 도메인이 contoso.com 로그인할 때 사용자 이름을 입력하여 jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-149">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="cf5ef-150">**연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-150">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="cf5ef-151">**암호** 자동 생성 암호를 사용하거나 확장하여 사용자의 강력한 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-151">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="cf5ef-152">90일 후에 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-152">They must change their password after 90 days.</span></span> <span data-ttu-id="cf5ef-153">또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정** 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-153">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="cf5ef-154">**역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-154">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="cf5ef-p112">**제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-p112">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="cf5ef-157">동시에 여러 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="cf5ef-157">Add multiple users at the same time</span></span>

<span data-ttu-id="cf5ef-158">다음 방법 중 원하는 방법을 사용하여 동시에 여러 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-158">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="cf5ef-159">**스프레드시트를 사용하여 사용자 일괄 추가**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-159">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="cf5ef-160">동시에 [여러 사용자 추가를 참조합니다.](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)</span><span class="sxs-lookup"><span data-stu-id="cf5ef-160">See [Add several users at the same time](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time).</span></span>
- <span data-ttu-id="cf5ef-161">**계정 추가 및 라이선스 할당을 자동화합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-161">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="cf5ef-162">[Microsoft 365 PowerShell을](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell)사용하여 사용자 계정 만들기를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-162">See [Create user accounts with Microsoft 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell).</span></span> <span data-ttu-id="cf5ef-163">이미 cmdlet을 사용하는 방법에 익숙한 경우 이 Windows PowerShell 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-163">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="cf5ef-164">**ActiveDirectory 사용 여부**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-164">**Using ActiveDirectory?**</span></span> <span data-ttu-id="cf5ef-165">[Microsoft 365에 대한 디렉터리 동기화를 설정합니다.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</span><span class="sxs-lookup"><span data-stu-id="cf5ef-165">[Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="cf5ef-166">Azure AD Connect 도구를 사용하여 Microsoft 365에서 Active Directory 사용자 계정 및 기타 Active Directory 개체를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-166">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="cf5ef-167">동기화하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-167">The sync only adds the user accounts.</span></span> <span data-ttu-id="cf5ef-168">동기화된 사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-168">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="cf5ef-169">**Exchange에서 마이그레이션 중이신가요?**</span><span class="sxs-lookup"><span data-stu-id="cf5ef-169">**Migrating from Exchange?**</span></span> <span data-ttu-id="cf5ef-170">여러 [전자 메일 계정을 Office 365로](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)마이그레이션하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-170">See [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="cf5ef-171">컷오버, 단계적 또는 하이브리드 Exchange 방법을 사용하여 여러 사서함을 Microsoft 365로 마이그레이션하는 경우 마이그레이션의 일부로 사용자를 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-171">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="cf5ef-172">마이그레이션하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-172">The migration only adds the user accounts.</span></span> <span data-ttu-id="cf5ef-173">전자 메일 및 기타 Office 앱을 사용하려면 먼저 사용자에게 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-173">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="cf5ef-174">사용자에게 라이선스를 할당하지 않은 경우 30일의 유예 기간 후에 해당 사서함을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-174">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="cf5ef-175">Microsoft 365 관리 센터에서 사용자에게 라이선스를 할당하는 방법을 학습합니다. [](../manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="cf5ef-175">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cf5ef-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cf5ef-176">Next steps</span></span>

<span data-ttu-id="cf5ef-177">사용자를 추가하고 나면 Microsoft에서 전자 메일 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-177">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="cf5ef-178">전자 메일에는 Microsoft 365에 로그인할 수 있도록 사용자의 사용자 ID와 암호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-178">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="cf5ef-179">새 암호를 전달하는 데 일반 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ef-179">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="cf5ef-180">직원 [빠른](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) 시작 가이드를 새 사용자와 공유하여 PC 또는 [Mac에 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 앱을 다운로드하고 설치하는 방법 및 모바일 장치에서 Office 앱 및 전자 메일을 설정하는 방법과 같은 것을 [설정할 수 있습니다.](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)</span><span class="sxs-lookup"><span data-stu-id="cf5ef-180">Share the [Employee quickstart guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="cf5ef-181">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="cf5ef-181">Related content</span></span>

<span data-ttu-id="cf5ef-182">[Microsoft 365에](add-new-employee.md) 새 직원 추가(문서)</span><span class="sxs-lookup"><span data-stu-id="cf5ef-182">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="cf5ef-183">[Microsoft 365에](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) 동시에 여러 사용자 추가(문서)</span><span class="sxs-lookup"><span data-stu-id="cf5ef-183">[Add several users at the same time to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (article)</span></span>\
<span data-ttu-id="cf5ef-184">[Microsoft 365에서](restore-user.md) 사용자 복원(문서)</span><span class="sxs-lookup"><span data-stu-id="cf5ef-184">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="cf5ef-185">[사용자에게 라이선스 할당(문서)\](../manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="cf5ef-185">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="cf5ef-186">[조직에서 사용자](delete-a-user.md) 삭제(문서)</span><span class="sxs-lookup"><span data-stu-id="cf5ef-186">[Delete a user from your organization](delete-a-user.md) (article)</span></span>
