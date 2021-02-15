---
title: Microsoft 365를 사용하여 데이터 개인 정보 보호 규정에 대한 정보 보호 배포
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: 정보를 보호하고 데이터 개인 정보 보호 규정을 준수하도록 보안 및 서비스 인프라를 구성합니다.
ms.openlocfilehash: 9af0a113d9b0eb2cbca07fdf457cd8bb7db3e094
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842299"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="31617-103">Microsoft 365를 사용하여 데이터 개인 정보 보호 규정에 대한 정보 보호 배포</span><span class="sxs-lookup"><span data-stu-id="31617-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="31617-104">조직은 사용자가 IT 인프라에 저장된 개인 정보 보호, 관리 및 제어 권한을 제공해야 하는 지역별 데이터 개인 정보 보호 규정의 적용을 을(를) 따라야 할 수 있습니다(이 경우, 조직은 클라우드와 같은 IT 인프라에 저장된 개인 정보를 보호, 관리 및 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-104">Your organization may be subject to regional data privacy regulations that require you to protect, manage, and provide rights and control over personal information stored in your IT infrastructure, including both on-premises and in the cloud.</span></span> <span data-ttu-id="31617-105">데이터 개인 정보 보호 규정의 가장 좋은 예는 유럽 연합의 GDPR(일반 데이터 보호 규정)입니다.</span><span class="sxs-lookup"><span data-stu-id="31617-105">The best example of a data privacy regulation is the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="31617-106">데이터 개인 정보 규정을 준수하지 못하면 상당한 벌금이 부과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31617-106">Failure to comply with data privacy regulations can result in substantial fines.</span></span>

<span data-ttu-id="31617-107">Microsoft 365의 데이터 유형의 예로는 Microsoft Teams의 채팅 세션, Exchange의 전자 메일 및 SharePoint 및 OneDrive의 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31617-107">Examples of the types of data in Microsoft 365 include chat sessions in Microsoft Teams, emails in Exchange, and files in SharePoint and OneDrive.</span></span> <span data-ttu-id="31617-108">이 솔루션은 위험을 평가하고, 데이터 개인 정보 규정이 적용된 Microsoft 365 서비스에 저장된 개인 데이터에 대한 데이터 개인 정보 보호 인시던트의 보호, 관리 및 대응 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-108">This solution provides guidance on how to assess risks and identify information, protect, govern, and respond to data privacy incidents for personal data stored in Microsoft 365 services that is subject to data privacy regulations.</span></span>

![데이터 개인 정보 보호 규정에 대한 정보 보호](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

<span data-ttu-id="31617-110">데이터 개인 정보 보호 요구에 대한 Microsoft 365 ID, 장치 및 위협 방지 컨트롤을 사용하는 데 관한 추가 정보도 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="31617-110">Additional information is also provided on the use of Microsoft 365 identity, device, and threat protection controls for your data privacy needs.</span></span> 

<span data-ttu-id="31617-111">데이터 개인 정보 보호 규정을 준수하기 위한 정보를 보호하기 위한 기준을 충족하기 위해 이러한 Microsoft 365 기능 및 기능을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="31617-111">To meet the criteria for protecting information for compliance with data privacy regulations, use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="31617-112">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="31617-112">Capability or feature</span></span> | <span data-ttu-id="31617-113">설명</span><span class="sxs-lookup"><span data-stu-id="31617-113">Description</span></span> | <span data-ttu-id="31617-114">라이선싱</span><span class="sxs-lookup"><span data-stu-id="31617-114">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="31617-115">규정 관리자</span><span class="sxs-lookup"><span data-stu-id="31617-115">Compliance Manager</span></span> | <span data-ttu-id="31617-116">규정 준수 활동을 관리하고, 현재 준수 구성의 전체 점수를 얻은 다음 Microsoft 365 규정 준수 센터에서 이 워크플로 기반 위험 평가 도구의 개선을 위한 권장 사항을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-116">Manage regulatory compliance activities, get an overall score of your current compliance configuration, and find recommendations for improvement in this workflow-based risk assessment tool in the Microsoft 365 compliance center.</span></span> | <span data-ttu-id="31617-117">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="31617-117">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="31617-118">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="31617-118">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="31617-119">전자 메일 메시지, 사무실 문서 및 협업 도구와 같은 Microsoft 365 앱과 데이터를 공격으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-119">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> | <span data-ttu-id="31617-120">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="31617-120">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="31617-121">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="31617-121">Sensitivity labels</span></span> | <span data-ttu-id="31617-122">전자 메일, 파일 또는 사이트에 다양한 수준의 보호 기능을 갖춘 레이블을 배치하여 사용자의 생산성과 협업 능력을 저해하지 않고 조직의 데이터를 분류하고 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-122">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="31617-123">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="31617-123">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="31617-124">데이터 손실 방지(DLP).</span><span class="sxs-lookup"><span data-stu-id="31617-124">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="31617-125">개인 정보가 포함된 데이터 공유와 같은 위험하거나 부주의하거나 부적절한 공유를 내외부적으로 탐지, 경고 및 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-125">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="31617-126">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="31617-126">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="31617-127">데이터 보존 레이블 및 정책.</span><span class="sxs-lookup"><span data-stu-id="31617-127">Data retention labels and policies</span></span> | <span data-ttu-id="31617-128">조직의 정책 또는 데이터 규정을 준수하기 위해 고객의 개인 데이터 스토리지에 대한 데이터 및 요구사항을 보관하는 기간과 같은 정보 거버넌스 제어를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-128">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="31617-129">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="31617-129">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="31617-130">전자 메일 암호화</span><span class="sxs-lookup"><span data-stu-id="31617-130">Email encryption</span></span> | <span data-ttu-id="31617-131">고객의 개인 데이터와 같이 규제 데이터가 들어 있는 조직 내외부의 사용자 간에 암호화된 전자 메일 메시지를 주고 받습니다.</span><span class="sxs-lookup"><span data-stu-id="31617-131">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="31617-132">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="31617-132">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a><span data-ttu-id="31617-133">이 솔루션의 지침 구성</span><span class="sxs-lookup"><span data-stu-id="31617-133">Organization of the guidance in this solution</span></span>

<span data-ttu-id="31617-134">하나 이상의 개인 정보 관련 규정에 따라 개인 데이터를 식별, 관리, 제어 및 모니터링하는 데 사용할 수 있는 Microsoft 365 도구를 이해하기 위해 이 지침은 섹션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="31617-134">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![데이터 개인 정보 보호 규정에 대한 정보 보호를 구현하는 단계](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

<span data-ttu-id="31617-136">이러한 각 섹션은 이 솔루션의 별도 문서에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-136">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="31617-137">데이터 개인 정보 보호 의무에 이미 익숙하고 기존 요금제에 대해 실행되고 있는 경우 금지, 보호, 보존 및 조사 지침에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31617-137">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="31617-138">이 지침에 따라 반드시 데이터 개인 정보 보호 규정을 준수할 필요는 없습니다. 특히 기능의 컨텍스트 외부에 있는 필요한 단계의 수를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-138">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="31617-139">귀하는 규정 준수를 보장하고 법률 및 규정 준수 팀에 문의하거나 규정 준수를 전문적으로 하는 타사의 지침과 조언을 구할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31617-139">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="31617-140">계획: 데이터 개인 정보 보호 위험을 평가하고 중요한 항목 식별</span><span class="sxs-lookup"><span data-stu-id="31617-140">Plan: Assess data privacy risks and identify sensitive items</span></span>

<span data-ttu-id="31617-141">조직에 적용될 데이터 개인 정보 규정 및 위험을 평가하는 것은 Microsoft 365 구성을 통해 달성할 수 있는 개선을 포함하여 개선을 구현하기 전에 먼저 취할 주요 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="31617-141">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="31617-142">여기에는 조직에서 준수해야 하는 규정 제어가 적용된 특정 중요한 정보 유형의 전반적인 준비 평가 또는 식별과 Microsoft 365 환경에서 이러한 유형의 발생이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31617-142">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="31617-143">자세한 내용은 데이터 개인 정보 보호 위험 평가 및 [중요한 항목 식별을 참조하세요.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="31617-143">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a><span data-ttu-id="31617-144">추적: 위험 평가 실행 및 준수 점수 확인</span><span class="sxs-lookup"><span data-stu-id="31617-144">Track: Run risk assessments and check your compliance score</span></span>

<span data-ttu-id="31617-145">Microsoft 365 규정 준수 센터에서 제공되는 준수 관리자는 사용자에게 적용되는 여러 데이터 개인 정보 보호 규정과 관련된 것뿐만 아니라 전반적인 개선 작업을 추적하고 관리할 수 있는 기본 제공 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-145">Compliance Manager, available in the Microsoft 365 compliance center, provides you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations that apply to you.</span></span>

<span data-ttu-id="31617-146">선택한 각 평가 템플릿에 대한 작업 항목을 추적하고 특정 규제 컨트롤을 보고 특정 작업과 관련될 수 있는 각 규정과 관련된 기본 제공 평가 템플릿을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-146">Leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="31617-147">자세한 내용은 준수 관리자를 사용하여 개선 [작업을 관리하세요.](information-protection-deploy-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="31617-147">For more information, see [Use Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-protect-personal-data"></a><span data-ttu-id="31617-148">방지: 개인 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="31617-148">Prevent: Protect personal data</span></span>

<span data-ttu-id="31617-149">Microsoft 365는 데이터 개인 정보 보호 규정 준수를 준수하는 데 사용할 수 있는 다양한 ID, 장치 및 위협 방지 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-149">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="31617-150">자세한 내용은 데이터 개인 정보 보호 규정에 대한 ID, 장치 및 [위협 보호 사용을 참조하세요.](information-protection-deploy-identity-device-threat.md)</span><span class="sxs-lookup"><span data-stu-id="31617-150">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="31617-151">이 문서에서는 이러한 영역에서 데이터 개인 정보 규정이 일반적으로 요구하는 사항에 대해 간략하게 설명하고 관련 Microsoft 365 솔루션 목록을 제공합니다. 또한 구현 요구 사항을 충족하는 데 도움이 되는 추가 정보로 연결되는 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-151">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="31617-152">데이터 개인 정보 보호 규정을 준수하는 정보 보호</span><span class="sxs-lookup"><span data-stu-id="31617-152">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="31617-153">데이터 개인 정보 보호 규정은 GDPR, 캘리포니아 소비자 보호법(CCPA), HIPAA-HITECH(미국 의료 개인 정보 보호법) 및 브라질 데이터 보호법(LGPD)의 샘플 집합에 있는 4개의 데이터 개인 정보 보호 규정에 대한 4개 이상의 정보 보호 컨트롤을 포함하여 사용자 환경에 사용할 수 있는 다양한 개인 정보 보호 제어를 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-153">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="31617-154">자세한 내용은 조직의 데이터 개인 [정보 보호 규정을 준수하는 정보 보호를 참조하세요.](information-protection-deploy-protect-information.md)</span><span class="sxs-lookup"><span data-stu-id="31617-154">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="31617-155">이 문서에서는 조직의 데이터 개인 정보 보호에 대한 정보 보호 요구 사항을 해결하기 위해 사용할 수 있는 주요 제어 체계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-155">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="31617-156">보존: 데이터 개인 정보 보호 규정이 적용된 정보 관리</span><span class="sxs-lookup"><span data-stu-id="31617-156">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="31617-157">데이터 개인 정보 규정은 GDPR, CCPA, HIPAA-HITECH 및 LGPD 샘플 집합의 네 가지 데이터 개인 정보 보호 규정에 대한 24개 이상의 컨트롤을 포함하여 사용자 환경에서 사용할 수 있는 개인 정보 거버넌스 제어를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="31617-157">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="31617-158">자세한 내용은 조직의 데이터 개인 [정보 보호 규정이 적용된 관리 정보를 참조하세요.](information-protection-deploy-govern.md)</span><span class="sxs-lookup"><span data-stu-id="31617-158">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="31617-159">데이터 개인 정보 보호 규정은 의도적인 보존과 같은 정보 거버넌스와 관련하여 모호할 수 있는 반면, 이 문서의 삭제 및 보관에서는 조직의 데이터 개인 정보 보호에 대한 주소 정보 거버넌스 요구 사항을 사용할 수 있는 기본 제어 체계를 세우고 &mdash; &mdash; 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31617-159">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a><span data-ttu-id="31617-160">조사: 데이터 개인 정보 보호 인시던트 모니터링, 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="31617-160">Investigate: Monitor, investigate, and respond to data privacy incidents</span></span>

<span data-ttu-id="31617-161">관련 기능을 작동할 때 조직의 데이터 개인 정보 인시던트 모니터링, 조사 및 대응에 도움이 되는 Microsoft 365 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31617-161">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="31617-162">이러한 각 기관에 대한 프로세스, 절차 및 기타 문서가 있는 것은 규제 기관의 규정 준수를 입증하는 데 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31617-162">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="31617-163">자세한 내용은 조직의 데이터 개인 정보 인시던트 모니터링 및 [대응을 참조하세요.](information-protection-deploy-monitor-respond.md)</span><span class="sxs-lookup"><span data-stu-id="31617-163">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
