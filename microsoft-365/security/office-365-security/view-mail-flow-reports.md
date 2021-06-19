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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 보안 및 준수 센터의 보고서 대시보드에서 사용할 수 있는 메일 흐름 & 있습니다.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029479"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="a6cda-103">보안 및 준수 센터의 보고서 대시보드에서 & 흐름 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a6cda-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="a6cda-104">**Applies to**</span></span>
- [<span data-ttu-id="a6cda-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a6cda-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a6cda-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="a6cda-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a6cda-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6cda-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="a6cda-108">이 항목에 설명된 대부분의 보고서는 EAC(Exchange 관리 센터)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="a6cda-109">자세한 내용은 새 Exchange 관리 센터의 메일 흐름 [보고서를 참조하세요.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="a6cda-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="a6cda-110">[Exchange 전송 규칙 보고서는](view-email-security-reports.md#exchange-transport-rule-report) Microsoft 365 Defender 포털에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="a6cda-111">보안 & 준수 센터의 메일 흐름 [](mail-flow-insights-v2.md) 대시보드에서 사용할 수 있는 메일 흐름 보고서 외에도 보고서 대시보드에서 다양한 추가 메일 흐름 보고서를 사용하여 Microsoft 365 조직을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="a6cda-112">필요한 권한이 [](#what-permissions-are-needed-to-view-these-reports)있는 경우 보고서 대시보드로 & 보안 및 준수 [센터에서](https://protection.office.com) 이러한 보고서를 볼 **수** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="a6cda-113">보고서 대시보드로 직접 이동하기 위해 를 를 <https://protection.office.com/insightdashboard> 습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![보안 및 준수 센터의 & 보고서](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="a6cda-115">커넥터 보고서</span><span class="sxs-lookup"><span data-stu-id="a6cda-115">Connector report</span></span>

<span data-ttu-id="a6cda-116">커넥터 **보고서에는** 조직에 대해 [](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 구성된 인바운드 및 아웃바운드 커넥터의 메일 흐름 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="a6cda-117">보고서를 표시하려면 보안 및 준수 & 를  열고 보고서 [대시보드로](https://protection.office.com)이동한 다음 \>  커넥터 **보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="a6cda-118">보고서로 직접 이동하기 위해 를 를 <https://protection.office.com/reportv2?id=ConnectorReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![보고서 대시보드의 커넥터 보고서 위젯](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="a6cda-120">커넥터 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-120">Report view for the Connector report</span></span>

<span data-ttu-id="a6cda-121">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="a6cda-122">**다음을 통해** 데이터 보기: 메일 흐름 : 이 차트는 다음을 통해 구성되는 인바운드 및 아웃바운드 메시지 수를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="a6cda-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="a6cda-123">**합계**</span><span class="sxs-lookup"><span data-stu-id="a6cda-123">**Total**</span></span>
  - <span data-ttu-id="a6cda-124">**커넥터가 없는 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="a6cda-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="a6cda-125">**커넥터가 없는 인터넷으로**</span><span class="sxs-lookup"><span data-stu-id="a6cda-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="a6cda-126">구성한 특정 커넥터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="a6cda-127">차트에서 데이터를 격리하려면 컨트롤에  대한 데이터 표시를 사용하여 이러한 옵션 중 하나 또는 모든 메일 **흐름을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![커넥터 보고서에서 메일 흐름으로 데이터 보기](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="a6cda-129">**다음을 통해 데이터 보기: TLS** 사용: 이 차트는 메일 흐름에 대한 TLS(전송 계층 보안) 버전 사용량의 백분율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="a6cda-130">차트에서 데이터를 격리하려면 컨트롤에 대한 데이터 **표시를** 사용하여 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="a6cda-131">**모든 메일 흐름**</span><span class="sxs-lookup"><span data-stu-id="a6cda-131">**All mail flow**</span></span>
  - <span data-ttu-id="a6cda-132">**커넥터가 없는 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="a6cda-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="a6cda-133">**커넥터가 없는 인터넷으로**</span><span class="sxs-lookup"><span data-stu-id="a6cda-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="a6cda-134">구성한 특정 커넥터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-134">A specific connector that you've configured.</span></span>

  ![커넥터 보고서에서 TLS 사용 현황으로 데이터 보기](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="a6cda-136">보고서 보기에서 **필터를** 클릭하면 시작 날짜 및  종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="a6cda-137">커넥터 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-137">Details table view for the Connector report</span></span>

<span data-ttu-id="a6cda-138">보고서 보기에서 **세부** 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a6cda-139">**날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-139">**Date**</span></span>
- <span data-ttu-id="a6cda-140">**커넥터 방향 및 이름**</span><span class="sxs-lookup"><span data-stu-id="a6cda-140">**Connector direction and name**</span></span>
- <span data-ttu-id="a6cda-141">**커넥터 유형**</span><span class="sxs-lookup"><span data-stu-id="a6cda-141">**Connector type**</span></span>
- <span data-ttu-id="a6cda-142">**강제 TLS?**: 값 **True** 또는 **False입니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="a6cda-143">**TLS** 없음(백분율)</span><span class="sxs-lookup"><span data-stu-id="a6cda-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="a6cda-144">**TLS 1.0(백분율)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="a6cda-145">**TLS 1.1(백분율)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="a6cda-146">**TLS 1.2(백분율)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="a6cda-147">**Volume**: 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="a6cda-148">세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a6cda-149">보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="a6cda-150">Exchange 전송 규칙 보고서</span><span class="sxs-lookup"><span data-stu-id="a6cda-150">Exchange transport rule report</span></span>

<span data-ttu-id="a6cda-151">**Exchange 전송 규칙 보고서는** 메일 흐름 규칙(전송 규칙)이 조직에서 들어오는 메시지와 보내고 있는 메시지에 대한 영향을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="a6cda-152">보고서를 표시하려면 보안 및 준수 & 를  열고 [보고서 대시보드로](https://protection.office.com)이동한 다음 \>  Exchange 전송 **규칙을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="a6cda-153">보고서로 직접 이동하기 위해 를 를 <https://protection.office.com/reportv2?id=ETRRuleReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![보고서 대시보드의 Exchange 전송 규칙 위젯](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="a6cda-155">Exchange 전송 규칙 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="a6cda-156">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="a6cda-157">**데이터 보기: Exchange 전송 규칙** \> **분석 결과: 방향:** 이 차트에는  전송  규칙의 영향을 받은 인바운드 및 아웃바운드 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="a6cda-158">**데이터 보기: Exchange 전송 규칙** \> **분석 결과: 심각도:** 이 차트는  높은 심각도 및 보통 심각도 및 낮은 심각도 **메시지의 수를** 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="a6cda-159">심각도 수준을 규칙의 작업으로 설정할 수 있습니다(**심각도** 수준 또는 _SetAuditSeverity로_ 이 규칙 감사).</span><span class="sxs-lookup"><span data-stu-id="a6cda-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="a6cda-160">자세한 내용은 [Exchange Online의 메일 흐름 규칙 작업을 참조하세요.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="a6cda-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="a6cda-161">**데이터 보기: DLP Exchange 전송 규칙** \> **분석 결과: 방향:** 이 차트에는  DLP(데이터 손실 방지) 전송 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지 수가 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="a6cda-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="a6cda-162">다음 옵션 중 을 선택하여 차트를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="a6cda-163">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="a6cda-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="a6cda-164">**데이터 표시: 손상된 사용자**</span><span class="sxs-lookup"><span data-stu-id="a6cda-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="a6cda-165">**데이터 표시: 미국 애국법이 검색된 콘텐츠의 양이 적습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="a6cda-166">**데이터 보기: DLP Exchange 전송 규칙** \> **세분화: 방향:** 이 보기에는  높은 심각도 및 보통 심각도 및 DLP 전송 규칙의 영향을 받은 낮은 심각도 메시지 수가 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="a6cda-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="a6cda-167">다음 옵션 중 을 선택하여 차트를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="a6cda-168">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="a6cda-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="a6cda-169">**데이터 표시: 손상된 사용자**</span><span class="sxs-lookup"><span data-stu-id="a6cda-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="a6cda-170">**데이터 표시: 미국 애국법이 검색된 콘텐츠의 양이 적습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="a6cda-171">보고서 보기에서 **필터를** 클릭하면 다음과 같은 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="a6cda-172">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="a6cda-173">방향 값</span><span class="sxs-lookup"><span data-stu-id="a6cda-173">Direction values</span></span>
- <span data-ttu-id="a6cda-174">심각도 값</span><span class="sxs-lookup"><span data-stu-id="a6cda-174">Severity values</span></span>

![Exchange 전송 규칙 보고서의 보고서 보기](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="a6cda-176">Exchange 전송 규칙 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="a6cda-177">세부 정보 **표 보기를** 클릭하면 표시되는 정보가 보고 있는 차트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a6cda-178">**데이터 보기: Exchange 전송 규칙:**</span><span class="sxs-lookup"><span data-stu-id="a6cda-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="a6cda-179">**날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-179">**Date**</span></span>
  - <span data-ttu-id="a6cda-180">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="a6cda-180">**Transport rule**</span></span>
  - <span data-ttu-id="a6cda-181">**제목**</span><span class="sxs-lookup"><span data-stu-id="a6cda-181">**Subject**</span></span>
  - <span data-ttu-id="a6cda-182">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="a6cda-182">**Sender address**</span></span>
  - <span data-ttu-id="a6cda-183">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="a6cda-183">**Recipient address**</span></span>
  - <span data-ttu-id="a6cda-184">**심각도**</span><span class="sxs-lookup"><span data-stu-id="a6cda-184">**Severity**</span></span>
  - <span data-ttu-id="a6cda-185">**방향**</span><span class="sxs-lookup"><span data-stu-id="a6cda-185">**Direction**</span></span>

- <span data-ttu-id="a6cda-186">**데이터 보기: DLP Exchange 전송 규칙:**</span><span class="sxs-lookup"><span data-stu-id="a6cda-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="a6cda-187">**날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-187">**Date**</span></span>
  - <span data-ttu-id="a6cda-188">**DLP 정책**</span><span class="sxs-lookup"><span data-stu-id="a6cda-188">**DLP policy**</span></span>
  - <span data-ttu-id="a6cda-189">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="a6cda-189">**Transport rule**</span></span>
  - <span data-ttu-id="a6cda-190">**제목**</span><span class="sxs-lookup"><span data-stu-id="a6cda-190">**Subject**</span></span>
  - <span data-ttu-id="a6cda-191">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="a6cda-191">**Sender address**</span></span>
  - <span data-ttu-id="a6cda-192">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="a6cda-192">**Recipient address**</span></span>
  - <span data-ttu-id="a6cda-193">**심각도**</span><span class="sxs-lookup"><span data-stu-id="a6cda-193">**Severity**</span></span>
  - <span data-ttu-id="a6cda-194">**방향**</span><span class="sxs-lookup"><span data-stu-id="a6cda-194">**Direction**</span></span>

<span data-ttu-id="a6cda-195">세부 정보 테이블 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a6cda-196">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="a6cda-197">방향 값</span><span class="sxs-lookup"><span data-stu-id="a6cda-197">Direction values</span></span>
- <span data-ttu-id="a6cda-198">심각도 값</span><span class="sxs-lookup"><span data-stu-id="a6cda-198">Severity values</span></span>

<span data-ttu-id="a6cda-199">보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="a6cda-200">전달 보고서</span><span class="sxs-lookup"><span data-stu-id="a6cda-200">Forwarding report</span></span>

<span data-ttu-id="a6cda-201">전달 **보고서에는** 조직의 자동 전달된 메시지가 사서함의 외부 도메인으로 Exchange Online 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="a6cda-202">전달된 메시지는 보안 또는 규정 준수 위험을 내포할 수 있으며 계정이 손상된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="a6cda-203">보고서를 표시하려면 보안 및 준수 & 를 열고 [보고서 대시보드로](https://protection.office.com)이동한 다음 보고서  \>  **전달을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="a6cda-204">보고서로 직접 이동하기 위해 를 를 <https://protection.office.com/reportv2?id=MailFlowForwarding> 습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![보고서 대시보드의 보고서 위젯 전달](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="a6cda-206">전달 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="a6cda-207">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a6cda-208">**데이터 표시: 전달** 메서드: 다음 메서드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="a6cda-209">**전송 규칙:** 메일 흐름 [규칙으로도 알려져 있습니다.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="a6cda-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="a6cda-210">**사서함 규칙:** 받은 편지함 [규칙으로도 알려져 있습니다.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="a6cda-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![전달 보고서의 전달 메서드 보기](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="a6cda-212">**데이터 표시:** 도메인 전달: 이 보기에는 전달 대상인 받는 사람 도메인이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![전달 보고서의 도메인 전달 보기](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="a6cda-214">**다음에 대한 데이터 표시: 전달자:** 다음 전달자 표시</span><span class="sxs-lookup"><span data-stu-id="a6cda-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="a6cda-215">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="a6cda-215">**Transport rule**</span></span>
  - <span data-ttu-id="a6cda-216">전달 받은 편지함 규칙이 포함된 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![전달 보고서의 전달자 보기](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="a6cda-218">보고서 보기에서 **필터를** 클릭하면 시작 날짜 및  종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="a6cda-219">전달 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="a6cda-220">보고서 보기에서 **세부** 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a6cda-221">**전달자:** 전달 **받은** 편지함 규칙이 포함된 사서함 또는 전송 규칙 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="a6cda-222">**전달 유형**: 값 **사서함** 규칙 또는 **전송 규칙입니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="a6cda-223">**받는 사람 이름**</span><span class="sxs-lookup"><span data-stu-id="a6cda-223">**Recipient name**</span></span>
- <span data-ttu-id="a6cda-224">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="a6cda-224">**Recipient domain**</span></span>
- <span data-ttu-id="a6cda-225">**세부 정보:** 메일 흐름 규칙의 GUID 값 또는 받은 편지함 규칙의 RuleIdentity 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="a6cda-226">**개수**</span><span class="sxs-lookup"><span data-stu-id="a6cda-226">**Count**</span></span>
- <span data-ttu-id="a6cda-227">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-227">**First forward date**</span></span>

<span data-ttu-id="a6cda-228">세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a6cda-229">보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="a6cda-230">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="a6cda-230">Mailflow status report</span></span>

<span data-ttu-id="a6cda-231">메일 **흐름 상태 보고서는** [](#sent-and-received-email-report)전송 및 수신 전자 메일 보고서와 유사하며, 에지에서 허용되거나 차단되는 전자 메일에 대한 추가 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="a6cda-232">이 보고서는 에지 보호 정보를 포함하는 유일한 보고서로, EOP(에지 보호)의 평가를 위해 서비스에 허용되기 전에 차단되는 전자 메일의 Exchange Online Protection 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a6cda-233">받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지가 아니라 5개의 다른 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="a6cda-234">보고서를 확인하려면 보안 및 준수 & 를 열고 보고서 [대시보드로](https://protection.office.com)이동하여 메일 흐름 상태  \>  **보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="a6cda-235">메일 흐름 상태 보고서로 직접 **이동하기 위해 를** 열고 을 을 를 열 수 <https://protection.office.com/mailflowStatusReport> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![보고서 대시보드의 메일 흐름 상태 보고서 위젯](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="a6cda-237">메일 흐름 상태 보고서의 형식 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="a6cda-238">보고서를 열면 유형 **탭이** 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="a6cda-239">기본적으로 이 보기에는 차트와 다음 필터로 구성된 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a6cda-240">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="a6cda-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="a6cda-241">**방향**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-241">**Direction**:</span></span>

  - <span data-ttu-id="a6cda-242">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="a6cda-242">**Inbound**</span></span>
  - <span data-ttu-id="a6cda-243">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="a6cda-243">**Outbound**</span></span>
  - <span data-ttu-id="a6cda-244">**Intra-org**: 이 개수는 테넌트 내의 메시지에 대한 수입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="a6cda-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="a6cda-245">보낸 사람 abc@domain.com 받는 사람 주소로 xyz@domain.com(인바운드 및 아웃바운드와 별도로 **계산)** </span><span class="sxs-lookup"><span data-stu-id="a6cda-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="a6cda-246">**유형:**</span><span class="sxs-lookup"><span data-stu-id="a6cda-246">**Type**:</span></span>

  - <span data-ttu-id="a6cda-247">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-247">**Good mail**</span></span>
  - <span data-ttu-id="a6cda-248">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="a6cda-248">**Malware**</span></span>
  - <span data-ttu-id="a6cda-249">**스팸**</span><span class="sxs-lookup"><span data-stu-id="a6cda-249">**Spam**</span></span>
  - <span data-ttu-id="a6cda-250">**에지 보호**</span><span class="sxs-lookup"><span data-stu-id="a6cda-250">**Edge protection**</span></span>
  - <span data-ttu-id="a6cda-251">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="a6cda-251">**Rule messages**</span></span>
  - <span data-ttu-id="a6cda-252">**피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-252">**Phishing email**</span></span>

<span data-ttu-id="a6cda-253">차트는 종류 값으로 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="a6cda-254">필터를 클릭하거나 차트  범례에서 값을 클릭하여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="a6cda-255">데이터 테이블에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-255">The data table contains the following information:</span></span>

- <span data-ttu-id="a6cda-256">**방향**</span><span class="sxs-lookup"><span data-stu-id="a6cda-256">**Direction**</span></span>
- <span data-ttu-id="a6cda-257">**유형**</span><span class="sxs-lookup"><span data-stu-id="a6cda-257">**Type**</span></span>
- <span data-ttu-id="a6cda-258">**24시간**</span><span class="sxs-lookup"><span data-stu-id="a6cda-258">**24 hours**</span></span>
- <span data-ttu-id="a6cda-259">**3일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-259">**3 days**</span></span>
- <span data-ttu-id="a6cda-260">**7일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-260">**7 days**</span></span>
- <span data-ttu-id="a6cda-261">**15일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-261">**15 days**</span></span>
- <span data-ttu-id="a6cda-262">**30일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-262">**30 days**</span></span>

<span data-ttu-id="a6cda-263">자세한 내용을 **보려면 범주** 선택을 클릭하면 다음 값에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="a6cda-264">**피싱 전자 메일:** 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="a6cda-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="a6cda-265">**전자 메일의** 맬웨어: 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="a6cda-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="a6cda-266">**스팸 검색:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="a6cda-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="a6cda-267">**Edge 차단 스팸:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="a6cda-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="a6cda-268">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-268">**Export**:</span></span>

<span data-ttu-id="a6cda-269">세부 정보 보기의 경우 하루 동안만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="a6cda-270">따라서 7일 동안 데이터를 내보내는 경우 7개 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="a6cda-271">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a6cda-272">해당 일의 데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![메일 흐름 상태 보고서에 보기 입력](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="a6cda-274">메일 흐름 상태 보고서의 방향 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="a6cda-275">방향 탭을 **클릭하면** 유형 보기의 동일한 기본 **필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="a6cda-276">차트는 방향 값으로 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="a6cda-277">필터를 클릭하거나 차트  범례에서 값을 클릭하여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="a6cda-278">형식 보기의 **동일한 필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="a6cda-279">데이터 테이블에는 형식 보기와 동일한 **정보가** 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="a6cda-280">사용 가능한 선택 **항목** 및 동작에 대한 자세한 내용은 종류 보기와 **같습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="a6cda-281">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-281">**Export**:</span></span>

<span data-ttu-id="a6cda-282">세부 정보 보기의 경우 하루 동안만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="a6cda-283">따라서 7일 동안 데이터를 내보내는 경우 7개 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="a6cda-284">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a6cda-285">해당 일의 데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![메일 흐름 상태 보고서의 방향 보기](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="a6cda-287">메일 흐름 상태 보고서의 유입경로 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="a6cda-288">**Funnel** 보기는 Microsoft의 전자 메일 위협 방지 기능이 조직에서 받는 전자 메일과 보내기 전자 메일을 필터링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="a6cda-289">전체 전자 메일 수와 에지 보호, 맬웨어 방지, 피싱 방지, 스팸 방지 및 스푸핑 방지를 포함하여 구성된 위협 방지 기능이 이 수에 미치는 영향을 자세히 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="a6cda-290">**FUNNel** 탭을 클릭하면 기본적으로 이 보기에는 차트와 다음 필터로 구성된 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a6cda-291">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="a6cda-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="a6cda-292">**방향**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-292">**Direction**:</span></span>

  - <span data-ttu-id="a6cda-293">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="a6cda-293">**Inbound**</span></span>
  - <span data-ttu-id="a6cda-294">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="a6cda-294">**Outbound**</span></span>
  - <span data-ttu-id="a6cda-295">**Intra-org:** 이 개수는 테넌트 내에서 보낸 메시지에 대한 수입니다. 즉, 보낸 abc@domain.com 받는 사람 xyz@domain.com(인바운드 및 아웃바운드와는 별도로 계산)를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="a6cda-296">집계 보기 및 데이터 테이블 보기는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="a6cda-297">필터를 **클릭하면** 차트와 데이터 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="a6cda-298">이 차트에는 다음별로 구성한 전자 메일 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="a6cda-299">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-299">**Total email**</span></span>
- <span data-ttu-id="a6cda-300">**Edge 보호 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-300">**Email after edge protection**</span></span>
- <span data-ttu-id="a6cda-301">**맬웨어 방지, 파일 신뢰도, 파일 형식 차단 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="a6cda-302">**피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="a6cda-303">**스팸 방지, 대량 메일 필터링 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="a6cda-304">**사용자 및 도메인** 가장 후 전자 메일 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6cda-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="a6cda-305">**파일 후 전자 메일 및 URL 확인**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6cda-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="a6cda-306">**배달 후 보호 후 무해한 것으로 감지된 전자 메일(URL 클릭 시간 보호)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="a6cda-307"><sup>1</sup> Defender for Office 365 전용</span><span class="sxs-lookup"><span data-stu-id="a6cda-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="a6cda-308">EOP 또는 Defender에서 필터링한 전자 메일을 개별적으로 Office 365 차트 범례의 값을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="a6cda-309">데이터 테이블에는 내선 날짜 순서로 표시되는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="a6cda-310">**날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-310">**Date**</span></span>
- <span data-ttu-id="a6cda-311">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-311">**Total email**</span></span>
- <span data-ttu-id="a6cda-312">**에지 보호**</span><span class="sxs-lookup"><span data-stu-id="a6cda-312">**Edge protection**</span></span>
- <span data-ttu-id="a6cda-313">**맬웨어 방지, 파일 신뢰도, 파일 형식 블록**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="a6cda-314">**파일 신뢰도:** 다른 Microsoft 고객이 첨부한 파일을 식별하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="a6cda-315">**파일 형식 블록:** 메시지에 식별된 악성 파일의 유형으로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="a6cda-316">**피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="a6cda-317">**URL 신뢰도:** 다른 Microsoft 고객이 URL을 식별하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="a6cda-318">**브랜드 가장:** 보낸 사람으로 가장하는 잘 알려진 브랜드에서 보낸 메시지로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="a6cda-319">**스푸핑** 방지: 받는 사람이 속한 도메인 또는 메시지 보낸 사람이 소유하지 않은 도메인을 스푸핑하려고 시도하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="a6cda-320">**스팸 방지, 대량 메일 필터링**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="a6cda-321">**대량 메일 필터링:** 받는 사람에게 대량 메일을 배달하려고 하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="a6cda-322">**사용자 및 도메인 가장(사용자** 및 도메인 Office 365) :</span><span class="sxs-lookup"><span data-stu-id="a6cda-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="a6cda-323">**사용자 가장:** 피싱 방지 정책의 가장 보호 설정에 정의된 사용자(메시지 보낸 사람)를 가장하려는 시도로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="a6cda-324">**도메인 가장:** 피싱 방지 정책의 가장 보호 설정에 정의된 도메인을 가장하려고 시도하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="a6cda-325">**파일 및 URL 확인(Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="a6cda-326">**파일 검색:** 첨부 파일 Safe 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="a6cda-327">**URL 검색:** 링크 정책에 의해 Safe 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="a6cda-328">**사후 배달 보호 및 ZAP(ATP) 또는 EOP(ZAP)**: ZAP는 제로 아워 자동 제거를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="a6cda-329">데이터 테이블에서 행을 선택하면 플라이아웃에 전자 메일 수의 추가 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="a6cda-330">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-330">**Export**:</span></span>

<span data-ttu-id="a6cda-331">옵션에서 **내보내기** 를 **클릭한** 후 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="a6cda-332">**요약(최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="a6cda-333">**세부 정보(지난 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="a6cda-334">**날짜에서** 범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="a6cda-335">현재 필터에 대한 데이터는 파일로 .csv 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="a6cda-336">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a6cda-337">데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![메일 흐름 상태 보고서의 유입경로 보기](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="a6cda-339">메일 흐름 상태 보고서의 기술 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="a6cda-340">기술 **보기는** **Funnel** 보기와 유사하여 구성된 위협 방지 기능에 대해 보다 세부적인 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="a6cda-341">차트에서 다양한 위협 방지 단계에서 메시지를 분류하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="a6cda-342">기술 보기  탭을 클릭하면 기본적으로 이 보기에는 차트와 다음 필터로 구성된 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a6cda-343">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="a6cda-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="a6cda-344">**방향**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-344">**Direction**:</span></span>

  - <span data-ttu-id="a6cda-345">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="a6cda-345">**Inbound**</span></span>
  - <span data-ttu-id="a6cda-346">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="a6cda-346">**Outbound**</span></span>
  - <span data-ttu-id="a6cda-347">**Intra-org**: 이 개수는 테넌트 내의 메시지에 대한 수입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="a6cda-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="a6cda-348">보낸 사람 abc@domain.com 받는 사람 주소로 xyz@domain.com(인바운드 및 아웃바운드와 별도로 계산)</span><span class="sxs-lookup"><span data-stu-id="a6cda-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="a6cda-349">집계 보기 및 데이터 테이블 보기는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="a6cda-350">필터를 **클릭하면** 차트와 데이터 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="a6cda-351">이 차트에는 다음 범주로 구성된 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="a6cda-352">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-352">**Total email**</span></span>
- <span data-ttu-id="a6cda-353">**Edge 허용** 및 **Edge 필터링**</span><span class="sxs-lookup"><span data-stu-id="a6cda-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="a6cda-354">**맬웨어가 아닌** **경우** Safe 검색, 맬웨어 방지 엔진 검색 <sup>\*</sup> 및 **규칙 메시지** </span><span class="sxs-lookup"><span data-stu-id="a6cda-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="a6cda-355">**피싱이 아닌** 경우, **DMARC 실패,** 가장 **검색,** **스푸핑 검색** 및 **피싱 감지**</span><span class="sxs-lookup"><span data-stu-id="a6cda-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="a6cda-356">**URL 검색 및 URL** 검색을 통해 검색 **안 하세요.**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a6cda-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="a6cda-357">**스팸 및**  **스팸 아미기**</span><span class="sxs-lookup"><span data-stu-id="a6cda-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="a6cda-358">**악성이 아닌 전자** **메일, Safe 링크** 검색 및 <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="a6cda-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="a6cda-359"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a6cda-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="a6cda-360">차트의 범주 위에 마우스를 대면 해당 범주의 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="a6cda-361">데이터 테이블에는 내선 날짜 순서로 표시되는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="a6cda-362">**날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-362">**Date**</span></span>
- <span data-ttu-id="a6cda-363">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-363">**Total email**</span></span>
- <span data-ttu-id="a6cda-364">**Edge 필터링**</span><span class="sxs-lookup"><span data-stu-id="a6cda-364">**Edge filtered**</span></span>
- <span data-ttu-id="a6cda-365">**맬웨어 방지 엔진, Safe 필터링된 규칙**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="a6cda-366">**필터링된 규칙:** 메일 흐름 규칙(전송 규칙)으로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="a6cda-367">**DMARC, 가장, 스푸핑, 피싱 필터링:**</span><span class="sxs-lookup"><span data-stu-id="a6cda-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="a6cda-368">**DMARC: DMARC** 인증 검사에 실패한 메시지로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="a6cda-369">**URL 검색**</span><span class="sxs-lookup"><span data-stu-id="a6cda-369">**URL detonation detection**</span></span>
- <span data-ttu-id="a6cda-370">**스팸 방지 필터링**</span><span class="sxs-lookup"><span data-stu-id="a6cda-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="a6cda-371">**ZAP 제거됨**</span><span class="sxs-lookup"><span data-stu-id="a6cda-371">**ZAP removed**</span></span>
- <span data-ttu-id="a6cda-372">**링크로 Safe 검색**</span><span class="sxs-lookup"><span data-stu-id="a6cda-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="a6cda-373">데이터 테이블에서 행을 선택하면 플라이아웃에 전자 메일 수의 추가 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="a6cda-374">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="a6cda-374">**Export**:</span></span>

<span data-ttu-id="a6cda-375">내보내기 **를 클릭할** 때 **옵션에서** 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="a6cda-376">**요약(최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="a6cda-377">**세부 정보(지난 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="a6cda-378">**날짜에서** 범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="a6cda-379">현재 필터에 대한 데이터는 파일로 .csv 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="a6cda-380">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a6cda-381">데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![메일 흐름 상태 보고서의 기술 보기](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="a6cda-383">보낸 전자 메일 보고서 및 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="a6cda-383">Sent and received email report</span></span>

<span data-ttu-id="a6cda-384">보내고 **받은** 전자 메일 보고서는 스팸 검색, 맬웨어 및 "양호"로 식별된 전자 메일을 포함하여 들어오고 받는 전자 메일에 대한 정보를 표시하는 스마트 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="a6cda-385">이 보고서와 [메일](#mailflow-status-report) 흐름 상태 보고서의 차이점은 이 보고서에는 에지 보호로 차단된 메시지에 대한 데이터가 포함되어 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="a6cda-386">**참고:** 받는 사람 5명에게 메시지가 전송된 경우 메시지를 하나의 메시지로 계산한다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="a6cda-387">보고서의 집계 보기 및 세부 정보 보기는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="a6cda-388">보고서를 확인하려면 보안 및 준수 & 를 열고 [보고서 대시보드로](https://protection.office.com)이동하여 보내고 받은 전자  \>  **메일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="a6cda-389">보고서로 직접 이동하기 위해 를 를 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![보고서 대시보드에서 보내고 받은 전자 메일 위젯](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="a6cda-391">보내고 받은 전자 메일 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="a6cda-392">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a6cda-393">**세분화하여 다음을 입력합니다.** 차트에는 사용 가능한 모든 범주가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="a6cda-394">**합계**</span><span class="sxs-lookup"><span data-stu-id="a6cda-394">**Total**</span></span>
  - <span data-ttu-id="a6cda-395">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="a6cda-395">**Good mail**</span></span>
  - <span data-ttu-id="a6cda-396">**맬웨어(맬웨어** 방지)(EOP)</span><span class="sxs-lookup"><span data-stu-id="a6cda-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="a6cda-397">**스팸 감지**</span><span class="sxs-lookup"><span data-stu-id="a6cda-397">**Spam detections**</span></span>
  - <span data-ttu-id="a6cda-398">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="a6cda-398">**Rule messages**</span></span>
  - <span data-ttu-id="a6cda-399">**고급 맬웨어(Microsoft** Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="a6cda-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="a6cda-400">차트에서 하루(데이터 데이터 포인트)를 마우스로 마우스로 대면 해당 일자에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보내고 받은 전자 메일 보고서에 보기 입력](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="a6cda-402">**분석 결과: 방향:** 차트에 **총,** 인바운드 **및** 아웃바운드 **데이터가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="a6cda-403">차트에서 하루(데이터 데이터 포인트)를 마우스로 마우스로 대면 해당 일자에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보내고 받은 전자 메일 보고서의 방향 보기](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="a6cda-405">**드릴다운** \> **맬웨어(맬웨어 방지)**: 이 선택을 통해 맬웨어 검색 [보고서로 진행됩니다.](view-email-security-reports.md#malware-detections-report)</span><span class="sxs-lookup"><span data-stu-id="a6cda-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="a6cda-406">**드릴다운** \> **스팸 검색)**: 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="a6cda-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="a6cda-407">보고서 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a6cda-408">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="a6cda-409">방향 값</span><span class="sxs-lookup"><span data-stu-id="a6cda-409">Direction values</span></span>
- <span data-ttu-id="a6cda-410">형식 값</span><span class="sxs-lookup"><span data-stu-id="a6cda-410">Type values</span></span>

<span data-ttu-id="a6cda-411">보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="a6cda-412">보내고 받은 전자 메일 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="a6cda-413">세분화로: 방향 또는  세분화:  방향 보기에서 세부 정보 표 보기를 클릭하면 다음 정보가 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="a6cda-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="a6cda-414">**날짜(UTC)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-414">**Date (UTC)**</span></span>
- <span data-ttu-id="a6cda-415">**유형**</span><span class="sxs-lookup"><span data-stu-id="a6cda-415">**Type**</span></span>
- <span data-ttu-id="a6cda-416">**방향**</span><span class="sxs-lookup"><span data-stu-id="a6cda-416">**Direction**</span></span>
- <span data-ttu-id="a6cda-417">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="a6cda-417">**Message count**</span></span>

<span data-ttu-id="a6cda-418">세부 정보 테이블 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a6cda-419">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="a6cda-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="a6cda-420">방향 값</span><span class="sxs-lookup"><span data-stu-id="a6cda-420">Direction values</span></span>
- <span data-ttu-id="a6cda-421">형식 값</span><span class="sxs-lookup"><span data-stu-id="a6cda-421">Type values</span></span>

<span data-ttu-id="a6cda-422">보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="a6cda-423">상위 보낸 사람 및 받는 사람 보고서</span><span class="sxs-lookup"><span data-stu-id="a6cda-423">Top senders and recipients report</span></span>

<span data-ttu-id="a6cda-424">상위 **보낸 사람 및** 받는 사람 보고서는 전자 메일 보낸 사람 및 받는 사람을 표시하는 파이 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="a6cda-425">보고서를 확인하려면 보안 및 준수 & 를 열고 [보고서 대시보드로](https://protection.office.com)이동한 다음 상위 보낸 사람 및 받는  \>  **사람을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="a6cda-426">보고서로 직접 이동하기 위해 를 를 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![보고서 대시보드의 상위 보낸 사람 및 받는 사람 위젯](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="a6cda-428">상위 보낸 사람 및 받는 사람 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="a6cda-429">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a6cda-430">**상위 메일 \> 보낸 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="a6cda-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="a6cda-431">**상위 메일 \> 받는 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="a6cda-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="a6cda-432">**상위 스팸 \> 받는 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="a6cda-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="a6cda-433">**데이터 표시 \> 상위 맬웨어** 받는 사람(EOP)</span><span class="sxs-lookup"><span data-stu-id="a6cda-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="a6cda-434">**상위 맬웨어 받는 사람에 대한 데이터 \> 표시(Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="a6cda-435">이러한 선택에 따라 파이 차트의 컴포지션이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="a6cda-436">파이 차트에서 에지 위에 마우스를 대면 보내거나 받은 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="a6cda-437">보고서 보기에서 **필터를** 클릭하면 시작 날짜 및  종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![상위 보낸 사람 및 받는 사람 보고서의 보고서 보기에 있는 파이 차트](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="a6cda-439">상위 보낸 사람 및 받는 사람 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="a6cda-440">세부 정보 **표 보기를** 클릭하면 표시되는 정보가 보고 있는 차트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a6cda-441">**상위 메일 \> 보낸 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="a6cda-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="a6cda-442">**상위 메일 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="a6cda-442">**Top mail senders**</span></span>
  - <span data-ttu-id="a6cda-443">**개수**</span><span class="sxs-lookup"><span data-stu-id="a6cda-443">**Count**</span></span>

- <span data-ttu-id="a6cda-444">**상위 메일 \> 받는 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="a6cda-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="a6cda-445">**상위 메일 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="a6cda-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="a6cda-446">**개수**</span><span class="sxs-lookup"><span data-stu-id="a6cda-446">**Count**</span></span>

- <span data-ttu-id="a6cda-447">**상위 스팸 \> 받는 사람에 대한 데이터 표시**</span><span class="sxs-lookup"><span data-stu-id="a6cda-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="a6cda-448">**상위 스팸 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="a6cda-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="a6cda-449">**개수**</span><span class="sxs-lookup"><span data-stu-id="a6cda-449">**Count**</span></span>

- <span data-ttu-id="a6cda-450">**데이터 표시 \> 상위 맬웨어** 받는 사람(EOP)</span><span class="sxs-lookup"><span data-stu-id="a6cda-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="a6cda-451">**상위 맬웨어 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="a6cda-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="a6cda-452">**개수**</span><span class="sxs-lookup"><span data-stu-id="a6cda-452">**Count**</span></span>

- <span data-ttu-id="a6cda-453">**상위 맬웨어 받는 사람에 대한 데이터 \> 표시(Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="a6cda-454">**상위 맬웨어 받는 사람(Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="a6cda-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="a6cda-455">**개수**</span><span class="sxs-lookup"><span data-stu-id="a6cda-455">**Count**</span></span>

<span data-ttu-id="a6cda-456">세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a6cda-457">보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6cda-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="a6cda-458">이러한 보고서를 보는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="a6cda-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="a6cda-459">이 문서에 설명된 보고서를 보고 사용하려면 Security & Compliance Center에서 다음 역할 그룹 중 하나에 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a6cda-460">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="a6cda-460">**Organization Management**</span></span>
- <span data-ttu-id="a6cda-461">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="a6cda-461">**Security Administrator**</span></span>
- <span data-ttu-id="a6cda-462">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="a6cda-462">**Security Reader**</span></span>
- <span data-ttu-id="a6cda-463">**전역 읽기**</span><span class="sxs-lookup"><span data-stu-id="a6cda-463">**Global Reader**</span></span>

<span data-ttu-id="a6cda-464">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6cda-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a6cda-465">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6cda-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a6cda-466">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6cda-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a6cda-467">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a6cda-467">Related topics</span></span>

[<span data-ttu-id="a6cda-468">보안 및 준수 센터의 스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="a6cda-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="a6cda-469">보안 및 준수 센터의 메일 흐름 파악</span><span class="sxs-lookup"><span data-stu-id="a6cda-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="a6cda-470">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="a6cda-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="a6cda-471">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a6cda-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
