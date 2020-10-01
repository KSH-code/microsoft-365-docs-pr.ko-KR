---
title: 제로 시간 자동 제거 (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 0 시간 자동 삭제 (ZAP)가 Exchange Online 사서함의 배달 된 메시지를 retroactively에서 정크 메일 폴더로 이동 하는 것을 retroactively 수 있는 격리 또는 피싱 인 것으로 확인 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 31e546ddf6e93ed0a265aef3737182cf30ae5a95
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327978"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="a4357-103">Exchange Online에서 제로 시간 자동 제거 (ZAP)</span><span class="sxs-lookup"><span data-stu-id="a4357-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="a4357-104">ZAP의 기본 기능</span><span class="sxs-lookup"><span data-stu-id="a4357-104">Basic features of ZAP</span></span>

<span data-ttu-id="a4357-105">Exchange Online의 사서함이 있는 Microsoft 365 조 직에서 제로 시간 자동 삭제 (ZAP)는 retroactively에서 Exchange Online 사서함으로 이미 배달 된 악의적인 피싱, 스팸 또는 맬웨어 메시지를 검색 하 고 neutralizes 하는 전자 메일 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="a4357-106">온-프레미스 Exchange 사서함을 보호 하는 독립 실행형 EOP (Exchange Online Protection) 환경에서는 ZAP이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="a4357-107">ZAP 작동 방식</span><span class="sxs-lookup"><span data-stu-id="a4357-107">How ZAP works</span></span>

<span data-ttu-id="a4357-108">스팸 및 맬웨어 서명은 서비스에서 매일 실시간으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="a4357-109">그러나 사용자에 게 콘텐츠를 배달 한 후에 weaponized를 포함 하 여 여러 가지 이유로 인해 여전히 악의적인 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="a4357-110">ZAP은 서비스의 스팸 및 맬웨어 서명에 대 한 업데이트를 지속적으로 모니터링 하 여이 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="a4357-111">ZAP은 이미 사용자의 사서함에 있는 메시지를 찾아 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="a4357-112">사용자가 ZAP 작업을 원활 하 게 수행할 수 있습니다. 메시지를 검색 하 고 이동한 경우 알림을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="a4357-113">[수신 허용-보낸 사람 목록](create-safe-sender-lists-in-office-365.md), 메일 흐름 규칙 (전송 규칙이 라고도 함), 받은 편지함 규칙 또는 추가 필터는 ZAP 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="a4357-114">메일 흐름에서와 마찬가지로 서비스에서 전달 된 메시지의 ZAP이 결정 되는 경우에도 수신 허용-보낸 사람 구성으로 인해 메시지가 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="a4357-115">이는 필터링을 우회 하도록 메시지를 구성 하는 경우에 주의 해야 할 또 다른 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="a4357-116">맬웨어 ZAP</span><span class="sxs-lookup"><span data-stu-id="a4357-116">Malware ZAP</span></span>

<span data-ttu-id="a4357-117">배달 후 맬웨어가 포함 되는 것으로 확인 된 **읽음 또는 읽지 않은 메시지** 에 대해 ZAP 설정별가 맬웨어 첨부 파일을 포함 하는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="a4357-118">관리자만 격리에서 맬웨어 메시지를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="a4357-119">맬웨어 ZAP은 맬웨어 방지 정책에서 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="a4357-120">자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4357-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="a4357-121">피싱 ZAP</span><span class="sxs-lookup"><span data-stu-id="a4357-121">Phish ZAP</span></span>

<span data-ttu-id="a4357-122">배달 후에 피싱으로 식별 되는 **읽음 또는 읽지 않은 메시지** 의 경우 ZAP 결과는 해당 하는 스팸 방지 정책에서 **피싱 전자 메일** 필터링 결과에 대해 구성 된 작업에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-122">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="a4357-123">다음 목록에서는 피싱에 대 한 사용 가능한 필터링 결과 작업 및 가능한 ZAP 결과에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-123">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="a4357-124">**X-헤더 추가**( **제목 줄 앞에 텍스트 포함**): ZAP이 메시지에 대해 작업을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="a4357-125">**정크 메일로 메시지 이동**: ZAP 사서함에서 정크 메일 규칙을 사용 하는 경우 (기본적으로 사용 하도록 설정 되어 있음) 메시지를 정크 메일 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="a4357-126">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4357-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="a4357-127">**전자 메일 주소로 메시지 리디렉션**, **메시지 삭제**, **격리 메시지**: ZAP 설정별 메시지</span><span class="sxs-lookup"><span data-stu-id="a4357-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="a4357-128">기본적으로 스팸 방지 정책에서 피싱 ZAP을 사용 하도록 설정 되어 있으며 **피싱 전자 메일** 필터링 결과의 기본 작업은 **메시지를 격리**하며,이는 메시지를 기본적으로 피싱 ZAP 설정별 한다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="a4357-129">스팸 필터링 verdicts 구성에 대 한 자세한 내용은 [Microsoft 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4357-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="a4357-130">스팸 ZAP</span><span class="sxs-lookup"><span data-stu-id="a4357-130">Spam ZAP</span></span>

<span data-ttu-id="a4357-131">배달 후 스팸으로 식별 된 **읽지 않은 메시지** 의 경우 ZAP 결과는 해당 하는 스팸 방지 정책에서 **스팸** 필터링 결과에 대해 구성 된 작업에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="a4357-132">스팸 및 가능한 ZAP 결과에 대 한 사용 가능한 필터링 결과 작업은 다음 목록에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="a4357-133">**X-헤더 추가**( **제목 줄 앞에 텍스트 포함**): ZAP이 메시지에 대해 작업을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="a4357-134">**정크 메일로 메시지 이동**: ZAP 사서함에서 정크 메일 규칙을 사용 하는 경우 (기본적으로 사용 하도록 설정 되어 있음) 메시지를 정크 메일 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="a4357-135">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4357-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="a4357-136">**전자 메일 주소로 메시지 리디렉션**, **메시지 삭제**, **격리 메시지**: ZAP 설정별 메시지</span><span class="sxs-lookup"><span data-stu-id="a4357-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="a4357-137">최종 사용자는 자신의 스팸 격리 된 메시지를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="a4357-138">기본적으로 스팸 방지 정책에서 스팸 ZAP을 사용 하도록 설정 되어 있으며 스팸 필터링 결과의 기본 작업은 **정크 메일 폴더로 메시지를 이동**하는 것으로 **, 스팸 zap** 은 **읽지 않은** 메시지를 정크 메일 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="a4357-139">스팸 필터링 verdicts 구성에 대 한 자세한 내용은 [Microsoft 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4357-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a><span data-ttu-id="a4357-140">Office 365 Advanced Threat Protection에 대 한 ZAP 고려 사항 (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="a4357-140">ZAP considerations for Office 365 Advanced Threat Protection (Office 365 ATP)</span></span>

<span data-ttu-id="a4357-141">ZAP은 안전한 첨부 파일 검색에서 [동적 배달](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) 프로세스에 있는 메시지를 격리 하지 않으며, EOP 맬웨어 필터링이 이미 해당 첨부 파일을 **맬웨어 경고 Text.txt** 파일로 바꾸었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="a4357-142">이러한 유형의 메시지에 대 한 피싱 또는 스팸 신호를 수신 하 고 스팸 방지 정책의 필터링 결과 메시지에 대 한 특정 작업을 수행 하도록 설정 된 경우 (정크로 이동, 리디렉션, 삭제 또는 격리), ZAP은 ' 정크로 이동 ' 작업을 기본값으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-142">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="a4357-143">메시지가 ZAP에서 이동 된 것을 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a4357-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="a4357-144">ZAP이 메시지를 이동 했는지 확인 하려면 [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report) 또는 [위협 탐색기 (및 실시간 검색)](threat-explorer.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="a4357-145">시스템 작업으로, ZAP이 Exchange 사서함 감사 로그에 기록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="a4357-146">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="a4357-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="a4357-147">합법적인 메시지를 정크 메일 폴더로 이동 하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="a4357-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="a4357-148">[가양성](report-junk-email-messages-to-microsoft.md)에 대 한 일반적인 보고 프로세스를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="a4357-149">메시지를 받은 편지함에서 정크 메일 폴더로 이동 하는 유일한 이유는 서비스가 스팸 또는 악성 메시지를 받는 것으로 확인 되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="a4357-150">정크 메일 폴더 대신 Quarantine 폴더를 사용 하는 경우에는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="a4357-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="a4357-151">ZAP은이 항목의 앞부분에서 설명한 스팸 방지 정책 구성을 기반으로 하는 메시지에 대해 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="a4357-152">수신 허용-보낸 사람, 메일 흐름 규칙 또는 허용/차단 된 보낸 사람 목록을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="a4357-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="a4357-153">수신 허용-보낸 사람, 메일 흐름 규칙 또는 차단 및 조직 설정 허용이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="a4357-154">서비스에서 구성 된 작업을 수행 하는 중 이므로 이러한 메시지는 ZAP에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="a4357-155">이는 필터링을 우회 하도록 메시지를 구성 하는 경우에 주의 해야 할 또 다른 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="a4357-156">다른 폴더 (예: 받은 편지함 규칙)로 메시지를 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="a4357-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="a4357-157">메시지가 삭제 되지 않았거나, 동일 하거나 더 강력 하지만 작업이 아직 적용 되지 않은 경우에도 ZAP이 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="a4357-158">예를 들어 피싱 정책이 quarantine로 설정 되어 있고 사용자 또는 관리자가 이미 전자 메일을 junked 하는 경우 격리를 통해 파일을 격리 하는 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-158">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="a4357-159">ZAP이 보류 중인 사서함에 어떤 영향을 줍니까?</span><span class="sxs-lookup"><span data-stu-id="a4357-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="a4357-160">ZAP은 보류 중인 사서함에서 메시지를 격리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="a4357-161">스팸 방지 정책에서 스팸 또는 피싱 결과에 대해 구성 된 작업을 기반으로 메시지를 정크 메일 폴더로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4357-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="a4357-162">Exchange Online의 보류에 대 한 자세한 내용은 [Exchange online의 원본 위치 유지 및 소송 보존](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4357-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
