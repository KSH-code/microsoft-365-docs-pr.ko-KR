---
title: 데이터 손실 방지 및 Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams 채널은 DLP(데이터 손실 방지) 정책을 지원합니다.
ms.openlocfilehash: fa7e0967e24d8fa5e64b84fbccf54ff8cf45d1d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843545"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="666bf-103">데이터 손실 방지 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="666bf-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="666bf-104">조직에 DLP(데이터 손실 방지)가 있는 경우 사용자가 특정 채널 또는 채팅 세션에서 중요한 정보를 공유하지 Microsoft Teams 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="666bf-105">다음은 이 보호가 작동하는 방식의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="666bf-106">**예제 1: 메시지의 중요한 정보 보호**</span><span class="sxs-lookup"><span data-stu-id="666bf-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="666bf-107">누군가가 게스트(외부 사용자)와 Teams 채팅 또는 채널에서 중요한 정보를 공유하려고 시도하는 경우를 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="666bf-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="666bf-108">이를 방지하는 DLP 정책이 정의되어 있는 경우 외부 사용자에게 전송되는 중요한 정보가 있는 메시지는 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="666bf-109">이 문제는 DLP 정책이 구성된 방식에 따라 자동으로 몇 초 내에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="666bf-110">다음을 Microsoft Teams 사용자와 공유하는 경우 중요한 Microsoft Teams 차단하는 DLP입니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="666bf-111">- [팀 및](/MicrosoftTeams/guest-access) 채널의 게스트 액세스 또는</span><span class="sxs-lookup"><span data-stu-id="666bf-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="666bf-112">- [모임 및](/MicrosoftTeams/manage-external-access) 채팅 세션의 외부 액세스</span><span class="sxs-lookup"><span data-stu-id="666bf-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="666bf-113">외부 채팅 세션에 대한 DLP는 보낸 사람 및 수신자가 모두 Teams 전용 모드에 있으며 기본 Microsoft Teams [사용하는 경우만 사용할 수 있습니다.](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="666bf-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="666bf-114">Teams 대한 DLP는 비즈니스용 Skype 비 네이티브 페더러드 채팅 세션과 상호 연결되는 메시지를 차단하지 않습니다. [](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="666bf-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="666bf-115">**예제 2: 문서의 중요한 정보 보호**</span><span class="sxs-lookup"><span data-stu-id="666bf-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="666bf-116">다른 사용자가 특정 채널 또는 채팅에서 게스트와 문서를 공유하려고 Microsoft Teams 중요한 정보가 포함된 경우를 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="666bf-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="666bf-117">이를 방지하는 DLP 정책이 정의되어 있는 경우 해당 사용자에 대해 문서가 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="666bf-118">이 보호 기능을 사용하려면, DLP 정책에 SharePoint 및 OneDrive가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="666bf-119">SharePoint DLP의 예로 Microsoft Teams 에 표시하므로 사용자에게 Office 365 DLP(Office 365 E3에 포함)에 대한 라이선스가 필요하지만 사용자에게 Office 365 Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="666bf-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="666bf-120">사용자에 대한 DLP Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="666bf-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="666bf-121">[데이터 손실 방지](dlp-learn-about-dlp.md) 기능은 다음에 대한 비공개 채널 Microsoft Teams 및 채널 메시지를 포함하기 위해 **확장했습니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="666bf-122">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="666bf-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="666bf-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="666bf-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="666bf-124">Microsoft 365 정보 보호 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="666bf-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="666bf-125">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="666bf-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="666bf-126">Office 365 Microsoft 365 E3 온라인, OneDrive 및 SharePoint DLP 보호가 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="666bf-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="666bf-127">이 파일에는 Teams Online을 사용하여 Teams 공유하기 때문에 SharePoint 공유하는 OneDrive 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="666bf-128">채팅에서 DLP 보호를 지원하려면 Teams E5가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="666bf-129">라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="666bf-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="666bf-130">DLP는 채팅 또는 채널 스레드의 실제 메시지에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="666bf-131">짧은 메시지 미리 보기를 포함하며 사용자의 알림 설정에 따라 나타나는 활동  알림은 DLP에 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="666bf-132">미리 보기에 표시되는 메시지 부분에 있는 모든 중요한 정보는 DLP 정책이 적용되고 메시지 자체를 제거한 후에도 알림에 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="666bf-133">DLP 보호 범위</span><span class="sxs-lookup"><span data-stu-id="666bf-133">Scope of DLP protection</span></span>

<span data-ttu-id="666bf-134">DLP 보호는 엔터티에 Teams 다르게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="666bf-135">사용자 계정/그룹/목록</span><span class="sxs-lookup"><span data-stu-id="666bf-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="666bf-136">Teams 엔터티</span><span class="sxs-lookup"><span data-stu-id="666bf-136">Teams Entity</span></span> |<span data-ttu-id="666bf-137">DLP 보호 사용 가능</span><span class="sxs-lookup"><span data-stu-id="666bf-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="666bf-138">개별 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="666bf-138">individual user accounts</span></span>     |<span data-ttu-id="666bf-139">1:1/n 채팅</span><span class="sxs-lookup"><span data-stu-id="666bf-139">1:1/n chats</span></span>         |<span data-ttu-id="666bf-140">예</span><span class="sxs-lookup"><span data-stu-id="666bf-140">yes</span></span>         |
|     |<span data-ttu-id="666bf-141">일반 채팅</span><span class="sxs-lookup"><span data-stu-id="666bf-141">general chats</span></span>         |<span data-ttu-id="666bf-142">아니요</span><span class="sxs-lookup"><span data-stu-id="666bf-142">no</span></span>         |
|     |<span data-ttu-id="666bf-143">비공개 채널</span><span class="sxs-lookup"><span data-stu-id="666bf-143">private channels</span></span>         |<span data-ttu-id="666bf-144">예</span><span class="sxs-lookup"><span data-stu-id="666bf-144">yes</span></span>         |
|<span data-ttu-id="666bf-145">보안 그룹/메일 그룹</span><span class="sxs-lookup"><span data-stu-id="666bf-145">security groups/distribution lists</span></span>  | <span data-ttu-id="666bf-146">1:1/n 채팅</span><span class="sxs-lookup"><span data-stu-id="666bf-146">1:1/n chats</span></span>         |<span data-ttu-id="666bf-147">예</span><span class="sxs-lookup"><span data-stu-id="666bf-147">yes</span></span>         |
|     |<span data-ttu-id="666bf-148">일반 채팅</span><span class="sxs-lookup"><span data-stu-id="666bf-148">general chats</span></span>         |<span data-ttu-id="666bf-149">아니요</span><span class="sxs-lookup"><span data-stu-id="666bf-149">no</span></span>         |
|     |<span data-ttu-id="666bf-150">비공개 채널</span><span class="sxs-lookup"><span data-stu-id="666bf-150">private channels</span></span>         |<span data-ttu-id="666bf-151">예</span><span class="sxs-lookup"><span data-stu-id="666bf-151">yes</span></span>        |
|<span data-ttu-id="666bf-152">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="666bf-152">Microsoft 365 group</span></span>    |<span data-ttu-id="666bf-153">1:1/n 채팅</span><span class="sxs-lookup"><span data-stu-id="666bf-153">1:1/n chats</span></span>          |<span data-ttu-id="666bf-154">아니요</span><span class="sxs-lookup"><span data-stu-id="666bf-154">no</span></span>         |
|     |<span data-ttu-id="666bf-155">일반 채팅</span><span class="sxs-lookup"><span data-stu-id="666bf-155">general chats</span></span>          |<span data-ttu-id="666bf-156">예</span><span class="sxs-lookup"><span data-stu-id="666bf-156">yes</span></span>        |
|     |<span data-ttu-id="666bf-157">비공개 채널</span><span class="sxs-lookup"><span data-stu-id="666bf-157">private channels</span></span>|<span data-ttu-id="666bf-158">아니요</span><span class="sxs-lookup"><span data-stu-id="666bf-158">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="666bf-159">정책 팁은 사용자를 교육하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-159">Policy tips help educate users</span></span>

<span data-ttu-id="666bf-160">웹, [Exchange, Outlook,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)Outlook, SharePoint [Online,](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)비즈니스용 OneDrive 사이트 및 Office 데스크톱 클라이언트에서 DLP가 작동하는 방식과 마찬가지로 DLP 정책을 사용하여 작업이 트리거될 때 정책 [팁이](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-160">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="666bf-161">정책 팁의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-161">Here's an example of a policy tip:</span></span>

![차단된 메시지 알림의 Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="666bf-163">여기서 보낸 사람이 공유 채널에서 주민 Microsoft Teams 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-163">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="666bf-164">What **can I do?** 링크를 클릭하면 보낸 사람이 문제를 해결할 수 있는 옵션을 제공하는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-164">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="666bf-165">보낸 사람이 정책을 다시 설정하거나 관리자에게 검토 및 해결을 알리도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-165">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![차단된 메시지 해결 옵션](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="666bf-167">조직에서 사용자가 DLP 정책을 다시 설정하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-167">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="666bf-168">DLP 정책을 구성할 때 기본 정책 팁을 사용하거나 조직의 정책 팁을 [사용자 지정할](#to-customize-policy-tips) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-168">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="666bf-169">보낸 사람이 Teams 채널에서 사회 보장 번호를 공유한 예제로 돌아가면 받는 사람이 본 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-169">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="666bf-170">![메시지가 차단됩니다.](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-170">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="666bf-171">정책 팁 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="666bf-171">To customize policy tips</span></span>

<span data-ttu-id="666bf-172">이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-172">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="666bf-173">자세한 내용은 사용 권한을 [참조합니다.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="666bf-173">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="666bf-174">준수 센터()로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-174">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="666bf-175">**데이터 손실 방지** > **정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-175">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="666bf-176">정책을 선택하고 정책 설정 옆에 **있는** 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-176">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="666bf-177">새 규칙을 만들거나 정책에 대한 기존 규칙을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-177">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="666bf-178">![정책에 대한 규칙 편집](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-178">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="666bf-179">사용자 **알림 탭에서** 전자  메일 텍스트 사용자 지정 및/또는 정책 팁 텍스트 **옵션 사용자 지정을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-179">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="666bf-180">![사용자 알림 및 정책 팁 사용자 지정](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-180">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="666bf-181">전자 메일 알림 및/또는 정책 팁에 사용할 텍스트를 지정하고 저장 을 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="666bf-181">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="666bf-182">정책 **설정 탭에서** 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-182">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="666bf-183">변경 내용이 데이터 센터를 통해 작동하고 사용자 계정과 동기화되는 데 약 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-183">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="666bf-184">기존 DLP 정책에 Microsoft Teams를 위치로 추가</span><span class="sxs-lookup"><span data-stu-id="666bf-184">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="666bf-185">이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-185">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="666bf-186">자세한 내용은 사용 권한을 [참조합니다.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="666bf-186">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="666bf-187">준수 센터()로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-187">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="666bf-188">**데이터 손실 방지** > **정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-188">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="666bf-189">정책을 선택하고 위치 에서 값을 **봐야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-189">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="666bf-190">채팅 및 **Teams 메시지가** 표시되어 있는 경우 모두 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-190">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="666bf-191">그렇지 않은 경우 편집 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-191">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="666bf-192">![기존 정책의 위치](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-192">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="666bf-193">상태 **열에서** 채팅 및 채널 메시지 **에 Teams 을 으로 끄습니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-193">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="666bf-194">![채팅 및 Teams 위한 DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-194">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="666bf-195">위치 **선택 탭에서** 모든 계정의 기본 설정을 유지하거나 특정 위치를 선택하도록 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-195">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="666bf-196">지정할 수 있는 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-196">You can specify:</span></span>

    1. <span data-ttu-id="666bf-197">포함하거나 제외할 최대 1,000개 개별 계정</span><span class="sxs-lookup"><span data-stu-id="666bf-197">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="666bf-198">포함하거나 제외할 메일 그룹 및 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="666bf-198">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="666bf-199">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-199">Then choose **Next**.</span></span>

7. <span data-ttu-id="666bf-200">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-200">Click **Save**.</span></span>

<span data-ttu-id="666bf-201">변경 내용이 데이터 센터를 통해 작동하고 사용자 계정과 동기화되는 데 약 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-201">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="666bf-202">Microsoft Teams에 대한 새 DLP 정책 정의</span><span class="sxs-lookup"><span data-stu-id="666bf-202">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="666bf-203">이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-203">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="666bf-204">자세한 내용은 사용 권한을 [참조합니다.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="666bf-204">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="666bf-205">준수 센터()로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-205">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="666bf-206">**데이터 손실 방지** > **정책** > **+ 정책 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-206">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="666bf-207">템플릿 [을](data-loss-prevention-policies.md#dlp-policy-templates)선택하고 다음 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-207">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="666bf-208">이 예제에서는 미국 개인 식별 정보 데이터 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-208">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="666bf-209">![DLP 정책에 대한 개인 정보 템플릿](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-209">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="666bf-210">정책 **이름 지정 탭에서** 정책의 이름과 설명을 지정하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-210">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="666bf-211">위치 **선택 탭에서** 모든 계정의 기본 설정을 유지하거나 특정 위치를 선택하도록 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-211">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="666bf-212">지정할 수 있는 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-212">You can specify:</span></span>

    1. <span data-ttu-id="666bf-213">포함하거나 제외할 최대 1,000개 개별 계정</span><span class="sxs-lookup"><span data-stu-id="666bf-213">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="666bf-214">포함하거나 제외할 메일 그룹 및 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="666bf-214">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="666bf-215">**공개 미리 보기 기능입니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-215">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP 정책 위치](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="666bf-217">중요한 정보가 포함된 문서가 Teams 부적절하게 공유되지 않는지 확인하려는 경우 SharePoint  사이트 및 OneDrive  계정과 채팅 및 채널 메시지와 **함께** Teams 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-217">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="666bf-218">정책 **설정 탭의** 보호할 콘텐츠 형식 사용자 지정에서 **기본** 단순 설정을 유지하거나 고급 설정 사용을 선택한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-218">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="666bf-219">고급 설정을 선택하는 경우 정책에 대한 규칙을 만들거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-219">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="666bf-220">이에 대한 도움말은 단순 설정 및 고급 설정 [을 참조하세요.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="666bf-220">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="666bf-221">정책 **설정 탭의** 중요한 정보를 검색하는 경우 어떤 작업을 하고 **싶나요?** 아래에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-221">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="666bf-222">다음은 기본 정책 팁 및 [](use-notifications-and-policy-tips.md)전자 메일 알림을 유지하거나 사용자 지정할 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-222">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="666bf-223">![팁 및 알림이 있는 DLP 정책 설정](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-223">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="666bf-224">설정 검토 또는 편집을 마치면 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-224">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="666bf-225">정책  설정 탭의 정책을 켜거나 먼저 테스트할지 여부에서 정책을 켜거나 먼저 테스트할지, 아니면 지금 해제된 후 다음 을 **선택합니다.** [](dlp-overview-plan-for-dlp.md#policy-deployment)</span><span class="sxs-lookup"><span data-stu-id="666bf-225">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="666bf-226">![정책을 켜는지 여부 지정](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-226">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="666bf-227">설정 **검토 탭에서** 새 정책에 대한 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-227">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="666bf-228">편집을 **선택해** 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-228">Choose **Edit** to make changes.</span></span> <span data-ttu-id="666bf-229">완료되면 만들기 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="666bf-229">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="666bf-230">새 정책이 데이터 센터를 통해 작동하고 사용자 계정에 동기화되는 데 약 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-230">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="666bf-231">중요한 문서에 대한 외부 액세스 방지</span><span class="sxs-lookup"><span data-stu-id="666bf-231">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="666bf-232">중요한 SharePoint 포함된 문서에 기본적으로 외부 게스트가 액세스하지 못하도록 SharePoint Teams 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-232">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="666bf-233">기본적으로 새 파일을 중요한 파일로 표시하여 DLP가 문서를 검사하고 공유하기 안전한 것으로 표시할 때까지 문서가 [보호되도록 할 수 있습니다.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="666bf-233">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="666bf-234">권장되는 DLP 정책 구조</span><span class="sxs-lookup"><span data-stu-id="666bf-234">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="666bf-235">**조건**</span><span class="sxs-lookup"><span data-stu-id="666bf-235">**Conditions**</span></span>
        - <span data-ttu-id="666bf-236">콘텐츠에 다음 중요한 정보 유형이 포함되어 있습니다. [적용되는 모든 정보 선택]</span><span class="sxs-lookup"><span data-stu-id="666bf-236">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="666bf-237">콘텐츠가 조직 Microsoft 365 사용자와 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="666bf-237">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="666bf-238">![중요한 콘텐츠의 외부 공유를 감지하기 위한 DLP 조건](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-238">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="666bf-239">**작업**</span><span class="sxs-lookup"><span data-stu-id="666bf-239">**Actions**</span></span>
        - <span data-ttu-id="666bf-240">외부 사용자의 콘텐츠에 대한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="666bf-240">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="666bf-241">전자 메일 및 정책 팁을 통해 사용자에게 알림</span><span class="sxs-lookup"><span data-stu-id="666bf-241">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="666bf-242">관리자에게 인시던트 보고서 보내기</span><span class="sxs-lookup"><span data-stu-id="666bf-242">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="666bf-243">![중요한 콘텐츠의 외부 공유를 차단하는 DLP 작업](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-243">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="666bf-244">외부 게스트와 중요한 정보를 포함하는 SharePoint 공유하려고 할 때 실행되는 DLP 정책:</span><span class="sxs-lookup"><span data-stu-id="666bf-244">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="666bf-245">![외부 공유 차단](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-245">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="666bf-246">게스트가 외부 차단을 통해 Teams 열려고 할 때 실행되는 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="666bf-246">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="666bf-247">![외부 액세스 차단](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="666bf-247">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="666bf-248">관련 문서</span><span class="sxs-lookup"><span data-stu-id="666bf-248">Related articles</span></span>

- [<span data-ttu-id="666bf-249">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="666bf-249">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="666bf-250">DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시</span><span class="sxs-lookup"><span data-stu-id="666bf-250">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
