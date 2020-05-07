---
title: Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제
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
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 보안 그룹을 만들거나 편집 하거나 삭제 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 6f4daa66c11675674fdbfbfeb625128d8f817520
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140444"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="69a12-103">Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="69a12-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="69a12-104">관리 센터가 변경 되는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-104">The admin center is changing.</span></span> <span data-ttu-id="69a12-105">환경이 여기에 나와 있는 세부 정보와 일치 하지 않으면 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69a12-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="69a12-106">Microsoft 365 **Groups** 페이지에서는 SharePoint ONLINE 및 CRM online에 동일한 사용 권한을 할당 하는 데 사용할 수 있는 사용자 계정 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="69a12-107">예를 들어 관리자는 특정 사용자 그룹에 게 SharePoint 사이트에 대 한 액세스 권한을 부여 하는 보안 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="69a12-108">전역 및 사용자 관리 관리자만 보안 그룹을 만들거나 편집 하거나 삭제할 수 있습니다. 관리자 역할에 대 한 자세한 내용은 [관리자 역할 할당](../add-users/assign-admin-roles.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="69a12-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="69a12-109">전자 메일을 보내거나 사용자 그룹에 사용 권한을 할당하는 데 사용할 수 있는 [Exchange Online 및 SharePoint Online의 그룹](#groups-in-exchange-online-and-sharepoint-online), 그리고 사이트 및 사이트 모음에 대한 사용자 권한 및 액세스 권한을 부여하는 [Exchange Online 및 SharePoint Online의 그룹](#groups-in-exchange-online-and-sharepoint-online)도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="69a12-110">사이트 사서함을 사용할 계획이신가요?</span><span class="sxs-lookup"><span data-stu-id="69a12-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="69a12-111">개별적으로 추가되지 않고 보안 그룹을 통해 SharePoint 사이트에 추가되는 모든 사용자는 SharePoint를 통해서만 사이트 사서함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="69a12-112">이러한 사용자는 Outlook에서 사이트 사서함에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="69a12-113">자세한 내용은 [사이트 사서함 대신 Microsoft 365 그룹 사용](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="69a12-113">For more information, see [Use Microsoft 365 groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="69a12-114">관리 센터에서 보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="69a12-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="69a12-115">보안 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="69a12-115">Add a security group</span></span>

1. <span data-ttu-id="69a12-116">Microsoft 365 관리 센터에서 **그룹** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="69a12-117">**그룹** 페이지에서 **그룹 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="69a12-118">**그룹 종류 선택** 페이지에서 **보안**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="69a12-119">단계에 따라 그룹 만들기를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="69a12-120">보안 그룹에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="69a12-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="69a12-121">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="69a12-122">**그룹** 페이지에서 보안 그룹 이름을 선택 하 고 **구성원** 탭에서 **모두 보기 및 구성원 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-122">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="69a12-123">그룹 창에서 **구성원 추가** 를 선택 하 고 목록에서 사용자를 선택 하거나 **검색** 상자에 추가할 사용자의 이름을 입력 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="69a12-124">구성원을 제거 하려면 이름 옆에 있는 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="69a12-125">**그룹** 페이지에서 보안 그룹 이름을 선택한 다음 **구성원**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="69a12-126">그룹 창에서 **구성원 추가** 를 선택 하 고 목록에서 사용자를 선택 하거나 **검색** 상자에 추가할 사용자의 이름을 입력 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="69a12-127">구성원을 제거 하려면 이름 옆에 있는 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-127">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="69a12-128">**그룹** 페이지에서 보안 그룹 이름을 선택한 다음 **구성원**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-128">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="69a12-129">그룹 창에서 **구성원 추가** 를 선택 하 고 목록에서 사용자를 선택 하거나 **검색** 상자에 추가할 사용자의 이름을 입력 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-129">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="69a12-130">구성원을 제거 하려면 이름 옆에 있는 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-130">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="69a12-131">보안 그룹 편집</span><span class="sxs-lookup"><span data-stu-id="69a12-131">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="69a12-132">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-132">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="69a12-133">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-133">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="69a12-134">**그룹** 페이지에서 그룹의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-134">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="69a12-135">설정 창에서 **일반** 탭 또는 **구성원** 탭을 선택 하 여 그룹 세부 정보 또는 구성원을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-135">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="69a12-136">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="69a12-137">**그룹** 페이지에서 그룹의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="69a12-138">보안 그룹 창에서 **이름** 또는 **구성원** 탭 옆에 있는 **편집** 을 선택 하 여 그룹 세부 정보 또는 구성원을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="69a12-139">변경 작업을 수행한 후 **닫기** **저장** \> 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-139">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="69a12-140">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-140">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="69a12-141">**그룹** 페이지에서 그룹의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-141">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="69a12-142">보안 그룹 창에서 **이름** 또는 **구성원** 탭 옆에 있는 **편집** 을 선택 하 여 그룹 세부 정보 또는 구성원을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-142">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="69a12-143">변경 작업을 수행한 후 **닫기** **저장** > 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-143">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="69a12-144">보안 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="69a12-144">Delete a security group</span></span>

1. <span data-ttu-id="69a12-145">관리 센터에서 **그룹** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-145">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="69a12-146">**그룹** 페이지에서 그룹의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-146">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="69a12-147">**그룹 삭제** (wasetbin 아이콘)를 선택 하 고 **삭제**를 선택 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-147">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="69a12-148">그룹을 삭제 한 후 **닫기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-148">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="69a12-149">Exchange Online 및 SharePoint Online의 그룹</span><span class="sxs-lookup"><span data-stu-id="69a12-149">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="69a12-150">전자 메일을 모두 동시에 보낼 수 있도록 사용자 그룹을 만들려는 경우에는 exchange 관리 센터에서 **관리** \> **exchange** \> **받는 사람** \> **그룹**으로 이동 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-150">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="69a12-151">그런 다음 **새로 만들기**![](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)를 선택 하 고 만들려는 그룹의 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-151">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="69a12-152">**메일 그룹**: 사용자 그룹에 메시지를 배포하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-152">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="69a12-153">*메일 사용이 가능한 메일 그룹*또는 *메일*그룹이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-153">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="69a12-154">자세한 내용은 [메일 그룹 관리](https://technet.microsoft.com/library/bb124513.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69a12-154">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="69a12-155">**보안 그룹**: 사용자 그룹에 메시지를 배포하거나 리소스에 대한 액세스 권한을 부여하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-155">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="69a12-156">이 그룹은 *메일 사용이 가능한 보안 그룹*이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-156">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="69a12-157">자세한 내용은 [메일 사용이 가능한 보안 그룹 관리](https://technet.microsoft.com/library/bb123521.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="69a12-157">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="69a12-158">**동적 메일 그룹**: 정의하는 필터 및 조건을 기반으로 메시지를 보낼 때마다 받는 사람 목록이 다시 계산되는 메일 그룹 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-158">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="69a12-159">자세한 내용은 [동적 메일 그룹 관리](https://technet.microsoft.com/library/bb123722.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69a12-159">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="69a12-160">Exchange 관리 센터에서 메일 그룹 및 메일 사용이 가능한 보안 그룹을 만든 후에는 해당 이름 및 사용자 목록이 **보안 그룹** 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-160">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="69a12-161">두 위치에서 모두 이러한 그룹을 삭제할 수 있지만 편집은 Exchange 관리 센터에서만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-161">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="69a12-162">동적 메일 그룹은 **보안 그룹** 페이지에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-162">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="69a12-163">SharePoint 그룹은 사이트 모음을 만들 때 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-163">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="69a12-164">기본 그룹은 SharePoint의 기본 사용 권한 수준(SharePoint 역할이라고도 함)을 통해 사용자 권한 및 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-164">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="69a12-165">자세한 내용은 [Sharepoint Online의 기본 sharepoint 그룹](https://docs.microsoft.com/sharepoint/default-sharepoint-groups)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69a12-165">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="69a12-166">어떤 보안 그룹을 SharePoint에서 만드는 보안 그룹과 다른 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="69a12-166">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="69a12-167">보안 그룹은 SharePoint, Exchange, MDM, Windows 등에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-167">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="69a12-168">SharePoint에서 만드는 보안 그룹은 해당 SharePoint 사이트 모음 에서만 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-168">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="69a12-169">조직의 보안 그룹을 안전 하 게 사용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="69a12-169">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="69a12-170">아니요.</span><span class="sxs-lookup"><span data-stu-id="69a12-170">No.</span></span> <span data-ttu-id="69a12-171">이 방법 만으로도 조직의 보안을 보다 효율적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-171">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="69a12-172">사용자 권한 및 사이트에 대 한 액세스 권한을 언제 든 지 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-172">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="69a12-173">그러나 보안 그룹을 사용 하면 대규모 사용자 그룹을 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-173">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="69a12-174">보안 그룹에 전자 메일을 보낼 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="69a12-174">Can I send email to a security group?</span></span>

<span data-ttu-id="69a12-175">예.</span><span class="sxs-lookup"><span data-stu-id="69a12-175">Yes.</span></span> <span data-ttu-id="69a12-176">그러나 전자 메일 및 공동 작업을 위해 그룹을 사용 하려는 경우에는 대신 [Microsoft 365 그룹을 만드는](../create-groups/create-groups.md) 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="69a12-176">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
