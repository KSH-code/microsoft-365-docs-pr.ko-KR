---
title: Microsoft에 대 한 Google 도메인에서 DNS 레코드 만들기
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Microsoft의 Google Domains에서 도메인을 확인 하 고 전자 메일, Lync 및 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 399482374f87d864edbc01feb4896b168d157f7f
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919751"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="4f7fc-103">Microsoft에 대 한 Google 도메인에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="4f7fc-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="4f7fc-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4f7fc-105">DNS 호스팅 공급자로 Google Domains를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, Lync 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="4f7fc-106">Google Domains에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="4f7fc-107">Microsoft에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Microsoft에서 공개 웹 사이트 사용하기](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f7fc-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4f7fc-109">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4f7fc-110">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Microsoft에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4f7fc-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="4f7fc-111">Add a TXT record for verification</span></span>
<span data-ttu-id="4f7fc-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4f7fc-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4f7fc-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f7fc-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4f7fc-p104">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="4f7fc-120">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="4f7fc-121">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="4f7fc-122">**My domains (내 도메인** ) 페이지에서 Microsoft와 함께 사용할 도메인을 찾은 다음 옆에 있는 **관리** 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-122">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="4f7fc-123">왼쪽 탐색에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="4f7fc-124">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-124">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4f7fc-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4f7fc-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4f7fc-127">**이름**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-127">**Name**</span></span> <br/> |<span data-ttu-id="4f7fc-128">**종류**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-128">**Type**</span></span> <br/> |<span data-ttu-id="4f7fc-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-129">**TTL**</span></span> <br/> |<span data-ttu-id="4f7fc-130">**데이터**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="4f7fc-131">TXT</span><span class="sxs-lookup"><span data-stu-id="4f7fc-131">TXT</span></span>  <br/> |<span data-ttu-id="4f7fc-132">1H</span><span class="sxs-lookup"><span data-stu-id="4f7fc-132">1H</span></span>  <br/> |<span data-ttu-id="4f7fc-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4f7fc-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4f7fc-134">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-134">**Note:** This is an example.</span></span> <span data-ttu-id="4f7fc-135">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="4f7fc-136">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="4f7fc-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="4f7fc-137">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="4f7fc-138">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4f7fc-139">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="4f7fc-140">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4f7fc-141">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4f7fc-142">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4f7fc-143">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4f7fc-144">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4f7fc-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4f7fc-146">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4f7fc-147">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4f7fc-148">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="4f7fc-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4f7fc-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4f7fc-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4f7fc-p108">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="4f7fc-153">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="4f7fc-154">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="4f7fc-155">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4f7fc-156">G Suite 전자 메일 계정이 있는 경우 먼저 해당 계정과 연결된 MX 레코드를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-156">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="4f7fc-157">G Suite MX 레코드를 통해 Microsoft에 필요한 다른 MX 레코드를 추가 하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-157">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="4f7fc-158">G Suite 레코드를 삭제한다고 해서 G Suite 계정이 삭제되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-158">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="4f7fc-159">G Suite MX 레코드를 삭제하려면 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-159">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="4f7fc-160">**가상 레코드** 섹션의 **G Suite** 영역에서 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="4f7fc-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-161">(You may have to scroll down.)</span></span>
    
    ![가상 레코드 섹션에서 삭제를 선택 합니다.](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="4f7fc-163">**삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-163">Select **Delete**.</span></span>
    
    ![삭제 선택](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="4f7fc-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4f7fc-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4f7fc-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4f7fc-168">**이름**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-168">**Name**</span></span>|<span data-ttu-id="4f7fc-169">**종류**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-169">**Type**</span></span>|<span data-ttu-id="4f7fc-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-170">**TTL**</span></span>|<span data-ttu-id="4f7fc-171">**데이터**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4f7fc-172">MX</span><span class="sxs-lookup"><span data-stu-id="4f7fc-172">MX</span></span>  <br/> |<span data-ttu-id="4f7fc-173">1H</span><span class="sxs-lookup"><span data-stu-id="4f7fc-173">1H</span></span>  <br/> |<span data-ttu-id="4f7fc-174">0  *\<도메인 키\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="4f7fc-175">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="4f7fc-p110">**0** 은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  </span><span class="sxs-lookup"><span data-stu-id="4f7fc-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="4f7fc-178">**참고:** Microsoft 계정에서 \<*도메인-키*\>를 받으세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-178">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="4f7fc-179">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="4f7fc-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="4f7fc-180">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![사용자 지정 리소스 레코드 구역에 값을 입력 하거나 붙여넣습니다.](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="4f7fc-182">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-182">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="4f7fc-184">다른 사용자 지정 MX 레코드가 있으면 해당 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="4f7fc-185">MX 레코드 행에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-185">Select **Edit** in the MX record row.</span></span> 
    
    ![MX 레코드 행에서 편집을 선택 합니다.](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="4f7fc-187">각각의 다른 사용자 지정 MX 레코드에 대해 **데이터** 상자에서 항목을 선택한 다음 키보드에서 **delete** 키를 눌러 해당 레코드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="4f7fc-188">각각의 다른 MX 레코드에 대한 **데이터** 항목을 삭제할 때까지 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="4f7fc-190">각각의 다른 MX 레코드에 대 한 **데이터** 항목을 삭제 한 경우 **저장** 을 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![저장을 선택](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4f7fc-192">Microsoft에 필요한 5 개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="4f7fc-192">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="4f7fc-193">시작 하려면 [Google Domains page]https://domains.google.com/registrar) 로 이동 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="4f7fc-194">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4f7fc-195">첫 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="4f7fc-196">**사용자 지정 리소스 레코드** 구역의 새 레코드 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="4f7fc-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4f7fc-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4f7fc-199">**이름**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-199">**Name**</span></span>|<span data-ttu-id="4f7fc-200">**종류**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-200">**Type**</span></span>|<span data-ttu-id="4f7fc-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-201">**TTL**</span></span>|<span data-ttu-id="4f7fc-202">**Data(데이터)**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4f7fc-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4f7fc-203">autodiscover</span></span>  <br/> |<span data-ttu-id="4f7fc-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f7fc-204">CNAME</span></span>  <br/> |<span data-ttu-id="4f7fc-205">1H</span><span class="sxs-lookup"><span data-stu-id="4f7fc-205">1H</span></span>  <br/> |<span data-ttu-id="4f7fc-206">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4f7fc-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="4f7fc-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4f7fc-208">sip</span><span class="sxs-lookup"><span data-stu-id="4f7fc-208">sip</span></span>  <br/> |<span data-ttu-id="4f7fc-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f7fc-209">CNAME</span></span>  <br/> |<span data-ttu-id="4f7fc-210">1H</span><span class="sxs-lookup"><span data-stu-id="4f7fc-210">1H</span></span>  <br/> |<span data-ttu-id="4f7fc-211">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4f7fc-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4f7fc-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4f7fc-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4f7fc-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4f7fc-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f7fc-214">CNAME</span></span>  <br/> |<span data-ttu-id="4f7fc-215">1H</span><span class="sxs-lookup"><span data-stu-id="4f7fc-215">1H</span></span>  <br/> |<span data-ttu-id="4f7fc-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4f7fc-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4f7fc-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4f7fc-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4f7fc-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4f7fc-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f7fc-219">CNAME</span></span>  <br/> |<span data-ttu-id="4f7fc-220">1H</span><span class="sxs-lookup"><span data-stu-id="4f7fc-220">1H</span></span>  <br/> |<span data-ttu-id="4f7fc-221">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4f7fc-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="4f7fc-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4f7fc-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4f7fc-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4f7fc-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f7fc-224">CNAME</span></span>  <br/> |<span data-ttu-id="4f7fc-225">1H</span><span class="sxs-lookup"><span data-stu-id="4f7fc-225">1H</span></span>  <br/> |<span data-ttu-id="4f7fc-226">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4f7fc-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="4f7fc-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![사용자 지정 리소스 레코드 구역에 값을 입력 하거나 붙여넣습니다.](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="4f7fc-229">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-229">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="4f7fc-231">나머지 4개의 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="4f7fc-232">**사용자 지정 리소스 레코드** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="4f7fc-233">필요한 CNAME 레코드를 모두 만들 때까지이 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4f7fc-234">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="4f7fc-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f7fc-235">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4f7fc-236">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4f7fc-237">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-237">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4f7fc-238">대신, 필수 Microsoft 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 단일 SPF 레코드가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-238">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="4f7fc-239">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="4f7fc-239">Need examples?</span></span> <span data-ttu-id="4f7fc-240">[Microsoft에 대한 외부 Domain Name System 레코드](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-240">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="4f7fc-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fc-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="4f7fc-p113">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="4f7fc-245">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="4f7fc-246">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="4f7fc-247">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="4f7fc-248">**사용자 지정 리소스 레코드** 구역의 TXT 레코드 행에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="4f7fc-p114">Google Domains에서는 여러 레코드를 포함할 수 있는 집합으로 TXT 레코드를 저장합니다. 도메인을 확인하는 데 사용한 TXT 레코드와 같은 다른 TXT 레코드가 하나 이상 있는 경우 해당 레코드 집합에 새 TXT 레코드를 추가해야 합니다. 추가 TXT 레코드를 개별 항목으로 입력하려고 하면 **중복 레코드** 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![TXT 레코드 행에서 편집을 선택 합니다.](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="4f7fc-253">**(+)** 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-253">Select the **(+)** control.</span></span> 
    
    ![더하기 컨트롤 선택](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="4f7fc-255">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4f7fc-256">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="4f7fc-257">**Data(데이터)**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="4f7fc-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4f7fc-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="4f7fc-259">모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![사용자 지정 리소스 레코드 구역에 값을 입력 하거나 붙여넣습니다.](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="4f7fc-261">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-261">Select **Save**.</span></span>
    
    ![저장을 선택](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4f7fc-263">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="4f7fc-263">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4f7fc-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4f7fc-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="4f7fc-p115">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="4f7fc-268">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="4f7fc-269">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="4f7fc-270">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="4f7fc-271">첫 번째 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="4f7fc-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4f7fc-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4f7fc-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4f7fc-275">**이름**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-275">**Name**</span></span>|<span data-ttu-id="4f7fc-276">**종류**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-276">**Type**</span></span>|<span data-ttu-id="4f7fc-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-277">**TTL**</span></span>|<span data-ttu-id="4f7fc-278">**데이터**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4f7fc-279">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="4f7fc-279">_sip._tls</span></span>|<span data-ttu-id="4f7fc-280">SRV</span><span class="sxs-lookup"><span data-stu-id="4f7fc-280">SRV</span></span>|<span data-ttu-id="4f7fc-281">1H</span><span class="sxs-lookup"><span data-stu-id="4f7fc-281">1H</span></span>|<span data-ttu-id="4f7fc-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="4f7fc-283">**이 값은 마침표 (.)로 끝나야 합니다.** **참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="4f7fc-284">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="4f7fc-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="4f7fc-285">SRV</span><span class="sxs-lookup"><span data-stu-id="4f7fc-285">SRV</span></span>|<span data-ttu-id="4f7fc-286">1H</span><span class="sxs-lookup"><span data-stu-id="4f7fc-286">1H</span></span>|<span data-ttu-id="4f7fc-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="4f7fc-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4f7fc-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="4f7fc-289">모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![사용자 지정 리소스 레코드 구역에 값을 입력 하거나 붙여넣습니다.](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="4f7fc-291">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-291">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="4f7fc-293">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="4f7fc-294">**사용자 지정 리소스 레코드** 구역에서 표의 두 번째 행 값을 사용 하 여 레코드를 만든 다음 다시 **추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4f7fc-295">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4f7fc-296">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4f7fc-297">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7fc-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
