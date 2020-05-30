---
title: 아웃 바운드 배달 풀
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Microsoft 365 데이터 센터에서 전자 메일 서버의 신뢰도를 보호 하기 위해 배달 풀을 사용 하는 방법을 알아봅니다.
ms.openlocfilehash: 213149eda3dd121b65b64e3bddbb4bd73d66f57c
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419163"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="b48af-103">아웃 바운드 배달 풀</span><span class="sxs-lookup"><span data-stu-id="b48af-103">Outbound delivery pools</span></span>

<span data-ttu-id="b48af-104">Microsoft 365 데이터 센터의 전자 메일 서버가 일시적으로 스팸 메일을 guilty 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="b48af-105">예를 들어 Microsoft 365를 통해 아웃 바운드 메일을 보내거나 Microsoft 365 계정을 손상 시킨 온-프레미스 전자 메일 조직의 맬웨어 또는 악성 스팸 공격이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="b48af-106">또한 공격자는 Microsoft 365 전달을 통해 메시지를 릴레이 하 여 검색을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-106">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="b48af-107">이러한 시나리오로 인해 영향을 받는 Microsoft 365 datacenter server의 IP 주소가 타사 차단 목록에 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-107">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="b48af-108">이러한 차단 목록을 사용 하는 대상 전자 메일 조직은 해당 메시지 원본의 전자 메일을 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-108">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="b48af-109">위험성이 높은 배달 풀</span><span class="sxs-lookup"><span data-stu-id="b48af-109">High-risk delivery pool</span></span>
<span data-ttu-id="b48af-110">이를 방지 하기 위해 스팸으로 확인 되거나 [서비스](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 의 전송 제한을 초과 하는 Microsoft 365 datacenter servers의 모든 아웃 바운드 메시지는 _높은 위험 배달 풀_ [을 통해 전송 됩니다.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="b48af-110">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="b48af-111">높은 위험 배달 풀은 "낮은 품질" 메시지 (예: 스팸 및 [백 분산](backscatter-messages-and-eop.md))를 보내는 데만 사용 되는 아웃 바운드 전자 메일에 대 한 별도의 IP 주소 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-111">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="b48af-112">높은 위험 배달 풀을 사용 하면 아웃 바운드 전자 메일에 대 한 일반 IP 주소 풀이 스팸을 보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-112">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="b48af-113">아웃 바운드 전자 메일의 일반 IP 주소 풀은 "고품질" 메시지를 보내는 신뢰도를 유지 하므로 이러한 IP 주소가 IP 차단 목록에 표시 되는 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-113">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="b48af-114">높은 위험 배달 풀의 IP 주소가 IP 차단 목록에 남아 있는 것은 매우 실질적인 일 이지만 이것은 의도적으로 설계 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-114">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="b48af-115">대부분의 전자 메일 조직에서는 높은 위험 배달 풀의 메시지를 수락 하지 않으므로 원하는 받는 사람에 게 배달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-115">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="b48af-116">자세한 내용은 [Control outbound 스팸](outbound-spam-controls.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b48af-116">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b48af-117">원본 전자 메일 도메인에 레코드가 없고 공용 DNS에 정의 된 MX 레코드가 없는 메시지는 항상 스팸 또는 전송 제한 처리에 관계 없이 위험성이 높은 배달 풀을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-117">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="b48af-118">바운스 메시지</span><span class="sxs-lookup"><span data-stu-id="b48af-118">Bounce messages</span></span>

<span data-ttu-id="b48af-119">아웃 바운드 높은 위험 배달 풀은 모든 배달 못 함 보고서 (Ndr, 바운스 메시지, 배달 상태 알림 또는 Dsn)에 대 한 배달을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-119">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="b48af-120">Ndr의 서 지에 대 한 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-120">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="b48af-121">서비스를 사용 하는 고객 중 한 명에 게 영향을 주는 스푸핑 캠페인</span><span class="sxs-lookup"><span data-stu-id="b48af-121">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="b48af-122">디렉터리 수집 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-122">A directory harvest attack.</span></span>
- <span data-ttu-id="b48af-123">스팸 공격</span><span class="sxs-lookup"><span data-stu-id="b48af-123">A spam attack.</span></span>
- <span data-ttu-id="b48af-124">Rogue 전자 메일 서버</span><span class="sxs-lookup"><span data-stu-id="b48af-124">A rogue email server.</span></span>

<span data-ttu-id="b48af-125">이러한 모든 문제로 인해 서비스에서 처리 하는 Ndr 수가 급격 하 게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-125">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="b48af-126">여러 번 이러한 ndr은 다른 전자 메일 서버 및 서비스에 스팸으로 표시 됩니다 ( _[후방 산란](backscatter-messages-and-eop.md)_ 이 라고도 함).</span><span class="sxs-lookup"><span data-stu-id="b48af-126">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="b48af-127">릴레이 풀</span><span class="sxs-lookup"><span data-stu-id="b48af-127">Relay pool</span></span>

<span data-ttu-id="b48af-128">최종 대상이 Microsoft 365를 실제 보낸 사람으로 간주 해서는 안 되므로 Microsoft 365에서 전달 되거나 외부에 릴레이 되는 메시지는 특수 릴레이 풀을 사용 하 여 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-128">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="b48af-129">또한 Microsoft 365에서 전자 메일을 자동으로 전달 하거나 릴레이 하기 위한 적법 한 illegitmate 시나리오가 있기 때문에이 트래픽을 격리 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-129">It's also important for us to isolate this traffic, because there are legitimate and illegitmate scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="b48af-130">높은 위험 수준 배달 그룹과 마찬가지로 릴레이 된 메일에는 별도의 IP 주소 풀이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-130">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="b48af-131">이 주소 풀은 자주 변경 될 수 있으므로 게시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-131">This address pool is not published since it can change often.</span></span> 

<span data-ttu-id="b48af-132">Microsoft 365에서는 전달 된 메시지를 안전 하 게 배달할 수 있도록 원래 보낸 사람이 합법적 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-132">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="b48af-133">이렇게 하려면 메시지가 도착 했을 때 SPF, DKIM 및 DMARC (전자 메일 인증)가 통과 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-133">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="b48af-134">보낸 사람을 인증할 수 있는 경우 보낸 사람 재작성을 사용 하 여 전달 된 메시지가 신뢰할 수 있는 원본에서 온 것 이라는 것을 수신자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-134">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="b48af-135">전송 도메인이 [보낸 사람 재작성 체계 (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)에서 인증을 통과 하는지 확인 하는 데 도움이 되는 방식 및 수행 방법에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48af-135">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
