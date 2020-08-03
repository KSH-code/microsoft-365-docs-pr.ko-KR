---
title: 공유 사서함 만들기
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: 공유 사서함을 만들어 회사의 여러 사용자가 하나의 주소로 전송된 전자 메일을 읽고 답장하는 업무를 나눌 수 있습니다.
ms.openlocfilehash: 47690e1295b67c01f86429d97e0fc8d82ad58d6f
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529638"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="2160b-103">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="2160b-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="2160b-104">조직에서 하이브리드 Exchange 환경을 사용하는 경우 온-프레미스 EAC(Exchange 관리 센터)를 사용하여 공유 사서함을 만들고 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="2160b-105">[Exchange 관리 센터에서 공유 사서함을 만드는 방법](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2160b-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span></span><br><br>
> <span data-ttu-id="2160b-106">공유 사서함 또는 Outlook용 Microsoft 365 그룹 중 무엇을 만들어야 하는지 확실하지 않은 경우 [Compare groups](../create-groups/compare-groups.md)(그룹 비교)에서 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2160b-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="2160b-107">현재 공유 사서함은 Microsoft 365 그룹으로 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="2160b-108">이것이 원하는 것이라면 [여기에서 투표](https://go.microsoft.com/fwlink/?linkid=871518)를 통해 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="2160b-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="2160b-p103">사용자 그룹이 info@contoso.com과 같은 공통 전자 메일 주소에서 전자 메일을 모니터링하고 보낼 수 있도록 공유 사서함을 만들 수 있습니다. 그룹에 속한 사용자가 공유 사서함에 전송된 메시지에 회신하면 해당 전자 메일은 개별 사용자가 아닌 공유 사서함에서 발송된 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="2160b-111">공유 사서함에는 공유 일정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="2160b-112">여러 중소기업에서는 모든 직원이 약속을 입력할 수 있는 공유 일정을 즐겨 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="2160b-113">예를 들어 고객을 방문하는 직원이 세 명 있는 경우 세 명 모두 공유 일정을 사용하여 약속을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="2160b-114">이렇게 하면 누가 어디에 있는지 모두에게 쉽게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="2160b-115">공유 사서함을 만들기 전에 자세한 내용은 [공유 사서함 정보](about-shared-mailboxes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2160b-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="2160b-116">공유 사서함 만들기 및 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="2160b-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="2160b-117">전역 관리자 계정 또는 Exchange 관리자 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="2160b-118">“**이 페이지에 액세스하거나 이 작업을 수행할 권한이 없습니다**”메시지가 나타나는 경우 관리자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="2160b-119">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="2160b-120">[관리 센터](https://go.microsoft.com/fwlink/p/?linkid=848041)에서 **그룹** \> **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="2160b-121">[관리 센터](https://go.microsoft.com/fwlink/p/?linkid=850627)에서 **그룹** \> **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="2160b-122">**공유 사서함** 페이지에서 **+ 사서함 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="2160b-123">공유 사서함의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="2160b-124">마법사에서 이름이 선택되지만, 원하는 경우 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![공유 사서함 이름을 지정합니다.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="2160b-126">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-126">Select **Add**.</span></span> <span data-ttu-id="2160b-127">몇 분 정도 기다린 다음에 구성원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="2160b-128">**다음 단계**에서 **이 사서함에 구성원 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="2160b-129">구성원은 이 공유 사서함으로 받는 메일과 보내는 회신을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![구성원 추가를 선택합니다.](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="2160b-131">**+구성원 추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-131">Select the **+Add members** button.</span></span> <span data-ttu-id="2160b-132">이 공유 사서함을 사용할 사람 옆에 확인 표시를 하고 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![공유 사서함에 구성원을 할당합니다.](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="2160b-134">**닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-134">Select **Close**.</span></span>

<span data-ttu-id="2160b-135">공유 일정이 포함된 공유 사서함을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="2160b-136">이제 다음 단계인 공유 사서함 계정에 대한 로그인 차단으로 넘어갑니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="2160b-137">공유 사서함 계정에 대한 로그인 차단</span><span class="sxs-lookup"><span data-stu-id="2160b-137">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="2160b-138">모든 공유 사서함에는 해당하는 사용자 계정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-138">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="2160b-139">공유 사서함을 만들 때 암호를 입력하라는 메시지가 표시되지 않으면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="2160b-139">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="2160b-140">계정에 암호가 있지만 시스템이 생성(알 수 없음)한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-140">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="2160b-141">계정을 사용하여 공유 사서함에 로그인해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-141">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="2160b-142">그러나 관리자가 단순히 공유 사서함 사용자 계정의 암호를 재설정하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="2160b-142">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="2160b-143">또는 공격자가 공유 사서함 계정 자격 증명에 대한 액세스 권한을 얻으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="2160b-143">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="2160b-144">이런 경우 사용자 계정이 공유 사서함에 로그인하여 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-144">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="2160b-145">이를 방지하려면 공유 사서함에 연결된 계정에 대한 로그인을 차단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-145">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="2160b-146">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="2160b-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2160b-147">사용자 계정 목록에서 공유 사서함의 계정을 찾습니다(예: 필터를 **라이선스가 없는 사용자**로 변경).</span><span class="sxs-lookup"><span data-stu-id="2160b-147">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="2160b-148">사용자를 선택하여 속성 창을 연 다음 **이 사용자 차단** 아이콘 및 ![이 사용자 차단 아이콘의 스크린 샷](../../media/block-user-icon.png)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-148">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="2160b-149">**참고**: 계정이 이미 차단된 경우 상단에 **로그인 차단됨**이 표시되고 아이콘은 **이 사용자 차단 해제**로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-149">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="2160b-150">**이 사용자를 차단할까요?** 창에서 **사용자의 로그인 차단**을 선택한 다음 **변경 사항 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-150">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="2160b-151">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2160b-152">사용자 계정 목록에서 공유 사서함의 계정을 찾은 다음(예: 보기를 **라이선스가 없는 사용자**로 변경) 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-152">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="2160b-153">속성 플라이 아웃에서 **로그인 차단**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-153">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="2160b-154">**참고:** 계정이 이미 차단된 경우 단추에 **로그인 차단 해제**가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-154">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="2160b-155">**로그인 상태 편집** 플라이 아웃에서 사용자의 로그인 차단이 선택되어 있는지 확인한 후 **저장**을 선택한 다음 **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-155">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2160b-156">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2160b-157">사용자 계정 목록에서 공유 사서함의 계정을 찾은 다음(예: 보기를 **라이선스가 없는 사용자**로 변경) 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-157">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="2160b-158">속성 플라이 아웃에서 **로그인 차단**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-158">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="2160b-159">**참고:** 계정이 이미 차단된 경우 단추에 **로그인 차단 해제**가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-159">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="2160b-160">**로그인 상태 편집** 플라이 아웃에서 사용자의 로그인 차단이 선택되어 있는지 확인한 후 **저장**을 선택한 다음 **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-160">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="2160b-161">Azure AD PowerShell을 사용하여 계정에 대한 로그인을 차단하는 방법(동시에 여러 계정 포함)에 대한 자세한 내용은 [Office 365 PowerShell을 사용하여 사용자 계정 차단](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2160b-161">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="2160b-162">공유 사서함을 Outlook에 추가</span><span class="sxs-lookup"><span data-stu-id="2160b-162">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="2160b-163">회사에서 automapping을 활성화한 경우(대부분의 사용자가 기본값으로 활성화함) Outlook을 종료하고 다시 시작하면 사용자의 Outlook 앱에 공유 사서함이 자동으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-163">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="2160b-164">Automapping은 공유 사서함이 아니라 사용자의 사서함에서 설정됩니다.  </span><span class="sxs-lookup"><span data-stu-id="2160b-164">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="2160b-165">즉 보안 그룹을 사용하여 공유 사서함에 액세스할 수 있는 사용자를 관리하려는 경우 automapping이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-165">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="2160b-166">따라서 automapping을 사용하려면 사용 권한을 명시적으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-166">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="2160b-167">Automapping은 기본적으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-167">Automapping is on by default.</span></span> <span data-ttu-id="2160b-168">이 기능을 해제하는 방법은 [공유 사서함에 대한 automapping 제거](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2160b-168">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="2160b-169">Outlook의 공유 사서함에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2160b-169">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="2160b-170"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Outlook에서 공유 사서함 열기 및 사용</a></span><span class="sxs-lookup"><span data-stu-id="2160b-170"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="2160b-171"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">웹용 Outlook에 공유 사서함 추가</a></span><span class="sxs-lookup"><span data-stu-id="2160b-171"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="2160b-172"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook 모바일에 공유 사서함 추가</a></span><span class="sxs-lookup"><span data-stu-id="2160b-172"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="2160b-173"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Mac 용 Outlook에서 공유 폴더 또는 사서함 열기</a></span><span class="sxs-lookup"><span data-stu-id="2160b-173"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="2160b-174"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">공유 사서함에 규칙 추가</a></span><span class="sxs-lookup"><span data-stu-id="2160b-174"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="2160b-175">모바일 장치(휴대폰 또는 태블릿)에서 공유 사서함 사용</span><span class="sxs-lookup"><span data-stu-id="2160b-175">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="2160b-176">다음 두 가지 방법으로 모바일 장치의 공유 사서함에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-176">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="2160b-177"><a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">iOS용 Outlook 앱</a> 또는 <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Android 모바일용 Outlook 앱</a>에서 공유 사서함을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-177">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="2160b-178">자세한 내용은 <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook 모바일에 공유 사서함 추가</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2160b-178">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="2160b-179">브라우저를 열고 로그인한 다음 웹용 Outlook으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-179">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="2160b-180">웹용 Outlook에서 공유 사서함에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-180">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="2160b-181">자세한 내용은 <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">웹용 Outlook에 공유 사서함 추가</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2160b-181">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2160b-182">공유 사서함은 Outlook for iOS 앱 또는 Outlook for Android 모바일 앱에만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-182">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="2160b-183">공유 일정 사용</span><span class="sxs-lookup"><span data-stu-id="2160b-183">Use the shared calendar</span></span>

<span data-ttu-id="2160b-184">공유 사서함을 만들면 공유 일정이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-184">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="2160b-185">약속과 사람들이 있는 장소를 계속 확인하기 위해 SharePoint 일정보다는 공유 사서함 일정을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-185">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="2160b-186">공유 일정은 Outlook과 통합되어 있으며 SharePoint 일정보다 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-186">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="2160b-187">Outlook 앱에서 일정 보기로 이동하고 공유 사서함을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="2160b-187">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="2160b-188">약속을 입력하면 공유 사서함의 구성원 모두가 약속을 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="2160b-188">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="2160b-189">공유 사서함의 모든 구성원은 개인 약속과 마찬가지로 일정에 대한 약속을 만들고보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-189">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="2160b-190">공유 사서함의 구성원인 모든 사용자는 공유 일정에 따른 변경 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2160b-190">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2160b-191">관련 문서</span><span class="sxs-lookup"><span data-stu-id="2160b-191">Related articles</span></span>

[<span data-ttu-id="2160b-192">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="2160b-192">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="2160b-193">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="2160b-193">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="2160b-194">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="2160b-194">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="2160b-195">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="2160b-195">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="2160b-196">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2160b-196">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)





