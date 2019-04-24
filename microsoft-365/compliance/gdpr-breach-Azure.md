---
title: Azure 및 GDPR의 위반 알림
description: Azure가 개인 데이터 위반으로부터 보호하는 방법 및 Microsoft가 위반 발생 시 대응하고 사용자에게 알리는 방법입니다.
keywords: Azure, Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 287175d6f78efa1052e446b230f39c33fc4d5fc6
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286433"
---
# <a name="azure-and-breach-notification-under-the-gdpr"></a><span data-ttu-id="88f9e-104">Azure 및 GDPR의 위반 알림</span><span class="sxs-lookup"><span data-stu-id="88f9e-104">Azure and Breach Notification Under the GDPR</span></span>

<span data-ttu-id="88f9e-p101">Microsoft Azure는 GDPR(일반 데이터 보호 규정)에 따라 의무를 다합니다. Microsoft Azure는 데이터 침해로부터 보호하기 위해 광범위한 보안 조치를 취합니다. 여기에는 물리적 및 논리적 보안 제어 뿐만 아니라 자동화된 보안 프로세스, 포괄적인 정보 보안 및 개인 정보 보호 정책, 모든 직원에 대한 개인 정보 보호 교육이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p101">Microsoft Azure takes its obligations under the General Data Protection Regulation (GDPR) seriously. Microsoft Azure takes extensive security measures to protect against data breaches. These include both physical and logical security controls, as well as automated security processes, comprehensive information security and privacy policies, and security and privacy training for all personnel.</span></span>

<span data-ttu-id="88f9e-p102">설계 단계부터 개인 정보 보호(Privacy-by-Design) 및 기본적으로 개인 정보 보호(Privacy-by-Default) 방법을 통합하는 필수 개발 프로세스인 [보안 개발 수명 주기](https://www.microsoft.com/sdl/)를 통해 처음부터 Microsoft Azure에 보안이 기본적으로 제공됩니다. Microsoft 보안 전략의 주요 원칙은 심층 방어 전략이 확장된 "위반 예측"입니다. Microsoft는 Azure의 보안 기능을 지속적으로 개선함으로써 새로운 위협에 앞서나갈 수 있습니다. Azure 보안에 대한 자세한 내용은 다음 [리소스](https://www.microsoft.com/trustcenter/security/azure-security)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p102">Security is built into Microsoft Azure from the ground up, starting with the [Security Development Lifecycle](https://www.microsoft.com/sdl/), a mandatory development process that incorporates privacy-by-design and privacy-by-default methodologies. The guiding principle of Microsoft’s security strategy is to “assume breach,” which is an extension of the defense-in-depth strategy. By constantly challenging the security capabilities of Azure, Microsoft can stay ahead of emerging threats. For more information on Azure security, please review these [resources](https://www.microsoft.com/trustcenter/security/azure-security).</span></span>

<span data-ttu-id="88f9e-p103">Microsoft에는 Microsoft Azure에 대한 공격 영향력을 완화하기 위해 작동하는 글로벌 연중무휴 인시던트 응답 서비스가 제공됩니다. 여러 보안 및 준수 감사(예: [ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018))를 통해 입증된 결과에 따라, Microsoft는 데이터 센터에서 연중무휴 CCTV 모니터링, 훈련된 보안 직원, 스마트 카드 및 생체 인식 제어를 비롯한 엄격한 운영 및 프로세스를 사용하여 무단 액세스를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p103">Microsoft has a global, 24x7 incident response service that works to mitigate the effects of attacks against Microsoft Azure. Attested by multiple security and compliance audits (e.g. [ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018)), Microsoft employs rigorous operations and processes at its data centers to prevent unauthorized access, including 24x7 video monitoring, trained security personnel, smart cards, and biometric controls.</span></span>

#### <a name="detection-of-potential-breaches"></a><span data-ttu-id="88f9e-114">잠재적인 침해 감지</span><span class="sxs-lookup"><span data-stu-id="88f9e-114">Detection of Potential Breaches</span></span>
-------------------------------

<span data-ttu-id="88f9e-p104">최신 클라우드 컴퓨팅의 특성으로 인해, 고객 클라우드 환경에서 발생하는 모든 데이터 침해가 Microsoft Azure 서비스와 관련된 것은 아닙니다. Microsoft는 Azure 서비스에 대해 공유 책임 모델을 사용하여 보안 및 운영 책임을 정의합니다. 클라우드 서비스 공급자와 고객 모두 클라우드 보안 부분 책임이 있으므로, 공유 책임이 클라우드 서비스의 보안을 논의할 때 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p104">Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is particularly important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.</span></span>

<span data-ttu-id="88f9e-p105">Microsoft는 고객의 책임 영역 내에서 보안 문제를 모니터링하거나 대응하지 않습니다. 고객에 의한 보안 손상은 Azure 보안 인시던트로 처리되지 않으며 고객 테넌트에서 대응 노력을 관리해야 합니다. 적절한 서비스 계약이 있는 경우, 고객 인시던트 대응이 Microsoft Azure [고객 지원 서비스](https://azure.microsoft.com/support/options/)와 협력해서 진행될 수 있습니다.또한 Microsoft Azure는 고객이 보안 인시던트 대응을 개발 및 관리하기 위해 활용할 수 있는 다양한 서비스(예: [Azure Security Center](https://azure.microsoft.com/services/security-center/))도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p105">Microsoft does not monitor for or respond to security incidents within the customer’s realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure also offers various services (e.g., [Azure Security Center](https://azure.microsoft.com/services/security-center/)) that customers can utilize for developing and managing security incident response.</span></span>

<span data-ttu-id="88f9e-p106">Azure는 Microsoft Azure 인시던트 관리 플랜에 속하는 보안 인시던트 대응 프로세스에 따라 잠재적인 데이터 위반에 대응합니다. Azure의 보안 인시던트 대응은 감지, 평가, 진단, 안정화 및 닫기의 5단계 프로세스로 구현됩니다. 보안 인시던트 대응 팀은 조사가 진행되면서 진단 및 안정화 단계 간을 전환할 수 있습니다. 보안 인시던트 대응 프로세스의 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p106">Azure responds to a potential data breach according to the security incident response process, which is a subset of the Microsoft Azure incident management plan. Azure’s security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="88f9e-126">단계</span><span class="sxs-lookup"><span data-stu-id="88f9e-126">Stage</span></span></th>
<th align="left"><span data-ttu-id="88f9e-127">설명</span><span class="sxs-lookup"><span data-stu-id="88f9e-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="88f9e-128">1</span><span class="sxs-lookup"><span data-stu-id="88f9e-128">1.</span></span></td>
<td align="left"><span data-ttu-id="88f9e-129">감지</span><span class="sxs-lookup"><span data-stu-id="88f9e-129">Detect</span></span></td>
<td align="left"><span data-ttu-id="88f9e-130">잠재적인 인시던트의 최초 지표</span><span class="sxs-lookup"><span data-stu-id="88f9e-130">First indication of a potential incident.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="88f9e-131">2</span><span class="sxs-lookup"><span data-stu-id="88f9e-131">2.</span></span></td>
<td align="left"><span data-ttu-id="88f9e-132">평가</span><span class="sxs-lookup"><span data-stu-id="88f9e-132">Assess</span></span></td>
<td align="left"><span data-ttu-id="88f9e-p107">출장 인시던트 대응 팀 구성원이 이벤트의 영향 및 심각도를 평가합니다. 이러한 평가는 증거에 따라 보안 대응 팀을 향한 추가 에스컬레이션으로 이어질 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p107">An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="88f9e-135">3</span><span class="sxs-lookup"><span data-stu-id="88f9e-135">3.</span></span></td>
<td align="left"><span data-ttu-id="88f9e-136">진단</span><span class="sxs-lookup"><span data-stu-id="88f9e-136">Diagnose</span></span></td>
<td align="left"><p><span data-ttu-id="88f9e-137">보안 응답 전문가가 해당 기술 또는 법정 조사를 수행하고, 방지, 완화 및 해결 전략을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-137">Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies.</span></span></p>
<p><span data-ttu-id="88f9e-138">보안 팀에서 고객 데이터가 불법적이거나 허가되지 않은 개인에게 노출되었을 수 있다고 판단할 경우 고객 인시던트 알림 프로세스가 동시에 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-138">If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="88f9e-139">4</span><span class="sxs-lookup"><span data-stu-id="88f9e-139">4.</span></span></td>
<td align="left"><span data-ttu-id="88f9e-140">안정화 및 복구</span><span class="sxs-lookup"><span data-stu-id="88f9e-140">Stabilize and Recover</span></span></td>
<td align="left"><span data-ttu-id="88f9e-p108">인시던트 대응 팀이 문제를 완화하기 위한 복구 계획을 세웁니다. 영향을 받은 시스템을 격리하는 것과 같은 위기 방지 단계가 즉시 진행되거나 진단과 동시에 수행될 수 있습니다. 즉각적인 위험이 지나간 후에 좀 더 장기적인 완화를 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p108">The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="88f9e-144">5</span><span class="sxs-lookup"><span data-stu-id="88f9e-144">5.</span></span></td>
<td align="left"><span data-ttu-id="88f9e-145">종료 및 사후 평가</span><span class="sxs-lookup"><span data-stu-id="88f9e-145">Close and Post-Mortem</span></span></td>
<td align="left"><span data-ttu-id="88f9e-146">인시던트 대응 팀은 정책, 절차 및 프로세스를 수정하여 이벤트 재발을 방지하기 위해 인시던트의 세부 정보를 대략적으로 설명하는 사후 평가를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-146">The incident response team creates a post-mortem that outlines the details of the incident, with the intention to revise policies, procedures, and processes to prevent a reoccurrence of the event.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="88f9e-147">[클라우드의 Microsoft Azure 보안 응답](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) 백서에서는 Microsoft가 Azure 내의 보안 인시던트를 조사, 관리 및 대응하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-147">The [Microsoft Azure Security Response in the Cloud](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) white paper further details how Microsoft investigates, manages, and responds to security incidents within Azure.</span></span>

<span data-ttu-id="88f9e-p109">Microsoft Azure에서 사용하는 감지 프로세스는 Azure 서비스의 기밀성, 무결성 및 가용성을 침해하는 이벤트를 검색하도록 고안되었습니다. 다음과 같은 일부 이벤트가 조사를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p109">The detection processes used by Microsoft Azure are designed to discover events that risk the confidentiality, integrity, and availability of Azure services. Several events can trigger an investigation:</span></span>

-   <span data-ttu-id="88f9e-p110">내부 모니터링 및 경고 프레임워크를 통한 자동화된 시스템 경고. 이러한 경고는 맬웨어 방지, 침입 감지와 같은 서명 기반 경보나 비정상 상황 발생 시 예상되는 작업 및 경고를 프로파일링하도록 설계된 알고리즘을 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p110">Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as antimalware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.</span></span>

-   <span data-ttu-id="88f9e-152">첫 번째 파티는 Microsoft Azure 및 Azure Government에서 실행되는 Microsoft 서비스에서 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-152">First party reports from Microsoft Services running on Microsoft Azure and Azure Government.</span></span>

-   <span data-ttu-id="88f9e-p111">보안 취약성이 <secure@microsoft.com>을 통해 [MSRC(Microsoft Security Response Center)](https://technet.microsoft.com/security/dn440717)로 보고됩니다. MSRC는 전 세계의 파트너 및 보안 연구자들과 협력하여 보안 인시던트를 방지하고 Microsoft 제품 보안을 향상시키도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p111">Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via <secure@microsoft.com>. MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.</span></span>

-   <span data-ttu-id="88f9e-155">고객은 [고객 지원 포털](http://www.windowsazure.com/support/contact/) 또는 Microsoft Azure 및 Azure Government 관리 포털을 통해 보고하며 Azure 인프라에 영향을 주는 의심스러운 작업(고객의 책임 범위 내에서 발생하는 작업과는 반대됨)을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-155">Customer reports via the [Customer Support Portal](http://www.windowsazure.com/support/contact/) or Microsoft Azure and Azure Government Management Portal, that describe suspicious activity attributed to the Azure infrastructure (as opposed to activity occurring within the customer’s scope of responsibility).</span></span>

-   <span data-ttu-id="88f9e-p112">보안 [레드팀 및 블루팀](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) 활동. 이 전략에서는 공격적인 Microsoft 보안 전문가로 이루어진 고도로 숙련된 레드팀을 활용하여 Azure의 잠재적인 약점을 알아내고 공격합니다. 보안 대응 블루팀은 레드팀의 활동을 감지하고 견제합니다.레드팀 및 블루팀 작업은 둘 다 Azure의 보안 대응 노력이 보안 인시던트를 효과적으로 관리하고 있는지를 확인하는 데 사용됩니다. 보안 레드팀 및 블루팀 활동은 고객 데이터 보호를 지원하기 위한 협약의 규칙에 따라 운영됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p112">Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly-skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.</span></span>

-   <span data-ttu-id="88f9e-p113">Azure 서비스 운영자에 의한 에스컬레이션. Microsoft 직원들은 잠재적인 보안 문제를 식별하고 에스컬레이션하도록 교육을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p113">Escalations by operators of Azure Services. Microsoft employees are trained to identify and escalate potential security issues.</span></span>

#### <a name="azures-data-breach-response"></a><span data-ttu-id="88f9e-163">Azure의 데이터 위반 대응</span><span class="sxs-lookup"><span data-stu-id="88f9e-163">Azure’s Data Breach Response</span></span>
----------------------------

<span data-ttu-id="88f9e-p114">Microsoft는 업무에 미치는 영향, 복구 가능성 및 인시던트의 영향 정보를 확인하여 조사 작업에 적절한 우선 순위 및 심각도를 할당합니다. 우선 순위와 심각도는 조사를 진행하는 동안 새롭게 알아낸 사실과 결론에 따라 변경될 수 있습니다. 고객 데이터에 대한 임박하거나 확인된 위험을 수반하는 보안 이벤트는 높은 심각도로 취급되며, 해결 방안을 찾기 위해 24시간 내내 작업이 진행됩니다. Microsoft Azure는 인시던트의 영향 정보를 다음 위반 범주로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p114">Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft Azure categorizes the information impact of the incident into the following breach categories:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="88f9e-168">범주</span><span class="sxs-lookup"><span data-stu-id="88f9e-168">Category</span></span></th>
<th align="left"><span data-ttu-id="88f9e-169">정의</span><span class="sxs-lookup"><span data-stu-id="88f9e-169">Definition</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="88f9e-170">없음</span><span class="sxs-lookup"><span data-stu-id="88f9e-170">None</span></span></td>
<td align="left"><span data-ttu-id="88f9e-171">정보가 노출, 변경, 삭제 또는 다른 방식으로 손상되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-171">No information was exfiltrated, changed, deleted, or otherwise compromised.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="88f9e-172">개인 정보 보호 위반</span><span class="sxs-lookup"><span data-stu-id="88f9e-172">Privacy Breach</span></span></td>
<td align="left"><span data-ttu-id="88f9e-173">납세자, 직원, 수익자 등의 중요한 개인 데이터가 액세스되었거나 노출되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-173">Sensitive personal data of taxpayers, employees, beneficiaries, etc. was accessed or exfiltrated.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="88f9e-174">독점 위반</span><span class="sxs-lookup"><span data-stu-id="88f9e-174">Proprietary Breach</span></span></td>
<td align="left"><span data-ttu-id="88f9e-175">PCII(보호되는 중요한 인프라 정보)와 같은 분류되지 않은 소유 정보가 액세스되었거나 노출되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-175">Unclassified proprietary information, such as protected critical infrastructure information (PCII), was accessed or exfiltrated.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="88f9e-176">무결성 손실</span><span class="sxs-lookup"><span data-stu-id="88f9e-176">Integrity Loss</span></span></td>
<td align="left"><span data-ttu-id="88f9e-177">중요한 정보 또는 소유 정보가 변경되었거나 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-177">Sensitive or proprietary information was changed or deleted.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="88f9e-p115">보안 대응 팀은 Microsoft Azure 보안 엔지니어 및 SME와 공조하여 증거를 통한 실제 데이터를 기준으로 이벤트를 분류합니다. 보안 이벤트를 다음과 같이 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p115">The Security Response Team works with Microsoft Azure Security Engineers and SMEs to classify the event based on factual data from the evidence. A security event may be classified as:</span></span>

-   <span data-ttu-id="88f9e-p116">**가양성:** 검색 조건을 충족하지만 정상적인 비즈니스 방식의 일부로 확인되며 필터링할 필요가 있는 이벤트입니다. 서비스 팀은 가양성에 대한 근본 원인을 파악하고, 감지 원본을 활용하고 필요에 따라 미세 <span id="_Toc350859432" class="anchor"></span>조정하여 체계적인 방식으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p116">**False Positive:** An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-<span id="_Toc350859432" class="anchor"></span>tuning them as needed.</span></span>

-   <span data-ttu-id="88f9e-182">**보안 인시던트:** Microsoft 장비 또는 Microsoft 시설에 저장되어 있는 모든 고객 데이터 또는 지원 데이터에 대한 불법 액세스 또는 이러한 장비 또는 시설에 대한 무단 액세스로 인해 고객 데이터 또는 지원 데이터가 손실, 노출 또는 변경되는 인시던트입니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-182">**Security Incident:** An incident where unlawful access to any Customer Data or Support Data stored on Microsoft’s equipment or in Microsoft’s facilities, or unauthorized access to such equipment or facilities resulting in loss, disclosure, or alteration of Customer Data or Support Data has occurred.</span></span>

-   <span data-ttu-id="88f9e-183">**CRSI(고객 보고 가능 보안 인시던트):** Microsoft의 시스템, 장비 또는 시설을 불법적으로 또는 허가 없이 액세스하거나 사용하여 고객 데이터를 공개, 수정 또는 손실하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-183">**Customer-Reportable Security Incident (CRSI):** An unlawful or unauthorized access to or use of Microsoft’s systems, equipment, or facilities resulting in disclosure, modification, or loss of customer data.</span></span>

-   <span data-ttu-id="88f9e-p117">**개인 정보 위반:** 개인 데이터와 관련된 보안 인시던트의 하위 형식입니다. 처리 절차는 보안 인시던트와 다르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p117">**Privacy Breach:** A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.</span></span>

<span data-ttu-id="88f9e-p118">CRSI가 선언되려면, Microsoft가 고객 데이터에 대한 무단 액세스가 발생했거나 발생했을 가능성이 높고, 알림이 진행되어야 하는 법적 또는 계약 조항이 있음을 확인해야 합니다. 구체적인 고객 영향, 리소스 액세스 및 복구 단계가 공개되면 좋지만 반드시 그럴 필요는 없습니다.인시던트는 일반적으로 보안 인시던트의 진단 단계가 끝난 후에 CRSI로 선언됩니다. 그렇지만 모든 관려 정보를 사용할 수 있게 되는 언제든지 이러한 선언이 진해욀 수 있습니다. 보안 인시던트 관리자는 고객 인시던트 알림 프로세스를 실행하기 전에, 보고 가능한 이벤트가 발생했을 것이라는 합리적인 추측을 넘어서는 명확한 증거를 확보해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p118">For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.</span></span>

<span data-ttu-id="88f9e-p119">조사 과정 전반에서, 보안 대응 팀은 전역 법률 자문과 긴밀히 협의하면서 법률적 의무 및 고객과의 약정에 따라 법정 조치가 수행되도록 합니다. 또한 다양한 운영 환경에서 시스템 및 고객 데이터를 보고 처리하는 데 중요한 제한 사항이 적용됩니다. 고객 데이터뿐만 아니라 중요한 데이터 또는 기밀 데이터는 해당 인시던트 티켓에 기록된 인시던트 관리자의 명시적인 서면 동의 없이 프로덕션 환경 외부로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p119">Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket.</span></span>

<span data-ttu-id="88f9e-p120">Microsoft는 고객 및 비즈니스 위험이 성공적으로 방지되고, 수정 조치가 구현되는지 확인합니다. 필요한 경우 이벤트와 연결된 즉각적인 보안 위험을 해결하기 위한 긴급 완화 단계가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p120">Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken.</span></span>

<span data-ttu-id="88f9e-p121">또한 Microsoft는 데이터 침해에 대한 내부 사후 평가도 완료합니다. 이 과정의 일부로, 대응 및 운영 절차가 충분한지 평가되고, 보안 인시던트 대응 SOP 또는 관련 프로세스에 필요할 수 있는 모든 업데이트가 파악되고 구현됩니다. 데이터 침해에 대한 내부 사후 평가는 고객이 사용할 수 없는 중대한 기밀 기록입니다. 그렇지만 사후 평가를 요약하여 다른 고객 이벤트 알림에 포함할 수 있습니다. 이러한 보고서는 Azure의 정기 감사 주기의 일부로 검토될 수 있게 외부 감사자에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p121">Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal post-mortems for data breaches are highly confidential records not available to customers. Post-mortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure’s routine audit cycle.</span></span>

#### <a name="customer-notification"></a><span data-ttu-id="88f9e-200">고객 알림</span><span class="sxs-lookup"><span data-stu-id="88f9e-200">Customer Notification</span></span>
---------------------

<span data-ttu-id="88f9e-p122">Microsoft Azure는 필요에 따라 데이터 침해 사실을 고객과 규제 기관에 알립니다. Microsoft은 Azure를 운영하면서 내부 구조를 과도하게 구획화하고 있습니다. 데이터 흐름 로그도 강력해졌습니다. 이러한 설계 방식은 대부분의 인시던트를 구체적인 고객의 범주에 포함할 수 있다는 장점이 있습니다. 이렇게 하는 목적은 데이터 침해 시, 영향을 받은 고객에게 정확하고 실행 가능한 방식으로 시기 적절하게 알리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p122">Microsoft Azure notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of Azure. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached.</span></span>

<span data-ttu-id="88f9e-p123">CRSI가 선언된 후에, 빠르게 변화하는 보안 위험이 고려되면서 가능한 한 신속하게 알림 프로세스가 진행됩니다. 일반적으로 인시던트 조사가 진행 중일 때는 알림 초안이 작성됩니다. 고객 알림은 다음 경우를 *제외하고* 침해를 선언하고 72시간 이내에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p123">After the declaration of a CRSI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* for the following circumstances:</span></span>

-   <span data-ttu-id="88f9e-p124">Microsoft가 알림을 진행할 때 다른 고객에 대한 위험이 증가할 수 있다고 판단한 경우, 예를 들어 알림이 진행될 경우 공격자가 알게 되어 수정 기회를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p124">Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.</span></span>

-   <span data-ttu-id="88f9e-211">Microsoft의 법률 부서 CELA(회사 외부 업무 및 법률 담당) 및 인시던트 책임 관리자가 기타 비정상적이거나 극단적인 상황을 조사한 경우.</span><span class="sxs-lookup"><span data-stu-id="88f9e-211">Other unusual or extreme circumstances vetted by Microsoft’s legal department Corporate External and Legal Affairs (CELA) and the Executive Incident Manager.</span></span>

<span data-ttu-id="88f9e-212">Microsoft Azure는 알림 프로세스를 과도하게 지연시키지 않으면서, 내부 조사를 수행할 수 있도록 하고, 최종 사용자 약정을 충족하도록 지원할 수 있는 자세한 정보를 고객에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-212">Microsoft Azure provides customers with detailed information enabling them to perform internal investigations and assisting them in meeting end user commitments, while not unduly delaying the notification process.</span></span>

<span data-ttu-id="88f9e-p125">개인 데이터 침해에 대한 알림은 전자 메일을 포함하여 Microsoft가 선택한 모든 방법을 통해 고객에게 전달됩니다. 데이터 침해 알림은 [구현 지침](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)에 따라 구성될 수 있는 Azure Security Center 제공 보안 연락처 목록으로 전달됩니다. Azure Security Center에 연락처 목록이 제공되지 않으면 알림은 Azure 구독의 한 명 이상의 관리자에게 전송됩니다. 이러한 알림이 성공적으로 전달되도록 하기 위해 고객은 적용 가능한 각 구독 및 온라인 서비스 포털의 관리 연락처 정보가 올바른지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p125">Notification of a personal data breach will be delivered to the customer by any means Microsoft selects, including via email. Notification of a data breach will be delivered to the list of security contacts provided in Azure Security center, which can be configured by following the [implementation guidelines](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). If contact information is not provided in Azure Security Center, the notification will be sent to one or more administrator in an Azure subscription. To ensure that notification can be successfully delivered, it is the customer’s responsibility to ensure that the administrative contact information on each applicable subscription and online services portal is correct.</span></span>

<span data-ttu-id="88f9e-p126">Microsoft Azure 또는 Azure Government 팀은 CSS(고객 서비스) 및 고객 AM(계정 관리자) 또는 TAM(기술 계정 관리자)과 같은 추가 Microsoft 직원에게도 알리도록 선택할 수 있습니다. 이러한 개인은 고객과 밀접하게 관련되어 있는 경우가 많으며 보다 빠른 수정이 이루어지는 데 도움이 될 수 있습니다.<span id="_Appendix_A" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="88f9e-p126">The Microsoft Azure or Azure Government team may also elect to notify additional Microsoft personnel such as Customer Service (CSS) and the customer’s Account Manager(s) (AM) or Technical Account Manager(s) (TAM). These individuals often have close relationships with the customer and can facilitate faster remediation<span id="_Appendix_A" class="anchor"></span></span></span>

#### <a name="microsoft-intune-data-breach"></a><span data-ttu-id="88f9e-219">Microsoft InTune 데이터 침해</span><span class="sxs-lookup"><span data-stu-id="88f9e-219">Microsoft InTune Data Breach</span></span>
----------------------------

<span data-ttu-id="88f9e-p127">Microsoft Intune은 Microsoft Enterprise Mobility + Security Suite 클라우드 서비스 제품의 핵심 구성 요소입니다. 데이터 거버넌스 전략을 지원하기 위해 모든 Microsoft 클라우드 서비스는 Microsoft의 설계 단계부터 개인 정보 및 보안 유지(Privacy and Security by Design) 및 기본적으로 개인 정보 및 보안 유지(Privacy and Security by Default) 방법을 사용하여 개발됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p127">Microsoft Intune is key component of the Microsoft Enterprise Mobility and Security Suite cloud service offering. To support the data governance strategy, all Microsoft cloud services are developed with the Microsoft Privacy and Security by Design and Privacy and Security by Default methodologies.</span></span>

<span data-ttu-id="88f9e-p128">이와 같이 Microsoft Intune 클라우드 서비스 제품은 Microsoft Azure 서비스 팀이 데이터 침해 프로세스에서 보호하기 위해 수행하는 것과 동일한 기술 및 조직적 방침을 따릅니다. 따라서 여기에 나오는 "Microsoft Azure 데이터 침해" 알림 문서에 설명된 모든 정보는 Microsoft Intune 서비스에서도 비슷합니다. 예를 들어, Microsoft Intune은 동일한 보안 인시던트 대응 프로세스 및 수명 주기(1단계: 감지부터 5단계<strong>:</strong> 닫기 및 사후 평가까지)를 유지하며, 고객 보안 인시던트 알림 프로세스도 동일합니다. 또한 Microsoft Intune은 Microsoft O365 팀과 직접 공조하여 Intune에서 모든 Microsoft O365 고객에 대한 침해 알림 의무를 이행합니다.</span><span class="sxs-lookup"><span data-stu-id="88f9e-p128">As such Microsoft Intune ‘s cloud service offering follows the same Technical and Organizational measures the Microsoft Azure service team(s) take for securing against data breach processes. Therefore, any information documented in the “Microsoft Azure Data Breach” notification document here is analogous to the Microsoft Intune service as well. For example, Microsoft Intune has the same Security Incident Response Process and Lifecycle (Stage 1: Detect thru Stage 5<strong>:</strong> Close and Postmortem) and also the same Customer Security Incident Notification process. In addition, Microsoft Intune also fulfills its obligations for Breach Notification for any Microsoft O365 customers using Intune by working directly with the Microsoft O365 team.</span></span>

<span data-ttu-id="88f9e-226">Microsoft에서 개인 데이터 위반을 감지하고 대처하는 방법에 대한 자세한 내용은 Service Trust Portal의 [GDPR에서 데이터 위반 알림](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88f9e-226">For more information about how Microsoft detects and responds to a breach of personal data, see [Data Breach Notification Under the GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) in the Service Trust Portal.</span></span>


#### <a name="learn-more"></a><span data-ttu-id="88f9e-227">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="88f9e-227">Learn more</span></span>
[<span data-ttu-id="88f9e-228">Microsoft 보안 센터</span><span class="sxs-lookup"><span data-stu-id="88f9e-228">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
