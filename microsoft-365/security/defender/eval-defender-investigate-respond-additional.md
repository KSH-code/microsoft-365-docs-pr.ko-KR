---
title: 파일럿 Microsoft 365 Defender 인시던트 대응 기능을 사용하여 인시던트의 우선 순위를 지정 및 관리하고, 자동화된 조사 및 대응을 구성하고, 고급 헌팅을 사용
description: 인시던트 대응 기능을 Microsoft 365 Defender 우선 순위를 지정하고 관리하고, 조사를 자동화하고, 위협 감지에서 고급 헌팅을 사용 합니다.
keywords: Microsoft 365 Defender 평가, Microsoft 365 Defender 평가, Microsoft 365 Defender Microsoft 365 Defender 평가 랩, Microsoft 365 Defender 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c554f7bcedbdb64118639f5a455fd6f6e55daaa6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458116"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a><span data-ttu-id="1f3a6-104">파일럿 Microsoft 365 Defender 인시던트 대응 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="1f3a6-104">Try Microsoft 365 Defender incident response capabilities in a pilot environment</span></span>

<span data-ttu-id="1f3a6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-105">**Applies to:**</span></span>
- <span data-ttu-id="1f3a6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f3a6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1f3a6-107">이 문서는 파일럿 환경을 사용하여 파일럿 환경에서 인시던트에 대한 조사 및 대응을 Microsoft 365 Defender [2단계](eval-defender-investigate-respond.md) 중 2단계입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-107">This article is [Step 2 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="1f3a6-108">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-investigate-respond.md)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-108">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="1f3a6-109">시뮬레이트된 [](eval-defender-investigate-respond-simulate-attack.md)공격에 대한 인시던트 대응을 수행한 후 다음과 같은 몇 가지 Microsoft 365 Defender 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-109">Once you have performed an [incident response for a simulated attack](eval-defender-investigate-respond-simulate-attack.md), here are some Microsoft 365 Defender capabilities to explore:</span></span>

|<span data-ttu-id="1f3a6-110">기능</span><span class="sxs-lookup"><span data-stu-id="1f3a6-110">Capability</span></span> |<span data-ttu-id="1f3a6-111">설명</span><span class="sxs-lookup"><span data-stu-id="1f3a6-111">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="1f3a6-112">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="1f3a6-112">Prioritize incidents</span></span>](#prioritize-incidents) | <span data-ttu-id="1f3a6-113">인시던트 큐 필터링 및 정렬을 사용하여 다음에 해결할 인시던트가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-113">Use filtering and sorting of the incidents queue to determine which incidents to address next.</span></span> |
| [<span data-ttu-id="1f3a6-114">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="1f3a6-114">Manage incidents</span></span>](#manage-incidents) | <span data-ttu-id="1f3a6-115">인시던트 속성을 수정하여 올바른 할당을 보장하고 태그 및 설명을 추가하고 인시던트 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-115">Modify incident properties to ensure correct assignment, add tags and comments, and to resolve an incident.</span></span> |
| [<span data-ttu-id="1f3a6-116">자동화된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="1f3a6-116">Automated investigation and response</span></span>](#examine-automated-investigation-and-response-with-the-action-center) | <span data-ttu-id="1f3a6-117">보안 운영 팀이 위협을 보다 효율적으로 해결할 수 있도록 도와주는 자동화된 조사 및 대응(AIR) 기능</span><span class="sxs-lookup"><span data-stu-id="1f3a6-117">Automated investigation and response (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span> <span data-ttu-id="1f3a6-118">알림 센터는 보류 중인 수정 작업 승인과 같은 인시던트 및 경고 작업에 대한 "단일 창 창" 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-118">The Action center is a "single pane of glass" experience for incident and alert tasks such as approving pending remediation actions.</span></span> |
| [<span data-ttu-id="1f3a6-119">지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="1f3a6-119">Advanced hunting</span></span>](#advanced-hunting) | <span data-ttu-id="1f3a6-120">네트워크에서 이벤트를 사전 검사하고 위협 표시기 및 엔터티를 찾을 수 있는 쿼리 기반 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-120">A query-based threat-hunting tool that lets you proactively inspect events in your network and locate threat indicators and entities.</span></span> <span data-ttu-id="1f3a6-121">또한 인시던트의 조사 및 수정 중에 고급 헌팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-121">You also use advanced hunting during the investigation and remediation of an incident.</span></span> |
||||

## <a name="prioritize-incidents"></a><span data-ttu-id="1f3a6-122">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="1f3a6-122">Prioritize incidents</span></span>

<span data-ttu-id="1f3a6-123">인시던트 및  인시던트 & 포털(>)의 빠른 실행에서 인시던트 Microsoft 365 Defender 큐로[security.microsoft.com.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-123">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="1f3a6-124">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-124">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="인시던트 큐의 예":::

<span data-ttu-id="1f3a6-126">최근 **인시던트** 및 알림 섹션에는 지난 24시간 동안 수신된 경고 및 인시던트 수의 그래프가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-126">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="1f3a6-127">인시던트 목록을 검사하고 할당 및 조사의 중요성에 우선 순위를 지정하기 위해 다음을 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-127">To examine the list of incidents and prioritize their importance for assignment and investigation, you can:</span></span> 

- <span data-ttu-id="1f3a6-128">사용자 지정 가능한 열을 구성(열 선택 선택)하여 인시던트 또는 영향을 주는 엔터티의 다양한 특성을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-128">Configure customizable columns (select **Choose columns**) to give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="1f3a6-129">이를 통해 분석을 위한 인시던트 우선 순위에 대한 정보를 통해 의사 결정을 내리는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-129">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

- <span data-ttu-id="1f3a6-130">필터링을 사용하여 특정 시나리오 또는 위협에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-130">Use filtering to focus on a specific scenario or threat.</span></span> <span data-ttu-id="1f3a6-131">인시던트 큐에 필터를 적용하면 즉각적인 주의가 필요한 인시던트가 결정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-131">Applying filters on the incident queue can help determine which incidents require immediate attention.</span></span> 

<span data-ttu-id="1f3a6-132">기본 인시던트 큐에서 **필터를** 선택하여 특정 인시던트 집합을 지정할 수 있는 필터 창을 표시합니다. </span><span class="sxs-lookup"><span data-stu-id="1f3a6-132">From the default incident queue, select **Filters** to see a **Filters** pane, from which you can specify a specific set of incidents.</span></span> <span data-ttu-id="1f3a6-133">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-133">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="인시던트 큐에 대한 필터 창의 예":::

<span data-ttu-id="1f3a6-135">자세한 내용은 인시던트 [우선 순위 지정을 참조하세요.](incident-queue.md)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-135">For more information, see [Prioritize incidents](incident-queue.md).</span></span>

## <a name="manage-incidents"></a><span data-ttu-id="1f3a6-136">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="1f3a6-136">Manage incidents</span></span>

<span data-ttu-id="1f3a6-137">인시던트에 대한  인시던트 관리 창에서 인시던트 관리를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-137">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="1f3a6-138">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-138">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="인시던트의 인시던트 관리 창 예":::

<span data-ttu-id="1f3a6-140">이 창은 다음의  문제 관리 링크에서 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-140">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="1f3a6-141">인시던트 큐에 있는 인시던트의 속성 창입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-141">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="1f3a6-142">**인시던트의** 요약 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-142">**Summary** page of an incident.</span></span>

<span data-ttu-id="1f3a6-143">인시던트 관리 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-143">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="1f3a6-144">인시던트 이름 편집</span><span class="sxs-lookup"><span data-stu-id="1f3a6-144">Edit the incident name</span></span>

  <span data-ttu-id="1f3a6-145">보안 팀 모범 사례에 따라 utomatically 할당된 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-145">Change the utomatically assigned name based on your security team best practices.</span></span>
  
- <span data-ttu-id="1f3a6-146">인시던트 태그 추가</span><span class="sxs-lookup"><span data-stu-id="1f3a6-146">Add incident tags</span></span>

  <span data-ttu-id="1f3a6-147">보안 팀이 나중에 필터링할 수 있는 인시던트 분류에 사용하는 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-147">Add tags that your security team uses to classify incidents, which can be later filtered.</span></span>
  
- <span data-ttu-id="1f3a6-148">인시던트 할당</span><span class="sxs-lookup"><span data-stu-id="1f3a6-148">Assign the incident to yourself</span></span>

  <span data-ttu-id="1f3a6-149">나중에 필터링할 수 있는 사용자 계정 이름에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-149">Assign it to your user account name, which can be later filtered.</span></span>
  
- <span data-ttu-id="1f3a6-150">인시던트 해결</span><span class="sxs-lookup"><span data-stu-id="1f3a6-150">Resolve an incident</span></span>

  <span data-ttu-id="1f3a6-151">인시던트가 수정된 후 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-151">Close the incident after it has been remediated.</span></span>
  
- <span data-ttu-id="1f3a6-152">분류 및 결정 설정</span><span class="sxs-lookup"><span data-stu-id="1f3a6-152">Set its classification and determination</span></span>

  <span data-ttu-id="1f3a6-153">인시던트 해결 시 위협 유형을 분류하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-153">Classify and select the threat type when you resolve an incident.</span></span>
  
- <span data-ttu-id="1f3a6-154">메모 추가</span><span class="sxs-lookup"><span data-stu-id="1f3a6-154">Add comments</span></span>

  <span data-ttu-id="1f3a6-155">보안 팀 모범 사례에 따라 진행률, 메모 또는 기타 정보에 설명을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-155">Use comments for progress, notes, or other information based on your security team best practices.</span></span> <span data-ttu-id="1f3a6-156">전체 설명 기록은 인시던트의 세부 정보 페이지의 설명 및 기록 옵션에서 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1f3a6-156">The full comment history is available from the **Comments and history** option in the details page of an incident.</span></span>

<span data-ttu-id="1f3a6-157">자세한 내용은 인시던트 [관리를 참조하세요.](manage-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-157">For more information, see [Manage incidents](manage-incidents.md).</span></span>

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a><span data-ttu-id="1f3a6-158">관리 센터를 통해 자동화된 조사 및 대응 검사</span><span class="sxs-lookup"><span data-stu-id="1f3a6-158">Examine automated investigation and response with the Action center</span></span>

<span data-ttu-id="1f3a6-159">조직에 대해 자동화된 조사 및 대응 기능이 구성되는 방식에 따라 보안 운영 팀의 승인만 수행되거나 자동으로 수정 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-159">Depending on how automated investigation and response capabilities are configured for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="1f3a6-160">보류 중이든 완료이든 모든 작업은 알림 [](m365d-action-center.md)센터에 나열됩니다. 이 센터에는 장치에 대한 보류 중 및 완료된 수정 작업, 전자 메일 & 공동 작업 콘텐츠 및 ID가 한 위치에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-160">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md), which lists pending and completed remediation actions for your devices, email & collaboration content, and identities in one location.</span></span>

<span data-ttu-id="1f3a6-161">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-161">Here's an example.</span></span>

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Microsoft 365 Defender":::

<span data-ttu-id="1f3a6-163">작업 센터에서 보류 중인 작업을 선택한 다음 플라이아웃 창에서 해당 작업을 승인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-163">From the Action center, you can select pending actions and then approve or reject them in the flyout pane.</span></span> <span data-ttu-id="1f3a6-164">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-164">Here's an example.</span></span>

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="조치 승인 또는 거부":::

<span data-ttu-id="1f3a6-166">자동화된 조사를 진행하고 제시간에 완료할 수 있도록 가능한 한 빨리 보류 중인 작업을 승인(또는 거부)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-166">Approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span>

<span data-ttu-id="1f3a6-167">자세한 내용은 자동화된 조사 및 [대응 및](m365d-autoir.md) [관리 센터를 참조하세요.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-167">For more information, see [Automated investigation and response](m365d-autoir.md) and [Action center](m365d-action-center.md).</span></span>

## <a name="advanced-hunting"></a><span data-ttu-id="1f3a6-168">고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="1f3a6-168">Advanced hunting</span></span>

> [!NOTE]
> <span data-ttu-id="1f3a6-169">고급 헌팅 시뮬레이션을 진행하기 전에 다음 비디오를 시청하여 고급 헌팅 개념을 이해하고 포털에서 찾을 수 있는 위치를 확인하며 보안 작업에 도움이 되는 방법을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-169">Before we walk you through the advanced hunting simulation, watch the following video to understand advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


<span data-ttu-id="1f3a6-170">선택적 파일 없는 [PowerShell](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) 공격 시뮬레이션이 이미 자격 증명 액세스 단계에 도달한 실제 공격인 경우 조사의 임의 지점에서 고급 헌팅을 사용하여 생성된 경고 및 영향을 받는 엔터티에서 이미 알고 있는 것을 사용하여 네트워크의 이벤트 및 레코드를 능동적으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-170">If the [optional fileless PowerShell attack simulation](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) were a real attack that had already reached the credential access stage, you can use advanced hunting at any point in the investigation to proactively search through events and records in the network using what you already know from the generated alerts and affected entities.</span></span> <span data-ttu-id="1f3a6-171">예를 들어 지난 30일 동안 외부 IP 주소에 대한 연결을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-171">For instance, you can query for any connections to the external IP address in the past 30 days.</span></span>

### <a name="hunting-environment-requirements"></a><span data-ttu-id="1f3a6-172">헌팅 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f3a6-172">Hunting environment requirements</span></span>

<span data-ttu-id="1f3a6-173">이 시뮬레이션에는 단일 내부 사서함 및 장치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-173">There's a single internal mailbox and device required for this simulation.</span></span> <span data-ttu-id="1f3a6-174">테스트 메시지를 보내기 위해 외부 전자 메일 계정도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-174">You'll also need an external email account to send the test message.</span></span>

1. <span data-ttu-id="1f3a6-175">테넌트에서 [를 사용하도록 설정되어 있는지 Microsoft 365 Defender.](m365d-enable.md#confirm-that-the-service-is-on)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-175">Verify that your tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>
2. <span data-ttu-id="1f3a6-176">전자 메일을 받는 데 사용할 대상 사서함을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-176">Identify a target mailbox to be used for receiving email.</span></span>

   - <span data-ttu-id="1f3a6-177">이 사서함은 Microsoft Defender에서 모니터링해야 Office 365</span><span class="sxs-lookup"><span data-stu-id="1f3a6-177">This mailbox must be monitored by Microsoft Defender for Office 365</span></span>

   - <span data-ttu-id="1f3a6-178">요구 사항 3의 장치가 이 사서함에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-178">The device from requirement 3 needs to access this mailbox</span></span>

3. <span data-ttu-id="1f3a6-179">테스트 장치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-179">Configure a test device:</span></span>

    <span data-ttu-id="1f3a6-180">a.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-180">a.</span></span> <span data-ttu-id="1f3a6-181">버전 1903 이상을 Windows 10 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="1f3a6-181">Make sure you are using Windows 10 version 1903 or later version.</span></span>

    <span data-ttu-id="1f3a6-182">b.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-182">b.</span></span> <span data-ttu-id="1f3a6-183">테스트 장치를 테스트 도메인에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-183">Join the test device to the test domain.</span></span>

    <span data-ttu-id="1f3a6-184">c.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-184">c.</span></span> <span data-ttu-id="1f3a6-185">[를 Windows Defender 바이러스 백신.](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-185">[Turn on Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="1f3a6-186">사용자 설정에 문제가 Windows Defender 바이러스 백신 문제 해결 항목을 [참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-186">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

    <span data-ttu-id="1f3a6-187">d.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-187">d.</span></span> <span data-ttu-id="1f3a6-188">[끝점용 Microsoft Defender에 온보딩합니다.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-188">[Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="1f3a6-189">시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="1f3a6-189">Run the simulation</span></span>

1. <span data-ttu-id="1f3a6-190">외부 전자 메일 계정에서 헌팅 환경 요구 사항 섹션의 2단계에서 식별된 사서함으로 전자 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-190">From an external email account, send an email to the mailbox identified in step 2 of the hunting environment requirements section.</span></span> <span data-ttu-id="1f3a6-191">기존 전자 메일 필터 정책을 통해 허용되는 첨부 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-191">Include an attachment that will be allowed through any existing email filter policies.</span></span> <span data-ttu-id="1f3a6-192">이 파일은 악성 파일이나 실행 파일이 아니어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-192">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="1f3a6-193">추천 파일 형식은 <i>.pdf</i>, <i></i>.exe(허용되는 경우) 또는 Word 파일과 같은 Office 문서 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-193">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or an Office document type such as a Word file.</span></span>

2. <span data-ttu-id="1f3a6-194">헌팅 환경 요구 사항 섹션의 3단계에 정의된 것으로 구성된 장치에서 보낸 전자 메일을 열습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-194">Open the sent email from the device configured as defined in step 3 of the hunting environment requirements section.</span></span> <span data-ttu-id="1f3a6-195">첨부 파일을 열거나 장치에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-195">Either open the attachment or save the file to the device.</span></span>

#### <a name="go-hunting"></a><span data-ttu-id="1f3a6-196">헌팅으로 이동</span><span class="sxs-lookup"><span data-stu-id="1f3a6-196">Go hunting</span></span>

1. <span data-ttu-id="1f3a6-197">웹 Microsoft 365 Defender [를 열 수 있습니다.](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-197">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="1f3a6-198">탐색 창에서 고급 헌팅 **> 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-198">From the navigation pane, select **Hunting > Advanced hunting**.</span></span>

3. <span data-ttu-id="1f3a6-199">전자 메일 이벤트를 수집하여 시작하는 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-199">Build a query that starts by gathering email events.</span></span>

   1. <span data-ttu-id="1f3a6-200">쿼리 **쿼리 > 새로 고치기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-200">Select **Query > New**.</span></span>

   1. <span data-ttu-id="1f3a6-201">고급 **헌팅** 아래의 전자 메일 **그룹에서** **EmailEvents 를 두 번 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-201">In the **Email** groups under **Advanced hunting**, double-click **EmailEvents**.</span></span> <span data-ttu-id="1f3a6-202">쿼리 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-202">You should see this in the query window.</span></span>

      ```console
      EmailEvents
      ```

   1. <span data-ttu-id="1f3a6-203">쿼리의 시간 프레임을 지난 24시간으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-203">Change the time frame of the query to the last 24 hours.</span></span> <span data-ttu-id="1f3a6-204">위의 시뮬레이션을 실행할 때 보낸 전자 메일이 지난 24시간 동안의 경우, 그렇지 않으면 필요한 경우 시간 프레임을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-204">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame as needed.</span></span>

   1. <span data-ttu-id="1f3a6-205">쿼리 **실행 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-205">Select **Run query**.</span></span> <span data-ttu-id="1f3a6-206">파일럿 환경에 따라 결과가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-206">You may have differing results depending on your pilot environment.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1f3a6-207">데이터 반환을 제한하는 필터링 옵션에 대한 다음 단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-207">See the next step for filtering options to limit data return.</span></span>

      ![고급 헌팅 쿼리 결과의 예](../../media/mtp/fig19.png)

        > [!NOTE]
        > <span data-ttu-id="1f3a6-209">고급 헌팅은 쿼리 결과를 테이블형 데이터로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-209">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="1f3a6-210">차트와 같은 다른 형식의 데이터를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-210">You can also opt to view the data in other format types such as charts.</span></span>

   1. <span data-ttu-id="1f3a6-211">결과를 확인하고 연 전자 메일을 식별할 수 있는지 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-211">Look at the results and see if you can identify the email you opened.</span></span> <span data-ttu-id="1f3a6-212">고급 헌팅에 메시지가 표시될 때 최대 2시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-212">It may take up to two hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="1f3a6-213">결과 범위를 좁히기 위해 **쿼리에 where** 조건을 추가하여 SenderMailFromDomain으로 "yahoo.com" 전자 메일만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-213">To narrow down the results, you can add the **where** condition to your query to only look for emails that have "yahoo.com" as their SenderMailFromDomain.</span></span> <span data-ttu-id="1f3a6-214">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-214">Here is an example.</span></span>

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. <span data-ttu-id="1f3a6-215">레코드를 검사할 수 있도록 쿼리에서 결과 행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-215">Click the resulting rows from the query so you can inspect the record.</span></span>

      ![고급 헌팅 결과가 선택될 때 열 수 있는 조사 레코드 쪽 패널의 예](../../media/mtp/fig21.png)

4. <span data-ttu-id="1f3a6-217">이제 전자 메일을 볼 수 있는 것으로 확인되면 첨부 파일에 대한 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-217">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="1f3a6-218">환경의 첨부 파일이 있는 모든 전자 메일에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-218">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="1f3a6-219">이 시뮬레이션에서는 사용자 환경에서 전송되는 전자 메일이 아니라 인바운드 전자 메일에 중점을 니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-219">For this simulation, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="1f3a6-220">메시지를 찾기 위해 추가한 필터를 제거하고 "| 여기서 **AttachmentCount > 및** **EmailDirection**  ==  **"Inbound""**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-220">Remove any filters you have added to locate your message and add "| where **AttachmentCount > 0** and **EmailDirection** == **"Inbound""**</span></span>

   <span data-ttu-id="1f3a6-221">다음 쿼리는 모든 전자 메일 이벤트에 대한 초기 쿼리보다 짧은 목록으로 결과를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-221">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. <span data-ttu-id="1f3a6-222">그런 다음 결과 집합에 첨부 파일에 대한 정보(예: 파일 이름, 해시)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-222">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="1f3a6-223">이렇게 하여 **EmailAttachmentInfo** 테이블을 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-223">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="1f3a6-224">조인에 사용할 일반 필드는 **NetworkMessageId** 및 **RecipientObjectId입니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-224">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

   <span data-ttu-id="1f3a6-225">다음 쿼리에는 "| **project-rename EmailTimestamp=Timestamp**" - 다음 단계에서 추가할 파일 작업과 관련된 타임스탬프와 전자 메일과 관련된 타임스탬프를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-225">The following query also includes an additional line "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. <span data-ttu-id="1f3a6-226">그런 다음 **EmailAttachmentInfo** 테이블의 **SHA256** 값을 사용하여 해당 해시에 대한 **DeviceFileEvents(끝점에서** 수행된 파일 작업)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-226">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span> <span data-ttu-id="1f3a6-227">여기서 공통 필드는 첨부 파일에 대한 SHA256 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-227">The common field here will be the SHA256 hash for the attachment.</span></span>

   <span data-ttu-id="1f3a6-228">결과 테이블에는 이제 끝점(끝점용 Microsoft Defender)의 세부 정보(예: 장치 이름, 수행된 작업(이 경우 FileCreated 이벤트만 포함) 및 파일이 저장된 위치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-228">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="1f3a6-229">프로세스와 연결된 계정 이름도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-229">The account name associated with the process will also be included.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   <span data-ttu-id="1f3a6-230">이제 사용자가 첨부 파일을 열거나 저장한 모든 인바운드 전자 메일을 식별하는 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-230">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="1f3a6-231">이 쿼리를 구체화하여 특정 보낸 사람 도메인, 파일 크기, 파일 형식 등도 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-231">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7. <span data-ttu-id="1f3a6-232">함수는 특수한 종류의 조인으로, 파일에 대한 추가 TI 데이터(예: 보급, 서명자 및 발급자 정보 등)를 끌어와야 합니다. 파일에 대한 자세한 내용을 확인하기 위해 **FileProfile()** 함수 향상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-232">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc. To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a><span data-ttu-id="1f3a6-233">검색 만들기</span><span class="sxs-lookup"><span data-stu-id="1f3a6-233">Create a detection</span></span>

<span data-ttu-id="1f3a6-234">향후 경고를 받을 정보를 식별하는 쿼리를 만든  후 쿼리에서 사용자 지정 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-234">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span>

<span data-ttu-id="1f3a6-235">사용자 지정 검색은 설정한 빈도에 따라 쿼리를 실행하고 쿼리 결과에 따라 선택한 영향을 미치는 자산에 따라 보안 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-235">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="1f3a6-236">이러한 경고는 인시던트와 상호 관련이 있으며 제품 중 하나에서 생성된 다른 보안 경고로 조사될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-236">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1. <span data-ttu-id="1f3a6-237">쿼리 페이지에서 이동 헌팅 지침의 7단계에서 추가된 줄 7과 8을 제거하고 검색 규칙 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-237">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span>

   ![고급 헌팅 페이지에서 검색 규칙 만들기를 클릭할 수 있는 위치의 예](../../media/mtp/fig22.png)

   > [!NOTE]
   > <span data-ttu-id="1f3a6-239">검색 규칙 **만들기를** 클릭하고 쿼리에 구문 오류가 있는 경우 검색 규칙이 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-239">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won't be saved.</span></span> <span data-ttu-id="1f3a6-240">쿼리를 다시 확인하여 오류가 없는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-240">Double-check your query to ensure there's no errors.</span></span>

2. <span data-ttu-id="1f3a6-241">보안 팀에서 경고를 이해할 수 있는 정보, 경고가 생성된 이유 및 수행할 것으로 예상되는 작업을 파악하는 데 필요한 필드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-241">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span>

   ![경고 세부 정보를 정의할 수 있는 검색 규칙 만들기 페이지의 예](../../media/mtp/fig23.png)

   <span data-ttu-id="1f3a6-243">이 검색 규칙 경고에 대한 정보를 통해 다음 사용자에게 정보를 제공하도록 필드를 명확히 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-243">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span>

3. <span data-ttu-id="1f3a6-244">이 경고에 영향을 미치는 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-244">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="1f3a6-245">이 경우 장치 및 **사서함 을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-245">In this case, select **Device** and **Mailbox**.</span></span>

   ![영향을 미치는 엔터티의 매개 변수를 선택할 수 있는 검색 규칙 만들기 페이지의 예](../../media/mtp/fig24.png)

4. <span data-ttu-id="1f3a6-247">경고가 트리거되는 경우 수행할 작업을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-247">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="1f3a6-248">이 경우 다른 작업을 수행할 수 있는 경우에도 바이러스 백신 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-248">In this case, run an antivirus scan, though other actions could be taken.</span></span>

   ![위협을 해결하기 위해 경고가 트리거될 때 바이러스 백신 검색을 실행할 수 있는 검색 규칙 만들기 페이지의 예](../../media/mtp/fig25.png)

5. <span data-ttu-id="1f3a6-250">경고 규칙의 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-250">Select the scope for the alert rule.</span></span> <span data-ttu-id="1f3a6-251">이 쿼리에는 디바이스가 포함되는 것이기 때문에 장치 그룹은 끝점 컨텍스트에 대한 Microsoft Defender에 따라 이 사용자 지정 검색과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-251">Since this query involves devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="1f3a6-252">영향을 미치는 엔터티로 장치를 포함하지 않는 사용자 지정 검색을 만드는 경우 범위가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-252">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>

   ![경고 규칙의 범위를 설정할 수 있는 검색 규칙 만들기 페이지의 예는 결과에 대한 기대치를 관리합니다.](../../media/mtp/fig26.png)

   <span data-ttu-id="1f3a6-254">이 파일럿에서는 이 규칙을 프로덕션 환경의 테스트 장치 하위 집합으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-254">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6. <span data-ttu-id="1f3a6-255">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-255">Select **Create**.</span></span> <span data-ttu-id="1f3a6-256">그런 다음 탐색 **패널에서 사용자** 지정 검색 규칙을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-256">Then, select **Custom detection rules** from the navigation panel.</span></span>

   ![메뉴의 사용자 지정 검색 규칙 옵션 예](../../media/mtp/fig27a.png)

   ![규칙 및 실행 세부 정보를 표시하는 검색 규칙 페이지의 예](../../media/mtp/fig27b.png)

   <span data-ttu-id="1f3a6-259">이 페이지에서 세부 정보 페이지를 여는 검색 규칙을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-259">From this page, you can select the detection rule, which will open a details page.</span></span>

   ![규칙 실행, 트리거된 경고 및 작업, 검색 편집 등 상태를 확인할 수 있는 전자 메일 첨부 파일 페이지의 예](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a><span data-ttu-id="1f3a6-261">고급 헌팅에 대한 전문 교육</span><span class="sxs-lookup"><span data-stu-id="1f3a6-261">Expert training on advanced hunting</span></span>

<span data-ttu-id="1f3a6-262">**사적** 추적은 새로운 보안 분석가와 위협 헌터를 위한 웹캐스트 시리즈입니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-262">**Tracking the adversary** is a webcast series for new security analysts and seasoned threat hunters.</span></span> <span data-ttu-id="1f3a6-263">고급 헌팅의 기본을 안내하여 정교한 쿼리를 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-263">It guides you through the basics of advanced hunting all the way to creating your own sophisticated queries.</span></span> 

<span data-ttu-id="1f3a6-264">고급 [헌팅에 대한](advanced-hunting-expert-training.md) 전문 교육을 참조하여 시작을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-264">See [Get expert training on advanced hunting](advanced-hunting-expert-training.md) to get started.</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="1f3a6-265">필요한 탐색</span><span class="sxs-lookup"><span data-stu-id="1f3a6-265">Navigation you may need</span></span>

[<span data-ttu-id="1f3a6-266">Microsoft 365 Defender 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="1f3a6-266">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
