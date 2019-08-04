---
title: GDPR에 대한 데이터 주체 요청
description: ''
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: dc4352ac14f42a227f1572b0c7f1442aa4dec838
ms.sourcegitcommit: c201f5cc13d501e5207ebad166e42f90260af0c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2019
ms.locfileid: "35078908"
---
# <a name="data-subject-requests-and-the-gdpr"></a><span data-ttu-id="c9bcb-103">데이터 주제 요청 및 GDPR</span><span class="sxs-lookup"><span data-stu-id="c9bcb-103">Data Subject Requests for the GDPR</span></span>

<span data-ttu-id="c9bcb-104">GDPR(일반 데이터 보호 규제)는 EU(유럽 연합) 회원국 국민에게 제품과 서비스를 제공하거나 귀하 또는 귀사가 어디에 있는지 관계없이 EU 거주자의 데이터를 수집하고 분석하는 조직에 새로운 규칙을 도입합니다. </span><span class="sxs-lookup"><span data-stu-id="c9bcb-104">The GDPR introduces new rules for companies, government agencies, non-profits, and other organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents. The GDPR applies no matter where you or your enterprise are located.</span></span> <span data-ttu-id="c9bcb-105">추가 세부 정보는 [GDPR 요약 항목](gdpr.md)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-105">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWs1SI] 

<span data-ttu-id="c9bcb-106">이 문서에서는 Microsoft 제품 및 서비스를 사용 하 여 GDPR 하에서 DSRs(데이터 주제 요청)를 완료하는 방법에 대한 정보를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-106">This document guides you to information on the completion of Data Subject Requests (DSRs) under the GDPR using Microsoft products and services.</span></span>

- [<span data-ttu-id="c9bcb-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="c9bcb-107">Office 365</span></span>](gdpr-dsr-Office365.md)
- [<span data-ttu-id="c9bcb-108">Azure</span><span class="sxs-lookup"><span data-stu-id="c9bcb-108">Azure</span></span>](gdpr-dsr-Azure.md)
- [<span data-ttu-id="c9bcb-109">Intune</span><span class="sxs-lookup"><span data-stu-id="c9bcb-109">Intune</span></span>](gdpr-dsr-Intune.md)
- [<span data-ttu-id="c9bcb-110">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c9bcb-110">Dynamics 365</span></span>](gdpr-dsr-Dynamics365.md)
- [<span data-ttu-id="c9bcb-111">Visual Studio 제품군</span><span class="sxs-lookup"><span data-stu-id="c9bcb-111">Visual Studio Family</span></span>](gdpr-dsr-visual-studio-family.md)
- [<span data-ttu-id="c9bcb-112">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="c9bcb-112">Azure DevOps Services</span></span>](gdpr-dsr-vsts.md)
- [<span data-ttu-id="c9bcb-113">Microsoft 지원 및 전문 서비스</span><span class="sxs-lookup"><span data-stu-id="c9bcb-113">Microsoft Support and Professional Services</span></span>](gdpr-dsr-prof-services.md)

## <a name="terminology"></a><span data-ttu-id="c9bcb-114">용어</span><span class="sxs-lookup"><span data-stu-id="c9bcb-114">Terminology</span></span>

<span data-ttu-id="c9bcb-115">이 문서에서 사용된 GDPR 용어에 대한 유용한 정의:</span><span class="sxs-lookup"><span data-stu-id="c9bcb-115">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="c9bcb-116">*데이터 컨트롤러(컨트롤러)*: 개인 데이터 처리의 목적과 수단을 결정하는 법인, 공공 기관, 에이전시 또는 다른 사람과 독립적으로 또는 공동으로 작업하는 기타 단체입니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-116">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="c9bcb-117">*개인 데이터* 및 *데이터 주체*: 식별되거나 식별 가능한 자연인(데이터 주체)과 관련된 모든 정보. 식별 가능한 자연인은 직접 또는 간접적으로 식별될 수 있는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-117">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="c9bcb-118">*프로세서*: 컨트롤러를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 에이전시 또는 기타 단체입니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-118">*Processor.* A natural or legal person, public authority, agency or other body which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="c9bcb-119">*고객 데이터*: 비즈니스 운영의 일상적인 작업에서 생성되고 저장되는 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-119">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dsr"></a><span data-ttu-id="c9bcb-120">DSR이란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c9bcb-120">What is a template?</span></span>

<span data-ttu-id="c9bcb-121">GDPR(일반 데이터 보호 규정)은 사람들(규정에서 데이터 주체)에게 고용주 또는 다른 유형의 기관이나 조직(데이터 컨트롤러 또는 간단하게 컨트롤러)에 의해 수집된 개인 데이터를 관리할 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-121">The General Data Protection Regulation (GDPR) gives rights to people (known in the regulation as data subjects) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the data controller or just controller).</span></span> <span data-ttu-id="c9bcb-122">GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 제공합니다. 이러한 권한에는 개인 데이터의 복사본을 얻거나, 수정을 요청하거나, 처리를 제한하거나, 삭제하거나, 다른 관리자에게 전달할 수 있도록 전자 형식으로 개인 데이터를 수신할 권한이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-122">The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller.</span></span>

<span data-ttu-id="c9bcb-123">컨트롤러는 요청된 조치를 취하거나 DSR을 컨트롤러가 수용할 수 없는 이유에 대한 설명을 제공함으로써 각 DSR을 즉시 고려하고 실질적인 응답을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-123">As a controller you are obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller.</span></span> <span data-ttu-id="c9bcb-124">컨트롤러는 주어진 DSR의 적절한 처분과 관련하여 자체 법률 또는 준수 고문과 상의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-124">A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.</span></span>

<span data-ttu-id="c9bcb-125">조직의 GDPR 준수 규칙에 따라 여러 프로세스가 DSR 완료하는 데 연관될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-125">Several processes may be involved completing a DSR, subject to your organization’s GDPR-compliance rules.</span></span>
  
- <span data-ttu-id="c9bcb-126">**검색**.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-126">**Discovery mailboxes**</span></span> <span data-ttu-id="c9bcb-127">DSR을 완료하는 데 필요한 데이터를 결정하는 프로세스</span><span class="sxs-lookup"><span data-stu-id="c9bcb-127">The process of determining what data is needed to complete a DSR.</span></span>
- <span data-ttu-id="c9bcb-128">**액세스**.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-128">**Access**</span></span> <span data-ttu-id="c9bcb-129">검색된 정보의 데이터 주체에 대한 검색 및 잠재적 전송</span><span class="sxs-lookup"><span data-stu-id="c9bcb-129">Retrieval and potential transmission to the data subject of discovered information.</span></span>
- <span data-ttu-id="c9bcb-130">**수정**.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-130">Rectify</span></span> <span data-ttu-id="c9bcb-131">변경 또는 기타 요청된 개인 데이터 변경 사항을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-131">Implement changes or other requested personal data changes.</span></span>
- <span data-ttu-id="c9bcb-132">**제한**.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-132">Restrict</span></span> <span data-ttu-id="c9bcb-133">액세스를 제한하거나 Microsoft 클라우드에서 데이터를 제거하여 개인 데이터의 액세스 또는 처리를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-133">Changing the access or processing of persona data by restricting access, or removing data from the Microsoft cloud.</span></span>
- <span data-ttu-id="c9bcb-134">**내보내기**.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-134">Export</span></span> <span data-ttu-id="c9bcb-135">GDPR의 "데이터 이식성(data-portability)"에서 제공하는 바와 같이 개인 데이터의 "구조화되고 일반적으로 사용되는 컴퓨터가 읽을 수 있는 형식"을 데이터 주체에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-135">Providing a “structured, commonly used, machine-readable format” of personal data to the data subject, as provided by the GDPR’s “right of data portability.”</span></span>
- <span data-ttu-id="c9bcb-136">**삭제**.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-136">**Delete**.</span></span> <span data-ttu-id="c9bcb-137">Microsoft 클라우드에서 개인 데이터를 영구적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-137">Permanent removal of personal data from the Microsoft cloud.</span></span>

## <a name="specific-dsr-considerations"></a><span data-ttu-id="c9bcb-138">특정 DSR 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c9bcb-138">Specific DSR Considerations</span></span>

### <a name="insights-generated-by-microsoft-products-or-services"></a><span data-ttu-id="c9bcb-139">Microsoft 제품 또는 서비스에서 생성된 인사이트</span><span class="sxs-lookup"><span data-stu-id="c9bcb-139">Insights generated by Microsoft Products or Services</span></span>

<span data-ttu-id="c9bcb-140">[인사이트](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)는 서비스(MyAnalytics 등)를 통해 생성될 수 있습니다. Office 365에는 사용자와 조직이 사용하는 인사이트를 제공하는 온라인 서비스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-140">[Insights](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) may be generated by services (MyAnalytics, etc.) Office 365 includes online services that provide insights to users and organizations that use them.</span></span> <span data-ttu-id="c9bcb-141">이러한 서비스에서 생성된 데이터를 통해 DSR과 관련된 개인 데이터가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-141">Data generated by these services may produce personal data relevant to a DSR.</span></span> <span data-ttu-id="c9bcb-142">서비스 관련 DSR 프로세스에 대한 자세한 내용은 아래 목록에 있는 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-142">Follow the link in the list below for details regarding service-specific DSR processes.</span></span>  

### <a name="dsrs-for-system-generated-logs"></a><span data-ttu-id="c9bcb-143">시스템 생성 로그용 DSRs</span><span class="sxs-lookup"><span data-stu-id="c9bcb-143">Part 2: Responding to DSRs for system-generated logs</span></span>

<span data-ttu-id="c9bcb-144">Microsoft에서 생성한 로그 및 관련 데이터는 GDPR의 "개인 데이터" 정의 하에 개인으로 간주되는 데이터가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-144">Logs and related data generated by Microsoft may contain data deemed personal under GDPR's definition of "personal data."</span></span> <span data-ttu-id="c9bcb-145">시스템 생성 로그에서 데이터를 제한하거나 수정하는 기능은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-145">Restricting or rectifying data in system-generated logs is not supported.</span></span> <span data-ttu-id="c9bcb-146">시스템 생성 로그의 데이터는 Microsoft 클라우드 및 진단 데이터 내에서 수행되는 실제 작업으로 구성되며, 이러한 데이터를 수정하면 작업의 기록 데이터가 손상되어 사기 및 보안 위험이 높아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-146">Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.</span></span> <span data-ttu-id="c9bcb-147">Microsoft는 DSR을 완료하는 데 필요한 시스템 생성 로그에 액세스하고, 내보내고, 삭제할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-147">Microsoft provides the ability to access, export, and delete system-generated logs that may be necessary to complete a DSR.</span></span> <span data-ttu-id="c9bcb-148">예를 들어 다음과 같은 데이터가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-148">Examples of such data may include:</span></span>  

- <span data-ttu-id="c9bcb-149">사용자 활동 로그와 같은 제품 및 서비스 사용 데이터</span><span class="sxs-lookup"><span data-stu-id="c9bcb-149">Product and service usage data such as user activity logs</span></span>
- <span data-ttu-id="c9bcb-150">사용자 검색 요청 및 쿼리 데이터</span><span class="sxs-lookup"><span data-stu-id="c9bcb-150">User search requests and query data</span></span>
- <span data-ttu-id="c9bcb-151">시스템 기능 및 사용자나 기타 시스템의 상호 작용으로 발생한 제품 및 서비스에서 생성된 데이터</span><span class="sxs-lookup"><span data-stu-id="c9bcb-151">Data generated by product and services as a product of system functionality and interaction by users or other systems</span></span>  

### <a name="yammer-and-kaizala"></a><span data-ttu-id="c9bcb-152">Yammer 및 Kaizala</span><span class="sxs-lookup"><span data-stu-id="c9bcb-152">Yammer and Kaizala</span></span>

<span data-ttu-id="c9bcb-p112">사용자 계정을 삭제해도 Yammer 및 Kaizala에 대한 시스템 생성 로그는 제거되지 않습니다. 이러한 응용 프로그램에서 데이터를 제거하려면 다음 중 하나를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-p112">Deleting a user’s account will not remove system-generated logs for Yammer and Kaizala. To remove the data from these applications, see one of the following:</span></span>

- [<span data-ttu-id="c9bcb-155">Yammer Enterprise에서 GDPR 데이터 주체 요청 관리</span><span class="sxs-lookup"><span data-stu-id="c9bcb-155">Manage GDPR data subject requests in Yammer Enterprise</span></span>](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [<span data-ttu-id="c9bcb-156">Kaizala에서 사용자의 조직 데이터 내보내기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="c9bcb-156">Export or delete a user's organizational data in Kaizala</span></span>](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a><span data-ttu-id="c9bcb-157">국가별 클라우드</span><span class="sxs-lookup"><span data-stu-id="c9bcb-157">National clouds</span></span>

<span data-ttu-id="c9bcb-158">일부 국가 클라우드에서는 전역 IT 관리자가 시스템 생성 로그를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-158">In some national clouds, a global IT Administrator needs to delete system-generated logs.</span></span>

### <a name="microsoft-services"></a><span data-ttu-id="c9bcb-159">Microsoft 서비스</span><span class="sxs-lookup"><span data-stu-id="c9bcb-159">Microsoft Services</span></span>

<span data-ttu-id="c9bcb-160">조직이나 사용자가 Microsoft 제품 및 서비스와 관련된 지원을 받기 위해 Microsoft와 함께하는 경우 이 데이터 중 일부는 개인 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-160">If your organization or users engage with Microsoft to receive,  support related to Microsoft products and services some of this data may contain personal data.</span></span> <span data-ttu-id="c9bcb-161">자세한 내용은 [GDPR에 대한 Microsoft 고객 지원 및 전문 서비스 데이터 주체 요청](gdpr-dsr-prof-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-161">Microsoft Support and Professional Services Data Subject Requests for the GDPR</span></span>

### <a name="microsoft-controller-products"></a><span data-ttu-id="c9bcb-162">Microsoft 컨트롤러 제품</span><span class="sxs-lookup"><span data-stu-id="c9bcb-162">Microsoft Controller Products</span></span>

<span data-ttu-id="c9bcb-163">경우에 따라 조직의 사용자가 Microsoft가 데이터 컨트롤러인 Microsoft 제품 또는 서비스에 액세스 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-163">In some circumstances, your organization’s users may access Microsoft products or services for which Microsoft is the data controller.</span></span> <span data-ttu-id="c9bcb-164">그러한 경우 사용자는 자신의 DSR을 Microsoft에 직접 시작해야 하며 Microsoft는 사용자에게 직접 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-164">In those cases, your users need to initiate their own DSRs directly to Microsoft, and Microsoft fulfills the requests directly to the user.</span></span>

### <a name="third-party-products"></a><span data-ttu-id="c9bcb-165">타사 제품</span><span class="sxs-lookup"><span data-stu-id="c9bcb-165">Third-party Products</span></span>

<span data-ttu-id="c9bcb-166">Microsoft 계정 인증을 통해 액세스되는 타사 제품 및 서비스의 경우 데이터 주체 요청은 해당 타사로 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bcb-166">For third-party products and services accessed through Microsoft account authentication, any data subject requests should be directed to the applicable third party.</span></span>

## <a name="learn-more"></a><span data-ttu-id="c9bcb-167">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c9bcb-167">Learn more</span></span>

- [<span data-ttu-id="c9bcb-168">Microsoft 보안 센터</span><span class="sxs-lookup"><span data-stu-id="c9bcb-168">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
