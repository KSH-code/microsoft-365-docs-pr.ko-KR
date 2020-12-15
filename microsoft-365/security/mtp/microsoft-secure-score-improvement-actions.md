---
title: Microsoft 보안 점수를 통해 보안 환경 평가
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수를 개선하기 위한 조치를 취하는 방법을 설명 합니다.
keywords: Microsoft 보안 점수, 보안 점수, Office 365 보안 점수, Microsoft 보안 점수, Microsoft 365 보안 센터, 개선 작업
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
ms.openlocfilehash: 8ebfe5746a69cc0161c38f0467954fabb3839240
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683346"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="61e63-104">Microsoft 보안 점수를 통해 보안 환경 평가</span><span class="sxs-lookup"><span data-stu-id="61e63-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="61e63-105">Microsoft 보안 점수는 조직의 보안 자세를 측정한 결과로, 수치가 높을수록 개선 작업이 더 많이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="61e63-106">Microsoft https://security.microsoft.com/securescore [365](overview-security-center.md)보안 센터에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="61e63-107">필요한 정보를 보다 빠르게 지원하기 위해 Microsoft 개선 작업은 그룹으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="61e63-108">ID(Azure Active Directory 계정 &)</span><span class="sxs-lookup"><span data-stu-id="61e63-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="61e63-109">장치(장치용 Microsoft 보안 점수라고도 [하는 끝점용 Microsoft Defender)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)</span><span class="sxs-lookup"><span data-stu-id="61e63-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="61e63-110">앱(Office 365 및 Microsoft Cloud App Security를 포함한 전자 메일 및 클라우드 앱)</span><span class="sxs-lookup"><span data-stu-id="61e63-110">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="61e63-111">Microsoft 보안 점수의 최근 릴리스에서는 Microsoft 보안 점수가 ID 보안 점수 및 Graph API와 일시적으로 양자화되지 않는 향상된 점수 매기기 모델이 릴리스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="61e63-112">자세히 보기</span><span class="sxs-lookup"><span data-stu-id="61e63-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="61e63-113">Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간에 점수가 분할된 방식과 사용 가능한 포인트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61e63-113">In the Microsoft Secure Score overview page, see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="61e63-114">또한 전체 점수, 벤치마크 비교를 사용하여 보안 점수의 기록 추세, 점수를 개선하기 위해 수행할 수 있는 우선 순위가 높은 개선 작업을 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="61e63-116">현재 점수 확인</span><span class="sxs-lookup"><span data-stu-id="61e63-116">Check your current score</span></span>

<span data-ttu-id="61e63-117">현재 점수를 확인한 후 Microsoft 보안 점수 개요 페이지로 이동하여 보안 점수가 표시되어 있는 **타일을 찾아 봐야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="61e63-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="61e63-118">점수는 가능한 총 점수에서 달성한 점수 수와 함께 백분율로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-118">Your score will be shown as a percentage, along with the number of points you've achieved out of a total possible points.</span></span>

<span data-ttu-id="61e63-119">또한 점수 옆에 있는  포함 단추를 선택하는 경우 점수의 다양한 보기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="61e63-120">이러한 서로 다른 점수 보기는 점수 타일 및 점 분석 차트의 그래프에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="61e63-121">다음은 전체 점수의 보기에 추가하여 전체 점수에 대한 더 많은 그림을 제공 할 수 있는 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="61e63-122">**계획된 점수**: 계획된 작업이 완료된 경우의 예정된 점수 표시</span><span class="sxs-lookup"><span data-stu-id="61e63-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="61e63-123">**현재 라이선스 점수:** 현재 Microsoft 라이선스로 달성할 수 있는 점수 표시</span><span class="sxs-lookup"><span data-stu-id="61e63-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="61e63-124">**달성 가능한 점수:** Microsoft 라이선스 및 현재 위험 수용으로 달성할 수 있는 점수 표시</span><span class="sxs-lookup"><span data-stu-id="61e63-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="61e63-125">이 보기는 가능한 모든 점수 보기를 포함하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-125">This view is what it will look like if you've included all possible score views:</span></span>

![계획된 점수, 현재 라이선스 점수 및 달성 가능한 점수를 포함한 보안 점수](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="61e63-127">점수 향상을 위한 조치 수행</span><span class="sxs-lookup"><span data-stu-id="61e63-127">Take action to improve your score</span></span>

<span data-ttu-id="61e63-128">개선 **작업 탭에는** 가능한 공격 표면을 해결하기 위한 보안 권장 사항이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="61e63-129">또한 해당 상태(해결, 계획, 위험 수락, 타사를 통해 해결, 대체 완화를 통해 해결 및 완료)도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="61e63-130">모든 개선 작업을 검색, 필터링 및 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="61e63-131">순위</span><span class="sxs-lookup"><span data-stu-id="61e63-131">Ranking</span></span>

<span data-ttu-id="61e63-132">순위는 달성하기 위해 남은 점수 수, 구현 난이도, 사용자 영향 및 복잡성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="61e63-133">순위가 가장 높은 개선 작업은 난이도, 사용자 영향 및 복잡성이 낮은 점수로 남습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="61e63-134">개선 작업 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="61e63-134">View improvement action details</span></span>

<span data-ttu-id="61e63-135">특정 개선 작업을 선택하면 전체 페이지 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="61e63-136">![개선 작업 플라이아웃 예제 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *그림 2: 개선 작업 플라이아웃 예제*</span><span class="sxs-lookup"><span data-stu-id="61e63-136">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="61e63-137">작업을 완료하기 위해 다음과 같은 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-137">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="61e63-138">구성 **화면으로** 이동하여 변경하려면 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="61e63-139">그런 다음 작업을 플라이아웃에서 볼 수 있는 가치가 있는 포인트를 얻게 됩니다. 일반적으로 포인트는 업데이트하는 데 24시간 정도 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="61e63-140">**공유를** 선택하여 개선 작업으로 직접 링크를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="61e63-141">전자 메일, Microsoft Teams, Microsoft Planner 또는 ServiceNow와 같은 링크를 공유할 플랫폼을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-141">You can also choose the platform to share the link, such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="61e63-142">ServiceNow를 선택하면 ServiceNow 및 Microsoft 365 보안 센터 홈에 표시되는 변경 티켓을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-142">Selecting ServiceNow will let you create a change ticket that will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="61e63-143">자세한 내용은 Microsoft 365 보안 센터 및 [ServiceNow 통합을 참조합니다.](tickets-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="61e63-143">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="61e63-144">개선 작업 상태 선택</span><span class="sxs-lookup"><span data-stu-id="61e63-144">Choose an improvement action status</span></span>

<span data-ttu-id="61e63-145">상태를 선택하고 개선 작업과 관련한 메모를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-145">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="61e63-146">**주소 -** 개선 작업이 필요하다는 사실과 향후에 해결될 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-146">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="61e63-147">이 상태는 부분적으로 검색되지만 완전히 완료되지 않은 작업에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-147">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="61e63-148">**계획** - 개선 작업을 완료하기 위한 구체적인 계획이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-148">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="61e63-149">**위험 수락** - 보안은 항상 사용 가능성과 균형을 유지해야 합니다. 모든 권장이 사용자 환경에 작동하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-149">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="61e63-150">이 경우 위험 또는 남은 위험을 수용할 수 있으며 개선 작업을 제정하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-150">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="61e63-151">점수는 부여되지 않지만 작업이 개선 작업 목록에 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-151">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="61e63-152">이 동작은 기록으로 보거나 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-152">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="61e63-153">**타사를** 통해 해결되고 대체 완화를 통해 **해결되었습니다.** 개선 작업은 타사 응용 프로그램 또는 소프트웨어 또는 내부 도구를 통해 이미 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-153">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="61e63-154">작업의 가치가 있는 점수를 얻을 수 있으므로 점수가 전반적인 보안 자세를 더 잘 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-154">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="61e63-155">타사 또는 내부 도구가 더 이상 컨트롤을 다루지 못하면 다른 상태를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-155">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="61e63-156">개선 작업이 이러한 상태 중 하나로 표시되어 있는 경우 Microsoft는 구현의 완성도에 대한 가시성을 확보하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-156">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="61e63-157">위협 & 관리 개선 작업</span><span class="sxs-lookup"><span data-stu-id="61e63-157">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="61e63-158">"장치" 범주의 개선 작업의 경우 상태를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-158">For improvement actions in the "Device" category, you won't be able to choose statuses.</span></span> <span data-ttu-id="61e63-159">대신 Microsoft [Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) 보안 센터의 관련 위협 & [취약성 관리(취약점 관리)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) 보안 권장 지침으로 연결하여 조치를 취하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-159">Instead, you'll be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="61e63-160">선택한 예외 및 작성 사당성은 해당 포털과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-160">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="61e63-161">Microsoft 보안 점수 포털에는 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-161">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="61e63-162">개선 작업 완료</span><span class="sxs-lookup"><span data-stu-id="61e63-162">Completed improvement actions</span></span>

<span data-ttu-id="61e63-163">개선 작업의 가능한 모든 지점이 달성된 경우 개선 작업이 "완료" 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="61e63-164">완료된 개선 작업은 Microsoft 데이터를 통해 확인하며 상태를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-164">Completed improvement actions are confirmed though Microsoft data, and you won't be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="61e63-165">정보 평가 및 사용자 영향 검토</span><span class="sxs-lookup"><span data-stu-id="61e63-165">Assess information and review user impact</span></span>

<span data-ttu-id="61e63-166">이 **섹션에서는** 범주, 공격으로부터 보호할 수 있는 공격 및 제품을 한눈에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-166">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="61e63-167">사용자 **영향은** 개선 작업이 제정된 경우 사용자에게 어떤  영향을 주는지 보여 주며 영향을 받는 사용자에게는 해당 작업을 경험할 수 있는 사람이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-167">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="61e63-168">개선 작업 구현</span><span class="sxs-lookup"><span data-stu-id="61e63-168">Implement the improvement action</span></span>

<span data-ttu-id="61e63-169">구현 **섹션에는** 개선 작업을 완료하기 위한 모든 선행 작업, 단계별 다음 단계, 개선 작업의 현재 구현 상태 및 자세한 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-169">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="61e63-170">선행 요구에는 획득해야 하는 라이선스 또는 개선 조치가 해결되기 전에 완료해야 하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-170">Prerequisites include any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="61e63-171">라이선스에 사용자 수가 충분한지 확인하여 개선 작업을 완료하고 해당 라이선스가 필요한 사용자에게 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="61e63-172">의견을 보내 주세요.</span><span class="sxs-lookup"><span data-stu-id="61e63-172">We want to hear from you</span></span>

<span data-ttu-id="61e63-173">문제가 있는 경우 보안, 개인 정보 보호 및 규정 준수 커뮤니티에 게시하여 [& 알려주세요.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="61e63-173">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="61e63-174">커뮤니티를 모니터링하고 있으며 도움을 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61e63-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="61e63-175">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="61e63-175">Related resources</span></span>

- [<span data-ttu-id="61e63-176">Microsoft 보안 점수 개요</span><span class="sxs-lookup"><span data-stu-id="61e63-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="61e63-177">Microsoft 보안 점수 기록 추적 및 목표 충족</span><span class="sxs-lookup"><span data-stu-id="61e63-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="61e63-178">향후 계획</span><span class="sxs-lookup"><span data-stu-id="61e63-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="61e63-179">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="61e63-179">What's new</span></span>](microsoft-secure-score-whats-new.md)
