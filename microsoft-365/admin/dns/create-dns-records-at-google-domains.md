---
title: Google 도메인에서 Office 365용 DNS 레코드 만들기
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: 도메인을 확인 하 고 Office 365 용 Google Domains의 전자 메일, Lync 및 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: c59a3d63797f20b0d3a42647eb68d7699ed63450
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249031"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a><span data-ttu-id="91778-103">Google 도메인에서 Office 365용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="91778-103">Create DNS records at Google Domains for Office 365</span></span>

 <span data-ttu-id="91778-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="91778-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="91778-105">DNS 호스팅 공급자로 Google Domains를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, Lync 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="91778-106">Google Domains에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="91778-106">After you add these records at Google Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="91778-107">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91778-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="91778-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="91778-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="91778-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="91778-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="91778-110">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91778-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="91778-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="91778-111">Add a TXT record for verification</span></span>
<span data-ttu-id="91778-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="91778-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="91778-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="91778-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="91778-p104">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="91778-120">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="91778-121">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="91778-122">**내 도메인** 페이지에서 Office 365에서 사용 하려는 도메인을 찾은 다음 옆에 있는 **관리** 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-122">On the **My domains** page, find the domain you want to use with Office 365, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="91778-123">왼쪽 탐색에서 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="91778-124">\* \* Custom resource records \* \* 섹션의 새 레코드 용 상자에 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="91778-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="91778-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="91778-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="91778-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="91778-127">**이름**</span><span class="sxs-lookup"><span data-stu-id="91778-127">**Name**</span></span> <br/> |<span data-ttu-id="91778-128">**종류**</span><span class="sxs-lookup"><span data-stu-id="91778-128">**Type**</span></span> <br/> |<span data-ttu-id="91778-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="91778-129">**TTL**</span></span> <br/> |<span data-ttu-id="91778-130">**데이터**</span><span class="sxs-lookup"><span data-stu-id="91778-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="91778-131">TXT</span><span class="sxs-lookup"><span data-stu-id="91778-131">TXT</span></span>  <br/> |<span data-ttu-id="91778-132">1H</span><span class="sxs-lookup"><span data-stu-id="91778-132">1H</span></span>  <br/> |<span data-ttu-id="91778-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="91778-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="91778-134">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-134">**Note:** This is an example.</span></span> <span data-ttu-id="91778-135">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="91778-136">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="91778-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="91778-137">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="91778-138">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="91778-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="91778-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="91778-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="91778-140">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="91778-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="91778-141">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="91778-142">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="91778-143">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="91778-144">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="91778-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="91778-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="91778-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="91778-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="91778-147">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91778-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="91778-148">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="91778-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="91778-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="91778-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="91778-p108">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="91778-153">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="91778-154">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="91778-155">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="91778-p109">G Suite 전자 메일 계정이 있는 경우 먼저 해당 계정과 연결된 MX 레코드를 삭제해야 합니다. G Suite MX 레코드는 Office 365에 필요한 MX 레코드를 비롯한 다른 모든 MX 레코드를 추가하지 못하게 합니다. G Suite 레코드를 삭제한다고 해서 G Suite 계정이 삭제되지는 않습니다. G Suite MX 레코드를 삭제하려면 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="91778-p109">If you have a G Suite email account, you must first delete the MX records associated with that account. The G Suite MX records prevent you from adding any other MX records, including those required for Office 365. Note that deleting the G Suite records does not delete your G Suite account. To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="91778-160">**가상 레코드** 섹션의 **G Suite** 영역에서 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="91778-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="91778-161">(You may have to scroll down.)</span></span>
    
    ![가상 레코드 섹션에서 삭제를 선택 합니다.](../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="91778-163">**삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-163">Select **Delete**.</span></span>
    
    ![삭제 선택](../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="91778-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="91778-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="91778-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="91778-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="91778-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="91778-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="91778-168">**이름**</span><span class="sxs-lookup"><span data-stu-id="91778-168">**Name**</span></span>|<span data-ttu-id="91778-169">**종류**</span><span class="sxs-lookup"><span data-stu-id="91778-169">**Type**</span></span>|<span data-ttu-id="91778-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="91778-170">**TTL**</span></span>|<span data-ttu-id="91778-171">**데이터**</span><span class="sxs-lookup"><span data-stu-id="91778-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="91778-172">MX</span><span class="sxs-lookup"><span data-stu-id="91778-172">MX</span></span>  <br/> |<span data-ttu-id="91778-173">1H</span><span class="sxs-lookup"><span data-stu-id="91778-173">1H</span></span>  <br/> |<span data-ttu-id="91778-174">0  *\<도메인 키\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="91778-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="91778-175">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="91778-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="91778-p110">**0** 은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  </span><span class="sxs-lookup"><span data-stu-id="91778-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="91778-178">**참고:** \<Office 365 계정에서 *도메인 키* \> 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91778-178">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span>  [<span data-ttu-id="91778-179">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="91778-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="91778-180">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91778-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![사용자 지정 리소스 레코드 구역에 값을 입력 하거나 붙여넣습니다.](../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="91778-182">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-182">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="91778-184">다른 사용자 지정 MX 레코드가 있으면 해당 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="91778-185">MX 레코드 행에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-185">Select **Edit** in the MX record row.</span></span> 
    
    ![MX 레코드 행에서 편집을 선택 합니다.](../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="91778-187">각각의 다른 사용자 지정 MX 레코드에 대해 **데이터** 상자에서 항목을 선택한 다음 키보드에서 **delete** 키를 눌러 해당 레코드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="91778-188">각각의 다른 MX 레코드에 대한 **데이터** 항목을 삭제할 때까지 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="91778-190">각각의 다른 MX 레코드에 대 한 **데이터** 항목을 삭제 한 경우 **저장** 을 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![저장을 선택](../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="91778-192">Office 365에 필요한 다섯 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-192">Add the five CNAME records that are required for Office 365</span></span>

1. <span data-ttu-id="91778-193">시작 하려면 [Google Domains page]https://domains.google.com/registrar) 로 이동 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="91778-194">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="91778-195">첫 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="91778-196">**사용자 지정 리소스 레코드** 구역의 새 레코드 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="91778-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="91778-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="91778-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="91778-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="91778-199">**이름**</span><span class="sxs-lookup"><span data-stu-id="91778-199">**Name**</span></span>|<span data-ttu-id="91778-200">**종류**</span><span class="sxs-lookup"><span data-stu-id="91778-200">**Type**</span></span>|<span data-ttu-id="91778-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="91778-201">**TTL**</span></span>|<span data-ttu-id="91778-202">**Data(데이터)**</span><span class="sxs-lookup"><span data-stu-id="91778-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="91778-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="91778-203">autodiscover</span></span>  <br/> |<span data-ttu-id="91778-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="91778-204">CNAME</span></span>  <br/> |<span data-ttu-id="91778-205">1H</span><span class="sxs-lookup"><span data-stu-id="91778-205">1H</span></span>  <br/> |<span data-ttu-id="91778-206">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="91778-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="91778-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="91778-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="91778-208">sip</span><span class="sxs-lookup"><span data-stu-id="91778-208">sip</span></span>  <br/> |<span data-ttu-id="91778-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="91778-209">CNAME</span></span>  <br/> |<span data-ttu-id="91778-210">1H</span><span class="sxs-lookup"><span data-stu-id="91778-210">1H</span></span>  <br/> |<span data-ttu-id="91778-211">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="91778-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="91778-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="91778-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="91778-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="91778-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="91778-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="91778-214">CNAME</span></span>  <br/> |<span data-ttu-id="91778-215">1H</span><span class="sxs-lookup"><span data-stu-id="91778-215">1H</span></span>  <br/> |<span data-ttu-id="91778-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="91778-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="91778-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="91778-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="91778-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="91778-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="91778-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="91778-219">CNAME</span></span>  <br/> |<span data-ttu-id="91778-220">1H</span><span class="sxs-lookup"><span data-stu-id="91778-220">1H</span></span>  <br/> |<span data-ttu-id="91778-221">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="91778-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="91778-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="91778-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="91778-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="91778-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="91778-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="91778-224">CNAME</span></span>  <br/> |<span data-ttu-id="91778-225">1H</span><span class="sxs-lookup"><span data-stu-id="91778-225">1H</span></span>  <br/> |<span data-ttu-id="91778-226">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="91778-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="91778-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="91778-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![사용자 지정 리소스 레코드 구역에 값을 입력 하거나 붙여넣습니다.](../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="91778-229">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-229">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="91778-231">나머지 4개의 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="91778-232">**사용자 지정 리소스 레코드** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="91778-233">필요한 CNAME 레코드를 모두 만들 때까지이 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="91778-234">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="91778-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91778-235">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="91778-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="91778-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="91778-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="91778-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="91778-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="91778-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="91778-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="91778-239">Need examples?</span><span class="sxs-lookup"><span data-stu-id="91778-239">Need examples?</span></span> <span data-ttu-id="91778-240">이러한 [외부 도메인 이름 시스템 레코드에서 Office 365를](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="91778-240">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="91778-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="91778-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="91778-p113">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="91778-245">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="91778-246">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="91778-247">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="91778-248">**사용자 지정 리소스 레코드** 구역의 TXT 레코드 행에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="91778-p114">Google Domains에서는 여러 레코드를 포함할 수 있는 집합으로 TXT 레코드를 저장합니다. 도메인을 확인하는 데 사용한 TXT 레코드와 같은 다른 TXT 레코드가 하나 이상 있는 경우 해당 레코드 집합에 새 TXT 레코드를 추가해야 합니다. 추가 TXT 레코드를 개별 항목으로 입력하려고 하면 **중복 레코드** 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91778-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![TXT 레코드 행에서 편집을 선택 합니다.](../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="91778-253">**(+)** 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-253">Select the **(+)** control.</span></span> 
    
    ![더하기 컨트롤 선택](../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="91778-255">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="91778-256">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="91778-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="91778-257">**Data(데이터)**</span><span class="sxs-lookup"><span data-stu-id="91778-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="91778-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="91778-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="91778-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span><span class="sxs-lookup"><span data-stu-id="91778-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![사용자 지정 리소스 레코드 구역에 값을 입력 하거나 붙여넣습니다.](../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="91778-261">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-261">Select **Save**.</span></span>
    
    ![저장을 선택](../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="91778-263">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="91778-263">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="91778-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="91778-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="91778-p115">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="91778-268">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="91778-269">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="91778-270">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="91778-271">첫 번째 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="91778-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="91778-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="91778-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="91778-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="91778-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="91778-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="91778-275">**이름**</span><span class="sxs-lookup"><span data-stu-id="91778-275">**Name**</span></span>|<span data-ttu-id="91778-276">**종류**</span><span class="sxs-lookup"><span data-stu-id="91778-276">**Type**</span></span>|<span data-ttu-id="91778-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="91778-277">**TTL**</span></span>|<span data-ttu-id="91778-278">**데이터**</span><span class="sxs-lookup"><span data-stu-id="91778-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="91778-279">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="91778-279">_sip._tls</span></span>|<span data-ttu-id="91778-280">SRV</span><span class="sxs-lookup"><span data-stu-id="91778-280">SRV</span></span>|<span data-ttu-id="91778-281">1H</span><span class="sxs-lookup"><span data-stu-id="91778-281">1H</span></span>|<span data-ttu-id="91778-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="91778-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="91778-283">**이 값은 마침표 (.)로 끝나야 합니다.** **참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="91778-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="91778-284">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="91778-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="91778-285">SRV</span><span class="sxs-lookup"><span data-stu-id="91778-285">SRV</span></span>|<span data-ttu-id="91778-286">1H</span><span class="sxs-lookup"><span data-stu-id="91778-286">1H</span></span>|<span data-ttu-id="91778-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="91778-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="91778-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="91778-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="91778-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span><span class="sxs-lookup"><span data-stu-id="91778-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![사용자 지정 리소스 레코드 구역에 값을 입력 하거나 붙여넣습니다.](../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="91778-291">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-291">Select **Add**.</span></span>
    
    ![추가를 선택 합니다.](../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="91778-293">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="91778-294">**사용자 지정 리소스 레코드** 구역에서 표의 두 번째 행 값을 사용 하 여 레코드를 만든 다음 다시 **추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="91778-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="91778-295">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="91778-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="91778-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="91778-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="91778-297">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91778-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
