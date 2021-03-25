---
title: 메일 흐름 지도
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
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 메일 흐름 맵을 사용하여 커넥터를 사용하지 않고도 조직에서 & 흐름을 시각화하고 추적하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206959"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="459cf-103">보안 및 준수 센터의 & 흐름 맵</span><span class="sxs-lookup"><span data-stu-id="459cf-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="459cf-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="459cf-104">**Applies to**</span></span>
- [<span data-ttu-id="459cf-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="459cf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="459cf-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="459cf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="459cf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="459cf-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="459cf-108">보안 **및** 준수 [](mail-flow-insights-v2.md) 센터의 메일 [](https://protection.office.com) 흐름 대시보드에 있는 메일 흐름 & 조직을 통해 메일이 흐르는 방식에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="459cf-109">이 정보를 사용하여 패턴을 학습하고, 오류를 식별하고, 발생할 때 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![보안 및 준수 센터의 메일 흐름 대시보드에서 메일 흐름 & 위젯](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="459cf-111">기본적으로 위젯에는 전날의 메일 흐름 패턴이 Sankey 다이어그램으로 알려진 *차트에* 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="459cf-112">왼쪽 화살표 왼쪽 화살표와 오른쪽 화살표 오른쪽 화살표를 사용하여 다른 일의 정보를 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) 표시하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="459cf-113">각 색은 서로 다른 인바운드 또는 아웃바운드 커넥터를 통해(또는 커넥터를 사용하지 않고) 메일 흐름을 나타내며,</span><span class="sxs-lookup"><span data-stu-id="459cf-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="459cf-114">특정 색 위에 마우스를 대면 해당 유형의 커넥터에 대한 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="459cf-115">메일 흐름 맵에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="459cf-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="459cf-116">메일 흐름 맵 **위젯을** 클릭하면 메일 흐름 지도 **보고서로 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="459cf-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="459cf-117">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="459cf-118">**데이터 표시: 개요:** 이 보기는 기본적으로 위젯의 더 큰 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="459cf-119">특정 색 위에 마우스를 대면 해당 유형의 커넥터에 대한 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![메일 흐름 지도 보고서의 개요 보기](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="459cf-121">**데이터 표시: 세부 정보:** 이 보기에는 커넥터 및 대상 도메인에 대한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="459cf-122">최상위 보낸 사람 및 받는 사람 도메인이 나열되어 나머지는 기타 에 **추가됩니다.**</span><span class="sxs-lookup"><span data-stu-id="459cf-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="459cf-123">특정 색과 섹션 위에 마우스를 대면 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![메일 흐름 지도 보고서의 세부 정보 보기](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="459cf-125">보고서 보기에서 **필터를** 클릭하면 시작 날짜 및  종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="459cf-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="459cf-126">특정 날짜 범위에 대한 보고서를 한명 이상의 받는 사람에게 전자 메일로 보내려면 다운로드 **요청을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="459cf-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="459cf-127">사용 가능한 경우 메일 흐름 맵 아래에 관련 인사이트가 [표시됩니다(예: Fix possible mail loop insight).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="459cf-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="459cf-128">메일 흐름 맵에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="459cf-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="459cf-129">보고서 보기에서 **세부** 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="459cf-130">**날짜**</span><span class="sxs-lookup"><span data-stu-id="459cf-130">**Date**</span></span>
- <span data-ttu-id="459cf-131">**범주**</span><span class="sxs-lookup"><span data-stu-id="459cf-131">**Category**</span></span>
- <span data-ttu-id="459cf-132">**커넥터/타사 서비스 공급자**</span><span class="sxs-lookup"><span data-stu-id="459cf-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="459cf-133">**보낸 사람/받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="459cf-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="459cf-134">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="459cf-134">**Message count**</span></span>

<span data-ttu-id="459cf-135">세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="459cf-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="459cf-136">행을 선택하면 플라이아웃에 유사한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="459cf-136">If you select a row, similar details are shown in a flyout:</span></span>

![메일 흐름 맵의 세부 정보 표에서 세부 정보 플라이아웃](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="459cf-138">특정 날짜 범위에 대한 보고서를 한명 이상의 받는 사람에게 전자 메일로 보내려면 다운로드 **요청을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="459cf-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="459cf-139">보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="459cf-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="459cf-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="459cf-140">See also</span></span>

<span data-ttu-id="459cf-141">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="459cf-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
