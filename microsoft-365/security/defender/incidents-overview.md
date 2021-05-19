---
title: Defender의 Microsoft 365 인시던트
description: 보안 센터에서 장치, 사용자 및 사서함에 Microsoft 365 조사합니다.
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
ms.openlocfilehash: cc2fcd7410c2f3122fb3ce49a40e93bfa0767331
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539026"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="f95dd-104">Defender의 Microsoft 365 인시던트</span><span class="sxs-lookup"><span data-stu-id="f95dd-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f95dd-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f95dd-105">**Applies to:**</span></span>
- <span data-ttu-id="f95dd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f95dd-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="f95dd-107">Microsoft 365 Defender를 경험해 보고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="f95dd-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="f95dd-108">[랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="f95dd-109">Microsoft 365 Defender의 인시던트는 공격의 스토리를 만드는 상호 관련된 경고 및 관련 데이터의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="f95dd-110">Microsoft 365 및 앱은 의심스러우거나 악의적인 이벤트나 활동을 감지할 때 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="f95dd-111">개별 경고는 완료되거나 지속적인 공격에 대한 중요한 단서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="f95dd-112">그러나 공격은 일반적으로 장치, 사용자 및 사서함과 같은 다양한 유형의 엔터티에 대해 다양한 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="f95dd-113">그 결과 테넌트의 여러 엔터티에 대한 여러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="f95dd-114">개별 경고를 함께 하여 공격에 대한 통찰력을 확보하는 것은 어렵고 시간이 많이 소요될 수 있기 때문에 Microsoft 365 Defender는 경고 및 관련 정보를 인시던트에 자동으로 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Defender가 Microsoft 365 이벤트와 인시던트의 상관 관계":::

<span data-ttu-id="f95dd-116">Defender의 인시던트에 대한 Microsoft 365 간략한 개요를 시청하세요(4분).</span><span class="sxs-lookup"><span data-stu-id="f95dd-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="f95dd-117">관련 경고를 인시던트로 그룹화하면 공격을 포괄적으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="f95dd-118">예를 들어 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-118">For example, you can see:</span></span>

- <span data-ttu-id="f95dd-119">공격이 시작된 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-119">Where the attack started.</span></span>
- <span data-ttu-id="f95dd-120">사용된 전술</span><span class="sxs-lookup"><span data-stu-id="f95dd-120">What tactics were used.</span></span>
- <span data-ttu-id="f95dd-121">공격이 테넌트에 얼마나 들어갔는가.</span><span class="sxs-lookup"><span data-stu-id="f95dd-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="f95dd-122">공격 범위(예: 영향을 받는 장치, 사용자 및 사서함 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="f95dd-123">공격과 관련된 모든 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="f95dd-124">이 [옵션을](m365d-enable.md)Microsoft 365 Defender는 [](m365d-autoir.md) 자동화 및 인공 지능을 통해 경고를 자동으로 조사하고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="f95dd-125">추가 수정 단계를 수행하여 공격을 해결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="f95dd-126">보안 센터의 인시던트 Microsoft 365 알림</span><span class="sxs-lookup"><span data-stu-id="f95dd-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="f95dd-127">인시던트  및 인시던트 & (>)의 빠른 실행에서 인시던트 및 인시던트 Microsoft 365[관리합니다(](https://security.microsoft.com)security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f95dd-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="f95dd-128">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="보안 센터의 인시던트 Microsoft 365 페이지":::

<span data-ttu-id="f95dd-130">인시던트 이름을 선택하면 인시던트 요약이 표시될 수 있으며 추가 정보가 있는 탭에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="보안 센터의 인시던트에 대한 요약 Microsoft 365 예":::

<span data-ttu-id="f95dd-132">인시던트에 대한 추가 탭은:</span><span class="sxs-lookup"><span data-stu-id="f95dd-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="f95dd-133">경고</span><span class="sxs-lookup"><span data-stu-id="f95dd-133">Alerts</span></span> 

  <span data-ttu-id="f95dd-134">인시던트 및 해당 정보와 관련된 모든 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="f95dd-135">디바이스</span><span class="sxs-lookup"><span data-stu-id="f95dd-135">Devices</span></span>

  <span data-ttu-id="f95dd-136">인시던트의 일부로 식별되거나 인시던트와 관련된 모든 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="f95dd-137">사용자</span><span class="sxs-lookup"><span data-stu-id="f95dd-137">Users</span></span>

  <span data-ttu-id="f95dd-138">인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="f95dd-139">사서함</span><span class="sxs-lookup"><span data-stu-id="f95dd-139">Mailboxes</span></span>

  <span data-ttu-id="f95dd-140">인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="f95dd-141">조사</span><span class="sxs-lookup"><span data-stu-id="f95dd-141">Investigations</span></span>

  <span data-ttu-id="f95dd-142">[인시던트의](m365d-autoir.md) 경고에 의해 트리거된 모든 자동화된 조사.</span><span class="sxs-lookup"><span data-stu-id="f95dd-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="f95dd-143">증거 및 응답</span><span class="sxs-lookup"><span data-stu-id="f95dd-143">Evidence and Response</span></span>

  <span data-ttu-id="f95dd-144">인시던트의 경고에서 지원되는 모든 이벤트 및 의심스러운 엔터티</span><span class="sxs-lookup"><span data-stu-id="f95dd-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="f95dd-145">Graph(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="f95dd-145">Graph (in preview)</span></span>

  <span data-ttu-id="f95dd-146">조직의 영향을 미치는 자산에 대한 경고의 연결을 보여 미치는 그림입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="f95dd-147">다음은 인시던트와 인시던트 데이터 및 인시던트 보안 센터의 인시던트 탭 Microsoft 365 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="인시던트 및 데이터와 보안 센터의 인시던트 탭과의 Microsoft 365 관계":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="f95dd-149">Defender에 대한 인시던트 Microsoft 365 워크플로 예</span><span class="sxs-lookup"><span data-stu-id="f95dd-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="f95dd-150">다음은 Microsoft 365 보안 센터에서 인시던트에 응답하기 위한 Microsoft 365 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="인시던트 대응 워크플로의 Microsoft 365":::

<span data-ttu-id="f95dd-152">지속적인 기준에 따라 인시던트 큐에서 분석 및 해결을 위해 우선 순위가 가장 높은 인시던트를 식별하고 대응을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="f95dd-153">이 조합은</span><span class="sxs-lookup"><span data-stu-id="f95dd-153">This is a combination of:</span></span>

- <span data-ttu-id="f95dd-154">[인시던트](incident-queue.md) 큐 필터링 및 정렬을 통해 우선 순위가 가장 높은 인시던트 결정</span><span class="sxs-lookup"><span data-stu-id="f95dd-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="f95dd-155">[직위를](manage-incidents.md) 수정하고, 분석가에게 할당하고, 태그와 설명을 추가하여 인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="f95dd-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="f95dd-156">각 인시던트에 대해 [공격을 시작하고 조사 및 분석을 경고합니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="f95dd-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   <span data-ttu-id="f95dd-157">a.</span><span class="sxs-lookup"><span data-stu-id="f95dd-157">a.</span></span> <span data-ttu-id="f95dd-158">인시던트의 요약을 보고 인시던트의 범위 및 심각도와 영향을  받는 엔터티(요약 탭)를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-158">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="f95dd-159">b.</span><span class="sxs-lookup"><span data-stu-id="f95dd-159">b.</span></span> <span data-ttu-id="f95dd-160">경고의 출처, 범위 및 심각도(경고 탭)를  이해하기 위해 경고 분석을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="f95dd-160">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="f95dd-161">c.</span><span class="sxs-lookup"><span data-stu-id="f95dd-161">c.</span></span> <span data-ttu-id="f95dd-162">필요한 경우 영향을 받는 장치, 사용자 및 사서함(장치, 사용자 및 사서함 탭)에 대한 **정보를** 수집합니다. </span><span class="sxs-lookup"><span data-stu-id="f95dd-162">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="f95dd-163">d.</span><span class="sxs-lookup"><span data-stu-id="f95dd-163">d.</span></span> <span data-ttu-id="f95dd-164">Defender에서 Microsoft 365 경고를 [](m365d-autoir.md) 자동으로 해결한 방법을 참조합니다(조사 **탭).**</span><span class="sxs-lookup"><span data-stu-id="f95dd-164">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="f95dd-165">e.</span><span class="sxs-lookup"><span data-stu-id="f95dd-165">e.</span></span> <span data-ttu-id="f95dd-166">필요한 경우 인시던트에 대한 데이터 집합의 정보를 사용하여 자세한 정보(증거 및 응답 **탭)를 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="f95dd-166">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="f95dd-167">분석 후 또는 분석 중에 포함을 수행하여 보안 위협의 공격 및 제거에 대한 추가 영향을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-167">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="f95dd-168">테넌트 리소스를 인시던트 이전 상태로 복원하여 공격으로부터 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-168">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="f95dd-169">[인시던트](manage-incidents.md#resolve-an-incident) 문제를 해결하고 인시던트 사후 학습을 통해 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-169">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="f95dd-170">공격의 유형과 그 영향에 대해 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-170">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="f95dd-171">[위협](threat-analytics.md) 분석 및 보안 커뮤니티에서 공격을 조사하여 보안 공격 추세를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-171">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="f95dd-172">인시던트 해결에 사용한 워크플로를 회수하고 필요한 경우 표준 워크플로, 프로세스, 정책 및 플레이북을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-172">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="f95dd-173">보안 구성의 변경이 필요한지 여부를 결정하고 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-173">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="f95dd-174">보안 분석이 처음인 경우 [](incidents-overview.md) 추가 정보는 첫 번째 인시던트에 응답하는 소개를 참조하고 인시던트 예제를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-174">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="f95dd-175">Defender에 대한 보안 Microsoft 365 예</span><span class="sxs-lookup"><span data-stu-id="f95dd-175">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="f95dd-176">다음은 Defender에 대한 보안 작업의 Microsoft 365 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-176">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Defender에 대한 보안 작업 Microsoft 365 예":::

<span data-ttu-id="f95dd-178">일별 작업에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-178">Daily tasks can include:</span></span>

- <span data-ttu-id="f95dd-179">[인시던트](manage-incidents.md) 관리</span><span class="sxs-lookup"><span data-stu-id="f95dd-179">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="f95dd-180">관리 [센터에서 자동화된 조사 및 대응(AIR)](m365d-action-center.md) 작업 검토</span><span class="sxs-lookup"><span data-stu-id="f95dd-180">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="f95dd-181">최신 위협 [분석 검토](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="f95dd-181">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="f95dd-182">[인시던트에](investigate-incidents.md) 응답</span><span class="sxs-lookup"><span data-stu-id="f95dd-182">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="f95dd-183">월별 작업에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-183">Monthly tasks can include:</span></span>

- <span data-ttu-id="f95dd-184">AIR [설정 검토](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="f95dd-184">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="f95dd-185">보안 [점수 및](microsoft-secure-score-improvement-actions.md) 위협 요소 [& 관리 검토](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="f95dd-185">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="f95dd-186">IT 보안 관리 체인에 보고</span><span class="sxs-lookup"><span data-stu-id="f95dd-186">Reporting to your IT security management chain</span></span>

<span data-ttu-id="f95dd-187">분기별 작업에는 CISO(최고 정보 보안 책임자)에게 보안 결과를 보고하고 브리핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-187">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="f95dd-188">연간 작업에는 직원, 시스템 및 프로세스를 테스트하기 위한 주요 인시던트 또는 위반 연습 수행이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-188">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="f95dd-189">매일, 월별, 분기별 및 연간 작업을 사용하여 프로세스, 정책 및 보안 구성을 업데이트하거나 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-189">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f95dd-190">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f95dd-190">Next steps</span></span>

<span data-ttu-id="f95dd-191">**보안 분석 및 인시던트** 대응이 새로운 경우:</span><span class="sxs-lookup"><span data-stu-id="f95dd-191">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="f95dd-192">공격의 [](first-incident-overview.md) 예와 함께 Microsoft 365 보안 센터에서 일반적인 분석, 수정 및 인시던트 사후 검토 과정을 안내하는 첫 번째 인시던트에 응답을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f95dd-192">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 security center with an example of an attack.</span></span>

<span data-ttu-id="f95dd-193">**보안 분석 및 인시던트** 대응 경험이 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="f95dd-193">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="f95dd-194">보안 센터의 인시던트  페이지에서 인시던트 Microsoft 365 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="f95dd-194">Get started with the incident queue from the **Incidents** page of the Microsoft 365 security center.</span></span> <span data-ttu-id="f95dd-195">여기에서 다음 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-195">From here, you can:</span></span>

  - <span data-ttu-id="f95dd-196">심각도 및 기타 [](incident-queue.md) 요인에 따라 우선 순위를 지정해야 하는 사고를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-196">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="f95dd-197">[인시던트](manage-incidents.md)관리 워크플로를 기반으로 태그 및 설명을 변경, 할당, 분류 및 추가하는 인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="f95dd-197">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="f95dd-198">[인시던트 조사를](investigate-incidents.md) 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f95dd-198">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="f95dd-199">[피싱,](https://docs.microsoft.com/security/compass/incident-response-playbooks) 암호 분사 및 앱 동의 부여 공격에 대한 자세한 지침은 다음 인시던트 대응 플레이북을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f95dd-199">See these [incident response playbooks](https://docs.microsoft.com/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

