---
title: 하이브리드 최신 인증을 사용하도록 비즈니스용 Skype 온-프레미스를 구성하는 방법
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 보다 안전한 사용자 인증 및 비즈니스용 Skype HMA(하이브리드 최신 인증)를 사용하도록 사내에서 하이브리드 인증을 구성하는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3177bafb6eff27053dca61ec576666cae4a97bb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911153"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="839d5-103">하이브리드 최신 인증을 사용하도록 비즈니스용 Skype 온-프레미스를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="839d5-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="839d5-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="839d5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="839d5-105">최신 인증은 보다 안전한 사용자 인증 및 권한 부여를 제공하는 ID 관리 방법으로, 비즈니스용 Skype 서버의 Exchange 서버와 도메인 분할 하이브리드에 사용할 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>
  
 <span data-ttu-id="839d5-106">**중요** MA(최신 인증)와 회사 또는 조직에서 이 인증을 사용하는 것을 선호하는 이유에 대해 알아 두시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="839d5-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="839d5-107">이 [문서에서](hybrid-modern-auth-overview.md) 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="839d5-108">MA에서 지원되는 비즈니스용 Skype 토폴로지가 필요한 경우 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>
  
 <span data-ttu-id="839d5-109">**시작하기 전에** 다음 용어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-109">**Before we begin**, I use these terms:</span></span>
  
- <span data-ttu-id="839d5-110">MA(최신 인증)</span><span class="sxs-lookup"><span data-stu-id="839d5-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="839d5-111">하이브리드 최신 인증(HMA)</span><span class="sxs-lookup"><span data-stu-id="839d5-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="839d5-112">Exchange(EXCH)</span><span class="sxs-lookup"><span data-stu-id="839d5-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="839d5-113">Exchange Online(EXO)</span><span class="sxs-lookup"><span data-stu-id="839d5-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="839d5-114">비즈니스용 Skype(SFB)</span><span class="sxs-lookup"><span data-stu-id="839d5-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="839d5-115">비즈니스용 Skype 온라인(SFBO)</span><span class="sxs-lookup"><span data-stu-id="839d5-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="839d5-116">또한 이 문서의 그래픽에 회색으로 표시되거나 희미해진 개체가 있는 경우  이는 회색으로 표시된 요소가 MA 관련 구성에 포함되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>
  
## <a name="read-the-summary"></a><span data-ttu-id="839d5-117">요약 읽기</span><span class="sxs-lookup"><span data-stu-id="839d5-117">Read the summary</span></span>

<span data-ttu-id="839d5-118">이 요약은 프로세스를 실행 중에 손실될 수 있는 단계로 세분화하고 전체 검사 목록에서 프로세스의 위치를 추적하는 데 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>
  
1. <span data-ttu-id="839d5-119">먼저 모든 선행 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="839d5-120">많은 **사전** 요구 사항들이 비즈니스용 Skype 및 Exchange 일반적이기 때문에 사전 요구 사항 검사 목록의 개요 문서를 [참조하세요.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="839d5-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="839d5-121">이  *문서의*  단계를 시작하기 전에 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="839d5-122">파일 또는 파일에서 필요한 HMA 관련 정보를 OneNote.</span><span class="sxs-lookup"><span data-stu-id="839d5-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="839d5-123">EXO에 대한 최신 인증을 켜기(아직 켜져 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="839d5-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="839d5-124">SFBO에 대한 최신 인증을 켜기(아직 켜져 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="839d5-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="839d5-125">하이브리드 최신 인증을 설정하여 Exchange.</span><span class="sxs-lookup"><span data-stu-id="839d5-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="839d5-126">하이브리드 최신 인증을 설정하여 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="839d5-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="839d5-127">이러한 단계에서는 SFB, SFBO, EXCH 및 EXO에 대해 MA를 켜야 합니다. 즉, SFB 및 SFBO의 HMA 구성에 참여할 수 있는 모든 제품(EXCH/EXO에 대한 종속성 포함)</span><span class="sxs-lookup"><span data-stu-id="839d5-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="839d5-128">즉, 사용자가 하이브리드의 일부(EXO + SFBO, EXO + SFB, EXCH + SFBO 또는 EXCH + SFB)에 사서함을 만들거나 있는 경우 완성된 제품은 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>
  
![비즈니스 HMA 토폴로지의 Skype 혼합 6개 토폴로지에는 가능한 네 개의 모든 위치에 MA가 있습니다.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
<span data-ttu-id="839d5-130">MA를 켜는 네 개의 다른 위치가 있습니다!</span><span class="sxs-lookup"><span data-stu-id="839d5-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="839d5-131">최상의 사용자 환경을 위해 이러한 네 위치에서 모두 MA를 켜는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="839d5-132">이러한 모든 위치에서 MA를 끄지 못하면 환경에 필요한 위치에서만 MA를 켜게 단계를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>
  
<span data-ttu-id="839d5-133">지원되는 [토폴로지의](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) 경우 MA를 비즈니스용 Skype 지원 가능성 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839d5-133">See the [Supportability topic for Skype for Business with MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) for supported topologies.</span></span>
  
 <span data-ttu-id="839d5-134">**중요** 시작하기 전에 모든 선행 조문을 충족하는지 다시 한 번 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="839d5-135">이 정보는 하이브리드 최신 인증 개요 및 선행 준비 사항 [에서 찾을 수 있습니다.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="839d5-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>
  
## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="839d5-136">필요한 모든 HMA 관련 정보 수집</span><span class="sxs-lookup"><span data-stu-id="839d5-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="839d5-137">최신 인증을 사용하기 위한 선행 [](hybrid-modern-auth-overview.md) 요구 사항을 충족하는지 다시 확인한 후(위의 참고 참조) 앞서 설명된 단계에서 HMA를 구성하는 데 필요한 정보를 저장하는 파일을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="839d5-138">이 문서에 사용된 예제:</span><span class="sxs-lookup"><span data-stu-id="839d5-138">Examples used in this article:</span></span>
  
- <span data-ttu-id="839d5-139">**SIP/SMTP 도메인**</span><span class="sxs-lookup"><span data-stu-id="839d5-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="839d5-140">예.</span><span class="sxs-lookup"><span data-stu-id="839d5-140">Ex.</span></span> <span data-ttu-id="839d5-141">contoso.com(Office 365)</span><span class="sxs-lookup"><span data-stu-id="839d5-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="839d5-142">**테넌트 ID**</span><span class="sxs-lookup"><span data-stu-id="839d5-142">**Tenant ID**</span></span>

  - <span data-ttu-id="839d5-143">사용자 테넌트(Office 365 로그인 시)를 나타내는 GUID contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="839d5-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="839d5-144">**SFB 2015 CU5 웹 서비스 URL**</span><span class="sxs-lookup"><span data-stu-id="839d5-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="839d5-145">배포된 모든 SfB 2015 풀에 대해 내부 및 외부 웹 서비스 URL이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="839d5-146">이러한 정보를 얻었다면 관리 셸에서 비즈니스용 Skype 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="839d5-147">예.</span><span class="sxs-lookup"><span data-stu-id="839d5-147">Ex.</span></span> <span data-ttu-id="839d5-148">내부: https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="839d5-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="839d5-149">예.</span><span class="sxs-lookup"><span data-stu-id="839d5-149">Ex.</span></span> <span data-ttu-id="839d5-150">외부: https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="839d5-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="839d5-151">Standard Edition 서버를 사용하는 경우 내부 URL은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="839d5-152">이 경우 내부 URL에 풀 fqdn을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-152">In this case, use the pool fqdn for the internal URL.</span></span>
  
## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="839d5-153">EXO에 대한 최신 인증 켜기</span><span class="sxs-lookup"><span data-stu-id="839d5-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="839d5-154">지침에 따라 다음을 Exchange Online: 최신 인증을 위해 [테넌트가 사용하도록 설정하는 방법.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="839d5-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>
  
## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="839d5-155">SFBO에 대한 최신 인증 켜기</span><span class="sxs-lookup"><span data-stu-id="839d5-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="839d5-156">온라인 비즈니스용 Skype 지침에 따라 최신 인증을 위해 [테넌트 사용](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span><span class="sxs-lookup"><span data-stu-id="839d5-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="839d5-157">하이브리드 최신 인증을 설정하여 Exchange 설정</span><span class="sxs-lookup"><span data-stu-id="839d5-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="839d5-158">하이브리드 최신 인증을 사용하도록 Exchange Server 구성하는 방법의 [지침을 따릅니다.](configure-exchange-server-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="839d5-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="839d5-159">하이브리드 최신 인증을 설정하여 비즈니스용 Skype 설정</span><span class="sxs-lookup"><span data-stu-id="839d5-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="839d5-160">프레미스 웹 서비스 URL을 2016년 12월에 SPNS로 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="839d5-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="839d5-161">이제 명령을 실행하여 SFBO에서 URL(이전 수집)을 서비스 사용자로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>
  
 <span data-ttu-id="839d5-162">**참고** SPNS(서비스 사용자 이름)는 웹 서비스를 식별하고 보안 주체(예: 계정 이름 또는 그룹)와 연결하여 서비스가 인증된 사용자를 대신하여 작업할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="839d5-163">서버에 인증하는 클라이언트는 SPNS에 포함된 정보를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>
  
1. <span data-ttu-id="839d5-164">먼저 다음 Azure Active Directory (Azure AD)에 [연결합니다.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="839d5-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

2. <span data-ttu-id="839d5-165">SFB 웹 서비스 URL 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="839d5-166">AppPrincipalId는 로 `00000004` 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="839d5-167">이 특성은 비즈니스용 Skype 온라인에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="839d5-168">이 명령의 출력(및 나중에 비교를 위해 스크린샷)을 확인합니다. 이 명령의 출력에는 SE 및 WS URL이 포함되지만 대부분 으로 시작하는 SPNS로 `00000004-0000-0ff1-ce00-000000000000/` 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="839d5-169">예를 **들어,** 내부 또는 외부 SFB URL이 없는 경우(예: 이 목록에 해당 특정 레코드를 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="839d5-170">아래의 예제  *URL을* 추가 명령에서 실제 URL로 바꾸세요!</span><span class="sxs-lookup"><span data-stu-id="839d5-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. <span data-ttu-id="839d5-171">2단계에서 **Get-MsolServicePrincipal** 명령을 다시 실행하고 출력을 확인하여 새 레코드가 추가된지 확인</span><span class="sxs-lookup"><span data-stu-id="839d5-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="839d5-172">이전의 목록 또는 스크린샷을 새 SPNS 목록과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="839d5-173">레코드의 새 목록을 스크린샷할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="839d5-174">성공하면 목록에 두 개의 새 URL이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="839d5-175">이 예제에서는 이제 SPNS 목록에 특정 URL 및 을 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/ 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="839d5-176">EvoSTS Auth 서버 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="839d5-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="839d5-177">관리 셸에서 다음 비즈니스용 Skype 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-177">Run the following command in the Skype for Business Management Shell.</span></span>
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="839d5-178">하이브리드 최신 인증 사용</span><span class="sxs-lookup"><span data-stu-id="839d5-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="839d5-179">이는 실제로 MA를 켜는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="839d5-180">클라이언트 인증 흐름을 변경하지 않고도 이전의 모든 단계를 미리 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="839d5-181">인증 흐름을 변경할 준비가 되면 관리 셸의 비즈니스용 Skype 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="839d5-182">확인</span><span class="sxs-lookup"><span data-stu-id="839d5-182">Verify</span></span>

<span data-ttu-id="839d5-183">HMA를 사용하도록 설정하면 클라이언트의 다음 로그인에서 새 인증 흐름을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="839d5-184">HMA를 켜면 클라이언트에 대한 재인식이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="839d5-185">클라이언트는 인증 토큰 및/또는 보유한 인증의 수명을 기반으로 다시 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="839d5-186">HMA가 사용하도록 설정한 후 작동하고 있는지 테스트하려면 테스트 SFB 클라이언트에서 로그아웃하고 Windows '내 자격 증명 삭제'를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="839d5-187">다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-187">Sign in again.</span></span> <span data-ttu-id="839d5-188">이제 클라이언트는 최신 인증 흐름을 사용하게 되기  때문에 이제 로그인에 클라이언트가 서버에 연결하고 로그인하기 Office 365 바로 전에 '직장 또는 학교' 계정에 대한 Office 365 프롬프트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>
  
<span data-ttu-id="839d5-189">또한 클라이언트에서 'OAuth 비즈니스용 Skype'에 대한 '구성 정보'를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="839d5-190">클라이언트 컴퓨터에서 이 작업을 실행하려면 Ctrl 키를 눌러서 알림 비즈니스용 Skype 아이콘을 마우스 오른쪽 단추로 Windows 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="839d5-191">나타나는 **메뉴에서** 구성 정보를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="839d5-192">바탕 화면에 비즈니스용 Skype '구성 정보 확인' 창에서 다음을 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>
  
![최신 인증을 사용하는 비즈니스용 Skype 클라이언트의 구성 정보에는 Lync 및 EWS OAUTH 기관 URL이 https://login.windows.net/common/oauth2/authorize 표시됩니다.](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
<span data-ttu-id="839d5-194">또한 Outlook 클라이언트(Windows 알림 트레이에서도)의 아이콘을 마우스 오른쪽 단추로 클릭하고 '연결 상태'를 클릭하는 동시에 Ctrl 키를 눌러야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="839d5-195">OAuth에 사용되는 bearer 토큰을 나타내는 'Bearer'의 AuthN 유형에 대해 클라이언트의 SMTP 주소를 \* 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839d5-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="839d5-196">관련 문서</span><span class="sxs-lookup"><span data-stu-id="839d5-196">Related articles</span></span>

<span data-ttu-id="839d5-197">[최신 인증 개요로 다시 연결합니다.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="839d5-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>
  
<span data-ttu-id="839d5-198">클라이언트에 대해 ADAL(최신 인증)을 사용하는 방법을 알아야 비즈니스용 Skype 있나요?</span><span class="sxs-lookup"><span data-stu-id="839d5-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="839d5-199">여기에 단계가 [있습니다.](./hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="839d5-199">We've got steps [here](./hybrid-modern-auth-overview.md).</span></span>