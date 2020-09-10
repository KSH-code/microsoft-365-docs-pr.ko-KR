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
ms.openlocfilehash: ad755398afc80f829561854217f1295ce8fff6f5
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417862"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a><span data-ttu-id="67ac6-104">PCI(Payment Card Industry) DSS(Data Security Standard)</span><span class="sxs-lookup"><span data-stu-id="67ac6-104">Payment Card Industry (PCI) Data Security Standard (DSS)</span></span>

## <a name="pci-dss-overview"></a><span data-ttu-id="67ac6-105">PCI DSS 개요</span><span class="sxs-lookup"><span data-stu-id="67ac6-105">PCI DSS overview</span></span>

<span data-ttu-id="67ac6-106">PCI(Payment Card Industry) DSS(Data Security Standard)는 신용 카드 데이터에 대한 통제를 강화하여 사기를 방지하도록 고안된 글로벌 정보 보안 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-106">The Payment Card Industry (PCI) Data Security Standards (DSS) is a global information security standard designed to prevent fraud through increased control of credit card data.</span></span> <span data-ttu-id="67ac6-107">모든 규모의 조직은 Visa, MasterCard, American Express, Discover, JCB(Japan Credit Bureau) 등 5개 주요 신용 카드 브랜드의 결제 카드를 수락한 경우 PCI DSS 표준을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-107">Organizations of all sizes must follow PCI DSS standards if they accept payment cards from the five major credit card brands — Visa, MasterCard, American Express, Discover, and the Japan Credit Bureau (JCB).</span></span> <span data-ttu-id="67ac6-108">지불 및 카드 소유자 데이터를 저장, 처리 또는 전송하는 모든 조직은 PCI DSS를 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-108">Compliance with PCI DSS is required for any organization that stores, processes, or transmits payment and cardholder data.</span></span>

## <a name="microsoft-and-pci-dss"></a><span data-ttu-id="67ac6-109">Microsoft와 PCI DSS</span><span class="sxs-lookup"><span data-stu-id="67ac6-109">Microsoft and PCI DSS</span></span>

<span data-ttu-id="67ac6-110">Microsoft는 승인된 QSA(Qualified Security Assessor)를 사용하여 연간 PCI DSS 평가를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-110">Microsoft completed an annual PCI DSS assessment using an approved Qualified Security Assessor (QSA).</span></span> <span data-ttu-id="67ac6-111">감사자는 인프라, 개발, 운영, 관리, 지원 및 범위 내 서비스 검증을 포함하여 Microsoft Azure, 비즈니스용 Microsoft OneDrive 및 Microsoft SharePoint Online 환경을 검토했습니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-111">The auditors reviewed Microsoft Azure, Microsoft OneDrive for Business, and Microsoft SharePoint Online  environments, which include validating the infrastructure, development, operations, management, support, and in-scope services.</span></span> <span data-ttu-id="67ac6-112">PCI DSS에서는 거래량을 기준으로 네 가지 규정 준수 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-112">The PCI DSS designates four levels of compliance based on transaction volume.</span></span> <span data-ttu-id="67ac6-113">Azure, 비즈니스용 OneDrive, SharePoint Online은 PCI DSS 버전 3.2의 서비스 공급자 수준 1(연간 6백만 개 이상의 최고 거래량) 규정 준수 인증을 획득했습니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-113">Azure, OneDrive for Business, and SharePoint Online are certified as compliant under PCI DSS version 3.2 at Service Provider Level 1 (the highest volume of transactions — more than 6 million a year).</span></span>

<span data-ttu-id="67ac6-114">고객이 열람 가능한 QSA에서 발행한 AoC(Attestation on Compliance) 및 규정 준수 보고서의 평가 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-114">The assessment results in an Attestation of Compliance (AoC), which is available to customers and Report on Compliance (RoC) issued by the QSA.</span></span> <span data-ttu-id="67ac6-115">규정 준수에 대한 유효 기간은 감사를 통과하여 평가자로부터 AoC를 받은 시점부터 AoC에 서명한 날짜가 포함된 연도의 말일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-115">The effective period for compliance begins upon passing the audit and receiving the AoC from the assessor and ends one year from the date the AoC is signed.</span></span> 

<span data-ttu-id="67ac6-116">카드 데이터 전용 네트워크(CDE) 또는 카드 처리 서비스를 개발하려는 고객은 많은 기본적인 부분에서 이러한 검증을 사용할 수 있습니다. 이를 통해 자체적으로 PCI DSS 인증을 얻기 위한 관련된 작업과 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-116">Customers who want to develop a cardholder environment or card processing service can use these validations in many of the underlying portions, thereby reducing the associated effort and costs of getting their own PCI DSS certification.</span></span>

<span data-ttu-id="67ac6-117">Azure, 비즈니스용 OneDrive, SharePoint Online의 PCI DSS 규정 준수 상태가 고객이 이러한 플랫폼에서 빌드하거나 호스팅하는 서비스에 대한 PCI DSS 인증으로 자동으로 전환되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-117">It is important to understand that PCI DSS compliance status for Azure, OneDrive for Business, and SharePoint Online not automatically translate to PCI DSS certification for the services that customers build or host on these platforms.</span></span> <span data-ttu-id="67ac6-118">고객은 일부 PCI DSS 요구 사항을 준수하는지 확인해야 할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-118">Customers are responsible for ensuring that they achieve compliance with PCI DSS requirements.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="67ac6-119">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="67ac6-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="67ac6-120">Azure 및 Azure Government</span><span class="sxs-lookup"><span data-stu-id="67ac6-120">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="67ac6-121">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="67ac6-121">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="67ac6-122">독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Flow 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="67ac6-122">Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="67ac6-123">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="67ac6-123">Microsoft Graph</span></span>
- <span data-ttu-id="67ac6-124">Intune</span><span class="sxs-lookup"><span data-stu-id="67ac6-124">Intune</span></span>
- [<span data-ttu-id="67ac6-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="67ac6-125">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- <span data-ttu-id="67ac6-126">독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 PowerApps 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="67ac6-126">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="67ac6-127">독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="67ac6-127">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="67ac6-128">비즈니스용 OneDrive 및 SharePoint Online(미국에만 해당)</span><span class="sxs-lookup"><span data-stu-id="67ac6-128">OneDrive for Business and SharePoint Online (United States only)</span></span>

## <a name="audit-reports-and-certificates"></a><span data-ttu-id="67ac6-129">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="67ac6-129">Audit, reports, and certificates</span></span>

- [<span data-ttu-id="67ac6-130">Azure PCI DSS 준수 증명(AoC)</span><span class="sxs-lookup"><span data-stu-id="67ac6-130">Azure PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/azure-pci)
- [<span data-ttu-id="67ac6-131">비즈니스용 OneDrive 및 SharePoint Online PCI DSS 준수 증명(AoC)</span><span class="sxs-lookup"><span data-stu-id="67ac6-131">OneDrive for Business and SharePoint Online PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a><span data-ttu-id="67ac6-132">Azure에서 실행되는 PCI DSS 솔루션 받기</span><span class="sxs-lookup"><span data-stu-id="67ac6-132">Get your PCI DSS solution running on Azure</span></span>

<span data-ttu-id="67ac6-133">Azure 보안 및 준수 PCI DSS 청사진을 사용하여 클라우드에서 PCI DSS 솔루션을 더 빠르게 빌드하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-133">Build and deploy your PCI DSS solution in the cloud even faster with the Azure Security and Compliance PCI DSS Blueprint.</span></span> <span data-ttu-id="67ac6-134">참조 아키텍처, 배포 지침, 제어 구현 매핑, 자동화된 스크립트 등을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-134">Get reference architectures, deployment guidance, control implementation mappings, automated scripts and more.</span></span> <span data-ttu-id="67ac6-135">[Azure PCI DSS 청사진 사용 시작하기](https://aka.ms/pciblueprint)</span><span class="sxs-lookup"><span data-stu-id="67ac6-135">[Start using the Azure PCI DSS Blueprint](https://aka.ms/pciblueprint).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="67ac6-136">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="67ac6-136">Frequently asked questions</span></span>

<span data-ttu-id="67ac6-137">**AoC(Attestation on Compliance) 표지 페이지에 "2018년 6월"이 표시된 이유는 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="67ac6-137">**Why does the Attestation of Compliance (AoC) cover page say “June 2018”?**</span></span>

<span data-ttu-id="67ac6-138">표지 페이지의 날짜 2018년 6월은 AoC 서식 파일이 게시된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-138">The June 2018 date on the cover page is when the AoC template was published.</span></span> <span data-ttu-id="67ac6-139">평가 날짜는 2조를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ac6-139">Refer to Section 2 for the date of the assessment.</span></span>

<span data-ttu-id="67ac6-140">**Azure 규정 준수 증명서가 여러 개인 이유는 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="67ac6-140">**Why are there multiple Azure Attestations of Compliance (AoCs)?**</span></span>

<span data-ttu-id="67ac6-141">Azure AoC 패키지에는 Azure Public, Germany, 클라우드에 해당하는 Aoc가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-141">The Azure AoC package has AoCs corresponding to Azure Public, Germany, and Government cloud.</span></span> <span data-ttu-id="67ac6-142">고객은 고객의 Azure 환경에 해당하는 AoC를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-142">Customers should use the AoC that corresponds with their Azure environment.</span></span>  

<span data-ttu-id="67ac6-143">**PA DSS와 PCI DSS는 서로 어떤 관계인가요?**</span><span class="sxs-lookup"><span data-stu-id="67ac6-143">**What is the relationship between the PA DSS and PCI DSS?**</span></span>

<span data-ttu-id="67ac6-144">PA DSS(Payment Application Data Security Standard)는 PCI DSS를 준수하고, Visa의 지불 응용 프로그램 모범 사례를 대체하고, 다른 주요 카드 발급자의 규정 준수(compliance) 요건을 통합하는 요건 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-144">The Payment Application Data Security Standard (PA DSS) is a set of requirements that comply with the PCI DSS, and replaces Visa’s Payment Application Best Practices, and consolidates the compliance requirements of the other primary card issuers.</span></span> <span data-ttu-id="67ac6-145">소프트웨어 공급업체에서는 PA DSS에 따라 카드 인증 또는 결제 프로세스의 일환으로 카드 소유자 지불 데이터를 저장, 처리 또는 전송하는 타사 응용 프로그램을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-145">The PA DSS helps software vendors develop third-party applications that store, process, or transmit cardholder payment data as part of a card authorization or settlement process.</span></span> <span data-ttu-id="67ac6-146">소매업체에서는 PCI DSS 규정을 효율적으로 준수하려면 PA DSS 인증 응용 프로그램을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-146">Retailers must use PA DSS certified applications to efficiently achieve their PCI DSS compliance.</span></span> <span data-ttu-id="67ac6-147">PA DSS는 Azure에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-147">The PA DSS does not apply to Azure.</span></span>

<span data-ttu-id="67ac6-148">**전표 매입업체란 무엇인가요? Azure는 매입업체를 이용하나요?**</span><span class="sxs-lookup"><span data-stu-id="67ac6-148">**What is an acquirer and does Azure use one?**</span></span>

<span data-ttu-id="67ac6-149">전표 매입업체란 결제 카드 거래를 처리하는 은행 또는 기타 기관입니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-149">An acquirer is a bank or other entity that processes payment card transactions.</span></span> <span data-ttu-id="67ac6-150">Azure는 카드 결제 처리 서비스를 제공하지 않으므로 전표 매입업체를 이용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-150">Azure does not offer payment card processing as a service and thus does not use an acquirer.</span></span>

<span data-ttu-id="67ac6-151">**PCI DSS는 어떤 회사 및 판매자에게 적용되나요?**</span><span class="sxs-lookup"><span data-stu-id="67ac6-151">**To what organizations and merchants does the PCI DSS apply?**</span></span>

<span data-ttu-id="67ac6-152">거래의 규모나 수에 상관없이 카드 소유자 데이터를 수락, 전송 또는 저장하는 모든 회사에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-152">PCI DSS applies to any company, no matter the size, or number of transactions, that accepts, transmits, or stores cardholder data.</span></span> <span data-ttu-id="67ac6-153">즉, 고객이 신용 카드 또는 직불 카드를 사용하여 회사에 지불하는 경우 PCI DSS 요구 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-153">That is, if any customer ever pays a company using a credit or debit card, then the PCI DSS requirements apply.</span></span> <span data-ttu-id="67ac6-154">기업은 12개월 동안의 총 거래량을 기준으로 네 가지 수준 중 하나로 검증됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-154">Companies are validated at one of four levels based on the total transaction volume over a 12-month period.</span></span> <span data-ttu-id="67ac6-155">연간 처리하는 거래 건수가 600만 건 초과인 기업은 수준 1, 100만 ~ 600만 건인 기업은 수준 2, 2만 ~ 1백만 건인 기업은 수준 3, 2만 건 미만인 기업은 수준 4에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-155">Level 1 is for companies that process over 6 million transactions a year; Level 2 for 1 million to 6 million transactions; Level 3 is for 20,000 to 1 million transactions; and Level 4 is for fewer than 20,000 transactions.</span></span>

<span data-ttu-id="67ac6-156">**Azure에 배포된 솔루션에 대한 우리 회사의 PCI DSS 규정 준수 활동은 어느 것부터 시작해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="67ac6-156">**Where do I begin my organization’s PCI DSS compliance efforts for a solution deployed on Azure?**</span></span>

<span data-ttu-id="67ac6-157">특정 규정 준수(compliance) 요건에 대한 자세한 내용은 PCI 보안 표준 심의회에서 제공하는 정보를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67ac6-157">The information that the PCI Security Standards Council makes available is a good place to learn about specific compliance requirements.</span></span> <span data-ttu-id="67ac6-158">위원회는 결제 카드 처리에 포함되는 판매자 및 기타 당사자를 대상으로 하는 [PCI DSS 빠른 참조 설명서(영문)](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)를 발행합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-158">The council publishes the [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) for merchants and others involved in payment card processing.</span></span> <span data-ttu-id="67ac6-159">이 설명서는 PCI DSS를 통해 결제 카드 거래 환경을 보호하고 PCI DSS를 적용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-159">The guide explains how the PCI DSS can help protect a payment card transaction environment and how to apply it.</span></span>

<span data-ttu-id="67ac6-160">규정 준수는 Azure에서 호스팅되지 않는 시스템 및 프로세스 평가를 비롯한 많은 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-160">Compliance involves several factors, including assessing the systems and processes not hosted on Azure.</span></span> <span data-ttu-id="67ac6-161">개별 요구 사항은 사용되는 Azure 서비스와 Azure가 솔루션에서 사용되는 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-161">Individual requirements vary based on which Azure services are used and how they are employed within the solution.</span></span>

<span data-ttu-id="67ac6-162">**비즈니스용 OneDrive 및 SharePoint Online가 미국 이외의 지역에서 PCI DSS를 준수할 계획이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="67ac6-162">**Are there plans for OneDrive for Business and SharePoint Online to be PCI DSS-compliant outside of the United States?**</span></span>

<span data-ttu-id="67ac6-163">현재 비즈니스용 OneDrive 및 SharePoint Online은 미국(US)에서만 PCI-DSS를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-163">Currently OneDrive for Business and SharePoint Online is PCI-DSS compliant only in the United States (US).</span></span> <span data-ttu-id="67ac6-164">Microsoft는 미국 이외의 지역에 대한 요구 사항과 타임라인을 평가하고 다른 지역이 로드맵에 추가되면 업데이트를 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-164">Microsoft will evaluate the requirements and timelines for regions outside of US and provide updates when and if other regions are added to the roadmap.</span></span>

<span data-ttu-id="67ac6-165">**무엇이 비즈니스용 OneDrive 및 SharePoint Online 범위 내에 있나요?**</span><span class="sxs-lookup"><span data-stu-id="67ac6-165">**What is in-scope for OneDrive for Business and SharePoint Online?**</span></span>

<span data-ttu-id="67ac6-166">현재 비즈니스용 OneDrive 및 SharePoint Online에 업로드된 파일과 문서만 PCI DSS를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="67ac6-166">Currently, only files and documents uploaded to OneDrive for Business and SharePoint Online will be complaint with PCI DSS.</span></span>

## <a name="resources"></a><span data-ttu-id="67ac6-167">리소스</span><span class="sxs-lookup"><span data-stu-id="67ac6-167">Resources</span></span>

- [<span data-ttu-id="67ac6-168">PCI 보안 표준 심의회(영문)</span><span class="sxs-lookup"><span data-stu-id="67ac6-168">PCI Security Standards Council</span></span>](https://www.pcisecuritystandards.org/)
- [<span data-ttu-id="67ac6-169">PCI 데이터 보안 표준(영문)</span><span class="sxs-lookup"><span data-stu-id="67ac6-169">PCI Data Security Standard</span></span>](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [<span data-ttu-id="67ac6-170">Azure PCI DSS 3.2.1 청사진</span><span class="sxs-lookup"><span data-stu-id="67ac6-170">Azure PCI DSS 3.2.1 Blueprint</span></span>](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [<span data-ttu-id="67ac6-171">PCI DSS 빠른 참조 설명서(영문)</span><span class="sxs-lookup"><span data-stu-id="67ac6-171">PCI DSS Quick Reference Guide</span></span>](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [<span data-ttu-id="67ac6-172">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="67ac6-172">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
