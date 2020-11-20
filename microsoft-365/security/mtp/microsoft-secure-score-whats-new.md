---
title: Microsoft 보안 점수의 새로운 기능
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수에 대 한 새로운 변경 사항에 대해 설명 합니다.
keywords: microsoft 보안 점수, 보안 점수, office 365 보안 점수, microsoft security 점수, microsoft 365 보안 센터
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
ms.openlocfilehash: 6d1358da465bd7e31ca7b234f140aa8e48bb7508
ms.sourcegitcommit: aa8d2de6ffac0157fffd14d0ea7f51ef0c287607
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49373998"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="08522-104">Microsoft 보안 점수의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="08522-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="08522-105">Microsoft 보안 점수가 보안 상태를 보다 효율적으로 대표 하도록 하기 위해 몇 가지 사항을 변경 했습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="08522-106">계획 된 변경 사항에 대 한 자세한 내용은 [Microsoft 보안 점수에서](microsoft-secure-score-whats-coming.md)제공 되는 기능을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08522-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

<span data-ttu-id="08522-107">Microsoft 보안 점수 https://security.microsoft.com/securescore 는 [microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="08522-108">11 월 2020</span><span class="sxs-lookup"><span data-stu-id="08522-108">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="08522-109">끝점에 대 한 Microsoft Defender에 대 한 서비스 관련 향상 작업 3 개 (이전의 Microsoft Defender ATP)가 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-109">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="08522-110">Windows 서비스에 대 한 따옴표 붙지 않은 서비스 경로 수정</span><span class="sxs-lookup"><span data-stu-id="08522-110">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="08522-111">서비스 실행 가능한 경로를 일반 보호 위치로 변경</span><span class="sxs-lookup"><span data-stu-id="08522-111">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="08522-112">Windows 레지스트리에서 캐시 된 암호를 사용 하지 않도록 서비스 계정 변경</span><span class="sxs-lookup"><span data-stu-id="08522-112">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="08522-113">2020년 10월</span><span class="sxs-lookup"><span data-stu-id="08522-113">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="08522-114">끝점에 대 한 Microsoft Defender와 관련 된 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="08522-114">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="08522-115">Microsoft Defender SmartScreen Windows 스토어 앱 웹 콘텐츠 검사를 설정 하 여 경고 표시</span><span class="sxs-lookup"><span data-stu-id="08522-115">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="08522-116">2020년 8월</span><span class="sxs-lookup"><span data-stu-id="08522-116">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="08522-117">Azure Active Directory에 대 한 개선 된 기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="08522-117">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="08522-118">정책을 사용 하 여 레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="08522-118">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="08522-119">Id 보안 점수 및 그래프 API와 호환 되지 않는 문제</span><span class="sxs-lookup"><span data-stu-id="08522-119">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="08522-120">최신 버전의 Microsoft 보안 점수에서는 향상 된 점수 매기기 모델이 출시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-120">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="08522-121">이러한 변경으로 인해 보안 환경을 보다 유연 하 고 정확 하 게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-121">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="08522-122">그러나 이러한 업데이트는 Microsoft 보안 점수가 Id 보안 점수 및 그래프 API와 일시적으로 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-122">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="08522-123">보안 성과를 식별 하 고 Graph API가 새 점수 매기기 모델을 채택 합니다.</span><span class="sxs-lookup"><span data-stu-id="08522-123">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="08522-124">그때까지 고객은 Microsoft 보안 점수, Id 보안 점수 및 그래프 API에서 보고 하는 점수의 차이를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-124">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="08522-125">이로 인해 불편을 끼쳐 드려서 죄송 하며, 향후 이러한 환경이 더 높은 호환성을 유지 하기 위해 노력 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-125">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="08522-126">업데이트 된 개선 작업</span><span class="sxs-lookup"><span data-stu-id="08522-126">Updated improvement actions</span></span>

- <span data-ttu-id="08522-127">Azure Active Directory 개선 작업 추가 됨</span><span class="sxs-lookup"><span data-stu-id="08522-127">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="08522-128">Id 향상 작업을 위해 Microsoft Defender를 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-128">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="08522-129">끝점 위협에 대 한 Microsoft Defender 지원 [& 취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="08522-129">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="08522-130">이제 TVM에서 제공 하는 모든 릴리스된 보안 권장 사항을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-130">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="08522-131">업데이트 된 인터페이스 및 기능</span><span class="sxs-lookup"><span data-stu-id="08522-131">Updated interface and functionality</span></span>

* <span data-ttu-id="08522-132">CISO 팀장 수준 토론을 위한 모든 새 메트릭 및 추세 보기</span><span class="sxs-lookup"><span data-stu-id="08522-132">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="08522-133">점수를 추적 하 고 벤치 마크 위한 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="08522-133">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="08522-134">점수 재발에 대 한 추적 및 이해 향상</span><span class="sxs-lookup"><span data-stu-id="08522-134">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="08522-135">개선 작업 필터링, 태그, 검색 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="08522-135">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="08522-136">점수 예측 및 계획 된 작업을 사용 하 여 향후 목표를 향해 관리</span><span class="sxs-lookup"><span data-stu-id="08522-136">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="08522-137">더 많은 내용을 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="08522-137">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="08522-138">사용자의 의견을 듣고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="08522-138">We want to hear from you</span></span>

<span data-ttu-id="08522-139">문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에 게시 하 여 알려 주세요.</span><span class="sxs-lookup"><span data-stu-id="08522-139">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="08522-140">당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="08522-140">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="08522-141">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="08522-141">Related resources</span></span>

- [<span data-ttu-id="08522-142">보안 상태 평가</span><span class="sxs-lookup"><span data-stu-id="08522-142">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="08522-143">Microsoft 보안 점수 기록 및 목표를 충족 하는 추적</span><span class="sxs-lookup"><span data-stu-id="08522-143">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="08522-144">향후 계획</span><span class="sxs-lookup"><span data-stu-id="08522-144">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
