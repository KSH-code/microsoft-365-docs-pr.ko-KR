---
title: ZAP(제로 아워 자동 비우기)
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
description: 관리자는 ZAP(제로 아워 자동 비우기)가 Exchange Online 사서함의 배달된 메시지를 스팸 또는 피싱으로 소급하여 정크 메일 폴더로 이동하는 방법을 알 수 있습니다.
ms.openlocfilehash: 7b43fb46adacfe1e9f1e7e622122df90e747ff44
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659432"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="9c3a2-103">Exchange Online의 ZAP(제로 아워 자동 비우기)</span><span class="sxs-lookup"><span data-stu-id="9c3a2-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="9c3a2-104">ZAP의 기본 기능</span><span class="sxs-lookup"><span data-stu-id="9c3a2-104">Basic features of ZAP</span></span>

<span data-ttu-id="9c3a2-105">Exchange Online에 사서함이 있는 Microsoft 365 조직에서 ZAP(제로 아워 자동 비우기)는 Exchange Online 사서함으로 이미 배달된 악의적인 피싱, 스팸 또는 맬웨어 메시지를 소급적으로 감지하고 중화하는 전자 메일 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="9c3a2-106">ZAP는 Exchange 사서함을 보호하는 독립 실행형 EOP(Exchange Online Protection) 환경에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="9c3a2-107">ZAP 작동 방식</span><span class="sxs-lookup"><span data-stu-id="9c3a2-107">How ZAP works</span></span>

<span data-ttu-id="9c3a2-108">스팸 및 맬웨어 서명은 서비스에서 매일 실시간으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="9c3a2-109">그러나 콘텐츠가 사용자에게 배달된 후 콘텐츠를 배달하는 경우를 포함하여 다양한 이유로 여전히 악의적인 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="9c3a2-110">ZAP는 서비스의 스팸 및 맬웨어 서명에 대한 업데이트를 지속적으로 모니터링하여 이 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="9c3a2-111">ZAP는 사용자 사서함에 이미 있는 메시지를 찾아 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="9c3a2-112">ZAP 작업은 사용자에게 매끄럽게 수행됩니다. 메시지가 검색되고 이동된 경우 알림을 수신하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="9c3a2-113">[수신 가능한 보낸](create-safe-sender-lists-in-office-365.md)사람 목록, 메일 흐름 규칙(전송 규칙), 받은 편지함 규칙 또는 추가 필터가 ZAP보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="9c3a2-114">메일 흐름에서 발생하는 일과 마찬가지로, 이는 서비스에서 배달된 메시지에 ZAP가 필요하다고 판단하는 경우에도 수신이 안전한 보낸 사람 구성으로 인하여 메시지가 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="9c3a2-115">이는 필터링을 무시할 메시지를 구성할 때 주의해야 하는 또 다른 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="9c3a2-116">맬웨어 ZAP</span><span class="sxs-lookup"><span data-stu-id="9c3a2-116">Malware ZAP</span></span>

<span data-ttu-id="9c3a2-117">배달 **후** 맬웨어가 포함된 것으로 확인된 읽거나 읽지 않은 메시지의 경우 ZAP는 맬웨어 첨부 파일이 포함된 메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="9c3a2-118">관리자만이 맬웨어 메시지를 확인 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="9c3a2-119">맬웨어 ZAP는 기본적으로 맬웨어 방지 정책에서 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="9c3a2-120">자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을 참조하세요.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9c3a2-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="9c3a2-121">피싱 ZAP</span><span class="sxs-lookup"><span data-stu-id="9c3a2-121">Phish ZAP</span></span>

<span data-ttu-id="9c3a2-122">배달  후 피싱으로 식별된 읽거나 읽지 않은 메시지의 경우 ZAP 결과는 해당  스팸 방지 정책에서 피싱 전자 메일 필터링 결과에 대해 구성된 동작에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-122">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="9c3a2-123">피싱에 대한 사용 가능한 필터링 결과 작업 및 가능한 ZAP 결과에 대한 설명은 다음 목록에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-123">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="9c3a2-124">**X-Header** **추가**, 제목 줄에 텍스트 추가: ZAP는 메시지에 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="9c3a2-125">**정크 메일로** 메시지 이동: ZAP는 사서함에서 정크 메일 규칙이 사용하도록 설정된 경우(기본적으로 사용하도록 설정되어 있는 경우) 메시지를 정크 메일 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="9c3a2-126">자세한 내용은 [Microsoft 365의 Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)사서함에 대한 정크 메일 설정 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="9c3a2-127">**메시지를 전자 메일 주소로 리디렉션**, 메시지 **삭제**, 메시지 **Quarantine 메시지**: ZAP가 메시지를 검지합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="9c3a2-128">기본적으로 피싱 ZAP는 스팸 방지 정책에서 사용하도록 설정되어  있으며, 피싱 전자 메일 필터링 판정에 대한 기본 작업은 피싱 ZAP가 메시지를 기본적으로 차단하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="9c3a2-129">스팸 필터링 판정 구성에 대한 자세한 내용은 [Microsoft 365에서](configure-your-spam-filter-policies.md)스팸 방지 정책 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="9c3a2-130">스팸 ZAP</span><span class="sxs-lookup"><span data-stu-id="9c3a2-130">Spam ZAP</span></span>

<span data-ttu-id="9c3a2-131">배달 **후** 스팸으로 식별되는 읽을 수 없는 메시지의 경우 ZAP 결과는 해당  스팸 방지 정책에서 스팸 필터링 결과에 대해 구성된 동작에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="9c3a2-132">다음 목록에는 스팸 및 해당 가능한 ZAP 결과에 대해 사용할 수 있는 필터링 결과 작업이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="9c3a2-133">**X-Header** **추가**, 제목 줄에 텍스트 추가: ZAP는 메시지에 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="9c3a2-134">**정크 메일로** 메시지 이동: ZAP는 사서함에서 정크 메일 규칙이 사용하도록 설정된 경우(기본적으로 사용하도록 설정되어 있는 경우) 메시지를 정크 메일 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="9c3a2-135">자세한 내용은 [Microsoft 365의 Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)사서함에 대한 정크 메일 설정 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="9c3a2-136">**메시지를 전자 메일 주소로 리디렉션**, 메시지 **삭제**, 메시지 **Quarantine 메시지**: ZAP가 메시지를 검지합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="9c3a2-137">최종 사용자는 자신의 스팸으로 차단된 메시지를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="9c3a2-138">기본적으로 스팸 ZAP는 스팸 방지 정책에서 사용하도록 설정되어  있으며 스팸 필터링 판정에 대한 기본 작업은 메시지를 정크  메일 폴더로 이동하는 것입니다. **즉,** 스팸 ZAP는 기본적으로 언데이트 메시지를 정크 메일 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="9c3a2-139">스팸 필터링 판정 구성에 대한 자세한 내용은 [Microsoft 365에서](configure-your-spam-filter-policies.md)스팸 방지 정책 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="9c3a2-140">Office 365용 Microsoft Defender에 대한 ZAP 고려 사항</span><span class="sxs-lookup"><span data-stu-id="9c3a2-140">ZAP considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9c3a2-141">ZAP는 안전 첨부 파일 검색에서 동적 배달 [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) 프로세스에 있는 메시지나 EOP 맬웨어 필터링이 첨부 파일을 이미 맬웨어 경고 파일로 Text.txt **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9c3a2-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="9c3a2-142">이러한 유형의 메시지에 대해 피싱 또는 스팸 신호를 수신하고 스팸 방지 정책의 필터링 판정이 메시지에 대해 일부 작업(정크, 리디렉션, 삭제 또는 Quarantine으로 이동)으로 설정된 경우 ZAP는 기본적으로 '정크로 이동' 작업으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-142">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="9c3a2-143">ZAP에서 메시지를 이동한 경우를 표시하는 방법</span><span class="sxs-lookup"><span data-stu-id="9c3a2-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="9c3a2-144">ZAP가 메시지를 이동한지 확인하려면 위협 [](view-email-security-reports.md#threat-protection-status-report) 방지 상태 보고서 또는 위협 탐색기(및 실시간 검색)를 사용할 [수 있습니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="9c3a2-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="9c3a2-145">시스템 작업으로 ZAP는 Exchange 사서함 감사 로그에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="9c3a2-146">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="9c3a2-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="9c3a2-147">합법적인 메시지가 정크 메일 폴더로 이동하면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="9c3a2-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="9c3a2-148">가짓 긍정에 대한 일반적인 보고 [프로세스를 따라야 합니다.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="9c3a2-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="9c3a2-149">메시지가 받은 편지함에서 정크 메일 폴더로 이동하는 유일한 이유는 서비스에서 메시지가 스팸 또는 악성으로 확인된 것이기뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="9c3a2-150">정크 메일 폴더 대신 Quarantine 폴더를 사용하는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="9c3a2-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="9c3a2-151">ZAP는 이 문서의 앞부분에서 설명한 대로 스팸 방지 정책의 구성에 따라 메시지에 대해 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this article.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="9c3a2-152">수신 허용 - 보낸 사람, 메일 흐름 규칙 또는 허용/차단된 보낸 사람 목록을 사용하는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="9c3a2-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="9c3a2-153">수신 허용 - 보낸 사람, 메일 흐름 규칙 또는 차단 및 허용 조직 설정이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="9c3a2-154">서비스가 사용자가 구성한 작업을 수행 중이기 때문에 이러한 메시지는 ZAP에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="9c3a2-155">이는 필터링을 무시할 메시지를 구성할 때 주의해야 하는 또 다른 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="9c3a2-156">메시지가 다른 폴더(예: 받은 편지함 규칙)로 이동된 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="9c3a2-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="9c3a2-157">ZAP는 메시지가 삭제되지 않은 경우 또는 동일하거나 더 강력한 작업이 아직 적용되지 않은 한 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="9c3a2-158">예를 들어 피싱 방지 정책이 정크 메일에 이미 있는 경우 ZAP는 메시지를 검지하기 위한 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-158">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="9c3a2-159">ZAP는 보류된 사서함에 어떤 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="9c3a2-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="9c3a2-160">ZAP는 보류된 사서함의 메시지를 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="9c3a2-161">ZAP는 스팸 방지 정책에서 스팸 또는 피싱 판정에 대해 구성된 작업을 기반으로 정크 메일 폴더로 메시지를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c3a2-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="9c3a2-162">Exchange Online의 보류에 대한 자세한 내용은 [Exchange Online의 In-Place Hold and Litigation Hold를 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)</span><span class="sxs-lookup"><span data-stu-id="9c3a2-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
