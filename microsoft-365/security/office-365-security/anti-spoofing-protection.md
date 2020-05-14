---
title: 스푸핑 방지 보호 기능
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
description: 관리자는 스푸핑된 보낸 사람 및 도메인의 피싱 공격을 완화하는 데 도움이 되며 EOP(Exchange Online Protection)에서 사용할 수 있는 스푸핑 방지 기능에 대해 알아볼 수 있습니다.
ms.openlocfilehash: c28f5cf18a8da3be06906eb1e6b118c856c40066
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209034"
---
# <a name="anti-spoofing-protection-in-eop"></a><span data-ttu-id="b29da-103">EOP의 스푸핑 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="b29da-103">Anti-spoofing protection in EOP</span></span>

<span data-ttu-id="b29da-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 경우, EOP에 가짜(위조) 발신인으로부터 조직을 보호하는 데 도움이 되는 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP includes features to help protect your organization from spoofed (forged) senders.</span></span>

<span data-ttu-id="b29da-105">사용자 보호와 관련해 Microsoft는 피싱 위협을 심각한 위험으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-105">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="b29da-106">스푸핑은 공격자가 흔히 사용하는 기술로</span><span class="sxs-lookup"><span data-stu-id="b29da-106">Spoofing is a common technique that's used by attackers.</span></span> <span data-ttu-id="b29da-107">**스푸핑된 메시지가 실제 출처가 아닌 다른 사람이나 다른 곳에서 시작된 것처럼 보입니다**.</span><span class="sxs-lookup"><span data-stu-id="b29da-107">**Spoofed messages appear to originate from someone or somewhere other than the actual source**.</span></span> <span data-ttu-id="b29da-108">이 기법은 사용자 자격 증명을 얻기 위해 고안된 피싱 캠페인에서 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-108">This technique is often used in phishing campaigns that are designed to obtain user credentials.</span></span> <span data-ttu-id="b29da-109">EOP의 스푸핑 방지 기술은 특히 메시지 본문에서 보낸 사람 머리글의 위조를 검사합니다(전자 메일 클라이언트에서 메시지 보낸 사람을 표시하는 데 사용됨).</span><span class="sxs-lookup"><span data-stu-id="b29da-109">The anti-spoofing technology in EOP specifically examines forgery of the From header in the message body (used to display the message sender in email clients).</span></span> <span data-ttu-id="b29da-110">EOP에서 보낸 사람 머리글이 위조되었다는 강한 확신이 있는 경우 메시지는 가짜로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-110">When EOP has high confidence that the From header is forged, the message is identified as spoofed.</span></span>

<span data-ttu-id="b29da-111">EOP에서 다음 스푸핑 방지 기술을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-111">The following anti-spoofing technologies are available in EOP:</span></span>

- <span data-ttu-id="b29da-112">**스푸핑 인텔리전스**: 내부 및 외부 도메인의 보낸 사람으로부터 스푸핑된 메시지를 검토하고 해당 보낸 사람을 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-112">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="b29da-113">자세한 내용은 [Microsoft 365에 스푸핑 인텔리전스 구성](learn-about-spoof-intelligence.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-113">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="b29da-114">**피싱 방지 정책**: EOP에서 피싱 방지 정책을 사용하면 스푸핑 인텔리전스를 설정 또는 해제하고, Outlook의 인증되지 않은 발신자 신원 확인을 설정 또는 해제하며, 차단된 스푸핑된 발신자(정크 메일 폴더 또는 격리로 이동)에 대한 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-114">**Anti-phishing policies**: In EOP, anti-phishing policies allow you to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to the Junk Email folder or quarantine).</span></span> <span data-ttu-id="b29da-115">Office 365 ATP(Advanced Threat Protection)에서 제공하는 고급 피싱 방지 정책에는 가장 방지 설정(보호된 발신자 및 도메인), 사서함 인텔리전스 설정 및 조정 가능한 고급 피싱 임계값 또한 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-115">Advanced anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP) also contain anti-impersonation settings (protected senders and domains), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="b29da-116">자세한 내용은 [Microsoft 365의 피싱 방지 정책](set-up-anti-phishing-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-116">For more information, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="b29da-117">**전자 메일 인증**: 모든 스푸핑 방지 작업의 필수 요소는 SPF, DKIM 및 DNS의 DMARC 레코드에서 전자 메일 인증(다른 말로 전자 메일 유효성 검사라고 함)을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-117">**Email authentication**: An integral part of any anti-spoofing effort is the use of email authentication (also known as email validation) by SPF, DKIM, and DMARC records in DNS.</span></span> <span data-ttu-id="b29da-118">대상 전자 메일 시스템에서 도메인에 속한 발신자로부터 시작되었다고 주장하는 메시지의 유효성을 검사할 수 있도록 도메인에 대해 이러한 레코드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-118">You can configure these records for your domains so destination email systems can check the validity of messages that claim to be from senders in your domains.</span></span> <span data-ttu-id="b29da-119">인바운드 메시지의 경우 Microsoft 365를 사용하려면 발신자 도메인에 대한 전자 메일 인증을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-119">For inbound messages, Microsoft 365 requires email authentication for sender domains.</span></span> <span data-ttu-id="b29da-120">자세한 내용은 [Microsoft 365의 전자 메일 인증](email-validation-and-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-120">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

<span data-ttu-id="b29da-121">2018년 10월부터 EOP에서 스푸핑 방지 보호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-121">As of October 2018, anti-spoofing protection is available in EOP.</span></span> <span data-ttu-id="b29da-122">그때까지는, Office 365 ATP가 있는 조직만 스푸핑 방지 보호 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-122">Before then, anti-spoofing protection was only available in organizatons with Office 365 ATP.</span></span>

<span data-ttu-id="b29da-123">EOP는 표준 전자 메일 인증 방법과 보낸 사람 신뢰도 기술을 조합하여 인증하지 못하는 메시지를 분석 및 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-123">EOP analyzes and blocks messages that can't be authenticated by the combination of standard email authentication methods and sender reputation techniques.</span></span>

![EOP 스푸핑 방지 검사](../../media/eop-anti-spoofing-protection.png)

## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="b29da-125">피싱 공격에서 스푸핑을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="b29da-125">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="b29da-126">스푸핑 메시지는 사용자에게 다음과 같은 부정적인 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-126">Spoofing messages have the following negative implications for users:</span></span>

- <span data-ttu-id="b29da-127">**스푸핑된 메시지가 사용자 속이기**: 스푸핑된 메시지는 수신인으로 하여금 링크를 클릭하고 자격 증명을 포기하거나 맬웨어를 다운로드하거나 민감한 콘텐츠가 있는 메시지에 회신하도록 속일 수 있습니다(비즈니스 전자 메일 손상 또는 BEC라고 함).</span><span class="sxs-lookup"><span data-stu-id="b29da-127">**Spoofed messages deceive users**: A spoofed message might trick the recipient into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (known as a business email compromise or BEC).</span></span>

  <span data-ttu-id="b29da-128">다음 메시지는 스푸핑된 발신자 msoutlook94@service.outlook.com을 사용하는 피싱의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-128">The following message is an example of phishing that uses the spoofed sender msoutlook94@service.outlook.com:</span></span>

  ![ervice.outlook.com으로 위장한 피싱 메일](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  <span data-ttu-id="b29da-130">이 메일은 service.outlook.com에서 발송되지 않았지만 공격자는 발송된 것처럼 보이도록 **보낸 사람** 머리글 필드를 도용했습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-130">This message didn't come from service.outlook.com, but the attacker spoofed the **From** header field to make it look like it did.</span></span> <span data-ttu-id="b29da-131">즉 받는 사람이 **암호 변경** 링크를 클릭하고 자격 증명을 넘기도록 속이려고 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-131">This was an attempt to trick the recipient into clicking the **change your password** link and giving up their credentials.</span></span>

  <span data-ttu-id="b29da-132">다음 메일은 도용 당한 전자 메일 도메인 contoso.com을 사용한 BEC의 한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-132">The following message is an example of BEC that uses the spoofed email domain contoso.com:</span></span>

  ![피싱 메일 - 비즈니스 전자 메일 손상](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  <span data-ttu-id="b29da-134">메일이 적법한 것처럼 보이지만 발신자 스푸핑에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-134">The message looks legitimate, but the sender is spoofed.</span></span>

- <span data-ttu-id="b29da-135">**사용자가 진짜 메일을 가짜로 혼동**: 피싱에 대해 아는 사용자라도 실제 메일과 스푸핑된 메일 간의 차이를 알아보기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-135">**Users confuse real messages for fake ones**: Even users who know about phishing might have difficulty seeing the differences between real messages and spoofed messages.</span></span>

  <span data-ttu-id="b29da-136">다음 메일은은 Microsoft Security 계정에서 발송된 실제 암호 재설정 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-136">The following message is an example of a real password reset message from the Microsoft Security account:</span></span>

  ![Microsoft의 합법적인 암호 재설정](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  <span data-ttu-id="b29da-138">메일은 정말로 Microsoft에서 발송되었지만 사용자는 의심하도록 훈련받았습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-138">The message really did come from Microsoft, but users have been conditioned to be suspicious.</span></span> <span data-ttu-id="b29da-139">실제 암호 재설정 메일과 가짜 메일 간의 차이점을 구별하기 어렵기 때문에 사용자는 이러한 메일을 무시하거나, 스팸으로 신고하거나, 아니면 쓸데없이 피싱 메일로 Microsoft에 신고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-139">Because it's difficult to the difference between a real password reset message and a fake one, users might ignore the message, report it as spam, or unnecessarily report the message to Microsoft as phishing.</span></span>

## <a name="different-types-of-spoofing"></a><span data-ttu-id="b29da-140">다양한 스푸핑 유형</span><span class="sxs-lookup"><span data-stu-id="b29da-140">Different types of spoofing</span></span>

<span data-ttu-id="b29da-141">Microsoft는 서로 다른 두 가지 유형의 스푸핑 메일을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-141">Microsoft differentiates between two different types of spoofed messages:</span></span>

- <span data-ttu-id="b29da-142">**조직 내 스푸핑**: _자체_ 스푸핑으로도 알려졌습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-142">**Intra-org spoofing**: Also known as _self-to-self_ spoofing.</span></span> <span data-ttu-id="b29da-143">예시:</span><span class="sxs-lookup"><span data-stu-id="b29da-143">For example:</span></span>

  - <span data-ttu-id="b29da-144">보낸 사람과 받는 사람이 같은 도메인 소속입니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-144">The sender and recipient are in the same domain:</span></span>
    > <span data-ttu-id="b29da-145">보낸 사람: jihoo@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b29da-145">From: chris@contoso.com</span></span> <br/> <span data-ttu-id="b29da-146">To: michelle@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b29da-146">To: michelle@contoso.com</span></span>

  - <span data-ttu-id="b29da-147">보낸 사람과 받는 사람이 같은 도메인의 하위 도메인 소속입니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-147">The sender and the recipient are in subdomains of the same domain:</span></span>
    > <span data-ttu-id="b29da-148">보낸 사람: laura@marketing.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b29da-148">From: laura@marketing.fabrikam.com</span></span> <br/> <span data-ttu-id="b29da-149">받는 사람: julia@engineering.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b29da-149">To: julia@engineering.fabrikam.com</span></span>

  - <span data-ttu-id="b29da-150">보낸 사람과 받는 사람이 동일한 조직에 속하는 다른 도메인 소속입니다(즉, 동일한 조직에서 두 도메인이 모두 [허용 도메인](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)으로 구성되어 있음).</span><span class="sxs-lookup"><span data-stu-id="b29da-150">The sender and recipient are in different domains that belong to the same organization (that is, both domains are configured as [accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the same organization):</span></span>
    > <span data-ttu-id="b29da-151">발신자: 보낸 사람@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b29da-151">From: sender @ microsoft.com</span></span> <br/> <span data-ttu-id="b29da-152">수신자: 받는 사람@bing.com</span><span class="sxs-lookup"><span data-stu-id="b29da-152">To: recipient @ bing.com</span></span>

    <span data-ttu-id="b29da-153">스팸봇 수확을 방지하고자 전자 메일 주소에서 공백이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-153">Spaces are used in the email addresses to prevent spambot harvesting.</span></span>

  <span data-ttu-id="b29da-154">조직 내 스푸핑으로 인해 [복합 인증](email-validation-and-authentication.md#composite-authentication)에 실패하는 메일에는 다음 머리글 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-154">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to intra-org spoofing contain the following header values:</span></span>

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - <span data-ttu-id="b29da-155">`reason=6xx`은(는) 조직 내 스푸핑임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-155">`reason=6xx` indicates intra-org spoofing.</span></span>

  - <span data-ttu-id="b29da-156">SFTY는 메일의 보안 수준을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-156">SFTY is the safety level of the message.</span></span> <span data-ttu-id="b29da-157">9는 피싱, 11은 조직 내 스푸핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-157">9 indicates phishing, .11 indicates intra-org spoofing.</span></span>

- <span data-ttu-id="b29da-158">**도메인 간 스푸핑**: 보낸 사람과 받는 사람 도메인이 다르고 서로 아무 관계가 없습니다(또는 외부 도메인).</span><span class="sxs-lookup"><span data-stu-id="b29da-158">**Cross-domain spoofing**: The sender and recipient domains are different, and have no relationship to each other (also known as external domains).</span></span> <span data-ttu-id="b29da-159">예시:</span><span class="sxs-lookup"><span data-stu-id="b29da-159">For example:</span></span>
    > <span data-ttu-id="b29da-160">보낸 사람: jihoo@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b29da-160">From: chris@contoso.com</span></span> <br/> <span data-ttu-id="b29da-161">받는 사람: michelle@tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="b29da-161">To: michelle@tailspintoys.com</span></span>

  <span data-ttu-id="b29da-162">도메인 간 스푸핑으로 인해 [복합 인증](email-validation-and-authentication.md#composite-authentication)에 실패하는 메일에는 다음 머리글 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-162">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to cross-domain spoofing contain the following headers values:</span></span>

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - <span data-ttu-id="b29da-163">`reason=000`은(는) 메일이 명시적 전자 메일 인증에 실패했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-163">`reason=000` indicates the message failed explicit email authentication.</span></span> <span data-ttu-id="b29da-164">`reason=001`은(는) 메일이 암묵적인 전자 메일 인증에 실패했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-164">`reason=001` indicates the message failed implicit email authentication.</span></span>

  - <span data-ttu-id="b29da-165">SFTY는 메일의 보안 수준을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-165">SFTY is the safety level of the message.</span></span> <span data-ttu-id="b29da-166">9는 피싱, .22는 도메인 간 스푸핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-166">9 indicates phishing, .22 indicates cross-domain spoofing.</span></span>

<span data-ttu-id="b29da-167">스푸핑과 관련된 범주 및 복합 인증(compauth) 값에 대한 자세한 내용은 [Microsoft 365의 스팸 방지 메시지 머리글](anti-spam-message-headers.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-167">For more information about the Category and composite authentication (compauth) values that are related to spoofing, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="b29da-168">DMARC에 대한 자세한 내용은 [Microsoft 365의 DMARC를 사용한 전자 메일 유효성 검사](use-dmarc-to-validate-email.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-168">For more information about DMARC, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="b29da-169">스푸핑으로 표시된 메일 수에 대한 보고서</span><span class="sxs-lookup"><span data-stu-id="b29da-169">Reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="b29da-170">EOP 조직은 보안 & 준수 센터의 보고서 대시보드에서 **스푸핑 감지** 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-170">EOP organizations can use the **Spoof detections** report in the reports dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="b29da-171">자세한 내용은 [스푸핑 감지 보고서](view-email-security-reports.md#spoof-detections-report)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-171">For more information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

<span data-ttu-id="b29da-172">Office 365 ATP 조직은 보안 & 준수 센터의 위협 탐색기를 사용하여 피싱 시도에 대한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-172">Office 365 ATP organization can use Threat Explorer in the Security & Compliance Center to view information about phishing attempts.</span></span> <span data-ttu-id="b29da-173">자세한 내용은 [Microsoft 365 위협 조사 및 대응](office-365-ti.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-173">For more information, see [Microsoft 365 threat investigation and response](office-365-ti.md).</span></span>

## <a name="problems-with-anti-spoofing-protection"></a><span data-ttu-id="b29da-174">스푸핑 방지 보호 관련 문제</span><span class="sxs-lookup"><span data-stu-id="b29da-174">Problems with anti-spoofing protection</span></span>

<span data-ttu-id="b29da-175">메일 그룹(또는 토록 목록)은 메일을 전달 및 수정하는 방식으로 인해 스푸핑 방지에 문제가 있는 것으로 알려졌습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-175">Mailing lists (also known as discussion lists) are known to have problems with anti-spoofing due to the way they forward and modify messages.</span></span>

<span data-ttu-id="b29da-176">예를 들어 Gabriela Laureano(glaureano@contoso.com)는 새 관찰에 관심이 있고 birdwatchers@fabrikam.com이라는 메일 그룹에 참여하여 그룹에 다음 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-176">For example, Gabriela Laureano (glaureano@contoso.com) is interested in bird watching, joins the mailing list birdwatchers@fabrikam.com, and sends the following message to the list:</span></span>

> <span data-ttu-id="b29da-177">**보낸 사람:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="b29da-177">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br/> <span data-ttu-id="b29da-178">**받는 사람:** Birdwatcher의 토론 목록 \<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="b29da-178">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br/><span data-ttu-id="b29da-179"> \
\**제목:\** 산 정상에서 바라보는 파란색 제비의 장관</span><span class="sxs-lookup"><span data-stu-id="b29da-179"> \
\**Subject:\** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="b29da-180">레이니어 이번 주</span><span class="sxs-lookup"><span data-stu-id="b29da-180">Rainier this week</span></span> <br/><br/><span data-ttu-id="b29da-181">이번 주에 레이니어 산에서 이 광경을 확인하고 싶은 </span><span class="sxs-lookup"><span data-stu-id="b29da-181">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="b29da-182">사람이 있습니까?</span><span class="sxs-lookup"><span data-stu-id="b29da-182">Rainier?</span></span>

<span data-ttu-id="b29da-183">메일 그룹 서버에서 메시지를 수신하고, 내용을 수정하며, 목록 구성원에게 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-183">The mailing list server receives the message, modifies its content, and replays it to the members of list.</span></span> <span data-ttu-id="b29da-184">재생된 메시지의 보낸 사람 주소(glaureano@contoso.com)는 같지만 제목 줄에 태그가 추가되고 메일의 맨 아래에 바닥글이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-184">The replayed message has the same From address (glaureano@contoso.com), but a tag is added to the subject line, and a footer is added to the bottom of the message.</span></span> <span data-ttu-id="b29da-185">이러한 수정 유형은 메일 그룹에서 일반적이며 스푸핑 오탐지를 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-185">This type of modification is common in mailing lists, and may result in false positives for spoofing.</span></span>

> <span data-ttu-id="b29da-186">**보낸 사람:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="b29da-186">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br/> <span data-ttu-id="b29da-187">**받는 사람:** Birdwatcher의 토론 목록 \<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="b29da-187">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br/> <span data-ttu-id="b29da-188">**제목:** [새 구경] 산 정상에서 바라보는 파란색 제비의 장관</span><span class="sxs-lookup"><span data-stu-id="b29da-188">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="b29da-189">레이니어 이번 주</span><span class="sxs-lookup"><span data-stu-id="b29da-189">Rainier this week</span></span> <br/><br/> <span data-ttu-id="b29da-190">이번 주에 레이니어 산에서 이 광경을 확인하고 싶은 </span><span class="sxs-lookup"><span data-stu-id="b29da-190">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="b29da-191">사람이 있습니까?</span><span class="sxs-lookup"><span data-stu-id="b29da-191">Rainier?</span></span> <br/><br/> <span data-ttu-id="b29da-192">Birdwatchers 토론 목록에 이 메시지가 전송되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-192">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="b29da-193">구독은 언제든지 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-193">You can unsubscribe at any time.</span></span>

<span data-ttu-id="b29da-194">메일 그룹 메일이 스푸핑 방지 검사를 통과할 수 있도록 메일 그룹 제어 여부에 따라 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-194">To help mailing list messages pass anti-spoofing checks, do following steps based on whether you control the mailing list:</span></span>

- <span data-ttu-id="b29da-195">조직이 메일 그룹을 소유한 경우:</span><span class="sxs-lookup"><span data-stu-id="b29da-195">Your organization owns the mailing list:</span></span>

  - <span data-ttu-id="b29da-196">DMARC.org의 FAQ를 확인하십시오. [메일링 목록을 운영 중이며 DMARC와 상호 운용하고 싶습니다. 어떻게 해야 합니까?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F).</span><span class="sxs-lookup"><span data-stu-id="b29da-196">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F).</span></span>

  - <span data-ttu-id="b29da-197">이 블로그 게시물의 지침을 읽으십시오: [메일 그룹 운영자가 DMARC와 상호 작용하여 실패를 방지하는 팁](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/).</span><span class="sxs-lookup"><span data-stu-id="b29da-197">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/).</span></span>

  - <span data-ttu-id="b29da-198">ARC를 지원하기 위해 메일 그룹 서버에 업데이트를 설치하는 것을 고려한다면 [https://arc-spec.org](https://arc-spec.org/)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b29da-198">Consider installing updates on your mailing list server to support ARC, see [https://arc-spec.org](https://arc-spec.org/)</span></span>

- <span data-ttu-id="b29da-199">조직이 메일 그룹을 소유하고 있지 않음:</span><span class="sxs-lookup"><span data-stu-id="b29da-199">Your organization doesn't own the mailing list:</span></span>

  - <span data-ttu-id="b29da-200">메일 그룹 관리자에게 메일 그룹이 리스트가 받아서 전달 중인 도메인의 전자 메일 인증을 구성할 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-200">Ask the maintainer of the mailing list to configure email authentication for the domain that the mailing list is relaying from.</span></span>

    <span data-ttu-id="b29da-201">충분한 수의 보낸 사람이 도메인 소유자에게 전자 메일 인증 레코드를 설정해야한다고 회신하면 이들은 작업을 수행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-201">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="b29da-202">Microsoft는 도메인 소유자와 함께 필요한 레코드를 게시하기도 하지만 개별 사용자가 요청할 때 더 많은 도움을줍니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-202">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

  - <span data-ttu-id="b29da-203">이메일 클라이언트에서 받은 편지함 규칙을 만들어 메일을 받은 편지함으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-203">Create inbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="b29da-204">[스푸핑 인텔리전스를 사용해 인증되지 않은 전자 메일의 허용된 송신자 구성](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email)에 나온 대로 관리자에게 재정의를 구성하도록 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-204">You can also ask your admins to configure overrides as discussed in the [Use spoof intelligence to configure permitted senders of unauthenticated email](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email).</span></span>

  - <span data-ttu-id="b29da-205">Microsoft 365에서 지원 티켓을 만들면 재정의를 만들어서 메일 그룹을 합법적인 것으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-205">Create a support ticket with Microsoft 365 to create an override for the mailing list to treat it as legitimate.</span></span> <span data-ttu-id="b29da-206">자세한 내용은 [비즈니스 제품에 대한 고객 지원팀 문의 - 관리자 도움말](../../admin/contact-support-for-business-products.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-206">For more information, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="b29da-207">그 밖의 모든 시도가 실패하면 Microsoft에 메일을 가양성으로 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-207">If all else fails, you can report the message as a false positive to Microsoft.</span></span> <span data-ttu-id="b29da-208">자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-208">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="b29da-209">Microsoft 지원 티켓으로 사용하도록 관리자에게 문의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-209">You may also contact your admin who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="b29da-210">Microsoft 엔지니어링 팀은 메시지가 스푸핑으로 표시된 이유를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-210">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

## <a name="considerations-for-anti-spoofing-protection"></a><span data-ttu-id="b29da-211">스푸핑 방지 보호 기능 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b29da-211">Considerations for anti-spoofing protection</span></span>

<span data-ttu-id="b29da-212">현재 Microsoft 365로 메시지를 전송하는 관리자의 경우, 전자 메일이 제대로 인증되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-212">If you're an admin who currently sends messages to Microsoft 365, you need to ensure that your email is properly authenticated.</span></span> <span data-ttu-id="b29da-213">인증되지 않으면 스팸 또는 피싱으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29da-213">Otherwise, it might be marked as spam or phish.</span></span> <span data-ttu-id="b29da-214">자세한 내용은 [인증 되지 않은 전자 메일을 보내려는 는 정당한 발신자용 솔루션](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29da-214">For more information, see [Solutions for legitimate senders who are sending unauthenticated email](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).</span></span>