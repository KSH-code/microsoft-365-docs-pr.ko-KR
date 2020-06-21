---
title: 사용자의 다른 전자 메일 별칭 추가
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
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Microsoft 365 for business 계정에 연결 된 전자 메일 주소를 두 개 이상 사용할 수 있는 방법을 알아봅니다. '
ms.openlocfilehash: c0e71ef150ccf592ea4f808a5e6609e1675767a4
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780292"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="d9c83-103">사용자의 다른 전자 메일 별칭 추가</span><span class="sxs-lookup"><span data-stu-id="d9c83-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d9c83-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-104">The admin center is changing.</span></span> <span data-ttu-id="d9c83-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9c83-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="d9c83-106">이 문서는 비즈니스 구독을 보유 하 고 있는 Microsoft 365 관리자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="d9c83-107">가정용 사용자용이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-107">It's not for home users.</span></span>
  
<span data-ttu-id="d9c83-108">Microsoft 365의 기본 전자 메일 주소는 일반적으로 계정을 만들 때 사용자에 게 할당 된 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="d9c83-109">사용자가 다른 사람에게 전자 메일을 보내면 전자 메일 앱의  *보낸 사람*  필드에 일반적으로 사용자의 기본 전자 메일 주소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="d9c83-110">또한 Microsoft 365 for business 계정에 연결 된 전자 메일 주소가 두 개 이상 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="d9c83-111">이러한 추가 주소를 별칭이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="d9c83-112">예를 들어 Jenna에 전자 메일 주소가 jenna@contosoco.com 있다고 가정 하지만 일부 사용자가 해당 이름으로 그녀를 참조 하기 때문에 jen@contosoco.com에서 전자 메일도 수신 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="d9c83-113">두 전자 메일 주소가 모두 Jenna의 받은 편지 함으로 이동 하도록 별칭을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="d9c83-114">사용자는 최대 400의 별칭을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="d9c83-115">추가 요금이나 라이선스는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="d9c83-116">여러 사용자가 info@NodPublishers.com 또는 sales@NodPublishers.com와 같은 단일 전자 메일 주소로 보내는 전자 메일을 관리 하도록 하려면 공유 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="d9c83-117">자세한 내용은 [공유 사서함 만들기](create-a-shared-mailbox.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9c83-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="d9c83-118">사용자에게 전자 메일 별칭 추가</span><span class="sxs-lookup"><span data-stu-id="d9c83-118">Add email aliases to a user</span></span>
<span data-ttu-id="d9c83-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="d9c83-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="d9c83-120">이 작업을 수행 하려면 [관리자 권한이](../add-users/about-admin-roles.md) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="d9c83-121">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="d9c83-122">**활성 사용자** 페이지에서 **전자 메일 별칭 관리**> 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="d9c83-123">사용자에 게 라이선스가 할당 되어 있지 않은 경우에는이 옵션이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="d9c83-124">**+ 별칭 추가** 를 선택 하 고 사용자의 새 별칭을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="d9c83-125">"**매개 변수 이름 ' EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다**." 라는 오류 메시지가 표시 되 면 테 넌 트 설정을 완료 하는 데 약간 시간이 걸리고, 최근에 추가한 경우 사용자 지정 도메인을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d9c83-126">설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d9c83-127">설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="d9c83-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d9c83-128">문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="d9c83-129">GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="d9c83-130">전자 메일 별칭은 드롭다운 목록의 도메인으로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="d9c83-131">목록에 다른 도메인 이름을 추가 하려면 [add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9c83-131">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="d9c83-132">작업을 마치면 **변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="d9c83-133">Office 365 전체를 새 별칭으로 채울 때까지 24시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-133">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="d9c83-134">이제 사용자에 게 기본 주소와 별칭이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="d9c83-135">예를 들어 메일이 지 민의 Hoffman의 기본 주소, Eliza@NodPublishers.com 및 별칭, Sales@NodPublishers.com 등으로 전송 되는 모든 메일은 메일이 지 민의의 받은 편지 함으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="d9c83-136">**사용자가 회신 하면 *보낸* 사람 주소가 기본 전자 메일 별칭이 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d9c83-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="d9c83-137">예를 들어 메시지가 Sales@NodPublishers.com에 게 전송 되 고 메일이 지 민의의 받은 편지함에 도착 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="d9c83-138">지민이 메시지에 회신하면 Sales@NodPublishers.com이 아니라 기본 전자 메일 주소가 보낸 사람으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="d9c83-139">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="d9c83-140">**활성 사용자** 페이지에서 편집할 사용자 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="d9c83-141">**사용자 이름/전자 메일 별칭**옆에 있는 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="d9c83-142">"**매개 변수 이름 ' EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다**." 라는 오류 메시지가 표시 되 면 테 넌 트 설정을 완료 하는 데 약간 시간이 걸리고, 최근에 추가한 경우 사용자 지정 도메인을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d9c83-143">설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d9c83-144">설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="d9c83-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d9c83-145">문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="d9c83-146">**별칭**아래의 텍스트 상자에 새 전자 메일 별칭의 첫 부분을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="d9c83-147">Office 365에 고유 도메인을 추가한 경우 드롭다운 목록을 사용하여 새 전자 메일의 도메인을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-147">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="d9c83-148">그런 다음 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d9c83-149">GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="d9c83-150">전자 메일 별칭은 드롭다운 목록의 도메인으로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="d9c83-151">목록에 다른 도메인 이름을 추가 하려면 [add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9c83-151">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="d9c83-152">작업을 마치면 **Save (저장**)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="d9c83-153">Office 365 전체를 새 별칭으로 채울 때까지 24시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-153">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="d9c83-154">이제 사용자에 게 기본 주소와 별칭이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="d9c83-155">예를 들어 메일이 지 민의 Hoffman의 기본 주소, Eliza@NodPublishers.com 및 별칭, Sales@NodPublishers.com 등으로 전송 되는 모든 메일은 메일이 지 민의의 받은 편지 함으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="d9c83-156">**사용자가 회신 하면 *보낸* 사람 주소가 기본 전자 메일 별칭이 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d9c83-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="d9c83-157">예를 들어 메시지가 Sales@NodPublishers.com에 게 전송 되 고 메일이 지 민의의 받은 편지함에 도착 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="d9c83-158">지민이 메시지에 회신하면 Sales@NodPublishers.com이 아니라 기본 전자 메일 주소가 보낸 사람으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d9c83-159">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="d9c83-160">**활성 사용자** 페이지에서 편집할 사용자 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="d9c83-161">**사용자 이름/전자 메일 별칭**옆에 있는 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="d9c83-162">"**매개 변수 이름 ' EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다**." 라는 오류 메시지가 표시 되 면 테 넌 트 설정을 완료 하는 데 약간 시간이 걸리고, 최근에 추가한 경우 사용자 지정 도메인을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d9c83-163">설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d9c83-164">설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="d9c83-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d9c83-165">문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="d9c83-166">**별칭**아래의 텍스트 상자에 새 전자 메일 별칭의 첫 부분을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="d9c83-167">Office 365에 고유 도메인을 추가한 경우 드롭다운 목록을 사용하여 새 전자 메일의 도메인을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-167">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="d9c83-168">그런 다음 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d9c83-169">GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="d9c83-170">전자 메일 별칭은 드롭다운 목록의 도메인으로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="d9c83-171">목록에 다른 도메인 이름을 추가 하려면 [add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9c83-171">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="d9c83-172">작업을 마치면 **Save (저장**)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="d9c83-173">Office 365 전체를 새 별칭으로 채울 때까지 24시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-173">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="d9c83-174">이제 사용자에 게 기본 주소와 별칭이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="d9c83-175">예를 들어 메일이 지 민의 Hoffman의 기본 주소, Eliza@NodPublishers.com 및 별칭, Sales@NodPublishers.com 등으로 전송 되는 모든 메일은 메일이 지 민의의 받은 편지 함으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="d9c83-176">**사용자가 회신 하면 *보낸* 사람 주소가 기본 전자 메일 별칭이 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d9c83-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="d9c83-177">예를 들어 메시지가 Sales@NodPublishers.com에 게 전송 되 고 메일이 지 민의의 받은 편지함에 도착 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="d9c83-178">지민이 메시지에 회신하면 Sales@NodPublishers.com이 아니라 기본 전자 메일 주소가 보낸 사람으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="d9c83-179">"Parameter name EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다." 라는 메시지가 표시 되었습니까?</span><span class="sxs-lookup"><span data-stu-id="d9c83-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="d9c83-180">"**매개 변수 이름 EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다**." 라는 오류 메시지가 표시 되 면 테 넌 트 설정이 완료 되는 데 시간이 더 오래 걸리거나 사용자 지정 도메인이 최근에 추가 된 경우에는이를 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d9c83-181">설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d9c83-182">설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="d9c83-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d9c83-183">문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="d9c83-184">GoDaddy 또는 다른 파트너로부터 구독을 구입했나요?</span><span class="sxs-lookup"><span data-stu-id="d9c83-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="d9c83-185">GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9c83-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d9c83-186">관련 문서</span><span class="sxs-lookup"><span data-stu-id="d9c83-186">Related articles</span></span>

[<span data-ttu-id="d9c83-187">다른 주소에서 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="d9c83-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="d9c83-188">사용자 이름 및 이메일 주소 변경</span><span class="sxs-lookup"><span data-stu-id="d9c83-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

