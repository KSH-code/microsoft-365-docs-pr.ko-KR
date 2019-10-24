---
title: 대량 불만 수준 값, 대량 메일, BCL 수준, BCL works, BCL 등급, 스팸 방지, 스팸 방지 헤더, 대량 메일 필터링, 대량 메일 중지
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: Office 365의 BCL (대량 확인 수준) 값에 대해 알아봅니다.
ms.openlocfilehash: 822c84ea9b36cfdae1d8faccf7e0c7d9f747c917
ms.sourcegitcommit: 7830969c8fa41724359657910716f3ce312cc2cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2019
ms.locfileid: "37650120"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="36569-103">대량 불만 수준 값</span><span class="sxs-lookup"><span data-stu-id="36569-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="36569-104">대량 메일 발송은 해당 보내는 패턴, 콘텐츠 작성 및 목록 가져오기 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="36569-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="36569-105">일부는 관련 콘텐츠가 포함 된 메시지를 구독자에 게 보내는 좋은 대량 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="36569-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="36569-106">이러한 메시지는 받는 사람의 불만을 거의 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="36569-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="36569-107">기타 대량 메일 전송 스팸과 유사한 원치 않는 메시지를 보내며 받는 사람 으로부터 많은 불만을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="36569-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="36569-108">이러한 유형의 대량 메일을 구별 하기 위해 대량 우편물의 메시지에 BCL (대량 불만 수준) 등급이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36569-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="36569-109">BCL 등급은 대량 메일에 불만을 생성 하기 위해 얼마나 큰 지에 따라 1에서 9 사이의 범위를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="36569-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="36569-110">BCL 9의 등급이 있는 보낸 사람은 받는 사람에 게 많은 불만을 생성할 수 있는 반면, BCL 3의 등급은 많은 불만을 생성할 가능성이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="36569-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="36569-111">Microsoft에서는 내부 및 타사 소스를 모두 사용 하 여 대량 메일을 식별 하 고 적절 한 BCL을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36569-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="36569-112">이 메시지 헤더에 대 한 자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36569-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="36569-113">등급이 9 인 대량 메일 발송은 불만을 창출 하기 때문에 기본 BCL은 7입니다.</span><span class="sxs-lookup"><span data-stu-id="36569-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="36569-114">즉, 그 이후에는 불만 수준이 7이 고 메일이 수락 되지 않을 때까지 대량 메일이 수락 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36569-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="36569-115">등급이 낮을수록 대량 메일이 더 적게 수락 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36569-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="36569-116">사용자가 있고, 대량 메일을 구분 하 고, BCL을 4로 설정 하는 경우에는 4 보다 더 높은 BCL을 사용 하는 대량 메일이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36569-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="36569-117">BCL 값을 사용 하 여 조직에서 필요한 대량 필터링 수준을 설정 하려면 [스팸 필터 정책 구성](configure-your-spam-filter-policies.md)의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="36569-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="36569-118">다음 표에는 현재 사용 중인 BCL 값에 대 한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36569-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="36569-119">**BCL 값**</span><span class="sxs-lookup"><span data-stu-id="36569-119">**BCL Value**</span></span>|<span data-ttu-id="36569-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="36569-120">**Description**</span></span>|
|<span data-ttu-id="36569-121">개</span><span class="sxs-lookup"><span data-stu-id="36569-121">0</span></span>|<span data-ttu-id="36569-122">메시지가 대량 보낸 사람 으로부터 온 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="36569-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="36569-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="36569-123">1, 2, 3</span></span>|<span data-ttu-id="36569-124">메시지가 몇 가지 불만을 생성 하는 대량 보낸 사람의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="36569-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="36569-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="36569-125">4, 5, 6, 7</span></span>|<span data-ttu-id="36569-126">이 메시지는 수많은 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="36569-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="36569-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="36569-127">8, 9</span></span>|<span data-ttu-id="36569-128">이 메시지는 많은 수의 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="36569-128">The message is from a bulk sender that generates a high number of complaints.</span></span>|
