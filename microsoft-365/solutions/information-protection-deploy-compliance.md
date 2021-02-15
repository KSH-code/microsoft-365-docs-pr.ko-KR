---
title: 준수 관리자를 사용하여 개선 작업 관리
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
- m365solution-scenario
ms.custom: ''
description: 준수 점수 및 준수 관리자를 사용하여 개인 데이터에 대한 보호 수준을 개선하는 방법을 학습합니다.
ms.openlocfilehash: f90826795197b392f629eb8eec71b7f27081b697
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791885"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="6c420-103">준수 관리자를 사용하여 개선 작업 관리</span><span class="sxs-lookup"><span data-stu-id="6c420-103">Use Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="6c420-104">Microsoft 준수 관리자는 유럽 연합 [GDPR(일반](../compliance/gdpr.md)데이터 보호 규정), 캘리포니아 소비자 보호법 [CCPA(](../compliance/ccpa-faq.md)캘리포니아 소비자 보호법), HIPAA-HITECH(미국 의료 개인 정보 보호법) 및 브라질 데이터 보호법(LGPD)과 같은 데이터 개인 정보 보호 규정과 관련된 개선을 관리하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-104">Microsoft Compliance Manager can help you manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](../compliance/gdpr.md), [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="6c420-105">이 문서에서는 데이터 개인 정보 보호를 위해 이 도구를 사용하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-105">This article provides guidance on the use of this tool for data privacy purposes.</span></span>

>[!Note]
><span data-ttu-id="6c420-106">준수 관리자의 권장 사항을 준수 보장으로 해석하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="6c420-107">규정 환경에 따라 고객 제어의 효율성을 평가하고 유효성을 검사하는 것은 귀하의 전적인 의의입니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="6c420-108">이러한 서비스는 온라인 서비스 약관의 사용 [약관을 따라야 합니다.](https://go.microsoft.com/fwlink/?linkid=2108910)</span><span class="sxs-lookup"><span data-stu-id="6c420-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="6c420-109">보안 및 규정 준수에 대한 [Microsoft 365 라이선싱 지침 참조](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span><span class="sxs-lookup"><span data-stu-id="6c420-109">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span></span>
>

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="6c420-110">준수 관리자 시작</span><span class="sxs-lookup"><span data-stu-id="6c420-110">Getting started with Compliance Manager</span></span>

#### <a name="what-is-compliance-manager"></a><span data-ttu-id="6c420-111">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="6c420-111">What is Compliance Manager</span></span>

<span data-ttu-id="6c420-112">[준수 관리자는](../compliance/compliance-manager.md) Microsoft 클라우드 서비스와 관련된 규정 준수 활동을 관리하기 위한 Microsoft 365 규정 준수 센터의 워크플로 기반 위험 평가 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-112">[Compliance Manager](../compliance/compliance-manager.md) is a workflow-based risk assessment tool in the Microsoft 365 compliance center for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="6c420-113">준수 관리자는 Microsoft 365 또는 Azure AD(Azure Active Directory) 구독의 일부로 Microsoft 클라우드 서비스에 대한 공유 책임 모델 내에서 규정 준수를 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-113">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="6c420-114">**평가 사용 준비**</span><span class="sxs-lookup"><span data-stu-id="6c420-114">**Ready to use assessments**</span></span>

<span data-ttu-id="6c420-115">준수 관리자는 GDPR 및 [](../compliance/compliance-manager-assessments.md) HIPAA/HITECH와 같은 데이터 개인 정보 관련 규정에 맞춰진 평가를 작성하기 위한 미리 작성된 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-115">Compliance Manager provides pre-built templates for [building assessments](../compliance/compliance-manager-assessments.md) that are aligned to data privacy-related regulations, such as GDPR and HIPAA/HITECH.</span></span> <span data-ttu-id="6c420-116">템플릿에는 규정 요구 사항을 충족하기 위한 개선 조치를 취하는 데 도움이 되는 기본 제공 컨트롤 매핑이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-116">The templates have built-in control mapping to help you take improvement actions for meeting the regulation's requirements.</span></span> <span data-ttu-id="6c420-117">각 평가는 Microsoft에서 관리하는 컨트롤로 나타난 대상 서비스에 대한 각 규정 호출 컨트롤에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-117">Each assessment provides information about the controls each regulation calls for specific to the target service, broken out by controls you manage and controls Microsoft manages.</span></span> 

<span data-ttu-id="6c420-118">미리 작성된 템플릿을 사용하면 위험 평가를 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-118">Using a pre-built template helps you quickly get started with risk assessments.</span></span> <span data-ttu-id="6c420-119">준수 관리자를 사용하는 데 습관해지고 나면 자체 컨트롤 및 개선 작업을 추가하여 미리 작성된 템플릿을 사용자 지정하거나 조직의 요구에 맞게 사용자 지정 평가를 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-119">As you become more proficient in using Compliance Manager, you can customize a pre-built template by adding your own controls and improvement actions, or you can create your own custom assessments to suit your organization's needs.</span></span>

<span data-ttu-id="6c420-120">준수 관리자가 제공하는 평가 [템플릿의](../compliance/compliance-manager-templates-list.md) 전체 목록을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="6c420-120">View the [full list of assessment templates](../compliance/compliance-manager-templates-list.md) provided by Compliance Manager.</span></span>

<span data-ttu-id="6c420-121">**실시간 준수 점수**</span><span class="sxs-lookup"><span data-stu-id="6c420-121">**Real-time compliance score**</span></span>

<span data-ttu-id="6c420-122">준수 관리자는 컨트롤 내에서 권장 개선 작업을 완료하는 진행률을 측정하는 준수 점수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-122">Compliance Manager also provides you with a compliance score that measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="6c420-123">이 점수를 사용하여 진행 상황을 모니터링하고 잠재력을 기반으로 작업의 우선 순위를 지정하여 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-123">You can use this score to help monitor your progress and prioritize actions based on their potential to reduce risk.</span></span>

#### <a name="use-the-compliance-manager-quickstart-guide"></a><span data-ttu-id="6c420-124">준수 관리자 빠른 시작 가이드 사용</span><span class="sxs-lookup"><span data-stu-id="6c420-124">Use the Compliance Manager quickstart guide</span></span>

<span data-ttu-id="6c420-125">준수 [관리자 빠른 시작](../compliance/compliance-manager-quickstart.md) 가이드는 규정 준수 관리자로 작업하는 데 도움이 되는 주요 리소스에 대한 단계와 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-125">The [Compliance Manager quickstart](../compliance/compliance-manager-quickstart.md) guide provides graduated steps and links to key resources to help you work with Compliance Manager:</span></span>

- [<span data-ttu-id="6c420-126">첫 번째 방문: 준수 관리자에 익숙해지기</span><span class="sxs-lookup"><span data-stu-id="6c420-126">First visit: get familiar with Compliance Manager</span></span>](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - <span data-ttu-id="6c420-127">준수 관리자 대시보드 작업</span><span class="sxs-lookup"><span data-stu-id="6c420-127">Working with your Compliance Manager dashboard</span></span>
    - <span data-ttu-id="6c420-128">준수 점수 이해</span><span class="sxs-lookup"><span data-stu-id="6c420-128">Understanding your compliance score</span></span>
    - <span data-ttu-id="6c420-129">개선 작업 학습</span><span class="sxs-lookup"><span data-stu-id="6c420-129">Learning about improvement actions</span></span>
    - <span data-ttu-id="6c420-130">평가 및 템플릿 이해</span><span class="sxs-lookup"><span data-stu-id="6c420-130">Understanding assessments and templates</span></span>
- [<span data-ttu-id="6c420-131">Ramping up: Configure Compliance Manager to manage your compliance activities</span><span class="sxs-lookup"><span data-stu-id="6c420-131">Ramping up: configure Compliance Manager to manage your compliance activities</span></span>](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - <span data-ttu-id="6c420-132">첫 번째 평가 구축 및 관리</span><span class="sxs-lookup"><span data-stu-id="6c420-132">Building and managing your first assessment</span></span>
    - <span data-ttu-id="6c420-133">개선 작업에 대한 구현 및 테스트 작업 수행을 통해 평가의 컨트롤 완료</span><span class="sxs-lookup"><span data-stu-id="6c420-133">Performing implementation and testing work on improvement actions to complete controls in your assessments</span></span>
    - <span data-ttu-id="6c420-134">다양한 작업이 준수 점수에 미치는 영향 이해</span><span class="sxs-lookup"><span data-stu-id="6c420-134">Understanding how different actions impact your compliance score</span></span>
- [<span data-ttu-id="6c420-135">확장: 고급 기능을 사용하여 사용자 지정 요구 사항 충족</span><span class="sxs-lookup"><span data-stu-id="6c420-135">Scaling up: use advanced functionality to meet your custom needs</span></span>](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - <span data-ttu-id="6c420-136">비 Microsoft 365 제품을 추적하는 사용자 지정 평가 만들기</span><span class="sxs-lookup"><span data-stu-id="6c420-136">Creating your custom assessments to track non-Microsoft 365 products</span></span>
    - <span data-ttu-id="6c420-137">기존 템플릿을 수정하여 컨트롤 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="6c420-137">Modifying existing templates to add or remove controls</span></span>
    - <span data-ttu-id="6c420-138">개선 작업의 자동화된 테스트 설정</span><span class="sxs-lookup"><span data-stu-id="6c420-138">Setting up automated testing of improvement actions</span></span>

## <a name="how-your-compliance-score-is-calculated"></a><span data-ttu-id="6c420-139">규정 준수 점수 계산 방법</span><span class="sxs-lookup"><span data-stu-id="6c420-139">How your compliance score is calculated</span></span>

<span data-ttu-id="6c420-140">준수 점수는 Microsoft와 고객 관리 컨트롤 구현의 조합에 따라 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-140">Your compliance score is calculated based on a combination of Microsoft and customer-managed control implementations.</span></span> <span data-ttu-id="6c420-141">자세한 [설명은](../compliance/compliance-score-calculation.md) 준수 점수 계산을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-141">See [compliance score calculation](../compliance/compliance-score-calculation.md) for a detailed explanation.</span></span>

<span data-ttu-id="6c420-142">컨트롤은 필수인지 또는 사용자 지정 컨트롤인지와 예방용인지, 감지용인지 또는 시정용인지에 따라 점수 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-142">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="6c420-143">이러한 컨트롤은 다른 컨트롤을 상대로 구현하지 않을 위험을 총체적으로 나타 내포합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-143">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="6c420-144">준수 점수 계산 문서에 설명된 것 처럼 예방용 컨트롤은 감지용 컨트롤 및 수정 컨트롤보다 높은 점수를 얻게 되고 필수 컨트롤은 재량에 비해 높은 점수를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-144">As presented in the compliance score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>

<span data-ttu-id="6c420-145">준수 점수 관리자 UI는 이러한 매개 변수를 나열하지 않으며 이러한 매개 변수를 필터링하는 기능을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-145">The Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="6c420-146">그러나 준수 관리자에서 연결된 템플릿을 다운로드하면 결과 데이터 집합에 대부분의 규정에 대한 이러한 매개 변수가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-146">However, if you download the associated template from  Compliance Manager, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="6c420-147">기술 컨트롤의 경우 준수 관리자는 작업이 성공적으로 구현되고 테스트된 후 개선 작업 점수를 자동으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-147">For technical controls, Compliance Manager automatically updates the improvement action score once the action has been successfully implemented and tested.</span></span> <span data-ttu-id="6c420-148">작업 또는 설명서와 관련된 작업과 같은 기타 비기술 제어 작업은 점수가 점수에 계산되기 전에 구현된 것으로 수동으로 &mdash; &mdash; 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-148">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually as implemented before points count toward your score.</span></span>

<span data-ttu-id="6c420-149">또한 많은 사용자가 데이터 개인 정보 규정 준수가 아닌 다른 이유로 보존 레이블을 사용하는 등의 다른 목적에 대해 특정 개선 작업을 구현하고 있으므로 의도적인 준수 작업의 일부가 아닌 다른 목적으로 사용되어도 해당 기능을 사용할 때의 크레딧을 얻게 &mdash; &mdash; 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-149">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="6c420-150">준수 점수는 광범위한 규모의 개선을 추적하기 위한 상대적인 측정값으로 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-150">Your compliance score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="6c420-151">완벽한 점수를 따라야 하는 것은 아니며,</span><span class="sxs-lookup"><span data-stu-id="6c420-151">You should not pursue a perfect score.</span></span>

## <a name="additional-guidance"></a><span data-ttu-id="6c420-152">추가 안내</span><span class="sxs-lookup"><span data-stu-id="6c420-152">Additional guidance</span></span>

<span data-ttu-id="6c420-153">다음은 준수 관리자를 사용하여 데이터 개인 정보 규정 준수를 달성하는 데 도움이 되는 몇 가지 중요한 팁입니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-153">Here are a few important tips for using Compliance Manager to help you achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="6c420-154">각 데이터 개인 정보 규정에는 기술 제어, 문서 사양 및 운영, 프로세스 및 보고 요구 사항이 조합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-154">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="6c420-155">이러한 모든 작업은 개선 작업에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-155">All of these show up in the improvement actions.</span></span>

- <span data-ttu-id="6c420-156">개선 작업 보기를 관심 영역에 집중하기 위해 준수 관리자 관리자의 솔루션 탭에 있는 작업 유형별로 필터링할 수 있습니다.  준수 관리자 대시보드 [보기 필터링에 대해 자세히 알아보습니다.](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)</span><span class="sxs-lookup"><span data-stu-id="6c420-156">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Manager admin. Learn more about [filtering your Compliance Manager dashboard view](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).</span></span>

- <span data-ttu-id="6c420-157">준수 관리자에서 식별된 개선 작업의 상대적 중요도와 우선 순위는 조직에서 관리해야 한다고 결정한 데이터 개인 정보 보호 위험과 함께 더 광범위한 위험 검토의 일부로 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-157">The relative importance and priority of improvement actions identified in Compliance Manager should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span>

- <span data-ttu-id="6c420-158">여러 규제 요구 사항에 대한 개선 작업 집계가 있는 경우에도 GDPR, LGPD, CCPA 및 HIPAA-HITECH에 대한 규정 평가 템플릿을 선택하면 준수 관리자에 약 400개 개선 작업이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-158">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Manager.</span></span> <span data-ttu-id="6c420-159">이 긴 목록을 보다 효율적으로 활용하기 위해 개선 작업 필터를 사용하여 결과 집합을 보다 관리 가능한 목록으로 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-159">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="6c420-160">범주 필터는 논리적 그룹화로 개선 작업을 필터링하는 수단을 제공합니다. 이 전체 솔루션의 문서 추적, 방지, 보호, 보존 및 조사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-160">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span>

- <span data-ttu-id="6c420-161">개선 작업에 나열된 일부 컨트롤은 특정 규제 문서와 더 직접적으로 연결된 것으로 간주될 수 있는 반면, 다른 컨트롤은 규정 준수와 더 간접적으로 연결될 수 있으며, 여러 번은 단순히 권장되는 활동이나 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="6c420-161">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and many times are simply recommended activities or best practices.</span></span>