---
title: Bluehost에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 Bluehost에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 1608aebdf984e22e45d7a2469acb0a8002fca2a1
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919554"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="9a431-103">Bluehost에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="9a431-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="9a431-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a431-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9a431-105">DNS 호스팅 공급자로 Bluehost를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9a431-106">Bluehost에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="9a431-107">Microsoft에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Microsoft에서 공개 웹 사이트 사용하기](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a431-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a431-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9a431-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9a431-109">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9a431-110">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a431-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9a431-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="9a431-111">Add a TXT record for verification</span></span>
<span data-ttu-id="9a431-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9a431-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9a431-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a431-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9a431-117">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="9a431-118">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9a431-119">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="9a431-120">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="9a431-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="9a431-121">***Domain_name*** 영역의 **dns 영역 편집기** 행에서 **dns 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="9a431-122">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9a431-122">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9a431-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9a431-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9a431-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="9a431-124">**Host Record**</span></span> <br/> |<span data-ttu-id="9a431-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9a431-125">**TTL**</span></span> <br/> |<span data-ttu-id="9a431-126">**종류**</span><span class="sxs-lookup"><span data-stu-id="9a431-126">**Type**</span></span> <br/> |<span data-ttu-id="9a431-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="9a431-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="9a431-128">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-128">14400</span></span>  <br/> |<span data-ttu-id="9a431-129">TXT</span><span class="sxs-lookup"><span data-stu-id="9a431-129">TXT</span></span>  <br/> |<span data-ttu-id="9a431-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9a431-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9a431-131">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-131">**Note:** This is an example.</span></span> <span data-ttu-id="9a431-132">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="9a431-133">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="9a431-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="9a431-134">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="9a431-135">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9a431-136">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드 검색을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="9a431-137">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9a431-138">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9a431-139">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9a431-140">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9a431-141">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9a431-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9a431-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9a431-143">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9a431-144">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a431-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9a431-145">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="9a431-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9a431-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9a431-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9a431-147">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="9a431-148">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9a431-149">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="9a431-150">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="9a431-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="9a431-151">***Domain_name*** 영역의 **dns 영역 편집기** 행에서 **dns 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="9a431-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9a431-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9a431-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9a431-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9a431-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="9a431-154">**Host Record**</span></span>|<span data-ttu-id="9a431-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9a431-155">**TTL**</span></span>|<span data-ttu-id="9a431-156">**유형**</span><span class="sxs-lookup"><span data-stu-id="9a431-156">**Type**</span></span>|<span data-ttu-id="9a431-157">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="9a431-157">**Points To**</span></span>|<span data-ttu-id="9a431-158">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="9a431-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9a431-159">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-159">14400</span></span>  <br/> |<span data-ttu-id="9a431-160">MX</span><span class="sxs-lookup"><span data-stu-id="9a431-160">MX</span></span>  <br/> | <span data-ttu-id="9a431-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9a431-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="9a431-162">**참고:** Microsoft 계정에서 \<*도메인-키*\>를 받으세요.</span><span class="sxs-lookup"><span data-stu-id="9a431-162">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="9a431-163">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="9a431-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="9a431-164">개</span><span class="sxs-lookup"><span data-stu-id="9a431-164">0</span></span>  <br/> <span data-ttu-id="9a431-165">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a431-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![드롭다운 목록에서 유형을 선택 합니다.](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="9a431-167">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-167">Select **add record**.</span></span>
    
    ![레코드 추가 선택](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="9a431-169">**MX(메일 교환기)** 구역에 다른 MX 레코드가 있으면 하나씩 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="9a431-170">다른 MX 레코드 중 하나에 대해 삭제를 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="9a431-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![각 추가 MX 레코드에 대해 삭제를 선택 합니다.](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="9a431-172">확인 대화 상자에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![확인을 선택 합니다.](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="9a431-174">같은 프로세스를 사용하여 이미 나열된 다른 MX 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9a431-175">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9a431-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9a431-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9a431-177">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="9a431-178">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9a431-179">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="9a431-180">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="9a431-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="9a431-181">***Domain_name*** 영역의 **dns 영역 편집기** 행에서 **dns 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="9a431-182">**A (호스트)** 레코드 구역에서 **자동 검색** 레코드의 행을 찾은 다음 해당 행에 대해 **삭제** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="9a431-183">Microsoft에서 요구 하는 **자동 검색** 레코드를 추가 *하기 전에* 기존 **자동 검색** 레코드를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-183">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="9a431-184">Bluehost에서는 두 개의 **autodiscover** 레코드를 동시에 유지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![삭제 선택](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="9a431-186">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-186">Select **OK**.</span></span>
    
    ![확인을 선택 합니다.](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="9a431-188">6개의 CNAME 레코드 중 첫 번째 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="9a431-189">**DNS 영역 편집기** 페이지의 **DNS 레코드 추가** 영역에서 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="9a431-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9a431-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9a431-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="9a431-191">**Host Record**</span></span>|<span data-ttu-id="9a431-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9a431-192">**TTL**</span></span>|<span data-ttu-id="9a431-193">**유형**</span><span class="sxs-lookup"><span data-stu-id="9a431-193">**Type**</span></span>|<span data-ttu-id="9a431-194">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="9a431-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9a431-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9a431-195">autodiscover</span></span>  <br/> |<span data-ttu-id="9a431-196">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-196">14400</span></span>  <br/> |<span data-ttu-id="9a431-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a431-197">CNAME</span></span>  <br/> |<span data-ttu-id="9a431-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9a431-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9a431-199">sip</span><span class="sxs-lookup"><span data-stu-id="9a431-199">sip</span></span>  <br/> |<span data-ttu-id="9a431-200">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-200">14400</span></span>  <br/> |<span data-ttu-id="9a431-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a431-201">CNAME</span></span>  <br/> |<span data-ttu-id="9a431-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9a431-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9a431-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9a431-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9a431-204">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-204">14400</span></span>  <br/> |<span data-ttu-id="9a431-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a431-205">CNAME</span></span>  <br/> |<span data-ttu-id="9a431-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9a431-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9a431-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9a431-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9a431-208">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-208">14400</span></span>  <br/> |<span data-ttu-id="9a431-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a431-209">CNAME</span></span>  <br/> |<span data-ttu-id="9a431-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9a431-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9a431-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9a431-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9a431-212">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-212">14400</span></span>  <br/> |<span data-ttu-id="9a431-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a431-213">CNAME</span></span>  <br/> |<span data-ttu-id="9a431-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9a431-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![첫 번째 CNAME 레코드 만들기](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="9a431-216">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-216">Select **add record**.</span></span>
    
    ![레코드 추가 선택](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="9a431-218">나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="9a431-219">여전히 **DNS 레코드 추가** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **레코드 추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="9a431-220">6개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9a431-221">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="9a431-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9a431-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9a431-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a431-223">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9a431-224">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9a431-225">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9a431-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9a431-226">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="9a431-227">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="9a431-227">Need examples?</span></span> <span data-ttu-id="9a431-228">[Microsoft에 대한 외부 Domain Name System 레코드](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a431-228">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="9a431-229">SPF 레코드의 유효성을 검사 하기 위해 이러한[spf 유효성 검사 도구](../setup/domains-faq.md)중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="9a431-230">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="9a431-231">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9a431-232">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="9a431-233">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="9a431-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="9a431-234">***Domain_name*** 영역의 **dns 영역 편집기** 행에서 **dns 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="9a431-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9a431-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9a431-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9a431-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="9a431-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="9a431-237">**Host Record**</span></span>|<span data-ttu-id="9a431-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9a431-238">**TTL**</span></span>|<span data-ttu-id="9a431-239">**종류**</span><span class="sxs-lookup"><span data-stu-id="9a431-239">**Type**</span></span>|<span data-ttu-id="9a431-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="9a431-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9a431-241">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-241">14400</span></span>  <br/> |<span data-ttu-id="9a431-242">TXT</span><span class="sxs-lookup"><span data-stu-id="9a431-242">TXT</span></span>  <br/> |<span data-ttu-id="9a431-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9a431-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="9a431-244">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![TXT 값 복사](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="9a431-246">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-246">Select **add record**.</span></span>
    
    ![레코드 추가 선택](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9a431-248">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="9a431-248">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9a431-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9a431-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9a431-250">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="9a431-251">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9a431-252">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="9a431-253">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="9a431-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="9a431-254">***Domain_name*** 영역의 **dns 영역 편집기** 행에서 **dns 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="9a431-255">2개의 SRV 레코드 중 첫 번째 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="9a431-256">**DNS 영역 편집기** 페이지의 **DNS 레코드 추가** 영역에서 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="9a431-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9a431-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9a431-258">**서비스**</span><span class="sxs-lookup"><span data-stu-id="9a431-258">**Service**</span></span>|<span data-ttu-id="9a431-259">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="9a431-259">**Protocol**</span></span>|<span data-ttu-id="9a431-260">**호스트**</span><span class="sxs-lookup"><span data-stu-id="9a431-260">**Host**</span></span>|<span data-ttu-id="9a431-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9a431-261">**TTL**</span></span>|<span data-ttu-id="9a431-262">**종류**</span><span class="sxs-lookup"><span data-stu-id="9a431-262">**Type**</span></span>|<span data-ttu-id="9a431-263">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="9a431-263">**Priority**</span></span>|<span data-ttu-id="9a431-264">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="9a431-264">**Weight**</span></span>|<span data-ttu-id="9a431-265">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="9a431-265">**Port**</span></span>|<span data-ttu-id="9a431-266">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="9a431-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9a431-267">_sip</span><span class="sxs-lookup"><span data-stu-id="9a431-267">_sip</span></span>  <br/> |<span data-ttu-id="9a431-268">_tls</span><span class="sxs-lookup"><span data-stu-id="9a431-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="9a431-269">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-269">14400</span></span>  <br/> |<span data-ttu-id="9a431-270">SRV</span><span class="sxs-lookup"><span data-stu-id="9a431-270">SRV</span></span>  <br/> |<span data-ttu-id="9a431-271">100</span><span class="sxs-lookup"><span data-stu-id="9a431-271">100</span></span>  <br/> |<span data-ttu-id="9a431-272">1 </span><span class="sxs-lookup"><span data-stu-id="9a431-272">1</span></span>  <br/> |<span data-ttu-id="9a431-273">443</span><span class="sxs-lookup"><span data-stu-id="9a431-273">443</span></span>  <br/> |<span data-ttu-id="9a431-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9a431-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9a431-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9a431-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="9a431-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="9a431-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="9a431-277">14400</span><span class="sxs-lookup"><span data-stu-id="9a431-277">14400</span></span>  <br/> |<span data-ttu-id="9a431-278">SRV</span><span class="sxs-lookup"><span data-stu-id="9a431-278">SRV</span></span>  <br/> |<span data-ttu-id="9a431-279">100</span><span class="sxs-lookup"><span data-stu-id="9a431-279">100</span></span>  <br/> |<span data-ttu-id="9a431-280">1 </span><span class="sxs-lookup"><span data-stu-id="9a431-280">1</span></span>  <br/> |<span data-ttu-id="9a431-281">5061</span><span class="sxs-lookup"><span data-stu-id="9a431-281">5061</span></span>  <br/> |<span data-ttu-id="9a431-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9a431-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![새 레코드의 값을 복사 합니다.](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="9a431-284">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-284">Select **add record**.</span></span>
    
    ![레코드 추가 선택](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="9a431-286">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="9a431-287">여전히 **DNS 레코드 추가** 구역에서 표에 있는 다른 행의 값을 사용 하 여 레코드를 만들고 다시 **레코드 추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="9a431-288">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9a431-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9a431-289">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a431-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9a431-290">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a431-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

