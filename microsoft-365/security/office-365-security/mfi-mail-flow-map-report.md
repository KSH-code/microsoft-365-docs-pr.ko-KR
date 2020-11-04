---
title: 메일 흐름 지도
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
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 메일 흐름 맵을 사용 하 여 커넥터를 통해 메일을 주고 받지 않는 커넥터를 사용 하는 방법을 시각화 하 고 추적 하는 방법을 알아봅니다.
ms.openlocfilehash: fc03f05db77c40dbf726692e6fb6069d587a5ffc
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877768"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="fc1f2-103">보안 & 준수 센터의 메일 흐름 맵</span><span class="sxs-lookup"><span data-stu-id="fc1f2-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fc1f2-104">[보안 & 준수 센터](https://protection.office.com) 의 메일 흐름 [대시보드의](mail-flow-insights-v2.md) **메일 흐름 맵은** 조직에서 메일이 흐르는 방식에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="fc1f2-105">이 정보를 사용 하 여 패턴을 파악 하 고, 상황을 식별 하 고, 문제가 발생 하면 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![보안 & 준수 센터의 메일 흐름 대시보드의 메일 흐름 맵 위젯](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="fc1f2-107">기본적으로 위젯은 *Sankey* 다이어그램 이라고 하는 차트에서 이전 날짜의 메일 흐름 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="fc1f2-108">왼쪽 화살표 ![ 왼쪽 화살표 ](../../media/scc-left-arrow.png) 및 오른쪽 화살표 오른쪽 화살표를 사용 ![ 하 여 ](../../media/scc-right-arrow.png) 다른 요일의 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="fc1f2-109">각각의 다른 색은 다른 인바운드 또는 아웃 바운드 커넥터 (또는 커넥터를 사용 하지 않고)에 대 한 메일 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="fc1f2-110">특정 색을 가리키면 해당 연결선 종류에 대 한 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="fc1f2-111">메일 흐름 맵의 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="fc1f2-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="fc1f2-112">**메일 흐름 맵** 위젯을 클릭 하면 **메일 흐름 맵** 보고서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="fc1f2-113">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fc1f2-114">**데이터 표시: 개요** :이는 기본적으로 더 큰 위젯의 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-114">**Show data for: Overview** : This is basically a larger view of the widget.</span></span> <span data-ttu-id="fc1f2-115">특정 색을 가리키면 해당 연결선 종류에 대 한 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![메일 흐름 맵 보고서의 개요 보기](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="fc1f2-117">**데이터 표시: 세부** 정보:이 보기에는 커넥터 및 대상 도메인에 대 한 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-117">**Show data for: Detail** : This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="fc1f2-118">상위 보낸 사람 및 받는 사람 도메인이 나열 되 고 나머지는 **다른 사용자에 게** 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="fc1f2-119">특정 색과 섹션을 가리키면 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![메일 흐름 맵 보고서의 세부 정보 보기](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="fc1f2-121">보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fc1f2-122">특정 날짜 범위에 대 한 보고서를 한 명 이상의 받는 사람에 게 전자 메일로 전송 하려면 **다운로드 요청** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="fc1f2-123">사용 가능한 경우 메일 흐름 맵 (예: [가능한 메일 루프 통찰력 파악](mfi-mail-loop-insight.md))에 관련 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="fc1f2-124">메일 흐름 맵에 대 한 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="fc1f2-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="fc1f2-125">보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="fc1f2-126">**날짜**</span><span class="sxs-lookup"><span data-stu-id="fc1f2-126">**Date**</span></span>
- <span data-ttu-id="fc1f2-127">**범주**</span><span class="sxs-lookup"><span data-stu-id="fc1f2-127">**Category**</span></span>
- <span data-ttu-id="fc1f2-128">**커넥터/타사 서비스 공급자**</span><span class="sxs-lookup"><span data-stu-id="fc1f2-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="fc1f2-129">**보낸 사람/받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="fc1f2-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="fc1f2-130">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="fc1f2-130">**Message count**</span></span>

<span data-ttu-id="fc1f2-131">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fc1f2-132">행을 선택 하는 경우 플라이 아웃에 다음과 유사한 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-132">If you select a row, similar details are shown in a flyout:</span></span>

![메일 흐름 맵의 세부 정보 테이블에서의 정보 플라이 아웃](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="fc1f2-134">특정 날짜 범위에 대 한 보고서를 한 명 이상의 받는 사람에 게 전자 메일로 전송 하려면 **다운로드 요청** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="fc1f2-135">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc1f2-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc1f2-136">See also</span></span>

<span data-ttu-id="fc1f2-137">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc1f2-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
