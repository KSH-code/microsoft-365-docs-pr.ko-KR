---
title: 클라우드 내 개인 데이터 보호를 위한 ISO/IEC 27018 규약
description: Microsoft는 클라우드 개인 정보 보호 정책에 대한 이 규약을 준수하는 최초의 클라우드 공급자입니다.
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
ms.openlocfilehash: 8e7dfcad68dc56e071072124c02c7e1346ddcde8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843354"
---
# <a name="isoiec-27018-code-of-practice-for-protecting-personal-data-in-the-cloud"></a><span data-ttu-id="58102-104">클라우드 내 개인 데이터 보호를 위한 ISO/IEC 27018 규약</span><span class="sxs-lookup"><span data-stu-id="58102-104">ISO/IEC 27018 Code of Practice for Protecting Personal Data in the Cloud</span></span>

## <a name="isoiec-27018-overview"></a><span data-ttu-id="58102-105">ISO/IEC 27018 개요</span><span class="sxs-lookup"><span data-stu-id="58102-105">ISO/IEC 27018 overview</span></span>

<span data-ttu-id="58102-106">ISO(International Organization for Standardization: 국제 표준화 기구)는 독립적인 비정부 조직으로 세계 최대의 자발적 국제 표준 개발자입니다.</span><span class="sxs-lookup"><span data-stu-id="58102-106">The International Organization for Standardization (ISO) is an independent nongovernmental organization and the world's largest developer of voluntary international standards.</span></span> <span data-ttu-id="58102-107">ISO/IEC 27000 표준군은 업종과 규모에 관계 없이 모든 조직에서 정보 자산의 보안을 유지할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="58102-107">The ISO/IEC 27000 family of standards helps organizations of every type and size keep information assets secure.</span></span>

<span data-ttu-id="58102-108">2014년 ISO는 클라우드 개인 정보 보호를 위한 최초의 국제 규약인 ISO/IEC 27001에 대한 추가 규정으로 ISO/IEC 27018:2014를 채택했습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-108">In 2014, the ISO adopted ISO/IEC 27018:2014, an addendum to ISO/IEC 27001, the first international code of practice for cloud privacy.</span></span> <span data-ttu-id="58102-109">EU 데이터 보호법에 기초한 이 규정은 PII(개인 식별 정보)의 처리자로 활동하는 CSP(클라우드 서비스 공급자)에게 PII 보호를 위한 최신 통제 수단 구현과 위험 평가에 대한 특정 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58102-109">Based on EU data-protection laws, it gives specific guidance to cloud service providers (CSPs) acting as processors of personally identifiable information (PII) on assessing risks and implementing state-of-the-art controls for protecting PII.</span></span>

<span data-ttu-id="58102-110">Microsoft와 ISO/IEC 27018</span><span class="sxs-lookup"><span data-stu-id="58102-110">Microsoft and ISO/IEC 27018</span></span>

<span data-ttu-id="58102-111">적어도 1년에 한 번 Microsoft Azure 및 Azure Germany는 공인된 타사 인증 기관을 통해 ISO/IEC 27001 및 ISO/IEC 27018 규정 준수에 대한 감사를 받고, 적용 가능한 보안 통제 수단이 있고 효과적으로 작동하는지 독립적으로 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="58102-111">At least once a year, Microsoft Azure and Azure Germany are audited for compliance with ISO/IEC 27001 and ISO/IEC 27018 by an accredited third-party certification body, providing independent validation that applicable security controls are in place and operating effectively.</span></span> <span data-ttu-id="58102-112">이 준수 확인 프로세스의 일환으로서 감사자는 적용서 보고서에서 Microsoft 범위 내 클라우드 서비스 및 상용 기술 지원 서비스에 Azure에서 PII 보호를 위한 ISO/IEC 27018 통제 수단이 통합되어 있음을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-112">As part of this compliance verification process, the auditors validate in their statement of applicability that Microsoft in-scope cloud services and commercial technical support services have incorporated ISO/IEC 27018 controls for the protection of PII in Azure.</span></span> <span data-ttu-id="58102-113">규정 준수 상태를 유지하려면 매년 Microsoft 클라우드 서비스에 대한 외부 검토를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58102-113">To remain compliant, Microsoft cloud services must be subject to annual third-party reviews.</span></span>

<span data-ttu-id="58102-114">ISO/IEC 27001 표준과 ISO/IEC 27018에 포함된 규약을 준수하는(이 행동 규약을 통합한 최초 주요 클라우드 공급자) Microsoft는 Microsoft의 개인 정보 보호 정책 및 절차가 확고하며 높은 수준의 자체 표준에 따른 것임을 입증하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-114">By following the standards of ISO/IEC 27001 and the code of practice embodied in ISO/IEC 27018, Microsoft (the first major cloud provider to incorporate this code of practice) demonstrates that its privacy policies and procedures are robust and in line with its high standards.</span></span>

- <span data-ttu-id="58102-115">**Microsoft 클라우드 서비스의 고객은 자신의 데이터가 저장되는 위치를 알고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="58102-115">**Customers of Microsoft cloud services know where their data is stored.**</span></span> <span data-ttu-id="58102-116">ISO/IEC 27018에 따라 인증된 CSP는 고객에게 데이터가 저장될 수 있는 국가를 알려주어야 하므로, Microsoft 클라우드 서비스 고객은 해당되는 정보 보안 규칙을 준수하는 데 필요한 시야를 확보하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58102-116">Because ISO/IEC 27018 requires certified CSPs to inform customers of the countries in which their data may be stored, Microsoft cloud service customers have the visibility they need to comply with any applicable information security rules.</span></span>
- <span data-ttu-id="58102-117">**고객 데이터는 명시적 승인 없이는 마케팅이나 광고에 사용되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="58102-117">**Customer data won't be used for marketing or advertising without explicit consent.**</span></span> <span data-ttu-id="58102-118">일부 CSP는 대상 지정된 광고 등 고유의 상업적 목적으로 고객 데이터를 사용하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="58102-118">Some CSPs use customer data for their own commercial ends, including for targeted advertising.</span></span> <span data-ttu-id="58102-119">Microsoft는 범위 내 엔터프라이즈 클라우드 서비스에 대해 ISO/IEC 27018을 채택했으므로, 고객은 데이터가 명시적 승인 없이는 이러한 목적으로 사용되지 않으며 이러한 승인이 클라우드 서비스의 사용 조건일 수 없음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-119">Because Microsoft has adopted ISO/IEC 27018 for its in-scope enterprise cloud services, customers can rest assured that their data will never be used for such purposes without explicit consent, and that consent cannot be a condition for use of the cloud service.</span></span>
- <span data-ttu-id="58102-120">**Microsoft 고객은 PII가 어떻게 처리될지 알고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="58102-120">**Microsoft customers know what's happening with their PII.**</span></span> <span data-ttu-id="58102-121">ISO/IEC 27018에 따르면 적정 기간 내에 개인 정보의 반환, 전송 및 보안 폐기를 고려하는 정책이 마련되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58102-121">ISO/IEC 27018 requires a policy that allows for the return, transfer, and secure disposal of personal information within a reasonable period of time.</span></span> <span data-ttu-id="58102-122">Microsoft는 고객 데이터에 대한 액세스 권한이 필요한 다른 업체와 협력할 경우 사전에 미리 이러한 하위 처리자의 신원을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="58102-122">If Microsoft works with other companies that need access to your customer data, Microsoft proactively discloses the identities of those sub-processors.</span></span>
- <span data-ttu-id="58102-123">**Microsoft는 고객 데이터 공개에 대해 법적 구속력이 있는 요청만을 준수합니다.**</span><span class="sxs-lookup"><span data-stu-id="58102-123">**Microsoft complies only with legally binding requests for disclosure of customer data.**</span></span> <span data-ttu-id="58102-124">Microsoft에서 이러한 요청을 준수해야 하는 경우(예를 들면 범죄 수사의 경우) 항상 고객에게 알립니다. 단, 이러한 알림 행위가 법적으로 금지되지 않는 경우에 한합니다.</span><span class="sxs-lookup"><span data-stu-id="58102-124">If Microsoft must comply with such a request (as in the case of a criminal investigation), it will always notify the customer unless it is prohibited by law from doing so.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="58102-125">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="58102-125">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="58102-126">Azure, Azure Government, Azure Germany</span><span class="sxs-lookup"><span data-stu-id="58102-126">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="58102-127">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="58102-127">Azure DevOps Services</span></span>
- <span data-ttu-id="58102-128">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="58102-128">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="58102-129">Dynamics 365, Dynamics 365 및 Dynamics 365 Germany</span><span class="sxs-lookup"><span data-stu-id="58102-129">Dynamics 365, Dynamics 365, and Dynamics 365 Germany</span></span>
- <span data-ttu-id="58102-130">Microsoft 전문 서비스: Azure, Dynamics 365, Intune, 비즈니스용 Microsoft 365의 중간 규모 비즈니스 및 엔터프라이즈 고객 대상 프리미어 및 온-프레미스</span><span class="sxs-lookup"><span data-stu-id="58102-130">Microsoft Professional Services: Premier and On Premises for Azure, Dynamics 365, Intune, and for medium business and enterprise customers of Microsoft 365 for business</span></span>
- <span data-ttu-id="58102-131">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="58102-131">Microsoft Graph</span></span>
- <span data-ttu-id="58102-132">Microsoft Healthcare Bot</span><span class="sxs-lookup"><span data-stu-id="58102-132">Microsoft Healthcare Bot</span></span>
- <span data-ttu-id="58102-133">Intune</span><span class="sxs-lookup"><span data-stu-id="58102-133">Intune</span></span>
- <span data-ttu-id="58102-134">Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="58102-134">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="58102-135">Power Automate(이전 Microsoft Flow): 독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="58102-135">Power Automate (formerly Microsoft Flow): cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="58102-136">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="58102-136">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- <span data-ttu-id="58102-137">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="58102-137">Office 365 Germany</span></span>
- <span data-ttu-id="58102-138">OMS 서비스 지도</span><span class="sxs-lookup"><span data-stu-id="58102-138">OMS Service Map</span></span>
- <span data-ttu-id="58102-139">PowerApps 클라우드 서비스: 독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태</span><span class="sxs-lookup"><span data-stu-id="58102-139">PowerApps cloud service: either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="58102-140">Power BI 클라우드 서비스: 독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태</span><span class="sxs-lookup"><span data-stu-id="58102-140">Power BI cloud service: either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="58102-141">Power BI가 포함됨</span><span class="sxs-lookup"><span data-stu-id="58102-141">Power BI Embedded</span></span>
- <span data-ttu-id="58102-142">파워 가상 에이전트</span><span class="sxs-lookup"><span data-stu-id="58102-142">Power Virtual Agents</span></span>
- <span data-ttu-id="58102-143">Microsoft 위협 전문가</span><span class="sxs-lookup"><span data-stu-id="58102-143">Microsoft Threat Experts</span></span>
- <span data-ttu-id="58102-144">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="58102-144">Microsoft Stream</span></span>
- <span data-ttu-id="58102-145">엔드포인트용 Microsoft Defender — 엔드포인트 감지 및 대응, 자동 조사 및 조치, 보안 점수</span><span class="sxs-lookup"><span data-stu-id="58102-145">Microsoft Defender for Endpoint  — Endpoint Detection & Response, Automatic Investigation & Remediation, Secure Score</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="58102-146">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="58102-146">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="58102-147">감사 주기</span><span class="sxs-lookup"><span data-stu-id="58102-147">Audit cycle</span></span>

<span data-ttu-id="58102-148">Microsoft 클라우드와 상용 기술 지원 서비스는 ISO/IEC 27001에 대한 인증 프로세스의 일부로서 ISO/IEC 27018 규약에 대해 1년에 한 번씩 감사를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-148">Microsoft cloud and commercial technical support services are audited once a year for the ISO/IEC 27018 code of practice as part of the certification process for ISO/IEC 27001.</span></span>

### <a name="audits-and-reports"></a><span data-ttu-id="58102-149">감사 및 보고서</span><span class="sxs-lookup"><span data-stu-id="58102-149">Audits and reports</span></span>

- [<span data-ttu-id="58102-150">Azure, Dynamics 365 및 온라인 서비스: ISO27018 인증서</span><span class="sxs-lookup"><span data-stu-id="58102-150">Azure, Dynamics 365, and Online Services: ISO27018 Certificate</span></span>](https://aka.ms/azureiso27018cert)
- [<span data-ttu-id="58102-151">AAzure, Dynamics 365 및 온라인 서비스: ISO27018 평가 보고서</span><span class="sxs-lookup"><span data-stu-id="58102-151">AAzure, Dynamics 365, and Online Services: ISO27018 Assessment Report</span></span>](https://aka.ms/azureiso27001report)
- [<span data-ttu-id="58102-152">Azure Germany: 클라우드 인증서 내 개인 데이터 보호를 위한 ISO27018 규약</span><span class="sxs-lookup"><span data-stu-id="58102-152">Azure Germany: ISO27018 Code of Practice for Protecting Personal Data in the Cloud Certificate</span></span>](https://servicetrust.microsoft.com/Documents/ComplianceReports?downloadDocument=1&documentId=6a0dab80-8382-4af6-980c-ed2ed9a341c6)

### <a name="office-365"></a><span data-ttu-id="58102-153">Office 365</span><span class="sxs-lookup"><span data-stu-id="58102-153">Office 365</span></span>

- [<span data-ttu-id="58102-154">Office 365: ISO 27001, 27018 및 27017 감사 평가 보고서</span><span class="sxs-lookup"><span data-stu-id="58102-154">Office 365: ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)
- [<span data-ttu-id="58102-155">Yammer ISO 27018 감사 평가 보고서</span><span class="sxs-lookup"><span data-stu-id="58102-155">Yammer ISO 27018 Audit Assessment Report</span></span>](https://aka.ms/YammerISO27018Auditreport)

### <a name="azure-devops-services"></a><span data-ttu-id="58102-156">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="58102-156">Azure DevOps Services</span></span>

- [<span data-ttu-id="58102-157">Azure DevOps Services: ISO27018 인증서 PII 665918</span><span class="sxs-lookup"><span data-stu-id="58102-157">Azure DevOps Services: ISO27018 Certificate PII 665918</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2062252)

## <a name="frequently-asked-questions"></a><span data-ttu-id="58102-158">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="58102-158">Frequently asked questions</span></span>

<span data-ttu-id="58102-159">**ISO/IEC 27018은 누구에게 적용되나요?**</span><span class="sxs-lookup"><span data-stu-id="58102-159">**To whom does ISO/IEC 27018 apply?**</span></span>

<span data-ttu-id="58102-160">이 규약은 다른 조직과의 계약 하에서 PII를 처리하는 CSP에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58102-160">This code of practice applies to CSPs that process PII under contract for other organizations.</span></span> <span data-ttu-id="58102-161">Microsoft에서는 해당 CSP에 대한 지원에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58102-161">At Microsoft, it also applies to the support of those CSPs.</span></span>

<span data-ttu-id="58102-162">**‘개인 정보 규제자’와 ‘개인 정보 처리자’의 차이점은 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="58102-162">**What is the difference between 'personal information controllers' and 'personal information processors'?**</span></span>

<span data-ttu-id="58102-163">ISO/IEC 27018 관련:</span><span class="sxs-lookup"><span data-stu-id="58102-163">In the context of ISO/IEC 27018:</span></span>

- <span data-ttu-id="58102-164">‘제어자’는 개인 정보의 수집, 유지, 처리 또는 사용을 제어합니다. 제어자에는 다른 회사를 대신하여 이를 제어하는 업체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58102-164">'Controllers' control the collection, holding, processing, or use of personal information; they include those who control it on another company's behalf.</span></span>
- <span data-ttu-id="58102-165">‘처리자’는 제어자를 대신하여 정보를 처리합니다. 이들은 정보 사용법이나 처리 목적에 관한 결정을 내리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-165">'Processors' process information on behalf of controllers; they do not make decisions as to how to use the information or the purposes of the processing.</span></span> <span data-ttu-id="58102-166">엔터프라이즈 클라우드 서비스 제공에 있어서 Microsoft(파트너의 공급자)는 정보 처리자입니다.</span><span class="sxs-lookup"><span data-stu-id="58102-166">In providing its enterprise cloud services, Microsoft (as a vendor to you) is an information processor.</span></span>

<span data-ttu-id="58102-167">**ISO/IEC 27018에 대한 Microsoft의 규정 준수 정보는 어디에서 확인할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="58102-167">**Where can I view Microsoft compliance information for ISO/IEC 27018?**</span></span>

- <span data-ttu-id="58102-168">[Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016), [Microsoft 전문 서비스](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270) 및 [Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016)에서 ISO/IEC 27018 인증서를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-168">You can review the ISO/IEC 27018 certificates from BSI for [Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016), [Microsoft Professional Services](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270), and [Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016).</span></span>
- <span data-ttu-id="58102-169">또한 [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert), [Office 365](https://aka.ms/Office365-Cert) 및 [Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159)에 대한 ISO/IEC 27018 인증을 기반으로 하는 BSI의 ISO/IEC 27001 인증서를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-169">You can also review ISO/IEC 27001 certificates from BSI upon which ISO/IEC 27018 certification is based for [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert), [Office 365](https://aka.ms/Office365-Cert), and [Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159).</span></span>
- <span data-ttu-id="58102-170">Microsoft가 ISO/IEC 27018을 준수하는지 검증한 독립 감사자인 BSI 보고서를 검토하려면 [Service Trust Portal](https://aka.ms/stphelp)을 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="58102-170">To review the BSI reports, the independent auditor that validated Microsoft compliance with ISO/IEC 27018, visit the [Service Trust Portal](https://aka.ms/stphelp).</span></span>

<span data-ttu-id="58102-171">**우리 회사의 인증 프로세스에 Microsoft의 규정 준수를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="58102-171">**Can I use Microsoft's compliance in my organization's certification process?**</span></span>

<span data-ttu-id="58102-172">예.</span><span class="sxs-lookup"><span data-stu-id="58102-172">Yes.</span></span> <span data-ttu-id="58102-173">ISO/IEC 27018를 준수하는 것이 Microsoft의 범위 내 엔터프라이즈 클라우드 서비스에서 배포되는 비즈니스 및 구현에 중요한 경우, 규정 준수 평가에서 Microsoft의 ISO/IEC 27001와 ISO/ICE 27018 준수에 대한 Microsoft의 증명을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-173">If compliance with ISO/IEC 27018 is important for your business and implementations deployed on any of Microsoft in-scope enterprise cloud services, you can use Microsoft's attestation of compliance with ISO/IEC 27018 with Microsoft's certification for ISO/IEC 27001 in your compliance assessment.</span></span>

<span data-ttu-id="58102-174">하지만 구현에 대한 규정 준수를 평가하기 위한 평가자와의 계약과 고유 조직 내 통제 수단 및 프로세스에 대해서는 파트너가 책임을 져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58102-174">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="58102-175">Microsoft 준수 관리자를 사용하여 위험 평가</span><span class="sxs-lookup"><span data-stu-id="58102-175">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="58102-176">[Microsoft 준수 관리자](compliance-manager.md)는 조직의 준수 입장을 이해하고 위험을 줄이기 위한 조치를 취하도록 돕는 [Microsoft 365 규정 준수 센터](microsoft-365-compliance-center.md)의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="58102-176">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="58102-177">준수 관리자는 이 규제에 대한 평가를 빌드하기 위한 프리미엄 서식 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58102-177">Compliance Manager offers a premium template for building an assessment for this regulation.</span></span> <span data-ttu-id="58102-178">준수 관리자의 **평가 서식 파일** 페이지에서 서식 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="58102-178">Find the template in the **assessment templates** page in Compliance Manager.</span></span> <span data-ttu-id="58102-179">[준수 관리자의 평가 빌드](compliance-manager-assessments.md) 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="58102-179">Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="58102-180">리소스</span><span class="sxs-lookup"><span data-stu-id="58102-180">Resources</span></span>

- [<span data-ttu-id="58102-181">ISO/IEC 27018:2014 규약</span><span class="sxs-lookup"><span data-stu-id="58102-181">ISO/IEC 27018:2014 code of practice</span></span>](https://aka.ms/ISO.IEC_27018.2014)
- [<span data-ttu-id="58102-182">Microsoft 공통 컨트롤 허브 규정 준수 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="58102-182">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="58102-183">Microsoft 엔터프라이즈 클라우드 및 기술 서비스용 데이터 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="58102-183">Data access policies for Microsoft enterprise cloud and technical services</span></span>](https://www.microsoft.com/trustcenter/Privacy/Who-can-access-your-data-and-on-what-terms)
- [<span data-ttu-id="58102-184">Microsoft 온라인 서비스 사용 약관</span><span class="sxs-lookup"><span data-stu-id="58102-184">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="58102-185">Microsoft Government 클라우드</span><span class="sxs-lookup"><span data-stu-id="58102-185">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="58102-186">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="58102-186">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
