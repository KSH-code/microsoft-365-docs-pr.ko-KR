---
title: GDPR 및 CCPA에 대한 Azure 데이터 주체 요청
description: ''
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR, CCPA
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
hideEdit: true
titleSuffix: Microsoft GDPR
ms.openlocfilehash: d54867ad5a469fb429d3edbe012aab9288d76e0f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594347"
---
# <a name="azure-data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="867d2-103">GDPR 및 CCPA에 대한 Azure 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="867d2-103">Azure Data Subject Requests for the GDPR and CCPA</span></span>

## <a name="introduction-to-data-subject-requests-dsrs"></a><span data-ttu-id="867d2-104">DSR(데이터 주체 요청) 소개</span><span class="sxs-lookup"><span data-stu-id="867d2-104">Introduction to Data Subject Requests (DSRs)</span></span>

<span data-ttu-id="867d2-p101">EU(유럽 연합) [GDPR(일반 데이터 보호 규정)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm)은 사용자(규정에 *데이터 주체*로 알려짐)에게 고용주 또는 다른 유형의 대리점 및 조직(*데이터 통제자* 또는 단순히 *통제자*로 지칭)이 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 개인 데이터는 GDPR에서는 보다 광범위하게 식별되었거나 식별 가능한 자연인과 관련된 모든 데이터로 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 부여합니다. 이러한 권한에는 개인 데이터 복사본 획득, 수정 요청, 처리 제한, 삭제 또는 다른 통제자에게 이동될 수 있도록 전자 형식으로 수신하는 권한이 포함됩니다. 데이터 주체가 통제자에게 개인 데이터에 대해 조치를 취할 것을 요구하는 공식적인 요청을 *데이터 주체 요청* 또는 DSR이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p101">The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR.</span></span>

<span data-ttu-id="867d2-109">마찬가지로 캘리포니아 소비자 개인 정보 보호법(CCPA)은 캘리포니아 소비자에게 GDPR의 데이터 주체 권리와 유사한 권리를 포함하여, 소비자의 개인 정보 삭제, 액세스 및 수신(이식성)과 같은 개인 정보 보호 권리 및 의무를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-109">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR’s Data Subject Rights, such as the right to delete, access and receive (portability) their personal information.</span></span> <span data-ttu-id="867d2-110">또한 CCPA는 특정 공개, 실행 권리 행사 시 차별 대우로부터 보호, “판매"로 분류되는 특정 데이터 전송에 대한 "옵트아웃(opt-out)/옵트인(opt-in)" 요구도 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-110">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and “opt-out/ opt-in” requirements for certain data transfers classified as “sales".</span></span> <span data-ttu-id="867d2-111">판매는 가치 있는 대가관계를 위하여 데이터 공유를 포함하도록 광범위하게 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-111">Sales are broadly defined to include the sharing of data for a valuable consideration.</span></span> <span data-ttu-id="867d2-112">CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="867d2-112">For more information about the CCPA, see the [California Consumer Privacy Act](offering-ccpa.md) and the [California Consumer Privacy Act FAQ](ccpa-faq.md).</span></span>

<span data-ttu-id="867d2-p103">이 가이드에서는 Microsoft 제품, 서비스 및 관리 도구를 사용하여 통제자 고객이 DSR에 응답하기 위해 개인 데이터를 찾고 조치를 취하는 데 도움을 주는 방식을 설명합니다. 특히, Microsoft 클라우드에 있는 개인 데이터를 찾고, 액세스하고, 조치를 취하는 방법도 포함되어 있습니다. 이 가이드에 설명된 프로세스에 대한 간략한 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p103">The guide discusses how to use Microsoft products, services and administrative tools to help our controller customers find and act on personal data to respond to DSRs. Specifically, this includes how to find, access, and act on personal data that reside in the Microsoft cloud. Here’s a quick overview of the processes outlined in this guide:</span></span>

- <span data-ttu-id="867d2-116">**검색:** 검색 및 검색 도구를 사용하여 DSR의 대상이 될 수 있는 고객 데이터를 더 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-116">**Discover:** Use search and discovery tools to more easily find customer data that may be the subject of a DSR.</span></span> <span data-ttu-id="867d2-117">잠재적으로 반응형 문서가 수집되면 다음 단계에 설명된 DSR 작업을 수행하여 요청에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-117">Once potentially responsive documents are collected, you can perform one or more of the DSR actions described in the following steps to respond to the request.</span></span> <span data-ttu-id="867d2-118">또는 요청이 DSR에 응답하기 위한 조직의 지침을 충족하지 않는다고 판단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-118">Alternatively, you may determine that the request doesn't meet your organization’s guidelines for responding to DSRs.</span></span>
- <span data-ttu-id="867d2-119">**액세스:** Microsoft 클라우드에 있는 개인 데이터를 검색하고, 요청될 경우 데이터 주체가 사용할 수 있는 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-119">**Access:** Retrieve personal data that resides in the Microsoft cloud and, if requested, make a copy of it that can be available to the data subject.</span></span>
- <span data-ttu-id="867d2-120">**수정:** 해당되는 경우 개인 데이터를 변경하거나 요청된 다른 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-120">**Rectify:** Make changes or implement other requested actions on the personal data, where applicable.</span></span>
- <span data-ttu-id="867d2-121">**제한** 다양한 Azure 서비스에 대한 라이선스를 제거하거나 가능한 경우 원하는 서비스를 꺼서 개인 데이터의 처리를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-121">**Restrict:** Restrict the processing of personal data, either by removing licenses for various Azure services or turning off the desired services where possible.</span></span> <span data-ttu-id="867d2-122">Microsoft 클라우드에서 데이터를 제거하고 온-프레미스 또는 다른 위치에 보존할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-122">You can also remove data from the Microsoft cloud and retain it on-premises or at another location.</span></span>
- <span data-ttu-id="867d2-123">**삭제:** Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-123">**Delete:** Permanently remove personal data that resided in the Microsoft cloud.</span></span>
- <span data-ttu-id="867d2-124">**내보내기/수신(이식성):** 개인 데이터 또는 개인 정보의 전자 사본(컴퓨터가 읽을 수 있는 형식)을 데이터 주체에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-124">**Export/Receive (Portability):** Provide an electronic copy (in a machine-readable format) of personal data or personal information to the data subject.</span></span> <span data-ttu-id="867d2-125">CCPA 하에서 개인 정보는 식별된 또는 식별 가능한 개인과 관련 있는 모든 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-125">Personal information under the CCPA is any information relating to an identified or identifiable person.</span></span> <span data-ttu-id="867d2-126">이때 개인의 비공개, 공개 또는 업무 역할이 구분되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-126">There is no distinction between a person’s private, public, or work roles.</span></span> <span data-ttu-id="867d2-127">정의된 "개인 정보"라는 용어는 GDPR에 따른 "개인 데이터"와 대략 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-127">The defined term “personal information” roughly lines up with “personal data” under GDPR.</span></span> <span data-ttu-id="867d2-128">그러나 CCPA에는 가족 및 가정 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-128">However, the CCPA also includes family and household data.</span></span> <span data-ttu-id="867d2-129">CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="867d2-129">For more information about the CCPA, see the [California Consumer Privacy Act](offering-ccpa.md) and the [California Consumer Privacy Act FAQ](ccpa-faq.md).</span></span>

<span data-ttu-id="867d2-130">이 가이드의 각 섹션에서는 데이터 통제자가 Microsoft 클라우드의 개인 데이터에 대한 DSR에 응답하기 위해 수행할 수 있는 기술적 절차를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-130">Each section in this guide outlines the technical procedures that a data controller organization can take to respond to a DSR for personal data in the Microsoft cloud.</span></span>

## <a name="terminology"></a><span data-ttu-id="867d2-131">용어</span><span class="sxs-lookup"><span data-stu-id="867d2-131">Terminology</span></span>

<span data-ttu-id="867d2-132">다음은 이 가이드와 관련된 용어의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-132">The following provides definitions of terms that are relevant to this guide.</span></span>

- <span data-ttu-id="867d2-133">**통제자:** 단독으로 또는 다른 대상과 함께 개인 데이터 처리의 목적 및 방법을 결정하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다. 이러한 처리의 목적 및 방법을 연합국 법률 또는 회원국 법률에 따라 결정하는 경우, 통제자 또는 구체적인 지명 기준을 연합국 법률 또는 회원국 법률에서 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-133">**Controller:** The natural or legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data; where the purposes and means of such processing are determined by Union or Member State law, the controller, or the specific criteria for its nomination may be provided for by Union or Member State law.</span></span>
- <span data-ttu-id="867d2-134">**개인 데이터 및 데이터 주체** 식별되었거나 식별 가능한 자연인(‘데이터 주체’)과 관련된 모든 정보입니다. 식별 가능한 자연인은 직간접적으로, 특히 이름, 식별 번호, 위치 데이터, 온라인 식별자 또는 해당 자연인의 신체적, 생리적, 유전적, 정신적, 경제적, 문화적 또는 사회적 ID와 같은 식별자를 참조하여 식별될 수 있는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-134">**Personal data and data subject:** Any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural, or social identity of that natural person.</span></span>
- <span data-ttu-id="867d2-135">**프로세서:** 통제자를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-135">**Processor:** A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>
- <span data-ttu-id="867d2-136">**고객 데이터:** 엔터프라이즈 서비스를 사용하여 고객이 Microsoft에 제공하거나 고객 대신에 Microsoft에 제공된 모든 데이터(모든 텍스트, 소리, 동영상 또는 이미지 파일 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-136">**Customer Data:** All data, including all text, sound, video, or image files, and software, that are provided to Microsoft by, or on behalf of, a customer through use of the enterprise service.</span></span> <span data-ttu-id="867d2-137">고객 데이터에는 (1) 최종 사용자의 식별 가능한 정보(예: Azure Active Directory의 사용자 이름 및 연락처 정보) 및 고객이 특정 서비스에 업로드하거나 해당 서비스에서 만드는 고객 콘텐츠(예: Azure Storage 계정의 고객 콘텐츠, Azure SQL 데이터베이스의 고객 콘텐츠 또는 Azure 가상 머신에 있는 고객의 가상 머신 이미지)가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-137">Customer Data includes both (1) identifiable information of end users (for example, user names and contact information in Azure Active Directory) and Customer Content that a customer uploads into or creates in specific services (for example, customer content in an Azure Storage account, customer content of an Azure SQL Database, or a customer’s virtual machine image in Azure Virtual Machines).</span></span>
- <span data-ttu-id="867d2-138">**시스템 생성 로그:** Microsoft에서 생성한 로그 및 관련 데이터이며, 이는 Microsoft에서 엔터프라이즈 서비스를 제공하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-138">**System-Generated Logs:** Logs and related data generated by Microsoft that help Microsoft provide enterprise services to users.</span></span> <span data-ttu-id="867d2-139">시스템 생성 로그에는 주로 가명 처리된 데이터(예: 일반적으로 시스템에서 생성된 숫자인 고유한 ID)가 있으며, 이 데이터는 개인을 직접 식별할 수 없지만 엔터프라이즈 서비스를 사용자에게 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-139">System-generated logs contain primarily pseudonymized data, such as unique identifiers — typically a number generated by the system that cannot on its own identify an individual person but is used to deliver the enterprise services to users.</span></span> <span data-ttu-id="867d2-140">시스템 생성 로그에는 사용자 이름과 같은 최종 사용자에 대한 식별 가능한 정보가 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-140">System-generated logs may also contain identifiable information about end users, such as a user name.</span></span>

## <a name="how-to-use-this-guide"></a><span data-ttu-id="867d2-141">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="867d2-141">How to use this guide</span></span>

<span data-ttu-id="867d2-142">이 가이드의 다음 두 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-142">This guide consists of two parts:</span></span>

- <span data-ttu-id="867d2-143">**1부: 고객 데이터에 대한 데이터 주체 요청에 응답:** 이 가이드 1부에서는 데이터를 작성한 애플리케이션에서 데이터를 액세스, 수정, 제한, 삭제 및 내보내는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-143">**Part 1: Responding to Data Subject Requests for Customer Data:** Part 1 of this guide discusses how to access, rectify, restrict, delete, and export data from applications in which you have authored data.</span></span> <span data-ttu-id="867d2-144">이 섹션에서는 최종 사용자의 고객 콘텐츠 및 식별 가능 정보에 대해 DSR을 실행하는 방법을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-144">This section details how to execute DSRs against both Customer Content and also identifiable information of end users.</span></span>
- <span data-ttu-id="867d2-145">**2부: 시스템 생성 로그에 대한 데이터 주 체 요청에 응답:** Microsoft의 엔터프라이즈 서비스를 사용할 경우, Microsoft는 서비스를 제공하기 위해 시스템 생성 로그라고 하는 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-145">**Part 2: Responding to Data Subject Requests for System-Generated Logs:** When you use Microsoft’s enterprise services, Microsoft generates some information, known as System-Generated Logs, in order to provide the service.</span></span> <span data-ttu-id="867d2-146">이 가이드의 2부에서는 Azure에서 이러한 정보를 액세스, 삭제 및 내보내는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-146">Part 2 of this guide discusses how to access, delete, and export such information for Azure.</span></span>

## <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a><span data-ttu-id="867d2-147">Azure Active Directory 및 Microsoft 서비스 계정에 대한 DSR 이해</span><span class="sxs-lookup"><span data-stu-id="867d2-147">Understanding DSRs for Azure Active Directory and Microsoft service accounts</span></span>

<span data-ttu-id="867d2-p111">엔터프라이즈 고객에게 제공되는 서비스를 고려할 때, DSR의 실행은 항상 특정 AAD(Azure Active Directory) 테넌트의 컨텍스트 내에서 이해할 수 있어야 합니다. 특히 DSR은 항상 지정된 AAD 테넌트 내에서 실행됩니다. 사용자가 여러 테넌트에 참여하는 경우, 지정된 DSR이 *반드시* 요청이 수신된 특정 테넌트의 컨텍스트 내에서 실행된다는 점을 강조해서 알려주는 것이 중요합니다. 이러한 정보는 한 엔터프라이즈 고객의 DSR 실행이 인접 엔터프라이즈 고객의 데이터에 영향을 미치지 **않는다는 것**을 의미하므로 반드시 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p111">When considering services provided to enterprise customers, execution of DSRs must always be understood within the context of a specific Azure Active Directory (AAD) tenant. Notably, DSRs are always executed within a given AAD tenant. If a user is participating in multiple tenants, it is important to emphasize that a given DSR is *only* executed within the context of the specific tenant the request was received within. This is critical to understand as it means the execution of a DSR by one enterprise customer **will not** impact the data of an adjacent enterprise customer.</span></span>

<span data-ttu-id="867d2-p112">엔터프라이즈 고객에게 제공되는 서비스 컨텍스트 내의 MSA(Microsoft 서비스 계정)도 마찬가지입니다. *AAD 테넌트와 연결된* MSA 계정에 대해 DSR을 실행할 경우 해당 테넌트 내의 데이터 **와만 관련됩니다**. 또한 테넌트 내에서 MSA 계정을 처리하는 경우에는 다음 사실을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p112">The same also applies for Microsoft Service Accounts (MSA) within the context of services provided to an enterprise customer: execution of a DSR against an MSA account *associated with an AAD tenant* **will only** pertain to data within the tenant. In addition, it is important to understand the following when handling MSA accounts within a tenant:</span></span>

- <span data-ttu-id="867d2-p113">MSA 사용자가 Azure 구독을 만들면 구독은 마치 AAD 테넌트인 것처럼 처리됩니다. 결과적으로 DSR은 위에 설명된 것처럼 테넌트 내로 한정됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p113">If an MSA user creates an Azure subscription, the subscription will be handled as if it were an AAD tenant. Consequently, DSRs are scoped within the tenant as described above.</span></span>
- <span data-ttu-id="867d2-p114">MSA 계정을 통해 만든 Azure 구독을 삭제한 경우 실제 MSA 계정에는 **영향을 주지 않습니다**. 다시 말해서 위에서 언급한 것처럼 Azure 구독 내에서 실행되는 DSR은 테넌트 범위로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p114">If an Azure subscription created via an MSA account is deleted, **it will not affect** the actual MSA account. Again, as noted above, DSRs executing within the Azure subscription are limited to the scope of the tenant itself.</span></span>

<span data-ttu-id="867d2-p115">**지정된 테넌트의 외부에 있는** MSA 계정 자체에 대한 DSR은 소비자 개인 정보 보호 대시보드를 통해 실행됩니다. 자세한 내용은 Windows 데이터 주체 요청 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="867d2-p115">DSRs against an MSA account itself, **outside a given tenant**, are executed via the Consumer Privacy Dashboard. Please refer to the Windows Data Subject Request Guide for further details.</span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a><span data-ttu-id="867d2-160">1부: 고객 데이터에 대한 DSR 가이드</span><span class="sxs-lookup"><span data-stu-id="867d2-160">Part 1: DSR Guide for customer data</span></span>

### <a name="executing-dsrs-against-customer-data"></a><span data-ttu-id="867d2-161">고객 데이터에 대해 DSR 실행</span><span class="sxs-lookup"><span data-stu-id="867d2-161">Executing DSRs against customer data</span></span>

<span data-ttu-id="867d2-p116">Microsoft는 Azure Portal을 통해 또는 특정 서비스에 대한 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접(*제품 내 환경*) 특정 고객 데이터를 액세스, 삭제 및 내보내는 기능을 제공합니다. 제품 내 환경에 대한 자세한 내용은 해당 서비스 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p116">Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as *in-product experiences*). Details regarding such in-product experiences are described in the respective services’ reference documentation.</span></span>

>[!IMPORTANT]  
> <span data-ttu-id="867d2-p117">제품 내 DSR을 지원하는 서비스에서는 서비스의 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 직접적으로 사용하고 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명해야 합니다. 따라서 지정된 데이터 주체에 대한 모든 요청을 완료하기 위해서는 Azure Portal 내의 DSR 외에도 지정된 서비스 내의 DSR도 실행해야 합니다. 자세한 내용은 특정 서비스 참조 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="867d2-p117">Services supporting in-product DSRs require direct usage of the service’s application programming interface (API) or user interface (UI), describing applicable CRUD (create, read, update, delete) operations. Consequently, execution of DSRs within a given service must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services’ reference documentation for further details.</span></span>

### <a name="step-1-discover"></a><span data-ttu-id="867d2-167">1단계: 검색</span><span class="sxs-lookup"><span data-stu-id="867d2-167">Step 1: Discover</span></span>

<span data-ttu-id="867d2-168">DSR에 대응하는 첫 번째 단계는 요청의 제목인 개인 데이터를 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-168">The first step in responding to a DSR is to find the personal data that is the subject of the request.</span></span> <span data-ttu-id="867d2-169">첫 번째 단계(문제가 된 개인 데이터 찾기 및 검토)를 통해 DSR의 준수 또는 거부에 필요한 이 조직의 요구 사항을 충족하는지를 판별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-169">This first step — finding and reviewing the personal data at issue — will help you determine whether a DSR meets your organization's requirements for honoring or declining a DSR.</span></span> <span data-ttu-id="867d2-170">예를 들어, 문제가 된 개인 데이터를 찾고 검토한 후, 이 작업이 타인의 권리와 자유에 불리한 영향을 미칠 수 있으므로 해당 요청이 조직의 요구 사항을 충족하지 않는지를 판별합니다. </span><span class="sxs-lookup"><span data-stu-id="867d2-170">For example, after finding and reviewing the personal data at issue, you may determine the request doesn’t meet your organization’s requirements because doing so may adversely affect the rights and freedoms of others.</span></span>

<span data-ttu-id="867d2-171">데이터를 찾은 후에 데이터 주체의 요청을 충족하기 위한 특정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-171">After you find the data, you can then perform the specific action to satisfy the request by the data subject.</span></span>

<span data-ttu-id="867d2-p119">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/)는 Microsoft의 클라우드 기반, 다중 테넌트 디렉터리 및 ID 관리 서비스입니다. [Azure Portal](https://portal.azure.com/)을 사용하여 [AAD(Azure Active Directory)](https://azure.microsoft.com/services/active-directory/) 환경에서 개인 데이터를 포함하는 고객 및 직원 사용자 프로필, 사용자 작업 정보와 같은 최종 사용자의 식별 가능한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p119">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) is Microsoft’s cloud-based, multi-tenant directory and identity management service. You can locate identifiable information of end users, such as customer and employee user profiles and user work information that contain personal data in your [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) environment by using the [Azure portal](https://portal.azure.com/).</span></span>

<span data-ttu-id="867d2-p120">이 서비스는 특정 사용자에 대한 개인 데이터를 찾거나 변경하려는 경우에 특히 유용합니다. 사용자 프로필과 작업 정보를 추가하거나 변경할 수도 있습니다. 디렉터리에 대한 전역 관리자인 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p120">This is particularly helpful if you want to find or change personal data for a specific user. You can also add or change user profile and work information. You must sign in with an account that’s a global admin for the directory.</span></span>

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a><span data-ttu-id="867d2-177">사용자 프로필 및 회사 정보를 찾아서 보려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="867d2-177">How do I locate or view user profile and work information?</span></span>

1. <span data-ttu-id="867d2-178">디렉터리에 대한 전역 관리자인 계정을 사용하여 [Azure Portal](https://portal.azure.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-178">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

2. <span data-ttu-id="867d2-179">**Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-179">Select **Azure Active Directory**.</span></span>

     ![모든 서비스 선택](media/gdpr-azure-dsr-azure-portal.png)

3. <span data-ttu-id="867d2-181">**사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-181">Select **Users**.</span></span>

     ![사용자 선택](media/gdpr-azure-dsr-azure-all-users.png)

4. <span data-ttu-id="867d2-183">**모든 사용자** 블레이드의 목록에서 사용자를 선택하고, 선택한 사용자에 대한 블레이드에서 **프로필**을 선택하여 개인 데이터가 포함될 수 있는 사용자 프로필 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-183">On the **All users** blade, select a user from the list, and then, on the blade for the selected user, select **Profile** to view user profile information that might contain personal data.</span></span>

    ![프로필 선택](media/gdpr-azure-dsr-azure-user-profile.png)

5. <span data-ttu-id="867d2-185">사용자 프로필 정보를 추가하거나 변경해야 할 경우 명령 모음에서 **편집**을 선택하여 이 작업을 수행하고, 변경 후 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-185">If you need to add or change user profile information, you can do so by selecting **Edit** in the command bar, then select **Save** after making changes.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="867d2-186">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="867d2-186">Service-specific interfaces</span></span>

<span data-ttu-id="867d2-p121">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p121">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-2-access"></a><span data-ttu-id="867d2-189">2단계: 액세스</span><span class="sxs-lookup"><span data-stu-id="867d2-189">Step 2: Access</span></span>

<span data-ttu-id="867d2-p122">DSR에 응답하는 개인 데이터가 포함된 고객 데이터를 찾은 후에 귀하와 조직은 데이터 주체에게 제공할 데이터를 결정해야 합니다. 실제 문서의 사본, 적절히 수정된 버전 또는 공유할 수 있는 부분의 스크린샷을 제공할 수 있습니다. 액세스 요청에 대한 이러한 각 응답에 대해, 응답 데이터를 포함하는 문서 또는 기타 항목 사본을 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p122">After you’ve found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.</span></span>

<span data-ttu-id="867d2-193">데이터 주체에 사본을 제공할 때는 다른 데이터 주체에 대한 개인 정보와 모든 기밀 정보를 제거하거나 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-193">When providing a copy to the data subject, you may have to remove or redact personal information about other data subjects and any confidential information.</span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="867d2-194">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="867d2-194">Azure Active Directory</span></span>

<span data-ttu-id="867d2-195">Microsoft는 엔터프라이즈 고객의 테넌트 관리자에게 DSR 액세스 요청을 관리하는 기능을 제공하는 포털 및 제품 내 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-195">Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage DSR access requests.</span></span> <span data-ttu-id="867d2-196">DSR 액세스 요청을 사용하며 사용자의 개인 데이터((a) 최종 사용자에 대한 ID 정보 및 (b) 시스템 생성 로그)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-196">DSR Access requests allow for access of the personal data of the user, including: (a) identifiable information about an end-user and (b) system-generated logs.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="867d2-197">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="867d2-197">Service-specific interfaces</span></span>

<span data-ttu-id="867d2-p124">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p124">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-3-rectify"></a><span data-ttu-id="867d2-200">3단계: 수정</span><span class="sxs-lookup"><span data-stu-id="867d2-200">Step 3: Rectify</span></span>

<span data-ttu-id="867d2-p125">데이터 주체가 조직 데이터에 포함된 개인 데이터를 수정할 것을 요청한 경우 귀하와 조직은 요청을 수락하는 것이 적절한지 여부를 결정해야 합니다. 데이터 수정에는 개인 데이터의 편집, 수정 또는 문서나 기타 형식 또는 항목에서 개인 데이터를 제거하는 것과 같은 작업이 포함될 수 있습니다. Microsoft 고객 지원 및 FastTrack 데이터에 대해 이 작업을 수행하는 가장 편리한 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p125">If a data subject has asked you to rectify the personal data that resides in your organization’s data, you and your organization will have to determine whether it’s appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item. The most expedient way to do this for Microsoft Support and FastTrack data is provided below.</span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="867d2-204">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="867d2-204">Azure Active Directory</span></span>

<span data-ttu-id="867d2-p126">엔터프라이즈 고객은 지정된 Microsoft 서비스의 특성에 따른 제한된 편집 기능을 비롯하여, DSR을 관리하여 요청을 수정하는 기능이 있습니다. 데이터 처리자의 역할을 하는 Microsoft는 Microsoft 서비스 내에서 실제 활동을 반영하고 이벤트의 기록 레코드를 구성하는 시스템 생성 로그를 수정하는 것을 허용하지 않습니다. 아래에 자세히 설명된 것처럼, Azure Active Directory에는 최종 사용자에 대한 식별 가능 정보를 수정할 수 있는 제한된 편집 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p126">Enterprise customers have the ability to manage DSR rectify requests, including limited editing features per the nature of a given Microsoft service. As a data processor, Microsoft does not offer the ability to correct system-generated logs as it reflects factual activities and constitutes a historical record of events within Microsoft services. With respect to Azure Active Directory, limited editing features exist to rectify identifiable information about an end-user, as described further below.</span></span>

##### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a><span data-ttu-id="867d2-208">Azure Active Directory: 부정확하거나 불완전한 개인 데이터의 수정</span><span class="sxs-lookup"><span data-stu-id="867d2-208">Azure Active Directory: rectify/correct inaccurate or incomplete personal data</span></span>

<span data-ttu-id="867d2-p127">[Azure Portal](https://portal.azure.com/)을 사용하여 [AAD(Azure Active Directory)](https://azure.microsoft.com/services/active-directory/) 환경에서 개인 데이터(예: 사용자 이름, 직책, 주소 또는 전화 번호)를 포함하는 고객 및 직원 사용자 프로필, 사용자 작업 정보와 같은 최종 사용자에 대한 식별 가능 정보를 수정, 업데이트 또는 삭제할 수 있습니다. 디렉터리에 대해 전역 관리자에 해당하는 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p127">You can correct, update, or delete identifiable information about end users, such as customer and employee user profiles and user work information that contain personal data, such as a user’s name, work title, address, or phone number, in your [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) environment by using the [Azure portal](https://portal.azure.com/). You must sign in with an account that’s a global admin for the directory.</span></span>

###### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a><span data-ttu-id="867d2-211">Azure Active Directory에서 사용자 프로필 및 작업 정보를 수저하거나 업데이트하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="867d2-211">How do I correct or update user profile and work information in Azure Active Directory?</span></span>

1. <span data-ttu-id="867d2-212">디렉터리에 대한 전역 관리자인 계정을 사용하여 [Azure Portal](https://portal.azure.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-212">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

2. <span data-ttu-id="867d2-213">**Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-213">Select **Azure Active Directory**.</span></span>

    ![모든 서비스 선택](media/gdpr-azure-dsr-azure-portal.png)

3. <span data-ttu-id="867d2-215">**사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-215">Select **Users**.</span></span>

    ![사용자 선택](media/gdpr-azure-dsr-azure-all-users.png)

4. <span data-ttu-id="867d2-217">**모든 사용자** 블레이드의 목록에서 사용자를 선택하고, 선택한 사용자에 대한 블레이드에서 **프로필**을 선택하여 수정하거나 업데이트해야 하는 사용자 프로필 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-217">On the **All users** blade, select a user from the list, and then, on the blade for the selected user, select **Profile** to view the user profile information that needs to be corrected or updated.</span></span>

    ![프로필 선택](media/gdpr-azure-dsr-azure-user-profile.png)

5. <span data-ttu-id="867d2-219">명령 모음에서 **편집**을 선택하여 작업 정보를 포함한 사용자 프로질 정보를 수정하거나 업데이트하고, 변경 후  **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-219">Correct or update the user profile information including work information by selecting **Edit** in the command bar, then select **Save** after making changes.</span></span>

    ![프로필 선택](media/gdpr-azure-dsr-azure-edit-user-profile.png)

#### <a name="service-specific-interfaces"></a><span data-ttu-id="867d2-221">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="867d2-221">Service-Specific Interfaces</span></span>

<span data-ttu-id="867d2-p128">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p128">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-4-restrict"></a><span data-ttu-id="867d2-224">4단계: 제한</span><span class="sxs-lookup"><span data-stu-id="867d2-224">Step 4: Restrict</span></span>

<span data-ttu-id="867d2-225">데이터 주체가 개인 데이터 처리를 제한하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-225">Data subjects may request that you restrict processing of their personal data.</span></span> <span data-ttu-id="867d2-226">Azure 포털과 기존 API(Application Programming Interface) 또는 UI(사용자 인터페이스)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-226">We provide both the Azure Portal and pre-existing application programming interfaces (APIs) or user interfaces (UIs).</span></span> <span data-ttu-id="867d2-227">이러한 환경은 엔터프라이즈 고객의 테넌트 관리자에게 데이터 내보내기 및 데이터 삭제의 조합을 통해 그와 같은 DSR을 관리할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-227">These experiences provide the enterprise customer’s tenant administrator the capability to manage such DSRs through a combination of data export and data deletion.</span></span> <span data-ttu-id="867d2-228">고객은 (1) 사용자의 개인 데이터에 대한 전자 사본((2)Microsoft 시스템에 상주하는 계정 및 관련 데이터 삭제 이후 발생하는 (a) 계정, (b) 시스템 생성 로그 및 (c) 관련 로그 포함)을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-228">A customer may (1) export an electronic copy of the personal data of the user, including (a) account(s), (b) system-generated logs, and (c) associated logs, followed with (2) deletion of the account and associated data residing within Microsoft systems.</span></span>

### <a name="step-5-delete"></a><span data-ttu-id="867d2-229">5단계: 삭제</span><span class="sxs-lookup"><span data-stu-id="867d2-229">Step 5: Delete</span></span>

<span data-ttu-id="867d2-230">조직의 고객 데이터에서 개인 데이터 제거하는 "삭제 권한"은 GDPR에서 핵심적인 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-230">The “right to erasure” by the removal of personal data from an organization’s Customer Data is a key protection in the GDPR.</span></span> <span data-ttu-id="867d2-231">개인 데이터를 제거하면 감사 로그 정보를 제외한, 모든 개인 데이터와 시스템 생성 로그가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-231">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span> <span data-ttu-id="867d2-232">사용자가 **일시 삭제**(아래 세부 정보 참조)되면, 계정이 30일 동안 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-232">When a user is **soft deleted** (see details below), the account is disabled for 30 days.</span></span> <span data-ttu-id="867d2-233">이 30일 동안 추가 작업이 없는 경우, 사용자가 **영구 삭제**됩니다(아래 세부 정보 참조).</span><span class="sxs-lookup"><span data-stu-id="867d2-233">If no further action is taken during this 30-day period, the user is **permanently deleted** (again, see details below).</span></span> <span data-ttu-id="867d2-234">**영구 삭제** 시, 사용자의 계정, 개인 데이터 및 시스템 생성 로그가 30일 이내에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-234">Upon a **permanent delete**, the user’s account, personal data, and system-generated logs are expunged within an additional 30 days.</span></span> <span data-ttu-id="867d2-235">테넌트 관리자가 즉시 **영구적 삭제**를 발행하는 경우, 사용자 계정, 개인 데이터 및 시스템 생성 로그가 발행 30 일 이내에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-235">If a tenant admin immediately issues a **permanent delete**, the user’s account, personal data, and system-generated logs are expunged within 30 days of issuance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="867d2-236">테넌트에서 사용자를 삭제하려면 테넌트 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-236">You must be a tenant administrator to delete a user from the tenant.</span></span>

#### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a><span data-ttu-id="867d2-237">Azure Portal을 통해 사용자 및 관련 데이터 삭제</span><span class="sxs-lookup"><span data-stu-id="867d2-237">Delete a user and associated data through the Azure portal</span></span>

<span data-ttu-id="867d2-238">데이터 주체에 대한 삭제 요청을 수신한 후에 Azure Portal을 사용하여 시스템 생성 로그 뿐만 아니라 사용자 및 관련 개인 정보를 둘 다 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-238">After you receive a delete request for a data subject, you can use the Azure portal to delete both a user and the associated personal information as well as system-generated logs.</span></span>

<span data-ttu-id="867d2-p131">이 데이터를 삭제한다는 것은 테넌트에서 사용자를 삭제하는 것을 의미합니다. 사용자는 처음에 일시적으로 삭제됩니다. 즉, 일시 삭제용으로 표시되고 30일 이내에 테넌트 관리자가 계정을 복구할 수 있습니다. 30일 후에 해당 계정은 테넌트에서 자동으로 영구 삭제됩니다. 해당 30일 이전에는 휴지통에서 일시 삭제된 사용자를 수동으로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p131">Deleting this data also means deleting the user from the tenant. Users are initially soft-deleted, which means the account can be recovered by a tenant admin within 30 days of being marked for soft-delete. After 30 days, the account is automatically, and permanently, deleted from the tenant. Prior to that 30 days, you can manually delete a soft-deleted user from the recycle bin.</span></span>

<span data-ttu-id="867d2-243">테넌트에서 사용자를 삭제하기 위한 고급 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-243">Here’s the high-level process for deleting users from your tenant.</span></span>

1. <span data-ttu-id="867d2-244">Azure Portal로 이동한 후 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-244">Go to the Azure portal and locate the user.</span></span>

2. <span data-ttu-id="867d2-p132">사용자를 삭제합니다. 처음에 사용자를 삭제하면 사용자의 계정이 휴지통으로 전송됩니다. **이때 사용자는 일시적으로 삭제됩니다. 즉, 계정은 사용되지 않도록 설정되지만 Azure Active Directory에서 지워지지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="867d2-p132">Delete the user. When you initially delete the user, the user’s account is sent to the Recycle Bin. **At this point, the user is soft deleted, meaning the account is disabled, but not expunged from Azure Active Directory.**</span></span>

3. <span data-ttu-id="867d2-p133">최근에 삭제된 사용자 목록으로 이동한 다음, 사용자를 영구적으로 삭제합니다. **이때 사용자는 영구적으로 삭제됩니다. 즉, 계정이 Azure Active Directory에서 지워진 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="867d2-p133">Go to the Recently deleted users list and permanently delete the user. **At this point the user is permanently deleted (also known as hard deleted), meaning the account has been expunged from Azure Active Directory**</span></span>

###### <a name="to-delete-a-user-from-an-azure-tenant"></a><span data-ttu-id="867d2-250">Azure 테넌트에서 사용자를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="867d2-250">To delete a user from an Azure tenant</span></span>

1. <span data-ttu-id="867d2-251">디렉터리에 대한 전역 관리자인 계정을 사용하여 [Azure Portal](https://portal.azure.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-251">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

2. <span data-ttu-id="867d2-252">**Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-252">Select **Azure Active Directory**.</span></span>

    ![모든 서비스 선택](media/gdpr-azure-dsr-azure-portal.png)

3. <span data-ttu-id="867d2-254">**사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-254">Select **Users**.</span></span>

    ![사용자 선택](media/gdpr-azure-dsr-azure-all-users.png)

4. <span data-ttu-id="867d2-256">삭제하려는 사용자 옆의 확인란을 선택하고 **사용자 삭제**를 선택한 후 사용자를 삭제할 것인지 묻는 상자에서 **예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-256">Check the box next to the user you want to delete, select **Delete user**, and then select **Yes** in the box asking if you want to delete the user.</span></span>

    ![사용자 관리](media/gdpr-azure-dsr-azure-selected-user.png)

5. <span data-ttu-id="867d2-258"> *\*모든 사용자** 블레이드에서  *\*삭제된 사용자*\*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-258">On the **All users** blade, select **Deleted users**.</span></span>

    ![사용자 프로필 보기](media/gdpr-azure-dsr-azure-deleted-user.png)

4. <span data-ttu-id="867d2-260">같은 사용자를 다시 선택하고 명령 모음에서  **영구적으로 삭제**를 선택한 후 확실히 삭제할 것인지 묻는 상자에서  **예** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-260">Select the same user again, select **Delete permanently** in the command bar, and then select **Yes** in the box asking if you’re sure.</span></span>

>[!IMPORTANT]  
><span data-ttu-id="867d2-p134">**예**를 클릭하면 사용자 및 모든 관련 데이터와 시스템 생성 로그가 영구적으로 삭제됩니다. 실수로 이렇게 삭제한 경우에는 수동으로 사용자를 테넌트에 다시 추가해야 합니다. 관련된 데이터 및 시스템 생성 로그는 복구 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p134">Be aware that by clicking **Yes** you are permanently, and irrevocably, deleting the user and all associated data and system-generated logs. If you do this by mistake, you’ll have to manually add the user back to the tenant. The associated data and system-generated logs are non-recoverable.</span></span>

   ![사용자 작업 정보 보기](media/gdpr-azure-dsr-azure-permanently-deleted-user.png)

#### <a name="service-specific-interfaces"></a><span data-ttu-id="867d2-265">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="867d2-265">Service-specific interfaces</span></span>

<span data-ttu-id="867d2-p135">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p135">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

## <a name="step-6-export"></a><span data-ttu-id="867d2-268">6단계: 내보내기</span><span class="sxs-lookup"><span data-stu-id="867d2-268">Step 6: Export</span></span>

<span data-ttu-id="867d2-269">"데이터 이식성의 권한”이 있는 경우 데이터 제목에서 다른 데이터 컨트롤러로 전송할 수 있는 해당 개인 데이터의 사본을 전자 형식으로 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-269">The “right of data portability” allows a data subject to request a copy of their personal data in an electronic format (that’s a “structured, commonly used, machine read-able, and interoperable format”) that may be transmitted to another data controller.</span></span> <span data-ttu-id="867d2-270">Azure는 조직이 네이티브 JSON 형식의 데이터를 지정된 Azure Storage Container로 내보내어 이를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-270">Azure supports this by enabling your organization to export the data in the native JSON format, to your specified Azure Storage Container.</span></span>

>[!IMPORTANT]
><span data-ttu-id="867d2-271">테넌트에서 사용자 데이터를 내보내려면 테넌트 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-271">You must be a tenant administrator to export user data from the tenant.</span></span>

### <a name="azure-active-directory"></a><span data-ttu-id="867d2-272">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="867d2-272">Azure Active Directory</span></span>

<span data-ttu-id="867d2-273">고객 데이터와 관련해서, Microsoft는 엔터프라이즈 고객의 테넌트 관리자에게 최종 사용자에 대한 식별 가능 정보의 내보내기 요청을 관리하는 기능을 지원하는 포털 및 제품 내 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-273">With respect to Customer Data, Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage export requests for identifiable information about an end user.</span></span>

### <a name="service-specific-interfaces"></a><span data-ttu-id="867d2-274">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="867d2-274">Service-specific interfaces</span></span>

<span data-ttu-id="867d2-p137">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p137">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

## <a name="part-2-system-generated-logs"></a><span data-ttu-id="867d2-277">2부: 시스템 생성 로그</span><span class="sxs-lookup"><span data-stu-id="867d2-277">Part 2: System-Generated Logs</span></span>

<span data-ttu-id="867d2-278">또한 Microsoft는 Azure의 사용자 사용과 관련된 특정 시스템 생성 로그를 액세스, 삭제 및 내보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-278">Microsoft also provides you with the ability to access, delete, and export certain system-generated logs associated with a user’s use of Azure.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="867d2-p138">시스템 생성 로그 문제를 제한하거나 수정하는 기능은 지원되지 않습니다. 시스템 생성 로그는 Microsoft 클라우드 및 진단 데이터 내에서 수행되는 실제 작업으로 구성되며, 이러한 데이터를 수정하면 작업의 기록 데이터가 손상되어 사기 및 보안 위험이 높아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p138">The ability to restrict or rectify system-generated logs is not supported. System-generated logs constitute factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions, increasing fraud and security risks.</span></span>

### <a name="executing-dsrs-against-system-generated-logs"></a><span data-ttu-id="867d2-281">시스템 생성 로그에 대해 DSR 실행</span><span class="sxs-lookup"><span data-stu-id="867d2-281">Executing DSRs against System-Generated Logs</span></span>

<span data-ttu-id="867d2-p139">Microsoft는 Azure Portal을 통해, 특정 서비스에 대한 프로그래밍 인터페이스 또는 사용자 인터페이스를 통해 직접 특정 시스템 생성 로그를 액세스, 삭제 및 내보낼 수 있는 기능을 제공합니다. 세부 정보는 해당 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p139">Microsoft provides the ability to access, delete, and export certain system-generated logs through the Azure Portal and also directly via programmatic interfaces or user interfaces for specific services. Details are described in the respective services’ reference documentation.</span></span>

>[!IMPORTANT]  
> <span data-ttu-id="867d2-p140">제품 내 DSR을 지원하는 서비스에서는 서비스의 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 직접적으로 사용해야 합니다. 따라서 지정된 데이터 주체에 대한 모든 요청을 완료하기 위해서는 Azure Portal 내의 DSR 외에도 제품 내 DSR도 **실행해야 합니다. 자세한 내용은 특정 서비스 참조 설명서를 참조하세요.**</span><span class="sxs-lookup"><span data-stu-id="867d2-p140">Services supporting in-product DSRs require direct usage of the service’s application programming interface (API) or user interface (UI). Consequently, execution of an in-product DSRs **must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services’ reference documentation for further details.**</span></span>

### <a name="step-1-access"></a><span data-ttu-id="867d2-286">1단계: 액세스</span><span class="sxs-lookup"><span data-stu-id="867d2-286">Step 1: Access</span></span>

<span data-ttu-id="867d2-p141">테넌트 관리자는 Azure의 특정 사용자의 사용과 관련된 시스템 생성 로그에 액세스할 수 있는 조직 내의 유일한 사람입니다. 액세스 요청에 대한 검색된 데이터는 컴퓨터가 읽을 수 있는 형식으로 제공되며, 데이터가 어떤 서비스에 연결되어 있는지 알 수 있도록 하는 파일로 제공됩니다. 위에서 설명한 것처럼 검색된 데이터에 서비스의 보안을 침해할 수 있는 데이터는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p141">The tenant admin is the only person within your organization who can access system-generated logs associated with a particular user’s use of Azure. The data retrieved for an access request will be provided in a machine-readable format and will be provided in files that will allow the user to know which services the data is associated with. As noted above, the data retrieved will not include data that may compromise the security of the service.</span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="867d2-290">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="867d2-290">Azure Active Directory</span></span>

<span data-ttu-id="867d2-291">Microsoft는 엔터프라이즈 고객의 테넌트 관리자에게 액세스 요청을 관리하는 기능을 제공하는 포털 및 제품 내 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-291">Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage access requests.</span></span> <span data-ttu-id="867d2-292">액세스 요청을 사용하며 사용자의 개인 데이터((a) 최종 사용자에 대한 ID 정보 및 (b) 서비스 생성 로그)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-292">Access requests will allow for access of the personal data of the user, including: (a) identifiable information about an end user and (b) service-generated logs.</span></span> <span data-ttu-id="867d2-293">프로세스는 1부 2단계: 액세스의 Azure Active Directory 섹션에 설명된 내용과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-293">The process is identical to that described in the Azure Active Directory section of Part 1, Step 2: Access.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="867d2-294">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="867d2-294">Service-specific interfaces</span></span>

<span data-ttu-id="867d2-p143">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p143">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-2-delete"></a><span data-ttu-id="867d2-297">2단계: 삭제</span><span class="sxs-lookup"><span data-stu-id="867d2-297">Step 2: Delete</span></span>

<span data-ttu-id="867d2-298">테넌트 관리자는 Azure 테넌트 내의 특정 사용자에 대한 DSR 삭제 요청을 실행할 수 있는 조직 내의 유일한 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-298">The tenant admin is the only person within your organization who can execute a DSR delete request for a particular user within an Azure tenant.</span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="867d2-299">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="867d2-299">Azure Active Directory</span></span>

<span data-ttu-id="867d2-p144">Microsoft는 엔터프라이즈 고객의 테넌트 관리자에게 DSR 삭제 요청을 관리하는 기능을 제공하는 포털 및 제품 환경을 둘 다 제공합니다. DSR 삭제 요청은 1부, 5단계: 삭제의 Azure Portal 섹션을 통해 사용자 및 관련 데이터 삭제에 설명된 것과 동일한 방식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p144">Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage DSR delete requests. DSR delete requests follow the same as described in the Delete a user and associated data through the Azure portal section of Part 1, Step 5: Delete.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="867d2-302">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="867d2-302">Service-specific interfaces</span></span>

<span data-ttu-id="867d2-p145">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p145">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-3-export"></a><span data-ttu-id="867d2-305">3단계: 내보내기</span><span class="sxs-lookup"><span data-stu-id="867d2-305">Step 3: Export</span></span>

<span data-ttu-id="867d2-p146">테넌트 관리자는 Azure의 특정 사용자의 사용과 관련된 시스템 생성 로그에 액세스할 수 있는 조직 내의 유일한 사람입니다. 내보내기 요청에 대한 검색된 데이터는 컴퓨터가 읽을 수 있는 형식으로 제공되며, 데이터가 어떤 서비스에 연결되어 있는지 알 수 있도록 하는 파일로 제공됩니다. 위에서 설명한 것처럼 검색된 데이터에 서비스의 보안 또는 안정성을 침해할 수 있는 데이터는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p146">The tenant admin is the only person within your organization who can access system-generated logs associated with a particular user’s use of Azure. The data retrieved for an export request will be provided in a machine-readable format and will be provided in files that will allow the user to know which services the data is associated with. As noted above, the data retrieved will not include data that may compromise the security or stability of the service.</span></span>

#### <a name="export-system-generated-logs-using-the-azure-portal"></a><span data-ttu-id="867d2-309">Azure Portal을 사용하여 시스템 생성 로그 내보내기</span><span class="sxs-lookup"><span data-stu-id="867d2-309">Export system-generated logs using the Azure portal</span></span>

<span data-ttu-id="867d2-310">데이터 주체에 대한 내보내기 요청을 받은 경우, Azure Portal을 사용하여 지정된 사용자와 연결된 시스템 생성 로그를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-310">After you receive an export request for a data subject, you can use the Azure portal to export system-generated logs associated with a given user.</span></span>

<span data-ttu-id="867d2-311">테넌트에서 데이터를 내보내기 위한 고급 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-311">Here’s the high-level process for exporting data from your tenant.</span></span>

1. <span data-ttu-id="867d2-312">Azure Portal로 이동한 후 사용자를 대신하여 내보내기 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-312">Go to the Azure portal and create an export request on behalf of the user.</span></span>
2. <span data-ttu-id="867d2-313">데이터를 내보내고 사용자에게 파일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-313">Export the data and send file to user.</span></span>

###### <a name="to-export-a-users-info-from-an-azure-tenant"></a><span data-ttu-id="867d2-314">Azure 테넌트에서 사용자 정보를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="867d2-314">To export a user’s info from an Azure tenant</span></span>

1. <span data-ttu-id="867d2-315">Azure Portal에서 **모든 서비스**를 선택하고 필터에 *정책*을 입력한 후 **정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-315">Open the Azure portal, select **All services**, type *policy* into the filter, and then select **Policy**.</span></span>

     ![<span data-ttu-id="867d2-316">모든 서비스 필터</span><span class="sxs-lookup"><span data-stu-id="867d2-316">All services filter</span></span> ](media/gdpr-azure-dsr-azure-policy.png)

2. <span data-ttu-id="867d2-317">**정책** 블레이드에서 **사용자 개인 정보**를 선택하고 **사용자 요청 관리**를 선택한 후 **내보내기 요청 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-317">In the **Policy** blade, select **User privacy**, select **Manage User Requests**, and then select **Add export request**.</span></span>

    ![<span data-ttu-id="867d2-318">내보내기 요청 추가</span><span class="sxs-lookup"><span data-stu-id="867d2-318">Add export request</span></span> ](media/gdpr-azure-dsr-azure-add-export-request.png)

3. <span data-ttu-id="867d2-319">다음과 같이 **데이터 내보내기 요청**을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-319">Complete the **Export data request**:</span></span>

    ![새 데이터 내보내기 요청](media/gdpr-azure-dsr-azure-export-data-request.png)

- <span data-ttu-id="867d2-p147">**사용자.** 내보내기를 요청한 Azure Active Directory 사용자의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p147">**User.** Type the email address of the Azure Active Directory user that requested the export.</span></span>
- <span data-ttu-id="867d2-p148">**구독.** 리소스 사용량을 보고하고 서비스 요청을 청구하는 데 사용하는 계정을 선택합니다. Azure Storage 계정의 위치이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p148">**Subscription.** Select the account you use to report resource usage and to bill for services. This is also the location of your Azure storage account.</span></span>
- <span data-ttu-id="867d2-326">**저장소 계정.**</span><span class="sxs-lookup"><span data-stu-id="867d2-326">**Storage account.**</span></span> <span data-ttu-id="867d2-327">Azure 저장소(Blob)의 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-327">Select the location of your Azure Storage (Blob).</span></span> <span data-ttu-id="867d2-328">자세한 내용은 [Microsoft Azure 저장소 소개 — Blob 저장소](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="867d2-328">For more info, see the [Introduction to Microsoft Azure Storage — Blob storage](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage) article.</span></span>
- <span data-ttu-id="867d2-p150">**컨테이너.** 사용자가 내보낸 개인 정보 데이터의 저장소 위치로서, 새 컨테이너를 만들거나 기존 컨테이너를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p150">**Container.** Create a new (or select an existing) container as the storage location for the user’s exported privacy data.</span></span>

4. <span data-ttu-id="867d2-331">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-331">Select **Create**.</span></span>

<span data-ttu-id="867d2-332">내보내기 요청이 **보류 중** 상태로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-332">The export request goes into **Pending** status.</span></span> <span data-ttu-id="867d2-333">**사용자 개인 정보 — 개요** 블레이드에서 보고서 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-333">You can view the report status on the **User privacy — Overview** blade.</span></span>

>[!IMPORTANT]  
><span data-ttu-id="867d2-334">개인 데이터는 여러 시스템에서 가져올 수 있으므로 내보내기 프로세스를 완료하는 데 최대 1개월이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-334">Because personal data can come from multiple systems, it’s possible that the export process might take up to one month to complete.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="867d2-335">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="867d2-335">Service-Specific Interfaces</span></span>

<span data-ttu-id="867d2-p152">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-p152">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="notify-about-exporting-or-deleting-issues"></a><span data-ttu-id="867d2-338">내보내기 또는 삭제 문제에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="867d2-338">Notify about exporting or deleting issues</span></span>

<span data-ttu-id="867d2-339">Azure Portal에서 데이터를 내보내거나 삭제하는 동안 문제가 발생하면 Azure Portal **도움말 + 지원** 블레이드로 이동하여 **등록 관리 > 기타 보안 및 준수 요청 > 개인 정보 보호 블레이드 및 GDPR 요청**에서 새 티켓을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="867d2-339">If you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management > Other Security and Compliance Request > Privacy Blade and GDPR Requests**.</span></span>

## <a name="learn-more"></a><span data-ttu-id="867d2-340">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="867d2-340">Learn more</span></span>

- [<span data-ttu-id="867d2-341">Microsoft 보안 센터</span><span class="sxs-lookup"><span data-stu-id="867d2-341">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)