---
title: 파일럿 Microsoft Threat Protection 프로젝트 계획
description: 예상 성과를 관리 하 고 성공적인 결과를 확인 하기 위해 관련자를 사용 하 여 파일럿 Microsoft Threat Protection 프로젝트를 계획 합니다.
keywords: Microsoft 위협 보호 파일럿, 파일럿 Microsoft 위협 보호 프로젝트 계획, 마이크로소프트의 microsoft threat Protection, Microsoft Threat Protection 파일럿 프로젝트, 사이버 보안, advanced persistent 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 사건, 자동화 된 조사 및 개선, 고급 구하기
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 7d1870d1b8972009bed657f476810ca011dc2621
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367980"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="dec1d-104">파일럿 Microsoft Threat Protection 프로젝트 계획</span><span class="sxs-lookup"><span data-stu-id="dec1d-104">Planning your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dec1d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="dec1d-105">**Applies to:**</span></span>
- <span data-ttu-id="dec1d-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="dec1d-106">Microsoft Threat Protection</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="파일럿 Microsoft Threat Protection 프로젝트 계획" />
      <br/><span data-ttu-id="dec1d-108">계획</a></span><span class="sxs-lookup"><span data-stu-id="dec1d-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 준비" />
      <br/><span data-ttu-id="dec1d-110">준비</a></span><span class="sxs-lookup"><span data-stu-id="dec1d-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Microsoft Threat Protection 공격 시뮬레이션 실행" />
     <br/><span data-ttu-id="dec1d-112">공격 시뮬레이션</a></span><span class="sxs-lookup"><span data-stu-id="dec1d-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Microsoft Threat Protection 파일럿을 닫고 요약 합니다." />
     <br/><span data-ttu-id="dec1d-114">닫기 및 요약</a></span><span class="sxs-lookup"><span data-stu-id="dec1d-114">Close and summarize</a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="dec1d-115">현재 계획 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="dec1d-116">파일럿 프로젝트가 성공적인 지 확인 하려면 처음에 관련자 로부터 철저 하 게 계획 하 고 승인을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="dec1d-117">계획 요소에는 식별 범위, 사용 사례, 요구 사항 및 성공 기준이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="dec1d-118">이 가이드에서는 파일럿 프로젝트를 계획 하는 방법을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="dec1d-119">최적의 결과를 위해 파일럿 지침을 최대한 면밀 하 게 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="dec1d-120">Scope</span><span class="sxs-lookup"><span data-stu-id="dec1d-120">Scope</span></span>

<span data-ttu-id="dec1d-121">시험 운용 범위에 따라 사용자 환경 및 적합 한 테스트 방법에 따른 테스트 범위가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="dec1d-122">다음은 고려해 야 할 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="dec1d-123">끝점, 서버, 도메인 컨트롤러를 포함 하는 개발 또는 테스트 환경</span><span class="sxs-lookup"><span data-stu-id="dec1d-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="dec1d-124">Microsoft 365, Azure, Active Directory 서비스, 끝점 및 서버가 포함 된 프로덕션 환경</span><span class="sxs-lookup"><span data-stu-id="dec1d-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="dec1d-125">아직 전체 라이선스가 없는 경우에는 평가판 라이선스를 통해 [Microsoft 위협 보호를 평가](https://aka.ms/mtp-trial-lab) 하 고 파일럿 프로젝트를 계획, 준비, 설정 및 구성 하 고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="dec1d-126">관련자는 시작부터 끝까지 쉽게 프로세스를 진행 하는 데 큰 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="dec1d-127">평가할 운영 체제의 유형도 조직 makeup을 기반으로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="dec1d-128">여기에는 [Mac 끝점](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux 서버](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 끝점](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="dec1d-129">사용 사례</span><span class="sxs-lookup"><span data-stu-id="dec1d-129">Use cases</span></span>

<span data-ttu-id="dec1d-130">사용 사례는 테스트 중인 도구를 의도 한 사용자가 소비 하는 방식에 대 한 설명을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="dec1d-131">이러한 요소는 SOC 분석가와 같은 특정 가상 사용자의 관점에서 사용자 스토리로 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="dec1d-132">예제:</span><span class="sxs-lookup"><span data-stu-id="dec1d-132">For example:</span></span>
- <span data-ttu-id="dec1d-133">SOC 분석가는 내 네트워크의 장치, 사용자 및 사서함에서 알림 및 이벤트를 확인, 상관 관계, 평가 및 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="dec1d-134">[인시던트 관리]</span><span class="sxs-lookup"><span data-stu-id="dec1d-134">[Incident management]</span></span>
- <span data-ttu-id="dec1d-135">SOC 분석가는 내 네트워크의 악의적인 이벤트를 자동으로 조사 하 고 대응 하기 위해 도구와 프로세스를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="dec1d-136">[자동 IR]</span><span class="sxs-lookup"><span data-stu-id="dec1d-136">[Auto IR]</span></span>
- <span data-ttu-id="dec1d-137">SOC 분석가는 필자의 환경에서 알려진 문제 및 잠재적인 위협과 의심 스러운 활동을 찾기 위해 환경의 데이터를 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="dec1d-138">[고급 구하기]</span><span class="sxs-lookup"><span data-stu-id="dec1d-138">[Advanced Hunting]</span></span>

<span data-ttu-id="dec1d-139">이러한 사용 사례는 정의 된 범위의 매개 변수 내에서 만들어져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="dec1d-140">예를 들어 테스트 범위에 Microsoft Cloud App Security와 같은 도구 평가가 포함 되어 있지 않은 경우에는이를 데이터 원본으로 사용 하는 경우에는 해당 사례를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="dec1d-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dec1d-141">Requirements</span></span>

<span data-ttu-id="dec1d-142">사용 사례 목록에서 요구 사항 만들기를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="dec1d-143">요구 사항에는 도구에서 사용 사례를 충족 하기 위해 수행 해야 하는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="dec1d-144">이러한 요구 사항은 구성 및 유지 관리, 통합에 대 한 지원, 그리고 찾기 기능, 사용자 지정 알림 작성 기능과 같은 기능별 요구 사항 등의 범주로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="dec1d-145">테스트 계획</span><span class="sxs-lookup"><span data-stu-id="dec1d-145">Test plan</span></span>

<span data-ttu-id="dec1d-146">요구 사항에 따라 다양 한 테스트 방법이 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="dec1d-147">예를 들어 자동화 된 수정의 efficacy를 평가 해야 하는 경우 테스트 계획에는 Microsoft Threat Protection 내에서 자동화 된 재구성 작업을 트리거하는 동작을 생성 하기 위한 단계가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft Threat Protection.</span></span> <span data-ttu-id="dec1d-148">요구 사항으로 인해 특정 동작이 나 공격을 검색 해야 하는 경우 테스트에 더 많은 단계가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="dec1d-149">요구 사항을 정확히 테스트할 수 있도록 계획을 수립 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="dec1d-150">성공 기준</span><span class="sxs-lookup"><span data-stu-id="dec1d-150">Success criteria</span></span>

<span data-ttu-id="dec1d-151">성공 기준은 궁극적으로 테스트 대상에 대 한 기준으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="dec1d-152">Microsoft Threat Protection (또는 해당 문제에 대 한 다른 기술)을 다른 도구나 자체에 대해 테스트할 지 여부에 관계 없이 도구에서 제공 하는 값을 결정 하려면 몇 가지 수량화 된 기준이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-152">Whether you are testing Microsoft Threat Protection (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="dec1d-153">범위, 요구 사항 및 테스트 계획에 따라 성공 기준은 테스트 점수를 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="dec1d-154">이는 합격 또는 불합격이 더 적거나 필요에 따라 가중치 점수를 많이 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="dec1d-155">예를 들어, 확인이 성공 하려면 도구는 특정 중요 한 영역에서 80% 이상 점수를 두어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="dec1d-156">표</span><span class="sxs-lookup"><span data-stu-id="dec1d-156">Scorecard</span></span>

<span data-ttu-id="dec1d-157">계획의 모든 요소를 함께 가져오는 한 가지 방법으로 성과 기록표를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="dec1d-158">아래의 샘플 성과 기록표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dec1d-158">See a sample scorecard below:</span></span>

|<span data-ttu-id="dec1d-159">**사용 사례**</span><span class="sxs-lookup"><span data-stu-id="dec1d-159">**Use case**</span></span>|<span data-ttu-id="dec1d-160">**요구 사항**</span><span class="sxs-lookup"><span data-stu-id="dec1d-160">**Requirements**</span></span>|<span data-ttu-id="dec1d-161">**구성 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="dec1d-161">**Configuration requirements**</span></span>|<span data-ttu-id="dec1d-162">**테스트 계획**</span><span class="sxs-lookup"><span data-stu-id="dec1d-162">**Test plan**</span></span>|<span data-ttu-id="dec1d-163">**예상 결과**</span><span class="sxs-lookup"><span data-stu-id="dec1d-163">**Expected outcome**</span></span>|<span data-ttu-id="dec1d-164">**테스트 상태**</span><span class="sxs-lookup"><span data-stu-id="dec1d-164">**Test status**</span></span>|<span data-ttu-id="dec1d-165">**점수**</span><span class="sxs-lookup"><span data-stu-id="dec1d-165">**Score**</span></span>|<span data-ttu-id="dec1d-166">**참고**</span><span class="sxs-lookup"><span data-stu-id="dec1d-166">**Notes**</span></span>|
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="dec1d-167">사건 관리</span><span class="sxs-lookup"><span data-stu-id="dec1d-167">Incident management</span></span>|<span data-ttu-id="dec1d-168">-Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dec1d-168">-  Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="dec1d-169">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="dec1d-169">- Azure ATP</span></span> </br></br><span data-ttu-id="dec1d-170">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="dec1d-170">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="dec1d-171">-Microsoft Cloud App Security (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="dec1d-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="dec1d-172">자세한 내용은 준비, 설정 및 구성을 위한 [필수 구성 요소](https://aka.ms/mtp-trial-lab) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dec1d-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="dec1d-173">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="dec1d-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="dec1d-174">문제 조사</span><span class="sxs-lookup"><span data-stu-id="dec1d-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="dec1d-175">Investigators는 사고의 범위와 영향을 이해 하 고 인시던트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1d-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="dec1d-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="dec1d-176">AutoIR</span></span>|<span data-ttu-id="dec1d-177">-Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dec1d-177">-   Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="dec1d-178">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="dec1d-178">- Azure ATP</span></span> </br></br><span data-ttu-id="dec1d-179">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="dec1d-179">- Microsoft Defender ATP</span></span> |<span data-ttu-id="dec1d-180">자세한 내용은 준비, 설정 및 구성을 위한 [필수 구성 요소](https://aka.ms/mtp-trial-lab) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dec1d-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="dec1d-181">AutoIR 사용</span><span class="sxs-lookup"><span data-stu-id="dec1d-181">Enable AutoIR</span></span>  |[<span data-ttu-id="dec1d-182">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="dec1d-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="dec1d-183">자동화 된 조사</span><span class="sxs-lookup"><span data-stu-id="dec1d-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="dec1d-184">Microsoft Threat Protection에서 경고 및 인시던트가 자동으로 재구성 됨</span><span class="sxs-lookup"><span data-stu-id="dec1d-184">Alerts and incidents are automatically remediated by Microsoft Threat Protection</span></span>||||
|<span data-ttu-id="dec1d-185">고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="dec1d-185">Advanced hunting</span></span>|<span data-ttu-id="dec1d-186">-Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dec1d-186">- Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="dec1d-187">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="dec1d-187">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="dec1d-188">-Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="dec1d-188">- Office 365 ATP</span></span>   |<span data-ttu-id="dec1d-189">자세한 내용은 준비, 설정 및 구성을 위한 [필수 구성 요소](https://aka.ms/mtp-trial-lab) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dec1d-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="dec1d-190">고급 구하기 시나리오</span><span class="sxs-lookup"><span data-stu-id="dec1d-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="dec1d-191">Investigators에서는 고급 검색을 통해 데이터를 찾고, 영향을 받는 엔터티에 대 한 피벗을 하며, 사용자 지정 감지를 만들면</span><span class="sxs-lookup"><span data-stu-id="dec1d-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="dec1d-192">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dec1d-192">Next step</span></span>
|<span data-ttu-id="dec1d-193">![준비 단계](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="dec1d-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="dec1d-194">준비 단계</span><span class="sxs-lookup"><span data-stu-id="dec1d-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="dec1d-195">Microsoft Threat Protection 파일럿 환경 준비</span><span class="sxs-lookup"><span data-stu-id="dec1d-195">Prepare your Microsoft Threat Protection pilot environment</span></span>
|:-------|:-----|
