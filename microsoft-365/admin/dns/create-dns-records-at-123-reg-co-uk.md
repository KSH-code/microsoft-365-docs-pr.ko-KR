---
title: 123 reg.co.uk에서 Office 365용 DNS 레코드를 만들기
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Office 365 용 123-reg.co.uk에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: acbc0f1c8a7eb7dcbe5f274d0f2c8b2c403e7de0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246882"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="bb35a-103">123 reg.co.uk에서 Office 365용 DNS 레코드를 만들기</span><span class="sxs-lookup"><span data-stu-id="bb35a-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="bb35a-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb35a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bb35a-105">DNS 호스팅 공급자로 123-reg.co.uk를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="bb35a-106">123-reg.co.uk에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="bb35a-107">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb35a-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb35a-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="bb35a-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="bb35a-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="bb35a-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="bb35a-110">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb35a-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="bb35a-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="bb35a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="bb35a-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="bb35a-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="bb35a-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb35a-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="bb35a-117">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-117">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="bb35a-118">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="bb35a-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="bb35a-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bb35a-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="bb35a-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="bb35a-121">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="bb35a-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bb35a-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="bb35a-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="bb35a-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="bb35a-124">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="bb35a-124">**Hostname**</span></span> <br/> |<span data-ttu-id="bb35a-125">**종류**</span><span class="sxs-lookup"><span data-stu-id="bb35a-125">**Type**</span></span> <br/> |<span data-ttu-id="bb35a-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="bb35a-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="bb35a-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="bb35a-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="bb35a-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bb35a-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bb35a-129">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-129">**Note:** This is an example.</span></span> <span data-ttu-id="bb35a-130">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-130">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="bb35a-131">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="bb35a-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="bb35a-132">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="bb35a-133">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="bb35a-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="bb35a-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="bb35a-135">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="bb35a-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="bb35a-136">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="bb35a-137">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="bb35a-138">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="bb35a-139">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bb35a-140">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="bb35a-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="bb35a-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="bb35a-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="bb35a-142">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb35a-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="bb35a-143">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="bb35a-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="bb35a-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="bb35a-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="bb35a-p107">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="bb35a-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="bb35a-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bb35a-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="bb35a-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="bb35a-149">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="bb35a-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bb35a-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="bb35a-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="bb35a-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bb35a-152">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="bb35a-152">**Hostname**</span></span>|<span data-ttu-id="bb35a-153">**종류**</span><span class="sxs-lookup"><span data-stu-id="bb35a-153">**Type**</span></span>|<span data-ttu-id="bb35a-154">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="bb35a-154">**Priority**</span></span>|<span data-ttu-id="bb35a-155">**대상 MX**</span><span class="sxs-lookup"><span data-stu-id="bb35a-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="bb35a-156">MX</span><span class="sxs-lookup"><span data-stu-id="bb35a-156">MX</span></span>  <br/> |<span data-ttu-id="bb35a-157">개</span><span class="sxs-lookup"><span data-stu-id="bb35a-157">1</span></span>  <br/> <span data-ttu-id="bb35a-158">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb35a-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="bb35a-159">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="bb35a-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="bb35a-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bb35a-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="bb35a-161">**참고:** Office 365 \<계정에서 도메인\> 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="bb35a-162">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="bb35a-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![표의 값 복사 및 붙여넣기](../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="bb35a-164">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-164">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="bb35a-166">다른 MX 레코드가 있으면 해당 레코드에 대한 **삭제(휴지통)** 아이콘을 선택하여 각 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![삭제 (휴지통 아이콘)를 선택 합니다.](../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="bb35a-168">Office 365에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="bb35a-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="bb35a-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="bb35a-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="bb35a-p109">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="bb35a-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="bb35a-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bb35a-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="bb35a-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="bb35a-174">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="bb35a-175">6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="bb35a-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bb35a-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="bb35a-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="bb35a-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bb35a-178">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="bb35a-178">**Hostname**</span></span>|<span data-ttu-id="bb35a-179">**종류**</span><span class="sxs-lookup"><span data-stu-id="bb35a-179">**Type**</span></span>|<span data-ttu-id="bb35a-180">**대상 CNAME**</span><span class="sxs-lookup"><span data-stu-id="bb35a-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="bb35a-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="bb35a-181">autodiscover</span></span>  <br/> |<span data-ttu-id="bb35a-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="bb35a-182">CNAME</span></span>  <br/> |<span data-ttu-id="bb35a-183">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="bb35a-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="bb35a-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bb35a-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bb35a-185">sip</span><span class="sxs-lookup"><span data-stu-id="bb35a-185">sip</span></span>  <br/> |<span data-ttu-id="bb35a-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="bb35a-186">CNAME</span></span>  <br/> |<span data-ttu-id="bb35a-187">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bb35a-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bb35a-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bb35a-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bb35a-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bb35a-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="bb35a-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="bb35a-190">CNAME</span></span>  <br/> |<span data-ttu-id="bb35a-191">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bb35a-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bb35a-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bb35a-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bb35a-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="bb35a-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="bb35a-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="bb35a-194">CNAME</span></span>  <br/> |<span data-ttu-id="bb35a-195">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="bb35a-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="bb35a-196">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb35a-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bb35a-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="bb35a-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="bb35a-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="bb35a-198">CNAME</span></span>  <br/> |<span data-ttu-id="bb35a-199">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="bb35a-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="bb35a-200">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb35a-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="bb35a-202">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-202">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="bb35a-204">나머지 5개의 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="bb35a-205">**고급 DNS** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="bb35a-206">6개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="bb35a-207">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="bb35a-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="bb35a-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="bb35a-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb35a-209">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="bb35a-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="bb35a-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="bb35a-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="bb35a-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb35a-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="bb35a-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="bb35a-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="bb35a-213">Need examples?</span><span class="sxs-lookup"><span data-stu-id="bb35a-213">Need examples?</span></span> <span data-ttu-id="bb35a-214">이러한 [외부 도메인 이름 시스템 레코드에서 Office 365를](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb35a-214">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="bb35a-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="bb35a-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="bb35a-216">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="bb35a-217">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="bb35a-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="bb35a-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bb35a-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="bb35a-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="bb35a-220">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="bb35a-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bb35a-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="bb35a-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="bb35a-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bb35a-223">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="bb35a-223">**Hostname**</span></span>|<span data-ttu-id="bb35a-224">**종류**</span><span class="sxs-lookup"><span data-stu-id="bb35a-224">**Type**</span></span>|<span data-ttu-id="bb35a-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="bb35a-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="bb35a-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="bb35a-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="bb35a-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="bb35a-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="bb35a-228">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-4-1](../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="bb35a-230">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-230">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="bb35a-232">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="bb35a-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="bb35a-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="bb35a-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="bb35a-p112">시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="bb35a-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="bb35a-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bb35a-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="bb35a-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="bb35a-238">**DNS 관리** 페이지에서 **고급 DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="bb35a-239">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="bb35a-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bb35a-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="bb35a-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="bb35a-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bb35a-242">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="bb35a-242">Hostname</span></span>|<span data-ttu-id="bb35a-243">종류</span><span class="sxs-lookup"><span data-stu-id="bb35a-243">Type</span></span>|<span data-ttu-id="bb35a-244">우선 순위</span><span class="sxs-lookup"><span data-stu-id="bb35a-244">Priority</span></span>|<span data-ttu-id="bb35a-245">TTL</span><span class="sxs-lookup"><span data-stu-id="bb35a-245">TTL</span></span>|<span data-ttu-id="bb35a-246">대상 SRV</span><span class="sxs-lookup"><span data-stu-id="bb35a-246">Destination SRV</span></span>|
    |<span data-ttu-id="bb35a-247">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="bb35a-247">_sip._tls</span></span>|<span data-ttu-id="bb35a-248">SRV</span><span class="sxs-lookup"><span data-stu-id="bb35a-248">SRV</span></span>|<span data-ttu-id="bb35a-249">100</span><span class="sxs-lookup"><span data-stu-id="bb35a-249">100</span></span>|<span data-ttu-id="bb35a-250">3600</span><span class="sxs-lookup"><span data-stu-id="bb35a-250">3600</span></span>|<span data-ttu-id="bb35a-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bb35a-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="bb35a-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bb35a-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="bb35a-253">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="bb35a-254">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="bb35a-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="bb35a-255">SRV</span><span class="sxs-lookup"><span data-stu-id="bb35a-255">SRV</span></span>|<span data-ttu-id="bb35a-256">100</span><span class="sxs-lookup"><span data-stu-id="bb35a-256">100</span></span>|<span data-ttu-id="bb35a-257">3600</span><span class="sxs-lookup"><span data-stu-id="bb35a-257">3600</span></span>|<span data-ttu-id="bb35a-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bb35a-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="bb35a-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bb35a-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="bb35a-260">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="bb35a-262">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-262">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="bb35a-264">다른 SRV 레코드를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="bb35a-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="bb35a-265">**고급 DNS** 구역에서 표의 두 번째 행 값을 사용 하 여 레코드를 만들고 다시 **추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb35a-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="bb35a-266">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="bb35a-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="bb35a-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="bb35a-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="bb35a-268">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb35a-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
