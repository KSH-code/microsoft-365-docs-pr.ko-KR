---
title: 스팸 지수
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 관리자는 SCL (스팸 지 수)에 따라 메시지의 스팸이 얼마나 되는지 또는 발생할 가능성이 어떻게 결정 되는지, 스팸 필터링이 SCL을 기반으로 하는 메시지에 적용 되는 기본 작업에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 519bc48e7285283ad0570b8f3ac598615b132875
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638287"
---
# <a name="spam-confidence-level-scl-in-office-365"></a><span data-ttu-id="05a2a-103">Office 365의 SCL (스팸 지 수)</span><span class="sxs-lookup"><span data-stu-id="05a2a-103">Spam confidence level (SCL) in Office 365</span></span>

<span data-ttu-id="05a2a-104">Exchange Online 사서함 없이 Microsoft 365 (Exchange online 또는 독립 실행형 Exchange Online Protection (EOP)이 인바운드 전자 메일 메시지를 수신 하면 메시지는 스팸 필터링을 통과 하며 스팸 점수가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-104">When Microsoft 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) receives an inbound email message, the message goes through spam filtering, and is assigned a spam score.</span></span> <span data-ttu-id="05a2a-105">이 점수는 X-헤더의 메시지에 추가 된 개별 SCL (스팸 지 수)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="05a2a-106">SCL이 높을수록 메시지가 스팸으로 표시 되는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="05a2a-107">이 서비스는 SCL을 기반으로 메시지에 대해 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-107">The service takes action on the message based on the SCL.</span></span>

<span data-ttu-id="05a2a-108">SCL의 의미와 메시지에 대해 수행 되는 기본 작업에 대 한 설명은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="05a2a-109">스팸 필터링 결과을 기반으로 하는 메시지에 대해 수행할 수 있는 작업에 대 한 자세한 내용은 [Configure 스팸 방지 정책 Office 365](configure-your-spam-filter-policies.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="05a2a-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

||||
|:---:|---|---|
|<span data-ttu-id="05a2a-110">**SCL**</span><span class="sxs-lookup"><span data-stu-id="05a2a-110">**SCL**</span></span>|<span data-ttu-id="05a2a-111">**정의**</span><span class="sxs-lookup"><span data-stu-id="05a2a-111">**Definition**</span></span>|<span data-ttu-id="05a2a-112">**기본 작업**</span><span class="sxs-lookup"><span data-stu-id="05a2a-112">**Default action**</span></span>|
|<span data-ttu-id="05a2a-113">-1</span><span class="sxs-lookup"><span data-stu-id="05a2a-113">-1</span></span>|<span data-ttu-id="05a2a-114">메시지가 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-114">The message skipped spam filtering.</span></span> <span data-ttu-id="05a2a-115">예를 들어 수신 허용-보낸 사람에 게 전송 된 메시지 이거나, 수신 하는 전자 메일 서버에서 온 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="05a2a-116">자세한 내용은 [Office 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a2a-116">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="05a2a-117">받는 사람의 받은 편지 함으로 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="05a2a-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="05a2a-118">0, 1</span></span>|<span data-ttu-id="05a2a-119">스팸 필터링에서 메시지가 스팸으로 확인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="05a2a-120">받는 사람의 받은 편지 함으로 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="05a2a-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="05a2a-121">5, 6</span></span>|<span data-ttu-id="05a2a-122">스팸 필터링에서 메시지를 **스팸으로** 표시</span><span class="sxs-lookup"><span data-stu-id="05a2a-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="05a2a-123">받는 사람의 정크 메일 폴더로 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="05a2a-124">9 </span><span class="sxs-lookup"><span data-stu-id="05a2a-124">9</span></span>|<span data-ttu-id="05a2a-125">스팸 필터링에서 메시지가 **높은 신뢰도 스팸으로** 표시 됨</span><span class="sxs-lookup"><span data-stu-id="05a2a-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="05a2a-126">받는 사람의 정크 메일 폴더로 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="05a2a-127">SCL 2, 3, 4, 7, 8은 스팸 필터링에서 사용 되지 않는다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="05a2a-128">메일 흐름 규칙 (전송 규칙이 라고도 함)을 사용 하 여 메시지의 SCL을 스탬프 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="05a2a-129">메일 흐름 규칙을 사용 하 여 SCL을 설정 하는 경우 값 5 또는 6은 **스팸**에 대 한 스팸 필터링 작업을 트리거하고 값 7, 8 또는 9는 **신뢰도가 높은 스팸**에 대 한 스팸 필터링 작업을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="05a2a-130">자세한 내용은 [메일 흐름 규칙을 사용 하 여 메시지에서 SCL (스팸 지 수) 설정을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="05a2a-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="05a2a-131">SCL과 마찬가지로, BCL (bulk 불만 수준)은 잘못 된 대량 전자 메일 ( _회색 메일이_라고도 함)을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="05a2a-132">BCL이 많을 수록 대량 메일 메시지가 불만을 창출 하는 것 이며, 따라서 스팸으로 발생할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="05a2a-133">스팸 방지 정책에서 BCL 임계값을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="05a2a-134">자세한 내용은 [office 365에서 스팸 방지 정책 구성](configure-your-spam-filter-policies.md), [OFFICE 365의 BCL (대량 불만 수준)](bulk-complaint-level-values.md)및 [정크 메일 및 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a2a-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in Office 365)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

||
|:-----|
|<span data-ttu-id="05a2a-135">![LinkedIn Learning용 단축 아이콘](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365를 처음 사용하시나요?**</span><span class="sxs-lookup"><span data-stu-id="05a2a-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**</span></span>         <span data-ttu-id="05a2a-136">LinkedIn 학습을 통해 제공 되는 **Microsoft 365 관리자 및 IT 전문가**를 위한 무료 비디오 과정을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a2a-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
