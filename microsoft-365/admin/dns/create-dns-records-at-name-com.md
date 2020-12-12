---
title: Microsoft용 NAME.COM DNS 레코드 만들기
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Microsoft에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 name.com 방법을 자세히 알아보고 있습니다.
ms.openlocfilehash: 2330755412abfe262ac79c4acbfc12e33af76fe2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657830"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="61909-103">Microsoft용 name.com DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="61909-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="61909-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="61909-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="61909-105">DNS 호스팅 공급자로 name.com을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="61909-106">새 도메인에서 이러한 레코드를 name.com Microsoft 서비스에서 작동 하게 도메인이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="61909-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="61909-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61909-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="61909-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="61909-110">Add a TXT record for verification</span></span>
<span data-ttu-id="61909-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="61909-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="61909-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61909-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="61909-p104">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61909-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61909-119">내 **도메인에서** 수정할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61909-121">세부 **정보 열에서** **DNS 레코드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61909-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61909-123">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="61909-124">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="61909-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61909-125">**유형**</span><span class="sxs-lookup"><span data-stu-id="61909-125">**Type**</span></span> <br/> |<span data-ttu-id="61909-126">**호스트**</span><span class="sxs-lookup"><span data-stu-id="61909-126">**Host**</span></span> <br/> |<span data-ttu-id="61909-127">**응답**</span><span class="sxs-lookup"><span data-stu-id="61909-127">**Answer**</span></span> <br/> |<span data-ttu-id="61909-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61909-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="61909-129">TXT</span><span class="sxs-lookup"><span data-stu-id="61909-129">TXT</span></span>  <br/> |<span data-ttu-id="61909-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="61909-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="61909-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="61909-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="61909-132">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="61909-132">**Note:** This is an example.</span></span> <span data-ttu-id="61909-133">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="61909-134">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="61909-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="61909-135">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-135">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="61909-137">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61909-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="61909-139">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="61909-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="61909-140">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="61909-141">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61909-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="61909-142">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="61909-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="61909-143">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="61909-144">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="61909-145">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="61909-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61909-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="61909-149">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="61909-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="61909-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="61909-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="61909-p107">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61909-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61909-154">내 **도메인에서** 수정할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61909-156">세부 **정보 열에서** **DNS 레코드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61909-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61909-158">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="61909-159">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="61909-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="61909-160">**유형**</span><span class="sxs-lookup"><span data-stu-id="61909-160">**Type**</span></span>|<span data-ttu-id="61909-161">**호스트**</span><span class="sxs-lookup"><span data-stu-id="61909-161">**Host**</span></span>|<span data-ttu-id="61909-162">**응답**</span><span class="sxs-lookup"><span data-stu-id="61909-162">**Answer**</span></span>|<span data-ttu-id="61909-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61909-163">**TTL**</span></span>|<span data-ttu-id="61909-164">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="61909-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61909-165">MX</span><span class="sxs-lookup"><span data-stu-id="61909-165">MX</span></span>  <br/> |<span data-ttu-id="61909-166">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="61909-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="61909-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="61909-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="61909-168">**참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="61909-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="61909-169">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="61909-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="61909-170">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="61909-171">0</span><span class="sxs-lookup"><span data-stu-id="61909-171">0</span></span>  <br/> <span data-ttu-id="61909-172">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61909-172">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="61909-174">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61909-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="61909-176">다른 MX 레코드가 있으면 다음 2단계 절차를 사용하여 각 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="61909-177">다른 MX 레코드에 대해 **작업 열에서** **삭제를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="61909-179">각 삭제를 확인하려면 **작업** 열에서 **삭제를** 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="61909-181">다른 MX 레코드를 각각 삭제할 때까지 이 2단계 절차를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="61909-182">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="61909-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="61909-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="61909-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="61909-p109">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61909-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61909-187">내 **도메인에서** 수정할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61909-189">세부 **정보 열에서** **DNS 레코드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61909-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61909-191">첫 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="61909-192">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. </span><span class="sxs-lookup"><span data-stu-id="61909-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="61909-193">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="61909-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="61909-194">**유형**</span><span class="sxs-lookup"><span data-stu-id="61909-194">**Type**</span></span>|<span data-ttu-id="61909-195">**호스트**</span><span class="sxs-lookup"><span data-stu-id="61909-195">**Host**</span></span>|<span data-ttu-id="61909-196">**응답**</span><span class="sxs-lookup"><span data-stu-id="61909-196">**Answer**</span></span>|<span data-ttu-id="61909-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61909-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61909-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="61909-198">CNAME</span></span>  <br/> |<span data-ttu-id="61909-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="61909-199">autodiscover</span></span>  <br/> |<span data-ttu-id="61909-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="61909-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="61909-201">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="61909-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="61909-202">CNAME</span></span>  <br/> |<span data-ttu-id="61909-203">sip</span><span class="sxs-lookup"><span data-stu-id="61909-203">sip</span></span>  <br/> |<span data-ttu-id="61909-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="61909-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="61909-205">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="61909-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="61909-206">CNAME</span></span>  <br/> |<span data-ttu-id="61909-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="61909-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="61909-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="61909-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="61909-209">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="61909-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="61909-210">CNAME</span></span>  <br/> |<span data-ttu-id="61909-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="61909-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="61909-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="61909-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="61909-213">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="61909-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="61909-214">CNAME</span></span>  <br/> |<span data-ttu-id="61909-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="61909-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="61909-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61909-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="61909-217">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-217">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="61909-219">레코드 **추가를 선택하여** 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="61909-221">두 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="61909-222">위 표의 두 번째 행 값을 사용하여  레코드 추가를 선택하여 두 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="61909-223">표의 세 번째, 네 번째, 다섯 번째 및 여섯 번째 행의 값을 사용하여 같은 방법으로 나머지 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="61909-224">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="61909-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="61909-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="61909-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="61909-226">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="61909-227">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="61909-228">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="61909-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="61909-229">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="61909-p111">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61909-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61909-233">내 **도메인에서** 수정할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61909-235">세부 **정보 열에서** **DNS 레코드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61909-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61909-237">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="61909-238">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="61909-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="61909-239">**유형**</span><span class="sxs-lookup"><span data-stu-id="61909-239">**Type**</span></span>|<span data-ttu-id="61909-240">**호스트**</span><span class="sxs-lookup"><span data-stu-id="61909-240">**Host**</span></span>|<span data-ttu-id="61909-241">**응답**</span><span class="sxs-lookup"><span data-stu-id="61909-241">**Answer**</span></span>|<span data-ttu-id="61909-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61909-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61909-243">TXT</span><span class="sxs-lookup"><span data-stu-id="61909-243">TXT</span></span>  <br/> |<span data-ttu-id="61909-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="61909-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="61909-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="61909-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="61909-246">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="61909-247">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="61909-247">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="61909-249">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61909-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="61909-251">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="61909-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="61909-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="61909-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="61909-p112">시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61909-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61909-256">내 **도메인에서** 수정할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61909-258">세부 **정보 열에서** **DNS 레코드+ 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61909-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61909-260">첫 번째 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="61909-261">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="61909-262">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="61909-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="61909-263">**유형**</span><span class="sxs-lookup"><span data-stu-id="61909-263">**Type**</span></span>|<span data-ttu-id="61909-264">**서비스**</span><span class="sxs-lookup"><span data-stu-id="61909-264">**Service**</span></span>|<span data-ttu-id="61909-265">**가중치**</span><span class="sxs-lookup"><span data-stu-id="61909-265">**Weight**</span></span>|<span data-ttu-id="61909-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61909-266">**TTL**</span></span>|<span data-ttu-id="61909-267">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="61909-267">**Prio**</span></span>|<span data-ttu-id="61909-268">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="61909-268">**Protocol**</span></span>|<span data-ttu-id="61909-269">**포트**</span><span class="sxs-lookup"><span data-stu-id="61909-269">**Port**</span></span>|<span data-ttu-id="61909-270">**대상**</span><span class="sxs-lookup"><span data-stu-id="61909-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61909-271">SRV</span><span class="sxs-lookup"><span data-stu-id="61909-271">SRV</span></span>|<span data-ttu-id="61909-272">sip</span><span class="sxs-lookup"><span data-stu-id="61909-272">sip</span></span>|<span data-ttu-id="61909-273">1 </span><span class="sxs-lookup"><span data-stu-id="61909-273">1</span></span>|<span data-ttu-id="61909-274">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-274">Use the default value (300).</span></span>|<span data-ttu-id="61909-275">100</span><span class="sxs-lookup"><span data-stu-id="61909-275">100</span></span>|<span data-ttu-id="61909-276">tls</span><span class="sxs-lookup"><span data-stu-id="61909-276">tls</span></span>|<span data-ttu-id="61909-277">443</span><span class="sxs-lookup"><span data-stu-id="61909-277">443</span></span>|<span data-ttu-id="61909-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="61909-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="61909-279">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="61909-280">SRV</span><span class="sxs-lookup"><span data-stu-id="61909-280">SRV</span></span>|<span data-ttu-id="61909-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="61909-281">sipfederationtls</span></span>|<span data-ttu-id="61909-282">1 </span><span class="sxs-lookup"><span data-stu-id="61909-282">1</span></span>|<span data-ttu-id="61909-283">기본값(300)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-283">Use the default value (300).</span></span>|<span data-ttu-id="61909-284">100</span><span class="sxs-lookup"><span data-stu-id="61909-284">100</span></span>|<span data-ttu-id="61909-285">tcp</span><span class="sxs-lookup"><span data-stu-id="61909-285">tcp</span></span>|<span data-ttu-id="61909-286">5061</span><span class="sxs-lookup"><span data-stu-id="61909-286">5061</span></span>|<span data-ttu-id="61909-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="61909-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="61909-288">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="61909-290">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61909-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="61909-292">두 번째 SRV 레코드 추가:</span><span class="sxs-lookup"><span data-stu-id="61909-292">Add the second SRV record:</span></span>

<span data-ttu-id="61909-293">위 표의 다음 행 값을 사용하여 레코드  추가를 선택하여 두 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="61909-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61909-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
