---
title: Microsoft 365 관리 센터 관리자 역할 할당
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 사용자가 관리 센터에서 특정 작업을 수행할 수 있도록 비즈니스의 사용자 또는 여러 사용자에게 관리자 역할을 할당하는 방법을 설명합니다.
ms.openlocfilehash: cfc4a7e106ca343435777aba1d0b9836f90a6f44
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904507"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="6f19a-103">관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="6f19a-103">Assign admin roles</span></span>

<span data-ttu-id="6f19a-104">Microsoft 비즈니스 구독을 구입한 사람인 경우 전역 관리자입니다. 즉, 구독의 제품을 무제한으로 제어할 수 있으며 대부분의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="6f19a-105">자세한 내용은 [관리자 역할 정보](about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f19a-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="6f19a-106">새 사용자를 추가할 때 관리자 역할을 할당하지 않은 경우 해당  사용자는 사용자 역할에 있으며 Microsoft 관리 센터에 대한 관리자 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="6f19a-107">하지만 작업을 완료하는 데 도움이 필요한 경우 사용자에게 관리자 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="6f19a-108">예를 들어 암호를 다시 설정하는 데 도움이 되는 누군가가 필요한 경우 전역 관리자 역할을 할당하지 말고 암호 관리자 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="6f19a-109">데이터 및 온라인 비즈니스에 무제한으로 액세스할 수 있는 전역 관리자가 너무 많은 경우 보안 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="6f19a-110">시청: 관리자 추가.</span><span class="sxs-lookup"><span data-stu-id="6f19a-110">Watch: Add an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="6f19a-111">이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f19a-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="6f19a-112">관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="6f19a-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="6f19a-113">다음 두 가지 방법으로 사용자에게 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="6f19a-114">사용자의 세부 정보 및 **역할** 관리로 이동하여 사용자에게 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="6f19a-115">또는 역할로 **이동하여** 역할을 선택한 다음 여러 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="6f19a-116">역할을 사용하여 사용자에게 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="6f19a-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="6f19a-117">관리 센터에서 역할  역할로 이동하여 조직에 사용할 수 있는 모든 관리자 >  역할을 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f19a-117">In the admin center, go to **Roles** > **Roles** to view all of the admin roles available for your organization.</span></span>
2. <span data-ttu-id="6f19a-118">사용자를 할당할 관리자 역할을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-118">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="6f19a-119">할당된 **관리자 추가** > **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6f19a-119">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="6f19a-120">사용자의 표시 이름  또는 사용자 이름을 입력한 다음 제안 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-120">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="6f19a-121">완료될 때까지 여러 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-121">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="6f19a-122">**저장을** 선택한 다음 사용자가 할당된 관리자 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-122">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="6f19a-123">활성 사용자의 관리자 역할에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="6f19a-123">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="6f19a-124">관리 센터에서 사용자 활성 **사용자** > [페이지로](https://go.microsoft.com/fwlink/p/?linkid=834822) 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-124">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="6f19a-125">활성 **사용자 페이지에서** 관리자 역할을 변경할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-125">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="6f19a-126">플라이아웃 창에서 역할 옆의 **역할** **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6f19a-126">In the flyout pane, next to **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="6f19a-127">사용자에게 할당할 관리자 역할을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-127">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="6f19a-128">원하는 역할이 없는 경우 목록 맨 아래에서 **모두** 표시를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-128">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6f19a-129">관리 센터에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-129">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6f19a-130">활성 **사용자 페이지에서** 관리자 역할을 변경할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-130">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="6f19a-131">플라이아웃 창에서 역할 옆의 **편집** 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6f19a-131">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="6f19a-132">편집 옵션이 없는 경우  편집할 수 있는 권한이 없는 것이고 다른 사용자에게 관리자 역할을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-132">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="6f19a-133">비즈니스의 전역 관리자에게 역할을 할당해달고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-133">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="6f19a-134">중소기업에서 비즈니스 소유자(구독을 구매한 사람)는 전역 관리자입니다. 대기업에서 IT 부서의 주요 직원은 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-134">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="6f19a-135">사용자 **지정된 관리자를** 선택하여 사용자 지정한 역할 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-135">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="6f19a-136">각 역할에 대한 설명은 관리자 역할 [정보를 참조하세요.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6f19a-136">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6f19a-137">관리 센터에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-137">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6f19a-138">활성 **사용자 페이지에서** 관리자 역할을 변경할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-138">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="6f19a-139">플라이아웃 창에서 역할 옆의 **편집** 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6f19a-139">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="6f19a-140">편집 옵션이 없는 경우  편집할 수 있는 권한이 없는 것이고 다른 사용자에게 관리자 역할을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-140">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="6f19a-141">비즈니스의 전역 관리자에게 역할을 할당해달고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-141">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="6f19a-142">중소기업에서 비즈니스 소유자(구독을 구매한 사람)는 전역 관리자입니다. 대기업에서 IT 부서의 주요 직원은 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-142">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="6f19a-143">사용자 **지정된 관리자를** 선택하여 사용자 지정한 역할 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-143">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="6f19a-144">각 역할에 대한 설명은 관리자 역할 [정보를 참조하세요.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6f19a-144">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="6f19a-145">여러 사용자에게 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="6f19a-145">Assign admin roles to multiple users</span></span>

<span data-ttu-id="6f19a-146">PowerShell을 알고 있는 경우 PowerShell을 통해 사용자 계정에 역할 [할당을 참조합니다.](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="6f19a-146">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="6f19a-147">이 방법은 수백 명의 사용자에게 역할을 할당하는 경우 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-147">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="6f19a-148">수십 명의 사용자에게 역할을 할당하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-148">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="6f19a-149">조직에서 관리자 역할 확인</span><span class="sxs-lookup"><span data-stu-id="6f19a-149">Check admin roles in your organization</span></span>

<span data-ttu-id="6f19a-150">다른 사용자에게 관리자 역할을 할당하기 위해 올바른 권한이 없는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-150">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="6f19a-151">올바른 사용 권한이 있는지 확인하거나 다른 관리자에게 역할을 할당해달고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-151">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="6f19a-152">다음 두 가지 방법으로 관리자 역할 권한을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-152">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="6f19a-153">사용자의 세부 정보로 이동하여 계정 페이지의 역할 **아래를** 볼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-153">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="6f19a-154">또는 역할로 **이동하여** 관리자 역할을 선택하고 할당된 관리자를 선택하여 할당된 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f19a-154">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="6f19a-155">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6f19a-155">Related articles</span></span>

[<span data-ttu-id="6f19a-156">Microsoft 365 관리자 역할 정보</span><span class="sxs-lookup"><span data-stu-id="6f19a-156">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

[<span data-ttu-id="6f19a-157">Azure Active Directory의 관리자 역할 권한</span><span class="sxs-lookup"><span data-stu-id="6f19a-157">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)

[<span data-ttu-id="6f19a-158">PowerShell을 통해 사용자 계정에 역할 할당</span><span class="sxs-lookup"><span data-stu-id="6f19a-158">Assign roles to user accounts with PowerShell</span></span>](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)

[<span data-ttu-id="6f19a-159">파트너 관계 승인 또는 제거</span><span class="sxs-lookup"><span data-stu-id="6f19a-159">Authorize or remove partner relationships</span></span>](../misc/add-partner.md)