---
title: Microsoft에 대 한 Cloudflare에서 DNS 레코드 만들기
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
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft에 대 한 Cloudflare로 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 301ed156584d9a9a2b84b88db7d6969ade5b34a2
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646154"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="06c6f-103">Microsoft에 대 한 Cloudflare에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="06c6f-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="06c6f-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="06c6f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="06c6f-105">Cloudflare가 DNS 호스팅 공급자 인 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="06c6f-106">Cloudflare에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 365 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="06c6f-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06c6f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="06c6f-110">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="06c6f-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="06c6f-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="06c6f-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="06c6f-112">이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="06c6f-113">Cloudflare에 등록할 때 Cloudflare **설정** 프로세스를 사용 하 여 도메인을 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="06c6f-114">추가한 도메인은 Cloudflare 또는 별도의 도메인 등록 기관에서 구입 했습니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="06c6f-115">Microsoft 365에서 도메인에 대 한 DNS 레코드를 확인 하 고 만들려면 먼저 도메인 등록 기관에서 이름 서버를 변경 하 여 Cloudflare 이름 서버을 사용 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="06c6f-116">도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="06c6f-117">도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="06c6f-118">다음 표의 값을 사용 하 여 두 개의 이름 서버 레코드를 만들거나 기존 이름 서버 레코드를 해당 값과 일치 하도록 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="06c6f-119">첫 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="06c6f-119">First nameserver</span></span>  <br/> |<span data-ttu-id="06c6f-120">Cloudflare에서 제공 하는 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="06c6f-121">두 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="06c6f-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="06c6f-122">Cloudflare에서 제공 하는 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="06c6f-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="06c6f-123">You should use at least two name server records.</span></span> <span data-ttu-id="06c6f-124">다른 이름 서버가 나열 되어 있으면 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="06c6f-125">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="06c6f-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="06c6f-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="06c6f-127">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="06c6f-128">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="06c6f-128">Add a TXT record for verification</span></span>
<span data-ttu-id="06c6f-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="06c6f-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="06c6f-p105">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="06c6f-p106">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="06c6f-134">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="06c6f-135">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="06c6f-136">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="06c6f-137">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="06c6f-138">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="06c6f-139">**유형**</span><span class="sxs-lookup"><span data-stu-id="06c6f-139">**Type**</span></span>|<span data-ttu-id="06c6f-140">**이름**</span><span class="sxs-lookup"><span data-stu-id="06c6f-140">**Name**</span></span>|<span data-ttu-id="06c6f-141">**자동 TTL**</span><span class="sxs-lookup"><span data-stu-id="06c6f-141">**Automatic TTL**</span></span>|<span data-ttu-id="06c6f-142">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="06c6f-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="06c6f-143">TXT</span><span class="sxs-lookup"><span data-stu-id="06c6f-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="06c6f-144">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-144">30 minutes</span></span>  <br/> |<span data-ttu-id="06c6f-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="06c6f-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="06c6f-146">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-146">**Note:** This is an example.</span></span> <span data-ttu-id="06c6f-147">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="06c6f-148">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="06c6f-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="06c6f-149">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="06c6f-150">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="06c6f-151">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="06c6f-152">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="06c6f-153">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="06c6f-154">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="06c6f-155">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="06c6f-156">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="06c6f-p109">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06c6f-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="06c6f-160">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="06c6f-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="06c6f-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="06c6f-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="06c6f-162">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="06c6f-163">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-163">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="06c6f-164">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="06c6f-165">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="06c6f-166">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="06c6f-167">**유형**</span><span class="sxs-lookup"><span data-stu-id="06c6f-167">**Type**</span></span>|<span data-ttu-id="06c6f-168">**이름**</span><span class="sxs-lookup"><span data-stu-id="06c6f-168">**Name**</span></span>|<span data-ttu-id="06c6f-169">**메일 서버**</span><span class="sxs-lookup"><span data-stu-id="06c6f-169">**Mail server**</span></span>|<span data-ttu-id="06c6f-170">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="06c6f-170">**Priority**</span></span>|<span data-ttu-id="06c6f-171">**TTL**</span><span class="sxs-lookup"><span data-stu-id="06c6f-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="06c6f-172">MX</span><span class="sxs-lookup"><span data-stu-id="06c6f-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="06c6f-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="06c6f-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="06c6f-174">**참고:**  *\<domain-key\>*  Microsoft 365 계정을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="06c6f-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="06c6f-175">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="06c6f-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="06c6f-176">1 </span><span class="sxs-lookup"><span data-stu-id="06c6f-176">1</span></span>  <br/> <span data-ttu-id="06c6f-177">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06c6f-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="06c6f-178">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="06c6f-179">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="06c6f-180">**Mx 레코드** 구역에 다른 mx 레코드가 나열 되어 있으면 **삭제 (X)** 아이콘을 선택 하 여 해당 레코드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="06c6f-181">확인 대화 상자에서 **삭제** 를 선택 하 여 변경 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="06c6f-182">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="06c6f-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="06c6f-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="06c6f-184">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="06c6f-185">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-185">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="06c6f-186">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="06c6f-187">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="06c6f-188">5 개의 CNAME 레코드 중 처음 일부를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="06c6f-189">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="06c6f-190">**유형**</span><span class="sxs-lookup"><span data-stu-id="06c6f-190">**Type**</span></span>|<span data-ttu-id="06c6f-191">**Name(이름)**</span><span class="sxs-lookup"><span data-stu-id="06c6f-191">**Name**</span></span>|<span data-ttu-id="06c6f-192">**Target(대상)**</span><span class="sxs-lookup"><span data-stu-id="06c6f-192">**Target**</span></span>|<span data-ttu-id="06c6f-193">**TTL**</span><span class="sxs-lookup"><span data-stu-id="06c6f-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="06c6f-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="06c6f-194">CNAME</span></span>  <br/> |<span data-ttu-id="06c6f-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="06c6f-195">autodiscover</span></span>  <br/> |<span data-ttu-id="06c6f-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="06c6f-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="06c6f-197">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="06c6f-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="06c6f-198">CNAME</span></span>  <br/> |<span data-ttu-id="06c6f-199">sip</span><span class="sxs-lookup"><span data-stu-id="06c6f-199">sip</span></span>  <br/> |<span data-ttu-id="06c6f-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06c6f-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="06c6f-201">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="06c6f-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="06c6f-202">CNAME</span></span>  <br/> |<span data-ttu-id="06c6f-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="06c6f-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="06c6f-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06c6f-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="06c6f-205">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="06c6f-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="06c6f-206">CNAME</span></span>  <br/> |<span data-ttu-id="06c6f-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="06c6f-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="06c6f-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="06c6f-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="06c6f-209">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="06c6f-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="06c6f-210">CNAME</span></span>  <br/> |<span data-ttu-id="06c6f-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="06c6f-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="06c6f-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="06c6f-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="06c6f-213">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="06c6f-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="06c6f-214">CNAME</span></span>  <br/> |<span data-ttu-id="06c6f-215">msoid</span><span class="sxs-lookup"><span data-stu-id="06c6f-215">msoid</span></span>  <br/> |<span data-ttu-id="06c6f-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="06c6f-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="06c6f-217">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="06c6f-218">**DNS 트래픽** 아이콘 (주황색 클라우드)을 선택 하 여 cloudflare 서버를 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="06c6f-219">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="06c6f-220">나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="06c6f-221">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="06c6f-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="06c6f-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="06c6f-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="06c6f-223">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="06c6f-224">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="06c6f-225">도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="06c6f-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="06c6f-226">대신, 필수 Microsoft 365 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="06c6f-227">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="06c6f-228">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="06c6f-229">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="06c6f-230">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="06c6f-231">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="06c6f-232">**유형**</span><span class="sxs-lookup"><span data-stu-id="06c6f-232">**Type**</span></span>|<span data-ttu-id="06c6f-233">**이름**</span><span class="sxs-lookup"><span data-stu-id="06c6f-233">**Name**</span></span>|<span data-ttu-id="06c6f-234">**TTL**</span><span class="sxs-lookup"><span data-stu-id="06c6f-234">**TTL**</span></span>|<span data-ttu-id="06c6f-235">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="06c6f-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="06c6f-236">TXT</span><span class="sxs-lookup"><span data-stu-id="06c6f-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="06c6f-237">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-237">30 minutes</span></span>  <br/> |<span data-ttu-id="06c6f-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="06c6f-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="06c6f-239">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="06c6f-240">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="06c6f-241">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="06c6f-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="06c6f-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="06c6f-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="06c6f-243">Cloudflare는이 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="06c6f-244">아래 단계와 현재 Cloudflare GUI (그래픽 사용자 인터페이스) 간의 불일치가 표시 되는 경우 [Cloudflare 커뮤니티](https://community.cloudflare.com/)를 활용 하세요.</span><span class="sxs-lookup"><span data-stu-id="06c6f-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="06c6f-245">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="06c6f-246">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="06c6f-247">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="06c6f-248">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="06c6f-249">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="06c6f-250">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 하 고 다음 표의 첫 번째 행에 있는 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="06c6f-251">**유형**</span><span class="sxs-lookup"><span data-stu-id="06c6f-251">**Type**</span></span>|<span data-ttu-id="06c6f-252">**서비스**</span><span class="sxs-lookup"><span data-stu-id="06c6f-252">**Service**</span></span>|<span data-ttu-id="06c6f-253">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="06c6f-253">**Protocol**</span></span>|<span data-ttu-id="06c6f-254">**이름**</span><span class="sxs-lookup"><span data-stu-id="06c6f-254">**Name**</span></span>|<span data-ttu-id="06c6f-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="06c6f-255">**TTL**</span></span>|<span data-ttu-id="06c6f-256">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="06c6f-256">**Priority**</span></span>|<span data-ttu-id="06c6f-257">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="06c6f-257">**Weight**</span></span>|<span data-ttu-id="06c6f-258">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="06c6f-258">**Port**</span></span>|<span data-ttu-id="06c6f-259">**대상**</span><span class="sxs-lookup"><span data-stu-id="06c6f-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="06c6f-260">SRV</span><span class="sxs-lookup"><span data-stu-id="06c6f-260">SRV</span></span>|<span data-ttu-id="06c6f-261">_sip</span><span class="sxs-lookup"><span data-stu-id="06c6f-261">_sip</span></span> |<span data-ttu-id="06c6f-262">TLS</span><span class="sxs-lookup"><span data-stu-id="06c6f-262">TLS</span></span> |<span data-ttu-id="06c6f-263">*Domain_name*사용 예를 들어 contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c6f-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="06c6f-264">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-264">30 minutes</span></span> | <span data-ttu-id="06c6f-265">100</span><span class="sxs-lookup"><span data-stu-id="06c6f-265">100</span></span>|<span data-ttu-id="06c6f-266">1 </span><span class="sxs-lookup"><span data-stu-id="06c6f-266">1</span></span> |<span data-ttu-id="06c6f-267">443</span><span class="sxs-lookup"><span data-stu-id="06c6f-267">443</span></span> |<span data-ttu-id="06c6f-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06c6f-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="06c6f-269">SRV</span><span class="sxs-lookup"><span data-stu-id="06c6f-269">SRV</span></span>|<span data-ttu-id="06c6f-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="06c6f-270">_sipfederationtls</span></span> | <span data-ttu-id="06c6f-271">TCP</span><span class="sxs-lookup"><span data-stu-id="06c6f-271">TCP</span></span>|<span data-ttu-id="06c6f-272">*Domain_name*사용 예를 들어 contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c6f-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="06c6f-273">30분</span><span class="sxs-lookup"><span data-stu-id="06c6f-273">30 minutes</span></span> |<span data-ttu-id="06c6f-274">100</span><span class="sxs-lookup"><span data-stu-id="06c6f-274">100</span></span> |<span data-ttu-id="06c6f-275">1 </span><span class="sxs-lookup"><span data-stu-id="06c6f-275">1</span></span> |<span data-ttu-id="06c6f-276">5061</span><span class="sxs-lookup"><span data-stu-id="06c6f-276">5061</span></span> | <span data-ttu-id="06c6f-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06c6f-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="06c6f-278">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="06c6f-279">표의 두 번째 행에서 값을 선택 하 여 다른 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c6f-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="06c6f-p117">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06c6f-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
