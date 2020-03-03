---
title: 웹 콘텐츠 접근성 지침
description: Microsoft는 전체 제품 또는 서비스 혹은 별도로 설치될 수 있는 제품의 일부를 반영하는 WCAG AA 보고서를 발표합니다.
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
ms.openlocfilehash: f1abc4d885a1d9a1d915bdf5492e3492dc4318a6
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42363024"
---
# <a name="web-content-accessibility-guidelines"></a><span data-ttu-id="45a78-104">웹 콘텐츠 접근성 지침</span><span class="sxs-lookup"><span data-stu-id="45a78-104">Web Content Accessibility Guidelines</span></span>

## <a name="about-wcag"></a><span data-ttu-id="45a78-105">WCAG에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="45a78-105">About WCAG</span></span>

<span data-ttu-id="45a78-106">WCAG(웹 콘텐츠 접근성 지침)는 장애가 있는 사용자가 웹 콘텐츠에 보다 쉽게 접근할 수 있도록 하는 데 사용할 수 있는 프레임워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-106">The Web Content Accessibility Guidelines (WCAG) provide a framework for making web content more accessible for people with disabilities.</span></span> <span data-ttu-id="45a78-107">WCAG 버전 2.0는 웹 표준을 만드는데 전념하는 월드 와이드 웹 컨소시엄(W3C)이 2008년 발행했으며 2018년 6월에 WCAG 2.1로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-107">WCAG version 2.0 was published in 2008 by the World Wide Web Consortium (W3C), an international organization dedicated to creating web standards, and updated to WCAG 2.1 in June 2018.</span></span> <span data-ttu-id="45a78-108">2012년 WCAG 2.0은 또한 국제 표준화 기구(ISO)가 ISO/IEC 40500:2012로 발행하였습니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-108">In 2012, WCAG 2.0 was also published by the International Organization for Standardization (ISO) as ISO/IEC 40500:2012.</span></span>

<span data-ttu-id="45a78-109">WCAG 2.1를 준수하는 콘텐츠 역시 WCAG 2.0를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-109">Content that conforms to WCAG 2.1 also conforms to WCAG 2.0.</span></span> <span data-ttu-id="45a78-110">WCAG 2.0의 준수를 필요로 하는 정책에 WCAG 2.1은 대체적 준수 방법을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-110">For policies requiring conformance to WCAG 2.0, WCAG 2.1 can provide an alternate means of conformance.</span></span>

<span data-ttu-id="45a78-111">Microsoft는 전 세계 고객, 기업 및 정부에 대한 주요 소프트웨어 및 클라우드 서비스 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-111">Microsoft is a major software and cloud-services provider to consumers, businesses, and governments around the world.</span></span> <span data-ttu-id="45a78-112">고객이 구입 의사 결정을 내릴 수 있도록 Microsoft에서는 제품 및 서비스가 WCAG 기준을 지원하는 정도를 설명하는 접근성 준수 보고서를 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-112">To assist customers in making purchasing decisions, Microsoft publishes Accessibility Conformance Reports describing the extent to which our products and services support the WCAG criteria.</span></span> <span data-ttu-id="45a78-113">이 정보를 통해 Microsoft 고객에게 특정 제품이나 서비스가 요구 사항을 충족하는지 확인하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-113">This information can help Microsoft customers determine whether a particular product or service will meet their specific needs.</span></span>
  
## <a name="microsoft-and-wcag"></a><span data-ttu-id="45a78-114">Microsoft와 WCAG</span><span class="sxs-lookup"><span data-stu-id="45a78-114">Microsoft and WCAG</span></span>

<span data-ttu-id="45a78-115">제품 및 서비스 개발에서 Microsoft의 WCAG 표준에 대한 고려 사항은 모든 고객이 기술 및 데이터에 액세스할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-115">Microsoft’s consideration of the WCAG standard in the development of products and services points to its commitment to making technology and data accessible for all customers.</span></span>

<span data-ttu-id="45a78-116">Microsoft는 전체 제품 또는 서비스를 반영하는 WCAG 보고서를 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-116">Microsoft publishes WCAG reports that reflect the complete product or service.</span></span> <span data-ttu-id="45a78-117">Microsoft는 일반적으로 개별 기능이나 구성 요소에 대한 보고서를 작성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-117">It generally does not create reports for individual features or components.</span></span> <span data-ttu-id="45a78-118">간혹 Microsoft는 사용자가 별도로 설치하도록 선택할 수 있는 기존 제품에 대한 새로운 구성 요소나 기존 구성 요소의 새로운 버전을 릴리스할 수도 있으며 해당 구성 요소에 대한 WCAG 보고서를 발표할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-118">Sometimes, Microsoft might release a new component for an existing product, or a new version of an existing component, which users can choose to install separately, and Microsoft might also publish a WCAG report for that component.</span></span>

[<span data-ttu-id="45a78-119">WCAG(ISO/IEC 40500) 접근성 표준 다운로드</span><span class="sxs-lookup"><span data-stu-id="45a78-119">Download the WCAG (ISO/IEC 40500) accessibility standards</span></span>](https://www.w3.org/WAI/standards-guidelines/wcag/)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="45a78-120">Microsoft 범위 내 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="45a78-120">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="45a78-121">Azure 및 Azure Government</span><span class="sxs-lookup"><span data-stu-id="45a78-121">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="45a78-122">Azure DevOps 서비스</span><span class="sxs-lookup"><span data-stu-id="45a78-122">Azure DevOps Services</span></span>
- <span data-ttu-id="45a78-123">Dynamics 365 및 Dynamics 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="45a78-123">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="45a78-124">Intune</span><span class="sxs-lookup"><span data-stu-id="45a78-124">Intune</span></span>
- <span data-ttu-id="45a78-125">Office 365 및 Office 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="45a78-125">Office 365 and Office 365 U.S. Government</span></span>
- <span data-ttu-id="45a78-126">Office 365 US Government Defense</span><span class="sxs-lookup"><span data-stu-id="45a78-126">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="45a78-127">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="45a78-127">Windows Server 2016</span></span>

## <a name="microsoft-accessibility-conformance-reports"></a><span data-ttu-id="45a78-128">Microsft 접근성 적합성 보고서</span><span class="sxs-lookup"><span data-stu-id="45a78-128">Microsoft accessibility conformance reports</span></span>

<span data-ttu-id="45a78-129">[모든 제품 및 서비스](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/)에 대한 WCAG 보고서를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="45a78-129">Read WCAG reports for [all our products and services](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/).</span></span>

## <a name="resources"></a><span data-ttu-id="45a78-130">리소스</span><span class="sxs-lookup"><span data-stu-id="45a78-130">Resources</span></span>

- <span data-ttu-id="45a78-131">[Microsoft 접근성 사이트](https://www.microsoft.com/accessibility): 접근성 기능 사용에 대한 정보를 얻고 모든 사람이 더 많은 것을 달성할 수 있도록 돕기 위해 Microsoft가 혁신하는 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-131">[Microsoft accessibility site](https://www.microsoft.com/accessibility): Get information on using accessibility features and explore the ways Microsoft innovates to help everyone achieve more.</span></span>
- <span data-ttu-id="45a78-132">[Office 365 접근성 센터](https://go.microsoft.com/fwlink/p/?linkid=2051801): 장애가 있는 사용자를 위한 Office 365 리소스</span><span class="sxs-lookup"><span data-stu-id="45a78-132">[Office 365 Accessibility Center](https://go.microsoft.com/fwlink/p/?linkid=2051801): Office 365 resources for people with disabilities.</span></span>
- <span data-ttu-id="45a78-133">[Enterprise Disability Answer Desk](https://go.microsoft.com/fwlink/p/?linkid=2050890): 제품 및 서비스 또는 규정 준수에 대한 접근성과 관련된 질문이 있는 엔터프라이즈 고객을 위한 전용 지원</span><span class="sxs-lookup"><span data-stu-id="45a78-133">[Enterprise Disability Answer Desk](https://go.microsoft.com/fwlink/p/?linkid=2050890): Dedicated support for enterprise customers with accessibility questions about our products and services or compliance.</span></span>
- [<span data-ttu-id="45a78-134">Microsoft 보안 센터에 대한 규정 준수</span><span class="sxs-lookup"><span data-stu-id="45a78-134">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="45a78-135">제공 사항의 배경 설명 다운로드</span><span class="sxs-lookup"><span data-stu-id="45a78-135">Download the offering backgrounder</span></span>

<span data-ttu-id="45a78-136">이 제공 사항에 대한 배경 설명 문서가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="45a78-136">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="45a78-137">[PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="45a78-137">Download the [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span></span>
