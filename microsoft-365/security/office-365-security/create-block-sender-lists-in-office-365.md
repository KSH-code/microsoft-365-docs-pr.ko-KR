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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 관리자는 EOP(Exchange Online Protection)에서 인바운드 메시지를 차단하는 사용 가능한 옵션 및 기본 설정 옵션을 알고 있을 수 있습니다.
ms.openlocfilehash: 9b676f96ccdff8be1fa49841a9e0ce44bb59964c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827316"
---
# <a name="create-blocked-sender-lists-in-eop"></a><span data-ttu-id="b6b00-103">EOP에서 차단된 보낸 사람 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="b6b00-103">Create blocked sender lists in EOP</span></span>

<span data-ttu-id="b6b00-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 관계없는 보낸 사람으로부터 전자 메일을 차단하는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="b6b00-105">이러한 옵션에는 Outlook 수신 거부, 수신 거부 목록 또는 차단된 도메인 목록이 스팸 방지 정책의 목록, Exchange 메일 흐름 규칙(전송 규칙이라고도 함) 및 IP 차단 목록(연결 필터링)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-105">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="b6b00-106">이러한 옵션은 집합적으로 차단된 보낸 사람 _목록으로 간주할 수 있습니다._</span><span class="sxs-lookup"><span data-stu-id="b6b00-106">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="b6b00-107">보낸 사람을 차단하는 가장 좋은 방법은 영향 범위에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-107">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="b6b00-108">단일 사용자의 경우 올바른 솔루션은 Outlook 수신 거부일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-108">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="b6b00-109">많은 사용자의 경우 다른 옵션 중 하나가 더 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-109">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="b6b00-110">다음 옵션은 영향 범위와 설명을 모두 통해 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-110">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="b6b00-111">목록은 좁은 범위에서 광범위하지만, *전체 권장 사항에 대한 자세한* 사항을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-111">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="b6b00-112">Outlook 수신 거부(각 사서함에 저장되어 있는 수신 거부 목록)</span><span class="sxs-lookup"><span data-stu-id="b6b00-112">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="b6b00-113">수신 거부 목록 또는 차단된 도메인 목록(스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="b6b00-113">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="b6b00-114">메일 흐름 규칙</span><span class="sxs-lookup"><span data-stu-id="b6b00-114">Mail flow rules</span></span>

4. <span data-ttu-id="b6b00-115">IP 차단 목록(연결 필터링)</span><span class="sxs-lookup"><span data-stu-id="b6b00-115">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="b6b00-116">조직 전체의 블록 설정을 사용하여 거짓 부정(스팸 부정)을 처리할 수 있고, 분석을 위해 Microsoft에 해당 메시지를 전송해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-116">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="b6b00-117">차단 목록을 사용하여 가양성을 관리하면 관리 오버헤드가 크게 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-117">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="b6b00-118">차단 목록을 사용하여 누락된 스팸을 조사할 경우 항목을 [Microsoft에](report-junk-email-messages-to-microsoft.md) 보고하는 것이 준비되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-118">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="b6b00-119">이와 비해 수신 허용 - 보낸 사람 목록을 사용하여 특정 소스에서 보내는 전자 메일을 항상 허용하는 몇 _가지 옵션도 있습니다._</span><span class="sxs-lookup"><span data-stu-id="b6b00-119">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="b6b00-120">자세한 내용은 [수신 허용 - 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6b00-120">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="email-message-basics"></a><span data-ttu-id="b6b00-121">전자 메일 메시지 기본 사항</span><span class="sxs-lookup"><span data-stu-id="b6b00-121">Email message basics</span></span>

<span data-ttu-id="b6b00-122">표준 SMTP 전자 메일 메시지는 메시지 *봉투와 메시지 내용으로* 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-122">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="b6b00-123">메시지 봉투에는 SMTP 서버 간에 메시지를 전송 및 배달하는 데 필요한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-123">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="b6b00-124">메시지 내용에는 메시지 헤더 필드(사서함 헤더) 및 *메시지 본문이*들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-124">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="b6b00-125">메시지 봉투는 RFC 5321에 설명되어 있고 메시지 헤더는 RFC 5322에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-125">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="b6b00-126">메시지 봉투는 메시지 전송 프로세스에 의해 생성되며 실제로는 메시지의 일부가 아닌 실제 메시지 봉투를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-126">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="b6b00-127">이 `5321.MailFrom` **주소(메일 보낸 사람** 주소, P1 보낸 사람 또는 봉투 보낸 사람이라고도 함)는 메시지의 SMTP 전송에 사용되는 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-127">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="b6b00-128">이 전자 메일 주소는 일반적으로 메시지 헤더의 **Return-Path** 헤더 필드에 기록됩니다(보낸 사람이 서로 다른 반기 전자 메일 **주소를 지정할 수는** 있습니다).</span><span class="sxs-lookup"><span data-stu-id="b6b00-128">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="b6b00-129">메시지를 배달할 수 없는 경우 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)를 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-129">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="b6b00-130">보낸 `5322.From` 사람 주소 또는 P2 **보낸** 사람이라고도 하는 보낸 사람 주소는 **보낸** 사람 헤더 필드의 전자 메일 주소이며, 전자 메일 클라이언트에 표시되는 보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-130">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="b6b00-131">대칭적으로, `5321.MailFrom` 주소가 `5322.From` 동일합니다(개인 간 통신).</span><span class="sxs-lookup"><span data-stu-id="b6b00-131">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="b6b00-132">그러나 다른 사용자를 대신하여 전자 메일을 보낼 때는 해당 주소가 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-132">However, when email is sent on behalf of someone else, the addresses can be different.</span></span>

<span data-ttu-id="b6b00-133">EOP에서 스팸 방지 정책의 수신 거부 목록과 차단된 도메인 목록이 모두 및 주소를 `5321.MailFrom` `5322.From` 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-133">Blocked sender lists and blocked domain lists in anti-spam policies in EOP inspect both the `5321.MailFrom` and `5322.From` addresses.</span></span> <span data-ttu-id="b6b00-134">Outlook 수신 거부는 주소만 `5322.From` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-134">Outlook Blocked Senders only uses the `5322.From` address.</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="b6b00-135">Outlook 수신 거부 사용</span><span class="sxs-lookup"><span data-stu-id="b6b00-135">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="b6b00-136">소수의 사용자만 사용자의 일본에서 사용자의 사서함을 수신하는 경우 사용자나 관리자는 사서함의 수신 거부 목록에 보낸 사람 전자 메일 주소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-136">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="b6b00-137">자세한 내용은 [Exchange Online 사서함에 대해 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="b6b00-137">For instructions, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="b6b00-138">사용자의 수신 거부 목록으로 인해 메시지가 성공적으로 차단된 경우 **X-Forefront-Antispam-Report 헤더** 필드에는 이 값이 포함됩니다. `SFV:BLK`</span><span class="sxs-lookup"><span data-stu-id="b6b00-138">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="b6b00-139">필요하지 않은 메시지가 평질이 있고 인식 가능한 원본의 뉴스레터인 경우 사용자가 메시지를 받지 못하도록 하는 추가 옵션이 전자 메일에서 구독 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-139">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="b6b00-140">차단할 보낸 사람 목록 또는 차단할 도메인 목록 사용</span><span class="sxs-lookup"><span data-stu-id="b6b00-140">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="b6b00-141">여러 사용자에게 영향을 받는 경우 스팸 방지 정책에서 그 다음 최상의 방법으로 보낸 사람 목록 또는 차단된 도메인 목록이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-141">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="b6b00-142">목록에 있는 보낸 사람이 보낸 메시지는 **스팸으로**표시되며, 메시지에서 **Spam** 사용자가 구성한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-142">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="b6b00-143">자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6b00-143">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="b6b00-144">이러한 목록에 대한 최대 제한은 약 1000개 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-144">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="b6b00-145">메일 흐름 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="b6b00-145">Use mail flow rules</span></span>

<span data-ttu-id="b6b00-146">특정 사용자에게 보내지거나 전체 조직에서 전송되는 메시지를 차단해야 하는 경우 메일 흐름 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-146">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="b6b00-147">메일 흐름 규칙은 원치 않는 메시지에서 키워드 또는 기타 속성을 찾을 수 있기 때문에 보낸 사람 목록 또는 수신 거부 도메인 목록보다 훨씬 더 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-147">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="b6b00-148">메시지를 식별하는 데 사용하는 조건이나 예외에 관계없이 메시지의 SCL(스팸 지수)을 9로 설정하도록 작업을 구성하여 메시지의 **신뢰도를 높게 표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6b00-148">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="b6b00-149">자세한 내용은 메일 흐름 [규칙을 사용하여 SCL 설정을 메시지에 시행합니다.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="b6b00-149">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6b00-150">과도하게 액세스하는 규칙을 *만들기가* 매우 어우중요하므로 매우 구체적인 조건을 사용하여 차단할 메시지만 식별하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-150">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="b6b00-151">또한 규칙에 대한 감사를 사용하도록 설정하고 규칙 결과를 테스트하여 모든 작업이 예상대로 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-151">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="b6b00-152">IP 차단 목록 사용</span><span class="sxs-lookup"><span data-stu-id="b6b00-152">Use the IP Block List</span></span>

<span data-ttu-id="b6b00-153">다른 옵션 중 하나를 사용하여 보낸 사람을 차단할 수 없는 *경우에는 연결* 필터 정책에서 IP 차단 목록만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-153">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="b6b00-154">자세한 내용은 [Configure the connection filter policy](configure-the-connection-filter-policy.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6b00-154">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="b6b00-155">차단된 IP 의 개수를 최소한으로 유지해야 하므로 전체 IP 주소 범위를 차단하지 않는 *것이* 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-155">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="b6b00-156">사용자 서비스에 *속한* IP 주소 범위(예: outlook.com) 또는 공유 인프라를 추가하는 일이 원치 않는 한 주의해야 하며, 일반 유지 관리의 일부로 차단된 IP 주소 목록을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b00-156">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
