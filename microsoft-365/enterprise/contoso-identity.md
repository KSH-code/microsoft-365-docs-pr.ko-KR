---
title: Contoso Corporation의 ID
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso가 IDaaS(Identity as a Service)를 활용하고 직원을 위해 클라우드 기반 인증을 제공하고, 파트너 및 고객을 위해 페더레이션 인증을 제공하는 방법을 알아봅니다.
ms.openlocfilehash: f3c8746345683652ce601400ae7297e96fff2ee3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051523"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="fbf50-103">Contoso Corporation의 ID</span><span class="sxs-lookup"><span data-stu-id="fbf50-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="fbf50-104">Microsoft는 Azure AD(Azure Active Directory)를 통해 클라우드 서비스 전반에 걸쳐 IDaaS(Identity as a Service)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="fbf50-105">엔터프라이즈용 Microsoft 365를 채택하기 위해 Contoso IDaaS 솔루션은 해당 사내 ID 공급자를 사용하며 기존의 신뢰할 수 있는 타사 ID 공급자와의 페더임 인증을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="fbf50-106">Contoso Active Directory 도메인 서비스 포리스트</span><span class="sxs-lookup"><span data-stu-id="fbf50-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="fbf50-107">Contoso는 7개의 하위 도메인이 있는 contoso com에 대해 단일 AD DS(Active Directory 도메인 서비스) \. 포리스트를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="fbf50-108">본사, 지역 허브 사무실 및 위성 사무실에는 로컬 인증 및 권한 부여를 위한 도메인 컨트롤러가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="fbf50-109">다음은 지역 허브를 포함하는 전 세계 여러 지역을 위한 지역 도메인이 있는 Contoso 포리스트입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contoso의 전 세계 포리스트 및 도메인](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="fbf50-111">Contoso는 Microsoft 365 워크로드 및 서비스에 대한 인증 및 권한 부여를 위해 contoso com 포리스트의 계정 및 그룹을 \. 사용하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="fbf50-112">Contoso 페더전 인증 인프라</span><span class="sxs-lookup"><span data-stu-id="fbf50-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="fbf50-113">Contoso는 다음을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-113">Contoso allows:</span></span>

- <span data-ttu-id="fbf50-114">고객은 Microsoft, Facebook 또는 Google Mail 계정을 사용하여 회사의 공용 웹 사이트에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="fbf50-115">공급업체 및 파트너는 LinkedIn, Salesforce 또는 Google Mail 계정을 사용하여 회사의 파트너 엑스트라넷에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="fbf50-116">다음은 공용 웹 사이트, 파트너 엑스트라넷 및 AD FS(Active Directory Federation Services) 서버 집합을 포함하는 Contoso DMZ입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="fbf50-117">DMZ는 고객, 파트너 및 인터넷 서비스가 포함된 인터넷에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![고객 및 파트너를 위한 페더전 인증에 대한 Contoso 지원](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="fbf50-119">DMZ의 AD FS 서버는 공용 웹 사이트에 액세스하기 위해 ID 공급자가 고객 자격 증명을 인증하고 파트너 엑스트라넷에 액세스하기 위한 파트너 자격 증명을 쉽게 인증할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="fbf50-120">Contoso는 이 인프라를 보관하고 고객 및 파트너 인증에 전담하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="fbf50-121">Contoso ID 설계자는 이 인프라를 Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) 및 [B2C](/azure/active-directory-b2c/solution-articles) 솔루션으로 변환하는 방법을 조사하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) and [B2C](/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="fbf50-122">클라우드 기반 인증을 위해 암호 해시 동기화를 사용하는 하이브리드 ID</span><span class="sxs-lookup"><span data-stu-id="fbf50-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="fbf50-123">Contoso는 Microsoft 365 클라우드 리소스에 대한 인증을 위해 해당 사내 AD DS 포리스트를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="fbf50-124">PHS(암호 해시 동기화)를 사용하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="fbf50-125">PHS는 엔터프라이즈용 Microsoft 365 구독의 Azure AD 테넌트와 사내 AD DS 포리스트를 동기화하여 사용자 및 그룹 계정 및 해시된 버전의 사용자 계정 암호를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="fbf50-126">디렉터리 동기화를 위해 Contoso는 파리 데이터 센터의 서버에 Azure AD Connect 도구를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="fbf50-127">다음은 Azure AD Connect를 실행하는 서버가 Contoso AD DS 포리스트에서 변경 내용을 폴링한 다음 해당 변경 내용을 Azure AD 테넌트와 동기화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso PHS 디렉터리 동기화 인프라](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="fbf50-129">ID 및 디바이스 액세스에 대한 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="fbf50-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="fbf50-130">Contoso는 다음 세 가지 보호 수준에서 Azure AD 및 Intune [조건부 액세스 정책](../security/defender-365-security/identity-access-policies.md) 세트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](../security/defender-365-security/identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="fbf50-131">*기준 보호는* 모든 사용자 계정에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="fbf50-132">*중요한* 보호는 고위 경영진 및 임원진에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="fbf50-133">*높은 규제 대상* 보호는 높은 규제 대상 데이터에 액세스할 수 있는 재무, 법률 및 연구 부서의 특정 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="fbf50-134">Contoso ID 및 장치 조건부 액세스 정책의 결과 집합은 다음과 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contoso의 ID 및 디바이스 조건부 액세스 정책](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="fbf50-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fbf50-136">Next step</span></span>

<span data-ttu-id="fbf50-137">Contoso에서 Microsoft Endpoint Configuration Manager 인프라를 사용하여 조직 전체에서 최신 [Windows 10 Enterprise를](contoso-win10.md) 배포하고 유지하는 방법을 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf50-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbf50-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbf50-138">See also</span></span>

[<span data-ttu-id="fbf50-139">Microsoft 365의 ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="fbf50-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="fbf50-140">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="fbf50-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fbf50-141">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="fbf50-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)