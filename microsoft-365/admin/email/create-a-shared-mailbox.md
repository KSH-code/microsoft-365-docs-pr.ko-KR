---
title: 공유 사서함 만들기
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: 공유 사서함을 만들어 회사의 여러 사용자가 하나의 주소로 전송된 전자 메일을 읽고 답장하는 업무를 나눌 수 있습니다.
ms.openlocfilehash: e628d72482ed7ff32a204eaf9503fdd9a271844a
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635501"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="ce264-103">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="ce264-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="ce264-104">조직에서 하이브리드 Exchange 환경을 사용하는 경우 온-프레미스 EAC(Exchange 관리 센터)를 사용하여 공유 사서함을 만들고 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="ce264-105">[Exchange 관리 센터에서 공유 사서함을 만드는 방법](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce264-105">See [Create shared mailboxes in the Exchange admin center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span></span><br><br>
> <span data-ttu-id="ce264-106">공유 사서함 또는 Outlook용 Microsoft 365 그룹 중 무엇을 만들어야 하는지 확실하지 않은 경우 [Compare groups](../create-groups/compare-groups.md)(그룹 비교)에서 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ce264-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="ce264-107">현재 공유 사서함은 Microsoft 365 그룹으로 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="ce264-108">이것이 원하는 것이라면 [여기에서 투표](https://go.microsoft.com/fwlink/?linkid=871518)를 통해 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="ce264-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="ce264-p103">사용자 그룹이 info@contoso.com과 같은 공통 전자 메일 주소에서 전자 메일을 모니터링하고 보낼 수 있도록 공유 사서함을 만들 수 있습니다. 그룹에 속한 사용자가 공유 사서함에 전송된 메시지에 회신하면 해당 전자 메일은 개별 사용자가 아닌 공유 사서함에서 발송된 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="ce264-p104">공유 사서함에는 공유 일정이 포함됩니다. 여러 중소기업에서는 모든 직원이 약속을 입력할 수 있는 공유 일정을 즐겨 사용합니다. 예를 들어 고객을 방문하는 직원이 세 명 있는 경우 세 명 모두 공유 일정을 사용하여 약속을 입력할 수 있습니다. 이렇게 하면 누가 어디에 있는지 모두에게 쉽게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-p104">Shared mailboxes include a shared calendar. A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments. For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments. This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="ce264-115">공유 사서함을 만들기 전에 자세한 내용은 [공유 사서함 정보](about-shared-mailboxes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce264-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="ce264-116">공유 사서함 만들기 및 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="ce264-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="ce264-117">전역 관리자 계정 또는 Exchange 관리자 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="ce264-118">“**이 페이지에 액세스하거나 이 작업을 수행할 권한이 없습니다**”메시지가 나타나는 경우 관리자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="ce264-119">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="ce264-120">[관리 센터](https://go.microsoft.com/fwlink/p/?linkid=848041)에서 **그룹** \> **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="ce264-121">[관리 센터](https://go.microsoft.com/fwlink/p/?linkid=850627)에서 **그룹** \> **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="ce264-122">**공유 사서함** 페이지에서 **+ 사서함 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="ce264-123">공유 사서함의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="ce264-124">마법사에서 이름이 선택되지만, 원하는 경우 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![공유 사서함 이름을 지정합니다.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="ce264-126">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-126">Select **Add**.</span></span> <span data-ttu-id="ce264-127">몇 분 정도 기다린 다음에 구성원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="ce264-128">**다음 단계** 에서 **이 사서함에 구성원 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="ce264-129">구성원은 이 공유 사서함으로 받는 메일과 보내는 회신을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![구성원 추가를 선택합니다.](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="ce264-131">**+구성원 추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-131">Select the **+Add members** button.</span></span> <span data-ttu-id="ce264-132">이 공유 사서함을 사용할 사람 옆에 확인 표시를 하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![공유 사서함에 구성원을 할당합니다.](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="ce264-134">**닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-134">Select **Close**.</span></span>

<span data-ttu-id="ce264-135">공유 일정이 포함된 공유 사서함을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="ce264-136">이제 다음 단계인 공유 사서함 계정에 대한 로그인 차단으로 넘어갑니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="which-permissions-should-you-use"></a><span data-ttu-id="ce264-137">사용해야 하는 권한</span><span class="sxs-lookup"><span data-stu-id="ce264-137">Which permissions should you use?</span></span>

<span data-ttu-id="ce264-138">공유 사서함에서 다음 사용 권한을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-138">You can use the following permissions with a shared mailbox:</span></span>

- <span data-ttu-id="ce264-139">**모든 액세스 권한**: 모든 권한이 있는 사용자는 공유 사서함을 열어 해당 사서함의 소유자로서 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-139">**Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox.</span></span> <span data-ttu-id="ce264-140">공유 사서함에 액세스한 후 사용자는 일정 항목을 만들고, 전자 메일 메시지를 읽고, 보고, 삭제하고, 변경하고, 작업 및 일정 연락처를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-140">After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts.</span></span> <span data-ttu-id="ce264-141">그러나 모든 권한을 가진 사용자라도 다른 사람 이름으로 보내기 또는 대신 보내기 사용 권한이 없으면 공유 사서함에서 전자 메일을 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-141">However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.</span></span>

- <span data-ttu-id="ce264-142">**다른 사람 이름으로 보내기**: 다른 사람 이름으로 보내기 사용 권한을 부여하면 사용자가 전자 메일을 보낼 때 공유 사서함인 것처럼 보이게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-142">**Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail.</span></span> <span data-ttu-id="ce264-143">예를 들어 Katerina가 마케팅 부서의 공유 사서함에 로그인하여 전자 메일을 보낸 경우에는 마케팅 부서에서 전자 메일을 보낸 것으로 보입니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-143">For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.</span></span>

- <span data-ttu-id="ce264-144">**대신 보내기**: 대신 보내기 권한이 있는 사용자는 공유 사서함 대신 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-144">**Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox.</span></span> <span data-ttu-id="ce264-145">예를 들면 John이 Reception Building 32 공유 사서함에 로그인하여 이메일을 보내면, "Reception Building 32 대신 John"이 보낸 것처럼 메일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-145">For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32".</span></span> <span data-ttu-id="ce264-146">EAC를 사용하여 대신 보내기 사용 권한을 부여할 수는 없습니다. 대신 보내기 사용 권한을 부여하려면 **Set-Mailbox** cmdlet을 _GrantSendonBehalf_ 매개 변수와 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-146">You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.</span></span>

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a><span data-ttu-id="ce264-147">EAC를 사용하여 공유 사서함 위임 편집</span><span class="sxs-lookup"><span data-stu-id="ce264-147">Use the EAC to edit shared mailbox delegation</span></span>

1. <span data-ttu-id="ce264-148">EAC에서 **받는 사람** > \>**공유** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-148">In the EAC, go to **Recipients** \> **Shared**.</span></span> <span data-ttu-id="ce264-149">공유 사서함을 선택한 다음 **편집** ![편집 아이콘](../../media/ITPro-EAC-EditIcon.png)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-149">Select the shared mailbox, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="ce264-150">**사서함 위임** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-150">Select **Mailbox delegation**.</span></span>

3. <span data-ttu-id="ce264-151">모든 권한 및 다른 사람 권한을 부여하거나 제거하려면 **아이콘** ![아이콘 추가](../../media/ITPro-EAC-AddIcon.png) 또는 **제거** ![아이콘 제거](../../media/ITPro-EAC-RemoveIcon.gif)를 선택한 다음 사용 권한을 부여할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-151">To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ce264-p115">모든 액세스 권한을 사용하면 사서함을 열 수 있을 뿐만 아니라 사서함에서 항목을 만들고 수정할 수 있습니다. 다른 사람 이름으로 보내기 권한을 사용하면 사서함 소유자가 아닌 사용자가 공유 사서함에서 전자 메일을 보낼 수 있습니다. 두 권한 모두 공유 사서함 작업에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-p115">The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.</span></span>

4. <span data-ttu-id="ce264-155">변경 내용을 저장하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-155">Select **Save** to save your changes.</span></span>


## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="ce264-156">공유 사서함 계정에 대한 로그인 차단</span><span class="sxs-lookup"><span data-stu-id="ce264-156">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="ce264-157">모든 공유 사서함에는 해당하는 사용자 계정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-157">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="ce264-158">공유 사서함을 만들 때 암호를 입력하라는 메시지가 표시되지 않으면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="ce264-158">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="ce264-159">계정에 암호가 있지만 시스템이 생성(알 수 없음)한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-159">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="ce264-160">계정을 사용하여 공유 사서함에 로그인해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-160">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="ce264-161">그러나 관리자가 단순히 공유 사서함 사용자 계정의 암호를 재설정하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="ce264-161">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="ce264-162">또는 공격자가 공유 사서함 계정 자격 증명에 대한 액세스 권한을 얻으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="ce264-162">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="ce264-163">이런 경우 사용자 계정이 공유 사서함에 로그인하여 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-163">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="ce264-164">이를 방지하려면 공유 사서함에 연결된 계정에 대한 로그인을 차단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-164">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ce264-165">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="ce264-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ce264-166">사용자 계정 목록에서 공유 사서함의 계정을 찾습니다(예: 필터를 **라이선스가 없는 사용자** 로 변경).</span><span class="sxs-lookup"><span data-stu-id="ce264-166">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="ce264-167">사용자를 선택하여 속성 창을 연 다음 **이 사용자 차단** 아이콘 및 ![이 사용자 차단 아이콘의 스크린 샷](../../media/block-user-icon.png)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-167">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="ce264-168">**참고**: 계정이 이미 차단된 경우 상단에 **로그인 차단됨** 이 표시되고 아이콘은 **이 사용자 차단 해제** 로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-168">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="ce264-169">**이 사용자를 차단할까요?** 창에서 **사용자의 로그인 차단** 을 선택한 다음 **변경 사항 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-169">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ce264-170">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ce264-171">사용자 계정 목록에서 공유 사서함의 계정을 찾은 다음(예: 보기를 **라이선스가 없는 사용자** 로 변경) 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-171">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="ce264-172">속성 플라이 아웃에서 **로그인 차단** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-172">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="ce264-173">**참고:** 계정이 이미 차단된 경우 단추에 **로그인 차단 해제** 가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-173">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="ce264-174">**로그인 상태 편집** 플라이 아웃에서 사용자의 로그인 차단이 선택되어 있는지 확인한 후 **저장** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-174">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ce264-175">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-175">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ce264-176">사용자 계정 목록에서 공유 사서함의 계정을 찾은 다음(예: 보기를 **라이선스가 없는 사용자** 로 변경) 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-176">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="ce264-177">속성 플라이 아웃에서 **로그인 차단** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-177">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="ce264-178">**참고:** 계정이 이미 차단된 경우 단추에 **로그인 차단 해제** 가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-178">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="ce264-179">**로그인 상태 편집** 플라이 아웃에서 사용자의 로그인 차단이 선택되어 있는지 확인한 후 **저장** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-179">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="ce264-180">Azure AD PowerShell을 사용하여 계정에 대한 로그인을 차단하는 방법(동시에 여러 계정 포함)에 대한 자세한 내용은 [Office 365 PowerShell을 사용하여 사용자 계정 차단](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce264-180">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="ce264-181">공유 사서함을 Outlook에 추가</span><span class="sxs-lookup"><span data-stu-id="ce264-181">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="ce264-182">회사에서 automapping을 활성화한 경우(대부분의 사용자가 기본값으로 활성화함) Outlook을 종료하고 다시 시작하면 사용자의 Outlook 앱에 공유 사서함이 자동으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-182">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="ce264-183">Automapping은 공유 사서함이 아니라 사용자의 사서함에서 설정됩니다.  </span><span class="sxs-lookup"><span data-stu-id="ce264-183">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="ce264-184">즉 보안 그룹을 사용하여 공유 사서함에 액세스할 수 있는 사용자를 관리하려는 경우 automapping이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-184">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="ce264-185">따라서 automapping을 사용하려면 사용 권한을 명시적으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-185">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="ce264-186">Automapping은 기본적으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-186">Automapping is on by default.</span></span> <span data-ttu-id="ce264-187">이 기능을 해제하는 방법은 [공유 사서함에 대한 automapping 제거](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce264-187">To learn how to turn it off, see [Remove automapping for a shared mailbox](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="ce264-188">Outlook의 공유 사서함에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce264-188">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="ce264-189"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Outlook에서 공유 사서함 열기 및 사용</a></span><span class="sxs-lookup"><span data-stu-id="ce264-189"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="ce264-190"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">웹용 Outlook에 공유 사서함 추가</a></span><span class="sxs-lookup"><span data-stu-id="ce264-190"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="ce264-191"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook 모바일에 공유 사서함 추가</a></span><span class="sxs-lookup"><span data-stu-id="ce264-191"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="ce264-192"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Mac 용 Outlook에서 공유 폴더 또는 사서함 열기</a></span><span class="sxs-lookup"><span data-stu-id="ce264-192"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="ce264-193"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">공유 사서함에 규칙 추가</a></span><span class="sxs-lookup"><span data-stu-id="ce264-193"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="ce264-194">모바일 장치(휴대폰 또는 태블릿)에서 공유 사서함 사용</span><span class="sxs-lookup"><span data-stu-id="ce264-194">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="ce264-195">다음 두 가지 방법으로 모바일 장치의 공유 사서함에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-195">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="ce264-196"><a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">iOS용 Outlook 앱</a> 또는 <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Android 모바일용 Outlook 앱</a>에서 공유 사서함을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-196">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="ce264-197">자세한 내용은 <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook 모바일에 공유 사서함 추가</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce264-197">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="ce264-198">브라우저를 열고 로그인한 다음 웹용 Outlook으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-198">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="ce264-199">웹용 Outlook에서 공유 사서함에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-199">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="ce264-200">자세한 내용은 <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">웹용 Outlook에 공유 사서함 추가</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce264-200">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ce264-201">공유 사서함은 Outlook for iOS 앱 또는 Outlook for Android 모바일 앱에만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-201">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="ce264-202">공유 일정 사용</span><span class="sxs-lookup"><span data-stu-id="ce264-202">Use the shared calendar</span></span>

<span data-ttu-id="ce264-203">공유 사서함을 만들면 공유 일정이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-203">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="ce264-204">약속과 사람들이 있는 장소를 계속 확인하기 위해 SharePoint 일정보다는 공유 사서함 일정을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-204">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="ce264-205">공유 일정은 Outlook과 통합되어 있으며 SharePoint 일정보다 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-205">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="ce264-206">Outlook 앱에서 일정 보기로 이동하고 공유 사서함을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="ce264-206">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="ce264-207">약속을 입력하면 공유 사서함의 구성원 모두가 약속을 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="ce264-207">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="ce264-208">공유 사서함의 모든 구성원은 개인 약속과 마찬가지로 일정에 대한 약속을 만들고보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-208">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="ce264-209">공유 사서함의 구성원인 모든 사용자는 공유 일정에 따른 변경 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce264-209">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-content"></a><span data-ttu-id="ce264-210">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="ce264-210">Related content</span></span>

<span data-ttu-id="ce264-211">[공유 사서함 정보](about-shared-mailboxes.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="ce264-211">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="ce264-212">[공유 사서함 구성](configure-a-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="ce264-212">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ce264-213">[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="ce264-213">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ce264-214">[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="ce264-214">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ce264-215">[공유 사서함 문제 해결](resolve-issues-with-shared-mailboxes.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="ce264-215">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>