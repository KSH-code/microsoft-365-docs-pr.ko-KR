---
title: 전자 메일 전달 구성
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.openlocfilehash: f6c177ba37cf2b8ce3966732adbe8428d9b6179e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780256"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="c1f00-103">전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="c1f00-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c1f00-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-104">The admin center is changing.</span></span> <span data-ttu-id="c1f00-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1f00-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="c1f00-106">조직의 관리자는 사용자 사서함에 대 한 전자 메일 전달을 설정 하기 위한 회사 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="c1f00-107">전자 메일 전달을 사용 하면 사용자의 사서함에 전송 된 전자 메일 메시지를 조직의 내부 또는 외부에 있는 다른 사용자의 사서함으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="c1f00-108">전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="c1f00-108">Configure email forwarding</span></span>

 <span data-ttu-id="c1f00-109">전자 메일 전달을 설정 하기 전에 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1f00-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="c1f00-110">전자 메일 전달을 설정한 후에는 *보낸* 사람 사서함으로 전송 되는 **새** 전자 메일만 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="c1f00-111">전자 메일을 전달 하려면 *보낸 사람* 계정에 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="c1f00-112">사용자가 조직을 떠난 경우 전자 메일 전달을 설정 하는 경우 [사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="c1f00-113">여러 사용자가 액세스할 수 있는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-113">This way several people can access it.</span></span> <span data-ttu-id="c1f00-114">그러나 공유 사서함은 50GB를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="c1f00-115">이러한 단계를 수행 하려면 Exchange 관리자 이거나 Microsoft 365의 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="c1f00-116">자세한 내용은 [관리 역할에 대 한](../add-users/about-admin-roles.md)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1f00-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c1f00-117">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-117">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="c1f00-118">전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-118">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="c1f00-119">**메일** 탭에서 **전자 메일 전달 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-119">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="c1f00-120">전자 메일 전달 페이지에서 **이 사서함에 보낸 모든 전자 메일**전달을 선택 하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c1f00-121">이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c1f00-122">**변경 내용 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-122">Select **Save changes**.</span></span>
    
    <span data-ttu-id="c1f00-123">**여러 전자 메일 주소로 착신 전환**하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c1f00-124">자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1f00-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="c1f00-125">또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="c1f00-126">전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c1f00-127">이렇게 하면 전자 메일 전달이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-127">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="c1f00-128">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="c1f00-129">전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-129">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="c1f00-130">**메일 설정을**확장 하 고 **전자 메일 전달** 섹션에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c1f00-131">전자 메일 전달 페이지에서 켜기/ **끄기를 설정**하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c1f00-132">이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c1f00-133">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-133">Select **Save**.</span></span>
    
    <span data-ttu-id="c1f00-134">**여러 전자 메일 주소로 착신 전환**하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c1f00-135">자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1f00-135">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="c1f00-136">또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="c1f00-137">전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c1f00-138">이렇게 하면 전자 메일 전달이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-138">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="c1f00-139">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="c1f00-140">전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-140">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="c1f00-141">**메일 설정을**확장 하 고 **전자 메일 전달** 섹션에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c1f00-142">전자 메일 전달 페이지에서 켜기/ **끄기를 설정**하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c1f00-143">이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c1f00-144">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-144">Select **Save**.</span></span>
    
    <span data-ttu-id="c1f00-145">**여러 전자 메일 주소로 착신 전환**하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c1f00-146">자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1f00-146">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="c1f00-147">또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="c1f00-148">전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c1f00-149">이렇게 하면 전자 메일 전달이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f00-149">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
