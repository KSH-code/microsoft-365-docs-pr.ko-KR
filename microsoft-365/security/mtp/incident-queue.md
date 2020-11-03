---
title: Microsoft 365 Defender의 문제점 우선 순위 지정
description: Microsoft 365 Defender의 인시던트 큐에서 인시던트의 우선 순위를 지정 하는 방법을 알아봅니다.
keywords: 사고, 큐, 개요, 장치, 식별, 사용자, 사서함, 전자 메일, 사고
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846715"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="1346a-104">Microsoft 365 Defender의 문제점 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="1346a-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1346a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1346a-105">**Applies to:**</span></span>
- <span data-ttu-id="1346a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1346a-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="1346a-107">Microsoft 365 Defender는 상관 분석을 적용 하 고 다양 한 제품의 모든 관련 알림과 조사를 하나의 인시던트로 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="1346a-108">Microsoft 365 Defender는 또한 Microsoft 365 Defender가 전체 부동산 및 제품군에 걸쳐 있는 종단 간 가시성과 함께 악의적으로 식별 될 수 있는 작업에 대 한 고유한 경고를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="1346a-109">이를 통해 Microsoft 365 Defender는 보다 폭넓은 공격 영역을 narrates, 보안 작업 분석가가 조직 전체에서 복잡 한 위협을 이해 하 고 처리할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="1346a-110">**사고 큐** 는 장치, 사용자 및 사서함에 대해 플래그가 지정 된 사고의 모음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="1346a-111">이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![사고 큐의 이미지](../../media/incidents-queue.png) 

<span data-ttu-id="1346a-113">기본적으로 Microsoft 365 보안 센터의 큐에는\ 최근 30일 동안 발생한 사고가 표시 되며, 최신 사고가 목록의 맨 위에 표시 되어 최신 사고를 가장 먼저 확인 할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1346a-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="1346a-114">사고 큐는 사고나 사고 관련 항목을 알려주는 커스터마이징이 가능한 열을 보여줌으로써 사고 처리 우선수위를 결정하는데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="1346a-115">보다 쉽게 확인할 수 있도록, 자동 인시던트 명명은 영향을 받는 끝점 (예: 사용자에 게 영향을 받음, 검색 원본 또는 범주)와 같은 경고 특성을 기반으로 하는 인시던트 이름을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="1346a-116">이를 통해 사고의 범위를 빠르게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="1346a-117">예를 들어 *여러 출처에서 보고 하는 여러 끝점에 대 한 다단계 인시던트가 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="1346a-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="1346a-118">자동 인시던트 이름 지정 롤아웃 이전에 존재 했던 인시던트는 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="1346a-119">또한 사고 큐는 여러 개의 필터링 옵션을 제공 합니다. 이 옵션을 적용 하면 환경이 허용하는 모든 기존 사고에 대한 광범위 한 스위프를 수행 하도록 선택 하거나 특정 시나리오 또는 위협에 집중할 수 있도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="1346a-120">사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="1346a-121">사용 가능한 필터</span><span class="sxs-lookup"><span data-stu-id="1346a-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="1346a-122">상태</span><span class="sxs-lookup"><span data-stu-id="1346a-122">Status</span></span>
<span data-ttu-id="1346a-123">상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="1346a-124">심각도</span><span class="sxs-lookup"><span data-stu-id="1346a-124">Severity</span></span>
<span data-ttu-id="1346a-125">사고의 심각도는 자산에 미칠 수 있는 영향을 의미합니다. </span><span class="sxs-lookup"><span data-stu-id="1346a-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="1346a-126">심각도가 높아지면 영향을 크게 받게 되므로 일반적으로 가장 즉각적으로 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="1346a-127">담당자(소유자)</span><span class="sxs-lookup"><span data-stu-id="1346a-127">Assigned to (owner)</span></span>
<span data-ttu-id="1346a-128">필터를 사용하여 특정 담당자에게 할당 된 목록이나 자신에게 할당된 목록을 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1346a-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="1346a-129">다중 경고 </span><span class="sxs-lookup"><span data-stu-id="1346a-129">Multiple alerts</span></span> 
<span data-ttu-id="1346a-130">하나 이상의 경고를 포함 하는 사고만 표시 하도록 필터링 할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1346a-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="1346a-131">이는 보다 복잡하거나 진화된 킬체인 공격일 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1346a-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="1346a-132">다중 서비스 원인</span><span class="sxs-lookup"><span data-stu-id="1346a-132">Multiple service sources</span></span> 
<span data-ttu-id="1346a-133">서로 다른 원본 (끝점에 대 한 Microsoft Defender, Microsoft Cloud App Security, Id 용 microsoft defender, Office 365 용 Microsoft Defender)의 경고가 포함 된 인시던트만 표시 되도록 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365)</span></span>
### <a name="service-sources"></a><span data-ttu-id="1346a-134">서비스 원인</span><span class="sxs-lookup"><span data-stu-id="1346a-134">Service sources</span></span>
<span data-ttu-id="1346a-135">특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="1346a-136">다중 범주</span><span class="sxs-lookup"><span data-stu-id="1346a-136">Multiple categories</span></span> 
<span data-ttu-id="1346a-137">킬체인의 다중 범주에 매핑된 사고 및 잠재적으로 더 큰 손상을 유발할만한 사고를 선택해서 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="1346a-138">범주</span><span class="sxs-lookup"><span data-stu-id="1346a-138">Categories</span></span>
<span data-ttu-id="1346a-139">범주를 선택 하여 킬체인 특정 단계에 집중할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1346a-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="1346a-140">데이터 민감도</span><span class="sxs-lookup"><span data-stu-id="1346a-140">Data sensitivity</span></span>
<span data-ttu-id="1346a-141">일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다. </span><span class="sxs-lookup"><span data-stu-id="1346a-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="1346a-142">필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="1346a-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="1346a-143">Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1346a-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="1346a-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1346a-144">Next steps</span></span>
<span data-ttu-id="1346a-145">사고의 우선순위를 결정한 뒤 사고에 대한 조사를 진행할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1346a-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="1346a-146">사고 조사</span><span class="sxs-lookup"><span data-stu-id="1346a-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="1346a-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1346a-147">Related topics</span></span>
- [<span data-ttu-id="1346a-148">사고 개요</span><span class="sxs-lookup"><span data-stu-id="1346a-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1346a-149">사고 조사</span><span class="sxs-lookup"><span data-stu-id="1346a-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="1346a-150">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="1346a-150">Manage incidents</span></span>](manage-incidents.md)
