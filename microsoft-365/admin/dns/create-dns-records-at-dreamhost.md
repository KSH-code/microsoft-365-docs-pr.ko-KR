---
title: Dreamhost에서 Office 365에 대 한 DNS 레코드 만들기
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Office 365 용 Dreamhost에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 201452bc68f82138c08e2054452747a900ed0e6b
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349489"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="cb568-103">Dreamhost에서 Office 365에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="cb568-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="cb568-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="cb568-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cb568-105">DreamHost이 DNS 호스팅 공급자 인 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, Lync 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="cb568-106">DreamHost에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="cb568-107">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb568-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb568-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb568-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cb568-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cb568-111">Add a TXT record for verification</span></span>
<span data-ttu-id="cb568-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cb568-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cb568-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb568-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cb568-117">시작 하려면 [이 링크](https://panel.dreamhost.com/)를 사용 하 여 DreamHost의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-117">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb568-118">로그인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-118">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-구성-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb568-120">**대시보드** 페이지에서 **도메인**을 선택 하 고 도메인을 **관리**합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-구성-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="cb568-122">도메인 **관리** 페이지의 **도메인** 섹션에서 편집 하려는 도메인의 **DNS** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-구성-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="cb568-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cb568-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cb568-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb568-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb568-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cb568-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cb568-127">**이름**</span><span class="sxs-lookup"><span data-stu-id="cb568-127">**Name**</span></span>|<span data-ttu-id="cb568-128">**종류**</span><span class="sxs-lookup"><span data-stu-id="cb568-128">**Type**</span></span>|<span data-ttu-id="cb568-129">**값**</span><span class="sxs-lookup"><span data-stu-id="cb568-129">**Value**</span></span>|<span data-ttu-id="cb568-130">**설명**</span><span class="sxs-lookup"><span data-stu-id="cb568-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb568-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cb568-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cb568-132">TXT</span><span class="sxs-lookup"><span data-stu-id="cb568-132">TXT</span></span>  <br/> |<span data-ttu-id="cb568-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cb568-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cb568-134">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-134">**Note:** This is an example.</span></span> <span data-ttu-id="cb568-135">여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="cb568-136">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="cb568-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cb568-137">(이 필드는 선택 사항입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb568-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="cb568-139">**지금 레코드 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="cb568-141">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cb568-142">이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="cb568-143">Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cb568-144">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb568-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cb568-145">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cb568-146">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="cb568-147">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="cb568-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb568-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cb568-151">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cb568-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cb568-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cb568-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="cb568-153">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="cb568-154">시작 하려면 [이 링크](https://panel.dreamhost.com/)를 사용 하 여 DreamHost의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-154">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb568-155">로그인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-155">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-구성-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb568-157">**대시보드** 페이지에서 **메일**, **사용자 지정 MX**를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-구성-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="cb568-159">**메일 배달 관리** 섹션의 **작업** 열에서 편집할 도메인에 대해 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-구성-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="cb568-161">**사용자 지정 MX 레코드** 구역의 새 레코드 용 상자에 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="cb568-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb568-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb568-163">기존의 다른 MX 레코드가 있는 경우 해당 레코드를 삭제 하도록 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="cb568-164">**MX 레코드 (필수)**</span><span class="sxs-lookup"><span data-stu-id="cb568-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="cb568-165">0  *\<도메인 키\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cb568-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="cb568-166">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="cb568-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="cb568-p108">0은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  </span><span class="sxs-lookup"><span data-stu-id="cb568-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="cb568-169">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="cb568-170">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="cb568-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-구성-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="cb568-172">**지금 사용자 지정 MX 레코드를 사용 하려면이 도메인 변경을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="cb568-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-구성-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="cb568-174">기존의 다른 MX 레코드가 있는 경우에는 항목을 선택한 다음 키보드에서 **delete** 키를 눌러 각 레코드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-구성-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="cb568-176">레코드를 모두 삭제 한 경우 **지금 사용자 지정 MX 레코드 업데이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-구성-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cb568-178">Office 365에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cb568-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="cb568-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cb568-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="cb568-180">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="cb568-181">시작 하려면 [이 링크](https://panel.dreamhost.com/)를 사용 하 여 DreamHost의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-181">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb568-182">로그인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-182">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-구성-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb568-184">**대시보드** 페이지에서 **도메인**을 선택 하 고 도메인을 **관리**합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-구성-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="cb568-186">도메인 **관리** 페이지의 **도메인** 섹션에서 편집 하려는 도메인의 **DNS** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-구성-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="cb568-188">**사용자 지정 DNS 레코드 추가** 구역의 새 레코드 용 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cb568-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb568-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb568-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cb568-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cb568-191">**이름**</span><span class="sxs-lookup"><span data-stu-id="cb568-191">**Name**</span></span>|<span data-ttu-id="cb568-192">**종류**</span><span class="sxs-lookup"><span data-stu-id="cb568-192">**Type**</span></span>|<span data-ttu-id="cb568-193">**값**</span><span class="sxs-lookup"><span data-stu-id="cb568-193">**Value**</span></span>|<span data-ttu-id="cb568-194">**설명**</span><span class="sxs-lookup"><span data-stu-id="cb568-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb568-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cb568-195">autodiscover</span></span>  <br/> |<span data-ttu-id="cb568-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb568-196">CNAME</span></span>  <br/> |<span data-ttu-id="cb568-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cb568-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="cb568-198">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cb568-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb568-199">(이 필드는 선택 사항입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb568-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb568-200">sip</span><span class="sxs-lookup"><span data-stu-id="cb568-200">sip</span></span>  <br/> |<span data-ttu-id="cb568-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb568-201">CNAME</span></span>  <br/> |<span data-ttu-id="cb568-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cb568-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb568-203">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cb568-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb568-204">(이 필드는 선택 사항입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb568-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb568-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cb568-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cb568-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb568-206">CNAME</span></span>  <br/> |<span data-ttu-id="cb568-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cb568-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb568-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cb568-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb568-209">(이 필드는 선택 사항입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb568-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb568-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cb568-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cb568-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb568-211">CNAME</span></span>  <br/> |<span data-ttu-id="cb568-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cb568-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="cb568-213">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cb568-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb568-214">(이 필드는 선택 사항입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb568-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb568-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cb568-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cb568-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb568-216">CNAME</span></span>  <br/> |<span data-ttu-id="cb568-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cb568-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="cb568-218">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cb568-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb568-219">(이 필드는 선택 사항입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb568-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-구성-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="cb568-221">**지금 레코드 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-구성-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="cb568-223">위의 두 단계와 표에 있는 나머지 다섯 개 행의 값을 사용 하 여 나머지 5 개의 CNAME 레코드를 각각 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cb568-224">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cb568-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cb568-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cb568-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb568-226">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cb568-227">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cb568-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb568-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cb568-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="cb568-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="cb568-230">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="cb568-231">시작 하려면 [이 링크](https://panel.dreamhost.com/)를 사용 하 여 DreamHost의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-231">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb568-232">로그인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-232">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-구성-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb568-234">**대시보드** 페이지에서 **도메인**을 선택 하 고 도메인을 **관리**합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-구성-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="cb568-236">도메인 **관리** 페이지의 **도메인** 섹션에서 편집 하려는 도메인의 **DNS** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-구성-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="cb568-238">**사용자 지정 DNS 레코드 추가** 구역의 새 레코드 용 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cb568-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb568-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb568-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cb568-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cb568-241">**이름**</span><span class="sxs-lookup"><span data-stu-id="cb568-241">**Name**</span></span>|<span data-ttu-id="cb568-242">**종류**</span><span class="sxs-lookup"><span data-stu-id="cb568-242">**Type**</span></span>|<span data-ttu-id="cb568-243">**값**</span><span class="sxs-lookup"><span data-stu-id="cb568-243">**Value**</span></span>|<span data-ttu-id="cb568-244">**설명**</span><span class="sxs-lookup"><span data-stu-id="cb568-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb568-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cb568-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cb568-246">TXT</span><span class="sxs-lookup"><span data-stu-id="cb568-246">TXT</span></span>  <br/> |<span data-ttu-id="cb568-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cb568-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cb568-248">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="cb568-249">(이 필드는 선택 사항입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb568-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-구성-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="cb568-251">**지금 레코드 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-구성-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="cb568-253">위의 두 단계와 표에 있는 두 번째 행의 값을 사용 하 여 다른 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cb568-254">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cb568-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="cb568-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cb568-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="cb568-256">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="cb568-257">시작 하려면 [이 링크](https://panel.dreamhost.com/)를 사용 하 여 DreamHost의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-257">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="cb568-258">로그인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-258">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-구성-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="cb568-260">**대시보드** 페이지에서 **도메인**을 선택 하 고 도메인을 **관리**합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-구성-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="cb568-262">도메인 **관리** 페이지의 **도메인** 섹션에서 편집 하려는 도메인의 **DNS** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-구성-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="cb568-264">**사용자 지정 DNS 레코드 추가** 구역의 새 레코드 용 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cb568-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb568-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cb568-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cb568-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cb568-267">**이름**</span><span class="sxs-lookup"><span data-stu-id="cb568-267">**Name**</span></span>|<span data-ttu-id="cb568-268">**종류**</span><span class="sxs-lookup"><span data-stu-id="cb568-268">**Type**</span></span>|<span data-ttu-id="cb568-269">**값**</span><span class="sxs-lookup"><span data-stu-id="cb568-269">**Value**</span></span>|<span data-ttu-id="cb568-270">**설명**</span><span class="sxs-lookup"><span data-stu-id="cb568-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb568-271">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="cb568-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="cb568-272">SRV</span><span class="sxs-lookup"><span data-stu-id="cb568-272">SRV</span></span>  <br/> |<span data-ttu-id="cb568-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="cb568-273">100 1 443</span></span>  <br/> <span data-ttu-id="cb568-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cb568-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb568-275">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cb568-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb568-276">(이 필드는 선택 사항입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb568-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="cb568-277">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="cb568-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="cb568-278">SRV</span><span class="sxs-lookup"><span data-stu-id="cb568-278">SRV</span></span>  <br/> |<span data-ttu-id="cb568-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="cb568-279">100 1 5061</span></span>  <br/> <span data-ttu-id="cb568-280">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cb568-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb568-281">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="cb568-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb568-282">(이 필드는 선택 사항입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb568-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-구성-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="cb568-284">**지금 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-구성-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="cb568-286">위의 두 단계와 표에 있는 두 번째 행의 값을 사용 하 여 다른 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb568-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="cb568-p114">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb568-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
