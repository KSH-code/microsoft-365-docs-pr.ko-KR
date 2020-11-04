---
title: 보안 대시보드 개요
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 새 보안 대시보드를 사용 하 여 Office 365 위협 방지 상태를 검토 하 고 보안 경고를 보고 작동 합니다.
ms.openlocfilehash: b49422621e70d597251cd342559e59ffa0e128f6
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877328"
---
# <a name="security-dashboard"></a><span data-ttu-id="a143a-103">보안 대시보드</span><span class="sxs-lookup"><span data-stu-id="a143a-103">Security Dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a><span data-ttu-id="a143a-104">기본 기능 및 보안 대시보드를 여는 방법</span><span class="sxs-lookup"><span data-stu-id="a143a-104">Basic functions and how to open Security Dashboard</span></span>

<span data-ttu-id="a143a-105">[보안 & 준수 센터](../../compliance/go-to-the-securitycompliance-center.md) 를 통해 조직에서 데이터 보호 및 규정 준수를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-105">The [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) enables your organization to manage data protection and compliance.</span></span> <span data-ttu-id="a143a-106">필요한 사용 권한이 있는 경우 보안 대시보드를 사용 하 여 위협 방지 상태를 검토 하 고 보안 경고에 대 한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-106">Assuming you have the necessary permissions, the Security Dashboard enables you to review your Threat Protection Status, as well as view and act on security alerts.</span></span>

<span data-ttu-id="a143a-107">비디오를 시청 하 여 개요를 확인 한 다음이 문서를 참조 하 여 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a143a-107">Watch the video to get an overview, and then read this article to learn more.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

<span data-ttu-id="a143a-108">조직의 구독에 포함 된 내용에 따라 보안 대시보드에는 다음 섹션에 설명 된 것 처럼 위협 관리 요약, 위협 방지 상태, 전역 주간 위협 감지, 맬웨어 등의 여러 widget이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-108">Depending on what your organization's subscription includes, the Security Dashboard includes several widgets, such as Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware, and more, as described in the following sections.</span></span>

<span data-ttu-id="a143a-109">보안 대시보드를 보려면 [보안 & 준수 센터](../../compliance/go-to-the-securitycompliance-center.md)에서 **위협 관리** \> **대시보드로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-109">To view the Security Dashboard, in the [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md), go to **Threat management** \> **Dashboard**.</span></span>

> [!NOTE]
> <span data-ttu-id="a143a-110">보안 대시보드를 보려면 전역 관리자, 보안 관리자 또는 보안 독자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-110">You must be a global administrator, a security administrator, or a security reader to view the Security Dashboard.</span></span> <span data-ttu-id="a143a-111">일부 위젯을 보려면 추가 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-111">Some widgets require additional permissions to view.</span></span> <span data-ttu-id="a143a-112">자세한 내용은 [Security & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a143a-112">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="threat-management-summary"></a><span data-ttu-id="a143a-113">위협 관리 요약</span><span class="sxs-lookup"><span data-stu-id="a143a-113">Threat Management Summary</span></span>

<span data-ttu-id="a143a-114">위협 관리 요약 위젯은 지난 7 일 동안 위협 으로부터 조직이 보호 된 방식을 한눈에 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-114">The Threat Management Summary widget tells you at a glance how your organization was protected from threats over the past seven (7) days.</span></span>

![보안 대시보드-위협 관리 요약 위젯](../../media/SecDash-ThreatMgmtSummary.png)

<span data-ttu-id="a143a-116">위협 관리 요약에 표시 되는 정보는 구독에 포함 된 항목에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-116">The information you'll see in the Threat Management Summary depends on what you subscription includes.</span></span> <span data-ttu-id="a143a-117">다음 표에는 Office 365 E3 및 Office 365 E5에 포함 된 정보에 대 한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-117">The following table describes what information is included for Office 365 E3 and Office 365 E5.</span></span>

|<span data-ttu-id="a143a-118">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="a143a-118">Office 365 E3</span></span>|<span data-ttu-id="a143a-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="a143a-119">Office 365 E5</span></span>|
|---|---|
|<span data-ttu-id="a143a-120">차단 된 맬웨어 메시지</span><span class="sxs-lookup"><span data-stu-id="a143a-120">Malware messages blocked</span></span><br/><span data-ttu-id="a143a-121">차단 된 피싱 메시지</span><span class="sxs-lookup"><span data-stu-id="a143a-121">Phishing messages blocked</span></span><br><span data-ttu-id="a143a-122">사용자가 보고 한 메시지</span><span class="sxs-lookup"><span data-stu-id="a143a-122">Messages reported by users</span></span><br><br><br><br>|<span data-ttu-id="a143a-123">차단 된 맬웨어 메시지</span><span class="sxs-lookup"><span data-stu-id="a143a-123">Malware messages blocked</span></span><br><span data-ttu-id="a143a-124">차단 된 피싱 메시지</span><span class="sxs-lookup"><span data-stu-id="a143a-124">Phishing messages blocked</span></span><br><span data-ttu-id="a143a-125">사용자가 보고 한 메시지</span><span class="sxs-lookup"><span data-stu-id="a143a-125">Messages reported by users</span></span><br><span data-ttu-id="a143a-126">제로 일 맬웨어 차단</span><span class="sxs-lookup"><span data-stu-id="a143a-126">Zero-day malware blocked</span></span><br><span data-ttu-id="a143a-127">검색 된 고급 피싱 메시지</span><span class="sxs-lookup"><span data-stu-id="a143a-127">Advanced phishing messages detected</span></span><br><span data-ttu-id="a143a-128">차단 된 악의적인 Url</span><span class="sxs-lookup"><span data-stu-id="a143a-128">Malicious URLs blocked</span></span>|

<span data-ttu-id="a143a-129">위협 관리 요약 위젯을 보거나 액세스 하려면 Defender for Office 365 reports를 볼 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-129">To view or access the Threat Management Summary widget, you must have permissions to view Defender for Office 365 reports.</span></span> <span data-ttu-id="a143a-130">자세한 내용은 [어떤 사용 권한으로 Defender For Office 365 reports?를 확인 해야 합니까?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a143a-130">To learn more, see [What permissions are needed to view the Defender for Office 365 reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).</span></span>

## <a name="threat-protection-status"></a><span data-ttu-id="a143a-131">위협 방지 상태</span><span class="sxs-lookup"><span data-stu-id="a143a-131">Threat Protection Status</span></span>

<span data-ttu-id="a143a-132">위협 방지 상태 위젯은 피싱 및 맬웨어 추이에 대 한 경향 및 상세 보기로 위협 보호 효과를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-132">The Threat Protection Status widget shows threat protection effectiveness with a trending and detailed view of phish and malware.</span></span>

![위협 방지 상태 위젯](../../media/tpswidget.png)

<span data-ttu-id="a143a-134">자세한 내용은 365 Microsoft [Defender For Office 365](office-365-atp.md)이 포함 되어 있는지 여부에 따라 사용 하는 EOP ( [Exchange Online Protection](exchange-online-protection-overview.md) )에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-134">The details depend on whether your Microsoft 365 subscription includes [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) with or without [Microsoft Defender for Office 365](office-365-atp.md).</span></span>

|<span data-ttu-id="a143a-135">구독에 다음이 포함 된 경우 ...</span><span class="sxs-lookup"><span data-stu-id="a143a-135">If your subscription includes...</span></span>|<span data-ttu-id="a143a-136">다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-136">You'll see these details</span></span>|
|---|---|
|<span data-ttu-id="a143a-137">EOP 이지만 Office 용 Microsoft Defender 365이 아님</span><span class="sxs-lookup"><span data-stu-id="a143a-137">EOP but not Microsoft Defender for Office 365</span></span>|<span data-ttu-id="a143a-138">EOP에서 검색 하 고 차단한 악성 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-138">Malicious email that was detected and blocked by EOP.</span></span><br><br> <span data-ttu-id="a143a-139">[위협 방지 상태 보고서 (EOP)](view-email-security-reports.md#threat-protection-status-report)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a143a-139">See [Threat Protection Status report (EOP)](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="a143a-140">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a143a-140">Microsoft Defender for Office 365</span></span>|<span data-ttu-id="a143a-141">EOP 및 Office 365 용 Defender에서 검색 및 차단 된 악의적인 콘텐츠 및 악성 전자 메일</span><span class="sxs-lookup"><span data-stu-id="a143a-141">Malicious content and malicious email detected and blocked by EOP and Defender for Office 365</span></span><br><br><span data-ttu-id="a143a-142">맬웨어 방지 엔진에 의해 차단 되는 악성 콘텐츠가 포함 된 고유 전자 메일 메시지의 집계 횟수, [영 자동 제거](zero-hour-auto-purge.md)및 office 365 기능 ( [안전 링크](atp-safe-links.md), [안전한 첨부 파일](atp-safe-attachments.md), [defender for office 365의 사전 피싱](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365))</span><span class="sxs-lookup"><span data-stu-id="a143a-142">Aggregated count of unique email messages with malicious content blocked by the anti-malware engine, [zero-hour auto purge](zero-hour-auto-purge.md), and Defender for Office 365 features (including [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing in Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span><br><br><span data-ttu-id="a143a-143">[위협 방지 상태 보고서](view-reports-for-atp.md#threat-protection-status-report)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a143a-143">See [Threat protection status report](view-reports-for-atp.md#threat-protection-status-report).</span></span>|

<span data-ttu-id="a143a-144">위협 방지 상태 위젯을 보거나 액세스 하려면 Defender for Office 365 보고서용 보기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-144">To view or access the Threat Protection Status widget, you must have permissions to view Defender for Office 365 reports.</span></span> <span data-ttu-id="a143a-145">자세한 내용은 [어떤 권한이 있는지 Defender For Office 365 reports를 확인 하는 데 필요한 사용 권한을](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a143a-145">To learn more, see [What permissions are needed to view the Defender for Office 365 reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)</span></span>

## <a name="global-weekly-threat-detections"></a><span data-ttu-id="a143a-146">전역 주간 위협 감지</span><span class="sxs-lookup"><span data-stu-id="a143a-146">Global Weekly Threat Detections</span></span>

<span data-ttu-id="a143a-147">전체 주간 위협 감지 위젯은 지난 7 일 동안 전자 메일 메시지에서 검색 된 위협의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-147">The Global Weekly Threat Detections widget shows how many threats were detected in email messages over the past seven (7) days.</span></span>

![전역 주간 위협 감지 위젯](../../media/globalweeklythreatdetections.png)

<span data-ttu-id="a143a-149">메트릭은 다음 표에 설명 된 대로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-149">The metrics are calculated as described in the following table:</span></span>

|<span data-ttu-id="a143a-150">메트릭</span><span class="sxs-lookup"><span data-stu-id="a143a-150">Metric</span></span>|<span data-ttu-id="a143a-151">계산 방법</span><span class="sxs-lookup"><span data-stu-id="a143a-151">How it's calculated</span></span>|
|---|---|
|<span data-ttu-id="a143a-152">검색 된 메시지</span><span class="sxs-lookup"><span data-stu-id="a143a-152">Messages scanned</span></span>|<span data-ttu-id="a143a-153">검색 된 전자 메일 메시지의 수를 받는 사람 수에 곱하여 함</span><span class="sxs-lookup"><span data-stu-id="a143a-153">Number of email messages scanned multiplied by the number of recipients</span></span>|
|<span data-ttu-id="a143a-154">위협이 중지 됨</span><span class="sxs-lookup"><span data-stu-id="a143a-154">Threats stopped</span></span>|<span data-ttu-id="a143a-155">맬웨어를 포함 하는 것으로 식별 되는 전자 메일 메시지 수 (받는 사람 수)</span><span class="sxs-lookup"><span data-stu-id="a143a-155">Number of email messages identified as containing malware multiplied by the number of recipients</span></span>|
|<span data-ttu-id="a143a-156">[Defender For Office 365에 대해](office-365-atp.md) 차단 됨</span><span class="sxs-lookup"><span data-stu-id="a143a-156">Blocked by [Defender for Office 365 ](office-365-atp.md)</span></span>|<span data-ttu-id="a143a-157">Defender for Office 365에 받는 사람 수를 곱하여 차단 된 전자 메일 메시지 수</span><span class="sxs-lookup"><span data-stu-id="a143a-157">Number of email messages blocked by Defender for Office 365 multiplied by the number of recipients</span></span>|
|<span data-ttu-id="a143a-158">배달 후 제거 됨</span><span class="sxs-lookup"><span data-stu-id="a143a-158">Removed after delivery</span></span>|<span data-ttu-id="a143a-159">[자동 삭제](zero-hour-auto-purge.md) 를 통해 제거 되는 메시지 수를 받는 사람 수 곱하여</span><span class="sxs-lookup"><span data-stu-id="a143a-159">Number of messages removed by [zero-hour auto purge](zero-hour-auto-purge.md) multiplied by the number of recipients</span></span>|

## <a name="malware"></a><span data-ttu-id="a143a-160">맬웨어</span><span class="sxs-lookup"><span data-stu-id="a143a-160">Malware</span></span>

<span data-ttu-id="a143a-161">맬웨어 위젯은 지난 7 일 동안의 맬웨어 추세 및 맬웨어 패밀리 유형에 대 한 세부 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-161">Malware widgets show details about malware trends and malware family types over the past seven (7) days.</span></span>

![맬웨어 추세 및 패밀리 유형](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a><span data-ttu-id="a143a-163">인사이트</span><span class="sxs-lookup"><span data-stu-id="a143a-163">Insights</span></span>

<span data-ttu-id="a143a-164">자세한 내용은 검토 해야 하는 주요 문제 뿐 아니라 권장 사항과 고려할 작업도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-164">Insights not only surface key issues you should review, they also include recommendations and actions to consider.</span></span>

![고급 통찰력](../../media/smartinsights.png)

<span data-ttu-id="a143a-166">예를 들어 일부 사용자가 정크 메일 옵션을 사용 하지 않도록 설정 했으므로 피싱 전자 메일 메시지가 배달 되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-166">For example, you might see that phishing email messages are being delivered because some users have disabled their junk mail options.</span></span> <span data-ttu-id="a143a-167">Insights 작동 방식에 대 한 자세한 내용은 [Security & 준수 센터의 Reports and insights](reports-and-insights-in-security-and-compliance.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a143a-167">To learn more about how insights work, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

## <a name="threat-investigation-and-response"></a><span data-ttu-id="a143a-168">위협 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="a143a-168">Threat investigation and response</span></span>

<span data-ttu-id="a143a-169">조직의 구독에  [Office 365 계획 2 용 Microsoft Defender](office-365-ti.md)가 포함 되어 있는 경우 보안 대시보드에 advanced threat 조사한 및 응답 도구가 포함 된 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-169">If your organization's subscription includes  [Microsoft Defender for Office 365 Plan 2](office-365-ti.md), your Security Dashboard has a section that includes advanced threat investigation and response tools.</span></span> <span data-ttu-id="a143a-170">이러한 도구에는 [자동화 된 조사 및 응답 기능이](automated-investigation-response-office.md)포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-170">These tools include [automated investigation and response capabilities](automated-investigation-response-office.md).</span></span> <span data-ttu-id="a143a-171">자동화 된 조사 및 응답은 [손상 된 사용자 계정에 빠르게 주소를 지정](address-compromised-users-quickly.md)하는 등의 시나리오에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-171">Automated investigation and response can be helpful in scenarios such as [addressing compromised user accounts quickly](address-compromised-users-quickly.md).</span></span>

<span data-ttu-id="a143a-172">자세한 내용은 [Office 365에서 자동 조사 및 응답을 사용 하 여 시작](office-365-air.md)하기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a143a-172">To learn more, see [Get started using Automated investigation and response (AIR) in Office 365](office-365-air.md).</span></span>

## <a name="trends"></a><span data-ttu-id="a143a-173">추세</span><span class="sxs-lookup"><span data-stu-id="a143a-173">Trends</span></span>

<span data-ttu-id="a143a-174">보안 대시보드 아래쪽에는 조직에 대 한 전자 메일 흐름 추세를 요약 하는 **추세** 섹션을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-174">Near the bottom of the Security Dashboard is a **Trends** section, which summarizes email flow trends for your organization.</span></span> <span data-ttu-id="a143a-175">보고서는 스팸으로 분류 된 전자 메일, 맬웨어, 피싱 시도 및 좋은 전자 메일에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-175">Reports provide information about email categorized as spam, malware, phishing attempts, and good email.</span></span> <span data-ttu-id="a143a-176">타일을 클릭 하 여 보고서에서 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-176">Click a tile to view more detailed information in the report.</span></span>

![조직에 대 한 전자 메일 흐름 추세를 요약 하는 추세 섹션](../../media/trends.png)

<span data-ttu-id="a143a-178">또한 조직의 구독에 [Office 365 계획 2에 대 한 Defender](office-365-ti.md)가 포함 되어 있는 경우 보안 팀이 우선 순위가 높은 보안 경고에 대 한 작업을 확인 하 고 수행할 수 있도록 하는 **최근 위협 관리 경고** 보고서가이 섹션에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-178">And, if your organization's subscription includes [Defender for Office 365 Plan 2](office-365-ti.md), you will also have a **Recent threat management alerts** report in this section that enables your security team to view and take action on high-priority security alerts.</span></span>

<span data-ttu-id="a143a-179">보내고 받은 전자 메일 위젯을 보거나 액세스 하려면 Defender for Office 365 reports에 대 한 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-179">To view or access the Sent and Received Email widget, you must have permissions to view Defender for Office 365 reports.</span></span> <span data-ttu-id="a143a-180">자세한 내용은 [어떤 사용 권한으로 Defender For Office 365 reports?를 확인 해야 합니까?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a143a-180">To learn more, see [What permissions are needed to view the Defender for Office 365 reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).</span></span>

<span data-ttu-id="a143a-181">최신 위협 관리 알림 위젯을 보거나 액세스 하려면 알림을 볼 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a143a-181">To view or access the Recent Threat Management Alerts widget, you must have permissions to view alerts.</span></span> <span data-ttu-id="a143a-182">자세한 내용은 [경고를 보는 데 필요한 RBAC 사용 권한을](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a143a-182">To learn more, see [RBAC permissions required to view alerts](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a143a-183">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a143a-183">Related topics</span></span>

[<span data-ttu-id="a143a-184">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="a143a-184">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="a143a-185">Microsoft Defender for Office 365에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="a143a-185">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="a143a-186">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a143a-186">Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="a143a-187">Office 365 위협 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="a143a-187">Office 365 Threat investigation and response</span></span>](office-365-ti.md)
