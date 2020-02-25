---
title: Office 365에 대 한 Namecheap에서 DNS 레코드 만들기
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365에 대 한 Namecheap의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: a913aa5f2d88be5bed246e813bebd590f401c07f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246547"
---
# <a name="create-dns-records-at-namecheap-for-office-365"></a><span data-ttu-id="39ddf-103">Office 365에 대 한 Namecheap에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="39ddf-103">Create DNS records at Namecheap for Office 365</span></span>

 <span data-ttu-id="39ddf-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="39ddf-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="39ddf-105">Namecheap DNS 호스팅 공급자 이면이 문서에 나와 있는 단계를 수행 하 여 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="39ddf-106">Namecheap 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-106">After you add these records at Namecheap, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39ddf-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39ddf-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="39ddf-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="39ddf-110">Add a TXT record for verification</span></span>
<span data-ttu-id="39ddf-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="39ddf-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="39ddf-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39ddf-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="39ddf-116">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="39ddf-117">시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-117">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="39ddf-118">로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-118">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="39ddf-120">**랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="39ddf-122">**도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="39ddf-124">**고급 DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="39ddf-126">**호스트 레코드** 섹션에서 **새 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="39ddf-128">**형식** 드롭다운에서 **TXT 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39ddf-129">**새 레코드 추가**를 선택 하면 **유형** 드롭다운이 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="39ddf-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="39ddf-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="39ddf-132">(드롭다운 목록에서 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="39ddf-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="39ddf-133">**유형**</span><span class="sxs-lookup"><span data-stu-id="39ddf-133">**Type**</span></span>|<span data-ttu-id="39ddf-134">**호스트**</span><span class="sxs-lookup"><span data-stu-id="39ddf-134">**Host**</span></span>|<span data-ttu-id="39ddf-135">**값**</span><span class="sxs-lookup"><span data-stu-id="39ddf-135">**Value**</span></span>|<span data-ttu-id="39ddf-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="39ddf-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="39ddf-137">TXT</span><span class="sxs-lookup"><span data-stu-id="39ddf-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="39ddf-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="39ddf-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="39ddf-139">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-139">**Note:** This is an example.</span></span> <span data-ttu-id="39ddf-140">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-140">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="39ddf-141">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="39ddf-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="39ddf-142">30 분</span><span class="sxs-lookup"><span data-stu-id="39ddf-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="39ddf-144">**변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="39ddf-146">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="39ddf-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="39ddf-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="39ddf-148">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="39ddf-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="39ddf-149">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="39ddf-150">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="39ddf-151">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="39ddf-152">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="39ddf-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39ddf-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="39ddf-156">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="39ddf-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="39ddf-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="39ddf-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="39ddf-158">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="39ddf-159">시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-159">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="39ddf-160">로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-160">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="39ddf-162">**랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="39ddf-164">**도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="39ddf-166">**고급 DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="39ddf-168">**메일 설정** 섹션의 **전자 메일 전달** 드롭다운 목록에서 **사용자 지정 MX** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="39ddf-169">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="39ddf-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-2-1](../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="39ddf-171">**새 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-2-2-1](../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="39ddf-173">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="39ddf-174">**우선 순위** 상자는 **값** 상자 오른쪽에 있는 이름 없는 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="39ddf-175">드롭다운 목록에서 **TTL** 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="39ddf-176">**유형**</span><span class="sxs-lookup"><span data-stu-id="39ddf-176">**Type**</span></span>|<span data-ttu-id="39ddf-177">**호스트**</span><span class="sxs-lookup"><span data-stu-id="39ddf-177">**Host**</span></span>|<span data-ttu-id="39ddf-178">**값**</span><span class="sxs-lookup"><span data-stu-id="39ddf-178">**Value**</span></span>|<span data-ttu-id="39ddf-179">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="39ddf-179">**Priority**</span></span>|<span data-ttu-id="39ddf-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="39ddf-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="39ddf-181">MX 레코드</span><span class="sxs-lookup"><span data-stu-id="39ddf-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="39ddf-182">\<\*\*\>mail.protection.outlook.com를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="39ddf-183">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="39ddf-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="39ddf-184">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-184">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="39ddf-185">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="39ddf-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="39ddf-186">개</span><span class="sxs-lookup"><span data-stu-id="39ddf-186">0</span></span>  <br/> <span data-ttu-id="39ddf-187">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39ddf-187">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="39ddf-188">30 분</span><span class="sxs-lookup"><span data-stu-id="39ddf-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-2-2-2](../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="39ddf-190">**변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-2-3](../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="39ddf-192">다른 MX 레코드가 있으면 다음 2단계 절차를 사용하여 각 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="39ddf-193">먼저 제거할 레코드에 대 한 **삭제 아이콘** (휴지통 가능)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-2-4](../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="39ddf-195">두 번째로, **예** 를 선택 하 여 삭제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-2-5](../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="39ddf-197">이 절차의 앞부분에서 추가한 MX 레코드 중 하나를 제외 하 고 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="39ddf-198">Office 365에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="39ddf-198">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="39ddf-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="39ddf-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="39ddf-200">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="39ddf-201">시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-201">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="39ddf-202">로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-202">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="39ddf-204">**랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="39ddf-206">**도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="39ddf-208">**고급 DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="39ddf-210">**호스트 레코드** 섹션에서 **새 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="39ddf-212">**유형** 드롭다운에서 **CNAME 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39ddf-213">**새 레코드 추가**를 선택 하면 **유형** 드롭다운이 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-3-1](../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="39ddf-215">새 레코드의 빈 상자에서 **레코드 종류**로 **CNAME**을 선택한 후 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="39ddf-216">**유형**</span><span class="sxs-lookup"><span data-stu-id="39ddf-216">**Type**</span></span>|<span data-ttu-id="39ddf-217">**호스트**</span><span class="sxs-lookup"><span data-stu-id="39ddf-217">**Host**</span></span>|<span data-ttu-id="39ddf-218">**값**</span><span class="sxs-lookup"><span data-stu-id="39ddf-218">**Value**</span></span>|<span data-ttu-id="39ddf-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="39ddf-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="39ddf-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="39ddf-220">CNAME</span></span>  <br/> |<span data-ttu-id="39ddf-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="39ddf-221">autodiscover</span></span>  <br/> |<span data-ttu-id="39ddf-222">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="39ddf-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="39ddf-223">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39ddf-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="39ddf-224">3600</span><span class="sxs-lookup"><span data-stu-id="39ddf-224">3600</span></span>  <br/> |
    |<span data-ttu-id="39ddf-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="39ddf-225">CNAME</span></span>  <br/> |<span data-ttu-id="39ddf-226">sip</span><span class="sxs-lookup"><span data-stu-id="39ddf-226">sip</span></span>  <br/> |<span data-ttu-id="39ddf-227">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="39ddf-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="39ddf-228">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39ddf-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="39ddf-229">3600</span><span class="sxs-lookup"><span data-stu-id="39ddf-229">3600</span></span>  <br/> |
    |<span data-ttu-id="39ddf-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="39ddf-230">CNAME</span></span>  <br/> |<span data-ttu-id="39ddf-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="39ddf-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="39ddf-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="39ddf-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="39ddf-233">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39ddf-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="39ddf-234">3600</span><span class="sxs-lookup"><span data-stu-id="39ddf-234">3600</span></span>  <br/> |
    |<span data-ttu-id="39ddf-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="39ddf-235">CNAME</span></span>  <br/> |<span data-ttu-id="39ddf-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="39ddf-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="39ddf-237">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="39ddf-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="39ddf-238">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39ddf-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="39ddf-239">3600</span><span class="sxs-lookup"><span data-stu-id="39ddf-239">3600</span></span>  <br/> |
    |<span data-ttu-id="39ddf-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="39ddf-240">CNAME</span></span>  <br/> |<span data-ttu-id="39ddf-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="39ddf-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="39ddf-242">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="39ddf-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="39ddf-243">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39ddf-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="39ddf-244">3600</span><span class="sxs-lookup"><span data-stu-id="39ddf-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-3-2](../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="39ddf-246">**변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-3-3](../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="39ddf-248">위의 네 가지 단계와 표에 있는 나머지 다섯 개 행의 값을 사용 하 여 나머지 5 개의 CNAME 레코드를 각각 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="39ddf-249">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="39ddf-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="39ddf-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="39ddf-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="39ddf-251">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="39ddf-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="39ddf-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="39ddf-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="39ddf-253">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="39ddf-253">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="39ddf-254">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="39ddf-254">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="39ddf-255">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="39ddf-256">시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-256">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="39ddf-257">로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-257">You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="39ddf-258">**랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="39ddf-260">**도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="39ddf-262">**고급 DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="39ddf-264">**호스트 레코드** 섹션에서 **새 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="39ddf-266">**형식** 드롭다운에서 **TXT 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39ddf-267">**새 레코드 추가**를 선택 하면 **유형** 드롭다운이 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-4-1](../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="39ddf-269">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="39ddf-270">(드롭다운 목록에서 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="39ddf-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="39ddf-271">**유형**</span><span class="sxs-lookup"><span data-stu-id="39ddf-271">**Type**</span></span>|<span data-ttu-id="39ddf-272">**호스트**</span><span class="sxs-lookup"><span data-stu-id="39ddf-272">**Host**</span></span>|<span data-ttu-id="39ddf-273">**값**</span><span class="sxs-lookup"><span data-stu-id="39ddf-273">**Value**</span></span>|<span data-ttu-id="39ddf-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="39ddf-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="39ddf-275">TXT</span><span class="sxs-lookup"><span data-stu-id="39ddf-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="39ddf-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="39ddf-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="39ddf-277">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="39ddf-278">30 분</span><span class="sxs-lookup"><span data-stu-id="39ddf-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-4-2](../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="39ddf-280">**변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-4-3](../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="39ddf-282">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="39ddf-282">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="39ddf-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="39ddf-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="39ddf-284">시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-284">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="39ddf-285">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="39ddf-285">You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="39ddf-287">**랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="39ddf-289">**도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="39ddf-291">**고급 DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="39ddf-293">**호스트 레코드** 섹션에서 **새 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="39ddf-295">**유형** 드롭다운에서 **SRV 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39ddf-296">**새 레코드 추가**를 선택 하면 **유형** 드롭다운이 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-5-1](../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="39ddf-298">새 레코드의 빈 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="39ddf-299">**서비스**</span><span class="sxs-lookup"><span data-stu-id="39ddf-299">**Service**</span></span>|<span data-ttu-id="39ddf-300">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="39ddf-300">**Protocol**</span></span>|<span data-ttu-id="39ddf-301">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="39ddf-301">**Priority**</span></span>|<span data-ttu-id="39ddf-302">**가중치**</span><span class="sxs-lookup"><span data-stu-id="39ddf-302">**Weight**</span></span>|<span data-ttu-id="39ddf-303">**포트**</span><span class="sxs-lookup"><span data-stu-id="39ddf-303">**Port**</span></span>|<span data-ttu-id="39ddf-304">**대상**</span><span class="sxs-lookup"><span data-stu-id="39ddf-304">**Target**</span></span>|<span data-ttu-id="39ddf-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="39ddf-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="39ddf-306">_sip</span><span class="sxs-lookup"><span data-stu-id="39ddf-306">_sip</span></span>  <br/> |<span data-ttu-id="39ddf-307">_tls</span><span class="sxs-lookup"><span data-stu-id="39ddf-307">_tls</span></span>  <br/> |<span data-ttu-id="39ddf-308">100</span><span class="sxs-lookup"><span data-stu-id="39ddf-308">100</span></span>  <br/> |<span data-ttu-id="39ddf-309">개</span><span class="sxs-lookup"><span data-stu-id="39ddf-309">1</span></span>  <br/> |<span data-ttu-id="39ddf-310">443</span><span class="sxs-lookup"><span data-stu-id="39ddf-310">443</span></span>  <br/> |<span data-ttu-id="39ddf-311">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="39ddf-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="39ddf-312">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="39ddf-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="39ddf-313">30 분</span><span class="sxs-lookup"><span data-stu-id="39ddf-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="39ddf-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="39ddf-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="39ddf-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="39ddf-315">_tcp</span></span>  <br/> |<span data-ttu-id="39ddf-316">100</span><span class="sxs-lookup"><span data-stu-id="39ddf-316">100</span></span>  <br/> |<span data-ttu-id="39ddf-317">개</span><span class="sxs-lookup"><span data-stu-id="39ddf-317">1</span></span>  <br/> |<span data-ttu-id="39ddf-318">5061</span><span class="sxs-lookup"><span data-stu-id="39ddf-318">5061</span></span>  <br/> |<span data-ttu-id="39ddf-319">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="39ddf-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="39ddf-320">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39ddf-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="39ddf-321">30 분</span><span class="sxs-lookup"><span data-stu-id="39ddf-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-5-2](../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="39ddf-323">**변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-5-3](../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="39ddf-325">위의 네 가지 단계와 표의 두 번째 행에 있는 값을 사용 하 여 다른 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ddf-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="39ddf-p114">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39ddf-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
