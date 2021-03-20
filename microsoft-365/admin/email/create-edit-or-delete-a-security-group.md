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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 보안 그룹을 만들거나 편집하거나 삭제하는 방법을 학습합니다.
ms.openlocfilehash: d2cc749acaf7b2e23674156f6ad9a200ec7b386d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915821"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1b122-103">Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="1b122-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1b122-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-104">The admin center is changing.</span></span> <span data-ttu-id="1b122-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b122-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="1b122-106">Microsoft 365 **그룹** 페이지에서 SharePoint Online 및 CRM Online에서 동일한 권한을 할당하는 데 사용할 수 있는 사용자 계정 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="1b122-107">예를 들어 관리자는 보안 그룹을 만들어 특정 사용자 그룹에 SharePoint 사이트에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="1b122-108">전역 관리자와 사용자 관리 관리자만 보안 그룹을 만들거나 편집하거나 삭제할 수 있는 권한이 있습니다. 관리자 역할에 대한 자세한 내용은 관리자 역할 [할당을 참조하세요.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="1b122-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="1b122-109">전자 메일을 보내거나 사용자 그룹에 사용 권한을 할당하는 데 사용할 수 있는 [Exchange Online 및 SharePoint Online의 그룹](#groups-in-exchange-online-and-sharepoint-online), 그리고 사이트 및 사이트 모음에 대한 사용자 권한 및 액세스 권한을 부여하는 [Exchange Online 및 SharePoint Online의 그룹](#groups-in-exchange-online-and-sharepoint-online)도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="1b122-110">사이트 사서함을 사용할 계획이신가요?</span><span class="sxs-lookup"><span data-stu-id="1b122-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="1b122-111">개별적으로 추가되지 않고 보안 그룹을 통해 SharePoint 사이트에 추가되는 모든 사용자는 SharePoint를 통해서만 사이트 사서함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="1b122-112">이러한 사용자는 Outlook에서 사이트 사서함에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="1b122-113">자세한 내용은 [Use Microsoft 365 Groups instead of Site Mailboxes을 참조하세요.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="1b122-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="1b122-114">관리 센터에서 보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="1b122-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="1b122-115">보안 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="1b122-115">Add a security group</span></span>

1. <span data-ttu-id="1b122-116">Microsoft 365 관리 센터에서 그룹 **그룹 페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="1b122-117">그룹 **페이지에서** 그룹 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="1b122-118">그룹 **유형 선택 페이지에서** 보안을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="1b122-119">단계에 따라 그룹 만들기를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="1b122-120">보안 그룹에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="1b122-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="1b122-121">그룹 페이지에서 보안 그룹  이름을 선택하고 구성원  탭에서 모두 보기 및 구성원 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="1b122-122">그룹 창에서 구성원  추가를 선택하고 목록에서 해당 사람을 선택하거나 검색 상자에 추가할  사람의 이름을 입력한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="1b122-123">구성원을 제거하려면 이름 옆에 있는 X를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1b122-124">그룹 페이지에서 보안 그룹 이름을 **선택하고** 구성원 옆에 **있는** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="1b122-125">그룹 창에서 구성원  추가를 선택하고 목록에서 해당 사람을 선택하거나 검색 상자에 추가할  사람의 이름을 입력한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="1b122-126">구성원을 제거하려면 이름 옆에 있는 X를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="1b122-127">그룹 페이지에서 보안 그룹 이름을 **선택하고** 구성원 옆에 **있는** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="1b122-128">그룹 창에서 구성원  추가를 선택하고 목록에서 해당 사람을 선택하거나 검색 상자에 추가할  사람의 이름을 입력한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="1b122-129">구성원을 제거하려면 이름 옆에 있는 X를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="1b122-130">보안 그룹 편집</span><span class="sxs-lookup"><span data-stu-id="1b122-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1b122-131">관리 센터에서 그룹 그룹  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="1b122-132">그룹 **페이지에서** 그룹의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1b122-133">설정 창에서 일반 탭  또는 구성원  탭을 선택하여 그룹 세부 정보 또는 구성원을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1b122-134">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">센터에서</a>그룹 그룹 **페이지로** \>  이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="1b122-135">그룹 **페이지에서** 그룹의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1b122-136">보안 그룹 창에서 이름 또는 구성원  탭  옆에 있는 편집을 선택하여 그룹 세부 정보 또는 구성원을 편집합니다. </span><span class="sxs-lookup"><span data-stu-id="1b122-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="1b122-137">변경한 후 저장 **닫기 를** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1b122-138">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">센터에서</a>그룹 그룹 **페이지로** \>  이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="1b122-139">그룹 **페이지에서** 그룹의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1b122-140">보안 그룹 창에서 이름 또는 구성원  탭  옆에 있는 편집을 선택하여 그룹 세부 정보 또는 구성원을 편집합니다. </span><span class="sxs-lookup"><span data-stu-id="1b122-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="1b122-141">변경한 후 저장 **닫기 를** > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="1b122-142">보안 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="1b122-142">Delete a security group</span></span>

1. <span data-ttu-id="1b122-143">관리 센터에서 그룹 그룹   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="1b122-144">그룹 **페이지에서** 그룹의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1b122-145">그룹  삭제(와세트빈 아이콘)를 선택한 다음 삭제 를 선택하여 **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="1b122-146">**그룹이** 삭제되면 닫기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="1b122-147">Exchange Online 및 SharePoint Online의 그룹</span><span class="sxs-lookup"><span data-stu-id="1b122-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="1b122-148">모든 사용자에게 동시에 전자 메일을 보낼 수 있도록 사용자 그룹을 만들 수 있도록 하려는 경우 Exchange  관리 센터에서 관리자 Exchange 받는 사람 그룹으로 하여 만들 \>  \> **수** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1b122-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="1b122-149">그런 다음 **새로** 추가 를 선택하고 만들 그룹의 ![ ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) 종류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="1b122-150">**메일 그룹**: 사용자 그룹에 메시지를 배포하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="1b122-151">메일 사용이 가능한 메일 그룹 또는 메일 *그룹이라고도 합니다.*</span><span class="sxs-lookup"><span data-stu-id="1b122-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="1b122-152">자세한 내용은 [메일 그룹 관리](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b122-152">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="1b122-153">**보안 그룹**: 사용자 그룹에 메시지를 배포하거나 리소스에 대한 액세스 권한을 부여하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="1b122-154">이 그룹을 메일 사용이 가능한 보안 *그룹이라고도 합니다.*</span><span class="sxs-lookup"><span data-stu-id="1b122-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="1b122-155">자세한 내용은 [메일 사용이 가능한 보안 그룹 관리](/Exchange/recipients/mail-enabled-security-groups)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1b122-155">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="1b122-156">**동적 메일 그룹**: 정의하는 필터 및 조건을 기반으로 메시지를 보낼 때마다 받는 사람 목록이 다시 계산되는 메일 그룹 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="1b122-157">자세한 내용은 동적 메일 그룹 [관리를 참조하세요.](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="1b122-157">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="1b122-158">Exchange 관리 센터에서 메일 그룹 및 메일 사용이 가능한 보안 그룹을 만들면 해당 이름 및 사용자 목록이 보안 그룹 **페이지에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="1b122-159">두 위치에서 모두 이러한 그룹을 삭제할 수 있지만 편집은 Exchange 관리 센터에서만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="1b122-160">동적 메일 그룹이 보안 그룹 페이지에 **표시되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="1b122-161">SharePoint 그룹은 사이트 모음을 만들 때 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="1b122-162">기본 그룹은 SharePoint의 기본 사용 권한 수준(SharePoint 역할이라고도 함)을 통해 사용자 권한 및 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="1b122-163">자세한 내용은 [SharePoint Online의 기본 SharePoint 그룹을 참조하세요.](/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="1b122-163">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="1b122-164">보안 그룹이 SharePoint에서 만드는 보안 그룹과 어떻게 다른가요?</span><span class="sxs-lookup"><span data-stu-id="1b122-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="1b122-165">보안 그룹은 SharePoint, Exchange, MDM, Windows 등에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="1b122-166">SharePoint에서 만드는 보안 그룹은 해당 SharePoint 사이트 모음에서만 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="1b122-167">조직을 안전하게 보호하기 위해 보안 그룹을 사용해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1b122-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="1b122-168">아니요.</span><span class="sxs-lookup"><span data-stu-id="1b122-168">No.</span></span> <span data-ttu-id="1b122-169">이는 조직의 보안을 관리할 수 있는 한 가지 방법일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-169">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="1b122-170">항상 사용자 권한 및 사이트에 대한 액세스 권한을 개별적으로 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-170">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="1b122-171">그러나 보안 그룹을 사용하면 더 큰 사용자 그룹을 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-171">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="1b122-172">보안 그룹에 전자 메일을 보낼 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1b122-172">Can I send email to a security group?</span></span>

<span data-ttu-id="1b122-173">예.</span><span class="sxs-lookup"><span data-stu-id="1b122-173">Yes.</span></span> <span data-ttu-id="1b122-174">그러나 전자 메일 및 공동 작업용 그룹을 사용하려는 경우 [대신 Microsoft 365](../create-groups/create-groups.md) 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1b122-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
