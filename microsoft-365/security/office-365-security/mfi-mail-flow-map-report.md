---
title: 메일 흐름 지도
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
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 메일 흐름 맵을 사용하여 커넥터를 사용하고 커넥터를 사용하지 않고 조직에서 메일 흐름을 이동하는 방법을 시각화하고 추적할 수 있습니다.
ms.openlocfilehash: d27513b905a2b6c1a7ae366040e9e29b2d67b258
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827004"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="4b218-103">보안 도메인 준수 센터의 & 흐름 맵</span><span class="sxs-lookup"><span data-stu-id="4b218-103">Mail flow map in the Security & Compliance Center</span></span>

<span data-ttu-id="4b218-104">보안 **및 준수 센터의** [메일 흐름 대시보드](mail-flow-insights-v2.md) &에 있는 메일 흐름 맵은 조직전체에서 메일이 수행되는 방식을 통한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="4b218-105">이 정보를 사용하여 패턴을 알아보고 필요에 따라 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![보안 그룹 준수 센터의 메일 흐름 대시보드에서 위단계 & 위위로 맵정](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="4b218-107">기본적으로 위소에서는 *Sankey* 다이어그램이라고 하는 차트에서 이전 날의 메일 흐름 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="4b218-108">왼쪽 화살표와 오른쪽 ![ 화살표를 ](../../media/scc-left-arrow.png) 사용하여 다양한 일간의 ![ ](../../media/scc-right-arrow.png) 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="4b218-109">각 색은 다른 인바운드 또는 아웃바운드 커넥터를 통한(또는 커넥터 사용 금지)를 통해서의 메일 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="4b218-110">특정 한 종류에 전화를 가리면 해당 유형의 커넥터에 대해 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="4b218-111">메일 흐름 맵에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="4b218-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="4b218-112">메일 흐름 맵 **위로를 클릭하면** 메일 흐름 맵 **보고서로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="4b218-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="4b218-113">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="4b218-114">**데이터 표시: 기본적으로**위작업의 더 큰 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="4b218-115">특정 한 종류에 전화를 가리면 해당 유형의 커넥터에 대해 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![메일 흐름 맵 보고서의 개요 보기](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="4b218-117">**데이터 표시: 세부 정보:** 이 보기는 커넥터 및 대상 도메인에 대한 세부 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="4b218-118">맨 위에 있는 보낸 사람 및 받는 사람 도메인이 나열되고 나머지는 다른 사람에 **게 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4b218-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="4b218-119">특정 색및 구역에 커서를 두면 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![메일 흐름 맵 보고서의 세부 정보 보기](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="4b218-121">보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4b218-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4b218-122">특정 날짜 범위에 대한 보고서에 대한 정보를 한 명 이상의 받는 사람에게 전자 메일로 보내려면 요청 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4b218-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="4b218-123">관련 인사이트가 사용 가능한 경우 메일 흐름 맵 아래에 표시됩니다(예: [수정 가능한 메일 루프 정보 정보](mfi-mail-loop-insight.md)확인).</span><span class="sxs-lookup"><span data-stu-id="4b218-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="4b218-124">메일 흐름 맵의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="4b218-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="4b218-125">보고서 보기에서 **세부 정보 표를** 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="4b218-126">**날짜**</span><span class="sxs-lookup"><span data-stu-id="4b218-126">**Date**</span></span>
- <span data-ttu-id="4b218-127">**범주**</span><span class="sxs-lookup"><span data-stu-id="4b218-127">**Category**</span></span>
- <span data-ttu-id="4b218-128">**커넥터/타사 서비스 공급자**</span><span class="sxs-lookup"><span data-stu-id="4b218-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="4b218-129">**보낸 사람/받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="4b218-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="4b218-130">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="4b218-130">**Message count**</span></span>

<span data-ttu-id="4b218-131">세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4b218-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4b218-132">행을 선택하는 경우 다음과 유사한 세부 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b218-132">If you select a row, similar details are shown in a flyout:</span></span>

![메일 흐름 맵의 세부 정보 표에서 세부 정보 플라이아웃](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="4b218-134">특정 날짜 범위에 대한 보고서에 대한 정보를 한 명 이상의 받는 사람에게 전자 메일로 보내려면 요청 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4b218-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="4b218-135">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4b218-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b218-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b218-136">See also</span></span>

<span data-ttu-id="4b218-137">메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="4b218-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
