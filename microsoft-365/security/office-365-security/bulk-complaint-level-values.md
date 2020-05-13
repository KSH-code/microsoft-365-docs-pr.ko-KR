---
title: 대량 불만 수준 값
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 관리자는 EOP (Exchange Online Protection)에서 사용 되는 BCL (대량 준수 수준) 값에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209610"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="88572-103">EOP의 BCL (대량 불만 수준)</span><span class="sxs-lookup"><span data-stu-id="88572-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="88572-104">Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (exchange online Protection) 조직에 사서함이 대량 우편물의 인바운드 메시지에 대 한 BCL (대량 준수 수준)을 할당 EOP.</span><span class="sxs-lookup"><span data-stu-id="88572-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="88572-105">BCL은 X-헤더의 메시지에 추가 되며 메시지를 스팸으로 식별 하는 데 사용 되는 [SCL (스팸](spam-confidence-levels.md) 지 수)과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="88572-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="88572-106">BCL이 높을수록 대량 메시지가 불만을 더 많이 창출 하 게 되며, 따라서 스팸으로 발생할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="88572-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="88572-107">Microsoft에서는 내부 및 타사 소스를 모두 사용 하 여 대량 메일을 식별 하 고 적절 한 BCL을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88572-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="88572-108">대량 메일 발송은 해당 보내는 패턴, 콘텐츠 만들기 및 받는 사람 가져오기 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="88572-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="88572-109">좋은 대량 메일 보낸 사람에 게 관련 콘텐츠가 포함 된 원하는 메시지를 구독자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="88572-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="88572-110">이러한 메시지는 받는 사람의 불만을 거의 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="88572-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="88572-111">기타 대량 메일 전송 스팸과 유사한 원치 않는 메시지를 보내며 받는 사람 으로부터 많은 불만을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="88572-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="88572-112">대량 메일 프로그램에서 보내는 메시지를 bulk mail 또는 회색 메일 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="88572-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="88572-113">스팸 필터링은 메시지를 BCL 임계값 (기본값 또는 지정한 값)을 기반으로 **대량 전자 메일로** 표시 하 고 메시지에 대해 지정 된 작업을 수행 합니다 (기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달 됨).</span><span class="sxs-lookup"><span data-stu-id="88572-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="88572-114">자세한 내용은 [스팸 방지 정책 구성](configure-your-spam-filter-policies.md) 및 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88572-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="88572-115">다음 표에는 BCL 임계값에 대 한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88572-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="88572-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="88572-116">**BCL**</span></span>|<span data-ttu-id="88572-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="88572-117">**Description**</span></span>|
|<span data-ttu-id="88572-118">개</span><span class="sxs-lookup"><span data-stu-id="88572-118">0</span></span>|<span data-ttu-id="88572-119">메시지가 대량 보낸 사람 으로부터 온 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="88572-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="88572-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="88572-120">1, 2, 3</span></span>|<span data-ttu-id="88572-121">메시지가 몇 가지 불만을 생성 하는 대량 보낸 사람의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="88572-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="88572-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="88572-122">4, 5, 6, 7</span></span>|<span data-ttu-id="88572-123">이 메시지는 수많은 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88572-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="88572-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="88572-124">8, 9</span></span>|<span data-ttu-id="88572-125">이 메시지는 많은 수의 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88572-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
