---
title: Cloudflare에서 Microsoft용 DNS 레코드 만들기
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Microsoft용 Cloudflare에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 학습합니다.
ms.openlocfilehash: 8d5dd7779f07fd42dd230ee33c40849da3519d26
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939275"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="42e39-103">Cloudflare에서 Microsoft용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="42e39-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="42e39-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="42e39-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="42e39-105">DNS 호스팅 공급자로 Cloudflare를 사용하고 있는 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="42e39-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="42e39-106">Cloudflare에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 365 서비스에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="42e39-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42e39-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="42e39-110">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="42e39-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="42e39-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="42e39-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="42e39-112">이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="42e39-113">Cloudflare에 등록할 때 Cloudflare 설치 프로세스를 사용하여 도메인을 **추가했습니다.**</span><span class="sxs-lookup"><span data-stu-id="42e39-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="42e39-114">추가한 도메인은 Cloudflare 또는 별도의 도메인 등록 기관에서 구입한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="42e39-115">Microsoft 365에서 도메인에 대한 DNS 레코드를 확인하고 만들하려면 먼저 도메인 등록 기관에서 Cloudflare의 이름 서버를 사용할 수 있도록 이름 서버를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="42e39-116">도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="42e39-117">도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="42e39-118">다음 표의 값을 사용하여 이름 서비스 레코드를 두 개 만들거나 이러한 값과 일치하게 기존 이름 서비스 레코드를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="42e39-119">첫 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="42e39-119">First nameserver</span></span>  <br/> |<span data-ttu-id="42e39-120">Cloudflare에서 제공하는 이름 서비스 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="42e39-121">두 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="42e39-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="42e39-122">Cloudflare에서 제공하는 이름 서비스 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="42e39-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="42e39-123">You should use at least two name server records.</span></span> <span data-ttu-id="42e39-124">다른 이름 서버가 나열되어 있는 경우 해당 서버를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="42e39-125">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="42e39-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="42e39-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="42e39-127">그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="42e39-128">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="42e39-128">Add a TXT record for verification</span></span>
<span data-ttu-id="42e39-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="42e39-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="42e39-p105">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42e39-p106">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="42e39-134">시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login)</span><span class="sxs-lookup"><span data-stu-id="42e39-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="42e39-135">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="42e39-136">홈 **페이지에서** 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="42e39-137">도메인의 **개요** 페이지에서 **DNS를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42e39-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="42e39-138">DNS 관리 **페이지에서** 레코드 추가를 클릭한 다음 다음 표의 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="42e39-139">유형</span><span class="sxs-lookup"><span data-stu-id="42e39-139">Type</span></span> | <span data-ttu-id="42e39-140">이름</span><span class="sxs-lookup"><span data-stu-id="42e39-140">Name</span></span> | <span data-ttu-id="42e39-141">자동 TTL</span><span class="sxs-lookup"><span data-stu-id="42e39-141">Automatic TTL</span></span> | <span data-ttu-id="42e39-142">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="42e39-142">Content</span></span> |
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="42e39-143">TXT</span><span class="sxs-lookup"><span data-stu-id="42e39-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="42e39-144">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-144">30 minutes</span></span>  <br/> |<span data-ttu-id="42e39-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="42e39-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="42e39-146">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-146">**Note:** This is an example.</span></span> <span data-ttu-id="42e39-147">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="42e39-148">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="42e39-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="42e39-149">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="42e39-150">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="42e39-151">이제 도메인 등록 기관의 사이트에 레코드를 추가한 후 Microsoft로 돌아가 레코드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="42e39-152">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="42e39-153">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="42e39-154">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="42e39-155">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="42e39-156">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="42e39-p109">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42e39-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="42e39-160">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="42e39-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="42e39-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="42e39-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="42e39-162">시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login)</span><span class="sxs-lookup"><span data-stu-id="42e39-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="42e39-163">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-163">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="42e39-164">홈 **페이지에서** 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="42e39-165">도메인의 **개요** 페이지에서 **DNS를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42e39-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="42e39-166">DNS 관리 **페이지에서** 레코드 추가를 클릭한 다음 다음 표의 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="42e39-167">유형</span><span class="sxs-lookup"><span data-stu-id="42e39-167">Type</span></span> | <span data-ttu-id="42e39-168">이름</span><span class="sxs-lookup"><span data-stu-id="42e39-168">Name</span></span> | <span data-ttu-id="42e39-169">메일 서버</span><span class="sxs-lookup"><span data-stu-id="42e39-169">Mail server</span></span> | <span data-ttu-id="42e39-170">우선 순위</span><span class="sxs-lookup"><span data-stu-id="42e39-170">Priority</span></span> | <span data-ttu-id="42e39-171">TTL</span><span class="sxs-lookup"><span data-stu-id="42e39-171">TTL</span></span> |
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="42e39-172">MX</span><span class="sxs-lookup"><span data-stu-id="42e39-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="42e39-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="42e39-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="42e39-174">**참고:** Microsoft  *\<domain-key\>*  365 계정에서 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="42e39-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="42e39-175">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="42e39-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="42e39-176">1 </span><span class="sxs-lookup"><span data-stu-id="42e39-176">1</span></span>  <br/> <span data-ttu-id="42e39-177">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42e39-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="42e39-178">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="42e39-179">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="42e39-180">MX 레코드 섹션에 나열된 다른 **MX** 레코드가 있는 경우 삭제(X) 아이콘을 선택하여 해당 레코드를 **삭제합니다.**</span><span class="sxs-lookup"><span data-stu-id="42e39-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="42e39-181">확인 대화 상자에서 **삭제를** 선택하여 변경 내용을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="42e39-182">Microsoft에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="42e39-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="42e39-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="42e39-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="42e39-184">시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login)</span><span class="sxs-lookup"><span data-stu-id="42e39-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="42e39-185">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-185">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="42e39-186">홈 **페이지에서** 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="42e39-187">도메인의 **개요** 페이지에서 **DNS를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42e39-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="42e39-188">5개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="42e39-189">DNS 관리 **페이지에서** 레코드 추가를 클릭한 다음 다음 표의 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    | <span data-ttu-id="42e39-190">유형</span><span class="sxs-lookup"><span data-stu-id="42e39-190">Type</span></span> | <span data-ttu-id="42e39-191">이름</span><span class="sxs-lookup"><span data-stu-id="42e39-191">Name</span></span> | <span data-ttu-id="42e39-192">Target(대상)</span><span class="sxs-lookup"><span data-stu-id="42e39-192">Target</span></span> | <span data-ttu-id="42e39-193">TTL</span><span class="sxs-lookup"><span data-stu-id="42e39-193">TTL</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="42e39-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="42e39-194">CNAME</span></span>  <br/> |<span data-ttu-id="42e39-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="42e39-195">autodiscover</span></span>  <br/> |<span data-ttu-id="42e39-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="42e39-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="42e39-197">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="42e39-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="42e39-198">CNAME</span></span>  <br/> |<span data-ttu-id="42e39-199">sip</span><span class="sxs-lookup"><span data-stu-id="42e39-199">sip</span></span>  <br/> |<span data-ttu-id="42e39-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="42e39-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="42e39-201">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="42e39-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="42e39-202">CNAME</span></span>  <br/> |<span data-ttu-id="42e39-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="42e39-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="42e39-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="42e39-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="42e39-205">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="42e39-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="42e39-206">CNAME</span></span>  <br/> |<span data-ttu-id="42e39-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="42e39-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="42e39-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="42e39-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="42e39-209">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="42e39-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="42e39-210">CNAME</span></span>  <br/> |<span data-ttu-id="42e39-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="42e39-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="42e39-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="42e39-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="42e39-213">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="42e39-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="42e39-214">CNAME</span></span>  <br/> |<span data-ttu-id="42e39-215">msoid</span><span class="sxs-lookup"><span data-stu-id="42e39-215">msoid</span></span>  <br/> |<span data-ttu-id="42e39-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="42e39-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="42e39-217">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="42e39-218">DNS 트래픽 **아이콘(주황색** 클라우드를 회색으로 변경)을 선택하여 Cloudflare 서버를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-218">Select the **DNS Traffic** icon (change orange cloud to grey) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="42e39-219">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="42e39-220">나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="42e39-221">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="42e39-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="42e39-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="42e39-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="42e39-223">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="42e39-224">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="42e39-225">도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="42e39-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="42e39-226">대신, 필수 Microsoft 365 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="42e39-227">시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login)</span><span class="sxs-lookup"><span data-stu-id="42e39-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="42e39-228">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="42e39-229">홈 **페이지에서** 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="42e39-230">도메인의 **개요** 페이지에서 **DNS를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42e39-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="42e39-231">DNS 관리 **페이지에서** 레코드 추가를 클릭한 다음 다음 표의 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    | <span data-ttu-id="42e39-232">유형</span><span class="sxs-lookup"><span data-stu-id="42e39-232">Type</span></span> | <span data-ttu-id="42e39-233">이름</span><span class="sxs-lookup"><span data-stu-id="42e39-233">Name</span></span> | <span data-ttu-id="42e39-234">TTL</span><span class="sxs-lookup"><span data-stu-id="42e39-234">TTL</span></span> | <span data-ttu-id="42e39-235">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="42e39-235">Content</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="42e39-236">TXT</span><span class="sxs-lookup"><span data-stu-id="42e39-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="42e39-237">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-237">30 minutes</span></span>  <br/> |<span data-ttu-id="42e39-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="42e39-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="42e39-239">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="42e39-240">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="42e39-241">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="42e39-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="42e39-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="42e39-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="42e39-243">Cloudflare는 이 기능을 사용할 수 있도록 하는 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="42e39-244">아래 단계와 현재 Cloudflare GUI(그래픽 사용자 인터페이스) 간에 불일치가 표시될 경우 [Cloudflare 커뮤니티를 활용하세요.](https://community.cloudflare.com/)</span><span class="sxs-lookup"><span data-stu-id="42e39-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="42e39-245">시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login)</span><span class="sxs-lookup"><span data-stu-id="42e39-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="42e39-246">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="42e39-247">홈 **페이지에서** 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="42e39-248">도메인의 **개요** 페이지에서 **DNS를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42e39-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="42e39-249">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="42e39-250">DNS 관리 **페이지에서** 레코드 추가를 클릭한 다음 다음 표의 첫 번째 행에서 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    | <span data-ttu-id="42e39-251">유형</span><span class="sxs-lookup"><span data-stu-id="42e39-251">Type</span></span> | <span data-ttu-id="42e39-252">서비스</span><span class="sxs-lookup"><span data-stu-id="42e39-252">Service</span></span> | <span data-ttu-id="42e39-253">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="42e39-253">Protocol</span></span> | <span data-ttu-id="42e39-254">이름</span><span class="sxs-lookup"><span data-stu-id="42e39-254">Name</span></span> | <span data-ttu-id="42e39-255">TTL</span><span class="sxs-lookup"><span data-stu-id="42e39-255">TTL</span></span> | <span data-ttu-id="42e39-256">우선 순위</span><span class="sxs-lookup"><span data-stu-id="42e39-256">Priority</span></span> | <span data-ttu-id="42e39-257">가중치</span><span class="sxs-lookup"><span data-stu-id="42e39-257">Weight</span></span> | <span data-ttu-id="42e39-258">포트</span><span class="sxs-lookup"><span data-stu-id="42e39-258">Port</span></span> | <span data-ttu-id="42e39-259">Target(대상)</span><span class="sxs-lookup"><span data-stu-id="42e39-259">Target</span></span> |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="42e39-260">SRV</span><span class="sxs-lookup"><span data-stu-id="42e39-260">SRV</span></span>|<span data-ttu-id="42e39-261">_sip</span><span class="sxs-lookup"><span data-stu-id="42e39-261">_sip</span></span> |<span data-ttu-id="42e39-262">TLS</span><span class="sxs-lookup"><span data-stu-id="42e39-262">TLS</span></span> |<span data-ttu-id="42e39-263">사용자 *domain_name;* 예를 들어 contoso.com</span><span class="sxs-lookup"><span data-stu-id="42e39-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="42e39-264">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-264">30 minutes</span></span> | <span data-ttu-id="42e39-265">100</span><span class="sxs-lookup"><span data-stu-id="42e39-265">100</span></span>|<span data-ttu-id="42e39-266">1 </span><span class="sxs-lookup"><span data-stu-id="42e39-266">1</span></span> |<span data-ttu-id="42e39-267">443</span><span class="sxs-lookup"><span data-stu-id="42e39-267">443</span></span> |<span data-ttu-id="42e39-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="42e39-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="42e39-269">SRV</span><span class="sxs-lookup"><span data-stu-id="42e39-269">SRV</span></span>|<span data-ttu-id="42e39-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="42e39-270">_sipfederationtls</span></span> | <span data-ttu-id="42e39-271">TCP</span><span class="sxs-lookup"><span data-stu-id="42e39-271">TCP</span></span>|<span data-ttu-id="42e39-272">사용자 *domain_name;* 예를 들어 contoso.com</span><span class="sxs-lookup"><span data-stu-id="42e39-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="42e39-273">30분</span><span class="sxs-lookup"><span data-stu-id="42e39-273">30 minutes</span></span> |<span data-ttu-id="42e39-274">100</span><span class="sxs-lookup"><span data-stu-id="42e39-274">100</span></span> |<span data-ttu-id="42e39-275">1 </span><span class="sxs-lookup"><span data-stu-id="42e39-275">1</span></span> |<span data-ttu-id="42e39-276">5061</span><span class="sxs-lookup"><span data-stu-id="42e39-276">5061</span></span> | <span data-ttu-id="42e39-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="42e39-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="42e39-278">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="42e39-279">표의 두 번째 행에서 값을 선택하여 다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="42e39-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="42e39-p117">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42e39-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
