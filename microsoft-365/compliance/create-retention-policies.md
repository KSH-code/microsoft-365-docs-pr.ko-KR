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
ms.openlocfilehash: 40e405a8ab3ac2159b9a3c5ab8f633bb690d5c24
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384556"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="c7386-104">보존 정책 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="c7386-104">Create and configure retention policies</span></span>

><span data-ttu-id="c7386-105">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="c7386-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c7386-106">콘텐츠를 보존할지, 삭제할지, 아니면 보존했다가 삭제할지를 사전에 결정하기 위해 보존 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-106">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span>

<span data-ttu-id="c7386-107">보존 정책을 사용하면 사이트 또는 사서함 수준에서 위치별로 콘텐츠의 보존 설정을 동일하게 할당하여 효율적으로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-107">A retention policy lets you do this very efficiently by assigning the same retention settings for content by location, at a site or mailbox level.</span></span> <span data-ttu-id="c7386-108">보존 정책 또는 보존 레이블을 사용해야 할지 확실하지 않다면 [보존 정책 및 보존 레이블](retention.md#retention-policies-and-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-108">If you're not sure whether to use a retention policy or a retention label, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="c7386-109">보존 정책과 보존이 작동하는 방식에 대한 자세한 내용은 [보존 정책과 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-109">For more information about retention policies and how retention works, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c7386-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c7386-110">Before you begin</span></span>

<span data-ttu-id="c7386-111">조직의 전역 관리자는 보존 정책을 만들고 편집할 수 있는 모든 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-111">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="c7386-112">전역 관리자로 로그인하지 않은 경우 [보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-112">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="c7386-113">보존 정책 만들기 및 구성하기</span><span class="sxs-lookup"><span data-stu-id="c7386-113">Create and configure a retention policy</span></span>

<span data-ttu-id="c7386-114">보존 정책은 여러 위치를 지원할 수 있지만 지원되는 모든 위치를 포함하는 단일 보존 정책을 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-114">Although a retention policy can support multiple locations, you can't create a single retention policy that includes all the supported locations:</span></span>

- <span data-ttu-id="c7386-115">Exchange 전자 메일</span><span class="sxs-lookup"><span data-stu-id="c7386-115">Exchange email</span></span>
- <span data-ttu-id="c7386-116">SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="c7386-116">SharePoint site</span></span>
- <span data-ttu-id="c7386-117">OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="c7386-117">OneDrive accounts</span></span>
- <span data-ttu-id="c7386-118">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="c7386-118">Microsoft 365 groups</span></span>
- <span data-ttu-id="c7386-119">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="c7386-119">Skype for Business</span></span>
- <span data-ttu-id="c7386-120">Exchange 공용 폴더</span><span class="sxs-lookup"><span data-stu-id="c7386-120">Exchange public folders</span></span>
- <span data-ttu-id="c7386-121">Teams 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="c7386-121">Teams channel messages</span></span>
- <span data-ttu-id="c7386-122">Teams 채팅</span><span class="sxs-lookup"><span data-stu-id="c7386-122">Teams chats</span></span>
- <span data-ttu-id="c7386-123">Yammer 커뮤니티 메시지</span><span class="sxs-lookup"><span data-stu-id="c7386-123">Yammer community messages</span></span>
- <span data-ttu-id="c7386-124">Yammer 개인 메시지</span><span class="sxs-lookup"><span data-stu-id="c7386-124">Yammer private messages</span></span>

<span data-ttu-id="c7386-125">보존 정책을 생성할 때 Teams 또는 Yammer 위치를 선택하면 다른 위치는 자동으로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-125">If you select the Teams or Yammer locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="c7386-126">따라서, 따라야 할 지침은 Teams 또는 Yammer 위치를 포함해야 하는지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-126">Therefore, the instructions to follow depend on whether you need to include the Teams or Yammer locations:</span></span>

- <span data-ttu-id="c7386-127">[Teams 위치](#retention-policy-for-teams-locations)에 대한 보존 정책에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="c7386-127">[Instructions for a retention policy for Teams locations](#retention-policy-for-teams-locations)</span></span>
- [<span data-ttu-id="c7386-128">Yammer 위치에 대한 보존 정책에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="c7386-128">Instructions for a retention policy for Yammer locations</span></span>](#retention-policy-for-yammer-locations)
- <span data-ttu-id="c7386-129">[Teams 및 Yammer](#retention-policy-for-locations-other-than-teams-and-yammer) 이외의 위치에 대한 보존 정책에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="c7386-129">[Instructions for a retention policy for locations other than Teams and Yammer](#retention-policy-for-locations-other-than-teams-and-yammer)</span></span>

<span data-ttu-id="c7386-130">보존 정책이 두 개 이상이고 보존 레이블도 사용하는 경우에는 여러 보존 설정이 동일한 콘텐츠에 적용되는 경우의 결과를 이해하기 위해 [보존 원칙 또는 우선하는 항목](retention.md#the-principles-of-retention-or-what-takes-precedence)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-130">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="c7386-131">Teams 위치 보존 정책</span><span class="sxs-lookup"><span data-stu-id="c7386-131">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="c7386-132">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-132">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="c7386-133">**새 보존 정책**을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-133">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="c7386-134">**정책을 적용하기 위한 위치 선택** 페이지에서, Teams에 대한 하나 혹은 양쪽 위치를 선택합니다. **Teams 채널 메시지** 및 **Teams 채팅**.</span><span class="sxs-lookup"><span data-stu-id="c7386-134">For the **Choose locations to apply the policy** page, select one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>

   <span data-ttu-id="c7386-135">**Teams 채널 메시지**의 경우, 표준 채널이지만 [비공개 채널](https://docs.microsoft.com/microsoftteams/private-channels)의 메시지는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-135">For **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="c7386-136">현재 개인 채널은 보존 정책에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-136">Currently, private channels aren't supported by retention policies.</span></span>

   <span data-ttu-id="c7386-137">기본적으로 [모든 팀과 모든 사용자가 선택되어 있지만](#a-policy-that-applies-to-entire-locations), [**선택** 및 **배제** 옵션](#a-policy-with-specific-inclusions-or-exclusions)을 선택하여 이를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-137">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the [**Choose** and **Exclude** options](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

4. <span data-ttu-id="c7386-138">**콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-138">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

   <span data-ttu-id="c7386-139">삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-139">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="c7386-140">자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-140">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="c7386-141">마법사를 완료하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-141">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="c7386-142">Teams 보존 정책에 대한 자세한 내용은 Teams 설명서에서 [Microsoft Teams의 보존 정책](https://docs.microsoft.com/microsoftteams/retention-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-142">For more information about retention policies for Teams, see [Retention policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) from the Teams documentation.</span></span>

#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="c7386-143">Teams 지원에 필요한 추가 보존 정책</span><span class="sxs-lookup"><span data-stu-id="c7386-143">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="c7386-144">Teams는 채팅 및 채널 메시지 그 이상</span><span class="sxs-lookup"><span data-stu-id="c7386-144">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="c7386-145">Microsoft 365 그룹에서 만든 팀(이전에는 Office 365 그룹)을 가진 경우 **Office 365 그룹** 위치를 사용하여 Microsoft 365 그룹을 포함하는 보존 정책을 추가적으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-145">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Office 365 groups** location.</span></span> <span data-ttu-id="c7386-146">이 보존 정책은 그룹의 사서함, 사이트 및 파일의 콘텐츠에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-146">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="c7386-147">Microsoft 365 그룹에 연결되어 있지 않은 팀 사이트가 있는 경우, Teams에서 파일을 보존하고 삭제하려면 **SharePoint 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-147">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="c7386-148">채팅에서 공유되는 파일은 해당 파일을 공유하는 사용자의 OneDrive 계정에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-148">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span>

- <span data-ttu-id="c7386-149">채널에 업로드된 파일은 해당 팀의 SharePoint 사이트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-149">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="c7386-150">특정 팀의 SharePoint 사이트 및 특정 팀 사용자의 OneDrive 계정을 선택하여 Microsoft 365 그룹에 연결되어 있지 않으면 해당 팀의 파일에 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-150">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="c7386-151">Microsoft 365 그룹, SharePoint 사이트 또는 OneDrive 계정에 적용되는 보존 정책은 해당 메시지가 삭제되기 전에 Teams 채팅 또는 채널 메시지에서 참조되는 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-151">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="c7386-152">이 시나리오에서는 파일이 Teams 메시지에 여전히 표시되지만 사용자가 파일을 선택하면 "파일을 찾을 수 없음" 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-152">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="c7386-153">이 동작은 보존 정책에만 국한된 것이 아니며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-153">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-yammer-locations"></a><span data-ttu-id="c7386-154">Yammer 위치에 대한 보존 정책</span><span class="sxs-lookup"><span data-stu-id="c7386-154">Retention policy for Yammer locations</span></span>

> [!NOTE]
> <span data-ttu-id="c7386-155">Yammer에 대한 보존 정책이 미리 보기에서 롤아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-155">Retention policies for Yammer are rolling out in preview.</span></span> <span data-ttu-id="c7386-156">아직 Yammer의 새 위치가 보이지 않으면 며칠 후에 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-156">If you don't yet see the new locations for Yammer, try again in a few days.</span></span>
>
> <span data-ttu-id="c7386-157">이 기능을 사용하려면 Yammer 네트워크가 하이브리드 모드가 아니라 [기본 모드](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-157">To use this feature, your Yammer network must be [Native Mode](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode), not Hybrid Mode.</span></span>

1. <span data-ttu-id="c7386-158">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-158">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="c7386-159">**새 보존 정책**을 선택하여 새 보존 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-159">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="c7386-160">**콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-160">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="c7386-161">삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-161">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="c7386-162">자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-162">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
    <span data-ttu-id="c7386-163">이 옵션은 Yammer 위치에 지원되지 않으므로 **고급 보존 설정 사용**을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-163">Do not select **Use advanced retention settings** because this option isn't supported for Yammer locations.</span></span> 

4. <span data-ttu-id="c7386-164">**위치 선택** 페이지에 대해 **특정 위치 선택**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-164">For the **Choose locations** page, select **Let me choose specific locations**.</span></span> <span data-ttu-id="c7386-165">그런 다음 Yammer에 대한 위치 중 하나 또는 둘 모두를 전환합니다. **Yammer 커뮤니티 메시지** 및 **Yammer 개인 메시지**.</span><span class="sxs-lookup"><span data-stu-id="c7386-165">Then toggle on one or both of the locations for Yammer: **Yammer community message** and **Yammer private messages**.</span></span>
    
    <span data-ttu-id="c7386-166">기본적으로 모든 커뮤니티와 사용자가 선택되지만 포함하거나 제외할 커뮤니티와 사용자를 지정하여 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-166">By default, all communities and users are selected, but you can refine this by specifying communities and users to be included or excluded.</span></span>
    
    <span data-ttu-id="c7386-167">Yammer 개인 메시지의 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-167">For Yammer private messages:</span></span> 
    - <span data-ttu-id="c7386-168">기본값 **모두**를 그대로 두면 Azure B2B 게스트 사용자가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-168">If you leave the default at **All**, Azure B2B guest users are not included.</span></span> 
    - <span data-ttu-id="c7386-169">**사용자 선택**을 선택한 경우, 계정을 알고 있는 외부 사용자에게 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-169">If you select **Choose user**, you can apply a retention policy to external users if you know their account.</span></span>

5. <span data-ttu-id="c7386-170">마법사를 완료하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-170">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="c7386-171">Yammer용 보존 정책이 작동하는 방식에 대한 자세한 내용은 [Yammer용 보존 정보](retention-policies-yammer.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-171">For more information about how retention policies work for Yammer, see [Learn about retention for Yammer](retention-policies-yammer.md).</span></span>

#### <a name="additional-retention-policies-needed-to-support-yammer"></a><span data-ttu-id="c7386-172">Yammer를 지원하려면 추가 보존 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-172">Additional retention policies needed to support Yammer</span></span>

<span data-ttu-id="c7386-173">Yammer는 단지 커뮤니티 메시지와 비공개 메시지 그 이상의 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-173">Yammer is more than just community messages and private messages.</span></span> <span data-ttu-id="c7386-174">Yammer 네트워크의 전자 메일 메시지를 유지 및 삭제하려면 **Office 365 그룹** 위치를 사용하여 Yammer에 사용되는 Microsoft 365 그룹을 포함하는 추가 보존 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-174">To retain and delete email messages for your Yammer network, configure an additional retention policy that includes any Microsoft 365 groups that are used for Yammer, by using the **Office 365 groups** location.</span></span> 

<span data-ttu-id="c7386-175">Yammer에 저장된 파일을 유지 및 삭제하려면 **SharePoint 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-175">To retain and delete files that are stored in Yammer, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations:</span></span>

- <span data-ttu-id="c7386-176">개인 메시지에서 공유되는 파일은 파일을 공유한 사용자의 OneDrive 계정에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-176">Files that are shared in private messages are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="c7386-177">커뮤니티에 업로드된 파일은 Yammer 커뮤니티의 SharePoint 사이트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-177">Files that are uploaded to communities are stored in the SharePoint site for the Yammer community.</span></span>

<span data-ttu-id="c7386-178">SharePoint 사이트 또는 OneDrive 계정에 적용된 보존 정책은 해당 메시지가 삭제되기 전에 Yammer 메시지에 참조된 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-178">It's possible that a retention policy that's applied to SharePoint sites or OneDrive accounts could delete a file that's referenced in a Yammer message before those messages get deleted.</span></span> <span data-ttu-id="c7386-179">이 시나리오에서는 파일이 Yammer 메시지에 여전히 표시되지만 사용자가 파일을 선택하면 "파일을 찾을 수 없음" 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-179">In this scenario, the file still displays in the Yammer message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="c7386-180">이러한 동작은 보존 정책에만 국한되지 않으며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-180">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a><span data-ttu-id="c7386-181">Teams 및 Yammer 이외의 위치에 대한 보존 정책</span><span class="sxs-lookup"><span data-stu-id="c7386-181">Retention policy for locations other than Teams and Yammer</span></span>

<span data-ttu-id="c7386-182">이러한 서비스에 적용되는 보존 정책에 대해 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-182">Use the following instructions for retention policies that apply to any of these services:</span></span>

- <span data-ttu-id="c7386-183">Exchange: 전자 메일 및 공용 폴더</span><span class="sxs-lookup"><span data-stu-id="c7386-183">Exchange: Email and public folders</span></span>
- <span data-ttu-id="c7386-184">SharePoint: 사이트</span><span class="sxs-lookup"><span data-stu-id="c7386-184">SharePoint: Sites</span></span>
- <span data-ttu-id="c7386-185">OneDrive: 계정</span><span class="sxs-lookup"><span data-stu-id="c7386-185">OneDrive: Accounts</span></span>
- <span data-ttu-id="c7386-186">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="c7386-186">Microsoft 365 groups</span></span>
- <span data-ttu-id="c7386-187">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="c7386-187">Skype for Business</span></span>

1. <span data-ttu-id="c7386-188">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-188">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="c7386-189">**새 보존 정책**을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-189">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="c7386-190">**위치 선택** 페이지를 선택하려면 Teams 위치를 제외한 모든 위치를 토글로 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-190">For the **Choose locations** page, toggle on or off any of the locations except the locations for Teams.</span></span> <span data-ttu-id="c7386-191">각 위치에 대해 설정을 기본값으로 유지하여 [전체 위치에 정책을 적용](#a-policy-that-applies-to-entire-locations)하거나 [포함 및 제외를 지정](#a-policy-with-specific-inclusions-or-exclusions)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-191">For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

    <span data-ttu-id="c7386-192">위치 관련 정보:</span><span class="sxs-lookup"><span data-stu-id="c7386-192">Information specific to locations:</span></span>
    - [<span data-ttu-id="c7386-193">Exchange 전자 메일 및 Exchange 공용 폴더</span><span class="sxs-lookup"><span data-stu-id="c7386-193">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="c7386-194">SharePoint 사이트 및 OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="c7386-194">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="c7386-195">Office 365 그룹</span><span class="sxs-lookup"><span data-stu-id="c7386-195">Office 365 groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="c7386-196">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="c7386-196">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="c7386-197">**콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-197">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

    <span data-ttu-id="c7386-198">삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-198">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="c7386-199">자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-199">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="c7386-200">마법사를 완료하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-200">Complete the wizard to save your settings.</span></span>

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="c7386-201">Exchange 전자 메일 및 Exchange 공용 폴더에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="c7386-201">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="c7386-202">**Exchange 전자 메일** 위치는 사서함 수준에서 보존 설정을 적용하여 사용자의 전자 메일, 일정 및 기타 사서함 항목에 대한 보존을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-202">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="c7386-203">다음 메일 항목 포함: 첨부 파일, 작업 및 일정 항목이 끝나는 날짜, 메모가 포함된 메일 메시지(임시 보관함 포함)</span><span class="sxs-lookup"><span data-stu-id="c7386-203">The following mail items are included: Mail messages (includes drafts) with any attachments, tasks and calendar items when they have an end date, and notes.</span></span> <span data-ttu-id="c7386-204">종료 날짜가 없는 모든 작업 및 일정 항목은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-204">Contacts, and any tasks and calendar items that don't have an end date are not included.</span></span> <span data-ttu-id="c7386-205">Skype 및 Teams에 저장된 메시지와 같이 사서함에 저장된 다른 항목은 이 위치에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-205">Other items stored in a mailbox, such as Skype and Teams saved messages, aren't included with this location.</span></span> <span data-ttu-id="c7386-206">이러한 항목은 자체 보존 위치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-206">These items have their own retention locations.</span></span>

<span data-ttu-id="c7386-207">Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-207">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="c7386-208">이러한 사서함의 콘텐츠를 보존하려면 **Office 365 그룹** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-208">To retain content in these mailboxes, select the **Office 365 groups** location.</span></span>

<span data-ttu-id="c7386-209">**Exchange 공용 폴더** 위치는 보존 설정을 모든 공용 폴더에 적용하며 폴더 또는 사서함 수준에서 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-209">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="c7386-210">SharePoint 사이트 및 OneDrive 계정에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="c7386-210">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="c7386-211">**SharePoint 사이트** 위치를 선택할 때 보존 정책을 사용하여 SharePoint 커뮤니케이션 사이트, Office 365 그룹으로 연결되지 않는 팀 사이트 및 클래식 사이트에서 문서를 보존하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-211">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Office 365 groups, and classic sites.</span></span> <span data-ttu-id="c7386-212">Office 365 그룹에서 연결된 팀 사이트는 이 옵션에서 지원되지 않으며 대신 해당 그룹의 사서함, 사이트 및 파일에 있는 콘텐츠에 적용되는 **Office 365 그룹** 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-212">Team sites connected by Office 365 groups aren't supported with this option and instead, use the **Office 365 groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="c7386-213">보존 정책이 사이트 수준에서 적용되더라도 보존 설정은 문서에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-213">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="c7386-214">보존 설정은 사이트 내의 라이브러리, 목록 및 폴더를 포함하는 구성 구조에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-214">Retention settings do not apply to the organizing structures that include libraries, lists, and folders within the site.</span></span>

<span data-ttu-id="c7386-215">SharePoint 사이트 또는 OneDrive 계정의 위치를 지정하는 경우, 사이트에 액세스할 수 있는 권한이 필요하지 않으며 **위치 편집** 페이지에서 URL을 지정하는 시점에 유효성 검사가 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-215">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="c7386-216">그러나 SharePoint 사이트를 색인화해야 하며 마법사 종료 시 지정한 사이트가 존재하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-216">However, the SharePoint sites must be indexed and the sites that you specify are checked that they exist at the end of the wizard.</span></span>

<span data-ttu-id="c7386-217">이 검사에 실패하는 경우, 입력한 URL에 대한 유효성 검사에 실패했다는 메시지가 표시되고 유효성 검사가 통과한 후에 마법사에서 보존 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-217">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="c7386-218">이 메시지가 표시되는 경우, 마법사에서 돌아가서 URL을 변경하거나 보존 정책에서 사이트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-218">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="c7386-219">포함하거나 제외할 개별 OneDrive 계정을 지정하려면 URL은 `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com` 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-219">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="c7386-220">예를 들어, "rsimone"라는 사용자 이름을 보유한 Contoso 테넌트에 있는 사용자의 경우: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="c7386-220">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="c7386-221">테넌트의 구문을 확인하고 사용자 URL을 확인하려면, [조직에 있는 모든 사용자 OneDrive URL 목록 가져오기](https://docs.microsoft.com/onedrive/list-onedrive-urls)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7386-221">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="c7386-222">Microsoft 365 그룹에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="c7386-222">Configuration information for Microsoft 365 groups</span></span>

<span data-ttu-id="c7386-223">Microsoft 365 그룹(이전 이름: Office 365 그룹)의 콘텐츠를 보존하거나 삭제하려면 **Office 365 그룹** 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-223">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Office 365 groups** location.</span></span> <span data-ttu-id="c7386-224">Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-224">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="c7386-225">또한 **Exchange 전자 메일** 위치에서 처음에 포함하거나 제외할 그룹 사서함을 지정할 수 있지만 보존 정책을 저장하려고 하면 "RemoteGroupMailbox"가 Exchange 위치에 대해 올바른 선택이 아니라는 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-225">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="c7386-226">만약 팀 사이트가 그룹이 만들어 졌을 때 선택되었거나 혹은 나중에 그룹에 추가 된 경우, 그룹 사서함 및 팀 사이트를 포함한 Microsoft 365 그룹에 적용되는 보존 정책</span><span class="sxs-lookup"><span data-stu-id="c7386-226">A retention policy applied to a Microsoft 365 group includes the group mailbox and teams site, if a teams site was selected at the time the group was created or later added to the group.</span></span> <span data-ttu-id="c7386-227">팀 사이트에 저장된 파일은 이 위치에 포함되지만 자신의 보존 정책 위치가 있는 Teams 채팅 혹은 Teams 채널 메시지는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-227">Files stored in the teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="c7386-228">비즈니스용 Skype에 대한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="c7386-228">Configuration information for Skype for Business</span></span>

<span data-ttu-id="c7386-229">Exchange 전자 메일과 달리, Skype 위치의 상태는 간단히 설정으로 전환하여 모든 사용자를 자동으로 포함할 수 없습니다. 그렇지만 해당 위치를 켜면 해당 대화를 보존하려는 사용자를 수동으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-229">Unlike Exchange email, you can't toggle the status of the Skype location on to automatically include all users, but when you turn on that location, you must then manually choose the users whose conversations you want to retain:</span></span>

![보존 정책을 위한 Skype 위치 선택](../media/skype-location-retention-policies.png)

<span data-ttu-id="c7386-231">**사용자 선택**을 선택하면 **모두 선택** 상자를 선택하여 모든 사용자를 빠르게 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-231">When you select **Choose user**, you can quickly include all users by selecting the **Select all** box.</span></span> <span data-ttu-id="c7386-232">그러나 각 사용자가 정책의 특정 포함사항으로 간주된다는 점을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-232">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="c7386-233">따라서 **모두 선택** 상자를 선택하여 1,000명의 사용자를 포함하는 경우, 포함할 1,000명의 사용자를 수동으로 선택한 것과 같으며 이는 비즈니스용 Skype에 대해 지원되는 최대를 선택하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-233">So if you include 1,000 users by selecting the **Select all** box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="c7386-234">Outlook 폴더인 **대화 내용**은 Skype 아카이빙은 관계가 없는 기능</span><span class="sxs-lookup"><span data-stu-id="c7386-234">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="c7386-235">**대화 내용**은 최종 사용자가 끌 수 있지만, Skype 아카이빙은 사용자는 액세스할 수 없고 eDiscovery에서만 액세스 가능한 숨김 폴더에 Skype 대화 사본을 저장하는 기능</span><span class="sxs-lookup"><span data-stu-id="c7386-235">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="c7386-236">콘텐츠를 보존 및 삭제하기 위한 설정</span><span class="sxs-lookup"><span data-stu-id="c7386-236">Settings for retaining and deleting content</span></span>

<span data-ttu-id="c7386-237">보존 정책에서 콘텐츠를 보존하고 삭제하기 위한 설정을 선택하면 보존 정책에 지정된 기간 동안 다음 구성 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-237">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="c7386-238">보존 전용</span><span class="sxs-lookup"><span data-stu-id="c7386-238">Retain-only</span></span>

    <span data-ttu-id="c7386-239">이 구성에서는 **특정 기간에 대한 항목을 보존**을 선택하고 **보존 기간의 종료 시, 아무 작업도 수행하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="c7386-239">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**.</span></span> <span data-ttu-id="c7386-240">또는 **항목을 영구적으로 보존**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-240">Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="c7386-241">보존 후 삭제</span><span class="sxs-lookup"><span data-stu-id="c7386-241">Retain and then delete</span></span>

    <span data-ttu-id="c7386-242">이 구성에서는 **특정 기간에 대한 항목을 보존**을 선택하고 **보존 기간의 종료 시, 항목을 자동으로 삭제합니다**.</span><span class="sxs-lookup"><span data-stu-id="c7386-242">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="c7386-243">삭제 전용</span><span class="sxs-lookup"><span data-stu-id="c7386-243">Delete-only</span></span>

    <span data-ttu-id="c7386-244">이 구성에서는 **특정 기간에 도달했을 때만 항목 삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-244">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="c7386-245">특정 기간 동안 콘텐츠 보존</span><span class="sxs-lookup"><span data-stu-id="c7386-245">Retaining content for a specific period of time</span></span>

<span data-ttu-id="c7386-246">보존 정책을 구성하면 항목을 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-246">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years.</span></span> <span data-ttu-id="c7386-247">또는 항목이 영구적으로 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-247">Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="c7386-248">보존 정책을 구성하면 콘텐츠를 영구적으로 또는 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-248">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="c7386-249">콘텐츠 보존 기간은 보존 정책이 적용된 시점이 아닌 콘텐츠 생성 시점을 기준으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-249">The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span>

<span data-ttu-id="c7386-250">보존 기간이 시작되는 경우 또한 콘텐츠를 언제 만들어졌을지 또는 콘텐츠가 마지막으로 수정된 경우에는 파일 및 SharePoint, OneDrive 및 Office 365 위치에 대해서만 지원되었는지의 경우를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-250">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Office 365 locations, when the content was last modified.</span></span>

<span data-ttu-id="c7386-251">예제:</span><span class="sxs-lookup"><span data-stu-id="c7386-251">Examples:</span></span>

- <span data-ttu-id="c7386-252">SharePoint: 콘텐츠가 마지막으로 수정된 후 7년 동안 사이트 모음에 항목을 유지하고 해당 사이트 모음에 있는 문서가 6년 내에 수정되지 않은 경우, 문서가 수정되지 않으면 다른 한 해에만 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-252">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="c7386-253">문서를 다시 편집하면 문서 사용 기간은 마지막으로 수정한 날부터 계산되고 앞으로 7년 동안 더 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-253">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>

- <span data-ttu-id="c7386-254">Exchange: 사서함의 항목을 7년 동안 보존하려고 하고 메시지가 6년 전에 발송되었다면, 메시지는 1년 동안만 더 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-254">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="c7386-255">Exchange 항목의 경우 해당 기간은 받는 전자 메일의 받은 날짜 또는 보내는 전자 메일에 대해 보낸 날짜를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-255">For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="c7386-256">항목을 최종 수정된 시점을 기준으로 보존하는 것은 OneDrive 및 SharePoint의 사이트 콘텐츠에만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-256">Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>

<span data-ttu-id="c7386-257">보존 기간이 끝나면 콘텐츠를 영구적으로 삭제할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-257">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>

![보존 설정 페이지](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="c7386-259">특정 사용 기간보다 오래된 콘텐츠 삭제</span><span class="sxs-lookup"><span data-stu-id="c7386-259">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="c7386-260">보존 정책은 항목을 보존했다가 삭제하거나, 혹은 보존하지 않고 오래된 콘텐츠를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-260">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>

<span data-ttu-id="c7386-261">두 경우 모두, 보존 정책이 항목을 삭제할 경우 보존 정책에 대해 지정된 기간은 정책이 할당된 시점이 아니라 콘텐츠가 만들어졌거나 수정된 이후부터 계산된다는 사실에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-261">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="c7386-262">따라서 처음으로 사이트에 보존 정책을 할당하기 전에 그리고 특히 정책이 항목을 삭제할 시, 먼저 기존 콘텐츠의 사용 기간과 정책이 기존 콘텐츠에 어떤 영향을 줄 수 있는지 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-262">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content.</span></span> <span data-ttu-id="c7386-263">또한 새 정책을 할당하기 전에 사이트 소유자에게 미리 알려, 가능한 영향을 평가할 시간을 줄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-263">You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="c7386-264">전체 위치에 적용되는 정책</span><span class="sxs-lookup"><span data-stu-id="c7386-264">A policy that applies to entire locations</span></span>

<span data-ttu-id="c7386-265">위치를 선택하는 경우 비즈니스용 Skype를 제외하고, 위치의 상태가 **On**인 경우, 기본 설정은 **모두**가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-265">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>

<span data-ttu-id="c7386-266">보존 정책이 전체의 위치 조합에 적용되는 경우 정책에 포함할 수 있는 수혜자, 사이트, 계정, 그룹 등에 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-266">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups etc that the policy can include.</span></span>

<span data-ttu-id="c7386-267">예를 들어, 정책에 모든 Exchange 전자 메일과 모든 SharePoint 사이트가 모두 포함된다면, 개수와 상관없이 모든 사이트와 수혜자가 포함될 것</span><span class="sxs-lookup"><span data-stu-id="c7386-267">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many.</span></span> <span data-ttu-id="c7386-268">또한 Exchange의 경우 정책이 적용된 후 만들어진 모든 새 사서함은 자동으로 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-268">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="c7386-269">특정 포함 또는 제외가 적용된 정책</span><span class="sxs-lookup"><span data-stu-id="c7386-269">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="c7386-270">선택적 구성을 사용하여 특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트에 대한 보존 설정의 범위를 지정 하는 경우에만 다음의 몇 가지 제한 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-270">Only if you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits to be aware of:</span></span> 

- <span data-ttu-id="c7386-271">보존 정책의 최대 수:</span><span class="sxs-lookup"><span data-stu-id="c7386-271">Maximum numbers for a retention policy:</span></span>
  - <span data-ttu-id="c7386-272">1,000개의 사서함</span><span class="sxs-lookup"><span data-stu-id="c7386-272">1,000 mailboxes</span></span>
  - <span data-ttu-id="c7386-273">1,000개의 Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="c7386-273">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="c7386-274">Teams 비공개 채팅에 참여하는 1,000명의 사용자</span><span class="sxs-lookup"><span data-stu-id="c7386-274">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="c7386-275">100개의 사이트(OneDrive 또는 SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c7386-275">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="c7386-276">또한 테넌트에 대해 지원되는 최대 정책 수는 10,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-276">There is also a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="c7386-277">이러한 항목에는 보존 정책, 보존 레이블 정책, 자동 적용 보존 정책이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-277">These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="c7386-278">보존 정책에 이러한 제한이 적용될 가능성이 높은 경우에는 해당 정책에 제한이 없는 전체 위치에 적용되는 기본 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-278">If your retention policies are likely to be subject to these limitations, use the default configuration that applies to the entire location because these policies don't have any limitations.</span></span>

<span data-ttu-id="c7386-279">선택적 구성을 사용하여 보존 설정의 범위를 지정하려면 해당 위치의 **상태**가 **켜짐**인지 확인한 후 링크를 사용하여 특정 사용자, Microsoft 365 그룹 또는 사이트를 포함하거나 배제하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-279">To use the optional configuration to scope your retention settings, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span>

> [!WARNING]
> <span data-ttu-id="c7386-280">마지막 구성을 포함했다가 제거하면 해당 위치에 대해 **모두**로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-280">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="c7386-281">정책을 저장하기 전에 원하는 구성인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-281">Make sure this is the configuration that you intend before you save the policy.</span></span>
>
> <span data-ttu-id="c7386-282">예를 들어 데이터를 삭제하도록 구성된 보존 정책에 포함할 SharePoint 사이트 하나를 지정한 다음 단일 사이트를 제거하면 기본적으로 모든 SharePoint 사이트는 데이터를 영구적으로 삭제하는 보존 정책의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-282">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="c7386-283">Exchange 수신인, OneDrive 계정, 팀 채팅 사용자 등의 경우에도 마찬가지</span><span class="sxs-lookup"><span data-stu-id="c7386-283">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
>
> <span data-ttu-id="c7386-284">이 시나리오에서 위치에 대한 **모두** 설정을 보존 정책의 적용을 받지 않으려면 위치를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-284">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="c7386-285">또는 정책에서 제외할 제외 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-285">Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="c7386-286">보존 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="c7386-286">Updating retention policies</span></span>

<span data-ttu-id="c7386-287">보존 정책을 편집하고 항목이 보존 정책의 원래 설정에 이미 적용되어 있는 경우 업데이트된 설정은 새로 식별된 항목 외에 이 항목에도 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-287">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="c7386-288">일반적으로 이 업데이트는 아주 간단하지만 며칠이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-288">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="c7386-289">Microsoft 365 위치에서 정책 복제가 완료되면 Microsoft 365 준수 센터의 보존 정책 상태가 **켜기(보류)** 에서 **켜기(성공)** 으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-289">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="c7386-290">PowerShell을 사용하여 보존 정책 잠금</span><span class="sxs-lookup"><span data-stu-id="c7386-290">Lock a retention policy by using PowerShell</span></span>

<span data-ttu-id="c7386-291">규정 요구 사항을 준수하기 위해 [보존 잠금](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)을 사용해야 하는 경우 PowerShell을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-291">You must use PowerShell if you need to use [Preservation Lock](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements) to comply with regulatory requirements.</span></span> <span data-ttu-id="c7386-292">유지 잠금이 적용된 후에는 관리자가 보존 정책을 사용하지 않도록 설정하거나 삭제할 수 없기 때문에, 이 기능을 사용하도록 설정하는 것은 잘못된 구성으로부터 보호하는 UI에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-292">Because administrators can't disable or delete a retention policy after a preservation lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="c7386-293">모든 구성 지원 보존 잠금이 있는 모든 보존 정책.</span><span class="sxs-lookup"><span data-stu-id="c7386-293">All retention policies with any configuration support Preservation Lock.</span></span> <span data-ttu-id="c7386-294">그러나 뒤에 나오는 PowerShell 명령을 사용하는 경우 **작업부하** 매개변수에는 정책에 구성된 실제 작업 부하를 반영하는 것이 아니라 **Exchange, SharePoint, OneDriveForBusines, Skype, ModernGroup**을 표시하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-294">However, when you use the PowerShell commands that follow, you'll notice that the **Workload** parameter always displays **Exchange, SharePoint, OneDriveForBusines, Skype, ModernGroup** rather than reflect the actual workloads configured in the policy.</span></span> <span data-ttu-id="c7386-295">이는 표시 문제일 뿐</span><span class="sxs-lookup"><span data-stu-id="c7386-295">This is a display issue only.</span></span>

1. <span data-ttu-id="c7386-296">[보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-296">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c7386-297">[RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)를 실행하여 잠글 정책의 이름을 나열하고 보존 정책을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-297">List your retention policies and find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="c7386-298">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="c7386-298">For example:</span></span>

   ![PowerShell의 보존 정책 목록](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="c7386-300">보존 정책에 보존 잠금을 설정하려면 [Set-RetentionCompliancePolicy]( ) cmdlet을 보존 정책 이름으로 실행하고 *RestrictiveRetention* 매개변수를 true로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-300">To place a Preservation Lock on a retention policy, run the [Set-RetentionCompliancePolicy]( ) cmdlet with the name of the retention policy, and the *RestrictiveRetention* parameter set to true:</span></span>

    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```

    <span data-ttu-id="c7386-301">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="c7386-301">For example:</span></span>

    ![PowerShell의 RestrictiveRetention 매개 변수](../media/retention-policy-preservation-lock-restrictiveretention.PNG)

     <span data-ttu-id="c7386-303">메시지가 표시되면 이 구성과 함께 제공되는 제한 사항을 읽고 **Y**를 입력하여 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-303">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>

   ![PowerShell에서 보존 정책 잠금을 원하는지 확인하는 메시지](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="c7386-305">이제 보존 정책에 보존 잠금이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-305">A Preservation Lock is now placed on the retention policy.</span></span> <span data-ttu-id="c7386-306">확인하려면 `Get-RetentionCompliancePolicy` 다시 실행 하지만, 보존 정책 이름을 지정하고 정책 매개변수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-306">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the retention policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="c7386-307">**RestrictiveRetention**이 **True**로 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7386-307">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="c7386-308">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="c7386-308">For example:</span></span>

![PowerShell에 모든 매개 변수와 함께 표시된 잠긴 정책](../media/retention-policy-preservation-lock-locked-policy.PNG)
