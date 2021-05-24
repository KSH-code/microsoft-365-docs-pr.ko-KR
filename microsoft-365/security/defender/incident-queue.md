---
title: Defender에서 인시던트 Microsoft 365 우선 순위 지정
description: Defender의 인시던트 큐에서 인시던트 Microsoft 365 방법 학습
keywords: 인시던트, 큐, 개요, 장치, ID, 사용자, 사서함, 전자 메일, 인시던트, 분석, 응답
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
ms.openlocfilehash: df2d2660267c38dccf5ef09fa4955615d3a78141
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636269"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="17eb4-104">Defender에서 인시던트 Microsoft 365 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="17eb4-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="17eb4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="17eb4-105">**Applies to:**</span></span>
- <span data-ttu-id="17eb4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17eb4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="17eb4-107">Microsoft 365 Defender는 상관 관계 분석을 적용하고 다양한 제품의 관련 경고 및 자동화된 조사를 인시던트에 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="17eb4-108">Microsoft 365 또한 Defender는 전체 제품 제품군에서 Microsoft 365 표시가 있는 경우 악성으로만 식별될 수 있는 활동에 대해 고유한 경고를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="17eb4-109">이 보기는 보안 분석가에게 보다 광범위한 공격 스토리를 제공하여 조직 전체의 복잡한 위협을 더 잘 이해하고 대응하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="17eb4-110">**인시던트 큐에는** 장치, 사용자 및 사서함에서 만들어진 인시던트 모음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="17eb4-111">이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="17eb4-112">인시던트 및  인시던트 & (>)의 빠른 실행에 대한 인시던트 Microsoft 365 큐로[security.microsoft.com.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="17eb4-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="17eb4-113">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="인시던트 큐의 예":::

<span data-ttu-id="17eb4-115">최근 **인시던트** 및 알림 섹션에는 지난 24시간 동안 수신된 경고 및 인시던트 수의 그래프가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="17eb4-116">기본적으로 보안 센터의 인시던트 Microsoft 365 지난 6개월 동안의 인시던트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="17eb4-117">가장 최근 인시던트는 목록 맨 위에 있으므로 먼저 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="17eb4-118">인시던트 큐에는 인시던트 또는 영향을 주는 엔터티의 다양한 특성을 표시하는 사용자 지정 가능한 열이 있습니다(열 선택 선택).</span><span class="sxs-lookup"><span data-stu-id="17eb4-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="17eb4-119">이를 통해 분석을 위한 인시던트 우선 순위에 대한 정보를 통해 의사 결정을 내리는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="17eb4-120">추가 가시성을 위해 자동 인시던트 명명은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 인시던트 이름을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="17eb4-121">이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="17eb4-122">예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*</span><span class="sxs-lookup"><span data-stu-id="17eb4-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="17eb4-123">자동 인시던트 명명을 출시하기 전에 존재한 인시던트의 이름은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="17eb4-124">또한 인시던트 큐는 여러 필터링 옵션을 노출합니다. 이 옵션을 적용하면 환경의 모든 기존 인시던트에 대한 광범위한 스위프를 수행하거나 특정 시나리오 또는 위협에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="17eb4-125">사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="17eb4-126">사용 가능한 필터</span><span class="sxs-lookup"><span data-stu-id="17eb4-126">Available filters</span></span>

<span data-ttu-id="17eb4-127">기본 인시던트 큐에서  필터를 선택하여 필터링된 인시던트 집합을 볼 수 있는 필터 창을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="17eb4-128">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="인시던트 큐에 대한 필터 창의 예":::

<span data-ttu-id="17eb4-130">다음 표에는 사용 가능한 필터 이름이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="17eb4-131">필터 이름</span><span class="sxs-lookup"><span data-stu-id="17eb4-131">Filter name</span></span> | <span data-ttu-id="17eb4-132">설명</span><span class="sxs-lookup"><span data-stu-id="17eb4-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="17eb4-133">할당된 사용자</span><span class="sxs-lookup"><span data-stu-id="17eb4-133">Assigned to</span></span> | <span data-ttu-id="17eb4-134">사용자에게 할당된 경고 또는 자동화에서 처리하는 경고를 표시하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="17eb4-135">범주</span><span class="sxs-lookup"><span data-stu-id="17eb4-135">Categories</span></span> | <span data-ttu-id="17eb4-136">범주를 선택해 특정 전략, 기술 또는 공격 구성 요소에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="17eb4-137">분류</span><span class="sxs-lookup"><span data-stu-id="17eb4-137">Classification</span></span> | <span data-ttu-id="17eb4-138">관련 경고의 설정된 분류에 따라 인시던트 필터링</span><span class="sxs-lookup"><span data-stu-id="17eb4-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="17eb4-139">값에는 실제 경고, 거짓 경고 또는 설정되지 않은 알림이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="17eb4-140">데이터 민감도</span><span class="sxs-lookup"><span data-stu-id="17eb4-140">Data sensitivity</span></span> | <span data-ttu-id="17eb4-141">일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다. </span><span class="sxs-lookup"><span data-stu-id="17eb4-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="17eb4-142">필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="17eb4-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="17eb4-143">Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="17eb4-144">장치 그룹</span><span class="sxs-lookup"><span data-stu-id="17eb4-144">Device group</span></span> | <span data-ttu-id="17eb4-145">정의된 장치 그룹으로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="17eb4-146">조사 상태</span><span class="sxs-lookup"><span data-stu-id="17eb4-146">Investigation state</span></span> | <span data-ttu-id="17eb4-147">자동화된 조사 상태를 통해 인시던트 필터링</span><span class="sxs-lookup"><span data-stu-id="17eb4-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="17eb4-148">다중 범주</span><span class="sxs-lookup"><span data-stu-id="17eb4-148">Multiple categories</span></span> | <span data-ttu-id="17eb4-149">여러 범주에 매핑된 인시던트만 표시하여 잠재적으로 더 많은 손상을 일으킬 수 있는 인시던트만 보게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="17eb4-150">다중 서비스 원인</span><span class="sxs-lookup"><span data-stu-id="17eb4-150">Multiple service sources</span></span>  | <span data-ttu-id="17eb4-151">다른 원본(끝점용 Microsoft Defender, Microsoft Cloud App Security, ID용 Microsoft Defender, Microsoft Defender for Office 365)의 경고만 표시하기 위해 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="17eb4-152">OS 플랫폼</span><span class="sxs-lookup"><span data-stu-id="17eb4-152">OS platform</span></span> | <span data-ttu-id="17eb4-153">운영 체제에 따라 인시던트 큐 보기를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="17eb4-154">서비스 원인</span><span class="sxs-lookup"><span data-stu-id="17eb4-154">Service sources</span></span> | <span data-ttu-id="17eb4-155">특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="17eb4-156">심각도</span><span class="sxs-lookup"><span data-stu-id="17eb4-156">Severity</span></span> | <span data-ttu-id="17eb4-157">인시던트의 심각도는 자산에 미칠 수 있는 영향을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="17eb4-158">심각도가 높을수록 영향이 클수록 일반적으로 가장 즉각적인 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="17eb4-159">상태</span><span class="sxs-lookup"><span data-stu-id="17eb4-159">Status</span></span> | <span data-ttu-id="17eb4-160">상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-steps"></a><span data-ttu-id="17eb4-161">다음 단계</span><span class="sxs-lookup"><span data-stu-id="17eb4-161">Next steps</span></span>

<span data-ttu-id="17eb4-162">우선 순위가 가장 높은 인시던트가 필요한 인시던트가 결정되면 선택하고 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-162">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="17eb4-163">[태그,](manage-incidents.md) 할당, 가짓 긍정 인시던트에 대한 즉각적인 해결 및 설명에 대한 인시던트의 속성을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="17eb4-163">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="17eb4-164">조사를 [시작 합니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="17eb4-164">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="17eb4-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17eb4-165">See also</span></span>
- [<span data-ttu-id="17eb4-166">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="17eb4-166">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="17eb4-167">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="17eb4-167">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="17eb4-168">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="17eb4-168">Investigate incidents</span></span>](investigate-incidents.md)
