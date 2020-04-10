---
title: Cloudflare에서 Office 365에 대 한 DNS 레코드 만들기
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스 (Office 365 용)에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 8d64824f880bab9e6691ebf47c9508c555562fe4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211814"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a><span data-ttu-id="20397-103">Cloudflare에서 Office 365에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="20397-103">Create DNS records at Cloudflare for Office 365</span></span>

 <span data-ttu-id="20397-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="20397-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="20397-105">Cloudflare가 DNS 호스팅 공급자 인 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="20397-106">Cloudflare에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20397-106">After you add these records at Cloudflare, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="20397-107">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20397-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="20397-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20397-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="20397-111">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="20397-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="20397-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="20397-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="20397-113">이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="20397-114">Cloudflare에 등록할 때 Cloudflare **설정** 프로세스를 사용 하 여 도메인을 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="20397-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="20397-115">추가한 도메인은 별도의 도메인 등록 기관에서 구매한 것입니다. Cloudflare는 도메인 등록 서비스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20397-115">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services.</span></span> <span data-ttu-id="20397-116">Office 365에서 도메인에 대 한 DNS 레코드를 확인 하 고 만들려면 먼저 도메인 등록 기관에서 이름 서버를 변경 하 여 Cloudflare 이름 서버을 사용 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-116">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="20397-117">도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="20397-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="20397-118">도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="20397-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="20397-119">다음 표의 값을 사용 하 여 두 개의 이름 서버 레코드를 만들거나 기존 이름 서버 레코드를 해당 값과 일치 하도록 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="20397-120">첫 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="20397-120">First nameserver</span></span>  <br/> |<span data-ttu-id="20397-121">Cloudflare에서 제공 하는 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="20397-122">두 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="20397-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="20397-123">Cloudflare에서 제공 하는 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="20397-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="20397-124">You should use at least two name server records.</span></span> <span data-ttu-id="20397-125">다른 이름 서버가 나열 되어 있으면 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="20397-126">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="20397-p104">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="20397-p104">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="20397-129">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="20397-129">Add a TXT record for verification</span></span>
<span data-ttu-id="20397-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="20397-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="20397-p105">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20397-p105">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20397-p106">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20397-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="20397-135">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="20397-136">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20397-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="20397-137">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="20397-138">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="20397-139">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="20397-140">**유형**</span><span class="sxs-lookup"><span data-stu-id="20397-140">**Type**</span></span>|<span data-ttu-id="20397-141">**이름**</span><span class="sxs-lookup"><span data-stu-id="20397-141">**Name**</span></span>|<span data-ttu-id="20397-142">**자동 TTL**</span><span class="sxs-lookup"><span data-stu-id="20397-142">**Automatic TTL**</span></span>|<span data-ttu-id="20397-143">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="20397-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="20397-144">TXT</span><span class="sxs-lookup"><span data-stu-id="20397-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="20397-145">30분</span><span class="sxs-lookup"><span data-stu-id="20397-145">30 minutes</span></span>  <br/> |<span data-ttu-id="20397-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="20397-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="20397-147">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="20397-147">**Note:** This is an example.</span></span> <span data-ttu-id="20397-148">여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-148">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="20397-149">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="20397-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="20397-150">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="20397-151">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="20397-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="20397-152">이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-152">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="20397-153">Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20397-153">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="20397-154">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="20397-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="20397-155">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="20397-156">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="20397-157">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="20397-p109">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20397-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="20397-161">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="20397-161">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="20397-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="20397-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="20397-163">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-163">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="20397-164">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20397-164">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="20397-165">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="20397-166">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="20397-167">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="20397-168">**유형**</span><span class="sxs-lookup"><span data-stu-id="20397-168">**Type**</span></span>|<span data-ttu-id="20397-169">**이름**</span><span class="sxs-lookup"><span data-stu-id="20397-169">**Name**</span></span>|<span data-ttu-id="20397-170">**메일 서버**</span><span class="sxs-lookup"><span data-stu-id="20397-170">**Mail server**</span></span>|<span data-ttu-id="20397-171">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="20397-171">**Priority**</span></span>|<span data-ttu-id="20397-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20397-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="20397-173">MX</span><span class="sxs-lookup"><span data-stu-id="20397-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="20397-174">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="20397-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="20397-175">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20397-175">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="20397-176">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="20397-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="20397-177">1 </span><span class="sxs-lookup"><span data-stu-id="20397-177">1</span></span>  <br/> <span data-ttu-id="20397-178">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20397-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="20397-179">30분</span><span class="sxs-lookup"><span data-stu-id="20397-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="20397-180">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="20397-181">**Mx 레코드** 구역에 다른 mx 레코드가 나열 되어 있으면 **삭제 (X)** 아이콘을 선택 하 여 해당 레코드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="20397-182">확인 대화 상자에서 **삭제** 를 선택 하 여 변경 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="20397-183">Office 365에 필요한 6 개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="20397-183">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="20397-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="20397-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="20397-185">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-185">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="20397-186">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20397-186">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="20397-187">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="20397-188">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="20397-189">5 개의 CNAME 레코드 중 처음 일부를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="20397-190">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="20397-191">**유형**</span><span class="sxs-lookup"><span data-stu-id="20397-191">**Type**</span></span>|<span data-ttu-id="20397-192">**Name(이름)**</span><span class="sxs-lookup"><span data-stu-id="20397-192">**Name**</span></span>|<span data-ttu-id="20397-193">**Target(대상)**</span><span class="sxs-lookup"><span data-stu-id="20397-193">**Target**</span></span>|<span data-ttu-id="20397-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20397-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="20397-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="20397-195">CNAME</span></span>  <br/> |<span data-ttu-id="20397-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="20397-196">autodiscover</span></span>  <br/> |<span data-ttu-id="20397-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="20397-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="20397-198">30분</span><span class="sxs-lookup"><span data-stu-id="20397-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="20397-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="20397-199">CNAME</span></span>  <br/> |<span data-ttu-id="20397-200">sip</span><span class="sxs-lookup"><span data-stu-id="20397-200">sip</span></span>  <br/> |<span data-ttu-id="20397-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20397-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="20397-202">30분</span><span class="sxs-lookup"><span data-stu-id="20397-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="20397-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="20397-203">CNAME</span></span>  <br/> |<span data-ttu-id="20397-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="20397-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="20397-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20397-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="20397-206">30분</span><span class="sxs-lookup"><span data-stu-id="20397-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="20397-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="20397-207">CNAME</span></span>  <br/> |<span data-ttu-id="20397-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="20397-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="20397-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="20397-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="20397-210">30분</span><span class="sxs-lookup"><span data-stu-id="20397-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="20397-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="20397-211">CNAME</span></span>  <br/> |<span data-ttu-id="20397-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="20397-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="20397-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20397-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="20397-214">30분</span><span class="sxs-lookup"><span data-stu-id="20397-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="20397-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="20397-215">CNAME</span></span>  <br/> |<span data-ttu-id="20397-216">msoid</span><span class="sxs-lookup"><span data-stu-id="20397-216">msoid</span></span>  <br/> |<span data-ttu-id="20397-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="20397-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="20397-218">30분</span><span class="sxs-lookup"><span data-stu-id="20397-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="20397-219">**DNS 트래픽** 아이콘 (주황색 클라우드)을 선택 하 여 cloudflare 서버를 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="20397-220">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="20397-221">나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="20397-222">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="20397-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="20397-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="20397-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="20397-224">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20397-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="20397-225">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20397-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="20397-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="20397-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="20397-227">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="20397-227">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="20397-228">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="20397-229">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20397-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="20397-230">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="20397-231">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="20397-232">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="20397-233">**유형**</span><span class="sxs-lookup"><span data-stu-id="20397-233">**Type**</span></span>|<span data-ttu-id="20397-234">**이름**</span><span class="sxs-lookup"><span data-stu-id="20397-234">**Name**</span></span>|<span data-ttu-id="20397-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20397-235">**TTL**</span></span>|<span data-ttu-id="20397-236">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="20397-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="20397-237">TXT</span><span class="sxs-lookup"><span data-stu-id="20397-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="20397-238">30분</span><span class="sxs-lookup"><span data-stu-id="20397-238">30 minutes</span></span>  <br/> |<span data-ttu-id="20397-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="20397-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="20397-240">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="20397-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="20397-241">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="20397-242">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="20397-242">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="20397-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="20397-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="20397-244">Cloudflare는이 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="20397-245">아래 단계와 현재 Cloudflare GUI (그래픽 사용자 인터페이스) 간의 불일치가 표시 되는 경우 [Cloudflare 커뮤니티](https://community.cloudflare.com/)를 활용 하세요.</span><span class="sxs-lookup"><span data-stu-id="20397-245">In case you see discrepancies between the steps below and the current Cloudflare GUI(Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="20397-246">시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="20397-247">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20397-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="20397-248">**홈** 페이지에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="20397-249">도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="20397-250">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="20397-251">**DNS 관리** 페이지에서 **레코드 추가**를 클릭 하 고 다음 표의 첫 번째 행에 있는 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="20397-252">**유형**</span><span class="sxs-lookup"><span data-stu-id="20397-252">**Type**</span></span>|<span data-ttu-id="20397-253">**서비스**</span><span class="sxs-lookup"><span data-stu-id="20397-253">**Service**</span></span>|<span data-ttu-id="20397-254">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="20397-254">**Protocol**</span></span>|<span data-ttu-id="20397-255">**이름**</span><span class="sxs-lookup"><span data-stu-id="20397-255">**Name**</span></span>|<span data-ttu-id="20397-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20397-256">**TTL**</span></span>|<span data-ttu-id="20397-257">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="20397-257">**Priority**</span></span>|<span data-ttu-id="20397-258">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="20397-258">**Weight**</span></span>|<span data-ttu-id="20397-259">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="20397-259">**Port**</span></span>|<span data-ttu-id="20397-260">**대상**</span><span class="sxs-lookup"><span data-stu-id="20397-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="20397-261">SRV</span><span class="sxs-lookup"><span data-stu-id="20397-261">SRV</span></span>|<span data-ttu-id="20397-262">_sip</span><span class="sxs-lookup"><span data-stu-id="20397-262">_sip</span></span> |<span data-ttu-id="20397-263">TLS</span><span class="sxs-lookup"><span data-stu-id="20397-263">TLS</span></span> |<span data-ttu-id="20397-264">*Domain_name*사용 예를 들어 contoso.com</span><span class="sxs-lookup"><span data-stu-id="20397-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="20397-265">30분</span><span class="sxs-lookup"><span data-stu-id="20397-265">30 minutes</span></span> | <span data-ttu-id="20397-266">100</span><span class="sxs-lookup"><span data-stu-id="20397-266">100</span></span>|<span data-ttu-id="20397-267">1 </span><span class="sxs-lookup"><span data-stu-id="20397-267">1</span></span> |<span data-ttu-id="20397-268">443</span><span class="sxs-lookup"><span data-stu-id="20397-268">443</span></span> |<span data-ttu-id="20397-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20397-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="20397-270">SRV</span><span class="sxs-lookup"><span data-stu-id="20397-270">SRV</span></span>|<span data-ttu-id="20397-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="20397-271">_sipfederationtls</span></span> | <span data-ttu-id="20397-272">TCP</span><span class="sxs-lookup"><span data-stu-id="20397-272">TCP</span></span>|<span data-ttu-id="20397-273">*Domain_name*사용 예를 들어 contoso.com</span><span class="sxs-lookup"><span data-stu-id="20397-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="20397-274">30분</span><span class="sxs-lookup"><span data-stu-id="20397-274">30 minutes</span></span> |<span data-ttu-id="20397-275">100</span><span class="sxs-lookup"><span data-stu-id="20397-275">100</span></span> |<span data-ttu-id="20397-276">1 </span><span class="sxs-lookup"><span data-stu-id="20397-276">1</span></span> |<span data-ttu-id="20397-277">5061</span><span class="sxs-lookup"><span data-stu-id="20397-277">5061</span></span> | <span data-ttu-id="20397-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20397-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="20397-279">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="20397-280">표의 두 번째 행에서 값을 선택 하 여 다른 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="20397-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="20397-p117">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20397-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
