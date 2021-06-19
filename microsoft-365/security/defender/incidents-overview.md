---
title: 인시던트 Microsoft 365 Defender
description: 사이트 포털에서 장치, 사용자 및 사서함에 걸쳐 볼 수 있는 인시던트 Microsoft 365 Defender 조사합니다.
keywords: 인시던트, 경고, 조사, 분석, 대응, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365, 인시던트 대응, 사이버 공격
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
ms.openlocfilehash: b6830c77a0c5cc93ea202844a8793c5f69f07650
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028526"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="fc2c0-104">인시던트 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc2c0-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fc2c0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fc2c0-105">**Applies to:**</span></span>
- <span data-ttu-id="fc2c0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc2c0-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="fc2c0-107">Microsoft 365 Defender를 경험해 보고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="fc2c0-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="fc2c0-108">[랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="fc2c0-109">이 Microsoft 365 Defender 인시던트는 공격의 스토리를 만드는 상호 관련된 경고 및 관련 데이터의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="fc2c0-110">Microsoft 365 및 앱은 의심스러우거나 악의적인 이벤트나 활동을 감지할 때 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="fc2c0-111">개별 경고는 완료되거나 지속적인 공격에 대한 중요한 단서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="fc2c0-112">그러나 공격은 일반적으로 장치, 사용자 및 사서함과 같은 다양한 유형의 엔터티에 대해 다양한 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="fc2c0-113">그 결과 테넌트의 여러 엔터티에 대한 여러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="fc2c0-114">개별 경고를 함께 하여 공격에 대한 통찰력을 확보하는 것은 까다롭고 시간이 많이 소요될 수 Microsoft 365 Defender 경고 및 관련 정보를 인시던트에 자동으로 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender 이벤트와 인시던트의 상관 관계 지정 방법":::

<span data-ttu-id="fc2c0-116">4분 동안의 인시던트에 대한 Microsoft 365 Defender 간략한 개요를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="fc2c0-117">관련 경고를 인시던트로 그룹화하면 공격을 포괄적으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="fc2c0-118">예를 들어 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-118">For example, you can see:</span></span>

- <span data-ttu-id="fc2c0-119">공격이 시작된 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-119">Where the attack started.</span></span>
- <span data-ttu-id="fc2c0-120">사용된 전술</span><span class="sxs-lookup"><span data-stu-id="fc2c0-120">What tactics were used.</span></span>
- <span data-ttu-id="fc2c0-121">공격이 테넌트에 얼마나 들어갔는가.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="fc2c0-122">공격 범위(예: 영향을 받는 장치, 사용자 및 사서함 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="fc2c0-123">공격과 관련된 모든 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="fc2c0-124">이 [옵션을](m365d-enable.md)Microsoft 365 Defender 자동화 [](m365d-autoir.md) 및 인공 지능을 통해 경고를 자동으로 조사하고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="fc2c0-125">추가 수정 단계를 수행하여 공격을 해결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="fc2c0-126">사이트 포털의 인시던트 Microsoft 365 Defender 알림</span><span class="sxs-lookup"><span data-stu-id="fc2c0-126">Incidents and alerts in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="fc2c0-127">인시던트  및 인시던트 & 포털(>)의 빠른 실행에서 인시던트 Microsoft 365 Defender 관리합니다 security.microsoft.com.[](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="fc2c0-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="fc2c0-128">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="사이트 포털의 인시던트 Microsoft 365 Defender 페이지":::

<span data-ttu-id="fc2c0-130">인시던트 이름을 선택하면 인시던트 요약이 표시될 수 있으며 추가 정보가 있는 탭에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="사이트 포털의 인시던트에 대한 요약 Microsoft 365 Defender 예":::

<span data-ttu-id="fc2c0-132">인시던트에 대한 추가 탭은:</span><span class="sxs-lookup"><span data-stu-id="fc2c0-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="fc2c0-133">경고</span><span class="sxs-lookup"><span data-stu-id="fc2c0-133">Alerts</span></span> 

  <span data-ttu-id="fc2c0-134">인시던트 및 해당 정보와 관련된 모든 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="fc2c0-135">디바이스</span><span class="sxs-lookup"><span data-stu-id="fc2c0-135">Devices</span></span>

  <span data-ttu-id="fc2c0-136">인시던트의 일부로 식별되거나 인시던트와 관련된 모든 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="fc2c0-137">사용자</span><span class="sxs-lookup"><span data-stu-id="fc2c0-137">Users</span></span>

  <span data-ttu-id="fc2c0-138">인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="fc2c0-139">사서함</span><span class="sxs-lookup"><span data-stu-id="fc2c0-139">Mailboxes</span></span>

  <span data-ttu-id="fc2c0-140">인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="fc2c0-141">조사</span><span class="sxs-lookup"><span data-stu-id="fc2c0-141">Investigations</span></span>

  <span data-ttu-id="fc2c0-142">[인시던트의](m365d-autoir.md) 경고에 의해 트리거된 모든 자동화된 조사.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="fc2c0-143">증거 및 응답</span><span class="sxs-lookup"><span data-stu-id="fc2c0-143">Evidence and Response</span></span>

  <span data-ttu-id="fc2c0-144">인시던트의 경고에서 지원되는 모든 이벤트 및 의심스러운 엔터티</span><span class="sxs-lookup"><span data-stu-id="fc2c0-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="fc2c0-145">Graph(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="fc2c0-145">Graph (in preview)</span></span>

  <span data-ttu-id="fc2c0-146">조직의 영향을 미치는 자산에 대한 경고의 연결을 보여 미치는 그림입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="fc2c0-147">다음은 인시던트와 인시던트 데이터 및 인시던트 포털에서 인시던트의 탭 Microsoft 365 Defender 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="인시던트 및 데이터와 인시던트 포털의 인시던트 탭 간의 Microsoft 365 Defender 관계":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="fc2c0-149">예제 인시던트 대응 워크플로를 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc2c0-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="fc2c0-150">다음은 Microsoft 365 포털을 사용하여 인시던트에 응답하기 위한 Microsoft 365 Defender 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="인시던트 대응 워크플로의 Microsoft 365":::

<span data-ttu-id="fc2c0-152">지속적인 기준에 따라 인시던트 큐에서 분석 및 해결을 위해 우선 순위가 가장 높은 인시던트를 식별하고 대응을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="fc2c0-153">이 조합은</span><span class="sxs-lookup"><span data-stu-id="fc2c0-153">This is a combination of:</span></span>

- <span data-ttu-id="fc2c0-154">[인시던트](incident-queue.md) 큐 필터링 및 정렬을 통해 우선 순위가 가장 높은 인시던트 결정</span><span class="sxs-lookup"><span data-stu-id="fc2c0-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="fc2c0-155">[직위를](manage-incidents.md) 수정하고, 분석가에게 할당하고, 태그와 설명을 추가하여 인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="fc2c0-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="fc2c0-156">각 인시던트에 대해 [공격을 시작하고 조사 및 분석을 경고합니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="fc2c0-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   1. <span data-ttu-id="fc2c0-157">인시던트의 요약을 보고 인시던트의 범위 및 심각도와 영향을  받는 엔터티(요약 탭)를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-157">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   1. <span data-ttu-id="fc2c0-158">경고의 출처, 범위 및 심각도(경고 탭)를  이해하기 위해 경고 분석을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   1. <span data-ttu-id="fc2c0-159">필요한 경우 영향을 받는 장치, 사용자 및 사서함(장치, 사용자 및 사서함 탭)에 대한 **정보를** 수집합니다. </span><span class="sxs-lookup"><span data-stu-id="fc2c0-159">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   1. <span data-ttu-id="fc2c0-160">일부 Microsoft 365 Defender 자동으로 해결한 방법(조사 탭)을 **참조합니다.** [](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="fc2c0-160">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   1. <span data-ttu-id="fc2c0-161">필요한 경우 인시던트에 대한 데이터 집합의 정보를 사용하여 자세한 정보(증거 및 응답 **탭)를 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc2c0-161">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="fc2c0-162">분석 후 또는 분석 중에 포함을 수행하여 보안 위협의 공격 및 제거에 대한 추가 영향을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-162">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="fc2c0-163">테넌트 리소스를 인시던트 이전 상태로 복원하여 공격으로부터 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-163">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="fc2c0-164">[인시던트](manage-incidents.md#resolve-an-incident) 문제를 해결하고 인시던트 사후 학습을 통해 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-164">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="fc2c0-165">공격의 유형과 그 영향에 대해 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-165">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="fc2c0-166">[위협](threat-analytics.md) 분석 및 보안 커뮤니티에서 공격을 조사하여 보안 공격 추세를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-166">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="fc2c0-167">인시던트 해결에 사용한 워크플로를 회수하고 필요한 경우 표준 워크플로, 프로세스, 정책 및 플레이북을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-167">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="fc2c0-168">보안 구성의 변경이 필요한지 여부를 결정하고 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-168">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="fc2c0-169">보안 분석이 처음인 경우 [](incidents-overview.md) 추가 정보는 첫 번째 인시던트에 응답하는 소개를 참조하고 인시던트 예제를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-169">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

<span data-ttu-id="fc2c0-170">Microsoft 제품 전반의 인시던트 대응에 대한 자세한 내용은 이 [문서를 참조하세요.](/security/compass/incident-response-overview)</span><span class="sxs-lookup"><span data-stu-id="fc2c0-170">For more information about incident response across Microsoft products, see [this article](/security/compass/incident-response-overview).</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="fc2c0-171">보안 작업의 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc2c0-171">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="fc2c0-172">다음은 보안 작업(SecOps)의 예입니다Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-172">Here's an example of security operations (SecOps) for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="보안 작업의 예로는 Microsoft 365 Defender":::

<span data-ttu-id="fc2c0-174">일별 작업에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-174">Daily tasks can include:</span></span>

- <span data-ttu-id="fc2c0-175">[인시던트](manage-incidents.md) 관리</span><span class="sxs-lookup"><span data-stu-id="fc2c0-175">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="fc2c0-176">관리 [센터에서 자동화된 조사 및 대응(AIR)](m365d-action-center.md) 작업 검토</span><span class="sxs-lookup"><span data-stu-id="fc2c0-176">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="fc2c0-177">최신 위협 [분석 검토](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="fc2c0-177">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="fc2c0-178">[인시던트에](investigate-incidents.md) 응답</span><span class="sxs-lookup"><span data-stu-id="fc2c0-178">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="fc2c0-179">월별 작업에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-179">Monthly tasks can include:</span></span>

- <span data-ttu-id="fc2c0-180">AIR [설정 검토](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="fc2c0-180">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="fc2c0-181">보안 [점수 및](microsoft-secure-score-improvement-actions.md) 위협 요소 [& 관리 검토](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="fc2c0-181">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="fc2c0-182">IT 보안 관리 체인에 보고</span><span class="sxs-lookup"><span data-stu-id="fc2c0-182">Reporting to your IT security management chain</span></span>

<span data-ttu-id="fc2c0-183">분기별 작업에는 CISO(최고 정보 보안 책임자)에게 보안 결과를 보고하고 브리핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-183">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="fc2c0-184">연간 작업에는 직원, 시스템 및 프로세스를 테스트하기 위한 주요 인시던트 또는 위반 연습 수행이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-184">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="fc2c0-185">매일, 월별, 분기별 및 연간 작업을 사용하여 프로세스, 정책 및 보안 구성을 업데이트하거나 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-185">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

### <a name="secops-resources-across-microsoft-products"></a><span data-ttu-id="fc2c0-186">Microsoft 제품 전반의 SecOps 리소스</span><span class="sxs-lookup"><span data-stu-id="fc2c0-186">SecOps resources across Microsoft products</span></span>

<span data-ttu-id="fc2c0-187">Microsoft 제품 전반의 SecOps에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-187">For more information about SecOps across Microsoft's products, see these resources:</span></span>

- [<span data-ttu-id="fc2c0-188">기능</span><span class="sxs-lookup"><span data-stu-id="fc2c0-188">Capabilities</span></span>](/security/compass/security-operations-capabilities)
- [<span data-ttu-id="fc2c0-189">모범 사례</span><span class="sxs-lookup"><span data-stu-id="fc2c0-189">Best practices</span></span>](/security/compass/security-operations)
- [<span data-ttu-id="fc2c0-190">비디오 및 슬라이드</span><span class="sxs-lookup"><span data-stu-id="fc2c0-190">Videos and slides</span></span>](/security/compass/security-operations-videos-and-decks)

## <a name="next-steps"></a><span data-ttu-id="fc2c0-191">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fc2c0-191">Next steps</span></span>

<span data-ttu-id="fc2c0-192">**보안 분석 및 인시던트** 대응이 새로운 경우:</span><span class="sxs-lookup"><span data-stu-id="fc2c0-192">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="fc2c0-193">예제 [](first-incident-overview.md) 공격을 통해 Microsoft 365 Defender 포털에서 일반적인 분석, 수정 및 사후 인시던트 검토 프로세스를 안내하는 안내를 받을 수 있는 첫 번째 인시던트에 응답 안내를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-193">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 Defender portal with an example attack.</span></span>

<span data-ttu-id="fc2c0-194">**보안 분석 및 인시던트** 대응 경험이 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="fc2c0-194">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="fc2c0-195">사이트 포털의 인시던트  페이지에서 인시던트 큐를 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-195">Get started with the incident queue from the **Incidents** page of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="fc2c0-196">여기에서 다음 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-196">From here, you can:</span></span>

  - <span data-ttu-id="fc2c0-197">심각도 및 기타 [](incident-queue.md) 요인에 따라 우선 순위를 지정해야 하는 사고를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-197">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="fc2c0-198">[인시던트](manage-incidents.md)관리 워크플로에 따라 태그 및 설명을 변경, 할당, 분류 및 추가하는 인시던트 관리 를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-198">[Manage incidents](manage-incidents.md), which includes renaming, assigning, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="fc2c0-199">[인시던트 조사를](investigate-incidents.md) 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-199">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="fc2c0-200">[피싱,](/security/compass/incident-response-playbooks) 암호 분사 및 앱 동의 부여 공격에 대한 자세한 지침은 다음 인시던트 대응 플레이북을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc2c0-200">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

