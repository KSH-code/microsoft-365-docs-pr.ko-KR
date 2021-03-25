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
description: 이 문서에서는 후방산자 및 EOP(후방 보호)에 Microsoft Exchange Online 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205112"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="48b8d-103">EOP의 후방 산란</span><span class="sxs-lookup"><span data-stu-id="48b8d-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="48b8d-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="48b8d-104">**Applies to**</span></span>
- [<span data-ttu-id="48b8d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="48b8d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="48b8d-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="48b8d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="48b8d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48b8d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="48b8d-108">*후방산은* 보내지 않은 메시지에 대해 수신하는 배달 못지 않은 보고서(NDRs 또는 반송 메시지라고도 알려지기)입니다.</span><span class="sxs-lookup"><span data-stu-id="48b8d-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="48b8d-109">스팸 발송자는 메시지의 보낸 사람: 주소를 위조(스푸핑)하며 메시지에 대한 신뢰성을 제공하기 위해 실제 전자 메일 주소를 사용하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="48b8d-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="48b8d-110">따라서 스패머가 존재하지 않는 받는 사람에게 메시지를 불가피하게 보내는 경우(스팸은 대량의 작업임) 대상 전자 메일 서버는 기본적으로 NDR에서 배달할 수 없는 메시지를 보낸 사람: 주소의 위조된 보낸 사람에게 반환하는 속임수입니다.</span><span class="sxs-lookup"><span data-stu-id="48b8d-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="48b8d-111">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 NDR을 생성하지 않고도 의심스러운 원본에서 메시지를 식별하고 자동으로 삭제하기 위해 노력합니다.</span><span class="sxs-lookup"><span data-stu-id="48b8d-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="48b8d-112">그러나 서비스를 통해 흐르는 전방 볼륨 전자 메일에 따라 EOP에서 의도치 않은 후방 메일을 보낼 가능성이 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48b8d-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="48b8d-113">Backscatterer.org 후방산 전송을 담당하는 전자 메일 서버의 차단 목록(DNS 차단 목록 또는 DNSBL)을 유지 관리하며 EOP 서버가 이 목록에 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48b8d-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="48b8d-114">그러나 스태머 목록이 아니기 때문에(자신의 입장에 따라) Backscatterer.org 차단 목록에서 제거하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48b8d-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="48b8d-115">Backscatter.org 웹 사이트( )는 서비스를 사용하여 거부 모드(대규모 전자 메일 서비스에서 거의 항상 일부 후방산을 보내는) 대신 수신 전자 메일을 안전한 모드로 검사하는 <http://www.backscatterer.org/?target=usage> 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="48b8d-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
