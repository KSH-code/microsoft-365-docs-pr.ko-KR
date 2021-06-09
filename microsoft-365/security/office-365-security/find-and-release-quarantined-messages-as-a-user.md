---
title: 사용자로 격리된 메시지 찾기 및 릴리스
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 사용자에게 전달되었어야 하는 EOP(Exchange Online Protection)에 격리된 메시지를 보고 관리하는 방법에 대해 알아볼 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4913d0c6fc34d912474bcceac8b1785c4a7e07b3
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821298"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="662be-103">EOP에서 사용자 권한으로 격리된 메시지 찾기 및 해제하기</span><span class="sxs-lookup"><span data-stu-id="662be-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="662be-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="662be-104">**Applies to**</span></span>
- [<span data-ttu-id="662be-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="662be-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="662be-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="662be-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="662be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="662be-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="662be-108">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="662be-109">자세한 내용은 [EOP에 격리](quarantine-email-messages.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662be-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="662be-110">격리된 메시지 수신자가 일반 사용자로서 메시지에 할 수 있는 작업이 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-110">As a recipient of a quarantined message, what you can do to the message as a regular user is described in the following table:</span></span>

<br>

****

|<span data-ttu-id="662be-111">격리 이유:</span><span class="sxs-lookup"><span data-stu-id="662be-111">Quarantine reason</span></span>|<span data-ttu-id="662be-112">보기</span><span class="sxs-lookup"><span data-stu-id="662be-112">View</span></span>|<span data-ttu-id="662be-113">릴리스</span><span class="sxs-lookup"><span data-stu-id="662be-113">Release</span></span>|<span data-ttu-id="662be-114">삭제</span><span class="sxs-lookup"><span data-stu-id="662be-114">Delete</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="662be-115">대량</span><span class="sxs-lookup"><span data-stu-id="662be-115">Bulk</span></span>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="662be-119">스팸</span><span class="sxs-lookup"><span data-stu-id="662be-119">Spam</span></span>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="662be-123">피싱(높은 신뢰도 피싱은 해당 안 됨)</span><span class="sxs-lookup"><span data-stu-id="662be-123">Phishing (not high confidence phishing)</span></span>|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)|
|

<span data-ttu-id="662be-126">Microsoft 365 보안 센터 또는 [최종 사용자 스팸 알림](use-spam-notifications-to-release-and-report-quarantined-messages.md)(관리자가 설정한 경우)에서 격리된 메시지를 보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-126">You view and manage your quarantined messages in the Microsoft 365 security center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="662be-127">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="662be-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="662be-128">보안 센터를 열려면 <https://security.microsoft.com>(으)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-128">To open the security center, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="662be-129">격리 페이지를 바로 열려면 <https://security.microsoft.com/quarantine>(으)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-129">To open the Quarantine page directly, go to <https://security.microsoft.com/quarantine>.</span></span>

- <span data-ttu-id="662be-130">관리자는 스팸 방지 정책에서 메시지를 영구적으로 삭제하기 전에 얼마 동안 메시지를 격리 상태로 유지할지 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-130">Admins can configure how long messages are kept in quarantine before they're permanently deleted in anti-spam policies.</span></span> <span data-ttu-id="662be-131">격리에서 만료되는 메시지는 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-131">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="662be-132">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662be-132">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="662be-133">관리자는 스팸 방지 정책에서 [최종 사용자 스팸 알림을 사용하도록 설정](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-133">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="662be-134">사용자는 격리된 스팸 메시지를 해제할 수 있지만 이 알림에서 격리된 피싱 메시지를 직접 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-134">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="662be-135">사용자는 이러한 알림에서 직접 검역된 피싱 메시지(고신뢰 피싱 메시지가 아님)를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-135">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="662be-136">자세한 내용은 [EOP의 최종 사용자 스팸 통지](use-spam-notifications-to-release-and-report-quarantined-messages.md)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-136">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="662be-137">높은 신뢰도 피싱, 악성 프로그램 또는 메일 흐름 규칙(트랜스포트 규칙이라고도 함)으로 검역된 메시지는 관리자만 사용할 수 있으며 사용자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-137">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="662be-138">자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662be-138">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="662be-139">메시지를 해제하고 가양성으로(정크 아님) 한 번만 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-139">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="662be-140">격리된 메시지 보기</span><span class="sxs-lookup"><span data-stu-id="662be-140">View your quarantined messages</span></span>

1. <span data-ttu-id="662be-141">보안 센터에서 **전자 메일 및 공동 작업** \> **검토** \> **격리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-141">In the security center, go to **Email & collaboration** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="662be-142">사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-142">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="662be-143">**열 수정** 을 클릭하여 최대 7개의 열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-143">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="662be-144">기본값은 별표(<sup>\*</sup>)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="662be-144">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="662be-145">**수신됨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="662be-145">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="662be-146">**보낸 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="662be-146">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="662be-147">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="662be-147">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="662be-148">**격리 이유**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="662be-148">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="662be-149">**해제되었나요?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="662be-149">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="662be-150">**정책 유형**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="662be-150">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="662be-151">**만료**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="662be-151">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="662be-152">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="662be-152">**Recipient**</span></span>
   - <span data-ttu-id="662be-153">**메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="662be-153">**Message ID**</span></span>
   - <span data-ttu-id="662be-154">**정책 이름**</span><span class="sxs-lookup"><span data-stu-id="662be-154">**Policy name**</span></span>
   - <span data-ttu-id="662be-155">**크기**</span><span class="sxs-lookup"><span data-stu-id="662be-155">**Size**</span></span>
   - <span data-ttu-id="662be-156">**방향**</span><span class="sxs-lookup"><span data-stu-id="662be-156">**Direction**</span></span>

   <span data-ttu-id="662be-157">작업을 마쳤으면 **저장** 을 클릭하거나 **기본으로 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-157">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="662be-158">결과를 필터링하려면 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-158">To filter the results, click **Filter**.</span></span> <span data-ttu-id="662be-159">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="662be-159">The available filters are:</span></span>

   - <span data-ttu-id="662be-160">**만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="662be-160">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="662be-161">**오늘**</span><span class="sxs-lookup"><span data-stu-id="662be-161">**Today**</span></span>
     - <span data-ttu-id="662be-162">**다음 2일**</span><span class="sxs-lookup"><span data-stu-id="662be-162">**Next 2 days**</span></span>
     - <span data-ttu-id="662be-163">**다음 7일**</span><span class="sxs-lookup"><span data-stu-id="662be-163">**Next 7 days**</span></span>
     - <span data-ttu-id="662be-164">**사용자 지정**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-164">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="662be-165">**받은 시간**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-165">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="662be-166">**격리 이유**:</span><span class="sxs-lookup"><span data-stu-id="662be-166">**Quarantine reason**:</span></span>
     - <span data-ttu-id="662be-167">**대량 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="662be-167">**Bulk**</span></span>
     - <span data-ttu-id="662be-168">**스팸**</span><span class="sxs-lookup"><span data-stu-id="662be-168">**Spam**</span></span>
     - <span data-ttu-id="662be-169">**피싱**</span><span class="sxs-lookup"><span data-stu-id="662be-169">**Phish**</span></span>

   - <span data-ttu-id="662be-170">**정책 유형**: 정책 유형별로 메시지를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-170">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="662be-171">**맬웨어 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="662be-171">**Anti-malware policy**</span></span>
     - <span data-ttu-id="662be-172">**안전한 첨부 파일 정책**(Office 365용 Defender)</span><span class="sxs-lookup"><span data-stu-id="662be-172">**Safe Attachments policy** (Defender for Office 365)</span></span>
     - <span data-ttu-id="662be-173">**피싱 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="662be-173">**Anti-phish policy**</span></span>
     - <span data-ttu-id="662be-174">**호스트된 필터 정책**(스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="662be-174">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="662be-175">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="662be-175">**Transport rule**</span></span>

     <sup>\*</sup>

   <span data-ttu-id="662be-176">필터를 지우려면 **지우기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="662be-177">필터 플라이아웃을 숨기려면 다시 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-177">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="662be-178">특정 메시지를 찾으려면 **결과 정렬 기준**(기본적으로 **메시지 ID** 단추) 및 해당 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="662be-179">와일드카드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-179">Wildcards aren't supported.</span></span> <span data-ttu-id="662be-180">다음 값을 기준으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-180">You can search by the following values:</span></span>

   - <span data-ttu-id="662be-181">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="662be-181">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="662be-182">목록에서 메시지를 선택하면 표시되는 **세부 정보** 플라이아웃 창에 **메시지 ID** 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="662be-182">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="662be-183">관리자는 [메시지 추적](message-trace-scc.md)을 사용하여 메시지와 해당 메시지 ID 값을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-183">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>
   - <span data-ttu-id="662be-184">**보낸 사람 전자 메일 주소**: 보낸 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="662be-184">**Sender email address**: A single sender's email address.</span></span>
   - <span data-ttu-id="662be-185">**정책 이름**: 메시지의 전체 정책 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-185">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="662be-186">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-186">The search is not case-sensitive.</span></span>
   - <span data-ttu-id="662be-187">**받는 사람 전자 메일 주소**: 받는 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="662be-187">**Recipient email address**: A single recipient's email address.</span></span>
   - <span data-ttu-id="662be-188">**제목**: 메시지의 전체 제목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-188">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="662be-189">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-189">The search is not case-sensitive.</span></span>

   <span data-ttu-id="662be-190">검색 조건을 입력한 후 ![새로 고침 단추](../../media/scc-quarantine-refresh.png) **새로 고침** 을 클릭하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-190">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="662be-191">격리된 특정 메시지를 찾은 후 해당 메시지를 선택하여 세부 정보를 확인하고 메시지에 대한 작업을 수행합니다(예를 들어 메시지를 보거나, 해제하거나, 다운로드하거나, 삭제하기).</span><span class="sxs-lookup"><span data-stu-id="662be-191">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="662be-192">메시지 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="662be-192">Export message results</span></span>

1. <span data-ttu-id="662be-193">원하는 메시지를 선택하고 **결과 내보내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-193">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="662be-194">브라우저를 열어 두라고 경고하는 확인 메시지에서 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-194">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="662be-195">내보내기가 준비되면 .csv 파일에 이름을 지정하고 다운로드 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-195">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="662be-196">격리된 메시지 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="662be-196">View quarantined message details</span></span>

<span data-ttu-id="662be-197">목록에서 전자 메일 메시지를 선택하면 **세부 정보** 플라이아웃 창에 다음 메시지 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="662be-197">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="662be-198">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="662be-198">**Message ID**: The globally unique identifier for the message.</span></span>
- <span data-ttu-id="662be-199">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="662be-199">**Sender address**</span></span>
- <span data-ttu-id="662be-200">**수신됨**: 메시지를 수신한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="662be-200">**Received**: The date/time when the message was received.</span></span>
- <span data-ttu-id="662be-201">**제목**</span><span class="sxs-lookup"><span data-stu-id="662be-201">**Subject**</span></span>
- <span data-ttu-id="662be-202">**격리 이유**: 메시지가 **스팸**, **대량 메일** 또는 **피싱** 으로 구분되었는지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-202">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>
- <span data-ttu-id="662be-203">**받는 사람**: 메시지에 받는 사람이 여러 명 있는 경우 **미리 보기 메시지** 또는 **메시지 헤더 보기** 를 클릭하여 전체 받는 사람의 목록을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-203">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>
- <span data-ttu-id="662be-204">**만료**: 격리에서 메시지가 자동으로 영구적으로 삭제되는 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="662be-204">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>
- <span data-ttu-id="662be-205">**해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="662be-205">**Released to**: All email addresses (if any) to which the message has been released.</span></span>
- <span data-ttu-id="662be-206">**아직 해제되지 않음**: 메시지가 아직 해제되지 않은 모든 전자 메일 주소(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="662be-206">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="662be-207">격리된 전자 메일에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="662be-207">Take action on quarantined email</span></span>

<span data-ttu-id="662be-208">메시지를 선택하면 **세부 정보** 플라이아웃 창에 메시지로 수행할 작업에 대한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-208">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="662be-209">**해제 메시지**: 표시되는 플라이아웃 창에서 **분석을 위해 Microsoft에 메시지를 보고** 할 것인지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-209">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="662be-210">이 옵션은 기본적으로 선택되어 있으며 잘못 격리된 메시지를 가양성으로 Microsoft에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-210">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="662be-211">작업을 마쳤으면 **메시지 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-211">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="662be-212">**메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면 이 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-212">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="662be-213">헤더 필드와 값을 자세히 분석하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음 **Microsoft 메시지 헤더 분석기** 를 선택하여 원격 연결 분석기로 이동합니다.(이 작업을 완료하기 위해 Microsoft 365를 닫지 않으려면 마우스 오른쪽 단추를 클릭하고 **새 탭에서 열기** 를 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="662be-213">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="662be-214">메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여넣고 **헤더 분석** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-214">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="662be-215">**메시지 미리 보기**: 표시되는 플라이아웃 창에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-215">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="662be-216">**원본 보기**: 모든 링크를 사용하지 않도록 설정한 HTML 버전의 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-216">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="662be-217">**텍스트 보기**: 일반 텍스트로 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-217">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="662be-218">**격리에서 제거하기**: 표시되는 경고에서 **예** 를 클릭하면 메시지가 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="662be-218">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="662be-219">**보낸 사람 차단**: 사서함의 수신 거부 목록에 보낸 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-219">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="662be-220">자세한 내용은 [메일 보낸 사람 차단](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662be-220">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="662be-221">사서함의 수신 거부 목록에 보낸 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-221">Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="662be-222">자세한 내용은 [메일 보낸 사람 차단](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662be-222">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="662be-223">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-223">When you're finished, click **Close**.</span></span>

<span data-ttu-id="662be-224">메시지를 해제하거나 제거하지 않으면 기본 격리 보존 기간이 만료된 후에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="662be-224">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="662be-225">여러 개의 격리된 전자 메일 메시지에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="662be-225">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="662be-226">목록에서 격리된 메시지를 여러 개(최대 100개) 선택하면 다음 **대량 전자 메일 작업** 플라이아웃 창이 나타나 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-226">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="662be-227">**메시지 해제하기**:이 옵션은 **특정 받는사람에게 메시지 해제하기** 를 선택할 수 없는 점을 제외하고 메시지를 하나만 해제할 때와 동일합니다. **모든 받는 사람에게 메시지 해제하기** 또는 **다른 사람에게 메시지 해제하기** 만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662be-227">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>
- <span data-ttu-id="662be-228">**메시지 삭제하기**: 표시되는 경고에서 **예** 를 클릭하면 메시지는 원래 받는 사람에게 보내지지 않고 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="662be-228">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="662be-229">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662be-229">When you're finished, click **Close**.</span></span>
