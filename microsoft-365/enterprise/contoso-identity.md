---
title: Contoso Corporation의 ID
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso가 IDaaS(Identity as a Service)를 활용하고 직원을 위해 클라우드 기반 인증을 제공하고, 파트너 및 고객을 위해 페더레이션 인증을 제공하는 방법을 알아봅니다.
ms.openlocfilehash: 77c90740fd39080ccc204552bc8407aa107e354a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068467"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="55bbe-103">Contoso Corporation의 ID</span><span class="sxs-lookup"><span data-stu-id="55bbe-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="55bbe-104">Microsoft은 Azure AD(Azure Active Directory)를 사용하는 해당 클라우드 서비스에서 IDaaS(Identity as a Service)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="55bbe-105">Microsoft 365 Enterprise를 채택하기 위해 Contoso의 IDaaS 솔루션은 해당 온-프레미스 ID 공급자를 활용해야 했으며, 기존의 신뢰할 수 있는 타사 ID 공급자와 함께 페더레이션 인증을 여전히 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-105">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="55bbe-106">Contoso의 Active Directory Domain Services 포리스트</span><span class="sxs-lookup"><span data-stu-id="55bbe-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="55bbe-107">Contoso는 각각이 세계의 지역을 나타내는 7개의 하위 도메인을 포함하는 contoso.com에 대해 단일 AD DS(Active Directory Domain Services) 포리스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="55bbe-108">본사, 지역 허브 사무실 및 위성 사무실에는 로컬 인증 및 권한 부여를 위한 도메인 컨트롤러가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="55bbe-109">다음은 지역 허브를 포함하는 전 세계 여러 지역에 대한 지역별 도메인을 포함하는 Contoso 포리스트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contoso의 전 세계 포리스트 및 도메인](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="55bbe-111">Contoso는 Microsoft 365 워크로드 및 서비스의 인증 및 권한 부여를 위해 contoso.com 포리스트의 계정과 그룹을 사용하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="55bbe-112">Contoso의 페더레이션 인증 인프라</span><span class="sxs-lookup"><span data-stu-id="55bbe-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="55bbe-113">Contoso는 다음을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-113">Contoso allows:</span></span>

- <span data-ttu-id="55bbe-114">고객이 Microsoft, Facebook 또는 Google Mail 계정을 사용하여 공용 웹 사이트에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="55bbe-115">공급업체 및 파트너가 LinkedIn, Salesforce 또는 Google Mail 계정을 사용하여 파트너 엑스트라넷에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="55bbe-p103">다음은 공개 웹 사이트, 파트너 엑스트라넷 및 AD FS(Active Directory Federation Services) 서버 집합을 포함하는 Contoso DMZ를 보여줍니다. 이 DMZ는 고객, 파트너 및 인터넷 서비스를 포함하는 인터넷에 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-p103">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Contoso의 고객 및 파트너에 대한 페더레이션 인증 지원](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="55bbe-119">DMZ의 AD FS 서버는 ID 공급자가 공용 웹 사이트 액세스용 고객 자격 증명과 파트너 엑스트라넷 액세스용 파트너 자격 증명을 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="55bbe-p104">Contoso는 이 인프라를 유지하고 고객 및 파트너 인증에만 사용하기로 결정했습니다. Contoso ID 설계자는 이러한 인프라를 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 및 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 솔루션으로 전환하는 작업을 조사하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="55bbe-122">클라우드 기반 인증을 위해 암호 해시 동기화를 사용하는 하이브리드 ID</span><span class="sxs-lookup"><span data-stu-id="55bbe-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="55bbe-123">Contoso는 Microsoft 365 클라우드 리소스에서 인증을 받기 위해 온-프레미스 AD DS 포리스트를 활용하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="55bbe-124">따라서 PHS(암호 해시 동기화)를 사용하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="55bbe-125">PHS는 온-프레미스 AD DS 포리스트를 해당 Microsoft 365 Enterprise 구독의 Azure AD 테넌트와 동기화하고, 사용자 및 그룹 계정과 사용자 계정 암호의 해시된 버전을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="55bbe-126">지속적인 디렉터리 동기화를 수행하기 위해 Contoso는 파리 데이터 센터에 있는 서버에 Azure AD Connect 도구를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="55bbe-127">다음은 Azure AD Connect에서 실행되는 서버가 Contoso AD DS 포리스트에서 변경 내용을 폴링한 후 Azure AD 테넌트와 동기화하는 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso의 PHS 디렉터리 동기화 인프라](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="55bbe-129">ID 및 디바이스 액세스에 대한 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="55bbe-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="55bbe-130">Contoso는 다음 세 가지 보호 수준에서 Azure AD 및 Intune [조건부 액세스 정책](identity-access-policies.md) 세트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="55bbe-131">**기준** 보호는 모든 사용자 계정에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="55bbe-132">**중요** 보호는 고위 경영진 및 실무진에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="55bbe-133">**높은 규제** 보호는 높은 규제 대상 데이터에 액세스하는 재무, 법률 및 연구 부서의 특정 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="55bbe-134">다음은 Consoto의 ID 및 디바이스 조건부 액세스 정책의 결과 세트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="55bbe-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Contoso의 ID 및 디바이스 조건부 액세스 정책](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="55bbe-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="55bbe-136">Next step</span></span>

<span data-ttu-id="55bbe-137">Contoso가 해당 Microsoft Endpoint Configuration Manager 인프라를 활용하여 조직 내에서 최신 Windows 10 Enterprise를 배포하고 유지하는 방법을 [알아봅니다](contoso-win10.md).</span><span class="sxs-lookup"><span data-stu-id="55bbe-137">[Learn](contoso-win10.md) how Contoso is leveraging its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="55bbe-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55bbe-138">See also</span></span>

[<span data-ttu-id="55bbe-139">Microsoft 365 Enterprise의 ID</span><span class="sxs-lookup"><span data-stu-id="55bbe-139">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="55bbe-140">배포 가이드</span><span class="sxs-lookup"><span data-stu-id="55bbe-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="55bbe-141">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="55bbe-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
