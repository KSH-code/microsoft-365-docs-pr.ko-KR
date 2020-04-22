---
title: 형사법 (CJIS) 보안 정책
description: Microsoft 정부 클라우드 서비스는 미국 범죄를 대상으로 하는 정보 서비스 보안 정책을 따릅니다.
keywords: Microsoft 365, 규정 준수, 제안
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
ms.openlocfilehash: 4ef19b106d5b00bb8b436b56b6da8bb653873f3a
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583325"
---
# <a name="criminal-justice-information-services-cjis-security-policy"></a><span data-ttu-id="d9db2-104">형사법 (CJIS) 보안 정책</span><span class="sxs-lookup"><span data-stu-id="d9db2-104">Criminal Justice Information Services (CJIS) Security Policy</span></span>

## <a name="cjis-overview"></a><span data-ttu-id="d9db2-105">CJIS 개요</span><span class="sxs-lookup"><span data-stu-id="d9db2-105">CJIS overview</span></span>

<span data-ttu-id="d9db2-106">FBI의 미국 연방 (정부 정보 서비스) 디비전은 상태, 로컬 및 연방 법 집행 및 범죄 조사 (CJI) (예: 지문 기록 및 형사법 기록)에 대 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-106">The Criminal Justice Information Services (CJIS) Division of the US Federal Bureau of Investigation (FBI) gives state, local, and federal law enforcement and criminal justice agencies access to criminal justice information (CJI) — for example, fingerprint records and criminal histories.</span></span> <span data-ttu-id="d9db2-107">법 집행 및 기타 정부 기관은 미국의 전송, 저장 또는 처리에 클라우드 서비스를 사용 하 여 CJI의 보안 요구 사항 및 제어를 최소화 하는 [Cjis 보안 정책을](https://aka.ms/cjis-security-policy)준수 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-107">Law enforcement and other government agencies in the United States must ensure that their use of cloud services for the transmission, storage, or processing of CJI complies with the [CJIS Security Policy](https://aka.ms/cjis-security-policy), which establishes minimum security requirements and controls to safeguard CJI.</span></span>

<span data-ttu-id="d9db2-108">CJIS 보안 정책은 presidential 및 FBI 가이드, 연방 법규 및 범죄 정책 보드 의사 결정을 통합 하 고 NIST (표준 및 기술)의 지침과 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-108">The CJIS Security Policy integrates presidential and FBI directives, federal laws, and the criminal justice community’s Advisory Policy Board decisions, along with guidance from the National Institute of Standards and Technology (NIST).</span></span> <span data-ttu-id="d9db2-109">진화 하는 보안 요구 사항을 반영 하도록 정책이 주기적으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-109">The Policy is periodically updated to reflect evolving security requirements.</span></span>

<span data-ttu-id="d9db2-110">CJIS 보안 정책은 클라우드 서비스 공급자와 같은 개인 계약자가 평가 하 여 클라우드 서비스 사용이 CJIS 요구 사항과 일치 하는지 확인 하는 데 사용할 수 있는 13 개의 영역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-110">The CJIS Security Policy defines 13 areas that private contractors such as cloud service providers must evaluate to determine if their use of cloud services can be consistent with CJIS requirements.</span></span> <span data-ttu-id="d9db2-111">이러한 영역은 Microsoft가 정부 클라우드 제품에 대 한 인증을 받은 프로그램[FedRAMP](offering-FedRAMP.md)(연방 위험 및 권한 부여 관리 프로그램)에 대 한 기초 이기도 한 NIST 800-53에 밀접 하 게 대응 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-111">These areas correspond closely to NIST 800-53, which is also the basis for the Federal Risk and Authorization Management Program ([FedRAMP](offering-FedRAMP.md)), a program under which Microsoft has been certified for its Government Cloud offerings.</span></span>

<span data-ttu-id="d9db2-112">또한 CJI를 처리 하는 모든 개인 수급 업체가 보안 정책에 필요한 CJI의 보안 및 기밀성을 보장 하는 데 도움이 되는, 미국 변호사에 게 승인 하는 통일 된 계약을 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-112">In addition, all private contractors who process CJI must sign the CJIS Security Addendum, a uniform agreement approved by the US Attorney General that helps ensure the security and confidentiality of CJI required by the Security Policy.</span></span> <span data-ttu-id="d9db2-113">또한 계약자가 연방 및 지방 법, 규정 및 표준과 일치 하는 보안 프로그램을 유지 관리 하 고 CJI 사용을 정부 기관에서 제공 하는 목적으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-113">It also commits the contractor to maintaining a security program consistent with federal and state laws, regulations, and standards, and limits the use of CJI to the purposes for which a government agency provided it.</span></span>

## <a name="microsoft-and-cjis-security-policy"></a><span data-ttu-id="d9db2-114">Microsoft 및 CJIS 보안 정책</span><span class="sxs-lookup"><span data-stu-id="d9db2-114">Microsoft and CJIS Security Policy</span></span>

<span data-ttu-id="d9db2-115">Microsoft는 CJIS 정보 계약을 사용 하 여 상태에 있는 CJIS 보안 추 록에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-115">Microsoft signs the CJIS Security Addendum in states with CJIS Information Agreements.</span></span> <span data-ttu-id="d9db2-116">이러한 규정은 CJIS 보안 정책 준수를 담당 하는 상태 법 집행 기관 Microsoft의 클라우드 보안 컨트롤을 사용 하 여 데이터의 전체 수명 주기를 보호 하 고 CJI에 대 한 액세스 권한이 있는 운영 인력이 적절 한 백그라운드에 있는지 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="d9db2-116">These tell state law enforcement authorities responsible for compliance with CJIS Security Policy how Microsoft's cloud security controls help protect the full lifecycle of data and ensure appropriate background screening of operating personnel with access to CJI.</span></span> <span data-ttu-id="d9db2-117">Microsoft는 계속 해 서 상태 정부를 사용 하 여 CJIS 정보 계약에 진입 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-117">Microsoft continues to work with state governments to enter into CJIS Information Agreements.</span></span>

<span data-ttu-id="d9db2-118">Microsoft는 microsoft Azure 정부, Microsoft Office 365 미국 정부 및 Microsoft Dynamics 365 U.S. 정부의 운영 정책 및 절차를 평가 했으며, 해당 서비스 계약에서 사용 범위 서비스를 사용할 때의 FBI 요구 사항을 충족 하는 기능을 보증 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-118">Microsoft has assessed the operational policies and procedures of Microsoft Azure Government, Microsoft Office 365 U.S. Government, and Microsoft Dynamics 365 U.S. Government, and will attest to their ability in the applicable services agreements to meet FBI requirements for the use of in-scope services.</span></span>

<span data-ttu-id="d9db2-119">Microsoft 클라우드의 CJIS 보안 정책 혜택에 대해 자세히 알아보세요: [Genetec에서 범죄 조사를 지운 방법 읽기](https://customers.microsoft.com/story/genetec)</span><span class="sxs-lookup"><span data-stu-id="d9db2-119">Learn about the benefits of CJIS Security policy on the Microsoft Cloud: [Read how Genetec cleared criminal investigations](https://customers.microsoft.com/story/genetec)</span></span>

<span data-ttu-id="d9db2-120">Azure 보안 및 준수 청사진을 사용 하 여 CJIS 보안 정책을 가속화 하는 방법을 알아봅니다. [Microsoft 정부 클라우드 서비스에 대 한 cjis 구현 지침 다운로드](https://gallery.technet.microsoft.com/CJIS-Implementation-62af7c27)</span><span class="sxs-lookup"><span data-stu-id="d9db2-120">Learn how to accelerate your CJIS Security policy with our Azure Security and Compliance Blueprint: [Download the CJIS implementation guidelines for Microsoft Government Cloud Services](https://gallery.technet.microsoft.com/CJIS-Implementation-62af7c27)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="d9db2-121">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="d9db2-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="d9db2-122">Azure 정부</span><span class="sxs-lookup"><span data-stu-id="d9db2-122">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="d9db2-123">Dynamics 365 미국 정부</span><span class="sxs-lookup"><span data-stu-id="d9db2-123">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- [<span data-ttu-id="d9db2-124">Office 365 미국 정부</span><span class="sxs-lookup"><span data-stu-id="d9db2-124">Office 365 U.S. Government</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="d9db2-125">독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="d9db2-125">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="d9db2-126">감사, 보고서 및 인증서</span><span class="sxs-lookup"><span data-stu-id="d9db2-126">Audits, reports, and certificates</span></span>

<span data-ttu-id="d9db2-127">FBI에서는 CJIS 요구 사항을 준수 하는 Microsoft의 인증을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-127">The FBI does not offer certification of Microsoft compliance with CJIS requirements.</span></span> <span data-ttu-id="d9db2-128">대신 microsoft와 microsoft와의 CJIS 기관 간의 계약에 microsoft와 해당 고객 간의 계약이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-128">Instead, a Microsoft attestation is included in agreements between Microsoft and a state’s CJIS authority, and between Microsoft and its customers.</span></span>

[<span data-ttu-id="d9db2-129">Microsoft CJIS 클라우드 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9db2-129">Microsoft CJIS Cloud Requirements</span></span>](https://aka.ms/MicrosoftCJISCloudRequirements)

## <a name="cjis-status-in-the-united-states-current-as-of-9232019"></a><span data-ttu-id="d9db2-130">미국 (현재 상태는 9/23/2019) 인 CJIS 상태</span><span class="sxs-lookup"><span data-stu-id="d9db2-130">CJIS status in the United States (current as of 9/23/2019)</span></span>

<span data-ttu-id="d9db2-131">37: 관리 계약을 포함 한 콜롬비아의 학구 및 해당 지역에 녹색으로 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-131">37 states and the District of Columbia with management agreements, highlighted on the map in green include:</span></span>

<span data-ttu-id="d9db2-132">앨라배마, 알래스카, Arkansas, 애리조나, 캘리포니아, Colorado, Florida, 그루지야, 하와이, Illinois, 인디애나, Iowa, Kansas, 켄터키, Maine, Massachusetts, Michigan, Minnesota, Missouri, Montana,, Jersey,,, Nevada, Carolina, Oregon, Pennsylvania,, Rhode,,,, Carolina,, Tennessee,</span><span class="sxs-lookup"><span data-stu-id="d9db2-132">Alabama, Alaska, Arkansas, Arizona, California, Colorado, Florida, Georgia, Hawaii, Illinois, Indiana, Iowa, Kansas, Kentucky, Maine, Massachusetts, Michigan, Minnesota, Missouri, Montana, New Jersey, New York, Nevada, North Carolina, Oklahoma, Oregon, Pennsylvania, Rhode Island, South Carolina, Tennessee, Texas, Utah, Vermont, Virginia, Washington, Washington D.C., West Virginia, Wisconsin.</span></span>

<span data-ttu-id="d9db2-133">해당 하는 CJIS 규정 제어를 충족 하기 위해 Microsoft는 범죄자가 클라우드 기반 솔루션을 구현 하 고 CJIS 보안 정책 V 5.8을 준수할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-133">Microsoft's commitment to meeting the applicable CJIS regulatory controls allows Criminal Justice organizations to implement cloud-based solutions and be compliant with CJIS Security Policy V5.8.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d9db2-134">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="d9db2-134">Frequently asked questions</span></span>

<span data-ttu-id="d9db2-135">**준수 정보를 요청 하는 위치**</span><span class="sxs-lookup"><span data-stu-id="d9db2-135">**Where can I request compliance information?**</span></span>

<span data-ttu-id="d9db2-136">관심 있는 관할지에 대 한 자세한 내용은 Microsoft 계정 담당자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9db2-136">Contact your Microsoft account representative for information on the jurisdiction you are interested in.</span></span> <span data-ttu-id="d9db2-137">현재 <cjis@microsoft.com> 어떤 상태에서 사용 가능한 서비스에 대 한 정보를 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-137">Contact <cjis@microsoft.com> for information on which services are currently available in which states.</span></span>

<span data-ttu-id="d9db2-138">**Microsoft는 클라우드 서비스가 내 상태 요구 사항을 준수 하도록 설정 하 고 있음을 어떻게 확인 하나요?**</span><span class="sxs-lookup"><span data-stu-id="d9db2-138">**How does Microsoft demonstrate that its cloud services enable compliance with my state’s requirements?**</span></span>

<span data-ttu-id="d9db2-139">Microsoft는 CSA (CJIS Systems 에이전시)를 사용 하 여 정보 계약에 서명 합니다. state의 CSA에서 복사본을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-139">Microsoft signs an Information Agreement with a state CJIS Systems Agency (CSA); you may request a copy from your state’s CSA.</span></span> <span data-ttu-id="d9db2-140">또한 Microsoft는 고객에 게 심층 보안, 개인 정보 보호 및 준수 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-140">In addition, Microsoft provides customers with in-depth security, privacy, and compliance information.</span></span> <span data-ttu-id="d9db2-141">고객은 또한 관련 감사 범위에 적합 한 보안 제어 (예: ISO 27001)를 구현 했는지 확인할 수 있도록 독립 감사자를 통해 준비 된 보안 및 준수 보고서를 검토 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-141">Customers may also review security and compliance reports prepared by independent auditors so they can validate that Microsoft has implemented security controls (such as ISO 27001) appropriate to the relevant audit scope.</span></span>

<span data-ttu-id="d9db2-142">**에이전시의 규정 준수 관련 활동은 어디에서 시작 하나요?**</span><span class="sxs-lookup"><span data-stu-id="d9db2-142">**Where do I start with my agency’s compliance effort?**</span></span>

<span data-ttu-id="d9db2-143">[Cjis 보안 정책은](https://aka.ms/cjis-security-policy) CJI을 보호 하기 위해 에이전시에서 수행 해야 하는 예방 조치를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-143">[CJIS Security Policy](https://aka.ms/cjis-security-policy) covers the precautions that your agency must take to protect CJI.</span></span> <span data-ttu-id="d9db2-144">또한 Microsoft 계정 담당자는 관할지 요구 사항에 익숙한 사용자에 게 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9db2-144">In addition, your Microsoft account representative can put you in touch with those familiar with the requirements of your jurisdiction</span></span>

## <a name="resources"></a><span data-ttu-id="d9db2-145">리소스</span><span class="sxs-lookup"><span data-stu-id="d9db2-145">Resources</span></span>

- [<span data-ttu-id="d9db2-146">형사법 정보 서비스</span><span class="sxs-lookup"><span data-stu-id="d9db2-146">Criminal Justice Information Services</span></span>](https://aka.ms/cjis)
- [<span data-ttu-id="d9db2-147">CJIS 보안 정책</span><span class="sxs-lookup"><span data-stu-id="d9db2-147">CJIS Security Policy</span></span>](https://aka.ms/cjis-security-policy)
- [<span data-ttu-id="d9db2-148">CJIS 보안 정책 버전 5.3 backgrounder</span><span class="sxs-lookup"><span data-stu-id="d9db2-148">CJIS security policy version 5.3 backgrounder</span></span>](https://aka.ms/cjis-backgrounder)
- [<span data-ttu-id="d9db2-149">Azure 정부에 대 한 CJIS 구현 지침</span><span class="sxs-lookup"><span data-stu-id="d9db2-149">CJIS implementation guidelines for Azure Government</span></span>](https://aka.ms/cjisimplementationguidelines)
- [<span data-ttu-id="d9db2-150">Microsoft 공통 컨트롤 허브 규정 준수 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="d9db2-150">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="d9db2-151">Microsoft Government 클라우드</span><span class="sxs-lookup"><span data-stu-id="d9db2-151">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/?linkid=2087246)
- [<span data-ttu-id="d9db2-152">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="d9db2-152">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
