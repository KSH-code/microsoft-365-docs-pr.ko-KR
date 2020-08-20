---
title: Wix에서 Microsoft용 DNS 레코드 만들기
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Microsoft에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype 온라인 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 알아봅니다.
ms.openlocfilehash: fcc0f8e8187e22dde68149e0f2a80073312bff7f
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814447"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="ab796-103">Wix에서 Microsoft용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="ab796-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="ab796-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab796-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ab796-105">DNS 호스팅 공급자로 Wix를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="ab796-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="ab796-107">[확인을 위한 TXT 레코드를 추가합니다.](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="ab796-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="ab796-108">[사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드를 추가합니다.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="ab796-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="ab796-109">[Microsoft에 필요한 5가지 CNAME 레코드를 추가합니다.](#add-the-five-cname-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="ab796-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="ab796-110">[전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드를 추가합니다.](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="ab796-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="ab796-111">[Microsoft 필요한 2개의 SRV 레코드를 추가합니다.](#add-the-two-srv-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="ab796-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="ab796-112">Wix에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ab796-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab796-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ab796-116">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="ab796-116">Add a TXT record for verification</span></span>
<span data-ttu-id="ab796-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="ab796-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="ab796-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab796-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="ab796-122">WIX는 하위 도메인에 대한 DNS 항목을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="ab796-123">시작하려면 이 링크를 사용하여 Wix의 도메인 페이지로 [이동합니다.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="ab796-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="ab796-124">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ab796-125">My **Domains(내** 도메인 관리자) **페이지의 Advanced(고급** 영역)에서 **DNS Edit DNS(고급 관리)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="ab796-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="ab796-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="ab796-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ab796-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="ab796-128">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="ab796-128">Host Name</span></span> <br/> | <span data-ttu-id="ab796-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="ab796-129">TXT Value</span></span> <br/> | <span data-ttu-id="ab796-130">TTL</span><span class="sxs-lookup"><span data-stu-id="ab796-130">TTL</span></span> <br/> |
   |<span data-ttu-id="ab796-131">자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="ab796-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ab796-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ab796-133">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-133">**Note:** This is an example.</span></span> <span data-ttu-id="ab796-134">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="ab796-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="ab796-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="ab796-136">1시간</span><span class="sxs-lookup"><span data-stu-id="ab796-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="ab796-137">DNS **편집기 위쪽의 DNS** 저장 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="ab796-138">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ab796-139">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ab796-140">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ab796-141">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab796-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ab796-142">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="ab796-143">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="ab796-144">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ab796-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab796-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ab796-148">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="ab796-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ab796-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="ab796-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="ab796-150">시작하려면 이 링크를 사용하여 Wix의 도메인 페이지로 [이동합니다.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="ab796-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="ab796-151">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ab796-152">내 **도메인 페이지의** 사서함 **영역에서** MX 레코드 **구성 링크를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="ab796-153">전자 **메일** 공급자 **드롭다운 목록에서 다른** 사람을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="ab796-154">다른 **위치를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="ab796-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="ab796-155">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="ab796-156">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="ab796-156">Host Name</span></span> | <span data-ttu-id="ab796-157">Points to </span><span class="sxs-lookup"><span data-stu-id="ab796-157">Points to</span></span> | <span data-ttu-id="ab796-158">우선 순위</span><span class="sxs-lookup"><span data-stu-id="ab796-158">Priority</span></span> | <span data-ttu-id="ab796-159">TTL</span><span class="sxs-lookup"><span data-stu-id="ab796-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="ab796-160">자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-160">Automatically populated</span></span> <br/> | <span data-ttu-id="ab796-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ab796-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ab796-162">**참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="ab796-163">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="ab796-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="ab796-164">0</span><span class="sxs-lookup"><span data-stu-id="ab796-164">0</span></span>  <br/> <span data-ttu-id="ab796-165">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab796-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="ab796-166">1시간</span><span class="sxs-lookup"><span data-stu-id="ab796-166">1 Hour</span></span>|
   
6. <span data-ttu-id="ab796-167">다른 MX 레코드가 나열된 경우 하나씩 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="ab796-168">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="ab796-169">확인 대화 상자에서 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ab796-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ab796-170">Microsoft에 필요한 5개의 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="ab796-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ab796-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="ab796-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="ab796-172">시작하려면 이 링크를 사용하여 Wix의 도메인 페이지로 [이동합니다.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="ab796-172">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="ab796-173">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="ab796-173">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="ab796-174">My **Domains(내** 도메인 관리자) **페이지의 Advanced(고급** 영역)에서 **DNS Edit DNS(고급 관리)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="ab796-175">각 CNAME **레코드에** 대해 **DNS 편집기의 CNAME(별칭)** 행에 다른 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="ab796-176">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="ab796-177">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="ab796-177">Host Name</span></span> | <span data-ttu-id="ab796-178">Points to </span><span class="sxs-lookup"><span data-stu-id="ab796-178">Points to</span></span> | <span data-ttu-id="ab796-179">TTL</span><span class="sxs-lookup"><span data-stu-id="ab796-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="ab796-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ab796-180">autodiscover</span></span>  <br/> |<span data-ttu-id="ab796-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ab796-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="ab796-182">1시간</span><span class="sxs-lookup"><span data-stu-id="ab796-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="ab796-183">sip</span><span class="sxs-lookup"><span data-stu-id="ab796-183">sip</span></span>  <br/> |<span data-ttu-id="ab796-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ab796-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="ab796-185">1시간</span><span class="sxs-lookup"><span data-stu-id="ab796-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="ab796-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ab796-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ab796-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ab796-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="ab796-188">1시간</span><span class="sxs-lookup"><span data-stu-id="ab796-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="ab796-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ab796-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ab796-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ab796-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="ab796-191">1시간</span><span class="sxs-lookup"><span data-stu-id="ab796-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="ab796-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ab796-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ab796-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ab796-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="ab796-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ab796-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="ab796-195">DNS **편집기 위쪽의 DNS** 저장 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="ab796-196">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ab796-197">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="ab796-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ab796-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="ab796-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab796-199">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ab796-200">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ab796-201">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ab796-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ab796-202">대신, 필수 Microsoft 값을 현재 레코드에 추가하여 두 값  *집합을 모두*  포함한 단일 SPF 레코드가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="ab796-203">시작하려면 이 링크를 사용하여 Wix의 도메인 페이지로 [이동합니다.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="ab796-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="ab796-204">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ab796-205">My **Domains(내** 도메인 관리자) **페이지의 Advanced(고급** 영역)에서 **DNS Edit DNS(고급 관리)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="ab796-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="ab796-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="ab796-207">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="ab796-208">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="ab796-208">Host Name</span></span> | <span data-ttu-id="ab796-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="ab796-209">TXT Value</span></span> | <span data-ttu-id="ab796-210">TTL</span><span class="sxs-lookup"><span data-stu-id="ab796-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="ab796-211">[비워 두기]</span><span class="sxs-lookup"><span data-stu-id="ab796-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="ab796-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ab796-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ab796-213">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="ab796-214">TXT</span><span class="sxs-lookup"><span data-stu-id="ab796-214">TXT</span></span>  <br/> | <span data-ttu-id="ab796-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ab796-215">1 Hour</span></span> |
   
5. <span data-ttu-id="ab796-216">DNS **편집기 위쪽의 DNS** 저장 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="ab796-217">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ab796-218">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="ab796-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ab796-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="ab796-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="ab796-220">시작하려면 이 링크를 사용하여 Wix의 도메인 페이지로 [이동합니다.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="ab796-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="ab796-221">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ab796-222">My **Domains(내** 도메인 관리자) **페이지의 Advanced(고급** 영역)에서 **DNS Edit DNS(고급 관리)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="ab796-223">DNS **편집기의** **SRV 행에서 다른** 것을 선택합니다 .</span><span class="sxs-lookup"><span data-stu-id="ab796-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="ab796-224">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="ab796-225">서비스</span><span class="sxs-lookup"><span data-stu-id="ab796-225">Service</span></span> | <span data-ttu-id="ab796-226">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="ab796-226">Protocol</span></span> | <span data-ttu-id="ab796-227">이름</span><span class="sxs-lookup"><span data-stu-id="ab796-227">Name</span></span> | <span data-ttu-id="ab796-228">두고트</span><span class="sxs-lookup"><span data-stu-id="ab796-228">Weight</span></span> | <span data-ttu-id="ab796-229">포트</span><span class="sxs-lookup"><span data-stu-id="ab796-229">Port</span></span> | <span data-ttu-id="ab796-230">Target(대상)</span><span class="sxs-lookup"><span data-stu-id="ab796-230">Target</span></span> | <span data-ttu-id="ab796-231">우선 순위</span><span class="sxs-lookup"><span data-stu-id="ab796-231">Priority</span></span> | <span data-ttu-id="ab796-232">TTL</span><span class="sxs-lookup"><span data-stu-id="ab796-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="ab796-233">sip</span><span class="sxs-lookup"><span data-stu-id="ab796-233">sip</span></span>  |<span data-ttu-id="ab796-234">tls</span><span class="sxs-lookup"><span data-stu-id="ab796-234">tls</span></span>  |<span data-ttu-id="ab796-235">자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-235">Automatically populated</span></span> |<span data-ttu-id="ab796-236">1</span><span class="sxs-lookup"><span data-stu-id="ab796-236">1</span></span>  |<span data-ttu-id="ab796-237">443</span><span class="sxs-lookup"><span data-stu-id="ab796-237">443</span></span>   |<span data-ttu-id="ab796-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ab796-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="ab796-239">100</span><span class="sxs-lookup"><span data-stu-id="ab796-239">100</span></span> |<span data-ttu-id="ab796-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ab796-240">1 Hour</span></span> |
   |<span data-ttu-id="ab796-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="ab796-241">sipfed</span></span>|<span data-ttu-id="ab796-242">tcp</span><span class="sxs-lookup"><span data-stu-id="ab796-242">tcp</span></span> |<span data-ttu-id="ab796-243">자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-243">Automatically populated</span></span>|<span data-ttu-id="ab796-244">1</span><span class="sxs-lookup"><span data-stu-id="ab796-244">1</span></span> |<span data-ttu-id="ab796-245">5061</span><span class="sxs-lookup"><span data-stu-id="ab796-245">5061</span></span> |<span data-ttu-id="ab796-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ab796-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="ab796-247">100</span><span class="sxs-lookup"><span data-stu-id="ab796-247">100</span></span> | <span data-ttu-id="ab796-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ab796-248">1 Hour</span></span> |
   
5. <span data-ttu-id="ab796-249">DNS **편집기 위쪽의 DNS** 저장 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="ab796-250">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="ab796-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ab796-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab796-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
