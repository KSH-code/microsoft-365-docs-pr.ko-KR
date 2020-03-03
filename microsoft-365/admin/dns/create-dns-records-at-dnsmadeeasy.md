---
title: DNSMadeEasy에서 Office 365용 DNS 레코드 만들기
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Office 365 용 DNSMadeEasy에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 82244d216652b1957aefc3b81acd881ea4b32393
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350319"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="8a180-103">DNSMadeEasy에서 Office 365용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="8a180-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="8a180-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a180-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8a180-105">DNS 호스팅 공급자로 DNSMadeEasy를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8a180-106">DNSMadeEasy에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="8a180-107">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a180-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a180-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8a180-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8a180-109">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8a180-110">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a180-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8a180-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8a180-111">Add a TXT record for verification</span></span>
<span data-ttu-id="8a180-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8a180-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8a180-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a180-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8a180-117">DNSMadeEasy 계정의 경우 추가한 도메인은 별도의 도메인 등록 기관에서 구매한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="8a180-118">DNSMadeEasy는 도메인 등록 서비스를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="8a180-119">DNSMadeEasy에서 로그인하고 DNS 레코드를 만드는 기능은 소유권의 충분한 증명이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="8a180-120">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="8a180-121">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="8a180-122">**관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="8a180-123">**관리 되는 DNS** 페이지의 **TXT 레코드** 영역에서 ( **+**) 컨트롤 ( **새로 추가**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="8a180-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8a180-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="8a180-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8a180-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="8a180-126">**이름**</span><span class="sxs-lookup"><span data-stu-id="8a180-126">**Name**</span></span> <br/> |<span data-ttu-id="8a180-127">**Value(값)**</span><span class="sxs-lookup"><span data-stu-id="8a180-127">**Value**</span></span> <br/> |<span data-ttu-id="8a180-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a180-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="8a180-129">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="8a180-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8a180-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8a180-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8a180-131">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-131">**Note:** This is an example.</span></span> <span data-ttu-id="8a180-132">여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="8a180-133">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="8a180-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8a180-134">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="8a180-135">**제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="8a180-136">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8a180-137">이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="8a180-138">Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8a180-139">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a180-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8a180-140">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8a180-141">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8a180-142">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8a180-143">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8a180-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8a180-144">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8a180-145">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a180-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="8a180-146">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8a180-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="8a180-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8a180-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8a180-p108">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="8a180-150">**관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="8a180-151">**관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-구성-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="8a180-153">**관리 되는 DNS** 페이지의 **MX 레코드** 영역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="8a180-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8a180-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-구성-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="8a180-156">**MX 레코드 추가** 영역의 새 레코드용 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8a180-157">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="8a180-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="8a180-158">**이름**</span><span class="sxs-lookup"><span data-stu-id="8a180-158">**Name**</span></span>|<span data-ttu-id="8a180-159">**서버**</span><span class="sxs-lookup"><span data-stu-id="8a180-159">**Server**</span></span>|<span data-ttu-id="8a180-160">**MX 수준**</span><span class="sxs-lookup"><span data-stu-id="8a180-160">**MX Level**</span></span>|<span data-ttu-id="8a180-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a180-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8a180-162">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="8a180-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="8a180-163">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8a180-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8a180-164">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8a180-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="8a180-165">**참고:** Office 365 계정에서 \<*도메인-키*\>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-165">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="8a180-166">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="8a180-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8a180-167">10 </span><span class="sxs-lookup"><span data-stu-id="8a180-167">10</span></span>  <br/> <span data-ttu-id="8a180-168">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a180-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="8a180-169">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-구성-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="8a180-171">**제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-구성-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="8a180-173">**MX 레코드** 구역에 다른 MX 레코드가 나열되어 있으면 하나씩 선택하여 모두 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-구성-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="8a180-175">모든 레코드를 선택 하 고 선택 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-구성-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="8a180-177">**MX 레코드 삭제** 대화 상자에서 **삭제** 를 선택 하 여 변경 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-구성-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="8a180-179">Office 365에 필요한 다섯 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="8a180-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8a180-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="8a180-p110">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="8a180-183">**관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="8a180-184">**관리 되는 DNS** 페이지의 **CNAME 레코드** 영역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="8a180-185">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8a180-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-구성-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="8a180-187">5 개의 CNAME 레코드 중 처음 일부를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="8a180-188">**CNAME 레코드 추가** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="8a180-189">**이름**</span><span class="sxs-lookup"><span data-stu-id="8a180-189">**Name**</span></span>|<span data-ttu-id="8a180-190">**별칭 대상**</span><span class="sxs-lookup"><span data-stu-id="8a180-190">**Alias to**</span></span>|<span data-ttu-id="8a180-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a180-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8a180-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8a180-192">autodiscover</span></span>  <br/> |<span data-ttu-id="8a180-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8a180-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="8a180-194">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8a180-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a180-195">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-195">1800</span></span>  <br/> |
    |<span data-ttu-id="8a180-196">sip</span><span class="sxs-lookup"><span data-stu-id="8a180-196">sip</span></span>  <br/> |<span data-ttu-id="8a180-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a180-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8a180-198">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8a180-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a180-199">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-199">1800</span></span>  <br/> |
    |<span data-ttu-id="8a180-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8a180-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8a180-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a180-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8a180-202">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8a180-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a180-203">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-203">1800</span></span>  <br/> |
    |<span data-ttu-id="8a180-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8a180-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8a180-205">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8a180-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="8a180-206">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8a180-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a180-207">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-207">1800</span></span>  <br/> |
    |<span data-ttu-id="8a180-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8a180-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8a180-209">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8a180-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="8a180-210">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8a180-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a180-211">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-구성-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="8a180-213">**제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-구성-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="8a180-215">나머지 4 개의 CNAME 레코드를 각각 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="8a180-216">**CNAME 레코드** 구역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 하 고 표에 있는 다음 행의 값을 사용 하 여 레코드를 만든 다음 다시 **제출을** 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="8a180-217">5 개의 CNAME 레코드를 모두 만들 때까지이 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8a180-218">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8a180-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8a180-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8a180-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a180-220">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8a180-221">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8a180-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a180-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="8a180-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="8a180-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="8a180-224">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="8a180-224">Need examples?</span></span> <span data-ttu-id="8a180-225">[Office 365에 대한 외부 Domain Name System 레코드](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a180-225">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="8a180-226">SPF 레코드의 유효성을 검사 하기 위해 이러한[spf 유효성 검사 도구](../setup/domains-faq.md)중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="8a180-227">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="8a180-228">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="8a180-229">**관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="8a180-230">**관리 되는 DNS** 페이지의 **TXT 레코드** 영역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="8a180-231">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="8a180-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-구성-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="8a180-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8a180-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="8a180-234">**이름**</span><span class="sxs-lookup"><span data-stu-id="8a180-234">**Name**</span></span>|<span data-ttu-id="8a180-235">**Value(값)**</span><span class="sxs-lookup"><span data-stu-id="8a180-235">**Value**</span></span>|<span data-ttu-id="8a180-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a180-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8a180-237">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="8a180-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8a180-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8a180-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8a180-239">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="8a180-240">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-구성-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="8a180-242">**제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-구성-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="8a180-244">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8a180-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="8a180-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8a180-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="8a180-p113">시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="8a180-248">**관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="8a180-249">**관리 되는 DNS** 페이지의 **SRV 레코드** 영역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="8a180-250">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="8a180-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-구성-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="8a180-252">2개의 SRV 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="8a180-253">**SRV 레코드 추가** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="8a180-254">**이름**</span><span class="sxs-lookup"><span data-stu-id="8a180-254">**Name**</span></span>|<span data-ttu-id="8a180-255">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="8a180-255">**Priority**</span></span>|<span data-ttu-id="8a180-256">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="8a180-256">**Weight**</span></span>|<span data-ttu-id="8a180-257">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="8a180-257">**Port**</span></span>|<span data-ttu-id="8a180-258">**호스트**</span><span class="sxs-lookup"><span data-stu-id="8a180-258">**Host**</span></span>|<span data-ttu-id="8a180-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a180-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8a180-260">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="8a180-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="8a180-261">100</span><span class="sxs-lookup"><span data-stu-id="8a180-261">100</span></span>  <br/> |<span data-ttu-id="8a180-262">개</span><span class="sxs-lookup"><span data-stu-id="8a180-262">1</span></span>  <br/> |<span data-ttu-id="8a180-263">443</span><span class="sxs-lookup"><span data-stu-id="8a180-263">443</span></span>  <br/> |<span data-ttu-id="8a180-264">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a180-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8a180-265">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8a180-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a180-266">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-266">1800</span></span>  <br/> |
    |<span data-ttu-id="8a180-267">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="8a180-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="8a180-268">100</span><span class="sxs-lookup"><span data-stu-id="8a180-268">100</span></span>  <br/> |<span data-ttu-id="8a180-269">개</span><span class="sxs-lookup"><span data-stu-id="8a180-269">1</span></span>  <br/> |<span data-ttu-id="8a180-270">5061</span><span class="sxs-lookup"><span data-stu-id="8a180-270">5061</span></span>  <br/> |<span data-ttu-id="8a180-271">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a180-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="8a180-272">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8a180-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a180-273">1800</span><span class="sxs-lookup"><span data-stu-id="8a180-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-구성-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="8a180-275">**제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-구성-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="8a180-277">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="8a180-278">**SRV 레코드** 구역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 하 고 표에 있는 다음 행의 값을 사용 하 여 레코드를 만든 다음 다시 **제출을** 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8a180-279">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8a180-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8a180-280">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a180-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8a180-281">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a180-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

