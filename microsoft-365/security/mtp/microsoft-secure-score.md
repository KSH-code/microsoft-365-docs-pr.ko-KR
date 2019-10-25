---
title: Microsoft Secure Score
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 세부 정보를 계산 하는 방법 및 보안 관리자가 예상할 수 있는 사항에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 점수, 보안 센터, 개선 작업
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: d8ba3626fc2b6cb7dbc56d32cb61baf34e43996e
ms.sourcegitcommit: 53148fc3663bdcfa9605684317785cb19f37e141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "37697753"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="c4678-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="c4678-104">Microsoft Secure Score</span></span>

<span data-ttu-id="c4678-105">Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-105">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="c4678-106">Microsoft 365 보안 센터의 중앙 집중식 대시보드를 통해 조직은 Microsoft 365 id, 데이터, 앱, 장치 및 인프라의 보안을 모니터링 하 고 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-106">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="c4678-107">보안 점수는 조직에서 다음을 수행 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-107">Secure Score helps organizations do the following:</span></span>  

* <span data-ttu-id="c4678-108">조직의 보안 환경의 현재 상태를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-108">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="c4678-109">검색, 표시 유형, 지침 및 제어 기능을 제공 하 여 보안 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-109">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="c4678-110">벤치 마크와 비교 하 여 Kpi (핵심 성과 지표)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-110">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="c4678-111">조직은 메트릭 및 추세의 견고한 시각화, 다른 Microsoft 제품과의 통합, 비슷한 조직과의 점수 비교에 대 한 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-111">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="c4678-112">이 점수는 타사 솔루션에서 권장 작업을 해결 한 경우에도 반영 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-112">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="c4678-113">또한 [Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)를 통해 권장 사항 및 점수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-113">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="c4678-114">[보안 점수 리소스 종류](https://go.microsoft.com/fwlink/?linkid=2092996)에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-114">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="c4678-115">작업 방법</span><span class="sxs-lookup"><span data-stu-id="c4678-115">How it works</span></span>

<span data-ttu-id="c4678-116">권장 되는 보안 기능을 구성 하 고, 보고서 보기와 같은 보안 관련 작업을 수행 하거나, 타사 응용 프로그램 또는 소프트웨어를 사용 하 여 개선 작업을 처리 하기 위한 사항이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-116">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="c4678-117">일부 향상 작업은 완전히 완료 된 경우에만 점수를 제공 하며 일부 장치 또는 사용자에 대해 완료 되 면 일부를 부분 포인트로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-117">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="c4678-118">보안은 항상 유용성과 균형을 유지 해야 하며 환경에 적합 한 모든 권장 사항은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-118">Security should always be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="c4678-119">점수가 실시간으로 업데이트 되어 시각화 및 향상 작업 페이지에 제공 된 정보를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-119">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="c4678-120">또한 보안 점수가 매일 동기화 되어 각 작업에 대 한 시스템 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-120">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="c4678-121">개선 작업의 점수를 획득 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c4678-121">How improvement actions are scored</span></span>

<span data-ttu-id="c4678-122">대부분은 이진 방식으로 점수가 지정 되며, 새 정책을 만들거나 특정 설정을 설정 하는 것과 같이 개선 작업을 구현 하는 경우에는 점수가 100% 인 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-122">Most are scored in a binary fashion — if you implement the improvement action, like creating a new policy or turning on a specific setting, you get 100% of the points .</span></span> <span data-ttu-id="c4678-123">다른 향상 작업의 경우 점수는 전체 구성에 대 한 비율로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-123">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="c4678-124">예를 들어, 향상 작업에 다단계 인증을 사용 하 여 모든 사용자를 보호 하 여 30 점을 제공 하 고 총 사용자 수가 5 100 개인 경우 2 포인트 (5 개의 보호/100 전체 \* 30 최대 포인트 = 2 pt)의 부분적인 점수가 부여 됩니다.  부분 점수)</span><span class="sxs-lookup"><span data-stu-id="c4678-124">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="c4678-125">안전한 점수에 포함 된 제품</span><span class="sxs-lookup"><span data-stu-id="c4678-125">Products included in Secure Score</span></span>

<span data-ttu-id="c4678-126">현재 Office 365 (SharePoint Online, Exchange Online, 비즈니스용 OneDrive, Microsoft Information Protection 등), Azure AD, Intune 및 Cloud App Security에 대 한 권장 사항이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-126">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, Intune, and Cloud App Security.</span></span> <span data-ttu-id="c4678-127">Azure ATP 및 Microsoft Defender ATP와 같은 다른 보안 제품에 대 한 권장 사항은 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-127">Recommendations for other security products, like Azure ATP and Microsoft Defender ATP, are coming soon.</span></span> <span data-ttu-id="c4678-128">권장 사항은 각 제품과 연결 된 모든 공격 표면을 다루지는 않지만 좋은 기준이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-128">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="c4678-129">또한 개선 작업을 제 3 자에서 다룬 것으로 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-129">You can also mark the improvement actions as covered by a third party.</span></span> 

## <a name="required-permissions"></a><span data-ttu-id="c4678-130">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="c4678-130">Required permissions</span></span>

<span data-ttu-id="c4678-131">Microsoft 보안 점수에 액세스할 수 있는 권한을 부여 하려면 Azure Active Directory에서 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-131">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="c4678-132">읽기 및 쓰기 역할</span><span class="sxs-lookup"><span data-stu-id="c4678-132">Read and write roles</span></span>

<span data-ttu-id="c4678-133">읽기 및 쓰기 액세스를 사용 하 여 변경을 수행 하 고 보안 점수와 직접 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-133">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="c4678-134">또한 다른 사용자에 게 읽기 전용 액세스 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-134">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="c4678-135">CompanyAdministrator</span><span class="sxs-lookup"><span data-stu-id="c4678-135">CompanyAdministrator</span></span>
* <span data-ttu-id="c4678-136">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="c4678-136">SecurityAdministrator</span></span>
* <span data-ttu-id="c4678-137">ExchangeAdmin</span><span class="sxs-lookup"><span data-stu-id="c4678-137">ExchangeAdmin</span></span>
* <span data-ttu-id="c4678-138">SharePointAdmin</span><span class="sxs-lookup"><span data-stu-id="c4678-138">SharePointAdmin</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="c4678-139">읽기 전용 역할</span><span class="sxs-lookup"><span data-stu-id="c4678-139">Read-only roles</span></span>

<span data-ttu-id="c4678-140">읽기 전용 액세스 권한을 사용 하면 향상 작업에 대 한 상태나 메모를 편집 하거나, 점수 영역을 편집 하거나, 사용자 지정 비교를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-140">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="c4678-141">HelpdeskAdmin</span><span class="sxs-lookup"><span data-stu-id="c4678-141">HelpdeskAdmin</span></span>
* <span data-ttu-id="c4678-142">UserAccountAdmin</span><span class="sxs-lookup"><span data-stu-id="c4678-142">UserAccountAdmin</span></span>
* <span data-ttu-id="c4678-143">서비스 관리</span><span class="sxs-lookup"><span data-stu-id="c4678-143">ServiceSupportAdmin</span></span>
* <span data-ttu-id="c4678-144">SecurityReader</span><span class="sxs-lookup"><span data-stu-id="c4678-144">SecurityReader</span></span>
* <span data-ttu-id="c4678-145">SecurityOperator</span><span class="sxs-lookup"><span data-stu-id="c4678-145">SecurityOperator</span></span>
* <span data-ttu-id="c4678-146">GlobalReader</span><span class="sxs-lookup"><span data-stu-id="c4678-146">GlobalReader</span></span>

### <a name="graph-api"></a><span data-ttu-id="c4678-147">Graph API</span><span class="sxs-lookup"><span data-stu-id="c4678-147">Graph API</span></span>

<span data-ttu-id="c4678-148">그래프 API에 액세스 하려면 역할 외에 다음 범위 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-148">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="c4678-149">SecurityEvents. All (읽기 전용 역할의 경우)</span><span class="sxs-lookup"><span data-stu-id="c4678-149">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="c4678-150">SecurityEvents. All (read 및 write role 용)</span><span class="sxs-lookup"><span data-stu-id="c4678-150">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="c4678-151">보안 환경을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-151">Gain visibility into your security posture</span></span>

<span data-ttu-id="c4678-152">필요한 정보를 보다 신속 하 게 지원 하기 위해 Microsoft 개선 작업을 그룹으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-152">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="c4678-153">Id (Azure AD 계정 및 역할)</span><span class="sxs-lookup"><span data-stu-id="c4678-153">Identity (Azure AD accounts and roles)</span></span>
* <span data-ttu-id="c4678-154">데이터 (Office 365 문서)</span><span class="sxs-lookup"><span data-stu-id="c4678-154">Data  (Office 365 documents)</span></span>
* <span data-ttu-id="c4678-155">장치 (Microsoft Defender ATP 디바이스, 곧 출시 예정)</span><span class="sxs-lookup"><span data-stu-id="c4678-155">Device (Microsoft Defender ATP devices, coming soon)</span></span>
* <span data-ttu-id="c4678-156">앱 (전자 메일 및 클라우드 앱)</span><span class="sxs-lookup"><span data-stu-id="c4678-156">App (email and cloud apps)</span></span>
* <span data-ttu-id="c4678-157">인프라 (Azure 리소스)</span><span class="sxs-lookup"><span data-stu-id="c4678-157">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="c4678-158">Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간의 점수가 분할 되는 방식과 사용할 수 있는 지점을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-158">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="c4678-159">개요 페이지는 또한 전체 점수에 대 한 모든 보기, 벤치 마크 비교를 사용한 보안 점수의 역사적 추세 및 점수를 높이기 위해 수행할 수 있는 향상 작업의 우선 순위를 지정 하는 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-159">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="c4678-160">![보안 점수 홈페이지](../media/secure-score/homepage-original.png)
*그림 1: Microsoft 보안 점수 개요 페이지*</span><span class="sxs-lookup"><span data-stu-id="c4678-160">![Secure Score homepage](../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="c4678-161">점수를 개선 하기 위한 조치 수행</span><span class="sxs-lookup"><span data-stu-id="c4678-161">Take action to improve your score</span></span>

<span data-ttu-id="c4678-162">향상 작업 탭에는 가능한 공격 표면을 해당 상태 (완료 됨, 완료 되지 않음, 타사를 통해 확인 및 무시 됨)와 함께 표시 되는 보안 권장 사항이 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-162">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="c4678-163">모든 개선 작업을 검색, 필터링 및 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-163">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="c4678-164">순서</span><span class="sxs-lookup"><span data-stu-id="c4678-164">Ranking</span></span>

<span data-ttu-id="c4678-165">순위는 달성할 수 있는 남은 점수, 구현 난이도, 사용자 영향 및 복잡도를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-165">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="c4678-166">순위가 가장 높은 향상 작업에는 낮은 난이도, 사용자 영향 및 복잡도의 점수가 많이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-166">The highest ranked improvement actions have the large amount of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="c4678-167">작업</span><span class="sxs-lookup"><span data-stu-id="c4678-167">Actions</span></span>

<span data-ttu-id="c4678-168">Microsoft 보안 점수에 의해 [점수 없음] 레이블이 지정 된 작업은 추적 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-168">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="c4678-169">계속 해 서 작업을 수행할 수는 있지만 작업이 완료 되 면 점수에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-169">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="c4678-170">향후 Microsoft 보안 점수에 따라 작업이 추적 되 고 이미 완료 된 경우 보안 점수가 자동으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-170">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="c4678-171">특정 개선 작업을 선택 하면 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-171">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="c4678-172">이 작업을 완료 하려면 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-172">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="c4678-173">**설정 보기** 를 선택 하 여 구성 화면으로 이동 하 고 변경을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-173">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="c4678-174">그리고 나 서 플라이 아웃 위쪽에 표시 되는 작업의 점수를 얻을 수 있습니다. 점수를 업데이트 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-174">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="c4678-175">타사 응용 프로그램 또는 소프트웨어에서 향상 된 기능을 이미 해결 했기 때문에 타사 **에서 문제 해결** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-175">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="c4678-176">이 작업을 수행 하면 보안 점수가 전반적인 보안 상태를 보다 효율적으로 반영할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-176">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="c4678-177">제 3 자가 더 이상 해당 컨트롤을 커버 하지 않으면 개선 작업을 완료 되지 않은 것으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-177">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="c4678-178">Microsoft는 개선 작업을 제 3 자까지 해결 된 것으로 표시 한 경우 점수 요구 사항이 충족 되었는지 여부를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-178">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="c4678-179">위험을 수락 하 고 개선 작업을 규정 하지 않기로 결정 했으므로 **무시** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-179">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="c4678-180">개선 작업을 무시 하 고 나면 최대 보안 점수 점수가 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-180">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="c4678-181">언제 든 지 기록에서이 작업을 보거나 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-181">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="c4678-182">향상 작업을 수행 하려면 환경의 일부를 정기적으로 검토 하 여 점수를 얻고 유지 해야 하므로 **검토** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-182">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="c4678-183">예를 들어 사서함 전달 규칙을 매주 검토 하 여 데이터가 네트워크에서 노출 되었습니다 되 고 있지 않은지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-183">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="c4678-184">변경할 필요는 없지만 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-184">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="c4678-185">정기적으로 규칙을 검토 하면 점수를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-185">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="c4678-186">그렇지 않으면 점수가 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-186">If not, the score is reduced.</span></span>

![보안 점수 향상 작업 예제](../media/secure-score/secure-score1x450.png) ![보안 점수 검토 개선 작업 예제](../media/secure-score/secure-score2x450.png)

<span data-ttu-id="c4678-189">*그림 2 & 3: 향상 작업 flyouts*</span><span class="sxs-lookup"><span data-stu-id="c4678-189">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="c4678-190">시간에 따른 모니터 향상</span><span class="sxs-lookup"><span data-stu-id="c4678-190">Monitor improvements over time</span></span>

<span data-ttu-id="c4678-191">**기록** 탭에서 시간에 따른 조직의 점수 그래프를 볼 수 있습니다. 그래프 아래에 선택한 시간 범위에 적용 된 모든 작업 및 결과 점과 범주와 같은 해당 특성의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-191">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="c4678-192">날짜 범위를 사용자 지정 하 고 범주별로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-192">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="c4678-193">위험 인식</span><span class="sxs-lookup"><span data-stu-id="c4678-193">Risk awareness</span></span>

<span data-ttu-id="c4678-194">Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 한 보안 환경을 나타내는 수치 요약입니다. 시스템 또는 데이터를 얼마나 많이 침해 해야 하는지 절대 측정 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-194">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="c4678-195">대신 Microsoft 환경에서 보안 제어를 채택 하는 범위를 나타내므로 위반 위험을 상쇄 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-195">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="c4678-196">보안 침해에의 한 온라인 서비스에는 전혀 문제가 되지 않으며 보안 점수가 보안상 침해에 대 한 보장으로 해석 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-196">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-coming"></a><span data-ttu-id="c4678-197">무슨 일 인가요?</span><span class="sxs-lookup"><span data-stu-id="c4678-197">What's coming?</span></span>

<span data-ttu-id="c4678-198">Microsoft 보안 점수가 보안 상태를 보다 잘 대표 하 고 유용성이 향상 되도록 하기 위해 곧 몇 가지 사항을 변경 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-198">In order to make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="c4678-199">점수와 가능한 최대 점수가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-199">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="c4678-200">그러나 보안 환경을 변경 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-200">However, this does not imply a change in your security posture.</span></span>

### <a name="removing-not-scored-and-review-improvement-actions"></a><span data-ttu-id="c4678-201">"점수가 매겨지지 않음" 및 "검토" 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="c4678-201">Removing “not scored” and “review” improvement actions</span></span>

<span data-ttu-id="c4678-202">보안 점수 원칙 중 하나는 점수가 표준화 되 고 간편 하 게 관련 되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-202">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="c4678-203">기능을 사용할 수 없거나 작업을 수행 하는 향상 된 기능으로 인해 혼동이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-203">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="c4678-204">한 Microsoft 보안 점수는 모든 권장 사항이 점수에 분명 하 게 영향을 미칠 수 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-204">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="c4678-205">점수가 매겨지지 않음 개선 조치를 수행할 수 없으며, 향상 된 개선 작업을 다른 개선 작업과 동일한 표준으로 측정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-205">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="c4678-206">이러한 이유로 검토 흐름에 대해 점수가 매겨지지 않거나 필요한 모든 개선 작업은 일시적으로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-206">For these reasons, all improvement actions that were not scored or required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="c4678-207">해당 부분에 대 한 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-207">No action is needed on your part.</span></span>

### <a name="simplification-of-the-point-system"></a><span data-ttu-id="c4678-208">지점 시스템 간소화</span><span class="sxs-lookup"><span data-stu-id="c4678-208">Simplification of the point system</span></span>

<span data-ttu-id="c4678-209">여러 환경에서 점수를 표준화 하기 위해 각 보안 점수 향상 동작 지점 합계는 10 포인트이 하까지 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-209">To standardize points across multiple experiences, each Secure Score improvement action point total will be updated to be worth 10 points or less.</span></span> <span data-ttu-id="c4678-210">현재와 미래에 추가 될 수 있는 보안 컨트롤의 광범위 한 breather에서 더 일관 된 기능을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-210">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="c4678-211">이 변경 내용이 중요 하 여 저장 지점 합계가 변경 되는 동안에는 보안 환경을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-211">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>  

### <a name="preview-features"></a><span data-ttu-id="c4678-212">미리 보기 기능</span><span class="sxs-lookup"><span data-stu-id="c4678-212">Preview features</span></span>

<span data-ttu-id="c4678-213">Preview 릴리스에는 다음과 같은 기능이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-213">The following features will be included in the preview release:</span></span>

* <span data-ttu-id="c4678-214">CISO 팀장 수준 토론을 위한 모든 새 메트릭 및 추세 보기</span><span class="sxs-lookup"><span data-stu-id="c4678-214">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="c4678-215">점수를 추적 하 고 벤치 마크 위한 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="c4678-215">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="c4678-216">점수 재발에 대 한 추적 및 모니터링 향상</span><span class="sxs-lookup"><span data-stu-id="c4678-216">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="c4678-217">개선 작업 필터링, 태그, 검색 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="c4678-217">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="c4678-218">점수 예측 및 계획 된 작업을 사용 하 여 향후 목표를 향해 관리</span><span class="sxs-lookup"><span data-stu-id="c4678-218">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="c4678-219">더 많은 내용을 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c4678-219">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="c4678-220">사용자의 의견을 듣고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-220">We want to hear from you</span></span>

<span data-ttu-id="c4678-221">문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에서 게시할 때 알려주십시오.</span><span class="sxs-lookup"><span data-stu-id="c4678-221">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="c4678-222">당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4678-222">We're monitoring the community and will provide help.</span></span>
