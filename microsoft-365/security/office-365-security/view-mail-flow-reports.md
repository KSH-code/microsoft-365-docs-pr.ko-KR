---
title: 보고서 대시보드에서 메일 흐름 보고서 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 준수 센터에서 보고서 대시보드에 사용할 수 있는 메일 흐름 보고서에 대해 & 있습니다.
ms.custom: ''
ms.openlocfilehash: 9e9249eab5d3519dac0e33acf40d600d471b7cb2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826460"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="6a07d-103">보안 규정 준수 센터의 보고서 대시보드에서 메일 & 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="6a07d-104">보안 & 준수 센터의 메일 흐름 대시보드에서 사용할 수 [있는 메일 흐름](mail-flow-insights-v2.md) 보고서 외에도 Microsoft 365 조직을 모니터링 하는 데 도움이 되는 보고서 대시보드에서 다양한 추가 메일 흐름 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="6a07d-105">필요한 권한이 있는 [경우 보고서 대시보드로](#what-permissions-are-needed-to-view-these-reports)이동하여 [보안 센터에서 & 이러한 보고서를](https://office.protection.com) 볼 **수** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="6a07d-106">보고서 대시보드로 직접 이동하려면 <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="6a07d-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Security Center의 보고서 & 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="6a07d-108">커넥터 보고서</span><span class="sxs-lookup"><span data-stu-id="6a07d-108">Connector report</span></span>

<span data-ttu-id="6a07d-109">커넥터 **보고서는** 조직에 대해 구성된 [인바운드 및 아웃바운드 커넥터에서의](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 메일 흐름 활동을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="6a07d-110">보고서를 보려면 준수 센터에서 [보안 & 보고서](https://protection.office.com)대시보드로 **Reports** \> **이동하여 커넥터** **보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="6a07d-111">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="6a07d-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![보고서 대시보드의 커넥터 보고서 위리인](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="6a07d-113">커넥터 보고서의 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-113">Report view for the Connector report</span></span>

<span data-ttu-id="6a07d-114">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="6a07d-115">**데이터 보기: 메일 흐름:** 이 차트에는 다음과 같이 구성된 인바운드 및 아웃바운드 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="6a07d-116">**합계**</span><span class="sxs-lookup"><span data-stu-id="6a07d-116">**Total**</span></span>
  - <span data-ttu-id="6a07d-117">**커넥터 없이 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="6a07d-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="6a07d-118">**커넥터 없이 인터넷으로 연결**</span><span class="sxs-lookup"><span data-stu-id="6a07d-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="6a07d-119">구성한 특정 커넥터</span><span class="sxs-lookup"><span data-stu-id="6a07d-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="6a07d-120">차트의 데이터를 격리하려면 컨트롤에 대한 **데이터 표시 컨트롤을** 사용하여 이러한 옵션 중 하나 또는 모든 메일 **흐름을 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![커넥터 보고서에서 메일 흐름별 데이터 보기](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="6a07d-122">**데이터 보기:TLS 사용: 이**차트는 메일 흐름에 대한 TLS(전송 계층 보안) 버전 사용의 백분율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="6a07d-123">차트의 데이터를 격리하려면 컨트롤의 **표시 데이터를 사용하여** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="6a07d-124">**모든 메일 흐름**</span><span class="sxs-lookup"><span data-stu-id="6a07d-124">**All mail flow**</span></span>
  - <span data-ttu-id="6a07d-125">**커넥터 없이 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="6a07d-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="6a07d-126">**커넥터 없이 인터넷으로 연결**</span><span class="sxs-lookup"><span data-stu-id="6a07d-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="6a07d-127">구성한 특정 커넥터</span><span class="sxs-lookup"><span data-stu-id="6a07d-127">A specific connector that you've configured.</span></span>

  ![커넥터 보고서에서 TLS 사용을 사용하여 데이터 보기](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="6a07d-129">보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="6a07d-130">커넥터 보고서의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-130">Details table view for the Connector report</span></span>

<span data-ttu-id="6a07d-131">보고서 보기에서 **세부 정보 표를** 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="6a07d-132">**날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-132">**Date**</span></span>
- <span data-ttu-id="6a07d-133">**커넥터 방향 및 이름**</span><span class="sxs-lookup"><span data-stu-id="6a07d-133">**Connector direction and name**</span></span>
- <span data-ttu-id="6a07d-134">**커넥터 유형**</span><span class="sxs-lookup"><span data-stu-id="6a07d-134">**Connector type**</span></span>
- <span data-ttu-id="6a07d-135">**강요된 TLS?**: **True** 또는 False **값입니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="6a07d-136">**TLS** 없음(비율)</span><span class="sxs-lookup"><span data-stu-id="6a07d-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="6a07d-137">**TLS** 1.0(백분율)</span><span class="sxs-lookup"><span data-stu-id="6a07d-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="6a07d-138">**TLS** 1.1(백분율)</span><span class="sxs-lookup"><span data-stu-id="6a07d-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="6a07d-139">**TLS** 1.2(백분율)</span><span class="sxs-lookup"><span data-stu-id="6a07d-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="6a07d-140">**볼륨**: 메시지의 수</span><span class="sxs-lookup"><span data-stu-id="6a07d-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="6a07d-141">세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6a07d-142">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="6a07d-143">Exchange 전송 규칙 보고서</span><span class="sxs-lookup"><span data-stu-id="6a07d-143">Exchange transport rule report</span></span>

<span data-ttu-id="6a07d-144">**Exchange 전송 규칙 보고서는** 조직에서 들어오고 나가는 메시지에 대한 메일 흐름 규칙(전송 규칙이라고도 함)의 영향을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="6a07d-145">보고서를 보려면 보안 서비스 관리 [& 만들고 보고서](https://protection.office.com)대시보드로 **이동한** \> **다음 Exchange 전송** **규칙을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="6a07d-146">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="6a07d-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![보고서 대시보드의 Exchange 전송 규칙 위과 위산](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="6a07d-148">Exchange 전송 규칙 보고서의 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="6a07d-149">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="6a07d-150">**다음을 사용하자 데이터 보기: Exchange 전송 규칙** \> **분석: 이 차트에는**전송 규칙의 영향을 **받은** 인바운드 및 아웃바운드 메시지 수가 표시됩니다. **Outbound**</span><span class="sxs-lookup"><span data-stu-id="6a07d-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="6a07d-151">**다음을 사용하자 데이터 보기: Exchange 전송 규칙** \> **분석: 심각도: 이**차트는 높은 **심각도 및** **중간 심각도,** 낮은 심각도 메시지 **수를 표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="6a07d-152">심각도 수준을 규칙에서 작업으로**설정합니다(심각도 수준 또는** _SetAuditSeverity를 사용하여 이 규칙 감사)._</span><span class="sxs-lookup"><span data-stu-id="6a07d-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="6a07d-153">자세한 내용은 [Exchange Online에서 메일 흐름 규칙 작업을 참조하세요.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="6a07d-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="6a07d-154">**DLP Exchange 전송 규칙별 데이터 보기** \> **분석: 이**차트에는 DLP(데이터 **Inbound** 손실 방지) 전송 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지 수가 표시됩니다. **Outbound**</span><span class="sxs-lookup"><span data-stu-id="6a07d-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="6a07d-155">다음 옵션 중에서 선택한 선택하더라도 차트를 더 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="6a07d-156">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="6a07d-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="6a07d-157">**데이터 표시: 보안 사용자 보안**</span><span class="sxs-lookup"><span data-stu-id="6a07d-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="6a07d-158">**미국(국가)에 대한 데이터 미만을 보냅니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="6a07d-159">**DLP Exchange 전송 규칙별 데이터 보기** \> **분석: 이 보기에는**DLP 전송 **규칙의 영향을** 받은 심각도 및 **Low severity** **중간**심각도 및 낮은 심각도 메시지의 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="6a07d-160">다음 옵션 중에서 선택한 선택하더라도 차트를 더 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="6a07d-161">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="6a07d-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="6a07d-162">**데이터 표시: 보안 사용자 보안**</span><span class="sxs-lookup"><span data-stu-id="6a07d-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="6a07d-163">**미국(국가)에 대한 데이터 미만을 보냅니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="6a07d-164">보고서 보기에서 **필터를** 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="6a07d-165">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="6a07d-166">방향 값</span><span class="sxs-lookup"><span data-stu-id="6a07d-166">Direction values</span></span>
- <span data-ttu-id="6a07d-167">심각도 값</span><span class="sxs-lookup"><span data-stu-id="6a07d-167">Severity values</span></span>

![Exchange 전송 규칙 보고서의 보고서 보기](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="6a07d-169">Exchange 전송 규칙 보고서의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="6a07d-170">세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="6a07d-171">**다음을 사용한 데이터 보기: Exchange 전송 규칙:**</span><span class="sxs-lookup"><span data-stu-id="6a07d-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="6a07d-172">**날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-172">**Date**</span></span>
  - <span data-ttu-id="6a07d-173">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="6a07d-173">**Transport rule**</span></span>
  - <span data-ttu-id="6a07d-174">**제목**</span><span class="sxs-lookup"><span data-stu-id="6a07d-174">**Subject**</span></span>
  - <span data-ttu-id="6a07d-175">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="6a07d-175">**Sender address**</span></span>
  - <span data-ttu-id="6a07d-176">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="6a07d-176">**Recipient address**</span></span>
  - <span data-ttu-id="6a07d-177">**심각도**</span><span class="sxs-lookup"><span data-stu-id="6a07d-177">**Severity**</span></span>
  - <span data-ttu-id="6a07d-178">**방향**</span><span class="sxs-lookup"><span data-stu-id="6a07d-178">**Direction**</span></span>

- <span data-ttu-id="6a07d-179">**DLP Exchange 전송 규칙: 사용자별 데이터 보기:**</span><span class="sxs-lookup"><span data-stu-id="6a07d-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="6a07d-180">**날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-180">**Date**</span></span>
  - <span data-ttu-id="6a07d-181">**DLP 정책**</span><span class="sxs-lookup"><span data-stu-id="6a07d-181">**DLP policy**</span></span>
  - <span data-ttu-id="6a07d-182">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="6a07d-182">**Transport rule**</span></span>
  - <span data-ttu-id="6a07d-183">**제목**</span><span class="sxs-lookup"><span data-stu-id="6a07d-183">**Subject**</span></span>
  - <span data-ttu-id="6a07d-184">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="6a07d-184">**Sender address**</span></span>
  - <span data-ttu-id="6a07d-185">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="6a07d-185">**Recipient address**</span></span>
  - <span data-ttu-id="6a07d-186">**심각도**</span><span class="sxs-lookup"><span data-stu-id="6a07d-186">**Severity**</span></span>
  - <span data-ttu-id="6a07d-187">**방향**</span><span class="sxs-lookup"><span data-stu-id="6a07d-187">**Direction**</span></span>

<span data-ttu-id="6a07d-188">세부 정보 표 **보기에서** 필터를 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="6a07d-189">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="6a07d-190">방향 값</span><span class="sxs-lookup"><span data-stu-id="6a07d-190">Direction values</span></span>
- <span data-ttu-id="6a07d-191">심각도 값</span><span class="sxs-lookup"><span data-stu-id="6a07d-191">Severity values</span></span>

<span data-ttu-id="6a07d-192">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="6a07d-193">전달 보고서</span><span class="sxs-lookup"><span data-stu-id="6a07d-193">Forwarding report</span></span>

<span data-ttu-id="6a07d-194">전달 **보고서에는 Exchange** Online 사서함에서 외부 도메인으로 자동으로 전달된 조직의 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="6a07d-195">전달된 메시지는 보안 또는 규정 준수 위험을 일어받을 수 있기며 계정이 노출된 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="6a07d-196">보고서를 보려면 준수 센터에서 [보안 & 보고서](https://protection.office.com) **대시보드로** \> **이동한 후** 전달 **보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="6a07d-197">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="6a07d-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![보고서 대시보드에서 보고서 위도를 전달합니다.](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="6a07d-199">전달 보고서의 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="6a07d-200">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="6a07d-201">**데이터 표시: 전달 메서드:** 다음 메서드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="6a07d-202">**전송 규칙:** 메일 흐름 [규칙이라고도 알려진 전송 규칙.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="6a07d-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="6a07d-203">**사서함 규칙:** 받은 편지함 [규칙이라고도 함](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)규칙.</span><span class="sxs-lookup"><span data-stu-id="6a07d-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![전달 보고서의 전달 방법 보기](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="6a07d-205">**데이터 가져오기: 전달 도메인:** 이 보기에는 전달 대상에 해당하는 받는 사람 도메인이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![전달 보고서의 전달 도메인 보기](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="6a07d-207">**데이터 표시: 전달자:** 다음 전달자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="6a07d-208">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="6a07d-208">**Transport rule**</span></span>
  - <span data-ttu-id="6a07d-209">전달 받은 편지함 규칙이 들어 있는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![전달 보고서의 전달자 보기](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="6a07d-211">보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="6a07d-212">전달 보고서의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="6a07d-213">보고서 보기에서 **세부 정보 표를** 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="6a07d-214">**전달자:** 전달 받은 **편지함** 규칙이 포함되어 있는 사서함 또는 가치 전송 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="6a07d-215">**전달 유형:** 값 사서함 **규칙 또는** **전송 규칙.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="6a07d-216">**받는 사람 이름**</span><span class="sxs-lookup"><span data-stu-id="6a07d-216">**Recipient name**</span></span>
- <span data-ttu-id="6a07d-217">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="6a07d-217">**Recipient domain**</span></span>
- <span data-ttu-id="6a07d-218">**세부**정보: 메일 흐름 규칙의 GUID 값 또는 받은 편지함 규칙의 RuleIdentity 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="6a07d-219">**개수**</span><span class="sxs-lookup"><span data-stu-id="6a07d-219">**Count**</span></span>
- <span data-ttu-id="6a07d-220">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-220">**First forward date**</span></span>

<span data-ttu-id="6a07d-221">세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6a07d-222">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="6a07d-223">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="6a07d-223">Mailflow status report</span></span>

<span data-ttu-id="6a07d-224">메일 **흐름 상태 보고서는 보낸 후** 받은 전자 메일 [보고서와](#sent-and-received-email-report)비슷하지만, Edge에서 허용하거나 차단하는 방법에 대한 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="6a07d-225">Edge 보호 정보를 포함하는 유일한 보고서이며 EOP(Exchange Online Protection)에서 평가를 위해 서비스로 허용되기 전에 차단되는 전자 메일의 양만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="6a07d-226">메시지를 받는 사람 5명에게 보낼 경우 메시지 하나가 5명인 다른 메시지로 계산된다는 점을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="6a07d-227">보고서를 보려면 보안 센터에서 [& 만들고 보고서](https://protection.office.com) **대시보드로** \> **이동한 후 메일** 흐름 상태 **보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="6a07d-228">메일 흐름 상태 보고서로 **직접 이동하려면 을**엽니다. <https://protection.office.com/mailflowStatusReport></span><span class="sxs-lookup"><span data-stu-id="6a07d-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![보고서 대시보드의 메일 흐름 상태 보고서 위리인](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="6a07d-230">메일 흐름 상태 보고서의 유형 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="6a07d-231">보고서를 열면 기본적으로 **Type(종류)** 탭이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="6a07d-232">기본적으로 이 보기에는 다음과 같은 필터로 구성된 차트와 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="6a07d-233">**날짜**: 지난 7일</span><span class="sxs-lookup"><span data-stu-id="6a07d-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="6a07d-234">**Direction**:</span><span class="sxs-lookup"><span data-stu-id="6a07d-234">**Direction**:</span></span>

  - <span data-ttu-id="6a07d-235">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="6a07d-235">**Inbound**</span></span>
  - <span data-ttu-id="6a07d-236">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="6a07d-236">**Outbound**</span></span>
  - <span data-ttu-id="6a07d-237">**조직 내: 이**수는 테넌트 내의 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="6a07d-238">보낸 abc@domain.com 사람 번호(인바운드 및 xyz@domain.com 아웃바운드에서 별도로 **계산)를 받는** 사람 **번호로 보내기**</span><span class="sxs-lookup"><span data-stu-id="6a07d-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="6a07d-239">**Type**:</span><span class="sxs-lookup"><span data-stu-id="6a07d-239">**Type**:</span></span>

  - <span data-ttu-id="6a07d-240">**정상 메일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-240">**Good mail**</span></span>
  - <span data-ttu-id="6a07d-241">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="6a07d-241">**Malware**</span></span>
  - <span data-ttu-id="6a07d-242">**스팸**</span><span class="sxs-lookup"><span data-stu-id="6a07d-242">**Spam**</span></span>
  - <span data-ttu-id="6a07d-243">**Edge 보호**</span><span class="sxs-lookup"><span data-stu-id="6a07d-243">**Edge protection**</span></span>
  - <span data-ttu-id="6a07d-244">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="6a07d-244">**Rule messages**</span></span>
  - <span data-ttu-id="6a07d-245">**피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-245">**Phishing email**</span></span>

<span data-ttu-id="6a07d-246">차트가 Type 값을 사용하여 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="6a07d-247">필터를 클릭하거나 차트 **범례에서** 값을 클릭하여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="6a07d-248">데이터 테이블에는 다음과 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-248">The data table contains the following information:</span></span>

- <span data-ttu-id="6a07d-249">**방향**</span><span class="sxs-lookup"><span data-stu-id="6a07d-249">**Direction**</span></span>
- <span data-ttu-id="6a07d-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="6a07d-250">**Type**</span></span>
- <span data-ttu-id="6a07d-251">**24시간**</span><span class="sxs-lookup"><span data-stu-id="6a07d-251">**24 hours**</span></span>
- <span data-ttu-id="6a07d-252">**3일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-252">**3 days**</span></span>
- <span data-ttu-id="6a07d-253">**7일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-253">**7 days**</span></span>
- <span data-ttu-id="6a07d-254">**15일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-254">**15 days**</span></span>
- <span data-ttu-id="6a07d-255">**30일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-255">**30 days**</span></span>

<span data-ttu-id="6a07d-256">자세한 **정보를 보기 위해 범주를 선택할 경우**다음 값 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="6a07d-257">**피싱 전자 메일:** 이 기능을 선택하면 위협 방지 상태 [보고서로 이동됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="6a07d-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="6a07d-258">**전자 메일의 맬웨어:** 이 선택을 선택하면 위협 방지 상태 [보고서로 이동됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="6a07d-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="6a07d-259">**스팸 검색:** 이 선택 항목을 사용하면 스팸 검색 [보고서로 이동됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="6a07d-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="6a07d-260">**Edge 차단된 스팸:** 이 선택 항목을 선택하면 스팸 [검색 보고서로 이동합니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="6a07d-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="6a07d-261">**Export**:</span><span class="sxs-lookup"><span data-stu-id="6a07d-261">**Export**:</span></span>

<span data-ttu-id="6a07d-262">세부 정보 보기의 경우 한 날짜에 한 번만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="6a07d-263">따라서 7일 동안 데이터를 내보내려면 7가지 다른 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="6a07d-264">내보낸 각 .csv 파일은 150,000개의 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="6a07d-265">해당 날짜의 데이터에 15만 개보다 많은 행이 포함되어 있는 경우 여러 개의 .csv 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="6a07d-266">메일 흐름 상태 보고서의 유형 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="6a07d-267">메일 흐름 상태 보고서의 방향 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="6a07d-268">방향 탭을 **클릭하면** 유형 보기의 동일한 기본 **필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="6a07d-269">차트가 Direction 값으로 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="6a07d-270">필터를 클릭하거나 차트 **범례에서** 값을 클릭하여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="6a07d-271">형식 보기의 동일한 **필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="6a07d-272">데이터 테이블에는 형식 보기의 동일한 정보가 **포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="6a07d-273">이 **범주에서 사용 가능한 더 자세한 선택** 항목 및 동작에 대한 범주선택은 유형 보기와 **같습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="6a07d-274">**Export**:</span><span class="sxs-lookup"><span data-stu-id="6a07d-274">**Export**:</span></span>

<span data-ttu-id="6a07d-275">세부 정보 보기의 경우 한 날짜에 한 번만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="6a07d-276">따라서 7일 동안 데이터를 내보내려면 7가지 다른 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="6a07d-277">내보낸 각 .csv 파일은 150,000개의 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="6a07d-278">해당 날짜의 데이터에 15만 개보다 많은 행이 포함되어 있는 경우 여러 개의 .csv 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="6a07d-279">메일 흐름 상태 보고서의 방향 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="6a07d-280">메일 흐름 상태 보고서의 Funnel 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="6a07d-281">금지 **보기에서는** Microsoft의 전자 메일 위협 방지 기능으로 조직 내 수신 및 보내는 전자 메일을 필터링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="6a07d-282">이 표에서는 총 전자 메일 수와 Edge 보호, 맬웨어 방지, 피싱 방지, 스팸 방지 및 스푸핑 방지를 비롯한 구성된 위협 보호 기능이 이 개수에 미치는 영향에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="6a07d-283">기본적으로 이 **보기에 포함된 새로운** 탭과 다음과 같은 필터로 구성된 데이터 테이블이 이 보기에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="6a07d-284">**날짜**: 지난 7일</span><span class="sxs-lookup"><span data-stu-id="6a07d-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="6a07d-285">**Direction**:</span><span class="sxs-lookup"><span data-stu-id="6a07d-285">**Direction**:</span></span>

  - <span data-ttu-id="6a07d-286">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="6a07d-286">**Inbound**</span></span>
  - <span data-ttu-id="6a07d-287">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="6a07d-287">**Outbound**</span></span>
  - <span data-ttu-id="6a07d-288">**조직 내: 테넌트**내에서 보낸 메시지에 대한 수입니다. 다시 보낸 사람 주소는 abc@domain.com 사람 주소(인바운드 및 xyz@domain.com 아웃바운드에서 별도로 계산됨)에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="6a07d-289">집계 보기 및 데이터 테이블 보기에서는 90일 동안 필터링이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="6a07d-290">**Filter를 클릭하면**차트 및 데이터 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="6a07d-291">이 차트에는 다음과 같이 구성된 전자 메일 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="6a07d-292">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-292">**Total email**</span></span>
- <span data-ttu-id="6a07d-293">**Edge 보호 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-293">**Email after edge protection**</span></span>
- <span data-ttu-id="6a07d-294">**Email after anti-malware, file reputation, file type block**</span><span class="sxs-lookup"><span data-stu-id="6a07d-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="6a07d-295">**피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지 후의 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="6a07d-296">**스팸 방지 후의 전자 메일, 대량 메일 필터링**</span><span class="sxs-lookup"><span data-stu-id="6a07d-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="6a07d-297">사용자 및 도메인 가장 1 **이후의**<sup>전자 메일</sup></span><span class="sxs-lookup"><span data-stu-id="6a07d-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="6a07d-298">**파일 및 URL 디온 1 이후의**<sup>메일</sup></span><span class="sxs-lookup"><span data-stu-id="6a07d-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="6a07d-299">**배달 후 보호 후 검색된 전자 메일(URL 클릭 시간 보호)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="6a07d-300"><sup>1</sup> Office 365 ATP만</span><span class="sxs-lookup"><span data-stu-id="6a07d-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="6a07d-301">EOP 또는 ATP를 사용하여 별도로 필터링된 전자 메일을 표시하려면 차트 범례에서 값을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="6a07d-302">데이터 테이블에는 내내의 날짜 순서대로 표시된 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="6a07d-303">**날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-303">**Date**</span></span>
- <span data-ttu-id="6a07d-304">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-304">**Total email**</span></span>
- <span data-ttu-id="6a07d-305">**Edge 보호**</span><span class="sxs-lookup"><span data-stu-id="6a07d-305">**Edge protection**</span></span>
- <span data-ttu-id="6a07d-306">**맬웨어 방지, 파일 신뢰도, 파일 형식 차단**</span><span class="sxs-lookup"><span data-stu-id="6a07d-306">**Anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="6a07d-307">**피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지**</span><span class="sxs-lookup"><span data-stu-id="6a07d-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="6a07d-308">**스팸 방지, 대량 메일 필터링**</span><span class="sxs-lookup"><span data-stu-id="6a07d-308">**Anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="6a07d-309">**사용자 및 도메인 가장(ATP)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-309">**User and domain impersonation (ATP)**</span></span>
- <span data-ttu-id="6a07d-310">**파일 및 URL 디터와이션(ATP)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-310">**File and URL detonation (ATP)**</span></span>
- <span data-ttu-id="6a07d-311">**POST-Delivery Protection and ZAP(ATP) 또는 ZAP(ZAP)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="6a07d-312">데이터 테이블에서 행을 선택하면 전자 메일 수에 대한 추가 분석이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="6a07d-313">**Export**:</span><span class="sxs-lookup"><span data-stu-id="6a07d-313">**Export**:</span></span>

<span data-ttu-id="6a07d-314">옵션에서 **내보내기를** **클릭한 후에는**다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="6a07d-315">**요약(가장 최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="6a07d-316">**세부 정보(지난 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="6a07d-317">날짜 **아래에서**범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="6a07d-318">현재 필터의 데이터는 .csv 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="6a07d-319">내보낸 각 .csv 파일은 150,000개의 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="6a07d-320">데이터에 15만 개보다 많은 행이 포함되어 있는 경우 여러 .csv 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="6a07d-321">메일 흐름 상태 보고서의 Funnel 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="6a07d-322">메일 흐름 상황 보고서기술 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="6a07d-323">기술 **보기는** 새로운 **보기와 비슷하며, 구성된** 위협 방지 기능에 대한 더 세부 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="6a07d-324">차트에서 다양한 위협 방지 단계에서 메시지가 분류되는 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="6a07d-325">기본적으로 Tech **보기 탭을** 클릭하면 이 보기에는 다음과 같은 필터를 사용하여 구성된 차트 및 데이터 테이블이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="6a07d-326">**날짜**: 지난 7일</span><span class="sxs-lookup"><span data-stu-id="6a07d-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="6a07d-327">**Direction**:</span><span class="sxs-lookup"><span data-stu-id="6a07d-327">**Direction**:</span></span>

  - <span data-ttu-id="6a07d-328">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="6a07d-328">**Inbound**</span></span>
  - <span data-ttu-id="6a07d-329">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="6a07d-329">**Outbound**</span></span>
  - <span data-ttu-id="6a07d-330">**조직 내: 이**수는 테넌트 내의 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="6a07d-331">보낸 abc@domain.com 사람 이름(인바운드 및 xyz@domain.com 아웃바운드에서 별도로 계산)을 통해 받는 사람 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="6a07d-332">집계 보기 및 데이터 테이블 보기에서는 90일 동안 필터링이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="6a07d-333">**Filter를 클릭하면**차트 및 데이터 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="6a07d-334">이 차트에는 다음 범주로 구성된 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-334">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="6a07d-335">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-335">**Total email**</span></span>
- <span data-ttu-id="6a07d-336">**Edge 허용, 에지 필터링**</span><span class="sxs-lookup"><span data-stu-id="6a07d-336">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="6a07d-337">**맬웨어가 아오오고 ATP(안전한 첨부 파일 검색), 맬웨어 방지 엔진 검색, 규칙 차단**</span><span class="sxs-lookup"><span data-stu-id="6a07d-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="6a07d-338">**피싱, DMARC 실패, 가장 감지, 스푸핑 탐지, 피싱 탐지**</span><span class="sxs-lookup"><span data-stu-id="6a07d-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="6a07d-339">**URL 감각이 포함된 검색, URL 감지(ATP)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="6a07d-340">**스팸이 아지 지 않습니다, 스팸**</span><span class="sxs-lookup"><span data-stu-id="6a07d-340">**Not spam, spam**</span></span>
- <span data-ttu-id="6a07d-341">**악성이 아닌 이메일, ATP(안전한 링크 검색), ZAP**</span><span class="sxs-lookup"><span data-stu-id="6a07d-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="6a07d-342">차트에서 범주 위에 위로 가리면 해당 범주의 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="6a07d-343">데이터 테이블에는 내내의 날짜 순서대로 표시된 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-343">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="6a07d-344">**날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-344">**Date**</span></span>
- <span data-ttu-id="6a07d-345">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-345">**Total email**</span></span>
- <span data-ttu-id="6a07d-346">**Edge 필터링됨**</span><span class="sxs-lookup"><span data-stu-id="6a07d-346">**Edge filtered**</span></span>
- <span data-ttu-id="6a07d-347">**맬웨어 방지 엔진, 안전한 첨부 파일, 규칙 필터링됨**</span><span class="sxs-lookup"><span data-stu-id="6a07d-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
- <span data-ttu-id="6a07d-348">**DMARC, 가장, 스푸핑, 피싱 필터링**</span><span class="sxs-lookup"><span data-stu-id="6a07d-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
- <span data-ttu-id="6a07d-349">**URL 감지**</span><span class="sxs-lookup"><span data-stu-id="6a07d-349">**URL detonation detection**</span></span>
- <span data-ttu-id="6a07d-350">**스팸 방지 필터링됨**</span><span class="sxs-lookup"><span data-stu-id="6a07d-350">**Anti-spam filtered**</span></span>
- <span data-ttu-id="6a07d-351">**ZAP 제거됨**</span><span class="sxs-lookup"><span data-stu-id="6a07d-351">**ZAP removed**</span></span>
- <span data-ttu-id="6a07d-352">**안전한 링크로 검색**</span><span class="sxs-lookup"><span data-stu-id="6a07d-352">**Detection by safe links**</span></span>

<span data-ttu-id="6a07d-353">데이터 테이블에서 행을 선택하면 전자 메일 수에 대한 추가 분석이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="6a07d-354">**Export**:</span><span class="sxs-lookup"><span data-stu-id="6a07d-354">**Export**:</span></span>

<span data-ttu-id="6a07d-355">내보내기를 **클릭하고**옵션 **아래에서** 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="6a07d-356">**요약(가장 최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="6a07d-357">**세부 정보(지난 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="6a07d-358">날짜 **아래에서**범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="6a07d-359">현재 필터의 데이터는 .csv 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="6a07d-360">내보낸 각 .csv 파일은 150,000개의 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="6a07d-361">데이터에 15만 개보다 많은 행이 포함되어 있는 경우 여러 .csv 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="6a07d-362">메일 흐름 상태 보고서의 Tech 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="6a07d-363">보낸 메일 및 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="6a07d-363">Sent and received email report</span></span>

<span data-ttu-id="6a07d-364">보낸 **및 받은 전자 메일 보고서는** 스팸 탐지, 맬웨어 및 "스팸"으로 확인된 전자 메일을 비롯한 수신 및 보내는 전자 메일에 대한 정보를 보여 주는 스마트 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="6a07d-365">이 보고서와 메일 흐름 상태 보고서의 차이점은 [Edge](#mailflow-status-report) 보호에서 차단된 메시지에 대한 데이터는 이 보고서에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="6a07d-366">보고서의 집계 보기 및 세부 정보 보기를 사용하면 필터링 기간을 90일 동안 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="6a07d-367">보고서를 보려면 규정 준수 [센터에서 보안 & 보고서 대시보드로](https://protection.office.com) **Reports** \> **이동한 다음 보낸 전자** **메일과 받은 전자 메일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="6a07d-368">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="6a07d-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![보고서 대시보드에서 고지되거나 받은 전자 메일 위장](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="6a07d-370">보낸 및 받은 전자 메일 보고서의 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="6a07d-371">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="6a07d-372">**분석합니다. 유형: 차트에**사용 가능한 모든 범주가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="6a07d-373">**합계**</span><span class="sxs-lookup"><span data-stu-id="6a07d-373">**Total**</span></span>
  - <span data-ttu-id="6a07d-374">**정상 메일**</span><span class="sxs-lookup"><span data-stu-id="6a07d-374">**Good mail**</span></span>
  - <span data-ttu-id="6a07d-375">**맬웨어 방지(맬웨어 방지)(EOP)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="6a07d-376">**스팸 감지**</span><span class="sxs-lookup"><span data-stu-id="6a07d-376">**Spam detections**</span></span>
  - <span data-ttu-id="6a07d-377">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="6a07d-377">**Rule messages**</span></span>
  - <span data-ttu-id="6a07d-378">**고급 맬웨어(Office** 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="6a07d-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="6a07d-379">차트에서 하루(데이터 요소)을 가리치면 해당 날짜에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보낸 전자 메일 및 받은 전자 메일 보고서의 유형 보기](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="6a07d-381">**분석 단위: 차트에 합계,** **인바운드** **및 아웃바운드** **데이터가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="6a07d-382">차트에서 하루(데이터 요소)을 가리치면 해당 날짜에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보낸 메일 및 받은 전자 메일 보고서의 방향 보기](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="6a07d-384">**아래쪽으로 드릴다운** \> **맬웨어(맬웨어 방지):** 이 옵션을 선택하면 전자 메일 [보고서에서 맬웨어 검색으로 이동됩니다.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="6a07d-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="6a07d-385">**아래쪽으로 드릴다운** \> **스팸 검색:** 이 선택 항목을 클릭하면 스팸 검색 [보고서로 이동됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="6a07d-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="6a07d-386">보고서 보기에서 **필터를** 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="6a07d-387">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="6a07d-388">방향 값</span><span class="sxs-lookup"><span data-stu-id="6a07d-388">Direction values</span></span>
- <span data-ttu-id="6a07d-389">Type 값</span><span class="sxs-lookup"><span data-stu-id="6a07d-389">Type values</span></span>

<span data-ttu-id="6a07d-390">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="6a07d-391">보낸 메일 및 받은 전자 메일 보고서의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="6a07d-392">항목 분석: **방향 보기에서 세부** 정보 **보기를** 아래쪽으로 **나누기를 선택하면** 다음 정보가 표시됩니다. 방향 보기를 선택하면 다음과 같은 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="6a07d-393">**날짜(UTC)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-393">**Date (UTC)**</span></span>
- <span data-ttu-id="6a07d-394">**Type**</span><span class="sxs-lookup"><span data-stu-id="6a07d-394">**Type**</span></span>
- <span data-ttu-id="6a07d-395">**방향**</span><span class="sxs-lookup"><span data-stu-id="6a07d-395">**Direction**</span></span>
- <span data-ttu-id="6a07d-396">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="6a07d-396">**Message count**</span></span>

<span data-ttu-id="6a07d-397">세부 정보 표 **보기에서** 필터를 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="6a07d-398">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="6a07d-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="6a07d-399">방향 값</span><span class="sxs-lookup"><span data-stu-id="6a07d-399">Direction values</span></span>
- <span data-ttu-id="6a07d-400">Type 값</span><span class="sxs-lookup"><span data-stu-id="6a07d-400">Type values</span></span>

<span data-ttu-id="6a07d-401">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="6a07d-402">상위 보낸 사람 및 받는 사람 보고서</span><span class="sxs-lookup"><span data-stu-id="6a07d-402">Top senders and recipients report</span></span>

<span data-ttu-id="6a07d-403">보낸 **사람 과정에서 가장 많이 사용된** 보낸 사람 및 받는 사람" 보고서는 주요 전자 메일 보낸 사람 및 받는 사람을 나타내는 원형 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="6a07d-404">보고서를 보려면 보안 센터에서 [& 보고서 대시보드로](https://protection.office.com) **Reports** \> **이동한 후** 상단 **발신자와 받는 사람을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="6a07d-405">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="6a07d-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![보고서 대시보드의 상위 보낸 사람 및 받는 사람 위산 위과](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="6a07d-407">상위 보낸 사람 및 받는 사람 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="6a07d-408">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="6a07d-409">**주요 메일 \> 보낸 사람을 위한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="6a07d-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="6a07d-410">**상위 메일 \> 수신자에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="6a07d-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="6a07d-411">**스팸상을 \> 많이 받는 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="6a07d-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="6a07d-412">**다음에 대한 데이터 표시 \> 상위 맬웨어 받는** 사람(EOP)</span><span class="sxs-lookup"><span data-stu-id="6a07d-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="6a07d-413">**다음에 대한 데이터 표시 \> ATP(상위 맬웨어 받는 사람)(Office** 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="6a07d-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="6a07d-414">원형 차트의 구성은 이러한 선택에 따라 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="6a07d-415">원형 차트에서 WEDGE를 가리면 보내거나 받은 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="6a07d-416">보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![상위 보낸 사람 및 받는 사람 보고서 보고서보고서 보고서의 보고서 보기에 원형 차트](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="6a07d-418">맨 위의 보낸 사람 및 받는 사람 보고서의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="6a07d-419">세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="6a07d-420">**주요 메일 \> 보낸 사람을 위한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="6a07d-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="6a07d-421">**주요 메일 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="6a07d-421">**Top mail senders**</span></span>
  - <span data-ttu-id="6a07d-422">**개수**</span><span class="sxs-lookup"><span data-stu-id="6a07d-422">**Count**</span></span>

- <span data-ttu-id="6a07d-423">**상위 메일 \> 수신자에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="6a07d-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="6a07d-424">**최상위 메일 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="6a07d-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="6a07d-425">**개수**</span><span class="sxs-lookup"><span data-stu-id="6a07d-425">**Count**</span></span>

- <span data-ttu-id="6a07d-426">**스팸상을 \> 많이 받는 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="6a07d-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="6a07d-427">**상위 스팸 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="6a07d-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="6a07d-428">**개수**</span><span class="sxs-lookup"><span data-stu-id="6a07d-428">**Count**</span></span>

- <span data-ttu-id="6a07d-429">**다음에 대한 데이터 표시 \> 상위 맬웨어 받는** 사람(EOP)</span><span class="sxs-lookup"><span data-stu-id="6a07d-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="6a07d-430">**상위 맬웨어 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="6a07d-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="6a07d-431">**개수**</span><span class="sxs-lookup"><span data-stu-id="6a07d-431">**Count**</span></span>

- <span data-ttu-id="6a07d-432">**다음에 대한 데이터 표시 \> ATP(상위 맬웨어 받는 사람)(Office** 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="6a07d-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="6a07d-433">**상위 맬웨어 받는 사람(ATP)**</span><span class="sxs-lookup"><span data-stu-id="6a07d-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="6a07d-434">**개수**</span><span class="sxs-lookup"><span data-stu-id="6a07d-434">**Count**</span></span>

<span data-ttu-id="6a07d-435">세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6a07d-436">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="6a07d-437">이러한 보고서를 보는 데 필요한 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="6a07d-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="6a07d-438">보고서를 보고 사용하려면 준수 센터 및 Exchange Online에서 보안 그룹의 & **합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a07d-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="6a07d-439">새 & 센터에서 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="6a07d-440">-Organization Management -Security Administrator (Azure Active Directory 관리 센터에서도 이 [작업을 수행할 수 있나요)](https://aad.portal.azure.com) - 보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="6a07d-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="6a07d-441">자세한 내용은 [보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a07d-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="6a07d-442">Exchange Online에서는 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a07d-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="6a07d-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span><span class="sxs-lookup"><span data-stu-id="6a07d-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="6a07d-444">자세한 내용은 [Exchange Online의 사용 권한을 사용하고](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) [Exchange Online의 역할 그룹 관리를 참조하세요.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)</span><span class="sxs-lookup"><span data-stu-id="6a07d-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a07d-445">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6a07d-445">Related topics</span></span>

[<span data-ttu-id="6a07d-446">보안 및 준수 센터의 스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="6a07d-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="6a07d-447">보안 및 준수 센터의 메일 흐름 파악</span><span class="sxs-lookup"><span data-stu-id="6a07d-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="6a07d-448">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="6a07d-449">Office 365 Advanced Threat Protection 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="6a07d-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
