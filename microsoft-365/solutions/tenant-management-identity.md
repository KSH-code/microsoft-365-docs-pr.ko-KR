---
title: 3단계. 엔터프라이즈 테넌트의 Microsoft 365 ID
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 테넌트에 대한 올바른 ID 모델을 Microsoft 365 강력한 사용자 로그인을 적용합니다.
ms.openlocfilehash: 57e84b38715c4fbe29f9aa362e363663b0401f91
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052365"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="d72b6-104">3단계.</span><span class="sxs-lookup"><span data-stu-id="d72b6-104">Step 3.</span></span> <span data-ttu-id="d72b6-105">엔터프라이즈 테넌트의 Microsoft 365 ID</span><span class="sxs-lookup"><span data-stu-id="d72b6-105">Identity for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="d72b6-106">Microsoft 365 테넌트에는 로그인에 대한 ID 및 인증을 Azure Active Directory(Azure AD) 테넌트가 포함되어 있습니다. ID 인프라를 올바르게 구성하는 것은 조직에 대한 사용자 액세스 및 Microsoft 365 관리하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-106">Your Microsoft 365 tenant includes an Azure Active Directory (Azure AD) tenant to manage identities and authentication for sign-ins. Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

## <a name="cloud-only-vs-hybrid"></a><span data-ttu-id="d72b6-107">클라우드 전용과 하이브리드 비교</span><span class="sxs-lookup"><span data-stu-id="d72b6-107">Cloud-only vs. hybrid</span></span>

<span data-ttu-id="d72b6-108">다음은 두 가지 유형의 ID 모델과 가장 잘 맞는 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-108">Here are the two types of identity models and their best fit and benefits.</span></span>


| <span data-ttu-id="d72b6-109">모델</span><span class="sxs-lookup"><span data-stu-id="d72b6-109">Model</span></span> | <span data-ttu-id="d72b6-110">설명</span><span class="sxs-lookup"><span data-stu-id="d72b6-110">Description</span></span> | <span data-ttu-id="d72b6-111">사용자 Microsoft 365 인증하는 방법</span><span class="sxs-lookup"><span data-stu-id="d72b6-111">How Microsoft 365 authenticates user credentials</span></span> | <span data-ttu-id="d72b6-112">최적 시나리오</span><span class="sxs-lookup"><span data-stu-id="d72b6-112">Best for</span></span> | <span data-ttu-id="d72b6-113">가장 큰 혜택</span><span class="sxs-lookup"><span data-stu-id="d72b6-113">Greatest benefit</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d72b6-114">클라우드 전용</span><span class="sxs-lookup"><span data-stu-id="d72b6-114">Cloud-only</span></span> | <span data-ttu-id="d72b6-115">사용자 계정은 사용자 테넌트의 Azure AD 테넌트에만 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-115">User account only exists in the Azure AD tenant for your Microsoft 365 tenant.</span></span> | <span data-ttu-id="d72b6-116">테넌트의 Azure AD Microsoft 365 클라우드 ID 계정으로 인증을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-116">The Azure AD tenant for your Microsoft 365 tenant performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="d72b6-117">사내 AD DS가 필요하지 않은 조직.</span><span class="sxs-lookup"><span data-stu-id="d72b6-117">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="d72b6-118">사용하기 간편합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-118">Simple to use.</span></span> <span data-ttu-id="d72b6-119">추가 디렉터리 도구 또는 서버는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-119">No extra directory tools or servers required.</span></span> |
| <span data-ttu-id="d72b6-120">하이브리드</span><span class="sxs-lookup"><span data-stu-id="d72b6-120">Hybrid</span></span> |  <span data-ttu-id="d72b6-121">사용자 계정이 AD DS(Active Directory 도메인 서비스)에 있으며 복사본은 Microsoft 365 테넌트의 Azure AD 테넌트에도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-121">User account exists in your on-premises Active Directory Domain Services (AD DS) and a copy is also in the Azure AD tenant for your Microsoft 365 tenant.</span></span> <span data-ttu-id="d72b6-122">Azure AD 커넥트 AD DS 변경 내용을 Azure AD 테넌트와 동기화하기 위해 사내 서버에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-122">Azure AD Connect runs on an on-premises server to synchronize AD DS changes to your Azure AD tenant.</span></span> <span data-ttu-id="d72b6-123">Azure AD의 사용자 계정에 이미 해시된 AD DS 사용자 계정 암호의 해시된 버전이 포함되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-123">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> | <span data-ttu-id="d72b6-124">테넌트의 Azure AD Microsoft 365 인증 프로세스를 처리하거나 사용자를 다른 ID 공급자로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-124">The Azure AD tenant for your Microsoft 365 tenant either handles the authentication process or redirects the user to another identity provider.</span></span> | <span data-ttu-id="d72b6-125">AD DS 또는 다른 ID 공급자를 사용하는 조직</span><span class="sxs-lookup"><span data-stu-id="d72b6-125">Organizations using AD DS or another identity provider.</span></span> | <span data-ttu-id="d72b6-126">사용자는 사내 또는 클라우드 기반 리소스에 액세스할 때 동일한 자격 증명을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-126">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||||

<span data-ttu-id="d72b6-127">다음은 클라우드 전용 ID의 기본 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-127">Here are the basic components of cloud-only identity.</span></span>
 
![클라우드 전용 ID의 기본 구성 요소](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="d72b6-129">이 그림에서 사내 및 원격 사용자는 해당 테넌트의 Azure AD 테넌트에 있는 계정으로 Microsoft 365 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-129">In this illustration, on-premises and remote users sign in with accounts in the Azure AD tenant of their Microsoft 365 tenant.</span></span>

<span data-ttu-id="d72b6-130">다음은 하이브리드 ID의 기본 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-130">Here are the basic components of hybrid identity.</span></span>

![하이브리드 ID의 기본 구성 요소](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="d72b6-132">이 그림에서, 사내 및 원격 사용자는 자신의 Microsoft 365 AD DS에서 복사된 Azure AD 테넌트의 계정을 사용하여 자신의 Microsoft 365 테넌트에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-132">In this illustration, on-premises and remote users sign in to their Microsoft 365 tenant with accounts in the Azure AD tenant that have been copied from their on-premises AD DS.</span></span>

## <a name="synchronizing-your-on-premises-ad-ds"></a><span data-ttu-id="d72b6-133">프레미스 AD DS 동기화</span><span class="sxs-lookup"><span data-stu-id="d72b6-133">Synchronizing your on-premises AD DS</span></span>

<span data-ttu-id="d72b6-134">비즈니스 요구 사항 및 기술 요구 사항에 따라 하이브리드 ID 모델 및 디렉터리 동기화는 비즈니스 요구 사항을 채택하는 엔터프라이즈 고객에게 가장 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d72b6-134">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="d72b6-135">디렉터리 동기화를 사용하면 AD DS의 ID를 관리할 수 있으며 사용자 계정, 그룹 및 연락처에 대한 모든 업데이트가 Microsoft 365 테넌트의 Azure AD 테넌트와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-135">Directory synchronization allows you to manage identities in your AD DS and all updates to user accounts, groups, and contacts are synchronized to the Azure AD tenant of your Microsoft 365 tenant.</span></span>

>[!Note]
><span data-ttu-id="d72b6-136">AD DS 사용자 계정이 처음으로 동기화되는 경우 사용자에게 Microsoft 365 라이선스가 자동으로 할당되지 Microsoft 365 서비스와 같은 서비스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-136">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="d72b6-137">먼저 사용 위치를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-137">You must first assign them a usage location.</span></span> <span data-ttu-id="d72b6-138">그런 다음 그룹 구성원 자격을 통해 개별적으로 또는 동적으로 이러한 사용자 계정에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-138">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

<span data-ttu-id="d72b6-139">다음은 하이브리드 ID 모델을 사용할 때의 두 가지 인증 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-139">Here are the two types of authentication when using the hybrid identity model.</span></span>

| <span data-ttu-id="d72b6-140">인증 유형</span><span class="sxs-lookup"><span data-stu-id="d72b6-140">Authentication type</span></span> | <span data-ttu-id="d72b6-141">설명</span><span class="sxs-lookup"><span data-stu-id="d72b6-141">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="d72b6-142">관리되는 인증</span><span class="sxs-lookup"><span data-stu-id="d72b6-142">Managed authentication</span></span> | <span data-ttu-id="d72b6-143">Azure AD는 로컬에 저장된 해시된 버전의 암호를 사용하여 인증 프로세스를 처리하거나, 자격 증명을 사내 소프트웨어 에이전트로 전송하여 인증 프로세스를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-143">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span> <br> <br>  <span data-ttu-id="d72b6-144">관리되는 인증에는 PHS(암호 해시 동기화) 및 PTA(통과 인증)의 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-144">There are two types of managed authentication: Password hash synchronization (PHS) and Pass-through authentication (PTA).</span></span> <span data-ttu-id="d72b6-145">PHS를 사용하여 Azure AD는 인증 자체를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-145">With PHS, Azure AD performs the authentication itself.</span></span> <span data-ttu-id="d72b6-146">PTA를 사용하는 경우 Azure AD에는 AD DS가 인증을 수행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-146">With PTA, Azure AD has AD DS perform the authentication.</span></span> |
| <span data-ttu-id="d72b6-147">페더레이션 인증</span><span class="sxs-lookup"><span data-stu-id="d72b6-147">Federated authentication</span></span> | <span data-ttu-id="d72b6-148">Azure AD는 인증을 요청하는 클라이언트 컴퓨터를 다른 ID 공급자로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-148">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span> |
|  |  |

<span data-ttu-id="d72b6-149">자세한 [내용은 올바른](/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-149">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>

## <a name="enforcing-strong-sign-ins"></a><span data-ttu-id="d72b6-150">강력한 로그인 강요</span><span class="sxs-lookup"><span data-stu-id="d72b6-150">Enforcing strong sign-ins</span></span>

<span data-ttu-id="d72b6-151">사용자 로그인의 보안을 강화하기 위해 다음 표의 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-151">To increase the security of user sign-ins, use the features and capabilities in the following table.</span></span>

| <span data-ttu-id="d72b6-152">기능</span><span class="sxs-lookup"><span data-stu-id="d72b6-152">Capability</span></span> | <span data-ttu-id="d72b6-153">설명</span><span class="sxs-lookup"><span data-stu-id="d72b6-153">Description</span></span> | <span data-ttu-id="d72b6-154">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d72b6-154">More information</span></span> | <span data-ttu-id="d72b6-155">라이선스 요구사항</span><span class="sxs-lookup"><span data-stu-id="d72b6-155">Licensing requirements</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d72b6-156">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="d72b6-156">Windows Hello for Business</span></span> | <span data-ttu-id="d72b6-157">다른 장치에서 로그인할 때 암호를 강력한 2단계 인증으로 Windows 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-157">Replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="d72b6-158">2단계 인증 요소는 장치에 연결된 새로운 유형의 사용자 자격 증명과 생체 인식 또는 PIN입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-158">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span> | [<span data-ttu-id="d72b6-159">비즈니스용 Windows Hello 개요</span><span class="sxs-lookup"><span data-stu-id="d72b6-159">Windows Hello for Business Overview</span></span>](/windows/security/identity-protection/hello-for-business/hello-overview) | <span data-ttu-id="d72b6-160">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="d72b6-160">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="d72b6-161">Azure AD 암호 보호</span><span class="sxs-lookup"><span data-stu-id="d72b6-161">Azure AD Password Protection</span></span> | <span data-ttu-id="d72b6-162">알려진 약한 암호와 해당 변형을 검색하고 차단하며 조직에 특정한 약한 용어를 추가로 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-162">Detects and blocks known weak passwords and their variants and can also block additional weak terms that are specific to your organization.</span></span> | [<span data-ttu-id="d72b6-163">Azure AD 암호 보호 구성</span><span class="sxs-lookup"><span data-stu-id="d72b6-163">Configure Azure AD password protection</span></span>](/azure/active-directory/authentication/concept-password-ban-bad) | <span data-ttu-id="d72b6-164">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="d72b6-164">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="d72b6-165">MFA(다단계 인증) 사용</span><span class="sxs-lookup"><span data-stu-id="d72b6-165">Use multi-factor authentication (MFA)</span></span> | <span data-ttu-id="d72b6-166">MFA를 사용하려면 사용자 로그인 시 사용자 계정 암호 이상의 추가 확인(예: 스마트폰 앱으로 확인 또는 스마트폰으로 전송된 문자 메시지)이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-166">MFA requires that user sign-ins be subject to an additional verification beyond the user account password, such as verification with a smartphone app or a text message sent to a smartphone.</span></span> <span data-ttu-id="d72b6-167">사용자가 [MFA를](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) 설정하는 방법에 대한 지침은 이 비디오를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d72b6-167">See [this video](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) for instructions on how users set up MFA.</span></span> | [<span data-ttu-id="d72b6-168">엔터프라이즈용 Microsoft 365 MFA</span><span class="sxs-lookup"><span data-stu-id="d72b6-168">MFA for Microsoft 365 for enterprise</span></span>](../enterprise/microsoft-365-secure-sign-in.md#mfa) | <span data-ttu-id="d72b6-169">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="d72b6-169">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="d72b6-170">ID 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="d72b6-170">Identity and device access configurations</span></span> | <span data-ttu-id="d72b6-171">설정 요청이 허용될지 여부 및 조건에 따라 부여할지 여부를 결정하는 조건부 액세스, Intune 및 Azure AD ID 보호 정책과 결합된 권장 선행 조건 기능 및 해당 설정으로 구성된 정책 및 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-171">Settings and policies that consist of recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span>  | [<span data-ttu-id="d72b6-172">ID 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="d72b6-172">Identity and device access configurations</span></span>](../security/defender-365-security/microsoft-365-policies-configurations.md) | <span data-ttu-id="d72b6-173">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="d72b6-173">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="d72b6-174">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="d72b6-174">Azure AD Identity Protection</span></span> | <span data-ttu-id="d72b6-175">공격자가 조직의 클라우드 서비스 및 데이터에 액세스하기 위해 사용자의 계정 이름과 암호를 확인하는 자격 증명 손상으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-175">Protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> | [<span data-ttu-id="d72b6-176">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="d72b6-176">Azure AD Identity Protection</span></span>](/azure/active-directory/active-directory-identityprotection) | <span data-ttu-id="d72b6-177">Microsoft 365 E5 Microsoft 365 E3 위협 방지 추가 & 있는 사용자 또는 사용자</span><span class="sxs-lookup"><span data-stu-id="d72b6-177">Microsoft 365 E5 or Microsoft 365 E3 with the Identity & Threat Protection add-on</span></span> |
|  |  |  |



## <a name="results-of-step-3"></a><span data-ttu-id="d72b6-178">3단계의 결과</span><span class="sxs-lookup"><span data-stu-id="d72b6-178">Results of Step 3</span></span>

<span data-ttu-id="d72b6-179">Microsoft 365 테넌트의 ID에 대해 다음을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-179">For identity for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="d72b6-180">사용할 ID 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-180">Which identity model to use.</span></span>
- <span data-ttu-id="d72b6-181">강력한 사용자 및 장치 액세스를 적용하는 방법</span><span class="sxs-lookup"><span data-stu-id="d72b6-181">How you will enforce strong user and device access.</span></span>

<span data-ttu-id="d72b6-182">다음은 새 하이브리드 ID 요소가 강조 표시된 테넌트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-182">Here is an example a tenant with the new hybrid identity elements highlighted.</span></span>

![테넌트에 대한 하이브리드 ID의 예](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

<span data-ttu-id="d72b6-184">이 그림에서 테넌트에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-184">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="d72b6-185">DirSync 서버 및 Azure AD 서버를 사용하여 Azure AD 테넌트와 동기화되는 AD DS 커넥트.</span><span class="sxs-lookup"><span data-stu-id="d72b6-185">An AD DS forest that is being synchronized with the Azure AD tenant using a DirSync server and Azure AD Connect.</span></span>
- <span data-ttu-id="d72b6-186">AD DS 포리스트의 AD DS 사용자 계정 및 기타 개체의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-186">A copy of the AD DS user accounts and other objects from the AD DS forest.</span></span>
- <span data-ttu-id="d72b6-187">사용자 계정을 기반으로 보안 사용자 로그인 및 액세스를 적용하는 조건부 액세스 정책 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-187">A set of Conditional Access policies to enforce secure user sign-ins and access based on the user account.</span></span> 

## <a name="ongoing-maintenance-for-identity"></a><span data-ttu-id="d72b6-188">ID에 대한 지속적인 유지 관리</span><span class="sxs-lookup"><span data-stu-id="d72b6-188">Ongoing maintenance for identity</span></span>

<span data-ttu-id="d72b6-189">지속적인 기준에 따라 다음을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-189">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="d72b6-190">사용자 계정 및 그룹을 추가하거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-190">Add or modify user accounts and groups.</span></span> <span data-ttu-id="d72b6-191">클라우드 전용 ID의 경우 클라우드 기반 사용자 및 그룹을 azure AD 도구(예: Microsoft 365 관리 센터 또는 PowerShell)로 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-191">For cloud-only identity, you maintain your cloud-based users and groups with Azure AD tools such as the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="d72b6-192">하이브리드 ID의 경우 AD DS 도구를 사용하여 사내 사용자 및 그룹을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-192">For hybrid identity, you maintain your on-premises users and groups with AD DS tools.</span></span>
- <span data-ttu-id="d72b6-193">로그인 보안 요구 사항을 적용하기 위해 ID 및 장치 액세스 구성을 추가하거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d72b6-193">Add or modify your identity and device access configuration to enforce sign-in security requirements.</span></span>

## <a name="next-step"></a><span data-ttu-id="d72b6-194">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d72b6-194">Next step</span></span>

<span data-ttu-id="d72b6-195">[![4단계. 서버 및 데이터로 Office 마이그레이션](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span><span class="sxs-lookup"><span data-stu-id="d72b6-195">[![Step 4. Migrate your on-premises Office servers and data](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span></span>

<span data-ttu-id="d72b6-196">마이그레이션을 [계속](tenant-management-migration.md) 진행하여 Office 서버와 데이터를 마이그레이션할 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d72b6-196">Continue with [migration](tenant-management-migration.md) to migrate your on-premises Office servers and their data to Microsoft 365.</span></span>