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
description: 이제 채팅 및 채널에 DLP 정책을 Microsoft Teams 적용할 수 있습니다. 이 문서에서 작동 방식에 대해 자세히 알아보세요.
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572468"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="4a9e7-104">데이터 손실 방지 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a9e7-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="4a9e7-105">데이터 손실 방지 기능은 최근 Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 정보 보호 및 거버넌스 또는 Office 365 Advanced Compliance 라이선스를 받은 사용자를 위한 채팅 및 채널 메시지에 Microsoft Teams 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="4a9e7-106">Office 365 및 Microsoft 365 E3 SharePoint 온라인, OneDrive 및 Exchange Online 대한 DLP 보호 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="4a9e7-107">여기에는 Teams SharePoint 온라인 및 OneDrive 사용하여 파일을 공유하기 때문에 Teams 통해 공유되는 파일도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="4a9e7-108">Teams 채팅에서 DLP 보호에 대한 지원은 E5가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="4a9e7-109">라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="4a9e7-110">Microsoft Teams용 DLP 개요</span><span class="sxs-lookup"><span data-stu-id="4a9e7-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="4a9e7-111">최근에는 **개인 채널 메시지를 포함한** Microsoft Teams 채팅 및 채널 메시지를 포함하도록 데이터 손실 [방지](dlp-learn-about-dlp.md) 기능이 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-111">Recently, [data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4a9e7-112">DLP는 현재 채팅 또는 채널 스레드의 실제 메시지에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="4a9e7-113">짧은 메시지 미리 보기를 포함하고 사용자의 알림 설정에 따라 표시되는 활동 알림은 현재 Teams DLP에 포함되지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="4a9e7-114">미리 보기에 나타나는 메시지 부분에 있는 중요한 정보는 DLP 정책이 적용되고 메시지 자체를 제거한 후에도 알림에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

<span data-ttu-id="4a9e7-115">이제 조직에 DLP가 있는 경우 Microsoft Teams 채널 또는 채팅 세션에서 중요한 정보를 공유하지 못하도록 하는 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="4a9e7-116">다음은 이 보호의 작동 방식에 대한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="4a9e7-117">**예 1: 메시지에서 중요한 정보를 보호합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="4a9e7-118">다른 사람이 Teams 채팅 또는 채널에서 게스트(외부 사용자)와 중요한 정보를 공유하려고 한다고 가정해 보라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="4a9e7-119">이를 방지하기 위해 DLP 정책이 정의된 경우 외부 사용자에게 전송되는 중요한 정보가 포함된 메시지가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="4a9e7-120">DLP 정책이 구성되는 방식에 따라 몇 초 내에 자동으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4a9e7-121">Microsoft Teams 대한 DLP는 다음과 같은 Microsoft Teams 사용자와 공유할 때 중요한 콘텐츠를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="4a9e7-122">- 팀 및 채널에서 [게스트 액세스;](/MicrosoftTeams/guest-access) 또는</span><span class="sxs-lookup"><span data-stu-id="4a9e7-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="4a9e7-123">- 회의 및 채팅 세션에서 [외부 액세스.](/MicrosoftTeams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="4a9e7-124">외부 채팅 세션의 DLP는 보낸자와 수신자가 Teams 전용 모드에 있고 [Microsoft Teams 네이티브 페더레이션을](/microsoftteams/manage-external-access)사용하는 경우에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="4a9e7-125">Teams 대한 DLP는 비즈니스용 Skype 또는 네이티브가 아닌 연합 채팅 세션이 있는 [interop에서](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) 메시지를 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="4a9e7-126">**예 2: 문서에서 중요한 정보 보호.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="4a9e7-127">다른 사람이 Microsoft Teams 채널 또는 채팅에서 게스트와 문서를 공유하려고 시도하고 문서에 중요한 정보가 포함되어 있다고 가정해 보실 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="4a9e7-128">이를 방지하기 위해 정의된 DLP 정책이 있는 경우 해당 사용자에 대해 문서가 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="4a9e7-129">이 경우 DLP 정책에보호가 준비되려면 SharePoint 및 OneDrive 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="4a9e7-130">(이 Microsoft Teams 표시 SharePoint 대 한 DLP의 예, 따라서 사용자가 Office 365 DLP에 대 한 라이센스 (Office 365 E3에 포함), 하지만 사용자가 Office 365 Advanced Compliance 대 한 라이센스를 필요로 하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="4a9e7-131">정책 팁은 사용자를 교육하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-131">Policy tips help educate users</span></span>

<span data-ttu-id="4a9e7-132">DLP가 [Exchange, Outlook, 웹,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint 온라인, 비즈니스용 OneDrive 사이트](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)및 Office 데스크톱 [클라이언트에서](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)Outlook 것과 마찬가지로 DLP 정책과 작업이 충돌할 때 정책 팁이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="4a9e7-133">정책 팁의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-133">Here's an example of a policy tip:</span></span>

![Teams 메시지 알림 차단](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="4a9e7-135">이 경우 보낸 사람은 Microsoft Teams 채널에서 사회 보장 번호를 공유하려고 시도했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="4a9e7-136">**수행할 수 있는 작업을 수행할 수 있습니까?** 링크는 보낸 사람이 문제를 해결할 수 있는 옵션을 제공하는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="4a9e7-137">이 경우 보낸 사람이 정책을 재정의하거나 관리자에게 정책을 검토하고 해결하도록 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![차단된 메시지를 해결하는 옵션](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="4a9e7-139">조직에서 사용자가 DLP 정책을 재정의할 수 있도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="4a9e7-140">또한 DLP 정책을 구성할 때 기본 정책 팁을 사용하거나 조직의 [정책 팁을 사용자 지정할](#to-customize-policy-tips) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="4a9e7-141">보낸 사람이 Teams 채널에서 사회 보장 번호를 공유한 예제로 돌아가면 받는 사람이 본 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4a9e7-142">![메시지가 차단됨](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="4a9e7-143">정책 팁 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4a9e7-143">To customize policy tips</span></span>

<span data-ttu-id="4a9e7-144">이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="4a9e7-145">자세한 내용은 [사용 권한을](data-loss-prevention-policies.md#permissions)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="4a9e7-146">보안 & 규정 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-146">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="4a9e7-147">**데이터 손실 방지** > **정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-147">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="4a9e7-148">정책을 선택하고 **정책 설정** 옆에 **있는 편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-148">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="4a9e7-149">새 규칙을 만들거나 정책에 대한 기존 규칙을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-149">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4a9e7-150">![정책에 대한 규칙 편집](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-150">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="4a9e7-151">사용자 **알림** 탭에서 **이메일 텍스트 사용자 지정을** 선택하고 정책 팁 텍스트 옵션을 **사용자 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-151">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4a9e7-152">![사용자 알림 및 정책 팁 사용자 지정](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-152">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="4a9e7-153">이메일 알림 및/또는 정책 팁에 사용할 텍스트를 지정한 다음 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-153">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="4a9e7-154">정책 **설정** 탭에서 **저장을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-154">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="4a9e7-155">변경 사항이 데이터 센터를 통해 작동하고 사용자 계정에 동기화하는 데 약 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-155">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="4a9e7-156">기존 DLP 정책에 Microsoft Teams를 위치로 추가</span><span class="sxs-lookup"><span data-stu-id="4a9e7-156">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="4a9e7-157">이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-157">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="4a9e7-158">자세한 내용은 [사용 권한을](data-loss-prevention-policies.md#permissions)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-158">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="4a9e7-159">보안 & 규정 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-159">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="4a9e7-160">**데이터 손실 방지** > **정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-160">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="4a9e7-161">정책을 선택하고 **위치** 아래값을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-161">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="4a9e7-162">**채팅 및 채널 메시지에 Teams** 표시되면 모두 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-162">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="4a9e7-163">그렇지 않은 경우 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-163">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4a9e7-164">![기존 정책의 위치](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-164">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="4a9e7-165">**상태** 열에서 **Teams 채팅 및 채널 메시지에** 대한 정책을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-165">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4a9e7-166">![Teams 채팅 및 채널용 DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-166">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="4a9e7-167">위치 **선택** 탭에서 모든 계정의 기본 설정을 유지하거나 **특정 위치를 선택하도록 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-167">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="4a9e7-168">지정할 수 있는 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-168">You can specify:</span></span>

    1. <span data-ttu-id="4a9e7-169">포함하거나 제외할 개별 계정 최대 1,000개</span><span class="sxs-lookup"><span data-stu-id="4a9e7-169">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="4a9e7-170">포함하거나 제외할 메일 목록 및 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-170">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="4a9e7-171">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-171">Then choose **Next**.</span></span>

7. <span data-ttu-id="4a9e7-172">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-172">Click **Save**.</span></span>

<span data-ttu-id="4a9e7-173">변경 사항이 데이터 센터를 통해 작동하고 사용자 계정에 동기화하는 데 약 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-173">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="4a9e7-174">Microsoft Teams에 대한 새 DLP 정책 정의</span><span class="sxs-lookup"><span data-stu-id="4a9e7-174">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="4a9e7-175">이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-175">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="4a9e7-176">자세한 내용은 [사용 권한을](data-loss-prevention-policies.md#permissions)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-176">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="4a9e7-177">보안 & 규정 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-177">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="4a9e7-178">**데이터 손실 방지** > **정책** > **+ 정책 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-178">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="4a9e7-179">[템플릿을](data-loss-prevention-policies.md#dlp-policy-templates)선택한 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-179">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="4a9e7-180">예제에서는 미국 개인 식별 정보 데이터 템플릿을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-180">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4a9e7-181">![DLP 정책에 대한 개인 정보 보호 템플릿](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-181">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="4a9e7-182">정책 **이름** 탭에서 정책에 대한 이름과 설명을 지정한 다음 **다음을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-182">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="4a9e7-183">위치 **선택** 탭에서 모든 계정의 기본 설정을 유지하거나 **특정 위치를 선택하도록 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-183">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="4a9e7-184">지정할 수 있는 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-184">You can specify:</span></span>

    1. <span data-ttu-id="4a9e7-185">포함하거나 제외할 개별 계정 최대 1,000개</span><span class="sxs-lookup"><span data-stu-id="4a9e7-185">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="4a9e7-186">포함하거나 제외할 메일 목록 및 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-186">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="4a9e7-187">**공개 미리 보기 기능입니다.**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-187">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP 정책 위치](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="4a9e7-189">중요한 정보가 포함된 문서가 Teams 부적절하게 공유되지 않도록 하려면 **SharePoint 사이트와** **OneDrive 계정이** Teams 채팅 및 **채널 메시지와** 함께 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-189">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="4a9e7-190">정책 **설정** 탭에서 **보호하려는 콘텐츠 유형을 사용자 지정하거나** 기본 간단한 설정을 유지하거나 **고급 설정을 선택한** 다음 **다음을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-190">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="4a9e7-191">고급 설정을 선택하면 정책에 대한 규칙을 만들거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-191">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="4a9e7-192">(이 에 대한 도움을 받으려면 [간단한 설정 과 고급 설정을](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)참조하십시오.)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-192">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="4a9e7-193">정책 **설정** 탭에서 **중요한 정보를 감지하면 어떻게 하시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-193">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="4a9e7-194">기본 [정책 팁과 이메일 알림을](use-notifications-and-policy-tips.md)유지하거나 사용자 지정할 수 있는 곳은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-194">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4a9e7-195">![팁 및 알림이 있는 DLP 정책 설정](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-195">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="4a9e7-196">설정 검토 또는 편집이 완료되면 **다음을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-196">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="4a9e7-197">정책 **설정** [](dlp-overview-plan-for-dlp.md#policy-deployment) **탭에서 정책을 켜거나 먼저 테스트하시겠습니까?** </span><span class="sxs-lookup"><span data-stu-id="4a9e7-197">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4a9e7-198">![정책을 켤지 여부를 지정합니다.](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-198">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="4a9e7-199">설정 **검토** 탭에서 새 정책의 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-199">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="4a9e7-200">**수정을** 선택하여 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-200">Choose **Edit** to make changes.</span></span> <span data-ttu-id="4a9e7-201">완료되면 **만들기를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-201">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="4a9e7-202">새 정책이 데이터 센터를 통해 작동하고 사용자 계정에 동기화하는 데 약 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-202">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="4a9e7-203">중요한 문서에 대한 외부 액세스 방지</span><span class="sxs-lookup"><span data-stu-id="4a9e7-203">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="4a9e7-204">중요한 정보가 포함된 SharePoint 문서는 기본적으로 SharePoint 또는 Teams 외부 게스트가 액세스할 수 없도록 하려면 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-204">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="4a9e7-205">DLP가 스캔할 때까지 문서를 보호하고 새 파일을 기본적으로 [민감한 파일로 표시하여](/sharepoint/sensitive-by-default)공유할 수 있는 안전한 것으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-205">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="4a9e7-206">권장되는 DLP 정책 구조</span><span class="sxs-lookup"><span data-stu-id="4a9e7-206">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="4a9e7-207">**조건**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-207">**Conditions**</span></span>
        - <span data-ttu-id="4a9e7-208">콘텐츠에는 이러한 중요한 정보 유형이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-208">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="4a9e7-209">콘텐츠는 Microsoft 365 조직 외부의 사용자와 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e7-209">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="4a9e7-210">![민감한 콘텐츠의 외부 공유를 감지하는 DLP 조건](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-210">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="4a9e7-211">**작업**</span><span class="sxs-lookup"><span data-stu-id="4a9e7-211">**Actions**</span></span>
        - <span data-ttu-id="4a9e7-212">외부 사용자의 콘텐츠에 대한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="4a9e7-212">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="4a9e7-213">전자 메일 및 정책 팁을 통해 사용자에게 알림</span><span class="sxs-lookup"><span data-stu-id="4a9e7-213">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="4a9e7-214">관리자에게 인시던트 보고서 보내기</span><span class="sxs-lookup"><span data-stu-id="4a9e7-214">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="4a9e7-215">![민감한 콘텐츠의 외부 공유를 차단하는 DLP 작업](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-215">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="4a9e7-216">중요한 정보가 포함된 SharePoint 문서를 외부 게스트와 공유하려고 할 때 작동하는 DLP 정책:</span><span class="sxs-lookup"><span data-stu-id="4a9e7-216">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4a9e7-217">![외부 공유 차단](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-217">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="4a9e7-218">게스트가 외부 블록이 있는 Teams 문서를 열려고 할 때 작동하는 DLP 정책:</span><span class="sxs-lookup"><span data-stu-id="4a9e7-218">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4a9e7-219">![외부 액세스 차단](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="4a9e7-219">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="4a9e7-220">관련 문서</span><span class="sxs-lookup"><span data-stu-id="4a9e7-220">Related articles</span></span>

[<span data-ttu-id="4a9e7-221">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="4a9e7-221">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="4a9e7-222">DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시</span><span class="sxs-lookup"><span data-stu-id="4a9e7-222">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
