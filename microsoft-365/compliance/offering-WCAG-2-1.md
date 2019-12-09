---
title: 웹 콘텐츠 접근성 지침 2.1
description: Microsoft는 전체 제품 또는 서비스 혹은 별도로 설치될 수 있는 제품의 일부를 반영하는 WCAG 2.1 AA 보고서를 게시합니다.
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
ms.openlocfilehash: a1887bd2b6c04836ebb11d224fcc59debcd88e55
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859448"
---
# <a name="web-content-accessibility-guidelines-21"></a><span data-ttu-id="312e3-104">웹 콘텐츠 접근성 지침 2.1</span><span class="sxs-lookup"><span data-stu-id="312e3-104">Web Content Accessibility Guidelines 2.1</span></span>

## <a name="about-wcag-21"></a><span data-ttu-id="312e3-105">WCAG 2.1에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="312e3-105">About WCAG 2.1</span></span>

<span data-ttu-id="312e3-106">WCAG 2.1은 그래픽 기능이 제한된 장치의 사용자 외에도 장애가 있는 사용자에 대한 접근성을 향상시키는 웹 콘텐츠를 개발하기 위한 프레임워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-106">WCAG 2.1 provides a framework for developing web content that improves accessibility for people with disabilities, in addition to users of devices with limited graphical abilities.</span></span> <span data-ttu-id="312e3-107">WCAG 2.0는 웹 표준을 만드는데 전념하는 월드 와이드 웹 컨소시엄(W3C)이 2008년 발행했으며 2018년 6월에 WCAG 2.1로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-107">WCAG 2.0 was published in 2008 by the World Wide Web Consortium (W3C), an international organization dedicated to creating web standards, and updated to WCAG 2.1 in June 2018.</span></span> <span data-ttu-id="312e3-108">2012년 WCAG 2.0은 또한 국제 표준화 기구(ISO)가 ISO/IEC 40500:2012로 발행하였습니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-108">In 2012, WCAG 2.0 was also published by the International Organization for Standardization (ISO) as ISO/IEC 40500:2012.</span></span>  
  
<span data-ttu-id="312e3-109">WCAG 2.1를 준수하는 콘텐츠 역시 WCAG 2.0를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-109">Content that conforms to WCAG 2.1 also conforms to WCAG 2.0.</span></span> <span data-ttu-id="312e3-110">WCAG 2.0의 준수를 필요로 하는 정책에 WCAG 2.1은 대체적 준수 방법을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-110">For policies requiring conformance to WCAG 2.0, WCAG 2.1 can provide an alternate means of conformance.</span></span>  
  
<span data-ttu-id="312e3-111">각 지침에 대한 준수의 요구 사항은 세 가지 레벨(A, AA 및 AAA)로 측정됩니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-111">Conformance requirements for each guideline are measured in three levels: A, AA, and AAA.</span></span> <span data-ttu-id="312e3-112">Microsoft는 전세계의 주와 정부에 주요 소프트웨어 및 클라우드 서비스를 공급하는 업체이기에, 모든 관련 [국제 표준과 규정 준수 컨트롤](https://go.microsoft.com/fwlink/p/?linkid=2052226)을 준수하기 위해 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-112">Because Microsoft is a major software and cloud-services provider to states and governments around the world, it is committed to complying with all relevant [international standards and compliance controls](https://go.microsoft.com/fwlink/p/?linkid=2052226).</span></span> <span data-ttu-id="312e3-113">Microsoft는 이러한 광범위한 접근성 표준을 준수하여 정부 내부 및 외부의 모든 고객이 Microsoft 서비스와 제품을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-113">By adhering to these wide-ranging accessibility standards, Microsoft ensures that all customers — both inside and outside of government — can use Microsoft services and products.</span></span>  

## <a name="microsoft-and-wcag-21"></a><span data-ttu-id="312e3-114">Microsoft 및 WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="312e3-114">Microsoft and WCAG 2.1</span></span>

<span data-ttu-id="312e3-115">Microsoft의 WCAG 2.1(ISO/IEC 40500) 표준의 준수는 모든 고객이 기술과 데이터에 액세스할 수 있도록 만들고자 하는 노력을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-115">Microsoft’s adherence to the WCAG 2.1 (ISO/IEC 40500) standard points to its commitment to making technology and data accessible for all customers.</span></span> <span data-ttu-id="312e3-116">WCAG 2.1(ISO/IEC 40500)는 ENr 301 549(유럽) 및 섹션 508(미국)을 보완하는 국제적 접근성 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-116">WCAG 2.1 (ISO/IEC 40500) is the international accessibility requirement that complements EN 301 549 (Europe) and Section 508 (U.S.).</span></span>  
  
<span data-ttu-id="312e3-117">Microsoft는 전체 제품 또는 서비스를 반영하는 WCAG 2.1 보고서를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-117">Microsoft publishes WCAG 2.1 reports that reflect the complete product or service.</span></span> <span data-ttu-id="312e3-118">Microsoft는 일반적으로 개별 기능이나 구성 요소에 대한 보고서를 작성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-118">It generally does not create reports for individual features or components.</span></span> <span data-ttu-id="312e3-119">간혹 Microsoft는 사용자가 별도로 설치하도록 선택할 수 있는 기존 제품에 대한 새로운 구성 요소나 기존 구성 요소의 새로운 버전을 릴리스할 수도 있으며 해당 구성 요소에 대한 WCAG 2.1 보고서를 게시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-119">Sometimes, Microsoft might release a new component for an existing product, or a new version of an existing component, which users can choose to install separately, and Microsoft might also publish a WCAG 2.1 report for that component.</span></span>  
  
[<span data-ttu-id="312e3-120">WCAG 2.1(ISO/IEC 40500) 접근성 표준 다운로드</span><span class="sxs-lookup"><span data-stu-id="312e3-120">Download the WCAG 2.1 (ISO/IEC 40500) accessibility standards</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2052226)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="312e3-121">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="312e3-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="312e3-122">Azure 및 Azure Government</span><span class="sxs-lookup"><span data-stu-id="312e3-122">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="312e3-123">Azure DevOps 서비스</span><span class="sxs-lookup"><span data-stu-id="312e3-123">Azure DevOps Services</span></span>
- <span data-ttu-id="312e3-124">Dynamics 365 및 Dynamics 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="312e3-124">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="312e3-125">Intune</span><span class="sxs-lookup"><span data-stu-id="312e3-125">Intune</span></span>
- <span data-ttu-id="312e3-126">Office 365 및 Office 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="312e3-126">Office 365 and Office 365 U.S. Government</span></span>
- <span data-ttu-id="312e3-127">Office 365 US Government Defense</span><span class="sxs-lookup"><span data-stu-id="312e3-127">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="312e3-128">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="312e3-128">Windows Server 2016</span></span>

## <a name="microsoft-accessibility-conformance-reports"></a><span data-ttu-id="312e3-129">Microsft 접근성 적합성 보고서</span><span class="sxs-lookup"><span data-stu-id="312e3-129">Microsoft accessibility conformance reports</span></span>

<span data-ttu-id="312e3-130">모든 제품 및 서비스에 대한 WCAG 보고서를 찾아보세요.</span><span class="sxs-lookup"><span data-stu-id="312e3-130">Find WCAG reports for all our products and services.</span></span>

[<span data-ttu-id="312e3-131">**자세한 정보**</span><span class="sxs-lookup"><span data-stu-id="312e3-131">**Learn more**</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050974)

## <a name="resources"></a><span data-ttu-id="312e3-132">리소스</span><span class="sxs-lookup"><span data-stu-id="312e3-132">Resources</span></span>

<span data-ttu-id="312e3-133">[Microsoft 접근성 사이트: 접근성 기능 사용에 대한 정보를 얻고 모든 사람이 더 많은 것을 달성할 수 있도록 돕기 위해 Microsoft가 혁신하는 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-133">[Microsoft accessibility site — Get information on using accessibility features and explore the ways Microsoft innovates to help everyone achieve more.</span></span>

[<span data-ttu-id="312e3-134">Office 365 접근성 센터</span><span class="sxs-lookup"><span data-stu-id="312e3-134">Office 365 Accessibility Center</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051801)
    - <span data-ttu-id="312e3-135">장애가 있는 사용자를 위한 Office 365 리소스.</span><span class="sxs-lookup"><span data-stu-id="312e3-135">Office 365 resources for people with disabilities.</span></span>

[<span data-ttu-id="312e3-136">Enterprise Disability Answer Desk</span><span class="sxs-lookup"><span data-stu-id="312e3-136">Enterprise Disability Answer Desk</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050890)
    - <span data-ttu-id="312e3-137">제품 및 서비스 또는 규정 준수에 대한 접근성과 관련된 질문이 있는 엔터프라이즈 고객을 위한 전용 지원</span><span class="sxs-lookup"><span data-stu-id="312e3-137">Dedicated support for enterprise customers with accessibility questions about our products and services or compliance.</span></span>

[<span data-ttu-id="312e3-138">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="312e3-138">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="312e3-139">제공 사항의 배경 설명 다운로드</span><span class="sxs-lookup"><span data-stu-id="312e3-139">Download the offering backgrounder</span></span>

<span data-ttu-id="312e3-140">이 제공 사항에 대한 배경 설명 문서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="312e3-140">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="312e3-141">[PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="312e3-141">Download the [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span></span>
