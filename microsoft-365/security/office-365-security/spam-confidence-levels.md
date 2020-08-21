---
title: 스팸 지수
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 메시지에 적용되는 SCL(스팸 지수)에 대해 자세히 알아보할 수 있습니다.
ms.openlocfilehash: 44687b8234e38e7f818aee908d1b65f382c908fe
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827400"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="c25ad-103">EOP의 SCL(스팸 지수)</span><span class="sxs-lookup"><span data-stu-id="c25ad-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="c25ad-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 인바운드 메시지는 EOP의 스팸 필터링을 통과하여 스팸 점수가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="c25ad-105">X-헤더의 메시지에 추가되는 개별 SCL(스팸 지수)에 매핑되는 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="c25ad-106">SCL이 높을수록 메시지가 스팸일 크기가 커집니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="c25ad-107">EOP는 SCL을 기반으로 메시지에 대해 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-107">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="c25ad-108">SCL의 의미와 메시지에 대해 수행되는 기본 작업은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="c25ad-109">스팸 필터링 필터에 따라 메시지에 대해 수행할 수 있는 작업에 대한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c25ad-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="c25ad-110">SCL</span><span class="sxs-lookup"><span data-stu-id="c25ad-110">SCL</span></span>|<span data-ttu-id="c25ad-111">정의</span><span class="sxs-lookup"><span data-stu-id="c25ad-111">Definition</span></span>|<span data-ttu-id="c25ad-112">기본 작업</span><span class="sxs-lookup"><span data-stu-id="c25ad-112">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="c25ad-113">-1</span><span class="sxs-lookup"><span data-stu-id="c25ad-113">-1</span></span>|<span data-ttu-id="c25ad-114">메시지가 스팸 필터링을 건너뛰어</span><span class="sxs-lookup"><span data-stu-id="c25ad-114">The message skipped spam filtering.</span></span> <span data-ttu-id="c25ad-115">예를 들어 Safe-SENDER FROM 의 메시지이거나 수신 허용 - 받는 사람에게 전송된 경우 또는 IP 허용 목록의 전자 메일 원본 서버에서 보내는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="c25ad-116">자세한 내용은 [EOP에서 수신 허용 - 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c25ad-116">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="c25ad-117">메시지를 받는 사람의 받은 편지함에 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="c25ad-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="c25ad-118">0, 1</span></span>|<span data-ttu-id="c25ad-119">스팸 필터링을 통해 메시지가 스팸이 아오지 않았음을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="c25ad-120">메시지를 받는 사람의 받은 편지함에 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="c25ad-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="c25ad-121">5, 6</span></span>|<span data-ttu-id="c25ad-122">메시지가 스팸으로 표시됨 스팸 **필터링**</span><span class="sxs-lookup"><span data-stu-id="c25ad-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="c25ad-123">메시지를 받는 사람의 정크 메일 폴더로 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="c25ad-124">9 </span><span class="sxs-lookup"><span data-stu-id="c25ad-124">9</span></span>|<span data-ttu-id="c25ad-125">스팸 필터링 결과 메시지를 높은 **신뢰도의 스팸으로 표시**</span><span class="sxs-lookup"><span data-stu-id="c25ad-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="c25ad-126">메시지를 받는 사람의 정크 메일 폴더로 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="c25ad-127">SCL 2, 3, 4, 7, 8은 스팸 필터링에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="c25ad-128">메일 흐름 규칙(전송 규칙이라고도 함)을 사용하여 SCL을 메시지에 스탬프 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="c25ad-129">메일 흐름 규칙을 사용하여 SCL을 설정하는 경우 값 5 또는 6은 스팸에 대한 스팸 필터링 작업을 **트리거하고,** 7, 8 또는 9는 높은 스팸 지수에 대한 스팸 필터링 **작업을 트리거합니다.**</span><span class="sxs-lookup"><span data-stu-id="c25ad-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="c25ad-130">자세한 내용은 메일 [흐름 규칙을 사용하여 메시지의 스팸 신뢰 수준(SCL)을 설정하는 방법을 참조하세요.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c25ad-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="c25ad-131">SCL과 마찬가지로 BCL(대량 호환 수준)은 대량 전자 메일(회색 메일이라고도 _함)을 식별합니다._</span><span class="sxs-lookup"><span data-stu-id="c25ad-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="c25ad-132">BCL이 높다는 것은 대량 메일 메시지가 위조를 생성할 가능성이 높다는 것을 의미합니다(그러기도 하다점).</span><span class="sxs-lookup"><span data-stu-id="c25ad-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="c25ad-133">스팸 방지 정책에서 BCL 임계값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c25ad-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="c25ad-134">자세한 내용은 [EOP에서 스팸 방지 정책 구성, EOP의](configure-your-spam-filter-policies.md) [BCL(대량 비정신 수준)](bulk-complaint-level-values.md)및 정크 메일과 대량 전자 메일의 차이점은 [무엇인가요?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="c25ad-134">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

|<!-- -->|
|---|
|<span data-ttu-id="c25ad-135">![LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New의** 짧은 아이콘</span><span class="sxs-lookup"><span data-stu-id="c25ad-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="c25ad-136">LinkedIn Learning에서 **제공한 Microsoft 365 admins and IT pros의**무료 비디오 과정을 확인해보세요.</span><span class="sxs-lookup"><span data-stu-id="c25ad-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
