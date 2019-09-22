---
title: 비 엔터프라이즈용 Microsoft 365 Enterprise 기본 인프라
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 비 엔터프라이즈 조직용 Microsoft 365 Enterprise에 대해 간소화된 기본 인프라 단계를 살펴보겠습니다.
ms.openlocfilehash: 37bbf04eafeb3adc63d9dd01d052376f98856df4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071737"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="7cf39-103">비 엔터프라이즈용 Microsoft 365 Enterprise 기본 인프라</span><span class="sxs-lookup"><span data-stu-id="7cf39-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="7cf39-104">엔터프라이즈 기반이 아닌 조직도 Microsoft 365 Enterprise를 배포하여 팀워크를 활성화하고 창의성을 여는 통합된 보안 인프라의 비즈니스 가치를 실현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-104">Non-enterprise organizations can also deploy Microsoft 365 Enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="7cf39-105">일반적으로 엔터프라이즈 기반이 아닌 조직은 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="7cf39-106">소규모의 온-프레미스 IT 인프라(예: 전자 메일 및 파일 서버와 AD DS(Active Directory Domain Services) 도메인) 또는 인프라가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="7cf39-107">소수의 IT 담당자. 이들 중 대부분은 네트워킹 또는 전자 메일과 같은 특정 기술 또는 워크로드의 전문가가 아닌, IT 제너럴리스트입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="7cf39-108">엔터프라이즈가 아닌, 중소기업의 경우, Microsoft는 [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-108">For your smaller, non-enterprise organization, Microsoft offers [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="7cf39-109">그러나 다음과 같은 이유로 인해 Microsoft 365 Enterprise가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-109">However, there are reasons why you might need Microsoft 365 Enterprise, such as:</span></span>

- <span data-ttu-id="7cf39-110">조직이 Microsoft 365 Business의 최대 개수인 300개 이상의 Microsoft 365 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 Business.</span></span>
- <span data-ttu-id="7cf39-111">조직에서 Microsoft 365 Business에서 제공하지 않는 고급 생산성, 음성, 보안 및 분석을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-111">Your organization needs the advanced productivity, voice, security, and analytics that are not available with Microsoft 365 Business.</span></span>

<span data-ttu-id="7cf39-112">이 문서에서는 비 엔터프라이즈에 적합한 Microsoft 365 Enterprise의 기본 인프라를 배포하는 간단한 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 Enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="7cf39-113">먼저, 구독 설정</span><span class="sxs-lookup"><span data-stu-id="7cf39-113">First, set up your subscription</span></span>

<span data-ttu-id="7cf39-114">구독에 적합한 DNS(Domain Name System) 도메인을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="7cf39-115">Office 365 구독이 이미 있는 경우 이 작업이 완료되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-115">If you already have an Office 365 subscription, this should have been done.</span></span> <span data-ttu-id="7cf39-116">그렇지 않은 경우 [Office 365에 도메인 추가](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="7cf39-117">그런 다음, Microsoft 365를 위한 추가 보안을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="7cf39-118">[향상된 보안 구성](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="7cf39-119">1단계: 네트워킹</span><span class="sxs-lookup"><span data-stu-id="7cf39-119">Phase 1: Networking</span></span>

<span data-ttu-id="7cf39-120">엔터프라이즈가 아닌 조직은 일반적으로 각 사무실에 로컬 인터넷 연결이 있으며 프록시 서버, 방화벽 또는 패킷 검사 디바이스를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="7cf39-121">트래픽이 사무실과 온-프레미스 사용자에게 가장 가까운 Microsoft 365 네트워크 위치로 리디렉션되도록 각 사무실에 서비스를 제공하는 ISP(인터넷 서비스 공급자)에는 지리적 로컬 DNS가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-121">The Internet service provider (ISP) serving each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 network location that is closest to your offices and their on-premises users.</span></span>

<span data-ttu-id="7cf39-122">따라서 ISP를 사용하여 각 사무실 위치의 해당 연결이 다음과 같은지를 확인하면 됩니다. </span><span class="sxs-lookup"><span data-stu-id="7cf39-122">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="7cf39-123">지리적 로컬 DNS 서버를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-123">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="7cf39-124">더 많은 Microsoft 365 클라우드 서비스를 사용하기 시작할 때 현재와 미래의 요구에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-124">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

<span data-ttu-id="7cf39-125">프록시 서버, 방화벽 또는 패킷 검사 디바이스를 사용하는 경우 자세한 내용은 [Microsoft 365 Enterprise의 네트워킹 인프라](networking-infrastructure.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-125">If you do use proxy servers, firewalls, or packet inspection devices, see [Networking infrastructure for Microsoft 365 Enterprise](networking-infrastructure.md) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7cf39-126">지금까지의 구성</span><span class="sxs-lookup"><span data-stu-id="7cf39-126">Your configuration so far</span></span>

<span data-ttu-id="7cf39-127">1단계 요소가 강조 표시된 시각적 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-127">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="7cf39-128">**조직**은 여러 개의 사무실이 있을 수 있고, 각 사무실에는 지리적 로컬 DNS 서버를 사용하는 ISP와의 로컬 인터넷 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-128">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="7cf39-129">ISP를 통해 각 사무실의 사용자는 가장 가까운 Microsoft 365 네트워크 위치와 Microsoft 365 구독의 리소스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-129">Through the ISP, users in each office can reach the nearest Microsoft 365 network location and the resources of your Microsoft 365 subscription.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="7cf39-130">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="7cf39-130">Phase 2: Identity</span></span>

<span data-ttu-id="7cf39-131">조직에 속한 각 직원은 로그인해야 하며, 이를 위해 Microsoft 365 Enterprise의 Azure AD(Azure Active Directory) 테넌트에 사용자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-131">Each of the employees of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="7cf39-132">그런 다음, 그룹을 사용하여 사용자 계정 및 기타 그룹을 포함하여 통신하거나 권한 있는 리소스(예: SharePoint Online 사이트 또는 팀)에 대한 액세스 권한을 획득합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-132">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="7cf39-133">관리자 계정</span><span class="sxs-lookup"><span data-stu-id="7cf39-133">Administrator accounts</span></span>

<span data-ttu-id="7cf39-134">강력한 암호와 MFA(다단계 인증)를 요구하여 전역 관리자 사용자 계정을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-134">Protect your global administrator user accounts by requiring strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="7cf39-135">자세한 내용은 [전역 관리자 계정 보호](identity-create-protect-global-admins.md#protect-global-administrator-accounts)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-135">See [Protect your Office 365 global administrator accounts](identity-create-protect-global-admins.md#protect-global-administrator-accounts) for more information about configuration.</span></span>

<span data-ttu-id="7cf39-136">조직에서 높은 수준의 보안을 요구하고 Microsoft 365 Enterprise E5를 사용하는 경우, Azure AD Privileged Identity Management를 사용하여 적시 관리자 액세스 권한을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-136">If your organization requires high security and you have Microsoft 365 Enterprise E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="7cf39-137">자세한 내용은 [주문형 전역 관리자 설정](identity-create-protect-global-admins.md#identity-pim)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-137">See [Set up on-demand global administrators](identity-create-protect-global-admins.md#identity-pim) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="7cf39-138">그룹에 대한 권장 사항</span><span class="sxs-lookup"><span data-stu-id="7cf39-138">Recommendations for groups</span></span>

<span data-ttu-id="7cf39-139">온-프레미스 AD DS 도메인이 있는 경우, Microsoft 365 Enterprise의 그룹을 Azure AD의 그룹으로 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-139">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 Enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="7cf39-140">온-프레미스 AD DS 도메인이 없는 경우, 이 보안 수준을 사용하여 Azure AD에서 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-140">If you don’t have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="7cf39-141">보안 수준</span><span class="sxs-lookup"><span data-stu-id="7cf39-141">Security level</span></span> | <span data-ttu-id="7cf39-142">설명</span><span class="sxs-lookup"><span data-stu-id="7cf39-142">Description</span></span> | <span data-ttu-id="7cf39-143">예제</span><span class="sxs-lookup"><span data-stu-id="7cf39-143">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="7cf39-144">기준</span><span class="sxs-lookup"><span data-stu-id="7cf39-144">Baseline</span></span> | <span data-ttu-id="7cf39-145">이는 데이터에 액세스하는 장치 및 데이터와 ID를 보호하는 데 최소한의 기본 표준입니다.데</span><span class="sxs-lookup"><span data-stu-id="7cf39-145">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="7cf39-146">이는 일반적으로 대부분의 사용자가 관리하는 대부분의 조직 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-146">This is typically most of your organization’s data managed by most of your users.</span></span> | <span data-ttu-id="7cf39-147">영업, 마케팅, 지원, 관리 및 제조와 같은 일선 직원을 위한 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-147">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="7cf39-148">중요</span><span class="sxs-lookup"><span data-stu-id="7cf39-148">Sensitive</span></span> | <span data-ttu-id="7cf39-149">이는 기준 수준을 넘어서 보호해야 하는 데이터의 하위 집합을 위한 추가 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-149">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="7cf39-150">이 그룹에는 모든 사용자가 사용할 수 있도록 설계되지 않은 부서 및 프로젝트에 해당하는 중요한 데이터를 사용하고 만드는 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-150">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="7cf39-151">미래의 제품을 개발하는 제품 또는 마케팅 팀</span><span class="sxs-lookup"><span data-stu-id="7cf39-151">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="7cf39-152">매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-152">Highly regulated</span></span> | <span data-ttu-id="7cf39-153">이는 고도로 분류되고 고려된 지적 재산권이나 영업 비밀, 또는 보안 규정을 준수해야 하는 데이터로서 일반적으로 소량의 데이터에 적용되는 가장 높은 수준의 보호입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-153">Highly regulated: This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span> |  <span data-ttu-id="7cf39-154">연구, 법률 및 재무 팀이나 고객 또는 파트너 데이터를 저장하거나 사용하는 팀</span><span class="sxs-lookup"><span data-stu-id="7cf39-154">Research, legal, and financial teams, or teams storing or using customer or partner data.</span></span> |
||||

### <a name="hybrid-identity"></a><span data-ttu-id="7cf39-155">하이브리드 ID</span><span class="sxs-lookup"><span data-stu-id="7cf39-155">Hybrid identity</span></span>

<span data-ttu-id="7cf39-156">온-프레미스 AD DS 도메인이 있는 경우 도메인의 사용자 계정, 그룹 및 연락처 세트를 Microsoft 365 Enterprise 구독의 Azure AD 테넌트와 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-156">If you have an on-premises AD DS domain, you need to synchronize the set of user accounts, groups, and contacts of your domain with the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="7cf39-157">엔터프라이즈 이외에는 서버에서 PHS(암호 해시 동기화)를 사용하여 Azure AD Connect를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-157">For your non-enterprise, you configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="7cf39-158">자세한 내용은 [ID 동기화](identity-add-user-accounts.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-158">See [Synchronize identities](identity-add-user-accounts.md) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="7cf39-159">조건부 액세스 정책을 사용하여 더욱 안전한 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="7cf39-159">More secure user access with conditional access policies</span></span>

<span data-ttu-id="7cf39-160">Azure AD는 사용자 로그인의 조건을 평가 하고, 조건부 액세스 정책을 사용하여 액세스를 허용하거나 거부하며 로그인을 완료하기 위해 수행해야 하는 추가 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-160">Azure AD evaluates the conditions of user sign-ins and can use conditional access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="7cf39-161">예를 들어, Azure AD에서 보통 또는 위험성이 높은 조건에 따라 로그인이 진행되고 있음을 확인하는 경우 사용자가 MFA를 수행하여 로그인을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-161">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="7cf39-162">조건부 액세스 정책을 사용자 계정 또는 그룹에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-162">You apply conditional access policies to user accounts or groups.</span></span> <span data-ttu-id="7cf39-163">더욱 간편하게 조건부 액세스 정책을 할당하려면 조직에서 다음 Azure AD 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-163">To facilitate an easier assignment of conditional access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="7cf39-164">기준</span><span class="sxs-lookup"><span data-stu-id="7cf39-164">Baseline</span></span>

  <span data-ttu-id="7cf39-165">기준 데이터에 대한 액세스 권한이 있는 사용자의 그룹 또는 사용자 계정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-165">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="7cf39-166">중요</span><span class="sxs-lookup"><span data-stu-id="7cf39-166">Sensitive</span></span>

  <span data-ttu-id="7cf39-167">중요한 데이터에 대한 액세스 권한이 있는 사용자의 그룹 또는 사용자 계정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-167">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="7cf39-168">매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-168">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="7cf39-169">매우 엄격한 규제 데이터에 대한 액세스 권한이 있는 사용자의 그룹 또는 사용자 계정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-169">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="7cf39-170">조건-액세스-제외</span><span class="sxs-lookup"><span data-stu-id="7cf39-170">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="7cf39-171">조건부 액세스 정책에서 사용자를 일시적으로 제외하는 데 사용할 수 있는 빈 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-171">An empty group that you can use to temporarily exclude a user from conditional access policies.</span></span>

<span data-ttu-id="7cf39-172">활성화하거나 만들기 위한 Azure AD 조건부 액세스 정책의 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-172">Here is the list of Azure AD conditional access policies to enable or create.</span></span>

| <span data-ttu-id="7cf39-173">Azure AD 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-173">Azure AD conditional access policy</span></span> | <span data-ttu-id="7cf39-174">적용 대상 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-174">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="7cf39-175">기준 정책: 관리자에게 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="7cf39-175">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="7cf39-176">이 정책은 관리자 역할에 적용되므로 그룹을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-176">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="7cf39-177">이 정책을 사용하도록 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-177">This policy just needs to be enabled.</span></span> <span data-ttu-id="7cf39-178">모든 후속 정책을 만들고 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-178">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="7cf39-179">최신 인증을 지원하지 않는 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="7cf39-179">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="7cf39-180">정책 설정에서 "모든 사용자"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-180">Select “All users” in the policy settings.</span></span> |
| <span data-ttu-id="7cf39-181">로그인 위험 수준이 보통 또는 위험인 경우 MFA 필요(Microsoft 365 Enterprise E5 필요)</span><span class="sxs-lookup"><span data-stu-id="7cf39-181">Require MFA when sign-in risk is medium or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="7cf39-182">기준</span><span class="sxs-lookup"><span data-stu-id="7cf39-182">Baseline</span></span> |
| <span data-ttu-id="7cf39-183">로그인 위험이 낮음, 보통 또는 높음인 경우 MFA 필요(Microsoft 365 Enterprise E5 필요)</span><span class="sxs-lookup"><span data-stu-id="7cf39-183">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="7cf39-184">중요</span><span class="sxs-lookup"><span data-stu-id="7cf39-184">Sensitive</span></span> |
| <span data-ttu-id="7cf39-185">항상 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="7cf39-185">Always require MFA</span></span> | <span data-ttu-id="7cf39-186">매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-186">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7cf39-187">IOS 및 Android 장치에서 승인된 앱 필요</span><span class="sxs-lookup"><span data-stu-id="7cf39-187">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="7cf39-188">기준, 중요, 매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-188">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7cf39-189">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="7cf39-189">Require compliant PCs</span></span> | <span data-ttu-id="7cf39-190">기준</span><span class="sxs-lookup"><span data-stu-id="7cf39-190">Baseline</span></span> |
| <span data-ttu-id="7cf39-191">호환 PC와 iOS 및 Android 장치 필요</span><span class="sxs-lookup"><span data-stu-id="7cf39-191">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="7cf39-192">중요, 매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-192">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="7cf39-193">다음은 만들고 활성화할 Azure AD Identity Protection(Microsoft 365 Enterprise E5 필요) 사용자 위험 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-193">Here is the Azure AD Identity Protection (requires Microsoft 365 Enterprise E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="7cf39-194">Azure AD Identity Protection 사용자 위험 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-194">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="7cf39-195">적용 대상 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-195">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="7cf39-196">높은 위험 사용자는 암호를 변경해야 함</span><span class="sxs-lookup"><span data-stu-id="7cf39-196">High risk users must change passwords</span></span> | <span data-ttu-id="7cf39-197">정책 설정에서 "모든 사용자"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-197">Select “All users” in the policy settings.</span></span> |
|||

<span data-ttu-id="7cf39-198">지침을 보려면 [일반적인 ID 및 장치 액세스 정책](identity-access-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-198">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="7cf39-199">더 쉬운 관리를 위한 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-199">Groups for easier management</span></span>

<span data-ttu-id="7cf39-200">다음은 그룹과 라이선싱 관리를 쉽게 할 수 있는 몇 가지 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-200">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="7cf39-201">기능</span><span class="sxs-lookup"><span data-stu-id="7cf39-201">Feature</span></span> | <span data-ttu-id="7cf39-202">사용</span><span class="sxs-lookup"><span data-stu-id="7cf39-202">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="7cf39-203">셀프 서비스 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="7cf39-203">Self-service group management</span></span> | <span data-ttu-id="7cf39-204">IT 담당자가 아닌 그룹 소유자로 Azure AD 그룹 관리를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-204">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="7cf39-205">자세한 내용은 [셀프 서비스 그룹 관리](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-205">See [Self-service group management](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="7cf39-206">동적 그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="7cf39-206">Dynamic group membership</span></span> | <span data-ttu-id="7cf39-207">사용자 계정 속성(예: 부서 또는 국가)에 따라 Azure AD 그룹에서 사용자 계정의 자동 추가 또는 제거를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-207">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="7cf39-208">자세한 내용은 [동적 그룹 구성원 자격](identity-use-group-management.md#set-up-dynamic-group-membership)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-208">See [Dynamic group membership](identity-use-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="7cf39-209">그룹 기반 라이선스</span><span class="sxs-lookup"><span data-stu-id="7cf39-209">Group-based licensing</span></span> | <span data-ttu-id="7cf39-210">구성원 자격을 사용하여 사용자 계정에 라이선스를 자동으로 할당하거나 할당 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-210">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="7cf39-211">자세한 [내용은 그룹 기반 라이선스](identity-use-group-management.md#set-up-automatic-licensing) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-211">See [Group-based licensing](identity-use-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="7cf39-212">그룹 기반 라이선스를 사용하는 경우 Microsoft 365 Enterprise 라이선스가 할당된 사용자 계정 이름을 포함하도록 LICENSED라는 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-212">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 Enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="7cf39-213">사용자 액세스 모니터링</span><span class="sxs-lookup"><span data-stu-id="7cf39-213">Monitor user access</span></span>

<span data-ttu-id="7cf39-214">Microsoft 365 Enterprise E5를 사용하는 경우 AD Identity Protection을 사용하여 사용자 로그인에 대한 자격 증명 해킹을 모니터링하고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-214">If you have Microsoft 365 Enterprise E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="7cf39-215">자세한 내용은 [자격 증명 해킹으로부터 보호](identity-secure-user-sign-ins.md#protect-against-credential-compromise)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-215">See [Protect against credential compromise](identity-secure-user-sign-ins.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7cf39-216">지금까지의 구성</span><span class="sxs-lookup"><span data-stu-id="7cf39-216">Your configuration so far</span></span>

<span data-ttu-id="7cf39-217">다음은 새 요소가 강조 표시된 하이브리드 ID의 ID 단계를 시각적으로 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-217">Here is a visual summary of the Identity phase for hybrid identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="7cf39-218">다음은 강조 표시된 새 하이브리드 ID 요소에 포함된 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-218">The new and highlighted hybrid identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="7cf39-219">사용자 계정 및 그룹이 포함된 온-프레미스 AD DS 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-219">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="7cf39-220">Azure AD Connect를 실행하는 Windows 기반 서버</span><span class="sxs-lookup"><span data-stu-id="7cf39-220">A Windows-based server running Azure AD Connect.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="7cf39-221">Azure AD에서 AD DS 계정 및 그룹의 동기화된 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-221">The synchronized set of AD DS accounts and groups in Azure AD.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="7cf39-222">Azure AD 설정을 사용하여 인증, 전역 계정 보안 및 그룹과 라이선스를 더 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-222">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="7cf39-223">Azure AD 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-223">Azure AD conditional access policies.</span></span> |
|||

<span data-ttu-id="7cf39-224">다음은 새 요소가 강조 표시된 클라우드 전용 ID의 ID 단계를 시각적으로 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-224">Here is a visual summary of the Identity phase for cloud-only identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
<span data-ttu-id="7cf39-225">다음은 강조 표시된 새 클라우드 전용 ID 요소에 포함된 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-225">The new and highlighted cloud-only identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="7cf39-226">Azure AD 설정을 사용하여 인증, 전역 계정 보안 및 그룹과 라이선스를 더 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-226">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="7cf39-227">Azure AD 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-227">Azure AD conditional access policies.</span></span> |
|||



## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="7cf39-228">3단계: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7cf39-228">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="7cf39-229">Windows 10 Enterprise 디바이스가 Microsoft 365의 ID 및 보안 인프라에 통합되었는지 확인하기 위한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-229">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365, here are your options:</span></span>

- <span data-ttu-id="7cf39-230">하이브리드(온-프레미스 AD DS 도메인 보유)</span><span class="sxs-lookup"><span data-stu-id="7cf39-230">Hybrid (you have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="7cf39-231">AD DS 도메인에 이미 조인된 각각의 기존 Windows 10 Enterprise 디바이스인 경우, 이를 Azure AD 테넌트에 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-231">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="7cf39-232">자세한 내용은 [하이브리드 Azure Active Directory 조인된 장치를 구성하는 방법](https://go.microsoft.com/fwlink/p/?linkid=872870)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-232">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="7cf39-233">새 Windows 10 Enterprise 장치의 경우, 이를 AD DS 도메인에 조인한 다음, Azure AD 테넌트에 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-233">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="7cf39-234">각 Windows 10 Enterprise 장치의 경우, 모바일 장치 관리에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-234">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="7cf39-235">자세한 지침은 [그룹 정책을 사용하여 Windows 10 디바이스 등록](https://go.microsoft.com/fwlink/p/?linkid=872871)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-235">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

- <span data-ttu-id="7cf39-236">클라우드 전용(온-프레미스 AD DS 도메인이 없음)</span><span class="sxs-lookup"><span data-stu-id="7cf39-236">Cloud-only (you do not have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="7cf39-237">각 Windows 10 Enterprise 디바이스를 구독의 Azure AD 테넌트에 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-237">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="7cf39-238">자세한 내용은 [회사 디바이스를 조직의 네트워크에 조인](https://docs.microsoft.com/ko-KR/azure/active-directory/user-help/user-help-join-device-on-network)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-238">See [Join your work device to your organization's network](https://docs.microsoft.com/ko-KR/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>


<span data-ttu-id="7cf39-239">Windows 10 Enterprise 디바이스를 설치하 고 조인한 후에는 각 디바이스가 비즈니스용 Windows 업데이트 클라우드 서비스에서 업데이트를 자동으로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-239">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="7cf39-240">일반적으로 엔터프라이즈가 아닌 조직은 Windows 10 업데이트를 배포하고 설치하기 위한 인프라를 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-240">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install Windows 10 updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7cf39-241">지금까지의 구성</span><span class="sxs-lookup"><span data-stu-id="7cf39-241">Your configuration so far</span></span>

<span data-ttu-id="7cf39-242">다음은 새 요소가 강조 표시된 Windows 10 Enterprise 단계를 시각적으로 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-242">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="7cf39-243">강조 표시된 새 Windows 10 Enterprise 요소에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-243">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="7cf39-244">Windows 디바이스에 설치된 Windows 10 Enterprise(예: 온-프레미스 노트북)</span><span class="sxs-lookup"><span data-stu-id="7cf39-244">Windows 10 Enterprise installed on Windows devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="7cf39-245">Windows 10 Enterprise의 새 설치에 대한 이미지와 최신 업데이트를 제공하는 비즈니스용 Windows Update를 제공하는 VLSC(Volume Licensing Service Center)입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-245">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-office-365-proplus"></a><span data-ttu-id="7cf39-246">4단계: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="7cf39-246">Phase 4: Office 365 ProPlus</span></span>

<span data-ttu-id="7cf39-247">Microsoft 365 Enterprise에는 Microsoft Office 구독 버전인 Office 365 ProPlus가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-247">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="7cf39-248">Office 2016 또는 Office 2019와 같이, Office 365 ProPlus는 클라이언트 디바이스에 직접 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-248">Like Office 2016 or Office 2019, Office 365 ProPlus is installed directly on your client devices.</span></span> <span data-ttu-id="7cf39-249">그러나 Office 365 ProPlus는 정기적으로 새로운 기능을 포함하는 업데이트를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-249">However, Office 365 ProPlus receives updates that include new features on a regular basis.</span></span> <span data-ttu-id="7cf39-250">자세한 내용은 [엔터프라이즈의 Office 365 ProPlus](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-250">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="7cf39-251">엔터프라이즈가 아닌 조직의 경우, 디바이스에서 Office 365 ProPlus를 수동으로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-251">For your non-enterprise organization, you manually install Office 365 ProPlus on devices.</span></span> <span data-ttu-id="7cf39-252">새 디바이스를 사용할 수 있도록 준비하는 과정에서 또는 온보딩 프로세스의 일부로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-252">This can be done as part of preparing a new device for use, or by the user as part of their onboarding process.</span></span>

<span data-ttu-id="7cf39-253">어떤 경우든, 관리자나 사용자가 Office 365 포털 https://portal.office.com에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-253">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="7cf39-254">**Microsoft Office Home** 탭에서 **Office 설치**를 클릭하고 설치 프로세스를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-254">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="7cf39-255">Office 365 ProPlus에 대한 기능 업데이트는 프로그램이 설치된 각 컴퓨터에서 매월 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-255">Feature updates to Office 365 ProPlus are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="7cf39-256">일반적으로 엔터프라이즈가 아닌 조직은 Office 365 ProPlus 업데이트를 배포하기 위한 인프라를 설정할 필요가 없습니다. </span><span class="sxs-lookup"><span data-stu-id="7cf39-256">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Office 365 ProPlus updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="7cf39-257">지금까지의 구성</span><span class="sxs-lookup"><span data-stu-id="7cf39-257">Your configuration so far</span></span>

<span data-ttu-id="7cf39-258">다음은 새 요소가 강조 표시된 Office 365 ProPlus 단계를 시각적으로 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-258">Here is a visual summary of the Office 365 ProPlus phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="7cf39-259">다음은 강조 표시된 새 Office 365 ProPlus 요소에 포함된 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-259">The new and highlighted Office 365 ProPlus elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="7cf39-260">디바이스에 설치된 Office 365 ProPlus(예: 온-프레미스 노트북)</span><span class="sxs-lookup"><span data-stu-id="7cf39-260">Office 365 ProPlus installed on devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="7cf39-261">디바이스가 Office 365 ProPlus 업데이트를 위해 액세스하는 Office 365 ProPlus용 Office CDN(Content Delivery Network).</span><span class="sxs-lookup"><span data-stu-id="7cf39-261">The Office Content Delivery Network (CDN) for Office 365 ProPlus, which devices access for Office 365 ProPlus updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="7cf39-262">5단계: 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="7cf39-262">Phase 5: Mobile device management</span></span>

<span data-ttu-id="7cf39-263">Microsoft 365 Enterprise에는 모바일 디바이스 관리용 Microsoft Intune이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-263">Microsoft 365 Enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="7cf39-264">Intune을 사용하면 Windows, iOS, Android 및 macOS 디바이스를 관리하여 데이터를 포함하여 조직의 리소스에 대한 액세스를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-264">With Intune, you can manage Windows, iOS, Android, and macOS devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="7cf39-265">Intune에서는 Azure AD의 사용자, 그룹 및 컴퓨터 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-265">Intune uses the user, group, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="7cf39-266">Intune은 다음과 같은 두 가지 유형의 모바일 디바이스 관리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-266">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="7cf39-267">MDM(모바일 장치 관리)은 장치가 Intune에 등록된 경우에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-267">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="7cf39-268">등록하면 관리되는 장치가 되며 조직에서 사용하는 정책, 규칙 및 설정을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-268">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="7cf39-269">이러한 유형의 장치는 보통 조직에서 소유 하며 직원에게 발행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-269">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="7cf39-270">개인 장치를 사용하는 사용자는 해당 장치를 등록하지 않거나 사용자의 정책과 설정을 사용하여 Intune에서 관리하고 싶지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-270">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="7cf39-271">그러나 조직의 리소스와 데이터는 계속 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-271">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="7cf39-272">이 시나리오에서는 MAM(모바일 애플리케이션 관리)를 사용하여 앱을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-272">For this scenario, you can protect your apps with mobile application management (MAM).</span></span>  

<span data-ttu-id="7cf39-273">Intune 정책은 디바이스 준수 및 앱 보호를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-273">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="7cf39-274">다음은 작성할 Intune 정책의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-274">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="7cf39-275">Intune 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-275">Intune policies</span></span> | <span data-ttu-id="7cf39-276">적용 대상 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-276">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="7cf39-277">Windows용 장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-277">Device compliance policy for Windows</span></span> | <span data-ttu-id="7cf39-278">기준, 중요, 매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-278">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7cf39-279">iOS용 장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-279">Device compliance policy for iOS</span></span> | <span data-ttu-id="7cf39-280">중요, 매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-280">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7cf39-281">MacOS용 장치 준수</span><span class="sxs-lookup"><span data-stu-id="7cf39-281">Device compliance for macOS</span></span> | <span data-ttu-id="7cf39-282">중요, 매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-282">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7cf39-283">Android 및 Android Enterprise용 장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-283">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="7cf39-284">중요, 매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-284">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7cf39-285">IOS용 앱 보호 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-285">App protection policy for iOS</span></span> | <span data-ttu-id="7cf39-286">기준, 중요, 매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7cf39-287">MacOS용 앱 보호 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-287">App protection policy for macOS</span></span> | <span data-ttu-id="7cf39-288">기준, 중요, 매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-288">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7cf39-289">Android 및 Android Enterprise용 앱 보호 정책</span><span class="sxs-lookup"><span data-stu-id="7cf39-289">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="7cf39-290">기준, 중요, 매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-290">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="7cf39-291">지침을 보려면 [일반적인 ID 및 장치 액세스 정책](identity-access-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-291">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7cf39-292">지금까지의 구성</span><span class="sxs-lookup"><span data-stu-id="7cf39-292">Your configuration so far</span></span>

<span data-ttu-id="7cf39-293">다음은 새 요소가 강조 표시된 모바일 장치 관리 단계를 시각적으로 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-293">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="7cf39-294">강조 표시된 새 모바일 디바이스 관리 요소에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-294">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="7cf39-295">Intune에 등록된 디바이스에는 Windows 10 Enterprise를 실행하는 온-프레미스 노트북이 예제로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-295">Devices that are enrolled in Intune, showing an on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="7cf39-296">디바이스 준수 및 앱 보호를 위한 Intune 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-296">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="7cf39-297">6단계: 정보 보호</span><span class="sxs-lookup"><span data-stu-id="7cf39-297">Phase 6: Information protection</span></span>

<span data-ttu-id="7cf39-298">Microsoft 365 Enterprise에는 다양한 수준의 관리, 보안 및 보호를 적용하여 데이터 분류를 다르게 처리할 수 있는 정보 보호 기능 호스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-298">Microsoft 365 Enterprise has a host of information protection features that allow you to treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="7cf39-299">예를 들어, 대부분의 직원 간 정규 서신 및 해당 사용자가 작업하는 문서에는 특정한 보호 기준 수준이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-299">For example, normal correspondence between most employees and the documents on which they work need a certain baseline level of protection.</span></span> <span data-ttu-id="7cf39-300">재무 레코드, 고객 데이터 및 지적 재산에는 더 높은 수준의 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-300">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="7cf39-301">정보 보호 전략의 첫 번째 단계는 보호 수준을 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-301">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="7cf39-302">대부분의 조직에서는 이미 조건부 액세스 정책에 사용되고 있는 이 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-302">Many organizations use these levels, which are already being used for conditional access policies:</span></span>

- <span data-ttu-id="7cf39-303">기준</span><span class="sxs-lookup"><span data-stu-id="7cf39-303">Baseline</span></span>

  <span data-ttu-id="7cf39-304">수준 1 데이터의 예로는 관리/영업/지원 담당자의 파일 및 일반적인 업무 관련 통신 내용(전자 메일)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-304">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="7cf39-305">중요</span><span class="sxs-lookup"><span data-stu-id="7cf39-305">Sensitive</span></span>

  <span data-ttu-id="7cf39-306">예로는 새로운 제품 또는 서비스 연구 개발 데이터 및 재무/법률 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-306">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span>

- <span data-ttu-id="7cf39-307">매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="7cf39-307">Highly regulated</span></span>

  <span data-ttu-id="7cf39-308">예로는 고객 및 파트너의 개인 식별 정보와 조직의 재무 정보 또는 지적 재산이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-308">Examples include customer and partner personally identifiable information and your organization’s financial information or intellectual property.</span></span>

<span data-ttu-id="7cf39-309">이 데이터 보안 수준에 따라, 다음 단계는 다음을 식별하고 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-309">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="7cf39-310">사용자 지정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="7cf39-310">Custom sensitive information types</span></span>

  <span data-ttu-id="7cf39-311">Microsoft 365는 상태 서비스, 신용 카드 번호와 같은 중요한 정보 유형을 다양하게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-311">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="7cf39-312">제공 목록에서 필요한 항목을 찾을 수 없는 경우 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-312">If you do not find one that you need in the supplied list, you can create your own.</span></span>

- <span data-ttu-id="7cf39-313">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="7cf39-313">Retention labels</span></span>

  <span data-ttu-id="7cf39-314">조직 정책과 지역별 규정을 준수하려면 특정 유형의 문서 또는 특정 콘텐츠가 담긴 문서를 보존해야 하는 기간을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-314">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="7cf39-315">보존 레이블을 사용하여 전자 메일 및 문서에 대해 이를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-315">You can implement this for email and documents using retention labels.</span></span>

- <span data-ttu-id="7cf39-316">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="7cf39-316">Sensitivity labels</span></span>

  <span data-ttu-id="7cf39-317">추가 보안 수준이 적용될 수 있도록 전자 메일 또는 문서에 지정된 민감도 레이블을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-317">You can label email or documents with a named sensitivity label so that additional levels of security can be applied.</span></span> <span data-ttu-id="7cf39-318">예를 들어 워터 마크, 암호화 및 사용 권한이 있으며, 이는 해당 전자 메일 또는 문서에 액세스할 수 있는 사용자와 수행할 수 있는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-318">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="7cf39-319">자세한 내용은 [Microsoft 365 분류 유형](infoprotect-configure-classification.md#microsoft-365-classification-types)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-319">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="7cf39-320">사용 권한에 민감도 레이블을 사용하는 경우, 추가 Azure AD 보안 그룹을 만들어 전자 메일과 문서를 사용하여 누가 무엇을 할 수 있는지를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-320">If you use sensitivity labels with permissions, you might have to create additional Azure AD security groups to define who is allowed to do what with email and documents.</span></span> 

<span data-ttu-id="7cf39-321">예를 들어, RESEARCH 민감도 레이블을 만들어 리서치 팀의 전자 메일과 문서를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-321">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="7cf39-322">다음 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-322">You determine that:</span></span>

- <span data-ttu-id="7cf39-323">연구원에게 RESEARCH 민감도 레이블로 표시된 문서를 변경할 수 있는 능력이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-323">Researchers must have the ability to change documents marked with the RESEARCH sensitivity label.</span></span>
- <span data-ttu-id="7cf39-324">연구원 이외 직원에게 RESEARCH 민감도 레이블로 표시된 문서를 볼 수 있는 능력만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-324">Non-research employees only need to have the ability to view documents marked with the RESEARCH sensitivity label.</span></span> 

<span data-ttu-id="7cf39-325">즉, 두 개의 추가 그룹을 만들고 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-325">This means you need to create and manage two additional groups:</span></span>

- <span data-ttu-id="7cf39-326">RESEARCH-모두</span><span class="sxs-lookup"><span data-stu-id="7cf39-326">RESEARCH-ALL</span></span>
- <span data-ttu-id="7cf39-327">RESEARCH-보기</span><span class="sxs-lookup"><span data-stu-id="7cf39-327">RESEARCH-VIEW</span></span>

<span data-ttu-id="7cf39-328">이러한 그룹과 해당 사용 권한은 RESEARCH 민감도 레이블에 대한 구성의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-328">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="7cf39-329">그룹 기반 사용 권한으로 구성된 민감도 레이블의 경우, 이 그룹의 구성원 자격을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-329">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7cf39-330">지금까지의 구성</span><span class="sxs-lookup"><span data-stu-id="7cf39-330">Your configuration so far</span></span>

<span data-ttu-id="7cf39-331">다음은 새 요소가 강조 표시된 정보 보호 단계를 시각적으로 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-331">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="7cf39-332">강조 표시된 새 정보 보호 요소에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-332">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="7cf39-333">사용자가 문서에 적용할 수 있는 세 가지 보안 수준에 대한 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-333">Sensitivity labels for the three levels of security that users can apply to documents.</span></span> |
|||

<span data-ttu-id="7cf39-334">사용자 지정 정보 유형 및 보존 레이블은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-334">Custom information types and retention labels are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="7cf39-335">온보딩</span><span class="sxs-lookup"><span data-stu-id="7cf39-335">User Onboarding</span></span>

<span data-ttu-id="7cf39-336">Microsoft 365 Enterprise 인프라를 사용하는 경우 직원을 손쉽게 온보딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-336">With your Microsoft 365 Enterprise infrastructure in place, you can easily onboard your employees.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="7cf39-337">새 Windows 10 Enterprise 디바이스</span><span class="sxs-lookup"><span data-stu-id="7cf39-337">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="7cf39-338">직원에게 새 Windows 10 Enterprise 디바이스를 제공하기 전에:</span><span class="sxs-lookup"><span data-stu-id="7cf39-338">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="7cf39-339">하이브리드 ID의 경우</span><span class="sxs-lookup"><span data-stu-id="7cf39-339">For hybrid identity</span></span>

  <span data-ttu-id="7cf39-340">AD DS에 디바이스를 조인하고, Azure AD 테넌트에 이 디바이스를 조인한 다음, 디바이스를 Intune에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-340">Join the device to your AD DS domain, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

- <span data-ttu-id="7cf39-341">클라우드 전용 ID의 경우</span><span class="sxs-lookup"><span data-stu-id="7cf39-341">For cloud-only identity</span></span>

  <span data-ttu-id="7cf39-342">Microsoft 365 Enterprise 구독의 Azure AD 테넌트에 디바이스를 조인하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-342">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="7cf39-343">AD DS 사용자 계정이 있는 기존 직원</span><span class="sxs-lookup"><span data-stu-id="7cf39-343">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="7cf39-344">하이브리드 ID를 사용하는 경우 조직에 대 한 초기 온보딩의 일부로, AD DS 사용자 계정을 다음 Azure AD 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-344">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="7cf39-345">사용 허가됨</span><span class="sxs-lookup"><span data-stu-id="7cf39-345">Licensed</span></span>
- <span data-ttu-id="7cf39-346">기준, 중요 및 매우 엄격한 규제가 적용되는 Azure AD 그룹의 구성원인 해당 AD DS 또는 Azure AD 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-346">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="7cf39-347">민감도 레이블 그룹(필요한 경우)</span><span class="sxs-lookup"><span data-stu-id="7cf39-347">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="7cf39-348">기존 직원이 해당 작업 그룹, 부서별 및 지역별 AD DS 그룹에 이미 추가되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-348">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

<span data-ttu-id="7cf39-349">Microsoft 365 관리 센터의 여러 Azure AD 그룹에 사용자 계정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-349">You can add a user account to multiple Azure AD groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7cf39-350">사용자 계정의 속성에서 **그룹 관리 > 구성원 자격 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-350">From the properties of the user account, click **Manage groups > Add memberships**.</span></span>

<span data-ttu-id="7cf39-351">Powershell을 사용하려면 이 [다운로드 가능한 Excel 통합 문서](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true)를 참조하여 지정된 사용자 계정 및 선택한 그룹 이름을 기준으로 PowerShell 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-351">If you want to use PowerShell, see this [downloadable Excel workbook](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true), which generates the PowerShell commands based on a specified user account and selected group names.</span></span>

### <a name="new-employee-with-a-cloud-only-user-account"></a><span data-ttu-id="7cf39-352">클라우드 전용 사용자 계정이 있는 신입 직원</span><span class="sxs-lookup"><span data-stu-id="7cf39-352">New employee with a cloud-only user account</span></span>

<span data-ttu-id="7cf39-353">클라우드 전용 ID를 사용하는 경우 조직에 대한 초기 온보딩의 일부로, 새 사용자 계정을 이 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-353">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="7cf39-354">사용 허가됨</span><span class="sxs-lookup"><span data-stu-id="7cf39-354">Licensed</span></span>
- <span data-ttu-id="7cf39-355">기준, 중요 및 매우 엄격한 규제가 적용되는 Azure AD 그룹의 구성원인 해당 Azure AD 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-355">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="7cf39-356">작업 그룹, 부서별 및 지역별 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-356">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="7cf39-357">민감도 레이블 그룹(필요한 경우)</span><span class="sxs-lookup"><span data-stu-id="7cf39-357">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="7cf39-358">Microsoft 365의 초기 로그인</span><span class="sxs-lookup"><span data-stu-id="7cf39-358">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="7cf39-359">직원들이 Microsoft 365에 처음으로 로그인할 때 다음을 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-359">For the first time employees sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="7cf39-360">사용자 계정 자격 증명을 사용하여 디바이스에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-360">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="7cf39-361">브라우저를 사용하여 Office 365 포털 https://portal.office.com에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-361">Using a browser on your local computer, sign in to the Office 365 portal (  ) using your global administrator account.</span></span>
3. <span data-ttu-id="7cf39-362">**Office 365 Home** 탭에서 장치에 Office 365 ProPlus를 설치하려면 **Office 설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-362">From the **Office 365 Home** tab, click **Install Office** to install Office 365 ProPlus on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="7cf39-363">최종 결과</span><span class="sxs-lookup"><span data-stu-id="7cf39-363">End results</span></span>

<span data-ttu-id="7cf39-364">다음은 엔터프라이즈가 아닌 조직을 위한 Microsoft 365 Enterprise 기본 인프라 구성의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-364">Here are the results of configuring the Microsoft 365 Enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="7cf39-365">인프라 결과</span><span class="sxs-lookup"><span data-stu-id="7cf39-365">Infrastructure results</span></span>

<span data-ttu-id="7cf39-366">Microsoft 365 Enterprise 인프라를 빌드하고 구성한 후에는 다음이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-366">After the build-out and configuration of your Microsoft 365 Enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="7cf39-367">지리적 로컬 DNS 서버를 사용하는 ISP가 충분하게 공급되는 각 사무소에 로컬 인터넷 연결이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-367">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="7cf39-368">하이브리드 ID의 경우, 온-프레미스 AD DS 도메인을 Azure AD 테넌트와 동기화하는 서버에서 Azure AD Connect를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-368">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="7cf39-369">이 그룹:</span><span class="sxs-lookup"><span data-stu-id="7cf39-369">These universal groups include:</span></span>
  - <span data-ttu-id="7cf39-370">사용 허가됨</span><span class="sxs-lookup"><span data-stu-id="7cf39-370">Licensed</span></span>
  - <span data-ttu-id="7cf39-371">조건-액세스-제외</span><span class="sxs-lookup"><span data-stu-id="7cf39-371">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="7cf39-372">기준, 중요 및 매우 엄격한 규제가 적용되는 Azure AD 그룹의 구성원이기도 한 해당 AD DS 또는 Azure AD 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-372">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="7cf39-373">작업 그룹, 부서별 및 지역별 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-373">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="7cf39-374">민감도 레이블 그룹(필요한 경우)</span><span class="sxs-lookup"><span data-stu-id="7cf39-374">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="7cf39-375">BASELINE, SENSITIVE, and HIGHLY-REGULATED 및 COND-ACCESS-EXCLUDE Azure AD 그룹을 사용하는 Azure AD 로그인 조건부 액세스 정책.</span><span class="sxs-lookup"><span data-stu-id="7cf39-375">Azure AD sign-in conditional access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="7cf39-376">Intune 응용 프로그램 및 장치 규정 준수 정책.</span><span class="sxs-lookup"><span data-stu-id="7cf39-376">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="7cf39-377">사용자 지정 중요한 정보 유형(필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="7cf39-377">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="7cf39-378">보존 레이블(필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="7cf39-378">Retention labels (as needed).</span></span>
- <span data-ttu-id="7cf39-379">민감도 레이블(필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="7cf39-379">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="7cf39-380">조직에서 AD DS 도메인, Azure AD Connect 서버 및 동기화된 AD DS 사용자 및 그룹을 포함하는 하이브리드 ID를 사용하는 경우 인프라를 시각적으로 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-380">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="7cf39-381">조직에서 클라우드 전용 ID를 사용하는 경우 인프라를 시각적으로 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-381">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![](./media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="7cf39-382">직원 결과</span><span class="sxs-lookup"><span data-stu-id="7cf39-382">Employee results</span></span>

<span data-ttu-id="7cf39-383">온보딩 후 직원마다 다음이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-383">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="7cf39-384">직원의 장치에서 해당 지역의 Microsoft 365 클라우드 서비스까지의 고성능 온-프레미스 네트워크 경로.</span><span class="sxs-lookup"><span data-stu-id="7cf39-384">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="7cf39-385">다음 그룹 구성원 자격이 있는 사용자 계정:</span><span class="sxs-lookup"><span data-stu-id="7cf39-385">A user account with these group memberships:</span></span>
   - <span data-ttu-id="7cf39-386">사용 허가됨</span><span class="sxs-lookup"><span data-stu-id="7cf39-386">Licensed</span></span>
   - <span data-ttu-id="7cf39-387">조건부 액세스 정책의 BASELINE, SENSITIVE 및 HIGHLY-REGULATED Azure AD 그룹의 구성원인 해당 AD DS 또는 Azure AD 보안 그룹.</span><span class="sxs-lookup"><span data-stu-id="7cf39-387">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for conditional access policies</span></span> 
   - <span data-ttu-id="7cf39-388">해당 작업 그룹, 부서별 및 지역별 그룹</span><span class="sxs-lookup"><span data-stu-id="7cf39-388">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="7cf39-389">민감도 레이블 그룹(필요한 경우)</span><span class="sxs-lookup"><span data-stu-id="7cf39-389">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="7cf39-390">Windows 10 Enterprise 장치:</span><span class="sxs-lookup"><span data-stu-id="7cf39-390">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="7cf39-391">Azure AD 테넌트(클라우드 전용) 또는 Azure AD 테넌트와 AD DS 도메인(하이브리드) 양쪽에 조인됨.</span><span class="sxs-lookup"><span data-stu-id="7cf39-391">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="7cf39-392">최신 Windows 10 Enterprise 제품 개선 사항 및 보안 기능 향상으로 자동 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-392">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="7cf39-393">Office 365 ProPlus가 설치되어 있으며, 최신 Office 제품 개선 사항 및 보안 기능 향상으로 자동 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-393">Has Office 365 ProPlus installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="7cf39-394">Intune에 등록되고 Intune 장치 준수 정책 및 앱 보호 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf39-394">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="7cf39-395">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7cf39-395">Next step</span></span>

<span data-ttu-id="7cf39-396">[워크로드와 시나리오](deploy-workloads.md)를 배포하여 Microsoft 365 Enterprise 기본 인프라의 기능과 구성을 최대한 활용하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf39-396">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
