---
title: 이벤트 타임라인의 위협 및 취약성 관리
description: 이벤트 타임라인은 조직에 위험이 도입되는 방식과 위험을 줄이기 위해 어떤 완화가 발생 하는지 해석하는 데 도움이 되는 위험 뉴스 피드입니다.
keywords: 이벤트 타임라인, Endpoint 이벤트 타임라인용 Microsoft Defender, Endpoint tvm 이벤트 타임라인용 Microsoft Defender, 위협 및 취약성 관리, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933484"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="45c04-104">이벤트 타임라인 - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="45c04-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="45c04-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="45c04-105">**Applies to:**</span></span>
- [<span data-ttu-id="45c04-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="45c04-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="45c04-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45c04-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="45c04-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="45c04-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="45c04-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="45c04-110">이벤트 타임라인은 새로운 취약성 또는 악용을 통해 조직에 위험이 도입된 방법을 해석하는 데 도움이 되는 위험 뉴스 피드입니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="45c04-111">조직의 위험에 영향을 줄 수 있는 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="45c04-112">예를 들어 도입된 새로운 취약성, 악용될 수 있는 취약성, 악용 키트에 추가된 악용 등도 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="45c04-113">또한 이벤트 타임라인은 큰 [](tvm-exposure-score.md) 변경의 원인을 확인할 수 있도록 노출 점수와 [장치에 대한 Microsoft 보안](tvm-microsoft-secure-score-devices.md) 점수에 대한 스토리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="45c04-114">이벤트는 디바이스 또는 장치의 점수에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="45c04-115">우선 순위가 높은 보안 권장 사항에 따라 수정해야 하는 사항을 해결하여 노출을 [줄입니다.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="45c04-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="45c04-116">새 취약성 이벤트에 대한 전자 메일을 얻습니다. [끝점용 Microsoft Defender에서 취약성](configure-vulnerability-email-notifications.md) 전자 메일 알림 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45c04-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="45c04-117">이벤트 타임라인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="45c04-118">또한 대시보드의 3가지 [진입점도 위협 및 취약성 관리 있습니다.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="45c04-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="45c04-119">**조직 노출 점수 카드:**"시간의에 따라 노출 점수" 그래프에서 이벤트 점 위에 마우스를 대고 "이 날의 모든 이벤트 보기"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="45c04-120">이벤트는 소프트웨어 취약성을 나타 내는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="45c04-121">**Microsoft Secure Score for Devices:**"Your score for devices over time" graph에서 이벤트 점 위에 마우스를 대고 "이 날의 모든 이벤트 보기"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="45c04-122">이벤트는 새 구성 평가를 나타내는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="45c04-123">**상위 이벤트 카드:** 상위 이벤트 테이블 아래쪽에서 "더 표시"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="45c04-124">카드에 지난 7일 동안 가장 영향력이 큰 세 가지 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="45c04-125">중요한 이벤트는 이벤트가 많은 장치에 영향을 주는지 또는 중요한 취약성인 경우를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="45c04-126">노출 점수 및 장치용 Microsoft 보안 점수 그래프</span><span class="sxs-lookup"><span data-stu-id="45c04-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="45c04-127">위협 및 취약성 관리 대시보드에서 노출 점수 그래프 위로 마우스를여 장치에 영향을 미치게 된 해당 날의 상위 소프트웨어 취약성 이벤트를 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="45c04-128">Microsoft Secure Score for Devices 그래프를 마우스로 마우스로 여서 점수에 영향을 주는 새로운 보안 구성 평가를 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="45c04-129">디바이스 또는 장치의 점수에 영향을 주는 이벤트가 없는 경우 아무 이벤트도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="45c04-130">![노출 점수가 장치용 Microsoft 보안 점수 ](images/tvm-event-timeline-exposure-score350.png) 
 ![ 호버](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="45c04-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="45c04-131">그 날의 이벤트로 드릴다운</span><span class="sxs-lookup"><span data-stu-id="45c04-131">Drill down to events from that day</span></span>

<span data-ttu-id="45c04-132">이 **날의** 모든 이벤트 표시를 선택하면 해당 날짜에 대한 사용자 지정 날짜 범위가 있는 이벤트 타임라인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![이벤트 타임라인 선택 사용자 지정 날짜 범위](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="45c04-134">날짜 **범위를 다른** 사용자 지정 범위 또는 미리 설정된 시간 범위로 변경하려면 사용자 지정 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![이벤트 타임라인 날짜 범위 옵션](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="45c04-136">이벤트 타임라인 개요</span><span class="sxs-lookup"><span data-stu-id="45c04-136">Event timeline overview</span></span>

<span data-ttu-id="45c04-137">이벤트 타임라인 페이지에서 이벤트와 관련된 모든 필요한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="45c04-138">기능:</span><span class="sxs-lookup"><span data-stu-id="45c04-138">Features:</span></span>

- <span data-ttu-id="45c04-139">열 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="45c04-139">Customize columns</span></span>
- <span data-ttu-id="45c04-140">이벤트 유형 또는 영향을 미치는 장치의 백분율별로 필터링</span><span class="sxs-lookup"><span data-stu-id="45c04-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="45c04-141">페이지당 30, 50 또는 100개 항목 보기</span><span class="sxs-lookup"><span data-stu-id="45c04-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="45c04-142">페이지 맨 위에 있는 두 개의 큰 숫자는 이벤트가 아니라 새로운 취약성 및 악용 가능한 취약성의 수를 보여 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="45c04-143">일부 이벤트는 여러 취약성을 가지며 일부 취약성은 여러 이벤트를 가지는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![이벤트 타임라인 페이지](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="45c04-145">열</span><span class="sxs-lookup"><span data-stu-id="45c04-145">Columns</span></span>

- <span data-ttu-id="45c04-146">**날짜**: 월, 일, 연도</span><span class="sxs-lookup"><span data-stu-id="45c04-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="45c04-147">**이벤트**: 구성 요소, 유형 및 영향을 미치는 장치 수를 비롯한 영향을 미치는 이벤트</span><span class="sxs-lookup"><span data-stu-id="45c04-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="45c04-148">**관련 구성 요소**: software</span><span class="sxs-lookup"><span data-stu-id="45c04-148">**Related component**: software</span></span>
- <span data-ttu-id="45c04-149">**원래 영향을 났던 장치:** 이 이벤트가 처음에 발생한 영향을 미치는 장치의 수 및 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="45c04-150">총 장치 수에서 원래 영향을 들은 장치의 비율을 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="45c04-151">**현재 영향을 미치는 장치:** 이 이벤트가 현재 영향을 미치는 장치의 현재 수 및 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="45c04-152">열 사용자 지정 을 선택하여 이 **필드를 찾을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="45c04-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="45c04-153">**유형**: 점수에 영향을 미치는 타임스탬프가 있는 이벤트를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="45c04-154">필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-154">They can be filtered.</span></span>
    - <span data-ttu-id="45c04-155">Exploit Kit에 추가된 Exploit</span><span class="sxs-lookup"><span data-stu-id="45c04-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="45c04-156">Exploit가 확인된 경우</span><span class="sxs-lookup"><span data-stu-id="45c04-156">Exploit was verified</span></span>
    - <span data-ttu-id="45c04-157">새 공개 악용</span><span class="sxs-lookup"><span data-stu-id="45c04-157">New public exploit</span></span>
    - <span data-ttu-id="45c04-158">새로운 취약성</span><span class="sxs-lookup"><span data-stu-id="45c04-158">New vulnerability</span></span>
    - <span data-ttu-id="45c04-159">새 구성 평가</span><span class="sxs-lookup"><span data-stu-id="45c04-159">New configuration assessment</span></span>
- <span data-ttu-id="45c04-160">**점수 추세**: 노출 점수 추세</span><span class="sxs-lookup"><span data-stu-id="45c04-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="45c04-161">아이콘</span><span class="sxs-lookup"><span data-stu-id="45c04-161">Icons</span></span>

<span data-ttu-id="45c04-162">다음 아이콘은 이벤트 옆에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-162">The following icons show up next to events:</span></span>

- ![버그 아이콘](images/tvm-black-bug-icon.png) <span data-ttu-id="45c04-164">새 공개 악용</span><span class="sxs-lookup"><span data-stu-id="45c04-164">New public exploit</span></span>
- ![보고 경고 아이콘](images/report-warning-icon.png) <span data-ttu-id="45c04-166">새로운 취약성 게시</span><span class="sxs-lookup"><span data-stu-id="45c04-166">New vulnerability was published</span></span>
- ![exploit kit](images/bug-lightning-icon2.png) <span data-ttu-id="45c04-168">Exploit Kit에서 찾은 Exploit</span><span class="sxs-lookup"><span data-stu-id="45c04-168">Exploit found in exploit kit</span></span>
- ![경고 아이콘이 있는 버그 아이콘](images/bug-caution-icon2.png) <span data-ttu-id="45c04-170">악용 확인</span><span class="sxs-lookup"><span data-stu-id="45c04-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="45c04-171">특정 이벤트로 드릴다운</span><span class="sxs-lookup"><span data-stu-id="45c04-171">Drill down to a specific event</span></span>

<span data-ttu-id="45c04-172">이벤트를 선택하면 장치에 영향을 주는 세부 정보 및 현재 CV 목록과 함께 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="45c04-173">CV를 더 표시하거나 관련 권장 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="45c04-174">"점수 추세" 아래의 화살표를 사용하면 이 이벤트가 조직 노출 점수를 잠재적으로 발생 또는 낮출지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="45c04-175">노출 점수가 높을수록 장치가 악용에 더 취약하다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![이벤트 타임라인 플라이아웃](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="45c04-177">이 페이지에서 관련 보안 권장 사항 보기로 **이동을** 선택하여 보안 권장 사항 페이지에서 새로운 소프트웨어 취약성을 해결합니다. [](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="45c04-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="45c04-178">보안 권장 사항에서 설명 및 취약점 세부 정보를 읽은 후 수정 요청을 제출하고 수정 페이지에서 요청을 추적할 [수 있습니다.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="45c04-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="45c04-179">소프트웨어 페이지에서 이벤트 타임라인 보기</span><span class="sxs-lookup"><span data-stu-id="45c04-179">View Event timelines in software pages</span></span>

<span data-ttu-id="45c04-180">소프트웨어 페이지를 열 > 플라이아웃의 "관련 구성 요소" 섹션에서 하이퍼링크된 소프트웨어 이름(예: Visual Studio 2017)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="45c04-181">소프트웨어 페이지에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="45c04-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="45c04-182">전체 페이지가 특정 소프트웨어의 모든 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="45c04-183">그래프 위에 마우스를 놓아 특정 소프트웨어에 대한 이벤트 타임라인을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![이벤트 타임라인 그래프가 있는 소프트웨어 페이지](images/tvm-event-timeline-software2.png)

<span data-ttu-id="45c04-185">이벤트 타임라인 탭으로 이동하여 해당 소프트웨어와 관련된 모든 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="45c04-186">보안 권장 사항, 발견된 취약성, 설치된 장치 및 버전 배포도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c04-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![이벤트 타임라인 탭이 있는 소프트웨어 페이지](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="45c04-188">관련 항목</span><span class="sxs-lookup"><span data-stu-id="45c04-188">Related topics</span></span>

- [<span data-ttu-id="45c04-189">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="45c04-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="45c04-190">Dashboard</span><span class="sxs-lookup"><span data-stu-id="45c04-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="45c04-191">노출 점수</span><span class="sxs-lookup"><span data-stu-id="45c04-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="45c04-192">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="45c04-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="45c04-193">취약성 수정</span><span class="sxs-lookup"><span data-stu-id="45c04-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="45c04-194">소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="45c04-194">Software inventory</span></span>](tvm-software-inventory.md)

