---
title: Office 365에서 기본적으로 보안
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: EOP(Exchange Online Protection)의 보안 기본 설정에 대해 자세히 알아보시고
ms.openlocfilehash: 8db8e7af569114e5829d24d65b8eee89c9dce8c3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787976"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="c710c-103">Office 365에서 기본적으로 보안</span><span class="sxs-lookup"><span data-stu-id="c710c-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c710c-104">"기본적으로 보안"은 가장 안전한 기본 설정을 정의하는 데 사용되는 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="c710c-105">그러나 보안은 생산성과 균형을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="c710c-106">여기에는 다음에 대한 균형 조정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-106">This can include balancing across:</span></span>

- <span data-ttu-id="c710c-107">**사용 가능성:** 설정이 사용자 생산성에 영향을 주면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-107">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="c710c-108">**위험**: 보안이 중요한 활동을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-108">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="c710c-109">**레거시 설정:** 새로운 최신 설정이 개선된 경우에도 비즈니스상의 이유로 이전 제품 및 기능에 대한 일부 구성을 유지 관리해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-109">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="c710c-110">Exchange Online에 사서함이 있는 Microsoft 365 조직은 EOP(Exchange Online Protection)를 통해 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="c710c-111">이 보호에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-111">This protection includes:</span></span>

- <span data-ttu-id="c710c-112">의심되는 맬웨어가 있는 전자 메일은 자동으로 차단되고 받는 사람에게 알림이 발송됩니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="c710c-113">[EOP에서 맬웨어 방지 정책 구성을 참조합니다.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c710c-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="c710c-114">높은 신뢰도 피싱으로 식별된 전자 메일은 스팸 방지 정책 조치에 따라 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-114">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="c710c-115">[EOP에서 스팸 방지 정책 구성을 참조합니다.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c710c-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c710c-116">EOP에 대한 자세한 내용은 [Exchange Online Protection 개요를 참조하세요.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c710c-116">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="c710c-117">Microsoft는 기본적으로 고객의 보안을 유지하기를 원하기 때문에 일부 테넌트는 맬웨어 또는 높은 신뢰도 피싱에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="c710c-118">이러한 오버라이드에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-118">These overrides include:</span></span>

- <span data-ttu-id="c710c-119">허용된 보낸 사람 목록 또는 허용된 도메인 목록(스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="c710c-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="c710c-120">Outlook 수신이 안전한 보낸 사람</span><span class="sxs-lookup"><span data-stu-id="c710c-120">Outlook Safe Senders</span></span>
- <span data-ttu-id="c710c-121">IP 허용 목록(연결 필터링)</span><span class="sxs-lookup"><span data-stu-id="c710c-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="c710c-122">이러한 overrides에 대한 자세한 내용은 수신이 가능한 보낸 사람 목록 [만들기에서 찾을 수 있습니다.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c710c-122">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="c710c-123">기본적으로 보안은 켜거나 끄는 설정이 아니며, 위험할 수 있는 메시지나 원치 않는 메시지를 사서함 밖으로 유지하기 위해 필터링이 기본적으로 작동하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-123">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="c710c-124">맬웨어 및 높은 신뢰도의 피싱 메시지는 차단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-124">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="c710c-125">관리자만 맬웨어 또는 높은 신뢰도 피싱으로 탐지된 메시지를 관리할 수 있으며, 가음성도 Microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-125">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="c710c-126">자세한 내용은 EOP에서 관리자로 [quarantined messages and files as an admin(EOP에서](manage-quarantined-messages-and-files.md) 관리자로 전송된 메시지 및 파일 관리)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c710c-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="c710c-127">이 작업을 수행하고 있는 이유에 대한 추가</span><span class="sxs-lookup"><span data-stu-id="c710c-127">More on why we're doing this</span></span>

<span data-ttu-id="c710c-128">기본적으로 보안이 유지되는 것은 허용이 있었어도 악의적인 메시지를 차단할 경우 취할 수 있는 동일한 조치를 취하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-128">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even if there was an allow in place.</span></span> <span data-ttu-id="c710c-129">이 방법은 맬웨어에 사용한 방법과 동일하며, 이제 이 동작을 높은 신뢰도의 피싱 메시지로 확장하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-129">This is the same approach that we've used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span> <span data-ttu-id="c710c-130">이 데이터는 높은 신뢰도 피싱 메시지에 대한 가긍성 비율이 매우 낮고 관리자가 관리자 제출을 통해 가음성 문제를 해결할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-130">Our data indicates that the false positive rate for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span> <span data-ttu-id="c710c-131">또한 이 데이터에서는 스팸 방지 정책 및 Outlook의 수신 허용 도메인 목록 및 허용된 도메인 목록이 너무 광범위하여 양호한 것보다 더 많은 해를 줄 수 있는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-131">Our data also indicates that the allowed sender lists and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and causing more harm than good.</span></span>

<span data-ttu-id="c710c-132">이를 또 다른 방법으로 말해서, 보안 서비스로, 사용자가 손상되지 않도록 사용자를 대신하여 행동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-132">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> <span data-ttu-id="c710c-133">또한 기본적으로 보안은 스팸 방지 정책에서 높은 신뢰도의 피싱 메시지에 대해 사용 가능한 옵션을 완전하게 받아들이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-133">In addition, secure by default is not a full takeover of your available options for high confidence phishing messages in anti-spam policies.</span></span> <span data-ttu-id="c710c-134">항상 사용 가능한 다른 작업을 계속 사용할 수 있습니다(정크 메일 폴더로 이동 또는 전자 메일 주소로 리디렉션).</span><span class="sxs-lookup"><span data-stu-id="c710c-134">Although we recommend Quarantine, the other actions that have always been available are still available (Move to Junk Email folder or Redirect to an email address).</span></span>

## <a name="exceptions"></a><span data-ttu-id="c710c-135">예외</span><span class="sxs-lookup"><span data-stu-id="c710c-135">Exceptions</span></span>

<span data-ttu-id="c710c-136">높은 신뢰도의 피싱 메시지가 필터링을 무시할 수 있는 유일한 무시는 Exchange 메일 흐름 규칙(전송 규칙라고도 합니다.)입니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-136">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="c710c-137">메일 흐름 규칙을 사용하여 필터링을 무시하는 경우 메일 흐름 규칙을 사용하여 [메시지에 SCL을 설정하십시오.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c710c-137">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="c710c-138">다음과 같은 시나리오에서만 오버라이드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-138">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="c710c-139">피싱 시뮬레이션: 시뮬레이션된 공격은 실제 공격이 조직에 영향을 미치기 전에 취약한 사용자를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-139">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="c710c-140">Security/SecOps 사서함: 보안 팀에서 필터되지 않은 메시지를 받는 데 사용하는 전용 사서함(좋음 및 불량)</span><span class="sxs-lookup"><span data-stu-id="c710c-140">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="c710c-141">그런 다음 Teams는 악성 콘텐츠가 포함되어 있는지 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-141">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="c710c-142">타사 필터: 도메인의 MX 레코드가 Office 365를 지정하지 않는 경우 기본적으로 보안이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-142">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="c710c-143">가양성: 관리자 제출을 통해 Microsoft에서 여전히 분석하고 있는 특정 메시지를 일시적으로 [허용할 수 있습니다.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c710c-143">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="c710c-144">모든 재지정과 함께 임시로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c710c-144">As with all overrides, it is recommended that they are temporary.</span></span>
