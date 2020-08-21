---
title: 스푸핑 방지 보호 기능 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection)의 스푸핑 방지 보호 기능에 대한 질문과 답변을 볼 수 있습니다.
ms.openlocfilehash: 66dbedaf638154c4a35359a4e5bc66c326c04d1e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826676"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="30ef5-103">스푸핑 방지 보호 기능 FAQ</span><span class="sxs-lookup"><span data-stu-id="30ef5-103">Anti-spoofing protection FAQ</span></span>

<span data-ttu-id="30ef5-104">이 항목에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 스푸핑 방지 보호기능에 대한 질문과 답변을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-104">This topic provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="30ef5-105">스팸 방지 보호 기능에 대한 질문과 대답은 스팸 [방지 보호 FAQ를 참조하세요.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="30ef5-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="30ef5-106">맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 [방지 보호 FAQ를 참조하세요.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="30ef5-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="30ef5-107">Microsoft가 인증되지 않은 인바운드 전자 메일을 보내도록 선택하는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="30ef5-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="30ef5-108">피싱 공격의 영향으로 인해 전자 메일 인증이 15년 이상 지속되었기 때문에 Microsoft는 합법적인 인바운드 전자 메일 손실 위험보다 인증되지 않은 인바운드 전자 메일을 지속적으로 받을 위험이 높다고 생각합니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-108">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="30ef5-109">인증되지 않은 인바운드 전자 메일로 인해 합법적 전자 메일이 스팸으로 표시됩니까?</span><span class="sxs-lookup"><span data-stu-id="30ef5-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="30ef5-110">Microsoft가 2018년에 이 기능을 사용하도록 설정하면 일부 가양성이 발생했습니다(좋은 메시지가 잘못된 것으로 표시됨).</span><span class="sxs-lookup"><span data-stu-id="30ef5-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="30ef5-111">하지만 시간이 지남에 따라 보낸 사람은 새로운 보낸 사람 인증 요구 사항으로 조정되며 대부분의 이메일 경로에 대해 스푸핑된(보이이이이) 메시지 수는 금지됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-111">However, over time, senders adjusted to the new sender authentication requirements, and the number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="30ef5-112">Microsoft 자체는 처음에 고객에게 배포하기 몇 주 전에 몇 주 전에 새로운 전자 메일 인증 요구 사항을 채택했습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-112">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="30ef5-113">처음에는 혼란이 있었지만 점차적으로 감소했습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-113">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a><span data-ttu-id="30ef5-114">ATP가 없는 Microsoft 365 고객은 스푸핑 인텔리전스를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="30ef5-114">Is spoof intelligence available to Microsoft 365 customers without ATP?</span></span>

<span data-ttu-id="30ef5-115">예.</span><span class="sxs-lookup"><span data-stu-id="30ef5-115">Yes.</span></span> <span data-ttu-id="30ef5-116">2018년 10월을 현재, Exchange Online 사서함이 없는 모든 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직을 보유한 모든 조직에서 스푸핑 인텔리전스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-116">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="30ef5-117">스푸핑 방지 기술은 초기에 Office 365 Enterprise E5 구독 또는 해당 구독에 대한 Office 365 ATP(Advanced Threat Protection) 추가 기능이 있는 조직에만 배포되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-117">Anti-spoofing technology was initially deployed only to organizations that had Office 365 Enterprise E5 subscriptions or the Office 365 Advanced Threat Protection (Office 365 ATP) add-on for their subscription.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="30ef5-118">스팸 또는 비스팸 메시지를 Microsoft에 다시 보고하려면 어떻게 합니까?</span><span class="sxs-lookup"><span data-stu-id="30ef5-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="30ef5-119">[Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30ef5-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="30ef5-120">저는 관리자이고 내 전자 메일 도메인에서 메시지에 대한 모든 원본을 모르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="30ef5-121">전자 [메일에 대해 모든 원본을 알 수 없습니다.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)</span><span class="sxs-lookup"><span data-stu-id="30ef5-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="30ef5-122">조직에서 스푸핑 방지 기능을 사용하지 않도록 설정하면 어떻게 됩니까?</span><span class="sxs-lookup"><span data-stu-id="30ef5-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="30ef5-123">피싱 및 스팸 메일을 놓치는 경우가 많아질 것이므로 이는 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-123">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="30ef5-124">모든 피싱이 스푸핑이 되는 것은 아니며 모든 스푸핑이 누락되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-124">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="30ef5-125">그러나 사용자의 위험은 스푸핑 방지를 사용하는 고객보다 높습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-125">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>

<span data-ttu-id="30ef5-126">이제 [커넥터에 대한 향상된 필터링을](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 사용할 수 있도록 전자 메일을 EOP에 배달하기 전에 MX 레코드가 다른 서버나 서비스를 가리키는 경우 스푸핑 방지 보호 기능을 더 이상 사용하지 않도록 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-126">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended that you turn off anti-spoofing protection if your MX record points to another server or service before delivering email to EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="30ef5-127">스푸핑 방지 기능은 모든 피싱으로부터 보호받을 수 있다는 의미입니까?</span><span class="sxs-lookup"><span data-stu-id="30ef5-127">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="30ef5-128">Unfortunately, no.</span><span class="sxs-lookup"><span data-stu-id="30ef5-128">Unfortunately, no.</span></span> <span data-ttu-id="30ef5-129">공격자는 다른 기법(예: 무료 전자 메일 서비스의 계정 또는 계정)을 사용하도록 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-129">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="30ef5-130">그러나 피싱 방지 기능은 다른 유형의 피싱 방법을 탐지하는 데 그다지 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-130">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="30ef5-131">EOP의 보호 계층은 함께 작동하고 서로 위에 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-131">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="30ef5-132">다른 대규모 전자 메일 서비스가 인증되지 않은 인바운드 전자 메일을 차단하나요?</span><span class="sxs-lookup"><span data-stu-id="30ef5-132">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="30ef5-133">거의 모든 대형 전자 메일 서비스는 기존의 SPF, DKIM 및 DMARC 검사를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-133">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="30ef5-134">일부 서비스는 다른 일반적인 검사를 포함하고 있지만 인증되지 않은 전자 메일을 차단하고 이를 스푸핑된 메시지로 간주하는 EOP는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-134">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as as spoofed messages.</span></span> <span data-ttu-id="30ef5-135">그러나 업체에서는 피싱 문제 때문에 인증되지 않은 전자 메일 문제에 대해 더욱 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-135">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="30ef5-136">스푸핑 방지를 사용하는 경우에도 고급 스팸 필터 설정 "SPF 레코드: 하드_실패"(MarkAsSpamSpfRecordHardFail)를_사용하도록 설정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="30ef5-136">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="30ef5-137">아니요.</span><span class="sxs-lookup"><span data-stu-id="30ef5-137">No.</span></span> <span data-ttu-id="30ef5-138">스푸핑 방지 설정은 더 이상 필요하지 않지만 SPF 하드 실패 및 더 광범위한 기준을 고려하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-138">This ASF setting no longer required because anti-spoofing not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="30ef5-139">스푸핑 방지를 사용하고 **SPF 레코드: 하드 실패**(_MarkAsSpamSpfRecordHardFail_)를 켠 경우 더 많은 오탐지가 발생할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-139">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="30ef5-140">스팸이나 피싱 메시지를 검색할 경우 추가적인 이점은 제공하지 않고 대부분 오탐지가 발생하기도 하며 대부분 의미로 오탐지될 수 있으며 이 기능을 사용하지 않도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-140">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="30ef5-141">자세한 내용은 [EOP에서 ASF(고급 스팸 필터) 설정을 참조하세요.](advanced-spam-filtering-asf-options.md)</span><span class="sxs-lookup"><span data-stu-id="30ef5-141">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="30ef5-142">보낸 사람 다시 작성 체크인을 통해 전달된 전자 메일을 수정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="30ef5-142">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="30ef5-143">SRS는 전달된 전자 메일 문제를 부분적으로만 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-143">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="30ef5-144">SMTP **MAIL FROM을**다시 쓰면 SRS를 통해 전달된 메시지가 다음 대상에서 SPF를 통과하는 지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-144">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="30ef5-145">그러나 스푸핑 방지는 MAIL FROM 또는 **From** DKIM 서명 도메인(또는 다른 신호)과 **함께 From** 주소를 기반으로 하기 때문에 SRS로 전달된 전자 메일이 스푸핑으로 표시되지 않도록 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30ef5-145">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
