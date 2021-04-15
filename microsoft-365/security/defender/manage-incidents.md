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
ms.openlocfilehash: 2d2bf18c6cacb377e710f34b74ec8f83bb77d3b1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760071"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="24e09-104">Microsoft 365 Defender에서 인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="24e09-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="24e09-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="24e09-105">**Applies to:**</span></span>
- <span data-ttu-id="24e09-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24e09-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="24e09-107">인시던트 관리는 위협이 포함 및 해결될 수 있도록 하는 중요한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="24e09-108">Microsoft 365 보안 센터(&)의 > 인시던트 및 인시던트 경고에서 인시던트 security.microsoft.com[관리합니다.](https://security.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="24e09-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="24e09-109">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="인시던트 큐의 예":::

<span data-ttu-id="24e09-111">인시던트 관리 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-111">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="24e09-112">인시던트 이름 변경</span><span class="sxs-lookup"><span data-stu-id="24e09-112">Change the incident name</span></span>
- <span data-ttu-id="24e09-113">인시던트 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-113">Add incident tags.</span></span>
- <span data-ttu-id="24e09-114">사용자 계정에 인시던트 할당</span><span class="sxs-lookup"><span data-stu-id="24e09-114">Assign the incident to a user account</span></span>
- <span data-ttu-id="24e09-115">해결</span><span class="sxs-lookup"><span data-stu-id="24e09-115">Resolve them</span></span> 
- <span data-ttu-id="24e09-116">분류 및 결정 설정</span><span class="sxs-lookup"><span data-stu-id="24e09-116">Set its classification and determination</span></span>
- <span data-ttu-id="24e09-117">설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-117">Add comments.</span></span>

<span data-ttu-id="24e09-118">인시던트에 대한  인시던트 관리 창에서 인시던트 관리를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="24e09-119">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="인시던트의 인시던트 관리 창 예":::

<span data-ttu-id="24e09-121">이 창은 다음의  문제 관리 링크에서 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="24e09-122">인시던트 큐에 있는 인시던트의 속성 창입니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="24e09-123">**인시던트의** 요약 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="24e09-124">조사하는 동안 경고를 한 인시던트에서 다른 인시던트로 이동하는  경우 경고 탭에서 이를 통해 모든 관련 경고가 포함된 더 크거나 작은 인시던트가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-124">In cases where, while investigating you would like to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="24e09-125">인시던트 이름 편집</span><span class="sxs-lookup"><span data-stu-id="24e09-125">Edit the incident name</span></span>

<span data-ttu-id="24e09-126">인시던트에는 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 이름이 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-126">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="24e09-127">이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="24e09-128">예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*</span><span class="sxs-lookup"><span data-stu-id="24e09-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="24e09-129">문제 관리 창의 인시던트 이름 필드에서 문제 이름을 **편집할 수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="24e09-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="24e09-130">자동 인시던트 명명 기능을 출시하기 전에 존재한 인시던트의 이름은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-130">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="24e09-131">인시던트 태그 추가</span><span class="sxs-lookup"><span data-stu-id="24e09-131">Add incident tags</span></span>

<span data-ttu-id="24e09-132">인시던트에 사용자 지정 태그를 추가할 수 있습니다. 예를 들어 인시던트 그룹에 공통적인 특성이 있는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="24e09-133">나중에 특정 태그가 포함된 모든 인시던트에 대한 인시던트 큐를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="24e09-134">입력을 시작할 때 선택한 태그 목록에서 선택할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="24e09-135">인시던트 할당</span><span class="sxs-lookup"><span data-stu-id="24e09-135">Assign incidents</span></span>

<span data-ttu-id="24e09-136">인시던트가 아직 할당되지 않은  경우 할당을 선택하고 사용자 계정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="24e09-137">이렇게 하면 인시던트 및 인시던트와 연결된 모든 경고의 소유권이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-incident"></a><span data-ttu-id="24e09-138">인시던트 해결</span><span class="sxs-lookup"><span data-stu-id="24e09-138">Resolve incident</span></span>

<span data-ttu-id="24e09-139">인시던트가 수정된 경우 인시던트 해결을 **선택하여** 토글을 오른쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="24e09-140">인시던트 해결을 통해 인시던트와 관련된 연결된 경고 및 활성 경고도 모두 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="24e09-141">해결되지 않은 인시던트가 활성으로 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="24e09-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="24e09-142">분류 및 결정 설정</span><span class="sxs-lookup"><span data-stu-id="24e09-142">Set the classification and determination</span></span>

<span data-ttu-id="24e09-143">인시던트 분류는 실제 경고인지 또는 거짓 경고인지를 분류 필드에서 구성하는 **것입니다.**</span><span class="sxs-lookup"><span data-stu-id="24e09-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="24e09-144">실제 경고인 경우 결정 필드를 사용하여 위협의 유형도 **지정해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="24e09-145">위협 유형을 지정하면 보안 팀이 위협 패턴을 보고 조직을 방어하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="24e09-146">메모 추가</span><span class="sxs-lookup"><span data-stu-id="24e09-146">Add comments</span></span>

<span data-ttu-id="24e09-147">설명 필드를 사용하여 인시던트에 여러 개의 설명을 추가할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="24e09-148">각 설명은 인시던트의 기록 이벤트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-148">Each comment is added to the historical events of the incident.</span></span> <span data-ttu-id="24e09-149">인시던트에 대한 설명과 기록은  요약 페이지의 설명 및 기록 **링크에서 볼 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e09-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>
