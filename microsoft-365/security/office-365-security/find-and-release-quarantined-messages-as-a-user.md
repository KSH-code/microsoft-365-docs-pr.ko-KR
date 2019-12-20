---
title: Office 365에서 사용자 권한으로 격리된 메시지 검색 및 해제
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
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
description: Office 365 사용자는 스팸으로 격리된 자신의 메시지를 수신한 스팸 알림에서 직접 응답(관리자가 기능을 설정한 경우)하거나 보안 &amp; 준수 센터에서 스팸 격리 기능을 사용하여 관리할 수 있습니다.
ms.openlocfilehash: bcc9b7ed52af0e9920506aa667e51daad7f82c80
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808003"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="d1bd3-103">Office 365에서 사용자 권한으로 격리된 메시지 검색 및 해제</span><span class="sxs-lookup"><span data-stu-id="d1bd3-103">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="d1bd3-104">Office 365 사용자는 자신에게 전송되지 않고 격리된 메시지를 [수신한 스팸 알림에서 직접 응답](use-spam-notifications-to-release-and-report-quarantined-messages.md)(관리자가 기능을 설정한 경우)하거나 보안 &amp; 준수 센터에서 스팸 격리 기능을 사용하여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-104">As an Office 365 user, you can manage messages that were sent to quarantine instead of sent to you in one of two ways: by [responding to spam notifications sent to you directly](use-spam-notifications-to-release-and-report-quarantined-messages.md) (if your admin has set this up), or by using the Security &amp; Compliance Center.</span></span>

> [!NOTE]
> <span data-ttu-id="d1bd3-105">관리자는 조직 내 다른 사용자의 [격리된 메시지를 관리](manage-quarantined-messages-and-files.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-105">If you're an admin, you can [manage quarantined messages](manage-quarantined-messages-and-files.md) for other people in your organization.</span></span>

## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a><span data-ttu-id="d1bd3-106">자신에게 전송되지 않고 격리된 메시지 보기</span><span class="sxs-lookup"><span data-stu-id="d1bd3-106">View messages that were sent to quarantine instead of to you</span></span>

1. <span data-ttu-id="d1bd3-107">회사 또는 학교 계정을 사용하여 Office 365에 로그인하고 [보안 및 준수 센터로 이동](../../compliance/go-to-the-securitycompliance-center.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-107">Sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) using your work or school account.</span></span>

2. <span data-ttu-id="d1bd3-108">왼쪽에서 **위협 관리**를 펼치고 **검토**를 선택한 후, **격리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-108">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d1bd3-109">보안 &amp; 준수 센터의 **격리** 페이지로 바로 이동하려면 다음의 URL을 사용합니다. [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="d1bd3-109">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

<span data-ttu-id="d1bd3-110">기본적으로 보안 &amp; 준수 센터는 스팸으로 격리 처리된 모든 전자 메일 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-110">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam.</span></span> <span data-ttu-id="d1bd3-111">메시지를 수신한 **날짜**를 기준으로 최신 항목부터 가장 오래된 항목 순으로 메시지가 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-111">The messages are sorted from newest to oldest based on the **Date** the message was received.</span></span> <span data-ttu-id="d1bd3-112">각 메시지의 **보낸 사람**, **제목**, 만료 날짜(**만료** 아래)도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-112">**Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message.</span></span> <span data-ttu-id="d1bd3-113">해당 열 머리글을 클릭하면 필드를 정렬할 수 있습니다. 열 머리글을 두 번 클릭하면 정렬 순서가 반대로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-113">You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span>

<span data-ttu-id="d1bd3-114">격리된 모든 메시지 목록을 보거나, 필터링하여 특정 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-114">You can view a list of all quarantined messages, or you can search for specific messages by filtering.</span></span> <span data-ttu-id="d1bd3-115">최대 100개 항목에 대해서만 대량 작업을 수행할 수 있으므로 항목이 100개보다 많을 경우 필터링하면 결과 집합을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-115">You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that.</span></span> <span data-ttu-id="d1bd3-116">드롭다운 목록에서 옵션을 선택하여 단일 격리 이유로 메시지를 빠르게 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-116">You can quickly filter messages for a single quarantine reason by choosing an option from the drop-down list.</span></span> <span data-ttu-id="d1bd3-117">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-117">Options include:</span></span>

- <span data-ttu-id="d1bd3-118">스팸으로 식별된 메일.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-118">Mail identified as spam.</span></span> <span data-ttu-id="d1bd3-119">이러한 격리된 메시지는 기본적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-119">These quarantined messages are shown by default.</span></span>

- <span data-ttu-id="d1bd3-120">대량 메일로 식별된 메일.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-120">Mail identified as bulk mail.</span></span>

<span data-ttu-id="d1bd3-121">격리된 특정 메시지를 찾은 후 메시지를 클릭하여 세부 정보를 확인하고 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-121">After you find a specific quarantined message, click the message to view details about it, and take actions.</span></span> <span data-ttu-id="d1bd3-122">메시지를 격리에서 해제하여 사서함으로 보내기, 메시지 미리 보기, 메시지 다운로드하기, 메시지 삭제 등의 작업을 바로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-122">You can release the message to your mailbox, preview the message, download the message, or delete the message from quarantine immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="d1bd3-123">다른 사용자에게 전송된 격리된 메시지에 대해 작업을 수행하려면 Office 365 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-123">You must have admin permissions in Office 365 to work with quarantined messages that were sent to other users.</span></span>

## <a name="to-filter-and-find-quarantined-messages"></a><span data-ttu-id="d1bd3-124">격리된 메시지 필터링 및 검색</span><span class="sxs-lookup"><span data-stu-id="d1bd3-124">To filter and find quarantined messages</span></span>

<span data-ttu-id="d1bd3-125">격리된 항목이 많은 경우 필터링하여 개수를 관리 가능한 집합으로 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-125">If you have a lot of quarantined items, you can reduce the number to a manageable set by filtering them.</span></span>

1. <span data-ttu-id="d1bd3-126">**격리** 페이지에서 **스팸** 또는 **대량 메일** 격리된 메시지를 볼 것인지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-126">On the **Quarantine** page, choose whether you want to view **spam** or **bulk** quarantined messages.</span></span>

2. <span data-ttu-id="d1bd3-127">**결과 정렬 기준** 아래에서 적절한 필터를 설정하여 조건을 임의로 조합해서 선택합니다(지금은 와일드카드를 사용할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="d1bd3-127">Under **Sort results by**, choose any combination of conditions by setting the appropriate filter or filters (you can't use wildcards at this time).</span></span> <span data-ttu-id="d1bd3-128">다음을 포함하여 선택할 수 있는 몇 가지 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-128">There are several conditions you can choose, including the following:</span></span>

   - <span data-ttu-id="d1bd3-129">**메시지 ID**: 메시지 ID를 아는 경우에 특정 메시지를 선택할 때 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-129">**Message ID**: Use this to select a specific message when you know the message ID.</span></span>

     <span data-ttu-id="d1bd3-130">예를 들어, 만약 조직내 사용자에게 메시지를 보내거나 받았어야 했는데 도달하지 않았다면 메시지 추적을 사용해서 메시지를 검색할 수 있습니다([메시지 추적 보안 및 준수 센터](message-trace-scc.md) 보기). </span><span class="sxs-lookup"><span data-stu-id="d1bd3-130">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Message trace in the Security & Compliance Center](message-trace-scc.md)).</span></span> <span data-ttu-id="d1bd3-131">메일 흐름 규칙에 해당하거나 스팸으로 확인되어 격리로 전송된 메시지가 있는 경우에 해당 메시지 ID를 지정하면 메시지를 격리에서 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-131">If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its Message ID.</span></span> <span data-ttu-id="d1bd3-132">전체 메시지 ID 문자열을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-132">Be sure to include the full Message ID string.</span></span> <span data-ttu-id="d1bd3-133">다음과 같이 꺾쇠괄호(\<\>)를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-133">This might include angle brackets (\<\>), for example:</span></span>

     `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`

   - <span data-ttu-id="d1bd3-134">**보낸 사람 전자 메일 주소**: 보낸 사람 단일 전자 메일 주소로 필터링할 때 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-134">**Sender email address**: Choose to filter by a single sender email address.</span></span>

   - <span data-ttu-id="d1bd3-135">**받는 사람 전자 메일 주소**: 받는 사람 단일 전자 메일 주소로 필터링하려면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-135">**Recipient email address**: Choose to filter by a single recipient email address.</span></span>

   - <span data-ttu-id="d1bd3-136">**제목**: 찾으려는 전자 메일 주소의 제목을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-136">**Subject**: Enter the subject of an email address you want to find.</span></span>

   - <span data-ttu-id="d1bd3-137">**날짜 범위**: 메시지가 격리로 전송된 날짜를 기준으로 필터링하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-137">**Date range**: You can choose to filter by the date the message was sent to quarantine.</span></span> <span data-ttu-id="d1bd3-138">시간, 날짜, 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-138">You can specify the date or a date range, including the time.</span></span>

   - <span data-ttu-id="d1bd3-139">**만료 날짜**: 만료 날짜로 검색하려면 **고급 필터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-139">**Expiration date**: To filter by expiration date, choose **Advanced filter**.</span></span> <span data-ttu-id="d1bd3-140">다음 24시간(**오늘**) 이내, 다음 48시간(**다음 2일**) 이내, 다음 주(**다음 7일**) 이내, 또는 사용자 지정된 시간 간격에 메시지가 격리에서 삭제되도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-140">You can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="d1bd3-141">기본적으로 스팸 및 대량 메일 메시지는 30일 동안 격리에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-141">By default, spam and bulk messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="d1bd3-142">그러나 이 기간은 구성 가능하며 관리자가 다른 격리 보존 기간을 설정했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-142">However, this time period is configurable and your admin might have set a different quarantine retention period.</span></span> <span data-ttu-id="d1bd3-143">Office 365가 격리에서 메시지를 삭제하면 해당 메시지를 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-143">When Office 365 deletes a message from quarantine, you can't get it back.</span></span>

## <a name="view-details-for-a-specific-message"></a><span data-ttu-id="d1bd3-144">특정 메시지에 대한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="d1bd3-144">View details for a specific message</span></span>

<span data-ttu-id="d1bd3-145">메시지를 선택하면 페이지 오른쪽 창에 메시지 속성에 대한 요약이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-145">After you select a message, you'll see a summary of the message properties in a pane on the right side of the page.</span></span>

- <span data-ttu-id="d1bd3-146">**메시지 ID**: 메시지의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-146">**Message ID**: The unique identifier for the message.</span></span>

- <span data-ttu-id="d1bd3-147">**보낸 사람 주소**: 메시지를 보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-147">**Sender Address**: Who sent the message.</span></span>

- <span data-ttu-id="d1bd3-148">**받은 날짜**: 메시지를 수신한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-148">**Received**: The date the message was received.</span></span>

- <span data-ttu-id="d1bd3-149">**제목**: 메시지 제목 줄의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-149">**Subject**: The text of the Subject line in the message.</span></span>

- <span data-ttu-id="d1bd3-150">**격리 이유**: 메시지가 **스팸**으로 구분되었는지, 아니면 **대량 메일**로 구분되었는지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-150">**Quarantine reason**: Shows if a message has been identified as **Spam** or **Bulk**.</span></span>

- <span data-ttu-id="d1bd3-151">**만료**: 메시지가 격리에서 삭제되는 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-151">**Expires**: The date when the message will be deleted from quarantine.</span></span>

- <span data-ttu-id="d1bd3-152">**해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-152">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="d1bd3-153">**아직 해제되지 않음**: 메시지가 아직 해제되지 않은 모든 전자 메일 주소(해당되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-153">**Not yet released to**: All email addresses (if any) to which the message has not been released.</span></span> <span data-ttu-id="d1bd3-154">메시지를 사서함으로 해제하려는 경우 **해제**를 선택할 수 있습니다(더 자세한 정보는 다음 섹션의 메시지 해제 참조).</span><span class="sxs-lookup"><span data-stu-id="d1bd3-154">You can choose **Release** if you want to release the message to your mailbox (more about releasing messages in the next section).</span></span>

<span data-ttu-id="d1bd3-155">다음 옵션 중 하나를 선택하면 메시지에 대한 더 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-155">You can get even more details about the message by choosing one of the following options:</span></span>

- <span data-ttu-id="d1bd3-156">**메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-156">**View message header**: Choose this to see the message header text.</span></span> <span data-ttu-id="d1bd3-157">헤더를 자세히 분석하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음 **Microsoft 메시지 헤더 분석기**를 선택하여 원격 연결 분석기로 이동합니다(이 작업을 수행할 때 Office 365를 닫지 않으려면 마우스 오른쪽 단추를 클릭하고 새 탭에서 열기 선택).</span><span class="sxs-lookup"><span data-stu-id="d1bd3-157">To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose Open in a new tab if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="d1bd3-158">메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여넣고 헤더 분석을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-158">Paste the message header onto the page in the Message Header Analyzer section, and choose Analyze headers.</span></span>

- <span data-ttu-id="d1bd3-159">**메시지 미리 보기**: 메시지 본문 텍스트의 원시 또는 HTML 버전을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-159">**Preview message**: Lets you see raw or HTML versions of the message body text.</span></span> <span data-ttu-id="d1bd3-160">HTML 보기에서는 링크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-160">In the HTML view, links are disabled.</span></span>

## <a name="manage-your-quarantined-messages"></a><span data-ttu-id="d1bd3-161">격리된 메시지 관리</span><span class="sxs-lookup"><span data-stu-id="d1bd3-161">Manage your quarantined messages</span></span>

<span data-ttu-id="d1bd3-162">메시지 또는 메시지 그룹을 선택한 후 격리된 메시지를 관리하기 위한 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-162">After you select a message or group of messages, you have several options for managing messages in quarantine.</span></span>

- <span data-ttu-id="d1bd3-163">아무 작업도 하지 않음.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-163">Do nothing.</span></span> <span data-ttu-id="d1bd3-164">아무 작업도 하지 않도록 선택하면 Office 365에서 만료 시 메시지를 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-164">If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration.</span></span> <span data-ttu-id="d1bd3-165">Office 365가 메시지를 격리에서 삭제하면 해당 메시지는 다시 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-165">Remember, when Office 365 deletes a message from quarantine, you can't get it back.</span></span>

- <span data-ttu-id="d1bd3-166">**메시지 해제**: 격리된 메시지(또는 여러 메시지)를 해제하여 사서함으로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-166">**Release message**: Release a quarantined message (or set of messages) so that the message is sent to your mailbox.</span></span> <span data-ttu-id="d1bd3-167">메시지를 해제할 때, Microsoft가 분석을 하도록 메시지를 보고하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-167">When you release a message, you have the option to report the message to Microsoft for analysis.</span></span>

    <span data-ttu-id="d1bd3-168">메시지를 보고(메시지를 가양성으로 보고라고도 함)하도록 선택하면 메시지가 Microsoft 스팸 분석 팀에게 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-168">When you choose to report a message, also called reporting a message as a false positive, the message is reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="d1bd3-169">팀은 가양성 메시지를 평가 및 분석하며, 분석 결과에 따라 서비스 수준 스팸 콘텐츠 필터 규칙이 이러한 메시지를 허용하도록 조정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-169">The team evaluates and analyzes false positive messages, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow these messages through.</span></span>

- <span data-ttu-id="d1bd3-170">**격리에서 제거**: 메시지를 사서함으로 해제하지 않고 메시지를 격리에서 바로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d1bd3-170">**Remove from quarantine**: Deletes the message immediately from quarantine without releasing the message to your mailbox.</span></span>
