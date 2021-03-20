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
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 사용자를 추가하고 동시에 Microsoft 365에 라이선스를 할당하는 방법을 알아보세요.
ms.date: 07/01/2020
ms.openlocfilehash: 3c752bd12c0aeb3806ad7d5d90373aad13730944
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906303"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="c18b7-103">사용자 추가 및 동시에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="c18b7-103">Add users and assign licenses at the same time</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c18b7-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-104">The admin center is changing.</span></span> <span data-ttu-id="c18b7-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c18b7-106">각 팀의 사용자는 [비즈니스용 Microsoft 365](https://www.microsoft.com/microsoft-365/business)에 로그인하여 액세스하기 위해 사용자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-106">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="c18b7-107">사용자 계정을 추가하는 가장 쉬운 방법은 Microsoft 365 관리 센터에서 계정을 한 번에 하나씩 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-107">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c18b7-108">이 단계를 진행하고 나면 사용자가 Microsoft 365 라이선스, 로그인 자격 증명 및 Microsoft 365 사서함을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-108">After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c18b7-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c18b7-109">Before you begin</span></span>

<span data-ttu-id="c18b7-110">사용자를 추가하고 라이선스를 할당하려면 전역, 라이선스 또는 사용자 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-110">You must be a global, license, or a user admin to add users and assign licenses.</span></span> <span data-ttu-id="c18b7-111">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-111">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="watch-add-users-in-the-admin-center"></a><span data-ttu-id="c18b7-112">시청: 관리 센터에서 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="c18b7-112">Watch: Add users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="c18b7-113">비디오에 사용된 단계는 사용자를 추가하기 위한 다른 시작점을 보여주지만, 나머지 단계는 다음 절차와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-113">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time"></a><span data-ttu-id="c18b7-114">사용자를 한 번에 한 명씩 추가</span><span class="sxs-lookup"><span data-stu-id="c18b7-114">Add users one at a time</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c18b7-115"><https://admin.microsoft.com>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-115">Go to the admin center at <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="c18b7-116">**사용자** > **활성 사용자** 로 이동한 후, **사용자 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-116">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="c18b7-117">**기본 설정** 창에서 사용자 정보를 입력하고 **다음** 을 택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-117">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="c18b7-118">**이름** 이름과 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-118">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="c18b7-119">**도메인** 계정의 도메인을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-119">**Domain** Choose the domain for the user's account.</span></span> <span data-ttu-id="c18b7-120">예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com인 경우 jakob@contoso.com을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-120">For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="c18b7-121">**암호 설정** 자동으로 생성되는 암호를 사용하거나 사용자에 대해 강력한 암호를 만들지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-121">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="c18b7-122">사용자는 90일 후에 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-122">The user must change their password after 90 days.</span></span> <span data-ttu-id="c18b7-123">또는 **사용자가 처음 로그인할 때 암호를 변경하도록 요구** 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-123">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="c18b7-124">사용자가 추가될 때 암호를 전자 메일로 보낼지 여부를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-124">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="c18b7-125">**제품 라이선스 할당** 창에서 사용자의 위치와 적절한 라이선스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-125">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="c18b7-126">사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-126">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="c18b7-127">**앱** 을 확장하고 앱을 선택하거나 선택을 선택 해제 사용자에게 라이선스가 있는 앱을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-127">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="c18b7-128">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-128">Select **Next**.</span></span>
5. <span data-ttu-id="c18b7-129">**선택적 설정** 창에서 **역할** 을 확장하여 이 사용자를 관리자로 만듭니다. **프로필 정보** 를 확장하여 사용자에 대한 추가 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-129">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="c18b7-130">**다음** 을 선택하고 새 사용자의 설정을 검토하고 원하는 대로 변경한 다음 **추가 완료**, **닫기** 를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-130">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c18b7-131"><https://portal.office.de/adminportal>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-131">Go to the admin center at <https://portal.office.de/adminportal>.</span></span>
2. <span data-ttu-id="c18b7-132">**사용자** > **활성 사용자** 로 이동한 후, **사용자 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-132">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="c18b7-133">**새 사용자** 창에서 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-133">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="c18b7-134">완료되면 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-134">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="c18b7-135">**이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-135">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="c18b7-136">**도메인** 예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com인 경우 jakob@contoso.com을 입력하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-136">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="c18b7-137">**연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-137">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="c18b7-138">**암호** 자동 생성된 암호를 사용하거나 확장하여 강력한 암호를 지정해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-138">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="c18b7-139">사용자는 90일 후에 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-139">They must change their password after 90 days.</span></span> <span data-ttu-id="c18b7-140">또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정** 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-140">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="c18b7-141">**역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-141">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="c18b7-p109">**제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c18b7-144"><https://portal.partner.microsoftonline.cn>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-144">Go to the admin center at <https://portal.partner.microsoftonline.cn>.</span></span>
2. <span data-ttu-id="c18b7-145">**사용자** > **활성 사용자** 로 이동한 후, **사용자 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-145">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="c18b7-146">**새 사용자** 창에서 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-146">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="c18b7-147">완료되면 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-147">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="c18b7-148">**이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-148">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="c18b7-149">**도메인** 예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com인 경우 jakob@contoso.com을 입력하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-149">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="c18b7-150">**연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-150">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="c18b7-151">**암호** 자동 생성된 암호를 사용하거나 확장하여 강력한 암호를 지정해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-151">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="c18b7-152">사용자는 90일 후에 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-152">They must change their password after 90 days.</span></span> <span data-ttu-id="c18b7-153">또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정** 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-153">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="c18b7-154">**역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-154">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="c18b7-p112">**제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-p112">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="c18b7-157">동시에 여러 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="c18b7-157">Add multiple users at the same time</span></span>

<span data-ttu-id="c18b7-158">다음 방법 중 원하는 방법을 사용하여 동시에 여러 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-158">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="c18b7-159">**스프레드시트를 사용하여 사용자를 일괄 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="c18b7-159">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="c18b7-160">[동시에 여러 사용자 추가](../../enterprise/add-several-users-at-the-same-time.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-160">See [Add several users at the same time](../../enterprise/add-several-users-at-the-same-time.md).</span></span>
- <span data-ttu-id="c18b7-161">**계정을 추가하고 라이선스를 할당하는 작업을 자동화합니다.**</span><span class="sxs-lookup"><span data-stu-id="c18b7-161">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="c18b7-162">[Microsoft 365 PowerShell을 사용하여 사용자 계정 만들기](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-162">See [Create user accounts with Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="c18b7-163">Windows PowerShell cmdlet 사용에 익숙한 경우 이 방법을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-163">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="c18b7-164">**ActiveDirectory를 사용하나요?**</span><span class="sxs-lookup"><span data-stu-id="c18b7-164">**Using ActiveDirectory?**</span></span> <span data-ttu-id="c18b7-165">[Microsoft 365의 디렉터리 동기화 설정](../../enterprise/set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="c18b7-165">[Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md).</span></span> <span data-ttu-id="c18b7-166">Microsoft 365에서 Azure AD Connect 도구를 사용하여 Active Directory 사용자 계정 및 기타 Active Directory 개체를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-166">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="c18b7-167">동기화를 수행하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-167">The sync only adds the user accounts.</span></span> <span data-ttu-id="c18b7-168">동기화된 사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-168">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="c18b7-169">**Exchange에서 마이그레이션하나요?**</span><span class="sxs-lookup"><span data-stu-id="c18b7-169">**Migrating from Exchange?**</span></span> <span data-ttu-id="c18b7-170">[Office 365로 여러 전자 메일 계정을 마이그레이션하는 방법](/Exchange/mailbox-migration/mailbox-migration)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-170">See [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="c18b7-171">단독형, 미리 구성된 또는 하이브리드 Exchange 방법을 사용하여 여러 사서함을 Microsoft 365로 마이그레이션하는 경우 마이그레이션의 일환으로 사용자가 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-171">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="c18b7-172">마이그레이션하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-172">The migration only adds the user accounts.</span></span> <span data-ttu-id="c18b7-173">사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-173">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="c18b7-174">사용자에게 라이선스를 할당하지 않은 경우 30일의 유예 기간 후에 해당 사서함이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-174">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="c18b7-175">Microsoft 365 관리 센터에서 [사용자에게 라이선스를 할당](../manage/assign-licenses-to-users.md)하는 방법을 배워보세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-175">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c18b7-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c18b7-176">Next steps</span></span>

<span data-ttu-id="c18b7-177">사용자를 추가한 후 Microsoft에서 전자 메일 알림을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-177">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="c18b7-178">전자 메일에는 사용자가 Microsoft 365에 로그인할 수 있도록 해당 사용자의 사용자 ID와 암호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-178">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="c18b7-179">새 암호를 알려 주기 위한 일반 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c18b7-179">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="c18b7-180">[직원 빠른 시작 가이드](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)를 새 사용자와 공유하여 [PC 또는 Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)에서 Office 앱을 다운로드하고 설치하는 방법, [모바일 장치에서 Office 앱 및 전자 메일을 설정](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)하는 방법 등을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="c18b7-180">Share the [Employee quickstart guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="c18b7-181">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="c18b7-181">Related content</span></span>

<span data-ttu-id="c18b7-182">[Microsoft 365에 새 직원 추가](add-new-employee.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="c18b7-182">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="c18b7-183">[Microsoft 365 앱에 동시에 여러 사용자 추가](../../enterprise/add-several-users-at-the-same-time.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="c18b7-183">[Add several users at the same time to Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (article)</span></span>\
<span data-ttu-id="c18b7-184">[Microsoft 365의 사용자 복원](restore-user.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="c18b7-184">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="c18b7-185">[사용자에게 라이선스 할당](../manage/assign-licenses-to-users.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="c18b7-185">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="c18b7-186">[조직에서 사용자 삭제](delete-a-user.md)(문서)\</span><span class="sxs-lookup"><span data-stu-id="c18b7-186">[Delete a user from your organization](delete-a-user.md) (article)</span></span>