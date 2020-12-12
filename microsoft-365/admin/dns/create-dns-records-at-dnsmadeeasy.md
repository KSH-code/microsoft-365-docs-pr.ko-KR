---
title: MICROSOFT용 DNSMadeEasy에서 DNS 레코드 만들기
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Microsoft용 DNSMadeEasy에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 719b416564447b3a6f4108b747ae921b4f6f6bb8
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657951"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="b2e99-103">MICROSOFT용 DNSMadeEasy에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="b2e99-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="b2e99-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2e99-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b2e99-105">DNS 호스팅 공급자로 DNSMadeEasy를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b2e99-106">DNSMadeEasy에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="b2e99-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b2e99-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b2e99-108">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b2e99-109">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2e99-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b2e99-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="b2e99-110">Add a TXT record for verification</span></span>
<span data-ttu-id="b2e99-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b2e99-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b2e99-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2e99-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b2e99-116">DNSMadeEasy 계정의 경우 추가한 도메인은 별도의 도메인 등록 기관에서 구매한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="b2e99-117">DNSMadeEasy는 도메인 등록 서비스를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="b2e99-118">DNSMadeEasy에서 로그인하고 DNS 레코드를 만드는 기능은 소유권의 충분한 증명이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="b2e99-119">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="b2e99-120">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b2e99-121">관리 콘솔 **페이지의** **최근에** 업데이트된 도메인 영역에서 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="b2e99-122">관리되는 **DNS** 페이지의 **TXT 레코드** 영역에서 ( **+** ) 컨트롤(새 **추가)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="b2e99-123">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b2e99-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="b2e99-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b2e99-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="b2e99-125">**이름**</span><span class="sxs-lookup"><span data-stu-id="b2e99-125">**Name**</span></span> <br/> |<span data-ttu-id="b2e99-126">**Value(값)**</span><span class="sxs-lookup"><span data-stu-id="b2e99-126">**Value**</span></span> <br/> |<span data-ttu-id="b2e99-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b2e99-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="b2e99-128">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="b2e99-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b2e99-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b2e99-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b2e99-130">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-130">**Note:** This is an example.</span></span> <span data-ttu-id="b2e99-131">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b2e99-132">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="b2e99-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b2e99-133">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="b2e99-134">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="b2e99-135">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b2e99-136">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b2e99-137">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b2e99-138">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b2e99-139">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b2e99-140">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b2e99-141">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b2e99-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b2e99-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b2e99-143">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b2e99-144">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2e99-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b2e99-145">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="b2e99-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b2e99-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b2e99-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b2e99-p108">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b2e99-149">관리 콘솔 **페이지의** **최근에** 업데이트된 도메인 영역에서 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="b2e99-150">관리 콘솔 **페이지의** **최근에** 업데이트된 도메인 영역에서 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="b2e99-152">관리되는 **DNS 페이지의** **MX 레코드** 영역에서 **(+) 컨트롤(새** **추가)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="b2e99-153">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b2e99-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="b2e99-155">**MX 레코드 추가** 영역의 새 레코드용 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b2e99-156">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b2e99-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="b2e99-157">**이름**</span><span class="sxs-lookup"><span data-stu-id="b2e99-157">**Name**</span></span>|<span data-ttu-id="b2e99-158">**서버**</span><span class="sxs-lookup"><span data-stu-id="b2e99-158">**Server**</span></span>|<span data-ttu-id="b2e99-159">**MX 수준**</span><span class="sxs-lookup"><span data-stu-id="b2e99-159">**MX Level**</span></span>|<span data-ttu-id="b2e99-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b2e99-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b2e99-161">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="b2e99-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="b2e99-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b2e99-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b2e99-163">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="b2e99-164">**참고:** Microsoft 계정에서 \<*domain-key*\>을(를) 받으세요.</span><span class="sxs-lookup"><span data-stu-id="b2e99-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="b2e99-165">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="b2e99-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b2e99-166">10 </span><span class="sxs-lookup"><span data-stu-id="b2e99-166">10</span></span>  <br/> <span data-ttu-id="b2e99-167">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2e99-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="b2e99-168">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="b2e99-170">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="b2e99-172">**MX 레코드** 구역에 다른 MX 레코드가 나열되어 있으면 하나씩 선택하여 모두 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="b2e99-174">모든 레코드를 선택하면 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="b2e99-176">**MX** 레코드 삭제 대화 상자에서 **삭제를** 선택하여 변경 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b2e99-178">Microsoft에 필요한 5개의 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="b2e99-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b2e99-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b2e99-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b2e99-p110">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b2e99-182">관리 콘솔 **페이지의** **최근에** 업데이트된 도메인 영역에서 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="b2e99-183">관리되는 **DNS** 페이지의 **CNAME 레코드** 영역에서 **(+) 컨트롤(새** **추가)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="b2e99-184">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b2e99-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="b2e99-186">5개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="b2e99-187">**CNAME 레코드 추가** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="b2e99-188">**이름**</span><span class="sxs-lookup"><span data-stu-id="b2e99-188">**Name**</span></span>|<span data-ttu-id="b2e99-189">**별칭 대상**</span><span class="sxs-lookup"><span data-stu-id="b2e99-189">**Alias to**</span></span>|<span data-ttu-id="b2e99-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b2e99-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b2e99-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b2e99-191">autodiscover</span></span>  <br/> |<span data-ttu-id="b2e99-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b2e99-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="b2e99-193">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b2e99-194">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-194">1800</span></span>  <br/> |
    |<span data-ttu-id="b2e99-195">sip</span><span class="sxs-lookup"><span data-stu-id="b2e99-195">sip</span></span>  <br/> |<span data-ttu-id="b2e99-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b2e99-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b2e99-197">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b2e99-198">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-198">1800</span></span>  <br/> |
    |<span data-ttu-id="b2e99-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b2e99-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b2e99-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b2e99-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b2e99-201">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b2e99-202">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-202">1800</span></span>  <br/> |
    |<span data-ttu-id="b2e99-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b2e99-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b2e99-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="b2e99-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="b2e99-205">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b2e99-206">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-206">1800</span></span>  <br/> |
    |<span data-ttu-id="b2e99-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b2e99-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b2e99-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b2e99-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="b2e99-209">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b2e99-210">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="b2e99-212">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="b2e99-214">다른 4개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="b2e99-215">**CNAME 레코드** 섹션에서 **(+) 컨트롤(새** **추가)을** 선택하고 표의 다음 행 값을 사용하여 레코드를 만든 다음 **제출을** 다시 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="b2e99-216">5개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b2e99-217">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="b2e99-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b2e99-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b2e99-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2e99-219">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b2e99-220">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b2e99-221">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b2e99-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b2e99-222">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="b2e99-223">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="b2e99-223">Need examples?</span></span> <span data-ttu-id="b2e99-224">[Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2e99-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="b2e99-225">SPF 레코드의 유효성을 검사하기 위해 다음 SPF 유효성 검사 도구 중[하나를 사용할 수 있습니다.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="b2e99-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="b2e99-226">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="b2e99-227">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b2e99-228">관리 콘솔 **페이지의** **최근에** 업데이트된 도메인 영역에서 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="b2e99-229">관리되는 **DNS** 페이지의 **TXT 레코드** 영역에서 **(+) 컨트롤(새** **추가)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="b2e99-230">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b2e99-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="b2e99-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b2e99-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="b2e99-233">**이름**</span><span class="sxs-lookup"><span data-stu-id="b2e99-233">**Name**</span></span>|<span data-ttu-id="b2e99-234">**Value(값)**</span><span class="sxs-lookup"><span data-stu-id="b2e99-234">**Value**</span></span>|<span data-ttu-id="b2e99-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b2e99-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b2e99-236">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="b2e99-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b2e99-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b2e99-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b2e99-238">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="b2e99-239">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="b2e99-241">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b2e99-243">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="b2e99-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b2e99-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b2e99-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="b2e99-p113">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b2e99-247">관리 콘솔 **페이지의** **최근에** 업데이트된 도메인 영역에서 업데이트할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="b2e99-248">관리되는 **DNS** 페이지의 **SRV 레코드** 영역에서 **(+) 컨트롤(새** **추가)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="b2e99-249">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b2e99-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="b2e99-251">2개의 SRV 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="b2e99-252">**SRV 레코드 추가** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="b2e99-253">**이름**</span><span class="sxs-lookup"><span data-stu-id="b2e99-253">**Name**</span></span>|<span data-ttu-id="b2e99-254">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="b2e99-254">**Priority**</span></span>|<span data-ttu-id="b2e99-255">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="b2e99-255">**Weight**</span></span>|<span data-ttu-id="b2e99-256">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="b2e99-256">**Port**</span></span>|<span data-ttu-id="b2e99-257">**호스트**</span><span class="sxs-lookup"><span data-stu-id="b2e99-257">**Host**</span></span>|<span data-ttu-id="b2e99-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b2e99-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b2e99-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="b2e99-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="b2e99-260">100</span><span class="sxs-lookup"><span data-stu-id="b2e99-260">100</span></span>  <br/> |<span data-ttu-id="b2e99-261">1 </span><span class="sxs-lookup"><span data-stu-id="b2e99-261">1</span></span>  <br/> |<span data-ttu-id="b2e99-262">443</span><span class="sxs-lookup"><span data-stu-id="b2e99-262">443</span></span>  <br/> |<span data-ttu-id="b2e99-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b2e99-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b2e99-264">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b2e99-265">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-265">1800</span></span>  <br/> |
    |<span data-ttu-id="b2e99-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="b2e99-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="b2e99-267">100</span><span class="sxs-lookup"><span data-stu-id="b2e99-267">100</span></span>  <br/> |<span data-ttu-id="b2e99-268">1 </span><span class="sxs-lookup"><span data-stu-id="b2e99-268">1</span></span>  <br/> |<span data-ttu-id="b2e99-269">5061</span><span class="sxs-lookup"><span data-stu-id="b2e99-269">5061</span></span>  <br/> |<span data-ttu-id="b2e99-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b2e99-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="b2e99-271">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2e99-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b2e99-272">1800</span><span class="sxs-lookup"><span data-stu-id="b2e99-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="b2e99-274">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="b2e99-276">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="b2e99-277">**SRV 레코드** 섹션에서 **(+) 컨트롤(새** **추가)을** 선택하고 표의 다음 행 값을 사용하여 레코드를 만든 다음 **제출을** 다시 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b2e99-278">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b2e99-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b2e99-279">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2e99-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b2e99-280">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2e99-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

