---
title: Name.com에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 name.com에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 9183d27641ee22d9e49be2ca04832ab68bc20ace
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919739"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="5a863-103">Name.com에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="5a863-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="5a863-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a863-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5a863-105">DNS 호스팅 공급자로 name.com을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5a863-106">Name.com에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="5a863-107">Microsoft에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Microsoft에서 공개 웹 사이트 사용하기](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a863-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a863-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a863-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5a863-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5a863-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5a863-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5a863-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5a863-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a863-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5a863-p104">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="5a863-120">**내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="5a863-122">**세부 정보** 열에서 **DNS 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-122">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="5a863-124">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="5a863-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5a863-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5a863-126">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5a863-126">**Type**</span></span> <br/> |<span data-ttu-id="5a863-127">**호스트**</span><span class="sxs-lookup"><span data-stu-id="5a863-127">**Host**</span></span> <br/> |<span data-ttu-id="5a863-128">**응답**</span><span class="sxs-lookup"><span data-stu-id="5a863-128">**Answer**</span></span> <br/> |<span data-ttu-id="5a863-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5a863-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="5a863-130">TXT</span><span class="sxs-lookup"><span data-stu-id="5a863-130">TXT</span></span>  <br/> |<span data-ttu-id="5a863-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="5a863-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5a863-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5a863-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5a863-133">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-133">**Note:** This is an example.</span></span> <span data-ttu-id="5a863-134">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="5a863-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="5a863-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5a863-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="5a863-136">Use the default value (300).</span></span>  <br/> |
   
    ![이름-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="5a863-138">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="5a863-140">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5a863-141">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="5a863-142">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5a863-143">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a863-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5a863-144">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5a863-145">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5a863-146">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="5a863-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a863-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5a863-150">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="5a863-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5a863-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5a863-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5a863-p107">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="5a863-155">**내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="5a863-157">**세부 정보** 열에서 **DNS 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="5a863-159">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="5a863-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5a863-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5a863-161">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5a863-161">**Type**</span></span>|<span data-ttu-id="5a863-162">**호스트**</span><span class="sxs-lookup"><span data-stu-id="5a863-162">**Host**</span></span>|<span data-ttu-id="5a863-163">**응답**</span><span class="sxs-lookup"><span data-stu-id="5a863-163">**Answer**</span></span>|<span data-ttu-id="5a863-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5a863-164">**TTL**</span></span>|<span data-ttu-id="5a863-165">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="5a863-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5a863-166">MX</span><span class="sxs-lookup"><span data-stu-id="5a863-166">MX</span></span>  <br/> |<span data-ttu-id="5a863-167">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="5a863-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="5a863-168">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5a863-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5a863-169">**참고:** Microsoft 계정에서 \* \<도메인 키\> \* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="5a863-170">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="5a863-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5a863-171">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="5a863-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="5a863-172">개</span><span class="sxs-lookup"><span data-stu-id="5a863-172">0</span></span>  <br/> <span data-ttu-id="5a863-173">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a863-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![이름-BP-구성-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="5a863-175">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="5a863-177">다른 MX 레코드가 있으면 다음 2단계 절차를 사용하여 각 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="5a863-178">각각의 다른 MX 레코드에 대해 **작업** 열에서 **삭제** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="5a863-180">각 삭제를 확인 하려면 **작업** 열에서 **삭제** 를 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="5a863-182">다른 MX 레코드를 각각 삭제할 때까지 이 2단계 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5a863-183">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="5a863-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5a863-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5a863-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5a863-p109">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="5a863-188">**내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="5a863-190">**세부 정보** 열에서 **DNS 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="5a863-192">첫 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="5a863-193">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. </span><span class="sxs-lookup"><span data-stu-id="5a863-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="5a863-194">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="5a863-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5a863-195">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5a863-195">**Type**</span></span>|<span data-ttu-id="5a863-196">**호스트**</span><span class="sxs-lookup"><span data-stu-id="5a863-196">**Host**</span></span>|<span data-ttu-id="5a863-197">**응답**</span><span class="sxs-lookup"><span data-stu-id="5a863-197">**Answer**</span></span>|<span data-ttu-id="5a863-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5a863-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5a863-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="5a863-199">CNAME</span></span>  <br/> |<span data-ttu-id="5a863-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5a863-200">autodiscover</span></span>  <br/> |<span data-ttu-id="5a863-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5a863-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="5a863-202">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="5a863-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="5a863-203">CNAME</span></span>  <br/> |<span data-ttu-id="5a863-204">sip</span><span class="sxs-lookup"><span data-stu-id="5a863-204">sip</span></span>  <br/> |<span data-ttu-id="5a863-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a863-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5a863-206">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="5a863-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="5a863-207">CNAME</span></span>  <br/> |<span data-ttu-id="5a863-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5a863-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5a863-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a863-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5a863-210">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="5a863-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="5a863-211">CNAME</span></span>  <br/> |<span data-ttu-id="5a863-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5a863-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5a863-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5a863-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="5a863-214">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="5a863-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="5a863-215">CNAME</span></span>  <br/> |<span data-ttu-id="5a863-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5a863-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5a863-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5a863-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="5a863-218">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-218">Use the default value (300).</span></span>  <br/> |
   
   ![이름-BP-구성-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="5a863-220">**레코드 추가** 를 선택 하 여 첫 번째 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="5a863-222">두 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="5a863-223">위 표에 있는 두 번째 행의 값을 사용한 다음 **레코드 추가** 를 선택 하 여 두 번째 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="5a863-224">표의 세 번째, 네 번째, 다섯 번째 및 여섯 번째 행의 값을 사용하여 같은 방법으로 나머지 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5a863-225">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5a863-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5a863-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5a863-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a863-227">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5a863-228">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5a863-229">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5a863-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5a863-230">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="5a863-p111">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="5a863-234">**내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="5a863-236">**세부 정보** 열에서 **DNS 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="5a863-238">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="5a863-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5a863-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5a863-240">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5a863-240">**Type**</span></span>|<span data-ttu-id="5a863-241">**호스트**</span><span class="sxs-lookup"><span data-stu-id="5a863-241">**Host**</span></span>|<span data-ttu-id="5a863-242">**응답**</span><span class="sxs-lookup"><span data-stu-id="5a863-242">**Answer**</span></span>|<span data-ttu-id="5a863-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5a863-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5a863-244">TXT</span><span class="sxs-lookup"><span data-stu-id="5a863-244">TXT</span></span>  <br/> |<span data-ttu-id="5a863-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="5a863-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5a863-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5a863-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5a863-247">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="5a863-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="5a863-248">Use the default value (300).</span></span>  <br/> |
   
   ![이름-BP-구성-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="5a863-250">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5a863-252">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="5a863-252">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5a863-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5a863-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5a863-p112">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="5a863-257">**내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="5a863-259">**세부 정보** 열에서 **DNS 레코드 +** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="5a863-261">첫 번째 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="5a863-262">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="5a863-263">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="5a863-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5a863-264">**유형**</span><span class="sxs-lookup"><span data-stu-id="5a863-264">**Type**</span></span>|<span data-ttu-id="5a863-265">**서비스**</span><span class="sxs-lookup"><span data-stu-id="5a863-265">**Service**</span></span>|<span data-ttu-id="5a863-266">**가중치**</span><span class="sxs-lookup"><span data-stu-id="5a863-266">**Weight**</span></span>|<span data-ttu-id="5a863-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5a863-267">**TTL**</span></span>|<span data-ttu-id="5a863-268">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="5a863-268">**Prio**</span></span>|<span data-ttu-id="5a863-269">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="5a863-269">**Protocol**</span></span>|<span data-ttu-id="5a863-270">**포트**</span><span class="sxs-lookup"><span data-stu-id="5a863-270">**Port**</span></span>|<span data-ttu-id="5a863-271">**대상**</span><span class="sxs-lookup"><span data-stu-id="5a863-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5a863-272">SRV</span><span class="sxs-lookup"><span data-stu-id="5a863-272">SRV</span></span>|<span data-ttu-id="5a863-273">sip</span><span class="sxs-lookup"><span data-stu-id="5a863-273">sip</span></span>|<span data-ttu-id="5a863-274">1 </span><span class="sxs-lookup"><span data-stu-id="5a863-274">1</span></span>|<span data-ttu-id="5a863-275">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-275">Use the default value (300).</span></span>|<span data-ttu-id="5a863-276">100</span><span class="sxs-lookup"><span data-stu-id="5a863-276">100</span></span>|<span data-ttu-id="5a863-277">tls</span><span class="sxs-lookup"><span data-stu-id="5a863-277">tls</span></span>|<span data-ttu-id="5a863-278">443</span><span class="sxs-lookup"><span data-stu-id="5a863-278">443</span></span>|<span data-ttu-id="5a863-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a863-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="5a863-280">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="5a863-281">SRV</span><span class="sxs-lookup"><span data-stu-id="5a863-281">SRV</span></span>|<span data-ttu-id="5a863-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="5a863-282">sipfederationtls</span></span>|<span data-ttu-id="5a863-283">1 </span><span class="sxs-lookup"><span data-stu-id="5a863-283">1</span></span>|<span data-ttu-id="5a863-284">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-284">Use the default value (300).</span></span>|<span data-ttu-id="5a863-285">100</span><span class="sxs-lookup"><span data-stu-id="5a863-285">100</span></span>|<span data-ttu-id="5a863-286">tcp</span><span class="sxs-lookup"><span data-stu-id="5a863-286">tcp</span></span>|<span data-ttu-id="5a863-287">5061</span><span class="sxs-lookup"><span data-stu-id="5a863-287">5061</span></span>|<span data-ttu-id="5a863-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a863-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="5a863-289">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![이름-BP-구성-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="5a863-291">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="5a863-293">두 번째 SRV 레코드 추가:</span><span class="sxs-lookup"><span data-stu-id="5a863-293">Add the second SRV record:</span></span>

<span data-ttu-id="5a863-294">위 표에 있는 다음 행의 값을 사용한 다음 **레코드 추가** 를 선택 하 여 두 번째 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a863-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="5a863-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a863-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
