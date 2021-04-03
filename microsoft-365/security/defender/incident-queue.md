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
ms.openlocfilehash: 5aba1ab4bed0eeb5f6127ab865ceea674e8d5902
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500996"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="87bb5-104">Microsoft 365 Defender에서 인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="87bb5-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="87bb5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="87bb5-105">**Applies to:**</span></span>
- <span data-ttu-id="87bb5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87bb5-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="87bb5-107">Microsoft 365 Defender는 상관 관계 분석을 적용하고 서로 다른 제품의 모든 관련 경고 및 조사를 하나의 인시던트로 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="87bb5-108">또한 Microsoft 365 Defender는 전체 자산 및 제품군에 걸쳐 Microsoft 365 Defender가 가지고 있는 종단 간 가시성을 통해 악성으로만 식별될 수 있는 활동에 대해 고유한 경고를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="87bb5-109">이 보기는 보안 운영 분석가에게 보다 광범위한 공격 스토리를 제공하여 조직 전체의 복잡한 위협을 더 잘 이해하고 대응하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="87bb5-110">**사고 큐** 는 장치, 사용자 및 사서함에 대해 플래그가 지정 된 사고의 모음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="87bb5-111">이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![사고 큐의 이미지](../../media/incidents-queue.png) 

<span data-ttu-id="87bb5-113">기본적으로 Microsoft 365 보안 센터의 큐에는 지난 30일 동안의 인시던트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="87bb5-114">가장 최근 인시던트는 목록 맨 위에 있으므로 먼저 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="87bb5-115">인시던트 큐는 인시던트 또는 포함된 엔터티의 다양한 특성을 표시하는 사용자 지정 가능한 열을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="87bb5-116">이렇게 하면 처리할 인시던트의 우선 순위 지정에 대한 정보를 통해 의사 결정을 내리는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="87bb5-117">추가 가시성을 위해 자동 인시던트 명명은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 인시던트 이름을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="87bb5-118">이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="87bb5-119">예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*</span><span class="sxs-lookup"><span data-stu-id="87bb5-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="87bb5-120">자동 인시던트 명명을 출시하기 전에 존재한 인시던트의 이름은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="87bb5-121">또한 인시던트 큐는 여러 필터링 옵션을 노출합니다. 이 옵션을 적용하면 환경의 모든 기존 인시던트에 대한 광범위한 스위프를 수행하거나 특정 시나리오 또는 위협에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="87bb5-122">사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="87bb5-123">사용 가능한 필터</span><span class="sxs-lookup"><span data-stu-id="87bb5-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="87bb5-124">할당된 사용자</span><span class="sxs-lookup"><span data-stu-id="87bb5-124">Assigned to</span></span>
<span data-ttu-id="87bb5-125">사용자에게 할당된 경고 또는 자동화에서 처리하는 경고를 표시하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="87bb5-126">범주</span><span class="sxs-lookup"><span data-stu-id="87bb5-126">Categories</span></span>
<span data-ttu-id="87bb5-127">범주를 선택해 특정 전략, 기술 또는 공격 구성 요소에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="87bb5-128">분류</span><span class="sxs-lookup"><span data-stu-id="87bb5-128">Classification</span></span>
<span data-ttu-id="87bb5-129">관련 경고의 설정된 분류에 따라 인시던트 필터링</span><span class="sxs-lookup"><span data-stu-id="87bb5-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="87bb5-130">값에는 실제 경고, 거짓 경고 또는 설정되지 않은 알림이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="87bb5-131">데이터 민감도</span><span class="sxs-lookup"><span data-stu-id="87bb5-131">Data sensitivity</span></span>
<span data-ttu-id="87bb5-132">일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다. </span><span class="sxs-lookup"><span data-stu-id="87bb5-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="87bb5-133">필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="87bb5-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="87bb5-134">Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="87bb5-135">장치 그룹</span><span class="sxs-lookup"><span data-stu-id="87bb5-135">Device group</span></span>
<span data-ttu-id="87bb5-136">정의된 장치 그룹으로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="87bb5-137">조사 상태</span><span class="sxs-lookup"><span data-stu-id="87bb5-137">Investigation state</span></span>
<span data-ttu-id="87bb5-138">자동화된 조사 상태를 통해 인시던트 필터링</span><span class="sxs-lookup"><span data-stu-id="87bb5-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="87bb5-139">다중 범주</span><span class="sxs-lookup"><span data-stu-id="87bb5-139">Multiple categories</span></span> 
<span data-ttu-id="87bb5-140">여러 범주에 매핑된 인시던트만 표시하여 잠재적으로 더 많은 손상을 일으킬 수 있는 인시던트만 보게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="87bb5-141">다중 서비스 원인</span><span class="sxs-lookup"><span data-stu-id="87bb5-141">Multiple service sources</span></span> 
<span data-ttu-id="87bb5-142">다른 원본(끝점용 Microsoft Defender, Microsoft Cloud App Security, ID용 Microsoft Defender, Office 365용 Microsoft Defender)의 경고가 포함된 인시던트만 표시하기 위해 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="87bb5-143">OS 플랫폼</span><span class="sxs-lookup"><span data-stu-id="87bb5-143">OS platform</span></span>
<span data-ttu-id="87bb5-144">운영 체제에 따라 인시던트 큐 보기를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="87bb5-145">서비스 원인</span><span class="sxs-lookup"><span data-stu-id="87bb5-145">Service sources</span></span>
<span data-ttu-id="87bb5-146">특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="87bb5-147">심각도</span><span class="sxs-lookup"><span data-stu-id="87bb5-147">Severity</span></span>
<span data-ttu-id="87bb5-148">인시던트의 심각도는 자산에 미칠 수 있는 영향을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="87bb5-149">심각도가 높을수록 영향이 클수록 일반적으로 가장 즉각적인 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="87bb5-150">상태</span><span class="sxs-lookup"><span data-stu-id="87bb5-150">Status</span></span>
<span data-ttu-id="87bb5-151">상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bb5-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="87bb5-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="87bb5-152">Next steps</span></span>
<span data-ttu-id="87bb5-153">사고의 우선순위를 결정한 뒤 사고에 대한 조사를 진행할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="87bb5-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="87bb5-154">사고 조사</span><span class="sxs-lookup"><span data-stu-id="87bb5-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="87bb5-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87bb5-155">See also</span></span>
- [<span data-ttu-id="87bb5-156">사고 개요</span><span class="sxs-lookup"><span data-stu-id="87bb5-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="87bb5-157">사고 조사</span><span class="sxs-lookup"><span data-stu-id="87bb5-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="87bb5-158">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="87bb5-158">Manage incidents</span></span>](manage-incidents.md)
