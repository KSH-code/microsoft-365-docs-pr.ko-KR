---
title: IPv6을 통한 익명 인바운드 전자 메일 지원 추가
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 Exchange Online 및 Exchange Online Protection의 IPv6 원본에서 익명 인바운드 전자 메일 지원을 구성하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 7384c1044cc02ec20079dc03068c2ca99e68d2c2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826780"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="d9619-103">Microsoft 365에서 IPv6을 통한 익명 인바운드 전자 메일 지원 추가</span><span class="sxs-lookup"><span data-stu-id="d9619-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="d9619-104">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직과 Microsoft 365 조직은 IPv6을 통한 익명 인바운드 전자 메일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="d9619-105">원본 IPv6 전자 메일 서버는 다음 요구 사항을 모두 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="d9619-106">원본 IPv6 주소에는 대상에서 IPv6 주소의 도메인 이름을 찾을 수 있도록 하는 유효한 PTR(역방향 DNS 조회) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="d9619-107">보낸 사람은 [RFC 7208](https://tools.ietf.org/html/rfc7208)에 정의되어 있는 SPF 확인 또는 [RFC 6376](https://dkim.org/)에 정의되어 있는 [DKIM 확인](https://www.rfc-editor.org/rfc/rfc6376.txt)을 통과해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="d9619-108">조직에서 IPv6을 통해 익명 인바운드 전자 메일을 받으려면 관리자가 Microsoft 지원 센터에 문의하여 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="d9619-109">지원 요청을 여는 방법에 대한 지침은 비즈니스 제품에 [대한 고객 지원에 문의 - 관리자 도움말을 참조하세요.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="d9619-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="d9619-110">조직에서 익명 인바운드 IPv6 메시지 지원을 사용하도록 설정하면 메시지는 서비스에서 제공한 일반 메시지 필터링을 거치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d9619-111">문제 해결</span><span class="sxs-lookup"><span data-stu-id="d9619-111">Troubleshooting</span></span>

- <span data-ttu-id="d9619-112">원본 전자 메일 서버에 역방향 DNS 조회 레코드가 없으면 메시지가 거부되며 다음 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="d9619-113">450 4.7.25 서비스를 사용할 수 없습니다. 송신 IPv6 주소 [2a01:111:f200:2004::240]에 역방향 DNS 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="d9619-114">보낸 사람이 SPF 또는 DKIM 유효성 검사를 통과하지 못하면 메시지가 거부됩니다. 이 오류는 배달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="d9619-115">450 4.7.26 서비스를 사용할 수 없음, IPv6을 통해 전송된 메시지 [2a01:111:f200:2004::240]가 SPF 또는 DKIM 유효성 검사를 통과해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="d9619-116">옵트인하기 전에 익명 IPv6 메시지를 받으하려고 하면 다음 오류와 함께 메시지가 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="d9619-117">550 5.2.1 서비스를 사용할 수 없음, [contoso.com]은 IPv6을 통한 전자 메일을 수락하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9619-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9619-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d9619-118">Related topics</span></span>

[<span data-ttu-id="d9619-119">DKIM으로 서명된 메시지의 유효성 검사 지원</span><span class="sxs-lookup"><span data-stu-id="d9619-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)