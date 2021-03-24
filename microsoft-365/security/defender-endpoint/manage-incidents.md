---
title: Microsoft Defender ATP 인시던트 관리
description: 인시던트 할당, 상태 업데이트 또는 분류 설정으로 인시던트 관리
keywords: 인시던트, 관리, 할당, 상태, 분류, 참 경고, 거짓 경고
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 412938e506895aaabfa0796cb1d46ea892876435
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070191"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="811f7-104">끝점 인시던트에 대한 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="811f7-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="811f7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="811f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="811f7-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="811f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="811f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="811f7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="811f7-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="811f7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="811f7-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="811f7-110">인시던트 관리는 모든 사이버 보안 작업의 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="811f7-111">인시던트 큐 또는 인시던트 관리 창에서 인시던트 를 선택하여 인시던트 **관리를 할 수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="811f7-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="811f7-112">인시던트 큐에서 인시던트를 선택하면 인시던트 관리 창이 표시되어 자세한 내용을 볼 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="811f7-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![인시던트 관리 창의 이미지](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="811f7-114">인시던트는 사용자에게 할당하거나, 상태 및 분류를 변경하거나, 이름을 바꾸거나, 설명을 추가하여 진행 상황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="811f7-115">추가 가시성을 위해 인시던트 이름은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="811f7-116">이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="811f7-117">예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*</span><span class="sxs-lookup"><span data-stu-id="811f7-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="811f7-118">자동 인시던트 명명을 출시하기 전에 존재한 인시던트의 이름은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![인시던트 세부 정보 페이지의 이미지](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="811f7-120">인시던트 할당</span><span class="sxs-lookup"><span data-stu-id="811f7-120">Assign incidents</span></span>
<span data-ttu-id="811f7-121">인시던트가 아직 할당되지 않은  경우 할당을 선택하여 인시던트가 사용자에게 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="811f7-122">이렇게 하면 인시던트뿐만 아니라, 관련된 모든 알림의 소유권을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="811f7-123">상태 및 분류 설정</span><span class="sxs-lookup"><span data-stu-id="811f7-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="811f7-124">인시던트 상태</span><span class="sxs-lookup"><span data-stu-id="811f7-124">Incident status</span></span>
<span data-ttu-id="811f7-125">조사가 진행됨에 따라 상태를 변경하여 인시던트(**활성** 또는 **해결됨**)를 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="811f7-126">이렇게 하면 팀에서 인시더트에 대한 대응 방법을 구성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="811f7-127">예를 들어 SoC 분석가가 해당  일에 대한 긴급한 활성 인시던트들을 검토하고 조사를 위해 자신을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="811f7-128">또는 인시던트가 수정된 경우  SoC 분석가가 인시던트 해결로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="811f7-129">분류</span><span class="sxs-lookup"><span data-stu-id="811f7-129">Classification</span></span>
<span data-ttu-id="811f7-130">분류를 설정하지 않도록 선택하거나 인시던트가 true 또는 false인지 여부를 지정하도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="811f7-131">이렇게 하면 팀에서 패턴을 보고 해당 정보에서 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="811f7-132">메모 추가</span><span class="sxs-lookup"><span data-stu-id="811f7-132">Add comments</span></span>
<span data-ttu-id="811f7-133">인시던트에 대한 메모를 추가하고 기록 이벤트를 보고 이전에 변경한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="811f7-134">알림에 대해 변경 사항이나 메모가 작성될 때마다, 해당 내용이 메모 및 기록 섹션에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="811f7-135">추가된 메모는 창에 바로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="811f7-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="811f7-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="811f7-136">Related topics</span></span>
- [<span data-ttu-id="811f7-137">인시던트 큐</span><span class="sxs-lookup"><span data-stu-id="811f7-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="811f7-138">인시던트 큐 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="811f7-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="811f7-139">사고 조사</span><span class="sxs-lookup"><span data-stu-id="811f7-139">Investigate incidents</span></span>](investigate-incidents.md)
