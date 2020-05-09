---
title: Microsoft 보안 점수 (이전 이터레이션)
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 보안 환경을 개선 하는 방법 및 보안 관리자가 예상할 수 있는 사항에 대해 설명 합니다.
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
ms.openlocfilehash: 383ef5a0ff61b861bd72dc08d7b974ef98592fcc
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173395"
---
# <a name="microsoft-secure-score-previous-iteration"></a><span data-ttu-id="295c5-104">Microsoft 보안 점수 (이전 이터레이션)</span><span class="sxs-lookup"><span data-stu-id="295c5-104">Microsoft Secure Score (previous iteration)</span></span>

>[!IMPORTANT]
><span data-ttu-id="295c5-105">이 Microsoft 보안 점수는 다음 몇 개월 동안 새로운 디자인 요소 및 기능으로 교체 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-105">This iteration of Microsoft Secure Score is being replaced with new design elements and features over the next few months.</span></span> <span data-ttu-id="295c5-106">최신 이터레이션이 아직 표시 되지 않는 경우에는 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-106">If you do not already see the newest iteration, you will soon.</span></span>
>
><span data-ttu-id="295c5-107">기록 옆에 **메트릭 & 추세** 탭이 표시 되 면 새 이터레이션이 진행 되 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-107">If you see a **Metrics & trends** tab next to History, you are in the new iteration.</span></span> [<span data-ttu-id="295c5-108">Microsoft 보안 성과로 이동 (신규)</span><span class="sxs-lookup"><span data-stu-id="295c5-108">Go to Microsoft Secure Score (new)</span></span>](microsoft-secure-score-new.md)

<span data-ttu-id="295c5-109">Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-109">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="295c5-110">보안 점수 권장 사항을 따르면 위협 으로부터 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-110">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="295c5-111">Microsoft 365 보안 센터의 중앙 집중식 대시보드를 통해 조직은 Microsoft 365 id, 데이터, 앱, 장치 및 인프라의 보안을 모니터링 하 고 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-111">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="295c5-112">보안 점수가 조직에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-112">Secure Score helps organizations:</span></span>

* <span data-ttu-id="295c5-113">조직의 보안 환경의 현재 상태를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-113">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="295c5-114">검색, 표시 유형, 지침 및 제어 기능을 제공 하 여 보안 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-114">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="295c5-115">벤치 마크와 비교 하 여 Kpi (핵심 성과 지표)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-115">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="295c5-116">조직은 메트릭 및 추세의 견고한 시각화, 다른 Microsoft 제품과의 통합, 비슷한 조직과의 점수 비교에 대 한 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-116">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="295c5-117">이 점수는 타사 솔루션에서 권장 작업을 해결 한 경우에도 반영 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-117">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="295c5-118">또한 [Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)를 통해 권장 사항 및 점수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-118">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="295c5-119">[보안 점수 리소스 종류](https://go.microsoft.com/fwlink/?linkid=2092996)에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-119">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="295c5-120">작동 방식</span><span class="sxs-lookup"><span data-stu-id="295c5-120">How it works</span></span>

<span data-ttu-id="295c5-121">권장 되는 보안 기능을 구성 하 고, 보고서 보기와 같은 보안 관련 작업을 수행 하거나, 타사 응용 프로그램 또는 소프트웨어를 사용 하 여 개선 작업을 처리 하기 위한 사항이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-121">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="295c5-122">일부 향상 작업은 완전히 완료 된 경우에만 점수를 제공 하며 일부 장치 또는 사용자에 대해 완료 되 면 일부를 부분 포인트로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-122">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span>

<span data-ttu-id="295c5-123">라이선스에 관계 없이 향상 된 가능한 전체 기능을 제공 하 여 보안 모범 사례를 이해 하 고 점수를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-123">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="295c5-124">절대 보안 상태는 조직이 소유한 제품 라이선스에 관계 없이 동일 하 게 유지 되는 보안 점수를 통해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-124">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="295c5-125">보안은 유용성과 균형을 유지 해야 하며 모든 권장 사항이 환경에 적합 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-125">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="295c5-126">점수가 실시간으로 업데이트 되어 시각화 및 향상 작업 페이지에 제공 된 정보를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-126">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="295c5-127">또한 보안 점수가 매일 동기화 되어 각 작업에 대 한 시스템 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-127">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="295c5-128">개선 작업의 점수를 획득 하는 방법</span><span class="sxs-lookup"><span data-stu-id="295c5-128">How improvement actions are scored</span></span>

<span data-ttu-id="295c5-129">대부분은 이진 방식으로 점수가 지정 되며, 새 정책 만들기 또는 특정 설정을 사용 하는 것과 같은 개선 작업을 구현 하는 경우에는 점수가 100% 인 점수를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-129">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="295c5-130">다른 향상 작업의 경우 점수는 전체 구성에 대 한 비율로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-130">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="295c5-131">예를 들어, 향상 된 작업에 다단계 인증을 사용 하 여 모든 사용자를 보호 하 여 30 점을 제공 하 고 총 사용자 수가 5 100 인 경우, 2 포인트 (5 개의 보호/100 총 \* 30 최대 포인트 = 2 포인트)의 부분적인 점수가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-131">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="295c5-132">안전한 점수에 포함 된 제품</span><span class="sxs-lookup"><span data-stu-id="295c5-132">Products included in Secure Score</span></span>

<span data-ttu-id="295c5-133">현재 Microsoft 365 (Exchange Online 포함), Azure AD, Microsoft Defender ATP, Azure ATP 및 Cloud App Security에 대 한 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-133">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="295c5-134">다른 보안 제품에 대 한 권장 사항은 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-134">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="295c5-135">권장 사항은 각 제품과 연결 된 모든 공격 표면을 다루지는 않지만 좋은 기준이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-135">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="295c5-136">또한 개선 작업을 제 3 자에서 다룬 것으로 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-136">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="295c5-137">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="295c5-137">Required permissions</span></span>

<span data-ttu-id="295c5-138">Microsoft 보안 점수에 액세스할 수 있는 권한을 부여 하려면 Azure Active Directory에서 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-138">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="295c5-139">읽기 및 쓰기 역할</span><span class="sxs-lookup"><span data-stu-id="295c5-139">Read and write roles</span></span>

<span data-ttu-id="295c5-140">읽기 및 쓰기 액세스를 사용 하 여 변경을 수행 하 고 보안 점수와 직접 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-140">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="295c5-141">또한 다른 사용자에 게 읽기 전용 액세스 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-141">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="295c5-142">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="295c5-142">Global administrator</span></span>
* <span data-ttu-id="295c5-143">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="295c5-143">Security administrator</span></span>
* <span data-ttu-id="295c5-144">Exchange 관리자</span><span class="sxs-lookup"><span data-stu-id="295c5-144">Exchange administrator</span></span>
* <span data-ttu-id="295c5-145">SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="295c5-145">SharePoint administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="295c5-146">읽기 전용 역할</span><span class="sxs-lookup"><span data-stu-id="295c5-146">Read-only roles</span></span>

<span data-ttu-id="295c5-147">읽기 전용 액세스 권한을 사용 하면 향상 작업에 대 한 상태나 메모를 편집 하거나, 점수 영역을 편집 하거나, 사용자 지정 비교를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-147">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="295c5-148">헬프데스크 관리자</span><span class="sxs-lookup"><span data-stu-id="295c5-148">Helpdesk administrator</span></span>
* <span data-ttu-id="295c5-149">사용자 관리자</span><span class="sxs-lookup"><span data-stu-id="295c5-149">User administrator</span></span>
* <span data-ttu-id="295c5-150">서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="295c5-150">Service administrator</span></span>
* <span data-ttu-id="295c5-151">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="295c5-151">Security reader</span></span>
* <span data-ttu-id="295c5-152">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="295c5-152">Security operator</span></span>
* <span data-ttu-id="295c5-153">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="295c5-153">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="295c5-154">Graph API</span><span class="sxs-lookup"><span data-stu-id="295c5-154">Graph API</span></span>

<span data-ttu-id="295c5-155">그래프 API에 액세스 하려면 역할 외에 다음 범위 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-155">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="295c5-156">SecurityEvents. All (읽기 전용 역할의 경우)</span><span class="sxs-lookup"><span data-stu-id="295c5-156">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="295c5-157">SecurityEvents. All (read 및 write role 용)</span><span class="sxs-lookup"><span data-stu-id="295c5-157">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="295c5-158">보안 환경을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-158">Gain visibility into your security posture</span></span>

<span data-ttu-id="295c5-159">필요한 정보를 보다 신속 하 게 지원 하기 위해 Microsoft 개선 작업을 그룹으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-159">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="295c5-160">Id (Azure AD 계정 & 역할)</span><span class="sxs-lookup"><span data-stu-id="295c5-160">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="295c5-161">데이터 (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="295c5-161">Data (Microsoft Information Protection)</span></span>
* <span data-ttu-id="295c5-162">장치 (지금 향상 작업 없음)</span><span class="sxs-lookup"><span data-stu-id="295c5-162">Device (no improvement actions for now)</span></span>
* <span data-ttu-id="295c5-163">앱 (Office 365 및 Microsoft Cloud App Security)을 포함 하는 전자 메일 및 클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="295c5-163">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="295c5-164">인프라 (지금은 향상 작업 없음)</span><span class="sxs-lookup"><span data-stu-id="295c5-164">Infrastructure (no improvement actions for now)</span></span>

<span data-ttu-id="295c5-165">Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간의 점수가 분할 되는 방식과 사용할 수 있는 지점을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-165">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="295c5-166">개요 페이지는 또한 전체 점수에 대 한 모든 보기, 벤치 마크 비교를 사용한 보안 점수의 역사적 추세 및 점수를 높이기 위해 수행할 수 있는 향상 작업의 우선 순위를 지정 하는 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-166">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="295c5-167">![보안 점수 홈페이지](../../media/secure-score/homepage-original.png)
*그림 1: Microsoft 보안 점수 개요 페이지*</span><span class="sxs-lookup"><span data-stu-id="295c5-167">![Secure Score homepage](../../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="295c5-168">점수를 개선 하기 위한 조치 수행</span><span class="sxs-lookup"><span data-stu-id="295c5-168">Take action to improve your score</span></span>

<span data-ttu-id="295c5-169">향상 작업 탭에는 가능한 공격 표면을 해당 상태 (완료 됨, 완료 되지 않음, 타사를 통해 확인 및 무시 됨)와 함께 표시 되는 보안 권장 사항이 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-169">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="295c5-170">모든 개선 작업을 검색, 필터링 및 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-170">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="295c5-171">순서</span><span class="sxs-lookup"><span data-stu-id="295c5-171">Ranking</span></span>

<span data-ttu-id="295c5-172">순위는 달성할 수 있는 남은 점수, 구현 난이도, 사용자 영향 및 복잡도를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-172">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="295c5-173">가장 높은 순위의 향상 작업에는 낮은 난이도, 사용자 영향 및 복잡도의 점수가 많이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-173">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="295c5-174">작업</span><span class="sxs-lookup"><span data-stu-id="295c5-174">Actions</span></span>

<span data-ttu-id="295c5-175">특정 개선 작업을 선택 하면 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-175">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="295c5-176">이 작업을 완료 하려면 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-176">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="295c5-177">**설정 보기** 를 선택 하 여 구성 화면으로 이동 하 고 변경을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-177">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="295c5-178">그리고 나 서 플라이 아웃 위쪽에 표시 되는 작업의 점수를 얻을 수 있습니다. 점수를 업데이트 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-178">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="295c5-179">타사 응용 프로그램 또는 소프트웨어에서 향상 된 기능을 이미 해결 했기 때문에 타사 **에서 문제 해결** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-179">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="295c5-180">이 작업을 수행 하면 보안 점수가 전반적인 보안 상태를 보다 효율적으로 반영할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-180">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="295c5-181">제 3 자가 더 이상 해당 컨트롤을 커버 하지 않으면 개선 작업을 완료 되지 않은 것으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-181">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="295c5-182">Microsoft는 개선 작업을 제 3 자까지 해결 된 것으로 표시 한 경우 점수 요구 사항이 충족 되었는지 여부를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-182">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="295c5-183">위험을 수락 하 고 개선 작업을 규정 하지 않기로 결정 했으므로 **무시** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-183">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="295c5-184">개선 작업을 무시 하 고 나면 최대 보안 점수 점수가 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-184">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="295c5-185">언제 든 지 기록에서이 작업을 보거나 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-185">You can view this action in history or undo it at any time.</span></span>

![보안 점수 향상 작업 예제](../../media/secure-score/secure-score1x450.png)

<span data-ttu-id="295c5-187">*그림 2: 개선 작업 플라이 아웃*</span><span class="sxs-lookup"><span data-stu-id="295c5-187">*Figures 2: Improvement action flyout*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="295c5-188">시간에 따른 모니터 향상</span><span class="sxs-lookup"><span data-stu-id="295c5-188">Monitor improvements over time</span></span>

<span data-ttu-id="295c5-189">**기록** 탭에서 시간에 따른 조직의 점수 그래프를 볼 수 있습니다. 그래프 아래에 선택한 시간 범위에 적용 된 모든 작업 및 결과 점과 범주와 같은 해당 특성의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-189">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="295c5-190">날짜 범위를 사용자 지정 하 고 범주별로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-190">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="295c5-191">위험 인식</span><span class="sxs-lookup"><span data-stu-id="295c5-191">Risk awareness</span></span>

<span data-ttu-id="295c5-192">Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 한 보안 환경을 나타내는 수치 요약입니다. 시스템 또는 데이터를 얼마나 많이 침해 해야 하는지 절대 측정 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-192">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="295c5-193">대신 Microsoft 환경에서 보안 제어를 채택 하는 범위를 나타내므로 위반 위험을 상쇄 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-193">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="295c5-194">보안 침해에의 한 온라인 서비스에는 전혀 문제가 되지 않으며 보안 점수가 보안상 침해에 대 한 보장으로 해석 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-194">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="295c5-195">어떠한 새로운 기능이 있나요?</span><span class="sxs-lookup"><span data-stu-id="295c5-195">What's new?</span></span>

<span data-ttu-id="295c5-196">Microsoft 보안 점수를 보안 상태를 보다 효율적으로 구성 하려면 몇 가지 사항을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-196">To make Microsoft Secure Score a better representative of your security posture we have made some changes.</span></span> <span data-ttu-id="295c5-197">계획 된 변경 사항에 대 한 자세한 내용은 [Microsoft 보안 점수에서](microsoft-secure-score-whats-coming.md) 제공 되는 기능을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="295c5-197">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

### <a name="april-21st-2020"></a><span data-ttu-id="295c5-198">4 월 21 일 2020</span><span class="sxs-lookup"><span data-stu-id="295c5-198">April 21st 2020</span></span>

#### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="295c5-199">신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업을 제거 하거나 보안 환경을 효과적으로 표현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-199">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="295c5-200">Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-200">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="295c5-201">문서에 IRM 보호 적용</span><span class="sxs-lookup"><span data-stu-id="295c5-201">Apply IRM protections to documents</span></span>
- <span data-ttu-id="295c5-202">데이터 손실 방지 정책 적용</span><span class="sxs-lookup"><span data-stu-id="295c5-202">Apply Data Loss Prevention policies</span></span>

### <a name="january---march-2020"></a><span data-ttu-id="295c5-203">1 월-2020 년 3 월</span><span class="sxs-lookup"><span data-stu-id="295c5-203">January - March 2020</span></span>

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="295c5-204">Azure AD 개선 작업에 대 한 보안 기본값 지원</span><span class="sxs-lookup"><span data-stu-id="295c5-204">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="295c5-205">Microsoft 보안 점수는 [AZURE AD에서 보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 지원 하기 위해 개선 작업을 업데이트 하 여 일반적인 공격에 대 한 미리 구성 된 보안 설정으로 조직을 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-205">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="295c5-206">이는 다음과 같은 개선 작업에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-206">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="295c5-207">모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="295c5-207">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="295c5-208">관리 역할에 대 한 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="295c5-208">Require MFA for administrative roles</span></span>
- <span data-ttu-id="295c5-209">정책을 사용 하 여 레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="295c5-209">Enable policy to block legacy authentication</span></span>

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="295c5-210">신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업을 제거 했거나 보안 환경을 효과적으로 표현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-210">Removed improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="295c5-211">Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-211">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="295c5-212">비즈니스용 OneDrive에 사용자 문서 저장</span><span class="sxs-lookup"><span data-stu-id="295c5-212">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="295c5-213">Office 365 ATP 안전한 첨부 파일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="295c5-213">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="295c5-214">Url을 확인 하기 위한 Office 365 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="295c5-214">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="295c5-215">사서함 위임 허용 안 함</span><span class="sxs-lookup"><span data-stu-id="295c5-215">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="295c5-216">사이트 및 문서에 대 한 익명 게스트 공유 링크 허용</span><span class="sxs-lookup"><span data-stu-id="295c5-216">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="295c5-217">Cloud App Security Console 켜기</span><span class="sxs-lookup"><span data-stu-id="295c5-217">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="295c5-218">외부 공유 링크에 대 한 만료 시간 구성</span><span class="sxs-lookup"><span data-stu-id="295c5-218">Configure expiration time for external sharing links</span></span>
- <span data-ttu-id="295c5-219">감사 데이터 기록 켜기</span><span class="sxs-lookup"><span data-stu-id="295c5-219">Turn on audit data recording</span></span>
- <span data-ttu-id="295c5-220">위험한 및 비호환 섀도 IT 응용 프로그램 검색</span><span class="sxs-lookup"><span data-stu-id="295c5-220">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="295c5-221">사용 권한 검토 & 환경에 연결 된 위험한 OAuth 응용 프로그램 차단</span><span class="sxs-lookup"><span data-stu-id="295c5-221">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="295c5-222">SharePoint online 문서 라이브러리에 대 한 버전 관리 설정</span><span class="sxs-lookup"><span data-stu-id="295c5-222">Set up versioning on SharePoint online document libraries</span></span>
- <span data-ttu-id="295c5-223">지난 30 일 동안 사용 되지 않은 계정 삭제/차단</span><span class="sxs-lookup"><span data-stu-id="295c5-223">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="295c5-224">전역 관리자를 5 명 미만으로 지정</span><span class="sxs-lookup"><span data-stu-id="295c5-224">Designate fewer than 5 global admins</span></span>

#### <a name="removed-not-scored-improvement-actions"></a><span data-ttu-id="295c5-225">"점수가 매겨지지 않음" 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="295c5-225">Removed "not scored" improvement actions</span></span>

<span data-ttu-id="295c5-226">보안 점수 원칙 중 하나는 점수가 표준화 되 고 간편 하 게 관련 되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-226">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="295c5-227">기능을 사용할 수 없거나 작업을 수행 하는 향상 된 기능으로 인해 혼동이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-227">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="295c5-228">Microsoft 보안 점수는 모든 권장 사항에 따라 점수가 명확 하 게 영향을 미칠 수 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-228">Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="295c5-229">점수를 획득 하지 않음 개선 조치를 측정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-229">Not scored improvement actions are not measurable.</span></span>  

<span data-ttu-id="295c5-230">이러한 이유로 점수가 없는 모든 개선 작업은 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-230">For these reasons, all improvement actions that were not scored have been removed.</span></span> <span data-ttu-id="295c5-231">해당 부분에 대 한 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-231">No action is needed on your part.</span></span>

#### <a name="removed-device-improvement-actions"></a><span data-ttu-id="295c5-232">장치 향상 작업 제거</span><span class="sxs-lookup"><span data-stu-id="295c5-232">Removed device improvement actions</span></span>

<span data-ttu-id="295c5-233">개선 작업의 Microsoft 보안 점수 장치 범주를 평가한 후에는 해당 작업이 장치 구성 상태가 아니라 정책 상태를 평가 하는 것으로 확인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-233">After an evaluation of the Microsoft Secure Score device category of improvement actions, it was determined that those actions currently assess the policy state and not the configuration state of devices.</span></span> <span data-ttu-id="295c5-234">구성은 보안에 직접적으로 연결 되므로 기존 장치 작업은 조직 상황을 완전히 나타내지 않고 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-234">Since configuration is directly tied to security posture, the existing device actions were determined to not fully represent organizational posture.</span></span>  <span data-ttu-id="295c5-235">장치 보안 환경을 보다 완전 하 게 나타내기 위해 진단 데이터를 직접 사용 하는 권장 사항 집합을 제공 하는 작업을 수행 하는 중에 장치 범주에서 현재 작업을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-235">We will be removing the current actions in the device category as we work to provide a set of recommendations which directly use diagnostic data to more fully represent device security posture.</span></span>

<span data-ttu-id="295c5-236">제거 된 개선 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-236">The following improvement actions have been removed:</span></span>

- <span data-ttu-id="295c5-237">Microsoft Intune 모바일 장치 관리 사용</span><span class="sxs-lookup"><span data-stu-id="295c5-237">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="295c5-238">Android 용 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-238">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="295c5-239">비즈니스용 Android 용 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-239">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="295c5-240">Android 용 Microsoft Intune 앱 보호 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-240">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="295c5-241">IOS 용 Microsoft Intune 앱 보호 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-241">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="295c5-242">Microsoft Intune 준수 정책이 비규격으로 지정 된 장치 표시</span><span class="sxs-lookup"><span data-stu-id="295c5-242">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="295c5-243">IOS 용 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-243">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="295c5-244">MacOS에 대 한 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-244">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="295c5-245">Windows 용 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-245">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="295c5-246">Android 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-246">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="295c5-247">비즈니스용 Android 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-247">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="295c5-248">MacOS 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-248">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="295c5-249">IOS 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-249">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="295c5-250">Windows 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-250">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="295c5-251">Microsoft Intune에서 향상 된 jailbreak 검색 사용</span><span class="sxs-lookup"><span data-stu-id="295c5-251">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="295c5-252">모든 장치에 패치를 적용 하 고 바이러스 백신 및 방화벽을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-252">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="295c5-253">Microsoft Intune에 Windows Defender ATP 통합 사용</span><span class="sxs-lookup"><span data-stu-id="295c5-253">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="295c5-254">Microsoft Intune Windows Information Protection 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="295c5-254">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="295c5-255">모든 장치에 고급 보안 구성 필요</span><span class="sxs-lookup"><span data-stu-id="295c5-255">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="295c5-256">매주 차단 된 장치 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="295c5-256">Review blocked devices report weekly</span></span>

#### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="295c5-257">MFA 개선 작업 업데이트</span><span class="sxs-lookup"><span data-stu-id="295c5-257">MFA improvement action updates</span></span>

<span data-ttu-id="295c5-258">비즈니스의 보안을 강화 하기 위해 기업에서 요구 하는 사항을 반영 하기 위해 Microsoft 보안 점수가 다단계 인증을 중심으로 하는 세 가지 향상 작업을 제거 하 고 2를 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-258">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score has removed three improvement actions centered around multi-factor authentication, and added two.</span></span>

<span data-ttu-id="295c5-259">제거 된 개선 작업:</span><span class="sxs-lookup"><span data-stu-id="295c5-259">Removed improvement actions:</span></span>

- <span data-ttu-id="295c5-260">Multi-factor authentication에 대 한 모든 사용자 등록</span><span class="sxs-lookup"><span data-stu-id="295c5-260">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="295c5-261">모든 사용자에 대해 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="295c5-261">Require MFA for all users</span></span>
- <span data-ttu-id="295c5-262">Azure AD 권한 있는 역할에 대해 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="295c5-262">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="295c5-263">개선 작업 추가:</span><span class="sxs-lookup"><span data-stu-id="295c5-263">Added improvement actions:</span></span>

- <span data-ttu-id="295c5-264">모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="295c5-264">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="295c5-265">관리 역할에 대 한 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="295c5-265">Require MFA for administrative roles</span></span>

 <span data-ttu-id="295c5-266">이러한 새로운 향상 작업을 수행 하려면 디렉터리 전체에서 MFA (multi-factor authentication)에 대 한 사용자 또는 관리자를 등록 하 고 조직의 요구 사항에 맞는 적절 한 정책 집합을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-266">These new improvement actions require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="295c5-267">기본 목표는 모든 사용자와 관리자가 여러 요소 또는 위험 기반 id 확인 메시지를 사용 하 여 인증할 수 있도록 하는 데 유연성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-267">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="295c5-268">이는 범위 결정을 적용 하는 정책이 여러 개 있거나 Microsoft가 MFA를 위해 사용자를 challenge 해야 하는 경우를 결정할 수 있도록 보안 기본값 (16 월 여섯째 부분)을 설정 하는 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-268">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

#### <a name="removed-review-improvement-actions"></a><span data-ttu-id="295c5-269">"검토" 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="295c5-269">Removed "review" improvement actions</span></span>

<span data-ttu-id="295c5-270">보안 점수 원칙 중 하나는 점수가 표준화 되 고 간편 하 게 관련 되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-270">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="295c5-271">기능을 사용할 수 없거나 작업을 수행 하는 향상 된 기능으로 인해 혼동이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-271">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="295c5-272">한 Microsoft 보안 점수는 모든 권장 사항이 점수에 분명 하 게 영향을 미칠 수 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-272">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="295c5-273">검토 개선 작업은 다른 개선 작업과 같은 표준으로 측정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-273">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="295c5-274">이러한 이유로 검토 흐름을 필요로 했던 모든 개선 작업이 일시적으로 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-274">For these reasons, all improvement actions that required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="295c5-275">해당 부분에 대 한 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-275">No action is needed on your part.</span></span>

### <a name="preview-features"></a><span data-ttu-id="295c5-276">미리 보기 기능</span><span class="sxs-lookup"><span data-stu-id="295c5-276">Preview features</span></span>

<span data-ttu-id="295c5-277">[Preview 릴리스에](microsoft-secure-score-preview.md)는 다음과 같은 기능이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-277">The following features will be included in the [preview release](microsoft-secure-score-preview.md):</span></span>

* <span data-ttu-id="295c5-278">CISO 팀장 수준 토론을 위한 모든 새 메트릭 및 추세 보기</span><span class="sxs-lookup"><span data-stu-id="295c5-278">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="295c5-279">점수를 추적 하 고 벤치 마크 위한 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="295c5-279">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="295c5-280">점수 재발에 대 한 추적 및 모니터링 향상</span><span class="sxs-lookup"><span data-stu-id="295c5-280">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="295c5-281">개선 작업 필터링, 태그, 검색 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="295c5-281">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="295c5-282">점수 예측 및 계획 된 작업을 사용 하 여 향후 목표를 향해 관리</span><span class="sxs-lookup"><span data-stu-id="295c5-282">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="295c5-283">포인트 시스템 단순화</span><span class="sxs-lookup"><span data-stu-id="295c5-283">Simplification of the points system</span></span>
* <span data-ttu-id="295c5-284">더 많은 내용을 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="295c5-284">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="295c5-285">사용자의 의견을 듣고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-285">We want to hear from you</span></span>

<span data-ttu-id="295c5-286">문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에서 게시할 때 알려주십시오.</span><span class="sxs-lookup"><span data-stu-id="295c5-286">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="295c5-287">당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="295c5-287">We're monitoring the community and will provide help.</span></span>
