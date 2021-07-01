---
title: DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: DLP(데이터 손실 방지) 정책에 정책 팁을 추가하여 사용자에게 DLP 정책과 충돌하는 콘텐츠를 사용 중일 때 이를 알리는 방법을 학습합니다.
ms.openlocfilehash: 53a4db6cfc37f35422a1efffaeac052370cd5988
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228654"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="b6620-103">DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시</span><span class="sxs-lookup"><span data-stu-id="b6620-103">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="b6620-104">DLP(데이터 손실 방지) 정책을 사용하여 Office 365에서 중요한 정보를 식별, 모니터링 및 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-104">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365.</span></span> <span data-ttu-id="b6620-105">이 중요한 정보로 작업하는 조직의 사람들이 DLP 정책을 준수하도록 하지만 불필요하게 작업을 완료하는 것을 차단하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-105">You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done.</span></span> <span data-ttu-id="b6620-106">이러한 경우 전자 메일 알림과 정책 팁이 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-106">This is where email notifications and policy tips can help.</span></span>

![메시지 표시줄에서는 Excel 2016 정책 팁](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

<span data-ttu-id="b6620-108">정책 팁은 다른 사용자가 D Excel LP 정책과 충돌하는 콘텐츠로 작업할 때 나타나는 알림 또는 경고입니다. 예를 들어 PII(개인 식별 정보)를 포함하며 외부 사용자와 공유되는 비즈니스용 OneDrive 사이트의 비즈니스용 OneDrive 통합 문서와 같은 콘텐츠.</span><span class="sxs-lookup"><span data-stu-id="b6620-108">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>

<span data-ttu-id="b6620-109">전자 메일 알림 및 정책 팁을 사용하여 인식을 높이고 조직의 정책에 대해 교육할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-109">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies.</span></span> <span data-ttu-id="b6620-110">유효한 업무상 필요한 경우나 정책이 가짓 긍정을 감지하는 경우 차단되지 않을 수 있도록 정책을 다시 설정하는 옵션을 사용자들에게 제공 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-110">You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>

<span data-ttu-id="b6620-111">준수 센터에서 DLP 정책을 만들 때 다음에 대한 사용자 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-111">In the Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>

- <span data-ttu-id="b6620-112">문제를 설명하는 전자 메일 알림을 선택한 사용자에 보내기</span><span class="sxs-lookup"><span data-stu-id="b6620-112">Send an email notification to the people you choose that describes the issue.</span></span>
> [!NOTE]
> <span data-ttu-id="b6620-113">알림 전자 메일은 보호되지 않은 것으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-113">Notification emails are sent unprotected.</span></span>

- <span data-ttu-id="b6620-114">DLP 정책과 충돌하는 콘텐츠에 대한 정책 팁을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-114">Display a policy tip for content that conflicts with the DLP policy:</span></span>

  - <span data-ttu-id="b6620-115">웹용 Outlook 및 Outlook 2013 이상에서 전자 메일의 경우 정책 팁은 메시지가 작성되는 동안 받는 사람 위에 있는 메시지의 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-115">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>

  - <span data-ttu-id="b6620-116">온라인 비즈니스용 OneDrive 또는 SharePoint 문서의 경우 정책 팁은 항목에 나타나는 경고 아이콘으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-116">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item.</span></span> <span data-ttu-id="b6620-117">자세한 내용을 확인하려면 항목을 선택한 다음  페이지의 오른쪽 위 모서리에 있는 정보 정보 창 아이콘을 선택하여 세부 정보 창을 열 ![ 수 ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-117">To view more information, you can select an item and then choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span>

  - <span data-ttu-id="b6620-118">DLP 정책에 Excel 사이트 또는 SharePoint Online 사이트에 저장된 Excel, PowerPoint 및 Word 문서의 경우 정책 팁이 메시지 표시줄 및 Backstage 보기(파일 메뉴 \> **정보)에** 표시됩니다 비즈니스용 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b6620-118">For Excel, PowerPoint, and Word documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view (**File** menu \> **Info**).</span></span>

## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="b6620-119">DLP 정책에 사용자 알림 추가</span><span class="sxs-lookup"><span data-stu-id="b6620-119">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="b6620-120">DLP 정책을 만들 때 사용자 알림을 **사용하도록 설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b6620-120">When you create a DLP policy, you can enable **User notifications**.</span></span> <span data-ttu-id="b6620-121">사용자 알림을 사용하도록 설정하면 Microsoft 365 알림과 정책 팁이 모두 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-121">When user notifications are enabled, Microsoft 365 sends out both email notifications and policy tips.</span></span> <span data-ttu-id="b6620-122">알림 전자 메일을 보낸 사용자, 전자 메일 텍스트 및 정책 팁 텍스트를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-122">You can customize who notification emails are sent to, the email text and the policy tip text.</span></span>

1. <span data-ttu-id="b6620-123">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-123">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="b6620-124">회사 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-124">Sign in using your work or school account.</span></span> <span data-ttu-id="b6620-125">이제 보안 및 준수 &amp; 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-125">You're now in the Security &amp; Compliance Center.</span></span>

3. <span data-ttu-id="b6620-126">보안 및 준수 &amp; 센터 왼쪽 탐색 데이터 손실 \> \> **방지** \> **정책** \> **+ 정책 만들기에서**.</span><span class="sxs-lookup"><span data-stu-id="b6620-126">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>

    ![정책 단추 만들기](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)

4. <span data-ttu-id="b6620-128">다음에 필요한 중요한 정보 유형을 보호하는 DLP 정책 템플릿을 \> **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b6620-128">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>

    <span data-ttu-id="b6620-129">빈 템플릿으로 시작하고 사용자 지정 **사용자** 지정 \> **정책 다음 을** \> **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b6620-129">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>

5. <span data-ttu-id="b6620-130">정책 이름을 \> 다음으로 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6620-130">Name the policy \> **Next**.</span></span>

6. <span data-ttu-id="b6620-131">DLP 정책이 보호할 위치를 선택하려는 경우 다음 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-131">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>

   - <span data-ttu-id="b6620-132">다음 **에서** 모든 위치를 \> **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="b6620-132">Choose **All locations in Office 365** \> **Next**.</span></span>

   - <span data-ttu-id="b6620-133">Let **me choose specific locations Next(다음으로 특정 위치 선택)** \> **를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="b6620-133">Choose **Let me choose specific locations** \> **Next**.</span></span>

   <span data-ttu-id="b6620-134">모든 Exchange 또는 모든 OneDrive 계정과 같은 전체 위치를 포함하거나 제외하기  위해 해당 위치의 상태를 켜거나 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-134">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span>

   <span data-ttu-id="b6620-135">특정 SharePoint 또는 OneDrive 계정만 포함하려면 상태를 켜기로 전환한 다음 포함 아래의  링크를 클릭하여 특정 사이트 또는 계정을 선택하세요. </span><span class="sxs-lookup"><span data-stu-id="b6620-135">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span>

7. <span data-ttu-id="b6620-136">고급 **설정 사용 다음** \> **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6620-136">Choose **Use advanced settings** \> **Next**.</span></span>

8. <span data-ttu-id="b6620-137">**+ 새 규칙** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-137">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="b6620-138">규칙 편집기에서 **사용자 알림에서** 상태를 으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-138">In the rule editor, under **User notifications**, switch the status on.</span></span>

    ![규칙 편집기에서 사용자 알림 섹션](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> <span data-ttu-id="b6620-140">DLP 정책은 해당 문서가 새 문서이든 기존 문서이든 정책과 일치하는 모든 문서에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-140">DLP policies apply to all documents that match the policy, whether those documents are new or existing.</span></span> <span data-ttu-id="b6620-141">그러나 전자 메일 알림은 새 콘텐츠가 기존 DLP 정책과 일치하는 경우만 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-141">However, an email notification is only generated when new content matches an existing DLP policy.</span></span> <span data-ttu-id="b6620-142">기존 콘텐츠는 보호되지만 전자 메일을 통해 사용자 알림을 생성하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-142">Existing content is protected, but will not generate a user notification via email.</span></span>

## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="b6620-143">전자 메일 알림을 구성하기 위한 옵션</span><span class="sxs-lookup"><span data-stu-id="b6620-143">Options for configuring email notifications</span></span>

<span data-ttu-id="b6620-144">DLP 정책의 각 규칙에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-144">For each rule in a DLP policy, you can:</span></span>

- <span data-ttu-id="b6620-p107">선택한 사람에게 알림을 보냅니다. 이러한 사용자에는 콘텐츠의 소유자, 콘텐츠를 마지막으로 수정한 사람, 콘텐츠가 저장된 사이트의 소유자 또는 특정 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p107">Send the notification to the people you choose. These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>

- <span data-ttu-id="b6620-147">HTML 또는 토큰을 사용하여 알림에 포함된 텍스트를 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-147">Customize the text that's included in the notification by using HTML or tokens.</span></span> <span data-ttu-id="b6620-148">자세한 내용은 아래 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6620-148">See the section below for more information.</span></span>

> [!NOTE]
>  <span data-ttu-id="b6620-149">전자 메일 알림은 그룹이나 메일 그룹이 아닌 개별 받는 사람에게만 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-149">Email notifications can be sent only to individual recipients—not groups or distribution lists.</span></span> <span data-ttu-id="b6620-150">새 콘텐츠만 전자 메일 알림을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-150">Only new content will trigger an email notification.</span></span> <span data-ttu-id="b6620-151">기존 콘텐츠를 편집하면 정책 팁이 트리거되지만 전자 메일 알림은 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-151">Editing existing content will trigger policy tips, but not an email notification.</span></span>

![전자 메일 알림 옵션](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)

### <a name="default-email-notification&quot;></a><span data-ttu-id=&quot;b6620-153&quot;>기본 전자 메일 알림</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;b6620-153&quot;>Default email notification</span></span>

<span data-ttu-id=&quot;b6620-154&quot;>알림에는 수행한 작업으로 시작되는 제목 줄(예: 전자 메일의 경우 &quot;알림&quot;, &quot;메시지 차단&quot; 또는 문서의 경우 &quot;액세스 차단")이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-154">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents.</span></span> <span data-ttu-id="b6620-155">알림이 문서에 대한 알림인 경우 알림 메시지 본문에는 문서가 저장된 사이트로 연결하고 문서에 대한 정책 팁을 여는 링크가 포함되어 있으며, 이 링크를 통해 문제를 해결할 수 있습니다(정책 팁에 대한 내용은 아래 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="b6620-155">If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips).</span></span> <span data-ttu-id="b6620-156">알림이 메시지에 대한 경우 알림에는 DLP 정책과 일치하는 메시지의 첨부 파일로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-156">If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>

![알림 메시지](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)

<span data-ttu-id="b6620-p111">기본적으로 알림에는 사이트의 항목에 대해 다음과 비슷한 텍스트가 표시됩니다. 알림 텍스트는 각 규칙에 대해 별도로 구성되므로 일치하는 규칙에 따라 표시되는 텍스트가 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p111">By default, notifications display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="b6620-160">**DLP 정책 규칙이 수행하는 작업...**</span><span class="sxs-lookup"><span data-stu-id="b6620-160">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="b6620-161">**그런 다음 SharePoint 또는 비즈니스용 OneDrive 기본 알림에 다음이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b6620-161">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="b6620-162">**그런 다음 메시지의 기본 Outlook 다음 메시지가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b6620-162">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b6620-163">알림을 보내지만 다시 설정은 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-163">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="b6620-164">이 항목이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-164">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="b6620-165">전자 메일 메시지가 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-165">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="b6620-166">액세스를 차단하고, 알림을 보내고, 재정의를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-166">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="b6620-167">이 항목이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-167">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="b6620-168">이 충돌을 해결하지 않으면 이 파일에 대한 액세스가 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-168">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="b6620-169">전자 메일 메시지가 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-169">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="b6620-170">메시지가 모든 받는 사람에게 배달되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-170">The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="b6620-171">액세스를 차단하고 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-171">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="b6620-p114">이 항목이 조직의 정책과 충돌합니다. 소유자, 마지막 수정자 및 주 사이트 모음 관리자를 제외한 모든 사람의 이 항목 액세스가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p114">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="b6620-174">전자 메일 메시지가 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-174">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="b6620-175">메시지가 모든 받는 사람에게 배달되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-175">The message wasn't delivered to all recipients.</span></span>  <br/> |

### <a name="custom-email-notification"></a><span data-ttu-id="b6620-176">사용자 지정 전자 메일 알림</span><span class="sxs-lookup"><span data-stu-id="b6620-176">Custom email notification</span></span>

<span data-ttu-id="b6620-177">최종 사용자 또는 관리자에게 기본 전자 메일 알림을 보내는 대신 사용자 지정 전자 메일 알림을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-177">You can create a custom email notification instead of sending the default email notification to your end users or admins.</span></span> <span data-ttu-id="b6620-178">사용자 지정 전자 메일 알림은 HTML을 지원하며 5,000자 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-178">The custom email notification supports HTML and has a 5,000-character limit.</span></span> <span data-ttu-id="b6620-179">HTML을 사용하여 알림에 이미지, 서식 및 기타 브랜드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-179">You can use HTML to include images, formatting, and other branding in the notification.</span></span>

<span data-ttu-id="b6620-180">다음 토큰을 사용하여 전자 메일 알림을 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-180">You can also use the following tokens to help customize the email notification.</span></span> <span data-ttu-id="b6620-181">이러한 토큰은 전송되는 알림의 특정 정보로 대체되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-181">These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="b6620-182">**토큰**</span><span class="sxs-lookup"><span data-stu-id="b6620-182">**Token**</span></span>|<span data-ttu-id="b6620-183">**설명**</span><span class="sxs-lookup"><span data-stu-id="b6620-183">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6620-184">%%AppliedActions%%</span><span class="sxs-lookup"><span data-stu-id="b6620-184">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="b6620-185">콘텐츠에 적용된 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-185">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="b6620-186">%%ContentURL%%</span><span class="sxs-lookup"><span data-stu-id="b6620-186">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="b6620-187">SharePoint 온라인 사이트 또는 비즈니스용 OneDrive URL입니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-187">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="b6620-188">%%MatchedConditions%%</span><span class="sxs-lookup"><span data-stu-id="b6620-188">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="b6620-189">콘텐츠와 일치하는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-189">The conditions that were matched by the content.</span></span> <span data-ttu-id="b6620-190">이 토큰을 사용하여 콘텐츠에 대한 가능한 문제를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-190">Use this token to inform people of possible issues with the content.</span></span>  <br/> |

![토큰이 나타나는 위치를 표시하는 알림 메시지](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)

## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="b6620-192">정책 팁 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="b6620-192">Options for configuring policy tips</span></span>

<span data-ttu-id="b6620-193">DLP 정책의 각 규칙에 대해 다음을 수행하도록 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-193">For each rule in a DLP policy, you can configure policy tips to:</span></span>

- <span data-ttu-id="b6620-194">콘텐츠가 DLP 정책과 충돌한다는 사실을 사용자에게 알려 충돌 해결을 위한 조치를 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-194">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict.</span></span> <span data-ttu-id="b6620-195">기본 텍스트(아래 표 참조)를 사용하거나 조직의 특정 정책에 대한 사용자 지정 텍스트를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-195">You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>

- <span data-ttu-id="b6620-p120">DLP 정책을 재정의할 수 있도록 허용합니다. 필요에 따라 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p120">Allow the person to override the DLP policy. Optionally, you can:</span></span>

  - <span data-ttu-id="b6620-198">사용자에게 정책을 재정의하기 위한 업무 정당성을 입력하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-198">Require the person to enter a business justification for overriding the policy.</span></span> <span data-ttu-id="b6620-199">이 정보는 기록되어 있으며 보안 및 준수 센터의  보고서 섹션에 있는 DLP 보고서에서 볼 &amp; 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-199">This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span>

  - <span data-ttu-id="b6620-p122">가양성을 보고하고 DLP 정책을 재정의할 수 있도록 허용합니다. 이 정보 또한 보고를 위해 기록되므로 가양성을 사용하여 규칙을 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p122">Allow the person to report a false positive and override the DLP policy. This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>

![정책 팁 옵션](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)

<span data-ttu-id="b6620-203">예를 들어 PII(개인 식별 정보)를 검색하는 비즈니스용 OneDrive 사이트에 DLP 정책을 적용할 수 있으며 이 정책에는 다음 세 가지 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-203">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>

1. <span data-ttu-id="b6620-p123">첫 번째 규칙: 문서에서 이 중요한 정보의 인스턴스가 5개 미만으로 검색되었으며 문서가 조직 내부의 사용자와 공유될 경우 **알림 보내기** 작업이 정책 팁을 표시합니다. 이 규칙은 단순히 사용자에게 알리고 액세스를 차단하지는 않으므로 정책 팁에 대해 재정의 옵션은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p123">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip. For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span>

2. <span data-ttu-id="b6620-206">두 번째 규칙: 문서에서 이 중요한 정보의 인스턴스가 6개 이상으로 검색되었으며 문서가 조직 내부의 사용자와 공유될 경우 **콘텐츠에 대한 액세스 차단** 작업은 파일에 대한 사용 권한을 제한하고, **알림 보내기** 작업은 사용자가 업무 정당성을 제공하여 이 규칙의 작업을 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-206">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification.</span></span> <span data-ttu-id="b6620-207">조직의 비즈니스에서 내부 사람이 PII 데이터를 공유해야 하는 경우도 있으며 DLP 정책이 이 작업을 차단하지 못하게 하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-207">Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span>

3. <span data-ttu-id="b6620-p125">세 번째 규칙: 문서에서 이 중요한 정보의 인스턴스가 6개 이상으로 검색되었으며 문서가 조직 외부의 사용자와 공유될 경우 **콘텐츠에 대한 액세스 차단** 작업은 파일에 대한 사용 권한을 제한하고, 이 정보가 외부로 공유될 수 있으므로 **알림 보내기** 작업은 사용자가 이 규칙의 작업을 재정의할 수 없도록 합니다. 어떠한 경우에도 조직의 사용자가 PII 데이터를 조직 외부와 공유하도록 허용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p125">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally. Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span>

<span data-ttu-id="b6620-210">다음을 통해 정책 팁을 사용하여 규칙을 재정의하는 방법을 보다 잘 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-210">Here are some fine points to understand about using a policy tip to override a rule:</span></span>

- <span data-ttu-id="b6620-211">이 옵션은 규칙에 따라 수행하며, 은(는) 규칙의 모든 작업을 어버린 것입니다(알림 보내기 제외).</span><span class="sxs-lookup"><span data-stu-id="b6620-211">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>

- <span data-ttu-id="b6620-212">콘텐츠가 DLP 정책의 여러 규칙과 일치할 수 있지만 가장 제한적인 가장 높은 우선 순위 규칙의 정책 팁만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-212">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown.</span></span> <span data-ttu-id="b6620-213">예를 들어 알림을 콘텐츠 액세스를 차단하는 규칙의 정책 팁은 단순히 알림을 보내는 규칙의 정책 팁보다 우선적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-213">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="b6620-214">따라서 정책 팁이 단계별로 표시되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-214">This prevents people from seeing a cascade of policy tips.</span></span>

- <span data-ttu-id="b6620-215">가장 제한적인 규칙의 정책 팁이 사용자의 규칙 재정의를 허용할 경우 이 규칙을 재정의하면 해당 콘텐츠가 일치하는 다른 모든 규칙이 함께 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-215">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>

## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="b6620-216">비즈니스용 OneDrive 사이트 및 SharePoint Online 사이트에 대한 정책 팁</span><span class="sxs-lookup"><span data-stu-id="b6620-216">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="b6620-217">비즈니스용 OneDrive 또는 SharePoint Online 사이트의 문서가 DLP 정책의 규칙과 일치하고 해당 규칙이 정책 팁을 사용하는 경우 정책 팁은 문서에 특수 아이콘을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-217">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>

1. <span data-ttu-id="b6620-218">규칙이 파일에 대한 알림을 보내는 경우 경고 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-218">If the rule sends a notification about the file, the warning icon appears.</span></span>

2. <span data-ttu-id="b6620-219">규칙이 문서 액세스를 차단하는 경우 차단됨 아이콘이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-219">If the rule blocks access to the document, the blocked icon appears.</span></span>

   ![계정의 문서에 대한 정책 팁 OneDrive 아이콘](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)

<span data-ttu-id="b6620-221">문서에 대한 작업을 수행하려면 페이지의 오른쪽 위 모서리에 있는 정보 정보 창 아이콘을 선택하여 세부 정보 창 보기 정책 팁 을 열 수 \>  ![ ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b6620-221">To take action on a document, you can select an item \> choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>

<span data-ttu-id="b6620-222">정책 팁에 콘텐츠에 대한 문제가 표시되고, 정책 팁이 이러한 옵션을 사용하여 구성되어 있으면 정책 팁 **해결**, **재정의** 를 선택하거나 가양성 **보고** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-222">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span>

![정책 팁을 표시하는 정보 창](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)

![무시 하는 옵션을 사용 하 여 정책 설명](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)

<span data-ttu-id="b6620-p127">DLP 정책은 사이트와 동기화되고 정책을 기준으로 콘텐츠가 주기적으로 비동기적으로 평가되므로 DLP 정책을 만들고 빠른 시간 내에 정책 팁이 제공될 수 있습니다. 마찬가지로 정책 팁을 해결하거나 재정의한 다음 얼마 되지 않아 사이트에 있는 문서에서 해당 아이콘이 없어집니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p127">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips. There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>

### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="b6620-227">사이트의 정책 팁 기본 텍스트</span><span class="sxs-lookup"><span data-stu-id="b6620-227">Default text for policy tips on sites</span></span>

<span data-ttu-id="b6620-p128">기본적으로 정책 팁에는 사이트의 항목에 대해 다음과 비슷한 텍스트가 표시됩니다. 알림 텍스트는 각 규칙에 대해 별도로 구성되므로 일치하는 규칙에 따라 표시되는 텍스트가 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p128">By default, policy tips display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="b6620-230">**DLP 정책 규칙이 수행하는 작업...**</span><span class="sxs-lookup"><span data-stu-id="b6620-230">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="b6620-231">**기본 정책 팁에 표시되는 내용...**</span><span class="sxs-lookup"><span data-stu-id="b6620-231">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6620-232">알림을 보내지만 다시 설정은 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-232">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="b6620-233">이 항목이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-233">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="b6620-234">액세스를 차단하고, 알림을 보내고, 재정의를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-234">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="b6620-235">이 항목이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-235">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="b6620-236">이 충돌을 해결하지 않으면 이 파일에 대한 액세스가 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-236">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="b6620-237">액세스를 차단하고 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-237">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="b6620-p130">이 항목이 조직의 정책과 충돌합니다. 소유자, 마지막 수정자 및 주 사이트 모음 관리자를 제외한 모든 사람의 이 항목 액세스가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p130">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |

### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="b6620-240">사이트의 정책 팁에 대한 사용자 지정 텍스트</span><span class="sxs-lookup"><span data-stu-id="b6620-240">Custom text for policy tips on sites</span></span>

<span data-ttu-id="b6620-241">정책 팁에 대한 텍스트를 전자 메일 알림과 별도로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-241">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="b6620-242">전자 메일 알림에 대한 사용자 지정 텍스트(위 섹션 참조)와 달리 정책 팁에 대한 사용자 지정 텍스트는 HTML 또는 토큰을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-242">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="b6620-243">대신 정책 팁에 대한 사용자 지정 텍스트는 256자 제한이 있는 일반 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-243">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>

## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="b6620-244">2013 이상 웹용 Outlook 및 Outlook 정책 팁</span><span class="sxs-lookup"><span data-stu-id="b6620-244">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="b6620-245">웹용 Outlook 및 Outlook 2013 이상에서 새 전자 메일을 작성하면 DLP 정책의 규칙과 일치하는 콘텐츠를 추가하고 해당 규칙에서 정책 팁을 사용하는 경우 정책 팁이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-245">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips.</span></span> <span data-ttu-id="b6620-246">정책 팁은 메시지가 작성되는 동안 메시지 위쪽의 받는 사람 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-246">The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>

![작성되는 메시지 맨 위에 있는 정책 팁](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)

<span data-ttu-id="b6620-248">정책 팁은 메시지 본문, 제목 줄 또는 메시지 첨부 파일에 중요한 정보가 표시되는지 여부에 따라 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-248">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>

![첨부 파일이 DLP 정책과 충돌하는 경우를 보여주는 정책 팁](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)

<span data-ttu-id="b6620-250">정책 팁이 다시 적용을 허용하도록 구성된 경우  자세한 정보 다시 적용 표시를 선택하고 비즈니스 사정을 입력하거나 가짓 긍정 다시 적용을 보고할 \>  \> 수 \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b6620-250">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>

![메시지의 정책 팁이 확장되고 정책 팁이 확장되고 정책 팁이 추가됩니다.](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)

![정책 팁을 다시 정할 수 있는 정책 팁 대화 상자](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)

<span data-ttu-id="b6620-253">전자 메일에 중요한 정보를 추가할 때 중요한 정보가 추가되는 시간과 정책 팁이 표시될 때 사이에 대기 시간이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-253">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="b6620-254">Outlook 2013 이상에서는 일부 조건에 대한 정책 팁 표시 지원</span><span class="sxs-lookup"><span data-stu-id="b6620-254">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="b6620-255">현재 Outlook 2013 이상에서는 다음 조건에 대한 정책 팁만 표시하는 것이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-255">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="b6620-256">콘텐츠 포함</span><span class="sxs-lookup"><span data-stu-id="b6620-256">Content contains</span></span>
- <span data-ttu-id="b6620-257">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="b6620-257">Content is shared</span></span>

<span data-ttu-id="b6620-258">예외는 조건으로 간주되어 있으며 이러한 모든 조건은 콘텐츠와 일치하고 Outlook 보호 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-258">Note that Exceptions are considered conditions and all of these conditions work in Outlook, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="b6620-259">그러나 사용자에게 정책 팁을 표시하는 것은 아직 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-259">But showing policy tips to users is not yet supported.</span></span>

### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a><span data-ttu-id="b6620-260">보안 및 준수 Exchange 정책 팁 &amp;</span><span class="sxs-lookup"><span data-stu-id="b6620-260">Policy tips in the Exchange admin center vs. the Security &amp; Compliance Center</span></span>

<span data-ttu-id="b6620-261">정책 팁은 Exchange 관리 센터에서 만든 DLP 정책 및 메일 흐름 규칙 또는 보안 및 준수 센터에서 만든 DLP 정책을 사용할 수 있지만 둘 다 사용할 &amp; 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-261">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security &amp; Compliance Center, but not both.</span></span> <span data-ttu-id="b6620-262">이러한 정책은 서로 다른 위치에 저장되지만 정책 팁은 단일 위치에서만 그릴 수 있기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-262">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>

<span data-ttu-id="b6620-263">Exchange 관리 센터에서 정책 팁을 구성한 경우 웹용 Outlook 및 Outlook 2013 이상에서 구성한 정책 팁은 Exchange 관리 센터에서 팁을 끄기 전까지는 웹용 Outlook 및 Outlook 2013 이상의 사용자에게 나타나지 &amp; 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-263">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="b6620-264">이렇게 하면 보안 준수 Exchange 전환할 때까지 현재 메일 흐름 규칙(전송 규칙)이 계속 &amp; 작동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-264">This ensures that your current Exchange mail flow rules (also known as transport rules) will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="b6620-265">정책 팁은 단일 위치에서만 그릴 수 있는 반면, 보안 및 준수 센터와 Exchange 관리 센터 둘 다에서 DLP 정책을 사용하는 경우에도 전자 메일 알림이 항상 &amp; 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-265">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange admin center.</span></span>

### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="b6620-266">전자 메일의 정책 팁에 대한 기본 텍스트</span><span class="sxs-lookup"><span data-stu-id="b6620-266">Default text for policy tips in email</span></span>

<span data-ttu-id="b6620-267">기본적으로 정책 팁에는 전자 메일에 대해 다음과 비슷한 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-267">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="b6620-268">**DLP 정책 규칙이 수행하는 작업...**</span><span class="sxs-lookup"><span data-stu-id="b6620-268">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="b6620-269">**기본 정책 팁에 표시되는 내용...**</span><span class="sxs-lookup"><span data-stu-id="b6620-269">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6620-270">알림을 보내지만 다시 설정은 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-270">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="b6620-271">전자 메일이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-271">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="b6620-272">액세스를 차단하고, 알림을 보내고, 재정의를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-272">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="b6620-273">전자 메일이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-273">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="b6620-274">액세스를 차단하고 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-274">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="b6620-275">전자 메일이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-275">Your email conflicts with a policy in your organization.</span></span>  <br/> |

## <a name="policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="b6620-276">Excel, PowerPoint 및 Word의 정책 팁</span><span class="sxs-lookup"><span data-stu-id="b6620-276">Policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="b6620-277">사용자가 데스크톱 버전의 Excel, PowerPoint 및 Word에서 중요한 콘텐츠로 작업하는 경우 정책 팁은 콘텐츠가 DLP 정책과 충돌하는 경우 실시간으로 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-277">When people work with sensitive content in the desktop versions of Excel, PowerPoint, and Word, policy tips can notify them in real time that the content conflicts with a DLP policy.</span></span> <span data-ttu-id="b6620-278">이를 위해 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-278">This requires that:</span></span>

- <span data-ttu-id="b6620-279">Office 문서가 비즈니스용 OneDrive 사이트 또는 SharePoint Online 사이트에 저장되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-279">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>

- <span data-ttu-id="b6620-280">사이트는 정책 팁을 사용하도록 구성된 DLP 정책에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-280">The site is included in a DLP policy that's configured to use policy tips.</span></span>

<span data-ttu-id="b6620-281">Office 데스크톱 프로그램에서 직접 DLP 정책을 Office 365 동기화한 다음 문서를 검사하여 DLP 정책과 충돌하지 않고 실시간으로 정책 팁을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-281">Office desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>

> [!NOTE]
> <span data-ttu-id="b6620-282">Office 데스크톱 앱에서 직접 문서를 검사하여 DLP 정책 팁을 표시해야 하는지 여부를 판단합니다. 온라인 사이트 또는 SharePoint 파일에 표시해야 비즈니스용 OneDrive 정책 팁은 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-282">Office desktop apps scan documents themselves to determine if DLP policy tips should be shown; they do not show policy tips that SharePoint Online sites or OneDrive for Business sites have already determined should be shown on a file.</span></span> <span data-ttu-id="b6620-283">따라서 데스크톱 앱에서 SharePoint Online 사이트 또는 비즈니스용 OneDrive DLP 정책 팁이 항상 비즈니스용 OneDrive 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-283">As a result, you may not always see a DLP policy tip in the desktop apps that you see in the SharePoint Online sites or OneDrive for Business sites.</span></span> <span data-ttu-id="b6620-284">반면에 웹 Office 응용 프로그램에는 온라인 사이트 또는 SharePoint 사이트가 비즈니스용 OneDrive DLP 정책 팁만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-284">In contrast, the Office applications on the web only show DLP policy tips that SharePoint Online sites or OneDrive for Business sites have already determined should be shown.</span></span>

<span data-ttu-id="b6620-285">DLP 정책에서 정책 팁을 구성한 방식에 따라, 사용자들은 간단히 정책 팁을 무시하거나, 업무 정당성을 지정하거나 지정하지 않은 상태로 정책을 재정의하거나, 가양성을 보고하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-285">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>

<span data-ttu-id="b6620-286">메시지 표시줄에 정책 팁이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-286">Policy tips appear on the Message Bar.</span></span>

![메시지 표시줄에서는 Excel 2016 정책 팁](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

<span data-ttu-id="b6620-288">또한 Backstage 보기에도 정책 팁이 나타납니다(**파일** 탭).</span><span class="sxs-lookup"><span data-stu-id="b6620-288">And policy tips also appear in the Backstage view (on the **File** tab).</span></span>

![Backstage Excel 2016의 정책 정보를 표시](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)

<span data-ttu-id="b6620-290">DLP 정책의 정책 팁이 이러한 옵션으로 구성되어 있는 경우 정책 팁 **해결** 또는 **재정의** 를 선택하거나 가양성 **보고** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-290">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span>

![정책 옵션에서 Excel 2016 Backstage에서 팁](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)

<span data-ttu-id="b6620-292">이러한 각 데스크톱 Office 정책 팁을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-292">In each of these Office desktop programs, people can choose to turn off policy tips.</span></span> <span data-ttu-id="b6620-293">정책 팁을 끄면, 단순히 알림에 불과한 정책 팁은 메시지 표시줄 또는 Backstage 보기에 표시되지 것입니다(**파일** 탭).</span><span class="sxs-lookup"><span data-stu-id="b6620-293">If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab).</span></span> <span data-ttu-id="b6620-294">그러나 차단 및 재정의에 대한 정책 팁은 계속 표시되고, 해당 사용자는 전자 메일 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-294">However, policy tips about blocking and overriding will still appear, and they will still receive the email notification.</span></span> <span data-ttu-id="b6620-295">또한 정책 팁을 꺼도 문서에 적용된 모든 DLP 정책에서 해당 문서가 제외되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-295">In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span>

### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="b6620-296">Excel 2016, PowerPoint 2016 및 Word 2016 정책 팁에 대한 기본 텍스트</span><span class="sxs-lookup"><span data-stu-id="b6620-296">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="b6620-p139">기본적으로 열린 문서의 메시지 표시줄 및 Backstage 보기에 다음과 비슷한 텍스트가 정책 팁으로 표시됩니다. 알림 텍스트는 각 규칙에 대해 별도로 구성되므로 일치하는 규칙에 따라 표시되는 텍스트가 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-p139">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="b6620-299">**DLP 정책 규칙이 수행하는 작업...**</span><span class="sxs-lookup"><span data-stu-id="b6620-299">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="b6620-300">**기본 정책 팁에 표시되는 내용...**</span><span class="sxs-lookup"><span data-stu-id="b6620-300">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6620-301">알림을 보내지만 다시 설정은 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-301">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="b6620-302">이 파일이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-302">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="b6620-303">자세한 내용은 **파일 메뉴로** 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="b6620-303">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="b6620-304">액세스를 차단하고, 알림을 보내고, 재정의를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-304">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="b6620-305">이 파일이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-305">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="b6620-306">이 충돌을 해결하지 않으면 이 파일에 대한 액세스가 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-306">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="b6620-307">자세한 내용은 **파일 메뉴로** 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="b6620-307">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="b6620-308">액세스를 차단하고 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-308">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="b6620-309">이 파일이 조직의 정책과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-309">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="b6620-310">이 충돌을 해결하지 않으면 이 파일에 대한 액세스가 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-310">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="b6620-311">자세한 내용은 **파일 메뉴로** 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="b6620-311">Go to the **File** menu for more information.</span></span>  <br/> |

### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="b6620-312">정책 팁에 대한 사용자 지정 Excel, PowerPoint 및 Word</span><span class="sxs-lookup"><span data-stu-id="b6620-312">Custom text for policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="b6620-313">정책 팁에 대한 텍스트를 전자 메일 알림과 별도로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-313">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="b6620-314">전자 메일 알림에 대한 사용자 지정 텍스트(위 섹션 참조)와 달리 정책 팁에 대한 사용자 지정 텍스트는 HTML 또는 토큰을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-314">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="b6620-315">대신 정책 팁에 대한 사용자 지정 텍스트는 256자 제한이 있는 일반 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b6620-315">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>

## <a name="more-information"></a><span data-ttu-id="b6620-316">추가 정보</span><span class="sxs-lookup"><span data-stu-id="b6620-316">More information</span></span>

- [<span data-ttu-id="b6620-317">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="b6620-317">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="b6620-318">템플릿으로부터 DLP 정책 생성</span><span class="sxs-lookup"><span data-stu-id="b6620-318">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="b6620-319">DLP 정책 조건, 예외 및 작업(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="b6620-319">DLP policy conditions, exceptions, and actions (preview)</span></span>](./dlp-microsoft-teams.md)
- [<span data-ttu-id="b6620-320">FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b6620-320">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
- [<span data-ttu-id="b6620-321">DLP 정책 템플릿에 포함되는 내용</span><span class="sxs-lookup"><span data-stu-id="b6620-321">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
- [<span data-ttu-id="b6620-322">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="b6620-322">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)