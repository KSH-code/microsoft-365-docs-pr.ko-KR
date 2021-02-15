---
title: Microsoft용 Google 도메인에서 DNS 레코드 만들기
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Microsoft용 Google 도메인에서 도메인을 확인하고 전자 메일용 DNS 레코드를 설정하고, Lync 및 기타 서비스를 설정하는 법을 알아봅니다.
ms.openlocfilehash: a20b08d92814865cee5b169cb435b898a6b068ac
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657866"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="751ce-103">Microsoft용 Google 도메인에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="751ce-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="751ce-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="751ce-105">DNS 호스팅 공급자로 Google Domains를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, Lync 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="751ce-106">Google Domains에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="751ce-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="751ce-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="751ce-108">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="751ce-109">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Microsoft에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="751ce-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="751ce-110">Add a TXT record for verification</span></span>
<span data-ttu-id="751ce-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="751ce-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="751ce-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="751ce-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="751ce-p104">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="751ce-119">**로그인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="751ce-120">로그인 자격 증명을 입력하고 다시 **로그인** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="751ce-121">**내 도메인** 페이지에서 Microsoft에 사용할 도메인을 찾고 옆에 있는 **관리** 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="751ce-122">왼쪽 탐색 창에서 **DNS** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="751ce-123">
            \*\*사용자 지정 리소스 레코드\*\* 구역의 새 레코드 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="751ce-124">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="751ce-125">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="751ce-126">**이름**</span><span class="sxs-lookup"><span data-stu-id="751ce-126">**Name**</span></span> <br/> |<span data-ttu-id="751ce-127">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="751ce-127">**Type**</span></span> <br/> |<span data-ttu-id="751ce-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="751ce-128">**TTL**</span></span> <br/> |<span data-ttu-id="751ce-129">**데이터**</span><span class="sxs-lookup"><span data-stu-id="751ce-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="751ce-130">TXT</span><span class="sxs-lookup"><span data-stu-id="751ce-130">TXT</span></span>  <br/> |<span data-ttu-id="751ce-131">1H</span><span class="sxs-lookup"><span data-stu-id="751ce-131">1H</span></span>  <br/> |<span data-ttu-id="751ce-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="751ce-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="751ce-133">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-133">**Note:** This is an example.</span></span> <span data-ttu-id="751ce-134">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="751ce-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="751ce-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="751ce-136">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="751ce-137">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="751ce-138">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="751ce-139">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="751ce-140">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="751ce-141">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="751ce-142">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="751ce-143">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="751ce-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="751ce-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="751ce-145">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="751ce-146">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="751ce-147">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="751ce-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="751ce-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="751ce-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="751ce-p108">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="751ce-152">**로그인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="751ce-153">로그인 자격 증명을 입력하고 다시 **로그인** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="751ce-154">**도메인** 페이지의 **도메인** 구역에서 편집할 도메인에 대해 **DNS 구성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="751ce-155">G Suite 전자 메일 계정이 있는 경우 먼저 해당 계정과 연결된 MX 레코드를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="751ce-156">G Suite MX 레코드는 Microsoft에 필요한 MX 레코드를 비롯한 다른 모든 MX 레코드를 추가하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="751ce-157">G Suite 레코드를 삭제한다고 해서 G Suite 계정이 삭제되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="751ce-158">G Suite MX 레코드를 삭제하려면 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="751ce-159">먼저 **G Suite** 영역의 **가상 레코드** 섹션에서 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="751ce-160">(아래로 스크롤 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-160">(You may have to scroll down.)</span></span>
    
    ![가상 레코드 구역에서 삭제를 선택합니다.](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="751ce-162">**삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-162">Select **Delete**.</span></span>
    
    ![삭제를 선택합니다.](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="751ce-164">
            \*\*사용자 지정 리소스 레코드\*\* 구역의 새 레코드 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="751ce-165">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="751ce-166">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="751ce-167">**이름**</span><span class="sxs-lookup"><span data-stu-id="751ce-167">**Name**</span></span>|<span data-ttu-id="751ce-168">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="751ce-168">**Type**</span></span>|<span data-ttu-id="751ce-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="751ce-169">**TTL**</span></span>|<span data-ttu-id="751ce-170">**데이터**</span><span class="sxs-lookup"><span data-stu-id="751ce-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="751ce-171">MX</span><span class="sxs-lookup"><span data-stu-id="751ce-171">MX</span></span>  <br/> |<span data-ttu-id="751ce-172">1H</span><span class="sxs-lookup"><span data-stu-id="751ce-172">1H</span></span>  <br/> |<span data-ttu-id="751ce-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="751ce-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="751ce-174">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="751ce-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="751ce-p110">**0** 은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  </span><span class="sxs-lookup"><span data-stu-id="751ce-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="751ce-177">**참고:** Microsoft 계정에서 \<*domain-key*\>을(를) 받으세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="751ce-178">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="751ce-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="751ce-179">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![사용자 지정 리소스 레코드 섹션에 값을 입력하거나 붙여넣습니다.](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="751ce-181">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-181">Select **Add**.</span></span>
    
    ![추가를 선택합니다.](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="751ce-183">다른 사용자 지정 MX 레코드가 있으면 해당 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="751ce-184">TXT 레코드 행에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-184">Select **Edit** in the MX record row.</span></span> 
    
    ![TXT 레코드 행에서 편집을 선택 합니다.](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="751ce-186">각각의 다른 사용자 지정 MX 레코드에 대한 **데이터** 상자의 항목을 선택하고 키보드에서 **삭제** 키를 눌러 해당 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="751ce-187">각각의 다른 MX 레코드에 대한 **데이터** 항목을 삭제할 때까지 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="751ce-189">각각의 다른 MX 레코드에 대한 **데이터** 항목을 삭제한 경우 **저장** 을 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![저장을 선택합니다.](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="751ce-191">Microsoft에 필요한 5개의 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="751ce-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="751ce-192">시작하려면, [Google Domains 페이지]로 이동하고 (https://domains.google.com/registrar) 로그인하세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="751ce-193">**도메인** 페이지의 **도메인** 구역에서 편집할 도메인에 대해 **DNS 구성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="751ce-194">첫 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="751ce-195">
            \*\*사용자 지정 리소스 레코드\*\* 구역의 새 레코드 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="751ce-196">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="751ce-197">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="751ce-198">**이름**</span><span class="sxs-lookup"><span data-stu-id="751ce-198">**Name**</span></span>|<span data-ttu-id="751ce-199">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="751ce-199">**Type**</span></span>|<span data-ttu-id="751ce-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="751ce-200">**TTL**</span></span>|<span data-ttu-id="751ce-201">**데이터**</span><span class="sxs-lookup"><span data-stu-id="751ce-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="751ce-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="751ce-202">autodiscover</span></span>  <br/> |<span data-ttu-id="751ce-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="751ce-203">CNAME</span></span>  <br/> |<span data-ttu-id="751ce-204">1H</span><span class="sxs-lookup"><span data-stu-id="751ce-204">1H</span></span>  <br/> |<span data-ttu-id="751ce-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="751ce-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="751ce-206">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="751ce-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="751ce-207">sip</span><span class="sxs-lookup"><span data-stu-id="751ce-207">sip</span></span>  <br/> |<span data-ttu-id="751ce-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="751ce-208">CNAME</span></span>  <br/> |<span data-ttu-id="751ce-209">1H</span><span class="sxs-lookup"><span data-stu-id="751ce-209">1H</span></span>  <br/> |<span data-ttu-id="751ce-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="751ce-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="751ce-211">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="751ce-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="751ce-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="751ce-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="751ce-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="751ce-213">CNAME</span></span>  <br/> |<span data-ttu-id="751ce-214">1H</span><span class="sxs-lookup"><span data-stu-id="751ce-214">1H</span></span>  <br/> |<span data-ttu-id="751ce-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="751ce-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="751ce-216">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="751ce-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="751ce-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="751ce-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="751ce-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="751ce-218">CNAME</span></span>  <br/> |<span data-ttu-id="751ce-219">1H</span><span class="sxs-lookup"><span data-stu-id="751ce-219">1H</span></span>  <br/> |<span data-ttu-id="751ce-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="751ce-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="751ce-221">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="751ce-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="751ce-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="751ce-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="751ce-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="751ce-223">CNAME</span></span>  <br/> |<span data-ttu-id="751ce-224">1H</span><span class="sxs-lookup"><span data-stu-id="751ce-224">1H</span></span>  <br/> |<span data-ttu-id="751ce-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="751ce-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="751ce-226">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="751ce-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![사용자 지정 리소스 레코드 섹션에 값을 입력하거나 붙여넣습니다.](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="751ce-228">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-228">Select **Add**.</span></span>
    
    ![추가를 선택합니다.](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="751ce-230">나머지 4개의 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="751ce-231">**사용자 지정 리소스 레코드** 구역에서 표의 다음 행 값을 사용하여 레코드를 만들고 다시 **추가** 를 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="751ce-232">요청 된 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="751ce-233">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="751ce-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="751ce-234">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="751ce-235">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="751ce-236">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="751ce-237">대신, 필수 Microsoft 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 단일 SPF 레코드가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="751ce-238">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="751ce-238">Need examples?</span></span> <span data-ttu-id="751ce-239">[Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="751ce-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="751ce-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="751ce-p113">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="751ce-244">**로그인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="751ce-245">로그인 자격 증명을 입력하고 다시 **로그인** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="751ce-246">**도메인** 페이지의 **도메인** 구역에서 편집할 도메인에 대해 **DNS 구성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="751ce-247">**사용자 지정 리소스 레코드** 구역의 TXT 레코드 행에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="751ce-p114">Google Domains에서는 여러 레코드를 포함할 수 있는 집합으로 TXT 레코드를 저장합니다. 도메인을 확인하는 데 사용한 TXT 레코드와 같은 다른 TXT 레코드가 하나 이상 있는 경우 해당 레코드 집합에 새 TXT 레코드를 추가해야 합니다. 추가 TXT 레코드를 개별 항목으로 입력하려고 하면 **중복 레코드** 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![TXT 레코드 행에서 편집을 선택 합니다.](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="751ce-252">**(+)** 컨트롤을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="751ce-252">Select the **(+)** control.</span></span> 
    
    ![더하기 관리를 선택](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="751ce-254">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="751ce-255">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="751ce-256">**데이터**</span><span class="sxs-lookup"><span data-stu-id="751ce-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="751ce-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="751ce-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="751ce-258">모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![사용자 지정 리소스 레코드 섹션에 값을 입력하거나 붙여넣습니다.](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="751ce-260">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-260">Select **Save**.</span></span>
    
    ![저장을 선택합니다.](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="751ce-262">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="751ce-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="751ce-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="751ce-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="751ce-p115">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="751ce-267">**로그인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="751ce-268">로그인 자격 증명을 입력하고 다시 **로그인** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="751ce-269">**도메인** 페이지의 **도메인** 구역에서 편집할 도메인에 대해 **DNS 구성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="751ce-270">첫 번째 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="751ce-271">
            \*\*사용자 지정 리소스 레코드\*\* 구역의 새 레코드 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="751ce-272">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="751ce-273">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="751ce-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="751ce-274">**이름**</span><span class="sxs-lookup"><span data-stu-id="751ce-274">**Name**</span></span>|<span data-ttu-id="751ce-275">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="751ce-275">**Type**</span></span>|<span data-ttu-id="751ce-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="751ce-276">**TTL**</span></span>|<span data-ttu-id="751ce-277">**데이터**</span><span class="sxs-lookup"><span data-stu-id="751ce-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="751ce-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="751ce-278">_sip._tls</span></span>|<span data-ttu-id="751ce-279">SRV</span><span class="sxs-lookup"><span data-stu-id="751ce-279">SRV</span></span>|<span data-ttu-id="751ce-280">1H</span><span class="sxs-lookup"><span data-stu-id="751ce-280">1H</span></span>|<span data-ttu-id="751ce-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="751ce-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="751ce-282">**이 값은 마침표(.)로 끝나야 합니다.** **참고:** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="751ce-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="751ce-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="751ce-284">SRV</span><span class="sxs-lookup"><span data-stu-id="751ce-284">SRV</span></span>|<span data-ttu-id="751ce-285">1H</span><span class="sxs-lookup"><span data-stu-id="751ce-285">1H</span></span>|<span data-ttu-id="751ce-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="751ce-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="751ce-287">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="751ce-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="751ce-288">모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![사용자 지정 리소스 레코드 섹션에 값을 입력하거나 붙여넣습니다.](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="751ce-290">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-290">Select **Add**.</span></span>
    
    ![추가를 선택합니다.](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="751ce-292">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="751ce-293">**사용자 지정 리소스 레코드** 구역에서 표의 두 번째 행 값을 사용하여 레코드를 만들고 다시 **추가** 를 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="751ce-294">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="751ce-294">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="751ce-295">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751ce-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="751ce-296">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="751ce-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
