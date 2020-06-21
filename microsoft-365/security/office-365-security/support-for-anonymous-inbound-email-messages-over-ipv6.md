---
title: IPv6을 통한 익명 인바운드 전자 메일 지원 추가
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 Exchange Online 및 Exchange Online Protection에서 IPv6 원본의 익명 인바운드 전자 메일에 대 한 지원을 구성 하는 방법을 알 수 있습니다.
ms.openlocfilehash: fbbcba3631c7b2a7060f07011c119ee973fdf4af
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818712"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="b3d0e-103">Microsoft 365에서 i p v 6을 통한 익명 인바운드 전자 메일 지원 추가</span><span class="sxs-lookup"><span data-stu-id="b3d0e-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="b3d0e-104">Exchange online 사서함 및 독립 실행형 EOP (Exchange Online Protection)가 포함 된 Microsoft 365 조직에서 온-IPv6을 통한 익명 인바운드 전자 메일을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="b3d0e-105">원본 IPv6 전자 메일 서버는 다음 요구 사항을 모두 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="b3d0e-106">원본 IPv6 주소에는 대상에서 IPv6 주소 로부터 도메인 이름을 찾을 수 있도록 하는 유효한 PTR (역방향 DNS 조회) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="b3d0e-107">보낸 사람은 [RFC 7208](https://tools.ietf.org/html/rfc7208)에 정의되어 있는 SPF 확인 또는 [RFC 6376](https://dkim.org/)에 정의되어 있는 [DKIM 확인](https://www.rfc-editor.org/rfc/rfc6376.txt)을 통과해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="b3d0e-108">조직이 i p v 6을 통해 익명 인바운드 전자 메일을 수신 하기 전에 관리자가 Microsoft 지원에 문의 하 여 도움을 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="b3d0e-109">지원 요청을 여는 방법에 대 한 자세한 내용은 [비즈니스 제품에 대 한 지원 문의-관리자 도움말](../../admin/contact-support-for-business-products.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="b3d0e-110">조직에서 익명 인바운드 IPv6 메시지 지원을 사용 하도록 설정한 후에는 메시지가 서비스에서 제공 하는 일반 메시지 필터링을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b3d0e-111">문제 해결</span><span class="sxs-lookup"><span data-stu-id="b3d0e-111">Troubleshooting</span></span>

- <span data-ttu-id="b3d0e-112">원본 전자 메일 서버에 IPv6 역방향 DNS 조회 레코드가 없으면 다음 오류가 발생 하 여 메시지가 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="b3d0e-113">450 4.7.25 서비스를 사용할 수 없음, 전송 IPv6 주소 [2a01:111: f200:2004:: 240]에 역방향 DNS 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="b3d0e-114">보낸 사람이 SPF 또는 DKIM 유효성 검사를 통과 하지 못하면 다음 오류가 발생 하 여 메시지가 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="b3d0e-115">450 4.7.26 서비스를 사용할 수 없음, IPv6을 통해 전송 되는 메시지는 SPF 또는 DKIM 유효성 검사를 통과 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="b3d0e-116">옵트인 하기 전에 익명 IPv6 메시지를 수신 하려고 하면 다음 오류와 함께 메시지가 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="b3d0e-117">550 5.2.1 서비스를 사용할 수 없음 [contoso.com]에서는 IPv6을 통한 전자 메일을 수락 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d0e-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3d0e-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b3d0e-118">Related topics</span></span>

[<span data-ttu-id="b3d0e-119">DKIM으로 서명된 메시지의 유효성 검사 지원</span><span class="sxs-lookup"><span data-stu-id="b3d0e-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)