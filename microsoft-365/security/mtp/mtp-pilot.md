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
ms.openlocfilehash: 4ec46891248c09f580b19d888573544ad2b4930f
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446870"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="5bed7-104">파일럿 Microsoft Threat Protection 프로젝트 실행</span><span class="sxs-lookup"><span data-stu-id="5bed7-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5bed7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5bed7-105">**Applies to:**</span></span>
- <span data-ttu-id="5bed7-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="5bed7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5bed7-107">MTP (Microsoft Threat Protection)의 이점과 채택을 효과적으로 확인 하기 위해 파일럿 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="5bed7-108">프로덕션 환경에서 Microsoft Threat Protection을 사용 하도록 설정 하 고 사용 사례를 시작 하기 전에 파일럿 프로젝트에 대해 수행할 작업을 결정 하 고 성공 기준을 설정 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-108">Before enabling Microsoft Threat Protection in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="5bed7-109">이 파일럿 playbook를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="5bed7-109">How to use this pilot playbook</span></span>

<span data-ttu-id="5bed7-110">이 가이드에서는 Microsoft Threat Protection에 대 한 개요와 파일럿 프로젝트를 설정 하는 방법에 대 한 단계별 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

![Microsoft Threat Protection 파일럿 실행 단계](../../media/pilotphases.png)

<span data-ttu-id="5bed7-112">다음의 시간 표시 막대는 환경에 적절 한 리소스가 있는 경우에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="5bed7-113">일부 검색 및 워크플로에는 다른 일부 사용자 보다 더 많은 학습 시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-113">Some detections and workflows might need more learning time than the others.</span></span>

![Microsoft Threat Protection 파일럿 실행을 위한 샘플 시간 표시줄](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="5bed7-115">최적의 결과를 위해 파일럿 지침을 최대한 면밀 하 게 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="5bed7-116">파일럿 playbook 단계</span><span class="sxs-lookup"><span data-stu-id="5bed7-116">Pilot playbook phases</span></span> 

<span data-ttu-id="5bed7-117">Microsoft Threat Protection 파일럿을 실행 하는 데는 다음과 같은 네 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="5bed7-118">단계</span><span class="sxs-lookup"><span data-stu-id="5bed7-118">Phase</span></span> | <span data-ttu-id="5bed7-119">설명</span><span class="sxs-lookup"><span data-stu-id="5bed7-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="5bed7-120">![계획](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="5bed7-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="5bed7-121">계획</span><span class="sxs-lookup"><span data-stu-id="5bed7-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="5bed7-122">Microsoft Threat Protection 파일럿 프로젝트를 실행 하기 전에 고려해 야 할 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="5bed7-123">-범위</span><span class="sxs-lookup"><span data-stu-id="5bed7-123">- Scope</span></span> <br> <span data-ttu-id="5bed7-124">-사용 사례</span><span class="sxs-lookup"><span data-stu-id="5bed7-124">- Use cases</span></span> <br><span data-ttu-id="5bed7-125">- 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bed7-125">- Requirements</span></span> <br><span data-ttu-id="5bed7-126">-테스트 계획</span><span class="sxs-lookup"><span data-stu-id="5bed7-126">- Test plan</span></span> <br> <span data-ttu-id="5bed7-127">-성공 조건</span><span class="sxs-lookup"><span data-stu-id="5bed7-127">- Success criteria</span></span> <br> <span data-ttu-id="5bed7-128">-성과 기록표</span><span class="sxs-lookup"><span data-stu-id="5bed7-128">- Scorecard</span></span> 
| <span data-ttu-id="5bed7-129">![미리](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="5bed7-129">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="5bed7-130">미리</span><span class="sxs-lookup"><span data-stu-id="5bed7-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="5bed7-131">Microsoft 365 보안 센터에 액세스 하 여 Microsoft Threat Protection 파일럿 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-131">Access Microsoft 365 Security Center to set up your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="5bed7-132">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-132">You'll be guided to:</span></span><br><br><span data-ttu-id="5bed7-133">-관련자 식별 및 파일럿에 대 한 승인 찾기</span><span class="sxs-lookup"><span data-stu-id="5bed7-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="5bed7-134">-환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="5bed7-134">- Environment considerations</span></span> <br><span data-ttu-id="5bed7-135">-액세스</span><span class="sxs-lookup"><span data-stu-id="5bed7-135">- Access</span></span> <br><span data-ttu-id="5bed7-136">-Azure Active Directory 설치</span><span class="sxs-lookup"><span data-stu-id="5bed7-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="5bed7-137">-구성 순서</span><span class="sxs-lookup"><span data-stu-id="5bed7-137">- Configuration order</span></span> <br> <span data-ttu-id="5bed7-138">-Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="5bed7-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="5bed7-139">-도메인 구성</span><span class="sxs-lookup"><span data-stu-id="5bed7-139">- Configure domain</span></span> <br><span data-ttu-id="5bed7-140">-Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="5bed7-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="5bed7-141">-포털에서 설치 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="5bed7-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="5bed7-142">![공격 시뮬레이션](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="5bed7-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="5bed7-143">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="5bed7-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="5bed7-144">공격을 시뮬레이트하기 위해 다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-144">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="5bed7-145">-테스트 환경 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="5bed7-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="5bed7-146">-시뮬레이션을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-146">-  Run the simulation</span></span> <br><span data-ttu-id="5bed7-147">-문제 조사</span><span class="sxs-lookup"><span data-stu-id="5bed7-147">- Investigate an incident</span></span> <br><span data-ttu-id="5bed7-148">-인시던트를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-148">- resolve the incident</span></span> 
| <span data-ttu-id="5bed7-149">![맺음말 및 요약](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="5bed7-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="5bed7-150">맺음말 및 요약</span><span class="sxs-lookup"><span data-stu-id="5bed7-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="5bed7-151">프로세스의 끝에 도달 하면 다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bed7-151">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="5bed7-152">-최종 출력으로 이동</span><span class="sxs-lookup"><span data-stu-id="5bed7-152">- Go through your final output</span></span><br><span data-ttu-id="5bed7-153">-결과를 이해 관계자에 게 제공</span><span class="sxs-lookup"><span data-stu-id="5bed7-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="5bed7-154">-사용자 의견 제공</span><span class="sxs-lookup"><span data-stu-id="5bed7-154">- Provide feedback</span></span> <br><span data-ttu-id="5bed7-155">-다음 단계 수행</span><span class="sxs-lookup"><span data-stu-id="5bed7-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="5bed7-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5bed7-156">Next step</span></span>
|<span data-ttu-id="5bed7-157">![계획 단계](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="5bed7-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="5bed7-158">계획 단계</span><span class="sxs-lookup"><span data-stu-id="5bed7-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="5bed7-159">Microsoft Threat Protection 파일럿 프로젝트 계획</span><span class="sxs-lookup"><span data-stu-id="5bed7-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
