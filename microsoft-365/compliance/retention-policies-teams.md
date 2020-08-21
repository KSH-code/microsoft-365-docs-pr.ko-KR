---
title: Teams의 보존에 대해 알아보기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft Teams에 적용되는 보존 정책에 대해 자세히 알아보기
ms.openlocfilehash: 3dcc0e3ea94d002f603b44b777d7666a65b4a725
ms.sourcegitcommit: c692bdc186fb29499816e8bb2addcddef34d23d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818323"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="cd906-103">Microsoft Teams의 보존에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="cd906-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="cd906-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="cd906-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="cd906-105">이 문서의 정보는 Microsoft Teams와 관련된 정보를 포함하므로 [보존에 대해 알아보기](retention.md)를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-105">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="cd906-106">보존이 Microsoft Teams에 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="cd906-106">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="cd906-107">보존 정책을 사용하여 Teams에서 채팅 및 채널 메시지를 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-107">You can use a retention policy to retain chats and channel messages in Teams.</span></span> <span data-ttu-id="cd906-108">Teams 채팅은 채팅에 포함된 각 사용자의 사서함에 있는 숨겨진 폴더에 저장되고, Teams 채널 메시지는 Teams의 그룹 사서함에 있는 유사한 숨겨진 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-108">Teams chats are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span>

<span data-ttu-id="cd906-109">Teams에서 역시 이 데이터를 저장하는 Azure 기반 채팅 서비스를 사용하고, 기본적으로 이 서비스에서는 데이터를 무제한적으로 저장한다는 사실을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-109">It's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data indefinitely.</span></span> <span data-ttu-id="cd906-110">이러한 이유로 Teams 위치를 사용하여 Teams 데이터를 보존 및 삭제하는 보존 정책을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-110">For this reason, we recommend that you create a retention policy that uses the Teams locations to retain and delete this Teams data.</span></span> <span data-ttu-id="cd906-111">이 보존 정책은 Exchange 사서함 및 기본 Azure 기반 채팅 서비스 모두에서 데이터를 영구적으로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-111">This retention policy can permanently delete data from both the Exchange mailboxes and the underlying Azure-powered chat service.</span></span> <span data-ttu-id="cd906-112">자세한 내용은 [Microsoft Teams의 보안 및 규정 준수](https://go.microsoft.com/fwlink/?linkid=871258) 및 특히 [정보 보호 아키텍처](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd906-112">For more information, see [Security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) and specifically, the [Information Protection Architecture](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="cd906-113">Teams 채팅 및 채널 메시지는 사용자 또는 그룹 사서함에 대해 구성된 보존 정책의 영향을받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-113">Teams chats and channel messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="cd906-114">Teams 채팅 및 채널 메시지가 Exchange에 저장되어 있어도이 Teams 데이터는 **Teams 채널 메시지** 및 **Teams 채팅** 위치에 대해 구성된 보존 정책에 의해서만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-114">Even though Teams chats and channel messages are stored in Exchange, this Teams data is included only by a retention policy that's configured for the **Teams channel messages** and **Teams chats** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="cd906-115">Teams 데이터를 보존하는 활성 보존 정책에 사용자가 포함되어 있고 Teams 데이터를 보존하기 위해 이 정책에 포함된 사용자의 사서함을 삭제하면 사서함이 [비활성 사서함](inactive-mailboxes-in-office-365.md)로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-115">If a user is included in an active retention policy that retains Teams data and you a delete a mailbox of a user who is included in this policy, to retain the Teams data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="cd906-116">사용자에 대한 이 Teams 데이터를 유지할 필요가 없는 경우 사서함을 삭제하기 전에 사용자 계정을 보존 정책에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-116">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="cd906-117">채팅 및 채널 메시지에 대한 보존 정책을 구성한 후에는, Exchange 서비스의 타이머 작업이 해당 Teams 메시지가 저장된 숨겨진 폴더의 항목을 주기적으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-117">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="cd906-118">타이머 작업의 실행은 7일까지 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-118">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="cd906-119">이러한 항목의 보존 기간이 만료되면, 해당 항목은 영구적으로 삭제되기 전에 모든 사용자 또는 그룹 사서함에서 "일시 삭제됨" 항목을 저장하는 또 다른 숨겨진 폴더인 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-119">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="cd906-120">채팅 및 채널 메시지에 대해 보존 정책을 구성한 후 콘텐츠가 취하는 경로는 보존 정책이 보존 및 삭제, 보존만 또는 삭제만 가능한지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-120">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="cd906-121">보존 정책이 보존 및 삭제하는 경우:</span><span class="sxs-lookup"><span data-stu-id="cd906-121">When the retention policy is to retain and then delete:</span></span>

![Teams 채팅 및 채널 메시지의 보존 흐름 다이어그램](../media/teamsretentionlifecycle.png)

<span data-ttu-id="cd906-123">다이어그램의 두 경로:</span><span class="sxs-lookup"><span data-stu-id="cd906-123">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="cd906-124">**보존 기간 동안 사용자가 채팅 또는 채널 메시지를 편집하거나** 삭제하는 경우에는 원본 메시지가 즉시 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-124">**If a chat or channel message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="cd906-125">이 메시지는 보존 기간이 만료 될 때까지 저장된 다음 24 시간 내에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-125">The message is stored there until the retention period expires and then the message is permanently deleted within 24 hours.</span></span>

2. <span data-ttu-id="cd906-126">**채팅 또는 채널 메시지가 삭제되지 않는 경우**, 편집 후 현재 메시지에 대한 메시지는 보존 기간이 만료 된 후 SubstrateHolds 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-126">**If a chat or channel message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="cd906-127">이 작업은 만료 날짜로부터 최대 7일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-127">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="cd906-128">메시지가 SubstrateHolds 폴더에 있으면 24시간 내에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-128">When the message is in the SubstrateHolds folder, it is then permanently deleted within 24 hours.</span></span> 

> [!NOTE]
> <span data-ttu-id="cd906-129">SubstrateHolds 폴더의 메시지는 eDiscovery 도구에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-129">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="cd906-130">메시지가 영구적으로 삭제 될 때까지 (SubstrateHolds 폴더에서)는 eDiscovery 도구에 의해 검색가능한 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-130">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="cd906-131">보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-131">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="cd906-132">보유 전용 보존 정책의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="cd906-132">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="cd906-133">**채팅 또는 채널 메시지를 편집하거나 삭제하는 경우**: 원본 메시지의 복사본은 SubstrateHolds 폴더에 즉시 만들어지고 보존 기간이 만료될 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-133">**If a chat or channel message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="cd906-134">그런 다음 24시간 이내에 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-134">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="cd906-135">**항목이 수정되거나 삭제되지 않거나** 보존 기간 중에 편집 후 현재 메시지에 대한 경우: 보존 기간 전후에 아무런 변화가 없습니다. 메시지는 원래 위치에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-135">**If the item is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="cd906-136">삭제 전용 보존 정책의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="cd906-136">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="cd906-137">보존 기간 동안 **메시지가 삭제되지 않은 경우**: 보존 기간이 끝나면 메시지가 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-137">**If the message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="cd906-138">이 작업은 만료 날짜로부터 최대 7일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-138">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="cd906-139">그런 다음 24시간 이내에 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-139">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="cd906-140">**해당 기간 동안 사용자가 항목을 삭제하는 경우** 그 항목이 24시간 이내에 영구적으로 삭제되는 SubstrateHolds 폴더로 즉시 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-140">**If the item is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is permanently deleted within 24 hours.</span></span>


## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="cd906-141">비즈니스용 Skype 및 팀 상호 운용 채팅</span><span class="sxs-lookup"><span data-stu-id="cd906-141">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="cd906-142">비즈니스용 Skype 채팅이 Teams로 이동하는 경우 해당 채팅은 Teams 채팅 스레드에서 메시지가 되고 해당 사서함에 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-142">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="cd906-143">Teams 보존 정책은 이러한 메시지를 Teams 스레드에서 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-143">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="cd906-144">그러나 비즈니스용 Skype 및 비즈니스용 Skype 클라이언트 쪽에서 대화 기록을 사용하도록 설정한 경우 기록이 사서함에 저장되는 경우 해당 Teams의 보존 정책이 해당 채팅 데이터를 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-144">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span> <span data-ttu-id="cd906-145">이 콘텐츠의 경우 비즈니스용 Skype에 대해 구성된 보존 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-145">For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="cd906-146">모임 및 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="cd906-146">Meetings and external users</span></span>

<span data-ttu-id="cd906-147">채널 모임 메시지는 채널 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채널 메시지** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="cd906-147">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="cd906-148">즉석 모임 메시지는 그룹 채팅 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채팅** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="cd906-148">Impromptu meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="cd906-149">조직에서 호스팅하는 모임에 외부 사용자가 포함된 경우:</span><span class="sxs-lookup"><span data-stu-id="cd906-149">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="cd906-150">외부 사용자가 테넌트에서 게스트 계정을 사용하여 참여하는 경우 이 사용자에게는 조직의 Teams 보존 정책을 적용할 수 있는 섀도 사서함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-150">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="cd906-151">모임의 모든 메시지는 사용자의 사서함과 섀도 사서함에 모두 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-151">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="cd906-152">외부 사용자가 다른 Microsoft 365 조직의 계정을 사용하여 참여하는 경우 보존 정책은 이 사용자의 메시지가 다른 테넌트의 해당 사용자의 사서함에 저장되어 있기 때문에 해당 사용자의 메시지를 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-152">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant.</span></span> <span data-ttu-id="cd906-153">그러나 동일한 모임의 경우 보존 정책이 사용자의 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-153">For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="cd906-154">사용자가 조직을 떠나는 경우</span><span class="sxs-lookup"><span data-stu-id="cd906-154">When a user leaves the organization</span></span> 

<span data-ttu-id="cd906-155">사용자가 조직을 떠나 Microsoft 365 계정이 삭제된 경우 보존이 적용되는 해당 사용자의 채팅 메시지는 비활성 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-155">If a user leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="cd906-156">채팅 메시지는 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-156">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="cd906-157">자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd906-157">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="cd906-158">사용자가 Teams에 저장한 파일이 있다면 SharePoint 및 OneDrive의 경우 [해당 섹션](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd906-158">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="cd906-159">제한 사항</span><span class="sxs-lookup"><span data-stu-id="cd906-159">Limitations</span></span>

<span data-ttu-id="cd906-160">Microsoft는 Teams에서 보존 기능을 최적화하기 위해 지속적으로 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-160">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="cd906-161">그 동안 Teams 채널 메시지와 채팅에 대한 보존을 사용할 때는 다음 몇 가지 제한 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-161">In the meantime, here are a few limitations to be aware of when you use retention for Teams channel messages and chats:</span></span>

- <span data-ttu-id="cd906-162">**Teams는 조직 전체 정책에 포함되지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="cd906-162">**Teams isn't included in an org-wide policy**.</span></span> <span data-ttu-id="cd906-163">Teams 채널 메시지 및 Teams 채팅에는 별도의 보존 정책이 필요하므로 조직 전체 정책을 만들어도 여기에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-163">If you create an org-wide policy, Teams channel messages and Teams chats aren't included because these require a separate retention policy.</span></span>

- <span data-ttu-id="cd906-164">**Teams는 고급 보존을 지원하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="cd906-164">**Teams doesn't support advanced retention**.</span></span> <span data-ttu-id="cd906-165">보존 정책을 만들 때 [특정 조건을 만족하는 콘텐츠를 식별하기 위해 고급 설정](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions)을 선택하면 Teams 위치를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-165">When you create a retention policy, if you choose the [Advanced settings to identify content that meets specific conditions](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions), the Teams locations are not available.</span></span> <span data-ttu-id="cd906-166">현재 Teams에서 보존은 해당 위치를 선택할 때 모든 채팅 및 채널 메시지 콘텐츠에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-166">Retention in Teams applies to all the chat and channel message content when you select those locations.</span></span>

- <span data-ttu-id="cd906-167">**개인 채널의 Teams 메시지는 Teams 채널 메시지에 대한 보존 정책을 구성할 때 포함되지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="cd906-167">**Teams messages in private channels aren't included when you configure a retention policy for Teams channel messages**.</span></span> <span data-ttu-id="cd906-168">현재 개인 채널은 보존 정책에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-168">Currently, private channels aren't supported by retention policies.</span></span> 

- <span data-ttu-id="cd906-169">**Teams 대화 및 채널 메시지에 대해 좋음 및 기타 응답이 유지되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd906-169">**Likes and other reactions are not retained for Teams chat and channel messages**.</span></span> <span data-ttu-id="cd906-170">이모티콘 형태의 다른 사람들의 반응은 보존 정책에 의해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-170">Reactions from others in the form of emoticons aren't supported by retention policies.</span></span>

- <span data-ttu-id="cd906-171">**Outlook에서 잘못된 표시 문제가 발생했습니다**.</span><span class="sxs-lookup"><span data-stu-id="cd906-171">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="cd906-172">Skype 또는 Teams 위치에 대한 보존 정책을 만드는 경우 사용자가 Outlook 데스크톱 클라이언트에서 사서함 폴더의 속성을 볼 때 해당 정책 중 하나가 기본 폴더 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-172">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="cd906-173">이것은 Outlook의 잘못된 표시 문제이며 [알려진 문제](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)입니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-173">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="cd906-174">기본 폴더 정책으로 표시되어야 하는 것은 폴더에 적용되는 사서함 보존 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-174">What should be displayed as the default folder policy is the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="cd906-175">Skype 또는 Teams 보존 정책은 사용자의 사서함에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-175">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

- <span data-ttu-id="cd906-176">**구성 문제**</span><span class="sxs-lookup"><span data-stu-id="cd906-176">**Configuration issues**:</span></span> 
    - <span data-ttu-id="cd906-177">**Teams 채널 메시지** 위치에 **팀 선택**을 선택하면 팀이 아닌 Microsoft 365 그룹이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-177">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="cd906-178">이 그룹을 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="cd906-178">Don't select these groups.</span></span>
    
    - <span data-ttu-id="cd906-179">**Teams 채팅** 위치에 대해 **사용자 선택**을 선택하면 게스트 및 사서함이 아닌 사용자가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd906-179">When you select **Choose users** for the **Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="cd906-180">보존 정책은 이러한 사용자를 위해 설계되지 않았으므로 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="cd906-180">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="cd906-181">구성 지침</span><span class="sxs-lookup"><span data-stu-id="cd906-181">Configuration guidance</span></span>

<span data-ttu-id="cd906-182">Microsoft 365에서 보존을 구성할 준비가 되면 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd906-182">If you're ready to configure retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>
