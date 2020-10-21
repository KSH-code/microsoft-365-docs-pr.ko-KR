---
title: Microsoft 용 Wix에서 DNS 레코드 만들기
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Microsoft 용 Wix의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: ee236a9178092bb8fd14a9615c2ac5911b1ecc87
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645662"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="c2df5-103">Microsoft 용 Wix에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="c2df5-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="c2df5-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2df5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c2df5-105">Wix가 DNS 호스팅 공급자 이면이 문서에 나와 있는 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="c2df5-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="c2df5-107">[확인을 위해 TXT 레코드를 추가](#add-a-txt-record-for-verification)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="c2df5-108">[도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="c2df5-109">[Microsoft에 필요한 다섯 개의 CNAME 레코드를 추가 합니다](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c2df5-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="c2df5-110">[SPF에 대 한 TXT 레코드를 추가 하 여 전자 메일 스팸 방지](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="c2df5-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="c2df5-111">[Microsoft에 필요한 두 개의 SRV 레코드를 추가](#add-the-two-srv-records-that-are-required-for-microsoft)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="c2df5-112">Wix에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c2df5-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2df5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c2df5-116">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="c2df5-116">Add a TXT record for verification</span></span>
<span data-ttu-id="c2df5-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="c2df5-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="c2df5-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2df5-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="c2df5-122">WIX에서는 하위 도메인에 대 한 DNS 항목을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="c2df5-123">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c2df5-124">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c2df5-125">**My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c2df5-126">DNS 편집기의 **TXT (텍스트)** 행에서 **다른** 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c2df5-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c2df5-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="c2df5-128">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="c2df5-128">Host Name</span></span> <br/> | <span data-ttu-id="c2df5-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="c2df5-129">TXT Value</span></span> <br/> | <span data-ttu-id="c2df5-130">TTL</span><span class="sxs-lookup"><span data-stu-id="c2df5-130">TTL</span></span> <br/> |
   |<span data-ttu-id="c2df5-131">자동으로 채워짐</span><span class="sxs-lookup"><span data-stu-id="c2df5-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="c2df5-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c2df5-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c2df5-133">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-133">**Note:** This is an example.</span></span> <span data-ttu-id="c2df5-134">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="c2df5-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="c2df5-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="c2df5-136">1시간</span><span class="sxs-lookup"><span data-stu-id="c2df5-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="c2df5-137">DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c2df5-138">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c2df5-139">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c2df5-140">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c2df5-141">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2df5-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c2df5-142">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="c2df5-143">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="c2df5-144">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c2df5-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2df5-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c2df5-148">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="c2df5-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c2df5-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="c2df5-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="c2df5-150">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c2df5-151">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c2df5-152">**My Domains (내 도메인** ) 페이지의 **사서함** 영역에서 **MX 레코드 구성** 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="c2df5-153">**전자 메일 공급자** 드롭다운 목록에서 **기타** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="c2df5-154">**+ 다른 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="c2df5-155">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c2df5-156">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="c2df5-156">Host Name</span></span> | <span data-ttu-id="c2df5-157">Points to </span><span class="sxs-lookup"><span data-stu-id="c2df5-157">Points to</span></span> | <span data-ttu-id="c2df5-158">우선 순위</span><span class="sxs-lookup"><span data-stu-id="c2df5-158">Priority</span></span> | <span data-ttu-id="c2df5-159">TTL</span><span class="sxs-lookup"><span data-stu-id="c2df5-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="c2df5-160">자동으로 채워짐</span><span class="sxs-lookup"><span data-stu-id="c2df5-160">Automatically populated</span></span> <br/> | <span data-ttu-id="c2df5-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c2df5-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c2df5-162">**참고:**  *\<domain-key\>*  Microsoft 계정에서를 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2df5-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="c2df5-163">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="c2df5-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="c2df5-164">개</span><span class="sxs-lookup"><span data-stu-id="c2df5-164">0</span></span>  <br/> <span data-ttu-id="c2df5-165">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2df5-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="c2df5-166">1시간</span><span class="sxs-lookup"><span data-stu-id="c2df5-166">1 Hour</span></span>|
   
6. <span data-ttu-id="c2df5-167">다른 MX 레코드가 나열 되어 있는 경우 각 레코드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="c2df5-168">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="c2df5-169">확인 대화 상자에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c2df5-170">Microsoft에 필요한 5개의 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="c2df5-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c2df5-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="c2df5-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="c2df5-172">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-172">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c2df5-173">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="c2df5-173">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c2df5-174">**My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c2df5-175">각 CNAME 레코드에 대 한 DNS 편집기의 **cname (별칭)** 행에서 다른 열로 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="c2df5-176">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c2df5-177">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="c2df5-177">Host Name</span></span> | <span data-ttu-id="c2df5-178">Points to </span><span class="sxs-lookup"><span data-stu-id="c2df5-178">Points to</span></span> | <span data-ttu-id="c2df5-179">TTL</span><span class="sxs-lookup"><span data-stu-id="c2df5-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="c2df5-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c2df5-180">autodiscover</span></span>  <br/> |<span data-ttu-id="c2df5-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c2df5-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="c2df5-182">1시간</span><span class="sxs-lookup"><span data-stu-id="c2df5-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="c2df5-183">sip</span><span class="sxs-lookup"><span data-stu-id="c2df5-183">sip</span></span>  <br/> |<span data-ttu-id="c2df5-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2df5-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c2df5-185">1시간</span><span class="sxs-lookup"><span data-stu-id="c2df5-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="c2df5-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c2df5-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c2df5-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2df5-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="c2df5-188">1시간</span><span class="sxs-lookup"><span data-stu-id="c2df5-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="c2df5-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c2df5-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c2df5-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c2df5-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="c2df5-191">1시간</span><span class="sxs-lookup"><span data-stu-id="c2df5-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="c2df5-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c2df5-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c2df5-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c2df5-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="c2df5-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c2df5-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="c2df5-195">DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c2df5-196">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c2df5-197">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="c2df5-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c2df5-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="c2df5-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2df5-199">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c2df5-200">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c2df5-201">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c2df5-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c2df5-202">대신, 두 값 집합을 모두 포함 하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="c2df5-203">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c2df5-204">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c2df5-205">**My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c2df5-206">DNS 편집기의 **TXT (텍스트)** 행에서 **다른** 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c2df5-207">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c2df5-208">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="c2df5-208">Host Name</span></span> | <span data-ttu-id="c2df5-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="c2df5-209">TXT Value</span></span> | <span data-ttu-id="c2df5-210">TTL</span><span class="sxs-lookup"><span data-stu-id="c2df5-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="c2df5-211">[이 값을 비워 둠]</span><span class="sxs-lookup"><span data-stu-id="c2df5-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="c2df5-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c2df5-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c2df5-213">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="c2df5-214">TXT</span><span class="sxs-lookup"><span data-stu-id="c2df5-214">TXT</span></span>  <br/> | <span data-ttu-id="c2df5-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c2df5-215">1 Hour</span></span> |
   
5. <span data-ttu-id="c2df5-216">DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c2df5-217">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c2df5-218">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="c2df5-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c2df5-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="c2df5-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="c2df5-220">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c2df5-221">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c2df5-222">**My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c2df5-223">DNS 편집기의 **SRV** 행에서 **다른 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c2df5-224">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c2df5-225">서비스</span><span class="sxs-lookup"><span data-stu-id="c2df5-225">Service</span></span> | <span data-ttu-id="c2df5-226">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="c2df5-226">Protocol</span></span> | <span data-ttu-id="c2df5-227">이름</span><span class="sxs-lookup"><span data-stu-id="c2df5-227">Name</span></span> | <span data-ttu-id="c2df5-228">가중치</span><span class="sxs-lookup"><span data-stu-id="c2df5-228">Weight</span></span> | <span data-ttu-id="c2df5-229">포트</span><span class="sxs-lookup"><span data-stu-id="c2df5-229">Port</span></span> | <span data-ttu-id="c2df5-230">Target(대상)</span><span class="sxs-lookup"><span data-stu-id="c2df5-230">Target</span></span> | <span data-ttu-id="c2df5-231">우선 순위</span><span class="sxs-lookup"><span data-stu-id="c2df5-231">Priority</span></span> | <span data-ttu-id="c2df5-232">TTL</span><span class="sxs-lookup"><span data-stu-id="c2df5-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="c2df5-233">sip</span><span class="sxs-lookup"><span data-stu-id="c2df5-233">sip</span></span>  |<span data-ttu-id="c2df5-234">tls</span><span class="sxs-lookup"><span data-stu-id="c2df5-234">tls</span></span>  |<span data-ttu-id="c2df5-235">자동으로 채워짐</span><span class="sxs-lookup"><span data-stu-id="c2df5-235">Automatically populated</span></span> |<span data-ttu-id="c2df5-236">1 </span><span class="sxs-lookup"><span data-stu-id="c2df5-236">1</span></span>  |<span data-ttu-id="c2df5-237">443</span><span class="sxs-lookup"><span data-stu-id="c2df5-237">443</span></span>   |<span data-ttu-id="c2df5-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2df5-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="c2df5-239">100</span><span class="sxs-lookup"><span data-stu-id="c2df5-239">100</span></span> |<span data-ttu-id="c2df5-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c2df5-240">1 Hour</span></span> |
   |<span data-ttu-id="c2df5-241">sipfed.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="c2df5-241">sipfed</span></span>|<span data-ttu-id="c2df5-242">tcp</span><span class="sxs-lookup"><span data-stu-id="c2df5-242">tcp</span></span> |<span data-ttu-id="c2df5-243">자동으로 채워짐</span><span class="sxs-lookup"><span data-stu-id="c2df5-243">Automatically populated</span></span>|<span data-ttu-id="c2df5-244">1 </span><span class="sxs-lookup"><span data-stu-id="c2df5-244">1</span></span> |<span data-ttu-id="c2df5-245">5061</span><span class="sxs-lookup"><span data-stu-id="c2df5-245">5061</span></span> |<span data-ttu-id="c2df5-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2df5-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="c2df5-247">100</span><span class="sxs-lookup"><span data-stu-id="c2df5-247">100</span></span> | <span data-ttu-id="c2df5-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c2df5-248">1 Hour</span></span> |
   
5. <span data-ttu-id="c2df5-249">DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c2df5-250">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c2df5-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c2df5-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2df5-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
