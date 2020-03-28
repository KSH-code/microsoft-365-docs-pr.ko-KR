---
title: 대량 불만 수준 값, 대량 메일, BCL 수준, BCL works, BCL 등급, 스팸 방지, 스팸 방지 헤더, 대량 메일 필터링, 대량 메일 중지
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Office 365의 BCL (대량 준수 수준) 값에 대해 알아봅니다.
ms.openlocfilehash: aa839fc1bcab141fe71c76e7f27b4f6bb23048b2
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030155"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="67bc5-103">Office 365의 BCL (대량 불만 수준)</span><span class="sxs-lookup"><span data-stu-id="67bc5-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="67bc5-104">대량 메일 발송은 해당 보내는 패턴, 콘텐츠 만들기 및 받는 사람 가져오기 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="67bc5-105">일부는 필요한 메시지를 구독자에 게 관련 콘텐츠와 함께 전송 하는 좋은 대량 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="67bc5-106">이러한 메시지는 받는 사람의 불만을 거의 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="67bc5-107">기타 대량 메일 전송 스팸과 유사한 원치 않는 메시지를 보내며 받는 사람 으로부터 많은 불만을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="67bc5-108">대량 메일 프로그램에서 보내는 메시지를 bulk mail 또는 회색 메일 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="67bc5-109">서로 다른 유형의 대량 메일 메일과 메시지를 구별 하기 위해 Exchange Online 사서함을 사용 하지 않고 Exchange Online 또는 독립 실행형 Exchange Online Protection (EOP) 365에 대량 우편물을 전송 하는 경우 인바운드 전자 메일이 추가 된 BCL (대량 불만 수준)에 할당 됩니다. X-헤더에 있는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers to Office 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="67bc5-110">BCL은 메시지를 스팸으로 식별 하는 데 사용 되는 [SCL (스팸](spam-confidence-levels.md) 지 수)과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="67bc5-111">BCL이 높을수록 대량 메시지가 불만을 더 많이 창출 하 게 되며, 따라서 스팸으로 발생할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="67bc5-112">Microsoft에서는 내부 및 타사 소스를 모두 사용 하 여 대량 메일을 식별 하 고 적절 한 BCL을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="67bc5-113">스팸 필터링은 메시지를 BCL 임계값 (기본값 또는 지정한 값)을 기반으로 **대량 전자 메일로** 표시 하 고 메시지에 대해 지정 된 작업을 수행 합니다 (기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달 됨).</span><span class="sxs-lookup"><span data-stu-id="67bc5-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="67bc5-114">자세한 내용은 [Office 365에서 스팸 방지 정책 구성](configure-your-spam-filter-policies.md) 및 [정크 메일 및 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67bc5-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="67bc5-115">다음 표에는 BCL 임계값에 대 한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="67bc5-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="67bc5-116">**BCL**</span></span>|<span data-ttu-id="67bc5-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="67bc5-117">**Description**</span></span>|
|<span data-ttu-id="67bc5-118">개</span><span class="sxs-lookup"><span data-stu-id="67bc5-118">0</span></span>|<span data-ttu-id="67bc5-119">메시지가 대량 보낸 사람 으로부터 온 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="67bc5-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="67bc5-120">1, 2, 3</span></span>|<span data-ttu-id="67bc5-121">메시지가 몇 가지 불만을 생성 하는 대량 보낸 사람의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="67bc5-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="67bc5-122">4, 5, 6, 7</span></span>|<span data-ttu-id="67bc5-123">이 메시지는 수많은 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="67bc5-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="67bc5-124">8, 9</span></span>|<span data-ttu-id="67bc5-125">이 메시지는 많은 수의 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67bc5-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
