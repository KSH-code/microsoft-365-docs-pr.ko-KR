---
title: IPv6을 통한 익명 인바운드 전자 메일 지원 추가
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 IPv6 원본의 익명 인바운드 전자 메일에 대한 지원을 구성하는 방법을 Exchange Online Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80fdcc9dcfe3006ef8b21aa19856fe8c0ea3ff70
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300052"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="2cc1c-103">IPv6을 통해 익명 인바운드 전자 메일에 대한 지원을 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2cc1c-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2cc1c-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="2cc1c-104">**Applies to**</span></span>
- [<span data-ttu-id="2cc1c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2cc1c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2cc1c-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="2cc1c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2cc1c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2cc1c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2cc1c-108">Microsoft 365 사서함이 없는 Exchange Online 및 EOP(독립 실행형 Exchange Online Protection) 조직이 Exchange Online IPv6을 통해 익명 인바운드 전자 메일을 지원하는 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="2cc1c-109">원본 IPv6 전자 메일 서버는 다음 요구 사항을 모두 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="2cc1c-110">원본 IPv6 주소에는 대상이 IPv6 주소에서 도메인 이름을 찾을 수 있는 유효한 PTR(역방향 DNS 검색) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="2cc1c-111">보낸 사람은 [RFC 7208](https://tools.ietf.org/html/rfc7208)에 정의되어 있는 SPF 확인 또는 [RFC 6376](http://dkim.org/)에 정의되어 있는 [DKIM 확인](https://www.rfc-editor.org/rfc/rfc6376.txt)을 통과해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="2cc1c-112">조직에서 IPv6을 통해 익명 인바운드 전자 메일을 받으기 전에 관리자는 Microsoft 지원에 문의하여 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="2cc1c-113">지원 요청을 여는 방법에 대한 자세한 내용은 비즈니스 제품에 대한 고객 지원 [문의 - 관리자 도움말을 참조하세요.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="2cc1c-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../business-video/get-help-support.md).</span></span>

<span data-ttu-id="2cc1c-114">조직에서 익명 인바운드 IPv6 메시지 지원이 사용하도록 설정되면 해당 메시지는 서비스에서 제공하는 일반 메시지 필터링을 거치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2cc1c-115">문제 해결</span><span class="sxs-lookup"><span data-stu-id="2cc1c-115">Troubleshooting</span></span>

- <span data-ttu-id="2cc1c-116">원본 전자 메일 서버에 IPv6 역방향 DNS 코드 레코드가 없는 경우 다음 오류와 함께 메시지가 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="2cc1c-117">450 4.7.25 서비스를 사용할 수 없거나 IPv6 주소 보내기[2a01:111:f200:2004::240]에 역방향 DNS 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="2cc1c-118">보낸 사람이 SPF 또는 DKIM 유효성 검사를 통과하지 못하면 다음 오류와 함께 메시지가 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="2cc1c-119">450 4.7.26 서비스를 사용할 수 없음, IPv6을 통해 전송된 메시지[2a01:111:f200:2004::240]은 SPF 또는 DKIM 유효성 검사를 통과해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="2cc1c-120">옵트인하기 전에 익명 IPv6 메시지를 받으려고 하면 다음 오류와 함께 메시지가 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="2cc1c-121">550 5.2.1 서비스를 사용할 수 없음, [contoso.com]는 IPv6을 통해 전자 메일을 수락하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc1c-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2cc1c-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2cc1c-122">Related topics</span></span>

[<span data-ttu-id="2cc1c-123">DKIM으로 서명된 메시지의 유효성 검사 지원</span><span class="sxs-lookup"><span data-stu-id="2cc1c-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
