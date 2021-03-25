---
title: 메일 흐름 대시보드의 허용되지 않은 도메인 보고서
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
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 허용되지 않는 도메인 보고서를 사용하여 Microsoft 365에서 보낸 사람 도메인이 구성되지 않은 & 조직의 메시지를 모니터링하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206336"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="6a809-103">보안 및 준수 센터의 & 도메인 보고서</span><span class="sxs-lookup"><span data-stu-id="6a809-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6a809-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="6a809-104">**Applies to**</span></span>
- [<span data-ttu-id="6a809-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6a809-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6a809-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="6a809-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6a809-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a809-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6a809-108">[보안](https://protection.office.com) & 준수 센터의 [](mail-flow-insights-v2.md) 메일 흐름 대시보드에 있는 허용되지 않는 도메인 보고서에는 보낸 사람 도메인이 Microsoft 365 조직의 허용 도메인으로 구성되지 않은 사용자의 전자 메일 조직에서 보낸 메시지에 대한 정보가 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="6a809-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="6a809-109">Microsoft 365는 이러한 메시지의 의도가 악성일 수 있는 것으로 증명할 데이터가 있는 경우 이러한 메시지를 스로틀할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a809-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="6a809-110">따라서 어떤 일이 일어나는지 이해하고 문제를 해결하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a809-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![보안 및 준수 센터의 메일 흐름 대시보드에서 허용되지 & 위젯](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="6a809-112">허용되지 않는 도메인 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="6a809-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="6a809-113">허용되지 않은 도메인  위젯에서 차트를 클릭하면 허용되지 않은 도메인 **보고서로 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6a809-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="6a809-114">기본적으로 영향을 받는 모든 커넥터에 대한 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a809-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="6a809-115">에 대한 **데이터 표시를** 클릭하면 드롭다운에서 특정 커넥터를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a809-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="6a809-116">차트에서 데이터 포인트(일)를 마우스로 마우스로 대면 커넥터의 총 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a809-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![허용되지 않는 도메인 보고서의 보고서 보기](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="6a809-118">허용되지 않는 도메인 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="6a809-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="6a809-119">보고서 보기에서 **세부** 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a809-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="6a809-120">**날짜**</span><span class="sxs-lookup"><span data-stu-id="6a809-120">**Date**</span></span>
- <span data-ttu-id="6a809-121">**인바운드 커넥터 이름**</span><span class="sxs-lookup"><span data-stu-id="6a809-121">**Inbound connector name**</span></span>
- <span data-ttu-id="6a809-122">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="6a809-122">**Sender domain**</span></span>
- <span data-ttu-id="6a809-123">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="6a809-123">**Message count**</span></span>
- <span data-ttu-id="6a809-124">**샘플 메시지:** 영향을 받는 메시지 샘플의 메시지 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6a809-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="6a809-125">세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a809-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6a809-126">특정 날짜 범위에 대한 보고서를 한명 이상의 받는 사람에게 전자 메일로 보내려면 다운로드 **요청을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a809-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="6a809-127">표에서 행을 선택하면 다음과 같은 정보가 있는 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a809-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="6a809-128">**날짜**</span><span class="sxs-lookup"><span data-stu-id="6a809-128">**Date**</span></span>
- <span data-ttu-id="6a809-129">**인바운드 커넥터 이름**</span><span class="sxs-lookup"><span data-stu-id="6a809-129">**Inbound connector name**</span></span>
- <span data-ttu-id="6a809-130">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="6a809-130">**Sender domain**</span></span>
- <span data-ttu-id="6a809-131">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="6a809-131">**Message count**</span></span>
- <span data-ttu-id="6a809-132">**샘플 메시지:** 샘플  메시지 보기를 클릭하여 [](message-trace-scc.md) 영향을 받는 메시지의 샘플에 대한 메시지 추적 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a809-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![허용되지 않는 도메인 보고서의 세부 정보 테이블 보기에서 행을 선택한 후의 세부 정보 플라이아웃](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="6a809-134">보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a809-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a809-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6a809-135">Related topics</span></span>

<span data-ttu-id="6a809-136">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="6a809-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
