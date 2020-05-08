---
title: 사용자로 격리된 메시지 찾기 및 릴리스
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Microsoft 365의 보안 및 준수 센터에서 격리된 메시지를 확인하고 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 177f60f1fccc764d74ec0374249a62c602cb84aa
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036515"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="fb498-103">사용자로 격리된 메시지 찾기 및 릴리스</span><span class="sxs-lookup"><span data-stu-id="fb498-103">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="fb498-104">격리는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="fb498-105">자세한 내용은 [Office 365의 격리](quarantine-email-messages.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb498-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="fb498-106">사용자는 사용자가 받는 사람인 격리되는 메시지를 보고, 해제하고, 삭제할 수 있으며 메시지는 스팸, 대량 전자 메일 또는 (2020년 4월부터)피싱으로 격리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="fb498-107">보안 및 준수 센터에서 또는 [최종 사용자 스팸 알림](use-spam-notifications-to-release-and-report-quarantined-messages.md)에서(관리자가 설정한 경우) 격리 된 메시지를보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-107">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fb498-108">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="fb498-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fb498-109">보안 및 준수 센터를 열려면 <https://protection.office.com>로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="fb498-109">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="fb498-110">격리 페이지를 바로 열려면 <https://protection.office.com/quarantine>으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="fb498-110">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="fb498-111">관리자는 메시지를 영구적으로 삭제하기 전에 얼마나 오래 메시지를 격리할지 구성할 수 있습니다(스팸 방지 정책).</span><span class="sxs-lookup"><span data-stu-id="fb498-111">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="fb498-112">격리에서 만료되는 메시지는 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-112">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="fb498-113">자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb498-113">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="fb498-114">관리자는 스팸 방지 정책에서 [최종 사용자 스팸 알림을 사용하도록 설정](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-114">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="fb498-115">사용자는 스팸 격리된 메시지를 해제할 수 있지만 이 알림에서 피싱 격리된 메시지를 직접 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-115">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="fb498-116">자세한 내용은 [Office 365에서 최종 사용자 스팸 알림](use-spam-notifications-to-release-and-report-quarantined-messages.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb498-116">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="fb498-117">신뢰도가 높은 피싱, 맬웨어 또는 메일 흐름 규칙(전송 규칙이라고도 함)에 의해 격리된 메시지는 관리자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-117">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="fb498-118">피싱 메시지는 관리자가 릴리스할 뿐 아니라 사용자가 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-118">Phish messages can be reviewed by users but only released by admins.</span></span> <span data-ttu-id="fb498-119">자세한 내용은 [Office 365에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb498-119">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="fb498-120">메시지를 해제하고 가양성으로(정크 아님) 한 번만 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-120">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="fb498-121">격리된 메시지 보기</span><span class="sxs-lookup"><span data-stu-id="fb498-121">View your quarantined messages</span></span>

1. <span data-ttu-id="fb498-122">보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-122">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="fb498-123">사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-123">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="fb498-124">**열 수정**을 클릭하여 최대 7개의 열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-124">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="fb498-125">기본값은 별표(<sup>\*</sup>)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-125">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="fb498-126">**수신됨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fb498-126">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="fb498-127">**보낸 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fb498-127">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="fb498-128">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fb498-128">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="fb498-129">**격리 이유**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fb498-129">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="fb498-130">**해제되었나요?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fb498-130">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="fb498-131">**정책 유형**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fb498-131">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="fb498-132">**만료**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fb498-132">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="fb498-133">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="fb498-133">**Recipient**</span></span>

   - <span data-ttu-id="fb498-134">**메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="fb498-134">**Message ID**</span></span>

   - <span data-ttu-id="fb498-135">**정책 이름**</span><span class="sxs-lookup"><span data-stu-id="fb498-135">**Policy name**</span></span>

   - <span data-ttu-id="fb498-136">**크기**</span><span class="sxs-lookup"><span data-stu-id="fb498-136">**Size**</span></span>

   - <span data-ttu-id="fb498-137">**방향**</span><span class="sxs-lookup"><span data-stu-id="fb498-137">**Direction**</span></span>

   <span data-ttu-id="fb498-138">작업을 마쳤으면 **저장**을 클릭하거나 **기본으로 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-138">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="fb498-139">결과를 필터링하려면 **필터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-139">To filter the results, click **Filter**.</span></span> <span data-ttu-id="fb498-140">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="fb498-140">The available filters are:</span></span>

   - <span data-ttu-id="fb498-141">**만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="fb498-141">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="fb498-142">**오늘**</span><span class="sxs-lookup"><span data-stu-id="fb498-142">**Today**</span></span>

     - <span data-ttu-id="fb498-143">**다음 2일**</span><span class="sxs-lookup"><span data-stu-id="fb498-143">**Next 2 days**</span></span>

     - <span data-ttu-id="fb498-144">**다음 7일**</span><span class="sxs-lookup"><span data-stu-id="fb498-144">**Next 7 days**</span></span>

     - <span data-ttu-id="fb498-145">**사용자 지정**: **시작 날짜**와 **종료 날짜**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-145">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="fb498-146">**받은 시간**: **시작 날짜**와 **종료 날짜**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-146">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="fb498-147">**격리 이유**:</span><span class="sxs-lookup"><span data-stu-id="fb498-147">**Quarantine reason**:</span></span>

     - <span data-ttu-id="fb498-148">**대량 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="fb498-148">**Bulk**</span></span>

     - <span data-ttu-id="fb498-149">**스팸**</span><span class="sxs-lookup"><span data-stu-id="fb498-149">**Spam**</span></span>

     - <span data-ttu-id="fb498-150">**피싱**(2020년 4월부터)</span><span class="sxs-lookup"><span data-stu-id="fb498-150">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="fb498-151">필터를 지우려면 **지우기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-151">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="fb498-152">필터 플라이아웃을 숨기려면 다시 **필터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-152">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="fb498-153">특정 메시지를 찾으려면 **결과 정렬 기준**(기본적으로 **메시지 ID** 단추) 및 해당 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-153">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="fb498-154">와일드카드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-154">Wildcards aren't supported.</span></span> <span data-ttu-id="fb498-155">다음 값을 기준으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-155">You can search by the following values:</span></span>

   - <span data-ttu-id="fb498-156">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-156">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="fb498-157">목록에서 메시지를 선택하면 표시되는 **세부 정보** 플라이아웃 창에 **메시지 ID** 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-157">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="fb498-158">관리자는 [메시지 추적](message-trace-scc.md)을 사용하여 메시지와 해당 메시지 ID 값을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-158">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="fb498-159">**보낸 사람 전자 메일 주소**: 보낸 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-159">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="fb498-160">**받는 사람 전자 메일 주소**: 받는 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-160">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="fb498-161">**제목**: 메시지의 전체 제목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-161">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="fb498-162">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-162">The search is not case-sensitive.</span></span>

   <span data-ttu-id="fb498-163">검색 조건을 입력한 후 ![새로 고침 단추](../../media/scc-quarantine-refresh.png) **새로 고침**을 클릭하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-163">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="fb498-164">격리된 특정 메시지를 찾은 후 해당 메시지를 선택하여 세부 정보를 확인하고 메시지에 대한 작업을 수행합니다(예를 들어 메시지를 보거나, 해제하거나, 다운로드하거나, 삭제하기).</span><span class="sxs-lookup"><span data-stu-id="fb498-164">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="fb498-165">메시지 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="fb498-165">Export message results</span></span>

1. <span data-ttu-id="fb498-166">원하는 메시지를 선택하고 **결과 내보내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-166">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="fb498-167">브라우저를 열어 두라고 경고하는 확인 메시지에서 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-167">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="fb498-168">내보내기가 준비되면 .csv 파일에 이름을 지정하고 다운로드 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-168">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="fb498-169">격리된 메시지 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="fb498-169">View quarantined message details</span></span>

<span data-ttu-id="fb498-170">목록에서 전자 메일 메시지를 선택하면 **세부 정보** 플라이아웃 창에 다음 메시지 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-170">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="fb498-171">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-171">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="fb498-172">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="fb498-172">**Sender address**</span></span>

- <span data-ttu-id="fb498-173">**수신됨**: 메시지를 수신한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-173">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="fb498-174">**제목**</span><span class="sxs-lookup"><span data-stu-id="fb498-174">**Subject**</span></span>

- <span data-ttu-id="fb498-175">**격리 이유**: 메시지가 **스팸**, **대량 전자 메일** 또는 (2020년 4월부터)**피싱**으로 구분되었는지 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-175">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="fb498-176">**받는 사람**: 메시지에 받는 사람이 여러 명 있는 경우 **미리 보기 메시지** 또는 **메시지 헤더 보기**를 클릭하여 전체 받는 사람의 목록을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-176">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="fb498-177">**만료**: 격리에서 메시지가 자동으로 영구적으로 삭제되는 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-177">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="fb498-178">**해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-178">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="fb498-179">**아직 해제되지 않음**: 메시지가 아직 해제되지 않은 모든 전자 메일 주소(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-179">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="fb498-180">격리된 전자 메일에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="fb498-180">Take action on quarantined email</span></span>

<span data-ttu-id="fb498-181">메시지를 선택하면 **세부 정보** 플라이아웃 창에 메시지로 수행할 작업에 대한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-181">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="fb498-182">**해제 메시지**: 표시되는 플라이아웃 창에서 **분석을 위해 Microsoft에 메시지를 보고**할 것인지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-182">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="fb498-183">이 옵션은 기본적으로 선택되어 있으며 잘못 격리된 메시지를 가양성으로 Microsoft에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-183">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="fb498-184">작업을 마쳤으면 **메시지 해제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-184">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="fb498-185">**메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면 이 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-185">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="fb498-186">헤더 필드와 값을 자세히 분석하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음 **Microsoft 메시지 헤더 분석기**를 선택하여 원격 연결 분석기로 이동합니다.(이 작업을 완료하기 위해 Microsoft 365를 닫지 않으려면 마우스 오른쪽 단추를 클릭하고 **새 탭에서 열기**를 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="fb498-186">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="fb498-187">메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여넣고 **헤더 분석**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-187">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="fb498-188">**메시지 미리 보기**: 표시되는 플라이아웃 창에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-188">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="fb498-189">**원본 보기**: 모든 링크를 사용하지 않도록 설정한 HTML 버전의 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-189">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="fb498-190">**텍스트 보기**: 일반 텍스트로 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-190">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="fb498-191">**메시지 다운로드하기**: 표시되는 플라이아웃 창에서 **이 메시지를 다운로드하는 데 따르는 위험을 알고 있습니다.** 를 선택하여 메시지의 로컬 복사본을 .eml 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-191">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="fb498-192">**격리에서 제거하기**: 표시되는 경고에서 **예**를 클릭하면 메시지가 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-192">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="fb498-193">작업을 마쳤으면 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-193">When you're finished, click **Close**.</span></span>

<span data-ttu-id="fb498-194">메시지를 해제하거나 제거하지 않으면 기본 격리 보존 기간이 만료된 후에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-194">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="fb498-195">여러 개의 격리된 전자 메일 메시지에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="fb498-195">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="fb498-196">목록에서 격리된 메시지를 여러 개(최대 100개) 선택하면 다음 **대량 전자 메일 작업** 플라이아웃 창이 나타나 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-196">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="fb498-197">**메시지 해제하기**:이 옵션은 **특정 받는사람에게 메시지 해제하기**를 선택할 수 없는 점을 제외하고 메시지를 하나만 해제할 때와 동일합니다. **모든 받는 사람에게 메시지 해제하기** 또는 **다른 사람에게 메시지 해제하기**만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-197">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="fb498-198">**메시지 삭제하기**: 표시되는 경고에서 **예**를 클릭하면 메시지는 원래 받는 사람에게 보내지지 않고 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-198">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="fb498-199">작업을 마쳤으면 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb498-199">When you're finished, click **Close**.</span></span>
