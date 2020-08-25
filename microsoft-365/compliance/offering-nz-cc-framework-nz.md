---
title: 뉴질and 정부 클라우드 컴퓨팅 보안 및 개인 정보 보호 고려 사항
description: Microsoft NZ는 뉴질and 클라우드 컴퓨팅 프레임워크에 게시된 질문을 해결합니다.
keywords: Microsoft 365, 규정 준수, 제품
localization_priority: None
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
ms.openlocfilehash: 99e7d28bea37ec282bd6358b5af81a3078dfdd38
ms.sourcegitcommit: b7f4f1e04b27519b818d4255022b28f99fbe54af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46852504"
---
# <a name="new-zealand-government-cloud-computing-security-and-privacy-considerations"></a><span data-ttu-id="e614e-104">뉴질and 정부 클라우드 컴퓨팅 보안 및 개인 정보 보호 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e614e-104">New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

## <a name="new-zealand-government-cloud-computing-security-and-privacy-overview"></a><span data-ttu-id="e614e-105">New Zealand Government Cloud Computing Security and Privacy 개요</span><span class="sxs-lookup"><span data-stu-id="e614e-105">New Zealand Government Cloud Computing Security and Privacy overview</span></span>

<span data-ttu-id="e614e-106">2015년 10월NewNewZealand Government는 일반 부문에서 정보 기술을 사용함에 대해 "클라우드 우선" 정책을 재검토하는 전기 적인 ICT 전략을 개정했습니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-106">In October 2015, the New Zealand Government endorsed a revised all-government ICT strategy that reaffirmed its “cloud first” policy on using information technology across the public sector.</span></span> <span data-ttu-id="e614e-107">수정된 전략은 GCIO(NZ 정부 기관)의 권한 하에서 개발 및 구현된 "클라우드 컴퓨팅 위험 및 보증 프레임워크"를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-107">The revised strategy retains the “Cloud Computing Risk and Assurance Framework” that was developed and implemented under the authority of the NZ Government Chief Information Officer (GCIO).</span></span>

<span data-ttu-id="e614e-108">정부는 모든 뉴질질국 서비스 관련 기부가 클라우드 서비스를 평가하고 채택할 때 이 프레임워크 내에서 작동할 것이라 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-108">The government expects all New Zealand State Service agencies to work within this framework when assessing and adopting cloud services.</span></span> <span data-ttu-id="e614e-109">"클라우드 컴퓨팅 요구 사항"에서는 정부의 클라우드 정책 기록에 대한 개요와 함께 클라우드 서비스를 도출할 때 수행해야 하는 기기니즘을 간략해설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-109">“Requirements for Cloud Computing” outlines what agencies must do when adopting cloud services along with an overview of the history of the government’s cloud policy.</span></span>

<span data-ttu-id="e614e-110">잠재적 클라우드 솔루션에 대한 일관되고 강력한 실사를 수행하도록 NZ 정부 기관을 지원하기 위해 GCIO는 "클라우드 컴퓨팅: 정보 보호 고려 사항"("클라우드 컴퓨팅 ISPC")을 게시하시기 바를 들수주세요.</span><span class="sxs-lookup"><span data-stu-id="e614e-110">To assist NZ government agencies in conducting consistent and robust due diligence on potential cloud solutions, the GCIO has published “Cloud Computing: Information Security and Privacy Considerations” (the “Cloud Computing ISPC”).</span></span> <span data-ttu-id="e614e-111">이 문서에는 데이터 주위, 개인 정보, 보안, 관리, 기밀성, 데이터 무결성, 가용성 및 인시던트 대응 및 관리에 관한 FAQ가 100개 이상 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-111">This document contains more than 100 questions focused on data sovereignty, privacy, security, governance, confidentiality, data integrity, availability, and incident response and management.</span></span> <span data-ttu-id="e614e-112">"클라우드 컴퓨팅 IPSC"는 클라우드 서비스 제공자가 공식 준수를 증명해야 하는 NZ 정부 표준을 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-112">Note that “Cloud Computing IPSC” does not define a NZ government standard against which cloud service providers must demonstrate formal compliance.</span></span> <span data-ttu-id="e614e-113">하지만 문서에 설정된 여러 질문은 클라우드 서비스 제공자가 다양한 관련 표준을 준수하는 방식을 이해하는 데 있어서도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-113">Many of the questions set out in the document do, however, point toward the importance of understanding how cloud service providers comply with a wide array of relevant standards.</span></span>

<span data-ttu-id="e614e-114">Microsoft 및 New Zealand Government 클라우드 컴퓨팅 보안 및 개인 정보 보호 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e614e-114">Microsoft and New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

<span data-ttu-id="e614e-115">Microsoft New Zealand는 Microsoft 엔터프라이즈 클라우드 서비스를 분석 및 평가하는 데 도용하기 위해 엔터프라이즈 클라우드 서비스가 "클라우드 컴퓨팅 ISPC"에 설정된 질문을 Microsoft 클라우드 서비스에 인증되는 표준에 연결하여 어떻게 해결할 수 있는지를 보여주는 일련의 문서를 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-115">To help agencies undertake their analysis and evaluation of Microsoft enterprise cloud services, Microsoft New Zealand has produced a series of documents showing how its enterprise cloud services address the questions set out in the “Cloud Computing ISPC” by linking them to the standards against which Microsoft cloud services are certified.</span></span> <span data-ttu-id="e614e-116">이 인증은 Microsoft가 공개 및 개인 부문 고객에게 클라우드 서비스가 개인 정보 보호 및 보안 위험을 완화하고 데이터 주권 문제를 해결하기 위해 설계, 제조 및 운영되고 있는지 를 지원하는 방법에 중심이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-116">These certifications are central to how Microsoft assures both public and private sector customers that its cloud services are designed, built, and operated to effectively mitigate privacy and security risks and address data sovereignty concerns.</span></span>

<span data-ttu-id="e614e-117">Azure 보안 및 규정 준수 Blueprint를 사용하여 NZ CC Framework 배포를 가중화하는 방법에 대해 알아봅니다. [NZ CC 프레임워크에 대한 Azure 대응 다운로드](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span><span class="sxs-lookup"><span data-stu-id="e614e-117">Learn how to accelerate your NZ CC Framework deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the NZ CC Framework](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="e614e-118">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="e614e-118">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="e614e-119">Azure 및 Azure Government</span><span class="sxs-lookup"><span data-stu-id="e614e-119">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="e614e-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e614e-120">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="e614e-121">Intune</span><span class="sxs-lookup"><span data-stu-id="e614e-121">Intune</span></span>
- <span data-ttu-id="e614e-122">독립형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="e614e-122">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- [<span data-ttu-id="e614e-123">Office 365</span><span class="sxs-lookup"><span data-stu-id="e614e-123">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="e614e-124">Exchange Online, SharePoint Online 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e614e-124">Exchange Online, SharePoint Online, and Microsoft Teams.</span></span> <span data-ttu-id="e614e-125">Microsoft NZ는 Exchange Online 및 SEEMail 통합을 위한 참조 아키텍처를 개발하기 위해 GCIO 팀과 함께 노축하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-125">Microsoft NZ has worked with the GCIO team to develop a reference architecture for integrating Exchange Online and SEEMail.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e614e-126">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="e614e-126">Frequently asked questions</span></span>

<span data-ttu-id="e614e-127">**프레임워크는 누엇에게 적용하나요?**</span><span class="sxs-lookup"><span data-stu-id="e614e-127">**To whom does the framework apply?**</span></span>

<span data-ttu-id="e614e-128">공공 및 비 공공 서비스 부서, 20개의 중구영보보드 및 일수의 구속 온사이드에 속하는 조직은 클라우드 서비스를 사용하기로 결정한 경우 프레임워크를 이용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-128">Organizations that fall under the GCIO mandate — the public and non-public service departments, the 20 district health boards, and seven Crown entities — must adhere to the framework when they are deciding on the use of a cloud service.</span></span>

<span data-ttu-id="e614e-129">**기관에서 이 프레임워크에 대한 Microsoft의 대응(ICT 시스템의 인증 프로세스)을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e614e-129">**Can my agency use Microsoft’s responses to this framework in the certification process of our ICT systems?**</span></span>

<span data-ttu-id="e614e-130">기관이 [뉴질레드](https://go.microsoft.com/fwlink/p/?linkid=2099496)정보 보안 수동에서 해당 ICT 시스템의 인증 및 인증을 받아야 하는 경우에는 이러한 응답을 분석의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e614e-130">If your agency is required to undertake certification and accreditation of its ICT system under the [New Zealand Information Security Manual](https://go.microsoft.com/fwlink/p/?linkid=2099496), then you can use these responses as part of your analysis.</span></span>

## <a name="resources"></a><span data-ttu-id="e614e-131">리소스</span><span class="sxs-lookup"><span data-stu-id="e614e-131">Resources</span></span>

- [<span data-ttu-id="e614e-132">오프사이트 호스팅되는 Office 생산성 서비스에 대한 보안 요구 사항: Office 365 준수 가이드</span><span class="sxs-lookup"><span data-stu-id="e614e-132">Security requirements for offshore hosted Office productivity services: conformance guide for Office 365</span></span>](https://aka.ms/o365-gcio-conformance-guidance)
- [<span data-ttu-id="e614e-133">뉴질레드 보안 및 개인 정보 보호 요구 사항 컨텍스트의 Microsoft Azure 규정 준수</span><span class="sxs-lookup"><span data-stu-id="e614e-133">Microsoft Azure compliance in the context of New Zealand security and privacy requirements</span></span>](https://aka.ms/azurecompliancenewzealand)
- [<span data-ttu-id="e614e-134">NZ 정부 ICT 전략 2015</span><span class="sxs-lookup"><span data-stu-id="e614e-134">NZ Government ICT Strategy 2015</span></span>](https://www.ict.govt.nz/strategy-and-action-plan/strategy/)
- [<span data-ttu-id="e614e-135">클라우드 컴퓨팅에 대한 NZ 정부 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e614e-135">NZ Government requirements for cloud computing</span></span>](https://aka.ms/NZ-Cloud-Requirements)
- [<span data-ttu-id="e614e-136">클라우드 컴퓨팅: 정보 보안 및 개인 정보 보호 고려 사항(ISPC)</span><span class="sxs-lookup"><span data-stu-id="e614e-136">Cloud Computing: Information Security and Privacy Considerations (ISPC)</span></span>](https://www.digital.govt.nz/standards-and-guidance/technology-and-architecture/cloud-services/)
- [<span data-ttu-id="e614e-137">Microsoft 온라인 서비스 사용 약관</span><span class="sxs-lookup"><span data-stu-id="e614e-137">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- <span data-ttu-id="e614e-138">[Office 365: SEEMail Integration 및 참조 아키텍처(클라우드](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) 서비스 도입에 대한 추가 Microsoft NZ 지침)</span><span class="sxs-lookup"><span data-stu-id="e614e-138">[Office 365: SEEMail Integration and Reference Architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) (additional Microsoft NZ guidance on cloud service adoption)</span></span>
- [<span data-ttu-id="e614e-139">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="e614e-139">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-responses-to-cloud-computing-ipsc"></a><span data-ttu-id="e614e-140">'클라우드 컴퓨팅 IPSC'에 대한 Microsoft의 대응</span><span class="sxs-lookup"><span data-stu-id="e614e-140">Microsoft responses to 'Cloud Computing IPSC'</span></span>

- [<span data-ttu-id="e614e-141">Azure</span><span class="sxs-lookup"><span data-stu-id="e614e-141">Azure</span></span>](https://aka.ms/Azure-NZ-response)
- [<span data-ttu-id="e614e-142">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e614e-142">Dynamics 365</span></span>](https://aka.ms/d365-nz-response)
- [<span data-ttu-id="e614e-143">Intune</span><span class="sxs-lookup"><span data-stu-id="e614e-143">Intune</span></span>](https://aka.ms/Intune-NZ-response)
- [<span data-ttu-id="e614e-144">Office 365</span><span class="sxs-lookup"><span data-stu-id="e614e-144">Office 365</span></span>](https://aka.ms/O365-NZ-Response)
- [<span data-ttu-id="e614e-145">Power BI</span><span class="sxs-lookup"><span data-stu-id="e614e-145">Power BI</span></span>](https://download.microsoft.com/download/5/1/7/51726B9B-2E76-49C4-9D4F-A36BF025CB93/Response-to-GCIO-105-questions-Power-BI.pdf)
