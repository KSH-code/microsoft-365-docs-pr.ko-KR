---
title: 도이치클라드에서 마이그레이션하기 위한 추가 Azure Active Directory 정보
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 독일 Microsoft Azure Active Directory(Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동하는 경우의 추가 정보입니다.'
ms.openlocfilehash: 0e7abd68945a9b685a33c120ff1e92fda62b2c56
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362729"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="76eec-103">도이치클라드에서 마이그레이션하기 위한 추가 Azure Active Directory 정보</span><span class="sxs-lookup"><span data-stu-id="76eec-103">Additional Azure Active Directory information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="76eec-104">Azure German 클라우드에서 Azure 공용 클라우드로의 이동을 완료하기 위해 OIDC(OpenID 커넥트) 끝점에서 상업용 클라우드 끝점 보고를 시작할 때 응용 프로그램의 인증 끝점, Azure Active Directory(Azure AD) Graph 및 MS Graph 끝점을 상업용 클라우드의 끝점으로 업데이트하는 것이 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-104">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="76eec-105">**언제 변경해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="76eec-105">**When should I make this change?**</span></span>

<span data-ttu-id="76eec-106">테넌트가 독일 클라우드에서 상업용 클라우드로의 마이그레이션을 완료하면 Azure/Office 포털에서 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-106">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="76eec-107">이 알림을 받은 후 30일이 지난 후 이러한 업데이트를 완료하면 앱이 Azure Germany 클라우드에서 Azure Public 클라우드로 마이그레이션된 테넌트에 대해 계속 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-107">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="76eec-108">로그인 기관을 업데이트하는 데는 세 가지 사전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-108">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="76eec-109">테넌트의 OIDC 검색 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 끝점은 Azure AD 공용 클라우드 끝점을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-109">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="76eec-110">테넌트가 페더넌트에 대해 설정된 경우 AD FS(Active Directory Federation Services)가 Azure AD Public과 동기화될 수 있도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-110">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="76eec-111">이 변경에 대한 Azure AD 커넥트 지침에 따라 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-111">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="76eec-112">응용 프로그램에서 사용하는 리소스 응용 프로그램은 Azure AD Germany와 Azure AD Public 둘 다에서 서명된 토큰을 수락하기 위해 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-112">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="76eec-113">**응용 프로그램 종류**</span><span class="sxs-lookup"><span data-stu-id="76eec-113">**What kind of applications?**</span></span>

<span data-ttu-id="76eec-114">응용 프로그램은 다음 중 한 개일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-114">An application could be any of the following:</span></span>

- [<span data-ttu-id="76eec-115">SPA(단일 페이지 앱)</span><span class="sxs-lookup"><span data-stu-id="76eec-115">Single-page app (SPA)</span></span>](/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="76eec-116">사용자에게 로그인하는 웹앱</span><span class="sxs-lookup"><span data-stu-id="76eec-116">Web app that signs in users</span></span>](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="76eec-117">웹 API를 호출하는 웹 앱</span><span class="sxs-lookup"><span data-stu-id="76eec-117">Web app that calls web APIs</span></span>](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="76eec-118">보호된 웹 API</span><span class="sxs-lookup"><span data-stu-id="76eec-118">Protected web API</span></span>](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="76eec-119">웹 API를 호출하는 웹 API</span><span class="sxs-lookup"><span data-stu-id="76eec-119">Web API that calls web APIs</span></span>](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="76eec-120">데스크톱 앱</span><span class="sxs-lookup"><span data-stu-id="76eec-120">Desktop app</span></span>](/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="76eec-121">데몬 앱</span><span class="sxs-lookup"><span data-stu-id="76eec-121">Daemon app</span></span>](/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="76eec-122">모바일 앱</span><span class="sxs-lookup"><span data-stu-id="76eec-122">Mobile app</span></span>](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="76eec-123">응용 프로그램이 권한으로 사용으로 전환하면 이 새 기관에서 토큰에 `login.microsoftonline.com` 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-123">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="76eec-124">다른 앱이 호출하는 리소스 응용 프로그램을 호스팅하는 경우 래시 토큰 유효성 검사를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-124">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="76eec-125">즉, 앱이 Azure AD Germany 및 Azure AD 공용 클라우드에서 서명된 토큰을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-125">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="76eec-126">서비스를 호출하는 모든 클라이언트 응용 프로그램이 Azure AD 공용 클라우드로 완전히 마이그레이션될 때까지 이 lax 토큰 유효성 검사가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-126">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="76eec-127">마이그레이션 후 리소스 응용 프로그램은 Azure AD 공용 클라우드에서 서명된 토큰만 수락하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-127">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="76eec-128">**업데이트해야 하는 것**</span><span class="sxs-lookup"><span data-stu-id="76eec-128">**What do I need to update?**</span></span>

1. <span data-ttu-id="76eec-129">Azure Germany 또는 Office 365 Germany 사용자를 인증하는 데 사용되는 응용 프로그램을 Azure Germany에서 호스팅하는 경우 인증 컨텍스트에서 기관으로 `https://login.microsoftonline.com` 사용되는지 확인</span><span class="sxs-lookup"><span data-stu-id="76eec-129">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="76eec-130">Azure AD 인증 컨텍스트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76eec-130">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="76eec-131">이는 응용 프로그램에 대한 인증뿐만 아니라 응용 프로그램이 호출할 수 있는 API에 대한 인증(즉, Microsoft Graph, Azure AD Graph, Azure Resource Manager)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-131">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="76eec-132">Azure AD Graph 끝점을 로 `https://graph.windows.net` 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-132">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="76eec-133">MS Graph 끝점을 로 `https://graph.microsoft.com` 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-133">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="76eec-134">응용 프로그램이 공용 클라우드로 사용하는 독일 클라우드 끝점(예: Exchange Online SharePoint Online용 끝점)을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-134">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="76eec-135">다음에 대한 관리 도구 및 스크립트에서 (대신) 환경 매개 `AzurePublic` `AzureGermany` 변수를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-135">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="76eec-136">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="76eec-136">Azure PowerShell</span></span>](/powershell/azure/install-az-ps)
    - [<span data-ttu-id="76eec-137">Azure AD PowerShell(MSOnline)</span><span class="sxs-lookup"><span data-stu-id="76eec-137">Azure AD PowerShell (MSOnline)</span></span>](/powershell/azure/active-directory/overview)
    - [<span data-ttu-id="76eec-138">Azure AD PowerShell(AzureAD)</span><span class="sxs-lookup"><span data-stu-id="76eec-138">Azure AD PowerShell (AzureAD)</span></span>](/powershell/azure/active-directory/install-adv2)
    - [<span data-ttu-id="76eec-139">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="76eec-139">Azure CLI</span></span>](/cli/azure/install-azure-cli)
 
<span data-ttu-id="76eec-140">**게시하는 응용 프로그램은 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="76eec-140">**What about applications that I publish?**</span></span>

<span data-ttu-id="76eec-141">테넌트 외부에 있는 사용자가 사용할 수 있는 응용 프로그램을 게시하는 경우 연속성을 보장하기 위해 응용 프로그램 등록을 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-141">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="76eec-142">응용 프로그램을 사용하는 다른 테넌트는 테넌트와 다른 시간으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-142">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="76eec-143">응용 프로그램에 대한 액세스 권한을 잃지 않도록 보장하려면 Azure Germany에서 Azure Public으로 동기화되는 앱에 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-143">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

<span data-ttu-id="76eec-144">**마이그레이션 중 새 다중 테넌트 응용 프로그램을 추가하는 경우**</span><span class="sxs-lookup"><span data-stu-id="76eec-144">**What about adding new multi-tenant applications during migration?**</span></span>

<span data-ttu-id="76eec-145">다른 조직(다중 테넌트 응용 프로그램)에서 게시하는 새 응용 프로그램을 사용하려는 경우 마이그레이션 프로세스(2~9단계)에서 해당 응용 프로그램을 추가하지는 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-145">If you want to consume a new application that is published by another organization (multi-tenant application) you will be restricted from adding that application during the migration process (phases 2 through phase 9).</span></span>  <span data-ttu-id="76eec-146">조직이 9단계를 완료하고 Azure 공용 인스턴스로 완전히 전환될 때 이 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-146">You may execute this task when your organization completes phase 9 and is fully transitioned to the Azure public instance.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="76eec-147">추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="76eec-147">Additional considerations</span></span>

<span data-ttu-id="76eec-148">다음은 Azure AD에 대한 몇 가지 추가 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-148">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="76eec-149">페더타 인증의 경우:</span><span class="sxs-lookup"><span data-stu-id="76eec-149">For federated authentication:</span></span>

  - <span data-ttu-id="76eec-150">테넌트 전환이 진행되는 동안에는 페더넌트 도메인을 만들거나 승격하거나 강락하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-150">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="76eec-151">Azure AD 서비스로의 마이그레이션이 완료된 후(테넌트가 완전히 완료된 경우) 페더링된 도메인 관리를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-151">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="76eec-152">AD FS(Active Directory Federation Services)에서 페더전된 인증을 사용하는 경우 마이그레이션 중에는 모든 인증에 사용되는 발급자 URIS를 변경하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-152">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="76eec-153">발급자 URIS를 변경하면 도메인의 사용자에 대한 인증 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-153">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="76eec-154">발급자 URIS는 AD FS에서 직접 변경할 수 있으며 도메인이 관리에서 페더러티로 변환되거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-154">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="76eec-155">고객이 마이그레이션되는 Azure AD 테넌트에서 페더넌트 도메인을 추가, 제거 또는 변환하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-155">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="76eec-156">발급자 URIS는 마이그레이션이 완전히 완료된 후 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-156">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="76eec-157">네트워킹의 경우:</span><span class="sxs-lookup"><span data-stu-id="76eec-157">For networking:</span></span>

  - <span data-ttu-id="76eec-158">Azure Portal에서 IPv6으로 명명된 네트워크를 만들 수 `http://portal.microsoftazure.de/` 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-158">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="76eec-159">에서 Azure Portal을 `https://portal.azure.com` 사용하여 IPv6으로 명명된 네트워크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-159">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="76eec-160">도이치랜드 Microsoft 클라우드 포털에서 Azure MFA(다단계 인증) 서비스 설정에 대한 신뢰할 수 있는 IP 주소 범위를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-160">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="76eec-161">서비스용 Azure AD 포털을 Office 365 Azure MFA 신뢰할 수 있는 IP 주소 범위를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-161">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="76eec-162">조건부 액세스의 경우:</span><span class="sxs-lookup"><span data-stu-id="76eec-162">For Conditional Access:</span></span> 

  - <span data-ttu-id="76eec-163">다음 부여 컨트롤이 있는 조건부 액세스 정책은 Office 365 서비스로의 마이그레이션이 완료될 때까지(Azure AD 마이그레이션 완료 단계 후) [지원되지](ms-cloud-germany-transition.md#how-is-the-migration-organized) 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-163">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="76eec-164">규격 장치 필요</span><span class="sxs-lookup"><span data-stu-id="76eec-164">Require Compliant Device</span></span>
    - <span data-ttu-id="76eec-165">승인된 앱 필요</span><span class="sxs-lookup"><span data-stu-id="76eec-165">Require Approved App</span></span>
    - <span data-ttu-id="76eec-166">앱 보호 정책 필요</span><span class="sxs-lookup"><span data-stu-id="76eec-166">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="76eec-167">조건부 액세스 정책 인터페이스는 사용하지 않도록 설정된 경우에도 테넌트에 대해 사용하도록 설정되는 보안 기본값에 대한 거짓 경고를 표시하며, 테넌트에 대해 조건부 액세스 정책이 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-167">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="76eec-168">경고를 무시하거나 Office 365 서비스 포털을 사용하여 조건부 액세스 정책을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-168">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="76eec-169">Intune 시나리오는 모든 Office 작업 마이그레이션을 포함하여 테넌트 마이그레이션이 완료된 후 전 세계 끝점에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-169">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="76eec-170">MFA 요청에 모바일 앱 알림 메서드를 사용하는 Microsoft 클라우드 도이클란드 사용자는 Microsoft Authenticator 앱의 UPN(사용자 계정 이름) 대신 사용자의 ObjectId(GUID)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-170">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="76eec-171">Azure AD 테넌트의 마이그레이션이 완료되어 Office 365 서비스에서 호스팅된 후 새로운 Microsoft Authenticator 정품 인증에 사용자의 UPNS가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-171">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="76eec-172">기존 Microsoft Authenticator 계정은 사용자 ObjectId를 계속 표시하지만 모바일 앱 알림에도 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-172">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="76eec-173">2019년 10월 22일 이후에 만들어진 테넌트의 경우 테넌트가 Office 365 서비스로 마이그레이션될 때 테넌트에 대해 보안 기본값이 자동으로 활성화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-173">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="76eec-174">테넌트 관리자는 보안 기본값을 사용하도록 설정하고 MFA에 등록할 수 있습니다. 또는 이 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-174">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="76eec-175">자세한 내용은 [Disabling security defaults을 참조하십시오.](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="76eec-175">For more information, see [Disabling security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="76eec-176">마이그레이션 중에 자동 사용되지 않는 조직은 보안 기본값을 사용하도록 설정하는 기능이 Office 365 서비스에서 롤아웃될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-176">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="76eec-177">보안 기본값을 명시적으로 사용하지 않도록 설정하거나 사용하도록 선택한 관리자는 속성 에서 기능을 업데이트하여 Azure Active Directory > **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="76eec-177">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="76eec-178">관리자가 이 기능을 명시적으로 사용하도록 설정한 후 자동 사용이 가능하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-178">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="76eec-179">테넌트가 마이그레이션 중이면 Office 365 독일 포털과 Office 365 포털에서 Azure AD ad 커넥트 버전에 대한 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-179">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="76eec-180">마이그레이션이 완료된 후 버전 경고가 더 이상 경고를 표시하지 않는 경우 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-180">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="76eec-181">마이그레이션 전이나 후에 경고가 표시될 경우 두 포털에서 Azure AD 커넥트 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-181">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="76eec-182">경고 메시지는 다음을 나타냅니다. "디렉터리 동기화 도구가 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="76eec-182">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="76eec-183">Microsoft 다운로드 센터로 이동하여 최신 버전의 Azure AD 2013을 다운로드하는 커넥트."</span><span class="sxs-lookup"><span data-stu-id="76eec-183">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="more-information"></a><span data-ttu-id="76eec-184">추가 정보</span><span class="sxs-lookup"><span data-stu-id="76eec-184">More information</span></span>

<span data-ttu-id="76eec-185">시작:</span><span class="sxs-lookup"><span data-stu-id="76eec-185">Getting started:</span></span>

- [<span data-ttu-id="76eec-186">독일 Microsoft 클라우드에서 새 독일 Office 365 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="76eec-186">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="76eec-187">Microsoft Cloud Deutschland 마이그레이션 지원</span><span class="sxs-lookup"><span data-stu-id="76eec-187">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="76eec-188">마이그레이션에 대해 옵트인하는 방법</span><span class="sxs-lookup"><span data-stu-id="76eec-188">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="76eec-189">마이그레이션 중의 고객 환경</span><span class="sxs-lookup"><span data-stu-id="76eec-189">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="76eec-190">전환을 통해 이동:</span><span class="sxs-lookup"><span data-stu-id="76eec-190">Moving through the transition:</span></span>

- [<span data-ttu-id="76eec-191">문장 작업 및 영향 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="76eec-191">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="76eec-192">추가 사전 작업</span><span class="sxs-lookup"><span data-stu-id="76eec-192">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="76eec-193">[Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.</span><span class="sxs-lookup"><span data-stu-id="76eec-193">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="76eec-194">클라우드 앱:</span><span class="sxs-lookup"><span data-stu-id="76eec-194">Cloud apps:</span></span>

- [<span data-ttu-id="76eec-195">Dynamics 365 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="76eec-195">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="76eec-196">Power BI 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="76eec-196">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="76eec-197">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="76eec-197">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
