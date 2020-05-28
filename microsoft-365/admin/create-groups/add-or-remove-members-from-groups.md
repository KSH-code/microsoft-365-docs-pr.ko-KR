---
title: Microsoft 365 그룹에서 구성원 추가 또는 제거
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Microsoft 365 관리 센터에서 그룹에 구성원을 추가 하 고, 그룹에서 구성원을 제거 하 고, 그룹 소유자 상태를 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 99f764c3fc0022a570af6f3dc232725025b4d32f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44388152"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a><span data-ttu-id="c672e-103">관리 센터를 사용 하 여 Microsoft 365 그룹에서 구성원 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="c672e-103">Add or remove members from Microsoft 365 groups using the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c672e-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-104">The admin center is changing.</span></span> <span data-ttu-id="c672e-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c672e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c672e-106">Microsoft 365에서 그룹 구성원은 일반적으로 고유한 그룹을 만들거나, 참가 하려는 그룹에 자신을 추가 하거나, 그룹 소유자의 초대를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-106">In Microsoft 365, group members typically create their own groups, add themselves to groups they want to join, or are invited by group owners.</span></span> <span data-ttu-id="c672e-107">그룹 소유권이 변경 되거나 구성원을 추가 또는 제거 해야 하는 경우에도 해당 변경 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-107">If group ownership changes, or if you determine that a member should be added or removed, as the admin you can also make that change.</span></span> <span data-ttu-id="c672e-108">전역 관리자, Exchange 관리자, 그룹 관리자 또는 사용자 관리자만 이러한 변경 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-108">Only a global administrator, Exchange administrator, Groups administrator, or user administrator can make these changes.</span></span> [<span data-ttu-id="c672e-109">Microsoft 365 그룹 이란?</span><span class="sxs-lookup"><span data-stu-id="c672e-109">What is a Microsoft 365 group?</span></span>](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)

> [!TIP]
> <span data-ttu-id="c672e-110">관리자가 아닌 경우 [Outlook을 사용 하 여 구성원을 추가 하거나 제거할](https://support.office.com/article/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de.aspx)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-110">If you're not an admin, you can [add or remove members using Outlook](https://support.office.com/article/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de.aspx).</span></span> 
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a><span data-ttu-id="c672e-111">관리 센터에서 그룹에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="c672e-111">Add a member to a group in the admin center</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c672e-112">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-112">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>  
    
2. <span data-ttu-id="c672e-113">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-113">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-114">세부 정보 창의 **구성원** 탭에서 **구성원 보기 및 모두 관리**를 선택 하 고 **구성원 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-114">In the details pane, on the **Members** tab, select **View all and manage members**, and then select **Add members**.</span></span>
      
4. <span data-ttu-id="c672e-115">추가할 구성원의 이름을 검색하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-115">Search for or select the name of the member you want to add.</span></span>
    
5. <span data-ttu-id="c672e-116">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-116">Select **Save**.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c672e-117">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-117">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>  
    
2. <span data-ttu-id="c672e-118">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-118">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-119">세부 정보 창에서 **구성원**옆에 있는 **편집**을 선택 하 고 **구성원 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-119">In the details pane, next to **Members**, select **Edit**, and then select **Add members**.</span></span>
      
4. <span data-ttu-id="c672e-120">추가할 구성원의 이름을 검색하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-120">Search for or select the name of the member you want to add.</span></span>
    
5. <span data-ttu-id="c672e-121">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-121">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c672e-122">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-122">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>  
    
2. <span data-ttu-id="c672e-123">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-123">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-124">세부 정보 창에서 **구성원**옆에 있는 **편집**을 선택 하 고 **구성원 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-124">In the details pane, next to **Members**, select **Edit**, and then select **Add members**.</span></span>
      
4. <span data-ttu-id="c672e-125">추가할 구성원의 이름을 검색하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-125">Search for or select the name of the member you want to add.</span></span>
    
5. <span data-ttu-id="c672e-126">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-126">Select **Save**.</span></span>

::: moniker-end

## <a name="add-a-group-to-a-member-in-the-admin-center"></a><span data-ttu-id="c672e-127">관리 센터에서 구성원에 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="c672e-127">Add a group to a member in the admin center</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c672e-128">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="c672e-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="c672e-129">사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-129">Select a user.</span></span>
    
3. <span data-ttu-id="c672e-130">세부 정보 창의 **계정** 탭에서 **그룹 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-130">In the details pane, on the **Account** tab, select **Manage groups**.</span></span>
      
4. <span data-ttu-id="c672e-131">추가할 그룹의 이름을 검색 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-131">Search for or select the name of the group you want to add.</span></span>
    
5. <span data-ttu-id="c672e-132">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-132">Select **Save**.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c672e-133">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="c672e-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="c672e-134">사용자 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-134">Select a user name.</span></span>
    
3. <span data-ttu-id="c672e-135">세부 정보 창의 **그룹 멤버 자격**옆에서 **편집**을 선택한 다음 **멤버 자격 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-135">In the details pane, next to **Group memberships**, select **Edit**, and then select **Add memberships**.</span></span>
      
4. <span data-ttu-id="c672e-136">추가할 그룹의 이름을 검색 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-136">Search for or select the name of the group you want to add.</span></span>
    
5. <span data-ttu-id="c672e-137">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-137">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c672e-138">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="c672e-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="c672e-139">사용자 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-139">Select a user name.</span></span>
    
3. <span data-ttu-id="c672e-140">세부 정보 창의 **그룹 멤버 자격**옆에서 **편집**을 선택한 다음 **멤버 자격 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-140">In the details pane, next to **Group memberships**, select **Edit**, and then select **Add memberships**.</span></span>
      
4. <span data-ttu-id="c672e-141">추가할 그룹의 이름을 검색 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-141">Search for or select the name of the group you want to add.</span></span>
    
5. <span data-ttu-id="c672e-142">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-142">Select **Save**.</span></span>

::: moniker-end



## <a name="remove-a-member-from-a-group-in-the-admin-center"></a><span data-ttu-id="c672e-143">관리 센터에서 그룹의 구성원 제거</span><span class="sxs-lookup"><span data-stu-id="c672e-143">Remove a member from a group in the admin center</span></span>

> [!NOTE]
> <span data-ttu-id="c672e-144">비공개 그룹에서 구성원을 제거하는 경우 해당 구성원을 그룹에서 차단하는 데 5분이 소요됩니다(멤버십 변경이 도메인 컨트롤러 간에 완전히 복제된 후).</span><span class="sxs-lookup"><span data-stu-id="c672e-144">When you remove a member from a private group, it takes 5 minutes for the person to be blocked from the group (after membership changes are fully replicated among domain controllers).</span></span> 
 
::: moniker range="o365-worldwide"
 
1. <span data-ttu-id="c672e-145">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-145">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="c672e-146">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-146">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-147">세부 정보 창의 **구성원** 탭에서 **모두 보기 및 구성원 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-147">In the details pane, on the **Members** tab, select **View all and manage members**.</span></span>
    
4. <span data-ttu-id="c672e-148">제거 하려는 구성원 옆에 있는 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-148">Next to the member you want to remove, select the X.</span></span>
    
5. <span data-ttu-id="c672e-149">**저장** 을 선택 하 여 구성원을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-149">Select **Save** to remove the member.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c672e-150">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-150">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="c672e-151">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-151">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-152">세부 정보 창에서 **구성원**옆에 있는 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-152">In the details pane, next to **Members**, select **Edit**.</span></span>
    
4. <span data-ttu-id="c672e-153">제거 하려는 구성원 옆에 있는 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-153">Next to the member you want to remove, select the X.</span></span>
    
5. <span data-ttu-id="c672e-154">**저장** 을 선택 하 여 구성원을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-154">Select **Save** to remove the member.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c672e-155">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-155">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="c672e-156">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-156">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-157">세부 정보 창에서 **구성원**옆에 있는 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-157">In the details pane, next to **Members**, select **Edit**.</span></span>
    
4. <span data-ttu-id="c672e-158">제거 하려는 구성원 옆에 있는 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-158">Next to the member you want to remove, select the X.</span></span>
    
5. <span data-ttu-id="c672e-159">**저장** 을 선택 하 여 구성원을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-159">Select **Save** to remove the member.</span></span> 

::: moniker-end

## <a name="manage-group-owner-status"></a><span data-ttu-id="c672e-160">그룹 소유자 상태 관리</span><span class="sxs-lookup"><span data-stu-id="c672e-160">Manage group owner status</span></span>

<span data-ttu-id="c672e-p103">기본적으로 그룹을 만든 사람은 그룹 소유자입니다. 그룹에는 종종 백업 지원 또는 기타 이유로 여러 명의 소유자가 있습니다. 구성원은 소유자 상태로 수준이 올라갈 수 있으며 소유자는 구성원 상태로 수준이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-p103">By default, the person who created the group is the group owner. Often a group will have multiple owners for backup support or other reasons. Members can be promoted to owner status and owners can be demoted to member status.</span></span>
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a><span data-ttu-id="c672e-164">관리 센터에서 구성원을 소유자 상태로 수준 올리기</span><span class="sxs-lookup"><span data-stu-id="c672e-164">Promote a member to owner status in the admin center</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c672e-165">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-165">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="c672e-166">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-166">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-167">세부 정보 창의 **구성원** 탭에서 **모두 보기 및 소유자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-167">In the details pane, on the **Members** tab, select **View all and manage owners**.</span></span>

4. <span data-ttu-id="c672e-168">구성원을 검색 하거나 **소유자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-168">Search for a member, or select **Add owners**.</span></span>
    
5. <span data-ttu-id="c672e-169">추가할 구성원의 이름 옆에 있는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-169">Select the check box next to the name of the member you want to add.</span></span>
    
6. <span data-ttu-id="c672e-170">**저장**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-170">Select **Save**, and then **Close**.</span></span>   
   
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c672e-171">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-171">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="c672e-172">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-172">Select a group name.</span></span>

3. <span data-ttu-id="c672e-173">세부 정보 창의 **소유자**옆에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-173">In the details pane, next to **Owners**, select **Edit**.</span></span>

4. <span data-ttu-id="c672e-174">구성원을 검색 하거나 **소유자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-174">Search for a member, or select **Add owners**.</span></span>
    
5. <span data-ttu-id="c672e-175">추가할 구성원의 이름 옆에 있는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-175">Select the check box next to the name of the member you want to add.</span></span>
    
6. <span data-ttu-id="c672e-176">**저장**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-176">Select **Save**, and then **Close**.</span></span>   

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c672e-177">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-177">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="c672e-178">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-178">Select a group name.</span></span>

3. <span data-ttu-id="c672e-179">세부 정보 창의 **소유자**옆에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-179">In the details pane, next to **Owners**, select **Edit**.</span></span>

4. <span data-ttu-id="c672e-180">구성원을 검색 하거나 **소유자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-180">Search for a member, or select **Add owners**.</span></span>
    
5. <span data-ttu-id="c672e-181">추가할 구성원의 이름 옆에 있는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-181">Select the check box next to the name of the member you want to add.</span></span>
    
6. <span data-ttu-id="c672e-182">**저장**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-182">Select **Save**, and then **Close**.</span></span>   

::: moniker-end

### <a name="remove-owner-status-in-the-admin-center"></a><span data-ttu-id="c672e-183">관리 센터에서 소유자 상태 제거</span><span class="sxs-lookup"><span data-stu-id="c672e-183">Remove owner status in the admin center</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c672e-184">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-184">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="c672e-185">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-185">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-186">세부 정보 창의 **구성원** 탭에서 **모두 보기 및 소유자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-186">In the details pane, on the **Members** tab, select **View all and manage owners**.</span></span>
    
5. <span data-ttu-id="c672e-187">소유자 이름 옆에 있는 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-187">Select the X next to the owner's name.</span></span> 
    
6. <span data-ttu-id="c672e-188">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-188">Select **Save**.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c672e-189">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-189">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="c672e-190">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-190">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-191">세부 정보 창의 **소유자**옆에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-191">In the details pane, next to **Owners**, select **Edit**.</span></span>
    
5. <span data-ttu-id="c672e-192">소유자 이름 옆에 있는 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-192">Select the X next to the owner's name.</span></span> 
    
6. <span data-ttu-id="c672e-193">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-193">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c672e-194">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-194">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="c672e-195">그룹 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-195">Select a group name.</span></span>
    
3. <span data-ttu-id="c672e-196">세부 정보 창의 **소유자**옆에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-196">In the details pane, next to **Owners**, select **Edit**.</span></span>
    
5. <span data-ttu-id="c672e-197">소유자 이름 옆에 있는 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-197">Select the X next to the owner's name.</span></span> 
    
6. <span data-ttu-id="c672e-198">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-198">Select **Save**.</span></span>

::: moniker-end


## <a name="more-on-managing-membership"></a><span data-ttu-id="c672e-199">멤버 자격 관리에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="c672e-199">More on managing membership</span></span>

- <span data-ttu-id="c672e-200">[Azure Active Directory에서 동적으로 그룹 관리](https://go.microsoft.com/fwlink/?linkid=847632): "그룹 멤버 자격을 어떻게 동적으로 관리할 수 있나요?" 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c672e-200">[Manage groups dynamically in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=847632): see the section "How can I manage the membership of a group dynamically?"</span></span>
    
- <span data-ttu-id="c672e-201">수백 또는 수천 명의 사용자를 그룹에 추가 하려면 [add-unifiedgrouplinks](https://go.microsoft.com/fwlink/p/?LinkId=616191)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-201">To add hundreds or thousands of users to groups, use the [Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191).</span></span>
    
- [<span data-ttu-id="c672e-202">분리된 그룹에 새 소유자 할당</span><span class="sxs-lookup"><span data-stu-id="c672e-202">Assign a new owner to an orphaned group</span></span>](https://support.microsoft.com/en-us/office/assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)
    
## <a name="articles-about-managing-groups"></a><span data-ttu-id="c672e-203">그룹 관리에 대한 문서</span><span class="sxs-lookup"><span data-stu-id="c672e-203">Articles about managing groups</span></span>
    
- [<span data-ttu-id="c672e-204">Outlook에서 Microsoft 365 그룹으로 메일 그룹 업그레이드</span><span class="sxs-lookup"><span data-stu-id="c672e-204">Upgrade distribution lists to Microsoft 365 groups in Outlook</span></span>](../manage/upgrade-distribution-lists.md)
    
- [<span data-ttu-id="c672e-205">Outlook에서 배포 목록을 그룹으로 업그레이드해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="c672e-205">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/en-us/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

- [<span data-ttu-id="c672e-206">Microsoft 365 그룹에서 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="c672e-206">Manage guest access in Microsoft 365 groups</span></span>](manage-guest-access-in-groups.md)    
    
- <span data-ttu-id="c672e-207">[PowerShell을 사용 하 여 Microsoft 365 그룹 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell):이 문서에서는 주요 cmdlet을 소개 하 고 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672e-207">[Manage Microsoft 365 groups with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell): this article introduces you to key cmdlets and provides examples</span></span>
    
- [<span data-ttu-id="c672e-208">Microsoft 365 그룹 명명 정책</span><span class="sxs-lookup"><span data-stu-id="c672e-208">Microsoft 365 groups naming policy</span></span>](groups-naming-policy.md)
