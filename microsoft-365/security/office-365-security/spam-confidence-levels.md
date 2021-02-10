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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)의 메시지에 적용된 SCL(스팸 지수)에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167158"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="116ad-103">EOP의 SCL(스팸 지수)</span><span class="sxs-lookup"><span data-stu-id="116ad-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="116ad-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="116ad-104">**Applies to**</span></span>
- [<span data-ttu-id="116ad-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="116ad-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="116ad-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="116ad-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="116ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="116ad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="116ad-108">Exchange Online 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 사서함이 있는 Microsoft 365 조직에서 인바운드 메시지는 EOP의 스팸 필터링을 통과하고 스팸 점수가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="116ad-109">이 점수는 X-헤더의 메시지에 추가된 개별 SCL(스팸 지수)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="116ad-110">SCL이 높을수록 메시지가 스팸일 가능성이 더 높을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="116ad-111">EOP는 SCL에 따라 메시지에 대한 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="116ad-112">다음 표에는 SCL의 의미와 메시지에 대해 수행되는 기본 작업이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="116ad-113">스팸 필터링 판정에 따라 메시지에 대해 수행할 수 있는 작업에 대한 자세한 내용은 EOP에서 스팸 방지 정책 구성을 [참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="116ad-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="116ad-114">SCL</span><span class="sxs-lookup"><span data-stu-id="116ad-114">SCL</span></span>|<span data-ttu-id="116ad-115">정의</span><span class="sxs-lookup"><span data-stu-id="116ad-115">Definition</span></span>|<span data-ttu-id="116ad-116">기본 작업</span><span class="sxs-lookup"><span data-stu-id="116ad-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="116ad-117">-1</span><span class="sxs-lookup"><span data-stu-id="116ad-117">-1</span></span>|<span data-ttu-id="116ad-118">메시지가 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-118">The message skipped spam filtering.</span></span> <span data-ttu-id="116ad-119">예를 들어 수신 허용 - 보낸 사람이 보낸 메시지, 수신 허용 - 받는 사람에게 전송된 메시지 또는 IP 허용 목록의 전자 메일 원본 서버에서 보낸 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="116ad-120">자세한 내용은 [EOP에서 수신이 가능한 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="116ad-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="116ad-121">받는 사람의 받은 편지함으로 메시지를 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="116ad-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="116ad-122">0, 1</span></span>|<span data-ttu-id="116ad-123">스팸 필터링에서 메시지가 스팸이 아닌 것으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="116ad-124">받는 사람의 받은 편지함으로 메시지를 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="116ad-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="116ad-125">5, 6</span></span>|<span data-ttu-id="116ad-126">스팸 필터링에서 메시지를 스팸으로 **표시**</span><span class="sxs-lookup"><span data-stu-id="116ad-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="116ad-127">받는 사람의 정크 메일 폴더로 메시지를 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="116ad-128">9 </span><span class="sxs-lookup"><span data-stu-id="116ad-128">9</span></span>|<span data-ttu-id="116ad-129">스팸 필터링에서 메시지를 높은 신뢰도 **스팸으로 표시**</span><span class="sxs-lookup"><span data-stu-id="116ad-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="116ad-130">받는 사람의 정크 메일 폴더로 메시지를 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="116ad-131">SCL 2, 3, 4, 7 및 8은 스팸 필터링에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="116ad-132">메일 흐름 규칙(전송 규칙)을 사용하여 메시지에 SCL 스탬프 처리를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="116ad-133">메일 흐름 규칙을 사용하여 SCL을 설정하는 경우 값 5 또는 6은 스팸에 대한 스팸 필터링 작업을 트리거하고 값 7, 8 또는 9는 높은 신뢰도 스팸에 대한 스팸 필터링 작업을 트리거합니다. </span><span class="sxs-lookup"><span data-stu-id="116ad-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="116ad-134">자세한 내용은 메일 흐름 규칙을 사용하여 메시지의 [SCL(스팸 지수)을 설정하세요.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="116ad-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="116ad-135">SCL과 유사하게 BCL(대량 불만 수준)은 잘못된 대량 전자 메일(회색 메일)을 _식별합니다._</span><span class="sxs-lookup"><span data-stu-id="116ad-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="116ad-136">BCL이 높을수록 대량 메일 메시지가 불만을 발생시킬 가능성이 높으므로 스팸일 가능성이 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="116ad-137">스팸 방지 정책에서 BCL 임계값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="116ad-138">자세한 내용은 [EOP에서](configure-your-spam-filter-policies.md)스팸 방지 정책 구성, [EOP의 BCL(대량](bulk-complaint-level-values.md)불만 수준) 및 정크 메일과 대량 전자 메일의 차이점을 [참조하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="116ad-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="116ad-139">![](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365의** 새로운 LinkedIn Learning에 대한 짧은 아이콘이 있나요?</span><span class="sxs-lookup"><span data-stu-id="116ad-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="116ad-140">LinkedIn Learning에서 제공한 **Microsoft 365** 관리자 및 IT pros를 위한 무료 비디오 과정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="116ad-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
