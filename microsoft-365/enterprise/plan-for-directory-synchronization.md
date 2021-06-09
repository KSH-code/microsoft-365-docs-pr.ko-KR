---
title: 하이브리드 ID 및 디렉터리 동기화를 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Active Directory 도메인 서비스 정리 및 Microsoft 365 도구와의 디렉터리 동기화에 Azure Active Directory 커넥트 설명
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927547"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="37267-103">하이브리드 ID 및 디렉터리 동기화를 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="37267-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="37267-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="37267-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="37267-105">비즈니스 요구 사항 및 기술 요구 사항에 따라 하이브리드 ID 모델 및 디렉터리 동기화는 비즈니스 요구 사항을 채택하는 엔터프라이즈 고객에게 가장 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37267-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="37267-106">디렉터리 동기화를 통해 AD DS(Active Directory 도메인 서비스)의 ID를 관리할 수 있으며 사용자 계정, 그룹 및 연락처에 대한 모든 업데이트가 Azure Active Directory 구독의 Azure AD(Azure Active Directory) 테넌트와 Microsoft 365 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="37267-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="37267-107">AD DS 사용자 계정이 처음으로 동기화되는 경우 사용자에게 Microsoft 365 라이선스가 자동으로 할당되지 Microsoft 365 서비스와 같은 서비스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="37267-108">먼저 사용 위치를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-108">You must first assign them a usage location.</span></span> <span data-ttu-id="37267-109">그런 다음 그룹 구성원 자격을 통해 개별적으로 또는 동적으로 이러한 사용자 계정에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="37267-110">하이브리드 ID에 대한 인증</span><span class="sxs-lookup"><span data-stu-id="37267-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="37267-111">하이브리드 ID 모델을 사용하는 경우 두 가지 인증 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="37267-112">관리되는 인증</span><span class="sxs-lookup"><span data-stu-id="37267-112">Managed authentication</span></span>

  <span data-ttu-id="37267-113">Azure AD는 로컬에 저장된 해시된 버전의 암호를 사용하여 인증 프로세스를 처리하거나, 자격 증명을 사내 소프트웨어 에이전트로 전송하여 인증 프로세스를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="37267-114">페더레이션 인증</span><span class="sxs-lookup"><span data-stu-id="37267-114">Federated authentication</span></span>

  <span data-ttu-id="37267-115">Azure AD는 인증을 요청하는 클라이언트 컴퓨터를 다른 ID 공급자로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="37267-116">관리되는 인증</span><span class="sxs-lookup"><span data-stu-id="37267-116">Managed authentication</span></span>

<span data-ttu-id="37267-117">관리되는 인증에는 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="37267-118">PHS(암호 해시 동기화)</span><span class="sxs-lookup"><span data-stu-id="37267-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="37267-119">Azure AD는 인증 자체를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="37267-120">통과 인증(PTA)</span><span class="sxs-lookup"><span data-stu-id="37267-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="37267-121">Azure AD에는 AD DS가 인증을 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="37267-122">PHS(암호 해시 동기화)</span><span class="sxs-lookup"><span data-stu-id="37267-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="37267-123">PHS를 사용하여 AD DS 사용자 계정을 Microsoft 365 사용자와 동기화하고 사용자를 사내에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="37267-124">사용자 암호 해시가 AD DS에서 Azure AD로 동기화되어 사용자가 동일한 암호를 사내 및 클라우드에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="37267-125">Azure AD에서 AD DS ID에 대한 인증을 사용하도록 설정하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="37267-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![PHS(암호 해시 동기화)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="37267-127">암호가 변경되거나 다시 설정되면 새 암호 해시가 Azure AD와 동기화되어 사용자가 클라우드 리소스 및 사내 리소스에 대해 항상 동일한 암호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="37267-128">사용자 암호는 Azure AD로 전송되거나 Azure AD에 명확한 텍스트로 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="37267-129">ID 보호와 같은 Azure AD의 일부 프리미엄 기능에는 선택한 인증 방법에 관계없이 PHS가 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="37267-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="37267-130">자세한 [내용은 올바른](/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="37267-131">통과 인증(PTA)</span><span class="sxs-lookup"><span data-stu-id="37267-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="37267-132">PTA는 하나 이상의 사내 서버에서 실행되는 소프트웨어 에이전트를 사용하여 AD DS를 통해 직접 사용자의 유효성을 검사하는 Azure AD 인증 서비스에 대한 간단한 암호 유효성 검사를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="37267-133">PTA를 사용하면 AD DS 사용자 계정을 Microsoft 365 사용자와 동기화하고 Microsoft 365 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![통과 인증(PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="37267-135">PTA를 사용하면 사용자가 자신의 프레미스 계정과 암호를 사용하여 Microsoft 365 및 응용 프로그램 모두에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="37267-136">이 구성은 Azure AD에 암호 해시를 저장하지 않고 사용자 암호의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="37267-137">PTA는 또한 보안 요구 사항이 있는 조직을 위해 바로 사내 사용자 계정 상태, 암호 정책 및 로그온 시간을 적용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37267-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="37267-138">자세한 [내용은 올바른](/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="37267-139">페더레이션 인증</span><span class="sxs-lookup"><span data-stu-id="37267-139">Federated authentication</span></span>

<span data-ttu-id="37267-140">페더러드 인증은 주로 보다 복잡한 인증 요구 사항이 있는 대기업 조직을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37267-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="37267-141">AD DS ID는 Microsoft 365 동기화되고 사용자 계정은 사내에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="37267-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="37267-142">페더러드 인증을 사용하는 경우 사용자는 동일한 암호를 사내 및 클라우드에서 사용할 수 있으며, 이 인증을 사용하기 위해 다시 로그인할 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37267-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="37267-143">페더타 인증은 스마트 카드 기반 인증 또는 타사 다단계 인증과 같은 추가 인증 요구 사항을 지원할 수 있으며 일반적으로 조직에서 Azure AD에서 기본적으로 지원하지 않는 인증 요구 사항이 있는 경우 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="37267-144">자세한 [내용은 올바른](/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="37267-145">타사 인증 및 ID 공급자</span><span class="sxs-lookup"><span data-stu-id="37267-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="37267-146">클라우드 리소스 액세스는 기본적으로 타사 IdP(Microsoft 365 공급자)에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="37267-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="37267-147">조직에서 타사 페더전 솔루션을 사용하는 경우 타사 페더러ation 솔루션이 Azure AD와 호환되는 경우 Microsoft 365 해당 솔루션과의 로그인을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="37267-148">자세한 내용은 [Azure AD 페더ation 호환성](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37267-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="37267-149">AD DS 준비</span><span class="sxs-lookup"><span data-stu-id="37267-149">AD DS Preparation</span></span>

<span data-ttu-id="37267-150">동기화를 사용하여 Microsoft 365 원활하게 전환하려면 디렉터리 동기화 배포를 시작하기 전에 AD DS 포리스트를 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="37267-151">디렉터리 준비는 다음 작업에 중점을 두야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="37267-152">중복 **proxyAddress** 및 **userPrincipalName 특성을** 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="37267-153">유효한 **userPrincipalName** 특성으로 비어 있으며 잘못된 **userPrincipalName** 특성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="37267-154">**givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname** 및 **userPrincipalName** 특성에서 유효하지 않은 문자와 의심할 수 있는 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="37267-155">특성을 준비하는 데 대한 자세한 내용은 동기화 도구에서 동기화되는 특성 [Azure Active Directory 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=396719)</span><span class="sxs-lookup"><span data-stu-id="37267-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="37267-156">이러한 특성은 Azure AD에서 동기화하는 커넥트 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="37267-157">다중 포리스트 배포 고려 사항</span><span class="sxs-lookup"><span data-stu-id="37267-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="37267-158">여러 포리스트 및 SSO 옵션의 경우 Azure AD 2013의 사용자 지정 [설치를 커넥트.](/azure/active-directory/hybrid/how-to-connect-install-custom)</span><span class="sxs-lookup"><span data-stu-id="37267-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="37267-159">조직에 인증을 위한 포리스트가 여러 개 있는 경우(로그온 포리스트) 다음을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="37267-160">**포리스트 통합을 고려합니다.**</span><span class="sxs-lookup"><span data-stu-id="37267-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="37267-161">일반적으로 여러 포리스트를 유지 관리하는 데 더 많은 오버헤드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="37267-162">조직에 별도의 포리스트의 필요성을 요구하는 보안 제약 조건이 없는 경우, 사내 환경을 단순화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="37267-163">**기본 로그온 포리스트에서만 사용**</span><span class="sxs-lookup"><span data-stu-id="37267-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="37267-164">초기 로그온 Microsoft 365 포리스트에만 배포하는 것이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37267-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="37267-165">다중 포리스트 AD DS 배포를 통합할 수 없는 경우 또는 다른 디렉터리 서비스를 사용하여 ID를 관리하는 경우 Microsoft 또는 파트너의 도움을 통해 이러한 디렉터리를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="37267-166">자세한 [내용은 Azure AD 커넥트](/azure/active-directory/hybrid/plan-connect-topologies) 토폴로지 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37267-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="37267-167">디렉터리 동기화에 종속된 기능</span><span class="sxs-lookup"><span data-stu-id="37267-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="37267-168">디렉터리 동기화는 다음과 같은 기능을 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="37267-169">Azure AD Seamless SSO(Single Sign-On)</span><span class="sxs-lookup"><span data-stu-id="37267-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="37267-170">Skype 동시 사용</span><span class="sxs-lookup"><span data-stu-id="37267-170">Skype coexistence</span></span>
- <span data-ttu-id="37267-171">Exchange 다음을 비롯한 하이브리드 배포를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="37267-172">온-프레미스 환경과 Exchange GAL(전체 주소 목록) Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37267-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="37267-173">여러 메일 시스템에서 GAL 정보를 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="37267-174">사용자 추가 및 서비스 제공에서 사용자를 Microsoft 365 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="37267-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="37267-175">이렇게 하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-175">This requires the following:</span></span>
  - <span data-ttu-id="37267-176">디렉터리 동기화 설정 중에 양측 동기화를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="37267-177">기본적으로 디렉터리 동기화 도구는 디렉터리 정보를 클라우드에만 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="37267-178">양자 동기화를 구성할 때 제한된 수의 개체 특성이 클라우드에서 복사되도록 쓰기 저장 기능을 사용하도록 설정한 다음 로컬 AD DS에 다시 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="37267-179">쓰기 쓰기 기능을 하이브리드 모드라고도 Exchange 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="37267-180">하이브리드 배포를 위한 Exchange 프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="37267-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="37267-181">일부 사용자 사서함을 이동하여 다른 Microsoft 365 사서함을 Microsoft 365 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37267-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="37267-182">안전한 보낸 사람 및 수신이 차단된 보낸 사람에 대한 모든 메시지는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37267-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="37267-183">기본 위임 및 전자 메일 대신 보내기 기능</span><span class="sxs-lookup"><span data-stu-id="37267-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="37267-184">통합된 사내 스마트 카드 또는 다단계 인증 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37267-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="37267-185">사진, 미리 보기, 회의실 및 보안 그룹 동기화</span><span class="sxs-lookup"><span data-stu-id="37267-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="37267-186">다음 단계</span><span class="sxs-lookup"><span data-stu-id="37267-186">Next step</span></span>

<span data-ttu-id="37267-187">하이브리드 ID를 배포할 준비가 되면 디렉터리 동기화 [준비를 참조합니다.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="37267-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
