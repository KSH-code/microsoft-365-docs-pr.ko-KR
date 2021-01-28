---
title: 메일 흐름 대시보드의 아웃바운드 및 인바운드 메일 흐름 정보
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 아웃바운드 및 & 정보를 얻을 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e46a0ebf0c14e31462d1e86d8a8d8c08486337af
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029825"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="493b0-103">보안 및 준수 센터의 아웃바운드 및 & 흐름 정보</span><span class="sxs-lookup"><span data-stu-id="493b0-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="493b0-104">[](mail-flow-insights-v2.md) Security [](view-mail-flow-reports.md#connector-report) **&** 준수 센터의 메일 흐름 대시보드에 [](https://protection.office.com) 있는 아웃바운드 및 인바운드 메일 흐름 정보는 커넥터 보고서와 이전 **TLS** 개요 보고서의 정보를 한 곳으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="493b0-105">위젯에는 조직으로 메시지를 배달할 때 연결에 사용되는 TLS 암호화가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="493b0-106">다른 전자 메일 서비스와 함께 설정한 연결은 양측에서 TLS를 제공하는 경우 TLS로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="493b0-107">위젯은 메일 흐름의 마지막 주에 대한 스냅숏을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![보안 및 준수 센터의 메일 흐름 대시보드에서 아웃바운드 & 및 인바운드 메일 흐름 위젯](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="493b0-109">위젯의 정보는 Microsoft 365의 커넥터 및 TLS 메시지 보호와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="493b0-110">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="493b0-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="493b0-111">커넥터를 사용하여 메일 흐름 구성</span><span class="sxs-lookup"><span data-stu-id="493b0-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="493b0-112">Office 365의 전자 메일 연결 보안을 위해 Exchange Online에서 TLS를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="493b0-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="493b0-113">Microsoft 365의 암호화에 대한 기술 참조 세부 정보</span><span class="sxs-lookup"><span data-stu-id="493b0-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="493b0-114">전송 중(TLS로 보호된 메시지)</span><span class="sxs-lookup"><span data-stu-id="493b0-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="493b0-115">위젯에서  세부 정보 보기를 클릭하면 **TLS(전송** 중 보호된 메시지) 플라이아웃에 조직에서 들어오고 나가는 메시지에 대한 TLS 보호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![아웃바운드 및 인바운드 전자 메일 위젯에서 세부 정보 보기를 클릭한 후 나타나는 전송 중(TLS로 보호된 메시지) 플라이아웃](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="493b0-117">현재 TLS 1.2는 Microsoft 365에서 제공하는 가장 안전한 TLS 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="493b0-118">준수 감사에 사용되는 TLS 암호화를 알아야 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="493b0-119">대부분의 원본 및 대상 전자 메일 서버와 직접적인 관계가 없는 것일 수 있으므로(소유하지도 않은 Microsoft도 아니며) 해당 서버에서 사용되는 TLS 암호화를 개선할 수 있는 옵션이 많지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="493b0-120">그러나 커넥터를 [](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 사용하여 전자 메일 서버와 Microsoft 365 간에 전송되는 메시지에 대해 사용 가능한 최상의 TLS 보호를 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="493b0-121">Microsoft 365와 파트너에 속하는 자체 전자 메일 서버 또는 서버 간의 메일 흐름이 일반 메시지보다 더 중요하고 민감하기 때문에 이러한 메시지에 보안 및 보안 강화를 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="493b0-122">사용되고 있는 TLS 암호화를 개선하기 위해 자체 전자 메일 서버를 업그레이드하거나 수정하거나 파트너에게 연락하여 동일한 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="493b0-123">커넥터 **보고서에는** Microsoft 365 커넥터를 사용하는 메시지에 대한 메일 흐름 볼륨과 TLS 암호화가 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="493b0-124">커넥터 보고서 **링크를** 클릭하여 커넥터 보고서로 [이동하면 됩니다.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="493b0-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="493b0-125">연결된 조건이 검색된 경우  커넥터 보고서 페이지에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="493b0-126">**중요한 TLS1.0 메일 흐름이 표시될 인바운드 파트너 커넥터**</span><span class="sxs-lookup"><span data-stu-id="493b0-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="493b0-127">**중요한 TLS1.0 메일 흐름을 보는 인바운드 OnPremises 커넥터**</span><span class="sxs-lookup"><span data-stu-id="493b0-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="493b0-128">TLS 1.0 연결의 경우 Microsoft 365에서 TLS 1.0 지원이 더 이상 사용되지 않는 문제를 방지하려면 전자 메일 서버 또는 파트너의 서버를 업그레이드하거나 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="493b0-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="493b0-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="493b0-129">See also</span></span>

<span data-ttu-id="493b0-130">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="493b0-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
