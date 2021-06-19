---
title: 위협 탐색기 및 실시간 검색
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 보안 센터의 탐색기 및 실시간 Microsoft 365 사용하여 위협을 효율적으로 조사하고 대응합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a7e3620859dfbc5f3d55501a880cef233e0a0be3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029588"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="77390-103">위협 탐색기 및 실시간 검색</span><span class="sxs-lookup"><span data-stu-id="77390-103">Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="77390-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="77390-104">**Applies to**</span></span>
- [<span data-ttu-id="77390-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="77390-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="77390-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77390-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="77390-107">조직에 Office 365 [Microsoft Defender가](defender-for-office-365.md)있으며 필요한 권한이 [](#required-licenses-and-permissions)있는 경우 **탐색기** 또는 실시간 검색(이전의 실시간  보고서) 중 [](#new-features-in-threat-explorer-and-real-time-detections)하나를 사용할 수 있습니다. 새로운 기능 확인 </span><span class="sxs-lookup"><span data-stu-id="77390-107">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **Real-time detections** (formerly *Real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="77390-108">보안 & 준수 센터에서 위협 관리로 이동한 다음 **탐색기**  또는 실시간 검색 **을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-108">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="77390-109">Microsoft Defender for Office 365 요금제 2를 사용하면 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-109">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="77390-110">Microsoft Defender for Office 365 요금제 1을 사용하면 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-110">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![위협 탐색기](../../media/threatmgmt-explorer.png)|![실시간 탐지](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="77390-113">탐색기 또는 실시간 검색을 통해 보안 운영 팀이 위협을 효율적으로 조사하고 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-113">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="77390-114">보고서는 다음 이미지와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-114">The report resembles the following image:</span></span>

![위협 관리 \> 탐색기로 이동](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="77390-116">이 보고서를 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-116">With this report, you can:</span></span>

- [<span data-ttu-id="77390-117">보안 기능에서 검색된 맬웨어 Microsoft 365 참조</span><span class="sxs-lookup"><span data-stu-id="77390-117">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="77390-118">피싱 URL 보기 및 판정 데이터 클릭</span><span class="sxs-lookup"><span data-stu-id="77390-118">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- <span data-ttu-id="77390-119">[탐색기 보기에서](#start-automated-investigation-and-response) 자동화된 조사 및 응답 프로세스 시작(Office 365 계획 2에만 해당)</span><span class="sxs-lookup"><span data-stu-id="77390-119">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="77390-120">악성 전자 메일 조사 등</span><span class="sxs-lookup"><span data-stu-id="77390-120">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="77390-121">위협 헌팅 환경 개선</span><span class="sxs-lookup"><span data-stu-id="77390-121">Improvements to Threat Hunting Experience</span></span>

### <a name="introduction-of-alert-id-for-mdo-alerts-within-explorerreal-time-detections-preview"></a><span data-ttu-id="77390-122">탐색기/실시간 감지 내 MDO 경고에 대한 경고 ID 소개(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="77390-122">Introduction of Alert ID for MDO alerts within Explorer/Real-time detections (Preview)</span></span>

<span data-ttu-id="77390-123">현재 경고에서 위협 탐색기로 이동하면 탐색기 내에서 필터링된 보기가 열리며 경고 정책 ID로 필터링된 보기가 표시됩니다(경고 정책의 고유 식별자인 정책 ID).</span><span class="sxs-lookup"><span data-stu-id="77390-123">Today, if you navigate from an alert to Threat Explorer, it opens a filtered view within the Explorer, with the view filtered by Alert policy ID (policy ID being a unique identifier for an Alert policy).</span></span>
<span data-ttu-id="77390-124">위협 탐색기 및 실시간 검색에 경고 ID(아래 경고 ID의 예 참조)를 도입하여 특정 경고 및 전자 메일 수와 관련된 메시지를 볼 수 있도록 이러한 통합을 더욱 관련성이 강화하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-124">We are making this integration more relevant by introducing the alert ID (see an example of alert ID below) in Threat Explorer and Real-time detections so that you see messages which are relevant to the specific alert, as well as a count of emails.</span></span> <span data-ttu-id="77390-125">또한 메시지가 경고의 일부이면 해당 메시지에서 특정 경고로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-125">You will also be able to see if a message was part of an alert, as well as navigate from that message to the specific alert.</span></span>

<span data-ttu-id="77390-126">개별 경고를 볼 때 URL 내에서 경고 ID를 사용할 수 있습니다. 의 `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1` 예입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-126">Alert ID is available within the URL when you are viewing an individual alert; an example being `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-127">![경고 ID 필터링](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="77390-127">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-128">![경고 ID 세부 정보 플라이아웃](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="77390-128">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days-preview"></a><span data-ttu-id="77390-129">평가판 테넌트에 대한 탐색기(및 실시간 검색) 데이터 보존 및 검색 제한 확장(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="77390-129">Extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days (Preview)</span></span>

<span data-ttu-id="77390-130">이러한 변경의 일부로, Office P1 및 P2 평가판 테넌트에 대한 위협 탐색기/실시간 검색에서 30일(이전 7일보다 증가)에 걸쳐 전자 메일 데이터를 검색하고 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-130">As part of this change, you will be able to search for, and filter email data across 30 days (an increase from the previous 7 days) in Threat Explorer/Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span>
<span data-ttu-id="77390-131">이는 이미 30일 데이터 보존 및 검색 기능이 있는 P1 및 P2/E5 고객의 프로덕션 테넌트에는 영향을 끼치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-131">This does not impact any production tenants for both P1 and P2/E5 customers, which already has the 30 day data retention and search capabilities.</span></span>

### <a name="updated-limits-for-export-of-records-for-threat-explorer-preview"></a><span data-ttu-id="77390-132">위협 탐색기 레코드 내보내기 제한 업데이트(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="77390-132">Updated limits for Export of records for Threat Explorer (Preview)</span></span>

<span data-ttu-id="77390-133">이 업데이트의 일부로 위협 탐색기에서 내보낼 수 있는 전자 메일 레코드의 행 수가 9990개에서 200,000개 레코드로 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-133">As part of this update, the number of rows for Email records that can be exported from Threat Explorer is increased from 9990 to 200,000 records.</span></span> <span data-ttu-id="77390-134">현재 내보낼 수 있는 열 집합은 동일하게 유지되지만 행 수는 현재 제한에서 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-134">The set of columns that can be exported currently will remain the same, but the number of rows will increase from the current limit.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="77390-135">위협 탐색기에서 태그</span><span class="sxs-lookup"><span data-stu-id="77390-135">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="77390-136">사용자 태그 기능은 *미리* 보기에 있으며, 모든 사용자가 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-136">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="77390-137">릴리스 일정에 대한 자세한 내용은 Microsoft 365 로드맵을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="77390-137">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="77390-138">사용자 태그는 Microsoft Defender에서 특정 사용자 그룹을 식별하여 Office 365.</span><span class="sxs-lookup"><span data-stu-id="77390-138">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="77390-139">라이선스 및 구성을 비롯한 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="77390-139">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="77390-140">위협 탐색기에서 다음 환경의 사용자 태그에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-140">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="77390-141">전자 메일 그리드 보기</span><span class="sxs-lookup"><span data-stu-id="77390-141">Email grid view</span></span>

<span data-ttu-id="77390-142">전자 **메일 그리드의** 태그 열에는 보낸 사람 또는 받는 사람 사서함에 적용된 모든 태그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-142">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="77390-143">기본적으로 우선 순위 계정과 같은 시스템 태그가 먼저 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-143">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-144">![전자 메일 그리드 보기에서 태그 필터링](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="77390-144">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="77390-145">필터링</span><span class="sxs-lookup"><span data-stu-id="77390-145">Filtering</span></span>

<span data-ttu-id="77390-146">태그를 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-146">You can use tags as a filter.</span></span> <span data-ttu-id="77390-147">우선 순위 계정 또는 특정 사용자 태그 시나리오에서 헌트하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-147">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="77390-148">특정 태그가 있는 결과를 제외할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-148">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="77390-149">이 기능을 다른 필터와 결합하여 조사 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-149">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="77390-150">[![필터 태그](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77390-150">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-151">![필터 태그 아미기](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="77390-151">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="77390-152">전자 메일 세부 정보 플라이아웃</span><span class="sxs-lookup"><span data-stu-id="77390-152">Email detail flyout</span></span>

<span data-ttu-id="77390-153">보낸 사람 및 받는 사람에 대한 개별 태그를 확인하려면 제목을 선택하여 메시지 세부 정보 플라이아웃을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-153">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="77390-154">전자 **메일에** 보낸 사람 및 받는 사람 태그가 있는 경우 요약 탭에 별도로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-154">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="77390-155">보낸 사람 및 받는 사람에 대한 개별 태그에 대한 정보도 내보낼 CSV 데이터로 확장되어 두 개의 개별 열에서 이러한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-155">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-156">![전자 메일 세부 정보 태그](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="77390-156">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="77390-157">태그 정보는 URL 클릭 플라이아웃에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-157">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="77390-158">이 보기를 보려면 피싱 또는 모든 전자 메일 보기로 이동한 다음 **URL** 또는 **URL 클릭 탭으로** 이동하세요. 해당 클릭과 연결된 태그를 포함하여 해당 URL의 클릭에 대한 추가 세부 정보를 보려면 개별 URL 플라이아웃을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-158">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="77390-159">업데이트된 시간 표시 막대 보기</span><span class="sxs-lookup"><span data-stu-id="77390-159">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-160">![URL 태그](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="77390-160">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="77390-161">[이 비디오](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)를 시청하여 자세히 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="77390-161">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="77390-162">위협 헌팅 환경 개선(예정)</span><span class="sxs-lookup"><span data-stu-id="77390-162">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="77390-163">전자 메일에 대한 위협 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="77390-163">Updated threat information for emails</span></span>

<span data-ttu-id="77390-164">당사는 전자 메일 레코드에 대한 데이터 정확도 및 일관성을 높이기 위해 플랫폼 및 데이터 품질 개선에 중점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-164">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="77390-165">향상된 기능으로는 ZAP 프로세스의 일부로 전자 메일에서 실행되는 작업과 같은 배달 전 및 사후 배달 정보가 단일 레코드로 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-165">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="77390-166">스팸 판정, 엔터티 수준 위협(예: 악의적인 URL) 및 최신 배달 위치와 같은 추가 세부 정보도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-166">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="77390-167">이러한 업데이트 후 메시지에 영향을 주는 다른 배달 후 이벤트에 관계없이 각 메시지에 대해 단일 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-167">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="77390-168">작업에는 ZAP, 수동 수정(즉, 관리자 작업), 동적 배달 등을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-168">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="77390-169">맬웨어 및 피싱 위협을 표시하는 것 외에도 전자 메일과 관련된 스팸 판정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-169">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="77390-170">전자 메일 내에서 해당 검색 기술과 함께 전자 메일과 관련된 모든 위협을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77390-170">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="77390-171">전자 메일에는 0, 1 또는 여러 위협이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-171">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="77390-172">전자 메일 플라이아웃의 **세부** 정보 섹션에서 현재 위협을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-172">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="77390-173">맬웨어 및 피싱과 같은 여러  위협에 대한 검색 기술 필드에는 위협을 식별한 감지 기술인 위협 감지 매핑이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-173">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="77390-174">이제 다양한 검색 기술에는 새로운 검색 방법과 스팸 감지 기술이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-174">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="77390-175">동일한 검색 기술 집합을 사용하여 여러 전자 메일 보기(맬웨어, 피싱, 모든 전자 메일)에서 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-175">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="77390-176">판정 분석이 반드시 엔터티에 연결되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-176">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="77390-177">예를 들어 전자 메일은 피싱 또는 스팸으로 분류될 수 있지만 피싱/스팸 판정으로 스탬프 처리된 URL은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-177">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="77390-178">이는 필터가 결과를 할당하기 전에 전자 메일의 콘텐츠 및 기타 세부 정보도 평가하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-178">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="77390-179">URL의 위협</span><span class="sxs-lookup"><span data-stu-id="77390-179">Threats in URLs</span></span>

<span data-ttu-id="77390-180">이제 전자 메일 플라이아웃 세부 정보 탭에서 URL에 대한 특정 위협을 볼 **수** 있습니다. 위협은  *맬웨어,* *피싱, 스팸* 또는 *없음일 수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-180">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-181">![URL 위협](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="77390-181">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="77390-182">업데이트된 시간 표시 막대 보기(예정)</span><span class="sxs-lookup"><span data-stu-id="77390-182">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-183">![업데이트된 시간 표시 막대 보기](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="77390-183">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="77390-184">시간 표시 막대 보기는 모든 배달 및 배달 후 이벤트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-184">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="77390-185">여기에는 이러한 이벤트의 하위 집합에 대해 해당 시점에 식별된 위협에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-185">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="77390-186">시간 표시 막대 보기는 해당 작업의 결과와 함께 추가 작업(예: ZAP 또는 수동 수정)에 대한 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-186">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="77390-187">시간 표시 막대 보기 정보에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-187">Timeline view information includes:</span></span>

- <span data-ttu-id="77390-188">**원본:** 이벤트의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-188">**Source:** Source of the event.</span></span> <span data-ttu-id="77390-189">관리자/시스템/사용자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-189">It can be admin/system/user.</span></span>
- <span data-ttu-id="77390-190">**이벤트:** 원본 배달, 수동 수정, ZAP, 제출 및 동적 배달과 같은 최상위 이벤트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-190">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="77390-191">**작업:** ZAP 또는 관리자 작업의 일부로 수행된 특정 작업(예: 소프트 삭제)입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-191">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="77390-192">**위협:** 이 시점에서 식별된 위협(맬웨어, 피싱, 스팸)을 다산합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-192">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="77390-193">**결과/세부 정보:** 작업의 결과에 대한 자세한 정보(예: ZAP/관리자 작업의 일부로 수행 여부)</span><span class="sxs-lookup"><span data-stu-id="77390-193">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="77390-194">원본 및 최신 배달 위치</span><span class="sxs-lookup"><span data-stu-id="77390-194">Original and latest delivery location</span></span>

<span data-ttu-id="77390-195">현재 전자 메일 그리드 및 전자 메일 플라이아웃에 배달 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-195">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="77390-196">배달 **위치 필드의** 이름을 원래 배달 위치 **__로 변경합니다._*또한 다른 필드\* _ 최신 배달 _위치 를 소개합니다._*\*</span><span class="sxs-lookup"><span data-stu-id="77390-196">The **Delivery location** field is getting renamed **_Original delivery location_*_. And we're introducing another field, _*_Latest delivery location_**.</span></span>

<span data-ttu-id="77390-197">**원래 배달 위치는** 처음에 전자 메일이 배달된 위치에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-197">**Original delivery location** will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="77390-198">**최신 배달 위치는** *ZAP와* 같은 시스템 작업 또는 삭제된 항목으로 이동과 같은 관리자 작업 후에 전자 *메일이 전송된 위치를 표시됩니다.*</span><span class="sxs-lookup"><span data-stu-id="77390-198">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="77390-199">최신 배달 위치는 메시지의 배달 후 또는 시스템/관리자 작업을 관리자에게 알려 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-199">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="77390-200">전자 메일에 대한 최종 사용자 작업은 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-200">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="77390-201">예를 들어 사용자가 메시지를 삭제하거나 메시지를 archive/pst로 이동한 경우 메시지 "배달" 위치가 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-201">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="77390-202">그러나 시스템 작업이 위치를 업데이트한 경우(예: ZAP로 인해 전자 메일이  검지로 이동) 최신 배달 위치는 "검사"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-202">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-203">![업데이트된 배달 위치](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="77390-203">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="77390-204">배달 위치 및  배달 작업이  "알 수 없음"으로 표시될 수 있는 몇 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-204">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="77390-205">메시지가 배달된 경우 배달 위치가 "배달된" 배달 위치로 표시될 수 있지만 받은 편지함 규칙은 메시지를 받은 편지함 또는 정크 메일 폴더 대신 기본 폴더(예: 임시 보관함 또는 보관함)로 이동했습니다.  </span><span class="sxs-lookup"><span data-stu-id="77390-205">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="77390-206">**ZAP와** 같은 관리자/시스템 작업을 시도했지만 메시지를 찾을 수 없는 경우 최신 배달 위치를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-206">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="77390-207">일반적으로 이 작업은 사용자가 메시지를 이동하거나 삭제한 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-207">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="77390-208">이러한 경우 시간 표시 막대 보기에서 **결과/세부** 정보 열을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-208">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="77390-209">"사용자가 메시지를 이동하거나 삭제했습니다."라는 문을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-209">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-210">![시간 표시 막대의 배달 위치](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="77390-210">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="77390-211">추가 작업</span><span class="sxs-lookup"><span data-stu-id="77390-211">Additional actions</span></span>

<span data-ttu-id="77390-212">*추가 작업은* 전자 메일을 배달한 후에 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-212">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="77390-213">여기에는 *ZAP,*  수동 수정(관리자가 수행한 작업(예: 소프트 *삭제),*  동적 배달 및 다시 처리(소수로 좋은 것으로 감지된 전자 메일의 경우)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-213">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> <span data-ttu-id="77390-214">보류 중인 변경 내용의 일부로 현재 배달 작업 필터에 표시되어 있는 "ZAP에서 제거됨" 값이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-214">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="77390-215">추가 작업을 통해 ZAP 시도가 있는 모든 전자 메일을 검색할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-215">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-216">![탐색기에서 추가 작업](../../media/Additional_Actions.png)</span><span class="sxs-lookup"><span data-stu-id="77390-216">![Additional Actions in Explorer](../../media/Additional_Actions.png)</span></span>

### <a name="system-overrides"></a><span data-ttu-id="77390-217">시스템 오버라이드</span><span class="sxs-lookup"><span data-stu-id="77390-217">System overrides</span></span>

<span data-ttu-id="77390-218">*시스템 다시 설정을 사용하면* 메시지의 의도된 배달 위치에 대한 예외를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-218">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="77390-219">필터링 스택에서 식별된 위협 및 기타 검색에 따라 시스템에서 제공하는 배달 위치를 다시 의합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-219">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="77390-220">시스템 오버라이드는 테넌트 또는 사용자 정책을 통해 설정하여 정책에서 제안한 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-220">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="77390-221">다시 설정은 사용자가 설정한 보낸 사람 정책과 같이 구성 간격으로 인해 의도하지 않은 악성 메시지 Safe 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-221">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="77390-222">이러한 값은 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-222">These override values can be:</span></span>

- <span data-ttu-id="77390-223">사용자 정책에서 허용: 사용자는 사서함 수준에서 도메인 또는 보낸 사람이 허용하는 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77390-223">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>

- <span data-ttu-id="77390-224">사용자 정책에 의해 차단: 사용자는 메일 상자 수준에서 도메인 또는 보낸 사람 차단 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77390-224">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>

- <span data-ttu-id="77390-225">조직 정책에서 허용: 조직의 보안 팀은 조직의 Exchange 사용자에 대해 보낸 사람 및 도메인을 허용하도록 정책 또는 메일 흐름 규칙(전송 규칙)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-225">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="77390-226">사용자 집합 또는 전체 조직에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-226">This can be for a set of users or the entire organization.</span></span>

- <span data-ttu-id="77390-227">조직 정책에 의해 차단: 조직의 보안 팀은 조직의 사용자에 대한 보낸 사람, 도메인, 메시지 언어 또는 원본 IPS를 차단하는 정책 또는 메일 흐름 규칙을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-227">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="77390-228">이 설정은 사용자 집합 또는 전체 조직에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-228">This can be applied to a set of users or the entire organization.</span></span>

- <span data-ttu-id="77390-229">조직 정책에 의해 차단된 파일 확장명: 조직의 보안 팀이 맬웨어 방지 정책 설정을 통해 파일 이름 확장명을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-229">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="77390-230">이러한 값은 조사에 도움이 될 수 있도록 전자 메일 세부 정보로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-230">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="77390-231">Secops 팀은 다양한 필터링 기능을 사용하여 차단된 파일 확장명을 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-231">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="77390-232">[![탐색기에서 시스템 오버라이드](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77390-232">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-233">![탐색기에서 시스템 눈금을 오버라이드합니다.](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="77390-233">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="77390-234">URL 및 클릭 환경 개선</span><span class="sxs-lookup"><span data-stu-id="77390-234">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="77390-235">향상된 기능으로는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-235">The improvements include:</span></span>

- <span data-ttu-id="77390-236">URL 플라이아웃의 클릭 섹션에 전체 클릭된 URL(URL의 일부인 쿼리 매개 변수 포함)을 표시하세요. </span><span class="sxs-lookup"><span data-stu-id="77390-236">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="77390-237">현재 URL 도메인 및 경로는 제목 표시줄에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-237">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="77390-238">전체 URL을 표시하기 위해 해당 정보를 확장하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-238">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="77390-239">URL  *필터(URL과* URL 도메인 및 URL 도메인 및 *경로)* 픽스: 업데이트는 URL/클릭 결과를 포함하는 메시지 검색에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-239">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="77390-240">프로토콜에 기반하지 않은 검색에 대한 지원을 사용하도록 설정하여 를 사용하지 않고 URL을 검색할 수 `http` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-240">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="77390-241">기본적으로 URL 검색은 다른 값을 명시적으로 지정하지 않는 한 http에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-241">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="77390-242">예제:</span><span class="sxs-lookup"><span data-stu-id="77390-242">For example:</span></span>
  - <span data-ttu-id="77390-243">URL, URL 도메인 및 URL 도메인 및 경로 필터 필드의 사전 사전을 사용하여 `http://` 검색합니다.   </span><span class="sxs-lookup"><span data-stu-id="77390-243">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="77390-244">검색에 동일한 결과가 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-244">The searches should show the same results.</span></span>
  - <span data-ttu-id="77390-245">`https://`URL에서 prefix를 **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-245">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="77390-246">값을 지정하지 않으면 `http://` prefix가 가정됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-246">When no value is specified, the `http://` prefix is assumed.</span></span>
  - <span data-ttu-id="77390-247">`/`은 URL 경로, **URL** 도메인, **URL** 도메인 및 경로 필드의 시작과 끝에서 **무시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-247">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="77390-248">`/` URL 필드의 끝에 있는 **은** 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-248">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="77390-249">피싱 신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="77390-249">Phish confidence level</span></span>

<span data-ttu-id="77390-250">피싱 신뢰 수준은 전자 메일이 "피싱"으로 분류된 신뢰 수준을 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-250">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="77390-251">가능한 두 값은 *High* 및 *Normal입니다.*</span><span class="sxs-lookup"><span data-stu-id="77390-251">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="77390-252">초기 단계에서 이 필터는 위협 탐색기 피싱 보기에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-252">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="77390-253">[![탐색기에서 피싱 지수](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77390-253">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="77390-254">ZAP URL 신호</span><span class="sxs-lookup"><span data-stu-id="77390-254">ZAP URL signal</span></span>

<span data-ttu-id="77390-255">ZAP URL 신호는 일반적으로 전자 메일이 피싱으로 식별되고 배달 후 제거된 ZAP 피싱 경고 시나리오에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-255">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="77390-256">이 신호는 경고를 Explorer의 해당 결과와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-256">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="77390-257">이 이벤트는 경고에 대한 IOC 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-257">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="77390-258">헌팅 프로세스를 개선하기 위해 헌팅 환경의 일관성을 높이기 위해 위협 탐색기 및 실시간 검색을 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-258">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="77390-259">변경 내용은 다음과 같이 간략하게 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-259">The changes are outlined here:</span></span>

- [<span data-ttu-id="77390-260">개선된 시간제</span><span class="sxs-lookup"><span data-stu-id="77390-260">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="77390-261">새로 고침 프로세스에서 업데이트</span><span class="sxs-lookup"><span data-stu-id="77390-261">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="77390-262">필터에 추가할 차트 드릴다운</span><span class="sxs-lookup"><span data-stu-id="77390-262">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="77390-263">제품 정보 업데이트에서</span><span class="sxs-lookup"><span data-stu-id="77390-263">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="77390-264">사용자 태그로 필터링</span><span class="sxs-lookup"><span data-stu-id="77390-264">Filter by user tags</span></span>

<span data-ttu-id="77390-265">이제 시스템 또는 사용자 지정 사용자 태그를 정렬하고 필터링하여 위협 범위를 빠르게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-265">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="77390-266">자세한 내용은 사용자 태그 [를 참조합니다.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="77390-266">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77390-267">사용자 태그별 필터링 및 정렬은 현재 공개 미리 보기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-267">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="77390-268">이 기능은 상업적으로 출시되기 전에 상당수 수정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-268">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="77390-269">Microsoft는 제공된 정보에 대해 표현적 또는 암시적 보증을하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-269">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-270">![탐색기에서 태그 열](../../media/threat-explorer-tags.png)</span><span class="sxs-lookup"><span data-stu-id="77390-270">![Tags column in Explorer](../../media/threat-explorer-tags.png)</span></span>

### <a name="timezone-improvements"></a><span data-ttu-id="77390-271">개선된 시간제</span><span class="sxs-lookup"><span data-stu-id="77390-271">Timezone improvements</span></span>

<span data-ttu-id="77390-272">내보낼 데이터뿐만 아니라 포털의 전자 메일 레코드에 대한 표준 시간대가 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-272">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="77390-273">전자 메일 그리드, 세부 정보 플라이아웃, 전자 메일 타임라인 및 유사한 전자 메일과 같은 환경 전반에 표시될 것이기 때문에 결과 집합의 표준 시간대가 명확합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-273">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-274">![탐색기에서 표준 시간대 보기](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="77390-274">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="77390-275">새로 고침 프로세스에서 업데이트</span><span class="sxs-lookup"><span data-stu-id="77390-275">Update in the refresh process</span></span>

<span data-ttu-id="77390-276">일부 사용자는 자동 새로 고침(예: 날짜를 변경하는 즉시 페이지가 새로 고쳐지음) 및 수동 새로 고침(다른 필터의 경우)과 혼동하는 것을 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-276">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="77390-277">마찬가지로 필터를 제거하면 자동 새로 고침이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-277">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="77390-278">쿼리를 수정하는 동안 필터를 변경하면 검색 환경이 불일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-278">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="77390-279">이러한 문제를 해결하기 위해 수동 필터링 메커니즘으로 이동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-279">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="77390-280">환경 관점에서 사용자는 다양한 필터 범위(필터 집합 및 날짜)를 적용 및 제거하고 새로 고침 단추를 선택하여 쿼리를 정의한 후 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-280">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="77390-281">이제 화면에서 새로 고침 단추도 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-281">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="77390-282">관련 도구 설명 및 제품 내 설명서도 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-282">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-283">![새로 고침을 선택하여 결과 필터링](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="77390-283">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="77390-284">필터에 추가할 차트 드릴다운</span><span class="sxs-lookup"><span data-stu-id="77390-284">Chart drilldown to add to filters</span></span>

<span data-ttu-id="77390-285">이제 범례 값을 차트로 차트에 필터로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-285">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="77390-286">결과를 **필터링하려면 새로** 고침 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-286">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-287">![차트에서 필터링으로 드릴다운](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="77390-287">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="77390-288">제품 내 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="77390-288">In-product information updates</span></span>

<span data-ttu-id="77390-289">이제 표 내의 총 검색 결과 수와 같은 추가 세부 정보를 제품 내에서 사용할 수 있습니다(아래 참조).</span><span class="sxs-lookup"><span data-stu-id="77390-289">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="77390-290">필터, 검색 환경 및 결과 집합에 대한 자세한 정보를 제공하기 위해 레이블, 오류 메시지 및 도구 탐색이 개선되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-290">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-291">![제품 내 정보 보기](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="77390-291">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="77390-292">위협 탐색기에서 확장된 기능</span><span class="sxs-lookup"><span data-stu-id="77390-292">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="77390-293">상위 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="77390-293">Top targeted users</span></span>

<span data-ttu-id="77390-294">현재 전자 메일의 맬웨어 보기에서 상위 대상 사용자 목록을 상위 맬웨어 패밀리 **섹션에 노출합니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-294">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="77390-295">피싱 및 모든 전자 메일 보기에서 이 보기를 확장할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-295">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="77390-296">상위 5명 대상 사용자와 해당 보기에 대한 각 사용자에 대한 시도 횟수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-296">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="77390-297">예를 들어 피싱 보기의 경우 피싱 시도 횟수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-297">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="77390-298">각 전자 메일 보기에 대한 오프라인 분석 시도 횟수와 함께 대상 사용자 목록을 최대 3,000개까지 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-298">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="77390-299">또한 시도 횟수(예: 아래 이미지에서 13회 시도)를 선택하면 위협 탐색기에서 필터링된 보기가 열리기 때문에 해당 사용자의 전자 메일 및 위협에 대한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-299">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-300">![상위 대상 사용자](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="77390-300">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="77390-301">Exchange 전송 규칙</span><span class="sxs-lookup"><span data-stu-id="77390-301">Exchange transport rules</span></span>

<span data-ttu-id="77390-302">데이터 강화의 일부로 메시지에 적용된 ETR(Exchange 전송 규칙)을 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-302">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="77390-303">이 정보는 전자 메일 그리드 보기에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-303">This information will be available in the Email grid view.</span></span> <span data-ttu-id="77390-304">표시하려면 표에서 **열** 옵션을 선택한 다음 열 **옵션에서** Exchange 규칙 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-304">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="77390-305">또한 전자 메일의 **세부** 정보 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-305">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="77390-306">메시지에 적용된 전송 규칙의 이름과 GUID를 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-306">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="77390-307">전송 규칙의 이름을 사용하여 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-307">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="77390-308">이는 부분 검색도 할 수 있는 "포함" 검색입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-308">This is a "Contains" search, which means you can do partial searches as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77390-309">ETR 검색 및 이름 가용성은 사용자에게 할당된 특정 역할에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="77390-309">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="77390-310">ETR 이름을 보고 검색하려면 다음 역할/권한 중 하나를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-310">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="77390-311">이러한 역할이 할당되지 않은 경우 전송 규칙의 이름을 보거나 ETR 이름을 사용하여 메시지를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-311">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="77390-312">그러나 전자 메일 세부 정보에서 ETR 레이블 및 GUID 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-312">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="77390-313">전자 메일 그리드, 전자 메일 플라이아웃, 필터 및 내보내기의 기타 레코드 보기 환경은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-313">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="77390-314">EXO 전용 - 데이터 손실 방지: 모두</span><span class="sxs-lookup"><span data-stu-id="77390-314">EXO Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="77390-315">EXO 전용 - O365SupportViewConfig: 모두</span><span class="sxs-lookup"><span data-stu-id="77390-315">EXO Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="77390-316">Microsoft Azure Active Directory 또는 EXO - 보안 관리자: 모두</span><span class="sxs-lookup"><span data-stu-id="77390-316">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
> - <span data-ttu-id="77390-317">AAD 또는 EXO - 보안 판독기: 모두</span><span class="sxs-lookup"><span data-stu-id="77390-317">AAD or EXO - Security Reader: All</span></span>
> - <span data-ttu-id="77390-318">EXO 전용 - 전송 규칙: 모두</span><span class="sxs-lookup"><span data-stu-id="77390-318">EXO Only - Transport Rules: All</span></span>
> - <span data-ttu-id="77390-319">EXO 전용 - View-Only 구성: 모두</span><span class="sxs-lookup"><span data-stu-id="77390-319">EXO Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="77390-320">전자 메일 그리드, 세부 정보 플라이아웃 및 내보내는 CSV 내에서 ETRS에는 아래 표시된 이름/GUID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-320">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="77390-321">![Exchange 전송 규칙](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="77390-321">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="77390-322">인바운드 커넥터</span><span class="sxs-lookup"><span data-stu-id="77390-322">Inbound connectors</span></span>

<span data-ttu-id="77390-323">커넥터는 조직 또는 조직에서 전자 메일이 전송되는 방법을 사용자 지정하는 Microsoft 365 Office 365 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-323">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="77390-324">보안 제한 또는 제어를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-324">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="77390-325">위협 탐색기 내에서 이제 전자 메일과 관련된 커넥터를 보고 커넥터 이름을 사용하여 전자 메일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-325">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="77390-326">커넥터 검색은 본질적으로 "포함"입니다. 즉, 부분 키워드 검색도 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-326">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="77390-327">주 그리드 보기, 세부 정보 플라이아웃 및 내보낼 CSV 내에서 커넥터는 다음과 같이 이름/GUID 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-327">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-328">![커넥터 세부 정보](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="77390-328">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="77390-329">위협 탐색기 및 실시간 검색의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="77390-329">New features in Threat Explorer and Real-time detections</span></span>

- [<span data-ttu-id="77390-330">가장된 사용자 및 도메인으로 전송된 피싱 전자 메일 보기</span><span class="sxs-lookup"><span data-stu-id="77390-330">View phishing emails sent to impersonated users and domains</span></span>](#view-phishing-emails-sent-to-impersonated-users-and-domains)
- [<span data-ttu-id="77390-331">전자 메일 헤더 미리 보기 및 전자 메일 본문 다운로드</span><span class="sxs-lookup"><span data-stu-id="77390-331">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="77390-332">전자 메일 타임라인</span><span class="sxs-lookup"><span data-stu-id="77390-332">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="77390-333">URL 내보내기 클릭 데이터</span><span class="sxs-lookup"><span data-stu-id="77390-333">Export URL click data</span></span>](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a><span data-ttu-id="77390-334">가장된 사용자 및 도메인으로 전송된 피싱 전자 메일 보기</span><span class="sxs-lookup"><span data-stu-id="77390-334">View phishing emails sent to impersonated users and domains</span></span>

<span data-ttu-id="77390-335">사용자 및 가장된 도메인에 대한 피싱 시도를 식별하려면 보호할 사용자 목록에 *추가해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="77390-335">To identify phishing attempts against users and domains that are impersonated users must be added to the list of *Users to protect*.</span></span> <span data-ttu-id="77390-336">도메인의 경우 관리자는 조직 도메인을 사용하도록 설정하거나 도메인에 도메인 이름을  *추가하여 보호해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="77390-336">For domains, admins must either enable *Organization domains*, or add a domain name to *Domains to protect*.</span></span> <span data-ttu-id="77390-337">보호할 도메인은 가장 섹션의 피싱 방지 정책 페이지에 *있습니다.* </span><span class="sxs-lookup"><span data-stu-id="77390-337">The domains to protect are found on the *Anti-Phishing policy page* in the *Impersonation* section.</span></span>

<span data-ttu-id="77390-338">피싱 메시지를 검토하고 가장된 사용자 또는 도메인을 검색하려면 전자 메일 > 탐색기 [보기를](threat-explorer-views.md) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-338">To review phish messages and search for impersonated users or domains, use the [Email > Phish view](threat-explorer-views.md) of Explorer.</span></span>

<span data-ttu-id="77390-339">이 예제에서는 위협 탐색기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-339">This example uses Threat Explorer.</span></span>

1. <span data-ttu-id="77390-340">보안 & [준수 센터(](https://protection.office.com) 에서 위협 관리 > 탐색기(또는 실시간 검색)를 https://protection.office.com) 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="77390-340">In the [Security & Compliance Center](https://protection.office.com) (https://protection.office.com), choose Threat management > Explorer (or Real-time detections).</span></span>

2. <span data-ttu-id="77390-341">보기 메뉴에서 피싱 메일 > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-341">In the View menu, choose Email > Phish.</span></span>

   <span data-ttu-id="77390-342">여기에서 **가장된** 도메인 또는 가장된 사용자를 선택할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-342">Here you can choose **impersonated domain** or **impersonated user**.</span></span>

3. <span data-ttu-id="77390-343">**가장된** **도메인** 을 선택한 다음 텍스트 상자에 보호된 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-343">**EITHER** select **Impersonated domain**, and then type a protected domain in the textbox.</span></span>

   <span data-ttu-id="77390-344">예를 들어 *contoso,* contoso.com 또는 에서와 같은 *보호된* 도메인 *이름을 contoso.com.au.*</span><span class="sxs-lookup"><span data-stu-id="77390-344">For example, search for protected domain names like *contoso*, *contoso.com*, or *contoso.com.au*.</span></span>

4. <span data-ttu-id="77390-345">전자 메일 탭 > 탭에서 메시지 제목을 선택하여 가장된 도메인/검색된 위치와 같은 추가 가장 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-345">Select the Subject of any message under the Email tab > Details tab to see additional impersonation information like Impersonated Domain / Detected location.</span></span>

    <span data-ttu-id="77390-346">**또는**</span><span class="sxs-lookup"><span data-stu-id="77390-346">**OR**</span></span>

    <span data-ttu-id="77390-347">가장된 **사용자를 선택하고** 텍스트 상자에 보호된 사용자의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-347">Select **Impersonated user** and type a protected user's email address in the textbox.</span></span>

    > [!TIP]
    > <span data-ttu-id="77390-348">**최상의 결과를 얻기** 위해 전체 *전자* 메일 주소를 사용하여 보호된 사용자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-348">**For best results**, use *full email addresses* to search protected users.</span></span> <span data-ttu-id="77390-349">예를 들어 사용자 가장을 조사할 때 firstname.lastname@contoso.com 보호된 사용자를 더 *빠르고* 성공적으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-349">You will find your protected user quicker and more successfully if you search for *firstname.lastname@contoso.com*, for example, when investigating user impersonation.</span></span> <span data-ttu-id="77390-350">보호된 도메인을 검색할 때 검색은 루트 도메인(예: contoso.com) 및 도메인 *이름(contoso)을 취합니다.*</span><span class="sxs-lookup"><span data-stu-id="77390-350">When searching for a protected domain the search will take the root domain (contoso.com, for example), and the domain name (*contoso*).</span></span> <span data-ttu-id="77390-351">루트 도메인을 검색하면 contoso.com 가장 및 도메인 *contoso.com* *contoso가 반환됩니다.* </span><span class="sxs-lookup"><span data-stu-id="77390-351">Searching for the root domain *contoso.com* will return both impersonations of *contoso.com* and the domain name *contoso*.</span></span>

5. <span data-ttu-id="77390-352">전자 **메일** 탭 세부 정보 탭에서 메시지 제목을 선택하여 사용자 또는 도메인에 대한 추가 가장 정보와 검색된 위치를 볼  >   *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="77390-352">Select the **Subject** of any message under **Email tab** > **Details tab** to see additional impersonation information about the user or domain, and the *Detected location*.</span></span>

    :::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="위협 탐색기에서는 검색 위치 및 검색된 위협(여기서 사용자의 피싱 가장)을 표시하는 보호된 사용자에 대한 세부 정보 창을 자세히 제공합니다.":::

> [!NOTE]
> <span data-ttu-id="77390-354">3단계 또는 5단계에서 검색 기술을  선택하고 가장 도메인  또는 가장 사용자를 각각 선택하는 경우 사용자 또는 도메인에 대한 전자 메일 탭 세부 정보 탭의 정보와 검색된 위치는 피싱 방지 정책 페이지에 나열된 사용자 또는 도메인과 관련된 메시지에만   >   표시됩니다.  </span><span class="sxs-lookup"><span data-stu-id="77390-354">In step 3 or 5, if you choose **Detection Technology** and select **Impersonation domain** or **Impersonation user** respectively, the information in the **Email tab** > **Details tab** about the user or domain, and the *Detected location* will be shown only on the messages that are related to the user or domain listed on the *Anti-Phishing policy* page.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="77390-355">전자 메일 헤더 미리 보기 및 전자 메일 본문 다운로드</span><span class="sxs-lookup"><span data-stu-id="77390-355">Preview email header and download email body</span></span>

<span data-ttu-id="77390-356">이제 전자 메일 헤더를 미리 보고 위협 탐색기에서 전자 메일 본문을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-356">You can now preview an email header and download the email body in Threat Explorer.</span></span> <span data-ttu-id="77390-357">관리자는 다운로드한 헤더/전자 메일 메시지를 위협에 대해 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-357">Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="77390-358">전자 메일 메시지를 다운로드하면 정보가 노출될 위험이 있기 때문에 이 프로세스는 RBAC(역할 기반 액세스 제어)에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-358">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="77390-359">모든 전자 메일 메시지 보기에서 메일을 다운로드할 수 있는 권한을 부여하려면 새 역할 미리 보기 를 보안 작업 또는 보안 관리자와 같은 다른 역할 그룹에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-359">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails in all-email messages view.</span></span> <span data-ttu-id="77390-360">그러나 전자 메일 헤더를 보는 데는 추가 역할이 필요하지 않습니다(위협 탐색기에서 메시지를 보는 데 필요한 역할 외).</span><span class="sxs-lookup"><span data-stu-id="77390-360">However, viewing the email header does not require any additional role (other than what is required to view messages in Threat Explorer).</span></span>

<span data-ttu-id="77390-361">탐색기 및 실시간 검색에는 전자 메일 메시지가 도착하는 위치를 보다 완전한 그림으로 제공하는 새로운 필드도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-361">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="77390-362">이러한 변경으로 보안 연산을 보다 쉽게 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-362">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="77390-363">그러나 주요 결과는 문제 전자 메일 메시지의 위치를 한눈에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-363">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="77390-364">이 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="77390-364">How is this done?</span></span> <span data-ttu-id="77390-365">이제 배달 상태가 두 개의 열로 나어집니다.</span><span class="sxs-lookup"><span data-stu-id="77390-365">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="77390-366">**배달 작업** - 전자 메일의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-366">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="77390-367">**배달 위치** - 전자 메일이 라우팅된 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-367">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="77390-368">*배달 작업은* 기존 정책 또는 검색으로 인해 전자 메일에서 수행된 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-368">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="77390-369">전자 메일에 대해 가능한 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-369">Here are the possible actions for an email:</span></span>

<br>

****

|<span data-ttu-id="77390-370">배달</span><span class="sxs-lookup"><span data-stu-id="77390-370">Delivered</span></span>|<span data-ttu-id="77390-371">정크</span><span class="sxs-lookup"><span data-stu-id="77390-371">Junked</span></span>|<span data-ttu-id="77390-372">차단됨</span><span class="sxs-lookup"><span data-stu-id="77390-372">Blocked</span></span>|<span data-ttu-id="77390-373">바꾸기</span><span class="sxs-lookup"><span data-stu-id="77390-373">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="77390-374">전자 메일이 사용자의 받은 편지함 또는 폴더로 배달된 경우 사용자가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-374">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="77390-375">전자 메일이 사용자의 정크 또는 삭제된 폴더로 전송되고 사용자가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-375">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="77390-376">분리되거나 실패했거나 삭제된 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-376">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="77390-377">이러한 메일은 사용자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-377">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="77390-378">전자 메일에 악의적인 첨부 파일이 .txt 첨부 파일이 악의적이었다고 밝혔습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-378">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|
|

<span data-ttu-id="77390-379">다음은 사용자가 볼 수 있는 것 및 볼 수 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-379">Here is what the user can and can't see:</span></span>

<br>

****

|<span data-ttu-id="77390-380">최종 사용자가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-380">Accessible to end users</span></span>|<span data-ttu-id="77390-381">최종 사용자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-381">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="77390-382">배달</span><span class="sxs-lookup"><span data-stu-id="77390-382">Delivered</span></span>|<span data-ttu-id="77390-383">차단됨</span><span class="sxs-lookup"><span data-stu-id="77390-383">Blocked</span></span>|
|<span data-ttu-id="77390-384">정크</span><span class="sxs-lookup"><span data-stu-id="77390-384">Junked</span></span>|<span data-ttu-id="77390-385">바꾸기</span><span class="sxs-lookup"><span data-stu-id="77390-385">Replaced</span></span>|
|

<span data-ttu-id="77390-386">**배달 위치는** 배달 후 실행된 정책 및 검색의 결과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="77390-386">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="77390-387">배달 작업 **_에 연결됩니다._**</span><span class="sxs-lookup"><span data-stu-id="77390-387">It's linked to **_Delivery action_**.</span></span> <span data-ttu-id="77390-388">다음은 가능한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-388">These are the possible values:</span></span>

- <span data-ttu-id="77390-389">*받은 편지함 또는 폴더:* 전자 메일이 받은 편지함 또는 폴더에 있습니다(전자 메일 규칙에 따라).</span><span class="sxs-lookup"><span data-stu-id="77390-389">*Inbox or folder*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="77390-390">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span><span class="sxs-lookup"><span data-stu-id="77390-390">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="77390-391">*정크 폴더:* 전자 메일이 사용자의 정크 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-391">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="77390-392">*삭제된 항목 폴더:* 사용자의 지우기 항목 폴더에 있는 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-392">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="77390-393">*Quarantine:* 전자 메일이 사용자의 사서함에 있는 것이 아니라 검호에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-393">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="77390-394">*실패:* 전자 메일이 사서함에 도달하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-394">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="77390-395">*삭제:* 메일 흐름에서 전자 메일이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-395">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="77390-396">전자 메일 타임라인</span><span class="sxs-lookup"><span data-stu-id="77390-396">Email timeline</span></span>

<span data-ttu-id="77390-397">전자 **메일 타임라인은** 관리자를 위한 헌팅 환경을 개선하는 새로운 탐색기 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-397">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="77390-398">이벤트를 이해하기 위해 여러 위치를 검사하는 데 소요되는 시간을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-398">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="77390-399">전자 메일이 도착할 때 여러 이벤트가 발생하거나 그에 근접하면 타임라인 보기에 해당 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-399">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="77390-400">전자 메일 배달 후 발생 하는 일부 이벤트는 특수 작업 **열에 캡처** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-400">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="77390-401">관리자는 타임라인의 정보를 메일 배달 후 수행된 특수 작업과 결합하여 정책이 작동되는 방식, 메일이 마지막으로 라우팅된 위치 및 경우에 따라 최종 평가가 어떤지 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-401">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="77390-402">자세한 내용은 에서 배달된 악성 전자 메일 조사 및 [Office 365.](investigate-malicious-email-that-was-delivered.md)</span><span class="sxs-lookup"><span data-stu-id="77390-402">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="77390-403">URL 내보내기 클릭 데이터</span><span class="sxs-lookup"><span data-stu-id="77390-403">Export URL click data</span></span>

<span data-ttu-id="77390-404">이제 URL 클릭에 대한 보고서를 내보낼 수 Microsoft Excel 메시지  **ID를** 보고 결과 를 클릭하여 URL 클릭 트래픽이 시작된 위치를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-404">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="77390-405">작동 방식은 다음과 같습니다. 빠른 실행 Office 365 위협 관리에서 다음 체인을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="77390-405">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="77390-406">**탐색기** \> **피싱 보기** \> **클릭 수** \> **상위 URL 또는** **URL 위쪽 클릭은** 모든 레코드를 선택하여 URL 플라이아웃을 \> 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-406">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="77390-407">목록에서 URL을 선택하면 플라이아웃 패널에  새 내보내기 단추가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-407">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="77390-408">이 단추를 사용하여 보다 쉽게 보고할 수 있도록 Excel 스프레드시트로 데이터를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-408">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="77390-409">실시간 검색 보고서에서 동일한 위치로 이동하기 위해 이 경로를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-409">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="77390-410">**탐색기** \> **실시간 검색** \> **피싱 보기** \> **URL** \> **상위 URL** 또는 위쪽 **클릭** URL 플라이아웃을 열려면 모든 레코드를 선택하여 클릭 \> \> **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-410">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="77390-411">네트워크 메시지 ID는 탐색기 또는 연결된 타사 도구를 통해 ID를 검색할 때 클릭을 특정 메일에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-411">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="77390-412">이러한 검색은 클릭 결과와 연결된 전자 메일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-412">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="77390-413">상호 관련 네트워크 메시지 ID를 사용하면 보다 빠르고 강력한 분석이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-413">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77390-414">![탐색기에서 클릭 탭](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="77390-414">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="77390-415">기술로 전자 메일에서 검색된 맬웨어 보기</span><span class="sxs-lookup"><span data-stu-id="77390-415">See malware detected in email by technology</span></span>

<span data-ttu-id="77390-416">전자 메일에서 검색된 맬웨어가 기술별로 정렬된 것으로 Microsoft 365 가정해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-416">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="77390-417">이렇게하려면 Email > [Explorer의](threat-explorer-views.md#email--malware) 맬웨어 보기(또는 실시간 검색)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-417">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="77390-418">In the Security & Compliance Center ( <https://protection.office.com> ), choose Threat **management** \> **Explorer** (or **Real-time detections**).</span><span class="sxs-lookup"><span data-stu-id="77390-418">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="77390-419">(이 예제에서는 Explorer를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="77390-419">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="77390-420">보기 **메뉴에서** 전자 메일 **맬웨어** \> **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-420">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77390-421">![탐색기용 보기 메뉴](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="77390-421">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="77390-422">보낸 **사람 을** 클릭한 다음 **기본** 검색 기술을 \> **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-422">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="77390-423">이제 검색 기술을 보고서의 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-423">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77390-424">![맬웨어 감지 기술](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="77390-424">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="77390-425">옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-425">Choose an option.</span></span> <span data-ttu-id="77390-426">그런 다음 새로 **고침 단추를** 선택하여 해당 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-426">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77390-427">![선택한 검색 기술](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="77390-427">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="77390-428">보고서가 새로 고쳐서 선택한 기술 옵션을 사용하여 전자 메일에서 맬웨어가 검색된 결과를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="77390-428">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="77390-429">여기에서 추가 분석을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-429">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="77390-430">피싱 URL 보기 및 판정 데이터 클릭</span><span class="sxs-lookup"><span data-stu-id="77390-430">View phishing URL and click verdict data</span></span>

<span data-ttu-id="77390-431">허용, 차단 및 재지정된 URL 목록을 포함하여 전자 메일의 URL을 통한 피싱 시도를 확인하려는 경우를 가정해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-431">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="77390-432">클릭한 URL을 식별하려면 링크 Safe [구성해야](safe-links.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-432">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="77390-433">클릭 시간 보호 [](set-up-safe-links-policies.md) 및 Safe 링크로 클릭 판정 로깅에 대한 링크 정책을 Safe 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-433">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="77390-434">메시지의 피싱 URL을 검토하고 피싱 메시지의 URL을 클릭하려면 탐색기 또는 실시간 검색의 전자 메일 [   >  **피싱**](threat-explorer-views.md#email--phish) 보기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-434">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="77390-435">In the Security & Compliance Center ( <https://protection.office.com> ), choose Threat **management** \> **Explorer** (or **Real-time detections**).</span><span class="sxs-lookup"><span data-stu-id="77390-435">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="77390-436">(이 예제에서는 Explorer를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="77390-436">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="77390-437">보기 **메뉴에서** 전자 **메일** \> **피싱 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-437">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77390-438">![피싱 컨텍스트에서 탐색기 메뉴 보기](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="77390-438">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="77390-439">보낸 **사람 을**  클릭한 다음 URL 확인 \> **클릭 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-439">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="77390-440">차단 및 다시 설정 차단과 같은 하나 이상의 옵션을 선택한  다음 해당 필터를 적용할 옵션과 같은 줄에서 새로 고침 단추를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="77390-440">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="77390-441">(브라우저 창을 새로 고치지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="77390-441">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77390-442">![URL 및 클릭 판정](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="77390-442">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="77390-443">보고서가 새로 고쳐지며 보고서 아래에 있는 URL 탭에 두 개의 서로 다른 URL 테이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-443">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="77390-444">**상위 URL은** 필터링한 메시지의 URL과 각 URL에 대한 전자 메일 배달 작업 수입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-444">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="77390-445">피싱 전자 메일 보기에서 이 목록에는 일반적으로 합법적인 URL이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-445">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="77390-446">공격자는 메시지에 좋은 URL과 잘못된 URL을 혼합하여 배달하려고 시도하지만 악의적인 링크가 더 흥미로워 보이게 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-446">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="77390-447">URL 표는 총 전자 메일 수를 통해 정렬되지만 보기를 단순화하기 위해 이 열은 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="77390-447">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="77390-448">**위쪽 클릭은** Safe 총 클릭 수별로 정렬된 링크로 래핑된 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-448">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="77390-449">보기를 단순화하기 위해 이 열도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-449">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="77390-450">열당 총 개수는 클릭한 각 URL에 Safe 링크 클릭 결과 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77390-450">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="77390-451">피싱 전자 메일 보기에서 이러한 URL은 일반적으로 의심스러우거나 악의적인 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-451">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="77390-452">그러나 보기에는 위협이 아닌 피싱 메시지에 있는 URL이 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-452">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="77390-453">Url clicks on unwrapped links don't show up here.</span><span class="sxs-lookup"><span data-stu-id="77390-453">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="77390-454">두 URL 테이블에는 배달 작업 및 위치로 피싱 전자 메일 메시지의 상위 URL이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-454">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="77390-455">표에는 경고에도 불구하고 차단되거나 방문한 URL 클릭이 표시 있으므로 사용자에게 제공된 잠재적인 잘못된 링크와 사용자의 클릭을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-455">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="77390-456">여기에서 추가 분석을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-456">From here, you can conduct further analysis.</span></span> <span data-ttu-id="77390-457">예를 들어 차트 아래에서 조직의 환경에서 차단된 전자 메일 메시지의 상위 URL을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-457">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77390-458">![차단된 탐색기 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="77390-458">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="77390-459">자세한 정보를 확인하려면 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-459">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="77390-460">URL 플라이아웃 대화 상자에서 전자 메일 메시지에 대한 필터링이 제거되어 작업 환경에서 URL 노출에 대한 전체 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-460">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="77390-461">이렇게 하면 탐색기에서 우려하는 전자 메일 메시지를 필터링하고, 잠재적 위협이 될 수 있는 특정 URL을 찾은 다음 탐색기 보기 자체에 URL 필터를 추가하지 않고도 URL 세부 정보 대화 상자를 통해 환경의 URL 노출에 대한 이해를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-461">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="77390-462">클릭 판정 해석</span><span class="sxs-lookup"><span data-stu-id="77390-462">Interpretation of click verdicts</span></span>

<span data-ttu-id="77390-463">전자 메일 또는 URL 플라이아웃, Top Clicks 및 필터링 환경 내에서 다양한 클릭 판정 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-463">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="77390-464">**없음:** URL에 대한 판정을 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-464">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="77390-465">사용자가 URL을 클릭한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-465">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="77390-466">**허용:** 사용자가 URL로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-466">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="77390-467">**차단된:** 사용자가 URL로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-467">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="77390-468">**보류 중인 판정:** 사용자에게 확인 대기 중인 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-468">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="77390-469">**차단된 은(는)** 사용자가 URL로 직접 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-469">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="77390-470">그러나 사용자가 URL로 이동하기 위해 차단을 어버렸다.</span><span class="sxs-lookup"><span data-stu-id="77390-470">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="77390-471">**보류 중인 판정이 무시됩니다.** 사용자에게 데토톤 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-471">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="77390-472">그러나 사용자가 URL에 액세스하기 위해 메시지를 오버라이드합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-472">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="77390-473">**오류:** 사용자에게 오류 페이지가 표시되거나 판정을 캡처하는 중 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-473">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="77390-474">**실패:** 판정을 캡처하는 동안 알 수 없는 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-474">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="77390-475">사용자가 URL을 클릭한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-475">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="77390-476">사용자가 보고한 전자 메일 메시지 검토</span><span class="sxs-lookup"><span data-stu-id="77390-476">Review email messages reported by users</span></span>

<span data-ttu-id="77390-477">조직의 사용자가 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능 을 통해 정크 메일, 정크 메일 아님 또는 피싱으로 보고한 전자 메일 메시지를 확인하려는 경우를 가정해  봐야 합니다. [](enable-the-report-message-add-in.md) [](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="77390-477">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="77390-478">이를 확인하려면 탐색기(또는 실시간 검색)의 전자 메일 제출 보기를 사용합니다. [   >   ](threat-explorer-views.md#email--submissions)</span><span class="sxs-lookup"><span data-stu-id="77390-478">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="77390-479">In the Security & Compliance Center ( <https://protection.office.com> ), choose Threat **management** \> **Explorer** (or **Real-time detections**).</span><span class="sxs-lookup"><span data-stu-id="77390-479">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="77390-480">(이 예제에서는 Explorer를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="77390-480">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="77390-481">보기 **메뉴에서** 전자 메일 제출  \> **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-481">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77390-482">![전자 메일용 탐색기 메뉴 보기](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="77390-482">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="77390-483">보낸 **사람 을** 클릭한 다음 **기본** 보고서 유형 \> **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77390-483">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="77390-484">피싱 등의 **옵션을** 선택한 다음 새로 **고침 단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-484">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77390-485">![사용자가 보고한 피싱](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="77390-485">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="77390-486">이 보고서는 조직의 사람들이 피싱 시도로 보고한 전자 메일 메시지에 대한 데이터를 표시하기 위해 새로 고쳐서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77390-486">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="77390-487">이 정보를 사용하여 추가 분석을 수행하고 필요한 경우 [Microsoft Defender에서](configure-mdo-anti-phishing-policies.md)피싱 방지 정책을 조정할 수 Office 365.</span><span class="sxs-lookup"><span data-stu-id="77390-487">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="77390-488">자동화된 조사 및 대응 시작</span><span class="sxs-lookup"><span data-stu-id="77390-488">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="77390-489">자동화된 조사 및 대응 기능은 *Microsoft Defender for Office 365 Plan 2* *및* Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="77390-489">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="77390-490">[자동화된 조사 및 대응은](automated-investigation-response-office.md) 사이버 공격을 조사하고 완화하는 데 소요된 보안 운영 팀의 시간과 노력을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-490">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="77390-491">보안 플레이북을 트리거할 수 있는 경고를 구성하는 것 외에도 탐색기 보기에서 자동화된 조사 및 응답 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-491">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="77390-492">자세한 내용은 예제: 보안 관리자가 Explorer에서 [조사를 트리거합니다.를 참조합니다.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)</span><span class="sxs-lookup"><span data-stu-id="77390-492">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="77390-493">탐색기 및 실시간 검색을 사용하는 더 많은 방법</span><span class="sxs-lookup"><span data-stu-id="77390-493">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="77390-494">이 문서에 설명된 시나리오 외에도 탐색기(또는 실시간 검색)에서 더 많은 보고 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-494">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="77390-495">다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-495">See the following articles:</span></span>

- [<span data-ttu-id="77390-496">배달된 악성 전자 메일 찾기 및 조사</span><span class="sxs-lookup"><span data-stu-id="77390-496">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="77390-497">SharePoint Online, OneDrive 및 파일에서 검색된 악성 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77390-497">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](./mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="77390-498">위협 탐색기(및 실시간 검색)에서 보기에 대한 개요를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-498">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="77390-499">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="77390-499">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="77390-500">자동화된 조사 및 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77390-500">Automated investigation and response in Microsoft 365 Defender</span></span>](../defender/m365d-autoir.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="77390-501">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="77390-501">Required licenses and permissions</span></span>

<span data-ttu-id="77390-502">탐색기 또는 실시간 검색을 사용하려면 [Office 365용 Microsoft Defender가](defender-for-office-365.md) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-502">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="77390-503">Explorer는 Office 365 계획 2용 Defender에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-503">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="77390-504">실시간 검색 보고서는 Defender for Office 365 계획 1에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-504">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="77390-505">Office 365용 Defender에서 보호해야 하는 모든 사용자에 대한 라이선스를 할당할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="77390-505">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="77390-506">탐색기 및 실시간 검색은 사용이 허가된 사용자에 대한 검색 데이터를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="77390-506">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="77390-507">탐색기 또는 실시간 검색을 보고 사용하려면 보안 관리자 또는 보안 읽기 권한자에 부여된 권한과 같은 적절한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-507">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="77390-508">보안 & 준수 센터의 경우 다음 역할 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-508">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="77390-509">조직 관리</span><span class="sxs-lookup"><span data-stu-id="77390-509">Organization Management</span></span>
  - <span data-ttu-id="77390-510">보안 관리자(Azure Active Directory 관리 센터에서 할당할 수 있습니다. <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="77390-510">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="77390-511">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="77390-511">Security Reader</span></span>

- <span data-ttu-id="77390-512">Exchange Online의 경우 Exchange 관리 센터( ) 또는 Exchange Online <https://admin.protection.outlook.com/ecp/> [PowerShell에서](/powershell/exchange/exchange-online-powershell)다음 역할 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-512">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="77390-513">조직 관리</span><span class="sxs-lookup"><span data-stu-id="77390-513">Organization Management</span></span>
  - <span data-ttu-id="77390-514">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="77390-514">View-Only Organization Management</span></span>
  - <span data-ttu-id="77390-515">보기 전용 받는 사람</span><span class="sxs-lookup"><span data-stu-id="77390-515">View-Only Recipients</span></span>
  - <span data-ttu-id="77390-516">준수 관리</span><span class="sxs-lookup"><span data-stu-id="77390-516">Compliance Management</span></span>

<span data-ttu-id="77390-517">역할 및 사용 권한에 대한 자세한 내용은 다음 리소스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-517">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="77390-518">보안 및 준수 센터의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="77390-518">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="77390-519">Exchange Online의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="77390-519">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="77390-520">위협 탐색기 및 실시간 검색 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="77390-520">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="77390-521">실시간 *검색 보고서는* Defender for Office 365 계획 1에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-521">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="77390-522">*위협 탐색기는* Defender for Office 365 계획 2에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-522">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="77390-523">실시간 검색 보고서를 사용하면 검색을 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-523">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="77390-524">위협 탐색기에서도 이 기능을 하지만 주어진 공격에 대한 추가 세부 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77390-524">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="77390-525">모든 *전자 메일* 보기는 위협 탐색기에서 사용할 수 있지만 실시간 검색 보고서에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-525">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="77390-526">위협 탐색기에는 더 많은 필터링 기능과 사용 가능한 작업이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77390-526">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="77390-527">자세한 내용은 [Office 365용 Microsoft Defender 서비스 설명: Office 365 계획용 Defender의 기능 가용성을 참조하세요.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="77390-527">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="other-articles"></a><span data-ttu-id="77390-528">기타 문서</span><span class="sxs-lookup"><span data-stu-id="77390-528">Other articles</span></span>

[<span data-ttu-id="77390-529">전자 메일 엔터티 페이지를 통해 전자 메일 조사</span><span class="sxs-lookup"><span data-stu-id="77390-529">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
