---
title: 규정 준수 제공 - CSA (Cloud Security Alliance) STAR 자체 평가
description: Microsoft STAR 자체 평가에서는 클라우드 서비스에서 Cloud Security Alliance 요구 사항을 충족하는 방법에 대해 자세히 설명합니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 28f526845ccaee4ea914c3859d4a2a9c34068048
ms.sourcegitcommit: 8ad30e6c5cd77a72e5c1ce463c9f693132cc0b15
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "38763037"
---
# <a name="compliance-offering-cloud-security-alliance-csa-star-self-assessment"></a><span data-ttu-id="09e7d-104">규정 준수 제안 - CSA (Cloud Security Alliance) STAR 자체 평가</span><span class="sxs-lookup"><span data-stu-id="09e7d-104">Compliance offering: Cloud Security Alliance (CSA) STAR self-assessment</span></span>

## <a name="csa-star-self-assessment-overview"></a><span data-ttu-id="09e7d-105">CSA STAR 자체 평가 개요</span><span class="sxs-lookup"><span data-stu-id="09e7d-105">CSA STAR self-assessment overview</span></span>

<span data-ttu-id="09e7d-106">CSA(Cloud Security Alliance)는 전문직 종사자, 회사 및 기타 주요 이해 관계자 연합이 주도하는 비영리 단체입니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-106">The Cloud Security Alliance (CSA) is a nonprofit organization led by a broad coalition of industry practitioners, corporations, and other important stakeholders.</span></span> <span data-ttu-id="09e7d-107">이 단체는 보다 안전한 클라우드 컴퓨팅 환경을 유지하고 잠재적 클라우드 고객이 IT 운영을 클라우드로 전환할 때 현명한 결정을 내릴 수 있도록 도와줄 모범 사례를 정의하는 데 전념하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-107">It is dedicated to defining best practices to help ensure a more secure cloud computing environment, and to helping potential cloud customers make informed decisions when transitioning their IT operations to the cloud.</span></span>  
  
<span data-ttu-id="09e7d-108">CSA는 2010년에 클라우드 IT 운영(CSA 관리 방식, 위험 관리 및 규정 준수(GRC) 스택)을 평가할 도구를 발표했습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-108">In 2010, the CSA published a suite of tools to assess cloud IT operations: the CSA Governance, Risk Management, and Compliance (GRC) Stack.</span></span> <span data-ttu-id="09e7d-109">클라우드 고객이 CSP(클라우드 서비스 공급자)가 업계 모범 사례 및 표준을 준수하고 규정을 준수하는 방식을 평가하는 데 도움을 주도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-109">It was designed to help cloud customers assess how cloud service providers (CSPs) follow industry best practices and standards and comply with regulations.</span></span>  
  
<span data-ttu-id="09e7d-110">2013년 CSA와 British Standards Institution(영국 표준 협회)는 CPS가 CSA 관련 평가를 게시할 수 있도록 STAR(Security, Trust & Assurance Registry: 보안, 트러스트 및 보증 등록)라고 하는 무료 및 공개적으로 액세스할 수 있는 등록 프로그램을 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-110">In 2013, the CSA and the British Standards Institution launched the Security, Trust & Assurance Registry (STAR), a free, publicly accessible registry in which CSPs can publish their CSA-related assessments.</span></span>  
  
<span data-ttu-id="09e7d-111">CSA STAR는 CSA GRC 스택의 두 가지 주요 구성 요소를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-111">CSA STAR is based on two key components of the CSA GRC Stack:</span></span>

- <span data-ttu-id="09e7d-112">CCM(Cloud Controls Matrix): 클라우드 고객이 CSP의 전반적인 보안 위험을 평가하는 데 도움이 되도록 16개 도메인의 기본 보안 원칙을 다루는 제어 프레임워크</span><span class="sxs-lookup"><span data-stu-id="09e7d-112">Cloud Controls Matrix (CCM): a controls framework covering fundamental security principles across 16 domains to help cloud customers assess the overall security risk of a CSP.</span></span>
- <span data-ttu-id="09e7d-113">CAIQ(Consensus Assessments Initiative Questionnaire): 고객 또는 클라우드 감사자가 CSA 모범 사례를 준수하는지 평가하기 위해 CSP에 질문할 수 있는 CCM을 기반으로 하는 140개 이상의 질문 집합.</span><span class="sxs-lookup"><span data-stu-id="09e7d-113">The Consensus Assessments Initiative Questionnaire (CAIQ): a set of more than 140 questions based on the CCM that a customer or cloud auditor may want to ask of CSPs to assess their compliance with CSA best practices.</span></span>

<span data-ttu-id="09e7d-114">STAR는 세 가지 수준의 보장을 제공합니다. CSA-STAR 자체 평가는 수준 1의 도입 제안으로, 무료이며 모든 CSP에게 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-114">STAR provides three levels of assurance; CSA-STAR Self-Assessment is the introductory offering at Level 1, which is free and open to all CSPs.</span></span> <span data-ttu-id="09e7d-115">보장 스택을 더 올라가 STAR 프로그램의 수준 2는 제3의 독립 기관 평가 기반 인증을 포함하고, 수준 3은 지속적인 모니터링을 기반으로 하는 인증을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-115">Going further up the assurance stack, Level 2 of the STAR program involves third-party assessment-based certifications, and Level 3 involves certifications based on continuous monitoring.</span></span>

## <a name="microsoft-and-csa-star-self-assessment"></a><span data-ttu-id="09e7d-116">Microsoft와 CSA STAR 자체 평가</span><span class="sxs-lookup"><span data-stu-id="09e7d-116">Microsoft and CSA STAR self-assessment</span></span>

<span data-ttu-id="09e7d-117">STAR 자체 평가의 일환으로 CSP는 CSA 모범 사례 준수를 보여주는 두 가지 유형의 문서(완료된 CAIQ 또는 CCM 준수를 문서화한 보고서)를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-117">As part of the STAR Self-Assessment, CSPs can submit two different types of documents to indicate their compliance with CSA best practices: a completed CAIQ, or a report documenting compliance with CCM.</span></span> <span data-ttu-id="09e7d-118">CSA STAR 자체 평가를 위해 Microsoft는 Microsoft Azure에 대한 CAIQ 및 CCM 기반 보고서와 Microsoft Dynamics 365와 Microsoft Office 365에 대한 CCM 기반 보고서를 모두 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-118">For the CSA STAR Self-Assessment, Microsoft publishes both a CAIQ and a CCM-based report for Microsoft Azure, and CCM-based reports for Microsoft Dynamics 365 and Microsoft Office 365.</span></span>  
  
<span data-ttu-id="09e7d-119">Microsoft 클라우드에서 CSA STAR 자체 평가의 이점에 대해 알아봅니다. [CSA STAR 자체 평가 배경 설명 다운로드](https://aka.ms/csastar-selfassessment-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="09e7d-119">Learn about the benefits of CSA STAR Self-Assessment on the Microsoft Cloud: [Download the CSA STAR Self-Assessment backgrounder](https://aka.ms/csastar-selfassessment-backgrounder)</span></span>

<span data-ttu-id="09e7d-120">Azure 보안 및 규정 준수 청사진을 사용하여 CSA STAR 자체 평가 배포를 가속화하는 방법에 대해 알아봅니다. [CSA Consensus Assessments에 대한 Azure 대응 다운로드](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)</span><span class="sxs-lookup"><span data-stu-id="09e7d-120">Learn how to accelerate your CSA STAR Self-Assessment deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the CSA Consensus Assessments](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="09e7d-121">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="09e7d-121">Microsoft cloud services</span></span>

- [<span data-ttu-id="09e7d-122">Azure 및 Azure Government</span><span class="sxs-lookup"><span data-stu-id="09e7d-122">Azure and Azure Government</span></span>](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [<span data-ttu-id="09e7d-123">Dynamics 365 CSA STAR 자체 평가</span><span class="sxs-lookup"><span data-stu-id="09e7d-123">Dynamics 365 CSA STAR Self-Assessment</span></span>](https://cloudsecurityalliance.org/star/registry/microsoft/)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="09e7d-124">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="09e7d-124">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="09e7d-125">정보 요청에 대한 Azure 표준 대응</span><span class="sxs-lookup"><span data-stu-id="09e7d-125">Azure standard response for request for information</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7ca8423-1bc5-4be0-bff8-b6056f87c134&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)
- [<span data-ttu-id="09e7d-126">Azure Cloud Security Alliance CAIQ</span><span class="sxs-lookup"><span data-stu-id="09e7d-126">Azure Cloud Security Alliance CAIQ</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a966a424-ecfd-4de2-9739-b08aee2d3ca0&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)
- [<span data-ttu-id="09e7d-127">CSA CAIQ v3.0.1에 대한 Azure 대응</span><span class="sxs-lookup"><span data-stu-id="09e7d-127">Azure responses to the CSA CAIQ v3.0.1</span></span>](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)

## <a name="frequently-asked-questions"></a><span data-ttu-id="09e7d-128">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="09e7d-128">Frequently asked questions</span></span>

<span data-ttu-id="09e7d-129">**CSA CCM이 어떤 산업 표준과 일치하나요?**</span><span class="sxs-lookup"><span data-stu-id="09e7d-129">**Which industry standards does the CSA CCM align with?**</span></span>

<span data-ttu-id="09e7d-130">CCM는 ISO 27001, PCI DSS, HIPAA, AICPA SOC 2, CIP, FedRAMP, NIST 등과 같은 업계에서 인정받는 보안 표준, 규정 및 제어 프레임워크에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-130">The CCM corresponds to industry-accepted security standards, regulations, and control frameworks such as ISO 27001, PCI DSS, HIPAA, AICPA SOC 2, NERC CIP, FedRAMP, NIST, and many more.</span></span> <span data-ttu-id="09e7d-131">최신 목록은 [CSA 웹 사이트](https://cloudsecurityalliance.org/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09e7d-131">For the most current list, visit the [CSA website](https://cloudsecurityalliance.org/).</span></span>

<span data-ttu-id="09e7d-132">**CSA 별 자체 평가가 중요한 이유는 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="09e7d-132">**Why is the CSA STAR Self-Assessment important?**</span></span>

<span data-ttu-id="09e7d-133">이를 통해 CSP는 CSA에서 게시한 모범 사례 준수 사항을 투명한 방식으로 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-133">It enables CSPs to document compliance with CSA published best practices in a transparent manner.</span></span> <span data-ttu-id="09e7d-134">자체 평가 보고서는 일반에게 공개되고 따라서 클라우드 고객은 CSP 보안 관례를 보고 동일한 기준을 사용하여 다양한 CSP를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-134">Self-assessment reports are publicly available, thereby helping cloud customers gain visibility into the security practices of CSPs, and compare various CSPs using the same baseline.</span></span>

<span data-ttu-id="09e7d-135">**Microsoft 비즈니스 클라우드 서비스는 어떤 CSA STAR 보증 수준을 획득했나요?**</span><span class="sxs-lookup"><span data-stu-id="09e7d-135">**Which CSA STAR levels of assurance have Microsoft business cloud services attained?**</span></span>

- <span data-ttu-id="09e7d-136">**수준 1**: **CSA STAR 자체 평가**: Azure, Dynamics 365, Office 365.</span><span class="sxs-lookup"><span data-stu-id="09e7d-136">**Level 1**: **CSA STAR Self-Assessment**: Azure, Dynamics 365, and Office 365.</span></span> <span data-ttu-id="09e7d-137">자체 평가는 클라우드 서비스 공급자가 고객이 서비스 보안을 평가하는 것을 돕기 위해 보안 제어를 문서화하는 무료 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-137">The Self-Assessment is a complimentary offering from cloud service providers to document their security controls to help customers assess the security of the service.</span></span>
- <span data-ttu-id="09e7d-138">**수준 2**: **CSA STAR 인증**: Azure, Cloud App Security, Intune, Power BI.</span><span class="sxs-lookup"><span data-stu-id="09e7d-138">**Level 2**: **CSA STAR Certification**: Azure, Cloud App Security, Intune, and Power BI.</span></span> <span data-ttu-id="09e7d-139">STAR 인증은 ISO/IEC 27001 인증을 획득과 CCM에 지정된 기준 충족에 기반합니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-139">STAR Certification is based on achieving ISO/IEC 27001 certification and meeting criteria specified in the CCM.</span></span> <span data-ttu-id="09e7d-140">클라우드 서비스 공급자의 보안 제어 및 관행에 대한 엄격한 제3자 평가 후에 이를 수여합니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-140">It is awarded after a rigorous third-party assessment of the security controls and practices of a cloud service provider.</span></span>
- <span data-ttu-id="09e7d-141">**수준 2**: **CSA STAR 증명**: Azure, Intune.</span><span class="sxs-lookup"><span data-stu-id="09e7d-141">**Level 2**: **CSA STAR Attestation**: Azure and Intune.</span></span> <span data-ttu-id="09e7d-142">CSA와 AICPA는 AICPA(Trust Service Principles, AT 101)와 CSA CCM의 기준을 사용하여 CPA가 SOC 2 계약을 수행하는 데 사용할 지침을 제공하기 위해 협력했습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-142">CSA and the AICPA have collaborated to provide guidelines for CPAs to use in conducting SOC 2 engagements, using criteria from the AICPA (Trust Service Principles, AT 101) and the CSA CCM.</span></span> <span data-ttu-id="09e7d-143">STAR 증명은 이러한 지침을 기반으로 하며 클라우드 공급자에 대한 엄격한 독립적인 평가 후에 수여됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-143">STAR Attestation is based on these guidelines and is awarded after rigorous independent assessments of cloud providers.</span></span>

## <a name="resources"></a><span data-ttu-id="09e7d-144">리소스</span><span class="sxs-lookup"><span data-stu-id="09e7d-144">Resources</span></span>

- [<span data-ttu-id="09e7d-145">Cloud Security Alliance</span><span class="sxs-lookup"><span data-stu-id="09e7d-145">Cloud Security Alliance</span></span>](https://cloudsecurityalliance.org/)
- [<span data-ttu-id="09e7d-146">Cloud Controls Matrix (CCM)</span><span class="sxs-lookup"><span data-stu-id="09e7d-146">Cloud Controls Matrix (CCM)</span></span>](https://cloudsecurityalliance.org/group/cloud-controls-matrix/)
- [<span data-ttu-id="09e7d-147">Consensus Assessments Initiative Questionnaire (CAIQ)</span><span class="sxs-lookup"><span data-stu-id="09e7d-147">Consensus Assessments Initiative Questionnaire (CAIQ)</span></span>](https://cloudsecurityalliance.org/group/consensus-assessments/)
- [<span data-ttu-id="09e7d-148">CSA STAR(Security, Trust & Assurance Registry: 보안, 트러스트 및 보증 등록)</span><span class="sxs-lookup"><span data-stu-id="09e7d-148">CSA Security, Trust & Assurance Registry (STAR)</span></span>](https://cloudsecurityalliance.org/star/)
- [<span data-ttu-id="09e7d-149">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="09e7d-149">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-csa-star-self-assessments"></a><span data-ttu-id="09e7d-150">Microsoft CSA STAR 자체 평가</span><span class="sxs-lookup"><span data-stu-id="09e7d-150">Microsoft CSA STAR self-assessments</span></span>

- [<span data-ttu-id="09e7d-151">Azure</span><span class="sxs-lookup"><span data-stu-id="09e7d-151">Azure</span></span>](https://aka.ms/Azure_STAR)
- [<span data-ttu-id="09e7d-152">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="09e7d-152">Dynamics 365</span></span>](https://aka.ms/DynamicsCRM_Online_STAR)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="09e7d-153">제공되는 사항의 배경 설명 다운로드</span><span class="sxs-lookup"><span data-stu-id="09e7d-153">Download the offering backgrounder</span></span>

<span data-ttu-id="09e7d-154">이 제공 사항에 대한 배경 설명 문서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="09e7d-154">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="09e7d-155">[PDF](https://download.microsoft.com/download/7/C/E/7CE08DFE-86D6-4690-9455-5123DA0A7C09/CSA-STAR-SelfAssessment-Compliance.pdf)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="09e7d-155">Download the [PDF version](https://download.microsoft.com/download/7/C/E/7CE08DFE-86D6-4690-9455-5123DA0A7C09/CSA-STAR-SelfAssessment-Compliance.pdf) orVisio version.</span></span>

