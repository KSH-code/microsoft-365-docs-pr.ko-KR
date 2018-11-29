---
title: Contoso Corporation의 ID
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso가 IDaaS(Identity as a Service)를 활용하고 직원을 위해 클라우드 기반 인증을 제공하고, 파트너 및 고객을 위해 페더레이션 인증을 제공하는 방법을 알아봅니다.
ms.openlocfilehash: 7571aa455cac4da9e56d7d2001ae4421c3769c94
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870188"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="bf624-103">Contoso Corporation의 ID</span><span class="sxs-lookup"><span data-stu-id="bf624-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="bf624-104">**요약:** Contoso가 IDaaS(Identity as a Service)를 활용하고 직원을 위해 클라우드 기반 인증을 제공하고, 파트너 및 고객을 위해 페더레이션 인증을 제공하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="bf624-p101">Microsoft는 Azure AD(Active Directory)와 함께 해당 클라우드 제품에서 IDaaS(ID as a Service)를 제공합니다. Microsoft 365 Enterprise를 도입하기 위해 Contoso의 IDaaS 솔루션은 해당 온-프레미스 ID 공급자를 활용하고, 기존의 신뢰할 수 있는 타사 ID 공급자와 함께 페더레이션 인증을 포함해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-p101">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (AD). To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-windows-server-ad-forest"></a><span data-ttu-id="bf624-107">Contoso의 Windows Server AD 포리스트</span><span class="sxs-lookup"><span data-stu-id="bf624-107">Contoso's Windows Server AD forest</span></span>

<span data-ttu-id="bf624-p102">Contoso는 하위 도메인 7개가 포함된 contoso.com용으로 단일 Windows Server AD(Active Directory) 포리스트를 사용합니다. 각 도메인은 전 세계의 각 지역에 사용됩니다. 본사, 지역 허브 사무소 및 위성 사무소에는 로컬 인증 및 권한 부여용 도메인 컨트롤러가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-p102">Contoso uses a single Windows Server Active Directory (AD) forest for contoso.com with seven sub-domains, one for each region of the world. The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="bf624-110">그림 1에서는 지역 허브를 포함하는 전 세계 여러 지역에 대한 지역별 도메인을 포함하는 Contoso 포리스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="bf624-111">**그림 1: Contoso의 전 세계 포리스트 및 도메인**</span><span class="sxs-lookup"><span data-stu-id="bf624-111">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="bf624-112">Contoso는 클라우드 기반 앱과 작업의 인증 및 권한 부여를 위해 contoso.com 포리스트의 계정과 그룹을 사용하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-112">Contoso wants to use the accounts and groups in the contoso.com forest for authentication and authorization for its cloud-based apps and workloads.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="bf624-113">Contoso의 페더레이션 인증 인프라</span><span class="sxs-lookup"><span data-stu-id="bf624-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="bf624-114">Contoso는 다음을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-114">Contoso allows:</span></span>

- <span data-ttu-id="bf624-115">고객이 Microsoft, Facebook 또는 Google Mail 계정을 사용하여 공용 웹 사이트에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="bf624-116">공급업체 및 파트너가 LinkedIn, Salesforce 또는 Google Mail 계정을 사용하여 파트너 엑스트라넷에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="bf624-p103">그림 2에서는 공개 웹 사이트, 파트너 엑스트라넷 및 AD FS(Active Directory Federation Services) 서버 집합을 포함하는 Contoso DMZ를 보여 줍니다. 이 DMZ는 고객, 파트너 및 인터넷 서비스를 포함하는 인터넷에 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="bf624-119">**그림 2: Contoso의 고객 및 파트너에 대한 페더레이션 인증 지원**</span><span class="sxs-lookup"><span data-stu-id="bf624-119">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="bf624-120">DMZ의 AD FS 서버는 공용 웹 사이트 액세스용 고객 자격 증명과 파트너 엑스트라넷 액세스용 파트너 자격 증명을 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-120">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="bf624-p104">Contoso는 이 인프라를 유지하고 고객 및 파트너 인증에만 사용하기로 결정했습니다. Contoso ID 엔지니어는 이러한 인프라를 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 및 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 솔루션으로 전환하는 작업을 조사하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-pass-through-authentication-for-cloud-based-authentication"></a><span data-ttu-id="bf624-123">클라우드 기반 인증을 위해 통과 인증을 사용하는 하이브리드 ID</span><span class="sxs-lookup"><span data-stu-id="bf624-123">Hybrid identity with pass-through authentication for cloud-based authentication</span></span>

<span data-ttu-id="bf624-p105">Contoso는 Microsoft 365 클라우드 리소스에서 인증을 받기 위해 해당 온-프레미스 Windows Server AD 포리스트를 활용하려고 했습니다. 따라서 PHS(암호 해시 동기화)를 사용한 PTA(통과 인증)을 채택하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-p105">Contoso wanted to leverage its on-premises Windows Server AD forest for authentication to Microsoft 365 cloud resources. It decided on pass-through authentication (PTA) with password hash synchronization (PHS).</span></span>

### <a name="pta-authentication"></a><span data-ttu-id="bf624-126">PTA 인증</span><span class="sxs-lookup"><span data-stu-id="bf624-126">PTA authentication</span></span>

<span data-ttu-id="bf624-p106">사용자 자격 증명의 인증을 위해 Contoso는 PTA를 사용하고 있습니다. Contoso 사용자가 클라우드 기반 리소스에 액세스할 때 전송하는 자격 증명은 Azure AD를 통해 Contoso 본사 데이터 센터에서 인증 에이전트를 실행하는 서버로 전달됩니다. 이러한 인증 에이전트 서버 중 하나가 Azure AD를 대신해서 사용자 자격 증명이 유효한지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-p106">For authentication of user credentials, Contoso is using PTA. When a Contoso user accesses a cloud-based resources, the credentials it sends are passed by Azure AD to a server running an Authentication Agent in the Contoso headquarters datacenter. One of these Authentication Agent servers validates the user credentials on behalf of Azure AD.</span></span>

<span data-ttu-id="bf624-130">그림 3에서는 인증 에이전트를 실행하는 Contoso 본사의 서버 집합을 보여 줍니다. 이러한 서버는 Azure AD에서 전달받은 인증 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-130">Figure 3 shows a set of servers in the Contoso headquarters running the Authentication Agent, which process authentication requests passed to it from Azure AD.</span></span> 

![](./media/contoso-identity/contoso-identity-fig3.png)
 
<span data-ttu-id="bf624-131">**그림 3: Contoso의 통과 인증 인프라**</span><span class="sxs-lookup"><span data-stu-id="bf624-131">**Figure 3: Contoso's pass-through authentication infrastructure**</span></span>

<span data-ttu-id="bf624-132">Contoso는 모든 인증 시도에 대해 사용자 계정 상태, 암호 정책의 즉각적인 변경 및 온-프레미스 Windows Server AD 포리스트에 대한 로그인 시간 변경을 발생하는지 평가되도록 하는 보안 요구를 이행하기 위해 PTA를 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-132">Contoso chose PTA to fulfill its security requirement that all authentication attempts be evaluated for immediate changes to user account states, password policies, and sign-in hours made to the on-premises Windows Server AD forest.</span></span>

### <a name="phs"></a><span data-ttu-id="bf624-133">PHS</span><span class="sxs-lookup"><span data-stu-id="bf624-133">PHS</span></span>

<span data-ttu-id="bf624-p107">PHS는 온-프레미스 Windows Server AD 포리스트를 해당 Microsoft 365 Enterprise 구독의 Azure AD 테넌트와 동기화하고 사용자 및 그룹 계정과 해시된 버전의 사용자 계정 암호를 복사합니다. Contoso는 PTA를 사용할 수 없는 경우에 Azure AD 테넌트에서 직접 인증할 수 있는 대체 방법을 제공하기 위해 PHS를 사용하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-p107">PHS synchronizes the on-premises Windows Server AD forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords. Contoso decided on PHS to provide an alternate method of authentication directly with the Azure AD tenant in the event that PTA is not available.</span></span>

<span data-ttu-id="bf624-p108">지속적인 디렉터리 동기화를 수행하기 위해 Contoso는 파리 데이터 센터의 서버에 Azure AD Connect 도구를 배포했습니다. 그림 4는 Azure AD Connect에서 실행되는 서버가 Contoso Windows Server AD 포리스트에서 변경 내용을 폴링하고 해당 변경 내용을 Azure AD 테넌트와 동기화하는 모습을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-p108">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="bf624-138">**그림 4: Contoso의 PHS 디렉터리 동기화 인프라**</span><span class="sxs-lookup"><span data-stu-id="bf624-138">**Figure 4: Contoso's PHS directory synchronization infrastructure**</span></span>

## <a name="conditional-access-policies-for-identity"></a><span data-ttu-id="bf624-139">ID에 대한 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="bf624-139">Conditional access policies for identity</span></span>

<span data-ttu-id="bf624-140">Contoso는 Azure AD가 인증 요청에 대한 로그인 위험이 있다고 판단할 경우 다단계 인증 및 암호 변경을 적용하도록 하기 위해 Azure AD [조건부 액세스 정책](identity-access-policies.md) 집합을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-140">Contoso created a set of Azure AD [conditional access policies](identity-access-policies.md) to ensure that multi-factor authentication and password changes are enforced when Azure AD determines there is sign-in risk for an authentication request.</span></span>

<span data-ttu-id="bf624-141">그림 5에서는 ID에 대한 조건부 액세스 정책의 결과 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf624-141">Figure 5 shows their resulting set of conditional access policies for identity.</span></span>

![](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="bf624-142">**그림 5: Contoso의 ID 기반 조건부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="bf624-142">**Figure 5: Contoso’s identity-based conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="bf624-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bf624-143">Next step</span></span>

<span data-ttu-id="bf624-144">Contoso가 해당 System Center Configuration Manager 인프라를 활용하여 조직 내에서 최신 Windows 10 Enterprise를 배포하고 유지하는 방법을 [알아봅니다](contoso-win10.md).</span><span class="sxs-lookup"><span data-stu-id="bf624-144">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf624-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf624-145">See also</span></span>

[<span data-ttu-id="bf624-146">Microsoft 365 Enterprise의 ID</span><span class="sxs-lookup"><span data-stu-id="bf624-146">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="bf624-147">배포 가이드</span><span class="sxs-lookup"><span data-stu-id="bf624-147">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="bf624-148">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="bf624-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
