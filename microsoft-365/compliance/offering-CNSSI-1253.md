---
title: 위원회의 국가 보안 시스템 명령 아니요 1253 (CNSSI 1253)
description: Azure 정부용 CNSSI 1253 보안 제어를 사용 하 여 높은 기밀성, 높은 무결성 및 높은 가용성이 필요한 미국 정부 시스템을 지원 합니다.
keywords: Microsoft 365, 규정 준수, 제품
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 12af7c84a922e3db0b7d234dce6f4095ba062a64
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39860038"
---
# <a name="committee-on-national-security-systems-instruction-no-1253-cnssi-1253"></a><span data-ttu-id="c1921-105">위원회의 국가 보안 시스템 명령 아니요</span><span class="sxs-lookup"><span data-stu-id="c1921-105">Committee on National Security Systems Instruction No.</span></span> <span data-ttu-id="c1921-106">1253 (CNSSI 1253)</span><span class="sxs-lookup"><span data-stu-id="c1921-106">1253 (CNSSI 1253)</span></span>

## <a name="about-cnss-instruction-1253"></a><span data-ttu-id="c1921-107">CNSS 명령 1253 정보</span><span class="sxs-lookup"><span data-stu-id="c1921-107">About CNSS Instruction 1253</span></span>

<span data-ttu-id="c1921-108">CNSS (국가 보안 시스템)의 위원회는 미국 정부 부서 및 기관에 대 한 국내 cybersecurity 정책을 설정 하는 정부 기관입니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-108">The Committee on National Security Systems (CNSS) is a governmental organization that sets national cybersecurity policy for US government departments and agencies.</span></span> <span data-ttu-id="c1921-109">[Cnss 명령 아니요. 1253](https://www.dss.mil/Portals/69/documents/io/rmf/CNSSI_No1253.pdf), "국가 보안 시스템에 대 한 보안 분류 및 제어 선택"에서는 연방 기관에서 국가 보안 정보 및 시스템을 적절 한 보안 수준으로 분류 하기 위해 적용 해야 하는 보안 표준에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-109">The [CNSS Instruction No. 1253](https://www.dss.mil/Portals/69/documents/io/rmf/CNSSI_No1253.pdf), “Security Categorization and Control Selection for National Security Systems,” provides guidance on the security standards that federal agencies should apply to categorize national security information and systems at appropriate security levels.</span></span>  
  
<span data-ttu-id="c1921-110">CNSSI 1253은 NIST SP 800-53을 기반으로 하며, FedRAMP 높은 권한 부여에 대 한 제어 기준을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-110">The CNSSI 1253 builds on NIST SP 800-53, which provides the control baseline for the FedRAMP High authorization.</span></span> <span data-ttu-id="c1921-111">그러나 CNSSI 1253와 NIST 발행물 사이에는 몇 가지 중요 한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-111">There are, however, some key differences between the CNSSI 1253 and NIST publications.</span></span>  
  
<span data-ttu-id="c1921-112">예를 들어, CNSSI 1253 방법은 보안 제어를 통해 기밀성, 무결성 및 가용성의 연결을 명시적으로 정의 하 고, 국립 보안 커뮤니티에 대 한 보안 제어 오버레이 사용을 구체화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-112">For example, the CNSSI 1253 approach explicitly defines the associations of Confidentiality, Integrity, and Availability with security controls, and refines the use of security control overlays for the national security community.</span></span> <span data-ttu-id="c1921-113">CNSS는 이러한 세 가지 보안 목표 각각에 대해 별도의 Low, Medium 및 High 범주를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-113">The CNSS uses a separate Low, Medium, and High category for each of these three security objectives.</span></span> <span data-ttu-id="c1921-114">이렇게 하면 보통-낮음 (보통 기밀성, 일반 무결성, 낮은 가용성)과 같은 분류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-114">This results in categorizations such as Moderate-Moderate-Low — Moderate Confidentiality, Moderate Integrity, and Low Availability.</span></span> <span data-ttu-id="c1921-115">CNSSI 1253 그런 다음 NIST SP 800-53의 컨트롤을 사용 하 여 가능한 각 시스템 분류에 대 한 적절 한 보안 기준을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-115">CNSSI 1253 then provides the appropriate security baselines for each possible system categorization using controls from NIST SP 800-53.</span></span>

## <a name="microsoft-and-cnssi-1253"></a><span data-ttu-id="c1921-116">Microsoft 및 CNSSI 1253</span><span class="sxs-lookup"><span data-stu-id="c1921-116">Microsoft and CNSSI 1253</span></span>

<span data-ttu-id="c1921-117">FedRAMP 승인 된 타사 평가 조직 (3PAO), Kratos SecureInfo는 CNSSI 1253 고가-높은 기준선을 사용 하 여 Microsoft Azure 정부 시스템의 준수 여부를 독립적으로 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-117">A FedRAMP-approved third-party assessment organization (3PAO), Kratos SecureInfo, has independently validated the compliance of the Microsoft Azure Government system with the CNSSI 1253 High-High-High Baseline.</span></span> <span data-ttu-id="c1921-118">Kratos SecureInfo attests Azure 정부의 CNSSI 1253 보안 평가 보고서 (SAP)에 있는 해당 보안 제어에 대 한 완벽 한 평가를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-118">Kratos SecureInfo attests that the CNSSI 1253 Security Assessment Report (SAR) of Azure Government provides a complete assessment of the applicable security controls stipulated in the Security Assessment Plan (SAP).</span></span> <span data-ttu-id="c1921-119">이 특별 행정구는 높은 기밀성, 높은 무결성 및 고가용성을 필요로 하는 시스템에 대해 CNSSI 1253 보안 제어를 선택 하기 위해 Azure 정부의 유효성을 검사 하기 위해 수행 된 테스트를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-119">The SAR documents the testing conducted to validate Azure Government against a selection of CNSSI 1253 security controls for systems requiring High Confidentiality, High Integrity, and High Availability.</span></span>  
  
<span data-ttu-id="c1921-120">현재 Azure 정부는 FedRAMP High Provisional 권한 부여 (공동 인증 위원회)에서 실행 되는 (P-ATO), 클라우드 컴퓨팅 보안의 영향 수준 5에 있는 PA (방어 Provisional 인증)의 부서를 운영 하 고 있습니다. 요구 사항 가이드 (SRG)</span><span class="sxs-lookup"><span data-stu-id="c1921-120">Azure Government currently possesses a FedRAMP High Provisional Authorization to Operate (P-ATO) issued by the Joint Authorization Board (JAB), and a Department of Defense Provisional Authorization (PA) at Impact Level 5 of the Cloud Computing Security Requirements Guide (SRG).</span></span> <span data-ttu-id="c1921-121">이러한 인증을 사용 하는 경우 Kratos SecureInfo는 이전 평가에서 테스트 한 보안 제어를 분석 하 여 CNSSI 1253 High-High 기준을 준수 하기 위해 테스트할 추가 CNSSI 1253 보안 제어를 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-121">Using these authorizations, Kratos SecureInfo analyzed the security controls that were tested in the previous assessments to determine which additional CNSSI 1253 security controls to test to ensure compliance with the CNSSI 1253 High-High-High baseline.</span></span> <span data-ttu-id="c1921-122">Kratos SecureInfo에서는 적절 한 43 적용 가능 보안 제어가 성공적인 구현 되었는지 확인 하 고, CNSSI 1253 특별 행정구에서 전체 테스트의 결과를 게시 하기 위해 증거를 검사 하 고 인터뷰를 실시 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-122">Kratos SecureInfo examined evidence and conducted interviews to validate the successful implementation of 43 applicable security controls and published the results of its complete testing in the CNSSI 1253 SAR.</span></span>  
  
<span data-ttu-id="c1921-123">까다로운 CNSSI 1253 요구 사항을 충족 하는 Azure 정부의 규정 준수는 Azure에서 CNSSI 1253과 호환 되는 다양 한 서비스를 제공 하 여 비용 절감 및 엄격한 혜택을 얻을 수 있도록 미국에서 공용 섹터 고객을 지원 한다는 것을 의미 합니다. Microsoft 클라우드의 보안입니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-123">The compliance of Azure Government with the demanding CNSSI 1253 requirements means that Azure can offer public sector customers in the United States a rich array of services compliant with CNSSI 1253, enabling them to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="c1921-124">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="c1921-124">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="c1921-125">Azure 정부</span><span class="sxs-lookup"><span data-stu-id="c1921-125">Azure Government</span></span>](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="c1921-126">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="c1921-126">Audits, reports, and certificates</span></span>

<span data-ttu-id="c1921-127">Azure 정부 CNSSI 1253, CNSSI 1253 High-높은 기준선 준수 증명</span><span class="sxs-lookup"><span data-stu-id="c1921-127">Azure Government CNSSI 1253 attestation of compliance with the CNSSI 1253 High-High-High baseline</span></span>

## <a name="how-to-implement"></a><span data-ttu-id="c1921-128">구현 방법</span><span class="sxs-lookup"><span data-stu-id="c1921-128">How to implement</span></span>

- <span data-ttu-id="c1921-129">[Azure 정부 설명서](https://docs.microsoft.com/azure/azure-government/): 자습서 및 방법 가이드 개발자가 Azure 정부를 사용 하 여 서비스를 배포 하 고 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-129">[Azure government documentation](https://docs.microsoft.com/azure/azure-government/): Tutorials and how-to guides help developers deploy and manage services using Azure Government.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c1921-130">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="c1921-130">Frequently asked questions</span></span>

<span data-ttu-id="c1921-131">**CNSSI 1253를 적용할 대상**</span><span class="sxs-lookup"><span data-stu-id="c1921-131">**To whom does CNSSI 1253 apply?**</span></span>

<span data-ttu-id="c1921-132">NSS (국내 보안 시스템)을 사용 하는 고객은 CNSSI 1253 요구 사항 및 컨트롤을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-132">Customers with national security systems (NSS) must comply with CNSSI 1253 requirements and controls.</span></span>

<span data-ttu-id="c1921-133">**CNSSI 1253 보안 컨트롤에 대해 테스트 된 Azure 환경은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="c1921-133">**Which Azure environments have been tested against CNSSI 1253 security controls?**</span></span>

<span data-ttu-id="c1921-134">Azure 정부 (FedRAMP 패키지 ID F1603087869)에서 이러한 컨트롤을 다시 테스트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-134">Azure Government (FedRAMP package ID F1603087869) has been tested again these controls.</span></span>

## <a name="resources"></a><span data-ttu-id="c1921-135">리소스</span><span class="sxs-lookup"><span data-stu-id="c1921-135">Resources</span></span>

- [<span data-ttu-id="c1921-136">Azure 정부 란?</span><span class="sxs-lookup"><span data-stu-id="c1921-136">What is Azure Government?</span></span>](https://docs.microsoft.com/azure/azure-government/documentation-government-welcome)
- [<span data-ttu-id="c1921-137">Azure 정부</span><span class="sxs-lookup"><span data-stu-id="c1921-137">Azure Government</span></span>](https://aka.ms/Azure-Government)
- [<span data-ttu-id="c1921-138">Microsoft 및 FedRAMP</span><span class="sxs-lookup"><span data-stu-id="c1921-138">Microsoft and FedRAMP</span></span>](offering-fedramp.md)
- [<span data-ttu-id="c1921-139">Microsoft 및 DoD Provisional 권한 부여</span><span class="sxs-lookup"><span data-stu-id="c1921-139">Microsoft and DoD Provisional Authorization</span></span>](offering-DoD-DISA-L2-L4-L5.md)
- [<span data-ttu-id="c1921-140">Microsoft Government 클라우드</span><span class="sxs-lookup"><span data-stu-id="c1921-140">Microsoft Government Cloud</span></span>](https://www.microsoft.com/enterprise/government)
- [<span data-ttu-id="c1921-141">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="c1921-141">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="c1921-142">제공 사항의 배경 설명 다운로드</span><span class="sxs-lookup"><span data-stu-id="c1921-142">Download the offering backgrounder</span></span>

<span data-ttu-id="c1921-143">이 제공 사항에 대한 배경 설명 문서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="c1921-143">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="c1921-144">[PDF](https://download.microsoft.com/download/6/E/C/6EC27E89-826E-44CB-A107-2A37AC879206/CNSSI_1253-Compliance.pdf)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c1921-144">Download the [PDF](https://download.microsoft.com/download/6/E/C/6EC27E89-826E-44CB-A107-2A37AC879206/CNSSI_1253-Compliance.pdf).</span></span>
