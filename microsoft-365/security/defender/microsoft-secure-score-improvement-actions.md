---
title: Microsoft 보안 점수를 통해 보안 환경 평가
description: 보안 센터에서 Microsoft 보안 점수를 개선하기 위한 조치를 Microsoft 365 설명
keywords: Microsoft 보안 점수, 보안 점수, Office 365 보안 점수, Microsoft 보안 점수, Microsoft 365 보안 센터, 개선 작업
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.technology: m365d
ms.openlocfilehash: 8b321fc8883cf490cb5b2814d5c2b617a52dbb29
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246400"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="4df47-104">Microsoft 보안 점수를 통해 보안 환경 평가</span><span class="sxs-lookup"><span data-stu-id="4df47-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4df47-105">Microsoft Secure Score는 조직의 보안 태세에 대한 평가 점수로, 점수가 높을수록 더 많은 개선 작업이 수행되었다는 뜻입니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="4df47-106">이 사이트는 보안 센터의 https://security.microsoft.com/securescore Microsoft 365 [있습니다.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="4df47-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="4df47-107">필요한 정보를 더 빠르게 찾을 수 있도록 Microsoft 개선 작업은 그룹으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-107">To help you find the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="4df47-108">ID(Azure Active Directory 계정 & 역할)</span><span class="sxs-lookup"><span data-stu-id="4df47-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="4df47-109">Device (Microsoft Defender for Endpoint, known [as Microsoft Secure Score for Devices)](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)</span><span class="sxs-lookup"><span data-stu-id="4df47-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="4df47-110">앱(전자 메일 및 클라우드 앱(Office 365 및 Microsoft Cloud App Security)</span><span class="sxs-lookup"><span data-stu-id="4df47-110">Apps (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="4df47-111">Microsoft 보안 점수의 최근 릴리스에서는 향상된 점수 모델이 릴리스되어 Microsoft 보안 점수가 ID 보안 점수 및 Graph API와 일시적으로 Graph 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="4df47-112">자세히 보기</span><span class="sxs-lookup"><span data-stu-id="4df47-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="4df47-113">Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간에 점수가 분할된 방법과 사용 가능한 포인트를 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-113">In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available.</span></span> <span data-ttu-id="4df47-114">또한 총 점수, 벤치마크 비교를 통해 보안 점수의 기록 추세, 점수를 개선하기 위해 수행할 수 있는 우선 순위가 높은 개선 작업에 대한 전체 보기를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![보안 점수 홈페이지](../../media/secure-score/secure-score-home-page.png)

## <a name="check-your-current-score"></a><span data-ttu-id="4df47-116">현재 점수 확인</span><span class="sxs-lookup"><span data-stu-id="4df47-116">Check your current score</span></span>

<span data-ttu-id="4df47-117">현재 점수를 확인하기 위해 Microsoft 보안 점수 개요 페이지로 이동하여 보안 점수 를 표시하는 **타일을 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="4df47-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="4df47-118">점수는 가능한 총 점수 중 달성한 점수 수와 함께 백분율로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-118">Your score will be shown as a percentage, along with the number of points you've achieved out of the total possible points.</span></span>

<span data-ttu-id="4df47-119">또한 점수 옆에 있는  포함 단추를 선택하는 경우 점수의 다양한 보기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="4df47-120">이러한 서로 다른 점수 보기는 점수 타일 및 점 분석 차트의 그래프에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="4df47-121">다음은 전체 점수의 보기에 추가하여 전체 점수에 대한 전체적인 그림을 볼 수 있는 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="4df47-122">**계획된 점수:** 계획된 작업이 완료된 경우의 예정된 점수 표시</span><span class="sxs-lookup"><span data-stu-id="4df47-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="4df47-123">**현재 라이선스 점수:** 현재 Microsoft 라이선스로 달성할 수 있는 점수 표시</span><span class="sxs-lookup"><span data-stu-id="4df47-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="4df47-124">**달성 가능한 점수:** Microsoft 라이선스 및 현재 위험 수용으로 달성할 수 있는 점수 표시</span><span class="sxs-lookup"><span data-stu-id="4df47-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="4df47-125">이 보기는 가능한 모든 점수 보기를 포함하면 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-125">This view is what it will look like if you've included all possible score views:</span></span>

![계획된 점수, 현재 라이선스 점수 및 달성 가능한 점수를 포함한 보안 점수](../../media/secure-score/secure-score-achievable.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="4df47-127">점수 향상을 위한 조치 수행</span><span class="sxs-lookup"><span data-stu-id="4df47-127">Take action to improve your score</span></span>

<span data-ttu-id="4df47-128">개선 **작업 탭에는** 가능한 공격 표면을 해결하기 위한 보안 권장 사항이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="4df47-129">또한 해당 상태(해결, 계획, 위험 수락, 타사를 통해 해결, 대체 완화를 통해 해결 및 완료)도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="4df47-130">모든 개선 작업을 검색, 필터링 및 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="4df47-131">순위</span><span class="sxs-lookup"><span data-stu-id="4df47-131">Ranking</span></span>

<span data-ttu-id="4df47-132">순위는 달성하기 위해 남은 포인트 수, 구현 난이도, 사용자 영향 및 복잡성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="4df47-133">가장 높은 순위의 개선 작업에는 난이도, 사용자 영향 및 복잡성이 낮은 점수가 남습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="4df47-134">개선 작업 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="4df47-134">View improvement action details</span></span>

<span data-ttu-id="4df47-135">특정 개선 작업을 선택하면 전체 페이지 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

![개선 작업 플라이아웃 예제](../../media/secure-score/secure-score-improvement-action-details.png)

<span data-ttu-id="4df47-137">작업을 완료하기 위해 다음과 같은 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-137">To complete the action, you have a few options:</span></span>

- <span data-ttu-id="4df47-138">관리를 **선택하여** 구성 화면으로 이동하고 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="4df47-139">그런 다음 작업의 가치와 플라이아웃에 표시되는 포인트를 얻게 됩니다. 포인트는 일반적으로 업데이트하는 데 24시간 정도 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

- <span data-ttu-id="4df47-140">**공유를** 선택하여 개선 작업으로 직접 링크를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="4df47-141">전자 메일, 메일 또는 Microsoft Planner와 같은 링크를 공유할 플랫폼을 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-141">You can also choose the platform to share the link, such as email, Microsoft Teams, or Microsoft Planner.</span></span>

<span data-ttu-id="4df47-142">**메모를** 추가하여 진행 상황을 추적하거나 메모를 남기고자 하는 기타 모든 것을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-142">Add **Notes** to keep track of progress or anything else you want to comment on.</span></span> <span data-ttu-id="4df47-143">개선 작업에서  자체 태그를 추가하는 경우 해당 태그를 사용하여 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-143">If you add your own **tags** to the improvement action, you can filter by those tags.</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="4df47-144">개선 작업 상태 선택</span><span class="sxs-lookup"><span data-stu-id="4df47-144">Choose an improvement action status</span></span>

<span data-ttu-id="4df47-145">상태를 선택하고 개선 작업과 관련한 메모를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-145">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="4df47-146">**주소 -** 개선 작업이 필요하다는 사실과 향후에 해결될 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-146">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="4df47-147">이 상태는 부분적으로 검색되지만 완전히 완료되지는 않은 작업에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-147">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="4df47-148">**계획** - 개선 작업을 완료하기 위한 구체적인 계획이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-148">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="4df47-149">**위험 수락** - 보안은 항상 사용 가능성과 균형을 조정해야 합니다. 모든 권장이 사용자 환경에 대해 작동하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-149">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="4df47-150">이 경우 위험 또는 남은 위험을 수용할 수 있으며 개선 작업을 실행하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-150">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="4df47-151">점은 제공되지 않지만 동작이 개선 작업 목록에 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-151">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="4df47-152">이 작업은 기록에서 보거나 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-152">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="4df47-153">**타사를 통해** 해결되고 대체 완화를 통해 해결 **-** 개선 작업은 타사 응용 프로그램 또는 소프트웨어 또는 내부 도구를 통해 이미 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-153">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="4df47-154">작업의 가치가 있는 점수를 얻게 있으므로 점수가 전반적인 보안 자세를 더 잘 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-154">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="4df47-155">타사 또는 내부 도구가 더 이상 컨트롤을 덮지 못하면 다른 상태를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-155">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="4df47-156">개선 작업이 이러한 상태 중 하나로 표시된 경우 Microsoft는 구현의 완전성을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-156">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="4df47-157">위협 & 취약성 관리 개선 작업</span><span class="sxs-lookup"><span data-stu-id="4df47-157">Threat & vulnerability management improvement actions</span></span>

<span data-ttu-id="4df47-158">"장치" 범주의 개선 작업의 경우 상태를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-158">For improvement actions in the "Device" category, you can't choose statuses.</span></span> <span data-ttu-id="4df47-159">대신 작업 수행을 위한 위협 및 취약성 관리 보안 [](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) 권장 Microsoft Defender 보안 센터 합니다. [](/windows/security/threat-protection/microsoft-defender-atp/use)</span><span class="sxs-lookup"><span data-stu-id="4df47-159">Instead, you'll be directed to the associated [threat and vulnerability management security recommendation](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="4df47-160">선택한 예외 및 작성 사당성은 해당 포털과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-160">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="4df47-161">Microsoft 보안 점수 포털에는 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-161">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="4df47-162">개선 작업 완료</span><span class="sxs-lookup"><span data-stu-id="4df47-162">Completed improvement actions</span></span>

<span data-ttu-id="4df47-163">개선 작업에 대해 가능한 모든 점수가 달성된 경우 개선 작업은 "완료" 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="4df47-164">Microsoft 데이터를 통해 개선 작업이 완료된 것으로 확인되면 상태를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-164">Completed improvement actions are confirmed though Microsoft data, and you can't change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="4df47-165">정보 평가 및 사용자 영향 검토</span><span class="sxs-lookup"><span data-stu-id="4df47-165">Assess information and review user impact</span></span>

<span data-ttu-id="4df47-166">이라는 **섹션은** 범주, 범주가 보호할 수 있는 공격 및 제품을 한눈에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-166">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="4df47-167">**사용자 영향** 개선 작업이 제정된 경우 사용자가 경험할  수 있으며 영향을 받는 사용자는 영향을 받는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-167">**User impact** is what the users will experience if the improvement action is enacted, and **Users affected** are the people who will be impacted.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="4df47-168">개선 작업 구현</span><span class="sxs-lookup"><span data-stu-id="4df47-168">Implement the improvement action</span></span>

<span data-ttu-id="4df47-169">구현 **섹션에는** 개선 작업을 완료하기 위한 모든 선행 작업, 단계별 다음 단계, 개선 작업의 현재 구현 상태 및 자세한 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-169">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="4df47-170">사전 요구에는 필요한 라이선스 또는 개선 작업이 해결되기 전에 완료해야 하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-170">Prerequisites include any licenses that are needed or actions to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="4df47-171">라이선스에 사용자 수가 충분한지 확인하여 개선 작업을 완료하고 해당 라이선스가 필요한 사용자에게 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="4df47-172">의견을 보내 주세요.</span><span class="sxs-lookup"><span data-stu-id="4df47-172">We want to hear from you</span></span>

<span data-ttu-id="4df47-173">문제가 있는 경우 보안, 개인 정보 보호 및 규정 준수 커뮤니티에 게시하여 & [알려주세요.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="4df47-173">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="4df47-174">커뮤니티를 모니터링하고 있으며 도움을 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4df47-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="4df47-175">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="4df47-175">Related resources</span></span>

- [<span data-ttu-id="4df47-176">Microsoft 보안 점수 개요</span><span class="sxs-lookup"><span data-stu-id="4df47-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="4df47-177">Microsoft 보안 점수 기록 추적 및 목표 충족</span><span class="sxs-lookup"><span data-stu-id="4df47-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="4df47-178">향후 계획</span><span class="sxs-lookup"><span data-stu-id="4df47-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="4df47-179">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="4df47-179">What's new</span></span>](microsoft-secure-score-whats-new.md)