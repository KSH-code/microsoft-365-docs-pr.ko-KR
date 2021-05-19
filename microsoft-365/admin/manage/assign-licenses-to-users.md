---
title: 사용자에게 라이선스 할당
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: 제품 라이선스를 특정 사용자에게 할당할지 아니면 사용자 라이선스를 특정 제품에 할당할지 여부에 따라 라이선스를 할당합니다.
ms.date: 04/26/2021
ms.openlocfilehash: 707c1c952aa737f0aa91d886e9fa304eabe26321
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537538"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="79178-103">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="79178-103">Assign licenses to users</span></span>

<span data-ttu-id="79178-104">**활성 사용자** 페이지 또는 **라이선스** 페이지에서 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="79178-105">제품 라이선스를 특정 사용자에게 할당할지 아니면 사용자 라이선스를 특정 제품에 할당할지 여부에 따라 사용하는 방법이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="79178-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="79178-106">관리자는 조직의 사용자가 구입한 셀프 서비스 구매 구독의 라이선스를 할당하거나 할당 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="79178-107">[셀프 서비스 구매 구독을 이어 받은 다음](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)할당 또는 할당 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="79178-108">[사용자를 추가하는 동시에 라이선스를 할당하는 방법에 대해 알아봅니다.](../add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="79178-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="79178-109">시작하기 전에 다음의 조건을 만족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-109">Before you begin</span></span>

- <span data-ttu-id="79178-110">라이선스를 할당하려면 전역, 라이선스 또는 사용자 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="79178-111">자세한 내용은 [Microsoft 365 관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79178-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="79178-112">[PowerShell을 사용하여 사용자 계정에 Microsoft 365 라이선스를 할당](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-112">You can [assign Microsoft 365 licenses to user accounts with PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="79178-113">그룹 기반 라이선싱을 사용하려면 [Azure Active Directory에서 그룹 구성원으로 사용자에게 라이선스 할당](/azure/active-directory/users-groups-roles/licensing-groups-assign)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79178-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="79178-114">Sway와 같은 일부 서비스는 사용자에게 자동으로 할당되므로 개별적으로 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="79178-115">라이선스 페이지를 사용하여 사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="79178-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="79178-116">**라이선스** 페이지를 사용하여 라이선스를 할당하는 경우 특정 제품에 대한 라이선스를 최대 20명의 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="79178-117">**라이선스** 페이지에는 구독하고 있는 모든 제품이 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79178-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="79178-118">각 제품에 대한 총 라이선스 수, 할당된 라이선스 수 및 사용할 수 있는 라이선스 수를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79178-119">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="79178-120">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">라이선스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="79178-121">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="79178-122">제품을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-122">Select a product.</span></span>
3. <span data-ttu-id="79178-123">제품 세부 정보 페이지에서 **라이선스 할당** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="79178-124">**사용자에게 라이선스 할당** 창에서 이름을 입력한 다음 결과에서 해당 이름을 선택하여 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="79178-125">한 번에 최대 20명의 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="79178-126">**앱 및 서비스를 설정 또는 해제** 를 선택하여 특정 항목에 대한 액세스 권한을 할당하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="79178-127">작업을 마치면 **할당** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="79178-128">충돌이 발생한 경우 메시지가 표시되고 문제 및 수정 방법에 대해 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="79178-129">예를 들어 충돌하는 서비스를 포함하는 라이선스를 선택한 경우 각 라이선스에 포함된 서비스를 검토하라는 오류 메시지가 표시되고 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="79178-130">사용자가 액세스할 수 있는 앱 및 서비스의 변경</span><span class="sxs-lookup"><span data-stu-id="79178-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79178-131">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-131">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="79178-132">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">라이선스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="79178-133">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="79178-134">**라이선스** 페이지에서 특정 사용자에 대한 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="79178-135">오른쪽 창에서 액세스 권한을 부여 또는 제거할 앱과 서비스를 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="79178-136">작업을 마치면 **저장** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="79178-137">활성 사용자 페이지를 사용하여 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="79178-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="79178-138">**활성 사용자** 페이지를 사용하여 라이선스를 할당할 때 사용자에게 제품에 대한 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="79178-139">여러 사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="79178-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79178-140">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="79178-141">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="79178-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="79178-142">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="79178-143">라이선스를 할당하려는 사용자의 이름 옆에 원을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="79178-144">맨 위에 있는 3개의 점(추가 작업)을 선택한 다음 **제품 라이선스 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-144">At the top, select the three dots (more actions), then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="79178-145">**제품 라이선스 관리** 창에서 **기존 제품 라이선스 할당에 추가** \> **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-145">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="79178-146">**기존 제품에 추가** 창에서 선택한 사용자에게 제공하려는 라이선스의 **설정** 위치로 토글합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-146">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.\</span></span>
    <span data-ttu-id="79178-147">기본적으로 해당 라이선스와 연결된 모든 서비스가 사용자에게 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="79178-147">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="79178-148">사용자가 이용할 수 있는 서비스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-148">You can limit which services are available to the users.</span></span> <span data-ttu-id="79178-149">사용자에게 제공하지 않으려는 서비스의 **해제** 위치로 토글합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-149">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="79178-150">창의 아래쪽에서 **추가** \> **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-150">At the bottom of the pane, select **Add** \> **Close**.</span></span>  


> [!NOTE]
> <span data-ttu-id="79178-151">많은 수의 사용자에게 라이선스를 할당하려는 경우 [Azure Active Directory에서 그룹 구성원으로 사용자에게 라이선스 할당](/azure/active-directory/enterprise-users/licensing-groups-assign)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="79178-151">If you want to assign licenses for a large number of users, use [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span></span>

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="79178-152">한 명의 사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="79178-152">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79178-153">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="79178-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="79178-154">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="79178-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="79178-155">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="79178-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="79178-156">라이선스를 할당하려는 사용자의 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-156">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="79178-157">오른쪽 창에서 **라이선스 및 앱** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-157">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="79178-158">**라이선스** 섹션을 확장하고 할당하려는 라이선스의 확인란을 선택한 다음 **변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-158">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="79178-159">게스트 사용자에게 라이선스를 할당</span><span class="sxs-lookup"><span data-stu-id="79178-159">Assign a license to a guest user</span></span>

<span data-ttu-id="79178-160">Azure Active Directory 관리 센터에서 게스트 사용자를 조직과 공동 작업하도록 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-160">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="79178-161">게스트 사용자에 대한 자세한 내용은 [Azure Active Directory B2B의 게스트 사용자 액세스란 무엇인가요?](/azure/active-directory/external-identities/what-is-b2b)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79178-161">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="79178-162">게스트 사용자가 없는 경우 [빠른 시작: Azure portal에서 디렉터리에 게스트 사용자 추가](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79178-162">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79178-163">다음 단계를 수행하려면 전역 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-163">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="79178-164"><a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory 관리 센터</a>로 이동</span><span class="sxs-lookup"><span data-stu-id="79178-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="79178-165">탐색 창에서 **사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-165">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="79178-166">**사용자 | 모든 사용자(미리 보기)** 페이지에서 **필터 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-166">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="79178-167">**필드 선택** 메뉴에서 **사용자 유형** 을 선택한 다음 **적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-167">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="79178-168">다음 메뉴에서 **게스트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-168">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="79178-169">결과 목록에서 라이선스가 필요한 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-169">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="79178-170">**관리** 에서 **라이선스** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-170">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="79178-171">**과제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-171">Select **Assignments**.</span></span>
9. <span data-ttu-id="79178-172">**라이선스 할당 업데이트** 페이지에서 라이선스를 할당하려는 제품을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-172">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="79178-173">오른쪽에서 게스트 사용자가 액세스하지 않을 서비스에 대한 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-173">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="79178-174">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79178-174">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="79178-175">다음 단계</span><span class="sxs-lookup"><span data-stu-id="79178-175">Next steps</span></span>

<span data-ttu-id="79178-176">사용자가 아직 Office 앱을 설치하지 않은 경우 [직원 빠른 시작 가이드](../../business-video/employee-quick-setup.md)를 사용자와 공유하여 [PC 또는 Mac에서 Microsoft 365 또는 Office 2019를 다운로드하고 설치하는 방법](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 및 [모바일 장치에서 Office 앱 및 전자 메일을 설정하는 방법](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)과 같은 항목을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79178-176">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](../../business-video/employee-quick-setup.md) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="79178-177">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="79178-177">Related content</span></span>

<span data-ttu-id="79178-178">[구독 및 라이선스 이해](../../commerce/licenses/subscriptions-and-licenses.md) (문서)</span><span class="sxs-lookup"><span data-stu-id="79178-178">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="79178-179">[사용자의 라이선스 할당 취소](remove-licenses-from-users.md) (문서)</span><span class="sxs-lookup"><span data-stu-id="79178-179">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="79178-180">[구독에 대한 라이선스 구입 또는 제거](../../commerce/licenses/buy-licenses.md) (문서)</span><span class="sxs-lookup"><span data-stu-id="79178-180">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
