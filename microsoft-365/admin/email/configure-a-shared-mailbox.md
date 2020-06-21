---
title: 공유 사서함 설정 구성
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
description: 공유 사서함을 만든 후에는 전자 메일 전달 및 자동 회신 같은 사용자에 대 한 일부 설정을 구성 해야 합니다. 나중에 사서함 이름이 나 구성원 등의 다른 설정을 변경할 수 있습니다.
ms.openlocfilehash: 3bde856f4db80192f5ed058a18c7942aa6a724b2
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739206"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="196e1-104">공유 사서함 설정 구성</span><span class="sxs-lookup"><span data-stu-id="196e1-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="196e1-105">[공유 사서함을 만든](create-a-shared-mailbox.md)후에는 전자 메일 전달 및 자동 회신과 같은 사서함 사용자에 대 한 일부 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="196e1-106">나중에 사서함 이름, 구성원 또는 구성원 권한과 같은 다른 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="196e1-107">공유 사서함의 이름 또는 전자 메일 별칭 변경 또는 기본 전자 메일 주소 변경</span><span class="sxs-lookup"><span data-stu-id="196e1-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="196e1-108">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="196e1-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="196e1-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="196e1-111">편집 하려는 공유 사서함을 선택 하 고 **이름, 전자 메일, 전자 메일 별칭**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="196e1-112">새 이름을 입력 하거나 다른 별칭을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="196e1-113">기본 전자 메일 주소를 변경 하려면 사서함에 전자 메일 별칭이 두 개 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="196e1-114">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="196e1-115">공유 사서함으로 전송되는 전자 메일 전달</span><span class="sxs-lookup"><span data-stu-id="196e1-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="196e1-116">전송 된 전자 메일을 전달 하기 위해 공유 사서함에 라이선스를 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="196e1-117">유효한 모든 전자 메일 주소 또는 메일 그룹으로 메시지를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="196e1-118">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="196e1-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="196e1-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="196e1-121">편집 하려는 공유 사서함을 선택 하 고 **전자 메일 전달** \> **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="196e1-122">켜기/ **끄기를 설정 하 고**메시지를 전달할 전자 메일 주소를 하나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="196e1-123">유효한 모든 전자 메일 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-123">It can be any valid email address.</span></span> <span data-ttu-id="196e1-124">여러 주소로 착신 전환 하려면 주소에 대 한 [메일 그룹을 만든](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) 다음이 상자에 그룹 이름을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="196e1-125">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="196e1-126">공유 사서함에서 자동 회신 보내기</span><span class="sxs-lookup"><span data-stu-id="196e1-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="196e1-127">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="196e1-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="196e1-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="196e1-130">편집 하려는 공유 사서함을 선택한 다음 **자동 회신** \> **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="196e1-131">켜기/ **끄기를 설정**으로 지정 하 고 조직 내부 또는 조직 외부의 사용자에 게 회신을 보낼지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="196e1-132">조직 내부 및 사용자에게 보내려는 회신을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="196e1-133">이미지는 추가할 수 없으며 텍스트만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="196e1-134">조직 외부의 사용자에 게 *도* 회신을 보내려면 회신을 받을 사용자의 확인란을 선택 하 고 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="196e1-135">조직 외부 사용자에게만 보내는 방법은 없지만, 조직 내부 사용자에게만 보낼 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="196e1-136">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="196e1-137">모든 사람이 보낸 전자 메일(회신)을 볼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="196e1-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="196e1-138">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox.</span><span class="sxs-lookup"><span data-stu-id="196e1-138">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox.</span></span> <span data-ttu-id="196e1-139">Instead, they are saved to the Sent Items folder of the person who sent the message.</span><span class="sxs-lookup"><span data-stu-id="196e1-139">Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="196e1-140">모든 사용자가 보낸 전자 메일을 볼 수 있도록 하려면 관리 센터에서 공유 사서함 설정을 편집 하 고 **보낸 항목** \> **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="196e1-141">공유 사서함이 Microsoft 전자 메일에 액세스 하는 데 사용할 수 있는 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="196e1-142">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="196e1-143"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="196e1-144"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="196e1-145">편집 하려는 공유 사서함을 선택 하 고 **전자 메일 앱** \> **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="196e1-146">구성원 들이 공유 사서함에 액세스 하는 데 사용할 수 있도록 하려는 모든 앱에 대해 켜기를 **On** 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="196e1-147">사용 하지 않을 앱에 대해 토글을 **해제** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="196e1-148">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="196e1-149">공유 사서함을 소송 보존 상태로 설정</span><span class="sxs-lookup"><span data-stu-id="196e1-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="196e1-150">소송 보존에 대 한 자세한 내용은 [소송 보존 만들기](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="196e1-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="196e1-151">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="196e1-152"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="196e1-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="196e1-154">편집 하려는 공유 사서함을 선택한 다음 **소송 보존** \> **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="196e1-155">토글을 **On**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="196e1-156">원하는 경우 보존 기간, s 메모 및 자세한 정보가 포함 된 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="196e1-157">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="196e1-158">구성원 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="196e1-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="196e1-159">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="196e1-160"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="196e1-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="196e1-162">편집 하려는 공유 사서함을 선택 하 고 **구성원** \> **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="196e1-163">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-163">Do one of the following:</span></span>
   - <span data-ttu-id="196e1-164">구성원을 추가 하려면 **구성원 추가**를 선택 하 고 추가할 구성원을 검색 하거나 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="196e1-165">구성원을 제거 하려면 검색 상자를 사용 하 여 필요한 경우 구성원을 검색 하 고 구성원의 이름 옆에 있는 **X** 를 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="196e1-166">**저장** 을 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="196e1-167">구성원의 사용 권한 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="196e1-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="196e1-168">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="196e1-169"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="196e1-170"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="196e1-171">편집 하려는 공유 사서함을 선택 하 고 **구성원** \> **사용자 지정 권한을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="196e1-172">구성원에 대해 변경할 사용 권한 옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="196e1-173">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-173">Do one of the following:</span></span>
   - <span data-ttu-id="196e1-174">추가 구성원에 게 해당 사용 권한을 부여 하려면 **사용 권한 추가**를 선택 하거나 추가할 구성원을 검색 하거나 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="196e1-175">구성원에서 사용 권한을 제거 하려면 필요한 경우 검색 상자를 사용 하 여 구성원을 검색 하 고 구성원 이름 옆에 있는 **X** 를 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="196e1-176">**저장** 을 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="196e1-177">전체 주소 목록에 공유 사서함 표시 또는 숨기기</span><span class="sxs-lookup"><span data-stu-id="196e1-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="196e1-178">전체 주소 목록에 공유 사서함을 표시 하지 않도록 선택 하면 해당 사서함이 조직의 주소 목록에 표시 되지 않지만 전송 된 전자 메일은 여전히 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="196e1-179">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="196e1-180"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="196e1-181"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **공유 사서함** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="196e1-182">편집 하려는 공유 사서함을 선택 하 고 **전체 주소 목록 편집에 표시** 를 선택 \> **Edit**합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="196e1-183">설정/ **해제**로 **전환** 합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="196e1-184">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="196e1-185">주소 목록에서 공유 사서함을 숨기면 새 공유 사서함 구성원이 해당 공유 사서함이 주소 목록에 다시 표시 될 때까지 Outlook 프로필에 숨겨진 사서함을 추가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="196e1-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="196e1-186">관련 문서</span><span class="sxs-lookup"><span data-stu-id="196e1-186">Related articles</span></span>

[<span data-ttu-id="196e1-187">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="196e1-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="196e1-188">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="196e1-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="196e1-189">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="196e1-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="196e1-190">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="196e1-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="196e1-191">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="196e1-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
