---
title: Microsoft Threat Protection 사고 우선순위
description: Microsoft Threat Protection의 사고 큐에서 우선 순위를 지정 하는 방법을 알아봅니다.
keywords: 사고, 큐, 개요, 장치, 식별, 사용자, 사서함, 전자 메일, 사고
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 0c4231fa6284d967bcc49e4d46b0869c57733443
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911431"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="1ecab-104">Microsoft Threat Protection 사고 우선순위</span><span class="sxs-lookup"><span data-stu-id="1ecab-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="1ecab-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1ecab-105">**Applies to:**</span></span>
- <span data-ttu-id="1ecab-106">Microsoft Threat Protection </span><span class="sxs-lookup"><span data-stu-id="1ecab-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="1ecab-107">Microsoft Threat Protection은 상관 관계 분석을 하고 관련된 모든 알람을 수집한 뒤 각각의 다른 제품에서 발생한 알람을 하나의 사고로 조사합니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="1ecab-108">Microsoft Threat Protection 전체 항목 및 제품군 엔드 투 엔드 가시성에서 악성으로 판단된 작업에 대해서는 특별 알람을 발생시킵니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="1ecab-109">Microsoft Threat Protection은 보다 광범위한 공격내용을 구연함으로써 보안 운영 분석가가 조직 전반을 위협하는 복잡한 공격을 이해하고 처리할 수 있도록 합니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="1ecab-110">**사고 큐**는 장치, 사용자 및 사서함에 대해 플래그가 지정 된 사고의 모음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="1ecab-111">이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![사고 큐의 이미지](../images/incidents-queue.png) 

<span data-ttu-id="1ecab-113">기본적으로 Microsoft 365 보안 센터의 큐에는\ 최근 30일 동안 발생한 사고가 표시 되며, 최신 사고가 목록의 맨 위에 표시 되어 최신 사고를 가장 먼저 확인 할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="1ecab-114">사고 큐는 사고나 사고 관련 항목을 알려주는 커스터마이징이 가능한 열을 보여줌으로써 사고 처리 우선수위를 결정하는데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span> 

<span data-ttu-id="1ecab-115">또한 사고 큐는 여러 개의 필터링 옵션을 제공 합니다. 이 옵션을 적용 하면 환경이 허용하는 모든 기존 사고에 대한 광범위 한 스위프를 수행 하도록 선택 하거나 특정 시나리오 또는 위협에 집중할 수 있도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-115">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="1ecab-116">사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-116">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="1ecab-117">사용 가능한 필터</span><span class="sxs-lookup"><span data-stu-id="1ecab-117">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="1ecab-118">상태</span><span class="sxs-lookup"><span data-stu-id="1ecab-118">Status</span></span>
<span data-ttu-id="1ecab-119">상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-119">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="1ecab-120">심각도</span><span class="sxs-lookup"><span data-stu-id="1ecab-120">Severity</span></span>
<span data-ttu-id="1ecab-121">사고의 심각도는 자산에 미칠 수 있는 영향을 의미합니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-121">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="1ecab-122">심각도가 높아지면 영향을 크게 받게 되므로 일반적으로 가장 즉각적으로 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-122">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="1ecab-123">담당자(소유자)</span><span class="sxs-lookup"><span data-stu-id="1ecab-123">Assigned to (owner)</span></span>
<span data-ttu-id="1ecab-124">필터를 사용하여 특정 담당자에게 할당 된 목록이나 자신에게 할당된 목록을 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-124">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="1ecab-125">다중 경고 </span><span class="sxs-lookup"><span data-stu-id="1ecab-125">Multiple alerts</span></span> 
<span data-ttu-id="1ecab-126">하나 이상의 경고를 포함 하는 사고만 표시 하도록 필터링 할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-126">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="1ecab-127">이는 보다 복잡하거나 진화된 킬체인 공격일 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-127">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="1ecab-128">다중 서비스 원인</span><span class="sxs-lookup"><span data-stu-id="1ecab-128">Multiple service sources</span></span> 
<span data-ttu-id="1ecab-129">다중 원인(Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP) 알림이 포함 된 사고만 표시 하도록 필터링 할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-129">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="1ecab-130">서비스 원인</span><span class="sxs-lookup"><span data-stu-id="1ecab-130">Service sources</span></span>
<span data-ttu-id="1ecab-131">특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-131">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="1ecab-132">다중 범주</span><span class="sxs-lookup"><span data-stu-id="1ecab-132">Multiple categories are supported.</span></span> 
<span data-ttu-id="1ecab-133">킬체인의 다중 범주에 매핑된 사고 및 잠재적으로 더 큰 손상을 유발할만한 사고를 선택해서 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-133">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="1ecab-134">범주</span><span class="sxs-lookup"><span data-stu-id="1ecab-134">Categories</span></span>
<span data-ttu-id="1ecab-135">범주를 선택 하여 킬체인 특정 단계에 집중할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-135">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="1ecab-136">데이터 민감도</span><span class="sxs-lookup"><span data-stu-id="1ecab-136">Data sensitivity</span></span>
<span data-ttu-id="1ecab-137">일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-137">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="1ecab-138">필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="1ecab-138">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="1ecab-139">Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ecab-139">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="1ecab-140">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1ecab-140">Next steps</span></span>
<span data-ttu-id="1ecab-141">사고의 우선순위를 결정한 뒤 사고에 대한 조사를 진행할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1ecab-141">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="1ecab-142">사고 조사</span><span class="sxs-lookup"><span data-stu-id="1ecab-142">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="1ecab-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1ecab-143">Related topics</span></span>
- [<span data-ttu-id="1ecab-144">사고 개요</span><span class="sxs-lookup"><span data-stu-id="1ecab-144">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1ecab-145">사고 조사</span><span class="sxs-lookup"><span data-stu-id="1ecab-145">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="1ecab-146">사고 관리</span><span class="sxs-lookup"><span data-stu-id="1ecab-146">Manage incidents</span></span>](manage-incidents.md)