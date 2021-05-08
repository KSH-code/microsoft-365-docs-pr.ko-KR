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
ms.openlocfilehash: db167894f32bcc1e30054b9cc4738af300b6d704
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280802"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="8be26-103">Microsoft Teams의 보존에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="8be26-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="8be26-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="8be26-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="8be26-105">Teams에서 보존 규정에 따라 채팅이나 메시지가 삭제되었다는 메시지를 본 적이 있다면 [보존 정책 관련 Teams 메시지](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-105">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="8be26-106">이 페이지는 해당 보존 정책을 관리하는 IT 관리자를 위한 정보를 담고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-106">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="8be26-107">이 문서의 정보는 Microsoft Teams 메시지와 관련된 정보를 포함하므로 [보존에 대해 알아보기](retention.md)를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-107">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams messages.</span></span>

<span data-ttu-id="8be26-108">다른 워크로드는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-108">For other workloads, see:</span></span>

- [<span data-ttu-id="8be26-109">SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="8be26-109">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="8be26-110">Yammer의 보존에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="8be26-110">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="8be26-111">Exchange의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="8be26-111">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="8be26-112">보존 및 삭제에 포함된 항목</span><span class="sxs-lookup"><span data-stu-id="8be26-112">What's included for retention and deletion</span></span>

<span data-ttu-id="8be26-113">Teams 채팅 메시지 및 채널 메시지는 Teams 보존 정책을 사용하여 삭제될 수 있으며, 메시지의 텍스트 외에도 다음의 Teams 항목(포함된 이미지, 표, 하이퍼텍스트 링크, 다른 Teams 메시지 및 파일, [카드 콘텐츠](/microsoftteams/platform/task-modules-and-cards/what-are-cards)에 연결된 링크)을 규정 준수를 위해 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-113">Teams chats messages and channel messages can be deleted by using retention policies for Teams, and in addition to the text in the messages, the following items can be retained for compliance reasons: Embedded images, tables, hypertext links, links to other Teams messages and files, and [card content](/microsoftteams/platform/task-modules-and-cards/what-are-cards).</span></span> <span data-ttu-id="8be26-114">채팅 메시지에는 채팅에 속한 모든 사람의 이름이 포함되어 있고, 채널 메시지에는 팀 이름과 메시지 제목이 포함되어 있습니다(제공되는 경우).</span><span class="sxs-lookup"><span data-stu-id="8be26-114">Chat messages include all the names of the people in the chat, and channel messages include the team name and the message title (if supplied).</span></span> 

> [!NOTE]
> <span data-ttu-id="8be26-115">Teams의 보존 정책에 카드 콘텐츠를 포함하는 것은 매우 최근에 추가된 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-115">Including card content in a retention policy for Teams is a fairly recent addition.</span></span> <span data-ttu-id="8be26-116">자세한 내용은 [이제 Teams의 응용 프로그램을 통한 적응형 카드 콘텐츠에 대한 Microsoft 365 규정 준수 기능 제공](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-116">For more information, see [Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).</span></span>

<span data-ttu-id="8be26-p103">현재 개인 채널의 Teams 메시지는 보존 정책에 대해 지원되지 않습니다. Teams에 대한 보존 정책을 사용할 때 코드 조각, Teams 모바일 클라이언트에서 녹음된 목소리 메모, 미리 보기, 알림 이미지, 이모티콘 형태로 표현된 다른 사용자의 응답은 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-p103">Teams messages in private channels are currently not supported for retention policies. Code snippets, recorded voice memos from the Teams mobile client, thumbnails, announcement images, and reactions from others in the form of emoticons are not retained when you use retention policies for Teams.</span></span>

<span data-ttu-id="8be26-p104">Teams에서 사용하는 전자 메일 및 파일은 Teams의 보존 정책에 포함되지 않습니다. 이 항목에는 자체 보존 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-p104">Emails and files that you use with Teams aren't included in retention policies for Teams. These items have their own retention policies.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="8be26-121">보존이 Microsoft Teams에서 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="8be26-121">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="8be26-122">이 섹션에서는 백엔드 스토리지 및 프로세스를 통해 규정 준수 요구 사항이 충족되는 방법과 현재 Teams 앱에 표시되는 메시지가 아니라 eDiscovery 도구를 통해 확인해야 하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-122">Use this section to understand how your compliance requirements are met by backend storage and processes, and should be verified by eDiscovery tools rather than by messages that are currently visible in the Teams app.</span></span>

<span data-ttu-id="8be26-123">보존 정책을 사용하여 Teams의 채팅 및 채널 메시지를 보존하고, 해당 채팅 및 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-123">You can use a retention policy to retain data from chats and channel messages in Teams, and delete these chats and messages.</span></span> <span data-ttu-id="8be26-124">Exchange 사서함은 이러한 메시지에서 복사된 데이터를 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-124">Behind the scenes, Exchange mailboxes are used to store data copied from these messages.</span></span> <span data-ttu-id="8be26-125">Teams 채팅의 테이터는 채팅에 포함된 각 사용자의 사서함에 있는 숨겨진 폴더에 저장되고, 팀의 그룹 사서함에 있는 유사한 숨겨진 폴더는 Teams 채널 메시지에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-125">Data from Teams chats is stored in a hidden folder in the mailbox of each user included in the chat, and a similar hidden folder in a group mailbox is used for Teams channel messages.</span></span> <span data-ttu-id="8be26-126">이러한 숨겨진 폴더는 사용자 또는 관리자가 직접 액세스할 수 있도록 설계되지 않지만 규정 준수 관리자가 eDiscovery 도구를 사용하여 검색할 수 있는 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-126">These hidden folders are not designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with eDiscovery tools.</span></span>

<span data-ttu-id="8be26-127">이러한 사서함은 RecipientTypeDetails 특성에 따라 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-127">These mailboxes are, listed by their RecipientTypeDetails attribute:</span></span>

- <span data-ttu-id="8be26-128">**UserMailbox**: 이러한 사서함은 클라우드 기반 Teams 사용자를 위한 메시지 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-128">**UserMailbox**: These mailboxes store message data for cloud-based Teams users.</span></span>
- <span data-ttu-id="8be26-129">**MailUser**: 이러한 사서함은 [온-프레미스 Teams 사용자](search-cloud-based-mailboxes-for-on-premises-users.md)를 위한 메시지 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-129">**MailUser**: These mailboxes store message data for [on-premises Teams users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
- <span data-ttu-id="8be26-130">**GroupMailbox**: 이러한 사서함은 Teams 채널의 메시지 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-130">**GroupMailbox**: These mailboxes store message data for Teams channels.</span></span>

<span data-ttu-id="8be26-131">Teams 회의실에 사용되는 RoomMailbox와 같은 다른 사서함 유형은 Teams 보존 정책에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-131">Other mailbox types, such as RoomMailbox that is used for Teams conference rooms, are not supported for Teams retention policies.</span></span>

<span data-ttu-id="8be26-132">Teams는 모든 메시지(채팅 및 채널 메시지)에 대해 Azure 제공 채팅 서비스를 기본 저장소로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-132">Teams uses an Azure-powered chat service as its primary storage for all messages (chats and channel messages).</span></span> <span data-ttu-id="8be26-133">Teams 메시지를 삭제해야 하는 경우, 메시지가 만들어진 시기에 따라 특정 기간 후에 메시지를 삭제할 수 있는 Teams용 보존 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-133">If you need to delete Teams messages for compliance reasons, retention policies for Teams can delete messages after a specified period, based on when they were created.</span></span> <span data-ttu-id="8be26-134">그런 다음 메시지는 규정 준수 작업을 위해 저장된 Exchange 사서함 및 기본 Azure 기반 채팅 서비스에서 사용하는 기본 저장소에서 모두 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-134">Messages are then permanently deleted from both the Exchange mailboxes where they stored for compliance operations, and from the primary storage used by the underlying Azure-powered chat service.</span></span> <span data-ttu-id="8be26-135">기본 아키텍처에 대한 자세한 내용은 [Microsoft Teams의 보안 및 규정 준수](/MicrosoftTeams/security-compliance-overview), 특히 [정보 보호 아키텍처](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-135">For more information about the underlying architecture, see [Security and compliance in Microsoft Teams](/MicrosoftTeams/security-compliance-overview) and specifically, the [Information Protection Architecture](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="8be26-136">Teams 채팅 및 채널 메시지의 이 데이터가 사서함에 저장되어 있는 경우, **Teams 채널 메시지** 및 **Teams 채팅** 에 대한 보존 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-136">Although this data from Teams chats and channel messages are stored in mailboxes, you must configure a retention policy for the **Teams channel messages** and **Teams chats** locations.</span></span> <span data-ttu-id="8be26-137">Teams 채팅 및 채널 메시지는 Exchange 사용자 또는 그룹 사서함에 대해 구성된 보존 정책에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-137">Teams chats and channel messages are not included in retention policies that are configured for Exchange user or group mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="8be26-138">Teams 메시지를 보존하는 활성 보존 정책에 사용자가 포함되어 있고 이 정책에 포함된 사용자의 사서함을 삭제하면, 사서함이 Teams 데이터를 보존하기 위해 [비활성 사서함](inactive-mailboxes-in-office-365.md)으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-138">If a user is included in an active retention policy that retains Teams messages and you a delete a mailbox of a user who is included in this policy, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md) to retain the Teams data.</span></span> <span data-ttu-id="8be26-139">사용자에 대한 이 Teams 데이터를 유지할 필요가 없는 경우 사서함을 삭제하기 전에 사용자 계정을 보존 정책에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-139">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="8be26-140">채팅 및 채널 메시지에 대한 보존 정책을 구성한 후에는, Exchange 서비스의 타이머 작업이 해당 Teams 메시지가 저장된 숨겨진 폴더의 항목을 주기적으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-140">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="8be26-141">일반적으로 타이머 작업을 실행하는 데 1~7일이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-141">The timer job typically takes 1-7 days to run.</span></span> <span data-ttu-id="8be26-142">이러한 항목의 보존 기간이 만료되면, 해당 항목은 영구적으로 삭제되기 전에 모든 사용자 또는 그룹 사서함에서 "일시 삭제됨" 항목을 저장하는 또 다른 숨겨진 폴더인 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-142">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span> 

<span data-ttu-id="8be26-143">메시지는 SubstrateHolds 폴더에 최소 1일 동안 남아 있으며 삭제할 수있는 경우, 타이머 작업은 다음에 실행할 때 해당 메시지를 영구적으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-143">Messages remain in the SubstrateHolds folder for at least 1 day, and then if they are eligible for deletion, the timer job permanently deletes them the next time it runs.</span></span>

<span data-ttu-id="8be26-144">채팅 및 채널 메시지에 대해 보존 정책을 구성한 후 콘텐츠가 취하는 경로는 보존 정책이 보존 및 삭제, 보존만 또는 삭제만 가능한지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-144">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="8be26-145">보존 정책이 보존 및 삭제하는 경우:</span><span class="sxs-lookup"><span data-stu-id="8be26-145">When the retention policy is to retain and then delete:</span></span>

![Teams 채팅 및 채널 메시지의 보존 흐름 다이어그램](../media/teamsretentionlifecycle.png)

<span data-ttu-id="8be26-147">다이어그램의 두 경로:</span><span class="sxs-lookup"><span data-stu-id="8be26-147">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="8be26-148">보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 편집하거나 삭제** 하는 경우에는, 원본 메시지가 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-148">**If a chat or channel message is edited or deleted** by a user during the retention period, the original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="8be26-149">메시지는 최소 1일 동안 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-149">The message is stored there for at least 1 day.</span></span> <span data-ttu-id="8be26-150">보존 기간이 만료되면 메시지가 다음에 실행될 때(일반적으로 1~7일) 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-150">When the retention period expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="8be26-151">**사용자가 채팅 또는 채널 메시지를 삭제하지 않는 경우**, 편집 후 현재 메시지에 대한 메시지는 보존 기간이 만료 된 후 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-151">**If a chat or channel message is not deleted** by a user and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="8be26-152">이 작업은 일반적으로 만료 날짜로부터 1~7일 사이에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-152">This action typically takes between 1-7 days from the expiry date.</span></span> <span data-ttu-id="8be26-153">메시지가 SubstrateHolds 폴더에 있으면 최소 1일 동안 여기에 저장되고 다음에 타이머 작업이 실행될 때 메시지가 영구적으로 삭제됩니다(일반적으로 1-7일 사이).</span><span class="sxs-lookup"><span data-stu-id="8be26-153">When the message is in the SubstrateHolds folder, it is stored there for at least 1 day, and then the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span> 

> [!NOTE]
> <span data-ttu-id="8be26-154">숨겨진 폴더를 포함하여 사서함에 저장된 메시지는 eDiscovery 도구로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-154">Messages stored in mailboxes, including the hidden folders, are searchable by eDiscovery tools.</span></span> <span data-ttu-id="8be26-155">SubstrateHolds 폴더에서 메시지가 영구적으로 삭제될 때까지 메시지는 eDiscovery 도구로 검색 가능한 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-155">Until messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="8be26-156">메시지가 SubstrateHolds 폴더에서 영구적으로 삭제되면 삭제 작업이 백엔드 Azure 채팅 서비스에 전달된 다음 동일한 작업을 Teams 클라이언트 앱에 릴레이합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-156">When messages are permanently deleted from the SubstrateHolds folder, a delete operation is communicated to the backend Azure chat service, that then relays the same operation to the Teams client app.</span></span> <span data-ttu-id="8be26-157">이 통신 또는 캐싱의 지연은 짧은 시간 동안 사용자가 Teams 앱에서 이러한 메시지를 계속 볼 수 있지만 이러한 메시지의 데이터가 eDiscovery 검색에서 반환되지 않는 이유를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-157">Delays in this communication or caching can explain why, for a short period of time, users might still see these messages in their Teams app, but data from these messages isn't returned in eDiscovery searches.</span></span> <span data-ttu-id="8be26-158">Teams 앱에 표시되는 메시지는 규정 준수 요구 사항을 위해 보존되었는지 또는 영구적으로 삭제되었는지를 정확하게 반영하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-158">Messages visible in the Teams app are not an accurate reflection of whether they are retained or permanently deleted for compliance requirements.</span></span>

<span data-ttu-id="8be26-159">보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-159">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="8be26-160">보유 전용 보존 정책의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="8be26-160">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="8be26-161">보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 편집하거나 삭제** 하는 경우에는, 원본 메시지가 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동되며 최소 1일 이상 해당 폴더에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-161">**If a chat or channel message is edited or deleted** by a user during the retention period: The original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder, and retained there for at least 1 day.</span></span> <span data-ttu-id="8be26-162">보존 정책이 영구 보존되도록 구성된 경우 항목은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-162">If the retention policy is configured to retain forever, the item remains there.</span></span> <span data-ttu-id="8be26-163">보존 정책에 보존 기간의 종료 날짜가 있고 보존 기간이 만료되면 메시지가 다음에 실행될 때(일반적으로 1~7일) 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-163">If the retention policy has an end date for the retention period and it expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="8be26-164">**사용자가 채팅 또는 채널 메시지를 수정 또는 삭제하지 않거나** 보존 기간 중에 편집 후 현재 메시지에 대한 경우: 보존 기간 전후에 아무런 변화가 없습니다. 메시지는 원래 위치에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-164">**If the chat or channel message is not modified or deleted** by a user and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="8be26-165">삭제 전용 보존 정책에 대한 콘텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="8be26-165">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="8be26-166">보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 편집하거나 삭제** 하는 경우에는, 원본 메시지가 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-166">**If the chat or channel message is edited or deleted** by a user during the retention period: The original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="8be26-167">메시지는 최소 1일 동안 해당 폴더에 보존되고 다음에 타이머 작업이 실행될 때 영구적으로 삭제됩니다(일반적으로 1-7일 사이).</span><span class="sxs-lookup"><span data-stu-id="8be26-167">The message is retained there for at least 1 day and permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="8be26-168">보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 삭제하지 않은 경우**: 보존 기간이 끝나면 메시지가 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-168">**If a chat or channel message is not deleted** by a user during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="8be26-169">이 작업은 일반적으로 만료 날짜로부터 1~7일 사이에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-169">This action typically takes between 1-7 days from the expiry date.</span></span> <span data-ttu-id="8be26-170">메시지는 최소 1일 동안 해당 폴더에 보존되고 다음에 타이머 작업이 실행될 때 영구적으로 삭제됩니다(일반적으로 1-7일 사이).</span><span class="sxs-lookup"><span data-stu-id="8be26-170">The message is retained there for at least 1 day and then permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

#### <a name="example-flows-and-timings-for-retention-policies"></a><span data-ttu-id="8be26-171">보존 정책의 흐름 및 타이밍 예</span><span class="sxs-lookup"><span data-stu-id="8be26-171">Example flows and timings for retention policies</span></span>

<span data-ttu-id="8be26-172">다음 예제를 사용하여 이전 섹션에서 설명한 프로세스 및 타이밍이 다음 구성을 가진 보존 정책에 어떻게 적용되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-172">Use the following examples to see how the processes and timings explained in the previous sections apply to retention policies that have the following configurations:</span></span>

- [<span data-ttu-id="8be26-173">예제 1: 7년 동안 보존만</span><span class="sxs-lookup"><span data-stu-id="8be26-173">Example 1: Retain-only for 7 years</span></span>](#example-1-retain-only-for-7-years)
- [<span data-ttu-id="8be26-174">예제 2: 30일 동안 보존한 다음 삭제</span><span class="sxs-lookup"><span data-stu-id="8be26-174">Example 2: Retain for 30 days and then delete</span></span>](#example-2-retain-for-30-days-and-then-delete)
- [<span data-ttu-id="8be26-175">예제 3: 1일 후에 ​​삭제만</span><span class="sxs-lookup"><span data-stu-id="8be26-175">Example 3: Delete-only after 1 day</span></span>](#example-3-delete-only-after-1-day)

<span data-ttu-id="8be26-176">영구 삭제를 참조하는 모든 예제의 경우 [보존 원칙](retention.md#the-principles-of-retention-or-what-takes-precedence)으로 인해 메시지가 항목을 보존하기 위한 다른 보존 정책의 적용을 받거나 eDiscovery 보존이 적용되는 경우 이 작업이 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-176">For all examples that refer to permanent deletion, because of the [principles of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), this action is suspended if the message is subject to another retention policy to retain the item or it is subject to an eDiscovery hold.</span></span>

##### <a name="example-1-retain-only-for-7-years"></a><span data-ttu-id="8be26-177">예제 1: 7년 동안 보존만</span><span class="sxs-lookup"><span data-stu-id="8be26-177">Example 1: Retain-only for 7 years</span></span>

<span data-ttu-id="8be26-178">1일 차에 사용자가 채팅 또는 채널 메시지를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-178">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="8be26-179">5일 차에 사용자가 해당 메시지를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-179">On day 5, the user edits that message.</span></span>

<span data-ttu-id="8be26-180">30일 차에 사용자가 현재 메시지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-180">On day 30, the user deletes the current message.</span></span>

<span data-ttu-id="8be26-181">보존 결과:</span><span class="sxs-lookup"><span data-stu-id="8be26-181">Retention outcomes:</span></span>

- <span data-ttu-id="8be26-182">원본 메시지의 경우:</span><span class="sxs-lookup"><span data-stu-id="8be26-182">For the original message:</span></span>
    - <span data-ttu-id="8be26-183">5일 차에는 메시지가 SubstrateHolds 폴더에 복사되어 eDiscovery 도구를 사용하여 1일부터 최소 7년(보존 기간) 동안 계속 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-183">On day 5, the message is copied to the SubstrateHolds folder where it can still be searched with eDiscovery tools for a minimum of 7 years from day 1 (the retention period).</span></span>

- <span data-ttu-id="8be26-184">현재 (편집된) 메시지의 경우:</span><span class="sxs-lookup"><span data-stu-id="8be26-184">For the current (edited) message:</span></span>
    - <span data-ttu-id="8be26-185">30일 차에는 메시지가 SubstrateHolds 폴더에 이동되어 eDiscovery 도구를 사용하여 1일부터 최소 7년(보존 기간) 동안 계속 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-185">On day 30, the message moves to the SubstrateHolds folder where it can still be searched with eDiscovery tools for a minimum of 7 years from day 1 (the retention period).</span></span>

<span data-ttu-id="8be26-186">사용자가 보존 기간이 아닌 지정된 보존 기간 이후에 현재 메시지를 삭제 한 경우 메시지는 여전히 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-186">If the user had deleted the current message after the specified retention period, instead of within the retention period, the message would still be moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="8be26-187">그러나 이제 보존 기간이 만료되었으므로 메시지는 최소 1일 후에 영구적으로 삭제되고 일반적으로 1~7일 이내에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-187">However, now the retention period has expired, the message would be permanently deleted after the minimum of 1 day and then typically within 1-7 days.</span></span>

##### <a name="example-2-retain-for-30-days-and-then-delete"></a><span data-ttu-id="8be26-188">예제 2: 30일 동안 보존한 다음 삭제</span><span class="sxs-lookup"><span data-stu-id="8be26-188">Example 2: Retain for 30 days and then delete</span></span>

<span data-ttu-id="8be26-189">1일 차에 사용자가 채팅 또는 채널 메시지를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-189">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="8be26-190">10일 차에 사용자가 해당 메시지를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-190">On day 10, the user edits that message.</span></span>

<span data-ttu-id="8be26-191">사용자는 더 이상 편집하지 않고 메시지를 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-191">The user doesn't make further edits and doesn't delete the message.</span></span>

<span data-ttu-id="8be26-192">보존 결과:</span><span class="sxs-lookup"><span data-stu-id="8be26-192">Retention outcomes:</span></span>

- <span data-ttu-id="8be26-193">원본 메시지의 경우:</span><span class="sxs-lookup"><span data-stu-id="8be26-193">For the original message:</span></span>
    - <span data-ttu-id="8be26-194">10 일에 메시지는 SubstrateHolds 폴더에 복사되며 eDiscovery 도구를 사용하여 검색 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-194">On day 10, the message is copied to the SubstrateHolds folder, where it can still be searched with eDiscovery tools.</span></span>
    - <span data-ttu-id="8be26-195">보존 기간(1일부터 30일)이 끝나면 메시지는 일반적으로 최소 1일 후 1~ 7일 이내에 영구적으로 삭제된 다음 eDiscovery 검색과 함께 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-195">At the end of the retention period (30 days from day 1), the message is permanently deleted typically within 1-7 days after the minimum of 1 day, and then won't be returned with eDiscovery searches.</span></span>

- <span data-ttu-id="8be26-196">현재 (편집된) 메시지의 경우:</span><span class="sxs-lookup"><span data-stu-id="8be26-196">For the current (edited) message:</span></span>
    - <span data-ttu-id="8be26-197">보존 기간(1일부터 30일)이 끝나면 메시지는 일반적으로 1~7일 이내에 SubstrateHolds 폴더로 이동하며 eDiscovery 도구를 사용하여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-197">At the end of the retention period (30 days from day 1), the message moves to the SubstrateHolds folder typically within 1-7 days, where it can still be searched with eDiscovery tools.</span></span>
    - <span data-ttu-id="8be26-198">그리고 나서 메시지는 일반적으로 최소 1일 후 1~ 7일 이내에 영구적으로 삭제된 다음 eDiscovery 검색과 함께 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-198">The message is then permanently deleted typically within 1-7 days after the minimum of 1 day, and then won't be returned with eDiscovery searches.</span></span>

##### <a name="example-3-delete-only-after-1-day"></a><span data-ttu-id="8be26-199">예제 3: 1일 후에 ​​삭제만</span><span class="sxs-lookup"><span data-stu-id="8be26-199">Example 3: Delete-only after 1 day</span></span>

> [!NOTE]
> <span data-ttu-id="8be26-200">1-7 일의 기간 내에 작동하는 이 구성 및 보존 프로세스의 짧은 1일 기간으로 인해 이 섹션에서는 일반적인 시간 범위 내에 있는 예제 타이밍을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-200">Because of the short one-day duration of this configuration and retention processes that operate within a time period of 1-7 days, this section shows example timings that are within the typical time ranges.</span></span>

<span data-ttu-id="8be26-201">1일 차에 사용자가 채팅 또는 채널 메시지를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-201">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="8be26-202">사용자가 메시지를 편집하거나 삭제하지 않은 경우 보존 결과의 예:</span><span class="sxs-lookup"><span data-stu-id="8be26-202">Example retention outcome if the user doesn't edit or delete the message:</span></span>

- <span data-ttu-id="8be26-203">5일(일반적으로 2일 보존 기간이 시작된 후 1~7일):</span><span class="sxs-lookup"><span data-stu-id="8be26-203">Day 5 (typically 1-7 days after the start of the retention period on day 2):</span></span>
    - <span data-ttu-id="8be26-204">메시지는 이 폴더로 이동하며 eDiscovery 도구로 검색할 수 있는 최소 1일 동안 이 폴더에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-204">The message moves to the SubstrateHolds folder and remains there for at least 1 day where it can still be searched with eDiscovery tools.</span></span>

- <span data-ttu-id="8be26-205">9일(일반적으로 SubstrateHolds 폴더에서 최소 1일 이후부터 1~7일):</span><span class="sxs-lookup"><span data-stu-id="8be26-205">Day 9 (typically 1-7 days after a minimum of 1 day in the SubstrateHolds folder):</span></span>
    - <span data-ttu-id="8be26-206">메시지가 영구적으로 삭제된 후 eDiscovery 검색에서 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-206">The message is permanently deleted and then won't be returned with eDiscovery searches.</span></span>

<span data-ttu-id="8be26-207">이 예제에서 볼 수 있는처럼, 하루만에 메시지를 삭제하도록 보존 정책을 구성할 수 있습니다. 그러나 이 서비스는 규정 준수 삭제를 보장하기 위해 여러 프로세스를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-207">As this example shows, although you can configure a retention policy to delete messages after just one day, the service undergoes multiple processes to ensure a compliant deletion.</span></span> <span data-ttu-id="8be26-208">결과적으로 1일 후 삭제 작업은 메시지가 영구적으로 삭제되기 까지 16일이 걸릴 수 있으므로 eDiscovery 검색에서 더 이상 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-208">As a result, a delete action after 1 day could take 16 days before the message is permanently deleted so that it's no longer returned in eDiscovery searches.</span></span>

## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="8be26-209">비즈니스용 Skype 및 팀 상호 운용 채팅</span><span class="sxs-lookup"><span data-stu-id="8be26-209">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="8be26-210">비즈니스용 Skype 채팅이 Teams로 이동하는 경우 해당 채팅은 Teams 채팅 스레드에서 메시지가 되고 해당 사서함에 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-210">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="8be26-211">Teams 보존 정책은 이러한 메시지를 Teams 스레드에서 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-211">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="8be26-p120">그러나 비즈니스용 Skype 및 비즈니스용 Skype 클라이언트 쪽에서 대화 기록을 사용하도록 설정한 경우 기록이 사서함에 저장되는 경우 해당 Teams의 보존 정책이 해당 채팅 데이터를 처리하지 않습니다. 이 콘텐츠의 경우 비즈니스용 Skype에 대해 구성된 보존 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-p120">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy. For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="8be26-214">모임 및 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="8be26-214">Meetings and external users</span></span>

<span data-ttu-id="8be26-215">채널 모임 메시지는 채널 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채널 메시지** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-215">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="8be26-216">즉석 모임 및 예약된 모임 메시지는 그룹 채팅 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채팅** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-216">Impromptu and scheduled meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="8be26-217">조직에서 호스팅하는 모임에 외부 사용자가 포함된 경우:</span><span class="sxs-lookup"><span data-stu-id="8be26-217">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="8be26-218">외부 사용자가 테넌트에서 게스트 계정을 사용하여 참여하는 경우 이 사용자에게는 조직의 Teams 보존 정책을 적용할 수 있는 섀도 사서함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-218">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="8be26-219">모임의 모든 메시지는 사용자의 사서함과 섀도 사서함에 모두 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-219">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="8be26-p122">외부 사용자가 다른 Microsoft 365 조직의 계정을 사용하여 참여하는 경우 보존 정책은 이 사용자의 메시지가 다른 테넌트의 해당 사용자의 사서함에 저장되어 있기 때문에 해당 사용자의 메시지를 삭제할 수 없습니다. 그러나 동일한 모임의 경우 보존 정책이 사용자의 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-p122">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant. For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="8be26-222">사용자가 조직을 떠나는 경우</span><span class="sxs-lookup"><span data-stu-id="8be26-222">When a user leaves the organization</span></span> 

<span data-ttu-id="8be26-223">Exchange Online에 사서함이 있는 사용자가 조직을 떠나 Microsoft 365 계정이 삭제된 경우 보존이 적용되는 해당 사용자의 채팅 메시지는 비활성 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-223">If a user who has a mailbox in Exchange Online leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="8be26-224">채팅 메시지는 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-224">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="8be26-225">자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-225">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="8be26-226">사용자가 Teams에 저장한 파일이 있다면 SharePoint 및 OneDrive의 경우 [해당 섹션](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-226">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="8be26-227">제한 사항</span><span class="sxs-lookup"><span data-stu-id="8be26-227">Limitations</span></span>

<span data-ttu-id="8be26-p124">Teams에서 보존 기능을 최적화하기 위해 지속적으로 작업하고 있습니다. 그 동안에는 Teams 채널 메시지 및 채팅에 보존 정책을 사용하는 경우 다음 제한 사항을 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-p124">We're continuously working on optimizing retention functionality in Teams. In the meantime, be aware of the following limitation when you use retention policies for Teams channel messages and chats:</span></span>

- <span data-ttu-id="8be26-230">**Outlook에서 잘못된 표시 문제가 발생했습니다**.</span><span class="sxs-lookup"><span data-stu-id="8be26-230">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="8be26-231">Skype 또는 Teams 위치에 대한 보존 정책을 만드는 경우 사용자가 Outlook 데스크톱 클라이언트에서 사서함 폴더의 속성을 볼 때 해당 정책 중 하나가 기본 폴더 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-231">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="8be26-232">이것은 Outlook의 잘못된 표시 문제이며 [알려진 문제](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)입니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-232">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="8be26-233">대신 폴더에 적용되는 사서함 보존 정책이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-233">Instead, you should see the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="8be26-234">Skype 또는 Teams 보존 정책은 사용자의 사서함에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be26-234">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="8be26-235">구성 지침</span><span class="sxs-lookup"><span data-stu-id="8be26-235">Configuration guidance</span></span>

<span data-ttu-id="8be26-236">Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-236">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="8be26-237">Teams에 대한 보존 정책을 구성할 준비가 되면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8be26-237">If you're ready to configure a retention policy for Teams, see [Create and configure retention policies](create-retention-policies.md).</span></span>