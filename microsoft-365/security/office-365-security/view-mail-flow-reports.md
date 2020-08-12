---
title: 보고서 대시보드에서 메일 흐름 보고서 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 보안 & 준수 센터의 보고서 대시보드에서 사용할 수 있는 메일 흐름 보고서에 대해 알아볼 수 있습니다.
ms.custom: ''
ms.openlocfilehash: acf74136fc61d38ea9aac47f36d96aa51a7b9905
ms.sourcegitcommit: 6319e73b3690b4cf1b7932f2b9f51c2c99e70eaa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "46635037"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="939fa-103">보안 & 준수 센터의 보고서 대시보드에서 메일 흐름 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="939fa-104">보안 & 준수 센터의 [메일 흐름 대시보드에서](mail-flow-insights-v2.md) 사용할 수 있는 메일 흐름 보고서 외에도, Microsoft 365 조직을 모니터링 하는 데 도움이 되도록 보고서 대시보드에서 다양 한 추가 메일 흐름 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="939fa-105">[필요한 권한이](#what-permissions-are-needed-to-view-these-reports)있는 경우 **보고서** 대시보드로 이동 하 여 [보안 & 준수 센터](https://office.protection.com) 에서 이러한 보고서를 볼 수 있습니다 \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="939fa-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="939fa-106">보고서 대시보드로 직접 이동 하려면를 엽니다 <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="939fa-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![보안 & 준수 센터의 보고서 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="939fa-108">커넥터 보고서</span><span class="sxs-lookup"><span data-stu-id="939fa-108">Connector report</span></span>

<span data-ttu-id="939fa-109">**커넥터 보고서** 에는 조직에 대해 구성 된 [인바운드 및 아웃 바운드 커넥터](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 에 대 한 메일 흐름 활동이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="939fa-110">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **커넥터 보고서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="939fa-111">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="939fa-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![보고서 대시보드의 커넥터 보고서 위젯](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="939fa-113">커넥터 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-113">Report view for the Connector report</span></span>

<span data-ttu-id="939fa-114">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="939fa-115">**데이터 보기 기준: 메일 흐름**:이 차트에서는 다음을 기준으로 구성한 인바운드 및 아웃 바운드 메시지의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="939fa-116">**합계**</span><span class="sxs-lookup"><span data-stu-id="939fa-116">**Total**</span></span>
  - <span data-ttu-id="939fa-117">**커넥터 없이 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="939fa-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="939fa-118">**커넥터 없이 인터넷에 연결**</span><span class="sxs-lookup"><span data-stu-id="939fa-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="939fa-119">구성한 특정 커넥터</span><span class="sxs-lookup"><span data-stu-id="939fa-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="939fa-120">차트에서 데이터를 격리 하려면 다음 **에 대 한 데이터 표시** 컨트롤을 사용 하 여 이러한 옵션 중 하나 또는 **모든 메일 흐름**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![커넥터 보고서에서 메일 흐름을 기준으로 데이터 보기](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="939fa-122">**데이터 보기 기준: tls 사용량**:이 차트에서는 메일 흐름에 대 한 Tls (전송 계층 보안) 버전 사용 비율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="939fa-123">차트에서 데이터를 격리 하려면 다음 **에 대 한 데이터 표시** 컨트롤을 사용 하 여 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="939fa-124">**모든 메일 흐름**</span><span class="sxs-lookup"><span data-stu-id="939fa-124">**All mail flow**</span></span>
  - <span data-ttu-id="939fa-125">**커넥터 없이 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="939fa-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="939fa-126">**커넥터 없이 인터넷에 연결**</span><span class="sxs-lookup"><span data-stu-id="939fa-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="939fa-127">구성한 특정 커넥터</span><span class="sxs-lookup"><span data-stu-id="939fa-127">A specific connector that you've configured.</span></span>

  ![커넥터 보고서에서 TLS 사용을 기준으로 데이터 보기](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="939fa-129">보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="939fa-130">커넥터 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-130">Details table view for the Connector report</span></span>

<span data-ttu-id="939fa-131">보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="939fa-132">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939fa-132">**Date**</span></span>
- <span data-ttu-id="939fa-133">**커넥터 방향 및 이름**</span><span class="sxs-lookup"><span data-stu-id="939fa-133">**Connector direction and name**</span></span>
- <span data-ttu-id="939fa-134">**커넥터 유형**</span><span class="sxs-lookup"><span data-stu-id="939fa-134">**Connector type**</span></span>
- <span data-ttu-id="939fa-135">**강제 TLS?**: **True** 또는 **False**값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="939fa-136">**TLS 없음** (백분율)</span><span class="sxs-lookup"><span data-stu-id="939fa-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="939fa-137">**TLS 1.0** (백분율)</span><span class="sxs-lookup"><span data-stu-id="939fa-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="939fa-138">**TLS 1.1** (백분율)</span><span class="sxs-lookup"><span data-stu-id="939fa-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="939fa-139">**TLS 1.2** (백분율)</span><span class="sxs-lookup"><span data-stu-id="939fa-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="939fa-140">**볼륨**: 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="939fa-141">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="939fa-142">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="939fa-143">Exchange 전송 규칙 보고서</span><span class="sxs-lookup"><span data-stu-id="939fa-143">Exchange transport rule report</span></span>

<span data-ttu-id="939fa-144">**Exchange 전송 규칙 보고서** 는 조직에서 들어오고 나가는 메시지에 대 한 메일 흐름 규칙 (전송 규칙이 라고도 함)의 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="939fa-145">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **Exchange 전송 규칙**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="939fa-146">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="939fa-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![보고서 대시보드의 Exchange 전송 규칙 위젯](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="939fa-148">Exchange 전송 규칙 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="939fa-149">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="939fa-150">**데이터 보기 기준: Exchange 전송 규칙** \> **아래로 나누기: 방향**:이 차트에서는 전송 규칙의 영향을 받는 **인바운드** 및 **아웃 바운드** 메시지의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="939fa-151">**데이터 보기 기준: Exchange 전송 규칙** \> **아래로 나누기: 심각도**:이 차트에는 **높은 심각도** 및 **보통 심각도**및 **심각도가 낮은** 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="939fa-152">심각도 수준을 규칙의 작업으로 설정 합니다 (심각도 수준이 나 _Setauditseverity_**으로이 규칙 감사** ).</span><span class="sxs-lookup"><span data-stu-id="939fa-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="939fa-153">자세한 내용은 [Mail flow rule actions In Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="939fa-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="939fa-154">**데이터 보기 기준: DLP Exchange 전송 규칙** \> **아래로 나누기: 방향**:이 차트에서는 DLP (데이터 손실 방지) 전송 규칙의 영향을 받는 **인바운드** 및 **아웃 바운드** 메시지의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="939fa-155">다음 옵션을 선택 하 여 차트를 보다 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="939fa-156">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="939fa-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="939fa-157">**데이터 표시: 손상 된 사용자**</span><span class="sxs-lookup"><span data-stu-id="939fa-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="939fa-158">**데이터 표시: 검색 된 콘텐츠가 부족 함 미국 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="939fa-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="939fa-159">**데이터 보기 기준: DLP Exchange 전송 규칙** \> **아래로 나누기: 방향**:이 보기에는 DLP 전송 규칙의 영향을 받은 **높은 심각도** 및 **중간**심각도 메시지와 **낮은 심각도** 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="939fa-160">다음 옵션을 선택 하 여 차트를 보다 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="939fa-161">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="939fa-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="939fa-162">**데이터 표시: 손상 된 사용자**</span><span class="sxs-lookup"><span data-stu-id="939fa-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="939fa-163">**데이터 표시: 검색 된 콘텐츠가 부족 함 미국 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="939fa-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="939fa-164">보고서 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="939fa-165">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939fa-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="939fa-166">방향 값</span><span class="sxs-lookup"><span data-stu-id="939fa-166">Direction values</span></span>
- <span data-ttu-id="939fa-167">심각도 값</span><span class="sxs-lookup"><span data-stu-id="939fa-167">Severity values</span></span>

![Exchange 전송 규칙 보고서의 보고서 보기](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="939fa-169">Exchange 전송 규칙 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="939fa-170">**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="939fa-171">**데이터 보기 기준: Exchange 전송 규칙**:</span><span class="sxs-lookup"><span data-stu-id="939fa-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="939fa-172">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939fa-172">**Date**</span></span>
  - <span data-ttu-id="939fa-173">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="939fa-173">**Transport rule**</span></span>
  - <span data-ttu-id="939fa-174">**제목**</span><span class="sxs-lookup"><span data-stu-id="939fa-174">**Subject**</span></span>
  - <span data-ttu-id="939fa-175">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939fa-175">**Sender address**</span></span>
  - <span data-ttu-id="939fa-176">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939fa-176">**Recipient address**</span></span>
  - <span data-ttu-id="939fa-177">**심각도**</span><span class="sxs-lookup"><span data-stu-id="939fa-177">**Severity**</span></span>
  - <span data-ttu-id="939fa-178">**방향**</span><span class="sxs-lookup"><span data-stu-id="939fa-178">**Direction**</span></span>

- <span data-ttu-id="939fa-179">**데이터 보기 기준: DLP Exchange 전송 규칙**:</span><span class="sxs-lookup"><span data-stu-id="939fa-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="939fa-180">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939fa-180">**Date**</span></span>
  - <span data-ttu-id="939fa-181">**DLP 정책**</span><span class="sxs-lookup"><span data-stu-id="939fa-181">**DLP policy**</span></span>
  - <span data-ttu-id="939fa-182">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="939fa-182">**Transport rule**</span></span>
  - <span data-ttu-id="939fa-183">**제목**</span><span class="sxs-lookup"><span data-stu-id="939fa-183">**Subject**</span></span>
  - <span data-ttu-id="939fa-184">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939fa-184">**Sender address**</span></span>
  - <span data-ttu-id="939fa-185">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939fa-185">**Recipient address**</span></span>
  - <span data-ttu-id="939fa-186">**심각도**</span><span class="sxs-lookup"><span data-stu-id="939fa-186">**Severity**</span></span>
  - <span data-ttu-id="939fa-187">**방향**</span><span class="sxs-lookup"><span data-stu-id="939fa-187">**Direction**</span></span>

<span data-ttu-id="939fa-188">세부 정보 표 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="939fa-189">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939fa-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="939fa-190">방향 값</span><span class="sxs-lookup"><span data-stu-id="939fa-190">Direction values</span></span>
- <span data-ttu-id="939fa-191">심각도 값</span><span class="sxs-lookup"><span data-stu-id="939fa-191">Severity values</span></span>

<span data-ttu-id="939fa-192">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="939fa-193">전달 보고서</span><span class="sxs-lookup"><span data-stu-id="939fa-193">Forwarding report</span></span>

<span data-ttu-id="939fa-194">**전달 보고서** 에는 조직의 자동으로 전달 되는 메시지가 Exchange Online 사서함의 외부 도메인으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="939fa-195">전달 된 메시지는 보안 또는 준수 위험을 초래할 수 있으며 계정이 손상 된 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="939fa-196">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **전달 보고서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="939fa-197">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="939fa-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![보고서 대시보드에서 보고서 위젯 전달](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="939fa-199">전달 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="939fa-200">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="939fa-201">**데이터 표시: 전달 메서드**: 다음과 같은 메서드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="939fa-202">**전송 규칙**: [메일 흐름 규칙이](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="939fa-203">**사서함 규칙**: [받은 편지함 규칙이](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![전달 보고서의 전달 메서드 보기](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="939fa-205">**다음에 대 한 데이터 표시: 전달 도메인**:이 보기에는 전달 대상이 되는 받는 사람 도메인이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![전달 보고서의 전달 도메인 보기](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="939fa-207">**데이터 표시: 전달자**: 다음 전달자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="939fa-208">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="939fa-208">**Transport rule**</span></span>
  - <span data-ttu-id="939fa-209">전달 받은 편지함 규칙을 포함 하는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![전달 보고서의 전달자 보기](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="939fa-211">보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="939fa-212">전달 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="939fa-213">보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="939fa-214">**전달자**: 값 **전송 규칙** 또는 전달 받은 편지함 규칙을 포함 하는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="939fa-215">**전달 유형**: 값 **사서함 규칙** 또는 **전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="939fa-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="939fa-216">**받는 사람 이름**</span><span class="sxs-lookup"><span data-stu-id="939fa-216">**Recipient name**</span></span>
- <span data-ttu-id="939fa-217">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="939fa-217">**Recipient domain**</span></span>
- <span data-ttu-id="939fa-218">**Details**: 메일 흐름 규칙의 GUID 값 또는 받은 편지함 규칙의 RuleIdentity 값입니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="939fa-219">**개수**</span><span class="sxs-lookup"><span data-stu-id="939fa-219">**Count**</span></span>
- <span data-ttu-id="939fa-220">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="939fa-220">**First forward date**</span></span>

<span data-ttu-id="939fa-221">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="939fa-222">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="939fa-223">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="939fa-223">Mailflow status report</span></span>

<span data-ttu-id="939fa-224">**메일 흐름 status 보고서** 는 edge에서 허용 되거나 차단 되는 전자 메일에 대 한 추가 정보가 포함 된 [보낸 날짜 및 받은 전자 메일 보고서](#sent-and-received-email-report)와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="939fa-225">이 보고서는 edge 보호 정보를 포함 하며, EOP (Exchange Online Protection)에서 평가를 위해 서비스에 허용 되기 전에 차단 되는 전자 메일의 양을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="939fa-226">메시지가 5 명의 받는 사람에 게 전송 되는 경우 메시지가 한 명의 메시지와 다르게 계산 된다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>  
<span data-ttu-id="939fa-227">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **메일 흐름 status report**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="939fa-228">**메일 흐름 상태 보고서**로 바로 이동 하려면을 엽니다 <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="939fa-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![보고서 대시보드의 메일 흐름 상태 보고서 위젯](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="939fa-230">메일 흐름 상황 보고서의 형식 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="939fa-231">보고서를 열 때 **형식** 탭이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="939fa-232">기본적으로이 보기에는 다음 필터를 사용 하 여 구성 된 차트 및 데이터 테이블이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="939fa-233">**날짜**: 지난 7 일</span><span class="sxs-lookup"><span data-stu-id="939fa-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="939fa-234">**방향**:</span><span class="sxs-lookup"><span data-stu-id="939fa-234">**Direction**:</span></span>

  - <span data-ttu-id="939fa-235">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="939fa-235">**Inbound**</span></span>
  - <span data-ttu-id="939fa-236">**아웃 바운드**</span><span class="sxs-lookup"><span data-stu-id="939fa-236">**Outbound**</span></span>
  - <span data-ttu-id="939fa-237">**조직 내**:이 수는 테 넌 트 내의 메시지에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="939fa-238">보낸 사람 abc@domain.com이 받는 사람 xyz@domain.com에 게 전송 합니다 ( **인바운드** 및 **아웃 바운드**와 별도로 계산 됨).</span><span class="sxs-lookup"><span data-stu-id="939fa-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="939fa-239">다음을 **입력**합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-239">**Type**:</span></span>

  - <span data-ttu-id="939fa-240">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="939fa-240">**Good mail**</span></span>
  - <span data-ttu-id="939fa-241">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="939fa-241">**Malware**</span></span>
  - <span data-ttu-id="939fa-242">**스팸**</span><span class="sxs-lookup"><span data-stu-id="939fa-242">**Spam**</span></span>
  - <span data-ttu-id="939fa-243">**에 지 보호**</span><span class="sxs-lookup"><span data-stu-id="939fa-243">**Edge protection**</span></span>
  - <span data-ttu-id="939fa-244">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="939fa-244">**Rule messages**</span></span>
  - <span data-ttu-id="939fa-245">**피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="939fa-245">**Phishing email**</span></span>

<span data-ttu-id="939fa-246">차트는 **형식** 값으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="939fa-247">**필터** 를 클릭 하거나 차트 범례에서 값을 클릭 하 여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-247">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="939fa-248">데이터 테이블에는 다음과 같은 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-248">The data table contains the following information:</span></span>

- <span data-ttu-id="939fa-249">**방향**</span><span class="sxs-lookup"><span data-stu-id="939fa-249">**Direction**</span></span>
- <span data-ttu-id="939fa-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="939fa-250">**Type**</span></span>
- <span data-ttu-id="939fa-251">**24시간**</span><span class="sxs-lookup"><span data-stu-id="939fa-251">**24 hours**</span></span>
- <span data-ttu-id="939fa-252">**3 일**</span><span class="sxs-lookup"><span data-stu-id="939fa-252">**3 days**</span></span>
- <span data-ttu-id="939fa-253">**7일**</span><span class="sxs-lookup"><span data-stu-id="939fa-253">**7 days**</span></span>
- <span data-ttu-id="939fa-254">**15일**</span><span class="sxs-lookup"><span data-stu-id="939fa-254">**15 days**</span></span>
- <span data-ttu-id="939fa-255">**30일**</span><span class="sxs-lookup"><span data-stu-id="939fa-255">**30 days**</span></span>

<span data-ttu-id="939fa-256">**자세한 내용을 보려면 범주 선택을**클릭 하면 다음 값 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="939fa-257">**피싱 전자 메일**:이 옵션을 선택 하면 [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="939fa-258">**전자 메일의 맬웨어**:이 옵션을 선택 하면 [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="939fa-259">**스팸 감지**:이 옵션을 선택 하면 [스팸 감지 보고서](view-email-security-reports.md#spam-detections-report)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="939fa-260">**Edge 차단 된 스팸**:이 옵션을 선택 하면 [스팸 감지 보고서](view-email-security-reports.md#spam-detections-report)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="939fa-261">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="939fa-261">**Export**:</span></span>

<span data-ttu-id="939fa-262">자세히 보기에 대해서는 1 일 동안 데이터만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="939fa-263">따라서 데이터를 7 일간 내보내려는 경우에는 7 개의 서로 다른 내보내기 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="939fa-264">내보낸 각 .csv 파일은 15만 행으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="939fa-265">해당 날짜의 데이터에 15만 개 이상의 행이 포함 되어 있는 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="939fa-266">메일 흐름 상황 보고서의 형식 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="939fa-267">메일 흐름 상태 보고서에 대 한 방향 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="939fa-268">**방향** 탭을 클릭 하면 **유형** 보기에서 같은 기본 필터가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="939fa-269">차트는 **방향** 값으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="939fa-270">**필터** 를 클릭 하거나 차트 범례에서 값을 클릭 하 여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="939fa-271">**Type** 보기에서 동일한 필터가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="939fa-272">데이터 테이블에 **유형** 보기와 동일한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="939fa-273">**자세한 내용에 대 한 자세한 내용은** **종류** 보기와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="939fa-274">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="939fa-274">**Export**:</span></span>

<span data-ttu-id="939fa-275">자세히 보기에 대해서는 1 일 동안 데이터만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="939fa-276">따라서 데이터를 7 일간 내보내려는 경우에는 7 개의 서로 다른 내보내기 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="939fa-277">내보낸 각 .csv 파일은 15만 행으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="939fa-278">해당 날짜의 데이터에 15만 개 이상의 행이 포함 되어 있는 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="939fa-279">메일 흐름 상황 보고서의 방향 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="939fa-280">보내고 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="939fa-280">Sent and received email report</span></span>

<span data-ttu-id="939fa-281">**Sent and received email** 보고서는 스팸 감지, 맬웨어 및 "양호"로 식별 된 전자 메일을 포함 하 여 수신 및 발신 전자 메일에 대 한 정보를 표시 하는 스마트 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-281">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="939fa-282">이 보고서와 [메일 흐름 status 보고서](#mailflow-status-report) 의 차이점은 다음과 같습니다 .이 보고서에는 edge 보호에 의해 차단 된 메시지에 대 한 데이터가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-282">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="939fa-283">보고서의 집계 보기 및 자세히 보기를 사용 하면 90 일의 필터링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-283">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="939fa-284">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **보내고 받은 전자 메일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-284">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="939fa-285">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="939fa-285">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![보고서 대시보드의 보낸 날짜 및 받은 전자 메일 위젯](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="939fa-287">보내고 받은 전자 메일 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-287">Report view for the Sent and received email report</span></span>

<span data-ttu-id="939fa-288">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-288">The following charts are available in the report view:</span></span>

- <span data-ttu-id="939fa-289">**아래로 나누기: Type**: 다음은 사용 가능한 모든 종류를 표시 하는 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-289">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="939fa-290">**합계**</span><span class="sxs-lookup"><span data-stu-id="939fa-290">**Total**</span></span>
  - <span data-ttu-id="939fa-291">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="939fa-291">**Good mail**</span></span>
  - <span data-ttu-id="939fa-292">**맬웨어 (맬웨어 방지)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="939fa-292">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="939fa-293">**스팸 감지**</span><span class="sxs-lookup"><span data-stu-id="939fa-293">**Spam detections**</span></span>
  - <span data-ttu-id="939fa-294">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="939fa-294">**Rule messages**</span></span>
  - <span data-ttu-id="939fa-295">**고급 맬웨어** (OFFICE 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="939fa-295">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="939fa-296">차트에서 날짜 (데이터 요소)를 가리키면 해당 날짜에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-296">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보낸 편지함 및 받은 전자 메일 보고서에 보기 입력](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="939fa-298">**나누기: 방향**: **합계**, **인바운드**및 **아웃 바운드** 데이터를 표시 하는 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-298">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="939fa-299">차트에서 날짜 (데이터 요소)를 가리키면 해당 날짜에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-299">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보내고 받은 전자 메일 보고서의 방향 보기](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="939fa-301">**드릴 다운 기준** \> **맬웨어 (맬웨어 방지)**:이 옵션을 선택 하면 [전자 메일 보고서에서 맬웨어가 탐지](view-email-security-reports.md#malware-detections-in-email-report)됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-301">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="939fa-302">**드릴 다운 기준** \> **스팸 검색)**:이 옵션을 선택 하면 [스팸 감지 보고서](view-email-security-reports.md#spam-detections-report)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-302">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="939fa-303">보고서 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-303">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="939fa-304">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939fa-304">**Start date** and **End date**</span></span>
- <span data-ttu-id="939fa-305">방향 값</span><span class="sxs-lookup"><span data-stu-id="939fa-305">Direction values</span></span>
- <span data-ttu-id="939fa-306">형식 값</span><span class="sxs-lookup"><span data-stu-id="939fa-306">Type values</span></span>

<span data-ttu-id="939fa-307">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-307">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="939fa-308">보내고 받은 전자 메일 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-308">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="939fa-309">**아래로 나누기: 방향** 보기 또는 **아래로 나누기 기준: 방향** 보기로 **자세히 표 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-309">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="939fa-310">**날짜 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="939fa-310">**Date (UTC)**</span></span>
- <span data-ttu-id="939fa-311">**Type**</span><span class="sxs-lookup"><span data-stu-id="939fa-311">**Type**</span></span>
- <span data-ttu-id="939fa-312">**방향**</span><span class="sxs-lookup"><span data-stu-id="939fa-312">**Direction**</span></span>
- <span data-ttu-id="939fa-313">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="939fa-313">**Message count**</span></span>

<span data-ttu-id="939fa-314">세부 정보 표 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-314">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="939fa-315">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939fa-315">**Start date** and **End date**</span></span>
- <span data-ttu-id="939fa-316">방향 값</span><span class="sxs-lookup"><span data-stu-id="939fa-316">Direction values</span></span>
- <span data-ttu-id="939fa-317">형식 값</span><span class="sxs-lookup"><span data-stu-id="939fa-317">Type values</span></span>

<span data-ttu-id="939fa-318">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-318">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="939fa-319">상위 보낸 사람 및 받는 사람 보고서</span><span class="sxs-lookup"><span data-stu-id="939fa-319">Top senders and recipients report</span></span>

<span data-ttu-id="939fa-320">**상위 보낸 사람 및 받는 사람** 보고서는 상위 전자 메일 보낸 사람 및 받는 사람을 표시 하는 원형 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-320">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="939fa-321">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **상위 보낸 사람 및 받는 사람**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-321">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="939fa-322">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="939fa-322">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![보고서 대시보드의 상위 보낸 사람 및 받는 사람 위젯](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="939fa-324">상위 보낸 사람 및 받는 사람 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-324">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="939fa-325">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-325">The following charts are available in the report view:</span></span>

- <span data-ttu-id="939fa-326">**상위 메일 보낸 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="939fa-326">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="939fa-327">**상위 메일 받는 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="939fa-327">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="939fa-328">**주요 스팸 받는 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="939fa-328">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="939fa-329">**데이터 \> 표시 상위 맬웨어 받는 사람** (EOP)</span><span class="sxs-lookup"><span data-stu-id="939fa-329">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="939fa-330">**데이터 \> 표시 최상위 맬웨어 받는 사람 (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="939fa-330">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="939fa-331">원형 차트의 컴포지션은 이러한 선택에 따라 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-331">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="939fa-332">원형 차트의 쐐기형 위에 마우스를 올리면 보내거나 받은 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-332">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="939fa-333">보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-333">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![상위 보낸 사람 및 받는 사람 보고서의 보고서 보기에 있는 원형 차트](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="939fa-335">상위 보낸 사람 및 받는 사람 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-335">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="939fa-336">**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-336">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="939fa-337">**상위 메일 보낸 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="939fa-337">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="939fa-338">**상위 메일 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="939fa-338">**Top mail senders**</span></span>
  - <span data-ttu-id="939fa-339">**개수**</span><span class="sxs-lookup"><span data-stu-id="939fa-339">**Count**</span></span>

- <span data-ttu-id="939fa-340">**상위 메일 받는 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="939fa-340">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="939fa-341">**주요 메일 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="939fa-341">**Top mail recipients**</span></span>
  - <span data-ttu-id="939fa-342">**개수**</span><span class="sxs-lookup"><span data-stu-id="939fa-342">**Count**</span></span>

- <span data-ttu-id="939fa-343">**주요 스팸 받는 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="939fa-343">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="939fa-344">**주요 스팸 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="939fa-344">**Top spam recipients**</span></span>
  - <span data-ttu-id="939fa-345">**개수**</span><span class="sxs-lookup"><span data-stu-id="939fa-345">**Count**</span></span>

- <span data-ttu-id="939fa-346">**데이터 \> 표시 상위 맬웨어 받는 사람** (EOP)</span><span class="sxs-lookup"><span data-stu-id="939fa-346">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="939fa-347">**주요 맬웨어 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="939fa-347">**Top malware recipients**</span></span>
  - <span data-ttu-id="939fa-348">**개수**</span><span class="sxs-lookup"><span data-stu-id="939fa-348">**Count**</span></span>

- <span data-ttu-id="939fa-349">**데이터 \> 표시 최상위 맬웨어 받는 사람 (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="939fa-349">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="939fa-350">**주요 ATP (맬웨어 수신자)**</span><span class="sxs-lookup"><span data-stu-id="939fa-350">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="939fa-351">**개수**</span><span class="sxs-lookup"><span data-stu-id="939fa-351">**Count**</span></span>

<span data-ttu-id="939fa-352">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-352">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="939fa-353">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-353">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="939fa-354">이러한 보고서를 표시 하는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="939fa-354">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="939fa-355">보고서를 보고 사용 하려면 보안 & 준수 센터 **및** Exchange Online에서 지정 된 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-355">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="939fa-356">보안 & 준수 센터에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-356">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="939fa-357">-조직 관리-보안 관리자 ( [Azure Active Directory 관리 센터](https://aad.portal.azure.com) 에서이 작업을 수행할 수도 있음)-보안 독자</span><span class="sxs-lookup"><span data-stu-id="939fa-357">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="939fa-358">자세한 내용은 [보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="939fa-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="939fa-359">Exchange Online에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="939fa-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="939fa-360">-조직 관리-보기 전용 조직 관리-보기 전용 받는 사람-준수 관리</span><span class="sxs-lookup"><span data-stu-id="939fa-360">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="939fa-361">자세한 내용은 exchange online의 [사용 권한](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 및 [exchange online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939fa-361">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="939fa-362">관련 항목</span><span class="sxs-lookup"><span data-stu-id="939fa-362">Related topics</span></span>

[<span data-ttu-id="939fa-363">보안 및 준수 센터의 스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="939fa-363">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="939fa-364">보안 및 준수 센터의 메일 흐름 파악</span><span class="sxs-lookup"><span data-stu-id="939fa-364">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="939fa-365">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-365">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="939fa-366">Office 365 Advanced Threat Protection에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939fa-366">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
