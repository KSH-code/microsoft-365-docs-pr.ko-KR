---
title: 사용자의 라이선스 할당 취소
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 사용자 계정에서 라이선스를 배정을 Unassigns(라이선스)하는 방법을 학습합니다.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114480"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="81069-103">사용자의 라이선스 할당 취소</span><span class="sxs-lookup"><span data-stu-id="81069-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="81069-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-104">The admin center is changing.</span></span> <span data-ttu-id="81069-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81069-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="81069-106">활성 사용자 페이지 또는 라이선스 페이지에서 사용자로부터  라이선스를 배포할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="81069-107">사용하는 방법은 특정 사용자의 제품 라이선스를 지정을 해지할지 아니면 특정 제품의 사용자 라이선스를 지정하지 않는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="81069-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="81069-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="81069-108">Before you begin</span></span>

- <span data-ttu-id="81069-109">라이선스를 할당을 할당하려면 전역, 라이선스, 사용자 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="81069-110">자세한 내용은 [Microsoft 365 관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81069-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="81069-111">[Office 365 PowerShell로 사용자 계정에서 라이선스를 제거](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span></span>
- <span data-ttu-id="81069-112">라이선스가 [](../add-users/delete-a-user.md) 할당된 사용자 계정을 삭제하여 다른 사용자가 라이선스를 사용할 수 있도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="81069-113">사용자 계정을 삭제하면 해당 라이선스를 즉시 다른 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="81069-114">라이선스 페이지를 사용하여 라이선스를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="81069-115">라이선스 페이지를 **사용하여** 라이선스를 지정하지 않는 경우 특정 제품에 대한 라이선스를 최대 20명까지 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="81069-116">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="81069-117">라이선스를 배포할 제품을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="81069-118">라이선스를 배포할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="81069-119">라이선스 **배포를 선택하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="81069-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="81069-120">라이선스를 배포하지 않은 **상자에서** 사용 안 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81069-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="81069-121">활성 사용자 페이지를 사용하여 라이선스를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="81069-122">활성 사용자  페이지를 사용하여 라이선스를 배포하지 않는 경우 사용자로부터 제품 라이선스를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="81069-123">한 사용자로부터 라이선스에 대한 라이선스를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="81069-124">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="81069-125">라이선스를 배포할 사용자의 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="81069-126">오른쪽 창에서 **라이선스 및 앱** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="81069-127">라이선스 **섹션을 확장하고,** 라이선스를 취소할 라이선스의 확인란을 선택 취소한 다음 변경 내용 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81069-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="81069-128">한 사용자로부터 라이선스에 대한 라이선스를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="81069-129">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="81069-130">라이선스를 배포할 사용자를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="81069-131">오른쪽의 **제품** 라이선스 행에서 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81069-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="81069-132">제품 라이선스 **창에서** 사용자에게 배포를 해제할  라이선스의 해제 위치로 토글합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="81069-133">예를 들어 Office 365 Enterprise E3 라이선스를 해제하는 경우 해당 사용자에 대해 해당 라이선스 및 해당 라이선스에 따라 모든 서비스에 대한 라이선스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="81069-134">**제품 라이선스** 창의 아래쪽에서 **저장** \> **닫기** \> **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="81069-135">한 사용자로부터 라이선스에 대한 라이선스를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="81069-136">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="81069-137">라이선스를 배포할 사용자를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="81069-138">오른쪽의 **제품** 라이선스 행에서 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81069-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="81069-139">제품 라이선스 **창에서** 사용자에게 배포를 해제할  라이선스의 해제 위치로 토글합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="81069-140">예를 들어 Office 365 Enterprise E3 라이선스를 해제하는 경우 해당 사용자에 대해 해당 라이선스 및 해당 라이선스에 따라 모든 서비스에 대한 라이선스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="81069-141">**제품 라이선스** 창의 아래쪽에서 **저장** \> **닫기** \> **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="81069-142">여러 사용자의 라이선스를 배정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="81069-143">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="81069-144">라이선스를 배포할 사용자의 이름 옆에 있는 원을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="81069-145">맨 위에 있는 **추가 옵션 (...)** 을 선택한 다음 **제품 라이선스 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="81069-146">**제품 라이선스 관리** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="81069-147">기존 제품 바꾸기 창의 맨 아래에서 선택한 사용자에서 모든 제품 라이선스 제거 확인란을 선택한 다음 **닫기 바꾸기를**   \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81069-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="81069-148">여러 사용자의 라이선스를 배정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="81069-149">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="81069-150">모든 라이선스를 배포할 사용자의 이름 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="81069-151">**대량 작업** 창에서 **제품 라이선스 편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="81069-152">**기존 제품 바꾸기** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="81069-153">기존 제품 바꾸기 창의 맨 아래에서 선택한 사용자에서 모든 제품 라이선스 제거 확인란을 선택한 다음 닫기 **바꾸기를**   \>  \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81069-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="81069-154">여러 사용자의 라이선스를 배정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="81069-155">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="81069-156">모든 라이선스를 배포할 사용자의 이름 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="81069-157">**대량 작업** 창에서 **제품 라이선스 편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="81069-158">**기존 제품 바꾸기** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81069-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="81069-159">기존 제품 바꾸기 창의 맨 아래에서 선택한 사용자에서 모든 제품 라이선스 제거 확인란을 선택한 다음 닫기 **바꾸기를**   \>  \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81069-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="81069-160">라이선스를 제거하면 사용자의 데이터가 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="81069-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="81069-161">라이선스가 사용자에서 제거되면 해당 계정과 연결된 데이터는 30일 동안 보전됩니다.</span><span class="sxs-lookup"><span data-stu-id="81069-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="81069-162">30일의 유예 기간이 지난 후 데이터가 삭제되고 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="81069-163">사용자가 Microsoft 365 관리 센터에서 삭제되거나 Active Directory 동기화를 통해 제거되지 않는 한 비즈니스용 OneDrive에 저장된 파일은 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="81069-164">자세한 내용은 [OneDrive 보존 및](https://docs.microsoft.com/onedrive/retention-and-deletion)삭제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81069-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="81069-165">라이선스가 제거되면 콘텐츠 검색 또는 Advanced eDiscovery와 같은 eDiscovery 도구를 사용하여 사용자의 사서함을 더 이상 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="81069-166">자세한 내용은 [Microsoft 365의](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)콘텐츠 검색에서 "연결이 끊어지거나 라이선스가 해제된 사서함 검색"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81069-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="81069-167">Office 365 Enterprise E3과 같은 엔터프라이즈 구독이 있는 경우 Exchange Online에서는 비활성 사서함을 사용하여 삭제된 사용자 계정의 사서함 데이터를 보존할 [수 있습니다.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="81069-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="81069-168">자세한 내용은 [Exchange Online에서 비활성 사서함 만들기 및 관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="81069-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="81069-169">라이선스가 제거된 후 Microsoft 365 데이터에 대한 사용자의 액세스를 차단하는 방법과 이후에 데이터에 액세스하는 방법에 대한 자세한 내용은 이전 직원 [제거를 참조합니다.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="81069-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="81069-170">사용자의 라이선스를 제거하고 여전히 Office 앱이 설치되어 있는 경우 Office 앱을 사용할 때 [Office에서](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) 사용 허가되지 않은 제품 및 정품 인증 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81069-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="81069-171">다음 단계</span><span class="sxs-lookup"><span data-stu-id="81069-171">Next steps</span></span>

<span data-ttu-id="81069-172">사용되지 않는 라이선스를 [](../../managed-desktop/get-started/assign-licenses.md)다른 사용자에게 다시 배포하지 않을 경우 필요한 [](../../commerce/licenses/buy-licenses.md) 것보다 많은 라이선스 비용을 지불하지 않을 수 있도록 구독에서 라이선스를 제거하는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81069-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="81069-173">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="81069-173">Related content</span></span>

<span data-ttu-id="81069-174">[구독에서 라이선스 제거(문서)\](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="81069-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)\</span></span>
<span data-ttu-id="81069-175">[사용자에게 라이선스 할당(문서)\](assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="81069-175">[Assign licenses to users](assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="81069-176">[비즈니스용 Microsoft 365의](../../commerce/licenses/subscriptions-and-licenses.md) 구독 및 라이선스 이해(문서)</span><span class="sxs-lookup"><span data-stu-id="81069-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>