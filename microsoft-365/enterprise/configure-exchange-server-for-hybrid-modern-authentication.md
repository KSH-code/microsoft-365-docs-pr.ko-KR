---
title: 하이브리드 최신 인증을 사용하도록 Exchange Server 온-프레미스를 구성하는 방법
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 보다 안전한 사용자 인증 및 권한 부여를 Exchange Server HMA(하이브리드 최신 인증)를 사용하도록 하이브리드 하이브리드 인증을 구성하는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0a0e521f4ac81a8aa113b2e945045d31f2c1952
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599502"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="c62eb-103">하이브리드 최신 인증을 사용하도록 Exchange Server 온-프레미스를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="c62eb-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="c62eb-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="c62eb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c62eb-105">HMA(하이브리드 최신 인증)는 보다 안전한 사용자 인증 및 권한 부여를 제공하는 ID 관리 방법으로, Exchange 서버의 사내 하이브리드 배포에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="c62eb-106">FYI</span><span class="sxs-lookup"><span data-stu-id="c62eb-106">FYI</span></span>

<span data-ttu-id="c62eb-107">시작하기 전에 다음을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-107">Before we begin, I call:</span></span>

- <span data-ttu-id="c62eb-108">하이브리드 최신 인증 \> HMA</span><span class="sxs-lookup"><span data-stu-id="c62eb-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="c62eb-109">Exchange on-premises \> EXCH</span><span class="sxs-lookup"><span data-stu-id="c62eb-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="c62eb-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="c62eb-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="c62eb-111">또한 이 문서의 그래픽에 '회색으로 표시' 또는 '희미해진' 개체가 있는 경우 이는 회색으로 표시된 요소가 HMA 관련 구성에 포함되지 않음을 *나타냅니다.*</span><span class="sxs-lookup"><span data-stu-id="c62eb-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="c62eb-112">하이브리드 최신 인증 사용</span><span class="sxs-lookup"><span data-stu-id="c62eb-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="c62eb-113">HMA를 켜는 것은 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="c62eb-114">시작하기 전에 사전 요구 사항을 충족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="c62eb-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="c62eb-115">비즈니스용  Skype와 Exchange 모두에 공통적인 선행 조인이 많기 때문에 하이브리드 최신 인증 개요 및 이 선행 준비는 비즈니스용 Skype 및 [Exchange](hybrid-modern-auth-overview.md)서버 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="c62eb-116">이 문서의 단계를 시작하기 전에 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="c62eb-117">Azure AD에서 **SPNS(서비스 사용자 이름)로** 사내 웹 서비스 URL 추가</span><span class="sxs-lookup"><span data-stu-id="c62eb-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="c62eb-118">EXCH가 여러 테넌트와 하이브리드에 있는 경우 이러한 사내 웹 서비스 URL을 EXCH와 하이브리드에 있는 모든 테넌트의 Azure AD에 SPNS로 추가해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="c62eb-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="c62eb-119">모든 가상 Director가 HMA에 대해 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="c62eb-120">EvoSTSAuth Server 개체 확인</span><span class="sxs-lookup"><span data-stu-id="c62eb-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="c62eb-121">EXCH에서 HMA를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c62eb-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="c62eb-122">Office 버전이 MA를 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="c62eb-122">Does your version of Office support MA?</span></span> <span data-ttu-id="c62eb-123">[Office 2013 및 Office 2016](modern-auth-for-office-2013-and-2016.md)클라이언트 앱에 대해 최신 인증이 작동하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c62eb-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="c62eb-124">모든 선행 요구 사항을 충족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="c62eb-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="c62eb-125">비즈니스용 Skype와 Exchange 둘 다에 공통적인 선행 조인이 많기 때문에 하이브리드 최신 인증 개요 및 하이브리드 비즈니스용 Skype 및 [Exchange](hybrid-modern-auth-overview.md)서버에서 이를 사용하기 위한 선행 준비를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="c62eb-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="c62eb-126">이  *문서의*  단계를 시작하기 전에 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-126">Do this  *before*  you begin any of the steps in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="c62eb-127">Outlook Web App 및 Exchange 제어판은 하이브리드 최신 인증에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-127">Outlook Web App and Exchange Control Panel does not work with hybrid Modern Authentication.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="c62eb-128">Azure AD에서 SPNS로 사내 웹 서비스 URL 추가</span><span class="sxs-lookup"><span data-stu-id="c62eb-128">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="c62eb-129">Azure AD SPNS로 사내 웹 서비스 URL을 할당하는 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-129">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="c62eb-130">SPNS는 인증 및 권한 부여 중에 클라이언트 컴퓨터 및 장치에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-130">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="c62eb-131">사내에서 Azure AD(Azure Active Directory)에 연결하는 데 사용할 수 있는 모든 URL은 Azure AD에 등록해야 합니다(내부 및 외부 네임스페이스 모두 포함).</span><span class="sxs-lookup"><span data-stu-id="c62eb-131">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="c62eb-132">먼저 AAD에 추가해야 하는 모든 URL을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-132">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="c62eb-133">다음 명령을 사내에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-133">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="c62eb-134">연결할 수 있는 URL 클라이언트가 AAD에 HTTPS 서비스 사용자 이름으로 나열되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c62eb-134">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="c62eb-135">EXCH가 여러 테넌트와 하이브리드에 있는 경우 이러한 HTTPS SPNS는 EXCH와 하이브리드에 있는 모든 테넌트의 AAD에 추가되어야 합니다. </span><span class="sxs-lookup"><span data-stu-id="c62eb-135">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="c62eb-136">먼저 다음 지침을 사용하여 [AAD에 연결합니다.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="c62eb-136">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c62eb-137">아래 명령을 사용하려면 이 페이지의 _Connect-MsolService_ 옵션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-137">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="c62eb-138">Exchange 관련 URL의 경우 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-138">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="c62eb-139"> https:// autodiscover.yourdomain.com 및 https:// mail.yourdomain.com *URL을* 포함해야 하지만 주로 000000002-0000-0ff1-ce00-000000000000/로 시작하는 SPNS로 구성되는 이 명령의 출력(및 나중에 비교를 위한 스크린샷)을 기록해 봐야 합니다. </span><span class="sxs-lookup"><span data-stu-id="c62eb-139">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="c62eb-140">누락된 https:// URL이 없는 경우 해당 특정 레코드를 이 목록에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-140">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="c62eb-141">이 목록에 내부 및 외부 MAPI/HTTP, EWS, ActiveSync, OAB 및 Autodiscover 레코드가 없는 경우 아래 명령을 사용하여 레코드를 추가해야 합니다(예제 URL은 ' 및 '이지만 예제 `mail.corp.contoso.com` `owa.contoso.com` **URL은** 자체 URL로 대체).</span><span class="sxs-lookup"><span data-stu-id="c62eb-141">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="c62eb-142">2단계에서 Get-MsolServicePrincipal 명령을 다시 실행하고 출력을 확인하여 새 레코드가 추가된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-142">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="c62eb-143">이전의 목록/스크린샷을 새 SPNS 목록과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-143">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="c62eb-144">레코드에 대한 새 목록의 스크린샷을 찍을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-144">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="c62eb-145">성공하면 목록에 두 개의 새 URL이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-145">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="c62eb-146">이 예제에서는 이제 SPNS 목록에 특정 URL 및 을  `https://mail.corp.contoso.com`  `https://owa.contoso.com` 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-146">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="c62eb-147">가상디렉터가 올바르게 구성되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="c62eb-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="c62eb-148">이제 Exchange에서 다음 명령을 실행하여 Outlook에서 사용할 수 있는 모든 가상디렉터에서 OAuth가 제대로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="c62eb-149">출력을 확인하여 이러한 각 VDirs에서 **OAuth가** 사용하도록 설정되어 있는지 확인합니다. 이 경우 다음과 같은 모양이 됩니다( 그리고 중요한 것은 'OAuth'입니다.).</span><span class="sxs-lookup"><span data-stu-id="c62eb-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="c62eb-150">OAuth가 서버 및 네 개의 가상디렉터에서 누락된 경우 계속하기 전에 관련 명령을 사용하여 추가해야 합니다([Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)및 [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="c62eb-150">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="c62eb-151">EvoSTS Auth 서버 개체가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c62eb-151">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="c62eb-152">이 마지막 명령에 대한 On-premises Exchange Management Shell으로 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-152">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="c62eb-153">이제 evoSTS 인증 공급자에 대한 항목이 On-프레미스에 유효한지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-153">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="c62eb-154">출력에 이름 EvoSts의 AuthServer가 표시되어 '사용' 상태가 True가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-154">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="c62eb-155">이 설정이 없는 경우 최신 버전의 하이브리드 구성 마법사를 다운로드하여 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-155">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="c62eb-156">EXCH가 여러 테넌트와 함께 하이브리드에 있는 경우 출력에 EXCH와 하이브리드의 각 테넌트에 대한 Name EvoSts - {GUID}의 AuthServer가 하나 표시되어야 합니다. 이러한 모든 AuthServer 개체에 대해 'Enabled' 상태가 True가 됩니다. </span><span class="sxs-lookup"><span data-stu-id="c62eb-156">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="c62eb-157">**중요** 환경에서 Exchange 2010을 실행하는 경우 EvoSTS 인증 공급자가 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-157">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="c62eb-158">HMA 사용</span><span class="sxs-lookup"><span data-stu-id="c62eb-158">Enable HMA</span></span>

<span data-ttu-id="c62eb-159">Exchange 관리 셸( On-premises)에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-159">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="c62eb-160">EXCH 버전이 Exchange 2016(CU18 이상) 또는 Exchange 2019(CU7 이상)이고 하이브리드가 2020년 9월 이후에 다운로드된 HCW를 사용하여 구성된 경우 Exchange 관리 셸의 On-premises에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-160">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="c62eb-161">EXCH가 여러 테넌트와 하이브리드에 있는 경우 각 테넌트에 해당하는 도메인을 사용하여 EXCH에 여러 AuthServer 개체가 있습니다. </span><span class="sxs-lookup"><span data-stu-id="c62eb-161">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="c62eb-162">이러한 AuthServer 개체 중 하나에 대해 **IsDefaultAuthorizationEndpoint** 플래그를 **true(IsDefaultAuthorizationEndpoint** cmdlet 사용)로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-162">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="c62eb-163">모든 Authserver 개체에 대해 이 플래그를 true로 설정할 수 없습니다. 이러한 AuthServer 개체의 **IsDefaultAuthorizationEndpoint** 플래그 중 하나를 true로 설정한 경우에도 HMA가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-163">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="c62eb-164">확인</span><span class="sxs-lookup"><span data-stu-id="c62eb-164">Verify</span></span>

<span data-ttu-id="c62eb-165">HMA를 사용하도록 설정하면 클라이언트의 다음 로그인에서 새 인증 흐름을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-165">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="c62eb-166">HMA를 켜면 클라이언트에 대한 재인식이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-166">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="c62eb-167">클라이언트는 인증 토큰 및/또는 보유한 인증의 수명을 기반으로 다시 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-167">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="c62eb-168">또한 Outlook 클라이언트(Windows 알림 트레이에서도)의 아이콘을 마우스 오른쪽 단추로 클릭하고 '연결 상태'를 클릭하는 동시에 Ctrl 키를 눌러야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-168">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="c62eb-169">OAuth에 사용되는 bearer 토큰을 나타내는 'Bearer'의 'Authn' 유형에 대해 클라이언트의 SMTP 주소를 \* 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-169">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="c62eb-170">HMA를 통해 비즈니스용 Skype를 구성해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="c62eb-170">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="c62eb-171">지원되는 토폴로지 목록과 [](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)구성 방법을 보여 주는 문서 2개가 [필요합니다.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="c62eb-171">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="c62eb-172">Android 및 iOS용 Outlook에서 하이브리드 최신 인증 사용</span><span class="sxs-lookup"><span data-stu-id="c62eb-172">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="c62eb-173">TCP 443에서 Exchange 서버를 사용하는 사내 고객인 경우 다음 IP 주소 범위에 대한 트래픽 처리를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-173">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

<span data-ttu-id="c62eb-174">iOS 및 Android용 Outlook 앱은 Microsoft 서비스를 사용하여 일상 생활과 작업을 찾고, 계획하고, 우선 순위를 정하는 데 도움을 주어 모바일 장치에서 Microsoft 365 또는 Office 365를 경험하는 가장 좋은 방법으로 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="c62eb-174">The Outlook app for iOS and Android is designed as the best way to experience Microsoft 365 or Office 365 on your mobile device by using Microsoft services to help find, plan, and prioritize your daily life and work.</span></span> <span data-ttu-id="c62eb-175">자세한 내용은 iOS 및 [Android용 Outlook에서](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019)하이브리드 최신 인증 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c62eb-175">For more information, please refer to [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c62eb-176">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c62eb-176">Related topics</span></span>

[<span data-ttu-id="c62eb-177">Office 365 전용/ITAR에서 vNext로의 전환을 위한 최신 인증 구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c62eb-177">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
