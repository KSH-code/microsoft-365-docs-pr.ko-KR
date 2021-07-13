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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 공유 사서함을 만들고 전자 메일 전달 및 자동 응답과 같은 사용자에 대한 일부 설정을 구성합니다.
ms.openlocfilehash: e69d1bbde5784339f3973bf456eca1ded72840af
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393994"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="8f40d-103">공유 사서함 설정 구성</span><span class="sxs-lookup"><span data-stu-id="8f40d-103">Configure shared mailbox settings</span></span>

<span data-ttu-id="8f40d-104">공유 [사서함을](create-a-shared-mailbox.md)만든 후 전자 메일 전달 및 자동 응답과 같은 사서함 사용자에 대한 일부 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-104">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="8f40d-105">나중에 사서함 이름, 구성원 또는 구성원 권한과 같은 다른 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-105">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="8f40d-106">공유 사서함의 이름 또는 전자 메일 별칭을 변경하거나 기본 전자 메일 주소 변경</span><span class="sxs-lookup"><span data-stu-id="8f40d-106">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="8f40d-107">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-107">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="8f40d-108">편집할 공유 사서함을 선택한 다음  이름, 전자 메일, 전자 메일 별칭 옆에 있는 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-108">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="8f40d-109">새 이름을 입력하거나 다른 별칭을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-109">Enter a new name, or add another alias.</span></span> <span data-ttu-id="8f40d-110">기본 전자 메일 주소를 변경하려면 사서함에 전자 메일 별칭이 두 개 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-110">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="8f40d-111">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-111">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="8f40d-112">공유 사서함으로 전송되는 전자 메일 전달</span><span class="sxs-lookup"><span data-stu-id="8f40d-112">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="8f40d-113">공유 사서함으로 전송된 전자 메일을 전달하기 위해 공유 사서함에 라이선스를 할당할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-113">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="8f40d-114">메시지를 유효한 전자 메일 주소 또는 메일로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-114">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="8f40d-115">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-115">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="8f40d-116">편집할 공유 사서함을 선택한 다음 전자 메일 전달 **편집 을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-116">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="8f40d-117">토글을 **으로 설정하고** 메시지를 전달할 전자 메일 주소를 하나 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-117">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="8f40d-118">유효한 전자 메일 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-118">It can be any valid email address.</span></span> <span data-ttu-id="8f40d-119">여러 주소로 전달하려면 주소에 대한 메일 그룹을 만든 다음 이 상자에 그룹의 이름을 입력해야 합니다. [](/office365/admin/setup/create-distribution-lists)</span><span class="sxs-lookup"><span data-stu-id="8f40d-119">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="8f40d-120">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-120">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="8f40d-121">공유 사서함에서 자동 회신 보내기</span><span class="sxs-lookup"><span data-stu-id="8f40d-121">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="8f40d-122">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-122">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="8f40d-123">편집할 공유 사서함을 선택한 다음 자동 답장 편집 **을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-123">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="8f40d-124">토글을 **으로 설정하고** 조직 내부 또는 조직 외부의 사용자에 대한 회신을 보낼지 여부를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f40d-124">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="8f40d-p105">조직 내부 및 사용자에게 보내려는 회신을 입력합니다. 이미지는 추가할 수 없으며 텍스트만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-p105">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="8f40d-127">조직 *외부의* 사용자들에게도 회신을 보내고 싶은 경우, 확인란을 선택하고 회신을 받을 대상을 선택하고 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-127">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="8f40d-128">조직 외부 사용자에게만 보내는 방법은 없지만, 조직 내부 사용자에게만 보낼 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-128">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="8f40d-129">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-129">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="8f40d-130">모든 사람이 보낸 전자 메일(회신)을 볼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="8f40d-130">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="8f40d-p107">기본적으로 공유 사서함에서 보낸 메시지는 공유 사서함의 보낸 편지함 폴더에 저장되지 않습니다. 대신, 메시지를 보낸 사람의 보낸 편지함 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-p107">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="8f40d-133">모든 사용자가 보낸 전자 메일을 볼 수 있도록 허용하려면 관리 센터에서 공유 사서함 설정을 편집하고 보낸 항목 **편집 을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-133">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="8f40d-134">공유 사서함이 Microsoft 전자 메일에 액세스하는 데 사용할 수 있는 앱 선택</span><span class="sxs-lookup"><span data-stu-id="8f40d-134">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="8f40d-135">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-135">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="8f40d-136">편집할 공유 사서함을 선택한 다음 전자 메일 앱 편집 **을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-136">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="8f40d-137">구성원이 공유 사서함에 액세스하는 데 사용할 수 있도록 할 모든 앱에 대해 토글을 으로 설정하십시오. </span><span class="sxs-lookup"><span data-stu-id="8f40d-137">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="8f40d-138">사용하지 않는 모든  앱에 대해 토글을 끄기로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="8f40d-138">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="8f40d-139">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-139">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="8f40d-140">공유 사서함에 소송 보류</span><span class="sxs-lookup"><span data-stu-id="8f40d-140">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="8f40d-141">소송 보유에 대한 자세한 내용은 [Create a Litigation Hold를 참조합니다.](../../compliance/create-a-litigation-hold.md)</span><span class="sxs-lookup"><span data-stu-id="8f40d-141">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="8f40d-142">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="8f40d-143">편집할 공유 사서함을 선택한 다음 소송 보류 편집 **을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-143">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="8f40d-144">토글을 **으로 설정**</span><span class="sxs-lookup"><span data-stu-id="8f40d-144">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="8f40d-145">선택적으로 기간, s 보류에 대한 메모 및 추가 정보가 있는 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-145">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="8f40d-146">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-146">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="8f40d-147">구성원 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="8f40d-147">Add or remove members</span></span>

1. <span data-ttu-id="8f40d-148">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-148">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="8f40d-149">편집할 공유 사서함을 선택한 다음 구성원 편집 **을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-149">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="8f40d-150">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-150">Do one of the following:</span></span>
   - <span data-ttu-id="8f40d-151">구성원을 추가하려면 구성원 **추가를** 선택하고 추가할 구성원을 검색하거나 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-151">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="8f40d-152">구성원을 제거하려면 검색 상자를 사용하여 필요한 경우 구성원을 검색하고 구성원 이름 **옆의 X를** 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-152">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="8f40d-153">저장을 **다시** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-153">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="8f40d-154">구성원의 사용 권한 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="8f40d-154">Add or remove permissions of members</span></span>

1. <span data-ttu-id="8f40d-155">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-155">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="8f40d-156">편집할 공유 사서함을 선택한 다음 구성원 **권한** 사용자 \> **지정 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-156">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="8f40d-157">**구성원에** 대해 변경할 권한 옆의 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-157">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="8f40d-158">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-158">Do one of the following:</span></span>
   - <span data-ttu-id="8f40d-159">추가 구성원에게 해당 권한을 부여하려면 사용 권한 **추가를** 선택하고 추가할 구성원을 검색하거나 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-159">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="8f40d-160">구성원에서 사용 권한을 제거하려면 필요한 경우 검색 상자를 사용하여 구성원을 검색하고 구성원 이름 옆의 **X를** 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-160">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="8f40d-161">저장을 **다시** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-161">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="8f40d-162">전체 주소 목록에서 공유 사서함 표시 또는 숨기기</span><span class="sxs-lookup"><span data-stu-id="8f40d-162">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="8f40d-163">전체 주소 목록에 공유 사서함을 표시하지 않는 경우 사서함은 조직의 주소 목록에 나타나지 않지만 해당 사서함으로 전송된 전자 메일을 계속 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-163">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="8f40d-164">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">공유 사서함</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-164">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="8f40d-165">편집할 공유 사서함을 선택한 다음 전체 주소 목록 편집에서 **표시를** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f40d-165">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="8f40d-166">토글을 설정 **또는 해제로** **설정**</span><span class="sxs-lookup"><span data-stu-id="8f40d-166">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="8f40d-167">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-167">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="8f40d-168">주소 목록에서 공유 사서함을 숨기면 새 공유 사서함 구성원이 주소 목록에 공유 사서함이 다시 표시될 때까지 Outlook 프로필에 숨겨진 사서함을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f40d-168">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="8f40d-169">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="8f40d-169">Related content</span></span>

<span data-ttu-id="8f40d-170">[공유 사서함 정보](about-shared-mailboxes.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="8f40d-170">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="8f40d-171">[공유 사서함](create-a-shared-mailbox.md) 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="8f40d-171">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="8f40d-172">[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="8f40d-172">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="8f40d-173">[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="8f40d-173">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="8f40d-174">[공유 사서함 문제 해결](resolve-issues-with-shared-mailboxes.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="8f40d-174">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>