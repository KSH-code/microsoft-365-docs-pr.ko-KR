---
title: Microsoft 365 Defender에서 인시던트 관리
description: 상태, 인시던트, 경고, 연관된 경고, 할당, 업데이트, 상태, 관리, 분류, microsoft, 365, m365를
keywords: 할당하고 업데이트하는 방법을 알아봅니다.인시던트, 인시던트, 경고, 연관 되는 경고, 할당, 업데이트, 상태, 관리, 분류, microsoft, 365, m365
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
ms.openlocfilehash: 72d368cd92739e191dcb292000b8429a472aa981
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498444"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="b4558-104">Microsoft 365 Defender에서 인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="b4558-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b4558-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b4558-105">**Applies to:**</span></span>
- <span data-ttu-id="b4558-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4558-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="b4558-107">인시던트 관리는 위협이 포함되어 있고 해결되었는지 확인하는 데 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="b4558-108">Microsoft 365 Defender에서 장치, 사용자 및 사서함의 인시던트 관리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-108">In Microsoft 365 Defender, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="b4558-109">**인시던트 큐** 에서 인시던트를 선택하여 인시던트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="b4558-110">인시던트의 이름을 편집하고 문제를 해결하며 분류 및 결정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="b4558-111">인시던트를 자신에게 할당하고 인시던트 태그와 메모를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="b4558-112">조사 중에 한 인시던트의 알림을 다른 인시던트로 이동하려는 경우, 모든 관련된 알림이 포함된 더 크거나 작은 인시던트를 만들어 알림 탭에서 해당 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="b4558-113">인시던트 이름 편집</span><span class="sxs-lookup"><span data-stu-id="b4558-113">Edit incident name</span></span>
<span data-ttu-id="b4558-114">인시던트에는 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 이름이 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="b4558-115">이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="b4558-116">예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*</span><span class="sxs-lookup"><span data-stu-id="b4558-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="b4558-117">기본 명명 규칙에 맞게 인시던트 이름을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="b4558-118">자동 인시던트 명명 기능을 출시하기 전에 존재한 인시던트의 이름은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="b4558-119">인시던트 할당</span><span class="sxs-lookup"><span data-stu-id="b4558-119">Assign incidents</span></span>
<span data-ttu-id="b4558-120">아직 인시던트가 할당되지 않은 경우 **나에게 할당** 을 선택하여 인시던트를 자신에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="b4558-121">이렇게 하면 인시던트뿐만 아니라, 관련된 모든 알림의 소유권을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="b4558-122">상태 및 분류 설정</span><span class="sxs-lookup"><span data-stu-id="b4558-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="b4558-123">인시던트 상태</span><span class="sxs-lookup"><span data-stu-id="b4558-123">Incident status</span></span>
<span data-ttu-id="b4558-124">조사가 진행됨에 따라 상태를 변경하여 인시던트(**활성** 또는 **해결됨**)를 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="b4558-125">이렇게 하면 팀에서 인시더트에 대한 대응 방법을 구성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="b4558-126">예를 들어, SOC 분석가가 해당 일의 긴급한 **활성** 인시던트를 검토하고 조사를 위해 자신에게 인시던트를 할당할 수 있습니다.ㅎ</span><span class="sxs-lookup"><span data-stu-id="b4558-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="b4558-127">또는, 인시던트가 조정된 경우 SOC 분석가가 인시던트를 **해결됨** 으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="b4558-128">문제를 해결하면 인시던트의 일부이며 계속 열려 있는 모든 알림이 자동으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="b4558-129">분류 및 결정</span><span class="sxs-lookup"><span data-stu-id="b4558-129">Classification and determination</span></span>
<span data-ttu-id="b4558-130">분류를 설정하지 않도록 선택하거나 인시던트가 true 또는 false인지 여부를 지정하도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="b4558-131">이렇게 하면 팀에서 패턴을 보고 해당 정보에서 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="b4558-132">메모 추가</span><span class="sxs-lookup"><span data-stu-id="b4558-132">Add comments</span></span>
<span data-ttu-id="b4558-133">인시던트에 대한 메모를 추가하고 기록 이벤트를 보고 이전에 변경한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="b4558-134">알림에 대해 변경 사항이나 메모가 작성될 때마다, 해당 내용이 메모 및 기록 섹션에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="b4558-135">추가된 메모는 창에 바로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="b4558-136">인시던트 태그 추가</span><span class="sxs-lookup"><span data-stu-id="b4558-136">Add incident tags</span></span>
<span data-ttu-id="b4558-137">인시던트에 사용자 지정 태그를 추가할 수 있습니다. 예를 들어 인시던트 그룹에 공통적인 특성이 있는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="b4558-138">나중에 특정 태그가 포함된 모든 인시던트의 인시던트 큐를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4558-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
