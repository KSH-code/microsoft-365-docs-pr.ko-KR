---
title: MyDomain에서 Office 365용 DNS 레코드 만들기
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: My Domain for Office 365에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype 온라인 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 알아보세요.
ms.openlocfilehash: 1a75c2ab0077cac07781e5102c43e53ed965b1df
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211694"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="6b088-103">MyDomain에서 Office 365용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="6b088-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="6b088-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="6b088-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="6b088-p101">MyDomain 웹 사이트는 SRV 레코드를 지원하지 않습니다. 따라서 일부 비즈니스용 Skype Online 및 Outlook Web App 기능이 작동하지 않습니다. 어떤 Office 365 계획을 사용하든 관계없이 MyDomain에서 DNS 레코드를 관리하는 경우에는 [상당한 서비스 제한 사항](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)이 있으며 다른 DNS 호스팅 공급자로 전환해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="6b088-107">서비스 제한 사항에도 불구하고 MyDomain에서 Office 365 DNS 레코드를 관리하려는 경우 이 문서의 단계를 따라 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="6b088-108">MyDomain에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="6b088-109">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b088-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b088-110">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6b088-110">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6b088-111">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-111">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6b088-112">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b088-112">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6b088-113">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="6b088-113">Add a TXT record for verification</span></span>
<span data-ttu-id="6b088-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6b088-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6b088-p103">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b088-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6b088-p105">시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6b088-121">**내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6b088-122">**도메인**에서 편집할 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6b088-123">**개요** 행에서 **DNS**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6b088-124">**수정** 드롭다운 목록에서 **TXT/SPF 레코드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="6b088-125">
            \*\*콘텐츠\*\* 아래의 새 레코드에 대한 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="6b088-126">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="6b088-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="6b088-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6b088-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6b088-128">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-128">**Note:** This is an example.</span></span> <span data-ttu-id="6b088-129">여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="6b088-130">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="6b088-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="6b088-131">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="6b088-132">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6b088-133">이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="6b088-134">Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6b088-135">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b088-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6b088-136">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6b088-137">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6b088-138">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6b088-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6b088-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6b088-140">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6b088-141">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b088-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="6b088-142">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="6b088-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="6b088-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6b088-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="6b088-p108">시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6b088-146">**내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6b088-147">**도메인**에서 편집할 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6b088-148">**개요** 행에서 **DNS**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6b088-149">
            *\*Modify(수정)*\* 드롭다운 목록에서 \*\*MX Record(MX 레코드)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="6b088-151">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6b088-152">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="6b088-152">**Priority**</span></span>|<span data-ttu-id="6b088-153">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="6b088-153">**Host**</span></span>|<span data-ttu-id="6b088-154">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="6b088-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6b088-155">0</span><span class="sxs-lookup"><span data-stu-id="6b088-155">0</span></span>  <br/> <span data-ttu-id="6b088-156">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b088-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="6b088-157">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6b088-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6b088-158">**참고:** Office 365 계정에서 \<*도메인-키*\>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="6b088-159"> > [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="6b088-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="6b088-161">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="6b088-163">기존의 다른 MX 레코드가 있는 경우 삭제할 각 레코드에 대해 **Action(작업)** 열에서 **Remove(제거)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="6b088-165">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="6b088-167">Office 365에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="6b088-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="6b088-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6b088-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="6b088-p110">시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6b088-171">**내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6b088-172">**도메인**에서 편집할 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6b088-173">**개요** 행에서 **DNS**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6b088-174">
            *\*Modify(수정)*\* 드롭다운 목록에서 \*\*CNAME Alias(CNAME 별칭)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="6b088-176">첫 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="6b088-177">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. </span><span class="sxs-lookup"><span data-stu-id="6b088-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="6b088-178">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="6b088-178">**Host**</span></span>|<span data-ttu-id="6b088-179">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="6b088-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6b088-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6b088-180">autodiscover</span></span>  <br/> |<span data-ttu-id="6b088-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6b088-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="6b088-182">sip</span><span class="sxs-lookup"><span data-stu-id="6b088-182">sip</span></span>  <br/> |<span data-ttu-id="6b088-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6b088-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6b088-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6b088-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6b088-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6b088-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6b088-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6b088-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6b088-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6b088-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="6b088-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6b088-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6b088-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6b088-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="6b088-191">**추가**를 선택하여 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="6b088-193">두 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="6b088-194">위 표의 두 번째 행의 값을 사용한 다음 **추가**를 선택하여 두 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="6b088-195">표의 세 번째, 네 번째, 다섯 번째 및 여섯 번째 행의 값을 사용하여 같은 방법으로 나머지 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6b088-196">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="6b088-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6b088-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6b088-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b088-198">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6b088-199">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6b088-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="6b088-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="6b088-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="6b088-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="6b088-202">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="6b088-202">Need examples?</span></span> <span data-ttu-id="6b088-203">[Office 365에 대한 외부 Domain Name System 레코드](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b088-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="6b088-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="6b088-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="6b088-p112">시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6b088-207">**내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6b088-208">**도메인**에서 편집할 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6b088-209">**개요** 행에서 **DNS**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6b088-210">
            \*\*수정*\* 드롭다운 목록에서 *\*TXT/SPF 레코드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="6b088-212">
            \*\*콘텐츠\*\* 아래의 새 레코드에 대한 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="6b088-213">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="6b088-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="6b088-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6b088-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6b088-215">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="6b088-217">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="6b088-219">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="6b088-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="6b088-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6b088-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="6b088-p113">MyDomain 웹 사이트는 SRV 레코드를 지원하지 않습니다. 따라서 일부 비즈니스용 Skype Online 및 Outlook Web App 기능이 작동하지 않습니다. 어떤 Office 365 계획을 사용하든 관계없이 MyDomain에서 DNS 레코드를 관리하는 경우에는 [상당한 서비스 제한 사항](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)이 있으며 다른 DNS 호스팅 공급자로 전환해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6b088-223">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6b088-223">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6b088-224">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b088-224">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6b088-225">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b088-225">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
