---
title: Defender에서 경고 Microsoft 365 조사
description: 여러 장치, 사용자 및 사서함에 걸쳐 경고를 조사합니다.
keywords: 인시던트, 경고, 조사, 분석, 대응, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365
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
ms.openlocfilehash: 6a34269c414f59d40c9160d5728159ed9cddf976
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651355"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="265b9-104">Defender에서 경고 Microsoft 365 조사</span><span class="sxs-lookup"><span data-stu-id="265b9-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="265b9-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="265b9-105">**Applies to:**</span></span>
- <span data-ttu-id="265b9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="265b9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="265b9-107">경고는 모든 인시던트의 기반이 며 사용자 환경에서 악의적 또는 의심스러운 이벤트가 발생하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="265b9-108">경고는 일반적으로 더 광범위한 공격의 일부로, 인시던트에 대한 단서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="265b9-109">Microsoft 365 관련 경고는 인시던트 를 형성하기 위해 함께 [집계됩니다.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="265b9-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="265b9-110">인시던트는 항상 공격의 광범위한 컨텍스트를 제공하겠지만, 심층 분석이 필요한 경우 경고를 분석하는 것이 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="265b9-111">경고 **큐에는** 현재 경고 집합이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="265b9-112">인시던트 및 경고  & > 보안 센터(Microsoft 365)의 빠른 실행에 대한 경고[큐로 security.microsoft.com.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="265b9-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="경고 큐의 예":::

<span data-ttu-id="265b9-114">Endpoint용 Microsoft Defender, Microsoft Defender for Office 365 및 Microsoft 365 Microsoft Defender와 같은 다양한 Microsoft 보안 솔루션의 알림이 여기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="265b9-115">기본적으로 Microsoft 365 보안 센터의 경고 큐에는 지난 30일 동안의 신규 및 진행 중인 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="265b9-116">가장 최근 경고는 목록 맨 위에 있으므로 먼저 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="265b9-117">기본 경고 큐에서 필터를  선택하여 경고의  하위 집합을 지정할 수 있는 필터 창을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="265b9-118">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="경고 큐에 대한 필터 창의 예":::

<span data-ttu-id="265b9-120">다음 조건에 따라 경고를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="265b9-121">심각도</span><span class="sxs-lookup"><span data-stu-id="265b9-121">Severity</span></span>
- <span data-ttu-id="265b9-122">상태</span><span class="sxs-lookup"><span data-stu-id="265b9-122">Status</span></span>
- <span data-ttu-id="265b9-123">범주</span><span class="sxs-lookup"><span data-stu-id="265b9-123">Category</span></span>
- <span data-ttu-id="265b9-124">검색 원본</span><span class="sxs-lookup"><span data-stu-id="265b9-124">Detection source</span></span>
- <span data-ttu-id="265b9-125">태그</span><span class="sxs-lookup"><span data-stu-id="265b9-125">Tags</span></span>
- <span data-ttu-id="265b9-126">정책</span><span class="sxs-lookup"><span data-stu-id="265b9-126">Policy</span></span>
- <span data-ttu-id="265b9-127">영향을 미치는 자산</span><span class="sxs-lookup"><span data-stu-id="265b9-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="265b9-128">경고 분석</span><span class="sxs-lookup"><span data-stu-id="265b9-128">Analyze an alert</span></span>

<span data-ttu-id="265b9-129">기본 경고 페이지를 표시하려면 경고의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="265b9-130">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="보안 센터에서 경고의 세부 정보 Microsoft 365 예":::

<span data-ttu-id="265b9-132">알림 관리 창에서 기본 경고 페이지 열기 **작업을 선택할 수도** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="265b9-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="265b9-133">경고 페이지는 다음 섹션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="265b9-134">경고 스토리 - 이 경고와 관련된 이벤트 및 경고의 체인을 일련 순서로 표시</span><span class="sxs-lookup"><span data-stu-id="265b9-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="265b9-135">요약 세부 정보</span><span class="sxs-lookup"><span data-stu-id="265b9-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="보안 센터에서 경고의 세부 정보 Microsoft 365 예":::

<span data-ttu-id="265b9-137">경고 페이지 전체에서 모든 엔터티 옆에 있는 타원(**...**)을 선택하여 경고 페이지를 열거나 경고를 다른 인시던트에 연결하는 등의 사용 가능한 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="265b9-138">영향을 받는 자산 분석</span><span class="sxs-lookup"><span data-stu-id="265b9-138">Analyze affected assets</span></span>

<span data-ttu-id="265b9-139">수행된 **작업** 섹션에는 사서함, 장치 및 이 경고의 영향을 받는 사용자와 같은 영향을 받는 자산 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-139">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="265b9-140">또한 관리 **센터에서** 보기를 선택하여  관리 센터의 기록 탭을 볼 Microsoft 365 있습니다. </span><span class="sxs-lookup"><span data-stu-id="265b9-140">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="265b9-141">경고 스토리에서 경고의 역할 추적</span><span class="sxs-lookup"><span data-stu-id="265b9-141">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="265b9-142">경고 스토리에는 프로세스 트리 보기에서 경고와 관련된 모든 자산 또는 엔터티가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-142">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="265b9-143">제목의 경고는 선택한 경고 페이지에 처음 방문할 때 포커스가 있는 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-143">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="265b9-144">경고 스토리의 자산은 확장 가능하고 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-144">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="265b9-145">추가 정보를 제공하고 경고 페이지의 컨텍스트에서 바로 조치를 취할 수 있도록 하여 응답을 즉석으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-145">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="265b9-146">경고 스토리 섹션에는 두 개 이상의 경고가 포함될 수 있습니다. 이 섹션에서는 선택한 경고 전후에 동일한 실행 트리와 관련된 추가 경고가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-146">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="265b9-147">세부 정보 페이지에서 추가 경고 정보 보기</span><span class="sxs-lookup"><span data-stu-id="265b9-147">View more alert information on the details page</span></span>

<span data-ttu-id="265b9-148">세부 정보 페이지에는 선택한 경고의 세부 정보 및 관련 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-148">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="265b9-149">경고 스토리에서 영향을 받는 자산 또는 엔터티를 선택하면 세부 정보 페이지가 변경되어 선택한 개체에 대한 상황에 맞는 정보 및 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-149">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="265b9-150">관심 있는 엔터티를 선택한 후 세부 정보 페이지가 변경되어 선택한 엔터티 유형에 대한 정보, 사용 가능한 기록 정보 및 경고 페이지에서 이 엔터티에 대해 직접 작업을 수행하기 위한 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-150">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="265b9-151">경고 관리</span><span class="sxs-lookup"><span data-stu-id="265b9-151">Manage alerts</span></span>

<span data-ttu-id="265b9-152">경고를 관리하려면 해당 행의 경고 큐에서 경고를 선택하여 경고 관리 **창을** 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-152">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="265b9-153">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-153">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="경고에 대한 요약 창의 예":::

<span data-ttu-id="265b9-155">경고 **관리 창에서** 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-155">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="265b9-156">경고 상태(신규, 해결, 진행 중)입니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-156">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="265b9-157">경고의 분류(설정되지 않은, True 경고, 거짓 경고)입니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-157">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="265b9-158">실제 경고로 분류하는 경우 결정 필드의 경고에 대한 위협 **유형입니다.**</span><span class="sxs-lookup"><span data-stu-id="265b9-158">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="265b9-159">경고에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-159">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="265b9-160">한 가지 관리 방법은 태그를 사용하여 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-160">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="265b9-161">Microsoft Defender for Office 365 태그 지정 기능은 증분적으로 배포되고 있으며 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-161">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="265b9-162">현재 수정된 태그 이름은 업데이트 후에 만들어진 *경고에만* 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-162">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="265b9-163">수정 전에 생성된 알림에는 업데이트된 태그 이름이 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-163">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="265b9-164">이 창에서 다음 추가 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-164">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="265b9-165">기본 경고 페이지 열기</span><span class="sxs-lookup"><span data-stu-id="265b9-165">Open the main alert page</span></span>
- <span data-ttu-id="265b9-166">Microsoft 위협 전문가에게 문의</span><span class="sxs-lookup"><span data-stu-id="265b9-166">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="265b9-167">제출 보기</span><span class="sxs-lookup"><span data-stu-id="265b9-167">View submission</span></span>
- <span data-ttu-id="265b9-168">다른 인시던트에 연결</span><span class="sxs-lookup"><span data-stu-id="265b9-168">Link to another incident</span></span>
- <span data-ttu-id="265b9-169">타임라인에서 경고 보기</span><span class="sxs-lookup"><span data-stu-id="265b9-169">See the alert in a timeline</span></span>
- <span data-ttu-id="265b9-170">제거 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="265b9-170">Create a suppression rule</span></span>

<span data-ttu-id="265b9-171">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="보안 센터의 경고에 대한 Microsoft 365 예":::

<span data-ttu-id="265b9-173">추가 작업 목록은 경고 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-173">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="265b9-174">경고 해결</span><span class="sxs-lookup"><span data-stu-id="265b9-174">Resolve an alert</span></span>

<span data-ttu-id="265b9-175">경고 분석이 완료되고 해결할 수 있는 경우 경고에  대한 경고 관리 창으로 이동하여 경고 상태를 **해결된** 것으로 표시하고 **False** 경고 또는 True 경고로 **분류합니다.**</span><span class="sxs-lookup"><span data-stu-id="265b9-175">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="265b9-176">실제 경고의 경우 결정 필드에 경고의 위협 유형을 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="265b9-176">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="265b9-177">경고를 분류하고 결정 값을 지정하면 Defender에서 Microsoft 365 보다 실제 경고와 거짓 경고를 덜 제공하게 조정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b9-177">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="265b9-178">다음 단계</span><span class="sxs-lookup"><span data-stu-id="265b9-178">Next steps</span></span>

<span data-ttu-id="265b9-179">In-process 인시던트에 필요한 경우 조사를 [계속합니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="265b9-179">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="265b9-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="265b9-180">See also</span></span>

- [<span data-ttu-id="265b9-181">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="265b9-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="265b9-182">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="265b9-182">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="265b9-183">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="265b9-183">Investigate incidents</span></span>](investigate-incidents.md)
