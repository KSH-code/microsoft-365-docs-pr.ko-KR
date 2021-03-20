---
title: 외부 전자 메일 전달 구성 및 제어, 자동 전달, 5.7.520 액세스 거부, 외부 전달을 사용하지 않도록 설정, 관리자가 외부 전달, 아웃바운드 스팸 방지 정책을 사용하지 않도록 설정했습니다.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4614fc9661c892457800b70e2f04f577b418b417
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910777"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="b42c0-103">Microsoft 365에서 자동 외부 전자 메일 전달 제어</span><span class="sxs-lookup"><span data-stu-id="b42c0-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b42c0-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="b42c0-104">**Applies to**</span></span>
- [<span data-ttu-id="b42c0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b42c0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b42c0-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="b42c0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b42c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b42c0-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b42c0-108">관리자는 외부 받는 사람(조직 외부의 받는 사람)에게 자동으로 전달되는 메시지를 제한하거나 제어해야 하는 회사 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="b42c0-109">전자 메일 전달은 유용할 수 있지만 잠재적인 정보 공개로 인해 보안 위험이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="b42c0-110">공격자는 이 정보를 사용하여 조직 또는 파트너를 공격할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="b42c0-111">Microsoft 365에서는 다음과 같은 유형의 자동 전달을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="b42c0-112">사용자는 받은 [](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 편지함 규칙을 구성하여 메시지를 외부 보낸 사람(고의적으로 또는 계정이 손상된 결과)에게 자동으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="b42c0-113">관리자는 외부 [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) 받는 사람에게 메시지를 자동으로 전달하도록 사서함 _전달(SMTP_ 전달)을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="b42c0-114">관리자는 단순히 메시지를 전달할지 또는 사서함에 전달된 메시지의 복사본을 보관할지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="b42c0-115">아웃바운드 스팸 필터 정책을 사용하여 외부 받는 사람에게 자동 전달을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="b42c0-116">세 가지 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-116">Three settings are available:</span></span>

- <span data-ttu-id="b42c0-117">**자동:** 자동 외부 전달이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="b42c0-118">메시지의 내부 자동 전달은 계속 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="b42c0-119">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-119">This is the default setting.</span></span>
- <span data-ttu-id="b42c0-120">**On:** 자동 외부 전달이 허용되고 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="b42c0-121">**Off:** 자동 외부 전달이 사용하지 않도록 설정되어 있으며 보낸 사람에 대한 배달되지 않는 보고서(NDR 또는 반송 메시지라고도 알려지음)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="b42c0-122">이러한 설정을 구성하는 방법에 대한 지침은 [EOP에서 아웃바운드 스팸 필터링 구성을 참조하세요.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="b42c0-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b42c0-123">자동 전달을 사용하지 않도록 설정하면 메시지를 외부 주소로 리디렉션하는 받은 편지함 규칙(사용자) 또는 사서함 전달(관리자)을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="b42c0-124">내부 사용자 간의 메시지 자동 전달은 아웃바운드 스팸 필터 정책의 설정에 의해 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="b42c0-125">자동 전달 메시지 보고서에서 외부 받는 사람에게 메시지를 자동으로 전달하는 사용자에 대한 정보를 볼 [수 있습니다.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="b42c0-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="b42c0-126">아웃바운드 스팸 필터 정책 설정이 다른 자동 전자 메일 전달 컨트롤에서 작동되는 방식</span><span class="sxs-lookup"><span data-stu-id="b42c0-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="b42c0-127">관리자는 자동 전자 메일 전달을 허용하거나 차단하도록 다른 컨트롤을 이미 구성한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="b42c0-128">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-128">For example:</span></span>

- <span data-ttu-id="b42c0-129">[일부 또는](/exchange/mail-flow-best-practices/remote-domains/remote-domains) 모든 외부 도메인으로 자동 전자 메일 전달을 허용하거나 차단하는 원격 도메인</span><span class="sxs-lookup"><span data-stu-id="b42c0-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="b42c0-130">[외부](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 받는 사람에게 자동으로 전달되는 메시지를 검색하고 차단하기 위해 Exchange 메일 흐름 규칙의 조건 및 작업(전송 규칙)입니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="b42c0-131">원격 도메인 설정 및 메일 흐름 규칙은 아웃바운드 스팸 필터 정책의 설정과 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="b42c0-132">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-132">For example:</span></span>

- <span data-ttu-id="b42c0-133">원격 도메인에 대해 자동 전달을 허용하지만 아웃바운드 스팸 필터 정책에서 자동 전달을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="b42c0-134">이 예에서는 자동으로 전달된 메시지가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="b42c0-135">아웃바운드 스팸 필터 정책에서 자동 전달을 허용하지만 메일 흐름 규칙 또는 원격 도메인 설정을 사용하여 자동으로 전달되는 전자 메일을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="b42c0-136">이 예에서는 메일 흐름 규칙 또는 원격 도메인 설정이 자동으로 전달되는 메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="b42c0-137">이 기능을 독립적으로 사용하면 아웃바운드 스팸 필터 정책에서 자동 전달을 허용하지만 원격 도메인을 사용하여 사용자가 메시지를 전달할 수 있는 외부 도메인을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42c0-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="b42c0-138">차단된 전자 메일 전달 메시지</span><span class="sxs-lookup"><span data-stu-id="b42c0-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="b42c0-139">메시지가 자동으로 전달된 것으로 감지되고 아웃바운드 스팸  필터 정책이 해당 활동을 차단하면 다음 정보가 포함된 NDR의 보낸 사람에 메시지가 반환됩니다. [](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="b42c0-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`