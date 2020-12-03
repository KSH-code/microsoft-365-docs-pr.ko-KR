---
title: 전자 메일 전달 구성
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365을 사용 하 여 하나 이상의 전자 메일 계정으로 전자 메일을 전달 하도록 설정 합니다.
ms.openlocfilehash: c821d4363a053b432c4376d7b4fec4926df7b568
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560795"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="1e620-103">전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="1e620-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1e620-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-104">The admin center is changing.</span></span> <span data-ttu-id="1e620-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e620-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="1e620-106">조직의 관리자는 사용자 사서함에 대 한 전자 메일 전달을 설정 하기 위한 회사 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="1e620-107">전자 메일 전달을 사용 하면 사용자의 사서함에 전송 된 전자 메일 메시지를 조직의 내부 또는 외부에 있는 다른 사용자의 사서함으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e620-108">아웃 바운드 스팸 필터 정책을 사용 하 여 외부의 받는 사람에 대 한 자동 전달을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="1e620-109">자세한 내용은 [Control automatic external email 착신 전환의 Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e620-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="1e620-110">전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="1e620-110">Configure email forwarding</span></span>

 <span data-ttu-id="1e620-111">전자 메일 전달을 설정 하기 전에 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e620-111">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="1e620-112">전자 메일 전달을 설정한 후에는 *보낸* 사람 사서함으로 전송 된 **새** 전자 메일만 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span> 
    
- <span data-ttu-id="1e620-113">전자 메일을 전달 하려면  *보낸 사람*  계정에 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="1e620-114">사용자가 조직을 떠난 경우 전자 메일 전달을 설정 하는 경우 [사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="1e620-115">여러 사용자가 액세스할 수 있는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-115">This way several people can access it.</span></span> <span data-ttu-id="1e620-116">그러나 공유 사서함은 50GB를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-116">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="1e620-117">이러한 단계를 수행 하려면 Exchange 관리자 이거나 Microsoft 365의 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="1e620-118">자세한 내용은 [관리 역할에 대 한](../add-users/about-admin-roles.md)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e620-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1e620-119">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="1e620-120">전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-120">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="1e620-121">**메일** 탭에서 **전자 메일 전달 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-121">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="1e620-122">전자 메일 전달 페이지에서 **이 사서함에 보낸 모든 전자 메일** 전달을 선택 하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="1e620-123">이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="1e620-124">**변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-124">Select **Save changes**.</span></span>
    
    <span data-ttu-id="1e620-125">**여러 전자 메일 주소로 착신 전환** 하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="1e620-126">자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e620-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="1e620-127">또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="1e620-128">전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="1e620-129">이렇게 하면 전자 메일 전달이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-129">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="1e620-130">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="1e620-131">전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-131">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="1e620-132">**메일 설정을** 확장 하 고 **전자 메일 전달** 섹션에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="1e620-133">전자 메일 전달 페이지에서 켜기/ **끄기를 설정** 하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="1e620-134">이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="1e620-135">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-135">Select **Save**.</span></span>
    
    <span data-ttu-id="1e620-136">**여러 전자 메일 주소로 착신 전환** 하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="1e620-137">자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e620-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="1e620-138">또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="1e620-139">전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="1e620-140">이렇게 하면 전자 메일 전달이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-140">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="1e620-141">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="1e620-142">전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-142">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="1e620-143">**메일 설정을** 확장 하 고 **전자 메일 전달** 섹션에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="1e620-144">전자 메일 전달 페이지에서 켜기/ **끄기를 설정** 하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="1e620-145">이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="1e620-146">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-146">Select **Save**.</span></span>
    
    <span data-ttu-id="1e620-147">**여러 전자 메일 주소로 착신 전환** 하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="1e620-148">자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e620-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="1e620-149">또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="1e620-150">전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="1e620-151">이렇게 하면 전자 메일 전달이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e620-151">If you do, email forwarding will stop.</span></span> 


::: moniker-end 
