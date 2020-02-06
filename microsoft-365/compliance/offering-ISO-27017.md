---
title: ISO/IEC 27017:2015 정보 보안 통제를 위한 규약
description: Microsoft 클라우드 서비스는 정보 보안 통제를 위해 이 규약을 구현했습니다.
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
ms.openlocfilehash: 6bd989a5600252ee60ada4eb4e3d1414ef3853d5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602245"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="2014a-104">ISO/IEC 27017:2015 정보 보안 통제를 위한 규약</span><span class="sxs-lookup"><span data-stu-id="2014a-104">ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="2014a-105">ISO-IEC 27017 개요</span><span class="sxs-lookup"><span data-stu-id="2014a-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="2014a-106">ISO/IEC 27017:2015 규약은 조직에서 ISO/IEC 27002:2013에 기초한 클라우드 컴퓨팅 정보 보안 관리 시스템을 구축할 때 클라우드 서비스 정보 보안 통제를 선택하기 위해 참조로 사용하도록 고안된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="2014a-107">또한 클라우드 서비스 공급자의 경우, 일반적으로 승인되는 보호 통제 장치를 구축하기 위한 지침 문서로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="2014a-108">이 국제 표준은 ISO/IEC 27002에 기초한 클라우드 구현 지침을 추가로 제공하고, 규제, 구현 지침 및 기타 정보에 대한 ISO/IEC 27002: 2013 의 5항부터 18항과 관련하여 클라우드 정보 보안 위협과 위험을 해결하기 위한 추가 규제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="2014a-109">특히 이 표준은 ISO/IEC 27002의 37개 규제에 대한 지침을 제공하며, ISO/IEC 27002에 중복되지 않은 7가지의 새로운 규제를 특별히 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="2014a-110">이러한 새 규제는 다음과 같은 중요 영역에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="2014a-111">클라우드 컴퓨팅 환경에서의 공유 역할과 책임</span><span class="sxs-lookup"><span data-stu-id="2014a-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="2014a-112">계약 종료 시 클라우드 서비스 고객 자산의 제거와 반환</span><span class="sxs-lookup"><span data-stu-id="2014a-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="2014a-113">한 고객의 가상 환경과 다른 고객의 가상 환경의 분리 및 보호</span><span class="sxs-lookup"><span data-stu-id="2014a-113">Protection and separation of a customer’s virtual environment from that of other customers</span></span>
- <span data-ttu-id="2014a-114">비즈니스 요구를 충족하기 위한 가상 컴퓨터 강화 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2014a-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="2014a-115">클라우드 컴퓨팅 환경의 관리 작업 절차</span><span class="sxs-lookup"><span data-stu-id="2014a-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="2014a-116">고객이 클라우드 컴퓨팅 환경 내의 관련 활동을 모니터링할 수 있도록 지원</span><span class="sxs-lookup"><span data-stu-id="2014a-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="2014a-117">가상 네트워크와 물리적 네트워크의 보안 관리 일관성 유지</span><span class="sxs-lookup"><span data-stu-id="2014a-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="2014a-118">Microsoft와 ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="2014a-118">Microsoft and ISO/IEC 27017</span></span>

<span data-ttu-id="2014a-119">ISO/IEC 27017은 클라우드 서비스 공급자 및 클라우드 서비스 고객을 위한 지침을 제공하는 고유한 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="2014a-120">또한 클라우드 서비스 고객이 클라우드 서비스 공급자에게 어떤 것을 바랄 수 있는지에 대한 실용적인 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="2014a-121">고객은 클라우드를 이용한 공유의 책임을 이해함으로써 ISO/IEC 27017로부터 직접적인 혜택을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

<span data-ttu-id="2014a-122">Microsoft 클라우드에서 ISO/IEC 27017 의 혜택에 대해 알아보세요. [ISO/IEC 27017: 정보 보안 통제를 위한 규약 다운로드](https://aka.ms/iso27017-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="2014a-122">Learn about the benefits of ISO/IEC 27017 on the Microsoft Cloud: [Download the ISO/IEC 27017: Code of Practice for Information Security Controls](https://aka.ms/iso27017-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="2014a-123">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="2014a-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="2014a-124">Azure, Azure Government, Azure Germany</span><span class="sxs-lookup"><span data-stu-id="2014a-124">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="2014a-125">클라우드 앱 보안</span><span class="sxs-lookup"><span data-stu-id="2014a-125">Cloud App Security</span></span>
- [<span data-ttu-id="2014a-126">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2014a-126">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="2014a-127">Genomics</span><span class="sxs-lookup"><span data-stu-id="2014a-127">Genomics</span></span>
- <span data-ttu-id="2014a-128">그래프</span><span class="sxs-lookup"><span data-stu-id="2014a-128">Graph</span></span>
- <span data-ttu-id="2014a-129">Intune</span><span class="sxs-lookup"><span data-stu-id="2014a-129">Intune</span></span>
- <span data-ttu-id="2014a-130">Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2014a-130">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="2014a-131">독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Microsoft Flow 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="2014a-131">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="2014a-132">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, 및 Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="2014a-132">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, and Office 365 Germany</span></span>
- <span data-ttu-id="2014a-133">독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 PowerApps 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="2014a-133">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="2014a-134">독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="2014a-134">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="2014a-135">Office 365에서 적용되는 서비스에 대한 [자세한 목록](https://go.microsoft.com/fwlink/p/?linkid=2077751)보기</span><span class="sxs-lookup"><span data-stu-id="2014a-135">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="2014a-136">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="2014a-136">Audits, reports, and certificates</span></span>

<span data-ttu-id="2014a-137">Microsoft 클라우드 서비스는 ISO/IEC 27001:2013에 대한 인증 프로세스의 일부로서 ISO/IEC 27017:2015 규약에 대해 1년에 한 번씩 감사를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-137">Microsoft cloud services are audited once a year for the ISO/IEC 27017:2015 code of practice as part of the certification process for ISO/IEC 27001:2013.</span></span>

- [<span data-ttu-id="2014a-138">Azure ISO 27017 인증서</span><span class="sxs-lookup"><span data-stu-id="2014a-138">Azure ISO 27017 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [<span data-ttu-id="2014a-139">Azure ISO 27017 평가 보고서</span><span class="sxs-lookup"><span data-stu-id="2014a-139">Azure ISO 27017 Assessment report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [<span data-ttu-id="2014a-140">Azure ISO 27017 적용성 보고서</span><span class="sxs-lookup"><span data-stu-id="2014a-140">Azure ISO 27017 Statement of Applicability</span></span>](https://aka.ms/AzureISO27017StatementofApplicability)
- [<span data-ttu-id="2014a-141">Office 365 ISO 27001, 27018, and 27017 감사 평가 보고서</span><span class="sxs-lookup"><span data-stu-id="2014a-141">Office 365 ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="2014a-142">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="2014a-142">Frequently asked questions</span></span>

<span data-ttu-id="2014a-143">이 표준은 누구에게 적용됩니까?</span><span class="sxs-lookup"><span data-stu-id="2014a-143">To whom does the standard apply?</span></span>

<span data-ttu-id="2014a-144">이 규약은 클라우드 서비스 공급자 및 클라우드 서비스 고객 모두에게 규제 및 구현 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-144">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="2014a-145">ISO/IEC 27002:2013과 유사한 형식으로 작성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-145">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="2014a-146">**ISO/IEC 27017:2015에 대한 Microsoft의 규정 준수 정보는 어디에서 확인할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="2014a-146">**Where can I view Microsoft’s compliance information for ISO/IEC 27017:2015?**</span></span>

<span data-ttu-id="2014a-147">Azure, Intune, Power BI에 대한 [ISO/IEC 27017:2015 인증서](https://aka.ms/azureiso27017)를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-147">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="2014a-148">**우리 회사의 인증 프로세스에 Microsoft의 ISO/IEC 27017 규정 준수를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="2014a-148">**Can I use the ISO/IEC 27017 compliance of Microsoft services in my organization’s certification process?**</span></span>

<span data-ttu-id="2014a-149">예.</span><span class="sxs-lookup"><span data-stu-id="2014a-149">Yes.</span></span> <span data-ttu-id="2014a-150">Microsoft 범위 내 엔터프라이즈 클라우드 서비스에 배포되는 구현에 대해 인증을 받아야 하는 고객은 규정 준수 평가 시 Microsoft의 관련 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-150">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="2014a-151">하지만 구현에 대한 규정 준수를 평가하기 위한 평가자와의 계약과 고유 조직 내 통제 수단 및 프로세스에 대해서는 파트너가 책임을 져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-151">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="2014a-152">**적용되는 감사 보고서 사본을 구하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="2014a-152">**How can I get copies of the applicable audit reports?**</span></span>

<span data-ttu-id="2014a-153">[Service Trust Portal](https://aka.ms/stphelp)에서는 제3의 독립 기관 감사 보고서와 기타 관련 문서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-153">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="2014a-154">이 포털을 이용하여 자체 규제 요건에 도움이 되는 문서를 다운로드하고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-154">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="2014a-155">리소스</span><span class="sxs-lookup"><span data-stu-id="2014a-155">Resources</span></span>

- [<span data-ttu-id="2014a-156">ISO/IEC 27017:2015 규약</span><span class="sxs-lookup"><span data-stu-id="2014a-156">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="2014a-157">Microsoft 온라인 서비스 사용 약관</span><span class="sxs-lookup"><span data-stu-id="2014a-157">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="2014a-158">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="2014a-158">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="2014a-159">제공 사항의 배경 설명 다운로드</span><span class="sxs-lookup"><span data-stu-id="2014a-159">Download the offering backgrounder</span></span>

<span data-ttu-id="2014a-160">이 제공 사항에 대한 배경 설명 문서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="2014a-160">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="2014a-161">[PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2014a-161">Download the [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span></span>
