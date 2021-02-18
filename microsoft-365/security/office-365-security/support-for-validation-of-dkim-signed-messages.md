---
title: DKIM(Domain Keys Identified Mail) 서명된 메시지의 유효성 검사 지원
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Exchange Online Protection 및 Exchange Online에서 DKIM 서명된 메시지의 유효성 검사에 대해 자세히
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9da41cc7918b36e1aa6a4a8cc48aea6cd2a865c6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290264"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="e6f02-103">DKIM으로 서명된 메시지의 유효성 검사 지원</span><span class="sxs-lookup"><span data-stu-id="e6f02-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e6f02-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="e6f02-104">**Applies to**</span></span>
- [<span data-ttu-id="e6f02-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e6f02-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e6f02-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="e6f02-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e6f02-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6f02-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e6f02-108">EOP(Exchange Online Protection) 및 Exchange Online은[모두 DKIM(Domain](https://www.rfc-editor.org/rfc/rfc6376.txt)Keys Identified Mail) 메시지의 인바운드 유효성 검사를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="e6f02-109">DKIM은 다른 사람이 전자 메일  메시지를 스푸핑하지 않은 것으로 확인한 후  보낸 도메인에서 전송된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="e6f02-110">전자 메일 메시지를 보낸 조직에 링크합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="e6f02-111">DKIM 확인은 IPv6으로 전송된 모든 메시지에 자동으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="e6f02-112">Microsoft 365는 IPv4를 통해 메일을 보낼 때 DKIM도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="e6f02-113">IPv6 지원에 대한 자세한 내용은 [IPv6을](support-for-anonymous-inbound-email-messages-over-ipv6.md)통해 익명 인바운드 전자 메일 메시지 지원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6f02-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="e6f02-114">DKIM은 메시지 헤더의 DKIM-Signature 디지털 서명된 메시지의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="e6f02-115">테스트 유효성 검사의 DKIM-Signature 스탬프가 Authentication-Results 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="e6f02-116">메시지 헤더 텍스트는 다음과 유사합니다(여기서 contoso.com 보낸 사람).</span><span class="sxs-lookup"><span data-stu-id="e6f02-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="e6f02-117">Authentication-Results 대한 자세한 내용은 RFC 7001(메시지 인증 상태를 나타내는 메시지 헤더 필드)을[참조하십시오.](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="e6f02-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="e6f02-118">Microsoft의 DKIM 구현은 이 RFC를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="e6f02-119">관리자는 DKIM 유효성 검사 결과에 [대해](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Exchange 메일 흐름 규칙(전송 규칙)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-119">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="e6f02-120">이러한 메일 흐름 규칙을 통해 관리자는 필요한 경우 메시지를 필터링하거나 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6f02-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
