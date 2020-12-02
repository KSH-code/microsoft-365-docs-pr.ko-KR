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
ms.openlocfilehash: 1a68c14a2d37f1fc3bfb032c4d3ca34c09a89890
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527772"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="2a884-103">Office 365에서 기본적으로 보안</span><span class="sxs-lookup"><span data-stu-id="2a884-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2a884-104">"기본적으로 보안"은 최대한 안전한 기본 설정을 정의 하는 데 사용 되는 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="2a884-105">그러나 보안을 생산성과 균형 있게 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="2a884-106">여기에는 다음과 같은 분산이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-106">This can include balancing across:</span></span>

- <span data-ttu-id="2a884-107">유용성: 설정이 사용자 생산성을 유지 하는 방식으로 제공 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="2a884-108">위험: 보안은 중요 한 작업을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="2a884-109">레거시 설정: 이전 제품 및 기능에 대 한 일부 구성은 새로운 최신 설정이 향상 되더라도 비즈니스 상의 이유로 유지 관리 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="2a884-110">Exchange Online 사서함이 있는 Microsoft 365 조직은 EOP (Exchange Online Protection)를 통해 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="2a884-111">이 보호에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-111">This protection includes:</span></span>

1. <span data-ttu-id="2a884-112">의심 스러운 맬웨어가 있는 전자 메일은 자동으로 격리 되 고 받는 사람에 게 알림이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="2a884-113">[EOP에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a884-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="2a884-114">"높은 신뢰도"로 식별 된 피싱 전자 메일은 스팸 방지 정책 작업에 따라 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="2a884-115">[EOP에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a884-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="2a884-116">Microsoft는 고객의 보안을 기본적으로 유지 하려고 하기 때문에 맬웨어 또는 높은 신뢰 피싱에 대해 일부 테 넌 트 재정의가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="2a884-117">이러한 재정의에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-117">These overrides include:</span></span>

- <span data-ttu-id="2a884-118">허용 된 보낸 사람 목록 또는 허용 된 도메인 목록 (스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="2a884-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="2a884-119">Outlook 수신 허용-보낸 사람</span><span class="sxs-lookup"><span data-stu-id="2a884-119">Outlook Safe senders</span></span>
- <span data-ttu-id="2a884-120">IP 허용 목록 (연결 필터링)</span><span class="sxs-lookup"><span data-stu-id="2a884-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="2a884-121">이러한 재정의에 대 한 자세한 내용은 [수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-121">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="2a884-122">기본적으로 보안은 설정 또는 해제할 수 있는 설정이 아니며, 필터링이 상자에서 작동 하 여 위험할 수도 있고 원치 않는 메시지를 사서함에서 제외 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="2a884-123">맬웨어 및 높은 신뢰도의 피싱이 격리로 전송 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-123">Malware and high confidence phishing should be sent to quarantine.</span></span> <span data-ttu-id="2a884-124">관리자만이 맬웨어 또는 높은 자신감 피싱 메일로 격리 된 메시지를 관리할 수 있으며, Microsoft에 가양성을 보고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="2a884-125">자세한 내용은 [격리 된 메시지 및 파일을 관리자 권한으로 EOP에서 관리](manage-quarantined-messages-and-files.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a884-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="2a884-126">예외</span><span class="sxs-lookup"><span data-stu-id="2a884-126">Exceptions</span></span>

<span data-ttu-id="2a884-127">높은 신뢰도 피싱 메시지는 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)은 필터링을 우회 하도록 허용 하는 유일한 재정의입니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-127">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="2a884-128">메일 흐름 규칙을 사용 하 여 필터링을 우회 하려면 [메일 흐름 규칙을 사용 하 여 메시지에 SCL을 설정](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)합니다 .를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2a884-128">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="2a884-129">재정의는 다음에 대해서만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-129">Overrides should only be used for:</span></span>

- <span data-ttu-id="2a884-130">피싱 시뮬레이션: 시뮬레이션 된 공격은 실제 공격이 조직에 영향을 미치는 경우 취약 한 사용자를 식별 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-130">Phishing simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="2a884-131">Security/SecOps 사서함: 보안 팀에서 필터링 되지 않은 메시지를 가져오는 데 사용 하는 전용 사서함입니다 (정상 및 불량).</span><span class="sxs-lookup"><span data-stu-id="2a884-131">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="2a884-132">그런 다음 팀이 악성 콘텐츠가 포함 되어 있는지 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-132">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="2a884-133">타사 필터: 타사 필터는 메일 필터링을 관리 하기 때문에 일부 타사 공급 업체는 EOP (SCL =-1)를 해제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-133">Third-party filters: some third-party vendors will recommend turning off EOP (SCL=-1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="2a884-134">Office 365 용 Defender에는 EOP as EOP이 필요 하므로이 기능을 해제 하는 것은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-134">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> <span data-ttu-id="2a884-135">대신 [커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-135">Instead, the recommendation here is to turn on [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) instead.</span></span>
- <span data-ttu-id="2a884-136">가양성: 여전히 [관리자 제출을 통해](admin-submission.md)Microsoft가 분석 중인 특정 메시지를 허용 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-136">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="2a884-137">모든 재정의와 마찬가지로 임시적으로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a884-137">As with all overrides, it is recommended that they are temporary.</span></span>
