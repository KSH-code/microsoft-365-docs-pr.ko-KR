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
description: 보안 및 준수 센터에서 탐색기 및 실시간 & 사용하여 위협을 효과적으로 조사하고 대응하는 방법을 알아보십시오.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4328bfc52497f911c57256f8366b3742523b17b0
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615567"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="dd9eb-103">위협 탐색기 및 실시간 검색</span><span class="sxs-lookup"><span data-stu-id="dd9eb-103">Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="dd9eb-104">조직에 [Microsoft Defender for Office 365가](office-365-atp.md) [](#required-licenses-and-permissions)있으며 필요한 권한이 있는 경우  **탐색기** 또는 실시간 검색(이전의 실시간 [](#new-features-in-threat-explorer-and-real-time-detections)보고서 *)* 중 하나를 사용할 수 있습니다. 새로운 기능 확인</span><span class="sxs-lookup"><span data-stu-id="dd9eb-104">If your organization has [Microsoft Defender for Office 365](office-365-atp.md), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **Real-time detections** (formerly *Real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="dd9eb-105">보안 & 준수 센터에서 **위협** 관리로 이동한 다음 **탐색기**  또는 실시간 검색을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

|<span data-ttu-id="dd9eb-106">Microsoft Defender for Office 365 요금제 2를 사용하면 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-106">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="dd9eb-107">Microsoft Defender for Office 365 요금제 1을 사용하면 다음이 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-107">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![위협 탐색기](../../media/threatmgmt-explorer.png)|![실시간 탐지](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="dd9eb-110">탐색기(또는 실시간 검색)를 사용하면 보안 운영 팀이 위협을 효과적으로 조사하고 대응할 수 있는 강력한 보고서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-110">With Explorer (or Real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently.</span></span> <span data-ttu-id="dd9eb-111">보고서는 다음 이미지와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-111">The report resembles the following image:</span></span>

![위협 관리 \> 탐색기로 이동](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="dd9eb-113">이 보고서를 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-113">With this report, you can:</span></span>

- [<span data-ttu-id="dd9eb-114">Microsoft 365 보안 기능에서 검색된 맬웨어 보기</span><span class="sxs-lookup"><span data-stu-id="dd9eb-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="dd9eb-115">피싱 URL에 대한 데이터 보기 및 판정 클릭</span><span class="sxs-lookup"><span data-stu-id="dd9eb-115">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="dd9eb-116">[탐색기 보기에서](#start-automated-investigation-and-response) 자동화된 조사 및 응답 프로세스 시작(Office 365 계획 2용 Defender만 해당)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- <span data-ttu-id="dd9eb-117">... [악의적인 전자 메일 조사 등!](#more-ways-to-use-explorer-or-real-time-detections)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-117">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dd9eb-118">위협 탐색기 및 실시간 검색 기능 개선</span><span class="sxs-lookup"><span data-stu-id="dd9eb-118">Experience Improvements to Threat Explorer and Real-time detections</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="dd9eb-119">위협 탐색기에서 태그</span><span class="sxs-lookup"><span data-stu-id="dd9eb-119">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="dd9eb-120">사용자 태그 기능은 미리 보기에 있으며 모든 사용자가 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-120">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="dd9eb-121">릴리스 일정에 대한 자세한 내용은 Microsoft 365 로드맵을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-121">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="dd9eb-122">사용자 태그는 Office 365용 Microsoft Defender의 특정 사용자 그룹에 대한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-122">User tags are identifiers for specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="dd9eb-123">태그, 라이선스 및 태그 구성에 대한 자세한 내용은 [사용자 태그를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-123">For more information around tags, licensing and configuring tags, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="dd9eb-124">위협 탐색기 내에서 다음 환경의 사용자 태그 관련 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-124">Within Threat Explorer, you can see information around user tags in the following experiences:</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="dd9eb-125">전자 메일 그리드 보기</span><span class="sxs-lookup"><span data-stu-id="dd9eb-125">Email Grid View</span></span>

<span data-ttu-id="dd9eb-126">전자 메일 표에 표시된 태그 열에는 보낸 사람 또는 받는 사람 사서함에 적용된 모든 태그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-126">The Tags column shown in the email grid would contain all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="dd9eb-127">기본적으로 우선 순위 계정과 같은 시스템 태그가 먼저 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-127">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-128">![전자 메일 그리드 보기에서 태그 필터링](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-128">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="dd9eb-129">필터링</span><span class="sxs-lookup"><span data-stu-id="dd9eb-129">Filtering</span></span>

<span data-ttu-id="dd9eb-130">이제 태그를 필터로 사용하여 우선 순위 계정 또는 특정 사용자 태그 시나리오를 검색할 수 있습니다(이 환경의 일부로 특정 태그가 있는 결과를 제외).</span><span class="sxs-lookup"><span data-stu-id="dd9eb-130">We now have Tags as a filter so you can hunt just across priority accounts, or specific User tags scenarios (and even exclude results with certain tags as part of this experience).</span></span> <span data-ttu-id="dd9eb-131">이러한 필터를 제공하는 여러 다른 필터와 결합하면 조사 범위를 좁히는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-131">Combining these with the multiple other filters that we provide, would help you to narrow down your scope of investigation</span></span>

<span data-ttu-id="dd9eb-132">[![필터 태그](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-132">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-133">![필터 태그 아미](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-133">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="dd9eb-134">전자 메일 세부 정보 플라이아웃</span><span class="sxs-lookup"><span data-stu-id="dd9eb-134">Email Detail Flyout</span></span>
<span data-ttu-id="dd9eb-135">보낸 사람 및 받는 사람에 대한 개별 태그를 보려면 제목을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-135">To view the individual tags for sender and Recipient, click on the subject.</span></span> <span data-ttu-id="dd9eb-136">메시지 세부 정보 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-136">It opens the message details flyout.</span></span> <span data-ttu-id="dd9eb-137">요약 탭에서 보낸 사람 및 받는 사람 태그가 전자 메일에 대해 표시되는 경우 별도로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-137">In the summary tab, sender and recipient tags are shown separately, if they are present for an email.</span></span>
<span data-ttu-id="dd9eb-138">보낸 사람 및 받는 사람에 대한 개별 태그에 대한 정보도 내보낼 수 있는 CSV로 확장되어 두 개의 개별 열에서 이러한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-138">The information about individual tags for sender and Recipient, also extends to exported CSV, where you can see these details in 2 separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-139">![전자 메일 세부 정보 태그](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-139">![Email Details Tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="dd9eb-140">태그 정보는 URL 클릭 플라이아웃에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-140">Tags information is also shown in URL clicks flyout.</span></span> <span data-ttu-id="dd9eb-141">URL 클릭 플라이아웃으로 이동하려면 피싱 또는 모든 전자 메일 보기로 이동한 다음 URL 또는 URL 클릭 탭으로 이동해야 합니다. 개별 URL 플라이아웃을 클릭하면 해당 URL의 클릭에 대한 자세한 정보가 표시될 수 있으며 해당 클릭과 태그가 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-141">To get to the URL clicks flyout, you would need to go to Phish or All Email view, and then to URLs or URL Clicks Tab. Clicking on an individual URL flyout would show more details about Clicks for that URL, and would have Tags associated with that click.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-142">![URL 태그](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-142">![URL Tags](../../media/tags-urls.png)</span></span>

## <a name="improvements-to-threat-hunting-experience-upcoming"></a><span data-ttu-id="dd9eb-143">위협 헌팅 환경 개선(예정)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-143">Improvements to Threat Hunting Experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="dd9eb-144">전자 메일에 대한 위협 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="dd9eb-144">Updated Threat Information for Emails</span></span>

<span data-ttu-id="dd9eb-145">당사는 전자 메일 레코드에 대한 데이터 정확도 및 일관성을 높이기 위해 플랫폼 및 데이터 품질 개선에 집중하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-145">We have focused on platform and data quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="dd9eb-146">이러한 업데이트 집합에는 배달 전 정보 및 배달 후 정보(예: ZAP 프로세스의 일부로 전자 메일에서 실행된 작업)를 단일 레코드로 통합하고 스팸 판정, 엔터티 수준 위협(예: 악의적인 URL) 및 최신 배달 위치와 같은 풍부한 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-146">These set of updates includes consolidation of pre-delivery and post-delivery information (example action executed on an email as part of ZAP process) into a single record  along with added richness like Spam verdict, Entity level threats (e.g., which URL was malicious) and latest delivery locations.</span></span>

<span data-ttu-id="dd9eb-147">이러한 업데이트 후 메시지에 대해 진행된 다양한 배달 후 이벤트에 관계없이 각 메시지에 대한 단일 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-147">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that have taken place on the message.</span></span> <span data-ttu-id="dd9eb-148">작업에는 ZAP, 수동 수정(관리자 작업), 동적 배달 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-148">Actions can include ZAP, Manual Remediation (which means admin action), Dynamic Delivery etc.</span></span>

<span data-ttu-id="dd9eb-149">맬웨어 및 피싱 위협을 표시하는 것 외에도 이제 전자 메일과 관련된 스팸 판정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-149">In addition to showing malware and phish threats, you'll now be able to see spam verdict associated with an email.</span></span> <span data-ttu-id="dd9eb-150">전자 메일 내에서 해당 검색 기술과 함께 전자 메일과 관련된 모든 위협을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-150">Within the email, you will be able to see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="dd9eb-151">각 전자 메일에는 0, 1 또는 여러 위협이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-151">Each email can have 0, 1, or multiple threats.</span></span> <span data-ttu-id="dd9eb-152">전자 메일 플라이아웃의 세부 정보 섹션에 현재 위협이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-152">You'll see the current Threats in the Details section of the Email flyout.</span></span> <span data-ttu-id="dd9eb-153">또한 여러 위협(예: 맬웨어와 피싱이 모두 있는 전자 메일)의 경우 검색 기술 필드는 Threat-Detection 매핑을 제공하게 하여 위협 식별을 이행한 검색 기술을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-153">Additionally, for multiple threats (e.g., an email having both Malware and Phish), Detection tech field would give the Threat-Detection mapping, meaning which detection tech led to the identification of the Threat.</span></span>

<span data-ttu-id="dd9eb-154">새로운 검색 방법과 스팸 검색 기술을 포함하기 위해 업데이트된 검색 기술 집합은 모든 다른 전자 메일 보기(맬웨어, 피싱, 모든 전자 메일)에서 동일하고 일관된 검색 기술 집합을 사용하여 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-154">The set of detection technologies has been updated to include new detection methods, as well as spam detection technologies, and across all the different email views (Malware, Phish, All Email), you'll have the same, consistent set of Detection technologies to filter the results.</span></span>

> [!NOTE]
> <span data-ttu-id="dd9eb-155">결과 분석이 반드시 엔터티에 연결되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-155">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="dd9eb-156">예를 들어 전자 메일은 피싱 또는 스팸으로 분류될 수 있지만 피싱/스팸 판정이 스탬프 처리된 URL은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-156">As an example, an email might be classified as Phish or Spam, but there are no URLs which have any Phish/Spam verdict stamped on them.</span></span> <span data-ttu-id="dd9eb-157">이는 결과를 할당하기 전에 필터가 전자 메일의 콘텐츠 및 기타 세부 정보도 평가하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-157">This is because our filters also evaluate content and other details for an email, before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="dd9eb-158">URL의 위협</span><span class="sxs-lookup"><span data-stu-id="dd9eb-158">Threats in URLs</span></span>

<span data-ttu-id="dd9eb-159">전자 메일 플라이아웃 > 세부 정보 탭에서 URL에 대한 특정 위협을 볼 수 있습니다(URL에 대한 위협은 맬웨어, 피싱, 스팸 또는 없음일 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="dd9eb-159">Within email flyout-> Details tab, you would now be able to see the specific threat for a URL (Threat for a URL can be Malware, Phish, Spam or None)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-160">![URL 위협](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-160">![URL Threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="dd9eb-161">업데이트된 시간 표시 막대 보기(예정된)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-161">Updated Timeline View (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-162">![업데이트된 시간 표시 막대 보기](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-162">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="dd9eb-163">타임라인 보기는 모든 배달 및 배달 후 이벤트를 식별하는 것 외에도 이러한 이벤트의 하위 집합에 대해 해당 시점에 식별된 위협에 대한 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-163">In addition to identifying all delivery and post-delivery events, timeline view also gives information about the Threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="dd9eb-164">또한 추가 작업(예: ZAP, 수동 수정)과 해당 작업의 결과에 대한 자세한 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-164">It also gives you more information about Additional Actions (e.g., ZAP, Manual Remediation) along with the Result of that action.</span></span> <span data-ttu-id="dd9eb-165">시간 표시 막대 보기에는 원래 배달 및 이후에 전자 메일에서 수행된 모든 배달 후 이벤트에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-165">Timeline view contains information about the Original delivery and subsequently any post-delivery events performed on an email.</span></span>

- <span data-ttu-id="dd9eb-166">원본: 이벤트의 원본에 따라 관리자/시스템/사용자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-166">Source: This can be Admin/System/user based on what was the source of the event.</span></span>
- <span data-ttu-id="dd9eb-167">이벤트: 여기에는 원본 배달, 수동 수정, ZAP, 제출 및 동적 배달과 같은 최상위 이벤트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-167">Event: This includes top-level events like Original Delivery, Manual Remediation, ZAP, Submissions, and Dynamic Delivery.</span></span>
- <span data-ttu-id="dd9eb-168">작업: ZAP 또는 관리자 작업의 일부로 수행된 특정 작업(예: 소프트 삭제)에 대해 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-168">Action: This covers the specific action that was taken either as part of ZAP or Admin Action (e.g., Soft Delete).</span></span>
- <span data-ttu-id="dd9eb-169">위협: 시점에서 식별된 위협(맬웨어, 피싱, 스팸)을 다 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-169">Threats: Covers the threats (Malware, Phish, Spam) identified at that point of time.</span></span>
- <span data-ttu-id="dd9eb-170">결과/세부 정보: ZAP/관리자 작업의 일부로 수행된지 여부에 대한 작업의 결과에 대한 자세한 내용을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-170">Result/Details: Covers more information about the Result of the Action, whether it was performed as part of ZAP/Admin Action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="dd9eb-171">원본 및 최신 배달 위치</span><span class="sxs-lookup"><span data-stu-id="dd9eb-171">Original and Latest Delivery location</span></span>

<span data-ttu-id="dd9eb-172">현재, 전자 메일 그리드 및 전자 메일 플라이아웃 내에 배달 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-172">Today, we surface delivery Location within email grid and email flyout.</span></span> <span data-ttu-id="dd9eb-173">앞으로 배달 위치 필드의 이름을 원래 배달 위치로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-173">Going forward, the Delivery Location field will be renamed to Original Delivery Location.</span></span> <span data-ttu-id="dd9eb-174">또한 최신 배달 위치라는 다른 필드도 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-174">Additionally, we're also introducing another field called Latest delivery location.</span></span>

<span data-ttu-id="dd9eb-175">원래 배달 위치는 처음에 전자 메일이 배달된 위치에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-175">The original delivery location would give more information about where an email was delivered initially.</span></span> <span data-ttu-id="dd9eb-176">최신 배달 위치에는 ZAP와 같은 시스템 작업 또는 삭제된 항목으로 이동과 같은 관리자 작업 후 전자 메일이 전송될 수 있는 **위치가 포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-176">The latest delivery location would include location where an email may have landed after system actions like ZAP or admin actions like **Move to Deleted Items**.</span></span> <span data-ttu-id="dd9eb-177">최신 배달 위치는 메시지의 배달 후 또는 시스템/관리자 작업을 관리자에게 알리기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-177">Latest delivery location is intended to inform admins of the message's last known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="dd9eb-178">기본적으로 전자 메일에 대한 최종 사용자 관련 작업은 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-178">By design, it doesn't include any end-user-related actions on the email.</span></span> <span data-ttu-id="dd9eb-179">예를 들어 사용자가 메시지를 삭제하거나 메시지를 보관/pst로 이동하면 "배달" 메시지가 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-179">For example: if a user deletes a message or moves the message to archive/pst, the message "delivery" location will not be updated.</span></span> <span data-ttu-id="dd9eb-180">그러나 시스템 작업이 위치를 업데이트한 경우(예: ZAP로 인해 전자 메일이 Quarantine으로 이동) 최신 배달 위치가 Quarantine으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-180">However, if a system action updated the location (e.g., ZAP resulting in an email moving to Quarantine), you would see the Latest delivery location as Quarantine.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-181">![업데이트된 배달 위치](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-181">![Updated Delivery Locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="dd9eb-182">배달 위치 및 배달 작업이 값으로 '알 수 없음'을 표시하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-182">There are few cases where Delivery Location and Delivery Action may show 'Unknown' as the value:</span></span>
>
> - <span data-ttu-id="dd9eb-183">배달 위치가 배달된 위치로 표시될 수 있으며 배달 위치는 알 수 없음으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-183">You might see Delivery location as Delivered, and Delivery Location as Unknown.</span></span> <span data-ttu-id="dd9eb-184">이 문제는 메시지가 배달되지만 받은 편지함 규칙이 메시지를 받은 편지함 또는 정크 메일 폴더 대신 기본 폴더(임시, 보관 등)로 이동한 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-184">This happens when the message was delivered, but an Inbox rule moved the message to a default folder (Draft, Archive, etc.) instead of the Inbox or Junk Email folders.</span></span>
>
> - <span data-ttu-id="dd9eb-185">관리자/시스템 작업(예: ZAP, 관리자 작업)을 시도했지만 메시지를 찾을 수 없는 경우 최신 배달 위치를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-185">Latest Delivery Location can be unknown if an admin/system action (e.g., ZAP, Admin Action) is attempted, but the message isn't found.</span></span> <span data-ttu-id="dd9eb-186">일반적으로 이 작업은 사용자가 메시지를 이동하거나 삭제한 후에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-186">Typically, the action happens after the user has moved or deleted the Message.</span></span> <span data-ttu-id="dd9eb-187">이러한 경우 시간 표시 막대 보기에서 결과/세부 정보 열을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-187">In such cases, verify the Result/Details Column in timeline view.</span></span> <span data-ttu-id="dd9eb-188">메시지를 찾아야 합니다. 사용자가 이동하거나 삭제한 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-188">Look for the message: Message moved or deleted by the user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-189">![시간 표시 막대의 배달 위치](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-189">![Delivery Locations for Timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="dd9eb-190">추가 작업</span><span class="sxs-lookup"><span data-stu-id="dd9eb-190">Additional Actions</span></span>

<span data-ttu-id="dd9eb-191">추가 작업은 전자 메일 배달 후 적용된 작업으로 구성되고 ZAP, 수동 수정(예: 관리자가 수행한 작업( 예: 소프트 삭제), 동적 배달 및 다시 처리(전자 메일이 소급적으로 양호한 것으로 감지)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-191">Additional Actions consist of the actions that were applied post the delivery of the Email, and can include ZAP, Manual Remediation (action taken by an Admin e.g., Soft Delete), Dynamic Delivery, and Reprocessed (an email was retroactively detected as good).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="dd9eb-192">이 변경의 일부로 현재 배달 작업 필터에 표시되어 있는 ZAP에서 제거됨 값이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-192">As part of this change, the Removed by ZAP value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="dd9eb-193">추가 작업을 통해 ZAP가 시도된 모든 전자 메일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-193">You'll have a way to search for all email with the ZAP attempt through the Additional Actions.</span></span>
>
> - <span data-ttu-id="dd9eb-194">검색 기술 및 추가 작업(특히 ZAP 시나리오의 경우)에 대한 새 필드와 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-194">There will be new fields and values for Detection technologies and Additional actions (especially for ZAP scenarios).</span></span> <span data-ttu-id="dd9eb-195">기존 저장된 쿼리 및 추적된 쿼리를 평가하여 새 값으로 작동하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-195">Evaluate your existing Saved Queries and Tracked queries to make sure they work with the new values.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-196">![탐색기에서 추가 작업](../../media/Additional_Actions.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-196">![Additional Actions in Explorer](../../media/Additional_Actions.png)</span></span>

### <a name="system-overrides"></a><span data-ttu-id="dd9eb-197">시스템 오버라이드</span><span class="sxs-lookup"><span data-stu-id="dd9eb-197">System overrides</span></span>

<span data-ttu-id="dd9eb-198">시스템 다시 설정은 시스템에서 제공한 배달 위치(필터링 스택에서 식별된 위협 및 기타 검색에 따라)를 다시 설정하여 메시지의 의도된 배달 위치에 예외를 만드는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-198">System overrides are a method of making exceptions to the intended delivery location of a message by overriding the delivery location provided by system (based on the threats and other detections identified by our filtering stack).</span></span> <span data-ttu-id="dd9eb-199">시스템 오버라이드는 테넌트 또는 사용자 정책을 통해 정책에서 제안한 메시지를 배달하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-199">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="dd9eb-200">다시 설정은 구성 간격(예: 사용자가 설정한 매우 광범위한 수신 -보낸 사람 정책)으로 인해 의도하지 않은 악성 메시지 배달을 식별하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-200">Overrides are useful in identifying any unintentional delivery of malicious messages due to configurations gaps (for example, a very broad Safe Sender policy set by a user).</span></span> <span data-ttu-id="dd9eb-201">이러한 은(는) 다음 값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-201">These override values can be:</span></span>

- <span data-ttu-id="dd9eb-202">사용자 정책에서 허용: 사용자가 사서함 수준에서 정책을 만들어 도메인 또는 보낸 사람이 허용하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-202">Allowed by user policy: This is when a user allows domains or senders by creating policies at the mailbox level.</span></span>
- <span data-ttu-id="dd9eb-203">사용자 정책에 의해 차단: 사용자가 사서함 수준에서 정책을 만들어 도메인 또는 보낸 사람 차단을 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-203">Blocked by user policy: This is when a user blocks domains or senders by creating policies at the mailbox level.</span></span>
- <span data-ttu-id="dd9eb-204">조직 정책에서 허용: 조직의 보안 팀에서 조직의 사용자에 대해 보낸 사람 및 도메인을 허용하도록 정책 또는 Exchange 메일 흐름 규칙(전송 규칙)을 설정하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-204">Allowed by org policy: This is when the organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="dd9eb-205">사용자 집합 또는 전체 조직에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-205">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="dd9eb-206">조직 정책에 의해 차단: 조직의 보안 팀에서 정책 또는 메일 흐름 규칙을 설정하여 조직의 사용자에 대한 보낸 사람, 도메인, 메시지 언어 또는 원본 IPS를 차단하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-206">Blocked by org policy: This is when the organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="dd9eb-207">사용자 집합이나 전체 조직에 대한 설정일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-207">This can also be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="dd9eb-208">조직 정책에 의해 차단되는 파일 확장명: 맬웨어 방지 정책 설정을 통해 조직의 보안 팀에 의해 파일 형식 확장명을 차단하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-208">File extension blocked by org policy: This is when a file type extension is blocked by the security teams of an organization through the anti-malware policy settings.</span></span> <span data-ttu-id="dd9eb-209">이제 조사에 도움이 될 수 있도록 이러한 값이 전자 메일 세부 정보로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-209">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="dd9eb-210">또한 Secops 팀은 다양한 필터링 기능을 사용하여 차단된 파일 확장명을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-210">Secops teams can also filter on blocked file extensions using the rich filtering capability.</span></span>

<span data-ttu-id="dd9eb-211">[![탐색기에서 시스템 오버라이드](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-211">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-212">![탐색기에서 시스템 눈금을 오버라이드](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-212">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-around-url-and-clicks-experience"></a><span data-ttu-id="dd9eb-213">URL 및 클릭 경험 개선</span><span class="sxs-lookup"><span data-stu-id="dd9eb-213">Improvements around URL and Clicks Experience</span></span>

<span data-ttu-id="dd9eb-214">URL 및 URL 클릭 데이터에 초점을 맞추는 개선 사항 집합은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-214">The set of improvements focused towards URL and URL clicks data include:</span></span>

- <span data-ttu-id="dd9eb-215">URL 플라이아웃의 Clicks 섹션 내에 전체 클릭된 URL(URL의 일부인 쿼리 매개 변수 포함)을 표시</span><span class="sxs-lookup"><span data-stu-id="dd9eb-215">Showing full Clicked URL (including any query Parameters which are part of URL) within the Clicks Section in URL Flyout.</span></span> <span data-ttu-id="dd9eb-216">현재 제목 표시줄에 URL 도메인 및 경로가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-216">Currently we show the URL domain and path in title bar.</span></span> <span data-ttu-id="dd9eb-217">전체 URL을 표시하기 위해 해당 정보를 확장하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-217">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="dd9eb-218">여러 URL 필터(URL과 URL 도메인 및 URL 도메인 및 경로) 픽스: URL/클릭 결과를 포함하는 메시지 검색에 대한 업데이트를 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-218">Fixes across URL filters (URL vs URL domain vs URL Domain and path): We've made updates around searching for messages that contain a URL/Click verdict.</span></span> <span data-ttu-id="dd9eb-219">그 일환으로 프로토콜에 대한 무관한 검색 지원을 사용하도록 설정했습니다(즉, http가 없는 URL을 직접 검색할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="dd9eb-219">As part of that, we've enabled support for protocol agnostic searches (meaning, you can directly search for a URL without http).</span></span> <span data-ttu-id="dd9eb-220">기본적으로 URL 검색은 명시적으로 지정되지 않은 경우 http에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-220">By default, the URL search maps to http, unless explicitly specified.</span></span> <span data-ttu-id="dd9eb-221">예시:</span><span class="sxs-lookup"><span data-stu-id="dd9eb-221">For example:</span></span>

  1. <span data-ttu-id="dd9eb-222">"URL", "URL 도메인" 및 "URL 도메인 및 경로" 필터 필드에 있는 경우와 없이 `http://` 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-222">Search with and without the `http://` prefix in "URL", "URL Domain", and "URL Domain and Path" filter fields.</span></span> <span data-ttu-id="dd9eb-223">이 동작은 일관성이 있으며 동일한 결과를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-223">This behavior is consistent, and should show the same result.</span></span>

  1. <span data-ttu-id="dd9eb-224">`https://`"URL"에서 사전을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-224">Search for the `https://` prefix in "URL".</span></span> <span data-ttu-id="dd9eb-225">이 두 개가 없는 경우, 이 `http://` 전제가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-225">When not present, the `http://` prefix is assumed.</span></span>

  1. <span data-ttu-id="dd9eb-226">`/` "URL 경로", "URL 도메인", "URL 도메인 및 경로" 필드의 시작과 끝은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-226">`/` in beginning and end of the "URL path", "URL Domain", "URL domain and path" fields is ignored.</span></span> <span data-ttu-id="dd9eb-227">`/` 끝에 있는 "URL" 필드는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-227">`/` at the end of the "URL" field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="dd9eb-228">피싱 지수</span><span class="sxs-lookup"><span data-stu-id="dd9eb-228">Phish Confidence Level</span></span>

<span data-ttu-id="dd9eb-229">피싱 신뢰 수준은 전자 메일이 피싱으로 분류된 신뢰 수준을 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-229">Phish confidence level helps to identify the degree of confidence, with which an email was categorized as Phish.</span></span> <span data-ttu-id="dd9eb-230">가능한 두 값은 높음과 보통입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-230">The two possible values are High and Normal.</span></span> <span data-ttu-id="dd9eb-231">초기 단계에서 이 필터는 위협 탐색기 피싱 보기에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-231">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="dd9eb-232">[![탐색기에서 피싱 지수](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-232">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="dd9eb-233">ZAP URL 신호</span><span class="sxs-lookup"><span data-stu-id="dd9eb-233">ZAP URL Signal</span></span>

<span data-ttu-id="dd9eb-234">일반적으로 전자 메일이 피싱으로 식별되고 배달 후 제거된 ZAP 피싱 경고 시나리오에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-234">Typically used for ZAP Phish Alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="dd9eb-235">이 설정은 경고를 탐색기에서 해당 결과와 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-235">This is used to connect the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="dd9eb-236">이 이벤트는 경고에 대한 IOC 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-236">It is one of the IOCs for the alert.</span></span>

<span data-ttu-id="dd9eb-237">헌팅 프로세스 개선의 일환으로 위협 탐색기 및 실시간 검색을 몇 가지 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-237">As part of improving the hunting process, we have made a few updates to Threat Explorer and Real-time detections.</span></span> <span data-ttu-id="dd9eb-238">다음은 헌팅 환경을 보다 일관되게 만드는 데 중점을 두는 '환경' 개선입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-238">These are 'experience' improvements, with the focus on making the hunting experience more consistent.</span></span> <span data-ttu-id="dd9eb-239">이러한 변경 내용은 아래에서 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-239">These changes are outlined below:</span></span>

- [<span data-ttu-id="dd9eb-240">개선된 시간제</span><span class="sxs-lookup"><span data-stu-id="dd9eb-240">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="dd9eb-241">새로 고침 프로세스에서 업데이트</span><span class="sxs-lookup"><span data-stu-id="dd9eb-241">Update in the Refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="dd9eb-242">필터에 추가할 차트 드릴다운</span><span class="sxs-lookup"><span data-stu-id="dd9eb-242">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="dd9eb-243">제품 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="dd9eb-243">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="dd9eb-244">사용자 태그로 필터링</span><span class="sxs-lookup"><span data-stu-id="dd9eb-244">Filter by user tags</span></span>

<span data-ttu-id="dd9eb-245">이제 시스템 또는 사용자 지정 사용자 태그별로 정렬 및 필터링하여 위협 범위를 빠르게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-245">You can now sort and filter by either system or custom user tags, to quickly grasp the scope of threats.</span></span> <span data-ttu-id="dd9eb-246">자세한 [내용은 사용자 태그를](user-tags.md) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-246">See [User tags](user-tags.md) to learn more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd9eb-247">사용자 태그별 필터링 및 정렬은 현재 공개 미리 보기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-247">Filtering and sorting by user tags is currently in public preview.</span></span>
> <span data-ttu-id="dd9eb-248">상업적으로 출시되기 전에 상당수 수정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-248">It may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dd9eb-249">Microsoft는 해당 정보에 대해 제공된 정보에 대해 표현적 또는 암시적 보증을하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-249">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

![탐색기에서 태그 열](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a><span data-ttu-id="dd9eb-251">개선된 시간제</span><span class="sxs-lookup"><span data-stu-id="dd9eb-251">Timezone improvements</span></span>

<span data-ttu-id="dd9eb-252">내보낼 데이터뿐만 아니라 포털 내의 전자 메일 레코드에 대한 타임존도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-252">You will see the timezone for the email records within the Portal, as well as for Exported data.</span></span> <span data-ttu-id="dd9eb-253">전자 메일 그리드, 세부 정보 플라이아웃, 전자 메일 타임라인 및 유사한 전자 메일과 같은 환경 전반에 걸쳐 표시되어 결과 집합의 시간대가 사용자에게 명확해집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-253">The timezone will be visible across experiences like Email Grid, Details Flyout, Email Timeline, and Similar Emails, so that the timezone for the result set is clear to the user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-254">![탐색기에서 Timezone 보기](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-254">![View Timezone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="dd9eb-255">새로 고침 프로세스에서 업데이트</span><span class="sxs-lookup"><span data-stu-id="dd9eb-255">Update in the Refresh process</span></span>

<span data-ttu-id="dd9eb-256">자동 새로 고침(예: 날짜를 변경하는 즉시 페이지가 새로 고쳐지기) 및 수동 새로 고침(다른 필터의 경우)과 혼동에 대한 피드백을 들어보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-256">We have heard feedback around confusion with automatic refresh (e.g. for date, as soon as you change the date, the page would refresh) and manual refresh (for other filters).</span></span> <span data-ttu-id="dd9eb-257">마찬가지로 필터를 제거하면 자동 새로 고침이 발생하여 쿼리를 수정하는 동안 다른 필터를 변경하면 검색 환경이 불일치할 수 있는 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-257">Similarly, removing filters leads to automatic refresh, this causes situations where changing the different filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="dd9eb-258">이를 해결하기 위해 수동 필터링 메커니즘으로 이동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-258">To solve this, we are moving to a manual filtering mechanism.</span></span>

<span data-ttu-id="dd9eb-259">환경 관점에서 사용자는 다양한 필터 범위(필터 집합 및 날짜)를 적용 및 제거하고 새로 고침 단추를 눌러 쿼리 정의가 완료되면 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-259">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set, and date), and press the refresh button to filter the results once they are done with defining the query.</span></span> <span data-ttu-id="dd9eb-260">화면에서 새로 고침 단추를 명확하게 호출하기 위해 새로 고침 단추도 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-260">The refresh button has also been updated to call it out clearly on the screen.</span></span> <span data-ttu-id="dd9eb-261">또한 이 변경에 대한 도구 설명 및 제품 내 설명서도 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-261">We have also updated tooltips and in-product documentation around this change.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-262">![새로 고침을 클릭하여 결과 필터링](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-262">![Click on Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="dd9eb-263">필터에 추가할 차트 드릴다운</span><span class="sxs-lookup"><span data-stu-id="dd9eb-263">Chart drilldown to add to filters</span></span>

<span data-ttu-id="dd9eb-264">이제 차트 범례 값을 클릭하여 해당 값을 필터로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-264">You will now be able to click on the chart legend values to add that value as a filter.</span></span> <span data-ttu-id="dd9eb-265">위에서 설명한 변경의 일부로 결과를 필터링하려면 새로 고침 단추를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-265">Note that you will still have to click on the refresh button to filter the results as part of the change described above.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-266">![차트를 통해 필터링할 드릴다운](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-266">![Drilldown through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="dd9eb-267">제품 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="dd9eb-267">In product information updates</span></span>

<span data-ttu-id="dd9eb-268">제품 내에 추가 세부 정보도 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-268">You should also see additional details within the product.</span></span> <span data-ttu-id="dd9eb-269">예를 들어 필터, 검색 환경 및 결과 집합에 대한 자세한 정보를 제공하려면 표 내의 총 검색 결과 수(아래 참조) 및 레이블, 오류 메시지 및 도구 설명에 대한 개선된 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-269">For example, the total number of search results within grid (see below), as well as improvements around labels, error messages and tooltips, to give more information around filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-270">![제품 내 정보 보기](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-270">![View In-product Info](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="dd9eb-271">위협 탐색기에서 확장된 기능</span><span class="sxs-lookup"><span data-stu-id="dd9eb-271">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="dd9eb-272">상위 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="dd9eb-272">Top targeted users</span></span>

<span data-ttu-id="dd9eb-273">오늘은 전자 메일용 맬웨어 보기(상위 맬웨어 패밀리 섹션 내에서)의 상위 대상 사용자 목록을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-273">Today we expose the list of the top targeted users in the Malware View for Emails (within the Top Malware Families section).</span></span> <span data-ttu-id="dd9eb-274">피싱 및 모든 전자 메일 보기 내에서 이 보기를 확장합니다. 여기서 상위 5개의 대상 사용자를 해당 보기에 대한 각 사용자에 대한 시도 횟수와 함께 볼 수 있습니다(예: 피싱 보기의 경우 피싱 시도 횟수를 볼 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="dd9eb-274">We will be extending this view within Phish and All Email views as well, where you will be able to see the top five targeted users along with the number of attempts for each user for the corresponding view (for example, for Phish view you will be able to see the number of Phish attempts).</span></span>
<span data-ttu-id="dd9eb-275">또한 각 전자 메일 보기에 대한 오프라인 분석 시도 횟수와 함께 대상 사용자 목록을 최대 3000개까지 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-275">You will also be able to export the list of targeted users up to a limit of 3000 along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="dd9eb-276">이 외에도 아니요를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-276">In addition to that, selecting No.</span></span> <span data-ttu-id="dd9eb-277">시도의 수(예: 아래 13회 시도)는 위협 탐색기에서 필터링된 보기를 열기 때문에 해당 사용자의 전자 메일 및 위협에 대한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-277">of attempts (for example, 13 attempts below) would open a filtered view in Threat Explorer, so that you can look at more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-278">![상위 대상 사용자](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-278">![Top Targeted Users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="dd9eb-279">Exchange 전송 규칙</span><span class="sxs-lookup"><span data-stu-id="dd9eb-279">Exchange transport rules</span></span>

<span data-ttu-id="dd9eb-280">데이터 강화의 일부로 메시지에 적용된 다양한 전송 규칙도 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-280">As part of data enrichment, you should also be able to see all the different transport rules which were applied to a message.</span></span> <span data-ttu-id="dd9eb-281">이 정보는 전자 메일의 세부 정보 플라이아웃뿐만 아니라 전자 메일 그리드 보기(표에서 열 옵션을 선택하고 그리드의 열 옵션에서 Exchange 전송 규칙 추가)에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-281">This information will be present within the Email grid view (to view this, select Column options in the grid and add Exchange Transport Rule from the Column options in the grid) as well as Details flyout in the email.</span></span>
<span data-ttu-id="dd9eb-282">메시지에 적용된 전송 규칙의 이름과 GUID를 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-282">You would be able to see both the GUID as well as the name of the transport rules which were applied to the message.</span></span> <span data-ttu-id="dd9eb-283">또한 전송 규칙의 이름을 사용하여 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-283">Additionally, you would be able to search for the messages using the name of the transport rule.</span></span> <span data-ttu-id="dd9eb-284">This would be a 'Contains' search which will be able to search using partial searches as well.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-284">This would be a 'Contains' search which means you will be able to search using partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="dd9eb-285">중요 참고 사항:</span><span class="sxs-lookup"><span data-stu-id="dd9eb-285">Important Note:</span></span>

<span data-ttu-id="dd9eb-286">ETR 검색 및 이름 사용 가능 여부는 사용자에게 할당된 특정 역할에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-286">ETR search and name availability would depend on the specific role that has been assigned to you.</span></span> <span data-ttu-id="dd9eb-287">ETR 이름을 보고 검색하려면 다음 역할/권한 중 하나를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-287">You will need to have one of the following roles/permissions in order to view the ETR names and search.</span></span>  <span data-ttu-id="dd9eb-288">다음 역할이 할당되지 않은 경우 전송 규칙의 이름을 보고 ETR 이름을 사용하여 메시지를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-288">If you do not have any of the following roles assigned to you, you will not be able to see the names of the transport rules, and search for the messages using the ETR names.</span></span> <span data-ttu-id="dd9eb-289">그러나 전자 메일 세부 정보 내에서 ETR 레이블 및 GUID 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-289">However, you will be able to see the ETR label and GUID information within the Email Details.</span></span> <span data-ttu-id="dd9eb-290">전자 메일 그리드, 전자 메일 플라이아웃, 필터 및 내보내기에서 레코드를 보는 다른 환경은 영향을 겪지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-290">Your other experiences around viewing records in Email Grids, Email flyouts, Filters, and Export are not impacted.</span></span>

- <span data-ttu-id="dd9eb-291">EXO 전용 - 데이터 손실 방지: 모두</span><span class="sxs-lookup"><span data-stu-id="dd9eb-291">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="dd9eb-292">EXO 전용 - O365SupportViewConfig: 모두</span><span class="sxs-lookup"><span data-stu-id="dd9eb-292">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="dd9eb-293">AAD 또는 EXO - 보안 관리자: 모두</span><span class="sxs-lookup"><span data-stu-id="dd9eb-293">AAD or EXO - Security Admin: All</span></span>
- <span data-ttu-id="dd9eb-294">AAD 또는 EXO - 보안 판독기: 모두</span><span class="sxs-lookup"><span data-stu-id="dd9eb-294">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="dd9eb-295">EXO 전용 - 전송 규칙: 모두</span><span class="sxs-lookup"><span data-stu-id="dd9eb-295">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="dd9eb-296">EXO 전용 - View-Only 구성: 모두</span><span class="sxs-lookup"><span data-stu-id="dd9eb-296">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="dd9eb-297">전자 메일 그리드, 세부 정보 플라이아웃 및 내보낼 CSV 내에서 ETRS는 아래와 같이 이름/GUID와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-297">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-298">![Exchange 전송 규칙](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-298">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="dd9eb-299">인바운드 커넥터</span><span class="sxs-lookup"><span data-stu-id="dd9eb-299">Inbound connectors</span></span>

<span data-ttu-id="dd9eb-300">커넥터는 보안 제한 또는 제어를 적용할 수 있는 기능을 사용하여 Microsoft 365 또는 Office 365 조직에서 전자 메일이 흐르는 방법을 사용자 지정하는 지침 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-300">Connectors are a collection of instructions that customize the way your email flows to and from your Microsoft 365 or Office 365 organization, with the ability to apply any security restriction or controls.</span></span> <span data-ttu-id="dd9eb-301">위협 탐색기 내에서 이제 전자 메일과 관련된 커넥터를 보고 커넥터 이름을 사용하여 전자 메일을 검색하는 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-301">Within Threat Explorer, you will now have the ability to view the connectors which are related to an email as well as search for emails using the connector names.</span></span>
<span data-ttu-id="dd9eb-302">커넥터 검색은 본질적으로 '포함'으로, 부분 키워드 검색도 작동해야 한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-302">The search for connectors is 'Contains' in nature which means partial keyword searches should work as well.</span></span>
<span data-ttu-id="dd9eb-303">기본 그리드 보기, 세부 정보 플라이아웃 및 내보낼 CSV 내에서 커넥터는 아래와 같이 이름/GUID 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-303">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown below:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-304">![커넥터 세부 정보](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-304">![Connector Details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dd9eb-305">위협 탐색기 및 실시간 검색의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="dd9eb-305">New features in Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="dd9eb-306">위협 탐색기 및 실시간 검색에 추가된 세 가지 새로운 기능:</span><span class="sxs-lookup"><span data-stu-id="dd9eb-306">Three new features added into Threat Explorer and Real-time detections:</span></span>

- [<span data-ttu-id="dd9eb-307">전자 메일 헤더 미리 보기 및 전자 메일 본문 다운로드</span><span class="sxs-lookup"><span data-stu-id="dd9eb-307">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="dd9eb-308">전자 메일 타임라인</span><span class="sxs-lookup"><span data-stu-id="dd9eb-308">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="dd9eb-309">URL 클릭 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="dd9eb-309">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="dd9eb-310">이러한 새로운 기능은 아래에서 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-310">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="dd9eb-311">전자 메일 헤더 미리 보기 및 전자 메일 본문 다운로드</span><span class="sxs-lookup"><span data-stu-id="dd9eb-311">Preview email header and download email body</span></span>

<span data-ttu-id="dd9eb-312">전자 메일 헤더를 미리 보고 전자 메일 본문을 다운로드하는 기능은 위협 탐색기에서 사용할 수 있는 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-312">The ability to preview an email header and download the email body are new features available in Threat Explorer.</span></span> <span data-ttu-id="dd9eb-313">관리자는 다운로드한 헤더/전자 메일 메시지에서 위협을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-313">Admins will be able to analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="dd9eb-314">전자 메일 메시지를 다운로드하면 정보가 노출될 위험이 있기 때문에 이 프로세스는 RBAC(역할 기반 액세스 제어)에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-314">Because downloading email messages can risk the exposure of information, this process is controlled by roles-based access control (RBAC).</span></span> <span data-ttu-id="dd9eb-315">모든 전자 메일 메시지 보기에서 메일 및 미리 보기 헤더를 다운로드할 수 있는 기능을 부여하려면 새 역할 미리 보기를 보안 작업 또는 보안 관리자와 같은 다른 역할 그룹에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-315">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="dd9eb-316">그러나 탐색기(및 실시간 검색)는 전자 메일 메시지가 시작되는 위치를 보다 완전한 그림으로 표시하도록 설계된 새로운 필드도 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-316">But Explorer (and Real-time detections) also adds fresh new fields designed to give you a more complete picture of where your email messages land.</span></span> <span data-ttu-id="dd9eb-317">이러한 변경의 목표는 보안 Ops 사용자에 대한 헌팅을 보다 쉽게 만드는 것이지만, 결과적으로 문제 전자 메일 메시지의 위치를 한 눈에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-317">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="dd9eb-318">어떻게 하면 하나요?</span><span class="sxs-lookup"><span data-stu-id="dd9eb-318">How is this done?</span></span> <span data-ttu-id="dd9eb-319">배달 상태가 이제 두 개의 열로 나어집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-319">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="dd9eb-320">**배달 작업** - 이 전자 메일의 상태는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="dd9eb-320">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="dd9eb-321">**배달 위치** - 이 전자 메일이 어디에서 라우팅된 결과인가요?</span><span class="sxs-lookup"><span data-stu-id="dd9eb-321">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="dd9eb-322">배달 작업은 기존 정책 또는 검색으로 인해 전자 메일에서 수행된 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-322">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="dd9eb-323">전자 메일이 수행할 수 있는 가능한 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-323">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="dd9eb-324">배달</span><span class="sxs-lookup"><span data-stu-id="dd9eb-324">Delivered</span></span>|<span data-ttu-id="dd9eb-325">정크</span><span class="sxs-lookup"><span data-stu-id="dd9eb-325">Junked</span></span>|<span data-ttu-id="dd9eb-326">차단됨</span><span class="sxs-lookup"><span data-stu-id="dd9eb-326">Blocked</span></span>|<span data-ttu-id="dd9eb-327">바꾸기</span><span class="sxs-lookup"><span data-stu-id="dd9eb-327">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="dd9eb-328">전자 메일이 사용자의 받은 편지함 또는 폴더로 배달된 경우 사용자가 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-328">Email was delivered to Inbox or folder of a user and the user can directly access it.</span></span>|<span data-ttu-id="dd9eb-329">전자 메일이 사용자의 정크 폴더 또는 삭제된 폴더로 전송된 경우 사용자는 해당 폴더의 전자 메일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-329">Email was sent to either user's Junk folder or Deleted folder, and the user has access to emails in those folders.</span></span>|<span data-ttu-id="dd9eb-330">중단되거나 실패했거나 삭제된 모든 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-330">Any emails that are quarantined, that  failed, or were dropped.</span></span> <span data-ttu-id="dd9eb-331">이 설정은 사용자가 완전히 사용할 수 없습니다!</span><span class="sxs-lookup"><span data-stu-id="dd9eb-331">This is completely inaccessible by the user!</span></span>|<span data-ttu-id="dd9eb-332">악의적인 첨부 파일이 첨부 파일이 악성 상태인 .txt 파일로 대체되는 모든 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-332">Any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>|

|<span data-ttu-id="dd9eb-333">배달</span><span class="sxs-lookup"><span data-stu-id="dd9eb-333">Delivered</span></span>|<span data-ttu-id="dd9eb-334">정크</span><span class="sxs-lookup"><span data-stu-id="dd9eb-334">Junked</span></span>|<span data-ttu-id="dd9eb-335">차단됨</span><span class="sxs-lookup"><span data-stu-id="dd9eb-335">Blocked</span></span>|<span data-ttu-id="dd9eb-336">바꾸기</span><span class="sxs-lookup"><span data-stu-id="dd9eb-336">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="dd9eb-337">전자 메일이 사용자의 받은 편지함이나 다른 폴더로 배달된 경우 사용자가 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-337">Email was delivered to the user's inbox or another folder, and the user can directly access it.</span></span>|<span data-ttu-id="dd9eb-338">전자 메일이 사용자의 정크 폴더 또는 삭제된 폴더로 전송된 경우 사용자는 해당 폴더의 전자 메일 메시지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-338">Email was sent to either user's Junk folder or Deleted folder, and the user has access to email messages in those folders.</span></span>|<span data-ttu-id="dd9eb-339">사용자가 액세스할 수 없는, 실패했거나 삭제된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-339">Any email messages that are quarantined, that failed, or were dropped, and are not accessible by the user.</span></span>|<span data-ttu-id="dd9eb-340">악의적인 첨부 파일이 첨부 파일이 악성 상태인 .txt 파일로 대체된 모든 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-340">Any email messages where malicious attachments were replaced by .txt files that state the attachments were malicious.</span></span>|
|

<span data-ttu-id="dd9eb-341">사용자가 볼 수 있는 것은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-341">And here is what the user can see, and what they can't:</span></span>

|<span data-ttu-id="dd9eb-342">최종 사용자가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-342">Accessible to end users</span></span>|<span data-ttu-id="dd9eb-343">최종 사용자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-343">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="dd9eb-344">배달</span><span class="sxs-lookup"><span data-stu-id="dd9eb-344">Delivered</span></span>|<span data-ttu-id="dd9eb-345">차단됨</span><span class="sxs-lookup"><span data-stu-id="dd9eb-345">Blocked</span></span>|
|<span data-ttu-id="dd9eb-346">정크</span><span class="sxs-lookup"><span data-stu-id="dd9eb-346">Junked</span></span>|<span data-ttu-id="dd9eb-347">바꾸기</span><span class="sxs-lookup"><span data-stu-id="dd9eb-347">Replaced</span></span>|

<span data-ttu-id="dd9eb-348">배달 위치는 배달 후 실행된 정책 및 검색의 결과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-348">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="dd9eb-349">배달 동작에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-349">It's linked to a Delivery Action.</span></span> <span data-ttu-id="dd9eb-350">이 필드는 문제가 메일이 발견될 때 수행된 작업을 파악하기 위해 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-350">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="dd9eb-351">배달 위치의 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-351">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="dd9eb-352">**받은 편지함 또는 폴더:** 전자 메일이 받은 편지함 또는 폴더입니다(전자 메일 규칙에 따라).</span><span class="sxs-lookup"><span data-stu-id="dd9eb-352">**Inbox or folder**: The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="dd9eb-353">**On-prem or external**: the mailbox doesn't exist on cloud but is on-premises.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-353">**On-prem or external**: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="dd9eb-354">**정크 폴더:** 전자 메일이 사용자의 정크 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-354">**Junk folder**: The email is in the Junk folder of a user.</span></span>
- <span data-ttu-id="dd9eb-355">**지우기 항목 폴더:** 사용자의 지우기 항목 폴더에 있는 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-355">**Deleted items folder**: The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="dd9eb-356">**Quarantine:** The email in quarantine, and is not in a user's mailbox.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-356">**Quarantine**: The email in quarantine, and is not in a user's mailbox.</span></span>
- <span data-ttu-id="dd9eb-357">**실패:** 전자 메일이 사서함에 도달하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-357">**Failed**: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="dd9eb-358">**삭제:** 메일 흐름에서 전자 메일이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-358">**Dropped**: The email gets lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="dd9eb-359">전자 메일 타임라인</span><span class="sxs-lookup"><span data-stu-id="dd9eb-359">Email timeline</span></span>

<span data-ttu-id="dd9eb-360">전자 **메일 타임라인은** 관리자에게 더 나은 헌팅 환경을 만들기 위한 또 다른 새로운 탐색기 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-360">The **Email Timeline** is another new Explorer feature aimed at making the hunting experience better for admins.</span></span> <span data-ttu-id="dd9eb-361">다양한 위치를 확인하여 이벤트를 파악하는 데 소요되는 시간이 적기 때문에 임의 지정이 끊어지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-361">It cuts down on randomization because there is less time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="dd9eb-362">전자 메일에서 동시에 여러 이벤트가 발생하거나 닫히면 타임라인 보기에 해당 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-362">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="dd9eb-363">실제로 메일 배달 후 발생 하는 일부 이벤트는 '특수 작업' 열에 캡처 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-363">In fact, some events that happen post-delivery to your mail will be captured in the 'Special action' column.</span></span> <span data-ttu-id="dd9eb-364">해당 메일 타임라인의 정보를 메일 사후 배달에 대해 수행한 특수한 작업과 결합하면 관리자가 정책 작동 방식, 메일이 마지막으로 라우팅된 위치 및 경우에 따라 최종 평가가 수행된 방식에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-364">Combining the information from the timeline of that mail with the special action taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="dd9eb-365">악의적인 전자 메일 메시지 조사에 대한 자세한 내용은 [Office 365에서](investigate-malicious-email-that-was-delivered.md)배달된 악성 전자 메일 조사 및 수정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-365">For more discussion about investigating malicious email messages, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="dd9eb-366">URL 클릭 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="dd9eb-366">Export URL click data</span></span>

<span data-ttu-id="dd9eb-367">또한 이제 URL 클릭에 대한 보고서를 Microsoft Excel로 내보낼 수 있습니다. 그러면 네트워크 메시지 ID와 해당 클릭 결과 모두를 볼 수 있어 URL 클릭 트래픽이 시작된 위치를 보다 쉽게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-367">Also, you will now be able to export reports for URL clicks to Microsoft Excel in order to view both their Network Message ID, and their Click Verdict, making the task of understanding where your URL click traffic originated easier.</span></span> <span data-ttu-id="dd9eb-368">작동 방식은 다음과 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-368">Here's how it works.</span></span> <span data-ttu-id="dd9eb-369">Office 365 빠른 실행의 위협 관리부터 다음 체인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-369">Starting in Threat Management on the Office 365 quick-launch, click through this chain:</span></span>

<span data-ttu-id="dd9eb-370">**탐색기** \> **피싱 보기** \> **클릭 수** \> **상위 URL 또는 URL 상위 클릭 수** \> **아무 레코드나 클릭하여 URL 플라이아웃 열기**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-370">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs or URL Top Clicks** \> **Click on any record to open URL flyout**</span></span>

<span data-ttu-id="dd9eb-371">목록에서 URL을 클릭하면 플라이아웃 패널에 새 내보내기 단추가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-371">When you click on a URL in the list, you'll see a new Export button on the fly-out panel.</span></span> <span data-ttu-id="dd9eb-372">이 단추를 사용하여 데이터를 Excel 스프레드시트로 이동하여 보다 쉽게 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-372">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="dd9eb-373">실시간 검색 보고서에서 동일한 위치에 다음과 같이 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-373">You can get to the same location in the Real-time detections report as follows:</span></span>

<span data-ttu-id="dd9eb-374">**탐색기** \> **실시간 검색** \> **피싱 보기** \> **URL** \> **상위 URL 또는 위쪽 클릭 수** \> **아무 레코드나 클릭하여 URL 플라이아웃 열기** \> **클릭 탭으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-374">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs or Top Clicks** \> **Click on any record to open URL flyout** \> **Navigate to the Clicks Tab.**</span></span>

> [!TIP]
> <span data-ttu-id="dd9eb-375">네트워크 메시지 ID는 탐색기 또는 네트워크 메시지 ID를 통해 관련 타사 도구를 검색할 때 클릭을 특정 메일에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-375">Network Message ID maps the click back to specific mails when you search through Explorer or associated third-party tools via Network Message ID.</span></span> <span data-ttu-id="dd9eb-376">네트워크 메시지 ID를 검색하면 관리자에게 클릭 결과와 관련된 특정 전자 메일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-376">Searching through the Network Message ID will give admins the specific email associated with a click result.</span></span> <span data-ttu-id="dd9eb-377">내보내기 시 네트워크 메시지 ID의 상호 관련 ID를 사용하면 보다 빠르고 강력한 분석이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-377">On export, having the correlating identification of Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd9eb-378">![탐색기에서 클릭 탭](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-378">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="dd9eb-379">기술로 전자 메일에서 검색된 맬웨어 확인</span><span class="sxs-lookup"><span data-stu-id="dd9eb-379">See malware detected in email by technology</span></span>

<span data-ttu-id="dd9eb-380">Microsoft 365 기술로 전자 메일에서 검색된 맬웨어를 확인하려는 경우를 가정해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-380">Suppose you want to see malware detected in email, by Microsoft 365 technology.</span></span> <span data-ttu-id="dd9eb-381">이렇게하려면 전자 메일 [탐색기](threat-explorer-views.md#email--malware) > 맬웨어 보기(또는 실시간 검색)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-381">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="dd9eb-382">보안 & 준수 센터()에서 위협 관리 탐색기(또는 실시간 검색)를 <https://protection.office.com>  \>  **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-382">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="dd9eb-383">(이 예제에서는 Explorer를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-383">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="dd9eb-384">보기 **메뉴에서** 전자  메일 맬웨어를 \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-384">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd9eb-385">![탐색기 보기 메뉴](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-385">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="dd9eb-386">보낸 **사람 클릭한** 다음 기본 검색 **기술을** \> **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-386">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="dd9eb-387">이제 검색 기술을 보고서의 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-387">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd9eb-388">![맬웨어 감지 기술](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-388">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="dd9eb-389">옵션을 선택한 다음 새로  고침 단추를 클릭하여 해당 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-389">Select an option, and then click the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd9eb-390">![선택한 검색 기술](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-390">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="dd9eb-391">보고서가 새로 고쳐서 선택한 기술 옵션을 사용하여 전자 메일에서 맬웨어가 검색된 결과를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-391">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="dd9eb-392">여기에서 추가 분석을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-392">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="dd9eb-393">피싱 URL에 대한 데이터 보기 및 판정 클릭</span><span class="sxs-lookup"><span data-stu-id="dd9eb-393">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="dd9eb-394">허용, 차단 및 재지정된 URL 목록을 포함하여 전자 메일의 URL을 통해 피싱 시도를 확인하려는 경우를 가정해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-394">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="dd9eb-395">클릭한 URL을 식별하려면 안전한 링크를 [구성해야](atp-safe-links.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-395">Identifying URLs that were clicked requires [Safe Links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="dd9eb-396">클릭 시간 보호 및 [](set-up-atp-safe-links-policies.md) 안전한 링크로 클릭 판정 로깅에 대해 안전한 링크 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-396">Make sure that you have set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="dd9eb-397">메시지의 피싱 URL을 검토하고 피싱 메시지의 URL을 클릭하려면 전자 [](threat-explorer-views.md#email--phish) 메일 > 탐색기 보기(또는 실시간 검색)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-397">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="dd9eb-398">보안 & 준수 센터()에서 위협 관리 탐색기(또는 실시간 검색)를 <https://protection.office.com>  \>  **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-398">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="dd9eb-399">(이 예제에서는 Explorer를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-399">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="dd9eb-400">보기 **메뉴에서** **전자** 메일 \> **피싱을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-400">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd9eb-401">![피싱 컨텍스트에서 탐색기 메뉴 보기](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-401">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="dd9eb-402">보낸 **사람 클릭한** 다음 **URL** 클릭 \> **verdict를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-402">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="dd9eb-403">차단 및 다시 설정 차단과 같은 하나 이상의 옵션을 선택한  다음 해당 필터를 적용하는 옵션과 같은 줄에 있는 새로 고침 단추를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="dd9eb-403">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="dd9eb-404">(브라우저 창을 새로 고치지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-404">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd9eb-405">![URL 및 클릭 판정](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-405">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="dd9eb-406">보고서가 새로 고쳐지며 보고서 아래에 있는 URL 탭에 두 개의 서로 다른 URL 테이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-406">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="dd9eb-407">**상위 URL은** 필터링한 메시지에 포함된 URL과 각 URL에 대한 전자 메일 배달 작업 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-407">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="dd9eb-408">피싱 전자 메일 보기에서 이 목록에는 일반적으로 합법적인 URL이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-408">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="dd9eb-409">공격자는 메시지에 좋은 URL과 잘못된 URL을 혼합하여 배달하려고 시도하지만 악의적인 링크를 클릭하면 더 흥미로우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-409">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="dd9eb-410">URL 표는 총 전자 메일 수에 따라 정렬됩니다(보기를 단순화하기 위해 이 열은 숨겨져 있습니다).</span><span class="sxs-lookup"><span data-stu-id="dd9eb-410">The table of URLs is sorted by total email count (but note that this column is hidden to simplify the view).</span></span>

   - <span data-ttu-id="dd9eb-411">**위쪽 클릭은** 클릭한 안전한 링크 래핑 URL로, 총 클릭 횟수별로 정렬됩니다(이 열은 보기를 단순화하기 위해 표시되지도 않습니다).</span><span class="sxs-lookup"><span data-stu-id="dd9eb-411">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="dd9eb-412">열별로 총 개수는 클릭한 각 URL에 대한 안전한 링크 클릭 결과 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-412">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="dd9eb-413">피싱 전자 메일 보기에서 이러한 URL은 더 자주 의심스러우거나 악의적인 URL이지만 위협이 아닌 피싱 메시지에 있는 URL을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-413">In the phish email view, these are more often suspicious or malicious URLs, but could include URLs that are not threats but are in phish messages.</span></span> <span data-ttu-id="dd9eb-414">래핑되지 않은 링크의 URL 클릭은 여기에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-414">URL clicks on unwrapped links will not show up here.</span></span>

   <span data-ttu-id="dd9eb-415">두 URL 테이블은 배달 작업 및 위치를 통해 피싱 전자 메일 메시지의 상위 URL을 표시하며, 차단된(또는 경고에도 불구하고 방문한) URL 클릭을 표시하여 사용자가 수신하고 사용자와 상호 작용하는 잠재적인 잘못된 링크를 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-415">The two URL tables show top URLs in phishing email messages by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="dd9eb-416">여기에서 추가 분석을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-416">From here, you can conduct further analysis.</span></span> <span data-ttu-id="dd9eb-417">예를 들어 차트 아래에서 조직의 환경에서 차단된 전자 메일 메시지의 상위 URL을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-417">For example, below the chart, you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd9eb-418">![차단된 탐색기 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-418">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="dd9eb-419">URL을 선택하여 자세한 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-419">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dd9eb-420">URL 플라이아웃 대화 상자에서 환경의 URL 노출에 대한 전체 보기를 표시하기 위해 전자 메일 메시지에 대한 필터링이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-420">In the URL flyout dialog, the filtering on email messages is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="dd9eb-421">이렇게 하면 탐색기에서 전자 메일 메시지를 우려하는 메시지로 필터링하고 잠재적 위협이 될 수 있는 특정 URL을 찾은 다음 탐색기 보기 자체에 URL 필터를 추가하지 않고도 URL 세부 정보 대화 상자를 통해 환경의 URL 노출에 대한 이해를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-421">This lets you filter down email messages in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-different-click-verdicts"></a><span data-ttu-id="dd9eb-422">다른 클릭 판정 해석</span><span class="sxs-lookup"><span data-stu-id="dd9eb-422">Interpretation of different click verdicts</span></span>

<span data-ttu-id="dd9eb-423">전자 메일 또는 URL 플라이아웃, Top Clicks 및 필터링 환경 내에서 다양한 클릭 값이 헌팅 환경의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-423">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you will see different click values as part of your hunting experience.</span></span> <span data-ttu-id="dd9eb-424">다음은 클릭 판정 및 해당 해석의 가능한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-424">Below are the possible values of Click Verdicts and their interpretation:</span></span>

- <span data-ttu-id="dd9eb-425">**없음**: URL에 대한 판정을 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-425">**None**: We were unable to capture the verdict for the URL.</span></span> <span data-ttu-id="dd9eb-426">사용자가 URL을 클릭한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-426">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="dd9eb-427">**허용:** 사용자가 URL로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-427">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="dd9eb-428">**차단:** 사용자가 URL로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-428">**Blocked**: The User was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="dd9eb-429">**보류 중인 판정:** 사용자에게 데토네이트 보류 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-429">**Pending verdict**: The user was presented with the detonation pending page.</span></span>
- <span data-ttu-id="dd9eb-430">**차단된 은(는)**: 사용자가 URL로 이동하지 않습니다. 그러나 사용자는 URL로 이동하기 위해 차단을 오버라이드합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-430">**Blocked overridden**: The user was blocked from navigating to the URL; however, the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="dd9eb-431">**보류 중인 판정 우회:** 사용자에게 데토네이트 페이지가 표시 그러나 사용자가 URL로 이동하기 위해 페이지를 오버라이드합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-431">**Pending verdict bypassed**: The user was presented with the detonation page; however, the user overrode the page to navigate to the URL.</span></span>
- <span data-ttu-id="dd9eb-432">**오류:** 사용자에게 오류 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-432">**Error**: The user was presented with the error page.</span></span> <span data-ttu-id="dd9eb-433">이는 또한 판정을 캡처하는 동안 오류가 발생했다는 의미일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-433">This can also mean there was an error in capturing the verdict.</span></span>
- <span data-ttu-id="dd9eb-434">**실패:** 판정을 캡처하는 동안 알 수 없는 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-434">**Failure**: There was unknown exception while capturing the verdict.</span></span> <span data-ttu-id="dd9eb-435">사용자가 URL을 클릭한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-435">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="dd9eb-436">사용자가 보고한 전자 메일 메시지 검토</span><span class="sxs-lookup"><span data-stu-id="dd9eb-436">Review email messages reported by users</span></span>

<span data-ttu-id="dd9eb-437">조직의 사용자가 웹용 Outlook 및 Outlook용 보고서 메시지 추가 기능을 사용하여 정크 메일, 정크 메일 아님 또는 피싱으로 보고한 전자 메일 메시지를 확인하려는 경우를 가정해 [봐야 합니다.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-437">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="dd9eb-438">이렇게하려면 전자 메일 [](threat-explorer-views.md#email--submissions) > 제출 보기(또는 실시간 검색)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-438">To do this, use the [Email > Submissions](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="dd9eb-439">보안 & 준수 센터()에서 위협 관리 탐색기(또는 실시간 검색)를 <https://protection.office.com>  \>  **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-439">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="dd9eb-440">(이 예제에서는 Explorer를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-440">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="dd9eb-441">보기 **메뉴에서** 전자 메일  \> **제출을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-441">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd9eb-442">![전자 메일용 탐색기 메뉴 보기](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-442">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="dd9eb-443">보낸 **사람 클릭한** 다음 기본 보고서 **유형을** \> **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-443">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="dd9eb-444">피싱과 같은 옵션을 선택하고 새로 **고침 단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-444">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd9eb-445">![사용자가 보고한 피싱](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-445">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="dd9eb-446">조직의 사용자들이 피싱 시도로 보고한 전자 메일 메시지에 대한 데이터를 표시하기 위해 보고서가 새로 고쳐서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-446">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="dd9eb-447">이 정보를 사용하여 추가 분석을 수행하고 필요한 경우 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-447">You can use this information to conduct further analysis, and if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="dd9eb-448">자동화된 조사 및 대응 시작</span><span class="sxs-lookup"><span data-stu-id="dd9eb-448">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="dd9eb-449">자동화된 조사 및 응답 기능은 **Office 365 계획 2 및 Office 365 E5용 Microsoft Defender에서** 사용할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-449">Automated investigation and response capabilities are available in **Microsoft Defender for Office 365 Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="dd9eb-450">(신규!) [자동화된 조사 및 대응을](automated-investigation-response-office.md) 통해 보안 운영 팀이 사이버 공격을 조사하고 완화하는 데 많은 시간과 노력을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-450">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="dd9eb-451">보안 플레이북을 트리거할 수 있는 경고를 구성하는 것 외에도 탐색기 보기에서 자동화된 조사 및 응답 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-451">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span>

<span data-ttu-id="dd9eb-452">이에 대한 자세한 내용은 예제: 보안 관리자가 [Explorer에서 조사를 트리거합니다.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-452">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="dd9eb-453">탐색기(또는 실시간 검색)를 사용하는 더 많은 방법</span><span class="sxs-lookup"><span data-stu-id="dd9eb-453">More ways to use Explorer (or Real-time detections)</span></span>

<span data-ttu-id="dd9eb-454">이 문서에 설명된 시나리오 외에도 탐색기(또는 실시간 검색)에서 더 많은 보고 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-454">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span>

- [<span data-ttu-id="dd9eb-455">배달된 악성 전자 메일 찾기 및 조사</span><span class="sxs-lookup"><span data-stu-id="dd9eb-455">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="dd9eb-456">SharePoint Online, OneDrive 및 Microsoft Teams에서 검색된 악성 파일 보기</span><span class="sxs-lookup"><span data-stu-id="dd9eb-456">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="dd9eb-457">위협 탐색기(및 실시간 검색)에서 보기에 대한 개요를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-457">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="dd9eb-458">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="dd9eb-458">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="dd9eb-459">Microsoft Threat Protection의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="dd9eb-459">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="dd9eb-460">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="dd9eb-460">Required licenses and permissions</span></span>

<span data-ttu-id="dd9eb-461">탐색기 또는 실시간 검색을 [사용하려면 Office 365용 Microsoft Defender가](office-365-atp.md) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-461">You must have [Microsoft Defender for Office 365](office-365-atp.md) to get Explorer or Real-time detections.</span></span>

- <span data-ttu-id="dd9eb-462">탐색기는 Office 365 계획 2용 Defender에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-462">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="dd9eb-463">실시간 검색 보고서는 Office 365 계획 1용 Defender에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-463">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="dd9eb-464">Office 365용 Defender에서 보호해야 하는 모든 사용자에 대한 라이선스 할당을 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-464">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="dd9eb-465">탐색기 또는 실시간 검색은 사용이 허가된 사용자에 대한 검색 데이터를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-465">(Explorer or Real-time detections shows detection data for licensed users.)</span></span>

<span data-ttu-id="dd9eb-466">탐색기 또는 실시간 검색을 보고 사용하려면 보안 관리자 또는 보안 읽기 권한자에 부여된 권한과 같은 적절한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-466">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="dd9eb-467">보안 및 & 센터의 경우 다음 역할 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-467">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="dd9eb-468">조직 관리</span><span class="sxs-lookup"><span data-stu-id="dd9eb-468">Organization Management</span></span>
  - <span data-ttu-id="dd9eb-469">보안 관리자(Azure Active Directory 관리 센터에서 할당할 수 있습니다. <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="dd9eb-469">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="dd9eb-470">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="dd9eb-470">Security Reader</span></span>

- <span data-ttu-id="dd9eb-471">Exchange Online의 경우 Exchange 관리 센터() 또는 <https://admin.protection.outlook.com/ecp/> [Exchange Online PowerShell에서](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)다음 역할 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-471">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="dd9eb-472">조직 관리</span><span class="sxs-lookup"><span data-stu-id="dd9eb-472">Organization Management</span></span>
  - <span data-ttu-id="dd9eb-473">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="dd9eb-473">View-Only Organization Management</span></span>
  - <span data-ttu-id="dd9eb-474">보기 전용 받는 사람</span><span class="sxs-lookup"><span data-stu-id="dd9eb-474">View-Only Recipients</span></span>
  - <span data-ttu-id="dd9eb-475">준수 관리</span><span class="sxs-lookup"><span data-stu-id="dd9eb-475">Compliance Management</span></span>

<span data-ttu-id="dd9eb-476">역할 및 사용 권한에 대한 자세한 내용은 다음 리소스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-476">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="dd9eb-477">보안 및 준수 센터의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="dd9eb-477">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="dd9eb-478">Exchange Online의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="dd9eb-478">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dd9eb-479">위협 탐색기 및 실시간 검색 간의 몇 가지 차이점</span><span class="sxs-lookup"><span data-stu-id="dd9eb-479">Some differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="dd9eb-480">실시간  검색 보고서는 Office 365 계획 1용 Defender에서 사용할 수 있는 반면 **위협** 탐색기는 Office 365 계획 2용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-480">The **Real-time detections** report is available in Defender for Office 365 Plan 1, whereas **Threat Explorer** is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="dd9eb-481">실시간 **검색 보고서를 사용하면** 검색을 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-481">The **Real-time detections** report allows you to view detections in real-time.</span></span> <span data-ttu-id="dd9eb-482">**위협 탐색기에서도** 이 기능을 하지만 주어진 공격에 대한 추가 세부 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-482">**Threat Explorer** does this as well, but also allows you to view additional details for a given attack.</span></span>
- <span data-ttu-id="dd9eb-483">위협 **탐색기에서** 모든  전자 메일 보기를 사용할 수 있으며 실시간 검색 보고서에는 **없습니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-483">An **All email** view is available in **Threat Explorer** (and is not in the **Real-time detections** report).</span></span>
- <span data-ttu-id="dd9eb-484">위협 탐색기에는 더 많은 필터링 기능과 사용 가능한 **작업이 포함되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="dd9eb-484">More filtering capabilities and available actions are included in **Threat Explorer**.</span></span>

<span data-ttu-id="dd9eb-485">자세한 내용은 Office [365용 Microsoft Defender 서비스 설명: Office 365 계획용 Defender의 기능 가용성을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="dd9eb-485">For more details, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
