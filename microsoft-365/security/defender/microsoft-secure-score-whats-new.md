---
title: Microsoft 보안 점수의 새로운
description: 보안 센터에서 Microsoft 보안 점수에 대한 새로운 변경 Microsoft 365 설명
keywords: Microsoft 보안 점수, 보안 점수, Office 365 보안 점수, Microsoft 보안 점수, Microsoft 365 보안 센터
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
ms.openlocfilehash: b3f86dfbc1ae89eff61c680737061b01998a527b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933868"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="74802-104">Microsoft 보안 점수의 새로운</span><span class="sxs-lookup"><span data-stu-id="74802-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="74802-105">Microsoft 보안 점수가 보안 자세를 보다 잘 대표할 수 있도록 몇 가지 변경 사항을 적용해 두었다.</span><span class="sxs-lookup"><span data-stu-id="74802-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="74802-106">계획된 변경에 대한 자세한 내용은 Microsoft 보안 [점수의 출시 예정을 참조하세요.](microsoft-secure-score-whats-coming.md)</span><span class="sxs-lookup"><span data-stu-id="74802-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

<span data-ttu-id="74802-107">Microsoft 보안 점수는 보안 센터의 Microsoft 365 https://security.microsoft.com/securescore [있습니다.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="74802-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>
    
## <a name="february-2021"></a><span data-ttu-id="74802-108">2021년 2월</span><span class="sxs-lookup"><span data-stu-id="74802-108">February 2021</span></span>

### <a name="compatibility-with-graph-api"></a><span data-ttu-id="74802-109">API와 Graph 호환성</span><span class="sxs-lookup"><span data-stu-id="74802-109">Compatibility with Graph API</span></span>

<span data-ttu-id="74802-110">Graph API를 통해 전달되는 Microsoft 보안 점수 권장 사항은 현재 보안 센터의 권장 사항과 Microsoft 365 가중치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-110">Microsoft Secure Score recommendations delivered via Graph API will look and be weighted the same as the recommendations you currently see in the Microsoft 365 security center.</span></span>

## <a name="january-2021"></a><span data-ttu-id="74802-111">2021년 1월</span><span class="sxs-lookup"><span data-stu-id="74802-111">January 2021</span></span>

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a><span data-ttu-id="74802-112">보안에 대한 첫 번째 보안 권장 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74802-112">Added our first security recommendation for Microsoft Teams</span></span>

<span data-ttu-id="74802-113">Microsoft Teams 고객에게 보안 점수의 새로운 개선 작업으로 "익명 사용자의 모임 참가 제한"이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-113">Microsoft Teams customers will see "Restrict anonymous users from joining meetings" as a new improvement action in Secure Score.</span></span>

## <a name="december-2020"></a><span data-ttu-id="74802-114">2020년 12월</span><span class="sxs-lookup"><span data-stu-id="74802-114">December 2020</span></span>

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="74802-115">끝점용 Microsoft Defender에 대한 6개의 계정 관련 개선 작업이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-115">Added six accounts-related improvement actions for Microsoft Defender for Endpoint:</span></span>

- <span data-ttu-id="74802-116">'최소 암호 길이'를 '14자 이상'으로 설정</span><span class="sxs-lookup"><span data-stu-id="74802-116">Set 'Minimum password length' to '14 or more characters'</span></span>
- <span data-ttu-id="74802-117">'암호 기록 적용'을 '24개 이상의 암호'로 설정</span><span class="sxs-lookup"><span data-stu-id="74802-117">Set 'Enforce password history' to '24 or more password(s)'</span></span>
- <span data-ttu-id="74802-118">'최대 암호 사용 기간'을 '60일 이하'로 설정하고 0일은 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-118">Set 'Maximum password age' to '60 or fewer days, but not 0'</span></span>
- <span data-ttu-id="74802-119">'최소 암호 사용'을 '1일 이상'으로 설정</span><span class="sxs-lookup"><span data-stu-id="74802-119">Set 'Minimum password age' to '1 or more day(s)'</span></span>
- <span data-ttu-id="74802-120">기본 제공 관리자 계정을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="74802-120">Disable the built-in Administrator account</span></span>
- <span data-ttu-id="74802-121">기본 제공 게스트 계정을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="74802-121">Disable the built-in Guest account</span></span>

## <a name="november-2020"></a><span data-ttu-id="74802-122">2020년 11월</span><span class="sxs-lookup"><span data-stu-id="74802-122">November 2020</span></span>

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a><span data-ttu-id="74802-123">보안 점수를 통해 ServiceNow 티켓을 만드는 기능을 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-123">Removed the ability to create ServiceNow tickets through Secure Score</span></span> 

<span data-ttu-id="74802-124">Share > **ServiceNow로** 진행하여 보안 점수를 통해 ServiceNow 티켓을 만드는 기능을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-124">The ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** is no longer available.</span></span> <span data-ttu-id="74802-125">다음 단계를 결정하는 동안 피드백을 보내주시고 지원을 계속해 주셔서 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="74802-125">Thank you for your feedback and continued support while we determine next steps.</span></span>

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="74802-126">끝점용 Microsoft Defender에 대한 세 가지 서비스 관련 개선 작업이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-126">Added three services-related improvement actions for Microsoft Defender for Endpoint:</span></span>

- <span data-ttu-id="74802-127">서비스에서 인용되지 않은 서비스 Windows 수정</span><span class="sxs-lookup"><span data-stu-id="74802-127">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="74802-128">서비스 실행 경로를 일반적인 보호된 위치로 변경</span><span class="sxs-lookup"><span data-stu-id="74802-128">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="74802-129">Windows 레지스트리에서 캐시된 암호를 방지하는 서비스 계정 변경</span><span class="sxs-lookup"><span data-stu-id="74802-129">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="74802-130">2020년 10월</span><span class="sxs-lookup"><span data-stu-id="74802-130">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="74802-131">끝점용 Microsoft Defender와 관련된 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="74802-131">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="74802-132">경고 Microsoft Defender SmartScreen Windows 스토어 앱 웹 콘텐츠 확인 설정</span><span class="sxs-lookup"><span data-stu-id="74802-132">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="74802-133">2020년 8월</span><span class="sxs-lookup"><span data-stu-id="74802-133">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="74802-134">업데이트된 업데이트된 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="74802-134">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="74802-135">정책을 사용하여 레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="74802-135">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score"></a><span data-ttu-id="74802-136">ID 보안 점수와 비호화</span><span class="sxs-lookup"><span data-stu-id="74802-136">Incompatibility with Identity Secure Score</span></span>

<span data-ttu-id="74802-137">Microsoft 보안 점수의 최근 릴리스에서는 향상된 점수 모델이 릴리스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-137">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="74802-138">이러한 변경을 통해 보안 자세를 보다 유연하고 정확하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-138">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="74802-139">그러나 이러한 업데이트로 Microsoft 보안 점수가 ID 보안 점수와 일시적으로 양호하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-139">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score.</span></span>

<span data-ttu-id="74802-140">시간이 지난 후 ID 보안 점수는 새로운 점수 매기기 모델을 채택합니다.</span><span class="sxs-lookup"><span data-stu-id="74802-140">In time, Identity Secure Score will adopt the new scoring model.</span></span> <span data-ttu-id="74802-141">그 때까지 고객은 Microsoft 보안 점수와 ID 보안 점수에서 보고한 점수의 차이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-141">Until then, customers will see differences in the scores reported by Microsoft Secure Score and the Identity Secure Score.</span></span> <span data-ttu-id="74802-142">이로 인해 불편을 드려 죄송합니다. 이러한 환경이 향후에 더 호환될 수 있도록 보장하기 위해 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="74802-142">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="74802-143">개선 작업 업데이트</span><span class="sxs-lookup"><span data-stu-id="74802-143">Updated improvement actions</span></span>

- <span data-ttu-id="74802-144">개선 Azure Active Directory 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-144">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="74802-145">ID 개선 작업에 대한 Microsoft Defender 추가</span><span class="sxs-lookup"><span data-stu-id="74802-145">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="74802-146">Endpoint Threat 및 & 관리 보안 권장 사항에 대한 Microsoft [Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 지원</span><span class="sxs-lookup"><span data-stu-id="74802-146">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="74802-147">이제 TVM에서 제공하는 모든 릴리스된 보안 권장 사항을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74802-147">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="74802-148">인터페이스 및 기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="74802-148">Updated interface and functionality</span></span>

* <span data-ttu-id="74802-149">CISO 및 주도 수준 토론에 대한 모든 새로운 메트릭 및 추세 보기</span><span class="sxs-lookup"><span data-stu-id="74802-149">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="74802-150">점수를 추적하고 벤치마크하는 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="74802-150">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="74802-151">점수 회귀에 대한 더 나은 추적 및 이해</span><span class="sxs-lookup"><span data-stu-id="74802-151">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="74802-152">개선 작업 필터링, 태그, 검색 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="74802-152">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="74802-153">점수 투영 및 계획된 작업을 사용하여 향후 목표에 대한 관리</span><span class="sxs-lookup"><span data-stu-id="74802-153">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="74802-154">그리고 더 많은!</span><span class="sxs-lookup"><span data-stu-id="74802-154">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="74802-155">의견을 보내 주세요.</span><span class="sxs-lookup"><span data-stu-id="74802-155">We want to hear from you</span></span>

<span data-ttu-id="74802-156">문제가 있는 경우 보안, 개인 정보 보호 및 규정 준수 커뮤니티에 게시하여 & [알려주세요.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="74802-156">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="74802-157">커뮤니티를 모니터링하고 있으며 도움을 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="74802-157">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="74802-158">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="74802-158">Related resources</span></span>

- [<span data-ttu-id="74802-159">보안 상태 평가</span><span class="sxs-lookup"><span data-stu-id="74802-159">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="74802-160">Microsoft 보안 점수 기록 추적 및 목표 충족</span><span class="sxs-lookup"><span data-stu-id="74802-160">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="74802-161">향후 계획</span><span class="sxs-lookup"><span data-stu-id="74802-161">What's coming</span></span>](microsoft-secure-score-whats-coming.md)