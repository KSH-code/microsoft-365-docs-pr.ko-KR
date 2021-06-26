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
description: 배달 풀을 사용하여 데이터 센터에서 전자 메일 서버의 신뢰를 보호하는 Microsoft 365 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137721"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="15f5b-103">아웃바운드 배달 풀</span><span class="sxs-lookup"><span data-stu-id="15f5b-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="15f5b-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="15f5b-104">**Applies to**</span></span>
- [<span data-ttu-id="15f5b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="15f5b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="15f5b-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="15f5b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="15f5b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15f5b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="15f5b-108">데이터 센터의 전자 메일 Microsoft 365 일시적으로 스팸을 보내지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="15f5b-109">예를 들어 맬웨어 또는 악의적인 스팸 공격은 전자 메일 계정을 통해 아웃바운드 메일을 보내는 Microsoft 365 또는 손상된 Microsoft 365 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="15f5b-110">또한 공격자는 메시지 전달을 통해 메시지를 릴레이하여 검색을 Microsoft 365 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="15f5b-111">이러한 시나리오는 영향을 받는 데이터 센터 서버의 IP Microsoft 365 차단 목록에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="15f5b-112">이러한 차단 목록을 사용하는 대상 전자 메일 조직은 해당 메시지 원본의 전자 메일을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="15f5b-113">고위험 배달 풀</span><span class="sxs-lookup"><span data-stu-id="15f5b-113">High-risk delivery pool</span></span>
<span data-ttu-id="15f5b-114">이를 방지하기 위해 스팸으로 확인되거나 서비스 또는 아웃바운드 스팸 정책의 전송 제한을 초과하는 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) Microsoft 365 데이터 [](configure-the-outbound-spam-policy.md) 센터 서버의 모든 아웃바운드 메시지가 위험도가 높은 배달 풀을 통해 _전송됩니다._</span><span class="sxs-lookup"><span data-stu-id="15f5b-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="15f5b-115">고위험 배달 풀은 "낮은 품질" 메시지(예: 스팸 및 후방 스캐터)를 보내는 데만 사용되는 아웃바운드 전자 메일에 대한 별도의 IP [주소 풀입니다.](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="15f5b-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="15f5b-116">높은 위험 배달 풀을 사용하면 아웃바운드 전자 메일의 일반 IP 주소 풀에서 스팸을 보내지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="15f5b-117">아웃바운드 전자 메일의 일반 IP 주소 풀은 "고품질" 메시지를 보내는 신뢰도 유지 관리로, 이러한 IP 주소가 IP 차단 목록에 표시될 가능성을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="15f5b-118">고위험 배달 풀의 IP 주소가 IP 차단 목록에 배치될 가능성은 매우 높지만 이는 설계에 따라 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="15f5b-119">많은 전자 메일 조직이 고위험 배달 풀의 메시지를 수락하지 못하기 때문에 의도한 받는 사람에게 배달이 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="15f5b-120">자세한 내용은 아웃바운드 스팸 [제어를 참조하세요.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="15f5b-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="15f5b-121">원본 전자 메일 도메인에 A 레코드가 없는 메시지와 공용 DNS에 정의된 MX 레코드가 없는 메시지는 스팸 또는 전송 제한 처리에 관계없이 항상 위험도가 높은 배달 풀을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="15f5b-122">반송 메시지</span><span class="sxs-lookup"><span data-stu-id="15f5b-122">Bounce messages</span></span>

<span data-ttu-id="15f5b-123">아웃바운드 고위험 배달 풀은 모든 배달되지 않은 보고서(NDRs, 반송 메시지, 배달 상태 알림 또는 DSN)의 배달을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="15f5b-124">NDRS의 급증에 대한 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="15f5b-125">서비스를 사용하는 고객 중 한 명에게 영향을 주는 스푸핑 캠페인입니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="15f5b-126">디렉터리 수집 공격.</span><span class="sxs-lookup"><span data-stu-id="15f5b-126">A directory harvest attack.</span></span>
- <span data-ttu-id="15f5b-127">스팸 공격.</span><span class="sxs-lookup"><span data-stu-id="15f5b-127">A spam attack.</span></span>
- <span data-ttu-id="15f5b-128">Rogue 전자 메일 서버.</span><span class="sxs-lookup"><span data-stu-id="15f5b-128">A rogue email server.</span></span>

<span data-ttu-id="15f5b-129">이러한 모든 문제로 인해 서비스에서 처리되는 NDRS 수가 갑자기 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="15f5b-130">대부분의 경우 이러한 NDRS는 다른 전자 메일 서버 및 서비스(후방 스캐터라고도 하는)에 스팸인 _[것으로 나타납니다.](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="15f5b-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>


### <a name="relay-pool"></a><span data-ttu-id="15f5b-131">릴레이 풀</span><span class="sxs-lookup"><span data-stu-id="15f5b-131">Relay pool</span></span>

<span data-ttu-id="15f5b-132">특정 시나리오에서 Microsoft 365 전달되거나 릴레이되는 메시지는 특수 릴레이 풀을 사용하여 전송됩니다. 대상은 실제 보낸 Microsoft 365 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-132">Messages that are forwarded or relayed via Microsoft 365 in certain scenarios will be sent using a special relay pool, because the destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="15f5b-133">전자 메일 트래픽을 격리하는 것이 중요합니다. 전자 메일을 전자 메일이 전송되지 않은 경우 자동 전달 또는 릴레이하는 합법적인 잘못된 시나리오가 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15f5b-133">It's important for us to isolate this email traffic, because there are legitimate and invalid scenarios for auto forwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="15f5b-134">위험이 높은 배달 풀과 마찬가지로 별도의 IP 주소 풀이 릴레이된 메일에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="15f5b-135">이 주소 풀은 자주 변경될 수 있기 때문에 게시되지 않습니다. 이 주소 풀은 해당 주소 풀에 대해 게시된 SPF 레코드에 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15f5b-135">This address pool is not published because it can change often, and it's not part of published SPF record for Microsoft 365.</span></span>

<span data-ttu-id="15f5b-136">Microsoft 365 전달된 메시지를 배달할 수 있도록 원래 보낸 사람이 합법적인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span>

<span data-ttu-id="15f5b-137">릴레이 풀을 사용하지 않도록 전달/릴레이된 메시지는 다음 조건 중 하나를 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-137">The forwarded/relayed message should meet one of the following criteria to avoid using the relay pool:</span></span>

- <span data-ttu-id="15f5b-138">아웃바운드 보낸 사람이 허용 [도메인에 있습니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="15f5b-138">The outbound sender is in an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
- <span data-ttu-id="15f5b-139">SPF는 메시지가 전송되면 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15f5b-139">SPF passes when the message comes to Microsoft 365.</span></span>
- <span data-ttu-id="15f5b-140">보낸 사람 도메인의 DKIM은 메시지가 전송되면 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15f5b-140">DKIM on the sender domain passes when the message comes to Microsoft 365.</span></span>
 
<span data-ttu-id="15f5b-141">아웃바운드 서버 IP(릴레이 풀은 40.95.0.0/16 범위에 해당)를 확인하거나 아웃바운드 서버 이름(이름에 "rly"이 사용)을 확인하여 메시지가 릴레이 풀을 통해 전송된 것으로 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-141">You can tell that a message was sent via the relay pool by looking at the outbound server IP (the relay pool will be in the 40.95.0.0/16 range), or by looking at the outbound server name (will have "rly" in the name).</span></span>

<span data-ttu-id="15f5b-142">보낸 사람을 인증할 수 있는 경우 SRS(Sender Rewriting Scheme)를 사용하여 받는 사람 전자 메일 시스템에서 전달된 메시지가 신뢰할 수 있는 원본에서 전송된 메시지인지 알 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-142">In cases where we can authenticate the sender, we use Sender Rewriting Scheme (SRS) to help the recipient email system know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="15f5b-143">보내는 도메인이 의 [SRS(Sender Rewriting Scheme)에서](/office365/troubleshoot/antispam/sender-rewriting-scheme)인증을 통과하도록 하는 데 도움이 되는 작업과 작동 방식에 대해 자세히 Office 365.</span><span class="sxs-lookup"><span data-stu-id="15f5b-143">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>

<span data-ttu-id="15f5b-144">DKIM이 작동하려면 도메인 보내기에 DKIM을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-144">For DKIM to work, make sure you enable DKIM for sending domain.</span></span> <span data-ttu-id="15f5b-145">예를 들어 fabrikam.com 조직의 contoso.com 도메인에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f5b-145">For example, fabrikam.com is part of contoso.com and is defined in the accepted domains of the organization.</span></span> <span data-ttu-id="15f5b-146">메시지 보낸 사람이 sender@fabrikam.com DKIM을 사용하도록 설정해야 fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="15f5b-146">If the message sender is sender@fabrikam.com, DKIM needs to be enabled for fabrikam.com.</span></span> <span data-ttu-id="15f5b-147">DKIM을 사용하여 사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 유효성을 검사하는 방법을 읽을 [수 있습니다.](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="15f5b-147">you can read on how to enable at [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="15f5b-148">사용자 지정 도메인을 추가하려면 [Add a domain to Microsoft 365.](../../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="15f5b-148">To add a custom domains follow the steps in [Add a domain to Microsoft 365](../../admin/setup/add-domain.md).</span></span>
