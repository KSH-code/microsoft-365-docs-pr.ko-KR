---
title: PCI(Payment Card Industry) DSS(Data Security Standard)
description: Azure, SharePoint Online 및 비즈니스용 OneDrive는 Payment Card Industry Data Security 표준 수준 1 버전 3.2를 준수합니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: cb4d1a4c4632763506fd2d3b05431acb9233f744
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071973"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a><span data-ttu-id="9f95a-104">PCI(Payment Card Industry) DSS(Data Security Standard)</span><span class="sxs-lookup"><span data-stu-id="9f95a-104">Payment Card Industry (PCI) Data Security Standard (DSS)</span></span>

## <a name="pci-dss-overview"></a><span data-ttu-id="9f95a-105">PCI DSS 개요</span><span class="sxs-lookup"><span data-stu-id="9f95a-105">PCI DSS overview</span></span>

<span data-ttu-id="9f95a-p101">지급 카드 산업(PCI) 데이터 보안 표준(DSS)는 신용 카드 데이터 통제 수준을 높여 사기를 방지하도록 디자인 된 글로벌 정보 보안 표준입니다. 만약 5대 대형 신용 카드사- 미자, 마스터카드, 아메리칸 익스프레스, 디스커버 및 JCB의 신용 카드 지급을 승인하려면 모든 조직은 크기에 상관 없이 PCI DSS 표준을 따라야 합니다. 지급 및 카드 소유주 데이터를 저장, 처리 혹은 전달 하는 모든 조직은 PCI DSS를 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p101">The Payment Card Industry (PCI) Data Security Standards (DSS) is a global information security standard designed to prevent fraud through increased control of credit card data. Organizations of all sizes must follow PCI DSS standards if they accept payment cards from the five major credit card brands — Visa, MasterCard, American Express, Discover, and the Japan Credit Bureau (JCB). Compliance with PCI DSS is required for any organization that stores, processes, or transmits payment and cardholder data.</span></span>

## <a name="microsoft-and-pci-dss"></a><span data-ttu-id="9f95a-109">Microsoft와 PCI DSS</span><span class="sxs-lookup"><span data-stu-id="9f95a-109">Microsoft and PCI DSS</span></span>

<span data-ttu-id="9f95a-p102">Microsoft는 적격 품질 검사자(QSA)의 승인을 사용하여 연간 PCI DSS 평가를 완료 했습니다. 감사가 인프라, 개발, 운영, 관리 지원 및 서비스 범위 확인 등을 포함하는 Microsoft Azure, 비즈니스용 Microsoft OneDrive 및 Microsoft SharePoint Online 환경을 검토하였습니다. PCI DSS는 거래 규모에 따라 4단계의 준수 수준을 지정합니다. Azure, 비즈니스용 OneDrive 및 SharePoint Online은 서비스 제공자 레벨 1(최대 거래 규모 - 연간 6백만건 이상)에서 PCI DSS 버전 3.2 준수 인증을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p102">Microsoft completed an annual PCI DSS assessment using an approved Qualified Security Assessor (QSA). The auditors reviewed Microsoft Azure, Microsoft OneDrive for Business, and Microsoft SharePoint Online  environments, which include validating the infrastructure, development, operations, management, support, and in-scope services. The PCI DSS designates four levels of compliance based on transaction volume. Azure, OneDrive for Business, and SharePoint Online are certified as compliant under PCI DSS version 3.2 at Service Provider Level 1 (the highest volume of transactions — more than 6 million a year).</span></span>

<span data-ttu-id="9f95a-p103">평가 결과는 고객에게 제공되고 QSA가 의해 준수 보고서(RoC)를 발행하는 규정 준수 증명서(AoC)로 제공됩니다. 준수 결과는 감사를 통과하고 검사자로부터 AoC를 발급받고 AoC에 서명되어 있는 날짜로부터 1년 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p103">The assessment results in an Attestation of Compliance (AoC), which is available to customers and Report on Compliance (RoC) issued by the QSA. The effective period for compliance begins upon passing the audit and receiving the AoC from the assessor and ends one year from the date the AoC is signed.</span></span> 

<span data-ttu-id="9f95a-116">카드 데이터 전용 네트워크(CDE) 또는 카드 처리 서비스를 개발하려는 고객은 많은 기본적인 부분에서 이러한 검증을 사용할 수 있습니다. 이를 통해 자체적으로 PCI DSS 인증을 얻기 위한 관련된 작업과 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-116">Customers who want to develop a cardholder environment or card processing service can use these validations in many of the underlying portions, thereby reducing the associated effort and costs of getting their own PCI DSS certification.</span></span>

<span data-ttu-id="9f95a-p104">Azure, 비즈니스용 OneDrive 및 SharePoint Online는 이 플랫폼을 사용하는 사용자가 빌드 혹은 호스트 하는 서비스를 PCI DSS 인증서로 자동으로 번역 하지 않기 때문에 PCI DSS 준수 상태를 이해하는 것은 중요합니다. 사용자는 PCI DSS 요구 사항을 준수 할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p104">It is important to understand that PCI DSS compliance status for Azure, OneDrive for Business, and SharePoint Online not automatically translate to PCI DSS certification for the services that customers build or host on these platforms. Customers are responsible for ensuring that they achieve compliance with PCI DSS requirements.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="9f95a-119">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="9f95a-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="9f95a-120">Azure 및 Azure Government</span><span class="sxs-lookup"><span data-stu-id="9f95a-120">Azure and Azure Government</span></span>](https://azure.microsoft.com/global-infrastructure/government/)
- <span data-ttu-id="9f95a-121">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9f95a-121">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="9f95a-122">독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Flow 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="9f95a-122">Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="9f95a-123">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="9f95a-123">Microsoft Graph</span></span>
- <span data-ttu-id="9f95a-124">Intune</span><span class="sxs-lookup"><span data-stu-id="9f95a-124">Intune</span></span>
- [<span data-ttu-id="9f95a-125">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9f95a-125">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- <span data-ttu-id="9f95a-126">독립 실행형 서비스 혹은 Office 365 또는 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 PowerApps 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="9f95a-126">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="9f95a-127">독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="9f95a-127">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="9f95a-128">비즈니스용 OneDrive 및 SharePoint Online(미국에만 해당)</span><span class="sxs-lookup"><span data-stu-id="9f95a-128">OneDrive for Business and SharePoint Online (United States only)</span></span>

## <a name="audit-reports-and-certificates"></a><span data-ttu-id="9f95a-129">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="9f95a-129">Audit, reports, and certificates</span></span>

- [<span data-ttu-id="9f95a-130">Azure PCI DSS 준수 증명(AoC)</span><span class="sxs-lookup"><span data-stu-id="9f95a-130">Azure PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/azure-pci)
- [<span data-ttu-id="9f95a-131">비즈니스용 OneDrive 및 SharePoint Online PCI DSS 준수 증명(AoC)</span><span class="sxs-lookup"><span data-stu-id="9f95a-131">OneDrive for Business and SharePoint Online PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a><span data-ttu-id="9f95a-132">Azure에서 실행되는 PCI DSS 솔루션 받기</span><span class="sxs-lookup"><span data-stu-id="9f95a-132">Get your PCI DSS solution running on Azure</span></span>

<span data-ttu-id="9f95a-p105">Azure 보안 및 PCI DSS 준수 청사진으로 PCI DSS 솔루션을 클라우드에서 더 빠르게 빌드하고 배포해보세요. 참고 아키텍처, 배포 지침, 수행 매핑 통제, 자동 스크립트 등을 얻어보세요. [Azure PCI DSS 청사진을 사용하여 시작하기](https://aka.ms/pciblueprint).</span><span class="sxs-lookup"><span data-stu-id="9f95a-p105">Build and deploy your PCI DSS solution in the cloud even faster with the Azure Security and Compliance PCI DSS Blueprint. Get reference architectures, deployment guidance, control implementation mappings, automated scripts and more. [Start using the Azure PCI DSS Blueprint](https://aka.ms/pciblueprint).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9f95a-136">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="9f95a-136">Frequently asked questions</span></span>

<span data-ttu-id="9f95a-137">**AoC(Attestation on Compliance) 표지 페이지에 ‘2018년 6월’이 표시된 이유는 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="9f95a-137">**Why does the Attestation of Compliance (AoC) cover page say 'June 2018'?**</span></span>

<span data-ttu-id="9f95a-p106">커버 페이지의 2018년 6월 날짜는 AoC 서식 파일이 게시된 날짜입니다. 평가 날짜는 섹션 2를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p106">The June 2018 date on the cover page is when the AoC template was published. Refer to Section 2 for the date of the assessment.</span></span>

<span data-ttu-id="9f95a-140">**Azure 규정 준수 증명서가 여러 개인 이유는 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="9f95a-140">**Why are there multiple Azure Attestations of Compliance (AoCs)?**</span></span>

<span data-ttu-id="9f95a-p107">Azure AoC 패키지에는 Azure 공개, 독일, 정부 클라우드에 해당하는 AoC가 있습니다. 고객은 Azure 환경에 해당하는 AoC를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p107">The Azure AoC package has AoCs corresponding to Azure Public, Germany, and Government cloud. Customers should use the AoC that corresponds with their Azure environment.</span></span>  

<span data-ttu-id="9f95a-143">**PA DSS와 PCI DSS는 서로 어떤 관계인가요?**</span><span class="sxs-lookup"><span data-stu-id="9f95a-143">**What is the relationship between the PA DSS and PCI DSS?**</span></span>

<span data-ttu-id="9f95a-p108">지급 응용 프로그램 데이터 보안 표준(PA DSS)는 PCI DSS를 준수하고 비자의 지급 응용 프로그램 모범 사례를 대체하며 다른 주 카드 발행자에 대한 준수 요구 사항을 통합하는 일련의 요구 사합니다. PA DSS는 소프트웨어 공급자가 타드 인증 혹은 정산 절차의 일환으로 카드 소유자 및 지급 데이터를 저장, 처리 혹은 전달 하는 제3자 응용 프로그램 개발을 할 수 있도록 도와줍니다. 소매 업체는 효율적은 PCI DSS 준수를 위하여 PA DSS 인증 응용 프로그램을 사용해야 합니다. PA DSS는 Azure에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p108">The Payment Application Data Security Standard (PA DSS) is a set of requirements that comply with the PCI DSS, and replaces Visa's Payment Application Best Practices, and consolidates the compliance requirements of the other primary card issuers. The PA DSS helps software vendors develop third-party applications that store, process, or transmit cardholder payment data as part of a card authorization or settlement process. Retailers must use PA DSS certified applications to efficiently achieve their PCI DSS compliance. The PA DSS does not apply to Azure.</span></span>

<span data-ttu-id="9f95a-148">**전표 매입 업체란 무엇인가요? Azure는 매입업체를 이용하나요?**</span><span class="sxs-lookup"><span data-stu-id="9f95a-148">**What is an acquirer and does Azure use one?**</span></span>

<span data-ttu-id="9f95a-p109">전표 매입 업체 카드 지급 거래를 수행하는 은행 혹은 다른 주체입니다. Azure는 지급 카드 처리를 서비스로 제공하지 않기 때문에 전표 매입 업체를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p109">An acquirer is a bank or other entity that processes payment card transactions. Azure does not offer payment card processing as a service and thus does not use an acquirer.</span></span>

<span data-ttu-id="9f95a-151">**PCI DSS는 어떤 회사 및 판매자에게 적용되나요?**</span><span class="sxs-lookup"><span data-stu-id="9f95a-151">**To what organizations and merchants does the PCI DSS apply?**</span></span>

<span data-ttu-id="9f95a-p110">PCI DSS는 회사의 규모 혹은 카드 소유자 데이터를 승인, 전달 혹은 저장 하는 수에 상관 없이 모든 회사에 적용됩니다. 어떤 고객이 신용카드나 직불 카드를 사용하여 회사에 결제를 하면 PCI DSS 요구사항이 적용된다는 의미입니다. 총 12개월간의 회사의 총 거래 규모에 기반하여 4단계 중 한 단계가 적용됩니다. 레벨 1은 1년에 총 6백만건 이상의 거래를 하는 회사를 의미하고, 레벨 2는 1백만건 이상 6백만건 이하의 거래, 레벨 3은 2만이상 1백만건 이상의 거래, 레벨 4는 2만건 미만의 거래를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p110">PCI DSS applies to any company, no matter the size, or number of transactions, that accepts, transmits, or stores cardholder data. That is, if any customer ever pays a company using a credit or debit card, then the PCI DSS requirements apply. Companies are validated at one of four levels based on the total transaction volume over a 12-month period. Level 1 is for companies that process over 6 million transactions a year; Level 2 for 1 million to 6 million transactions; Level 3 is for 20,000 to 1 million transactions; and Level 4 is for fewer than 20,000 transactions.</span></span>

<span data-ttu-id="9f95a-156">**Azure에 배포된 솔루션에 대한 우리 회사의 PCI DSS 규정 준수 활동은 어느 것부터 시작해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="9f95a-156">**Where do I begin my organization's PCI DSS compliance efforts for a solution deployed on Azure?**</span></span>

<span data-ttu-id="9f95a-p111">PCI 보안 표준 위원회는 특정 준수 요구사항을 알기 위한 좋은 정보를 제공합니다. 위원회는 상인과 다른 지불 카드 처리 관련자들을 위하여 [PCI DSS 빠른 참고 가이드](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)를 발간합니다. 이 가이드는 PCI DSS가 지불 카드 거래 환경을 보호하는 방법과 이를 적용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p111">The information that the PCI Security Standards Council makes available is a good place to learn about specific compliance requirements. The council publishes the [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) for merchants and others involved in payment card processing. The guide explains how the PCI DSS can help protect a payment card transaction environment and how to apply it.</span></span>

<span data-ttu-id="9f95a-p112">준수에는 Azure에서 호스트 하지 않는 시스템을 평가하고 처리하는 것을 포함하여 다양한 요소가 적용됩니다. 어떤 Azure 서비스를 사용하는지에 따라 그리고 솔루션내에서 사용되는 방식에 따라 요구 사항이 상이합니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p112">Compliance involves several factors, including assessing the systems and processes not hosted on Azure. Individual requirements vary based on which Azure services are used and how they are employed within the solution.</span></span>

<span data-ttu-id="9f95a-162">**비즈니스용 OneDrive 및 SharePoint Online가 미국 이외의 지역에서 PCI DSS를 준수할 계획이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="9f95a-162">**Are there plans for OneDrive for Business and SharePoint Online to be PCI DSS-compliant outside of the United States?**</span></span>

<span data-ttu-id="9f95a-p113">현재 비즈니스용 OneDrive 및 SharePoint Online은 미국에서만 PCI DSS 준수 대상입니다. Microsoft는 미국 외 지역에 요구되는 사항과 요구 시기를 평가하고 다른 지역이 로드맵에 추가된다면 그 때 업데이트를 제공할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p113">Currently OneDrive for Business and SharePoint Online is PCI-DSS compliant only in the United States (US). Microsoft will evaluate the requirements and timelines for regions outside of US and provide updates when and if other regions are added to the roadmap.</span></span>

<span data-ttu-id="9f95a-165">**무엇이 비즈니스용 OneDrive 및 SharePoint Online 범위 내에 있나요?**</span><span class="sxs-lookup"><span data-stu-id="9f95a-165">**What is in-scope for OneDrive for Business and SharePoint Online?**</span></span>

<span data-ttu-id="9f95a-166">현재 비즈니스용 OneDrive 및 SharePoint Online에 업로드된 파일과 문서만 PCI DSS를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-166">Currently, only files and documents uploaded to OneDrive for Business and SharePoint Online will be complaint with PCI DSS.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="9f95a-167">Microsoft 준수 관리자를 사용하여 위험 평가</span><span class="sxs-lookup"><span data-stu-id="9f95a-167">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="9f95a-p114">[Microsoft 준수 관리자](compliance-manager.md)는 사용자 조직의 준수 상태를 이해하고 위험을 줄이기 위한 활동에 도움을 주는 [Microsoft 365 규정 준수 센터](microsoft-365-compliance-center.md)의 기능입니다. 준수 관리자는 이 규정에 관한 평가를 작성하기 위한 프리미엄 문서 서식을 제공합니다. 준수 관리자의 **평가 문서 서식 페이지** 에서 문서 서식을 찾을 수 있습니다. [준수 관리자에서 평가를 빌드](compliance-manager-assessments.md)하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9f95a-p114">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks. Compliance Manager offers a premium template for building an assessment for this regulation. Find the template in the **assessment templates** page in Compliance Manager. Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="9f95a-172">리소스</span><span class="sxs-lookup"><span data-stu-id="9f95a-172">Resources</span></span>

- [<span data-ttu-id="9f95a-173">PCI 보안 표준 심의회(영문)</span><span class="sxs-lookup"><span data-stu-id="9f95a-173">PCI Security Standards Council</span></span>](https://www.pcisecuritystandards.org/)
- [<span data-ttu-id="9f95a-174">PCI 데이터 보안 표준(영문)</span><span class="sxs-lookup"><span data-stu-id="9f95a-174">PCI Data Security Standard</span></span>](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [<span data-ttu-id="9f95a-175">Azure PCI DSS 3.2.1 청사진</span><span class="sxs-lookup"><span data-stu-id="9f95a-175">Azure PCI DSS 3.2.1 Blueprint</span></span>](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [<span data-ttu-id="9f95a-176">PCI DSS 빠른 참조 설명서(영문)</span><span class="sxs-lookup"><span data-stu-id="9f95a-176">PCI DSS Quick Reference Guide</span></span>](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [<span data-ttu-id="9f95a-177">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="9f95a-177">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
