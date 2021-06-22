---
title: 보고 및 메시지 추적
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 EOP(Microsoft Exchange Online 보호) 관리자가 사용할 수 있는 보고서 및 문제 해결 도구에 대해 자세히 알아보게 됩니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc49a92d5fb1fb0368b14eef7524638542f38deb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054373"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="57314-103">EOP의 보고 및 메시지 추적</span><span class="sxs-lookup"><span data-stu-id="57314-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="57314-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="57314-104">**Applies to**</span></span>
- [<span data-ttu-id="57314-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="57314-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="57314-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="57314-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="57314-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57314-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="57314-108">Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 EOP는 Exchange Online 조직의 전반적인 상태를 확인하는 데 도움이 되는 다양한 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57314-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="57314-109">받는 사람에게 메시지가 도착하지 않는 등 특정 이벤트에 대한 문제를 해결할 수 있는 도구와 규정 준수 요구 사항을 지원하는 감사 보고서도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="57314-110">사용 현황 보고서</span><span class="sxs-lookup"><span data-stu-id="57314-110">Usage reports</span></span>

- <span data-ttu-id="57314-111">**Microsoft 365 그룹 활동:** 생성 및 사용되는 Microsoft 365 그룹 수에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span> <span data-ttu-id="57314-112">자세한 내용은 관리 센터의 Microsoft 365 보고서 - Microsoft 365 [참조하세요.](../../admin/activity-reports/office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="57314-112">For more information, see [Microsoft 365 Reports in the admin center - Microsoft 365 groups](../../admin/activity-reports/office-365-groups.md).</span></span>
- <span data-ttu-id="57314-113">**전자 메일 활동:** 전체 조직 및 특정 사용자가 보내고, 받고, 읽은 메시지 수에 대한 정보를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-113">**Email activity**: View information about the number of messages sent, received, and read in your whole organization, and by specific users.</span></span> <span data-ttu-id="57314-114">자세한 내용은 관리 Microsoft 365 보고서 - 전자 메일 활동을 [참조하세요.](../../admin/activity-reports/email-activity.md)</span><span class="sxs-lookup"><span data-stu-id="57314-114">For more information, see [Microsoft 365 Reports in the admin center - Email activity](../../admin/activity-reports/email-activity.md).</span></span>
- <span data-ttu-id="57314-115">**전자 메일 앱 사용:** 사용되는 전자 메일 앱에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-115">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="57314-116">여기에는 각 앱의 총 연결 수와 연결되는 앱의 Outlook 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="57314-116">This includes the total number of connections for each app, and the versions of Outlook that are connecting.</span></span> <span data-ttu-id="57314-117">자세한 내용은 관리 센터의 Microsoft 365 보고서 - 전자 메일 [앱 사용을 참조하세요.](../../admin/activity-reports/email-apps-usage.md)</span><span class="sxs-lookup"><span data-stu-id="57314-117">For more information, see [Microsoft 365 Reports in the admin center - Email apps usage](../../admin/activity-reports/email-apps-usage.md).</span></span>
- <span data-ttu-id="57314-118">**사서함 사용:** 사서함에 대해 사용된 저장소, 할당량 소비, 항목 수 및 마지막 활동(보내기 또는 읽기 활동)에 대한 정보를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-118">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span> <span data-ttu-id="57314-119">자세한 내용은 관리 센터의 Microsoft 365 보고서 - 사서함 [사용량을 참조하세요.](../../admin/activity-reports/mailbox-usage.md)</span><span class="sxs-lookup"><span data-stu-id="57314-119">For more information, see [Microsoft 365 Reports in the admin center - Mailbox usage](../../admin/activity-reports/mailbox-usage.md).</span></span>

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="57314-120">Microsoft 365 Defender 포털의 보안 보고서</span><span class="sxs-lookup"><span data-stu-id="57314-120">Security reports in the Microsoft 365 defender portal</span></span>

<span data-ttu-id="57314-121">이러한 향상된 보고서는 요약 정보와 자세한 내용을 드릴다운하는 기능을 포함하는 EOP 관리자를 위한 대화형 보고 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57314-121">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

- <span data-ttu-id="57314-122">**Defender for Office 365:** Microsoft Defender for 금고 링크 및 금고 첨부 파일에 대한 정보를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="57314-122">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span> <span data-ttu-id="57314-123">자세한 내용은 view [Defender for Office 365 portal에서 Microsoft 365 Defender 참조하세요.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="57314-123">For more information, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
- <span data-ttu-id="57314-124">**EOP:** 맬웨어 검색, 스푸핑된 메일, 스팸 검색 및 조직과의 메일 흐름에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span> <span data-ttu-id="57314-125">자세한 내용은 Microsoft 365 Defender 포털에서 전자 [메일 보안 보고서 보기를 참조하세요.](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="57314-125">For more information, see [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="57314-126">Microsoft 365를 사용한 사용자 지정 Graph</span><span class="sxs-lookup"><span data-stu-id="57314-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="57314-127">Microsoft 365를 사용하여 관리 센터에서 사용할 수 있는 보고서를 프로그래밍 Graph.</span><span class="sxs-lookup"><span data-stu-id="57314-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="57314-128">자세한 내용은 [Overview of Microsoft Graph](/graph/overview) and Working with Office 365 usage reports in Microsoft [Graph.](/graph/api/resources/report)</span><span class="sxs-lookup"><span data-stu-id="57314-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="57314-129">Message trace</span><span class="sxs-lookup"><span data-stu-id="57314-129">Message trace</span></span>

<span data-ttu-id="57314-130">EOP를 통과하는 전자 메일 메시지를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="57314-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="57314-131">이를 통해 서비스에서 전자 메일 메시지를 수신, 거부, 지연 또는 배달했는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="57314-132">또한 최종 상태에 도달하기 전에 메시지에 대해 수행된 작업도 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="57314-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="57314-133">이 정보를 사용하여 사용자의 질문에 효율적으로 답변하고, 메일 흐름 문제를 해결하고, 정책 변경의 유효성을 검사하고, 기술 지원에 도움을 요청해야 하는 필요성을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="57314-134">포털의 메시지 [추적을 Microsoft 365 Defender 참조합니다.](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="57314-134">See [Message trace in the Microsoft 365 Defender portal](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="57314-135">감사 로깅</span><span class="sxs-lookup"><span data-stu-id="57314-135">Audit logging</span></span>

<span data-ttu-id="57314-136">조직 관리자가 변경한 특정 내용을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="57314-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="57314-137">이러한 보고서를 사용하면 구성 문제를 해결하거나 보안 또는 규정 준수 관련 문제의 원인을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="57314-138">에서 [감사 보고서를 Exchange Online.](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)</span><span class="sxs-lookup"><span data-stu-id="57314-138">See [Auditing reports in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="57314-139">보고 및 메시지 추적 데이터 사용 가능 여부 및 대기 시간</span><span class="sxs-lookup"><span data-stu-id="57314-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="57314-140">다음 표에는 EOP 보고 및 메시지 추적 데이터를 사용할 수 있는 시기와 기간에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

<br>

****

|<span data-ttu-id="57314-141">보고서 유형</span><span class="sxs-lookup"><span data-stu-id="57314-141">Report type</span></span>|<span data-ttu-id="57314-142">데이터 사용 가능 기간(확인 기간)</span><span class="sxs-lookup"><span data-stu-id="57314-142">Data available for (look back period)</span></span>|<span data-ttu-id="57314-143">대기 시간</span><span class="sxs-lookup"><span data-stu-id="57314-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="57314-144">메일 보호 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="57314-144">Mail protection summary reports</span></span>|<span data-ttu-id="57314-145">90일</span><span class="sxs-lookup"><span data-stu-id="57314-145">90 days</span></span>|<span data-ttu-id="57314-p111">메시지 데이터 집계는 대부분 24~48시간 이내에 완료됩니다. 일부 사소한 증분 집계 변경의 경우 5일까지 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-p111">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="57314-148">메일 보호 세부 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="57314-148">Mail protection detail reports</span></span>|<span data-ttu-id="57314-149">90일</span><span class="sxs-lookup"><span data-stu-id="57314-149">90 days</span></span>|<span data-ttu-id="57314-p112">7일 미만의 세부 데이터는 24시간 이내에 표시되지만 48시간이 될 때까지 완료되지 않을 수 있습니다. 일부 사소한 증분 변경의 경우 5일까지 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-p112">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="57314-152">7일이 지난 메시지에 대한 상세 보고서를 보려면 결과가 표시되는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="57314-153">메시지 추적 데이터</span><span class="sxs-lookup"><span data-stu-id="57314-153">Message trace data</span></span>|<span data-ttu-id="57314-154">90일</span><span class="sxs-lookup"><span data-stu-id="57314-154">90 days</span></span>|<span data-ttu-id="57314-155">7일 미만의 메시지에 대해 메시지 추적을 실행하면 메시지가 5~30분 이내에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57314-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="57314-156">7일이 지난 메시지에 대해 메시지 추적을 실행하면 결과가 표시되는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57314-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="57314-157">데이터 가용성 및 대기 시간은 관리 센터 또는 원격 PowerShell을 통해 요청된 경우와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="57314-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
