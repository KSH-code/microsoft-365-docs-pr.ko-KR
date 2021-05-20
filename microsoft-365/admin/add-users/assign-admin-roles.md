---
title: 관리자 역할 Microsoft 365 관리자 센터 할당
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
description: 관리자 센터에서 특정 작업을 수행할 수 있도록 비즈니스의 사용자 또는 여러 사용자에게 관리자 역할을 할당하는 방법을 알아봅니다.
ms.openlocfilehash: f23a30cfd1be53982572d745d476558c3be615e6
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571868"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="45b8a-103">관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="45b8a-103">Assign admin roles</span></span>

<span data-ttu-id="45b8a-104">Microsoft 비즈니스 구독을 구매한 사용자인 경우 글로벌 관리자입니다. 즉, 구독에서 제품을 무제한으로 제어할 수 있으며 대부분의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="45b8a-105">자세한 내용은 [관리자 역할 정보](about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45b8a-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="45b8a-106">새 사용자를 추가할 때 관리자 역할을 할당하지 않으면 *사용자 역할에* 있으며 Microsoft 관리자 센터에 관리자 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="45b8a-107">그러나 작업을 수행하는 데 도움이 필요한 경우 사용자에게 관리자 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="45b8a-108">예를 들어 암호를 재설정하는 데 도움이 되는 사람이 필요한 경우 전역 관리자 역할을 할당해서는 안 되며 암호 관리자 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="45b8a-109">데이터 및 온라인 비즈니스에 무제한으로 액세스할 수 있는 전역 관리자가 너무 많을 경우 보안의 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="45b8a-110">보기: 관리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-110">Watch: Add an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="45b8a-111">이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](../../business-video/index.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45b8a-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="45b8a-112">관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="45b8a-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="45b8a-113">다음과 같은 2가지 방법으로 역할에 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="45b8a-114">사용자의 세부 정보 및 관리 **역할을** 사용하여 사용자에게 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="45b8a-115">또는 **역할로** 이동하여 역할을 선택한 다음 여러 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="45b8a-116">역할 사용 하 여 사용자에 게 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="45b8a-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="45b8a-117">관리 센터에서 **역할로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="45b8a-117">In the admin center, go to **Roles**.</span></span> <span data-ttu-id="45b8a-118">Azure **AD** 또는 **Intune** 탭을 선택하여 조직에서 사용할 수 있는 관리자 역할을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-118">Choose the **Azure AD** or **Intune** tabs to view the admin roles available for your organization.</span></span>
2. <span data-ttu-id="45b8a-119">사용자를 할당할 관리자 역할을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="45b8a-120">할당된 관리자 추가 를 **선택합니다.** > </span><span class="sxs-lookup"><span data-stu-id="45b8a-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="45b8a-121">사용자의 **표시 이름** 또는 **사용자 이름을** 입력한 다음 제안 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="45b8a-122">완료될 때까지 여러 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="45b8a-123">**저장을** 선택한 다음 사용자가 할당된 관리자 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="45b8a-124">활성 사용자의 관리자 역할에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="45b8a-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="45b8a-125">관리 센터에서 **사용자** > [활성 사용자](https://go.microsoft.com/fwlink/p/?linkid=834822) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="45b8a-126">Active **사용자** 페이지에서 변경하려는 관리자 역할이 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="45b8a-127">플라이아웃 창에서 **역할** 아래에서 **역할 관리를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-127">In the flyout pane, under **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="45b8a-128">사용자에게 할당할 관리자 역할을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="45b8a-129">원하는 역할이 표시되지 않으면 목록 하단에 모두 **표시를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="45b8a-130">관리 센터에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="45b8a-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="45b8a-131">Active **사용자** 페이지에서 변경하려는 관리자 역할이 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="45b8a-132">플라이아웃 창에서 **역할** 옆에 있는 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="45b8a-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="45b8a-133">**편집** 옵션이 표시되지 않으면 편집 권한이 없으며 다른 사람에게 관리자 역할을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="45b8a-134">비즈니스의 글로벌 관리자에게 역할을 할당하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="45b8a-135">중소기업에서 비즈니스 소유자(구독을 구입한 사람)는 글로벌 관리자입니다. 대기업에서는 IT 부서의 핵심 담당자가 글로벌 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="45b8a-136">**사용자 지정 관리자를** 선택하여 사용자 지정한 역할 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="45b8a-137">각 역할에 대한 설명은 [관리자 역할 에 대해 참조하세요.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="45b8a-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="45b8a-138">관리 센터에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="45b8a-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="45b8a-139">Active **사용자** 페이지에서 변경하려는 관리자 역할이 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="45b8a-140">플라이아웃 창에서 **역할** 옆에 있는 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="45b8a-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="45b8a-141">**편집** 옵션이 표시되지 않으면 편집 권한이 없으며 다른 사람에게 관리자 역할을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="45b8a-142">비즈니스의 글로벌 관리자에게 역할을 할당하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="45b8a-143">중소기업에서 비즈니스 소유자(구독을 구입한 사람)는 글로벌 관리자입니다. 대기업에서는 IT 부서의 핵심 담당자가 글로벌 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="45b8a-144">**사용자 지정 관리자를** 선택하여 사용자 지정한 역할 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="45b8a-145">각 역할에 대한 설명은 [관리자 역할 에 대해 참조하세요.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="45b8a-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="45b8a-146">여러 사용자에게 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="45b8a-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="45b8a-147">PowerShell을 알고 있는 경우 [PowerShell을 사용하여 사용자 계정에 역할 할당을 참조하세요.](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="45b8a-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="45b8a-148">이 방법은 수백 명의 사용자에게 역할을 할당하는 경우 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="45b8a-149">수십 명의 사용자에게 역할을 할당하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="45b8a-150">조직의 관리자 역할 확인</span><span class="sxs-lookup"><span data-stu-id="45b8a-150">Check admin roles in your organization</span></span>

<span data-ttu-id="45b8a-151">다른 사용자에게 관리자 역할을 할당할 수 있는 올바른 권한이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-151">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="45b8a-152">올바른 권한이 있는지 확인하거나 다른 관리자에게 역할을 할당하도록 요청하십시오.</span><span class="sxs-lookup"><span data-stu-id="45b8a-152">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="45b8a-153">다음과 같은 2가지 방법으로 관리자 역할 권한을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-153">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="45b8a-154">사용자의 세부 정보로 이동하여 **계정** 페이지의 **역할** 아래를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-154">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="45b8a-155">또는 **역할로** 이동하여 관리자 역할을 선택하고 할당된 관리자를 선택하여 할당된 사용자를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b8a-155">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="45b8a-156">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="45b8a-156">Related content</span></span>

<span data-ttu-id="45b8a-157">[관리자 역할 Microsoft 365](about-admin-roles.md) 대해(문서)</span><span class="sxs-lookup"><span data-stu-id="45b8a-157">[About Microsoft 365 admin roles](about-admin-roles.md) (article)</span></span>

<span data-ttu-id="45b8a-158">[Azure Active Directory 관리자 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 권한(문서)</span><span class="sxs-lookup"><span data-stu-id="45b8a-158">[Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (article)</span></span>

<span data-ttu-id="45b8a-159">[PowerShell(문서)을 사용하여 사용자 계정에 역할 할당](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="45b8a-159">[Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (article)</span></span>

<span data-ttu-id="45b8a-160">[파트너 관계 승인 또는](../misc/add-partner.md) 삭제(기사)</span><span class="sxs-lookup"><span data-stu-id="45b8a-160">[Authorize or remove partner relationships](../misc/add-partner.md) (article)</span></span>