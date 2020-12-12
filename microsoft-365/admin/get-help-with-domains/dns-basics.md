---
title: DNS 기본 사항
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: 도메인 관리에 도움이 되는 도메인 및 관련 DNS 레코드에 대해 알아봅니다.
ms.openlocfilehash: 1f5d49eb588a7c4245751360fa3309bf20496512
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658534"
---
# <a name="dns-basics"></a><span data-ttu-id="a3fd7-103">DNS 기본 사항</span><span class="sxs-lookup"><span data-stu-id="a3fd7-103">DNS basics</span></span>

 <span data-ttu-id="a3fd7-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="a3fd7-105">도메인 이름(예: contoso.com)은 전 세계 도메인 등록 기관 및 데이터베이스 시스템을 사용하여 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-105">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases.</span></span> <span data-ttu-id="a3fd7-106">DNS(Domain Name System)는 사람이 읽을 수 있는 컴퓨터 호스트 이름과 네트워킹 장비에서 사용하는 IP 주소 간의 매핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-106">The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment.</span></span> <span data-ttu-id="a3fd7-107">DNS 및 도메인 등록 기관 기본 사항을 이해하면 도메인을 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-107">An understanding of DNS and domain registrar basics can help you manage domains.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="a3fd7-108">도메인 이름(예: contoso.com)은 전 세계 도메인 등록 기관 및 데이터베이스 시스템을 사용하여 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-108">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases.</span></span> <span data-ttu-id="a3fd7-109">DNS(Domain Name System)는 사람이 읽을 수 있는 컴퓨터 호스트 이름과 네트워킹 장비에서 사용하는 IP 주소 간의 매핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-109">The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment.</span></span> <span data-ttu-id="a3fd7-110">DNS 및 도메인 등록 기관 기본 사항을 이해하면 도메인을 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-110">An understanding of DNS and domain registrar basics can help you manage domains.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="a3fd7-111">도메인 이름(예: contoso.com)은 전 세계 도메인 등록 기관 및 데이터베이스 시스템을 사용하여 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-111">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases.</span></span> <span data-ttu-id="a3fd7-112">DNS(Domain Name System)는 사람이 읽을 수 있는 컴퓨터 호스트 이름과 네트워킹 장비에서 사용하는 IP 주소 간의 매핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-112">The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment.</span></span> <span data-ttu-id="a3fd7-113">DNS 및 도메인 등록 기관 기본 사항을 이해하면 관리자가 도메인을 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-113">An understanding of DNS and domain registrar basics will help admins manage domains.</span></span>
  
::: moniker-end

## <a name="what-are-domain-names"></a><span data-ttu-id="a3fd7-114">도메인 이름이란?</span><span class="sxs-lookup"><span data-stu-id="a3fd7-114">What are domain names?</span></span>

<span data-ttu-id="a3fd7-115">도메인 이름은 URL 및 전자 메일 주소에서 사용되며 여러 수준으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-115">Domain names are used in URLs and email addresses, and they have different levels.</span></span> <span data-ttu-id="a3fd7-116">예를 들어, mail.contoso.com에는 다음과 같은 세 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-116">For example, mail.contoso.com is a domain name with the following three levels:</span></span>
  
- <span data-ttu-id="a3fd7-117">**.com** 은 최상위 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-117">**.com** is the top-level domain</span></span> 
    
- <span data-ttu-id="a3fd7-118">**contoso** 는 두 번째 수준 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-118">**contoso** is the second-level domain</span></span> 
    
- <span data-ttu-id="a3fd7-119">**mail** 은 세 번째 수준 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-119">**mail** is the third-level domain</span></span> 
    
<span data-ttu-id="a3fd7-120">세 번째 수준 도메인을 사용하는 이유는 무엇일까요?</span><span class="sxs-lookup"><span data-stu-id="a3fd7-120">Why use a third-level domain?</span></span> <span data-ttu-id="a3fd7-121">사용자가 마케팅 또는 블로그에 다른 도메인 이름을 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-121">You might want to have different domain names for marketing or a blog.</span></span> <span data-ttu-id="a3fd7-122">예를 들어 blog.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-122">For example, blog.contoso.com.</span></span> <span data-ttu-id="a3fd7-123">일반적으로 Microsoft에서 사용하도록 contoso.com과 같은 두 번째 수준 도메인을 추가하지만, 원한다면 세 번째 수준 도메인을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-123">You typically add a second-level domain, like contoso.com, to use with Microsoft but you can also use third-level domains if you like.</span></span>
  
<span data-ttu-id="a3fd7-124">각 제품 유형에 따라 도메인에서 수행할 수 있는 기능에 대한 자세한 내용은 [Microsoft 365 및 Office 365 플랫폼 서비스 설명](https://go.microsoft.com/fwlink/?LinkId=402693)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-124">Learn more about what you can do with domains for each type of offering in the [Microsoft 365 and Office 365 platform service description](https://go.microsoft.com/fwlink/?LinkId=402693).</span></span>
  
## <a name="understand-dns-record-types"></a><span data-ttu-id="a3fd7-125">DNS 레코드 종류 이해</span><span class="sxs-lookup"><span data-stu-id="a3fd7-125">Understand DNS record types</span></span>

<span data-ttu-id="a3fd7-126">도메인의 DNS 호스트에 저장된 DNS 레코드는 도메인의 트래픽을 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-126">DNS records stored at a DNS host for your domain are used to direct traffic for your domain.</span></span> <span data-ttu-id="a3fd7-127">다음 표에서는 자주 사용하는 DNS 레코드와 이러한 레코드를 사용하는 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-127">The following table describes frequently used DNS records and how they're used.</span></span>
  
|<span data-ttu-id="a3fd7-128">**NS(이름 서버) 레코드**</span><span class="sxs-lookup"><span data-stu-id="a3fd7-128">**NS (nameserver) record**</span></span>|<span data-ttu-id="a3fd7-129">**특정 도메인에 대해 "신뢰할 수 있는 이름 서버"를 식별합니다. 도메인의 이름 서버를 변경하면 DNS 레코드가 관리되는 위치 및 DNS 시스템이 메일 서버 등에 관한 정보를 찾는 위치가 변경됩니다. Microsoft에는 자체 이름 서버가 있지만, 도메인에 이미 설정되어 있는 이름 서버를 계속 사용할 수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a3fd7-129">**Identifies the name servers that are the "authoritative nameservers" for a domain. When you change the nameservers for your domain, you change where your DNS records are managed and where the DNS system looks for information about mail servers and so on. Microsoft has its own nameservers, or you may decide to keep using the nameservers that are already set up with your domain.**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3fd7-130">레코드(주소 레코드)</span><span class="sxs-lookup"><span data-stu-id="a3fd7-130">A record (address record)</span></span>  <br/> |<span data-ttu-id="a3fd7-131">IP 주소와 도메인 이름을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-131">Associates a domain name with an IP address.</span></span>  <br/> |
|<span data-ttu-id="a3fd7-132">CNAME(별칭 또는 정식 이름) 레코드</span><span class="sxs-lookup"><span data-stu-id="a3fd7-132">CNAME (alias or canonical) record</span></span>  <br/> |<span data-ttu-id="a3fd7-133">DNS 시스템에서 한 도메인을 다른 도메인으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-133">Redirects one domain to another in the DNS system.</span></span> <span data-ttu-id="a3fd7-134">이름 서버가 도메인을 조회하여 CNAME 레코드가 있다는 것을 발견하면 첫 번째 도메인 이름을 CNAME으로 대체하고 새 이름을 조회합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-134">When a name server looks up a domain and finds that it has a CNAME record, the server replaces the first domain name with the CNAME, and then looks up the new name.</span></span>  <br/> |
|<span data-ttu-id="a3fd7-135">MX(메일 교환기) 레코드</span><span class="sxs-lookup"><span data-stu-id="a3fd7-135">MX (mail exchanger) record</span></span>  <br/> |<span data-ttu-id="a3fd7-136">전자 메일을 보낼 위치를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-136">Points to where your email should be sent.</span></span> <span data-ttu-id="a3fd7-137">여기에는 우선 순위 필드도 있어 우선 순위대로 여러 서버에 메일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-137">It also has a priority field so that you can send mail to different servers in a priority order.</span></span>  <br/> |
|<span data-ttu-id="a3fd7-138">SPF(Sender Policy Framework) 레코드</span><span class="sxs-lookup"><span data-stu-id="a3fd7-138">SPF (sender policy framework) record</span></span>  <br/> |<span data-ttu-id="a3fd7-139">전자 메일 스푸핑 및 피싱을 방지하는 데 도움이 되는 TXT 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-139">A TXT record that helps prevent email spoofing and phishing.</span></span>  <br/> |
|<span data-ttu-id="a3fd7-140">SRV(서비스) 레코드</span><span class="sxs-lookup"><span data-stu-id="a3fd7-140">SRV (service) record</span></span>  <br/> |<span data-ttu-id="a3fd7-141">비즈니스용 Skype Online 및 Exchange Online에서 Microsoft 서비스 간의 정보 흐름을 조정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-141">Used by Skype for Business Online and Exchange Online to coordinate the flow of information between Microsoft services.</span></span> <span data-ttu-id="a3fd7-142">예를 들어 SRV 레코드는 Outlook Web App에서 현재 상태를 확인하고 비즈니스용 Skype Online, Skype 또는 다른 회사의 사용자와 기타 인스턴트 메시징 도구를 사용하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-142">For example, the SRV records are required to see presence in Outlook Web App, and to use Skype for Business Online, Skype, or other instant messaging tools with people in other companies.</span></span>  <br/> |
|<span data-ttu-id="a3fd7-143">TTL(time-to-live)</span><span class="sxs-lookup"><span data-stu-id="a3fd7-143">TTL (time-to-live)</span></span>  <br/> |<span data-ttu-id="a3fd7-144">이름 서버가 업데이트된 버전을 찾기 전에 서버에서 DNS 레코드가 유지되는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-144">The amount of time that a nameserver keeps a DNS record before the server looks for an updated version.</span></span>  <br/> |
   
## <a name="how-does-dns-work"></a><span data-ttu-id="a3fd7-145">DNS의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="a3fd7-145">How does DNS work?</span></span>

<span data-ttu-id="a3fd7-146">Microsoft 365와 같은 클라우드 서비스를 사용하여 도메인을 설정하는 과정에는 도메인에 대한 [DNS 레코드](dns-basics.md)를 변경하거나 추가하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-146">Part of setting up your domain with a cloud service like Microsoft 365 includes changing or adding [DNS records](dns-basics.md) for the domain.</span></span> <span data-ttu-id="a3fd7-147">인터넷이 DNS(Domain Name System) 및 도메인 이름과 작동하는 방식 때문에, 전자 메일 및 웹 사이트 등 항목을 보내거나 찾을 위치를 파악하기 위해 이러한 변경 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-147">These changes are required because of how the Internet works with the DNS, Domain Name System, and domain names, to know where to send or find things, like email and websites.</span></span> 
  
<span data-ttu-id="a3fd7-148">인터넷은 DNS(Domain Name System)를 사용하도록 설정되어 있기 때문에, 실제로는 IP(인터넷 프로토콜) 주소라고 하는 외우기 힘든 숫자로 된 특정 인터넷 위치를 사용자는 contoso.com과 같은 친숙한 이름을 사용하여 찾을 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-148">The Internet is set up to use DNS, or Domain Name System, which lets us use familiar names, like contoso.com, to locate specific Internet locations that are actually, under the covers, labeled with hard-to-remember numbers called IP (Internet Protocol) addresses.</span></span> <span data-ttu-id="a3fd7-149">IP 주소는 70.42.241.42와 같은 형식입니다. 따라서 도메인 이름을 사용하여 전자 메일 호스트 및 웹 사이트 등의 위치를 식별하는 것이 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-149">IP addresses look something like 70.42.241.42, so you can see it's much easier to use a domain name to identify locations like email hosts and websites.</span></span>
  
<span data-ttu-id="a3fd7-150">즉, DNS 레코드는 전자 메일을 보낼 위치(예: joe@contoso.com) 또는 도메인 이름을 사용하는 웹 사이트를 찾을 위치(예: www.contoso.com)를 인터넷에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-150">So that's the short answer: DNS records tell the Internet where to send email (like joe@contoso.com) or find websites (like www.contoso.com) that use your domain name.</span></span> <span data-ttu-id="a3fd7-151">올바른 정보를 도메인의 올바른 DNS 레코드에 입력하면 DNS 시스템이 모든 것을 정확하게 라우팅하므로 사용자의 전자 메일이 다른 곳이 아닌 Microsoft 365에 도착합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-151">When you put the right information into the right DNS records for your domain, the DNS system routes everything correctly so your email, for example, arrives in Microsoft 365 instead of somewhere else.</span></span>
  
<span data-ttu-id="a3fd7-152">도메인의 DNS 레코드는 다른 방법으로도 유용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="a3fd7-152">A domain's DNS records can be helpful in other ways, too.</span></span> <span data-ttu-id="a3fd7-153">예를 들어 Exchange는 Outlook이 올바른 Exchange 서버에 대한 연결을 자동으로 설정할 수 있게 하는 DNS 레코드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-153">For example, Exchange checks a DNS record that lets Outlook automatically set up a connection to the right Exchange server.</span></span>
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a><span data-ttu-id="a3fd7-154">DNS 레코드를 통해 인터넷에서 올바른 위치에 전자 메일 전송</span><span class="sxs-lookup"><span data-stu-id="a3fd7-154">DNS records help the Internet send email to the right place</span></span>

<span data-ttu-id="a3fd7-155">위에서 설명했듯이, DNS는 기본적으로 트래픽을 인터넷으로 전달하여 외우기 어려운 IP 주소에 친숙한 도메인 이름을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-155">As you read above, DNS essentially directs traffic around the Internet, mapping friendly domain names to those hard-to-remember IP addresses.</span></span> <span data-ttu-id="a3fd7-156">MX 레코드라고 하는 DNS 레코드는 특히 전자 메일을 올바른 호스트에 보내는 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-156">One DNS record, called the MX record, is specifically for sending email to the right host.</span></span>
  
<span data-ttu-id="a3fd7-157">DNS 레코드는 도메인에 대한 정보의 데이터베이스와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-157">DNS records are like a database of information about your domain.</span></span> <span data-ttu-id="a3fd7-158">레코드 및 해당 값은 영역 파일이라는 항목에 보관되며 여기에는 도메인에 대한 각 레코드 목록과 해당 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-158">The records and their values are kept in something called a zone file, which includes a list of each record for your domain and what its value is.</span></span> <span data-ttu-id="a3fd7-159">도메인 등록 기관과 기타 DNS 호스팅 회사는 사용자의 도메인 영역 파일에서 레코드를 편집할 수 있도록 웹 사이트에 UI를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-159">Domain registrars and other DNS hosting companies provide a UI on their websites so you can edit the records in your domain's zone file.</span></span> <span data-ttu-id="a3fd7-160">이는 도메인에 대한 MX 레코드를 업데이트하여 전자 메일 메시지가 Microsoft 365로 전송되도록 하는 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-160">And that's where you update the MX record for your domain, to send email messages to Microsoft 365.</span></span>
  
 <span data-ttu-id="a3fd7-161">*다음 단계에서 도메인의 MX 레코드를 업데이트하여 전자 메일을 Microsoft 365로 변경하면 해당 도메인으로 전송된 모든 전자 메일이 Microsoft 365로 배달되기 시작합니다.*</span><span class="sxs-lookup"><span data-stu-id="a3fd7-161">*When you change your email to Microsoft 365, by updating your domain's MX record in the next step, ALL email sent to that domain will start coming to Microsoft 365.*</span></span>  <span data-ttu-id="a3fd7-162">다른 사용자가 해당 도메인을 전자 메일에 사용하는 경우 해당 사용자 각각에 대해 Microsoft 365 사서함을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-162">If other people use your domain for email, you must set up Microsoft 365 mailboxes for each of those people.</span></span> 
  
<span data-ttu-id="a3fd7-163">복잡하게 보이나요?</span><span class="sxs-lookup"><span data-stu-id="a3fd7-163">Sound complicated?</span></span> <span data-ttu-id="a3fd7-164">그럴 수도 있지만 Microsoft 도메인 설정의 단계별로 자세히 안내됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-164">Well, it can be, but we walk you through each step in the Microsoft domain setup.</span></span>
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a><span data-ttu-id="a3fd7-165">DNS는 또한 인터넷에 웹 사이트를 찾을 위치를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-165">DNS tells the Internet where to look for websites too</span></span>

<span data-ttu-id="a3fd7-166">예를 들어 www.contoso.com과 같이 웹 사이트 주소를 입력하면 인터넷은 먼저 DNS 서버 중 하나에서 contoso.com에 대한 NS(이름 서버) 레코드를 사용하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-166">When you type in a website address, for example, www.contoso.com, the Internet first checks with one of the DNS servers for something called a name server (NS) record for (in this case) contoso.com.</span></span> <span data-ttu-id="a3fd7-167">NS 레코드는 해당 도메인에 대한 다른 모든 DNS 레코드 값을 포함하는 영역 파일을 찾을 위치를 인터넷에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-167">The NS record tells the Internet where it should look for the zone file that has all the other DNS record values for that domain.</span></span> <span data-ttu-id="a3fd7-168">DNS 서버는 많은 수가 있으며, 이들은 모두 서로 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-168">There are lots of DNS servers, all connected to each other.</span></span> <span data-ttu-id="a3fd7-169">서버들은 서로 협력하여 고유하게 등록된 모든 도메인 이름과 도메인의 영역 파일이 있는 위치를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-169">The servers work together to keep track of all registered domain names, which have to be unique, and where the domain's zone files are.</span></span>
  
::: moniker range="o365-worldwide"

<span data-ttu-id="a3fd7-170">Contoso.com의 NS 레코드에 "godaddy.com"이 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-170">Let's say that the NS record for contoso.com says "godaddy.com."</span></span> <span data-ttu-id="a3fd7-171">이제 인터넷은 contoso.com에 대한 다른 모든 DNS 레코드를 나열하는 영역 파일을 찾을 위치가 GoDaddy.com이라는 것을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-171">Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com.</span></span> <span data-ttu-id="a3fd7-172">이러한 DNS 레코드에는 contoso.com 및 기타 레코드에 대한 전자 메일을 보낼 위치를 나타내는 MX 레코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-172">Those DNS records include the MX record that says where to send emails for contoso.com and other records.</span></span> <span data-ttu-id="a3fd7-173">MX 레코드에 "Microsoft 365로 전자 메일 보내기"를 설정(기술적 용어로)하는 값이 있는 경우에는 contoso.com 전자 메일 주소(예: joe@contoso.com)로 전송된 모든 전자 메일 메시지가 Microsoft 365로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-173">If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent.</span></span> <span data-ttu-id="a3fd7-174">그런 다음 해당 위치에 "joe" 라는 사서함이 있으면 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-174">Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="a3fd7-175">Contoso.com의 NS 레코드에 "godaddy.com"이 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-175">Let's say that the NS record for contoso.com says "godaddy.com."</span></span> <span data-ttu-id="a3fd7-176">이제 인터넷은 contoso.com에 대한 다른 모든 DNS 레코드를 나열하는 영역 파일을 찾을 위치가 GoDaddy.com이라는 것을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-176">Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com.</span></span> <span data-ttu-id="a3fd7-177">이러한 DNS 레코드에는 contoso.com 및 기타 레코드에 대한 전자 메일을 보낼 위치를 나타내는 MX 레코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-177">Those DNS records include the MX record that says where to send emails for contoso.com and other records.</span></span> <span data-ttu-id="a3fd7-178">MX 레코드에 "Microsoft 365로 전자 메일 보내기"를 설정(기술적 용어로)하는 값이 있는 경우에는 contoso.com 전자 메일 주소(예: joe@contoso.com)로 전송된 모든 전자 메일 메시지가 Microsoft 365로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-178">If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent.</span></span> <span data-ttu-id="a3fd7-179">그런 다음 해당 위치에 "joe" 라는 사서함이 있으면 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-179">Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="a3fd7-180">Contoso.com의 NS 레코드에 "hichina.com."이 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-180">Let's say that the NS record for contoso.com says "hichina.com."</span></span> <span data-ttu-id="a3fd7-181">이제 인터넷은 contoso.com에 대한 다른 모든 DNS 레코드를 나열하는 영역 파일을 찾을 위치가 hichina.com이라는 것을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-181">Now the Internet knows that hichina.com is where to look for the zone file listing all the other DNS records for contoso.com.</span></span> <span data-ttu-id="a3fd7-182">이러한 DNS 레코드에는 contoso.com 및 기타 레코드에 대한 전자 메일을 보낼 위치를 나타내는 MX 레코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-182">Those DNS records include the MX record that says where to send emails for contoso.com and other records.</span></span> <span data-ttu-id="a3fd7-183">MX 레코드에 "Microsoft 365로 전자 메일 보내기"를 설정(기술적 용어로)하는 값이 있는 경우에는 contoso.com 전자 메일 주소(예: joe@contoso.com)로 전송된 모든 전자 메일 메시지가 Microsoft 365로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-183">If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent.</span></span> <span data-ttu-id="a3fd7-184">그런 다음 해당 위치에 "joe" 라는 사서함이 있으면 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-184">Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

<span data-ttu-id="a3fd7-185">Microsoft 365에서 이러한 모든 설정이 제대로 작동하기 위해 입력해야 하는 실제 값이 도메인을 설정할 때 도메인 설정 단계에서 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-185">The actual values that you must enter for all of this to work with Microsoft 365 are listed for you when you're setting up your domain, in the domain setup steps.</span></span> <span data-ttu-id="a3fd7-186">수동으로 설정하는 경우 값을 복사하여 DNS 호스트(이는 도메인 등록 기관이 될 수 있지만, 꼭 그럴 필요는 없습니다)의 올바른 DNS 레코드(MX 레코드, CNAME 레코드 등)에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-186">If you're doing the set up manually, you copy and paste the values into the correct DNS records (MX record, CNAME records, and so on) at your DNS host, which might be your domain registrar but doesn't have to be.</span></span>
  
::: moniker range="o365-worldwide"

<span data-ttu-id="a3fd7-187">도메인 영역 파일이 도메인 등록 기관 이외의 다른 곳에 있을 수 있는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="a3fd7-187">Why might your domain's zone file be somewhere besides at your domain registrar?</span></span> <span data-ttu-id="a3fd7-188">GoDaddy와 같은 도메인 등록 기관에 도메인 이름을 등록할 수 있지만, DNS 레코드는 별도의 DNS 호스팅 회사나 웹 호스팅 회사 등 다른 곳에서 관리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-188">Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company.</span></span> <span data-ttu-id="a3fd7-189">도메인의 NS 레코드는 해당 정보를 저장하므로 모든 DNS 서버가 검색할 위치를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-189">The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="a3fd7-190">도메인 영역 파일이 도메인 등록 기관 이외의 다른 곳에 있을 수 있는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="a3fd7-190">Why might your domain's zone file be somewhere besides at your domain registrar?</span></span> <span data-ttu-id="a3fd7-191">GoDaddy와 같은 도메인 등록 기관에 도메인 이름을 등록할 수 있지만, DNS 레코드는 별도의 DNS 호스팅 회사나 웹 호스팅 회사 등 다른 곳에서 관리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-191">Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company.</span></span> <span data-ttu-id="a3fd7-192">도메인의 NS 레코드는 해당 정보를 저장하므로 모든 DNS 서버가 검색할 위치를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-192">The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="a3fd7-193">도메인 영역 파일이 도메인 등록 기관 이외의 다른 곳에 있을 수 있는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="a3fd7-193">Why might your domain's zone file be somewhere besides at your domain registrar?</span></span> <span data-ttu-id="a3fd7-194">HiChina와 같은 도메인 등록 기관에 도메인 이름을 등록할 수 있지만, DNS 레코드는 별도의 DNS 호스팅 회사나 웹 호스팅 회사 등 다른 곳에서 관리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-194">Well, you might register your domain name at a domain registrar like HiChina, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company.</span></span> <span data-ttu-id="a3fd7-195">도메인의 NS 레코드는 해당 정보를 저장하므로 모든 DNS 서버가 검색할 위치를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-195">The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a><span data-ttu-id="a3fd7-196">Microsoft 365에서 도메인을 추가해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="a3fd7-196">Why add a domain in Microsoft 365?</span></span>


<span data-ttu-id="a3fd7-197">사용자 지정 도메인(예: fourthcoffee.com)을 Microsoft 365에 추가하면 서비스에서 더 짧고 친숙한 전자 메일 주소와 사용자 ID를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-197">Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service.</span></span> <span data-ttu-id="a3fd7-198">Microsoft 365 계정에 가입할 때 [사용할 도메인이 제공](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)되지만, 여기에는 "onmicrosoft.com"이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-198">You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com."</span></span> <span data-ttu-id="a3fd7-199">많은 사용자가 전자 메일에 Microsoft 365를 사용하려는 경우 조직 또는 비즈니스 도메인을 추가하는 것을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-199">Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a3fd7-200">Outlook 또는 Word 등의 Microsoft 앱을 다운로드하고 사용하려는 경우에는 도메인을 추가할 필요가 없습니다. [PC 또는 Mac에 Office를 설치](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-200">If you just want to download and use Microsoft apps, like Outlook or Word, you don't need to add a domain: [Install Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> 
  
<span data-ttu-id="a3fd7-201">전자 메일, 공개 웹 사이트 및 메신저 주소에 Microsoft 365의 사용자 도메인 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-201">You can use your domain name in Microsoft 365 with your email, public website, and instant messaging address.</span></span>
  
- <span data-ttu-id="a3fd7-202">**전자 메일:** 도메인 이름을 사용하면 전자 메일을 사용자 지정할 수 있으므로 계정과 함께 제공되는 [초기 onmicrosoft.com 전자 메일 주소](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)보다 더 짧고 기억하기 쉬운 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-202">**Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account.</span></span> <span data-ttu-id="a3fd7-203">따라서 전자 메일 주소(Microsoft 365에 로그인하는 데 사용하는 회사 계정으로도 사용됨)가 joe@contoso.onmicrosoft.com 대신 joe@contoso.com으로 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-203">So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com.</span></span> 
    
- <span data-ttu-id="a3fd7-204">**웹 사이트:** Microsoft 365 구독에 SharePoint Online 공개 웹 사이트(더 이상 구입할 수 없음)가 포함된 경우 공개 웹 사이트에는 contoso-public.sharepoint.com과 같은 초기 주소가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-204">**Website:** If you have an Microsoft 365 subscription that includes a SharePoint Online Public Website (no longer available for purchase), your public website comes with an initial address like this: contoso-public.sharepoint.com.</span></span> <span data-ttu-id="a3fd7-205">비즈니스를 위한 웹 사이트를 설정한 경우 www.contoso.com과 같이 사용자 지정 도메인 이름을 사용하여 웹 사이트 주소의 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-205">If you set up your website for your business, you can use a custom domain name to rename the website address to something like www.contoso.com.</span></span> 
    
- <span data-ttu-id="a3fd7-206">**인스턴트 메시징:** 도메인 이름을 사용하도록 비즈니스용 Skype Online 주소를 사용자 지정할 수도 있으므로, 조직의 사용자들이 더 짧고 기억하기 쉬운 주소(예: joe@contoso.com)를 사용하여 비즈니스용 Skype Online에서 서로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-206">**Instant messaging:** Your Skype for Business Online address can also be customized to use your domain name, so people in your organization can connect with each other on Skype for Business Online by using a shorter, easier-to-remember address (like joe@contoso.com).</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a><span data-ttu-id="a3fd7-207">Microsoft 365에서 도메인을 추가해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="a3fd7-207">Why add a domain in Microsoft 365?</span></span>


<span data-ttu-id="a3fd7-208">사용자 지정 도메인(예: fourthcoffee.com)을 Microsoft 365에 추가하면 서비스에서 더 짧고 친숙한 전자 메일 주소와 사용자 ID를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-208">Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service.</span></span> <span data-ttu-id="a3fd7-209">Microsoft 365 계정에 가입할 때 [사용할 도메인이 제공](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)되지만, 여기에는 "onmicrosoft.com"이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-209">You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com."</span></span> <span data-ttu-id="a3fd7-210">많은 사용자가 전자 메일에 Microsoft 365를 사용하려는 경우 조직 또는 비즈니스 도메인을 추가하는 것을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-210">Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a3fd7-211">Outlook 또는 Word 등의 Microsoft 365 앱만을 다운로드하고 사용하려는 경우에는 도메인을 추가할 필요가 없습니다. [PC 또는 Mac에 Office를 설치](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-211">If you just want to download and use Microsoft 365 apps, like Outlook or Word, you don't need to add a domain: [Install Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> 
  
<span data-ttu-id="a3fd7-212">전자 메일, 공개 웹 사이트 및 메신저 주소에 Microsoft 365의 사용자 도메인 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-212">You can use your domain name in Microsoft 365 with your email, public website, and instant messaging address.</span></span>
  
- <span data-ttu-id="a3fd7-213">**전자 메일:** 도메인 이름을 사용하면 전자 메일을 사용자 지정할 수 있으므로 계정과 함께 제공되는 [초기 onmicrosoft.com 전자 메일 주소](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)보다 더 짧고 기억하기 쉬운 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-213">**Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account.</span></span> <span data-ttu-id="a3fd7-214">따라서 전자 메일 주소(Microsoft 365에 로그인하는 데 사용하는 회사 계정으로도 사용됨)가 joe@contoso.onmicrosoft.com 대신 joe@contoso.com으로 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-214">So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com.</span></span> 
    
- <span data-ttu-id="a3fd7-215">**웹 사이트:** 구독에 SharePoint Online 공개 웹 사이트(더 이상 구입할 수 없음)가 포함된 경우 공개 웹 사이트에는 contoso-public.sharepoint.com과 같은 초기 주소가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-215">**Website:** If you have a subscription that includes a SharePoint Online Public Website (no longer available for purchase), your public website comes with an initial address like this: contoso-public.sharepoint.com.</span></span> <span data-ttu-id="a3fd7-216">비즈니스를 위한 웹 사이트를 설정한 경우 www.contoso.com과 같이 사용자 지정 도메인 이름을 사용하여 웹 사이트 주소의 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-216">If you set up your website for your business, you can use a custom domain name to rename the website address to something like www.contoso.com.</span></span> 
    
- <span data-ttu-id="a3fd7-217">**인스턴트 메시징:** 도메인 이름을 사용하도록 비즈니스용 Skype Online 주소를 사용자 지정할 수도 있으므로, 조직의 사용자들이 더 짧고 기억하기 쉬운 주소(예: joe@contoso.com)를 사용하여 비즈니스용 Skype Online에서 서로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-217">**Instant messaging:** Your Skype for Business Online address can also be customized to use your domain name, so people in your organization can connect with each other on Skype for Business Online by using a shorter, easier-to-remember address (like joe@contoso.com).</span></span> 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a><span data-ttu-id="a3fd7-218">Microsoft 365에 필요한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="a3fd7-218">The DNS records required for Microsoft 365</span></span>

<span data-ttu-id="a3fd7-219">Microsoft 365에서 도메인이 작동하려면 많은 DNS 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-219">There are a number of DNS records required for Microsoft 365 to work with your domain.</span></span> <span data-ttu-id="a3fd7-220">Microsoft 365로 전자 메일이 전송되도록 도메인의 MX 레코드를 설정하는 것 외에, Outlook을 올바른 Exchange Server에 자동으로 연결하고, 메신저를 설정하고, 스팸 메일을 방지하는 등의 작업에 유용한 레코드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-220">In addition to setting up your domain's MX record so email will be sent to Microsoft 365, there are records to help with tasks like making sure Outlook can automatically connect to the right Exchange server, setting up instant messaging, and helping to prevent spam email.</span></span>
  
<span data-ttu-id="a3fd7-221">도메인을 설정하기 위한 [값 목록을 찾을](information-for-dns-records.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-221">You can [find a list of values](information-for-dns-records.md) to set up your domain.</span></span> <span data-ttu-id="a3fd7-222">Microsoft 365 관리 센터에 바로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-222">They're included right in the Microsoft 365 admin center.</span></span> 
  
<span data-ttu-id="a3fd7-223">또는 배포를 계획하고 있는 경우 Microsoft 365에 필요한 모든 DNS 레코드, 해당 기능, 예시 값 목록을 검토해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-223">Or, if you're planning a deployment, you may want to review a list of all the DNS records required for Microsoft 365, what their function is, and example values.</span></span> <span data-ttu-id="a3fd7-224">[Microsoft 365에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-224">Check out [External Domain Name System records for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span>
  
## <a name="how-can-i-learn-more"></a><span data-ttu-id="a3fd7-225">자세한 내용을 알고 싶은 경우</span><span class="sxs-lookup"><span data-stu-id="a3fd7-225">How can I learn more?</span></span>

<span data-ttu-id="a3fd7-226">다음 중 하나를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-226">Check out one of the following:</span></span> 
  
- <span data-ttu-id="a3fd7-227">도메인이 어디에 등록되어 있는지 잘 모르시나요?</span><span class="sxs-lookup"><span data-stu-id="a3fd7-227">Not sure where your domain is registered?</span></span> [<span data-ttu-id="a3fd7-228">도메인 등록 기관 찾기 도움말을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-228">Get help finding your domain registrar.</span></span>](find-your-domain-registrar.md)
- <span data-ttu-id="a3fd7-229">Microsoft 365에서 도메인을 사용하기 전에 먼저 [마법사 단계를 완료해야 하는 이유](../setup/add-domain.md)를 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-229">Find out [why you have to complete the wizard steps](../setup/add-domain.md) before you can use your domain with Microsoft 365.</span></span>
