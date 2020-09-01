---
title: Microsoft 보안 점수를 통해 보안 상황 평가
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
ms.openlocfilehash: 3b913b3d53abf8c46fbcc9e053f91f512864c9d8
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315834"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="9e2c4-104">Microsoft 보안 점수를 사용 하 여 보안 상황 평가</span><span class="sxs-lookup"><span data-stu-id="9e2c4-104">Assess your security posture with Microsoft Secure Score</span></span>

<span data-ttu-id="9e2c4-105">Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="9e2c4-106">이 도구 https://security.microsoft.com/securescore 는 [Microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="9e2c4-107">필요한 정보를 보다 신속 하 게 지원 하기 위해 Microsoft 개선 작업을 그룹으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="9e2c4-108">Id (Azure Active Directory 계정 & 역할)</span><span class="sxs-lookup"><span data-stu-id="9e2c4-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="9e2c4-109">데이터 (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="9e2c4-109">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="9e2c4-110">장치 ( [장치에 대 한 Microsoft 보안 점수](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)라고 알려진 MICROSOFT Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="9e2c4-110">Device (Microsoft Defender ATP, known as [Microsoft Secure Score for Devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="9e2c4-111">앱 (Office 365 및 Microsoft Cloud App Security)을 포함 하는 전자 메일 및 클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="9e2c4-111">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="9e2c4-112">인프라 (지금은 향상 작업 없음)</span><span class="sxs-lookup"><span data-stu-id="9e2c4-112">Infrastructure (no improvement actions for now)</span></span>

>[!NOTE]
><span data-ttu-id="9e2c4-113">Microsoft 보안 점수가 최근 릴리스에서는 Microsoft 보안 점수가 Id 보안 점수 및 그래프 API와 일시적으로 호환 되지 않는 향상 된 점수 매기기 모델이 출시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-113">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="9e2c4-114">자세히 보기</span><span class="sxs-lookup"><span data-stu-id="9e2c4-114">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="9e2c4-115">Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간 점 분할 방식 및 사용 가능한 점수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-115">In the Microsoft Secure Score overview page, see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="9e2c4-116">또한 전체 점수, 벤치 마크 비교가 포함 된 보안 점수의 역사적 추세, 점수를 높이기 위해 수행할 수 있는 우선 순위 지정 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-116">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="9e2c4-118">현재 점수 확인</span><span class="sxs-lookup"><span data-stu-id="9e2c4-118">Check your current score</span></span>

<span data-ttu-id="9e2c4-119">현재 점수를 확인 하려면 Microsoft 보안 점수 개요 페이지로 이동 하 여 **보안 점수가**있는 타일을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-119">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="9e2c4-120">점수는 총 가능한 점수에서 달성 한 점수와 함께 백분율로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-120">Your score will be shown as a percentage, along with the number of points you've achieved out of a total possible points.</span></span>

<span data-ttu-id="9e2c4-121">또한 점수 옆에 있는 **포함** 단추를 선택 하면 점수에 대 한 다양 한 보기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-121">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="9e2c4-122">이러한 서로 다른 점수 보기는 점수 타일 및 점 분석 차트의 그래프에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-122">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="9e2c4-123">다음과 같은 점수를 통해 전체 점수를 보기에 추가 하 여 전체 점수를 완벽 하 게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-123">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="9e2c4-124">**계획 된 점수**: 계획 된 작업이 완료 되 면 예상 점수 표시</span><span class="sxs-lookup"><span data-stu-id="9e2c4-124">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="9e2c4-125">**현재 사용권 점수**: 현재 Microsoft 라이선스로 얻을 수 있는 점수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-125">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="9e2c4-126">실현 가능한 **점수**: Microsoft 라이선스 및 현재 위험 수용으로 달성 가능한 점수 표시</span><span class="sxs-lookup"><span data-stu-id="9e2c4-126">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="9e2c4-127">이 보기는 가능한 모든 점수 보기를 포함 했을 때의 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-127">This view is what it will look like if you've included all possible score views:</span></span>

![계획 된 점수, 현재 라이선스 점수 및 달성 가능한 점수를 포함 하는 보안 점수](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="9e2c4-129">점수를 개선 하기 위한 조치 수행</span><span class="sxs-lookup"><span data-stu-id="9e2c4-129">Take action to improve your score</span></span>

<span data-ttu-id="9e2c4-130">**향상 작업** 탭에는 가능한 공격 표면을 해결 하는 보안 권장 사항이 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-130">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="9e2c4-131">또한 해당 상태 (주소, 계획 된 위험, 허용 됨, 타사를 통해 해결 됨, 대안 완화 및 완료 됨)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-131">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="9e2c4-132">모든 개선 작업을 검색, 필터링 및 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-132">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="9e2c4-133">순서</span><span class="sxs-lookup"><span data-stu-id="9e2c4-133">Ranking</span></span>

<span data-ttu-id="9e2c4-134">순위는 달성 하기 위해 남은 점수, 구현 난이도, 사용자 영향 및 복잡도에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-134">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="9e2c4-135">가장 높은 순위의 향상 작업에는 낮은 난이도, 사용자 영향 및 복잡도의 점수가 많이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-135">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="9e2c4-136">향상 작업 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="9e2c4-136">View improvement action details</span></span>

<span data-ttu-id="9e2c4-137">특정 향상 작업을 선택 하면 전체 페이지 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-137">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="9e2c4-138">![향상 작업 플라이 아웃 예 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *그림 2: 개선 작업 플라이 아웃 예제*</span><span class="sxs-lookup"><span data-stu-id="9e2c4-138">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="9e2c4-139">이 작업을 완료 하려면 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-139">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="9e2c4-140">**관리** 를 선택 하 여 구성 화면으로 이동 하 고 변경을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-140">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="9e2c4-141">그런 다음 동작의 가치를 즉시 파악할 수 있습니다. 점수는 일반적으로 업데이트 하는 데 약 24 시간이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-141">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="9e2c4-142">**공유** 를 선택 하 여 개선 작업에 대 한 직접 링크를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-142">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="9e2c4-143">또한 전자 메일, Microsoft 팀, Microsoft Planner 또는 ServiceNow와 같이 링크를 공유 하는 플랫폼을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-143">You can also choose the platform to share the link, such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="9e2c4-144">ServiceNow를 선택 하면 ServiceNow 및 Microsoft 365 보안 센터 홈에 표시 되는 변경 티켓을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-144">Selecting ServiceNow will let you create a change ticket that will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="9e2c4-145">자세한 내용은 [Microsoft 365 보안 센터 및 ServiceNow 통합](tickets-security-center.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-145">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="9e2c4-146">향상 작업 상태 선택</span><span class="sxs-lookup"><span data-stu-id="9e2c4-146">Choose an improvement action status</span></span>

<span data-ttu-id="9e2c4-147">상태를 선택 하 고 향상 작업과 관련 된 메모를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-147">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="9e2c4-148">**해결 방법** -개선 작업이 필요 하다는 것을 인식 하 고 미래에 특정 시점에 해결할 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-148">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="9e2c4-149">이 상태는 부분적으로 검색 되었지만 완전히 완료 되지 않은 작업에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-149">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="9e2c4-150">**계획** 됨-개선 작업을 완료 하기 위한 구체적인 계획을 수립 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-150">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="9e2c4-151">**위험 허용** -보안은 항상 유용성과 균형을 유지 해야 하며, 환경에 대 한 모든 권장 사항은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-151">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="9e2c4-152">이 경우 위험 또는 남은 위험을 수락 하 고 개선 작업을 적용 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-152">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="9e2c4-153">모든 점수를 제공 하는 것은 아니지만 해당 작업은 향상 작업 목록에 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-153">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="9e2c4-154">언제 든 지 기록에서이 작업을 보거나 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-154">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="9e2c4-155">타사 응용 프로그램 또는 소프트웨어 또는 내부 도구를 통해 **제 3 자를 통해 확인** 되 고 **대체 완화 작업을 통해 해결** 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-155">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="9e2c4-156">작업을 수행 하는 것이 가장 좋은 점수를 얻을 수 있으므로 점수가 사용자의 전체 보안 상태를 보다 잘 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-156">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="9e2c4-157">타사 또는 내부 도구가 더 이상 해당 컨트롤을 커버 하지 않으면 다른 상태를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-157">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="9e2c4-158">향상 작업이 이러한 상태 중 하나로 표시 된 경우 Microsoft는 구현의 완성도를 명확 하 게 파악할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-158">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="9e2c4-159">위협 & 취약성 관리 개선 작업</span><span class="sxs-lookup"><span data-stu-id="9e2c4-159">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="9e2c4-160">"장치" 범주의 향상 작업에 대해 상태를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-160">For improvement actions in the "Device" category, you won't be able to choose statuses.</span></span> <span data-ttu-id="9e2c4-161">대신 [Microsoft Defender 보안 센터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) 의 [tvm (& 취약성 관리) 보안 권장 사항을](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) 연결 하 여 조치를 취할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-161">Instead, you'll be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="9e2c4-162">선택한 예외와 작성 한 사유는 해당 포털에 한정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-162">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="9e2c4-163">Microsoft 보안 점수 포털에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-163">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="9e2c4-164">완료 된 개선 작업</span><span class="sxs-lookup"><span data-stu-id="9e2c4-164">Completed improvement actions</span></span>

<span data-ttu-id="9e2c4-165">향상 작업에 대 한 가능한 모든 점수를 얻은 후에는 개선 조치에 "완료 됨" 상태가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-165">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="9e2c4-166">완료 된 개선 작업은 Microsoft 데이터를 통해 확인 되며 상태를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-166">Completed improvement actions are confirmed though Microsoft data, and you won't be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="9e2c4-167">정보 평가 및 사용자 영향 검토</span><span class="sxs-lookup"><span data-stu-id="9e2c4-167">Assess information and review user impact</span></span>

<span data-ttu-id="9e2c4-168">이 **섹션에서 설명** 하는 부분은 범주, 보안을 통해 보호할 수 있는 공격 및 제품에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-168">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="9e2c4-169">**사용자 영향** 에 따라 개선 작업이 실행 되는 경우 사용자에 게 발생할 항목이 표시 되 고, **영향을 받는 사용자** 에 게는이를 표시할 사람이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-169">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="9e2c4-170">개선 작업 구현</span><span class="sxs-lookup"><span data-stu-id="9e2c4-170">Implement the improvement action</span></span>

<span data-ttu-id="9e2c4-171">**구현** 섹션에는 개선 작업을 완료 하기 위한 다음 단계, 개선 작업의 현재 구현 상태 및 자세한 링크를 보여 주는 모든 필수 구성 요소, 단계별 단계가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-171">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="9e2c4-172">필수 구성 요소에는 개선 작업을 처리 하기 전에 수행 해야 하는 모든 라이선스 또는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-172">Prerequisites include any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="9e2c4-173">라이선스에 개선 작업을 완료 하 고 해당 라이선스가 필요한 사용자에 게 적용 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-173">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="9e2c4-174">사용자의 의견을 듣고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-174">We want to hear from you</span></span>

<span data-ttu-id="9e2c4-175">문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에 게시 하 여 알려 주세요.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-175">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="9e2c4-176">당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e2c4-176">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="9e2c4-177">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="9e2c4-177">Related resources</span></span>

- [<span data-ttu-id="9e2c4-178">Microsoft 보안 점수 개요</span><span class="sxs-lookup"><span data-stu-id="9e2c4-178">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="9e2c4-179">Microsoft 보안 점수 기록 및 목표를 충족 하는 추적</span><span class="sxs-lookup"><span data-stu-id="9e2c4-179">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="9e2c4-180">향후 계획</span><span class="sxs-lookup"><span data-stu-id="9e2c4-180">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="9e2c4-181">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="9e2c4-181">What's new</span></span>](microsoft-secure-score-whats-new.md)