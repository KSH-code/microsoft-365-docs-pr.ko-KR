---
title: '2단계: 사용자 환경에 대한 분류 구성'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 조직에서 데이터를 분류하는 다양한 방법을 이해하고 구성합니다.
ms.openlocfilehash: e8c40ca4c419edc2d59a060dfd4fe8918cf4e784
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067255"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="ae2f0-103">2단계: 사용자 환경에 대한 분류 구성</span><span class="sxs-lookup"><span data-stu-id="ae2f0-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="ae2f0-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="ae2f0-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![6단계: 정보 보호](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="ae2f0-106">이 단계에서는 법률 및 준수 팀과 함께 조직의 데이터에 대한 분류 체계를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-106">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="ae2f0-107">Microsoft 365 분류 유형</span><span class="sxs-lookup"><span data-stu-id="ae2f0-107">Microsoft 365 classification types</span></span>

<span data-ttu-id="ae2f0-108">Microsoft 365에는 네 가지 유형의 분류가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-108">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="ae2f0-109">중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="ae2f0-109">Sensitive information types</span></span>
- <span data-ttu-id="ae2f0-110">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="ae2f0-110">Retention labels</span></span>
- <span data-ttu-id="ae2f0-111">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="ae2f0-111">Sensitivity labels</span></span>
- <span data-ttu-id="ae2f0-112">Azure Information Protection 레이블 및 보호</span><span class="sxs-lookup"><span data-stu-id="ae2f0-112">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="ae2f0-113">중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="ae2f0-113">Sensitive information types</span></span>

<span data-ttu-id="ae2f0-114">Microsoft 365의 중요한 정보 유형은 특정 정보 유형 검색 인식과 같은 자동화된 프로세스의 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-114">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="ae2f0-115">여기에는 의료 서비스 번호 및 신용 카드 번호와 같은 중요한 직원 또는 고객 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-115">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="ae2f0-116">중요한 정보 유형을 사용하여 중요한 데이터를 찾고 DLP (데이터 손실 방지) 규칙 및 정책을 적용하여 이 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-116">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="ae2f0-117">자세한 내용은 [DLP 정책에 포함 된 내용을](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-117">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="ae2f0-118">중요한 정보 유형은 일반 데이터 보호 규정 (GDPR)과 같이 규제 준수 및 규제 요구 사항을 충족하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-118">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="ae2f0-119">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="ae2f0-119">Retention labels</span></span>

<span data-ttu-id="ae2f0-120">데이터 거버넌스 전략 정의의 일부는 조직 정책 및 지역 규정에 따라 특정 내용이 포함된 특정 유형의 문서 또는 문서를 보관하는 기간을 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-120">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="ae2f0-121">예를 들어, 일부 유형의 문서는 설정된 시간 동안 보존한 다음 삭제해야하며 일부는 영구적으로 보관해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-121">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="ae2f0-122">Microsoft 365에 저장된 문서의 경우 Exchange 전자 메일, SharePoint Online, 비즈니스용 OneDrive 및 Teams 채팅 및 채널 메시지에 저장된 문서 및 데이터에 보존 레이블을 정의하고 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-122">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="ae2f0-123">보존 레이블을 사용하는 경우 보관 정책을 적용해야하는 파일의 각 범주에 대한 레이블을 구성해야합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-123">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="ae2f0-124">보존 레이블 내에서 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-124">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="ae2f0-125">파일에 대한 설명 집합 (예 : 비즈니스 부서, 파일 범주 또는 규정별).</span><span class="sxs-lookup"><span data-stu-id="ae2f0-125">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="ae2f0-126">보존 기간에 도달 한 후 보존 시간 및 동작과 같은 보존 레이블이 첨부된 파일의 보존 설정.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-126">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="ae2f0-127">사이트의 모든 새 문서에 기본 보존 레이블을 적용하도록 SharePoint Online 사이트를 구성하여 파일에 보존 레이블을 자동으로 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-127">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="ae2f0-128">자세한 내용은 [보존 레이블 개요](https://docs.microsoft.com/office365/securitycompliance/labels)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-128">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="ae2f0-129">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="ae2f0-129">Sensitivity labels</span></span>

<span data-ttu-id="ae2f0-130">특정 유형의 문서 또는 특정 내용의 문서에 대해 보안을 보호하고 구현하는 부분에는 추가 보안을 적용 할 수 있도록 레이블이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-130">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="ae2f0-131">Microsoft 365의 민감도 레이블을 사용하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-131">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="ae2f0-132">암호화, 사용 권한 또는 워터 마크 추가와 같은 보호 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-132">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="ae2f0-133">WIP (Windows 정보 보호) 엔드포인트 보호를 사용하여 콘텐츠가 Twitter 또는 Gmail과 같은 타사 앱으로 복사되거나 USB 드라이브와 같은 이동식 저장소로 복제되지 않도록합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-133">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="ae2f0-134">Microsoft CAS(Cloud App Security)를 사용하여 타사 앱 및 서비스의 콘텐츠를 보호하세요.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-134">Use Microsoft Cloud App Security (CAS) to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="ae2f0-135">보호 설정을 사용하지 않고 콘텐츠를 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-135">Classify content without using any protection settings.</span></span>

<span data-ttu-id="ae2f0-136">민감도 레이블을 사용하는 경우 각 보안 및 정보 보호 수준에 대한 레이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-136">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="ae2f0-137">예를 들어 다음에 대해 세 가지 민감도 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-137">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="ae2f0-138">기준</span><span class="sxs-lookup"><span data-stu-id="ae2f0-138">Baseline</span></span>
- <span data-ttu-id="ae2f0-139">중요</span><span class="sxs-lookup"><span data-stu-id="ae2f0-139">Sensitive</span></span>
- <span data-ttu-id="ae2f0-140">매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="ae2f0-140">Highly regulated</span></span>

<span data-ttu-id="ae2f0-141">SharePoint Online 사이트에 규제가 엄격한 데이터가 포함된 파일을 저장한 후 파일이 사이트를 나갈 경우 해당 사이트와 동일한 권한을 파일에 사용하려는 경우, 권한이 해당 사이트와 동일한 추가 민감도 레이블을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-141">If you store files with highly regulated data in a SharePoint Online site and want those files to have the same permissions as the site if the files leave the site, you need to create an additional sensitivity label whose permissions are the same as the site.</span></span>

<span data-ttu-id="ae2f0-142">자세한 내용은 이 [민감도 레이블 개요](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-142">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="ae2f0-143">Azure Information Protection 레이블 및 보호</span><span class="sxs-lookup"><span data-stu-id="ae2f0-143">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="ae2f0-144">Azure Information Protection 레이블을 사용하여 조직의 문서와 전자 메일을 분류하고 선택적으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-144">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="ae2f0-145">이러한 레이블은 Microsoft 365 외부에 저장된 문서에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-145">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="ae2f0-146">이러한 레이블은 규칙 및 조건을 정의한 관리자는 자동으로, 사용자는 수동으로 적용할 수 있으며, 사용자가 권장 사항을 제공받은 경우에는 자동 또는 수동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-146">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="ae2f0-147">Azure Information Protection 레이블 및 보호를 계획하고 배포하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-147">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="ae2f0-148">[Azure Information Protection에 대한 요구 사항](https://docs.microsoft.com/information-protection/get-started/requirements)을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-148">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="ae2f0-149">[분류, 레이블 지정 및 보호에 대한 배포 로드맵](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-149">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="ae2f0-150">자세한 내용은 [Azure Information Protection 설명서 라이브러리](https://docs.microsoft.com/information-protection/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-150">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="ae2f0-151">기존 Azure Information Protection 레이블은 민감도 레이블과 원활하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-151">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="ae2f0-152">예를 들어, 기존 Azure Information Protection 레이블과 문서 및 이메일에 적용되는 레이블을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-152">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="ae2f0-153">민감도 및 Azure 정보 보호 레이블이 모두 있는 경우 [Azure Information Protection 레이블을 민감도 레이블로 마이그레이션](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels)해야합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-153">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="ae2f0-154">예: GDPR에 대한 분류</span><span class="sxs-lookup"><span data-stu-id="ae2f0-154">Example: Classification for GDPR</span></span>

<span data-ttu-id="ae2f0-155">GDPR에 대한 개인 데이터를 포함하는 예제 분류 체계는 [개인 데이터에 대한 분류 체계 설계](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-155">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="ae2f0-156">테스트 드라이브 시도</span><span class="sxs-lookup"><span data-stu-id="ae2f0-156">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="ae2f0-158">테스트 랩 가이드: 데이터 분류</span><span class="sxs-lookup"><span data-stu-id="ae2f0-158">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="ae2f0-159">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step2)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ae2f0-159">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ae2f0-160">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ae2f0-160">Next step</span></span>

|||
|:-------|:-----|
|![3단계](../media/stepnumbers/Step3.png)|[<span data-ttu-id="ae2f0-162">Office 365에 대한 향상된 보안 구성</span><span class="sxs-lookup"><span data-stu-id="ae2f0-162">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

