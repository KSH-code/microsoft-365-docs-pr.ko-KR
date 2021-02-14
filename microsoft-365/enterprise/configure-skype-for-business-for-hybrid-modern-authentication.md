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
description: 하이브리드 HMA(최신 인증)를 사용하도록 비즈니스용 Skype를 구성하여 보다 안전한 사용자 인증 및 권한 부여를 제공하는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695023"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="d818d-103">하이브리드 최신 인증을 사용하도록 비즈니스용 Skype 온-프레미스를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="d818d-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="d818d-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d818d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d818d-105">최신 인증은 보다 안전한 사용자 인증 및 권한 부여를 제공하는 ID 관리 방법으로, 비즈니스용 Skype 서버(On-premises 및 Exchange server on-premises) 및 분할 도메인 비즈니스용 Skype 하이브리드에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>
  
 <span data-ttu-id="d818d-106">**중요** MA(최신 인증)에 대해 더 잘 알고자 하나요, 회사 또는 조직에서 이 인증을 사용하는 것이 좋은 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d818d-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="d818d-107">개요는 [이](hybrid-modern-auth-overview.md) 문서에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="d818d-108">MA에서 지원되는 비즈니스용 Skype 토폴로지가 필요한 경우 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>
  
 <span data-ttu-id="d818d-109">**시작하기 전에** 다음 용어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-109">**Before we begin**, I use these terms:</span></span>
  
- <span data-ttu-id="d818d-110">MA(최신 인증)</span><span class="sxs-lookup"><span data-stu-id="d818d-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="d818d-111">HMA(하이브리드 최신 인증)</span><span class="sxs-lookup"><span data-stu-id="d818d-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="d818d-112">EXCH(Exchange On-premises)</span><span class="sxs-lookup"><span data-stu-id="d818d-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="d818d-113">EXO(Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="d818d-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="d818d-114">비즈니스용 Skype(SFB)</span><span class="sxs-lookup"><span data-stu-id="d818d-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="d818d-115">SFBO(비즈니스용 Skype Online)</span><span class="sxs-lookup"><span data-stu-id="d818d-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="d818d-116">또한 이 문서의 그래픽에 회색으로 표시되거나 희미해진 개체가 있는 경우  이는 회색으로 표시된 요소가 MA 관련 구성에 포함되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>
  
## <a name="read-the-summary"></a><span data-ttu-id="d818d-117">요약 읽기</span><span class="sxs-lookup"><span data-stu-id="d818d-117">Read the summary</span></span>

<span data-ttu-id="d818d-118">이 요약은 프로세스를 실행 중에 손실될 수 있는 단계로 세분화하며 전체 검사 목록에서 프로세스의 위치를 추적하는 데 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>
  
1. <span data-ttu-id="d818d-119">먼저 모든 선행 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="d818d-120">비즈니스용  Skype와 Exchange 모두에 대해 많은 선행이 공통적이기 때문에 사전 다시 시작 검사 목록에 대한 개요 문서를 [참조하세요.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d818d-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="d818d-121">이  *문서의*  단계를 시작하기 전에 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="d818d-122">파일 또는 OneNote에 필요한 HMA 관련 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="d818d-123">EXO에 대한 최신 인증을 켜기(아직 켜져 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="d818d-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="d818d-124">SFBO에 대한 최신 인증을 켜기(아직 켜져 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="d818d-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="d818d-125">Exchange의 하이브리드 최신 인증을 켜고, Exchange의 모든 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="d818d-126">비즈니스용 Skype에 대한 하이브리드 최신 인증을 설정하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="d818d-127">이러한 단계는 SFB, SFBO, EXCH 및 EXO에 대한 MA를 켜는 것입니다. 즉, SFB 및 SFBO의 HMA 구성에 참여할 수 있는 모든 제품(EXCH/EXO에 대한 종속성 포함)</span><span class="sxs-lookup"><span data-stu-id="d818d-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="d818d-128">즉, 사용자가 하이브리드의 일부(EXO + SFBO, EXO + SFB, EXCH + SFBO 또는 EXCH + SFB)에 사서함을 만들거나 있는 경우 완료된 제품은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>
  
![혼합 6개의 비즈니스용 Skype HMA 토폴로지에는 네 가지 가능한 모든 위치에 MA가 있습니다.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
<span data-ttu-id="d818d-130">MA를 켜는 네 개의 다른 위치가 있습니다!</span><span class="sxs-lookup"><span data-stu-id="d818d-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="d818d-131">최상의 사용자 환경을 위해 이러한 네 위치에서 모두 MA를 켜는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="d818d-132">이러한 모든 위치에서 MA를 끄지 못하면 환경에 필요한 위치에서만 MA를 켜게 단계를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>
  
<span data-ttu-id="d818d-133">지원되는 [토폴로지의](https://technet.microsoft.com/library/mt803262.aspx) 경우 MA가 있는 비즈니스용 Skype에 대한 지원 가능성 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d818d-133">See the [Supportability topic for Skype for Business with MA](https://technet.microsoft.com/library/mt803262.aspx) for supported topologies.</span></span>
  
 <span data-ttu-id="d818d-134">**중요** 시작하기 전에 모든 선행 조처를 충족하는지 다시 한 번 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="d818d-135">이 정보는 하이브리드 최신 인증 개요 및 선행 사항에서 [찾을 수 있습니다.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d818d-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>
  
## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="d818d-136">필요한 모든 HMA 관련 정보 수집</span><span class="sxs-lookup"><span data-stu-id="d818d-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="d818d-137">최신 인증을 사용하기 위한 선행 [](hybrid-modern-auth-overview.md) 요구 사항을 충족하는지 다시 확인한 후(위의 참고 사항 참조) 앞 단계에서 HMA를 구성하는 데 필요한 정보를 저장하는 파일을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="d818d-138">이 문서에 사용된 예제:</span><span class="sxs-lookup"><span data-stu-id="d818d-138">Examples used in this article:</span></span>
  
- <span data-ttu-id="d818d-139">**SIP/SMTP 도메인**</span><span class="sxs-lookup"><span data-stu-id="d818d-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="d818d-140">예.</span><span class="sxs-lookup"><span data-stu-id="d818d-140">Ex.</span></span> <span data-ttu-id="d818d-141">contoso.com(Office 365와 페더된 경우)</span><span class="sxs-lookup"><span data-stu-id="d818d-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="d818d-142">**테넌트 ID**</span><span class="sxs-lookup"><span data-stu-id="d818d-142">**Tenant ID**</span></span>

  - <span data-ttu-id="d818d-143">Office 365 테넌트(로그인 시)를 나타내는 GUID입니다contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="d818d-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="d818d-144">**SFB 2015 CU5 웹 서비스 URL**</span><span class="sxs-lookup"><span data-stu-id="d818d-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="d818d-145">배포된 모든 SfB 2015 풀에 대한 내부 및 외부 웹 서비스 URL이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="d818d-146">이러한 정보를 얻었다면 비즈니스용 Skype 관리 셸에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="d818d-147">예.</span><span class="sxs-lookup"><span data-stu-id="d818d-147">Ex.</span></span> <span data-ttu-id="d818d-148">내부: https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d818d-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="d818d-149">예.</span><span class="sxs-lookup"><span data-stu-id="d818d-149">Ex.</span></span> <span data-ttu-id="d818d-150">외부: https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d818d-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="d818d-151">Standard Edition 서버를 사용하는 경우 내부 URL이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="d818d-152">이 경우 내부 URL에 풀 fqdn을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-152">In this case, use the pool fqdn for the internal URL.</span></span>
  
## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="d818d-153">EXO에 대한 최신 인증 켜기</span><span class="sxs-lookup"><span data-stu-id="d818d-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="d818d-154">다음 지침을 따릅니다. Exchange Online: 최신 인증을 위해 [테넌트를 사용하도록 설정하는 방법.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="d818d-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>
  
## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="d818d-155">SFBO에 대한 최신 인증 켜기</span><span class="sxs-lookup"><span data-stu-id="d818d-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="d818d-156">다음 지침을 따릅니다. [비즈니스용 Skype Online: 최신 인증을 위해 테넌트 사용.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="d818d-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="d818d-157">Exchange On-premises에 대한 하이브리드 최신 인증 켜기</span><span class="sxs-lookup"><span data-stu-id="d818d-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="d818d-158">다음 지침을 따릅니다. 하이브리드 최신 인증을 사용하도록 Exchange Server [구성하는 방법.](configure-exchange-server-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="d818d-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="d818d-159">비즈니스용 Skype의 하이브리드 최신 인증 켜기</span><span class="sxs-lookup"><span data-stu-id="d818d-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="d818d-160">Azure Active Directory에서 SPNS로 On-premises 웹 서비스 URL 추가</span><span class="sxs-lookup"><span data-stu-id="d818d-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="d818d-161">이제 SFBO에서 URL을 서비스 보안 주체로 추가하는 명령을 실행해야 합니다(이전 수집).</span><span class="sxs-lookup"><span data-stu-id="d818d-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>
  
 <span data-ttu-id="d818d-162">**참고** SPNS(서비스 사용자 이름)는 웹 서비스를 식별하고 보안 주체(예: 계정 이름 또는 그룹)와 연결하여 서비스가 인증된 사용자를 대신하여 작업할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="d818d-163">서버에 인증하는 클라이언트는 SPNS에 포함된 정보를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>
  
1. <span data-ttu-id="d818d-164">먼저 다음 지침을 사용하여 Azure AD(Azure Active [Directory)에 연결합니다.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="d818d-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

2. <span data-ttu-id="d818d-165">SFB 웹 서비스 URL 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="d818d-166">AppPrincipalId는 `00000004` .로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="d818d-167">이는 비즈니스용 Skype Online에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="d818d-168">SE 및 WS URL을 포함하지만 주로 0으로 시작하는 SPNS로 구성되는 이 명령의 출력(및 나중에 비교를 위한 스크린샷)을 `00000004-0000-0ff1-ce00-000000000000/` 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="d818d-169">예를 들어, 내부 또는 외부 SFB URL이 없는 경우(예: 이 목록에 해당 특정 레코드를  https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="d818d-170">아래 예제  *URL을* 추가 명령에서 실제 URL로 바꾸십시오!</span><span class="sxs-lookup"><span data-stu-id="d818d-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. <span data-ttu-id="d818d-171">2단계에서 **Get-MsolServicePrincipal** 명령을 다시 실행하고 출력을 확인하여 새 레코드가 추가된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="d818d-172">이전의 목록 또는 스크린샷을 SPNS의 새 목록과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="d818d-173">레코드에 대한 새 목록을 스크린샷할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="d818d-174">성공하면 목록에 두 개의 새 URL이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="d818d-175">이 예제를 통해 SPNS 목록에는 이제 특정 URL 및 를 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/ 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="d818d-176">EvoSTS Auth 서버 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="d818d-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="d818d-177">비즈니스용 Skype 관리 셸에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-177">Run the following command in the Skype for Business Management Shell.</span></span>
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="d818d-178">하이브리드 최신 인증 사용</span><span class="sxs-lookup"><span data-stu-id="d818d-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="d818d-179">이는 실제로 MA를 켜는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="d818d-180">클라이언트 인증 흐름을 변경하지 않고도 이전의 모든 단계를 미리 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="d818d-181">인증 흐름을 변경할 준비가 되면 비즈니스용 Skype 관리 셸에서 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="d818d-182">확인</span><span class="sxs-lookup"><span data-stu-id="d818d-182">Verify</span></span>

<span data-ttu-id="d818d-183">HMA를 사용하도록 설정하면 클라이언트의 다음 로그인에서 새 인증 흐름을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="d818d-184">HMA를 켜면 클라이언트에 대해 재인식이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="d818d-185">클라이언트는 인증 토큰 및/또는 보유한 인증의 수명을 기반으로 다시 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="d818d-186">HMA가 활성화된 후 작동하고 있는지 테스트하려면 테스트 SFB Windows 클라이언트에서 로그아웃하고 '내 자격 증명 삭제'를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="d818d-187">다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-187">Sign in again.</span></span> <span data-ttu-id="d818d-188">이제 클라이언트는 최신 인증 흐름을 사용하며 로그인에는 클라이언트가 서버에 연결하고 로그인하기 직전에 '직장 또는 학교' 계정에 대한 **Office 365** 프롬프트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>
  
<span data-ttu-id="d818d-189">또한 비즈니스용 Skype 클라이언트의 '구성 정보'에서 'OAuth 기관'을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="d818d-190">클라이언트 컴퓨터에서 이 작업을 실행하려면 Windows 알림 트레이에서 비즈니스용 Skype 아이콘을 마우스 오른쪽 단추로 클릭하는 동시에 Ctrl 키를 눌러야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="d818d-191">메뉴가 **나타나면** 구성 정보를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="d818d-192">바탕 화면에 나타나는 '비즈니스용 Skype 구성 정보' 창에서 다음을 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>
  
![최신 인증을 사용하는 비즈니스용 Skype 클라이언트의 구성 정보는 Lync 및 EWS OAUTH 기관 URL을 https://login.windows.net/common/oauth2/authorize 보여줍니다.](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
<span data-ttu-id="d818d-194">또한 Outlook 클라이언트(Windows 알림 트레이에서도)의 아이콘을 마우스 오른쪽 단추로 클릭하고 '연결 상태'를 클릭하는 동시에 Ctrl 키를 눌러야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="d818d-195">OAuth에 사용되는 보유자 토큰을 나타내는 'Bearer'의 AuthN 유형에 대해 클라이언트의 SMTP \* 주소를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d818d-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d818d-196">관련 문서</span><span class="sxs-lookup"><span data-stu-id="d818d-196">Related articles</span></span>

<span data-ttu-id="d818d-197">[최신 인증 개요로 다시 연결합니다.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d818d-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>
  
<span data-ttu-id="d818d-198">비즈니스용 Skype 클라이언트에 대해 ADAL(최신 인증)을 사용하는 방법을 알아야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d818d-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="d818d-199">여기에 단계가 [있습니다.](https://technet.microsoft.com/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="d818d-199">We've got steps [here](https://technet.microsoft.com/library/mt710548.aspx).</span></span>
