---
title: Microsoft 규정 준수 점수
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
description: Microsoft 규정 준수 점수는 조직이 위험 평가를 간소화 하 고 자동화 하는 데 도움이 되며, 위험을 해결 하기 위한 권장 조치를 제시 합니다.
ms.openlocfilehash: dff5e6c057df37c076e328d5203a1eb4e4b3207a
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635116"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="0b34d-103">Microsoft 준수 점수 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="0b34d-103">Microsoft Compliance Score (Preview)</span></span>

<span data-ttu-id="0b34d-104">Microsoft 규정 준수 점수가 규정 준수를 관리 하 고 사용자에 게 친숙 한 환경을 통해 규정 준수 위험을 줄이는 방식을 단순화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-104">Microsoft Compliance Score helps to simplify the way you manage compliance and reduce compliance risks through a user-friendly experience.</span></span> <span data-ttu-id="0b34d-105">이제 [Microsoft 365 준수 센터](microsoft-365-compliance-center.md)의 공개 미리 보기에 준수 점수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-105">Compliance Score is now available for public preview in the  [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>

<span data-ttu-id="0b34d-106">**이 문서의 내용** 이 문서를 읽으면 규정 준수 점수가 무엇 이며, 조직에 맞게 설정 하는 방법을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-106">**In this article:** Read this article to understand what Compliance Score is and how to set it up for your organization.</span></span>

<span data-ttu-id="0b34d-107">**업데이트에 대해 알아봅니다.** 준수 점수 [릴리스 정보](compliance-score-release-notes.md) 를 참조 하 여 미리 보기 버전의 준수 점수와 관련 된 새로운 기능과 알려진 문제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-107">**Learn about updates:** Go to the [Compliance Score release notes](compliance-score-release-notes.md) to see what's new and known issues with the preview version of Compliance Score.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="0b34d-108">준수 점수 란?</span><span class="sxs-lookup"><span data-stu-id="0b34d-108">What is Compliance Score</span></span>

<span data-ttu-id="0b34d-109">Microsoft 준수 점수는 조직의 규정 준수 상태를 이해 하는 데 도움이 되는 Microsoft 365 준수 센터의 미리 보기 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-109">Microsoft Compliance Score is a preview feature in the Microsoft 365 compliance center to help you understand your organization’s compliance posture.</span></span> <span data-ttu-id="0b34d-110">데이터 보호 및 규정 표준에 대 한 위험을 줄이는 데 도움이 되는 작업 완료의 진행 상태를 측정 하는 위험 기반 점수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-110">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="0b34d-111">규정 준수 점수를 모든 위험 평가를 추적 하는 도구로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-111">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="0b34d-112">공통 도구를 통해 위험 평가를 효율적으로 완료 하는 데 도움이 되는 워크플로 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-112">It provides workflow capabilities to help you efficiently complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="0b34d-113">현재 [준수 관리자](compliance-manager-overview.md)를 사용 하는 경우 준수 점수가 보다 간단 하 고 사용자에 게 친숙 한 디자인을 갖춘 독립 실행형 기능 이므로 더 쉽게 준수를 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-113">If you currently use [Compliance Manager](compliance-manager-overview.md), you’ll notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help you manage compliance more easily.</span></span> 

<span data-ttu-id="0b34d-114">기본 준수 점수 페이지는 사용자 지정 대시보드입니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-114">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="0b34d-115">현재 점수를 표시 하 고, 주의 해야 하는 사항을 확인 하 고, 점수를 높이기 위한 작업을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-115">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="0b34d-116">준수 점수 대시보드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-116">Your Compliance Score dashboard will look like this:</span></span>

<span data-ttu-id="0b34d-117">![준수 점수-대시보드](../media/compliance-score-dashboard.png "준수 점수 대시보드")</span><span class="sxs-lookup"><span data-stu-id="0b34d-117">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="0b34d-118">간소화 된 준수 관리</span><span class="sxs-lookup"><span data-stu-id="0b34d-118">Simplified compliance management</span></span>

<span data-ttu-id="0b34d-119">규정 준수 점수가 다음을 제공 하 여 준수 관리를 간소화 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-119">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="0b34d-120">**지속적인 평가**: Microsoft 365 환경을 자동으로 검색 하 여 시스템에서 데이터 보호 컨트롤의 효율성을 검색 하 고 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-120">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="0b34d-121">**권장 작업**: 점수를 최대화 하는 컨트롤을 구현 하는 방법에 대 한 권장 사항 및 단계별 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-121">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="0b34d-122">**기본 제공 컨트롤 매핑**: 기본 제공 되는 일반 컨트롤 프레임 워크를 제공 하 여 진화 하는 준수 가로를 유지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-122">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="0b34d-123">규정 준수 점수가 특정 표준 또는 규정에 대 한 조직 준수를 절대 측정 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-123">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="0b34d-124">개인 데이터 및 개별 개인 정보에 대 한 위험을 줄일 수 있는 컨트롤을 채택한 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-124">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="0b34d-125">준수 점수 및 준수 관리자의 권장 사항은 준수 보장으로 해석 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-125">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="0b34d-126">이 서비스는 현재 미리 볼 수 있으며 [온라인 서비스 약관](https://go.microsoft.com/fwlink/?linkid=2108910)의 사용 약관에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-126">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="0b34d-127">준수 관리자와의 관계</span><span class="sxs-lookup"><span data-stu-id="0b34d-127">Relationship to Compliance Manager</span></span>

<span data-ttu-id="0b34d-128">준수 점수가 규정 준수 관리자의 단순화 된 버전으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-128">Think of Compliance Score as a simplified version of Compliance Manager.</span></span> <span data-ttu-id="0b34d-129">두 가지가 서로 다른 통합 도구로 존재 하지만, 규정 준수 점수를 통해 전반적인 준수 상태를 보다 쉽게 모니터링 하 고 단계를 수행 하 여이를 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-129">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="0b34d-130">준수 점수가 준수 관리자와 동일한 백엔드를 공유 하므로 준수 관리자에 게 이미 있을 수 있는 모든 데이터는 준수 점수에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-130">Compliance Score shares the same backend with Compliance Manager, so any data you may already have in Compliance Manager will show in Compliance Score.</span></span>

<span data-ttu-id="0b34d-131">공개 미리 보기 중 일부 기능은 규정 검사 관리 및 템플릿 만들기와 같은 준수 관리자 에게만 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-131">During public preview, some functionality remains solely in Compliance Manager, such as managing assessments and creating templates.</span></span> <span data-ttu-id="0b34d-132">준수 점수의 모든 준수 관리 활동을 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-132">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="0b34d-133">준수 관리자가 처리 한 함수에 대 한 자세한 내용은 해당 도구에 대 한 안내가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-133">When you come to functions handled by Compliance Manager, you will be guided to that tool.</span></span> <span data-ttu-id="0b34d-134">따라서이 설명서 중 일부는 준수 관리자 항목으로 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-134">For that reason, some of this documentation directs you to Compliance Manager topics.</span></span>

<span data-ttu-id="0b34d-135">준수 [점수 릴리스 정보](compliance-score-release-notes.md)에서 준수 점수와 준수 관리자 간의 관계에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0b34d-135">Learn more about the relationship between Compliance Score and Compliance Manager in the [Compliance Score release notes](compliance-score-release-notes.md).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="0b34d-136">점수 이해</span><span class="sxs-lookup"><span data-stu-id="0b34d-136">Understanding your score</span></span>

<span data-ttu-id="0b34d-137">준수 점수가 Microsoft 365 데이터 보호 기준을 기반으로 초기 점수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-137">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="0b34d-138">이 기준은 일반적인 업계 규정 및 표준을 포함 하는 컨트롤 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-138">This baseline is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="0b34d-139">이 점수는 준수 상태를 평가 하는 데 적합 한 출발점 이지만 조직과 보다 관련성이 높은 평가를 추가 하는 경우 준수 점수가 더욱 강력해 집니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-139">While this score is a good starting point for assessing your compliance posture, Compliance Score becomes more powerful once you add assessments that are more relevant to your organization.</span></span>

<span data-ttu-id="0b34d-140">예를 들어 조직이 금융 서비스 업계에 속하는 경우 FFIEC 평가를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-140">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="0b34d-141">조직이 의료 업계에 속하는 경우 HIPAA/HITECH 평가를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-141">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span> <span data-ttu-id="0b34d-142">[준수 관리자에서 평가를 추가](working-with-compliance-manager.md#assessments)하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-142">Learn how to [add assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

<span data-ttu-id="0b34d-143">[준수 점수가 계산 되 고 지속적으로 모니터링 되는 방식](compliance-score-methodology.md)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0b34d-143">Learn more about [how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>


## <a name="key-components-controls-assessments-templates-groups"></a><span data-ttu-id="0b34d-144">주요 구성 요소: 컨트롤, 평가, 템플릿, 그룹</span><span class="sxs-lookup"><span data-stu-id="0b34d-144">Key components: controls, assessments, templates, groups</span></span>

<span data-ttu-id="0b34d-145">규정 준수 점수에서는 준수 작업을 관리 하는 데 도움이 되는 여러 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-145">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="0b34d-146">규정 준수 점수를 사용 하 여 준수 작업을 할당, 테스트 및 모니터링 하는 경우 이러한 주요 구성 요소에 대 한 기본적인 이해가 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-146">As you use Compliance Score to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of these key components.</span></span> <span data-ttu-id="0b34d-147">다음 다이어그램은 이러한 항목 간의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-147">This diagram shows the relationships among them:</span></span>

<span data-ttu-id="0b34d-148">![준수 관리자 버전 3의 관계](../media/compliance-manager-relationships.png "규정 준수 점수 구성 요소")</span><span class="sxs-lookup"><span data-stu-id="0b34d-148">![Relationships in Compliance Manager Version 3](../media/compliance-manager-relationships.png "Compliance Score components")</span></span>

### <a name="controls"></a><span data-ttu-id="0b34d-149">컨트롤</span><span class="sxs-lookup"><span data-stu-id="0b34d-149">Controls</span></span>

<span data-ttu-id="0b34d-150">제어는 규정, 표준 또는 내부 정책의 특정 요구 사항을 충족 하기 위해 시스템 구성, 조직 프로세스 및 사용자 책임을 평가 하 고 관리 하는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-150">A control defines how you assess and manage system configuration, organizational process, and people accountability to meet a specific requirement of a regulation, standard, or internal policy.</span></span>

<span data-ttu-id="0b34d-151">규정 준수 점수에는 다음과 같은 두 가지 유형의 컨트롤이 추적 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-151">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="0b34d-152">**Microsoft 관리 되는 컨트롤**: microsoft 클라우드 서비스에 대 한 컨트롤로, 마이크로소프트에서 구현를 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-152">**Microsoft-managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="0b34d-153">**고객 관리 컨트롤**: 조직에서 관리 하는 컨트롤 (구현 담당)</span><span class="sxs-lookup"><span data-stu-id="0b34d-153">**Customer-managed controls**: controls managed by your organization, which you are responsible for implementing</span></span>
 
### <a name="assessments"></a><span data-ttu-id="0b34d-154">평가가</span><span class="sxs-lookup"><span data-stu-id="0b34d-154">Assessments</span></span>

<span data-ttu-id="0b34d-155">평가는 조직의 점수 매기기 프로세스를 시작 하는 서식 파일을 평가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-155">An assessment is an evaluation of a template that initiates the scoring process for your organization.</span></span> <span data-ttu-id="0b34d-156">평가는 표준, 규정 또는 법률 요구 사항을 충족 하는 데 필요한 작업을 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-156">Assessments group the actions necessary to meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="0b34d-157">예를 들어 내 모든 작업을 완료 하면 Office 365 설정이 ISO 27001 요구 사항을 충족 하는 줄에 표시 된다는 평가가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-157">For example, you may have an assessment that, when you complete all actions within it, brings your Office 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="0b34d-158">기본적으로 규정 준수 점수는 조직에 Microsoft 365 데이터 보호 기준을 기반으로 하는 평가를 제공 하며, 데이터 보호 및 규정 준수 위험을 줄이는 데 권장 됩니다 ([자세한 정보](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span><span class="sxs-lookup"><span data-stu-id="0b34d-158">By default, Compliance Score provides your organization with an assessment based on the Microsoft 365 data protection baseline, a recommendation for reducing your data protection and compliance risks ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

<span data-ttu-id="0b34d-159">평가에는 다음과 같은 몇 가지 구성 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-159">Assessments include several components:</span></span>

- <span data-ttu-id="0b34d-160">**범위 내 서비스**: 평가에 적용할 수 있는 특정 Microsoft 서비스 집합</span><span class="sxs-lookup"><span data-stu-id="0b34d-160">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="0b34d-161">**Microsoft 관리 컨트롤**: microsoft에서 구현 하 고 테스트 하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0b34d-161">**Microsoft-managed controls**: controls that Microsoft implemented and tested</span></span>
- <span data-ttu-id="0b34d-162">**고객 관리 컨트롤**: 관리 하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0b34d-162">**Customer-managed controls**: controls that you manage</span></span>
- <span data-ttu-id="0b34d-163">**평가 점수**: 해당 평가 내에서 작업을 완료 하 여 얻은 점수 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-163">**Assessment score**: the percentage of the points achieved by completing actions within that assessment</span></span>

> [!NOTE]
> <span data-ttu-id="0b34d-164">규정 준수 점수에는 평가 및 해당 평가가 전체 점수에 미치는 영향을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-164">Compliance Score displays your assessments and how they factor into your overall score.</span></span> <span data-ttu-id="0b34d-165">그러나 공개 미리 보기 동안에는 규정 준수 관리자에 게 평가를 관리 하도록 지시할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-165">However, during public preview you will be directed to Compliance Manager to manage your assessments.</span></span>

<span data-ttu-id="0b34d-166">[준수 관리자에서 평가 작업](working-with-compliance-manager.md#assessments)을 수행 하기 위한 자세한 지침을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-166">View detailed instructions for [working with assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

### <a name="templates"></a><span data-ttu-id="0b34d-167">템플릿</span><span class="sxs-lookup"><span data-stu-id="0b34d-167">Templates</span></span>

<span data-ttu-id="0b34d-168">규정 준수 점수는 미리 구성 된 서식 파일을 평가에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-168">Compliance Score provides pre-configured templates for assessments.</span></span> <span data-ttu-id="0b34d-169">규정 준수 점수를 사용 하 여 사용자의 요구에 맞게 자체 평가를 위한 템플릿을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-169">Compliance Score also allows you to create templates for your own assessments to suit your needs.</span></span> <span data-ttu-id="0b34d-170">예를 들어 비즈니스 프로세스 컨트롤에 대 한 서식 파일을 만들거나 미리 구성 된 서식 파일 중 하나에 포함 되지 않는 지역별 데이터 보호 또는 규정 준수 표준을 위한 서식 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-170">For example, you can create a template for your business process control, or a template for a regional data protection or compliance standard that isn’t covered by one of the pre-configured templates.</span></span>  <span data-ttu-id="0b34d-171">템플릿을 직접 만들면 사용자 지정 평가를 만들어 준수 점수가 Microsoft 클라우드 평가 뿐 아니라 조직의 범위에 있는 다른 위험 평가에도 추적 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-171">By creating your own templates, you can create custom assessments to ensure that Compliance Score tracks not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

<span data-ttu-id="0b34d-172">기존 서식 파일을 복사 하거나 Excel 파일에서 컨트롤 정보를 가져와서 새 서식 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-172">You can create new templates by copying an existing template, or by importing controls information from an Excel file.</span></span> <span data-ttu-id="0b34d-173">[준수 관리자에서 서식 파일을 만드는](working-with-compliance-manager.md#templates)방법에 대 한 자세한 지침을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-173">View detailed instructions for [creating templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>

<span data-ttu-id="0b34d-174">규정 준수 점수를 위해 미리 구성 된 서식 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-174">The pre-configured templates for Compliance Score are:</span></span>

1. [<span data-ttu-id="0b34d-175">브라질 LGPD (일반 데이터 보호 법)</span><span class="sxs-lookup"><span data-stu-id="0b34d-175">Brazil General Data Protection Law (LGPD)</span></span>](https://go.microsoft.com/fwlink/?linkid=2115387)
2. <span data-ttu-id="0b34d-176">[캘리포니아 CCPA (소비자 개인 정보 보호 Act)](https://go.microsoft.com/fwlink/?linkid=2108871) (Preview)</span><span class="sxs-lookup"><span data-stu-id="0b34d-176">[California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (Preview)</span></span>
3. [<span data-ttu-id="0b34d-177">CSA (cloud Security 제휴) 3.0.1 (CCM)</span><span class="sxs-lookup"><span data-stu-id="0b34d-177">Cloud Security Alliance (CSA) Cloud Controls Matrix (CCM) 3.0.1</span></span>](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [<span data-ttu-id="0b34d-178">유럽 연합 GDPR</span><span class="sxs-lookup"><span data-stu-id="0b34d-178">European Union GDPR</span></span>](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [<span data-ttu-id="0b34d-179">연방 금융 기관 검사 Council (FFIEC) 정보 보안 소책자</span><span class="sxs-lookup"><span data-stu-id="0b34d-179">Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet</span></span>](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [<span data-ttu-id="0b34d-180">FedRAMP 보통</span><span class="sxs-lookup"><span data-stu-id="0b34d-180">FedRAMP Moderate</span></span>](https://go.microsoft.com/fwlink/?linkid=2108869)
7. <span data-ttu-id="0b34d-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)</span><span class="sxs-lookup"><span data-stu-id="0b34d-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)</span></span>
8. <span data-ttu-id="0b34d-182">[Irap](https://go.microsoft.com/fwlink/?linkid=2113709) / [오스트레일리아 정부 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="0b34d-182">[IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [Australian Government ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (Preview)</span></span>
9. [<span data-ttu-id="0b34d-183">ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="0b34d-183">ISO 27001:2013</span></span>](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [<span data-ttu-id="0b34d-184">ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="0b34d-184">ISO 27018:2014</span></span>](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [<span data-ttu-id="0b34d-185">ISO 27701:2019</span><span class="sxs-lookup"><span data-stu-id="0b34d-185">ISO 27701:2019</span></span>](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [<span data-ttu-id="0b34d-186">Microsoft 365 데이터 보호 초기 계획</span><span class="sxs-lookup"><span data-stu-id="0b34d-186">Microsoft 365 Data Protection Baseline</span></span>](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [<span data-ttu-id="0b34d-187">NIST 800-53 Rev. 4</span><span class="sxs-lookup"><span data-stu-id="0b34d-187">NIST 800-53 Rev. 4</span></span>](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [<span data-ttu-id="0b34d-188">NIST 800-171</span><span class="sxs-lookup"><span data-stu-id="0b34d-188">NIST 800-171</span></span>](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [<span data-ttu-id="0b34d-189">NIST Cybersecurity Framework (CSF)</span><span class="sxs-lookup"><span data-stu-id="0b34d-189">NIST Cybersecurity Framework (CSF)</span></span>](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [<span data-ttu-id="0b34d-190">SOC 1</span><span class="sxs-lookup"><span data-stu-id="0b34d-190">SOC 1</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [<span data-ttu-id="0b34d-191">SOC 2</span><span class="sxs-lookup"><span data-stu-id="0b34d-191">SOC 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)

> [!NOTE]
> <span data-ttu-id="0b34d-192">공개 미리 보기 중에 규정 준수 관리자로 이동 하 여 템플릿을 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-192">During public preview, go to Compliance Manager to create and manage your templates.</span></span>

### <a name="groups"></a><span data-ttu-id="0b34d-193">그룹</span><span class="sxs-lookup"><span data-stu-id="0b34d-193">Groups</span></span>

<span data-ttu-id="0b34d-194">그룹을 사용 하면 사용자에 게 논리적으로 평가를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-194">Groups allow you to organize assessments in a way that is logical to you.</span></span> <span data-ttu-id="0b34d-195">예를 들어 평가를 연, 규정 준수 standard, 서비스, 조직 내의 팀 또는 기타 다른 방식으로 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-195">For example, you may choose to group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span>

<span data-ttu-id="0b34d-196">같은 그룹의 서로 다른 두 평가에서 고객 관리 작업을 공유 하는 경우 한 평가에서의 구현 세부 정보, 테스트 및 상태는 그룹의 다른 평가에 있는 동일한 작업과 자동으로 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-196">When two different assessments in the same group share customer-managed actions, the completion of implementation details, testing, and status for the action in one assessment automatically synchronizes to the same action in any other assessment in the group.</span></span> <span data-ttu-id="0b34d-197">이렇게 하면 그룹 전체에 대해 할당 된 개선 작업을 통합 하 고 복제 작업을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-197">This unifies the assigned improvement actions across the group and reduces duplicating work.</span></span>

<span data-ttu-id="0b34d-198">[준수 관리자에서 그룹을 만드는](working-with-compliance-manager.md#groups)방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-198">Learn how to [create groups in Compliance Manager](working-with-compliance-manager.md#groups).</span></span> <span data-ttu-id="0b34d-199">그룹을 만든 후에는 [준수 점수 대시보드를 필터링](compliance-score-setup.md#filtering-your-dashboard-view) 하 여 하나 이상의 그룹에 따라 점수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-199">Once you create groups, you can [filter you Compliance Score dashboard](compliance-score-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

## <a name="next-step-begin-setup"></a><span data-ttu-id="0b34d-200">다음 단계: 설치 시작</span><span class="sxs-lookup"><span data-stu-id="0b34d-200">Next step: begin setup</span></span>

<span data-ttu-id="0b34d-201">[준수 점수 설정](compliance-score-setup.md)에 로그인 하 고, 사용 권한을 설정 하 고, 업데이트 및 대시보드 보기를 구성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0b34d-201">Learn how to sign in, set up permissions, and configure updates and dashboard views at [Compliance Score setup](compliance-score-setup.md).</span></span>
