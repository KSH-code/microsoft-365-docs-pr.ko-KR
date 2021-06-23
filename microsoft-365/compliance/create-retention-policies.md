---
title: 콘텐츠를 자동으로 보존하거나 삭제하는 보존 정책을 만들고 구성하기
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
description: 보존 정책을 사용하면 사용자가 전자 메일과 문서, 대화를 사용하여 생성하는 콘텐츠를 효율적으로 유지 관리할 수 있습니다. 원하는 내용을 유지하고 원하지 않는 항목을 제거하세요.
ms.openlocfilehash: 2ddc95b5e614fb321ccc5472bc6031f570218528
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053074"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="746d5-104">보존 정책 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="746d5-104">Create and configure retention policies</span></span>

><span data-ttu-id="746d5-105">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="746d5-105">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="746d5-106">콘텐츠를 보존할지, 삭제할지, 아니면 보존했다가 삭제할지를 사전에 결정하여 조직 데이터를 관리하기 위해 보존 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-106">Use a retention policy to manage the data for your organization by deciding proactively whether to retain content, delete content, or retain and then delete the content.</span></span>

<span data-ttu-id="746d5-107">보존 정책은 컨테이너 수준에서 동일한 데이터 보존 설정을 할당하여 해당 컨테이너의 콘텐츠가 자동으로 이를 상속하게 함으로써 이 작업을 매우 효율적으로 수행할 수 있게 해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-107">A retention policy lets you do this very efficiently by assigning the same retention settings at the container level to be automatically inherited by content in that container.</span></span> <span data-ttu-id="746d5-108">예를 들어 SharePoint 사이트의 모든 항목과 사용자 Exchange 사서함의 모든 전자 메일, Microsoft Teams에서 사용되는 팀의 모든 채널 메시지가 여기 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-108">For example, all items in SharePoint sites, all email messages in users' Exchange mailboxes, all channel messages for teams that are used with Microsoft Teams.</span></span> <span data-ttu-id="746d5-109">컨테이너 수준에서의 보존 정책이나 항목 수준에서의 보존 레이블을 사용해야 할지가 확실하지 않다면 [보존 정책 및 보존 레이블](retention.md#retention-policies-and-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-109">If you're not sure whether to use a retention policy at the container level or a retention label at the item level, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="746d5-110">Microsoft 365에서의 보존 정책과 보존 레이블 작동 방식에 대한 자세한 내용은 [보존 정책과 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-110">For more information about retention policies and how retention works in Microsoft 365, see [Learn about retention policies and retention labels](retention.md).</span></span>

> [!NOTE]
> <span data-ttu-id="746d5-111">이 페이지의 정보는 규정 준수 관리자를 위한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-111">The information on this page is for compliance administrators.</span></span> <span data-ttu-id="746d5-112">관리자가 아니지만 본인이 사용하는 앱의 보존 정책 구성 방식을 알고 싶다면 지원 센터나 IT 팀 또는 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-112">If you are not an administrator and want to understand how retention policies have been configured for the apps that you use, contact your help desk, IT department, or administrator.</span></span> <span data-ttu-id="746d5-113">Teams 차트와 채널 메시지에 보존 정책 관련 메시지가 표시된다면 [보존 정책 관련 Teams 메시지](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)를 리뷰하는 게 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-113">If you're seeing messages about retention policies in Teams chats and channel messages, you might find it helpful to review [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="746d5-114">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="746d5-114">Before you begin</span></span>

<span data-ttu-id="746d5-115">조직의 전역 관리자는 보존 정책을 만들고 편집할 수 있는 모든 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-115">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="746d5-116">전역 관리자로 로그인하지 않은 경우 [보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-116">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="746d5-117">보존 정책 만들기 및 구성하기</span><span class="sxs-lookup"><span data-stu-id="746d5-117">Create and configure a retention policy</span></span>

<span data-ttu-id="746d5-118">보존 정책은 보존 정책에 ‘위치’로 식별되는 여러 서비스를 지원할 수 있지만 지원되는 모든 위치를 포함하는 단일 보존 정책을 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-118">Although a retention policy can support multiple services that are identified as "locations" in the retention policy, you can't create a single retention policy that includes all the supported locations:</span></span>

- <span data-ttu-id="746d5-119">Exchange 전자 메일</span><span class="sxs-lookup"><span data-stu-id="746d5-119">Exchange email</span></span>
- <span data-ttu-id="746d5-120">SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="746d5-120">SharePoint site</span></span>
- <span data-ttu-id="746d5-121">OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="746d5-121">OneDrive accounts</span></span>
- <span data-ttu-id="746d5-122">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="746d5-122">Microsoft 365 groups</span></span>
- <span data-ttu-id="746d5-123">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="746d5-123">Skype for Business</span></span>
- <span data-ttu-id="746d5-124">Exchange 공용 폴더</span><span class="sxs-lookup"><span data-stu-id="746d5-124">Exchange public folders</span></span>
- <span data-ttu-id="746d5-125">Teams 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="746d5-125">Teams channel messages</span></span>
- <span data-ttu-id="746d5-126">Teams 채팅</span><span class="sxs-lookup"><span data-stu-id="746d5-126">Teams chats</span></span>
- <span data-ttu-id="746d5-127">Yammer 커뮤니티 메시지</span><span class="sxs-lookup"><span data-stu-id="746d5-127">Yammer community messages</span></span>
- <span data-ttu-id="746d5-128">Yammer 사용자 메시지</span><span class="sxs-lookup"><span data-stu-id="746d5-128">Yammer user messages</span></span>

<span data-ttu-id="746d5-129">보존 정책을 생성할 때 Teams 또는 Yammer 위치를 선택하면 다른 위치는 자동으로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-129">If you select the Teams or Yammer locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="746d5-130">즉, Teams 또는 Yammer 위치 포함 여부에 따라, 따라야 할 지침도 달라진다는 뜻이죠.</span><span class="sxs-lookup"><span data-stu-id="746d5-130">This means that the instructions to follow depend on whether you need to include the Teams or Yammer locations:</span></span>

- <span data-ttu-id="746d5-131">[Teams 위치](#retention-policy-for-teams-locations)에 대한 보존 정책에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="746d5-131">[Instructions for a retention policy for Teams locations](#retention-policy-for-teams-locations)</span></span>
- [<span data-ttu-id="746d5-132">Yammer 위치에 대한 보존 정책에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="746d5-132">Instructions for a retention policy for Yammer locations</span></span>](#retention-policy-for-yammer-locations)
- <span data-ttu-id="746d5-133">[Teams 및 Yammer](#retention-policy-for-locations-other-than-teams-and-yammer) 이외의 위치에 대한 보존 정책에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="746d5-133">[Instructions for a retention policy for locations other than Teams and Yammer](#retention-policy-for-locations-other-than-teams-and-yammer)</span></span>

<span data-ttu-id="746d5-134">보존 정책이 두 개 이상이고 보존 레이블도 사용하는 경우에는 여러 보존 설정이 동일한 콘텐츠에 적용되는 경우의 결과를 이해하기 위해 [보존 원칙 또는 우선하는 항목](retention.md#the-principles-of-retention-or-what-takes-precedence)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-134">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="746d5-135">Teams 위치 보존 정책</span><span class="sxs-lookup"><span data-stu-id="746d5-135">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="746d5-136">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-136">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="746d5-137">**새 보존 정책** 을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-137">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="746d5-138">**정책을 적용하기 위한 위치 선택** 페이지에서, Teams에 대한 하나 혹은 양쪽 위치를 선택합니다. **Teams 채널 메시지** 및 **Teams 채팅**.</span><span class="sxs-lookup"><span data-stu-id="746d5-138">For the **Choose locations to apply the policy** page, select one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>

   <span data-ttu-id="746d5-139">**Teams 채널 메시지** 의 경우, 표준 채널이지만 [비공개 채널](/microsoftteams/private-channels)의 메시지는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-139">For **Teams channel messages**, message from standard channels but not [private channels](/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="746d5-140">현재 개인 채널은 보존 정책에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-140">Currently, private channels aren't supported by retention policies.</span></span>

   <span data-ttu-id="746d5-141">기본적으로 [모든 팀과 모든 사용자가 선택되어 있지만](#a-policy-that-applies-to-entire-locations), [**선택** 및 **배제** 옵션](#a-policy-with-specific-inclusions-or-exclusions)을 선택하여 이를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-141">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the [**Choose** and **Exclude** options](#a-policy-with-specific-inclusions-or-exclusions).</span></span> <span data-ttu-id="746d5-142">그러나 기본값을 변경하기 전에 포함 또는 제외되도록 구성할 때 메시지를 삭제하는 보존 정책의 다음과 같은 결과에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-142">However, before you change the default, be aware of the following consequences for a retention policy that deletes messages when it's configured for includes or excludes:</span></span>
    
    - <span data-ttu-id="746d5-143">그룹 채팅의 경우 메시지 복사본이 채팅에 포함된 각 사용자의 사서함에 저장되어 있기 때문에 정책을 할당하지 않은 사용자의 메시지 복사본이 eDiscovery 결과에 계속 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-143">For group chats, because a copy of messages are saved in each user's mailbox who are included in the chat, copies of messages will continue to be returned in eDiscovery results from users who weren't assigned the policy.</span></span>
    - <span data-ttu-id="746d5-144">정책을 할당하지 않은 사용자의 경우 삭제된 메시지가 Teams 검색 결과에 반환되지만 사용자에게 할당된 정책에서 영구적으로 삭제한 결과 메시지 내용은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-144">For users who weren't assigned the policy, deleted messages will be returned in their Teams search results but won't display the contents of the message as a result of the permanent deletion from the policy assigned to users.</span></span>

4. <span data-ttu-id="746d5-145">**콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-145">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

   <span data-ttu-id="746d5-146">삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-146">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="746d5-147">자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-147">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="746d5-148">마법사를 완료하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-148">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="746d5-149">Teams에 대한 보존 정책을 사용하고 최종 사용자 환경을 이해해야할 시기에 대한 지침은 Teams 설명서에서 [Microsoft Teams에 대한 보존 정책 관리](/microsoftteams/retention-policies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-149">For guidance when to use retention policies for Teams and understand the end user experience, see [Manage retention policies for Microsoft Teams](/microsoftteams/retention-policies) from the Teams documentation.</span></span>

<span data-ttu-id="746d5-150">예제 연습을 통해 보존 및 타이밍 정보용으로 지원되는 메시지 요소를 포함하여 Teams에 대한 보존 작동 방식에 관한 기술 세부 정보는 [Microsoft Teams의 보존에 대해 자세히 알아보기](retention-policies-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-150">For technical details about how retention works for Teams, including what elements of messages are supported for retention and timing information with example walkthroughs, see [Learn about retention for Microsoft Teams](retention-policies-teams.md).</span></span>

#### <a name="known-configuration-issues"></a><span data-ttu-id="746d5-151">알려진 구성 문제</span><span class="sxs-lookup"><span data-stu-id="746d5-151">Known configuration issues</span></span>

- <span data-ttu-id="746d5-152">항목을 마지막으로 수정한 경우 보존 기간을 시작하는 옵션을 선택할 수 있어도 항상 **항목을 만든 시간** 이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-152">Although you can select the option to start the retention period when items were last modified, the value of **When items were created** is always used.</span></span> <span data-ttu-id="746d5-153">편집된 메시지의 경우 원본 메시지의 복사본이 원래 타임스탬프와 함께 저장되어 미리 편집된 메시지를 만들 때를 식별하고, 사후 편집된 메시지에 새로운 타임스탬프가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-153">For messages that are edited, a copy of the original message is saved with its original timestamp to identify when this pre-edited message was created, and the post-edited message has a newer timestamp.</span></span>

- <span data-ttu-id="746d5-154">**Teams 채널 메시지** 위치에 **팀 선택** 을 선택하면 팀이 아닌 Microsoft 365 그룹이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-154">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="746d5-155">이 그룹을 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-155">Don't select these groups.</span></span>

- <span data-ttu-id="746d5-156">**Teams 채팅을 위한 사용자 선택** 위치를 선택하면 게스트 및 비 사서함이 사용자가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-156">When you select **Choose users for the Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="746d5-157">보존 정책은 이러한 사용자를 위해 설계되지 않았으므로 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-157">Retention policies aren't designed for these users, so don't select them.</span></span>


#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="746d5-158">Teams 지원에 필요한 추가 보존 정책</span><span class="sxs-lookup"><span data-stu-id="746d5-158">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="746d5-159">Teams는 채팅 및 채널 메시지 그 이상</span><span class="sxs-lookup"><span data-stu-id="746d5-159">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="746d5-160">Microsoft 365 그룹에서 만든 팀(이전에는 Office 365 그룹)이 있는 경우 **Microsoft 365 그룹** 위치를 사용하여 Microsoft 365 그룹을 포함하는 보존 정책을 추가적으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-160">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="746d5-161">이 보존 정책은 그룹의 사서함, 사이트 및 파일의 콘텐츠에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-161">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="746d5-162">Microsoft 365 그룹에 연결되어 있지 않은 팀 사이트가 있는 경우, Teams에서 파일을 보존하고 삭제하려면 **SharePoint 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-162">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="746d5-163">채팅에서 공유되는 파일은 해당 파일을 공유하는 사용자의 OneDrive 계정에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-163">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span>

- <span data-ttu-id="746d5-164">채널에 업로드된 파일은 해당 팀의 SharePoint 사이트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-164">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="746d5-165">특정 팀의 SharePoint 사이트 및 특정 팀 사용자의 OneDrive 계정을 선택하여 Microsoft 365 그룹에 연결되어 있지 않으면 해당 팀의 파일에 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-165">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="746d5-166">Microsoft 365 그룹, SharePoint 사이트 또는 OneDrive 계정에 적용되는 보존 정책은 해당 메시지가 삭제되기 전에 Teams 채팅 또는 채널 메시지에서 참조되는 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-166">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="746d5-167">이 시나리오에서는 파일이 Teams 메시지에 여전히 표시되지만 사용자가 파일을 선택하면 "파일을 찾을 수 없음" 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-167">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="746d5-168">이 동작은 보존 정책에만 국한된 것이 아니며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-168">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-yammer-locations"></a><span data-ttu-id="746d5-169">Yammer 위치에 대한 보존 정책</span><span class="sxs-lookup"><span data-stu-id="746d5-169">Retention policy for Yammer locations</span></span>

> [!NOTE]
> <span data-ttu-id="746d5-170">Yammer에 대한 보존 정책은 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-170">Retention policies for Yammer are in preview.</span></span>
>
> <span data-ttu-id="746d5-171">이 기능을 사용하려면 Yammer 네트워크가 하이브리드 모드가 아니라 [기본 모드](/yammer/configure-your-yammer-network/overview-native-mode)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-171">To use this feature, your Yammer network must be [Native Mode](/yammer/configure-your-yammer-network/overview-native-mode), not Hybrid Mode.</span></span>

1. <span data-ttu-id="746d5-172">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-172">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="746d5-173">**새 보존 정책** 을 선택하여 새 보존 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-173">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="746d5-174">**콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-174">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="746d5-175">삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-175">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="746d5-176">자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-176">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

4. <span data-ttu-id="746d5-177">**위치 선택** 페이지에 대해 **특정 위치 선택** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-177">For the **Choose locations** page, select **Let me choose specific locations**.</span></span> <span data-ttu-id="746d5-178">그런 다음 Yammer에 대한 위치 중 하나 또는 둘 모두를 전환합니다. **Yammer 커뮤니티 메시지** 및 **Yammer 사용자 메시지**.</span><span class="sxs-lookup"><span data-stu-id="746d5-178">Then toggle on one or both of the locations for Yammer: **Yammer community message** and **Yammer user messages**.</span></span>
    
    <span data-ttu-id="746d5-179">기본적으로 모든 커뮤니티와 사용자가 선택되지만 포함하거나 제외할 커뮤니티와 사용자를 지정하여 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-179">By default, all communities and users are selected, but you can refine this by specifying communities and users to be included or excluded.</span></span>
    
    <span data-ttu-id="746d5-180">Yammer 사용자 메시지의 경우:</span><span class="sxs-lookup"><span data-stu-id="746d5-180">For Yammer user messages:</span></span> 
    - <span data-ttu-id="746d5-181">기본값 **모두** 를 그대로 두면 Azure B2B 게스트 사용자가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-181">If you leave the default at **All**, Azure B2B guest users are not included.</span></span> 
    - <span data-ttu-id="746d5-182">**사용자 선택** 을 선택한 경우, 계정을 알고 있는 외부 사용자에게 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-182">If you select **Choose user**, you can apply a retention policy to external users if you know their account.</span></span>

5. <span data-ttu-id="746d5-183">마법사를 완료하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-183">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="746d5-184">Yammer용 보존 정책이 작동하는 방식에 대한 자세한 내용은 [Yammer용 보존 정보](retention-policies-yammer.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-184">For more information about how retention policies work for Yammer, see [Learn about retention for Yammer](retention-policies-yammer.md).</span></span>

#### <a name="additional-retention-policies-needed-to-support-yammer"></a><span data-ttu-id="746d5-185">Yammer를 지원하려면 추가 보존 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-185">Additional retention policies needed to support Yammer</span></span>

<span data-ttu-id="746d5-186">Yammer는 단지 커뮤니티 메시지와 비공개 메시지 그 이상의 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-186">Yammer is more than just community messages and private messages.</span></span> <span data-ttu-id="746d5-187">Yammer 네트워크의 전자 메일 메시지를 보존 및 삭제하려면 **Microsoft 365 그룹** 위치를 사용하여 Yammer에 사용되는 Microsoft 365 그룹을 포함하는 추가 보존 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-187">To retain and delete email messages for your Yammer network, configure an additional retention policy that includes any Microsoft 365 groups that are used for Yammer, by using the **Microsoft 365 Groups** location.</span></span> 

<span data-ttu-id="746d5-188">Yammer에 저장된 파일을 유지 및 삭제하려면 **SharePoint 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-188">To retain and delete files that are stored in Yammer, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations:</span></span>

- <span data-ttu-id="746d5-189">개인 메시지에서 공유되는 파일은 파일을 공유한 사용자의 OneDrive 계정에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-189">Files that are shared in private messages are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="746d5-190">커뮤니티에 업로드된 파일은 Yammer 커뮤니티의 SharePoint 사이트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-190">Files that are uploaded to communities are stored in the SharePoint site for the Yammer community.</span></span>

<span data-ttu-id="746d5-191">SharePoint 사이트 또는 OneDrive 계정에 적용된 보존 정책은 해당 메시지가 삭제되기 전에 Yammer 메시지에 참조된 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-191">It's possible that a retention policy that's applied to SharePoint sites or OneDrive accounts could delete a file that's referenced in a Yammer message before those messages get deleted.</span></span> <span data-ttu-id="746d5-192">이 시나리오에서는 파일이 Yammer 메시지에 여전히 표시되지만 사용자가 파일을 선택하면 "파일을 찾을 수 없음" 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-192">In this scenario, the file still displays in the Yammer message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="746d5-193">이러한 동작은 보존 정책에만 국한되지 않으며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-193">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a><span data-ttu-id="746d5-194">Teams 및 Yammer 이외의 위치에 대한 보존 정책</span><span class="sxs-lookup"><span data-stu-id="746d5-194">Retention policy for locations other than Teams and Yammer</span></span>

<span data-ttu-id="746d5-195">이러한 서비스에 적용되는 보존 정책에 대해 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-195">Use the following instructions for retention policies that apply to any of these services:</span></span>

- <span data-ttu-id="746d5-196">Exchange: 전자 메일 및 공용 폴더</span><span class="sxs-lookup"><span data-stu-id="746d5-196">Exchange: Email and public folders</span></span>
- <span data-ttu-id="746d5-197">SharePoint: 사이트</span><span class="sxs-lookup"><span data-stu-id="746d5-197">SharePoint: Sites</span></span>
- <span data-ttu-id="746d5-198">OneDrive: 계정</span><span class="sxs-lookup"><span data-stu-id="746d5-198">OneDrive: Accounts</span></span>
- <span data-ttu-id="746d5-199">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="746d5-199">Microsoft 365 groups</span></span>
- <span data-ttu-id="746d5-200">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="746d5-200">Skype for Business</span></span>

1. <span data-ttu-id="746d5-201">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-201">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="746d5-202">**새 보존 정책** 을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-202">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="746d5-203">**위치 선택** 페이지를 선택하려면 Teams 위치를 제외한 모든 위치를 토글로 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-203">For the **Choose locations** page, toggle on or off any of the locations except the locations for Teams.</span></span> <span data-ttu-id="746d5-204">각 위치에 대해 설정을 기본값으로 유지하여 [전체 위치에 정책을 적용](#a-policy-that-applies-to-entire-locations)하거나 [포함 및 제외를 지정](#a-policy-with-specific-inclusions-or-exclusions)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-204">For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

    <span data-ttu-id="746d5-205">위치 관련 정보:</span><span class="sxs-lookup"><span data-stu-id="746d5-205">Information specific to locations:</span></span>
    - [<span data-ttu-id="746d5-206">Exchange 전자 메일 및 Exchange 공용 폴더</span><span class="sxs-lookup"><span data-stu-id="746d5-206">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="746d5-207">SharePoint 사이트 및 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="746d5-207">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="746d5-208">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="746d5-208">Microsoft 365 Groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="746d5-209">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="746d5-209">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="746d5-210">**콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-210">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

    <span data-ttu-id="746d5-211">삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-211">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="746d5-212">자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-212">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="746d5-213">마법사를 완료하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-213">Complete the wizard to save your settings.</span></span>

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="746d5-214">Exchange 전자 메일 및 Exchange 공용 폴더에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="746d5-214">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="746d5-215">**Exchange 전자 메일** 위치는 사서함 수준에서 보존 설정을 적용하여 사용자의 전자 메일, 일정 및 기타 사서함 항목에 대한 보존을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-215">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="746d5-216">Exchange에 대한 보존 설정을 구성할 때 포함되고 제외되는 항목에 대한 자세한 내용은 [보존 및 삭제에 포함되는 항목](retention-policies-exchange.md#whats-included-for-retention-and-deletion)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-216">For detailed information about which items are included and excluded when you configure retention settings for Exchange, see [What's included for retention and deletion](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span></span>

<span data-ttu-id="746d5-217">Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-217">Note that even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="746d5-218">이러한 사서함의 콘텐츠를 보존하려면 **Microsoft 365 그룹** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-218">To retain content in these mailboxes, select the **Microsoft 365 Groups** location.</span></span>

<span data-ttu-id="746d5-219">**Exchange 공용 폴더** 위치는 보존 설정을 모든 공용 폴더에 적용하며 폴더 또는 사서함 수준에서 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-219">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="746d5-220">SharePoint 사이트 및 OneDrive 계정에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="746d5-220">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="746d5-221">**SharePoint 사이트** 위치를 선택할 때 보존 정책을 사용하여 SharePoint 커뮤니케이션 사이트, Microsoft 365 그룹으로 연결되지 않는 팀 사이트 및 클래식 사이트에서 문서를 보존하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-221">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Microsoft 365 groups, and classic sites.</span></span> <span data-ttu-id="746d5-222">Microsoft 365 그룹에서 연결된 팀 사이트는 이 옵션으로 지원되지 않으며 대신 해당 그룹의 사서함, 사이트 및 파일에 있는 콘텐츠에 적용되는 **Microsoft 365 그룹** 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-222">Team sites connected by Microsoft 365 groups aren't supported with this option and instead, use the **Microsoft 365 Groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="746d5-223">보존 정책이 사이트 수준에서 적용되더라도 보존 설정은 문서에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-223">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="746d5-224">SharePoint 및 OneDrive에 대한 보존 설정을 구성할 때 포함되고 제외되는 항목에 대한 자세한 내용은 [보존 및 삭제에 포함되는 항목](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-224">For detailed information about what's included and excluded when you configure retention settings for SharePoint and OneDrive, see [What's included for retention and deletion](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion).</span></span> 

<span data-ttu-id="746d5-225">SharePoint 사이트 또는 OneDrive 계정의 위치를 지정하는 경우, 사이트에 액세스할 수 있는 권한이 필요하지 않으며 **위치 편집** 페이지에서 URL을 지정하는 시점에 유효성 검사가 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-225">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="746d5-226">그러나 지정하는 SharePoint 사이트는 마법사 종료 시 존재하는지 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-226">However, the SharePoint sites that you specify are checked that they exist at the end of the wizard.</span></span> <span data-ttu-id="746d5-227">이 검사에 실패하는 경우, 입력한 URL에 대한 유효성 검사에 실패했다는 메시지가 표시되고 유효성 검사가 통과한 후에 마법사에서 보존 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-227">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="746d5-228">이 메시지가 표시되는 경우, 마법사에서 돌아가서 URL을 변경하거나 보존 정책에서 사이트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-228">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="746d5-229">포함하거나 제외할 개별 OneDrive 계정을 지정하려면 URL은 `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com` 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-229">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="746d5-230">예를 들어, "rsimone"라는 사용자 이름을 보유한 Contoso 테넌트에 있는 사용자의 경우: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="746d5-230">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="746d5-231">테넌트의 구문을 확인하고 사용자 URL을 확인하려면, [조직에 있는 모든 사용자 OneDrive URL 목록 가져오기](/onedrive/list-onedrive-urls)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-231">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="746d5-232">Microsoft 365 그룹에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="746d5-232">Configuration information for Microsoft 365 Groups</span></span>

<span data-ttu-id="746d5-233">Microsoft 365 그룹(이전의 Office 365 그룹)의 콘텐츠를 보존하거나 삭제하려면 **Microsoft 365 그룹** 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-233">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="746d5-234">Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-234">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="746d5-235">**Exchange 전자 메일** 위치에서 처음에 포함하거나 제외할 그룹 사서함을 지정할 수 있지만 보존 정책을 저장하려고 하면 "RemoteGroupMailbox"가 Exchange 위치에 대해 올바른 선택이 아니라는 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-235">Although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you'll see an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="746d5-236">Microsoft 365 그룹에 적용되는 보존 정책에는 그룹 사서함 및 SharePoint Teams 사이트가 기본값으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-236">By default, a retention policy applied to a Microsoft 365 group includes the group mailbox and SharePoint teams site.</span></span> <span data-ttu-id="746d5-237">SharePoint Teams 사이트에 저장된 파일은 이 위치에 포함되지만 Teams 대화 또는 Teams 채널 메시지가 고유한 보존 정책 위치를 가지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-237">Files stored in the SharePoint teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

<span data-ttu-id="746d5-238">보존 정책을 Microsoft 365 사서함에만 적용되거나 연결된 SharePoint 팀 사이트에만 적용하기 위해 기본값을 변경하려면 [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell cmdlet을 *Applications* 매개 변수와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-238">To change the default because you want the retention policy to apply to either just the Microsoft 365 mailboxes, or just the connected SharePoint teams sites, use the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell cmdlet with the *Applications* parameter with one of the following values:</span></span>

- <span data-ttu-id="746d5-239">그룹과 연결된 Microsoft 365 사서함의 경우`Group:Exchange`</span><span class="sxs-lookup"><span data-stu-id="746d5-239">`Group:Exchange` for just Microsoft 365 mailboxes that are connected to the group.</span></span>
- <span data-ttu-id="746d5-240">그룹과 연결된 SharePoint 사이트의 경우 `Group:SharePoint`</span><span class="sxs-lookup"><span data-stu-id="746d5-240">`Group:SharePoint` for just SharePoint sites that are connected to the group.</span></span>

<span data-ttu-id="746d5-241">선택한 Microsoft 365 그룹이 사서함과 SharePoint 사이트의 기본값으로 돌아가기 위해 `Group:Exchange,SharePoint`를 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-241">To return to the default value of both the mailbox and SharePoint site for the selected Microsoft 365 groups, specify `Group:Exchange,SharePoint`.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="746d5-242">비즈니스용 Skype에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="746d5-242">Configuration information for Skype for Business</span></span>

<span data-ttu-id="746d5-243">다른 위치와 달리 모든 사용자를 자동으로 포함하도록 Skype 위치의 상태를 전환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-243">Unlike other locations, you can't toggle the status of the Skype location on to automatically include all users.</span></span> <span data-ttu-id="746d5-244">대신, 해당 위치를 켜면 **편집** 옵션을 선택하여 대화를 유지할 사용자를 수동으로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-244">Instead, when you turn on that location, you must then select the **Edit** option to manually choose the users whose conversations you want to retain:</span></span>

![보존 정책을 위한 Skype 위치 편집](../media/skype-location-retention-policies.png)

<span data-ttu-id="746d5-246">이 **편집** 옵션을 선택한 후 **비즈니스용 Skype** 창에서 **이름** 열 앞에 숨겨진 상자를 선택하여 모든 사용자를 빠르게 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-246">After you select this **Edit** option, in the **Skype for Business** pane you can quickly include all users by selecting the hidden box before the **Name** column.</span></span> <span data-ttu-id="746d5-247">그러나 각 사용자가 정책의 특정 포함사항으로 간주된다는 점을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-247">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="746d5-248">따라서 이 상자를 선택하여 1,000명의 사용자를 포함하는 경우, 포함할 1,000명의 사용자를 수동으로 선택한 것과 같으며 이는 비즈니스용 Skype에 대해 지원되는 최대를 선택하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-248">So if you include 1,000 users by selecting this box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="746d5-249">Outlook 폴더인 **대화 내용** 은 Skype 아카이빙은 관계가 없는 기능</span><span class="sxs-lookup"><span data-stu-id="746d5-249">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="746d5-250">**대화 내용** 은 최종 사용자가 끌 수 있지만, Skype 아카이빙은 사용자는 액세스할 수 없고 eDiscovery에서만 액세스 가능한 숨김 폴더에 Skype 대화 사본을 저장하는 기능</span><span class="sxs-lookup"><span data-stu-id="746d5-250">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="746d5-251">콘텐츠를 보존 및 삭제하기 위한 설정</span><span class="sxs-lookup"><span data-stu-id="746d5-251">Settings for retaining and deleting content</span></span>

<span data-ttu-id="746d5-252">보존 정책에서 콘텐츠를 보존하고 삭제하기 위한 설정을 선택하면 보존 정책에 지정된 기간 동안 다음 구성 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-252">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="746d5-253">보존 전용</span><span class="sxs-lookup"><span data-stu-id="746d5-253">Retain-only</span></span>

    <span data-ttu-id="746d5-254">이 구성에서는 **특정 기간에 대한 항목을 보존** 을 선택하고 **보존 기간의 종료 시, 아무 작업도 수행하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="746d5-254">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**.</span></span> <span data-ttu-id="746d5-255">또는 **항목을 영구적으로 보존** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-255">Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="746d5-256">보존 후 삭제</span><span class="sxs-lookup"><span data-stu-id="746d5-256">Retain and then delete</span></span>

    <span data-ttu-id="746d5-257">이 구성에서는 **특정 기간에 대한 항목을 보존** 을 선택하고 **보존 기간의 종료 시, 항목을 자동으로 삭제합니다**.</span><span class="sxs-lookup"><span data-stu-id="746d5-257">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="746d5-258">삭제 전용</span><span class="sxs-lookup"><span data-stu-id="746d5-258">Delete-only</span></span>

    <span data-ttu-id="746d5-259">이 구성에서는 **특정 기간에 도달했을 때만 항목 삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-259">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="746d5-260">특정 기간 동안 콘텐츠 보존</span><span class="sxs-lookup"><span data-stu-id="746d5-260">Retaining content for a specific period of time</span></span>

<span data-ttu-id="746d5-261">보존 정책을 구성하면 항목을 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-261">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years.</span></span> <span data-ttu-id="746d5-262">또는 항목이 영구적으로 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-262">Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="746d5-263">보존 정책을 구성하면 콘텐츠를 영구적으로 또는 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-263">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="746d5-264">콘텐츠 보존 기간은 보존 정책이 적용된 시점이 아닌 콘텐츠 생성 시점을 기준으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-264">The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span>

<span data-ttu-id="746d5-265">보존 기간이 시작되는 경우, 또한 콘텐츠가 언제 만들어졌는지 또는 콘텐츠가 마지막으로 수정된 경우에는 파일 및 SharePoint, OneDrive 및 Microsoft 365 위치에 대해서만 지원되었는지의 경우를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-265">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups, when the content was last modified.</span></span>

<span data-ttu-id="746d5-266">예제:</span><span class="sxs-lookup"><span data-stu-id="746d5-266">Examples:</span></span>

- <span data-ttu-id="746d5-p132">SharePoint: 내용을 마지막으로 수정한 후 7년 동안 사이트 모음에 항목을 보관하고 해당 사이트 모음에 있는 문서가 6년 동안 수정되지 않은 경우, 문서가 수정되지 않은 경우, 문서는 1년 더만 보존됩니다. 문서를 다시 편집할 경우, 문서의 연령이 새로운 마지막 수정 날짜로부터 계산되며, 7년 더 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-p132">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified. If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>

- <span data-ttu-id="746d5-p133">Exchange: 7년 동안 우편함에 항목을 보관하고 6년 전에 메시지가 발송된 경우 메시지는 1년 동안만 유지됩니다. Exchange 항목의 경우 기간은 수신 전자 메일에 대해 수신된 날짜 또는 송신 전자 메일에 대해 전송된 날짜를 기준으로 합니다. 마지막으로 수정한 시점을 기준으로 항목을 유지하면 OneDrive 및 SharePoint의 사이트 컨텐츠에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-p133">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year. For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email. Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>

<span data-ttu-id="746d5-272">보존 기간이 끝나면 콘텐츠를 영구적으로 삭제할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-272">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>

![보존 설정 페이지](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="746d5-274">특정 사용 기간보다 오래된 콘텐츠 삭제</span><span class="sxs-lookup"><span data-stu-id="746d5-274">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="746d5-275">보존 정책은 항목을 보존했다가 삭제하거나, 혹은 보존하지 않고 오래된 콘텐츠를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-275">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>

<span data-ttu-id="746d5-276">두 경우 모두, 보존 정책이 항목을 삭제할 경우 보존 정책에 대해 지정된 기간은 정책이 할당된 시점이 아니라 콘텐츠가 만들어졌거나 수정된 이후부터 계산된다는 사실에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-276">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="746d5-p134">따라서 보존 정책을 처음으로 할당하기 전에 특히 해당 정책이 항목을 삭제할 때 먼저 기존 콘텐츠의 사용 기간과 해당 콘텐츠에 미치는 영향을 고려해야 합니다. 또한 새 정책을 할당하기 전에 사용자에게 가능한 영향을 평가할 시간을 제공하기 위해 새 정책을 전달해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-p134">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content. You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="746d5-279">전체 위치에 적용되는 정책</span><span class="sxs-lookup"><span data-stu-id="746d5-279">A policy that applies to entire locations</span></span>

<span data-ttu-id="746d5-280">위치를 선택하는 경우 비즈니스용 Skype를 제외하고, 위치의 상태가 **On** 인 경우, 기본 설정은 **모두** 가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-280">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>

<span data-ttu-id="746d5-281">보존 정책이 전체 위치의 조합에 적용되는 경우, 정책에 포함할 수 있는 수혜자, 사이트, 계정, 그룹 등의 수에 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-281">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups, etc., that the policy can include.</span></span>

<span data-ttu-id="746d5-p135">예를 들어 정책에 모든 Exchange 전자 메일과 모든 SharePoint 사이트가 포함된 경우 개수에 상관없이 모든 사이트와 수신자가 포함됩니다. 또한 Exchange의 경우 정책이 적용된 후 생성된 새 편지함이 정책을 자동으로 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-p135">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many. And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="746d5-284">특정 포함 또는 제외가 적용된 정책</span><span class="sxs-lookup"><span data-stu-id="746d5-284">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="746d5-285">선택적 구성을 사용하여 특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트에 대한 보존 설정의 범위를 지정하는 경우 정책별 몇 가지 제한 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-285">Be aware that if you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of.</span></span> <span data-ttu-id="746d5-286">자세한 내용은 [보존 정책 및 보존 레이블 정책의 제한 사항](retention-limits.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-286">For more information, see [Limits for retention policies and retention label policies](retention-limits.md).</span></span> 

<span data-ttu-id="746d5-287">선택적 구성을 사용하여 보존 설정의 범위를 지정하려면 해당 위치의 **상태** 가 **켜짐** 인지 확인한 후 링크를 사용하여 특정 사용자, Microsoft 365 그룹 또는 사이트를 포함하거나 배제하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-287">To use the optional configuration to scope your retention settings, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span>

> [!WARNING]
> <span data-ttu-id="746d5-288">마지막 구성을 포함했다가 제거하면 해당 위치에 대해 **모두** 로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-288">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="746d5-289">정책을 저장하기 전에 원하는 구성인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-289">Make sure this is the configuration that you intend before you save the policy.</span></span>
>
> <span data-ttu-id="746d5-290">예를 들어 데이터를 삭제하도록 구성된 보존 정책에 포함할 SharePoint 사이트 하나를 지정한 다음 단일 사이트를 제거하면 기본적으로 모든 SharePoint 사이트는 데이터를 영구적으로 삭제하는 보존 정책의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-290">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="746d5-291">Exchange 수신인, OneDrive 계정, 팀 채팅 사용자 등의 경우에도 마찬가지</span><span class="sxs-lookup"><span data-stu-id="746d5-291">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
>
> <span data-ttu-id="746d5-292">이 시나리오에서 위치에 대한 **모두** 설정을 보존 정책의 적용을 받지 않으려면 위치를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-292">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="746d5-293">또는 정책에서 제외할 제외 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-293">Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="746d5-294">보존 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="746d5-294">Updating retention policies</span></span>

<span data-ttu-id="746d5-295">다음 내용을 포함하는 보존 정책을 만들고 저장한 후에는 일부 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-295">Some settings can't be changed after a retention policy is created and saved, which include:</span></span>
- <span data-ttu-id="746d5-296">보존 기간 및 보존 기간의 시작 시기를 제외한 보존 정책 이름 및 보존 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-296">The retention policy name and the retention settings except the retention period and when to start the retention period.</span></span>

<span data-ttu-id="746d5-297">보존 정책을 편집하고 항목이 보존 정책의 원래 설정에 이미 적용되어 있는 경우 업데이트된 설정은 새로 식별된 항목 외에 이 항목에도 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-297">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="746d5-298">일반적으로 이 업데이트는 아주 간단하지만 며칠이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-298">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="746d5-299">Microsoft 365 위치에서 정책 복제가 완료되면 Microsoft 365 준수 센터의 보존 정책 상태가 **켜기(보류)** 에서 **켜기(성공)** 으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="746d5-299">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="746d5-300">변경 방지를 위한 정책 잠금</span><span class="sxs-lookup"><span data-stu-id="746d5-300">Locking the policy to prevent changes</span></span>

<span data-ttu-id="746d5-301">아무도 정책을 끄거나, 삭제하거나, 제한 수준을 낮출 수 없도록 하려면, [보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 보존 잠금 사용](retention-preservation-lock.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="746d5-301">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>
