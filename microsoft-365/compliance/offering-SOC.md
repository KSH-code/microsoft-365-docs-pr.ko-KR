---
title: SOC(서비스 조직 컨트롤)
description: Microsoft 클라우드 서비스는 운영 보안에 대한 서비스 조직 컨트롤 표준을 준수합니다.
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
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 380e1b2fadc48c395fbd8c2b10c0d65a6ba01675
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40804261"
---
# <a name="service-organization-controls-soc"></a><span data-ttu-id="0fdff-104">SOC(서비스 조직 컨트롤)</span><span class="sxs-lookup"><span data-stu-id="0fdff-104">Service Organization Controls (SOC)</span></span>

## <a name="soc-1-2-and-3-reports-overview"></a><span data-ttu-id="0fdff-105">SOC 1, 2 및 3 보고서 개요</span><span class="sxs-lookup"><span data-stu-id="0fdff-105">SOC 1, 2, and 3 Reports overview</span></span>

<span data-ttu-id="0fdff-106">점차적으로 기업에서는 데이터 저장소, 응용 프로그램 액세스 등과 같은 기본 기능을 CSP(클라우드 서비스 공급자) 및 기타 서비스 조직에 아웃소싱합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-106">Increasingly, businesses outsource basic functions such as data storage and access to applications to cloud service providers (CSPs) and other service organizations.</span></span> <span data-ttu-id="0fdff-107">이에 대응하여 AICPA(American Institute of Certified Public Accountants)는 클라우드에서 저장 및 처리되는 정보의 기밀성과 개인 정보를 보호하는 제어 표준인 SOC(Service Organization Controls) 프레임워크를 개발했습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-107">In response, the American Institute of Certified Public Accountants (AICPA) has developed the Service Organization Controls (SOC) framework, a standard for controls that safeguard the confidentiality and privacy of information stored and processed in the cloud.</span></span> <span data-ttu-id="0fdff-108">이 프레임워크는 국제 서비스 조직에 대한 보고 표준인 ISAE(International Standard on Assurance Engagements)을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-108">This aligns with the International Standard on Assurance Engagements (ISAE), the reporting standard for international service organizations.</span></span>

<span data-ttu-id="0fdff-109">SOC 프레임워크를 기반으로 하는 서비스 감사는 범위 내 Microsoft 클라우드 서비스에 적용되는 두 범주(SOC 1 및 SOC 2)로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-109">Service audits based on the SOC framework fall into two categories — SOC 1 and SOC 2 — that apply to in-scope Microsoft cloud services.</span></span>

<span data-ttu-id="0fdff-110">재무 제표를 감사하는 CPA 회사를 위한 SOC 1 감사에서는 공급자의 클라우드 서비스를 사용하는 고객의 재무 보고서에 영향을 주는 CPA 내부 통제 수단의 유효성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-110">A SOC 1 audit, intended for CPA firms that audit financial statements, evaluates the effectiveness of a CSP’s internal controls that affect the financial reports of a customer using the provider’s cloud services.</span></span> <span data-ttu-id="0fdff-111">SSAE(Statement on Standards for Attestation Engagements) 18 및 ISAE 3402(International Standards for Assurance</span><span class="sxs-lookup"><span data-stu-id="0fdff-111">The Statement on Standards for Attestation Engagements (SSAE 18) and the International Standards for Assurance Engagements No.</span></span> <span data-ttu-id="0fdff-112">Engagements No. 3402)는 감사 수행 및 SOC 1 보고서의 기반이 되는 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-112">3402 (ISAE 3402) are the standards under which the audit is performed, and is the basis of the SOC 1 report.</span></span>

<span data-ttu-id="0fdff-113">SOC 2 감사에서는 AICPA 트러스트 서비스 원칙 및 기준을 기반으로 CSP 시스템의 유효성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-113">A SOC 2 audit gauges the effectiveness of a CSP’s system based on the AICPA Trust Service Principles and Criteria.</span></span> <span data-ttu-id="0fdff-114">SOC 2 및 SOC 3 보고서는 Attest Engagement under Attestation Standards(AT) 제101조를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-114">An Attest Engagement under Attestation Standards (AT) Section 101 is the basis of SOC 2 and SOC 3 reports.</span></span>

<span data-ttu-id="0fdff-115">SOC 1 또는 SOC 2 감사를 마치면서 서비스 감사자는 CSP 시스템을 설명하고 통제 수단에 대한 CSP 설명의 공정성을 평가하는 의견을 SOC 1 유형 2 또는 SOC 2 유형 2 보고서에 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-115">At the conclusion of a SOC 1 or SOC 2 audit, the service auditor renders an opinion in a SOC 1 Type 2 or SOC 2 Type 2 report, which describes the CSP’s system and assesses the fairness of the CSP’s description of its controls.</span></span> <span data-ttu-id="0fdff-116">또한 CSP의 통제 수단이 적절히 설계되었는지, 지정된 날짜에 시행되었는지, 지정된 기간 동안 효율적으로 시행되었는지 여부를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-116">It also evaluates whether the CSP’s controls are designed appropriately, were in operation on a specified date, and were operating effectively over a specified time period.</span></span>

<span data-ttu-id="0fdff-117">또한 감사자는 CSP 통제 수단에 대한 보장을 원하지만 전체 SOC 2 보고서는 필요 없는 사용자를 위해 SOC 2 유형 2 감사 보고서를 축약한 SOC 3 보고서를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-117">Auditors can also create a SOC 3 report — an abbreviated version of the SOC 2 Type 2 audit report — for users who want assurance about the CSP’s controls but don’t need a full SOC 2 report.</span></span> <span data-ttu-id="0fdff-118">단, CSP에 SOC 2에 대해 부적격 감사 의견이 있는 경우에만 SOC 3 보고서를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-118">A SOC 3 report can be conferred only if the CSP has an unqualified audit opinion for SOC 2.</span></span>

## <a name="microsoft-and-soc-1-2-and-3-reports"></a><span data-ttu-id="0fdff-119">Microsoft 및 SOC 1, 2 및 3 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-119">Microsoft and SOC 1, 2, and 3 Reports</span></span>

<span data-ttu-id="0fdff-120">독립된 타사 감사자가 SOC 보고 프레임워크에 따라 Microsoft가 제공하는 클라우드 서비스를 최소 매년 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-120">Microsoft covered cloud services are audited at least annually against the SOC reporting framework by independent third-party auditors.</span></span> <span data-ttu-id="0fdff-121">Microsoft 클라우드 서비스에 대한 감사에는 각 서비스에 대한 범위 내 트러스트 원칙에 적용되는 데이터 보안, 가용성, 처리 무결성, 기밀성 등에 대한 통제 수단이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-121">The audit for Microsoft cloud services covers controls for data security, availability, processing integrity, and confidentiality as applicable to in-scope trust principles for each service.</span></span>

<span data-ttu-id="0fdff-122">Microsoft는 SOC 1 유형 2, SOC 2 유형 2 및 SOC 3 보고서를 완성했습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-122">Microsoft has achieved SOC 1 Type 2, SOC 2 Type 2, and SOC 3 reports.</span></span> <span data-ttu-id="0fdff-123">일반적으로 SOC 1 및 SOC 2 보고서는 Microsoft와 비밀 유지 계약을 체결한 고객만 사용할 수 있고, SOC 3 보고서는 공개적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-123">In general, the availability of SOC 1 and SOC 2 reports is restricted to customers who have signed nondisclosure agreements with Microsoft; the SOC 3 report is publicly available.</span></span>

<span data-ttu-id="0fdff-124">Microsoft 클라우드에서 SOC 1, 2, 3의 이점에 대해 자세히 알아보세요. [SOC 1 및 SOC 2 유형 2 보고서 다운로드](https://aka.ms/soc_backgrounder)</span><span class="sxs-lookup"><span data-stu-id="0fdff-124">Learn about the benefits of SOC 1, 2, 3 on the Microsoft Cloud: [Download the SOC 1 and SOC 2 type 2 reports backgrounder](https://aka.ms/soc_backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="0fdff-125">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="0fdff-125">Microsoft in-scope cloud services</span></span>

### <a name="covered-services-for-soc-1-and-soc-2"></a><span data-ttu-id="0fdff-126">SOC 1 및 SOC 2에 대해 적용되는 서비스</span><span class="sxs-lookup"><span data-stu-id="0fdff-126">Covered services for SOC 1 and SOC 2</span></span>

- <span data-ttu-id="0fdff-127">Azure, Azure Government, Azure Germany [상세 목록](https://aka.ms/AzureCompliance)</span><span class="sxs-lookup"><span data-stu-id="0fdff-127">Azure, Azure Government, and Azure Germany [detailed list](https://aka.ms/AzureCompliance)</span></span>
- <span data-ttu-id="0fdff-128">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0fdff-128">Cloud App Security</span></span>
- <span data-ttu-id="0fdff-129">Dynamics 365 및 Dynamics 365 U.S. Government [상세 목록](https://aka.ms/d365-compliance-list)</span><span class="sxs-lookup"><span data-stu-id="0fdff-129">Dynamics 365 and Dynamics 365 U.S. Government [detailed list](https://aka.ms/d365-compliance-list)</span></span>
- <span data-ttu-id="0fdff-130">Graph</span><span class="sxs-lookup"><span data-stu-id="0fdff-130">Graph</span></span>
- <span data-ttu-id="0fdff-131">Intune</span><span class="sxs-lookup"><span data-stu-id="0fdff-131">Intune</span></span>
- <span data-ttu-id="0fdff-132">독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Microsoft Flow 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="0fdff-132">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="0fdff-133">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense [상세 목록](https://go.microsoft.com/fwlink/p/?LinkID=2077751) Yammer는 SOC 1 유형 1 보고서를 달성했습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-133">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense [detailed list](https://go.microsoft.com/fwlink/p/?LinkID=2077751); Yammer has achieved a SOC 1 Type 1 report</span></span>
- <span data-ttu-id="0fdff-134">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="0fdff-134">Office 365 Germany</span></span>
- <span data-ttu-id="0fdff-135">독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 PowerApps 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="0fdff-135">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="0fdff-136">독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="0fdff-136">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="0fdff-137">Stream</span><span class="sxs-lookup"><span data-stu-id="0fdff-137">Stream</span></span>
- <span data-ttu-id="0fdff-138">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="0fdff-138">Azure DevOps Services</span></span>

### <a name="covered-services-for-soc-3"></a><span data-ttu-id="0fdff-139">SOC 3에 대해 적용되는 서비스</span><span class="sxs-lookup"><span data-stu-id="0fdff-139">Covered services for SOC 3</span></span>

- <span data-ttu-id="0fdff-140">Azure, Azure Government, Azure Germany [상세 목록](https://aka.ms/AzureCompliance)</span><span class="sxs-lookup"><span data-stu-id="0fdff-140">Azure, Azure Government, and Azure Germany [detailed list](https://aka.ms/AzureCompliance)</span></span>
- <span data-ttu-id="0fdff-141">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0fdff-141">Cloud App Security</span></span>
- <span data-ttu-id="0fdff-142">그래프</span><span class="sxs-lookup"><span data-stu-id="0fdff-142">Graph</span></span>
- <span data-ttu-id="0fdff-143">Intune</span><span class="sxs-lookup"><span data-stu-id="0fdff-143">Intune</span></span>
- <span data-ttu-id="0fdff-144">독립 실행형 서비스로서 또는 Office 365나 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Microsoft Flow 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="0fdff-144">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="0fdff-145">독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 PowerApps 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="0fdff-145">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="0fdff-146">Power BI</span><span class="sxs-lookup"><span data-stu-id="0fdff-146">Power BI</span></span>
- <span data-ttu-id="0fdff-147">Stream</span><span class="sxs-lookup"><span data-stu-id="0fdff-147">Stream</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="0fdff-148">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="0fdff-148">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="0fdff-149">감사 주기</span><span class="sxs-lookup"><span data-stu-id="0fdff-149">Audit cycle</span></span>

<span data-ttu-id="0fdff-150">SOC 1 (SSAE18, ISAE 3402) 및 SOC 2 (AT Section 101) 표준에 따라 Microsoft 클라우드 서비스를 적어도 매년 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-150">Microsoft cloud services are audited at least annually against SOC 1 (SSAE18, ISAE 3402) and SOC 2 (AT Section 101) standards.</span></span>

#### <a name="azure-cloud-app-security-flow-graph-intune-power-bi-powerapps-stream-and-microsoft-datacenters"></a><span data-ttu-id="0fdff-151">Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, Microsoft Datacenters</span><span class="sxs-lookup"><span data-stu-id="0fdff-151">Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters</span></span>

- [<span data-ttu-id="0fdff-152">Azure 및 Azure Government SOC 1 유형 2 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-152">Azure and Azure Government SOC 1 Type 2 Report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2099601)
- [<span data-ttu-id="0fdff-153">Azure 및 Azure Government SOC 2 유형 2 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-153">Azure and Azure Government SOC 2 Type 2 Report</span></span>](https://aka.ms/azuresoc2auditreport)
- [<span data-ttu-id="0fdff-154">Azure 및 Azure Government SOC 3 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-154">Azure and Azure Government SOC 3 Report</span></span>](https://aka.ms/azuresoc3auditreport)

#### <a name="dynamics-365"></a><span data-ttu-id="0fdff-155">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0fdff-155">Dynamics 365</span></span>

- [<span data-ttu-id="0fdff-156">Dynamics 365 SOC 1 유형 2 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-156">Dynamics 365 SOC 1 Type 2 Report</span></span>](https://aka.ms/Dynamics365SOC1AuditReport)
- [<span data-ttu-id="0fdff-157">Dynamics 365 SOC 2 AT 101 유형 II 감사 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-157">Dynamics 365 SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/Dynamics365SOC2AuditReport)
- [<span data-ttu-id="0fdff-158">브리지 레터 및 추가 감사 보고서를 참조하기</span><span class="sxs-lookup"><span data-stu-id="0fdff-158">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

#### <a name="office-365"></a><span data-ttu-id="0fdff-159">Office 365</span><span class="sxs-lookup"><span data-stu-id="0fdff-159">Office 365</span></span>

- [<span data-ttu-id="0fdff-160">Office 365 SOC 1 SSAE 16 유형 II 감사 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-160">Office 365 SOC 1 SSAE 16 Type II Audit Report</span></span>](https://aka.ms/office365soc1auditreport)
- [<span data-ttu-id="0fdff-161">Office 365 SOC 2 AT 101 유형 II 감사 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-161">Office 365 SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/Office365SOC2AuditReport)
- [<span data-ttu-id="0fdff-162">Office 365 Customer Lockbox SOC 1 SSAE 16 감사 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-162">Office 365 Customer Lockbox SOC 1 SSAE 16 Audit Report</span></span>](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [<span data-ttu-id="0fdff-163">Yammer SOC 2 AT 101 유형 II 감사 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-163">Yammer SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/YammerSOC2AuditReport)
- [<span data-ttu-id="0fdff-164">Yammer SOC 2 AT 101 유형 I 감사 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-164">Yammer SOC 2 AT 101 Type I Audit Report</span></span>](https://aka.ms/YammerSOC2Type1AuditReport)
- [<span data-ttu-id="0fdff-165">브리지 레터 및 추가 감사 보고서를 참조하기</span><span class="sxs-lookup"><span data-stu-id="0fdff-165">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a><span data-ttu-id="0fdff-166">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="0fdff-166">Frequently asked questions</span></span>

<span data-ttu-id="0fdff-167">**SOC 보고서 사본을 구하려면 어떻게 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="0fdff-167">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="0fdff-168">감사자 검색에서는 보고서에서 Microsoft 비즈니스 클라우드 서비스 결과를 파트너의 법률 및 규정 요구 사항과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-168">With the reports, your auditors can compare Microsoft business cloud services results with your own legal and regulatory requirements.</span></span>

- <span data-ttu-id="0fdff-169">[서비스 트러스트 플랫폼](https://www.microsoft.com/trustcenter/STP/default.aspx)를 통해 모든 SOC 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-169">You can see all SOC reports through the [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx).</span></span>
- <span data-ttu-id="0fdff-170">[서비스 트러스트 플랫폼](https://www.microsoft.com/trustcenter/STP/default.aspx)에 액세스할 수 없는 Azure DevOps 서비스 고객은 SOC 1 및 SOC 2 보고서를 위해 [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com)에 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-170">Azure DevOps Service customers that can’t access [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) can email [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) for its SOC 1 and SOC 2 reports.</span></span> <span data-ttu-id="0fdff-171">이 전자 메일은 Azure DevOps SOC 보고서만 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-171">This email is to request Azure DevOps SOC reports only.</span></span>

<span data-ttu-id="0fdff-172">**Azure SOC 보고서는 얼마나 자주 발행되나요?**</span><span class="sxs-lookup"><span data-stu-id="0fdff-172">**How often are Azure SOC reports issued?**</span></span>

<span data-ttu-id="0fdff-173">Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream 및 Microsoft Datacenters에 대한 SOC 보고서는 과거 12개월 연속 실행 기간(감사 기간)을 기반으로 하고 1년에 두 번 새 보고서가 발행됩니다.(기간 종료은 3월 31일과 9월 30일)</span><span class="sxs-lookup"><span data-stu-id="0fdff-173">SOC reports for Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters are based on a rolling 12-month run window (audit period) with new reports issued quarterly.</span></span> <span data-ttu-id="0fdff-174">브리지 레터는 10/1~12/31을 커버하는 1월과 4/16~6/30의 기간을 커버하는 7월에 발행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-174">Bridge letters are issued in January to cover the period of 10/1 – 12/31 and July to cover the period of 4/1 – 6/30.</span></span> <span data-ttu-id="0fdff-175">고객은 Service Trust Portal에서 최신 보고서를 [다운로드](https://aka.ms/stp)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-175">Customers can [download](https://aka.ms/stp) the latest reports from the Service Trust Portal.</span></span>

<span data-ttu-id="0fdff-176">**Microsoft 데이터 센터에 대한 자체 감사를 실시해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="0fdff-176">**Do I need to conduct my own audit of Microsoft datacenters?**</span></span>

<span data-ttu-id="0fdff-177">아니요.</span><span class="sxs-lookup"><span data-stu-id="0fdff-177">No.</span></span> <span data-ttu-id="0fdff-178">Microsoft는 독립 감사 보고서 및 인증을 고객과 공유하여 Microsoft가 보안 약속을 지키는지를 확인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-178">Microsoft shares the independent audit reports and certifications with customers so that they can verify Microsoft compliance with its security commitments.</span></span>

<span data-ttu-id="0fdff-179">**우리 회사의 인증 프로세스에 Microsoft의 규정 준수를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="0fdff-179">**Can I use Microsoft’s compliance in my organization’s certification process?**</span></span>

<span data-ttu-id="0fdff-180">예.</span><span class="sxs-lookup"><span data-stu-id="0fdff-180">Yes.</span></span> <span data-ttu-id="0fdff-181">응용 프로그램 및 데이터를 적용 대상 Microsoft 클라우드 서비스로 마이그레이션하면 Microsoft에서 보유한 감사 및 인증을 획득할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-181">When you migrate your applications and data to covered Microsoft cloud services, you can build on the audits and certifications that Microsoft holds.</span></span> <span data-ttu-id="0fdff-182">독립 보고서에서는 파트너 데이터의 보안 및 개인 정보를 유지하기 위해 Microsoft에서 구현한 통제 수단의 유효성을 입증합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-182">The independent reports attest to the effectiveness of controls that Microsoft has implemented to help maintain the security and privacy of your data.</span></span>

<span data-ttu-id="0fdff-183">**우리 회사의 자체 규정 준수 활동은 어느 것부터 시작해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="0fdff-183">**Where do I start with my organization’s own compliance effort?**</span></span>

<span data-ttu-id="0fdff-184">[서비스 조직을 위한 SOC 도구 키트](https://aka.ms/soc-toolkit)는 SOC 보고 프로세스를 이해하고 조직의 프로세스 사용을 촉진하는 데 도움이 되는 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-184">The [SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) is a helpful resource for understanding SOC reporting processes and promoting your organization’s use of them.</span></span>

## <a name="resources"></a><span data-ttu-id="0fdff-185">리소스</span><span class="sxs-lookup"><span data-stu-id="0fdff-185">Resources</span></span>

 - [<span data-ttu-id="0fdff-186">Microsoft 클라우드 서비스를 사용하여 데이터를 더욱 효과적으로 보호하기</span><span class="sxs-lookup"><span data-stu-id="0fdff-186">Better protect your data by using Microsoft cloud services</span></span>](https://www.microsoft.com/trustcenter/guidance/protect-data)
 - [<span data-ttu-id="0fdff-187">SOC(Service Organization Control) 보고서</span><span class="sxs-lookup"><span data-stu-id="0fdff-187">Service Organization Control (SOC) Reports</span></span>](https://aka.ms/mssocreports)
 - [<span data-ttu-id="0fdff-188">SSAE 16 감사 표준</span><span class="sxs-lookup"><span data-stu-id="0fdff-188">SSAE 16 Auditing Standard</span></span>](https://www.ssae-16.com/)
 - [<span data-ttu-id="0fdff-189">ISAE 3402 Standard</span><span class="sxs-lookup"><span data-stu-id="0fdff-189">ISAE 3402 Standard</span></span>](https://isae3402.com/)
 - [<span data-ttu-id="0fdff-190">Microsoft 공통 컨트롤 허브 규정 준수 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="0fdff-190">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
 - [<span data-ttu-id="0fdff-191">Microsoft 온라인 서비스 사용 약관</span><span class="sxs-lookup"><span data-stu-id="0fdff-191">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
 - [<span data-ttu-id="0fdff-192">Microsoft Government 클라우드</span><span class="sxs-lookup"><span data-stu-id="0fdff-192">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
 - [<span data-ttu-id="0fdff-193">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="0fdff-193">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="0fdff-194">제공 사항의 배경 설명 다운로드</span><span class="sxs-lookup"><span data-stu-id="0fdff-194">Download the offering backgrounder</span></span>

<span data-ttu-id="0fdff-195">이 제공 사항에 대한 배경 설명 문서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="0fdff-195">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="0fdff-196">[PDF](https://download.microsoft.com/download/F/E/1/FE10DD69-B5A9-4DA7-A86A-1F565D2B6472/SOC_backgrounder-2018.pdf)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdff-196">Download the [PDF](https://download.microsoft.com/download/F/E/1/FE10DD69-B5A9-4DA7-A86A-1F565D2B6472/SOC_backgrounder-2018.pdf).</span></span>
