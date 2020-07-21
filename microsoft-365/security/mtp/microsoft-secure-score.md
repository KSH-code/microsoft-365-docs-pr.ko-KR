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
ms.openlocfilehash: 862a25eddda6048349df937641914377cb25874f
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200041"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="5d305-104">Microsoft 보안 점수</span><span class="sxs-lookup"><span data-stu-id="5d305-104">Microsoft Secure Score</span></span>

<span data-ttu-id="5d305-105">Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="5d305-106">이 도구 https://security.microsoft.com/securescore 는 [Microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="5d305-107">보안 점수 권장 사항을 따르면 위협 으로부터 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="5d305-108">Microsoft 365 보안 센터의 중앙 집중식 대시보드를 통해 조직은 Microsoft 365 id, 데이터, 앱, 장치 및 인프라의 보안을 모니터링 하 고 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="5d305-109">보안 점수가 조직에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="5d305-110">조직의 보안 환경의 현재 상태를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="5d305-111">검색, 표시 유형, 지침 및 제어 기능을 제공 하 여 보안 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="5d305-112">벤치 마크와 비교 하 여 Kpi (핵심 성과 지표)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="5d305-113">조직은 메트릭 및 추세의 견고한 시각화, 다른 Microsoft 제품과의 통합, 비슷한 조직과의 점수 비교에 대 한 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="5d305-114">이 점수는 타사 솔루션에서 권장 작업을 해결 한 경우에도 반영 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="5d305-116">작업 방법</span><span class="sxs-lookup"><span data-stu-id="5d305-116">How it works</span></span>

<span data-ttu-id="5d305-117">권장 되는 보안 기능을 구성 하 고, 보안 관련 작업을 수행 하거나, 타사 응용 프로그램 또는 소프트웨어를 사용 하 여 개선 작업을 처리 하거나, 대체 문제를 해결 하기 위한 사항이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-117">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software, or an alternate mitigation.</span></span> <span data-ttu-id="5d305-118">일부 향상 작업은 완전히 완료 된 경우에만 점수를 제공 하며 일부 장치 또는 사용자에 대해 완료 되 면 일부를 부분 포인트로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="5d305-119">개선 작업 중 하나를 규정 하지 않으려는 경우 위험 또는 남은 위험을 수락 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-119">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="5d305-120">지원 되는 Microsoft 제품 중 하나에 대 한 라이선스가 있는 경우 해당 제품에 대 한 추천을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-120">If you have a license for one of the supported Microsoft products, then you will see recommendations for those products.</span></span> <span data-ttu-id="5d305-121">라이선스 버전, 구독 또는 계획에 관계 없이 제품에 대 한 모든 향상 된 기능을 확인할 수 있으므로, 보안 모범 사례를 이해 하 고 점수를 높일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-121">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="5d305-122">절대 보안 고 지는 조직이 특정 제품에 대해 소유한 라이선스에 관계 없이 동일 하 게 유지 되는 보안 점수로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-122">Your absolute security posture is represented by Secure Score, which stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="5d305-123">보안은 유용성과 균형을 유지 해야 하며 모든 권장 사항이 환경에 적합 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-123">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="5d305-124">점수가 실시간으로 업데이트 되어 시각화 및 향상 작업 페이지에 제공 된 정보를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-124">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="5d305-125">또한 보안 점수가 매일 동기화 되어 각 작업에 대 한 시스템 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-125">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="5d305-126">주요 시나리오</span><span class="sxs-lookup"><span data-stu-id="5d305-126">Key scenarios</span></span>

- [<span data-ttu-id="5d305-127">현재 점수 확인</span><span class="sxs-lookup"><span data-stu-id="5d305-127">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="5d305-128">점수를 사용자와 같은 조직에 비교</span><span class="sxs-lookup"><span data-stu-id="5d305-128">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="5d305-129">개선 작업 보기 및 작업 계획 결정</span><span class="sxs-lookup"><span data-stu-id="5d305-129">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="5d305-130">조사 하거나 구현 하기 위한 워크플로 시작</span><span class="sxs-lookup"><span data-stu-id="5d305-130">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="5d305-131">Microsoft 365 보안 센터 및 ServiceNow 통합</span><span class="sxs-lookup"><span data-stu-id="5d305-131">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="5d305-132">개선 작업의 점수를 획득 하는 방법</span><span class="sxs-lookup"><span data-stu-id="5d305-132">How improvement actions are scored</span></span>

<span data-ttu-id="5d305-133">각 향상 작업은 10 점 이내에 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-133">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="5d305-134">대부분은 이진 방식으로 점수가 지정 되며, 새 정책 만들기 또는 특정 설정을 사용 하는 것과 같은 개선 작업을 구현 하는 경우에는 점수가 100% 인 점수를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-134">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="5d305-135">다른 향상 작업의 경우 점수는 전체 구성에 대 한 비율로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-135">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="5d305-136">예를 들어, 향상 작업에 다단계 인증을 사용 하 여 모든 사용자를 보호 하 여 10 점을 확보 하 고 100 명의 총 사용자 50만 보호 하는 경우에는 5 개 점수 (50 protected/100 total \* 10 max points = 5 포인트의 부분적인 점수)가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-136">For example, if the improvement action states you get 10 points by protecting all your users with multi-factor authentication and you only have 50 of 100 total users protected, you would be given a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="5d305-137">안전한 점수에 포함 된 제품</span><span class="sxs-lookup"><span data-stu-id="5d305-137">Products included in Secure Score</span></span>

<span data-ttu-id="5d305-138">현재 Microsoft 365 (Exchange Online 포함), Azure AD, Microsoft Defender ATP, Azure ATP 및 Cloud App Security에 대 한 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-138">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="5d305-139">다른 보안 제품에 대 한 권장 사항은 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-139">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="5d305-140">권장 사항은 각 제품과 연결 된 모든 공격 표면을 다루지는 않지만 좋은 기준이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-140">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="5d305-141">또한 제 3 자 또는 다른 완화 조치로 인 한 향상 작업을 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-141">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="5d305-142">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="5d305-142">Security defaults</span></span>

<span data-ttu-id="5d305-143">Microsoft 보안 점수에는 [Azure Active Directory에서 보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 지원 하기 위해 개선 작업이 업데이트 되었으며, 일반적인 공격에 대 한 미리 구성 된 보안 설정을 사용 하 여 조직을 보다 쉽게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-143">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="5d305-144">보안 기본값을 설정 하면 다음과 같은 개선 작업에 대 한 전체 점수가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-144">If you turn on security defaults, you will be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="5d305-145">모든 사용자가 보안 액세스에 대 한 다단계 인증을 완료할 수 있는지 확인 (9 포인트)</span><span class="sxs-lookup"><span data-stu-id="5d305-145">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="5d305-146">관리 역할에 대 한 MFA 필요 (10 포인트)</span><span class="sxs-lookup"><span data-stu-id="5d305-146">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="5d305-147">정책을 사용 하 여 레거시 인증을 차단 합니다 (7 포인트).</span><span class="sxs-lookup"><span data-stu-id="5d305-147">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="5d305-148">보안 기본값에는 "로그인 위험 정책" 및 "사용자 위험 정책" 개선 작업에 비슷한 보안 기능을 제공 하는 보안 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-148">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="5d305-149">보안 기본값에서 이러한 정책을 설정 하는 대신, 상태를 "대안 완화"로 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-149">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="5d305-150">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="5d305-150">Required permissions</span></span>

<span data-ttu-id="5d305-151">Microsoft 보안 점수에 액세스할 수 있는 권한을 부여 하려면 Azure Active Directory에서 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-151">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="5d305-152">읽기 및 쓰기 역할</span><span class="sxs-lookup"><span data-stu-id="5d305-152">Read and write roles</span></span>

<span data-ttu-id="5d305-153">읽기 및 쓰기 액세스를 사용 하 여 변경을 수행 하 고 보안 점수와 직접 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-153">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="5d305-154">또한 다른 사용자에 게 읽기 전용 액세스 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-154">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="5d305-155">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="5d305-155">Global administrator</span></span>
* <span data-ttu-id="5d305-156">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="5d305-156">Security administrator</span></span>
* <span data-ttu-id="5d305-157">Exchange 관리자</span><span class="sxs-lookup"><span data-stu-id="5d305-157">Exchange administrator</span></span>
* <span data-ttu-id="5d305-158">SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="5d305-158">SharePoint administrator</span></span>
* <span data-ttu-id="5d305-159">계정 관리자</span><span class="sxs-lookup"><span data-stu-id="5d305-159">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="5d305-160">읽기 전용 역할</span><span class="sxs-lookup"><span data-stu-id="5d305-160">Read-only roles</span></span>

<span data-ttu-id="5d305-161">읽기 전용 액세스 권한을 사용 하면 향상 작업에 대 한 상태나 메모를 편집 하거나, 점수 영역을 편집 하거나, 사용자 지정 비교를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-161">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="5d305-162">헬프데스크 관리자</span><span class="sxs-lookup"><span data-stu-id="5d305-162">Helpdesk administrator</span></span>
* <span data-ttu-id="5d305-163">사용자 관리자</span><span class="sxs-lookup"><span data-stu-id="5d305-163">User administrator</span></span>
* <span data-ttu-id="5d305-164">서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="5d305-164">Service administrator</span></span>
* <span data-ttu-id="5d305-165">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="5d305-165">Security reader</span></span>
* <span data-ttu-id="5d305-166">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="5d305-166">Security operator</span></span>
* <span data-ttu-id="5d305-167">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="5d305-167">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="5d305-168">위험 인식</span><span class="sxs-lookup"><span data-stu-id="5d305-168">Risk awareness</span></span>

<span data-ttu-id="5d305-169">Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 한 보안 환경을 나타내는 수치 요약입니다. 시스템 또는 데이터를 얼마나 많이 침해 해야 하는지 절대 측정 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-169">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="5d305-170">대신 Microsoft 환경에서 보안 제어를 채택 하는 범위를 나타내므로 위반 위험을 상쇄 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-170">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="5d305-171">보안 침해에의 한 온라인 서비스에는 전혀 문제가 되지 않으며 보안 점수가 보안상 침해에 대 한 보장으로 해석 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-171">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="5d305-172">사용자의 의견을 듣고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-172">We want to hear from you</span></span>

<span data-ttu-id="5d305-173">문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에서 게시할 때 알려주십시오.</span><span class="sxs-lookup"><span data-stu-id="5d305-173">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="5d305-174">당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="5d305-175">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="5d305-175">Related resources</span></span>

- [<span data-ttu-id="5d305-176">보안 환경을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d305-176">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="5d305-177">Microsoft 보안 점수 기록 및 목표를 충족 하는 추적</span><span class="sxs-lookup"><span data-stu-id="5d305-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="5d305-178">향후 계획</span><span class="sxs-lookup"><span data-stu-id="5d305-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="5d305-179">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="5d305-179">What's new</span></span>](microsoft-secure-score-whats-new.md)
