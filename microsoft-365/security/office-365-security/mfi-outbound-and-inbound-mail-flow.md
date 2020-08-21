---
title: 메일 흐름 대시보드의 아웃바운드 및 인바운드 메일 흐름 분석
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 관리자는 보안 그룹 준수 센터의 메일 흐름 대시보드에서 아웃바운드 및 인바운드 메일 흐름 정보에 대해 알아& 있습니다.
ms.openlocfilehash: 920c1212f4d6dee508704c93272e48140e199710
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826896"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="74772-103">보안 센터의 아웃바운드 및 인바운드 & 흐름</span><span class="sxs-lookup"><span data-stu-id="74772-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="74772-104">보안 **& 준수 센터의 메일 흐름** 대시보드에서의 아웃바운드 및 인바운드 메일 흐름 인사이트는 커넥터 [보고서의](view-mail-flow-reports.md#connector-report) 정보와 이전 TLS 개요 보고서의 **정보를 한 위치에** 통합합니다. [Mail flow dashboard](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="74772-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="74772-105">위리에는 조직으로 메시지를 배달하고 조직에서 메시지를 배달할 때 연결에 사용되는 TLS 암호화가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74772-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="74772-106">다른 전자 메일 서비스에서 설정하는 연결은 TLS에서 모두 제공하는 연결에 의해 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="74772-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="74772-107">위장은 메일 흐름의 지난 주에 대한 스냅숏을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74772-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![준수 센터의 보안 흐름 대시보드에서 아웃바운드 및 인바운드 & 위예로 인바운드 및 인바운드 메일 흐름 위유](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="74772-109">위리수의 정보는 Microsoft 365의 커넥터 및 TLS 메시지 보호와 관련되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74772-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="74772-110">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74772-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="74772-111">커넥터를 사용하여 메일 흐름 구성</span><span class="sxs-lookup"><span data-stu-id="74772-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="74772-112">Exchange Online에서 전자 메일 연결 보안을 위해 TLS를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="74772-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="74772-113">Microsoft 365의 암호화에 대한 기술 관련 세부 정보</span><span class="sxs-lookup"><span data-stu-id="74772-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="74772-114">전송 중 보호된 메시지(TLS에 의해)</span><span class="sxs-lookup"><span data-stu-id="74772-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="74772-115">위의 **보기를 클릭하면** **TLS로** 보호되는 메시지 플라이아웃에 TLS(조직으로 들어오고 나가는 메시지) 에지 가로채기가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="74772-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![전송 중으로 보호되는 메시지는 아웃바운드 및 인바운드 전자 메일 위와 같이 표시됩니다.](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="74772-117">현재 TLS 1.2는 Microsoft 365에서 제공하는 가장 안전한 TLS 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="74772-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="74772-118">종종 규정 준수 감사에 사용되는 TLS 암호화를 알고야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74772-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="74772-119">대부분의 원본 및 대상 전자 메일 서버와 직접적인 관계가 없는 경우(이를 소유하지 않을 것이며 Microsoft에서는 아무것도 제공하지 않음) 이러한 서버에서 사용되는 TLS 암호화를 개선할 수 있는 많은 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74772-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="74772-120">그렇지만 커넥터를 [사용하여 전자 메일 서버와](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) Microsoft 365 간에 전송되는 메시지에 대해 최적의 TLS 보호를 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74772-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="74772-121">Microsoft 365와 자체 전자 메일 서버 또는 파트너에 속한 자체 전자 메일 서버 간의 메일 흐름은 일반 메시지보다 훨씬 중요하고 민감한 경우가 므로 추가 보안과 보안을 해당 메시지에 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74772-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="74772-122">사용자 고유의 전자 메일 서버를 업그레이드하거나 수정하여 사용 중이될 TLS 암호화를 개선하거나 파트너에게 도달하여 동일한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74772-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="74772-123">커넥터 **보고서에는** Microsoft 365 커넥터를 사용하는 메시지에 대한 메일 흐름 볼륨과 TLS 암호화가 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74772-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="74772-124">커넥터 보고서 **링크를 클릭하여** 커넥터 보고서로 이동할 [수 있습니다.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="74772-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="74772-125">연결된 조건이 검색되면 커넥터 보고서 페이지에서 다음 **정보를** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74772-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="74772-126">**중요한 TLS1.0 메일 흐름이 표시되는 인바운드 파트너 커넥터**</span><span class="sxs-lookup"><span data-stu-id="74772-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="74772-127">**중요한 TLS1.0 메일 흐름이 표시된 인바운드 온-프레미스 커넥터**</span><span class="sxs-lookup"><span data-stu-id="74772-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="74772-128">TLS 1.0 연결의 경우, Microsoft 365에서 더 이상 TLS 1.0 지원이 더 이상 사용되지 않는 경우 발생하는 문제를 피하려면 실제로 전자 메일 서버 또는 파트너의 서버를 업그레이드하거나 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74772-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="74772-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74772-129">See also</span></span>

<span data-ttu-id="74772-130">메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="74772-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
