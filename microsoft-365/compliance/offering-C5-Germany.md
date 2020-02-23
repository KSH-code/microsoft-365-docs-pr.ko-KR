---
title: 클라우드 컴퓨팅 규정 준수 컨트롤 카탈로그(C5)
description: Azure, Azure Government 및 Azure Germany가 C5(클라우드 컴퓨팅 규정 준수 컨트롤 카달로그)에 대한 규정 준수를 증명하는 방법을 알아보십시오.
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
ms.openlocfilehash: 837dda3a506a2ba2a743b1aed89a5c004a4fb163
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228554"
---
# <a name="cloud-computing-compliance-controls-catalog-c5"></a><span data-ttu-id="51e4c-104">클라우드 컴퓨팅 규정 준수 컨트롤 카탈로그(C5)</span><span class="sxs-lookup"><span data-stu-id="51e4c-104">Cloud Computing Compliance Controls Catalog (C5)</span></span>

## <a name="c5-overview"></a><span data-ttu-id="51e4c-105">C5 개요</span><span class="sxs-lookup"><span data-stu-id="51e4c-105">C5 overview</span></span>

<span data-ttu-id="51e4c-106">2016에서 정보 보안을 위한 독일어 (Bundesamt für Sicherheit, BSI)는 클라우드 컴퓨팅 준수 컨트롤 카탈로그 (C5)를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-106">In 2016, the German Federal Office for Information Security (Bundesamt für Sicherheit in der Informationstechnik, or BSI) created the Cloud Computing Compliance Controls Catalog (C5).</span></span> <span data-ttu-id="51e4c-107">C5는 감사 표준으로, 클라우드 보안을 위한 필수 최소 기준을 설정하고 독일 정부 기관 및 정부와 협력하는 조직의 퍼블릭 클라우드 솔루션 채택을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-107">C5 is an audited standard that establishes a mandatory minimum baseline for cloud security and the adoption of public cloud solutions by German government agencies and organizations that work with government.</span></span> <span data-ttu-id="51e4c-108">또한 C5는 민간 부문에서도 도입 사례가 점차 늘고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-108">C5 is also being increasingly adopted by the private sector.</span></span>

<span data-ttu-id="51e4c-109">C5 요구 사항 카탈로그의 목적은 클라우드 서비스 공급자를 인증하기 위한 일관된 보안 프레임워크를 제공하고 고객에게 데이터가 안전하게 관리된다는 확신을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-109">The purpose of the C5 catalog of requirements is to provide a consistent security framework for certifying cloud service providers and to give customers assurance that their data will be managed securely.</span></span>

<span data-ttu-id="51e4c-110">C5는 ISO/IEC 27001:2013, 클라우드 보안 제휴 클라우드 컨트롤 매트릭스 3.0.1 및 BSI의 IT-Grundschutz 카달로그와 같은 국제적으로 유명한 보안 표준을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-110">C5 is based on internationally recognized IT security standards like ISO/IEC 27001:2013, the Cloud Security Alliance Cloud Controls Matrix 3.0.1, and BSI’s own IT-Grundschutz Catalogues.</span></span> <span data-ttu-id="51e4c-111">이 카탈로그는 17개의 도메인(예: 정보 보안 및 물리적 보안 조직)에 대한 114개의 요구 사항으로 구성되어 있으며 모든 클라우드 서비스 제공자의 기본 보안 요구 사항과 기밀성이 높은 데이터 및 고가용성이 필요한 상황을 처리하기 위한 추가 요구 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-111">The catalog consists of 114 requirements across 17 domains — for example, the organization of information security and physical security — with security requirements basic to all cloud service providers, and additional requirements for processing highly confidential data and situations requiring high availability.</span></span>

<span data-ttu-id="51e4c-112">또한 BSI는 투명성에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-112">The BSI also puts emphasis on transparency.</span></span> <span data-ttu-id="51e4c-113">감사의 일환으로, 클라우드 제공자는 상세한 시스템 설명을 포함하고 관할권 및 데이터 처리 위치, 서비스 제공 및 클라우드 서비스에 발행된 기타 인증과 같은 환경 매개 변수와 클라우드 제공자의 공공기관에 대한 공개 의무에 대한 정보를 공개해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-113">As part of an audit, the cloud provider must include a detailed system description and disclose environmental parameters like jurisdiction and data processing location, provision of services, and other certifications issued to the cloud services, and information about the cloud provider’s disclosure obligations to public authorities.</span></span> <span data-ttu-id="51e4c-114">이를 통해 잠재적인 클라우드 고객은 클라우드 서비스가 데이터 보호, 회사 정책 또는 산업 스파이의 위협을 해결하는 기능과 같은 법적 요구 사항 준수와 같은 필수 요구 사항을 충족하는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-114">This helps potential cloud customers decide whether the cloud services meet their essential requirements such as compliance with legal requirements like data protection, company policies, or the ability to address the threat of industrial espionage.</span></span>

## <a name="microsoft-and-c5"></a><span data-ttu-id="51e4c-115">Microsoft와 C5</span><span class="sxs-lookup"><span data-stu-id="51e4c-115">Microsoft and C5</span></span>

<span data-ttu-id="51e4c-116">SOC 2(AT Section 101) 표준에 따라 Microsoft 클라우드 서비스를 적어도 매년 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-116">Microsoft cloud services are audited at least annually against SOC 2 (AT Section 101) standards.</span></span> <span data-ttu-id="51e4c-117">BSI에 따르면 C5 감사는 SOC 2 감사와 결합되어 시스템 설명의 일부 및 겹치는 컨트롤에 대한 감사 결과를 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-117">According to BSI, a C5 audit can be combined with a SOC 2 audit to reuse parts of the system description and audit results for overlapping controls.</span></span> <span data-ttu-id="51e4c-118">Microsoft Azure, Azure Government 및 Azure Germany는 독립 감사원이 수행한 감사 평가를 기반으로 C5 준수 여부를 증명하는 결합된 보고서(C5, SOC 2 유형 2, CSA STAR 증명)를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-118">Microsoft Azure, Azure Government, and Azure Germany maintain a combined report (C5, SOC 2 Type 2, CSA STAR Attestation) based on the audit assessment performed by an independent auditor, which demonstrates proof of compliance with C5.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="51e4c-119">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="51e4c-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="51e4c-120">Azure, Azure Government, Azure Germany</span><span class="sxs-lookup"><span data-stu-id="51e4c-120">Azure, Azure Government, and Azure Germany</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="51e4c-121">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="51e4c-121">Office 365 Germany</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="51e4c-122">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="51e4c-122">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="51e4c-123">Azure, Azure Government, 및 Azure Germany SOC 2 유형 II 보고서.pdf</span><span class="sxs-lookup"><span data-stu-id="51e4c-123">Azure, Azure Government, and Azure Germany SOC 2 Type II Report.pdf</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2093520)

## <a name="frequently-asked-questions"></a><span data-ttu-id="51e4c-124">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="51e4c-124">Frequently asked questions</span></span>

<span data-ttu-id="51e4c-125">**사용자가 C5에 대한 Microsoft 규정 준수를 사용하여 조직에서 자신의 C5 증명을 받을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="51e4c-125">**Can I use Microsoft compliance with C5 to help my organization get its own C5 attestation?**</span></span>

<span data-ttu-id="51e4c-126">예.</span><span class="sxs-lookup"><span data-stu-id="51e4c-126">Yes.</span></span> <span data-ttu-id="51e4c-127">C5가 요구되는 프로그램이나 이니셔티브에 대한 기초로서 Microsoft 클라우드 서비스의 증명을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-127">You may use the attestation of Microsoft cloud services as the foundation for any program or initiative that requires C5.</span></span> <span data-ttu-id="51e4c-128">그러나 이러한 서비스 외부에 있거나 이러한 서비스에 구축 된 구성 요소에 대해서 자체적인 C5 증명을 달성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-128">However, you need to achieve your own C5 attestation for components outside or built on top of these services.</span></span>

<span data-ttu-id="51e4c-129">**C5와 IT-Grundschutz 카탈로그의 차이점은 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="51e4c-129">**What’s the difference between C5 and the IT-Grundschutz Catalogues?**</span></span>

<span data-ttu-id="51e4c-130">IT-Grundschutz는 조직이 IT 시스템에 대한 보안 조치를 식별하고 구현하는 데 도움이 되는 특정 방법론을 제공하며 C5 표준이 구축되는 요소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-130">IT-Grundschutz supplies the specific methodology to help organizations identify and implement security measures for IT systems and is one of the elements upon which the C5 standards are built.</span></span> <span data-ttu-id="51e4c-131">C5는 클라우드 서비스 제공자를 위한 일련의 감사 표준을 제공하지만 구현 세부 사항은 클라우드 서비스 제공자에 맡깁니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-131">C5 provides a set of audit standards for cloud service providers but leaves the details of implementation up to the cloud service provider.</span></span>

<span data-ttu-id="51e4c-132">**Microsoft Cloud Germany 란 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="51e4c-132">**What is Microsoft Cloud Germany?**</span></span>

<span data-ttu-id="51e4c-133">Microsoft Cloud Germany는 독일에 물리적으로 기반을 두고 있으며 독일 개인 정보 보호법의 요구 사항을 준수하며, 다른 국가로의 개인 데이터 전송을 제한하고, 국내 법률을 위반할 수 있는 다른 관할 구역으로부터 당국에 의한 액세스를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-133">Microsoft Cloud Germany is physically based in Germany, adhering to the requirement of German privacy law, which limits the transfer of personal data to other countries and offers protection against access by authorities from other jurisdictions who could violate domestic laws.</span></span> <span data-ttu-id="51e4c-134">Azure Germany는 독일의 데이터 상주가 있는 독일 데이터 센터의 Azure 서비스를 제공하며 독일 법률에 따라 통제되는 고유한 데이터 피신탁 모델을 통해 제공되는 엄격한 데이터 액세스 및 제어 수단을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-134">Azure Germany delivers Azure services from German datacenters with data residency in Germany, and it delivers strict data access and control measures provided through a unique data trustee model governed under German law.</span></span>

## <a name="resources"></a><span data-ttu-id="51e4c-135">리소스</span><span class="sxs-lookup"><span data-stu-id="51e4c-135">Resources</span></span>

- <span data-ttu-id="51e4c-136">클라우드 컴퓨팅 규정 준수 컨트롤 카탈로그(C5) ([영어](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Criteria_Catalogue/Compliance_Criteria_Catalogue_node.html)) ([독일어](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Kriterienkatalog/Kriterienkatalog_node.html))</span><span class="sxs-lookup"><span data-stu-id="51e4c-136">Cloud Computing Compliance Controls Catalogue (C5) ([English](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Criteria_Catalogue/Compliance_Criteria_Catalogue_node.html)) ([German](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Kriterienkatalog/Kriterienkatalog_node.html))</span></span>
- <span data-ttu-id="51e4c-137">클라우드 컴퓨팅 공급자에 대한 보안 권장 사항([영어](https://www.bsi.bund.de/EN/Topics/CloudComputing/Secure_use_of_cloud_services/Secure_use_cloud_services_node.html)) ([독일어](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Sichere_Nutzung_Cloud/Sichere_Nutzung_Cloud_node.html))</span><span class="sxs-lookup"><span data-stu-id="51e4c-137">Security Recommendations for Cloud Computing Providers ([English](https://www.bsi.bund.de/EN/Topics/CloudComputing/Secure_use_of_cloud_services/Secure_use_cloud_services_node.html)) ([German](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Sichere_Nutzung_Cloud/Sichere_Nutzung_Cloud_node.html))</span></span>
- [<span data-ttu-id="51e4c-138">준수 보고서: C5-und SOC-Testate Azure 독일</span><span class="sxs-lookup"><span data-stu-id="51e4c-138">Compliance Reports: C5- und SOC-Testate Azure Deutschland</span></span>](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=df100ae1-baf9-4785-8a6d-864c0bc5c308&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)
- <span data-ttu-id="51e4c-139">Microsoft Azure Germany용 [IT-Grundschutz 규정 준수 통합 문서](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7)</span><span class="sxs-lookup"><span data-stu-id="51e4c-139">[IT-Grundschutz Compliance Workbook](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7) for Microsoft Azure Germany</span></span>
- [<span data-ttu-id="51e4c-140">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="51e4c-140">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="51e4c-141">제공 사항의 배경 설명 다운로드</span><span class="sxs-lookup"><span data-stu-id="51e4c-141">Download the offering backgrounder</span></span>

<span data-ttu-id="51e4c-142">이 제공 사항에 대한 배경 설명 문서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="51e4c-142">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="51e4c-143">[PDF](https://download.microsoft.com/download/E/F/6/EF619A4D-C17C-4279-8DC4-79C0620676AB/C5Germany-Compliance.pdf)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="51e4c-143">Download the [PDF](https://download.microsoft.com/download/E/F/6/EF619A4D-C17C-4279-8DC4-79C0620676AB/C5Germany-Compliance.pdf).</span></span>
