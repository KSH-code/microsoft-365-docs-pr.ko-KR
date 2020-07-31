---
title: Microsoft 365을 사용 하 여 데이터 개인 정보 보호 규정에 대 한 information protection 배포
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
description: 보안 및 서비스 인프라를 구성 하 여 정보를 보호 하 고 데이터 개인 정보 규정을 준수 합니다.
ms.openlocfilehash: 640ce075515c687c037cb0e4ab3e03e3beda81dc
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522292"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="36e47-103">Microsoft 365을 사용 하 여 데이터 개인 정보 보호 규정에 대 한 information protection 배포</span><span class="sxs-lookup"><span data-stu-id="36e47-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="36e47-104">조직에서 온-프레미스와 클라우드를 모두 포함 하 여 IT 인프라에 저장 된 개인 정보를 보호, 관리 및 제어 해야 하는 지역별 데이터 개인 정보 규정을 준수할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-104">Your organization may be subject to regional data privacy regulations that require you to protect, manage, and provide rights and control over personal information stored in your IT infrastructure, including both on-premises and in the cloud.</span></span> <span data-ttu-id="36e47-105">데이터 개인 정보 취급 규정의 가장 좋은 예는 유럽 연합의 GDPR (일반 데이터 보호 규정)입니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-105">The best example of a data privacy regulation is the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="36e47-106">데이터 개인 정보 규정을 준수 하지 않으면 상당한 벌금과 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-106">Failure to comply with data privacy regulations can result in substantial fines.</span></span>

<span data-ttu-id="36e47-107">Microsoft 365의 데이터 형식에는 Microsoft 팀의 채팅 세션, Exchange의 전자 메일 및 SharePoint 및 OneDrive의 파일 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-107">Examples of the types of data in Microsoft 365 include chat sessions in Microsoft Teams, emails in Exchange, and files in SharePoint and OneDrive.</span></span> <span data-ttu-id="36e47-108">이 솔루션은 데이터 개인 정보 규정을 준수 하는 Microsoft 365 services에 저장 된 개인 데이터에 대 한 데이터 개인 정보 인시던트를 식별, 검색, 보호, 제어 및 대응 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-108">This solution provides guidance on how to identify, locate, protect, govern, and respond to data privacy incidents for personal data stored in Microsoft 365 services that is subject to data privacy regulations.</span></span>

![데이터 개인 정보 규정을 위한 정보 보호 배포](../media/information-protection-deploy/information-protection-deploy-big-picture.png)

<span data-ttu-id="36e47-110">데이터 개인 정보 요구 사항에 대해 Microsoft 365 id, 장치 및 위협 방지 컨트롤을 사용 하는 경우에도 추가 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-110">Additional information is also provided on the use of Microsoft 365 identity, device, and threat protection controls for your data privacy needs.</span></span> 

<span data-ttu-id="36e47-111">데이터 개인 정보 규정 준수를 위해 정보를 보호 하기 위한 기준을 충족 하려면 이러한 Microsoft 365 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-111">To meet the criteria for protecting information for compliance with data privacy regulations, use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="36e47-112">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="36e47-112">Capability or feature</span></span> | <span data-ttu-id="36e47-113">설명</span><span class="sxs-lookup"><span data-stu-id="36e47-113">Description</span></span> | <span data-ttu-id="36e47-114">라이선싱</span><span class="sxs-lookup"><span data-stu-id="36e47-114">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="36e47-115">규정 관리자</span><span class="sxs-lookup"><span data-stu-id="36e47-115">Compliance Manager</span></span> | <span data-ttu-id="36e47-116">Microsoft 서비스 신뢰 포털에서 이 워크플로우 기반 위험 평가 도구를 사용하여 Microsoft 클라우드 서비스와 관련된 규정 준수 활동을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-116">Manage regulatory compliance activities related to Microsoft cloud services with this workflow-based risk assessment tool in the Microsoft Service Trust Portal.</span></span> | <span data-ttu-id="36e47-117">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="36e47-117">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="36e47-118">준수 점수(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="36e47-118">Compliance Score (preview)</span></span> | <span data-ttu-id="36e47-119">Microsoft 365 Compliance Center에서 현재 규정 준수 구성의 전체 점수와 이를 개선하기 위한 권장 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-119">See an overall score of your current compliance configuration and recommendations for improving it in the Microsoft 365 Compliance Center.</span></span> | <span data-ttu-id="36e47-120">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="36e47-120">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="36e47-121">Office ATP (Advanced Threat Protection)</span><span class="sxs-lookup"><span data-stu-id="36e47-121">Office Advanced Threat Protection (ATP)</span></span> | <span data-ttu-id="36e47-122">전자 메일 메시지, 사무실 문서 및 협업 도구와 같은 Microsoft 365 앱과 데이터를 공격으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-122">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> | <span data-ttu-id="36e47-123">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="36e47-123">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="36e47-124">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="36e47-124">Sensitivity labels</span></span> | <span data-ttu-id="36e47-125">전자 메일, 파일 또는 사이트에 다양한 수준의 보호 기능을 갖춘 레이블을 배치하여 사용자의 생산성과 협업 능력을 저해하지 않고 조직의 데이터를 분류하고 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-125">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="36e47-126">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="36e47-126">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="36e47-127">데이터 손실 방지(DLP).</span><span class="sxs-lookup"><span data-stu-id="36e47-127">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="36e47-128">개인 정보가 포함된 데이터 공유와 같은 위험하거나 부주의하거나 부적절한 공유를 내외부적으로 탐지, 경고 및 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-128">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="36e47-129">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="36e47-129">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="36e47-130">데이터 보존 레이블 및 정책.</span><span class="sxs-lookup"><span data-stu-id="36e47-130">Data retention labels and policies</span></span> | <span data-ttu-id="36e47-131">조직의 정책 또는 데이터 규정을 준수하기 위해 고객의 개인 데이터 스토리지에 대한 데이터 및 요구사항을 보관하는 기간과 같은 정보 거버넌스 제어를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-131">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="36e47-132">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="36e47-132">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="36e47-133">전자 메일 암호화</span><span class="sxs-lookup"><span data-stu-id="36e47-133">Email encryption</span></span> | <span data-ttu-id="36e47-134">고객의 개인 데이터와 같이 규제 데이터가 들어 있는 조직 내외부의 사용자 간에 암호화된 전자 메일 메시지를 주고 받습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-134">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="36e47-135">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="36e47-135">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a><span data-ttu-id="36e47-136">이 솔루션의 지침 구성</span><span class="sxs-lookup"><span data-stu-id="36e47-136">Organization of the guidance in this solution</span></span>

<span data-ttu-id="36e47-137">하나 이상의 개인 정보 관련 규정에 따라 개인 데이터를 식별, 관리, 제어 및 모니터링 하는 데 사용할 수 있는 Microsoft 365 도구를 이해 하는 데 도움이 되도록이 지침은 섹션으로 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-137">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![데이터 개인 정보 규정을 위한 정보 보호 배포](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="36e47-139">이러한 각 섹션은이 솔루션의 별도 문서에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-139">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="36e47-140">데이터 개인 정보 취급 방침을 이미 잘 알고 있고 기존 계획에 대해 실행 중인 경우에는 방지, 보호, 보존 및 조사 지침에 중점을 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-140">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="36e47-141">이 가이드를 따르면, 특히 기능 컨텍스트 외부에 있는 필요한 단계 수를 고려 하 여 데이터 개인 정보 규정을 준수 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-141">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="36e47-142">준수 여부를 확인 하 고 법률 및 규정 준수 팀에 문의 하거나, 규정 준수를 전문적으로 진행 하는 제 3 자가 제공 하는 지침 및 조언을 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-142">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="36e47-143">계획: 데이터 개인 정보 위험 평가 및 중요 한 항목 확인</span><span class="sxs-lookup"><span data-stu-id="36e47-143">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="36e47-144">조직에 적용 되는 데이터 개인 정보 규정 및 위험 요소를 평가 하는 것은 Microsoft 365 구성을 통해 얻을 수 있는 기능을 포함 하 여 개선 된 사항을 구현 하기 전에 먼저 수행 해야 하는 주요 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-144">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="36e47-145">여기에는 조직에서 준수 해야 하는 규정 통제와 관련 된 특정 중요 한 정보 유형, 그리고 Microsoft 365 환경에서 발생 하는 상황을 식별 하는 전반적인 준비 평가 또는 id가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-145">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="36e47-146">자세한 내용은 [데이터 개인 정보 보호 위험 평가 및 중요 한 항목 식별](information-protection-deploy-assess.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36e47-146">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="36e47-147">추적: 준수 점수 및 준수 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="36e47-147">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="36e47-148">준수 점수 및 준수 관리자는 Microsoft 365 준수 관리 센터 및 서비스 신뢰 포털에서 사용 가능한 통합 도구 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-148">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="36e47-149">이러한 도구를 함께 사용 하면 기본 제공 되는 다양 한 데이터 개인 정보 규정에 따라 전반적인 향상 작업을 추적 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-149">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="36e47-150">또한이 도구를 사용 하면 각 규제 규정에 따라 기본 제공 되는 평가 템플릿을 활용 하 여 선택한 각 평가 템플릿의 작업 항목을 추적할 수 있을 뿐만 아니라 특정 규정 제어를 확인 하 고 특정 작업에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-150">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="36e47-151">자세한 내용은 [준수 점수 및 준수 관리자를 사용 하 여 개선 작업 관리](information-protection-deploy-compliance.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36e47-151">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="36e47-152">금지: 데이터 개인 정보 규정에 id, 장치 및 위협 보호 사용</span><span class="sxs-lookup"><span data-stu-id="36e47-152">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="36e47-153">Microsoft 365에서는 데이터 개인 정보 규정 준수를 준수 하는 데 사용할 수 있는 다양 한 id, 장치 및 위협 보호 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-153">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="36e47-154">자세한 내용은 [데이터 개인 정보 규정에 대 한 id, 장치 및 위협 보호 사용](information-protection-deploy-identity-device-threat.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36e47-154">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="36e47-155">이 문서에서는 이러한 영역에서 일반적으로 호출 되는 데이터 개인 정보 보호 규정을 소개 하 고, 구현 요구 사항을 해결 하는 데 도움이 되는 자세한 정보에 대 한 링크와 함께 관련 Microsoft 365 솔루션 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-155">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="36e47-156">데이터 개인 정보 규정의 영향을 받는 정보 보호</span><span class="sxs-lookup"><span data-stu-id="36e47-156">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="36e47-157">데이터 프라이버시 규정은 GDPR, 캘리포니아 CCPA), HIPAA-HITECH (미국 의료 보험 개인 정보 보호 act) 및 LGPD (브라질 Data Protection Act)의 예제 집합에 있는 4 가지 데이터 개인 정보 보호 기능을 40 포함 하 여 사용자 환경에서 사용할 수 있는 다양 한 개인 정보 보호 컨트롤을 규정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-157">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="36e47-158">자세한 내용은 [조직의 데이터 개인 정보 규정에 대 한 정보 보호 주체를](information-protection-deploy-protect-information.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36e47-158">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="36e47-159">이 문서에서는 조직의 데이터 프라이버시에 대 한 정보 보호 요구 사항을 해결 하는 데 사용할 수 있는 기본 컨트롤 구성표를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-159">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="36e47-160">Retain: 데이터 개인 정보 규정의 영향을 받는 정보를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-160">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="36e47-161">데이터 개인 정보 규정 통화 GDPR, CCPA, HIPAA-HITECH 및 LGPD의 예제 집합에 포함 된 4 가지 데이터 개인 정보 규정에 따라 25 개 이상의 컨트롤을 비롯 하 여 사용자 환경에서 사용 될 수 있는 개인 홍보 관리 컨트롤에 대 한 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-161">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="36e47-162">자세한 내용은 [조직의 데이터 개인 정보 규정에 대 한 제어 정보](information-protection-deploy-govern.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36e47-162">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="36e47-163">고의적 보존, 삭제 및 보관과 같은 정보 거 버 넌 스에 대 한 데이터 개인 정보 규정은 모호 하 게 할 수 있지만, &mdash; &mdash; 이 문서에서는 조직의 데이터 개인 정보 보호를 위해 주소 정보 관리 요구 사항을 사용할 수 있는 기본 컨트롤 스키마를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-163">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="36e47-164">조사: 데이터 개인 정보 규정을 모니터링 하 고 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-164">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="36e47-165">관련 기능을 operationalize 때 조직의 데이터 개인 정보 인시던트를 모니터링, 조사 및 대응 하는 데 도움이 되는 Microsoft 365 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-165">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="36e47-166">이러한 각 단계에 대 한 프로세스, 절차 및 기타 설명서도 규정 된 본문에 대 한 준수를 시연 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-166">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="36e47-167">자세한 내용은 [조직의 데이터 개인 정보 보호 인시던트에 모니터링 및 응답을](information-protection-deploy-monitor-respond.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36e47-167">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
