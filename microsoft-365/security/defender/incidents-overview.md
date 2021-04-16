---
title: Microsoft 365 Defender의 인시던트
description: 여러 장치, 사용자 및 사서함에 표시되는 인시던트를 조사합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
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
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861626"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="ea49d-104">Microsoft 365 Defender의 인시던트</span><span class="sxs-lookup"><span data-stu-id="ea49d-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ea49d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ea49d-105">**Applies to:**</span></span>
- <span data-ttu-id="ea49d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea49d-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="ea49d-107">Microsoft 365 Defender를 경험해 보고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="ea49d-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="ea49d-108">[랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="ea49d-109">Microsoft 365 Defender의 인시던트는 공격의 스토리를 만드는 상관 관계 있는 경고 및 관련 데이터의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="ea49d-110">Microsoft 365 서비스 및 앱은 의심스러운 또는 악의적인 이벤트 또는 활동을 감지할 때 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="ea49d-111">개별 경고는 완료되거나 지속적인 공격에 대한 중요한 단서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="ea49d-112">그러나 공격은 일반적으로 장치, 사용자 및 사서함과 같은 다양한 유형의 엔터티에 대해 다양한 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="ea49d-113">그 결과 테넌트의 여러 엔터티에 대한 여러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="ea49d-114">개별 경고를 함께 하여 공격에 대한 통찰력을 확보하는 것은 어렵고 시간이 많이 소요될 수 있기 때문에 Microsoft 365 Defender는 경고 및 관련 정보를 인시던트에 자동으로 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender가 엔터티의 이벤트를 인시던트와 상관 관계 지정하는 방법":::

<span data-ttu-id="ea49d-116">Microsoft 365 Defender의 인시던트에 대한 간략한 개요(4분)를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="ea49d-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="ea49d-117">관련 경고를 인시던트로 그룹화하면 공격을 포괄적으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="ea49d-118">예를 들어 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-118">For example, you can see:</span></span>

- <span data-ttu-id="ea49d-119">공격이 시작된 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-119">Where the attack started.</span></span>
- <span data-ttu-id="ea49d-120">사용된 전술</span><span class="sxs-lookup"><span data-stu-id="ea49d-120">What tactics were used.</span></span>
- <span data-ttu-id="ea49d-121">공격이 테넌트에 얼마나 들어갔는가.</span><span class="sxs-lookup"><span data-stu-id="ea49d-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="ea49d-122">공격 범위(예: 영향을 받는 장치, 사용자 및 사서함 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="ea49d-123">공격과 관련된 모든 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="ea49d-124">[활성화된](m365d-enable.md)경우 Microsoft 365 Defender는 자동화 및 인공 지능을 통해 경고를 자동으로 조사하고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="ea49d-125">추가 수정 단계를 수행하여 공격을 해결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="ea49d-126">Microsoft 365 보안 센터의 인시던트 및 경고</span><span class="sxs-lookup"><span data-stu-id="ea49d-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="ea49d-127">Microsoft 365 보안 센터(&)의 > 인시던트 및 인시던트 경고에서 인시던트 security.microsoft.com[관리합니다.](https://security.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="ea49d-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="ea49d-128">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 보안 센터의 인시던트 페이지":::

<span data-ttu-id="ea49d-130">인시던트 이름을 선택하면 인시던트 요약이 표시될 수 있으며 추가 정보가 있는 탭에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 보안 센터의 인시던트에 대한 요약 페이지 예":::

<span data-ttu-id="ea49d-132">인시던트에 대한 추가 탭은:</span><span class="sxs-lookup"><span data-stu-id="ea49d-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="ea49d-133">경고</span><span class="sxs-lookup"><span data-stu-id="ea49d-133">Alerts</span></span> 

  <span data-ttu-id="ea49d-134">인시던트 및 해당 정보와 관련된 모든 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="ea49d-135">디바이스</span><span class="sxs-lookup"><span data-stu-id="ea49d-135">Devices</span></span>

  <span data-ttu-id="ea49d-136">인시던트의 일부로 식별되거나 인시던트와 관련된 모든 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="ea49d-137">사용자</span><span class="sxs-lookup"><span data-stu-id="ea49d-137">Users</span></span>

  <span data-ttu-id="ea49d-138">인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="ea49d-139">사서함</span><span class="sxs-lookup"><span data-stu-id="ea49d-139">Mailboxes</span></span>

  <span data-ttu-id="ea49d-140">인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="ea49d-141">조사</span><span class="sxs-lookup"><span data-stu-id="ea49d-141">Investigations</span></span>

  <span data-ttu-id="ea49d-142">인시던트의 경고에 의해 트리거된 모든 자동화된 조사.</span><span class="sxs-lookup"><span data-stu-id="ea49d-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="ea49d-143">증거 및 응답</span><span class="sxs-lookup"><span data-stu-id="ea49d-143">Evidence and Response</span></span>

  <span data-ttu-id="ea49d-144">인시던트의 경고에서 지원되는 모든 이벤트 및 의심스러운 엔터티</span><span class="sxs-lookup"><span data-stu-id="ea49d-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="ea49d-145">다음은 인시던트와 인시던트 데이터 및 Microsoft 365 보안 센터의 인시던트 탭 간의 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Microsoft 365 보안 센터에서 인시던트와 인시던트의 데이터와 인시던트의 관계":::

## <a name="next-step"></a><span data-ttu-id="ea49d-147">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ea49d-147">Next step</span></span>

<span data-ttu-id="ea49d-148">인시던트  페이지의 인시던트 큐에 최근 인시던트가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="ea49d-149">여기에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-149">From here, you can:</span></span>

- <span data-ttu-id="ea49d-150">심각도 및 기타 [](incident-queue.md) 요인에 따라 우선 순위를 지정해야 하는 사고를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="ea49d-151">[인시던트에 대한](investigate-incidents.md) 조사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="ea49d-152">[인시던트](manage-incidents.md)관리 를 관리합니다. 여기에는 인시던트 이름 변경, 할당, 분류 및 인시던트 관리 워크플로에 대한 태그 추가가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea49d-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
