---
title: 위협 탐색기 및 실시간 검색
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 보안 및 준수 센터에서 Explorer 및 실시간 검색을 사용 하 여 위협에 효과적이 고 효율적으로 대응 하는 방법에 대해 알아봅니다 &amp; .
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89708efa6a34b5ca7a302ba0ad331a2dac99f5d9
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477181"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="e40ba-103">위협 탐색기 및 실시간 검색</span><span class="sxs-lookup"><span data-stu-id="e40ba-103">Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e40ba-104">조직에 [office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP)이 있고 [필요한 사용 권한이](#required-licenses-and-permissions)있는 경우에는 **Explorer** 또는 **실시간** 검색 (이전에는 [새로운 기능을 참조 하세요](#new-features-in-threat-explorer-and-real-time-detections) *.)을* 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="e40ba-105">보안 & 준수 센터에서 **위협 관리**로 이동한 다음 **Explorer** _또는_ **실시간**검색을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

|<span data-ttu-id="e40ba-106">ATP 계획 2를 사용 하는 경우 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-106">With ATP Plan 2, you see:</span></span>|<span data-ttu-id="e40ba-107">ATP 계획 1을 사용 하는 경우 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-107">With ATP Plan 1, you see:</span></span>|
|---|---|
|![위협 탐색기](../../media/threatmgmt-explorer.png)|![실시간 탐지](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="e40ba-110">Explorer (또는 실시간 검색)를 사용 하는 경우 보안 운영 팀이 효과적이 고 효율적으로 위협을 조사 하 고 대응 하는 데 사용할 수 있는 강력한 보고서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently.</span></span> <span data-ttu-id="e40ba-111">보고서는 다음 이미지와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-111">The report resembles the following image:</span></span>

![위협 관리 탐색기로 이동 \>](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="e40ba-113">이 보고서를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-113">With this report, you can:</span></span>

- [<span data-ttu-id="e40ba-114">Microsoft 365 보안 기능으로 검색 된 맬웨어를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e40ba-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="e40ba-115">피싱 Url에 대 한 데이터를 확인 하 고 결과를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-115">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="e40ba-116">[탐색기에서 보기 로부터 자동화 된 조사 및 응답 프로세스 시작](#start-automated-investigation-and-response) (ATP 요금제 2에만 해당)</span><span class="sxs-lookup"><span data-stu-id="e40ba-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="e40ba-117">... [악성 전자 메일을 조사 하 고 더 많은 방법을 확인해](#more-ways-to-use-explorer-or-real-time-detections)보세요.</span><span class="sxs-lookup"><span data-stu-id="e40ba-117">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="tags-in-threat-explorer"></a><span data-ttu-id="e40ba-118">위협 탐색기의 태그</span><span class="sxs-lookup"><span data-stu-id="e40ba-118">Tags in Threat Explorer</span></span>

> [!NOTE] 
> <span data-ttu-id="e40ba-119">사용자 태그 기능은 미리 보기에서 모든 사용자가 사용할 수 없으며 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-119">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="e40ba-120">릴리스 일정에 대 한 자세한 내용은 Microsoft 365 로드맵를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e40ba-120">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="e40ba-121">사용자 태그는 Microsoft Defender for Office 365의 특정 사용자 그룹에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-121">User tags are identifiers for specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e40ba-122">태그에 대 한 자세한 내용, 태그 라이선스 및 구성에 대 한 자세한 내용은 [Office 365 ATP의 사용자 태그](user-tags.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e40ba-122">For more information around Tags, licensing and configuring Tags, read more here: [User tags in Office 365 ATP](user-tags.md).</span></span>

<span data-ttu-id="e40ba-123">위협 탐색기 내에서 사용자 태그에 대 한 정보를 볼 수 있는 경험은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-123">Within Threat Explorer, you will be able to see information around User Tags in the following experiences:</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="e40ba-124">전자 메일 표 보기</span><span class="sxs-lookup"><span data-stu-id="e40ba-124">Email Grid View</span></span>

<span data-ttu-id="e40ba-125">전자 메일 표에 표시 되는 태그 열에는 보낸 사람 또는 받는 사람 사서함에 적용 된 모든 태그가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-125">The Tags column shown in the email grid would contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="e40ba-126">기본적으로 우선 순위 계정과 같은 시스템 태그가 먼저 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-126">By default, system tags like priority accounts are shown first.</span></span>

![필터 태그](../../media/tags-grid.png)

#### <a name="filtering"></a><span data-ttu-id="e40ba-128">필터링</span><span class="sxs-lookup"><span data-stu-id="e40ba-128">Filtering</span></span>
<span data-ttu-id="e40ba-129">이제는 태그를 필터로 사용 하 여 우선 순위 계정 또는 특정 사용자 태그 시나리오를 검색 하 고 특정 태그에서 결과를이 환경의 일부로 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-129">We now have Tags as a filter so you can hunt just across priority accounts, or specific User tags scenarios (and even exclude results with certain tags as part of this experience).</span></span> <span data-ttu-id="e40ba-130">이러한 정보를 제공 하는 여러 필터를 결합 하 여 조사 범위를 좁히는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-130">Combining these with the multiple other filters that we provide, would help you to narrow down your scope of investigation</span></span>

![필터 태그](../../media/tags-filter-normal.png)

![필터 태그 아님](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a><span data-ttu-id="e40ba-133">전자 메일 세부 정보 플라이 아웃</span><span class="sxs-lookup"><span data-stu-id="e40ba-133">Email Detail Flyout</span></span>
<span data-ttu-id="e40ba-134">보낸 사람과 받는 사람에 대 한 개별 태그를 보려면 제목을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-134">To view the individual tags for sender and Recipient, click on the subject.</span></span> <span data-ttu-id="e40ba-135">메시지 세부 정보 플라이 아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-135">It opens the message details flyout.</span></span> <span data-ttu-id="e40ba-136">요약 탭에서는 전자 메일을 보낼 때 보낸 사람 및 받는 사람 태그가 별도로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-136">In the summary tab, sender and recipient tags are shown separately, if they are present for an email.</span></span>
<span data-ttu-id="e40ba-137">보낸 사람과 받는 사람에 대 한 개별 태그에 대 한 정보는 내보낸 CSV로 확장 되며, 이러한 세부 정보를 두 개의 개별 열에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-137">The information about individual tags for sender and Recipient, also extends to exported CSV, where you can see these details in 2 separate columns.</span></span> 

![전자 메일 세부 정보 태그](../../media/tags-flyout.png)

<span data-ttu-id="e40ba-139">태그 정보는 URL 클릭 시 플라이 아웃에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-139">Tags information is also shown in URL clicks flyout.</span></span> <span data-ttu-id="e40ba-140">URL로 이동 하려면 플라이 아웃을 클릭 하 고, url 또는 URL 클릭 탭에 대 한 자세한 정보를 보려면 개별 URL 플라이 아웃을 클릭 하 여 해당 URL의 클릭에 대 한 자세한 내용을 표시 하 고, 해당 클릭과 관련 된 태그를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-140">To get to the URL clicks flyout, you would need to go to Phish or All Email view, and then to URLs or URL Clicks Tab. Clicking on an individual URL flyout would show more details about Clicks for that URL, and would have Tags associated with that click.</span></span> 

![URL 태그](../../media/tags-urls.png)

## <a name="improvements-to-threat-hunting-experience-upcoming"></a><span data-ttu-id="e40ba-142">위협 요소 구하기 환경 개선 (다가오는 예정)</span><span class="sxs-lookup"><span data-stu-id="e40ba-142">Improvements to Threat Hunting Experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="e40ba-143">전자 메일에 대 한 업데이트 된 위협 정보</span><span class="sxs-lookup"><span data-stu-id="e40ba-143">Updated Threat Information for Emails</span></span>

<span data-ttu-id="e40ba-144">전자 메일 레코드의 데이터 정확성과 일관성을 높이기 위해 플랫폼 및 데이터 품질 개선에 중점을 두었습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-144">We have focused on platform and data quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="e40ba-145">이러한 업데이트 집합에는 배달 전 및 배달 전 정보 (예: 전자 메일에 대해 ZAP 프로세스의 일부로 실행 되는 작업)가 단일 레코드에 포함 되어 있으며,이는 스팸 결과, 엔터티 수준 위협 (URL은 악성) 및 최신 배달 위치와 같은 추가 된 다양성과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-145">These set of updates includes consolidation of pre-delivery and post-delivery information (example action executed on an email as part of ZAP process) into a single record  along with added richness like Spam verdict, Entity level threats (e.g., which URL was malicious) and latest delivery locations.</span></span> 

<span data-ttu-id="e40ba-146">이러한 업데이트 후에는 메시지에 대해 발생 한 다른 배달 후 이벤트에 관계 없이 각 메시지에 대해 단일 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-146">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that have taken place on the message.</span></span> <span data-ttu-id="e40ba-147">작업에는 ZAP, 수동 재구성 (관리 작업을 의미), 동적 배달 등이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-147">Actions can include ZAP, Manual Remediation (which means admin action), Dynamic Delivery etc.</span></span> 

<span data-ttu-id="e40ba-148">이제 맬웨어 및 피싱 위협을 표시 하는 것 외에도 전자 메일과 연결 된 스팸 결과 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-148">In addition to showing malware and phish threats, you'll now be able to see spam verdict associated with an email.</span></span> <span data-ttu-id="e40ba-149">전자 메일 내에서 전자 메일과 관련 된 모든 위협을 해당 검색 기술과 함께 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-149">Within the email, you will be able to see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="e40ba-150">각 전자 메일에는 0 개, 1 개 또는 여러 개의 위협이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-150">Each email can have 0, 1, or multiple threats.</span></span> <span data-ttu-id="e40ba-151">전자 메일 플라이 아웃의 세부 정보 섹션에 현재 위협이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-151">You'll see the current Threats in the Details section of the Email flyout.</span></span> <span data-ttu-id="e40ba-152">또한 여러 위협의 경우 (예: 맬웨어 및 피싱이 둘 다 있는 전자 메일) 검색 기술 필드는 Threat-Detection 매핑을 제공 하 여 위협 식별을 위한 검색 기술에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-152">Additionally, for multiple threats (e.g., an email having both Malware and Phish), Detection tech field would give the Threat-Detection mapping, meaning which detection tech led to the identification of the Threat.</span></span>

<span data-ttu-id="e40ba-153">검색 기술 집합은 새로운 검색 방법 뿐 아니라 스팸 감지 기술 및 모든 다른 전자 메일 보기 (맬웨어, 피싱, 모든 전자 메일)에 걸쳐 결과를 필터링 할 수 있는 동일한 수준의 검색 기술이 제공 되도록 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-153">The set of detection technologies has been updated to include new detection methods, as well as spam detection technologies, and across all the different email views (Malware, Phish, All Email), you'll have the same, consistent set of Detection technologies to filter the results.</span></span> 

> [!NOTE]
> <span data-ttu-id="e40ba-154">결과 분석이 반드시 엔터티에 연결 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-154">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="e40ba-155">예를 들어 전자 메일은 피싱 또는 스팸으로 분류 되지만 피싱/스팸 결과 스탬프를 포함 하는 Url은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-155">As an example, an email might be classified as Phish or Spam, but there are no URLs which have any Phish/Spam verdict stamped on them.</span></span> <span data-ttu-id="e40ba-156">이는 결과를 할당 하기 전에 필터에서 콘텐츠와 전자 메일에 대 한 기타 세부 정보를 평가 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-156">This is because our filters also evaluate content and other details for an email, before assigning a verdict.</span></span> 
 
#### <a name="threats-in-urls"></a><span data-ttu-id="e40ba-157">Url의 위협</span><span class="sxs-lookup"><span data-stu-id="e40ba-157">Threats in URLs</span></span>

<span data-ttu-id="e40ba-158">이제 전자 메일 플라이 아웃-> 세부 정보 탭에서 URL에 대 한 특정 위협을 볼 수 있습니다 (URL에 대 한 위협: 맬웨어, 피싱, 스팸 또는 없음).</span><span class="sxs-lookup"><span data-stu-id="e40ba-158">Within email flyout-> Details tab, you would now be able to see the specific threat for a URL (Threat for a URL can be Malware, Phish, Spam or None)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-159">![URL 위협](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-159">![URL Threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="e40ba-160">업데이트 된 시간 표시 막대 보기 (예정 됨)</span><span class="sxs-lookup"><span data-stu-id="e40ba-160">Updated Timeline View (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-161">![업데이트 된 시간 표시 막대 보기](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-161">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="e40ba-162">시간 표시 막대 보기는 모든 배달 및 배달 후 이벤트를 식별 하는 것 외에도 이러한 이벤트의 하위 집합에 대 한 해당 시점에 식별 된 위협에 대 한 정보도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-162">In addition to identifying all delivery and post-delivery events, timeline view also gives information about the Threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="e40ba-163">또한이 작업의 결과와 함께 ZAP, 수동 재구성 등의 추가 작업에 대 한 자세한 정보도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-163">It also gives you more information about Additional Actions (e.g., ZAP, Manual Remediation) along with the Result of that action.</span></span> <span data-ttu-id="e40ba-164">시간 표시 막대 보기에는 원래 배달에 대 한 정보와 이후에 전자 메일에 대해 수행 된 배달 후 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-164">Timeline view contains information about the Original delivery and subsequently any post-delivery events performed on an email.</span></span>

-   <span data-ttu-id="e40ba-165">원본:이는 이벤트의 출처를 기반으로 하는 관리자/시스템/사용자 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-165">Source: This can be Admin/System/user based on what was the source of the event.</span></span>
-   <span data-ttu-id="e40ba-166">이벤트: 원래 배달, 수동 재구성, ZAP, 전송, 동적 배달과 같은 최상위 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-166">Event: This includes top-level events like Original Delivery, Manual Remediation, ZAP, Submissions, and Dynamic Delivery.</span></span>
-   <span data-ttu-id="e40ba-167">작업:이 작업은 ZAP 또는 관리 작업 (예: 소프트 삭제)의 일부로 수행 된 특정 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-167">Action: This covers the specific action that was taken either as part of ZAP or Admin Action (e.g., Soft Delete).</span></span>
-   <span data-ttu-id="e40ba-168">위협: 해당 시점에 식별 된 위협 (맬웨어, 피싱, 스팸)을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-168">Threats: Covers the threats (Malware, Phish, Spam) identified at that point of time.</span></span>
-   <span data-ttu-id="e40ba-169">Result/Details: 작업 결과에 대 한 자세한 내용은 ZAP/Admin 작업의 일부로 수행 되었는지 여부에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-169">Result/Details: Covers more information about the Result of the Action, whether it was performed as part of ZAP/Admin Action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="e40ba-170">원본 및 최신 배달 위치</span><span class="sxs-lookup"><span data-stu-id="e40ba-170">Original and Latest Delivery location</span></span>

<span data-ttu-id="e40ba-171">오늘날에는 전자 메일 표 및 전자 메일 플라이 아웃 내에 배달 위치가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-171">Today, we surface delivery Location within email grid and email flyout.</span></span> <span data-ttu-id="e40ba-172">전달 되는 경우 배달 위치 필드의 이름이 원래 배달 위치로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-172">Going forward, the Delivery Location field will be renamed to Original Delivery Location.</span></span> <span data-ttu-id="e40ba-173">또한 최신 배달 위치 라는 다른 필드도 소개 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-173">Additionally, we're also introducing another field called Latest delivery location.</span></span> 

<span data-ttu-id="e40ba-174">원래 배달 위치는 처음에 전자 메일이 배달 된 위치에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-174">The original delivery location would give more information about where an email was delivered initially.</span></span> <span data-ttu-id="e40ba-175">최신 배달 위치에는 전자 메일에서 **삭제 된 항목으로 이동**같은 ZAP 또는 관리 작업 등의 시스템 작업을 수행 하 여 마법사로 돌아갑니다 수 있는 위치가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-175">The latest delivery location would include location where an email may have landed after system actions like ZAP or admin actions like **Move to Deleted Items**.</span></span> <span data-ttu-id="e40ba-176">최신 배달 위치는 메시지의 마지막으로 알려진 위치, 배달 후 또는 시스템/관리자 작업을 관리자에 게 알리기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-176">Latest delivery location is intended to inform admins of the message's last known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="e40ba-177">기본적으로 전자 메일에는 최종 사용자 관련 작업이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-177">By design, it doesn't include any end-user-related actions on the email.</span></span> <span data-ttu-id="e40ba-178">예를 들어 사용자가 메시지를 삭제 하거나 메시지를 보관/pst로 옮기면 메시지 "배달" 위치가 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-178">For example: if a user deletes a message or moves the message to archive/pst, the message "delivery" location will not be updated.</span></span> <span data-ttu-id="e40ba-179">그러나 시스템 작업에서 위치를 업데이트 하는 경우 (예: 전자 메일을 격리로 이동 하는 ZAP) 최신 배달 위치가 격리로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-179">However, if a system action updated the location (e.g., ZAP resulting in an email moving to Quarantine), you would see the Latest delivery location as Quarantine.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-180">![업데이트 된 배달 위치](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-180">![Updated Delivery Locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="e40ba-181">배달 위치 및 배달 작업에서 ' 알 수 없음 '이 값으로 표시 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-181">There are few cases where Delivery Location and Delivery Action may show 'Unknown' as the value:</span></span>
> 
> - <span data-ttu-id="e40ba-182">배달 위치가 배달 됨 및 알 수 없는 배달 위치로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-182">You might see Delivery location as Delivered, and Delivery Location as Unknown.</span></span> <span data-ttu-id="e40ba-183">메시지가 배달 되었지만 받은 편지함 규칙에서 받은 편지함 또는 정크 메일 폴더 대신 기본 폴더 (임시, 보관 등)로 메시지를 이동한 경우에 이러한 상황이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-183">This happens when the message was delivered, but an Inbox rule moved the message to a default folder (Draft, Archive, etc.) instead of the Inbox or Junk Email folders.</span></span> 
> 
> - <span data-ttu-id="e40ba-184">최신 배달 위치는 관리/시스템 작업 (예: ZAP, 관리 작업)을 시도 했지만 해당 메시지가 없는 경우 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-184">Latest Delivery Location can be unknown if an admin/system action (e.g., ZAP, Admin Action) is attempted, but the message isn't found.</span></span> <span data-ttu-id="e40ba-185">일반적으로이 작업은 사용자가 메시지를 이동 하거나 삭제 한 후에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-185">Typically, the action happens after the user has moved or deleted the Message.</span></span> <span data-ttu-id="e40ba-186">이러한 경우 시간 표시 막대 보기에서 결과/세부 정보 열을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-186">In such cases, verify the Result/Details Column in timeline view.</span></span> <span data-ttu-id="e40ba-187">메시지가 사용자에 의해 이동 또는 삭제 된 메시지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-187">Look for the message: Message moved or deleted by the user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-188">![시간 표시 막대의 배달 위치](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-188">![Delivery Locations for Timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="e40ba-189">추가 작업</span><span class="sxs-lookup"><span data-stu-id="e40ba-189">Additional Actions</span></span> 

<span data-ttu-id="e40ba-190">추가 작업은 적용 된 작업으로 구성 되며 전자 메일 배달이 진행 되 고 ZAP, 수동 재구성 (관리자가 수행 하는 작업 (예: 일시 삭제), 동적 배달 및 다시 처리 (전자 메일이 retroactively 검색 됨)이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-190">Additional Actions consist of the actions that were applied post the delivery of the Email, and can include ZAP, Manual Remediation (action taken by an Admin e.g., Soft Delete), Dynamic Delivery, and Reprocessed (an email was retroactively detected as good).</span></span> 

> [!NOTE]
>
> - <span data-ttu-id="e40ba-191">이러한 변경의 일환으로 배달 작업 필터에 현재 표시 된 ZAP 값이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-191">As part of this change, the Removed by ZAP value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="e40ba-192">추가 작업을 통해 ZAP을 시도 하는 모든 전자 메일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-192">You'll have a way to search for all email with the ZAP attempt through the Additional Actions.</span></span>
>
> - <span data-ttu-id="e40ba-193">검색 기술 및 추가 작업에 대 한 새로운 필드와 값 (특히 ZAP 시나리오)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-193">There will be new fields and values for Detection technologies and Additional actions (especially for ZAP scenarios).</span></span> <span data-ttu-id="e40ba-194">기존의 저장 된 쿼리 및 추적 한 쿼리를 평가 하 여 새 값으로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-194">Evaluate your existing Saved Queries and Tracked queries to make sure they work with the new values.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-195">![Additional_Actions](../../media/Additional_Actions.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-195">![Additional_Actions](../../media/Additional_Actions.png)</span></span>

### <a name="system-overrides"></a><span data-ttu-id="e40ba-196">시스템 재정의</span><span class="sxs-lookup"><span data-stu-id="e40ba-196">System overrides</span></span> 

<span data-ttu-id="e40ba-197">시스템 재정의는 필터링 스택에서 식별 된 위협 및 기타 검색에 따라 시스템에서 제공 하는 배달 위치를 재정의 하 여 메시지의 원하는 배달 위치를 예외로 만드는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-197">System overrides are a method of making exceptions to the intended delivery location of a message by overriding the delivery location provided by system (based on the threats and other detections identified by our filtering stack).</span></span> <span data-ttu-id="e40ba-198">정책에서 권장 하는 대로 메시지를 배달 하기 위해 테 넌 트 또는 사용자 정책을 통해 시스템 재정의를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-198">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="e40ba-199">재정의는 구성 간격 (예: 사용자가 설정 하는 매우 광범위 한 안전한 보낸 사람 정책)으로 인해 악의적인 메시지가 예기치 않게 배달 되는 것을 식별 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-199">Overrides are useful in identifying any unintentional delivery of malicious messages due to configurations gaps (for example, a very broad Safe Sender policy set by a user).</span></span> <span data-ttu-id="e40ba-200">이러한 재정의 값은 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-200">These override values can be:</span></span>

- <span data-ttu-id="e40ba-201">사용자 정책에 의해 허용 됨: 사용자가 사서함 수준에서 정책을 만들어 도메인 이나 보낸 사람을 허용 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-201">Allowed by user policy: This is when a user allows domains or senders by creating policies at the mailbox level.</span></span>
- <span data-ttu-id="e40ba-202">사용자 정책에 의해 차단 됨: 사용자가 사서함 수준에서 정책을 만들어 도메인 이나 보낸 사람을 차단 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-202">Blocked by user policy: This is when a user blocks domains or senders by creating policies at the mailbox level.</span></span>
- <span data-ttu-id="e40ba-203">조직 정책에서 허용: 조직의 보안 팀이 조직의 사용자에 게 보낸 사람 및 도메인을 허용 하는 정책 또는 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)을 설정 하는 경우</span><span class="sxs-lookup"><span data-stu-id="e40ba-203">Allowed by org policy: This is when the organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="e40ba-204">이는 사용자 집합 또는 전체 조직에 대 한 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-204">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="e40ba-205">조직 정책에 의해 차단 됨: 조직의 보안 팀이 조직의 사용자에 대 한 보낸 사람, 도메인, 메시지 언어 또는 원본 Ip를 차단 하는 정책 또는 메일 흐름 규칙을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-205">Blocked by org policy: This is when the organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="e40ba-206">이는 사용자 집합 또는 전체 조직에도 해당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-206">This can also be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="e40ba-207">조직 정책에 의해 차단 된 파일 확장명:이는 파일 형식 확장이 맬웨어 방지 정책 설정을 통해 조직의 보안 팀에 의해 차단 되는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-207">File extension blocked by org policy: This is when a file type extension is blocked by the security teams of an organization through the anti-malware policy settings.</span></span> <span data-ttu-id="e40ba-208">이러한 값은 조사를 지원 하기 위해 이제 전자 메일 세부 정보에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-208">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="e40ba-209">Secops 팀은 다양 한 필터링 기능을 사용 하 여 차단 된 파일 확장명을 기준으로 필터링 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-209">Secops teams can also filter on blocked file extensions using the rich filtering capability.</span></span>

![System_Overrides](../../media/System_Overrides.png)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-211">![System_Overrides_Grid](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-211">![System_Overrides_Grid](../../media/System_Overrides_Grid.png)</span></span>


### <a name="improvements-around-url-and-clicks-experience"></a><span data-ttu-id="e40ba-212">URL 및 클릭 환경에 대 한 개선 사항</span><span class="sxs-lookup"><span data-stu-id="e40ba-212">Improvements around URL and Clicks Experience</span></span>

<span data-ttu-id="e40ba-213">URL 및 URL 클릭 데이터를 중심으로 하는 향상 된 기능 집합은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-213">The set of improvements focused towards URL and URL clicks data include:</span></span>

 - <span data-ttu-id="e40ba-214">Url 플라이 아웃의 클릭 섹션 내에서 URL의 일부인 쿼리 매개 변수를 포함 하 여 클릭 한 전체 URL을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-214">Showing full Clicked URL (including any query Parameters which are part of URL) within the Clicks Section in URL Flyout.</span></span> <span data-ttu-id="e40ba-215">현재 URL 도메인과 경로가 제목 표시줄에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-215">Currently we show the URL domain and path in title bar.</span></span> <span data-ttu-id="e40ba-216">이 정보를 확장 하 여 전체 URL을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-216">We're extending that information to show the full URL.</span></span>
 
 - <span data-ttu-id="e40ba-217">Url 필터 (URL vs url 도메인 vs URL 도메인 및 경로): URL이 포함 된 메시지를 검색 하는 과정에서 업데이트를 수행 하 고 결과를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-217">Fixes across URL filters (URL vs URL domain vs URL Domain and path): We've made updates around searching for messages that contain a URL/Click verdict.</span></span> <span data-ttu-id="e40ba-218">이 작업의 일부로, 프로토콜에 관계 없이 검색을 지원 하도록 설정 했습니다 (http를 사용 하지 않고 URL을 직접 검색할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="e40ba-218">As part of that, we've enabled support for protocol agnostic searches (meaning, you can directly search for a URL without http).</span></span> <span data-ttu-id="e40ba-219">기본적으로 URL 검색은 명시적으로 지정 된 경우를 제외 하 고 http에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-219">By default, the URL search maps to http, unless explicitly specified.</span></span> <span data-ttu-id="e40ba-220">예시:</span><span class="sxs-lookup"><span data-stu-id="e40ba-220">For example:</span></span>

   1. <span data-ttu-id="e40ba-221">`http://`"Url", "Url 도메인" 및 "Url 도메인 및 경로" 필터 필드에서 접두사를 사용 하지 않고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-221">Search with and without the `http://` prefix in "URL", "URL Domain", and "URL Domain and Path" filter fields.</span></span> <span data-ttu-id="e40ba-222">이 동작은 일관적 이며 같은 결과를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-222">This behavior is consistent, and should show the same result.</span></span>
   
   1. <span data-ttu-id="e40ba-223">`https://`"URL"에서 접두사를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-223">Search for the `https://` prefix in "URL".</span></span> <span data-ttu-id="e40ba-224">이 매개 변수를 제공 하지 않으면 `http://` 접두사를 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-224">When not present, the `http://` prefix is assumed.</span></span>
   
   1. <span data-ttu-id="e40ba-225">`/` "URL 경로", "url 도메인 및 경로" 필드의 시작과 끝에는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-225">`/` in beginning and end of the "URL path", "URL Domain", "URL domain and path" fields is ignored.</span></span> <span data-ttu-id="e40ba-226">`/` "URL" 필드 끝에는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-226">`/` at the end of the "URL" field is ignored.</span></span> 

### <a name="phish-confidence-level"></a><span data-ttu-id="e40ba-227">피싱 신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="e40ba-227">Phish Confidence Level</span></span>

<span data-ttu-id="e40ba-228">피싱 신뢰 수준에서는 전자 메일이 피싱로 분류 되는 신뢰도를 식별 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-228">Phish confidence level helps to identify the degree of confidence, with which an email was categorized as Phish.</span></span> <span data-ttu-id="e40ba-229">두 가지 가능한 값은 High 및 Normal입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-229">The two possible values are High and Normal.</span></span> <span data-ttu-id="e40ba-230">초기 단계에서이 필터는 Threat Explorer의 피싱 보기 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-230">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

![Phish_Confidence_Level](../../media/Phish_Confidence_Level.png)

### <a name="zap-url-signal"></a><span data-ttu-id="e40ba-232">ZAP URL 신호</span><span class="sxs-lookup"><span data-stu-id="e40ba-232">ZAP URL Signal</span></span> 

<span data-ttu-id="e40ba-233">일반적으로 전자 메일이 피싱로 식별 되 고 배달 후 제거 된 ZAP 피싱 경고 시나리오에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-233">Typically used for ZAP Phish Alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="e40ba-234">이는 해당 경고를 탐색기의 해당 결과와 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-234">This is used to connect the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="e40ba-235">이는 경고에 대 한 IOCs 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-235">It is one of the IOCs for the alert.</span></span> 

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="e40ba-236">위협 탐색기 및 Real-Time 검색 기능이 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-236">Experience Improvements to Threat Explorer and Real-Time Detections</span></span>

<span data-ttu-id="e40ba-237">검색 프로세스를 개선 하는 과정에서 위협 탐색기와 Real-Time 검색을 몇 가지 업데이트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-237">As part of improving the hunting process, we have made a few updates to Threat Explorer and Real-Time Detections.</span></span> <span data-ttu-id="e40ba-238">이러한 기능은 개선 된 경험을 보다 일관성 있게 만드는 데 중점을 둔 ' 경험 ' 향상 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-238">These are ‘experience’ improvements, with the focus on making the hunting experience more consistent.</span></span> <span data-ttu-id="e40ba-239">이러한 변경 내용은 아래에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-239">These changes are outlined below:</span></span>

- [<span data-ttu-id="e40ba-240">향상 된 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="e40ba-240">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="e40ba-241">새로 고침 프로세스의 업데이트</span><span class="sxs-lookup"><span data-stu-id="e40ba-241">Update in the Refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="e40ba-242">필터에 추가할 차트 드릴 다운</span><span class="sxs-lookup"><span data-stu-id="e40ba-242">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="e40ba-243">제품 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="e40ba-243">In product information updates</span></span>](#in-product-information-updates)

### <a name="timezone-improvements"></a><span data-ttu-id="e40ba-244">향상 된 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="e40ba-244">Timezone improvements</span></span>

<span data-ttu-id="e40ba-245">내보낸 데이터 뿐만 아니라 포털 내의 전자 메일 레코드에 대 한 표준 시간대가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-245">You will see the timezone for the email records within the Portal, as well as for Exported data.</span></span> <span data-ttu-id="e40ba-246">표준 시간대는 전자 메일 표, 세부 정보 플라이 아웃, 전자 메일 일정 및 유사한 전자 메일 같은 경험을 통해 표시 되므로 결과 집합에 대 한 표준 시간대가 사용자에 게 분명 하 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-246">The timezone will be visible across experiences like Email Grid, Details Flyout, Email Timeline, and Similar Emails, so that the timezone for the result set is clear to the user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-247">![탐색기에서 표준 시간대 보기](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-247">![View Timezone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="e40ba-248">새로 고침 프로세스의 업데이트</span><span class="sxs-lookup"><span data-stu-id="e40ba-248">Update in the Refresh process</span></span>

<span data-ttu-id="e40ba-249">자동 새로 고침을 사용한 혼동에 대 한 의견을 들었습니다 (예: 날짜를 변경 하는 즉시, 페이지를 새로 고치는 작업) 및 수동 새로 고침 (기타 필터에 대 한 경우).</span><span class="sxs-lookup"><span data-stu-id="e40ba-249">We have heard feedback around confusion with automatic refresh (e.g. for date, as soon as you change the date, the page would refresh) and manual refresh (for other filters).</span></span> <span data-ttu-id="e40ba-250">마찬가지로, 필터를 제거 하면 자동 새로 고침이 실행 되므로 쿼리를 수정 하는 동안 다른 필터를 변경 하면 검색 환경이 일치 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-250">Similarly, removing filters leads to automatic refresh, this causes situations where changing the different filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="e40ba-251">이를 해결 하기 위해 수동 필터링 메커니즘으로 이동 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-251">To solve this, we are moving to a manual filtering mechanism.</span></span>

<span data-ttu-id="e40ba-252">경험 측면에서 볼 때 사용자는 필터 집합 및 날짜에서 서로 다른 필터 범위를 적용 하 고 제거할 수 있으며, 새로 고침 단추를 눌러 쿼리 정의 작업을 완료 한 후에 결과를 필터링 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-252">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set, and date), and press the refresh button to filter the results once they are done with defining the query.</span></span> <span data-ttu-id="e40ba-253">화면에서 명확 하 게 전화를 걸기 위해 새로 고침 단추도 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-253">The refresh button has also been updated to call it out clearly on the screen.</span></span> <span data-ttu-id="e40ba-254">또한이 변경 사항에 대 한 도구 설명 및 제품 설명서도 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-254">We have also updated tooltips and in-product documentation around this change.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-255">![새로 고침을 클릭 하 여 결과를 필터링 합니다.](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-255">![Click on Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="e40ba-256">필터에 추가할 차트 드릴 다운</span><span class="sxs-lookup"><span data-stu-id="e40ba-256">Chart drilldown to add to filters</span></span>

<span data-ttu-id="e40ba-257">이제 차트 범례 값을 클릭 하 여 해당 값을 필터로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-257">You will now be able to click on the chart legend values to add that value as a filter.</span></span> <span data-ttu-id="e40ba-258">위에서 설명한 변경 내용의 일부로 결과를 필터링 하려면 새로 고침 단추를 클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-258">Note that you will still have to click on the refresh button to filter the results as part of the change described above.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-259">![차트에서 필터링으로 드릴 다운](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-259">![Drilldown through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="e40ba-260">제품 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="e40ba-260">In product information updates</span></span>

<span data-ttu-id="e40ba-261">제품 내에 추가 정보도 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-261">You should also see additional details within the product.</span></span> <span data-ttu-id="e40ba-262">예를 들어 표 내에 있는 총 검색 결과 수 (아래 참조)와 레이블 주위의 향상 된 기능, 필터, 검색 환경 및 결과 집합에 대 한 자세한 정보를 제공 하기 위해 오류 메시지와 도구 설명이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-262">For example, the total number of search results within grid (see below), as well as improvements around labels, error messages and tooltips, to give more information around filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-263">![제품 내 정보 보기](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-263">![View In-product Info](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="e40ba-264">위협 탐색기의 확장 기능</span><span class="sxs-lookup"><span data-stu-id="e40ba-264">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="e40ba-265">상위 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="e40ba-265">Top targeted users</span></span>

<span data-ttu-id="e40ba-266">현재는 전자 메일에 대 한 맬웨어 보기에서 가장 많이 대상으로 지정 된 사용자의 목록을 최상위 맬웨어 제품군 내에서 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-266">Today we expose the list of the top targeted users in the Malware View for Emails (within the Top Malware Families section).</span></span> <span data-ttu-id="e40ba-267">여기서는 피싱 및 모든 전자 메일 보기에서이 보기를 확장 하 고 해당 하는 보기에 대 한 각 사용자의 시도 횟수 (예: 피싱 보기에서 피싱 시도 횟수를 볼 수 있음)와 함께 상위 5 개 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-267">We will be extending this view within Phish and All Email views as well, where you will be able to see the top five targeted users along with the number of attempts for each user for the corresponding view (for example, for Phish view you will be able to see the number of Phish attempts).</span></span>
<span data-ttu-id="e40ba-268">또한 각 전자 메일 보기에 대 한 오프 라인 분석 시도 횟수와 함께 대상 사용자 목록을 최대 3000까지 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-268">You will also be able to export the list of targeted users up to a limit of 3000 along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="e40ba-269">이 외에도 아니요를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-269">In addition to that, selecting No.</span></span> <span data-ttu-id="e40ba-270">(예: 아래의 13 번 시도)은 위협 탐색기에서 필터링 된 보기를 열고 해당 사용자의 전자 메일 및 위협에 대 한 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-270">of attempts (for example, 13 attempts below) would open a filtered view in Threat Explorer, so that you can look at more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-271">![상위 대상 사용자](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-271">![Top Targeted Users](../../media/Top_Targeted_Users.png)</span></span>


### <a name="exchange-transport-rules"></a><span data-ttu-id="e40ba-272">Exchange 전송 규칙</span><span class="sxs-lookup"><span data-stu-id="e40ba-272">Exchange transport rules</span></span>
<span data-ttu-id="e40ba-273">또한 데이터 향상의 일부로, 메시지에 적용 된 다른 전송 규칙도 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-273">As part of data enrichment, you should also be able to see all the different transport rules which were applied to a message.</span></span> <span data-ttu-id="e40ba-274">이 정보는 전자 메일 표 보기 내에 표시 되며,이를 확인 하려면 표에서 열 옵션을 선택 하 고 표에 있는 열 옵션에서 Exchange 전송 규칙 추가와 전자 메일의 세부 정보 플라이 아웃을 함께 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-274">This information will be present within the Email grid view (to view this, select Column options in the grid and add Exchange Transport Rule from the Column options in the grid) as well as Details flyout in the email.</span></span>
<span data-ttu-id="e40ba-275">메시지에 적용 된 전송 규칙의 이름 뿐 아니라 GUID도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-275">You would be able to see both the GUID as well as the name of the transport rules which were applied to the message.</span></span> <span data-ttu-id="e40ba-276">또한 전송 규칙의 이름을 사용 하 여 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-276">Additionally, you would be able to search for the messages using the name of the transport rule.</span></span> <span data-ttu-id="e40ba-277">이는 ' 포함 ' 검색으로, 부분 검색을 사용 하 여 검색할 수 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-277">This would be a ‘Contains’ search which means you will be able to search using partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="e40ba-278">중요 참고 사항:</span><span class="sxs-lookup"><span data-stu-id="e40ba-278">Important Note:</span></span>
<span data-ttu-id="e40ba-279">ETR 검색 및 이름 사용 가능 여부는 자신에 게 할당 된 특정 역할에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-279">ETR search and name availability would depend on the specific role that has been assigned to you.</span></span> <span data-ttu-id="e40ba-280">ETR 이름과 검색을 보려면 다음 역할/사용 권한 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-280">You will need to have one of the following roles/permissions in order to view the ETR names and search.</span></span>  <span data-ttu-id="e40ba-281">사용자에 게 할당 된 다음 역할이 없는 경우 전송 규칙의 이름을 확인 하 고 ETR 이름을 사용 하 여 메시지를 검색할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-281">If you do not have any of the following roles assigned to you, you will not be able to see the names of the transport rules, and search for the messages using the ETR names.</span></span> <span data-ttu-id="e40ba-282">그러나 전자 메일 세부 정보 내에서 ETR 레이블과 GUID 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-282">However, you will be able to see the ETR label and GUID information within the Email Details.</span></span> <span data-ttu-id="e40ba-283">전자 메일 표에서 레코드를 보는 경우의 다른 경험에는 영향을 주지 않습니다 (전자 메일 flyouts, 필터 및 내보내기).</span><span class="sxs-lookup"><span data-stu-id="e40ba-283">Your other experiences around viewing records in Email Grids, Email flyouts, Filters, and Export are not impacted.</span></span>

- <span data-ttu-id="e40ba-284">EXO Only-데이터 손실 방지: 모두</span><span class="sxs-lookup"><span data-stu-id="e40ba-284">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="e40ba-285">EXO Only-O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="e40ba-285">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="e40ba-286">AAD 또는 EXO-보안 관리자: 모두</span><span class="sxs-lookup"><span data-stu-id="e40ba-286">AAD or EXO - Security Admin: All</span></span>
- <span data-ttu-id="e40ba-287">AAD 또는 EXO-보안 읽기 권한자: 모두</span><span class="sxs-lookup"><span data-stu-id="e40ba-287">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="e40ba-288">EXO Only-전송 규칙: 모두</span><span class="sxs-lookup"><span data-stu-id="e40ba-288">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="e40ba-289">EXO Only-View-Only 구성: 모두</span><span class="sxs-lookup"><span data-stu-id="e40ba-289">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="e40ba-290">전자 메일 표, 세부 정보 플라이 아웃 및 내보낸 CSV에는 아래와 같이 이름/GUID와 함께 ETRs가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-290">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-291">![Exchange 전송 규칙](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-291">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="e40ba-292">인바운드 커넥터</span><span class="sxs-lookup"><span data-stu-id="e40ba-292">Inbound connectors</span></span>

<span data-ttu-id="e40ba-293">커넥터는 Microsoft 365 또는 Office 365 조 직에서 전자 메일이 들어오고 나가는 방식을 사용자 지정 하는 지침 모음으로, 보안 제한이 나 제어를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-293">Connectors are a collection of instructions that customize the way your email flows to and from your Microsoft 365 or Office 365 organization, with the ability to apply any security restriction or controls.</span></span> <span data-ttu-id="e40ba-294">이제는 위협 탐색기 내에서 전자 메일과 관련 된 커넥터를 확인 하 고 커넥터 이름을 사용 하 여 전자 메일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-294">Within Threat Explorer, you will now have the ability to view the connectors which are related to an email as well as search for emails using the connector names.</span></span>
<span data-ttu-id="e40ba-295">커넥터 검색은 부분적인 키워드 검색도 작동 하도록 ' 포함 ' 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-295">The search for connectors is ‘Contains’ in nature which means partial keyword searches should work as well.</span></span>
<span data-ttu-id="e40ba-296">기본 눈금 보기, 세부 정보 플라이 아웃 및 내보낸 CSV에서 커넥터는 아래와 같이 이름/GUID 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-296">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown below:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-297">![커넥터 세부 정보](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-297">![Connector Details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="e40ba-298">위협 탐색기 및 실시간 검색의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e40ba-298">New features in Threat Explorer and real-time detections</span></span>

<span data-ttu-id="e40ba-299">위협 탐색기 및 실시간 검색에 다음과 같은 세 가지 새로운 기능이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-299">Three new features added into Threat Explorer and real-time detections:</span></span>

- [<span data-ttu-id="e40ba-300">전자 메일 머리글 미리 보기 및 전자 메일 본문 다운로드</span><span class="sxs-lookup"><span data-stu-id="e40ba-300">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="e40ba-301">전자 메일 시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="e40ba-301">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="e40ba-302">URL 내보내기 데이터 클릭</span><span class="sxs-lookup"><span data-stu-id="e40ba-302">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="e40ba-303">이러한 새로운 기능은 아래에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-303">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="e40ba-304">전자 메일 머리글 미리 보기 및 전자 메일 본문 다운로드</span><span class="sxs-lookup"><span data-stu-id="e40ba-304">Preview email header and download email body</span></span>

<span data-ttu-id="e40ba-305">전자 메일 머리글을 미리 보고 전자 메일 본문을 다운로드 하는 기능은 위협 탐색기에서 사용할 수 있는 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-305">The ability to preview an email header and download the email body are new features available in Threat Explorer.</span></span> <span data-ttu-id="e40ba-306">관리자가 다운로드 한 헤더/전자 메일 메시지를 분석 하 여 위협을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-306">Admins will be able to analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="e40ba-307">전자 메일 메시지를 다운로드 하면 정보의 노출을 초래할 수 있으므로이 프로세스는 RBAC (역할 기반 액세스 제어)를 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-307">Because downloading email messages can risk the exposure of information, this process is controlled by roles-based access control (RBAC).</span></span> <span data-ttu-id="e40ba-308">모든 전자 메일 메시지 보기에서 메일을 다운로드 하 고 머리글을 미리 볼 수 있도록 하려면 새 역할인 *미리 보기*를 다른 역할 그룹 (예: 보안 작업 또는 보안 관리자)에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-308">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="e40ba-309">그러나 Explorer (및 실시간 검색)도 새로운 새 필드를 추가 하 여 전자 메일 메시지가 있는 위치를 보다 완전 하 게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-309">But Explorer (and real-time detections) also adds fresh new fields designed to give you a more complete picture of where your email messages land.</span></span> <span data-ttu-id="e40ba-310">이러한 변경 목표의 일환으로는 보안 Ops 사용자에 게 더 쉽게 사냥을 제공할 수 있지만 문제 전자 메일 메시지의 위치를 한눈에 파악 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-310">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="e40ba-311">어떤 작업을 수행 하나요?</span><span class="sxs-lookup"><span data-stu-id="e40ba-311">How is this done?</span></span> <span data-ttu-id="e40ba-312">배달 상태는 이제 다음과 같은 두 개의 열로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-312">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="e40ba-313">**배달 작업** -이 전자 메일의 상태는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="e40ba-313">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="e40ba-314">**배달 위치** -이 전자 메일의 경로가 어떻게 설정 되었습니까?</span><span class="sxs-lookup"><span data-stu-id="e40ba-314">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="e40ba-315">배달 작업은 기존 정책 또는 검색으로 인해 전자 메일에 대해 수행 되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-315">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="e40ba-316">다음은 전자 메일에 사용할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-316">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="e40ba-317">배달</span><span class="sxs-lookup"><span data-stu-id="e40ba-317">Delivered</span></span>|<span data-ttu-id="e40ba-318">Junked</span><span class="sxs-lookup"><span data-stu-id="e40ba-318">Junked</span></span>|<span data-ttu-id="e40ba-319">차단됨</span><span class="sxs-lookup"><span data-stu-id="e40ba-319">Blocked</span></span>|<span data-ttu-id="e40ba-320">바뀌면</span><span class="sxs-lookup"><span data-stu-id="e40ba-320">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="e40ba-321">전자 메일이 사용자의 받은 편지함 또는 폴더에 배달 되었으며 사용자가 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-321">Email was delivered to Inbox or folder of a user and the user can directly access it.</span></span>|<span data-ttu-id="e40ba-322">사용자의 정크 폴더 또는 삭제 된 폴더에 전자 메일이 전송 되 고 해당 폴더의 전자 메일에 대 한 액세스 권한이 사용자에 게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-322">Email was sent to either user’s Junk folder or Deleted folder, and the user has access to emails in those folders.</span></span>|<span data-ttu-id="e40ba-323">격리 되거나, 실패 했거나, 삭제 된 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-323">Any emails that are quarantined, that  failed, or were dropped.</span></span> <span data-ttu-id="e40ba-324">사용자가이를 완전히 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-324">This is completely inaccessible by the user!</span></span>|<span data-ttu-id="e40ba-325">첨부 파일이 악성 인 .txt 파일로 악의적 첨부 파일이 교체 되는 모든 전자 메일</span><span class="sxs-lookup"><span data-stu-id="e40ba-325">Any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>|

|<span data-ttu-id="e40ba-326">배달</span><span class="sxs-lookup"><span data-stu-id="e40ba-326">Delivered</span></span>|<span data-ttu-id="e40ba-327">Junked</span><span class="sxs-lookup"><span data-stu-id="e40ba-327">Junked</span></span>|<span data-ttu-id="e40ba-328">차단됨</span><span class="sxs-lookup"><span data-stu-id="e40ba-328">Blocked</span></span>|<span data-ttu-id="e40ba-329">바뀌면</span><span class="sxs-lookup"><span data-stu-id="e40ba-329">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="e40ba-330">전자 메일이 사용자의 받은 편지함 또는 다른 폴더로 배달 되었으며 사용자가 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-330">Email was delivered to the user's inbox or another folder, and the user can directly access it.</span></span>|<span data-ttu-id="e40ba-331">사용자의 정크 폴더 또는 삭제 된 폴더로 전자 메일이 전송 되 고 해당 폴더의 전자 메일 메시지에 대 한 액세스 권한이 사용자에 게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-331">Email was sent to either user's Junk folder or Deleted folder, and the user has access to email messages in those folders.</span></span>|<span data-ttu-id="e40ba-332">격리 되거나, 실패 했거나, 삭제 되었으며 사용자가 액세스할 수 없는 전자 메일 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-332">Any email messages that are quarantined, that failed, or were dropped, and are not accessible by the user.</span></span>|<span data-ttu-id="e40ba-333">첨부 파일이 악성 인 .txt 파일로 악의적 첨부 파일을 바꾼 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="e40ba-333">Any email messages where malicious attachments were replaced by .txt files that state the attachments were malicious.</span></span>|
|

<span data-ttu-id="e40ba-334">다음은 사용자가 볼 수 있는 것과 그렇지 않은 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-334">And here is what the user can see, and what they can't:</span></span>

|<span data-ttu-id="e40ba-335">최종 사용자가 액세스할 수 있음</span><span class="sxs-lookup"><span data-stu-id="e40ba-335">Accessible to end users</span></span>|<span data-ttu-id="e40ba-336">최종 사용자가 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="e40ba-336">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="e40ba-337">배달</span><span class="sxs-lookup"><span data-stu-id="e40ba-337">Delivered</span></span>|<span data-ttu-id="e40ba-338">차단됨</span><span class="sxs-lookup"><span data-stu-id="e40ba-338">Blocked</span></span>|
|<span data-ttu-id="e40ba-339">Junked</span><span class="sxs-lookup"><span data-stu-id="e40ba-339">Junked</span></span>|<span data-ttu-id="e40ba-340">바뀌면</span><span class="sxs-lookup"><span data-stu-id="e40ba-340">Replaced</span></span>|

<span data-ttu-id="e40ba-341">배달 위치는 배달 후 실행 되는 정책 및 검색의 결과를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-341">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="e40ba-342">배달 작업에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-342">It's linked to a Delivery Action.</span></span> <span data-ttu-id="e40ba-343">이 필드는 문제 메일을 찾은 경우 수행 되는 작업에 대 한 통찰력을 제공 하기 위해 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-343">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="e40ba-344">배달 위치의 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-344">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="e40ba-345">**받은 편지함 또는 폴더**: 전자 메일이 받은 편지함 또는 폴더 (전자 메일 규칙에 따라)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-345">**Inbox or folder**: The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="e40ba-346">**온-프레미스 또는 external**: 사서함이 클라우드에는 없지만 온-프레미스에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="e40ba-346">**On-prem or external**: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="e40ba-347">**정크 폴더**: 전자 메일이 사용자의 정크 메일 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-347">**Junk folder**: The email is in the Junk folder of a user.</span></span>
- <span data-ttu-id="e40ba-348">**지운 편지함 폴더**: 사용자의 지운 편지함 폴더에 있는 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-348">**Deleted items folder**: The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="e40ba-349">**격리**: 사용자의 사서함에 없는 전자 메일 격리</span><span class="sxs-lookup"><span data-stu-id="e40ba-349">**Quarantine**: The email in quarantine, and is not in a user's mailbox.</span></span>
- <span data-ttu-id="e40ba-350">**실패**: 전자 메일이 사서함에 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-350">**Failed**: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="e40ba-351">**삭제**됨: 메일 흐름의 어딘가에 메일이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-351">**Dropped**: The email gets lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="e40ba-352">전자 메일 시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="e40ba-352">Email timeline</span></span>

<span data-ttu-id="e40ba-353">**전자 메일 시간 표시 막대** 는 관리자에 게 더 적합 한 사냥 환경을 구현 하기 위한 또 다른 새로운 탐색기 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-353">The **Email Timeline** is another new Explorer feature aimed at making the hunting experience better for admins.</span></span> <span data-ttu-id="e40ba-354">다른 위치를 확인 하는 데 소요 되는 시간이 감소 하 여 이벤트를 이해 하기 위해 임의 시간에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-354">It cuts down on randomization because there is less time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="e40ba-355">전자 메일에서 여러 이벤트가 발생 하거나 같은 시간에 발생할 경우 해당 이벤트가 시간 표시 막대 보기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-355">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="e40ba-356">실제로 메일에 대해 배달이 발생 하는 일부 이벤트는 ' 특수 동작 ' 열에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-356">In fact, some events that happen post-delivery to your mail will be captured in the 'Special action' column.</span></span> <span data-ttu-id="e40ba-357">해당 메일의 시간 표시줄에 있는 정보를 메일 발송에 대해 수행 된 특수 작업과 함께 사용 하면 관리자가 정책이 작동 하는 방식, 메일을 최종적으로 라우팅된 위치, 그리고 경우에 따라 최종 평가가 수행 된 방식을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-357">Combining the information from the timeline of that mail with the special action taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="e40ba-358">악성 전자 메일 메시지를 조사 하는 방법에 대 한 자세한 내용은 [Office 365에서 제공 된 악성 전자 메일 조사 및 재구성](investigate-malicious-email-that-was-delivered.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e40ba-358">For more discussion about investigating malicious email messages, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="e40ba-359">URL 내보내기 데이터 클릭</span><span class="sxs-lookup"><span data-stu-id="e40ba-359">Export URL click data</span></span>

<span data-ttu-id="e40ba-360">또한 이제는 URL 클릭에 대 한 보고서를 Microsoft Excel로 내보내 해당 네트워크 메시지 ID를 확인 하 고, 결과 클릭 하 여 URL이 더 쉽게 전송 되는 위치를 이해 하는 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-360">Also, you will now be able to export reports for URL clicks to Microsoft Excel in order to view both their Network Message ID, and their Click Verdict, making the task of understanding where your URL click traffic originated easier.</span></span> <span data-ttu-id="e40ba-361">작동 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-361">Here's how it works.</span></span> <span data-ttu-id="e40ba-362">Office 365 빠른 실행의 위협 관리에서이 체인을 통해를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-362">Starting in Threat Management on the Office 365 quick-launch, click through this chain:</span></span>

<span data-ttu-id="e40ba-363">**탐색기** \> **피싱 보기** \> **클릭** \> 상위 **url 또는 위쪽 Url 클릭** \> **임의의 레코드를 클릭 하 여 URL 플라이 아웃을 엽니다** .</span><span class="sxs-lookup"><span data-stu-id="e40ba-363">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs or URL Top Clicks** \> **Click on any record to open URL flyout**</span></span>

<span data-ttu-id="e40ba-364">목록에서 URL을 클릭 하면 플라이 아웃 패널에 새 내보내기 단추가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-364">When you click on a URL in the list, you'll see a new Export button on the fly-out panel.</span></span> <span data-ttu-id="e40ba-365">이 단추를 사용 하 여 데이터를 보다 쉽게 보고 하도록 Excel 스프레드시트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-365">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="e40ba-366">실시간 검색 보고서의 동일한 위치를 다음과 같이 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-366">You can get to the same location in the real-time detections report as follows:</span></span>

<span data-ttu-id="e40ba-367">**탐색기** \> **실시간 검색** \> **피싱 보기** \> **Url** \> **상위 url 또는 위쪽 클릭** \> **임의의 레코드를 클릭 하 여 URL 플라이 아웃** \> 을 엽니다. **클릭 탭으로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e40ba-367">**Explorer** \> **Real-time Detections** \> **View Phish** \> **URLs** \> **Top URLs or Top Clicks** \> **Click on any record to open URL flyout** \> **Navigate to the Clicks Tab.**</span></span>

> [!TIP]
> <span data-ttu-id="e40ba-368">Network Message ID는 네트워크 메시지 ID를 통해 탐색기나 연결 된 타사 도구를 검색할 때 클릭을 특정 메일에 다시 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-368">Network Message ID maps the click back to specific mails when you search through Explorer or associated 3rd party tools via Network Message ID.</span></span> <span data-ttu-id="e40ba-369">네트워크 메시지 ID를 통해 검색 하면 관리자가 클릭 결과와 연결 된 특정 전자 메일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-369">Searching through the Network Message ID will give admins the specific email associated with a click result.</span></span> <span data-ttu-id="e40ba-370">내보낼 때 네트워크 메시지 ID의 일치 확인을 통해 더 빠르고 강력한 분석이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-370">On export having, the correlating identification of Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e40ba-371">![탐색기의 클릭 탭](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-371">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="e40ba-372">기술 별로 전자 메일에서 발견 된 맬웨어를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e40ba-372">See malware detected in email by technology</span></span>

<span data-ttu-id="e40ba-373">Microsoft 365 기술을 통해 전자 메일로 검색 된 맬웨어를 확인 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-373">Suppose you want to see malware detected in email, by Microsoft 365 technology.</span></span> <span data-ttu-id="e40ba-374">이 작업을 수행 하려면 [전자 메일 > 맬웨어](threat-explorer-views.md#email--malware) 보기 Explorer (또는 실시간 검색)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-374">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="e40ba-375">보안 & 준수 센터 ()에서 [https://protection.office.com](https://protection.office.com) **Threat management**  >  **Explorer** (또는 **실시간**검색)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-375">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="e40ba-376">(이 예제에서는 탐색기를 사용 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e40ba-376">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="e40ba-377">**보기** 메뉴에서 **전자 메일**  >  **맬웨어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-377">In the **View** menu, choose **Email** > **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40ba-378">![탐색기에 대 한 보기 메뉴](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-378">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="e40ba-379">**보낸 사람**을 클릭 한 다음 **기본**  >  **검색 기술을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-379">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span>

   <span data-ttu-id="e40ba-380">이제 검색 기술을 보고서에 대 한 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-380">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40ba-381">![맬웨어 검색 기술](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-381">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="e40ba-382">옵션을 선택한 다음 **새로 고침** 단추를 클릭 하 여 해당 필터를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-382">Select an option, and then click the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40ba-383">![선택한 검색 기술](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-383">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="e40ba-384">선택한 기술 옵션을 사용 하 여 전자 메일로 검색 된 결과 맬웨어가 표시 되도록 보고서가 새로 고쳐집니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-384">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="e40ba-385">여기서는 추가 분석을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-385">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="e40ba-386">피싱 Url에 대 한 데이터를 확인 하 고 결과를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-386">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="e40ba-387">허용, 차단 및 재정의 된 Url 목록을 비롯 하 여 전자 메일의 Url을 통한 피싱 시도를 확인 하려는 경우를 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-387">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="e40ba-388">클릭 한 Url을 식별 하려면 [안전한 링크](atp-safe-links.md) 를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-388">Identifying URLs that were clicked requires [Safe Links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="e40ba-389">클릭 시간 보호에 대 한 [안전한 링크 정책을](set-up-atp-safe-links-policies.md) 설정 해야 하며 안전한 링크를 클릭 하 여 verdicts을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-389">Make sure that you have set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="e40ba-390">메시지에서 피싱 Url을 검토 하 고 피싱 메시지의 Url을 클릭 하려면 [전자 메일 > 피싱](threat-explorer-views.md#email--phish) Explorer 보기 (실시간 검색)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-390">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="e40ba-391">보안 & 준수 센터 ()에서 [https://protection.office.com](https://protection.office.com) **Threat management**  >  **Explorer** (또는 **실시간**검색)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-391">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="e40ba-392">(이 예제에서는 탐색기를 사용 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e40ba-392">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="e40ba-393">**보기** 메뉴에서 **전자 메일**  >  **피싱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-393">In the **View** menu, choose **Email** > **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40ba-394">![탐색기에 대 한 보기 메뉴](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-394">![View menu for Explorer](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="e40ba-395">**보낸 사람**을 클릭 한 다음 **url**을 선택  >  합니다**결과를 클릭**합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-395">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="e40ba-396">**차단** 됨 및 **무시 된 블록과**같은 옵션을 하나 이상 선택 하 고 해당 필터를 적용 하는 옵션과 같은 줄에 있는 **새로 고침** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-396">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="e40ba-397">(브라우저 창을 새로 고치지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="e40ba-397">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40ba-398">![Url을 선택 하 고 verdicts을 클릭 합니다.](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-398">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="e40ba-399">보고서를 새로 고치면 보고서 아래의 URL 탭에 서로 다른 두 개의 URL 테이블이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-399">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="e40ba-400">**상위 url** 은 필터링 된 메시지에 포함 된 url 및 각 URL에 대 한 전자 메일 배달 작업 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-400">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="e40ba-401">피싱 전자 메일 보기에서 일반적으로이 목록에는 합법적인 Url이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-401">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="e40ba-402">공격자는 메시지에 효과적이 고 잘못 된 Url을 함께 사용 하 여 배달 하려고 할 수 있지만, 사용자가 클릭 하는 데 더 흥미로운 악성 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-402">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="e40ba-403">Url의 테이블은 총 전자 메일 수로 정렬 되지만 보기를 단순하게 하기 위해이 열이 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-403">The table of URLs is sorted by total email count (but note that this column is hidden to simplify the view).</span></span>

   - <span data-ttu-id="e40ba-404">**위쪽** 클릭은 클릭 한 안전한 링크 래핑된 url이 총 클릭 횟수에 따라 정렬 되며 보기를 단순화 하기 위해이 열도 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-404">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="e40ba-405">총 개수 열에서 안전한 링크를 나타냅니다. 클릭 한 각 URL에 대해 결과 count를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-405">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="e40ba-406">피싱 email (전자 메일 보기)에서 이러한 메시지는 일반적으로 의심 되거나 악성 Url 이지만 위협이 아닌 Url을 포함할 수 있지만 피싱 메시지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-406">In the phish email view, these are more often suspicious or malicious URLs, but could include URLs that are not threats but are in phish messages.</span></span> <span data-ttu-id="e40ba-407">래핑 해제 한 링크의 URL 클릭은 여기에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-407">URL clicks on unwrapped links will not show up here.</span></span>

   <span data-ttu-id="e40ba-408">두 개의 URL 테이블은 배달 작업 및 위치로 피싱 전자 메일 메시지의 상위 Url을 표시 하 고, 사용자가 사용자와 상호 작용 한 잘못 된 링크를 확인할 수 있도록 차단 된 (또는 경고에 따라 방문) URL 클릭을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-408">The two URL tables show top URLs in phishing email messages by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="e40ba-409">여기서는 추가 분석을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-409">From here, you can conduct further analysis.</span></span> <span data-ttu-id="e40ba-410">예를 들어 차트 아래에서 조직의 환경에서 차단 된 전자 메일 메시지의 최상위 Url을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-410">For example, below the chart, you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40ba-411">![차단 된 탐색기 Url](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-411">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="e40ba-412">자세한 정보를 보려면 URL을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-412">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e40ba-413">URL 플라이 아웃 대화 상자에서 전자 메일 메시지에 대 한 필터링이 제거 되어 사용자 환경에 표시 되는 URL의 전체 보기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-413">In the URL flyout dialog, the filtering on email messages is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="e40ba-414">이를 통해 탐색기의 전자 메일 메시지를 관심 있는 항목으로 필터링 하 고, 잠재적인 위협이 되는 특정 Url을 찾은 다음, url 필터 대화 상자를 통해 해당 환경의 URL 노출에 대 한 이해를 탐색기 보기 자체에 추가 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-414">This lets you filter down email messages in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-different-click-verdicts"></a><span data-ttu-id="e40ba-415">다른 클릭 verdicts 해석</span><span class="sxs-lookup"><span data-stu-id="e40ba-415">Interpretation of different click verdicts</span></span>

<span data-ttu-id="e40ba-416">전자 메일 또는 URL flyouts에서 위쪽 클릭을 비롯 하 여 필터링 환경 내에서 찾기 환경의 일부로 다른 클릭 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-416">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you will see different click values as part of your hunting experience.</span></span> <span data-ttu-id="e40ba-417">다음은 Verdicts 클릭 가능한 값과 해석 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-417">Below are the possible values of Click Verdicts and their interpretation:</span></span>

- <span data-ttu-id="e40ba-418">**없음**: URL에 대 한 결과를 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-418">**None**: We were unable to capture the verdict for the URL.</span></span> <span data-ttu-id="e40ba-419">사용자가 URL을 클릭 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-419">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="e40ba-420">**허용**: 사용자가 URL로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-420">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="e40ba-421">**차단 됨**: 사용자가 URL로 이동할 수 없도록 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-421">**Blocked**: The User was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="e40ba-422">**보류 중인 결과**: 사용자에 게 샌드 박싱 Pending 페이지와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-422">**Pending verdict**: The user was presented with the detonation pending page.</span></span>
- <span data-ttu-id="e40ba-423">**차단 된 재정의**: 사용자가 URL로 이동할 수 없도록 차단 되었습니다. 그러나 사용자가이 블록에서 URL로 이동 하는 것을 중단 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-423">**Blocked overridden**: The user was blocked from navigating to the URL; however, the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="e40ba-424">**결과 바이패스 보류**: 사용자에 게 샌드 박싱 페이지와 함께 제공 됩니다. 그러나 사용자가 페이지를 제거 하 여 URL로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-424">**Pending verdict bypassed**: The user was presented with the detonation page; however, the user overrode the page to navigate to the URL.</span></span>
- <span data-ttu-id="e40ba-425">**오류**: 사용자에 게 오류 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-425">**Error**: The user was presented with the error page.</span></span> <span data-ttu-id="e40ba-426">또한 결과를 캡처하는 중에 오류가 발생 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-426">This can also mean there was an error in capturing the verdict.</span></span>
- <span data-ttu-id="e40ba-427">**실패**: 결과를 캡처하는 동안 알 수 없는 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-427">**Failure**: There was unknown exception while capturing the verdict.</span></span> <span data-ttu-id="e40ba-428">사용자가 URL을 클릭 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-428">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="e40ba-429">사용자가 보고 한 전자 메일 메시지 검토</span><span class="sxs-lookup"><span data-stu-id="e40ba-429">Review email messages reported by users</span></span>

<span data-ttu-id="e40ba-430">조직의 사용자가 [outlook 및 웹용 outlook에 대 한 보고서 메시지 추가 기능](enable-the-report-message-add-in.md)을 사용 하 여 정크 메일 또는 피싱이 아닌 메시지를 보고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-430">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="e40ba-431">이 작업을 수행 하려면 [전자 메일 > 전송](threat-explorer-views.md#email--submissions) Explorer (또는 실시간 검색)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-431">To do this, use the [Email > Submissions](threat-explorer-views.md#email--submissions) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="e40ba-432">보안 & 준수 센터 ()에서 [https://protection.office.com](https://protection.office.com) **Threat management**  >  **Explorer** (또는 **실시간**검색)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-432">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="e40ba-433">(이 예제에서는 탐색기를 사용 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e40ba-433">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="e40ba-434">**보기** 메뉴에서 **전자 메일**  >  **제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-434">In the **View** menu, choose **Email** > **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40ba-435">![탐색기에 대 한 보기 메뉴](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-435">![View menu for Explorer](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="e40ba-436">**보낸 사람**을 클릭 한 다음 **기본**  >  **보고서 유형을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-436">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="e40ba-437">**피싱**등의 옵션을 선택 하 고 **새로 고침** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-437">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e40ba-438">![사용자가 보고 한 피싱](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="e40ba-438">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="e40ba-439">보고서가 새로 고쳐지고 조직의 사용자가 피싱 시도로 보고 한 전자 메일 메시지에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-439">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="e40ba-440">이 정보를 사용 하 여 추가 분석을 수행 하 고, 필요한 경우 [ATP 피싱 방지 정책을](configure-atp-anti-phishing-policies.md)조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-440">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="e40ba-441">자동 조사 및 응답 시작</span><span class="sxs-lookup"><span data-stu-id="e40ba-441">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="e40ba-442">자동화 된 조사 및 응답 기능은 **office 365 ATP 계획 2** 및 **Office 365 E5**에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-442">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="e40ba-443">(새로운 방법!) [자동화 된 조사 및 응답](automated-investigation-response-office.md) 을 통해 보안 운영 팀이 고 사이버 공격을 조사 및 완화할 때 필요한 시간과 노력을 많이 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-443">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="e40ba-444">보안 playbook 트리거될 수 있는 알림을 구성 하는 것 외에도 탐색기의 보기에서 자동화 된 조사 및 응답 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-444">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span>

<span data-ttu-id="e40ba-445">이에 대 한 자세한 내용은 [예제: 보안 관리자가 탐색기에서 조사를 트리거하는 예](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e40ba-445">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="e40ba-446">Explorer (또는 실시간 검색)를 사용 하는 여러 방법</span><span class="sxs-lookup"><span data-stu-id="e40ba-446">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="e40ba-447">이 문서에서 설명 하는 시나리오 외에도 Explorer (또는 실시간 검색)에서 사용할 수 있는 보고 옵션이 더 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-447">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span>

- [<span data-ttu-id="e40ba-448">배달된 악성 전자 메일 찾기 및 조사</span><span class="sxs-lookup"><span data-stu-id="e40ba-448">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="e40ba-449">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="e40ba-449">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="e40ba-450">위협 탐색기 및 실시간 검색의 보기에 대 한 개요 보기</span><span class="sxs-lookup"><span data-stu-id="e40ba-450">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="e40ba-451">Microsoft Threat Protection의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="e40ba-451">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="e40ba-452">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="e40ba-452">Required licenses and permissions</span></span>

<span data-ttu-id="e40ba-453">Explorer 또는 실시간 검색을 하려면 [Office 365 ATP](office-365-atp.md) 가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-453">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>

- <span data-ttu-id="e40ba-454">Explorer는 Office 365 ATP 계획 2에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-454">Explorer is included in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="e40ba-455">실시간 검색 보고서는 Office 365 ATP 계획 1에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-455">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="e40ba-456">Office 365 ATP로 보호 해야 하는 모든 사용자에 대해 라이선스를 할당 하도록 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-456">Plan to assign licenses for all users who should be protected by Office 365 ATP.</span></span> <span data-ttu-id="e40ba-457">(탐색기 또는 실시간 검색은 사용이 허가 된 사용자에 대 한 검색 데이터를 표시 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e40ba-457">(Explorer or real-time detections shows detection data for licensed users.)</span></span>

<span data-ttu-id="e40ba-458">탐색기 또는 실시간 검색을 보고 사용 하려면 보안 관리자 또는 보안 판독기에 부여 된 것과 같은 적절 한 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-458">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="e40ba-459">보안 &amp; 및 준수 센터에는 다음 역할 중 하나가 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-459">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="e40ba-460">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e40ba-460">Organization Management</span></span>
  - <span data-ttu-id="e40ba-461">보안 관리자 (Azure Active Directory 관리 센터에서 할당할 수 [https://aad.portal.azure.com](https://aad.portal.azure.com) 있음)</span><span class="sxs-lookup"><span data-stu-id="e40ba-461">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="e40ba-462">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="e40ba-462">Security Reader</span></span>

- <span data-ttu-id="e40ba-463">Exchange Online의 경우 Exchange 관리 센터 ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) 또는 PowerShell cmdlet ( [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)참조)에서 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-463">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="e40ba-464">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e40ba-464">Organization Management</span></span>
  - <span data-ttu-id="e40ba-465">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="e40ba-465">View-only Organization Management</span></span>
  - <span data-ttu-id="e40ba-466">보기 권한만 있는 받는 사람 역할</span><span class="sxs-lookup"><span data-stu-id="e40ba-466">View-Only Recipients role</span></span>
  - <span data-ttu-id="e40ba-467">준수 관리</span><span class="sxs-lookup"><span data-stu-id="e40ba-467">Compliance Management</span></span>

<span data-ttu-id="e40ba-468">역할 및 사용 권한에 대 한 자세한 내용은 다음 리소스를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e40ba-468">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="e40ba-469">보안 및 준수 센터의 사용 권한 &amp;</span><span class="sxs-lookup"><span data-stu-id="e40ba-469">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="e40ba-470">Exchange Online의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="e40ba-470">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="e40ba-471">위협 탐색기와 실시간 감지 간의 약간의 차이점</span><span class="sxs-lookup"><span data-stu-id="e40ba-471">Some differences between Threat Explorer and real-time detections</span></span>

- <span data-ttu-id="e40ba-472">**실시간** 검색 보고서는 OFFICE 365 atp 계획 1에서 사용할 수 있지만, **Threat Explorer** 는 office 365 atp 계획 2에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-472">The **real-time detections** report is available in Office 365 ATP Plan 1, whereas **Threat Explorer** is available in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="e40ba-473">**실시간** 검색 보고서를 사용 하면 검색을 실시간으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-473">The **real-time detections** report allows you to view detections in real time.</span></span> <span data-ttu-id="e40ba-474">**위협 탐색기** 도이를 수행 하지만 지정 된 공격에 대 한 추가 세부 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-474">**Threat Explorer** does this as well, but also allows you to view additional details for a given attack.</span></span>
- <span data-ttu-id="e40ba-475">**모든 전자 메일** 보기는 **위협 탐색기** 에서 사용할 수 있으며 **실시간** 검색 보고서에는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-475">An **All email** view is available in **Threat Explorer** (and is not in the **real-time detections** report).</span></span>
- <span data-ttu-id="e40ba-476">**위협 탐색기**에는 추가 필터링 기능 및 사용 가능한 작업이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40ba-476">More filtering capabilities and available actions are included in **Threat Explorer**.</span></span>

<span data-ttu-id="e40ba-477">자세한 내용은 [Office 365 Atp 서비스 설명: atp (Advanced Threat Protection) 계획에서의 기능 사용 가능 여부](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e40ba-477">For more details, see [Office 365 ATP Service Description: Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
