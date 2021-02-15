---
title: Bluehost에서 Microsoft용 DNS 레코드 만들기
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Microsoft용 Bluehost에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: a9de709b0981c3e74eec1a3ea0e0452d068c5ad4
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658150"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="d9b6d-103">Bluehost에서 Microsoft용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="d9b6d-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="d9b6d-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d9b6d-105">DNS 호스팅 공급자로 Bluehost를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d9b6d-106">Bluehost에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="d9b6d-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d9b6d-108">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d9b6d-109">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d9b6d-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d9b6d-110">Add a TXT record for verification</span></span>
<span data-ttu-id="d9b6d-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d9b6d-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d9b6d-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9b6d-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d9b6d-116">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="d9b6d-117">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d9b6d-118">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="d9b6d-119">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="d9b6d-120">domain_name ***_ 영역의 _* DNS 영역** 편집기 행에서 DNS 레코드 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-120">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="d9b6d-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d9b6d-122">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d9b6d-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-123">**Host Record**</span></span> <br/> |<span data-ttu-id="d9b6d-124">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-124">**TTL**</span></span> <br/> |<span data-ttu-id="d9b6d-125">**종류**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-125">**Type**</span></span> <br/> |<span data-ttu-id="d9b6d-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="d9b6d-127">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-127">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-128">TXT</span><span class="sxs-lookup"><span data-stu-id="d9b6d-128">TXT</span></span>  <br/> |<span data-ttu-id="d9b6d-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d9b6d-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d9b6d-130">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-130">**Note:** This is an example.</span></span> <span data-ttu-id="d9b6d-131">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="d9b6d-132">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="d9b6d-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="d9b6d-133">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="d9b6d-134">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d9b6d-135">이제 도메인 등록 기관의 사이트에 레코드를 추가한 후 Microsoft로 돌아가서 레코드에 대한 검색을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="d9b6d-136">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d9b6d-137">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d9b6d-138">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d9b6d-139">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d9b6d-140">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d9b6d-141">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-141">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d9b6d-142">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-142">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d9b6d-143">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-143">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d9b6d-144">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="d9b6d-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d9b6d-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d9b6d-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d9b6d-146">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="d9b6d-147">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d9b6d-148">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="d9b6d-149">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="d9b6d-150">domain_name ***_ 영역의 _* DNS 영역** 편집기 행에서 DNS 레코드 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-150">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="d9b6d-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d9b6d-152">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d9b6d-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-153">**Host Record**</span></span>|<span data-ttu-id="d9b6d-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-154">**TTL**</span></span>|<span data-ttu-id="d9b6d-155">**종류**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-155">**Type**</span></span>|<span data-ttu-id="d9b6d-156">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-156">**Points To**</span></span>|<span data-ttu-id="d9b6d-157">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d9b6d-158">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-158">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-159">MX</span><span class="sxs-lookup"><span data-stu-id="d9b6d-159">MX</span></span>  <br/> | <span data-ttu-id="d9b6d-160">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d9b6d-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="d9b6d-161">**참고:** Microsoft 계정에서 \<*domain-key*\>을(를) 받으세요.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="d9b6d-162">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="d9b6d-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d9b6d-163">0</span><span class="sxs-lookup"><span data-stu-id="d9b6d-163">0</span></span>  <br/> <span data-ttu-id="d9b6d-164">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Choose Type from the drop-down list](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="d9b6d-166">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-166">Select **add record**.</span></span>
    
    ![레코드 추가 선택](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="d9b6d-168">**MX(메일 교환기)** 구역에 다른 MX 레코드가 있으면 하나씩 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="d9b6d-169">다른 MX 레코드 중 하나에 대해 삭제를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![각 추가 MX 레코드에 대해 삭제 선택](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="d9b6d-171">확인 대화 상자에서 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![확인 선택](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="d9b6d-173">같은 프로세스를 사용하여 이미 나열된 다른 MX 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d9b6d-174">Microsoft에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d9b6d-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d9b6d-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d9b6d-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d9b6d-176">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="d9b6d-177">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d9b6d-178">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="d9b6d-179">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="d9b6d-180">domain_name ***_ 영역의 _* DNS 영역** 편집기 행에서 DNS 레코드 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-180">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="d9b6d-181">**A(호스트)** 레코드 섹션에서 자동 검색  레코드의 행을 찾은 다음 해당 행에 대한 **삭제를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d9b6d-182">Microsoft에 필요한 자동iscover 레코드를 추가하기 전에 기존  **자동iscover** 레코드를 삭제해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="d9b6d-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="d9b6d-183">Bluehost에서는 두 개의 **autodiscover** 레코드를 동시에 유지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![삭제를 선택합니다.](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="d9b6d-185">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-185">Select **OK**.</span></span>
    
    ![확인 선택](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="d9b6d-187">6개의 CNAME 레코드 중 첫 번째 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="d9b6d-188">**DNS 영역 편집기** 페이지의 **DNS 레코드 추가** 영역에서 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d9b6d-189">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d9b6d-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-190">**Host Record**</span></span>|<span data-ttu-id="d9b6d-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-191">**TTL**</span></span>|<span data-ttu-id="d9b6d-192">**종류**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-192">**Type**</span></span>|<span data-ttu-id="d9b6d-193">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d9b6d-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d9b6d-194">autodiscover</span></span>  <br/> |<span data-ttu-id="d9b6d-195">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-195">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="d9b6d-196">CNAME</span></span>  <br/> |<span data-ttu-id="d9b6d-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d9b6d-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d9b6d-198">sip</span><span class="sxs-lookup"><span data-stu-id="d9b6d-198">sip</span></span>  <br/> |<span data-ttu-id="d9b6d-199">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-199">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="d9b6d-200">CNAME</span></span>  <br/> |<span data-ttu-id="d9b6d-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d9b6d-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d9b6d-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d9b6d-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d9b6d-203">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-203">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="d9b6d-204">CNAME</span></span>  <br/> |<span data-ttu-id="d9b6d-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d9b6d-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d9b6d-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d9b6d-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d9b6d-207">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-207">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="d9b6d-208">CNAME</span></span>  <br/> |<span data-ttu-id="d9b6d-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d9b6d-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d9b6d-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d9b6d-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d9b6d-211">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-211">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="d9b6d-212">CNAME</span></span>  <br/> |<span data-ttu-id="d9b6d-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d9b6d-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![첫 번째 CNAME 레코드 만들기](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="d9b6d-215">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-215">Select **add record**.</span></span>
    
    ![레코드 추가 선택](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="d9b6d-217">나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="d9b6d-218">여전히 **DNS 레코드** 추가 섹션에서 표의 다음 행 값을 사용하여 레코드를 만든  다음 레코드 추가를 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="d9b6d-219">6개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d9b6d-220">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d9b6d-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d9b6d-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d9b6d-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9b6d-222">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d9b6d-223">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d9b6d-224">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d9b6d-225">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="d9b6d-226">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="d9b6d-226">Need examples?</span></span> <span data-ttu-id="d9b6d-227">[Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="d9b6d-228">SPF 레코드의 유효성을 검사하기 위해 다음 SPF 유효성 검사 도구 중[하나를 사용할 수 있습니다.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="d9b6d-229">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="d9b6d-230">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d9b6d-231">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="d9b6d-232">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="d9b6d-233">domain_name ***_ 영역의 _* DNS 영역** 편집기 행에서 DNS 레코드 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-233">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="d9b6d-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d9b6d-235">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="d9b6d-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-236">**Host Record**</span></span>|<span data-ttu-id="d9b6d-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-237">**TTL**</span></span>|<span data-ttu-id="d9b6d-238">**종류**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-238">**Type**</span></span>|<span data-ttu-id="d9b6d-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d9b6d-240">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-240">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-241">TXT</span><span class="sxs-lookup"><span data-stu-id="d9b6d-241">TXT</span></span>  <br/> |<span data-ttu-id="d9b6d-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d9b6d-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="d9b6d-243">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![TXT 값 복사](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="d9b6d-245">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-245">Select **add record**.</span></span>
    
    ![레코드 추가 선택](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d9b6d-247">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="d9b6d-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d9b6d-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d9b6d-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d9b6d-249">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="d9b6d-250">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d9b6d-251">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="d9b6d-252">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="d9b6d-253">domain_name ***_ 영역의 _* DNS 영역** 편집기 행에서 DNS 레코드 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-253">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="d9b6d-254">2개의 SRV 레코드 중 첫 번째 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="d9b6d-255">**DNS 영역 편집기** 페이지의 **DNS 레코드 추가** 영역에서 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d9b6d-256">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d9b6d-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d9b6d-257">**서비스**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-257">**Service**</span></span>|<span data-ttu-id="d9b6d-258">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-258">**Protocol**</span></span>|<span data-ttu-id="d9b6d-259">**호스트**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-259">**Host**</span></span>|<span data-ttu-id="d9b6d-260">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-260">**TTL**</span></span>|<span data-ttu-id="d9b6d-261">**종류**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-261">**Type**</span></span>|<span data-ttu-id="d9b6d-262">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-262">**Priority**</span></span>|<span data-ttu-id="d9b6d-263">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-263">**Weight**</span></span>|<span data-ttu-id="d9b6d-264">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-264">**Port**</span></span>|<span data-ttu-id="d9b6d-265">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d9b6d-266">_sip</span><span class="sxs-lookup"><span data-stu-id="d9b6d-266">_sip</span></span>  <br/> |<span data-ttu-id="d9b6d-267">_tls</span><span class="sxs-lookup"><span data-stu-id="d9b6d-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="d9b6d-268">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-268">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-269">SRV</span><span class="sxs-lookup"><span data-stu-id="d9b6d-269">SRV</span></span>  <br/> |<span data-ttu-id="d9b6d-270">100</span><span class="sxs-lookup"><span data-stu-id="d9b6d-270">100</span></span>  <br/> |<span data-ttu-id="d9b6d-271">1 </span><span class="sxs-lookup"><span data-stu-id="d9b6d-271">1</span></span>  <br/> |<span data-ttu-id="d9b6d-272">443</span><span class="sxs-lookup"><span data-stu-id="d9b6d-272">443</span></span>  <br/> |<span data-ttu-id="d9b6d-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d9b6d-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d9b6d-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d9b6d-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="d9b6d-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="d9b6d-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="d9b6d-276">14400</span><span class="sxs-lookup"><span data-stu-id="d9b6d-276">14400</span></span>  <br/> |<span data-ttu-id="d9b6d-277">SRV</span><span class="sxs-lookup"><span data-stu-id="d9b6d-277">SRV</span></span>  <br/> |<span data-ttu-id="d9b6d-278">100</span><span class="sxs-lookup"><span data-stu-id="d9b6d-278">100</span></span>  <br/> |<span data-ttu-id="d9b6d-279">1 </span><span class="sxs-lookup"><span data-stu-id="d9b6d-279">1</span></span>  <br/> |<span data-ttu-id="d9b6d-280">5061</span><span class="sxs-lookup"><span data-stu-id="d9b6d-280">5061</span></span>  <br/> |<span data-ttu-id="d9b6d-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d9b6d-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![새 레코드의 값 복사](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="d9b6d-283">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9b6d-283">Select **add record**.</span></span>
    
    ![레코드 추가 선택](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="d9b6d-285">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="d9b6d-286">여전히 **DNS 레코드** 추가 섹션에서 표의 다른 행 값을 사용하여 레코드를 만든  다음 레코드 추가를 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d9b6d-287">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-287">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d9b6d-288">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-288">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d9b6d-289">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b6d-289">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

