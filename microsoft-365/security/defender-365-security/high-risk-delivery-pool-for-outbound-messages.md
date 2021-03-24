---
title: 아웃바운드 배달 풀
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Microsoft 365 데이터 센터에서 배달 풀을 사용하여 전자 메일 서버의 신뢰도 보호 방법에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 461b5f9aa0407c5115ab84a075c793139a8b4305
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071407"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="638dc-103">아웃바운드 배달 풀</span><span class="sxs-lookup"><span data-stu-id="638dc-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="638dc-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="638dc-104">**Applies to**</span></span>
- [<span data-ttu-id="638dc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="638dc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="638dc-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="638dc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="638dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="638dc-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="638dc-108">Microsoft 365 데이터 센터의 전자 메일 서버가 일시적으로 스팸을 보내지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="638dc-109">예를 들어 Microsoft 365를 통해 아웃바운드 메일을 전송하거나 손상된 Microsoft 365 계정을 보내는 사내 전자 메일 조직의 맬웨어 또는 악의적인 스팸 공격이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="638dc-110">또한 공격자는 Microsoft 365 전달을 통해 메시지를 릴레이하여 검색을 방지하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="638dc-111">이러한 시나리오는 영향을 받는 Microsoft 365 데이터 센터 서버의 IP 주소가 타사 차단 목록에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="638dc-112">이러한 차단 목록을 사용하는 대상 전자 메일 조직은 해당 메시지 원본의 전자 메일을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-112">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="638dc-113">고위험 배달 풀</span><span class="sxs-lookup"><span data-stu-id="638dc-113">High-risk delivery pool</span></span>
<span data-ttu-id="638dc-114">이를 방지하기 위해 스팸으로 확인되거나 서비스 또는 아웃바운드 스팸 정책의 전송 제한을 초과하는 Microsoft [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 365 데이터 센터 서버의 모든 아웃바운드 메시지가 위험도가 높은 배달 풀을 통해 _전송됩니다._ [](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="638dc-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="638dc-115">고위험 배달 풀은 "낮은 품질" 메시지(예: 스팸 및 후방 스캐터)를 보내는 데만 사용되는 아웃바운드 전자 메일에 대한 별도의 IP [주소 풀입니다.](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="638dc-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="638dc-116">높은 위험 배달 풀을 사용하면 아웃바운드 전자 메일의 일반 IP 주소 풀에서 스팸을 보내지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="638dc-117">아웃바운드 전자 메일의 일반 IP 주소 풀은 "고품질" 메시지를 보내는 신뢰도 유지 관리로, 이러한 IP 주소가 IP 차단 목록에 표시될 가능성을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="638dc-118">고위험 배달 풀의 IP 주소가 IP 차단 목록에 배치될 가능성은 매우 높지만 이는 디자인에 따라 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="638dc-119">많은 전자 메일 조직이 고위험 배달 풀의 메시지를 수락하지 못하기 때문에 의도한 받는 사람에게 배달이 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="638dc-120">자세한 내용은 아웃바운드 스팸 [제어를 참조하세요.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="638dc-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="638dc-121">원본 전자 메일 도메인에 A 레코드가 없는 메시지와 공용 DNS에 정의된 MX 레코드가 없는 메시지는 스팸 또는 전송 제한 처리에 관계없이 항상 위험도가 높은 배달 풀을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="638dc-122">반송 메시지</span><span class="sxs-lookup"><span data-stu-id="638dc-122">Bounce messages</span></span>

<span data-ttu-id="638dc-123">아웃바운드 고위험 배달 풀은 모든 배달되지 않은 보고서(NDRs, 반송 메시지, 배달 상태 알림 또는 DSN)의 배달을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="638dc-124">NDRS의 급증에 대한 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="638dc-125">서비스를 사용하는 고객 중 한 명에게 영향을 주는 스푸핑 캠페인입니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="638dc-126">디렉터리 수집 공격.</span><span class="sxs-lookup"><span data-stu-id="638dc-126">A directory harvest attack.</span></span>
- <span data-ttu-id="638dc-127">스팸 공격.</span><span class="sxs-lookup"><span data-stu-id="638dc-127">A spam attack.</span></span>
- <span data-ttu-id="638dc-128">Rogue 전자 메일 서버.</span><span class="sxs-lookup"><span data-stu-id="638dc-128">A rogue email server.</span></span>

<span data-ttu-id="638dc-129">이러한 모든 문제로 인해 서비스에서 처리되는 NDRS 수가 갑자기 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="638dc-130">대부분의 경우 이러한 NDRS는 다른 전자 메일 서버 및 서비스(후방 스캐터라고도 하는)에 스팸인 _[것으로 나타납니다.](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="638dc-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="638dc-131">릴레이 풀</span><span class="sxs-lookup"><span data-stu-id="638dc-131">Relay pool</span></span>

<span data-ttu-id="638dc-132">Microsoft 365에서 전달되거나 릴레이되는 메시지는 특수 릴레이 풀을 사용하여 전송됩니다. 최종 대상은 Microsoft 365를 실제 보낸 사람으로 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-132">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="638dc-133">Microsoft 365에서 전자 메일을 자동 전달하거나 릴레이하는 합법적인 잘못된 시나리오가 있기 때문에 이 트래픽을 격리하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-133">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="638dc-134">위험이 높은 배달 풀과 마찬가지로 별도의 IP 주소 풀이 릴레이된 메일에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="638dc-135">이 주소 풀은 자주 변경될 수 있는 게시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-135">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="638dc-136">Microsoft 365는 전달된 메시지를 배달할 수 있도록 원래 보낸 사람이 합법적인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="638dc-137">이를 위해 전자 메일 인증(SPF, DKIM 및 DMARC)은 메시지가 전송된 경우 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-137">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="638dc-138">보낸 사람 인증을 할 수 있는 경우 Sender Rewriting을 사용하여 수신자가 전달된 메시지가 신뢰할 수 있는 원본의 메시지인지 알 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-138">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="638dc-139">보내는 도메인이 [SRS(Sender Rewriting Scheme)에서](/office365/troubleshoot/antispam/sender-rewriting-scheme)인증을 통과하도록 하는 데 도움이 되는 작업 및 작동 방식에 대해 자세히 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638dc-139">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>