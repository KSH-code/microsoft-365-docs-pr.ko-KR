---
title: 공유 사서함 설정 구성
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
description: 공유 사서함을 만든 후 전자 메일 전달 및 자동 응답과 같은 사용자에 대한 일부 설정을 구성할 수 있습니다. 나중에 사서함 이름 또는 구성원과 같은 다른 설정을 변경할 수 있습니다.
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926609"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="5d3d0-104">공유 사서함 설정 구성</span><span class="sxs-lookup"><span data-stu-id="5d3d0-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="5d3d0-105">공유 [사서함을](create-a-shared-mailbox.md)만든 후 전자 메일 전달 및 자동 응답과 같은 사서함 사용자에 대한 일부 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="5d3d0-106">나중에 사서함 이름, 구성원 또는 구성원 권한과 같은 다른 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="5d3d0-107">공유 사서함의 이름 또는 전자 메일 별칭 변경 또는 기본 전자 메일 주소 변경</span><span class="sxs-lookup"><span data-stu-id="5d3d0-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5d3d0-108">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="5d3d0-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5d3d0-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="5d3d0-111">편집할 공유 사서함을 선택한 다음  이름, 전자 메일, 전자 메일 별칭 옆에 있는 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="5d3d0-112">새 이름을 입력하거나 다른 별칭을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="5d3d0-113">기본 전자 메일 주소를 변경하려면 사서함에 전자 메일 별칭이 두 개 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="5d3d0-114">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="5d3d0-115">공유 사서함으로 전송되는 전자 메일 전달</span><span class="sxs-lookup"><span data-stu-id="5d3d0-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="5d3d0-116">공유 사서함으로 전송된 전자 메일을 전달하기 위해 공유 사서함에 라이선스를 할당할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="5d3d0-117">메시지를 유효한 전자 메일 주소 또는 메일로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5d3d0-118">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="5d3d0-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5d3d0-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="5d3d0-121">편집할 공유 사서함을 선택한 다음 전자 메일 전달 **편집을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="5d3d0-122">토글을 **On으로 설정하고** 전자 메일 주소를 하나 입력하여 메시지를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="5d3d0-123">유효한 전자 메일 주소가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-123">It can be any valid email address.</span></span> <span data-ttu-id="5d3d0-124">여러 주소로 전달하려면 주소에 대한 메일 그룹을 만든 다음 이 상자에 그룹의 이름을 입력해야 합니다. [](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists)</span><span class="sxs-lookup"><span data-stu-id="5d3d0-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="5d3d0-125">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="5d3d0-126">공유 사서함에서 자동 회신 보내기</span><span class="sxs-lookup"><span data-stu-id="5d3d0-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5d3d0-127">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="5d3d0-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5d3d0-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="5d3d0-130">편집할 공유 사서함을 선택한 다음 자동 답장 **편집을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="5d3d0-131">토글을 **설정하고** 조직 내부 또는 조직 외부의 사용자에게 회신을 보낼지 여부를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="5d3d0-132">조직 내부 및 사용자에게 보내려는 회신을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="5d3d0-133">이미지는 추가할 수 없으며 텍스트만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="5d3d0-134">조직 외부의  다른 사용자도 회신을 보내고 싶은 경우 회신을 받을 확인란을 선택하고 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="5d3d0-135">조직 외부 사용자에게만 보내는 방법은 없지만, 조직 내부 사용자에게만 보낼 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="5d3d0-136">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="5d3d0-137">모든 사람이 보낸 전자 메일(회신)을 볼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="5d3d0-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="5d3d0-p108">기본적으로 공유 사서함에서 보낸 메시지는 공유 사서함의 보낸 편지함 폴더에 저장되지 않습니다. 대신, 메시지를 보낸 사람의 보낸 편지함 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="5d3d0-140">모든 사용자가 보낸 전자 메일을 볼 수 있도록 허용하려면 관리 센터에서 공유 사서함 설정을 편집하고 보낸 사람 항목 **편집을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="5d3d0-141">공유 사서함이 Microsoft 전자 메일에 액세스하는 데 사용할 수 있는 앱 선택</span><span class="sxs-lookup"><span data-stu-id="5d3d0-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5d3d0-142">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="5d3d0-143"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5d3d0-144"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="5d3d0-145">편집할 공유 사서함을 선택한 다음 전자 메일 앱 **편집을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="5d3d0-146">구성원이 공유 사서함에 액세스하는 데 사용할 수 있도록 할 모든 앱에 대해 토글을 On으로 설정 </span><span class="sxs-lookup"><span data-stu-id="5d3d0-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="5d3d0-147">사용하지 않는 앱에  대해 토글을 해제로 설정</span><span class="sxs-lookup"><span data-stu-id="5d3d0-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="5d3d0-148">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="5d3d0-149">공유 사서함을 소송 보유로 설정</span><span class="sxs-lookup"><span data-stu-id="5d3d0-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="5d3d0-150">소송 보유에 대한 자세한 내용은 소송 보유 만들기를 [참조합니다.](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)</span><span class="sxs-lookup"><span data-stu-id="5d3d0-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5d3d0-151">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="5d3d0-152"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5d3d0-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="5d3d0-154">편집할 공유 사서함을 선택한 다음  소송 보유 편집을 \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="5d3d0-155">토글을 **On으로 설정**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="5d3d0-156">필요한 경우 기간, 보류에 대한 참고 사항 및 추가 정보가 있는 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="5d3d0-157">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="5d3d0-158">구성원 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="5d3d0-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5d3d0-159">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="5d3d0-160"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5d3d0-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="5d3d0-162">편집할 공유 사서함을 선택한 다음 **구성원 편집을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="5d3d0-163">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-163">Do one of the following:</span></span>
   - <span data-ttu-id="5d3d0-164">구성원을 추가하려면 구성원 **추가를** 선택하고 추가할 구성원을 검색하거나 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="5d3d0-165">구성원을 제거하려면 검색 상자를 사용하여 필요한 경우 구성원을 검색하고 구성원 이름 **옆의 X를** 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="5d3d0-166">다시 **저장을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="5d3d0-167">구성원의 사용 권한 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="5d3d0-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5d3d0-168">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="5d3d0-169"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5d3d0-170"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="5d3d0-171">편집할 공유 사서함을 선택한 다음 **구성원** 사용자 지정 \> **권한을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="5d3d0-172">구성원에 **대해** 변경할 사용 권한 옆의 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="5d3d0-173">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-173">Do one of the following:</span></span>
   - <span data-ttu-id="5d3d0-174">추가 구성원에게 해당 권한을 부여하려면 사용 권한 **추가를** 선택하고 추가할 구성원을 검색하거나 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="5d3d0-175">구성원에서 사용 권한을 제거하려면 검색 상자를 사용하여 필요한 경우 구성원을 검색하고 구성원 이름 옆의 **X를** 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="5d3d0-176">다시 **저장을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="5d3d0-177">전체 주소 목록에서 공유 사서함 표시 또는 숨기기</span><span class="sxs-lookup"><span data-stu-id="5d3d0-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="5d3d0-178">전체 주소 목록에 공유 사서함을 표시하지 않는 경우 사서함이 조직의 주소 목록에 나타나지 않지만 사서함으로 전송된 전자 메일은 계속 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5d3d0-179">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="5d3d0-180"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5d3d0-181"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="5d3d0-182">편집할 공유 사서함을 선택한 다음 전체 주소 목록 편집에서 **표시를** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3d0-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="5d3d0-183">토글을 설정 **또는 해제합니다.** </span><span class="sxs-lookup"><span data-stu-id="5d3d0-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="5d3d0-184">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="5d3d0-185">주소 목록에서 공유 사서함을 숨기면 새 공유 사서함 구성원이 주소 목록에 공유 사서함이 다시 표시될 때까지 숨겨진 사서함을 Outlook 프로필에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3d0-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="5d3d0-186">관련 문서</span><span class="sxs-lookup"><span data-stu-id="5d3d0-186">Related articles</span></span>

[<span data-ttu-id="5d3d0-187">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="5d3d0-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="5d3d0-188">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="5d3d0-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="5d3d0-189">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="5d3d0-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="5d3d0-190">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="5d3d0-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="5d3d0-191">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5d3d0-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
