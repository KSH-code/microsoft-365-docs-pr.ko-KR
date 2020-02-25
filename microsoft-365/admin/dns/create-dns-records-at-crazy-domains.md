---
title: Crazy Domains에서 Office 365용 DNS 레코드 만들기
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 5b344ebdc4a4608c27c0a84299ea171391c09ba0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248159"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a><span data-ttu-id="3fd7c-103">Crazy Domains에서 Office 365용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="3fd7c-103">Create DNS records at Crazy Domains for Office 365</span></span>

 <span data-ttu-id="3fd7c-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3fd7c-105">DNS 호스팅 공급자로 Crazy Domains를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3fd7c-106">Crazy Domains에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-106">After you add these records at Crazy Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="3fd7c-107">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3fd7c-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3fd7c-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3fd7c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="3fd7c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3fd7c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3fd7c-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3fd7c-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3fd7c-p104">시작하려면 [이 링크](https://manage.crazydomains.com/members/domains/)를 사용하여 Crazy Domains의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-구성-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="3fd7c-120">**내 계정** 섹션에서 **도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-구성-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="3fd7c-122">**도메인 이름** 페이지의 **도메인** 섹션에서 업데이트 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-구성-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="3fd7c-124">**DNS 설정** 섹션에서 드롭다운 목록 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-구성-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="3fd7c-126">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-구성-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="3fd7c-128">**Add Record(레코드 추가)** 드롭다운 목록에서 **TXT Record(TXT 레코드)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="3fd7c-130">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-130">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="3fd7c-132">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="3fd7c-133">**Sub Domain(하위 도메인)**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-133">**Sub Domain**</span></span>|<span data-ttu-id="3fd7c-134">**Text Record(텍스트 레코드)**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3fd7c-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3fd7c-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3fd7c-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3fd7c-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3fd7c-137">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-137">**Note:** This is an example.</span></span> <span data-ttu-id="3fd7c-138">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="3fd7c-139">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="3fd7c-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="3fd7c-141">**업데이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-141">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="3fd7c-143">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3fd7c-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="3fd7c-145">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-145">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3fd7c-146">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3fd7c-147">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3fd7c-148">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3fd7c-149">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3fd7c-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="3fd7c-153">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3fd7c-153">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="3fd7c-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3fd7c-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3fd7c-p107">시작하려면 [이 링크](https://manage.crazydomains.com/members/domains/)를 사용하여 Crazy Domains의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-구성-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="3fd7c-158">**내 계정** 섹션에서 **도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-구성-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="3fd7c-160">**도메인 이름** 페이지의 **도메인** 섹션에서 업데이트 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-구성-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="3fd7c-162">**DNS 설정** 섹션에서 드롭다운 목록 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-구성-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="3fd7c-164">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-구성-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="3fd7c-166">**레코드 추가:** 드롭다운 목록에서 **MX 레코드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-구성-2-1](../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="3fd7c-168">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-168">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-구성-2-2](../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="3fd7c-170">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="3fd7c-171">(드롭다운 목록에서 **Priority (우선 순위** ) 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="3fd7c-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3fd7c-172">**영역용 메일**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-172">**Mail For Zone**</span></span>|<span data-ttu-id="3fd7c-173">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-173">**Priority**</span></span>|<span data-ttu-id="3fd7c-174">**서버에 할당**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3fd7c-175">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="3fd7c-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3fd7c-176">개</span><span class="sxs-lookup"><span data-stu-id="3fd7c-176">1</span></span>  <br/> <span data-ttu-id="3fd7c-177">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="3fd7c-178">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3fd7c-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3fd7c-179">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-179">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="3fd7c-180">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="3fd7c-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-구성-2-3](../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="3fd7c-182">**업데이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-182">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-구성-2-4](../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="3fd7c-184">**Mx 레코드** 구역에 다른 mx 레코드가 나열 되어 있으면 해당 레코드 중 하나에 대해 **수정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-구성-2-5](../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="3fd7c-186">**삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-구성-2-6](../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="3fd7c-188">**업데이트** 를 선택 하 여 삭제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-구성-2-7](../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="3fd7c-190">이 절차의 앞에서 추가한 MX 레코드만 남을 때까지 목록에 있는 다른 MX 레코드를 동일한 방법으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="3fd7c-191">Office 365에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3fd7c-191">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="3fd7c-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3fd7c-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3fd7c-p109">시작하려면 [이 링크](https://manage.crazydomains.com/members/domains/)를 사용하여 Crazy Domains의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-구성-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="3fd7c-196">**내 계정** 섹션에서 **도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-구성-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="3fd7c-198">**도메인 이름** 페이지의 **도메인** 섹션에서 업데이트 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-구성-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="3fd7c-200">**DNS 설정** 섹션에서 드롭다운 목록 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-구성-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="3fd7c-202">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-구성-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="3fd7c-204">**레코드 추가:** 드롭다운 목록에서 **CNAME 레코드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-구성-3-1](../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="3fd7c-206">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-206">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-구성-3-2](../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="3fd7c-208">6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3fd7c-209">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="3fd7c-210">**Sub Domain(하위 도메인)**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-210">**Sub Domain**</span></span>|<span data-ttu-id="3fd7c-211">**별칭**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3fd7c-212">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3fd7c-212">autodiscover</span></span>  <br/> |<span data-ttu-id="3fd7c-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3fd7c-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="3fd7c-214">sip</span><span class="sxs-lookup"><span data-stu-id="3fd7c-214">sip</span></span>  <br/> |<span data-ttu-id="3fd7c-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3fd7c-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3fd7c-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3fd7c-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3fd7c-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3fd7c-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3fd7c-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3fd7c-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3fd7c-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3fd7c-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="3fd7c-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3fd7c-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3fd7c-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3fd7c-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-구성-3-3](../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="3fd7c-223">**CNAME 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-구성-3-4](../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="3fd7c-225">두 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="3fd7c-226">새 레코드의 상자에서 표에 있는 다음 행의 값을 사용한 다음 **CNAME 레코드 추가**를 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="3fd7c-227">6개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="3fd7c-228">**업데이트** 를 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-구성-3-5](../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3fd7c-230">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3fd7c-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3fd7c-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3fd7c-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fd7c-232">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3fd7c-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3fd7c-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="3fd7c-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="3fd7c-p111">시작하려면 [이 링크](https://manage.crazydomains.com/members/domains/)를 사용하여 Crazy Domains의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-구성-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="3fd7c-239">**내 계정** 섹션에서 **도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-구성-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="3fd7c-241">**도메인 이름** 페이지의 **도메인** 섹션에서 업데이트 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-구성-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="3fd7c-243">**DNS 설정** 섹션에서 드롭다운 목록 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-구성-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="3fd7c-245">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-구성-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="3fd7c-247">**레코드 추가:** 드롭다운 목록에서 **TXT 레코드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-구성-4-1](../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="3fd7c-249">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-249">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-구성-4-2](../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="3fd7c-251">새 레코드의 상자에서 다음 표의 값을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="3fd7c-252">**Sub Domain(하위 도메인)**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-252">**Sub Domain**</span></span>|<span data-ttu-id="3fd7c-253">**Text Record(텍스트 레코드)**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3fd7c-254">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="3fd7c-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3fd7c-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3fd7c-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3fd7c-256">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-구성-4-3](../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="3fd7c-258">**업데이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-258">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-구성-4-4](../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="3fd7c-260">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3fd7c-260">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="3fd7c-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3fd7c-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3fd7c-p112">시작하려면 [이 링크](https://manage.crazydomains.com/members/domains/)를 사용하여 Crazy Domains의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-구성-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="3fd7c-265">**내 계정** 섹션에서 **도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-구성-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="3fd7c-267">**도메인 이름** 페이지의 **도메인** 섹션에서 업데이트 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-구성-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="3fd7c-269">**DNS 설정** 섹션에서 드롭다운 목록 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-구성-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="3fd7c-271">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-구성-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="3fd7c-273">**레코드 추가:** 드롭다운 목록에서 **SRV 레코드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-구성-5-1](../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="3fd7c-275">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-275">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-구성-5-2](../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="3fd7c-277">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3fd7c-278">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="3fd7c-279">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-279">**Record Type**</span></span>|<span data-ttu-id="3fd7c-280">**Sub Domain(하위 도메인)**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-280">**Sub Domain**</span></span>|<span data-ttu-id="3fd7c-281">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-281">**Priority**</span></span>|<span data-ttu-id="3fd7c-282">**가중치**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-282">**Weight**</span></span>|<span data-ttu-id="3fd7c-283">**포트**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-283">**Port**</span></span>|<span data-ttu-id="3fd7c-284">**대상**</span><span class="sxs-lookup"><span data-stu-id="3fd7c-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3fd7c-285">SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="3fd7c-285">SRV Record</span></span>  <br/> |<span data-ttu-id="3fd7c-286">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="3fd7c-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="3fd7c-287">100</span><span class="sxs-lookup"><span data-stu-id="3fd7c-287">100</span></span>  <br/> |<span data-ttu-id="3fd7c-288">개</span><span class="sxs-lookup"><span data-stu-id="3fd7c-288">1</span></span>  <br/> |<span data-ttu-id="3fd7c-289">443</span><span class="sxs-lookup"><span data-stu-id="3fd7c-289">443</span></span>  <br/> |<span data-ttu-id="3fd7c-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3fd7c-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3fd7c-291">SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="3fd7c-291">SRV Record</span></span>  <br/> |<span data-ttu-id="3fd7c-292">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="3fd7c-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="3fd7c-293">100</span><span class="sxs-lookup"><span data-stu-id="3fd7c-293">100</span></span>  <br/> |<span data-ttu-id="3fd7c-294">개</span><span class="sxs-lookup"><span data-stu-id="3fd7c-294">1</span></span>  <br/> |<span data-ttu-id="3fd7c-295">5061</span><span class="sxs-lookup"><span data-stu-id="3fd7c-295">5061</span></span>  <br/> |<span data-ttu-id="3fd7c-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3fd7c-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-구성-5-3](../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="3fd7c-298">**SRV 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-구성-5-4](../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="3fd7c-300">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3fd7c-301">새 레코드의 상자에서 표에 있는 두 번째 행의 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="3fd7c-302">**업데이트** 를 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-구성-5-5](../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="3fd7c-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fd7c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
