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
description: 관리자는 보안 & 준수 센터의 보고서 대시보드에서 사용할 수 있는 메일 흐름 보고서에 대해 알아볼 수 있습니다.
ms.custom: ''
ms.openlocfilehash: 807166ea0c6ea8a26716bc7017387499382c9e7e
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131336"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="dfb73-103">보안 & 준수 센터의 보고서 대시보드에서 메일 흐름 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dfb73-104">보안 & 준수 센터의 [메일 흐름 대시보드에서](mail-flow-insights-v2.md) 사용할 수 있는 메일 흐름 보고서 외에도, Microsoft 365 조직을 모니터링 하는 데 도움이 되도록 보고서 대시보드에서 다양 한 추가 메일 흐름 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="dfb73-105">[필요한 권한이](#what-permissions-are-needed-to-view-these-reports)있는 경우 **보고서** 대시보드로 이동 하 여 [보안 & 준수 센터](https://office.protection.com) 에서 이러한 보고서를 볼 수 있습니다 \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="dfb73-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="dfb73-106">보고서 대시보드로 직접 이동 하려면를 엽니다 <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="dfb73-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![보안 & 준수 센터의 보고서 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="dfb73-108">커넥터 보고서</span><span class="sxs-lookup"><span data-stu-id="dfb73-108">Connector report</span></span>

<span data-ttu-id="dfb73-109">**커넥터 보고서** 에는 조직에 대해 구성 된 [인바운드 및 아웃 바운드 커넥터](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 에 대 한 메일 흐름 활동이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="dfb73-110">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **커넥터 보고서** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="dfb73-111">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="dfb73-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![보고서 대시보드의 커넥터 보고서 위젯](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="dfb73-113">커넥터 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-113">Report view for the Connector report</span></span>

<span data-ttu-id="dfb73-114">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="dfb73-115">**데이터 보기 기준: 메일 흐름**:이 차트에서는 다음을 기준으로 구성한 인바운드 및 아웃 바운드 메시지의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="dfb73-116">**합계**</span><span class="sxs-lookup"><span data-stu-id="dfb73-116">**Total**</span></span>
  - <span data-ttu-id="dfb73-117">**커넥터 없이 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="dfb73-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="dfb73-118">**커넥터 없이 인터넷에 연결**</span><span class="sxs-lookup"><span data-stu-id="dfb73-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="dfb73-119">구성한 특정 커넥터</span><span class="sxs-lookup"><span data-stu-id="dfb73-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="dfb73-120">차트에서 데이터를 격리 하려면 다음 **에 대 한 데이터 표시** 컨트롤을 사용 하 여 이러한 옵션 중 하나 또는 **모든 메일 흐름** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![커넥터 보고서에서 메일 흐름을 기준으로 데이터 보기](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="dfb73-122">**데이터 보기 기준: tls 사용량**:이 차트에서는 메일 흐름에 대 한 Tls (전송 계층 보안) 버전 사용 비율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="dfb73-123">차트에서 데이터를 격리 하려면 다음 **에 대 한 데이터 표시** 컨트롤을 사용 하 여 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="dfb73-124">**모든 메일 흐름**</span><span class="sxs-lookup"><span data-stu-id="dfb73-124">**All mail flow**</span></span>
  - <span data-ttu-id="dfb73-125">**커넥터 없이 인터넷에서**</span><span class="sxs-lookup"><span data-stu-id="dfb73-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="dfb73-126">**커넥터 없이 인터넷에 연결**</span><span class="sxs-lookup"><span data-stu-id="dfb73-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="dfb73-127">구성한 특정 커넥터</span><span class="sxs-lookup"><span data-stu-id="dfb73-127">A specific connector that you've configured.</span></span>

  ![커넥터 보고서에서 TLS 사용을 기준으로 데이터 보기](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="dfb73-129">보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="dfb73-130">커넥터 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-130">Details table view for the Connector report</span></span>

<span data-ttu-id="dfb73-131">보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="dfb73-132">**날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-132">**Date**</span></span>
- <span data-ttu-id="dfb73-133">**커넥터 방향 및 이름**</span><span class="sxs-lookup"><span data-stu-id="dfb73-133">**Connector direction and name**</span></span>
- <span data-ttu-id="dfb73-134">**커넥터 유형**</span><span class="sxs-lookup"><span data-stu-id="dfb73-134">**Connector type**</span></span>
- <span data-ttu-id="dfb73-135">**강제 TLS?**: **True** 또는 **False** 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="dfb73-136">**TLS 없음** (백분율)</span><span class="sxs-lookup"><span data-stu-id="dfb73-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="dfb73-137">**TLS 1.0** (백분율)</span><span class="sxs-lookup"><span data-stu-id="dfb73-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="dfb73-138">**TLS 1.1** (백분율)</span><span class="sxs-lookup"><span data-stu-id="dfb73-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="dfb73-139">**TLS 1.2** (백분율)</span><span class="sxs-lookup"><span data-stu-id="dfb73-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="dfb73-140">**볼륨**: 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="dfb73-141">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dfb73-142">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="dfb73-143">Exchange 전송 규칙 보고서</span><span class="sxs-lookup"><span data-stu-id="dfb73-143">Exchange transport rule report</span></span>

<span data-ttu-id="dfb73-144">**Exchange 전송 규칙 보고서** 는 조직에서 들어오고 나가는 메시지에 대 한 메일 흐름 규칙 (전송 규칙이 라고도 함)의 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="dfb73-145">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **Exchange 전송 규칙** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="dfb73-146">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="dfb73-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![보고서 대시보드의 Exchange 전송 규칙 위젯](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="dfb73-148">Exchange 전송 규칙 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="dfb73-149">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="dfb73-150">**데이터 보기 기준: Exchange 전송 규칙** \> **아래로 나누기: 방향**:이 차트에서는 전송 규칙의 영향을 받는 **인바운드** 및 **아웃 바운드** 메시지의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="dfb73-151">**데이터 보기 기준: Exchange 전송 규칙** \> **아래로 나누기: 심각도**:이 차트에는 **높은 심각도** 및 **보통 심각도** 및 **심각도가 낮은** 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="dfb73-152">심각도 수준을 규칙의 작업으로 설정 합니다 (심각도 수준이 나 _Setauditseverity_**으로이 규칙 감사** ).</span><span class="sxs-lookup"><span data-stu-id="dfb73-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="dfb73-153">자세한 내용은 [Mail flow rule actions In Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dfb73-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="dfb73-154">**데이터 보기 기준: DLP Exchange 전송 규칙** \> **아래로 나누기: 방향**:이 차트에서는 DLP (데이터 손실 방지) 전송 규칙의 영향을 받는 **인바운드** 및 **아웃 바운드** 메시지의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="dfb73-155">다음 옵션을 선택 하 여 차트를 보다 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="dfb73-156">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="dfb73-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="dfb73-157">**데이터 표시: 손상 된 사용자**</span><span class="sxs-lookup"><span data-stu-id="dfb73-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="dfb73-158">**데이터 표시: 검색 된 콘텐츠가 부족 함 미국 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="dfb73-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="dfb73-159">**데이터 보기 기준: DLP Exchange 전송 규칙** \> **아래로 나누기: 방향**:이 보기에는 DLP 전송 규칙의 영향을 받은 **높은 심각도** 및 **중간** 심각도 메시지와 **낮은 심각도** 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="dfb73-160">다음 옵션을 선택 하 여 차트를 보다 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="dfb73-161">**데이터 표시: 모든 DLP 전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="dfb73-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="dfb73-162">**데이터 표시: 손상 된 사용자**</span><span class="sxs-lookup"><span data-stu-id="dfb73-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="dfb73-163">**데이터 표시: 검색 된 콘텐츠가 부족 함 미국 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="dfb73-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="dfb73-164">보고서 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="dfb73-165">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="dfb73-166">방향 값</span><span class="sxs-lookup"><span data-stu-id="dfb73-166">Direction values</span></span>
- <span data-ttu-id="dfb73-167">심각도 값</span><span class="sxs-lookup"><span data-stu-id="dfb73-167">Severity values</span></span>

![Exchange 전송 규칙 보고서의 보고서 보기](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="dfb73-169">Exchange 전송 규칙 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="dfb73-170">**세부 정보 표 보기** 를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="dfb73-171">**데이터 보기 기준: Exchange 전송 규칙**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="dfb73-172">**날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-172">**Date**</span></span>
  - <span data-ttu-id="dfb73-173">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="dfb73-173">**Transport rule**</span></span>
  - <span data-ttu-id="dfb73-174">**제목**</span><span class="sxs-lookup"><span data-stu-id="dfb73-174">**Subject**</span></span>
  - <span data-ttu-id="dfb73-175">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="dfb73-175">**Sender address**</span></span>
  - <span data-ttu-id="dfb73-176">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="dfb73-176">**Recipient address**</span></span>
  - <span data-ttu-id="dfb73-177">**심각도**</span><span class="sxs-lookup"><span data-stu-id="dfb73-177">**Severity**</span></span>
  - <span data-ttu-id="dfb73-178">**방향**</span><span class="sxs-lookup"><span data-stu-id="dfb73-178">**Direction**</span></span>

- <span data-ttu-id="dfb73-179">**데이터 보기 기준: DLP Exchange 전송 규칙**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="dfb73-180">**날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-180">**Date**</span></span>
  - <span data-ttu-id="dfb73-181">**DLP 정책**</span><span class="sxs-lookup"><span data-stu-id="dfb73-181">**DLP policy**</span></span>
  - <span data-ttu-id="dfb73-182">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="dfb73-182">**Transport rule**</span></span>
  - <span data-ttu-id="dfb73-183">**제목**</span><span class="sxs-lookup"><span data-stu-id="dfb73-183">**Subject**</span></span>
  - <span data-ttu-id="dfb73-184">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="dfb73-184">**Sender address**</span></span>
  - <span data-ttu-id="dfb73-185">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="dfb73-185">**Recipient address**</span></span>
  - <span data-ttu-id="dfb73-186">**심각도**</span><span class="sxs-lookup"><span data-stu-id="dfb73-186">**Severity**</span></span>
  - <span data-ttu-id="dfb73-187">**방향**</span><span class="sxs-lookup"><span data-stu-id="dfb73-187">**Direction**</span></span>

<span data-ttu-id="dfb73-188">세부 정보 표 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="dfb73-189">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="dfb73-190">방향 값</span><span class="sxs-lookup"><span data-stu-id="dfb73-190">Direction values</span></span>
- <span data-ttu-id="dfb73-191">심각도 값</span><span class="sxs-lookup"><span data-stu-id="dfb73-191">Severity values</span></span>

<span data-ttu-id="dfb73-192">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="dfb73-193">전달 보고서</span><span class="sxs-lookup"><span data-stu-id="dfb73-193">Forwarding report</span></span>

<span data-ttu-id="dfb73-194">**전달 보고서** 에는 조직의 자동으로 전달 되는 메시지가 Exchange Online 사서함의 외부 도메인으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="dfb73-195">전달 된 메시지는 보안 또는 준수 위험을 초래할 수 있으며 계정이 손상 된 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="dfb73-196">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **전달 보고서** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="dfb73-197">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="dfb73-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![보고서 대시보드에서 보고서 위젯 전달](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="dfb73-199">전달 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="dfb73-200">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="dfb73-201">**데이터 표시: 전달 메서드**: 다음과 같은 메서드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="dfb73-202">**전송 규칙**: [메일 흐름 규칙이](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="dfb73-203">**사서함 규칙**: [받은 편지함 규칙이](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![전달 보고서의 전달 메서드 보기](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="dfb73-205">**다음에 대 한 데이터 표시: 전달 도메인**:이 보기에는 전달 대상이 되는 받는 사람 도메인이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![전달 보고서의 전달 도메인 보기](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="dfb73-207">**데이터 표시: 전달자**: 다음 전달자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="dfb73-208">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="dfb73-208">**Transport rule**</span></span>
  - <span data-ttu-id="dfb73-209">전달 받은 편지함 규칙을 포함 하는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![전달 보고서의 전달자 보기](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="dfb73-211">보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="dfb73-212">전달 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="dfb73-213">보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="dfb73-214">**전달자**: 값 **전송 규칙** 또는 전달 받은 편지함 규칙을 포함 하는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="dfb73-215">**전달 유형**: 값 **사서함 규칙** 또는 **전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="dfb73-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="dfb73-216">**받는 사람 이름**</span><span class="sxs-lookup"><span data-stu-id="dfb73-216">**Recipient name**</span></span>
- <span data-ttu-id="dfb73-217">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="dfb73-217">**Recipient domain**</span></span>
- <span data-ttu-id="dfb73-218">**Details**: 메일 흐름 규칙의 GUID 값 또는 받은 편지함 규칙의 RuleIdentity 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="dfb73-219">**개수**</span><span class="sxs-lookup"><span data-stu-id="dfb73-219">**Count**</span></span>
- <span data-ttu-id="dfb73-220">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-220">**First forward date**</span></span>

<span data-ttu-id="dfb73-221">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dfb73-222">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="dfb73-223">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="dfb73-223">Mailflow status report</span></span>

<span data-ttu-id="dfb73-224">**메일 흐름 status 보고서** 는 edge에서 허용 되거나 차단 되는 전자 메일에 대 한 추가 정보가 포함 된 [보낸 날짜 및 받은 전자 메일 보고서](#sent-and-received-email-report)와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="dfb73-225">이 보고서는 edge 보호 정보를 포함 하며, EOP (Exchange Online Protection)에서 평가를 위해 서비스에 허용 되기 전에 차단 되는 전자 메일의 양을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="dfb73-226">메시지가 5 명의 받는 사람에 게 전송 되는 경우 메시지가 한 명의 메시지와 다르게 계산 된다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="dfb73-227">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **메일 흐름 status report** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="dfb73-228">**메일 흐름 상태 보고서** 로 바로 이동 하려면을 엽니다 <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="dfb73-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![보고서 대시보드의 메일 흐름 상태 보고서 위젯](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="dfb73-230">메일 흐름 상황 보고서의 형식 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="dfb73-231">보고서를 열 때 **형식** 탭이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="dfb73-232">기본적으로이 보기에는 다음 필터를 사용 하 여 구성 된 차트 및 데이터 테이블이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="dfb73-233">**날짜**: 지난 7 일</span><span class="sxs-lookup"><span data-stu-id="dfb73-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="dfb73-234">**방향**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-234">**Direction**:</span></span>

  - <span data-ttu-id="dfb73-235">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="dfb73-235">**Inbound**</span></span>
  - <span data-ttu-id="dfb73-236">**아웃 바운드**</span><span class="sxs-lookup"><span data-stu-id="dfb73-236">**Outbound**</span></span>
  - <span data-ttu-id="dfb73-237">**조직 내**:이 수는 테 넌 트 내의 메시지에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="dfb73-238">보낸 사람 abc@domain.com이 받는 사람 xyz@domain.com에 게 전송 합니다 ( **인바운드** 및 **아웃 바운드** 와 별도로 계산 됨).</span><span class="sxs-lookup"><span data-stu-id="dfb73-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="dfb73-239">다음을 **입력** 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-239">**Type**:</span></span>

  - <span data-ttu-id="dfb73-240">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-240">**Good mail**</span></span>
  - <span data-ttu-id="dfb73-241">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="dfb73-241">**Malware**</span></span>
  - <span data-ttu-id="dfb73-242">**스팸**</span><span class="sxs-lookup"><span data-stu-id="dfb73-242">**Spam**</span></span>
  - <span data-ttu-id="dfb73-243">**에 지 보호**</span><span class="sxs-lookup"><span data-stu-id="dfb73-243">**Edge protection**</span></span>
  - <span data-ttu-id="dfb73-244">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="dfb73-244">**Rule messages**</span></span>
  - <span data-ttu-id="dfb73-245">**피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-245">**Phishing email**</span></span>

<span data-ttu-id="dfb73-246">차트는 **형식** 값으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="dfb73-247">**필터** 를 클릭 하거나 차트 범례에서 값을 클릭 하 여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="dfb73-248">데이터 테이블에는 다음과 같은 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-248">The data table contains the following information:</span></span>

- <span data-ttu-id="dfb73-249">**방향**</span><span class="sxs-lookup"><span data-stu-id="dfb73-249">**Direction**</span></span>
- <span data-ttu-id="dfb73-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="dfb73-250">**Type**</span></span>
- <span data-ttu-id="dfb73-251">**24시간**</span><span class="sxs-lookup"><span data-stu-id="dfb73-251">**24 hours**</span></span>
- <span data-ttu-id="dfb73-252">**3 일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-252">**3 days**</span></span>
- <span data-ttu-id="dfb73-253">**7일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-253">**7 days**</span></span>
- <span data-ttu-id="dfb73-254">**15일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-254">**15 days**</span></span>
- <span data-ttu-id="dfb73-255">**30일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-255">**30 days**</span></span>

<span data-ttu-id="dfb73-256">**자세한 내용을 보려면 범주 선택을** 클릭 하면 다음 값 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="dfb73-257">**피싱 전자 메일**:이 옵션을 선택 하면 [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="dfb73-258">**전자 메일의 맬웨어**:이 옵션을 선택 하면 [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="dfb73-259">**스팸 감지**:이 옵션을 선택 하면 [스팸 감지 보고서](view-email-security-reports.md#spam-detections-report)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="dfb73-260">**Edge 차단 된 스팸**:이 옵션을 선택 하면 [스팸 감지 보고서](view-email-security-reports.md#spam-detections-report)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="dfb73-261">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-261">**Export**:</span></span>

<span data-ttu-id="dfb73-262">자세히 보기에 대해서는 1 일 동안 데이터만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="dfb73-263">따라서 데이터를 7 일간 내보내려는 경우에는 7 개의 서로 다른 내보내기 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="dfb73-264">내보낸 각 .csv 파일은 15만 행으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="dfb73-265">해당 날짜의 데이터에 15만 개 이상의 행이 포함 되어 있는 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="dfb73-266">메일 흐름 상황 보고서의 형식 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="dfb73-267">메일 흐름 상태 보고서에 대 한 방향 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="dfb73-268">**방향** 탭을 클릭 하면 **유형** 보기에서 같은 기본 필터가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="dfb73-269">차트는 **방향** 값으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="dfb73-270">**필터** 를 클릭 하거나 차트 범례에서 값을 클릭 하 여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="dfb73-271">**Type** 보기에서 동일한 필터가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="dfb73-272">데이터 테이블에 **유형** 보기와 동일한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="dfb73-273">**자세한 내용에 대 한 자세한 내용은** **종류** 보기와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="dfb73-274">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-274">**Export**:</span></span>

<span data-ttu-id="dfb73-275">자세히 보기에 대해서는 1 일 동안 데이터만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="dfb73-276">따라서 데이터를 7 일간 내보내려는 경우에는 7 개의 서로 다른 내보내기 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="dfb73-277">내보낸 각 .csv 파일은 15만 행으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="dfb73-278">해당 날짜의 데이터에 15만 개 이상의 행이 포함 되어 있는 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="dfb73-279">메일 흐름 상황 보고서의 방향 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="dfb73-280">메일 흐름 상태 보고서에 대 한 깔때기 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="dfb73-281">**깔때기형** 보기는 Microsoft의 전자 메일 위협 보호 기능이 조직에서 들어오고 나가는 전자 메일을 필터링 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="dfb73-282">또한 전체 전자 메일 수에 대 한 세부 정보를 제공 하 고 edge 보호, 맬웨어 방지, 피싱 방지, 스팸 방지 및 스푸핑 방지를 포함 하 여이 수에 영향을 주는 구성 된 위협 방지 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="dfb73-283">기본적으로 **깔때기** 탭을 클릭 하면 다음 필터를 사용 하 여 구성 된 차트 및 데이터 테이블이 보기에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="dfb73-284">**날짜**: 지난 7 일</span><span class="sxs-lookup"><span data-stu-id="dfb73-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="dfb73-285">**방향**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-285">**Direction**:</span></span>

  - <span data-ttu-id="dfb73-286">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="dfb73-286">**Inbound**</span></span>
  - <span data-ttu-id="dfb73-287">**아웃 바운드**</span><span class="sxs-lookup"><span data-stu-id="dfb73-287">**Outbound**</span></span>
  - <span data-ttu-id="dfb73-288">**조직 내**:이 수는 테 넌 트 내에서 전송 되는 메시지에 대 한 것입니다. 즉, 보낸 사람 abc@domain.com는 받는 사람 xyz@domain.com에 게 전송 합니다 (인바운드 및 아웃 바운드와 별개로 계산 됨).</span><span class="sxs-lookup"><span data-stu-id="dfb73-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="dfb73-289">집계 보기 및 데이터 테이블 보기는 90 일의 필터링을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="dfb73-290">**필터** 를 클릭 하면 차트와 데이터 테이블을 모두 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="dfb73-291">이 차트에는 다음으로 구성 된 전자 메일 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="dfb73-292">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-292">**Total email**</span></span>
- <span data-ttu-id="dfb73-293">**Edge 보호 후의 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-293">**Email after edge protection**</span></span>
- <span data-ttu-id="dfb73-294">**맬웨어 방지, 파일 신뢰도, 파일 형식 블록 후의 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="dfb73-295">**피싱, URL 신뢰도, 브랜드 가장을 사용한 후의 전자 메일-스푸핑 방지**</span><span class="sxs-lookup"><span data-stu-id="dfb73-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="dfb73-296">**스팸 방지, 대량 메일 필터링 후의 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="dfb73-297">**사용자 및 도메인 가장 1 다음의 전자 메일**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dfb73-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="dfb73-298">**파일 및 URL 샌드 박싱 1 다음에 전자 메일 보내기**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dfb73-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="dfb73-299">**배달 후 보호를 수행한 후 전자 메일이 심각 하지 않음으로 감지 됨 (URL 클릭 시간 보호)**</span><span class="sxs-lookup"><span data-stu-id="dfb73-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="dfb73-300"><sup>1</sup> Defender for Office 365 전용</span><span class="sxs-lookup"><span data-stu-id="dfb73-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="dfb73-301">EOP 또는 Office 365 용 Defender에서 필터링 한 전자 메일을 별도로 보려면 차트 범례의 값을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="dfb73-302">데이터 테이블에는 다음과 같은 정보가 내림차순으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="dfb73-303">**날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-303">**Date**</span></span>
- <span data-ttu-id="dfb73-304">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-304">**Total email**</span></span>
- <span data-ttu-id="dfb73-305">**에 지 보호**</span><span class="sxs-lookup"><span data-stu-id="dfb73-305">**Edge protection**</span></span>
- <span data-ttu-id="dfb73-306">**맬웨어 방지, 파일 신뢰도, 파일 형식 블록**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="dfb73-307">**파일 신뢰도**: 다른 Microsoft 고객이 첨부 한 파일의 식별으로 인해 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="dfb73-308">**파일 형식 블록**: 메시지에서 식별 된 악의적인 파일의 유형으로 인해 필터가 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="dfb73-309">**앤티 피싱, URL 신뢰도, 브랜드 가장, 스푸핑 방지**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="dfb73-310">**Url 신뢰도**: 다른 Microsoft 고객의 url 식별으로 인해 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="dfb73-311">**브랜드 가장**: 보낸 사람이 가장 잘 알려진 브랜드에서 오는 메시지로 인해 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="dfb73-312">**스푸핑 방지**: 받는 사람이 속한 도메인을 스푸핑 하는 메시지 또는 메시지 보낸 사람이 소유 하지 않은 도메인을 스푸핑할 때 메시지가 필터링 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="dfb73-313">**스팸 방지, 대량 메일 필터링**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="dfb73-314">**대량 메일 필터링**: 받는 사람에 게 대량 메일을 배달 하는 시도로 인해 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="dfb73-315">**사용자 및 도메인 가장 (Defender For Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="dfb73-316">**사용자 가장**: 피싱 방지 정책의 가장 보호 설정에 정의 되어 있는 사용자 (메시지 보낸 사람)를 가장 하는 시도로 인해 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="dfb73-317">**도메인 가장**: 피싱 방지 정책의 가장 보호 설정에서 정의한 도메인을 가장 하는 시도로 인해 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="dfb73-318">**파일 및 URL 샌드 박싱 (Defender For Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="dfb73-319">**파일 샌드 박싱**: 안전한 첨부 파일 정책에 따라 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="dfb73-320">**URL 샌드 박싱**: 안전한 링크 정책에 따라 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="dfb73-321">**전송 이후 ATP (보호 및 zap) 또는 zap (EOP)**: zap은 0 시간 자동 제거를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="dfb73-322">데이터 테이블에서 행을 선택 하면 전자 메일 개수에 대 한 자세한 분석 내용이 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="dfb73-323">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-323">**Export**:</span></span>

<span data-ttu-id="dfb73-324">**옵션** 에서 **내보내기를** 클릭 한 후에는 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="dfb73-325">**요약 (가장 최근 90 일 동안의 데이터 포함)**</span><span class="sxs-lookup"><span data-stu-id="dfb73-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="dfb73-326">**세부 정보 (최대 30 일 동안의 데이터 포함)**</span><span class="sxs-lookup"><span data-stu-id="dfb73-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="dfb73-327">**날짜** 에서 범위를 선택 하 고 **적용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="dfb73-328">현재 필터의 데이터를 .csv 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="dfb73-329">내보낸 각 .csv 파일은 15만 행으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="dfb73-330">데이터에 포함 된 행이 15만 개 보다 많은 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="dfb73-331">메일 흐름 상황 보고서의 깔때기 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="dfb73-332">메일 흐름 상태 보고서에 대 한 기술 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="dfb73-333">**기술 보기** 는 **깔때기형** 보기와 비슷하며 구성 된 위협 보호 기능에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="dfb73-334">차트에서 메시지가 위협 방지의 각 단계에서 분류 되는 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="dfb73-335">**기술 보기** 탭을 클릭 하면 기본적으로이 보기에 다음 필터를 사용 하 여 구성 된 차트 및 데이터 테이블이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="dfb73-336">**날짜**: 지난 7 일</span><span class="sxs-lookup"><span data-stu-id="dfb73-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="dfb73-337">**방향**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-337">**Direction**:</span></span>

  - <span data-ttu-id="dfb73-338">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="dfb73-338">**Inbound**</span></span>
  - <span data-ttu-id="dfb73-339">**아웃 바운드**</span><span class="sxs-lookup"><span data-stu-id="dfb73-339">**Outbound**</span></span>
  - <span data-ttu-id="dfb73-340">**조직 내**:이 수는 테 넌 트 내의 메시지에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="dfb73-341">보낸 사람 abc@domain.com이 받는 사람 xyz@domain.com에 게 전송 합니다 (인바운드 및 아웃 바운드와 별도로 계산 됨).</span><span class="sxs-lookup"><span data-stu-id="dfb73-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="dfb73-342">집계 보기 및 데이터 테이블 보기는 90 일의 필터링을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="dfb73-343">**필터** 를 클릭 하면 차트와 데이터 테이블을 모두 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="dfb73-344">이 차트에서는 다음 범주로 구성 된 메시지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="dfb73-345">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-345">**Total email**</span></span>
- <span data-ttu-id="dfb73-346">에 **지 허용** 및에 **지 필터링**</span><span class="sxs-lookup"><span data-stu-id="dfb73-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="dfb73-347">**맬웨어**, **안전한 첨부 파일 감지** <sup>\*</sup> , **맬웨어 방지 엔진 감지** 및 **규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="dfb73-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="dfb73-348">**피싱**, **DMARC 오류**, **가장 감지**, **스푸핑 감지** 및 **피싱 검색**</span><span class="sxs-lookup"><span data-stu-id="dfb73-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="dfb73-349">URL 샌드 박싱 및 **url 샌드 박싱 검색** **을 사용 하 여 검색 되지 않음**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfb73-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="dfb73-350">**스팸** 및 **스팸** 아님</span><span class="sxs-lookup"><span data-stu-id="dfb73-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="dfb73-351">**악의적이 지 않은 전자 메일**, **안전한 링크 검색** <sup>\*</sup> 및 **ZAP**</span><span class="sxs-lookup"><span data-stu-id="dfb73-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="dfb73-352"><sup>\*</sup> Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="dfb73-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="dfb73-353">차트의 범주 위에 마우스를 올리면 해당 범주의 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="dfb73-354">데이터 테이블에는 다음과 같은 정보가 내림차순으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="dfb73-355">**날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-355">**Date**</span></span>
- <span data-ttu-id="dfb73-356">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-356">**Total email**</span></span>
- <span data-ttu-id="dfb73-357">**에 지 필터링 됨**</span><span class="sxs-lookup"><span data-stu-id="dfb73-357">**Edge filtered**</span></span>
- <span data-ttu-id="dfb73-358">**맬웨어 방지 엔진, 안전한 첨부 파일, 규칙 필터링** 됨:</span><span class="sxs-lookup"><span data-stu-id="dfb73-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="dfb73-359">**규칙 필터링** 됨: 메일 흐름 규칙 (전송 규칙이 라고도 함)으로 인해 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="dfb73-360">**DMARC, 가장, 스푸핑, 피싱 필터링** 됨:</span><span class="sxs-lookup"><span data-stu-id="dfb73-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="dfb73-361">**DMARC**: 해당 DMARC 인증 확인을 실패 한 메시지로 인해 필터링 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="dfb73-362">**URL 샌드 박싱 검색**</span><span class="sxs-lookup"><span data-stu-id="dfb73-362">**URL detonation detection**</span></span>
- <span data-ttu-id="dfb73-363">**스팸 방지 필터링**</span><span class="sxs-lookup"><span data-stu-id="dfb73-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="dfb73-364">**제거 된 ZAP**</span><span class="sxs-lookup"><span data-stu-id="dfb73-364">**ZAP removed**</span></span>
- <span data-ttu-id="dfb73-365">**안전한 링크를 통한 검색**</span><span class="sxs-lookup"><span data-stu-id="dfb73-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="dfb73-366">데이터 테이블에서 행을 선택 하면 전자 메일 개수에 대 한 자세한 분석 내용이 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="dfb73-367">**내보내기**:</span><span class="sxs-lookup"><span data-stu-id="dfb73-367">**Export**:</span></span>

<span data-ttu-id="dfb73-368">**내보내기** 를 클릭 하면 **옵션** 에서 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="dfb73-369">**요약 (가장 최근 90 일 동안의 데이터 포함)**</span><span class="sxs-lookup"><span data-stu-id="dfb73-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="dfb73-370">**세부 정보 (최대 30 일 동안의 데이터 포함)**</span><span class="sxs-lookup"><span data-stu-id="dfb73-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="dfb73-371">**날짜** 에서 범위를 선택 하 고 **적용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="dfb73-372">현재 필터의 데이터를 .csv 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="dfb73-373">내보낸 각 .csv 파일은 15만 행으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="dfb73-374">데이터에 포함 된 행이 15만 개 보다 많은 경우 여러 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="dfb73-375">메일 흐름 상황 보고서의 기술 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="dfb73-376">보내고 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="dfb73-376">Sent and received email report</span></span>

<span data-ttu-id="dfb73-377">**Sent and received email** 보고서는 스팸 감지, 맬웨어 및 "양호"로 식별 된 전자 메일을 포함 하 여 수신 및 발신 전자 메일에 대 한 정보를 표시 하는 스마트 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="dfb73-378">이 보고서와 [메일 흐름 status 보고서](#mailflow-status-report) 의 차이점은 다음과 같습니다 .이 보고서에는 edge 보호에 의해 차단 된 메시지에 대 한 데이터가 포함 되어 있지 않습니다. 메시지가 5 명의 받는 사람에 게 전송 되 면 메시지 하나로 계산 된다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="dfb73-379">보고서의 집계 보기 및 자세히 보기를 사용 하면 90 일의 필터링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="dfb73-380">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **보내고 받은 전자 메일** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="dfb73-381">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="dfb73-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![보고서 대시보드의 보낸 날짜 및 받은 전자 메일 위젯](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="dfb73-383">보내고 받은 전자 메일 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="dfb73-384">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="dfb73-385">**아래로 나누기: Type**: 다음은 사용 가능한 모든 종류를 표시 하는 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="dfb73-386">**합계**</span><span class="sxs-lookup"><span data-stu-id="dfb73-386">**Total**</span></span>
  - <span data-ttu-id="dfb73-387">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="dfb73-387">**Good mail**</span></span>
  - <span data-ttu-id="dfb73-388">**맬웨어 (맬웨어 방지)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="dfb73-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="dfb73-389">**스팸 감지**</span><span class="sxs-lookup"><span data-stu-id="dfb73-389">**Spam detections**</span></span>
  - <span data-ttu-id="dfb73-390">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="dfb73-390">**Rule messages**</span></span>
  - <span data-ttu-id="dfb73-391">**고급 맬웨어** (Office 365 용 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="dfb73-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="dfb73-392">차트에서 날짜 (데이터 요소)를 가리키면 해당 날짜에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보낸 편지함 및 받은 전자 메일 보고서에 보기 입력](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="dfb73-394">**나누기: 방향**: **합계**, **인바운드** 및 **아웃 바운드** 데이터를 표시 하는 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="dfb73-395">차트에서 날짜 (데이터 요소)를 가리키면 해당 날짜에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![보내고 받은 전자 메일 보고서의 방향 보기](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="dfb73-397">**드릴 다운 기준** \> **맬웨어 (맬웨어 방지)**:이 옵션을 선택 하면 [전자 메일 보고서에서 맬웨어가 탐지](view-email-security-reports.md#malware-detections-in-email-report)됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="dfb73-398">**드릴 다운 기준** \> **스팸 검색)**:이 옵션을 선택 하면 [스팸 감지 보고서](view-email-security-reports.md#spam-detections-report)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="dfb73-399">보고서 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="dfb73-400">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="dfb73-401">방향 값</span><span class="sxs-lookup"><span data-stu-id="dfb73-401">Direction values</span></span>
- <span data-ttu-id="dfb73-402">형식 값</span><span class="sxs-lookup"><span data-stu-id="dfb73-402">Type values</span></span>

<span data-ttu-id="dfb73-403">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="dfb73-404">보내고 받은 전자 메일 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="dfb73-405">**아래로 나누기: 방향** 보기 또는 **아래로 나누기 기준: 방향** 보기로 **자세히 표 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="dfb73-406">**날짜 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="dfb73-406">**Date (UTC)**</span></span>
- <span data-ttu-id="dfb73-407">**Type**</span><span class="sxs-lookup"><span data-stu-id="dfb73-407">**Type**</span></span>
- <span data-ttu-id="dfb73-408">**방향**</span><span class="sxs-lookup"><span data-stu-id="dfb73-408">**Direction**</span></span>
- <span data-ttu-id="dfb73-409">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="dfb73-409">**Message count**</span></span>

<span data-ttu-id="dfb73-410">세부 정보 표 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="dfb73-411">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="dfb73-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="dfb73-412">방향 값</span><span class="sxs-lookup"><span data-stu-id="dfb73-412">Direction values</span></span>
- <span data-ttu-id="dfb73-413">형식 값</span><span class="sxs-lookup"><span data-stu-id="dfb73-413">Type values</span></span>

<span data-ttu-id="dfb73-414">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="dfb73-415">상위 보낸 사람 및 받는 사람 보고서</span><span class="sxs-lookup"><span data-stu-id="dfb73-415">Top senders and recipients report</span></span>

<span data-ttu-id="dfb73-416">**상위 보낸 사람 및 받는 사람** 보고서는 상위 전자 메일 보낸 사람 및 받는 사람을 표시 하는 원형 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="dfb73-417">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **상위 보낸 사람 및 받는 사람** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="dfb73-418">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="dfb73-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![보고서 대시보드의 상위 보낸 사람 및 받는 사람 위젯](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="dfb73-420">상위 보낸 사람 및 받는 사람 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="dfb73-421">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="dfb73-422">**상위 메일 보낸 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="dfb73-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="dfb73-423">**상위 메일 받는 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="dfb73-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="dfb73-424">**주요 스팸 받는 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="dfb73-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="dfb73-425">**데이터 \> 표시 상위 맬웨어 받는 사람** (EOP)</span><span class="sxs-lookup"><span data-stu-id="dfb73-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="dfb73-426">**상위 맬웨어 받는 사람에 대 한 데이터 표시 \> (Office 365 용 Defender)**</span><span class="sxs-lookup"><span data-stu-id="dfb73-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="dfb73-427">원형 차트의 컴포지션은 이러한 선택에 따라 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="dfb73-428">원형 차트의 쐐기형 위에 마우스를 올리면 보내거나 받은 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="dfb73-429">보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![상위 보낸 사람 및 받는 사람 보고서의 보고서 보기에 있는 원형 차트](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="dfb73-431">상위 보낸 사람 및 받는 사람 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="dfb73-432">**세부 정보 표 보기** 를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="dfb73-433">**상위 메일 보낸 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="dfb73-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="dfb73-434">**상위 메일 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="dfb73-434">**Top mail senders**</span></span>
  - <span data-ttu-id="dfb73-435">**개수**</span><span class="sxs-lookup"><span data-stu-id="dfb73-435">**Count**</span></span>

- <span data-ttu-id="dfb73-436">**상위 메일 받는 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="dfb73-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="dfb73-437">**주요 메일 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="dfb73-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="dfb73-438">**개수**</span><span class="sxs-lookup"><span data-stu-id="dfb73-438">**Count**</span></span>

- <span data-ttu-id="dfb73-439">**주요 스팸 받는 사람에 대 한 데이터 표시 \>**</span><span class="sxs-lookup"><span data-stu-id="dfb73-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="dfb73-440">**주요 스팸 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="dfb73-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="dfb73-441">**개수**</span><span class="sxs-lookup"><span data-stu-id="dfb73-441">**Count**</span></span>

- <span data-ttu-id="dfb73-442">**데이터 \> 표시 상위 맬웨어 받는 사람** (EOP)</span><span class="sxs-lookup"><span data-stu-id="dfb73-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="dfb73-443">**주요 맬웨어 받는 사람**</span><span class="sxs-lookup"><span data-stu-id="dfb73-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="dfb73-444">**개수**</span><span class="sxs-lookup"><span data-stu-id="dfb73-444">**Count**</span></span>

- <span data-ttu-id="dfb73-445">**상위 맬웨어 받는 사람에 대 한 데이터 표시 \> (Office 365 용 Defender)**</span><span class="sxs-lookup"><span data-stu-id="dfb73-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="dfb73-446">**상위 맬웨어 받는 사람 (Office 365 용 Defender)**</span><span class="sxs-lookup"><span data-stu-id="dfb73-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="dfb73-447">**개수**</span><span class="sxs-lookup"><span data-stu-id="dfb73-447">**Count**</span></span>

<span data-ttu-id="dfb73-448">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dfb73-449">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="dfb73-450">이러한 보고서를 표시 하는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="dfb73-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="dfb73-451">보고서를 보고 사용 하려면 보안 & 준수 센터 **및** Exchange Online에서 지정 된 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-451">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="dfb73-452">보안 & 준수 센터에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-452">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="dfb73-453">-조직 관리-보안 관리자 ( [Azure Active Directory 관리 센터](https://aad.portal.azure.com) 에서이 작업을 수행할 수도 있음)-보안 독자</span><span class="sxs-lookup"><span data-stu-id="dfb73-453">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="dfb73-454">자세한 내용은 [보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfb73-454">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="dfb73-455">Exchange Online에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-455">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="dfb73-456">-조직 관리-보기 전용 조직 관리-보기 전용 받는 사람-준수 관리</span><span class="sxs-lookup"><span data-stu-id="dfb73-456">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="dfb73-457">자세한 내용은 exchange online의 [사용 권한](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 및 [exchange online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dfb73-457">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dfb73-458">관련 항목</span><span class="sxs-lookup"><span data-stu-id="dfb73-458">Related topics</span></span>

[<span data-ttu-id="dfb73-459">보안 및 준수 센터의 스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="dfb73-459">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="dfb73-460">보안 및 준수 센터의 메일 흐름 파악</span><span class="sxs-lookup"><span data-stu-id="dfb73-460">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="dfb73-461">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-461">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="dfb73-462">Microsoft Defender for Office 365에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="dfb73-462">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
