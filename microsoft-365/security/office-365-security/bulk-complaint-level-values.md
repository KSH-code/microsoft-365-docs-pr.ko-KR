---
title: 대량 불만 수준 값
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(대량 불만 수준)에 사용되는 BCL(대량 불만 수준) 값에 대해 Exchange Online Protection 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537946"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="c76a9-103">EOP의 BCL(대량 불만 수준)</span><span class="sxs-lookup"><span data-stu-id="c76a9-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c76a9-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="c76a9-104">**Applies to**</span></span>
- [<span data-ttu-id="c76a9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c76a9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c76a9-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="c76a9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c76a9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c76a9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c76a9-108">Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection)에 사서함이 있는 Exchange Online 조직에서 EOP는 대량 메일러의 인바운드 메시지에 BCL(대량 불만 수준)을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk complaint level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="c76a9-109">BCL은 X-헤더의 메시지에 추가된 후 메시지를 스팸으로 식별하는 데 사용되는 [SCL(스팸](spam-confidence-levels.md) 지수)과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="c76a9-110">BCL이 높을수록 대량 메시지가 불만을 생성할 가능성이 높기 때문에 스팸일 가능성이 더 높을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="c76a9-111">Microsoft는 내부 및 타사 소스를 모두 사용하여 대량 메일을 식별하고 적절한 BCL을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="c76a9-112">대량 메일은 보내는 패턴, 콘텐츠 생성 및 받는 사람 취득 관행에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="c76a9-113">양호한 대량 메일러는 구독자에게 관련 콘텐츠가 있는 원하는 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="c76a9-114">이러한 메시지는 받는 사람으로부터 몇 가지 불만을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="c76a9-115">다른 대량 메일러는 스팸과 매우 많고 받는 사람으로부터 많은 불만을 생성하는 원치 않는 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="c76a9-116">대량 메일러의 메시지는 대량 메일 또는 회색 메일로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="c76a9-117">스팸 필터링은 BCL  임계값(지정한 값)을 기준으로 메시지를 대량 전자 메일로 표시하고 메시지에 대해 지정된 작업을 실행합니다(기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달).</span><span class="sxs-lookup"><span data-stu-id="c76a9-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="c76a9-118">자세한 내용은 [스팸](configure-your-spam-filter-policies.md) 방지 정책 구성 및 정크 메일과 대량 전자 메일의 [차이점을 참조하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="c76a9-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="c76a9-119">테넌트 허용/차단 목록을 사용하여 대량 메일 필터링에 대한 예외를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-119">You can use the Tenant Allow/Block List to configure exceptions for bulk mail filtering.</span></span> <span data-ttu-id="c76a9-120">지정된 도메인의 보낸 사람이 보낸 메시지는 스팸 방지  정책에서 대량 전자 메일 스팸 필터링 판정에 대한 작업을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-120">Messages from senders in the specified domains don't receive the action for the **Bulk email** spam filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="c76a9-121">자세한 내용은 [테넌트 허용/차단 목록 관리를 참조하세요.](tenant-allow-block-list.md)</span><span class="sxs-lookup"><span data-stu-id="c76a9-121">For more information, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

<span data-ttu-id="c76a9-122">BCL 임계값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-122">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="c76a9-123">BCL</span><span class="sxs-lookup"><span data-stu-id="c76a9-123">BCL</span></span>|<span data-ttu-id="c76a9-124">설명</span><span class="sxs-lookup"><span data-stu-id="c76a9-124">Description</span></span>|
|:---:|---|
|<span data-ttu-id="c76a9-125">0</span><span class="sxs-lookup"><span data-stu-id="c76a9-125">0</span></span>|<span data-ttu-id="c76a9-126">메시지가 대량 보낸 사람이 아닌 경우</span><span class="sxs-lookup"><span data-stu-id="c76a9-126">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="c76a9-127">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="c76a9-127">1, 2, 3</span></span>|<span data-ttu-id="c76a9-128">이 메시지는 몇 가지 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-128">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="c76a9-129">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c76a9-129">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="c76a9-130">이 메시지는 불만이 혼합된 수의 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-130">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="c76a9-131">8, 9</span><span class="sxs-lookup"><span data-stu-id="c76a9-131">8, 9</span></span>|<span data-ttu-id="c76a9-132">이 메시지는 많은 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-132">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="c76a9-133"><sup>\*</sup> 스팸 방지 정책에 사용되는 기본 임계값입니다.</span><span class="sxs-lookup"><span data-stu-id="c76a9-133"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
