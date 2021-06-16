---
title: 공유 사서함에서 분리된 메시지 보기 및 릴리스
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 사용자는 사용 권한이 있는 공유 사서함으로 전송된 분리된 메시지를 보고 해당 메시지를 보는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4b958bb07660f4e0c93865300e190c713148a21d
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933058"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="098d6-103">공유 사서함에서 분리된 메시지 보기 및 릴리스</span><span class="sxs-lookup"><span data-stu-id="098d6-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="098d6-104">이 문서에서 설명하는 기능은 현재 미리 보기로 제공되어 있으며 모든 사람이 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="098d6-105">사용자는 [EOP에서](find-and-release-quarantined-messages-as-a-user.md)사용자로 검색 및 릴리스에 설명된 바와 같이 받는 사람 중 한 에 있는 분리된 메시지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="098d6-106">그러나 사용자가 **사서함의** 공유 사서함에 설명된 모든 권한 및 다른 사람으로 보내기 또는 대신 보내기 권한이 있는 공유 사서함은 [Exchange Online.](/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="098d6-106">But what about **shared mailboxes** where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="098d6-107">이전에는 사용자가 공유 사서함에 전송된 분리된 메시지를 관리할 수 있는 기능을 사용하려면 관리자가 공유 사서함에 대해 automapping을 사용하도록 설정(관리자가 다른 사서함에 대한 액세스 권한을 사용자에게 부여할 때 기본적으로 사용하도록 설정)을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="098d6-108">그러나 사용자가 액세스할 수 있는 사서함의 크기와 수에 따라 Outlook에서 사용자가 액세스할 수  있는 모든 사서함을 열려고 할 때 성능이 아날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="098d6-109">이러한 이유로 많은 관리자가 공유 [사서함에 대한 automapping을 제거하기로 선택했습니다.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="098d6-109">For this reason, many admins choose to [remove automapping for shared mailboxes](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="098d6-110">이제 사용자가 공유 사서함으로 전송된 고지된 메시지를 관리하기 위해 더 이상 automapping이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="098d6-111">작동하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-111">It just works.</span></span> <span data-ttu-id="098d6-112">공유 사서함에 전송된 서로 다른 두 가지 방법으로는 서로 다른 두 가지 방법으로 메시지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="098d6-113">관리자가 스팸 [](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)방지 정책에서 최종 사용자 스팸 알림을 사용하도록 설정한 경우 공유 사서함의 최종 사용자 스팸 알림에  액세스할 수 있는 모든 사용자는 알림의 검토 단추를 클릭하여 Microsoft 365 Defender 포털에서 검사로 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-113">If the admin has [enabled end-user spam notifications in anti-spam policies](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="098d6-114">이 방법을 사용하면 사용자가 공유 사서함으로 전송된 분리된 메시지만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="098d6-115">사용자는 이 컨텍스트에서 자체적으로 메시지를 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-115">Users can't manage their own quarantine messages in this context.</span></span>
- <span data-ttu-id="098d6-116">사용자는 Defender 포털의 Microsoft 365 [수 있습니다.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="098d6-116">The user can [go to the quarantine in the Microsoft 365 Defender portal](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="098d6-117">기본적으로 사용자에게 전송된 메시지만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="098d6-118">그러나 정렬 결과(메시지  ID 단추 기본적으로 메시지 **ID** 단추)를 받는 사람 전자 메일 주소로 변경하고 **공유** 사서함 전자 메일 주소를 입력한 다음 새로 고침을 클릭하여 공유 사서함으로 전송된 고지된 메시지를 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="098d6-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![받는 사람 전자 메일 주소로 quarantined 메시지를 정렬합니다.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="098d6-120">방법과 관계없이 사용자는 받는 사람 열을  사용하여 분리된 메시지에 대해 혼동을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="098d6-121">표시할 최대 열 수는 7개이기 때문에 사용자가 열 **수정을** 클릭하고 기존 열을 제거(예: 정책 **유형),** 받는 사람 을 선택한 다음 저장 **또는** 기본으로 저장을 **클릭해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="098d6-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![정책 유형 열을 제거하고 받는 사람 열을 분리합니다.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="098d6-123">주의 사항</span><span class="sxs-lookup"><span data-stu-id="098d6-123">Things to keep in mind</span></span>

- <span data-ttu-id="098d6-124">분리된 메시지에 대한 첫 번째 사용자가 공유 사서함을 사용하는 모든 사용자의 메시지의 결정에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="098d6-125">예를 들어 10명 사용자가 공유 사서함에 액세스하고 사용자가 메시지를 삭제하기로 결정하면 10명 모두에 대해 메시지가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="098d6-126">마찬가지로 사용자가 메시지를 해제하기로 결정한 경우 공유 사서함에 릴리스된 후 공유 사서함의 다른 모든 사용자가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="098d6-127">현재 공유  사서함으로 전송된 고지된  메시지에 대한 세부 정보 플라이아웃에서 보낸 사람 차단 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="098d6-128">공유 사서함에 대한 검지 작업과 관련하여 중첩된 보안 그룹을 사용하여 공유 사서함에 대한 액세스 권한을 부여하는 경우 중첩된 그룹의 수준은 두 개를 넘지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-128">Regarding quarantine operations for shared mailboxes, if you use nested security groups to grant access to a shared mailbox, we recommend no more than two levels of nested groups.</span></span> <span data-ttu-id="098d6-129">예를 들어 그룹 A는 그룹 C의 구성원인 그룹 B의 구성원입니다. 공유 사서함에 사용 권한을 할당하려면 그룹을 A에 추가한 다음 그룹 C를 공유 사서함에 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-129">For example, Group A is a member of Group B, which is a member of Group C. To assign permissions to a shared mailbox, don't add the user to Group A and then assign Group C to the shared mailbox.</span></span>  

- <span data-ttu-id="098d6-130">Exchange Online [PowerShell에서](/powershell/exchange/connect-to-exchange-online-powershell)공유 사서함에 대해 quarantined messages를 관리하려면 최종 사용자는 _RecipientAddress_ 매개 변수 값에 대해 공유 사서함 전자 메일 주소와 함께 [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) cmdlet을 사용하여 메시지를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-130">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="098d6-131">예시:</span><span class="sxs-lookup"><span data-stu-id="098d6-131">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="098d6-132">그런 다음 최종 사용자는 목록에서 분리된 메시지를 선택하여 보거나 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-132">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="098d6-133">이 예에서는 공유 사서함으로 전송된 모든 고지된 메시지를 보여 주며 목록의 첫 번째 메시지는 0, 두 번째 메시지는 1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="098d6-133">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="098d6-134">구문 및 매개 변수에 대한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="098d6-134">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="098d6-135">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="098d6-135">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="098d6-136">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="098d6-136">Get-QuarantineMessageHeader</span></span>](/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="098d6-137">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="098d6-137">Preview-QuarantineMessage</span></span>](/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="098d6-138">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="098d6-138">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
