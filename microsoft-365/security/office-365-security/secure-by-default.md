---
title: 기본적으로 보안은 Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: EOP(보안 기본 설정)에 대해 Exchange Online Protection 자세히 알아보시다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d5cdc8f8faa9c2d5772fd1572134ea49cdd77da
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624052"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="3333f-103">기본적으로 보안은 Office 365</span><span class="sxs-lookup"><span data-stu-id="3333f-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3333f-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="3333f-104">**Applies to**</span></span>
- [<span data-ttu-id="3333f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3333f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3333f-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="3333f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3333f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3333f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3333f-108">"기본적으로 보안"은 가장 안전한 기본 설정을 정의하는 데 사용되는 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="3333f-109">그러나 보안은 생산성과 균형을 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="3333f-110">여기에는 다음과 같은 분산이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-110">This can include balancing across:</span></span>

- <span data-ttu-id="3333f-111">**사용 가능성:** 설정 생산성을 높이지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="3333f-112">**위험:** 보안이 중요한 활동을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="3333f-113">**레거시 설정:** 새 최신 설정이 개선된 경우에도 비즈니스상의 이유로 이전 제품 및 기능에 대한 일부 구성을 유지 관리해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="3333f-114">Microsoft 365 사서함이 있는 Exchange Online EOP(Exchange Online Protection 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="3333f-115">이 보호에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-115">This protection includes:</span></span>

- <span data-ttu-id="3333f-116">의심되는 맬웨어가 있는 전자 메일은 자동으로 고지되고 받는 사람에게 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="3333f-117">[EOP에서 맬웨어 방지 정책 구성을 참조합니다.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3333f-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="3333f-118">높은 신뢰도 피싱으로 식별된 전자 메일은 스팸 방지 정책 조치에 따라 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="3333f-119">[EOP에서 스팸 방지 정책 구성을 참조합니다.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3333f-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="3333f-120">EOP에 대한 자세한 내용은 Exchange Online Protection [개요를 참조하세요.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3333f-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="3333f-121">Microsoft는 기본적으로 고객의 보안을 유지하기를 원하기 때문에 일부 테넌트는 맬웨어 또는 높은 신뢰도 피싱에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="3333f-122">이러한 오버라이드에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-122">These overrides include:</span></span>

- <span data-ttu-id="3333f-123">허용된 보낸 사람 목록 또는 허용된 도메인 목록(스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="3333f-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="3333f-124">Outlook 수신이 안전한 보낸 사람</span><span class="sxs-lookup"><span data-stu-id="3333f-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="3333f-125">IP 허용 목록(연결 필터링)</span><span class="sxs-lookup"><span data-stu-id="3333f-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="3333f-126">이러한 오버라이드에 대한 자세한 내용은 안전한 보낸 사람 목록 만들기 [에서 찾을 수 있습니다.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="3333f-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3333f-127">EOP 스팸 방지 정책에서 높은  신뢰도의 피싱 전자 메일  판정에 대한 정크 메일 폴더로 메시지 이동 작업을 더는 사용되지 않는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="3333f-128">높은 신뢰도의 피싱 메시지에 대해 이 작업을 사용하는 스팸 방지 정책은 메시지 를 **Quarantine message 로 변환합니다.**</span><span class="sxs-lookup"><span data-stu-id="3333f-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="3333f-129">높은 **신뢰도의** 피싱 메시지에 대한 전자 메일 주소로 메시지 리디렉션 작업은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="3333f-130">기본적으로 보안은 켜거나 끄는 설정이 아니며, 필터링이 기본적으로 작동하여 잠재적으로 위험하거나 원치 않는 메시지를 사서함 밖으로 유지하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="3333f-131">맬웨어 및 높은 신뢰도의 피싱 메시지는 차단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="3333f-132">관리자만 맬웨어 또는 높은 신뢰도 피싱으로 보호된 메시지를 관리할 수 있으며, Microsoft에 가음성 보고도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="3333f-133">자세한 내용은 EOP에서 관리자로 [quarantined messages and files를 참조하세요.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="3333f-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="3333f-134">이 작업을 수행하고 있는 이유에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="3333f-134">More on why we're doing this</span></span>

<span data-ttu-id="3333f-135">기본적으로 보안이 유지되는 경우: 구성된 예외로 메시지가 배달될 수 있는 경우에도 악의적인 메시지를 알고 있는 경우 메시지에 대해 동일한 작업을 수행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="3333f-136">이는 항상 맬웨어에 사용한 방법과 동일하며, 이제는 높은 신뢰도의 피싱 메시지로 동일한 동작을 확장하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="3333f-137">이 데이터는 사용자가 정크 메일 폴더와 Quarantine의 메시지에서 악의적인 링크를 클릭할 가능성이 30배 더 높을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="3333f-138">또한 이 데이터는 높은 신뢰도의 피싱 메시지에 대한 가음성 비율(양호한 메시지)이 매우 낮고 관리자가 관리자 제출을 통해 가짓 긍정을 해결할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="3333f-139">또한 스팸 방지 정책 및 수신 허용 정책의 허용된 보낸 사람 및 허용된 도메인 목록이 Outlook 너무 광범위하여 양호한 것보다 더 많은 손상을 초래하는 것으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="3333f-140">또 다른 방법으로 말해서, 보안 서비스로, 사용자가 손상되지 않도록 사용자를 대신하여 행동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span>

## <a name="exceptions"></a><span data-ttu-id="3333f-141">예외</span><span class="sxs-lookup"><span data-stu-id="3333f-141">Exceptions</span></span>

> [!NOTE]
> <span data-ttu-id="3333f-142">2021년 7월에는 기본적으로 보안이 Exchange 메일 흐름 규칙(전송 규칙)으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-142">In July 2021, secure by default will be extended to Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="3333f-143">메일 흐름 규칙을 사용하여 타사 피싱 시뮬레이션 또는 필터되지 않은 배달을 보안 작업 사서함으로 허용하는 경우 결국 이러한 [](configure-advanced-delivery.md) 규칙을 제거하고 기능을 사용할 수 있는 경우 고급 배달 정책을 사용하여 _전환해야 합니다._</span><span class="sxs-lookup"><span data-stu-id="3333f-143">If you use mail flow rules to allow third-party phishing simulations or unfiltered delivery to security operation mailboxes, you eventually need to eliminate these rules and switch to using the [advanced delivery policy](configure-advanced-delivery.md) _when the feature is available to you_.</span></span>

<span data-ttu-id="3333f-144">높은 신뢰도의 피싱 메시지가 필터링을 무시할 수 있는 유일한 무시는 메일 흐름 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-144">The only override that allows high confidence phishing message to bypass filtering is mail flow rules.</span></span> <span data-ttu-id="3333f-145">메일 흐름 규칙을 사용하여 필터링을 무시하는 경우 메일 흐름 규칙을 사용하여 [메시지에서 SCL 설정을 참조합니다.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)</span><span class="sxs-lookup"><span data-stu-id="3333f-145">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

<span data-ttu-id="3333f-146">다음과 같은 시나리오에서만 오버라이드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-146">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="3333f-147">피싱 시뮬레이션: 시뮬레이션된 공격은 실제 공격이 조직에 영향을 미치기 전에 취약한 사용자를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-147">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="3333f-148">보안/SecOps 사서함: 보안 팀에서 필터되지 않은 메시지를 받는 데 사용하는 전용 사서함(좋음 및 불량)</span><span class="sxs-lookup"><span data-stu-id="3333f-148">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="3333f-149">Teams 검토하여 악성 콘텐츠가 포함되어 있는지 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-149">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="3333f-150">타사 필터: 도메인의 MX 레코드가 기본 설정을 지정하지 않는 경우 기본적으로 보안이 적용되지 Office 365.</span><span class="sxs-lookup"><span data-stu-id="3333f-150">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="3333f-151">가양성: 관리자 제출을 통해 Microsoft에서 여전히 분석하고 있는 특정 메시지를 일시적으로 [허용할 수 있습니다.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="3333f-151">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="3333f-152">모든 재지정과 함께 임시로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3333f-152">As with all overrides, it is recommended that they are temporary.</span></span>
