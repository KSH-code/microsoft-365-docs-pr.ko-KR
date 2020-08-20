---
title: Microsoft 보안 점수의 새로운 기능
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수가 변경된 새로운 사항에 대해 설명합니다.
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
ms.openlocfilehash: 644e12d3b9dfecc0a31c8d464033e41670bc7b88
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815234"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="e92ce-104">Microsoft 보안 점수의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e92ce-104">What's new in Microsoft Secure Score</span></span>

<span data-ttu-id="e92ce-105">Microsoft 보안 점수를 보다 정확하게 위한 보안 환경을 만들려면 몇 가지 사항을 변경하시기 가간 작업을 수행하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e92ce-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="e92ce-106">계획된 변경 사항에 대한 자세한 내용은 [Microsoft Secure Score를 통해 제공될 기능을 확인합니다.](microsoft-secure-score-whats-coming.md)</span><span class="sxs-lookup"><span data-stu-id="e92ce-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="july-2020"></a><span data-ttu-id="e92ce-107">2020년 7월</span><span class="sxs-lookup"><span data-stu-id="e92ce-107">July 2020</span></span>

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a><span data-ttu-id="e92ce-108">Azure Advanced Threat Protection에 대한 개선 작업 추가</span><span class="sxs-lookup"><span data-stu-id="e92ce-108">Adding improvement actions for Azure Advanced Threat Protection</span></span>

- <span data-ttu-id="e92ce-109">위험한 기본 이동 경로</span><span class="sxs-lookup"><span data-stu-id="e92ce-109">Risky lateral movement paths</span></span>
- <span data-ttu-id="e92ce-110">보안되지 않은 계정 특성</span><span class="sxs-lookup"><span data-stu-id="e92ce-110">Unsecure account attributes</span></span>
- <span data-ttu-id="e92ce-111">Active Directory 트러스트에서 보안 기능 사용</span><span class="sxs-lookup"><span data-stu-id="e92ce-111">Enable security features on Active Directory trusts</span></span>
- <span data-ttu-id="e92ce-112">ID의 보안되지 않은 SID 기록 특성 제거</span><span class="sxs-lookup"><span data-stu-id="e92ce-112">Remove unsecure SID history attributes from entities</span></span>

## <a name="june-2020"></a><span data-ttu-id="e92ce-113">2020년 6월</span><span class="sxs-lookup"><span data-stu-id="e92ce-113">June 2020</span></span>

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="e92ce-114">Microsoft Defender Advanced Threat Protection에 대한 향상 조치 제거</span><span class="sxs-lookup"><span data-stu-id="e92ce-114">Removed improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="e92ce-115">공격 범위 축소 규칙 켜기</span><span class="sxs-lookup"><span data-stu-id="e92ce-115">Turn on Attack Surface Reduction rules</span></span>

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="e92ce-116">Microsoft Defender Advanced Threat Protection에 대한 개선 조치 추가</span><span class="sxs-lookup"><span data-stu-id="e92ce-116">Added improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="e92ce-117">Adobe Reader에서 하위 프로세스를 만들 수 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-117">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="e92ce-118">임의 배포에 고급 보호 사용</span><span class="sxs-lookup"><span data-stu-id="e92ce-118">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="e92ce-119">모든 Office 응용 프로그램에서 하위 프로세스를 만드는 것을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="e92ce-119">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="e92ce-120">Office 응용 프로그램에서 실행 가능 콘텐츠를 만드는 것을 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-120">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="e92ce-121">JavaScript 또는 VBScript에서 다운로드된 실행 가능 콘텐츠 실행 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-121">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="e92ce-122">잠재적으로 조작된 스크립트 실행을 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-122">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="e92ce-123">메일 클라이언트 및 웹 메일에서 실행 콘텐츠 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-123">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="e92ce-124">Office 통신 응용 프로그램에서 하위 프로세스를 만드는 것을 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-124">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="e92ce-125">USB에서 실행되는 신뢰할 수 없는 프로세스와 서명되지 않은 프로세스 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-125">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="e92ce-126">WMI 이벤트 구독을 통해 지속성 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-126">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="e92ce-127">Office 응용 프로그램이 다른 프로세스에 코드를 삽입하는 작업을 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-127">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="e92ce-128">준비, 연령 또는 신뢰할 수 있는 목록 조건을 충족하지 않는 경우 실행 파일이 실행되지 않도록 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-128">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="e92ce-129">PSExec 및 WMI 명령에서 실행되는 프로세스 생성 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-129">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="e92ce-130">Windows 로컬 보안 기관 하위 시스템(2)에서 자격 증명 lsass.exe 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-130">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="e92ce-131">Office 매크로에서 Win32 API 호출 차단</span><span class="sxs-lookup"><span data-stu-id="e92ce-131">Block Win32 API calls from Office macros</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="e92ce-132">ID 보안 점수 및 Graph API와 이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="e92ce-132">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="e92ce-133">Microsoft 보안 점수의 최근 릴리스에서 개선된 점수 모델이 릴리스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e92ce-133">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="e92ce-134">이러한 변경 사항을 통해 보안 환경을 보다 유연하고 정확하고 정확한 보기로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e92ce-134">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="e92ce-135">그러나 이러한 업데이트는 ID 보안 점수 및 그래프 API와 일시적으로 호환되지 않아진 상태에서 Microsoft Secure Score로 만들였습니다.</span><span class="sxs-lookup"><span data-stu-id="e92ce-135">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="e92ce-136">시간으로 ID 보안 점수 및 Graph API가 새 점수 모델을 채택합니다.</span><span class="sxs-lookup"><span data-stu-id="e92ce-136">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="e92ce-137">고객에게Microsoft Secure Score, ID Secure Score 및 Graph API에서 보고한 점수에 차이점이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e92ce-137">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="e92ce-138">이러한 경험이 어우러지고, 이로 인해 이러한 환경이 더욱 호환되는지 확인하기 위해 노트하세요.</span><span class="sxs-lookup"><span data-stu-id="e92ce-138">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="e92ce-139">업데이트된 개선 작업</span><span class="sxs-lookup"><span data-stu-id="e92ce-139">Updated improvement actions</span></span>

- <span data-ttu-id="e92ce-140">Azure Active Directory 개선 작업 추가됨</span><span class="sxs-lookup"><span data-stu-id="e92ce-140">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="e92ce-141">Azure Advanced Threat Protection 개선 작업 추가됨</span><span class="sxs-lookup"><span data-stu-id="e92ce-141">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="e92ce-142">Microsoft Defender ATP [위협 & 취약성 관리 보안](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 권장 사항에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="e92ce-142">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="e92ce-143">현재 출시된 모든 보안 권장 사항이 이제 사용 가능</span><span class="sxs-lookup"><span data-stu-id="e92ce-143">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="e92ce-144">업데이트된 인터페이스 및 기능</span><span class="sxs-lookup"><span data-stu-id="e92ce-144">Updated interface and functionality</span></span>

* <span data-ttu-id="e92ce-145">CISO 및 리더 수준 토론에 대한 모든 새로운 메트릭 및 추세 보기</span><span class="sxs-lookup"><span data-stu-id="e92ce-145">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="e92ce-146">점수를 추적 및 벤치마크하는 새로운 방법</span><span class="sxs-lookup"><span data-stu-id="e92ce-146">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="e92ce-147">점수 회수에 대한 추적 및 이해 향상</span><span class="sxs-lookup"><span data-stu-id="e92ce-147">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="e92ce-148">개선 조치를 필터링, 태그, 검색 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="e92ce-148">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="e92ce-149">점수 프로젝션 및 계획된 작업을 사용하여 향후 목표 관리</span><span class="sxs-lookup"><span data-stu-id="e92ce-149">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="e92ce-150">기타!</span><span class="sxs-lookup"><span data-stu-id="e92ce-150">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="e92ce-151">Microsoft에서 날레이를 우리 저</span><span class="sxs-lookup"><span data-stu-id="e92ce-151">We want to hear from you</span></span>

<span data-ttu-id="e92ce-152">문제가 있는 경우 보안, 개인 정보 보호 및 준수 [커뮤니티에 &](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="e92ce-152">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="e92ce-153">커뮤니티 모니터링 및 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e92ce-153">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e92ce-154">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="e92ce-154">Related resources</span></span>

- [<span data-ttu-id="e92ce-155">보안 상태 평가</span><span class="sxs-lookup"><span data-stu-id="e92ce-155">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="e92ce-156">Microsoft 보안 점수 기록 추적 및 목표 충족</span><span class="sxs-lookup"><span data-stu-id="e92ce-156">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="e92ce-157">향후 계획</span><span class="sxs-lookup"><span data-stu-id="e92ce-157">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
