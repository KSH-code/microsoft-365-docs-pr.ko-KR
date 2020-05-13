---
title: 아웃바운드 메시지용 높은 위험 배달 풀
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
description: 위험성이 높은 배달 풀을 사용 하 여 Microsoft 365 데이터 센터에서 전자 메일 서버의 신뢰도를 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: 190dc3bd7ed2a6cddb23c8bc7c117dee30fd4f13
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209190"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="3c6b6-103">아웃바운드 메시지용 높은 위험 배달 풀</span><span class="sxs-lookup"><span data-stu-id="3c6b6-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="3c6b6-104">Microsoft 365 데이터 센터의 전자 메일 서버가 일시적으로 스팸 메일을 guilty 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="3c6b6-105">예를 들어 Microsoft 365를 통해 아웃 바운드 메일을 보내거나 Microsoft 365 계정을 손상 시킨 온-프레미스 전자 메일 조직의 맬웨어 또는 악성 스팸 공격이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="3c6b6-106">이러한 시나리오로 인해 영향을 받는 Microsoft 365 datacenter server의 IP 주소가 타사 차단 목록에 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-106">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="3c6b6-107">이러한 차단 목록을 사용 하는 대상 전자 메일 조직은 해당 메시지 원본의 전자 메일을 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="3c6b6-108">이를 방지 하기 위해 스팸으로 확인 되거나 [서비스](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 의 전송 제한을 초과 하는 Microsoft 365 datacenter servers의 모든 아웃 바운드 메시지는 _높은 위험 배달 풀_ [을 통해 전송 됩니다.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="3c6b6-108">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="3c6b6-109">높은 위험 배달 풀은 "낮은 품질" 메시지 (예: 스팸 및 [백 분산](backscatter-messages-and-eop.md))를 보내는 데만 사용 되는 아웃 바운드 전자 메일에 대 한 보조 IP 주소 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="3c6b6-110">높은 위험 배달 풀을 사용 하면 아웃 바운드 전자 메일에 대 한 일반 IP 주소 풀이 스팸을 보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="3c6b6-111">아웃 바운드 전자 메일의 일반 IP 주소 풀은 "고품질" 메시지를 보내는 신뢰도를 유지 하므로 이러한 IP 주소가 IP 차단 목록에 표시 되는 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="3c6b6-112">높은 위험 배달 풀의 IP 주소가 IP 차단 목록에 남아 있는 것은 매우 실질적인 일 이지만 이것은 의도적으로 설계 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="3c6b6-113">대부분의 전자 메일 조직에서는 높은 위험 배달 풀의 메시지를 수락 하지 않으므로 원하는 받는 사람에 게 배달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="3c6b6-114">자세한 내용은 [Control outbound 스팸](outbound-spam-controls.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-114">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3c6b6-115">원본 전자 메일 도메인에 레코드가 없고 공용 DNS에 정의 된 MX 레코드가 없는 메시지는 항상 스팸 또는 전송 제한 처리에 관계 없이 위험성이 높은 배달 풀을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="3c6b6-116">바운스 메시지</span><span class="sxs-lookup"><span data-stu-id="3c6b6-116">Bounce messages</span></span>

<span data-ttu-id="3c6b6-117">아웃 바운드 높은 위험 배달 풀은 모든 배달 못 함 보고서 (Ndr, 바운스 메시지, 배달 상태 알림 또는 Dsn)에 대 한 배달을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="3c6b6-118">Ndr의 서 지에 대 한 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="3c6b6-119">서비스를 사용 하는 고객 중 한 명에 게 영향을 주는 스푸핑 캠페인</span><span class="sxs-lookup"><span data-stu-id="3c6b6-119">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="3c6b6-120">디렉터리 수집 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-120">A directory harvest attack.</span></span>
- <span data-ttu-id="3c6b6-121">스팸 공격</span><span class="sxs-lookup"><span data-stu-id="3c6b6-121">A spam attack.</span></span>
- <span data-ttu-id="3c6b6-122">Rogue 전자 메일 서버</span><span class="sxs-lookup"><span data-stu-id="3c6b6-122">A rogue email server.</span></span>

<span data-ttu-id="3c6b6-123">이러한 모든 문제로 인해 서비스에서 처리 하는 Ndr 수가 급격 하 게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6b6-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="3c6b6-124">여러 번 이러한 ndr은 다른 전자 메일 서버 및 서비스에 스팸으로 표시 됩니다 ( _[후방 산란](backscatter-messages-and-eop.md)_ 이 라고도 함).</span><span class="sxs-lookup"><span data-stu-id="3c6b6-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
