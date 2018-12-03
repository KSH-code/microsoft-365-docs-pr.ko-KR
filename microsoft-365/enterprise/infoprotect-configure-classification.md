---
title: '2단계: 사용자 환경에 대한 분류 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 조직에서 데이터를 분류하는 다양한 방법을 이해하고 구성합니다.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869917"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="070cc-103">2단계: 사용자 환경에 대한 분류 구성</span><span class="sxs-lookup"><span data-stu-id="070cc-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="070cc-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="070cc-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="070cc-105">이 단계에서는 법률 및 준수 팀과 함께 조직의 데이터에 대한 분류 체계를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="070cc-105">In Step 3, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-classifications"></a><span data-ttu-id="070cc-106">Microsoft 분류</span><span class="sxs-lookup"><span data-stu-id="070cc-106">Microsoft classifications</span></span>

<span data-ttu-id="070cc-107">Microsoft 365에는 세 가지 유형의 분류가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="070cc-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="070cc-108">Office 365의 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="070cc-108">Sensitive information types for Office 365</span></span>
- <span data-ttu-id="070cc-109">Office 365 레이블</span><span class="sxs-lookup"><span data-stu-id="070cc-109">Office 365 labels</span></span>
- <span data-ttu-id="070cc-110">Azure Information Protection 레이블 및 보호</span><span class="sxs-lookup"><span data-stu-id="070cc-110">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types-for-office-365"></a><span data-ttu-id="070cc-111">Office 365의 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="070cc-111">Sensitive information types for Office 365</span></span>

<span data-ttu-id="070cc-p101">Office 365의 중요한 정보 유형은 검색과 같은 자동화된 프로세스에서 건강 보험 번호 및 신용 카드 번호와 같은 특정 정보 유형을 인식하는 방법을 정의합니다. 중요한 정보 유형을 사용하여 중요한 데이터를 찾고 데이터 손실 방지 규칙을 적용하여 이 데이터를 보호할 수 있습니다. 자세한 내용은 [데이터 손실 방지 정책 개요](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)를 참조하세요. 예를 들어 중요한 정보 유형은 GDPR(일반 데이터 보호 규정)과 같은 준수 및 규정 요구 사항을 준수하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="070cc-p101">Sensitive information types for Office 365 define how automated processes such as search recognize specific information types such as health service numbers and credit card numbers. You use sensitive information types to find sensitive data and apply data loss prevention rules and policies to protect this data. For more information, see [Overview of data loss prevention policies](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). For example, sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="office-365-labels"></a><span data-ttu-id="070cc-116">Office 365 레이블</span><span class="sxs-lookup"><span data-stu-id="070cc-116">Office 365 labels</span></span>
<span data-ttu-id="070cc-p102">개인 데이터뿐 아니라 SharePoint Online 및 비즈니스용 OneDrive에 저장된 높은 규제 및 영업 비밀 파일에 Office 365 레이블을 사용할 수 있습니다. 레이블을 만드는 방법을 포함하여 자세한 내용은 [레이블 개요](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="070cc-p102">You can use Office 365 labels for personal data and for highly regulated and trade secret files stored in SharePoint Online and OneDrive for Business. For more information, including how to create them, see [Overview of labels](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span></span>

<span data-ttu-id="070cc-p103">Office 365 레이블을 사용하려면 각 보호 수준에 대해 하나 이상을 구성해야 합니다. 예를 들어 다음에 대한 세 가지 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="070cc-p103">If you decide to use Office 365 labels, you should configure at least one for each level of protection. For example, create three labels for:</span></span>

- <span data-ttu-id="070cc-121">기준</span><span class="sxs-lookup"><span data-stu-id="070cc-121">Baseline</span></span>
- <span data-ttu-id="070cc-122">중요</span><span class="sxs-lookup"><span data-stu-id="070cc-122">Sensitive</span></span>
- <span data-ttu-id="070cc-123">높은 규제</span><span class="sxs-lookup"><span data-stu-id="070cc-123">Highly regulated</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="070cc-124">Azure Information Protection 레이블 및 보호</span><span class="sxs-lookup"><span data-stu-id="070cc-124">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="070cc-p104">Azure Information Protection 레이블을 사용하여 조직의 문서와 전자 메일을 분류하고 필요에 따라 보호할 수 있습니다. 이러한 레이블은 Office 365 외부에 저장된 문서에 적용될 수 있으며, 규칙 및 조건을 정의하는 관리자가 자동으로 적용하거나, 사용자가 수동으로 적용하거나, 사용자에게 권장 사항을 제공하는 상황에서 두 가지 방법을 조합하여 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="070cc-p104">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails. These labels can apply to documents that are stored outside of Office 365. These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="070cc-128">Azure Information Protection 레이블 및 보호를 계획하고 배포하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="070cc-128">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="070cc-129">[Azure Information Protection에 대한 요구 사항](https://docs.microsoft.com/information-protection/get-started/requirements)을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="070cc-129">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="070cc-130">[분류, 레이블 지정 및 보호에 대한 배포 로드맵](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="070cc-130">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="070cc-131">자세한 내용은 [Azure Information Protection 설명서 라이브러리](https://docs.microsoft.com/information-protection/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="070cc-131">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

## <a name="classification-for-gdpr"></a><span data-ttu-id="070cc-132">GDPR에 대한 분류</span><span class="sxs-lookup"><span data-stu-id="070cc-132">Classification for GDPR</span></span>

<span data-ttu-id="070cc-133">GDPR에 대한 개인 데이터를 포함하는 예제 분류 체계는 [개인 데이터에 대한 분류 체계 설계](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="070cc-133">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="070cc-135">테스트 랩 가이드: 데이터 분류</span><span class="sxs-lookup"><span data-stu-id="070cc-135">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="070cc-136">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step3)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="070cc-136">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="070cc-137">다음 단계</span><span class="sxs-lookup"><span data-stu-id="070cc-137">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="070cc-138">Office 365에 대한 향상된 보안 구성</span><span class="sxs-lookup"><span data-stu-id="070cc-138">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

