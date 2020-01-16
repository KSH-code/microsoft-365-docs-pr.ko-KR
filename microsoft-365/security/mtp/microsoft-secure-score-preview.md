---
title: Microsoft 보안 점수 (미리 보기)
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 세부 정보를 계산 하는 방법 및 보안 관리자가이를 사용 하는 것으로 예상할 수 있는 사항에 대해 설명 합니다.
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
ms.openlocfilehash: 284efd5224f3e48ab718c0de0c877f68fc0bdecc
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210480"
---
# <a name="microsoft-secure-score-preview"></a><span data-ttu-id="6295f-104">Microsoft 보안 점수 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="6295f-104">Microsoft Secure Score (preview)</span></span>

>[!IMPORTANT]
><span data-ttu-id="6295f-105">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-105">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6295f-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="6295f-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6295f-107">Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-107">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="6295f-108">보안 점수 권장 사항을 따르면 위협 으로부터 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-108">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="6295f-109">Microsoft 365 보안 센터의 중앙 집중식 대시보드를 통해 조직은 Microsoft 365 id, 데이터, 앱, 장치 및 인프라의 보안을 모니터링 하 고 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-109">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="6295f-110">보안 점수가 조직에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-110">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="6295f-111">조직의 보안 환경의 현재 상태를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-111">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="6295f-112">검색, 표시 유형, 지침 및 제어 기능을 제공 하 여 보안 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-112">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="6295f-113">벤치 마크와 비교 하 여 Kpi (핵심 성과 지표)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-113">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="6295f-114">조직은 메트릭 및 추세의 견고한 시각화, 다른 Microsoft 제품과의 통합, 비슷한 조직과의 점수 비교에 대 한 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-114">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="6295f-115">이 점수는 타사 솔루션에서 권장 작업을 해결 한 경우에도 반영 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-115">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="6295f-116">또한 [Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)를 통해 권장 사항 및 점수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-116">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="6295f-117">[보안 점수 리소스 종류](https://go.microsoft.com/fwlink/?linkid=2092996)에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-117">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="6295f-118">작업 방법</span><span class="sxs-lookup"><span data-stu-id="6295f-118">How it works</span></span>

<span data-ttu-id="6295f-119">권장 되는 보안 기능을 구성 하 고, 보안 관련 작업을 수행 하거나, 타사 응용 프로그램 또는 소프트웨어를 사용 하 여 개선 작업을 처리 하기 위한 사항이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-119">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="6295f-120">일부 향상 작업은 완전히 완료 된 경우에만 점수를 제공 하며 일부 장치 또는 사용자에 대해 완료 되 면 일부를 부분 포인트로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-120">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="6295f-121">개선 작업 중 하나를 규정 하지 않으려는 경우 위험 또는 남은 위험을 수락 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-121">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="6295f-122">라이선스에 관계 없이 향상 된 가능한 전체 기능을 제공 하 여 보안 모범 사례를 이해 하 고 점수를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-122">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="6295f-123">절대 보안 상태는 조직이 소유한 제품 라이선스에 관계 없이 동일 하 게 유지 되는 보안 점수를 통해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-123">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="6295f-124">보안은 유용성과 균형을 유지 해야 하며 모든 권장 사항이 환경에 적합 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-124">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="6295f-125">점수가 실시간으로 업데이트 되어 시각화 및 향상 작업 페이지에 제공 된 정보를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-125">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="6295f-126">또한 보안 점수가 매일 동기화 되어 각 작업에 대 한 시스템 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-126">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="6295f-127">개선 작업의 점수를 획득 하는 방법</span><span class="sxs-lookup"><span data-stu-id="6295f-127">How improvement actions are scored</span></span>

<span data-ttu-id="6295f-128">각 향상 작업은 10 점 이내에 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-128">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="6295f-129">대부분은 이진 방식으로 점수가 지정 되며, 새 정책 만들기 또는 특정 설정을 사용 하는 것과 같은 개선 작업을 구현 하는 경우에는 점수가 100% 인 점수를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-129">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="6295f-130">다른 향상 작업의 경우 점수는 전체 구성에 대 한 비율로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-130">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="6295f-131">예를 들어, 향상 된 작업에 다단계 인증을 사용 하 여 모든 사용자를 보호 하 여 30 점을 제공 하 고 총 사용자 수가 5 100 인 경우, 2 포인트 (5 개의 보호/100 총 \* 30 최대 포인트 = 2 포인트)의 부분적인 점수가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-131">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="6295f-132">안전한 점수에 포함 된 제품</span><span class="sxs-lookup"><span data-stu-id="6295f-132">Products included in Secure Score</span></span>

<span data-ttu-id="6295f-133">현재 Office 365 (SharePoint Online, Exchange Online, 비즈니스용 OneDrive, Microsoft Information Protection 등), Azure AD, Microsoft Defender ATP 및 Cloud App Security에 대 한 권장 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-133">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, Microsoft Defender ATP, and Cloud App Security.</span></span> <span data-ttu-id="6295f-134">다른 보안 제품에 대 한 권장 사항은 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-134">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="6295f-135">권장 사항은 각 제품과 연결 된 모든 공격 표면을 다루지는 않지만 좋은 기준이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-135">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="6295f-136">또한 개선 작업을 제 3 자에서 다룬 것으로 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-136">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="6295f-137">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="6295f-137">Required permissions</span></span>

<span data-ttu-id="6295f-138">Microsoft 보안 점수에 액세스할 수 있는 권한을 부여 하려면 Azure Active Directory에서 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-138">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="6295f-139">읽기 및 쓰기 역할</span><span class="sxs-lookup"><span data-stu-id="6295f-139">Read and write roles</span></span>

<span data-ttu-id="6295f-140">읽기 및 쓰기 액세스를 사용 하 여 변경을 수행 하 고 보안 점수와 직접 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-140">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="6295f-141">또한 다른 사용자에 게 읽기 전용 액세스 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-141">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="6295f-142">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="6295f-142">Global administrator</span></span>
* <span data-ttu-id="6295f-143">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="6295f-143">Security administrator</span></span>
* <span data-ttu-id="6295f-144">Exchange 관리자</span><span class="sxs-lookup"><span data-stu-id="6295f-144">Exchange administrator</span></span>
* <span data-ttu-id="6295f-145">SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="6295f-145">SharePoint administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="6295f-146">읽기 전용 역할</span><span class="sxs-lookup"><span data-stu-id="6295f-146">Read-only roles</span></span>

<span data-ttu-id="6295f-147">읽기 전용 액세스 권한을 사용 하면 향상 작업에 대 한 상태나 메모를 편집 하거나, 점수 영역을 편집 하거나, 사용자 지정 비교를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-147">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="6295f-148">헬프데스크 관리자</span><span class="sxs-lookup"><span data-stu-id="6295f-148">Helpdesk administrator</span></span>
* <span data-ttu-id="6295f-149">User administrator</span><span class="sxs-lookup"><span data-stu-id="6295f-149">User administrator</span></span>
* <span data-ttu-id="6295f-150">서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="6295f-150">Service administrator</span></span>
* <span data-ttu-id="6295f-151">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="6295f-151">Security reader</span></span>
* <span data-ttu-id="6295f-152">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="6295f-152">Security operator</span></span>
* <span data-ttu-id="6295f-153">전역 독자</span><span class="sxs-lookup"><span data-stu-id="6295f-153">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="6295f-154">Graph API</span><span class="sxs-lookup"><span data-stu-id="6295f-154">Graph API</span></span>

<span data-ttu-id="6295f-155">그래프 API에 액세스 하려면 역할 외에 다음 범위 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-155">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="6295f-156">SecurityEvents. All (읽기 전용 역할의 경우)</span><span class="sxs-lookup"><span data-stu-id="6295f-156">SecurityEvents.Read.All (for read-only roles)</span></span>
* <span data-ttu-id="6295f-157">SecurityEvents. All (읽기 및 쓰기 역할 용)</span><span class="sxs-lookup"><span data-stu-id="6295f-157">SecurityEvents.ReadWrite.All (for read and write roles)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="6295f-158">보안 환경을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-158">Gain visibility into your security posture</span></span>

<span data-ttu-id="6295f-159">필요한 정보를 보다 신속 하 게 지원 하기 위해 Microsoft 개선 작업을 그룹으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-159">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="6295f-160">Id (Azure AD 계정 & 역할, Azure ATP가 곧 출시 될 예정)</span><span class="sxs-lookup"><span data-stu-id="6295f-160">Identity (Azure AD accounts & roles, with Azure ATP coming soon)</span></span>
* <span data-ttu-id="6295f-161">데이터 (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="6295f-161">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="6295f-162">장치 (Microsoft Defender ATP 장치)</span><span class="sxs-lookup"><span data-stu-id="6295f-162">Device (Microsoft Defender ATP devices)</span></span>
* <span data-ttu-id="6295f-163">앱 (Office 365 및 Microsoft Cloud App Security)을 포함 하는 전자 메일 및 클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="6295f-163">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="6295f-164">인프라 (Azure 리소스)</span><span class="sxs-lookup"><span data-stu-id="6295f-164">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="6295f-165">Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간의 점수가 분할 되는 방식과 사용할 수 있는 지점을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-165">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="6295f-166">개요 페이지는 또한 전체 점수에 대 한 모든 보기, 벤치 마크 비교를 사용한 보안 점수의 역사적 추세 및 점수를 높이기 위해 수행할 수 있는 향상 작업의 우선 순위를 지정 하는 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-166">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="6295f-167">![보안 점수 홈페이지](../media/secure-score/secure-score-homepage.png)
*그림 1: Microsoft 보안 점수 개요 페이지*</span><span class="sxs-lookup"><span data-stu-id="6295f-167">![Secure Score homepage](../media/secure-score/secure-score-homepage.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="6295f-168">점수를 개선 하기 위한 조치 수행</span><span class="sxs-lookup"><span data-stu-id="6295f-168">Take action to improve your score</span></span>

<span data-ttu-id="6295f-169">향상 작업 탭에는 가능한 공격 대상 및 해당 상태 (완료 됨, 계획 됨, 위험 수락, 타사 및 받는 사람 주소)를 포함 하는 보안 권장 사항이 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-169">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, planned, risk accepted, third party, and to address).</span></span> <span data-ttu-id="6295f-170">모든 개선 작업을 검색, 필터링 및 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-170">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="6295f-171">순서</span><span class="sxs-lookup"><span data-stu-id="6295f-171">Ranking</span></span>

<span data-ttu-id="6295f-172">순위는 달성할 수 있는 남은 점수, 구현 난이도, 사용자 영향 및 복잡도를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-172">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="6295f-173">가장 높은 순위의 향상 작업에는 낮은 난이도, 사용자 영향 및 복잡도의 점수가 많이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-173">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="6295f-174">작업</span><span class="sxs-lookup"><span data-stu-id="6295f-174">Actions</span></span>

<span data-ttu-id="6295f-175">특정 향상 작업을 선택 하면 전체 페이지 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-175">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="6295f-176">![향상 작업 플라이 아웃](../media/secure-score/secure-score-improvement-action.png)
예*그림 2: 개선 작업 플라이 아웃 예제*</span><span class="sxs-lookup"><span data-stu-id="6295f-176">![Improvement action flyout example](../media/secure-score/secure-score-improvement-action.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="6295f-177">이 작업을 완료 하려면 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-177">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="6295f-178">**관리** 를 선택 하 여 구성 화면으로 이동 하 고 변경을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-178">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="6295f-179">그런 다음 동작이 가치 있는 점수를 얻게 되며 플라이 아웃 됩니다. 점수는 일반적으로 업데이트 하는 데 약 24 시간이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-179">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="6295f-180">**공유** 를 선택 하 여 개선 작업에 대 한 직접 링크를 복사 하거나, 전자 메일, microsoft 팀, Microsoft Planner 또는 ServiceNow와 같은 링크를 공유할 플랫폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-180">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="6295f-181">ServiceNow를 선택 하면 ServiceNow 및 Microsoft 365 보안 센터 홈에 표시 되는 변경 티켓을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-181">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="6295f-182">자세한 내용은 [Microsoft 365 보안 센터 및 ServiceNow 통합](tickets.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6295f-182">To learn more, see [Microsoft 365 Security Center and ServiceNow integration](tickets.md).</span></span>

* <span data-ttu-id="6295f-183">**상태 및 메모 편집** 을 선택 하 여 수동 상태를 편집 하거나 개선 작업에 관련 된 메모를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-183">Select **Edit status and notes** to edit any manual statuses or record notes specific to the improvement action.</span></span> <span data-ttu-id="6295f-184">향상 작업 탭에서 상태를 기준으로 필터링 하거나 그룹화 할 수 있습니다. 선택할 수 있는 조각상은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-184">You can filter or group by the statuses in the improvement actions tab. The statues you can select are the following</span></span>

    * <span data-ttu-id="6295f-185">**해결 방법** : 개선 작업이 필요한 지를 인식 하 고 미래에 특정 시점에 해결할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-185">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="6295f-186">이 상태는 부분적으로 검색 되었지만 완전히 완료 되지 않은 작업에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-186">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
    * <span data-ttu-id="6295f-187">**계획** 됨-개선 작업을 완료 하기 위한 구체적인 계획이 마련 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-187">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
    * <span data-ttu-id="6295f-188">**위험 수락** -보안이 항상 유용성과 균형을 유지 해야 하며, 환경에 대 한 모든 권장 사항이 적합 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-188">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="6295f-189">이 경우 위험 또는 남은 위험을 수락 하 고 개선 작업을 적용 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-189">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="6295f-190">모든 점수를 제공 하는 것은 아니지만 해당 작업은 개선 작업 목록에 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-190">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="6295f-191">언제 든 지 기록에서이 작업을 보거나 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-191">You can view this action in history or undo it at any time.</span></span>
    * <span data-ttu-id="6295f-192">타사 응용 프로그램 또는 소프트웨어에서 개선 작업을 이미 처리 한 타사를 **통해 해결** 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-192">**Resolve through third party** — The improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="6295f-193">작업을 수행 하는 점수를 얻게 되므로 점수가 향상 되어 전반적인 보안 환경을 보다 효율적으로 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-193">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="6295f-194">제 3 자가 더 이상 해당 컨트롤을 커버 하지 않으면 다른 상태를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-194">If a third party no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="6295f-195">개선 작업이 타사를 통해 해결 된 것으로 표시 되는 경우 Microsoft는 구현의 완성도를 명확 하 게 파악할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-195">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as resolved through third party</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6295f-196">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6295f-196">Prerequisites</span></span>

<span data-ttu-id="6295f-197">구현 섹션의 필수 구성 요소에는 획득 해야 하는 모든 라이선스 또는 개선 작업을 처리 하기 전에 완료 해야 하는 작업이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-197">Prerequisites in the Implementation section will list any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="6295f-198">라이선스에 개선 작업을 완료 하 고 해당 라이선스가 필요한 사용자에 게 적용 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-198">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="track-your-score-history-and-meet-goals"></a><span data-ttu-id="6295f-199">점수 내역 추적 및 목표 달성</span><span class="sxs-lookup"><span data-stu-id="6295f-199">Track your score history and meet goals</span></span>

<span data-ttu-id="6295f-200">**기록** 탭에서 시간에 따른 조직의 점수 그래프를 볼 수 있습니다. 그래프 아래에 선택한 시간 범위에 적용 된 모든 작업 및 결과 점과 범주와 같은 해당 특성의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-200">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="6295f-201">날짜 범위를 사용자 지정 하 고 범주별로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-201">You can customize a date range and filter by category.</span></span>

<span data-ttu-id="6295f-202">**메트릭 & 추세** 탭에는 다양 한 그래프와 차트를 통해 추세를 보다 명확 하 게 표시 하 고 목표를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-202">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="6295f-203">시각화의 전체 페이지에 대 한 날짜 범위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-203">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="6295f-204">시각화에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-204">The visualizations include:</span></span>

* <span data-ttu-id="6295f-205">**보안 점수 영역** — 조직의 목표 및 양호한 점수, 양호 및 불량 점수의 범위에 따라 사용자 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-205">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="6295f-206">**회귀 추세** -구성, 사용자 또는 장치 변경으로 인해 회귀 된 지점에 대 한 시간 표시 막대입니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-206">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="6295f-207">**비교 추세** — 조직의 보안 점수가 다른 사람들과 비교 하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-207">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="6295f-208">이 보기에는 비슷한 사용자 수를 갖는 조직의 점수 평균을 나타내는 줄과 설정할 수 있는 custom 비교 보기가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-208">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="6295f-209">**위험 수락 추세** — "위험 수용 됨"으로 표시 된 개선 작업의 시간 표시 막대입니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-209">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="6295f-210">**점수 변경** -지정 된 날짜 범위에서 얻은 점수 수, 회귀 된 점수 또는 후속 점수 변경과 함께 추가 된 새 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-210">**Score changes** — The number of points achieved, points regressed, or new actions added, along with the subsequent score change, in the specified date range.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="6295f-211">위험 인식</span><span class="sxs-lookup"><span data-stu-id="6295f-211">Risk awareness</span></span>

<span data-ttu-id="6295f-212">Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 한 보안 환경을 나타내는 수치 요약입니다. 시스템 또는 데이터를 얼마나 많이 침해 해야 하는지 절대 측정 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-212">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="6295f-213">대신 Microsoft 환경에서 보안 제어를 채택 하는 범위를 나타내므로 위반 위험을 상쇄 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-213">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="6295f-214">보안 침해에의 한 온라인 서비스에는 전혀 문제가 되지 않으며 보안 점수가 보안상 침해에 대 한 보장으로 해석 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-214">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-coming"></a><span data-ttu-id="6295f-215">무슨 일 인가요?</span><span class="sxs-lookup"><span data-stu-id="6295f-215">What's coming?</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="6295f-216">MFA 개선 작업 업데이트</span><span class="sxs-lookup"><span data-stu-id="6295f-216">MFA improvement action updates</span></span>

<span data-ttu-id="6295f-217">비즈니스의 보안을 강화 하기 위해 기업에서 요구 하는 사항을 반영 하기 위해 Microsoft 보안 점수는 다단계 인증을 중심으로 하는 세 가지 개선 작업을 제거 하 고 두 개를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-217">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="6295f-218">제거 되는 3:</span><span class="sxs-lookup"><span data-stu-id="6295f-218">The three that will be removed:</span></span>
- <span data-ttu-id="6295f-219">Multi-factor authentication에 대 한 모든 사용자 등록</span><span class="sxs-lookup"><span data-stu-id="6295f-219">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="6295f-220">모든 사용자에 대해 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="6295f-220">Require MFA for all users</span></span>
- <span data-ttu-id="6295f-221">Azure AD 권한 있는 역할에 대해 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6295f-221">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="6295f-222">새 향상 작업:</span><span class="sxs-lookup"><span data-stu-id="6295f-222">New improvement actions:</span></span>
- <span data-ttu-id="6295f-223">모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="6295f-223">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="6295f-224">관리 역할에 대 한 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6295f-224">Require MFA for administrative roles</span></span>

 <span data-ttu-id="6295f-225">이러한 새로운 향상 작업을 수행 하려면 디렉터리 전체에서 MFA (multi-factor authentication)에 대 한 사용자 또는 관리자를 등록 하 고 조직의 요구 사항에 맞는 적절 한 정책 집합을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-225">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="6295f-226">기본 목표는 모든 사용자와 관리자가 여러 요소 또는 위험 기반 id 확인 메시지를 사용 하 여 인증할 수 있도록 하는 데 유연성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-226">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="6295f-227">여기에는 Microsoft가 MFA를 지 원하는 경우 또는 범위 결정을 적용 하는 여러 정책을 사용 하는 경우를 결정 하는 보안 기본값 설정 형태가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-227">That can take the form of setting security defaults that let Microsoft decide when to challenge users for MFA, or having multiple policies that apply scoped decisions.</span></span>

## <a name="whats-new"></a><span data-ttu-id="6295f-228">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="6295f-228">What’s new?</span></span> 

<span data-ttu-id="6295f-229">Microsoft 보안 점수가 보안 상태를 보다 잘 대표 하 고 유용성이 향상 되도록 하기 위해 몇 가지 사항을 변경 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-229">To make Microsoft Secure Score a better representative of your security posture and improve usability, we have made some changes.</span></span> <span data-ttu-id="6295f-230">점수 및 가능한 최대 점수가 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-230">Your score and the maximum possible score have changed.</span></span> <span data-ttu-id="6295f-231">그러나 보안 환경을 변경 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-231">However, this does not imply a change in your security posture.</span></span>

### <a name="updated-interface-and-functionality"></a><span data-ttu-id="6295f-232">업데이트 된 인터페이스 및 기능</span><span class="sxs-lookup"><span data-stu-id="6295f-232">Updated interface and functionality</span></span>

* <span data-ttu-id="6295f-233">CISO 팀장 수준 토론을 위한 모든 새 메트릭 및 추세 보기</span><span class="sxs-lookup"><span data-stu-id="6295f-233">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="6295f-234">점수를 추적 하 고 벤치 마크 위한 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="6295f-234">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="6295f-235">점수 재발에 대 한 추적 및 이해 향상</span><span class="sxs-lookup"><span data-stu-id="6295f-235">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="6295f-236">개선 작업 필터링, 태그, 검색 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="6295f-236">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="6295f-237">점수 예측 및 계획 된 작업을 사용 하 여 향후 목표를 향해 관리</span><span class="sxs-lookup"><span data-stu-id="6295f-237">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="6295f-238">더 많은 내용을 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6295f-238">And more!</span></span>

### <a name="removed-not-scored-and-review-improvement-actions"></a><span data-ttu-id="6295f-239">"점수가 매겨지지 않음" 및 "검토" 개선 작업</span><span class="sxs-lookup"><span data-stu-id="6295f-239">Removed “not scored” and “review” improvement actions</span></span>

<span data-ttu-id="6295f-240">보안 점수 원칙 중 하나는 점수가 표준화 되 고 간편 하 게 관련 되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-240">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="6295f-241">기능을 사용할 수 없거나 작업을 수행 하는 향상 된 기능으로 인해 혼동이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-241">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="6295f-242">한 Microsoft 보안 점수는 모든 권장 사항이 점수에 분명 하 게 영향을 미칠 수 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-242">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="6295f-243">점수가 매겨지지 않음 개선 조치를 수행할 수 없으며, 향상 된 개선 작업을 다른 개선 작업과 동일한 표준으로 측정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-243">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>

<span data-ttu-id="6295f-244">이러한 이유로 검토 흐름에 대해 점수가 매겨지지 않거나 필요한 모든 개선 작업이 일시적으로 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-244">For these reasons, all improvement actions that were not scored or required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="6295f-245">해당 부분에 대 한 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-245">No action is needed on your part.</span></span>

### <a name="simplification-of-the-point-system"></a><span data-ttu-id="6295f-246">지점 시스템 간소화</span><span class="sxs-lookup"><span data-stu-id="6295f-246">Simplification of the point system</span></span>

<span data-ttu-id="6295f-247">여러 환경에서 점수를 표준화 하기 위해 각 보안 점수 향상 동작 지점 합계가 10 포인트이 하까지 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-247">To standardize points across multiple experiences, each Secure Score improvement action point total has been updated to be worth 10 points or less.</span></span> <span data-ttu-id="6295f-248">현재와 미래에 추가 될 수 있는 보안 컨트롤의 광범위 한 breather에서 더 일관 된 기능을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-248">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="6295f-249">이 변경 내용이 중요 하 여 저장 지점 합계가 변경 되는 동안에는 보안 환경을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-249">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="6295f-250">사용자의 의견을 듣고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-250">We want to hear from you</span></span>

<span data-ttu-id="6295f-251">문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에서 게시할 때 알려주십시오.</span><span class="sxs-lookup"><span data-stu-id="6295f-251">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="6295f-252">당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6295f-252">We're monitoring the community and will provide help.</span></span>
