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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 EOP(Exchange Online Protection)에서 스푸핑 방지 보호에 대한 질문과 대답을 볼 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7e7163037029761a53a5461de592e46ab5ea0485
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917561"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="d3afd-103">스푸핑 방지 보호 기능 FAQ</span><span class="sxs-lookup"><span data-stu-id="d3afd-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d3afd-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="d3afd-104">**Applies to**</span></span>
- [<span data-ttu-id="d3afd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d3afd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d3afd-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="d3afd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d3afd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3afd-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="d3afd-108">이 문서에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 대한 스푸핑 방지 보호에 대한 질문과 대답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-108">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="d3afd-109">스팸 방지 보호에 대한 질문과 대답은 스팸 방지 보호 [FAQ 를 참조하세요.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="d3afd-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="d3afd-110">맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 방지 보호 [FAQ를 참조하세요.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="d3afd-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="d3afd-111">Microsoft에서 확인되지 않은 인바운드 전자 메일을 정크로 선택한 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d3afd-111">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="d3afd-112">Microsoft는 무단 인바운드 전자 메일을 계속 허용할 위험이 합법적인 인바운드 전자 메일을 잃을 위험보다 높다는 생각을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-112">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="d3afd-113">정크 메일 정크를 통해 합법적인 전자 메일이 스팸으로 표시될 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d3afd-113">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="d3afd-114">Microsoft에서 2018년 이 기능을 사용하도록 설정한 경우 일부 가음성(좋은 메시지는 나쁜 것으로 표시)이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-114">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="d3afd-115">그러나 시간이 지날 때 보낸 사람이 요구 사항에 맞게 조정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-115">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="d3afd-116">스푸핑된 것으로 잘못 확인된 메시지 수는 대부분의 전자 메일 경로에서 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-116">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="d3afd-117">Microsoft 자체는 고객에게 배포하기 몇 주 전에 먼저 새로운 전자 메일 인증 요구 사항을 채택했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-117">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="d3afd-118">처음에는 혼란이 있었지만 점차적으로 감소했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-118">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="d3afd-119">Office 365용 Defender 없이 Microsoft 365 고객이 스푸핑 인텔리전스를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d3afd-119">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="d3afd-120">예.</span><span class="sxs-lookup"><span data-stu-id="d3afd-120">Yes.</span></span> <span data-ttu-id="d3afd-121">2018년 10월부터 Exchange Online 사서함이 있는 모든 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직에서는 스푸핑 인텔리전스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-121">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="d3afd-122">스팸 또는 비스팸 메시지를 Microsoft에 다시 보고하려면 어떻게 합니까?</span><span class="sxs-lookup"><span data-stu-id="d3afd-122">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="d3afd-123">[Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3afd-123">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="d3afd-124">I'm an admin and I don't know all of sources for messages in my email domain!</span><span class="sxs-lookup"><span data-stu-id="d3afd-124">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="d3afd-125">You [don't know all sources for your email을 참조하세요.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)</span><span class="sxs-lookup"><span data-stu-id="d3afd-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="d3afd-126">조직에서 스푸핑 방지 보호 기능을 사용하지 않도록 설정하면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="d3afd-126">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="d3afd-127">스푸핑 방지 보호 기능을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-127">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="d3afd-128">보호 기능을 설정하면 조직에서 더 많은 피싱 및 스팸 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-128">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="d3afd-129">모든 피싱이 스푸핑하는 것은 아니며 스푸핑된 메시지 중 모든 메시지가 누락되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-129">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="d3afd-130">그러나 위험은 더 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-130">However, your risk will be higher.</span></span>

<span data-ttu-id="d3afd-131">이제 [커넥터에](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 대한 향상된 필터링을 사용할 수 있습니다. 전자 메일이 EOP보다 먼저 다른 서비스를 통해 라우팅되는 경우 스푸핑 방지 보호 기능을 해제하는 것이 더 이상 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-131">Now that [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="d3afd-132">스푸핑 방지 보호가 모든 피싱으로부터 보호될 것입니까?</span><span class="sxs-lookup"><span data-stu-id="d3afd-132">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="d3afd-133">안타깝게도, 아니요.</span><span class="sxs-lookup"><span data-stu-id="d3afd-133">Unfortunately, no.</span></span> <span data-ttu-id="d3afd-134">공격자는 다른 기술(예: 무료 전자 메일 서비스의 손상된 계정 또는 계정)을 사용하기 위해 적응합니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-134">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="d3afd-135">그러나 피싱 방지 보호는 이러한 다른 유형의 피싱 방법을 감지하는 데 훨씬 더 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-135">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="d3afd-136">EOP의 보호 계층은 함께 작동하고 서로 위에 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-136">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="d3afd-137">다른 대규모 전자 메일 서비스가 확인되지 않은 인바운드 전자 메일을 차단하나요?</span><span class="sxs-lookup"><span data-stu-id="d3afd-137">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="d3afd-138">거의 모든 대규모 전자 메일 서비스는 기존의 SPF, DKIM 및 DMARC 검사를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-138">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="d3afd-139">일부 서비스에는 기타 더 엄격한 검사가 있지만 EOP에서 확인되지 않은 전자 메일을 차단하고 이를 스푸핑된 메시지로 취급하는 서비스는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-139">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="d3afd-140">그러나 업계에서는 특히 피싱 문제로 인하여 확인되지 않은 전자 메일의 문제에 대해 더 잘 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-140">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="d3afd-141">스푸핑 방지를 사용하도록 설정한 경우 고급 스팸 필터 설정 "SPF 레코드: 하드 _실패"(MarkAsSpamSpfRecordHardFail)를_ 사용하도록 설정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d3afd-141">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="d3afd-142">아니요.</span><span class="sxs-lookup"><span data-stu-id="d3afd-142">No.</span></span> <span data-ttu-id="d3afd-143">이 ASF 설정은 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-143">This ASF setting is no longer required.</span></span> <span data-ttu-id="d3afd-144">스푸핑 방지 보호는 SPF 하드 실패와 훨씬 광범위한 기준을 모두 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-144">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="d3afd-145">스푸핑 방지를 사용하고 **SPF 레코드: 하드 실패**(_MarkAsSpamSpfRecordHardFail_)를 켠 경우 더 많은 오탐지가 발생할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-145">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="d3afd-146">스팸 또는 피싱 메시지를 검색할 수 있는 추가 이점은 거의 제공되지 않고 대부분 가극적이지 않도록 설정하는 대신 이 기능을 사용하지 않도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-146">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="d3afd-147">자세한 내용은 [EOP의 ASF(고급 스팸 필터) 설정을 참조하세요.](advanced-spam-filtering-asf-options.md)</span><span class="sxs-lookup"><span data-stu-id="d3afd-147">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="d3afd-148">Sender Rewriting Scheme은 전달된 전자 메일을 해결하는 데 도움이 하나요?</span><span class="sxs-lookup"><span data-stu-id="d3afd-148">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="d3afd-149">SRS는 전달된 전자 메일 문제를 부분적으로만 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-149">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="d3afd-150">SRS는 SMTP **MAIL FROM을** 다시 하여 전달된 메시지가 다음 대상에 SPF를 전달하는지 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-150">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="d3afd-151">그러나 스푸핑 방지는 **MAIL FROM**  또는 DKIM 서명 도메인(또는 기타 신호)와 함께 보낸 편지지 주소를 기반으로 하여 SRS 전달 전자 메일이 스푸핑으로 표시되지 않도록 하는 것만으로는 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3afd-151">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>