---
title: 스푸핑 방지 보호 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Exchange Online 및 독립 실행형 Exchange Online Protection (EOP)의 스푸핑 방지 보호 기능에 대 한 질문과 대답이 faq와 함께 제공 됩니다.
ms.openlocfilehash: b39e48fd57b899e6296d40ab10aac265cb4165a3
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529890"
---
# <a name="anti-spoofing-protection-faq-in-office-365"></a><span data-ttu-id="b7431-103">Office 365의 스푸핑 방지 보호 FAQ</span><span class="sxs-lookup"><span data-stu-id="b7431-103">Anti-spoofing protection FAQ in Office 365</span></span>

<span data-ttu-id="b7431-104">이 항목에서는 Exchange Online 사서함이 없는 Exchange Online 또는 독립 실행형 EOP (Exchange Online Protection) 고객의 사서함을 포함 하는 Office 365 고객을 위한 스푸핑 방지 보호에 대 한 질문과 대답을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-104">This topic provides frequently asked questions and answers about anti-spoofing protection for Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

<span data-ttu-id="b7431-105">스팸 방지 보호 기능에 대 한 질문과 대답은 [스팸 방지 보호 FAQ](anti-spam-protection-faq.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7431-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="b7431-106">맬웨어 방지 보호에 대 한 질문과 대답은 [Office 365에서 맬웨어 방지 보호 FAQ](anti-malware-protection-faq-eop.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7431-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ in Office 365](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="b7431-107">Microsoft에서 정크로 인증 되지 않은 인바운드 전자 메일을 선택한 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b7431-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="b7431-108">피싱 공격이 영향을 받으면서 전자 메일 인증이 15 년 동안 진행 되었기 때문에 Microsoft는 인증 되지 않은 인바운드 전자 메일을 계속 허용 하는 위험이 합법적인 인바운드 전자 메일이 손실 되는 위험 보다 높다는 것을 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-108">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="b7431-109">인증 되지 않은 인바운드 전자 메일로 인해 합법적인 전자 메일이 스팸으로 표시 junking?</span><span class="sxs-lookup"><span data-stu-id="b7431-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="b7431-110">Microsoft에서 2018의이 기능을 사용 하도록 설정 하면 가양성 메시지가 잘못 된 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="b7431-111">그러나 시간이 지남에 따라 보낸 사람이 새로운 보낸 사람 인증 요구 사항에 맞게 조정 되었으며, 스푸핑된로 잘못 식별 되어 된 메시지의 수는 대부분의 전자 메일 경로에서 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-111">However, over time, senders adjusted to the new sender authentication requirements, and the number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="b7431-112">Microsoft는 먼저 새 전자 메일 인증 요구 사항을 고객에 게 배포 하기 위해 몇 주 정도 도입 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-112">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="b7431-113">처음에는 혼란이 있었지만 점차적으로 감소했습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-113">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-office-365-customers-without-atp"></a><span data-ttu-id="b7431-114">Office 365 고객이 ATP를 사용 하지 않고 스푸핑 인텔리전스를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b7431-114">Is spoof intelligence available to Office 365 customers without ATP?</span></span>

<span data-ttu-id="b7431-115">예.</span><span class="sxs-lookup"><span data-stu-id="b7431-115">Yes.</span></span> <span data-ttu-id="b7431-116">2018 년 10 월 부터는 Exchange Online 사서함이 있는 모든 조직이 나 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 있는 모든 조직에서 스푸핑 인텔리전스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-116">As of October 2018, spoof intelligence is available to all organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="b7431-117">스푸핑 방지 기술은 Office 365 Enterprise E5 구독 또는 구독에 대 한 Office 365 Advanced Threat Protection (ATP) 추가 기능을 가진 조직에 처음으로 배포 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-117">Anti-spoofing technology was initially deployed to organizations that had Office 365 Enterprise E5 subscriptions or the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="b7431-118">스팸 또는 비스팸 메시지를 Microsoft에 다시 보고하려면 어떻게 합니까?</span><span class="sxs-lookup"><span data-stu-id="b7431-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="b7431-119">[Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7431-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="b7431-120">관리자이 고 전자 메일 도메인에 있는 메시지의 모든 원본을 알지 못하는 경우</span><span class="sxs-lookup"><span data-stu-id="b7431-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="b7431-121">[전자 메일의 모든 원본을 알지 못하는 것을 볼 수 있습니다](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span><span class="sxs-lookup"><span data-stu-id="b7431-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="b7431-122">조직에서 스푸핑 방지 보호를 사용 하지 않도록 설정 하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="b7431-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="b7431-123">피싱 및 스팸 메일을 놓치는 경우가 많아질 것이므로 이는 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-123">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="b7431-124">모든 피싱이 스푸핑이 되는 것은 아니며 모든 스푸핑이 누락되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-124">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="b7431-125">그러나 사용자의 위험은 스푸핑 방지를 사용하는 고객보다 높습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-125">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>

<span data-ttu-id="b7431-126">이제 [커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 을 사용할 수 있으므로 MX 레코드가 EOP에 전자 메일을 배달 하기 전에 다른 서버 또는 서비스를 가리키는 경우 스푸핑 방지 보호를 해제 하는 것이 더 이상 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-126">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended that you turn off anti-spoofing protection if your MX record points to another server or service before delivering email to EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="b7431-127">스푸핑 방지 보호는 모든 피싱 으로부터 보호 될 것 이라는 의미 입니까?</span><span class="sxs-lookup"><span data-stu-id="b7431-127">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="b7431-128">안타깝게도</span><span class="sxs-lookup"><span data-stu-id="b7431-128">Unfortunately, no.</span></span> <span data-ttu-id="b7431-129">공격자는 다른 기술 (예: 손상 된 계정 또는 무료 전자 메일 서비스의 계정) 사용에 적응 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-129">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="b7431-130">그러나 피싱 방지 보호 기능은 이러한 다른 유형의 피싱 방법을 보다 효율적으로 검색 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-130">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="b7431-131">Office 365의 보호 계층은 함께 작동 하 고 서로의 위에 구축 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-131">The protection layers in Office 365 are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="b7431-132">다른 대규모 전자 메일 서비스가 인증 되지 않은 인바운드 전자 메일을 차단 하나요?</span><span class="sxs-lookup"><span data-stu-id="b7431-132">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="b7431-133">거의 모든 대규모 전자 메일 서비스는 기존 SPF, DKIM 및 DMARC 검사를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-133">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="b7431-134">일부 서비스는 좀 더 엄격한 검사를 수행 하지만 Office 365에서 인증 되지 않은 전자 메일을 차단 하 고이를 스푸핑된 메시지로 취급 해야 하는 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-134">Some services have other, more strict checks, but few go as far as Office 365 to block unauthenticated email and treat them as as spoofed messages.</span></span> <span data-ttu-id="b7431-135">그러나 업계에서는 특히 피싱 문제로 인해 인증 되지 않은 전자 메일의 문제를 보다 잘 파악 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-135">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="b7431-136">스푸핑 방지를 사용 하도록 설정한 경우에도 고급 스팸 필터 설정 "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_)을 사용 하도록 설정 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="b7431-136">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="b7431-137">아니요.</span><span class="sxs-lookup"><span data-stu-id="b7431-137">No.</span></span> <span data-ttu-id="b7431-138">SPF 하드에 오류가 발생 하는 것은 아니지만 보다 광범위 한 조건 집합으로 간주 되므로이 ASF 설정은 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-138">This ASF setting no longer required because anti-spoofing not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="b7431-139">스푸핑 방지를 사용하고 **SPF 레코드: 하드 실패**(_MarkAsSpamSpfRecordHardFail_)를 켠 경우 더 많은 오탐지가 발생할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-139">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="b7431-140">스팸 또는 피싱 메시지를 검색 하는 경우에는이 기능을 사용 하지 않는 것이 좋지만 대부분의 경우에는 대개 가양성을 생성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-140">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="b7431-141">자세한 내용은, [Office 365의 고급 스팸 필터링(ASF) 설정](advanced-spam-filtering-asf-options.md)을 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="b7431-141">For more information, see [Advanced Spam Filter (ASF) settings in Office 365](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="b7431-142">보낸 사람 다시 쓰기 체계가 전달 된 전자 메일을 수정 합니까?</span><span class="sxs-lookup"><span data-stu-id="b7431-142">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="b7431-143">SRS는 전달된 전자 메일 문제를 부분적으로만 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-143">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="b7431-144">SRS는에서 SMTP **메일**을 다시 작성 하 여 전달 된 메시지가 다음 목적지에서 SPF를 통과 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-144">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="b7431-145">그러나 위조 방지는 보낸 사람 주소 또는 DKIM 서명 도메인 (또는 기타 신호의)을 사용 하 여 **보내는** **출처** 를 기반으로 하기 때문에 SRS 전달 전자 메일이 스푸핑된로 표시 되지 않도록 하는 것은 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7431-145">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
