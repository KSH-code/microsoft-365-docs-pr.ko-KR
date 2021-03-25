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
ms.openlocfilehash: 961912427f9c343f8235f0ed8e990431669ff9e5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205589"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="3fc4f-103">EOP에서 사용자 권한으로 격리된 메시지 찾기 및 해제하기</span><span class="sxs-lookup"><span data-stu-id="3fc4f-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3fc4f-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-104">**Applies to**</span></span>
- [<span data-ttu-id="3fc4f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3fc4f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3fc4f-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="3fc4f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3fc4f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3fc4f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3fc4f-108">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="3fc4f-109">자세한 내용은 [EOP에 격리](quarantine-email-messages.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="3fc4f-110">사용자가 받는 사람인 경우 사용자는 격리된 메시지를 보고 해제하고 삭제할 수 있으며, 메시지는 스팸 또는 벌크 메일로 격리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-110">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="3fc4f-111">2020년 4월부터 사용자가 받는 사람인 경우 사용자는 격리된 피싱(높은 정확도가 아닌 피싱) 메시지를 보거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-111">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="3fc4f-112">보안 및 준수 센터에서 또는 [최종 사용자 스팸 알림](use-spam-notifications-to-release-and-report-quarantined-messages.md)에서(관리자가 설정한 경우) 격리 된 메시지를보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-112">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3fc4f-113">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="3fc4f-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3fc4f-114">보안 및 준수 센터를 열려면 <https://protection.office.com>로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-114">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="3fc4f-115">격리 페이지를 바로 열려면 <https://protection.office.com/quarantine>으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-115">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="3fc4f-116">관리자는 메시지를 영구적으로 삭제하기 전에 얼마나 오래 메시지를 격리할지 구성할 수 있습니다(스팸 방지 정책).</span><span class="sxs-lookup"><span data-stu-id="3fc4f-116">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="3fc4f-117">격리에서 만료되는 메시지는 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-117">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="3fc4f-118">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="3fc4f-119">관리자는 스팸 방지 정책에서 [최종 사용자 스팸 알림을 사용하도록 설정](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-119">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="3fc4f-120">사용자는 격리된 스팸 메시지를 해제할 수 있지만 이 알림에서 격리된 피싱 메시지를 직접 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-120">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="3fc4f-121">사용자는 이러한 알림에서 직접 검역된 피싱 메시지(고신뢰 피싱 메시지가 아님)를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-121">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="3fc4f-122">자세한 내용은 [EOP의 최종 사용자 스팸 통지](use-spam-notifications-to-release-and-report-quarantined-messages.md)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-122">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="3fc4f-123">높은 신뢰도 피싱, 악성 프로그램 또는 메일 흐름 규칙(트랜스포트 규칙이라고도 함)으로 검역된 메시지는 관리자만 사용할 수 있으며 사용자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-123">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="3fc4f-124">자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-124">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="3fc4f-125">메시지를 해제하고 가양성으로(정크 아님) 한 번만 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-125">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="3fc4f-126">격리된 메시지 보기</span><span class="sxs-lookup"><span data-stu-id="3fc4f-126">View your quarantined messages</span></span>

1. <span data-ttu-id="3fc4f-127">보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-127">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="3fc4f-128">사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-128">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="3fc4f-129">**열 수정** 을 클릭하여 최대 7개의 열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-129">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="3fc4f-130">기본값은 별표(<sup>\*</sup>)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-130">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="3fc4f-131">**수신됨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fc4f-131">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="3fc4f-132">**보낸 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fc4f-132">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="3fc4f-133">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fc4f-133">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="3fc4f-134">**격리 이유**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fc4f-134">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="3fc4f-135">**해제되었나요?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fc4f-135">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="3fc4f-136">**정책 유형**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fc4f-136">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="3fc4f-137">**만료**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fc4f-137">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="3fc4f-138">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-138">**Recipient**</span></span>
   - <span data-ttu-id="3fc4f-139">**메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-139">**Message ID**</span></span>
   - <span data-ttu-id="3fc4f-140">**정책 이름**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-140">**Policy name**</span></span>
   - <span data-ttu-id="3fc4f-141">**크기**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-141">**Size**</span></span>
   - <span data-ttu-id="3fc4f-142">**방향**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-142">**Direction**</span></span>

   <span data-ttu-id="3fc4f-143">작업을 마쳤으면 **저장** 을 클릭하거나 **기본으로 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-143">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="3fc4f-144">결과를 필터링하려면 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-144">To filter the results, click **Filter**.</span></span> <span data-ttu-id="3fc4f-145">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="3fc4f-145">The available filters are:</span></span>

   - <span data-ttu-id="3fc4f-146">**만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="3fc4f-146">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="3fc4f-147">**오늘**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-147">**Today**</span></span>
     - <span data-ttu-id="3fc4f-148">**다음 2일**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-148">**Next 2 days**</span></span>
     - <span data-ttu-id="3fc4f-149">**다음 7일**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-149">**Next 7 days**</span></span>
     - <span data-ttu-id="3fc4f-150">**사용자 지정**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-150">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="3fc4f-151">**받은 시간**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-151">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="3fc4f-152">**격리 이유**:</span><span class="sxs-lookup"><span data-stu-id="3fc4f-152">**Quarantine reason**:</span></span>
     - <span data-ttu-id="3fc4f-153">**대량 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-153">**Bulk**</span></span>
     - <span data-ttu-id="3fc4f-154">**스팸**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-154">**Spam**</span></span>
     - <span data-ttu-id="3fc4f-155">**피싱**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-155">**Phish**</span></span>

   - <span data-ttu-id="3fc4f-156">**정책 유형**: 정책 유형별로 메시지를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-156">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="3fc4f-157">**피싱 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-157">**Anti-phish policy**</span></span>
     - <span data-ttu-id="3fc4f-158">**호스트된 필터 정책**(스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="3fc4f-158">**Hosted content filter policy** (anti-spam policy)</span></span>

   <span data-ttu-id="3fc4f-159">필터를 지우려면 **지우기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-159">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="3fc4f-160">필터 플라이아웃을 숨기려면 다시 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-160">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="3fc4f-161">특정 메시지를 찾으려면 **결과 정렬 기준**(기본적으로 **메시지 ID** 단추) 및 해당 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-161">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="3fc4f-162">와일드카드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-162">Wildcards aren't supported.</span></span> <span data-ttu-id="3fc4f-163">다음 값을 기준으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-163">You can search by the following values:</span></span>

   - <span data-ttu-id="3fc4f-164">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-164">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="3fc4f-165">목록에서 메시지를 선택하면 표시되는 **세부 정보** 플라이아웃 창에 **메시지 ID** 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-165">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="3fc4f-166">관리자는 [메시지 추적](message-trace-scc.md)을 사용하여 메시지와 해당 메시지 ID 값을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-166">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="3fc4f-167">**보낸 사람 전자 메일 주소**: 보낸 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-167">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="3fc4f-168">**정책 이름**: 메시지의 전체 정책 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-168">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="3fc4f-169">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-169">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="3fc4f-170">**받는 사람 전자 메일 주소**: 받는 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-170">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="3fc4f-171">**제목**: 메시지의 전체 제목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-171">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="3fc4f-172">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-172">The search is not case-sensitive.</span></span>

   <span data-ttu-id="3fc4f-173">검색 조건을 입력한 후 ![새로 고침 단추](../../media/scc-quarantine-refresh.png) **새로 고침** 을 클릭하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-173">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="3fc4f-174">격리된 특정 메시지를 찾은 후 해당 메시지를 선택하여 세부 정보를 확인하고 메시지에 대한 작업을 수행합니다(예를 들어 메시지를 보거나, 해제하거나, 다운로드하거나, 삭제하기).</span><span class="sxs-lookup"><span data-stu-id="3fc4f-174">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="3fc4f-175">메시지 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="3fc4f-175">Export message results</span></span>

1. <span data-ttu-id="3fc4f-176">원하는 메시지를 선택하고 **결과 내보내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-176">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="3fc4f-177">브라우저를 열어 두라고 경고하는 확인 메시지에서 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-177">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="3fc4f-178">내보내기가 준비되면 .csv 파일에 이름을 지정하고 다운로드 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-178">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="3fc4f-179">격리된 메시지 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="3fc4f-179">View quarantined message details</span></span>

<span data-ttu-id="3fc4f-180">목록에서 전자 메일 메시지를 선택하면 **세부 정보** 플라이아웃 창에 다음 메시지 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-180">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3fc4f-181">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-181">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="3fc4f-182">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-182">**Sender address**</span></span>

- <span data-ttu-id="3fc4f-183">**수신됨**: 메시지를 수신한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-183">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="3fc4f-184">**제목**</span><span class="sxs-lookup"><span data-stu-id="3fc4f-184">**Subject**</span></span>

- <span data-ttu-id="3fc4f-185">**격리 이유**: 메시지가 **스팸**, **대량 메일** 또는 **피싱** 으로 구분되었는지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-185">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="3fc4f-186">**받는 사람**: 메시지에 받는 사람이 여러 명 있는 경우 **미리 보기 메시지** 또는 **메시지 헤더 보기** 를 클릭하여 전체 받는 사람의 목록을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-186">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="3fc4f-187">**만료**: 격리에서 메시지가 자동으로 영구적으로 삭제되는 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-187">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="3fc4f-188">**해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-188">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="3fc4f-189">**아직 해제되지 않음**: 메시지가 아직 해제되지 않은 모든 전자 메일 주소(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-189">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="3fc4f-190">격리된 전자 메일에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="3fc4f-190">Take action on quarantined email</span></span>

<span data-ttu-id="3fc4f-191">메시지를 선택하면 **세부 정보** 플라이아웃 창에 메시지로 수행할 작업에 대한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-191">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3fc4f-192">**해제 메시지**: 표시되는 플라이아웃 창에서 **분석을 위해 Microsoft에 메시지를 보고** 할 것인지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-192">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="3fc4f-193">이 옵션은 기본적으로 선택되어 있으며 잘못 격리된 메시지를 가양성으로 Microsoft에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-193">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="3fc4f-194">작업을 마쳤으면 **메시지 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-194">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="3fc4f-195">**메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면 이 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-195">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="3fc4f-196">헤더 필드와 값을 자세히 분석하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음 **Microsoft 메시지 헤더 분석기** 를 선택하여 원격 연결 분석기로 이동합니다.(이 작업을 완료하기 위해 Microsoft 365를 닫지 않으려면 마우스 오른쪽 단추를 클릭하고 **새 탭에서 열기** 를 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="3fc4f-196">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="3fc4f-197">메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여넣고 **헤더 분석** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-197">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="3fc4f-198">**메시지 미리 보기**: 표시되는 플라이아웃 창에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-198">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="3fc4f-199">**원본 보기**: 모든 링크를 사용하지 않도록 설정한 HTML 버전의 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-199">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="3fc4f-200">**텍스트 보기**: 일반 텍스트로 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-200">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="3fc4f-201">**격리에서 제거하기**: 표시되는 경고에서 **예** 를 클릭하면 메시지가 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-201">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="3fc4f-202">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-202">When you're finished, click **Close**.</span></span>

<span data-ttu-id="3fc4f-203">메시지를 해제하거나 제거하지 않으면 기본 격리 보존 기간이 만료된 후에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-203">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="3fc4f-204">여러 개의 격리된 전자 메일 메시지에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="3fc4f-204">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="3fc4f-205">목록에서 격리된 메시지를 여러 개(최대 100개) 선택하면 다음 **대량 전자 메일 작업** 플라이아웃 창이 나타나 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-205">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="3fc4f-206">**메시지 해제하기**:이 옵션은 **특정 받는사람에게 메시지 해제하기** 를 선택할 수 없는 점을 제외하고 메시지를 하나만 해제할 때와 동일합니다. **모든 받는 사람에게 메시지 해제하기** 또는 **다른 사람에게 메시지 해제하기** 만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-206">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="3fc4f-207">**메시지 삭제하기**: 표시되는 경고에서 **예** 를 클릭하면 메시지는 원래 받는 사람에게 보내지지 않고 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-207">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="3fc4f-208">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc4f-208">When you're finished, click **Close**.</span></span>
