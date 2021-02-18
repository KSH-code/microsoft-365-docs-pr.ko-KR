---
title: 위협 탐색기 및 실시간 검색 보기
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 위협 탐색기 및 실시간 검색 보고서를 사용하여 보안 및 준수 센터에서 위협을 조사하고 & 방법에 대해 자세히 알아보십시오.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aef3f7fe69e5cbd1d70b7aee3284f0c5dc6416df
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290288"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="b2eb1-103">위협 탐색기 및 실시간 검색 보기</span><span class="sxs-lookup"><span data-stu-id="b2eb1-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b2eb1-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="b2eb1-104">**Applies to**</span></span>
- [<span data-ttu-id="b2eb1-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="b2eb1-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b2eb1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2eb1-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![위협 탐색기](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="b2eb1-108">[위협](threat-explorer.md) 탐색기(및 실시간 검색 보고서)는 보안 운영 팀이 보안 및 준수 센터에서 위협을 조사하고 대응하는 데 도움이 되는 강력한 거의 & 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="b2eb1-109">탐색기(및 실시간 검색 보고서)는 Office 365의 전자 메일 및 파일에 의심되는 맬웨어 및 피싱과 조직에 대한 기타 보안 위협 및 위험에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="b2eb1-110">[Office 365 요금제 2용 Microsoft Defender가](office-365-atp.md) 있는 경우 탐색기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="b2eb1-111">Office 365 요금제 1용 Microsoft Defender가 있는 경우 실시간 검색이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="b2eb1-112">탐색기(또는 실시간 검색 보고서)를 처음 열면 기본 보기에 지난 7일 동안의 전자 메일 맬웨어 검색이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="b2eb1-113">또한 이 보고서에는 안전한 링크로 검색된 악의적인 URL, 안전한 첨부 [](atp-safe-links.md)파일에서 검색된 악성 파일 등 Office 365용 Microsoft Defender 검색이 표시될 [수도 있습니다.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="b2eb1-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="b2eb1-114">이 보고서는 지난 30일 동안의 데이터를 표시하기 위해 수정할 수 있습니다(Office 365 P2 유료 구독용 Microsoft Defender 사용).</span><span class="sxs-lookup"><span data-stu-id="b2eb1-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="b2eb1-115">평가판 구독에는 지난 7일 동안의 데이터만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="b2eb1-116">구독</span><span class="sxs-lookup"><span data-stu-id="b2eb1-116">Subscription</span></span>|<span data-ttu-id="b2eb1-117">유틸리티</span><span class="sxs-lookup"><span data-stu-id="b2eb1-117">Utility</span></span>|<span data-ttu-id="b2eb1-118">데이터 일 수</span><span class="sxs-lookup"><span data-stu-id="b2eb1-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="b2eb1-119">Microsoft Defender for Office 365 P1 평가판</span><span class="sxs-lookup"><span data-stu-id="b2eb1-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="b2eb1-120">실시간 탐지</span><span class="sxs-lookup"><span data-stu-id="b2eb1-120">Real-time detections</span></span>|<span data-ttu-id="b2eb1-121">7 </span><span class="sxs-lookup"><span data-stu-id="b2eb1-121">7</span></span>|
|<span data-ttu-id="b2eb1-122">Office 365 P1용 Microsoft Defender 유료</span><span class="sxs-lookup"><span data-stu-id="b2eb1-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="b2eb1-123">실시간 탐지</span><span class="sxs-lookup"><span data-stu-id="b2eb1-123">Real-time detections</span></span>|<span data-ttu-id="b2eb1-124">30</span><span class="sxs-lookup"><span data-stu-id="b2eb1-124">30</span></span>|
|<span data-ttu-id="b2eb1-125">Office 365 P1용 Microsoft Defender 유료 테스트 Defender for Office 365 P2 평가판</span><span class="sxs-lookup"><span data-stu-id="b2eb1-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="b2eb1-126">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="b2eb1-126">Threat Explorer</span></span>|<span data-ttu-id="b2eb1-127">7 </span><span class="sxs-lookup"><span data-stu-id="b2eb1-127">7</span></span>|
|<span data-ttu-id="b2eb1-128">Microsoft Defender for Office 365 P2 평가판</span><span class="sxs-lookup"><span data-stu-id="b2eb1-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="b2eb1-129">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="b2eb1-129">Threat Explorer</span></span>|<span data-ttu-id="b2eb1-130">7 </span><span class="sxs-lookup"><span data-stu-id="b2eb1-130">7</span></span>|
|<span data-ttu-id="b2eb1-131">Office 365 P2용 Microsoft Defender 유료</span><span class="sxs-lookup"><span data-stu-id="b2eb1-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="b2eb1-132">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="b2eb1-132">Threat Explorer</span></span>|<span data-ttu-id="b2eb1-133">30</span><span class="sxs-lookup"><span data-stu-id="b2eb1-133">30</span></span>|
|

<span data-ttu-id="b2eb1-134">보기 **메뉴를** 사용하여 표시되는 정보를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-134">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="b2eb1-135">도구tips를 사용하면 사용할 보기를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-135">Tooltips help you determine which view to use.</span></span>

![위협 탐색기 보기 메뉴](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="b2eb1-137">보기를 선택한 후 필터를 적용하고 추가 분석을 수행하기 위한 쿼리를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-137">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="b2eb1-138">다음 섹션에서는 탐색기에서 사용할 수 있는 다양한 보기(또는 실시간 검색)에 대한 간략한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-138">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="b2eb1-139">전자 메일 > 맬웨어</span><span class="sxs-lookup"><span data-stu-id="b2eb1-139">Email > Malware</span></span>

<span data-ttu-id="b2eb1-140">이 보고서를 확인하려면 탐색기(또는 실시간 검색)에서 전자 메일 맬웨어  \>  \> **보기를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b2eb1-140">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="b2eb1-141">이 보기에는 맬웨어가 포함된 것으로 확인된 전자 메일 메시지에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-141">This view shows information about email messages that were identified as containing malware.</span></span>

![맬웨어로 식별된 전자 메일에 대한 데이터 보기](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="b2eb1-143">보낸 **사람 클릭하여** 보기 옵션 목록을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-143">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="b2eb1-144">이 목록을 사용하여 보낸 사람, 받는 사람, 보낸 사람 도메인, 제목, 검색 기술, 보호 상태 등에서 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-144">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="b2eb1-145">예를 들어 검색된 전자 메일 메시지에 대해 수행된 작업을 확인하기 위해 목록에서 **보호** 상태를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-145">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="b2eb1-146">옵션을 선택한 다음 새로 고침 단추를 클릭하여 보고서에 해당 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-146">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![위협 탐색기용 위협 방지 상태 옵션](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="b2eb1-148">차트 아래에서 특정 메시지에 대한 자세한 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-148">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="b2eb1-149">목록에서 항목을 선택하면 선택한 항목에 대한 자세한 내용을 볼 수 있는 플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-149">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![플라이아웃이 열린 위협 탐색기](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="b2eb1-151">피싱 > 메일</span><span class="sxs-lookup"><span data-stu-id="b2eb1-151">Email > Phish</span></span>

<span data-ttu-id="b2eb1-152">이 보고서를 확인하려면 탐색기(또는 실시간 검색)에서 전자 메일 피싱  \>  \> **보기를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b2eb1-152">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="b2eb1-153">이 보기에는 피싱 시도로 식별된 전자 메일 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-153">This view shows email messages identified as phishing attempts.</span></span>

![피싱 시도로 식별된 전자 메일에 대한 데이터 보기](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="b2eb1-155">보낸 **사람 클릭하여** 보기 옵션 목록을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-155">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="b2eb1-156">이 목록을 사용하여 보낸 사람, 받는 사람, 보낸 사람 도메인, 보낸 사람 IP, URL 도메인, 클릭 판정 등에서 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-156">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="b2eb1-157">예를 들어 피싱 시도로 식별된 URL을 클릭할 때 수행된 작업을 보려면  목록에서 판정 클릭을 선택하고 하나 이상의 옵션을 선택한 다음 새로 고침 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-157">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![피싱 보고서에 대한 결과 옵션 클릭](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="b2eb1-159">차트 아래에서 특정 메시지, URL 클릭, URL 및 전자 메일 출처에 대한 자세한 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-159">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![전자 메일 메시지에서 피싱으로 검색된 URL](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="b2eb1-161">목록에서 항목(예: 검색된 URL)을 선택하면 선택한 항목에 대한 자세한 내용을 볼 수 있는 플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-161">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![검색된 URL에 대한 세부 정보](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="b2eb1-163">전자 > 제출</span><span class="sxs-lookup"><span data-stu-id="b2eb1-163">Email > Submissions</span></span>

<span data-ttu-id="b2eb1-164">이 보고서를 확인하려면 탐색기(또는 실시간 검색)에서 전자 메일 제출  \>  \> **보기를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b2eb1-164">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="b2eb1-165">이 보기에는 사용자가 정크 메일, 정크 메일 또는 피싱 전자 메일로 보고한 전자 메일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-165">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![사용자가 보고한 전자 메일 메시지](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="b2eb1-167">보낸 **사람 클릭하여** 보기 옵션 목록을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-167">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="b2eb1-168">이 목록을 사용하여 보낸 사람, 받는 사람, 보고서 유형(전자 메일이 정크 메일이 아닌 정크 메일 또는 피싱으로 확인) 등별로 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-168">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="b2eb1-169">예를 들어 피싱 시도로 보고된 전자 메일 메시지에 대한  정보를 보려면 보낸 사람 보고서 유형을 클릭하고 \>  **피싱을** 선택한 다음 새로 고침 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-169">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![보고서 유형 필터에 대해 선택한 피싱](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="b2eb1-171">차트 아래에서 제목 줄, 보낸 사람 IP 주소, 메시지를 정크 메일로 보고한 사용자, 정크 메일 메시지 또는 피싱 등의 특정 전자 메일 메시지에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-171">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![피싱 시도로 보고된 메시지](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="b2eb1-173">목록에서 항목을 선택하여 추가 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-173">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="b2eb1-174">전자 메일 > 모든 전자 메일</span><span class="sxs-lookup"><span data-stu-id="b2eb1-174">Email > All email</span></span>

<span data-ttu-id="b2eb1-175">이 보고서를 확인하려면 탐색기에서 **전자** 메일 모두 \>  \> **보기를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b2eb1-175">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="b2eb1-176">이 보기는 피싱 또는 맬웨어로 인해 악의적인 것으로 식별된 전자 메일뿐만 아니라 모든 악성 메일(일반 전자 메일, 스팸 및 대량 메일)을 포함하여 전자 메일 활동에 대한 전체 보기를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-176">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="b2eb1-177">표시할 데이터가 너무 많을 경우 필터를 추가하고 필요한 경우 보고 있는 날짜 범위를 좁힐 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="b2eb1-177">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="b2eb1-178">필터를 적용하려면 **보낸** 사람, 목록에서 항목을 선택한 다음 새로 고침 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-178">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="b2eb1-179">이 예제에서는 검색  기술을 필터로 사용했습니다(몇 가지 옵션을 사용할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="b2eb1-179">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="b2eb1-180">보낸 사람, 보낸 사람의 도메인, 받는 사람, 제목, 첨부 파일 이름, 맬웨어 패밀리, 보호 상태(Office 365의 위협 방지 기능 및 정책에 의해 수행되는 작업), 검색 기술(맬웨어가 검색된 방법) 등으로 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-180">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![검색 기술로 검색된 전자 메일에 대한 데이터 보기](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="b2eb1-182">차트 아래에서 제목 줄, 받는 사람, 보낸 사람, 상태 등 특정 전자 메일 메시지에 대한 자세한 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-182">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="b2eb1-183">콘텐츠 > 맬웨어</span><span class="sxs-lookup"><span data-stu-id="b2eb1-183">Content > Malware</span></span>

<span data-ttu-id="b2eb1-184">이 보고서를 보고 탐색기(또는 실시간 검색)에서 콘텐츠 맬웨어  \> **보기를** \> **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b2eb1-184">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="b2eb1-185">이 보기는 SharePoint Online, 비즈니스용 [OneDrive 및 Microsoft Teams에서 Office 365용 Microsoft Defender에](atp-for-spo-odb-and-teams.md)의해 악성으로 식별된 파일을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-185">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="b2eb1-186">맬웨어 패밀리, 검색 기술(맬웨어가 검색된 방법) 및 워크로드(OneDrive, SharePoint 또는 Teams)를 통해 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-186">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![검색된 맬웨어에 대한 데이터 보기](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="b2eb1-188">차트 아래에서 첨부 파일 이름, 작업량, 파일 크기, 파일을 마지막으로 수정한 사람 등 특정 파일에 대한 자세한 정보를 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-188">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="b2eb1-189">Click-to-filter capabilities</span><span class="sxs-lookup"><span data-stu-id="b2eb1-189">Click-to-filter capabilities</span></span>

<span data-ttu-id="b2eb1-190">탐색기(및 실시간 검색)를 사용하여 클릭으로 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-190">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="b2eb1-191">범례에서 항목을 클릭하면 해당 항목이 보고서의 필터가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-191">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="b2eb1-192">예를 들어 탐색기에서 맬웨어 보기를 보고 있는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-192">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![위협 관리 \> 탐색기로 이동](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="b2eb1-194">이 **차트에서 ATP** 검색을 클릭하면 보기가 다음으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-194">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Office 365 검색 결과용 Defender만 표시하기 위해 필터링된 탐색기](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="b2eb1-196">이 보기에서는 이제 안전한 첨부 파일로 검색된 파일에 대한 [데이터를 보고 있습니다.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="b2eb1-196">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="b2eb1-197">차트 아래에서는 안전한 첨부 파일에서 검색된 첨부 파일이 있는 특정 전자 메일 메시지에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-197">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![검색된 첨부 파일이 있는 전자 메일 메시지에 대한 특정 세부 정보](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="b2eb1-199">하나 이상의 항목을 선택하면 **동작** 메뉴가 활성화되어 선택한 항목에 대해 선택할 수 있는 여러 가지 선택 항목이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-199">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![항목을 선택하면 동작 메뉴가 활성화됩니다.](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="b2eb1-201">클릭으로 필터링하고 특정 세부 정보로 이동하는 기능을 사용하면 위협을 조사하는 데 많은 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-201">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="b2eb1-202">쿼리 및 필터</span><span class="sxs-lookup"><span data-stu-id="b2eb1-202">Queries and filters</span></span>

<span data-ttu-id="b2eb1-203">탐색기(및 실시간 검색 보고서)에는 상위 대상 사용자, 상위 맬웨어 패밀리, 검색 기술 등의 세부 정보를 드릴다운할 수 있는 몇 가지 강력한 필터 및 쿼리 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-203">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="b2eb1-204">각 보고서 종류는 데이터를 보고 탐색하는 다양한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-204">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2eb1-205">탐색기(또는 실시간 검색)에 대한 쿼리 표시줄에 추가 또는 물음표와 같은 와일드카드 문자를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-205">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="b2eb1-206">제목 필드에서  전자 메일 메시지를 검색할 때 탐색기(또는 실시간 검색)는 부분 일치를 수행하고 와일드카드 검색과 유사한 결과를 산출합니다.</span><span class="sxs-lookup"><span data-stu-id="b2eb1-206">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
