---
title: Names.co.uk에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 Names.co.uk에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 2552017e06001c0b28605558b823fdb4c670ef8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629326"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="eee2c-103">Names.co.uk에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="eee2c-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="eee2c-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="eee2c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="eee2c-105">DNS 호스팅 공급자로 Names.co.uk를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="eee2c-106">Names.co.uk에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="eee2c-107">Microsoft의 웹 사이트에 대 한 호스트 및 DNS에 대 한 자세한 내용은 [microsoft에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eee2c-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="eee2c-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eee2c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="eee2c-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="eee2c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="eee2c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="eee2c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="eee2c-113">Microsoft에서 도메인을 사용 하기 전에 사용자가 소유 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="eee2c-114">도메인 등록 기관에서 계정에 로그인 하 고 DNS 레코드를 만들 수 있는 기능은 Microsoft에 도메인을 소유 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eee2c-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="eee2c-p104">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-구성-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="eee2c-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="eee2c-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="eee2c-121">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-121">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-구성-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="eee2c-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eee2c-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="eee2c-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="eee2c-125">행을 추가 해야 하는 경우 **a/CNAME 레코드 추가 (+)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="eee2c-126">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="eee2c-127">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="eee2c-127">**Host name**</span></span>|<span data-ttu-id="eee2c-128">**종류**</span><span class="sxs-lookup"><span data-stu-id="eee2c-128">**Type**</span></span>|<span data-ttu-id="eee2c-129">**결과**</span><span class="sxs-lookup"><span data-stu-id="eee2c-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="eee2c-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eee2c-131">TXT</span><span class="sxs-lookup"><span data-stu-id="eee2c-131">TXT</span></span>  <br/> |<span data-ttu-id="eee2c-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="eee2c-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="eee2c-133">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-133">**Note:** This is an example.</span></span> <span data-ttu-id="eee2c-134">표에서 특정 **대상 또는 지점** 값을 사용 하 여 여기서 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="eee2c-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="eee2c-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="eee2c-137">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-137">Select **Save**.</span></span>
    
    <span data-ttu-id="eee2c-138">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-138">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="eee2c-140">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="eee2c-141">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="eee2c-142">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="eee2c-143">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="eee2c-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="eee2c-144">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="eee2c-145">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="eee2c-146">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="eee2c-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eee2c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="eee2c-150">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="eee2c-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="eee2c-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="eee2c-p107">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-구성-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="eee2c-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="eee2c-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="eee2c-156">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-156">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-구성-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="eee2c-158">**DNS 영역 추가/수정** 페이지의 **메일 교환 레코드** 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="eee2c-159">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="eee2c-160">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="eee2c-160">**Host name**</span></span>|<span data-ttu-id="eee2c-161">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="eee2c-161">**Priority**</span></span>|<span data-ttu-id="eee2c-162">**결과**</span><span class="sxs-lookup"><span data-stu-id="eee2c-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="eee2c-163">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eee2c-164">1 </span><span class="sxs-lookup"><span data-stu-id="eee2c-164">1</span></span>  <br/> <span data-ttu-id="eee2c-165">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eee2c-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="eee2c-166">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eee2c-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="eee2c-167">> [!NOTE]> Microsoft 계정에서 \* \<도메인 키\> \* 를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="eee2c-168">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="eee2c-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-구성-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="eee2c-170">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-170">Select **Save**.</span></span>
    
    <span data-ttu-id="eee2c-171">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-171">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-구성-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="eee2c-173">**메일 교환 레코드** 구역에 나열된 다른 MX 레코드가 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-구성-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="eee2c-175">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-175">Select **Save**.</span></span>
    
    <span data-ttu-id="eee2c-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-176">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-구성-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="eee2c-178">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="eee2c-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="eee2c-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="eee2c-p109">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-구성-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="eee2c-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="eee2c-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="eee2c-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-184">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-구성-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="eee2c-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eee2c-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="eee2c-187">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="eee2c-188">행을 추가 해야 하는 경우 **a/CNAME 레코드 추가 (+)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="eee2c-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="eee2c-190">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="eee2c-190">**Host Name**</span></span>|<span data-ttu-id="eee2c-191">**종류**</span><span class="sxs-lookup"><span data-stu-id="eee2c-191">**Type**</span></span>|<span data-ttu-id="eee2c-192">**결과**</span><span class="sxs-lookup"><span data-stu-id="eee2c-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="eee2c-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="eee2c-193">autodiscover</span></span>  <br/> |<span data-ttu-id="eee2c-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="eee2c-194">CNAME</span></span>  <br/> |<span data-ttu-id="eee2c-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eee2c-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="eee2c-196">sip</span><span class="sxs-lookup"><span data-stu-id="eee2c-196">sip</span></span>  <br/> |<span data-ttu-id="eee2c-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="eee2c-197">CNAME</span></span>  <br/> |<span data-ttu-id="eee2c-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eee2c-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="eee2c-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eee2c-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="eee2c-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="eee2c-200">CNAME</span></span>  <br/> |<span data-ttu-id="eee2c-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eee2c-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="eee2c-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="eee2c-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="eee2c-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="eee2c-203">CNAME</span></span>  <br/> |<span data-ttu-id="eee2c-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="eee2c-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="eee2c-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="eee2c-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="eee2c-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="eee2c-206">CNAME</span></span>  <br/> |<span data-ttu-id="eee2c-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="eee2c-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-구성-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="eee2c-209">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-209">Select **Save**.</span></span>
    
    ![NamesUK-BP-구성-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="eee2c-211">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="eee2c-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="eee2c-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="eee2c-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="eee2c-213">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="eee2c-214">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="eee2c-215">도메인에 대 한 SPF 레코드가 이미 있는 경우 Microsoft에 대해 새로 만들지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="eee2c-215">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="eee2c-216">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-216">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="eee2c-p111">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-구성-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="eee2c-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="eee2c-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="eee2c-221">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-221">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-구성-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="eee2c-223">**계정에 DNS 영역** 페이지의 **Domain name (도메인 이름** ) 열에서 업데이트 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-구성-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="eee2c-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eee2c-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="eee2c-226">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="eee2c-227">행을 추가 해야 하는 경우 **a/CNAME 레코드 추가 (+)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="eee2c-228">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="eee2c-229">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="eee2c-229">**Host name**</span></span>|<span data-ttu-id="eee2c-230">**종류**</span><span class="sxs-lookup"><span data-stu-id="eee2c-230">**Type**</span></span>|<span data-ttu-id="eee2c-231">**결과**</span><span class="sxs-lookup"><span data-stu-id="eee2c-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="eee2c-232">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eee2c-233">TXT</span><span class="sxs-lookup"><span data-stu-id="eee2c-233">TXT</span></span>  <br/> |<span data-ttu-id="eee2c-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="eee2c-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="eee2c-235">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-구성-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="eee2c-237">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-237">Select **Save**.</span></span>
    
    <span data-ttu-id="eee2c-238">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-238">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-구성-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="eee2c-240">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="eee2c-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="eee2c-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="eee2c-p112">시작하려면 [이 링크](https://account.names.co.uk/dashboard#/)를 사용하여 Names.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-구성-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="eee2c-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="eee2c-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="eee2c-246">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-246">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-구성-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="eee2c-248">**DNS 영역 추가/수정** 페이지의 **서비스 레코드** 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="eee2c-249">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="eee2c-250">**이름**</span><span class="sxs-lookup"><span data-stu-id="eee2c-250">**Name**</span></span>|<span data-ttu-id="eee2c-251">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="eee2c-251">**Priority**</span></span>|<span data-ttu-id="eee2c-252">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="eee2c-252">**Weight**</span></span>|<span data-ttu-id="eee2c-253">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="eee2c-253">**Port**</span></span>|<span data-ttu-id="eee2c-254">**결과**</span><span class="sxs-lookup"><span data-stu-id="eee2c-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eee2c-255">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="eee2c-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="eee2c-256">100</span><span class="sxs-lookup"><span data-stu-id="eee2c-256">100</span></span>  <br/> |<span data-ttu-id="eee2c-257">1 </span><span class="sxs-lookup"><span data-stu-id="eee2c-257">1</span></span>  <br/> |<span data-ttu-id="eee2c-258">443</span><span class="sxs-lookup"><span data-stu-id="eee2c-258">443</span></span>  <br/> |<span data-ttu-id="eee2c-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eee2c-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="eee2c-260">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="eee2c-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="eee2c-261">100</span><span class="sxs-lookup"><span data-stu-id="eee2c-261">100</span></span>  <br/> |<span data-ttu-id="eee2c-262">1 </span><span class="sxs-lookup"><span data-stu-id="eee2c-262">1</span></span>  <br/> |<span data-ttu-id="eee2c-263">5061</span><span class="sxs-lookup"><span data-stu-id="eee2c-263">5061</span></span>  <br/> |<span data-ttu-id="eee2c-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eee2c-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-구성-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="eee2c-266">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee2c-266">Select **Save**.</span></span>
    
    <span data-ttu-id="eee2c-267">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="eee2c-267">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-구성-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="eee2c-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eee2c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
