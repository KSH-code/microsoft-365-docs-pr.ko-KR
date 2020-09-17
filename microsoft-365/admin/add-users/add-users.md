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
description: 동시에 Microsoft 365에 사용자를 추가 하 고 라이선스를 할당 하는 방법에 대해 알아봅니다.
ms.date: 07/01/2020
ms.openlocfilehash: 95f84ead009b7510699e467bf5f12bf32d8097d8
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948799"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="32aa5-103">사용자 추가 및 동시에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="32aa5-103">Add users and assign licenses at the same time</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="32aa5-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-104">The admin center is changing.</span></span> <span data-ttu-id="32aa5-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32aa5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="32aa5-106">팀 구성원은 각각 사용자 계정을 사용 하 여 [비즈니스용 Microsoft 365](https://www.microsoft.com/microsoft-365/business)에 로그인 하 고 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-106">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="32aa5-107">사용자 계정을 추가 하는 가장 쉬운 방법은 Microsoft 365 관리 센터에서 한 번에 하나씩 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-107">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="32aa5-108">이 단계를 수행한 후에는 사용자에 게 Microsoft 365 라이선스, 로그인 자격 증명 및 Microsoft 365 사서함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-108">After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="32aa5-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="32aa5-109">Before you begin</span></span>

<span data-ttu-id="32aa5-110">사용자를 추가 하 고 라이선스를 할당 하려면 전역, 라이선스 또는 사용자 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-110">You must be a Global, License, or a User admin to add users and assign licenses.</span></span> <span data-ttu-id="32aa5-111">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32aa5-111">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="watch-add-users-in-the-admin-center"></a><span data-ttu-id="32aa5-112">시청: 관리 센터에서 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="32aa5-112">Watch: Add users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="32aa5-113">비디오에서 사용 하는 단계는 사용자 추가를 위한 다른 출발점을 보여 주지만 나머지 단계는 다음 절차와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-113">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time"></a><span data-ttu-id="32aa5-114">한 번에 하나씩 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="32aa5-114">Add users one at a time</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="32aa5-115"><https://admin.microsoft.com> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-115">Go to the admin center at <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="32aa5-116">**사용자** > **활성 사용자**로 이동 하 여 **사용자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-116">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="32aa5-117">기본 **설정** 창에서 기본 사용자 정보를 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-117">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="32aa5-118">**이름** 성과 이름, 표시 이름 및 사용자 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-118">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="32aa5-119">**도메인** 사용자 계정에 대 한 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-119">**Domain** Choose the domain for the user's account.</span></span> <span data-ttu-id="32aa5-120">예를 들어 사용자 이름이 Jakob이 고 도메인이 contoso.com 이면 jakob@contoso.com를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-120">For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="32aa5-121">**암호 설정** 자동 생성 된 암호를 사용 하거나 사용자의 강력한 암호를 직접 만들려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-121">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="32aa5-122">사용자는 90 일 후 암호를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-122">The user must change their password after 90 days.</span></span> <span data-ttu-id="32aa5-123">또는 **이 사용자가 처음 로그인 할 때 암호를 변경**하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-123">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="32aa5-124">사용자를 추가할 때 전자 메일로 암호를 보낼지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-124">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="32aa5-125">**제품 라이선스 할당** 창에서 사용자에 대 한 적절 한 위치 및 라이선스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-125">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="32aa5-126">사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-126">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="32aa5-127">**앱** 을 확장 하 고 앱을 선택 하거나 선택을 취소 하 여 사용자에 게 라이선스가 있는 앱을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-127">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="32aa5-128">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-128">Select **Next**.</span></span>
5. <span data-ttu-id="32aa5-129">**선택적 설정** 창에서 **역할** 을 확장 하 여이 사용자를 관리자로 설정 합니다. **프로필 정보** 를 확장 하 여 사용자에 대 한 추가 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-129">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="32aa5-130">**다음**을 선택 하 고 새 사용자의 설정을 검토 하 고 원하는 대로 변경한 다음 **추가 완료**를 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-130">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="32aa5-131"><https://portal.office.de/adminportal> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-131">Go to the admin center at <https://portal.office.de/adminportal>.</span></span>
2. <span data-ttu-id="32aa5-132">**사용자** > **활성 사용자**로 이동 하 여 **사용자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-132">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="32aa5-133">**새 사용자** 창에서 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-133">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="32aa5-134">작업이 완료 되 면 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-134">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="32aa5-135">**이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-135">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="32aa5-136">**도메인** 예를 들어 사용자 이름이 Jakob이 고 도메인이 contoso.com 이면 jakob@contoso.com를 입력 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-136">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="32aa5-137">**연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-137">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="32aa5-138">**암호** 자동 생성 된 암호를 사용 하거나 확장 하 여 사용자에 대 한 강력한 암호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-138">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="32aa5-139">90 일 후에는 암호를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-139">They must change their password after 90 days.</span></span> <span data-ttu-id="32aa5-140">또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정**할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-140">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="32aa5-141">**역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-141">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="32aa5-p109">**제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="32aa5-144"><https://portal.partner.microsoftonline.cn> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-144">Go to the admin center at <https://portal.partner.microsoftonline.cn>.</span></span>
2. <span data-ttu-id="32aa5-145">**사용자** > **활성 사용자**로 이동 하 여 **사용자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-145">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="32aa5-146">**새 사용자** 창에서 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-146">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="32aa5-147">작업이 완료 되 면 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-147">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="32aa5-148">**이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-148">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="32aa5-149">**도메인** 예를 들어 사용자 이름이 Jakob이 고 도메인이 contoso.com 이면 jakob@contoso.com를 입력 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-149">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="32aa5-150">**연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-150">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="32aa5-151">**암호** 자동 생성 된 암호를 사용 하거나 확장 하 여 사용자에 대 한 강력한 암호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-151">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="32aa5-152">90 일 후에는 암호를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-152">They must change their password after 90 days.</span></span> <span data-ttu-id="32aa5-153">또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정**할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-153">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="32aa5-154">**역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-154">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="32aa5-p112">**제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-p112">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="32aa5-157">동시에 여러 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="32aa5-157">Add multiple users at the same time</span></span>

<span data-ttu-id="32aa5-158">다음 방법 중 하나를 사용 하 여 여러 사용자를 동시에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-158">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="32aa5-159">**스프레드시트를 사용 하 여 사용자를 대량으로 추가 합니다.**</span><span class="sxs-lookup"><span data-stu-id="32aa5-159">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="32aa5-160">동시 [에 여러 사용자 추가](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32aa5-160">See [Add several users at the same time](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time).</span></span>
- <span data-ttu-id="32aa5-161">**계정 추가 및 라이선스 할당을 자동화 합니다.**</span><span class="sxs-lookup"><span data-stu-id="32aa5-161">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="32aa5-162">[Microsoft 365 PowerShell을 사용 하 여 사용자 계정 만들기를](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32aa5-162">See [Create user accounts with Microsoft 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell).</span></span> <span data-ttu-id="32aa5-163">Windows PowerShell cmdlet을 사용 하는 것이 이미 익숙한 경우이 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-163">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="32aa5-164">**ActiveDirectory 사용**</span><span class="sxs-lookup"><span data-stu-id="32aa5-164">**Using ActiveDirectory?**</span></span> <span data-ttu-id="32aa5-165">[Microsoft 365에 대 한 디렉터리 동기화를 설정](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-165">[Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="32aa5-166">Microsoft 365에서 Azure AD Connect 도구를 사용 하 여 Active Directory 사용자 계정 및 기타 Active Directory 개체를 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-166">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="32aa5-167">동기화하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-167">The sync only adds the user accounts.</span></span> <span data-ttu-id="32aa5-168">동기화 된 사용자에 게 라이선스를 할당 해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-168">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="32aa5-169">**Exchange에서 마이그레이션 여부**</span><span class="sxs-lookup"><span data-stu-id="32aa5-169">**Migrating from Exchange?**</span></span> <span data-ttu-id="32aa5-170">[여러 전자 메일 계정을 Office 365로 마이그레이션하는 방법을](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32aa5-170">See [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="32aa5-171">두 개 이상의 사서함을 Microsoft 365로 마이그레이션하는 경우, 단계적으로 또는 하이브리드 Exchange 방법을 사용 하 여 사용자를 마이그레이션의 일부로 자동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-171">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="32aa5-172">마이그레이션하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-172">The migration only adds the user accounts.</span></span> <span data-ttu-id="32aa5-173">사용자에 게 라이선스를 할당 해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-173">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="32aa5-174">사용자에 게 라이선스를 할당 하지 않으면 유예 기간이 30 일 후에 사서함이 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-174">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="32aa5-175">Microsoft 365 관리 센터에서 [사용자에 게 라이선스를 할당](../manage/assign-licenses-to-users.md) 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-175">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="32aa5-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="32aa5-176">Next steps</span></span>

<span data-ttu-id="32aa5-177">사용자를 추가 하면 Microsoft에서 전자 메일 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-177">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="32aa5-178">이 전자 메일에는 사용자가 Microsoft 365에 로그인 할 수 있도록 개인이 사용 하는 ID와 암호가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-178">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="32aa5-179">새 암호를 전달하는 데 일반 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-179">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="32aa5-180">[직원 빠른 시작 가이드](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) 를 새 사용자와 공유 하 여 [PC 또는 Mac에 office 앱을 다운로드 하 고 설치](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 하는 방법, [모바일 장치에서 office 앱 및 전자 메일을 설정](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)하는 방법 등의 작업을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aa5-180">Share the [Employee quickstart guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="32aa5-181">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="32aa5-181">Related content</span></span>

<span data-ttu-id="32aa5-182">[Microsoft 365에 새 직원 추가](add-new-employee.md) (문서) </span><span class="sxs-lookup"><span data-stu-id="32aa5-182">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="32aa5-183">동시에 [여러 사용자 추가 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (문서) </span><span class="sxs-lookup"><span data-stu-id="32aa5-183">[Add several users at the same time to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (article)</span></span>\
<span data-ttu-id="32aa5-184">[Microsoft 365에서 사용자 복원](restore-user.md) (문서) </span><span class="sxs-lookup"><span data-stu-id="32aa5-184">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="32aa5-185">[사용자에 게 라이선스 할당](../manage/assign-licenses-to-users.md) (문서) </span><span class="sxs-lookup"><span data-stu-id="32aa5-185">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="32aa5-186">[조직에서 사용자 삭제](delete-a-user.md) (문서)</span><span class="sxs-lookup"><span data-stu-id="32aa5-186">[Delete a user from your organization](delete-a-user.md) (article)</span></span>
