---
title: 파일럿 Microsoft 365 Defender 실행
description: 프로덕션에서 Microsoft 365 Defender 파일럿 프로젝트를 실행하여 프로젝트의 이점과 채택을 Microsoft 365 Defender.
keywords: Microsoft 365 Defender 파일럿, 파일럿 Microsoft 365 Defender 프로젝트 실행, 프로덕션 Microsoft 365 Defender 평가, Microsoft 365 Defender 파일럿 프로젝트, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: fd84ef93d679be6e1e42f823dcac1f2d5181f1e9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289958"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="7fa2d-104">파일럿 Microsoft 365 Defender 실행</span><span class="sxs-lookup"><span data-stu-id="7fa2d-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7fa2d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7fa2d-105">**Applies to:**</span></span>
- <span data-ttu-id="7fa2d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fa2d-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="7fa2d-107">이 가이드에서는 포인터를 제공하여 체계적인 계획을 세우고, 공격 시뮬레이션 기능을 사용하는 방법을 안내하고, 최종적으로 주요 이행을 끝내고 결과를 반영하고 문서화할 수 있도록 파일럿 프로젝트를 실행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![파일럿 실행의 Microsoft 365 Defender 단계](../../media/pilotphases.png)


<span data-ttu-id="7fa2d-109">파일럿을 실행하면 파일럿 도입의 이점을 효과적으로 확인할 수 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="7fa2d-110">프로덕션 환경에서 Microsoft 365 Defender 사용 사례를 시작하기 전에 파일럿 프로젝트에 대해 수행할 작업을 결정하고 성공 기준을 설정하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="7fa2d-111">이 파일럿 플레이북을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="7fa2d-111">How to use this pilot playbook</span></span>

<span data-ttu-id="7fa2d-112">이 가이드에서는 파일럿 프로젝트를 설정하는 Microsoft 365 Defender 단계별 지침을 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="7fa2d-113">Microsoft 365 Defender 엔드포인트, ID, 전자 메일 및 응용 프로그램에서 기본적으로 보호, 탐지, 방지, 조사 및 대응을 조정하여 정교한 공격으로부터 통합된 보호를 제공하는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군입니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="7fa2d-114">이를 위해 다음 기능을 단일 보안 솔루션으로 결합하고 오케스트레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>

- <span data-ttu-id="7fa2d-115">끝점용 Microsoft Defender(끝점)</span><span class="sxs-lookup"><span data-stu-id="7fa2d-115">Microsoft Defender for Endpoint (endpoints)</span></span>
- <span data-ttu-id="7fa2d-116">Microsoft Defender for Office 365(전자 메일)</span><span class="sxs-lookup"><span data-stu-id="7fa2d-116">Microsoft Defender for Office 365 (email)</span></span>
- <span data-ttu-id="7fa2d-117">Microsoft Defender for Identity(ID)</span><span class="sxs-lookup"><span data-stu-id="7fa2d-117">Microsoft Defender for Identity (identity)</span></span>
- <span data-ttu-id="7fa2d-118">Microsoft Cloud App Security(앱)</span><span class="sxs-lookup"><span data-stu-id="7fa2d-118">Microsoft Cloud App Security (apps)</span></span>

![클라우드 of_Microsoft 앱, Microsoft Cloud App Security 및 데이터용 끝점에 대한 사용자용 Microsoft Defender 365 Defender 솔루션인 ID용 Microsoft Defender를 Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="7fa2d-120">통합된 Microsoft 365 Defender 솔루션을 사용하여 보안 전문가는 끝점용 Microsoft Defender, Office 365, ID용 Microsoft Defender 및 Microsoft Cloud App Security 수신하는 위협 신호를 통합하고 위협의 전체 범위와 영향, 환경에 들어오는 방법, 영향을 받는 방법 및 현재 조직에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="7fa2d-121">Microsoft 365 Defender 공격을 방지하거나 중지하고 영향을 받는 사서함, 끝점 및 사용자 ID를 자동으로 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="7fa2d-122">자세한 [내용은 Microsoft 365 Defender 개요를](microsoft-365-defender.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>

<span data-ttu-id="7fa2d-123">다음 샘플 타임라인은 환경에 적합한 리소스를 확보하는 데 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="7fa2d-124">일부 검색 및 워크플로는 다른 검색보다 학습 시간이 더 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-124">Some detections and workflows might need more learning time than the others.</span></span>

![파일럿 실행 시 샘플 Microsoft 365 Defender 시간 표시 막대](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> <span data-ttu-id="7fa2d-126">최적의 결과를 얻기 위해 가능한 한 파일럿 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>

### <a name="pilot-playbook-phases"></a><span data-ttu-id="7fa2d-127">파일럿 플레이북 단계</span><span class="sxs-lookup"><span data-stu-id="7fa2d-127">Pilot playbook phases</span></span>

<span data-ttu-id="7fa2d-128">파일럿 실행에는 네 가지 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="7fa2d-129">단계</span><span class="sxs-lookup"><span data-stu-id="7fa2d-129">Phase</span></span> | <span data-ttu-id="7fa2d-130">설명</span><span class="sxs-lookup"><span data-stu-id="7fa2d-130">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="7fa2d-131">계획</span><span class="sxs-lookup"><span data-stu-id="7fa2d-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="7fa2d-132">~ 1일</span><span class="sxs-lookup"><span data-stu-id="7fa2d-132">~ 1 day</span></span>| <span data-ttu-id="7fa2d-133">파일럿 프로젝트를 실행하기 전에 고려해야 할 Microsoft 365 Defender 대해 알아보고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="7fa2d-134">- 범위</span><span class="sxs-lookup"><span data-stu-id="7fa2d-134">- Scope</span></span> <br> <span data-ttu-id="7fa2d-135">- 사용 사례</span><span class="sxs-lookup"><span data-stu-id="7fa2d-135">- Use cases</span></span> <br><span data-ttu-id="7fa2d-136">- 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fa2d-136">- Requirements</span></span> <br><span data-ttu-id="7fa2d-137">- 테스트 계획</span><span class="sxs-lookup"><span data-stu-id="7fa2d-137">- Test plan</span></span> <br> <span data-ttu-id="7fa2d-138">- 성공 기준</span><span class="sxs-lookup"><span data-stu-id="7fa2d-138">- Success criteria</span></span> <br> <span data-ttu-id="7fa2d-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="7fa2d-139">- Scorecard</span></span> 
| [<span data-ttu-id="7fa2d-140">준비</span><span class="sxs-lookup"><span data-stu-id="7fa2d-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="7fa2d-141">~2일</span><span class="sxs-lookup"><span data-stu-id="7fa2d-141">~2 days</span></span>|  <span data-ttu-id="7fa2d-142">보안 Microsoft 365 액세스하여 파일럿 Microsoft 365 Defender 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="7fa2d-143">다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-143">You'll be guided to:</span></span><br><br><span data-ttu-id="7fa2d-144">- 관련자 식별 및 파일럿에 대한 사인오프 검색</span><span class="sxs-lookup"><span data-stu-id="7fa2d-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="7fa2d-145">- 환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7fa2d-145">- Environment considerations</span></span> <br><span data-ttu-id="7fa2d-146">- Access</span><span class="sxs-lookup"><span data-stu-id="7fa2d-146">- Access</span></span> <br><span data-ttu-id="7fa2d-147">- Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="7fa2d-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="7fa2d-148">- 구성 순서</span><span class="sxs-lookup"><span data-stu-id="7fa2d-148">- Configuration order</span></span> <br> <span data-ttu-id="7fa2d-149">- 평가판에 Microsoft 365 E5 등록</span><span class="sxs-lookup"><span data-stu-id="7fa2d-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="7fa2d-150">- 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="7fa2d-150">- Configure domain</span></span> <br><span data-ttu-id="7fa2d-151">- Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="7fa2d-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="7fa2d-152">- 포털에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="7fa2d-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="7fa2d-153">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="7fa2d-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="7fa2d-154">~2일</span><span class="sxs-lookup"><span data-stu-id="7fa2d-154">~2 days</span></span>| <span data-ttu-id="7fa2d-155">공격을 시뮬레이션하기 위해 다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="7fa2d-156">- 테스트 환경 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="7fa2d-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="7fa2d-157">- 시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="7fa2d-157">-  Run the simulation</span></span> <br><span data-ttu-id="7fa2d-158">- 인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="7fa2d-158">- Investigate an incident</span></span> <br><span data-ttu-id="7fa2d-159">- 인시던트 해결</span><span class="sxs-lookup"><span data-stu-id="7fa2d-159">- resolve the incident</span></span> 
| [<span data-ttu-id="7fa2d-160">닫기 및 요약</span><span class="sxs-lookup"><span data-stu-id="7fa2d-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="7fa2d-161">~ 1일</span><span class="sxs-lookup"><span data-stu-id="7fa2d-161">~ 1 day</span></span>| <span data-ttu-id="7fa2d-162">프로세스의 끝에 도달하면 다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="7fa2d-163">- 최종 출력을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-163">- Go through your final output</span></span><br><span data-ttu-id="7fa2d-164">- 이해 관계자에게 출력 표시</span><span class="sxs-lookup"><span data-stu-id="7fa2d-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="7fa2d-165">- 피드백 제공</span><span class="sxs-lookup"><span data-stu-id="7fa2d-165">- Provide feedback</span></span> <br><span data-ttu-id="7fa2d-166">- 다음 단계 수행</span><span class="sxs-lookup"><span data-stu-id="7fa2d-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="7fa2d-167">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7fa2d-167">Next step</span></span>

|[<span data-ttu-id="7fa2d-168">계획 단계</span><span class="sxs-lookup"><span data-stu-id="7fa2d-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="7fa2d-169">파일럿 Microsoft 365 Defender 계획</span><span class="sxs-lookup"><span data-stu-id="7fa2d-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
