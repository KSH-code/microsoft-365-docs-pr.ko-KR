---
title: 메일 흐름 대시보드의 상위 도메인 메일 흐름 상태 이해
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 최상위 도메인 메일 흐름 상태 정보를 사용 하 여 전자 메일 도메인의 MX 레코드와 관련 된 메일 흐름 문제를 해결 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: d4abc311e96df87894d5f059328f1a16a00190b8
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877514"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="ba209-103">보안 & 준수 센터의 상위 도메인 메일 흐름 상태 이해</span><span class="sxs-lookup"><span data-stu-id="ba209-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ba209-104">[보안 & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드의](mail-flow-insights-v2.md) **최상위 도메인 메일 흐름 상태** 정보는 메일 흐름 측면에서 조직의 도메인에 대 한 현재 상태를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba209-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="ba209-105">이러한 통찰력은 외부 전자 메일을 받을 수 없는 경우와 같이 \* *_메일 흐름에 영향_* 을 주는 도메인을 식별 하 고 문제를 해결 하는 데 도움이 되며, 특히 도메인 만료 또는 잘못 된 MX 레코드가 있는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="ba209-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow impacting_* _ issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![보안 & 준수 센터의 메일 흐름 대시보드의 상위 도메인 흐름 상태 위젯](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="ba209-107">위젯에 *자세히 보기* \*를 클릭 하면 각 도메인의 상태에 대 한 세부 정보를 보여 주는 **도메인 상태** 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ba209-107">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="ba209-108">**도메인**</span><span class="sxs-lookup"><span data-stu-id="ba209-108">**Domain**</span></span>
- <span data-ttu-id="ba209-109">**이전 MX 레코드**</span><span class="sxs-lookup"><span data-stu-id="ba209-109">**Previous MX record**</span></span>
- <span data-ttu-id="ba209-110">**현재 MX 레코드**</span><span class="sxs-lookup"><span data-stu-id="ba209-110">**Current MX record**</span></span>
- <span data-ttu-id="ba209-111">**전자 메일 수신 상태**</span><span class="sxs-lookup"><span data-stu-id="ba209-111">**Email receiving status**</span></span>
- <span data-ttu-id="ba209-112">**도메인 상태** : 녹색 확인 표시는 현재 MX 레코드 (위젯을 클릭 한 시점)가 record에 대해 수행한 값과 일치 하 고, 지난 2 시간 동안 도메인에서 전자 메일을 받았는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba209-112">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="ba209-113">빨간색 X는 MX 레코드가 변경 되었으며 도메인에서 지난 6 시간 동안 전자 메일을 받지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba209-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="ba209-114">이는 사용자의 도메인이 만료 되었거나 MX 레코드가 잘못 업데이트 되었음을 나타내는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba209-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="ba209-115">도메인 등록 기관 또는 DNS 호스팅 서비스에 문의 하 여 도메인의 사용 기간이 만료 되었는지 여부 또는 도메인의 MX 레코드가 올바르지 않은 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba209-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="ba209-116">더 많은 도메인에 대 한 동일한 정보를 보려면 **자세히 보기** 를 클릭 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba209-116">You can click **View more** to see the same information for more domains.</span></span>

![상위 도메인 메일 흐름 상태 이해의 세부 정보 플라이 아웃](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="ba209-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ba209-118">Related topics</span></span>

<span data-ttu-id="ba209-119">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba209-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
