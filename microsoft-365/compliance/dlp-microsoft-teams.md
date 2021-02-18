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
description: 이제 Microsoft Teams 채팅 및 채널에 DLP 정책을 적용할 수 있습니다. 이 문서를 읽고 작동 방식에 대해 자세히 알아보고자 합니다.
ms.openlocfilehash: 13d5d73423cc6ad7db76076f6a53dde668b8fa5c
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279366"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="6c17a-104">데이터 손실 방지 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c17a-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="6c17a-105">데이터 손실 방지 기능은 최근에 Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 정보 보호 및 거버넌스 또는 Office 365 고급 규정 준수 라이선스가 있는 사용자를 위한 Microsoft Teams 채팅 및 채널 메시지에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="6c17a-106">Office 365 및 Microsoft 365 E3에는 SharePoint Online, OneDrive 및 Exchange Online에 대한 DLP 보호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="6c17a-107">여기에는 Teams에서 SharePoint Online 및 OneDrive를 사용하여 파일을 공유하기 때문에 Teams를 통해 공유되는 파일도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="6c17a-108">Teams 채팅에서 DLP 보호를 지원하려면 E5가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="6c17a-109">라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c17a-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c17a-110">Teams용 DLP는 사용자에게 Exchange Online에 사서함이 있는 경우만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-110">DLP for Teams is only supported when the user has a mailbox that is in Exchange Online</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="6c17a-111">Microsoft Teams용 DLP 개요</span><span class="sxs-lookup"><span data-stu-id="6c17a-111">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="6c17a-112">최근에는 [](data-loss-prevention-policies.md) 비공개 채널 메시지를 포함하여 Microsoft Teams 채팅 및 채널 메시지를 포함하기 위해 DLP(데이터 손실 방지) **기능이 확장했습니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-112">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span>

<span data-ttu-id="6c17a-113">조직에 DLP가 있는 경우 이제 사용자가 Microsoft Teams 채널 또는 채팅 세션에서 중요한 정보를 공유하지 못하게 하는 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-113">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="6c17a-114">다음은 이 보호가 작동하는 방식의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-114">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="6c17a-115">**예제 1: 메시지의 중요한 정보 보호.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-115">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="6c17a-116">누군가 Teams 채팅 또는 채널에서 게스트(외부 사용자)와 중요한 정보를 공유하려고 시도하는 경우를 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6c17a-116">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="6c17a-117">이를 방지하는 DLP 정책이 정의되어 있는 경우 외부 사용자에게 전송되는 중요한 정보가 있는 메시지가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-117">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="6c17a-118">이 문제는 DLP 정책이 구성된 방식에 따라 초 내에 자동으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-118">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6c17a-119">Microsoft Teams용 DLP는 사용자가 있는 Microsoft Teams 사용자와 공유할 때 중요한 콘텐츠를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-119">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="6c17a-120">- [팀 및](https://docs.microsoft.com/MicrosoftTeams/guest-access) 채널의 게스트 액세스 또는</span><span class="sxs-lookup"><span data-stu-id="6c17a-120">- [guest access](https://docs.microsoft.com/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="6c17a-121">- [모임 및](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) 채팅 세션의 외부 액세스</span><span class="sxs-lookup"><span data-stu-id="6c17a-121">- [external access](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="6c17a-122">외부 채팅 세션에 대한 DLP는 보낸 사람과 수신자가 둘 다 Teams 전용 모드에 있으며 Microsoft Teams 기본 페더러ation을 사용하는 [경우만 작동됩니다.](https://docs.microsoft.com/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="6c17a-122">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="6c17a-123">Teams용 DLP는 비즈니스용 [](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) Skype 또는 기본이 아닌 페더타 채팅 세션과 상호 연동된 메시지를 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-123">DLP for Teams does not block messages in [interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="6c17a-124">**예제 2: 문서의 중요한 정보 보호**</span><span class="sxs-lookup"><span data-stu-id="6c17a-124">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="6c17a-125">누군가 Microsoft Teams 채널 또는 채팅에서 게스트와 문서를 공유하려고 시도하고 문서에 중요한 정보가 포함되어 있는 경우를 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6c17a-125">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="6c17a-126">이를 방지하는 DLP 정책이 정의되어 있는 경우 해당 사용자에 대해 문서가 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-126">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="6c17a-127">이 경우 보호를 적용하려면 DLP 정책에 SharePoint 및 OneDrive가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-127">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="6c17a-128">이 예제는 Microsoft Teams에 표시하는 SharePoint용 DLP의 예로, 사용자에게 Office 365 DLP(Office 365 E3에 포함)에 대한 라이선스가 필요하지만 사용자에게 Office 365 고급 규정 준수 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-128">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="6c17a-129">정책 팁은 사용자를 교육하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-129">Policy tips help educate users</span></span>

<span data-ttu-id="6c17a-130">[Exchange, Outlook,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)웹용 Outlook, SharePoint Online, 비즈니스용 [OneDrive](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)사이트 및 [Office 데스크톱](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)클라이언트에서 DLP가 작동하는 방식과 마찬가지로 작업이 DLP 정책과 충돌할 때 정책 팁이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-130">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="6c17a-131">정책 팁의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-131">Here's an example of a policy tip:</span></span>

![Teams에서 차단된 메시지 알림](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="6c17a-133">이 경우 보낸 사람이 Microsoft Teams 채널에서 사회 보장 번호를 공유하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-133">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="6c17a-134">What **can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span><span class="sxs-lookup"><span data-stu-id="6c17a-134">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="6c17a-135">이 경우 보낸 사람이 정책을 다시 적용하거나 관리자에게 검토 및 해결을 알리도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-135">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![차단된 메시지 해결 옵션](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="6c17a-137">조직에서 사용자가 DLP 정책을 다시 정할 수 있도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-137">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="6c17a-138">또한 DLP 정책을 구성할 때 기본 정책 팁을 사용하거나 조직의 정책 팁을 사용자 [지정할](#to-customize-policy-tips) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-138">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="6c17a-139">보낸 사람이 Teams 채널에서 사회 보장 번호를 공유한 예제로 돌아가면 받는 사람이 본 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-139">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![메시지가 차단됩니다.](../media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="6c17a-141">**What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span><span class="sxs-lookup"><span data-stu-id="6c17a-141">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="6c17a-142">정책 팁을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="6c17a-142">To customize policy tips</span></span>

<span data-ttu-id="6c17a-143">이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-143">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="6c17a-144">자세한 내용은 [사용 권한을 참조합니다.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="6c17a-144">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="6c17a-145">보안 & 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-145">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="6c17a-146">데이터 **손실 방지 정책을**  >  **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-146">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="6c17a-147">정책을 선택하고 정책 설정 **옆에** 있는 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-147">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="6c17a-148">새 규칙을 만들거나 정책에 대한 기존 규칙을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-148">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![정책 규칙 편집](../media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="6c17a-150">사용자 **알림 탭에서** 전자  메일 텍스트 사용자 지정 및/또는 정책 팁 텍스트 **옵션 사용자 지정을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-150">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="6c17a-151">![사용자 알림 및 정책 팁 사용자 지정](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="6c17a-151">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="6c17a-152">전자 메일 알림 및/또는 정책 팁에 사용할 텍스트를 지정하고 저장을 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-152">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="6c17a-153">정책 설정 **탭에서** 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-153">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="6c17a-154">변경 내용이 데이터 센터를 통해 작동하고 사용자 계정과 동기화할 수 있도록 약 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-154">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="6c17a-155">기존 DLP 정책에 위치로 Microsoft Teams 추가</span><span class="sxs-lookup"><span data-stu-id="6c17a-155">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="6c17a-156">이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-156">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="6c17a-157">자세한 내용은 [사용 권한을 참조합니다.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="6c17a-157">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="6c17a-158">보안 & 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-158">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="6c17a-159">데이터 **손실 방지 정책을**  >  **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-159">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="6c17a-160">정책을 선택하고 위치의 값을 **봐야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-160">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="6c17a-161">Teams 채팅 및 **채널** 메시지가 표시되어 있는 경우 모두 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-161">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="6c17a-162">그렇지 않은 경우 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-162">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="6c17a-163">![기존 정책의 위치](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="6c17a-163">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="6c17a-164">상태 **열에서** Teams 채팅 및 채널 메시지에 대한 **정책을 켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-164">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="6c17a-165">![Teams 채팅 및 채널용 DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="6c17a-165">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="6c17a-166">위치 **선택 탭에서** 모든 계정의 기본 설정을 유지하거나 특정 위치를 선택하도록 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-166">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="6c17a-167">지정할 수 있는 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-167">You can specify:</span></span>
    1. <span data-ttu-id="6c17a-168">포함하거나 제외할 개별 계정 최대 1,000개</span><span class="sxs-lookup"><span data-stu-id="6c17a-168">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="6c17a-169">포함하거나 제외할 메일 그룹 및 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="6c17a-169">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="6c17a-170">**공개 미리 보기 기능입니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-170">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="6c17a-171">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-171">Then choose **Next**.</span></span>



6. <span data-ttu-id="6c17a-172">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-172">Click **Save**.</span></span>

<span data-ttu-id="6c17a-173">변경 내용이 데이터 센터를 통해 작동하고 사용자 계정과 동기화할 수 있도록 약 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-173">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="6c17a-174">Microsoft Teams에 대한 새 DLP 정책 정의</span><span class="sxs-lookup"><span data-stu-id="6c17a-174">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="6c17a-175">이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-175">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="6c17a-176">자세한 내용은 [사용 권한을 참조합니다.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="6c17a-176">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="6c17a-177">보안 & 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-177">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="6c17a-178">데이터 **손실 방지**  >  **정책**  >  **+ 정책 만들기를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-178">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="6c17a-179">서식 파일을 [선택하고](data-loss-prevention-policies.md#dlp-policy-templates)다음을 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-179">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="6c17a-180">이 예제에서는 미국 개인 식별 정보 데이터 템플릿을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-180">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="6c17a-181">![DLP 정책에 대한 개인 정보 템플릿](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="6c17a-181">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="6c17a-182">정책 **이름 탭에서** 정책의 이름과 설명을 지정하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-182">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="6c17a-183">위치 **선택 탭에서** 모든 계정의 기본 설정을 유지하거나 특정 위치를 선택하도록 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-183">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="6c17a-184">지정할 수 있는 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-184">You can specify:</span></span>
    1. <span data-ttu-id="6c17a-185">포함하거나 제외할 개별 계정 최대 1,000개</span><span class="sxs-lookup"><span data-stu-id="6c17a-185">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="6c17a-186">포함하거나 제외할 메일 그룹 및 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="6c17a-186">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="6c17a-187">**공개 미리 보기 기능입니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-187">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

![DLP 정책 위치](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> <span data-ttu-id="6c17a-189">Teams에서 중요한 정보를 포함하는 문서가 부적절하게 공유되지 않는지 확인하려는 경우 Teams 채팅 및 채널 메시지와 함께  **SharePoint** 사이트 및 **OneDrive** 계정이 켜져 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6c17a-189">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>


6. <span data-ttu-id="6c17a-190">정책 설정 **탭의** 보호할 콘텐츠 형식 사용자 지정 **아래에서** 기본 간단한 설정을 유지하거나 고급 설정 사용을 선택한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-190">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="6c17a-191">고급 설정을 선택하는 경우 정책에 대한 규칙을 만들거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-191">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="6c17a-192">이에 대한 도움말을 얻었다면 간단한 설정과 고급 설정을 [참조하세요.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="6c17a-192">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="6c17a-193">정책 설정 **탭의** 중요한 정보를 검색하는 경우 어떤 작업을 하고 **싶나요?** 아래에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-193">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="6c17a-194">(다음은 기본 정책 팁 및 전자 메일 알림을 유지하거나 [사용자](use-notifications-and-policy-tips.md)지정할 수 있는 위치입니다.)</span><span class="sxs-lookup"><span data-stu-id="6c17a-194">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="6c17a-195">![팁 및 알림이 있는 DLP 정책 설정](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="6c17a-195">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="6c17a-196">설정 검토 또는 편집을 마치면 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-196">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="6c17a-197">정책  설정 탭의 정책 설정 탭에서 먼저 정책을 켜거나 테스트할지 여부, 정책을 [켜거나,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)먼저 테스트할지, 아니면 지금 해제된 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-197">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="6c17a-198">![정책을 끄지 여부를 지정합니다.](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="6c17a-198">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="6c17a-199">설정 **검토 탭에서** 새 정책에 대한 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-199">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="6c17a-200">편집을 **선택해** 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-200">Choose **Edit** to make changes.</span></span> <span data-ttu-id="6c17a-201">완료되면 만들기를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c17a-201">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="6c17a-202">새 정책이 데이터 센터를 통해 작동하고 사용자 계정에 동기화하도록 약 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-202">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="6c17a-203">중요한 문서에 대한 외부 액세스 방지</span><span class="sxs-lookup"><span data-stu-id="6c17a-203">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="6c17a-204">중요한 정보가 포함된 SharePoint 문서는 기본적으로 SharePoint 또는 Teams에서 외부 게스트가 액세스할 수 없는지 확인하려면 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-204">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="6c17a-205">DLP에서 검사하고 새 파일을 기본적으로 중요한 것으로 표시하여 문서를 공유하기에 안전한 것으로 표시할 때까지 문서가 보호되도록 [할 수 있습니다.](https://docs.microsoft.com/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="6c17a-205">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](https://docs.microsoft.com/sharepoint/sensitive-by-default)</span></span>
- <span data-ttu-id="6c17a-206">권장 DLP 정책 구조</span><span class="sxs-lookup"><span data-stu-id="6c17a-206">Recommended DLP policy structure</span></span>
    - <span data-ttu-id="6c17a-207">**조건**</span><span class="sxs-lookup"><span data-stu-id="6c17a-207">**Conditions**</span></span>
        - <span data-ttu-id="6c17a-208">콘텐츠에는 다음 중요한 정보 유형이 포함되어 있습니다. [적용되는 모든 정보 선택]</span><span class="sxs-lookup"><span data-stu-id="6c17a-208">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        - <span data-ttu-id="6c17a-209">콘텐츠가 Microsoft 365에서 조직 외부의 사용자와 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c17a-209">Content is shared from Microsoft 365 with people outside my organization</span></span>
        <br/><span data-ttu-id="6c17a-210">![중요한 콘텐츠의 외부 공유를 감지하기 위한 DLP 조건](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="6c17a-210">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span><br/>


    - <span data-ttu-id="6c17a-211">**작업**</span><span class="sxs-lookup"><span data-stu-id="6c17a-211">**Actions**</span></span>
        - <span data-ttu-id="6c17a-212">외부 사용자에 대한 콘텐츠 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="6c17a-212">Restrict access to the content for external users</span></span>
        - <span data-ttu-id="6c17a-213">사용자에게 전자 메일 및 정책 팁 알림</span><span class="sxs-lookup"><span data-stu-id="6c17a-213">Notify users with email and policy tips</span></span>
        - <span data-ttu-id="6c17a-214">관리자에게 문제 보고서 보내기</span><span class="sxs-lookup"><span data-stu-id="6c17a-214">Send incident reports to the Administrator</span></span>    
        <br/>![중요한 콘텐츠의 외부 공유를 차단하기 위한 DLP 작업](../media/dlp-teams-external-sharing/external-action.png)<br/>

<span data-ttu-id="6c17a-216">SharePoint에서 중요한 정보가 포함된 문서를 외부 게스트와 공유하려고 할 때 실행될 DLP 정책:</span><span class="sxs-lookup"><span data-stu-id="6c17a-216">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>
<br/><span data-ttu-id="6c17a-217">![외부 공유 차단](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="6c17a-217">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span><br/>


<span data-ttu-id="6c17a-218">게스트가 외부 차단을 통해 Teams에서 문서를 열려고 시도할 때 실행된 DLP 정책:</span><span class="sxs-lookup"><span data-stu-id="6c17a-218">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>
<br/><span data-ttu-id="6c17a-219">![외부 액세스 차단](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="6c17a-219">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span><br/>

## <a name="related-articles"></a><span data-ttu-id="6c17a-220">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6c17a-220">Related articles</span></span>

[<span data-ttu-id="6c17a-221">DLP 정책 생성, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="6c17a-221">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="6c17a-222">DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시</span><span class="sxs-lookup"><span data-stu-id="6c17a-222">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
