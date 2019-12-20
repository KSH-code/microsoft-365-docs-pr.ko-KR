---
title: 연방 위험 및 권한 부여 관리 프로그램 (FedRAMP)
description: Microsoft에는 미국 연방 위험 및 권한 부여 관리 프로그램인 P-ATOs 및 ATOs가 부여 되었습니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: da8e7e473210c42cb5d95f2701779561c95b6bb3
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40804951"
---
# <a name="federal-risk-and-authorization-management-program-fedramp"></a><span data-ttu-id="4f77b-104">연방 위험 및 권한 부여 관리 프로그램 (FedRAMP)</span><span class="sxs-lookup"><span data-stu-id="4f77b-104">Federal Risk and Authorization Management Program (FedRAMP)</span></span>

## <a name="fedramp-overview"></a><span data-ttu-id="4f77b-105">FedRAMP 개요</span><span class="sxs-lookup"><span data-stu-id="4f77b-105">FedRAMP overview</span></span>

<span data-ttu-id="4f77b-106">미국 연방 위험 및 권한 부여 관리 프로그램 (FedRAMP)은 연방 정보 보안 관리 작업에서 클라우드 컴퓨팅 제품 및 서비스를 평가, 모니터링 및 승인 하는 표준화 된 방법을 제공 하도록 설정 되었습니다 ( FISMA)를 만들고 연방 기관에의 한 안전한 클라우드 솔루션 채택 속도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-106">The US Federal Risk and Authorization Management Program (FedRAMP) was established to provide a standardized approach for assessing, monitoring, and authorizing cloud computing products and services under the Federal Information Security Management Act (FISMA), and to accelerate the adoption of secure cloud solutions by federal agencies.</span></span>

<span data-ttu-id="4f77b-107">이제 관리 및 예산 사무소에는 모든 임원 연방 기관에서 FedRAMP를 사용 하 여 클라우드 서비스의 보안을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-107">The Office of Management and Budget now requires all executive federal agencies to use FedRAMP to validate the security of cloud services.</span></span> <span data-ttu-id="4f77b-108">다른 기관 에서도이를 채택 했으며, 공용 섹터의 다른 영역 에서도 유용 합니다. 국내 표준 및 기술 (NIST) 800-53은 표준을 설정 하며, FedRAMP는 CSP (클라우드 서비스 공급자)가 해당 표준을 충족 하는지 인증 하는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-108">(Other agencies have also adopted it, so it is useful in other areas of the public sector as well.) The National Institute of Standards and Technology (NIST) 800-53 sets the standard, and FedRAMP is the program that certifies that a cloud service provider (CSP) meets that standard.</span></span>

<span data-ttu-id="4f77b-109">Ca에 서비스를 판매할 수 있도록 하는 Csp desiring는 FedRAMP 준수를 시연 하기 위해 세 가지 경로를 사용 하 여 Provisional 기관에서 작동 (P-ATO) 합니다. 정부 기관에서 운영 (ATO) 권한을 받습니다. 또는 독립적으로 작동 하 여 프로그램 요구 사항을 충족 하는 CSP 제공 패키지를 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-109">CSPs desiring to sell services to a federal agency can take three paths to demonstrate FedRAMP compliance: earn a Provisional Authority to Operate (P-ATO) from the Joint Authorization Board (JAB); receive an Authority to Operate (ATO) from a federal agency; or work independently to develop a CSP Supplied Package that meets program requirements.</span></span> <span data-ttu-id="4f77b-110">이러한 각 경로에는 FedRAMP PMO (Program Management Office) 및 프로그램에서 공인 하는 독립 타사 조직의 평가를 통해 엄격한 기술 검토가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-110">Each of these paths requires a stringent technical review by the FedRAMP Program Management Office (PMO) and an assessment by an independent third-party organization that is accredited by the program.</span></span>

<span data-ttu-id="4f77b-111">FedRAMP 인증은 NIST 지침 (낮음, 중간, 높음)에 따라 세 가지 영향 수준으로 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-111">FedRAMP authorizations are granted at three impact levels based on NIST guidelines — low, medium, and high.</span></span> <span data-ttu-id="4f77b-112">이러한 경우 기밀성, 무결성 또는 가용성의 손실로 인 한 영향을 조직에 미칠 수 있는 영향은 낮음 (제한적 효과), 중간 (심각한 부정적 효과), 높음 (심각 또는 치명적 효과)</span><span class="sxs-lookup"><span data-stu-id="4f77b-112">These rank the impact that the loss of confidentiality, integrity, or availability could have on an organization — low (limited effect), medium (serious adverse effect), and high (severe or catastrophic effect).</span></span>

## <a name="microsoft-and-fedramp"></a><span data-ttu-id="4f77b-113">Microsoft 및 FedRAMP</span><span class="sxs-lookup"><span data-stu-id="4f77b-113">Microsoft and FedRAMP</span></span>

<span data-ttu-id="4f77b-114">Azure 정부, Office 365 U.S. 정부 및 Dynamics 365 정부를 포함 하는 Microsoft의 정부 클라우드 서비스는 미국 연방 위험 및 FedRAMP (권한 부여 관리 프로그램)의 까다로운 요구 사항을 충족 하 고 미국 연방 기관을 사용 하도록 설정 합니다. Microsoft 클라우드의 비용 절감 및 엄격한 보안 혜택을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-114">Microsoft’s government cloud services, including Azure Government, Office 365 U.S. Government, and Dynamics 365 Government meet the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling U.S. federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

<span data-ttu-id="4f77b-115">Microsoft 정부 클라우드 서비스는 공공 부문 고객에 게 FedRAMP와 호환 되는 다양 한 서비스를 제공 하며, FedRAMP에 대 한 Azure 보안 및 규정 준수 청사진을 비롯 한 강력한 지침 및 구현 도구를 통해 배포를 자동화 하는 데 도움이 됩니다. FedRAMP 환경에서의 Azure 리소스 구성</span><span class="sxs-lookup"><span data-stu-id="4f77b-115">Microsoft government cloud services offer public sector customers a rich array of services compliant with FedRAMP, and robust guidance and implementation tools, including the Azure Security and Compliance Blueprint for FedRAMP, which helps automate deployment and configuration of Azure resources in a FedRAMP environment.</span></span>

<span data-ttu-id="4f77b-116">Microsoft 클라우드에서 FEDRAMP의 혜택에 대해 자세히 알아보기: [FEDRAMP 준수 Backgrounder 다운로드](https://aka.ms/fedramp-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="4f77b-116">Learn about the benefits of FEDRAMP on the Microsoft Cloud: [Download the FedRAMP compliance backgrounder](https://aka.ms/fedramp-backgrounder)</span></span>

<span data-ttu-id="4f77b-117">Azure 보안 및 준수 청사진을 사용 하 여 FEDRAMP 배포를 가속화 하는 방법을 알아봅니다. [Azure 다운로드-청사진 FEDRAMP HIGH SSP](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=64de30d4-42c6-47e7-bd52-0be935710df9&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_FedRAMP%20Blueprint)</span><span class="sxs-lookup"><span data-stu-id="4f77b-117">Learn how to accelerate your FEDRAMP deployment with our Azure Security and Compliance Blueprint: [Download the Azure — Blueprint FedRAMP High SSP](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=64de30d4-42c6-47e7-bd52-0be935710df9&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_FedRAMP%20Blueprint)</span></span>

## <a name="microsoft-azure-p-atos"></a><span data-ttu-id="4f77b-118">Microsoft Azure P-ATOs</span><span class="sxs-lookup"><span data-stu-id="4f77b-118">Microsoft Azure P-ATOs</span></span>

<span data-ttu-id="4f77b-119">Azure 및 Azure 정부에서 공동 인증 위원회 로부터 P-ATO을 획득 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-119">Azure and Azure Government have earned a P-ATO from the Joint Authorization Board</span></span>

<span data-ttu-id="4f77b-120">JAB는 FedRAMP의 기본 거 버 넌 스 및 의사 결정 몸체입니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-120">The JAB is the primary governance and decision-making body for FedRAMP.</span></span> <span data-ttu-id="4f77b-121">방어 부서의 대표, Homeland 보안 부서 및 일반 서비스 관리가 해당 보드에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-121">Representatives from the Department of Defense, the Department of Homeland Security, and the General Services Administration serve on the board.</span></span> <span data-ttu-id="4f77b-122">이 보드는 FedRAMP 규정 준수를 보여 주는 Csp에 ATO을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-122">The board grants a P-ATO to CSPs that have demonstrated FedRAMP compliance.</span></span>

<span data-ttu-id="4f77b-123">Azure는 보통 영향 수준으로 P-ATO을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-123">Azure maintains a P-ATO at the Moderate Impact Level.</span></span> <span data-ttu-id="4f77b-124">(Azure는 P-ATO를 수신 하는 인프라 및 플랫폼 서비스가 포함 된 첫 번째 공용 클라우드입니다.) 또한 JAB에는 높은 영향 수준에 따라 Azure 정부 a P-ATO이 부여 되며, FedRAMP 인정을 위한 가장 높은 막대 이며, Azure 정부 사용을 통해 중요 한 데이터를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-124">(Azure was the first public cloud with infrastructure and platform services to receive a P-ATO.) The JAB has also granted Azure Government a P-ATO at the High Impact Level, the highest bar for FedRAMP accreditation, which authorizes the use of Azure Government to process highly sensitive data.</span></span> <span data-ttu-id="4f77b-125">필수 NIST 800-53 표준은 정보 시스템의 보안 종류 (기밀성, 무결성 및 가용성)를 설정 하 여 조직의 정보 및 정보 시스템에 대 한 잠재적 영향을 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-125">The mandatory NIST 800-53 standards establish security categories of information systems — confidentiality, integrity, and availability — to assess the potential impact on an organization should its information and information systems be compromised.</span></span> <span data-ttu-id="4f77b-126">Azure 및 Azure 정부에 대 한 FedRAMP 감사에는 인프라, 개발, 운영, 관리 및 범위 내 서비스 지원을 포함 하는 정보 보안 관리 시스템이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-126">The FedRAMP audit of Azure and Azure Government included the Information Security Management System that encompasses infrastructure, development, operations, management, and support of in-scope services.</span></span>

<span data-ttu-id="4f77b-127">P-ATO에 대 한 권한이 부여 되 면 CSP는 여전히 인증을 받아야 합니다 (ATO).</span><span class="sxs-lookup"><span data-stu-id="4f77b-127">Once a P-ATO is granted, a CSP still requires an authorization — an ATO — from any government agency it works with.</span></span> <span data-ttu-id="4f77b-128">Azure의 경우 정부 기관은 자체 보안 권한 부여 프로세스에서 Azure P-ATO을 사용 하 여 FedRAMP 요구 사항을 충족 하는 에이전시 ATO을 발급 하기 위한 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-128">In the case of Azure, a government agency can use the Azure P-ATO in its own security authorization process and rely on it as the basis for issuing an agency ATO that also meets FedRAMP requirements.</span></span>

## <a name="dynamics-365-us-government-ato"></a><span data-ttu-id="4f77b-129">Dynamics 365 미국 정부 ATO</span><span class="sxs-lookup"><span data-stu-id="4f77b-129">Dynamics 365 U.S. Government ATO</span></span>

- <span data-ttu-id="4f77b-130">Dynamics 365 U.S. 정부에서 HUD 로부터 ATO을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-130">Dynamics 365 U.S. Government has received an ATO from HUD</span></span>
- <span data-ttu-id="4f77b-131">Dynamics 365 U.S. 정부에는 FedRAMP 에이전시 ATO이 고 HUD (도시 개발) 부서에 의해 높은 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-131">Dynamics 365 U.S. Government was granted a FedRAMP Agency ATO at the High Impact Level by the Department of Housing and Urban Development (HUD).</span></span> <span data-ttu-id="4f77b-132">인증 범위는 정부 커뮤니티 클라우드로 제한 되지만 Dynamics 365 미국 정부 비즈니스 및 엔터프라이즈 계획은 동일한 엄격한 FedRAMP 컨트롤 집합에 따라 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-132">(Note that although the scope of the certification is limited to the Government Community Cloud, Dynamics 365 U.S. Government business and enterprise plans operate following the same set of stringent FedRAMP controls.)</span></span>

## <a name="office-365-atos"></a><span data-ttu-id="4f77b-133">Office 365 ATOs</span><span class="sxs-lookup"><span data-stu-id="4f77b-133">Office 365 ATOs</span></span>

- <span data-ttu-id="4f77b-134">Office 365, Office 365 미국 정부에는 DHHS의 ATO가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-134">Office 365, Office 365 U.S. Government have an ATO from DHHS.</span></span>
- <span data-ttu-id="4f77b-135">Office 365 미국 정부 방어는 DISA (방어 정보 시스템 에이전시) 로부터 P를 ATO 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-135">Office 365 U.S. Government Defense has a P-ATO from Defense Information Systems Agency (DISA).</span></span>
- <span data-ttu-id="4f77b-136">Office 365 (엔터프라이즈 및 비즈니스 계획) 및 Office 365 U.S. 정부에는 검사기의 일반에 해당 하는 FedRAMP 에이전시 ATO (의료 및 휴먼 서비스) 사무실의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-136">Office 365 (Enterprise and Business plans) and Office 365 U.S. Government have a FedRAMP Agency ATO at the Moderate Impact Level from the Department of Health and Human Services (DHHS) Office of the Inspector General.</span></span> <span data-ttu-id="4f77b-137">Office 365 미국 정부는이 인증을 얻기 위한 최초 클라우드 기반 전자 메일 및 공동 작업 서비스 였습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-137">Office 365 U.S. Government was the first cloud-based email and collaboration service to obtain this authorization.</span></span>
- <span data-ttu-id="4f77b-138">O365 미국 정부 방어를 사용 하려는 고객은 DISA P-ATO을 활용 하 여 O365의 수락을 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-138">Any customer wishing to consume O365 U.S. Government Defense may utilize the DISA P-ATO to generate an Agency ATO to document their acceptance of O365.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="4f77b-139">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="4f77b-139">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="4f77b-140">Azure 및 Azure Government</span><span class="sxs-lookup"><span data-stu-id="4f77b-140">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2095323)
- [<span data-ttu-id="4f77b-141">Dynamics 365 미국 정부</span><span class="sxs-lookup"><span data-stu-id="4f77b-141">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="4f77b-142">Intune</span><span class="sxs-lookup"><span data-stu-id="4f77b-142">Intune</span></span>
- [<span data-ttu-id="4f77b-143">Office 365 및 Office 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="4f77b-143">Office 365 and Office 365 U.S. Government</span></span>](https://aka.ms/o365-compliance-framework)
- <span data-ttu-id="4f77b-144">Office 365 US Government Defense</span><span class="sxs-lookup"><span data-stu-id="4f77b-144">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="4f77b-145">독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="4f77b-145">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="4f77b-146">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="4f77b-146">Microsoft Defender ATP</span></span>

> [!NOTE]
> <span data-ttu-id="4f77b-147">Azure 정부 내에 Azure Active Directory를 사용 하려면 Azure 공개 클라우드에서 Azure 정부 외부에 배포 된 구성 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-147">The use of Azure Active Directory within Azure Government requires the use of components that are deployed outside of Azure Government on the Azure public cloud.</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="4f77b-148">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="4f77b-148">Audits, reports, and certificates</span></span>

<span data-ttu-id="4f77b-149">Microsoft는 ATO 및 ATOs를 유지 하기 위해 매년 클라우드 서비스를 recertify 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-149">Microsoft is required to recertify its cloud services each year to maintain its P-ATO and ATOs.</span></span> <span data-ttu-id="4f77b-150">이렇게 하려면 Microsoft에서 해당 보안 제어를 지속적으로 모니터링 하 고 평가 해야 하며 해당 서비스의 보안이 준수 되 고 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-150">To do so, Microsoft must monitor and assess its security controls continuously, and demonstrate that the security of its services remains in compliance.</span></span>

- [<span data-ttu-id="4f77b-151">Microsoft 클라우드 서비스 인증</span><span class="sxs-lookup"><span data-stu-id="4f77b-151">Microsoft cloud services authorizations</span></span>](https://marketplace.fedramp.gov/#/product/azure-government?sort=productName&productNameSearch=azure)
- [<span data-ttu-id="4f77b-152">Microsoft FedRAMP 감사 보고서</span><span class="sxs-lookup"><span data-stu-id="4f77b-152">Microsoft FedRAMP Audit Reports</span></span>](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="ramp-up-your-fedramp-solutions-on-azure-government"></a><span data-ttu-id="4f77b-153">Azure 정부에서 FedRAMP 솔루션 진입</span><span class="sxs-lookup"><span data-stu-id="4f77b-153">Ramp up your FedRAMP solutions on Azure Government</span></span>

<span data-ttu-id="4f77b-154">Microsoft에서 ATO 프로세스를 안내 하 고 Azure 보안 및 준수 FedRAMP 청사진을 사용 하 여 FedRAMP 솔루션을 신속 하 게 배포할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-154">Let Microsoft guide you through the ATO process and quickly deploy your FedRAMP solutions with the Azure Security and Compliance FedRAMP blueprint.</span></span> <span data-ttu-id="4f77b-155">이 청사진에서는 참조 아키텍처, 배포 지침, 제어 구현 매핑, ATO 팩터리 지원 등을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-155">Our blueprint gets you started with reference architectures, deployment guidance, control implementation mappings, ATO Factory support, and more.</span></span>

[<span data-ttu-id="4f77b-156">Azure FedRAMP 청사진 사용 시작</span><span class="sxs-lookup"><span data-stu-id="4f77b-156">Start using the Azure FedRAMP Blueprint</span></span>](https://aka.ms/fedrampblueprint)

## <a name="frequently-asked-questions"></a><span data-ttu-id="4f77b-157">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="4f77b-157">Frequently asked questions</span></span>

<span data-ttu-id="4f77b-158">**Microsoft 클라우드 서비스가 FISMA (연방 정보 보안 관리) Act를 준수 하나요?**</span><span class="sxs-lookup"><span data-stu-id="4f77b-158">**Do Microsoft cloud services comply with the Federal Information Security Management Act (FISMA)?**</span></span>

<span data-ttu-id="4f77b-159">FISMA는 미국 연방 기관 및 해당 파트너가 FISMA 요구 사항을 준수 하는 조직에서 정보 시스템 및 서비스를 제공 하는 데 필요한 연방 법률입니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-159">FISMA is a federal law that requires US federal agencies and their partners to procure information systems and services only from organizations that adhere to FISMA requirements.</span></span> <span data-ttu-id="4f77b-160">FISMA와 호환 됨을 나타내는 대부분의 기관 및 공급 업체는 특수 발행물 800-53 rev 4에서 NIST가 식별 한 컨트롤을 충족 하는 방법을 참조 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-160">Most agencies and their vendors that indicate that they are FISMA-compliant are referring to how they meet the controls identified by the NIST in Special Publication 800-53 rev 4.</span></span> <span data-ttu-id="4f77b-161">FISMA 프로세스 (기본 표준은 아님)는 2011에서 FedRAMP로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-161">The FISMA process (but not the underlying standards themselves) was replaced by FedRAMP in 2011.</span></span>

<span data-ttu-id="4f77b-162">**FedRAMP이 적용 되는 사람**</span><span class="sxs-lookup"><span data-stu-id="4f77b-162">**To whom does FedRAMP apply?**</span></span>

<span data-ttu-id="4f77b-163">"FedRAMP은 낮은 및 중간 위험 영향 수준에서 연방 에이전시 클라우드 배포 및 서비스 모델에 필수입니다."</span><span class="sxs-lookup"><span data-stu-id="4f77b-163">“FedRAMP is mandatory for federal agency cloud deployments and service models at the low and moderate risk impact levels.”</span></span> <span data-ttu-id="4f77b-164">CSP에 참여 하려는 모든 연방 에이전시는 FedRAMP 사양을 충족 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-164">Any federal agency that wants to engage a CSP may be required to meet FedRAMP specifications.</span></span> <span data-ttu-id="4f77b-165">또한 연방 정부 기관에서 사용 하는 제품 또는 서비스에서 클라우드 기술을 활용 하는 회사는 ATO을 받아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-165">In addition, companies that employ cloud technologies in products or services used by the federal government may be required to obtain an ATO.</span></span>

<span data-ttu-id="4f77b-166">**에이전시에서 규정 준수 관련 활동을 시작 하는 위치**</span><span class="sxs-lookup"><span data-stu-id="4f77b-166">**Where does my agency start its own compliance effort?**</span></span>

<span data-ttu-id="4f77b-167">FedRAMP을 성공적으로 탐색 하 고 요구 사항을 충족 하기 위해 연방 기관에서 수행 해야 하는 단계에 대 한 개요를 보려면 [www.fedramp.gov/participate/agencies](https://www.fedramp.gov/agency-authorization/)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-167">For an overview of the steps federal agencies must take to successfully navigate FedRAMP and meet its requirements, go to [www.fedramp.gov/participate/agencies](https://www.fedramp.gov/agency-authorization/).</span></span>

<span data-ttu-id="4f77b-168">**에이전시의 인증 프로세스에서 Microsoft 준수를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="4f77b-168">**Can I use Microsoft compliance in my agency’s authorization process?**</span></span>

<span data-ttu-id="4f77b-169">예.</span><span class="sxs-lookup"><span data-stu-id="4f77b-169">Yes.</span></span> <span data-ttu-id="4f77b-170">연방 정부 기관에서 ATO를 필요로 하는 모든 프로그램 또는 이니셔티브의 기반으로 Microsoft 클라우드 서비스의 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-170">You may use the certifications of Microsoft cloud services as the foundation for any program or initiative that requires an ATO from a federal government agency.</span></span> <span data-ttu-id="4f77b-171">그러나 이러한 서비스 외부의 구성 요소에 대 한 사용자의 권한 부여를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-171">However, you need to achieve your own authorizations for components outside these services.</span></span>

## <a name="resources"></a><span data-ttu-id="4f77b-172">리소스</span><span class="sxs-lookup"><span data-stu-id="4f77b-172">Resources</span></span>

- [<span data-ttu-id="4f77b-173">연방 위험 및 권한 부여 관리 프로그램</span><span class="sxs-lookup"><span data-stu-id="4f77b-173">Federal Risk and Authorization Management Program</span></span>](https://www.fedramp.gov/)
- [<span data-ttu-id="4f77b-174">Microsoft 공통 컨트롤 허브 규정 준수 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="4f77b-174">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="4f77b-175">Microsoft Government 클라우드</span><span class="sxs-lookup"><span data-stu-id="4f77b-175">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="4f77b-176">FedRAMP 보안 평가 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="4f77b-176">FedRAMP Security Assessment Framework</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2099507)
- [<span data-ttu-id="4f77b-177">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="4f77b-177">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="4f77b-178">제공 사항의 배경 설명 다운로드</span><span class="sxs-lookup"><span data-stu-id="4f77b-178">Download the offering backgrounder</span></span>

<span data-ttu-id="4f77b-179">이 제공 사항에 대한 배경 설명 문서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="4f77b-179">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="4f77b-180">[PDF](https://download.microsoft.com/download/6/B/7/6B7B25B8-D44F-439A-80A9-1ED04C88B922/FedRAMP_backgrounder-2018.pdf)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4f77b-180">Download the [PDF](https://download.microsoft.com/download/6/B/7/6B7B25B8-D44F-439A-80A9-1ED04C88B922/FedRAMP_backgrounder-2018.pdf).</span></span>
