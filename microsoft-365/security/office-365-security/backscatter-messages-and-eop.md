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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 후방산자 및 EOP(Microsoft Exchange Online 보호)에 대해 자세히 알아보게 될 것입니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286972"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="b0c9a-103">EOP의 후방 산란</span><span class="sxs-lookup"><span data-stu-id="b0c9a-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b0c9a-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="b0c9a-104">**Applies to**</span></span>
- [<span data-ttu-id="b0c9a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b0c9a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b0c9a-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="b0c9a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b0c9a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0c9a-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b0c9a-108">*후방산은* 보내지 않은 메시지에 대해 수신하는 배달 못지 않은 보고서(NDRS 또는 반송 메시지라고도 합니다.)입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c9a-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="b0c9a-109">스팸 발송자(스푸핑)는 메시지의 보낸사용자: 주소를위조(스푸핑)하며, 종종 실제 전자 메일 주소를 사용하여 메시지에 신뢰성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c9a-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="b0c9a-110">따라서 스패머가 존재하지 않는 받는 사람에게 메시지를 보낼 수 없는 경우(스팸은 대량의 작업임) 대상 전자 메일 서버는 기본적으로 NDR에서 배달할 수 없는 메시지를 보낸 사람: 주소의 위조된 보낸 사람에게 반환하는 속임수입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c9a-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="b0c9a-111">Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 NDR을 생성하지 않고도 의심스러운 원본에서 메시지를 식별하고 자동으로 삭제하기 위해 모든 노력을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c9a-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="b0c9a-112">그러나 서비스를 통해 흐르는 볼륨 전자 메일에 따라 EOP가 의도치 않은 후방 메일을 보낼 가능성이 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c9a-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="b0c9a-113">Backscatterer.org 전송을 담당하는 전자 메일 서버의 차단 목록(DNS 차단 목록 또는 DNSBL)을 유지 관리하고 EOP 서버가 이 목록에 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c9a-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="b0c9a-114">그러나 스태머 목록이 아니기 때문에 (자신의 입장에서) Backscatterer.org 차단 목록에서 제거하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c9a-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="b0c9a-115">Backscatter.org 웹 사이트()는 서비스를 사용하여 거부 모드 대신 수신 전자 메일을 안전한 모드로 검사하는 것이 좋습니다(대규모 전자 메일 서비스는 거의 항상 일부 후방산을 <http://www.backscatterer.org/?target=usage> 전송).</span><span class="sxs-lookup"><span data-stu-id="b0c9a-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
