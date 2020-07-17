---
title: 도메인 FAQ
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 도메인에 대 한 자세한 내용은 질문과 대답을 확인 하세요.
ms.openlocfilehash: c588586ddd3d57fdbe78d7751131f61e6aa53eba
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068106"
---
# <a name="domains-faq"></a><span data-ttu-id="19524-103">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="19524-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="19524-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-104">The admin center is changing.</span></span> <span data-ttu-id="19524-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19524-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="19524-106">이 문서에는 Microsoft 365의 도메인에 대 한 질문과 대답이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="19524-107">질문에 대한 대답을 찾을 수 없는 경우 저희에게 메모를 남겨 알려주시면 목록에 추가해 드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="19524-108">이 문서의 내용</span><span class="sxs-lookup"><span data-stu-id="19524-108">In this article</span></span>

- [<span data-ttu-id="19524-109">MX 우선 순위란?</span><span class="sxs-lookup"><span data-stu-id="19524-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="19524-110">내 도메인에 대 한 SPF 레코드를 확인 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="19524-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="19524-111">도메인 이름 이란?</span><span class="sxs-lookup"><span data-stu-id="19524-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="19524-112">DNS 공급자가 특정 레코드 종류를 지원 하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="19524-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="19524-113">Microsoft 365에서 기본 도메인을 설정 하거나 변경 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="19524-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="19524-114">사용자 지정 하위 도메인 또는 여러 도메인을 Microsoft 365에 추가할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="19524-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="19524-115">"Onmicrosoft.com" 도메인을 보유 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="19524-115">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="19524-116">"Onmicrosoft.de" 도메인을 보유 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="19524-116">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="19524-117">비영리 또는 학력 상태를 확인 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="19524-117">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="19524-118">MX 우선 순위란?</span><span class="sxs-lookup"><span data-stu-id="19524-118">What is MX priority?</span></span>

<span data-ttu-id="19524-119">메일은 가장 낮은 기본 설정 번호 (가장 높은 우선 순위)를 사용 하 여 메일 교환 서버로 배달 되므로 메일 라우팅에 사용 하는 MX 레코드는 가장 낮은 기본 설정 번호 (일반적으로 0 또는 *높은* 우선 순위)를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-119">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="19524-120">MX 레코드를 만들 때 대부분의 DNS 호스팅 공급자가 기본 설정 번호를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-120">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="19524-121">일부 레이블은 box *기본 설정* 및 일부 레이블의 *우선 순위* 입니다.</span><span class="sxs-lookup"><span data-stu-id="19524-121">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="19524-122">일부 필요한 경우에는 *낮음* , *중간* 또는 *높음을* 선택 하 라는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-122">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="19524-123">MX 레코드가 하나인 경우에는 우선 순위 또는 기본 설정에 적절 한 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-123">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="19524-124">두 개 이상 있는 경우 메일 라우팅에 대 한 MX 레코드의 우선 순위가 도메인을 소유 하 고 있는지 확인 하는 데 사용 되는 것 보다 높은 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-124">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="19524-125">내 도메인에 대 한 SPF 레코드를 확인 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="19524-125">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="19524-126">**SPF에 대해서는 TXT 레코드를**하나만 만들거나 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-126">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="19524-127">SPF 레코드가 이미 있는 경우 새 Microsoft 365 값을 만드는 대신 새 사용자에 게 해당 레코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-127">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="19524-128">Microsoft 전자 메일에 대 한 SPF 레코드를 추가 하거나 업데이트 한 후 다음 도구 중 하나를 사용 하 여 구문이 올바른지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-128">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="19524-129">SPF 레코드 테스트 도구</span><span class="sxs-lookup"><span data-stu-id="19524-129">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="19524-130">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="19524-130">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="19524-131">웹 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19524-131">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="19524-132">도메인 이름 이란?</span><span class="sxs-lookup"><span data-stu-id="19524-132">What is a domain name?</span></span>

<span data-ttu-id="19524-133">도메인은 전자 메일 주소에서 **@** 기호 뒤에, 그리고 웹 주소에서 **www.**</span><span class="sxs-lookup"><span data-stu-id="19524-133">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="19524-134">뒤에 나타나는 고유한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="19524-134">in web addresses.</span></span> <span data-ttu-id="19524-135">일반적으로 *yourbusiness.com* 또는 stateuniversity.edu와 같은 표준 인터넷 접미사와 조직의 이름 형식을 사용 합니다 *.*</span><span class="sxs-lookup"><span data-stu-id="19524-135">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="19524-136">"**Rob \@ contoso.com**"과 같은 사용자 지정 도메인을 Microsoft 365와 함께 사용 하면 신용 및 브랜드를 위한 신뢰도를 구축 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-136">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="19524-137">[Microsoft 365에서 도메인을 구입 하 여 자동으로 설정](../get-help-with-domains/buy-a-domain-name.md)하거나 이미 도메인 등록 기관에서 소유한 사용자를 구입 하거나 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-137">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="19524-138">DNS 공급자가 특정 레코드 종류를 지원 하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="19524-138">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="19524-139">자체 DNS 레코드를 관리 하는 경우 DNS 호스트에서 Microsoft 365에 필요한 모든 DNS 레코드를 지원 하지 않으면 일부 Microsoft 365 기능이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-139">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="19524-140">필요한 모든 DNS 레코드를 지 원하는 등록자에 게 도메인을 전송 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-140">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="19524-141">필요한 모든 DNS 레코드를 지 원하는 공급자:</span><span class="sxs-lookup"><span data-stu-id="19524-141">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="19524-142">Dynadot</span><span class="sxs-lookup"><span data-stu-id="19524-142">Dynadot</span></span>
    
- <span data-ttu-id="19524-143">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="19524-143">eNomCentral</span></span>
    
- <span data-ttu-id="19524-144">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="19524-144">Europe Registry</span></span>
    
- <span data-ttu-id="19524-145">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="19524-145">GoDaddy</span></span>
    
- <span data-ttu-id="19524-146">가리키기</span><span class="sxs-lookup"><span data-stu-id="19524-146">Hover</span></span>
    
- <span data-ttu-id="19524-147">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="19524-147">MyHosting.com</span></span>
    
- <span data-ttu-id="19524-148">Name.com</span><span class="sxs-lookup"><span data-stu-id="19524-148">Name.com</span></span>
    
- <span data-ttu-id="19524-149">거의 무료 음성</span><span class="sxs-lookup"><span data-stu-id="19524-149">Nearly Free Speech</span></span>
    
- <span data-ttu-id="19524-150">Nettica</span><span class="sxs-lookup"><span data-stu-id="19524-150">Nettica</span></span>
    
- <span data-ttu-id="19524-151">NIC(Network Information Center)</span><span class="sxs-lookup"><span data-stu-id="19524-151">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="19524-152">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="19524-152">Network Solutions</span></span>
    
- <span data-ttu-id="19524-153">Register.com</span><span class="sxs-lookup"><span data-stu-id="19524-153">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="19524-154">Microsoft 365에서 기본 도메인을 설정 하거나 변경 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="19524-154">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="19524-155">기본 도메인을 선택 하려면 먼저 Microsoft 365에 추가한 사용자 지정 도메인이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-155">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="19524-156">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="19524-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="19524-157">I관리 센터에서 \*\* 설정 \*\* > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="19524-157">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="19524-158">I관리 센터에서 \*\* 설정 \*\* > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="19524-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="19524-159">**도메인** 페이지에서 새 전자 메일 주소에 대 한 기본값으로 설정할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-159">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="19524-160">**기본값으로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-160">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="19524-161">*Onmicrosoft.com* 도메인의 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-161">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="19524-162">*Onmicrosoft.de* 도메인의 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-162">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="19524-163">*Partner.onmschina.cn* 도메인의 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-163">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="19524-164">사용자 지정 하위 도메인 또는 여러 도메인을 Microsoft 365에 추가할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="19524-164">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="19524-165">예.</span><span class="sxs-lookup"><span data-stu-id="19524-165">Yes.</span></span> <span data-ttu-id="19524-166">하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-166">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="19524-167">Microsoft에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 하거나 Microsoft 로부터 도메인을 구매한 경우에는 하위 도메인을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-167">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="19524-168">예로!</span><span class="sxs-lookup"><span data-stu-id="19524-168">Yes!</span></span> <span data-ttu-id="19524-169">하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-169">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="19524-170">Microsoft에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 하거나 Microsoft 로부터 도메인을 구매한 경우에는 하위 도메인을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-170">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="19524-171">예로!</span><span class="sxs-lookup"><span data-stu-id="19524-171">Yes!</span></span> <span data-ttu-id="19524-172">하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-172">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="19524-173">21Vianet에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 허용 하는 경우 하위 도메인을 추가 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19524-173">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="19524-174">일반적으로 Microsoft 365 구독에는 최대 900 개의 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-174">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="19524-175">예를 들어 contoso.com 및 contosomarketing.com 도메인을 추가한 다음 하위 도메인 www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com 등을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-175">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="19524-176">하위 도메인을 추가 하면 유효성이 확인 되는 상위 도메인을 기반으로 자동으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19524-176">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="19524-177">Microsoft 365에 여러 도메인을 추가 하면 추가한 도메인에서 모든 서비스 (예를 들어 전자 메일)를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-177">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="19524-178">*도메인의 MX 레코드를 업데이트 하 여 Microsoft 365에 대 한 전자 메일을 변경 하면 해당 도메인으로 전송 된 모든 전자 메일이 Microsoft 365로 시작 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="19524-178">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="19524-179">Microsoft 365 구독에 contoso.com 도메인을 추가한 경우 다른 Microsoft 365 조직에 하위 도메인 xyz.contoso.com를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-179">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="19524-180">하위 도메인을 추가할 때 DNS 호스팅 공급자에 TXT 레코드를 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19524-180">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="19524-181">"Onmicrosoft.com" 도메인을 보유 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="19524-181">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="19524-182">Microsoft 365는 서비스에 등록할 때 *contoso.onmicrosoft.com*와 같은 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="19524-182">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="19524-183">등록할 때 만드는 사용자 ID에는 *alan@contoso.onmicrosoft.com*와 같은 도메인이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19524-183">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="19524-184">**전자 메일을 *alan \@ contoso.com*:** 으로 지정 하려면 [도메인을 구입](../get-help-with-domains/buy-a-domain-name.md) 하거나 [사용자 및 도메인을 이미 소유 하 고 있는 경우 Microsoft 365에 추가](add-domain.md) 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-184">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="19524-185">**등록 후에는 onmicrosoft 도메인의 이름을 바꿀 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="19524-185">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="19524-186">예를 들어 선택한 초기 도메인이 fourthcoffee.onmicrosoft.com 인 경우 fabrikam.onmicrosoft.com로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-186">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="19524-187">다른 onmicrosoft.com 도메인을 사용 하려면 Microsoft 365을 사용 하 여 새 구독을 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-187">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="19524-188">**팀 사이트 URL의 이름은 바꿀 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="19524-188">**You can't rename your team site URL.**</span></span> <span data-ttu-id="19524-189">팀 사이트 URL은 onmicrosoft.com 도메인 이름을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-189">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="19524-190">아쉽게도 SharePoint Online 아키텍처의 작동 방식 때문에 팀 사이트의 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-190">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="19524-191">**Onmicrosoft 도메인은 제거할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="19524-191">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="19524-192">Microsoft 365는 구독을 위해 배후에서 사용 되 고 있으므로 주변을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-192">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="19524-193">하지만 사용자 지정 도메인을 추가한 후에는 직접 도메인을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-193">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="19524-194">도메인을 추가한 후에도 초기 onmicrosoft.com 도메인을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-194">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="19524-195">여전히 전자 메일 및 기타 서비스에 대해 작동 하기 때문에 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-195">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="19524-196">"Onmicrosoft.de" 도메인을 보유 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="19524-196">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="19524-197">Microsoft 365는 서비스에 등록할 때 *contoso.onmicrosoft.de*와 같은 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="19524-197">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="19524-198">등록할 때 만드는 사용자 ID에는 *alan@contoso.onmicrosoft.de*와 같은 도메인이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19524-198">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="19524-199">**전자 메일을 *alan@contoso.de*같이 표시 하려면** [도메인을 구입](../get-help-with-domains/buy-a-domain-name.md) 하거나 [사용자와 도메인을 이미 소유한 경우 Microsoft 365에 추가](add-domain.md) 의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="19524-199">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="19524-200">**등록 후에는 onmicrosoft 도메인의 이름을 바꿀 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="19524-200">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="19524-201">예를 들어 선택한 초기 도메인이 fourthcoffee.onmicrosoft.de 인 경우 fabrikam.onmicrosoft.de로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-201">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="19524-202">다른 onmicrosoft.de 도메인을 사용 하려면 Microsoft 365을 사용 하 여 새 구독을 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-202">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="19524-203">**팀 사이트 URL의 이름은 바꿀 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="19524-203">**You can't rename your team site URL.**</span></span> <span data-ttu-id="19524-204">팀 사이트 URL은 onmicrosoft.de 도메인 이름을 기반으로 합니다. 아쉽게도 SharePoint Online 아키텍처의 작동 방식 때문에 팀 사이트의 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-204">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="19524-205">**Onmicrosoft 도메인은 제거할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="19524-205">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="19524-206">Microsoft 365는 구독을 위해 배후에서 사용 되 고 있으므로 주변을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-206">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="19524-207">하지만 사용자 지정 도메인을 추가한 후에는 직접 도메인을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-207">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="19524-208">도메인을 추가한 후에도 초기 onmicrosoft.de 도메인을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-208">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="19524-209">여전히 전자 메일 및 기타 서비스에 대해 작동 하기 때문에 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-209">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="19524-210">비영리 또는 학력 상태를 확인 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="19524-210">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="19524-211">[관리 센터](https://docs.microsoft.com/microsoft-365/admin/admin-home) 에서 **설치** 를 선택 하 여 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-211">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="19524-212">(먼저 Microsoft 365에 로그인 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="19524-212">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="19524-213">학교 관리자가 되기 위해 Microsoft 365에서 **관리자로가** 는 것으로 관리 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-213">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="19524-214">도메인에 대 한 DNS 호스트 웹 사이트에 TXT DNS 레코드를 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19524-214">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="19524-215">다음과 같은 이유 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="19524-215">Why?</span></span> <span data-ttu-id="19524-216">DNS 호스트에 로그인 하 고 도메인에 대 한 레코드를 추가 하는 경우 Microsoft 365에서 도메인 이름을 소유 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-216">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="19524-217">레코드를 추가한 후 Microsoft 365 포털로 돌아가서 추가 된 내용을 확인 한 다음 Microsoft 365에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19524-217">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="19524-218">Microsoft 365을 받으려면 비영리이 있나요?</span><span class="sxs-lookup"><span data-stu-id="19524-218">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="19524-219">[조직에서](https://www.microsoft.com/en-us/nonprofits/eligibility) 서비스를 확인 한 다음 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="19524-219">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="19524-220">학교에서 관리자 되는 것에 대해 자세히 알고 싶으십니까?</span><span class="sxs-lookup"><span data-stu-id="19524-220">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="19524-221">를 [참고](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)하세요.</span><span class="sxs-lookup"><span data-stu-id="19524-221">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>