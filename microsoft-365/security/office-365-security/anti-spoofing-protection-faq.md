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
description: 관리자는 EOP (Exchange Online Protection)에서 스푸핑 방지 보호에 대 한 질문과 대답을 볼 수 있습니다.
ms.openlocfilehash: 3547b0a0af6d2e541d4ec3546d9bbd4aa34c3a6b
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867142"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="dea5a-103">스푸핑 방지 보호 기능 FAQ</span><span class="sxs-lookup"><span data-stu-id="dea5a-103">Anti-spoofing protection FAQ</span></span>

<span data-ttu-id="dea5a-104">이 문서에서는 exchange online의 사서함을 포함 하는 Microsoft 365 조직에 대 한 스푸핑 방지 보호 기능에 대 한 질문과 대답을 제공 하 고 EOP (독립 실행형 Exchange Online Protection) 조직</span><span class="sxs-lookup"><span data-stu-id="dea5a-104">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="dea5a-105">스팸 방지 보호 기능에 대 한 질문과 대답은 [스팸 방지 보호 FAQ](anti-spam-protection-faq.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dea5a-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="dea5a-106">맬웨어 방지 보호 기능에 대 한 질문과 대답은 [맬웨어 방지 보호 FAQ](anti-malware-protection-faq-eop.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dea5a-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="dea5a-107">Microsoft에서 정크로 인증 되지 않은 인바운드 전자 메일을 선택한 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="dea5a-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="dea5a-108">Microsoft는 인증 되지 않은 인바운드 전자 메일을 계속 해 서 허용 하는 위험이 합법적인 인바운드 전자 메일이 손실 되는 위험 보다 높다는 것을 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-108">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="dea5a-109">인증 되지 않은 인바운드 전자 메일로 인해 합법적인 전자 메일이 스팸으로 표시 junking?</span><span class="sxs-lookup"><span data-stu-id="dea5a-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="dea5a-110">Microsoft에서 2018의이 기능을 사용 하도록 설정 하면 가양성 메시지가 잘못 된 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="dea5a-111">그러나 시간이 지남에 따라 보낸 사람이 요구 사항에 맞게 조정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-111">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="dea5a-112">대부분의 전자 메일 경로에서는 스푸핑된로 잘못 식별 되어 된 메시지 수가 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-112">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="dea5a-113">Microsoft는 먼저 새 전자 메일 인증 요구 사항을 고객에 게 배포 하기 위해 몇 주 정도 도입 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-113">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="dea5a-114">처음에는 혼란이 있었지만 점차적으로 감소했습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-114">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a><span data-ttu-id="dea5a-115">Microsoft 365 고객이 ATP를 사용 하지 않고 스푸핑 인텔리전스를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="dea5a-115">Is spoof intelligence available to Microsoft 365 customers without ATP?</span></span>

<span data-ttu-id="dea5a-116">예.</span><span class="sxs-lookup"><span data-stu-id="dea5a-116">Yes.</span></span> <span data-ttu-id="dea5a-117">10 월 2018 부터는 Exchange Online에 사서함이 있는 모든 조직에서 스푸핑 인텔리전스를 사용할 수 있으며 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-117">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="dea5a-118">스푸핑 방지 기술은 초기에 Office 365 Advanced Threat Protection 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-118">Anti-spoofing technology was initially only available in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="dea5a-119">예를 들어 Microsoft E5 구독 또는 ATP 추가 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-119">For example, Microsoft E5 subscriptions or ATP add-ons.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="dea5a-120">스팸 또는 비스팸 메시지를 Microsoft에 다시 보고하려면 어떻게 합니까?</span><span class="sxs-lookup"><span data-stu-id="dea5a-120">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="dea5a-121">[Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dea5a-121">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="dea5a-122">관리자이 고 전자 메일 도메인에 있는 메시지의 모든 원본을 알지 못하는 경우</span><span class="sxs-lookup"><span data-stu-id="dea5a-122">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="dea5a-123">[전자 메일의 모든 원본을 알지 못하는 것을 볼 수 있습니다](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span><span class="sxs-lookup"><span data-stu-id="dea5a-123">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="dea5a-124">조직에서 스푸핑 방지 보호를 사용 하지 않도록 설정 하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="dea5a-124">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="dea5a-125">스푸핑 방지 보호를 사용 하지 않도록 설정 하는 것은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-125">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="dea5a-126">보호를 사용 하지 않도록 설정 하면 조직에서 더 많은 피싱 및 스팸 메시지가 배달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-126">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="dea5a-127">모든 피싱이 스푸핑 중인 것은 아니며 모든 스푸핑된 메시지가 누락 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-127">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="dea5a-128">하지만 위험은 더 커집니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-128">However, your risk will be higher.</span></span>

<span data-ttu-id="dea5a-129">이제 [커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 을 사용할 수 있으므로 EOP 전에 다른 서비스를 통해 전자 메일을 라우팅하는 경우 스푸핑 방지 보호 기능을 해제 하는 것이 더 이상 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-129">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="dea5a-130">스푸핑 방지 보호는 모든 피싱 으로부터 보호 될 것 이라는 의미 입니까?</span><span class="sxs-lookup"><span data-stu-id="dea5a-130">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="dea5a-131">안타깝게도</span><span class="sxs-lookup"><span data-stu-id="dea5a-131">Unfortunately, no.</span></span> <span data-ttu-id="dea5a-132">공격자는 다른 기술 (예: 손상 된 계정 또는 무료 전자 메일 서비스의 계정) 사용에 적응 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-132">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="dea5a-133">그러나 피싱 방지 보호 기능은 이러한 다른 유형의 피싱 방법을 보다 효율적으로 검색 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-133">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="dea5a-134">EOP의 보호 계층은 함께 작동 하 고 서로의 위에 구축 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-134">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="dea5a-135">다른 대규모 전자 메일 서비스가 인증 되지 않은 인바운드 전자 메일을 차단 하나요?</span><span class="sxs-lookup"><span data-stu-id="dea5a-135">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="dea5a-136">거의 모든 대규모 전자 메일 서비스는 기존 SPF, DKIM 및 DMARC 검사를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-136">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="dea5a-137">일부 서비스는 좀 더 엄격한 검사를 수행 하지만 인증 되지 않은 전자 메일을 차단 하 고이를 스푸핑된 메시지로 취급 하기 위해 EOP을 수행 하는 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-137">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="dea5a-138">그러나 업계에서는 특히 피싱 문제로 인해 인증 되지 않은 전자 메일의 문제를 보다 잘 파악 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-138">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="dea5a-139">스푸핑 방지를 사용 하도록 설정한 경우에도 고급 스팸 필터 설정 "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_)을 사용 하도록 설정 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dea5a-139">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="dea5a-140">아니요.</span><span class="sxs-lookup"><span data-stu-id="dea5a-140">No.</span></span> <span data-ttu-id="dea5a-141">이 ASF 설정은 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-141">This ASF setting is no longer required.</span></span> <span data-ttu-id="dea5a-142">스푸핑 방지 보호 기능은 SPF 하드 실패와 보다 광범위 한 기준 집합을 모두 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-142">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="dea5a-143">스푸핑 방지를 사용하고 **SPF 레코드: 하드 실패**(_MarkAsSpamSpfRecordHardFail_)를 켠 경우 더 많은 오탐지가 발생할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-143">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="dea5a-144">스팸 또는 피싱 메시지를 검색 하는 경우에는이 기능을 사용 하지 않는 것이 좋지만 대부분의 경우에는 대개 가양성을 생성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-144">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="dea5a-145">자세한 내용은 [EOP의 ASF (Advanced 스팸 필터) 설정을](advanced-spam-filtering-asf-options.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dea5a-145">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="dea5a-146">보낸 사람 다시 쓰기 체계가 전달 된 전자 메일을 수정 합니까?</span><span class="sxs-lookup"><span data-stu-id="dea5a-146">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="dea5a-147">SRS는 전달된 전자 메일 문제를 부분적으로만 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-147">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="dea5a-148">SRS는에서 SMTP **메일**을 다시 작성 하 여 전달 된 메시지가 다음 목적지에서 SPF를 통과 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-148">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="dea5a-149">그러나 위조 방지는 보낸 사람 주소 또는 DKIM 서명 도메인 (또는 기타 신호의)을 사용 하 여 **보내는** **출처** 를 기반으로 하기 때문에 SRS 전달 전자 메일이 스푸핑된로 표시 되지 않도록 하는 것은 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dea5a-149">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
