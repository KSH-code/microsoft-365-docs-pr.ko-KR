---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 추가 Azure Active Directory 정보
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
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동하는 경우의 추가 Azure Active Directory 정보입니다.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688800"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="f78fb-103">도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 추가 Azure Active Directory 정보</span><span class="sxs-lookup"><span data-stu-id="f78fb-103">Additional Azure Active Directory information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="f78fb-104">Azure German 클라우드에서 Azure 공용 클라우드로의 이동을 완료하기 위해 OIDC(OpenID Connect) 끝점에서 상업용 클라우드 끝점 보고를 시작할 때 응용 프로그램의 인증 끝점, Azure AD(Azure Active Directory) Graph 및 MS Graph 끝점을 상업용 클라우드의 끝점으로 업데이트하는 것이 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-104">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="f78fb-105">**이 변경은 언제 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="f78fb-105">**When should I make this change?**</span></span>

<span data-ttu-id="f78fb-106">테넌트가 독일 클라우드에서 상업용 클라우드로의 마이그레이션을 완료하면 Azure/Office 포털에서 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-106">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="f78fb-107">이 알림을 받은 후 30일이 지난 후 이러한 업데이트를 완료하면 앱이 Azure Germany 클라우드에서 Azure Public 클라우드로 마이그레이션된 테넌트에 대해 계속 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-107">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="f78fb-108">로그인 기관을 업데이트하는 데는 세 가지 사전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-108">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="f78fb-109">테넌트의 OIDC 검색 끝점은 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` Azure AD 공용 클라우드 끝점을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-109">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="f78fb-110">테넌트가 페더넌트에 대해 설정되어 있는 경우 Azure AD Public과 동기화하기 위해 AD FS(Active Directory Federation Services)가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-110">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="f78fb-111">지침에 따라 이 변경을 위해 Azure AD Connect 설정을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-111">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="f78fb-112">응용 프로그램에서 사용하는 리소스 응용 프로그램은 Azure AD Germany와 Azure AD Public에서 서명된 토큰을 수락하기 위해 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-112">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="f78fb-113">**응용 프로그램 종류**</span><span class="sxs-lookup"><span data-stu-id="f78fb-113">**What kind of applications?**</span></span>

<span data-ttu-id="f78fb-114">응용 프로그램은 다음 중 한 개일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-114">An application could be any of the following:</span></span>

- [<span data-ttu-id="f78fb-115">SPA(단일 페이지 앱)</span><span class="sxs-lookup"><span data-stu-id="f78fb-115">Single-page app (SPA)</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="f78fb-116">사용자에게 로그인하는 웹앱</span><span class="sxs-lookup"><span data-stu-id="f78fb-116">Web app that signs in users</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="f78fb-117">웹 API를 호출하는 웹 앱</span><span class="sxs-lookup"><span data-stu-id="f78fb-117">Web app that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="f78fb-118">보호된 웹 API</span><span class="sxs-lookup"><span data-stu-id="f78fb-118">Protected web API</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="f78fb-119">웹 API를 호출하는 웹 API</span><span class="sxs-lookup"><span data-stu-id="f78fb-119">Web API that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="f78fb-120">데스크톱 앱</span><span class="sxs-lookup"><span data-stu-id="f78fb-120">Desktop app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="f78fb-121">데몬 앱</span><span class="sxs-lookup"><span data-stu-id="f78fb-121">Daemon app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="f78fb-122">모바일 앱</span><span class="sxs-lookup"><span data-stu-id="f78fb-122">Mobile app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="f78fb-123">응용 프로그램이 권한으로 사용으로 전환하면 이 새 기관에서 토큰에 `login.microsoftonline.com` 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-123">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="f78fb-124">다른 앱이 호출하는 리소스 응용 프로그램을 호스팅하는 경우 록스 토큰 유효성 검사를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-124">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="f78fb-125">즉, 앱이 Azure AD Germany와 Azure AD 공용 클라우드에서 서명한 토큰을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-125">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="f78fb-126">서비스를 호출하는 모든 클라이언트 응용 프로그램이 Azure AD 공용 클라우드로 완전히 마이그레이션될 때까지 이 lax 토큰 유효성 검사가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-126">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="f78fb-127">마이그레이션 후 리소스 응용 프로그램은 Azure AD 공용 클라우드에서 서명된 토큰만 수락하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-127">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="f78fb-128">**업데이트해야 하는 이유는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="f78fb-128">**What do I need to update?**</span></span>

1. <span data-ttu-id="f78fb-129">Azure Germany 또는 Office 365 Germany 사용자를 인증하는 데 사용되는 응용 프로그램을 Azure Germany에서 호스팅하는 경우 인증 컨텍스트에서 기관으로 `https://login.microsoftonline.com` 사용되는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="f78fb-129">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="f78fb-130">Azure AD 인증 컨텍스트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f78fb-130">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="f78fb-131">이는 응용 프로그램에 대한 인증과 응용 프로그램이 호출할 수 있는 API(즉, Microsoft Graph, Azure AD Graph, Azure Resource Manager)에 대한 인증에 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-131">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="f78fb-132">Azure AD Graph 끝점을 `https://graph.windows.net` 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-132">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="f78fb-133">MS Graph 끝점을 `https://graph.microsoft.com` 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-133">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="f78fb-134">응용 프로그램에서 공용 클라우드의 끝점으로 사용하는 독일 클라우드 끝점(예: Exchange Online 및 SharePoint Online용 끝점)을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-134">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="f78fb-135">다음에 대한 관리 도구 및 스크립트에서 (대신) 환경 매개 `AzurePublic` `AzureGermany` 변수를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-135">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="f78fb-136">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f78fb-136">Azure PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [<span data-ttu-id="f78fb-137">Azure AD PowerShell(MSOnline)</span><span class="sxs-lookup"><span data-stu-id="f78fb-137">Azure AD PowerShell (MSOnline)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [<span data-ttu-id="f78fb-138">Azure AD PowerShell(AzureAD)</span><span class="sxs-lookup"><span data-stu-id="f78fb-138">Azure AD PowerShell (AzureAD)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [<span data-ttu-id="f78fb-139">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="f78fb-139">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
<span data-ttu-id="f78fb-140">**게시하는 응용 프로그램은 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="f78fb-140">**What about applications that I publish?**</span></span>

<span data-ttu-id="f78fb-141">테넌트 외부에 있는 사용자가 사용할 수 있는 응용 프로그램을 게시하는 경우 연속성을 보장하기 위해 응용 프로그램 등록을 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-141">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="f78fb-142">응용 프로그램을 사용하는 다른 테넌트는 테넌트와 다른 시간으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-142">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="f78fb-143">응용 프로그램에 대한 액세스 권한을 잃지 않도록 보장하려면 Azure Germany에서 Azure Public으로 동기화되는 앱에 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-143">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="f78fb-144">추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f78fb-144">Additional considerations</span></span>

<span data-ttu-id="f78fb-145">Azure AD에 대한 몇 가지 추가 고려 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-145">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="f78fb-146">페더타 인증의 경우:</span><span class="sxs-lookup"><span data-stu-id="f78fb-146">For federated authentication:</span></span>

  - <span data-ttu-id="f78fb-147">테넌트 전환이 진행되는 동안 페더넌트 도메인을 만들거나 승격하거나 강하하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-147">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="f78fb-148">Azure AD 서비스로의 마이그레이션이 완료된 후(테넌트가 완전히 완료된 경우) 페더링 도메인 관리를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-148">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="f78fb-149">AD FS(Active Directory Federation Services)에서 페더타 인증을 사용하는 경우 마이그레이션 중에는 모든 인증에 사용되는 발급자 URIS를 변경하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-149">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="f78fb-150">발급자 UR을 변경하면 도메인의 사용자에 대한 인증 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-150">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="f78fb-151">발급자 URIS는 AD FS에서 직접 변경하거나 도메인이 관리에서 페더러티로 변환되거나 그 반대로 변환될 때 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-151">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="f78fb-152">고객이 마이그레이션되는 Azure AD 테넌트에서 페더티된 도메인을 추가, 제거 또는 변환하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-152">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="f78fb-153">마이그레이션이 완전히 완료된 후 발급자 URIS를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-153">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="f78fb-154">네트워킹의 경우:</span><span class="sxs-lookup"><span data-stu-id="f78fb-154">For networking:</span></span>

  - <span data-ttu-id="f78fb-155">Azure Portal에서는 IPv6으로 명명된 네트워크를 만들 수 `http://portal.microsoftazure.de/` 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-155">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="f78fb-156">Azure Portal을 사용하여 IPv6으로 명명된 네트워크를 `https://portal.azure.com` 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-156">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="f78fb-157">도이치란드 Microsoft 클라우드 포털에서 Azure MFA(Multi-Factor Authentication) 서비스 설정에 대한 신뢰할 수 있는 IP 주소 범위를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-157">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="f78fb-158">Office 365 서비스에 대한 Azure AD 포털을 사용하여 Azure MFA 신뢰할 수 있는 IP 주소 범위를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-158">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="f78fb-159">조건부 액세스의 경우:</span><span class="sxs-lookup"><span data-stu-id="f78fb-159">For Conditional Access:</span></span> 

  - <span data-ttu-id="f78fb-160">다음 부여 컨트롤이 있는 조건부 액세스 정책은 Office 365 서비스로의 마이그레이션이 완료될 때까지(Azure AD 마이그레이션 단계 완료 후) [지원되지](ms-cloud-germany-transition.md#how-is-the-migration-organized) 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-160">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="f78fb-161">규격 장치 필요</span><span class="sxs-lookup"><span data-stu-id="f78fb-161">Require Compliant Device</span></span>
    - <span data-ttu-id="f78fb-162">승인된 앱 필요</span><span class="sxs-lookup"><span data-stu-id="f78fb-162">Require Approved App</span></span>
    - <span data-ttu-id="f78fb-163">앱 보호 정책 필요</span><span class="sxs-lookup"><span data-stu-id="f78fb-163">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="f78fb-164">조건부 액세스 정책 인터페이스는 사용하지 않도록 설정되어 있는 경우에도 테넌트에 대해 사용하도록 설정되는 보안 기본값에 대한 거짓 경고를 표시하며, 테넌트에 대한 조건부 액세스 정책이 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-164">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="f78fb-165">경고를 무시하거나 Office 365 서비스 포털을 사용하여 조건부 액세스 정책을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-165">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="f78fb-166">Intune 시나리오는 모든 Office 워크로드 마이그레이션을 포함하여 테넌트 마이그레이션이 완료된 후 전 세계 끝점에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-166">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="f78fb-167">MFA 요청에 모바일 앱 알림 방법을 사용하는 Microsoft 클라우드 도이클랜드 사용자는 Microsoft Authenticator 앱에서 UPN(사용자 계정 이름) 대신 사용자의 ObjectId(GUID)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-167">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="f78fb-168">Azure AD 테넌트의 마이그레이션이 완료 및 Office 365 서비스에서 호스트된 후 새로운 Microsoft Authenticator 정품 인증에는 사용자의 UPNS가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-168">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="f78fb-169">기존 Microsoft Authenticator 계정에는 사용자 ObjectId가 계속 표시되지만 모바일 앱 알림에 대해 계속 작동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-169">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="f78fb-170">2019년 10월 22일 이후에 만들어진 테넌트의 경우 Office 365 서비스로 마이그레이션할 때 테넌트에 대해 보안 기본값이 자동으로 활성화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-170">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="f78fb-171">테넌트 관리자는 보안 기본값을 사용하도록 설정하고 MFA에 등록할 수 있습니다. 또는 이 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-171">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="f78fb-172">자세한 내용은 보안 [기본값을 사용할 수 없습니다.](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="f78fb-172">For more information, see [Disabling security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="f78fb-173">보안 기본값을 사용하도록 설정하는 기능이 Office 365 서비스에 롤아웃되어 마이그레이션하는 동안 자동 사용되지 않는 조직은 향후에도 자동 등록될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-173">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="f78fb-174">보안 기본값을 명시적으로 사용하지 않도록 설정하거나 사용하도록 선택한 관리자는 Azure Active Directory 속성 속성에서 기능을 **업데이트하여 > 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f78fb-174">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="f78fb-175">관리자가 기능을 명시적으로 사용하도록 설정한 후 자동 사용이 가능하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-175">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="f78fb-176">테넌트가 마이그레이션 중이면 Office 365 Germany 포털 및 Office 365 포털에서 Azure AD Connect 버전에 대한 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-176">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="f78fb-177">마이그레이션이 완료된 후 버전 경고가 더 이상 경고를 표시하지 않는 경우 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-177">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="f78fb-178">마이그레이션 전이나 후에 경고가 있는 경우 두 포털에서 Azure AD Connect를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-178">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="f78fb-179">경고 메시지에는 "사용 중이지 않았다면 디렉터리 동기화 도구가 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="f78fb-179">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="f78fb-180">최신 버전의 Azure AD Connect를 다운로드하려면 Microsoft 다운로드 센터로 이동하는 것이 좋습니다."</span><span class="sxs-lookup"><span data-stu-id="f78fb-180">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="more-information"></a><span data-ttu-id="f78fb-181">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f78fb-181">More information</span></span>

<span data-ttu-id="f78fb-182">시작:</span><span class="sxs-lookup"><span data-stu-id="f78fb-182">Getting started:</span></span>

- [<span data-ttu-id="f78fb-183">독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f78fb-183">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="f78fb-184">Microsoft Cloud Deutschland 마이그레이션 지원</span><span class="sxs-lookup"><span data-stu-id="f78fb-184">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="f78fb-185">마이그레이션에 대해 옵트인하는 방법</span><span class="sxs-lookup"><span data-stu-id="f78fb-185">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="f78fb-186">마이그레이션 중의 고객 환경</span><span class="sxs-lookup"><span data-stu-id="f78fb-186">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="f78fb-187">전환을 통해 이동:</span><span class="sxs-lookup"><span data-stu-id="f78fb-187">Moving through the transition:</span></span>

- [<span data-ttu-id="f78fb-188">문장 작업 및 영향 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f78fb-188">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="f78fb-189">추가 사전 작업</span><span class="sxs-lookup"><span data-stu-id="f78fb-189">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="f78fb-190">[Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경 및](ms-cloud-germany-transition-add-experience.md) [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.</span><span class="sxs-lookup"><span data-stu-id="f78fb-190">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="f78fb-191">클라우드 앱:</span><span class="sxs-lookup"><span data-stu-id="f78fb-191">Cloud apps:</span></span>

- [<span data-ttu-id="f78fb-192">Dynamics 365 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="f78fb-192">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="f78fb-193">Power BI 마이그레이션 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="f78fb-193">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="f78fb-194">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="f78fb-194">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
