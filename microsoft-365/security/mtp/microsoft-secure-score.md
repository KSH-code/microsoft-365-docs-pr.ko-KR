---
title: Microsoft Secure Score
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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094801"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="1ecb4-104">Microsoft 보안 점수</span><span class="sxs-lookup"><span data-stu-id="1ecb4-104">Microsoft Secure Score</span></span>

<span data-ttu-id="1ecb4-105">Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="1ecb4-106">이 도구 https://security.microsoft.com/securescore 는 [Microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="1ecb4-107">보안 점수 권장 사항을 따르면 위협 으로부터 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="1ecb4-108">Microsoft 365 보안 센터의 중앙 집중식 대시보드를 통해 조직은 Microsoft 365 id, 데이터, 앱, 장치 및 인프라의 보안을 모니터링 하 고 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="1ecb4-109">보안 점수가 조직에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="1ecb4-110">조직의 보안 환경의 현재 상태를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="1ecb4-111">검색, 표시 유형, 지침 및 제어 기능을 제공 하 여 보안 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="1ecb4-112">벤치 마크와 비교 하 여 Kpi (핵심 성과 지표)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="1ecb4-113">조직은 메트릭 및 추세의 견고한 시각화, 다른 Microsoft 제품과의 통합, 비슷한 조직과의 점수 비교에 대 한 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="1ecb4-114">이 점수는 타사 솔루션에서 권장 작업을 해결 한 경우에도 반영 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="1ecb4-116">작업 방법</span><span class="sxs-lookup"><span data-stu-id="1ecb4-116">How it works</span></span>

<span data-ttu-id="1ecb4-117">권장 되는 보안 기능을 구성 하 고, 보안 관련 작업을 수행 하거나, 타사 응용 프로그램 또는 소프트웨어를 사용 하 여 개선 작업을 처리 하거나, 대체 문제를 해결 하기 위한 사항이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-117">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software, or an alternate mitigation.</span></span> <span data-ttu-id="1ecb4-118">일부 향상 작업은 완전히 완료 된 경우에만 점수를 제공 하며 일부 장치 또는 사용자에 대해 완료 되 면 일부를 부분 포인트로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="1ecb4-119">개선 작업 중 하나를 규정 하지 않으려는 경우 위험 또는 남은 위험을 수락 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-119">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="1ecb4-120">라이선스에 관계 없이 향상 된 가능한 전체 기능을 제공 하 여 보안 모범 사례를 이해 하 고 점수를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-120">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="1ecb4-121">절대 보안 상태는 조직이 소유한 제품 라이선스에 관계 없이 동일 하 게 유지 되는 보안 점수를 통해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-121">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="1ecb4-122">보안은 유용성과 균형을 유지 해야 하며 모든 권장 사항이 환경에 적합 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-122">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="1ecb4-123">점수가 실시간으로 업데이트 되어 시각화 및 향상 작업 페이지에 제공 된 정보를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-123">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="1ecb4-124">또한 보안 점수가 매일 동기화 되어 각 작업에 대 한 시스템 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-124">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="1ecb4-125">주요 시나리오</span><span class="sxs-lookup"><span data-stu-id="1ecb4-125">Key scenarios</span></span>

- [<span data-ttu-id="1ecb4-126">현재 점수 확인</span><span class="sxs-lookup"><span data-stu-id="1ecb4-126">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="1ecb4-127">점수를 사용자와 같은 조직에 비교</span><span class="sxs-lookup"><span data-stu-id="1ecb4-127">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="1ecb4-128">개선 작업 보기 및 작업 계획 결정</span><span class="sxs-lookup"><span data-stu-id="1ecb4-128">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="1ecb4-129">조사 하거나 구현 하기 위한 워크플로 시작</span><span class="sxs-lookup"><span data-stu-id="1ecb4-129">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="1ecb4-130">Microsoft 365 보안 센터 및 ServiceNow 통합</span><span class="sxs-lookup"><span data-stu-id="1ecb4-130">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="1ecb4-131">개선 작업의 점수를 획득 하는 방법</span><span class="sxs-lookup"><span data-stu-id="1ecb4-131">How improvement actions are scored</span></span>

<span data-ttu-id="1ecb4-132">각 향상 작업은 10 점 이내에 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-132">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="1ecb4-133">대부분은 이진 방식으로 점수가 지정 되며, 새 정책 만들기 또는 특정 설정을 사용 하는 것과 같은 개선 작업을 구현 하는 경우에는 점수가 100% 인 점수를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-133">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="1ecb4-134">다른 향상 작업의 경우 점수는 전체 구성에 대 한 비율로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-134">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="1ecb4-135">예를 들어, 향상 작업에 다단계 인증을 사용 하 여 모든 사용자를 보호 하 여 10 점을 확보 하 고 100 명의 총 사용자 50만 보호 하는 경우에는 5 개 점수 (50 protected/100 total \* 10 max points = 5 포인트의 부분적인 점수)가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-135">For example, if the improvement action states you get 10 points by protecting all your users with multi-factor authentication and you only have 50 of 100 total users protected, you would be given a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="1ecb4-136">안전한 점수에 포함 된 제품</span><span class="sxs-lookup"><span data-stu-id="1ecb4-136">Products included in Secure Score</span></span>

<span data-ttu-id="1ecb4-137">현재 Microsoft 365 (Exchange Online 포함), Azure AD, Microsoft Defender ATP, Azure ATP 및 Cloud App Security에 대 한 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-137">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="1ecb4-138">다른 보안 제품에 대 한 권장 사항은 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-138">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="1ecb4-139">권장 사항은 각 제품과 연결 된 모든 공격 표면을 다루지는 않지만 좋은 기준이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-139">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="1ecb4-140">또한 제 3 자 또는 다른 완화 조치로 인 한 향상 작업을 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-140">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="1ecb4-141">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="1ecb4-141">Security defaults</span></span>

<span data-ttu-id="1ecb4-142">Microsoft 보안 점수에는 [Azure Active Directory에서 보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 지원 하기 위해 개선 작업이 업데이트 되었으며, 일반적인 공격에 대 한 미리 구성 된 보안 설정을 사용 하 여 조직을 보다 쉽게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-142">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="1ecb4-143">보안 기본값을 설정 하면 다음과 같은 개선 작업에 대 한 전체 점수가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-143">If you turn on security defaults, you will be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="1ecb4-144">모든 사용자가 보안 액세스에 대 한 다단계 인증을 완료할 수 있는지 확인 (9 포인트)</span><span class="sxs-lookup"><span data-stu-id="1ecb4-144">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="1ecb4-145">관리 역할에 대 한 MFA 필요 (10 포인트)</span><span class="sxs-lookup"><span data-stu-id="1ecb4-145">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="1ecb4-146">정책을 사용 하 여 레거시 인증을 차단 합니다 (7 포인트).</span><span class="sxs-lookup"><span data-stu-id="1ecb4-146">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="1ecb4-147">보안 기본값에는 "로그인 위험 정책" 및 "사용자 위험 정책" 개선 작업에 비슷한 보안 기능을 제공 하는 보안 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-147">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="1ecb4-148">보안 기본값에서 이러한 정책을 설정 하는 대신, 상태를 "대안 완화"로 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-148">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="1ecb4-149">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="1ecb4-149">Required permissions</span></span>

<span data-ttu-id="1ecb4-150">Microsoft 보안 점수에 액세스할 수 있는 권한을 부여 하려면 Azure Active Directory에서 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-150">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="1ecb4-151">읽기 및 쓰기 역할</span><span class="sxs-lookup"><span data-stu-id="1ecb4-151">Read and write roles</span></span>

<span data-ttu-id="1ecb4-152">읽기 및 쓰기 액세스를 사용 하 여 변경을 수행 하 고 보안 점수와 직접 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-152">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="1ecb4-153">또한 다른 사용자에 게 읽기 전용 액세스 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-153">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="1ecb4-154">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-154">Global administrator</span></span>
* <span data-ttu-id="1ecb4-155">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-155">Security administrator</span></span>
* <span data-ttu-id="1ecb4-156">Exchange 관리자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-156">Exchange administrator</span></span>
* <span data-ttu-id="1ecb4-157">SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-157">SharePoint administrator</span></span>
* <span data-ttu-id="1ecb4-158">계정 관리자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-158">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="1ecb4-159">읽기 전용 역할</span><span class="sxs-lookup"><span data-stu-id="1ecb4-159">Read-only roles</span></span>

<span data-ttu-id="1ecb4-160">읽기 전용 액세스 권한을 사용 하면 향상 작업에 대 한 상태나 메모를 편집 하거나, 점수 영역을 편집 하거나, 사용자 지정 비교를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-160">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="1ecb4-161">헬프데스크 관리자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-161">Helpdesk administrator</span></span>
* <span data-ttu-id="1ecb4-162">사용자 관리자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-162">User administrator</span></span>
* <span data-ttu-id="1ecb4-163">서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-163">Service administrator</span></span>
* <span data-ttu-id="1ecb4-164">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-164">Security reader</span></span>
* <span data-ttu-id="1ecb4-165">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-165">Security operator</span></span>
* <span data-ttu-id="1ecb4-166">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="1ecb4-166">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="1ecb4-167">위험 인식</span><span class="sxs-lookup"><span data-stu-id="1ecb4-167">Risk awareness</span></span>

<span data-ttu-id="1ecb4-168">Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 한 보안 환경을 나타내는 수치 요약입니다. 시스템 또는 데이터를 얼마나 많이 침해 해야 하는지 절대 측정 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-168">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="1ecb4-169">대신 Microsoft 환경에서 보안 제어를 채택 하는 범위를 나타내므로 위반 위험을 상쇄 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-169">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="1ecb4-170">보안 침해에의 한 온라인 서비스에는 전혀 문제가 되지 않으며 보안 점수가 보안상 침해에 대 한 보장으로 해석 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-170">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="1ecb4-171">어떠한 새로운 기능이 있나요?</span><span class="sxs-lookup"><span data-stu-id="1ecb4-171">What's new?</span></span> 

<span data-ttu-id="1ecb4-172">Microsoft 보안 점수가 보안 상태를 보다 효율적으로 대표 하도록 하기 위해 몇 가지 사항을 변경 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-172">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="1ecb4-173">계획 된 변경 사항에 대 한 자세한 내용은 [Microsoft 보안 점수에서](microsoft-secure-score-whats-coming.md)제공 되는 기능을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-173">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="1ecb4-174">Id 보안 점수 및 그래프 API와 호환 되지 않는 문제</span><span class="sxs-lookup"><span data-stu-id="1ecb4-174">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="1ecb4-175">최신 버전의 Microsoft 보안 점수에서는 향상 된 점수 매기기 모델이 출시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-175">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="1ecb4-176">이러한 변경으로 인해 보안 환경을 보다 유연 하 고 정확 하 게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-176">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="1ecb4-177">그러나 이러한 업데이트는 Microsoft 보안 점수가 Id 보안 점수 및 그래프 API와 일시적으로 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-177">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="1ecb4-178">보안 성과를 식별 하 고 Graph API가 새 점수 매기기 모델을 채택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-178">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="1ecb4-179">그때까지 고객은 Microsoft 보안 점수, Id 보안 점수 및 그래프 API에서 보고 하는 점수의 차이를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-179">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="1ecb4-180">이로 인해 불편을 끼쳐 드려서 죄송 하며, 향후 이러한 환경이 더 높은 호환성을 유지 하기 위해 노력 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-180">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

### <a name="updated-improvement-actions"></a><span data-ttu-id="1ecb4-181">업데이트 된 개선 작업</span><span class="sxs-lookup"><span data-stu-id="1ecb4-181">Updated improvement actions</span></span>

- <span data-ttu-id="1ecb4-182">Azure Active Directory 개선 작업 추가 됨</span><span class="sxs-lookup"><span data-stu-id="1ecb4-182">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="1ecb4-183">Azure Advanced Threat Protection 개선 작업 추가</span><span class="sxs-lookup"><span data-stu-id="1ecb4-183">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="1ecb4-184">Microsoft Defender ATP [위협 & 취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 보안 권장 사항에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="1ecb4-184">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="1ecb4-185">이제 TVM에서 제공 하는 모든 릴리스된 보안 권장 사항을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-185">All released security recommendations supplied by TVM are now available</span></span>

### <a name="updated-interface-and-functionality"></a><span data-ttu-id="1ecb4-186">업데이트 된 인터페이스 및 기능</span><span class="sxs-lookup"><span data-stu-id="1ecb4-186">Updated interface and functionality</span></span>

* <span data-ttu-id="1ecb4-187">CISO 팀장 수준 토론을 위한 모든 새 메트릭 및 추세 보기</span><span class="sxs-lookup"><span data-stu-id="1ecb4-187">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="1ecb4-188">점수를 추적 하 고 벤치 마크 위한 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="1ecb4-188">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="1ecb4-189">점수 재발에 대 한 추적 및 이해 향상</span><span class="sxs-lookup"><span data-stu-id="1ecb4-189">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="1ecb4-190">개선 작업 필터링, 태그, 검색 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="1ecb4-190">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="1ecb4-191">점수 예측 및 계획 된 작업을 사용 하 여 향후 목표를 향해 관리</span><span class="sxs-lookup"><span data-stu-id="1ecb4-191">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="1ecb4-192">더 많은 내용을 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-192">And more!</span></span>

### <a name="june-2020"></a><span data-ttu-id="1ecb4-193">2020년 6월</span><span class="sxs-lookup"><span data-stu-id="1ecb4-193">June 2020</span></span>

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="1ecb4-194">Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 제거 됨</span><span class="sxs-lookup"><span data-stu-id="1ecb4-194">Removed improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="1ecb4-195">공격 표면 축소 규칙 켜기</span><span class="sxs-lookup"><span data-stu-id="1ecb4-195">Turn on Attack Surface Reduction rules</span></span>

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="1ecb4-196">Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 추가</span><span class="sxs-lookup"><span data-stu-id="1ecb4-196">Added improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="1ecb4-197">하위 프로세스를 만들지 못하도록 Adobe Reader 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-197">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="1ecb4-198">랜 섬 웨어에 대 한 고급 보호 사용</span><span class="sxs-lookup"><span data-stu-id="1ecb4-198">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="1ecb4-199">모든 Office 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-199">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="1ecb4-200">Office 응용 프로그램에서 실행 가능한 콘텐츠를 만들지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-200">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="1ecb4-201">다운로드 한 실행 가능한 콘텐츠를 실행 하는 JavaScript 또는 VBScript 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-201">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="1ecb4-202">잠재적으로 난독 처리 된 스크립트의 실행 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-202">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="1ecb4-203">전자 메일 클라이언트 및 webmail에서 실행 가능한 콘텐츠 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-203">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="1ecb4-204">Office 통신 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-204">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="1ecb4-205">신뢰할 수 없으며 USB에서 실행 되는 서명 되지 않은 프로세스 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-205">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="1ecb4-206">WMI 이벤트 구독을 통해 지 속성 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-206">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="1ecb4-207">Office 응용 프로그램에서 다른 프로세스에 코드를 주입 하지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-207">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="1ecb4-208">실행 파일이 전파, 연령 또는 신뢰할 수 있는 목록 조건을 충족 하지 않는 이상 실행 되지 않도록 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-208">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="1ecb4-209">PSExec 및 WMI 명령에서 시작 되는 프로세스 만들기 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-209">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="1ecb4-210">Windows 로컬 보안 기관 하위 시스템 (lsass.exe)에서 자격 증명 가로채기 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-210">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="1ecb4-211">Office 매크로에서 Win32 API 호출 차단</span><span class="sxs-lookup"><span data-stu-id="1ecb4-211">Block Win32 API calls from Office macros</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="1ecb4-212">사용자의 의견을 듣고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-212">We want to hear from you</span></span>

<span data-ttu-id="1ecb4-213">문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에서 게시할 때 알려주십시오.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-213">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="1ecb4-214">당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-214">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="1ecb4-215">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="1ecb4-215">Related resources</span></span>

- [<span data-ttu-id="1ecb4-216">보안 환경을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ecb4-216">Gain visibility into your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="1ecb4-217">Microsoft 보안 점수 기록 및 목표를 충족 하는 추적</span><span class="sxs-lookup"><span data-stu-id="1ecb4-217">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="1ecb4-218">향후 계획</span><span class="sxs-lookup"><span data-stu-id="1ecb4-218">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
