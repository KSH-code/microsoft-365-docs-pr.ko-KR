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
ms.openlocfilehash: 985131900a5e07188c0af641fb86f794d558f80b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919784"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="4bfcc-103">Microsoft Teams의 보존에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="4bfcc-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="4bfcc-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="4bfcc-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="4bfcc-105">Teams에서 보존 규정에 따라 채팅이나 메시지가 삭제되었다는 메시지를 본 적이 있다면 [보존 정책 관련 Teams 메시지](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-105">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="4bfcc-106">이 페이지는 해당 보존 정책을 관리하는 IT 관리자를 위한 정보를 담고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-106">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="4bfcc-107">이 문서의 정보는 Microsoft Teams 메시지와 관련된 정보를 포함하므로 [보존에 대해 알아보기](retention.md)를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-107">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams messages.</span></span>

<span data-ttu-id="4bfcc-108">다른 워크로드는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-108">For other workloads, see:</span></span>

- [<span data-ttu-id="4bfcc-109">SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="4bfcc-109">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="4bfcc-110">Yammer의 보존에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="4bfcc-110">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="4bfcc-111">Exchange의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="4bfcc-111">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="4bfcc-112">보존 및 삭제에 포함된 항목</span><span class="sxs-lookup"><span data-stu-id="4bfcc-112">What's included for retention and deletion</span></span>

<span data-ttu-id="4bfcc-113">Teams 보존 정책을 통해 다음의 Teams 항목(포함된 이미지, 표, 하이퍼텍스트 링크, 다른 Teams 메시지, 파일, [카드 콘텐츠](/microsoftteams/platform/task-modules-and-cards/what-are-cards)에 연결된 링크를 포함한 채팅 및 채널 메시지)을 보존하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-113">The following Teams items can be retained and deleted by using retention policies for Teams: Chat messages and channel messages, including embedded images, tables, hypertext links and links to other Teams messages and files, and [card content](/microsoftteams/platform/task-modules-and-cards/what-are-cards).</span></span> <span data-ttu-id="4bfcc-114">채팅 메시지에는 채팅에 속한 모든 사람의 이름이 포함되어 있고, 채널 메시지에는 팀 이름과 메시지 제목이 포함되어 있습니다(제공되는 경우).</span><span class="sxs-lookup"><span data-stu-id="4bfcc-114">Chat messages include all the names of the people in the chat, and channel messages include the team name and the message title (if supplied).</span></span> 

> [!NOTE]
> <span data-ttu-id="4bfcc-115">카드 콘텐츠 포함은 최근에 추가된 사항이며 이제 테넌트에 완전히 배포되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-115">Including card content is a recent addition and now fully rolled out to tenants.</span></span> <span data-ttu-id="4bfcc-116">자세한 내용은 [이제 Teams의 응용 프로그램을 통한 적응형 카드 콘텐츠에 대한 Microsoft 365 규정 준수 기능 제공](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-116">For more information, see [Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).</span></span>

<span data-ttu-id="4bfcc-117">현재 비공개 채널의 Teams 메시지는 보존 정책에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-117">Teams messages in private channels are currently not supported for retention policies.</span></span> <span data-ttu-id="4bfcc-118">Teams에 대한 보존 정책을 사용할 때 코드 조각, Teams 모바일 클라이언트에서 녹음된 목소리 메모, 미리 보기, 알림 이미지, 이모티콘 형태로 표현된 다른 사용자의 응답은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-118">Code snippets, recorded voice memos from the Teams mobile client, thumbnails, announcement images, and reactions from others in the form of emoticons are not included when you use retention policies for Teams.</span></span>

<span data-ttu-id="4bfcc-119">Teams에서 사용하는 전자 메일 및 파일은 Teams의 보존 정책에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-119">Emails and files that you use with Teams aren't included in retention policies for Teams.</span></span> <span data-ttu-id="4bfcc-120">이러한 항목은 자체 보존 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-120">These items have their own retention policies.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="4bfcc-121">보존이 Microsoft Teams에서 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="4bfcc-121">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="4bfcc-122">보존 정책을 사용하여 Teams의 채팅 및 채널 메시지를 보존하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-122">You can use a retention policy to retain and delete data from chats and channel messages in Teams.</span></span> <span data-ttu-id="4bfcc-123">Exchange 사서함은 뒤에서 이러한 메시지를 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-123">Behind the scenes, Exchange mailboxes are used to store these messages.</span></span> <span data-ttu-id="4bfcc-124">Teams 채팅의 테이터는 채팅에 포함된 각 사용자의 사서함에 있는 숨겨진 폴더에 저장되고, 팀의 그룹 사서함에 있는 유사한 숨겨진 폴더는 Teams 채널 메시지에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-124">Data from Teams chats is stored in a hidden folder in the mailbox of each user included in the chat, and a similar hidden folder in a group mailbox is used for Teams channel messages.</span></span>

<span data-ttu-id="4bfcc-125">이러한 사서함은 RecipientTypeDetails 특성에 따라 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-125">These mailboxes are, listed by their RecipientTypeDetails attribute:</span></span>

- <span data-ttu-id="4bfcc-126">**MailUser**: 이러한 사서함은 클라우드 기반 Teams 사용자를 위한 메시지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-126">**MailUser**: These mailboxes store messages for cloud-based Teams users.</span></span>
- <span data-ttu-id="4bfcc-127">**UserMailbox**: 이러한 사서함은 [온-프레미스 Teams 사용자](search-cloud-based-mailboxes-for-on-premises-users.md)를 위한 메시지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-127">**UserMailbox**: These mailboxes store messages for [on-premises Teams users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
- <span data-ttu-id="4bfcc-128">**GroupMailbox**: 이러한 사서함은 Teams 채널의 메시지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-128">**GroupMailbox**: These mailboxes store messages for Teams channels.</span></span>

<span data-ttu-id="4bfcc-129">Teams 회의실에 사용되는 RoomMailbox와 같은 다른 사서함 유형은 Teams 보존 정책에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-129">Other mailbox types, such as RoomMailbox that is used for Teams conference rooms, are not supported for Teams retention policies.</span></span>

<span data-ttu-id="4bfcc-130">Teams에서 역시 이 데이터를 저장하는 Azure 기반 채팅 서비스를 사용하고, 기본적으로 이 서비스에서는 데이터를 무제한적으로 저장한다는 사실을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-130">It's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data indefinitely.</span></span> <span data-ttu-id="4bfcc-131">따라서 규정 준수를 이유로 Teams 메시지를 삭제해야 하는 경우 Exchange 사서함과 기본 Azure 기반 채팅 서비스 모두에서 이 데이터를 영구적으로 삭제할 수 있는 Teams에 대한 보존 정책을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-131">For this reason, if you need to delete Teams messages for compliance reasons, we recommend that you use retention policies for Teams that can permanently delete this data from both the Exchange mailboxes and the underlying Azure-powered chat service.</span></span> <span data-ttu-id="4bfcc-132">기본 아키텍처에 대한 자세한 내용은 [Microsoft Teams의 보안 및 규정 준수](/MicrosoftTeams/security-compliance-overview) 및 특히 [정보 보호 아키텍처](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-132">For more information about the underlying architecture, see [Security and compliance in Microsoft Teams](/MicrosoftTeams/security-compliance-overview) and specifically, the [Information Protection Architecture](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="4bfcc-133">Teams 채팅 및 채널 메시지가 사서함에 저장되어 있어도 이 Teams 데이터는 **Teams 채널 메시지** 및 **Teams 채팅** 위치에 대해 구성된 보존 정책에 의해서만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-133">Although Teams chats and channel messages are stored in mailboxes, this Teams data is included only by a retention policy that's configured for the **Teams channel messages** and **Teams chats** locations.</span></span> <span data-ttu-id="4bfcc-134">Teams 채팅 및 채널 메시지는 Exchange 사용자 또는 그룹 사서함에 대해 구성된 보존 정책의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-134">Teams chats and channel messages are not affected by retention policies that are configured for Exchange user or group mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="4bfcc-135">Teams 데이터를 보존하는 활성 보존 정책에 사용자가 포함되어 있고 Teams 데이터를 보존하기 위해 이 정책에 포함된 사용자의 사서함을 삭제하면 사서함이 [비활성 사서함](inactive-mailboxes-in-office-365.md)로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-135">If a user is included in an active retention policy that retains Teams data and you a delete a mailbox of a user who is included in this policy, to retain the Teams data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="4bfcc-136">사용자에 대한 이 Teams 데이터를 유지할 필요가 없는 경우 사서함을 삭제하기 전에 사용자 계정을 보존 정책에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-136">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="4bfcc-137">채팅 및 채널 메시지에 대한 보존 정책을 구성한 후에는, Exchange 서비스의 타이머 작업이 해당 Teams 메시지가 저장된 숨겨진 폴더의 항목을 주기적으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-137">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="4bfcc-138">타이머 작업의 실행은 7일까지 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-138">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="4bfcc-139">이러한 항목의 보존 기간이 만료되면, 해당 항목은 영구적으로 삭제되기 전에 모든 사용자 또는 그룹 사서함에서 "일시 삭제됨" 항목을 저장하는 또 다른 숨겨진 폴더인 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-139">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="4bfcc-140">채팅 및 채널 메시지에 대해 보존 정책을 구성한 후 콘텐츠가 취하는 경로는 보존 정책이 보존 및 삭제, 보존만 또는 삭제만 가능한지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-140">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="4bfcc-141">보존 정책이 보존 및 삭제하는 경우:</span><span class="sxs-lookup"><span data-stu-id="4bfcc-141">When the retention policy is to retain and then delete:</span></span>

![Teams 채팅 및 채널 메시지의 보존 흐름 다이어그램](../media/teamsretentionlifecycle.png)

<span data-ttu-id="4bfcc-143">다이어그램의 두 경로:</span><span class="sxs-lookup"><span data-stu-id="4bfcc-143">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="4bfcc-144">보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 편집하거나 삭제** 하는 경우에는, 원본 메시지가 21일 내에 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-144">**If a chat or channel message is edited or deleted** by the user during the retention period, the original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder within 21 days.</span></span> <span data-ttu-id="4bfcc-145">이 메시지는 보존 기간이 만료 될 때까지 저장된 다음 24 시간 내에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-145">The message is stored there until the retention period expires and then the message is permanently deleted within 24 hours.</span></span>

2. <span data-ttu-id="4bfcc-146">**채팅 또는 채널 메시지가 삭제되지 않는 경우**, 편집 후 현재 메시지에 대한 메시지는 보존 기간이 만료 된 후 SubstrateHolds 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-146">**If a chat or channel message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="4bfcc-147">이 작업은 만료 날짜로부터 최대 7일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-147">This action takes up to 7 days from the expiry date.</span></span> <span data-ttu-id="4bfcc-148">메시지가 SubstrateHolds 폴더에 있으면 24시간 내에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-148">When the message is in the SubstrateHolds folder, it is then permanently deleted within 24 hours.</span></span> 

> [!NOTE]
> <span data-ttu-id="4bfcc-149">SubstrateHolds 폴더의 메시지는 eDiscovery 도구에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-149">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="4bfcc-150">SubstrateHolds 폴더에서 메시지가 영구적으로 삭제될 때까지 메시지는 eDiscovery 도구로 검색 가능한 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-150">Until messages are permanently deleted from this SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="4bfcc-151">보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-151">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="4bfcc-152">보유 전용 보존 정책의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="4bfcc-152">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="4bfcc-153">**채팅 또는 채널 메시지를 편집하거나 삭제하는 경우**, 원본 메시지의 복사본은 21일 내에 SubstrateHolds 폴더에 만들어지고 보존 기간이 만료될 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-153">**If a chat or channel message is edited or deleted**: A copy of the original message is created in the SubstrateHolds folder within 21 days, and retained there until the retention period expires.</span></span> <span data-ttu-id="4bfcc-154">그런 다음 24시간 이내에 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-154">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="4bfcc-155">**항목이 수정되거나 삭제되지 않거나** 보존 기간 중에 편집 후 현재 메시지에 대한 경우: 보존 기간 전후에 아무런 변화가 없습니다. 메시지는 원래 위치에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-155">**If the item is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="4bfcc-156">삭제 전용 보존 정책의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="4bfcc-156">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="4bfcc-157">보존 기간 동안 **메시지가 삭제되지 않은 경우**: 보존 기간이 끝나면 메시지가 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-157">**If the message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="4bfcc-158">이 작업은 만료 날짜로부터 최대 7일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-158">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="4bfcc-159">그런 다음 24시간 이내에 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-159">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="4bfcc-160">해당 기간 동안 **사용자가 해당 항목을 삭제하는 경우** 항목은 21일 이내에 24시간 안에 영구적으로 삭제되는 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-160">**If the item is deleted by the user** during the period, the item is moved to the SubstrateHolds folder within 21 days where it is then permanently deleted within 24 hours.</span></span>


## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="4bfcc-161">비즈니스용 Skype 및 팀 상호 운용 채팅</span><span class="sxs-lookup"><span data-stu-id="4bfcc-161">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="4bfcc-162">비즈니스용 Skype 채팅이 Teams로 이동하는 경우 해당 채팅은 Teams 채팅 스레드에서 메시지가 되고 해당 사서함에 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-162">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="4bfcc-163">Teams 보존 정책은 이러한 메시지를 Teams 스레드에서 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-163">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="4bfcc-164">그러나 비즈니스용 Skype 및 비즈니스용 Skype 클라이언트 쪽에서 대화 기록을 사용하도록 설정한 경우 기록이 사서함에 저장되는 경우 해당 Teams의 보존 정책이 해당 채팅 데이터를 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-164">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span> <span data-ttu-id="4bfcc-165">이 콘텐츠의 경우 비즈니스용 Skype에 대해 구성된 보존 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-165">For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="4bfcc-166">모임 및 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="4bfcc-166">Meetings and external users</span></span>

<span data-ttu-id="4bfcc-167">채널 모임 메시지는 채널 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채널 메시지** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-167">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="4bfcc-168">즉석 모임 및 예약된 모임 메시지는 그룹 채팅 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채팅** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-168">Impromptu and scheduled meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="4bfcc-169">조직에서 호스팅하는 모임에 외부 사용자가 포함된 경우:</span><span class="sxs-lookup"><span data-stu-id="4bfcc-169">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="4bfcc-170">외부 사용자가 테넌트에서 게스트 계정을 사용하여 참여하는 경우 이 사용자에게는 조직의 Teams 보존 정책을 적용할 수 있는 섀도 사서함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-170">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="4bfcc-171">모임의 모든 메시지는 사용자의 사서함과 섀도 사서함에 모두 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-171">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="4bfcc-172">외부 사용자가 다른 Microsoft 365 조직의 계정을 사용하여 참여하는 경우 보존 정책은 이 사용자의 메시지가 다른 테넌트의 해당 사용자의 사서함에 저장되어 있기 때문에 해당 사용자의 메시지를 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-172">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant.</span></span> <span data-ttu-id="4bfcc-173">그러나 동일한 모임의 경우 보존 정책이 사용자의 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-173">For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="4bfcc-174">사용자가 조직을 떠나는 경우</span><span class="sxs-lookup"><span data-stu-id="4bfcc-174">When a user leaves the organization</span></span> 

<span data-ttu-id="4bfcc-175">Exchange Online에 사서함이 있는 사용자가 조직을 떠나 Microsoft 365 계정이 삭제된 경우 보존이 적용되는 해당 사용자의 채팅 메시지는 비활성 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-175">If a user who has a mailbox in Exchange Online leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="4bfcc-176">채팅 메시지는 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-176">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="4bfcc-177">자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-177">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="4bfcc-178">사용자가 Teams에 저장한 파일이 있다면 SharePoint 및 OneDrive의 경우 [해당 섹션](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-178">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="4bfcc-179">제한 사항</span><span class="sxs-lookup"><span data-stu-id="4bfcc-179">Limitations</span></span>

<span data-ttu-id="4bfcc-180">Microsoft는 Teams에서 보존 기능을 최적화하기 위해 지속적으로 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-180">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="4bfcc-181">그 동안 Teams 채널 메시지와 채팅에 대한 보존을 사용할 때는 다음 몇 가지 제한 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-181">In the meantime, here are a few limitations to be aware of when you use retention for Teams channel messages and chats:</span></span>

- <span data-ttu-id="4bfcc-182">**Outlook에서 잘못된 표시 문제가 발생했습니다**.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-182">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="4bfcc-183">Skype 또는 Teams 위치에 대한 보존 정책을 만드는 경우 사용자가 Outlook 데스크톱 클라이언트에서 사서함 폴더의 속성을 볼 때 해당 정책 중 하나가 기본 폴더 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-183">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="4bfcc-184">이것은 Outlook의 잘못된 표시 문제이며 [알려진 문제](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)입니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-184">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="4bfcc-185">기본 폴더 정책으로 표시되어야 하는 것은 폴더에 적용되는 사서함 보존 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-185">What should be displayed as the default folder policy is the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="4bfcc-186">Skype 또는 Teams 보존 정책은 사용자의 사서함에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-186">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

- <span data-ttu-id="4bfcc-187">**구성 문제**</span><span class="sxs-lookup"><span data-stu-id="4bfcc-187">**Configuration issues**:</span></span> 
    - <span data-ttu-id="4bfcc-188">**Teams 채널 메시지** 위치에 **팀 선택** 을 선택하면 팀이 아닌 Microsoft 365 그룹이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-188">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="4bfcc-189">이 그룹을 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-189">Don't select these groups.</span></span>
    
    - <span data-ttu-id="4bfcc-190">**Teams 채팅** 위치에 대해 **사용자 선택** 을 선택하면 게스트 및 사서함이 아닌 사용자가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-190">When you select **Choose users** for the **Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="4bfcc-191">보존 정책은 이러한 사용자를 위해 설계되지 않았으므로 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-191">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="4bfcc-192">구성 지침</span><span class="sxs-lookup"><span data-stu-id="4bfcc-192">Configuration guidance</span></span>

<span data-ttu-id="4bfcc-193">Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-193">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="4bfcc-194">Teams에 대한 보존 정책을 구성할 준비가 되면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bfcc-194">If you're ready to configure a retention policy for Teams, see [Create and configure retention policies](create-retention-policies.md).</span></span>