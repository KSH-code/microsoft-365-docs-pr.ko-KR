---
title: 사용자의 라이선스 할당 취소
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- manage_licenses
- okr_smb
- commerce
search.appverid:
- MET150
description: 사용자 계정에서 라이선스를 배정을 unassign하는 방법을 학습합니다.
ms.date: 07/01/2020
ms.openlocfilehash: 87bb8f6fe0e85fc4ac832f2bc4ad746e8d6386eb
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310995"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="23645-103">사용자의 라이선스 할당 취소</span><span class="sxs-lookup"><span data-stu-id="23645-103">Unassign licenses from users</span></span>

<span data-ttu-id="23645-104">활성 사용자 페이지 또는 라이선스 페이지에서 사용자로부터  라이선스를 **배포할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="23645-105">사용하는 방법은 특정 사용자의 제품 라이선스를 지정을 해지할지 아니면 특정 제품의 사용자 라이선스를 지정을 해지할지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="23645-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="23645-106">관리자는 조직의 사용자가 구입한 셀프 서비스 구매 구독의 라이선스를 할당하거나 할당 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="23645-107">[셀프 서비스 구매 구독을 이어 받은 다음](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)할당 또는 할당 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="23645-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="23645-108">Before you begin</span></span>

- <span data-ttu-id="23645-109">라이선스를 할당하지하려면 전역, 라이선스, 사용자 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="23645-110">자세한 내용은 [Microsoft 365 관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23645-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="23645-111">[Office 365 PowerShell로 사용자 계정에서 라이선스를 제거](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="23645-112">라이선스가 [할당된](../add-users/delete-a-user.md) 사용자 계정을 삭제하여 다른 사용자가 라이선스를 사용할 수 있도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="23645-113">사용자 계정을 삭제하면 다른 사용자에게 라이선스를 즉시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="23645-114">라이선스 페이지를 사용하여 라이선스를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="23645-115">라이선스 페이지를 **사용하여** 라이선스를 지정하지 않은 경우 특정 제품에 대한 라이선스를 최대 20명까지 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23645-116">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="23645-117"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **청구** > **라이선스** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-117">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23645-118"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **청구** > **라이선스** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-118">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="23645-119">라이선스를 해지할 제품을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="23645-120">라이선스를 배포할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="23645-121">라이선스 **배포를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="23645-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="23645-122">라이선스의 **Unassign(라이선스)** 상자에서 **Unassign (1)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="23645-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="23645-123">활성 사용자 페이지를 사용하여 라이선스의 배포를 허가합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="23645-124">활성 사용자  페이지를 사용하여 라이선스를 배포할 때 사용자로부터 제품 라이선스를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="23645-125">한 사용자의 라이선스에 대한 라이선스를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-125">Unassign licenses from one user</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="23645-126">관리 센터에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-126">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="23645-127"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **청구** > **활성 사용자** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-127">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23645-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **청구** > **활성 사용자** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="23645-129">라이선스를 배포할 사용자의 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="23645-130">오른쪽 창에서 **라이선스 및 앱** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="23645-131">라이선스 **섹션을 확장하고,** 라이선스를 취소할 라이선스의 확인란을 선택 취소한 다음 변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="23645-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="23645-132">여러 사용자의 라이선스를 배정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23645-133">관리 센터에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-133">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="23645-134"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **청구** > **활성 사용자** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23645-135"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **청구** > **활성 사용자** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-135">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="23645-136">라이선스를 배포할 사용자의 이름 옆에 있는 원을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="23645-137">맨 위에 있는 **추가 옵션 (...)** 을 선택한 다음 **제품 라이선스 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-137">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="23645-138">**제품 라이선스 관리** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23645-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="23645-139">기존 제품 바꾸기 창의 아래쪽에서  선택한 사용자에서 모든 제품 라이선스 제거 확인란을 선택한 다음 **바꾸기 닫기를**  \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="23645-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="23645-140">라이선스를 제거하면 사용자의 데이터가 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="23645-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="23645-141">라이선스가 사용자에서 제거되면 해당 계정과 연결된 데이터는 30일 동안 보전됩니다.</span><span class="sxs-lookup"><span data-stu-id="23645-141">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="23645-142">30일의 유예 기간이 경과하면 데이터가 삭제되고 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="23645-143">사용자가 비즈니스용 OneDrive 관리 센터에서 삭제되거나 Active Directory 동기화를 통해 제거되지 않는 한 Microsoft 365 파일을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="23645-144">자세한 내용은 보존 [및 OneDrive 참조하세요.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="23645-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="23645-145">라이선스가 제거되면 콘텐츠 검색 또는 검색과 같은 eDiscovery 도구를 사용하여 사용자의 사서함을 더 이상 검색할 수 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="23645-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content search or Advanced eDiscovery.</span></span> <span data-ttu-id="23645-146">자세한 내용은 콘텐츠 검색 참조의 "연결이 끊어지거나 라이선스가 해제된 사서함 [검색"을 참조하세요.](../../compliance/content-search-reference.md#searching-disconnected-or-de-licensed-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="23645-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content search reference](../../compliance/content-search-reference.md#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="23645-147">E3와 같은 Enterprise Office 365 Enterprise 구독이 있는 경우 Exchange Online 비활성 사서함을 사용하여 삭제된 사용자 계정의 사서함 데이터를 보존할 [수 있습니다.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="23645-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="23645-148">자세한 내용은 [에서 비활성 사서함](../../compliance/create-and-manage-inactive-mailboxes.md)만들기 및 관리를 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="23645-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="23645-149">라이선스가 제거된 후 사용자의 Microsoft 365 액세스를 차단하는 방법과 그 이후에 데이터에 액세스하는 방법에 대한 자세한 내용은 이전 직원 [제거를 참조합니다.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="23645-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="23645-150">사용자의 라이선스를 제거하고 아직 Office 앱이 설치되어 있는 경우 [](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) 라이선스가 없는 제품 및 정품 인증 오류가 Office 앱을 사용할 때 Office 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="23645-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="23645-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="23645-151">Next steps</span></span>

<span data-ttu-id="23645-152">사용되지 않는 라이선스를 [](../../managed-desktop/get-started/assign-licenses.md)다른 사용자에게 다시 재할당하지 않을 경우 [](../../commerce/licenses/buy-licenses.md) 필요한 것보다 많은 라이선스 비용을 지불하지 않을 수 있도록 구독에서 라이선스를 제거하는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23645-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="23645-153">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="23645-153">Related content</span></span>

<span data-ttu-id="23645-154">[구독에서 라이선스 제거(문서)\](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="23645-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)\</span></span>
<span data-ttu-id="23645-155">[사용자에게 라이선스 할당](assign-licenses-to-users.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="23645-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="23645-156">[비즈니스용 Microsoft 365 구독 및 라이선스](../../commerce/licenses/subscriptions-and-licenses.md) 이해(문서)</span><span class="sxs-lookup"><span data-stu-id="23645-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>