---
title: 도메인 FAQ
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: FAQ에서 질문에 대 한 답변을 찾아 Office 365의 도메인에 대해 자세히 알아보세요.
ms.custom: okr_smb
ms.openlocfilehash: f3c72f1ce772e3021d79aa4568dbfdb700400803
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257018"
---
# <a name="domains-faq"></a><span data-ttu-id="a7340-103">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="a7340-103">Domains FAQ</span></span>

<span data-ttu-id="a7340-104">이 문서에는 Office 365의 도메인에 대 한 질문과 대답이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-104">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="a7340-105">질문에 대한 대답을 찾을 수 없는 경우 저희에게 메모를 남겨 알려주시면 목록에 추가해 드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-105">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="a7340-106">MX 우선 순위란?</span><span class="sxs-lookup"><span data-stu-id="a7340-106">What is MX priority?</span></span>

<span data-ttu-id="a7340-107">메일은 가장 낮은 기본 설정 번호 (가장 높은 우선 순위)를 사용 하 여 메일 교환 서버로 배달 되므로 메일 라우팅에 사용 하는 MX 레코드는 가장 낮은 기본 설정 번호 (일반적으로 0 또는 *높은* 우선 순위)를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-107">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="a7340-108">MX 레코드를 만들 때 대부분의 DNS 호스팅 공급자가 기본 설정 번호를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-108">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="a7340-109">일부 레이블은 box *기본 설정* 및 일부 레이블의 *우선 순위* 입니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-109">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="a7340-110">일부 필요한 경우에는 *낮음* , *중간* 또는 *높음을* 선택 하 라는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-110">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="a7340-111">MX 레코드가 하나인 경우에는 우선 순위 또는 기본 설정에 적절 한 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-111">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="a7340-112">두 개 이상 있는 경우 메일 라우팅에 대 한 MX 레코드의 우선 순위가 도메인을 소유 하 고 있는지 확인 하는 데 사용 되는 것 보다 높은 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-112">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="a7340-113">내 도메인에 대 한 SPF 레코드를 확인 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="a7340-113">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="a7340-114">**SPF에 대해서는 TXT 레코드를**하나만 만들거나 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-114">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="a7340-115">SPF 레코드가 이미 있는 경우 새 Office 365 값을 만드는 대신 새로 만들어 해당 레코드에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-115">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="a7340-116">Office 365 전자 메일에 대 한 SPF 레코드를 추가 하거나 업데이트 한 후 다음 도구 중 하나를 사용 하 여 해당 구문이 올바른지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-116">After you've added or updated your SPF record for Office 365 email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="a7340-117">SPF 레코드 테스트 도구</span><span class="sxs-lookup"><span data-stu-id="a7340-117">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="a7340-118">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="a7340-118">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="a7340-119">웹 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7340-119">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="a7340-120">Office 365에서 내 DNS 레코드를 관리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a7340-120">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="a7340-121">Office 365의 DNS 관리에 대 한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-121">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="a7340-122">NS (이름 서버) 레코드를 변경 하면 전자 메일에 대 한 MX 레코드를 설정 하는 것 처럼 Office 365에서 모든 서비스 관련 레코드를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-122">You change your nameserver (NS) records, and then Office 365 takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="a7340-123">**는**</span><span class="sxs-lookup"><span data-stu-id="a7340-123">**(Recommended)**</span></span>
    
2. <span data-ttu-id="a7340-124">DNS 호스트에서 전자 메일 및 기타 Office 365 서비스에 대 한 DNS 레코드를 직접 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-124">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="a7340-125">**(전문가 전용)**</span><span class="sxs-lookup"><span data-stu-id="a7340-125">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="a7340-126">Office 365에서 DNS 레코드를 만들고 호스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-126">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="a7340-127">**장점**</span><span class="sxs-lookup"><span data-stu-id="a7340-127">**Advantages**</span></span> 
- <span data-ttu-id="a7340-128">Office 365 서비스의 DNS 레코드에 대해 입력 한 값으로 실수를 염려할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-128">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="a7340-129">도메인 등록자와 DNS 호스트를 보다 유연 하 게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-129">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="a7340-130">공급자가 필요한 모든 레코드 형식을 지원 하지 않더라도 이름 서버 레코드를 변경할 수 있는 공급자가 모두 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-130">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="a7340-131">Office 365에서 새 DNS 레코드를 추가 하는 경우에는 업데이트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-131">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="a7340-132">단점</span><span class="sxs-lookup"><span data-stu-id="a7340-132">Disadvantages</span></span> 
- <span data-ttu-id="a7340-133">Office 365 외부에서 전자 메일을 호스팅하도록 DNS 레코드를 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-133">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="a7340-134">Www.fourthcoffee.com와 같이 해당 주소에 대해 도메인에 공용 웹 사이트를 이미 사용 하 고 있는 경우에는 Office 365에서 해당 주소로 사용자를 리디렉션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-134">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="a7340-135">리디렉션을 설정 하려면 고정 IP 주소가 필요 하며, 공개 웹 사이트에는 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-135">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="a7340-136">-현재 도메인 등록 기관에서 도메인의 이름 서버 레코드를 변경 하는 것을 허용 하지 않는 경우이 DNS 관리 옵션을 사용 하려면 다른 등록 기관으로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-136">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="a7340-137">직접 DNS 레코드를 관리 하는 경우</span><span class="sxs-lookup"><span data-stu-id="a7340-137">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="a7340-138">장점</span><span class="sxs-lookup"><span data-stu-id="a7340-138">Advantages</span></span>
- <span data-ttu-id="a7340-139">Office 365 서비스에 대 한 DNS 레코드를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-139">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="a7340-140">Www.fourthcoffee.com 처럼 해당 주소에 대 한 도메인을 가진 공개 웹 사이트가 있는 경우에는 리디렉션을 사용 하 여 Office 365에서 도메인을 설정한 후에도 사용자의 웹 사이트에 계속 액세스할 수 있도록 하는 데 신경 쓰지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-140">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="a7340-141">온-프레미스 Exchange 서버와 같은 다른 위치에서 전자 메일을 호스팅할 수 있는 유연성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-141">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="a7340-142">단점</span><span class="sxs-lookup"><span data-stu-id="a7340-142">Disadvantages</span></span>
<span data-ttu-id="a7340-143">Office 365 서비스에 대 한 DNS 레코드를 직접 설정 해야 합니다 (GoDaddy 도메인을 갖고 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="a7340-143">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="a7340-144">현재 DNS 호스트가 Office 365에 필요한 레코드 종류 중 일부를 지원 하지 않는 경우 일부 Office 365 기능을 사용할 수 없으며 다른 DNS 호스트로 전환 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-144">If your current DNS host doesn't support all of the required record types for Office 365, some Office 365 features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="a7340-145">Office 365에서 DNS 레코드에 대 한 요구 사항을 변경 하거나 새 서비스를 추가 하는 경우 DNS 호스트에서 직접 업데이트를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-145">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="a7340-146">도메인 이름 이란?</span><span class="sxs-lookup"><span data-stu-id="a7340-146">What is a domain name?</span></span>


<span data-ttu-id="a7340-147">도메인은 전자 메일 주소에서 **@** 기호 뒤에, 그리고 웹 주소에서 **www.**</span><span class="sxs-lookup"><span data-stu-id="a7340-147">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="a7340-148">뒤에 나타나는 고유한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-148">in web addresses.</span></span> <span data-ttu-id="a7340-149">일반적으로 *yourbusiness.com* 또는 stateuniversity.edu와 같은 표준 인터넷 접미사와 조직의 이름 형식을 사용 합니다 *.*</span><span class="sxs-lookup"><span data-stu-id="a7340-149">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="a7340-150">"**Rob\@contoso.com**"와 같은 사용자 지정 도메인을 Office 365와 함께 사용 하면 신용 및 브랜드를 위한 신뢰도를 구축 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-150">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="a7340-151">[Office 365에서 도메인을 구입 하 여이를 자동으로 설정](../get-help-with-domains/buy-a-domain-name.md)하거나 이미 도메인 등록 기관에서 소유한 사용자를 구입 하거나 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-151">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="a7340-152">Microsoft에서 구입한 도메인을 다른 공급자에 게 전송할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a7340-152">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="a7340-153">예, 그러나 office 365 도메인을 다른 등록 365 60 기관으로 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-153">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="a7340-154">*Whois* 쿼리에는 Office 365 구매한 도메인 등록 자가 와일드 서 지 도메인 LLC로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-154">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="a7340-155">그러나 Office 365 구매한 도메인에 대 한 Office 365에만 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-155">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="a7340-156">아래 단계에 따라 Office 365의 코드를 가져온 다음 다른 도메인 등록 기관 웹 사이트로 이동 하 여 해당 등록자에 게 도메인 이름을 전송 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-156">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>
  
1. <span data-ttu-id="a7340-157">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="a7340-158">Office 365 독일를 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-158">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="a7340-159">21Vianet에서 운영 하는 Office 365를 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-159">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a7340-160">**도메인** 페이지에서 다른 도메인 등록자에 게 전송할 Office 365 도메인을 선택 하 고 **도메인 전송을** > **사용 하 여 도메인 전송을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-160">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="a7340-161">단계에 따라 도메인 전송을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-161">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="a7340-162">코드를 받은 후 도메인 이름을 관리 하려는 도메인 등록 기관 웹 사이트로 이동 하 여 도메인을 전송 하기 위한 지침을 따르세요 (웹 사이트에서 도움말 검색).</span><span class="sxs-lookup"><span data-stu-id="a7340-162">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="a7340-163">코드를 다시 표시 해야 하는 경우에는 Office 365의 **도메인 설정** 페이지에서 **도메인 전송을 위한 인증 코드 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-163">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="a7340-164">전송이 완료 되 면 새 도메인 등록 기관에서 도메인을 갱신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-164">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="a7340-165">프로세스를 마치려면 관리 센터 **도메인** 페이지로 돌아가 **전체 도메인 전송을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-165">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="a7340-166">*참고: Office 365에서 구매한 도메인은 이름 서버 변경 또는 Office 365 테 넌 트 간에 도메인을 전송 하기에 적합 하지 않습니다.  이러한 두 가지 중 하나가 필요한 경우 도메인 등록을 다른 등록자에 게 전송 해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="a7340-166">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="a7340-167">Office 365에서 내 DNS 레코드를 관리 하는 방법을 변경 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="a7340-167">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="a7340-168">DNS 관리를 Office 365 외부의 DNS 호스트로 변경</span><span class="sxs-lookup"><span data-stu-id="a7340-168">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="a7340-169">도메인의 도메인 등록 기관에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-169">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="a7340-170">등록자 웹 사이트에서 이름 서버 레코드를 업데이트 하는 영역을 찾고 도메인의 DNS 호스트를 가리키도록 이름 서버을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-170">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span></span> <span data-ttu-id="a7340-171">DNS 호스트는 종종 도메인 등록자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-171">(The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="a7340-172">다음 링크를 통해 도메인 설정 마법사로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-172">Follow a link to go to the domains setup wizard:</span></span>
    
4. <span data-ttu-id="a7340-173">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-173">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="a7340-174">Office 365 독일를 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-174">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="a7340-175">21Vianet에서 운영 하는 Office 365를 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-175">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
5. <span data-ttu-id="a7340-176">**도메인** 페이지에서 전환 중인 도메인을 선택 하 고 **DNS 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-176">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="a7340-177">도메인 설정 마법사의 **온라인 서비스 설정** 페이지에서 **직접 DNS 레코드 관리**를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-177">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="a7340-178">**Dns 설정 업데이트** 페이지에서 마법사가 제안한 dns 레코드를 등록자의 웹 사이트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-178">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="a7340-179">레코드를 추가한 후에는 Office 365로 돌아와서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-179">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="a7340-180">DNS 관리를 Office 365으로 변경</span><span class="sxs-lookup"><span data-stu-id="a7340-180">Change DNS management to Office 365</span></span>
  
1. <span data-ttu-id="a7340-181">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-181">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="a7340-182">Office 365 독일를 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-182">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="a7340-183">21Vianet에서 운영 하는 Office 365를 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-183">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a7340-184">**도메인** 페이지에서 전환 중인 도메인을 선택 하 고 **DNS 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-184">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="a7340-185">도메인 설정 마법사의 **온라인 서비스 설정** 페이지에서 **내 온라인 서비스 설정을 선택 합니다. (권장)** 를 선택한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-185">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a7340-186">아직 도메인을 확인 하지 않은 경우에는이 단계를 수행 하 여 먼저이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-186">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="a7340-187">**DNS 설정 업데이트** 페이지에서 Office 365에 대 한 이름 서버를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-187">On the **Update DNS settings** page, we list the nameservers for Office 365.</span></span> <span data-ttu-id="a7340-188">도메인의 도메인 등록 기관으로 이동 하 여 이름 서버를 Office 365 이름 서버로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-188">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="a7340-189">이름 서버를 업데이트 한 후 **1 시간 이상 기다립니다**.</span><span class="sxs-lookup"><span data-stu-id="a7340-189">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="a7340-190">그런 다음 Office 365에서 마법사를 다시 클릭 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-190">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="a7340-191">DNS 공급자가 특정 레코드 종류를 지원 하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="a7340-191">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="a7340-192">자체 DNS 레코드를 관리 하는 경우 DNS 호스트가 Office 365에 필요한 모든 DNS 레코드를 지원 하지 않으면 일부 Office 365 기능이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-192">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span></span> <span data-ttu-id="a7340-193">필요한 모든 DNS 레코드를 지 원하는 등록자에 게 도메인을 전송 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-193">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="a7340-194">필요한 모든 DNS 레코드를 지 원하는 공급자:</span><span class="sxs-lookup"><span data-stu-id="a7340-194">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="a7340-195">Dynadot</span><span class="sxs-lookup"><span data-stu-id="a7340-195">Dynadot</span></span>
    
- <span data-ttu-id="a7340-196">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="a7340-196">eNomCentral</span></span>
    
- <span data-ttu-id="a7340-197">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="a7340-197">Europe Registry</span></span>
    
- <span data-ttu-id="a7340-198">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="a7340-198">GoDaddy</span></span>
    
- <span data-ttu-id="a7340-199">가리키기</span><span class="sxs-lookup"><span data-stu-id="a7340-199">Hover</span></span>
    
- <span data-ttu-id="a7340-200">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="a7340-200">MyHosting.com</span></span>
    
- <span data-ttu-id="a7340-201">Name.com</span><span class="sxs-lookup"><span data-stu-id="a7340-201">Name.com</span></span>
    
- <span data-ttu-id="a7340-202">거의 무료 음성</span><span class="sxs-lookup"><span data-stu-id="a7340-202">Nearly Free Speech</span></span>
    
- <span data-ttu-id="a7340-203">Nettica</span><span class="sxs-lookup"><span data-stu-id="a7340-203">Nettica</span></span>
    
- <span data-ttu-id="a7340-204">NIC(Network Information Center)</span><span class="sxs-lookup"><span data-stu-id="a7340-204">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="a7340-205">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="a7340-205">Network Solutions</span></span>
    
- <span data-ttu-id="a7340-206">Register.com</span><span class="sxs-lookup"><span data-stu-id="a7340-206">Register.com</span></span>
    
 <span data-ttu-id="a7340-207">**SRV 레코드가 지원 되지 않으면**다음과 같은 Office 365 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-207">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="a7340-208">Outlook Web App과의 비즈니스용 Skype 온라인 IM 및 현재 상태 통합</span><span class="sxs-lookup"><span data-stu-id="a7340-208">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="a7340-209">다른 조직의 비즈니스용 Skype Online 사용자와의 외부 통신 (페더레이션)</span><span class="sxs-lookup"><span data-stu-id="a7340-209">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="a7340-210">Microsoft 계정 (이전의 Windows Live ID)으로 로그인 한 비즈니스용 Skype Online 사용자와의 공용 인터넷 연결 (PIC)</span><span class="sxs-lookup"><span data-stu-id="a7340-210">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="a7340-211">**여러 CNAME 레코드를 지원 하지 않는 경우** 비즈니스용 Skype Online에 대해 다음 기능 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-211">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="a7340-212">전자 메일 데스크톱 클라이언트와 모바일 클라이언트는 자동 검색을 사용 하 여 사용자가 서버 이름을 입력 하지 않고도 로그인 할 수 있도록 Exchange Online 서비스를 자동적으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-212">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="a7340-213">비즈니스용 skype Online 데스크톱 클라이언트는 자동 검색을 사용 하 여 사용자가 서버 이름을 입력 하지 않고도 로그인 할 수 있도록 비즈니스용 Skype Online 서비스를 자동적으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-213">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="a7340-214">비즈니스용 skype Online 모바일 클라이언트는 자동 검색을 사용 하 여 사용자가 서버 이름을 입력 하지 않고도 로그인 할 수 있도록 비즈니스용 Skype Online 서비스를 자동적으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-214">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
 <span data-ttu-id="a7340-215">**SPF/TXT 레코드를 지원 하지 않는 경우**다른 사용자가 사용자의 도메인을 사용 하 여 스팸 또는 기타 악성 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-215">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span></span> <span data-ttu-id="a7340-216">SPF 레코드는 도메인에서 전자 메일을 보낼 수 있는 권한이 부여 된 서버를 식별 하는 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-216">SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="a7340-217">Office 365에서 기본 도메인을 설정 하거나 변경 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="a7340-217">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="a7340-218">기본 도메인을 선택 하려면 먼저 Office 365에 추가한 사용자 지정 도메인이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-218">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>
  
1. <span data-ttu-id="a7340-219">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-219">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="a7340-220">Office 365 독일를 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-220">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="a7340-221">21Vianet에서 운영 하는 Office 365를 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-221">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a7340-222">**도메인** 페이지에서 새 전자 메일 주소에 대 한 기본값으로 설정할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-222">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="a7340-223">**기본값으로 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-223">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="a7340-224">*Onmicrosoft.com* 도메인의 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-224">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="a7340-225">*Onmicrosoft.de* 도메인의 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-225">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="a7340-226">*Partner.onmschina.cn* 도메인의 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-226">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="a7340-227">사용자 지정 하위 도메인 또는 여러 도메인을 Office 365에 추가할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a7340-227">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="a7340-228">예로!</span><span class="sxs-lookup"><span data-stu-id="a7340-228">Yes!</span></span> <span data-ttu-id="a7340-229">하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-229">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="a7340-230">Microsoft에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 하거나 Microsoft 로부터 도메인을 구매한 경우에는 하위 도메인을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-230">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="a7340-231">예로!</span><span class="sxs-lookup"><span data-stu-id="a7340-231">Yes!</span></span> <span data-ttu-id="a7340-232">하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-232">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="a7340-233">Microsoft에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 하거나 Microsoft 로부터 도메인을 구매한 경우에는 하위 도메인을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-233">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="a7340-234">예로!</span><span class="sxs-lookup"><span data-stu-id="a7340-234">Yes!</span></span> <span data-ttu-id="a7340-235">하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-235">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="a7340-236">21Vianet에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 허용 하는 경우 하위 도메인을 추가 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-236">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="a7340-237">일반적으로 Office 365 구독에는 최대 900 개의 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-237">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="a7340-238">예를 들어 contoso.com 및 contosomarketing.com 도메인을 추가한 다음 하위 도메인 www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com 등을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-238">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="a7340-239">하위 도메인을 추가 하면 유효성이 확인 되는 상위 도메인을 기반으로 자동으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-239">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="a7340-240">여러 도메인을 Office 365에 추가 하면 추가한 도메인에서 모든 서비스 (예를 들어 전자 메일)를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-240">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="a7340-241">*도메인의 MX 레코드를 업데이트 하 여 전자 메일을 Office 365로 변경 하면 해당 도메인으로 전송 된 모든 전자 메일이 Office 365로 시작 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="a7340-241">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="a7340-242">이미 Office 365 테 넌 트에 contoso.com 도메인을 추가한 경우에는 다른 Office 365 테 넌 트에 xyz.contoso.com 하위 도메인을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-242">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="a7340-243">하위 도메인을 추가할 때 DNS 호스팅 공급자에 TXT 레코드를 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-243">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="a7340-244">"Onmicrosoft.com" 도메인을 보유 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="a7340-244">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="a7340-245">Office 365에서는 서비스에 등록할 때 *contoso.onmicrosoft.com*와 같은 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-245">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="a7340-246">등록할 때 만드는 사용자 ID에는 *alan@contoso.onmicrosoft.com*와 같은 도메인이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-246">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="a7340-247">**전자 메일을 *\@alan contoso.com*:** 으로 지정 하려면 [도메인을 구입](../get-help-with-domains/buy-a-domain-name.md) 하거나 사용자 및 도메인을 이미 소유 하 고 있는 경우 [Office 365에 추가](add-domain.md) 의 단계를 수행 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7340-247">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="a7340-248">**등록 후에는 onmicrosoft 도메인의 이름을 바꿀 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7340-248">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="a7340-249">예를 들어 선택한 초기 도메인이 fourthcoffee.onmicrosoft.com 인 경우 fabrikam.onmicrosoft.com로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-249">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="a7340-250">다른 onmicrosoft.com 도메인을 사용 하려면 Office 365에서 새 구독을 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-250">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="a7340-251">**팀 사이트 URL의 이름은 바꿀 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7340-251">**You can't rename your team site URL.**</span></span> <span data-ttu-id="a7340-252">팀 사이트 URL은 onmicrosoft.com 도메인 이름을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-252">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="a7340-253">아쉽게도 SharePoint Online 아키텍처의 작동 방식 때문에 팀 사이트의 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-253">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="a7340-254">**Onmicrosoft 도메인은 제거할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7340-254">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="a7340-255">Office 365에서는 구독을 위해 백그라운드에서 사용 되기 때문에이를 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-255">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="a7340-256">하지만 사용자 지정 도메인을 추가한 후에는 직접 도메인을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-256">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="a7340-257">도메인을 추가한 후에도 초기 onmicrosoft.com 도메인을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-257">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="a7340-258">여전히 전자 메일 및 기타 서비스에 대해 작동 하기 때문에 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-258">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="a7340-259">"Onmicrosoft.de" 도메인을 보유 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="a7340-259">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="a7340-260">Office 365에서는 서비스에 등록할 때 *contoso.onmicrosoft.de*와 같은 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-260">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="a7340-261">등록할 때 만드는 사용자 ID에는 *alan@contoso.onmicrosoft.de*와 같은 도메인이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-261">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="a7340-262">**전자 메일을 *alan@contoso.de*같이 표시 하려면** [도메인을 구입](../get-help-with-domains/buy-a-domain-name.md) 하거나 [사용자와 도메인을 이미 소유한 경우 Office 365에 추가](add-domain.md) 의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a7340-262">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="a7340-263">**등록 후에는 onmicrosoft 도메인의 이름을 바꿀 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7340-263">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="a7340-264">예를 들어 선택한 초기 도메인이 fourthcoffee.onmicrosoft.de 인 경우 fabrikam.onmicrosoft.de로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-264">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="a7340-265">다른 onmicrosoft.de 도메인을 사용 하려면 Office 365에서 새 구독을 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-265">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="a7340-266">**팀 사이트 URL의 이름은 바꿀 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7340-266">**You can't rename your team site URL.**</span></span> <span data-ttu-id="a7340-267">팀 사이트 URL은 onmicrosoft.de 도메인 이름을 기반으로 합니다. 아쉽게도 SharePoint Online 아키텍처의 작동 방식 때문에 팀 사이트의 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-267">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="a7340-268">**Onmicrosoft 도메인은 제거할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7340-268">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="a7340-269">Office 365에서는 구독을 위해 백그라운드에서 사용 되기 때문에이를 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-269">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="a7340-270">하지만 사용자 지정 도메인을 추가한 후에는 직접 도메인을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-270">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="a7340-271">도메인을 추가한 후에도 초기 onmicrosoft.de 도메인을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-271">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="a7340-272">여전히 전자 메일 및 기타 서비스에 대해 작동 하기 때문에 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-272">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="a7340-273">비영리 또는 학력 상태를 확인 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="a7340-273">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="a7340-274">[관리 센터](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) 에서 **설치** 를 선택 하 여 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-274">Select **Setup** in the [admin center](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) to start the wizard.</span></span> <span data-ttu-id="a7340-275">(먼저 Office 365에 로그인 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="a7340-275">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="a7340-276">학교 관리자가 되도록 하려면 Office 365에서 **관리자 권한으로 관리** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-276">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="a7340-277">도메인에 대 한 DNS 호스트 웹 사이트에 TXT DNS 레코드를 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-277">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="a7340-278">다음과 같은 이유 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-278">Why?</span></span> <span data-ttu-id="a7340-279">DNS 호스트에 로그인 하 고 도메인에 대 한 레코드를 추가 하 여 Office 365에서 도메인 이름을 소유 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-279">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="a7340-280">레코드를 추가한 후에는 Office 365 포털로 돌아가 Office 365에서 확인할 수 있도록 해당 포털을 추가 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-280">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="a7340-281">비영리이 있고 Office 365을 받으려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="a7340-281">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="a7340-282">[조직에서](https://www.microsoft.com/en-us/nonprofits/eligibility) 서비스를 확인 한 다음 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-282">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="a7340-283">학교에서 관리자 되는 것에 대해 자세히 알고 싶으십니까?</span><span class="sxs-lookup"><span data-stu-id="a7340-283">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="a7340-284">를 [참고](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)하세요.</span><span class="sxs-lookup"><span data-stu-id="a7340-284">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="a7340-285">사용자 지정 도메인의 몇 가지 전자 메일 주소만 사용 하 여 Office 365를 파일럿 할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a7340-285">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="a7340-286">다음과 같은 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-286">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="a7340-287">현재 전자 메일 공급자가 전자 메일 전달을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-287">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="a7340-288">Office 365에서 이러한 레코드를 관리 하는 것이 아니라 DNS 호스팅 공급자에서 Office 365 관련 DNS 레코드를 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-288">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="a7340-289">이에 대 한 자세한 내용은 자신만의 DNS 레코드를 관리 하려는 경우 Office 365에 도메인 추가를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7340-289">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="a7340-290">일부 Office 365 기능은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-290">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="a7340-291">사용자는 다른 전자 메일 공급자의 사용자에 대 한 약속 있음/없음 정보를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-291">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="a7340-292">관리자는 모든 사용자의 계정을 한 위치에서 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-292">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="a7340-293">사용자가 Office 365 스팸 필터링을 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-293">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="a7340-294">Office 365 파일럿을 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a7340-294">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="a7340-295">Microsoft 365 관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-295">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="a7340-296">회사 또는 학교 계정을 사용하여 Office 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-296">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="a7340-297">**설정** \> **도메인**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-297">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="a7340-298">사용 하려는 도메인을 소유 하 고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="a7340-298">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="a7340-299">**도메인** 페이지에서 **도메인 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-299">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="a7340-300">패널에서 도메인 (이 예에서는 cohowinery.com)을 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-300">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="a7340-301">도메인 **확인** 페이지에서 단계별 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-301">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="a7340-302">드롭다운 목록에서 DNS 호스팅 공급자를 선택 하 고 지침에 따라 도메인을 소유 하 고 있음을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-302">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="a7340-303">**확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-303">Select **Verify**.</span></span> <span data-ttu-id="a7340-304">DNS 변경 사항을 적용 하기 위해 몇 분에서 72 시간까지 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-304">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="a7340-305">확인이 성공 하면 DNS 레코드를 수정 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-305">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="a7340-306">Exchange Online에서 도메인을 공유로 표시</span><span class="sxs-lookup"><span data-stu-id="a7340-306">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="a7340-307">EAC ( **Exchange 관리 센터** )로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-307">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="a7340-308">**메일 흐름** 섹션에서 **허용 도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-308">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="a7340-309">수정 하려는 도메인을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-309">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="a7340-310">열려 있는 창에서 **내부 릴레이**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-310">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="a7340-311">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-311">Select **Save**.</span></span> <span data-ttu-id="a7340-312">이 설정을 적용 하려면 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-312">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="a7340-313">필요에 따라 기존 전자 메일 서버 차단 해제</span><span class="sxs-lookup"><span data-stu-id="a7340-313">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="a7340-314">Office 365에서는 스팸 보호를 위해 EOP (Exchange Online Protection)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-314">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="a7340-315">EOP에서 현재 메일 서버에 의해 전달 되는 대량의 스팸 볼륨이 감지 되 면 전달이 차단 될 수 있으며,이로 인해 착신 전환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-315">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="a7340-316">다른 전자 메일 공급자가 사용 하는 스팸 방지 기능이 확실 한 경우에는 해당 서버를 Office 365에서 허용 목록 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-316">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="a7340-317">그러나 이렇게 하면 원래 서버를 통해 수신 되는 모든 스팸 메일이 Office 365 사서함으로 전달 되 고, Office 365에서 스팸을 차단 하는 정도를 평가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-317">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="a7340-318">EAC (Exchange 관리 센터)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-318">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="a7340-319">EAC에서 **보호**를 선택 하 고 **연결 필터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-319">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="a7340-320">**IP 허용 목록**에서를 선택 **+** 하 고 현재 전자 메일 공급자 로부터 가져올 수 있는 메일 서버 IP 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-320">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="a7340-321">사용자 계정 만들기 및 기본 (회신) 주소 설정</span><span class="sxs-lookup"><span data-stu-id="a7340-321">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="a7340-322">Microsoft 365 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-322">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="a7340-323">왼쪽 탐색 모음에서 **사용자** \> **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-323">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="a7340-324">사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-324">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="a7340-325">각 계정에 대해 **+ (새로 만들기)** 를 선택 하 고 필요한 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-325">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="a7340-326">사용자의 전자 메일을 현재와 동일 하 게 유지 하려면 **사용자 이름** 필드가 사용자의 기존 전자 메일 주소와 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-326">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="a7340-327">사용자 이름 옆의 드롭다운 목록에서 사용자 지정 도메인 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-327">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="a7340-328">닫기 **만들기** \> \*\*\*\* 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-328">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="a7340-329">DNS 호스팅 공급자에서 DNS 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7340-329">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="a7340-330">DNS 호스팅 공급자의 웹 사이트에 로그인 하 고 dns [호스팅 공급자에서 Office 365 단계](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)에 해당 하는 Dns 레코드 만들기를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-330">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="a7340-331">**다음 예외를 확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a7340-331">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="a7340-332">새 MX 레코드를 만들거나 기존 MX 레코드를 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-332">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="a7340-333">이전 전자 메일 공급자에 대 한 SPF (보낸 사람 정책 프레임 워크) 레코드가 이미 있는 경우 Exchange Online에 대 한 새 SPF (TXT) 레코드를 만드는 대신 현재 TXT 레코드에 "include:"를 추가 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-333">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="a7340-334">예를 들어 "v = spf1 mx에는:adatum를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-334">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="a7340-335">SPF 레코드가 아직 없는 경우에는 Office 365에서 권장 하는 하나를 수정 하 여 현재 전자 메일 공급자에 대 한 도메인을 포함 하 고 spf.protection.outlook.com를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-335">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="a7340-336">이렇게 하면 두 전자 메일 시스템에서 보내는 메시지가 모두 승인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-336">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="a7340-337">현재 공급자에서 전자 메일 전달 설정</span><span class="sxs-lookup"><span data-stu-id="a7340-337">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="a7340-338">현재 전자 메일 공급자에서 사용자 전자 메일 계정에 대 한 착신 전환을 onmicrosoft.com 도메인으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-338">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="a7340-339">사용자 A의 사서함이 usera@yourcompany.onmicrosoft.com로 전달 되어야 함</span><span class="sxs-lookup"><span data-stu-id="a7340-339">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="a7340-340">사용자 B의 사서함이 userb@yourcompany.onmicrosoft.com로 전달 되어야 함</span><span class="sxs-lookup"><span data-stu-id="a7340-340">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="a7340-341">이 단계를 완료 하면 다음이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-341">When you complete this step:</span></span>
        
    5. <span data-ttu-id="a7340-342">Usera@yourcompany.com 및 userb@yourcompany.com에 게 전송 되는 모든 메일은 Office 365에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-342">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="a7340-343">참고:</span><span class="sxs-lookup"><span data-stu-id="a7340-343">Notes:</span></span>
        
        - <span data-ttu-id="a7340-344">착신 전환 설정에 대 한 정확한 단계는 현재 전자 메일 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7340-344">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="a7340-345">현재 전자 메일 공급자에 메시지 복사본을 보관할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-345">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="a7340-346">대부분의 공급자는 보낸 사람의 회신 주소를 그대로 두고 전자 메일을 전달 하 여 회신이 원래 보낸 사람에 게 이동 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-346">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="a7340-347">메일 흐름 테스트</span><span class="sxs-lookup"><span data-stu-id="a7340-347">Test mail flow</span></span>
    
    1. <span data-ttu-id="a7340-348">사용자 A의 자격 증명을 사용 하 여 Outlook Web App에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-348">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="a7340-349">다음 테스트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-349">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="a7340-350">로컬 Office 365 전자 메일을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-350">Test local Office 365 email.</span></span> <span data-ttu-id="a7340-351">예를 들어 사용자 B에 게 전자 메일을 보냅니다. 이 전자 메일을 즉시 배달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-351">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="a7340-352">이 시나리오에서는 Office 365에서 사서함을 로컬으로 인식 하기 때문에 메시지가 원래 서버에서 사용자 B의 사서함으로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-352">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="a7340-353">다른 전자 메일 시스템에 있는 사람에 대 한 전자 메일을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-353">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="a7340-354">예를 들어 사용자 C에 게 전자 메일을 보냅니다. 이 전자 메일은 원래 메일 서버에서 사용자 C의 사서함으로 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-354">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="a7340-355">외부 계정에서 또는 다른 전자 메일 시스템의 직원 전자 메일 계정에서 다른 전자 메일 시스템에 대 한 전달이 제대로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-355">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="a7340-356">예를 들어 사용자 C의 origninal 서버 계정 또는 Hotmail 계정에서 사용자 A에 게 전자 메일을 보내 사용자 A의 Office 365 사서함에 도착 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-356">For example, from User C's origninal server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="a7340-357">사서함 콘텐츠 이동</span><span class="sxs-lookup"><span data-stu-id="a7340-357">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="a7340-358">사용자는 두 명만 이동할 수 있으며, User A와 User B가 Outlook을 이미 사용 하 고 있으므로 전자 메일을 이동 하려면 이전을 엽니다. PST 파일을 outlook 데이터 파일 (.pst)에서 Outlook 항목 가져오기에 표시 된 대로 새 Outlook 프로필의 메시지, 일정 항목, 연락처 등을 복사 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-358">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="a7340-359">Office 365 사서함의 적절 한 위치에 구성 된 항목은 모든 장치에서 어디에 나 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-359">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="a7340-360">더 많은 사서함이 포함 되거나 직원이 아직 Outlook을 사용 하 고 있지 않은 경우 Exchange 관리 센터에서 사용할 수 있는 마이그레이션 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7340-360">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="a7340-361">시작 하려면 Exchange 관리 센터로 이동 하 여 IMAP 서버에서 Exchange Online 사서함으로 전자 메일 마이그레이션의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a7340-361">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
