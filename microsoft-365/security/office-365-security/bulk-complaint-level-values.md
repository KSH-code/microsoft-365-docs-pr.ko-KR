---
title: 대량 부상 수준 값
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection)에서 사용되는 BCL(대량 준수 수준) 값에 대해 자세히 배우할 수 있습니다.
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827436"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="46b6b-103">EOP의 BCL(대량 부과 수준)</span><span class="sxs-lookup"><span data-stu-id="46b6b-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="46b6b-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 대량 메일러의 인바운드 메시지에 BCL(대량 준수 수준)을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="46b6b-105">BCL은 X-헤더의 메시지에 추가되며 메시지를 스팸으로 식별하는 데 사용되는 [SCL(스팸 지수)과](spam-confidence-levels.md) 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="46b6b-106">BCL이 높다는 것은 대량 메시지가 위조를 생성할 수 있음을 의미합니다(그러기도 하다점).</span><span class="sxs-lookup"><span data-stu-id="46b6b-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="46b6b-107">Microsoft는 내부 및 타사 원본을 둘 다 사용하여 대량 메일을 식별하고 해당 BCL을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="46b6b-108">메일 대량 메일은 송신 패턴, 콘텐츠 생성, 받는 사람 취득 관행에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="46b6b-109">양질 메일 러스터는 관련 내용이 있는 원하는 메시지를 구독자에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="46b6b-110">이러한 메시지는 받는 사람이 몇 가지 일만할 수 있는 사서함 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="46b6b-111">다른 대량 메일러는 스팸과 비밀히 유사한 원치 않는 메시지를 보내고 받는 사람이 많은 위한 문제를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="46b6b-112">대량 메일러에서 보낸 메시지를 대량 메일 또는 회색 메일이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="46b6b-113">스팸 필터링은 BCL **Bulk email** 임계값(지정한 값 또는 값)을 기준으로 메시지를 대량 전자 메일로 표시하고 메시지에 대해 지정된 작업을 수행합니다(기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달됨).</span><span class="sxs-lookup"><span data-stu-id="46b6b-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="46b6b-114">자세한 내용은 [스팸 방지 정책 구성 및 정크](configure-your-spam-filter-policies.md) 메일과 [대량 전자 메일의 차이점을 확인하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="46b6b-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="46b6b-115">BCL 임계값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-115">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="46b6b-116">BCL</span><span class="sxs-lookup"><span data-stu-id="46b6b-116">BCL</span></span>|<span data-ttu-id="46b6b-117">설명</span><span class="sxs-lookup"><span data-stu-id="46b6b-117">Description</span></span>|
|:---:|---|
|<span data-ttu-id="46b6b-118">0</span><span class="sxs-lookup"><span data-stu-id="46b6b-118">0</span></span>|<span data-ttu-id="46b6b-119">이 메시지는 대량 메일로 보낸 사람이 보낸 것이 아없습니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="46b6b-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="46b6b-120">1, 2, 3</span></span>|<span data-ttu-id="46b6b-121">몇 가지 만한 추가 정보가 생성되는 대량의 보낸 사람이 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="46b6b-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="46b6b-122">4, 5, 6, 7</span></span>|<span data-ttu-id="46b6b-123">"사서함"에 대한 메시지는 혼합 수의 위만을 생성하는 대량 메일보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="46b6b-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="46b6b-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="46b6b-124">8, 9</span></span>|<span data-ttu-id="46b6b-125">수량의 수의 문제를 일체하는 대량 메일 보낸 사람이 메시지를 받은 경우</span><span class="sxs-lookup"><span data-stu-id="46b6b-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
