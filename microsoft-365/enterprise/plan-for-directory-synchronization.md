---
title: Microsoft 365에 대한 하이브리드 ID 및 디렉터리 동기화
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
description: Microsoft 365, Active Directory 도메인 서비스 정리 및 Azure Active Directory Connect 도구와의 디렉터리 동기화에 대해 설명합니다.
ms.openlocfilehash: 02b594f9db02df7e855a20dfc65b21ab2dbe91c0
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327382"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="611f0-103">Microsoft 365에 대한 하이브리드 ID 및 디렉터리 동기화</span><span class="sxs-lookup"><span data-stu-id="611f0-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="611f0-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="611f0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="611f0-105">비즈니스 요구 사항 및 기술 요구 사항에 따라 Microsoft 365를 채택하는 엔터프라이즈 고객에게는 하이브리드 ID 모델 및 디렉터리 동기화가 가장 일반적인 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="611f0-106">디렉터리 동기화를 사용하면 AD DS(Active Directory 도메인 서비스)에서 ID를 관리할 수 있으며 사용자 계정, 그룹 및 연락처에 대한 모든 업데이트가 Microsoft 365 구독의 Azure AD(Azure Active Directory) 테넌트와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="611f0-107">AD DS 사용자 계정이 처음으로 동기화되는 경우 Microsoft 365 라이선스가 자동으로 할당되지는 않습니다. 전자 메일과 같은 Microsoft 365 서비스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="611f0-108">먼저 사용 위치를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-108">You must first assign them a usage location.</span></span> <span data-ttu-id="611f0-109">그런 다음 그룹 구성원 자격을 통해 개별적으로 또는 동적으로 이러한 사용자 계정에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="611f0-110">하이브리드 ID에 대한 인증</span><span class="sxs-lookup"><span data-stu-id="611f0-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="611f0-111">하이브리드 ID 모델을 사용하는 경우 다음 두 가지 인증 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="611f0-112">관리되는 인증</span><span class="sxs-lookup"><span data-stu-id="611f0-112">Managed authentication</span></span>

  <span data-ttu-id="611f0-113">Azure AD는 로컬에 저장된 해시된 암호 버전을 사용하여 인증 프로세스를 처리하거나, 자격 증명을 프레미스 소프트웨어 에이전트에 전송하여 해당 자격 증명을 전송하여 해당 인증서를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="611f0-114">페더레이션 인증</span><span class="sxs-lookup"><span data-stu-id="611f0-114">Federated authentication</span></span>

  <span data-ttu-id="611f0-115">Azure AD는 인증을 요청하는 클라이언트 컴퓨터를 다른 ID 공급자로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="611f0-116">관리되는 인증</span><span class="sxs-lookup"><span data-stu-id="611f0-116">Managed authentication</span></span>

<span data-ttu-id="611f0-117">관리되는 인증에는 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="611f0-118">PHS(암호 해시 동기화)</span><span class="sxs-lookup"><span data-stu-id="611f0-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="611f0-119">Azure AD는 인증 자체를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="611f0-120">통과 인증(PTA)</span><span class="sxs-lookup"><span data-stu-id="611f0-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="611f0-121">Azure AD에는 AD DS가 인증을 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="611f0-122">PHS(암호 해시 동기화)</span><span class="sxs-lookup"><span data-stu-id="611f0-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="611f0-123">PHS를 사용하여 AD DS 사용자 계정을 Microsoft 365와 동기화하고 사용자를 On-premises에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="611f0-124">사용자 암호 해시가 AD DS에서 Azure AD로 동기화되어 사용자가 동일한 암호를 On-premises와 클라우드에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="611f0-125">Azure AD에서 AD DS ID에 대한 인증을 사용하도록 설정하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![PHS(암호 해시 동기화)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="611f0-127">암호가 변경되거나 다시 설정되면 새 암호 해시가 Azure AD와 동기화되어 사용자가 항상 클라우드 리소스 및 On-premises 리소스에 대해 동일한 암호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="611f0-128">사용자 암호는 Azure AD로 전송되거나 Azure AD에 명확한 텍스트로 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="611f0-129">ID 보호와 같은 Azure AD의 일부 고급 기능에는 어떤 인증 방법이 선택되어 있는지와 관계없이 PHS가 필요하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="611f0-130">자세한 [내용은 올바른](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-130">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="611f0-131">통과 인증(PTA)</span><span class="sxs-lookup"><span data-stu-id="611f0-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="611f0-132">PTA는 하나 이상의 ON-프레미스 서버에서 실행되는 소프트웨어 에이전트를 사용하여 AD DS를 통해 직접 사용자의 유효성을 검사하는 Azure AD 인증 서비스에 대한 간단한 암호 유효성 검사를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="611f0-133">PTA를 사용하면 AD DS 사용자 계정을 Microsoft 365와 동기화하고 사용자를 On-premises에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![통과 인증(PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="611f0-135">PTA를 사용하면 사용자가 자신의 On-프레미스 계정과 암호를 사용하여 Microsoft 365 리소스와 응용 프로그램 모두에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="611f0-136">이 구성은 Azure AD에 암호 해시를 저장하지 않고도 사용자 암호의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="611f0-137">PTA는 또한 보안 요구 사항이 있는 조직에 대해 즉각적으로온-프레미스 사용자 계정 상태, 암호 정책 및 로그온 시간을 적용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="611f0-138">자세한 [내용은 올바른](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-138">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="611f0-139">페더레이션 인증</span><span class="sxs-lookup"><span data-stu-id="611f0-139">Federated authentication</span></span>

<span data-ttu-id="611f0-140">페더타 인증은 주로 보다 복잡한 인증 요구 사항이 있는 대기업 조직을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="611f0-141">AD DS ID는 Microsoft 365와 동기화되고 사용자 계정은 프레미스에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="611f0-142">페더전된 인증을 사용하는 경우 사용자는 동일한 암호를 On-premises 및 클라우드에서 사용할 수 있으며 Microsoft 365를 사용하기 위해 다시 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="611f0-143">페더타 인증은 스마트 카드 기반 인증 또는 타사 다단계 인증과 같은 추가 인증 요구 사항을 지원할 수 있으며, 일반적으로 조직에서 Azure AD에서 기본적으로 지원하지 않는 인증 요구 사항이 있는 경우 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="611f0-144">자세한 [내용은 올바른](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-144">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="611f0-145">타사 인증 및 ID 공급자</span><span class="sxs-lookup"><span data-stu-id="611f0-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="611f0-146">Microsoft 365와 동기화할 수 있으며 클라우드 리소스 액세스는 주로 타사 IdP(ID 공급자)에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="611f0-147">조직에서 타사 페더전 솔루션을 사용하는 경우 타사 페더러ation 솔루션이 Azure AD와 호환되는 경우 해당 솔루션으로 Microsoft 365에 대한 로그인을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="611f0-148">자세한 내용은 [Azure AD 페더ation 호환성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="611f0-148">See the [Azure AD federation compatibility list](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="611f0-149">AD DS 준비</span><span class="sxs-lookup"><span data-stu-id="611f0-149">AD DS Preparation</span></span>

<span data-ttu-id="611f0-150">동기화를 사용하여 Microsoft 365로 원활하게 전환하려면 Microsoft 365 디렉터리 동기화 배포를 시작하기 전에 AD DS 포리스트를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="611f0-151">디렉터리 준비는 다음 작업에 중점을 두야 합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="611f0-152">중복 **proxyAddress** 및 **userPrincipalName 특성을** 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="611f0-153">유효한 **userPrincipalName** 특성으로 비어 있으며 잘못된 **userPrincipalName 특성을** 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="611f0-154">**givenName, surname** **(sn),** **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname** 및 **userPrincipalName** 특성에서 유효하지 않은 문자와 의심할 수 있는 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="611f0-155">특성을 준비하는 데 대한 자세한 내용은 Azure Active Directory 동기화 도구로 동기화된 특성 [목록을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=396719)</span><span class="sxs-lookup"><span data-stu-id="611f0-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="611f0-156">Azure AD Connect가 동기화하는 특성과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="611f0-157">다중 포리스트 배포 고려 사항</span><span class="sxs-lookup"><span data-stu-id="611f0-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="611f0-158">여러 포리스트 및 SSO 옵션의 경우 Azure AD Connect의 사용자 지정 [설치를 사용하세요.](https://go.microsoft.com/fwlink/p/?LinkId=698430)</span><span class="sxs-lookup"><span data-stu-id="611f0-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>
  
<span data-ttu-id="611f0-159">조직에 인증용 포리스트가 여러 개 있는 경우(로그온 포리스트) 다음을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="611f0-160">**포리스트 통합을 고려합니다.**</span><span class="sxs-lookup"><span data-stu-id="611f0-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="611f0-161">일반적으로 여러 포리스트를 유지 관리하는 데 더 많은 오버헤드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="611f0-162">조직에 별도의 포리스트의 필요성을 요구하는 보안 제약 조건이 없는 경우,프레미스 환경을 단순화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="611f0-163">**기본 로그온 포리스트에서만 사용**</span><span class="sxs-lookup"><span data-stu-id="611f0-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="611f0-164">Microsoft 365의 초기 롤아웃을 위해 기본 로그온 포리스트에만 Microsoft 365를 배포하는 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="611f0-165">다중 포리스트 AD DS 배포를 통합할 수 없는 경우 또는 다른 디렉터리 서비스를 사용하여 ID를 관리하는 경우 Microsoft 또는 파트너의 도움을 통해 이러한 디렉터리를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="611f0-166">자세한 [내용은 Azure AD Connect에 대한](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) 토폴로지에서 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="611f0-166">See [Topologies for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="611f0-167">디렉터리 동기화에 종속된 기능</span><span class="sxs-lookup"><span data-stu-id="611f0-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="611f0-168">다음 기능을 사용하려면 디렉터리 동기화가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="611f0-169">Azure AD Seamless Single Sign-On(SSO)</span><span class="sxs-lookup"><span data-stu-id="611f0-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="611f0-170">Skype 공존성</span><span class="sxs-lookup"><span data-stu-id="611f0-170">Skype coexistence</span></span>
- <span data-ttu-id="611f0-171">다음을 비롯한 Exchange 하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="611f0-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="611f0-172">온-프레미스 Exchange 환경과 Microsoft 365 간에 완전히 공유된 GAL(전체 주소 목록)입니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="611f0-173">여러 메일 시스템에서 GAL 정보를 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="611f0-174">Microsoft 365 서비스 제품에서 사용자를 추가하고 제거할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="611f0-175">이렇게 하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-175">This requires the following:</span></span>
  - <span data-ttu-id="611f0-176">디렉터리 동기화를 설정하는 동안 양측 동기화를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="611f0-177">기본적으로 디렉터리 동기화 도구는 디렉터리 정보를 클라우드에만 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="611f0-178">양자 동기화를 구성할 때 제한된 수의 개체 특성이 클라우드에서 복사되도록 쓰기 저장 기능을 사용하도록 설정한 다음 로컬 AD DS에 다시 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="611f0-179">쓰기 기록을 Exchange 하이브리드 모드라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="611f0-180">On-premises Exchange hybrid deployment</span><span class="sxs-lookup"><span data-stu-id="611f0-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="611f0-181">일부 사용자 사서함을 Microsoft 365로 이동하는 동시에 다른 사용자 사서함을 On-premises로 유지하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="611f0-182">수신 수신이 차단된 보낸 사람 및 수신 차단된 보낸 사람은 Microsoft 365로 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="611f0-183">기본 위임 및 전자 메일 대신 보내기 기능</span><span class="sxs-lookup"><span data-stu-id="611f0-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="611f0-184">통합된 On-premises 스마트 카드 또는 다단계 인증 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611f0-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="611f0-185">사진, 미리 보기, 회의실 및 보안 그룹 동기화</span><span class="sxs-lookup"><span data-stu-id="611f0-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="611f0-186">다음 단계</span><span class="sxs-lookup"><span data-stu-id="611f0-186">Next step</span></span>

<span data-ttu-id="611f0-187">하이브리드 ID를 배포할 준비가 되면 디렉터리 동기화 [준비를 참조합니다.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="611f0-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
  
