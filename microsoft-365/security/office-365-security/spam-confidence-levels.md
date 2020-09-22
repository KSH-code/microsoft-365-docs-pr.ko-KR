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
description: 관리자는 EOP (Exchange Online Protection)에서 메시지에 적용 되는 SCL (스팸 지 수)에 대해 알아봅니다.
ms.openlocfilehash: fbd892b0171cee71f516d7ca3b26b91da664af79
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202236"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="24834-103">EOP의 SCL (스팸 지 수)</span><span class="sxs-lookup"><span data-stu-id="24834-103">Spam confidence level (SCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="24834-104">Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (독립 실행형 Exchange Online Protection) 조직에서 인바운드 메시지는 EOP의 스팸 필터링을 통해 수행 되며 스팸 점수가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24834-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="24834-105">이 점수는 X-헤더의 메시지에 추가 된 개별 SCL (스팸 지 수)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="24834-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="24834-106">SCL이 높을수록 메시지가 스팸으로 표시 되는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="24834-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="24834-107">EOP는 SCL을 기반으로 메시지에 대해 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="24834-107">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="24834-108">SCL의 의미와 메시지에 대해 수행 되는 기본 작업에 대 한 설명은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24834-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="24834-109">스팸 필터링 결과을 기반으로 하는 메시지에 대해 수행할 수 있는 작업에 대 한 자세한 내용은 [Configure 스팸 방지 정책 EOP](configure-your-spam-filter-policies.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="24834-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="24834-110">SCL</span><span class="sxs-lookup"><span data-stu-id="24834-110">SCL</span></span>|<span data-ttu-id="24834-111">정의</span><span class="sxs-lookup"><span data-stu-id="24834-111">Definition</span></span>|<span data-ttu-id="24834-112">기본 작업</span><span class="sxs-lookup"><span data-stu-id="24834-112">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="24834-113">-1</span><span class="sxs-lookup"><span data-stu-id="24834-113">-1</span></span>|<span data-ttu-id="24834-114">메시지가 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="24834-114">The message skipped spam filtering.</span></span> <span data-ttu-id="24834-115">예를 들어 수신 허용-보낸 사람에 게 전송 된 메시지 이거나, 수신 하는 전자 메일 서버에서 온 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="24834-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="24834-116">자세한 내용은 [EOP에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="24834-116">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="24834-117">받는 사람의 받은 편지 함으로 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="24834-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="24834-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="24834-118">0, 1</span></span>|<span data-ttu-id="24834-119">스팸 필터링에서 메시지가 스팸으로 확인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="24834-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="24834-120">받는 사람의 받은 편지 함으로 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="24834-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="24834-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="24834-121">5, 6</span></span>|<span data-ttu-id="24834-122">스팸 필터링에서 메시지를 **스팸으로** 표시</span><span class="sxs-lookup"><span data-stu-id="24834-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="24834-123">받는 사람의 정크 메일 폴더로 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="24834-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="24834-124">9 </span><span class="sxs-lookup"><span data-stu-id="24834-124">9</span></span>|<span data-ttu-id="24834-125">스팸 필터링에서 메시지가 **높은 신뢰도 스팸으로** 표시 됨</span><span class="sxs-lookup"><span data-stu-id="24834-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="24834-126">받는 사람의 정크 메일 폴더로 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="24834-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="24834-127">SCL 2, 3, 4, 7, 8은 스팸 필터링에서 사용 되지 않는다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24834-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="24834-128">메일 흐름 규칙 (전송 규칙이 라고도 함)을 사용 하 여 메시지의 SCL을 스탬프 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24834-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="24834-129">메일 흐름 규칙을 사용 하 여 SCL을 설정 하는 경우 값 5 또는 6은 **스팸**에 대 한 스팸 필터링 작업을 트리거하고 값 7, 8 또는 9는 **신뢰도가 높은 스팸**에 대 한 스팸 필터링 작업을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="24834-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="24834-130">자세한 내용은 [메일 흐름 규칙을 사용 하 여 메시지에서 SCL (스팸 지 수) 설정을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="24834-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="24834-131">SCL과 마찬가지로, BCL (bulk 불만 수준)은 잘못 된 대량 전자 메일 ( _회색 메일이_라고도 함)을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="24834-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="24834-132">BCL이 높을수록 대량 메일 메시지가 불만을 발생시킬 가능성이 높으므로 스팸일 가능성이 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="24834-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="24834-133">스팸 방지 정책에서 BCL 임계값을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="24834-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="24834-134">자세한 내용은 [EOP에서 스팸 방지 정책 구성](configure-your-spam-filter-policies.md), [EOP의 BCL (대량 불만 수준](bulk-complaint-level-values.md)) 및 [정크 메일 및 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24834-134">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

|<!-- -->|
|---|
|<span data-ttu-id="24834-135">![LinkedIn에 대 한 짧은 아이콘은 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365를 처음으로 학습 하나요?**</span><span class="sxs-lookup"><span data-stu-id="24834-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="24834-136">LinkedIn 학습을 통해 제공 되는 **Microsoft 365 관리자 및 IT 전문가**를 위한 무료 비디오 과정을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="24834-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
