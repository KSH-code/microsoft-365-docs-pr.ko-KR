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
description: Office365를 사용하여 하나 이상의 전자 메일 계정으로 전자 메일 전달을 설정할 수 있습니다.
ms.openlocfilehash: 1168b549443de218339b1b8dcb32e57da175a2aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926645"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="5b2ed-103">Microsoft 365에서 전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="5b2ed-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5b2ed-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-104">The admin center is changing.</span></span> <span data-ttu-id="5b2ed-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="5b2ed-106">조직의 관리자는 사용자 사서함에 대한 전자 메일 전달을 설정하기 위한 회사 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="5b2ed-107">전자 메일 전달을 사용하면 사용자의 사서함으로 전송된 전자 메일 메시지를 조직 내부 또는 외부의 다른 사용자의 사서함으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b2ed-108">아웃바운드 스팸 필터 정책을 사용하여 외부 받는 사람에게 자동 전달을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="5b2ed-109">자세한 내용은 [Microsoft 365에서](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)자동 외부 전자 메일 전달 제어를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="5b2ed-110">전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="5b2ed-110">Configure email forwarding</span></span>

<span data-ttu-id="5b2ed-111">전자 메일 전달을 설정하기 전에 다음을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="5b2ed-112">전자 메일 전달을 설정하면  사서함에서 보낸  새 전자 메일만 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="5b2ed-113">전자 메일 전달을 위해서는 계정에  *라이선스가*  필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="5b2ed-114">사용자가 조직을 떠났기 때문에 전자 메일 전달을 설정하는 경우 사서함을 공유 사서함으로 변환하는 [옵션도 있습니다.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="5b2ed-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="5b2ed-115">이렇게 하면 여러 사람이 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-115">This way several people can access it.</span></span> <span data-ttu-id="5b2ed-116">그러나 공유 사서함은 50GB를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="5b2ed-117">다음 단계를 수행하려면 Microsoft 365의 Exchange 관리자 또는 전역 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="5b2ed-118">자세한 내용은 관리자 역할에 [대한 항목을 참조하세요.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5b2ed-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5b2ed-119">관리 센터에서 사용자  \> **[활성 사용자 페이지로](https://go.microsoft.com/fwlink/p/?linkid=834822)** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="5b2ed-120">속성 페이지를 열기 위해 전자 메일을 전달할 사용자의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="5b2ed-121">메일 **탭에서** 전자 메일 전달 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5b2ed-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="5b2ed-122">전자 메일 전달 페이지에서 이 사서함으로 전송된 모든 전자 메일 전달을 선택하고 **전달** 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="5b2ed-123">이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="5b2ed-124">**변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-124">Select **Save changes**.</span></span>

    <span data-ttu-id="5b2ed-125">**여러 전자 메일 주소로 전달하기** 위해 사용자에게 Outlook에서 주소로 전달할 규칙을 설정하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="5b2ed-126">자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="5b2ed-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="5b2ed-127">또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹을 만들고 [](add-user-or-contact-to-distribution-list.md)해당 그룹에 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 설정하여 전달을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="5b2ed-128">전달할 전자 메일의 사용자 계정을 삭제하거나 라이선스를 제거하지 않습니다!</span><span class="sxs-lookup"><span data-stu-id="5b2ed-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="5b2ed-129">이렇게 하면 전자 메일 전달이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5b2ed-130">관리 센터에서 사용자  \> **[활성 사용자 페이지로](https://go.microsoft.com/fwlink/p/?linkid=847686)** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="5b2ed-131">속성 페이지를 열기 위해 전자 메일을 전달할 사용자의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="5b2ed-132">메일 **설정을 확장한** 다음 전자 메일 전달 **섹션에서** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5b2ed-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="5b2ed-133">전자 메일 전달 페이지에서 토글을 **설정하고** 전달 주소를 입력한 다음 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="5b2ed-134">이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="5b2ed-135">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-135">Select **Save**.</span></span>

   <span data-ttu-id="5b2ed-136">**여러 전자 메일 주소로 전달하기** 위해 사용자에게 Outlook에서 주소로 전달할 규칙을 설정하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="5b2ed-137">자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="5b2ed-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="5b2ed-138">또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹을 만들고 [](add-user-or-contact-to-distribution-list.md)해당 그룹에 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 설정하여 전달을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="5b2ed-139">전달할 전자 메일의 사용자 계정을 삭제하거나 라이선스를 제거하지 않습니다!</span><span class="sxs-lookup"><span data-stu-id="5b2ed-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="5b2ed-140">이렇게 하면 전자 메일 전달이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5b2ed-141">관리 센터에서 사용자  \> **[활성 사용자 페이지로](https://go.microsoft.com/fwlink/p/?linkid=850628)** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="5b2ed-142">속성 페이지를 열기 위해 전자 메일을 전달할 사용자의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="5b2ed-143">메일 **설정을 확장한** 다음 전자 메일 전달 **섹션에서** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5b2ed-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="5b2ed-144">전자 메일 전달 페이지에서 토글을 **설정하고** 전달 주소를 입력한 다음 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="5b2ed-145">이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="5b2ed-146">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-146">Select **Save**.</span></span>

   <span data-ttu-id="5b2ed-147">**여러 전자 메일 주소로 전달하기** 위해 사용자에게 Outlook에서 주소로 전달할 규칙을 설정하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="5b2ed-148">자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="5b2ed-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="5b2ed-149">또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹을 만들고 [](add-user-or-contact-to-distribution-list.md)해당 그룹에 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 설정하여 전달을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="5b2ed-150">전달할 전자 메일의 사용자 계정을 삭제하거나 라이선스를 제거하지 않습니다!</span><span class="sxs-lookup"><span data-stu-id="5b2ed-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="5b2ed-151">이렇게 하면 전자 메일 전달이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b2ed-151">If you do, email forwarding will stop.</span></span>

::: moniker-end
