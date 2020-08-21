---
title: 메일 흐름 대시보드의 최상위 도메인 메일 흐름 상태 정보
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 주요 도메인 메일 흐름 상태 정보를 사용하여 전자 메일 도메인의 MX 레코드와 관련된 메일 흐름 문제를 해결하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827018"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="4b322-103">보안 도메인 준수 센터의 최상위 도메인 & 상태 정보</span><span class="sxs-lookup"><span data-stu-id="4b322-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="4b322-104">보안 & **준수 센터의 메일** 흐름 [대시보드에서](mail-flow-insights-v2.md) 최상위 도메인 메일 흐름 상태 정보를 사용하면 메일 흐름에 관한 조직의 도메인에 대한 현재 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b322-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="4b322-105">이 인사이트는 메일 흐름에 영향을 미치는 도메인(예: ***mail flow impacting*** 외부 전자 메일을 받을 수 없음), 특히 잘못된 MX 레코드를 가진 도메인을 식별하고 문제를 해결하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b322-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![보안 흐름 대시보드의 도메인 흐름 상태 위내& 위내](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="4b322-107">위반에서 **세부 정보 보기를** 클릭하면 각 도메인의 **상태에** 대한 자세한 정보가 표시되는 도메인 상태 플라이 아웃이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b322-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="4b322-108">**도메인**</span><span class="sxs-lookup"><span data-stu-id="4b322-108">**Domain**</span></span>
- <span data-ttu-id="4b322-109">**이전 MX 레코드**</span><span class="sxs-lookup"><span data-stu-id="4b322-109">**Previous MX record**</span></span>
- <span data-ttu-id="4b322-110">**현재 MX 레코드**</span><span class="sxs-lookup"><span data-stu-id="4b322-110">**Current MX record**</span></span>
- <span data-ttu-id="4b322-111">**전자 메일 받기 상태**</span><span class="sxs-lookup"><span data-stu-id="4b322-111">**Email receiving status**</span></span>
- <span data-ttu-id="4b322-112">**도메인 상태:** 녹색 확인 표시는 (위키를 클릭한 시점에) 현재 MX 레코드(위키를 클릭한 시간)와 일치하는 값이며 지나면 2시간 동안 도메인에 전자 메일을 받임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b322-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="4b322-113">빨간색 X는 MX 레코드가 변경되었음을 나타내고 지나면 6시간 동안 도메인에 전자 메일을 받지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b322-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="4b322-114">이는 도메인이 만료되었거나 MX 레코드가 잘못 업데이트되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b322-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="4b322-115">도메인 등록 기관 또는 DNS 호스팅 서비스에 확인하여 도메인이 만료되었는지 또는 도메인의 MX 레코드가 잘못되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b322-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="4b322-116">더 많은 **도메인에 대해 동일한 정보를** 보려면 더 많은 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b322-116">You can click **View more** to see the same information for more domains.</span></span>

![상위 도메인 메일 흐름 상태 정보의 플라이아웃 세부 정보](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="4b322-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4b322-118">Related topics</span></span>

<span data-ttu-id="4b322-119">메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="4b322-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
