---
title: 외부 전자 메일 전달, 자동 전달, 5.7.520 액세스 거부, 외부 전달을 사용 하지 않도록 설정, 관리자가 외부 전달을 사용 하지 않도록 설정, 아웃 바운드 스팸 방지 정책
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 59e2c938c70dd8e3060fd85d084acbe8f79856ad
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806631"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="a91ba-103">Microsoft 365에서 자동 외부 전자 메일 전달 제어</span><span class="sxs-lookup"><span data-stu-id="a91ba-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a91ba-104">관리자는 외부의 받는 사람 (조직 외부의 받는 사람)에 게 자동으로 전달 되는 메시지를 제한 하거나 제어 하기 위한 회사 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="a91ba-105">전자 메일 전달은 유용할 수 있지만 정보 공개로 인 한 보안 위험을 초래할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="a91ba-106">공격자는이 정보를 사용 하 여 조직이 나 파트너를 공격할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="a91ba-107">Microsoft 365에서는 다음과 같은 자동 전달 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="a91ba-108">사용자는 외부의 보낸 사람에 게 메시지를 자동으로 전달 하는 [받은 편지함 규칙](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 을 구성할 수 있습니다 (고의적으로 또는 손상 된 계정의 결과로).</span><span class="sxs-lookup"><span data-stu-id="a91ba-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="a91ba-109">관리자는 [사서함 전달](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) ( _SMTP 전달_ 도 함)을 구성 하 여 메시지를 외부 받는 사람에 게 자동으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_ ) to automatically forward messages to external recipients.</span></span>

<span data-ttu-id="a91ba-110">아웃 바운드 스팸 필터 정책을 사용 하 여 외부의 받는 사람에 대 한 자동 전달을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-110">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="a91ba-111">다음과 같은 세 가지 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-111">Three settings are available:</span></span>

- <span data-ttu-id="a91ba-112">**자동** : 자동 외부 전달이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-112">**Automatic** : Automatic external forwarding is blocked.</span></span> <span data-ttu-id="a91ba-113">내부 자동 메시지 전달은 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-113">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="a91ba-114">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-114">This is the default setting.</span></span>

- <span data-ttu-id="a91ba-115">**켜기** : 자동 외부 전달은 허용 되며 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-115">**On** : Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="a91ba-116">**Off** : 자동 외부 전달이 사용 하지 않도록 설정 되며 보낸 사람에 게 배달 못 함 보고서 (NDR 또는 바운스 메시지가 라고도 함)가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-116">**Off** : Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="a91ba-117">이러한 설정을 구성 하는 방법에 대 한 지침은 [EOP에서 아웃 바운드 스팸 필터링 구성을](configure-the-outbound-spam-policy.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a91ba-117">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="a91ba-118">자동 전달을 사용 하지 않도록 설정 하면 메시지를 외부 주소로 리디렉션하는 모든 받은 편지함 규칙 (사용자) 또는 관리자 (사서함 전달)가 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-118">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
> 
> - <span data-ttu-id="a91ba-119">내부 사용자 간에 메시지를 자동으로 전달 하는 것은 아웃 바운드 스팸 필터 정책의 설정에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-119">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
> 
> - <span data-ttu-id="a91ba-120">[자동 전달 메시지 보고서](mfi-auto-forwarded-messages-report.md)에서 외부의 받는 사람에 게 메시지를 자동으로 전달 하는 사용자에 대 한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-120">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="a91ba-121">아웃 바운드 스팸 필터 정책 설정이 다른 자동 전자 메일 전달 컨트롤에서 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="a91ba-121">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="a91ba-122">관리자는 자동 전자 메일 전달을 허용 하거나 차단 하도록 다른 컨트롤을 이미 구성 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-122">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="a91ba-123">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="a91ba-123">For example:</span></span>

- <span data-ttu-id="a91ba-124">일부 또는 모든 외부 도메인에 대 한 자동 전자 메일 전달을 허용 하거나 차단 하기 위한 [원격 도메인](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains)</span><span class="sxs-lookup"><span data-stu-id="a91ba-124">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="a91ba-125">Exchange [메일 흐름 규칙](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 의 조건 및 작업 (전송 규칙이 라고도 함)은 자동으로 전달 되는 메시지를 검색 하 고 외부 받는 사람에 게 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-125">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="a91ba-126">원격 도메인 설정 및 메일 흐름 규칙은 아웃 바운드 스팸 필터 정책의 설정과 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-126">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="a91ba-127">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="a91ba-127">For example:</span></span>

- <span data-ttu-id="a91ba-128">원격 도메인에 대해 자동 전달을 허용 하지만 아웃 바운드 스팸 필터 정책의 자동 전달을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-128">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="a91ba-129">이 예에서는 자동 전달 메시지가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-129">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="a91ba-130">아웃 바운드 스팸 필터 정책에서 자동 전달을 허용 하지만 메일 흐름 규칙 또는 원격 도메인 설정을 사용 하 여 자동으로 전달 되는 전자 메일을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-130">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="a91ba-131">이 예에서는 메일 흐름 규칙 또는 원격 도메인 설정이 자동 전달 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-131">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="a91ba-132">이 기능 독립성은 아웃 바운드 스팸 필터 정책에서 자동 전달을 허용 하지만 원격 도메인을 사용 하 여 사용자가 메시지를 전달할 수 있는 외부 도메인을 제어 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-132">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="a91ba-133">차단 된 전자 메일 전달 메시지</span><span class="sxs-lookup"><span data-stu-id="a91ba-133">The blocked email forwarding message</span></span>

<span data-ttu-id="a91ba-134">메시지가 자동으로 전달 되는 것으로 감지 되 고 조직 정책에서 해당 작업을 *차단* 하면 해당 메시지는 다음 정보가 포함 된 NDR의 보낸 사람에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91ba-134">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
