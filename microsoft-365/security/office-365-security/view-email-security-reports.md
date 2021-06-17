---
title: Microsoft 365 Defender 포털에서 전자 메일 보안 보고서 보기
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
description: 조직에 대한 전자 메일 보안 보고서를 찾아 사용하는 방법에 대해 자세히 알아보습니다. 전자 메일 보안 보고서는 Microsoft 365 Defender 포털에서 사용할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985306"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="44287-104">Microsoft 365 Defender 포털에서 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="44287-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="44287-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="44287-105">**Applies to**</span></span>
- [<span data-ttu-id="44287-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="44287-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="44287-107">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="44287-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="44287-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44287-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="44287-109">Microsoft 365의 스팸 방지, 맬웨어 방지 및 암호화 기능과 같은 전자 메일 보안 기능이 조직을 보호하는 방법을 볼 수 있도록 Microsoft 365 Defender 포털에서 다양한 보고서를 사용할 수 <https://security.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="44287-110">필요한 권한이 [](#what-permissions-are-needed-to-view-these-reports)있는 경우 보고서 전자 메일 및 공동 작업 전자 메일 공동  작업 전자 메일 & 공동 작업 보고서로 이동하여 Microsoft 365 Defender \>  \> **포털에서 & 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="44287-111">전자 메일 및 공동 작업 **& 페이지로** 직접 이동하기 위해 를 를 를 열 수 <https://security.microsoft.com/emailandcollabreport> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft & 365 Defender 포털의 전자 메일 공동 작업 보고서 페이지](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="44287-113">Email & collaboration **reports** 페이지의 일부 보고서에는 Office 365용 Microsoft Defender가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="44287-114">이러한 보고서에 대한 자세한 내용은 [Microsoft 365 Defender 포털에서 Office 365용 Defender 보고서 보기를 참조하세요.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="44287-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="44287-115">메일 흐름과 관련된 보고서는 이제 EAC(Exchange 관리 센터)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="44287-116">이러한 보고서에 대한 자세한 내용은 새 Exchange 관리 센터의 메일 흐름 [보고서를 참조하세요.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="44287-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="44287-117">손상된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="44287-118">이 보고서는 Exchange Online 사서함이 있는 Microsoft 365 조직에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="44287-119">독립 실행형 EOP(Exchange Online Protection) 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="44287-120">손상된 **사용자 보고서에는** 지난 7일 이내에  의심 또는 제한으로  표시된 사용자 계정 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="44287-121">이러한 상태 중 하나에 있는 계정이 문제가 발생하거나 손상될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="44287-122">자주 사용하는 경우 보고서를 사용하여 의심스러우거나 제한된 계정에서 스파이크 및 추세를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="44287-123">손상된 사용자에 대한 자세한 내용은 손상된 전자 메일 계정에 응답을 [참조하세요.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="44287-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![전자 메일 및 공동 작업 보고서 & 손상된 사용자 위젯](../../media/compromised-users-report-widget.png)

<span data-ttu-id="44287-125">집계 보기는 지난 90일간의 데이터를 표시하고 세부 정보 보기에는 지난 30일간의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="44287-126">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자 메일 &  공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="44287-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="44287-127">손상된 **사용자에서** 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="44287-128">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/CompromisedUsers> 습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="44287-129">세부 **정보** 보기를 클릭한 후 필터를 클릭하고 플라이아웃에 나타나는 다음 값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="44287-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="44287-130">**날짜(UTC)**: **시작 날짜 및** 종료 **날짜입니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="44287-131">**활동**:</span><span class="sxs-lookup"><span data-stu-id="44287-131">**Activity**:</span></span>
  - <span data-ttu-id="44287-132">**의심스러운**: 사용자 계정이 의심스러운 전자 메일을 보냈고 전자 메일을 보내지 못하도록 제한될 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="44287-133">**제한:** 사용자 계정은 의심스러운 패턴으로 인해 전자 메일을 보내지 못하도록 제한되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="44287-134">필터링이 끝나면 적용 또는 **취소를** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![손상된 사용자 보고서의 보고서 보기](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="44287-136">그래프 아래 표에서 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="44287-137">**만들기 시간**</span><span class="sxs-lookup"><span data-stu-id="44287-137">**Creation time**</span></span>
- <span data-ttu-id="44287-138">**사용자 ID**</span><span class="sxs-lookup"><span data-stu-id="44287-138">**User ID**</span></span>
- <span data-ttu-id="44287-139">**작업**</span><span class="sxs-lookup"><span data-stu-id="44287-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="44287-140">Exchange 전송 규칙 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-140">Exchange transport rule report</span></span>

<span data-ttu-id="44287-141">**Exchange 전송 규칙 보고서는** 메일 흐름 규칙(전송 규칙)이 조직에서 들어오는 메시지와 보내고 있는 메시지에 대한 영향을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="44287-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="44287-142">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자 메일 &  공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="44287-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="44287-143">**Exchange 전송 규칙에서** 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="44287-144">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/ETRRuleReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![전자 메일 및 공동 작업 보고서 & Exchange 전송 규칙 위젯](../../media/transport-rule-report-widget.png)

<span data-ttu-id="44287-146">세부 정보 **보기를 클릭하면** 다음 차트 및 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="44287-147">**Exchange 전송 규칙으로 데이터 보기** \> **방향별** 차트 분석: 이 차트는  메일  흐름 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지의 수를 보여 주는 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="44287-148">**Exchange 전송 규칙으로 데이터 보기** \> **심각도별** 차트 분석: 이 차트는 높은 심각도,  보통 심각도  및 낮은 심각도 메시지 수를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="44287-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="44287-149">심각도 수준을 규칙의 작업으로 설정할 수 있습니다(**심각도** 수준 또는 _SetAuditSeverity로_ 이 규칙 감사).</span><span class="sxs-lookup"><span data-stu-id="44287-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="44287-150">자세한 내용은 [Exchange Online의 메일 흐름 규칙 작업을 참조하세요.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="44287-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="44287-151">**DLP Exchange 전송 규칙으로 데이터 보기** \> **방향별** 차트 분석: 이 차트는  DLP(데이터 손실 방지) 메일 흐름 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지 수를 보여 주는 차트입니다. </span><span class="sxs-lookup"><span data-stu-id="44287-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="44287-152">**DLP Exchange 전송 규칙으로 데이터 보기** \> **심각도별** 차트 분석: 이 보기에는 DLP 메일 흐름 규칙의 영향을  받은 높은 심각도, 보통 심각도 및 낮은 심각도 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="44287-153">**Exchange 전송 규칙 선택으로** 데이터 보기 선택의 경우 그래프 아래의 세부 정보 표에 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="44287-154">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-154">**Date**</span></span>
- <span data-ttu-id="44287-155">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="44287-155">**Transport rule**</span></span>
- <span data-ttu-id="44287-156">**제목**</span><span class="sxs-lookup"><span data-stu-id="44287-156">**Subject**</span></span>
- <span data-ttu-id="44287-157">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="44287-157">**Sender address**</span></span>
- <span data-ttu-id="44287-158">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="44287-158">**Recipient address**</span></span>
- <span data-ttu-id="44287-159">**심각도**</span><span class="sxs-lookup"><span data-stu-id="44287-159">**Severity**</span></span>
- <span data-ttu-id="44287-160">**방향**</span><span class="sxs-lookup"><span data-stu-id="44287-160">**Direction**</span></span>

<span data-ttu-id="44287-161">**DLP Exchange** 전송 규칙 선택으로 데이터 보기의 경우 그래프 아래의 세부 정보 표에 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="44287-162">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-162">**Date**</span></span>
- <span data-ttu-id="44287-163">**DLP 정책**</span><span class="sxs-lookup"><span data-stu-id="44287-163">**DLP policy**</span></span>
- <span data-ttu-id="44287-164">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="44287-164">**Transport rule**</span></span>
- <span data-ttu-id="44287-165">**제목**</span><span class="sxs-lookup"><span data-stu-id="44287-165">**Subject**</span></span>
- <span data-ttu-id="44287-166">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="44287-166">**Sender address**</span></span>
- <span data-ttu-id="44287-167">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="44287-167">**Recipient address**</span></span>
- <span data-ttu-id="44287-168">**심각도**</span><span class="sxs-lookup"><span data-stu-id="44287-168">**Severity**</span></span>
- <span data-ttu-id="44287-169">**방향**</span><span class="sxs-lookup"><span data-stu-id="44287-169">**Direction**</span></span>

<span data-ttu-id="44287-170">필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="44287-171">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="44287-172">**방향:** **아웃바운드** 및 **인바운드**</span><span class="sxs-lookup"><span data-stu-id="44287-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="44287-173">**심각도:** **높은 심각도,** **보통 심각도** 및 **낮은 심각도**</span><span class="sxs-lookup"><span data-stu-id="44287-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Exchange 전송 규칙 보고서의 보고서 보기](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="44287-175">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-175">Mailflow status report</span></span>

<span data-ttu-id="44287-176">**메일 흐름** 상태 보고서는 수신 및 보낸 전자 메일, 스팸 검색, 맬웨어, "양호"로 식별된 전자 메일 및 에지에서 허용되거나 차단된 전자 메일에 대한 정보를 표시하는 스마트 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="44287-177">이 보고서는 에지 보호 정보를 포함하는 유일한 보고서로, EOP(Exchange Online Protection)에서 평가하기 위해 서비스에 허용되기 전에 차단되는 전자 메일의 수만 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="44287-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="44287-178">받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지가 아니라 5개의 다른 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="44287-179">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자 메일 &  공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="44287-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="44287-180">메일 **흐름 상태 요약에서** 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="44287-181">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/mailflowStatusReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![메일 흐름 상태 요약 위젯 전자 메일 & 공동 작업 보고서 페이지의](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="44287-183">메일 흐름 상태 보고서의 형식 보기</span><span class="sxs-lookup"><span data-stu-id="44287-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="44287-184">보고서를 열면 유형 **탭이** 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="44287-185">기본적으로 이 보기에는 차트와 다음 필터로 구성된 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="44287-186">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="44287-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="44287-187">**메일 방향**:</span><span class="sxs-lookup"><span data-stu-id="44287-187">**Mail direction**:</span></span>
  - <span data-ttu-id="44287-188">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="44287-188">**Inbound**</span></span>
  - <span data-ttu-id="44287-189">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="44287-189">**Outbound**</span></span>
  - <span data-ttu-id="44287-190">**Intra-org**: 이 개수는 테넌트 내의 메시지에 대한 수입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="44287-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="44287-191">보낸 사람 abc@domain.com 받는 사람 주소로 xyz@domain.com(인바운드 및 아웃바운드와 별도로 **계산)** </span><span class="sxs-lookup"><span data-stu-id="44287-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="44287-192">**유형:**</span><span class="sxs-lookup"><span data-stu-id="44287-192">**Type**:</span></span>
  - <span data-ttu-id="44287-193">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-193">**Good mail**</span></span>
  - <span data-ttu-id="44287-194">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="44287-194">**Malware**</span></span>
  - <span data-ttu-id="44287-195">**스팸**</span><span class="sxs-lookup"><span data-stu-id="44287-195">**Spam**</span></span>
  - <span data-ttu-id="44287-196">**에지 보호**</span><span class="sxs-lookup"><span data-stu-id="44287-196">**Edge protection**</span></span>
  - <span data-ttu-id="44287-197">**규칙 메시지**</span><span class="sxs-lookup"><span data-stu-id="44287-197">**Rule messages**</span></span>
  - <span data-ttu-id="44287-198">**피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-198">**Phishing email**</span></span>
- <span data-ttu-id="44287-199">**도메인**: **모두**</span><span class="sxs-lookup"><span data-stu-id="44287-199">**Domain**: **All**</span></span>

<span data-ttu-id="44287-200">차트는 종류 값으로 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="44287-201">필터를 클릭하거나 차트  범례에서 값을 클릭하여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="44287-202">데이터 테이블에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-202">The data table contains the following information:</span></span>

- <span data-ttu-id="44287-203">**방향**</span><span class="sxs-lookup"><span data-stu-id="44287-203">**Direction**</span></span>
- <span data-ttu-id="44287-204">**유형**</span><span class="sxs-lookup"><span data-stu-id="44287-204">**Type**</span></span>
- <span data-ttu-id="44287-205">**24시간**</span><span class="sxs-lookup"><span data-stu-id="44287-205">**24 hours**</span></span>
- <span data-ttu-id="44287-206">**3일**</span><span class="sxs-lookup"><span data-stu-id="44287-206">**3 days**</span></span>
- <span data-ttu-id="44287-207">**7일**</span><span class="sxs-lookup"><span data-stu-id="44287-207">**7 days**</span></span>
- <span data-ttu-id="44287-208">**15일**</span><span class="sxs-lookup"><span data-stu-id="44287-208">**15 days**</span></span>
- <span data-ttu-id="44287-209">**30일**</span><span class="sxs-lookup"><span data-stu-id="44287-209">**30 days**</span></span>

<span data-ttu-id="44287-210">자세한 내용을 **보려면 범주** 선택을 클릭하면 다음 값에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="44287-211">**피싱 전자 메일:** 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="44287-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="44287-212">**전자 메일의** 맬웨어: 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="44287-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="44287-213">**스팸 검색:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="44287-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="44287-214">**Edge 차단 스팸:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="44287-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="44287-215">형식 보기에서 내보내기</span><span class="sxs-lookup"><span data-stu-id="44287-215">Export from Type view</span></span>

<span data-ttu-id="44287-216">세부 정보 보기의 경우 하루 동안만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="44287-217">따라서 7일 동안 데이터를 내보내는 경우 7개 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="44287-218">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="44287-219">해당 일의 데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="44287-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![메일 흐름 상태 보고서에 보기 입력](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="44287-221">메일 흐름 상태 보고서의 방향 보기</span><span class="sxs-lookup"><span data-stu-id="44287-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="44287-222">방향 탭을 **클릭하면** 유형 보기의 동일한 기본 **필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="44287-223">차트는 방향 값으로 **구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="44287-224">필터를 클릭하거나 차트  범례에서 값을 클릭하여 이러한 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="44287-225">형식 보기의 **동일한 필터가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="44287-226">데이터 테이블에는 형식 보기와 동일한 **정보가** 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="44287-227">사용 가능한 선택 **항목** 및 동작에 대한 자세한 내용은 종류 보기와 **같습니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="44287-228">방향 보기에서 내보내기</span><span class="sxs-lookup"><span data-stu-id="44287-228">Export from Direction view</span></span>

<span data-ttu-id="44287-229">세부 정보 보기의 경우 하루 동안만 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="44287-230">따라서 7일 동안 데이터를 내보내는 경우 7개 내보내기 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="44287-231">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="44287-232">해당 일의 데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="44287-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![메일 흐름 상태 보고서의 방향 보기](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="44287-234">메일 흐름 상태 보고서의 유입경로 보기</span><span class="sxs-lookup"><span data-stu-id="44287-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="44287-235">**Funnel** 보기는 Microsoft의 전자 메일 위협 방지 기능이 조직에서 받는 전자 메일과 보내기 전자 메일을 필터링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="44287-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="44287-236">전체 전자 메일 수와 에지 보호, 맬웨어 방지, 피싱 방지, 스팸 방지 및 스푸핑 방지를 포함하여 구성된 위협 방지 기능이 이 수에 미치는 영향을 자세히 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="44287-237">**FUNNel** 탭을 클릭하면 기본적으로 이 보기에는 차트와 다음 필터로 구성된 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="44287-238">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="44287-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="44287-239">**방향**:</span><span class="sxs-lookup"><span data-stu-id="44287-239">**Direction**:</span></span>

  - <span data-ttu-id="44287-240">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="44287-240">**Inbound**</span></span>
  - <span data-ttu-id="44287-241">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="44287-241">**Outbound**</span></span>
  - <span data-ttu-id="44287-242">**Intra-org:** 이 개수는 테넌트 내에서 보낸 메시지에 대한 수입니다. 즉, 보낸 abc@domain.com 받는 사람 xyz@domain.com(인바운드 및 아웃바운드와는 별도로 계산)를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="44287-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="44287-243">집계 보기 및 데이터 테이블 보기는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="44287-244">필터를 **클릭하면** 차트와 데이터 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="44287-245">이 차트에는 다음별로 구성한 전자 메일 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="44287-246">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-246">**Total email**</span></span>
- <span data-ttu-id="44287-247">**Edge 보호 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-247">**Email after edge protection**</span></span>
- <span data-ttu-id="44287-248">**전송 후 전자 메일 규칙(메일** 흐름 규칙)</span><span class="sxs-lookup"><span data-stu-id="44287-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="44287-249">**맬웨어 방지, 파일 신뢰도, 파일 형식 차단 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="44287-250">**피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="44287-251">**스팸 방지, 대량 메일 필터링 후 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="44287-252">**사용자 및 도메인 가장 후 전자 메일**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="44287-253">**파일 및 URL 확인 후 전자 메일**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="44287-254">**배달 후 보호 후 무해한 것으로 감지된 전자 메일(URL 클릭 시간 보호)**</span><span class="sxs-lookup"><span data-stu-id="44287-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="44287-255"><sup>\*</sup>Defender for Office 365 전용</span><span class="sxs-lookup"><span data-stu-id="44287-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="44287-256">EOP 또는 Defender에서 필터링한 전자 메일을 개별적으로 Office 365 차트 범례의 값을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="44287-257">데이터 테이블에는 내선 날짜 순서로 표시되는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="44287-258">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-258">**Date**</span></span>
- <span data-ttu-id="44287-259">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-259">**Total email**</span></span>
- <span data-ttu-id="44287-260">**에지 보호**</span><span class="sxs-lookup"><span data-stu-id="44287-260">**Edge protection**</span></span>
- <span data-ttu-id="44287-261">**맬웨어 방지, 파일 신뢰도, 파일 형식 블록**:</span><span class="sxs-lookup"><span data-stu-id="44287-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="44287-262">**파일 신뢰도:** 다른 Microsoft 고객이 첨부한 파일을 식별하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="44287-263">**파일 형식 블록:** 메시지에 식별된 악성 파일의 유형으로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="44287-264">**피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지**:</span><span class="sxs-lookup"><span data-stu-id="44287-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="44287-265">**URL 신뢰도:** 다른 Microsoft 고객이 URL을 식별하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="44287-266">**브랜드 가장:** 보낸 사람으로 가장하는 잘 알려진 브랜드에서 보낸 메시지로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="44287-267">**스푸핑** 방지: 받는 사람이 속한 도메인 또는 메시지 보낸 사람이 소유하지 않은 도메인을 스푸핑하려고 시도하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="44287-268">**스팸 방지, 대량 메일 필터링**:</span><span class="sxs-lookup"><span data-stu-id="44287-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="44287-269">**대량 메일 필터링:** 스팸 방지 정책의 BCL(대량 불만 수준) 임계값을 기준으로 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="44287-270">**사용자 및 도메인 가장(사용자** 및 도메인 Office 365) :</span><span class="sxs-lookup"><span data-stu-id="44287-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="44287-271">**사용자 가장:** 피싱 방지 정책의 가장 보호 설정에 정의된 사용자(메시지 보낸 사람)를 가장하려는 시도로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="44287-272">**도메인 가장:** 피싱 방지 정책의 가장 보호 설정에 정의된 도메인을 가장하려고 시도하여 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="44287-273">**파일 및 URL 확인(Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="44287-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="44287-274">**파일 검색:** 첨부 파일 Safe 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="44287-275">**URL 검색:** 링크 정책에 의해 Safe 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="44287-276">**사후 배달 보호 및 ZAP(ATP) 또는 EOP(ZAP)**: 맬웨어, 스팸 및 피싱에 대한 ZAP(제로 아워 자동 제거)입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="44287-277">데이터 테이블에서 행을 선택하면 플라이아웃에 전자 메일 수의 추가 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="44287-278">펀들 보기에서 내보내기</span><span class="sxs-lookup"><span data-stu-id="44287-278">Export from Funnel view</span></span>

<span data-ttu-id="44287-279">옵션에서 **내보내기** 를 **클릭한** 후 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="44287-280">**요약(최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="44287-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="44287-281">**세부 정보(지난 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="44287-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="44287-282">**날짜에서** 범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="44287-283">현재 필터에 대한 데이터는 파일로 .csv 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="44287-284">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="44287-285">데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="44287-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![메일 흐름 상태 보고서의 유입경로 보기](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="44287-287">메일 흐름 상태 보고서의 기술 보기</span><span class="sxs-lookup"><span data-stu-id="44287-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="44287-288">기술 **보기는** **Funnel** 보기와 유사하여 구성된 위협 방지 기능에 대해 보다 세부적인 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="44287-289">차트에서 다양한 위협 방지 단계에서 메시지를 분류하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="44287-290">기술 보기  탭을 클릭하면 기본적으로 이 보기에는 차트와 다음 필터로 구성된 데이터 테이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="44287-291">**날짜:** 지난 7일</span><span class="sxs-lookup"><span data-stu-id="44287-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="44287-292">**방향**:</span><span class="sxs-lookup"><span data-stu-id="44287-292">**Direction**:</span></span>

  - <span data-ttu-id="44287-293">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="44287-293">**Inbound**</span></span>
  - <span data-ttu-id="44287-294">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="44287-294">**Outbound**</span></span>
  - <span data-ttu-id="44287-295">**Intra-org**: 이 개수는 테넌트 내의 메시지에 대한 수입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="44287-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="44287-296">보낸 사람 abc@domain.com 받는 사람 주소로 xyz@domain.com(인바운드 및 아웃바운드와 별도로 계산)</span><span class="sxs-lookup"><span data-stu-id="44287-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="44287-297">집계 보기 및 데이터 테이블 보기는 90일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="44287-298">필터를 **클릭하면** 차트와 데이터 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="44287-299">이 차트에는 다음 범주로 구성된 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="44287-300">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-300">**Total email**</span></span>
- <span data-ttu-id="44287-301">**Edge 허용** 및 **Edge 필터링**</span><span class="sxs-lookup"><span data-stu-id="44287-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="44287-302">**전송 규칙 허용** 및 **전송 규칙 필터링(메일** 흐름 규칙)</span><span class="sxs-lookup"><span data-stu-id="44287-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="44287-303">**맬웨어가** 아닌 경우 **Safe 검색** <sup>\*</sup> 및 맬웨어 방지 엔진 **검색**</span><span class="sxs-lookup"><span data-stu-id="44287-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="44287-304">**피싱이 아닌** 경우,  **DMARC 실패,** 가장 <sup>\*</sup> 검색, **스푸핑 검색** 및 **피싱 감지**</span><span class="sxs-lookup"><span data-stu-id="44287-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="44287-305">**URL 검색 및 URL** 검색을 통해 검색 **안 하세요.**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="44287-306">**스팸 및**  **스팸 아미기**</span><span class="sxs-lookup"><span data-stu-id="44287-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="44287-307">**악성이 아닌 전자** **메일, Safe 링크** 검색 및 <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="44287-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="44287-308"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="44287-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="44287-309">차트의 범주 위에 마우스를 대면 해당 범주의 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="44287-310">데이터 테이블에는 내선 날짜 순서로 표시되는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="44287-311">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-311">**Date**</span></span>
- <span data-ttu-id="44287-312">**총 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="44287-312">**Total email**</span></span>
- <span data-ttu-id="44287-313">**Edge 필터링**</span><span class="sxs-lookup"><span data-stu-id="44287-313">**Edge filtered**</span></span>
- <span data-ttu-id="44287-314">**규칙 메시지:** 메일 흐름 규칙(전송 규칙)으로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="44287-315">**맬웨어 방지 엔진**, **Safe 첨부 파일** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="44287-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="44287-316">**DMARC, 가장,** <sup>\*</sup> **스푸핑,** **피싱 필터링 :**</span><span class="sxs-lookup"><span data-stu-id="44287-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="44287-317">**DMARC: DMARC** 인증 검사에 실패한 메시지로 인해 필터링된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="44287-318">**URL 검색**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="44287-319">**스팸 방지 필터링**</span><span class="sxs-lookup"><span data-stu-id="44287-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="44287-320">**ZAP 제거됨**</span><span class="sxs-lookup"><span data-stu-id="44287-320">**ZAP removed**</span></span>
- <span data-ttu-id="44287-321">**링크로 Safe 검색**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="44287-322"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="44287-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="44287-323">데이터 테이블에서 행을 선택하면 플라이아웃에 전자 메일 수의 추가 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="44287-324">기술 보기에서 내보내기</span><span class="sxs-lookup"><span data-stu-id="44287-324">Export from Tech view</span></span>

<span data-ttu-id="44287-325">내보내기 **를 클릭할** 때 **옵션에서** 다음 값 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="44287-326">**요약(최근 90일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="44287-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="44287-327">**세부 정보(지난 30일 동안의 데이터 사용)**</span><span class="sxs-lookup"><span data-stu-id="44287-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="44287-328">**날짜에서** 범위를 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="44287-329">현재 필터에 대한 데이터는 파일로 .csv 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="44287-330">내보낼 각 .csv 행은 150,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="44287-331">데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="44287-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![메일 흐름 상태 보고서의 기술 보기](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="44287-333">맬웨어 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-333">Malware detections report</span></span>

<span data-ttu-id="44287-334">맬웨어 검색 보고서 **보고서는** 들어오는 전자 메일 메시지와 보내기 전자 메일 메시지의 맬웨어 검색에 대한 정보를 Exchange Online Protection EOP에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="44287-335">EOP의 맬웨어 보호에 대한 자세한 내용은 [EOP의 맬웨어 방지 보호를 참조하세요.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="44287-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="44287-336">집계 보기 필터는 90일 동안 허용되는 반면 세부 정보 테이블 필터는 10일 동안만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="44287-337">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="44287-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="44287-338">전자 **메일에서 검색된 맬웨어에서** 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="44287-339">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/MalwareDetections> 습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![전자 메일 및 공동 작업 보고서 페이지의 전자 메일 위젯에서 & 검색](../../media/malware-detections-widget.png)

<span data-ttu-id="44287-341">세부 **정보** 보기를 클릭한 후 필터를 클릭하고 다음을  선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="44287-342">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-343">**방향:** **인바운드 및** **아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="44287-343">**Direction**: **Inbound** and **Outbound**</span></span>

![전자 메일 보고서의 맬웨어 검색에서 보고서 보기](../../media/malware-detections-report-view.png)

<span data-ttu-id="44287-345">그래프 아래의 세부 정보 표에서 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="44287-346">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-346">**Date**</span></span>
- <span data-ttu-id="44287-347">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="44287-347">**Sender address**</span></span>
- <span data-ttu-id="44287-348">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="44287-348">**Recipient address**</span></span>
- <span data-ttu-id="44287-349">**메시지 ID:** 메시지 헤더의 **Message-ID** 헤더 필드에서 사용할 수 있으며 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="44287-350">값을 예로 들 수 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 있습니다(괄호 참고).</span><span class="sxs-lookup"><span data-stu-id="44287-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="44287-351">**제목**</span><span class="sxs-lookup"><span data-stu-id="44287-351">**Subject**</span></span>
- <span data-ttu-id="44287-352">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="44287-352">**Filename**</span></span>
- <span data-ttu-id="44287-353">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="44287-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="44287-354">메일 대기 시간 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-354">Mail latency report</span></span>

<span data-ttu-id="44287-355">**Defender** for Office 365 메일 대기 시간 보고서에는 조직 내에서 경험하는 메일 배달 및 확인 대기 시간에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="44287-356">자세한 내용은 메일 대기 [시간 보고서를 참조하세요.](view-reports-for-mdo.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="44287-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="44287-357">스팸 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="44287-358">스팸 **검색 보고서는** 2021년 6월 30일에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="44287-359">위협 방지 상태 보고서에서 동일한 [정보를 사용할 수 있습니다.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="44287-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="44287-360">스푸핑 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="44287-361">이 문서에 설명된 향상된 스푸핑 검색 보고서는 미리 보기에 있으며 변경될 수 있으며 일부 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="44287-362">이전 버전의 보고서에는 양호한 **메일과** 스팸으로 **걸려 오기만 표시되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="44287-363">**스푸핑 검색 보고서에는** 스푸핑으로 인해 차단되거나 허용된 메시지에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="44287-364">스푸핑에 대한 자세한 내용은 [EOP의 스푸핑 방지 보호를 참조하세요.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="44287-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="44287-365">보고서의 집계 보기는 45일 동안 필터링할 수 있는 반면 세부 정보 보기는 <sup>\*</sup> 10일의 필터링만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="44287-366"><sup>\*</sup> 결국 최대 90일의 필터링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="44287-367">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="44287-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="44287-368">**스푸핑 검색에서** 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="44287-369">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/SpoofMailReportV2> 습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![전자 메일 및 공동 작업 보고서 페이지의 & 위젯 스푸핑](../../media/spoof-detections-widget.png)

<span data-ttu-id="44287-371">차트에서 하루(데이터 데이터 포인트)에 마우스를 대면 검색된 스푸핑된 메시지 수와 그 이유를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="44287-372">세부 **정보** 보기를 클릭한 후 필터를 클릭하고 다음 값  중 하나 이상을 선택하여 차트와 세부 정보 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="44287-373">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-374">**결과**:</span><span class="sxs-lookup"><span data-stu-id="44287-374">**Result**:</span></span>
  - <span data-ttu-id="44287-375">**통과**</span><span class="sxs-lookup"><span data-stu-id="44287-375">**Pass**</span></span>
  - <span data-ttu-id="44287-376">**실패**</span><span class="sxs-lookup"><span data-stu-id="44287-376">**Fail**</span></span>
  - <span data-ttu-id="44287-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="44287-377">**SoftPass**</span></span>
  - <span data-ttu-id="44287-378">**없음**</span><span class="sxs-lookup"><span data-stu-id="44287-378">**None**</span></span>
  - <span data-ttu-id="44287-379">**기타**</span><span class="sxs-lookup"><span data-stu-id="44287-379">**Other**</span></span>
- <span data-ttu-id="44287-380">**스푸핑 유형:** **내부 및** **외부**</span><span class="sxs-lookup"><span data-stu-id="44287-380">**Spoof type**: **Internal** and **External**</span></span>

![사이트 포털의 스푸핑 메일 보고서 Microsoft 365 Defender 페이지](../../media/spoof-detections-report-page.png)

<span data-ttu-id="44287-382">그래프 아래 표에서 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="44287-383">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-383">**Date**</span></span>
- <span data-ttu-id="44287-384">**스푸핑된 사용자**</span><span class="sxs-lookup"><span data-stu-id="44287-384">**Spoofed user**</span></span>
- <span data-ttu-id="44287-385">**인프라 보내기**</span><span class="sxs-lookup"><span data-stu-id="44287-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="44287-386">**스푸핑 유형**</span><span class="sxs-lookup"><span data-stu-id="44287-386">**Spoof type**</span></span>
- <span data-ttu-id="44287-387">**결과**</span><span class="sxs-lookup"><span data-stu-id="44287-387">**Result**</span></span>
- <span data-ttu-id="44287-388">**결과 코드**</span><span class="sxs-lookup"><span data-stu-id="44287-388">**Result code**</span></span>
- <span data-ttu-id="44287-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="44287-389">**SPF**</span></span>
- <span data-ttu-id="44287-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="44287-390">**DKIM**</span></span>
- <span data-ttu-id="44287-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="44287-391">**DMARC**</span></span>
- <span data-ttu-id="44287-392">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="44287-392">**Message count**</span></span>

<span data-ttu-id="44287-393">복합 인증 결과 코드에 대한 자세한 내용은 에서 스팸 방지 메시지 [헤더를 Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="44287-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="44287-394">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-394">Threat protection status report</span></span>

<span data-ttu-id="44287-395">**위협 방지 상태 보고서는** EOP 및 Defender에서 모두 사용할 수 Office 365. 그러나 보고서에는 다른 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="44287-396">예를 들어 EOP 고객은 전자 메일에서 검색된 맬웨어에 대한 정보를 볼 수 있지만, 전자 메일, Safe 및 에 대한 첨부 파일에서 검색된 악성 파일에 대한 SharePoint, OneDrive [Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="44287-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="44287-397">이 보고서는 맬웨어 방지 엔진에 의해 차단된 파일 또는 웹 사이트 주소(URL), [ZAP(제로](zero-hour-auto-purge.md)아워 자동 제거) 및 피싱 방지 정책의 Safe [링크,](safe-links.md) [](safe-attachments.md)Safe 첨부 파일 및 가장 보호 기능과 같은 Office 365 기능에 대한 Defender와 같은 악성 콘텐츠가 있는 전자 메일 메시지 수를 [제공합니다.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="44287-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="44287-398">이 정보를 사용하여 추세를 식별하거나 조직 정책에 조정이 필요한지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="44287-399">**참고:** 받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지가 아니라 5개의 다른 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="44287-400">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="44287-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="44287-401">위협 **방지 상태의** 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="44287-402">보고서로 직접 이동하기 위해 다음 URL 중 하나를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="44287-403">Defender for Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="44287-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="44287-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="44287-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![전자 메일 및 공동 작업 보고서 & 위협 방지 상태 위젯](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="44287-406">기본적으로 세부 정보 보기를 클릭하면 차트에 지난 7일간의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="44287-407">필터를 **클릭하면** 90일 날짜 범위를 선택할 수 있습니다(평가판 구독은 30일로 제한될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="44287-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="44287-408">세부 정보 표에서는 30일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="44287-409">다음 섹션에서는 사용 가능한 보기에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="44287-410">개요로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="44287-410">View data by Overview</span></span>

![위협 방지 상태 보고서의 개요 보기](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="44287-412">개요로 **데이터** 보기 보기에서 차트에 다음과 같은 검색 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="44287-413">**전자 메일 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="44287-413">**Email malware**</span></span>
- <span data-ttu-id="44287-414">**전자 메일 피싱**</span><span class="sxs-lookup"><span data-stu-id="44287-414">**Email phish**</span></span>
- <span data-ttu-id="44287-415">**콘텐츠 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="44287-415">**Content malware**</span></span>

<span data-ttu-id="44287-416">차트 아래에 세부 정보 표를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-416">No details table is available below the chart.</span></span>

<span data-ttu-id="44287-417">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="44287-418">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-419">**검색:** **전자 메일 맬웨어,** **전자 메일 피싱** 또는 **콘텐츠 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="44287-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="44287-420">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="44287-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="44287-421">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="44287-422">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="44287-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="44287-423">**방향**</span><span class="sxs-lookup"><span data-stu-id="44287-423">**Direction**</span></span>
- <span data-ttu-id="44287-424">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44287-424">**Domain**</span></span>
- <span data-ttu-id="44287-425">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="44287-425">**Policy type**</span></span>

<span data-ttu-id="44287-426">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="44287-427">검색 기술별 전자 메일 피싱 및 차트 \> 분석으로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="44287-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![위협 방지 상태 보고서의 피싱 전자 메일에 대한 검색 기술 보기](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="44287-429">전자 메일 **피싱으로 데이터 \> 보기** **및** 검색 기술별 차트 분석 보기에서 차트에 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="44287-430">**URL 악의적인 신뢰도:** 다른 Office 365 고객에 대한 <sup>\*</sup> 악의적인 URL 신뢰도 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44287-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="44287-431">**고급 필터:** 기계 학습을 기반으로 하는 피싱 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="44287-432">**일반 필터:** 분석가 규칙에 기반한 피싱 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="44287-433">**스푸핑된** 도메인: 보낸 사람이 받는 사람 도메인을 스푸핑하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="44287-434">**스푸핑 외부** 도메인: 보낸 사람이 다른 도메인을 스푸핑하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="44287-435">**스푸핑 DMARC:** 메시지에 대한 DMARC 인증 실패.</span><span class="sxs-lookup"><span data-stu-id="44287-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="44287-436">**가장 브랜드:** 보낸 사람 기반의 잘 알려진 브랜드 가장.</span><span class="sxs-lookup"><span data-stu-id="44287-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="44287-437">**혼합 분석 검색**</span><span class="sxs-lookup"><span data-stu-id="44287-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="44287-438">**파일 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="44287-438">**File reputation**</span></span>
- <span data-ttu-id="44287-439">**지문 일치**</span><span class="sxs-lookup"><span data-stu-id="44287-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="44287-440">**URL 확인 신뢰도**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="44287-441">**URL 확인**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="44287-442">**가장 사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="44287-443">**가장 도메인:** 고객이 소유하거나 정의하는 도메인의 <sup>\*</sup> 가장입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="44287-444">**사서함 인텔리전스 가장:** 관리자가 정의하거나 사서함 인텔리전스를 통해 학습한 사용자의 <sup>\*</sup> 가장입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="44287-445">**파일 Detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="44287-446">**캠페인**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="44287-447">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="44287-448">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-448">**Date**</span></span>
- <span data-ttu-id="44287-449">**제목**</span><span class="sxs-lookup"><span data-stu-id="44287-449">**Subject**</span></span>
- <span data-ttu-id="44287-450">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-450">**Sender**</span></span>
- <span data-ttu-id="44287-451">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-451">**Recipients**</span></span>
- <span data-ttu-id="44287-452">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="44287-452">**Detected by**</span></span>
- <span data-ttu-id="44287-453">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="44287-453">**Delivery Status**</span></span>
- <span data-ttu-id="44287-454">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="44287-454">**Source of Compromise**</span></span>
- <span data-ttu-id="44287-455">**태그**</span><span class="sxs-lookup"><span data-stu-id="44287-455">**Tags**</span></span>

<span data-ttu-id="44287-456">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="44287-457">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-458">**감지**</span><span class="sxs-lookup"><span data-stu-id="44287-458">**Detection**</span></span>
- <span data-ttu-id="44287-459">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="44287-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="44287-460">**방향**</span><span class="sxs-lookup"><span data-stu-id="44287-460">**Direction**</span></span>
- <span data-ttu-id="44287-461">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="44287-462">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="44287-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="44287-463">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44287-463">**Domain**</span></span>
- <span data-ttu-id="44287-464">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="44287-464">**Policy type**</span></span>
- <span data-ttu-id="44287-465">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="44287-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="44287-466">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-466">**Recipients**</span></span>

<span data-ttu-id="44287-467">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="44287-468">전자 메일 맬웨어 및 검색 기술별 \> 차트 분석으로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="44287-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![위협 방지 상태 보고서의 맬웨어에 대한 검색 기술 보기](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="44287-470">전자 메일 **맬웨어로 \> 데이터** 보기 및 검색 기술별 **차트** 분석 보기에서 차트에 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="44287-471">**파일 검색:** 첨부 Safe <sup>\*</sup> 검색.</span><span class="sxs-lookup"><span data-stu-id="44287-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="44287-472">**파일 디버터 신뢰도:** 모든 악성 파일 신뢰도에서 Office 365 <sup>\*</sup> 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="44287-473">**파일 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="44287-473">**File reputation**</span></span>
- <span data-ttu-id="44287-474">**맬웨어 방지 엔진:** <sup>\*</sup> 맬웨어 방지 엔진에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="44287-475">**맬웨어** 방지 정책 파일 형식 블록: 메시지에 식별된 악성 파일의 유형으로 인해 필터링된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="44287-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="44287-476">**URL 악의적인 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="44287-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="44287-477">**URL 확인**</span><span class="sxs-lookup"><span data-stu-id="44287-477">**URL detonation**</span></span>
- <span data-ttu-id="44287-478">**URL 확인 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="44287-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="44287-479">**캠페인**</span><span class="sxs-lookup"><span data-stu-id="44287-479">**Campaign**</span></span>

<span data-ttu-id="44287-480">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="44287-481">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-481">**Date**</span></span>
- <span data-ttu-id="44287-482">**제목**</span><span class="sxs-lookup"><span data-stu-id="44287-482">**Subject**</span></span>
- <span data-ttu-id="44287-483">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-483">**Sender**</span></span>
- <span data-ttu-id="44287-484">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-484">**Recipients**</span></span>
- <span data-ttu-id="44287-485">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="44287-485">**Detected by**</span></span>
- <span data-ttu-id="44287-486">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="44287-486">**Delivery Status**</span></span>
- <span data-ttu-id="44287-487">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="44287-487">**Source of Compromise**</span></span>
- <span data-ttu-id="44287-488">**태그**</span><span class="sxs-lookup"><span data-stu-id="44287-488">**Tags**</span></span>

<span data-ttu-id="44287-489">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="44287-490">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-491">**감지**</span><span class="sxs-lookup"><span data-stu-id="44287-491">**Detection**</span></span>
- <span data-ttu-id="44287-492">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="44287-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="44287-493">**방향**</span><span class="sxs-lookup"><span data-stu-id="44287-493">**Direction**</span></span>
- <span data-ttu-id="44287-494">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="44287-495">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="44287-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="44287-496">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44287-496">**Domain**</span></span>
- <span data-ttu-id="44287-497">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="44287-497">**Policy type**</span></span>
- <span data-ttu-id="44287-498">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="44287-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="44287-499">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-499">**Recipients**</span></span>

<span data-ttu-id="44287-500">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="44287-501">정책 유형별 차트 분석 및 전자 메일 피싱 또는 전자 메일 맬웨어로 데이터 \> \> 보기</span><span class="sxs-lookup"><span data-stu-id="44287-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![위협 방지 상태 보고서의 피싱 전자 메일 또는 맬웨어 전자 메일에 대한 정책 유형 보기](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="44287-503">정책 **유형별** 차트 분석 및 전자 메일 피싱 또는 전자 메일 맬웨어 보기로 데이터 보기에서 차트에 표시되는 정보는 다음과 같습니다. **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="44287-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="44287-504">**맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="44287-504">**Anti-malware**</span></span>
- <span data-ttu-id="44287-505">**Safe 첨부 파일**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44287-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="44287-506">**피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="44287-506">**Anti-phish**</span></span>
- <span data-ttu-id="44287-507">**스팸 방지**</span><span class="sxs-lookup"><span data-stu-id="44287-507">**Anti-spam**</span></span>
- <span data-ttu-id="44287-508">**메일 흐름 규칙(전송** 규칙으로도 알려지기)</span><span class="sxs-lookup"><span data-stu-id="44287-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="44287-509">**기타**</span><span class="sxs-lookup"><span data-stu-id="44287-509">**Others**</span></span>

<span data-ttu-id="44287-510">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="44287-511">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-511">**Date**</span></span>
- <span data-ttu-id="44287-512">**제목**</span><span class="sxs-lookup"><span data-stu-id="44287-512">**Subject**</span></span>
- <span data-ttu-id="44287-513">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-513">**Sender**</span></span>
- <span data-ttu-id="44287-514">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-514">**Recipients**</span></span>
- <span data-ttu-id="44287-515">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="44287-515">**Detected by**</span></span>
- <span data-ttu-id="44287-516">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="44287-516">**Delivery Status**</span></span>
- <span data-ttu-id="44287-517">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="44287-517">**Source of Compromise**</span></span>
- <span data-ttu-id="44287-518">**태그**</span><span class="sxs-lookup"><span data-stu-id="44287-518">**Tags**</span></span>

<span data-ttu-id="44287-519">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="44287-520">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-521">**감지**</span><span class="sxs-lookup"><span data-stu-id="44287-521">**Detection**</span></span>
- <span data-ttu-id="44287-522">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="44287-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="44287-523">**방향**</span><span class="sxs-lookup"><span data-stu-id="44287-523">**Direction**</span></span>
- <span data-ttu-id="44287-524">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="44287-525">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="44287-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="44287-526">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44287-526">**Domain**</span></span>
- <span data-ttu-id="44287-527">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="44287-527">**Policy type**</span></span>
- <span data-ttu-id="44287-528">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="44287-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="44287-529">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-529">**Recipients**</span></span>

<span data-ttu-id="44287-530">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="44287-531">배달 상태별 차트 분석 및 전자 메일 피싱 또는 전자 메일 맬웨어로 데이터 \> \> 보기</span><span class="sxs-lookup"><span data-stu-id="44287-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![위협 방지 상태 보고서의 피싱 전자 메일 및 맬웨어 전자 메일에 대한 배달 상태 보기](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="44287-533">배달 **상태별** 차트 분석 및 전자 메일 피싱으로 데이터 **\> 보기** 또는 전자 메일 맬웨어 보기로 데이터 **\> 보기에서** 차트에 표시되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="44287-534">**호스트된 사서함: 받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="44287-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="44287-535">**호스트된 사서함: 정크 메일함**</span><span class="sxs-lookup"><span data-stu-id="44287-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="44287-536">**호스트된 사서함: 사용자 지정 폴더**</span><span class="sxs-lookup"><span data-stu-id="44287-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="44287-537">**호스트된 사서함: 삭제된 항목**</span><span class="sxs-lookup"><span data-stu-id="44287-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="44287-538">**전달**</span><span class="sxs-lookup"><span data-stu-id="44287-538">**Forwarded**</span></span>
- <span data-ttu-id="44287-539">**On-premises server: Delivered**</span><span class="sxs-lookup"><span data-stu-id="44287-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="44287-540">**격리**</span><span class="sxs-lookup"><span data-stu-id="44287-540">**Quarantine**</span></span>
- <span data-ttu-id="44287-541">**배달 실패**</span><span class="sxs-lookup"><span data-stu-id="44287-541">**Delivery failed**</span></span>
- <span data-ttu-id="44287-542">**삭제**</span><span class="sxs-lookup"><span data-stu-id="44287-542">**Dropped**</span></span>

<span data-ttu-id="44287-543">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="44287-544">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-544">**Date**</span></span>
- <span data-ttu-id="44287-545">**제목**</span><span class="sxs-lookup"><span data-stu-id="44287-545">**Subject**</span></span>
- <span data-ttu-id="44287-546">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-546">**Sender**</span></span>
- <span data-ttu-id="44287-547">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-547">**Recipients**</span></span>
- <span data-ttu-id="44287-548">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="44287-548">**Detected by**</span></span>
- <span data-ttu-id="44287-549">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="44287-549">**Delivery Status**</span></span>
- <span data-ttu-id="44287-550">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="44287-550">**Source of Compromise**</span></span>
- <span data-ttu-id="44287-551">**태그**</span><span class="sxs-lookup"><span data-stu-id="44287-551">**Tags**</span></span>

<span data-ttu-id="44287-552">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="44287-553">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-554">**감지**</span><span class="sxs-lookup"><span data-stu-id="44287-554">**Detection**</span></span>
- <span data-ttu-id="44287-555">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="44287-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="44287-556">**방향**</span><span class="sxs-lookup"><span data-stu-id="44287-556">**Direction**</span></span>
- <span data-ttu-id="44287-557">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="44287-558">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="44287-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="44287-559">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44287-559">**Domain**</span></span>
- <span data-ttu-id="44287-560">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="44287-560">**Policy type**</span></span>
- <span data-ttu-id="44287-561">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="44287-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="44287-562">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-562">**Recipients**</span></span>

<span data-ttu-id="44287-563">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="44287-564">콘텐츠 맬웨어로 \> 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="44287-564">View data by Content \> Malware</span></span>

![위협 방지 상태 보고서의 콘텐츠 맬웨어 보기](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="44287-566">콘텐츠 **맬웨어로 \> 데이터** 보기 보기에서 조직의 Microsoft Defender에 대한 차트에 다음 Office 365 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="44287-567">**맬웨어** 방지 엔진 : Sharepoint, OneDrive 및 에서 Microsoft Teams 기본 제공 바이러스 검색에 의해 검색된 악성 [Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="44287-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="44287-568">**파일 검색:** Safe, 파일 및 Safe 파일에서 검색된 악성 [SharePoint,](mdo-for-spo-odb-and-teams.md)OneDrive 및 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="44287-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="44287-569">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="44287-570">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-571">**위치**</span><span class="sxs-lookup"><span data-stu-id="44287-571">**Location**</span></span>
- <span data-ttu-id="44287-572">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="44287-572">**Detected by**</span></span>
- <span data-ttu-id="44287-573">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="44287-573">**Malware name**</span></span>

<span data-ttu-id="44287-574">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="44287-575">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-576">**검색:** **맬웨어 방지 엔진** 또는 **파일 검색**</span><span class="sxs-lookup"><span data-stu-id="44287-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="44287-577">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="44287-578">시스템 오버라이드로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="44287-578">View data by System override</span></span>

![위협 방지 상태 보고서의 메시지 오버라이드 보기](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="44287-580">시스템으로 데이터 **보기 override** 보기에서 다음과 같은 이유 정보가 차트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="44287-581">**사내 건너뛰기**</span><span class="sxs-lookup"><span data-stu-id="44287-581">**On-premises skip**</span></span>
- <span data-ttu-id="44287-582">**IP 허용**</span><span class="sxs-lookup"><span data-stu-id="44287-582">**IP allow**</span></span>
- <span data-ttu-id="44287-583">**Exchange 전송 규칙(메일** 흐름 규칙)</span><span class="sxs-lookup"><span data-stu-id="44287-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="44287-584">**조직에서 허용된 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="44287-585">**조직 허용 도메인**</span><span class="sxs-lookup"><span data-stu-id="44287-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="44287-586">**ZAP를 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="44287-587">**정크 메일 폴더를 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="44287-588">**사용자 Safe 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-588">**User Safe Sender**</span></span>
- <span data-ttu-id="44287-589">**사용자 Safe 도메인**</span><span class="sxs-lookup"><span data-stu-id="44287-589">**User Safe Domain**</span></span>

<span data-ttu-id="44287-590">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="44287-591">**날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-591">**Date**</span></span>
- <span data-ttu-id="44287-592">**제목**</span><span class="sxs-lookup"><span data-stu-id="44287-592">**Subject**</span></span>
- <span data-ttu-id="44287-593">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-593">**Sender**</span></span>
- <span data-ttu-id="44287-594">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-594">**Recipients**</span></span>
- <span data-ttu-id="44287-595">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="44287-595">**Detected by**</span></span>
- <span data-ttu-id="44287-596">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="44287-596">**Delivery Status**</span></span>
- <span data-ttu-id="44287-597">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="44287-597">**Source of Compromise**</span></span>
- <span data-ttu-id="44287-598">**태그**</span><span class="sxs-lookup"><span data-stu-id="44287-598">**Tags**</span></span>

<span data-ttu-id="44287-599">필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="44287-600">**날짜:** **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="44287-601">**감지**</span><span class="sxs-lookup"><span data-stu-id="44287-601">**Detection**</span></span>
- <span data-ttu-id="44287-602">**보호:** **MDO(Office 365용** Defender) 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="44287-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="44287-603">**방향**</span><span class="sxs-lookup"><span data-stu-id="44287-603">**Direction**</span></span>
- <span data-ttu-id="44287-604">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="44287-605">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="44287-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="44287-606">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44287-606">**Domain**</span></span>
- <span data-ttu-id="44287-607">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="44287-607">**Policy type**</span></span>
- <span data-ttu-id="44287-608">**정책 이름(세부** 정보 표에만 해당)</span><span class="sxs-lookup"><span data-stu-id="44287-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="44287-609">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-609">**Recipients**</span></span>

<span data-ttu-id="44287-610">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="44287-611"><sup>\*</sup>Defender for Office 365 전용</span><span class="sxs-lookup"><span data-stu-id="44287-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="44287-612">상위 맬웨어 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-612">Top malware report</span></span>

<span data-ttu-id="44287-613">Top **malware report** shows the various kinds of malware that was detected by [anti-malware protection in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="44287-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="44287-614">Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="44287-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="44287-615">Top **malware(상위 맬웨어)에서** **View details(세부 정보 보기)를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="44287-616">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/TopMalware> 습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![전자 메일 및 공동 작업 & 페이지의 상위 맬웨어 위젯](../../media/top-malware-report-widget.png)

<span data-ttu-id="44287-618">파이 차트에서 에지 위에 마우스를 대면 맬웨어의 종류 이름과 해당 맬웨어가 있는 것으로 감지된 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="44287-619">세부 정보 **보기를** 클릭하면 보고서 페이지에 더 큰 버전의 파이 차트가 표시됩니다. 차트 아래의 세부 정보 표에는 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44287-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="44287-620">**상위 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="44287-620">**Top malware**</span></span>
- <span data-ttu-id="44287-621">**개수**</span><span class="sxs-lookup"><span data-stu-id="44287-621">**Count**</span></span>

<span data-ttu-id="44287-622">필터를 **클릭하면** 시작 날짜 및 종료 날짜로 날짜 범위를 **지정할** **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![상위 맬웨어 보고서 보기](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="44287-624">URL 위협 방지 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-624">URL threat protection report</span></span>

<span data-ttu-id="44287-625">**URL 위협 방지 보고서는** Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="44287-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="44287-626">자세한 내용은 [URL 위협 방지 보고서를 참조하세요.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="44287-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="44287-627">사용자가 보고한 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="44287-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44287-628">사용자가 보고한  메시지 보고서가 제대로 작동하려면 사용자 환경의 감사 로깅을 설정해야 Microsoft 365 있습니다. </span><span class="sxs-lookup"><span data-stu-id="44287-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="44287-629">이 작업은 일반적으로 감사 로그 역할이 할당된 사용자가 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="44287-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="44287-630">자세한 내용은 감사 로그 Microsoft 365 설정 또는 해제를 [참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="44287-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="44287-631">사용자 **보고** 메시지 보고서에는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 사용자가 [](enable-the-report-message-add-in.md) 정크 메일, 피싱 시도 또는 양호한 메일로 보고한 전자 메일 메시지에 대한 정보가 [표시됩니다.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="44287-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="44287-632">Microsoft 365 Defender 포털에서 보고서를 확인하면 보고서 전자  메일 & 공동 작업 전자 메일 & 보고서 사용자가 메시지를 \>  \>  \> **보고했습니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="44287-633">사용자가 **보고한 메시지에서** 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="44287-634">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/userSubmissionReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="44287-635">Microsoft 365 Defender 포털에서 관리 [제출으로 이동하려면 제출로](admin-submission.md) **이동을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![사용자가 전자 메일 및 공동 작업 보고서 페이지에서 & 위젯을 보고했습니다.](../../media/user-reported-messages-widget.png)

<span data-ttu-id="44287-637">세부 **정보** 보기를 클릭한 후 필터를 클릭하고 플라이아웃에 나타나는 다음 값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="44287-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="44287-638">**보고된 날짜:** **시작 시간** 및 **종료 시간**</span><span class="sxs-lookup"><span data-stu-id="44287-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="44287-639">**보고한**</span><span class="sxs-lookup"><span data-stu-id="44287-639">**Reported by**</span></span>
- <span data-ttu-id="44287-640">**전자 메일 제목**</span><span class="sxs-lookup"><span data-stu-id="44287-640">**Email subject**</span></span>
- <span data-ttu-id="44287-641">**보고된 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="44287-641">**Message reported ID**</span></span>
- <span data-ttu-id="44287-642">**네트워크 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="44287-642">**Network Message ID**</span></span>
- <span data-ttu-id="44287-643">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-643">**Sender**</span></span>
- <span data-ttu-id="44287-644">**보고된 이유**</span><span class="sxs-lookup"><span data-stu-id="44287-644">**Reported reason**</span></span>
  - <span data-ttu-id="44287-645">**정크 아님**</span><span class="sxs-lookup"><span data-stu-id="44287-645">**Not junk**</span></span>
  - <span data-ttu-id="44287-646">**피싱**</span><span class="sxs-lookup"><span data-stu-id="44287-646">**Phish**</span></span>
  - <span data-ttu-id="44287-647">**스팸**</span><span class="sxs-lookup"><span data-stu-id="44287-647">**Spam**</span></span>
- <span data-ttu-id="44287-648">**피싱 시뮬레이션:** **예** 또는 **아니요**</span><span class="sxs-lookup"><span data-stu-id="44287-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="44287-649">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="44287-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="44287-650">항목을 그룹화하려면 그룹을 **클릭하고** 드롭다운 목록에서 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="44287-651">**없음**</span><span class="sxs-lookup"><span data-stu-id="44287-651">**None**</span></span>
- <span data-ttu-id="44287-652">**이유**</span><span class="sxs-lookup"><span data-stu-id="44287-652">**Reason**</span></span>
- <span data-ttu-id="44287-653">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-653">**Sender**</span></span>
- <span data-ttu-id="44287-654">**보고한**</span><span class="sxs-lookup"><span data-stu-id="44287-654">**Reported by**</span></span>
- <span data-ttu-id="44287-655">**결과 다시 검색**</span><span class="sxs-lookup"><span data-stu-id="44287-655">**Rescan result**</span></span>
- <span data-ttu-id="44287-656">**피싱 시뮬레이션**</span><span class="sxs-lookup"><span data-stu-id="44287-656">**Phish simulation**</span></span>

![사용자가 보고한 메시지 보고서](../../media/user-reported-messages-report.png)

<span data-ttu-id="44287-658">그래프 아래 표에서 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44287-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="44287-659">**전자 메일 제목**</span><span class="sxs-lookup"><span data-stu-id="44287-659">**Email subject**</span></span>
- <span data-ttu-id="44287-660">**보고한**</span><span class="sxs-lookup"><span data-stu-id="44287-660">**Reported by**</span></span>
- <span data-ttu-id="44287-661">**보고된 날짜**</span><span class="sxs-lookup"><span data-stu-id="44287-661">**Date reported**</span></span>
- <span data-ttu-id="44287-662">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="44287-662">**Sender**</span></span>
- <span data-ttu-id="44287-663">**보고된 이유**</span><span class="sxs-lookup"><span data-stu-id="44287-663">**Reported reason**</span></span>
- <span data-ttu-id="44287-664">**결과 다시 검색**</span><span class="sxs-lookup"><span data-stu-id="44287-664">**Rescan result**</span></span>
- <span data-ttu-id="44287-665">**태그**</span><span class="sxs-lookup"><span data-stu-id="44287-665">**Tags**</span></span>

<span data-ttu-id="44287-666">분석을 위해 Microsoft에 메시지를 제출하려면 표에서 메시지 항목을 선택하고 분석을 위해 **Microsoft에** 제출을 클릭한 다음 드롭다운 목록에서 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="44287-667">**정리 보고**</span><span class="sxs-lookup"><span data-stu-id="44287-667">**Report clean**</span></span>
- <span data-ttu-id="44287-668">**피싱 보고**</span><span class="sxs-lookup"><span data-stu-id="44287-668">**Report phishing**</span></span>
- <span data-ttu-id="44287-669">**맬웨어 보고**</span><span class="sxs-lookup"><span data-stu-id="44287-669">**Report malware**</span></span>
- <span data-ttu-id="44287-670">**스팸 보고**'</span><span class="sxs-lookup"><span data-stu-id="44287-670">**Report spam**'</span></span>
- <span data-ttu-id="44287-671">**조사** 트리거(Office 365)</span><span class="sxs-lookup"><span data-stu-id="44287-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="44287-672">이러한 보고서를 보는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="44287-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="44287-673">이 문서에 설명된 보고서를 보고 사용하려면 Microsoft 365 Defender 포털에서 다음 역할 그룹 중 하나에 Microsoft 365 Defender 합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="44287-674">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="44287-674">**Organization Management**</span></span>
- <span data-ttu-id="44287-675">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="44287-675">**Security Administrator**</span></span>
- <span data-ttu-id="44287-676">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="44287-676">**Security Reader**</span></span>
- <span data-ttu-id="44287-677">**전역 읽기**</span><span class="sxs-lookup"><span data-stu-id="44287-677">**Global Reader**</span></span>

<span data-ttu-id="44287-678">자세한 내용은 Microsoft 365 Defender [포털의 사용 권한을 참조하세요.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="44287-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="44287-679">**참고:** Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한과 Microsoft 365 Defender 포털의 다른  기능에 대한 사용 권한이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44287-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="44287-680">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44287-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="44287-681">보고서에 데이터가 표시되지 않는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="44287-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="44287-682">보고서에 데이터가 없는 경우 정책이 올바르게 설정되어 있는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="44287-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="44287-683">자세한 내용은 [위협으로부터 보호를 참조합니다.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="44287-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="44287-684">관련 항목</span><span class="sxs-lookup"><span data-stu-id="44287-684">Related topics</span></span>

[<span data-ttu-id="44287-685">EOP의 스팸 방지 및 맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="44287-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="44287-686">검색 포털의 스마트 보고서 및 Microsoft 365 Defender 정보</span><span class="sxs-lookup"><span data-stu-id="44287-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="44287-687">사이트 포털에서 메일 흐름 Microsoft 365 Defender 보기</span><span class="sxs-lookup"><span data-stu-id="44287-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="44287-688">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="44287-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
