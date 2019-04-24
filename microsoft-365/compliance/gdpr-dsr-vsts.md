---
title: GDPR에 대한 Azure DevOps 데이터 주체 요청
keywords: Visual Studio Team Services, VSTS, Azure DevOpsS 설명서, 개인 정보, GDPR
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: jitojo
ms.author: jominana
manager: douge
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: b3711e0a68600152750d85e6287be735e204a92d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285096"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="8dbbc-103">GDPR에 대한 Azure DevOps Services 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="8dbbc-103">Azure DevOps Services Data Subject Requests for the GDPR</span></span>

<span data-ttu-id="8dbbc-p101">유럽 연합 [GDPR(일반 데이터 보호 규정)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm)은 사용자(규정에 *데이터 주체*로 알려짐)에게 *데이터 통제자*가 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 데이터 통제자 또는 단순히 *통제자*는 고용주 또는 다른 유형의 대리점 및 조직(데이터 통제자 또는 단순히 통제자로 지칭)이 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 개인 데이터는 GDPR에서는 보다 광범위하게 식별되었거나 식별 가능한 자연인과 관련된 모든 데이터로 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 부여합니다. 이러한 권한에는 개인 데이터 복사본 획득, 수정 요청, 처리 제한, 삭제 또는 다른 통제자에게 이동될 수 있도록 전자 형식으로 수신하는 권한이 포함됩니다. 데이터 주체가 통제자에게 개인 데이터에 대해 조치를 취할 것을 요구하는 공식적인 요청을 *데이터 주체 요청* 또는 DSR이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-p101">The European Union [General Data Protection Regulation (GDPR)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people, known in the regulation as *data subjects*, to manage the personal data that's collected by a *data controller*. A data controller, or just *controller*, is an employer or other type of agency or organization. Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data. These rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request*, or DSR.</span></span>

<span data-ttu-id="8dbbc-110">GDPR 대한 일반적인 내용은 [Service Trust Portal의 GDPR 섹션](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-110">For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

<span data-ttu-id="8dbbc-111">이 가이드에서는 Microsoft 도구를 사용하여 인증(로그인)된 Azure DevOps Services(이전에는 Visual Studio Team Services로 알려짐) 세션 동안 수집된 개인 데이터를 내보내거나 삭제하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-111">This guide discusses how to use Microsoft tools to export or delete personal data collected during an authenticated (signed-in) session of Azure DevOps Services (formerly known as Visual Studio Team Services).</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="8dbbc-112">추가 개인 정보 보호 정보</span><span class="sxs-lookup"><span data-stu-id="8dbbc-112">Additional privacy information</span></span>

<span data-ttu-id="8dbbc-113">[Microsoft 개인정보 취급방침](https://privacy.microsoft.com/privacystatement), [OST(온라인 서비스 약관)](https://www.microsoft.com/licensing/product-licensing/products.aspx) 및 [Microsoft의 GDPR 약속](/legal/gdpr) 문서에 데이터 처리 방법이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-113">The [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement), [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx), and [Microsoft's GDPR Commitments](/legal/gdpr) articles describe our data processing practices.</span></span>

## <a name="personal-data-we-collect"></a><span data-ttu-id="8dbbc-114">수집한 개인 데이터</span><span class="sxs-lookup"><span data-stu-id="8dbbc-114">Personal data we collect</span></span>

<span data-ttu-id="8dbbc-p102">Microsoft는 Azure DevOps Services를 작동하고 개선하기 위해 사용자의 데이터를 수집합니다. Azure DevOps Services는 두 가지 범주의 데이터, &mdash;즉, 고객 데이터 및 시스템 생성 로그를 수집합니다. 고객 데이터에는 Azure DevOps Services가 서비스를 운영하는 데 필요한 사용자를 식별할 수 있는 트랜잭션의 및 상호 작용 데이터가 포함되어 있습니다. 시스템 생성 로그에는 각 제품 영역 및 기능에 대해 집계된 서비스 사용 현황 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-p102">Microsoft collects data from users to operate and improve Azure DevOps Services. Azure DevOps Services collects two categories of data&mdash;customer data and system-generated logs. Customer data includes user-identifiable transactional and interactional data that Azure DevOps Services needs to operate the service. System-generated logs include service usage data that is aggregated for each product area and feature.</span></span>

## <a name="delete-azure-devops-data"></a><span data-ttu-id="8dbbc-119">Azure DevOps 데이터 삭제</span><span class="sxs-lookup"><span data-stu-id="8dbbc-119">Delete Azure DevOps data</span></span>

<span data-ttu-id="8dbbc-p103">연결된 Azure DevOps Services 고객 데이터를 삭제하고 시스템 생성 로그에서 찾은 개인 식별이 가능한 데이터를 익명화하는 첫 번째 단계는 AAD(Azure Active Directory) ID 계정 또는 MSA(Microsoft 계정)을 닫는 것입니다. VSTS는 엄격한 무결성, 추적 가능성 및 감사 규칙을 제공하는 레코드 시스템으로서 활용됩니다. 이러한 기존 의무는 GDPR에 대한 삭제 및 보존 의무에 영향을 미칩니다. ID 계정을 닫아도 Azure DevOps Services 조직의 개별 ID와 연결된 아티팩트 및 레코드는 수정되거나, 제거되거나, 변경되지 않습니다. 전체 Azure DevOps Services 조직이 삭제되면 해당 조직에서 발견된 개인 식별이 가능한 모든 관련된 데이터 및 시스템 생성 로그가 시스템에서 제거됩니다(필수 Azure DevOps Services 조직의 30일 일시 삭제 기간 후).</span><span class="sxs-lookup"><span data-stu-id="8dbbc-p103">The first step to delete associated Azure DevOps Services customer data and to anonymize personally identifiable data found in system-generated logs is to close your Azure Active Directory (AAD) identity account or Microsoft Account (MSA). Azure DevOps Services is relied upon as a system of record with strict integrity, traceability, and audit rules. These existing obligations affect our delete and retention obligations for GDPR. Closing the identity account does not alter, remove, or change artifacts and records associated with the individual identity in the Azure DevOps organization. We have ensured that when an entire Azure DevOps organization is deleted, all associated personally identifiable data and system-generated logs found in that organization are removed from our system (after the requisite Azure DevOps organization 30-day soft-delete period).</span></span>

## <a name="export-azure-devops-data"></a><span data-ttu-id="8dbbc-125">Azure DevOps 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="8dbbc-125">Export Azure DevOps data</span></span>

<span data-ttu-id="8dbbc-126">통제자는 Azure DevOps 서비스에 로그인하는 데 사용한 ID 공급자(MSA 또는 AAD)에 따라, 두 가지 방법 중 하나로 데이터 주체에서 수집된 고객 데이터 및 시스템 생성 로그를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-126">Controllers can export customer data and system-generated logs collected from their data subjects by one of two methods, depending upon the identity provider (MSA or AAD) used to sign in to the Azure DevOps service.</span></span>

- <span data-ttu-id="8dbbc-127">Azure 테넌트가 지원하는 계정(예를 들어, Azure 구독과 관련된 AAD 계정 또는 MSA 계정)을 사용하여 인증을 받는 사용자는 [GDPR에 대한 Azure 데이터 주체 요청](../compliance/gdpr-dsr-azure.md)의 지침을 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-127">Users that authenticate using an account that is backed by an Azure tenant, for example, AAD account or MSA account associated with an Azure subscription, can follow the instructions in [Azure Data Subject Requests for the GDPR](../compliance/gdpr-dsr-azure.md).</span></span>

- <span data-ttu-id="8dbbc-p104">MSA ID를 사용하여 인증을 받는 사용자는 이 [개인 정보 요청 사이트](https://www.microsoft.com/concern/privacyrequest-msa)를 사용하여 여러 Microsoft 서비스에서 MSA ID에 연결된 작업 데이터를 볼 수 있습니다. 이 시나리오에서는 사용자가 자신의 개인 데이터에 대한 통제자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-p104">Users that authenticate using an MSA identity can use this [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) to view activity data tied to their MSA identity across multiple Microsoft services. In this scenario, the user is a controller for their own personal data.</span></span>

## <a name="export-or-delete-issues"></a><span data-ttu-id="8dbbc-130">내보내기 또는 삭제 문제</span><span class="sxs-lookup"><span data-stu-id="8dbbc-130">Export or delete issues</span></span>

<span data-ttu-id="8dbbc-131">AAD ID의 경우 Azure Portal에서 데이터를 내보내거나 삭제하는 동안 문제가 발생하면 Azure Portal **도움말 + 지원** 블레이드로 이동하여 **등록 관리** > **기타 보안 및 준수 요청** > **개인 정보 보호 블레이드 및 GDPR 요청**에서 새 티켓을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-131">For AAD identities, if you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management** > **Other Security and Compliance Request** > **Privacy Blade and GDPR Requests**.</span></span>

<span data-ttu-id="8dbbc-132">MSA ID의 경우 개인 정보 요청 사이트에서 데이터를 내보낼 때 문제가 발생할 경우 [개인 정보 요청 사이트](https://www.microsoft.com/concern/privacyrequest-msa)에 로그인한 후 요청 웹 양식을 통해 Microsoft 개인 정보 보호 지원 팀에 대한 지원 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-132">For MSA identities, if you run into issues while exporting data from the Privacy Request site, log on to the [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) and submit a request for help from the Microsoft Privacy team via the request webform.</span></span>

## <a name="learn-more"></a><span data-ttu-id="8dbbc-133">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="8dbbc-133">Learn more</span></span>

<span data-ttu-id="8dbbc-p105">Microsoft는 예외없이, Azure DevOps Services 데이터를 안전하고 비공개로 유지할 것을 약속드립니다. [Azure DevOps Services 데이터 보호 개요](/vsts/articles/team-services-security-whitepaper?view=vsts) 백서를 참조하여 Microsoft가 사용자의 Azure DevOps Services 데이터를 보호하는 방법을 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="8dbbc-p105">Microsoft is committed to ensuring that your Azure DevOps Services data remains secure and private, without exception. Visit the [Azure DevOps Services data protection overview](/vsts/articles/team-services-security-whitepaper?view=vsts) whitepaper to learn more about how we protect your Azure DevOps Services data.</span></span>

## <a name="see-also"></a><span data-ttu-id="8dbbc-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dbbc-136">See also</span></span>

- [<span data-ttu-id="8dbbc-137">일반적으로 사용할 수 있는 엔터프라이즈 소프트웨어 제품의 고객에 대한 Microsoft의 GDPR 약속</span><span class="sxs-lookup"><span data-stu-id="8dbbc-137">Microsoft's GDPR commitments to customers of our generally available enterprise software products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="8dbbc-138">Microsoft 보안 센터</span><span class="sxs-lookup"><span data-stu-id="8dbbc-138">Microsoft Trust center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [<span data-ttu-id="8dbbc-139">Service Trust portal</span><span class="sxs-lookup"><span data-stu-id="8dbbc-139">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="8dbbc-140">Microsoft 개인 정보 대시보드</span><span class="sxs-lookup"><span data-stu-id="8dbbc-140">Microsoft privacy dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="8dbbc-141">Microsoft 개인 정보 응답 센터</span><span class="sxs-lookup"><span data-stu-id="8dbbc-141">Microsoft privacy response center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="8dbbc-142">GDPR에 대한 Azure 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="8dbbc-142">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)