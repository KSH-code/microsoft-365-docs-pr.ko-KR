---
title: Dyn.com에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 Dyn.com에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: f9b705f94f05799b0aa97539e372c3efcfe2e4c8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629590"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="3d008-103">Dyn.com에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="3d008-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="3d008-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d008-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3d008-105">DNS 호스팅 공급자로 Dyn.com을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="3d008-106">Microsoft의 웹 사이트에 대 한 호스트 및 DNS에 대 한 자세한 내용은 [microsoft에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d008-106">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3d008-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d008-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3d008-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3d008-110">Add a TXT record for verification</span></span>
<span data-ttu-id="3d008-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3d008-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="3d008-p102">시작하려면 [이 링크](https://account.dyn.com/dns/)를 사용하여 Dyn.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3d008-115">**영역 수준 서비스** 페이지에서 편집할 도메인에 대해 **Dyn Standard DNS 서비스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3d008-116">도메인의 **DNS** 페이지에서 **기본 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3d008-117">**전문가 인터페이스 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3d008-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d008-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d008-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3d008-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d008-120">**호스트**</span><span class="sxs-lookup"><span data-stu-id="3d008-120">**Host**</span></span>|<span data-ttu-id="3d008-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d008-121">**TTL**</span></span>|<span data-ttu-id="3d008-122">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="3d008-122">**Type**</span></span>|<span data-ttu-id="3d008-123">**데이터**</span><span class="sxs-lookup"><span data-stu-id="3d008-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d008-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3d008-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3d008-125">600</span><span class="sxs-lookup"><span data-stu-id="3d008-125">600</span></span>  <br/> |<span data-ttu-id="3d008-126">TXT</span><span class="sxs-lookup"><span data-stu-id="3d008-126">TXT</span></span>  <br/> |<span data-ttu-id="3d008-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3d008-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3d008-128">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-128">**Note:** This is an example.</span></span> <span data-ttu-id="3d008-129">표에서 특정 **대상 또는 지점** 값을 사용 하 여 여기서 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3d008-130">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="3d008-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="3d008-132">**레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="3d008-134">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3d008-135">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3d008-136">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3d008-137">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3d008-138">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3d008-139">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3d008-140">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3d008-p104">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d008-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3d008-144">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3d008-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3d008-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3d008-p105">시작하려면 [이 링크](https://account.dyn.com/dns/)를 사용하여 Dyn.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3d008-149">**영역 수준 서비스** 페이지에서 편집할 도메인에 대해 **Dyn Standard DNS 서비스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3d008-150">도메인의 DNS 페이지에서 **기본 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3d008-151">**전문가 인터페이스 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3d008-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d008-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d008-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3d008-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d008-154">**호스트**</span><span class="sxs-lookup"><span data-stu-id="3d008-154">**Host**</span></span>|<span data-ttu-id="3d008-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d008-155">**TTL**</span></span>|<span data-ttu-id="3d008-156">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="3d008-156">**Type**</span></span>|<span data-ttu-id="3d008-157">**데이터**</span><span class="sxs-lookup"><span data-stu-id="3d008-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d008-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3d008-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3d008-159">600</span><span class="sxs-lookup"><span data-stu-id="3d008-159">600</span></span>  <br/> |<span data-ttu-id="3d008-160">MX</span><span class="sxs-lookup"><span data-stu-id="3d008-160">MX</span></span>  <br/> |<span data-ttu-id="3d008-161">10  *\<도메인 키\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3d008-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3d008-162">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d008-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3d008-p106">**10** 은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  </span><span class="sxs-lookup"><span data-stu-id="3d008-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="3d008-165">**참고:** Microsoft 계정에서 \* \<도메인 키\> \* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="3d008-166">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="3d008-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="3d008-167">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d008-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-구성-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="3d008-169">**레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="3d008-171">다른 MX 레코드가 있으면 **삭제** 열에서 각 레코드의 확인란을 선택하여 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="3d008-173">**변경 내용 적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d008-175">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3d008-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3d008-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3d008-p108">시작하려면 [이 링크](https://account.dyn.com/dns/)를 사용하여 Dyn.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3d008-180">**영역 수준 서비스** 페이지에서 편집할 도메인에 대해 **Dyn Standard DNS 서비스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3d008-181">도메인의 **DNS** 페이지에서 **기본 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3d008-182">**전문가 인터페이스 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3d008-183">6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3d008-184">**DNS 레코드 추가** 구역의 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="3d008-185">(드롭다운 목록에서 **종류** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="3d008-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d008-186">**호스트**</span><span class="sxs-lookup"><span data-stu-id="3d008-186">**Host**</span></span>|<span data-ttu-id="3d008-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d008-187">**TTL**</span></span>|<span data-ttu-id="3d008-188">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="3d008-188">**Type**</span></span>|<span data-ttu-id="3d008-189">**데이터**</span><span class="sxs-lookup"><span data-stu-id="3d008-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d008-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3d008-190">autodiscover</span></span>  <br/> |<span data-ttu-id="3d008-191">600</span><span class="sxs-lookup"><span data-stu-id="3d008-191">600</span></span>  <br/> |<span data-ttu-id="3d008-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d008-192">CNAME</span></span>  <br/> |<span data-ttu-id="3d008-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d008-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3d008-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3d008-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3d008-195">sip</span><span class="sxs-lookup"><span data-stu-id="3d008-195">sip</span></span>  <br/> |<span data-ttu-id="3d008-196">600</span><span class="sxs-lookup"><span data-stu-id="3d008-196">600</span></span>  <br/> |<span data-ttu-id="3d008-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d008-197">CNAME</span></span>  <br/> |<span data-ttu-id="3d008-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d008-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3d008-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3d008-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3d008-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3d008-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3d008-201">600</span><span class="sxs-lookup"><span data-stu-id="3d008-201">600</span></span>  <br/> |<span data-ttu-id="3d008-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d008-202">CNAME</span></span>  <br/> |<span data-ttu-id="3d008-203">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d008-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3d008-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3d008-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3d008-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3d008-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3d008-206">600</span><span class="sxs-lookup"><span data-stu-id="3d008-206">600</span></span>  <br/> |<span data-ttu-id="3d008-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d008-207">CNAME</span></span>  <br/> |<span data-ttu-id="3d008-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3d008-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3d008-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3d008-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3d008-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3d008-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3d008-211">600</span><span class="sxs-lookup"><span data-stu-id="3d008-211">600</span></span>  <br/> |<span data-ttu-id="3d008-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d008-212">CNAME</span></span>  <br/> |<span data-ttu-id="3d008-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3d008-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3d008-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3d008-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-구성-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="3d008-216">**레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="3d008-218">나머지 CNAME 레코드 다섯 개를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="3d008-219">**DNS 레코드 추가** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **레코드 만들기** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="3d008-220">6개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3d008-221">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3d008-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3d008-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3d008-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d008-223">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3d008-224">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3d008-225">도메인에 대 한 SPF 레코드가 이미 있는 경우 Microsoft에 대해 새로 만들지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="3d008-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3d008-226">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="3d008-p110">시작하려면 [이 링크](https://account.dyn.com/dns/)를 사용하여 Dyn.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3d008-230">**영역 수준 서비스** 페이지에서 편집할 도메인에 대해 **Dyn Standard DNS 서비스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3d008-231">도메인의 **DNS** 페이지에서 **기본 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3d008-232">**전문가 인터페이스 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3d008-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d008-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3d008-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3d008-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d008-235">**호스트**</span><span class="sxs-lookup"><span data-stu-id="3d008-235">**Host**</span></span>|<span data-ttu-id="3d008-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d008-236">**TTL**</span></span>|<span data-ttu-id="3d008-237">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="3d008-237">**Type**</span></span>|<span data-ttu-id="3d008-238">**데이터**</span><span class="sxs-lookup"><span data-stu-id="3d008-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d008-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3d008-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3d008-240">600</span><span class="sxs-lookup"><span data-stu-id="3d008-240">600</span></span>  <br/> |<span data-ttu-id="3d008-241">TXT</span><span class="sxs-lookup"><span data-stu-id="3d008-241">TXT</span></span>  <br/> |<span data-ttu-id="3d008-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3d008-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3d008-243">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-구성-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="3d008-245">**레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-245">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3d008-247">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3d008-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3d008-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3d008-249">시작하려면 [이 링크](https://account.dyn.com/dns/)를 사용하여 Dyn.com의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="3d008-250">먼저 로그인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3d008-252">**영역 수준 서비스** 페이지에서 편집할 도메인에 대해 **Dyn Standard DNS 서비스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3d008-253">도메인의 **DNS** 페이지에서 **기본 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3d008-254">**전문가 인터페이스 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3d008-255">2개의 SRV 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3d008-256">**DNS 레코드 추가** 구역의 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="3d008-257">(드롭다운 목록에서 **종류** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="3d008-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d008-258">**호스트**</span><span class="sxs-lookup"><span data-stu-id="3d008-258">**Host**</span></span>|<span data-ttu-id="3d008-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3d008-259">**TTL**</span></span>|<span data-ttu-id="3d008-260">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="3d008-260">**Type**</span></span>|<span data-ttu-id="3d008-261">**데이터**</span><span class="sxs-lookup"><span data-stu-id="3d008-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d008-262">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="3d008-262">_sip._tls</span></span>|<span data-ttu-id="3d008-263">600</span><span class="sxs-lookup"><span data-stu-id="3d008-263">600</span></span>|<span data-ttu-id="3d008-264">SRV</span><span class="sxs-lookup"><span data-stu-id="3d008-264">SRV</span></span>|<span data-ttu-id="3d008-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3d008-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="3d008-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3d008-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="3d008-267">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="3d008-268">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="3d008-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3d008-269">600</span><span class="sxs-lookup"><span data-stu-id="3d008-269">600</span></span>|<span data-ttu-id="3d008-270">SRV</span><span class="sxs-lookup"><span data-stu-id="3d008-270">SRV</span></span>|<span data-ttu-id="3d008-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3d008-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="3d008-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3d008-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="3d008-273">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-구성-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="3d008-275">**레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="3d008-277">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3d008-278">**DNS 레코드 추가** 구역에서 표의 두 번째 행 값을 사용 하 여 레코드를 만들고 다시 **레코드 만들기** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d008-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="3d008-p114">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d008-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
