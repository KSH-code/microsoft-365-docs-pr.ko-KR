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
description: EOP (Exchange Online Protection)의 보안 강화 설정에 대 한 자세한 정보
ms.openlocfilehash: 54000d351463ba90751f1f27638fb52847cf05ce
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558517"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="00434-103">Office 365에서 기본적으로 보안</span><span class="sxs-lookup"><span data-stu-id="00434-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="00434-104">"기본적으로 보안"은 최대한 안전한 기본 설정을 정의 하는 데 사용 되는 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="00434-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="00434-105">그러나 보안을 생산성과 균형 있게 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00434-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="00434-106">여기에는 다음과 같은 분산이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-106">This can include balancing across:</span></span>

- <span data-ttu-id="00434-107">**유용성**: 설정이 사용자 생산성을 유지 하는 방식으로 제공 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00434-107">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="00434-108">**위험**: 보안은 중요 한 작업을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-108">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="00434-109">**레거시 설정**: 이전 제품 및 기능에 대 한 일부 구성은 새로운 최신 설정이 향상 되더라도 비즈니스 상의 이유로 유지 관리 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-109">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="00434-110">Exchange Online 사서함이 있는 Microsoft 365 조직은 EOP (Exchange Online Protection)를 통해 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00434-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="00434-111">이 보호에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00434-111">This protection includes:</span></span>

- <span data-ttu-id="00434-112">의심 스러운 맬웨어가 있는 전자 메일은 자동으로 격리 되 고 받는 사람에 게 알림이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00434-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="00434-113">[EOP에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00434-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="00434-114">높은 신뢰도의 피싱 메일로 확인 된 전자 메일은 스팸 방지 정책 작업에 따라 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00434-114">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="00434-115">[EOP에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00434-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="00434-116">Microsoft는 고객의 보안을 기본적으로 유지 하려고 하기 때문에 맬웨어 또는 높은 신뢰 피싱에 대해 일부 테 넌 트 재정의가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="00434-117">이러한 재정의에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00434-117">These overrides include:</span></span>

- <span data-ttu-id="00434-118">허용 된 보낸 사람 목록 또는 허용 된 도메인 목록 (스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="00434-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="00434-119">Outlook 수신 허용-보낸 사람</span><span class="sxs-lookup"><span data-stu-id="00434-119">Outlook Safe Senders</span></span>
- <span data-ttu-id="00434-120">IP 허용 목록 (연결 필터링)</span><span class="sxs-lookup"><span data-stu-id="00434-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="00434-121">이러한 재정의에 대 한 자세한 내용은 [수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-121">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="00434-122">보안은 기본적으로 설정 하거나 해제할 수 있는 설정이 아니며, 필터링이 사용자의 위험 또는 원치 않는 메시지를 사서함 외부로 보호 하기 위해 상자에서 작동 하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="00434-122">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="00434-123">맬웨어 및 높은 신뢰도 피싱 메시지를 격리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00434-123">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="00434-124">관리자만이 맬웨어 또는 높은 신뢰도 피싱 메일로 격리 된 메시지를 관리할 수 있으며 여기에서 가양성을 Microsoft에 보고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-124">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="00434-125">자세한 내용은 [격리 된 메시지 및 파일을 관리자 권한으로 EOP에서 관리](manage-quarantined-messages-and-files.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00434-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="00434-126">이 작업을 수행 하는 이유에 대 한 자세한 내용을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="00434-126">More on why we're doing this</span></span>

<span data-ttu-id="00434-127">기본적으로 안전 하다 고 생각 하는 것은 현재 위치에 있더라도 메시지를 악의적으로 알고 있는 경우에도 메시지에 대해 동일한 작업을 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00434-127">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even if there was an allow in place.</span></span> <span data-ttu-id="00434-128">이 방법은 맬웨어에 사용한 것과 동일한 방식으로, 이제 높은 신뢰도 피싱 메시지에 대해 이와 동일한 동작을 확장 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00434-128">This is the same approach that we've used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span> <span data-ttu-id="00434-129">이 데이터는 신뢰도가 높은 피싱 메시지에 대 한 가양성 비율이 매우 낮은 것을 나타내며 관리자는 관리자 제출을 통해 가양성을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-129">Our data indicates that the false positive rate for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span> <span data-ttu-id="00434-130">또한이 데이터는 스팸 방지 정책 및 Outlook의 수신 허용-보낸 사람 목록과 허용 되는 도메인 목록이 너무 광범위 하 여 더 많은 피해를 야기 한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00434-130">Our data also indicates that the allowed sender lists and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and causing more harm than good.</span></span>

<span data-ttu-id="00434-131">또 다른 방법으로, 보안 서비스의 역할을 하는 것 이므로 사용자가 공격에 노출 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-131">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> <span data-ttu-id="00434-132">또한 기본적으로 보안은 스팸 방지 정책에서 높은 신뢰도 피싱 메시지에 사용할 수 있는 옵션의 전체 인수 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="00434-132">In addition, secure by default is not a full takeover of your available options for high confidence phishing messages in anti-spam policies.</span></span> <span data-ttu-id="00434-133">격리를 권장 하지만, 항상 사용할 수 있는 다른 작업은 여전히 사용할 수 있습니다 (정크 메일 폴더로 이동 하거나 전자 메일 주소로 리디렉션).</span><span class="sxs-lookup"><span data-stu-id="00434-133">Although we recommend Quarantine, the other actions that have always been available are still available (Move to Junk Email folder or Redirect to an email address).</span></span>

## <a name="exceptions"></a><span data-ttu-id="00434-134">예외</span><span class="sxs-lookup"><span data-stu-id="00434-134">Exceptions</span></span>

<span data-ttu-id="00434-135">높은 신뢰도 피싱 메시지는 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)은 필터링을 우회 하도록 허용 하는 유일한 재정의입니다.</span><span class="sxs-lookup"><span data-stu-id="00434-135">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="00434-136">메일 흐름 규칙을 사용 하 여 필터링을 우회 하려면 [메일 흐름 규칙을 사용 하 여 메시지에 SCL을 설정](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)합니다 .를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00434-136">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="00434-137">다음과 같은 시나리오에서는 재정의를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-137">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="00434-138">피싱 시뮬레이션: 시뮬레이션 된 공격은 실제 공격이 조직에 영향을 미치는 경우 취약 한 사용자를 식별 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-138">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="00434-139">Security/SecOps 사서함: 보안 팀에서 필터링 되지 않은 메시지를 가져오는 데 사용 하는 전용 사서함입니다 (정상 및 불량).</span><span class="sxs-lookup"><span data-stu-id="00434-139">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="00434-140">그런 다음 팀이 악성 콘텐츠가 포함 되어 있는지 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-140">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="00434-141">타사 필터: 타사 필터는 메일 필터링을 관리 하기 때문에 일부 타사 공급 업체는 EOP (SCL =-1)를 해제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-141">Third-party filters: Some third-party vendors will recommend turning off EOP (SCL=-1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="00434-142">Office 365 용 Defender에는 EOP as EOP이 필요 하므로이 기능을 해제 하는 것은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-142">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> <span data-ttu-id="00434-143">대신 [커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-143">Instead, the recommendation here is to turn on [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>
- <span data-ttu-id="00434-144">가양성: [관리자 제출을 통해](admin-submission.md)여전히 Microsoft가 분석 중인 특정 메시지를 일시적으로 허용 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-144">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="00434-145">모든 재정의와 마찬가지로 임시적으로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00434-145">As with all overrides, it is recommended that they are temporary.</span></span>
