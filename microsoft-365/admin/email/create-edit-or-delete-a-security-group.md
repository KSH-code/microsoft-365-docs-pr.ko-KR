---
title: Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 보안 그룹을 만들거나 편집하거나 삭제하는 방법을 학습합니다.
ms.openlocfilehash: 03e391727f9a61b1fc8e819e92d5a119017c38e0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579341"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="882cc-103">Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="882cc-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="882cc-104">Microsoft 365 **그룹** 페이지에서 SharePoint Online 및 CRM Online에서 동일한 권한을 할당하는 데 사용할 수 있는 사용자 계정 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="882cc-105">예를 들어 관리자는 보안 그룹을 만들어 특정 사용자 그룹에 SharePoint 사이트에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="882cc-106">전역 관리자와 사용자 관리 관리자만 보안 그룹을 만들거나 편집하거나 삭제할 수 있는 권한이 있습니다. 관리자 역할에 대한 자세한 내용은 관리자 역할 [할당을 참조하세요.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="882cc-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="882cc-107">전자 메일을 보내거나 사용자 그룹에 사용 권한을 할당하는 데 사용할 수 있는 [Exchange Online 및 SharePoint Online의 그룹](#groups-in-exchange-online-and-sharepoint-online), 그리고 사이트 및 사이트 모음에 대한 사용자 권한 및 액세스 권한을 부여하는 [Exchange Online 및 SharePoint Online의 그룹](#groups-in-exchange-online-and-sharepoint-online)도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="882cc-108">사이트 사서함을 사용할 계획이신가요?</span><span class="sxs-lookup"><span data-stu-id="882cc-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="882cc-109">개별적으로 추가되지 않고 보안 그룹을 통해 SharePoint 사이트에 추가되는 모든 사용자는 SharePoint를 통해서만 사이트 사서함을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="882cc-110">이러한 사용자는 Outlook에서 사이트 사서함에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="882cc-111">자세한 내용은 [Use Microsoft 365 Groups instead of Site Mailboxes을 참조하세요.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="882cc-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="882cc-112">관리 센터에서 보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="882cc-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="882cc-113">보안 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="882cc-113">Add a security group</span></span>

1. <span data-ttu-id="882cc-114">Microsoft 365 관리 센터에서 그룹 **그룹 페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="882cc-115">그룹 **페이지에서** 그룹 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="882cc-116">그룹 **유형 선택 페이지에서** 보안을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="882cc-117">단계에 따라 그룹 만들기를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="882cc-118">보안 그룹에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="882cc-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="882cc-119">그룹 페이지에서 보안 그룹  이름을 선택하고 구성원  탭에서 모두 보기 및 구성원 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="882cc-120">그룹 창에서 구성원  추가를 선택하고 목록에서 해당 사람을 선택하거나 검색 상자에 추가할  사람의 이름을 입력한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="882cc-121">구성원을 제거하려면 이름 옆에 있는 X를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-121">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="882cc-122">그룹 페이지에서 보안 그룹 이름을 **선택하고** 구성원 옆에 **있는** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-122">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="882cc-123">그룹 창에서 구성원  추가를 선택하고 목록에서 해당 사람을 선택하거나 검색 상자에 추가할  사람의 이름을 입력한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="882cc-124">구성원을 제거하려면 이름 옆에 있는 X를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="882cc-125">그룹 페이지에서 보안 그룹 이름을 **선택하고** 구성원 옆에 **있는** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="882cc-126">그룹 창에서 구성원  추가를 선택하고 목록에서 해당 사람을 선택하거나 검색 상자에 추가할  사람의 이름을 입력한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="882cc-127">구성원을 제거하려면 이름 옆에 있는 X를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-127">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="882cc-128">보안 그룹 편집</span><span class="sxs-lookup"><span data-stu-id="882cc-128">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="882cc-129">관리 센터에서 그룹 그룹  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-129">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="882cc-130">그룹 **페이지에서** 그룹의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-130">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="882cc-131">설정 창에서 일반 탭  또는 구성원  탭을 선택하여 그룹 세부 정보 또는 구성원을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-131">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="882cc-132">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">센터에서</a>그룹 그룹 **페이지로** \>  이동합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="882cc-133">그룹 **페이지에서** 그룹의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-133">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="882cc-134">보안 그룹 창에서 이름 또는 구성원  탭  옆에 있는 편집을 선택하여 그룹 세부 정보 또는 구성원을 편집합니다. </span><span class="sxs-lookup"><span data-stu-id="882cc-134">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="882cc-135">변경한 후 저장 **닫기 를** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-135">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="882cc-136">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">센터에서</a>그룹 그룹 **페이지로** \>  이동합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-136">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="882cc-137">그룹 **페이지에서** 그룹의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="882cc-138">보안 그룹 창에서 이름 또는 구성원  탭  옆에 있는 편집을 선택하여 그룹 세부 정보 또는 구성원을 편집합니다. </span><span class="sxs-lookup"><span data-stu-id="882cc-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="882cc-139">변경한 후 저장 **닫기 를** > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-139">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="882cc-140">보안 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="882cc-140">Delete a security group</span></span>

1. <span data-ttu-id="882cc-141">관리 센터에서 그룹 그룹   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-141">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="882cc-142">그룹 **페이지에서** 그룹의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-142">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="882cc-143">그룹  삭제(와세트빈 아이콘)를 선택한 다음 삭제 를 선택하여 **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-143">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="882cc-144">**그룹이** 삭제되면 닫기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-144">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="882cc-145">Exchange Online 및 SharePoint Online의 그룹</span><span class="sxs-lookup"><span data-stu-id="882cc-145">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="882cc-146">모든 사용자에게 동시에 전자 메일을 보낼 수 있도록 사용자 그룹을 만들 수 있도록 하려는 경우 Exchange  관리 센터에서 관리자 Exchange 받는 사람 그룹으로 하여 만들 \>  \> **수** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="882cc-146">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="882cc-147">그런 다음 **새로** 추가 를 선택하고 만들 그룹의 ![ ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) 종류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-147">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="882cc-148">**메일 그룹**: 사용자 그룹에 메시지를 배포하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-148">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="882cc-149">메일 사용이 가능한 메일 그룹 또는 메일 *그룹이라고도 합니다.*</span><span class="sxs-lookup"><span data-stu-id="882cc-149">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="882cc-150">자세한 내용은 [메일 그룹 관리](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="882cc-150">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="882cc-151">**보안 그룹**: 사용자 그룹에 메시지를 배포하거나 리소스에 대한 액세스 권한을 부여하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-151">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="882cc-152">이 그룹을 메일 사용이 가능한 보안 *그룹이라고도 합니다.*</span><span class="sxs-lookup"><span data-stu-id="882cc-152">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="882cc-153">자세한 내용은 [메일 사용이 가능한 보안 그룹 관리](/Exchange/recipients/mail-enabled-security-groups)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="882cc-153">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="882cc-154">**동적 메일 그룹**: 정의하는 필터 및 조건을 기반으로 메시지를 보낼 때마다 받는 사람 목록이 다시 계산되는 메일 그룹 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-154">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="882cc-155">자세한 내용은 동적 메일 그룹 [관리를 참조하세요.](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="882cc-155">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="882cc-156">Exchange 관리 센터에서 메일 그룹 및 메일 사용이 가능한 보안 그룹을 만들면 해당 이름 및 사용자 목록이 보안 그룹 **페이지에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-156">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="882cc-157">두 위치에서 모두 이러한 그룹을 삭제할 수 있지만 편집은 Exchange 관리 센터에서만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-157">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="882cc-158">동적 메일 그룹이 보안 그룹 페이지에 **표시되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-158">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="882cc-159">SharePoint 그룹은 사이트 모음을 만들 때 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-159">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="882cc-160">기본 그룹은 SharePoint의 기본 사용 권한 수준(SharePoint 역할이라고도 함)을 통해 사용자 권한 및 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-160">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="882cc-161">자세한 내용은 [SharePoint Online의 기본 SharePoint 그룹을 참조하세요.](/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="882cc-161">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="882cc-162">보안 그룹이 SharePoint에서 만드는 보안 그룹과 어떻게 다른가요?</span><span class="sxs-lookup"><span data-stu-id="882cc-162">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="882cc-163">보안 그룹은 SharePoint, Exchange, MDM, Windows 등에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-163">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="882cc-164">SharePoint에서 만드는 보안 그룹은 해당 SharePoint 사이트 모음에서만 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-164">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="882cc-165">조직을 안전하게 보호하기 위해 보안 그룹을 사용해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="882cc-165">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="882cc-166">아니요.</span><span class="sxs-lookup"><span data-stu-id="882cc-166">No.</span></span> <span data-ttu-id="882cc-167">이는 조직의 보안을 관리할 수 있는 한 가지 방법일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-167">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="882cc-168">항상 사용자 권한 및 사이트에 대한 액세스 권한을 개별적으로 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-168">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="882cc-169">그러나 보안 그룹을 사용하면 더 큰 사용자 그룹을 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-169">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="882cc-170">보안 그룹에 전자 메일을 보낼 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="882cc-170">Can I send email to a security group?</span></span>

<span data-ttu-id="882cc-171">예.</span><span class="sxs-lookup"><span data-stu-id="882cc-171">Yes.</span></span> <span data-ttu-id="882cc-172">그러나 전자 메일 및 공동 작업용 그룹을 사용하려는 경우 [대신 Microsoft 365](../create-groups/create-groups.md) 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="882cc-172">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
