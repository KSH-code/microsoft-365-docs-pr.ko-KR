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
- m365initiative-defender-office365
description: 관리자는 EOP(Exchange Online Protection)에서 스푸핑 방지 보호에 대한 질문과 대답을 볼 수 있습니다.
ms.openlocfilehash: f567c7bc0c6a6efed7621cec86c5db4e616290b7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616734"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="66d37-103">스푸핑 방지 보호 기능 FAQ</span><span class="sxs-lookup"><span data-stu-id="66d37-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="66d37-104">이 문서에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 대한 스푸핑 방지 보호에 대한 질문과 대답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-104">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="66d37-105">스팸 방지 보호에 대한 질문과 대답은 스팸 방지 보호 [FAQ를 참조하세요.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="66d37-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="66d37-106">맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 방지 [보호 FAQ를 참조하세요.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="66d37-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="66d37-107">Microsoft에서 확인되지 않은 인바운드 전자 메일을 정크로 선택한 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="66d37-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="66d37-108">Microsoft는 합법적인 인바운드 전자 메일을 잃을 위험보다 더 높은 것으로 생각하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-108">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="66d37-109">정크 메일 정크를 통해 합법적인 전자 메일이 스팸으로 표시될 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="66d37-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="66d37-110">Microsoft에서 2018년 이 기능을 사용하도록 설정하면 일부 가음성(좋은 메시지가 잘못된 것으로 표시)이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="66d37-111">그러나 시간이 지날 때 보낸 사람이 요구 사항에 맞게 조정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-111">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="66d37-112">스푸핑으로 잘못 확인된 메시지 수는 대부분의 전자 메일 경로에서 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-112">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="66d37-113">Microsoft 자체는 고객에게 배포하기 몇 주 전에 먼저 새로운 전자 메일 인증 요구 사항을 채택했습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-113">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="66d37-114">처음에는 혼란이 있었지만 점차적으로 감소했습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-114">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="66d37-115">Office 365용 Defender 없이 Microsoft 365 고객이 스푸핑 인텔리전스를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="66d37-115">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="66d37-116">예.</span><span class="sxs-lookup"><span data-stu-id="66d37-116">Yes.</span></span> <span data-ttu-id="66d37-117">2018년 10월부터 Exchange Online 사서함이 있는 모든 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직에서는 스푸핑 인텔리전스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-117">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="66d37-118">스팸 또는 비스팸 메시지를 Microsoft에 다시 보고하려면 어떻게 합니까?</span><span class="sxs-lookup"><span data-stu-id="66d37-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="66d37-119">[Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66d37-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="66d37-120">I'm an admin and I don't know all of sources for messages in my email domain!</span><span class="sxs-lookup"><span data-stu-id="66d37-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="66d37-121">See [You don't know all sources for your email.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)</span><span class="sxs-lookup"><span data-stu-id="66d37-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="66d37-122">조직에서 스푸핑 방지 보호 기능을 사용하지 않도록 설정하면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="66d37-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="66d37-123">스푸핑 방지 보호 기능을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-123">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="66d37-124">보호 기능을 설정하면 조직에 더 많은 피싱 및 스팸 메시지가 배달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-124">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="66d37-125">모든 피싱이 스푸핑인 것은 아니며, 스푸핑된 메시지 중 모든 메시지가 누락되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-125">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="66d37-126">그러나 위험은 더 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-126">However, your risk will be higher.</span></span>

<span data-ttu-id="66d37-127">커넥터에 [](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 대한 향상된 필터링을 사용할 수 있습니다. 전자 메일이 EOP 전에 다른 서비스를 통해 라우팅되는 경우 더 이상 스푸핑 방지 보호 기능을 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-127">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="66d37-128">스푸핑 방지 보호가 모든 피싱으로부터 보호될 것입니까?</span><span class="sxs-lookup"><span data-stu-id="66d37-128">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="66d37-129">안타깝게도, 아니요.</span><span class="sxs-lookup"><span data-stu-id="66d37-129">Unfortunately, no.</span></span> <span data-ttu-id="66d37-130">공격자는 다른 기술(예: 무료 전자 메일 서비스의 손상된 계정 또는 계정)을 사용하기 위해 적응합니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-130">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="66d37-131">그러나 피싱 방지 보호는 이러한 다른 유형의 피싱 방법을 검색하는 데 훨씬 더 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-131">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="66d37-132">EOP의 보호 계층은 함께 작동하고 서로를 토대화하여 설계됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-132">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="66d37-133">다른 대규모 전자 메일 서비스에서 확인되지 않은 인바운드 전자 메일을 차단하나요?</span><span class="sxs-lookup"><span data-stu-id="66d37-133">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="66d37-134">거의 모든 대규모 전자 메일 서비스는 기존의 SPF, DKIM 및 DMARC 검사를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-134">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="66d37-135">일부 서비스에는 좀 더 엄격한 기타 검사가 있지만, EOP에서 확인되지 않은 전자 메일을 차단하고 이를 스푸핑된 메시지로 취급하는 서비스는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-135">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="66d37-136">그러나 업계에서는 특히 피싱 문제로인 미인증 전자 메일의 문제에 대해 더 잘 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-136">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="66d37-137">스푸핑 방지를 사용하도록 설정한 경우 고급 스팸 필터 설정 "SPF 레코드: 하드 _실패"(MarkAsSpamSpfRecordHardFail)를_ 사용하도록 설정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="66d37-137">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="66d37-138">아니요.</span><span class="sxs-lookup"><span data-stu-id="66d37-138">No.</span></span> <span data-ttu-id="66d37-139">이 ASF 설정은 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-139">This ASF setting is no longer required.</span></span> <span data-ttu-id="66d37-140">스푸핑 방지 보호는 SPF 하드 실패와 훨씬 광범위한 기준 집합을 모두 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-140">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="66d37-141">스푸핑 방지를 사용하고 **SPF 레코드: 하드 실패**(_MarkAsSpamSpfRecordHardFail_)를 켠 경우 더 많은 오탐지가 발생할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-141">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="66d37-142">스팸 또는 피싱 메시지를 검색할 수 있는 추가 이점이 거의 없는 이 기능을 사용하지 않도록 설정하고 대신 대부분 오탐지가 생성되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-142">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="66d37-143">자세한 내용은 [EOP의 ASF(고급](advanced-spam-filtering-asf-options.md)스팸 필터) 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66d37-143">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="66d37-144">보낸 사람 다시 덮기 스키마가 전달된 전자 메일을 수정하는 데 도움이 하나요?</span><span class="sxs-lookup"><span data-stu-id="66d37-144">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="66d37-145">SRS는 전달된 전자 메일 문제를 부분적으로만 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-145">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="66d37-146">SRS는 SMTP **MAIL FROM을** 다시 하여 전달된 메시지가 다음 대상에 SPF를 전달하는지 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-146">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="66d37-147">그러나 스푸핑 방지는 **MAIL FROM**  또는 DKIM 서명 도메인(또는 기타 신호)와 함께 보낸 편지지 주소를 기반으로 하기 때문에 SRS 전달 전자 메일이 스푸핑으로 표시되지 않도록 방지하는 것만으로는 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66d37-147">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
