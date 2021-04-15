---
title: Microsoft 365 Defender에서 경고 조사
description: 여러 장치, 사용자 및 사서함에 걸쳐 경고를 조사합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 601a8674327c424592c65014793599dc19b2bcd3
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51759435"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="fb2f1-104">Microsoft 365 Defender에서 경고 조사</span><span class="sxs-lookup"><span data-stu-id="fb2f1-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fb2f1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fb2f1-105">**Applies to:**</span></span>
- <span data-ttu-id="fb2f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb2f1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fb2f1-107">경고는 모든 인시던트의 기반이 며 사용자 환경에서 악의적 또는 의심스러운 이벤트가 발생하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="fb2f1-108">경고는 일반적으로 더 광범위한 공격의 일부로, 인시던트에 대한 단서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="fb2f1-109">Microsoft 365 Defender에서 관련 경고는 인시던트 형성을 위해 함께 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="fb2f1-110">인시던트는 항상 공격의 광범위한 컨텍스트를 제공하겠지만, 심층 분석이 필요한 경우 경고 조사가 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="fb2f1-111">조사에서 경고 페이지 사용</span><span class="sxs-lookup"><span data-stu-id="fb2f1-111">Using alert pages in investigations</span></span>

<span data-ttu-id="fb2f1-112">인시던트 페이지의 경고 탭에서 알림을 선택하면 개별 경고 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="fb2f1-113">경고 페이지는 영향을 받는 자산, 경고 스토리 및 세부 정보 창의 세 섹션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![경고 예제 페이지 이미지](../../media/new-alert-page2.png)

<span data-ttu-id="fb2f1-115">경고 페이지 전체에서 엔터티 옆에 있는 3개의 점 아이콘(**...**)을 선택하여 특정 자산 페이지를 열거나 특정 수정 단계를 수행하는 등 사용 가능한 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="fb2f1-116">영향을 받는 자산 분석</span><span class="sxs-lookup"><span data-stu-id="fb2f1-116">Analyze affected assets</span></span>
<span data-ttu-id="fb2f1-117">영향을 받는 자산 섹션에는 사서함, 장치 및 이 경고의 영향을 받는 사용자가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="fb2f1-118">자산 카드를 선택하면 세부 정보 쪽 창에 자산과 관련된 다른 경고(있는 경우)가 포함 된 정보를 채우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="fb2f1-119">경고 스토리에서 경고의 역할 추적</span><span class="sxs-lookup"><span data-stu-id="fb2f1-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="fb2f1-120">경고 스토리에는 프로세스 트리 보기에서 경고와 관련된 모든 자산 또는 엔터티가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="fb2f1-121">제목의 경고는 선택한 경고 페이지에 처음 방문할 때 포커스가 있는 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="fb2f1-122">경고 스토리의 자산은 확장 가능하고 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="fb2f1-123">경고 페이지의 컨텍스트에서 바로 조치를 취할 수 있도록 하여 추가 정보와 즉석 응답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb2f1-124">경고 스토리 섹션에는 두 개 이상의 경고가 포함될 수 있습니다. 이 섹션에서는 선택한 경고 전후에 동일한 실행 트리와 관련된 추가 경고가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="fb2f1-125">세부 정보 창에서 추가 경고 정보 보기</span><span class="sxs-lookup"><span data-stu-id="fb2f1-125">View more alert information in the details pane</span></span>

<span data-ttu-id="fb2f1-126">세부 정보 창에는 처음에 선택한 경고의 세부 정보와 관련된 세부 정보 및 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="fb2f1-127">경고 스토리에서 영향을 받는 자산 또는 엔터티를 선택하면 세부 정보 창이 변경되어 선택한 개체에 대한 상황 정보 및 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="fb2f1-128">관심 있는 엔터티를 선택하면 세부 정보 창이 변경되어 선택한 엔터티 유형에 대한 정보, 사용 가능한 기록 정보 및 경고 페이지에서 이 엔터티에 대해 직접 작업을 수행하기 위한 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="fb2f1-129">경고 관리</span><span class="sxs-lookup"><span data-stu-id="fb2f1-129">Manage alerts</span></span>

<span data-ttu-id="fb2f1-130">경고 조사가 완료되면 시작한 경고로 돌아가 경고 상태를 해결된 것으로 표시하고 이를 False 경고 또는 True 경고로 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="fb2f1-131">경고를 분류하면 더 많은 실제 경고와 거짓 경고를 덜 제공하기 위해 제품을 조정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="fb2f1-132">한 가지 관리 방법은 태그를 사용하여 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="fb2f1-133">Microsoft Defender for Office 365에 대한 태그 지정 기능은 증분적으로 배포되고 있으며 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="fb2f1-134">현재 수정된 태그 이름은 업데이트 후에 만들어진 *경고에만* 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="fb2f1-135">수정 전에 생성된 알림에는 업데이트된 태그 이름이 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="fb2f1-136">통합 경고 큐 관리</span><span class="sxs-lookup"><span data-stu-id="fb2f1-136">Manage the unified alert queue</span></span>

<span data-ttu-id="fb2f1-137">Microsoft 365 보안 센터 & 창에서 인시던트 및 경고를 선택하면 통합 경고 큐로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="fb2f1-138">이 섹션에는 끝점용 Microsoft Defender, Office 365용 Microsoft Defender 및 Microsoft 365 Defender와 같은 다양한 Microsoft 보안 솔루션의 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![샘플 경고 페이지의 이미지](../../media/unified-alert-queue.png)

<span data-ttu-id="fb2f1-140">경고 큐에는 네트워크에서 플래그가 지정된 경고 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="fb2f1-141">기본적으로 큐에는 지난 30일 동안의 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="fb2f1-142">가장 최근 경고는 가장 최근 경고를 먼저 볼 수 있도록 목록 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="fb2f1-143">시작 시 통합 경고 큐에는 7일 동안의 Office 365용 Microsoft Defender 경고만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="fb2f1-144">큐는 시간이 지날 때에도 계속 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-144">The queue will continue to build over time.</span></span> <span data-ttu-id="fb2f1-145">통합 경고 큐를 실행하기 전에 경고를 평가해야 하는 경우 보안 및 준수 센터의 경고 [큐를 사용 합니다.](https://protection.office.com/viewalerts)</span><span class="sxs-lookup"><span data-stu-id="fb2f1-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="fb2f1-146">위쪽 탐색에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="fb2f1-147">필터 적용</span><span class="sxs-lookup"><span data-stu-id="fb2f1-147">Apply filters</span></span>
- <span data-ttu-id="fb2f1-148">열을 추가 또는 제거하기 위해 열 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="fb2f1-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="fb2f1-149">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="fb2f1-149">Export data</span></span>

<span data-ttu-id="fb2f1-150">다른 기준에 따라 경고를 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb2f1-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="fb2f1-151">심각도</span><span class="sxs-lookup"><span data-stu-id="fb2f1-151">Severity</span></span>
- <span data-ttu-id="fb2f1-152">상태</span><span class="sxs-lookup"><span data-stu-id="fb2f1-152">Status</span></span>
- <span data-ttu-id="fb2f1-153">범주</span><span class="sxs-lookup"><span data-stu-id="fb2f1-153">Category</span></span>
- <span data-ttu-id="fb2f1-154">검색 원본</span><span class="sxs-lookup"><span data-stu-id="fb2f1-154">Detection source</span></span>
- <span data-ttu-id="fb2f1-155">정책</span><span class="sxs-lookup"><span data-stu-id="fb2f1-155">Policy</span></span>
- <span data-ttu-id="fb2f1-156">영향을 미치는 자산</span><span class="sxs-lookup"><span data-stu-id="fb2f1-156">Impacted assets</span></span>
- <span data-ttu-id="fb2f1-157">첫 번째 활동</span><span class="sxs-lookup"><span data-stu-id="fb2f1-157">First activity</span></span>
- <span data-ttu-id="fb2f1-158">마지막 활동</span><span class="sxs-lookup"><span data-stu-id="fb2f1-158">Last activity</span></span>


<span data-ttu-id="fb2f1-159">인시던트에 대한 조사를 시작하기 위해 [Microsoft 365 Defender에서](investigate-incidents.md) 인시던트 조사를 읽어 보시고</span><span class="sxs-lookup"><span data-stu-id="fb2f1-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="fb2f1-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb2f1-160">See also</span></span>

- [<span data-ttu-id="fb2f1-161">사고 개요</span><span class="sxs-lookup"><span data-stu-id="fb2f1-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="fb2f1-162">사고 조사</span><span class="sxs-lookup"><span data-stu-id="fb2f1-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="fb2f1-163">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="fb2f1-163">Manage incidents</span></span>](manage-incidents.md)
