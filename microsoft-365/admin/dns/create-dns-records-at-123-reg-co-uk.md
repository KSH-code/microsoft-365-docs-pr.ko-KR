---
title: 123-reg.co.uk에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 123-reg.co.uk에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 51542e1f00153a87ca06ec540d391de6ca621bab
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307034"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="835b5-103">123-reg.co.uk에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="835b5-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="835b5-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="835b5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="835b5-105">DNS 호스팅 공급자로 123-reg.co.uk를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="835b5-106">123-reg.co.uk에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="835b5-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="835b5-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="835b5-108">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="835b5-109">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="835b5-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="835b5-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="835b5-110">Add a TXT record for verification</span></span>
<span data-ttu-id="835b5-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="835b5-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="835b5-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="835b5-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="835b5-p104">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="835b5-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="835b5-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="835b5-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="835b5-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="835b5-120">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="835b5-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="835b5-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="835b5-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="835b5-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="835b5-123">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="835b5-123">**Hostname**</span></span> <br/> |<span data-ttu-id="835b5-124">**종류**</span><span class="sxs-lookup"><span data-stu-id="835b5-124">**Type**</span></span> <br/> |<span data-ttu-id="835b5-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="835b5-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="835b5-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="835b5-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="835b5-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="835b5-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="835b5-128">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-128">**Note:** This is an example.</span></span> <span data-ttu-id="835b5-129">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="835b5-130">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="835b5-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="835b5-131">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="835b5-132">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="835b5-133">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드 검색을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="835b5-134">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="835b5-135">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="835b5-136">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="835b5-137">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="835b5-138">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="835b5-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="835b5-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="835b5-140">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="835b5-141">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="835b5-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="835b5-142">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="835b5-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="835b5-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="835b5-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="835b5-p107">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="835b5-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="835b5-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="835b5-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="835b5-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="835b5-148">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="835b5-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="835b5-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="835b5-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="835b5-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="835b5-151">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="835b5-151">**Hostname**</span></span>|<span data-ttu-id="835b5-152">**종류**</span><span class="sxs-lookup"><span data-stu-id="835b5-152">**Type**</span></span>|<span data-ttu-id="835b5-153">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="835b5-153">**Priority**</span></span>|<span data-ttu-id="835b5-154">**대상 MX**</span><span class="sxs-lookup"><span data-stu-id="835b5-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="835b5-155">MX</span><span class="sxs-lookup"><span data-stu-id="835b5-155">MX</span></span>  <br/> |<span data-ttu-id="835b5-156">1 </span><span class="sxs-lookup"><span data-stu-id="835b5-156">1</span></span>  <br/> <span data-ttu-id="835b5-157">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="835b5-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="835b5-158">*\<domain-key\>*  . mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="835b5-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="835b5-159">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="835b5-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="835b5-160">**참고:** Microsoft 계정에서 \<domain-key\>을(를) 받으세요.</span><span class="sxs-lookup"><span data-stu-id="835b5-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="835b5-161">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="835b5-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![표의 값 복사 및 붙여넣기](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="835b5-163">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-163">Select **Add**.</span></span>
    
    ![추가를 선택합니다.](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="835b5-165">다른 MX 레코드가 있으면 해당 레코드에 대한 **삭제(휴지통)** 아이콘을 선택하여 각 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![삭제 (휴지통 아이콘)를 선택 합니다.](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="835b5-167">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-167">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="835b5-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="835b5-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="835b5-p109">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="835b5-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="835b5-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="835b5-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="835b5-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="835b5-173">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="835b5-174">6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-174">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="835b5-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="835b5-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="835b5-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="835b5-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="835b5-177">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="835b5-177">**Hostname**</span></span>|<span data-ttu-id="835b5-178">**종류**</span><span class="sxs-lookup"><span data-stu-id="835b5-178">**Type**</span></span>|<span data-ttu-id="835b5-179">**대상 CNAME**</span><span class="sxs-lookup"><span data-stu-id="835b5-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="835b5-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="835b5-180">autodiscover</span></span>  <br/> |<span data-ttu-id="835b5-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="835b5-181">CNAME</span></span>  <br/> |<span data-ttu-id="835b5-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="835b5-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="835b5-183">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="835b5-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="835b5-184">sip</span><span class="sxs-lookup"><span data-stu-id="835b5-184">sip</span></span>  <br/> |<span data-ttu-id="835b5-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="835b5-185">CNAME</span></span>  <br/> |<span data-ttu-id="835b5-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="835b5-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="835b5-187">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="835b5-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="835b5-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="835b5-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="835b5-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="835b5-189">CNAME</span></span>  <br/> |<span data-ttu-id="835b5-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="835b5-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="835b5-191">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="835b5-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="835b5-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="835b5-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="835b5-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="835b5-193">CNAME</span></span>  <br/> |<span data-ttu-id="835b5-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="835b5-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="835b5-195">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="835b5-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="835b5-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="835b5-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="835b5-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="835b5-197">CNAME</span></span>  <br/> |<span data-ttu-id="835b5-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="835b5-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="835b5-199">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="835b5-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="835b5-201">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-201">Select **Add**.</span></span>
    
    ![추가를 선택합니다.](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="835b5-203">나머지 5개의 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-203">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="835b5-204">**고급 DNS** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="835b5-205">6개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-205">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="835b5-206">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="835b5-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="835b5-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="835b5-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="835b5-208">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="835b5-209">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="835b5-210">도메인에 대 한 SPF 레코드가 이미 있는 경우 마이크로 Sfot에 대해 새로 만들지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="835b5-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="835b5-211">대신, 두 값 집합을 모두 포함 하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="835b5-212">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="835b5-212">Need examples?</span></span> <span data-ttu-id="835b5-213">[Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="835b5-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="835b5-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="835b5-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="835b5-215">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="835b5-216">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="835b5-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="835b5-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="835b5-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="835b5-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="835b5-219">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="835b5-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="835b5-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="835b5-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="835b5-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="835b5-222">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="835b5-222">**Hostname**</span></span>|<span data-ttu-id="835b5-223">**종류**</span><span class="sxs-lookup"><span data-stu-id="835b5-223">**Type**</span></span>|<span data-ttu-id="835b5-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="835b5-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="835b5-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="835b5-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="835b5-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="835b5-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="835b5-227">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="835b5-229">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-229">Select **Add**.</span></span>
    
    ![추가를 선택합니다.](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="835b5-231">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="835b5-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="835b5-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="835b5-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="835b5-p112">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="835b5-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="835b5-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="835b5-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="835b5-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="835b5-237">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="835b5-238">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="835b5-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="835b5-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="835b5-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="835b5-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="835b5-241">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="835b5-241">Hostname</span></span>|<span data-ttu-id="835b5-242">종류</span><span class="sxs-lookup"><span data-stu-id="835b5-242">Type</span></span>|<span data-ttu-id="835b5-243">우선 순위</span><span class="sxs-lookup"><span data-stu-id="835b5-243">Priority</span></span>|<span data-ttu-id="835b5-244">TTL</span><span class="sxs-lookup"><span data-stu-id="835b5-244">TTL</span></span>|<span data-ttu-id="835b5-245">대상 SRV</span><span class="sxs-lookup"><span data-stu-id="835b5-245">Destination SRV</span></span>|
    |<span data-ttu-id="835b5-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="835b5-246">_sip._tls</span></span>|<span data-ttu-id="835b5-247">SRV</span><span class="sxs-lookup"><span data-stu-id="835b5-247">SRV</span></span>|<span data-ttu-id="835b5-248">100</span><span class="sxs-lookup"><span data-stu-id="835b5-248">100</span></span>|<span data-ttu-id="835b5-249">3600</span><span class="sxs-lookup"><span data-stu-id="835b5-249">3600</span></span>|<span data-ttu-id="835b5-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="835b5-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="835b5-251">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="835b5-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="835b5-252">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="835b5-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="835b5-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="835b5-254">SRV</span><span class="sxs-lookup"><span data-stu-id="835b5-254">SRV</span></span>|<span data-ttu-id="835b5-255">100</span><span class="sxs-lookup"><span data-stu-id="835b5-255">100</span></span>|<span data-ttu-id="835b5-256">3600</span><span class="sxs-lookup"><span data-stu-id="835b5-256">3600</span></span>|<span data-ttu-id="835b5-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="835b5-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="835b5-258">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="835b5-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="835b5-259">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="835b5-261">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-261">Select **Add**.</span></span>
    
    ![추가를 선택합니다.](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="835b5-263">다른 SRV 레코드를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="835b5-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="835b5-264">**고급 DNS** 구역에서 표의 두 번째 행 값을 사용 하 여 레코드를 만들고 다시 **추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="835b5-265">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="835b5-265">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="835b5-266">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835b5-266">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="835b5-267">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="835b5-267">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
