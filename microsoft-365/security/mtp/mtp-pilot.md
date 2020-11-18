---
title: 파일럿 Microsoft 365 Defender 프로젝트 실행
description: Microsoft 365 Defender의 이점과 채택을 효과적으로 확인 하기 위해 프로덕션 환경에서 파일럿 Microsoft 365 Defender 프로젝트를 실행 합니다.
keywords: Microsoft 위협 보호 파일럿, 파일럿 Microsoft 위협 보호 프로젝트를 실행 하 고, microsoft threat protection 파일럿 프로젝트, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화 된 조사 및 업데이트, 고급 구하기 등을 평가 합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 50f334a055a5bd974f9ea1f39c8fa38d44be9c26
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131287"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="939d1-104">파일럿 Microsoft 365 Defender 프로젝트 실행</span><span class="sxs-lookup"><span data-stu-id="939d1-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="939d1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="939d1-105">**Applies to:**</span></span>
- <span data-ttu-id="939d1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="939d1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="939d1-107">Microsoft 365 Defender의 이점과 채택을 효과적으로 확인 하기 위해 파일럿 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-107">To effectively determine the benefit and adoption of Microsoft 365 Defender, you can run a pilot project.</span></span> <span data-ttu-id="939d1-108">프로덕션 환경에서 Microsoft 365 Defender를 사용 하도록 설정 하 고 사용 사례를 시작 하기 전에 파일럿 프로젝트에 대해 수행할 작업을 결정 하 고 성공 기준을 설정 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-108">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="939d1-109">이 파일럿 playbook를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="939d1-109">How to use this pilot playbook</span></span>

<span data-ttu-id="939d1-110">이 가이드에서는 Microsoft 365 Defender에 대 한 개요와 파일럿 프로젝트를 설정 하는 방법에 대 한 단계별 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-110">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="939d1-111">Microsoft 365 Defender는 여러 끝점, id, 전자 메일 및 응용 프로그램 간의 보호, 검색, 예방, 조사 및 응답을 고유 하 게 조정 하 고 복잡 한 공격에 대 한 통합 된 보호 기능을 제공 하는 통합 사전 및 사후 위반 엔터프라이즈 방어 제품군입니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-111">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="939d1-112">이를 위해 다음과 같은 기능을 단일 보안 솔루션으로 결합 하 고 orchestrating 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-112">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="939d1-113">끝점에 대 한 microsoft Defender, Microsoft Defender Advanced Threat Protection의 새 이름 (끝점)</span><span class="sxs-lookup"><span data-stu-id="939d1-113">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="939d1-114">Microsoft Defender for Office 365, Office 365 ATP의 새 이름 (전자 메일)</span><span class="sxs-lookup"><span data-stu-id="939d1-114">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="939d1-115">Id 용 Microsoft Defender, Azure ATP의 새 이름 (id)</span><span class="sxs-lookup"><span data-stu-id="939d1-115">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="939d1-116">Microsoft Cloud App Security (앱)</span><span class="sxs-lookup"><span data-stu-id="939d1-116">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 Defender solution for users 365, for a for a for a for a for a for a for a for a 사용자](../../media/mtp/m365pillars.png)

<span data-ttu-id="939d1-118">통합 Microsoft 365 Defender 솔루션을 사용 하 여 보안 전문가는 끝점, microsoft Defender for Office 365, microsoft Defender for Identity 및 Microsoft Cloud App Security receive에 대 한 위협 신호를 보내고, 위협의 전체 범위와 영향, 해당 환경의 진입 방식, 영향을 받는 방식 및 현재 조직에 영향을 주는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-118">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="939d1-119">Microsoft 365 Defender는 자동 작업을 수행 하 여 공격을 방지 하거나 중지 하 고 영향을 받는 사서함, 끝점 및 사용자 id를 자체 치유 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-119">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="939d1-120">자세한 내용은 [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d1-120">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>

![Microsoft 365 Defender 파일럿 실행 단계](../../media/pilotphases.png)

<span data-ttu-id="939d1-122">다음의 시간 표시 막대는 환경에 적절 한 리소스가 있는 경우에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-122">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="939d1-123">일부 검색 및 워크플로에는 다른 일부 사용자 보다 더 많은 학습 시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-123">Some detections and workflows might need more learning time than the others.</span></span>

![Microsoft 365 Defender 파일럿 실행의 샘플 시간 표시줄](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="939d1-125">최적의 결과를 위해 파일럿 지침을 최대한 면밀 하 게 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-125">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="939d1-126">파일럿 playbook 단계</span><span class="sxs-lookup"><span data-stu-id="939d1-126">Pilot playbook phases</span></span> 

<span data-ttu-id="939d1-127">Microsoft 365 Defender 파일럿을 실행 하는 데는 다음과 같은 네 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-127">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="939d1-128">단계</span><span class="sxs-lookup"><span data-stu-id="939d1-128">Phase</span></span> | <span data-ttu-id="939d1-129">설명</span><span class="sxs-lookup"><span data-stu-id="939d1-129">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="939d1-130">계획</span><span class="sxs-lookup"><span data-stu-id="939d1-130">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="939d1-131">~ 1 일</span><span class="sxs-lookup"><span data-stu-id="939d1-131">~ 1 day</span></span>| <span data-ttu-id="939d1-132">Microsoft 365 Defender 파일럿 프로젝트를 실행 하기 전에 고려해 야 할 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-132">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="939d1-133">-범위</span><span class="sxs-lookup"><span data-stu-id="939d1-133">- Scope</span></span> <br> <span data-ttu-id="939d1-134">-사용 사례</span><span class="sxs-lookup"><span data-stu-id="939d1-134">- Use cases</span></span> <br><span data-ttu-id="939d1-135">- 요구 사항</span><span class="sxs-lookup"><span data-stu-id="939d1-135">- Requirements</span></span> <br><span data-ttu-id="939d1-136">-테스트 계획</span><span class="sxs-lookup"><span data-stu-id="939d1-136">- Test plan</span></span> <br> <span data-ttu-id="939d1-137">-성공 조건</span><span class="sxs-lookup"><span data-stu-id="939d1-137">- Success criteria</span></span> <br> <span data-ttu-id="939d1-138">-성과 기록표</span><span class="sxs-lookup"><span data-stu-id="939d1-138">- Scorecard</span></span> 
| [<span data-ttu-id="939d1-139">미리</span><span class="sxs-lookup"><span data-stu-id="939d1-139">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="939d1-140">~ 2 일</span><span class="sxs-lookup"><span data-stu-id="939d1-140">~2 days</span></span>|  <span data-ttu-id="939d1-141">Microsoft 365 보안 센터에 액세스 하 여 Microsoft 365 Defender 파일럿 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-141">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="939d1-142">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-142">You'll be guided to:</span></span><br><br><span data-ttu-id="939d1-143">-관련자 식별 및 파일럿에 대 한 승인 찾기</span><span class="sxs-lookup"><span data-stu-id="939d1-143">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="939d1-144">-환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="939d1-144">- Environment considerations</span></span> <br><span data-ttu-id="939d1-145">-액세스</span><span class="sxs-lookup"><span data-stu-id="939d1-145">- Access</span></span> <br><span data-ttu-id="939d1-146">-Azure Active Directory 설치</span><span class="sxs-lookup"><span data-stu-id="939d1-146">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="939d1-147">-구성 순서</span><span class="sxs-lookup"><span data-stu-id="939d1-147">- Configuration order</span></span> <br> <span data-ttu-id="939d1-148">-Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="939d1-148">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="939d1-149">-도메인 구성</span><span class="sxs-lookup"><span data-stu-id="939d1-149">- Configure domain</span></span> <br><span data-ttu-id="939d1-150">-Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="939d1-150">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="939d1-151">-포털에서 설치 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="939d1-151">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="939d1-152">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="939d1-152">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="939d1-153">~ 2 일</span><span class="sxs-lookup"><span data-stu-id="939d1-153">~2 days</span></span>| <span data-ttu-id="939d1-154">공격을 시뮬레이트하기 위해 다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-154">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="939d1-155">-테스트 환경 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="939d1-155">- Verify the test environment requirements</span></span> <br><span data-ttu-id="939d1-156">-시뮬레이션을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-156">-  Run the simulation</span></span> <br><span data-ttu-id="939d1-157">-문제 조사</span><span class="sxs-lookup"><span data-stu-id="939d1-157">- Investigate an incident</span></span> <br><span data-ttu-id="939d1-158">-인시던트를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-158">- resolve the incident</span></span> 
| [<span data-ttu-id="939d1-159">맺음말 및 요약</span><span class="sxs-lookup"><span data-stu-id="939d1-159">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="939d1-160">~ 1 일</span><span class="sxs-lookup"><span data-stu-id="939d1-160">~ 1 day</span></span>| <span data-ttu-id="939d1-161">프로세스의 끝에 도달 하면 다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d1-161">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="939d1-162">-최종 출력으로 이동</span><span class="sxs-lookup"><span data-stu-id="939d1-162">- Go through your final output</span></span><br><span data-ttu-id="939d1-163">-결과를 이해 관계자에 게 제공</span><span class="sxs-lookup"><span data-stu-id="939d1-163">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="939d1-164">-사용자 의견 제공</span><span class="sxs-lookup"><span data-stu-id="939d1-164">- Provide feedback</span></span> <br><span data-ttu-id="939d1-165">-다음 단계 수행</span><span class="sxs-lookup"><span data-stu-id="939d1-165">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="939d1-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="939d1-166">Next step</span></span>
|[<span data-ttu-id="939d1-167">계획 단계</span><span class="sxs-lookup"><span data-stu-id="939d1-167">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="939d1-168">Microsoft 365 Defender 파일럿 프로젝트 계획</span><span class="sxs-lookup"><span data-stu-id="939d1-168">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
