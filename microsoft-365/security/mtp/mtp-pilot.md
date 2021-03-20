---
title: 파일럿 Microsoft 365 Defender 프로젝트 실행
description: 프로덕션에서 파일럿 Microsoft 365 Defender 프로젝트를 실행하여 Microsoft 365 Defender의 이점과 채택을 효과적으로 결정할 수 있습니다.
keywords: Microsoft 위협 방지 파일럿, 파일럿 Microsoft Threat Protection 프로젝트 실행, 프로덕션에서 Microsoft Threat Protection 평가, Microsoft Threat Protection 파일럿 프로젝트, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c6c373d084c7f7cf12073c6402695af644944bad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910873"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="198d4-104">파일럿 Microsoft 365 Defender 프로젝트 실행</span><span class="sxs-lookup"><span data-stu-id="198d4-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="198d4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="198d4-105">**Applies to:**</span></span>
- <span data-ttu-id="198d4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="198d4-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="198d4-107">이 가이드에서는 포인터를 제공하여 체계적인 계획을 세우고, 공격 시뮬레이션 기능을 사용하는 방법을 안내하고, 최종적으로 주요 이행을 끝내고 결과를 반영하고 문서화할 수 있도록 파일럿 프로젝트를 실행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Microsoft 365 Defender 파일럿 실행 단계](../../media/pilotphases.png)


<span data-ttu-id="198d4-109">파일럿을 실행하면 Microsoft 365 Defender 채택의 이점을 효과적으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="198d4-110">프로덕션 환경에서 Microsoft 365 Defender를 사용하도록 설정하고 사용 사례를 시작하기 전에 파일럿 프로젝트에 대해 수행할 작업을 결정하고 성공 기준을 설정하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="198d4-111">이 파일럿 플레이북을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="198d4-111">How to use this pilot playbook</span></span>

<span data-ttu-id="198d4-112">이 가이드에서는 Microsoft 365 Defender에 대한 개요와 파일럿 프로젝트를 설정하는 방법에 대한 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="198d4-113">Microsoft 365 Defender는 엔드포인트, ID, 전자 메일 및 응용 프로그램에서 기본적으로 보호, 탐지, 예방, 조사 및 대응을 조정하여 정교한 공격으로부터 통합된 보호를 제공하는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군입니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="198d4-114">이를 위해 다음 기능을 단일 보안 솔루션으로 결합하고 오케스트레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="198d4-115">끝점용 Microsoft Defender, Microsoft Defender Advanced Threat Protection의 새 이름(끝점)</span><span class="sxs-lookup"><span data-stu-id="198d4-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="198d4-116">Office 365 ATP의 새 이름인 Office 365용 Microsoft Defender(전자 메일)</span><span class="sxs-lookup"><span data-stu-id="198d4-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="198d4-117">Azure ATP의 새 이름인 Id용 Microsoft Defender(ID)</span><span class="sxs-lookup"><span data-stu-id="198d4-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="198d4-118">Microsoft Cloud App Security(앱)</span><span class="sxs-lookup"><span data-stu-id="198d4-118">Microsoft Cloud App Security (apps)</span></span>

![사용자용 of_Microsoft 365 Defender 솔루션, 끝점용 Microsoft Defender for Endpoint, 클라우드 앱용, Microsoft Cloud App Security 및 데이터용 Microsoft Defender for Office 365용 Microsoft Defender 솔루션](../../media/mtp/m365pillars.png)

<span data-ttu-id="198d4-120">통합된 Microsoft 365 Defender 솔루션을 사용하여 보안 전문가는 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, ID용 Microsoft Defender 및 Microsoft Cloud App Security에서 수신하는 위협 신호를 통합하고 위협의 전체 범위와 영향, 환경에 들어오는 방법, 영향을 받는 방법 및 현재 조직에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="198d4-121">Microsoft 365 Defender는 공격을 방지하거나 중지하고 영향을 받는 사서함, 끝점 및 사용자 ID를 자체적으로 고치기 위한 자동 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="198d4-122">자세한 내용은 [Microsoft 365 Defender 개요를](./microsoft-threat-protection.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="198d4-122">See the [Microsoft 365 Defender overview](./microsoft-threat-protection.md) for details.</span></span>



<span data-ttu-id="198d4-123">다음 샘플 타임라인은 환경에 적합한 리소스를 확보하는 데 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="198d4-124">일부 검색 및 워크플로는 다른 검색보다 학습 시간이 더 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-124">Some detections and workflows might need more learning time than the others.</span></span>

![Microsoft 365 Defender 파일럿 실행 시 샘플 타임라인](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="198d4-126">최적의 결과를 얻기 위해 가능한 한 파일럿 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="198d4-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="198d4-127">파일럿 플레이북 단계</span><span class="sxs-lookup"><span data-stu-id="198d4-127">Pilot playbook phases</span></span> 

<span data-ttu-id="198d4-128">Microsoft 365 Defender 파일럿을 실행하는 네 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="198d4-129">단계</span><span class="sxs-lookup"><span data-stu-id="198d4-129">Phase</span></span> | <span data-ttu-id="198d4-130">설명</span><span class="sxs-lookup"><span data-stu-id="198d4-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="198d4-131">계획</span><span class="sxs-lookup"><span data-stu-id="198d4-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="198d4-132">~ 1일</span><span class="sxs-lookup"><span data-stu-id="198d4-132">~ 1 day</span></span>| <span data-ttu-id="198d4-133">Microsoft 365 Defender 파일럿 프로젝트를 실행하기 전에 고려해야 할 사항에 대해 자세히 알아보고</span><span class="sxs-lookup"><span data-stu-id="198d4-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="198d4-134">- 범위</span><span class="sxs-lookup"><span data-stu-id="198d4-134">- Scope</span></span> <br> <span data-ttu-id="198d4-135">- 사용 사례</span><span class="sxs-lookup"><span data-stu-id="198d4-135">- Use cases</span></span> <br><span data-ttu-id="198d4-136">- 요구 사항</span><span class="sxs-lookup"><span data-stu-id="198d4-136">- Requirements</span></span> <br><span data-ttu-id="198d4-137">- 테스트 계획</span><span class="sxs-lookup"><span data-stu-id="198d4-137">- Test plan</span></span> <br> <span data-ttu-id="198d4-138">- 성공 기준</span><span class="sxs-lookup"><span data-stu-id="198d4-138">- Success criteria</span></span> <br> <span data-ttu-id="198d4-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="198d4-139">- Scorecard</span></span> 
| [<span data-ttu-id="198d4-140">준비</span><span class="sxs-lookup"><span data-stu-id="198d4-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="198d4-141">~2일</span><span class="sxs-lookup"><span data-stu-id="198d4-141">~2 days</span></span>|  <span data-ttu-id="198d4-142">Microsoft 365 보안 센터에 액세스하여 Microsoft 365 Defender 파일럿 환경을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="198d4-143">다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-143">You'll be guided to:</span></span><br><br><span data-ttu-id="198d4-144">- 관련자 식별 및 파일럿에 대한 사인오프 검색</span><span class="sxs-lookup"><span data-stu-id="198d4-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="198d4-145">- 환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="198d4-145">- Environment considerations</span></span> <br><span data-ttu-id="198d4-146">- Access</span><span class="sxs-lookup"><span data-stu-id="198d4-146">- Access</span></span> <br><span data-ttu-id="198d4-147">- Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="198d4-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="198d4-148">- 구성 순서</span><span class="sxs-lookup"><span data-stu-id="198d4-148">- Configuration order</span></span> <br> <span data-ttu-id="198d4-149">- Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="198d4-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="198d4-150">- 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="198d4-150">- Configure domain</span></span> <br><span data-ttu-id="198d4-151">- Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="198d4-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="198d4-152">- 포털에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="198d4-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="198d4-153">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="198d4-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="198d4-154">~2일</span><span class="sxs-lookup"><span data-stu-id="198d4-154">~2 days</span></span>| <span data-ttu-id="198d4-155">공격을 시뮬레이션하기 위해 다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="198d4-156">- 테스트 환경 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="198d4-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="198d4-157">- 시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="198d4-157">-  Run the simulation</span></span> <br><span data-ttu-id="198d4-158">- 인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="198d4-158">- Investigate an incident</span></span> <br><span data-ttu-id="198d4-159">- 인시던트 해결</span><span class="sxs-lookup"><span data-stu-id="198d4-159">- resolve the incident</span></span> 
| [<span data-ttu-id="198d4-160">닫기 및 요약</span><span class="sxs-lookup"><span data-stu-id="198d4-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="198d4-161">~ 1일</span><span class="sxs-lookup"><span data-stu-id="198d4-161">~ 1 day</span></span>| <span data-ttu-id="198d4-162">프로세스의 끝에 도달하면 다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="198d4-163">- 최종 출력을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="198d4-163">- Go through your final output</span></span><br><span data-ttu-id="198d4-164">- 이해 관계자에게 출력 표시</span><span class="sxs-lookup"><span data-stu-id="198d4-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="198d4-165">- 피드백 제공</span><span class="sxs-lookup"><span data-stu-id="198d4-165">- Provide feedback</span></span> <br><span data-ttu-id="198d4-166">- 다음 단계 수행</span><span class="sxs-lookup"><span data-stu-id="198d4-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="198d4-167">다음 단계</span><span class="sxs-lookup"><span data-stu-id="198d4-167">Next step</span></span>
|[<span data-ttu-id="198d4-168">계획 단계</span><span class="sxs-lookup"><span data-stu-id="198d4-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="198d4-169">Microsoft 365 Defender 파일럿 프로젝트 계획</span><span class="sxs-lookup"><span data-stu-id="198d4-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|