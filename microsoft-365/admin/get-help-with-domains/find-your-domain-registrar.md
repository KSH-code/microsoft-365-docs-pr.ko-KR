---
title: Office 365의 도메인 등록 기관 찾기
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: InterNIC 검색을 사용하여 도메인 등록 기관 및 DNS 호스팅 공급자를 찾는 방법에 대해 알아보세요.
ms.openlocfilehash: 058eb4468e073b6929fbc763b3d9bdb189063213
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255134"
---
# <a name="find-your-domain-registrar-for-office-365"></a><span data-ttu-id="cf462-103">Office 365의 도메인 등록 기관 찾기</span><span class="sxs-lookup"><span data-stu-id="cf462-103">Find your domain registrar for Office 365</span></span>

 <span data-ttu-id="cf462-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf462-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="cf462-105">도메인 등록 기관</span><span class="sxs-lookup"><span data-stu-id="cf462-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="cf462-106">도메인 이름 등록 기관 찾기</span><span class="sxs-lookup"><span data-stu-id="cf462-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="cf462-107">*.COM*, *.NET*, and *.EDU*로 끝나는 도메인만이 이 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="cf462-108">[InterNIC 검색 페이지](https://go.microsoft.com/fwlink/p/?LinkId=402770)의 **Whois Search(Whois 검색)** 상자에 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="cf462-109">예: *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="cf462-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="cf462-110">**Domain(도메인)** 옵션을 선택하고 **Submit(제출)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="cf462-111">**Whois Search Results(Whois 검색 결과)** 페이지에서 **Registrar(등록 기관)** 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="cf462-112">이 항목에는 도메인에 등록 기관 서비스를 제공하는 조직이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="cf462-113">DNS 호스팅 공급자</span><span class="sxs-lookup"><span data-stu-id="cf462-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="cf462-114">DNS 호스팅 공급자 찾기</span><span class="sxs-lookup"><span data-stu-id="cf462-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="cf462-115">*.COM*, *.NET*, and *.EDU*로 끝나는 도메인만이 이 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="cf462-116">[InterNIC 검색 페이지]( https://go.microsoft.com/fwlink/p/?LinkId=402770)의 **Whois Search(Whois 검색)** 상자에 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="cf462-117">예로 contoso.com 등을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="cf462-118">**Domain(도메인)** 옵션을 선택하고 **Submit(제출)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="cf462-119">
            \*\*Whois Search Results(Whois 검색 결과)** 페이지에서 첫 번째 \*\*Name Server(이름 서버)** 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="cf462-120">콜론(:) 뒤에 나타나는 NS(이름 서버) 정보를 복사하고 페이지 위쪽의 **검색** 상자에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="cf462-121">**Nameserver(이름 서버)** 를 선택하고 **Submit(제출)** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="cf462-p105">
            \*\*Whois Search Results(Whois 검색 결과)\*\* 페이지에서 \*\*Registrar(등록 기관)\*\* 항목을 찾습니다. 이 항목에는 DNS 호스팅 공급자, 즉 도메인의 이름 서버를 소유한 DNS 공급자가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf462-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

