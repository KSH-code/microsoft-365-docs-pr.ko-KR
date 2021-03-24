---
title: 차단할 보낸 사람 목록 만들기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
description: 관리자는 EOP(Exchange Online Protection)에서 인바운드 메시지를 차단하는 사용 가능한 옵션 및 기본 옵션에 대해 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a9ee0a026e33bf07bb929607b8eed9078d0b6e4c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073359"
---
# <a name="create-blocked-sender-lists-in-eop"></a><span data-ttu-id="9056b-103">EOP에서 차단된 보낸 사람 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="9056b-103">Create blocked sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9056b-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="9056b-104">**Applies to**</span></span>
- [<span data-ttu-id="9056b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9056b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9056b-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="9056b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9056b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9056b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9056b-108">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 원치 않는 보낸 사람으로부터 전자 메일을 차단하는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="9056b-109">이러한 옵션에는 Outlook 차단된 보낸 사람, 스팸 방지 정책의 차단된 보낸 사람 목록 또는 차단된 도메인 목록, Exchange 메일 흐름 규칙(전송 규칙) 및 IP 차단 목록(연결 필터링)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-109">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="9056b-110">전체적으로 이러한 옵션을 수신 차단된 보낸 사람 _목록으로 생각할 수 있습니다._</span><span class="sxs-lookup"><span data-stu-id="9056b-110">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="9056b-111">보낸 사람 차단의 가장 좋은 방법은 영향 범위에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-111">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="9056b-112">단일 사용자의 경우 Outlook 수신이 차단된 보낸 사람일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-112">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="9056b-113">많은 사용자의 경우 다른 옵션 중 하나에 더 적합한 옵션 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-113">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="9056b-114">다음 옵션은 영향 범위와 범위 모두에 따라 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-114">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="9056b-115">목록은 좁아지지만 전체 권장 사항에 대한 *자세한* 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-115">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="9056b-116">Outlook 수신이 차단된 보낸 사람(각 사서함에 저장된 수신 차단된 보낸 사람 목록)</span><span class="sxs-lookup"><span data-stu-id="9056b-116">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="9056b-117">차단된 보낸 사람 목록 또는 차단된 도메인 목록(스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="9056b-117">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="9056b-118">메일 흐름 규칙</span><span class="sxs-lookup"><span data-stu-id="9056b-118">Mail flow rules</span></span>

4. <span data-ttu-id="9056b-119">IP 차단 목록(연결 필터링)</span><span class="sxs-lookup"><span data-stu-id="9056b-119">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="9056b-120">조직 전체 차단 설정을 사용하여 거짓 부정(스팸 누락)을 해결할 수 있는 반면, 분석을 위해 해당 메시지를 Microsoft에 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-120">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="9056b-121">차단 목록을 사용하여 거짓 부정을 관리하면 관리 오버헤드가 크게 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-121">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="9056b-122">차단 목록을 사용하여 누락된 스팸을 반사하는 경우 [Report messages and files to Microsoft(Microsoft에](report-junk-email-messages-to-microsoft.md) 메시지 및 파일 보고) 항목을 준비된 상태로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-122">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="9056b-123">반면에 수신 허용 - 보낸 사람 목록을 사용하여 특정 원본의 전자 메일을 항상 허용하는 몇 가지 _옵션도 있습니다._</span><span class="sxs-lookup"><span data-stu-id="9056b-123">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="9056b-124">자세한 내용은 [수신 허용 - 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9056b-124">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="email-message-basics"></a><span data-ttu-id="9056b-125">전자 메일 메시지 기본</span><span class="sxs-lookup"><span data-stu-id="9056b-125">Email message basics</span></span>

<span data-ttu-id="9056b-126">표준 SMTP 전자 메일 메시지는 메시지 봉투와 메시지 콘텐츠로 구성됩니다. </span><span class="sxs-lookup"><span data-stu-id="9056b-126">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="9056b-127">메시지 봉투에는 SMTP 서버 간에 메시지를 전송하고 배달하는 데 필요한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-127">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="9056b-128">메시지 콘텐츠에는 메시지 헤더 필드(총체적으로 메시지 *헤더)와* 메시지 본문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-128">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="9056b-129">메시지 봉투는 RFC 5321에 설명되어 있으며 메시지 헤더는 RFC 5322에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-129">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="9056b-130">받는 사람은 메시지 전송 프로세스에 의해 생성되어 실제로 메시지의 일부가 아니기 때문에 실제 메시지 봉투를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-130">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="9056b-131">주소(MAIL FROM 주소, P1 보낸 사람 또는 봉투 보낸 사람)는 메시지의 SMTP 전송에 사용되는 전자 메일 `5321.MailFrom` 주소입니다. </span><span class="sxs-lookup"><span data-stu-id="9056b-131">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="9056b-132">이 전자 메일 주소는 일반적으로 메시지 헤더의 **반환 경로** 헤더 필드에 기록됩니다(보낸 사람이 다른  반환 경로 전자 메일 주소를 지정하는 것은 가능).</span><span class="sxs-lookup"><span data-stu-id="9056b-132">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="9056b-133">메시지를 배달할 수 없는 경우 배달 못 한 보고서(NDR 또는 반송 메시지라고도 알려)의 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-133">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="9056b-134">보낸 사람(보낸 사람 주소 또는 P2 보낸 사람)은 보낸 사람 헤더 필드의 전자 메일 주소로, 전자 메일 클라이언트에 표시되는 보낸 사람 전자 메일 `5322.From` 주소입니다.  </span><span class="sxs-lookup"><span data-stu-id="9056b-134">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="9056b-135">자주 및 `5321.MailFrom` `5322.From` 주소는 동일합니다(개인 간 통신).</span><span class="sxs-lookup"><span data-stu-id="9056b-135">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="9056b-136">그러나 다른 사람을 대신하여 전자 메일을 보낼 경우 주소가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-136">However, when email is sent on behalf of someone else, the addresses can be different.</span></span>

<span data-ttu-id="9056b-137">EOP의 스팸 방지 정책에서 차단된 보낸 사람 목록 및 차단된 도메인 목록은 및 주소를 `5321.MailFrom` 모두 `5322.From` 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-137">Blocked sender lists and blocked domain lists in anti-spam policies in EOP inspect both the `5321.MailFrom` and `5322.From` addresses.</span></span> <span data-ttu-id="9056b-138">Outlook 수신이 차단된 보낸 사람만 `5322.From` 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-138">Outlook Blocked Senders only uses the `5322.From` address.</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="9056b-139">Outlook 수신이 차단된 보낸 사람 사용</span><span class="sxs-lookup"><span data-stu-id="9056b-139">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="9056b-140">소수의 사용자만 원치 않는 전자 메일을 받은 경우 사용자 또는 관리자는 사서함의 수신 차단된 보낸 사람 목록에 보낸 사람 전자 메일 주소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-140">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="9056b-141">자세한 내용은 Exchange Online 사서함에 대한 정크 메일 [설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="9056b-141">For instructions, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="9056b-142">사용자의 수신이 차단된 보낸 사람 목록으로 인해 메시지가 차단된 경우 **X-Forefront-Antispam-Report** 헤더 필드에는 값이 를 포함하게 `SFV:BLK` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-142">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="9056b-143">원치 않는 메시지가 수신 가능하고 인식할 수 있는 원본의 뉴스레터인 경우 사용자가 메시지를 받지 못하도록 하는 또 다른 옵션으로 전자 메일 구독을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-143">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="9056b-144">차단된 보낸 사람 목록 또는 차단된 도메인 목록 사용</span><span class="sxs-lookup"><span data-stu-id="9056b-144">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="9056b-145">여러 사용자가 영향을 받는 경우 범위가 더 넓어지기 때문에 다음으로는 스팸 방지 정책의 차단된 보낸 사람 목록 또는 차단된 도메인 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-145">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="9056b-146">목록의 보낸 사람이 보낸 메시지는 스팸으로 표시되어 있으며 스팸 필터 판정에 대해 구성한 작업이 메시지에 대해 수행됩니다. </span><span class="sxs-lookup"><span data-stu-id="9056b-146">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="9056b-147">자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9056b-147">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="9056b-148">이러한 목록의 최대 제한은 약 1,000개 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-148">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="9056b-149">메일 흐름 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="9056b-149">Use mail flow rules</span></span>

<span data-ttu-id="9056b-150">특정 사용자 또는 전체 조직에 전송된 메시지를 차단해야 하는 경우 메일 흐름 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-150">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="9056b-151">메일 흐름 규칙은 원치 않는 메시지에서 키워드 또는 기타 속성을 검색할 수 있기 때문에 보낸 사람 목록 또는 차단된 보낸 사람 도메인 목록을 차단하는 것보다 더 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-151">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="9056b-152">메시지를 식별하는 데 사용하는 조건 또는 예외에 관계없이 메시지의 SCL(스팸 지수)을 9로 설정하여 메시지를 높은 지수 스팸으로 표시하도록 작업을 **구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="9056b-152">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="9056b-153">자세한 내용은 메일 흐름 규칙을 사용하여 [메시지에서 SCL 설정을 참조하세요.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="9056b-153">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9056b-154">너무 적극적인 규칙을 쉽게  만들 수 있으므로 매우 구체적인 조건을 사용하여 차단하려는 메시지만 식별하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-154">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="9056b-155">또한 규칙에 대한 감사를 사용하도록 설정하고 규칙 결과를 테스트하여 모든 것이 예상대로 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-155">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="9056b-156">IP 차단 목록 사용</span><span class="sxs-lookup"><span data-stu-id="9056b-156">Use the IP Block List</span></span>

<span data-ttu-id="9056b-157">다른 옵션 중 하나를 사용하여 보낸 사람 차단을 사용할  수 없는 경우 연결 필터 정책에서 IP 차단 목록을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-157">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="9056b-158">자세한 내용은 [Configure the connection filter policy](configure-the-connection-filter-policy.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9056b-158">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="9056b-159">차단된 IP 수를 최소한으로 유지하는 것이 중요하기 때문에 전체 IP 주소 범위를 차단하지 않는 것이 *좋습니다.*</span><span class="sxs-lookup"><span data-stu-id="9056b-159">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="9056b-160">특히 *소비자* 서비스(예: outlook.com) 또는 공유 인프라에 속하는 IP 주소 범위를 추가하지 말고 정기적인 유지 관리의 일부로 차단된 IP 주소 목록을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9056b-160">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
