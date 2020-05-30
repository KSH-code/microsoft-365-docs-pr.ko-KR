---
title: 규정 준수 점수 계산
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
ms.openlocfilehash: e1a13cee8086e158f3869a00384166366c0a63dc
ms.sourcegitcommit: 436841236dc41390a3be9f8936d19d3d017fa35c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/30/2020
ms.locfileid: "44429193"
---
# <a name="microsoft-compliance-score-preview-calculation"></a><span data-ttu-id="a1ecd-103">Microsoft 규정 준수 점수 (미리 보기) 계산</span><span class="sxs-lookup"><span data-stu-id="a1ecd-103">Microsoft Compliance Score (preview) calculation</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1ecd-104">준수 점수 및 준수 관리자의 권장 사항을 준수 보장으로 해석하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-104">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="a1ecd-105">규정 환경에 따라 고객 컨트롤의 효율성을 평가 하 고 유효성을 검사 하는 작업은 사용자의 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-105">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="a1ecd-106">이러한 서비스는 현재 미리 보기로 사용 되며 [온라인 서비스 약관](https://go.microsoft.com/fwlink/?linkid=2108910)의 사용 약관에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-106">These services are currently in preview and subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="a1ecd-107">[보안 및 규정 준수에 대 한 자세한 내용은 Microsoft 365 라이선싱 지침을](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-107">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="overview"></a><span data-ttu-id="a1ecd-108">개요</span><span class="sxs-lookup"><span data-stu-id="a1ecd-108">Overview</span></span>

<span data-ttu-id="a1ecd-109">규정 준수 점수 대시보드에는 컨트롤 내에서 향상 작업을 완료 하는 과정의 진행 상황을 측정 하는 점수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-109">The Compliance Score dashboard displays a score that measures your progress in completing improvement actions within controls.</span></span> <span data-ttu-id="a1ecd-110">작업을 완료 하면 점수가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-110">Your points accrue when you complete actions.</span></span>

<span data-ttu-id="a1ecd-111">점수는 Microsoft가 관리 하는 작업 및 고객 관리 작업의 완료를 기반으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-111">Your score is calculated based on the completion of Microsoft-managed actions and customer-managed actions.</span></span> <span data-ttu-id="a1ecd-112">각 작업은 발생할 수 있는 잠재적 위험에 따라 점수에 서로 다른 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-112">Each action has a different impact on your score, depending on the potential risks involved.</span></span> <span data-ttu-id="a1ecd-113">점수는 전반적인 준수 상태를 개선 하기 위해 집중할 작업을 우선적으로 적용 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-113">Your score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="a1ecd-114">컨트롤에 대해 표시 되는 규정 준수 점수 값은 합격/불합격 기준에 따라 전체 점수 *에 적용 됩니다* .</span><span class="sxs-lookup"><span data-stu-id="a1ecd-114">The displayed Compliance Score values for the control are applied *in their entirety* to your total score on a pass/fail basis.</span></span> <span data-ttu-id="a1ecd-115">컨트롤이 구현 되 고 후속 평가 테스트를 통과 하거나 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-115">Either the control is implemented and passes the subsequent assessment test, or it does not.</span></span> <span data-ttu-id="a1ecd-116">지정 된 점은 컨트롤의 준수 점수에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-116">Assigned points are added to Compliance Score when the control has:</span></span>

- <span data-ttu-id="a1ecd-117">**구현 상태** 는 **구현** 됨 또는 **대체 구현과** 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-117">**Implementation Status** equals **Implemented** or **Alternative Implementation** and,</span></span>
- <span data-ttu-id="a1ecd-118">**테스트 결과가** **통과**됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-118">**Test Result** equals **Passed**.</span></span>

<span data-ttu-id="a1ecd-119">향상 작업을 통해 획득 한 점수 합계가 컨트롤 점수에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-119">The sum of points earned by taking improvement actions is the control score.</span></span> <span data-ttu-id="a1ecd-120">계산 점수는 컨트롤 점수의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-120">The sum of your control scores is the assessment score.</span></span> <span data-ttu-id="a1ecd-121">평가 점수의 합은 전반적인 준수 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-121">The sum of your assessment scores is your overall compliance score.</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="a1ecd-122">Microsoft 365 데이터 보호 기준을 기반으로 한 초기 점수</span><span class="sxs-lookup"><span data-stu-id="a1ecd-122">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="a1ecd-123">규정 준수 점수는 데이터 보호 및 일반 데이터 거 버 넌 스에 대 한 주요 규정 및 표준을 포함 하는 컨트롤 집합인 Microsoft 365 데이터 보호 기준을 기반으로 초기 점수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-123">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline, which is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="a1ecd-124">이 기준은 기본적으로 NIST CSF (표준 및 기술 Cybersecurity 프레임 워크) 및 ISO (국제 표준화 기구)를 비롯 하 여 FedRAMP (연방 위험 및 권한 부여 관리 프로그램) 및 GDPR (유럽 연합의 일반 데이터 보호 규정)의 요소를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-124">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

## <a name="how-compliance-score-continuously-assesses-controls"></a><span data-ttu-id="a1ecd-125">규정 준수 점수가 지속적으로 제어를 평가 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a1ecd-125">How Compliance Score continuously assesses controls</span></span>

<span data-ttu-id="a1ecd-126">규정 준수 점수가 Microsoft 365 환경을 자동으로 검색 하 고 시스템 설정을 계속 검색 하며, 기술 제어 상태를 자동으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-126">Compliance Score automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical control status.</span></span> <span data-ttu-id="a1ecd-127">보안 점수는 모니터링을 수행 하는 기본 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-127">Secure Score is the underlying engine that performs the monitoring.</span></span> <span data-ttu-id="a1ecd-128">[보안 점수 및 작동 방식에 대해 자세히 알아보세요](../security/mtp/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="a1ecd-128">[Learn more about Secure Score and how it works](../security/mtp/microsoft-secure-score.md).</span></span>

<span data-ttu-id="a1ecd-129">제어 상태는 24 시간 마다 준수 점수 대시보드에 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-129">Your control status is updated on your Compliance Score dashboard every 24 hours.</span></span> <span data-ttu-id="a1ecd-130">사용자가 컨트롤을 구현 하는 권장 사항을 따르면 다음 날에 제어 상태를 업데이트 한 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-130">Once you follow a recommendation to implement a control, you'll see the control status updated the next day.</span></span>

<span data-ttu-id="a1ecd-131">예를 들어 Azure AD 포털에서 MFA (multi-factor authentication)를 설정 하는 경우 준수 점수가 설정을 감지 하 고 제어 액세스 솔루션 세부 정보에 해당 사실을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-131">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Score detects the setting and reflects that in the control access solution details.</span></span> <span data-ttu-id="a1ecd-132">반대로, MFA를 설정 하지 않은 경우에는 권장 되는 조치로 인 한 준수 점수 플래그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-132">Conversely, if you didn't turn on MFA, Compliance Score flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="a1ecd-133">공개 미리 보기 중에는 일부 컨트롤에 대해서도 연속 평가를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-133">During public preview, continuous assessment is available to a portion of controls, but not all.</span></span>
  
## <a name="control-types-and-points"></a><span data-ttu-id="a1ecd-134">컨트롤 형식 및 요소</span><span class="sxs-lookup"><span data-stu-id="a1ecd-134">Control types and points</span></span>

<span data-ttu-id="a1ecd-135">규정 준수 점수에는 다음과 같은 두 가지 유형의 컨트롤이 추적 되며, 이러한 컨트롤은 각각 전체 점수에 기여 하는 점수를 갖고 관리 및 고객 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-135">Compliance Score tracks two types of controls—Microsoft-managed and customer-managed—each of which have points that contribute to your overall score:</span></span>

1. <span data-ttu-id="a1ecd-136">**고객 관리 지점은** 조직에서 관리 하는 컨트롤을 기반으로 하는 준수 점수에 기여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-136">**Customer-managed points** contribute to your compliance score based on controls managed by your organization.</span></span>
2. <span data-ttu-id="a1ecd-137">**Microsoft가 관리** 하는 지점은 클라우드 서비스 공급자로 microsoft가 관리 하는 컨트롤을 기반으로 하는 준수 점수에 기여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-137">**Microsoft-managed points** contribute to your compliance score based on controls managed by Microsoft as a cloud service provider.</span></span>

<span data-ttu-id="a1ecd-138">컨트롤이 필수 인지 아니면 임의 인지에 따라 점수 값이 할당 되 고 사용자가 예방적이 든 상관 없이 예방용 인지 인지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-138">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span>

### <a name="mandatory-and-discretionary-controls"></a><span data-ttu-id="a1ecd-139">필수 및 임의 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a1ecd-139">Mandatory and discretionary controls</span></span>

 - <span data-ttu-id="a1ecd-140">**필수 컨트롤** 은 고의적으로 또는 실수로 건너뛸 수 없는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-140">**Mandatory controls** are actions that can't be bypassed, either intentionally or accidentally.</span></span> <span data-ttu-id="a1ecd-141">예를 들어 암호 길이, 복잡성 및 만료에 대 한 요구 사항을 설정 하는 중앙 집중식으로 관리 되는 암호 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-141">An example is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="a1ecd-142">사용자는 이러한 요구 사항을 준수 하 여 시스템에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-142">Users must follow these requirements to access the system.</span></span>
  
 - <span data-ttu-id="a1ecd-143">사용자는 **임의 컨트롤** 을 사용 하 여 정책을 이해 하 고 그에 따라 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-143">**Discretionary controls** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="a1ecd-144">예를 들어 사용자가 자신의 컴퓨터를 사용 하는 경우 사용자에 게 의존 하므로 임의의 컨트롤을 잠그려고 하는 정책이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-144">For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-controls"></a><span data-ttu-id="a1ecd-145">예방적, 예방용 인지 및 정정 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a1ecd-145">Preventative, detective, and corrective controls</span></span>
  
 - <span data-ttu-id="a1ecd-146">**예방적 컨트롤** 은 특정 위험을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-146">**Preventative controls** address specific risks.</span></span> <span data-ttu-id="a1ecd-147">예를 들어 암호화를 사용 하 여 rest에서 정보를 보호 하는 것은 공격 및 침해에 대 한 예방적 통제입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-147">For example, protecting information at rest using encryption is a preventative control against attacks and breaches.</span></span> <span data-ttu-id="a1ecd-148">의무를 구분 하 고 사기를 방지 하는 예방 통제를 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-148">Separation of duties is a preventative control to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="a1ecd-149">**예방용 인지 컨트롤** 은 시스템을 적극적으로 모니터링 하 여 위험을 나타내거나 침입 또는 침해를 감지 하는 데 사용할 수 있는 불규칙 한 조건이 나 행동을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-149">**Detective controls** actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or breaches.</span></span> <span data-ttu-id="a1ecd-150">시스템 액세스 감사 및 권한 있는 관리 작업 감사는 예방용 인지 모니터링 컨트롤의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-150">System access auditing and privileged administrative actions auditing are types of detective monitoring controls.</span></span> <span data-ttu-id="a1ecd-151">규정 준수 감사는 프로세스 문제를 찾는 데 사용 되는 예방용 인지 제어 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-151">Regulatory compliance audits are a type of detective control used to find process issues.</span></span>
  
- <span data-ttu-id="a1ecd-152">**수정 컨트롤** 은 보안 사고가 최소화 된 상태로 유지 하 고, 정정 작업을 수행 하 여 즉각적인 영향을 줄이고, 가능한 경우 피해를 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-152">**Corrective controls** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="a1ecd-153">개인 정보 보호 인시던트 응답은 손상을 제한 하 고 위반 후 시스템을 작동 상태로 복원 하는 정정 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-153">Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="a1ecd-154">각 컨트롤은 표시 되는 위험에 따라 규정 준수 점수에 할당 된 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ecd-154">Each control has an assigned value in Compliance Score based on the risk it represents:</span></span>

|<span data-ttu-id="a1ecd-155">**유형**</span><span class="sxs-lookup"><span data-stu-id="a1ecd-155">**Type**</span></span>|<span data-ttu-id="a1ecd-156">**할당 된 점수**</span><span class="sxs-lookup"><span data-stu-id="a1ecd-156">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="a1ecd-157">예방적 필수</span><span class="sxs-lookup"><span data-stu-id="a1ecd-157">Preventative mandatory</span></span> | <span data-ttu-id="a1ecd-158">kb(56kbps</span><span class="sxs-lookup"><span data-stu-id="a1ecd-158">27</span></span> |
| <span data-ttu-id="a1ecd-159">예방적 임의</span><span class="sxs-lookup"><span data-stu-id="a1ecd-159">Preventative discretionary</span></span> | <span data-ttu-id="a1ecd-160">9 </span><span class="sxs-lookup"><span data-stu-id="a1ecd-160">9</span></span> |
| <span data-ttu-id="a1ecd-161">예방용 인지 필수</span><span class="sxs-lookup"><span data-stu-id="a1ecd-161">Detective mandatory</span></span> | <span data-ttu-id="a1ecd-162">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="a1ecd-162">3</span></span> |
| <span data-ttu-id="a1ecd-163">예방용 인지 임의</span><span class="sxs-lookup"><span data-stu-id="a1ecd-163">Detective discretionary</span></span> | <span data-ttu-id="a1ecd-164">1 </span><span class="sxs-lookup"><span data-stu-id="a1ecd-164">1</span></span> |
| <span data-ttu-id="a1ecd-165">정정 필수</span><span class="sxs-lookup"><span data-stu-id="a1ecd-165">Corrective mandatory</span></span> | <span data-ttu-id="a1ecd-166">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="a1ecd-166">3</span></span> |
| <span data-ttu-id="a1ecd-167">정정 임의</span><span class="sxs-lookup"><span data-stu-id="a1ecd-167">Corrective discretionary</span></span> | <span data-ttu-id="a1ecd-168">1 </span><span class="sxs-lookup"><span data-stu-id="a1ecd-168">1</span></span> |
  
<span data-ttu-id="a1ecd-169">![규정 준수 점수 컨트롤 포인트 값](../media/compliance-score-controls-scoring.png "규정 준수 점수 컨트롤 포인트 값")</span><span class="sxs-lookup"><span data-stu-id="a1ecd-169">![Compliance Score controls point values](../media/compliance-score-controls-scoring.png "Compliance Score controls point values")</span></span>