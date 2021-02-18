---
title: 메일 흐름 대시보드의 최상위 도메인 메일 흐름 상태 정보
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 최상위 도메인 메일 흐름 상태 정보를 사용하여 MX 레코드와 관련된 & 문제를 해결하는 방법을 확인할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ecda78047384a581a1043d0049b8dd25fadbe27
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290624"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="5d6f6-103">보안 및 준수 센터의 & 메일 흐름 상태 정보</span><span class="sxs-lookup"><span data-stu-id="5d6f6-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5d6f6-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="5d6f6-104">**Applies to**</span></span>
- [<span data-ttu-id="5d6f6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5d6f6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5d6f6-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="5d6f6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="5d6f6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d6f6-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="5d6f6-108">보안 **및** 준수 센터의 [](mail-flow-insights-v2.md) 메일 흐름 [대시보드에서](https://protection.office.com) 최상위 도메인 & 상태 정보를 통해 조직의 현재 메일 흐름 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6f6-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="5d6f6-109">이 인사이트는 메일 흐름 문제가 발생하는 도메인을 식별하고 ***문제를 해결하는 데 도움이*** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6f6-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="5d6f6-110">예를 들어 도메인이 만료되었거나 도메인에 잘못된 MX 레코드가 있기 때문에 도메인에서 외부 전자 메일을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6f6-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![보안 및 준수 센터의 메일 흐름 대시보드에서 & 흐름 상태 위젯](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="5d6f6-112">위젯에서 **세부** 정보 보기를 클릭하면  각 도메인의 상태에 대한 자세한 정보가 나타나는 도메인 상태 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5d6f6-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="5d6f6-113">**도메인**</span><span class="sxs-lookup"><span data-stu-id="5d6f6-113">**Domain**</span></span>
- <span data-ttu-id="5d6f6-114">**이전 MX 레코드**</span><span class="sxs-lookup"><span data-stu-id="5d6f6-114">**Previous MX record**</span></span>
- <span data-ttu-id="5d6f6-115">**현재 MX 레코드**</span><span class="sxs-lookup"><span data-stu-id="5d6f6-115">**Current MX record**</span></span>
- <span data-ttu-id="5d6f6-116">**전자 메일 수신 상태**</span><span class="sxs-lookup"><span data-stu-id="5d6f6-116">**Email receiving status**</span></span>
- <span data-ttu-id="5d6f6-117">**도메인 상태:** 녹색 확인 표시는 위젯을 클릭할 때 현재 MX 레코드가 레코드에 있는 값과 일치하고 도메인이 지난 2시간 동안 전자 메일을 수신한 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d6f6-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="5d6f6-118">빨간색 X는 MX 레코드가 변경되고 도메인이 지난 6시간 동안 전자 메일을 받지 않은 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d6f6-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="5d6f6-119">이는 도메인이 만료되었거나 MX 레코드가 잘못 업데이트된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6f6-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="5d6f6-120">도메인 등록 기관 또는 DNS 호스팅 서비스에 확인하여 도메인이 만료되었거나 도메인의 MX 레코드가 올바르지 않은지 확인해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6f6-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="5d6f6-121">더 보기를 **클릭하여** 더 많은 도메인에 대한 동일한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6f6-121">You can click **View more** to see the same information for more domains.</span></span>

![최상위 도메인 메일 흐름 상태 정보의 세부 정보 플라이아웃](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="5d6f6-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d6f6-123">See also</span></span>

<span data-ttu-id="5d6f6-124">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f6-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
