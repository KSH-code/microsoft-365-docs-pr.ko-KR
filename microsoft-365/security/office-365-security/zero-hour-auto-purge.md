---
title: 제로 아워 자동 비우기 - 스팸 및 맬웨어로부터 보호
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
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
description: ZAP (자동 삭제)은 사용자의 받은 편지 함으로 이미 배달 된 스팸 또는 맬웨어가 있는 메시지를 검색 한 다음 악의적인 콘텐츠를 렌더링 하는 전자 메일 보호 기능입니다. ZAP이 수행 하는 방법은 검색 된 악의적인 콘텐츠의 유형에 따라 다릅니다.
ms.openlocfilehash: 725dc9da9119169937231372585489bdf192b11e
ms.sourcegitcommit: 0d423b50d2f1f4eccd64e35e00f67313244efba9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37319271"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="6b4b6-104">제로 아워 자동 비우기 - 스팸 및 맬웨어로부터 보호</span><span class="sxs-lookup"><span data-stu-id="6b4b6-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="6b4b6-105">개요</span><span class="sxs-lookup"><span data-stu-id="6b4b6-105">Overview</span></span>

<span data-ttu-id="6b4b6-106">ZAP (자동 삭제)은 사용자의 받은 편지 함으로 이미 배달 된 피싱, 스팸 또는 맬웨어가 있는 메시지를 검색 한 다음 악성 콘텐츠 무해 함을 렌더링 하는 전자 메일 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="6b4b6-107">ZAP이 수행 하는 방법은 검색 된 악의적인 콘텐츠의 유형에 따라 다릅니다. 메일은 mail content, Url 또는 attachments로 인해 zapped 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="6b4b6-108">ZAP은 Exchange Online 사서함이 포함 된 모든 Office 365 구독에 포함 된 기본 Exchange Online Protection에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="6b4b6-109">ZAP은 기본적으로 설정 되어 있지만 다음 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="6b4b6-110">**스팸 작업** 은 **정크 메일 폴더로 메시지를 이동**하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="6b4b6-111">또한 모든 사서함을 ZAP에 게 표시 하지 않으려는 경우 사용자 집합에만 적용 되는 새 스팸 필터 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="6b4b6-112">사용자가 기본 정크 메일 설정을 유지 했으며 정크 메일 보호를 해제 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="6b4b6-113">(Outlook의 사용자 옵션에 대 한 자세한 내용은 [정크 메일 필터의 보호 수준 변경을](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="6b4b6-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>
  
## <a name="how-zap-works"></a><span data-ttu-id="6b4b6-114">ZAP 작동 방식</span><span class="sxs-lookup"><span data-stu-id="6b4b6-114">How ZAP works</span></span>

<span data-ttu-id="6b4b6-115">Office 365에서는 매일 실시간으로 스팸 방지 엔진 및 맬웨어 서명을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="6b4b6-116">그러나 사용자에 게 콘텐츠를 배달 한 후에 weaponized를 포함 하 여 여러 가지 이유로 인해 사용자가 여전히 해당 받은 편지함에 악성 메시지를 배달 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="6b4b6-117">ZAP은 Office 365 스팸 및 맬웨어 서명에 대 한 업데이트를 지속적으로 모니터링 하 여이를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="6b4b6-118">ZAP은 이전에 전달한 메시지 중 사용자의 받은 편지함에 이미 배달 된 메시지가 있는지 찾아 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="6b4b6-119">사서함 사용자에 게는 ZAP 동작이 원활 하 게 수행 됩니다. 전자 메일 메시지를 이동 하는 경우이 사용자에 게 알림이 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="6b4b6-120">메시지가 2 일 보다 오래 된 것은 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="6b4b6-121">허용 목록, [메일 흐름 규칙](https://go.microsoft.com/fwlink/p/?LinkId=722755) (전송 규칙이 라고도 함) 및 최종 사용자 규칙 또는 추가 필터가 ZAP 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="6b4b6-122">맬웨어 ZAP</span><span class="sxs-lookup"><span data-stu-id="6b4b6-122">Malware ZAP</span></span>

<span data-ttu-id="6b4b6-123">새로 검색 된 맬웨어의 경우 ZAP은 전자 메일 메시지에서 첨부 파일을 제거 하 고 사용자 사서함에는 메시지 본문을 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-123">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="6b4b6-124">메일의 읽기 상태에 관계 없이 첨부 파일이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-124">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="6b4b6-125">맬웨어 ZAP은 맬웨어 정책에서 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-125">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="6b4b6-126">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell의 [get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) Cmdlet에서 *ZapEnabled* 매개 변수를 사용 하 여 맬웨어 ZAP을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-126">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="6b4b6-127">피싱 ZAP</span><span class="sxs-lookup"><span data-stu-id="6b4b6-127">Phish ZAP</span></span>

<span data-ttu-id="6b4b6-128">배달 후에 피싱으로 식별 되는 메일의 경우에는 사용자에 게 적용 되는 스팸 정책에 따라 ZAP이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-128">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="6b4b6-129">피싱 action이 메일에 대해 작업을 수행 하도록 설정 된 경우 (리디렉션, 삭제, 격리, 정크로 이동) ZAP은 메일의 읽기 상태에 관계 없이 사용자의 받은 편지함에 있는 정크 메일 폴더로 메시지를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-129">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="6b4b6-130">정책 피싱 동작이 작업을 수행 하도록 설정 되지 않은 경우 (X-헤더 추가, 주체 수정, 작업 없음) ZAP은 메일에 대해 작업을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-130">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="6b4b6-131">[스팸 필터 정책을 구성](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) 하는 방법에 대 한 자세한 내용은 여기에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-131">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="6b4b6-132">피싱 ZAP은 스팸 정책에서 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-132">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="6b4b6-133">EOP cmdlet의 *PhishZapEnabled* 매개 변수를 사용 하 여 피싱 ZAP을 사용 하지 [않도록 설정할 수](https://go.microsoft.com/fwlink/p/?LinkId=722758)있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-133">Phish ZAP can be disabled using the *PhishZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>

> <span data-ttu-id="6b4b6-134">**[참고]** 피싱 및 스팸 ZAP을 모두 제어 하는 이전 *ZapEnabled* cmdlet 매개 변수는 **사용 되지 않으며, 2020 년 2 월 1**일입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-134">**[NOTE]** the previous *ZapEnabled* cmdlet parameter which controlled both Phish and Spam ZAP will be **deprecated February 1, 2020**.</span></span> <span data-ttu-id="6b4b6-135">ZapEnabled 매개 변수를 사용 하는 스크립트를 작성 한 경우이를 SpamZapEnabled 및 PhishZapEnabled를 사용 하도록 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-135">If you have written any scripts which use the ZapEnabled parameter, we recommend updating them to use SpamZapEnabled and PhishZapEnabled.</span></span> <span data-ttu-id="6b4b6-136">전환 기간에는 cmdlet을 통해 모든 3 개의 매개 변수 (ZapEnabled, PhishZapEnabled 및 SpamZapEnabled)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-136">In the transitional period all 3 parameters (ZapEnabled, PhishZapEnabled, and SpamZapEnabled) will be available through the cmdlet.</span></span> <span data-ttu-id="6b4b6-137">UI 또는 PowerShell을 통해 명시적으로 설정 하기 전에는 PhishZapEnabled 및 SpamZapEnabled에 ZapEnabled 매개 변수의 상속 된 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-137">Until explicitly set via UI or PowerShell, PhishZapEnabled and SpamZapEnabled will show an inherited value from the ZapEnabled parameter.</span></span> <span data-ttu-id="6b4b6-138">새 매개 변수를 설정한 후에는 ZapEnabled 매개 변수에서 더 이상 상속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-138">Once the new parameters are set, they will no longer inherit from the ZapEnabled parameter.</span></span> <span data-ttu-id="6b4b6-139">이 기능을 사용 하지 않으면 ZapEnabled 설정이 PhishZapEnabled 또는 SpamZapEnabled 속성에 영향을 주지 않으며 ZapEnabled가 cmdlet의 매개 변수 목록에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-139">After it is deprecated, setting ZapEnabled will have no affect on the PhishZapEnabled or SpamZapEnabled properties and ZapEnabled will be removed from the list of parameters in cmdlets.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="6b4b6-140">스팸 ZAP</span><span class="sxs-lookup"><span data-stu-id="6b4b6-140">Spam ZAP</span></span>

<span data-ttu-id="6b4b6-141">배달 후 스팸으로 확인 된 메일의 경우에는 사용자에 게 적용 되는 스팸 정책에 따라 ZAP이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-141">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="6b4b6-142">메일에 대해 작업을 수행 하도록 정책 스팸 작업을 설정한 경우 (리디렉션, 삭제, 격리, 정크로 이동), 메시지가 읽지 않은 경우에는 메시지가 사용자의 받은 편지함에 있는 정크 메일 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-142">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="6b4b6-143">정책 스팸 작업이 작업을 수행 하도록 설정 되지 않은 경우 (X-헤더 추가, 주체 수정, 작업 없음) ZAP은 메일에 대해 작업을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-143">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="6b4b6-144">[스팸 필터 정책을 구성](configure-your-spam-filter-policies.md) 하는 방법에 대 한 자세한 내용은 여기에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-144">Learn more about how to [Configure your spam filter policies](configure-your-spam-filter-policies.md) here.</span></span>

<span data-ttu-id="6b4b6-145">스팸 ZAP은 스팸 정책에서 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-145">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="6b4b6-146">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 [get-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) Cmdlet의 *SpamZapEnabled* 매개 변수를 사용 하 여 스팸 ZAP을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-146">You can disable Spam ZAP by using the *SpamZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

> <span data-ttu-id="6b4b6-147">**[참고]** 피싱 및 스팸 ZAP을 모두 제어 하는 이전 *ZapEnabled* cmdlet 매개 변수는 **사용 되지 않으며, 2020 년 2 월 1**일입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-147">**[NOTE]** the previous *ZapEnabled* cmdlet parameter which controlled both Phish and Spam ZAP will be **deprecated February 1, 2020**.</span></span> <span data-ttu-id="6b4b6-148">ZapEnabled 매개 변수를 사용 하는 스크립트를 작성 한 경우이를 SpamZapEnabled 및 PhishZapEnabled를 사용 하도록 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-148">If you have written any scripts which use the ZapEnabled parameter, we recommend updating them to use SpamZapEnabled and PhishZapEnabled.</span></span> <span data-ttu-id="6b4b6-149">전환 기간에는 cmdlet을 통해 모든 3 개의 매개 변수 (ZapEnabled, PhishZapEnabled 및 SpamZapEnabled)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-149">In the transitional period all 3 parameters (ZapEnabled, PhishZapEnabled, and SpamZapEnabled) will be available through the cmdlet.</span></span> <span data-ttu-id="6b4b6-150">UI 또는 PowerShell을 통해 명시적으로 설정 하기 전에는 PhishZapEnabled 및 SpamZapEnabled에 ZapEnabled 매개 변수의 상속 된 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-150">Until explicitly set via UI or PowerShell, PhishZapEnabled and SpamZapEnabled will show an inherited value from the ZapEnabled parameter.</span></span> <span data-ttu-id="6b4b6-151">새 매개 변수를 설정한 후에는 ZapEnabled 매개 변수에서 더 이상 상속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-151">Once the new parameters are set, they will no longer inherit from the ZapEnabled parameter.</span></span> <span data-ttu-id="6b4b6-152">이 기능을 사용 하지 않으면 ZapEnabled 설정이 PhishZapEnabled 또는 SpamZapEnabled 속성에 영향을 주지 않으며 ZapEnabled가 cmdlet의 매개 변수 목록에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-152">After it is deprecated, setting ZapEnabled will have no affect on the PhishZapEnabled or SpamZapEnabled properties and ZapEnabled will be removed from the list of parameters in cmdlets.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="6b4b6-153">메시지가 ZAP에서 이동 된 것을 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="6b4b6-153">How to see if ZAP moved your message</span></span>

<span data-ttu-id="6b4b6-154">ZAP이 메시지를 이동 했는지 확인 하려면 [위협 방지 상태 보고서](../../compliance/view-email-security-reports.md#threat-protection-status-report) 또는 [위협 탐색기 (및 실시간 검색)](threat-explorer.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-154">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](../../compliance/view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="6b4b6-155">ZAP 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6b4b6-155">Disable ZAP</span></span>

<span data-ttu-id="6b4b6-156">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-156">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="6b4b6-157">Exchange Online Protection PowerShell에 연결 하려면 [Exchange Online Protection powershell에 연결](https://go.microsoft.com/fwlink/p/?linkid=627290)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-157">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="6b4b6-158">맬웨어 ZAP 사용 안 함 \* \*</span><span class="sxs-lookup"><span data-stu-id="6b4b6-158">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="6b4b6-159">이 예에서는 "Test" 라는 맬웨어 필터 정책에서 ZAP을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-159">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="6b4b6-160">구문 및 매개 변수에 대 한 자세한 내용은 [get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-160">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="6b4b6-161">피싱 ZAP 및 스팸 ZAP 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6b4b6-161">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="6b4b6-162">O365 테 넌 트에 대 한 피싱 및 스팸 ZAP을 사용 하지 않도록 설정 하거나, 사용자 집합 [을 설정 하려면](https://go.microsoft.com/fwlink/p/?LinkId=722758)EOP cmdlet *PhishZapEnabled* 및 *SpamZapEnabled* 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-162">To disable Phish and Spam ZAP for your O365 tenant, or a set of users, use the *PhishZapEnabled* and *SpamZapEnabled* parameters of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>

<span data-ttu-id="6b4b6-163">다음 예제에서는 "Test" 라는 콘텐츠 필터 정책에 대해 피싱 및 스팸 ZAP을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-163">In the following example, phish and spam ZAP are disabled for a content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

<span data-ttu-id="6b4b6-164">구문 및 매개 변수에 대 한 자세한 내용은 [get-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-164">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="6b4b6-165">FAQ</span><span class="sxs-lookup"><span data-stu-id="6b4b6-165">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="6b4b6-166">합법적인 메시지를 정크 메일 폴더로 이동 하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="6b4b6-166">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="6b4b6-167">[가양성](../../compliance/prevent-email-from-being-marked-as-spam.md)에 대 한 일반 보고 프로세스를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-167">You should follow the normal reporting process for [false-positives](../../compliance/prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="6b4b6-168">메시지를 받은 편지함에서 정크 메일 폴더로 이동 하는 유일한 이유는 서비스가 스팸 또는 악성 메시지를 받는 것으로 확인 되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-168">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="6b4b6-169">정크 메일 폴더 대신 Office 365 검역을 사용 하는 경우에는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b4b6-169">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="6b4b6-170">지금은 메시지를 받은 편지함에서 격리로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-170">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="6b4b6-171">사용자 지정 메일 흐름 규칙 (차단/허용 규칙)이 있는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="6b4b6-171">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="6b4b6-172">관리자가 만든 규칙 (메일 흐름 규칙) 또는 차단 및 허용 규칙을 우선적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-172">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="6b4b6-173">이러한 메시지는 기능 조건에서 제외 되므로 메일 흐름은 규칙 동작 (차단/허용 규칙)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-173">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="6b4b6-174">다른 폴더 (예: 받은 편지함 규칙)로 메시지를 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="6b4b6-174">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="6b4b6-175">메시지가 삭제 되었거나 정크 상태인 경우가 아니면이 경우에도 ZAP이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4b6-175">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b4b6-176">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6b4b6-176">Related Topics</span></span>

[<span data-ttu-id="6b4b6-177">Office 365 이메일 스팸 방지 보호</span><span class="sxs-lookup"><span data-stu-id="6b4b6-177">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="6b4b6-178">Office 365 스팸 필터로 전자 메일 스팸을 차단하여 거짓 부정 문제 방지</span><span class="sxs-lookup"><span data-stu-id="6b4b6-178">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
