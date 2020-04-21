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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365을 사용 하 여 하나 이상의 전자 메일 계정으로 전자 메일을 전달 하도록 설정 합니다.
ms.openlocfilehash: 5807649fa43d094fd8f05cf63e2905d7cdb6dd7d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628918"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="b32dd-103">전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="b32dd-103">Configure email forwarding</span></span>
  
<span data-ttu-id="b32dd-104">조직의 관리자는 사용자 사서함에 대 한 전자 메일 전달을 설정 하기 위한 회사 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="b32dd-105">전자 메일 전달을 사용 하면 사용자의 사서함에 전송 된 전자 메일 메시지를 조직의 내부 또는 외부에 있는 다른 사용자의 사서함으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="b32dd-106">전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="b32dd-106">Configure email forwarding</span></span>

 <span data-ttu-id="b32dd-107">전자 메일 전달을 설정 하기 전에 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="b32dd-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="b32dd-108">전자 메일 전달을 설정한 후에는 *보낸* 사람 사서함으로 전송 되는 **새** 전자 메일만 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="b32dd-109">전자 메일을 전달 하려면 *보낸 사람* 계정에 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="b32dd-110">사용자가 조직을 떠난 경우 전자 메일 전달을 설정 하는 경우 [사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="b32dd-111">여러 사용자가 액세스할 수 있는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-111">This way several people can access it.</span></span> <span data-ttu-id="b32dd-112">그러나 공유 사서함은 50GB를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="b32dd-113">이러한 단계를 수행 하려면 Exchange 관리자 이거나 Microsoft 365의 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-113">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="b32dd-114">자세한 내용은 [관리 역할에 대 한](../add-users/about-admin-roles.md)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b32dd-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b32dd-115">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="b32dd-116">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="b32dd-117">전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="b32dd-118">**메일** 탭에서 **전자 메일 전달 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="b32dd-119">전자 메일 전달 페이지에서 **이 사서함에 보낸 모든 전자 메일**전달을 선택 하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b32dd-120">이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b32dd-121">**변경 내용 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="b32dd-122">**여러 전자 메일 주소로 착신 전환**하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-122">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b32dd-123">자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b32dd-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="b32dd-124">또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="b32dd-125">전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b32dd-126">이렇게 하면 전자 메일 전달이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="b32dd-127">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="b32dd-128">전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="b32dd-129">**메일 설정을**확장 하 고 **전자 메일 전달** 섹션에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="b32dd-130">전자 메일 전달 페이지에서 켜기/ **끄기를 설정**하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b32dd-131">이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b32dd-132">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-132">Select **Save**.</span></span>
    
    <span data-ttu-id="b32dd-133">**여러 전자 메일 주소로 착신 전환**하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b32dd-134">자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b32dd-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="b32dd-135">또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="b32dd-136">전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b32dd-137">이렇게 하면 전자 메일 전달이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b32dd-138">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="b32dd-139">전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="b32dd-140">**메일 설정을**확장 하 고 **전자 메일 전달** 섹션에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="b32dd-141">전자 메일 전달 페이지에서 켜기/ **끄기를 설정**하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b32dd-142">이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b32dd-143">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-143">Select **Save**.</span></span>
    
    <span data-ttu-id="b32dd-144">**여러 전자 메일 주소로 착신 전환**하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b32dd-145">자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b32dd-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="b32dd-146">또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="b32dd-147">전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b32dd-148">이렇게 하면 전자 메일 전달이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b32dd-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
