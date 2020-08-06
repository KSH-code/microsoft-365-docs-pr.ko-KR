---
title: 메일 흐름 대시보드의 허용 되지 않는 도메인 보고서
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 허용 되지 않는 도메인 보고서를 사용 하 여 보낸 사람의 도메인이 Microsoft 365에 구성 되어 있지 않은 온-프레미스 조직의 메시지를 모니터링 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 649163729bbb73140f9cfb7e75c9fd06f3908cce
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577482"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="cdcb7-103">보안 & 준수 센터의 허용 되지 않는 도메인 보고서</span><span class="sxs-lookup"><span data-stu-id="cdcb7-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="cdcb7-104">보안 & 준수 센터의 [메일 흐름 대시보드의](mail-flow-insights-v2.md) **허용 되지 않는 도메인** 보고서는 보낸 사람의 도메인이 Microsoft 365 조직에서 허용 도메인으로 구성 되지 않은 온-프레미스 전자 메일 조직의 메시지에 대 한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="cdcb7-105">이러한 메시지가 악성 임을 증명 하는 데이터가 있는 경우 Microsoft 365에서 이러한 메시지를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="cdcb7-106">따라서 문제를 파악 하 고 해결 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![보안 & 준수 센터의 메일 흐름 대시보드에 허용 되지 않는 도메인 위젯](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="cdcb7-108">허용 되지 않는 도메인 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="cdcb7-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="cdcb7-109">**허용 되지 않는 도메인** 위젯에 있는 차트를 클릭 하면 **허용 되지 않는 도메인** 보고서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="cdcb7-110">기본적으로 영향을 받는 모든 커넥터에 대 한 활동이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="cdcb7-111">**에 대 한 데이터 표시**를 클릭 하면 드롭다운에서 특정 커넥터를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="cdcb7-112">차트의 데이터 요소 (일)를 가리키면 커넥터에 대 한 총 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![허용 되지 않는 도메인 보고서의 보고서 보기](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="cdcb7-114">허용 되지 않는 도메인 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="cdcb7-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="cdcb7-115">보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="cdcb7-116">**날짜**</span><span class="sxs-lookup"><span data-stu-id="cdcb7-116">**Date**</span></span>
- <span data-ttu-id="cdcb7-117">**인바운드 커넥터 이름**</span><span class="sxs-lookup"><span data-stu-id="cdcb7-117">**Inbound connector name**</span></span>
- <span data-ttu-id="cdcb7-118">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="cdcb7-118">**Sender domain**</span></span>
- <span data-ttu-id="cdcb7-119">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="cdcb7-119">**Message count**</span></span>
- <span data-ttu-id="cdcb7-120">**예제 메시지**: 영향을 받는 메시지의 예제 메시지 id입니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="cdcb7-121">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cdcb7-122">특정 날짜 범위에 대 한 보고서를 한 명 이상의 받는 사람에 게 전자 메일로 전송 하려면 **다운로드 요청**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="cdcb7-123">테이블에서 행을 선택 하면 다음 정보와 함께 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="cdcb7-124">**날짜**</span><span class="sxs-lookup"><span data-stu-id="cdcb7-124">**Date**</span></span>
- <span data-ttu-id="cdcb7-125">**인바운드 커넥터 이름**</span><span class="sxs-lookup"><span data-stu-id="cdcb7-125">**Inbound connector name**</span></span>
- <span data-ttu-id="cdcb7-126">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="cdcb7-126">**Sender domain**</span></span>
- <span data-ttu-id="cdcb7-127">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="cdcb7-127">**Message count**</span></span>
- <span data-ttu-id="cdcb7-128">**예제 메시지**: **예제 메시지 보기** 를 클릭 하 여 영향을 받는 메시지의 예제에 대 한 [메시지 추적](message-trace-scc.md) 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![허용 되지 않는 도메인 보고서의 세부 정보 테이블 보기에서 행을 선택한 후의 세부 정보 플라이 아웃](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="cdcb7-130">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cdcb7-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cdcb7-131">Related topics</span></span>

<span data-ttu-id="cdcb7-132">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
