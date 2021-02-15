---
title: Microsoft용 NAMES.CO.UK DNS 레코드 만들기
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Microsoft에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 Names.co.uk 방법을 배워보아야 합니다.
ms.openlocfilehash: 51dc9b3271468d42e82f98a1b85de5104416b015
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657818"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="d8f81-103">Microsoft용 NAMES.CO.UK DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="d8f81-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="d8f81-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f81-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d8f81-105">DNS 호스팅 공급자로 Names.co.uk를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="d8f81-106">새 도메인에서 이러한 레코드를 Names.co.uk Microsoft 서비스에서 작동 하게 도메인이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="d8f81-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d8f81-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d8f81-110">Add a TXT record for verification</span></span>
<span data-ttu-id="d8f81-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d8f81-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d8f81-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8f81-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d8f81-p104">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8f81-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8f81-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8f81-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8f81-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d8f81-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8f81-123">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d8f81-124">행을 추가해야 하는 경우 **A/CNAME 레코드 추가(+)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d8f81-125">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="d8f81-126">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f81-126">**Host name**</span></span>|<span data-ttu-id="d8f81-127">**종류**</span><span class="sxs-lookup"><span data-stu-id="d8f81-127">**Type**</span></span>|<span data-ttu-id="d8f81-128">**결과**</span><span class="sxs-lookup"><span data-stu-id="d8f81-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d8f81-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d8f81-130">TXT</span><span class="sxs-lookup"><span data-stu-id="d8f81-130">TXT</span></span>  <br/> |<span data-ttu-id="d8f81-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d8f81-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d8f81-132">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-132">**Note:** This is an example.</span></span> <span data-ttu-id="d8f81-133">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d8f81-134">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="d8f81-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="d8f81-136">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-136">Select **Save**.</span></span>
    
    <span data-ttu-id="d8f81-137">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="d8f81-139">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d8f81-140">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d8f81-141">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d8f81-142">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8f81-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d8f81-143">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d8f81-144">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d8f81-145">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d8f81-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d8f81-149">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="d8f81-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d8f81-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d8f81-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d8f81-p107">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8f81-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8f81-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8f81-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8f81-157">**DNS 영역 추가/수정** 페이지의 **메일 교환 레코드** 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8f81-158">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d8f81-159">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f81-159">**Host name**</span></span>|<span data-ttu-id="d8f81-160">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="d8f81-160">**Priority**</span></span>|<span data-ttu-id="d8f81-161">**결과**</span><span class="sxs-lookup"><span data-stu-id="d8f81-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d8f81-162">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d8f81-163">1 </span><span class="sxs-lookup"><span data-stu-id="d8f81-163">1</span></span>  <br/> <span data-ttu-id="d8f81-164">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f81-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="d8f81-165">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d8f81-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d8f81-166">> [!NOTE]>  *\<domain-key\>*  Microsoft 계정에서 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f81-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="d8f81-167">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="d8f81-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="d8f81-169">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-169">Select **Save**.</span></span>
    
    <span data-ttu-id="d8f81-170">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="d8f81-172">**메일 교환 레코드** 구역에 나열된 다른 MX 레코드가 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="d8f81-174">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-174">Select **Save**.</span></span>
    
    <span data-ttu-id="d8f81-175">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d8f81-177">Microsoft에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d8f81-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d8f81-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d8f81-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d8f81-p109">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8f81-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8f81-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8f81-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8f81-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d8f81-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8f81-186">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d8f81-187">행을 추가해야 하는 경우 **A/CNAME 레코드 추가(+)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d8f81-188">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d8f81-189">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f81-189">**Host Name**</span></span>|<span data-ttu-id="d8f81-190">**종류**</span><span class="sxs-lookup"><span data-stu-id="d8f81-190">**Type**</span></span>|<span data-ttu-id="d8f81-191">**결과**</span><span class="sxs-lookup"><span data-stu-id="d8f81-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d8f81-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d8f81-192">autodiscover</span></span>  <br/> |<span data-ttu-id="d8f81-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8f81-193">CNAME</span></span>  <br/> |<span data-ttu-id="d8f81-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d8f81-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d8f81-195">sip</span><span class="sxs-lookup"><span data-stu-id="d8f81-195">sip</span></span>  <br/> |<span data-ttu-id="d8f81-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8f81-196">CNAME</span></span>  <br/> |<span data-ttu-id="d8f81-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d8f81-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d8f81-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d8f81-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d8f81-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8f81-199">CNAME</span></span>  <br/> |<span data-ttu-id="d8f81-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d8f81-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d8f81-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d8f81-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d8f81-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8f81-202">CNAME</span></span>  <br/> |<span data-ttu-id="d8f81-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d8f81-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d8f81-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d8f81-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d8f81-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8f81-205">CNAME</span></span>  <br/> |<span data-ttu-id="d8f81-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d8f81-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="d8f81-208">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d8f81-210">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d8f81-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d8f81-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d8f81-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8f81-212">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d8f81-213">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d8f81-214">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d8f81-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d8f81-215">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="d8f81-p111">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8f81-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8f81-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8f81-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8f81-222">계정의 **DNS** 영역 페이지의 도메인 **이름** 열에서 업데이트할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="d8f81-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d8f81-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8f81-225">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d8f81-226">행을 추가해야 하는 경우 **A/CNAME 레코드 추가(+)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d8f81-227">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d8f81-228">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f81-228">**Host name**</span></span>|<span data-ttu-id="d8f81-229">**종류**</span><span class="sxs-lookup"><span data-stu-id="d8f81-229">**Type**</span></span>|<span data-ttu-id="d8f81-230">**결과**</span><span class="sxs-lookup"><span data-stu-id="d8f81-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d8f81-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d8f81-232">TXT</span><span class="sxs-lookup"><span data-stu-id="d8f81-232">TXT</span></span>  <br/> |<span data-ttu-id="d8f81-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d8f81-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d8f81-234">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="d8f81-236">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-236">Select **Save**.</span></span>
    
    <span data-ttu-id="d8f81-237">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d8f81-239">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="d8f81-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d8f81-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d8f81-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d8f81-p112">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8f81-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8f81-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8f81-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8f81-247">**DNS 영역 추가/수정** 페이지의 **서비스 레코드** 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8f81-248">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d8f81-249">**이름**</span><span class="sxs-lookup"><span data-stu-id="d8f81-249">**Name**</span></span>|<span data-ttu-id="d8f81-250">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="d8f81-250">**Priority**</span></span>|<span data-ttu-id="d8f81-251">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="d8f81-251">**Weight**</span></span>|<span data-ttu-id="d8f81-252">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="d8f81-252">**Port**</span></span>|<span data-ttu-id="d8f81-253">**결과**</span><span class="sxs-lookup"><span data-stu-id="d8f81-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d8f81-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="d8f81-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="d8f81-255">100</span><span class="sxs-lookup"><span data-stu-id="d8f81-255">100</span></span>  <br/> |<span data-ttu-id="d8f81-256">1 </span><span class="sxs-lookup"><span data-stu-id="d8f81-256">1</span></span>  <br/> |<span data-ttu-id="d8f81-257">443</span><span class="sxs-lookup"><span data-stu-id="d8f81-257">443</span></span>  <br/> |<span data-ttu-id="d8f81-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d8f81-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d8f81-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="d8f81-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="d8f81-260">100</span><span class="sxs-lookup"><span data-stu-id="d8f81-260">100</span></span>  <br/> |<span data-ttu-id="d8f81-261">1 </span><span class="sxs-lookup"><span data-stu-id="d8f81-261">1</span></span>  <br/> |<span data-ttu-id="d8f81-262">5061</span><span class="sxs-lookup"><span data-stu-id="d8f81-262">5061</span></span>  <br/> |<span data-ttu-id="d8f81-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d8f81-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="d8f81-265">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f81-265">Select **Save**.</span></span>
    
    <span data-ttu-id="d8f81-266">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d8f81-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="d8f81-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f81-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
