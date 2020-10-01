---
title: 준수 관리자를 사용 하 여 개선 작업 관리
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: 준수 점수 및 준수 관리자를 사용 하 여 개인 데이터에 대 한 보호 수준을 향상 시키는 방법을 알아봅니다.
ms.openlocfilehash: b5a112b7614de23af8540346e26dac3b7a4fa1c9
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333483"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="e9e22-103">준수 관리자를 사용 하 여 개선 작업 관리</span><span class="sxs-lookup"><span data-stu-id="e9e22-103">Use Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="e9e22-104">Microsoft 준수 관리자는 유럽 연합 [일반 데이터 보호 규정 (GDPR)](../compliance/gdpr.md), [캘리포니아 소비자 보호 Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (미국 의료 보험 개인 정보 취급 방침), LGPD (브라질 data Protection act)와 같은 데이터 개인 정보 규정에 관련 된 개선 사항을 관리 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-104">Microsoft Compliance Manager can help you manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](../compliance/gdpr.md), [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="e9e22-105">이 문서에서는 데이터 개인 정보 보호를 위해이 도구를 사용 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-105">This article provides guidance on the use of this tool for data privacy purposes.</span></span>

>[!Note]
><span data-ttu-id="e9e22-106">준수 관리자의 권장 사항을 준수 보장으로 해석하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="e9e22-107">규정 환경에 따라 고객 컨트롤의 효율성을 평가 하 고 유효성을 검사 하는 작업은 사용자의 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="e9e22-108">이러한 서비스는 [온라인 서비스 약관](https://go.microsoft.com/fwlink/?linkid=2108910)의 사용 약관에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="e9e22-109">[보안 및 규정 준수에 대 한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager) 참조</span><span class="sxs-lookup"><span data-stu-id="e9e22-109">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span></span>
>

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="e9e22-110">준수 관리자 시작</span><span class="sxs-lookup"><span data-stu-id="e9e22-110">Getting started with Compliance Manager</span></span>

#### <a name="what-is-compliance-manager"></a><span data-ttu-id="e9e22-111">준수 관리자 란?</span><span class="sxs-lookup"><span data-stu-id="e9e22-111">What is Compliance Manager</span></span>

<span data-ttu-id="e9e22-112">[준수 관리자](../compliance/compliance-manager.md) 는 microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 관리 하기 위한 microsoft 365 준수 센터의 워크플로 기반 위험 평가 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-112">[Compliance Manager](../compliance/compliance-manager.md) is a workflow-based risk assessment tool in the Microsoft 365 compliance center for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="e9e22-113">Microsoft 365 또는 Azure AD (Active Directory) 구독의 일부로, 준수 관리자는 Microsoft 클라우드 서비스에 대 한 공유 책임 모델 내에서 규정 준수를 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-113">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="e9e22-114">**평가를 사용할 준비가 되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="e9e22-114">**Ready to use assessments**</span></span>

<span data-ttu-id="e9e22-115">준수 관리자는 GDPR 및 HIPAA/HITECH와 같은 데이터 개인 정보 관련 규정에 부합 되는 [평가를 빌드하기](../compliance/compliance-manager-assessments.md) 위한 미리 작성 된 템플릿을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-115">Compliance Manager provides pre-built templates for [building assessments](../compliance/compliance-manager-assessments.md) that are aligned to data privacy-related regulations, such as GDPR and HIPAA/HITECH.</span></span> <span data-ttu-id="e9e22-116">이 서식 파일에는 규정 요구 사항을 충족 하기 위한 개선 작업을 수행 하는 데 도움이 되는 기본 제공 컨트롤 매핑이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-116">The templates have built-in control mapping to help you take improvement actions for meeting the regulation's requirements.</span></span> <span data-ttu-id="e9e22-117">각 평가에서는 특정 대상 서비스에 대 한 각 규정 호출을 제어 하는 컨트롤에 대 한 정보를 제공 하며, Microsoft에서 관리 하 고 제어 하는 컨트롤을 통해 분류 하 여</span><span class="sxs-lookup"><span data-stu-id="e9e22-117">Each assessment provides information about the controls each regulation calls for specific to the target service, broken out by controls you manage and controls Microsoft manages.</span></span> 

<span data-ttu-id="e9e22-118">미리 작성 된 서식 파일을 사용 하면 위험 평가를 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-118">Using a pre-built template helps you quickly get started with risk assessments.</span></span> <span data-ttu-id="e9e22-119">규정 준수 관리자를 보다 능숙 하 게 사용할 수 있는 것 처럼, 사용자가 직접 작성 한 서식 파일을 사용자 지정할 수도 있고, 향상 된 작업을 추가 하 여 조직의 요구 사항에 맞게 고유한 사용자 지정 평가를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-119">As you become more proficient in using Compliance Manger, you can customize a pre-built template by adding your own controls and improvement actions, or you can create your own custom assessments to suit your organization's needs.</span></span>

<span data-ttu-id="e9e22-120">준수 관리자가 제공한 [평가 템플릿의 전체 목록을](../compliance/compliance-manager-templates-list.md) 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-120">View the [full list of assessment templates](../compliance/compliance-manager-templates-list.md) provided by Compliance Manager.</span></span>

<span data-ttu-id="e9e22-121">**실시간 준수 점수**</span><span class="sxs-lookup"><span data-stu-id="e9e22-121">**Real-time compliance score**</span></span>

<span data-ttu-id="e9e22-122">또한 준수 관리자는 컨트롤 내에서 권장 되는 개선 작업을 완료 하는 과정을 측정 하는 준수 점수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-122">Compliance Manager also provides you with a compliance score that measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="e9e22-123">이 점수를 사용 하 여 위험을 줄일 수 있도록 진행 상황을 모니터링 하 고 작업의 우선 순위를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-123">You can use this score to help monitor your progress and prioritize actions based on their potential to reduce risk.</span></span>

#### <a name="use-the-compliance-manager-quickstart-guide"></a><span data-ttu-id="e9e22-124">준수 관리자의 빠른 시작 가이드 사용</span><span class="sxs-lookup"><span data-stu-id="e9e22-124">Use the Compliance Manager quickstart guide</span></span>

<span data-ttu-id="e9e22-125">[준수 관리자의 빠른](../compliance/compliance-manager-quickstart.md) 단계 및 준수 관리자와 함께 작업 하는 데 도움이 되는 주요 리소스에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-125">The [Compliance Manager quickstart](../compliance/compliance-manager-quickstart.md) guide provides graduated steps and links to key resources to help you work with Compliance Manager:</span></span>

- [<span data-ttu-id="e9e22-126">처음 방문: 준수 관리자에 게 익숙해져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-126">First visit: get familiar with Compliance Manager</span></span>](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - <span data-ttu-id="e9e22-127">준수 관리자 대시보드 작업</span><span class="sxs-lookup"><span data-stu-id="e9e22-127">Working with your Compliance Manager dashboard</span></span>
    - <span data-ttu-id="e9e22-128">준수 점수 이해</span><span class="sxs-lookup"><span data-stu-id="e9e22-128">Understanding your compliance score</span></span>
    - <span data-ttu-id="e9e22-129">개선 작업에 대 한 학습</span><span class="sxs-lookup"><span data-stu-id="e9e22-129">Learning about improvement actions</span></span>
    - <span data-ttu-id="e9e22-130">평가 및 템플릿 이해</span><span class="sxs-lookup"><span data-stu-id="e9e22-130">Understanding assessments and templates</span></span>
- [<span data-ttu-id="e9e22-131">램프 업: 준수 작업을 관리 하도록 준수 관리자 구성</span><span class="sxs-lookup"><span data-stu-id="e9e22-131">Ramping up: configure Compliance Manager to manage your compliance activities</span></span>](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - <span data-ttu-id="e9e22-132">첫 번째 평가 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="e9e22-132">Building and managing your first assessment</span></span>
    - <span data-ttu-id="e9e22-133">평가에서 제어를 완료 하기 위한 개선 작업에 대 한 구현 및 테스트 작업 수행</span><span class="sxs-lookup"><span data-stu-id="e9e22-133">Performing implementation and testing work on improvement actions to complete controls in your assessments</span></span>
    - <span data-ttu-id="e9e22-134">다양 한 작업으로 인해 준수 점수가 영향을 미치는 방식 이해</span><span class="sxs-lookup"><span data-stu-id="e9e22-134">Understanding how different actions impact your compliance score</span></span>
- [<span data-ttu-id="e9e22-135">수직 확장: 사용자 지정 요구 사항을 충족 하기 위해 고급 기능 사용</span><span class="sxs-lookup"><span data-stu-id="e9e22-135">Scaling up: use advanced functionality to meet your custom needs</span></span>](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - <span data-ttu-id="e9e22-136">Microsoft 제품이 아닌 365 제품을 추적 하기 위한 사용자 지정 평가 만들기</span><span class="sxs-lookup"><span data-stu-id="e9e22-136">Creating your custom assessments to track non-Microsoft 365 products</span></span>
    - <span data-ttu-id="e9e22-137">기존 서식 파일을 수정 하 여 컨트롤 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="e9e22-137">Modifying existing templates to add or remove controls</span></span>
    - <span data-ttu-id="e9e22-138">개선 작업에 대 한 자동화 된 테스트 설정</span><span class="sxs-lookup"><span data-stu-id="e9e22-138">Setting up automated testing of improvement actions</span></span>

## <a name="how-your-compliance-score-is-calculated"></a><span data-ttu-id="e9e22-139">규정 준수 점수 계산 방법</span><span class="sxs-lookup"><span data-stu-id="e9e22-139">How your compliance score is calculated</span></span>

<span data-ttu-id="e9e22-140">Microsoft 및 고객 관리 제어 구현의 조합에 따라 규정 준수 점수가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-140">Your compliance score is calculated based on a combination of Microsoft and customer-managed control implementations.</span></span> <span data-ttu-id="e9e22-141">자세한 설명은 [준수 점수 계산](../compliance/compliance-score-calculation.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9e22-141">See [compliance score calculation](../compliance/compliance-score-calculation.md) for a detailed explanation.</span></span>

<span data-ttu-id="e9e22-142">컨트롤이 필수 인지 아니면 임의 인지에 따라 점수 값이 할당 되 고 사용자가 예방적이 든 상관 없이 예방용 인지 인지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-142">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="e9e22-143">이는 다른 컨트롤을 기준으로이를 구현 하지 않을 위험을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-143">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="e9e22-144">규정 준수 점수 계산 문서에 나와 있는 것 처럼 예방적 컨트롤은 예방용 인지 보다 더 높은 점수를 얻게 되며, 필수 컨트롤은 임의의 것 보다 더 높은 점수를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-144">As presented in the compliance score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>

<span data-ttu-id="e9e22-145">규정 준수 점수 관리자 UI에는 이러한 매개 변수가 나열 되지 않으며 필터링 기능도 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-145">The Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="e9e22-146">그러나 준수 관리자에서 연결 된 서식 파일을 다운로드 하는 경우 결과 데이터 집합에는 대부분의 규정에 해당 하는 매개 변수가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-146">However, if you download the associated template from  Compliance Manager, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="e9e22-147">기술 제어의 경우 준수 관리자는 작업을 성공적으로 구현 및 테스트 한 후에 향상 된 개선 작업 점수를 자동으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-147">For technical controls, Compliance Manager automatically updates the improvement action score once the action has been successfully implemented and tested.</span></span> <span data-ttu-id="e9e22-148">&mdash;작동 하거나 설명서와 관련 된 기타 기술 없는 제어 작업을 &mdash; 점수가 점수에 들어가기 전에 구현 됨에 따라 수동으로 기록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-148">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually as implemented before points count toward your score.</span></span>

<span data-ttu-id="e9e22-149">또한 &mdash; 데이터 개인 정보 규정 준수 이외의 이유로 보존 레이블을 사용 하 여 다른 용도로도 사용 하는 경우에는 해당 기능을 사용 하는 것이 좋지만 &mdash; , 의도적인 규정 준수 작업의 일부가 아닌 경우에는 다른 목적에 대 한 특정 향상 작업을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-149">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="e9e22-150">규정 준수 점수는 광범위 한 규모의 개선을 추적 하기 위한 상대 수단으로 간주 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-150">Your compliance score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="e9e22-151">완벽 한 점수를가지고 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-151">You should not pursue a perfect score.</span></span>

## <a name="additional-guidance"></a><span data-ttu-id="e9e22-152">추가 안내</span><span class="sxs-lookup"><span data-stu-id="e9e22-152">Additional guidance</span></span>

<span data-ttu-id="e9e22-153">다음은 준수 관리자를 사용 하 여 데이터 개인 정보 규정 준수를 달성 하는 데 도움이 되는 몇 가지 중요 한 팁입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-153">Here are a few important tips for using Compliance Manager to help you achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="e9e22-154">각 데이터 개인 정보 규정에는 기술 컨트롤, 문서 사양, 운영, 프로세스 및 보고 요구 사항의 조합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-154">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="e9e22-155">이러한 모든 기능을 향상 작업에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-155">All of these show up in the improvement actions.</span></span>

- <span data-ttu-id="e9e22-156">검토 작업을 관심 있는 영역에 집중 하기 위해 준수 관리자 관리자의 **솔루션** 탭에서 작업 유형별로 필터링 할 수 있습니다. [준수 관리자 대시보드 보기 필터링](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)에 대해 더 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="e9e22-156">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Manager admin. Learn more about [filtering your Compliance Manager dashboard view](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).</span></span>

- <span data-ttu-id="e9e22-157">준수 관리자에서 식별 된 개선 작업의 상대적 중요도와 우선 순위는 조직에서 관리 해야 하는 데이터 개인 정보 위험과 함께 광범위 한 위험 검토의 일부로 간주 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-157">The relative importance and priority of improvement actions identified in Compliance Manager should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span>

- <span data-ttu-id="e9e22-158">여러 규정 요구 사항에 대 한 향상 된 작업 집계를 사용 하는 경우에도 GDPR, LGPD, CCPA 및 HIPAA-HITECH에 대 한 규정 평가 템플릿이 선택 된 경우 준수 관리자에 게는 거의 400 개선 작업이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-158">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Manager.</span></span> <span data-ttu-id="e9e22-159">이 긴 목록을 보다 효율적으로 활용 하려면 향상 작업 필터를 사용 하 여 결과 집합을 보다 쉽게 관리할 수 있는 목록으로 줄이십시오.</span><span class="sxs-lookup"><span data-stu-id="e9e22-159">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="e9e22-160">Categories filter는이 전체 솔루션의 추적, 방지, 보호, 보존 및 조사를 수행 하는 논리적 그룹화를 통해 향상 작업을 필터링 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-160">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span>

- <span data-ttu-id="e9e22-161">향상 작업에 나열 된 일부 컨트롤은 특정 규제 문서에 직접 연결 되어 있는 것으로 간주 되는 반면, 다른 컨트롤은 규정의 스피릿와 간접적으로 더 많이 연결 될 수 있으며,이는 단순히 권장 되는 작업 또는 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e22-161">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and many times are simply recommended activities or best practices.</span></span>