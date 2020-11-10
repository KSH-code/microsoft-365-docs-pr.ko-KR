---
title: 데이터 손실 방지 및 Microsoft 팀
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
description: 이제 Microsoft 팀 채팅 및 채널에 DLP 정책을 적용할 수 있습니다. 이 문서를 읽으면 작동 방식에 대해 자세히 알아볼 수 있습니다.
ms.openlocfilehash: 22f279eaccaed20984a59b9b3ae5655df00b2ae3
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951091"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="ca682-104">데이터 손실 방지 및 Microsoft 팀</span><span class="sxs-lookup"><span data-stu-id="ca682-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="ca682-105">데이터 손실 방지 기능은 최근 Office 365 Advanced Compliance 라이선스 사용자에 대한 Microsoft Teams 채팅 및 채널 메시지에 추가되었으며, 이는 독립 실행형 옵션으로 제공되며 Office 365 E5 및 Microsoft 365 E5 규정 준수에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="ca682-106">Office 365 및 Microsoft 365 E3에는 SharePoint Online, OneDrive 및 Exchange Online에 대 한 DLP 보호 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="ca682-107">또한 팀이 SharePoint Online 및 OneDrive를 사용 하 여 파일을 공유 하기 때문에 팀을 통해 공유 되는 파일도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="ca682-108">팀 대화방에서 DLP 보호를 지원 하려면 E5가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="ca682-109">라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca682-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="ca682-110">Microsoft 팀의 DLP 개요</span><span class="sxs-lookup"><span data-stu-id="ca682-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="ca682-111">최근에 DLP ( [데이터 손실 방지](data-loss-prevention-policies.md) ) 기능은 **개인 채널 메시지를 포함 하 여** Microsoft 팀 채팅 및 채널 메시지를 포함 하도록 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-111">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span>


<span data-ttu-id="ca682-112">조직에 DLP가 있는 경우에는 사용자가 Microsoft 팀 채널 또는 채팅 세션에서 중요 한 정보를 공유 하지 못하도록 하는 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-112">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="ca682-113">다음은 이러한 보호의 작동 방식에 대 한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-113">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="ca682-114">**예 1: 메시지의 중요 한 정보 보호**</span><span class="sxs-lookup"><span data-stu-id="ca682-114">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="ca682-115">다른 사용자가 guests (외부 사용자)를 사용 하 여 팀 채팅 이나 채널에서 중요 한 정보를 공유 하려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-115">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="ca682-116">이를 방지 하기 위해 DLP 정책이 정의 된 경우 외부 사용자에 게 전송 되는 중요 한 정보가 포함 된 메시지가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-116">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="ca682-117">이 작업은 DLP 정책이 구성 되는 방식에 따라 자동으로 몇 초 이내에 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-117">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca682-118">Microsoft 팀의 DLP는 다음을 포함 하는 Microsoft 팀 사용자와 공유할 때 중요 한 콘텐츠를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-118">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="ca682-119">- 팀 및 채널에서의 [게스트 액세스](https://docs.microsoft.com/MicrosoftTeams/guest-access) 사용자나</span><span class="sxs-lookup"><span data-stu-id="ca682-119">- [guest access](https://docs.microsoft.com/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="ca682-120">- 모임 및 채팅 세션의 [외부 액세스](https://docs.microsoft.com/MicrosoftTeams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="ca682-120">- [external access](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="ca682-121">외부 채팅 세션에 대 한 DLP는 보낸 사람과 받는 사람이 모두 팀 전용 모드이 고 [Microsoft 팀 전용 페더레이션을](https://docs.microsoft.com/microsoftteams/manage-external-access)사용 하는 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-121">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="ca682-122">팀에 대 한 DLP는 비즈니스용 Skype 또는 비기본 페더레이션 채팅 세션을 사용한 [interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) 의 메시지를 차단 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-122">DLP for Teams does not block messages in [interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="ca682-123">**예 2: 문서에서 중요 한 정보를 보호** 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-123">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="ca682-124">다른 사용자가 Microsoft 팀 채널 또는 채팅에서 게스트와 문서를 공유 하려고 하지만 문서에 중요 한 정보가 포함 되어 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-124">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="ca682-125">이를 방지 하기 위해 DLP 정책을 정의 하는 경우 해당 사용자에 대 한 문서가 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-125">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="ca682-126">이 경우에는 보호 기능을 적용 하기 위해 DLP 정책에 SharePoint 및 OneDrive가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-126">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="ca682-127">(이는 Microsoft 팀에 표시 되는 SharePoint 용 DLP의 예 이며, 사용자가 office 365 DLP (Office 365 E3에 포함)에 대 한 사용이 허가 되어야 하지만, 사용자에 게 Office 365 고급 규정 준수를 허가할 필요가 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="ca682-127">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="ca682-128">사용자를 교육 하는 데 도움이 되는 정책 팁</span><span class="sxs-lookup"><span data-stu-id="ca682-128">Policy tips help educate users</span></span>

<span data-ttu-id="ca682-129">[Exchange, outlook, 웹용 outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, 비즈니스용 OneDrive 사이트](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)및 [Office 데스크톱 클라이언트](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)에서 dlp가 작동 하는 방식과 마찬가지로, 작업이 DLP 정책과 충돌할 때 정책 팁이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-129">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="ca682-130">정책 팁의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-130">Here's an example of a policy tip:</span></span>

![팀의 차단 된 메시지 알림](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="ca682-132">이 경우 보낸 사람은 Microsoft 팀 채널에서 주민 등록 번호를 공유 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-132">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="ca682-133">어떤 작업을 **수행할 수 있나요?** link에서는이 문제를 해결 하기 위한 옵션을 제공 하는 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-133">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="ca682-134">이 경우 보낸 사람은 정책을 재정의 하도록 선택 하거나 관리자에 게 문의 하 여 검토 하 고 해결 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-134">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![차단 된 메시지 해결 옵션](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="ca682-136">조직에서는 사용자가 DLP 정책을 재정의할 수 있도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-136">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="ca682-137">그리고 DLP 정책을 구성할 때 기본 정책 팁을 사용 하거나 조직에 대 한 [정책 팁을 사용자 지정할](#to-customize-policy-tips) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-137">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="ca682-138">예를 들어 보낸 사람이 팀 채널에서 주민 등록 번호를 공유 하는 경우, 받는 사람에 게 표시 되는 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-138">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![메시지 차단 됨](../media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="ca682-140">" **설명** 합니다." 링크를 선택 하면 메시지가 차단 된 이유를 설명 하는 DLP 정책에 대 한 [문서](data-loss-prevention-policies.md) 를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-140">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="ca682-141">정책 팁을 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="ca682-141">To customize policy tips</span></span>

<span data-ttu-id="ca682-142">이 작업을 수행 하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-142">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="ca682-143">자세한 내용은 [사용 권한을](data-loss-prevention-policies.md#permissions)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca682-143">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="ca682-144">보안 & 준수 센터 ()로 이동 [https://protection.office.com](https://protection.office.com) 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-144">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="ca682-145">**데이터 손실 방지**  >  **정책을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-145">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="ca682-146">정책을 선택 하 고 **정책 설정** 옆에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-146">Select a policy, and next to **Policy settings** , choose **Edit**.</span></span>

4. <span data-ttu-id="ca682-147">새 규칙을 만들거나 정책에 대 한 기존 규칙을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-147">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![정책에 대 한 규칙 편집](../media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="ca682-149">**사용자 알림** 탭에서 **전자 메일 텍스트 사용자 지정** 및/또는 **정책 팁 텍스트 옵션 사용자 지정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-149">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="ca682-150">![사용자 알림 및 정책 팁 사용자 지정](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-150">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="ca682-151">전자 메일 알림 및/또는 정책 팁에 사용할 텍스트를 지정 하 고 **저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-151">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="ca682-152">**정책 설정** 탭에서 **저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-152">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="ca682-153">변경 내용이 데이터 센터를 통해 작동 하 고 사용자 계정과 동기화 되도록 약 1 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-153">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="ca682-154">Microsoft 팀을 기존 DLP 정책에 대 한 위치로 추가</span><span class="sxs-lookup"><span data-stu-id="ca682-154">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="ca682-155">이 작업을 수행 하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-155">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="ca682-156">자세한 내용은 [사용 권한을](data-loss-prevention-policies.md#permissions)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca682-156">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="ca682-157">보안 & 준수 센터 ()로 이동 [https://protection.office.com](https://protection.office.com) 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-157">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="ca682-158">**데이터 손실 방지**  >  **정책을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-158">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="ca682-159">정책을 선택 하 고 **위치** 아래의 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-159">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="ca682-160">**팀 채팅 및 채널 메시지가** 표시 되 면 모든 설정이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-160">If you see **Teams chat and channel messages** , you're all set.</span></span> <span data-ttu-id="ca682-161">그렇지 않으면 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-161">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="ca682-162">![기존 정책에 대 한 위치](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-162">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="ca682-163">**상태** 열에서 **팀 채팅 및 채널 메시지** 에 대 한 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-163">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="ca682-164">![팀 채팅 및 채널에 대 한 DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-164">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="ca682-165">모든 계정의 기본 설정을 유지 하거나 포함 하거나 제외할 계정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-165">Keep the default settings of all accounts, or specify which accounts to include or exclude.</span></span>

6. <span data-ttu-id="ca682-166">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-166">Click **Save**.</span></span>

<span data-ttu-id="ca682-167">변경 내용이 데이터 센터를 통해 작동 하 고 사용자 계정과 동기화 되도록 약 1 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-167">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->
## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="ca682-168">Microsoft 팀에 대 한 새 DLP 정책 정의</span><span class="sxs-lookup"><span data-stu-id="ca682-168">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="ca682-169">이 작업을 수행 하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-169">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="ca682-170">자세한 내용은 [사용 권한을](data-loss-prevention-policies.md#permissions)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca682-170">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="ca682-171">보안 & 준수 센터 ()로 이동 [https://protection.office.com](https://protection.office.com) 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-171">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="ca682-172">**데이터 손실 방지**  >  **정책** 및  >  **정책 만들기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-172">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="ca682-173">[서식 파일](data-loss-prevention-policies.md#dlp-policy-templates)을 선택 하 고 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-173">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="ca682-174">이 예제에서는 미국 개인 식별이 가능한 정보 데이터 서식 파일을 선택 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-174">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="ca682-175">![DLP 정책에 대 한 개인 정보 서식 파일](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-175">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="ca682-176">**정책 이름** 지정 탭에서 정책의 이름과 설명을 입력 하 고 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-176">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="ca682-177">**위치 선택** 탭에서 모든 위치의 기본 설정을 유지 하거나, **특정 위치 선택 허용** 을 선택 하 고 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-177">On the **Choose locations** tab, keep the default setting of all locations, or select **Let me choose specific locations** , and then choose **Next**.</span></span><br/><span data-ttu-id="ca682-178">특정 위치를 선택 하는 경우 DLP 정책에 대해이를 선택한 후 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-178">If you chose specific locations, select them for your DLP policy, and then choose **Next**.</span></span><br/><span data-ttu-id="ca682-179">![DLP 정책 위치](../media/dlp-teams-selectlocationsnewpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-179">![DLP policy locations](../media/dlp-teams-selectlocationsnewpolicy.png)</span></span><br/>
    > [!NOTE]
    > <span data-ttu-id="ca682-180">중요 한 정보가 포함 된 문서가 팀에서 잘못 공유 되지 않도록 하려면 **팀 채팅 및 채널 메시지** 와 함께 **SharePoint 사이트** 와 **OneDrive 계정이** 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-180">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

<br/>

6. <span data-ttu-id="ca682-181">**정책 설정** 탭의 **보호 하려는 콘텐츠 형식 사용자 지정** 에서 기본 설정을 유지 하거나 **고급 설정 사용** 을 선택 하 고 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-181">On the **Policy settings** tab, under **Customize the type of content you want to protect** , keep the default simple settings, or choose **Use advanced settings** , and then choose **Next**.</span></span> <span data-ttu-id="ca682-182">고급 설정을 선택 하는 경우 정책에 대 한 규칙을 만들거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-182">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="ca682-183">이에 대 한 도움말을 보려면 [단순 설정 및 고급 설정을](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca682-183">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="ca682-184">**정책 설정** 탭의 **중요 한 정보를 검색 하는 경우 어떤** 작업을 수행 하 시겠습니까?에서 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-184">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?** , review the settings.</span></span> <span data-ttu-id="ca682-185">(여기에서 기본 [정책 팁과 전자 메일 알림을](use-notifications-and-policy-tips.md)유지 하거나 사용자 지정할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="ca682-185">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="ca682-186">![팁 및 알림이 포함 된 DLP 정책 설정](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-186">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="ca682-187">설정 검토 또는 편집을 마친 후 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-187">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="ca682-188">**정책 설정** 탭의 정책을 **설정 하거나 먼저 테스트를 수행** 하 시겠습니까?에서 정책을 켤 지, [먼저](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)테스트를 시작할지, 지금은 해제를 선택 하 고 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-188">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?** , choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="ca682-189">![정책을 켤 지 여부를 지정 합니다.](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-189">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="ca682-190">**설정 검토** 탭에서 새 정책에 대 한 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-190">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="ca682-191">**편집** 을 선택 하 여 변경 내용을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-191">Choose **Edit** to make changes.</span></span> <span data-ttu-id="ca682-192">작업이 완료 되 면 **만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-192">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="ca682-193">새 정책이 데이터 센터를 통해 작동 하 고 사용자 계정과 동기화 되도록 약 1 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-193">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="ca682-194">중요 한 문서에 대 한 외부 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="ca682-194">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="ca682-195">중요 한 정보를 포함 하는 SharePoint 문서를 SharePoint 또는 팀의 외부 게스트에서 기본적으로 액세스할 수 없도록 하려면 다음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-195">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="ca682-196">[새 파일을 기본적으로 중요 한 것으로 표시](https://docs.microsoft.com/sharepoint/sensitive-by-default) 하 여 DLP가 검색 되어 공유 해도 안전한 것으로 표시 될 때까지 문서가 보호 되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca682-196">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](https://docs.microsoft.com/sharepoint/sensitive-by-default)</span></span>
- <span data-ttu-id="ca682-197">권장 DLP 정책 구조</span><span class="sxs-lookup"><span data-stu-id="ca682-197">Recommended DLP policy structure</span></span>
    - <span data-ttu-id="ca682-198">**조건**</span><span class="sxs-lookup"><span data-stu-id="ca682-198">**Conditions**</span></span>
        - <span data-ttu-id="ca682-199">콘텐츠에는 다음 중요 한 정보 유형이 포함 됩니다. [모두 선택]</span><span class="sxs-lookup"><span data-stu-id="ca682-199">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        - <span data-ttu-id="ca682-200">콘텐츠가 Microsoft 365에서 조직 외부의 사용자와 공유 됨</span><span class="sxs-lookup"><span data-stu-id="ca682-200">Content is shared from Microsoft 365 with people outside my organization</span></span>
        <br/><span data-ttu-id="ca682-201">![중요 한 콘텐츠의 외부 공유를 검색 하기 위한 DLP 조건](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-201">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span><br/>


    - <span data-ttu-id="ca682-202">**작업**</span><span class="sxs-lookup"><span data-stu-id="ca682-202">**Actions**</span></span>
        - <span data-ttu-id="ca682-203">외부 사용자에 대 한 콘텐츠에 대 한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="ca682-203">Restrict access to the content for external users</span></span>
        - <span data-ttu-id="ca682-204">전자 메일 및 정책 팁으로 사용자에 게 알림</span><span class="sxs-lookup"><span data-stu-id="ca682-204">Notify users with email and policy tips</span></span>
        - <span data-ttu-id="ca682-205">관리자에 게 문제 보고서 보내기</span><span class="sxs-lookup"><span data-stu-id="ca682-205">Send incident reports to the Administrator</span></span>    
        <br/>![중요 콘텐츠의 외부 공유를 차단 하는 DLP 작업](../media/dlp-teams-external-sharing/external-action.png)<br/>

<span data-ttu-id="ca682-207">외부 게스트가 중요 한 정보를 포함 하는 SharePoint에서 문서를 공유 하려고 할 때 수행 되는 DLP 정책:</span><span class="sxs-lookup"><span data-stu-id="ca682-207">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>
<br/><span data-ttu-id="ca682-208">![외부 공유 차단 됨](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-208">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span><br/>


<span data-ttu-id="ca682-209">게스트에서 외부 차단 된 팀의 문서를 열려고 할 때 수행 되는 DLP 정책:</span><span class="sxs-lookup"><span data-stu-id="ca682-209">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>
<br/><span data-ttu-id="ca682-210">![외부 액세스 차단 됨](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="ca682-210">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span><br/>

## <a name="related-articles"></a><span data-ttu-id="ca682-211">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ca682-211">Related articles</span></span>

[<span data-ttu-id="ca682-212">DLP 정책 생성, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="ca682-212">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="ca682-213">DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시</span><span class="sxs-lookup"><span data-stu-id="ca682-213">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
