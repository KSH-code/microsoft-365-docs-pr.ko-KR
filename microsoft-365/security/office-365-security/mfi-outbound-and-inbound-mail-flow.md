---
title: 메일 흐름 대시보드의 아웃 바운드 및 인바운드 메일 흐름 이해
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
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에 있는 아웃 바운드 및 인바운드 메일 흐름에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 33bfe3882c274fa655d17c80aba007e8d246b250
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199304"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="2631a-103">보안 & 준수 센터의 아웃 바운드 및 인바운드 메일 흐름 이해</span><span class="sxs-lookup"><span data-stu-id="2631a-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2631a-104">[Security & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드에](mail-flow-insights-v2.md) 있는 **아웃 바운드 및 인바운드 메일 흐름** 에 대 한 정보는 [커넥터 보고서](view-mail-flow-reports.md#connector-report) 와 이전 **TLS 개요 보고서** 의 정보가 한 곳에 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="2631a-105">위젯은 조직에서 메시지를 배달할 때 연결에 사용 되는 TLS 암호화를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="2631a-106">두 쪽에서 모두 TLS를 제공 하는 경우 다른 전자 메일 서비스와 함께 설정 되는 연결은 TLS에 의해 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="2631a-107">이 위젯은 메일 흐름의 마지막 주에 대 한 스냅숏을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![보안 & 준수 센터의 메일 흐름 대시보드의 아웃 바운드 및 인바운드 메일 흐름 위젯](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="2631a-109">위젯의 정보는 커넥터 및 Microsoft 365의 TLS 메시지 보호와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="2631a-110">자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2631a-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="2631a-111">커넥터를 사용 하 여 메일 흐름 구성</span><span class="sxs-lookup"><span data-stu-id="2631a-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="2631a-112">Exchange Online이 TLS를 사용 하 여 전자 메일 연결을 보호 하는 방법</span><span class="sxs-lookup"><span data-stu-id="2631a-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="2631a-113">Microsoft 365의 암호화에 대 한 기술 참조 세부 정보</span><span class="sxs-lookup"><span data-stu-id="2631a-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="2631a-114">메시지가 전송 중에 보호 됨 (TLS에서)</span><span class="sxs-lookup"><span data-stu-id="2631a-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="2631a-115">위젯에 대 한 **세부 정보 보기** 를 클릭 하면 **전송 (TLS에서) 플라이 아웃에서 보호 된 메시지가** 조직에 들어오고 나가는 메시지에 대 한 TLS 보호 기능을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![아웃 바운드 및 인바운드 전자 메일 위젯에 대 한 세부 정보 보기를 클릭 하면 표시 되는 전송 (TLS에 의해) 플라이 아웃을 통해 보호 된 메시지](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="2631a-117">현재 TLS 1.2은 Microsoft 365에서 제공 하는 가장 안전한 버전의 TLS입니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="2631a-118">준수 감사에 사용 되는 TLS 암호화를 알아야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="2631a-119">대부분의 원본 및 대상 전자 메일 서버 (사용자가 소유 하지 않으며 Microsoft는 사용 하지 않음)와 직접 관계가 없을 수도 있으므로 이러한 서버에서 사용한 TLS 암호화를 향상 시킬 수 있는 여러 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="2631a-120">그러나 [커넥터](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 를 사용 하 여 전자 메일 서버와 Microsoft 365 간에 전송 되는 메시지에 대 한 최선의 사용 가능 TLS 보호를 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="2631a-121">Microsoft 365와 자체 전자 메일 서버 또는 파트너에 속하는 서버 간의 메일 흐름은 일반적으로 일반 메시지 보다 중요 하 고 중요 하며 이러한 메시지에는 추가 보안 및 감시를 적용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="2631a-122">자체 전자 메일 서버를 업그레이드 하거나 수정 하 여 사용 중인 TLS 암호화를 개선 하거나, 파트너에 게 연락 하 여 동일한 작업을 수행 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="2631a-123">**커넥터 보고서** 에는 Microsoft 365 커넥터를 사용 하는 메시지에 대 한 메일 흐름 볼륨과 TLS 암호화가 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="2631a-124">**커넥터 보고서** 링크를 클릭 하 여 [커넥터 보고서](view-mail-flow-reports.md#connector-report)로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="2631a-125">연결 된 조건이 검색 된 경우 **커넥터 보고서** 페이지에서 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="2631a-126">**인바운드 파트너 커넥터 중요 TLS 1.0 메일 흐름 보기**</span><span class="sxs-lookup"><span data-stu-id="2631a-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="2631a-127">**인바운드 OnPremises 커넥터 중요 TLS 1.0 메일 흐름 보기**</span><span class="sxs-lookup"><span data-stu-id="2631a-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="2631a-128">TLS 1.0 연결의 경우 Microsoft 365에서 TLS 1.0 지원이 더 이상 사용 되지 않는 경우 문제를 방지 하기 위해 전자 메일 서버 또는 파트너의 서버를 업그레이드 하거나 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2631a-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="2631a-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2631a-129">See also</span></span>

<span data-ttu-id="2631a-130">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2631a-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
