---
title: Microsoft 규정 준수 점수 (미리 보기) 계산
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 규정 준수 점수가 위험을 해결 하 고 준수 상태를 개선 하기 위해 수행한 조치에 따라 개인 설정 점수를 계산 하는 방법을 이해 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024678"
---
# <a name="compliance-score-preview-calculation"></a><span data-ttu-id="201be-103">규정 준수 점수 (미리 보기) 계산</span><span class="sxs-lookup"><span data-stu-id="201be-103">Compliance Score (preview) calculation</span></span>

> [!IMPORTANT]
> <span data-ttu-id="201be-104">준수 점수 및 준수 관리자의 권장 사항을 준수 보장으로 해석하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="201be-104">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="201be-105">규정 환경에 따라 고객 컨트롤의 효율성을 평가 하 고 유효성을 검사 하는 작업은 사용자의 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-105">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="201be-106">이러한 서비스는 현재 미리 보기로 사용 되며 [온라인 서비스 약관](https://go.microsoft.com/fwlink/?linkid=2108910)의 사용 약관에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="201be-106">These services are currently in preview and subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="201be-107">[보안 및 규정 준수에 대 한 자세한 내용은 Microsoft 365 라이선싱 지침을](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="201be-107">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="how-compliance-score-works"></a><span data-ttu-id="201be-108">준수 점수 작동 방식</span><span class="sxs-lookup"><span data-stu-id="201be-108">How Compliance Score works</span></span>

<span data-ttu-id="201be-109">규정 준수 점수 대시보드에는 컨트롤 내에서 향상 작업을 완료 하는 과정의 진행 상황을 측정 하는 점수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="201be-109">The Compliance Score dashboard displays a score that measures your progress in completing improvement actions within controls.</span></span> <span data-ttu-id="201be-110">각 작업은 발생할 수 있는 잠재적 위험에 따라 점수에 서로 다른 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="201be-110">Each action has a different impact on your score, depending on the potential risks involved.</span></span> <span data-ttu-id="201be-111">점수는 전반적인 준수 상태를 개선 하기 위해 집중할 작업을 우선적으로 적용 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-111">Your score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="201be-112">컨트롤에 대해 표시 되는 규정 준수 점수 값은 합격/불합격 기준에 따라 전체 점수 *에 적용 됩니다* .</span><span class="sxs-lookup"><span data-stu-id="201be-112">The displayed Compliance Score values for the control are applied *in their entirety* to your total score on a pass/fail basis.</span></span> <span data-ttu-id="201be-113">컨트롤이 구현 되 고 후속 평가 테스트를 통과 하거나 그렇지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="201be-113">Either the control is implemented and passes the subsequent assessment test, or it doesn't.</span></span> 

<span data-ttu-id="201be-114">컨트롤의 규정 준수 점수에는 다음과 같은 점수가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="201be-114">Points are added to your compliance score when the control has:</span></span>

- <span data-ttu-id="201be-115">**구현 상태** 는 **구현** 됨 또는 **대체 구현**으로 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-115">**Implementation Status** equals **Implemented** or **Alternative Implementation**, and</span></span>
- <span data-ttu-id="201be-116">**테스트 결과가** **통과**됩니다.</span><span class="sxs-lookup"><span data-stu-id="201be-116">**Test Result** equals **Passed**.</span></span>

<span data-ttu-id="201be-117">컨트롤 점수는 향상 작업을 수행 하 여 획득 한 점수를 더한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-117">A control score is the sum of points earned by taking improvement actions.</span></span> <span data-ttu-id="201be-118">계산 점수는 컨트롤 점수의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-118">The sum of your control scores is the assessment score.</span></span> <span data-ttu-id="201be-119">**평가 점수의 합은 전반적인 준수 점수입니다.**</span><span class="sxs-lookup"><span data-stu-id="201be-119">**The sum of your assessment scores is your overall compliance score.**</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="201be-120">Microsoft 365 데이터 보호 기준을 기반으로 한 초기 점수</span><span class="sxs-lookup"><span data-stu-id="201be-120">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="201be-121">준수 점수가 Microsoft 365 데이터 보호 기준을 기반으로 초기 점수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-121">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="201be-122">이 기준은 데이터 보호 및 일반 데이터 관리를 위한 주요 규정 및 표준을 포함 하는 컨트롤 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-122">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="201be-123">이 기준은 기본적으로 NIST CSF (표준 및 기술 Cybersecurity 프레임 워크) 및 ISO (국제 표준화 기구)를 비롯 하 여 FedRAMP (연방 위험 및 권한 부여 관리 프로그램) 및 GDPR (유럽 연합의 일반 데이터 보호 규정)의 요소를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="201be-123">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="201be-124">다른 평가를 구성 하기 전에 모든 조직에서 기본적으로 제공 하는 데이터 보호 기준 평가는 초기 점수를 계산 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="201be-124">The data protection baseline assessment (provided by default to all organizations) is used to calculate your initial score before you configure any other assessments.</span></span> <span data-ttu-id="201be-125">처음 방문할 때 준수 점수는 이미 Microsoft 365 솔루션의 신호를 수집 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-125">Upon your first visit, Compliance Score is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="201be-126">주요 데이터 보호 표준 및 규정을 기준으로 조직이 수행 하는 방법을 한눈에 확인 하 고 고려해 야 할 개선 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-126">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="201be-127">모든 조직에는 특정 요구 사항이 있기 때문에 규정 준수 점수를 통해 위험을 최대한 포괄적으로 최소화 하 고 관리 하는 데 도움이 되는 고유한 평가를 설정 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-127">Because every organization has specific needs, Compliance Score relies on you to set up and manage your own assessments to help minimize and mitigate risk as comprehensively as possible.</span></span>

## <a name="how-compliance-score-continuously-assesses-controls"></a><span data-ttu-id="201be-128">규정 준수 점수가 지속적으로 제어를 평가 하는 방법</span><span class="sxs-lookup"><span data-stu-id="201be-128">How Compliance Score continuously assesses controls</span></span>

<span data-ttu-id="201be-129">규정 준수 점수가 Microsoft 365 환경을 자동으로 검색 하 고 시스템 설정을 계속 검색 하며, 기술 제어 상태를 자동으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-129">Compliance Score automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical control status.</span></span> <span data-ttu-id="201be-130">보안 점수는 모니터링을 수행 하는 기본 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-130">Secure Score is the underlying engine that performs the monitoring.</span></span>

<span data-ttu-id="201be-131">제어 상태는 24 시간 마다 준수 점수 대시보드에 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="201be-131">Your control status is updated on your Compliance Score dashboard every 24 hours.</span></span> <span data-ttu-id="201be-132">사용자가 컨트롤을 구현 하는 권장 사항을 따르면 다음 날에 제어 상태를 업데이트 한 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-132">Once you follow a recommendation to implement a control, you'll see the control status updated the next day.</span></span>

<span data-ttu-id="201be-133">예를 들어 Azure AD 포털에서 MFA (multi-factor authentication)를 설정 하는 경우 준수 점수가 설정을 감지 하 고 제어 액세스 솔루션 세부 정보에 해당 사실을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-133">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Score detects the setting and reflects that in the control access solution details.</span></span> <span data-ttu-id="201be-134">반대로, MFA를 설정 하지 않은 경우에는 권장 되는 조치로 인 한 준수 점수 플래그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-134">Conversely, if you didn't turn on MFA, Compliance Score flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="201be-135">공개 미리 보기 중에는 일부 컨트롤에 대해서도 연속 평가를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-135">During public preview, continuous assessment is available to a portion of controls, but not all.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="201be-136">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="201be-136">Learn more</span></span>
<span data-ttu-id="201be-137">[보안 점수 및 작동 방식에 대해 읽어](../security/mtp/microsoft-secure-score-new.md)보세요.</span><span class="sxs-lookup"><span data-stu-id="201be-137">[Read about Secure Score and how it works](../security/mtp/microsoft-secure-score-new.md).</span></span>
  
## <a name="action-types-and-points"></a><span data-ttu-id="201be-138">작업 유형 및 점</span><span class="sxs-lookup"><span data-stu-id="201be-138">Action types and points</span></span>

<span data-ttu-id="201be-139">준수 점수에는 관리 하는 작업 및 Microsoft가 관리 하는 작업 이라는 두 가지 유형의 작업이 추적 됩니다.</span><span class="sxs-lookup"><span data-stu-id="201be-139">Compliance Score tracks two types of actions: actions you manage, and actions Microsoft manages.</span></span> <span data-ttu-id="201be-140">두 가지 작업 유형에 모두 완료 시 전체 점수를 계산 하는 점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-140">Both types of actions have points that count toward your overall score when completed:</span></span>

1. <span data-ttu-id="201be-141">**점수가** 조직에서 관리 하는 컨트롤을 기반으로 준수 점수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-141">**Your points** contribute to your compliance score based on controls managed by your organization.</span></span>
2. <span data-ttu-id="201be-142">**Microsoft 관리 지점은** 클라우드 서비스 공급자로 microsoft가 관리 하는 작업을 기반으로 준수 점수에 기여 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-142">**Microsoft managed points** contribute to your compliance score based on actions managed by Microsoft as a cloud service provider.</span></span>

<span data-ttu-id="201be-143">작업에는 필수 또는 임의 인지에 따라 점수 값이 할당 되 고, 사용자에 게 예방, 예방용 인지 또는 정정 인지 여부가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="201be-143">Actions are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span>

### <a name="mandatory-and-discretionary-actions"></a><span data-ttu-id="201be-144">필수 및 임의 작업</span><span class="sxs-lookup"><span data-stu-id="201be-144">Mandatory and discretionary actions</span></span>

 - <span data-ttu-id="201be-145">**필수 작업** 은 고의적으로 또는 실수로 건너뛸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-145">**Mandatory actions** can't be bypassed, either intentionally or accidentally.</span></span> <span data-ttu-id="201be-146">예를 들어 암호 길이, 복잡성 및 만료에 대 한 요구 사항을 설정 하는 중앙 집중식으로 관리 되는 암호 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-146">An example is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="201be-147">사용자는 이러한 요구 사항을 준수 하 여 시스템에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-147">Users must follow these requirements to access the system.</span></span>
  
 - <span data-ttu-id="201be-148">**임의 작업** 은 사용자에 게 정책을 이해 하 고 그에 따라 조치를 취할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-148">**Discretionary actions** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="201be-149">예를 들어 사용자가 자신의 컴퓨터에서 작업을 수행 하는 데 사용 하는 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-149">For example, a policy requiring users to lock their computer when they leave it is a discretionary action because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-actions"></a><span data-ttu-id="201be-150">예방적, 예방용 인지 및 정정 작업</span><span class="sxs-lookup"><span data-stu-id="201be-150">Preventative, detective, and corrective actions</span></span>
  
 - <span data-ttu-id="201be-151">**예방적 작업** 은 특정 위험을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-151">**Preventative actions** address specific risks.</span></span> <span data-ttu-id="201be-152">예를 들어 암호화를 사용 하 여 rest에서 정보를 보호 하는 것은 공격 및 침해에 대 한 예방 조치입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-152">For example, protecting information at rest using encryption is a preventative action against attacks and breaches.</span></span> <span data-ttu-id="201be-153">의무의 분리는 관심 충돌을 관리 하 고 사기를 방지 하기 위한 예방 조치입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-153">Separation of duties is a preventative action to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="201be-154">**예방용 인지 작업** 은 시스템을 적극적으로 모니터링 하 여 위험을 나타내거나 침입 또는 침해를 감지 하는 데 사용할 수 있는 불규칙 한 조건이 나 행동을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-154">**Detective actions** actively monitor systems to identify irregular conditions or behaviors that represent risk, or that can be used to detect intrusions or breaches.</span></span> <span data-ttu-id="201be-155">예를 들면 시스템 액세스 감사 및 권한 있는 관리 작업을 예로 들 있습니다.</span><span class="sxs-lookup"><span data-stu-id="201be-155">Examples include system access auditing and privileged administrative actions.</span></span> <span data-ttu-id="201be-156">규정 준수 감사는 프로세스 문제를 찾는 데 사용 되는 예방용 인지 작업 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-156">Regulatory compliance audits are a type of detective action used to find process issues.</span></span>
  
- <span data-ttu-id="201be-157">**정정 작업** 에서는 보안 인시던트가 부정적으로 영향을 최소화 하 고, 정정 작업을 수행 하 여 즉각적인 영향을 줄이고, 가능한 경우 피해를 반대로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="201be-157">**Corrective actions** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="201be-158">개인 정보 보호 인시던트 응답은 손상을 제한 하 고 위반 후 시스템을 작동 상태로 복원 하기 위한 정정 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="201be-158">Privacy incident response is a corrective action to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="201be-159">각 작업은 표시 되는 위험에 따라 규정 준수 점수에 할당 된 값을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="201be-159">Each action has an assigned value in Compliance Score based on the risk it represents:</span></span>

|<span data-ttu-id="201be-160">**유형**</span><span class="sxs-lookup"><span data-stu-id="201be-160">**Type**</span></span>|<span data-ttu-id="201be-161">**할당 된 점수**</span><span class="sxs-lookup"><span data-stu-id="201be-161">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="201be-162">예방적 필수</span><span class="sxs-lookup"><span data-stu-id="201be-162">Preventative mandatory</span></span> | <span data-ttu-id="201be-163">kb(56kbps</span><span class="sxs-lookup"><span data-stu-id="201be-163">27</span></span> |
| <span data-ttu-id="201be-164">예방적 임의</span><span class="sxs-lookup"><span data-stu-id="201be-164">Preventative discretionary</span></span> | <span data-ttu-id="201be-165">9 </span><span class="sxs-lookup"><span data-stu-id="201be-165">9</span></span> |
| <span data-ttu-id="201be-166">예방용 인지 필수</span><span class="sxs-lookup"><span data-stu-id="201be-166">Detective mandatory</span></span> | <span data-ttu-id="201be-167">3 </span><span class="sxs-lookup"><span data-stu-id="201be-167">3</span></span> |
| <span data-ttu-id="201be-168">예방용 인지 임의</span><span class="sxs-lookup"><span data-stu-id="201be-168">Detective discretionary</span></span> | <span data-ttu-id="201be-169">1 </span><span class="sxs-lookup"><span data-stu-id="201be-169">1</span></span> |
| <span data-ttu-id="201be-170">정정 필수</span><span class="sxs-lookup"><span data-stu-id="201be-170">Corrective mandatory</span></span> | <span data-ttu-id="201be-171">3 </span><span class="sxs-lookup"><span data-stu-id="201be-171">3</span></span> |
| <span data-ttu-id="201be-172">정정 임의</span><span class="sxs-lookup"><span data-stu-id="201be-172">Corrective discretionary</span></span> | <span data-ttu-id="201be-173">1 </span><span class="sxs-lookup"><span data-stu-id="201be-173">1</span></span> |
  
<span data-ttu-id="201be-174">![규정 준수 점수 컨트롤 포인트 값](../media/compliance-score-controls-scoring.png "규정 준수 점수 컨트롤 포인트 값")</span><span class="sxs-lookup"><span data-stu-id="201be-174">![Compliance Score controls point values](../media/compliance-score-controls-scoring.png "Compliance Score controls point values")</span></span>