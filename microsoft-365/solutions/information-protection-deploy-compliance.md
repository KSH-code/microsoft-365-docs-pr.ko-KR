---
title: 준수 점수 및 준수 관리자를 사용 하 여 개선 작업 관리
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
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
ms.openlocfilehash: 5b1d465ad03a6aad5370f76b2cdde0657efd2f79
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521056"
---
# <a name="use-compliance-score-and-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="a17af-103">준수 점수 및 준수 관리자를 사용 하 여 개선 작업 관리</span><span class="sxs-lookup"><span data-stu-id="a17af-103">Use Compliance Score and Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="a17af-104">Microsoft 규정 준수 점수 및 준수 관리자를 함께 사용 하 여 유럽 연합의 [일반 데이터 보호 규정 (GDPR)](../compliance/gdpr.md), [캘리포니아 소비자 보호 Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (미국 의료 보험 개인 정보 취급 방침), LGPD (브라질 data Protection act)와 같은 데이터 개인 정보 규정에 관련 된 개선 사항을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-104">Microsoft Compliance Score and Compliance Manager can be used together to manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](../compliance/gdpr.md), [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="a17af-105">이 문서에서는 데이터 개인 정보 보호를 위해 이러한 도구를 사용 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-105">This article provides guidance on the use of these tools for data privacy purposes.</span></span>

![개선 작업을 관리 하는 준수 점수 및 준수 관리자](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-grid.png)

>[!Note]
><span data-ttu-id="a17af-107">준수 관리자에 제공 되는 고객 작업은 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-107">The customer actions provided in Compliance Manager are recommendations.</span></span> <span data-ttu-id="a17af-108">구현 하기 전에 규정 환경에서 이러한 권장 사항의 효과를 평가 하는 것은 사용자의 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-108">It is up to you to evaluate the effectiveness of these recommendations in your regulatory environments prior to implementation.</span></span> <span data-ttu-id="a17af-109">준수 관리자 권장 사항은 준수 보장으로 해석 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-109">Compliance Manager recommendations should not be interpreted as a guarantee of compliance.</span></span>
>

## <a name="planned-updates-for-compliance-score-and-compliance-manager"></a><span data-ttu-id="a17af-110">준수 점수 및 준수 관리자에 대 한 계획 된 업데이트</span><span class="sxs-lookup"><span data-stu-id="a17af-110">Planned updates for Compliance Score and Compliance Manager</span></span>

<span data-ttu-id="a17af-111">[준수 점수](../compliance/compliance-score.md) (현재 미리 보기)에는 [준수 관리자](../compliance/compliance-manager-overview.md)의 규정 (예: gdpr)에 대 한 대상 평가를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-111">[Compliance Score](../compliance/compliance-score.md) (currently in preview) requires adding your target assessments for a regulation (such as GDPR) from the [Compliance Manager](../compliance/compliance-manager-overview.md).</span></span> <span data-ttu-id="a17af-112">향후 릴리스에서는 준수 관리자의 대부분의 기능이 통합 준수 점수 환경으로 병합 되어 여러 도구를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-112">In a future release, much of the functionality in Compliance Manager will be merged into a unified Compliance Score experience, reducing the need for multiple tools.</span></span>

<span data-ttu-id="a17af-113">다음은 구독에 대 한 도구 이며, 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-113">Here are the tools for your subscription, which require you to sign-in:</span></span>

- [<span data-ttu-id="a17af-114">Microsoft 준수 관리 센터의 준수 점수</span><span class="sxs-lookup"><span data-stu-id="a17af-114">Compliance Score in the Microsoft Compliance admin center</span></span>](https://compliance.microsoft.com/compliancescore)
- [<span data-ttu-id="a17af-115">Microsoft 서비스 보안 포털의 준수 관리자</span><span class="sxs-lookup"><span data-stu-id="a17af-115">Compliance Manager in the Microsoft Services Trust Portal</span></span>](https://servicetrust.microsoft.com/ComplianceManager/V3)

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="a17af-116">준수 관리자 시작</span><span class="sxs-lookup"><span data-stu-id="a17af-116">Getting started with Compliance Manager</span></span> 

<span data-ttu-id="a17af-117">현재 미리 보기로 제공 되는 [준수 관리자](../compliance/working-with-compliance-manager.md) 는 microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 관리 하기 위한 Microsoft 서비스 신뢰 포털의 무료 워크플로 기반 위험 평가 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-117">[Compliance Manager](../compliance/working-with-compliance-manager.md) (currently in preview) is a free workflow-based risk assessment tool in the Microsoft Service Trust Portal for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="a17af-118">Microsoft 365 또는 Azure AD (Active Directory) 구독의 일부로, 준수 관리자는 Microsoft 클라우드 서비스에 대 한 공유 책임 모델 내에서 규정 준수를 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-118">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="a17af-119">준수 센터의 **준수 점수** 페이지에서 전반적인 준수 점수를 확인 하 고 기타 다양 한 기능을 수행할 수 있지만, 먼저 서비스 트러스트 포털을 통해 준수 관리자를 사용 하 여 데이터 개인 정보 규정에 대 한 평가를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-119">While you can view your overall compliance score and perform a number of other functions in the Compliance center's **Compliance Score** page, you need to use Compliance Manager through the Services Trust Portal to first configure assessments for your data privacy regulations.</span></span> <span data-ttu-id="a17af-120">이러한 평가의 데이터는 추가 보기 및 필터링을 위해 준수 점수에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-120">Data from these assessments will then show up in Compliance Score for further viewing and filtering.</span></span> 

<span data-ttu-id="a17af-121">준수 관리자 인터페이스를 사용 하 여 하나 이상의 데이터 개인 정보 관련 규정 템플릿을 선택 하 고 그룹화 하 여 해당 집합에서 필요한 향상 작업을 평가 하 고 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-121">Using the Compliance Manager interface, you can select one or more data privacy-related regulation templates and group them to assess and track required improvement actions across the set.</span></span> <span data-ttu-id="a17af-122">또한 Microsoft와 고객 관리 되는 컨트롤과 구분 하 여 대상 서비스에 대 한 각 규정 호출 컨트롤에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-122">You can also view information about the controls each regulation calls for specific to the target service, separated by Microsoft vs. customer-managed controls.</span></span>

<span data-ttu-id="a17af-123">여기에서 선택한 평가 및 개선 상태는 준수 관리자의 초기 설정 중요성을 강조 하는 Microsoft 준수 센터의 준수 점수에도 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-123">Assessments and improvement status selected here also appear in Compliance Score in the Microsoft Compliance Center, which emphasize the importance of your initial setup in Compliance Manager.</span></span> <span data-ttu-id="a17af-124">이러한 관계는 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-124">These relationships are shown in this figure.</span></span>
 
![Microsoft 준수 센터의 준수 점수 관계](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-ui.png)

<span data-ttu-id="a17af-126">시작 하는 데 도움이 되는 주요 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-126">Here are the key steps to help you get started.</span></span>

### <a name="1-assessment-templates"></a><span data-ttu-id="a17af-127">1. 평가 템플릿</span><span class="sxs-lookup"><span data-stu-id="a17af-127">1. Assessment templates</span></span>

<span data-ttu-id="a17af-128">준수 관리자의 첫 번째 단계는 관심 있는 데이터 개인 정보 규정에 구체적인 평가를 추가 하 고 정의 된 "데이터 개인 정보 규정" 그룹에 포함 시키는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-128">From the Compliance Manager, the first step is to add assessments specific to the data privacy regulations of interest and include them in a defined "Data Privacy Regulations" group.</span></span>

<span data-ttu-id="a17af-129">[그룹](../compliance/working-with-compliance-manager.md#groups) 은 평가를 구성 하 고, 동일한 또는 관련 고객 관리 컨트롤이 있는 평가 간에 일반 정보 및 워크플로 작업을 공유 하는 데 사용할 수 있는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-129">[Groups](../compliance/working-with-compliance-manager.md#groups) are containers that allow you to organize Assessments and share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span> <span data-ttu-id="a17af-130">같은 그룹의 서로 다른 두 평가에서 고객 관리 되는 컨트롤을 공유 하는 경우 컨트롤의 구현 세부 정보, 테스트 및 상태가 그룹의 다른 평가에서 같은 컨트롤과 자동으로 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-130">When two different Assessments in the same group share customer-managed control, the completion of implementation details, testing, and status for the control automatically synchronize to the same control in any other Assessment in the Group.</span></span> <span data-ttu-id="a17af-131">이렇게 하면 그룹 전체에서 각 컨트롤에 대해 할당 된 작업 항목이 통합 되 고 복제 작업이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-131">This unifies the assigned Action Items for each control across the group and reduces duplicating work.</span></span> 

<span data-ttu-id="a17af-132">그룹을 사용 하 여 구성 하는 방법도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-132">You can also choose to use groups to organize.</span></span> <span data-ttu-id="a17af-133">규정 준수 작업을 구성 하는 데 도움이 되는 연도, 영역, 준수 표준 또는 기타 그룹화 별 평가.</span><span class="sxs-lookup"><span data-stu-id="a17af-133">Assessments by year, area, compliance standard, or other groupings to help organize your compliance work.</span></span>


### <a name="2-action-items"></a><span data-ttu-id="a17af-134">2. 작업 항목</span><span class="sxs-lookup"><span data-stu-id="a17af-134">2. Action items</span></span>

<span data-ttu-id="a17af-135">평가를 추가한 후에는 각 그룹 또는 개별 규정에 해당 하는 작업 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-135">Once the assessments have been added, you can view Action Items specific to each group or individual regulation:</span></span>

- <span data-ttu-id="a17af-136">**향상 작업 목록**</span><span class="sxs-lookup"><span data-stu-id="a17af-136">**Improvement action list.**</span></span> <span data-ttu-id="a17af-137">작업 항목 목록으로 이동 하 여 그룹에 포함 된 규정 전반에 걸쳐 있는 개선 작업을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-137">Navigate to the Action Items list and view the improvement actions associated across the regulations included in the group.</span></span> <span data-ttu-id="a17af-138">대부분의 작업 범위는 하나의 목록 항목이 여러 규정을 나타낼 수 있도록 규정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-138">Many actions span regulations so a single list item may represent multiple regulations.</span></span> 
 
- <span data-ttu-id="a17af-139">**향상 작업 필터링.**</span><span class="sxs-lookup"><span data-stu-id="a17af-139">**Improvement action filtering.**</span></span> <span data-ttu-id="a17af-140">대부분의 데이터 개인 정보 보호 규정 및 규정 그룹의 경우 향상 작업 목록이 매우 커질 수 있으므로 필터 드롭다운을 사용 하 여 목록을 필터링 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-140">For many data privacy regulations and groups of regulations, the list of improvement actions can be quite large, so consider filtering the list using the filter drop down.</span></span> <span data-ttu-id="a17af-141">예를 들어 "기술 제어"를 선택 하는 경우 많은 작업이 준수 관리자에도 문서화 되는 다양 한 측면에서 관리 작업과 관련 되어 있기 때문에 조직에서 기술 구현이 포함 된 것으로 목록이 축소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-141">For example, if you select "technical controls", the list will be reduced to just those which have a technical implementation in the organization, as many of the actions are related to administrative operations in various aspects of the business which are also documented in Compliance Manager.</span></span> <span data-ttu-id="a17af-142">이 문서에서는 기술 제어에 대해 중점적으로 설명 하므로이 필터링 방식을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-142">In this article, we will focus on technical controls, so this filtering approach is recommended.</span></span>
 
- <span data-ttu-id="a17af-143">**추가 정보 및 검토**</span><span class="sxs-lookup"><span data-stu-id="a17af-143">**Additional information and review.**</span></span> <span data-ttu-id="a17af-144">각 작업에 대해 **자세한 내용을**보려면 링크를 클릭 하 고, 권장 작업에 대해 자세히 설명 하거나, **검토**를 통해 다음을 수행할 수 있는 양식을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-144">For each action, you can click on the link to **Read More**, which tells you more about the recommended activity, or **Review**, which opens a form allowing you to do the following:</span></span>
 
   - <span data-ttu-id="a17af-145">조직의 다른 사용자에 게 작업을 할당 하 여 관리</span><span class="sxs-lookup"><span data-stu-id="a17af-145">Assign the action to a someone in your organization to manage</span></span>
   - <span data-ttu-id="a17af-146">작업 주소 지정과 관련 된 문서 관리</span><span class="sxs-lookup"><span data-stu-id="a17af-146">Manage documents related to addressing the action</span></span>
   - <span data-ttu-id="a17af-147">항목의 상태 지정</span><span class="sxs-lookup"><span data-stu-id="a17af-147">Specify status for the item</span></span>
   - <span data-ttu-id="a17af-148">구현 및 테스트 날짜 지정</span><span class="sxs-lookup"><span data-stu-id="a17af-148">Specify implementation and test dates</span></span>
   - <span data-ttu-id="a17af-149">주제 작업에 대 한 추가 정보, 구현 메모 및 테스트 계획 메모를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-149">Record additional information, implementation notes, and test plan notes for the subject action</span></span>
  
- <span data-ttu-id="a17af-150">**범위가 벗어나 해당 되지 않는 항목**</span><span class="sxs-lookup"><span data-stu-id="a17af-150">**Non-applicable items as out-of-scope.**</span></span> <span data-ttu-id="a17af-151">작업 항목 목록에 포함 된 일부 개선 작업은 계획 된 구현에 적용 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-151">Some improvement actions included in the Action Items list might not apply to your planned implementation.</span></span> <span data-ttu-id="a17af-152">규정 준수 관리자의 범위를 벗어나 해당 작업 및 해당 증거를 준수 점수 값 계산에서 제거 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-152">You can specify that they are out of scope in Compliance Manager and remove the action and its evidence from the calculation of the compliance score value.</span></span> 

<span data-ttu-id="a17af-153">예를 들어 조직에서 Microsoft 관리 키를 사용 하기로 선택한 경우에는 고객 키를 사용 하는 권장 사항을 배포에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-153">For example, if your organization has elected to use Microsoft Managed Key", a recommendation to Use Customer Key is not applicable to your deployment.</span></span> <span data-ttu-id="a17af-154">이 경우 조직에서 해당 규정 템플릿에 대 한 **제어 작업** 의 **범위 내에 없는** 것으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-154">In this case, your organization would mark it as **Not in scope** in the **Control Actions** for the applicable regulatory template.</span></span>
 
### <a name="3-controls-info"></a><span data-ttu-id="a17af-155">3. 컨트롤 정보</span><span class="sxs-lookup"><span data-stu-id="a17af-155">3. Controls info</span></span>

<span data-ttu-id="a17af-156">평가 별 보기의 경우 각 평가 그룹의 [컨트롤 정보](../compliance/compliance-manager-overview.md#controls) 를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-156">For an assessment-specific view, view the [Controls Info](../compliance/compliance-manager-overview.md#controls) for each assessment group.</span></span> <span data-ttu-id="a17af-157">이는 기술적 컨트롤별 보기를 제공 하는 작업 항목 목록과는 다른, 평가 관련 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-157">This provides an assessment-specific view, which is difference than the Action Items list, which provides a technical control-specific view.</span></span>
 
![제어 항목에 대 한 평가의 관계](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-control.png)

<span data-ttu-id="a17af-159">**제어 정보** 목록으로 이동 하 여 해당 규정에 대 한 범위 내 서비스의 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-159">Navigate to the **Controls Info** list and view the list of in-scope services for the regulation in question.</span></span> 
 
<span data-ttu-id="a17af-160">규정 관련 컨트롤 그룹화 각 서비스 영역에 대해 control area에서 제공 하는 작업을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-160">Regulation-specific control groupings list the actions provided by control area for each service area.</span></span> <span data-ttu-id="a17af-161">각 작업 집합에 대해 준수 관리자는 작업에 대 한 자세한 정보를 제공 하 고, 제어 방식을 선택 하는 데 도움이 되는 검토 옵션을 제시 하거나 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-161">For each set of actions, the Compliance Manager provides more information on the action and may suggest or provide review options to assist the organization in choosing a control approach.</span></span>
 
<span data-ttu-id="a17af-162">이 인터페이스는 기술 작업과 관련 된 세부 정보 및 해당 작업과 관련 된 규정에 대 한 추가 컨텍스트를 볼 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-162">Note that this interface provides the capability to view details specific to the technical action, together with the status of actions related to the control, and supplemental context about the regulations to which the action is related.</span></span>

### <a name="4-template-download"></a><span data-ttu-id="a17af-163">4. 서식 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="a17af-163">4. Template download</span></span>

<span data-ttu-id="a17af-164">스프레드시트 기반 규정 분석에 익숙한 다른 방법은 서식 파일 목록을 사용 하 여 각각의 각 평가에 대 한 템플릿을 다운로드 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-164">For those more familiar with spreadsheet-based regulatory analysis, another approach is to download the template for each respective assessment using the Templates listing.</span></span> <span data-ttu-id="a17af-165">다운로드 한 서식 파일에는 각 서식 파일의 규정 및 기술 제어 정보를 모두 나열 하 고, 특정 역할에 따라 비즈니스 관련 보기를 탐색/필터링 하 고 생성 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-165">The downloaded templates list both the regulatory as well as technical control information for each template and may be easier for certain roles to navigate/filter and to generate business-specific views.</span></span>
 
<span data-ttu-id="a17af-166">**서식 파일 추가**를 사용 하 여 기존 서식 파일을 기반으로 조직에 대해 사용자 지정 된 새 서식 파일을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-166">You can also add a new template customized for your organization based on an existing template, using **Add Template**.</span></span> <span data-ttu-id="a17af-167">이렇게 하려면 원하는 서식 파일 (예: HIPAA/HITECH)을 다운로드 한 다음 목적으로 수정 하 고 준수 관리자 도구에 다시 업로드 해야 하며, 이제 평가를 수행 하 고 다른 서식 파일 및 평가와 마찬가지로 전체 준수 관리자 및 규정 준수 점수 매기기 도구 모음에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-167">This requires that you download a template of choice (such as HIPAA/HITECH)), then modify it for your purposes and upload back into the Compliance Manager tool, where it will now drive assessments and scoring similar to other templates and assessments as part of the overall Compliance Manager and Compliance Score toolset.</span></span>
 
>[!Tip]
><span data-ttu-id="a17af-168">많은 수의 규정 또는 중복 된 개선 작업을 처리 하는 경우 각각의 각 템플릿을 다운로드 하 고 데이터 집합을 결합 하 여 조직에 적용 되지 않는 개선 작업 또는 컨트롤 유형을 제거 하 고 다시 업로드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-168">if dealing with a large number of regulations or overlapping improvement actions, consider downloading each respective template and combining the data sets, removing improvement actions or control types that do not apply to your organization, and re-uploading.</span></span> <span data-ttu-id="a17af-169">모든 컨트롤 정보 섹션을 탐색 하 고 범위를 벗어나 표시 하는 것 보다이 방법이 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-169">This may be easier than navigating every control info section and marking each as out of scope.</span></span>
>

## <a name="compliance-score"></a><span data-ttu-id="a17af-170">준수 점수</span><span class="sxs-lookup"><span data-stu-id="a17af-170">Compliance Score</span></span>

<span data-ttu-id="a17af-171">규정 준수 관리자에서 평가 및 검토 사양을 수행한 후에는 [준수 점수](../compliance/compliance-score.md) 도구로 이동 하 여 점수 및 조각화를 검토 하 고 데이터를 제어 영역에 포함 하 여 더 자세히 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-171">Once the assessments and review specifications are performed in Compliance Manager, you can now go to the [Compliance Score](../compliance/compliance-score.md) tool and review the score and slice and dice the data further, including by control area.</span></span>

<span data-ttu-id="a17af-172">Microsoft 365 준수 관리 센터의 준수 점수 도구는 준수 관리자 및 다양 한 Microsoft 365 서비스에서 얻은 준수 데이터를 검토 하 고 필터링 하는 여러 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-172">The Compliance Score tool in the Microsoft 365 Compliance admin center provides several approaches to review and filter compliance data obtained from Compliance Manager and various Microsoft 365 services.</span></span> <span data-ttu-id="a17af-173">이 도구는 다양 한 구성 설정이 구현 되 고 Microsoft 보안 점수를 공유 하 여 다양 한 개선 작업이 두 가지 점수에 모두 표시 되도록 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-173">This tool is automatically updated when various configuration settings are implemented and shares signals with the Microsoft Secure Score so that many improvement actions will show up in both scores.</span></span> 
 
<span data-ttu-id="a17af-174">준수 점수는 다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-174">The Compliance Score provides:</span></span>

- <span data-ttu-id="a17af-175">수집 된 점수가 Microsoft 및 고객 관리 컨트롤로 분류 됨</span><span class="sxs-lookup"><span data-stu-id="a17af-175">A collected score, broken down by Microsoft and customer-managed controls</span></span>
- <span data-ttu-id="a17af-176">개선 작업 및 완료 상태 롤업</span><span class="sxs-lookup"><span data-stu-id="a17af-176">A rollup of improvement actions and completion status</span></span>
- <span data-ttu-id="a17af-177">점수에 영향을 주는 Microsoft 365 솔루션 목록</span><span class="sxs-lookup"><span data-stu-id="a17af-177">A listing of Microsoft 365 solutions impacting your score</span></span>

### <a name="how-the-compliance-score-gets-calculated"></a><span data-ttu-id="a17af-178">준수 점수가 계산 되는 방식</span><span class="sxs-lookup"><span data-stu-id="a17af-178">How the compliance score gets calculated</span></span>

<span data-ttu-id="a17af-179">또한 점수는 microsoft [규정 준수 점수 계산 문서](../compliance/compliance-score-methodology.md)에 자세히 설명 된 대로 microsoft 및 고객 관리 제어 구현의 조합에 따라 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-179">In short, the score is calculated based on a combination of Microsoft and customer-managed control implementations, as explained in more detail in the [Microsoft Compliance Score calculation article](../compliance/compliance-score-methodology.md).</span></span>

<span data-ttu-id="a17af-180">컨트롤이 필수 인지 아니면 임의 인지에 따라 점수 값이 할당 되 고 사용자가 예방적이 든 상관 없이 예방용 인지 인지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-180">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="a17af-181">이는 다른 컨트롤을 기준으로이를 구현 하지 않을 위험을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-181">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="a17af-182">Microsoft 규정 준수 점수 계산 문서에 나와 있는 것 처럼 예방적 컨트롤은 예방용 인지 보다 더 높은 점수를 얻게 되며, 필수 컨트롤은 임의의 것 보다 더 높은 점수를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-182">As presented in the Microsoft Compliance Score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>
 
<span data-ttu-id="a17af-183">준수 점수 관리자 UI에는 이러한 매개 변수가 나열 되지 않으며,이를 통해 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-183">Note that the Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="a17af-184">그러나 준수 관리자 도구에서 연결 된 서식 파일을 다운로드 하는 경우 결과 데이터 집합에는 대부분의 규정에 해당 하는 매개 변수가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-184">However, if you download the associated template from the Compliance Manager tool, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="a17af-185">기술 제어의 경우 규정 준수 점수는 관련 기능이 활성화 되 면 향상 된 개선 작업 점수를 자동으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-185">For technical controls, Compliance Score will automatically update the improvement action score once the related feature is activated.</span></span> <span data-ttu-id="a17af-186">&mdash;작동 하거나 설명서와 관련 된 기타 기술 없는 제어 작업은 &mdash; 서비스 트러스트 포털의 준수 관리자 도구에서 수동으로 기록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-186">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually in the Compliance Manager tool on the Services Trust Portal.</span></span> 

<span data-ttu-id="a17af-187">또한 &mdash; 데이터 개인 정보 규정 준수 이외의 이유로 보존 레이블을 사용 하 여 다른 용도로도 사용 하는 경우에는 해당 기능을 사용 하는 것이 좋지만 &mdash; , 의도적인 규정 준수 작업의 일부가 아닌 경우에는 다른 목적에 대 한 특정 향상 작업을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-187">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="a17af-188">규정 준수 점수는 광범위 한 규모의 개선을 추적 하기 위한 상대 수단으로 간주 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-188">Your Compliance Score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="a17af-189">완벽 한 점수를가지고 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-189">You should not pursue a perfect score.</span></span> 

### <a name="additional-guidance"></a><span data-ttu-id="a17af-190">추가 안내</span><span class="sxs-lookup"><span data-stu-id="a17af-190">Additional guidance</span></span>

<span data-ttu-id="a17af-191">다음은 준수 점수 및 준수 관리자를 사용 하 여 데이터 개인 정보 규정 준수를 달성할 수 있도록 하는 몇 가지 중요 한 팁입니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-191">Here are a few important tips for the use of Compliance Score and Compliance Manager for you to achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="a17af-192">각 데이터 개인 정보 규정에는 기술 컨트롤, 문서 사양, 운영, 프로세스 및 보고 요구 사항의 조합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-192">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="a17af-193">이러한 모든 기능을 향상 작업에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-193">All of these show up in the improvement actions.</span></span> 

- <span data-ttu-id="a17af-194">이 문서에서는 준수 관리자 및 준수 점수의 데이터 개인 정보 보호를 위해 지정 된 기술 컨트롤의 하위 집합에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-194">This article focuses on a subset of the technical controls specified for data privacy in Compliance Manager and Compliance Score.</span></span> <span data-ttu-id="a17af-195">기술 외 관리 컨트롤에 대 한 자세한 내용은 준수 관리자 도구 및 [설명서](../compliance/compliance-score.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a17af-195">Refer to the Compliance Manager tool and [documentation](../compliance/compliance-score.md) for more information on non-technical administrative controls.</span></span>

- <span data-ttu-id="a17af-196">해당 영역에 개선 작업 보기를 집중 시키려면 준수 점수 관리자의 **솔루션** 탭에서 작업 유형별로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-196">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Score admin.</span></span>

- <span data-ttu-id="a17af-197">규정 준수 점수에 명시 된 개선 작업의 상대적 중요도와 우선 순위는 조직에서 관리 해야 하는 데이터 개인 정보 위험과 함께 광범위 한 위험 검토의 일부로 간주 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-197">The relative importance and priority of improvement actions identified in Compliance Score should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span> 

- <span data-ttu-id="a17af-198">전역 조직인 경우 여러 데이터 개인 정보 규정 템플릿을 준수 관리자에 게 평가로 추가 하면 규정 준수 점수가 각 향상 작업에 대 한 필드 목록에서 적용 가능한 각 항목을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-198">If you are a global organization and you add multiple data privacy regulation templates into Compliance Manager as Assessments, Compliance Score will combine each applicable one in a field listing for each improvement action.</span></span>
 
- <span data-ttu-id="a17af-199">여러 규정 요구 사항에 대 한 향상 된 작업 집계를 사용 하는 경우에도 GDPR, LGPD, CCPA 및 HIPAA-HITECH에 대 한 규정 평가 템플릿이 선택 되는 경우, 대부분의 400 개선 작업이 준수 점수에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-199">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Score.</span></span> <span data-ttu-id="a17af-200">이 긴 목록을 보다 효율적으로 활용 하려면 향상 작업 필터를 사용 하 여 결과 집합을 보다 쉽게 관리할 수 있는 목록으로 줄이십시오.</span><span class="sxs-lookup"><span data-stu-id="a17af-200">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="a17af-201">Categories filter는이 전체 솔루션의 추적, 방지, 보호, 보존 및 조사를 수행 하는 논리적 그룹화를 통해 향상 작업을 필터링 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-201">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span> 

- <span data-ttu-id="a17af-202">향상 작업에 나열 된 일부 컨트롤은 특정 규제 문서에 보다 직접적으로 연결 될 수 있는 반면, 다른 컨트롤은 규제의 스피릿와 간접적으로 더 많이 연결 될 수 있으며, 그래도 수행 해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17af-202">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and are many times just things you should consider doing anyway.</span></span>

