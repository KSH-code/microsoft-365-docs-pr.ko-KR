---
title: 데이터 보호 영향 평가
description: 이 문서는 정보와 데이터 컨트롤러를 제공하여 DPIA 필요 여부, 필요한 경우 포함할 세부 사항을 결정할 수 있도록 지원합니다.
keywords: 데이터 보호 영향 평가, DPIA, Dynamics 365, Microsoft Professional Services, Microsoft 365, Microsoft 365 설명서, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: cc633dc261594607a87e7aae7da03e0a427a2492
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594418"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a><span data-ttu-id="8e000-104">GDPR에 대한 데이터 보호 영향 평가</span><span class="sxs-lookup"><span data-stu-id="8e000-104">Data Protection Impact Assessment for the GDPR</span></span>

<span data-ttu-id="8e000-105">GDPR(일반 데이터 보호 규제)는 EU(유럽 연합) 회원국 국민에게 제품과 서비스를 제공하거나 귀하 또는 귀사가 어디에 있는지 관계없이 EU 거주자의 데이터를 수집하고 분석하는 조직에 새로운 규칙을 도입합니다. </span><span class="sxs-lookup"><span data-stu-id="8e000-105">The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located.</span></span> <span data-ttu-id="8e000-106">추가 세부 정보는 [GDPR 요약 항목](gdpr.md)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-106">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrOQE] 

<span data-ttu-id="8e000-107">이 문서에서는 Microsoft 제품 및 서비스를 사용하는 경우 GDPR 하의 DPIAs(데이터 보호 영향 평가)에 대한 정보를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-107">This document guides you to information regarding Data Protection Impact Assessments (DPIAs) under the GDPR when using Microsoft products and services.</span></span>

## <a name="terminology"></a><span data-ttu-id="8e000-108">용어</span><span class="sxs-lookup"><span data-stu-id="8e000-108">Terminology</span></span>

<span data-ttu-id="8e000-109">이 문서에서 사용된 GDPR 용어에 대한 유용한 정의:</span><span class="sxs-lookup"><span data-stu-id="8e000-109">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="8e000-110">*데이터 컨트롤러(컨트롤러)*: 개인 데이터 처리의 목적과 수단을 결정하는 법인, 공공 기관, 에이전시 또는 다른 사람과 독립적으로 또는 공동으로 작업하는 기타 단체입니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-110">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="8e000-111">*개인 데이터* 및 *데이터 주체*: 식별되거나 식별 가능한 자연인(데이터 주체)과 관련된 모든 정보. 식별 가능한 자연인은 직접 또는 간접적으로 식별될 수 있는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-111">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="8e000-112">*프로세서*: 컨트롤러를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 에이전시 또는 기타 단체입니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-112">*Processor*: A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="8e000-113">*고객 데이터*: 비즈니스 운영의 일상적인 작업에서 생성되고 저장되는 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-113">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dpia"></a><span data-ttu-id="8e000-114">DPIA란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8e000-114">What is a DPIA?</span></span>

<span data-ttu-id="8e000-115">GDPR은 "자연인의 권리와 자유에 대한 높은 위험을 초래할 가능성이 있는" 작업에 대해 컨트롤러가 DPIA(데이터 보호 영향 평가)를 준비하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-115">The GDPR requires controllers to prepare a Data Protection Impact Assessment (DPIA) for operations that are “likely to result in a high risk to the rights and freedoms of natural persons.”</span></span> <span data-ttu-id="8e000-116">DPIA를 만들어야 하는 Microsoft 제품 및 서비스에는 아무것도 내제되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-116">There is nothing inherent in Microsoft products and services that need the creation of a DPIA.</span></span> <span data-ttu-id="8e000-117">그러나 Microsoft 제품 및 서비스는 사용자 지정할 수 있기 때문에 Microsoft 구성의 세부 사항에 따라 DPIA가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-117">However, because Microsoft products and services are highly customizable, a DPIA may be needed depending on the details of your Microsoft configuration.</span></span> <span data-ttu-id="8e000-118">Microsoft는 그러한 정보에 대한 통제권이 없으며 그러한 정보에 대한 인사이트를 거의 또는 전혀 가지고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-118">Microsoft has no control over, and little or no insight into such information.</span></span> <span data-ttu-id="8e000-119">사용자는 데이터 컨트롤러로서 데이터의 적절한 사용을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-119">You, as a data controller must determine appropriate uses of their data.</span></span>

## <a name="dpia-in-action"></a><span data-ttu-id="8e000-120">DPIA 실행</span><span class="sxs-lookup"><span data-stu-id="8e000-120">DPIA in Action</span></span>

<span data-ttu-id="8e000-121">DPIA 지침은 Office 365, Azure, Dynamics 365 및 Microsoft 지원 및 전문 서비스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-121">The DPIA guidance applies to Office 365, Azure, Dynamics 365, and Microsoft Support and Professional Services.</span></span> <span data-ttu-id="8e000-122">해당 지침에는 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-122">That guidance includes consideration of:</span></span>

1. <span data-ttu-id="8e000-123">**DPIA는 언제 필요 한가요?**: DPIA 완료 여부를 고려할 때 아래에 열거된 위험 요소를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-123">**When is a DPIA needed?**: The risk factors listed below should be addressed when considering whether to complete a DPIA.</span></span> <span data-ttu-id="8e000-124">그 밖의 잠재적인 요소 및 기타 세부 정보는 각 가이드의 1부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-124">Other potential factors and further details are found in Part 1 of each of the guidelines.</span></span>  

    - <span data-ttu-id="8e000-125">자동화된 프로세스를 기반으로하는 체계적이고 광범위한 데이터 평가.</span><span class="sxs-lookup"><span data-stu-id="8e000-125">A systematic and extensive evaluation of data based on automated processing.</span></span>  
    - <span data-ttu-id="8e000-126">다양한 특정 범주의 데이터(자연인을 고유하게 식별하는 정보를 나타내는 데이터) 또는 범죄 전과 및 위법 행위와 관련된 개인 데이터 대규모 처리.</span><span class="sxs-lookup"><span data-stu-id="8e000-126">Processing on a large scale of special categories of data (data revealing information uniquely identifying a natural person), or of personal data relating to criminal convictions and offenses.</span></span>
    - <span data-ttu-id="8e000-127">공개적으로 액세스할 수 있는 영역을 대규모로 체계적으로 모니터링.</span><span class="sxs-lookup"><span data-stu-id="8e000-127">Systematic monitoring of a publicly accessible area on a large scale.</span></span>

    <span data-ttu-id="8e000-128">GDPR에서는 다음을 명확하게 제시합니다. “처리 작업에서 개인 담당 의사, 다른 의료 전문가 또는 법률가가 환자 또는 클라이언트의 개인 데이터를 우려할 경우 개인 데이터 처리는 대규모로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-128">The GDPR clarifies “The processing of personal data should not be considered to be on a large scale if the processing concerns personal data from patients or clients by an individual physician, other health care professional, or lawyer.</span></span> <span data-ttu-id="8e000-129">그러한 경우 데이터 보호 영향 평가는 필수 사항이 아닙니다.”</span><span class="sxs-lookup"><span data-stu-id="8e000-129">In such cases, a data protection impact assessment should not be mandatory.”</span></span>

2. <span data-ttu-id="8e000-130">**DPIA를 완료하는 데 필요한 것은 무엇인가요?**: DPIA는 의도된 프로세스에 대한 특정 정보를 제공해야 합니다. 이는 가이드 2부에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-130">**What is required to complete a DPIA?**: A DPIA should provide specific information about the intended processing, which is detailed in Part 2 of the guidance.</span></span> <span data-ttu-id="8e000-131">해당 정보에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-131">That information includes:</span></span>

    - <span data-ttu-id="8e000-132">DPIA의 목적과 관련한 데이터 처리의 필요성 및 비례의 원칙 평가</span><span class="sxs-lookup"><span data-stu-id="8e000-132">Assessment of the necessity, and proportionality of data processing in relation to the purpose of the DPIA.</span></span>  
    - <span data-ttu-id="8e000-133">자연인의 권리와 자유에 대한 위험 평가;</span><span class="sxs-lookup"><span data-stu-id="8e000-133">Assessment of the risks to the rights and freedoms of natural persons.</span></span>
    - <span data-ttu-id="8e000-134">안전 조치, 보안 조치 및 개인 정보 보호를 보장하고 GDPR 준수를 입증하는 메커니즘을 포함하여 위험을 해결하기 위한 의도된 조치.</span><span class="sxs-lookup"><span data-stu-id="8e000-134">Intended measures to address the risks, including safeguards, security measures, and mechanisms to ensure the protection of personal data and demonstrate compliance with the GDPR.</span></span>
    - <span data-ttu-id="8e000-135">처리 목적</span><span class="sxs-lookup"><span data-stu-id="8e000-135">Purposes of processing</span></span>  
    - <span data-ttu-id="8e000-136">처리된 개인 데이터의 범주</span><span class="sxs-lookup"><span data-stu-id="8e000-136">Categories of personal data processed</span></span>  
    - <span data-ttu-id="8e000-137">데이터 보존</span><span class="sxs-lookup"><span data-stu-id="8e000-137">Data retention</span></span>  
    - <span data-ttu-id="8e000-138">개인 데이터의 위치 및 전송</span><span class="sxs-lookup"><span data-stu-id="8e000-138">Location and transfers of personal data</span></span>  
    - <span data-ttu-id="8e000-139">타사 하위 프로세서와 데이터 공유</span><span class="sxs-lookup"><span data-stu-id="8e000-139">Data sharing with third-party subprocessors</span></span>  
    - <span data-ttu-id="8e000-140">독립 타사와 데이터 공유</span><span class="sxs-lookup"><span data-stu-id="8e000-140">Data sharing with independent third-parties</span></span>  
    - <span data-ttu-id="8e000-141">데이터 주체 권리</span><span class="sxs-lookup"><span data-stu-id="8e000-141">Data subject rights</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="8e000-142">추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8e000-142">Additional Considerations</span></span>

<span data-ttu-id="8e000-143">Microsoft 구현에 관련된 구체적인 세부 정보는 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-143">Specific details that may be relevant to your Microsoft implementation are below.</span></span>

- <span data-ttu-id="8e000-144">[Office 365](gdpr-dpia-office365.md):이 문서는 Exchange Online, SharePoint online, Yammer, 비즈니스용 Skype, Power BI를 비롯하여 Office 365 응용 프로그램 및 서비스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-144">[Office 365](gdpr-dpia-office365.md): This document applies to Office 365 applications and services, including but not limited to Exchange Online, SharePoint Online, Yammer, Skype for Business, and Power BI.</span></span> <span data-ttu-id="8e000-145">자세한 내용은 표 [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) 및 [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e000-145">Refer to Tables [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) and [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) for more details.</span></span>  
- <span data-ttu-id="8e000-146">[Azure](gdpr-dpia-azure.md): 고객은 개인 정보 책임자와 관리 담당자 및 법적 자문과 함께 Microsoft Azure 사용과 관련된 DPIA의 필요 여부 및 내용을 결정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-146">[Azure](gdpr-dpia-azure.md): Customers are encouraged to work with their privacy officers and legal counsel to determine the necessity and content of any DPIAs related to their use of Microsoft Azure.</span></span>  
- <span data-ttu-id="8e000-147">[Dynamics 365](gdpr-dpia-dynamics.md): DPIA의 내용은 사용하고 있는 Dynamics 365 도구에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-147">[Dynamics 365](gdpr-dpia-dynamics.md): The contents of a DPIA may vary according to which Dynamics 365 tools you are employing.</span></span> <span data-ttu-id="8e000-148">자세한 내용은 [2부 DPIA의 내용](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e000-148">For specific details refer to [Part 2 Contents of a DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia).</span></span>
- <span data-ttu-id="8e000-149">[Microsoft 지원 및 전문 서비스](gdpr-dpia-prof-services.md): 전문 서비스는 특정 루틴이나 자동화된 데이터 처리를 수행하지 않으며 특수 범주를 처리하거나 공개적으로 액세스할 수 있는 데이터를 모니터링하거나 필요로 하는 작업을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-149">[Microsoft Support and Professional Services](gdpr-dpia-prof-services.md): Professional Services does not conduct certain routine or automated data processing, nor is it intended to process special categories or perform tasks that facilitate or require monitoring of publicly accessible data.</span></span> <span data-ttu-id="8e000-150">자세한 내용은 [1부 — DPIA 필요 여부 결정](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e000-150">For details see [Part 1 — Determining Whether a DPIA is needed](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed).</span></span> <span data-ttu-id="8e000-151">컨트롤러는 컨트롤러의 특정 구현 및 전문 서비스 사용과 관련하여 위에서 설명한 DPIA 요소를 다른 관련 요소와 함께 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e000-151">Controllers must consider the DPIA elements outlined above, along with any other relevant factors, in the context of the controller’s specific implementations and uses of Professional Services.</span></span> <span data-ttu-id="8e000-152">전문 서비스에 대한 자세한 내용은 [2부 — DPIA의 내용](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e000-152">For Professional Services information, see [Part 2 — Contents of a DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia).</span></span>

## <a name="learn-more"></a><span data-ttu-id="8e000-153">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="8e000-153">Learn more</span></span>

- [<span data-ttu-id="8e000-154">Microsoft 보안 센터</span><span class="sxs-lookup"><span data-stu-id="8e000-154">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
