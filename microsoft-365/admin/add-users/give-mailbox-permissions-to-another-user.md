---
title: 다른 사용자에게 사서함 권한 제공 - 관리자 도움말
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 사용자에게 다른 사용자의 사서함에 액세스할 수 있는 권한을 부여합니다. 그러면 사용자가 다른 사용자의 사서함에서 전자 메일을 읽고 보낼 수 있습니다.
ms.openlocfilehash: 0e5f7b154fa37ae9775e7208574b2a5395e7c239
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634283"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="ff634-103">다른 사용자에게 사서함 권한 제공 - 관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="ff634-103">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="ff634-p101">관리자는 회사의 필요에 따라 일부 사용자가 다른 사용자의 사서함에 액세스할 수 있도록 허용해야 할 수 있습니다. 예를 들어 비서가 관리자의 사서함에서 전자 메일을 읽고 보낼 수 있도록 허용해야 하거나, 한 사용자가 다른 사용자를 대신해서 전자 메일을 보낼 수 있게 허용해야 할 수 있습니다. 이 항목에서는 이러한 작업을 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-p101">As the admin, you may have company requirements to allow some users access to another user's mailbox. For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user. This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="ff634-107">공유 사서함 만들기 및 관리에 대한 자세한 내용은 [공유 사서함 만들기](../email/create-a-shared-mailbox.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ff634-107">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="ff634-108">사서함 사용 권한을 설정하려고 하나요?</span><span class="sxs-lookup"><span data-stu-id="ff634-108">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="ff634-p102">사서함 사용 권한을 사용하여 다른 사용자에게 사서함에 대한 읽기/쓰기 권한을 부여할 수 있습니다. 아래 문서는 이 기능을 설정하고 사용하는 데 필요한 도움말을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-p102">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="ff634-111">**사용 권한 설정:**</span><span class="sxs-lookup"><span data-stu-id="ff634-111">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="ff634-p103">사용 권한을 설정하는 첫 번째 단계는 다른 사용자가 지정된 사서함에서 수행할 수 있도록 할 작업을 결정하는 것입니다. 사용자가 사서함에서 전자 메일을 읽고, 다른 사용자를 대신하여 전자 메일을 보내고, 해당 사서함에서 전송된 것처럼 전자 메일을 보내도록 허용할 수 있습니다. 각 사용 권한 유형을 설정하는 방법에 대해서는 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff634-p103">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="ff634-115">다른 사용자의 사서함에서 전자 메일 읽기</span><span class="sxs-lookup"><span data-stu-id="ff634-115">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="ff634-116">다른 사용자의 사서함에서 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="ff634-116">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="ff634-117">다른 사용자를 대신하여 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="ff634-117">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="ff634-118">**전파 변경:**</span><span class="sxs-lookup"><span data-stu-id="ff634-118">**Changing propagation:**</span></span>
  
<span data-ttu-id="ff634-119">사용 권한을 설정한 후 변경 내용이 시스템을 통해 전파되고 적용될 때까지 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-119">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="ff634-120">**사용 권한을 설정한 후 사용하는 방법:**</span><span class="sxs-lookup"><span data-stu-id="ff634-120">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="ff634-p104">액세스 권한이 부여된 후 사서함에 액세스하는 방법은 여러 가지가 있습니다. 이 내용에 대한 도움말은 [다른 사용자의 사서함에 액세스](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff634-p104">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="ff634-123">권한은 현재 조직 테넌트 내에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-123">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="ff634-124">테넌트 외 사용자로는 사서함 사용 권한을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-124">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="ff634-125">다른 사용자의 사서함에서 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="ff634-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ff634-126">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="ff634-127">사용자의 이름(보내기 권한을 부여할 사용자)을 선택하고 해당 속성 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="ff634-128">**메일** 탭에서 **사서함 권한 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="ff634-129">**보내기** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="ff634-130">**권한 추가** 를 선택한 다음 보내기 권한을 부여할 사용자의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="ff634-131">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ff634-132">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="ff634-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ff634-133">원하는 사용자를 선택하고 **메일 설정** 을 펼친 후 **사서함 권한** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ff634-134">**보내기** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="ff634-135">**권한 추가** 를 선택한 다음 보내기 권한을 부여할 사용자의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="ff634-136">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ff634-137">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="ff634-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="ff634-138">원하는 사용자를 선택하고 **메일 설정** 을 펼친 후 **사서함 권한** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ff634-139">**보내기** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="ff634-140">**권한 추가** 를 선택한 다음 보내기 권한을 부여할 사용자의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="ff634-141">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="ff634-142">다른 사용자의 사서함에 있는 전자 메일 읽기</span><span class="sxs-lookup"><span data-stu-id="ff634-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ff634-143">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="ff634-144">사용자의 이름(읽을 사서함의 사용자)을 선택하고 해당 속성 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="ff634-145">**메일** 탭에서 **사서함 권한 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="ff634-146">**읽기 및 관리** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="ff634-147">**권한 추가** 를 선택한 다음 해당 사서함에서 전자 메일 읽기를 허용할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="ff634-148">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-148">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="ff634-149">Exchange 관리 센터에서 부여된 경우 **읽기** 와 **관리** 권한을 **전체 액세스** 권한이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-149">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="ff634-150">전체 액세스 권한은 **다른 이름으로 보내기** 또는 **대신 보내기** 권한을 부여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-150">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ff634-151">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="ff634-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="ff634-152">원하는 사용자를 선택하고 **메일 설정** 을 펼친 후 **사서함 권한** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-152">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="ff634-153">**읽기 및 관리** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-153">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="ff634-154">**권한 추가** 를 선택한 다음 해당 사서함에서 전자 메일 읽기를 허용할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-154">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="ff634-155">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-155">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ff634-156">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="ff634-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="ff634-157">원하는 사용자를 선택하고 **메일 설정** 을 펼친 후 **사서함 권한** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-157">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="ff634-158">**읽기 및 관리** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-158">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="ff634-159">**권한 추가** 를 선택한 다음 해당 사서함에서 전자 메일 읽기를 허용할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-159">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="ff634-160">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-160">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="ff634-161">다른 사용자를 대신하여 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="ff634-161">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ff634-162">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-162">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ff634-163">사용자의 이름(**대신 보내기** 권한을 부여할 사용자)을 선택하고 해당 속성 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-163">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="ff634-164">**메일** 탭에서 **사서함 권한 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-164">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="ff634-165">**대신 보내기** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-165">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="ff634-166">**권한 추가** 를 선택한 다음 해당 사서함을 대신하여 전자 메일 보내기를 허용할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-166">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="ff634-167">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-167">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ff634-168">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="ff634-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ff634-169">원하는 사용자를 선택하고 **메일 설정** 을 펼친 후 **사서함 권한** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-169">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ff634-170">**대신 보내기** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-170">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="ff634-171">**권한 추가** 를 선택한 다음 해당 사서함을 대신하여 전자 메일 보내기를 허용할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-171">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="ff634-172">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-172">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ff634-173">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="ff634-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="ff634-174">원하는 사용자를 선택하고 **메일 설정** 을 펼친 후 **사서함 권한** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-174">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ff634-175">**대신 보내기** 옆에 있는 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-175">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="ff634-176">**권한 추가** 를 선택한 다음 해당 사서함을 대신하여 전자 메일 보내기를 허용할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-176">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="ff634-177">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff634-177">Select **Save**.</span></span>

::: moniker-end


## <a name="related-content"></a><span data-ttu-id="ff634-178">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="ff634-178">Related content</span></span>
  
<span data-ttu-id="ff634-179">[다른 사용자의 메일 및 일정 항목 관리](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)(문서)</span><span class="sxs-lookup"><span data-stu-id="ff634-179">[Manage another person's mail and calendar items](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (article)</span></span>\   
<span data-ttu-id="ff634-180">[다른 사용자 또는 그룹 이름으로 전자 메일 보내기](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)(문서)</span><span class="sxs-lookup"><span data-stu-id="ff634-180">[Send email from another person or group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (article)</span></span>\
<span data-ttu-id="ff634-181">[사용자 이름 및 전자 메일 주소 변경](../add-users/change-a-user-name-and-email-address.md)(비디오)</span><span class="sxs-lookup"><span data-stu-id="ff634-181">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (video)</span></span>

