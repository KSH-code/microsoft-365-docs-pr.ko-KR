---
title: Microsoft Secure Score
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 보안 자세를 개선하는 방법 및 보안 관리자가 기대할 수 있는 기능을 기술합니다.
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
ms.openlocfilehash: 7fe5be065ee45700a1f08a39c8050757c3843f7b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682574"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="82c22-104">Microsoft 보안 점수</span><span class="sxs-lookup"><span data-stu-id="82c22-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="82c22-105">Microsoft 보안 점수는 조직의 보안 자세를 측정한 결과로, 수치가 높을수록 개선 작업이 더 많이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="82c22-106">Microsoft https://security.microsoft.com/securescore [365](overview-security-center.md)보안 센터에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="82c22-107">보안 점수 권장 사항을 따라 조직을 위협으로부터 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="82c22-108">Microsoft 365 보안 센터의 중앙 집중식 대시보드에서 조직은 Microsoft 365 ID, 앱 및 장치의 보안을 모니터링하고 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="82c22-109">보안 점수는 조직에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="82c22-110">조직의 보안 상태의 현재 상태를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="82c22-111">검색 가능성, 가시성, 지침 및 제어 기능을 제공하여 보안의 보안을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="82c22-112">벤치마크와 비교하여 KPIS(핵심 성과 지표)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="82c22-113">조직은 메트릭 및 추세의 강력한 시각화, 다른 Microsoft 제품과의 통합, 유사한 조직과의 점수 비교 등의 강력한 시각화에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="82c22-114">또한 타사 솔루션에서 권장 작업을 해결한 경우 점수가 반영될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="82c22-116">작업 방법</span><span class="sxs-lookup"><span data-stu-id="82c22-116">How it works</span></span>

<span data-ttu-id="82c22-117">다음 작업에 대한 포인트가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="82c22-118">권장 보안 기능 구성</span><span class="sxs-lookup"><span data-stu-id="82c22-118">Configuring recommended security features</span></span>
- <span data-ttu-id="82c22-119">보안 관련 작업 수행</span><span class="sxs-lookup"><span data-stu-id="82c22-119">Performing security-related tasks</span></span>
- <span data-ttu-id="82c22-120">타사 응용 프로그램 또는 소프트웨어를 사용하여 개선 작업 해결 또는 대체 완화</span><span class="sxs-lookup"><span data-stu-id="82c22-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="82c22-121">일부 개선 작업은 완전히 완료될 때만 포인트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="82c22-122">일부는 일부 장치 또는 사용자에 대해 완료된 경우 부분 지점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="82c22-123">개선 작업 중 하나를 제정할 수 없는 경우 위험 또는 남은 위험을 수용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="82c22-124">지원되는 Microsoft 제품 중 하나의 라이선스가 있는 경우 해당 제품에 대한 권장 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="82c22-125">라이선스 버전, 구독 또는 계획에 관계없이 제품에 대해 가능한 전체 개선된 기능 집합이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="82c22-126">이렇게 하면 보안 모범 사례를 이해하고 점수를 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="82c22-127">보안 점수로 표현되는 절대 보안 자세는 조직이 특정 제품에 대해 소유하는 라이선스에 상관없이 동일하게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="82c22-128">보안은 사용 가능성과 균형을 유지해야 하며, 모든 권장이 사용자 환경에 작동할 수 있는 것은 아니라는 사실에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="82c22-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="82c22-129">점수는 시각화 및 개선 작업 페이지에 제공된 정보를 반영하기 위해 실시간으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="82c22-130">또한 보안 점수는 매일 동기화하여 각 작업의 달성한 점수에 대한 시스템 데이터를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="82c22-131">주요 시나리오</span><span class="sxs-lookup"><span data-stu-id="82c22-131">Key scenarios</span></span>

- [<span data-ttu-id="82c22-132">현재 점수 확인</span><span class="sxs-lookup"><span data-stu-id="82c22-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="82c22-133">점수를 사용자와 같은 조직과 비교</span><span class="sxs-lookup"><span data-stu-id="82c22-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="82c22-134">개선 작업 보기 및 작업 계획 결정</span><span class="sxs-lookup"><span data-stu-id="82c22-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="82c22-135">조사 또는 구현을 위한 작업 흐름 시작</span><span class="sxs-lookup"><span data-stu-id="82c22-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="82c22-136">Microsoft 365 보안 센터 및 ServiceNow 통합</span><span class="sxs-lookup"><span data-stu-id="82c22-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="82c22-137">개선 작업 점수가 기록된 방법</span><span class="sxs-lookup"><span data-stu-id="82c22-137">How improvement actions are scored</span></span>

<span data-ttu-id="82c22-138">각 개선 작업은 10포인트 이하의 가치가 있으며 대부분의 점수는 이진수로 점수가 매겨진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="82c22-139">새 정책을 만들거나 특정 설정을 설정하는 등 개선 작업을 구현하면 100%의 포인트를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="82c22-140">다른 개선 작업의 경우 점은 전체 구성에 대한 백분율로 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="82c22-141">예를 들어 향상된 작업 상태는 다단계 인증으로 모든 사용자를 보호하여 10점을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="82c22-142">총 사용자 100명 중 50명만 보호할 수 있으므로 부분 점수(50 보호/ 총 100개 \* 10 max pts = 5pts)를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="82c22-143">보안 점수에 포함된 제품</span><span class="sxs-lookup"><span data-stu-id="82c22-143">Products included in Secure Score</span></span>

<span data-ttu-id="82c22-144">현재 Microsoft 365(Exchange Online 포함), Azure Active Directory, 끝점용 Microsoft Defender, ID용 Microsoft Defender 및 Cloud App Security에 대한 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Cloud App Security.</span></span> <span data-ttu-id="82c22-145">다른 보안 제품에 대한 권장 사항은 곧 제공될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="82c22-146">권장 사항은 각 제품과 관련된 모든 공격 표면을 다루지 않지만 좋은 기준입니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="82c22-147">또한 제3자 또는 대체 완화에 적용된 개선 작업을 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="82c22-148">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="82c22-148">Security defaults</span></span>

<span data-ttu-id="82c22-149">Microsoft Secure Score는 일반적인 공격에 대해 미리 구성한 보안 설정으로 조직을 보다 쉽게 보호할 수 있도록 [Azure Active Directory의](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)보안 기본값을 지원하기 위해 개선 작업을 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="82c22-150">보안 기본값을 설정하면 다음과 같은 개선 작업에 대한 전체 점수가 주어지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="82c22-151">모든 사용자가 보안 액세스를 위해 다단계 인증을 완료할 수 있도록 합니다(9포인트).</span><span class="sxs-lookup"><span data-stu-id="82c22-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="82c22-152">관리 역할에 MFA 필요(10포인트)</span><span class="sxs-lookup"><span data-stu-id="82c22-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="82c22-153">레거시 인증을 차단하는 정책 사용(7포인트)</span><span class="sxs-lookup"><span data-stu-id="82c22-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="82c22-154">보안 기본값에는 "로그인 위험 정책" 및 "사용자 위험 정책" 개선 작업과 유사한 보안을 제공하는 보안 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="82c22-155">보안 기본값 위에 이러한 정책을 설정하는 대신 상태를 "대체 완화를 통해 해결되었습니다."로 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="82c22-156">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="82c22-156">Required permissions</span></span>

<span data-ttu-id="82c22-157">Microsoft 보안 점수에 액세스할 수 있는 권한을 부여하려면 Azure Active Directory에서 다음 역할 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="82c22-158">역할 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="82c22-158">Read and write roles</span></span>

<span data-ttu-id="82c22-159">읽기 및 쓰기 액세스를 사용하면 변경을 통해 보안 점수와 직접 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="82c22-160">다른 사용자에게 읽기 전용 액세스를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="82c22-161">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="82c22-161">Global administrator</span></span>
* <span data-ttu-id="82c22-162">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="82c22-162">Security administrator</span></span>
* <span data-ttu-id="82c22-163">Exchange 관리자</span><span class="sxs-lookup"><span data-stu-id="82c22-163">Exchange administrator</span></span>
* <span data-ttu-id="82c22-164">SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="82c22-164">SharePoint administrator</span></span>
* <span data-ttu-id="82c22-165">계정 관리자</span><span class="sxs-lookup"><span data-stu-id="82c22-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="82c22-166">읽기 전용 역할</span><span class="sxs-lookup"><span data-stu-id="82c22-166">Read-only roles</span></span>

<span data-ttu-id="82c22-167">읽기 전용 액세스를 사용하면 개선 작업의 상태 또는 메모를 편집하거나, 점수 영역 편집 또는 사용자 지정 비교를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="82c22-168">헬프데스크 관리자</span><span class="sxs-lookup"><span data-stu-id="82c22-168">Helpdesk administrator</span></span>
* <span data-ttu-id="82c22-169">사용자 관리자</span><span class="sxs-lookup"><span data-stu-id="82c22-169">User administrator</span></span>
* <span data-ttu-id="82c22-170">서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="82c22-170">Service administrator</span></span>
* <span data-ttu-id="82c22-171">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="82c22-171">Security reader</span></span>
* <span data-ttu-id="82c22-172">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="82c22-172">Security operator</span></span>
* <span data-ttu-id="82c22-173">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="82c22-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="82c22-174">위험 인식</span><span class="sxs-lookup"><span data-stu-id="82c22-174">Risk awareness</span></span>

<span data-ttu-id="82c22-175">Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 하는 보안의 수치 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="82c22-176">이는 시스템 또는 데이터가 침해될 가능성에 대한 절대적인 측정치가 아니며,</span><span class="sxs-lookup"><span data-stu-id="82c22-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="82c22-177">그보다는 Microsoft 환경에서 보안 제어를 채택한 범위를 나타내며 위반 위험을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="82c22-178">온라인 서비스가 보안 위반으로부터 완전히 제거되지 않는 것은 아니며 보안 점수는 어떤 방식으로든 보안 위반에 대한 보장으로 해석되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="82c22-179">의견을 보내 주세요.</span><span class="sxs-lookup"><span data-stu-id="82c22-179">We want to hear from you</span></span>

<span data-ttu-id="82c22-180">문제가 있는 경우 보안, 개인 정보 보호 및 규정 준수 커뮤니티에 게시하여 [& 알려주세요.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="82c22-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="82c22-181">커뮤니티를 모니터링하고 있으며 도움을 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="82c22-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="82c22-182">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="82c22-182">Related resources</span></span>

- [<span data-ttu-id="82c22-183">보안 상태 평가</span><span class="sxs-lookup"><span data-stu-id="82c22-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="82c22-184">Microsoft 보안 점수 기록 추적 및 목표 충족</span><span class="sxs-lookup"><span data-stu-id="82c22-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="82c22-185">향후 계획</span><span class="sxs-lookup"><span data-stu-id="82c22-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="82c22-186">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="82c22-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
