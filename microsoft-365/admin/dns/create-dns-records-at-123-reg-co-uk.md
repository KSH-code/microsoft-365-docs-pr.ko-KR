---
title: Microsoft용 123-REG.CO.UK DNS 레코드 만들기
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Microsoft에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 123-reg.co.uk 대해 자세히 알아보습니다.
ms.openlocfilehash: d1e4d3d01a5e6b4f72c98fe09cf57374dd2417a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910429"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="a0385-103">Microsoft용 123-REG.CO.UK DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="a0385-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="a0385-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0385-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a0385-105">DNS 호스팅 공급자로 123-reg.co.uk를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a0385-106">이 레코드를 123-reg.co.uk Microsoft 서비스에서 작동 하게 도메인이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="a0385-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a0385-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a0385-108">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a0385-109">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0385-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a0385-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="a0385-110">Add a TXT record for verification</span></span>
<span data-ttu-id="a0385-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a0385-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a0385-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0385-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a0385-p104">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a0385-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="a0385-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="a0385-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="a0385-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="a0385-120">DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="a0385-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a0385-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a0385-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a0385-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="a0385-123">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="a0385-123">**Hostname**</span></span> <br/> |<span data-ttu-id="a0385-124">**종류**</span><span class="sxs-lookup"><span data-stu-id="a0385-124">**Type**</span></span> <br/> |<span data-ttu-id="a0385-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="a0385-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="a0385-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="a0385-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="a0385-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a0385-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a0385-128">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-128">**Note:** This is an example.</span></span> <span data-ttu-id="a0385-129">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="a0385-130">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="a0385-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="a0385-131">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="a0385-132">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a0385-133">이제 도메인 등록 기관의 사이트에 레코드를 추가한 후 Microsoft로 돌아가 레코드에 대한 검색을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="a0385-134">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a0385-135">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a0385-136">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a0385-137">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a0385-138">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a0385-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a0385-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a0385-140">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a0385-141">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0385-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a0385-142">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="a0385-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a0385-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a0385-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a0385-p107">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a0385-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="a0385-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="a0385-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="a0385-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="a0385-148">DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="a0385-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a0385-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a0385-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a0385-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a0385-151">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="a0385-151">**Hostname**</span></span>|<span data-ttu-id="a0385-152">**종류**</span><span class="sxs-lookup"><span data-stu-id="a0385-152">**Type**</span></span>|<span data-ttu-id="a0385-153">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="a0385-153">**Priority**</span></span>|<span data-ttu-id="a0385-154">**대상 MX**</span><span class="sxs-lookup"><span data-stu-id="a0385-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a0385-155">MX</span><span class="sxs-lookup"><span data-stu-id="a0385-155">MX</span></span>  <br/> |<span data-ttu-id="a0385-156">1</span><span class="sxs-lookup"><span data-stu-id="a0385-156">1</span></span>  <br/> <span data-ttu-id="a0385-157">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.yml)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0385-157">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="a0385-158">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a0385-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="a0385-159">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0385-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="a0385-160">**참고:** Microsoft 계정에서 \<domain-key\>을(를) 받으세요.</span><span class="sxs-lookup"><span data-stu-id="a0385-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="a0385-161">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="a0385-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![표의 값 복사 및 붙여넣기](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="a0385-163">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-163">Select **Add**.</span></span>
    
    ![추가 단추가 선택된 대화 상자의 스크린샷](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="a0385-165">다른 MX 레코드가 있으면 해당 레코드에 대한 **삭제(휴지통)** 아이콘을 선택하여 각 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![삭제 선택(휴지통 아이콘)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a0385-167">Microsoft에 필요한 5개의 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="a0385-167">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a0385-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a0385-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a0385-p109">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a0385-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="a0385-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="a0385-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="a0385-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="a0385-173">DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="a0385-174">5개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-174">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="a0385-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a0385-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a0385-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a0385-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a0385-177">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="a0385-177">**Hostname**</span></span>|<span data-ttu-id="a0385-178">**종류**</span><span class="sxs-lookup"><span data-stu-id="a0385-178">**Type**</span></span>|<span data-ttu-id="a0385-179">**대상 CNAME**</span><span class="sxs-lookup"><span data-stu-id="a0385-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a0385-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a0385-180">autodiscover</span></span>  <br/> |<span data-ttu-id="a0385-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0385-181">CNAME</span></span>  <br/> |<span data-ttu-id="a0385-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a0385-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="a0385-183">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0385-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a0385-184">sip</span><span class="sxs-lookup"><span data-stu-id="a0385-184">sip</span></span>  <br/> |<span data-ttu-id="a0385-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0385-185">CNAME</span></span>  <br/> |<span data-ttu-id="a0385-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a0385-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a0385-187">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0385-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a0385-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a0385-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a0385-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0385-189">CNAME</span></span>  <br/> |<span data-ttu-id="a0385-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a0385-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a0385-191">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0385-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a0385-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a0385-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a0385-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0385-193">CNAME</span></span>  <br/> |<span data-ttu-id="a0385-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="a0385-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="a0385-195">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0385-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a0385-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a0385-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a0385-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="a0385-197">CNAME</span></span>  <br/> |<span data-ttu-id="a0385-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a0385-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="a0385-199">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0385-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![복사하여 붙여넣을 대상 CNAME 스크린샷](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="a0385-201">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-201">Select **Add**.</span></span>
    
    ![대상 CNAME을 추가하는 스크린샷](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="a0385-203">나머지 4개의 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-203">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="a0385-204">고급 **DNS 섹션에서** 표의 다음 행 값을 사용하여 레코드를 만든 다음  추가를 다시 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="a0385-205">5개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-205">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a0385-206">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="a0385-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a0385-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a0385-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0385-208">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a0385-209">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a0385-210">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a0385-210">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a0385-211">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="a0385-212">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="a0385-212">Need examples?</span></span> <span data-ttu-id="a0385-213">[Microsoft에 대한 외부 Domain Name System 레코드](../../enterprise/external-domain-name-system-records.md#external-dns-records-required-for-spf)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0385-213">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="a0385-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="a0385-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="a0385-215">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="a0385-216">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a0385-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="a0385-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="a0385-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="a0385-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="a0385-219">DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="a0385-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a0385-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a0385-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a0385-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a0385-222">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="a0385-222">**Hostname**</span></span>|<span data-ttu-id="a0385-223">**종류**</span><span class="sxs-lookup"><span data-stu-id="a0385-223">**Type**</span></span>|<span data-ttu-id="a0385-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="a0385-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a0385-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="a0385-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="a0385-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a0385-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a0385-227">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="a0385-229">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-229">Select **Add**.</span></span>
    
    ![대상 TXT/SPF 스크린샷](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a0385-231">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="a0385-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a0385-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a0385-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a0385-p112">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a0385-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="a0385-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="a0385-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="a0385-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="a0385-237">DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="a0385-238">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="a0385-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a0385-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a0385-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a0385-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a0385-241">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="a0385-241">Hostname</span></span>|<span data-ttu-id="a0385-242">종류</span><span class="sxs-lookup"><span data-stu-id="a0385-242">Type</span></span>|<span data-ttu-id="a0385-243">우선 순위</span><span class="sxs-lookup"><span data-stu-id="a0385-243">Priority</span></span>|<span data-ttu-id="a0385-244">TTL</span><span class="sxs-lookup"><span data-stu-id="a0385-244">TTL</span></span>|<span data-ttu-id="a0385-245">대상 SRV</span><span class="sxs-lookup"><span data-stu-id="a0385-245">Destination SRV</span></span>|
    |<span data-ttu-id="a0385-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="a0385-246">_sip._tls</span></span>|<span data-ttu-id="a0385-247">SRV</span><span class="sxs-lookup"><span data-stu-id="a0385-247">SRV</span></span>|<span data-ttu-id="a0385-248">100</span><span class="sxs-lookup"><span data-stu-id="a0385-248">100</span></span>|<span data-ttu-id="a0385-249">3600</span><span class="sxs-lookup"><span data-stu-id="a0385-249">3600</span></span>|<span data-ttu-id="a0385-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a0385-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="a0385-251">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0385-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="a0385-252">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="a0385-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="a0385-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="a0385-254">SRV</span><span class="sxs-lookup"><span data-stu-id="a0385-254">SRV</span></span>|<span data-ttu-id="a0385-255">100</span><span class="sxs-lookup"><span data-stu-id="a0385-255">100</span></span>|<span data-ttu-id="a0385-256">3600</span><span class="sxs-lookup"><span data-stu-id="a0385-256">3600</span></span>|<span data-ttu-id="a0385-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a0385-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="a0385-258">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0385-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="a0385-259">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![표의 DNS 값 스크린샷](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="a0385-261">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-261">Select **Add**.</span></span>
    
    ![대상 SRV를 추가하는 스크린샷](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="a0385-263">다른 SRV 레코드를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a0385-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="a0385-264">고급 **DNS 섹션에서** 표의 두 번째 행 값을 사용하여 레코드를 만든  다음 추가를 다시 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a0385-265">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a0385-265">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a0385-266">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0385-266">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a0385-267">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0385-267">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
