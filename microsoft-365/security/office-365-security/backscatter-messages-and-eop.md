---
title: EOP의 후방 산란
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 백 분산 및 Microsoft EOP (Exchange Online Protection)에 대해 설명 합니다.
ms.openlocfilehash: 2a752c89e2430f24441d14178942b89362736322
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203590"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="f2436-103">EOP의 후방 산란</span><span class="sxs-lookup"><span data-stu-id="f2436-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f2436-104">*Backscatter* 은 보내지 않은 메시지에 대해 수신 하는 배달 못 함 보고서 (ndr 또는 바운스 메시지)입니다.</span><span class="sxs-lookup"><span data-stu-id="f2436-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="f2436-105">스팸 발송자가 메시지의 보낸 사람: 주소를 위조 하 고, 실제 전자 메일 주소를 사용 하 여 메시지에 대 한 신뢰성을 전송 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f2436-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="f2436-106">따라서 스팸 발송자가 보낸 사람이 존재 하지 않는 받는 사람에 게 메시지를 보내는 경우 (스팸을 사용 하는 경우), 대상 전자 메일 서버가 본질적으로 NDR에 배달할 수 없는 메시지를 From: 주소에 있는 위조 된 보낸 사람에 게 반환 tricked 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2436-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="f2436-107">Exchange online 사서함이 없는 Microsoft 365의 EOP (exchange online Protection) 조직에 사서함이 EOP에서는 NDR을 생성 하지 않고 dubious 원본에서 메시지를 식별 하 고 자동으로 삭제 하기 위한 모든 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2436-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="f2436-108">그러나 서비스를 통해 전달 되는 양은 대량 전자 메일을 기반으로 EOP에서 실수로 산을 보낼 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2436-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="f2436-109">Backscatterer.org에서는 백 산 발송을 담당 하는 전자 메일 서버의 차단 목록 (DNS 차단 목록 또는 DNSBL이 라고도 함)을 유지 관리 하 고이 목록에 EOP 서버를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2436-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="f2436-110">그러나 Backscatterer.org 차단 목록에서 본인을 제거 하지는 않습니다 (자체 허용).</span><span class="sxs-lookup"><span data-stu-id="f2436-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="f2436-111">Backscatter.org website ( <http://www.backscatterer.org/?target=usage> )는 서비스를 사용 하 여 거부 모드 대신 안전 모드에서 들어오는 전자 메일을 확인 하는 것이 좋습니다 (대규모 전자 메일 서비스는 거의 모든 백 분산을 보내는 경우).</span><span class="sxs-lookup"><span data-stu-id="f2436-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
