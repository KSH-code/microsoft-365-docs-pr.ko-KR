---
title: GDPR 및 CCPA에 대한 Azure DevOps 데이터 주체 요청
keywords: Visual Studio Team Services, VSTS, Azure DevOpsS 설명서, 개인 정보, GDPR, CCPA
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a43c2e874092de70535c0150f10870b8a071aafc
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557978"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="c7cfe-103">GDPR 및 CCPA에 대한 Azure DevOps Services 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="c7cfe-103">Azure DevOps Services Data Subject Requests for the GDPR and CCPA</span></span>

<span data-ttu-id="c7cfe-p101">유럽 연합 [GDPR(일반 데이터 보호 규정)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm)은 사용자(규정에 *데이터 주체*로 알려짐)에게 *데이터 통제자*가 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 데이터 통제자 또는 단순히 *통제자*는 고용주 또는 다른 유형의 대리점 및 조직(데이터 통제자 또는 단순히 통제자로 지칭)이 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 개인 데이터는 GDPR에서는 보다 광범위하게 식별되었거나 식별 가능한 자연인과 관련된 모든 데이터로 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 부여합니다. 이러한 권한에는 개인 데이터 복사본 획득, 수정 요청, 처리 제한, 삭제 또는 다른 통제자에게 이동될 수 있도록 전자 형식으로 수신하는 권한이 포함됩니다. 데이터 주체가 통제자에게 개인 데이터에 대해 조치를 취할 것을 요구하는 공식적인 요청을 *데이터 주체 요청* 또는 DSR이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-p101">The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people, known in the regulation as *data subjects*, to manage the personal data that's collected by a *data controller*. A data controller, or just *controller*, is an employer or other type of agency or organization. Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data. These rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request*, or DSR.</span></span>

<span data-ttu-id="c7cfe-110">마찬가지로 캘리포니아 소비자 개인 정보 보호법(CCPA)은 캘리포니아 소비자에게 GDPR의 데이터 주체 권리와 유사한 권리를 포함하여, 소비자의 개인 정보 삭제, 액세스 및 수신(이식성)과 같은 개인 정보 보호 권리 및 의무를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-110">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR’s Data Subject Rights, such as the right to delete, access and receive (portability) their personal information.</span></span>  <span data-ttu-id="c7cfe-111">또한 CCPA는 특정 공개, 실행 권리 행사 시 차별 대우로부터 보호, “판매"로 분류되는 특정 데이터 전송에 대한 "옵트아웃(opt-out)/옵트인(opt-in)" 요구도 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-111">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and “opt-out/ opt-in” requirements for certain data transfers classified as “sales".</span></span> <span data-ttu-id="c7cfe-112">판매는 가치 있는 대가관계를 위하여 데이터 공유를 포함하도록 광범위하게 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-112">Sales are broadly defined to include the sharing of data for a valuable consideration.</span></span> <span data-ttu-id="c7cfe-113">CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-113">For more information about the CCPA, see the [California Consumer Privacy Act](offering-ccpa.md) and the [California Consumer Privacy Act FAQ](ccpa-faq.md).</span></span>

<span data-ttu-id="c7cfe-114">GDPR 대한 일반적인 내용은 [Service Trust Portal의 GDPR 섹션](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-114">For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

<span data-ttu-id="c7cfe-115">이 가이드에서는 Microsoft 도구를 사용하여 인증(로그인)된 Azure DevOps Services(이전에는 Visual Studio Team Services로 알려짐) 세션 동안 수집된 개인 데이터를 내보내거나 삭제하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-115">This guide discusses how to use Microsoft tools to export or delete personal data collected during an authenticated (signed-in) session of Azure DevOps Services (formerly known as Visual Studio Team Services).</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="c7cfe-116">추가 개인 정보 보호 정보</span><span class="sxs-lookup"><span data-stu-id="c7cfe-116">Additional privacy information</span></span>

<span data-ttu-id="c7cfe-117">[Microsoft 개인정보 취급방침](https://privacy.microsoft.com/privacystatement), [OST(온라인 서비스 약관)](https://www.microsoft.com/licensing/product-licensing/products.aspx) 및 [Microsoft의 GDPR 약속](/legal/gdpr) 문서에 데이터 처리 방법이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-117">The [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement), [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx), and [Microsoft's GDPR Commitments](/legal/gdpr) articles describe our data processing practices.</span></span>

## <a name="personal-data-we-collect"></a><span data-ttu-id="c7cfe-118">수집한 개인 데이터</span><span class="sxs-lookup"><span data-stu-id="c7cfe-118">Personal data we collect</span></span>

<span data-ttu-id="c7cfe-119">Microsoft는 Azure DevOps Services를 운영하고 개선하기 위해 사용자로부터 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-119">Microsoft collects data from users to operate and improve Azure DevOps Services.</span></span> <span data-ttu-id="c7cfe-120">Azure DevOps Services는 고객 데이터와 시스템 생성 로그라는 두 가지 범주의 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-120">Azure DevOps Services collects two categories of data — customer data and system-generated logs.</span></span> <span data-ttu-id="c7cfe-121">고객 데이터에는 Azure DevOps Services에서 서비스를 운영하는 데 필요한 사용자 식별 가능 트랜잭션 및 상호 작용 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-121">Customer data includes user-identifiable transactional and interactional data that Azure DevOps Services needs to operate the service.</span></span> <span data-ttu-id="c7cfe-122">시스템 생성 로그에는 각 제품 영역 및 기능에 대해 집계하는 서비스 사용 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-122">System-generated logs include service usage data that is aggregated for each product area and feature.</span></span>

## <a name="delete-azure-devops-data"></a><span data-ttu-id="c7cfe-123">Azure DevOps 데이터 삭제</span><span class="sxs-lookup"><span data-stu-id="c7cfe-123">Delete Azure DevOps data</span></span>

<span data-ttu-id="c7cfe-124">시스템 생성 로그에서 관련 Azure DevOps Services 고객 데이터를 삭제하고 개인 식별 가능 데이터를 익명 처리하는 첫 번째 단계는 AAD(Azure Active Directory) ID 계정 또는 Microsoft 계정(MSA)을 종료하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-124">The first step to delete associated Azure DevOps Services customer data and to anonymize personally identifiable data found in system-generated logs is to close your Azure Active Directory (AAD) identity account or Microsoft Account (MSA).</span></span> <span data-ttu-id="c7cfe-125">Azure DevOps Services는 엄격한 무결성, 추적성 및 감사 규칙을 갖춘 레코드 시스템으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-125">Azure DevOps Services is relied upon as a system of record with strict integrity, traceability, and audit rules.</span></span> <span data-ttu-id="c7cfe-126">이러한 기존 의무는 GDPR의 삭제 및 보유 의무에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-126">These existing obligations affect our delete and retention obligations for GDPR.</span></span> <span data-ttu-id="c7cfe-127">ID 계정을 종료해도 Azure DevOps 조직의 개별 ID와 관련된 아티팩트 및 레코드는 변경 또는 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-127">Closing the identity account does not alter, remove, or change artifacts and records associated with the individual identity in the Azure DevOps organization.</span></span> <span data-ttu-id="c7cfe-128">전체 Azure DevOps 조직이 삭제되면 해당 조직에서 찾은 모든 관련 개인 식별 데이터와 시스템 생성 로그가 시스템에서 제거됩니다(필수 Azure DevOps 조직 30일 일시 삭제 기간 이후).</span><span class="sxs-lookup"><span data-stu-id="c7cfe-128">We have ensured that when an entire Azure DevOps organization is deleted, all associated personally identifiable data, and system-generated logs found in that organization are removed from our system (after the requisite Azure DevOps organization 30-day soft-delete period).</span></span>

## <a name="export-azure-devops-data"></a><span data-ttu-id="c7cfe-129">Azure DevOps 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="c7cfe-129">Export Azure DevOps data</span></span>

<span data-ttu-id="c7cfe-130">통제자는 Azure DevOps 서비스에 로그인하는 데 사용한 ID 공급자(MSA 또는 AAD)에 따라, 두 가지 방법 중 하나로 데이터 주체에서 수집된 고객 데이터 및 시스템 생성 로그를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-130">Controllers can export customer data and system-generated logs collected from their data subjects by one of two methods, depending upon the identity provider (MSA or AAD) used to sign in to the Azure DevOps service.</span></span>

- <span data-ttu-id="c7cfe-131">Azure 테넌트가 지원하는 계정(예를 들어, Azure 구독과 관련된 AAD 계정 또는 MSA 계정)을 사용하여 인증을 받는 사용자는 [GDPR에 대한 Azure 데이터 주체 요청](gdpr-dsr-azure.md)의 지침을 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-131">Users that authenticate using an account that is backed by an Azure tenant, for example, AAD account or MSA account associated with an Azure subscription, can follow the instructions in [Azure Data Subject Requests for the GDPR](gdpr-dsr-azure.md).</span></span>

- <span data-ttu-id="c7cfe-p105">MSA ID를 사용하여 인증을 받는 사용자는 이 [개인 정보 요청 사이트](https://www.microsoft.com/concern/privacyrequest-msa)를 사용하여 여러 Microsoft 서비스에서 MSA ID에 연결된 작업 데이터를 볼 수 있습니다. 이 시나리오에서는 사용자가 자신의 개인 데이터에 대한 통제자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-p105">Users that authenticate using an MSA identity can use this [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) to view activity data tied to their MSA identity across multiple Microsoft services. In this scenario, the user is a controller for their own personal data.</span></span>

## <a name="export-or-delete-issues"></a><span data-ttu-id="c7cfe-134">내보내기 또는 삭제 문제</span><span class="sxs-lookup"><span data-stu-id="c7cfe-134">Export or delete issues</span></span>

<span data-ttu-id="c7cfe-135">AAD ID의 경우 Azure Portal에서 데이터를 내보내거나 삭제하는 동안 문제가 발생하면 Azure Portal **도움말 + 지원** 블레이드로 이동하여 **등록 관리** > **기타 보안 및 준수 요청** > **개인 정보 보호 블레이드 및 GDPR 요청**에서 새 티켓을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-135">For AAD identities, if you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management** > **Other Security and Compliance Request** > **Privacy Blade and GDPR Requests**.</span></span>

<span data-ttu-id="c7cfe-136">MSA ID의 경우 개인 정보 요청 사이트에서 데이터를 내보낼 때 문제가 발생할 경우 [개인 정보 요청 사이트](https://www.microsoft.com/concern/privacyrequest-msa)에 로그인한 후 요청 웹 양식을 통해 Microsoft 개인 정보 보호 지원 팀에 대한 지원 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-136">For MSA identities, if you run into issues while exporting data from the Privacy Request site, log on to the [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) and submit a request for help from the Microsoft Privacy team via the request webform.</span></span>

## <a name="learn-more"></a><span data-ttu-id="c7cfe-137">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c7cfe-137">Learn more</span></span>

<span data-ttu-id="c7cfe-p106">Microsoft는 예외없이, Azure DevOps Services 데이터를 안전하고 비공개로 유지할 것을 약속드립니다. [Azure DevOps Services 데이터 보호 개요](/vsts/articles/team-services-security-whitepaper?view=vsts) 백서를 참조하여 Microsoft가 사용자의 Azure DevOps Services 데이터를 보호하는 방법을 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c7cfe-p106">Microsoft is committed to ensuring that your Azure DevOps Services data remains secure and private, without exception. Visit the [Azure DevOps Services data protection overview](/vsts/articles/team-services-security-whitepaper?view=vsts) whitepaper to learn more about how we protect your Azure DevOps Services data.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7cfe-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7cfe-140">See also</span></span>

- [<span data-ttu-id="c7cfe-141">일반적으로 사용할 수 있는 엔터프라이즈 소프트웨어 제품의 고객에 대한 Microsoft의 GDPR 약속</span><span class="sxs-lookup"><span data-stu-id="c7cfe-141">Microsoft's GDPR commitments to customers of our generally available enterprise software products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="c7cfe-142">Microsoft 보안 센터</span><span class="sxs-lookup"><span data-stu-id="c7cfe-142">Microsoft Trust center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
- [<span data-ttu-id="c7cfe-143">Service Trust portal</span><span class="sxs-lookup"><span data-stu-id="c7cfe-143">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="c7cfe-144">Microsoft 개인 정보 대시보드</span><span class="sxs-lookup"><span data-stu-id="c7cfe-144">Microsoft privacy dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="c7cfe-145">Microsoft 개인 정보 응답 센터</span><span class="sxs-lookup"><span data-stu-id="c7cfe-145">Microsoft privacy response center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="c7cfe-146">GDPR에 대한 Azure 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="c7cfe-146">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)
