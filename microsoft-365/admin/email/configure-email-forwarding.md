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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 전자 메일 전달을 사용하면 조직 내부 또는 외부의 다른 사서함으로 Microsoft 365 전자 메일 메시지를 전달할 수 있습니다.
ms.openlocfilehash: dfea738f5d786b6e476dd02dc92fd0aef452d62f
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730141"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="c238d-103">전자 메일 전달 구성 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c238d-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="c238d-104">조직의 관리자는 사용자 사서함에 대한 전자 메일 전달을 설정해야 하는 회사 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="c238d-105">전자 메일 전달을 사용하면 사용자 사서함으로 전송된 전자 메일 메시지를 조직 내부 또는 외부의 다른 사용자의 사서함으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c238d-106">아웃바운드 스팸 필터 정책을 사용하여 외부 받는 사람에게 자동 전달을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="c238d-107">자세한 내용은 에서 자동 외부 전자 메일 전달 [제어를 Microsoft 365.](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)</span><span class="sxs-lookup"><span data-stu-id="c238d-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="c238d-108">전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="c238d-108">Configure email forwarding</span></span>

<span data-ttu-id="c238d-109">전자 메일 전달을 설정하기 전에 다음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="c238d-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="c238d-110">원격 도메인의 사용자에 자동으로 전달된 메시지를 보낼 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-110">Allow automatically forwarded messages to be sent to people on the remote domain.</span></span> <span data-ttu-id="c238d-111">자세한 [내용은 원격 도메인](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) 관리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-111">See [Manage remote domains](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) for details.</span></span>

- <span data-ttu-id="c238d-112">전자 메일 전달을 설정하면  사서함으로 전송된  새 전자 메일만 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="c238d-113">전자 메일 전달을 사용하려면 시작  *계정에*  라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="c238d-114">사용자가 조직을 떠났기 때문에 전자 메일 전달을 설정하는 경우 사서함을 공유 사서함으로 변환하는 [옵션도 있습니다.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="c238d-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="c238d-115">이렇게 하면 여러 사람이 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-115">This way several people can access it.</span></span> <span data-ttu-id="c238d-116">그러나 공유 사서함은 50GB를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="c238d-117">이러한 단계를 수행하려면 Exchange 관리자 또는 전역 관리자 Microsoft 365 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="c238d-118">자세한 내용은 관리자 역할 [정보를 참조하세요.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c238d-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="c238d-119">관리 센터에서 사용자 활성 **사용자** \> **[페이지로](https://go.microsoft.com/fwlink/p/?linkid=834822)** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="c238d-120">전자 메일을 전달할 사용자의 이름을 선택한 다음 속성 페이지를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="c238d-120">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="c238d-121">메일 **탭에서** 전자 메일 전달 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c238d-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="c238d-122">전자 메일 전달 페이지에서 이 사서함에 전송된 모든 전자 메일 전달을 선택하고 전달 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c238d-123">이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c238d-124">**변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-124">Select **Save changes**.</span></span>

    <span data-ttu-id="c238d-125">여러 전자 메일 **주소로** 전달하기 위해 사용자에게 주소로 전달할 규칙을 Outlook 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> 
    
    1.  <span data-ttu-id="c238d-126">Outlook **홈**  >  **규칙**  >   **>** **규칙 관리 & 열기**</span><span class="sxs-lookup"><span data-stu-id="c238d-126">Open **outlook** > **Home** >  **Rules** > Select **Manage Rules & Alerts**</span></span>
    1. <span data-ttu-id="c238d-127">새 **규칙** 목록의 맨 아래에 있는 받은 메시지에 규칙 적용을 선택하고  >   다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c238d-127">Select **New Rule** > **Select Apply rule on message I receive** located near bottom of list, then click **Next**.</span></span>
    1. <span data-ttu-id="c238d-128">메시지가 **표시될** 때 예를 클릭합니다. 이 규칙은 받은 모든 메시지에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-128">Click **Yes** when asked This rule will be applied to every message you receive.</span></span> 
    1. <span data-ttu-id="c238d-129">다음 목록에서 작업을 선택하여 사용자 또는 공용 그룹으로 **리디렉션하고** 추가 규칙 **처리를 중지합니다.**</span><span class="sxs-lookup"><span data-stu-id="c238d-129">On the next list select the actions **redirect it to people or public group** and **stop processing more rules**</span></span>
    1. <span data-ttu-id="c238d-130">창의 아래쪽에서  밑조가 있는 구 사람 또는 공용 그룹을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-130">Click the underlined phrase **people or public group** in the bottom part of window.</span></span>
    1. <span data-ttu-id="c238d-131">전자 메일을 **전달할 전자** 메일 주소를 To 필드에 입력한 다음 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c238d-131">Type the **email address** to forward mail to in the To field, then click **OK**.</span></span>
    1. <span data-ttu-id="c238d-132">완료 **선택**</span><span class="sxs-lookup"><span data-stu-id="c238d-132">Select **Finish**</span></span>
    

     <span data-ttu-id="c238d-133">또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹 을 만들고 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 안내하는 전달을 설정할 수 있습니다. [](add-user-or-contact-to-distribution-list.md)</span><span class="sxs-lookup"><span data-stu-id="c238d-133">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="c238d-134">전달할 전자 메일인 사용자의 계정을 삭제하거나 라이선스를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-134">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c238d-135">이렇게 하면 전자 메일 전달이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-135">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c238d-136">관리 센터에서 사용자 활성 **사용자** \> **[페이지로](https://go.microsoft.com/fwlink/p/?linkid=847686)** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-136">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="c238d-137">전자 메일을 전달할 사용자의 이름을 선택하여 속성 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-137">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="c238d-138">메일 **설정을 확장하고** 전자 메일 전달 **섹션에서** 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c238d-138">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c238d-139">전자 메일 전달 페이지에서 토글을 **으로** 설정하고 전달 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-139">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c238d-140">이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-140">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c238d-141">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-141">Select **Save**.</span></span>

   <span data-ttu-id="c238d-142">여러 전자 메일 **주소로** 전달하기 위해 사용자에게 주소로 전달할 규칙을 Outlook 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-142">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c238d-143">자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달을 참조합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="c238d-143">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="c238d-144">또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹 을 만들고 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 안내하는 전달을 설정할 수 있습니다. [](add-user-or-contact-to-distribution-list.md)</span><span class="sxs-lookup"><span data-stu-id="c238d-144">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="c238d-145">전달할 전자 메일인 사용자의 계정을 삭제하거나 라이선스를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-145">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c238d-146">이렇게 하면 전자 메일 전달이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-146">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c238d-147">관리 센터에서 사용자 활성 **사용자** \> **[페이지로](https://go.microsoft.com/fwlink/p/?linkid=850628)** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-147">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="c238d-148">전자 메일을 전달할 사용자의 이름을 선택하여 속성 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-148">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="c238d-149">메일 **설정을 확장하고** 전자 메일 전달 **섹션에서** 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c238d-149">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c238d-150">전자 메일 전달 페이지에서 토글을 **으로** 설정하고 전달 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-150">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c238d-151">이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-151">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c238d-152">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-152">Select **Save**.</span></span>

   <span data-ttu-id="c238d-153">여러 전자 메일 **주소로** 전달하기 위해 사용자에게 주소로 전달할 규칙을 Outlook 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-153">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c238d-154">자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달을 참조합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="c238d-154">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="c238d-155">또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹 을 만들고 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 안내하는 전달을 설정할 수 있습니다. [](add-user-or-contact-to-distribution-list.md)</span><span class="sxs-lookup"><span data-stu-id="c238d-155">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="c238d-156">전달할 전자 메일인 사용자의 계정을 삭제하거나 라이선스를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-156">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="c238d-157">이렇게 하면 전자 메일 전달이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c238d-157">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="c238d-158">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="c238d-158">Related content</span></span> 

<span data-ttu-id="c238d-159">[공유 사서함](../email/create-a-shared-mailbox.md) 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="c238d-159">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="c238d-160">[다른 주소에서 전자 메일](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) 보내기(문서)</span><span class="sxs-lookup"><span data-stu-id="c238d-160">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="c238d-161">[사용자 이름 및 전자 메일 주소](../add-users/change-a-user-name-and-email-address.md) 변경(문서)</span><span class="sxs-lookup"><span data-stu-id="c238d-161">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>
