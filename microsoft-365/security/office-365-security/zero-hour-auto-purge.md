---
title: 제로 아사이트 자동 비우기(ZAP)
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
description: 관리자는 ZAP(제로 아우스 자동 비우기)가 Exchange Online 사서함의 배달된 메시지를 스팸 또는 피싱으로 사후 분류된 격리나 정크 메일 폴더로 리드로 이어지는 방법에 대해 알아질 수 있습니다.
ms.openlocfilehash: 9096486ed98657fede7927089592c92fffdad70e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826700"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="8b085-103">Exchange Online의 ZAP(제로 아우스 자동 비우기)</span><span class="sxs-lookup"><span data-stu-id="8b085-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

## <a name="basic-features-of-zap"></a><span data-ttu-id="8b085-104">ZAP의 기본 기능</span><span class="sxs-lookup"><span data-stu-id="8b085-104">Basic features of ZAP</span></span>

<span data-ttu-id="8b085-105">Exchange Online의 사서함이 있는 Microsoft 365 조직에서 ZAP(제로 아르기 자동 비우기)는 Exchange Online 사서함으로 이미 배달된 악성, 스팸 또는 맬웨어 메시지를 사실로 감지하고 중을 보내는 전자 메일 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="8b085-106">ZAP는 온-프레미스 Exchange 사서함을 보호하는 독립 실행형 EOP(Exchange Online Protection) 환경에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="8b085-107">ZAP 작동 방식</span><span class="sxs-lookup"><span data-stu-id="8b085-107">How ZAP works</span></span>

<span data-ttu-id="8b085-108">스팸 및 맬웨어 서명은 매일 서비스에서 실시간으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="8b085-109">그러나 사용자는 사용자에게 콘텐츠가 전달된 후 콘텐츠가 환중화된 경우를 포함하여 다양한 이유로 악성 메시지를 계속 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="8b085-110">ZAP는 서비스에서 스팸 및 맬웨어 서명에 지속적으로 업데이트를 모니터링하여 이 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="8b085-111">ZAP는 이미 사용자 사서함에 있는 메시지를 찾아 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="8b085-112">ZAP 작업은 사용자에게 일특하지 않습니다. 또한 메시지가 탐지되어 이동될 경우 알리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="8b085-113">[수신 허용 - 보낸](create-safe-sender-lists-in-office-365.md)사람 목록, 메일 흐름 규칙(전송 규칙이라고도 함), 받은 편지함 규칙 또는 추가 필터는 ZAP보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="8b085-114">이는 메일 흐름에서 의미와 유사하게, 서비스에 배달된 메시지에 ZAP가 필요하다고 결정해도 안전한 보낸 사람 구성으로 인해 메시지가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="8b085-115">이는 필터링을 무시하도록 메시지를 구성할 때 주의해야 할 다른 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="8b085-116">맬웨어 ZAP</span><span class="sxs-lookup"><span data-stu-id="8b085-116">Malware ZAP</span></span>

<span data-ttu-id="8b085-117">배달 **후 맬웨어가 포함된** 읽거나 읽지 않은 메시지의 경우 ZAP는 맬웨어 첨부 파일을 포함하는 메시지를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="8b085-118">관리자만 격리에서 맬웨어 메시지를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="8b085-119">맬웨어 ZAP는 맬웨어 방지 정책에서 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="8b085-120">자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을 참조하세요.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8b085-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="8b085-121">피싱 ZAP</span><span class="sxs-lookup"><span data-stu-id="8b085-121">Phish ZAP</span></span>

<span data-ttu-id="8b085-122">배달 **후 피싱으로 식별된** 메시지를 읽거나 읽지 않은 메시지의 경우 ZAP 결과는 해당 스팸 방지 정책에서 **피싱 전자** 메일 필터링 결과에 대해 구성한 작업에 따라 달라지기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-122">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="8b085-123">다음 목록에는 피싱에 대한 사용 가능한 필터링 결과 작업과 가능한 ZAP 결과가 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-123">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="8b085-124">**X-헤더 추가,** **제목 줄 끝에 텍스트를**추가: ZAP는 메시지에서 작업이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="8b085-125">**정크 메일로 메시지**이동 : ZAP는 사서함에 정크 메일 규칙이 활성화되어 있는 한 정크 메일 폴더로 메시지를 이동합니다(기본적으로 활성화되어 있음).</span><span class="sxs-lookup"><span data-stu-id="8b085-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="8b085-126">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="8b085-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="8b085-127">**전자 메일 주소로 메시지** **리디렉션,** 메시지 **삭제, 격리**메시지: ZAP는 메시지를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="8b085-128">기본적으로 피싱 ZAP는 스팸 방지 정책에서 사용하도록 설정되어 있고 피싱 **전자** 메일 필터링 결과에 대한 기본 작업은 **격리**메시지입니다. 따라서 피싱 ZAP는 기본적으로 메시지를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="8b085-129">스팸 필터링 조건을 구성하는 방법에 대한 자세한 내용은 [Microsoft 365의 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8b085-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="8b085-130">스팸 ZAP</span><span class="sxs-lookup"><span data-stu-id="8b085-130">Spam ZAP</span></span>

<span data-ttu-id="8b085-131">배달 **후 스팸으로** 확인된 읽지 않은 메시지의 경우 ZAP 결과는 해당 스팸 방지 **정책에서 스팸 필터링 결과에** 대해 구성된 작업에 따라 달라지며</span><span class="sxs-lookup"><span data-stu-id="8b085-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="8b085-132">다음 목록에서는 스팸에 대해 사용 가능한 필터링 결과 작업 과정과 가능한 ZAP 결과에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="8b085-133">**X-헤더 추가,** **제목 줄 끝에 텍스트를**추가: ZAP는 메시지에서 작업이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="8b085-134">**정크 메일로 메시지**이동 : ZAP는 사서함에 정크 메일 규칙이 활성화되어 있는 한 정크 메일 폴더로 메시지를 이동합니다(기본적으로 활성화되어 있음).</span><span class="sxs-lookup"><span data-stu-id="8b085-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="8b085-135">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="8b085-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="8b085-136">**전자 메일 주소로 메시지** **리디렉션,** 메시지 **삭제, 격리**메시지: ZAP는 메시지를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="8b085-137">최종 사용자는 자신의 스팸 격리 메시지를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="8b085-138">스팸 ZAP는 스팸 방지 정책에서 기본적으로 사용하도록 설정되어 **Spam** 있고 스팸 필터링 결과에 대한 기본 작업은 메시지를 정크 메일 **unread** **폴더로 이동하는**것입니다. 따라서 스팸 ZAP는 기본적으로 읽지 않은 메시지를 정크 메일 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="8b085-139">스팸 필터링 조건을 구성하는 방법에 대한 자세한 내용은 [Microsoft 365의 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8b085-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a><span data-ttu-id="8b085-140">Office 365 ATP(Advanced Threat Protection)에 대한 ZAP 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8b085-140">ZAP considerations for Office 365 Advanced Threat Protection (Office 365 ATP)</span></span>

<span data-ttu-id="8b085-141">ZAP는 동적 배달 검사 프로세스에 있는 메시지나 맬웨어 필터링이 이미 맬웨어 경고 Text.txt파일로 첨부 파일을 대체한 위치를 **격리시키지** 않습니다. [Dynamic Delivery](dynamic-delivery-and-previewing.md)</span><span class="sxs-lookup"><span data-stu-id="8b085-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="8b085-142">이러한 유형의 메시지에 대한 피싱 또는 스팸 신호를 받고 메시지(정크 메일로 이동, 리디렉션, 삭제, 격리로 이동) 메시지에 대해 특정 작업을 수행하도록 설정되어 있는 경우 ZAP는 기본적으로 '정크 메일로 이동' 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-142">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="8b085-143">ZAP가 메시지를 이동한 지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="8b085-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="8b085-144">ZAP에서 메시지를 이동하라는 확인하려면 위협 방지 [상태 보고서](view-email-security-reports.md#threat-protection-status-report) 또는 [위협 탐색기(실시간 검색)를 사용하면 됩니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="8b085-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="8b085-145">시스템 작업으로 ZAP는 Exchange 사서함 감사 로그에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="8b085-146">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="8b085-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="8b085-147">합법적 메시지가 정크 메일 폴더로 이동된 경우 어떻게 됩니까?</span><span class="sxs-lookup"><span data-stu-id="8b085-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="8b085-148">가양성에 대한 일반 보고 [프로세스를 따라야 합니다.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="8b085-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="8b085-149">이유로 받은 편지함에서 정크 메일 폴더로 메시지가 이동되는 이유는 서비스에서 메시지가 스팸 또는 악의적으로 확인되었기 때문이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="8b085-150">정크 메일 폴더 대신 격리 폴더를 사용하는 경우 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="8b085-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="8b085-151">ZAP는 이 항목 앞부분에서 설명한 것과 같이 구성을 기반으로 메시지에 대해 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="8b085-152">수신 허용 - 보낸 사람, 메일 흐름 규칙 또는 허용/수신 거부 목록을 사용하고 있는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="8b085-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="8b085-153">안전한 보낸 사람, 메일 흐름 규칙 또는 조직 설정을 우선및 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="8b085-154">서비스에서 구성한 작업을 수행하므로 이러한 메시지는 ZAP에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="8b085-155">이는 필터링을 무시하도록 메시지를 구성할 때 주의해야 할 다른 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="8b085-156">메시지가 다른 폴더(예: 받은 편지함 규칙)로 이동된 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="8b085-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="8b085-157">ZAP는 메시지가 삭제되지 않았거나 동일한(봉계) 작업이 아직 적용되지 않은 한 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="8b085-158">예를 들어 피싱 정책이 격리로 설정되어 있고 사용자 또는 관리자가 이미 이메일을 정크한 경우 격리는 파일을 격리하기 위한 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-158">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="8b085-159">ZAP가 보류된 사서함에 어떤 영향을 주나요?</span><span class="sxs-lookup"><span data-stu-id="8b085-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="8b085-160">ZAP는 보류된 사서함에서 메시지를 격리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="8b085-161">ZAP는 스팸 방지 정책의 스팸 또는 피싱 결과에 대해 구성된 작업에 따라 정크 메일 폴더로 메시지를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b085-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="8b085-162">Exchange Online의 보류에 대한 자세한 내용은 Exchange [Online의 원본 위치 유지 및 소송 보존을 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)</span><span class="sxs-lookup"><span data-stu-id="8b085-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
