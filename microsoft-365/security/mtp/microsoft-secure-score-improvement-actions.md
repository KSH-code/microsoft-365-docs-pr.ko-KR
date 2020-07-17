---
title: Microsoft 보안 점수를 통한 보안 상황에 대 한 가시성 획득
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수를 개선 하기 위한 조치를 취하는 방법에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 점수, 보안 센터, 개선 작업
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 0ae1a196f11f383c1d3f9fd2056d5d19e7cdd6da
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45095074"
---
# <a name="gain-visibility-into-your-security-posture-through-microsoft-secure-score"></a><span data-ttu-id="296e7-104">Microsoft 보안 점수를 통한 보안 상황에 대 한 가시성 획득</span><span class="sxs-lookup"><span data-stu-id="296e7-104">Gain visibility into your security posture through Microsoft Secure Score</span></span>

<span data-ttu-id="296e7-105">Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="296e7-106">이 도구 https://security.microsoft.com/securescore 는 [Microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="296e7-107">필요한 정보를 보다 신속 하 게 지원 하기 위해 Microsoft 개선 작업을 그룹으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="296e7-108">Id (Azure AD 계정 & 역할)</span><span class="sxs-lookup"><span data-stu-id="296e7-108">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="296e7-109">데이터 (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="296e7-109">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="296e7-110">장치 ( [구성 점수](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)라고 알려진 MICROSOFT Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="296e7-110">Device (Microsoft Defender ATP, known as [Configuration score](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score))</span></span>
* <span data-ttu-id="296e7-111">앱 (Office 365 및 Microsoft Cloud App Security)을 포함 하는 전자 메일 및 클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="296e7-111">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="296e7-112">인프라 (지금은 향상 작업 없음)</span><span class="sxs-lookup"><span data-stu-id="296e7-112">Infrastructure (no improvement actions for now)</span></span>

>[!NOTE]
><span data-ttu-id="296e7-113">Microsoft 보안 점수가 최근 릴리스에서는 Microsoft 보안 점수가 Id 보안 점수 및 그래프 API와 일시적으로 호환 되지 않는 향상 된 점수 매기기 모델이 출시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-113">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="296e7-114">자세히 보기</span><span class="sxs-lookup"><span data-stu-id="296e7-114">View details</span></span>](microsoft-secure-score.md#incompatibility-with-identity-secure-score-and-graph-api)

<span data-ttu-id="296e7-115">Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간의 점수가 분할 되는 방식과 사용할 수 있는 지점을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-115">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="296e7-116">개요 페이지는 또한 전체 점수에 대 한 모든 보기, 벤치 마크 비교를 사용한 보안 점수의 역사적 추세 및 점수를 높이기 위해 수행할 수 있는 향상 작업의 우선 순위를 지정 하는 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-116">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="296e7-118">현재 점수 확인</span><span class="sxs-lookup"><span data-stu-id="296e7-118">Check your current score</span></span>

<span data-ttu-id="296e7-119">현재 점수를 확인 하려면 Microsoft 보안 점수 개요 페이지로 이동 하 여 **보안 점수가**있는 타일을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-119">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="296e7-120">점수는 총 가능한 최대 점수까지 달성 한 점수와 함께 백분율로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-120">Your score will be shown as a percentage, along with the number of points you have achieved out of a total possible points.</span></span>

<span data-ttu-id="296e7-121">또한 점수 옆에 있는 **포함** 단추를 선택 하면 점수에 대 한 다양 한 보기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-121">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="296e7-122">이러한 서로 다른 점수 보기는 점수 타일 및 점 분석 차트의 그래프에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-122">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="296e7-123">다음과 같은 점수를 통해 전체 점수를 보기에 추가 하 여 전체 점수를 완벽 하 게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-123">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="296e7-124">**계획 된 점수**: 계획 된 작업이 완료 되 면 예상 점수 표시</span><span class="sxs-lookup"><span data-stu-id="296e7-124">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="296e7-125">**현재 사용권 점수**: 현재 Microsoft 라이선스로 얻을 수 있는 점수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-125">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="296e7-126">실현 가능한 **점수**: Microsoft 라이선스 및 현재 위험 수용으로 달성 가능한 점수 표시</span><span class="sxs-lookup"><span data-stu-id="296e7-126">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="296e7-127">가능한 모든 점수 보기를 포함 하는 경우 표시 되는 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-127">This is what it will look like if you have included all possible score views:</span></span>

![계획 된 점수, 현재 라이선스 점수 및 달성 가능한 점수를 포함 하는 보안 점수](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="296e7-129">점수를 개선 하기 위한 조치 수행</span><span class="sxs-lookup"><span data-stu-id="296e7-129">Take action to improve your score</span></span>

<span data-ttu-id="296e7-130">**향상 작업** 탭에는 가능한 공격 지를 확인 하는 보안 권장 사항과 함께 해당 상태 (주소, 계획 된 위험, 허용 됨, 제 3 자가 해결 됨, 대안 완화 및 완료 됨)가 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-130">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces, along with their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="296e7-131">모든 개선 작업을 검색, 필터링 및 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-131">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="296e7-132">순서</span><span class="sxs-lookup"><span data-stu-id="296e7-132">Ranking</span></span>

<span data-ttu-id="296e7-133">순위는 달성할 수 있는 남은 점수, 구현 난이도, 사용자 영향 및 복잡도를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-133">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="296e7-134">가장 높은 순위의 향상 작업에는 낮은 난이도, 사용자 영향 및 복잡도의 점수가 많이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-134">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="296e7-135">향상 작업 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="296e7-135">View improvement action details</span></span>

<span data-ttu-id="296e7-136">특정 향상 작업을 선택 하면 전체 페이지 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-136">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="296e7-137">![향상 작업 플라이 아웃 예 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *그림 2: 개선 작업 플라이 아웃 예제*</span><span class="sxs-lookup"><span data-stu-id="296e7-137">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="296e7-138">이 작업을 완료 하려면 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-138">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="296e7-139">**관리** 를 선택 하 여 구성 화면으로 이동 하 고 변경을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-139">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="296e7-140">그런 다음 동작이 가치 있는 점수를 얻게 되며 플라이 아웃 됩니다. 점수는 일반적으로 업데이트 하는 데 약 24 시간이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-140">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="296e7-141">**공유** 를 선택 하 여 개선 작업에 대 한 직접 링크를 복사 하거나, 전자 메일, microsoft 팀, Microsoft Planner 또는 ServiceNow와 같은 링크를 공유할 플랫폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-141">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="296e7-142">ServiceNow를 선택 하면 ServiceNow 및 Microsoft 365 보안 센터 홈에 표시 되는 변경 티켓을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-142">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="296e7-143">자세한 내용은 [Microsoft 365 보안 센터 및 ServiceNow 통합](tickets-security-center.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="296e7-143">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="296e7-144">향상 작업 상태 선택</span><span class="sxs-lookup"><span data-stu-id="296e7-144">Choose an improvement action status</span></span>

<span data-ttu-id="296e7-145">상태를 선택 하 고 향상 작업과 관련 된 메모를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-145">Choose any statuses and record notes specific to the improvement action.</span></span> <span data-ttu-id="296e7-146">선택할 수 있는 동상은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-146">The statues you can select are the following:</span></span>

* <span data-ttu-id="296e7-147">**해결 방법** : 개선 작업이 필요한 지를 인식 하 고 미래에 특정 시점에 해결할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-147">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="296e7-148">이 상태는 부분적으로 검색 되었지만 완전히 완료 되지 않은 작업에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-148">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
* <span data-ttu-id="296e7-149">**계획** 됨-개선 작업을 완료 하기 위한 구체적인 계획이 마련 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-149">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
* <span data-ttu-id="296e7-150">**위험 수락** -보안이 항상 유용성과 균형을 유지 해야 하며, 환경에 대 한 모든 권장 사항이 적합 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-150">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="296e7-151">이 경우 위험 또는 남은 위험을 수락 하 고 개선 작업을 적용 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-151">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="296e7-152">모든 점수를 제공 하는 것은 아니지만 해당 작업은 개선 작업 목록에 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-152">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="296e7-153">언제 든 지 기록에서이 작업을 보거나 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-153">You can view this action in history or undo it at any time.</span></span>
* <span data-ttu-id="296e7-154">타사 응용 프로그램 또는 소프트웨어 또는 내부 도구로 이미 향상 된 기능을 사용 하 여 타사에서 **확인** 하 고 **다른 완화 작업을 통해 해결** 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-154">**Resolved through third party** and **Resolved through alternate mitigation** — The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="296e7-155">작업을 수행 하는 점수를 얻게 되므로 점수가 향상 되어 전반적인 보안 환경을 보다 효율적으로 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-155">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="296e7-156">타사 또는 내부 도구가 더 이상 해당 컨트롤을 커버 하지 않으면 다른 상태를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-156">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="296e7-157">향상 작업이 이러한 상태 중 하나로 표시 되는 경우 Microsoft는 구현의 완성도를 명확 하 게 파악할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-157">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="296e7-158">위협 & 취약성 관리 개선 작업</span><span class="sxs-lookup"><span data-stu-id="296e7-158">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="296e7-159">"장치" 범주의 향상 작업을 수행 하는 경우 상태를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-159">For improvement actions in the "Device" category, you will not be able to choose statuses.</span></span> <span data-ttu-id="296e7-160">대신 [Microsoft Defender 보안 센터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) 의 [tvm (& 취약성 관리) 보안 권장 사항을](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) 연결 하 여 조치를 취할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-160">Instead, you will be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="296e7-161">선택한 예외 및 작성 한 사유는 해당 포털에만 적용 되며 Microsoft 보안 점수 포털에는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-161">The exception you choose and justification you write will specific to that portal, and will not be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="296e7-162">완료 된 개선 작업</span><span class="sxs-lookup"><span data-stu-id="296e7-162">Completed improvement actions</span></span>

<span data-ttu-id="296e7-163">향상 작업에 대 한 가능한 모든 점수를 얻은 후에는 개선 조치에 "완료 됨" 상태가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="296e7-164">완료 된 개선 작업은 Microsoft 데이터를 통해 확인 되며 상태를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-164">Completed improvement actions are confirmed though Microsoft data, and you will not be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="296e7-165">정보 평가 및 사용자 영향 검토</span><span class="sxs-lookup"><span data-stu-id="296e7-165">Assess information and review user impact</span></span>

<span data-ttu-id="296e7-166">**살펴보기** 섹션에는 범주, 제품에 대해 보호할 수 있는 공격 및 제품이 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-166">The **At a glance** section will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="296e7-167">**사용자 영향** 에 따라 개선 작업이 실행 되는 경우 사용자에 게 발생할 항목이 표시 되 고, **영향을 받는 사용자** 에 게는이를 표시할 사람이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-167">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="296e7-168">개선 작업 구현</span><span class="sxs-lookup"><span data-stu-id="296e7-168">Implement the improvement action</span></span>

<span data-ttu-id="296e7-169">**구현** 섹션에서는 다음 단계에 따라 개선 작업을 완료 하기 위한 단계, 개선 작업의 현재 구현 상태 및 자세한 링크를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-169">The **Implementation** section shows any prerequisites, step by step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="296e7-170">필수 구성 요소는 개선 작업을 처리 하기 전에 완료 해야 하는 작업 또는 획득 해야 하는 모든 라이선스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-170">Prerequisites will be any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="296e7-171">라이선스에 개선 작업을 완료 하 고 해당 라이선스가 필요한 사용자에 게 적용 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="296e7-172">사용자의 의견을 듣고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-172">We want to hear from you</span></span>

<span data-ttu-id="296e7-173">문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에서 게시할 때 알려주십시오.</span><span class="sxs-lookup"><span data-stu-id="296e7-173">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="296e7-174">당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="296e7-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="296e7-175">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="296e7-175">Related resources</span></span>

- [<span data-ttu-id="296e7-176">Microsoft 보안 점수 개요</span><span class="sxs-lookup"><span data-stu-id="296e7-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="296e7-177">Microsoft 보안 점수 기록 및 목표를 충족 하는 추적</span><span class="sxs-lookup"><span data-stu-id="296e7-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="296e7-178">향후 계획</span><span class="sxs-lookup"><span data-stu-id="296e7-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)