---
title: 전자 메일 보안 보고서 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft 365 Defender 포털에서 사용할 수 있는 전자 메일 보안 보고서를 찾아 사용하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad5a9f0d87902deb1985daebfa61cd733d22cbec
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029575"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="f453f-103">Microsoft 365 Defender 포털에서 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f453f-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f453f-104">**Applies to**</span></span>
- [<span data-ttu-id="f453f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f453f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f453f-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="f453f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f453f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f453f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f453f-108">Microsoft 365의 스팸 방지, 맬웨어 방지 및 암호화 기능과 같은 전자 메일 보안 기능이 조직을 보호하는 방법을 볼 수 있도록 Microsoft 365 Defender 포털에서 다양한 보고서를 사용할 수 <https://security.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="f453f-109">필요한 권한이 [](#what-permissions-are-needed-to-view-these-reports)있는 경우 보고서 전자 메일 및 공동 작업 전자 메일 공동  작업 전자 메일 & 공동 작업 보고서로 이동하여 Microsoft 365 Defender \>  \> **포털에서 & 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-110">전자 메일 및 공동 작업 **& 페이지로** 직접 이동하기 위해 를 를 를 열 수 <https://security.microsoft.com/emailandcollabreport> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft & 365 Defender 포털의 전자 메일 공동 작업 보고서 페이지](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="f453f-112">Email & collaboration **reports** 페이지의 일부 보고서에는 Office 365용 Microsoft Defender가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f453f-113">이러한 보고서에 대한 자세한 내용은 [Microsoft 365 Defender 포털에서 Office 365용 Defender 보고서 보기를 참조하세요.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="f453f-114">메일 흐름과 관련된 보고서는 이제 EAC(Exchange 관리 센터)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="f453f-115">이러한 보고서에 대한 자세한 내용은 새 Exchange 관리 센터의 메일 흐름 [보고서를 참조하세요.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="f453f-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="f453f-116">손상된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="f453f-117">이 보고서는 Exchange Online 사서함이 있는 Microsoft 365 조직에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="f453f-118">독립 실행형 EOP(Exchange Online Protection) 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="f453f-119">손상된 **사용자 보고서에는** 지난 7일 이내에  의심 또는 제한으로  표시된 사용자 계정 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="f453f-120">이러한 상태 중 하나에 있는 계정이 문제가 발생하거나 손상될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="f453f-121">자주 사용하는 경우 보고서를 사용하여 의심스러우거나 제한된 계정에서 스파이크 및 추세를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="f453f-122">손상된 사용자에 대한 자세한 내용은 손상된 전자 메일 계정에 응답을 [참조하세요.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![전자 메일 및 공동 작업 보고서 & 손상된 사용자 위젯](../../media/compromised-users-report-widget.png)

<span data-ttu-id="f453f-124">집계 보기는 지난 90일간의 데이터를 표시하고 세부 정보 보기에는 지난 30일간의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="f453f-125">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자 메일 &  공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f453f-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-126">전자 메일 & **공동** 작업 보고서 페이지에서 손상된 사용자를 **찾은** 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="f453f-127">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/CompromisedUsers> 습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="f453f-128">손상된  사용자 페이지에서 필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f453f-129">**날짜(UTC)**: **시작 날짜 및** 종료 **날짜입니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="f453f-130">**활동**:</span><span class="sxs-lookup"><span data-stu-id="f453f-130">**Activity**:</span></span>
  - <span data-ttu-id="f453f-131">**의심스러운**: 사용자 계정이 의심스러운 전자 메일을 보냈고 전자 메일을 보내지 못하도록 제한될 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="f453f-132">**제한:** 사용자 계정은 의심스러운 패턴으로 인해 전자 메일을 보내지 못하도록 제한되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="f453f-133">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![손상된 사용자 보고서의 보고서 보기](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="f453f-135">그래프 아래의 세부 정보 표에서 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="f453f-136">**만들기 시간**</span><span class="sxs-lookup"><span data-stu-id="f453f-136">**Creation time**</span></span>
- <span data-ttu-id="f453f-137">**사용자 ID**</span><span class="sxs-lookup"><span data-stu-id="f453f-137">**User ID**</span></span>
- <span data-ttu-id="f453f-138">**작업**</span><span class="sxs-lookup"><span data-stu-id="f453f-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="f453f-139">Exchange 전송 규칙 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-139">Exchange transport rule report</span></span>

<span data-ttu-id="f453f-140">**Exchange 전송 규칙 보고서는** 메일 흐름 규칙(전송 규칙)이 조직에서 들어오는 메시지와 보내고 있는 메시지에 대한 영향을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="f453f-141">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자 메일 &  공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f453f-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-142">전자 메일 & **공동 작업 보고서** 페이지에서 Exchange 전송 규칙을 **찾은** 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="f453f-143">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/ETRRuleReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![전자 메일 및 공동 작업 보고서 & Exchange 전송 규칙 위젯](../../media/transport-rule-report-widget.png)

<span data-ttu-id="f453f-145">Exchange 전송 **규칙 보고서 페이지에서** 사용 가능한 차트 및 데이터는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="f453f-146">방향별 차트 분석</span><span class="sxs-lookup"><span data-stu-id="f453f-146">Chart breakdown by Direction</span></span>

![Exchange 전송 규칙 보고서의 Exchange 전송 규칙에 대한 방향 보기](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="f453f-148">방향별 **차트 분석 을 선택하면** 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="f453f-149">**Exchange 전송 규칙으로** 데이터 보기: 메일  흐름 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지 수입니다. </span><span class="sxs-lookup"><span data-stu-id="f453f-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="f453f-150">DLP Exchange 전송 규칙으로 데이터  보기:  **DLP(데이터** 손실 방지) 메일 흐름 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="f453f-151">그래프 아래의 세부 정보 표에는 다음 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="f453f-152">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-152">**Date**</span></span>
- <span data-ttu-id="f453f-153">**DLP 정책(DLP** Exchange 전송 **규칙으로만** 데이터 보기)</span><span class="sxs-lookup"><span data-stu-id="f453f-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="f453f-154">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="f453f-154">**Transport rule**</span></span>
- <span data-ttu-id="f453f-155">**제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-155">**Subject**</span></span>
- <span data-ttu-id="f453f-156">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="f453f-156">**Sender address**</span></span>
- <span data-ttu-id="f453f-157">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="f453f-157">**Recipient address**</span></span>
- <span data-ttu-id="f453f-158">**심각도**</span><span class="sxs-lookup"><span data-stu-id="f453f-158">**Severity**</span></span>
- <span data-ttu-id="f453f-159">**방향**</span><span class="sxs-lookup"><span data-stu-id="f453f-159">**Direction**</span></span>

<span data-ttu-id="f453f-160">필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f453f-161">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-162">**방향:** **아웃바운드** 및 **인바운드**</span><span class="sxs-lookup"><span data-stu-id="f453f-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="f453f-163">**심각도:** **높은 심각도,** **보통 심각도** 및 **낮은 심각도**</span><span class="sxs-lookup"><span data-stu-id="f453f-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="f453f-164">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="f453f-165">심각도별 차트 분석</span><span class="sxs-lookup"><span data-stu-id="f453f-165">Chart breakdown by Severity</span></span>

![Exchange 전송 규칙 보고서의 Exchange 전송 규칙에 대한 심각도 보기](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="f453f-167">심각도별 차트 분석 **을** 선택하면 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="f453f-168">**Exchange 전송 규칙으로** 데이터 보기: 높은 심각도, 중간 심각도 및 낮은 심각도 메시지 **수입니다.** </span><span class="sxs-lookup"><span data-stu-id="f453f-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="f453f-169">심각도 수준을 규칙의 작업으로 설정할 수 있습니다(**심각도** 수준 또는 _SetAuditSeverity로_ 이 규칙 감사).</span><span class="sxs-lookup"><span data-stu-id="f453f-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="f453f-170">자세한 내용은 [Exchange Online의 메일 흐름 규칙 작업을 참조하세요.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="f453f-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="f453f-171">**DLP Exchange** 전송 규칙으로 데이터 보기: DLP 메일 흐름 규칙의 영향을 받은 높은 심각도, 보통 심각도 및 낮은 심각도 메시지 수입니다.  </span><span class="sxs-lookup"><span data-stu-id="f453f-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="f453f-172">그래프 아래의 세부 정보 표에는 다음 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="f453f-173">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-173">**Date**</span></span>
- <span data-ttu-id="f453f-174">**DLP 정책(DLP** Exchange 전송 **규칙으로만** 데이터 보기)</span><span class="sxs-lookup"><span data-stu-id="f453f-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="f453f-175">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="f453f-175">**Transport rule**</span></span>
- <span data-ttu-id="f453f-176">**제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-176">**Subject**</span></span>
- <span data-ttu-id="f453f-177">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="f453f-177">**Sender address**</span></span>
- <span data-ttu-id="f453f-178">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="f453f-178">**Recipient address**</span></span>
- <span data-ttu-id="f453f-179">**심각도**</span><span class="sxs-lookup"><span data-stu-id="f453f-179">**Severity**</span></span>
- <span data-ttu-id="f453f-180">**방향**</span><span class="sxs-lookup"><span data-stu-id="f453f-180">**Direction**</span></span>

<span data-ttu-id="f453f-181">필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f453f-182">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-183">**방향:** **아웃바운드** 및 **인바운드**</span><span class="sxs-lookup"><span data-stu-id="f453f-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="f453f-184">**심각도:** **높은 심각도,** **보통 심각도** 및 **낮은 심각도**</span><span class="sxs-lookup"><span data-stu-id="f453f-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="f453f-185">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="f453f-186">전달 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="f453f-187">이제 **EAC에서** 전달 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="f453f-188">자세한 내용은 새 EAC의 자동 전달된 메시지 [보고서를 참조하세요.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)</span><span class="sxs-lookup"><span data-stu-id="f453f-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="f453f-189">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-189">Mailflow status report</span></span>

<span data-ttu-id="f453f-190">**메일 흐름** 상태 보고서는 수신 및 보낸 전자 메일, 스팸 검색, 맬웨어, "양호"로 식별된 전자 메일 및 에지에서 허용되거나 차단된 전자 메일에 대한 정보를 표시하는 스마트 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="f453f-191">이 보고서는 에지 보호 정보를 포함하는 유일한 보고서로, EOP(Exchange Online Protection)에서 평가하기 위해 서비스에 허용되기 전에 차단되는 전자 메일의 수만 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="f453f-192">받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지가 아니라 5개의 다른 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="f453f-193">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자 메일 &  공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f453f-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-194">전자 메일 & **공동** 작업 보고서 페이지에서 메일 흐름 상태 요약을 **찾은** 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="f453f-195">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/mailflowStatusReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![메일 흐름 상태 요약 위젯 전자 메일 & 공동 작업 보고서 페이지의](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="f453f-197">메일 흐름 상태 보고서의 형식 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-197">Type view for the Mailflow status report</span></span>

![메일 흐름 상태 보고서에 보기 입력](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="f453f-199">메일 흐름 **상태 보고서** 페이지에서  유형 탭이 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="f453f-200">기본적으로 이 보기에는 차트 및 다음 필터로 구성된 세부 정보 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="f453f-201">**날짜(UTC)** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="f453f-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="f453f-202">**메일 방향**:</span><span class="sxs-lookup"><span data-stu-id="f453f-202">**Mail direction**:</span></span>
  - <span data-ttu-id="f453f-203">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="f453f-203">**Inbound**</span></span>
  - <span data-ttu-id="f453f-204">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="f453f-204">**Outbound**</span></span>
  - <span data-ttu-id="f453f-205">**Intra-org**: 이 개수는 테넌트 내의 메시지에 대한 수입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="f453f-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f453f-206">보낸 사람 abc@domain.com 받는 사람 주소로 xyz@domain.com(인바운드 및 아웃바운드와 별도로 **계산)** </span><span class="sxs-lookup"><span data-stu-id="f453f-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="f453f-207">**유형:**</span><span class="sxs-lookup"><span data-stu-id="f453f-207">**Type**:</span></span>
  - <span data-ttu-id="f453f-208">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-208">**Good mail**</span></span>
  - <span data-ttu-id="f453f-209">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="f453f-209">**Malware**</span></span>
  - <span data-ttu-id="f453f-210">**스팸**</span><span class="sxs-lookup"><span data-stu-id="f453f-210">**Spam**</span></span>
  - <span data-ttu-id="f453f-211">**에지 보호**</span><span class="sxs-lookup"><span data-stu-id="f453f-211">**Edge protection**</span></span>
  - <span data-ttu-id="f453f-212">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="f453f-212">**Rule messages**</span></span>
  - <span data-ttu-id="f453f-213">**피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-213">**Phishing email**</span></span>
- <span data-ttu-id="f453f-214">**도메인**: **모두**</span><span class="sxs-lookup"><span data-stu-id="f453f-214">**Domain**: **All**</span></span>

<span data-ttu-id="f453f-215">차트는 종류 값으로 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="f453f-216">필터 를 클릭하여 이러한 필터를 변경할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="f453f-217">그래프 아래의 세부 정보 표에는 다음 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="f453f-218">**방향**</span><span class="sxs-lookup"><span data-stu-id="f453f-218">**Direction**</span></span>
- <span data-ttu-id="f453f-219">**유형**</span><span class="sxs-lookup"><span data-stu-id="f453f-219">**Type**</span></span>
- <span data-ttu-id="f453f-220">**24시간**</span><span class="sxs-lookup"><span data-stu-id="f453f-220">**24 hours**</span></span>
- <span data-ttu-id="f453f-221">**3일**</span><span class="sxs-lookup"><span data-stu-id="f453f-221">**3 days**</span></span>
- <span data-ttu-id="f453f-222">**7일**</span><span class="sxs-lookup"><span data-stu-id="f453f-222">**7 days**</span></span>
- <span data-ttu-id="f453f-223">**15일**</span><span class="sxs-lookup"><span data-stu-id="f453f-223">**15 days**</span></span>
- <span data-ttu-id="f453f-224">**30일**</span><span class="sxs-lookup"><span data-stu-id="f453f-224">**30 days**</span></span>

<span data-ttu-id="f453f-225">자세한 내용을 **보려면 범주** 선택을 클릭하면 다음 값에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="f453f-226">**피싱 전자 메일:** 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f453f-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f453f-227">**전자 메일의** 맬웨어: 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f453f-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f453f-228">**스팸 검색:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f453f-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="f453f-229">**Edge 차단 스팸:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f453f-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="f453f-230">형식 보기에서 내보내기</span><span class="sxs-lookup"><span data-stu-id="f453f-230">Export from Type view</span></span>

<span data-ttu-id="f453f-231">세부 정보 보기의 경우 하루 동안만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f453f-232">따라서 7일 동안 데이터를 내보내는 경우 7개 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f453f-233">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f453f-234">해당 일의 데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="f453f-235">메일 흐름 상태 보고서의 방향 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-235">Direction view for the Mailflow status report</span></span>

![메일 흐름 상태 보고서의 방향 보기](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="f453f-237">방향 탭을 **클릭하면** 유형 보기의 동일한 기본 **필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="f453f-238">차트는 방향 값으로 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="f453f-239">필터 를 클릭하여 이러한 필터를 변경할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="f453f-240">형식 보기의 **동일한 필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f453f-241">세부 정보 테이블에는 형식 보기와 동일한 **정보가** 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="f453f-242">사용 가능한 선택 **항목** 및 동작에 대한 자세한 내용은 종류 보기와 **같습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="f453f-243">방향 보기에서 내보내기</span><span class="sxs-lookup"><span data-stu-id="f453f-243">Export from Direction view</span></span>

<span data-ttu-id="f453f-244">세부 정보 보기의 경우 하루 동안만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f453f-245">따라서 7일 동안 데이터를 내보내는 경우 7개 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f453f-246">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f453f-247">해당 일의 데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="f453f-248">메일 흐름 상태 보고서의 유입경로 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="f453f-249">**Funnel** 보기는 Microsoft의 전자 메일 위협 방지 기능이 조직에서 받는 전자 메일과 보내기 전자 메일을 필터링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="f453f-250">전체 전자 메일 수와 에지 보호, 맬웨어 방지, 피싱 방지, 스팸 방지 및 스푸핑 방지를 포함하여 구성된 위협 방지 기능이 이 수에 미치는 영향을 자세히 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![메일 흐름 상태 보고서의 유입경로 보기](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="f453f-252">유정  탭을 클릭하면 기본적으로 이 보기에는 차트와 다음 필터로 구성된 세부 정보 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="f453f-253">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="f453f-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f453f-254">**방향**:</span><span class="sxs-lookup"><span data-stu-id="f453f-254">**Direction**:</span></span>
  - <span data-ttu-id="f453f-255">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="f453f-255">**Inbound**</span></span>
  - <span data-ttu-id="f453f-256">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="f453f-256">**Outbound**</span></span>
  - <span data-ttu-id="f453f-257">**Intra-org:** 이 개수는 테넌트 내에서 보낸 메시지에 대한 수입니다. 즉, 보낸 abc@domain.com 받는 사람 xyz@domain.com(인바운드 및 아웃바운드와는 별도로 계산)를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="f453f-258">집계 보기 및 세부 정보 테이블 보기에서는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f453f-259">필터 를 클릭하여 이러한 필터를 변경할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="f453f-260">형식 보기의 **동일한 필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f453f-261">이 차트에는 다음별로 구성한 전자 메일 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="f453f-262">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-262">**Total email**</span></span>
- <span data-ttu-id="f453f-263">**Edge 보호 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-263">**Email after edge protection**</span></span>
- <span data-ttu-id="f453f-264">**전송 후 전자 메일 규칙(메일** 흐름 규칙)</span><span class="sxs-lookup"><span data-stu-id="f453f-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="f453f-265">**맬웨어 방지, 파일 신뢰도, 파일 형식 차단 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="f453f-266">**피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="f453f-267">**스팸 방지, 대량 메일 필터링 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="f453f-268">**사용자 및 도메인 가장 후 전자 메일**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="f453f-269">**파일 및 URL 확인 후 전자 메일**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="f453f-270">**배달 후 보호 후 무해한 것으로 감지된 전자 메일(URL 클릭 시간 보호)**</span><span class="sxs-lookup"><span data-stu-id="f453f-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="f453f-271"><sup>\*</sup>Defender for Office 365 전용</span><span class="sxs-lookup"><span data-stu-id="f453f-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="f453f-272">EOP 또는 Defender에서 필터링한 전자 메일을 개별적으로 Office 365 차트 범례의 값을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="f453f-273">세부 정보 표에는 내선 날짜 순서로 표시된 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f453f-274">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-274">**Date**</span></span>
- <span data-ttu-id="f453f-275">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-275">**Total email**</span></span>
- <span data-ttu-id="f453f-276">**에지 보호**</span><span class="sxs-lookup"><span data-stu-id="f453f-276">**Edge protection**</span></span>
- <span data-ttu-id="f453f-277">**맬웨어 방지, 파일 신뢰도, 파일 형식 블록**:</span><span class="sxs-lookup"><span data-stu-id="f453f-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="f453f-278">**파일 신뢰도:** 다른 Microsoft 고객이 첨부한 파일을 식별하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="f453f-279">**파일 형식 블록:** 메시지에 식별된 악성 파일의 유형으로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="f453f-280">**피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지**:</span><span class="sxs-lookup"><span data-stu-id="f453f-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="f453f-281">**URL 신뢰도:** 다른 Microsoft 고객이 URL을 식별하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="f453f-282">**브랜드 가장:** 보낸 사람으로 가장하는 잘 알려진 브랜드에서 보낸 메시지로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="f453f-283">**스푸핑** 방지: 받는 사람이 속한 도메인 또는 메시지 보낸 사람이 소유하지 않은 도메인을 스푸핑하려고 시도하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="f453f-284">**스팸 방지, 대량 메일 필터링**:</span><span class="sxs-lookup"><span data-stu-id="f453f-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="f453f-285">**대량 메일 필터링:** 스팸 방지 정책의 BCL(대량 불만 수준) 임계값을 기준으로 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="f453f-286">**사용자 및 도메인 가장(사용자** 및 도메인 Office 365) :</span><span class="sxs-lookup"><span data-stu-id="f453f-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f453f-287">**사용자 가장:** 피싱 방지 정책의 가장 보호 설정에 정의된 사용자(메시지 보낸 사람)를 가장하려는 시도로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="f453f-288">**도메인 가장:** 피싱 방지 정책의 가장 보호 설정에 정의된 도메인을 가장하려고 시도하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="f453f-289">**파일 및 URL 확인(Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="f453f-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f453f-290">**파일 검색:** 첨부 파일 Safe 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="f453f-291">**URL 검색:** 링크 정책에 의해 Safe 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="f453f-292">**사후 배달 보호 및 ZAP(ATP) 또는 EOP(ZAP)**: 맬웨어, 스팸 및 피싱에 대한 ZAP(제로 아워 자동 제거)입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="f453f-293">세부 정보 표에서 행을 선택하면 플라이아웃에 전자 메일 수에 대한 추가 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="f453f-294">펀들 보기에서 내보내기</span><span class="sxs-lookup"><span data-stu-id="f453f-294">Export from Funnel view</span></span>

<span data-ttu-id="f453f-295">옵션에서 **내보내기** 를 **클릭한** 후 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="f453f-296">**요약(최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="f453f-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f453f-297">**세부 정보(지난 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="f453f-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f453f-298">**날짜에서** 범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f453f-299">현재 필터에 대한 데이터는 파일로 .csv 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f453f-300">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f453f-301">데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="f453f-302">메일 흐름 상태 보고서의 기술 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="f453f-303">기술 **보기는** **Funnel** 보기와 유사하여 구성된 위협 방지 기능에 대해 보다 세부적인 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="f453f-304">차트에서 다양한 위협 방지 단계에서 메시지를 분류하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="f453f-305">기술 보기  탭을 클릭하면 기본적으로 이 보기에는 차트와 다음 필터로 구성된 세부 정보 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="f453f-306">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="f453f-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f453f-307">**방향**:</span><span class="sxs-lookup"><span data-stu-id="f453f-307">**Direction**:</span></span>
  - <span data-ttu-id="f453f-308">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="f453f-308">**Inbound**</span></span>
  - <span data-ttu-id="f453f-309">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="f453f-309">**Outbound**</span></span>
  - <span data-ttu-id="f453f-310">**Intra-org**: 이 개수는 테넌트 내의 메시지에 대한 수입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="f453f-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f453f-311">보낸 사람 abc@domain.com 받는 사람 주소로 xyz@domain.com(인바운드 및 아웃바운드와 별도로 계산)</span><span class="sxs-lookup"><span data-stu-id="f453f-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="f453f-312">집계 보기 및 세부 정보 테이블 보기에서는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f453f-313">필터 를 클릭하여 이러한 필터를 변경할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="f453f-314">형식 보기의 **동일한 필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f453f-315">이 차트에는 다음 범주로 구성된 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f453f-316">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-316">**Total email**</span></span>
- <span data-ttu-id="f453f-317">**Edge 허용** 및 **Edge 필터링**</span><span class="sxs-lookup"><span data-stu-id="f453f-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="f453f-318">**전송 규칙 허용** 및 **전송 규칙 필터링(메일** 흐름 규칙)</span><span class="sxs-lookup"><span data-stu-id="f453f-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="f453f-319">**맬웨어가** 아닌 경우 **Safe 검색** <sup>\*</sup> 및 맬웨어 방지 엔진 **검색**</span><span class="sxs-lookup"><span data-stu-id="f453f-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="f453f-320">**피싱이 아닌** 경우,  **DMARC 실패,** 가장 <sup>\*</sup> 검색, **스푸핑 검색** 및 **피싱 감지**</span><span class="sxs-lookup"><span data-stu-id="f453f-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="f453f-321">**URL 검색 및 URL** 검색을 통해 검색 **안 하세요.**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="f453f-322">**스팸 및**  **스팸 아미기**</span><span class="sxs-lookup"><span data-stu-id="f453f-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="f453f-323">**악성이 아닌 전자** **메일, Safe 링크** 검색 및 <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="f453f-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="f453f-324"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f453f-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="f453f-325">차트의 범주 위에 마우스를 대면 해당 범주의 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="f453f-326">세부 정보 표에는 내선 날짜 순서로 표시된 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f453f-327">**날짜(UTC)**</span><span class="sxs-lookup"><span data-stu-id="f453f-327">**Date (UTC)**</span></span>
- <span data-ttu-id="f453f-328">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-328">**Total email**</span></span>
- <span data-ttu-id="f453f-329">**Edge 필터링**</span><span class="sxs-lookup"><span data-stu-id="f453f-329">**Edge filtered**</span></span>
- <span data-ttu-id="f453f-330">**규칙 메시지:** 메일 흐름 규칙(전송 규칙)으로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="f453f-331">**맬웨어 방지 엔진**, **Safe 첨부 파일** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="f453f-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="f453f-332">**DMARC, 가장,** <sup>\*</sup> **스푸핑,** **피싱 필터링 :**</span><span class="sxs-lookup"><span data-stu-id="f453f-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="f453f-333">**DMARC: DMARC** 인증 검사에 실패한 메시지로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="f453f-334">**URL 검색**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="f453f-335">**스팸 방지 필터링**</span><span class="sxs-lookup"><span data-stu-id="f453f-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="f453f-336">**ZAP 제거됨**</span><span class="sxs-lookup"><span data-stu-id="f453f-336">**ZAP removed**</span></span>
- <span data-ttu-id="f453f-337">**링크로 Safe 검색**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="f453f-338"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f453f-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="f453f-339">세부 정보 표에서 행을 선택하면 플라이아웃에 전자 메일 수에 대한 추가 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="f453f-340">기술 보기에서 내보내기</span><span class="sxs-lookup"><span data-stu-id="f453f-340">Export from Tech view</span></span>

<span data-ttu-id="f453f-341">내보내기 **를 클릭할** 때 **옵션에서** 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="f453f-342">**요약(최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="f453f-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f453f-343">**세부 정보(지난 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="f453f-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f453f-344">**날짜에서** 범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f453f-345">현재 필터에 대한 데이터는 파일로 .csv 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f453f-346">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f453f-347">데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![메일 흐름 상태 보고서의 기술 보기](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="f453f-349">맬웨어 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-349">Malware detections report</span></span>

<span data-ttu-id="f453f-350">맬웨어 검색 보고서 **보고서는** 들어오는 전자 메일 메시지와 보내기 전자 메일 메시지의 맬웨어 검색에 대한 정보를 Exchange Online Protection EOP에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="f453f-351">EOP의 맬웨어 보호에 대한 자세한 내용은 [EOP의 맬웨어 방지 보호를 참조하세요.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="f453f-352">집계 보기 필터는 90일 동안 허용되는 반면 세부 정보 테이블 필터는 10일 동안만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="f453f-353">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f453f-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-354">전자 메일 & 공동 작업 보고서 페이지에서 전자 **메일에서** 검색된 **맬웨어를** 찾은 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="f453f-355">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/MalwareDetections> 습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![전자 메일 및 공동 작업 보고서 페이지의 전자 메일 위젯에서 & 검색](../../media/malware-detections-widget.png)

<span data-ttu-id="f453f-357">**맬웨어** 검색 보고서 페이지에서 필터를 클릭하고 다음 값 중  하나를 선택하여 차트와 세부 정보 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="f453f-358">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-359">**방향:** **인바운드 및** **아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="f453f-359">**Direction**: **Inbound** and **Outbound**</span></span>

![전자 메일 보고서의 맬웨어 검색에서 보고서 보기](../../media/malware-detections-report-view.png)

<span data-ttu-id="f453f-361">그래프 아래의 세부 정보 표에서 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="f453f-362">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-362">**Date**</span></span>
- <span data-ttu-id="f453f-363">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="f453f-363">**Sender address**</span></span>
- <span data-ttu-id="f453f-364">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="f453f-364">**Recipient address**</span></span>
- <span data-ttu-id="f453f-365">**메시지 ID:** 메시지 헤더의 **Message-ID** 헤더 필드에서 사용할 수 있으며 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="f453f-366">값을 예로 들 수 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 있습니다(괄호 참고).</span><span class="sxs-lookup"><span data-stu-id="f453f-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="f453f-367">**제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-367">**Subject**</span></span>
- <span data-ttu-id="f453f-368">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="f453f-368">**Filename**</span></span>
- <span data-ttu-id="f453f-369">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="f453f-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="f453f-370">메일 대기 시간 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-370">Mail latency report</span></span>

<span data-ttu-id="f453f-371">**Defender** for Office 365 메일 대기 시간 보고서에는 조직 내에서 경험하는 메일 배달 및 확인 대기 시간에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="f453f-372">자세한 내용은 메일 대기 [시간 보고서를 참조하세요.](view-reports-for-mdo.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="f453f-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="f453f-373">스팸 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="f453f-374">스팸 **검색 보고서는** 결국 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="f453f-375">위협 방지 상태 보고서에서 동일한 [정보를 사용할 수 있습니다.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f453f-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="f453f-376">스푸핑 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="f453f-377">이 문서에 설명된 향상된 스푸핑 검색 보고서는 미리 보기에 있으며 변경될 수 있으며 일부 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="f453f-378">이전 버전의 보고서에는 양호한 **메일과** 스팸으로 **걸려 오기만 표시되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="f453f-379">**스푸핑 검색 보고서에는** 스푸핑으로 인해 차단되거나 허용된 메시지에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="f453f-380">스푸핑에 대한 자세한 내용은 [EOP의 스푸핑 방지 보호를 참조하세요.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="f453f-381">보고서의 집계 보기는 45일 동안 필터링할 수 있는 반면 세부 정보 보기는 <sup>\*</sup> 10일의 필터링만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="f453f-382"><sup>\*</sup> 결국 최대 90일의 필터링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="f453f-383">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f453f-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-384">전자 메일 **& 공동 작업** 보고서  페이지에서 스푸핑 검색을 찾은 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="f453f-385">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/SpoofMailReportV2> 습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![전자 메일 및 공동 작업 보고서 페이지의 & 위젯 스푸핑](../../media/spoof-detections-widget.png)

<span data-ttu-id="f453f-387">차트에는 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-387">The chart shows the following information:</span></span>

- <span data-ttu-id="f453f-388">**통과**</span><span class="sxs-lookup"><span data-stu-id="f453f-388">**Pass**</span></span>
- <span data-ttu-id="f453f-389">**실패**</span><span class="sxs-lookup"><span data-stu-id="f453f-389">**Fail**</span></span>
- <span data-ttu-id="f453f-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="f453f-390">**SoftPass**</span></span>
- <span data-ttu-id="f453f-391">**없음**</span><span class="sxs-lookup"><span data-stu-id="f453f-391">**None**</span></span>
- <span data-ttu-id="f453f-392">**기타**</span><span class="sxs-lookup"><span data-stu-id="f453f-392">**Other**</span></span>

<span data-ttu-id="f453f-393">차트에서 하루(데이터 데이터 포인트)에 마우스를 대면 검색된 스푸핑된 메시지 수와 그 이유를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="f453f-394">**스푸핑 메일** 보고서 페이지에서 필터를 클릭하고 다음 값 중 하나  이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="f453f-395">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-396">**결과**:</span><span class="sxs-lookup"><span data-stu-id="f453f-396">**Result**:</span></span>
  - <span data-ttu-id="f453f-397">**통과**</span><span class="sxs-lookup"><span data-stu-id="f453f-397">**Pass**</span></span>
  - <span data-ttu-id="f453f-398">**실패**</span><span class="sxs-lookup"><span data-stu-id="f453f-398">**Fail**</span></span>
  - <span data-ttu-id="f453f-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="f453f-399">**SoftPass**</span></span>
  - <span data-ttu-id="f453f-400">**없음**</span><span class="sxs-lookup"><span data-stu-id="f453f-400">**None**</span></span>
  - <span data-ttu-id="f453f-401">**기타**</span><span class="sxs-lookup"><span data-stu-id="f453f-401">**Other**</span></span>
- <span data-ttu-id="f453f-402">**스푸핑 유형:** **내부 및** **외부**</span><span class="sxs-lookup"><span data-stu-id="f453f-402">**Spoof type**: **Internal** and **External**</span></span>

![사이트 포털의 스푸핑 메일 보고서 Microsoft 365 Defender 페이지](../../media/spoof-detections-report-page.png)

<span data-ttu-id="f453f-404">그래프 아래의 세부 정보 표에서 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="f453f-405">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-405">**Date**</span></span>
- <span data-ttu-id="f453f-406">**스푸핑된 사용자**</span><span class="sxs-lookup"><span data-stu-id="f453f-406">**Spoofed user**</span></span>
- <span data-ttu-id="f453f-407">**인프라 보내기**</span><span class="sxs-lookup"><span data-stu-id="f453f-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="f453f-408">**스푸핑 유형**</span><span class="sxs-lookup"><span data-stu-id="f453f-408">**Spoof type**</span></span>
- <span data-ttu-id="f453f-409">**결과**</span><span class="sxs-lookup"><span data-stu-id="f453f-409">**Result**</span></span>
- <span data-ttu-id="f453f-410">**결과 코드**</span><span class="sxs-lookup"><span data-stu-id="f453f-410">**Result code**</span></span>
- <span data-ttu-id="f453f-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="f453f-411">**SPF**</span></span>
- <span data-ttu-id="f453f-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="f453f-412">**DKIM**</span></span>
- <span data-ttu-id="f453f-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="f453f-413">**DMARC**</span></span>
- <span data-ttu-id="f453f-414">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="f453f-414">**Message count**</span></span>

<span data-ttu-id="f453f-415">복합 인증 결과 코드에 대한 자세한 내용은 에서 스팸 방지 메시지 [헤더를 Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="f453f-416">제출 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-416">Submissions report</span></span>

<span data-ttu-id="f453f-417">제출 **보고서에는** 관리자가 분석을 위해 Microsoft에 보고한 항목에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="f453f-418">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f453f-419">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f453f-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-420">전자 메일 & **공동** 작업 보고서 페이지에서 제출을 **찾은** 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="f453f-421">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/adminSubmissionReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="f453f-422">Microsoft 365 Defender 포털에서 관리 [제출으로 이동하려면 제출로](admin-submission.md) **이동을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![전자 메일 및 공동 작업 & 페이지의 제출 위젯](../../media/submissions-report-widget.png)

<span data-ttu-id="f453f-424">차트에는 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-424">The chart shows the following information:</span></span>

- <span data-ttu-id="f453f-425">**보류 중**</span><span class="sxs-lookup"><span data-stu-id="f453f-425">**Pending**</span></span>
- <span data-ttu-id="f453f-426">**완료**</span><span class="sxs-lookup"><span data-stu-id="f453f-426">**Completed**</span></span>

<span data-ttu-id="f453f-427">제출 **페이지에서** 필터를 클릭하고 다음 값 중 하나 이상을  선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="f453f-428">**보고된 날짜:** **시작 시간** 및 **종료 시간**</span><span class="sxs-lookup"><span data-stu-id="f453f-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="f453f-429">**제출 유형**:</span><span class="sxs-lookup"><span data-stu-id="f453f-429">**Submission type**:</span></span>
  - <span data-ttu-id="f453f-430">**전자 메일**</span><span class="sxs-lookup"><span data-stu-id="f453f-430">**Email**</span></span>
  - <span data-ttu-id="f453f-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="f453f-431">**URL**</span></span>
  - <span data-ttu-id="f453f-432">**파일**</span><span class="sxs-lookup"><span data-stu-id="f453f-432">**File**</span></span>
- <span data-ttu-id="f453f-433">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="f453f-433">**Submission ID**</span></span>
- <span data-ttu-id="f453f-434">**네트워크 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="f453f-434">**Network Message ID**</span></span>
- <span data-ttu-id="f453f-435">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-435">**Sender**</span></span>
- <span data-ttu-id="f453f-436">**이름**</span><span class="sxs-lookup"><span data-stu-id="f453f-436">**Name**</span></span>
- <span data-ttu-id="f453f-437">**제출한 인원**</span><span class="sxs-lookup"><span data-stu-id="f453f-437">**Submitted by**</span></span>
- <span data-ttu-id="f453f-438">**제출 이유:**</span><span class="sxs-lookup"><span data-stu-id="f453f-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="f453f-439">**정크 아님**</span><span class="sxs-lookup"><span data-stu-id="f453f-439">**Not junk**</span></span>
  - <span data-ttu-id="f453f-440">**피싱**</span><span class="sxs-lookup"><span data-stu-id="f453f-440">**Phish**</span></span>
  - <span data-ttu-id="f453f-441">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="f453f-441">**Malware**</span></span>
  - <span data-ttu-id="f453f-442">**스팸**</span><span class="sxs-lookup"><span data-stu-id="f453f-442">**Spam**</span></span>
- <span data-ttu-id="f453f-443">**상태 다시 검색:**</span><span class="sxs-lookup"><span data-stu-id="f453f-443">**Rescan status**:</span></span>
  - <span data-ttu-id="f453f-444">**보류 중**</span><span class="sxs-lookup"><span data-stu-id="f453f-444">**Pending**</span></span>
  - <span data-ttu-id="f453f-445">**완료**</span><span class="sxs-lookup"><span data-stu-id="f453f-445">**Completed**</span></span>

<span data-ttu-id="f453f-446">그래프 아래의 세부 정보 표에는 동일한 정보가  표시되어  있으며 전자 메일  및 공동 작업 제출의 분석 제출 탭에서와 동일한 **그룹 또는 & 옵션이** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="f453f-447">자세한 내용은 Microsoft에 대한 [관리자 제출 보기를 참조하세요.](admin-submission.md#view-admin-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="f453f-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Microsoft 365 Defender 포털의 제출 보고서 페이지](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="f453f-449">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-449">Threat protection status report</span></span>

<span data-ttu-id="f453f-450">**위협 방지 상태 보고서는** EOP 및 Defender에서 모두 사용할 수 Office 365. 그러나 보고서에는 다른 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="f453f-451">예를 들어 EOP 고객은 전자 메일에서 검색된 맬웨어에 대한 정보를 볼 수 있지만, 전자 메일, Safe 및 에 대한 첨부 파일에서 검색된 악성 파일에 대한 SharePoint, OneDrive [Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="f453f-452">이 보고서는 맬웨어 방지 엔진에 의해 차단된 파일 또는 웹 사이트 주소(URL), [ZAP(제로](zero-hour-auto-purge.md)아워 자동 제거) 및 피싱 방지 정책의 Safe [링크,](safe-links.md) [](safe-attachments.md)Safe 첨부 파일 및 가장 보호 기능과 같은 Office 365 기능에 대한 Defender와 같은 악성 콘텐츠가 있는 전자 메일 메시지 수를 [제공합니다.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="f453f-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="f453f-453">이 정보를 사용하여 추세를 식별하거나 조직 정책에 조정이 필요한지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="f453f-454">**참고:** 받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지가 아니라 5개의 다른 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="f453f-455">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f453f-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-456">전자 메일 & 공동 작업 **보고서** 페이지에서 위협 방지 상태를 **찾은** 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="f453f-457">보고서로 직접 이동하기 위해 다음 URL 중 하나를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="f453f-458">Defender for Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="f453f-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="f453f-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="f453f-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![전자 메일 및 공동 작업 보고서 & 위협 방지 상태 위젯](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="f453f-461">기본적으로 차트에는 지난 7일간의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="f453f-462">위협 방지  상태  보고서 페이지에서 필터링을 클릭하면 90일 날짜 범위를 선택할 수 있습니다(평가판 구독은 30일로 제한될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="f453f-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="f453f-463">세부 정보 표에서는 30일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="f453f-464">다음 섹션에서는 사용 가능한 보기에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="f453f-465">개요로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-465">View data by Overview</span></span>

![위협 방지 상태 보고서의 개요 보기](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="f453f-467">개요로 **데이터** 보기 보기에서 차트에 다음과 같은 검색 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="f453f-468">**전자 메일 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="f453f-468">**Email malware**</span></span>
- <span data-ttu-id="f453f-469">**전자 메일 피싱**</span><span class="sxs-lookup"><span data-stu-id="f453f-469">**Email phish**</span></span>
- <span data-ttu-id="f453f-470">**콘텐츠 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="f453f-470">**Content malware**</span></span>

<span data-ttu-id="f453f-471">차트 아래에 세부 정보 표를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-471">No details table is available below the chart.</span></span>

<span data-ttu-id="f453f-472">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f453f-473">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-474">**검색:** **전자 메일 맬웨어,** **전자 메일 피싱** 또는 **콘텐츠 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="f453f-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="f453f-475">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="f453f-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f453f-476">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f453f-477">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f453f-478">**방향**</span><span class="sxs-lookup"><span data-stu-id="f453f-478">**Direction**</span></span>
- <span data-ttu-id="f453f-479">**도메인**</span><span class="sxs-lookup"><span data-stu-id="f453f-479">**Domain**</span></span>
- <span data-ttu-id="f453f-480">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="f453f-480">**Policy type**</span></span>

<span data-ttu-id="f453f-481">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="f453f-482">검색 기술별 전자 메일 피싱 및 차트 \> 분석으로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![위협 방지 상태 보고서의 피싱 전자 메일에 대한 검색 기술 보기](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="f453f-484">전자 메일 **피싱으로 데이터 \> 보기** **및** 검색 기술별 차트 분석 보기에서 차트에 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="f453f-485">**URL 악의적인 신뢰도:** 다른 Office 365 고객에 대한 <sup>\*</sup> 악의적인 URL 신뢰도 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f453f-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="f453f-486">**고급 필터:** 기계 학습을 기반으로 하는 피싱 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="f453f-487">**일반 필터:** 분석가 규칙에 기반한 피싱 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="f453f-488">**스푸핑된** 도메인: 보낸 사람이 받는 사람 도메인을 스푸핑하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="f453f-489">**스푸핑 외부** 도메인: 보낸 사람이 다른 도메인을 스푸핑하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="f453f-490">**스푸핑 DMARC:** 메시지에 대한 DMARC 인증 실패.</span><span class="sxs-lookup"><span data-stu-id="f453f-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="f453f-491">**가장 브랜드:** 보낸 사람 기반의 잘 알려진 브랜드 가장.</span><span class="sxs-lookup"><span data-stu-id="f453f-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="f453f-492">**혼합 분석 검색**</span><span class="sxs-lookup"><span data-stu-id="f453f-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="f453f-493">**파일 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="f453f-493">**File reputation**</span></span>
- <span data-ttu-id="f453f-494">**지문 일치**</span><span class="sxs-lookup"><span data-stu-id="f453f-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="f453f-495">**URL 확인 신뢰도**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="f453f-496">**URL 확인**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="f453f-497">**가장 사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="f453f-498">**가장 도메인:** 고객이 소유하거나 정의하는 도메인의 <sup>\*</sup> 가장입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="f453f-499">**사서함 인텔리전스 가장:** 관리자가 정의하거나 사서함 인텔리전스를 통해 학습한 사용자의 <sup>\*</sup> 가장입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="f453f-500">**파일 Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="f453f-501">**캠페인**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="f453f-502">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f453f-503">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-503">**Date**</span></span>
- <span data-ttu-id="f453f-504">**제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-504">**Subject**</span></span>
- <span data-ttu-id="f453f-505">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-505">**Sender**</span></span>
- <span data-ttu-id="f453f-506">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-506">**Recipients**</span></span>
- <span data-ttu-id="f453f-507">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="f453f-507">**Detected by**</span></span>
- <span data-ttu-id="f453f-508">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="f453f-508">**Delivery Status**</span></span>
- <span data-ttu-id="f453f-509">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="f453f-509">**Source of Compromise**</span></span>
- <span data-ttu-id="f453f-510">**태그**</span><span class="sxs-lookup"><span data-stu-id="f453f-510">**Tags**</span></span>

<span data-ttu-id="f453f-511">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f453f-512">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-513">**감지**</span><span class="sxs-lookup"><span data-stu-id="f453f-513">**Detection**</span></span>
- <span data-ttu-id="f453f-514">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="f453f-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f453f-515">**방향**</span><span class="sxs-lookup"><span data-stu-id="f453f-515">**Direction**</span></span>
- <span data-ttu-id="f453f-516">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f453f-517">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f453f-518">**도메인**</span><span class="sxs-lookup"><span data-stu-id="f453f-518">**Domain**</span></span>
- <span data-ttu-id="f453f-519">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="f453f-519">**Policy type**</span></span>
- <span data-ttu-id="f453f-520">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="f453f-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f453f-521">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-521">**Recipients**</span></span>

<span data-ttu-id="f453f-522">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="f453f-523">전자 메일 맬웨어 및 검색 기술별 \> 차트 분석으로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![위협 방지 상태 보고서의 맬웨어에 대한 검색 기술 보기](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="f453f-525">전자 메일 **맬웨어로 \> 데이터** 보기 및 검색 기술별 **차트** 분석 보기에서 차트에 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="f453f-526">**파일 검색:** 첨부 Safe <sup>\*</sup> 검색.</span><span class="sxs-lookup"><span data-stu-id="f453f-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="f453f-527">**파일 디버터 신뢰도:** 모든 악성 파일 신뢰도에서 Office 365 <sup>\*</sup> 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="f453f-528">**파일 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="f453f-528">**File reputation**</span></span>
- <span data-ttu-id="f453f-529">**맬웨어 방지 엔진:** <sup>\*</sup> 맬웨어 방지 엔진에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="f453f-530">**맬웨어** 방지 정책 파일 형식 블록: 메시지에 식별된 악성 파일의 유형으로 인해 필터링된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="f453f-531">**URL 악의적인 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="f453f-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="f453f-532">**URL 확인**</span><span class="sxs-lookup"><span data-stu-id="f453f-532">**URL detonation**</span></span>
- <span data-ttu-id="f453f-533">**URL 확인 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="f453f-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="f453f-534">**캠페인**</span><span class="sxs-lookup"><span data-stu-id="f453f-534">**Campaign**</span></span>

<span data-ttu-id="f453f-535">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f453f-536">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-536">**Date**</span></span>
- <span data-ttu-id="f453f-537">**제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-537">**Subject**</span></span>
- <span data-ttu-id="f453f-538">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-538">**Sender**</span></span>
- <span data-ttu-id="f453f-539">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-539">**Recipients**</span></span>
- <span data-ttu-id="f453f-540">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="f453f-540">**Detected by**</span></span>
- <span data-ttu-id="f453f-541">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="f453f-541">**Delivery Status**</span></span>
- <span data-ttu-id="f453f-542">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="f453f-542">**Source of Compromise**</span></span>
- <span data-ttu-id="f453f-543">**태그**</span><span class="sxs-lookup"><span data-stu-id="f453f-543">**Tags**</span></span>

<span data-ttu-id="f453f-544">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f453f-545">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-546">**감지**</span><span class="sxs-lookup"><span data-stu-id="f453f-546">**Detection**</span></span>
- <span data-ttu-id="f453f-547">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="f453f-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f453f-548">**방향**</span><span class="sxs-lookup"><span data-stu-id="f453f-548">**Direction**</span></span>
- <span data-ttu-id="f453f-549">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f453f-550">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f453f-551">**도메인**</span><span class="sxs-lookup"><span data-stu-id="f453f-551">**Domain**</span></span>
- <span data-ttu-id="f453f-552">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="f453f-552">**Policy type**</span></span>
- <span data-ttu-id="f453f-553">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="f453f-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f453f-554">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-554">**Recipients**</span></span>

<span data-ttu-id="f453f-555">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="f453f-556">정책 유형별 차트 분석 및 전자 메일 피싱 또는 전자 메일 맬웨어로 데이터 \> \> 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![위협 방지 상태 보고서의 피싱 전자 메일 또는 맬웨어 전자 메일에 대한 정책 유형 보기](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="f453f-558">정책 **유형별** 차트 분석 및 전자 메일 피싱 또는 전자 메일 맬웨어 보기로 데이터 보기에서 차트에 표시되는 정보는 다음과 같습니다. **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="f453f-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="f453f-559">**맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="f453f-559">**Anti-malware**</span></span>
- <span data-ttu-id="f453f-560">**Safe 첨부 파일**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f453f-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="f453f-561">**피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="f453f-561">**Anti-phish**</span></span>
- <span data-ttu-id="f453f-562">**스팸 방지**</span><span class="sxs-lookup"><span data-stu-id="f453f-562">**Anti-spam**</span></span>
- <span data-ttu-id="f453f-563">**메일 흐름 규칙(전송** 규칙으로도 알려지기)</span><span class="sxs-lookup"><span data-stu-id="f453f-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="f453f-564">**기타**</span><span class="sxs-lookup"><span data-stu-id="f453f-564">**Others**</span></span>

<span data-ttu-id="f453f-565">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f453f-566">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-566">**Date**</span></span>
- <span data-ttu-id="f453f-567">**제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-567">**Subject**</span></span>
- <span data-ttu-id="f453f-568">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-568">**Sender**</span></span>
- <span data-ttu-id="f453f-569">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-569">**Recipients**</span></span>
- <span data-ttu-id="f453f-570">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="f453f-570">**Detected by**</span></span>
- <span data-ttu-id="f453f-571">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="f453f-571">**Delivery Status**</span></span>
- <span data-ttu-id="f453f-572">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="f453f-572">**Source of Compromise**</span></span>
- <span data-ttu-id="f453f-573">**태그**</span><span class="sxs-lookup"><span data-stu-id="f453f-573">**Tags**</span></span>

<span data-ttu-id="f453f-574">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f453f-575">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-576">**감지**</span><span class="sxs-lookup"><span data-stu-id="f453f-576">**Detection**</span></span>
- <span data-ttu-id="f453f-577">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="f453f-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f453f-578">**방향**</span><span class="sxs-lookup"><span data-stu-id="f453f-578">**Direction**</span></span>
- <span data-ttu-id="f453f-579">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f453f-580">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f453f-581">**도메인**</span><span class="sxs-lookup"><span data-stu-id="f453f-581">**Domain**</span></span>
- <span data-ttu-id="f453f-582">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="f453f-582">**Policy type**</span></span>
- <span data-ttu-id="f453f-583">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="f453f-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f453f-584">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-584">**Recipients**</span></span>

<span data-ttu-id="f453f-585">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="f453f-586">배달 상태별 차트 분석 및 전자 메일 피싱 또는 전자 메일 맬웨어로 데이터 \> \> 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![위협 방지 상태 보고서의 피싱 전자 메일 및 맬웨어 전자 메일에 대한 배달 상태 보기](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="f453f-588">배달 **상태별** 차트 분석 및 전자 메일 피싱으로 데이터 **\> 보기** 또는 전자 메일 맬웨어 보기로 데이터 **\> 보기에서** 차트에 표시되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="f453f-589">**호스트된 사서함: 받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="f453f-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="f453f-590">**호스트된 사서함: 정크 메일함**</span><span class="sxs-lookup"><span data-stu-id="f453f-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="f453f-591">**호스트된 사서함: 사용자 지정 폴더**</span><span class="sxs-lookup"><span data-stu-id="f453f-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="f453f-592">**호스트된 사서함: 삭제된 항목**</span><span class="sxs-lookup"><span data-stu-id="f453f-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="f453f-593">**전달**</span><span class="sxs-lookup"><span data-stu-id="f453f-593">**Forwarded**</span></span>
- <span data-ttu-id="f453f-594">**On-premises server: Delivered**</span><span class="sxs-lookup"><span data-stu-id="f453f-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="f453f-595">**격리**</span><span class="sxs-lookup"><span data-stu-id="f453f-595">**Quarantine**</span></span>
- <span data-ttu-id="f453f-596">**배달 실패**</span><span class="sxs-lookup"><span data-stu-id="f453f-596">**Delivery failed**</span></span>
- <span data-ttu-id="f453f-597">**삭제**</span><span class="sxs-lookup"><span data-stu-id="f453f-597">**Dropped**</span></span>

<span data-ttu-id="f453f-598">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f453f-599">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-599">**Date**</span></span>
- <span data-ttu-id="f453f-600">**제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-600">**Subject**</span></span>
- <span data-ttu-id="f453f-601">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-601">**Sender**</span></span>
- <span data-ttu-id="f453f-602">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-602">**Recipients**</span></span>
- <span data-ttu-id="f453f-603">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="f453f-603">**Detected by**</span></span>
- <span data-ttu-id="f453f-604">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="f453f-604">**Delivery Status**</span></span>
- <span data-ttu-id="f453f-605">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="f453f-605">**Source of Compromise**</span></span>
- <span data-ttu-id="f453f-606">**태그**</span><span class="sxs-lookup"><span data-stu-id="f453f-606">**Tags**</span></span>

<span data-ttu-id="f453f-607">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f453f-608">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-609">**감지**</span><span class="sxs-lookup"><span data-stu-id="f453f-609">**Detection**</span></span>
- <span data-ttu-id="f453f-610">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="f453f-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f453f-611">**방향**</span><span class="sxs-lookup"><span data-stu-id="f453f-611">**Direction**</span></span>
- <span data-ttu-id="f453f-612">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f453f-613">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f453f-614">**도메인**</span><span class="sxs-lookup"><span data-stu-id="f453f-614">**Domain**</span></span>
- <span data-ttu-id="f453f-615">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="f453f-615">**Policy type**</span></span>
- <span data-ttu-id="f453f-616">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="f453f-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f453f-617">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-617">**Recipients**</span></span>

<span data-ttu-id="f453f-618">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="f453f-619">콘텐츠 맬웨어로 \> 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-619">View data by Content \> Malware</span></span>

![위협 방지 상태 보고서의 콘텐츠 맬웨어 보기](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="f453f-621">콘텐츠 **맬웨어로 \> 데이터** 보기 보기에서 조직의 Microsoft Defender에 대한 차트에 다음 Office 365 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="f453f-622">**맬웨어** 방지 엔진 : Sharepoint, OneDrive 및 에서 Microsoft Teams 기본 제공 바이러스 검색에 의해 검색된 악성 [Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="f453f-623">**파일 검색:** Safe, 파일 및 Safe 파일에서 검색된 악성 [SharePoint,](mdo-for-spo-odb-and-teams.md)OneDrive 및 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f453f-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="f453f-624">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f453f-625">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-626">**위치**</span><span class="sxs-lookup"><span data-stu-id="f453f-626">**Location**</span></span>
- <span data-ttu-id="f453f-627">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="f453f-627">**Detected by**</span></span>
- <span data-ttu-id="f453f-628">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="f453f-628">**Malware name**</span></span>

<span data-ttu-id="f453f-629">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f453f-630">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-631">**검색:** **맬웨어 방지 엔진** 또는 **파일 검색**</span><span class="sxs-lookup"><span data-stu-id="f453f-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="f453f-632">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="f453f-633">시스템 오버라이드로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-633">View data by System override</span></span>

![위협 방지 상태 보고서의 메시지 오버라이드 보기](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="f453f-635">시스템으로 데이터 **보기 override** 보기에서 다음과 같은 이유 정보가 차트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="f453f-636">**사내 건너뛰기**</span><span class="sxs-lookup"><span data-stu-id="f453f-636">**On-premises skip**</span></span>
- <span data-ttu-id="f453f-637">**IP 허용**</span><span class="sxs-lookup"><span data-stu-id="f453f-637">**IP allow**</span></span>
- <span data-ttu-id="f453f-638">**Exchange 전송 규칙(메일** 흐름 규칙)</span><span class="sxs-lookup"><span data-stu-id="f453f-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="f453f-639">**조직에서 허용된 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="f453f-640">**조직 허용 도메인**</span><span class="sxs-lookup"><span data-stu-id="f453f-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="f453f-641">**ZAP를 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="f453f-642">**정크 메일 폴더를 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="f453f-643">**사용자 Safe 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-643">**User Safe Sender**</span></span>
- <span data-ttu-id="f453f-644">**사용자 Safe 도메인**</span><span class="sxs-lookup"><span data-stu-id="f453f-644">**User Safe Domain**</span></span>

<span data-ttu-id="f453f-645">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f453f-646">**날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-646">**Date**</span></span>
- <span data-ttu-id="f453f-647">**제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-647">**Subject**</span></span>
- <span data-ttu-id="f453f-648">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-648">**Sender**</span></span>
- <span data-ttu-id="f453f-649">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-649">**Recipients**</span></span>
- <span data-ttu-id="f453f-650">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="f453f-650">**Detected by**</span></span>
- <span data-ttu-id="f453f-651">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="f453f-651">**Delivery Status**</span></span>
- <span data-ttu-id="f453f-652">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="f453f-652">**Source of Compromise**</span></span>
- <span data-ttu-id="f453f-653">**태그**</span><span class="sxs-lookup"><span data-stu-id="f453f-653">**Tags**</span></span>

<span data-ttu-id="f453f-654">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="f453f-655">**날짜(UTC)** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="f453f-656">**감지**</span><span class="sxs-lookup"><span data-stu-id="f453f-656">**Detection**</span></span>
- <span data-ttu-id="f453f-657">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="f453f-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="f453f-658">**방향**</span><span class="sxs-lookup"><span data-stu-id="f453f-658">**Direction**</span></span>
- <span data-ttu-id="f453f-659">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f453f-660">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="f453f-661">**도메인**</span><span class="sxs-lookup"><span data-stu-id="f453f-661">**Domain**</span></span>
- <span data-ttu-id="f453f-662">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="f453f-662">**Policy type**</span></span>
- <span data-ttu-id="f453f-663">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="f453f-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="f453f-664">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-664">**Recipients**</span></span>

<span data-ttu-id="f453f-665">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f453f-666"><sup>\*</sup>Defender for Office 365 전용</span><span class="sxs-lookup"><span data-stu-id="f453f-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="f453f-667">상위 맬웨어 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-667">Top malware report</span></span>

<span data-ttu-id="f453f-668">Top **malware report** shows the various kinds of malware that was detected by [anti-malware protection in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="f453f-669">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f453f-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-670">전자 메일 & **공동** 작업 보고서 페이지에서 상위 맬웨어를 찾은 다음 세부 정보  **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="f453f-671">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/TopMalware> 습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![전자 메일 및 공동 작업 & 페이지의 상위 맬웨어 위젯](../../media/top-malware-report-widget.png)

<span data-ttu-id="f453f-673">파이 차트에서 에지 위에 마우스를 대면 맬웨어의 종류 이름과 해당 맬웨어가 있는 것으로 감지된 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="f453f-674">상위 **맬웨어 보고서 페이지에는** 더 큰 버전의 파이 차트가 보고서 페이지에 표시됩니다. 차트 아래의 세부 정보 표에는 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="f453f-675">**상위 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="f453f-675">**Top malware**</span></span>
- <span data-ttu-id="f453f-676">**개수**</span><span class="sxs-lookup"><span data-stu-id="f453f-676">**Count**</span></span>

<span data-ttu-id="f453f-677">필터를 **클릭하면** 시작 날짜 및 종료 날짜로 날짜 범위를 **지정할** **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![상위 맬웨어 보고서 보기](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="f453f-679">URL 위협 방지 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-679">URL threat protection report</span></span>

<span data-ttu-id="f453f-680">**URL 위협 방지 보고서는** Microsoft Defender에서만 사용할 수 Office 365.</span><span class="sxs-lookup"><span data-stu-id="f453f-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f453f-681">자세한 내용은 [URL 위협 방지 보고서를 참조하세요.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="f453f-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="f453f-682">사용자가 보고한 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="f453f-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f453f-683">사용자가 보고한  메시지 보고서가 제대로 작동하려면 사용자 환경의 감사 로깅을 설정해야 Microsoft 365 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f453f-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="f453f-684">이 작업은 일반적으로 감사 로그 역할이 할당된 사용자가 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f453f-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="f453f-685">자세한 내용은 감사 로그 Microsoft 365 설정 또는 해제를 [참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="f453f-686">사용자 **보고** 메시지 보고서에는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 사용자가 [](enable-the-report-message-add-in.md) 정크 메일, 피싱 시도 또는 양호한 메일로 보고한 전자 메일 메시지에 대한 정보가 [표시됩니다.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="f453f-687">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f453f-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f453f-688">전자 메일 & **공동** 작업 보고서 페이지에서 사용자가 보고한 메시지를 **찾은** 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="f453f-689">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/userSubmissionReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="f453f-690">Microsoft 365 Defender 포털에서 관리 [제출으로 이동하려면 제출로](admin-submission.md) **이동을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![사용자가 전자 메일 및 공동 작업 보고서 페이지에서 & 위젯을 보고했습니다.](../../media/user-reported-messages-widget.png)

<span data-ttu-id="f453f-692">사용자가  보고한 메시지 페이지에서 필터를 클릭하고 플라이아웃에 나타나는  다음 값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f453f-693">**보고된 날짜:** **시작 시간** 및 **종료 시간**</span><span class="sxs-lookup"><span data-stu-id="f453f-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="f453f-694">**보고한**</span><span class="sxs-lookup"><span data-stu-id="f453f-694">**Reported by**</span></span>
- <span data-ttu-id="f453f-695">**전자 메일 제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-695">**Email subject**</span></span>
- <span data-ttu-id="f453f-696">**보고된 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="f453f-696">**Message reported ID**</span></span>
- <span data-ttu-id="f453f-697">**네트워크 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="f453f-697">**Network Message ID**</span></span>
- <span data-ttu-id="f453f-698">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-698">**Sender**</span></span>
- <span data-ttu-id="f453f-699">**보고된 이유**</span><span class="sxs-lookup"><span data-stu-id="f453f-699">**Reported reason**</span></span>
  - <span data-ttu-id="f453f-700">**정크 아님**</span><span class="sxs-lookup"><span data-stu-id="f453f-700">**Not junk**</span></span>
  - <span data-ttu-id="f453f-701">**피싱**</span><span class="sxs-lookup"><span data-stu-id="f453f-701">**Phish**</span></span>
  - <span data-ttu-id="f453f-702">**스팸**</span><span class="sxs-lookup"><span data-stu-id="f453f-702">**Spam**</span></span>
- <span data-ttu-id="f453f-703">**피싱 시뮬레이션:** **예** 또는 **아니요**</span><span class="sxs-lookup"><span data-stu-id="f453f-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="f453f-704">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f453f-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f453f-705">항목을 그룹화하려면 그룹을 **클릭하고** 드롭다운 목록에서 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="f453f-706">**없음**</span><span class="sxs-lookup"><span data-stu-id="f453f-706">**None**</span></span>
- <span data-ttu-id="f453f-707">**이유**</span><span class="sxs-lookup"><span data-stu-id="f453f-707">**Reason**</span></span>
- <span data-ttu-id="f453f-708">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-708">**Sender**</span></span>
- <span data-ttu-id="f453f-709">**보고한**</span><span class="sxs-lookup"><span data-stu-id="f453f-709">**Reported by**</span></span>
- <span data-ttu-id="f453f-710">**결과 다시 검색**</span><span class="sxs-lookup"><span data-stu-id="f453f-710">**Rescan result**</span></span>
- <span data-ttu-id="f453f-711">**피싱 시뮬레이션**</span><span class="sxs-lookup"><span data-stu-id="f453f-711">**Phish simulation**</span></span>

![사용자가 보고한 메시지 보고서](../../media/user-reported-messages-report.png)

<span data-ttu-id="f453f-713">그래프 아래의 세부 정보 표에서 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="f453f-714">**전자 메일 제목**</span><span class="sxs-lookup"><span data-stu-id="f453f-714">**Email subject**</span></span>
- <span data-ttu-id="f453f-715">**보고한**</span><span class="sxs-lookup"><span data-stu-id="f453f-715">**Reported by**</span></span>
- <span data-ttu-id="f453f-716">**보고된 날짜**</span><span class="sxs-lookup"><span data-stu-id="f453f-716">**Date reported**</span></span>
- <span data-ttu-id="f453f-717">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="f453f-717">**Sender**</span></span>
- <span data-ttu-id="f453f-718">**보고된 이유**</span><span class="sxs-lookup"><span data-stu-id="f453f-718">**Reported reason**</span></span>
- <span data-ttu-id="f453f-719">**결과 다시 검색**</span><span class="sxs-lookup"><span data-stu-id="f453f-719">**Rescan result**</span></span>
- <span data-ttu-id="f453f-720">**태그**</span><span class="sxs-lookup"><span data-stu-id="f453f-720">**Tags**</span></span>

<span data-ttu-id="f453f-721">분석을 위해 Microsoft에 메시지를 제출하려면 표에서 메시지 항목을 선택하고 분석을 위해 **Microsoft에** 제출을 클릭한 다음 드롭다운 목록에서 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="f453f-722">**정리 보고**</span><span class="sxs-lookup"><span data-stu-id="f453f-722">**Report clean**</span></span>
- <span data-ttu-id="f453f-723">**피싱 보고**</span><span class="sxs-lookup"><span data-stu-id="f453f-723">**Report phishing**</span></span>
- <span data-ttu-id="f453f-724">**맬웨어 보고**</span><span class="sxs-lookup"><span data-stu-id="f453f-724">**Report malware**</span></span>
- <span data-ttu-id="f453f-725">**스팸 보고**'</span><span class="sxs-lookup"><span data-stu-id="f453f-725">**Report spam**'</span></span>
- <span data-ttu-id="f453f-726">**조사** 트리거(Office 365)</span><span class="sxs-lookup"><span data-stu-id="f453f-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="f453f-727">이러한 보고서를 보는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="f453f-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="f453f-728">이 문서에 설명된 보고서를 보고 사용하려면 Microsoft 365 Defender 포털에서 다음 역할 그룹 중 하나에 Microsoft 365 Defender 합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="f453f-729">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="f453f-729">**Organization Management**</span></span>
- <span data-ttu-id="f453f-730">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="f453f-730">**Security Administrator**</span></span>
- <span data-ttu-id="f453f-731">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="f453f-731">**Security Reader**</span></span>
- <span data-ttu-id="f453f-732">**전역 읽기**</span><span class="sxs-lookup"><span data-stu-id="f453f-732">**Global Reader**</span></span>

<span data-ttu-id="f453f-733">자세한 내용은 Microsoft 365 Defender [포털의 사용 권한을 참조하세요.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f453f-734">**참고:** Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한과 Microsoft 365 Defender 포털의 다른  기능에 대한 사용 권한이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f453f-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f453f-735">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f453f-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="f453f-736">보고서에 데이터가 표시되지 않는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="f453f-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="f453f-737">보고서에 데이터가 없는 경우 정책이 올바르게 설정되어 있는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f453f-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="f453f-738">자세한 내용은 [위협으로부터 보호를 참조합니다.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="f453f-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f453f-739">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f453f-739">Related topics</span></span>

[<span data-ttu-id="f453f-740">EOP의 스팸 방지 및 맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="f453f-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="f453f-741">검색 포털의 스마트 보고서 및 Microsoft 365 Defender 정보</span><span class="sxs-lookup"><span data-stu-id="f453f-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f453f-742">사이트 포털에서 메일 흐름 Microsoft 365 Defender 보기</span><span class="sxs-lookup"><span data-stu-id="f453f-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="f453f-743">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f453f-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
