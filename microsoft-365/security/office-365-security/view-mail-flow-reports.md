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
description: 관리자는 보안 및 준수 센터의 보고서 대시보드에서 사용할 수 있는 메일 흐름 & 수 있습니다.
ms.custom: ''
ms.openlocfilehash: 1ededf2d0d693c537c159c52d00deb03f278b4b2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659468"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="91409-103">보안 및 준수 센터의 보고서 대시보드에서 & 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="91409-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="91409-104">보안 및 준수 센터의 메일 흐름 [](mail-flow-insights-v2.md) 대시보드에서 사용할 수 있는 메일 흐름 보고서 외에도 & 보고서 대시보드에서 다양한 추가 메일 흐름 보고서를 사용하여 Microsoft 365 조직을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="91409-105">필요한 사용 [](#what-permissions-are-needed-to-view-these-reports)권한이 있는 경우 보고서 대시보드로 & 보안 및 준수 [센터에서](https://office.protection.com) 이러한 보고서를 볼 **수** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="91409-106">보고서 대시보드로 직접 이동하기 위해 를 <https://protection.office.com/insightdashboard> 열습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![보안 및 준수 & 대시보드 보고](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="91409-108">커넥터 보고서</span><span class="sxs-lookup"><span data-stu-id="91409-108">Connector report</span></span>

<span data-ttu-id="91409-109">커넥터 **보고서에는** 조직에 대해 [](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 구성된 인바운드 및 아웃바운드 커넥터의 메일 흐름 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="91409-110">보고서를 표시하려면 보안 및 준수 [센터를 &](https://protection.office.com) **보고서** 대시보드로 이동하여 커넥터 보고서를 \>  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="91409-111">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=ConnectorReport> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![보고서 대시보드의 커넥터 보고서 위젯](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="91409-113">커넥터 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="91409-113">Report view for the Connector report</span></span>

<span data-ttu-id="91409-114">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="91409-115">**데이터 보기: 메일 흐름:** 이 차트에는 다음을 통해 구성되는 인바운드 및 아웃바운드 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="91409-116">**합계**</span><span class="sxs-lookup"><span data-stu-id="91409-116">**Total**</span></span>
  - <span data-ttu-id="91409-117">**커넥터가 없는 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="91409-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="91409-118">**커넥터가 없는 인터넷으로**</span><span class="sxs-lookup"><span data-stu-id="91409-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="91409-119">구성한 특정 커넥터입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="91409-120">차트에서 데이터를 격리하려면 컨트롤에  대한 데이터 표시를 사용하여 이러한 옵션 또는 모든 메일 흐름 중 하나를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![커넥터 보고서에서 메일 흐름에 따라 데이터 보기](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="91409-122">**데이터 보기: TLS 사용법:** 이 차트는 메일 흐름에 대한 TLS(전송 계층 보안) 버전 사용량의 백분율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91409-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="91409-123">차트에서 데이터를 격리하려면 컨트롤에  대한 데이터 표시를 사용하여 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91409-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="91409-124">**모든 메일 흐름**</span><span class="sxs-lookup"><span data-stu-id="91409-124">**All mail flow**</span></span>
  - <span data-ttu-id="91409-125">**커넥터가 없는 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="91409-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="91409-126">**커넥터가 없는 인터넷으로**</span><span class="sxs-lookup"><span data-stu-id="91409-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="91409-127">구성한 특정 커넥터입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-127">A specific connector that you've configured.</span></span>

  ![커넥터 보고서에서 TLS 사용 현황으로 데이터 보기](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="91409-129">보고서 보기에서 **필터를** 클릭하면 시작 날짜와 종료  날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="91409-130">커넥터 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="91409-130">Details table view for the Connector report</span></span>

<span data-ttu-id="91409-131">보고서 **보기에서** 세부 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="91409-132">**날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-132">**Date**</span></span>
- <span data-ttu-id="91409-133">**커넥터 방향 및 이름**</span><span class="sxs-lookup"><span data-stu-id="91409-133">**Connector direction and name**</span></span>
- <span data-ttu-id="91409-134">**커넥터 유형**</span><span class="sxs-lookup"><span data-stu-id="91409-134">**Connector type**</span></span>
- <span data-ttu-id="91409-135">**강제 TLS?**: **True** 또는 **False** 값</span><span class="sxs-lookup"><span data-stu-id="91409-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="91409-136">**TLS** 없음(백분율)</span><span class="sxs-lookup"><span data-stu-id="91409-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="91409-137">**TLS 1.0(백분율)**</span><span class="sxs-lookup"><span data-stu-id="91409-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="91409-138">**TLS 1.1(백분율)**</span><span class="sxs-lookup"><span data-stu-id="91409-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="91409-139">**TLS 1.2(백분율)**</span><span class="sxs-lookup"><span data-stu-id="91409-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="91409-140">**볼륨**: 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="91409-141">세부 정보 표 보기에서 **필터를** 클릭하면 시작 날짜와  종료 날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="91409-142">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="91409-143">Exchange 전송 규칙 보고서</span><span class="sxs-lookup"><span data-stu-id="91409-143">Exchange transport rule report</span></span>

<span data-ttu-id="91409-144">**Exchange 전송 규칙 보고서는** 메일 흐름 규칙(전송 규칙라고도 알려지음)이 조직의 받는 메시지와 보내진 메시지에 줄 수 있는 영향을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="91409-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="91409-145">보고서를 표시하려면 보안 및 준수 [&](https://protection.office.com)보고서 대시보드로 이동하여 Exchange 전송  \>  **규칙을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="91409-146">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=ETRRuleReport> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![보고서 대시보드의 Exchange 전송 규칙 위젯](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="91409-148">Exchange 전송 규칙 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="91409-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="91409-149">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="91409-150">**데이터 보기: Exchange 전송 규칙** \> **세분화: 방향:** 이 차트에는  전송 규칙의 영향을 받은 인바운드 및 **아웃바운드** 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="91409-151">**데이터 보기: Exchange 전송 규칙** \> **심각도:** 이 차트는 높은 심각도  및 보통 심각도 및 낮은 심각도 메시지의 수를 **보여** 주며, </span><span class="sxs-lookup"><span data-stu-id="91409-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="91409-152">심각도 수준을 규칙의 작업으로 설정할 수 있습니다(심각도 수준 또는 _SetAuditSeverity로_ 이 규칙 감사).</span><span class="sxs-lookup"><span data-stu-id="91409-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="91409-153">자세한 내용은 [Exchange Online의 메일 흐름 규칙 작업을 참조하세요.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="91409-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="91409-154">**데이터 보기: DLP Exchange 전송 규칙** \> **세분화: 방향:** 이 차트는  DLP(데이터 손실 방지) 전송 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지의 수를 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="91409-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="91409-155">다음 옵션 중 원하는 옵션을 선택하여 차트를 추가로 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="91409-156">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="91409-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="91409-157">**데이터 표시: 손상된 사용자**</span><span class="sxs-lookup"><span data-stu-id="91409-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="91409-158">**데이터 표시: 미국 애국법에서 검색된 콘텐츠의 양이 적습니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="91409-159">**데이터 보기: DLP Exchange 전송 규칙** \> **세분화: 방향:** 이 보기에는  높은 심각도 및 보통 심각도 및 DLP 전송 규칙의 영향을 받은 낮은 심각도 메시지의 수가 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="91409-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="91409-160">다음 옵션 중 원하는 옵션을 선택하여 차트를 추가로 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="91409-161">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="91409-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="91409-162">**데이터 표시: 손상된 사용자**</span><span class="sxs-lookup"><span data-stu-id="91409-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="91409-163">**데이터 표시: 미국 애국법에서 검색된 콘텐츠의 양이 적습니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="91409-164">보고서 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="91409-165">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="91409-166">방향 값</span><span class="sxs-lookup"><span data-stu-id="91409-166">Direction values</span></span>
- <span data-ttu-id="91409-167">심각도 값</span><span class="sxs-lookup"><span data-stu-id="91409-167">Severity values</span></span>

![Exchange 전송 규칙 보고서의 보고서 보기](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="91409-169">Exchange 전송 규칙 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="91409-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="91409-170">세부 **정보** 표 보기를 클릭하면 표시되는 정보는 보고 있는 차트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="91409-171">**데이터 보기: Exchange 전송 규칙:**</span><span class="sxs-lookup"><span data-stu-id="91409-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="91409-172">**날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-172">**Date**</span></span>
  - <span data-ttu-id="91409-173">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="91409-173">**Transport rule**</span></span>
  - <span data-ttu-id="91409-174">**제목**</span><span class="sxs-lookup"><span data-stu-id="91409-174">**Subject**</span></span>
  - <span data-ttu-id="91409-175">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="91409-175">**Sender address**</span></span>
  - <span data-ttu-id="91409-176">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="91409-176">**Recipient address**</span></span>
  - <span data-ttu-id="91409-177">**심각도**</span><span class="sxs-lookup"><span data-stu-id="91409-177">**Severity**</span></span>
  - <span data-ttu-id="91409-178">**방향**</span><span class="sxs-lookup"><span data-stu-id="91409-178">**Direction**</span></span>

- <span data-ttu-id="91409-179">**데이터 보기: DLP Exchange 전송 규칙:**</span><span class="sxs-lookup"><span data-stu-id="91409-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="91409-180">**날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-180">**Date**</span></span>
  - <span data-ttu-id="91409-181">**DLP 정책**</span><span class="sxs-lookup"><span data-stu-id="91409-181">**DLP policy**</span></span>
  - <span data-ttu-id="91409-182">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="91409-182">**Transport rule**</span></span>
  - <span data-ttu-id="91409-183">**제목**</span><span class="sxs-lookup"><span data-stu-id="91409-183">**Subject**</span></span>
  - <span data-ttu-id="91409-184">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="91409-184">**Sender address**</span></span>
  - <span data-ttu-id="91409-185">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="91409-185">**Recipient address**</span></span>
  - <span data-ttu-id="91409-186">**심각도**</span><span class="sxs-lookup"><span data-stu-id="91409-186">**Severity**</span></span>
  - <span data-ttu-id="91409-187">**방향**</span><span class="sxs-lookup"><span data-stu-id="91409-187">**Direction**</span></span>

<span data-ttu-id="91409-188">세부 정보 테이블 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="91409-189">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="91409-190">방향 값</span><span class="sxs-lookup"><span data-stu-id="91409-190">Direction values</span></span>
- <span data-ttu-id="91409-191">심각도 값</span><span class="sxs-lookup"><span data-stu-id="91409-191">Severity values</span></span>

<span data-ttu-id="91409-192">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="91409-193">전달 보고서</span><span class="sxs-lookup"><span data-stu-id="91409-193">Forwarding report</span></span>

<span data-ttu-id="91409-194">전달 **보고서에는** Exchange Online 사서함의 외부 도메인으로 조직의 자동으로 전달된 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="91409-195">전달된 메시지는 보안 또는 규정 준수 위험을 내포할 수 있으며 계정이 손상된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="91409-196">보고서를 표시하려면 보안 및 준수 [&](https://protection.office.com)열고 보고서  대시보드로 이동한 후 전달 \>  **보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="91409-197">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=MailFlowForwarding> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![보고서 대시보드에서 보고서 위젯 전달](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="91409-199">전달 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="91409-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="91409-200">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="91409-201">**데이터 표시: 전달** 메서드: 다음 메서드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="91409-202">**전송 규칙:** 메일 흐름 [규칙으로도 알려져 있습니다.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="91409-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="91409-203">**사서함 규칙:** 받은 편지함 [규칙으로도 알려져 있습니다.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="91409-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![전달 보고서의 전달 메서드 보기](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="91409-205">**다음에 대한 데이터 표시:** 전달 도메인: 이 보기에는 전달 대상인 받는 사람 도메인이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![전달 보고서의 전달 도메인 보기](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="91409-207">**다음에 대한 데이터 표시: 전달자:** 다음 전달자 표시</span><span class="sxs-lookup"><span data-stu-id="91409-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="91409-208">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="91409-208">**Transport rule**</span></span>
  - <span data-ttu-id="91409-209">전달 받은 편지함 규칙이 포함된 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![전달 보고서의 전달자 보기](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="91409-211">보고서 보기에서 **필터를** 클릭하면 시작 날짜와 종료  날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="91409-212">전달 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="91409-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="91409-213">보고서 **보기에서** 세부 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="91409-214">**전달자:** 전달 **받은** 편지함 규칙이 포함된 값 전송 규칙 또는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="91409-215">**전달 유형:** 사서함 규칙 또는 전송 **규칙** 값입니다. </span><span class="sxs-lookup"><span data-stu-id="91409-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="91409-216">**받는 사람 이름**</span><span class="sxs-lookup"><span data-stu-id="91409-216">**Recipient name**</span></span>
- <span data-ttu-id="91409-217">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="91409-217">**Recipient domain**</span></span>
- <span data-ttu-id="91409-218">**세부 정보:** 메일 흐름 규칙의 GUID 값 또는 받은 편지함 규칙의 RuleIdentity 값입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="91409-219">**개수**</span><span class="sxs-lookup"><span data-stu-id="91409-219">**Count**</span></span>
- <span data-ttu-id="91409-220">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-220">**First forward date**</span></span>

<span data-ttu-id="91409-221">세부 정보 표 보기에서 **필터를** 클릭하면 시작 날짜와  종료 날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="91409-222">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="91409-223">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="91409-223">Mailflow status report</span></span>

<span data-ttu-id="91409-224">메일 **흐름 상태 보고서는** 보낸 전자 메일 및 받은 전자 메일 보고서와 유사하며, [](#sent-and-received-email-report)에지에서 허용되거나 차단된 전자 메일에 대한 추가 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="91409-225">이 보고서는 에지 보호 정보를 포함하는 유일한 보고서로, EOP(Exchange Online Protection)의 평가를 위해 서비스에 허용되기 전에 차단되는 전자 메일의 수만 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="91409-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="91409-226">받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지가 아니라 5개의 다른 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="91409-227">보고서를 확인하려면 보안 & 준수 센터를 열고  보고서 대시보드로 이동하여 메일 흐름 [상태](https://protection.office.com) \>  **보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="91409-228">메일 흐름 상태 **보고서로** 직접 이동 하 고 를 를 를 를 를 를 를 를 열 수 <https://protection.office.com/mailflowStatusReport> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![보고서 대시보드의 메일 흐름 상황 보고서 위젯](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="91409-230">메일 흐름 상태 보고서의 형식 보기</span><span class="sxs-lookup"><span data-stu-id="91409-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="91409-231">보고서를 열면 유형  탭이 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="91409-232">기본적으로 이 보기에는 다음 필터로 구성된 차트 및 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="91409-233">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="91409-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="91409-234">**방향**:</span><span class="sxs-lookup"><span data-stu-id="91409-234">**Direction**:</span></span>

  - <span data-ttu-id="91409-235">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="91409-235">**Inbound**</span></span>
  - <span data-ttu-id="91409-236">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="91409-236">**Outbound**</span></span>
  - <span data-ttu-id="91409-237">**Intra-org**: This count is for messages within a tenant i.e</span><span class="sxs-lookup"><span data-stu-id="91409-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="91409-238">보낸 사람 abc@domain.com 받는 사람에게 xyz@domain.com(인바운드  및 아웃바운드와 별도로 **계산)**</span><span class="sxs-lookup"><span data-stu-id="91409-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="91409-239">**Type**:</span><span class="sxs-lookup"><span data-stu-id="91409-239">**Type**:</span></span>

  - <span data-ttu-id="91409-240">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-240">**Good mail**</span></span>
  - <span data-ttu-id="91409-241">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="91409-241">**Malware**</span></span>
  - <span data-ttu-id="91409-242">**스팸**</span><span class="sxs-lookup"><span data-stu-id="91409-242">**Spam**</span></span>
  - <span data-ttu-id="91409-243">**에지 보호**</span><span class="sxs-lookup"><span data-stu-id="91409-243">**Edge protection**</span></span>
  - <span data-ttu-id="91409-244">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="91409-244">**Rule messages**</span></span>
  - <span data-ttu-id="91409-245">**피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-245">**Phishing email**</span></span>

<span data-ttu-id="91409-246">차트는 형식 값으로 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="91409-247">필터를 클릭하거나 차트  범례에서 값을 클릭하여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="91409-248">데이터 테이블에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-248">The data table contains the following information:</span></span>

- <span data-ttu-id="91409-249">**방향**</span><span class="sxs-lookup"><span data-stu-id="91409-249">**Direction**</span></span>
- <span data-ttu-id="91409-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="91409-250">**Type**</span></span>
- <span data-ttu-id="91409-251">**24시간**</span><span class="sxs-lookup"><span data-stu-id="91409-251">**24 hours**</span></span>
- <span data-ttu-id="91409-252">**3일**</span><span class="sxs-lookup"><span data-stu-id="91409-252">**3 days**</span></span>
- <span data-ttu-id="91409-253">**7일**</span><span class="sxs-lookup"><span data-stu-id="91409-253">**7 days**</span></span>
- <span data-ttu-id="91409-254">**15일**</span><span class="sxs-lookup"><span data-stu-id="91409-254">**15 days**</span></span>
- <span data-ttu-id="91409-255">**30일**</span><span class="sxs-lookup"><span data-stu-id="91409-255">**30 days**</span></span>

<span data-ttu-id="91409-256">자세한 내용을 **보려면 범주** 선택을 클릭하면 다음 값에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="91409-257">**피싱 전자 메일**: 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="91409-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="91409-258">**전자 메일의** 맬웨어: 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="91409-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="91409-259">**스팸 검색:** 이 선택을 통해 스팸 검색 보고서로 [전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="91409-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="91409-260">**Edge 차단 스팸:** 이 선택을 통해 스팸 검색 보고서로 [전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="91409-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="91409-261">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="91409-261">**Export**:</span></span>

<span data-ttu-id="91409-262">세부 정보 보기의 경우 하루 동안만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="91409-263">따라서 7일 동안 데이터를 내보내는 경우 7개 다른 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91409-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="91409-264">내보낼 .csv 파일은 각각 150,000개 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="91409-265">해당 일의 데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="91409-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="91409-266">메일 흐름 상태 보고서의 유형 보기</span><span class="sxs-lookup"><span data-stu-id="91409-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="91409-267">메일 흐름 상태 보고서의 방향 보기</span><span class="sxs-lookup"><span data-stu-id="91409-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="91409-268">방향 **탭을** 클릭하면 유형 보기의 동일한 기본 **필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="91409-269">차트는 방향 값으로 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="91409-270">필터를 클릭하거나 차트  범례에서 값을 클릭하여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="91409-271">형식 보기의 **동일한 필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="91409-272">데이터 테이블에는 형식 보기와 동일한 **정보가** 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="91409-273">사용 **가능한 선택 항목** 및 동작에 대한 자세한 내용은 종류 선택 보기와 같습니다. </span><span class="sxs-lookup"><span data-stu-id="91409-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="91409-274">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="91409-274">**Export**:</span></span>

<span data-ttu-id="91409-275">세부 정보 보기의 경우 하루 동안만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="91409-276">따라서 7일 동안 데이터를 내보내는 경우 7개 다른 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91409-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="91409-277">내보낼 .csv 파일은 각각 150,000개 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="91409-278">해당 일의 데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="91409-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="91409-279">메일 흐름 상태 보고서의 방향 보기</span><span class="sxs-lookup"><span data-stu-id="91409-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="91409-280">메일 흐름 상태 보고서의 FUNNEL 보기</span><span class="sxs-lookup"><span data-stu-id="91409-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="91409-281">**Funnel** 보기는 Microsoft의 전자 메일 위협 방지 기능이 조직에서 수신 및 전송되는 전자 메일을 필터링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="91409-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="91409-282">전체 전자 메일 수와 에지 보호, 맬웨어 방지, 피싱 방지, 스팸 방지 및 스푸핑 방지를 비롯한 구성된 위협 방지 기능이 이 수에 미치는 영향에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91409-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="91409-283">**FUNNel** 탭을 클릭하면 기본적으로 이 보기에는 차트와 다음 필터로 구성된 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="91409-284">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="91409-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="91409-285">**방향**:</span><span class="sxs-lookup"><span data-stu-id="91409-285">**Direction**:</span></span>

  - <span data-ttu-id="91409-286">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="91409-286">**Inbound**</span></span>
  - <span data-ttu-id="91409-287">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="91409-287">**Outbound**</span></span>
  - <span data-ttu-id="91409-288">**내부:** 테넌트 내에서 보낸 메시지에 대한 수입니다. 즉, 보낸 abc@domain.com 받는 사람에게 xyz@domain.com 수 있습니다(인바운드 및 아웃바운드와는 별도로 계산).</span><span class="sxs-lookup"><span data-stu-id="91409-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="91409-289">집계 보기 및 데이터 테이블 보기는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="91409-290">필터를 클릭하면 차트와 데이터 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="91409-291">이 차트에는 다음별로 구성한 전자 메일 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="91409-292">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-292">**Total email**</span></span>
- <span data-ttu-id="91409-293">**Edge 보호 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-293">**Email after edge protection**</span></span>
- <span data-ttu-id="91409-294">**맬웨어 방지, 파일 신뢰도, 파일 형식 블록 이후의 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="91409-295">**피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지 이후의 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="91409-296">**스팸 방지, 대량 메일 필터링 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="91409-297">사용자 및 도메인 가장 <sup>1</sup> **이후의 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="91409-298">**파일 후 전자 메일 및 URL 확인**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="91409-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="91409-299">**배달 후 보호 후 무해한 것으로 감지된 전자 메일(URL 클릭 시간 보호)**</span><span class="sxs-lookup"><span data-stu-id="91409-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="91409-300"><sup>1</sup> Office 365용 Defender만</span><span class="sxs-lookup"><span data-stu-id="91409-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="91409-301">EOP 또는 Office 365용 Defender에서 개별적으로 필터링한 전자 메일을 보려면 차트 범례의 값을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91409-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="91409-302">데이터 테이블에는 내선 날짜 순서로 표시되는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="91409-303">**날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-303">**Date**</span></span>
- <span data-ttu-id="91409-304">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-304">**Total email**</span></span>
- <span data-ttu-id="91409-305">**에지 보호**</span><span class="sxs-lookup"><span data-stu-id="91409-305">**Edge protection**</span></span>
- <span data-ttu-id="91409-306">**맬웨어 방지, 파일 신뢰도, 파일 형식 블록:**</span><span class="sxs-lookup"><span data-stu-id="91409-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="91409-307">**파일 신뢰도**: 다른 Microsoft 고객이 첨부한 파일을 식별하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="91409-308">**파일 형식 블록:** 메시지에 식별된 악성 파일의 유형으로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="91409-309">**피싱 방지, URL 신뢰도, 브랜드 가장,** 스푸핑 방지:</span><span class="sxs-lookup"><span data-stu-id="91409-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="91409-310">**URL 신뢰도**: 다른 Microsoft 고객이 URL을 식별하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="91409-311">**브랜드 가장:** 보낸 사람으로 가장하는 잘 알려진 브랜드에서 보낸 메시지로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="91409-312">**스푸핑** 방지: 받는 사람이 속한 도메인 또는 메시지 보낸 사람이 소유하지 않은 도메인을 스푸핑하려고 하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="91409-313">**스팸 방지, 대량 메일 필터링:**</span><span class="sxs-lookup"><span data-stu-id="91409-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="91409-314">**대량 메일 필터링:** 받는 사람에게 대량 메일을 배달하려고 시도하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="91409-315">**사용자 및 도메인 가장(Office 365용 Defender)**:</span><span class="sxs-lookup"><span data-stu-id="91409-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="91409-316">**사용자 가장:** 피싱 방지 정책의 가장 보호 설정에 정의된 사용자(메시지 보낸 사람)를 가장하려는 시도로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="91409-317">**도메인 가장:** 피싱 방지 정책의 가장 보호 설정에 정의된 도메인을 가장하려는 시도로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="91409-318">**파일 및 URL 확인(Office 365용 Defender)**:</span><span class="sxs-lookup"><span data-stu-id="91409-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="91409-319">**파일 검색:** 안전한 첨부 파일 정책에 의해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="91409-320">**URL 검색:** 안전한 링크 정책에 의해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="91409-321">**사후 배달 보호 및 ATP(ZAP) 또는 EOP(ZAP)**: ZAP는 0시간 자동 비우기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91409-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="91409-322">데이터 테이블에서 행을 선택하면 플라이아웃에 전자 메일 수의 추가 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="91409-323">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="91409-323">**Export**:</span></span>

<span data-ttu-id="91409-324">옵션에서 **내보내기를** 클릭한 후 다음 값 중 하나를 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="91409-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="91409-325">**요약(최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="91409-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="91409-326">**세부 정보(최근 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="91409-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="91409-327">**날짜에서** 범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="91409-328">현재 필터에 대한 데이터는 .csv 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="91409-329">내보낼 .csv 파일은 각각 150,000개 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="91409-330">데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="91409-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="91409-331">메일 흐름 상태 보고서의 FUNNEL 보기</span><span class="sxs-lookup"><span data-stu-id="91409-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="91409-332">메일 흐름 상태 보고서에 대한 기술 보기</span><span class="sxs-lookup"><span data-stu-id="91409-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="91409-333">기술 **보기는** **Funnel** 보기와 유사하여 구성된 위협 방지 기능에 대한 보다 세부적인 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91409-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="91409-334">차트에서 다양한 위협 방지 단계에서 메시지를 분류하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="91409-335">기술 보기  탭을 클릭하면 기본적으로 이 보기에는 차트와 다음 필터로 구성된 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="91409-336">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="91409-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="91409-337">**방향**:</span><span class="sxs-lookup"><span data-stu-id="91409-337">**Direction**:</span></span>

  - <span data-ttu-id="91409-338">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="91409-338">**Inbound**</span></span>
  - <span data-ttu-id="91409-339">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="91409-339">**Outbound**</span></span>
  - <span data-ttu-id="91409-340">**Intra-org**: This count is for messages within a tenant i.e</span><span class="sxs-lookup"><span data-stu-id="91409-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="91409-341">보낸 사람 abc@domain.com 받는 사람에게 xyz@domain.com(인바운드 및 아웃바운드와 별도로 계산)</span><span class="sxs-lookup"><span data-stu-id="91409-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="91409-342">집계 보기 및 데이터 테이블 보기는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="91409-343">필터를 클릭하면 차트와 데이터 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="91409-344">이 차트에는 다음 범주로 구성된 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="91409-345">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-345">**Total email**</span></span>
- <span data-ttu-id="91409-346">**에지** 허용 **및 Edge 필터링**</span><span class="sxs-lookup"><span data-stu-id="91409-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="91409-347">**맬웨어가 아닌** 경우, **안전 첨부 파일 검색,** 맬웨어 방지 <sup>\*</sup> 엔진 **검색** 및 **규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="91409-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="91409-348">**피싱** 금지, **DMARC 실패,** 가장 **검색,** 스푸핑 **검색** 및 **피싱 감지**</span><span class="sxs-lookup"><span data-stu-id="91409-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="91409-349">**URL 검색 및 URL** 검색으로 검색 **안**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91409-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="91409-350">**스팸 및** 스팸  **아미**</span><span class="sxs-lookup"><span data-stu-id="91409-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="91409-351">**악성이 아닌 전자 메일,** **안전한 링크 검색** 및 <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="91409-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="91409-352"><sup>\*</sup> Office 365용 Defender</span><span class="sxs-lookup"><span data-stu-id="91409-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="91409-353">차트에서 범주 위에 마우스를 대면 해당 범주의 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="91409-354">데이터 테이블에는 내선 날짜 순서로 표시되는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="91409-355">**날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-355">**Date**</span></span>
- <span data-ttu-id="91409-356">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-356">**Total email**</span></span>
- <span data-ttu-id="91409-357">**필터링된 에지**</span><span class="sxs-lookup"><span data-stu-id="91409-357">**Edge filtered**</span></span>
- <span data-ttu-id="91409-358">**맬웨어 방지 엔진, 안전한 첨부 파일, 필터링된 규칙:**</span><span class="sxs-lookup"><span data-stu-id="91409-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="91409-359">**규칙 필터링된** 규칙: 메일 흐름 규칙(전송 규칙 이라고도 알려지음)으로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="91409-360">**DMARC, 가장, 스푸핑, 피싱 필터링:**</span><span class="sxs-lookup"><span data-stu-id="91409-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="91409-361">**DMARC**: 메시지의 DMARC 인증 검사에 실패하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="91409-362">**URL 검색**</span><span class="sxs-lookup"><span data-stu-id="91409-362">**URL detonation detection**</span></span>
- <span data-ttu-id="91409-363">**스팸 방지 필터링**</span><span class="sxs-lookup"><span data-stu-id="91409-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="91409-364">**ZAP 제거됨**</span><span class="sxs-lookup"><span data-stu-id="91409-364">**ZAP removed**</span></span>
- <span data-ttu-id="91409-365">**안전한 링크로 검색**</span><span class="sxs-lookup"><span data-stu-id="91409-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="91409-366">데이터 테이블에서 행을 선택하면 플라이아웃에 전자 메일 수의 추가 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="91409-367">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="91409-367">**Export**:</span></span>

<span data-ttu-id="91409-368">내보내기 **클릭 시** **옵션에서** 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="91409-369">**요약(최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="91409-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="91409-370">**세부 정보(최근 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="91409-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="91409-371">**날짜에서** 범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="91409-372">현재 필터에 대한 데이터는 .csv 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="91409-373">내보낼 .csv 파일은 각각 150,000개 행으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="91409-374">데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="91409-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="91409-375">메일 흐름 상태 보고서의 기술 보기</span><span class="sxs-lookup"><span data-stu-id="91409-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="91409-376">보낸 메일 및 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="91409-376">Sent and received email report</span></span>

<span data-ttu-id="91409-377">**보내고** 받는 전자 메일 보고서는 스팸 검색, 맬웨어 및 "양호"로 식별된 전자 메일을 포함하여 들어오고 받는 전자 메일에 대한 정보를 표시하는 스마트 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="91409-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="91409-378">이 보고서와 [메일](#mailflow-status-report) 흐름 상태 보고서의 차이점은 이 보고서에 Edge 보호로 차단된 메시지에 대한 데이터는 포함하지 않습니다. 받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="91409-379">보고서의 집계 보기 및 세부 정보 보기에서는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="91409-380">보고서를 확인하려면 Security [& 준수](https://protection.office.com)센터를 열고  보고서 대시보드로 이동하여 보내고 받은 전자 메일을 \>  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="91409-381">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![보고서 대시보드에서 보낸 전자 메일 위젯 및 받은 전자 메일 위젯](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="91409-383">보내고 받은 전자 메일 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="91409-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="91409-384">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="91409-385">**세분화: 유형:** 차트에 사용 가능한 모든 범주가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="91409-386">**합계**</span><span class="sxs-lookup"><span data-stu-id="91409-386">**Total**</span></span>
  - <span data-ttu-id="91409-387">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="91409-387">**Good mail**</span></span>
  - <span data-ttu-id="91409-388">**맬웨어(맬웨어** 방지)(EOP)</span><span class="sxs-lookup"><span data-stu-id="91409-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="91409-389">**스팸 감지**</span><span class="sxs-lookup"><span data-stu-id="91409-389">**Spam detections**</span></span>
  - <span data-ttu-id="91409-390">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="91409-390">**Rule messages**</span></span>
  - <span data-ttu-id="91409-391">**고급 맬웨어(Office** 365용 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="91409-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="91409-392">차트에서 하루(데이터 포인트)에 마우스를 대면 해당 일자에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보내고 받은 전자 메일 보고서에 보기 입력](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="91409-394">**세분화하여: 방향:** 차트에  **총,** 인바운드 및 **아웃바운드 데이터가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="91409-395">차트에서 하루(데이터 포인트)에 마우스를 대면 해당 일자에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보내고 받은 전자 메일 보고서의 방향 보기](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="91409-397">**드릴다운** \> **맬웨어(맬웨어 방지)**: 이 선택을 통해 전자 메일 보고서의 [맬웨어 검색으로 전달됩니다.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="91409-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="91409-398">**드릴다운** \> **스팸 검색)**: 이 선택을 통해 스팸 검색 보고서로 [전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="91409-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="91409-399">보고서 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="91409-400">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="91409-401">방향 값</span><span class="sxs-lookup"><span data-stu-id="91409-401">Direction values</span></span>
- <span data-ttu-id="91409-402">형식 값</span><span class="sxs-lookup"><span data-stu-id="91409-402">Type values</span></span>

<span data-ttu-id="91409-403">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="91409-404">보낸 전자 메일 보고서 및 받은 전자 메일 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="91409-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="91409-405">**세분화로** 세부 정보 표 **보기:** 방향  또는 세분화: 방향 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="91409-406">**날짜(UTC)**</span><span class="sxs-lookup"><span data-stu-id="91409-406">**Date (UTC)**</span></span>
- <span data-ttu-id="91409-407">**Type**</span><span class="sxs-lookup"><span data-stu-id="91409-407">**Type**</span></span>
- <span data-ttu-id="91409-408">**방향**</span><span class="sxs-lookup"><span data-stu-id="91409-408">**Direction**</span></span>
- <span data-ttu-id="91409-409">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="91409-409">**Message count**</span></span>

<span data-ttu-id="91409-410">세부 정보 테이블 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="91409-411">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="91409-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="91409-412">방향 값</span><span class="sxs-lookup"><span data-stu-id="91409-412">Direction values</span></span>
- <span data-ttu-id="91409-413">형식 값</span><span class="sxs-lookup"><span data-stu-id="91409-413">Type values</span></span>

<span data-ttu-id="91409-414">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="91409-415">상위 보낸 사람 및 받는 사람 보고서</span><span class="sxs-lookup"><span data-stu-id="91409-415">Top senders and recipients report</span></span>

<span data-ttu-id="91409-416">Top **senders and recipients** report is a pie chart showing your top email senders and recipients.</span><span class="sxs-lookup"><span data-stu-id="91409-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="91409-417">보고서를 확인하려면 보안 & 준수 센터를 열고  보고서 대시보드로 이동한 다음 상위 보낸 사람 [및 받는](https://protection.office.com) \>  **사람을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="91409-418">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![보고서 대시보드의 상위 보낸 사람 및 받는 사람 위젯](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="91409-420">상위 보낸 사람 및 받는 사람 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="91409-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="91409-421">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="91409-422">**상위 메일 보낸 \> 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="91409-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="91409-423">**상위 메일 \> 받는 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="91409-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="91409-424">**상위 스팸 받는 \> 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="91409-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="91409-425">**데이터 표시 \> 상위 맬웨어 받는** 사람(EOP)</span><span class="sxs-lookup"><span data-stu-id="91409-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="91409-426">**상위 맬웨어 받는 사람에 대한 데이터 \> 표시(Office 365용 Defender)**</span><span class="sxs-lookup"><span data-stu-id="91409-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="91409-427">이러한 선택에 따라 파이 차트의 컴포지션이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="91409-428">파이 차트에서 에지 위에 마우스를 대면 보내거나 받은 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="91409-429">보고서 보기에서 **필터를** 클릭하면 시작 날짜와 종료  날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![상위 보낸 사람 및 받는 사람 보고서의 보고서 보기에 있는 파이 차트](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="91409-431">상위 보낸 사람 및 받는 사람 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="91409-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="91409-432">세부 **정보** 표 보기를 클릭하면 표시되는 정보는 보고 있는 차트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91409-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="91409-433">**상위 메일 보낸 \> 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="91409-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="91409-434">**상위 메일 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="91409-434">**Top mail senders**</span></span>
  - <span data-ttu-id="91409-435">**개수**</span><span class="sxs-lookup"><span data-stu-id="91409-435">**Count**</span></span>

- <span data-ttu-id="91409-436">**상위 메일 \> 받는 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="91409-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="91409-437">**상위 메일 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="91409-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="91409-438">**개수**</span><span class="sxs-lookup"><span data-stu-id="91409-438">**Count**</span></span>

- <span data-ttu-id="91409-439">**상위 스팸 받는 \> 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="91409-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="91409-440">**상위 스팸 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="91409-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="91409-441">**개수**</span><span class="sxs-lookup"><span data-stu-id="91409-441">**Count**</span></span>

- <span data-ttu-id="91409-442">**데이터 표시 \> 상위 맬웨어 받는** 사람(EOP)</span><span class="sxs-lookup"><span data-stu-id="91409-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="91409-443">**상위 맬웨어 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="91409-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="91409-444">**개수**</span><span class="sxs-lookup"><span data-stu-id="91409-444">**Count**</span></span>

- <span data-ttu-id="91409-445">**상위 맬웨어 받는 사람에 대한 데이터 \> 표시(Office 365용 Defender)**</span><span class="sxs-lookup"><span data-stu-id="91409-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="91409-446">**상위 맬웨어 받는 사람(Office 365용 Defender)**</span><span class="sxs-lookup"><span data-stu-id="91409-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="91409-447">**개수**</span><span class="sxs-lookup"><span data-stu-id="91409-447">**Count**</span></span>

<span data-ttu-id="91409-448">세부 정보 표 보기에서 **필터를** 클릭하면 시작 날짜와  종료 날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="91409-449">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91409-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="91409-450">이러한 보고서를 보는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="91409-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="91409-451">이 문서에 설명된 보고서를 보고 사용하려면 Security & 준수 센터에서 다음 역할 그룹 중 하나에 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="91409-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="91409-452">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="91409-452">**Organization Management**</span></span>
- <span data-ttu-id="91409-453">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="91409-453">**Security Administrator**</span></span>
- <span data-ttu-id="91409-454">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="91409-454">**Security Reader**</span></span>
- <span data-ttu-id="91409-455">**전역 읽기**</span><span class="sxs-lookup"><span data-stu-id="91409-455">**Global Reader**</span></span>

<span data-ttu-id="91409-456">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91409-456">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="91409-457">**참고:** Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안  & 준수 센터의 필요한 사용 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="91409-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="91409-458">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91409-458">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-topics"></a><span data-ttu-id="91409-459">관련 항목</span><span class="sxs-lookup"><span data-stu-id="91409-459">Related topics</span></span>

[<span data-ttu-id="91409-460">보안 및 준수 센터의 스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="91409-460">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="91409-461">보안 및 준수 센터의 메일 흐름 파악</span><span class="sxs-lookup"><span data-stu-id="91409-461">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="91409-462">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="91409-462">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="91409-463">Office 365용 Microsoft Defender에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="91409-463">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
