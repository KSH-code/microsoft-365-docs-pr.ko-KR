---
title: GDPR에 대한 Azure 데이터 주체 요청
description: ''
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: e74c4c96b66a7c21bc46520dbcdeb34898bceaf9
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286083"
---
# <a name="azure-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="feed6-103">GDPR에 대한 Azure 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="feed6-103">Azure Data Subject Requests for the GDPR</span></span>

## <a name="introduction-to-data-subject-requests-dsrs"></a><span data-ttu-id="feed6-104">DSR(데이터 주체 요청) 소개</span><span class="sxs-lookup"><span data-stu-id="feed6-104">Introduction to Data Subject Requests (DSRs)</span></span>

<span data-ttu-id="feed6-p101">EU GDPR(일반 데이터 보호 규정)은 사용자(규정에 *데이터 주체*로 알려짐)에게 고용주 또는 다른 유형의 대리점 및 조직(*데이터 통제자* 또는 단순히 *통제자*로 지칭)이 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 개인 데이터는 GDPR에서는 보다 광범위하게 식별되었거나 식별 가능한 자연인과 관련된 모든 데이터로 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 부여합니다. 이러한 권한에는 개인 데이터 복사본 획득, 수정 요청, 처리 제한, 삭제 또는 다른 통제자에게 이동될 수 있도록 전자 형식으로 수신하는 권한이 포함됩니다. 데이터 주체가 통제자에게 개인 데이터에 대해 조치를 취할 것을 요구하는 공식적인 요청을 *데이터 주체 요청* 또는 DSR이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p101">The EU Data Protection Regulation (GDPR) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR.</span></span>

<span data-ttu-id="feed6-p102">이 가이드에서는 Microsoft 제품, 서비스 및 관리 도구를 사용하여 통제자 고객이 DSR에 응답하기 위해 개인 데이터를 찾고 조치를 취하는 데 도움을 주는 방식을 설명합니다. 특히, Microsoft 클라우드에 있는 개인 데이터를 찾고, 액세스하고, 조치를 취하는 방법도 포함되어 있습니다. 이 가이드에 설명된 프로세스에 대한 간략한 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p102">The guide discusses how to use Microsoft products, services and administrative tools to help our controller customers find and act on personal data to respond to DSRs. Specifically, this includes how to find, access, and act on personal data that reside in the Microsoft cloud. Here’s a quick overview of the processes outlined in this guide:</span></span>

1.  <span data-ttu-id="feed6-p103">***검색***—검색 도구를 사용하여 DSR의 대상이 될 수 있는 고객 데이터를 좀 더 쉽게 찾을 수 있습니다. 잠재적인 반응형 문서가 일단 수집되면 다음 단계에 설명된 DSR 작업 중 하나 이상을 수행하여 요청에 응답할 수 있습니다. 또는 요청이 DSR에 응답하기 위한 조직 지침을 충족하지 않는지도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p103">***Discover***—Use search and discovery tools to more easily find customer data that may be the subject of a DSR. Once potentially responsive documents are collected, you can perform one or more of the DSR actions described in the following steps to respond to the request. Alternatively, you may determine that the request doesn't meet your organization’s guidelines for responding to DSRs.</span></span>

2.  <span data-ttu-id="feed6-115">***액세스***—Microsoft 클라우드에 있는 개인 데이터를 검색하고, 요청될 경우 데이터 주체가 사용할 수 있는 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-115">***Access***—Retrieve personal data that resides in the Microsoft cloud and, if requested, make a copy of it that can be available to the data subject.</span></span>

3.  <span data-ttu-id="feed6-116">***수정***—해당되는 경우 개인 데이터를 변경하거나 요청된 다른 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-116">***Rectify***—Make changes or implement other requested actions on the personal data, where applicable.</span></span>

4.  <span data-ttu-id="feed6-p104">***제한***—가능한 경우 다양한 Azure 서비스에 대한 라이선스를 제거하거나 원하는 서비스를 해제하여 개인 데이터의 처리를 제한합니다. 또한 Microsoft 클라우드에서 데이터를 제거하고 온-프레미스 또는 다른 위치에 유지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p104">***Restrict***—Restrict the processing of personal data, either by removing licenses for various Azure services or turning off the desired services where possible. You can also remove data from the Microsoft cloud and retain it on-premises or at another location.</span></span>

5.  <span data-ttu-id="feed6-119">***삭제***Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-119">***Delete***—Permanently remove personal data that resided in the Microsoft cloud.</span></span>

6.  <span data-ttu-id="feed6-120">***내보내기***—개인 데이터의 전자 사본(컴퓨터가 읽을 수 있는 형식)을 데이터 주체에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-120">***Export***—Provide an electronic copy (in a machine-readable format) of personal data to the data subject.</span></span>

<span data-ttu-id="feed6-121">이 가이드의 각 섹션에서는 데이터 통제자가 Microsoft 클라우드의 개인 데이터에 대한 DSR에 응답하기 위해 수행할 수 있는 기술적 절차를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-121">Each section in this guide outlines the technical procedures that a data controller organization can take to respond to a DSR for personal data in the Microsoft cloud.</span></span>

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>
### <a name="terminology"></a><span data-ttu-id="feed6-122">용어</span><span class="sxs-lookup"><span data-stu-id="feed6-122">Terminology</span></span>

<span data-ttu-id="feed6-123">다음은 이 가이드와 관련된 용어의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-123">The following provides definitions of terms that are relevant to this guide.</span></span>

-   <span data-ttu-id="feed6-124">*통제자*—단독으로 또는 다른 대상과 함께 개인 데이터 처리의 목적 및 방법을 결정하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다. 이러한 처리의 목적 및 방법을 연합국 법률 또는 회원국 법률에 따라 결정하는 경우, 통제자 또는 구체적인 지명 기준을 연합국 법률 또는 회원국 법률에서 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-124">*Controller*—The natural or legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data; where the purposes and means of such processing are determined by Union or Member State law, the controller or the specific criteria for its nomination may be provided for by Union or Member State law.</span></span>

-   <span data-ttu-id="feed6-125">*개인 데이터* 및 *데이터 주체*—식별되었거나 식별 가능한 자연인(‘데이터 주체’)과 관련된 모든 정보입니다. 식별 가능한 자연인은 직간접적으로, 특히 이름, 식별 번호, 위치 데이터, 온라인 식별자 또는 해당 자연인의 신체적, 생리적, 유전적, 정신적, 경제적, 문화적 또는 사회적 ID와 같은 식별자를 참조하여 식별될 수 있는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-125">*Personal data* and *data subject*—Any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person.</span></span>

-   <span data-ttu-id="feed6-126">*프로세서*—통제자를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-126">*Processor*—A natural or legal person, public authority, agency or other body which processes personal data on behalf of the controller.</span></span>

-   <span data-ttu-id="feed6-p105">*고객 데이터*—엔터프라이즈 서비스를 사용하여 고객이 또는 고객을 대신해서 Microsoft에 제공되는 모든 텍스트, 사운드, 비디오 또는 이미지 파일, 소프트웨어를 포함하는 모든 데이터입니다. 고객 데이터에는 (1) 최종 사용자의 식별 가능 정보(예: 사용자 이름 및 Azure Active Directory의 연락처 정보) 및 고객이 특정 서비스에서 업로드하거나 만든 고객 콘텐츠(예: Azure Storage의 고객 콘텐츠, Azure SQL Database의 고객 콘텐츠 또는 Azure Virtual Machines의 고객 가상 머신 이미지)가 둘 다 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p105">*Customer Data*—All data, including all text, sound, video, or image files, and software, that are provided to Microsoft by, or on behalf of, a customer through use of the enterprise service. Customer Data includes both (1) identifiable information of end users (e.g., user names and contact information in Azure Active Directory) and Customer Content that a customer uploads into or creates in specific services (e.g., customer content in an Azure Storage account, customer content of an Azure SQL Database, or a customer’s virtual machine image in Azure Virtual Machines).</span></span>

-   <span data-ttu-id="feed6-p106">*시스템 생성 로그*—Microsoft가 사용자에게 엔터프라이즈 서비스를 제공하는 데 도움을 주는 Microsoft 생성 로그 및 관련 데이터입니다. 시스템 생성 로그에는 일반적으로 자체적으로는 개인을 식별할 수 없지만 사용자에게 엔터프라이즈 서비스를 전달하는 데 사용되는 시스템 생성 번호에 해당하는 주로 필명화된 데이터(예: 고유 식별자)가 포함됩니다. 최종 사용자에 대한 식별 가능 정보(예: 사용자 이름)도 시스템 생성 로그에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p106">*System-Generated Logs*—Logs and related data generated by Microsoft that help Microsoft provide enterprise services to users. System-generated logs contain primarily pseudonymized data, such as unique identifiers – typically a number generated by the system that cannot on its own identify an individual person but is used to deliver the enterprise services to users. System-generated logs may also contain identifiable information about end users, such as a user name.</span></span>

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="feed6-132">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="feed6-132">How to use this guide</span></span>

<span data-ttu-id="feed6-133">이 가이드의 다음 두 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-133">This guide consists of two parts:</span></span>

<span data-ttu-id="feed6-p107">**1부: 고객 데이터에 대한 데이터 주체 요청에 응답** — 이 가이드 1부에서는 데이터를 작성한 애플리케이션에서 데이터를 액세스, 수정, 제한, 삭제 및 내보내는 방법을 설명합니다. 이 섹션에서는 최종 사용자의 고객 콘텐츠 및 식별 가능 정보에 대해 DSR을 실행하는 방법을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p107">**Part 1: Responding to Data Subject Requests for Customer Data** — Part 1 of this guide discusses how to access, rectify, restrict, delete, and export data from applications in which you have authored data. This section details how to execute DSRs against both Customer Content and also identifiable information of end users.</span></span>

<span data-ttu-id="feed6-p108">**2부: 시스템 생성 로그에 대한 데이터 주 체 요청에 응답** — Microsoft의 엔터프라이즈 서비스를 사용할 경우, Microsoft는 서비스를 제공하기 위해 시스템 생성 로그라고 하는 정보를 생성합니다. 이 가이드의 2부에서는 Azure에서 이러한 정보를 액세스, 삭제 및 내보내는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p108">**Part 2: Responding to Data Subject Requests for System-Generated Logs** — When you use Microsoft’s enterprise services, Microsoft generates some information, known as System-Generated Logs, in order to provide the service. Part 2 of this guide discusses how to access, delete and export such information for Azure.</span></span>

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a><span data-ttu-id="feed6-138">Azure Active Directory 및 Microsoft 서비스 계정에 대한 DSR 이해</span><span class="sxs-lookup"><span data-stu-id="feed6-138">Understanding DSRs for Azure Active Directory and Microsoft Service Accounts</span></span>

<span data-ttu-id="feed6-p109">엔터프라이즈 고객에게 제공되는 서비스를 고려할 때, DSR의 실행은 항상 특정 AAD(Azure Active Directory) 테넌트의 컨텍스트 내에서 이해할 수 있어야 합니다. 특히 DSR은 항상 지정된 AAD 테넌트 내에서 실행됩니다. 사용자가 여러 테넌트에 참여하는 경우, 지정된 DSR이 *반드시* 요청이 수신된 특정 테넌트의 컨텍스트 내에서 실행된다는 점을 강조해서 알려주는 것이 중요합니다. 이러한 정보는 한 엔터프라이즈 고객의 DSR 실행이 인접 엔터프라이즈 고객의 데이터에 영향을 미치지 **않는다는 것**을 의미하므로 반드시 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p109">When considering services provided to enterprise customers, execution of DSRs must always be understood within the context of a specific Azure Active Directory (AAD) tenant. Notably, DSRs are always executed within a given AAD tenant. If a user is participating in multiple tenants, it is important to emphasize that a given DSR is *only* executed within the context of the specific tenant the request was received within. This is critical to understand as it means the execution of a DSR by one enterprise customer **will not** impact the data of an adjacent enterprise customer.</span></span>

<span data-ttu-id="feed6-p110">엔터프라이즈 고객에게 제공되는 서비스 컨텍스트 내의 MSA(Microsoft 서비스 계정)도 마찬가지입니다. *AAD 테넌트와 연결된* MSA 계정에 대해 DSR을 실행할 경우 해당 테넌트 내의 데이터 **와만 관련됩니다**. 또한 테넌트 내에서 MSA 계정을 처리하는 경우에는 다음 사실을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p110">The same also applies for Microsoft Service Accounts (MSA) within the context of services provided to an enterprise customer: execution of a DSR against an MSA account *associated with an AAD tenant* **will only** pertain to data within the tenant. In addition, it is important to understand the following when handling MSA accounts within a tenant:</span></span>

-   <span data-ttu-id="feed6-p111">MSA 사용자가 Azure 구독을 만들면 구독은 마치 AAD 테넌트인 것처럼 처리됩니다. 결과적으로 DSR은 위에 설명된 것처럼 테넌트 내로 한정됩니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p111">If an MSA user creates an Azure subscription, the subscription will be handled as if it were an AAD tenant. Consequently, DSRs are scoped within the tenant as described above.</span></span>

-   <span data-ttu-id="feed6-p112">MSA 계정을 통해 만든 Azure 구독을 삭제한 경우 실제 MSA 계정에는 **영향을 주지 않습니다**. 다시 말해서 위에서 언급한 것처럼 Azure 구독 내에서 실행되는 DSR은 테넌트 범위로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p112">If an Azure subscription created via an MSA account is deleted, **it will not affect** the actual MSA account. Again, as noted above, DSRs executing within the Azure subscription are limited to the scope of the tenant itself.</span></span>

<span data-ttu-id="feed6-p113">**지정된 테넌트의 외부에 있는** MSA 계정 자체에 대한 DSR은 소비자 개인 정보 보호 대시보드를 통해 실행됩니다. 자세한 내용은 Windows 데이터 주체 요청 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="feed6-p113">DSRs against an MSA account itself, **outside a given tenant**, are executed via the Consumer Privacy Dashboard. Please refer to the Windows Data Subject Request Guide for further details.</span></span>

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a><span data-ttu-id="feed6-151">1부: 고객 데이터에 대한 DSR 가이드</span><span class="sxs-lookup"><span data-stu-id="feed6-151">Part 1: DSR Guide for Customer Data</span></span>

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

## <a name="executing-dsrs-against-customer-data"></a><span data-ttu-id="feed6-152">고객 데이터에 대해 DSR 실행</span><span class="sxs-lookup"><span data-stu-id="feed6-152">Executing DSRs against Customer Data</span></span>

<span data-ttu-id="feed6-p114">Microsoft는 Azure Portal을 통해 또는 특정 서비스에 대한 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접(*제품 내 환경*) 특정 고객 데이터를 액세스, 삭제 및 내보내는 기능을 제공합니다. 제품 내 환경에 대한 자세한 내용은 해당 서비스 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p114">Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as *in-product experiences*). Details regarding such in-product experiences are described in the respective services’ reference documentation.</span></span>

><span data-ttu-id="feed6-155">[중요]</span><span class="sxs-lookup"><span data-stu-id="feed6-155">[Important]</span></span>  
> <span data-ttu-id="feed6-p115">제품 내 DSR을 지원하는 서비스에서는 서비스의 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 직접적으로 사용하고 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명해야 합니다. 따라서 지정된 데이터 주체에 대한 모든 요청을 완료하기 위해서는 Azure Portal 내의 DSR 외에도 지정된 서비스 내의 DSR도 실행해야 합니다. 자세한 내용은 특정 서비스 참조 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="feed6-p115">Services supporting in-product DSRs require direct usage of the service’s application programming interface (API) or user interface (UI), describing applicable CRUD (create, read, update, delete) operations. Consequently, execution of DSRs within a given service must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services’ reference documentation for further details.</span></span>

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-1-discover"></a><span data-ttu-id="feed6-159">1단계: 검색</span><span class="sxs-lookup"><span data-stu-id="feed6-159">Step 1: Discover</span></span>

<span data-ttu-id="feed6-p116">DSR에 응답하는 첫 번째 단계는 요청의 대상인 개인 데이터를 찾는 것입니다. 첫 번째 단계인 문제의 개인 데이터 찾기 및 검토 작업은 DSR이 DSR 적용 또는 거부에 대한 조직 요건을 충족하는지 여부를 결정하는 데 도움이 됩니다. 예를 들어, 문제의 개인 데이터를 찾아서 검토한 후에는 요청이 조직 요건을 충족하지 않는지 판단할 수 있습니다. 조직 요건을 충족하지 못하면 타인의 권리와 자유에 부정적인 영향을 미칠 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p116">The first step in responding to a DSR is to find the personal data that is the subject of the request. This first step - finding and reviewing the personal data at issue - will help you determine whether a DSR meets your organization's requirements for honoring or declining a DSR. For example, after finding and reviewing the personal data at issue, you may determine the request doesn’t meet your organization’s requirements because doing so may adversely affect the rights and freedoms of others.</span></span>

<span data-ttu-id="feed6-163">데이터를 찾은 후에 데이터 주체의 요청을 충족하기 위한 특정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-163">After you find the data, you can then perform the specific action to satisfy the request by the data subject.</span></span>

<span id="_Toc511384807" class="anchor"><span id="_Toc511163878" class="anchor"><span id="_Toc511136235" class="anchor"><span id="_Toc511125168" class="anchor"><span id="_Toc511120755" class="anchor"><span id="_Toc511122662" class="anchor"></span></span></span></span></span></span>
### <a name="azure-active-directory"></a><span data-ttu-id="feed6-164">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="feed6-164">Azure Active Directory</span></span>

<span data-ttu-id="feed6-p117">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/)는 Microsoft의 클라우드 기반, 다중 테넌트 디렉터리 및 ID 관리 서비스입니다. [Azure Portal](https://portal.azure.com/)을 사용하여 [AAD(Azure Active Directory)](https://azure.microsoft.com/services/active-directory/) 환경에서 개인 데이터를 포함하는 고객 및 직원 사용자 프로필, 사용자 작업 정보와 같은 최종 사용자의 식별 가능한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p117">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) is Microsoft’s cloud-based, multi-tenant directory and identity management service. You can locate identifiable information of end users, such as customer and employee user profiles and user work information that contain personal data in your [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) environment by using the [Azure portal](https://portal.azure.com/).</span></span>

<span data-ttu-id="feed6-p118">이 서비스는 특정 사용자에 대한 개인 데이터를 찾거나 변경하려는 경우에 특히 유용합니다. 사용자 프로필과 작업 정보를 추가하거나 변경할 수도 있습니다. 디렉터리에 대한 전역 관리자인 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p118">This is particularly helpful if you want to find or change personal data for a specific user. You can also add or change user profile and work information. You must sign in with an account that’s a global admin for the directory.</span></span>

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a><span data-ttu-id="feed6-170">사용자 프로필 및 회사 정보를 찾아서 보려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="feed6-170">How do I locate or view user profile and work information?</span></span>

1. <span data-ttu-id="feed6-171">디렉터리에 대한 전역 관리자인 계정을 사용하여 [Azure Portal](https://portal.azure.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-171">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

1. <span data-ttu-id="feed6-172">**모든 서비스**를 선택하고 텍스트 상자에 **사용자 및 그룹**을 입력한 후 **Enter** 키를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-172">Select **All services**, enter **Users and groups** in the text box, and then select **Enter**.</span></span>

     ![모든 서비스 선택](media/azure-dsr_image3.png)

3. <span data-ttu-id="feed6-174">**사용자 및 그룹** 블레이드에서 **사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-174">On the **Users and groups** blade, select **Users**.</span></span>

     ![사용자 선택](media/azure-dsr_image9.png)

4.  <span data-ttu-id="feed6-176">**사용자 및 그룹 - 사용자** 블레이드의 목록에서 사용자를 선택하고, 선택한 사용자에 대한 블레이드에서 **프로필**을 선택하여 개인 데이터가 포함될 수 있는 사용자 프로필 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-176">On the **Users and groups - Users** blade, select a user from the list, and then, on the blade for the selected user, select **Profile** to view user profile information that might contain personal data.</span></span>

    ![프로필 선택](media/azure-dsr_image5.png)

5. <span data-ttu-id="feed6-178">사용자 프로필 정보를 추가하거나 변경해야 할 경우 이 작업을 수행한 후 명령 모음에서 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-178">If you need to add or change user profile information, you can do so, and then, in the command bar, select **Save.**</span></span>

<!-- steps 6 and 7 not in original 
6. On the blade for the selected user, select **Work Info** to view user work information that may contain personal data.

     ![Select work info](media/azure-dsr_image11.png)

7. If you need to add or change user work information, you can do so, and then, in the command bar, select **Save.**

end of text to isolate -->

<span id="_Toc511384808" class="anchor"><span id="_Toc511163879" class="anchor"><span id="_Toc511136236" class="anchor"><span id="_Toc511125169" class="anchor"><span id="_Toc511120756" class="anchor"><span id="_Toc511122663" class="anchor"></span></span></span></span></span></span>

### <a name="service-specific-interfaces"></a><span data-ttu-id="feed6-179">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="feed6-179">Service-Specific Interfaces</span></span>

<span data-ttu-id="feed6-p119">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p119">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Access" class="anchor"><span id="_Toc508792512" class="anchor"><span id="_Ref511119401" class="anchor"><span id="_Toc511122664" class="anchor"><span id="_Toc511120757" class="anchor"><span id="_Toc511125170" class="anchor"><span id="_Toc511136237" class="anchor"><span id="_Toc511163880" class="anchor"><span id="_Toc511384809" class="anchor"><span id="_Hlk503968195" class="anchor"></span></span></span></span></span></span></span></span></span></span>
## <a name="step-2-access"></a><span data-ttu-id="feed6-182">2단계: 액세스</span><span class="sxs-lookup"><span data-stu-id="feed6-182">Step 2: Access</span></span>

<span data-ttu-id="feed6-p120">DSR에 응답하는 개인 데이터가 포함된 고객 데이터를 찾은 후에 귀하와 조직은 데이터 주체에게 제공할 데이터를 결정해야 합니다. 실제 문서의 사본, 적절히 수정된 버전 또는 공유할 수 있는 부분의 스크린샷을 제공할 수 있습니다. 액세스 요청에 대한 이러한 각 응답에 대해, 응답 데이터를 포함하는 문서 또는 기타 항목 사본을 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p120">After you’ve found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.</span></span>

<span data-ttu-id="feed6-186">데이터 주체에 사본을 제공할 때는 다른 데이터 주체에 대한 개인 정보와 모든 기밀 정보를 제거하거나 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-186">When providing a copy to the data subject, you may have to remove or redact personal information about other data subjects and any confidential information.</span></span>

<span data-ttu-id="feed6-187"><span id="_Using_Content_Search_1" class="anchor"></span>다음은 DSR 액세스 요청에 대한 응답으로 데이터 복사본을 다운로드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-187"><span id="_Using_Content_Search_1" class="anchor"></span>The following explains how to get a copy of data in response to a DSR access request.</span></span>

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="azure-active-directory"></a><span data-ttu-id="feed6-188">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="feed6-188">Azure Active Directory</span></span>

<span data-ttu-id="feed6-p121"><span id="_Forms_1" class="anchor"></span>Microsoft에서는 엔터프라이즈 고객의 테넌트 관리자에게 DSR 액세스 요청을 관리할 수 있는 기능을 제공하는 포털 및 제품 환경을 둘 다 제공합니다. DSR 액세스 요청은 (a) 최종 사용자에 대한 식별 정보와 (b) 시스템 생성 로그를 포함하여 사용자의 개인 데이터에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p121"><span id="_Forms_1" class="anchor"></span>Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage DSR access requests. DSR Access requests allow for access of the personal data of the user, including: (a) identifiable information about an end-user and (b) system-generated logs.</span></span>

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a><span data-ttu-id="feed6-191">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="feed6-191">Service-Specific Interfaces</span></span>

<span data-ttu-id="feed6-p122">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p122">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-3-rectify"></a><span data-ttu-id="feed6-194">3단계: 수정</span><span class="sxs-lookup"><span data-stu-id="feed6-194">Step 3: Rectify</span></span>

<span data-ttu-id="feed6-p123">데이터 주체가 조직 데이터에 포함된 개인 데이터를 수정할 것을 요청한 경우 귀하와 조직은 요청을 수락하는 것이 적절한지 여부를 결정해야 합니다. 데이터 수정에는 개인 데이터의 편집, 수정 또는 문서나 기타 형식 또는 항목에서 개인 데이터를 제거하는 것과 같은 작업이 포함될 수 있습니다. Microsoft 고객 지원 및 FastTrack 데이터에 대해 이 작업을 수행하는 가장 편리한 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p123">If a data subject has asked you to rectify the personal data that resides in your organization’s data, you and your organization will have to determine whether it’s appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item. The most expedient way to do this for Microsoft Support and FastTrack data is provided below.</span></span>

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>
### <a name="azure-active-directory"></a><span data-ttu-id="feed6-198">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="feed6-198">Azure Active Directory</span></span>

<span data-ttu-id="feed6-p124">엔터프라이즈 고객은 지정된 Microsoft 서비스의 특성에 따른 제한된 편집 기능을 비롯하여, DSR을 관리하여 요청을 수정하는 기능이 있습니다. 데이터 처리자의 역할을 하는 Microsoft는 Microsoft 서비스 내에서 실제 활동을 반영하고 이벤트의 기록 레코드를 구성하는 시스템 생성 로그를 수정하는 것을 허용하지 않습니다. 아래에 자세히 설명된 것처럼, Azure Active Directory에는 최종 사용자에 대한 식별 가능 정보를 수정할 수 있는 제한된 편집 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p124">Enterprise customers have the ability to manage DSR rectify requests, including limited editing features per the nature of a given Microsoft service. As a data processor, Microsoft does not offer the ability to correct system-generated logs as it reflects factual activities and constitutes a historical record of events within Microsoft services. With respect to Azure Active Directory, limited editing features exist to rectify identifiable information about an end-user, as described further below.</span></span>

#### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a><span data-ttu-id="feed6-202">Azure Active Directory: 부정확하거나 불완전한 개인 데이터의 수정</span><span class="sxs-lookup"><span data-stu-id="feed6-202">Azure Active Directory: rectify/correct inaccurate or incomplete personal data</span></span>

<span data-ttu-id="feed6-p125">[Azure Portal](https://portal.azure.com/)을 사용하여 [AAD(Azure Active Directory)](https://azure.microsoft.com/services/active-directory/) 환경에서 개인 데이터(예: 사용자 이름, 직책, 주소 또는 전화 번호)를 포함하는 고객 및 직원 사용자 프로필, 사용자 작업 정보와 같은 최종 사용자에 대한 식별 가능 정보를 수정, 업데이트 또는 삭제할 수 있습니다. 디렉터리에 대해 전역 관리자에 해당하는 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p125">You can correct, update, or delete identifiable information about end users, such as customer and employee user profiles and user work information that contain personal data, such as a user’s name, work title, address, or phone number, in your [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) environment by using the [Azure portal](https://portal.azure.com/). You must sign in with an account that’s a global admin for the directory.</span></span>

##### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a><span data-ttu-id="feed6-205">Azure Active Directory에서 사용자 프로필 및 작업 정보를 수저하거나 업데이트하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="feed6-205">How do I correct or update user profile and work information in Azure Active Directory?</span></span>

1.  <span data-ttu-id="feed6-206">디렉터리에 대한 전역 관리자인 계정을 사용하여 [Azure Portal](https://portal.azure.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-206">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

2.  <span data-ttu-id="feed6-207">**모든 서비스**를 선택하고 텍스트 상자에 **사용자 및 그룹**을 입력한 후 **Enter** 키를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-207">Select **All services**, enter **Users and groups** in the text box, and then select **Enter**.</span></span>

    ![모든 서비스 선택](media/azure-dsr_image3.png)

3.  <span data-ttu-id="feed6-209">**사용자 및 그룹** 블레이드에서 **사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-209">On the **Users and groups** blade, select **Users**.</span></span>
         
    ![사용자 선택](media/azure-dsr_image9.png)

4.  <span data-ttu-id="feed6-211">**사용자 및 그룹 - 사용자** 블레이드의 목록에서 사용자를 선택하고, 선택한 사용자에 대한 블레이드에서 **프로필**을 선택하여 수정하거나 업데이트해야 하는 사용자 프로필 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-211">On the **Users and groups - Users** blade, select a user from the list, and then, on the blade for the selected user, select **Profile** to view the user profile information that needs to be corrected or updated.</span></span>

    ![프로필 선택](media/azure-dsr_image5.png)

5.  <span data-ttu-id="feed6-213">해당 정보를 수정하거나 업데이트한 다음, 명령 모음에서 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-213">Correct or update the information, and then, in the command bar, select **Save.**</span></span>

6.  <span data-ttu-id="feed6-214">선택한 사용자의 블레이드에서 **작업 정보**를 선택하여 수정하거나 업데이트해야 하는 사용자 작업 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-214">On the blade for the selected user, select **Work Info** to view user work information that needs to be corrected or updated.</span></span>

    ![작업 정보 선택](media/azure-dsr_image4.png)

7.  <span data-ttu-id="feed6-216">사용자 작업 정보를 수정하거나 업데이트한 다음, 명령 모음에서 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-216">Correct or update the user work information, and then, in the command bar, select **Save.**</span></span>

<span id="_Toc511384814" class="anchor"><span id="_Toc511163885" class="anchor"><span id="_Toc511136242" class="anchor"><span id="_Toc511125175" class="anchor"><span id="_Toc511120762" class="anchor"><span id="_Toc511122669" class="anchor"></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a><span data-ttu-id="feed6-217">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="feed6-217">Service-Specific Interfaces</span></span>

<span data-ttu-id="feed6-p126">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p126">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Gain_access_to" class="anchor"><span id="_Toc508792521" class="anchor"><span id="_Toc511122670" class="anchor"><span id="_Toc511120763" class="anchor"><span id="_Toc511125176" class="anchor"><span id="_Toc511136243" class="anchor"><span id="_Toc511163886" class="anchor"><span id="_Toc511384815" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-4-restrict"></a><span data-ttu-id="feed6-220">4단계: 제한</span><span class="sxs-lookup"><span data-stu-id="feed6-220">Step 4: Restrict</span></span>

<span data-ttu-id="feed6-p127"><span id="_Delete" class="anchor"></span>데이터 주체는 개인 데이터 처리를 제한할 것을 요청할 수 있습니다. Microsoft는 Azure Portal과 기존의 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 둘 다 제공합니다. 이러한 환경은 엔터프라이즈 고객의 테넌트 관리자가 데이터 내보내기 및 데이터 삭제를 조합하여 이러한 DSR을 관리할 수 있도록 합니다. 고객은 (a) 계정, (b) 시스템 생성 로그 및 (c) 관련 로그를 포함하는 (1) 사용자 개인의 전자 사본을 내보내고 (2) Microsoft 시스템 내에 있는 계정 및 관련 데이터를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p127"><span id="_Delete" class="anchor"></span>Data subjects may request that you restrict processing of their personal data. We provide both the Azure Portal and pre-existing application programming interfaces (APIs) or user interfaces (UIs). These experiences provide the enterprise customer’s tenant administrator the capability to manage such DSRs through a combination of data export and data deletion. A customer may (1) export an electronic copy of the personal data of the user, including (a) account(s), (b) system-generated logs, and (c) associated logs, followed with (2) deletion of the account and associated data residing within Microsoft systems.</span></span>

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
## <a name="step-5-delete"></a><span data-ttu-id="feed6-225">5단계: 삭제</span><span class="sxs-lookup"><span data-stu-id="feed6-225">Step 5: Delete</span></span>

<span data-ttu-id="feed6-p128">조직의 고객 데이터에서 개인 데이터를 제거하는 "지우기 권리"는 GDPR의 핵심 보호 기능입니다. 개인 데이터 제거에는 감사 로그 정보를 제외한 모든 개인 데이터 및 시스템 생성 로그의 제거가 포함됩니다. 사용자가 **일시적으로 삭제**되면(아래의 세부 정보 참조) 계정을 30일 동안 사용할 수 없게 됩니다. 이 30일 기간 동안 추가 작업이 수행되지 않으면 사용자는 **영구적으로 삭제**됩니다(아래의 세부 정보 참조). **영구 삭제** 시, 사용자 계정, 개인 데이터 및 시스템 생성 로그는 그 다음 30일 이내에 지워집니다. 테넌트 관리자가 즉시 **영구 삭제**를 수행하면 사용자 계정, 개인 데이터 및 시스템 생성 로그가 발급 후 30일 이내에 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p128">The “right to erasure” by the removal of personal data from an organization’s Customer Data is a key protection in the GDPR. Removing personal data includes removing all personal data and system-generated logs, except audit log information. When a user is **soft deleted** (see details below), the account is disabled for 30 days. If no further action is taken during this 30 day period, the user is **permanently deleted** (again, see details below). Upon a **permanent delete**, the user’s account, personal data, and system-generated logs are expunged within an additional 30 days. If a tenant admin immediately issues a **permanent delete**, the user’s account, personal data, and system-generated logs are expunged within 30 days of issuance.</span></span>

><span data-ttu-id="feed6-232">[중요] 테넌트에서 사용자를 삭제하려면 테넌트 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-232">[Important] You must be a tenant administrator to delete a user from the tenant.</span></span>

<span id="_Toc511384817" class="anchor"><span id="_Toc511163888" class="anchor"><span id="_Toc511136245" class="anchor"><span id="_Toc511125178" class="anchor"><span id="_Toc511120765" class="anchor"><span id="_Toc511122672" class="anchor"><span id="_Ref511119801" class="anchor"></span></span></span></span></span></span></span>

### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a><span data-ttu-id="feed6-233">Azure Portal을 통해 사용자 및 관련 데이터 삭제</span><span class="sxs-lookup"><span data-stu-id="feed6-233">Delete a user and associated data through the Azure portal</span></span>

<span data-ttu-id="feed6-234">데이터 주체에 대한 삭제 요청을 수신한 후에 Azure Portal을 사용하여 시스템 생성 로그 뿐만 아니라 사용자 및 관련 개인 정보를 둘 다 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-234">After you receive a delete request for a data subject, you can use the Azure portal to delete both a user and the associated personal information as well as system-generated logs.</span></span>

<span data-ttu-id="feed6-p129">이 데이터를 삭제한다는 것은 테넌트에서 사용자를 삭제하는 것을 의미합니다. 사용자는 처음에 일시적으로 삭제됩니다. 즉, 일시 삭제용으로 표시되고 30일 이내에 테넌트 관리자가 계정을 복구할 수 있습니다. 30일 후에 해당 계정은 테넌트에서 자동으로 영구 삭제됩니다. 해당 30일 이전에는 휴지통에서 일시 삭제된 사용자를 수동으로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p129">Deleting this data also means deleting the user from the tenant. Users are initially soft-deleted, which means the account can be recovered by a tenant admin within 30 days of being marked for soft-delete. After 30 days, the account is automatically, and permanently, deleted from the tenant. Prior to that 30 days, you can manually delete a soft-deleted user from the recycle bin.</span></span>

<span data-ttu-id="feed6-239">테넌트에서 사용자를 삭제하기 위한 고급 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-239">Here’s the high-level process for deleting users from your tenant.</span></span>

1.  <span data-ttu-id="feed6-240">Azure Portal로 이동한 후 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-240">Go to the Azure portal and locate the user.</span></span>

2.  <span data-ttu-id="feed6-p130">사용자를 삭제합니다. 처음에 사용자를 삭제하면 사용자의 계정이 휴지통으로 전송됩니다. **이때 사용자는 일시적으로 삭제됩니다. 즉, 계정은 사용되지 않도록 설정되지만 Azure Active Directory에서 지워지지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="feed6-p130">Delete the user. When you initially delete the user, the user’s account is sent to the Recycle Bin. **At this point, the user is soft deleted, meaning the account is disabled, but not expunged from Azure Active Directory.**</span></span>

3.  <span data-ttu-id="feed6-p131">최근에 삭제된 사용자 목록으로 이동한 다음, 사용자를 영구적으로 삭제합니다. **이때 사용자는 영구적으로 삭제됩니다. 즉, 계정이 Azure Active Directory에서 지워진 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="feed6-p131">Go to the Recently deleted users list and permanently delete the user. **At this point the user is permanently deleted (also known as hard deleted), meaning the account has been expunged from Azure Active Directory**</span></span>

##### <a name="to-delete-a-user-from-an-azure-tenant"></a><span data-ttu-id="feed6-246">Azure 테넌트에서 사용자를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="feed6-246">To delete a user from an Azure tenant</span></span>

1.  <span data-ttu-id="feed6-247">Azure Portal을 열고 **Azure Active Directory** 블레이드를 선택한 다음, **사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-247">Open the Azure portal, select the **Azure Active Directory** blade, and then select **Users**.</span></span>

    <span data-ttu-id="feed6-248">**사용자 - 모든 사용자** 블레이드가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-248">The **Users – All users** blade appears.</span></span>

    ![사용자 찾기](media/azure-dsr_image8.png)

2.  <span data-ttu-id="feed6-250">삭제하려는 사용자 옆의 확인란을 선택하고 **사용자 삭제**를 선택한 후 사용자를 삭제할 것인지 묻는 상자에서 **예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-250">Check the box next to the user you want to delete, select **Delete user**, and then select **Yes** in the box asking if you want to delete the user.</span></span>

    ![사용자 관리](media/azure-dsr_image9.png)

3.  <span data-ttu-id="feed6-252">**표시** 드롭다운 상자에서 **최근에 삭제된 사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-252">In the **Show** drop-down box, select **Recently deleted users**.</span></span>

    ![사용자 프로필 보기](media/azure-dsr_image10.png)

4.  <span data-ttu-id="feed6-254">같은 사용자를 다시 선택하고 **영구적으로 삭제**를 선택한 후 확실히 삭제할 것인지 묻는 상자에서 **예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-254">Select the same user again, select **Delete permanently**, and then select **Yes** in the box asking if you’re sure.</span></span>

><span data-ttu-id="feed6-255">[중요]</span><span class="sxs-lookup"><span data-stu-id="feed6-255">[Important]</span></span>  
><span data-ttu-id="feed6-p132">**예**를 클릭하면 사용자 및 모든 관련 데이터와 시스템 생성 로그가 영구적으로 삭제됩니다. 실수로 이렇게 삭제한 경우에는 수동으로 사용자를 테넌트에 다시 추가해야 합니다. 관련된 데이터 및 시스템 생성 로그는 복구 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p132">Be aware that by clicking **Yes** you are permanently, and irrevocably, deleting the user and all associated data and system-generated logs. If you do this by mistake, you’ll have to manually add the user back to the tenant. The associated data and system-generated logs are non-recoverable.</span></span>

   ![사용자 작업 정보 보기](media/azure-dsr_image11.png)

<span id="_Export" class="anchor"><span id="_Step_6:_Export" class="anchor"><span id="_Toc511116629" class="anchor"><span id="_Toc511122673" class="anchor"><span id="_Toc511120766" class="anchor"><span id="_Toc511125179" class="anchor"><span id="_Toc511136246" class="anchor"><span id="_Toc511163889" class="anchor"><span id="_Toc508792534" class="anchor"></span></span></span></span></span></span></span></span></span>

### <a name="service-specific-interfaces"></a><span data-ttu-id="feed6-260">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="feed6-260">Service-Specific Interfaces</span></span>

<span data-ttu-id="feed6-p133">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p133">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Toc511384819" class="anchor"><span id="_Toc511163890" class="anchor"><span id="_Toc511136247" class="anchor"><span id="_Toc511125180" class="anchor"><span id="_Toc511120767" class="anchor"><span id="_Toc511122674" class="anchor"></span></span></span></span></span></span>
## <a name="step-6-export"></a><span data-ttu-id="feed6-263">6단계: 내보내기</span><span class="sxs-lookup"><span data-stu-id="feed6-263">Step 6: Export</span></span>

<span data-ttu-id="feed6-p134"><span id="_Power_BI_2" class="anchor"></span>"데이터 이동성 권리"를 통해 데이터 주체는 다른 데이터 통제자에게 전송될 수 있는 개인 데이터 사본을 전자 형식(즉, “구조화되고, 일반적으로 사용되며 컴퓨터가 읽을 수 있는 상호 운용 가능한 형식”)으로 요청할 수 있습니다. Azure에서는 조직이 지정된 Azure Storage 컨테이너에 네이티브 JSON 형식의 데이터를 내보낼 수 있도록 하여 이러한 권리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p134"><span id="_Power_BI_2" class="anchor"></span>The “right of data portability” allows a data subject to request a copy of their personal data in an electronic format (that’s a “structured, commonly used, machine read-able and interoperable format”) that may be transmitted to another data controller. Azure supports this by enabling your organization to export the data in the native JSON format, to your specified Azure Storage Container.</span></span>

><span data-ttu-id="feed6-266">[중요] 테넌트에서 사용자 데이터를 내보내려면 테넌트 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-266">[Important] You must be a tenant administrator to export user data from the tenant.</span></span>

<span id="_Toc511384820" class="anchor"><span id="_Toc511163891" class="anchor"><span id="_Toc511136248" class="anchor"><span id="_Toc511125181" class="anchor"><span id="_Toc511120768" class="anchor"><span id="_Toc511122675" class="anchor"><span id="_Ref511119875" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a><span data-ttu-id="feed6-267">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="feed6-267">Azure Active Directory</span></span>

<span data-ttu-id="feed6-268">고객 데이터와 관련해서, Microsoft는 엔터프라이즈 고객의 테넌트 관리자에게 최종 사용자에 대한 식별 가능 정보의 내보내기 요청을 관리하는 기능을 지원하는 포털 및 제품 내 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-268">With respect to Customer Data, Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage export requests for identifiable information about an end-user.</span></span>

<span id="_Toc511384821" class="anchor"><span id="_Toc511163892" class="anchor"></span></span>
### <a name="service-specific-interfaces"></a><span data-ttu-id="feed6-269">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="feed6-269">Service-Specific Interfaces</span></span>

<span data-ttu-id="feed6-p135">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p135">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a><span data-ttu-id="feed6-272">2부: 시스템 생성 로그</span><span class="sxs-lookup"><span data-stu-id="feed6-272">Part 2: System-Generated Logs</span></span>


<span data-ttu-id="feed6-273">또한 Microsoft는 Azure의 사용자 사용과 관련된 특정 시스템 생성 로그를 액세스, 삭제 및 내보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-273">Microsoft also provides you with the ability to access, delete and export certain system-generated logs associated with a user’s use of Azure.</span></span>

>[!Important]
> <span data-ttu-id="feed6-p136">시스템 생성 로그 문제를 제한하거나 수정하는 기능은 지원되지 않습니다. 시스템 생성 로그는 Microsoft 클라우드 및 진단 데이터 내에서 수행되는 실제 작업으로 구성되며, 이러한 데이터를 수정하면 작업의 기록 데이터가 손상되어 사기 및 보안 위험이 높아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p136">The ability to restrict or rectify system-generated logs is not supported. System-generated logs constitute factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions, increasing fraud and security risks.</span></span>

<span id="_Toc511384823" class="anchor"><span id="_Toc511163894" class="anchor"><span id="_Toc511136252" class="anchor"><span id="_Toc511125185" class="anchor"><span id="_Toc511120772" class="anchor"><span id="_Toc511122679" class="anchor"></span></span></span></span></span></span>
## <a name="executing-dsrs-against-system-generated-logs"></a><span data-ttu-id="feed6-276">시스템 생성 로그에 대해 DSR 실행</span><span class="sxs-lookup"><span data-stu-id="feed6-276">Executing DSRs against System-Generated Logs</span></span>

<span data-ttu-id="feed6-p137">Microsoft는 Azure Portal을 통해, 특정 서비스에 대한 프로그래밍 인터페이스 또는 사용자 인터페이스를 통해 직접 특정 시스템 생성 로그를 액세스, 삭제 및 내보낼 수 있는 기능을 제공합니다. 세부 정보는 해당 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p137">Microsoft provides the ability to access, delete, and export certain system-generated logs through the Azure Portal and also directly via programmatic interfaces or user interfaces for specific services. Details are described in the respective services’ reference documentation.</span></span>

>[!Important]  
> <span data-ttu-id="feed6-p138">제품 내 DSR을 지원하는 서비스에서는 서비스의 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 직접적으로 사용해야 합니다. 따라서 지정된 데이터 주체에 대한 모든 요청을 완료하기 위해서는 Azure Portal 내의 DSR 외에도 제품 내 DSR도 **실행해야 합니다. 자세한 내용은 특정 서비스 참조 설명서를 참조하세요.**</span><span class="sxs-lookup"><span data-stu-id="feed6-p138">Services supporting in-product DSRs require direct usage of the service’s application programming interface (API) or user interface (UI). Consequently, execution of an in-product DSRs **must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services’ reference documentation for further details.**</span></span>

<span id="_Toc511384824" class="anchor"><span id="_Toc511163895" class="anchor"><span id="_Toc511136253" class="anchor"><span id="_Toc511125186" class="anchor"><span id="_Toc511120773" class="anchor"><span id="_Toc511122680" class="anchor"><span id="_Ref511119063" class="anchor"><span id="_Toc508792552" class="anchor"><span id="_Toc509825622" class="anchor"></span></span></span></span></span></span></span></span></span>
## <a name="step-1-access"></a><span data-ttu-id="feed6-281">1단계: 액세스</span><span class="sxs-lookup"><span data-stu-id="feed6-281">Step 1: Access</span></span> 

<span data-ttu-id="feed6-p139">테넌트 관리자는 Azure의 특정 사용자의 사용과 관련된 시스템 생성 로그에 액세스할 수 있는 조직 내의 유일한 사람입니다. 액세스 요청에 대한 검색된 데이터는 컴퓨터가 읽을 수 있는 형식으로 제공되며, 데이터가 어떤 서비스에 연결되어 있는지 알 수 있도록 하는 파일로 제공됩니다. 위에서 설명한 것처럼 검색된 데이터에 서비스의 보안을 침해할 수 있는 데이터는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p139">The tenant admin is the only person within your organization who can access system-generated logs associated with a particular user’s use of Azure. The data retrieved for an access request will be provided in a machine-readable format and will be provided in files that will allow the user to know which services the data is associated with. As noted above, the data retrieved will not include data that may compromise the security of the service.</span></span>

<span id="_Toc511384825" class="anchor"><span id="_Toc511163896" class="anchor"><span id="_Toc511136254" class="anchor"><span id="_Toc511125187" class="anchor"><span id="_Toc511120774" class="anchor"><span id="_Toc511122681" class="anchor"><span id="_Toc511119129" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a><span data-ttu-id="feed6-285">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="feed6-285">Azure Active Directory</span></span>

<span data-ttu-id="feed6-p140">Microsoft에서는 엔터프라이즈 고객의 테넌트 관리자에게 액세스 요청을 관리할 수 있는 기능을 제공하는 포털 및 제품 환경을 둘 다 제공합니다. 액세스 요청은 (a) 최종 사용자에 대한 식별 정보와 (b) 서비스 생성 로그를 포함하여 사용자의 개인 데이터에 액세스할 수 있도록 합니다. 이 프로세스는 1부, 2단계: 액세스의 Azure Active Directory 섹션에 설명된 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p140">Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage access requests. Access requests will allow for access of the personal data of the user, including: (a) identifiable information about an end-user and (b) service-generated logs. The process is identical to that described in the Azure Active Directory section of Part 1, Step 2: Access.</span></span>

<span id="_Toc511384826" class="anchor"><span id="_Toc511163897" class="anchor"><span id="_Toc511136255" class="anchor"><span id="_Toc511125188" class="anchor"><span id="_Toc511120775" class="anchor"><span id="_Toc511122682" class="anchor"><span id="_Toc511119130" class="anchor"></span></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a><span data-ttu-id="feed6-289">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="feed6-289">Service-Specific Interfaces</span></span>

<span data-ttu-id="feed6-p141">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p141">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Toc511384827" class="anchor"><span id="_Toc511163898" class="anchor"><span id="_Toc511136256" class="anchor"><span id="_Toc511125189" class="anchor"><span id="_Toc511120776" class="anchor"><span id="_Toc511122683" class="anchor"><span id="_Toc508792553" class="anchor"><span id="_Toc509825623" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-2-delete"></a><span data-ttu-id="feed6-292">2단계: 삭제</span><span class="sxs-lookup"><span data-stu-id="feed6-292">Step 2: Delete</span></span>

<span data-ttu-id="feed6-293">테넌트 관리자는 Azure 테넌트 내의 특정 사용자에 대한 DSR 삭제 요청을 실행할 수 있는 조직 내의 유일한 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-293">The tenant admin is the only person within your organization who can execute a DSR delete request for a particular user within an Azure tenant.</span></span>

<span id="_Toc511384828" class="anchor"><span id="_Toc511163899" class="anchor"><span id="_Toc511136257" class="anchor"><span id="_Toc511125190" class="anchor"><span id="_Toc511120777" class="anchor"><span id="_Toc511122684" class="anchor"><span id="_Toc511119563" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a><span data-ttu-id="feed6-294">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="feed6-294">Azure Active Directory</span></span>

<span data-ttu-id="feed6-p142">Microsoft는 엔터프라이즈 고객의 테넌트 관리자에게 DSR 삭제 요청을 관리하는 기능을 제공하는 포털 및 제품 환경을 둘 다 제공합니다. DSR 삭제 요청은 1부, 5단계: 삭제의 Azure Portal 섹션을 통해 사용자 및 관련 데이터 삭제에 설명된 것과 동일한 방식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p142">Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage DSR delete requests. DSR delete requests follow the same as described in the Delete a user and associated data through the Azure portal section of Part 1, Step 5: Delete.</span></span>

<span id="_Toc511384829" class="anchor"><span id="_Toc511163900" class="anchor"><span id="_Toc511136258" class="anchor"><span id="_Toc511125191" class="anchor"><span id="_Toc511120778" class="anchor"><span id="_Toc511122685" class="anchor"><span id="_Toc511119564" class="anchor"></span></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a><span data-ttu-id="feed6-297">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="feed6-297">Service-Specific Interfaces</span></span>

<span data-ttu-id="feed6-p143">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p143">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Toc511384830" class="anchor"><span id="_Toc511163901" class="anchor"><span id="_Toc511136259" class="anchor"><span id="_Toc511125192" class="anchor"><span id="_Toc511120779" class="anchor"><span id="_Toc511122686" class="anchor"><span id="_Toc508792554" class="anchor"><span id="_Toc509825624" class="anchor"></span></span></span></span></span></span></span></span>

## <a name="step-3-export"></a><span data-ttu-id="feed6-300">3단계: 내보내기</span><span class="sxs-lookup"><span data-stu-id="feed6-300">Step 3: Export</span></span>

<span data-ttu-id="feed6-p144">테넌트 관리자는 Azure의 특정 사용자의 사용과 관련된 시스템 생성 로그에 액세스할 수 있는 조직 내의 유일한 사람입니다. 내보내기 요청에 대한 검색된 데이터는 컴퓨터가 읽을 수 있는 형식으로 제공되며, 데이터가 어떤 서비스에 연결되어 있는지 알 수 있도록 하는 파일로 제공됩니다. 위에서 설명한 것처럼 검색된 데이터에 서비스의 보안 또는 안정성을 침해할 수 있는 데이터는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p144">The tenant admin is the only person within your organization who can access system-generated logs associated with a particular user’s use of Azure. The data retrieved for an export request will be provided in a machine-readable format and will be provided in files that will allow the user to know which services the data is associated with. As noted above, the data retrieved will not include data that may compromise the security or stability of the service.</span></span>

<span id="_Toc511384831" class="anchor"><span id="_Toc511163902" class="anchor"></span></span>
### <a name="export-system-generated-logs-using-the-azure-portal"></a><span data-ttu-id="feed6-304">Azure Portal을 사용하여 시스템 생성 로그 내보내기</span><span class="sxs-lookup"><span data-stu-id="feed6-304">Export system-generated logs using the Azure portal</span></span>

<span data-ttu-id="feed6-305">데이터 주체에 대한 내보내기 요청을 받은 경우, Azure Portal을 사용하여 지정된 사용자와 연결된 시스템 생성 로그를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-305">After you receive an export request for a data subject, you can use the Azure portal to export system-generated logs associated with a given user.</span></span>

<span data-ttu-id="feed6-306">테넌트에서 데이터를 내보내기 위한 고급 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-306">Here’s the high-level process for exporting data from your tenant.</span></span>

1.  <span data-ttu-id="feed6-307">Azure Portal로 이동한 후 사용자를 대신하여 내보내기 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-307">Go to the Azure portal and create an export request on behalf of the user.</span></span>

2.  <span data-ttu-id="feed6-308">데이터를 내보내고 사용자에게 파일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-308">Export the data and send file to user.</span></span>

##### <a name="to-export-a-users-info-from-an-azure-tenant"></a><span data-ttu-id="feed6-309">Azure 테넌트에서 사용자 정보를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="feed6-309">To export a user’s info from an Azure tenant</span></span>

1.  <span data-ttu-id="feed6-310">Azure Portal에서 **모든 서비스**를 선택하고 필터에 *정책*을 입력한 후 **정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-310">Open the Azure portal, select **All services**, type *policy* into the filter, and then select **Policy**.</span></span>

     ![<span data-ttu-id="feed6-311">모든 서비스 필터</span><span class="sxs-lookup"><span data-stu-id="feed6-311">All services filter</span></span> ](media/azure-dsr_image12.png)

2.  <span data-ttu-id="feed6-312">**정책** 블레이드에서 **사용자 개인 정보**를 선택하고 **사용자 요청 관리**를 선택한 후 **내보내기 요청 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-312">In the **Policy** blade, select **User privacy**, select **Manage User Requests**, and then select **Add export request**.</span></span>

    ![<span data-ttu-id="feed6-313">내보내기 요청 추가</span><span class="sxs-lookup"><span data-stu-id="feed6-313">Add export request</span></span> ](media/azure-dsr_image13.png)

3.  <span data-ttu-id="feed6-314">다음과 같이 **데이터 내보내기 요청**을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-314">Complete the **Export data request**:</span></span>

    ![새 데이터 내보내기 요청](media/azure-dsr_image14.png)

-   <span data-ttu-id="feed6-p145">**사용자.** 내보내기를 요청한 Azure Active Directory 사용자의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p145">**User.** Type the email address of the Azure Active Directory user that requested the export.</span></span>

-   <span data-ttu-id="feed6-p146">**구독.** 리소스 사용량을 보고하고 서비스 요청을 청구하는 데 사용하는 계정을 선택합니다. Azure Storage 계정의 위치이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p146">**Subscription.** Select the account you use to report resource usage and to bill for services. This is also the location of your Azure storage account.</span></span>

-   <span data-ttu-id="feed6-p147">**저장소 계정.** Azure Storage(Blob)의 위치를 선택합니다. 자세한 내용은 [Microsoft Azure Storage 소개 - Blob 저장소](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="feed6-p147">**Storage account.** Select the location of your Azure Storage (Blob). For more info, see the [Introduction to Microsoft Azure Storage – Blob storage](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage) article.</span></span>

-   <span data-ttu-id="feed6-p148">**컨테이너.** 사용자가 내보낸 개인 정보 데이터의 저장소 위치로서, 새 컨테이너를 만들거나 기존 컨테이너를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p148">**Container.** Create a new (or select an existing) container as the storage location for the user’s exported privacy data.</span></span>

4.  <span data-ttu-id="feed6-326">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-326">Select **Create**.</span></span>

<span data-ttu-id="feed6-p149">내보내기 요청은 **보류 중** 상태가 됩니다. **사용자 개인 정보 - 개요** 블레이드에서 보고서 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p149">The export request goes into **Pending** status. You can view the report status on the **User privacy - Overview** blade.</span></span>
>
><span data-ttu-id="feed6-329">[중요]</span><span class="sxs-lookup"><span data-stu-id="feed6-329">[Important]</span></span>  
><span data-ttu-id="feed6-330">개인 데이터는 여러 시스템에서 가져올 수 있으므로 내보내기 프로세스를 완료하는 데 최대 1개월이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-330">Because personal data can come from multiple systems, it’s possible that the export process might take up to one month to complete.</span></span>

<span id="_Toc511384832" class="anchor"><span id="_Toc511163903" class="anchor"></span></span>

### <a name="service-specific-interfaces"></a><span data-ttu-id="feed6-331">서비스 관련 인터페이스</span><span class="sxs-lookup"><span data-stu-id="feed6-331">Service-Specific Interfaces</span></span>

<span data-ttu-id="feed6-p150">Microsoft에서는 특정 서비스의 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접 고객 데이터를 검색하는 기능을 제공합니다. 세부 사항은 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명하는 서비스의 참조 설명서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-p150">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

## <a name="notify-about-exporting-or-deleting-issues"></a><span data-ttu-id="feed6-334">내보내기 또는 삭제 문제에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="feed6-334">Notify about exporting or deleting issues</span></span>
<span data-ttu-id="feed6-335">Azure Portal에서 데이터를 내보내거나 삭제하는 동안 문제가 발생하면 Azure Portal **도움말 + 지원** 블레이드로 이동하여 **등록 관리 > 기타 보안 및 준수 요청 > 개인 정보 보호 블레이드 및 GDPR 요청**에서 새 티켓을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="feed6-335">If you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management > Other Security and Compliance Request > Privacy Blade and GDPR Requests**.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="feed6-336">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="feed6-336">Learn more</span></span>
[<span data-ttu-id="feed6-337">Microsoft 보안 센터</span><span class="sxs-lookup"><span data-stu-id="feed6-337">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)