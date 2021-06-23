---
title: Office 365용 Defender 보고서 보기
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 검색 포털에서 사용할 수 있는 Office 365 Defender를 찾아 Microsoft 365 Defender 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7eab856f22ac1c2282e83897db6e3f93d4d97e6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083515"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="b51c7-103">검색 포털에서 Office 365 대한 Microsoft 365 Defender 보기</span><span class="sxs-lookup"><span data-stu-id="b51c7-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b51c7-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="b51c7-104">**Applies to**</span></span>
- [<span data-ttu-id="b51c7-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="b51c7-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b51c7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b51c7-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b51c7-107">Office 365 조직용 Microsoft Defender(예: Microsoft 365 E5 구독 또는 Office 365 Plan 1용 Microsoft Defender 또는 Office 365 Plan 2 추가 기능용 Microsoft Defender)에는 다양한 보안 관련 보고서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="b51c7-108">필요한 권한이 [](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)있는 경우 보고서 전자 메일 Microsoft 365 Defender 공동 작업 전자  메일 & 공동 작업 보고서로 이동하여 & \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b51c7-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b51c7-109">전자 메일 및 공동 작업 **& 페이지로** 직접 이동하기 위해 를 를 를 열 수 <https://security.microsoft.com/emailandcollabreport> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![& 포털의 전자 메일 Microsoft 365 Defender 공동 작업 보고서 페이지](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="b51c7-111">보안에 대해 Defender가 필요하지 Office 365 전자 메일 보안 보고서는 Microsoft 365 Defender 포털의 전자 메일 [보안 보고서 보기에 설명되어 있습니다.](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="b51c7-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="b51c7-112">메일 흐름과 관련된 보고서는 이제 EAC(Exchange 관리 센터)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="b51c7-113">이러한 보고서에 대한 자세한 내용은 새 Exchange 관리 센터의 [메일 흐름 보고서를 참조하세요.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="b51c7-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="b51c7-114">금고 첨부 파일 형식 보고서</span><span class="sxs-lookup"><span data-stu-id="b51c7-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="b51c7-115">첨부 **금고 파일 형식 보고서가** 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="b51c7-116">위협 방지 상태 보고서에서 동일한 [정보를 사용할 수 있습니다.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b51c7-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="b51c7-117">금고 첨부 파일 메시지 처리 보고서</span><span class="sxs-lookup"><span data-stu-id="b51c7-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="b51c7-118">첨부 **금고 메시지 처리 보고서는** 결국 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="b51c7-119">위협 방지 상태 보고서에서 동일한 [정보를 사용할 수 있습니다.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b51c7-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="b51c7-120">메일 대기 시간 보고서</span><span class="sxs-lookup"><span data-stu-id="b51c7-120">Mail latency report</span></span>

<span data-ttu-id="b51c7-121">메일 **대기 시간 보고서에는** 조직 내에서 경험한 메일 배달 및 확인 대기 시간에 대한 집계 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="b51c7-122">서비스의 메일 배달 시간은 다양한 요인의 영향을 받지만 절대 배달 시간(초)은 성공 또는 문제를 나타내는 좋은 지표가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="b51c7-123">하루의 배달 시간이 느리면 다른 날의 평균 배달 시간으로 간주되거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="b51c7-124">이는 다른 메시지의 관찰된 배달 시간에 대한 통계 데이터를 기반으로 메시지 배달을 한정합니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="b51c7-125">클라이언트 쪽 및 네트워크 대기 시간은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="b51c7-126">보고서를 보시고 Microsoft 365 Defender [포털을](https://security.microsoft.com)열고 보고서  전자 메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="b51c7-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b51c7-127">전자 메일 & **공동** 작업 보고서 페이지에서 메일 대기 시간 보고서를 **찾은** 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b51c7-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="b51c7-128">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/mailLatencyReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![전자 메일 및 공동 작업 보고서 페이지의 메일 & 보고서 위젯](../../media/mail-latency-report-widget.png)

<span data-ttu-id="b51c7-130">메일 대기 **시간 보고서** 페이지에서는 메일 대기 시간 보고서 페이지에서 다음 **탭을 사용할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="b51c7-131">**50번째 백분위수:** 메시지 배달 시간의 중간입니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="b51c7-132">이 값은 평균 배달 시간으로 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="b51c7-133">이 탭은 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-133">This tab is selected by default.</span></span>
- <span data-ttu-id="b51c7-134">**90번째 백분위수:** 메시지 배달 대기 시간이 길어졌다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="b51c7-135">메시지의 10%만 배달하는 데 이 값보다 오래 걸렸다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="b51c7-136">**99번째 백분위수:** 메시지 배달에 대한 가장 높은 대기 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="b51c7-137">선택한 탭에 관계없이 차트에는 다음 범주로 구성된 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="b51c7-138">**메일 배달 대기 시간**</span><span class="sxs-lookup"><span data-stu-id="b51c7-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="b51c7-139">**Detonations**</span><span class="sxs-lookup"><span data-stu-id="b51c7-139">**Detonations**</span></span>

<span data-ttu-id="b51c7-140">차트의 범주 위에 마우스를 대면 각 범주의 대기 시간 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![메일 대기 시간 보고서의 50번째 백분위수 보기](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="b51c7-142">필터를 **클릭하면** 다음 값으로 차트와 세부 정보 테이블을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="b51c7-143">**날짜(UTC)**: **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="b51c7-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="b51c7-144">**메시지 보기:** 다음 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="b51c7-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="b51c7-145">**모든 메시지**</span><span class="sxs-lookup"><span data-stu-id="b51c7-145">**All messages**</span></span>
  - <span data-ttu-id="b51c7-146">**첨부 파일 또는 URL이 포함된 메시지**</span><span class="sxs-lookup"><span data-stu-id="b51c7-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="b51c7-147">**확인된 메시지**</span><span class="sxs-lookup"><span data-stu-id="b51c7-147">**Detonated messages**</span></span>

<span data-ttu-id="b51c7-148">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b51c7-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b51c7-149">차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b51c7-150">**날짜(UTC)**</span><span class="sxs-lookup"><span data-stu-id="b51c7-150">**Date (UTC)**</span></span>
- <span data-ttu-id="b51c7-151">**백분위수:** **50**, **90** 또는 **99**</span><span class="sxs-lookup"><span data-stu-id="b51c7-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="b51c7-152">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="b51c7-152">**Message count**</span></span>
- <span data-ttu-id="b51c7-153">**전체 대기 시간**</span><span class="sxs-lookup"><span data-stu-id="b51c7-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="b51c7-154">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="b51c7-154">Threat protection status report</span></span>

<span data-ttu-id="b51c7-155">**위협 방지** 상태 보고서는 EOP(Exchange Online Protection) 및 Microsoft Defender에서 검색하고 [](exchange-online-protection-overview.md) 차단하는 악성 콘텐츠 및 악의적인 전자 메일에 대한 정보를 함께 Office 365.</span><span class="sxs-lookup"><span data-stu-id="b51c7-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b51c7-156">자세한 내용은 위협 방지 상태 [보고서를 참조하세요.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b51c7-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="b51c7-157">URL 위협 방지 보고서</span><span class="sxs-lookup"><span data-stu-id="b51c7-157">URL threat protection report</span></span>

<span data-ttu-id="b51c7-158">**URL 위협 방지 보고서는** 검색된 위협에 대한 요약 및 추세 보기와 URL 클릭에 대해 링크의 [일부로 금고 제공합니다.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="b51c7-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="b51c7-159">이 보고서에는 사용자 클릭 추적 안 하도록 옵션을 선택한 금고 링크 정책이 적용된 사용자의 클릭 데이터가 **없습니다.**</span><span class="sxs-lookup"><span data-stu-id="b51c7-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="b51c7-160">보고서를 보시고 Microsoft 365 Defender [포털을](https://security.microsoft.com)열고 보고서  전자 메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="b51c7-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b51c7-161">전자 메일 & **공동 작업 보고서** 페이지에서 URL 보호 페이지를 **찾은** 다음 세부 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b51c7-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="b51c7-162">보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/URLProtectionActionReport> 습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![전자 메일 및 공동 작업 보고서 & URL 보호 보고서 위젯](../../media/url-protection-report-widget.png)

<span data-ttu-id="b51c7-164">다음 섹션에서는 **URL 위협** 방지 보고서 페이지의 사용 가능한 보기에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="b51c7-165">이는 데이터가 더 큰 *데이터* 집합의 추세를 나타내는 보호 추세 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="b51c7-166">따라서 여기에서 차트의 데이터를 실시간으로 사용할 수 없지만 세부 정보 테이블의 데이터는 있으므로 두 데이터 간에 약간의 불일치가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="b51c7-167">차트는 4시간마다 한 번씩 새로 고쳐지며 지난 90일 동안의 데이터를 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="b51c7-168">URL 클릭 보호 작업으로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="b51c7-168">View data by URL click protection action</span></span>

![URL 위협 방지 보고서의 URL 클릭 보호 작업 보기](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="b51c7-170">**URL로 데이터** 보기 보호 작업 보기에는 조직의 사용자가 클릭한 URL 클릭 수와 클릭 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="b51c7-171">**허용:** 사용자가 URL로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="b51c7-172">**차단:** 사용자가 URL로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="b51c7-173">**차단 및 클릭:** 사용자가 URL로 계속 이동하도록 선택</span><span class="sxs-lookup"><span data-stu-id="b51c7-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="b51c7-174">**검사 중 클릭:** 검사가 완료되기 전에 사용자가 링크를 클릭한 경우</span><span class="sxs-lookup"><span data-stu-id="b51c7-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="b51c7-175">클릭은 사용자가 악성 웹 사이트로 차단 페이지를 클릭했다는 것을 나타냅니다(관리자는 링크 정책에서 클릭을 금고 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="b51c7-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="b51c7-176">필터를 **클릭하면** 나타나는 플라이아웃에서 다음 값 중 하나 이상을 선택하여 보고서 및 세부 정보 테이블을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b51c7-177">**날짜(UTC)**: **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="b51c7-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="b51c7-178">**검색**:</span><span class="sxs-lookup"><span data-stu-id="b51c7-178">**Detection**:</span></span>
  - <span data-ttu-id="b51c7-179">**허용됨**</span><span class="sxs-lookup"><span data-stu-id="b51c7-179">**Allowed**</span></span>
  - <span data-ttu-id="b51c7-180">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="b51c7-180">**Blocked**</span></span>
  - <span data-ttu-id="b51c7-181">**차단 및 클릭**</span><span class="sxs-lookup"><span data-stu-id="b51c7-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="b51c7-182">**검사 중 클릭한 기간**</span><span class="sxs-lookup"><span data-stu-id="b51c7-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="b51c7-183">**도메인**: 보고서 결과에 나열된 URL 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="b51c7-184">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="b51c7-184">**Recipients**</span></span>

<span data-ttu-id="b51c7-185">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b51c7-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b51c7-186">차트 아래의 세부 정보 표에서는 지난 7일 동안 조직 내에서 발생된 모든 클릭 수에 대해 다음과 같은 거의 실시간 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="b51c7-187">**클릭 시간**</span><span class="sxs-lookup"><span data-stu-id="b51c7-187">**Click time**</span></span>
- <span data-ttu-id="b51c7-188">**사용자**</span><span class="sxs-lookup"><span data-stu-id="b51c7-188">**User**</span></span>
- <span data-ttu-id="b51c7-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="b51c7-189">**URL**</span></span>
- <span data-ttu-id="b51c7-190">**작업**</span><span class="sxs-lookup"><span data-stu-id="b51c7-190">**Action**</span></span>
- <span data-ttu-id="b51c7-191">**앱**</span><span class="sxs-lookup"><span data-stu-id="b51c7-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="b51c7-192">응용 프로그램으로 클릭한 URL로 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="b51c7-192">View data by URL click by application</span></span>

![URL 위협 방지 보고서의 응용 프로그램 보기로 URL 클릭](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="b51c7-194">응용 **프로그램 보기에서 URL로 데이터** 보기를 클릭하면 링크가 지원되는 앱의 URL 클릭 금고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="b51c7-195">**전자 메일 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="b51c7-195">**Email client**</span></span>
- <span data-ttu-id="b51c7-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="b51c7-196">**PowerPoint**</span></span>
- <span data-ttu-id="b51c7-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="b51c7-197">**Word**</span></span>
- <span data-ttu-id="b51c7-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="b51c7-198">**Excel**</span></span>
- <span data-ttu-id="b51c7-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="b51c7-199">**OneNote**</span></span>
- <span data-ttu-id="b51c7-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="b51c7-200">**Visio**</span></span>
- <span data-ttu-id="b51c7-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="b51c7-201">**Teams**</span></span>
- <span data-ttu-id="b51c7-202">**기타**</span><span class="sxs-lookup"><span data-stu-id="b51c7-202">**Others**</span></span>

<span data-ttu-id="b51c7-203">필터를 **클릭하면** 나타나는 플라이아웃에서 다음 값 중 하나 이상을 선택하여 보고서 및 세부 정보 테이블을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b51c7-204">**날짜(UTC)**: **시작 날짜 및** 종료 **날짜**</span><span class="sxs-lookup"><span data-stu-id="b51c7-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="b51c7-205">**검색:** 차트에서 사용 가능한 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="b51c7-206">**도메인**: 보고서 결과에 나열된 URL 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="b51c7-207">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="b51c7-207">**Recipients**</span></span>

<span data-ttu-id="b51c7-208">필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b51c7-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b51c7-209">차트 아래의 세부 정보 표에서는 지난 7일 동안 조직 내에서 발생된 모든 클릭 수에 대해 다음과 같은 거의 실시간 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="b51c7-210">**클릭 시간**</span><span class="sxs-lookup"><span data-stu-id="b51c7-210">**Click time**</span></span>
- <span data-ttu-id="b51c7-211">**사용자**</span><span class="sxs-lookup"><span data-stu-id="b51c7-211">**User**</span></span>
- <span data-ttu-id="b51c7-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="b51c7-212">**URL**</span></span>
- <span data-ttu-id="b51c7-213">**작업**</span><span class="sxs-lookup"><span data-stu-id="b51c7-213">**Action**</span></span>
- <span data-ttu-id="b51c7-214">**앱**</span><span class="sxs-lookup"><span data-stu-id="b51c7-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="b51c7-215">볼 추가 보고서</span><span class="sxs-lookup"><span data-stu-id="b51c7-215">Additional reports to view</span></span>

<span data-ttu-id="b51c7-216">이 문서에 설명된 보고서 외에도 다음 표에 설명된 몇 가지 다른 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="b51c7-217">보고서</span><span class="sxs-lookup"><span data-stu-id="b51c7-217">Report</span></span>|<span data-ttu-id="b51c7-218">항목</span><span class="sxs-lookup"><span data-stu-id="b51c7-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="b51c7-219">**탐색기(Office 365** 계획 2용 Microsoft Defender) 또는 실시간 검색(Office 365 계획 1용 Microsoft Defender) </span><span class="sxs-lookup"><span data-stu-id="b51c7-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="b51c7-220">위협 탐색기 (실시간 검출)</span><span class="sxs-lookup"><span data-stu-id="b51c7-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="b51c7-221">**전자 메일 보안 보고서(** 예: 상위 보낸 사람 및 받는 사람 보고서, 스푸핑 메일 보고서 및 스팸 검색 보고서)</span><span class="sxs-lookup"><span data-stu-id="b51c7-221">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="b51c7-222">전자 메일 포털에서 전자 메일 Microsoft 365 Defender 보기</span><span class="sxs-lookup"><span data-stu-id="b51c7-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="b51c7-223">**메일 흐름 보고서(** 예: 전달 보고서, 메일 흐름 상황 보고서 및 최상위 보낸 사람 및 받는 사람 보고서)</span><span class="sxs-lookup"><span data-stu-id="b51c7-223">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="b51c7-224">새 관리 센터의 메일 흐름 Exchange 보고서</span><span class="sxs-lookup"><span data-stu-id="b51c7-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|<span data-ttu-id="b51c7-225">**링크에 금고 URL** 추적(PowerShell에만 해당).</span><span class="sxs-lookup"><span data-stu-id="b51c7-225">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="b51c7-226">이 cmdlet의 출력은 지난 7일 동안의 금고 링크 작업의 결과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-226">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="b51c7-227">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="b51c7-227">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="b51c7-228">**EOP 및 Microsoft Defender for Office 365** 메일 트래픽 결과(PowerShell에만 해당)</span><span class="sxs-lookup"><span data-stu-id="b51c7-228">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="b51c7-229">이 cmdlet의 출력에는 Domain, Date, Event Type, Direction, Action 및 Message Count에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-229">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="b51c7-230">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="b51c7-230">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="b51c7-231">**전자 메일 검색에 대한 EOP 및 Defender에 대한 Office 365 보고서입니다(PowerShell에만** 해당).</span><span class="sxs-lookup"><span data-stu-id="b51c7-231">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="b51c7-232">이 cmdlet의 출력에는 악성 파일 또는 URL, 피싱 시도, 가장 및 전자 메일 또는 파일의 기타 잠재적 위협에 대한 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-232">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="b51c7-233">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="b51c7-233">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="b51c7-234">보고서에 대한 Defender를 보는 데 Office 365 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="b51c7-234">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="b51c7-235">이 문서에 설명된 보고서를 보고 사용하려면 Microsoft 365 Defender 포털에서 다음 역할 그룹 중 하나에 Microsoft 365 Defender 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-235">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="b51c7-236">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="b51c7-236">**Organization Management**</span></span>
- <span data-ttu-id="b51c7-237">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="b51c7-237">**Security Administrator**</span></span>
- <span data-ttu-id="b51c7-238">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="b51c7-238">**Security Reader**</span></span>
- <span data-ttu-id="b51c7-239">**전역 읽기**</span><span class="sxs-lookup"><span data-stu-id="b51c7-239">**Global Reader**</span></span>

<span data-ttu-id="b51c7-240">자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b51c7-240">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="b51c7-241">**참고:** Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한과 Microsoft 365 Defender 포털의 다른  기능에 대한 사용 권한이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b51c7-241">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b51c7-242">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b51c7-242">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="b51c7-243">보고서에 데이터가 표시되지 않는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="b51c7-243">What if the reports aren't showing data?</span></span>

<span data-ttu-id="b51c7-244">보고서에 대한 Defender에 Office 365 없는 경우 정책이 올바르게 설정되어 있는지 다시 한 번 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-244">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="b51c7-245">조직에서 보호 기능을 [금고](set-up-safe-links-policies.md) 수 [](set-up-safe-attachments-policies.md) 있도록 금고 링크 정책 및 금고 첨부 파일 정책이 Office 365 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51c7-245">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="b51c7-246">또한 스팸 [방지 및 맬웨어 방지 보호를 참조합니다.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b51c7-246">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b51c7-247">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b51c7-247">Related topics</span></span>

[<span data-ttu-id="b51c7-248">검색 포털의 스마트 보고서 및 Microsoft 365 Defender 정보</span><span class="sxs-lookup"><span data-stu-id="b51c7-248">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b51c7-249">역할 권한(Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b51c7-249">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
