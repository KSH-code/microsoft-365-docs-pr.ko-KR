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
description: 관리자는 EOP(Exchange Online Protection)에서 사용되는 BCL(대량 준수 수준) 값에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c68314cf992d39a105293955b6fade7b1a2bec56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289904"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="f9053-103">EOP의 BCL(대량 불만 수준)</span><span class="sxs-lookup"><span data-stu-id="f9053-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f9053-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f9053-104">**Applies to**</span></span>
- [<span data-ttu-id="f9053-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f9053-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f9053-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="f9053-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f9053-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9053-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f9053-108">Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 대량 메일러의 인바운드 메시지에 BCL(대량 규격 수준)을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="f9053-109">BCL은 X-헤더의 메시지에 추가된 후 메시지를 스팸으로 식별하는 데 사용되는 [SCL(스팸](spam-confidence-levels.md) 지수)과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="f9053-110">BCL이 높을수록 대량 메시지가 불만을 생성할 가능성이 높기 때문에 스팸일 가능성이 더 높음</span><span class="sxs-lookup"><span data-stu-id="f9053-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="f9053-111">Microsoft는 내부 및 타사 원본을 모두 사용하여 대량 메일을 식별하고 적절한 BCL을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="f9053-112">대량 메일러는 보내는 패턴, 콘텐츠 생성 및 받는 사람 취득 사례에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="f9053-113">대량 메일이 양호한 경우 구독자에게 관련 콘텐츠가 있는 원하는 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="f9053-114">이러한 메시지는 받는 사람으로부터 몇 가지 불만을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="f9053-115">다른 대량 메일러는 스팸과 매우 많고 받는 사람으로부터 많은 불만을 생성하는 원치 않는 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="f9053-116">대량 메일러의 메시지는 대량 메일 또는 회색 메일로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="f9053-117">스팸 필터링은 BCL  임계값(기본값 또는 지정한 값)에 따라 메시지를 대량 전자 메일로 표시하고 메시지에 대해 지정된 작업을 실행합니다(기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달).</span><span class="sxs-lookup"><span data-stu-id="f9053-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="f9053-118">자세한 내용은 스팸 [](configure-your-spam-filter-policies.md) 방지 정책 구성 및 정크 메일과 대량 전자 메일의 [차이점을 참조하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="f9053-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="f9053-119">BCL 임계값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="f9053-120">BCL</span><span class="sxs-lookup"><span data-stu-id="f9053-120">BCL</span></span>|<span data-ttu-id="f9053-121">설명</span><span class="sxs-lookup"><span data-stu-id="f9053-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="f9053-122">0</span><span class="sxs-lookup"><span data-stu-id="f9053-122">0</span></span>|<span data-ttu-id="f9053-123">메시지가 대량 보낸 사람이 아닌 경우</span><span class="sxs-lookup"><span data-stu-id="f9053-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="f9053-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="f9053-124">1, 2, 3</span></span>|<span data-ttu-id="f9053-125">이 메시지는 몇 가지 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="f9053-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f9053-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="f9053-127">이 메시지는 혼합된 불만 수를 생성하는 대량 보낸 사람이 보낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="f9053-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="f9053-128">8, 9</span></span>|<span data-ttu-id="f9053-129">이 메시지는 많은 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="f9053-130"><sup>\*</sup> 스팸 방지 정책에 사용되는 기본 임계값입니다.</span><span class="sxs-lookup"><span data-stu-id="f9053-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
