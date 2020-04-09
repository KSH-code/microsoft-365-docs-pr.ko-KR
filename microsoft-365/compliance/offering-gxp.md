---
title: 임상, 실험실 및 제조 모범 사례 (GxP)
description: Azure 및 Office 365는 생명과학 조직이 GxP 규정 요구 사항을 충족하도록 도울 수 있습니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: b4699ca9fda4f8d5364dff0fdabd868b886540b3
ms.sourcegitcommit: b1ec6ba779a94ddbaab11a272e40abe1d3064532
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43165903"
---
# <a name="good-clinical-laboratory-and-manufacturing-practices-gxp"></a><span data-ttu-id="dbb9e-104">임상, 실험실 및 제조 모범 사례 (GxP)</span><span class="sxs-lookup"><span data-stu-id="dbb9e-104">Good Clinical, Laboratory, and Manufacturing Practices (GxP)</span></span>

## <a name="about-gxp"></a><span data-ttu-id="dbb9e-105">GxP 정보</span><span class="sxs-lookup"><span data-stu-id="dbb9e-105">About GxP</span></span>

<span data-ttu-id="dbb9e-106">*GxP*라는 용어는 "모범 사례" 지침 및 규정의 일반적인 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-106">The term *GxP* is a general abbreviation for "good practice" guidelines and regulations.</span></span> <span data-ttu-id="dbb9e-107">"x"는 임상 (GCP), 제조 (GMP), 유통 (GDP), 실험실 (GLP), 농업 (GAP) 등의 특정 분야를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-107">The "x" represents a particular field — clinical (GCP), manufacturing (GMP), distribution (GDP), laboratory (GLP), agriculture (GAP), and so on.</span></span> <span data-ttu-id="dbb9e-108">단일 규제 기관이나 관리는 없습니다. 요구 사항은 국가마다 다르지만 각 국가마다 고유한 지침과 규제 기관이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-108">There is no single regulatory entity or administration; each country has its own guidelines and regulators, although requirements are similar from country to country.</span></span> <span data-ttu-id="dbb9e-109">GxP 규정에는 [미국 FDA CFR Title 21 Part 11](https://aka.ms/FDA-CFR) 및 EU의 [EudraLex Volume 4 — GMP 지침, 부속서 11](https://ec.europa.eu/health/documents/eudralex/vol-4_en)에 요약된 규정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-109">GxP regulations include those outlined in the [US FDA CFR Title 21 Part 11](https://aka.ms/FDA-CFR) and [EudraLex Volume 4 — GMP Guidelines, Annex 11](https://ec.europa.eu/health/documents/eudralex/vol-4_en) in the EU.</span></span>

<span data-ttu-id="dbb9e-110">규제 목표는 규제 산업에서 기업이 생산 과정에서 사용하기에 안전하고 엄격한 품질 표준을 충족하는 제품을 제조하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-110">Regulatory goals aim to make sure that businesses in regulated industries manufacture products that are safe to use and meet stringent quality standards during the production process.</span></span> <span data-ttu-id="dbb9e-111">GxP 프로세스를 사용하는 컴퓨터 시스템은 GxP 요구 사항 준수 확인이 필요하며, 시스템이 이를 충족시키는 능력을 보여줄 수 있을 때 자격을 갖춘 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-111">Computerized systems that use GxP processes require validation of adherence to GxP requirements and are considered qualified when the system can demonstrate its ability to fulfill them.</span></span>

## <a name="microsoft-and-gxp"></a><span data-ttu-id="dbb9e-112">Microsoft와 GxP</span><span class="sxs-lookup"><span data-stu-id="dbb9e-112">Microsoft and GxP</span></span>

<span data-ttu-id="dbb9e-113">Microsoft는 리서치, 임상 연구, 유지 관리, 제조 및 생명 과학 제품 및 서비스의 배포를 다루는 조직에게 규제 측면에서 임상, 실험실 및 제조 모범 사례 (GxP)의 요구 사항을 충족하도록 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-113">Microsoft can help organizations that deal with regulated aspects of the research, clinical study, maintenance, manufacturing, and distribution of life science products and services meet their requirements under Good Clinical, Laboratory, and Manufacturing Practices (GxP).</span></span> <span data-ttu-id="dbb9e-114">여기에는 CFR Title 21 Part 11 하의 미국 FDA (식품의약국)에 적용되는 컴퓨터 시스템의 보안 및 전자 기록의 신뢰성에 대한 규정과 EU에서 컴퓨터 시스템에 대한 지침인 EudraLex, Volume 4, 부속서 11을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-114">These include regulations enforced by the US Food and Drug Administration (FDA) under CFR Title 21 Part 11 for the security of computer systems and the reliability and trustworthiness of electronic records, as well as EudraLex, Volume 4, Annex 11, recognized guidelines for computerized systems in the EU.</span></span>

<span data-ttu-id="dbb9e-115">클라우드 서비스 제공 업체에 대한 GxP 인증은 없습니다. 그러나</span><span class="sxs-lookup"><span data-stu-id="dbb9e-115">There is no GxP certification for cloud service providers; however:</span></span>

- <span data-ttu-id="dbb9e-116">Microsoft Azure 및 Microsoft Office 365는 ISO 9001 (QMS) 및 ISO/IEC 27001 (ISMS)을 포함하여 품질 관리 및 정보 보안에 대한 많은 독립적인 감사를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-116">Microsoft Azure and Microsoft Office 365 have undergone many independent audits for quality management and information security, including ISO 9001 (QMS) and ISO/IEC 27001 (ISMS).</span></span> <span data-ttu-id="dbb9e-117">여기에는 Microsoft 절차 및 기술 제어에 대한 정기 감사가 포함되며 효과가 검증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-117">This includes regular audits of Microsoft procedural and technical controls, verified for effectiveness.</span></span>
- <span data-ttu-id="dbb9e-118">Microsoft 자격 접근 방식은 또한 *자동화 제조 모범 사례* (GAMP) 시리즈의 모범 사례 가이드(ISPE(International Society for Pharmaceutical Engineering)로 부터) 및 *규제되는 GxP 환경의 컴퓨터 시스템에 대한 모범 사례*(Pharmaceutical Inspection Cooperation Scheme (PIC/S) PI 011-3로 부터)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-118">The Microsoft qualification approach is also based on industry best practices, including the *Good Automated Manufacturing Practices* (GAMP) series of Good Practices Guides (from the International Society for Pharmaceutical Engineering (ISPE)), and *Good Practices for Computerized Systems in Regulated GxP Environments* (from the Pharmaceutical Inspection Cooperation Scheme (PIC/S) PI 011-3).</span></span>

<span data-ttu-id="dbb9e-119">이러한 표준과 모범 사례는 GxP 규정 준수에 특별히 초점을 맞추지 않지만, 그 목적과 목표는 유사하며 Microsoft 클라우드 서비스에 저장된 데이터의 기밀성, 무결성 및 가용성을 보장하는 데 도움이됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-119">Although these standards and best practices do not specifically focus on GxP regulatory compliance, their purpose and objectives are similar and help ensure the confidentiality, integrity, and availability of data stored in Microsoft cloud services.</span></span>

<span data-ttu-id="dbb9e-120">Microsoft는 생명 과학 산업의 품질 보증 및 규제 GxP 준수를 전문으로 하는 독립 기관인 [Montrium](https://www.montrium.com/)을 유지하여 Microsoft에 대한 GxP 자격 검토를 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-120">Microsoft retained [Montrium](https://www.montrium.com/), an independent organization specializing in quality assurance and regulatory GxP compliance for the life sciences industry, to conduct the GxP qualification review for Microsoft.</span></span> <span data-ttu-id="dbb9e-121">결과적인 자격 지침 ([Azure](https://aka.ms/gxpcompliance) 및 [Office 365](https://resources.techcommunity.microsoft.com/wp-content/uploads/2019/05/Microsoft-Office-365-GxP-Guidelines.pdf))은 이러한 클라우드 서비스를 사용하여 GxP 규제 컴퓨터 시스템을 호스팅 및 지원하려는 생명 과학 조직을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-121">The resulting Qualification Guidelines ([Azure](https://aka.ms/gxpcompliance) and [Office 365](https://resources.techcommunity.microsoft.com/wp-content/uploads/2019/05/Microsoft-Office-365-GxP-Guidelines.pdf)) are intended for life sciences organizations that plan to use these cloud services to host and support GxP-regulated computerized systems.</span></span> <span data-ttu-id="dbb9e-122">이 지침은 GxP 요구 사항을 충족하기 위해 Microsoft와 고객이 공유하는 책임을 식별하고, 범위 내 Microsoft 클라우드 서비스를 사용하는 고객이 GxP 컴퓨터 시스템에 대한 제어를 유지하기 위해 설정할 수 있는 활동 및 컨트롤을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-122">The guidelines identify the responsibility shared by Microsoft and its customers for meeting GxP requirements, as well as recommend activities and controls that customers using in-scope Microsoft cloud services can establish to maintain control over GxP computerized systems.</span></span>

<span data-ttu-id="dbb9e-123">Azure 및 Office 365에서 GxP 솔루션을 구축하는 생명 과학 조직은 클라우드 효율성을 활용하면서 환자 안전, 제품 품질 및 데이터 무결성을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-123">Life sciences organizations building GxP solutions on Azure and Office 365 can take advantage of the cloud's efficiencies while also protecting patient safety, product quality, and data integrity.</span></span> <span data-ttu-id="dbb9e-124">고객은 특정 수준에서 데이터 개인 정보 보호 및 무결성을 강화하는 여러 계층의 보안 및 거버넌스 기술, 운영 관행 및 규정 준수 정책의 혜택을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-124">Customers also benefit from multiple layers of security and governance technologies, operational practices, and compliance policies that enforce data privacy and integrity at specific levels.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="dbb9e-125">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="dbb9e-125">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="dbb9e-126">Azure</span><span class="sxs-lookup"><span data-stu-id="dbb9e-126">Azure</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="dbb9e-127">Office 365</span><span class="sxs-lookup"><span data-stu-id="dbb9e-127">Office 365</span></span>](https://aka.ms/o365-compliance-framework)

## <a name="how-to-implement"></a><span data-ttu-id="dbb9e-128">구현 방법</span><span class="sxs-lookup"><span data-stu-id="dbb9e-128">How to implement</span></span>

- <span data-ttu-id="dbb9e-129">[Azure GxP 지침](https://aka.ms/gxpcompliance): GxP 모범 사례 및 규정을 준수하면서 Azure를 사용하기 위한 포괄적인 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-129">[Azure GxP Guidelines](https://aka.ms/gxpcompliance): A comprehensive toolset for using Azure while adhering to GxP best practices and regulations.</span></span>
- <span data-ttu-id="dbb9e-130">[GxP 시스템과 함께 Azure 사용](https://aka.ms/GXP-Azure-Strategies): 생명 과학 조직이 GxP 응용 프로그램을 구축하기 위한 전략을 수립하는 데 도움이됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-130">[Using Azure with GxP Systems](https://aka.ms/GXP-Azure-Strategies): Help for life science organizations in establishing a strategy for building GxP applications.</span></span>
- <span data-ttu-id="dbb9e-131">FDA CFR Title 21 Part 11 가이드: 전자 기록에 대한 FDA 지침을 준수하는 [Azure](https://aka.ms/Azure-FDA-Guidelines) 및 [Office 365](https://resources.techcommunity.microsoft.com/wp-content/uploads/2019/05/Microsoft-Office-365-GxP-Guidelines.pdf) 인증 전략 수립에 대한 도움을 받으세요.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-131">FDA CFR Title 21 Part 11 Guides: Get help establishing an [Azure](https://aka.ms/Azure-FDA-Guidelines) and [Office 365](https://resources.techcommunity.microsoft.com/wp-content/uploads/2019/05/Microsoft-Office-365-GxP-Guidelines.pdf) qualification strategy that complies with FDA guidelines for electronic records.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="dbb9e-132">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="dbb9e-132">Frequently asked questions</span></span>

<span data-ttu-id="dbb9e-133">**조직의 GxP 규정 준수 노력에 Microsoft GxP 규정 준수를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="dbb9e-133">**Can I use Microsoft GxP compliance in my organization's GxP compliance efforts?**</span></span>

<span data-ttu-id="dbb9e-134">Azure에 응용 프로그램을 배포하는 고객은 의도 된 용도에 따라 컴퓨터 시스템에 적용되는 GxP 요구 사항을 확인한 다음 자격 및 유효성 검사 프로세스를 관리하는 내부 절차를 따라 해당 요구 사항을 충족했음을 증명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-134">Customers deploying applications on Azure should determine the GxP requirements that apply to their computerized systems based on the intended use and then follow internal procedures governing qualification and validation processes to demonstrate that they have met those requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="dbb9e-135">리소스</span><span class="sxs-lookup"><span data-stu-id="dbb9e-135">Resources</span></span>

- [<span data-ttu-id="dbb9e-136">Microsoft와 FDA CFR Title 21 Part 11</span><span class="sxs-lookup"><span data-stu-id="dbb9e-136">Microsoft and FDA CFR Title 21 Part 11</span></span>](offering-fda-cfr-title-21-part-11.md)
- [<span data-ttu-id="dbb9e-137">Microsoft와 ISO/IEC 27001</span><span class="sxs-lookup"><span data-stu-id="dbb9e-137">Microsoft and ISO/IEC 27001</span></span>](offering-iso-27001.md)
- [<span data-ttu-id="dbb9e-138">Microsoft와 ISO 9001</span><span class="sxs-lookup"><span data-stu-id="dbb9e-138">Microsoft and ISO 9001</span></span>](offering-iso-9001.md)
- [<span data-ttu-id="dbb9e-139">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="dbb9e-139">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="dbb9e-140">제공 사항의 배경 설명 다운로드</span><span class="sxs-lookup"><span data-stu-id="dbb9e-140">Download the offering backgrounder</span></span>

<span data-ttu-id="dbb9e-141">이 제공 사항에 대한 배경 설명 문서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="dbb9e-141">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="dbb9e-142">[PDF](https://download.microsoft.com/download/4/5/B/45B4B144-E0D0-432E-A210-B8AF841F9A0A/GXP-Compliance.pdf)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb9e-142">Download the [PDF](https://download.microsoft.com/download/4/5/B/45B4B144-E0D0-432E-A210-B8AF841F9A0A/GXP-Compliance.pdf).</span></span>
