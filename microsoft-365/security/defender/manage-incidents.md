---
title: Defender에서 인시던트 Microsoft 365 관리
description: 상태, 인시던트, 경고, 연관된 경고, 할당, 업데이트, 상태, 관리, 분류, microsoft, 365, m365를
keywords: 인시던트, 인시던트, 분석, 대응, 경고, 상관 관계 경고, 할당, 업데이트, 상태, 관리, 분류, Microsoft, 365, m365
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
ms.openlocfilehash: 725e6226a56b3aae3670cde18969afdda1ec1940
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530841"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="6fb71-104">Defender에서 인시던트 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="6fb71-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6fb71-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6fb71-105">**Applies to:**</span></span>
- <span data-ttu-id="6fb71-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fb71-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6fb71-107">인시던트 관리는 위협이 포함 및 해결될 수 있도록 하는 중요한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="6fb71-108">인시던트  및 인시던트 & (>)의 빠른 실행에서 인시던트 및 인시던트 Microsoft 365[관리합니다(](https://security.microsoft.com)security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6fb71-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="6fb71-109">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="인시던트 큐의 예":::

<span data-ttu-id="6fb71-111">인시던트 관리 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-111">Here are the ways you can manage your incidents:</span></span>

- [<span data-ttu-id="6fb71-112">인시던트 이름 편집</span><span class="sxs-lookup"><span data-stu-id="6fb71-112">Edit the incident name</span></span>](#edit-the-incident-name)
- [<span data-ttu-id="6fb71-113">인시던트 태그 추가</span><span class="sxs-lookup"><span data-stu-id="6fb71-113">Add incident tags</span></span>](#add-incident-tags)
- [<span data-ttu-id="6fb71-114">사용자 계정에 인시던트 할당</span><span class="sxs-lookup"><span data-stu-id="6fb71-114">Assign the incident to a user account</span></span>](#assign-incidents)
- [<span data-ttu-id="6fb71-115">해결</span><span class="sxs-lookup"><span data-stu-id="6fb71-115">Resolve them</span></span>](#resolve-an-incident)
- [<span data-ttu-id="6fb71-116">분류 및 결정 설정</span><span class="sxs-lookup"><span data-stu-id="6fb71-116">Set its classification and determination</span></span>](#set-the-classification-and-determination)
- [<span data-ttu-id="6fb71-117">메모 추가</span><span class="sxs-lookup"><span data-stu-id="6fb71-117">Add comments</span></span>](#add-comments)

<span data-ttu-id="6fb71-118">인시던트에 대한  인시던트 관리 창에서 인시던트 관리를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="6fb71-119">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="인시던트의 인시던트 관리 창 예":::

<span data-ttu-id="6fb71-121">이 창은 다음의  문제 관리 링크에서 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="6fb71-122">인시던트 큐에 있는 인시던트의 속성 창입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="6fb71-123">**인시던트의** 요약 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="6fb71-124">한 인시던트에서 다른 인시던트로 경고를 이동하려는  경우 경고 탭에서 알림을 이동하여 모든 관련 알림을 포함하는 더 크거나 작은 인시던트가 생성될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-124">In cases where you want to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="6fb71-125">인시던트 이름 편집</span><span class="sxs-lookup"><span data-stu-id="6fb71-125">Edit the incident name</span></span>

<span data-ttu-id="6fb71-126">Microsoft 365 Defender는 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 이름을 자동으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="6fb71-127">이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="6fb71-128">예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*</span><span class="sxs-lookup"><span data-stu-id="6fb71-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="6fb71-129">문제 관리 창의 인시던트 이름 필드에서 문제 이름을 **편집할 수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="6fb71-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="6fb71-130">자동 인시던트 명명 기능을 출시하기 전에 존재한 인시던트의 이름은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="6fb71-131">인시던트 태그 추가</span><span class="sxs-lookup"><span data-stu-id="6fb71-131">Add incident tags</span></span>

<span data-ttu-id="6fb71-132">인시던트에 사용자 지정 태그를 추가할 수 있습니다. 예를 들어 인시던트 그룹에 공통적인 특성이 있는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="6fb71-133">나중에 특정 태그가 포함된 모든 인시던트에 대한 인시던트 큐를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="6fb71-134">입력을 시작할 때 선택한 태그 목록에서 선택할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="6fb71-135">인시던트 할당</span><span class="sxs-lookup"><span data-stu-id="6fb71-135">Assign incidents</span></span>

<span data-ttu-id="6fb71-136">인시던트가 아직 할당되지 않은  경우 할당을 선택하고 사용자 계정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="6fb71-137">이렇게 하면 인시던트 및 인시던트와 연결된 모든 경고의 소유권이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-an-incident"></a><span data-ttu-id="6fb71-138">인시던트 해결</span><span class="sxs-lookup"><span data-stu-id="6fb71-138">Resolve an incident</span></span>

<span data-ttu-id="6fb71-139">인시던트가 수정된 경우 인시던트 해결을 **선택하여** 토글을 오른쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="6fb71-140">인시던트 해결을 통해 인시던트와 관련된 연결된 경고 및 활성 경고도 모두 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="6fb71-141">해결되지 않은 인시던트가 활성으로 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6fb71-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="6fb71-142">분류 및 결정 설정</span><span class="sxs-lookup"><span data-stu-id="6fb71-142">Set the classification and determination</span></span>

<span data-ttu-id="6fb71-143">인시던트 분류는 실제 경고인지 또는 거짓 경고인지를 분류 필드에서 구성하는 **것입니다.**</span><span class="sxs-lookup"><span data-stu-id="6fb71-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="6fb71-144">실제 경고인 경우 결정 필드를 사용하여 위협의 유형도 **지정해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="6fb71-145">위협 유형을 지정하면 보안 팀이 위협 패턴을 보고 조직을 방어하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="6fb71-146">메모 추가</span><span class="sxs-lookup"><span data-stu-id="6fb71-146">Add comments</span></span>

<span data-ttu-id="6fb71-147">설명 필드를 사용하여 인시던트에 여러 개의 설명을 추가할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="6fb71-148">각 설명은 인시던트의 기록 이벤트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-148">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="6fb71-149">인시던트에 대한 설명과 기록은  요약 페이지의 설명 및 기록 **링크에서 볼 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb71-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6fb71-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6fb71-150">Next steps</span></span>

<span data-ttu-id="6fb71-151">새 인시던트의 경우 조사를 [시작합니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="6fb71-151">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="6fb71-152">In-process 인시던트의 경우 조사를 [계속합니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="6fb71-152">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="6fb71-153">해결된 인시던트의 경우 인시던트 [사후 검토를 수행 합니다.](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="6fb71-153">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6fb71-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fb71-154">See also</span></span>

- [<span data-ttu-id="6fb71-155">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="6fb71-155">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6fb71-156">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="6fb71-156">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="6fb71-157">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="6fb71-157">Investigate incidents</span></span>](investigate-incidents.md)
