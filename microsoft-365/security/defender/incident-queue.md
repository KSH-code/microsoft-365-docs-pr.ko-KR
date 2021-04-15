---
title: Microsoft 365 Defender에서 인시던트 우선 순위 지정
description: Microsoft 365 Defender의 인시던트 큐에서 인시던트 필터링 방법 학습
keywords: 사고, 큐, 개요, 장치, 식별, 사용자, 사서함, 전자 메일, 사고
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
ms.openlocfilehash: 12207d69b0a1565caf762a265c1a0d32158ca291
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759847"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="3c155-104">Microsoft 365 Defender에서 인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="3c155-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3c155-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3c155-105">**Applies to:**</span></span>
- <span data-ttu-id="3c155-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c155-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3c155-107">Microsoft 365 Defender는 상관 관계 분석을 적용하고 관련 경고 및 다양한 제품의 자동화된 조사를 인시던트에 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="3c155-108">또한 Microsoft 365 Defender는 전체 제품군에 걸쳐 Microsoft 365 Defender가 보유하고 있는 종단 간 표시가 있는 경우 악성으로만 식별될 수 있는 활동에 대해 고유한 경고를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="3c155-109">이 보기는 보안 분석가에게 보다 광범위한 공격 스토리를 제공하여 조직 전체의 복잡한 위협을 더 잘 이해하고 대응하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="3c155-110">**인시던트 큐에는** 장치, 사용자 및 사서함에서 만들어진 인시던트 모음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="3c155-111">이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="3c155-112">인시던트 및  인시던트 & Microsoft 365 보안 센터(>)의 빠른 실행에서 인시던트[큐로 security.microsoft.com.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3c155-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="인시던트 큐의 예":::

<span data-ttu-id="3c155-114">기본적으로 Microsoft 365 보안 센터의 큐에는 지난 6개월 동안의 인시던트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-114">By default, the queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="3c155-115">가장 최근 인시던트는 목록 맨 위에 있으므로 먼저 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="3c155-116">인시던트 큐에는 인시던트 또는 영향을 주는 엔터티의 다양한 특성을 표시하는 사용자 지정 가능한 열이 있습니다(열 선택 선택).</span><span class="sxs-lookup"><span data-stu-id="3c155-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="3c155-117">이를 통해 분석에 대한 인시던트 우선 순위에 대한 정보를 통해 의사 결정을 내리는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-117">This helps you make an informed decision regarding the prioritization of incidents for anaylsis.</span></span>

<span data-ttu-id="3c155-118">추가 가시성을 위해 자동 인시던트 명명은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 인시던트 이름을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="3c155-119">이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="3c155-120">예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*</span><span class="sxs-lookup"><span data-stu-id="3c155-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="3c155-121">자동 인시던트 명명을 출시하기 전에 존재한 인시던트의 이름은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="3c155-122">또한 인시던트 큐는 여러 필터링 옵션을 노출합니다. 이 옵션을 적용하면 환경의 모든 기존 인시던트에 대한 광범위한 스위프를 수행하거나 특정 시나리오 또는 위협에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="3c155-123">사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="3c155-124">사용 가능한 필터</span><span class="sxs-lookup"><span data-stu-id="3c155-124">Available filters</span></span>

<span data-ttu-id="3c155-125">기본 인시던트 큐에서  필터를 선택하여 필터링된 인시던트 집합을 볼 수 있는 필터 창을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="3c155-126">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="인시던트 큐에 대한 필터 창의 예":::

<span data-ttu-id="3c155-128">다음 표에는 사용 가능한 필터 이름이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="3c155-129">필터 이름</span><span class="sxs-lookup"><span data-stu-id="3c155-129">Filter name</span></span> | <span data-ttu-id="3c155-130">설명</span><span class="sxs-lookup"><span data-stu-id="3c155-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="3c155-131">할당된 사용자</span><span class="sxs-lookup"><span data-stu-id="3c155-131">Assigned to</span></span> | <span data-ttu-id="3c155-132">사용자에게 할당된 경고 또는 자동화에서 처리하는 경고를 표시하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="3c155-133">범주</span><span class="sxs-lookup"><span data-stu-id="3c155-133">Categories</span></span> | <span data-ttu-id="3c155-134">범주를 선택해 특정 전략, 기술 또는 공격 구성 요소에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="3c155-135">분류</span><span class="sxs-lookup"><span data-stu-id="3c155-135">Classification</span></span> | <span data-ttu-id="3c155-136">관련 경고의 설정된 분류에 따라 인시던트 필터링</span><span class="sxs-lookup"><span data-stu-id="3c155-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="3c155-137">값에는 실제 경고, 거짓 경고 또는 설정되지 않은 알림이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="3c155-138">데이터 민감도</span><span class="sxs-lookup"><span data-stu-id="3c155-138">Data sensitivity</span></span> | <span data-ttu-id="3c155-139">일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다. </span><span class="sxs-lookup"><span data-stu-id="3c155-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="3c155-140">필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="3c155-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="3c155-141">Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="3c155-142">장치 그룹</span><span class="sxs-lookup"><span data-stu-id="3c155-142">Device group</span></span> | <span data-ttu-id="3c155-143">정의된 장치 그룹으로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="3c155-144">조사 상태</span><span class="sxs-lookup"><span data-stu-id="3c155-144">Investigation state</span></span> | <span data-ttu-id="3c155-145">자동화된 조사 상태를 통해 인시던트 필터링</span><span class="sxs-lookup"><span data-stu-id="3c155-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="3c155-146">다중 범주</span><span class="sxs-lookup"><span data-stu-id="3c155-146">Multiple categories</span></span> | <span data-ttu-id="3c155-147">여러 범주에 매핑된 인시던트만 표시하여 잠재적으로 더 많은 손상을 일으킬 수 있는 인시던트만 보게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="3c155-148">다중 서비스 원인</span><span class="sxs-lookup"><span data-stu-id="3c155-148">Multiple service sources</span></span>  | <span data-ttu-id="3c155-149">다른 원본(끝점용 Microsoft Defender, Microsoft Cloud App Security, ID용 Microsoft Defender, Office 365용 Microsoft Defender)의 경고가 포함된 인시던트만 표시하기 위해 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="3c155-150">OS 플랫폼</span><span class="sxs-lookup"><span data-stu-id="3c155-150">OS platform</span></span> | <span data-ttu-id="3c155-151">운영 체제에 따라 인시던트 큐 보기를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="3c155-152">서비스 원인</span><span class="sxs-lookup"><span data-stu-id="3c155-152">Service sources</span></span> | <span data-ttu-id="3c155-153">특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="3c155-154">심각도</span><span class="sxs-lookup"><span data-stu-id="3c155-154">Severity</span></span> | <span data-ttu-id="3c155-155">인시던트의 심각도는 자산에 미칠 수 있는 영향을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="3c155-156">심각도가 높을수록 영향이 클수록 일반적으로 가장 즉각적인 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="3c155-157">상태</span><span class="sxs-lookup"><span data-stu-id="3c155-157">Status</span></span> | <span data-ttu-id="3c155-158">상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="3c155-159">인시던트 대응 워크플로</span><span class="sxs-lookup"><span data-stu-id="3c155-159">Incident response workflow</span></span>

<span data-ttu-id="3c155-160">다음은 인시던트에 응답하기 위한 일반적인 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-160">Here is the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="3c155-161">조사 및 해결을 위해 우선 순위가 가장 높은 인시던트 식별 및 세분화</span><span class="sxs-lookup"><span data-stu-id="3c155-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="3c155-162">우선 순위가 높은 각 인시던트에 대해 조사를 [시작합니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="3c155-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="3c155-163">a.</span><span class="sxs-lookup"><span data-stu-id="3c155-163">a.</span></span> <span data-ttu-id="3c155-164">인시던트의 요약을 보고 인시던트의 범위, 영향을 받는 엔터티 및  심각도(요약 탭)를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-164">View the summary of the incident to understand it's scope, what entities are affected, and severity (the **Summary** tab).</span></span>

   <span data-ttu-id="3c155-165">b.</span><span class="sxs-lookup"><span data-stu-id="3c155-165">b.</span></span> <span data-ttu-id="3c155-166">경고를 보고 시작하여 경고의 출처, 범위 및 **심각도(경고** 탭)를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="3c155-167">c.</span><span class="sxs-lookup"><span data-stu-id="3c155-167">c.</span></span> <span data-ttu-id="3c155-168">필요한 경우 영향을 받는 장치, 사용자 및 사서함(장치, 사용자 및 사서함 탭)에 대한 **정보를** 수집합니다. </span><span class="sxs-lookup"><span data-stu-id="3c155-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="3c155-169">d.</span><span class="sxs-lookup"><span data-stu-id="3c155-169">d.</span></span> <span data-ttu-id="3c155-170">Microsoft 365 Defender가 일부 경고(조사 탭)를 자동으로 해결한 **방법을** 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="3c155-171">e.</span><span class="sxs-lookup"><span data-stu-id="3c155-171">e.</span></span> <span data-ttu-id="3c155-172">필요한 경우 인시던트에 대한 데이터 집합의 정보를 사용하여 자세한 정보(증거 및 응답 **탭)를 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c155-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

<span data-ttu-id="3c155-173">조사할 때 다음을 염려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-173">As you investigate, you should be concerned with:</span></span>

- <span data-ttu-id="3c155-174">포함: 테넌트에 대한 추가 영향을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-174">Containment: Reducing any additional impact on your tenant.</span></span>
- <span data-ttu-id="3c155-175">지우기: 보안 위협 제거.</span><span class="sxs-lookup"><span data-stu-id="3c155-175">Eradication: Removing the security threat.</span></span>
- <span data-ttu-id="3c155-176">복구: 테넌트 리소스를 공격 전에 있는 상태로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-176">Recovery: Restoring your tenant resources to the state they were in before the attack.</span></span>

<span data-ttu-id="3c155-177">인시던트 해결 후 잠시 시간을 내어 다음을 배우는 것이 가장 까다로워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-177">After you resolve the incident, take a moment to learn from it to:</span></span>

- <span data-ttu-id="3c155-178">공격의 유형과 그 영향에 대해 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-178">Understand the type of the attack and its impact.</span></span>
- <span data-ttu-id="3c155-179">보안 커뮤니티에서 보안 공격 추세를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-179">Research the attack in the security community for a security attack trend.</span></span>
- <span data-ttu-id="3c155-180">인시던트 해결에 사용한 워크플로를 회수하고 필요한 경우 표준 워크플로 및 plalbook을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-180">Recall the workflow you used to resolve the incident and update your standard workflows and plalbooks as needed.</span></span>

<span data-ttu-id="3c155-181">다음은 기본 프로세스에 대한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="3c155-181">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="인시던트 조사를 위한 기본 프로세스":::

## <a name="next-step"></a><span data-ttu-id="3c155-183">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3c155-183">Next step</span></span>

<span data-ttu-id="3c155-184">우선 순위가 가장 높은 인시던트가 필요한 사고를 확인한 후 해당 인시던트 를 선택하고 조사를 [시작합니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="3c155-184">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c155-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c155-185">See also</span></span>
- [<span data-ttu-id="3c155-186">사고 개요</span><span class="sxs-lookup"><span data-stu-id="3c155-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="3c155-187">사고 조사</span><span class="sxs-lookup"><span data-stu-id="3c155-187">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="3c155-188">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="3c155-188">Manage incidents</span></span>](manage-incidents.md)
