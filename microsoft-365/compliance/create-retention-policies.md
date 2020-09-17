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
description: 보존 정책을 사용하면 사용자가 전자 메일, 문서 및 대화를 사용하여 생성하는 콘텐츠를 매우 효율적으로 유지 관리할 수 있습니다. 원하는 내용을 유지하고 원하지 않는 항목을 제거하세요.
ms.openlocfilehash: 8663da0a93bb4781af747d810200d4a2a777acb4
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948176"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="3b6e4-104">보존 정책 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="3b6e4-104">Create and configure retention policies</span></span>

><span data-ttu-id="3b6e4-105">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="3b6e4-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="3b6e4-106">콘텐츠를 보존할지, 삭제할지, 아니면 보존했다가 삭제할지를 사전에 결정하기 위해 보존 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-106">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span>

<span data-ttu-id="3b6e4-107">보존 정책을 사용하면 사이트 또는 사서함 수준에서 위치별로 콘텐츠의 보존 설정을 동일하게 할당하여 효율적으로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-107">A retention policy lets you do this very efficiently by assigning the same retention settings for content by location, at a site or mailbox level.</span></span> <span data-ttu-id="3b6e4-108">보존 정책 또는 보존 레이블을 사용해야 할지 확실하지 않다면 [보존 정책 및 보존 레이블](retention.md#retention-policies-and-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-108">If you're not sure whether to use a retention policy or a retention label, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="3b6e4-109">보존 정책과 보존이 작동하는 방식에 대한 자세한 내용은 [보존 정책과 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-109">For more information about retention policies and how retention works, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3b6e4-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="3b6e4-110">Before you begin</span></span>

<span data-ttu-id="3b6e4-111">조직의 전역 관리자는 보존 정책을 만들고 편집할 수 있는 모든 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-111">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="3b6e4-112">전역 관리자로 로그인하지 않은 경우 [보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-112">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="3b6e4-113">보존 정책 만들기 및 구성하기</span><span class="sxs-lookup"><span data-stu-id="3b6e4-113">Create and configure a retention policy</span></span>

<span data-ttu-id="3b6e4-114">보존 정책은 여러 위치를 지원할 수 있지만 지원되는 모든 위치를 포함하는 단일 보존 정책을 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-114">Although a retention policy can support multiple locations, you can't create a single retention policy that includes all the supported locations:</span></span>

- <span data-ttu-id="3b6e4-115">Exchange 전자 메일</span><span class="sxs-lookup"><span data-stu-id="3b6e4-115">Exchange email</span></span>
- <span data-ttu-id="3b6e4-116">SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="3b6e4-116">SharePoint site</span></span>
- <span data-ttu-id="3b6e4-117">OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="3b6e4-117">OneDrive accounts</span></span>
- <span data-ttu-id="3b6e4-118">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="3b6e4-118">Microsoft 365 groups</span></span>
- <span data-ttu-id="3b6e4-119">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="3b6e4-119">Skype for Business</span></span>
- <span data-ttu-id="3b6e4-120">Exchange 공용 폴더</span><span class="sxs-lookup"><span data-stu-id="3b6e4-120">Exchange public folders</span></span>
- <span data-ttu-id="3b6e4-121">Teams 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="3b6e4-121">Teams channel messages</span></span>
- <span data-ttu-id="3b6e4-122">Teams 채팅</span><span class="sxs-lookup"><span data-stu-id="3b6e4-122">Teams chats</span></span>

<span data-ttu-id="3b6e4-123">보존 정책을 만들 때 Teams 위치 중 하나를 선택하면 다른 위치는 자동으로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-123">When you select either of the Teams locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="3b6e4-124">따라서, 따라야 하는 지침은 Teams 위치를 포함해야 하는지에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-124">Therefore, the instructions to follow depend on whether you need to include the Teams locations:</span></span>

- [<span data-ttu-id="3b6e4-125">Teams 위치 보존 정책에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="3b6e4-125">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="3b6e4-126">Teams 이외의 위치 보존 정책에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="3b6e4-126">Instructions for a retention policy for locations other than Teams</span></span>](#retention-policy-for-locations-other-than-teams)

<span data-ttu-id="3b6e4-127">보존 정책이 두 개 이상이고 보존 레이블도 사용하는 경우에는 여러 보존 설정이 동일한 콘텐츠에 적용되는 경우의 결과를 이해하기 위해 [보존 원칙 또는 우선하는 항목](retention.md#the-principles-of-retention-or-what-takes-precedence)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-127">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="3b6e4-128">Teams 위치 보존 정책</span><span class="sxs-lookup"><span data-stu-id="3b6e4-128">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="3b6e4-129">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-129">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="3b6e4-130">**새 보존 정책**을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-130">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="3b6e4-131">**정책을 적용하기 위한 위치 선택** 페이지에서, Teams에 대한 하나 혹은 양쪽 위치를 선택합니다. **Teams 채널 메시지** 및 **Teams 채팅**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-131">For the **Choose locations to apply the policy** page, select one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>

   <span data-ttu-id="3b6e4-132">**Teams 채널 메시지**의 경우, 표준 채널이지만 [비공개 채널](https://docs.microsoft.com/microsoftteams/private-channels)의 메시지는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-132">For **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="3b6e4-133">현재 개인 채널은 보존 정책에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-133">Currently, private channels aren't supported by retention policies.</span></span>

   <span data-ttu-id="3b6e4-134">기본적으로 [모든 팀과 모든 사용자가 선택되어 있지만](#a-policy-that-applies-to-entire-locations), [**선택** 및 **배제** 옵션](#a-policy-with-specific-inclusions-or-exclusions)을 선택하여 이를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-134">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the [**Choose** and **Exclude** options](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

4. <span data-ttu-id="3b6e4-135">**콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-135">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

   <span data-ttu-id="3b6e4-136">삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-136">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="3b6e4-137">자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-137">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="3b6e4-138">마법사를 완료하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-138">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="3b6e4-139">Teams 보존 정책에 대한 자세한 내용은 Teams 설명서에서 [Microsoft Teams의 보존 정책](https://docs.microsoft.com/microsoftteams/retention-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-139">For more information about retention policies for Teams, see [Retention policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) from the Teams documentation.</span></span>

#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="3b6e4-140">Teams 지원에 필요한 추가 보존 정책</span><span class="sxs-lookup"><span data-stu-id="3b6e4-140">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="3b6e4-141">Teams는 채팅 및 채널 메시지 그 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-141">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="3b6e4-142">Microsoft 365 그룹에서 만든 팀(이전에는 Office 365 그룹)을 가진 경우 **Office 365 그룹** 위치를 사용하여 Microsoft 365 그룹을 포함하는 보존 정책을 추가적으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-142">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Office 365 groups** location.</span></span> <span data-ttu-id="3b6e4-143">이 보존 정책은 그룹의 사서함, 사이트 및 파일의 콘텐츠에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-143">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="3b6e4-144">Microsoft 365 그룹에 연결되어 있지 않은 팀 사이트가 있는 경우, Teams에서 파일을 보존하고 삭제하려면 **SharePoint 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-144">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="3b6e4-145">채팅에서 공유되는 파일은 해당 파일을 공유하는 사용자의 OneDrive 계정에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-145">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span>

- <span data-ttu-id="3b6e4-146">채널에 업로드된 파일은 해당 팀의 SharePoint 사이트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-146">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="3b6e4-147">특정 팀의 SharePoint 사이트 및 특정 팀 사용자의 OneDrive 계정을 선택하여 Microsoft 365 그룹에 연결되어 있지 않으면 해당 팀의 파일에 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-147">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="3b6e4-148">Microsoft 365 그룹, SharePoint 사이트 또는 OneDrive 계정에 적용되는 보존 정책은 해당 메시지가 삭제되기 전에 Teams 채팅 또는 채널 메시지에서 참조되는 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-148">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="3b6e4-149">이 시나리오에서는 파일이 Teams 메시지에 여전히 표시되지만 사용자가 파일을 선택하면 "파일을 찾을 수 없음" 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-149">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="3b6e4-150">이 동작은 보존 정책에만 국한된 것이 아니며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-150">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-locations-other-than-teams"></a><span data-ttu-id="3b6e4-151">Teams 이외의 위치 보존 정책</span><span class="sxs-lookup"><span data-stu-id="3b6e4-151">Retention policy for locations other than Teams</span></span>

1. <span data-ttu-id="3b6e4-152">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-152">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="3b6e4-153">**새 보존 정책**을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-153">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="3b6e4-154">**위치 선택** 페이지를 선택하려면 Teams 위치를 제외한 모든 위치를 토글로 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-154">For the **Choose locations** page, toggle on or off any of the locations except the locations for Teams.</span></span> <span data-ttu-id="3b6e4-155">각 위치에 대해 설정을 기본값으로 유지하여 [전체 위치에 정책을 적용](#a-policy-that-applies-to-entire-locations)하거나 [포함 및 제외를 지정](#a-policy-with-specific-inclusions-or-exclusions)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-155">For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

    <span data-ttu-id="3b6e4-156">위치 관련 정보:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-156">Information specific to locations:</span></span>
    - [<span data-ttu-id="3b6e4-157">Exchange 전자 메일 및 Exchange 공용 폴더</span><span class="sxs-lookup"><span data-stu-id="3b6e4-157">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="3b6e4-158">SharePoint 사이트 및 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="3b6e4-158">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="3b6e4-159">Office 365 그룹</span><span class="sxs-lookup"><span data-stu-id="3b6e4-159">Office 365 groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="3b6e4-160">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="3b6e4-160">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="3b6e4-161">**콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-161">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

    <span data-ttu-id="3b6e4-162">삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-162">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="3b6e4-163">자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-163">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="3b6e4-164">마법사를 완료하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-164">Complete the wizard to save your settings.</span></span>

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="3b6e4-165">Exchange 전자 메일 및 Exchange 공용 폴더에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="3b6e4-165">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="3b6e4-166">**Exchange 전자 메일** 위치는 사서함 수준에서 보존 설정을 적용하여 사용자의 전자 메일, 일정 및 기타 사서함 항목에 대한 보존을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-166">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="3b6e4-167">다음 메일 항목 포함: 첨부 파일, 작업 및 일정 항목이 끝나는 날짜, 메모가 포함된 메일 메시지(임시 보관함 포함)</span><span class="sxs-lookup"><span data-stu-id="3b6e4-167">The following mail items are included: Mail messages (includes drafts) with any attachments, tasks and calendar items when they have an end date, and notes.</span></span> <span data-ttu-id="3b6e4-168">종료 날짜가 없는 모든 작업 및 일정 항목은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-168">Contacts, and any tasks and calendar items that don't have an end date are not included.</span></span> <span data-ttu-id="3b6e4-169">Skype 및 Teams에 저장된 메시지와 같이 사서함에 저장된 다른 항목은 이 위치에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-169">Other items stored in a mailbox, such as Skype and Teams saved messages, aren't included with this location.</span></span> <span data-ttu-id="3b6e4-170">이러한 항목은 자체 보존 위치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-170">These items have their own retention locations.</span></span>

<span data-ttu-id="3b6e4-171">Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-171">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="3b6e4-172">이러한 사서함의 콘텐츠를 보존하려면 **Office 365 그룹** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-172">To retain content in these mailboxes, select the **Office 365 groups** location.</span></span>

<span data-ttu-id="3b6e4-173">**Exchange 공용 폴더** 위치는 보존 설정을 모든 공용 폴더에 적용하며 폴더 또는 사서함 수준에서 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-173">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="3b6e4-174">SharePoint 사이트 및 OneDrive 계정에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="3b6e4-174">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="3b6e4-175">**SharePoint 사이트** 위치를 선택할 때 보존 정책을 사용하여 SharePoint 커뮤니케이션 사이트, Office 365 그룹으로 연결되지 않는 팀 사이트 및 클래식 사이트에서 문서를 보존하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-175">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Office 365 groups, and classic sites.</span></span> <span data-ttu-id="3b6e4-176">Office 365 그룹에서 연결된 팀 사이트는 이 옵션에서 지원되지 않으며 대신 해당 그룹의 사서함, 사이트 및 파일에 있는 콘텐츠에 적용되는 **Office 365 그룹** 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-176">Team sites connected by Office 365 groups aren't supported with this option and instead, use the **Office 365 groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="3b6e4-177">보존 정책이 사이트 수준에서 적용되더라도 보존 설정은 문서에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-177">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="3b6e4-178">보존 설정은 사이트 내의 라이브러리, 목록 및 폴더를 포함하는 구성 구조에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-178">Retention settings do not apply to the organizing structures that include libraries, lists, and folders within the site.</span></span>

<span data-ttu-id="3b6e4-179">SharePoint 사이트 또는 OneDrive 계정의 위치를 지정하는 경우, 사이트에 액세스할 수 있는 권한이 필요하지 않으며 **위치 편집** 페이지에서 URL을 지정하는 시점에 유효성 검사가 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-179">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="3b6e4-180">그러나 SharePoint 사이트를 색인화해야 하며 마법사 종료 시 지정한 사이트가 존재하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-180">However, the SharePoint sites must be indexed and the sites that you specify are checked that they exist at the end of the wizard.</span></span>

<span data-ttu-id="3b6e4-181">이 검사에 실패하는 경우, 입력한 URL에 대한 유효성 검사에 실패했다는 메시지가 표시되고 유효성 검사가 통과한 후에 마법사에서 보존 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-181">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="3b6e4-182">이 메시지가 표시되는 경우, 마법사에서 돌아가서 URL을 변경하거나 보존 정책에서 사이트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-182">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="3b6e4-183">포함하거나 제외할 개별 OneDrive 계정을 지정하려면 URL은 `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com` 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-183">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="3b6e4-184">예를 들어, "rsimone"라는 사용자 이름을 보유한 Contoso 테넌트에 있는 사용자의 경우: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="3b6e4-184">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="3b6e4-185">테넌트의 구문을 확인하고 사용자 URL을 확인하려면, [조직에 있는 모든 사용자 OneDrive URL 목록 가져오기](https://docs.microsoft.com/onedrive/list-onedrive-urls)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-185">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="3b6e4-186">Microsoft 365 그룹에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="3b6e4-186">Configuration information for Microsoft 365 groups</span></span>

<span data-ttu-id="3b6e4-187">Microsoft 365 그룹(이전 이름: Office 365 그룹)의 콘텐츠를 보존하거나 삭제하려면 **Office 365 그룹** 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-187">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Office 365 groups** location.</span></span> <span data-ttu-id="3b6e4-188">Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-188">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="3b6e4-189">또한 **Exchange 전자 메일** 위치에서 처음에 포함하거나 제외할 그룹 사서함을 지정할 수 있지만 보존 정책을 저장하려고 하면 "RemoteGroupMailbox"가 Exchange 위치에 대해 올바른 선택이 아니라는 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-189">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="3b6e4-190">만약 팀 사이트가 그룹이 만들어 졌을 때 선택되었거나 혹은 나중에 그룹에 추가 된 경우, 그룹 사서함 및 팀 사이트를 포함한 Microsoft 365 그룹에 적용되는 보존 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-190">A retention policy applied to a Microsoft 365 group includes the group mailbox and teams site, if a teams site was selected at the time the group was created or later added to the group.</span></span> <span data-ttu-id="3b6e4-191">팀 사이트에 저장된 파일은 이 위치에 포함되지만 자신의 보존 정책 위치가 있는 Teams 채팅 혹은 Teams 채널 메시지는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-191">Files stored in the teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="3b6e4-192">비즈니스용 Skype에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="3b6e4-192">Configuration information for Skype for Business</span></span>

<span data-ttu-id="3b6e4-193">Exchange 전자 메일과 달리, Skype 위치의 상태는 간단히 설정으로 전환하여 모든 사용자를 자동으로 포함할 수 없습니다. 그렇지만 해당 위치를 켜면 해당 대화를 보존하려는 사용자를 수동으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-193">Unlike Exchange email, you can't toggle the status of the Skype location on to automatically include all users, but when you turn on that location, you must then manually choose the users whose conversations you want to retain:</span></span>

![보존 정책을 위한 Skype 위치 선택](../media/skype-location-retention-policies.png)

<span data-ttu-id="3b6e4-195">**사용자 선택**을 선택하면 **모두 선택** 상자를 선택하여 모든 사용자를 빠르게 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-195">When you select **Choose user**, you can quickly include all users by selecting the **Select all** box.</span></span> <span data-ttu-id="3b6e4-196">그러나 각 사용자가 정책의 특정 포함사항으로 간주된다는 점을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-196">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="3b6e4-197">따라서 **모두 선택** 상자를 선택하여 1,000명의 사용자를 포함하는 경우, 포함할 1,000명의 사용자를 수동으로 선택한 것과 같으며 이는 비즈니스용 Skype에 대해 지원되는 최대를 선택하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-197">So if you include 1,000 users by selecting the **Select all** box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="3b6e4-198">Outlook 폴더인 **대화 내용**은 Skype 아카이빙은 관계가 없는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-198">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="3b6e4-199">**대화 내용**은 최종 사용자가 끌 수 있지만, Skype 아카이빙은 사용자는 액세스할 수 없고 eDiscovery에서만 액세스 가능한 숨김 폴더에 Skype 대화 사본을 저장하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-199">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="3b6e4-200">콘텐츠를 보존 및 삭제하기 위한 설정</span><span class="sxs-lookup"><span data-stu-id="3b6e4-200">Settings for retaining and deleting content</span></span>

<span data-ttu-id="3b6e4-201">보존 정책에서 콘텐츠를 보존하고 삭제하기 위한 설정을 선택하면 보존 정책에 지정된 기간 동안 다음 구성 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-201">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="3b6e4-202">보존 전용</span><span class="sxs-lookup"><span data-stu-id="3b6e4-202">Retain-only</span></span>

    <span data-ttu-id="3b6e4-203">이 구성에서는 **특정 기간에 대한 항목을 보존**을 선택하고 **보존 기간의 종료 시, 아무 작업도 수행하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-203">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**.</span></span> <span data-ttu-id="3b6e4-204">또는 **항목을 영구적으로 보존**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-204">Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="3b6e4-205">보존 후 삭제</span><span class="sxs-lookup"><span data-stu-id="3b6e4-205">Retain and then delete</span></span>

    <span data-ttu-id="3b6e4-206">이 구성에서는 **특정 기간에 대한 항목을 보존**을 선택하고 **보존 기간의 종료 시, 항목을 자동으로 삭제합니다**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-206">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="3b6e4-207">삭제 전용</span><span class="sxs-lookup"><span data-stu-id="3b6e4-207">Delete-only</span></span>

    <span data-ttu-id="3b6e4-208">이 구성에서는 **특정 기간에 도달했을 때만 항목 삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-208">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="3b6e4-209">특정 기간 동안 콘텐츠 보존</span><span class="sxs-lookup"><span data-stu-id="3b6e4-209">Retaining content for a specific period of time</span></span>

<span data-ttu-id="3b6e4-210">보존 정책을 구성하면 항목을 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-210">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years.</span></span> <span data-ttu-id="3b6e4-211">또는 항목이 영구적으로 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-211">Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="3b6e4-212">보존 정책을 구성하면 콘텐츠를 영구적으로 또는 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-212">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="3b6e4-213">콘텐츠 보존 기간은 보존 정책이 적용된 시점이 아닌 콘텐츠 생성 시점을 기준으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-213">The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span>

<span data-ttu-id="3b6e4-214">보존 기간이 시작되는 경우 또한 콘텐츠를 언제 만들어졌을지 또는 콘텐츠가 마지막으로 수정된 경우에는 파일 및 SharePoint, OneDrive 및 Office 365 위치에 대해서만 지원되었는지의 경우를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-214">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Office 365 locations, when the content was last modified.</span></span>

<span data-ttu-id="3b6e4-215">예제:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-215">Examples:</span></span>

- <span data-ttu-id="3b6e4-216">SharePoint: 콘텐츠가 마지막으로 수정된 후 7년 동안 사이트 모음에 항목을 유지하고 해당 사이트 모음에 있는 문서가 6년 내에 수정되지 않은 경우, 문서가 수정되지 않으면 다른 한 해에만 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-216">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="3b6e4-217">문서를 다시 편집하면 문서 사용 기간은 마지막으로 수정한 날부터 계산되고 앞으로 7년 동안 더 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-217">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>

- <span data-ttu-id="3b6e4-218">Exchange: 사서함의 항목을 7년 동안 보존하려고 하고 메시지가 6년 전에 발송되었다면, 메시지는 1년 동안만 더 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-218">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="3b6e4-219">Exchange 항목의 경우 해당 기간은 받는 전자 메일의 받은 날짜 또는 보내는 전자 메일에 대해 보낸 날짜를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-219">For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="3b6e4-220">항목을 최종 수정된 시점을 기준으로 보존하는 것은 OneDrive 및 SharePoint의 사이트 콘텐츠에만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-220">Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>

<span data-ttu-id="3b6e4-221">보존 기간이 끝나면 콘텐츠를 영구적으로 삭제할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-221">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>

![보존 설정 페이지](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="3b6e4-223">특정 사용 기간보다 오래된 콘텐츠 삭제</span><span class="sxs-lookup"><span data-stu-id="3b6e4-223">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="3b6e4-224">보존 정책은 항목을 보존했다가 삭제하거나, 혹은 보존하지 않고 오래된 콘텐츠를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-224">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>

<span data-ttu-id="3b6e4-225">두 경우 모두, 보존 정책이 항목을 삭제할 경우 보존 정책에 대해 지정된 기간은 정책이 할당된 시점이 아니라 콘텐츠가 만들어졌거나 수정된 이후부터 계산된다는 사실에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-225">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="3b6e4-226">따라서 처음으로 사이트에 보존 정책을 할당하기 전에 그리고 특히 정책이 항목을 삭제할 시, 먼저 기존 콘텐츠의 사용 기간과 정책이 기존 콘텐츠에 어떤 영향을 줄 수 있는지 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-226">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content.</span></span> <span data-ttu-id="3b6e4-227">또한 새 정책을 할당하기 전에 사이트 소유자에게 미리 알려, 가능한 영향을 평가할 시간을 줄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-227">You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="3b6e4-228">전체 위치에 적용되는 정책</span><span class="sxs-lookup"><span data-stu-id="3b6e4-228">A policy that applies to entire locations</span></span>

<span data-ttu-id="3b6e4-229">위치를 선택하는 경우 비즈니스용 Skype를 제외하고, 위치의 상태가 **On**인 경우, 기본 설정은 **모두**가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-229">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>

<span data-ttu-id="3b6e4-230">보존 정책이 전체의 위치 조합에 적용되는 경우 정책에 포함할 수 있는 수혜자, 사이트, 계정, 그룹 등에 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-230">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups etc that the policy can include.</span></span>

<span data-ttu-id="3b6e4-231">예를 들어, 정책에 모든 Exchange 전자 메일과 모든 SharePoint 사이트가 모두 포함된다면, 개수와 상관없이 모든 사이트와 수혜자가 포함될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-231">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many.</span></span> <span data-ttu-id="3b6e4-232">또한 Exchange의 경우 정책이 적용된 후 만들어진 모든 새 사서함은 자동으로 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-232">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="3b6e4-233">특정 포함 또는 제외가 적용된 정책</span><span class="sxs-lookup"><span data-stu-id="3b6e4-233">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="3b6e4-234">특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트에 보존 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-234">You can also apply a retention policy to specific users, specific Microsoft 365 groups, or specific sites.</span></span> <span data-ttu-id="3b6e4-235">이는 해당 위치의 **상태**를 **켠**후 다음 링크를 사용하여 특정 사용자, Microsoft 365 그룹 또는 사이트를 포함하거나 배제하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-235">To do so, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span>

<span data-ttu-id="3b6e4-236">그러나 이 구성을 사용하는 경우 보존 정책에는 다음과 같은 1000개의 특정 개체를 포함하거나 제외하는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-236">However, using this configuration, there are some limits when your retention policy includes or excludes over 1,000 specific objects:</span></span>

- <span data-ttu-id="3b6e4-237">보존 정책의 최대 수:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-237">Maximum numbers for the retention policy:</span></span>
  - <span data-ttu-id="3b6e4-238">1,000개의 사서함</span><span class="sxs-lookup"><span data-stu-id="3b6e4-238">1,000 mailboxes</span></span>
  - <span data-ttu-id="3b6e4-239">1,000개의 Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="3b6e4-239">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="3b6e4-240">Teams 비공개 채팅에 참여하는 1,000명의 사용자</span><span class="sxs-lookup"><span data-stu-id="3b6e4-240">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="3b6e4-241">100개의 사이트(OneDrive 또는 SharePoint)</span><span class="sxs-lookup"><span data-stu-id="3b6e4-241">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="3b6e4-242">테넌트에 대해 지원되는 최대 정책 수는 10,000입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-242">There is a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="3b6e4-243">이러한 항목에는 보존 정책, 보존 레이블 정책, 자동 적용 보존 정책이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-243">These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="3b6e4-244">보존 정책에 이러한 제한이 적용되는 경우 전체 위치에 적용되는 구성 옵션을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-244">If your retention policies are likely to be subject to these limitations, choose the configuration options that apply to entire locations.</span></span>

> [!WARNING]
> <span data-ttu-id="3b6e4-245">마지막 구성을 포함했다가 제거하면 해당 위치에 대해 **모두**로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-245">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="3b6e4-246">정책을 저장하기 전에 원하는 구성인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-246">Make sure this is the configuration that you intend before you save the policy.</span></span>
>
> <span data-ttu-id="3b6e4-247">예를 들어 데이터를 삭제하도록 구성된 보존 정책에 포함할 SharePoint 사이트 하나를 지정한 다음 단일 사이트를 제거하면 기본적으로 모든 SharePoint 사이트는 데이터를 영구적으로 삭제하는 보존 정책의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-247">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="3b6e4-248">Exchange 수신인, OneDrive 계정, 팀 채팅 사용자 등의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-248">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
>
> <span data-ttu-id="3b6e4-249">이 시나리오에서 위치에 대한 **모두** 설정을 보존 정책의 적용을 받지 않으려면 위치를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-249">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="3b6e4-250">또는 정책에서 제외할 제외 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-250">Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="3b6e4-251">보존 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="3b6e4-251">Updating retention policies</span></span>

<span data-ttu-id="3b6e4-252">보존 정책을 편집하고 항목이 보존 정책의 원래 설정에 이미 적용되어 있는 경우 업데이트된 설정은 새로 식별된 항목 외에 이 항목에도 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-252">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="3b6e4-253">일반적으로 이 업데이트는 아주 간단하지만 며칠이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-253">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="3b6e4-254">Microsoft 365 위치에서 정책 복제가 완료되면 Microsoft 365 준수 센터의 보존 정책 상태가 **켜기(보류)** 에서 **켜기(성공)** 으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-254">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="3b6e4-255">PowerShell을 사용하여 보존 정책 잠금</span><span class="sxs-lookup"><span data-stu-id="3b6e4-255">Lock a retention policy by using PowerShell</span></span>

<span data-ttu-id="3b6e4-256">규정 요구 사항을 준수하기 위해 [보존 잠금](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)을 사용해야 하는 경우 PowerShell을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-256">You must use PowerShell if you need to use [Preservation Lock](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements) to comply with regulatory requirements.</span></span> <span data-ttu-id="3b6e4-257">유지 잠금이 적용된 후에는 관리자가 보존 정책을 사용하지 않도록 설정하거나 삭제할 수 없기 때문에, 이 기능을 사용하도록 설정하는 것은 잘못된 구성으로부터 보호하는 UI에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-257">Because administrators can't disable or delete a retention policy after a preservation lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="3b6e4-258">모든 구성 지원 보존 잠금이 있는 모든 보존 정책.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-258">All retention policies with any configuration support Preservation Lock.</span></span> <span data-ttu-id="3b6e4-259">그러나 뒤에 나오는 PowerShell 명령을 사용하는 경우 **작업부하** 매개변수에는 정책에 구성된 실제 작업 부하를 반영하는 것이 아니라 **Exchange, SharePoint, OneDriveForBusines, Skype, ModernGroup**을 표시하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-259">However, when you use the PowerShell commands that follow, you'll notice that the **Workload** parameter always displays **Exchange, SharePoint, OneDriveForBusines, Skype, ModernGroup** rather than reflect the actual workloads configured in the policy.</span></span> <span data-ttu-id="3b6e4-260">이는 표시 문제일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-260">This is a display issue only.</span></span>

1. <span data-ttu-id="3b6e4-261">[보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-261">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="3b6e4-262">[RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)를 실행하여 잠글 정책의 이름을 나열하고 보존 정책을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-262">List your retention policies and find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="3b6e4-263">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="3b6e4-263">For example:</span></span>

   ![PowerShell의 보존 정책 목록](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="3b6e4-265">보존 정책에 보존 잠금을 설정하려면 [Set-RetentionCompliancePolicy]( ) cmdlet을 보존 정책 이름으로 실행하고 *RestrictiveRetention* 매개변수를 true로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-265">To place a Preservation Lock on a retention policy, run the [Set-RetentionCompliancePolicy]( ) cmdlet with the name of the retention policy, and the *RestrictiveRetention* parameter set to true:</span></span>

    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```

    <span data-ttu-id="3b6e4-266">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="3b6e4-266">For example:</span></span>

    ![PowerShell의 RestrictiveRetention 매개 변수](../media/retention-policy-preservation-lock-restrictiveretention.PNG)

     <span data-ttu-id="3b6e4-268">메시지가 표시되면 이 구성과 함께 제공되는 제한 사항을 읽고 **Y**를 입력하여 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-268">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>

   ![PowerShell에서 보존 정책 잠금을 원하는지 확인하는 메시지](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="3b6e4-270">이제 보존 정책에 보존 잠금이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-270">A Preservation Lock is now placed on the retention policy.</span></span> <span data-ttu-id="3b6e4-271">확인하려면 `Get-RetentionCompliancePolicy` 다시 실행 하지만, 보존 정책 이름을 지정하고 정책 매개변수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-271">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the retention policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="3b6e4-272">**RestrictiveRetention**이 **True**로 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-272">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="3b6e4-273">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="3b6e4-273">For example:</span></span>

![PowerShell에 모든 매개 변수와 함께 표시된 잠긴 정책](../media/retention-policy-preservation-lock-locked-policy.PNG)
