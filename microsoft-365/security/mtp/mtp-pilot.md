---
title: 파일럿 Microsoft Threat Protection 프로젝트 실행
description: MTP (Microsoft Threat Protection)의 이점과 채택을 효과적으로 파악 하기 위해 프로덕션 환경에서 파일럿 Microsoft 위협 보호 프로젝트를 실행 합니다.
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
ms.openlocfilehash: f49f1afe5461a4f2eff0a3049f1d14d1892f70ce
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477023"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="dd69b-104">파일럿 Microsoft Threat Protection 프로젝트 실행</span><span class="sxs-lookup"><span data-stu-id="dd69b-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dd69b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="dd69b-105">**Applies to:**</span></span>
- <span data-ttu-id="dd69b-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="dd69b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="dd69b-107">MTP (Microsoft Threat Protection)의 이점과 채택을 효과적으로 확인 하기 위해 파일럿 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="dd69b-108">프로덕션 환경에서 Microsoft Threat Protection을 사용 하도록 설정 하 고 사용 사례를 시작 하기 전에 파일럿 프로젝트에 대해 수행할 작업을 결정 하 고 성공 기준을 설정 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-108">Before enabling Microsoft Threat Protection in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="dd69b-109">이 파일럿 playbook를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dd69b-109">How to use this pilot playbook</span></span>

<span data-ttu-id="dd69b-110">이 가이드에서는 Microsoft Threat Protection에 대 한 개요와 파일럿 프로젝트를 설정 하는 방법에 대 한 단계별 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="dd69b-111">Microsoft Threat Protection은 보안, 검색, 예방, 조사 및 끝점, id, 전자 메일 및 응용 프로그램 간의 응답을 고유 하 게 조정 하 여 정교한 공격에 대 한 통합 된 보호 기능을 제공 하는 통합 사전 및 사후 위반 엔터프라이즈 방어 제품군입니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-111">Microsoft Threat Protection is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="dd69b-112">이를 위해 다음과 같은 기능을 단일 보안 솔루션으로 결합 하 고 orchestrating 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-112">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="dd69b-113">끝점에 대 한 microsoft Defender, Microsoft Defender Advanced Threat Protection의 새 이름 (끝점)</span><span class="sxs-lookup"><span data-stu-id="dd69b-113">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="dd69b-114">Microsoft Defender for Office 365, Office 365 ATP의 새 이름 (전자 메일)</span><span class="sxs-lookup"><span data-stu-id="dd69b-114">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="dd69b-115">Id 용 Microsoft Defender, Azure ATP의 새 이름 (id)</span><span class="sxs-lookup"><span data-stu-id="dd69b-115">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="dd69b-116">Microsoft Cloud App Security (앱)</span><span class="sxs-lookup"><span data-stu-id="dd69b-116">Microsoft Cloud App Security (apps)</span></span>

![<span data-ttu-id="dd69b-117">사용자, Azure Advanced threat protection, 끝점에 대 한 위협 보호 솔루션, Microsoft Defender Advanced Threat Protection, 클라우드 앱, Microsoft Cloud App Security 및 data의 경우 Office 365 Advanced Threat Protection of_Microsoft</span><span class="sxs-lookup"><span data-stu-id="dd69b-117">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp/m365pillars.png)

<span data-ttu-id="dd69b-118">통합 Microsoft 위협 보호 솔루션을 사용 하는 경우 보안 전문가는 Microsoft Defender Advanced Threat Protection, Office 365 ATP, Azure ATP 및 Microsoft Cloud App Security 수신에 게 신호를 보내고, 위협의 전체 범위와 영향, 해당 환경의 진입 방식, 영향을 받는 방식 및 조직에 현재 적용 되는 방식을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-118">With the integrated Microsoft Threat Protection solution, security professionals can stitch together the threat signals that Microsoft Defender Advanced Threat Protection, Office 365 ATP, Azure ATP, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="dd69b-119">Microsoft Threat Protection은 공격을 방지 하거나 중지 하는 자동 작업을 수행 하 고 영향을 받는 사서함, 끝점 및 사용자 id를 자체 치유 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-119">Microsoft Threat Protection takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="dd69b-120">자세한 내용은 [Microsoft Threat Protection 개요](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd69b-120">See the [Microsoft Threat Protection overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>

![Microsoft Threat Protection 파일럿 실행 단계](../../media/pilotphases.png)

<span data-ttu-id="dd69b-122">다음의 시간 표시 막대는 환경에 적절 한 리소스가 있는 경우에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-122">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="dd69b-123">일부 검색 및 워크플로에는 다른 일부 사용자 보다 더 많은 학습 시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-123">Some detections and workflows might need more learning time than the others.</span></span>

![Microsoft Threat Protection 파일럿 실행을 위한 샘플 시간 표시줄](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="dd69b-125">최적의 결과를 위해 파일럿 지침을 최대한 면밀 하 게 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-125">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="dd69b-126">파일럿 playbook 단계</span><span class="sxs-lookup"><span data-stu-id="dd69b-126">Pilot playbook phases</span></span> 

<span data-ttu-id="dd69b-127">Microsoft Threat Protection 파일럿을 실행 하는 데는 다음과 같은 네 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-127">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="dd69b-128">단계</span><span class="sxs-lookup"><span data-stu-id="dd69b-128">Phase</span></span> | <span data-ttu-id="dd69b-129">설명</span><span class="sxs-lookup"><span data-stu-id="dd69b-129">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="dd69b-130">![계획](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="dd69b-130">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="dd69b-131">계획</span><span class="sxs-lookup"><span data-stu-id="dd69b-131">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="dd69b-132">Microsoft Threat Protection 파일럿 프로젝트를 실행 하기 전에 고려해 야 할 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-132">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="dd69b-133">-범위</span><span class="sxs-lookup"><span data-stu-id="dd69b-133">- Scope</span></span> <br> <span data-ttu-id="dd69b-134">-사용 사례</span><span class="sxs-lookup"><span data-stu-id="dd69b-134">- Use cases</span></span> <br><span data-ttu-id="dd69b-135">- 요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd69b-135">- Requirements</span></span> <br><span data-ttu-id="dd69b-136">-테스트 계획</span><span class="sxs-lookup"><span data-stu-id="dd69b-136">- Test plan</span></span> <br> <span data-ttu-id="dd69b-137">-성공 조건</span><span class="sxs-lookup"><span data-stu-id="dd69b-137">- Success criteria</span></span> <br> <span data-ttu-id="dd69b-138">-성과 기록표</span><span class="sxs-lookup"><span data-stu-id="dd69b-138">- Scorecard</span></span> 
| <span data-ttu-id="dd69b-139">![미리](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="dd69b-139">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="dd69b-140">미리</span><span class="sxs-lookup"><span data-stu-id="dd69b-140">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="dd69b-141">Microsoft 365 보안 센터에 액세스 하 여 Microsoft Threat Protection 파일럿 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-141">Access Microsoft 365 Security Center to set up your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="dd69b-142">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-142">You'll be guided to:</span></span><br><br><span data-ttu-id="dd69b-143">-관련자 식별 및 파일럿에 대 한 승인 찾기</span><span class="sxs-lookup"><span data-stu-id="dd69b-143">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="dd69b-144">-환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="dd69b-144">- Environment considerations</span></span> <br><span data-ttu-id="dd69b-145">-액세스</span><span class="sxs-lookup"><span data-stu-id="dd69b-145">- Access</span></span> <br><span data-ttu-id="dd69b-146">-Azure Active Directory 설치</span><span class="sxs-lookup"><span data-stu-id="dd69b-146">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="dd69b-147">-구성 순서</span><span class="sxs-lookup"><span data-stu-id="dd69b-147">- Configuration order</span></span> <br> <span data-ttu-id="dd69b-148">-Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="dd69b-148">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="dd69b-149">-도메인 구성</span><span class="sxs-lookup"><span data-stu-id="dd69b-149">- Configure domain</span></span> <br><span data-ttu-id="dd69b-150">-Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="dd69b-150">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="dd69b-151">-포털에서 설치 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="dd69b-151">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="dd69b-152">![공격 시뮬레이션](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="dd69b-152">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="dd69b-153">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="dd69b-153">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="dd69b-154">공격을 시뮬레이트하기 위해 다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-154">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="dd69b-155">-테스트 환경 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="dd69b-155">- Verify the test environment requirements</span></span> <br><span data-ttu-id="dd69b-156">-시뮬레이션을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-156">-  Run the simulation</span></span> <br><span data-ttu-id="dd69b-157">-문제 조사</span><span class="sxs-lookup"><span data-stu-id="dd69b-157">- Investigate an incident</span></span> <br><span data-ttu-id="dd69b-158">-인시던트를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-158">- resolve the incident</span></span> 
| <span data-ttu-id="dd69b-159">![맺음말 및 요약](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="dd69b-159">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="dd69b-160">맺음말 및 요약</span><span class="sxs-lookup"><span data-stu-id="dd69b-160">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="dd69b-161">프로세스의 끝에 도달 하면 다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd69b-161">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="dd69b-162">-최종 출력으로 이동</span><span class="sxs-lookup"><span data-stu-id="dd69b-162">- Go through your final output</span></span><br><span data-ttu-id="dd69b-163">-결과를 이해 관계자에 게 제공</span><span class="sxs-lookup"><span data-stu-id="dd69b-163">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="dd69b-164">-사용자 의견 제공</span><span class="sxs-lookup"><span data-stu-id="dd69b-164">- Provide feedback</span></span> <br><span data-ttu-id="dd69b-165">-다음 단계 수행</span><span class="sxs-lookup"><span data-stu-id="dd69b-165">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="dd69b-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dd69b-166">Next step</span></span>
|<span data-ttu-id="dd69b-167">![계획 단계](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="dd69b-167">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="dd69b-168">계획 단계</span><span class="sxs-lookup"><span data-stu-id="dd69b-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="dd69b-169">Microsoft Threat Protection 파일럿 프로젝트 계획</span><span class="sxs-lookup"><span data-stu-id="dd69b-169">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
